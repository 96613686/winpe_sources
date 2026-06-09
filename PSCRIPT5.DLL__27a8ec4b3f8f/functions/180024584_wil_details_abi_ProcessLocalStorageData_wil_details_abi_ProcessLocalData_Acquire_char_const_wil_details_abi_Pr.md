# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180024584`
- end: `0x180024957`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180025de0`

## callees

- `0x180001f20`
- `0x180002938`
- `0x1800242d8`
- `0x180024584`
- `0x180024d68`
- `0x180025118`
- `0x180025b68`
- `0x180026880`
- `0x180027c74`
- `0x1800284d4`
- `0x180028d00`
- `0x180029488`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800247a3`
- `KERNEL32!GetProcessHeap` at `0x1800247a3`
- `KERNEL32!GetCurrentProcessId` at `0x1800245bd`
- `KERNEL32!GetCurrentProcessId` at `0x1800245bd`
- `KERNEL32!CreateMutexExW` at `0x180024602`
- `KERNEL32!CreateMutexExW` at `0x180024602`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024629`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024629`
- `KERNEL32!ReleaseMutex` at `0x1800246c9`
- `KERNEL32!ReleaseMutex` at `0x1800247e6`
- `KERNEL32!ReleaseMutex` at `0x180024889`
- `KERNEL32!ReleaseMutex` at `0x1800246c9`
- `KERNEL32!ReleaseMutex` at `0x1800247e6`
- `KERNEL32!ReleaseMutex` at `0x180024889`
- `KERNEL32!HeapFree` at `0x1800247b7`
- `KERNEL32!HeapFree` at `0x1800247b7`
- `KERNEL32!CloseHandle` at `0x1800246e0`
- `KERNEL32!CloseHandle` at `0x1800247fd`
- `KERNEL32!CloseHandle` at `0x1800248a5`
- `KERNEL32!CloseHandle` at `0x1800246e0`
- `KERNEL32!CloseHandle` at `0x1800247fd`
- `KERNEL32!CloseHandle` at `0x1800248a5`

## pseudocode

