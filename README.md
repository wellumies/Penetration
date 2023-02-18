# Penetration
Links to tools, study material and basic penetration testing process

<h4>Recon</h4>

    #run nmap for default TCP ports. Results to sub-folder "nmap"
      sudo nmap -sC -sV -oA nmap/default -v <IP>
    
    #run nmap for ALL tcp ports. Results to sub-folder "nmap"
      sudo nmap -p- -sC -sV -oA nmap/allports_tcp -v <IP>

    #run nmap for ALL udp ports. Results to sub-folder "nmap"
      sudo nmap -p- -sU -sC -sV nmap/allports_udp -v <IP>
      
    #run gobuster to brute force any subdirectories
      sudo gobuster dir -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -u <URL>
      
    #run gobuster to find filetypes php,bak and txt
      sudo gobuster dir -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt -x php,txt,bak -u <URL>
      
    #run gobuster to find virtual hosts under one IP
      sudo gobuster vhost -w /usr/share/seclists/Discovery/DNS/bitquark-subdomains-top100000.txt -u <FQDN> --append-domain
      
    #run ffuf to find subdomains. Do this by fuzzing the Host-header. Drop responses with size 6359
        sudo ffuf -w /usr/share/seclists/Discovery/DNS/bitquark-subdomains-top100000.txt -u http://interface.htb -H 'Host: FUZZ.interface.htb' -fs 6359
      
      
<h4>Reverse shells</h4>

    #Cheat Sheet for ALOT of reverse shells
    https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md
    
    #Reverse shell generator
    https://www.revshells.com/
    
    #Resources in Kali linux
    /usr/share/seclists/Web-Shells/
    /usr/share/webshells
    
<h4>Privilege escalation</h4>
  
  <h5>Linux</h5>
    
    #find SUID files
      find / -perm /4000 2>/dev/null
  
    #find GUID files
      find / -perm /2000 2>/dev/null
  
    #sudo rights
      sudo -l

    #GTFO binaries. How to bypass local security and privesc
      https://gtfobins.github.io/

    #Download linPEAS
      https://github.com/carlospolop/PEASS-ng/releases
      
  <h5>Windows</h5>
    
    #download winPEAS
    https://github.com/carlospolop/PEASS-ng/releases
  
<h4>General tools</h4>

  #CyberChef. Your favourite online cook
  https://gchq.github.io/CyberChef/
  
  #process spy. See running processes with an unprivileged user
  https://github.com/DominicBreuker/pspy
  
