# LaunchEventReportingConsole(ErcCmdMode)

- ea: `0x140007cf0`
- end: `0x140008217`
- name: `?LaunchEventReportingConsole@@YAJW4ErcCmdMode@@@Z`
- size: `1319`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000659c`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140007cf0`
- `0x140008c04`
- `0x140008c40`
- `0x14000a62c`
- `0x14000a6dc`
- `0x140017c8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007d79`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140008067`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140008067`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007ee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000800a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000801a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000811a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000812a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400081e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400081f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000800a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000801a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000811a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000812a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400081e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400081f2`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140007d87`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140007d87`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140007da7`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x140007da7`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x140007e7e`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400080db`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400081a3`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x140007e7e`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400080db`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1400081a3`

## string_xrefs

- `0x14000816d`: `GetSystemDirectory failed.`
- `0x140007e22`: `\RunDll32.exe`
- `0x140007e5d`: `StringCchCat failed (path = %ws).`
- `0x140007ef6`: `\WerConCpl.dll`
- `0x140007f30`: `Cannot launch ERC. ERC is not installed on the system.`
- `0x1400080b5`: `CreateProcess failed (path = %ws, args = %ws)`

## pseudocode

```c
__int64 __fastcall LaunchEventReportingConsole(int a1)
{
  HANDLE CurrentProcess; // rax
  WINBOOL v3; // eax
  signed int LastError; // eax
  signed int v5; // ebx
  unsigned __int64 v6; // rdx
  int v7; // esi
  WCHAR *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v11; // rdx
  const char *v12; // rax
  __int64 v13; // rdx
  int v14; // ebx
  int v15; // ebx
  int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  wil::details *bInheritHandles; // [rsp+20h] [rbp-E0h]
  wil::details *bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  const char *dwCreationFlags; // [rsp+28h] [rbp-D8h]
  const char *dwCreationFlagsa; // [rsp+28h] [rbp-D8h]
  const char *dwCreationFlagsb; // [rsp+28h] [rbp-D8h]
  const char *lpEnvironment; // [rsp+30h] [rbp-D0h]
  WINBOOL Wow64Process; // [rsp+50h] [rbp-B0h] BYREF
  PVOID OldValue; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION hObject; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v31[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR CommandLine[264]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+758h] [rbp+658h]

  memset_0(CommandLine, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(v31, 0, 0x208u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&hObject, 0, sizeof(hObject));
  OldValue = 0;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    v3 = Wow64Process;
  }
  else
  {
    v3 = 0;
    Wow64Process = 0;
  }
  if ( v3 && !Wow64DisableWow64FsRedirection(&OldValue) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LODWORD(bInheritHandles) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "LaunchEventReportingConsole",
      bInheritHandles,
      (int)"Wow64DisableWow64FsRedirection failed.",
      lpEnvironment);
LABEL_64:
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    return (unsigned int)v5;
  }
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    v19 = GetLastError();
    v5 = v19;
    if ( v19 > 0 )
      v5 = (unsigned __int16)v19 | 0x80070000;
    v13 = 160;
    goto LABEL_59;
  }
  v7 = StringCchCatW(Buffer, v6, L"\\RunDll32.exe");
  if ( v7 < 0 )
  {
    v8 = Buffer;
    v9 = 169;
    goto LABEL_14;
  }
  if ( GetSystemDirectoryW(v31, 0x104u) - 1 > 0x102 )
  {
    v18 = GetLastError();
    v5 = v18;
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
    v13 = 177;
LABEL_59:
    v12 = "GetSystemDirectory failed.";
    goto LABEL_60;
  }
  v7 = StringCchCatW(v31, v11, L"\\WerConCpl.dll");
  if ( v7 < 0 )
  {
    v8 = v31;
    v9 = 186;
LABEL_14:
    LODWORD(bInheritHandles) = v7;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "LaunchEventReportingConsole",
      bInheritHandles,
      (int)"StringCchCat failed (path = %ws).",
      (const char *)v8);
    if ( Wow64Process && !Wow64RevertWow64FsRedirection(OldValue) )
      wil::details::in1diag4::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "LaunchEventReportingConsole::<lambda_2ae86ac6110312972aaedb22b26507d3>::operator ()",
        "Wow64RevertWow64FsRedirection failed.",
        dwCreationFlags);
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    return (unsigned int)v7;
  }
  if ( !UtilFileExists(v31) )
  {
    v12 = "Cannot launch ERC. ERC is not installed on the system.";
    v5 = -2147024894;
    v13 = 198;
LABEL_60:
    LODWORD(bInheritHandles) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "LaunchEventReportingConsole",
      bInheritHandles,
      (int)v12,
      lpEnvironment);