```c
signed int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  void *v10; // rdx
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
  unsigned __int64 v29; // rax
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v7;
  }
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(pszDest, (__int64)v10, v34, (bool *)v12);
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
  v20 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (__int64)"wil", (const char *)0x8007000ELL);
    goto LABEL_18;
  }
  *(_OWORD *)v34 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer(
          (wil::details_abi::SemaphoreValue *)v34,
          pszDest,
          (unsigned __int64)v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (__int64)"wil", (const char *)(unsigned int)v23);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
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
  *((_QWORD *)v22 + 2) = v34[0];
  v29 = v34[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v7;
  v34[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v34[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
  v7 = 0;
LABEL_23:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180024584  mov     [rsp-8+arg_10], rbx
0x180024589  push    rbp
0x18002458a  push    rsi
0x18002458b  push    rdi
0x18002458c  push    r14
0x18002458e  push    r15
0x180024590  lea     rbp, [rsp-160h]
0x180024598  sub     rsp, 260h
0x18002459f  mov     rax, cs:__security_cookie
0x1800245a6  xor     rax, rsp
0x1800245a9  mov     [rbp+180h+var_30], rax
0x1800245b0  mov     r15, rdx
0x1800245b3  mov     qword ptr [rdx], 0
0x1800245ba  mov     rbx, rcx
0x1800245bd  call    cs:__imp_GetCurrentProcessId
0x1800245c4  nop     dword ptr [rax+rax+00h]
0x1800245c9  mov     r14d, 78h ; 'x'
0x1800245cf  mov     [rsp+280h+var_258], rbx
0x1800245d4  mov     r9d, eax
0x1800245d7  mov     [rsp+280h+var_260], r14d; int
0x1800245dc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800245e3  mov     edx, 104h; cchDest
0x1800245e8  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1800245ed  call    StringCchPrintfW
0x1800245f2  mov     r9d, 1F0001h; dwDesiredAccess
0x1800245f8  lea     rdx, [rsp+280h+pszDest]; lpName
0x1800245fd  xor     r8d, r8d; dwFlags
0x180024600  xor     ecx, ecx; lpMutexAttributes
0x180024602  call    cs:__imp_CreateMutexExW
0x180024609  nop     dword ptr [rax+rax+00h]
0x18002460e  mov     rbx, rax
0x180024611  test    rax, rax
0x180024614  jnz     short loc_180024620
0x180024616  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002461b  jmp     loc_1800248B7
0x180024620  xor     r8d, r8d; bAlertable
0x180024623  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180024626  mov     rcx, rbx; hHandle
0x180024629  call    cs:__imp_WaitForSingleObjectEx
0x180024630  nop     dword ptr [rax+rax+00h]
0x180024635  cmp     eax, 102h
0x18002463a  jz      short loc_18002464C
0x18002463c  test    eax, 0FFFFFF7Fh
0x180024641  jnz     loc_180024902
0x180024647  mov     rdi, rbx
0x18002464a  jmp     short loc_18002464E
0x18002464c  xor     edi, edi
0x18002464e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180024653  mov     [rsp+280h+var_250], 0
0x18002465c  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180024661  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180024666  mov     esi, eax
0x180024668  test    eax, eax
0x18002466a  jns     loc_1800246FB
0x180024670  mov     rcx, [rbp+188h]; this
0x180024677  lea     r8, aWil; "wil"
0x18002467e  mov     r9d, eax; char *
0x180024681  mov     edx, 66h ; 'f'; void *
0x180024686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002468b  mov     rcx, [rbp+188h]; this
0x180024692  lea     r8, aWil; "wil"
0x180024699  mov     r9d, esi; char *
0x18002469c  mov     edx, 6Fh ; 'o'; void *
0x1800246a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246a6  mov     rcx, [rbp+188h]; this
0x1800246ad  lea     r8, aWil; "wil"
0x1800246b4  mov     r9d, esi; char *
0x1800246b7  mov     edx, 12Eh; void *
0x1800246bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246c1  test    rdi, rdi
0x1800246c4  jz      short loc_1800246DD
0x1800246c6  mov     rcx, rdi; hMutex
0x1800246c9  call    cs:__imp_ReleaseMutex
0x1800246d0  nop     dword ptr [rax+rax+00h]
0x1800246d5  test    eax, eax
0x1800246d7  jz      loc_18002490F
0x1800246dd  mov     rcx, rbx; hObject
0x1800246e0  call    cs:__imp_CloseHandle
0x1800246e7  nop     dword ptr [rax+rax+00h]
0x1800246ec  test    eax, eax
0x1800246ee  jz      loc_180024921
0x1800246f4  mov     eax, esi
0x1800246f6  jmp     loc_1800248B7
0x1800246fb  mov     rax, [rsp+280h+var_250]
0x180024700  lea     rcx, ds:0[rax*4]
0x180024708  test    rcx, rcx
0x18002470b  jz      short loc_18002471B
0x18002470d  mov     [r15], rcx
0x180024710  mov     eax, [rcx]
0x180024712  inc     eax
0x180024714  mov     [rcx], eax
0x180024716  jmp     loc_180024881
0x18002471b  mov     rdx, r14; dwBytes
0x18002471e  mov     qword ptr [r15], 0
0x180024725  mov     ecx, 8; dwFlags
0x18002472a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002472f  mov     r14, rax
0x180024732  test    rax, rax
0x180024735  jnz     short loc_180024759
0x180024737  mov     rcx, [rbp+188h]; this
0x18002473e  lea     r8, aWil; "wil"
0x180024745  mov     esi, 8007000Eh
0x18002474a  mov     edx, 14Bh; void *
0x18002474f  mov     r9d, esi; char *
0x180024752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024757  jmp     short loc_1800247C3
0x180024759  xorps   xmm0, xmm0
0x18002475c  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180024761  mov     r8, r14; void *
0x180024764  lea     rcx, [rsp+280h+var_250]; this
0x180024769  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18002476f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180024774  mov     esi, eax
0x180024776  test    eax, eax
0x180024778  jns     loc_180024816
0x18002477e  mov     rcx, [rbp+188h]; this
0x180024785  lea     r8, aWil; "wil"
0x18002478c  mov     r9d, eax; char *
0x18002478f  mov     edx, 14Eh; void *
0x180024794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024799  lea     rcx, [rsp+280h+var_250]; this
0x18002479e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800247a3  call    cs:__imp_GetProcessHeap
0x1800247aa  nop     dword ptr [rax+rax+00h]
0x1800247af  mov     r8, r14; lpMem
0x1800247b2  xor     edx, edx; dwFlags
0x1800247b4  mov     rcx, rax; hHeap
0x1800247b7  call    cs:__imp_HeapFree
0x1800247be  nop     dword ptr [rax+rax+00h]
0x1800247c3  mov     rcx, [rbp+188h]; this
0x1800247ca  lea     r8, aWil; "wil"
0x1800247d1  mov     r9d, esi; char *
0x1800247d4  mov     edx, 137h; void *
0x1800247d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247de  test    rdi, rdi
0x1800247e1  jz      short loc_1800247FA
0x1800247e3  mov     rcx, rdi; hMutex
0x1800247e6  call    cs:__imp_ReleaseMutex
0x1800247ed  nop     dword ptr [rax+rax+00h]
0x1800247f2  test    eax, eax
0x1800247f4  jz      loc_180024933
0x1800247fa  mov     rcx, rbx; hObject
0x1800247fd  call    cs:__imp_CloseHandle
0x180024804  nop     dword ptr [rax+rax+00h]
0x180024809  test    eax, eax
0x18002480b  jz      loc_1800248F0
0x180024811  jmp     loc_1800246F4
0x180024816  mov     rax, [rsp+280h+var_250]
0x18002481b  lea     rcx, [r14+22h]; void *
0x18002481f  xor     edx, edx; Val
0x180024821  mov     [r14+10h], rax
0x180024825  mov     rax, [rsp+280h+var_250+8]
0x18002482a  mov     dword ptr [r14], 1
0x180024831  mov     [r14+8], rbx
0x180024835  lea     r8d, [rdx+56h]; Size
0x180024839  mov     [rsp+280h+var_250], 0
0x180024842  mov     [r14+18h], rax
0x180024846  mov     [rsp+280h+var_250+8], 0
0x18002484f  call    memset_0
0x180024854  xor     edx, edx; Val
0x180024856  mov     word ptr [r14+20h], 58h ; 'X'
0x18002485d  lea     rcx, [r14+28h]; void *
0x180024861  mov     dword ptr [r14+24h], 1
0x180024869  lea     r8d, [rdx+50h]; Size
0x18002486d  call    memset_0
0x180024872  lea     rcx, [rsp+280h+var_250]; this
0x180024877  mov     [r15], r14
0x18002487a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18002487f  xor     ebx, ebx
0x180024881  test    rdi, rdi
0x180024884  jz      short loc_18002489D
0x180024886  mov     rcx, rdi; hMutex
0x180024889  call    cs:__imp_ReleaseMutex
0x180024890  nop     dword ptr [rax+rax+00h]
0x180024895  test    eax, eax
0x180024897  jz      loc_180024945
0x18002489d  test    rbx, rbx
0x1800248a0  jz      short loc_1800248B5
0x1800248a2  mov     rcx, rbx; hObject
0x1800248a5  call    cs:__imp_CloseHandle
0x1800248ac  nop     dword ptr [rax+rax+00h]
0x1800248b1  test    eax, eax
0x1800248b3  jz      short loc_1800248DE
0x1800248b5  xor     eax, eax
0x1800248b7  mov     rcx, [rbp+180h+var_30]
0x1800248be  xor     rcx, rsp; StackCookie
0x1800248c1  call    __security_check_cookie
0x1800248c6  mov     rbx, [rsp+280h+arg_10]
0x1800248ce  add     rsp, 260h
0x1800248d5  pop     r15
0x1800248d7  pop     r14
0x1800248d9  pop     rdi
0x1800248da  pop     rsi
0x1800248db  pop     rbp
0x1800248dc  retn
0x1800248de  mov     rcx, [rbp+188h]; this
0x1800248e5  mov     edx, 0A0Bh; void *
0x1800248ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800248f0  mov     rcx, [rbp+188h]; this
0x1800248f7  mov     edx, 0A0Bh; void *
0x1800248fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024902  mov     rcx, [rbp+188h]; this
0x180024909  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002490f  mov     rcx, [rbp+188h]; this
0x180024916  mov     edx, 0A15h; void *
0x18002491b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024921  mov     rcx, [rbp+188h]; this
0x180024928  mov     edx, 0A0Bh; void *
0x18002492d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024933  mov     rcx, [rbp+188h]; this
0x18002493a  mov     edx, 0A15h; void *
0x18002493f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024945  mov     rcx, [rbp+188h]; this
0x18002494c  mov     edx, 0A15h; void *
0x180024951  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
