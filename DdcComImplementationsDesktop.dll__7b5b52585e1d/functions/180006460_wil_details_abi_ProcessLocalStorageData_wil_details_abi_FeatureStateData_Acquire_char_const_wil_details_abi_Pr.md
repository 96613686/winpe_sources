# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006460`
- end: `0x180006827`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180006b04`

## callees

- `0x1800016b0`
- `0x180002134`
- `0x1800057d0`
- `0x180006460`
- `0x180006830`
- `0x180006c94`
- `0x1800075b8`
- `0x1800081a8`
- `0x1800094d4`
- `0x180009fc8`
- `0x18000a31c`
- `0x18000aafc`
- `0x18000ab0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006499`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006499`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000667e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000667e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006670`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006670`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800064d7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800064d7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006709`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006709`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800064f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800064f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006579`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000673c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006579`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000673c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000658a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000664a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006752`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000658a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000664a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006752`

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
0x180006460  mov     [rsp-8+arg_10], rbx
0x180006465  push    rbp
0x180006466  push    rsi
0x180006467  push    rdi
0x180006468  push    r14
0x18000646a  push    r15
0x18000646c  lea     rbp, [rsp-160h]
0x180006474  sub     rsp, 260h
0x18000647b  mov     rax, cs:__security_cookie
0x180006482  xor     rax, rsp
0x180006485  mov     [rbp+180h+var_30], rax
0x18000648c  mov     r15, rdx
0x18000648f  mov     qword ptr [rdx], 0
0x180006496  mov     rbx, rcx
0x180006499  call    cs:__imp_GetCurrentProcessId
0x18000649f  mov     r14d, 130h
0x1800064a5  mov     [rsp+280h+var_258], rbx
0x1800064aa  mov     r9d, eax
0x1800064ad  mov     [rsp+280h+var_260], r14d; int
0x1800064b2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800064b9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800064be  lea     edx, [r14-2Ch]; unsigned __int64
0x1800064c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800064c7  mov     r9d, 1F0001h; dwDesiredAccess
0x1800064cd  lea     rdx, [rsp+280h+Name]; lpName
0x1800064d2  xor     r8d, r8d; dwFlags
0x1800064d5  xor     ecx, ecx; lpMutexAttributes
0x1800064d7  call    cs:__imp_CreateMutexExW
0x1800064dd  mov     rbx, rax
0x1800064e0  test    rax, rax
0x1800064e3  jnz     short loc_1800064EF
0x1800064e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800064ea  jmp     loc_18000675E
0x1800064ef  xor     r8d, r8d; bAlertable
0x1800064f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800064f5  mov     rcx, rbx; hHandle
0x1800064f8  call    cs:__imp_WaitForSingleObjectEx
0x1800064fe  cmp     eax, 102h
0x180006503  jz      short loc_180006515
0x180006505  test    eax, 0FFFFFF7Fh
0x18000650a  jnz     loc_1800067A8
0x180006510  mov     rdi, rbx
0x180006513  jmp     short loc_180006517
0x180006515  xor     edi, edi
0x180006517  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000651c  mov     [rsp+280h+hObject], 0
0x180006525  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000652a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000652f  mov     esi, eax
0x180006531  test    eax, eax
0x180006533  jns     short loc_18000659F
0x180006535  mov     rcx, [rbp+188h]; this
0x18000653c  mov     r9d, eax; char *
0x18000653f  mov     edx, 66h ; 'f'; void *
0x180006544  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006549  mov     rcx, [rbp+188h]; this
0x180006550  mov     r9d, esi; char *
0x180006553  mov     edx, 6Fh ; 'o'; void *
0x180006558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000655d  mov     rcx, [rbp+188h]; this
0x180006564  mov     r9d, esi; char *
0x180006567  mov     edx, 12Eh; void *
0x18000656c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006571  test    rdi, rdi
0x180006574  jz      short loc_180006587
0x180006576  mov     rcx, rdi; hMutex
0x180006579  call    cs:__imp_ReleaseMutex
0x18000657f  test    eax, eax
0x180006581  jz      loc_1800067B5
0x180006587  mov     rcx, rbx; hObject
0x18000658a  call    cs:__imp_CloseHandle
0x180006590  test    eax, eax
0x180006592  jz      loc_1800067C7
0x180006598  mov     eax, esi
0x18000659a  jmp     loc_18000675E
0x18000659f  mov     rax, [rsp+280h+hObject]
0x1800065a4  lea     rcx, ds:0[rax*4]
0x1800065ac  test    rcx, rcx
0x1800065af  jz      short loc_1800065BF
0x1800065b1  mov     [r15], rcx
0x1800065b4  mov     eax, [rcx]
0x1800065b6  inc     eax
0x1800065b8  mov     [rcx], eax
0x1800065ba  jmp     loc_180006734
0x1800065bf  mov     rdx, r14; dwBytes
0x1800065c2  mov     qword ptr [r15], 0
0x1800065c9  mov     ecx, 8; dwFlags
0x1800065ce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800065d3  mov     r14, rax
0x1800065d6  test    rax, rax
0x1800065d9  jnz     short loc_1800065F9
0x1800065db  mov     rcx, [rbp+188h]; this
0x1800065e2  mov     esi, 8007000Eh
0x1800065e7  mov     r9d, esi; char *
0x1800065ea  mov     edx, 14Bh; void *
0x1800065ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065f4  jmp     loc_180006684
0x1800065f9  xorps   xmm0, xmm0
0x1800065fc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006602  test    r14b, 3
0x180006606  jnz     loc_1800067D9
0x18000660c  mov     r9, r14
0x18000660f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006614  shr     r9, 2; unsigned __int64
0x180006618  lea     rcx, [rsp+280h+hObject]; this
0x18000661d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006622  mov     esi, eax
0x180006624  test    eax, eax
0x180006626  jns     loc_1800066C4
0x18000662c  mov     rcx, [rbp+188h]; this
0x180006633  mov     r9d, eax; char *
0x180006636  mov     edx, 14Eh; void *
0x18000663b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006640  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006645  test    rcx, rcx
0x180006648  jz      short loc_180006658
0x18000664a  call    cs:__imp_CloseHandle
0x180006650  test    eax, eax
0x180006652  jz      loc_1800067DF
0x180006658  mov     rcx, [rsp+280h+hObject]; hObject
0x18000665d  test    rcx, rcx
0x180006660  jz      short loc_180006670
0x180006662  call    cs:__imp_CloseHandle
0x180006668  test    eax, eax
0x18000666a  jz      loc_1800067F1
0x180006670  call    cs:__imp_GetProcessHeap
0x180006676  mov     r8, r14; lpMem
0x180006679  xor     edx, edx; dwFlags
0x18000667b  mov     rcx, rax; hHeap
0x18000667e  call    cs:__imp_HeapFree
0x180006684  mov     rcx, [rbp+188h]; this
0x18000668b  mov     r9d, esi; char *
0x18000668e  mov     edx, 137h; void *
0x180006693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006698  test    rdi, rdi
0x18000669b  jz      short loc_1800066AE
0x18000669d  mov     rcx, rdi; hMutex
0x1800066a0  call    cs:__imp_ReleaseMutex
0x1800066a6  test    eax, eax
0x1800066a8  jz      loc_180006803
0x1800066ae  mov     rcx, rbx; hObject
0x1800066b1  call    cs:__imp_CloseHandle
0x1800066b7  test    eax, eax
0x1800066b9  jz      loc_180006796
0x1800066bf  jmp     loc_180006598
0x1800066c4  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800066c9  lea     rcx, [r14+28h]; void *
0x1800066cd  mov     dword ptr [r14], 1
0x1800066d4  xor     edx, edx; Val
0x1800066d6  mov     [r14+8], rbx
0x1800066da  mov     r8d, 108h; Size
0x1800066e0  movdqu  xmmword ptr [r14+10h], xmm0
0x1800066e6  call    memset_0
0x1800066eb  xor     eax, eax
0x1800066ed  lea     rcx, [r14+28h]; this
0x1800066f1  mov     [r14+20h], rax
0x1800066f5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800066fa  lea     rbx, [r14+0E8h]
0x180006701  xor     r8d, r8d; Flags
0x180006704  mov     rcx, rbx; lpCriticalSection
0x180006707  xor     edx, edx; dwSpinCount
0x180006709  call    cs:__imp_InitializeCriticalSectionEx
0x18000670f  mov     qword ptr [rbx+28h], 0
0x180006717  mov     qword ptr [rbx+30h], 0
0x18000671f  mov     qword ptr [rbx+38h], 0
0x180006727  mov     qword ptr [rbx+40h], 0
0x18000672f  xor     ebx, ebx
0x180006731  mov     [r15], r14
0x180006734  test    rdi, rdi
0x180006737  jz      short loc_18000674A
0x180006739  mov     rcx, rdi; hMutex
0x18000673c  call    cs:__imp_ReleaseMutex
0x180006742  test    eax, eax
0x180006744  jz      loc_180006815
0x18000674a  test    rbx, rbx
0x18000674d  jz      short loc_18000675C
0x18000674f  mov     rcx, rbx; hObject
0x180006752  call    cs:__imp_CloseHandle
0x180006758  test    eax, eax
0x18000675a  jz      short loc_180006784
0x18000675c  xor     eax, eax
0x18000675e  mov     rcx, [rbp+180h+var_30]
0x180006765  xor     rcx, rsp; StackCookie
0x180006768  call    __security_check_cookie
0x18000676d  mov     rbx, [rsp+280h+arg_10]
0x180006775  add     rsp, 260h
0x18000677c  pop     r15
0x18000677e  pop     r14
0x180006780  pop     rdi
0x180006781  pop     rsi
0x180006782  pop     rbp
0x180006783  retn
0x180006784  mov     rcx, [rbp+188h]; this
0x18000678b  mov     edx, 0A0Bh; void *
0x180006790  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006796  mov     rcx, [rbp+188h]; this
0x18000679d  mov     edx, 0A0Bh; void *
0x1800067a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067a8  mov     rcx, [rbp+188h]; this
0x1800067af  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800067b5  mov     rcx, [rbp+188h]; this
0x1800067bc  mov     edx, 0A15h; void *
0x1800067c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067c7  mov     rcx, [rbp+188h]; this
0x1800067ce  mov     edx, 0A0Bh; void *
0x1800067d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067d9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800067df  mov     rcx, [rbp+188h]; this
0x1800067e6  mov     edx, 0A0Bh; void *
0x1800067eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067f1  mov     rcx, [rbp+188h]; this
0x1800067f8  mov     edx, 0A0Bh; void *
0x1800067fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006803  mov     rcx, [rbp+188h]; this
0x18000680a  mov     edx, 0A15h; void *
0x18000680f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006815  mov     rcx, [rbp+188h]; this
0x18000681c  mov     edx, 0A15h; void *
0x180006821  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
