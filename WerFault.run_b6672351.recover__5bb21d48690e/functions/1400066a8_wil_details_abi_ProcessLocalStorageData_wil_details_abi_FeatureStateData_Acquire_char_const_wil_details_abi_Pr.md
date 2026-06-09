# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400066a8`
- end: `0x140006aa8`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140006cec`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140005794`
- `0x140005f18`
- `0x1400066a8`
- `0x140006ab0`
- `0x140006f44`
- `0x140007d58`
- `0x140008ce8`
- `0x14000aad4`
- `0x14000b580`
- `0x14000bacc`
- `0x14000c720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000674c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000674c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006725`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400067ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006909`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400069da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400067ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006909`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400069da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006997`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006997`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400066e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400066e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069f6`

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
0x1400066a8  mov     [rsp-8+arg_10], rbx
0x1400066ad  push    rbp
0x1400066ae  push    rsi
0x1400066af  push    rdi
0x1400066b0  push    r14
0x1400066b2  push    r15
0x1400066b4  lea     rbp, [rsp-160h]
0x1400066bc  sub     rsp, 260h
0x1400066c3  mov     rax, cs:__security_cookie
0x1400066ca  xor     rax, rsp
0x1400066cd  mov     [rbp+180h+var_30], rax
0x1400066d4  mov     r15, rdx
0x1400066d7  mov     qword ptr [rdx], 0
0x1400066de  mov     rbx, rcx
0x1400066e1  call    cs:__imp_GetCurrentProcessId
0x1400066e8  nop     dword ptr [rax+rax+00h]
0x1400066ed  mov     r14d, 130h
0x1400066f3  mov     [rsp+280h+var_258], rbx
0x1400066f8  mov     r9d, eax
0x1400066fb  mov     [rsp+280h+var_260], r14d; int
0x140006700  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140006707  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000670c  lea     edx, [r14-2Ch]; unsigned __int64
0x140006710  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140006715  mov     r9d, 1F0001h; dwDesiredAccess
0x14000671b  lea     rdx, [rsp+280h+Name]; lpName
0x140006720  xor     r8d, r8d; dwFlags
0x140006723  xor     ecx, ecx; lpMutexAttributes
0x140006725  call    cs:__imp_CreateMutexExW
0x14000672c  nop     dword ptr [rax+rax+00h]
0x140006731  mov     rbx, rax
0x140006734  test    rax, rax
0x140006737  jnz     short loc_140006743
0x140006739  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000673e  jmp     loc_140006A08
0x140006743  xor     r8d, r8d; bAlertable
0x140006746  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140006749  mov     rcx, rbx; hHandle
0x14000674c  call    cs:__imp_WaitForSingleObjectEx
0x140006753  nop     dword ptr [rax+rax+00h]
0x140006758  cmp     eax, 102h
0x14000675d  jz      short loc_14000676F
0x14000675f  test    eax, 0FFFFFF7Fh
0x140006764  jnz     loc_140006A53
0x14000676a  mov     rdi, rbx
0x14000676d  jmp     short loc_140006771
0x14000676f  xor     edi, edi
0x140006771  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140006776  mov     [rsp+280h+var_250], 0
0x14000677f  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140006784  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140006789  mov     esi, eax
0x14000678b  test    eax, eax
0x14000678d  jns     loc_14000681E
0x140006793  mov     rcx, [rbp+188h]; this
0x14000679a  lea     r8, aWil; "wil"
0x1400067a1  mov     r9d, eax; char *
0x1400067a4  mov     edx, 66h ; 'f'; void *
0x1400067a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067ae  mov     rcx, [rbp+188h]; this
0x1400067b5  lea     r8, aWil; "wil"
0x1400067bc  mov     r9d, esi; char *
0x1400067bf  mov     edx, 6Fh ; 'o'; void *
0x1400067c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067c9  mov     rcx, [rbp+188h]; this
0x1400067d0  lea     r8, aWil; "wil"
0x1400067d7  mov     r9d, esi; char *
0x1400067da  mov     edx, 12Eh; void *
0x1400067df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067e4  test    rdi, rdi
0x1400067e7  jz      short loc_140006800
0x1400067e9  mov     rcx, rdi; hMutex
0x1400067ec  call    cs:__imp_ReleaseMutex
0x1400067f3  nop     dword ptr [rax+rax+00h]
0x1400067f8  test    eax, eax
0x1400067fa  jz      loc_140006A60
0x140006800  mov     rcx, rbx; hObject
0x140006803  call    cs:__imp_CloseHandle
0x14000680a  nop     dword ptr [rax+rax+00h]
0x14000680f  test    eax, eax
0x140006811  jz      loc_140006A72
0x140006817  mov     eax, esi
0x140006819  jmp     loc_140006A08
0x14000681e  mov     rax, [rsp+280h+var_250]
0x140006823  lea     rcx, ds:0[rax*4]
0x14000682b  test    rcx, rcx
0x14000682e  jz      short loc_14000683E
0x140006830  mov     [r15], rcx
0x140006833  mov     eax, [rcx]
0x140006835  inc     eax
0x140006837  mov     [rcx], eax
0x140006839  jmp     loc_1400069D2
0x14000683e  mov     rdx, r14; dwBytes
0x140006841  mov     qword ptr [r15], 0
0x140006848  mov     ecx, 8; dwFlags
0x14000684d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006852  mov     r14, rax
0x140006855  test    rax, rax
0x140006858  jnz     short loc_14000687C
0x14000685a  mov     rcx, [rbp+188h]; this
0x140006861  lea     r8, aWil; "wil"
0x140006868  mov     esi, 8007000Eh
0x14000686d  mov     edx, 14Bh; void *
0x140006872  mov     r9d, esi; char *
0x140006875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000687a  jmp     short loc_1400068E6
0x14000687c  xorps   xmm0, xmm0
0x14000687f  lea     rdx, [rsp+280h+Name]; wchar_t *
0x140006884  mov     r8, r14; void *
0x140006887  lea     rcx, [rsp+280h+var_250]; this
0x14000688c  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140006892  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEB_WPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(wchar_t const *,void *)
0x140006897  mov     esi, eax
0x140006899  test    eax, eax
0x14000689b  jns     loc_140006939
0x1400068a1  mov     rcx, [rbp+188h]; this
0x1400068a8  lea     r8, aWil; "wil"
0x1400068af  mov     r9d, eax; char *
0x1400068b2  mov     edx, 14Eh; void *
0x1400068b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400068bc  lea     rcx, [rsp+280h+var_250]; this
0x1400068c1  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400068c6  call    cs:__imp_GetProcessHeap
0x1400068cd  nop     dword ptr [rax+rax+00h]
0x1400068d2  mov     r8, r14; lpMem
0x1400068d5  xor     edx, edx; dwFlags
0x1400068d7  mov     rcx, rax; hHeap
0x1400068da  call    cs:__imp_HeapFree
0x1400068e1  nop     dword ptr [rax+rax+00h]
0x1400068e6  mov     rcx, [rbp+188h]; this
0x1400068ed  lea     r8, aWil; "wil"
0x1400068f4  mov     r9d, esi; char *
0x1400068f7  mov     edx, 137h; void *
0x1400068fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006901  test    rdi, rdi
0x140006904  jz      short loc_14000691D
0x140006906  mov     rcx, rdi; hMutex
0x140006909  call    cs:__imp_ReleaseMutex
0x140006910  nop     dword ptr [rax+rax+00h]
0x140006915  test    eax, eax
0x140006917  jz      loc_140006A84
0x14000691d  mov     rcx, rbx; hObject
0x140006920  call    cs:__imp_CloseHandle
0x140006927  nop     dword ptr [rax+rax+00h]
0x14000692c  test    eax, eax
0x14000692e  jz      loc_140006A41
0x140006934  jmp     loc_140006817
0x140006939  mov     rax, [rsp+280h+var_250]
0x14000693e  lea     rcx, [r14+28h]; void *
0x140006942  mov     [r14+10h], rax
0x140006946  xor     edx, edx; Val
0x140006948  mov     rax, [rsp+280h+var_250+8]
0x14000694d  mov     r8d, 108h; Size
0x140006953  mov     [r14+18h], rax
0x140006957  mov     dword ptr [r14], 1
0x14000695e  mov     [r14+8], rbx
0x140006962  mov     [rsp+280h+var_250], 0
0x14000696b  mov     [rsp+280h+var_250+8], 0
0x140006974  call    memset_0
0x140006979  xor     eax, eax
0x14000697b  lea     rcx, [r14+28h]; this
0x14000697f  mov     [r14+20h], rax
0x140006983  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006988  lea     rbx, [r14+0E8h]
0x14000698f  xor     r8d, r8d; Flags
0x140006992  mov     rcx, rbx; lpCriticalSection
0x140006995  xor     edx, edx; dwSpinCount
0x140006997  call    cs:__imp_InitializeCriticalSectionEx
0x14000699e  nop     dword ptr [rax+rax+00h]
0x1400069a3  mov     qword ptr [rbx+28h], 0
0x1400069ab  lea     rcx, [rsp+280h+var_250]; this
0x1400069b0  mov     qword ptr [rbx+30h], 0
0x1400069b8  mov     qword ptr [rbx+38h], 0
0x1400069c0  mov     qword ptr [rbx+40h], 0
0x1400069c8  mov     [r15], r14
0x1400069cb  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400069d0  xor     ebx, ebx
0x1400069d2  test    rdi, rdi
0x1400069d5  jz      short loc_1400069EE
0x1400069d7  mov     rcx, rdi; hMutex
0x1400069da  call    cs:__imp_ReleaseMutex
0x1400069e1  nop     dword ptr [rax+rax+00h]
0x1400069e6  test    eax, eax
0x1400069e8  jz      loc_140006A96
0x1400069ee  test    rbx, rbx
0x1400069f1  jz      short loc_140006A06
0x1400069f3  mov     rcx, rbx; hObject
0x1400069f6  call    cs:__imp_CloseHandle
0x1400069fd  nop     dword ptr [rax+rax+00h]
0x140006a02  test    eax, eax
0x140006a04  jz      short loc_140006A2F
0x140006a06  xor     eax, eax
0x140006a08  mov     rcx, [rbp+180h+var_30]
0x140006a0f  xor     rcx, rsp; StackCookie
0x140006a12  call    __security_check_cookie
0x140006a17  mov     rbx, [rsp+280h+arg_10]
0x140006a1f  add     rsp, 260h
0x140006a26  pop     r15
0x140006a28  pop     r14
0x140006a2a  pop     rdi
0x140006a2b  pop     rsi
0x140006a2c  pop     rbp
0x140006a2d  retn
0x140006a2f  mov     rcx, [rbp+188h]; this
0x140006a36  mov     edx, 0A0Bh; void *
0x140006a3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a41  mov     rcx, [rbp+188h]; this
0x140006a48  mov     edx, 0A0Bh; void *
0x140006a4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a53  mov     rcx, [rbp+188h]; this
0x140006a5a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140006a60  mov     rcx, [rbp+188h]; this
0x140006a67  mov     edx, 0A15h; void *
0x140006a6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a72  mov     rcx, [rbp+188h]; this
0x140006a79  mov     edx, 0A0Bh; void *
0x140006a7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a84  mov     rcx, [rbp+188h]; this
0x140006a8b  mov     edx, 0A15h; void *
0x140006a90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006a96  mov     rcx, [rbp+188h]; this
0x140006a9d  mov     edx, 0A15h; void *
0x140006aa2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
