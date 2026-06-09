# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003648`
- end: `0x1800039ed`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005854`

## callees

- `0x180003338`
- `0x180003648`
- `0x180003dcc`
- `0x18000436c`
- `0x1800055d0`
- `0x180006468`
- `0x180007a94`
- `0x1800084ac`
- `0x180008a0c`
- `0x180009500`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003681`
- `KERNEL32!GetCurrentProcessId` at `0x180003681`
- `KERNEL32!CreateMutexExW` at `0x1800036c6`
- `KERNEL32!CreateMutexExW` at `0x1800036c6`
- `KERNEL32!GetProcessHeap` at `0x180003840`
- `KERNEL32!GetProcessHeap` at `0x180003840`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800036ed`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800036ed`
- `KERNEL32!ReleaseMutex` at `0x180003774`
- `KERNEL32!ReleaseMutex` at `0x18000387c`
- `KERNEL32!ReleaseMutex` at `0x18000391f`
- `KERNEL32!ReleaseMutex` at `0x180003774`
- `KERNEL32!ReleaseMutex` at `0x18000387c`
- `KERNEL32!ReleaseMutex` at `0x18000391f`
- `KERNEL32!CloseHandle` at `0x18000378b`
- `KERNEL32!CloseHandle` at `0x180003893`
- `KERNEL32!CloseHandle` at `0x18000393b`
- `KERNEL32!CloseHandle` at `0x18000378b`
- `KERNEL32!CloseHandle` at `0x180003893`
- `KERNEL32!CloseHandle` at `0x18000393b`
- `KERNEL32!HeapFree` at `0x180003854`
- `KERNEL32!HeapFree` at `0x180003854`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v42 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v42, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v42[0];
  v34 = v42[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v42[0] = 0;
  *((_QWORD *)v25 + 3) = v34;
  v42[1] = 0;
  memset_0((char *)v25 + 34, 0, 0x56u);
  *((_WORD *)v25 + 16) = 88;
  v25[9] = 1;
  memset_0(v25 + 10, 0, 0x50u);
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180003648  mov     [rsp-8+arg_10], rbx
0x18000364d  push    rbp
0x18000364e  push    rsi
0x18000364f  push    rdi
0x180003650  push    r14
0x180003652  push    r15
0x180003654  lea     rbp, [rsp-160h]
0x18000365c  sub     rsp, 260h
0x180003663  mov     rax, cs:__security_cookie
0x18000366a  xor     rax, rsp
0x18000366d  mov     [rbp+180h+var_30], rax
0x180003674  mov     r15, rdx
0x180003677  mov     qword ptr [rdx], 0
0x18000367e  mov     rbx, rcx
0x180003681  call    cs:__imp_GetCurrentProcessId
0x180003688  nop     dword ptr [rax+rax+00h]
0x18000368d  mov     r14d, 78h ; 'x'
0x180003693  mov     [rsp+280h+var_258], rbx
0x180003698  mov     r9d, eax
0x18000369b  mov     [rsp+280h+var_260], r14d; int
0x1800036a0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800036a7  mov     edx, 104h; unsigned __int64
0x1800036ac  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800036b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800036b6  mov     r9d, 1F0001h; dwDesiredAccess
0x1800036bc  lea     rdx, [rsp+280h+Name]; lpName
0x1800036c1  xor     r8d, r8d; dwFlags
0x1800036c4  xor     ecx, ecx; lpMutexAttributes
0x1800036c6  call    cs:__imp_CreateMutexExW
0x1800036cd  nop     dword ptr [rax+rax+00h]
0x1800036d2  mov     rbx, rax
0x1800036d5  test    rax, rax
0x1800036d8  jnz     short loc_1800036E4
0x1800036da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800036df  jmp     loc_18000394D
0x1800036e4  xor     r8d, r8d; bAlertable
0x1800036e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800036ea  mov     rcx, rbx; hHandle
0x1800036ed  call    cs:__imp_WaitForSingleObjectEx
0x1800036f4  nop     dword ptr [rax+rax+00h]
0x1800036f9  cmp     eax, 102h
0x1800036fe  jz      short loc_180003710
0x180003700  test    eax, 0FFFFFF7Fh
0x180003705  jnz     loc_180003998
0x18000370b  mov     rdi, rbx
0x18000370e  jmp     short loc_180003712
0x180003710  xor     edi, edi
0x180003712  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180003717  mov     [rsp+280h+var_250], 0
0x180003720  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003725  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000372a  mov     esi, eax
0x18000372c  test    eax, eax
0x18000372e  jns     short loc_1800037A6
0x180003730  mov     rcx, [rbp+188h]; this
0x180003737  mov     r9d, eax; char *
0x18000373a  mov     edx, 66h ; 'f'; void *
0x18000373f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003744  mov     rcx, [rbp+188h]; this
0x18000374b  mov     r9d, esi; char *
0x18000374e  mov     edx, 6Fh ; 'o'; void *
0x180003753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003758  mov     rcx, [rbp+188h]; this
0x18000375f  mov     r9d, esi; char *
0x180003762  mov     edx, 12Eh; void *
0x180003767  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000376c  test    rdi, rdi
0x18000376f  jz      short loc_180003788
0x180003771  mov     rcx, rdi; hMutex
0x180003774  call    cs:__imp_ReleaseMutex
0x18000377b  nop     dword ptr [rax+rax+00h]
0x180003780  test    eax, eax
0x180003782  jz      loc_1800039A5
0x180003788  mov     rcx, rbx; hObject
0x18000378b  call    cs:__imp_CloseHandle
0x180003792  nop     dword ptr [rax+rax+00h]
0x180003797  test    eax, eax
0x180003799  jz      loc_1800039B7
0x18000379f  mov     eax, esi
0x1800037a1  jmp     loc_18000394D
0x1800037a6  mov     rax, [rsp+280h+var_250]
0x1800037ab  lea     rcx, ds:0[rax*4]
0x1800037b3  test    rcx, rcx
0x1800037b6  jz      short loc_1800037C6
0x1800037b8  mov     [r15], rcx
0x1800037bb  mov     eax, [rcx]
0x1800037bd  inc     eax
0x1800037bf  mov     [rcx], eax
0x1800037c1  jmp     loc_180003917
0x1800037c6  mov     rdx, r14; dwBytes
0x1800037c9  mov     qword ptr [r15], 0
0x1800037d0  mov     ecx, 8; dwFlags
0x1800037d5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800037da  mov     r14, rax
0x1800037dd  test    rax, rax
0x1800037e0  jnz     short loc_1800037FD
0x1800037e2  mov     rcx, [rbp+188h]; this
0x1800037e9  mov     esi, 8007000Eh
0x1800037ee  mov     r9d, esi; char *
0x1800037f1  mov     edx, 14Bh; void *
0x1800037f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037fb  jmp     short loc_180003860
0x1800037fd  xorps   xmm0, xmm0
0x180003800  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003805  mov     r8, r14; void *
0x180003808  lea     rcx, [rsp+280h+var_250]; this
0x18000380d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180003813  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003818  mov     esi, eax
0x18000381a  test    eax, eax
0x18000381c  jns     loc_1800038AC
0x180003822  mov     rcx, [rbp+188h]; this
0x180003829  mov     r9d, eax; char *
0x18000382c  mov     edx, 14Eh; void *
0x180003831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003836  lea     rcx, [rsp+280h+var_250]; this
0x18000383b  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003840  call    cs:__imp_GetProcessHeap
0x180003847  nop     dword ptr [rax+rax+00h]
0x18000384c  mov     r8, r14; lpMem
0x18000384f  xor     edx, edx; dwFlags
0x180003851  mov     rcx, rax; hHeap
0x180003854  call    cs:__imp_HeapFree
0x18000385b  nop     dword ptr [rax+rax+00h]
0x180003860  mov     rcx, [rbp+188h]; this
0x180003867  mov     r9d, esi; char *
0x18000386a  mov     edx, 137h; void *
0x18000386f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003874  test    rdi, rdi
0x180003877  jz      short loc_180003890
0x180003879  mov     rcx, rdi; hMutex
0x18000387c  call    cs:__imp_ReleaseMutex
0x180003883  nop     dword ptr [rax+rax+00h]
0x180003888  test    eax, eax
0x18000388a  jz      loc_1800039C9
0x180003890  mov     rcx, rbx; hObject
0x180003893  call    cs:__imp_CloseHandle
0x18000389a  nop     dword ptr [rax+rax+00h]
0x18000389f  test    eax, eax
0x1800038a1  jz      loc_180003986
0x1800038a7  jmp     loc_18000379F
0x1800038ac  mov     rax, [rsp+280h+var_250]
0x1800038b1  lea     rcx, [r14+22h]; void *
0x1800038b5  xor     edx, edx; Val
0x1800038b7  mov     [r14+10h], rax
0x1800038bb  mov     rax, [rsp+280h+var_250+8]
0x1800038c0  mov     dword ptr [r14], 1
0x1800038c7  mov     [r14+8], rbx
0x1800038cb  lea     r8d, [rdx+56h]; Size
0x1800038cf  mov     [rsp+280h+var_250], 0
0x1800038d8  mov     [r14+18h], rax
0x1800038dc  mov     [rsp+280h+var_250+8], 0
0x1800038e5  call    memset_0
0x1800038ea  xor     edx, edx; Val
0x1800038ec  mov     word ptr [r14+20h], 58h ; 'X'
0x1800038f3  lea     rcx, [r14+28h]; void *
0x1800038f7  mov     dword ptr [r14+24h], 1
0x1800038ff  lea     r8d, [rdx+50h]; Size
0x180003903  call    memset_0
0x180003908  lea     rcx, [rsp+280h+var_250]; this
0x18000390d  mov     [r15], r14
0x180003910  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003915  xor     ebx, ebx
0x180003917  test    rdi, rdi
0x18000391a  jz      short loc_180003933
0x18000391c  mov     rcx, rdi; hMutex
0x18000391f  call    cs:__imp_ReleaseMutex
0x180003926  nop     dword ptr [rax+rax+00h]
0x18000392b  test    eax, eax
0x18000392d  jz      loc_1800039DB
0x180003933  test    rbx, rbx
0x180003936  jz      short loc_18000394B
0x180003938  mov     rcx, rbx; hObject
0x18000393b  call    cs:__imp_CloseHandle
0x180003942  nop     dword ptr [rax+rax+00h]
0x180003947  test    eax, eax
0x180003949  jz      short loc_180003974
0x18000394b  xor     eax, eax
0x18000394d  mov     rcx, [rbp+180h+var_30]
0x180003954  xor     rcx, rsp; StackCookie
0x180003957  call    __security_check_cookie
0x18000395c  mov     rbx, [rsp+280h+arg_10]
0x180003964  add     rsp, 260h
0x18000396b  pop     r15
0x18000396d  pop     r14
0x18000396f  pop     rdi
0x180003970  pop     rsi
0x180003971  pop     rbp
0x180003972  retn
0x180003974  mov     rcx, [rbp+188h]; this
0x18000397b  mov     edx, 0A0Bh; void *
0x180003980  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003986  mov     rcx, [rbp+188h]; this
0x18000398d  mov     edx, 0A0Bh; void *
0x180003992  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003998  mov     rcx, [rbp+188h]; this
0x18000399f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800039a5  mov     rcx, [rbp+188h]; this
0x1800039ac  mov     edx, 0A15h; void *
0x1800039b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039b7  mov     rcx, [rbp+188h]; this
0x1800039be  mov     edx, 0A0Bh; void *
0x1800039c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039c9  mov     rcx, [rbp+188h]; this
0x1800039d0  mov     edx, 0A15h; void *
0x1800039d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039db  mov     rcx, [rbp+188h]; this
0x1800039e2  mov     edx, 0A15h; void *
0x1800039e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
