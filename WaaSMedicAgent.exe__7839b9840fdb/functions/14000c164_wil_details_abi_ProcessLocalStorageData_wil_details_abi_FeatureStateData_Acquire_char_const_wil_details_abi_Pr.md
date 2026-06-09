# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000c164`
- end: `0x14000c555`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000c55c`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x140004cc8`
- `0x140004fb4`
- `0x140005640`
- `0x1400061e4`
- `0x14000644c`
- `0x140006e60`
- `0x140006f1c`
- `0x1400073b0`
- `0x1400073c0`
- `0x14000baa0`
- `0x14000c164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c1fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c1fc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000c1db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000c1db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000c437`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000c437`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c292`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c3ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c46a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c292`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c3ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c46a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c3a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c3a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c397`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000c19d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000c19d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c3df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c3df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c480`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
0x14000c164  mov     [rsp-8+arg_10], rbx
0x14000c169  push    rbp
0x14000c16a  push    rsi
0x14000c16b  push    rdi
0x14000c16c  push    r14
0x14000c16e  push    r15
0x14000c170  lea     rbp, [rsp-160h]
0x14000c178  sub     rsp, 260h
0x14000c17f  mov     rax, cs:__security_cookie
0x14000c186  xor     rax, rsp
0x14000c189  mov     [rbp+180h+var_30], rax
0x14000c190  mov     r15, rdx
0x14000c193  mov     qword ptr [rdx], 0
0x14000c19a  mov     rbx, rcx
0x14000c19d  call    cs:__imp_GetCurrentProcessId
0x14000c1a3  mov     r14d, 130h
0x14000c1a9  mov     [rsp+280h+var_258], rbx
0x14000c1ae  mov     r9d, eax
0x14000c1b1  mov     [rsp+280h+var_260], r14d; int
0x14000c1b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000c1bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c1c2  lea     edx, [r14-2Ch]; unsigned __int64
0x14000c1c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c1cb  mov     r9d, 1F0001h; dwDesiredAccess
0x14000c1d1  lea     rdx, [rsp+280h+Name]; lpName
0x14000c1d6  xor     r8d, r8d; dwFlags
0x14000c1d9  xor     ecx, ecx; lpMutexAttributes
0x14000c1db  call    cs:__imp_CreateMutexExW
0x14000c1e1  mov     rbx, rax
0x14000c1e4  test    rax, rax
0x14000c1e7  jnz     short loc_14000C1F3
0x14000c1e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000c1ee  jmp     loc_14000C48C
0x14000c1f3  xor     r8d, r8d; bAlertable
0x14000c1f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000c1f9  mov     rcx, rbx; hHandle
0x14000c1fc  call    cs:__imp_WaitForSingleObjectEx
0x14000c202  cmp     eax, 102h
0x14000c207  jz      short loc_14000C219
0x14000c209  test    eax, 0FFFFFF7Fh
0x14000c20e  jnz     loc_14000C4D6
0x14000c214  mov     rdi, rbx
0x14000c217  jmp     short loc_14000C21B
0x14000c219  xor     edi, edi
0x14000c21b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000c220  mov     [rsp+280h+hObject], 0
0x14000c229  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c22e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000c233  mov     esi, eax
0x14000c235  test    eax, eax
0x14000c237  jns     short loc_14000C2B8
0x14000c239  mov     rcx, [rbp+188h]; this
0x14000c240  lea     r8, aWil; "wil"
0x14000c247  mov     r9d, eax; char *
0x14000c24a  mov     edx, 66h ; 'f'; void *
0x14000c24f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c254  mov     rcx, [rbp+188h]; this
0x14000c25b  lea     r8, aWil; "wil"
0x14000c262  mov     r9d, esi; char *
0x14000c265  mov     edx, 6Fh ; 'o'; void *
0x14000c26a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c26f  mov     rcx, [rbp+188h]; this
0x14000c276  lea     r8, aWil; "wil"
0x14000c27d  mov     r9d, esi; char *
0x14000c280  mov     edx, 12Eh; void *
0x14000c285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c28a  test    rdi, rdi
0x14000c28d  jz      short loc_14000C2A0
0x14000c28f  mov     rcx, rdi; hMutex
0x14000c292  call    cs:__imp_ReleaseMutex
0x14000c298  test    eax, eax
0x14000c29a  jz      loc_14000C4E3
0x14000c2a0  mov     rcx, rbx; hObject
0x14000c2a3  call    cs:__imp_CloseHandle
0x14000c2a9  test    eax, eax
0x14000c2ab  jz      loc_14000C4F5
0x14000c2b1  mov     eax, esi
0x14000c2b3  jmp     loc_14000C48C
0x14000c2b8  mov     rax, [rsp+280h+hObject]
0x14000c2bd  lea     rcx, ds:0[rax*4]
0x14000c2c5  test    rcx, rcx
0x14000c2c8  jz      short loc_14000C2D8
0x14000c2ca  mov     [r15], rcx
0x14000c2cd  mov     eax, [rcx]
0x14000c2cf  inc     eax
0x14000c2d1  mov     [rcx], eax
0x14000c2d3  jmp     loc_14000C462
0x14000c2d8  mov     rdx, r14; dwBytes
0x14000c2db  mov     qword ptr [r15], 0
0x14000c2e2  mov     ecx, 8; dwFlags
0x14000c2e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c2ec  mov     r14, rax
0x14000c2ef  test    rax, rax
0x14000c2f2  jnz     short loc_14000C319
0x14000c2f4  mov     rcx, [rbp+188h]; this
0x14000c2fb  lea     r8, aWil; "wil"
0x14000c302  mov     esi, 8007000Eh
0x14000c307  mov     edx, 14Bh; void *
0x14000c30c  mov     r9d, esi; char *
0x14000c30f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c314  jmp     loc_14000C3AB
0x14000c319  xorps   xmm0, xmm0
0x14000c31c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000c322  test    r14b, 3
0x14000c326  jnz     loc_14000C507
0x14000c32c  mov     r9, r14
0x14000c32f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000c334  shr     r9, 2; unsigned __int64
0x14000c338  lea     rcx, [rsp+280h+hObject]; this
0x14000c33d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000c342  mov     esi, eax
0x14000c344  test    eax, eax
0x14000c346  jns     loc_14000C3F2
0x14000c34c  mov     rcx, [rbp+188h]; this
0x14000c353  lea     r8, aWil; "wil"
0x14000c35a  mov     r9d, eax; char *
0x14000c35d  mov     edx, 14Eh; void *
0x14000c362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c367  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000c36c  test    rcx, rcx
0x14000c36f  jz      short loc_14000C37F
0x14000c371  call    cs:__imp_CloseHandle
0x14000c377  test    eax, eax
0x14000c379  jz      loc_14000C50D
0x14000c37f  mov     rcx, [rsp+280h+hObject]; hObject
0x14000c384  test    rcx, rcx
0x14000c387  jz      short loc_14000C397
0x14000c389  call    cs:__imp_CloseHandle
0x14000c38f  test    eax, eax
0x14000c391  jz      loc_14000C51F
0x14000c397  call    cs:__imp_GetProcessHeap
0x14000c39d  mov     r8, r14; lpMem
0x14000c3a0  xor     edx, edx; dwFlags
0x14000c3a2  mov     rcx, rax; hHeap
0x14000c3a5  call    cs:__imp_HeapFree
0x14000c3ab  mov     rcx, [rbp+188h]; this
0x14000c3b2  lea     r8, aWil; "wil"
0x14000c3b9  mov     r9d, esi; char *
0x14000c3bc  mov     edx, 137h; void *
0x14000c3c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c3c6  test    rdi, rdi
0x14000c3c9  jz      short loc_14000C3DC
0x14000c3cb  mov     rcx, rdi; hMutex
0x14000c3ce  call    cs:__imp_ReleaseMutex
0x14000c3d4  test    eax, eax
0x14000c3d6  jz      loc_14000C531
0x14000c3dc  mov     rcx, rbx; hObject
0x14000c3df  call    cs:__imp_CloseHandle
0x14000c3e5  test    eax, eax
0x14000c3e7  jz      loc_14000C4C4
0x14000c3ed  jmp     loc_14000C2B1
0x14000c3f2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000c3f7  lea     rcx, [r14+28h]; void *
0x14000c3fb  mov     dword ptr [r14], 1
0x14000c402  xor     edx, edx; Val
0x14000c404  mov     [r14+8], rbx
0x14000c408  mov     r8d, 108h; Size
0x14000c40e  movdqu  xmmword ptr [r14+10h], xmm0
0x14000c414  call    memset_0
0x14000c419  xor     eax, eax
0x14000c41b  lea     rcx, [r14+28h]; this
0x14000c41f  mov     [r14+20h], rax
0x14000c423  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000c428  lea     rbx, [r14+0E8h]
0x14000c42f  xor     r8d, r8d; Flags
0x14000c432  mov     rcx, rbx; lpCriticalSection
0x14000c435  xor     edx, edx; dwSpinCount
0x14000c437  call    cs:__imp_InitializeCriticalSectionEx
0x14000c43d  mov     qword ptr [rbx+28h], 0
0x14000c445  mov     qword ptr [rbx+30h], 0
0x14000c44d  mov     qword ptr [rbx+38h], 0
0x14000c455  mov     qword ptr [rbx+40h], 0
0x14000c45d  xor     ebx, ebx
0x14000c45f  mov     [r15], r14
0x14000c462  test    rdi, rdi
0x14000c465  jz      short loc_14000C478
0x14000c467  mov     rcx, rdi; hMutex
0x14000c46a  call    cs:__imp_ReleaseMutex
0x14000c470  test    eax, eax
0x14000c472  jz      loc_14000C543
0x14000c478  test    rbx, rbx
0x14000c47b  jz      short loc_14000C48A
0x14000c47d  mov     rcx, rbx; hObject
0x14000c480  call    cs:__imp_CloseHandle
0x14000c486  test    eax, eax
0x14000c488  jz      short loc_14000C4B2
0x14000c48a  xor     eax, eax
0x14000c48c  mov     rcx, [rbp+180h+var_30]
0x14000c493  xor     rcx, rsp; StackCookie
0x14000c496  call    __security_check_cookie
0x14000c49b  mov     rbx, [rsp+280h+arg_10]
0x14000c4a3  add     rsp, 260h
0x14000c4aa  pop     r15
0x14000c4ac  pop     r14
0x14000c4ae  pop     rdi
0x14000c4af  pop     rsi
0x14000c4b0  pop     rbp
0x14000c4b1  retn
0x14000c4b2  mov     rcx, [rbp+188h]; this
0x14000c4b9  mov     edx, 0A0Bh; void *
0x14000c4be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c4c4  mov     rcx, [rbp+188h]; this
0x14000c4cb  mov     edx, 0A0Bh; void *
0x14000c4d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c4d6  mov     rcx, [rbp+188h]; this
0x14000c4dd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000c4e3  mov     rcx, [rbp+188h]; this
0x14000c4ea  mov     edx, 0A15h; void *
0x14000c4ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c4f5  mov     rcx, [rbp+188h]; this
0x14000c4fc  mov     edx, 0A0Bh; void *
0x14000c501  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c507  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000c50d  mov     rcx, [rbp+188h]; this
0x14000c514  mov     edx, 0A0Bh; void *
0x14000c519  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c51f  mov     rcx, [rbp+188h]; this
0x14000c526  mov     edx, 0A0Bh; void *
0x14000c52b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c531  mov     rcx, [rbp+188h]; this
0x14000c538  mov     edx, 0A15h; void *
0x14000c53d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c543  mov     rcx, [rbp+188h]; this
0x14000c54a  mov     edx, 0A15h; void *
0x14000c54f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
