# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a1f8`
- end: `0x18000a596`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000bf00`

## callees

- `0x1800028f0`
- `0x1800033e8`
- `0x18000a1f8`
- `0x18000a96c`
- `0x18000ae88`
- `0x18000bc98`
- `0x18000cac0`
- `0x18000e354`
- `0x18000ee48`
- `0x18000f2cc`
- `0x18000fb7c`
- `0x18000fb8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a270`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a270`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a312`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a43b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a4ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a312`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a43b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a4ab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a291`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a291`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a40b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a40b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a419`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a323`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a44c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a323`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a44c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4c1`

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
0x18000a1f8  mov     [rsp-8+arg_10], rbx
0x18000a1fd  push    rbp
0x18000a1fe  push    rsi
0x18000a1ff  push    rdi
0x18000a200  push    r14
0x18000a202  push    r15
0x18000a204  lea     rbp, [rsp-160h]
0x18000a20c  sub     rsp, 260h
0x18000a213  mov     rax, cs:__security_cookie
0x18000a21a  xor     rax, rsp
0x18000a21d  mov     [rbp+180h+var_30], rax
0x18000a224  mov     r15, rdx
0x18000a227  mov     qword ptr [rdx], 0
0x18000a22e  mov     rbx, rcx
0x18000a231  call    cs:__imp_GetCurrentProcessId
0x18000a237  mov     r14d, 78h ; 'x'
0x18000a23d  mov     [rsp+280h+var_258], rbx
0x18000a242  mov     r9d, eax
0x18000a245  mov     [rsp+280h+var_260], r14d; int
0x18000a24a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a251  mov     edx, 104h; unsigned __int64
0x18000a256  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a25b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a260  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a266  lea     rdx, [rsp+280h+Name]; lpName
0x18000a26b  xor     r8d, r8d; dwFlags
0x18000a26e  xor     ecx, ecx; lpMutexAttributes
0x18000a270  call    cs:__imp_CreateMutexExW
0x18000a276  mov     rbx, rax
0x18000a279  test    rax, rax
0x18000a27c  jnz     short loc_18000A288
0x18000a27e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a283  jmp     loc_18000A4CD
0x18000a288  xor     r8d, r8d; bAlertable
0x18000a28b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a28e  mov     rcx, rbx; hHandle
0x18000a291  call    cs:__imp_WaitForSingleObjectEx
0x18000a297  cmp     eax, 102h
0x18000a29c  jz      short loc_18000A2AE
0x18000a29e  test    eax, 0FFFFFF7Fh
0x18000a2a3  jnz     loc_18000A505
0x18000a2a9  mov     rdi, rbx
0x18000a2ac  jmp     short loc_18000A2B0
0x18000a2ae  xor     edi, edi
0x18000a2b0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000a2b5  mov     [rsp+280h+hObject], 0
0x18000a2be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a2c3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a2c8  mov     esi, eax
0x18000a2ca  test    eax, eax
0x18000a2cc  jns     short loc_18000A338
0x18000a2ce  mov     rcx, [rbp+188h]; this
0x18000a2d5  mov     r9d, eax; char *
0x18000a2d8  mov     edx, 66h ; 'f'; void *
0x18000a2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2e2  mov     rcx, [rbp+188h]; this
0x18000a2e9  mov     r9d, esi; char *
0x18000a2ec  mov     edx, 6Fh ; 'o'; void *
0x18000a2f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2f6  mov     rcx, [rbp+188h]; this
0x18000a2fd  mov     r9d, esi; char *
0x18000a300  mov     edx, 12Eh; void *
0x18000a305  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a30a  test    rdi, rdi
0x18000a30d  jz      short loc_18000A320
0x18000a30f  mov     rcx, rdi; hMutex
0x18000a312  call    cs:__imp_ReleaseMutex
0x18000a318  test    eax, eax
0x18000a31a  jz      loc_18000A512
0x18000a320  mov     rcx, rbx; hObject
0x18000a323  call    cs:__imp_CloseHandle
0x18000a329  test    eax, eax
0x18000a32b  jz      loc_18000A524
0x18000a331  mov     eax, esi
0x18000a333  jmp     loc_18000A4CD
0x18000a338  mov     rax, [rsp+280h+hObject]
0x18000a33d  lea     rcx, ds:0[rax*4]
0x18000a345  test    rcx, rcx
0x18000a348  jz      short loc_18000A358
0x18000a34a  mov     [r15], rcx
0x18000a34d  mov     eax, [rcx]
0x18000a34f  inc     eax
0x18000a351  mov     [rcx], eax
0x18000a353  jmp     loc_18000A4A3
0x18000a358  mov     rdx, r14; dwBytes
0x18000a35b  mov     qword ptr [r15], 0
0x18000a362  mov     ecx, 8; dwFlags
0x18000a367  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a36c  mov     rsi, rax
0x18000a36f  test    rax, rax
0x18000a372  jnz     short loc_18000A393
0x18000a374  mov     rcx, [rbp+188h]; this
0x18000a37b  mov     r14d, 8007000Eh
0x18000a381  mov     r9d, r14d; char *
0x18000a384  mov     edx, 14Bh; void *
0x18000a389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a38e  jmp     loc_18000A41F
0x18000a393  xorps   xmm0, xmm0
0x18000a396  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000a39c  test    sil, 3
0x18000a3a0  jnz     loc_18000A536
0x18000a3a6  mov     r9, rsi
0x18000a3a9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a3ae  shr     r9, 2; unsigned __int64
0x18000a3b2  lea     rcx, [rsp+280h+hObject]; this
0x18000a3b7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000a3bc  mov     r14d, eax
0x18000a3bf  test    eax, eax
0x18000a3c1  jns     loc_18000A45F
0x18000a3c7  mov     rcx, [rbp+188h]; this
0x18000a3ce  mov     r9d, eax; char *
0x18000a3d1  mov     edx, 14Eh; void *
0x18000a3d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3db  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000a3e0  test    rcx, rcx
0x18000a3e3  jz      short loc_18000A3F3
0x18000a3e5  call    cs:__imp_CloseHandle
0x18000a3eb  test    eax, eax
0x18000a3ed  jz      loc_18000A53C
0x18000a3f3  mov     rcx, [rsp+280h+hObject]; hObject
0x18000a3f8  test    rcx, rcx
0x18000a3fb  jz      short loc_18000A40B
0x18000a3fd  call    cs:__imp_CloseHandle
0x18000a403  test    eax, eax
0x18000a405  jz      loc_18000A54E
0x18000a40b  call    cs:__imp_GetProcessHeap
0x18000a411  mov     r8, rsi; lpMem
0x18000a414  xor     edx, edx; dwFlags
0x18000a416  mov     rcx, rax; hHeap
0x18000a419  call    cs:__imp_HeapFree
0x18000a41f  mov     rcx, [rbp+188h]; this
0x18000a426  mov     r9d, r14d; char *
0x18000a429  mov     edx, 137h; void *
0x18000a42e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a433  test    rdi, rdi
0x18000a436  jz      short loc_18000A449
0x18000a438  mov     rcx, rdi; hMutex
0x18000a43b  call    cs:__imp_ReleaseMutex
0x18000a441  test    eax, eax
0x18000a443  jz      loc_18000A560
0x18000a449  mov     rcx, rbx; hObject
0x18000a44c  call    cs:__imp_CloseHandle
0x18000a452  test    eax, eax
0x18000a454  jz      loc_18000A572
0x18000a45a  mov     eax, r14d
0x18000a45d  jmp     short loc_18000A4CD
0x18000a45f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000a464  xor     edx, edx; Val
0x18000a466  mov     dword ptr [rsi], 1
0x18000a46c  lea     rcx, [rsi+22h]; void *
0x18000a470  mov     [rsi+8], rbx
0x18000a474  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000a479  lea     r8d, [rdx+56h]; Size
0x18000a47d  call    memset_0
0x18000a482  xor     edx, edx; Val
0x18000a484  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000a48a  lea     rcx, [rsi+28h]; void *
0x18000a48e  mov     dword ptr [rsi+24h], 1
0x18000a495  lea     r8d, [rdx+50h]; Size
0x18000a499  call    memset_0
0x18000a49e  xor     ebx, ebx
0x18000a4a0  mov     [r15], rsi
0x18000a4a3  test    rdi, rdi
0x18000a4a6  jz      short loc_18000A4B9
0x18000a4a8  mov     rcx, rdi; hMutex
0x18000a4ab  call    cs:__imp_ReleaseMutex
0x18000a4b1  test    eax, eax
0x18000a4b3  jz      loc_18000A584
0x18000a4b9  test    rbx, rbx
0x18000a4bc  jz      short loc_18000A4CB
0x18000a4be  mov     rcx, rbx; hObject
0x18000a4c1  call    cs:__imp_CloseHandle
0x18000a4c7  test    eax, eax
0x18000a4c9  jz      short loc_18000A4F3
0x18000a4cb  xor     eax, eax
0x18000a4cd  mov     rcx, [rbp+180h+var_30]
0x18000a4d4  xor     rcx, rsp; StackCookie
0x18000a4d7  call    __security_check_cookie
0x18000a4dc  mov     rbx, [rsp+280h+arg_10]
0x18000a4e4  add     rsp, 260h
0x18000a4eb  pop     r15
0x18000a4ed  pop     r14
0x18000a4ef  pop     rdi
0x18000a4f0  pop     rsi
0x18000a4f1  pop     rbp
0x18000a4f2  retn
0x18000a4f3  mov     rcx, [rbp+188h]; this
0x18000a4fa  mov     edx, 0A0Bh; void *
0x18000a4ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a505  mov     rcx, [rbp+188h]; this
0x18000a50c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a512  mov     rcx, [rbp+188h]; this
0x18000a519  mov     edx, 0A15h; void *
0x18000a51e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a524  mov     rcx, [rbp+188h]; this
0x18000a52b  mov     edx, 0A0Bh; void *
0x18000a530  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a536  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a53c  mov     rcx, [rbp+188h]; this
0x18000a543  mov     edx, 0A0Bh; void *
0x18000a548  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a54e  mov     rcx, [rbp+188h]; this
0x18000a555  mov     edx, 0A0Bh; void *
0x18000a55a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a560  mov     rcx, [rbp+188h]; this
0x18000a567  mov     edx, 0A15h; void *
0x18000a56c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a572  mov     rcx, [rbp+188h]; this
0x18000a579  mov     edx, 0A0Bh; void *
0x18000a57e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a584  mov     rcx, [rbp+188h]; this
0x18000a58b  mov     edx, 0A15h; void *
0x18000a590  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
