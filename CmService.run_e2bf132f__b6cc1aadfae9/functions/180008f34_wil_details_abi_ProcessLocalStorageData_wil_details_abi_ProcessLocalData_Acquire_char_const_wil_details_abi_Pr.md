# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008f34`
- end: `0x180009313`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000ad18`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x1800089c0`
- `0x180008f34`
- `0x180009730`
- `0x18000a10c`
- `0x18000a9f0`
- `0x18000c0a4`
- `0x18000da88`
- `0x180015370`
- `0x1800158b4`
- `0x180016658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009079`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009196`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009239`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009079`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009196`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009239`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008fd9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008fd9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008fb2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008fb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009153`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009255`

## string_xrefs

- `0x1800092b9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned __int64 v28; // rax
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v36, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v34);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_23;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v22 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v20);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v35);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v36[0];
  v28 = v36[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v36[0] = 0;
  *((_QWORD *)v21 + 3) = v28;
  v36[1] = 0;
  memset_0((char *)v21 + 34, 0, 0x56u);
  *((_WORD *)v21 + 16) = 88;
  v21[9] = 1;
  memset_0(v21 + 10, 0, 0x50u);
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180008f34  mov     [rsp-8+arg_10], rbx
0x180008f39  push    rbp
0x180008f3a  push    rsi
0x180008f3b  push    rdi
0x180008f3c  push    r14
0x180008f3e  push    r15
0x180008f40  lea     rbp, [rsp-160h]
0x180008f48  sub     rsp, 260h
0x180008f4f  mov     rax, cs:__security_cookie
0x180008f56  xor     rax, rsp
0x180008f59  mov     [rbp+180h+var_30], rax
0x180008f60  mov     r15, rdx
0x180008f63  mov     qword ptr [rdx], 0
0x180008f6a  mov     rbx, rcx
0x180008f6d  call    cs:__imp_GetCurrentProcessId
0x180008f74  nop     dword ptr [rax+rax+00h]
0x180008f79  mov     r14d, 78h ; 'x'
0x180008f7f  mov     [rsp+280h+var_258], rbx
0x180008f84  mov     r9d, eax
0x180008f87  mov     [rsp+280h+var_260], r14d; int
0x180008f8c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008f93  mov     edx, 104h; unsigned __int64
0x180008f98  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008f9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008fa2  mov     r9d, 1F0001h; dwDesiredAccess
0x180008fa8  lea     rdx, [rsp+280h+Name]; lpName
0x180008fad  xor     r8d, r8d; dwFlags
0x180008fb0  xor     ecx, ecx; lpMutexAttributes
0x180008fb2  call    cs:__imp_CreateMutexExW
0x180008fb9  nop     dword ptr [rax+rax+00h]
0x180008fbe  mov     rbx, rax
0x180008fc1  test    rax, rax
0x180008fc4  jnz     short loc_180008FD0
0x180008fc6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008fcb  jmp     loc_180009267
0x180008fd0  xor     r8d, r8d; bAlertable
0x180008fd3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008fd6  mov     rcx, rbx; hHandle
0x180008fd9  call    cs:__imp_WaitForSingleObjectEx
0x180008fe0  nop     dword ptr [rax+rax+00h]
0x180008fe5  cmp     eax, 102h
0x180008fea  jz      short loc_180008FFC
0x180008fec  test    eax, 0FFFFFF7Fh
0x180008ff1  jnz     loc_1800092B2
0x180008ff7  mov     rdi, rbx
0x180008ffa  jmp     short loc_180008FFE
0x180008ffc  xor     edi, edi
0x180008ffe  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180009003  mov     [rsp+280h+var_250], 0
0x18000900c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009011  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009016  mov     esi, eax
0x180009018  test    eax, eax
0x18000901a  jns     loc_1800090AB
0x180009020  mov     rcx, [rbp+188h]; this
0x180009027  lea     r8, aWil; "wil"
0x18000902e  mov     r9d, eax; char *
0x180009031  mov     edx, 66h ; 'f'; void *
0x180009036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000903b  mov     rcx, [rbp+188h]; this
0x180009042  lea     r8, aWil; "wil"
0x180009049  mov     r9d, esi; char *
0x18000904c  mov     edx, 6Fh ; 'o'; void *
0x180009051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009056  mov     rcx, [rbp+188h]; this
0x18000905d  lea     r8, aWil; "wil"
0x180009064  mov     r9d, esi; char *
0x180009067  mov     edx, 12Eh; void *
0x18000906c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009071  test    rdi, rdi
0x180009074  jz      short loc_18000908D
0x180009076  mov     rcx, rdi; hMutex
0x180009079  call    cs:__imp_ReleaseMutex
0x180009080  nop     dword ptr [rax+rax+00h]
0x180009085  test    eax, eax
0x180009087  jz      loc_1800092CB
0x18000908d  mov     rcx, rbx; hObject
0x180009090  call    cs:__imp_CloseHandle
0x180009097  nop     dword ptr [rax+rax+00h]
0x18000909c  test    eax, eax
0x18000909e  jz      loc_1800092DD
0x1800090a4  mov     eax, esi
0x1800090a6  jmp     loc_180009267
0x1800090ab  mov     rax, [rsp+280h+var_250]
0x1800090b0  lea     rcx, ds:0[rax*4]
0x1800090b8  test    rcx, rcx
0x1800090bb  jz      short loc_1800090CB
0x1800090bd  mov     [r15], rcx
0x1800090c0  mov     eax, [rcx]
0x1800090c2  inc     eax
0x1800090c4  mov     [rcx], eax
0x1800090c6  jmp     loc_180009231
0x1800090cb  mov     rdx, r14; dwBytes
0x1800090ce  mov     qword ptr [r15], 0
0x1800090d5  mov     ecx, 8; dwFlags
0x1800090da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800090df  mov     r14, rax
0x1800090e2  test    rax, rax
0x1800090e5  jnz     short loc_180009109
0x1800090e7  mov     rcx, [rbp+188h]; this
0x1800090ee  lea     r8, aWil; "wil"
0x1800090f5  mov     esi, 8007000Eh
0x1800090fa  mov     edx, 14Bh; void *
0x1800090ff  mov     r9d, esi; char *
0x180009102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009107  jmp     short loc_180009173
0x180009109  xorps   xmm0, xmm0
0x18000910c  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009111  mov     r8, r14; void *
0x180009114  lea     rcx, [rsp+280h+var_250]; this
0x180009119  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000911f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180009124  mov     esi, eax
0x180009126  test    eax, eax
0x180009128  jns     loc_1800091C6
0x18000912e  mov     rcx, [rbp+188h]; this
0x180009135  lea     r8, aWil; "wil"
0x18000913c  mov     r9d, eax; char *
0x18000913f  mov     edx, 14Eh; void *
0x180009144  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009149  lea     rcx, [rsp+280h+var_250]; this
0x18000914e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009153  call    cs:__imp_GetProcessHeap
0x18000915a  nop     dword ptr [rax+rax+00h]
0x18000915f  mov     r8, r14; lpMem
0x180009162  xor     edx, edx; dwFlags
0x180009164  mov     rcx, rax; hHeap
0x180009167  call    cs:__imp_HeapFree
0x18000916e  nop     dword ptr [rax+rax+00h]
0x180009173  mov     rcx, [rbp+188h]; this
0x18000917a  lea     r8, aWil; "wil"
0x180009181  mov     r9d, esi; char *
0x180009184  mov     edx, 137h; void *
0x180009189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000918e  test    rdi, rdi
0x180009191  jz      short loc_1800091AA
0x180009193  mov     rcx, rdi; hMutex
0x180009196  call    cs:__imp_ReleaseMutex
0x18000919d  nop     dword ptr [rax+rax+00h]
0x1800091a2  test    eax, eax
0x1800091a4  jz      loc_1800092EF
0x1800091aa  mov     rcx, rbx; hObject
0x1800091ad  call    cs:__imp_CloseHandle
0x1800091b4  nop     dword ptr [rax+rax+00h]
0x1800091b9  test    eax, eax
0x1800091bb  jz      loc_1800092A0
0x1800091c1  jmp     loc_1800090A4
0x1800091c6  mov     rax, [rsp+280h+var_250]
0x1800091cb  lea     rcx, [r14+22h]; void *
0x1800091cf  xor     edx, edx; Val
0x1800091d1  mov     [r14+10h], rax
0x1800091d5  mov     rax, [rsp+280h+var_250+8]
0x1800091da  mov     dword ptr [r14], 1
0x1800091e1  mov     [r14+8], rbx
0x1800091e5  lea     r8d, [rdx+56h]; Size
0x1800091e9  mov     [rsp+280h+var_250], 0
0x1800091f2  mov     [r14+18h], rax
0x1800091f6  mov     [rsp+280h+var_250+8], 0
0x1800091ff  call    memset_0
0x180009204  xor     edx, edx; Val
0x180009206  mov     word ptr [r14+20h], 58h ; 'X'
0x18000920d  lea     rcx, [r14+28h]; void *
0x180009211  mov     dword ptr [r14+24h], 1
0x180009219  lea     r8d, [rdx+50h]; Size
0x18000921d  call    memset_0
0x180009222  lea     rcx, [rsp+280h+var_250]; this
0x180009227  mov     [r15], r14
0x18000922a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000922f  xor     ebx, ebx
0x180009231  test    rdi, rdi
0x180009234  jz      short loc_18000924D
0x180009236  mov     rcx, rdi; hMutex
0x180009239  call    cs:__imp_ReleaseMutex
0x180009240  nop     dword ptr [rax+rax+00h]
0x180009245  test    eax, eax
0x180009247  jz      loc_180009301
0x18000924d  test    rbx, rbx
0x180009250  jz      short loc_180009265
0x180009252  mov     rcx, rbx; hObject
0x180009255  call    cs:__imp_CloseHandle
0x18000925c  nop     dword ptr [rax+rax+00h]
0x180009261  test    eax, eax
0x180009263  jz      short loc_18000928E
0x180009265  xor     eax, eax
0x180009267  mov     rcx, [rbp+180h+var_30]
0x18000926e  xor     rcx, rsp; StackCookie
0x180009271  call    __security_check_cookie
0x180009276  mov     rbx, [rsp+280h+arg_10]
0x18000927e  add     rsp, 260h
0x180009285  pop     r15
0x180009287  pop     r14
0x180009289  pop     rdi
0x18000928a  pop     rsi
0x18000928b  pop     rbp
0x18000928c  retn
0x18000928e  mov     rcx, [rbp+188h]; this
0x180009295  mov     edx, 0A0Bh; void *
0x18000929a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092a0  mov     rcx, [rbp+188h]; this
0x1800092a7  mov     edx, 0A0Bh; void *
0x1800092ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092b2  mov     rcx, [rbp+188h]; this
0x1800092b9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800092c0  mov     edx, 0E01h; void *
0x1800092c5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800092cb  mov     rcx, [rbp+188h]; this
0x1800092d2  mov     edx, 0A15h; void *
0x1800092d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092dd  mov     rcx, [rbp+188h]; this
0x1800092e4  mov     edx, 0A0Bh; void *
0x1800092e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092ef  mov     rcx, [rbp+188h]; this
0x1800092f6  mov     edx, 0A15h; void *
0x1800092fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009301  mov     rcx, [rbp+188h]; this
0x180009308  mov     edx, 0A15h; void *
0x18000930d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
