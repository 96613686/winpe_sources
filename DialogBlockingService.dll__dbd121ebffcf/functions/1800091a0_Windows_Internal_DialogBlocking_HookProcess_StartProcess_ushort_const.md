# Windows::Internal::DialogBlocking::HookProcess::StartProcess(ushort const *)

- ea: `0x1800091a0`
- end: `0x1800093b6`
- name: `?StartProcess@HookProcess@DialogBlocking@Internal@Windows@@AEAAJPEBG@Z`
- size: `534`
- prototype: `__int64 __fastcall(Windows::Internal::DialogBlocking::HookProcess *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800090a0`

## callees

- `0x18000205a`
- `0x1800020d0`
- `0x1800067e4`
- `0x1800091a0`
- `0x18000952c`
- `0x180009588`
- `0x18000c7f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800092b6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800092b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000936d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000936d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000931b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000931b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000937b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000939d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000937b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000939d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000933d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000933d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009388`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009284`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009284`
- `WTSAPI32!WTSQueryUserToken` at `0x180009205`
- `WTSAPI32!WTSQueryUserToken` at `0x180009205`

## string_xrefs

- `0x180009213`: `base\embedded\sys\dialogblocking\service\lib\hookmgr.cpp`
- `0x180009329`: `base\embedded\sys\dialogblocking\service\lib\hookmgr.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::DialogBlocking::HookProcess::StartProcess(
        Windows::Internal::DialogBlocking::HookProcess *this,
        const unsigned __int16 *a2)
{
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned int LastError; // ebx
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  size_t v11; // rbx
  size_t v12; // r14
  char *v13; // rax
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  char *v17; // rdi
  const char *v18; // r9
  HANDLE hProcess; // r14
  char *v20; // rsi
  DWORD v21; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  HANDLE phToken; // [rsp+140h] [rbp+77h] BYREF
  char *v26; // [rsp+148h] [rbp+7Fh]

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 104;
  StartupInfo.wShowWindow = 5;
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  phToken = 0;
  if ( !WTSQueryUserToken(*((_DWORD *)this + 1), &phToken) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x60,
                  (unsigned int)"base\\embedded\\sys\\dialogblocking\\service\\lib\\hookmgr.cpp",
                  v6);
LABEL_3:
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    return LastError;
  }
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, v4, v5, v6);
  v9 = 0x7FFFFFFF;
  v10 = a2;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = 2 * (v10 - a2);
  v12 = v11 + 2;
  v13 = (char *)LocalAlloc(0, v11 + 2);
  v17 = v13;
  if ( v13 )
  {
    if ( v11 )
    {
      if ( v12 < v11 )
      {
        memset_0(v13, 0, v12);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v13, a2, v11);
      }
    }
    *(_WORD *)&v17[v11] = 0;
  }
  v26 = v17;
  if ( !v17 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v14, v15, v16);
  if ( !CreateProcessAsUserW(phToken, 0, (LPWSTR)v17, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x63,
                  (unsigned int)"base\\embedded\\sys\\dialogblocking\\service\\lib\\hookmgr.cpp",
                  v18);
    LocalFree(v17);
    goto LABEL_3;
  }
  hProcess = ProcessInformation.hProcess;
  v20 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v21 = GetLastError();
    CloseHandle(v20);
    SetLastError(v21);
  }
  *((_QWORD *)this + 2) = hProcess;
  CloseHandle(ProcessInformation.hThread);
  *(_BYTE *)this = 1;
  LocalFree(v17);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  return 0;
}

```

## disassembly

