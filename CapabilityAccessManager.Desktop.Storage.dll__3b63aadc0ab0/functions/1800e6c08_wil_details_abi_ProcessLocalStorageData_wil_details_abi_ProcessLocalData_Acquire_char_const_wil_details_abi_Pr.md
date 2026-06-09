# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800e6c08`
- end: `0x1800e6fdc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800e8604`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e6c08`
- `0x1800e73e8`
- `0x1800e793c`
- `0x1800e82b8`
- `0x1800e90b0`
- `0x1800eabf4`
- `0x1800eb6f4`
- `0x1800ebc8c`
- `0x1800ec608`
- `0x1800ec618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e6ca1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e6ca1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e6c80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e6c80`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6d37`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6e75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6ee5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6d37`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6e75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e6ee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6e3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6e3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6e4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6e4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e6c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e6c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6efb`

## string_xrefs

- `0x1800e6f46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x1800e6c08  mov     [rsp-8+arg_10], rbx
0x1800e6c0d  push    rbp
0x1800e6c0e  push    rsi
0x1800e6c0f  push    rdi
0x1800e6c10  push    r14
0x1800e6c12  push    r15
0x1800e6c14  lea     rbp, [rsp-160h]
0x1800e6c1c  sub     rsp, 260h
0x1800e6c23  mov     rax, cs:__security_cookie
0x1800e6c2a  xor     rax, rsp
0x1800e6c2d  mov     [rbp+180h+var_30], rax
0x1800e6c34  mov     r15, rdx
0x1800e6c37  mov     qword ptr [rdx], 0
0x1800e6c3e  mov     rbx, rcx
0x1800e6c41  call    cs:__imp_GetCurrentProcessId
0x1800e6c47  mov     r14d, 78h ; 'x'
0x1800e6c4d  mov     [rsp+280h+var_258], rbx
0x1800e6c52  mov     r9d, eax
0x1800e6c55  mov     [rsp+280h+var_260], r14d; int
0x1800e6c5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800e6c61  mov     edx, 104h; unsigned __int64
0x1800e6c66  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800e6c6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e6c70  mov     r9d, 1F0001h; dwDesiredAccess
0x1800e6c76  lea     rdx, [rsp+280h+Name]; lpName
0x1800e6c7b  xor     r8d, r8d; dwFlags
0x1800e6c7e  xor     ecx, ecx; lpMutexAttributes
0x1800e6c80  call    cs:__imp_CreateMutexExW
0x1800e6c86  mov     rbx, rax
0x1800e6c89  test    rax, rax
0x1800e6c8c  jnz     short loc_1800E6C98
0x1800e6c8e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e6c93  jmp     loc_1800E6F07
0x1800e6c98  xor     r8d, r8d; bAlertable
0x1800e6c9b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800e6c9e  mov     rcx, rbx; hHandle
0x1800e6ca1  call    cs:__imp_WaitForSingleObjectEx
0x1800e6ca7  cmp     eax, 102h
0x1800e6cac  jz      short loc_1800E6CBE
0x1800e6cae  test    eax, 0FFFFFF7Fh
0x1800e6cb3  jnz     loc_1800E6F3F
0x1800e6cb9  mov     rdi, rbx
0x1800e6cbc  jmp     short loc_1800E6CC0
0x1800e6cbe  xor     edi, edi
0x1800e6cc0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800e6cc5  mov     [rsp+280h+hObject], 0
0x1800e6cce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800e6cd3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800e6cd8  mov     esi, eax
0x1800e6cda  test    eax, eax
0x1800e6cdc  jns     short loc_1800E6D5D
0x1800e6cde  mov     rcx, [rbp+188h]; this
0x1800e6ce5  lea     r8, aWil; "wil"
0x1800e6cec  mov     r9d, eax; char *
0x1800e6cef  mov     edx, 66h ; 'f'; void *
0x1800e6cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6cf9  mov     rcx, [rbp+188h]; this
0x1800e6d00  lea     r8, aWil; "wil"
0x1800e6d07  mov     r9d, esi; char *
0x1800e6d0a  mov     edx, 6Fh ; 'o'; void *
0x1800e6d0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6d14  mov     rcx, [rbp+188h]; this
0x1800e6d1b  lea     r8, aWil; "wil"
0x1800e6d22  mov     r9d, esi; char *
0x1800e6d25  mov     edx, 12Eh; void *
0x1800e6d2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6d2f  test    rdi, rdi
0x1800e6d32  jz      short loc_1800E6D45
0x1800e6d34  mov     rcx, rdi; hMutex
0x1800e6d37  call    cs:__imp_ReleaseMutex
0x1800e6d3d  test    eax, eax
0x1800e6d3f  jz      loc_1800E6F58
0x1800e6d45  mov     rcx, rbx; hObject
0x1800e6d48  call    cs:__imp_CloseHandle
0x1800e6d4e  test    eax, eax
0x1800e6d50  jz      loc_1800E6F6A
0x1800e6d56  mov     eax, esi
0x1800e6d58  jmp     loc_1800E6F07
0x1800e6d5d  mov     rax, [rsp+280h+hObject]
0x1800e6d62  lea     rcx, ds:0[rax*4]
0x1800e6d6a  test    rcx, rcx
0x1800e6d6d  jz      short loc_1800E6D7D
0x1800e6d6f  mov     [r15], rcx
0x1800e6d72  mov     eax, [rcx]
0x1800e6d74  inc     eax
0x1800e6d76  mov     [rcx], eax
0x1800e6d78  jmp     loc_1800E6EDD
0x1800e6d7d  mov     rdx, r14; dwBytes
0x1800e6d80  mov     qword ptr [r15], 0
0x1800e6d87  mov     ecx, 8; dwFlags
0x1800e6d8c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800e6d91  mov     rsi, rax
0x1800e6d94  test    rax, rax
0x1800e6d97  jnz     short loc_1800E6DBF
0x1800e6d99  mov     rcx, [rbp+188h]; this
0x1800e6da0  lea     r8, aWil; "wil"
0x1800e6da7  mov     r14d, 8007000Eh
0x1800e6dad  mov     edx, 14Bh; void *
0x1800e6db2  mov     r9d, r14d; char *
0x1800e6db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6dba  jmp     loc_1800E6E52
0x1800e6dbf  xorps   xmm0, xmm0
0x1800e6dc2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800e6dc8  test    sil, 3
0x1800e6dcc  jnz     loc_1800E6F7C
0x1800e6dd2  mov     r9, rsi
0x1800e6dd5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800e6dda  shr     r9, 2; unsigned __int64
0x1800e6dde  lea     rcx, [rsp+280h+hObject]; this
0x1800e6de3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800e6de8  mov     r14d, eax
0x1800e6deb  test    eax, eax
0x1800e6ded  jns     loc_1800E6E99
0x1800e6df3  mov     rcx, [rbp+188h]; this
0x1800e6dfa  lea     r8, aWil; "wil"
0x1800e6e01  mov     r9d, eax; char *
0x1800e6e04  mov     edx, 14Eh; void *
0x1800e6e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6e0e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800e6e13  test    rcx, rcx
0x1800e6e16  jz      short loc_1800E6E26
0x1800e6e18  call    cs:__imp_CloseHandle
0x1800e6e1e  test    eax, eax
0x1800e6e20  jz      loc_1800E6F82
0x1800e6e26  mov     rcx, [rsp+280h+hObject]; hObject
0x1800e6e2b  test    rcx, rcx
0x1800e6e2e  jz      short loc_1800E6E3E
0x1800e6e30  call    cs:__imp_CloseHandle
0x1800e6e36  test    eax, eax
0x1800e6e38  jz      loc_1800E6F94
0x1800e6e3e  call    cs:__imp_GetProcessHeap
0x1800e6e44  mov     r8, rsi; lpMem
0x1800e6e47  xor     edx, edx; dwFlags
0x1800e6e49  mov     rcx, rax; hHeap
0x1800e6e4c  call    cs:__imp_HeapFree
0x1800e6e52  mov     rcx, [rbp+188h]; this
0x1800e6e59  lea     r8, aWil; "wil"
0x1800e6e60  mov     r9d, r14d; char *
0x1800e6e63  mov     edx, 137h; void *
0x1800e6e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6e6d  test    rdi, rdi
0x1800e6e70  jz      short loc_1800E6E83
0x1800e6e72  mov     rcx, rdi; hMutex
0x1800e6e75  call    cs:__imp_ReleaseMutex
0x1800e6e7b  test    eax, eax
0x1800e6e7d  jz      loc_1800E6FA6
0x1800e6e83  mov     rcx, rbx; hObject
0x1800e6e86  call    cs:__imp_CloseHandle
0x1800e6e8c  test    eax, eax
0x1800e6e8e  jz      loc_1800E6FB8
0x1800e6e94  mov     eax, r14d
0x1800e6e97  jmp     short loc_1800E6F07
0x1800e6e99  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800e6e9e  xor     edx, edx; Val
0x1800e6ea0  mov     dword ptr [rsi], 1
0x1800e6ea6  lea     rcx, [rsi+22h]; void *
0x1800e6eaa  mov     [rsi+8], rbx
0x1800e6eae  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800e6eb3  lea     r8d, [rdx+56h]; Size
0x1800e6eb7  call    memset_0
0x1800e6ebc  xor     edx, edx; Val
0x1800e6ebe  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800e6ec4  lea     rcx, [rsi+28h]; void *
0x1800e6ec8  mov     dword ptr [rsi+24h], 1
0x1800e6ecf  lea     r8d, [rdx+50h]; Size
0x1800e6ed3  call    memset_0
0x1800e6ed8  xor     ebx, ebx
0x1800e6eda  mov     [r15], rsi
0x1800e6edd  test    rdi, rdi
0x1800e6ee0  jz      short loc_1800E6EF3
0x1800e6ee2  mov     rcx, rdi; hMutex
0x1800e6ee5  call    cs:__imp_ReleaseMutex
0x1800e6eeb  test    eax, eax
0x1800e6eed  jz      loc_1800E6FCA
0x1800e6ef3  test    rbx, rbx
0x1800e6ef6  jz      short loc_1800E6F05
0x1800e6ef8  mov     rcx, rbx; hObject
0x1800e6efb  call    cs:__imp_CloseHandle
0x1800e6f01  test    eax, eax
0x1800e6f03  jz      short loc_1800E6F2D
0x1800e6f05  xor     eax, eax
0x1800e6f07  mov     rcx, [rbp+180h+var_30]
0x1800e6f0e  xor     rcx, rsp; StackCookie
0x1800e6f11  call    __security_check_cookie
0x1800e6f16  mov     rbx, [rsp+280h+arg_10]
0x1800e6f1e  add     rsp, 260h
0x1800e6f25  pop     r15
0x1800e6f27  pop     r14
0x1800e6f29  pop     rdi
0x1800e6f2a  pop     rsi
0x1800e6f2b  pop     rbp
0x1800e6f2c  retn
0x1800e6f2d  mov     rcx, [rbp+188h]; this
0x1800e6f34  mov     edx, 0A0Bh; void *
0x1800e6f39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6f3f  mov     rcx, [rbp+188h]; this
0x1800e6f46  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800e6f4d  mov     edx, 0E01h; void *
0x1800e6f52  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e6f58  mov     rcx, [rbp+188h]; this
0x1800e6f5f  mov     edx, 0A15h; void *
0x1800e6f64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6f6a  mov     rcx, [rbp+188h]; this
0x1800e6f71  mov     edx, 0A0Bh; void *
0x1800e6f76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6f7c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800e6f82  mov     rcx, [rbp+188h]; this
0x1800e6f89  mov     edx, 0A0Bh; void *
0x1800e6f8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6f94  mov     rcx, [rbp+188h]; this
0x1800e6f9b  mov     edx, 0A0Bh; void *
0x1800e6fa0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6fa6  mov     rcx, [rbp+188h]; this
0x1800e6fad  mov     edx, 0A15h; void *
0x1800e6fb2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6fb8  mov     rcx, [rbp+188h]; this
0x1800e6fbf  mov     edx, 0A0Bh; void *
0x1800e6fc4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e6fca  mov     rcx, [rbp+188h]; this
0x1800e6fd1  mov     edx, 0A15h; void *
0x1800e6fd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
