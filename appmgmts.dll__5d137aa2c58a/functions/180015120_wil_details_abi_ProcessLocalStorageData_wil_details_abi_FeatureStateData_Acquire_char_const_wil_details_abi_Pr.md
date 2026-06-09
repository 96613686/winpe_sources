# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180015120`
- end: `0x1800154e7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800157d4`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180008f58`
- `0x180014490`
- `0x180015120`
- `0x1800154f0`
- `0x180015964`
- `0x180016298`
- `0x180016e88`
- `0x1800181b4`
- `0x180018ecc`
- `0x1800196ac`
- `0x1800196bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001524a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001530a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001524a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001530a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015412`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015239`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015360`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015239`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015360`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153fc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800153c9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800153c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015197`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015197`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800151b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800151b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001533e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001533e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015330`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015330`

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
0x180015120  mov     [rsp-8+arg_10], rbx
0x180015125  push    rbp
0x180015126  push    rsi
0x180015127  push    rdi
0x180015128  push    r14
0x18001512a  push    r15
0x18001512c  lea     rbp, [rsp-160h]
0x180015134  sub     rsp, 260h
0x18001513b  mov     rax, cs:__security_cookie
0x180015142  xor     rax, rsp
0x180015145  mov     [rbp+180h+var_30], rax
0x18001514c  mov     r15, rdx
0x18001514f  mov     qword ptr [rdx], 0
0x180015156  mov     rbx, rcx
0x180015159  call    cs:__imp_GetCurrentProcessId
0x18001515f  mov     r14d, 130h
0x180015165  mov     [rsp+280h+var_258], rbx
0x18001516a  mov     r9d, eax
0x18001516d  mov     [rsp+280h+var_260], r14d; int
0x180015172  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180015179  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001517e  lea     edx, [r14-2Ch]; unsigned __int64
0x180015182  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015187  mov     r9d, 1F0001h; dwDesiredAccess
0x18001518d  lea     rdx, [rsp+280h+Name]; lpName
0x180015192  xor     r8d, r8d; dwFlags
0x180015195  xor     ecx, ecx; lpMutexAttributes
0x180015197  call    cs:__imp_CreateMutexExW
0x18001519d  mov     rbx, rax
0x1800151a0  test    rax, rax
0x1800151a3  jnz     short loc_1800151AF
0x1800151a5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800151aa  jmp     loc_18001541E
0x1800151af  xor     r8d, r8d; bAlertable
0x1800151b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800151b5  mov     rcx, rbx; hHandle
0x1800151b8  call    cs:__imp_WaitForSingleObjectEx
0x1800151be  cmp     eax, 102h
0x1800151c3  jz      short loc_1800151D5
0x1800151c5  test    eax, 0FFFFFF7Fh
0x1800151ca  jnz     loc_180015468
0x1800151d0  mov     rdi, rbx
0x1800151d3  jmp     short loc_1800151D7
0x1800151d5  xor     edi, edi
0x1800151d7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800151dc  mov     [rsp+280h+hObject], 0
0x1800151e5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800151ea  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800151ef  mov     esi, eax
0x1800151f1  test    eax, eax
0x1800151f3  jns     short loc_18001525F
0x1800151f5  mov     rcx, [rbp+188h]; this
0x1800151fc  mov     r9d, eax; char *
0x1800151ff  mov     edx, 66h ; 'f'; void *
0x180015204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015209  mov     rcx, [rbp+188h]; this
0x180015210  mov     r9d, esi; char *
0x180015213  mov     edx, 6Fh ; 'o'; void *
0x180015218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001521d  mov     rcx, [rbp+188h]; this
0x180015224  mov     r9d, esi; char *
0x180015227  mov     edx, 12Eh; void *
0x18001522c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015231  test    rdi, rdi
0x180015234  jz      short loc_180015247
0x180015236  mov     rcx, rdi; hMutex
0x180015239  call    cs:__imp_ReleaseMutex
0x18001523f  test    eax, eax
0x180015241  jz      loc_180015475
0x180015247  mov     rcx, rbx; hObject
0x18001524a  call    cs:__imp_CloseHandle
0x180015250  test    eax, eax
0x180015252  jz      loc_180015487
0x180015258  mov     eax, esi
0x18001525a  jmp     loc_18001541E
0x18001525f  mov     rax, [rsp+280h+hObject]
0x180015264  lea     rcx, ds:0[rax*4]
0x18001526c  test    rcx, rcx
0x18001526f  jz      short loc_18001527F
0x180015271  mov     [r15], rcx
0x180015274  mov     eax, [rcx]
0x180015276  inc     eax
0x180015278  mov     [rcx], eax
0x18001527a  jmp     loc_1800153F4
0x18001527f  mov     rdx, r14; dwBytes
0x180015282  mov     qword ptr [r15], 0
0x180015289  mov     ecx, 8; dwFlags
0x18001528e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015293  mov     r14, rax
0x180015296  test    rax, rax
0x180015299  jnz     short loc_1800152B9
0x18001529b  mov     rcx, [rbp+188h]; this
0x1800152a2  mov     esi, 8007000Eh
0x1800152a7  mov     r9d, esi; char *
0x1800152aa  mov     edx, 14Bh; void *
0x1800152af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152b4  jmp     loc_180015344
0x1800152b9  xorps   xmm0, xmm0
0x1800152bc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800152c2  test    r14b, 3
0x1800152c6  jnz     loc_180015499
0x1800152cc  mov     r9, r14
0x1800152cf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800152d4  shr     r9, 2; unsigned __int64
0x1800152d8  lea     rcx, [rsp+280h+hObject]; this
0x1800152dd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800152e2  mov     esi, eax
0x1800152e4  test    eax, eax
0x1800152e6  jns     loc_180015384
0x1800152ec  mov     rcx, [rbp+188h]; this
0x1800152f3  mov     r9d, eax; char *
0x1800152f6  mov     edx, 14Eh; void *
0x1800152fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015300  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180015305  test    rcx, rcx
0x180015308  jz      short loc_180015318
0x18001530a  call    cs:__imp_CloseHandle
0x180015310  test    eax, eax
0x180015312  jz      loc_18001549F
0x180015318  mov     rcx, [rsp+280h+hObject]; hObject
0x18001531d  test    rcx, rcx
0x180015320  jz      short loc_180015330
0x180015322  call    cs:__imp_CloseHandle
0x180015328  test    eax, eax
0x18001532a  jz      loc_1800154B1
0x180015330  call    cs:__imp_GetProcessHeap
0x180015336  mov     r8, r14; lpMem
0x180015339  xor     edx, edx; dwFlags
0x18001533b  mov     rcx, rax; hHeap
0x18001533e  call    cs:__imp_HeapFree
0x180015344  mov     rcx, [rbp+188h]; this
0x18001534b  mov     r9d, esi; char *
0x18001534e  mov     edx, 137h; void *
0x180015353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015358  test    rdi, rdi
0x18001535b  jz      short loc_18001536E
0x18001535d  mov     rcx, rdi; hMutex
0x180015360  call    cs:__imp_ReleaseMutex
0x180015366  test    eax, eax
0x180015368  jz      loc_1800154C3
0x18001536e  mov     rcx, rbx; hObject
0x180015371  call    cs:__imp_CloseHandle
0x180015377  test    eax, eax
0x180015379  jz      loc_180015456
0x18001537f  jmp     loc_180015258
0x180015384  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180015389  lea     rcx, [r14+28h]; void *
0x18001538d  mov     dword ptr [r14], 1
0x180015394  xor     edx, edx; Val
0x180015396  mov     [r14+8], rbx
0x18001539a  mov     r8d, 108h; Size
0x1800153a0  movdqu  xmmword ptr [r14+10h], xmm0
0x1800153a6  call    memset_0
0x1800153ab  xor     eax, eax
0x1800153ad  lea     rcx, [r14+28h]; this
0x1800153b1  mov     [r14+20h], rax
0x1800153b5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800153ba  lea     rbx, [r14+0E8h]
0x1800153c1  xor     r8d, r8d; Flags
0x1800153c4  mov     rcx, rbx; lpCriticalSection
0x1800153c7  xor     edx, edx; dwSpinCount
0x1800153c9  call    cs:__imp_InitializeCriticalSectionEx
0x1800153cf  mov     qword ptr [rbx+28h], 0
0x1800153d7  mov     qword ptr [rbx+30h], 0
0x1800153df  mov     qword ptr [rbx+38h], 0
0x1800153e7  mov     qword ptr [rbx+40h], 0
0x1800153ef  xor     ebx, ebx
0x1800153f1  mov     [r15], r14
0x1800153f4  test    rdi, rdi
0x1800153f7  jz      short loc_18001540A
0x1800153f9  mov     rcx, rdi; hMutex
0x1800153fc  call    cs:__imp_ReleaseMutex
0x180015402  test    eax, eax
0x180015404  jz      loc_1800154D5
0x18001540a  test    rbx, rbx
0x18001540d  jz      short loc_18001541C
0x18001540f  mov     rcx, rbx; hObject
0x180015412  call    cs:__imp_CloseHandle
0x180015418  test    eax, eax
0x18001541a  jz      short loc_180015444
0x18001541c  xor     eax, eax
0x18001541e  mov     rcx, [rbp+180h+var_30]
0x180015425  xor     rcx, rsp; StackCookie
0x180015428  call    __security_check_cookie
0x18001542d  mov     rbx, [rsp+280h+arg_10]
0x180015435  add     rsp, 260h
0x18001543c  pop     r15
0x18001543e  pop     r14
0x180015440  pop     rdi
0x180015441  pop     rsi
0x180015442  pop     rbp
0x180015443  retn
0x180015444  mov     rcx, [rbp+188h]; this
0x18001544b  mov     edx, 0A0Bh; void *
0x180015450  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015456  mov     rcx, [rbp+188h]; this
0x18001545d  mov     edx, 0A0Bh; void *
0x180015462  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015468  mov     rcx, [rbp+188h]; this
0x18001546f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180015475  mov     rcx, [rbp+188h]; this
0x18001547c  mov     edx, 0A15h; void *
0x180015481  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015487  mov     rcx, [rbp+188h]; this
0x18001548e  mov     edx, 0A0Bh; void *
0x180015493  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015499  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001549f  mov     rcx, [rbp+188h]; this
0x1800154a6  mov     edx, 0A0Bh; void *
0x1800154ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800154b1  mov     rcx, [rbp+188h]; this
0x1800154b8  mov     edx, 0A0Bh; void *
0x1800154bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800154c3  mov     rcx, [rbp+188h]; this
0x1800154ca  mov     edx, 0A15h; void *
0x1800154cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800154d5  mov     rcx, [rbp+188h]; this
0x1800154dc  mov     edx, 0A15h; void *
0x1800154e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
