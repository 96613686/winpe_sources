# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180015244`
- end: `0x18001563a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180015fac`

## callees

- `0x180003520`
- `0x180004118`
- `0x18000708c`
- `0x1800074c4`
- `0x180008088`
- `0x180008d74`
- `0x1800092a4`
- `0x180009c94`
- `0x180009d88`
- `0x18000a364`
- `0x18000a374`
- `0x180011f7c`
- `0x180015244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180015517`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180015517`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800152bb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800152bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800152dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800152dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015372`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800154ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001554a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015372`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800154ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001554a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015485`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015485`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015477`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001527d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001527d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015560`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015560`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x180015244  mov     [rsp-8+arg_10], rbx
0x180015249  push    rbp
0x18001524a  push    rsi
0x18001524b  push    rdi
0x18001524c  push    r14
0x18001524e  push    r15
0x180015250  lea     rbp, [rsp-160h]
0x180015258  sub     rsp, 260h
0x18001525f  mov     rax, cs:__security_cookie
0x180015266  xor     rax, rsp
0x180015269  mov     [rbp+180h+var_30], rax
0x180015270  mov     r15, rdx
0x180015273  mov     qword ptr [rdx], 0
0x18001527a  mov     rbx, rcx
0x18001527d  call    cs:__imp_GetCurrentProcessId
0x180015283  mov     r14d, 130h
0x180015289  mov     [rsp+280h+var_258], rbx
0x18001528e  mov     r9d, eax
0x180015291  mov     [rsp+280h+var_260], r14d; int
0x180015296  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001529d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800152a2  lea     edx, [r14-2Ch]; unsigned __int64
0x1800152a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800152ab  mov     r9d, 1F0001h; dwDesiredAccess
0x1800152b1  lea     rdx, [rsp+280h+Name]; lpName
0x1800152b6  xor     r8d, r8d; dwFlags
0x1800152b9  xor     ecx, ecx; lpMutexAttributes
0x1800152bb  call    cs:__imp_CreateMutexExW
0x1800152c1  mov     rbx, rax
0x1800152c4  test    rax, rax
0x1800152c7  jnz     short loc_1800152D3
0x1800152c9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800152ce  jmp     loc_18001556C
0x1800152d3  xor     r8d, r8d; bAlertable
0x1800152d6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800152d9  mov     rcx, rbx; hHandle
0x1800152dc  call    cs:__imp_WaitForSingleObjectEx
0x1800152e2  cmp     eax, 102h
0x1800152e7  jz      short loc_1800152F9
0x1800152e9  test    eax, 0FFFFFF7Fh
0x1800152ee  jnz     loc_1800155B6
0x1800152f4  mov     rdi, rbx
0x1800152f7  jmp     short loc_1800152FB
0x1800152f9  xor     edi, edi
0x1800152fb  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180015300  mov     [rsp+280h+hObject], 0
0x180015309  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001530e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180015313  mov     esi, eax
0x180015315  test    eax, eax
0x180015317  jns     short loc_180015398
0x180015319  mov     rcx, [rbp+188h]; this
0x180015320  lea     r8, aWil; "wil"
0x180015327  mov     r9d, eax; char *
0x18001532a  mov     edx, 66h ; 'f'; void *
0x18001532f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015334  mov     rcx, [rbp+188h]; this
0x18001533b  lea     r8, aWil; "wil"
0x180015342  mov     r9d, esi; char *
0x180015345  mov     edx, 6Fh ; 'o'; void *
0x18001534a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001534f  mov     rcx, [rbp+188h]; this
0x180015356  lea     r8, aWil; "wil"
0x18001535d  mov     r9d, esi; char *
0x180015360  mov     edx, 12Eh; void *
0x180015365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001536a  test    rdi, rdi
0x18001536d  jz      short loc_180015380
0x18001536f  mov     rcx, rdi; hMutex
0x180015372  call    cs:__imp_ReleaseMutex
0x180015378  test    eax, eax
0x18001537a  jz      loc_1800155C8
0x180015380  mov     rcx, rbx; hObject
0x180015383  call    cs:__imp_CloseHandle
0x180015389  test    eax, eax
0x18001538b  jz      loc_1800155DA
0x180015391  mov     eax, esi
0x180015393  jmp     loc_18001556C
0x180015398  mov     rax, [rsp+280h+hObject]
0x18001539d  lea     rcx, ds:0[rax*4]
0x1800153a5  test    rcx, rcx
0x1800153a8  jz      short loc_1800153B8
0x1800153aa  mov     [r15], rcx
0x1800153ad  mov     eax, [rcx]
0x1800153af  inc     eax
0x1800153b1  mov     [rcx], eax
0x1800153b3  jmp     loc_180015542
0x1800153b8  mov     rdx, r14; dwBytes
0x1800153bb  mov     qword ptr [r15], 0
0x1800153c2  mov     ecx, 8; dwFlags
0x1800153c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800153cc  mov     r14, rax
0x1800153cf  test    rax, rax
0x1800153d2  jnz     short loc_1800153F9
0x1800153d4  mov     rcx, [rbp+188h]; this
0x1800153db  lea     r8, aWil; "wil"
0x1800153e2  mov     esi, 8007000Eh
0x1800153e7  mov     edx, 14Bh; void *
0x1800153ec  mov     r9d, esi; char *
0x1800153ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153f4  jmp     loc_18001548B
0x1800153f9  xorps   xmm0, xmm0
0x1800153fc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180015402  test    r14b, 3
0x180015406  jnz     loc_1800155EC
0x18001540c  mov     r9, r14
0x18001540f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180015414  shr     r9, 2; unsigned __int64
0x180015418  lea     rcx, [rsp+280h+hObject]; this
0x18001541d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180015422  mov     esi, eax
0x180015424  test    eax, eax
0x180015426  jns     loc_1800154D2
0x18001542c  mov     rcx, [rbp+188h]; this
0x180015433  lea     r8, aWil; "wil"
0x18001543a  mov     r9d, eax; char *
0x18001543d  mov     edx, 14Eh; void *
0x180015442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015447  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18001544c  test    rcx, rcx
0x18001544f  jz      short loc_18001545F
0x180015451  call    cs:__imp_CloseHandle
0x180015457  test    eax, eax
0x180015459  jz      loc_1800155F2
0x18001545f  mov     rcx, [rsp+280h+hObject]; hObject
0x180015464  test    rcx, rcx
0x180015467  jz      short loc_180015477
0x180015469  call    cs:__imp_CloseHandle
0x18001546f  test    eax, eax
0x180015471  jz      loc_180015604
0x180015477  call    cs:__imp_GetProcessHeap
0x18001547d  mov     r8, r14; lpMem
0x180015480  xor     edx, edx; dwFlags
0x180015482  mov     rcx, rax; hHeap
0x180015485  call    cs:__imp_HeapFree
0x18001548b  mov     rcx, [rbp+188h]; this
0x180015492  lea     r8, aWil; "wil"
0x180015499  mov     r9d, esi; char *
0x18001549c  mov     edx, 137h; void *
0x1800154a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154a6  test    rdi, rdi
0x1800154a9  jz      short loc_1800154BC
0x1800154ab  mov     rcx, rdi; hMutex
0x1800154ae  call    cs:__imp_ReleaseMutex
0x1800154b4  test    eax, eax
0x1800154b6  jz      loc_180015616
0x1800154bc  mov     rcx, rbx; hObject
0x1800154bf  call    cs:__imp_CloseHandle
0x1800154c5  test    eax, eax
0x1800154c7  jz      loc_1800155A4
0x1800154cd  jmp     loc_180015391
0x1800154d2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800154d7  lea     rcx, [r14+28h]; void *
0x1800154db  mov     dword ptr [r14], 1
0x1800154e2  xor     edx, edx; Val
0x1800154e4  mov     [r14+8], rbx
0x1800154e8  mov     r8d, 108h; Size
0x1800154ee  movdqu  xmmword ptr [r14+10h], xmm0
0x1800154f4  call    memset_0
0x1800154f9  xor     eax, eax
0x1800154fb  lea     rcx, [r14+28h]; this
0x1800154ff  mov     [r14+20h], rax
0x180015503  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180015508  lea     rbx, [r14+0E8h]
0x18001550f  xor     r8d, r8d; Flags
0x180015512  mov     rcx, rbx; lpCriticalSection
0x180015515  xor     edx, edx; dwSpinCount
0x180015517  call    cs:__imp_InitializeCriticalSectionEx
0x18001551d  mov     qword ptr [rbx+28h], 0
0x180015525  mov     qword ptr [rbx+30h], 0
0x18001552d  mov     qword ptr [rbx+38h], 0
0x180015535  mov     qword ptr [rbx+40h], 0
0x18001553d  xor     ebx, ebx
0x18001553f  mov     [r15], r14
0x180015542  test    rdi, rdi
0x180015545  jz      short loc_180015558
0x180015547  mov     rcx, rdi; hMutex
0x18001554a  call    cs:__imp_ReleaseMutex
0x180015550  test    eax, eax
0x180015552  jz      loc_180015628
0x180015558  test    rbx, rbx
0x18001555b  jz      short loc_18001556A
0x18001555d  mov     rcx, rbx; hObject
0x180015560  call    cs:__imp_CloseHandle
0x180015566  test    eax, eax
0x180015568  jz      short loc_180015592
0x18001556a  xor     eax, eax
0x18001556c  mov     rcx, [rbp+180h+var_30]
0x180015573  xor     rcx, rsp; StackCookie
0x180015576  call    __security_check_cookie
0x18001557b  mov     rbx, [rsp+280h+arg_10]
0x180015583  add     rsp, 260h
0x18001558a  pop     r15
0x18001558c  pop     r14
0x18001558e  pop     rdi
0x18001558f  pop     rsi
0x180015590  pop     rbp
0x180015591  retn
0x180015592  mov     rcx, [rbp+188h]; this
0x180015599  mov     edx, 0A0Bh; void *
0x18001559e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800155a4  mov     rcx, [rbp+188h]; this
0x1800155ab  mov     edx, 0A0Bh; void *
0x1800155b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800155b6  mov     rcx, [rbp+188h]; this
0x1800155bd  mov     edx, 0E01h; void *
0x1800155c2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800155c8  mov     rcx, [rbp+188h]; this
0x1800155cf  mov     edx, 0A15h; void *
0x1800155d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800155da  mov     rcx, [rbp+188h]; this
0x1800155e1  mov     edx, 0A0Bh; void *
0x1800155e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800155ec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800155f2  mov     rcx, [rbp+188h]; this
0x1800155f9  mov     edx, 0A0Bh; void *
0x1800155fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015604  mov     rcx, [rbp+188h]; this
0x18001560b  mov     edx, 0A0Bh; void *
0x180015610  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015616  mov     rcx, [rbp+188h]; this
0x18001561d  mov     edx, 0A15h; void *
0x180015622  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015628  mov     rcx, [rbp+188h]; this
0x18001562f  mov     edx, 0A15h; void *
0x180015634  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
