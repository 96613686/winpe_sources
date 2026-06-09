# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003b08`
- end: `0x180003ea6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800054f0`

## callees

- `0x180001670`
- `0x180002034`
- `0x180003b08`
- `0x18000427c`
- `0x180004798`
- `0x180005288`
- `0x180005f68`
- `0x180007964`
- `0x180008458`
- `0x1800088bc`
- `0x18000916c`
- `0x18000917c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c22`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c22`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ba1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ba1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x180003b08  mov     [rsp-8+arg_10], rbx
0x180003b0d  push    rbp
0x180003b0e  push    rsi
0x180003b0f  push    rdi
0x180003b10  push    r14
0x180003b12  push    r15
0x180003b14  lea     rbp, [rsp-160h]
0x180003b1c  sub     rsp, 260h
0x180003b23  mov     rax, cs:__security_cookie
0x180003b2a  xor     rax, rsp
0x180003b2d  mov     [rbp+180h+var_30], rax
0x180003b34  mov     r15, rdx
0x180003b37  mov     qword ptr [rdx], 0
0x180003b3e  mov     rbx, rcx
0x180003b41  call    cs:__imp_GetCurrentProcessId
0x180003b47  mov     r14d, 78h ; 'x'
0x180003b4d  mov     [rsp+280h+var_258], rbx
0x180003b52  mov     r9d, eax
0x180003b55  mov     [rsp+280h+var_260], r14d; int
0x180003b5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003b61  mov     edx, 104h; unsigned __int64
0x180003b66  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b70  mov     r9d, 1F0001h; dwDesiredAccess
0x180003b76  lea     rdx, [rsp+280h+Name]; lpName
0x180003b7b  xor     r8d, r8d; dwFlags
0x180003b7e  xor     ecx, ecx; lpMutexAttributes
0x180003b80  call    cs:__imp_CreateMutexExW
0x180003b86  mov     rbx, rax
0x180003b89  test    rax, rax
0x180003b8c  jnz     short loc_180003B98
0x180003b8e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b93  jmp     loc_180003DDD
0x180003b98  xor     r8d, r8d; bAlertable
0x180003b9b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b9e  mov     rcx, rbx; hHandle
0x180003ba1  call    cs:__imp_WaitForSingleObjectEx
0x180003ba7  cmp     eax, 102h
0x180003bac  jz      short loc_180003BBE
0x180003bae  test    eax, 0FFFFFF7Fh
0x180003bb3  jnz     loc_180003E15
0x180003bb9  mov     rdi, rbx
0x180003bbc  jmp     short loc_180003BC0
0x180003bbe  xor     edi, edi
0x180003bc0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003bc5  mov     [rsp+280h+hObject], 0
0x180003bce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003bd3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003bd8  mov     esi, eax
0x180003bda  test    eax, eax
0x180003bdc  jns     short loc_180003C48
0x180003bde  mov     rcx, [rbp+188h]; this
0x180003be5  mov     r9d, eax; char *
0x180003be8  mov     edx, 66h ; 'f'; void *
0x180003bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bf2  mov     rcx, [rbp+188h]; this
0x180003bf9  mov     r9d, esi; char *
0x180003bfc  mov     edx, 6Fh ; 'o'; void *
0x180003c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c06  mov     rcx, [rbp+188h]; this
0x180003c0d  mov     r9d, esi; char *
0x180003c10  mov     edx, 12Eh; void *
0x180003c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1a  test    rdi, rdi
0x180003c1d  jz      short loc_180003C30
0x180003c1f  mov     rcx, rdi; hMutex
0x180003c22  call    cs:__imp_ReleaseMutex
0x180003c28  test    eax, eax
0x180003c2a  jz      loc_180003E22
0x180003c30  mov     rcx, rbx; hObject
0x180003c33  call    cs:__imp_CloseHandle
0x180003c39  test    eax, eax
0x180003c3b  jz      loc_180003E34
0x180003c41  mov     eax, esi
0x180003c43  jmp     loc_180003DDD
0x180003c48  mov     rax, [rsp+280h+hObject]
0x180003c4d  lea     rcx, ds:0[rax*4]
0x180003c55  test    rcx, rcx
0x180003c58  jz      short loc_180003C68
0x180003c5a  mov     [r15], rcx
0x180003c5d  mov     eax, [rcx]
0x180003c5f  inc     eax
0x180003c61  mov     [rcx], eax
0x180003c63  jmp     loc_180003DB3
0x180003c68  mov     rdx, r14; dwBytes
0x180003c6b  mov     qword ptr [r15], 0
0x180003c72  mov     ecx, 8; dwFlags
0x180003c77  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c7c  mov     rsi, rax
0x180003c7f  test    rax, rax
0x180003c82  jnz     short loc_180003CA3
0x180003c84  mov     rcx, [rbp+188h]; this
0x180003c8b  mov     r14d, 8007000Eh
0x180003c91  mov     r9d, r14d; char *
0x180003c94  mov     edx, 14Bh; void *
0x180003c99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c9e  jmp     loc_180003D2F
0x180003ca3  xorps   xmm0, xmm0
0x180003ca6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003cac  test    sil, 3
0x180003cb0  jnz     loc_180003E46
0x180003cb6  mov     r9, rsi
0x180003cb9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003cbe  shr     r9, 2; unsigned __int64
0x180003cc2  lea     rcx, [rsp+280h+hObject]; this
0x180003cc7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ccc  mov     r14d, eax
0x180003ccf  test    eax, eax
0x180003cd1  jns     loc_180003D6F
0x180003cd7  mov     rcx, [rbp+188h]; this
0x180003cde  mov     r9d, eax; char *
0x180003ce1  mov     edx, 14Eh; void *
0x180003ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ceb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003cf0  test    rcx, rcx
0x180003cf3  jz      short loc_180003D03
0x180003cf5  call    cs:__imp_CloseHandle
0x180003cfb  test    eax, eax
0x180003cfd  jz      loc_180003E4C
0x180003d03  mov     rcx, [rsp+280h+hObject]; hObject
0x180003d08  test    rcx, rcx
0x180003d0b  jz      short loc_180003D1B
0x180003d0d  call    cs:__imp_CloseHandle
0x180003d13  test    eax, eax
0x180003d15  jz      loc_180003E5E
0x180003d1b  call    cs:__imp_GetProcessHeap
0x180003d21  mov     r8, rsi; lpMem
0x180003d24  xor     edx, edx; dwFlags
0x180003d26  mov     rcx, rax; hHeap
0x180003d29  call    cs:__imp_HeapFree
0x180003d2f  mov     rcx, [rbp+188h]; this
0x180003d36  mov     r9d, r14d; char *
0x180003d39  mov     edx, 137h; void *
0x180003d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d43  test    rdi, rdi
0x180003d46  jz      short loc_180003D59
0x180003d48  mov     rcx, rdi; hMutex
0x180003d4b  call    cs:__imp_ReleaseMutex
0x180003d51  test    eax, eax
0x180003d53  jz      loc_180003E70
0x180003d59  mov     rcx, rbx; hObject
0x180003d5c  call    cs:__imp_CloseHandle
0x180003d62  test    eax, eax
0x180003d64  jz      loc_180003E82
0x180003d6a  mov     eax, r14d
0x180003d6d  jmp     short loc_180003DDD
0x180003d6f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d74  xor     edx, edx; Val
0x180003d76  mov     dword ptr [rsi], 1
0x180003d7c  lea     rcx, [rsi+22h]; void *
0x180003d80  mov     [rsi+8], rbx
0x180003d84  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003d89  lea     r8d, [rdx+56h]; Size
0x180003d8d  call    memset_0
0x180003d92  xor     edx, edx; Val
0x180003d94  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d9a  lea     rcx, [rsi+28h]; void *
0x180003d9e  mov     dword ptr [rsi+24h], 1
0x180003da5  lea     r8d, [rdx+50h]; Size
0x180003da9  call    memset_0
0x180003dae  xor     ebx, ebx
0x180003db0  mov     [r15], rsi
0x180003db3  test    rdi, rdi
0x180003db6  jz      short loc_180003DC9
0x180003db8  mov     rcx, rdi; hMutex
0x180003dbb  call    cs:__imp_ReleaseMutex
0x180003dc1  test    eax, eax
0x180003dc3  jz      loc_180003E94
0x180003dc9  test    rbx, rbx
0x180003dcc  jz      short loc_180003DDB
0x180003dce  mov     rcx, rbx; hObject
0x180003dd1  call    cs:__imp_CloseHandle
0x180003dd7  test    eax, eax
0x180003dd9  jz      short loc_180003E03
0x180003ddb  xor     eax, eax
0x180003ddd  mov     rcx, [rbp+180h+var_30]
0x180003de4  xor     rcx, rsp; StackCookie
0x180003de7  call    __security_check_cookie
0x180003dec  mov     rbx, [rsp+280h+arg_10]
0x180003df4  add     rsp, 260h
0x180003dfb  pop     r15
0x180003dfd  pop     r14
0x180003dff  pop     rdi
0x180003e00  pop     rsi
0x180003e01  pop     rbp
0x180003e02  retn
0x180003e03  mov     rcx, [rbp+188h]; this
0x180003e0a  mov     edx, 0A0Bh; void *
0x180003e0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e15  mov     rcx, [rbp+188h]; this
0x180003e1c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003e22  mov     rcx, [rbp+188h]; this
0x180003e29  mov     edx, 0A15h; void *
0x180003e2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e34  mov     rcx, [rbp+188h]; this
0x180003e3b  mov     edx, 0A0Bh; void *
0x180003e40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e46  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e4c  mov     rcx, [rbp+188h]; this
0x180003e53  mov     edx, 0A0Bh; void *
0x180003e58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e5e  mov     rcx, [rbp+188h]; this
0x180003e65  mov     edx, 0A0Bh; void *
0x180003e6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e70  mov     rcx, [rbp+188h]; this
0x180003e77  mov     edx, 0A15h; void *
0x180003e7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e82  mov     rcx, [rbp+188h]; this
0x180003e89  mov     edx, 0A0Bh; void *
0x180003e8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e94  mov     rcx, [rbp+188h]; this
0x180003e9b  mov     edx, 0A15h; void *
0x180003ea0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
