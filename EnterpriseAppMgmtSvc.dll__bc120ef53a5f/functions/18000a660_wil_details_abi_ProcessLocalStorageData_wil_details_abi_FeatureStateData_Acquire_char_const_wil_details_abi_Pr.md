# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a660`
- end: `0x18000aa60`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000ac84`

## callees

- `0x180005ff4`
- `0x180009e74`
- `0x18000a448`
- `0x18000a660`
- `0x18000aa68`
- `0x18000aedc`
- `0x18000b5b8`
- `0x18000bc08`
- `0x18000d3dc`
- `0x18000daf4`
- `0x18000e7c8`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a87e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a87e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a892`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a699`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a9ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a9ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a7a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a8c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a992`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a7a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a8c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a992`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a94f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a94f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a704`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a704`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a6dd`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x18000a660  mov     [rsp-8+arg_10], rbx
0x18000a665  push    rbp
0x18000a666  push    rsi
0x18000a667  push    rdi
0x18000a668  push    r14
0x18000a66a  push    r15
0x18000a66c  lea     rbp, [rsp-160h]
0x18000a674  sub     rsp, 260h
0x18000a67b  mov     rax, cs:__security_cookie
0x18000a682  xor     rax, rsp
0x18000a685  mov     [rbp+180h+var_30], rax
0x18000a68c  mov     r15, rdx
0x18000a68f  mov     qword ptr [rdx], 0
0x18000a696  mov     rbx, rcx
0x18000a699  call    cs:__imp_GetCurrentProcessId
0x18000a6a0  nop     dword ptr [rax+rax+00h]
0x18000a6a5  mov     r14d, 130h
0x18000a6ab  mov     [rsp+280h+var_258], rbx
0x18000a6b0  mov     r9d, eax
0x18000a6b3  mov     [rsp+280h+var_260], r14d; int
0x18000a6b8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a6bf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a6c4  lea     edx, [r14-2Ch]; unsigned __int64
0x18000a6c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a6cd  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a6d3  lea     rdx, [rsp+280h+Name]; lpName
0x18000a6d8  xor     r8d, r8d; dwFlags
0x18000a6db  xor     ecx, ecx; lpMutexAttributes
0x18000a6dd  call    cs:__imp_CreateMutexExW
0x18000a6e4  nop     dword ptr [rax+rax+00h]
0x18000a6e9  mov     rbx, rax
0x18000a6ec  test    rax, rax
0x18000a6ef  jnz     short loc_18000A6FB
0x18000a6f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a6f6  jmp     loc_18000A9C0
0x18000a6fb  xor     r8d, r8d; bAlertable
0x18000a6fe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a701  mov     rcx, rbx; hHandle
0x18000a704  call    cs:__imp_WaitForSingleObjectEx
0x18000a70b  nop     dword ptr [rax+rax+00h]
0x18000a710  cmp     eax, 102h
0x18000a715  jz      short loc_18000A727
0x18000a717  test    eax, 0FFFFFF7Fh
0x18000a71c  jnz     loc_18000AA0B
0x18000a722  mov     rdi, rbx
0x18000a725  jmp     short loc_18000A729
0x18000a727  xor     edi, edi
0x18000a729  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000a72e  mov     [rsp+280h+var_250], 0
0x18000a737  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a73c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a741  mov     esi, eax
0x18000a743  test    eax, eax
0x18000a745  jns     loc_18000A7D6
0x18000a74b  mov     rcx, [rbp+188h]; this
0x18000a752  lea     r8, aWil; "wil"
0x18000a759  mov     r9d, eax; char *
0x18000a75c  mov     edx, 66h ; 'f'; void *
0x18000a761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a766  mov     rcx, [rbp+188h]; this
0x18000a76d  lea     r8, aWil; "wil"
0x18000a774  mov     r9d, esi; char *
0x18000a777  mov     edx, 6Fh ; 'o'; void *
0x18000a77c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a781  mov     rcx, [rbp+188h]; this
0x18000a788  lea     r8, aWil; "wil"
0x18000a78f  mov     r9d, esi; char *
0x18000a792  mov     edx, 12Eh; void *
0x18000a797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a79c  test    rdi, rdi
0x18000a79f  jz      short loc_18000A7B8
0x18000a7a1  mov     rcx, rdi; hMutex
0x18000a7a4  call    cs:__imp_ReleaseMutex
0x18000a7ab  nop     dword ptr [rax+rax+00h]
0x18000a7b0  test    eax, eax
0x18000a7b2  jz      loc_18000AA18
0x18000a7b8  mov     rcx, rbx; hObject
0x18000a7bb  call    cs:__imp_CloseHandle
0x18000a7c2  nop     dword ptr [rax+rax+00h]
0x18000a7c7  test    eax, eax
0x18000a7c9  jz      loc_18000AA2A
0x18000a7cf  mov     eax, esi
0x18000a7d1  jmp     loc_18000A9C0
0x18000a7d6  mov     rax, [rsp+280h+var_250]
0x18000a7db  lea     rcx, ds:0[rax*4]
0x18000a7e3  test    rcx, rcx
0x18000a7e6  jz      short loc_18000A7F6
0x18000a7e8  mov     [r15], rcx
0x18000a7eb  mov     eax, [rcx]
0x18000a7ed  inc     eax
0x18000a7ef  mov     [rcx], eax
0x18000a7f1  jmp     loc_18000A98A
0x18000a7f6  mov     rdx, r14; dwBytes
0x18000a7f9  mov     qword ptr [r15], 0
0x18000a800  mov     ecx, 8; dwFlags
0x18000a805  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a80a  mov     r14, rax
0x18000a80d  test    rax, rax
0x18000a810  jnz     short loc_18000A834
0x18000a812  mov     rcx, [rbp+188h]; this
0x18000a819  lea     r8, aWil; "wil"
0x18000a820  mov     esi, 8007000Eh
0x18000a825  mov     edx, 14Bh; void *
0x18000a82a  mov     r9d, esi; char *
0x18000a82d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a832  jmp     short loc_18000A89E
0x18000a834  xorps   xmm0, xmm0
0x18000a837  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a83c  mov     r8, r14; void *
0x18000a83f  lea     rcx, [rsp+280h+var_250]; this
0x18000a844  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000a84a  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000a84f  mov     esi, eax
0x18000a851  test    eax, eax
0x18000a853  jns     loc_18000A8F1
0x18000a859  mov     rcx, [rbp+188h]; this
0x18000a860  lea     r8, aWil; "wil"
0x18000a867  mov     r9d, eax; char *
0x18000a86a  mov     edx, 14Eh; void *
0x18000a86f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a874  lea     rcx, [rsp+280h+var_250]; this
0x18000a879  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a87e  call    cs:__imp_GetProcessHeap
0x18000a885  nop     dword ptr [rax+rax+00h]
0x18000a88a  mov     r8, r14; lpMem
0x18000a88d  xor     edx, edx; dwFlags
0x18000a88f  mov     rcx, rax; hHeap
0x18000a892  call    cs:__imp_HeapFree
0x18000a899  nop     dword ptr [rax+rax+00h]
0x18000a89e  mov     rcx, [rbp+188h]; this
0x18000a8a5  lea     r8, aWil; "wil"
0x18000a8ac  mov     r9d, esi; char *
0x18000a8af  mov     edx, 137h; void *
0x18000a8b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8b9  test    rdi, rdi
0x18000a8bc  jz      short loc_18000A8D5
0x18000a8be  mov     rcx, rdi; hMutex
0x18000a8c1  call    cs:__imp_ReleaseMutex
0x18000a8c8  nop     dword ptr [rax+rax+00h]
0x18000a8cd  test    eax, eax
0x18000a8cf  jz      loc_18000AA3C
0x18000a8d5  mov     rcx, rbx; hObject
0x18000a8d8  call    cs:__imp_CloseHandle
0x18000a8df  nop     dword ptr [rax+rax+00h]
0x18000a8e4  test    eax, eax
0x18000a8e6  jz      loc_18000A9F9
0x18000a8ec  jmp     loc_18000A7CF
0x18000a8f1  mov     rax, [rsp+280h+var_250]
0x18000a8f6  lea     rcx, [r14+28h]; void *
0x18000a8fa  mov     [r14+10h], rax
0x18000a8fe  xor     edx, edx; Val
0x18000a900  mov     rax, [rsp+280h+var_250+8]
0x18000a905  mov     r8d, 108h; Size
0x18000a90b  mov     [r14+18h], rax
0x18000a90f  mov     dword ptr [r14], 1
0x18000a916  mov     [r14+8], rbx
0x18000a91a  mov     [rsp+280h+var_250], 0
0x18000a923  mov     [rsp+280h+var_250+8], 0
0x18000a92c  call    memset_0
0x18000a931  xor     eax, eax
0x18000a933  lea     rcx, [r14+28h]; this
0x18000a937  mov     [r14+20h], rax
0x18000a93b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a940  lea     rbx, [r14+0E8h]
0x18000a947  xor     r8d, r8d; Flags
0x18000a94a  mov     rcx, rbx; lpCriticalSection
0x18000a94d  xor     edx, edx; dwSpinCount
0x18000a94f  call    cs:__imp_InitializeCriticalSectionEx
0x18000a956  nop     dword ptr [rax+rax+00h]
0x18000a95b  mov     qword ptr [rbx+28h], 0
0x18000a963  lea     rcx, [rsp+280h+var_250]; this
0x18000a968  mov     qword ptr [rbx+30h], 0
0x18000a970  mov     qword ptr [rbx+38h], 0
0x18000a978  mov     qword ptr [rbx+40h], 0
0x18000a980  mov     [r15], r14
0x18000a983  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a988  xor     ebx, ebx
0x18000a98a  test    rdi, rdi
0x18000a98d  jz      short loc_18000A9A6
0x18000a98f  mov     rcx, rdi; hMutex
0x18000a992  call    cs:__imp_ReleaseMutex
0x18000a999  nop     dword ptr [rax+rax+00h]
0x18000a99e  test    eax, eax
0x18000a9a0  jz      loc_18000AA4E
0x18000a9a6  test    rbx, rbx
0x18000a9a9  jz      short loc_18000A9BE
0x18000a9ab  mov     rcx, rbx; hObject
0x18000a9ae  call    cs:__imp_CloseHandle
0x18000a9b5  nop     dword ptr [rax+rax+00h]
0x18000a9ba  test    eax, eax
0x18000a9bc  jz      short loc_18000A9E7
0x18000a9be  xor     eax, eax
0x18000a9c0  mov     rcx, [rbp+180h+var_30]
0x18000a9c7  xor     rcx, rsp; StackCookie
0x18000a9ca  call    __security_check_cookie
0x18000a9cf  mov     rbx, [rsp+280h+arg_10]
0x18000a9d7  add     rsp, 260h
0x18000a9de  pop     r15
0x18000a9e0  pop     r14
0x18000a9e2  pop     rdi
0x18000a9e3  pop     rsi
0x18000a9e4  pop     rbp
0x18000a9e5  retn
0x18000a9e7  mov     rcx, [rbp+188h]; this
0x18000a9ee  mov     edx, 0A0Bh; void *
0x18000a9f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9f9  mov     rcx, [rbp+188h]; this
0x18000aa00  mov     edx, 0A0Bh; void *
0x18000aa05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa0b  mov     rcx, [rbp+188h]; this
0x18000aa12  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000aa18  mov     rcx, [rbp+188h]; this
0x18000aa1f  mov     edx, 0A15h; void *
0x18000aa24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa2a  mov     rcx, [rbp+188h]; this
0x18000aa31  mov     edx, 0A0Bh; void *
0x18000aa36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa3c  mov     rcx, [rbp+188h]; this
0x18000aa43  mov     edx, 0A15h; void *
0x18000aa48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa4e  mov     rcx, [rbp+188h]; this
0x18000aa55  mov     edx, 0A15h; void *
0x18000aa5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