```asm
0x1800091a0  push    rbp
0x1800091a2  push    rbx
0x1800091a3  push    rsi
0x1800091a4  push    rdi
0x1800091a5  push    r12
0x1800091a7  push    r14
0x1800091a9  push    r15
0x1800091ab  lea     rbp, [rsp-27h]
0x1800091b0  sub     rsp, 0F0h
0x1800091b7  mov     rsi, rdx
0x1800091ba  mov     r15, rcx
0x1800091bd  xor     r12d, r12d
0x1800091c0  mov     [rbp+57h+arg_0], r12d
0x1800091c4  lea     ebx, [r12+68h]
0x1800091c9  mov     r8d, ebx; Size
0x1800091cc  xor     edx, edx; Val
0x1800091ce  lea     rcx, [rbp+57h+StartupInfo]; void *
0x1800091d2  call    memset_0
0x1800091d7  xorps   xmm0, xmm0
0x1800091da  xor     eax, eax
0x1800091dc  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1800091e0  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1800091e4  mov     [rbp+57h+StartupInfo.cb], ebx
0x1800091e7  lea     eax, [rbx-63h]
0x1800091ea  mov     [rbp+57h+StartupInfo.wShowWindow], ax
0x1800091ee  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1800091f5  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x1800091f9  mov     [rbp+57h+phToken], r12
0x1800091fd  lea     rdx, [rbp+57h+phToken]; phToken
0x180009201  mov     ecx, [r15+4]; SessionId
0x180009205  call    cs:__imp_WTSQueryUserToken
0x18000920b  test    eax, eax
0x18000920d  jnz     short loc_18000924C
0x18000920f  mov     rcx, [rbp+5Fh]; this
0x180009213  lea     r8, aBaseEmbeddedSy_0; "base\\embedded\\sys\\dialogblocking\\se"...
0x18000921a  lea     edx, [rbx-8]; void *
0x18000921d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009222  mov     ebx, eax
0x180009224  mov     rcx, [rbp+57h+phToken]; hObject
0x180009228  lea     rdx, [rcx-1]
0x18000922c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180009230  ja      short loc_180009238
0x180009232  call    cs:__imp_CloseHandle
0x180009238  mov     eax, ebx
0x18000923a  add     rsp, 0F0h
0x180009241  pop     r15
0x180009243  pop     r14
0x180009245  pop     r12
0x180009247  pop     rdi
0x180009248  pop     rsi
0x180009249  pop     rbx
0x18000924a  pop     rbp
0x18000924b  retn
0x18000924c  mov     rcx, [rbp+5Fh]; this
0x180009250  test    rsi, rsi
0x180009253  jz      loc_1800093AA
0x180009259  mov     ecx, 7FFFFFFFh
0x18000925e  mov     rax, rsi
0x180009261  cmp     [rax], r12w
0x180009265  jz      short loc_180009271
0x180009267  add     rax, 2
0x18000926b  sub     rcx, 1
0x18000926f  jnz     short loc_180009261
0x180009271  sub     rax, rsi
0x180009274  sar     rax, 1
0x180009277  lea     rbx, [rax+rax]
0x18000927b  lea     r14, [rbx+2]
0x18000927f  mov     rdx, r14; uBytes
0x180009282  xor     ecx, ecx; uFlags
0x180009284  call    cs:__imp_LocalAlloc
0x18000928a  mov     rdi, rax
0x18000928d  test    rax, rax
0x180009290  jz      short loc_1800092CC
0x180009292  test    rbx, rbx
0x180009295  jz      short loc_1800092C7
0x180009297  mov     rcx, rax; void *
0x18000929a  cmp     r14, rbx
0x18000929d  jb      short loc_1800092AC
0x18000929f  mov     r8, rbx; Size
0x1800092a2  mov     rdx, rsi; Src
0x1800092a5  call    memcpy_0
0x1800092aa  jmp     short loc_1800092C7
0x1800092ac  mov     r8, r14; Size
0x1800092af  xor     edx, edx; Val
0x1800092b1  call    memset_0
0x1800092b6  call    cs:__imp__o__errno
0x1800092bc  mov     dword ptr [rax], 22h ; '"'
0x1800092c2  call    _invalid_parameter_noinfo
0x1800092c7  mov     [rbx+rdi], r12w
0x1800092cc  mov     [rbp+57h+arg_18], rdi
0x1800092d0  mov     [rbp+57h+arg_0], 2
0x1800092d7  mov     rcx, [rbp+5Fh]; this
0x1800092db  test    rdi, rdi
0x1800092de  jz      loc_1800093B0
0x1800092e4  lea     rax, [rbp+57h+ProcessInformation]
0x1800092e8  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x1800092ed  lea     rax, [rbp+57h+StartupInfo]
0x1800092f1  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x1800092f6  mov     [rsp+120h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800092fb  mov     [rsp+120h+lpEnvironment], r12; lpEnvironment
0x180009300  mov     [rsp+120h+dwCreationFlags], r12d; dwCreationFlags
0x180009305  mov     [rsp+120h+bInheritHandles], r12d; bInheritHandles
0x18000930a  mov     [rsp+120h+lpThreadAttributes], r12; lpThreadAttributes
0x18000930f  xor     r9d, r9d; lpProcessAttributes
0x180009312  mov     r8, rdi; lpCommandLine
0x180009315  xor     edx, edx; lpApplicationName
0x180009317  mov     rcx, [rbp+57h+phToken]; hToken
0x18000931b  call    cs:__imp_CreateProcessAsUserW
0x180009321  test    eax, eax
0x180009323  jnz     short loc_180009348
0x180009325  mov     rcx, [rbp+5Fh]; this
0x180009329  lea     r8, aBaseEmbeddedSy_0; "base\\embedded\\sys\\dialogblocking\\se"...
0x180009330  lea     edx, [rax+63h]; void *
0x180009333  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009338  mov     ebx, eax
0x18000933a  mov     rcx, rdi; hMem
0x18000933d  call    cs:__imp_LocalFree
0x180009343  jmp     loc_180009224
0x180009348  mov     r14, [rbp+57h+ProcessInformation.hProcess]
0x18000934c  mov     rsi, [r15+10h]
0x180009350  lea     rax, [rsi-1]
0x180009354  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009358  ja      short loc_180009373
0x18000935a  call    cs:__imp_GetLastError
0x180009360  mov     ebx, eax
0x180009362  mov     rcx, rsi; hObject
0x180009365  call    cs:__imp_CloseHandle
0x18000936b  mov     ecx, ebx; dwErrCode
0x18000936d  call    cs:__imp_SetLastError
0x180009373  mov     [r15+10h], r14
0x180009377  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18000937b  call    cs:__imp_CloseHandle
0x180009381  mov     byte ptr [r15], 1
0x180009385  mov     rcx, rdi; hMem
0x180009388  call    cs:__imp_LocalFree
0x18000938e  nop
0x18000938f  mov     rcx, [rbp+57h+phToken]; hObject
0x180009393  lea     rax, [rcx-1]
0x180009397  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000939b  ja      short loc_1800093A3
0x18000939d  call    cs:__imp_CloseHandle
0x1800093a3  xor     eax, eax
0x1800093a5  jmp     loc_18000923A
0x1800093aa  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800093b0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
