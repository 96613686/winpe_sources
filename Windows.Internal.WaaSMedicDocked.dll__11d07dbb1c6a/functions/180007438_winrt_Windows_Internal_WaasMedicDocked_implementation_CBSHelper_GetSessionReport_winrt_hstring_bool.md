# winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::GetSessionReport(winrt::hstring &,bool &)

- ea: `0x180007438`
- end: `0x180007784`
- name: `?GetSessionReport@CBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@QEAA?AUhresult@6@AEAUhstring@6@AEA_N@Z`
- size: `844`
- prototype: `int *__fastcall(__int64, int *, volatile signed __int32 **, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800073f0`

## callees

- `0x180001570`
- `0x18000204c`
- `0x180002070`
- `0x1800048e4`
- `0x180005db8`
- `0x180006590`
- `0x180006830`
- `0x180007438`
- `0x180009088`
- `0x18000d010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800076f1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800076f1`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800076de`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800076de`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007699`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007699`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180007684`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180007684`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800076cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800076cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000755d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007652`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007670`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007746`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000755d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007652`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007670`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000754f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007662`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007738`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000754f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007662`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007738`

## string_xrefs

- `0x180007619`: `Get CbsSessionPropertyRepairNeeded property.`

## pseudocode

```c
int *__fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::GetSessionReport(
        __int64 a1,
        int *a2,
        volatile signed __int32 **a3,
        bool *a4)
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 **); // rcx
  int v8; // ebx
  void (*v9)(void); // rax
  __int64 v10; // rax
  int v11; // ebx
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v14; // rax
  volatile signed __int32 *v15; // r15
  volatile signed __int32 *v16; // rbx
  int v17; // eax
  HANDLE v18; // rax
  wchar_t *v19; // rbx
  int v20; // esi
  HANDLE v21; // rax
  __int64 v22; // rax
  int v23; // ebx
  void *v24; // rbx
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  _DWORD *v28; // rax
  _DWORD *v29; // rsi
  const wchar_t *v30; // rbx
  int v31; // eax
  void *v32; // rbx
  HANDLE v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  int v37; // [rsp+20h] [rbp-60h]
  const char *v38; // [rsp+28h] [rbp-58h]
  __int64 *v39; // [rsp+30h] [rbp-50h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-48h] BYREF
  LPVOID v41; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *String[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v7 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))(a1 + 32);
  v39 = 0;
  v8 = (**v7)(v7, &GUID_dc95a094_ee0e_4974_9600_027d2321c2d4, &v39);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
      (const char *)(unsigned int)v8,
      (int)"Query ICbsSession7",
      v38);
    *a2 = v8;
    goto LABEL_3;
  }
  if ( !v39 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
      (const char *)0x8000FFFFLL,
      v37);
    *a2 = -2147418113;
    goto LABEL_3;
  }
  lpMem = 0;
  v10 = *v39;
  lpMem = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *))(v10 + 96))(v39, 5, &lpMem);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
      (const char *)(unsigned int)v11,
      (int)"Get CbsSessionPropertyReport property.",
      v38);
    *a2 = v11;
    v12 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    goto LABEL_3;
  }
  v14 = (volatile signed __int32 **)winrt::hstring::hstring((winrt::hstring *)&EndPtr, (const unsigned __int16 *)lpMem);
  if ( a3 != v14 )
  {
    v15 = *v14;
    *v14 = 0;
    v16 = *a3;
    if ( *a3 )
    {
      v17 = _InterlockedDecrement(v16 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          goto LABEL_27;
      }
      else
      {
        v18 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v18, 0, (LPVOID)v16);
      }
    }
    *a3 = v15;
  }
  v19 = EndPtr;
  if ( !EndPtr )
    goto LABEL_20;
  v20 = _InterlockedDecrement((volatile signed __int32 *)EndPtr + 6);
  if ( !v20 )
  {
    v21 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v21, 0, v19);
    goto LABEL_20;
  }
  if ( v20 < 0 )
LABEL_27:
    abort();
