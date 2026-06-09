# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400062cc`
- end: `0x14000669f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140007fd4`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140005f18`
- `0x1400062cc`
- `0x140006ab0`
- `0x140006f44`
- `0x140007d58`
- `0x140008ce8`
- `0x14000aad4`
- `0x14000b580`
- `0x14000bacc`
- `0x14000c720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006371`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006371`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000634a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000634a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006411`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000652e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400065d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006411`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000652e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400065d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400064ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400064ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400064eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400064eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006305`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400065ed`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x1400062cc  mov     [rsp-8+arg_10], rbx
0x1400062d1  push    rbp
0x1400062d2  push    rsi
0x1400062d3  push    rdi
0x1400062d4  push    r14
0x1400062d6  push    r15
0x1400062d8  lea     rbp, [rsp-160h]
0x1400062e0  sub     rsp, 260h
0x1400062e7  mov     rax, cs:__security_cookie
0x1400062ee  xor     rax, rsp
0x1400062f1  mov     [rbp+180h+var_30], rax
0x1400062f8  mov     r15, rdx
0x1400062fb  mov     qword ptr [rdx], 0
0x140006302  mov     rbx, rcx
0x140006305  call    cs:__imp_GetCurrentProcessId
0x14000630c  nop     dword ptr [rax+rax+00h]
0x140006311  mov     r14d, 78h ; 'x'
0x140006317  mov     [rsp+280h+var_258], rbx
0x14000631c  mov     r9d, eax
0x14000631f  mov     [rsp+280h+var_260], r14d; int
0x140006324  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000632b  mov     edx, 104h; unsigned __int64
0x140006330  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140006335  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000633a  mov     r9d, 1F0001h; dwDesiredAccess
0x140006340  lea     rdx, [rsp+280h+Name]; lpName
0x140006345  xor     r8d, r8d; dwFlags
0x140006348  xor     ecx, ecx; lpMutexAttributes
0x14000634a  call    cs:__imp_CreateMutexExW
0x140006351  nop     dword ptr [rax+rax+00h]
0x140006356  mov     rbx, rax
0x140006359  test    rax, rax
0x14000635c  jnz     short loc_140006368
0x14000635e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006363  jmp     loc_1400065FF
0x140006368  xor     r8d, r8d; bAlertable
0x14000636b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000636e  mov     rcx, rbx; hHandle
0x140006371  call    cs:__imp_WaitForSingleObjectEx
0x140006378  nop     dword ptr [rax+rax+00h]
0x14000637d  cmp     eax, 102h
0x140006382  jz      short loc_140006394
0x140006384  test    eax, 0FFFFFF7Fh
0x140006389  jnz     loc_14000664A
0x14000638f  mov     rdi, rbx
0x140006392  jmp     short loc_140006396
0x140006394  xor     edi, edi
0x140006396  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14000639b  mov     [rsp+280h+var_250], 0
0x1400063a4  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400063a9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1400063ae  mov     esi, eax
0x1400063b0  test    eax, eax
0x1400063b2  jns     loc_140006443
0x1400063b8  mov     rcx, [rbp+188h]; this
0x1400063bf  lea     r8, aWil; "wil"
0x1400063c6  mov     r9d, eax; char *
0x1400063c9  mov     edx, 66h ; 'f'; void *
0x1400063ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400063d3  mov     rcx, [rbp+188h]; this
0x1400063da  lea     r8, aWil; "wil"
0x1400063e1  mov     r9d, esi; char *
0x1400063e4  mov     edx, 6Fh ; 'o'; void *
0x1400063e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400063ee  mov     rcx, [rbp+188h]; this
0x1400063f5  lea     r8, aWil; "wil"
0x1400063fc  mov     r9d, esi; char *
0x1400063ff  mov     edx, 12Eh; void *
0x140006404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006409  test    rdi, rdi
0x14000640c  jz      short loc_140006425
0x14000640e  mov     rcx, rdi; hMutex
0x140006411  call    cs:__imp_ReleaseMutex
0x140006418  nop     dword ptr [rax+rax+00h]
0x14000641d  test    eax, eax
0x14000641f  jz      loc_140006657
0x140006425  mov     rcx, rbx; hObject
0x140006428  call    cs:__imp_CloseHandle
0x14000642f  nop     dword ptr [rax+rax+00h]
0x140006434  test    eax, eax
0x140006436  jz      loc_140006669
0x14000643c  mov     eax, esi
0x14000643e  jmp     loc_1400065FF
0x140006443  mov     rax, [rsp+280h+var_250]
0x140006448  lea     rcx, ds:0[rax*4]
0x140006450  test    rcx, rcx
0x140006453  jz      short loc_140006463
0x140006455  mov     [r15], rcx
0x140006458  mov     eax, [rcx]
0x14000645a  inc     eax
0x14000645c  mov     [rcx], eax
0x14000645e  jmp     loc_1400065C9
0x140006463  mov     rdx, r14; dwBytes
0x140006466  mov     qword ptr [r15], 0
0x14000646d  mov     ecx, 8; dwFlags
0x140006472  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006477  mov     r14, rax
0x14000647a  test    rax, rax
0x14000647d  jnz     short loc_1400064A1
0x14000647f  mov     rcx, [rbp+188h]; this
0x140006486  lea     r8, aWil; "wil"
0x14000648d  mov     esi, 8007000Eh
0x140006492  mov     edx, 14Bh; void *
0x140006497  mov     r9d, esi; char *
0x14000649a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000649f  jmp     short loc_14000650B
0x1400064a1  xorps   xmm0, xmm0
0x1400064a4  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1400064a9  mov     r8, r14; void *
0x1400064ac  lea     rcx, [rsp+280h+var_250]; this
0x1400064b1  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1400064b7  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEB_WPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(wchar_t const *,void *)
0x1400064bc  mov     esi, eax
0x1400064be  test    eax, eax
0x1400064c0  jns     loc_14000655E
0x1400064c6  mov     rcx, [rbp+188h]; this
0x1400064cd  lea     r8, aWil; "wil"
0x1400064d4  mov     r9d, eax; char *
0x1400064d7  mov     edx, 14Eh; void *
0x1400064dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064e1  lea     rcx, [rsp+280h+var_250]; this
0x1400064e6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400064eb  call    cs:__imp_GetProcessHeap
0x1400064f2  nop     dword ptr [rax+rax+00h]
0x1400064f7  mov     r8, r14; lpMem
0x1400064fa  xor     edx, edx; dwFlags
0x1400064fc  mov     rcx, rax; hHeap
0x1400064ff  call    cs:__imp_HeapFree
0x140006506  nop     dword ptr [rax+rax+00h]
0x14000650b  mov     rcx, [rbp+188h]; this
0x140006512  lea     r8, aWil; "wil"
0x140006519  mov     r9d, esi; char *
0x14000651c  mov     edx, 137h; void *
0x140006521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006526  test    rdi, rdi
0x140006529  jz      short loc_140006542
0x14000652b  mov     rcx, rdi; hMutex
0x14000652e  call    cs:__imp_ReleaseMutex
0x140006535  nop     dword ptr [rax+rax+00h]
0x14000653a  test    eax, eax
0x14000653c  jz      loc_14000667B
0x140006542  mov     rcx, rbx; hObject
0x140006545  call    cs:__imp_CloseHandle
0x14000654c  nop     dword ptr [rax+rax+00h]
0x140006551  test    eax, eax
0x140006553  jz      loc_140006638
0x140006559  jmp     loc_14000643C
0x14000655e  mov     rax, [rsp+280h+var_250]
0x140006563  lea     rcx, [r14+22h]; void *
0x140006567  xor     edx, edx; Val
0x140006569  mov     [r14+10h], rax
0x14000656d  mov     rax, [rsp+280h+var_250+8]
0x140006572  mov     dword ptr [r14], 1
0x140006579  mov     [r14+8], rbx
0x14000657d  lea     r8d, [rdx+56h]; Size
0x140006581  mov     [rsp+280h+var_250], 0
0x14000658a  mov     [r14+18h], rax
0x14000658e  mov     [rsp+280h+var_250+8], 0
0x140006597  call    memset_0
0x14000659c  xor     edx, edx; Val
0x14000659e  mov     word ptr [r14+20h], 58h ; 'X'
0x1400065a5  lea     rcx, [r14+28h]; void *
0x1400065a9  mov     dword ptr [r14+24h], 1
0x1400065b1  lea     r8d, [rdx+50h]; Size
0x1400065b5  call    memset_0
0x1400065ba  lea     rcx, [rsp+280h+var_250]; this
0x1400065bf  mov     [r15], r14
0x1400065c2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400065c7  xor     ebx, ebx
0x1400065c9  test    rdi, rdi
0x1400065cc  jz      short loc_1400065E5
0x1400065ce  mov     rcx, rdi; hMutex
0x1400065d1  call    cs:__imp_ReleaseMutex
0x1400065d8  nop     dword ptr [rax+rax+00h]
0x1400065dd  test    eax, eax
0x1400065df  jz      loc_14000668D
0x1400065e5  test    rbx, rbx
0x1400065e8  jz      short loc_1400065FD
0x1400065ea  mov     rcx, rbx; hObject
0x1400065ed  call    cs:__imp_CloseHandle
0x1400065f4  nop     dword ptr [rax+rax+00h]
0x1400065f9  test    eax, eax
0x1400065fb  jz      short loc_140006626
0x1400065fd  xor     eax, eax
0x1400065ff  mov     rcx, [rbp+180h+var_30]
0x140006606  xor     rcx, rsp; StackCookie
0x140006609  call    __security_check_cookie
0x14000660e  mov     rbx, [rsp+280h+arg_10]
0x140006616  add     rsp, 260h
0x14000661d  pop     r15
0x14000661f  pop     r14
0x140006621  pop     rdi
0x140006622  pop     rsi
0x140006623  pop     rbp
0x140006624  retn
0x140006626  mov     rcx, [rbp+188h]; this
0x14000662d  mov     edx, 0A0Bh; void *
0x140006632  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006638  mov     rcx, [rbp+188h]; this
0x14000663f  mov     edx, 0A0Bh; void *
0x140006644  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000664a  mov     rcx, [rbp+188h]; this
0x140006651  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140006657  mov     rcx, [rbp+188h]; this
0x14000665e  mov     edx, 0A15h; void *
0x140006663  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006669  mov     rcx, [rbp+188h]; this
0x140006670  mov     edx, 0A0Bh; void *
0x140006675  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000667b  mov     rcx, [rbp+188h]; this
0x140006682  mov     edx, 0A15h; void *
0x140006687  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000668d  mov     rcx, [rbp+188h]; this
0x140006694  mov     edx, 0A15h; void *
0x140006699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
