# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400063bc`
- end: `0x140006783`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140006bf8`

## callees

- `0x140003474`
- `0x1400037f4`
- `0x140003e48`
- `0x140004a94`
- `0x140004ce0`
- `0x1400050ac`
- `0x140005138`
- `0x1400054ec`
- `0x1400054fc`
- `0x140005ba8`
- `0x1400063bc`
- `0x14001346e`
- `0x1400134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006665`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006665`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006454`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006454`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400064d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400065fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006698`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400064d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400065fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006698`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006433`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006433`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400065da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400065da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400063f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400063f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000660d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000660d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400066ae`

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
0x1400063bc  mov     [rsp-8+arg_10], rbx
0x1400063c1  push    rbp
0x1400063c2  push    rsi
0x1400063c3  push    rdi
0x1400063c4  push    r14
0x1400063c6  push    r15
0x1400063c8  lea     rbp, [rsp-160h]
0x1400063d0  sub     rsp, 260h
0x1400063d7  mov     rax, cs:__security_cookie
0x1400063de  xor     rax, rsp
0x1400063e1  mov     [rbp+180h+var_30], rax
0x1400063e8  mov     r15, rdx
0x1400063eb  mov     qword ptr [rdx], 0
0x1400063f2  mov     rbx, rcx
0x1400063f5  call    cs:__imp_GetCurrentProcessId
0x1400063fb  mov     r14d, 130h
0x140006401  mov     [rsp+280h+var_258], rbx
0x140006406  mov     r9d, eax
0x140006409  mov     [rsp+280h+var_260], r14d; int
0x14000640e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006415  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000641a  lea     edx, [r14-2Ch]; unsigned __int64
0x14000641e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006423  mov     r9d, 1F0001h; dwDesiredAccess
0x140006429  lea     rdx, [rsp+280h+Name]; lpName
0x14000642e  xor     r8d, r8d; dwFlags
0x140006431  xor     ecx, ecx; lpMutexAttributes
0x140006433  call    cs:__imp_CreateMutexExW
0x140006439  mov     rbx, rax
0x14000643c  test    rax, rax
0x14000643f  jnz     short loc_14000644B
0x140006441  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006446  jmp     loc_1400066BA
0x14000644b  xor     r8d, r8d; bAlertable
0x14000644e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140006451  mov     rcx, rbx; hHandle
0x140006454  call    cs:__imp_WaitForSingleObjectEx
0x14000645a  cmp     eax, 102h
0x14000645f  jz      short loc_140006471
0x140006461  test    eax, 0FFFFFF7Fh
0x140006466  jnz     loc_140006704
0x14000646c  mov     rdi, rbx
0x14000646f  jmp     short loc_140006473
0x140006471  xor     edi, edi
0x140006473  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140006478  mov     [rsp+280h+hObject], 0
0x140006481  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006486  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000648b  mov     esi, eax
0x14000648d  test    eax, eax
0x14000648f  jns     short loc_1400064FB
0x140006491  mov     rcx, [rbp+188h]; this
0x140006498  mov     r9d, eax; char *
0x14000649b  mov     edx, 66h ; 'f'; void *
0x1400064a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064a5  mov     rcx, [rbp+188h]; this
0x1400064ac  mov     r9d, esi; char *
0x1400064af  mov     edx, 6Fh ; 'o'; void *
0x1400064b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064b9  mov     rcx, [rbp+188h]; this
0x1400064c0  mov     r9d, esi; char *
0x1400064c3  mov     edx, 12Eh; void *
0x1400064c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064cd  test    rdi, rdi
0x1400064d0  jz      short loc_1400064E3
0x1400064d2  mov     rcx, rdi; hMutex
0x1400064d5  call    cs:__imp_ReleaseMutex
0x1400064db  test    eax, eax
0x1400064dd  jz      loc_140006711
0x1400064e3  mov     rcx, rbx; hObject
0x1400064e6  call    cs:__imp_CloseHandle
0x1400064ec  test    eax, eax
0x1400064ee  jz      loc_140006723
0x1400064f4  mov     eax, esi
0x1400064f6  jmp     loc_1400066BA
0x1400064fb  mov     rax, [rsp+280h+hObject]
0x140006500  lea     rcx, ds:0[rax*4]
0x140006508  test    rcx, rcx
0x14000650b  jz      short loc_14000651B
0x14000650d  mov     [r15], rcx
0x140006510  mov     eax, [rcx]
0x140006512  inc     eax
0x140006514  mov     [rcx], eax
0x140006516  jmp     loc_140006690
0x14000651b  mov     rdx, r14; dwBytes
0x14000651e  mov     qword ptr [r15], 0
0x140006525  mov     ecx, 8; dwFlags
0x14000652a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000652f  mov     r14, rax
0x140006532  test    rax, rax
0x140006535  jnz     short loc_140006555
0x140006537  mov     rcx, [rbp+188h]; this
0x14000653e  mov     esi, 8007000Eh
0x140006543  mov     r9d, esi; char *
0x140006546  mov     edx, 14Bh; void *
0x14000654b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006550  jmp     loc_1400065E0
0x140006555  xorps   xmm0, xmm0
0x140006558  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000655e  test    r14b, 3
0x140006562  jnz     loc_140006735
0x140006568  mov     r9, r14
0x14000656b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140006570  shr     r9, 2; unsigned __int64
0x140006574  lea     rcx, [rsp+280h+hObject]; this
0x140006579  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000657e  mov     esi, eax
0x140006580  test    eax, eax
0x140006582  jns     loc_140006620
0x140006588  mov     rcx, [rbp+188h]; this
0x14000658f  mov     r9d, eax; char *
0x140006592  mov     edx, 14Eh; void *
0x140006597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000659c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400065a1  test    rcx, rcx
0x1400065a4  jz      short loc_1400065B4
0x1400065a6  call    cs:__imp_CloseHandle
0x1400065ac  test    eax, eax
0x1400065ae  jz      loc_14000673B
0x1400065b4  mov     rcx, [rsp+280h+hObject]; hObject
0x1400065b9  test    rcx, rcx
0x1400065bc  jz      short loc_1400065CC
0x1400065be  call    cs:__imp_CloseHandle
0x1400065c4  test    eax, eax
0x1400065c6  jz      loc_14000674D
0x1400065cc  call    cs:__imp_GetProcessHeap
0x1400065d2  mov     r8, r14; lpMem
0x1400065d5  xor     edx, edx; dwFlags
0x1400065d7  mov     rcx, rax; hHeap
0x1400065da  call    cs:__imp_HeapFree
0x1400065e0  mov     rcx, [rbp+188h]; this
0x1400065e7  mov     r9d, esi; char *
0x1400065ea  mov     edx, 137h; void *
0x1400065ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400065f4  test    rdi, rdi
0x1400065f7  jz      short loc_14000660A
0x1400065f9  mov     rcx, rdi; hMutex
0x1400065fc  call    cs:__imp_ReleaseMutex
0x140006602  test    eax, eax
0x140006604  jz      loc_14000675F
0x14000660a  mov     rcx, rbx; hObject
0x14000660d  call    cs:__imp_CloseHandle
0x140006613  test    eax, eax
0x140006615  jz      loc_1400066F2
0x14000661b  jmp     loc_1400064F4
0x140006620  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140006625  lea     rcx, [r14+28h]; void *
0x140006629  mov     dword ptr [r14], 1
0x140006630  xor     edx, edx; Val
0x140006632  mov     [r14+8], rbx
0x140006636  mov     r8d, 108h; Size
0x14000663c  movdqu  xmmword ptr [r14+10h], xmm0
0x140006642  call    memset_0
0x140006647  xor     eax, eax
0x140006649  lea     rcx, [r14+28h]; this
0x14000664d  mov     [r14+20h], rax
0x140006651  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006656  lea     rbx, [r14+0E8h]
0x14000665d  xor     r8d, r8d; Flags
0x140006660  mov     rcx, rbx; lpCriticalSection
0x140006663  xor     edx, edx; dwSpinCount
0x140006665  call    cs:__imp_InitializeCriticalSectionEx
0x14000666b  mov     qword ptr [rbx+28h], 0
0x140006673  mov     qword ptr [rbx+30h], 0
0x14000667b  mov     qword ptr [rbx+38h], 0
0x140006683  mov     qword ptr [rbx+40h], 0
0x14000668b  xor     ebx, ebx
0x14000668d  mov     [r15], r14
0x140006690  test    rdi, rdi
0x140006693  jz      short loc_1400066A6
0x140006695  mov     rcx, rdi; hMutex
0x140006698  call    cs:__imp_ReleaseMutex
0x14000669e  test    eax, eax
0x1400066a0  jz      loc_140006771
0x1400066a6  test    rbx, rbx
0x1400066a9  jz      short loc_1400066B8
0x1400066ab  mov     rcx, rbx; hObject
0x1400066ae  call    cs:__imp_CloseHandle
0x1400066b4  test    eax, eax
0x1400066b6  jz      short loc_1400066E0
0x1400066b8  xor     eax, eax
0x1400066ba  mov     rcx, [rbp+180h+var_30]
0x1400066c1  xor     rcx, rsp; StackCookie
0x1400066c4  call    __security_check_cookie
0x1400066c9  mov     rbx, [rsp+280h+arg_10]
0x1400066d1  add     rsp, 260h
0x1400066d8  pop     r15
0x1400066da  pop     r14
0x1400066dc  pop     rdi
0x1400066dd  pop     rsi
0x1400066de  pop     rbp
0x1400066df  retn
0x1400066e0  mov     rcx, [rbp+188h]; this
0x1400066e7  mov     edx, 0A0Bh; void *
0x1400066ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400066f2  mov     rcx, [rbp+188h]; this
0x1400066f9  mov     edx, 0A0Bh; void *
0x1400066fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006704  mov     rcx, [rbp+188h]; this
0x14000670b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140006711  mov     rcx, [rbp+188h]; this
0x140006718  mov     edx, 0A15h; void *
0x14000671d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006723  mov     rcx, [rbp+188h]; this
0x14000672a  mov     edx, 0A0Bh; void *
0x14000672f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006735  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000673b  mov     rcx, [rbp+188h]; this
0x140006742  mov     edx, 0A0Bh; void *
0x140006747  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000674d  mov     rcx, [rbp+188h]; this
0x140006754  mov     edx, 0A0Bh; void *
0x140006759  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000675f  mov     rcx, [rbp+188h]; this
0x140006766  mov     edx, 0A15h; void *
0x14000676b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006771  mov     rcx, [rbp+188h]; this
0x140006778  mov     edx, 0A15h; void *
0x14000677d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
