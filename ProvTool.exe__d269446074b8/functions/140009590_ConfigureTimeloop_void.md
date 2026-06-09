# ConfigureTimeloop(void)

- ea: `0x140009590`
- end: `0x1400098b4`
- name: `?ConfigureTimeloop@@YAJXZ`
- size: `804`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140006b04`

## callees

- `0x140001ebf`
- `0x140007714`
- `0x140007734`
- `0x140008804`
- `0x140009590`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009710`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009710`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000969e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000969e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140009724`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140009724`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009820`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140009629`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140009629`

## string_xrefs

- `0x140009622`: `%windir%\System32\uwfmgr.exe`

## pseudocode

```c
__int64 ConfigureTimeloop(void)
{
  const char *v0; // r9
  __int64 result; // rax
  const char *v2; // r9
  const char *v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  unsigned int LastError; // ebx
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  DWORD v10; // ebx
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  BOOL bInheritHandles; // [rsp+20h] [rbp-308h]
  DWORD ExitCode; // [rsp+50h] [rbp-2D8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-2D0h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+70h] [rbp-2B8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-298h] BYREF
  WCHAR Dst[264]; // [rsp+100h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.cbReserved2 = 0;
  memset(&StartupInfo.lpReserved, 0, 24);
  StartupInfo.lpReserved2 = 0;
  StartupInfo.dwFlags = 0;
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  *(_QWORD *)&ProcessAttributes.bInheritHandle = 0;
  ProcessAttributes.lpSecurityDescriptor = 0;
  if ( ExpandEnvironmentStringsW(L"%windir%\\System32\\uwfmgr.exe", Dst, 0x104u) )
  {
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(
           Dst,
           (LPWSTR)L"uwfmgr.exe overlay reset-persistentstate on",
           &ProcessAttributes,
           0,
           0,
           0,
           0,
           0,
           &StartupInfo,
           &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      ExitCode = 0;
      if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      {
        v10 = ExitCode;
        if ( (ExitCode & 0x80000000) == 0 )
        {
          if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v2);
          if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v2);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x58,
            (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
            (const char *)ExitCode,
            bInheritHandles);
          if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v2);
          if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v2);
          result = v10;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x57,
                      (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
                      v2);
        if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v2);
        if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v2);
        result = LastError;
      }
    }
    else
    {
      v4 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x53,
             (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
             v3);
      if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v2);
      if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v2);
      result = v4;
    }
  }
  else
  {
    result = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x43,
               (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
               v0);
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      ExitCode = wil::details::in1diag3::Return_CaughtException(
                   retaddr,
                   (void *)0x5B,
                   (unsigned int)"onecoreuap\\admin\\prov\\provtool\\timeloop.cpp",
                   v2);
      result = ExitCode;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x140009590  mov     [rsp+arg_0], rbx
0x140009595  push    rdi
0x140009596  sub     rsp, 320h
0x14000959d  mov     rax, cs:__security_cookie
0x1400095a4  xor     rax, rsp
0x1400095a7  mov     [rsp+328h+var_18], rax
0x1400095af  mov     ebx, 68h ; 'h'
0x1400095b4  mov     r8d, ebx; Size
0x1400095b7  xor     edx, edx; Val
0x1400095b9  lea     rcx, [rsp+328h+StartupInfo]; void *
0x1400095c1  call    memset_0
0x1400095c6  mov     [rsp+328h+StartupInfo.cb], ebx
0x1400095cd  xor     edi, edi
0x1400095cf  mov     [rsp+328h+StartupInfo.cbReserved2], di
0x1400095d7  mov     [rsp+328h+StartupInfo.lpDesktop], rdi
0x1400095df  mov     [rsp+328h+StartupInfo.lpReserved], rdi
0x1400095e7  mov     [rsp+328h+StartupInfo.lpReserved2], rdi
0x1400095ef  mov     [rsp+328h+StartupInfo.lpTitle], rdi
0x1400095f7  mov     [rsp+328h+StartupInfo.dwFlags], edi
0x1400095fe  mov     qword ptr [rsp+328h+ProcessAttributes.nLength], 18h
0x140009607  mov     qword ptr [rsp+328h+ProcessAttributes.bInheritHandle], rdi
0x14000960f  mov     [rsp+328h+ProcessAttributes.lpSecurityDescriptor], rdi
0x140009614  mov     r8d, 104h; nSize
0x14000961a  lea     rdx, [rsp+328h+Dst]; lpDst
0x140009622  lea     rcx, Src; "%windir%\\System32\\uwfmgr.exe"
0x140009629  call    cs:__imp_ExpandEnvironmentStringsW
0x14000962f  test    eax, eax
0x140009631  jnz     short loc_14000964F
0x140009633  mov     rcx, [rsp+328h]; this
0x14000963b  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x140009642  lea     edx, [rbx-25h]; void *
0x140009645  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000964a  jmp     loc_14000983A
0x14000964f  xorps   xmm0, xmm0
0x140009652  xor     eax, eax
0x140009654  movups  xmmword ptr [rsp+328h+ProcessInformation.hProcess], xmm0
0x140009659  mov     qword ptr [rsp+328h+ProcessInformation.dwProcessId], rax
0x14000965e  lea     rax, [rsp+328h+ProcessInformation]
0x140009663  mov     [rsp+328h+lpProcessInformation], rax; lpProcessInformation
0x140009668  lea     rax, [rsp+328h+StartupInfo]
0x140009670  mov     [rsp+328h+lpStartupInfo], rax; lpStartupInfo
0x140009675  mov     [rsp+328h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x14000967a  mov     [rsp+328h+lpEnvironment], rdi; lpEnvironment
0x14000967f  mov     [rsp+328h+dwCreationFlags], edi; dwCreationFlags
0x140009683  mov     [rsp+328h+bInheritHandles], edi; int
0x140009687  xor     r9d, r9d; lpThreadAttributes
0x14000968a  lea     r8, [rsp+328h+ProcessAttributes]; lpProcessAttributes
0x14000968f  lea     rdx, CommandLine; "uwfmgr.exe overlay reset-persistentstat"...
0x140009696  lea     rcx, [rsp+328h+Dst]; lpApplicationName
0x14000969e  call    cs:__imp_CreateProcessW
0x1400096a4  test    eax, eax
0x1400096a6  jnz     short loc_140009708
0x1400096a8  mov     rcx, [rsp+328h]; this
0x1400096b0  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x1400096b7  lea     edx, [rax+53h]; void *
0x1400096ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400096bf  mov     ebx, eax
0x1400096c1  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hObject
0x1400096c6  test    rcx, rcx
0x1400096c9  jz      short loc_1400096E1
0x1400096cb  call    cs:__imp_CloseHandle
0x1400096d1  mov     rcx, [rsp+328h]; this
0x1400096d9  test    eax, eax
0x1400096db  jz      loc_14000985B
0x1400096e1  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hObject
0x1400096e6  test    rcx, rcx
0x1400096e9  jz      short loc_140009701
0x1400096eb  call    cs:__imp_CloseHandle
0x1400096f1  mov     rcx, [rsp+328h]; this
0x1400096f9  test    eax, eax
0x1400096fb  jz      loc_140009866
0x140009701  mov     eax, ebx
0x140009703  jmp     loc_14000983A
0x140009708  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000970b  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hHandle
0x140009710  call    cs:__imp_WaitForSingleObject
0x140009716  mov     [rsp+328h+ExitCode], edi
0x14000971a  lea     rdx, [rsp+328h+ExitCode]; lpExitCode
0x14000971f  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hProcess
0x140009724  call    cs:__imp_GetExitCodeProcess
0x14000972a  test    eax, eax
0x14000972c  jnz     short loc_14000978E
0x14000972e  mov     rcx, [rsp+328h]; this
0x140009736  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x14000973d  lea     edx, [rax+57h]; void *
0x140009740  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009745  mov     ebx, eax
0x140009747  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hObject
0x14000974c  test    rcx, rcx
0x14000974f  jz      short loc_140009767
0x140009751  call    cs:__imp_CloseHandle
0x140009757  mov     rcx, [rsp+328h]; this
0x14000975f  test    eax, eax
0x140009761  jz      loc_140009871
0x140009767  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hObject
0x14000976c  test    rcx, rcx
0x14000976f  jz      short loc_140009787
0x140009771  call    cs:__imp_CloseHandle
0x140009777  mov     rcx, [rsp+328h]; this
0x14000977f  test    eax, eax
0x140009781  jz      loc_14000987C
0x140009787  mov     eax, ebx
0x140009789  jmp     loc_14000983A
0x14000978e  mov     ebx, [rsp+328h+ExitCode]
0x140009792  test    ebx, ebx
0x140009794  jns     short loc_1400097F6
0x140009796  mov     rcx, [rsp+328h]; this
0x14000979e  mov     r9d, ebx; char *
0x1400097a1  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\provtool\\time"...
0x1400097a8  mov     edx, 58h ; 'X'; void *
0x1400097ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400097b2  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hObject
0x1400097b7  test    rcx, rcx
0x1400097ba  jz      short loc_1400097D2
0x1400097bc  call    cs:__imp_CloseHandle
0x1400097c2  mov     rcx, [rsp+328h]; this
0x1400097ca  test    eax, eax
0x1400097cc  jz      loc_140009887
0x1400097d2  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hObject
0x1400097d7  test    rcx, rcx
0x1400097da  jz      short loc_1400097F2
0x1400097dc  call    cs:__imp_CloseHandle
0x1400097e2  mov     rcx, [rsp+328h]; this
0x1400097ea  test    eax, eax
0x1400097ec  jz      loc_140009892
0x1400097f2  mov     eax, ebx
0x1400097f4  jmp     short loc_14000983A
0x1400097f6  mov     rcx, [rsp+328h+ProcessInformation.hProcess]; hObject
0x1400097fb  test    rcx, rcx
0x1400097fe  jz      short loc_140009816
0x140009800  call    cs:__imp_CloseHandle
0x140009806  mov     rcx, [rsp+328h]; this
0x14000980e  test    eax, eax
0x140009810  jz      loc_14000989D
0x140009816  mov     rcx, [rsp+328h+ProcessInformation.hThread]; hObject
0x14000981b  test    rcx, rcx
0x14000981e  jz      short loc_140009832
0x140009820  call    cs:__imp_CloseHandle
0x140009826  mov     rcx, [rsp+328h]; this
0x14000982e  test    eax, eax
0x140009830  jz      short loc_1400098A8
0x140009832  xor     eax, eax
0x140009834  jmp     short loc_14000983A
0x140009836  mov     eax, [rsp+328h+ExitCode]
0x14000983a  mov     rcx, [rsp+328h+var_18]
0x140009842  xor     rcx, rsp; StackCookie
0x140009845  call    __security_check_cookie
0x14000984a  mov     rbx, [rsp+328h+arg_0]
0x140009852  add     rsp, 320h
0x140009859  pop     rdi
0x14000985a  retn
0x14000985b  mov     edx, 0A0Bh; void *
0x140009860  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009866  mov     edx, 0A0Bh; void *
0x14000986b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009871  mov     edx, 0A0Bh; void *
0x140009876  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000987c  mov     edx, 0A0Bh; void *
0x140009881  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009887  mov     edx, 0A0Bh; void *
0x14000988c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009892  mov     edx, 0A0Bh; void *
0x140009897  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000989d  mov     edx, 0A0Bh; void *
0x1400098a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400098a8  mov     edx, 0A0Bh; void *
0x1400098ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
