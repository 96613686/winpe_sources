# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800072fc`
- end: `0x180007701`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1029`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007a3c`

## callees

- `0x180003400`
- `0x180004558`
- `0x18000633c`
- `0x180006a64`
- `0x1800072fc`
- `0x180007808`
- `0x180007dcc`
- `0x1800088b4`
- `0x180009a5c`
- `0x18000b470`
- `0x18000bf2c`
- `0x18000c49c`
- `0x18000ce74`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180007379`
- `KERNEL32!CreateMutexExW` at `0x180007379`
- `KERNEL32!GetCurrentProcessId` at `0x180007335`
- `KERNEL32!GetCurrentProcessId` at `0x180007335`
- `KERNEL32!GetProcessHeap` at `0x18000751a`
- `KERNEL32!GetProcessHeap` at `0x18000751a`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800073a0`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800073a0`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800075eb`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800075eb`
- `KERNEL32!ReleaseMutex` at `0x180007440`
- `KERNEL32!ReleaseMutex` at `0x18000755d`
- `KERNEL32!ReleaseMutex` at `0x18000762e`
- `KERNEL32!ReleaseMutex` at `0x180007440`
- `KERNEL32!ReleaseMutex` at `0x18000755d`
- `KERNEL32!ReleaseMutex` at `0x18000762e`
- `KERNEL32!HeapFree` at `0x18000752e`
- `KERNEL32!HeapFree` at `0x18000752e`
- `KERNEL32!CloseHandle` at `0x180007457`
- `KERNEL32!CloseHandle` at `0x180007574`
- `KERNEL32!CloseHandle` at `0x18000764a`
- `KERNEL32!CloseHandle` at `0x180007457`
- `KERNEL32!CloseHandle` at `0x180007574`
- `KERNEL32!CloseHandle` at `0x18000764a`

## pseudocode

```c
signed int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // r9
  void *v13; // rdi
  int ValueInternal; // eax
  unsigned int v15; // esi
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 304, a1);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, 3585, v11, v12);
    v13 = v7;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, v33, (bool *)v12);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (__int64)"wil", (const char *)(unsigned int)ValueInternal);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (__int64)"wil", (const char *)v15);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (__int64)"wil", (const char *)v15);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (__int64)"wil", (const char *)0x8007000ELL);
    goto LABEL_18;
  }
  *(_OWORD *)v33 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer(
          (wil::details_abi::SemaphoreValue *)v33,
          Name,
          (unsigned __int64)v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (__int64)"wil", (const char *)(unsigned int)v23);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (__int64)"wil", (const char *)v15);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v33[0];
  *((_QWORD *)v22 + 3) = v33[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v7;
  v33[0] = 0;
  v33[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
  v7 = 0;
LABEL_23:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x1800072fc  mov     [rsp-8+arg_10], rbx
0x180007301  push    rbp
0x180007302  push    rsi
0x180007303  push    rdi
0x180007304  push    r14
0x180007306  push    r15
0x180007308  lea     rbp, [rsp-160h]
0x180007310  sub     rsp, 260h
0x180007317  mov     rax, cs:__security_cookie
0x18000731e  xor     rax, rsp
0x180007321  mov     [rbp+180h+var_30], rax
0x180007328  mov     r15, rdx
0x18000732b  mov     qword ptr [rdx], 0
0x180007332  mov     rbx, rcx
0x180007335  call    cs:__imp_GetCurrentProcessId
0x18000733c  nop     dword ptr [rax+rax+00h]
0x180007341  mov     r14d, 130h
0x180007347  mov     [rsp+280h+var_258], rbx
0x18000734c  mov     r9d, eax
0x18000734f  mov     [rsp+280h+var_260], r14d; int
0x180007354  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000735b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007360  lea     edx, [r14-2Ch]; unsigned __int64
0x180007364  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007369  mov     r9d, 1F0001h; dwDesiredAccess
0x18000736f  lea     rdx, [rsp+280h+Name]; lpName
0x180007374  xor     r8d, r8d; dwFlags
0x180007377  xor     ecx, ecx; lpMutexAttributes
0x180007379  call    cs:__imp_CreateMutexExW
0x180007380  nop     dword ptr [rax+rax+00h]
0x180007385  mov     rbx, rax
0x180007388  test    rax, rax
0x18000738b  jnz     short loc_180007397
0x18000738d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007392  jmp     loc_18000765C
0x180007397  xor     r8d, r8d; bAlertable
0x18000739a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000739d  mov     rcx, rbx; hHandle
0x1800073a0  call    cs:__imp_WaitForSingleObjectEx
0x1800073a7  nop     dword ptr [rax+rax+00h]
0x1800073ac  cmp     eax, 102h
0x1800073b1  jz      short loc_1800073C3
0x1800073b3  test    eax, 0FFFFFF7Fh
0x1800073b8  jnz     loc_1800076A7
0x1800073be  mov     rdi, rbx
0x1800073c1  jmp     short loc_1800073C5
0x1800073c3  xor     edi, edi
0x1800073c5  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800073ca  mov     [rsp+280h+var_250], 0
0x1800073d3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800073d8  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800073dd  mov     esi, eax
0x1800073df  test    eax, eax
0x1800073e1  jns     loc_180007472
0x1800073e7  mov     rcx, [rbp+188h]; this
0x1800073ee  lea     r8, aWil; "wil"
0x1800073f5  mov     r9d, eax; char *
0x1800073f8  mov     edx, 66h ; 'f'; void *
0x1800073fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007402  mov     rcx, [rbp+188h]; this
0x180007409  lea     r8, aWil; "wil"
0x180007410  mov     r9d, esi; char *
0x180007413  mov     edx, 6Fh ; 'o'; void *
0x180007418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000741d  mov     rcx, [rbp+188h]; this
0x180007424  lea     r8, aWil; "wil"
0x18000742b  mov     r9d, esi; char *
0x18000742e  mov     edx, 12Eh; void *
0x180007433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007438  test    rdi, rdi
0x18000743b  jz      short loc_180007454
0x18000743d  mov     rcx, rdi; hMutex
0x180007440  call    cs:__imp_ReleaseMutex
0x180007447  nop     dword ptr [rax+rax+00h]
0x18000744c  test    eax, eax
0x18000744e  jz      loc_1800076B9
0x180007454  mov     rcx, rbx; hObject
0x180007457  call    cs:__imp_CloseHandle
0x18000745e  nop     dword ptr [rax+rax+00h]
0x180007463  test    eax, eax
0x180007465  jz      loc_1800076CB
0x18000746b  mov     eax, esi
0x18000746d  jmp     loc_18000765C
0x180007472  mov     rax, [rsp+280h+var_250]
0x180007477  lea     rcx, ds:0[rax*4]
0x18000747f  test    rcx, rcx
0x180007482  jz      short loc_180007492
0x180007484  mov     [r15], rcx
0x180007487  mov     eax, [rcx]
0x180007489  inc     eax
0x18000748b  mov     [rcx], eax
0x18000748d  jmp     loc_180007626
0x180007492  mov     rdx, r14; dwBytes
0x180007495  mov     qword ptr [r15], 0
0x18000749c  mov     ecx, 8; dwFlags
0x1800074a1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800074a6  mov     r14, rax
0x1800074a9  test    rax, rax
0x1800074ac  jnz     short loc_1800074D0
0x1800074ae  mov     rcx, [rbp+188h]; this
0x1800074b5  lea     r8, aWil; "wil"
0x1800074bc  mov     esi, 8007000Eh
0x1800074c1  mov     edx, 14Bh; void *
0x1800074c6  mov     r9d, esi; char *
0x1800074c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074ce  jmp     short loc_18000753A
0x1800074d0  xorps   xmm0, xmm0
0x1800074d3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800074d8  mov     r8, r14; void *
0x1800074db  lea     rcx, [rsp+280h+var_250]; this
0x1800074e0  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800074e6  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800074eb  mov     esi, eax
0x1800074ed  test    eax, eax
0x1800074ef  jns     loc_18000758D
0x1800074f5  mov     rcx, [rbp+188h]; this
0x1800074fc  lea     r8, aWil; "wil"
0x180007503  mov     r9d, eax; char *
0x180007506  mov     edx, 14Eh; void *
0x18000750b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007510  lea     rcx, [rsp+280h+var_250]; this
0x180007515  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000751a  call    cs:__imp_GetProcessHeap
0x180007521  nop     dword ptr [rax+rax+00h]
0x180007526  mov     r8, r14; lpMem
0x180007529  xor     edx, edx; dwFlags
0x18000752b  mov     rcx, rax; hHeap
0x18000752e  call    cs:__imp_HeapFree
0x180007535  nop     dword ptr [rax+rax+00h]
0x18000753a  mov     rcx, [rbp+188h]; this
0x180007541  lea     r8, aWil; "wil"
0x180007548  mov     r9d, esi; char *
0x18000754b  mov     edx, 137h; void *
0x180007550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007555  test    rdi, rdi
0x180007558  jz      short loc_180007571
0x18000755a  mov     rcx, rdi; hMutex
0x18000755d  call    cs:__imp_ReleaseMutex
0x180007564  nop     dword ptr [rax+rax+00h]
0x180007569  test    eax, eax
0x18000756b  jz      loc_1800076DD
0x180007571  mov     rcx, rbx; hObject
0x180007574  call    cs:__imp_CloseHandle
0x18000757b  nop     dword ptr [rax+rax+00h]
0x180007580  test    eax, eax
0x180007582  jz      loc_180007695
0x180007588  jmp     loc_18000746B
0x18000758d  mov     rax, [rsp+280h+var_250]
0x180007592  lea     rcx, [r14+28h]; void *
0x180007596  mov     [r14+10h], rax
0x18000759a  xor     edx, edx; Val
0x18000759c  mov     rax, [rsp+280h+var_250+8]
0x1800075a1  mov     r8d, 108h; Size
0x1800075a7  mov     [r14+18h], rax
0x1800075ab  mov     dword ptr [r14], 1
0x1800075b2  mov     [r14+8], rbx
0x1800075b6  mov     [rsp+280h+var_250], 0
0x1800075bf  mov     [rsp+280h+var_250+8], 0
0x1800075c8  call    memset_0
0x1800075cd  xor     eax, eax
0x1800075cf  lea     rcx, [r14+28h]; this
0x1800075d3  mov     [r14+20h], rax
0x1800075d7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800075dc  lea     rbx, [r14+0E8h]
0x1800075e3  xor     r8d, r8d; Flags
0x1800075e6  mov     rcx, rbx; lpCriticalSection
0x1800075e9  xor     edx, edx; dwSpinCount
0x1800075eb  call    cs:__imp_InitializeCriticalSectionEx
0x1800075f2  nop     dword ptr [rax+rax+00h]
0x1800075f7  mov     qword ptr [rbx+28h], 0
0x1800075ff  lea     rcx, [rsp+280h+var_250]; this
0x180007604  mov     qword ptr [rbx+30h], 0
0x18000760c  mov     qword ptr [rbx+38h], 0
0x180007614  mov     qword ptr [rbx+40h], 0
0x18000761c  mov     [r15], r14
0x18000761f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007624  xor     ebx, ebx
0x180007626  test    rdi, rdi
0x180007629  jz      short loc_180007642
0x18000762b  mov     rcx, rdi; hMutex
0x18000762e  call    cs:__imp_ReleaseMutex
0x180007635  nop     dword ptr [rax+rax+00h]
0x18000763a  test    eax, eax
0x18000763c  jz      loc_1800076EF
0x180007642  test    rbx, rbx
0x180007645  jz      short loc_18000765A
0x180007647  mov     rcx, rbx; hObject
0x18000764a  call    cs:__imp_CloseHandle
0x180007651  nop     dword ptr [rax+rax+00h]
0x180007656  test    eax, eax
0x180007658  jz      short loc_180007683
0x18000765a  xor     eax, eax
0x18000765c  mov     rcx, [rbp+180h+var_30]
0x180007663  xor     rcx, rsp; StackCookie
0x180007666  call    __security_check_cookie
0x18000766b  mov     rbx, [rsp+280h+arg_10]
0x180007673  add     rsp, 260h
0x18000767a  pop     r15
0x18000767c  pop     r14
0x18000767e  pop     rdi
0x18000767f  pop     rsi
0x180007680  pop     rbp
0x180007681  retn
0x180007683  mov     rcx, [rbp+188h]; this
0x18000768a  mov     edx, 0A0Bh; void *
0x18000768f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007695  mov     rcx, [rbp+188h]; this
0x18000769c  mov     edx, 0A0Bh; void *
0x1800076a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076a7  mov     rcx, [rbp+188h]; this
0x1800076ae  mov     edx, 0E01h; void *
0x1800076b3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800076b9  mov     rcx, [rbp+188h]; this
0x1800076c0  mov     edx, 0A15h; void *
0x1800076c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076cb  mov     rcx, [rbp+188h]; this
0x1800076d2  mov     edx, 0A0Bh; void *
0x1800076d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076dd  mov     rcx, [rbp+188h]; this
0x1800076e4  mov     edx, 0A15h; void *
0x1800076e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076ef  mov     rcx, [rbp+188h]; this
0x1800076f6  mov     edx, 0A15h; void *
0x1800076fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
