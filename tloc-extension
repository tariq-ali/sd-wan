# l3 tloc-extension configuration on router-a

interface GigabitEthernet1
 description internet-transport
 no shutdown
 ip address 172.20.0.10 255.255.255.252
 negotiation auto
exit
interface GigabitEthernet2
 description tloc-extension 
 no shutdown
 ip address 172.21.0.5 255.255.255.252
 negotiation auto
exit

interface Tunnel1
 no shutdown
 ip unnumbered GigabitEthernet1
 tunnel source GigabitEthernet1
 tunnel mode sdwan
exit

sdwan
 interface GigabitEthernet1
  tunnel-interface
   encapsulation ipsec
   color public-internet restrict
  exit
  
 interface GigabitEthernet2
  tloc-extension-gre-from 172.21.0.10 xconnect GigabitEthernet1
 exit


# l3 tloc-extension configuration on router-b

 
 interface GigabitEthernet1
 description internet-transport
 no shutdown
 ip address 172.21.0.10 255.255.255.252
 negotiation auto
exit

interface Tunnel1
 no shutdown
 ip unnumbered GigabitEthernet1
 tunnel source GigabitEthernet1
 tunnel mode sdwan

sdwan
 interface GigabitEthernet1
  tunnel-interface
   encapsulation ipsec
   color public-internet restrict
   tloc-extension-gre-to 172.21.0.5
  exit
  
  
