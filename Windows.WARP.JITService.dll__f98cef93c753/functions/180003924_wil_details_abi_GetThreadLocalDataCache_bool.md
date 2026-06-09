# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003924`
- end: `0x180003d0c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `1000`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180003e00`

## callees

- `0x180001364`
- `0x1800017fc`
- `0x180001e80`
- `0x180002de0`
- `0x180002e24`
- `0x180002e40`
- `0x180003280`
- `0x180003490`
- `0x180003924`
- `0x180008a80`
- `0x18000941c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039ab`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000396e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000396e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0e`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // r12
  __int64 v2; // rsi
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  HANDLE v7; // r15
  int LastErrorFailHr; // r14d
  __int64 v9; // rbx
  DWORD CurrentThreadId; // r8d
  __int64 i; // rax
  DWORD v12; // eax
  void *v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  void *v16; // rdi
  int Pointer; // eax
  unsigned __int64 v18; // r8
  __int64 v19; // r8
  const char *v20; // r9
  __int64 v21; // r8
  const char *v22; // r9
  _QWORD *v23; // rax
  unsigned int v24; // r8d
  _QWORD *v25; // r13
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  __int64 v34; // r8
  const char *v35; // r9
  __int64 v36; // r8
  const char *v37; // r9
  __int128 v38; // xmm0
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // r8
  const char *v42; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( !wil::details_abi::g_pProcessLocalData )
    return (struct wil::details_abi::ThreadLocalData *)v2;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
    Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
    v6 = Mutex;
    if ( !Mutex )
    {
      v7 = 0;
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
      goto LABEL_5;
    }
    v12 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
    if ( v12 == 258 )
    {
      v16 = 0;
    }
    else
    {
      if ( (v12 & 0xFFFFFF7F) != 0 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, v13, v14, v15);
      v16 = v6;
    }
    hObject[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, hObject);
    if ( Pointer < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v18, (const char *)(unsigned int)Pointer, 120);
      if ( v16 && !ReleaseMutex(v16) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v19, v20);
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      goto LABEL_8;
    }
    v7 = hObject[0];
    if ( hObject[0] )
    {
      ++*(_DWORD *)hObject[0];
      goto LABEL_34;
    }
    v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v18);
    v25 = v23;
    if ( v23 )
    {
      *(_OWORD *)hObject = 0;
      v27 = wil::details_abi::SemaphoreValue::CreateFromPointer(
              (wil::details_abi::SemaphoreValue *)hObject,
              Name,
              (unsigned __int64)v23);
      LastErrorFailHr = v27;
      if ( v27 >= 0 )
      {
        v38 = *(_OWORD *)hObject;
        *(_DWORD *)v25 = 1;
        v25[1] = v6;
        *((_OWORD *)v25 + 1) = v38;
        memset_0((char *)v25 + 34, 0, 0x56u);
        *((_WORD *)v25 + 16) = 88;
        *((_DWORD *)v25 + 9) = 1;
        memset_0(v25 + 5, 0, 0x50u);
        v6 = 0;
        v7 = v25;
LABEL_34:
        if ( v16 && !ReleaseMutex(v16) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v39, v40);
        if ( v6 && !CloseHandle(v6) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
LABEL_6:
        if ( !*(_QWORD *)(v1 + 8) )
          *(_QWORD *)(v1 + 8) = v7;
        goto LABEL_8;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
      if ( hObject[1] && !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      if ( hObject[0] && !CloseHandle(hObject[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v25);
    }
    else
    {
      LastErrorFailHr = -2147024882;
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)(unsigned int)LastErrorFailHr, v44);
    if ( v16 && !ReleaseMutex(v16) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
LABEL_5:
    if ( LastErrorFailHr < 0 )
      goto LABEL_8;
    goto LABEL_6;
  }
LABEL_8:
  v9 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
  if ( v9 )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( i = *(_QWORD *)(v9 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v2 = i + 16;
        if ( i != -16 && !*(_QWORD *)(i + 24) )
          *(_QWORD *)(i + 24) = v9 + 4;
        return (struct wil::details_abi::ThreadLocalData *)v2;
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x180003924  push    rbp
0x180003926  push    rbx
0x180003927  push    rsi
0x180003928  push    rdi
0x180003929  push    r12
0x18000392b  push    r13
0x18000392d  push    r14
0x18000392f  push    r15
0x180003931  lea     rbp, [rsp-168h]
0x180003939  sub     rsp, 268h
0x180003940  mov     rax, cs:__security_cookie
0x180003947  xor     rax, rsp
0x18000394a  mov     [rbp+1A0h+var_50], rax
0x180003951  mov     r12, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003958  xor     esi, esi
0x18000395a  test    r12, r12
0x18000395d  jz      loc_180003C49
0x180003963  cmp     [r12+8], rsi
0x180003968  jnz     short loc_1800039D5
0x18000396a  mov     rbx, [r12]
0x18000396e  call    cs:__imp_GetCurrentProcessId
0x180003974  lea     r14d, [rsi+78h]
0x180003978  mov     [rsp+2A0h+var_278], rbx
0x18000397d  mov     r9d, eax
0x180003980  mov     [rsp+2A0h+var_280], r14d; int
0x180003985  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000398c  mov     edx, 104h; unsigned __int64
0x180003991  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180003996  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000399b  mov     r9d, 1F0001h; dwDesiredAccess
0x1800039a1  lea     rdx, [rsp+2A0h+Name]; lpName
0x1800039a6  xor     r8d, r8d; dwFlags
0x1800039a9  xor     ecx, ecx; lpMutexAttributes
0x1800039ab  call    cs:__imp_CreateMutexExW
0x1800039b1  mov     rbx, rax
0x1800039b4  test    rax, rax
0x1800039b7  jnz     short loc_180003A21
0x1800039b9  xor     r15d, r15d
0x1800039bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800039c1  mov     r14d, eax
0x1800039c4  test    r14d, r14d
0x1800039c7  js      short loc_1800039D5
0x1800039c9  cmp     [r12+8], rsi
0x1800039ce  jnz     short loc_1800039D5
0x1800039d0  mov     [r12+8], r15
0x1800039d5  mov     rax, [r12+8]
0x1800039da  lea     rcx, [rax+20h]
0x1800039de  neg     rax
0x1800039e1  sbb     rbx, rbx
0x1800039e4  and     rbx, rcx
0x1800039e7  jz      loc_180003C49
0x1800039ed  call    cs:__imp_GetCurrentThreadId
0x1800039f3  mov     ecx, eax
0x1800039f5  mov     r8d, eax
0x1800039f8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003a02  shr     rcx, 2
0x180003a06  mul     rcx
0x180003a09  shr     rdx, 3
0x180003a0d  lea     rax, [rdx+rdx*4]
0x180003a11  add     rax, rax
0x180003a14  sub     rcx, rax
0x180003a17  mov     rax, [rbx+rcx*8+8]
0x180003a1c  jmp     loc_180003C2A
0x180003a21  xor     r8d, r8d; bAlertable
0x180003a24  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003a27  mov     rcx, rbx; hHandle
0x180003a2a  call    cs:__imp_WaitForSingleObjectEx
0x180003a30  cmp     eax, 102h
0x180003a35  jz      short loc_180003A47
0x180003a37  test    eax, 0FFFFFF7Fh
0x180003a3c  jnz     loc_180003CB7
0x180003a42  mov     rdi, rbx
0x180003a45  jmp     short loc_180003A49
0x180003a47  xor     edi, edi
0x180003a49  lea     rdx, [rsp+2A0h+hObject]; void **
0x180003a4e  mov     [rsp+2A0h+hObject], rsi
0x180003a53  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180003a58  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003a5d  test    eax, eax
0x180003a5f  jns     short loc_180003AA1
0x180003a61  mov     rcx, [rbp+1A8h]; this
0x180003a68  mov     r9d, eax; char *
0x180003a6b  mov     edx, 12Eh; void *
0x180003a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a75  test    rdi, rdi
0x180003a78  jz      short loc_180003A8B
0x180003a7a  mov     rcx, rdi; hMutex
0x180003a7d  call    cs:__imp_ReleaseMutex
0x180003a83  test    eax, eax
0x180003a85  jz      loc_180003CC4
0x180003a8b  mov     rcx, rbx; hObject
0x180003a8e  call    cs:__imp_CloseHandle
0x180003a94  test    eax, eax
0x180003a96  jz      loc_180003C81
0x180003a9c  jmp     loc_1800039D5
0x180003aa1  mov     r15, [rsp+2A0h+hObject]
0x180003aa6  test    r15, r15
0x180003aa9  jz      short loc_180003AB8
0x180003aab  mov     eax, [r15]
0x180003aae  inc     eax
0x180003ab0  mov     [r15], eax
0x180003ab3  jmp     loc_180003BF0
0x180003ab8  mov     rdx, r14; dwBytes
0x180003abb  mov     ecx, 8; dwFlags
0x180003ac0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003ac5  mov     r13, rax
0x180003ac8  test    rax, rax
0x180003acb  jnz     short loc_180003AE9
0x180003acd  mov     rcx, [rbp+1A8h]; this
0x180003ad4  mov     r14d, 8007000Eh
0x180003ada  mov     r9d, r14d; char *
0x180003add  mov     edx, 14Bh; void *
0x180003ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ae7  jmp     short loc_180003B67
0x180003ae9  xorps   xmm0, xmm0
0x180003aec  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180003af1  mov     r8, r13; void *
0x180003af4  lea     rcx, [rsp+2A0h+hObject]; this
0x180003af9  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x180003aff  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003b04  mov     r14d, eax
0x180003b07  test    eax, eax
0x180003b09  jns     loc_180003BA7
0x180003b0f  mov     rcx, [rbp+1A8h]; this
0x180003b16  mov     r9d, eax; char *
0x180003b19  mov     edx, 14Eh; void *
0x180003b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b23  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180003b28  test    rcx, rcx
0x180003b2b  jz      short loc_180003B3B
0x180003b2d  call    cs:__imp_CloseHandle
0x180003b33  test    eax, eax
0x180003b35  jz      loc_180003CD6
0x180003b3b  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180003b40  test    rcx, rcx
0x180003b43  jz      short loc_180003B53
0x180003b45  call    cs:__imp_CloseHandle
0x180003b4b  test    eax, eax
0x180003b4d  jz      loc_180003CE8
0x180003b53  call    cs:__imp_GetProcessHeap
0x180003b59  mov     r8, r13; lpMem
0x180003b5c  xor     edx, edx; dwFlags
0x180003b5e  mov     rcx, rax; hHeap
0x180003b61  call    cs:__imp_HeapFree
0x180003b67  mov     rcx, [rbp+1A8h]; this
0x180003b6e  mov     r9d, r14d; char *
0x180003b71  mov     edx, 137h; void *
0x180003b76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b7b  test    rdi, rdi
0x180003b7e  jz      short loc_180003B91
0x180003b80  mov     rcx, rdi; hMutex
0x180003b83  call    cs:__imp_ReleaseMutex
0x180003b89  test    eax, eax
0x180003b8b  jz      loc_180003CFA
0x180003b91  mov     rcx, rbx; hObject
0x180003b94  call    cs:__imp_CloseHandle
0x180003b9a  test    eax, eax
0x180003b9c  jz      loc_180003C93
0x180003ba2  jmp     loc_1800039C4
0x180003ba7  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x180003bac  xor     edx, edx; Val
0x180003bae  mov     dword ptr [r13+0], 1
0x180003bb6  lea     rcx, [r13+22h]; void *
0x180003bba  mov     [r13+8], rbx
0x180003bbe  movdqu  xmmword ptr [r13+10h], xmm0
0x180003bc4  lea     r8d, [rdx+56h]; Size
0x180003bc8  call    memset_0
0x180003bcd  xor     edx, edx; Val
0x180003bcf  mov     word ptr [r13+20h], 58h ; 'X'
0x180003bd6  lea     rcx, [r13+28h]; void *
0x180003bda  mov     dword ptr [r13+24h], 1
0x180003be2  lea     r8d, [rdx+50h]; Size
0x180003be6  call    memset_0
0x180003beb  xor     ebx, ebx
0x180003bed  mov     r15, r13
0x180003bf0  test    rdi, rdi
0x180003bf3  jz      short loc_180003C02
0x180003bf5  mov     rcx, rdi; hMutex
0x180003bf8  call    cs:__imp_ReleaseMutex
0x180003bfe  test    eax, eax
0x180003c00  jz      short loc_180003C6F
0x180003c02  test    rbx, rbx
0x180003c05  jz      loc_1800039C9
0x180003c0b  mov     rcx, rbx; hObject
0x180003c0e  call    cs:__imp_CloseHandle
0x180003c14  test    eax, eax
0x180003c16  jz      loc_180003CA5
0x180003c1c  jmp     loc_1800039C9
0x180003c21  cmp     [rax], r8d
0x180003c24  jz      short loc_180003C31
0x180003c26  mov     rax, [rax+8]
0x180003c2a  test    rax, rax
0x180003c2d  jnz     short loc_180003C21
0x180003c2f  jmp     short loc_180003C49
0x180003c31  lea     rsi, [rax+10h]
0x180003c35  test    rsi, rsi
0x180003c38  jz      short loc_180003C49
0x180003c3a  cmp     qword ptr [rsi+8], 0
0x180003c3f  jnz     short loc_180003C49
0x180003c41  lea     rax, [rbx+4]
0x180003c45  mov     [rsi+8], rax
0x180003c49  mov     rax, rsi
0x180003c4c  mov     rcx, [rbp+1A0h+var_50]
0x180003c53  xor     rcx, rsp; StackCookie
0x180003c56  call    __security_check_cookie
0x180003c5b  add     rsp, 268h
0x180003c62  pop     r15
0x180003c64  pop     r14
0x180003c66  pop     r13
0x180003c68  pop     r12
0x180003c6a  pop     rdi
0x180003c6b  pop     rsi
0x180003c6c  pop     rbx
0x180003c6d  pop     rbp
0x180003c6e  retn
0x180003c6f  mov     rcx, [rbp+1A8h]; this
0x180003c76  mov     edx, 0A15h; void *
0x180003c7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c81  mov     rcx, [rbp+1A8h]; this
0x180003c88  mov     edx, 0A0Bh; void *
0x180003c8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c93  mov     rcx, [rbp+1A8h]; this
0x180003c9a  mov     edx, 0A0Bh; void *
0x180003c9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ca5  mov     rcx, [rbp+1A8h]; this
0x180003cac  mov     edx, 0A0Bh; void *
0x180003cb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cb7  mov     rcx, [rbp+1A8h]; this
0x180003cbe  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003cc4  mov     rcx, [rbp+1A8h]; this
0x180003ccb  mov     edx, 0A15h; void *
0x180003cd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cd6  mov     rcx, [rbp+1A8h]; this
0x180003cdd  mov     edx, 0A0Bh; void *
0x180003ce2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ce8  mov     rcx, [rbp+1A8h]; this
0x180003cef  mov     edx, 0A0Bh; void *
0x180003cf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cfa  mov     rcx, [rbp+1A8h]; this
0x180003d01  mov     edx, 0A15h; void *
0x180003d06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
