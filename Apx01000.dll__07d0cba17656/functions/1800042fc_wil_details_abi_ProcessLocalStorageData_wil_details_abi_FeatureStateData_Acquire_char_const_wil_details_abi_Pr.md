# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800042fc`
- end: `0x1800046c3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004994`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x180003494`
- `0x1800042fc`
- `0x1800046cc`
- `0x180004be8`
- `0x180005518`
- `0x1800061f8`
- `0x1800077c4`
- `0x1800082b8`
- `0x18000871c`
- `0x180008fcc`
- `0x180008fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004373`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004373`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004394`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004394`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004415`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000453c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004415`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000453c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800045d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800045a5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800045a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000451a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000451a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000450c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000450c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000454d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000454d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ee`

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
0x1800042fc  mov     [rsp-8+arg_10], rbx
0x180004301  push    rbp
0x180004302  push    rsi
0x180004303  push    rdi
0x180004304  push    r14
0x180004306  push    r15
0x180004308  lea     rbp, [rsp-160h]
0x180004310  sub     rsp, 260h
0x180004317  mov     rax, cs:__security_cookie
0x18000431e  xor     rax, rsp
0x180004321  mov     [rbp+180h+var_30], rax
0x180004328  mov     r15, rdx
0x18000432b  mov     qword ptr [rdx], 0
0x180004332  mov     rbx, rcx
0x180004335  call    cs:__imp_GetCurrentProcessId
0x18000433b  mov     r14d, 130h
0x180004341  mov     [rsp+280h+var_258], rbx
0x180004346  mov     r9d, eax
0x180004349  mov     [rsp+280h+var_260], r14d; int
0x18000434e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004355  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000435a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000435e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004363  mov     r9d, 1F0001h; dwDesiredAccess
0x180004369  lea     rdx, [rsp+280h+Name]; lpName
0x18000436e  xor     r8d, r8d; dwFlags
0x180004371  xor     ecx, ecx; lpMutexAttributes
0x180004373  call    cs:__imp_CreateMutexExW
0x180004379  mov     rbx, rax
0x18000437c  test    rax, rax
0x18000437f  jnz     short loc_18000438B
0x180004381  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004386  jmp     loc_1800045FA
0x18000438b  xor     r8d, r8d; bAlertable
0x18000438e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004391  mov     rcx, rbx; hHandle
0x180004394  call    cs:__imp_WaitForSingleObjectEx
0x18000439a  cmp     eax, 102h
0x18000439f  jz      short loc_1800043B1
0x1800043a1  test    eax, 0FFFFFF7Fh
0x1800043a6  jnz     loc_180004644
0x1800043ac  mov     rdi, rbx
0x1800043af  jmp     short loc_1800043B3
0x1800043b1  xor     edi, edi
0x1800043b3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800043b8  mov     [rsp+280h+hObject], 0
0x1800043c1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800043c6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800043cb  mov     esi, eax
0x1800043cd  test    eax, eax
0x1800043cf  jns     short loc_18000443B
0x1800043d1  mov     rcx, [rbp+188h]; this
0x1800043d8  mov     r9d, eax; char *
0x1800043db  mov     edx, 66h ; 'f'; void *
0x1800043e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043e5  mov     rcx, [rbp+188h]; this
0x1800043ec  mov     r9d, esi; char *
0x1800043ef  mov     edx, 6Fh ; 'o'; void *
0x1800043f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043f9  mov     rcx, [rbp+188h]; this
0x180004400  mov     r9d, esi; char *
0x180004403  mov     edx, 12Eh; void *
0x180004408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000440d  test    rdi, rdi
0x180004410  jz      short loc_180004423
0x180004412  mov     rcx, rdi; hMutex
0x180004415  call    cs:__imp_ReleaseMutex
0x18000441b  test    eax, eax
0x18000441d  jz      loc_180004651
0x180004423  mov     rcx, rbx; hObject
0x180004426  call    cs:__imp_CloseHandle
0x18000442c  test    eax, eax
0x18000442e  jz      loc_180004663
0x180004434  mov     eax, esi
0x180004436  jmp     loc_1800045FA
0x18000443b  mov     rax, [rsp+280h+hObject]
0x180004440  lea     rcx, ds:0[rax*4]
0x180004448  test    rcx, rcx
0x18000444b  jz      short loc_18000445B
0x18000444d  mov     [r15], rcx
0x180004450  mov     eax, [rcx]
0x180004452  inc     eax
0x180004454  mov     [rcx], eax
0x180004456  jmp     loc_1800045D0
0x18000445b  mov     rdx, r14; dwBytes
0x18000445e  mov     qword ptr [r15], 0
0x180004465  mov     ecx, 8; dwFlags
0x18000446a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000446f  mov     r14, rax
0x180004472  test    rax, rax
0x180004475  jnz     short loc_180004495
0x180004477  mov     rcx, [rbp+188h]; this
0x18000447e  mov     esi, 8007000Eh
0x180004483  mov     r9d, esi; char *
0x180004486  mov     edx, 14Bh; void *
0x18000448b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004490  jmp     loc_180004520
0x180004495  xorps   xmm0, xmm0
0x180004498  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000449e  test    r14b, 3
0x1800044a2  jnz     loc_180004675
0x1800044a8  mov     r9, r14
0x1800044ab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800044b0  shr     r9, 2; unsigned __int64
0x1800044b4  lea     rcx, [rsp+280h+hObject]; this
0x1800044b9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800044be  mov     esi, eax
0x1800044c0  test    eax, eax
0x1800044c2  jns     loc_180004560
0x1800044c8  mov     rcx, [rbp+188h]; this
0x1800044cf  mov     r9d, eax; char *
0x1800044d2  mov     edx, 14Eh; void *
0x1800044d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044dc  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800044e1  test    rcx, rcx
0x1800044e4  jz      short loc_1800044F4
0x1800044e6  call    cs:__imp_CloseHandle
0x1800044ec  test    eax, eax
0x1800044ee  jz      loc_18000467B
0x1800044f4  mov     rcx, [rsp+280h+hObject]; hObject
0x1800044f9  test    rcx, rcx
0x1800044fc  jz      short loc_18000450C
0x1800044fe  call    cs:__imp_CloseHandle
0x180004504  test    eax, eax
0x180004506  jz      loc_18000468D
0x18000450c  call    cs:__imp_GetProcessHeap
0x180004512  mov     r8, r14; lpMem
0x180004515  xor     edx, edx; dwFlags
0x180004517  mov     rcx, rax; hHeap
0x18000451a  call    cs:__imp_HeapFree
0x180004520  mov     rcx, [rbp+188h]; this
0x180004527  mov     r9d, esi; char *
0x18000452a  mov     edx, 137h; void *
0x18000452f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004534  test    rdi, rdi
0x180004537  jz      short loc_18000454A
0x180004539  mov     rcx, rdi; hMutex
0x18000453c  call    cs:__imp_ReleaseMutex
0x180004542  test    eax, eax
0x180004544  jz      loc_18000469F
0x18000454a  mov     rcx, rbx; hObject
0x18000454d  call    cs:__imp_CloseHandle
0x180004553  test    eax, eax
0x180004555  jz      loc_180004632
0x18000455b  jmp     loc_180004434
0x180004560  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004565  lea     rcx, [r14+28h]; void *
0x180004569  mov     dword ptr [r14], 1
0x180004570  xor     edx, edx; Val
0x180004572  mov     [r14+8], rbx
0x180004576  mov     r8d, 108h; Size
0x18000457c  movdqu  xmmword ptr [r14+10h], xmm0
0x180004582  call    memset_0
0x180004587  xor     eax, eax
0x180004589  lea     rcx, [r14+28h]; this
0x18000458d  mov     [r14+20h], rax
0x180004591  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004596  lea     rbx, [r14+0E8h]
0x18000459d  xor     r8d, r8d; Flags
0x1800045a0  mov     rcx, rbx; lpCriticalSection
0x1800045a3  xor     edx, edx; dwSpinCount
0x1800045a5  call    cs:__imp_InitializeCriticalSectionEx
0x1800045ab  mov     qword ptr [rbx+28h], 0
0x1800045b3  mov     qword ptr [rbx+30h], 0
0x1800045bb  mov     qword ptr [rbx+38h], 0
0x1800045c3  mov     qword ptr [rbx+40h], 0
0x1800045cb  xor     ebx, ebx
0x1800045cd  mov     [r15], r14
0x1800045d0  test    rdi, rdi
0x1800045d3  jz      short loc_1800045E6
0x1800045d5  mov     rcx, rdi; hMutex
0x1800045d8  call    cs:__imp_ReleaseMutex
0x1800045de  test    eax, eax
0x1800045e0  jz      loc_1800046B1
0x1800045e6  test    rbx, rbx
0x1800045e9  jz      short loc_1800045F8
0x1800045eb  mov     rcx, rbx; hObject
0x1800045ee  call    cs:__imp_CloseHandle
0x1800045f4  test    eax, eax
0x1800045f6  jz      short loc_180004620
0x1800045f8  xor     eax, eax
0x1800045fa  mov     rcx, [rbp+180h+var_30]
0x180004601  xor     rcx, rsp; StackCookie
0x180004604  call    __security_check_cookie
0x180004609  mov     rbx, [rsp+280h+arg_10]
0x180004611  add     rsp, 260h
0x180004618  pop     r15
0x18000461a  pop     r14
0x18000461c  pop     rdi
0x18000461d  pop     rsi
0x18000461e  pop     rbp
0x18000461f  retn
0x180004620  mov     rcx, [rbp+188h]; this
0x180004627  mov     edx, 0A0Bh; void *
0x18000462c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004632  mov     rcx, [rbp+188h]; this
0x180004639  mov     edx, 0A0Bh; void *
0x18000463e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004644  mov     rcx, [rbp+188h]; this
0x18000464b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004651  mov     rcx, [rbp+188h]; this
0x180004658  mov     edx, 0A15h; void *
0x18000465d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004663  mov     rcx, [rbp+188h]; this
0x18000466a  mov     edx, 0A0Bh; void *
0x18000466f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004675  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000467b  mov     rcx, [rbp+188h]; this
0x180004682  mov     edx, 0A0Bh; void *
0x180004687  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000468d  mov     rcx, [rbp+188h]; this
0x180004694  mov     edx, 0A0Bh; void *
0x180004699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000469f  mov     rcx, [rbp+188h]; this
0x1800046a6  mov     edx, 0A15h; void *
0x1800046ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800046b1  mov     rcx, [rbp+188h]; this
0x1800046b8  mov     edx, 0A15h; void *
0x1800046bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
