# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008080`
- end: `0x180008454`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008a9c`

## callees

- `0x1800056e4`
- `0x18000694c`
- `0x180006ea0`
- `0x1800071d4`
- `0x1800071e4`
- `0x180008080`
- `0x18000845c`
- `0x180008834`
- `0x1800097b0`
- `0x18000986c`
- `0x18000e962`
- `0x18000e990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800080b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800080b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800081af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000835d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800081af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000835d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080f8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800080f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008119`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008373`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008373`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082c4`

## string_xrefs

- `0x1800083be`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x180008080  mov     [rsp-8+arg_10], rbx
0x180008085  push    rbp
0x180008086  push    rsi
0x180008087  push    rdi
0x180008088  push    r14
0x18000808a  push    r15
0x18000808c  lea     rbp, [rsp-160h]
0x180008094  sub     rsp, 260h
0x18000809b  mov     rax, cs:__security_cookie
0x1800080a2  xor     rax, rsp
0x1800080a5  mov     [rbp+180h+var_30], rax
0x1800080ac  mov     r15, rdx
0x1800080af  mov     qword ptr [rdx], 0
0x1800080b6  mov     rbx, rcx
0x1800080b9  call    cs:__imp_GetCurrentProcessId
0x1800080bf  mov     r14d, 78h ; 'x'
0x1800080c5  mov     [rsp+280h+var_258], rbx
0x1800080ca  mov     r9d, eax
0x1800080cd  mov     [rsp+280h+var_260], r14d; int
0x1800080d2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800080d9  mov     edx, 104h; unsigned __int64
0x1800080de  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800080e3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800080e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800080ee  lea     rdx, [rsp+280h+Name]; lpName
0x1800080f3  xor     r8d, r8d; dwFlags
0x1800080f6  xor     ecx, ecx; lpMutexAttributes
0x1800080f8  call    cs:__imp_CreateMutexExW
0x1800080fe  mov     rbx, rax
0x180008101  test    rax, rax
0x180008104  jnz     short loc_180008110
0x180008106  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000810b  jmp     loc_18000837F
0x180008110  xor     r8d, r8d; bAlertable
0x180008113  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008116  mov     rcx, rbx; hHandle
0x180008119  call    cs:__imp_WaitForSingleObjectEx
0x18000811f  cmp     eax, 102h
0x180008124  jz      short loc_180008136
0x180008126  test    eax, 0FFFFFF7Fh
0x18000812b  jnz     loc_1800083B7
0x180008131  mov     rdi, rbx
0x180008134  jmp     short loc_180008138
0x180008136  xor     edi, edi
0x180008138  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000813d  mov     [rsp+280h+hObject], 0
0x180008146  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000814b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180008150  mov     esi, eax
0x180008152  test    eax, eax
0x180008154  jns     short loc_1800081D5
0x180008156  mov     rcx, [rbp+188h]; this
0x18000815d  lea     r8, aWil; "wil"
0x180008164  mov     r9d, eax; char *
0x180008167  mov     edx, 66h ; 'f'; void *
0x18000816c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008171  mov     rcx, [rbp+188h]; this
0x180008178  lea     r8, aWil; "wil"
0x18000817f  mov     r9d, esi; char *
0x180008182  mov     edx, 6Fh ; 'o'; void *
0x180008187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000818c  mov     rcx, [rbp+188h]; this
0x180008193  lea     r8, aWil; "wil"
0x18000819a  mov     r9d, esi; char *
0x18000819d  mov     edx, 12Eh; void *
0x1800081a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081a7  test    rdi, rdi
0x1800081aa  jz      short loc_1800081BD
0x1800081ac  mov     rcx, rdi; hMutex
0x1800081af  call    cs:__imp_ReleaseMutex
0x1800081b5  test    eax, eax
0x1800081b7  jz      loc_1800083D0
0x1800081bd  mov     rcx, rbx; hObject
0x1800081c0  call    cs:__imp_CloseHandle
0x1800081c6  test    eax, eax
0x1800081c8  jz      loc_1800083E2
0x1800081ce  mov     eax, esi
0x1800081d0  jmp     loc_18000837F
0x1800081d5  mov     rax, [rsp+280h+hObject]
0x1800081da  lea     rcx, ds:0[rax*4]
0x1800081e2  test    rcx, rcx
0x1800081e5  jz      short loc_1800081F5
0x1800081e7  mov     [r15], rcx
0x1800081ea  mov     eax, [rcx]
0x1800081ec  inc     eax
0x1800081ee  mov     [rcx], eax
0x1800081f0  jmp     loc_180008355
0x1800081f5  mov     rdx, r14; dwBytes
0x1800081f8  mov     qword ptr [r15], 0
0x1800081ff  mov     ecx, 8; dwFlags
0x180008204  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008209  mov     rsi, rax
0x18000820c  test    rax, rax
0x18000820f  jnz     short loc_180008237
0x180008211  mov     rcx, [rbp+188h]; this
0x180008218  lea     r8, aWil; "wil"
0x18000821f  mov     r14d, 8007000Eh
0x180008225  mov     edx, 14Bh; void *
0x18000822a  mov     r9d, r14d; char *
0x18000822d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008232  jmp     loc_1800082CA
0x180008237  xorps   xmm0, xmm0
0x18000823a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008240  test    sil, 3
0x180008244  jnz     loc_1800083F4
0x18000824a  mov     r9, rsi
0x18000824d  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180008252  shr     r9, 2; unsigned __int64
0x180008256  lea     rcx, [rsp+280h+hObject]; this
0x18000825b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180008260  mov     r14d, eax
0x180008263  test    eax, eax
0x180008265  jns     loc_180008311
0x18000826b  mov     rcx, [rbp+188h]; this
0x180008272  lea     r8, aWil; "wil"
0x180008279  mov     r9d, eax; char *
0x18000827c  mov     edx, 14Eh; void *
0x180008281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008286  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000828b  test    rcx, rcx
0x18000828e  jz      short loc_18000829E
0x180008290  call    cs:__imp_CloseHandle
0x180008296  test    eax, eax
0x180008298  jz      loc_1800083FA
0x18000829e  mov     rcx, [rsp+280h+hObject]; hObject
0x1800082a3  test    rcx, rcx
0x1800082a6  jz      short loc_1800082B6
0x1800082a8  call    cs:__imp_CloseHandle
0x1800082ae  test    eax, eax
0x1800082b0  jz      loc_18000840C
0x1800082b6  call    cs:__imp_GetProcessHeap
0x1800082bc  mov     r8, rsi; lpMem
0x1800082bf  xor     edx, edx; dwFlags
0x1800082c1  mov     rcx, rax; hHeap
0x1800082c4  call    cs:__imp_HeapFree
0x1800082ca  mov     rcx, [rbp+188h]; this
0x1800082d1  lea     r8, aWil; "wil"
0x1800082d8  mov     r9d, r14d; char *
0x1800082db  mov     edx, 137h; void *
0x1800082e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082e5  test    rdi, rdi
0x1800082e8  jz      short loc_1800082FB
0x1800082ea  mov     rcx, rdi; hMutex
0x1800082ed  call    cs:__imp_ReleaseMutex
0x1800082f3  test    eax, eax
0x1800082f5  jz      loc_18000841E
0x1800082fb  mov     rcx, rbx; hObject
0x1800082fe  call    cs:__imp_CloseHandle
0x180008304  test    eax, eax
0x180008306  jz      loc_180008430
0x18000830c  mov     eax, r14d
0x18000830f  jmp     short loc_18000837F
0x180008311  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008316  xor     edx, edx; Val
0x180008318  mov     dword ptr [rsi], 1
0x18000831e  lea     rcx, [rsi+22h]; void *
0x180008322  mov     [rsi+8], rbx
0x180008326  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000832b  lea     r8d, [rdx+56h]; Size
0x18000832f  call    memset_0
0x180008334  xor     edx, edx; Val
0x180008336  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000833c  lea     rcx, [rsi+28h]; void *
0x180008340  mov     dword ptr [rsi+24h], 1
0x180008347  lea     r8d, [rdx+50h]; Size
0x18000834b  call    memset_0
0x180008350  xor     ebx, ebx
0x180008352  mov     [r15], rsi
0x180008355  test    rdi, rdi
0x180008358  jz      short loc_18000836B
0x18000835a  mov     rcx, rdi; hMutex
0x18000835d  call    cs:__imp_ReleaseMutex
0x180008363  test    eax, eax
0x180008365  jz      loc_180008442
0x18000836b  test    rbx, rbx
0x18000836e  jz      short loc_18000837D
0x180008370  mov     rcx, rbx; hObject
0x180008373  call    cs:__imp_CloseHandle
0x180008379  test    eax, eax
0x18000837b  jz      short loc_1800083A5
0x18000837d  xor     eax, eax
0x18000837f  mov     rcx, [rbp+180h+var_30]
0x180008386  xor     rcx, rsp; StackCookie
0x180008389  call    __security_check_cookie
0x18000838e  mov     rbx, [rsp+280h+arg_10]
0x180008396  add     rsp, 260h
0x18000839d  pop     r15
0x18000839f  pop     r14
0x1800083a1  pop     rdi
0x1800083a2  pop     rsi
0x1800083a3  pop     rbp
0x1800083a4  retn
0x1800083a5  mov     rcx, [rbp+188h]; this
0x1800083ac  mov     edx, 0A0Bh; void *
0x1800083b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083b7  mov     rcx, [rbp+188h]; this
0x1800083be  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800083c5  mov     edx, 0E01h; void *
0x1800083ca  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800083d0  mov     rcx, [rbp+188h]; this
0x1800083d7  mov     edx, 0A15h; void *
0x1800083dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083e2  mov     rcx, [rbp+188h]; this
0x1800083e9  mov     edx, 0A0Bh; void *
0x1800083ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800083fa  mov     rcx, [rbp+188h]; this
0x180008401  mov     edx, 0A0Bh; void *
0x180008406  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000840c  mov     rcx, [rbp+188h]; this
0x180008413  mov     edx, 0A0Bh; void *
0x180008418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000841e  mov     rcx, [rbp+188h]; this
0x180008425  mov     edx, 0A15h; void *
0x18000842a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008430  mov     rcx, [rbp+188h]; this
0x180008437  mov     edx, 0A0Bh; void *
0x18000843c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008442  mov     rcx, [rbp+188h]; this
0x180008449  mov     edx, 0A15h; void *
0x18000844e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
