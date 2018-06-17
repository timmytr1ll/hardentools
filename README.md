![Hardentools](https://github.com/securitywithoutborders/hardentools/raw/master/graphics/icon%40128.png)

# Hardentools

Hardentools is a collection of simple utilities designed to disable a number of "features" exposed by operating systems (Microsoft Windows, for now), and primary consumer applications. These features, commonly thought for Enterprise customers, are generally useless to regular users and rather pose as dangers as they are very commonly abused by attackers to execute malicious code on a victim's computer. The intent of this tool is to simply reduce the attack surface by disabling the low-hanging fruit. **Hardentools is intended for individuals at risk, who might want an extra level of security at the price of *some* usability**. It is not intended for corporate environments.

> **WARNING**: This is just an experiment, it is not meant for public distribution yet. Also, this tool disables a number of features, including of Microsoft Office, Adobe Reader, and Windows, that might cause malfunctions to certain applications. Use this at your own risk.

Bear in mind, after running Hardentools you won't be able, for example, to do complex calculations with Microsoft Office Excel or use the Command-line terminal, but those are pretty much the only considerable "downsides" of having a slightly safer Windows environment. Before deciding to use it, make sure you read this document thoroughly and understand that yes, something might break. In case you experience malfunctions as a result of the modifications implemented by this tool, please do let us know.

When you're ready, you can find the latest download [here](https://github.com/securitywithoutborders/hardentools/releases).

## How to use it

Once you double-click on the icon, depending on your Windows security settings, you should be prompted with an User Access Control dialog asking you confirmation to allow Hardentools to run. Click "Yes".

![screenshot1](https://github.com/securitywithoutborders/hardentools/raw/master/graphics/screenshot1.png)

Then, you will see the main Hardentools window. It's very simple, you just click on the "Harden" button, and the tool will make the changes to your Windows configuration to disable a set of features that are risky. Once completed, you will be asked to restart your computer for all the changes to have full effect.

![screenshot2](https://github.com/securitywithoutborders/hardentools/raw/master/graphics/screenshot2.png)

In case you wish to restore the original settings and revert the changes Hardentools made (for example, if you need to use cmd.exe), you can simply re-run the tool and instead of an "Harden" button you will be prompted with a "Restore" button. Similarly, click it and wait for the modifications to be reverted.

**Please note**: the modifications made by Hardentools are exclusively contextual to the Windows user account used to run the tool from. In case you want Hardentools to change settings for other Windows users as well, you will have to run it from each one of them logged in.

## What this tool does NOT

- It does NOT prevent software from being exploited.
- It does NOT prevent the abuse of every available risky feature.
- **It is NOT an Antivirus**. It does not protect your computer. It doesn't identify, block, or remove any malware.
- It does NOT prevent the changes it implements from being reverted. If malicious code runs on the system and it is able to restore them, the premise of the tool is defeated, isn't it?


## Disabled Features

### Generic Windows Features

- **Disable Windows Script Host**. Windows Script Host allows the execution of VBScript and Javascript files on Windows operating systems. This is very commonly used by regular malware (such as ransomware) as well as targeted malware.

- **Disabling AutoRun and AutoPlay**. Disables AutoRun / AutoPlay for all devices. For example, this should prevent applicatons from automatically executing when you plug a USB stick into your computer.

- **Disables powershell.exe, powershell_ise.exe and cmd.exe execution via Windows Explorer**. You will not be able to use the terminal and it should prevent the use of PowerShell by malicious code trying to infect the system.

- **Sets User Account Control (UAC) to always ask for permission** (even on configuration changes only) and to use "secure desktop".

- **Disable file extensions mainly used for malicious purposes**. Disables the ".hta", ".js", ".JSE", ".WSH", ".WSF", ".scf", ".scr", ".vbs", ".vbe" and ".pif" file extensions for the current user (and for system wide defaults, which is only relevant for newly created users).

- **Shows file extensions and hidden files in explorer**.

- **Windows Defender Attack Surface Reduction (ASR)**. Enables varios remediations using ASR starting with Windows 10 / 1709 (Block executable content from email client and webmail, Block Office applications from creating child processes, Block Office applications from creating executable content & from injecting code into other processes, Block JavaScript or VBScript from launching downloaded executable content, Block execution of potentially obfuscated scripts, Block Win32 API calls from Office macro)

### Microsoft Office

- **Disable Macros**. Macros are at times used by Microsoft Office users to script and automate certain activities, especially calculations with Microsoft Excel. However, macros are currently a security plague, and they are widely used as a vehicle for compromise. With Hardentools, macros are disabled and the "Enable this Content" notification is disabled too, to prevent users from being tricked.

- **Disable OLE object execution**. Microsoft Office applications are able to embed so called "OLE objects" and execute them, at times also automatically (for example through PowerPoint animations). Windows executables, such as spyware, can also be embedded and executed as an object. This is also a security disaster which we observed used time and time again, particularly in attacks against activists in repressed regions. Hardentools entirely disables this functionality.

- **Disabling ActiveX**. Disables ActiveX Controls for all Office applications.

- **Disable DDE**. Disables DDE for Word and Excel

### Acrobat Reader

- **Disable JavaScript in PDF documents**. Acrobat Reader allows to execute JavaScript code from within PDF documents. This is widely abused for exploitation and malicious activity.

- **Disable execution of objects embedded in PDF documents**. Acrobat Reader also allows to execute embedded objects by opening them. This would normally raise a security alert, but given that legitimate uses of this are rare and limited, Hardentools disables this.

- **Switch on the Protected Mode** (enabled by default in current versions)

- **Switch on Protected View** for all files from untrusted sources

- **Switch on Enhanced Security** (enabled by default in current versions)


## Authors

This tools is developed by Claudio Guarnieri, Mariano Graziano and Florian Probst.
