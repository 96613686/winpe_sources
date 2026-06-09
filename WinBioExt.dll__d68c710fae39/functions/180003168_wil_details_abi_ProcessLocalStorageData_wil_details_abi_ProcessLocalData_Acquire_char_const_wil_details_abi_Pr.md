# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003168`
- end: `0x180003512`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004090`

## callees

- `0x180001610`
- `0x180002084`
- `0x180003168`
- `0x180003518`
- `0x1800037e4`
- `0x180003e28`
- `0x1800048f8`
- `0x180004cf4`
- `0x1800056e4`
- `0x18000579c`
- `0x180005b4c`
- `0x180005b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003282`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000341b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003282`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000341b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800031e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003201`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003389`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000336d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000336d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003431`

## string_xrefs

- `0x18000347c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _QWORD *v25; // rsi
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v25 = (_QWORD *)v22;
  if ( v22 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v22 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v24,
            v22 >> 2);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v39 = *(_OWORD *)hObject;
      *(_DWORD *)v25 = 1;
      v25[1] = v6;
      *((_OWORD *)v25 + 1) = v39;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v25;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v46);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return v26;
}

```

## disassembly

```asm
0x180003168  mov     [rsp-8+arg_10], rbx
0x18000316d  push    rbp
0x18000316e  push    rsi
0x18000316f  push    rdi
0x180003170  push    r14
0x180003172  push    r15
0x180003174  lea     rbp, [rsp-160h]
0x18000317c  sub     rsp, 260h
0x180003183  mov     rax, cs:__security_cookie
0x18000318a  xor     rax, rsp
0x18000318d  mov     [rbp+180h+var_30], rax
0x180003194  mov     r15, rdx
0x180003197  mov     qword ptr [rdx], 0
0x18000319e  mov     rbx, rcx
0x1800031a1  call    cs:__imp_GetCurrentProcessId
0x1800031a7  mov     r14d, 78h ; 'x'
0x1800031ad  mov     [rsp+280h+var_258], rbx
0x1800031b2  mov     r9d, eax
0x1800031b5  mov     [rsp+280h+var_260], r14d; int
0x1800031ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800031c1  mov     edx, 104h; unsigned __int64
0x1800031c6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800031cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800031d0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800031d6  lea     rdx, [rsp+280h+Name]; lpName
0x1800031db  xor     r8d, r8d; dwFlags
0x1800031de  xor     ecx, ecx; lpMutexAttributes
0x1800031e0  call    cs:__imp_CreateMutexExW
0x1800031e6  mov     rbx, rax
0x1800031e9  test    rax, rax
0x1800031ec  jnz     short loc_1800031F8
0x1800031ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800031f3  jmp     loc_18000343D
0x1800031f8  xor     r8d, r8d; bAlertable
0x1800031fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800031fe  mov     rcx, rbx; hHandle
0x180003201  call    cs:__imp_WaitForSingleObjectEx
0x180003207  cmp     eax, 102h
0x18000320c  jz      short loc_18000321E
0x18000320e  test    eax, 0FFFFFF7Fh
0x180003213  jnz     loc_180003475
0x180003219  mov     rdi, rbx
0x18000321c  jmp     short loc_180003220
0x18000321e  xor     edi, edi
0x180003220  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003225  mov     [rsp+280h+hObject], 0
0x18000322e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003233  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003238  mov     esi, eax
0x18000323a  test    eax, eax
0x18000323c  jns     short loc_1800032A8
0x18000323e  mov     rcx, [rbp+188h]; this
0x180003245  mov     r9d, eax; char *
0x180003248  mov     edx, 66h ; 'f'; void *
0x18000324d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003252  mov     rcx, [rbp+188h]; this
0x180003259  mov     r9d, esi; char *
0x18000325c  mov     edx, 6Fh ; 'o'; void *
0x180003261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003266  mov     rcx, [rbp+188h]; this
0x18000326d  mov     r9d, esi; char *
0x180003270  mov     edx, 12Eh; void *
0x180003275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000327a  test    rdi, rdi
0x18000327d  jz      short loc_180003290
0x18000327f  mov     rcx, rdi; hMutex
0x180003282  call    cs:__imp_ReleaseMutex
0x180003288  test    eax, eax
0x18000328a  jz      loc_18000348E
0x180003290  mov     rcx, rbx; hObject
0x180003293  call    cs:__imp_CloseHandle
0x180003299  test    eax, eax
0x18000329b  jz      loc_1800034A0
0x1800032a1  mov     eax, esi
0x1800032a3  jmp     loc_18000343D
0x1800032a8  mov     rax, [rsp+280h+hObject]
0x1800032ad  lea     rcx, ds:0[rax*4]
0x1800032b5  test    rcx, rcx
0x1800032b8  jz      short loc_1800032C8
0x1800032ba  mov     [r15], rcx
0x1800032bd  mov     eax, [rcx]
0x1800032bf  inc     eax
0x1800032c1  mov     [rcx], eax
0x1800032c3  jmp     loc_180003413
0x1800032c8  mov     rdx, r14; dwBytes
0x1800032cb  mov     qword ptr [r15], 0
0x1800032d2  mov     ecx, 8; dwFlags
0x1800032d7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800032dc  mov     rsi, rax
0x1800032df  test    rax, rax
0x1800032e2  jnz     short loc_180003303
0x1800032e4  mov     rcx, [rbp+188h]; this
0x1800032eb  mov     r14d, 8007000Eh
0x1800032f1  mov     r9d, r14d; char *
0x1800032f4  mov     edx, 14Bh; void *
0x1800032f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032fe  jmp     loc_18000338F
0x180003303  xorps   xmm0, xmm0
0x180003306  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000330c  test    sil, 3
0x180003310  jnz     loc_1800034B2
0x180003316  mov     r9, rsi
0x180003319  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000331e  shr     r9, 2; unsigned __int64
0x180003322  lea     rcx, [rsp+280h+hObject]; this
0x180003327  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000332c  mov     r14d, eax
0x18000332f  test    eax, eax
0x180003331  jns     loc_1800033CF
0x180003337  mov     rcx, [rbp+188h]; this
0x18000333e  mov     r9d, eax; char *
0x180003341  mov     edx, 14Eh; void *
0x180003346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000334b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003350  test    rcx, rcx
0x180003353  jz      short loc_180003363
0x180003355  call    cs:__imp_CloseHandle
0x18000335b  test    eax, eax
0x18000335d  jz      loc_1800034B8
0x180003363  mov     rcx, [rsp+280h+hObject]; hObject
0x180003368  test    rcx, rcx
0x18000336b  jz      short loc_18000337B
0x18000336d  call    cs:__imp_CloseHandle
0x180003373  test    eax, eax
0x180003375  jz      loc_1800034CA
0x18000337b  call    cs:__imp_GetProcessHeap
0x180003381  mov     r8, rsi; lpMem
0x180003384  xor     edx, edx; dwFlags
0x180003386  mov     rcx, rax; hHeap
0x180003389  call    cs:__imp_HeapFree
0x18000338f  mov     rcx, [rbp+188h]; this
0x180003396  mov     r9d, r14d; char *
0x180003399  mov     edx, 137h; void *
0x18000339e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033a3  test    rdi, rdi
0x1800033a6  jz      short loc_1800033B9
0x1800033a8  mov     rcx, rdi; hMutex
0x1800033ab  call    cs:__imp_ReleaseMutex
0x1800033b1  test    eax, eax
0x1800033b3  jz      loc_1800034DC
0x1800033b9  mov     rcx, rbx; hObject
0x1800033bc  call    cs:__imp_CloseHandle
0x1800033c2  test    eax, eax
0x1800033c4  jz      loc_1800034EE
0x1800033ca  mov     eax, r14d
0x1800033cd  jmp     short loc_18000343D
0x1800033cf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800033d4  xor     edx, edx; Val
0x1800033d6  mov     dword ptr [rsi], 1
0x1800033dc  lea     rcx, [rsi+22h]; void *
0x1800033e0  mov     [rsi+8], rbx
0x1800033e4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800033e9  lea     r8d, [rdx+56h]; Size
0x1800033ed  call    memset_0
0x1800033f2  xor     edx, edx; Val
0x1800033f4  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800033fa  lea     rcx, [rsi+28h]; void *
0x1800033fe  mov     dword ptr [rsi+24h], 1
0x180003405  lea     r8d, [rdx+50h]; Size
0x180003409  call    memset_0
0x18000340e  xor     ebx, ebx
0x180003410  mov     [r15], rsi
0x180003413  test    rdi, rdi
0x180003416  jz      short loc_180003429
0x180003418  mov     rcx, rdi; hMutex
0x18000341b  call    cs:__imp_ReleaseMutex
0x180003421  test    eax, eax
0x180003423  jz      loc_180003500
0x180003429  test    rbx, rbx
0x18000342c  jz      short loc_18000343B
0x18000342e  mov     rcx, rbx; hObject
0x180003431  call    cs:__imp_CloseHandle
0x180003437  test    eax, eax
0x180003439  jz      short loc_180003463
0x18000343b  xor     eax, eax
0x18000343d  mov     rcx, [rbp+180h+var_30]
0x180003444  xor     rcx, rsp; StackCookie
0x180003447  call    __security_check_cookie
0x18000344c  mov     rbx, [rsp+280h+arg_10]
0x180003454  add     rsp, 260h
0x18000345b  pop     r15
0x18000345d  pop     r14
0x18000345f  pop     rdi
0x180003460  pop     rsi
0x180003461  pop     rbp
0x180003462  retn
0x180003463  mov     rcx, [rbp+188h]; this
0x18000346a  mov     edx, 0A0Bh; void *
0x18000346f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003475  mov     rcx, [rbp+188h]; this
0x18000347c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003483  mov     edx, 0E01h; void *
0x180003488  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000348e  mov     rcx, [rbp+188h]; this
0x180003495  mov     edx, 0A15h; void *
0x18000349a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034a0  mov     rcx, [rbp+188h]; this
0x1800034a7  mov     edx, 0A0Bh; void *
0x1800034ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800034b8  mov     rcx, [rbp+188h]; this
0x1800034bf  mov     edx, 0A0Bh; void *
0x1800034c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034ca  mov     rcx, [rbp+188h]; this
0x1800034d1  mov     edx, 0A0Bh; void *
0x1800034d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034dc  mov     rcx, [rbp+188h]; this
0x1800034e3  mov     edx, 0A15h; void *
0x1800034e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034ee  mov     rcx, [rbp+188h]; this
0x1800034f5  mov     edx, 0A0Bh; void *
0x1800034fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003500  mov     rcx, [rbp+188h]; this
0x180003507  mov     edx, 0A15h; void *
0x18000350c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
