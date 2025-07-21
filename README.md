# Quake2-MSVC
Quake II original source code rebuild with Visual Studio

## Source files and tools:
Quake 2 v3.21 src: [get](https://web.archive.org/web/20151202082645/ftp://ftp.idsoftware.com/idstuff/source/q2source-3.21.zip "get")<br>
VC 2008 Express: [get](https://download.microsoft.com/download/8/B/5/8B5804AD-4990-40D0-A6AA-CE894CBBB3DC/VS2008ExpressENUX1397868.iso "get")<br>
VC 2010 Express: [get](https://web.archive.org/web/20161014172355/http://download.microsoft.com/download/1/E/5/1E5F1C0A-0D5B-426A-A603-1798B951DDAE/VS2010Express1.iso "get")<br>
VS 2022 Community: [get](https://aka.ms/vs/17/release/vs_community.exe "get")<br>
Windows 2003 DDK 5.2.3790.1830: [get](https://winworldpc.com/product/windows-sdk-ddk/2003-nt-52 "get")<br>

## Steps to build a project:
### Build with VS 2022 Community:
1) Open and upgrade quake2.dsw with VC 2008 Express
2) Open and upgrade quake2.sln with VC 2010 Express
3) Open and upgrade quake2.sln with VS 2022 Community
4) Project "ref_soft" -> Properties -> Linker -> Advanced -> Image Has Safe Exception Handlers:<br>
change to "NO"
5) Build Projects

### Build with VC 2010 Express:
1) install Windows 2003 DDK:<br>
Install Path: C:\WINDDK\3790.1830<br>
Install Components:<br>
\+ Windows Driver Development Kit Common headers<br>
2) Open and upgrade quake2.dsw with VC 2008 Express
4) Open and upgrade quake2.sln with VC 2010 Express
5) Project "quake2" -> Properties -> VC++ Directories:<br>
Include Directories:<br>
add path "C:\WINDDK\3790.1830\inc\mfc42"<br>
```
Required files:
WINDDK\3790.1830\inc\mfc42\afxres.h
WINDDK\3790.1830\inc\mfc42\winres.h
```
6) Build Projects

### Build with VC 2008 Express:
1) install Windows 2003 DDK:<br>
Install Path: C:\WINDDK\3790.1830
Install Components:<br>
\+ Windows Driver Development Kit Common headers<br>
\+ Windows Driver Development Kit Required Build Tools<br>
\+ Windows Server 2003 Headers<br>
3) Open and upgrade quake2.dsw with VC 2008 Express
4) Menu -> Tools -> Options -> VC++ Directories<br>
Executable files:<br>
add path "C:\WINDDK\3790.1830\bin\x86"<br>
Include files:<br>
add path "C:\WINDDK\3790.1830\inc\mfc42"<br>
add path "C:\WINDDK\3790.1830\inc\wnet"<br>
```
Required files:
WINDDK\3790.1830\bin\x86\ml.exe
WINDDK\3790.1830\inc\mfc42\afxres.h
WINDDK\3790.1830\inc\mfc42\winres.h
WINDDK\3790.1830\inc\wnet\dsound.h
```
5) Build Projects