LABEL_61:
    if ( Wow64Process && !Wow64RevertWow64FsRedirection(OldValue) )
      wil::details::in1diag4::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "LaunchEventReportingConsole::<lambda_2ae86ac6110312972aaedb22b26507d3>::operator ()",
        "Wow64RevertWow64FsRedirection failed.",
        dwCreationFlagsb);
    goto LABEL_64;
  }
  if ( a1 )
  {
    v14 = a1 - 1;
    if ( v14 )
    {
      v15 = v14 - 2;
      if ( v15 )
      {
        if ( v15 != 1 )
          goto LABEL_37;
        v16 = StringCchPrintfW(
                CommandLine,
                0x104u,
                L"\"%ws\" \"%ws\", LaunchErcApp -queuereportingnopester",
                Buffer,
                v31);
      }
      else
      {
        v16 = StringCchPrintfW(
                CommandLine,
                0x104u,
                L"\"%ws\" \"%ws\", LaunchErcApp -queuereportingconsentedonly",
                Buffer,
                v31);
      }
    }
    else
    {
      v16 = StringCchPrintfW(CommandLine, 0x104u, L"\"%ws\" \"%ws\", LaunchErcApp -responsepester", Buffer, v31);
    }
  }
  else
  {
    v16 = StringCchPrintfW(CommandLine, 0x104u, L"\"%ws\" \"%ws\", LaunchErcApp -queuereporting", Buffer, v31);
  }
  v5 = v16;
  if ( v16 < 0 )
  {
    v12 = "StringCChPrintf failed.";
    v13 = 254;
    goto LABEL_60;
  }
LABEL_37:
  LODWORD(bInheritHandles) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x102,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "LaunchEventReportingConsole",
    bInheritHandles,
    (int)"Creating process %ws %ws",
    (const char *)Buffer,
    CommandLine);
  StartupInfo.cb = 104;
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &hObject) )
  {
    v17 = GetLastError();
    v5 = v17;
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
    LODWORD(bInheritHandlesa) = v5;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "LaunchEventReportingConsole",
      bInheritHandlesa,
      (int)"CreateProcess failed (path = %ws, args = %ws)",
      (const char *)Buffer,
      CommandLine);
    goto LABEL_61;
  }
  if ( Wow64Process && !Wow64RevertWow64FsRedirection(OldValue) )
    wil::details::in1diag4::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "LaunchEventReportingConsole::<lambda_2ae86ac6110312972aaedb22b26507d3>::operator ()",
      "Wow64RevertWow64FsRedirection failed.",
      dwCreationFlagsa);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return 0;
}

