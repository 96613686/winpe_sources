# UpdateDllComRegistration(ushort const *,bool,bool,bool)

- ea: `0x18001874c`
- end: `0x18001899c`
- name: `?UpdateDllComRegistration@@YAJPEBG_N11@Z`
- size: `592`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, char, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800136f0`
- `0x18001b350`

## callees

- `0x180003400`
- `0x180004558`
- `0x18000be68`
- `0x18000bf2c`
- `0x18001874c`
- `0x180018f00`
- `0x180036ed0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x1800188d3`
- `KERNEL32!CreateProcessW` at `0x1800188d3`
- `KERNEL32!WaitForSingleObject` at `0x1800188f2`
- `KERNEL32!WaitForSingleObject` at `0x1800188f2`
- `KERNEL32!CloseHandle` at `0x18001892a`
- `KERNEL32!CloseHandle` at `0x18001893b`
- `KERNEL32!CloseHandle` at `0x18001892a`
- `KERNEL32!CloseHandle` at `0x18001893b`
- `KERNEL32!GetLastError` at `0x18001890a`
- `KERNEL32!GetLastError` at `0x180018949`
- `KERNEL32!GetLastError` at `0x18001890a`
- `KERNEL32!GetLastError` at `0x180018949`

## string_xrefs

- `0x180018791`: `DLL Path: %ws, isWOW: %ws`
- `0x18001879f`: `UpdateDllComRegistration`
- `0x180018851`: `UpdateDllComRegistration`
- `0x18001896e`: `UpdateDllComRegistration`
- `0x1800187e0`: `\System32\regsvr32.exe`

## pseudocode

```c
__int64 __fastcall UpdateDllComRegistration(const unsigned __int16 *a1, char a2, char a3, char a4)
{
  const wchar_t *v5; // r9
  unsigned __int16 *v9; // rdx
  int WindowsDirectoryW; // ebx
  unsigned __int16 *v11; // r8
  const wchar_t *v12; // rax
  DWORD v13; // eax
  signed int LastError; // eax
  signed int v15; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ApplicationName[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v5 = L"true";
  if ( !a2 )
    v5 = L"false";
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "UpdateDllComRegistration",
    L"DLL Path: %ws, isWOW: %ws",
    a1,
    v5);
  memset_0(ApplicationName, 0, 0x208u);
  WindowsDirectoryW = Win32Adapters::FileSystem::GetWindowsDirectoryW(ApplicationName, v9);
  if ( WindowsDirectoryW >= 0 )
  {
    v11 = L"\\SysWOW64\\regsvr32.exe";
    if ( !a2 )
      v11 = L"\\System32\\regsvr32.exe";
    WindowsDirectoryW = StringCchCatW(ApplicationName, 260, v11);
  }
  memset_0(CommandLine, 0, sizeof(CommandLine));
  if ( WindowsDirectoryW >= 0 )
  {
    v12 = &Filename;
    if ( !a4 )
      v12 = L" /u";
    WindowsDirectoryW = StringCchPrintfW(CommandLine, 0x208u, L"%s /s%s \"%s\"", ApplicationName, v12, a1);
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "UpdateDllComRegistration",
    L"RegSvr32 cmd line: %hs",
    CommandLine);
  if ( WindowsDirectoryW >= 0 )
  {
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( CreateProcessW(ApplicationName, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( a3 )
      {
        v13 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
        if ( v13 == -1 || v13 == 258 )
        {
          LastError = GetLastError();
          WindowsDirectoryW = LastError;
          if ( LastError > 0 )
            WindowsDirectoryW = (unsigned __int16)LastError | 0x80070000;
        }
      }
      CloseHandle(ProcessInformation.hThread);
      CloseHandle(ProcessInformation.hProcess);
    }
    else
    {
      v15 = GetLastError();
      WindowsDirectoryW = v15;
      if ( v15 > 0 )
        WindowsDirectoryW = (unsigned __int16)v15 | 0x80070000;
    }
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "UpdateDllComRegistration",
    L"Finished hr: 0x%x",
    (unsigned int)WindowsDirectoryW);
  return (unsigned int)WindowsDirectoryW;
}

```

## disassembly

```asm
0x18001874c  push    rbp
0x18001874e  push    rbx
0x18001874f  push    rsi
0x180018750  push    rdi
0x180018751  push    r14
0x180018753  push    r15
0x180018755  lea     rbp, [rsp-618h]
0x18001875d  sub     rsp, 718h
0x180018764  mov     rax, cs:__security_cookie
0x18001876b  xor     rax, rsp
0x18001876e  mov     [rbp+640h+var_40], rax
0x180018775  mov     r15b, r9b
0x180018778  lea     rax, aFalse_0; "false"
0x18001877f  test    dl, dl
0x180018781  lea     r9, aTrue; "true"
0x180018788  mov     sil, r8b
0x18001878b  mov     dil, dl
0x18001878e  mov     r14, rcx
0x180018791  lea     rdx, aDllPathWsIswow; "DLL Path: %ws, isWOW: %ws"
0x180018798  mov     r8, rcx
0x18001879b  cmovz   r9, rax
0x18001879f  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x1800187a6  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800187ab  xor     edx, edx; Val
0x1800187ad  lea     rcx, [rbp+640h+ApplicationName]; void *
0x1800187b1  mov     r8d, 208h; Size
0x1800187b7  call    memset_0
0x1800187bc  lea     rcx, [rbp+640h+ApplicationName]; this
0x1800187c0  call    ?GetWindowsDirectoryW@FileSystem@Win32Adapters@@YAJPEAGK@Z; Win32Adapters::FileSystem::GetWindowsDirectoryW(ushort *,ulong)
0x1800187c5  mov     ebx, eax
0x1800187c7  test    eax, eax
0x1800187c9  js      short loc_1800187EE
0x1800187cb  lea     rcx, [rbp+640h+ApplicationName]; unsigned __int16 *
0x1800187cf  mov     edx, 104h; unsigned __int64
0x1800187d4  lea     r8, aSyswow64Regsvr; "\\SysWOW64\\regsvr32.exe"
0x1800187db  test    dil, dil
0x1800187de  jnz     short loc_1800187E7
0x1800187e0  lea     r8, aSystem32Regsvr; "\\System32\\regsvr32.exe"
0x1800187e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800187ec  mov     ebx, eax
0x1800187ee  xor     edx, edx; Val
0x1800187f0  lea     rcx, [rbp+640h+CommandLine]; void *
0x1800187f7  mov     r8d, 410h; Size
0x1800187fd  call    memset_0
0x180018802  test    ebx, ebx
0x180018804  js      short loc_180018843
0x180018806  test    r15b, r15b
0x180018809  mov     qword ptr [rsp+740h+dwCreationFlags], r14
0x18001880e  lea     rcx, aU_1; " /u"
0x180018815  mov     edx, 208h; unsigned __int64
0x18001881a  lea     rax, Filename
0x180018821  cmovz   rax, rcx
0x180018825  lea     r9, [rbp+640h+ApplicationName]
0x180018829  lea     rcx, [rbp+640h+CommandLine]; unsigned __int16 *
0x180018830  mov     qword ptr [rsp+740h+bInheritHandles], rax
0x180018835  lea     r8, aSSSS; "%s /s%s \"%s\""
0x18001883c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018841  mov     ebx, eax
0x180018843  lea     r8, [rbp+640h+CommandLine]
0x18001884a  lea     rdx, aRegsvr32CmdLin; "RegSvr32 cmd line: %hs"
0x180018851  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x180018858  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001885d  test    ebx, ebx
0x18001885f  js      loc_180018964
0x180018865  xor     eax, eax
0x180018867  lea     rcx, [rsp+740h+StartupInfo+4]; void *
0x18001886c  xorps   xmm0, xmm0
0x18001886f  mov     qword ptr [rsp+740h+ProcessInformation.dwProcessId], rax
0x180018874  xor     edx, edx; Val
0x180018876  movups  xmmword ptr [rsp+740h+ProcessInformation.hProcess], xmm0
0x18001887b  lea     r8d, [rax+64h]; Size
0x18001887f  call    memset_0
0x180018884  lea     rax, [rsp+740h+ProcessInformation]
0x180018889  mov     [rsp+740h+StartupInfo.cb], 68h ; 'h'
0x180018891  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x180018896  lea     rdx, [rbp+640h+CommandLine]; lpCommandLine
0x18001889d  lea     rax, [rsp+740h+StartupInfo]
0x1800188a2  xor     r9d, r9d; lpThreadAttributes
0x1800188a5  mov     [rsp+740h+lpStartupInfo], rax; lpStartupInfo
0x1800188aa  lea     rcx, [rbp+640h+ApplicationName]; lpApplicationName
0x1800188ae  mov     [rsp+740h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800188b7  xor     r8d, r8d; lpProcessAttributes
0x1800188ba  mov     [rsp+740h+lpEnvironment], 0; lpEnvironment
0x1800188c3  mov     [rsp+740h+dwCreationFlags], 8000000h; dwCreationFlags
0x1800188cb  mov     [rsp+740h+bInheritHandles], 0; bInheritHandles
0x1800188d3  call    cs:__imp_CreateProcessW
0x1800188da  nop     dword ptr [rax+rax+00h]
0x1800188df  test    eax, eax
0x1800188e1  jz      short loc_180018949
0x1800188e3  test    sil, sil
0x1800188e6  jz      short loc_180018925
0x1800188e8  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hHandle
0x1800188ed  mov     edx, 0EA60h; dwMilliseconds
0x1800188f2  call    cs:__imp_WaitForSingleObject
0x1800188f9  nop     dword ptr [rax+rax+00h]
0x1800188fe  cmp     eax, 0FFFFFFFFh
0x180018901  jz      short loc_18001890A
0x180018903  cmp     eax, 102h
0x180018908  jnz     short loc_180018925
0x18001890a  call    cs:__imp_GetLastError
0x180018911  nop     dword ptr [rax+rax+00h]
0x180018916  mov     ebx, eax
0x180018918  test    eax, eax
0x18001891a  jle     short loc_180018925
0x18001891c  movzx   ebx, ax
0x18001891f  or      ebx, 80070000h
0x180018925  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hObject
0x18001892a  call    cs:__imp_CloseHandle
0x180018931  nop     dword ptr [rax+rax+00h]
0x180018936  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hObject
0x18001893b  call    cs:__imp_CloseHandle
0x180018942  nop     dword ptr [rax+rax+00h]
0x180018947  jmp     short loc_180018964
0x180018949  call    cs:__imp_GetLastError
0x180018950  nop     dword ptr [rax+rax+00h]
0x180018955  mov     ebx, eax
0x180018957  test    eax, eax
0x180018959  jle     short loc_180018964
0x18001895b  movzx   ebx, ax
0x18001895e  or      ebx, 80070000h
0x180018964  mov     r8d, ebx
0x180018967  lea     rdx, aFinishedHr0xX; "Finished hr: 0x%x"
0x18001896e  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x180018975  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001897a  mov     eax, ebx
0x18001897c  mov     rcx, [rbp+640h+var_40]
0x180018983  xor     rcx, rsp; StackCookie
0x180018986  call    __security_check_cookie
0x18001898b  add     rsp, 718h
0x180018992  pop     r15
0x180018994  pop     r14
0x180018996  pop     rdi
0x180018997  pop     rsi
0x180018998  pop     rbx
0x180018999  pop     rbp
0x18001899a  retn
```
