# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800073b8`
- end: `0x180007789`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `977`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007f4c`

## callees

- `0x1800016c0`
- `0x180002158`
- `0x180006214`
- `0x180006958`
- `0x1800071b4`
- `0x1800073b8`
- `0x180007790`
- `0x1800079e0`
- `0x180007ce4`
- `0x180008288`
- `0x180008e60`
- `0x180008f3c`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007430`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007430`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007451`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007451`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800075fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007693`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800074e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800075fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a9`

## string_xrefs

- `0x1800076e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000770d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007726`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007745`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000775e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007777`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
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
  _QWORD *v22; // rsi
  unsigned int v23; // r14d
  int v24; // eax
  HANDLE ProcessHeap; // rax
  const char *v26; // r9
  const char *v27; // r9
  unsigned __int64 v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v34, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v31);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v32);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = (_QWORD *)v19;
  if ( v19 )
  {
    *(_OWORD *)v34 = 0;
    if ( (v19 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
    v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v34,
            Name,
            v21,
            v19 >> 2);
    v23 = v24;
    if ( v24 >= 0 )
    {
      v22[2] = v34[0];
      v28 = v34[1];
      *(_DWORD *)v22 = 1;
      v22[1] = v6;
      v34[0] = 0;
      v22[3] = v28;
      v34[1] = 0;
      memset_0((char *)v22 + 34, 0, 0x56u);
      *((_WORD *)v22 + 16) = 88;
      *((_DWORD *)v22 + 9) = 1;
      memset_0(v22 + 5, 0, 0x50u);
      *a2 = v22;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
      v6 = 0;
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v30);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
  }
  else
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v23, v33);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return v23;
}

```

## disassembly

