# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006598`
- end: `0x180006989`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180006d64`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x180005428`
- `0x180006598`
- `0x180006990`
- `0x180006fdc`
- `0x180007930`
- `0x1800088e0`
- `0x18000a0f4`
- `0x18000ac20`
- `0x18000b0ac`
- `0x18000bf6c`
- `0x18000bf7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000689e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000689e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000686b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000686b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000660f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000660f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800065d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068b4`

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
0x180006598  mov     [rsp-8+arg_10], rbx
0x18000659d  push    rbp
0x18000659e  push    rsi
0x18000659f  push    rdi
0x1800065a0  push    r14
0x1800065a2  push    r15
0x1800065a4  lea     rbp, [rsp-160h]
0x1800065ac  sub     rsp, 260h
0x1800065b3  mov     rax, cs:__security_cookie
0x1800065ba  xor     rax, rsp
0x1800065bd  mov     [rbp+180h+var_30], rax
0x1800065c4  mov     r15, rdx
0x1800065c7  mov     qword ptr [rdx], 0
0x1800065ce  mov     rbx, rcx
0x1800065d1  call    cs:__imp_GetCurrentProcessId
0x1800065d7  mov     r14d, 130h
0x1800065dd  mov     [rsp+280h+var_258], rbx
0x1800065e2  mov     r9d, eax
0x1800065e5  mov     [rsp+280h+var_260], r14d; int
0x1800065ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800065f1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800065f6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800065fa  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800065ff  mov     r9d, 1F0001h; dwDesiredAccess
0x180006605  lea     rdx, [rsp+280h+Name]; lpName
0x18000660a  xor     r8d, r8d; dwFlags
0x18000660d  xor     ecx, ecx; lpMutexAttributes
0x18000660f  call    cs:__imp_CreateMutexExW
0x180006615  mov     rbx, rax
0x180006618  test    rax, rax
0x18000661b  jnz     short loc_180006627
0x18000661d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006622  jmp     loc_1800068C0
0x180006627  xor     r8d, r8d; bAlertable
0x18000662a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000662d  mov     rcx, rbx; hHandle
0x180006630  call    cs:__imp_WaitForSingleObjectEx
0x180006636  cmp     eax, 102h
0x18000663b  jz      short loc_18000664D
0x18000663d  test    eax, 0FFFFFF7Fh
0x180006642  jnz     loc_18000690A
0x180006648  mov     rdi, rbx
0x18000664b  jmp     short loc_18000664F
0x18000664d  xor     edi, edi
0x18000664f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006654  mov     [rsp+280h+hObject], 0
0x18000665d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006662  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180006667  mov     esi, eax
0x180006669  test    eax, eax
0x18000666b  jns     short loc_1800066EC
0x18000666d  mov     rcx, [rbp+188h]; this
0x180006674  lea     r8, aWil; "wil"
0x18000667b  mov     r9d, eax; char *
0x18000667e  mov     edx, 66h ; 'f'; void *
0x180006683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006688  mov     rcx, [rbp+188h]; this
0x18000668f  lea     r8, aWil; "wil"
0x180006696  mov     r9d, esi; char *
0x180006699  mov     edx, 6Fh ; 'o'; void *
0x18000669e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066a3  mov     rcx, [rbp+188h]; this
0x1800066aa  lea     r8, aWil; "wil"
0x1800066b1  mov     r9d, esi; char *
0x1800066b4  mov     edx, 12Eh; void *
0x1800066b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066be  test    rdi, rdi
0x1800066c1  jz      short loc_1800066D4
0x1800066c3  mov     rcx, rdi; hMutex
0x1800066c6  call    cs:__imp_ReleaseMutex
0x1800066cc  test    eax, eax
0x1800066ce  jz      loc_180006917
0x1800066d4  mov     rcx, rbx; hObject
0x1800066d7  call    cs:__imp_CloseHandle
0x1800066dd  test    eax, eax
0x1800066df  jz      loc_180006929
0x1800066e5  mov     eax, esi
0x1800066e7  jmp     loc_1800068C0
0x1800066ec  mov     rax, [rsp+280h+hObject]
0x1800066f1  lea     rcx, ds:0[rax*4]
0x1800066f9  test    rcx, rcx
0x1800066fc  jz      short loc_18000670C
0x1800066fe  mov     [r15], rcx
0x180006701  mov     eax, [rcx]
0x180006703  inc     eax
0x180006705  mov     [rcx], eax
0x180006707  jmp     loc_180006896
0x18000670c  mov     rdx, r14; dwBytes
0x18000670f  mov     qword ptr [r15], 0
0x180006716  mov     ecx, 8; dwFlags
0x18000671b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006720  mov     r14, rax
0x180006723  test    rax, rax
0x180006726  jnz     short loc_18000674D
0x180006728  mov     rcx, [rbp+188h]; this
0x18000672f  lea     r8, aWil; "wil"
0x180006736  mov     esi, 8007000Eh
0x18000673b  mov     edx, 14Bh; void *
0x180006740  mov     r9d, esi; char *
0x180006743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006748  jmp     loc_1800067DF
0x18000674d  xorps   xmm0, xmm0
0x180006750  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006756  test    r14b, 3
0x18000675a  jnz     loc_18000693B
0x180006760  mov     r9, r14
0x180006763  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180006768  shr     r9, 2; unsigned __int64
0x18000676c  lea     rcx, [rsp+280h+hObject]; this
0x180006771  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180006776  mov     esi, eax
0x180006778  test    eax, eax
0x18000677a  jns     loc_180006826
0x180006780  mov     rcx, [rbp+188h]; this
0x180006787  lea     r8, aWil; "wil"
0x18000678e  mov     r9d, eax; char *
0x180006791  mov     edx, 14Eh; void *
0x180006796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000679b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800067a0  test    rcx, rcx
0x1800067a3  jz      short loc_1800067B3
0x1800067a5  call    cs:__imp_CloseHandle
0x1800067ab  test    eax, eax
0x1800067ad  jz      loc_180006941
0x1800067b3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800067b8  test    rcx, rcx
0x1800067bb  jz      short loc_1800067CB
0x1800067bd  call    cs:__imp_CloseHandle
0x1800067c3  test    eax, eax
0x1800067c5  jz      loc_180006953
0x1800067cb  call    cs:__imp_GetProcessHeap
0x1800067d1  mov     r8, r14; lpMem
0x1800067d4  xor     edx, edx; dwFlags
0x1800067d6  mov     rcx, rax; hHeap
0x1800067d9  call    cs:__imp_HeapFree
0x1800067df  mov     rcx, [rbp+188h]; this
0x1800067e6  lea     r8, aWil; "wil"
0x1800067ed  mov     r9d, esi; char *
0x1800067f0  mov     edx, 137h; void *
0x1800067f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067fa  test    rdi, rdi
0x1800067fd  jz      short loc_180006810
0x1800067ff  mov     rcx, rdi; hMutex
0x180006802  call    cs:__imp_ReleaseMutex
0x180006808  test    eax, eax
0x18000680a  jz      loc_180006965
0x180006810  mov     rcx, rbx; hObject
0x180006813  call    cs:__imp_CloseHandle
0x180006819  test    eax, eax
0x18000681b  jz      loc_1800068F8
0x180006821  jmp     loc_1800066E5
0x180006826  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000682b  lea     rcx, [r14+28h]; void *
0x18000682f  mov     dword ptr [r14], 1
0x180006836  xor     edx, edx; Val
0x180006838  mov     [r14+8], rbx
0x18000683c  mov     r8d, 108h; Size
0x180006842  movdqu  xmmword ptr [r14+10h], xmm0
0x180006848  call    memset_0
0x18000684d  xor     eax, eax
0x18000684f  lea     rcx, [r14+28h]; this
0x180006853  mov     [r14+20h], rax
0x180006857  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000685c  lea     rbx, [r14+0E8h]
0x180006863  xor     r8d, r8d; Flags
0x180006866  mov     rcx, rbx; lpCriticalSection
0x180006869  xor     edx, edx; dwSpinCount
0x18000686b  call    cs:__imp_InitializeCriticalSectionEx
0x180006871  mov     qword ptr [rbx+28h], 0
0x180006879  mov     qword ptr [rbx+30h], 0
0x180006881  mov     qword ptr [rbx+38h], 0
0x180006889  mov     qword ptr [rbx+40h], 0
0x180006891  xor     ebx, ebx
0x180006893  mov     [r15], r14
0x180006896  test    rdi, rdi
0x180006899  jz      short loc_1800068AC
0x18000689b  mov     rcx, rdi; hMutex
0x18000689e  call    cs:__imp_ReleaseMutex
0x1800068a4  test    eax, eax
0x1800068a6  jz      loc_180006977
0x1800068ac  test    rbx, rbx
0x1800068af  jz      short loc_1800068BE
0x1800068b1  mov     rcx, rbx; hObject
0x1800068b4  call    cs:__imp_CloseHandle
0x1800068ba  test    eax, eax
0x1800068bc  jz      short loc_1800068E6
0x1800068be  xor     eax, eax
0x1800068c0  mov     rcx, [rbp+180h+var_30]
0x1800068c7  xor     rcx, rsp; StackCookie
0x1800068ca  call    __security_check_cookie
0x1800068cf  mov     rbx, [rsp+280h+arg_10]
0x1800068d7  add     rsp, 260h
0x1800068de  pop     r15
0x1800068e0  pop     r14
0x1800068e2  pop     rdi
0x1800068e3  pop     rsi
0x1800068e4  pop     rbp
0x1800068e5  retn
0x1800068e6  mov     rcx, [rbp+188h]; this
0x1800068ed  mov     edx, 0A0Bh; void *
0x1800068f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800068f8  mov     rcx, [rbp+188h]; this
0x1800068ff  mov     edx, 0A0Bh; void *
0x180006904  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000690a  mov     rcx, [rbp+188h]; this
0x180006911  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006917  mov     rcx, [rbp+188h]; this
0x18000691e  mov     edx, 0A15h; void *
0x180006923  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006929  mov     rcx, [rbp+188h]; this
0x180006930  mov     edx, 0A0Bh; void *
0x180006935  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000693b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006941  mov     rcx, [rbp+188h]; this
0x180006948  mov     edx, 0A0Bh; void *
0x18000694d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006953  mov     rcx, [rbp+188h]; this
0x18000695a  mov     edx, 0A0Bh; void *
0x18000695f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006965  mov     rcx, [rbp+188h]; this
0x18000696c  mov     edx, 0A15h; void *
0x180006971  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006977  mov     rcx, [rbp+188h]; this
0x18000697e  mov     edx, 0A15h; void *
0x180006983  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
