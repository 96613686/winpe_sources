# UpdateDllComRegistration(ushort const *,bool,bool,bool)

- ea: `0x180017c3c`
- end: `0x180017e67`
- name: `?UpdateDllComRegistration@@YAJPEBG_N11@Z`
- size: `555`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, char, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012f3c`
- `0x18001a6e0`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18000be0c`
- `0x18000bed0`
- `0x180017c3c`
- `0x1800183a0`
- `0x180035c90`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x180017dc3`
- `KERNEL32!CreateProcessW` at `0x180017dc3`
- `KERNEL32!WaitForSingleObject` at `0x180017ddc`
- `KERNEL32!WaitForSingleObject` at `0x180017ddc`
- `KERNEL32!CloseHandle` at `0x180017e08`
- `KERNEL32!CloseHandle` at `0x180017e13`
- `KERNEL32!CloseHandle` at `0x180017e08`
- `KERNEL32!CloseHandle` at `0x180017e13`
- `KERNEL32!GetLastError` at `0x180017dee`
- `KERNEL32!GetLastError` at `0x180017e1b`
- `KERNEL32!GetLastError` at `0x180017dee`
- `KERNEL32!GetLastError` at `0x180017e1b`

## string_xrefs

- `0x180017c81`: `DLL Path: %ws, isWOW: %ws`
- `0x180017c8f`: `UpdateDllComRegistration`
- `0x180017d41`: `UpdateDllComRegistration`
- `0x180017e3a`: `UpdateDllComRegistration`
- `0x180017cd0`: `\System32\regsvr32.exe`

## pseudocode

```c
__int64 __fastcall UpdateDllComRegistration(const unsigned __int16 *a1, char a2, char a3, char a4)
{
  const wchar_t *v5; // r9
  unsigned __int16 *v9; // rdx
  unsigned int v10; // r8d
  signed int WindowsDirectoryW; // ebx
  const unsigned __int16 *v12; // r8
  const wchar_t *v13; // rax
  DWORD v14; // eax
  signed int LastError; // eax
  signed int v16; // eax
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
  WindowsDirectoryW = Win32Adapters::FileSystem::GetWindowsDirectoryW(
                        (Win32Adapters::FileSystem *)ApplicationName,
                        v9,
                        v10);
  if ( WindowsDirectoryW >= 0 )
  {
    v12 = L"\\SysWOW64\\regsvr32.exe";
    if ( !a2 )
      v12 = L"\\System32\\regsvr32.exe";
    WindowsDirectoryW = StringCchCatW(ApplicationName, 0x104u, v12);
  }
  memset_0(CommandLine, 0, sizeof(CommandLine));
  if ( WindowsDirectoryW >= 0 )
  {
    v13 = &Filename;
    if ( !a4 )
      v13 = L" /u";
    WindowsDirectoryW = StringCchPrintfW(CommandLine, 0x208u, L"%s /s%s \"%s\"", ApplicationName, v13, a1);
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
        v14 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
        if ( v14 == -1 || v14 == 258 )
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
      v16 = GetLastError();
      WindowsDirectoryW = v16;
      if ( v16 > 0 )
        WindowsDirectoryW = (unsigned __int16)v16 | 0x80070000;
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
0x180017c3c  push    rbp
0x180017c3e  push    rbx
0x180017c3f  push    rsi
0x180017c40  push    rdi
0x180017c41  push    r14
0x180017c43  push    r15
0x180017c45  lea     rbp, [rsp-618h]
0x180017c4d  sub     rsp, 718h
0x180017c54  mov     rax, cs:__security_cookie
0x180017c5b  xor     rax, rsp
0x180017c5e  mov     [rbp+640h+var_40], rax
0x180017c65  mov     r15b, r9b
0x180017c68  lea     rax, aFalse_0; "false"
0x180017c6f  test    dl, dl
0x180017c71  lea     r9, aTrue; "true"
0x180017c78  mov     sil, r8b
0x180017c7b  mov     dil, dl
0x180017c7e  mov     r14, rcx
0x180017c81  lea     rdx, aDllPathWsIswow; "DLL Path: %ws, isWOW: %ws"
0x180017c88  mov     r8, rcx
0x180017c8b  cmovz   r9, rax
0x180017c8f  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x180017c96  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180017c9b  xor     edx, edx; Val
0x180017c9d  lea     rcx, [rbp+640h+ApplicationName]; void *
0x180017ca1  mov     r8d, 208h; Size
0x180017ca7  call    memset_0
0x180017cac  lea     rcx, [rbp+640h+ApplicationName]; this
0x180017cb0  call    ?GetWindowsDirectoryW@FileSystem@Win32Adapters@@YAJPEAGK@Z; Win32Adapters::FileSystem::GetWindowsDirectoryW(ushort *,ulong)
0x180017cb5  mov     ebx, eax
0x180017cb7  test    eax, eax
0x180017cb9  js      short loc_180017CDE
0x180017cbb  lea     rcx, [rbp+640h+ApplicationName]; unsigned __int16 *
0x180017cbf  mov     edx, 104h; unsigned __int64
0x180017cc4  lea     r8, aSyswow64Regsvr; "\\SysWOW64\\regsvr32.exe"
0x180017ccb  test    dil, dil
0x180017cce  jnz     short loc_180017CD7
0x180017cd0  lea     r8, aSystem32Regsvr; "\\System32\\regsvr32.exe"
0x180017cd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017cdc  mov     ebx, eax
0x180017cde  xor     edx, edx; Val
0x180017ce0  lea     rcx, [rbp+640h+CommandLine]; void *
0x180017ce7  mov     r8d, 410h; Size
0x180017ced  call    memset_0
0x180017cf2  test    ebx, ebx
0x180017cf4  js      short loc_180017D33
0x180017cf6  test    r15b, r15b
0x180017cf9  mov     qword ptr [rsp+740h+dwCreationFlags], r14
0x180017cfe  lea     rcx, aU_1; " /u"
0x180017d05  mov     edx, 208h; unsigned __int64
0x180017d0a  lea     rax, Filename
0x180017d11  cmovz   rax, rcx
0x180017d15  lea     r9, [rbp+640h+ApplicationName]
0x180017d19  lea     rcx, [rbp+640h+CommandLine]; unsigned __int16 *
0x180017d20  mov     qword ptr [rsp+740h+bInheritHandles], rax
0x180017d25  lea     r8, aSSSS; "%s /s%s \"%s\""
0x180017d2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017d31  mov     ebx, eax
0x180017d33  lea     r8, [rbp+640h+CommandLine]
0x180017d3a  lea     rdx, aRegsvr32CmdLin; "RegSvr32 cmd line: %hs"
0x180017d41  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x180017d48  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180017d4d  test    ebx, ebx
0x180017d4f  js      loc_180017E30
0x180017d55  xor     eax, eax
0x180017d57  lea     rcx, [rsp+740h+StartupInfo+4]; void *
0x180017d5c  xorps   xmm0, xmm0
0x180017d5f  mov     qword ptr [rsp+740h+ProcessInformation.dwProcessId], rax
0x180017d64  xor     edx, edx; Val
0x180017d66  movups  xmmword ptr [rsp+740h+ProcessInformation.hProcess], xmm0
0x180017d6b  lea     r8d, [rax+64h]; Size
0x180017d6f  call    memset_0
0x180017d74  lea     rax, [rsp+740h+ProcessInformation]
0x180017d79  mov     [rsp+740h+StartupInfo.cb], 68h ; 'h'
0x180017d81  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x180017d86  lea     rdx, [rbp+640h+CommandLine]; lpCommandLine
0x180017d8d  lea     rax, [rsp+740h+StartupInfo]
0x180017d92  xor     r9d, r9d; lpThreadAttributes
0x180017d95  mov     [rsp+740h+lpStartupInfo], rax; lpStartupInfo
0x180017d9a  lea     rcx, [rbp+640h+ApplicationName]; lpApplicationName
0x180017d9e  mov     [rsp+740h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180017da7  xor     r8d, r8d; lpProcessAttributes
0x180017daa  mov     [rsp+740h+lpEnvironment], 0; lpEnvironment
0x180017db3  mov     [rsp+740h+dwCreationFlags], 8000000h; dwCreationFlags
0x180017dbb  mov     [rsp+740h+bInheritHandles], 0; bInheritHandles
0x180017dc3  call    cs:__imp_CreateProcessW
0x180017dc9  test    eax, eax
0x180017dcb  jz      short loc_180017E1B
0x180017dcd  test    sil, sil
0x180017dd0  jz      short loc_180017E03
0x180017dd2  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hHandle
0x180017dd7  mov     edx, 0EA60h; dwMilliseconds
0x180017ddc  call    cs:__imp_WaitForSingleObject
0x180017de2  cmp     eax, 0FFFFFFFFh
0x180017de5  jz      short loc_180017DEE
0x180017de7  cmp     eax, 102h
0x180017dec  jnz     short loc_180017E03
0x180017dee  call    cs:__imp_GetLastError
0x180017df4  mov     ebx, eax
0x180017df6  test    eax, eax
0x180017df8  jle     short loc_180017E03
0x180017dfa  movzx   ebx, ax
0x180017dfd  or      ebx, 80070000h
0x180017e03  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hObject
0x180017e08  call    cs:__imp_CloseHandle
0x180017e0e  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hObject
0x180017e13  call    cs:__imp_CloseHandle
0x180017e19  jmp     short loc_180017E30
0x180017e1b  call    cs:__imp_GetLastError
0x180017e21  mov     ebx, eax
0x180017e23  test    eax, eax
0x180017e25  jle     short loc_180017E30
0x180017e27  movzx   ebx, ax
0x180017e2a  or      ebx, 80070000h
0x180017e30  mov     r8d, ebx
0x180017e33  lea     rdx, aFinishedHr0xX; "Finished hr: 0x%x"
0x180017e3a  lea     rcx, aUpdatedllcomre; "UpdateDllComRegistration"
0x180017e41  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180017e46  mov     eax, ebx
0x180017e48  mov     rcx, [rbp+640h+var_40]
0x180017e4f  xor     rcx, rsp; StackCookie
0x180017e52  call    __security_check_cookie
0x180017e57  add     rsp, 718h
0x180017e5e  pop     r15
0x180017e60  pop     r14
0x180017e62  pop     rdi
0x180017e63  pop     rsi
0x180017e64  pop     rbx
0x180017e65  pop     rbp
0x180017e66  retn
```
