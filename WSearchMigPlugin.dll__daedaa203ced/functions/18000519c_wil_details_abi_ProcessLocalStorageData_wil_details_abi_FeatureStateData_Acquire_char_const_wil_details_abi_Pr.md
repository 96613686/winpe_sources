# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000519c`
- end: `0x180005563`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005834`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x180004360`
- `0x18000519c`
- `0x18000556c`
- `0x180005a90`
- `0x1800063f0`
- `0x1800070f4`
- `0x1800086cc`
- `0x1800091e4`
- `0x18000964c`
- `0x180009efc`
- `0x180009f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005445`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005445`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800053dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005478`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800053dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005478`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005213`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005213`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005234`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005234`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005386`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000539e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005386`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000539e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x18000519c  mov     [rsp-8+arg_10], rbx
0x1800051a1  push    rbp
0x1800051a2  push    rsi
0x1800051a3  push    rdi
0x1800051a4  push    r14
0x1800051a6  push    r15
0x1800051a8  lea     rbp, [rsp-160h]
0x1800051b0  sub     rsp, 260h
0x1800051b7  mov     rax, cs:__security_cookie
0x1800051be  xor     rax, rsp
0x1800051c1  mov     [rbp+180h+var_30], rax
0x1800051c8  mov     r15, rdx
0x1800051cb  mov     qword ptr [rdx], 0
0x1800051d2  mov     rbx, rcx
0x1800051d5  call    cs:__imp_GetCurrentProcessId
0x1800051db  mov     r14d, 130h
0x1800051e1  mov     [rsp+280h+var_258], rbx
0x1800051e6  mov     r9d, eax
0x1800051e9  mov     [rsp+280h+var_260], r14d; int
0x1800051ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800051f5  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800051fa  lea     edx, [r14-2Ch]; unsigned __int64
0x1800051fe  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005203  mov     r9d, 1F0001h; dwDesiredAccess
0x180005209  lea     rdx, [rsp+280h+Name]; lpName
0x18000520e  xor     r8d, r8d; dwFlags
0x180005211  xor     ecx, ecx; lpMutexAttributes
0x180005213  call    cs:__imp_CreateMutexExW
0x180005219  mov     rbx, rax
0x18000521c  test    rax, rax
0x18000521f  jnz     short loc_18000522B
0x180005221  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005226  jmp     loc_18000549A
0x18000522b  xor     r8d, r8d; bAlertable
0x18000522e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005231  mov     rcx, rbx; hHandle
0x180005234  call    cs:__imp_WaitForSingleObjectEx
0x18000523a  cmp     eax, 102h
0x18000523f  jz      short loc_180005251
0x180005241  test    eax, 0FFFFFF7Fh
0x180005246  jnz     loc_1800054E4
0x18000524c  mov     rdi, rbx
0x18000524f  jmp     short loc_180005253
0x180005251  xor     edi, edi
0x180005253  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005258  mov     [rsp+280h+hObject], 0
0x180005261  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005266  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000526b  mov     esi, eax
0x18000526d  test    eax, eax
0x18000526f  jns     short loc_1800052DB
0x180005271  mov     rcx, [rbp+188h]; this
0x180005278  mov     r9d, eax; char *
0x18000527b  mov     edx, 66h ; 'f'; void *
0x180005280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005285  mov     rcx, [rbp+188h]; this
0x18000528c  mov     r9d, esi; char *
0x18000528f  mov     edx, 6Fh ; 'o'; void *
0x180005294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005299  mov     rcx, [rbp+188h]; this
0x1800052a0  mov     r9d, esi; char *
0x1800052a3  mov     edx, 12Eh; void *
0x1800052a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052ad  test    rdi, rdi
0x1800052b0  jz      short loc_1800052C3
0x1800052b2  mov     rcx, rdi; hMutex
0x1800052b5  call    cs:__imp_ReleaseMutex
0x1800052bb  test    eax, eax
0x1800052bd  jz      loc_1800054F1
0x1800052c3  mov     rcx, rbx; hObject
0x1800052c6  call    cs:__imp_CloseHandle
0x1800052cc  test    eax, eax
0x1800052ce  jz      loc_180005503
0x1800052d4  mov     eax, esi
0x1800052d6  jmp     loc_18000549A
0x1800052db  mov     rax, [rsp+280h+hObject]
0x1800052e0  lea     rcx, ds:0[rax*4]
0x1800052e8  test    rcx, rcx
0x1800052eb  jz      short loc_1800052FB
0x1800052ed  mov     [r15], rcx
0x1800052f0  mov     eax, [rcx]
0x1800052f2  inc     eax
0x1800052f4  mov     [rcx], eax
0x1800052f6  jmp     loc_180005470
0x1800052fb  mov     rdx, r14; dwBytes
0x1800052fe  mov     qword ptr [r15], 0
0x180005305  mov     ecx, 8; dwFlags
0x18000530a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000530f  mov     r14, rax
0x180005312  test    rax, rax
0x180005315  jnz     short loc_180005335
0x180005317  mov     rcx, [rbp+188h]; this
0x18000531e  mov     esi, 8007000Eh
0x180005323  mov     r9d, esi; char *
0x180005326  mov     edx, 14Bh; void *
0x18000532b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005330  jmp     loc_1800053C0
0x180005335  xorps   xmm0, xmm0
0x180005338  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000533e  test    r14b, 3
0x180005342  jnz     loc_180005515
0x180005348  mov     r9, r14
0x18000534b  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180005350  shr     r9, 2; unsigned __int64
0x180005354  lea     rcx, [rsp+280h+hObject]; this
0x180005359  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000535e  mov     esi, eax
0x180005360  test    eax, eax
0x180005362  jns     loc_180005400
0x180005368  mov     rcx, [rbp+188h]; this
0x18000536f  mov     r9d, eax; char *
0x180005372  mov     edx, 14Eh; void *
0x180005377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000537c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005381  test    rcx, rcx
0x180005384  jz      short loc_180005394
0x180005386  call    cs:__imp_CloseHandle
0x18000538c  test    eax, eax
0x18000538e  jz      loc_18000551B
0x180005394  mov     rcx, [rsp+280h+hObject]; hObject
0x180005399  test    rcx, rcx
0x18000539c  jz      short loc_1800053AC
0x18000539e  call    cs:__imp_CloseHandle
0x1800053a4  test    eax, eax
0x1800053a6  jz      loc_18000552D
0x1800053ac  call    cs:__imp_GetProcessHeap
0x1800053b2  mov     r8, r14; lpMem
0x1800053b5  xor     edx, edx; dwFlags
0x1800053b7  mov     rcx, rax; hHeap
0x1800053ba  call    cs:__imp_HeapFree
0x1800053c0  mov     rcx, [rbp+188h]; this
0x1800053c7  mov     r9d, esi; char *
0x1800053ca  mov     edx, 137h; void *
0x1800053cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053d4  test    rdi, rdi
0x1800053d7  jz      short loc_1800053EA
0x1800053d9  mov     rcx, rdi; hMutex
0x1800053dc  call    cs:__imp_ReleaseMutex
0x1800053e2  test    eax, eax
0x1800053e4  jz      loc_18000553F
0x1800053ea  mov     rcx, rbx; hObject
0x1800053ed  call    cs:__imp_CloseHandle
0x1800053f3  test    eax, eax
0x1800053f5  jz      loc_1800054D2
0x1800053fb  jmp     loc_1800052D4
0x180005400  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005405  lea     rcx, [r14+28h]; void *
0x180005409  mov     dword ptr [r14], 1
0x180005410  xor     edx, edx; Val
0x180005412  mov     [r14+8], rbx
0x180005416  mov     r8d, 108h; Size
0x18000541c  movdqu  xmmword ptr [r14+10h], xmm0
0x180005422  call    memset_0
0x180005427  xor     eax, eax
0x180005429  lea     rcx, [r14+28h]; this
0x18000542d  mov     [r14+20h], rax
0x180005431  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005436  lea     rbx, [r14+0E8h]
0x18000543d  xor     r8d, r8d; Flags
0x180005440  mov     rcx, rbx; lpCriticalSection
0x180005443  xor     edx, edx; dwSpinCount
0x180005445  call    cs:__imp_InitializeCriticalSectionEx
0x18000544b  mov     qword ptr [rbx+28h], 0
0x180005453  mov     qword ptr [rbx+30h], 0
0x18000545b  mov     qword ptr [rbx+38h], 0
0x180005463  mov     qword ptr [rbx+40h], 0
0x18000546b  xor     ebx, ebx
0x18000546d  mov     [r15], r14
0x180005470  test    rdi, rdi
0x180005473  jz      short loc_180005486
0x180005475  mov     rcx, rdi; hMutex
0x180005478  call    cs:__imp_ReleaseMutex
0x18000547e  test    eax, eax
0x180005480  jz      loc_180005551
0x180005486  test    rbx, rbx
0x180005489  jz      short loc_180005498
0x18000548b  mov     rcx, rbx; hObject
0x18000548e  call    cs:__imp_CloseHandle
0x180005494  test    eax, eax
0x180005496  jz      short loc_1800054C0
0x180005498  xor     eax, eax
0x18000549a  mov     rcx, [rbp+180h+var_30]
0x1800054a1  xor     rcx, rsp; StackCookie
0x1800054a4  call    __security_check_cookie
0x1800054a9  mov     rbx, [rsp+280h+arg_10]
0x1800054b1  add     rsp, 260h
0x1800054b8  pop     r15
0x1800054ba  pop     r14
0x1800054bc  pop     rdi
0x1800054bd  pop     rsi
0x1800054be  pop     rbp
0x1800054bf  retn
0x1800054c0  mov     rcx, [rbp+188h]; this
0x1800054c7  mov     edx, 0A0Bh; void *
0x1800054cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054d2  mov     rcx, [rbp+188h]; this
0x1800054d9  mov     edx, 0A0Bh; void *
0x1800054de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054e4  mov     rcx, [rbp+188h]; this
0x1800054eb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800054f1  mov     rcx, [rbp+188h]; this
0x1800054f8  mov     edx, 0A15h; void *
0x1800054fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005503  mov     rcx, [rbp+188h]; this
0x18000550a  mov     edx, 0A0Bh; void *
0x18000550f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005515  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000551b  mov     rcx, [rbp+188h]; this
0x180005522  mov     edx, 0A0Bh; void *
0x180005527  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000552d  mov     rcx, [rbp+188h]; this
0x180005534  mov     edx, 0A0Bh; void *
0x180005539  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000553f  mov     rcx, [rbp+188h]; this
0x180005546  mov     edx, 0A15h; void *
0x18000554b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005551  mov     rcx, [rbp+188h]; this
0x180005558  mov     edx, 0A15h; void *
0x18000555d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
