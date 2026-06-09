# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a3b8`
- end: `0x18000a7a9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000aa8c`

## callees

- `0x180005de8`
- `0x180009b78`
- `0x18000a3b8`
- `0x18000a7b0`
- `0x18000ace0`
- `0x18000b320`
- `0x18000b85c`
- `0x18000cfe8`
- `0x18000d5a4`
- `0x18000e238`
- `0x18000e248`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a4e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a622`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a6be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a4e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a622`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a6be`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a68b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a68b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a450`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a450`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a42f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a42f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  bool v23; // r8
  _DWORD *v24; // r14
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
      304);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x18000a3b8  mov     [rsp-8+arg_10], rbx
0x18000a3bd  push    rbp
0x18000a3be  push    rsi
0x18000a3bf  push    rdi
0x18000a3c0  push    r14
0x18000a3c2  push    r15
0x18000a3c4  lea     rbp, [rsp-160h]
0x18000a3cc  sub     rsp, 260h
0x18000a3d3  mov     rax, cs:__security_cookie
0x18000a3da  xor     rax, rsp
0x18000a3dd  mov     [rbp+180h+var_30], rax
0x18000a3e4  mov     r15, rdx
0x18000a3e7  mov     qword ptr [rdx], 0
0x18000a3ee  mov     rbx, rcx
0x18000a3f1  call    cs:__imp_GetCurrentProcessId
0x18000a3f7  mov     r14d, 130h
0x18000a3fd  mov     [rsp+280h+var_258], rbx
0x18000a402  mov     r9d, eax
0x18000a405  mov     [rsp+280h+var_260], r14d; int
0x18000a40a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a411  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a416  lea     edx, [r14-2Ch]; unsigned __int64
0x18000a41a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a41f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a425  lea     rdx, [rsp+280h+Name]; lpName
0x18000a42a  xor     r8d, r8d; dwFlags
0x18000a42d  xor     ecx, ecx; lpMutexAttributes
0x18000a42f  call    cs:__imp_CreateMutexExW
0x18000a435  mov     rbx, rax
0x18000a438  test    rax, rax
0x18000a43b  jnz     short loc_18000A447
0x18000a43d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a442  jmp     loc_18000A6E0
0x18000a447  xor     r8d, r8d; bAlertable
0x18000a44a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a44d  mov     rcx, rbx; hHandle
0x18000a450  call    cs:__imp_WaitForSingleObjectEx
0x18000a456  cmp     eax, 102h
0x18000a45b  jz      short loc_18000A46D
0x18000a45d  test    eax, 0FFFFFF7Fh
0x18000a462  jnz     loc_18000A72A
0x18000a468  mov     rdi, rbx
0x18000a46b  jmp     short loc_18000A46F
0x18000a46d  xor     edi, edi
0x18000a46f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000a474  mov     [rsp+280h+hObject], 0
0x18000a47d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a482  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a487  mov     esi, eax
0x18000a489  test    eax, eax
0x18000a48b  jns     short loc_18000A50C
0x18000a48d  mov     rcx, [rbp+188h]; this
0x18000a494  lea     r8, aWil; "wil"
0x18000a49b  mov     r9d, eax; char *
0x18000a49e  mov     edx, 66h ; 'f'; void *
0x18000a4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4a8  mov     rcx, [rbp+188h]; this
0x18000a4af  lea     r8, aWil; "wil"
0x18000a4b6  mov     r9d, esi; char *
0x18000a4b9  mov     edx, 6Fh ; 'o'; void *
0x18000a4be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4c3  mov     rcx, [rbp+188h]; this
0x18000a4ca  lea     r8, aWil; "wil"
0x18000a4d1  mov     r9d, esi; char *
0x18000a4d4  mov     edx, 12Eh; void *
0x18000a4d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4de  test    rdi, rdi
0x18000a4e1  jz      short loc_18000A4F4
0x18000a4e3  mov     rcx, rdi; hMutex
0x18000a4e6  call    cs:__imp_ReleaseMutex
0x18000a4ec  test    eax, eax
0x18000a4ee  jz      loc_18000A737
0x18000a4f4  mov     rcx, rbx; hObject
0x18000a4f7  call    cs:__imp_CloseHandle
0x18000a4fd  test    eax, eax
0x18000a4ff  jz      loc_18000A749
0x18000a505  mov     eax, esi
0x18000a507  jmp     loc_18000A6E0
0x18000a50c  mov     rax, [rsp+280h+hObject]
0x18000a511  lea     rcx, ds:0[rax*4]
0x18000a519  test    rcx, rcx
0x18000a51c  jz      short loc_18000A52C
0x18000a51e  mov     [r15], rcx
0x18000a521  mov     eax, [rcx]
0x18000a523  inc     eax
0x18000a525  mov     [rcx], eax
0x18000a527  jmp     loc_18000A6B6
0x18000a52c  mov     rdx, r14; dwBytes
0x18000a52f  mov     qword ptr [r15], 0
0x18000a536  mov     ecx, 8; dwFlags
0x18000a53b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a540  mov     r14, rax
0x18000a543  test    rax, rax
0x18000a546  jnz     short loc_18000A56D
0x18000a548  mov     rcx, [rbp+188h]; this
0x18000a54f  lea     r8, aWil; "wil"
0x18000a556  mov     esi, 8007000Eh
0x18000a55b  mov     edx, 14Bh; void *
0x18000a560  mov     r9d, esi; char *
0x18000a563  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a568  jmp     loc_18000A5FF
0x18000a56d  xorps   xmm0, xmm0
0x18000a570  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000a576  test    r14b, 3
0x18000a57a  jnz     loc_18000A75B
0x18000a580  mov     r9, r14
0x18000a583  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a588  shr     r9, 2; unsigned __int64
0x18000a58c  lea     rcx, [rsp+280h+hObject]; this
0x18000a591  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000a596  mov     esi, eax
0x18000a598  test    eax, eax
0x18000a59a  jns     loc_18000A646
0x18000a5a0  mov     rcx, [rbp+188h]; this
0x18000a5a7  lea     r8, aWil; "wil"
0x18000a5ae  mov     r9d, eax; char *
0x18000a5b1  mov     edx, 14Eh; void *
0x18000a5b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5bb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000a5c0  test    rcx, rcx
0x18000a5c3  jz      short loc_18000A5D3
0x18000a5c5  call    cs:__imp_CloseHandle
0x18000a5cb  test    eax, eax
0x18000a5cd  jz      loc_18000A761
0x18000a5d3  mov     rcx, [rsp+280h+hObject]; hObject
0x18000a5d8  test    rcx, rcx
0x18000a5db  jz      short loc_18000A5EB
0x18000a5dd  call    cs:__imp_CloseHandle
0x18000a5e3  test    eax, eax
0x18000a5e5  jz      loc_18000A773
0x18000a5eb  call    cs:__imp_GetProcessHeap
0x18000a5f1  mov     r8, r14; lpMem
0x18000a5f4  xor     edx, edx; dwFlags
0x18000a5f6  mov     rcx, rax; hHeap
0x18000a5f9  call    cs:__imp_HeapFree
0x18000a5ff  mov     rcx, [rbp+188h]; this
0x18000a606  lea     r8, aWil; "wil"
0x18000a60d  mov     r9d, esi; char *
0x18000a610  mov     edx, 137h; void *
0x18000a615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a61a  test    rdi, rdi
0x18000a61d  jz      short loc_18000A630
0x18000a61f  mov     rcx, rdi; hMutex
0x18000a622  call    cs:__imp_ReleaseMutex
0x18000a628  test    eax, eax
0x18000a62a  jz      loc_18000A785
0x18000a630  mov     rcx, rbx; hObject
0x18000a633  call    cs:__imp_CloseHandle
0x18000a639  test    eax, eax
0x18000a63b  jz      loc_18000A718
0x18000a641  jmp     loc_18000A505
0x18000a646  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000a64b  lea     rcx, [r14+28h]; void *
0x18000a64f  mov     dword ptr [r14], 1
0x18000a656  xor     edx, edx; Val
0x18000a658  mov     [r14+8], rbx
0x18000a65c  mov     r8d, 108h; Size
0x18000a662  movdqu  xmmword ptr [r14+10h], xmm0
0x18000a668  call    memset_0
0x18000a66d  xor     eax, eax
0x18000a66f  lea     rcx, [r14+28h]; this
0x18000a673  mov     [r14+20h], rax
0x18000a677  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a67c  lea     rbx, [r14+0E8h]
0x18000a683  xor     r8d, r8d; Flags
0x18000a686  mov     rcx, rbx; lpCriticalSection
0x18000a689  xor     edx, edx; dwSpinCount
0x18000a68b  call    cs:__imp_InitializeCriticalSectionEx
0x18000a691  mov     qword ptr [rbx+28h], 0
0x18000a699  mov     qword ptr [rbx+30h], 0
0x18000a6a1  mov     qword ptr [rbx+38h], 0
0x18000a6a9  mov     qword ptr [rbx+40h], 0
0x18000a6b1  xor     ebx, ebx
0x18000a6b3  mov     [r15], r14
0x18000a6b6  test    rdi, rdi
0x18000a6b9  jz      short loc_18000A6CC
0x18000a6bb  mov     rcx, rdi; hMutex
0x18000a6be  call    cs:__imp_ReleaseMutex
0x18000a6c4  test    eax, eax
0x18000a6c6  jz      loc_18000A797
0x18000a6cc  test    rbx, rbx
0x18000a6cf  jz      short loc_18000A6DE
0x18000a6d1  mov     rcx, rbx; hObject
0x18000a6d4  call    cs:__imp_CloseHandle
0x18000a6da  test    eax, eax
0x18000a6dc  jz      short loc_18000A706
0x18000a6de  xor     eax, eax
0x18000a6e0  mov     rcx, [rbp+180h+var_30]
0x18000a6e7  xor     rcx, rsp; StackCookie
0x18000a6ea  call    __security_check_cookie
0x18000a6ef  mov     rbx, [rsp+280h+arg_10]
0x18000a6f7  add     rsp, 260h
0x18000a6fe  pop     r15
0x18000a700  pop     r14
0x18000a702  pop     rdi
0x18000a703  pop     rsi
0x18000a704  pop     rbp
0x18000a705  retn
0x18000a706  mov     rcx, [rbp+188h]; this
0x18000a70d  mov     edx, 0A0Bh; void *
0x18000a712  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a718  mov     rcx, [rbp+188h]; this
0x18000a71f  mov     edx, 0A0Bh; void *
0x18000a724  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a72a  mov     rcx, [rbp+188h]; this
0x18000a731  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a737  mov     rcx, [rbp+188h]; this
0x18000a73e  mov     edx, 0A15h; void *
0x18000a743  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a749  mov     rcx, [rbp+188h]; this
0x18000a750  mov     edx, 0A0Bh; void *
0x18000a755  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a75b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a761  mov     rcx, [rbp+188h]; this
0x18000a768  mov     edx, 0A0Bh; void *
0x18000a76d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a773  mov     rcx, [rbp+188h]; this
0x18000a77a  mov     edx, 0A0Bh; void *
0x18000a77f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a785  mov     rcx, [rbp+188h]; this
0x18000a78c  mov     edx, 0A15h; void *
0x18000a791  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a797  mov     rcx, [rbp+188h]; this
0x18000a79e  mov     edx, 0A15h; void *
0x18000a7a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
