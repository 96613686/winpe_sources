# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000522c`
- end: `0x18000561d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180005a90`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x180004318`
- `0x180004ab8`
- `0x18000522c`
- `0x18000568c`
- `0x180005cf0`
- `0x180006628`
- `0x180007358`
- `0x180008c24`
- `0x180009718`
- `0x180009bac`
- `0x18000a48c`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800052c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800052c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000535a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000546d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000552c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000535a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000546d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000552c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800054ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800054ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800052a3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800052a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005444`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000536b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005542`

## string_xrefs

- `0x18000557b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005594`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800055ba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800055d3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800055f2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000560b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v32[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v32, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v32[0]);
  if ( 4 * v32[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = (_DWORD *)v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v32 = 0;
  if ( (v19 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v32,
          Name,
          v21,
          v19 >> 2);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v32[0];
  *((_QWORD *)v22 + 3) = v32[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v32[0] = 0;
  v32[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  return 0;
}

```

## disassembly

```asm
0x18000522c  mov     [rsp-8+arg_10], rbx
0x180005231  push    rbp
0x180005232  push    rsi
0x180005233  push    rdi
0x180005234  push    r14
0x180005236  push    r15
0x180005238  lea     rbp, [rsp-160h]
0x180005240  sub     rsp, 260h
0x180005247  mov     rax, cs:__security_cookie
0x18000524e  xor     rax, rsp
0x180005251  mov     [rbp+180h+var_30], rax
0x180005258  mov     r15, rdx
0x18000525b  mov     qword ptr [rdx], 0
0x180005262  mov     rbx, rcx
0x180005265  call    cs:__imp_GetCurrentProcessId
0x18000526b  mov     r14d, 130h
0x180005271  mov     [rsp+280h+var_258], rbx
0x180005276  mov     r9d, eax
0x180005279  mov     [rsp+280h+var_260], r14d; int
0x18000527e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005285  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000528a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000528e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005293  mov     r9d, 1F0001h; dwDesiredAccess
0x180005299  lea     rdx, [rsp+280h+Name]; lpName
0x18000529e  xor     r8d, r8d; dwFlags
0x1800052a1  xor     ecx, ecx; lpMutexAttributes
0x1800052a3  call    cs:__imp_CreateMutexExW
0x1800052a9  mov     rbx, rax
0x1800052ac  test    rax, rax
0x1800052af  jnz     short loc_1800052BB
0x1800052b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800052b6  jmp     loc_18000554E
0x1800052bb  xor     r8d, r8d; bAlertable
0x1800052be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800052c1  mov     rcx, rbx; hHandle
0x1800052c4  call    cs:__imp_WaitForSingleObjectEx
0x1800052ca  cmp     eax, 102h
0x1800052cf  jz      short loc_1800052E1
0x1800052d1  test    eax, 0FFFFFF7Fh
0x1800052d6  jnz     loc_1800055A6
0x1800052dc  mov     rdi, rbx
0x1800052df  jmp     short loc_1800052E3
0x1800052e1  xor     edi, edi
0x1800052e3  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800052e8  mov     [rsp+280h+var_250], 0
0x1800052f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800052f6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800052fb  mov     esi, eax
0x1800052fd  test    eax, eax
0x1800052ff  jns     short loc_180005380
0x180005301  mov     rcx, [rbp+188h]; this
0x180005308  lea     r8, aWil; "wil"
0x18000530f  mov     r9d, eax; char *
0x180005312  mov     edx, 66h ; 'f'; void *
0x180005317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000531c  mov     rcx, [rbp+188h]; this
0x180005323  lea     r8, aWil; "wil"
0x18000532a  mov     r9d, esi; char *
0x18000532d  mov     edx, 6Fh ; 'o'; void *
0x180005332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005337  mov     rcx, [rbp+188h]; this
0x18000533e  lea     r8, aWil; "wil"
0x180005345  mov     r9d, esi; char *
0x180005348  mov     edx, 12Eh; void *
0x18000534d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005352  test    rdi, rdi
0x180005355  jz      short loc_180005368
0x180005357  mov     rcx, rdi; hMutex
0x18000535a  call    cs:__imp_ReleaseMutex
0x180005360  test    eax, eax
0x180005362  jz      loc_1800055B3
0x180005368  mov     rcx, rbx; hObject
0x18000536b  call    cs:__imp_CloseHandle
0x180005371  test    eax, eax
0x180005373  jz      loc_1800055CC
0x180005379  mov     eax, esi
0x18000537b  jmp     loc_18000554E
0x180005380  mov     rax, [rsp+280h+var_250]
0x180005385  lea     rcx, ds:0[rax*4]
0x18000538d  test    rcx, rcx
0x180005390  jz      short loc_1800053A0
0x180005392  mov     [r15], rcx
0x180005395  mov     eax, [rcx]
0x180005397  inc     eax
0x180005399  mov     [rcx], eax
0x18000539b  jmp     loc_180005524
0x1800053a0  mov     rdx, r14; dwBytes
0x1800053a3  mov     qword ptr [r15], 0
0x1800053aa  mov     ecx, 8; dwFlags
0x1800053af  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800053b4  mov     r14, rax
0x1800053b7  test    rax, rax
0x1800053ba  jnz     short loc_1800053DE
0x1800053bc  mov     rcx, [rbp+188h]; this
0x1800053c3  lea     r8, aWil; "wil"
0x1800053ca  mov     esi, 8007000Eh
0x1800053cf  mov     edx, 14Bh; void *
0x1800053d4  mov     r9d, esi; char *
0x1800053d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053dc  jmp     short loc_18000544A
0x1800053de  xorps   xmm0, xmm0
0x1800053e1  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800053e7  test    r14b, 3
0x1800053eb  jnz     loc_1800055E5
0x1800053f1  mov     r9, r14
0x1800053f4  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800053f9  shr     r9, 2; unsigned __int64
0x1800053fd  lea     rcx, [rsp+280h+var_250]; this
0x180005402  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005407  mov     esi, eax
0x180005409  test    eax, eax
0x18000540b  jns     loc_180005491
0x180005411  mov     rcx, [rbp+188h]; this
0x180005418  lea     r8, aWil; "wil"
0x18000541f  mov     r9d, eax; char *
0x180005422  mov     edx, 14Eh; void *
0x180005427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000542c  lea     rcx, [rsp+280h+var_250]; this
0x180005431  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005436  call    cs:__imp_GetProcessHeap
0x18000543c  mov     r8, r14; lpMem
0x18000543f  xor     edx, edx; dwFlags
0x180005441  mov     rcx, rax; hHeap
0x180005444  call    cs:__imp_HeapFree
0x18000544a  mov     rcx, [rbp+188h]; this
0x180005451  lea     r8, aWil; "wil"
0x180005458  mov     r9d, esi; char *
0x18000545b  mov     edx, 137h; void *
0x180005460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005465  test    rdi, rdi
0x180005468  jz      short loc_18000547B
0x18000546a  mov     rcx, rdi; hMutex
0x18000546d  call    cs:__imp_ReleaseMutex
0x180005473  test    eax, eax
0x180005475  jz      loc_1800055EB
0x18000547b  mov     rcx, rbx; hObject
0x18000547e  call    cs:__imp_CloseHandle
0x180005484  test    eax, eax
0x180005486  jz      loc_18000558D
0x18000548c  jmp     loc_180005379
0x180005491  mov     rax, [rsp+280h+var_250]
0x180005496  lea     rcx, [r14+28h]; void *
0x18000549a  mov     [r14+10h], rax
0x18000549e  xor     edx, edx; Val
0x1800054a0  mov     rax, [rsp+280h+var_250+8]
0x1800054a5  mov     r8d, 108h; Size
0x1800054ab  mov     [r14+18h], rax
0x1800054af  mov     dword ptr [r14], 1
0x1800054b6  mov     [r14+8], rbx
0x1800054ba  mov     [rsp+280h+var_250], 0
0x1800054c3  mov     [rsp+280h+var_250+8], 0
0x1800054cc  call    memset_0
0x1800054d1  xor     eax, eax
0x1800054d3  lea     rcx, [r14+28h]; this
0x1800054d7  mov     [r14+20h], rax
0x1800054db  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800054e0  lea     rbx, [r14+0E8h]
0x1800054e7  xor     r8d, r8d; Flags
0x1800054ea  mov     rcx, rbx; lpCriticalSection
0x1800054ed  xor     edx, edx; dwSpinCount
0x1800054ef  call    cs:__imp_InitializeCriticalSectionEx
0x1800054f5  mov     qword ptr [rbx+28h], 0
0x1800054fd  lea     rcx, [rsp+280h+var_250]; this
0x180005502  mov     qword ptr [rbx+30h], 0
0x18000550a  mov     qword ptr [rbx+38h], 0
0x180005512  mov     qword ptr [rbx+40h], 0
0x18000551a  mov     [r15], r14
0x18000551d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005522  xor     ebx, ebx
0x180005524  test    rdi, rdi
0x180005527  jz      short loc_18000553A
0x180005529  mov     rcx, rdi; hMutex
0x18000552c  call    cs:__imp_ReleaseMutex
0x180005532  test    eax, eax
0x180005534  jz      loc_180005604
0x18000553a  test    rbx, rbx
0x18000553d  jz      short loc_18000554C
0x18000553f  mov     rcx, rbx; hObject
0x180005542  call    cs:__imp_CloseHandle
0x180005548  test    eax, eax
0x18000554a  jz      short loc_180005574
0x18000554c  xor     eax, eax
0x18000554e  mov     rcx, [rbp+180h+var_30]
0x180005555  xor     rcx, rsp; StackCookie
0x180005558  call    __security_check_cookie
0x18000555d  mov     rbx, [rsp+280h+arg_10]
0x180005565  add     rsp, 260h
0x18000556c  pop     r15
0x18000556e  pop     r14
0x180005570  pop     rdi
0x180005571  pop     rsi
0x180005572  pop     rbp
0x180005573  retn
0x180005574  mov     rcx, [rbp+188h]; this
0x18000557b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005582  mov     edx, 0A0Bh; void *
0x180005587  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000558d  mov     rcx, [rbp+188h]; this
0x180005594  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000559b  mov     edx, 0A0Bh; void *
0x1800055a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055a6  mov     rcx, [rbp+188h]; this
0x1800055ad  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800055b3  mov     rcx, [rbp+188h]; this
0x1800055ba  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800055c1  mov     edx, 0A15h; void *
0x1800055c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055cc  mov     rcx, [rbp+188h]; this
0x1800055d3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800055da  mov     edx, 0A0Bh; void *
0x1800055df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055e5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800055eb  mov     rcx, [rbp+188h]; this
0x1800055f2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800055f9  mov     edx, 0A15h; void *
0x1800055fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005604  mov     rcx, [rbp+188h]; this
0x18000560b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005612  mov     edx, 0A15h; void *
0x180005617  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
