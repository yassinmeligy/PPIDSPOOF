# PPIDSPOOF
PPID Spoofing using the CreateProcess API call with STARTUPINFOEX. 
a POC of PPID spoofing to build a Hunt and Detection technique

While reviewing some defense evasion techniques, I came across an interesting technique that I hadn`t had the opportunity to simulate before. PPID Spoofing  using CreateProcess API call with STARTUPINFOEX we can specify the parent process of the newly created process.
Malware can leverage this to conceal its execution. So I compiled some C++ code to simulate this technique (Thanks to ChatGPT). and I spawned the cmd parent of lsass and other elevated processes. and finally, it works! Is that easy? Yes.
Back to detection, we must admit that many environments may have the visibility required, but it is not being utilized to its best advantage. Sysmon Eventid 1 is the keyword here. Sysmon XML has an "Execution PID" field that can be useful in detecting PPID spoofing.
The key difference between the parent PID and the Execution PID value is a valid detection for this technique, although some Windows utilities use this technique for legitimate purposes like UAC which may introduce some FalsePositve .

Note: This Code is generated by ChatGPT and all right rights received to it 