```asm
0x1800073b8  mov     [rsp-8+arg_10], rbx
0x1800073bd  push    rbp
0x1800073be  push    rsi
0x1800073bf  push    rdi
0x1800073c0  push    r14
0x1800073c2  push    r15
0x1800073c4  lea     rbp, [rsp-160h]
0x1800073cc  sub     rsp, 260h
0x1800073d3  mov     rax, cs:__security_cookie
0x1800073da  xor     rax, rsp
0x1800073dd  mov     [rbp+180h+var_30], rax
0x1800073e4  mov     r15, rdx
0x1800073e7  mov     qword ptr [rdx], 0
0x1800073ee  mov     rbx, rcx
0x1800073f1  call    cs:__imp_GetCurrentProcessId
0x1800073f7  mov     r14d, 78h ; 'x'
0x1800073fd  mov     [rsp+280h+var_258], rbx
0x180007402  mov     r9d, eax
0x180007405  mov     [rsp+280h+var_260], r14d; int
0x18000740a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007411  mov     edx, 104h; unsigned __int64
0x180007416  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000741b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007420  mov     r9d, 1F0001h; dwDesiredAccess
0x180007426  lea     rdx, [rsp+280h+Name]; lpName
0x18000742b  xor     r8d, r8d; dwFlags
0x18000742e  xor     ecx, ecx; lpMutexAttributes
0x180007430  call    cs:__imp_CreateMutexExW
0x180007436  mov     rbx, rax
0x180007439  test    rax, rax
0x18000743c  jnz     short loc_180007448
0x18000743e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007443  jmp     loc_1800076B5
0x180007448  xor     r8d, r8d; bAlertable
0x18000744b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000744e  mov     rcx, rbx; hHandle
0x180007451  call    cs:__imp_WaitForSingleObjectEx
0x180007457  cmp     eax, 102h
0x18000745c  jz      short loc_18000746E
0x18000745e  test    eax, 0FFFFFF7Fh
0x180007463  jnz     loc_1800076F4
0x180007469  mov     rdi, rbx
0x18000746c  jmp     short loc_180007470
0x18000746e  xor     edi, edi
0x180007470  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180007475  mov     [rsp+280h+var_250], 0
0x18000747e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007483  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007488  mov     esi, eax
0x18000748a  test    eax, eax
0x18000748c  jns     short loc_18000750D
0x18000748e  mov     rcx, [rbp+188h]; this
0x180007495  lea     r8, aWil; "wil"
0x18000749c  mov     r9d, eax; char *
0x18000749f  mov     edx, 66h ; 'f'; void *
0x1800074a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074a9  mov     rcx, [rbp+188h]; this
0x1800074b0  lea     r8, aWil; "wil"
0x1800074b7  mov     r9d, esi; char *
0x1800074ba  mov     edx, 6Fh ; 'o'; void *
0x1800074bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074c4  mov     rcx, [rbp+188h]; this
0x1800074cb  lea     r8, aWil; "wil"
0x1800074d2  mov     r9d, esi; char *
0x1800074d5  mov     edx, 12Eh; void *
0x1800074da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074df  test    rdi, rdi
0x1800074e2  jz      short loc_1800074F5
0x1800074e4  mov     rcx, rdi; hMutex
0x1800074e7  call    cs:__imp_ReleaseMutex
0x1800074ed  test    eax, eax
0x1800074ef  jz      loc_180007706
0x1800074f5  mov     rcx, rbx; hObject
0x1800074f8  call    cs:__imp_CloseHandle
0x1800074fe  test    eax, eax
0x180007500  jz      loc_18000771F
0x180007506  mov     eax, esi
0x180007508  jmp     loc_1800076B5
0x18000750d  mov     rax, [rsp+280h+var_250]
0x180007512  lea     rcx, ds:0[rax*4]
0x18000751a  test    rcx, rcx
0x18000751d  jz      short loc_18000752D
0x18000751f  mov     [r15], rcx
0x180007522  mov     eax, [rcx]
0x180007524  inc     eax
0x180007526  mov     [rcx], eax
0x180007528  jmp     loc_18000768B
0x18000752d  mov     rdx, r14; dwBytes
0x180007530  mov     qword ptr [r15], 0
0x180007537  mov     ecx, 8; dwFlags
0x18000753c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007541  mov     rsi, rax
0x180007544  test    rax, rax
0x180007547  jnz     short loc_18000756C
0x180007549  mov     rcx, [rbp+188h]; this
0x180007550  lea     r8, aWil; "wil"
0x180007557  mov     r14d, 8007000Eh
0x18000755d  mov     edx, 14Bh; void *
0x180007562  mov     r9d, r14d; char *
0x180007565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000756a  jmp     short loc_1800075D9
0x18000756c  xorps   xmm0, xmm0
0x18000756f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007575  test    sil, 3
0x180007579  jnz     loc_180007738
0x18000757f  mov     r9, rsi
0x180007582  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007587  shr     r9, 2; unsigned __int64
0x18000758b  lea     rcx, [rsp+280h+var_250]; this
0x180007590  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007595  mov     r14d, eax
0x180007598  test    eax, eax
0x18000759a  jns     loc_180007623
0x1800075a0  mov     rcx, [rbp+188h]; this
0x1800075a7  lea     r8, aWil; "wil"
0x1800075ae  mov     r9d, eax; char *
0x1800075b1  mov     edx, 14Eh; void *
0x1800075b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075bb  lea     rcx, [rsp+280h+var_250]; this
0x1800075c0  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800075c5  call    cs:__imp_GetProcessHeap
0x1800075cb  mov     r8, rsi; lpMem
0x1800075ce  xor     edx, edx; dwFlags
0x1800075d0  mov     rcx, rax; hHeap
0x1800075d3  call    cs:__imp_HeapFree
0x1800075d9  mov     rcx, [rbp+188h]; this
0x1800075e0  lea     r8, aWil; "wil"
0x1800075e7  mov     r9d, r14d; char *
0x1800075ea  mov     edx, 137h; void *
0x1800075ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075f4  test    rdi, rdi
0x1800075f7  jz      short loc_18000760A
0x1800075f9  mov     rcx, rdi; hMutex
0x1800075fc  call    cs:__imp_ReleaseMutex
0x180007602  test    eax, eax
0x180007604  jz      loc_18000773E
0x18000760a  mov     rcx, rbx; hObject
0x18000760d  call    cs:__imp_CloseHandle
0x180007613  test    eax, eax
0x180007615  jz      loc_180007757
0x18000761b  mov     eax, r14d
0x18000761e  jmp     loc_1800076B5
0x180007623  mov     rax, [rsp+280h+var_250]
0x180007628  lea     rcx, [rsi+22h]; void *
0x18000762c  xor     edx, edx; Val
0x18000762e  mov     [rsi+10h], rax
0x180007632  mov     rax, [rsp+280h+var_250+8]
0x180007637  mov     dword ptr [rsi], 1
0x18000763d  mov     [rsi+8], rbx
0x180007641  lea     r8d, [rdx+56h]; Size
0x180007645  mov     [rsp+280h+var_250], 0
0x18000764e  mov     [rsi+18h], rax
0x180007652  mov     [rsp+280h+var_250+8], 0
0x18000765b  call    memset_0
0x180007660  xor     edx, edx; Val
0x180007662  mov     word ptr [rsi+20h], 58h ; 'X'
0x180007668  lea     rcx, [rsi+28h]; void *
0x18000766c  mov     dword ptr [rsi+24h], 1
0x180007673  lea     r8d, [rdx+50h]; Size
0x180007677  call    memset_0
0x18000767c  lea     rcx, [rsp+280h+var_250]; this
0x180007681  mov     [r15], rsi
0x180007684  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007689  xor     ebx, ebx
0x18000768b  test    rdi, rdi
0x18000768e  jz      short loc_1800076A1
0x180007690  mov     rcx, rdi; hMutex
0x180007693  call    cs:__imp_ReleaseMutex
0x180007699  test    eax, eax
0x18000769b  jz      loc_180007770
0x1800076a1  test    rbx, rbx
0x1800076a4  jz      short loc_1800076B3
0x1800076a6  mov     rcx, rbx; hObject
0x1800076a9  call    cs:__imp_CloseHandle
0x1800076af  test    eax, eax
0x1800076b1  jz      short loc_1800076DB
0x1800076b3  xor     eax, eax
0x1800076b5  mov     rcx, [rbp+180h+var_30]
0x1800076bc  xor     rcx, rsp; StackCookie
0x1800076bf  call    __security_check_cookie
0x1800076c4  mov     rbx, [rsp+280h+arg_10]
0x1800076cc  add     rsp, 260h
0x1800076d3  pop     r15
0x1800076d5  pop     r14
0x1800076d7  pop     rdi
0x1800076d8  pop     rsi
0x1800076d9  pop     rbp
0x1800076da  retn
0x1800076db  mov     rcx, [rbp+188h]; this
0x1800076e2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800076e9  mov     edx, 0A0Bh; void *
0x1800076ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800076f4  mov     rcx, [rbp+188h]; this
0x1800076fb  mov     edx, 0E01h; void *
0x180007700  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007706  mov     rcx, [rbp+188h]; this
0x18000770d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007714  mov     edx, 0A15h; void *
0x180007719  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000771f  mov     rcx, [rbp+188h]; this
0x180007726  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000772d  mov     edx, 0A0Bh; void *
0x180007732  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007738  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000773e  mov     rcx, [rbp+188h]; this
0x180007745  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000774c  mov     edx, 0A15h; void *
0x180007751  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007757  mov     rcx, [rbp+188h]; this
0x18000775e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007765  mov     edx, 0A0Bh; void *
0x18000776a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007770  mov     rcx, [rbp+188h]; this
0x180007777  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000777e  mov     edx, 0A15h; void *
0x180007783  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
