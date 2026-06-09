# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004148`
- end: `0x180004515`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800059f0`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180004148`
- `0x180004918`
- `0x180004e60`
- `0x180005788`
- `0x180006478`
- `0x180007be4`
- `0x1800086d8`
- `0x180008b6c`
- `0x18000943c`
- `0x18000944c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800041c0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800041c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004277`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004425`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004277`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000437e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000437e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000438c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000438c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443b`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180004148  mov     [rsp-8+arg_10], rbx
0x18000414d  push    rbp
0x18000414e  push    rsi
0x18000414f  push    rdi
0x180004150  push    r14
0x180004152  push    r15
0x180004154  lea     rbp, [rsp-160h]
0x18000415c  sub     rsp, 260h
0x180004163  mov     rax, cs:__security_cookie
0x18000416a  xor     rax, rsp
0x18000416d  mov     [rbp+180h+var_30], rax
0x180004174  mov     r15, rdx
0x180004177  mov     qword ptr [rdx], 0
0x18000417e  mov     rbx, rcx
0x180004181  call    cs:__imp_GetCurrentProcessId
0x180004187  mov     r14d, 78h ; 'x'
0x18000418d  mov     [rsp+280h+var_258], rbx
0x180004192  mov     r9d, eax
0x180004195  mov     [rsp+280h+var_260], r14d; int
0x18000419a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800041a1  mov     edx, 104h; unsigned __int64
0x1800041a6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800041ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800041b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800041b6  lea     rdx, [rsp+280h+Name]; lpName
0x1800041bb  xor     r8d, r8d; dwFlags
0x1800041be  xor     ecx, ecx; lpMutexAttributes
0x1800041c0  call    cs:__imp_CreateMutexExW
0x1800041c6  mov     rbx, rax
0x1800041c9  test    rax, rax
0x1800041cc  jnz     short loc_1800041D8
0x1800041ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800041d3  jmp     loc_180004447
0x1800041d8  xor     r8d, r8d; bAlertable
0x1800041db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800041de  mov     rcx, rbx; hHandle
0x1800041e1  call    cs:__imp_WaitForSingleObjectEx
0x1800041e7  cmp     eax, 102h
0x1800041ec  jz      short loc_1800041FE
0x1800041ee  test    eax, 0FFFFFF7Fh
0x1800041f3  jnz     loc_18000447F
0x1800041f9  mov     rdi, rbx
0x1800041fc  jmp     short loc_180004200
0x1800041fe  xor     edi, edi
0x180004200  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004205  mov     [rsp+280h+hObject], 0
0x18000420e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004213  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004218  mov     esi, eax
0x18000421a  test    eax, eax
0x18000421c  jns     short loc_18000429D
0x18000421e  mov     rcx, [rbp+188h]; this
0x180004225  lea     r8, aWil; "wil"
0x18000422c  mov     r9d, eax; char *
0x18000422f  mov     edx, 66h ; 'f'; void *
0x180004234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004239  mov     rcx, [rbp+188h]; this
0x180004240  lea     r8, aWil; "wil"
0x180004247  mov     r9d, esi; char *
0x18000424a  mov     edx, 6Fh ; 'o'; void *
0x18000424f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004254  mov     rcx, [rbp+188h]; this
0x18000425b  lea     r8, aWil; "wil"
0x180004262  mov     r9d, esi; char *
0x180004265  mov     edx, 12Eh; void *
0x18000426a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000426f  test    rdi, rdi
0x180004272  jz      short loc_180004285
0x180004274  mov     rcx, rdi; hMutex
0x180004277  call    cs:__imp_ReleaseMutex
0x18000427d  test    eax, eax
0x18000427f  jz      loc_180004491
0x180004285  mov     rcx, rbx; hObject
0x180004288  call    cs:__imp_CloseHandle
0x18000428e  test    eax, eax
0x180004290  jz      loc_1800044A3
0x180004296  mov     eax, esi
0x180004298  jmp     loc_180004447
0x18000429d  mov     rax, [rsp+280h+hObject]
0x1800042a2  lea     rcx, ds:0[rax*4]
0x1800042aa  test    rcx, rcx
0x1800042ad  jz      short loc_1800042BD
0x1800042af  mov     [r15], rcx
0x1800042b2  mov     eax, [rcx]
0x1800042b4  inc     eax
0x1800042b6  mov     [rcx], eax
0x1800042b8  jmp     loc_18000441D
0x1800042bd  mov     rdx, r14; dwBytes
0x1800042c0  mov     qword ptr [r15], 0
0x1800042c7  mov     ecx, 8; dwFlags
0x1800042cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800042d1  mov     rsi, rax
0x1800042d4  test    rax, rax
0x1800042d7  jnz     short loc_1800042FF
0x1800042d9  mov     rcx, [rbp+188h]; this
0x1800042e0  lea     r8, aWil; "wil"
0x1800042e7  mov     r14d, 8007000Eh
0x1800042ed  mov     edx, 14Bh; void *
0x1800042f2  mov     r9d, r14d; char *
0x1800042f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042fa  jmp     loc_180004392
0x1800042ff  xorps   xmm0, xmm0
0x180004302  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004308  test    sil, 3
0x18000430c  jnz     loc_1800044B5
0x180004312  mov     r9, rsi
0x180004315  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000431a  shr     r9, 2; unsigned __int64
0x18000431e  lea     rcx, [rsp+280h+hObject]; this
0x180004323  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004328  mov     r14d, eax
0x18000432b  test    eax, eax
0x18000432d  jns     loc_1800043D9
0x180004333  mov     rcx, [rbp+188h]; this
0x18000433a  lea     r8, aWil; "wil"
0x180004341  mov     r9d, eax; char *
0x180004344  mov     edx, 14Eh; void *
0x180004349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000434e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004353  test    rcx, rcx
0x180004356  jz      short loc_180004366
0x180004358  call    cs:__imp_CloseHandle
0x18000435e  test    eax, eax
0x180004360  jz      loc_1800044BB
0x180004366  mov     rcx, [rsp+280h+hObject]; hObject
0x18000436b  test    rcx, rcx
0x18000436e  jz      short loc_18000437E
0x180004370  call    cs:__imp_CloseHandle
0x180004376  test    eax, eax
0x180004378  jz      loc_1800044CD
0x18000437e  call    cs:__imp_GetProcessHeap
0x180004384  mov     r8, rsi; lpMem
0x180004387  xor     edx, edx; dwFlags
0x180004389  mov     rcx, rax; hHeap
0x18000438c  call    cs:__imp_HeapFree
0x180004392  mov     rcx, [rbp+188h]; this
0x180004399  lea     r8, aWil; "wil"
0x1800043a0  mov     r9d, r14d; char *
0x1800043a3  mov     edx, 137h; void *
0x1800043a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043ad  test    rdi, rdi
0x1800043b0  jz      short loc_1800043C3
0x1800043b2  mov     rcx, rdi; hMutex
0x1800043b5  call    cs:__imp_ReleaseMutex
0x1800043bb  test    eax, eax
0x1800043bd  jz      loc_1800044DF
0x1800043c3  mov     rcx, rbx; hObject
0x1800043c6  call    cs:__imp_CloseHandle
0x1800043cc  test    eax, eax
0x1800043ce  jz      loc_1800044F1
0x1800043d4  mov     eax, r14d
0x1800043d7  jmp     short loc_180004447
0x1800043d9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800043de  xor     edx, edx; Val
0x1800043e0  mov     dword ptr [rsi], 1
0x1800043e6  lea     rcx, [rsi+22h]; void *
0x1800043ea  mov     [rsi+8], rbx
0x1800043ee  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800043f3  lea     r8d, [rdx+56h]; Size
0x1800043f7  call    memset_0
0x1800043fc  xor     edx, edx; Val
0x1800043fe  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004404  lea     rcx, [rsi+28h]; void *
0x180004408  mov     dword ptr [rsi+24h], 1
0x18000440f  lea     r8d, [rdx+50h]; Size
0x180004413  call    memset_0
0x180004418  xor     ebx, ebx
0x18000441a  mov     [r15], rsi
0x18000441d  test    rdi, rdi
0x180004420  jz      short loc_180004433
0x180004422  mov     rcx, rdi; hMutex
0x180004425  call    cs:__imp_ReleaseMutex
0x18000442b  test    eax, eax
0x18000442d  jz      loc_180004503
0x180004433  test    rbx, rbx
0x180004436  jz      short loc_180004445
0x180004438  mov     rcx, rbx; hObject
0x18000443b  call    cs:__imp_CloseHandle
0x180004441  test    eax, eax
0x180004443  jz      short loc_18000446D
0x180004445  xor     eax, eax
0x180004447  mov     rcx, [rbp+180h+var_30]
0x18000444e  xor     rcx, rsp; StackCookie
0x180004451  call    __security_check_cookie
0x180004456  mov     rbx, [rsp+280h+arg_10]
0x18000445e  add     rsp, 260h
0x180004465  pop     r15
0x180004467  pop     r14
0x180004469  pop     rdi
0x18000446a  pop     rsi
0x18000446b  pop     rbp
0x18000446c  retn
0x18000446d  mov     rcx, [rbp+188h]; this
0x180004474  mov     edx, 0A0Bh; void *
0x180004479  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000447f  mov     rcx, [rbp+188h]; this
0x180004486  mov     edx, 0E01h; void *
0x18000448b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004491  mov     rcx, [rbp+188h]; this
0x180004498  mov     edx, 0A15h; void *
0x18000449d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044a3  mov     rcx, [rbp+188h]; this
0x1800044aa  mov     edx, 0A0Bh; void *
0x1800044af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044b5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800044bb  mov     rcx, [rbp+188h]; this
0x1800044c2  mov     edx, 0A0Bh; void *
0x1800044c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044cd  mov     rcx, [rbp+188h]; this
0x1800044d4  mov     edx, 0A0Bh; void *
0x1800044d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044df  mov     rcx, [rbp+188h]; this
0x1800044e6  mov     edx, 0A15h; void *
0x1800044eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044f1  mov     rcx, [rbp+188h]; this
0x1800044f8  mov     edx, 0A0Bh; void *
0x1800044fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004503  mov     rcx, [rbp+188h]; this
0x18000450a  mov     edx, 0A15h; void *
0x18000450f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