LABEL_20:
  v41 = 0;
  v22 = *v39;
  v41 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *))(v22 + 96))(v39, 22, &v41);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
      (const char *)(unsigned int)v23,
      (int)"Get CbsSessionPropertyRepairNeeded property.",
      v38);
    *a2 = v23;
    v24 = v41;
    if ( v41 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
    }
    v26 = lpMem;
    if ( lpMem )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
    }
LABEL_3:
    if ( v39 )
    {
      v9 = *(void (**)(void))(*v39 + 16);
LABEL_40:
      v9();
      return a2;
    }
    return a2;
  }
  std::wstring::wstring(String, v41);
  v28 = (_DWORD *)_o__errno();
  v29 = v28;
  v30 = (const wchar_t *)String;
  if ( String[3] > (wchar_t *)7 )
    v30 = String[0];
  EndPtr = 0;
  *v28 = 0;
  v31 = wcstol(v30, &EndPtr, 10);
  if ( v30 == EndPtr )
  {
    std::_Xinvalid_argument("invalid stoi argument");
    __debugbreak();
  }
  if ( *v29 == 34 )
  {
    std::_Xout_of_range("stoi argument out of range");
    __debugbreak();
  }
  *a4 = v31 != 0;
  *a2 = 0;
  std::wstring::~wstring(String);
  v32 = v41;
  if ( v41 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v32);
  }
  v34 = lpMem;
  if ( lpMem )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v34);
  }
  if ( v39 )
  {
    v9 = *(void (**)(void))(*v39 + 16);
    goto LABEL_40;
  }
  return a2;
}

