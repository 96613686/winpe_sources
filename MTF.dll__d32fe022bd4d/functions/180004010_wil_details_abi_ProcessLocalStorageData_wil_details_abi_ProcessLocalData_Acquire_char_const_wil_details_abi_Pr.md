# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004010`
- end: `0x1800043e4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004fd4`

## callees

- `0x180004010`
- `0x1800043ec`
- `0x1800046d4`
- `0x180004cc8`
- `0x18000599c`
- `0x180006074`
- `0x1800068a4`
- `0x18000697c`
- `0x180006f00`
- `0x180006f10`
- `0x18002bc62`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004088`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004088`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800040a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800040a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000413f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000427d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000413f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000427d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004246`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004246`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004254`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000428e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000428e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004303`

## string_xrefs

- `0x18000434e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x180004010  mov     [rsp-8+arg_10], rbx
0x180004015  push    rbp
0x180004016  push    rsi
0x180004017  push    rdi
0x180004018  push    r14
0x18000401a  push    r15
0x18000401c  lea     rbp, [rsp-160h]
0x180004024  sub     rsp, 260h
0x18000402b  mov     rax, cs:__security_cookie
0x180004032  xor     rax, rsp
0x180004035  mov     [rbp+180h+var_30], rax
0x18000403c  mov     r15, rdx
0x18000403f  mov     qword ptr [rdx], 0
0x180004046  mov     rbx, rcx
0x180004049  call    cs:__imp_GetCurrentProcessId
0x18000404f  mov     r14d, 78h ; 'x'
0x180004055  mov     [rsp+280h+var_258], rbx
0x18000405a  mov     r9d, eax
0x18000405d  mov     [rsp+280h+var_260], r14d; int
0x180004062  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004069  mov     edx, 104h; unsigned __int64
0x18000406e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004073  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004078  mov     r9d, 1F0001h; dwDesiredAccess
0x18000407e  lea     rdx, [rsp+280h+Name]; lpName
0x180004083  xor     r8d, r8d; dwFlags
0x180004086  xor     ecx, ecx; lpMutexAttributes
0x180004088  call    cs:__imp_CreateMutexExW
0x18000408e  mov     rbx, rax
0x180004091  test    rax, rax
0x180004094  jnz     short loc_1800040A0
0x180004096  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000409b  jmp     loc_18000430F
0x1800040a0  xor     r8d, r8d; bAlertable
0x1800040a3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800040a6  mov     rcx, rbx; hHandle
0x1800040a9  call    cs:__imp_WaitForSingleObjectEx
0x1800040af  cmp     eax, 102h
0x1800040b4  jz      short loc_1800040C6
0x1800040b6  test    eax, 0FFFFFF7Fh
0x1800040bb  jnz     loc_180004347
0x1800040c1  mov     rdi, rbx
0x1800040c4  jmp     short loc_1800040C8
0x1800040c6  xor     edi, edi
0x1800040c8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800040cd  mov     [rsp+280h+hObject], 0
0x1800040d6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800040db  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800040e0  mov     esi, eax
0x1800040e2  test    eax, eax
0x1800040e4  jns     short loc_180004165
0x1800040e6  mov     rcx, [rbp+188h]; this
0x1800040ed  lea     r8, aWil; "wil"
0x1800040f4  mov     r9d, eax; char *
0x1800040f7  mov     edx, 66h ; 'f'; void *
0x1800040fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004101  mov     rcx, [rbp+188h]; this
0x180004108  lea     r8, aWil; "wil"
0x18000410f  mov     r9d, esi; char *
0x180004112  mov     edx, 6Fh ; 'o'; void *
0x180004117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000411c  mov     rcx, [rbp+188h]; this
0x180004123  lea     r8, aWil; "wil"
0x18000412a  mov     r9d, esi; char *
0x18000412d  mov     edx, 12Eh; void *
0x180004132  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004137  test    rdi, rdi
0x18000413a  jz      short loc_18000414D
0x18000413c  mov     rcx, rdi; hMutex
0x18000413f  call    cs:__imp_ReleaseMutex
0x180004145  test    eax, eax
0x180004147  jz      loc_180004360
0x18000414d  mov     rcx, rbx; hObject
0x180004150  call    cs:__imp_CloseHandle
0x180004156  test    eax, eax
0x180004158  jz      loc_180004372
0x18000415e  mov     eax, esi
0x180004160  jmp     loc_18000430F
0x180004165  mov     rax, [rsp+280h+hObject]
0x18000416a  lea     rcx, ds:0[rax*4]
0x180004172  test    rcx, rcx
0x180004175  jz      short loc_180004185
0x180004177  mov     [r15], rcx
0x18000417a  mov     eax, [rcx]
0x18000417c  inc     eax
0x18000417e  mov     [rcx], eax
0x180004180  jmp     loc_1800042E5
0x180004185  mov     rdx, r14; dwBytes
0x180004188  mov     qword ptr [r15], 0
0x18000418f  mov     ecx, 8; dwFlags
0x180004194  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004199  mov     rsi, rax
0x18000419c  test    rax, rax
0x18000419f  jnz     short loc_1800041C7
0x1800041a1  mov     rcx, [rbp+188h]; this
0x1800041a8  lea     r8, aWil; "wil"
0x1800041af  mov     r14d, 8007000Eh
0x1800041b5  mov     edx, 14Bh; void *
0x1800041ba  mov     r9d, r14d; char *
0x1800041bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041c2  jmp     loc_18000425A
0x1800041c7  xorps   xmm0, xmm0
0x1800041ca  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800041d0  test    sil, 3
0x1800041d4  jnz     loc_180004384
0x1800041da  mov     r9, rsi
0x1800041dd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800041e2  shr     r9, 2; unsigned __int64
0x1800041e6  lea     rcx, [rsp+280h+hObject]; this
0x1800041eb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800041f0  mov     r14d, eax
0x1800041f3  test    eax, eax
0x1800041f5  jns     loc_1800042A1
0x1800041fb  mov     rcx, [rbp+188h]; this
0x180004202  lea     r8, aWil; "wil"
0x180004209  mov     r9d, eax; char *
0x18000420c  mov     edx, 14Eh; void *
0x180004211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004216  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000421b  test    rcx, rcx
0x18000421e  jz      short loc_18000422E
0x180004220  call    cs:__imp_CloseHandle
0x180004226  test    eax, eax
0x180004228  jz      loc_18000438A
0x18000422e  mov     rcx, [rsp+280h+hObject]; hObject
0x180004233  test    rcx, rcx
0x180004236  jz      short loc_180004246
0x180004238  call    cs:__imp_CloseHandle
0x18000423e  test    eax, eax
0x180004240  jz      loc_18000439C
0x180004246  call    cs:__imp_GetProcessHeap
0x18000424c  mov     r8, rsi; lpMem
0x18000424f  xor     edx, edx; dwFlags
0x180004251  mov     rcx, rax; hHeap
0x180004254  call    cs:__imp_HeapFree
0x18000425a  mov     rcx, [rbp+188h]; this
0x180004261  lea     r8, aWil; "wil"
0x180004268  mov     r9d, r14d; char *
0x18000426b  mov     edx, 137h; void *
0x180004270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004275  test    rdi, rdi
0x180004278  jz      short loc_18000428B
0x18000427a  mov     rcx, rdi; hMutex
0x18000427d  call    cs:__imp_ReleaseMutex
0x180004283  test    eax, eax
0x180004285  jz      loc_1800043AE
0x18000428b  mov     rcx, rbx; hObject
0x18000428e  call    cs:__imp_CloseHandle
0x180004294  test    eax, eax
0x180004296  jz      loc_1800043C0
0x18000429c  mov     eax, r14d
0x18000429f  jmp     short loc_18000430F
0x1800042a1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800042a6  xor     edx, edx; Val
0x1800042a8  mov     dword ptr [rsi], 1
0x1800042ae  lea     rcx, [rsi+22h]; void *
0x1800042b2  mov     [rsi+8], rbx
0x1800042b6  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800042bb  lea     r8d, [rdx+56h]; Size
0x1800042bf  call    memset_0
0x1800042c4  xor     edx, edx; Val
0x1800042c6  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800042cc  lea     rcx, [rsi+28h]; void *
0x1800042d0  mov     dword ptr [rsi+24h], 1
0x1800042d7  lea     r8d, [rdx+50h]; Size
0x1800042db  call    memset_0
0x1800042e0  xor     ebx, ebx
0x1800042e2  mov     [r15], rsi
0x1800042e5  test    rdi, rdi
0x1800042e8  jz      short loc_1800042FB
0x1800042ea  mov     rcx, rdi; hMutex
0x1800042ed  call    cs:__imp_ReleaseMutex
0x1800042f3  test    eax, eax
0x1800042f5  jz      loc_1800043D2
0x1800042fb  test    rbx, rbx
0x1800042fe  jz      short loc_18000430D
0x180004300  mov     rcx, rbx; hObject
0x180004303  call    cs:__imp_CloseHandle
0x180004309  test    eax, eax
0x18000430b  jz      short loc_180004335
0x18000430d  xor     eax, eax
0x18000430f  mov     rcx, [rbp+180h+var_30]
0x180004316  xor     rcx, rsp; StackCookie
0x180004319  call    __security_check_cookie
0x18000431e  mov     rbx, [rsp+280h+arg_10]
0x180004326  add     rsp, 260h
0x18000432d  pop     r15
0x18000432f  pop     r14
0x180004331  pop     rdi
0x180004332  pop     rsi
0x180004333  pop     rbp
0x180004334  retn
0x180004335  mov     rcx, [rbp+188h]; this
0x18000433c  mov     edx, 0A0Bh; void *
0x180004341  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004347  mov     rcx, [rbp+188h]; this
0x18000434e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004355  mov     edx, 0E01h; void *
0x18000435a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004360  mov     rcx, [rbp+188h]; this
0x180004367  mov     edx, 0A15h; void *
0x18000436c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004372  mov     rcx, [rbp+188h]; this
0x180004379  mov     edx, 0A0Bh; void *
0x18000437e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004384  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000438a  mov     rcx, [rbp+188h]; this
0x180004391  mov     edx, 0A0Bh; void *
0x180004396  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000439c  mov     rcx, [rbp+188h]; this
0x1800043a3  mov     edx, 0A0Bh; void *
0x1800043a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800043ae  mov     rcx, [rbp+188h]; this
0x1800043b5  mov     edx, 0A15h; void *
0x1800043ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800043c0  mov     rcx, [rbp+188h]; this
0x1800043c7  mov     edx, 0A0Bh; void *
0x1800043cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800043d2  mov     rcx, [rbp+188h]; this
0x1800043d9  mov     edx, 0A15h; void *
0x1800043de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
