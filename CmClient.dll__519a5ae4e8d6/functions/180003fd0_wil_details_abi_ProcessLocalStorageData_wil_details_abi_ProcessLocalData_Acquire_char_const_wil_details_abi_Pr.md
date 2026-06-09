# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003fd0`
- end: `0x1800043a8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005160`

## callees

- `0x180001550`
- `0x180002158`
- `0x180003ee4`
- `0x180003fd0`
- `0x180004650`
- `0x1800048a0`
- `0x180004ef8`
- `0x1800062a4`
- `0x1800066e4`
- `0x180006ae4`
- `0x180006b70`
- `0x180006ffc`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004069`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004069`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004214`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004214`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ab`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004048`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c1`

## string_xrefs

- `0x1800042fa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004313`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000432c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004345`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004364`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000437d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004396`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
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
  return v22;
}

```

## disassembly

```asm
0x180003fd0  mov     [rsp-8+arg_10], rbx
0x180003fd5  push    rbp
0x180003fd6  push    rsi
0x180003fd7  push    rdi
0x180003fd8  push    r14
0x180003fda  push    r15
0x180003fdc  lea     rbp, [rsp-160h]
0x180003fe4  sub     rsp, 260h
0x180003feb  mov     rax, cs:__security_cookie
0x180003ff2  xor     rax, rsp
0x180003ff5  mov     [rbp+180h+var_30], rax
0x180003ffc  mov     r15, rdx
0x180003fff  mov     qword ptr [rdx], 0
0x180004006  mov     rbx, rcx
0x180004009  call    cs:__imp_GetCurrentProcessId
0x18000400f  mov     r14d, 78h ; 'x'
0x180004015  mov     [rsp+280h+var_258], rbx
0x18000401a  mov     r9d, eax
0x18000401d  mov     [rsp+280h+var_260], r14d; int
0x180004022  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004029  mov     edx, 104h; unsigned __int64
0x18000402e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004033  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004038  mov     r9d, 1F0001h; dwDesiredAccess
0x18000403e  lea     rdx, [rsp+280h+Name]; lpName
0x180004043  xor     r8d, r8d; dwFlags
0x180004046  xor     ecx, ecx; lpMutexAttributes
0x180004048  call    cs:__imp_CreateMutexExW
0x18000404e  mov     rbx, rax
0x180004051  test    rax, rax
0x180004054  jnz     short loc_180004060
0x180004056  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000405b  jmp     loc_1800042CD
0x180004060  xor     r8d, r8d; bAlertable
0x180004063  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004066  mov     rcx, rbx; hHandle
0x180004069  call    cs:__imp_WaitForSingleObjectEx
0x18000406f  cmp     eax, 102h
0x180004074  jz      short loc_180004086
0x180004076  test    eax, 0FFFFFF7Fh
0x18000407b  jnz     loc_18000430C
0x180004081  mov     rdi, rbx
0x180004084  jmp     short loc_180004088
0x180004086  xor     edi, edi
0x180004088  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000408d  mov     [rsp+280h+var_250], 0
0x180004096  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000409b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800040a0  mov     esi, eax
0x1800040a2  test    eax, eax
0x1800040a4  jns     short loc_180004125
0x1800040a6  mov     rcx, [rbp+188h]; this
0x1800040ad  lea     r8, aWil; "wil"
0x1800040b4  mov     r9d, eax; char *
0x1800040b7  mov     edx, 66h ; 'f'; void *
0x1800040bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040c1  mov     rcx, [rbp+188h]; this
0x1800040c8  lea     r8, aWil; "wil"
0x1800040cf  mov     r9d, esi; char *
0x1800040d2  mov     edx, 6Fh ; 'o'; void *
0x1800040d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040dc  mov     rcx, [rbp+188h]; this
0x1800040e3  lea     r8, aWil; "wil"
0x1800040ea  mov     r9d, esi; char *
0x1800040ed  mov     edx, 12Eh; void *
0x1800040f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040f7  test    rdi, rdi
0x1800040fa  jz      short loc_18000410D
0x1800040fc  mov     rcx, rdi; hMutex
0x1800040ff  call    cs:__imp_ReleaseMutex
0x180004105  test    eax, eax
0x180004107  jz      loc_180004325
0x18000410d  mov     rcx, rbx; hObject
0x180004110  call    cs:__imp_CloseHandle
0x180004116  test    eax, eax
0x180004118  jz      loc_18000433E
0x18000411e  mov     eax, esi
0x180004120  jmp     loc_1800042CD
0x180004125  mov     rax, [rsp+280h+var_250]
0x18000412a  lea     rcx, ds:0[rax*4]
0x180004132  test    rcx, rcx
0x180004135  jz      short loc_180004145
0x180004137  mov     [r15], rcx
0x18000413a  mov     eax, [rcx]
0x18000413c  inc     eax
0x18000413e  mov     [rcx], eax
0x180004140  jmp     loc_1800042A3
0x180004145  mov     rdx, r14; dwBytes
0x180004148  mov     qword ptr [r15], 0
0x18000414f  mov     ecx, 8; dwFlags
0x180004154  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004159  mov     rsi, rax
0x18000415c  test    rax, rax
0x18000415f  jnz     short loc_180004184
0x180004161  mov     rcx, [rbp+188h]; this
0x180004168  lea     r8, aWil; "wil"
0x18000416f  mov     r14d, 8007000Eh
0x180004175  mov     edx, 14Bh; void *
0x18000417a  mov     r9d, r14d; char *
0x18000417d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004182  jmp     short loc_1800041F1
0x180004184  xorps   xmm0, xmm0
0x180004187  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000418d  test    sil, 3
0x180004191  jnz     loc_180004357
0x180004197  mov     r9, rsi
0x18000419a  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000419f  shr     r9, 2; unsigned __int64
0x1800041a3  lea     rcx, [rsp+280h+var_250]; this
0x1800041a8  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800041ad  mov     r14d, eax
0x1800041b0  test    eax, eax
0x1800041b2  jns     loc_18000423B
0x1800041b8  mov     rcx, [rbp+188h]; this
0x1800041bf  lea     r8, aWil; "wil"
0x1800041c6  mov     r9d, eax; char *
0x1800041c9  mov     edx, 14Eh; void *
0x1800041ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041d3  lea     rcx, [rsp+280h+var_250]; this
0x1800041d8  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800041dd  call    cs:__imp_GetProcessHeap
0x1800041e3  mov     r8, rsi; lpMem
0x1800041e6  xor     edx, edx; dwFlags
0x1800041e8  mov     rcx, rax; hHeap
0x1800041eb  call    cs:__imp_HeapFree
0x1800041f1  mov     rcx, [rbp+188h]; this
0x1800041f8  lea     r8, aWil; "wil"
0x1800041ff  mov     r9d, r14d; char *
0x180004202  mov     edx, 137h; void *
0x180004207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000420c  test    rdi, rdi
0x18000420f  jz      short loc_180004222
0x180004211  mov     rcx, rdi; hMutex
0x180004214  call    cs:__imp_ReleaseMutex
0x18000421a  test    eax, eax
0x18000421c  jz      loc_18000435D
0x180004222  mov     rcx, rbx; hObject
0x180004225  call    cs:__imp_CloseHandle
0x18000422b  test    eax, eax
0x18000422d  jz      loc_180004376
0x180004233  mov     eax, r14d
0x180004236  jmp     loc_1800042CD
0x18000423b  mov     rax, [rsp+280h+var_250]
0x180004240  lea     rcx, [rsi+22h]; void *
0x180004244  xor     edx, edx; Val
0x180004246  mov     [rsi+10h], rax
0x18000424a  mov     rax, [rsp+280h+var_250+8]
0x18000424f  mov     dword ptr [rsi], 1
0x180004255  mov     [rsi+8], rbx
0x180004259  lea     r8d, [rdx+56h]; Size
0x18000425d  mov     [rsp+280h+var_250], 0
0x180004266  mov     [rsi+18h], rax
0x18000426a  mov     [rsp+280h+var_250+8], 0
0x180004273  call    memset_0
0x180004278  xor     edx, edx; Val
0x18000427a  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004280  lea     rcx, [rsi+28h]; void *
0x180004284  mov     dword ptr [rsi+24h], 1
0x18000428b  lea     r8d, [rdx+50h]; Size
0x18000428f  call    memset_0
0x180004294  lea     rcx, [rsp+280h+var_250]; this
0x180004299  mov     [r15], rsi
0x18000429c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800042a1  xor     ebx, ebx
0x1800042a3  test    rdi, rdi
0x1800042a6  jz      short loc_1800042B9
0x1800042a8  mov     rcx, rdi; hMutex
0x1800042ab  call    cs:__imp_ReleaseMutex
0x1800042b1  test    eax, eax
0x1800042b3  jz      loc_18000438F
0x1800042b9  test    rbx, rbx
0x1800042bc  jz      short loc_1800042CB
0x1800042be  mov     rcx, rbx; hObject
0x1800042c1  call    cs:__imp_CloseHandle
0x1800042c7  test    eax, eax
0x1800042c9  jz      short loc_1800042F3
0x1800042cb  xor     eax, eax
0x1800042cd  mov     rcx, [rbp+180h+var_30]
0x1800042d4  xor     rcx, rsp; StackCookie
0x1800042d7  call    __security_check_cookie
0x1800042dc  mov     rbx, [rsp+280h+arg_10]
0x1800042e4  add     rsp, 260h
0x1800042eb  pop     r15
0x1800042ed  pop     r14
0x1800042ef  pop     rdi
0x1800042f0  pop     rsi
0x1800042f1  pop     rbp
0x1800042f2  retn
0x1800042f3  mov     rcx, [rbp+188h]; this
0x1800042fa  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004301  mov     edx, 0A0Bh; void *
0x180004306  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000430c  mov     rcx, [rbp+188h]; this
0x180004313  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000431a  mov     edx, 0E01h; void *
0x18000431f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004325  mov     rcx, [rbp+188h]; this
0x18000432c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004333  mov     edx, 0A15h; void *
0x180004338  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000433e  mov     rcx, [rbp+188h]; this
0x180004345  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000434c  mov     edx, 0A0Bh; void *
0x180004351  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004357  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000435d  mov     rcx, [rbp+188h]; this
0x180004364  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000436b  mov     edx, 0A15h; void *
0x180004370  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004376  mov     rcx, [rbp+188h]; this
0x18000437d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004384  mov     edx, 0A0Bh; void *
0x180004389  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000438f  mov     rcx, [rbp+188h]; this
0x180004396  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000439d  mov     edx, 0A15h; void *
0x1800043a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