```

## disassembly

```asm
0x180007438  push    rbp
0x18000743a  push    rbx
0x18000743b  push    rsi
0x18000743c  push    rdi
0x18000743d  push    r12
0x18000743f  push    r14
0x180007441  push    r15
0x180007443  mov     rbp, rsp
0x180007446  sub     rsp, 80h
0x18000744d  mov     rax, cs:__security_cookie
0x180007454  xor     rax, rsp
0x180007457  mov     [rbp+var_10], rax
0x18000745b  mov     r12, r9
0x18000745e  mov     r14, r8
0x180007461  mov     rdi, rdx
0x180007464  mov     rcx, [rcx+20h]
0x180007468  mov     [rbp+var_50], 0
0x180007470  mov     rax, [rcx]
0x180007473  lea     r8, [rbp+var_50]
0x180007477  lea     rdx, _GUID_dc95a094_ee0e_4974_9600_027d2321c2d4
0x18000747e  mov     rax, [rax]
0x180007481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007486  mov     ebx, eax
0x180007488  test    eax, eax
0x18000748a  jns     short loc_1800074CB
0x18000748c  mov     rcx, [rbp+38h]; this
0x180007490  lea     rax, aQueryIcbssessi_0; "Query ICbsSession7"
0x180007497  mov     qword ptr [rsp+80h+var_60], rax; int
0x18000749c  mov     r9d, ebx; char *
0x18000749f  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x1800074a6  mov     edx, 27h ; '''; void *
0x1800074ab  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800074b0  mov     [rdi], ebx
0x1800074b2  mov     rcx, [rbp+var_50]
0x1800074b6  test    rcx, rcx
0x1800074b9  jz      loc_180007763
0x1800074bf  mov     rax, [rcx]
0x1800074c2  mov     rax, [rax+10h]
0x1800074c6  jmp     loc_18000775D
0x1800074cb  mov     rcx, [rbp+var_50]
0x1800074cf  test    rcx, rcx
0x1800074d2  jnz     short loc_1800074F5
0x1800074d4  mov     rcx, [rbp+38h]; this
0x1800074d8  mov     ebx, 8000FFFFh
0x1800074dd  mov     r9d, ebx; char *
0x1800074e0  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x1800074e7  mov     edx, 28h ; '('; void *
0x1800074ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074f1  mov     [rdi], ebx
0x1800074f3  jmp     short loc_1800074B2
0x1800074f5  mov     [rbp+lpMem], 0
0x1800074fd  mov     rax, [rcx]
0x180007500  mov     [rbp+lpMem], 0
0x180007508  lea     r8, [rbp+lpMem]
0x18000750c  mov     edx, 5
0x180007511  mov     rax, [rax+60h]
0x180007515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751a  mov     ebx, eax
0x18000751c  test    eax, eax
0x18000751e  jns     short loc_180007569
0x180007520  mov     rcx, [rbp+38h]; this
0x180007524  lea     rax, aGetCbssessionp; "Get CbsSessionPropertyReport property."
0x18000752b  mov     qword ptr [rsp+80h+var_60], rax; int
0x180007530  mov     r9d, ebx; char *
0x180007533  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000753a  mov     edx, 2Bh ; '+'; void *
0x18000753f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007544  mov     [rdi], ebx
0x180007546  mov     rbx, [rbp+lpMem]
0x18000754a  test    rbx, rbx
0x18000754d  jz      short loc_180007564
0x18000754f  call    cs:__imp_GetProcessHeap
0x180007555  mov     rcx, rax; hHeap
0x180007558  mov     r8, rbx; lpMem
0x18000755b  xor     edx, edx; dwFlags
0x18000755d  call    cs:__imp_HeapFree
0x180007563  nop
0x180007564  jmp     loc_1800074B2
0x180007569  mov     rdx, [rbp+lpMem]; unsigned __int16 *
0x18000756d  lea     rcx, [rbp+EndPtr]; this
0x180007571  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180007576  or      esi, 0FFFFFFFFh
0x180007579  cmp     r14, rax
0x18000757c  jz      short loc_1800075BC
0x18000757e  mov     r15, [rax]
0x180007581  mov     qword ptr [rax], 0
0x180007588  mov     rbx, [r14]
0x18000758b  test    rbx, rbx
0x18000758e  jz      short loc_1800075B9
0x180007590  mov     eax, esi
0x180007592  lock xadd [rbx+18h], eax
0x180007597  sub     eax, 1
0x18000759a  jnz     short loc_1800075B1
0x18000759c  nop
0x18000759d  call    WINRT_IMPL_GetProcessHeap
0x1800075a2  mov     rcx, rax; hHeap
0x1800075a5  mov     r8, rbx; lpMem
0x1800075a8  xor     edx, edx; dwFlags
0x1800075aa  call    WINRT_IMPL_HeapFree
0x1800075af  jmp     short loc_1800075B9
0x1800075b1  test    eax, eax
0x1800075b3  js      loc_180007684
0x1800075b9  mov     [r14], r15
0x1800075bc  mov     rbx, [rbp+EndPtr]
0x1800075c0  test    rbx, rbx
0x1800075c3  jz      short loc_1800075E6
0x1800075c5  lock xadd [rbx+18h], esi
0x1800075ca  sub     esi, 1
0x1800075cd  jnz     loc_18000767C
0x1800075d3  nop
0x1800075d4  call    WINRT_IMPL_GetProcessHeap
0x1800075d9  mov     rcx, rax; hHeap
0x1800075dc  mov     r8, rbx; lpMem
0x1800075df  xor     edx, edx; dwFlags
0x1800075e1  call    WINRT_IMPL_HeapFree
0x1800075e6  mov     [rbp+var_40], 0
0x1800075ee  mov     rcx, [rbp+var_50]
0x1800075f2  mov     rax, [rcx]
0x1800075f5  mov     [rbp+var_40], 0
0x1800075fd  lea     r8, [rbp+var_40]
0x180007601  mov     edx, 16h
0x180007606  mov     rax, [rax+60h]
0x18000760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000760f  mov     ebx, eax
0x180007611  test    eax, eax
0x180007613  jns     short loc_18000768B
0x180007615  mov     rcx, [rbp+38h]; this
0x180007619  lea     rax, aGetCbssessionp_0; "Get CbsSessionPropertyRepairNeeded prop"...
0x180007620  mov     qword ptr [rsp+80h+var_60], rax; int
0x180007625  mov     r9d, ebx; char *
0x180007628  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000762f  mov     edx, 2Fh ; '/'; void *
0x180007634  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007639  mov     [rdi], ebx
0x18000763b  mov     rbx, [rbp+var_40]
0x18000763f  test    rbx, rbx
0x180007642  jz      short loc_180007659
0x180007644  call    cs:__imp_GetProcessHeap
0x18000764a  mov     rcx, rax; hHeap
0x18000764d  mov     r8, rbx; lpMem
0x180007650  xor     edx, edx; dwFlags
0x180007652  call    cs:__imp_HeapFree
0x180007658  nop
0x180007659  mov     rbx, [rbp+lpMem]
0x18000765d  test    rbx, rbx
0x180007660  jz      short loc_180007677
0x180007662  call    cs:__imp_GetProcessHeap
0x180007668  mov     rcx, rax; hHeap
0x18000766b  mov     r8, rbx; lpMem
0x18000766e  xor     edx, edx; dwFlags
0x180007670  call    cs:__imp_HeapFree
0x180007676  nop
0x180007677  jmp     loc_1800074B2
0x18000767c  test    esi, esi
0x18000767e  jns     loc_1800075E6
0x180007684  call    cs:__imp_abort
0x18000768b  mov     rdx, [rbp+var_40]
0x18000768f  lea     rcx, [rbp+String]
0x180007693  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180007698  nop
0x180007699  call    cs:__imp__o__errno
0x18000769f  mov     rsi, rax
0x1800076a2  lea     rbx, [rbp+String]
0x1800076a6  cmp     [rbp+var_18], 7
0x1800076ab  cmova   rbx, [rbp+String]
0x1800076b0  mov     [rbp+EndPtr], 0
0x1800076b8  mov     dword ptr [rax], 0
0x1800076be  mov     r8d, 0Ah; Radix
0x1800076c4  lea     rdx, [rbp+EndPtr]; EndPtr
0x1800076c8  mov     rcx, rbx; String
0x1800076cb  call    cs:__imp_wcstol
0x1800076d1  cmp     rbx, [rbp+EndPtr]
0x1800076d5  jnz     short loc_1800076E5
0x1800076d7  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x1800076de  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x1800076e4  int     3; Trap to Debugger
0x1800076e5  cmp     dword ptr [rsi], 22h ; '"'
0x1800076e8  jnz     short loc_1800076F8
0x1800076ea  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x1800076f1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800076f7  int     3; Trap to Debugger
0x1800076f8  test    eax, eax
0x1800076fa  setnz   al
0x1800076fd  mov     [r12], al
0x180007701  mov     dword ptr [rdi], 0
0x180007707  lea     rcx, [rbp+String]
0x18000770b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007710  nop
0x180007711  mov     rbx, [rbp+var_40]
0x180007715  test    rbx, rbx
0x180007718  jz      short loc_18000772F
0x18000771a  call    cs:__imp_GetProcessHeap
0x180007720  mov     rcx, rax; hHeap
0x180007723  mov     r8, rbx; lpMem
0x180007726  xor     edx, edx; dwFlags
0x180007728  call    cs:__imp_HeapFree
0x18000772e  nop
0x18000772f  mov     rbx, [rbp+lpMem]
0x180007733  test    rbx, rbx
0x180007736  jz      short loc_18000774D
0x180007738  call    cs:__imp_GetProcessHeap
0x18000773e  mov     rcx, rax; hHeap
0x180007741  mov     r8, rbx; lpMem
0x180007744  xor     edx, edx; dwFlags
0x180007746  call    cs:__imp_HeapFree
0x18000774c  nop
0x18000774d  mov     rcx, [rbp+var_50]
0x180007751  test    rcx, rcx
0x180007754  jz      short loc_180007763
0x180007756  mov     rdx, [rcx]
0x180007759  mov     rax, [rdx+10h]
0x18000775d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007762  nop
0x180007763  mov     rax, rdi
0x180007766  mov     rcx, [rbp+var_10]
0x18000776a  xor     rcx, rsp; StackCookie
0x18000776d  call    __security_check_cookie
0x180007772  add     rsp, 80h
0x180007779  pop     r15
0x18000777b  pop     r14
0x18000777d  pop     r12
0x18000777f  pop     rdi
0x180007780  pop     rsi
0x180007781  pop     rbx
0x180007782  pop     rbp
0x180007783  retn
```
