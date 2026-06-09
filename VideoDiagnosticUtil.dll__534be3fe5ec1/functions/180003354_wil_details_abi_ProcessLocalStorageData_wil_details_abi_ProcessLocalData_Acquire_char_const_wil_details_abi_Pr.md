# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003354`
- end: `0x1800036f9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004840`

## callees

- `0x1800030e8`
- `0x180003354`
- `0x180003ad8`
- `0x180003e60`
- `0x1800046f8`
- `0x1800054f8`
- `0x180006870`
- `0x180006c98`
- `0x1800070e4`
- `0x18000787c`
- `0x18000967e`
- `0x1800096b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000354c`
- `KERNEL32!GetProcessHeap` at `0x18000354c`
- `KERNEL32!HeapFree` at `0x180003560`
- `KERNEL32!HeapFree` at `0x180003560`
- `KERNEL32!CloseHandle` at `0x180003497`
- `KERNEL32!CloseHandle` at `0x18000359f`
- `KERNEL32!CloseHandle` at `0x180003647`
- `KERNEL32!CloseHandle` at `0x180003497`
- `KERNEL32!CloseHandle` at `0x18000359f`
- `KERNEL32!CloseHandle` at `0x180003647`
- `KERNEL32!GetCurrentProcessId` at `0x18000338d`
- `KERNEL32!GetCurrentProcessId` at `0x18000338d`
- `KERNEL32!CreateMutexExW` at `0x1800033d2`
- `KERNEL32!CreateMutexExW` at `0x1800033d2`
- `KERNEL32!ReleaseMutex` at `0x180003480`
- `KERNEL32!ReleaseMutex` at `0x180003588`
- `KERNEL32!ReleaseMutex` at `0x18000362b`
- `KERNEL32!ReleaseMutex` at `0x180003480`
- `KERNEL32!ReleaseMutex` at `0x180003588`
- `KERNEL32!ReleaseMutex` at `0x18000362b`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800033f9`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800033f9`

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
0x180003354  mov     [rsp-8+arg_10], rbx
0x180003359  push    rbp
0x18000335a  push    rsi
0x18000335b  push    rdi
0x18000335c  push    r14
0x18000335e  push    r15
0x180003360  lea     rbp, [rsp-160h]
0x180003368  sub     rsp, 260h
0x18000336f  mov     rax, cs:__security_cookie
0x180003376  xor     rax, rsp
0x180003379  mov     [rbp+180h+var_30], rax
0x180003380  mov     r15, rdx
0x180003383  mov     qword ptr [rdx], 0
0x18000338a  mov     rbx, rcx
0x18000338d  call    cs:__imp_GetCurrentProcessId
0x180003394  nop     dword ptr [rax+rax+00h]
0x180003399  mov     r14d, 78h ; 'x'
0x18000339f  mov     [rsp+280h+var_258], rbx
0x1800033a4  mov     r9d, eax
0x1800033a7  mov     [rsp+280h+var_260], r14d; int
0x1800033ac  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800033b3  mov     edx, 104h; unsigned __int64
0x1800033b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800033bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800033c2  mov     r9d, 1F0001h; dwDesiredAccess
0x1800033c8  lea     rdx, [rsp+280h+Name]; lpName
0x1800033cd  xor     r8d, r8d; dwFlags
0x1800033d0  xor     ecx, ecx; lpMutexAttributes
0x1800033d2  call    cs:__imp_CreateMutexExW
0x1800033d9  nop     dword ptr [rax+rax+00h]
0x1800033de  mov     rbx, rax
0x1800033e1  test    rax, rax
0x1800033e4  jnz     short loc_1800033F0
0x1800033e6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800033eb  jmp     loc_180003659
0x1800033f0  xor     r8d, r8d; bAlertable
0x1800033f3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800033f6  mov     rcx, rbx; hHandle
0x1800033f9  call    cs:__imp_WaitForSingleObjectEx
0x180003400  nop     dword ptr [rax+rax+00h]
0x180003405  cmp     eax, 102h
0x18000340a  jz      short loc_18000341C
0x18000340c  test    eax, 0FFFFFF7Fh
0x180003411  jnz     loc_1800036A4
0x180003417  mov     rdi, rbx
0x18000341a  jmp     short loc_18000341E
0x18000341c  xor     edi, edi
0x18000341e  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180003423  mov     [rsp+280h+var_250], 0
0x18000342c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003431  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003436  mov     esi, eax
0x180003438  test    eax, eax
0x18000343a  jns     short loc_1800034B2
0x18000343c  mov     rcx, [rbp+188h]; this
0x180003443  mov     r9d, eax; char *
0x180003446  mov     edx, 66h ; 'f'; void *
0x18000344b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003450  mov     rcx, [rbp+188h]; this
0x180003457  mov     r9d, esi; char *
0x18000345a  mov     edx, 6Fh ; 'o'; void *
0x18000345f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003464  mov     rcx, [rbp+188h]; this
0x18000346b  mov     r9d, esi; char *
0x18000346e  mov     edx, 12Eh; void *
0x180003473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003478  test    rdi, rdi
0x18000347b  jz      short loc_180003494
0x18000347d  mov     rcx, rdi; hMutex
0x180003480  call    cs:__imp_ReleaseMutex
0x180003487  nop     dword ptr [rax+rax+00h]
0x18000348c  test    eax, eax
0x18000348e  jz      loc_1800036B1
0x180003494  mov     rcx, rbx; hObject
0x180003497  call    cs:__imp_CloseHandle
0x18000349e  nop     dword ptr [rax+rax+00h]
0x1800034a3  test    eax, eax
0x1800034a5  jz      loc_1800036C3
0x1800034ab  mov     eax, esi
0x1800034ad  jmp     loc_180003659
0x1800034b2  mov     rax, [rsp+280h+var_250]
0x1800034b7  lea     rcx, ds:0[rax*4]
0x1800034bf  test    rcx, rcx
0x1800034c2  jz      short loc_1800034D2
0x1800034c4  mov     [r15], rcx
0x1800034c7  mov     eax, [rcx]
0x1800034c9  inc     eax
0x1800034cb  mov     [rcx], eax
0x1800034cd  jmp     loc_180003623
0x1800034d2  mov     rdx, r14; dwBytes
0x1800034d5  mov     qword ptr [r15], 0
0x1800034dc  mov     ecx, 8; dwFlags
0x1800034e1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800034e6  mov     r14, rax
0x1800034e9  test    rax, rax
0x1800034ec  jnz     short loc_180003509
0x1800034ee  mov     rcx, [rbp+188h]; this
0x1800034f5  mov     esi, 8007000Eh
0x1800034fa  mov     r9d, esi; char *
0x1800034fd  mov     edx, 14Bh; void *
0x180003502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003507  jmp     short loc_18000356C
0x180003509  xorps   xmm0, xmm0
0x18000350c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003511  mov     r8, r14; void *
0x180003514  lea     rcx, [rsp+280h+var_250]; this
0x180003519  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000351f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003524  mov     esi, eax
0x180003526  test    eax, eax
0x180003528  jns     loc_1800035B8
0x18000352e  mov     rcx, [rbp+188h]; this
0x180003535  mov     r9d, eax; char *
0x180003538  mov     edx, 14Eh; void *
0x18000353d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003542  lea     rcx, [rsp+280h+var_250]; this
0x180003547  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000354c  call    cs:__imp_GetProcessHeap
0x180003553  nop     dword ptr [rax+rax+00h]
0x180003558  mov     r8, r14; lpMem
0x18000355b  xor     edx, edx; dwFlags
0x18000355d  mov     rcx, rax; hHeap
0x180003560  call    cs:__imp_HeapFree
0x180003567  nop     dword ptr [rax+rax+00h]
0x18000356c  mov     rcx, [rbp+188h]; this
0x180003573  mov     r9d, esi; char *
0x180003576  mov     edx, 137h; void *
0x18000357b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003580  test    rdi, rdi
0x180003583  jz      short loc_18000359C
0x180003585  mov     rcx, rdi; hMutex
0x180003588  call    cs:__imp_ReleaseMutex
0x18000358f  nop     dword ptr [rax+rax+00h]
0x180003594  test    eax, eax
0x180003596  jz      loc_1800036D5
0x18000359c  mov     rcx, rbx; hObject
0x18000359f  call    cs:__imp_CloseHandle
0x1800035a6  nop     dword ptr [rax+rax+00h]
0x1800035ab  test    eax, eax
0x1800035ad  jz      loc_180003692
0x1800035b3  jmp     loc_1800034AB
0x1800035b8  mov     rax, [rsp+280h+var_250]
0x1800035bd  lea     rcx, [r14+22h]; void *
0x1800035c1  xor     edx, edx; Val
0x1800035c3  mov     [r14+10h], rax
0x1800035c7  mov     rax, [rsp+280h+var_250+8]
0x1800035cc  mov     dword ptr [r14], 1
0x1800035d3  mov     [r14+8], rbx
0x1800035d7  lea     r8d, [rdx+56h]; Size
0x1800035db  mov     [rsp+280h+var_250], 0
0x1800035e4  mov     [r14+18h], rax
0x1800035e8  mov     [rsp+280h+var_250+8], 0
0x1800035f1  call    memset_0
0x1800035f6  xor     edx, edx; Val
0x1800035f8  mov     word ptr [r14+20h], 58h ; 'X'
0x1800035ff  lea     rcx, [r14+28h]; void *
0x180003603  mov     dword ptr [r14+24h], 1
0x18000360b  lea     r8d, [rdx+50h]; Size
0x18000360f  call    memset_0
0x180003614  lea     rcx, [rsp+280h+var_250]; this
0x180003619  mov     [r15], r14
0x18000361c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003621  xor     ebx, ebx
0x180003623  test    rdi, rdi
0x180003626  jz      short loc_18000363F
0x180003628  mov     rcx, rdi; hMutex
0x18000362b  call    cs:__imp_ReleaseMutex
0x180003632  nop     dword ptr [rax+rax+00h]
0x180003637  test    eax, eax
0x180003639  jz      loc_1800036E7
0x18000363f  test    rbx, rbx
0x180003642  jz      short loc_180003657
0x180003644  mov     rcx, rbx; hObject
0x180003647  call    cs:__imp_CloseHandle
0x18000364e  nop     dword ptr [rax+rax+00h]
0x180003653  test    eax, eax
0x180003655  jz      short loc_180003680
0x180003657  xor     eax, eax
0x180003659  mov     rcx, [rbp+180h+var_30]
0x180003660  xor     rcx, rsp; StackCookie
0x180003663  call    __security_check_cookie
0x180003668  mov     rbx, [rsp+280h+arg_10]
0x180003670  add     rsp, 260h
0x180003677  pop     r15
0x180003679  pop     r14
0x18000367b  pop     rdi
0x18000367c  pop     rsi
0x18000367d  pop     rbp
0x18000367e  retn
0x180003680  mov     rcx, [rbp+188h]; this
0x180003687  mov     edx, 0A0Bh; void *
0x18000368c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003692  mov     rcx, [rbp+188h]; this
0x180003699  mov     edx, 0A0Bh; void *
0x18000369e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036a4  mov     rcx, [rbp+188h]; this
0x1800036ab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800036b1  mov     rcx, [rbp+188h]; this
0x1800036b8  mov     edx, 0A15h; void *
0x1800036bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036c3  mov     rcx, [rbp+188h]; this
0x1800036ca  mov     edx, 0A0Bh; void *
0x1800036cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036d5  mov     rcx, [rbp+188h]; this
0x1800036dc  mov     edx, 0A15h; void *
0x1800036e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800036e7  mov     rcx, [rbp+188h]; this
0x1800036ee  mov     edx, 0A15h; void *
0x1800036f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
