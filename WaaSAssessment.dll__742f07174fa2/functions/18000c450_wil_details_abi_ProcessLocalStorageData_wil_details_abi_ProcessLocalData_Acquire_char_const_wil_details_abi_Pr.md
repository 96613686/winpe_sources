# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c450`
- end: `0x18000c818`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000e83c`

## callees

- `0x18000b2d8`
- `0x18000c450`
- `0x18000cfac`
- `0x18000d280`
- `0x18000dbd0`
- `0x18000edc0`
- `0x18000efec`
- `0x18000f36c`
- `0x18000f6e0`
- `0x18000f6f0`
- `0x18001972e`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c4c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c4c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c72d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c72d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c4e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c4e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c678`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c678`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c743`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = *(_OWORD *)hObject;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      *a2 = v24;
      v6 = 0;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v42);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x18000c450  mov     [rsp-8+arg_10], rbx
0x18000c455  push    rbp
0x18000c456  push    rsi
0x18000c457  push    rdi
0x18000c458  push    r14
0x18000c45a  push    r15
0x18000c45c  lea     rbp, [rsp-160h]
0x18000c464  sub     rsp, 260h
0x18000c46b  mov     rax, cs:__security_cookie
0x18000c472  xor     rax, rsp
0x18000c475  mov     [rbp+180h+var_30], rax
0x18000c47c  mov     r15, rdx
0x18000c47f  mov     rbx, rcx
0x18000c482  mov     qword ptr [rdx], 0
0x18000c489  call    cs:__imp_GetCurrentProcessId
0x18000c48f  mov     r9d, eax
0x18000c492  mov     [rsp+280h+var_258], rbx
0x18000c497  mov     r14d, 78h ; 'x'
0x18000c49d  mov     [rsp+280h+var_260], r14d; int
0x18000c4a2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c4a9  mov     edx, 104h; unsigned __int64
0x18000c4ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c4b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c4b8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c4be  xor     r8d, r8d; dwFlags
0x18000c4c1  lea     rdx, [rsp+280h+Name]; lpName
0x18000c4c6  xor     ecx, ecx; lpMutexAttributes
0x18000c4c8  call    cs:__imp_CreateMutexExW
0x18000c4ce  mov     rbx, rax
0x18000c4d1  test    rax, rax
0x18000c4d4  jnz     short loc_18000C4E0
0x18000c4d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c4db  jmp     loc_18000C74F
0x18000c4e0  xor     r8d, r8d; bAlertable
0x18000c4e3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c4e6  mov     rcx, rbx; hHandle
0x18000c4e9  call    cs:__imp_WaitForSingleObjectEx
0x18000c4ef  cmp     eax, 102h
0x18000c4f4  jz      short loc_18000C506
0x18000c4f6  test    eax, 0FFFFFF7Fh
0x18000c4fb  jnz     loc_18000C787
0x18000c501  mov     rdi, rbx
0x18000c504  jmp     short loc_18000C508
0x18000c506  xor     edi, edi
0x18000c508  mov     [rsp+280h+hObject], 0
0x18000c511  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000c516  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c51b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c520  mov     esi, eax
0x18000c522  test    eax, eax
0x18000c524  jns     short loc_18000C5A5
0x18000c526  mov     rcx, [rbp+188h]; this
0x18000c52d  mov     r9d, eax; char *
0x18000c530  lea     r8, aWil; "wil"
0x18000c537  mov     edx, 66h ; 'f'; void *
0x18000c53c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c541  mov     rcx, [rbp+188h]; this
0x18000c548  mov     r9d, esi; char *
0x18000c54b  lea     r8, aWil; "wil"
0x18000c552  mov     edx, 6Fh ; 'o'; void *
0x18000c557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c55c  mov     rcx, [rbp+188h]; this
0x18000c563  mov     r9d, esi; char *
0x18000c566  lea     r8, aWil; "wil"
0x18000c56d  mov     edx, 12Eh; void *
0x18000c572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c577  test    rdi, rdi
0x18000c57a  jz      short loc_18000C58D
0x18000c57c  mov     rcx, rdi; hMutex
0x18000c57f  call    cs:__imp_ReleaseMutex
0x18000c585  test    eax, eax
0x18000c587  jz      loc_18000C794
0x18000c58d  mov     rcx, rbx; hObject
0x18000c590  call    cs:__imp_CloseHandle
0x18000c596  test    eax, eax
0x18000c598  jz      loc_18000C7A6
0x18000c59e  mov     eax, esi
0x18000c5a0  jmp     loc_18000C74F
0x18000c5a5  mov     rax, [rsp+280h+hObject]
0x18000c5aa  lea     rcx, ds:0[rax*4]
0x18000c5b2  test    rcx, rcx
0x18000c5b5  jz      short loc_18000C5C5
0x18000c5b7  mov     [r15], rcx
0x18000c5ba  mov     eax, [rcx]
0x18000c5bc  inc     eax
0x18000c5be  mov     [rcx], eax
0x18000c5c0  jmp     loc_18000C725
0x18000c5c5  mov     qword ptr [r15], 0
0x18000c5cc  mov     rdx, r14; dwBytes
0x18000c5cf  mov     ecx, 8; dwFlags
0x18000c5d4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c5d9  mov     rsi, rax
0x18000c5dc  test    rax, rax
0x18000c5df  jnz     short loc_18000C607
0x18000c5e1  mov     rcx, [rbp+188h]; this
0x18000c5e8  mov     r14d, 8007000Eh
0x18000c5ee  mov     r9d, r14d; char *
0x18000c5f1  lea     r8, aWil; "wil"
0x18000c5f8  mov     edx, 14Bh; void *
0x18000c5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c602  jmp     loc_18000C69A
0x18000c607  xorps   xmm0, xmm0
0x18000c60a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000c610  test    sil, 3
0x18000c614  jnz     loc_18000C7B8
0x18000c61a  mov     r9, rsi
0x18000c61d  shr     r9, 2; unsigned __int64
0x18000c621  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000c626  lea     rcx, [rsp+280h+hObject]; this
0x18000c62b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000c630  mov     r14d, eax
0x18000c633  test    eax, eax
0x18000c635  jns     loc_18000C6E1
0x18000c63b  mov     rcx, [rbp+188h]; this
0x18000c642  mov     r9d, eax; char *
0x18000c645  lea     r8, aWil; "wil"
0x18000c64c  mov     edx, 14Eh; void *
0x18000c651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c656  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000c65b  test    rcx, rcx
0x18000c65e  jz      short loc_18000C66E
0x18000c660  call    cs:__imp_CloseHandle
0x18000c666  test    eax, eax
0x18000c668  jz      loc_18000C7BE
0x18000c66e  mov     rcx, [rsp+280h+hObject]; hObject
0x18000c673  test    rcx, rcx
0x18000c676  jz      short loc_18000C686
0x18000c678  call    cs:__imp_CloseHandle
0x18000c67e  test    eax, eax
0x18000c680  jz      loc_18000C7D0
0x18000c686  call    cs:__imp_GetProcessHeap
0x18000c68c  mov     rcx, rax; hHeap
0x18000c68f  mov     r8, rsi; lpMem
0x18000c692  xor     edx, edx; dwFlags
0x18000c694  call    cs:__imp_HeapFree
0x18000c69a  mov     rcx, [rbp+188h]; this
0x18000c6a1  mov     r9d, r14d; char *
0x18000c6a4  lea     r8, aWil; "wil"
0x18000c6ab  mov     edx, 137h; void *
0x18000c6b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6b5  test    rdi, rdi
0x18000c6b8  jz      short loc_18000C6CB
0x18000c6ba  mov     rcx, rdi; hMutex
0x18000c6bd  call    cs:__imp_ReleaseMutex
0x18000c6c3  test    eax, eax
0x18000c6c5  jz      loc_18000C7E2
0x18000c6cb  mov     rcx, rbx; hObject
0x18000c6ce  call    cs:__imp_CloseHandle
0x18000c6d4  test    eax, eax
0x18000c6d6  jz      loc_18000C7F4
0x18000c6dc  mov     eax, r14d
0x18000c6df  jmp     short loc_18000C74F
0x18000c6e1  mov     dword ptr [rsi], 1
0x18000c6e7  mov     [rsi+8], rbx
0x18000c6eb  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000c6f0  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000c6f5  lea     rcx, [rsi+22h]; void *
0x18000c6f9  xor     edx, edx; Val
0x18000c6fb  lea     r8d, [rdx+56h]; Size
0x18000c6ff  call    memset_0
0x18000c704  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000c70a  mov     dword ptr [rsi+24h], 1
0x18000c711  lea     rcx, [rsi+28h]; void *
0x18000c715  xor     edx, edx; Val
0x18000c717  lea     r8d, [rdx+50h]; Size
0x18000c71b  call    memset_0
0x18000c720  mov     [r15], rsi
0x18000c723  xor     ebx, ebx
0x18000c725  test    rdi, rdi
0x18000c728  jz      short loc_18000C73B
0x18000c72a  mov     rcx, rdi; hMutex
0x18000c72d  call    cs:__imp_ReleaseMutex
0x18000c733  test    eax, eax
0x18000c735  jz      loc_18000C806
0x18000c73b  test    rbx, rbx
0x18000c73e  jz      short loc_18000C74D
0x18000c740  mov     rcx, rbx; hObject
0x18000c743  call    cs:__imp_CloseHandle
0x18000c749  test    eax, eax
0x18000c74b  jz      short loc_18000C775
0x18000c74d  xor     eax, eax
0x18000c74f  mov     rcx, [rbp+180h+var_30]
0x18000c756  xor     rcx, rsp; StackCookie
0x18000c759  call    __security_check_cookie
0x18000c75e  mov     rbx, [rsp+280h+arg_10]
0x18000c766  add     rsp, 260h
0x18000c76d  pop     r15
0x18000c76f  pop     r14
0x18000c771  pop     rdi
0x18000c772  pop     rsi
0x18000c773  pop     rbp
0x18000c774  retn
0x18000c775  mov     rcx, [rbp+188h]; this
0x18000c77c  mov     edx, 0A0Bh; void *
0x18000c781  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c787  mov     rcx, [rbp+188h]; this
0x18000c78e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000c794  mov     rcx, [rbp+188h]; this
0x18000c79b  mov     edx, 0A15h; void *
0x18000c7a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c7a6  mov     rcx, [rbp+188h]; this
0x18000c7ad  mov     edx, 0A0Bh; void *
0x18000c7b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c7b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c7be  mov     rcx, [rbp+188h]; this
0x18000c7c5  mov     edx, 0A0Bh; void *
0x18000c7ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c7d0  mov     rcx, [rbp+188h]; this
0x18000c7d7  mov     edx, 0A0Bh; void *
0x18000c7dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c7e2  mov     rcx, [rbp+188h]; this
0x18000c7e9  mov     edx, 0A15h; void *
0x18000c7ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c7f4  mov     rcx, [rbp+188h]; this
0x18000c7fb  mov     edx, 0A0Bh; void *
0x18000c800  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c806  mov     rcx, [rbp+188h]; this
0x18000c80d  mov     edx, 0A15h; void *
0x18000c812  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
