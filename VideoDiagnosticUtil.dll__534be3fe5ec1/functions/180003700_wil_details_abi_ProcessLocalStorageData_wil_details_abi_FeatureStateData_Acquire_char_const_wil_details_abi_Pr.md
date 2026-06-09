# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003700`
- end: `0x180003ad2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180003ce4`

## callees

- `0x180002d04`
- `0x1800030e8`
- `0x180003700`
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

- `KERNEL32!GetProcessHeap` at `0x1800038f7`
- `KERNEL32!GetProcessHeap` at `0x1800038f7`
- `KERNEL32!HeapFree` at `0x18000390b`
- `KERNEL32!HeapFree` at `0x18000390b`
- `KERNEL32!CloseHandle` at `0x180003842`
- `KERNEL32!CloseHandle` at `0x18000394a`
- `KERNEL32!CloseHandle` at `0x180003a20`
- `KERNEL32!CloseHandle` at `0x180003842`
- `KERNEL32!CloseHandle` at `0x18000394a`
- `KERNEL32!CloseHandle` at `0x180003a20`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800039c1`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800039c1`
- `KERNEL32!GetCurrentProcessId` at `0x180003739`
- `KERNEL32!GetCurrentProcessId` at `0x180003739`
- `KERNEL32!CreateMutexExW` at `0x18000377d`
- `KERNEL32!CreateMutexExW` at `0x18000377d`
- `KERNEL32!ReleaseMutex` at `0x18000382b`
- `KERNEL32!ReleaseMutex` at `0x180003933`
- `KERNEL32!ReleaseMutex` at `0x180003a04`
- `KERNEL32!ReleaseMutex` at `0x18000382b`
- `KERNEL32!ReleaseMutex` at `0x180003933`
- `KERNEL32!ReleaseMutex` at `0x180003a04`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800037a4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800037a4`

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
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x180003700  mov     [rsp-8+arg_10], rbx
0x180003705  push    rbp
0x180003706  push    rsi
0x180003707  push    rdi
0x180003708  push    r14
0x18000370a  push    r15
0x18000370c  lea     rbp, [rsp-160h]
0x180003714  sub     rsp, 260h
0x18000371b  mov     rax, cs:__security_cookie
0x180003722  xor     rax, rsp
0x180003725  mov     [rbp+180h+var_30], rax
0x18000372c  mov     r15, rdx
0x18000372f  mov     qword ptr [rdx], 0
0x180003736  mov     rbx, rcx
0x180003739  call    cs:__imp_GetCurrentProcessId
0x180003740  nop     dword ptr [rax+rax+00h]
0x180003745  mov     r14d, 130h
0x18000374b  mov     [rsp+280h+var_258], rbx
0x180003750  mov     r9d, eax
0x180003753  mov     [rsp+280h+var_260], r14d; int
0x180003758  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000375f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003764  lea     edx, [r14-2Ch]; unsigned __int64
0x180003768  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000376d  mov     r9d, 1F0001h; dwDesiredAccess
0x180003773  lea     rdx, [rsp+280h+Name]; lpName
0x180003778  xor     r8d, r8d; dwFlags
0x18000377b  xor     ecx, ecx; lpMutexAttributes
0x18000377d  call    cs:__imp_CreateMutexExW
0x180003784  nop     dword ptr [rax+rax+00h]
0x180003789  mov     rbx, rax
0x18000378c  test    rax, rax
0x18000378f  jnz     short loc_18000379B
0x180003791  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003796  jmp     loc_180003A32
0x18000379b  xor     r8d, r8d; bAlertable
0x18000379e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800037a1  mov     rcx, rbx; hHandle
0x1800037a4  call    cs:__imp_WaitForSingleObjectEx
0x1800037ab  nop     dword ptr [rax+rax+00h]
0x1800037b0  cmp     eax, 102h
0x1800037b5  jz      short loc_1800037C7
0x1800037b7  test    eax, 0FFFFFF7Fh
0x1800037bc  jnz     loc_180003A7D
0x1800037c2  mov     rdi, rbx
0x1800037c5  jmp     short loc_1800037C9
0x1800037c7  xor     edi, edi
0x1800037c9  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800037ce  mov     [rsp+280h+var_250], 0
0x1800037d7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800037dc  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800037e1  mov     esi, eax
0x1800037e3  test    eax, eax
0x1800037e5  jns     short loc_18000385D
0x1800037e7  mov     rcx, [rbp+188h]; this
0x1800037ee  mov     r9d, eax; char *
0x1800037f1  mov     edx, 66h ; 'f'; void *
0x1800037f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037fb  mov     rcx, [rbp+188h]; this
0x180003802  mov     r9d, esi; char *
0x180003805  mov     edx, 6Fh ; 'o'; void *
0x18000380a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000380f  mov     rcx, [rbp+188h]; this
0x180003816  mov     r9d, esi; char *
0x180003819  mov     edx, 12Eh; void *
0x18000381e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003823  test    rdi, rdi
0x180003826  jz      short loc_18000383F
0x180003828  mov     rcx, rdi; hMutex
0x18000382b  call    cs:__imp_ReleaseMutex
0x180003832  nop     dword ptr [rax+rax+00h]
0x180003837  test    eax, eax
0x180003839  jz      loc_180003A8A
0x18000383f  mov     rcx, rbx; hObject
0x180003842  call    cs:__imp_CloseHandle
0x180003849  nop     dword ptr [rax+rax+00h]
0x18000384e  test    eax, eax
0x180003850  jz      loc_180003A9C
0x180003856  mov     eax, esi
0x180003858  jmp     loc_180003A32
0x18000385d  mov     rax, [rsp+280h+var_250]
0x180003862  lea     rcx, ds:0[rax*4]
0x18000386a  test    rcx, rcx
0x18000386d  jz      short loc_18000387D
0x18000386f  mov     [r15], rcx
0x180003872  mov     eax, [rcx]
0x180003874  inc     eax
0x180003876  mov     [rcx], eax
0x180003878  jmp     loc_1800039FC
0x18000387d  mov     rdx, r14; dwBytes
0x180003880  mov     qword ptr [r15], 0
0x180003887  mov     ecx, 8; dwFlags
0x18000388c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003891  mov     r14, rax
0x180003894  test    rax, rax
0x180003897  jnz     short loc_1800038B4
0x180003899  mov     rcx, [rbp+188h]; this
0x1800038a0  mov     esi, 8007000Eh
0x1800038a5  mov     r9d, esi; char *
0x1800038a8  mov     edx, 14Bh; void *
0x1800038ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038b2  jmp     short loc_180003917
0x1800038b4  xorps   xmm0, xmm0
0x1800038b7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800038bc  mov     r8, r14; void *
0x1800038bf  lea     rcx, [rsp+280h+var_250]; this
0x1800038c4  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800038ca  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800038cf  mov     esi, eax
0x1800038d1  test    eax, eax
0x1800038d3  jns     loc_180003963
0x1800038d9  mov     rcx, [rbp+188h]; this
0x1800038e0  mov     r9d, eax; char *
0x1800038e3  mov     edx, 14Eh; void *
0x1800038e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ed  lea     rcx, [rsp+280h+var_250]; this
0x1800038f2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800038f7  call    cs:__imp_GetProcessHeap
0x1800038fe  nop     dword ptr [rax+rax+00h]
0x180003903  mov     r8, r14; lpMem
0x180003906  xor     edx, edx; dwFlags
0x180003908  mov     rcx, rax; hHeap
0x18000390b  call    cs:__imp_HeapFree
0x180003912  nop     dword ptr [rax+rax+00h]
0x180003917  mov     rcx, [rbp+188h]; this
0x18000391e  mov     r9d, esi; char *
0x180003921  mov     edx, 137h; void *
0x180003926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000392b  test    rdi, rdi
0x18000392e  jz      short loc_180003947
0x180003930  mov     rcx, rdi; hMutex
0x180003933  call    cs:__imp_ReleaseMutex
0x18000393a  nop     dword ptr [rax+rax+00h]
0x18000393f  test    eax, eax
0x180003941  jz      loc_180003AAE
0x180003947  mov     rcx, rbx; hObject
0x18000394a  call    cs:__imp_CloseHandle
0x180003951  nop     dword ptr [rax+rax+00h]
0x180003956  test    eax, eax
0x180003958  jz      loc_180003A6B
0x18000395e  jmp     loc_180003856
0x180003963  mov     rax, [rsp+280h+var_250]
0x180003968  lea     rcx, [r14+28h]; void *
0x18000396c  mov     [r14+10h], rax
0x180003970  xor     edx, edx; Val
0x180003972  mov     rax, [rsp+280h+var_250+8]
0x180003977  mov     r8d, 108h; Size
0x18000397d  mov     [r14+18h], rax
0x180003981  mov     dword ptr [r14], 1
0x180003988  mov     [r14+8], rbx
0x18000398c  mov     [rsp+280h+var_250], 0
0x180003995  mov     [rsp+280h+var_250+8], 0
0x18000399e  call    memset_0
0x1800039a3  xor     eax, eax
0x1800039a5  lea     rcx, [r14+28h]; this
0x1800039a9  mov     [r14+20h], rax
0x1800039ad  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800039b2  lea     rbx, [r14+0E8h]
0x1800039b9  xor     r8d, r8d; Flags
0x1800039bc  mov     rcx, rbx; lpCriticalSection
0x1800039bf  xor     edx, edx; dwSpinCount
0x1800039c1  call    cs:__imp_InitializeCriticalSectionEx
0x1800039c8  nop     dword ptr [rax+rax+00h]
0x1800039cd  mov     qword ptr [rbx+28h], 0
0x1800039d5  lea     rcx, [rsp+280h+var_250]; this
0x1800039da  mov     qword ptr [rbx+30h], 0
0x1800039e2  mov     qword ptr [rbx+38h], 0
0x1800039ea  mov     qword ptr [rbx+40h], 0
0x1800039f2  mov     [r15], r14
0x1800039f5  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800039fa  xor     ebx, ebx
0x1800039fc  test    rdi, rdi
0x1800039ff  jz      short loc_180003A18
0x180003a01  mov     rcx, rdi; hMutex
0x180003a04  call    cs:__imp_ReleaseMutex
0x180003a0b  nop     dword ptr [rax+rax+00h]
0x180003a10  test    eax, eax
0x180003a12  jz      loc_180003AC0
0x180003a18  test    rbx, rbx
0x180003a1b  jz      short loc_180003A30
0x180003a1d  mov     rcx, rbx; hObject
0x180003a20  call    cs:__imp_CloseHandle
0x180003a27  nop     dword ptr [rax+rax+00h]
0x180003a2c  test    eax, eax
0x180003a2e  jz      short loc_180003A59
0x180003a30  xor     eax, eax
0x180003a32  mov     rcx, [rbp+180h+var_30]
0x180003a39  xor     rcx, rsp; StackCookie
0x180003a3c  call    __security_check_cookie
0x180003a41  mov     rbx, [rsp+280h+arg_10]
0x180003a49  add     rsp, 260h
0x180003a50  pop     r15
0x180003a52  pop     r14
0x180003a54  pop     rdi
0x180003a55  pop     rsi
0x180003a56  pop     rbp
0x180003a57  retn
0x180003a59  mov     rcx, [rbp+188h]; this
0x180003a60  mov     edx, 0A0Bh; void *
0x180003a65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a6b  mov     rcx, [rbp+188h]; this
0x180003a72  mov     edx, 0A0Bh; void *
0x180003a77  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a7d  mov     rcx, [rbp+188h]; this
0x180003a84  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003a8a  mov     rcx, [rbp+188h]; this
0x180003a91  mov     edx, 0A15h; void *
0x180003a96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a9c  mov     rcx, [rbp+188h]; this
0x180003aa3  mov     edx, 0A0Bh; void *
0x180003aa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003aae  mov     rcx, [rbp+188h]; this
0x180003ab5  mov     edx, 0A15h; void *
0x180003aba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ac0  mov     rcx, [rbp+188h]; this
0x180003ac7  mov     edx, 0A15h; void *
0x180003acc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