```

## disassembly

```asm
0x140007cf0  push    rbp
0x140007cf2  push    rbx
0x140007cf3  push    rsi
0x140007cf4  push    rdi
0x140007cf5  push    r14
0x140007cf7  lea     rbp, [rsp-630h]
0x140007cff  sub     rsp, 730h
0x140007d06  mov     rax, cs:__security_cookie
0x140007d0d  xor     rax, rsp
0x140007d10  mov     [rbp+650h+var_30], rax
0x140007d17  mov     ebx, ecx
0x140007d19  mov     edi, 208h
0x140007d1e  mov     r8d, edi; Size
0x140007d21  lea     rcx, [rbp+650h+CommandLine]; void *
0x140007d28  xor     edx, edx; Val
0x140007d2a  call    memset_0
0x140007d2f  mov     r8d, edi; Size
0x140007d32  lea     rcx, [rbp+650h+Buffer]; void *
0x140007d36  xor     edx, edx; Val
0x140007d38  call    memset_0
0x140007d3d  mov     r8d, edi; Size
0x140007d40  lea     rcx, [rbp+650h+var_450]; void *
0x140007d47  xor     edx, edx; Val
0x140007d49  call    memset_0
0x140007d4e  xor     edx, edx; Val
0x140007d50  lea     rcx, [rbp+650h+StartupInfo]; void *
0x140007d54  lea     r8d, [rdx+68h]; Size
0x140007d58  call    memset_0
0x140007d5d  xorps   xmm0, xmm0
0x140007d60  xor     eax, eax
0x140007d62  xor     r14d, r14d
0x140007d65  mov     [rsp+750h+var_6E0], rax
0x140007d6a  movups  xmmword ptr [rsp+750h+hObject], xmm0
0x140007d6f  mov     [rsp+750h+OldValue], r14
0x140007d74  mov     [rsp+750h+Wow64Process], r14d
0x140007d79  call    cs:__imp_GetCurrentProcess
0x140007d7f  mov     rcx, rax; hProcess
0x140007d82  lea     rdx, [rsp+750h+Wow64Process]; Wow64Process
0x140007d87  call    cs:__imp_IsWow64Process
0x140007d8d  test    eax, eax
0x140007d8f  jnz     short loc_140007D9A
0x140007d91  mov     eax, r14d
0x140007d94  mov     [rsp+750h+Wow64Process], eax
0x140007d98  jmp     short loc_140007D9E
0x140007d9a  mov     eax, [rsp+750h+Wow64Process]
0x140007d9e  test    eax, eax
0x140007da0  jz      short loc_140007E04
0x140007da2  lea     rcx, [rsp+750h+OldValue]; OldValue
0x140007da7  call    cs:__imp_Wow64DisableWow64FsRedirection
0x140007dad  test    eax, eax
0x140007daf  jnz     short loc_140007E04
0x140007db1  call    cs:__imp_GetLastError
0x140007db7  mov     ebx, eax
0x140007db9  test    eax, eax
0x140007dbb  jle     short loc_140007DC6
0x140007dbd  movzx   ebx, ax
0x140007dc0  or      ebx, 80070000h
0x140007dc6  mov     rcx, [rbp+658h]; this
0x140007dcd  lea     r9, aLauncheventrep; "LaunchEventReportingConsole"
0x140007dd4  test    ebx, ebx
0x140007dd6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140007ddd  mov     eax, 80004005h
0x140007de2  mov     edx, 8Eh; void *
0x140007de7  cmovns  ebx, eax
0x140007dea  lea     rax, aWow64disablewo; "Wow64DisableWow64FsRedirection failed."
0x140007df1  mov     qword ptr [rsp+750h+dwCreationFlags], rax; int
0x140007df6  mov     [rsp+750h+bInheritHandles], ebx; wil::details *
0x140007dfa  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140007dff  jmp     loc_1400081D8
0x140007e04  mov     edi, 104h
0x140007e09  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x140007e0d  mov     edx, edi; uSize
0x140007e0f  call    cs:__imp_GetSystemDirectoryW
0x140007e15  dec     eax
0x140007e17  cmp     eax, 102h
0x140007e1c  ja      loc_140008153
0x140007e22  lea     r8, aRundll32Exe; "\\RunDll32.exe"
0x140007e29  lea     rcx, [rbp+650h+Buffer]; wchar_t *
0x140007e2d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140007e32  mov     esi, eax
0x140007e34  test    eax, eax
0x140007e36  jns     loc_140007EDA
0x140007e3c  lea     rax, [rbp+650h+Buffer]
0x140007e40  lea     edx, [rdi-5Bh]; void *
0x140007e43  mov     rcx, [rbp+658h]; this
0x140007e4a  lea     r9, aLauncheventrep; "LaunchEventReportingConsole"
0x140007e51  mov     [rsp+750h+lpEnvironment], rax; char *
0x140007e56  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140007e5d  lea     rax, aStringcchcatFa; "StringCchCat failed (path = %ws)."
0x140007e64  mov     qword ptr [rsp+750h+dwCreationFlags], rax; char *
0x140007e69  mov     [rsp+750h+bInheritHandles], esi; wil::details *
0x140007e6d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140007e72  cmp     [rsp+750h+Wow64Process], r14d
0x140007e77  jz      short loc_140007EB3
0x140007e79  mov     rcx, [rsp+750h+OldValue]; OlValue
0x140007e7e  call    cs:__imp_Wow64RevertWow64FsRedirection
0x140007e84  test    eax, eax
0x140007e86  jnz     short loc_140007EB3
0x140007e88  mov     rcx, [rbp+658h]; this
0x140007e8f  lea     rax, aWow64revertwow; "Wow64RevertWow64FsRedirection failed."
0x140007e96  lea     r9, aLauncheventrep_0; "LaunchEventReportingConsole::<lambda_2a"...
0x140007e9d  mov     qword ptr [rsp+750h+bInheritHandles], rax; char *
0x140007ea2  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140007ea9  mov     edx, 98h; void *
0x140007eae  call    ?Log_GetLastErrorMsg@in1diag4@details@wil@@YAKPEAXIPEBD11ZZ; wil::details::in1diag4::Log_GetLastErrorMsg(void *,uint,char const *,char const *,char const *,...)
0x140007eb3  mov     rcx, [rsp+750h+hObject]; hObject
0x140007eb8  test    rcx, rcx
0x140007ebb  jz      short loc_140007EC3
0x140007ebd  call    cs:__imp_CloseHandle
0x140007ec3  mov     rcx, [rsp+750h+hObject+8]; hObject
0x140007ec8  test    rcx, rcx
0x140007ecb  jz      short loc_140007ED3
0x140007ecd  call    cs:__imp_CloseHandle
0x140007ed3  mov     eax, esi
0x140007ed5  jmp     loc_1400081FA
0x140007eda  mov     edx, edi; uSize
0x140007edc  lea     rcx, [rbp+650h+var_450]; lpBuffer
0x140007ee3  call    cs:__imp_GetSystemDirectoryW
0x140007ee9  dec     eax
0x140007eeb  cmp     eax, 102h
0x140007ef0  ja      loc_140008137
0x140007ef6  lea     r8, aWerconcplDll; "\\WerConCpl.dll"
0x140007efd  lea     rcx, [rbp+650h+var_450]; wchar_t *
0x140007f04  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140007f09  mov     esi, eax
0x140007f0b  test    eax, eax
0x140007f0d  jns     short loc_140007F20
0x140007f0f  lea     rax, [rbp+650h+var_450]
0x140007f16  mov     edx, 0BAh
0x140007f1b  jmp     loc_140007E43
0x140007f20  lea     rcx, [rbp+650h+var_450]; wchar_t *
0x140007f27  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140007f2c  test    al, al
0x140007f2e  jnz     short loc_140007F46
0x140007f30  lea     rax, aCannotLaunchEr; "Cannot launch ERC. ERC is not installed"...
0x140007f37  mov     ebx, 80070002h
0x140007f3c  mov     edx, 0C6h
0x140007f41  jmp     loc_140008174
0x140007f46  test    ebx, ebx
0x140007f48  jz      short loc_140007F74
0x140007f4a  sub     ebx, 1
0x140007f4d  jz      short loc_140007F6B
0x140007f4f  sub     ebx, 2
0x140007f52  jz      short loc_140007F62
0x140007f54  cmp     ebx, 1
0x140007f57  jnz     short loc_140007FB1
0x140007f59  lea     r8, aWsWsLauncherca_0; "\"%ws\" \"%ws\", LaunchErcApp -queuerep"...
0x140007f60  jmp     short loc_140007F7B
0x140007f62  lea     r8, aWsWsLauncherca_1; "\"%ws\" \"%ws\", LaunchErcApp -queuerep"...
0x140007f69  jmp     short loc_140007F7B
0x140007f6b  lea     r8, aWsWsLauncherca; "\"%ws\" \"%ws\", LaunchErcApp -response"...
0x140007f72  jmp     short loc_140007F7B
0x140007f74  lea     r8, aWsWsLauncherca_2; "\"%ws\" \"%ws\", LaunchErcApp -queuerep"...
0x140007f7b  lea     rax, [rbp+650h+var_450]
0x140007f82  mov     rdx, rdi; unsigned __int64
0x140007f85  lea     r9, [rbp+650h+Buffer]
0x140007f89  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x140007f8e  lea     rcx, [rbp+650h+CommandLine]; wchar_t *
0x140007f95  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140007f9a  mov     ebx, eax
0x140007f9c  test    eax, eax
0x140007f9e  jns     short loc_140007FB1
0x140007fa0  lea     rax, aStringcchprint; "StringCChPrintf failed."
0x140007fa7  mov     edx, 0FEh
0x140007fac  jmp     loc_140008174
0x140007fb1  mov     rcx, [rbp+658h]; this
0x140007fb8  lea     rax, [rbp+650h+CommandLine]
0x140007fbf  mov     [rsp+750h+lpCurrentDirectory], rax
0x140007fc4  lea     r9, aLauncheventrep; "LaunchEventReportingConsole"
0x140007fcb  lea     rax, [rbp+650h+Buffer]
0x140007fcf  mov     edx, 102h; void *
0x140007fd4  mov     [rsp+750h+lpEnvironment], rax; char *
0x140007fd9  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140007fe0  lea     rax, aCreatingProces; "Creating process %ws %ws"
0x140007fe7  mov     qword ptr [rsp+750h+dwCreationFlags], rax; int
0x140007fec  mov     [rsp+750h+bInheritHandles], 80000000h; wil::details *
0x140007ff4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140007ff9  mov     rcx, [rsp+750h+hObject]; hObject
0x140007ffe  mov     [rbp+650h+StartupInfo.cb], 68h ; 'h'
0x140008005  test    rcx, rcx
0x140008008  jz      short loc_140008010
0x14000800a  call    cs:__imp_CloseHandle
0x140008010  mov     rcx, [rsp+750h+hObject+8]; hObject
0x140008015  test    rcx, rcx
0x140008018  jz      short loc_140008020
0x14000801a  call    cs:__imp_CloseHandle
0x140008020  xor     eax, eax
0x140008022  lea     rdx, [rbp+650h+CommandLine]; lpCommandLine
0x140008029  mov     [rsp+750h+var_6E0], rax
0x14000802e  lea     rcx, [rbp+650h+Buffer]; lpApplicationName
0x140008032  lea     rax, [rsp+750h+hObject]
0x140008037  xorps   xmm0, xmm0
0x14000803a  mov     [rsp+750h+lpProcessInformation], rax; lpProcessInformation
0x14000803f  xor     r9d, r9d; lpThreadAttributes
0x140008042  lea     rax, [rbp+650h+StartupInfo]
0x140008046  xor     r8d, r8d; lpProcessAttributes
0x140008049  mov     [rsp+750h+lpStartupInfo], rax; lpStartupInfo
0x14000804e  mov     [rsp+750h+lpCurrentDirectory], r14; lpCurrentDirectory
0x140008053  mov     [rsp+750h+lpEnvironment], r14; lpEnvironment
0x140008058  mov     [rsp+750h+dwCreationFlags], r14d; char *
0x14000805d  mov     [rsp+750h+bInheritHandles], r14d; bInheritHandles
0x140008062  movups  xmmword ptr [rsp+750h+hObject], xmm0
0x140008067  call    cs:__imp_CreateProcessW
0x14000806d  test    eax, eax
0x14000806f  jnz     short loc_1400080CF
0x140008071  call    cs:__imp_GetLastError
0x140008077  mov     ebx, eax
0x140008079  test    eax, eax
0x14000807b  jle     short loc_140008086
0x14000807d  movzx   ebx, ax
0x140008080  or      ebx, 80070000h
0x140008086  mov     rcx, [rbp+658h]; this
0x14000808d  lea     rax, [rbp+650h+CommandLine]
0x140008094  mov     [rsp+750h+lpCurrentDirectory], rax
0x140008099  lea     r9, aLauncheventrep; "LaunchEventReportingConsole"
0x1400080a0  lea     rax, [rbp+650h+Buffer]
0x1400080a4  mov     edx, 115h; void *
0x1400080a9  mov     [rsp+750h+lpEnvironment], rax; char *
0x1400080ae  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400080b5  lea     rax, aCreateprocessF_0; "CreateProcess failed (path = %ws, args "...
0x1400080bc  mov     qword ptr [rsp+750h+dwCreationFlags], rax; int
0x1400080c1  mov     [rsp+750h+bInheritHandles], ebx; wil::details *
0x1400080c5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400080ca  jmp     loc_140008197
0x1400080cf  cmp     [rsp+750h+Wow64Process], r14d
0x1400080d4  jz      short loc_140008110
0x1400080d6  mov     rcx, [rsp+750h+OldValue]; OlValue
0x1400080db  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1400080e1  test    eax, eax
0x1400080e3  jnz     short loc_140008110
0x1400080e5  mov     rcx, [rbp+658h]; this
0x1400080ec  lea     rax, aWow64revertwow; "Wow64RevertWow64FsRedirection failed."
0x1400080f3  lea     r9, aLauncheventrep_0; "LaunchEventReportingConsole::<lambda_2a"...
0x1400080fa  mov     qword ptr [rsp+750h+bInheritHandles], rax; char *
0x1400080ff  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140008106  mov     edx, 98h; void *
0x14000810b  call    ?Log_GetLastErrorMsg@in1diag4@details@wil@@YAKPEAXIPEBD11ZZ; wil::details::in1diag4::Log_GetLastErrorMsg(void *,uint,char const *,char const *,char const *,...)
0x140008110  mov     rcx, [rsp+750h+hObject]; hObject
0x140008115  test    rcx, rcx
0x140008118  jz      short loc_140008120
0x14000811a  call    cs:__imp_CloseHandle
0x140008120  mov     rcx, [rsp+750h+hObject+8]; hObject
0x140008125  test    rcx, rcx
0x140008128  jz      short loc_140008130
0x14000812a  call    cs:__imp_CloseHandle
0x140008130  xor     eax, eax
0x140008132  jmp     loc_1400081FA
0x140008137  call    cs:__imp_GetLastError
0x14000813d  mov     ebx, eax
0x14000813f  test    eax, eax
0x140008141  jle     short loc_14000814C
0x140008143  movzx   ebx, ax
0x140008146  or      ebx, 80070000h
0x14000814c  mov     edx, 0B1h
0x140008151  jmp     short loc_14000816D
0x140008153  call    cs:__imp_GetLastError
0x140008159  mov     ebx, eax
0x14000815b  test    eax, eax
0x14000815d  jle     short loc_140008168
0x14000815f  movzx   ebx, ax
0x140008162  or      ebx, 80070000h
0x140008168  mov     edx, 0A0h; void *
0x14000816d  lea     rax, aGetsystemdirec; "GetSystemDirectory failed."
0x140008174  mov     rcx, [rbp+658h]; this
0x14000817b  lea     r9, aLauncheventrep; "LaunchEventReportingConsole"
0x140008182  mov     qword ptr [rsp+750h+dwCreationFlags], rax; char *
0x140008187  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000818e  mov     [rsp+750h+bInheritHandles], ebx; wil::details *
0x140008192  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140008197  cmp     [rsp+750h+Wow64Process], r14d
0x14000819c  jz      short loc_1400081D8
0x14000819e  mov     rcx, [rsp+750h+OldValue]; OlValue
0x1400081a3  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1400081a9  test    eax, eax
0x1400081ab  jnz     short loc_1400081D8
0x1400081ad  mov     rcx, [rbp+658h]; this
0x1400081b4  lea     rax, aWow64revertwow; "Wow64RevertWow64FsRedirection failed."
0x1400081bb  lea     r9, aLauncheventrep_0; "LaunchEventReportingConsole::<lambda_2a"...
0x1400081c2  mov     qword ptr [rsp+750h+bInheritHandles], rax; char *
0x1400081c7  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400081ce  mov     edx, 98h; void *
0x1400081d3  call    ?Log_GetLastErrorMsg@in1diag4@details@wil@@YAKPEAXIPEBD11ZZ; wil::details::in1diag4::Log_GetLastErrorMsg(void *,uint,char const *,char const *,char const *,...)
0x1400081d8  mov     rcx, [rsp+750h+hObject]; hObject
0x1400081dd  test    rcx, rcx
0x1400081e0  jz      short loc_1400081E8
0x1400081e2  call    cs:__imp_CloseHandle
0x1400081e8  mov     rcx, [rsp+750h+hObject+8]; hObject
0x1400081ed  test    rcx, rcx
0x1400081f0  jz      short loc_1400081F8
0x1400081f2  call    cs:__imp_CloseHandle
0x1400081f8  mov     eax, ebx
0x1400081fa  mov     rcx, [rbp+650h+var_30]
0x140008201  xor     rcx, rsp; StackCookie
0x140008204  call    __security_check_cookie
0x140008209  add     rsp, 730h
0x140008210  pop     r14
0x140008212  pop     rdi
0x140008213  pop     rsi
0x140008214  pop     rbx
0x140008215  pop     rbp
  ... truncated ...
```
