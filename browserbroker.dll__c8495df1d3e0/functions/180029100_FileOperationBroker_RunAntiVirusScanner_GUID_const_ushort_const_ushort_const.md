# FileOperationBroker::RunAntiVirusScanner(_GUID const &,ushort const *,ushort const *)

- ea: `0x180029100`
- end: `0x1800293fd`
- name: `?RunAntiVirusScanner@FileOperationBroker@@UEAAJAEBU_GUID@@PEBG1@Z`
- size: `765`
- prototype: `int(FileOperationBroker *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180003170`
- `0x1800037ac`
- `0x18000d088`
- `0x18000d1c0`
- `0x18000dc58`
- `0x18000dc74`
- `0x18000e428`
- `0x180029100`
- `0x18002ad60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029360`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029397`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002938d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002938d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002932f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002932f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002919a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002919a`
- `RPCRT4!RpcStringFreeW` at `0x1800293cd`
- `RPCRT4!RpcStringFreeW` at `0x1800293cd`
- `RPCRT4!UuidToStringW` at `0x180029164`
- `RPCRT4!UuidToStringW` at `0x180029164`

## string_xrefs

- `0x180029178`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x1800291a4`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x18002925e`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x180029295`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x1800292c3`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x180029371`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`
- `0x18002923d`: `browser_broker.exe -IOAVHost`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::RunAntiVirusScanner(
        FileOperationBroker *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 result; // rax
  RPC_STATUS v8; // eax
  const char *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // ecx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rdi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  const char *v21; // r9
  int LastError; // eax
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  LODWORD(StringUuid) = 0;
  result = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&StringUuid);
  ExitCode = result;
  if ( (int)result >= 0 )
  {
    StringUuid = 0;
    v8 = UuidToStringW(a2, &StringUuid);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x32C,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
        (const char *)(unsigned int)v8,
        bInheritHandles);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x32F,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
        v9);
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    v11 = -1;
    do
      ++v11;
    while ( StringUuid[v11] );
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v13 = v11 + v10 + v12 + 32;
    if ( a4 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a4[v14] );
      v13 += v14 + 1;
    }
    v15 = v13;
    v16 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
    v17 = StringCchPrintfW(v16, (unsigned int)v15, L"%s\\%s %s|%s", Buffer);
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x33C,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
        (const char *)(unsigned int)v17,
        (int)L"browser_broker.exe -IOAVHost");
    if ( a4 )
    {
      v18 = StringCchCatW(v16, v15, L"|");
      if ( v18 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x340,
          (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
          (const char *)(unsigned int)v18,
          (int)L"browser_broker.exe -IOAVHost");
      v19 = StringCchCatW(v16, v15, a4);
      if ( v19 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x341,
          (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
          (const char *)(unsigned int)v19,
          (int)L"browser_broker.exe -IOAVHost");
    }
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( CreateProcessW(0, v16, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x34E,
          (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
          v21);
      if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ExitCode = LastError;
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      CloseHandle(ProcessInformation.hThread);
      CloseHandle(ProcessInformation.hProcess);
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      ExitCode = v20;
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    RpcStringFreeW(&StringUuid);
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x180029100  mov     [rsp-8+arg_0], rbx
0x180029105  push    rbp
0x180029106  push    rsi
0x180029107  push    rdi
0x180029108  push    r14
0x18002910a  push    r15
0x18002910c  lea     rbp, [rsp-210h]
0x180029114  sub     rsp, 310h
0x18002911b  mov     rax, cs:__security_cookie
0x180029122  xor     rax, rsp
0x180029125  mov     [rbp+230h+var_30], rax
0x18002912c  xor     r15d, r15d
0x18002912f  mov     rdi, rdx
0x180029132  lea     rdx, [rsp+330h+StringUuid]; unsigned int *
0x180029137  mov     dword ptr [rsp+330h+StringUuid], r15d
0x18002913c  mov     rbx, r9
0x18002913f  mov     r14, r8
0x180029142  lea     ecx, [r15+1]; unsigned int
0x180029146  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18002914b  mov     [rsp+330h+ExitCode], eax
0x18002914f  test    eax, eax
0x180029151  js      loc_1800293D7
0x180029157  lea     rdx, [rsp+330h+StringUuid]; StringUuid
0x18002915c  mov     [rsp+330h+StringUuid], r15
0x180029161  mov     rcx, rdi; Uuid
0x180029164  call    cs:__imp_UuidToStringW
0x18002916a  mov     rcx, [rbp+238h]; this
0x180029171  test    eax, eax
0x180029173  jns     short loc_18002918A
0x180029175  mov     r9d, eax; char *
0x180029178  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002917f  mov     edx, 32Ch; void *
0x180029184  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002918a  mov     rdi, [rbp+238h]
0x180029191  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x180029195  mov     edx, 104h; uSize
0x18002919a  call    cs:__imp_GetSystemDirectoryW
0x1800291a0  test    eax, eax
0x1800291a2  jnz     short loc_1800291B9
0x1800291a4  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800291ab  mov     edx, 32Fh; void *
0x1800291b0  mov     rcx, rdi; this
0x1800291b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800291bd  lea     rcx, [rbp+230h+Buffer]
0x1800291c1  mov     rax, r8
0x1800291c4  inc     rax
0x1800291c7  cmp     [rcx+rax*2], r15w
0x1800291cc  jnz     short loc_1800291C4
0x1800291ce  mov     rcx, [rsp+330h+StringUuid]
0x1800291d3  mov     rdx, r8
0x1800291d6  inc     rdx
0x1800291d9  cmp     [rcx+rdx*2], r15w
0x1800291de  jnz     short loc_1800291D6
0x1800291e0  mov     rcx, r8
0x1800291e3  inc     rcx
0x1800291e6  cmp     [r14+rcx*2], r15w
0x1800291eb  jnz     short loc_1800291E3
0x1800291ed  add     ecx, 20h ; ' '
0x1800291f0  add     ecx, eax
0x1800291f2  add     ecx, edx
0x1800291f4  test    rbx, rbx
0x1800291f7  jz      short loc_18002920A
0x1800291f9  mov     rax, r8
0x1800291fc  inc     rax
0x1800291ff  cmp     [rbx+rax*2], r15w
0x180029204  jnz     short loc_1800291FC
0x180029206  inc     ecx
0x180029208  add     ecx, eax
0x18002920a  mov     esi, ecx
0x18002920c  mov     eax, 2
0x180029211  mul     rsi
0x180029214  cmovb   rax, r8
0x180029218  mov     rcx, rax; unsigned __int64
0x18002921b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029220  mov     rdi, rax
0x180029223  mov     [rsp+330h+lpEnvironment], r14
0x180029228  mov     rax, [rsp+330h+StringUuid]
0x18002922d  lea     r9, [rbp+230h+Buffer]
0x180029231  mov     qword ptr [rsp+330h+dwCreationFlags], rax
0x180029236  lea     r8, aSSSS; "%s\\%s %s|%s"
0x18002923d  lea     rax, aBrowserBrokerE; "browser_broker.exe -IOAVHost"
0x180029244  mov     edx, esi; unsigned __int64
0x180029246  mov     rcx, rdi; unsigned __int16 *
0x180029249  mov     qword ptr [rsp+330h+bInheritHandles], rax; int
0x18002924e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029253  test    eax, eax
0x180029255  jns     short loc_180029273
0x180029257  mov     rcx, [rbp+238h]; this
0x18002925e  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180029265  mov     r9d, eax; char *
0x180029268  mov     edx, 33Ch; void *
0x18002926d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180029273  test    rbx, rbx
0x180029276  jz      short loc_1800292D8
0x180029278  lea     r8, asc_180030B54; "|"
0x18002927f  mov     rdx, rsi; unsigned __int64
0x180029282  mov     rcx, rdi; unsigned __int16 *
0x180029285  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002928a  test    eax, eax
0x18002928c  jns     short loc_1800292AA
0x18002928e  mov     rcx, [rbp+238h]; this
0x180029295  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002929c  mov     r9d, eax; char *
0x18002929f  mov     edx, 340h; void *
0x1800292a4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800292aa  mov     r8, rbx; unsigned __int16 *
0x1800292ad  mov     rdx, rsi; unsigned __int64
0x1800292b0  mov     rcx, rdi; unsigned __int16 *
0x1800292b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800292b8  test    eax, eax
0x1800292ba  jns     short loc_1800292D8
0x1800292bc  mov     rcx, [rbp+238h]; this
0x1800292c3  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800292ca  mov     r9d, eax; char *
0x1800292cd  mov     edx, 341h; void *
0x1800292d2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800292d8  xor     eax, eax
0x1800292da  lea     rcx, [rbp+230h+StartupInfo+4]; void *
0x1800292de  xorps   xmm0, xmm0
0x1800292e1  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x1800292e6  xor     edx, edx; Val
0x1800292e8  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x1800292ed  lea     r8d, [rax+64h]; Size
0x1800292f1  call    memset_0
0x1800292f6  lea     rax, [rsp+330h+ProcessInformation]
0x1800292fb  mov     [rbp+230h+StartupInfo.cb], 68h ; 'h'
0x180029302  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x180029307  xor     r9d, r9d; lpThreadAttributes
0x18002930a  lea     rax, [rbp+230h+StartupInfo]
0x18002930e  xor     r8d, r8d; lpProcessAttributes
0x180029311  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x180029316  mov     rdx, rdi; lpCommandLine
0x180029319  mov     [rsp+330h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18002931e  xor     ecx, ecx; lpApplicationName
0x180029320  mov     [rsp+330h+lpEnvironment], r15; lpEnvironment
0x180029325  mov     [rsp+330h+dwCreationFlags], r15d; dwCreationFlags
0x18002932a  mov     [rsp+330h+bInheritHandles], r15d; bInheritHandles
0x18002932f  call    cs:__imp_CreateProcessW
0x180029335  test    eax, eax
0x180029337  jnz     short loc_180029356
0x180029339  call    cs:__imp_GetLastError
0x18002933f  test    eax, eax
0x180029341  jle     short loc_18002934B
0x180029343  movzx   eax, ax
0x180029346  or      eax, 80070000h
0x18002934b  mov     [rsp+330h+ExitCode], eax
0x18002934f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029354  jmp     short loc_1800293C8
0x180029356  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hHandle
0x18002935b  or      ebx, 0FFFFFFFFh
0x18002935e  mov     edx, ebx; dwMilliseconds
0x180029360  call    cs:__imp_WaitForSingleObject
0x180029366  cmp     eax, ebx
0x180029368  jnz     short loc_180029383
0x18002936a  mov     rcx, [rbp+238h]; this
0x180029371  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180029378  mov     edx, 34Eh; void *
0x18002937d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029383  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hProcess
0x180029388  lea     rdx, [rsp+330h+ExitCode]; lpExitCode
0x18002938d  call    cs:__imp_GetExitCodeProcess
0x180029393  test    eax, eax
0x180029395  jnz     short loc_1800293B2
0x180029397  call    cs:__imp_GetLastError
0x18002939d  test    eax, eax
0x18002939f  jle     short loc_1800293A9
0x1800293a1  movzx   eax, ax
0x1800293a4  or      eax, 80070000h
0x1800293a9  mov     [rsp+330h+ExitCode], eax
0x1800293ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800293b2  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x1800293b7  call    cs:__imp_CloseHandle
0x1800293bd  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x1800293c2  call    cs:__imp_CloseHandle
0x1800293c8  lea     rcx, [rsp+330h+StringUuid]; String
0x1800293cd  call    cs:__imp_RpcStringFreeW
0x1800293d3  mov     eax, [rsp+330h+ExitCode]
0x1800293d7  mov     rcx, [rbp+230h+var_30]
0x1800293de  xor     rcx, rsp; StackCookie
0x1800293e1  call    __security_check_cookie
0x1800293e6  mov     rbx, [rsp+330h+arg_0]
0x1800293ee  add     rsp, 310h
0x1800293f5  pop     r15
0x1800293f7  pop     r14
0x1800293f9  pop     rdi
0x1800293fa  pop     rsi
0x1800293fb  pop     rbp
0x1800293fc  retn
```
