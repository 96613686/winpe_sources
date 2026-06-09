# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003018`
- end: `0x1800033e0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003ee0`

## callees

- `0x1800016a0`
- `0x180002058`
- `0x180003018`
- `0x1800033e8`
- `0x180003630`
- `0x180003c78`
- `0x180004758`
- `0x180004bc4`
- `0x180005550`
- `0x18000560c`
- `0x1800059cc`
- `0x1800059dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003147`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003285`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800032f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003147`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003285`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800032f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800030b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800030b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003090`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003090`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000325c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000325c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000324e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000324e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003051`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000330b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000330b`

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
  void *v9; // rdx
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
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
0x180003018  mov     [rsp-8+arg_10], rbx
0x18000301d  push    rbp
0x18000301e  push    rsi
0x18000301f  push    rdi
0x180003020  push    r14
0x180003022  push    r15
0x180003024  lea     rbp, [rsp-160h]
0x18000302c  sub     rsp, 260h
0x180003033  mov     rax, cs:__security_cookie
0x18000303a  xor     rax, rsp
0x18000303d  mov     [rbp+180h+var_30], rax
0x180003044  mov     r15, rdx
0x180003047  mov     qword ptr [rdx], 0
0x18000304e  mov     rbx, rcx
0x180003051  call    cs:__imp_GetCurrentProcessId
0x180003057  mov     r14d, 78h ; 'x'
0x18000305d  mov     [rsp+280h+var_258], rbx
0x180003062  mov     r9d, eax
0x180003065  mov     [rsp+280h+var_260], r14d; int
0x18000306a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003071  mov     edx, 104h; unsigned __int64
0x180003076  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000307b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003080  mov     r9d, 1F0001h; dwDesiredAccess
0x180003086  lea     rdx, [rsp+280h+Name]; lpName
0x18000308b  xor     r8d, r8d; dwFlags
0x18000308e  xor     ecx, ecx; lpMutexAttributes
0x180003090  call    cs:__imp_CreateMutexExW
0x180003096  mov     rbx, rax
0x180003099  test    rax, rax
0x18000309c  jnz     short loc_1800030A8
0x18000309e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800030a3  jmp     loc_180003317
0x1800030a8  xor     r8d, r8d; bAlertable
0x1800030ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800030ae  mov     rcx, rbx; hHandle
0x1800030b1  call    cs:__imp_WaitForSingleObjectEx
0x1800030b7  cmp     eax, 102h
0x1800030bc  jz      short loc_1800030CE
0x1800030be  test    eax, 0FFFFFF7Fh
0x1800030c3  jnz     loc_18000334F
0x1800030c9  mov     rdi, rbx
0x1800030cc  jmp     short loc_1800030D0
0x1800030ce  xor     edi, edi
0x1800030d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800030d5  mov     [rsp+280h+hObject], 0
0x1800030de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800030e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800030e8  mov     esi, eax
0x1800030ea  test    eax, eax
0x1800030ec  jns     short loc_18000316D
0x1800030ee  mov     rcx, [rbp+188h]; this
0x1800030f5  lea     r8, aWil; "wil"
0x1800030fc  mov     r9d, eax; char *
0x1800030ff  mov     edx, 66h ; 'f'; void *
0x180003104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003109  mov     rcx, [rbp+188h]; this
0x180003110  lea     r8, aWil; "wil"
0x180003117  mov     r9d, esi; char *
0x18000311a  mov     edx, 6Fh ; 'o'; void *
0x18000311f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003124  mov     rcx, [rbp+188h]; this
0x18000312b  lea     r8, aWil; "wil"
0x180003132  mov     r9d, esi; char *
0x180003135  mov     edx, 12Eh; void *
0x18000313a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000313f  test    rdi, rdi
0x180003142  jz      short loc_180003155
0x180003144  mov     rcx, rdi; hMutex
0x180003147  call    cs:__imp_ReleaseMutex
0x18000314d  test    eax, eax
0x18000314f  jz      loc_18000335C
0x180003155  mov     rcx, rbx; hObject
0x180003158  call    cs:__imp_CloseHandle
0x18000315e  test    eax, eax
0x180003160  jz      loc_18000336E
0x180003166  mov     eax, esi
0x180003168  jmp     loc_180003317
0x18000316d  mov     rax, [rsp+280h+hObject]
0x180003172  lea     rcx, ds:0[rax*4]
0x18000317a  test    rcx, rcx
0x18000317d  jz      short loc_18000318D
0x18000317f  mov     [r15], rcx
0x180003182  mov     eax, [rcx]
0x180003184  inc     eax
0x180003186  mov     [rcx], eax
0x180003188  jmp     loc_1800032ED
0x18000318d  mov     rdx, r14; dwBytes
0x180003190  mov     qword ptr [r15], 0
0x180003197  mov     ecx, 8; dwFlags
0x18000319c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800031a1  mov     rsi, rax
0x1800031a4  test    rax, rax
0x1800031a7  jnz     short loc_1800031CF
0x1800031a9  mov     rcx, [rbp+188h]; this
0x1800031b0  lea     r8, aWil; "wil"
0x1800031b7  mov     r14d, 8007000Eh
0x1800031bd  mov     edx, 14Bh; void *
0x1800031c2  mov     r9d, r14d; char *
0x1800031c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031ca  jmp     loc_180003262
0x1800031cf  xorps   xmm0, xmm0
0x1800031d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800031d8  test    sil, 3
0x1800031dc  jnz     loc_180003380
0x1800031e2  mov     r9, rsi
0x1800031e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800031ea  shr     r9, 2; unsigned __int64
0x1800031ee  lea     rcx, [rsp+280h+hObject]; this
0x1800031f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800031f8  mov     r14d, eax
0x1800031fb  test    eax, eax
0x1800031fd  jns     loc_1800032A9
0x180003203  mov     rcx, [rbp+188h]; this
0x18000320a  lea     r8, aWil; "wil"
0x180003211  mov     r9d, eax; char *
0x180003214  mov     edx, 14Eh; void *
0x180003219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000321e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003223  test    rcx, rcx
0x180003226  jz      short loc_180003236
0x180003228  call    cs:__imp_CloseHandle
0x18000322e  test    eax, eax
0x180003230  jz      loc_180003386
0x180003236  mov     rcx, [rsp+280h+hObject]; hObject
0x18000323b  test    rcx, rcx
0x18000323e  jz      short loc_18000324E
0x180003240  call    cs:__imp_CloseHandle
0x180003246  test    eax, eax
0x180003248  jz      loc_180003398
0x18000324e  call    cs:__imp_GetProcessHeap
0x180003254  mov     r8, rsi; lpMem
0x180003257  xor     edx, edx; dwFlags
0x180003259  mov     rcx, rax; hHeap
0x18000325c  call    cs:__imp_HeapFree
0x180003262  mov     rcx, [rbp+188h]; this
0x180003269  lea     r8, aWil; "wil"
0x180003270  mov     r9d, r14d; char *
0x180003273  mov     edx, 137h; void *
0x180003278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000327d  test    rdi, rdi
0x180003280  jz      short loc_180003293
0x180003282  mov     rcx, rdi; hMutex
0x180003285  call    cs:__imp_ReleaseMutex
0x18000328b  test    eax, eax
0x18000328d  jz      loc_1800033AA
0x180003293  mov     rcx, rbx; hObject
0x180003296  call    cs:__imp_CloseHandle
0x18000329c  test    eax, eax
0x18000329e  jz      loc_1800033BC
0x1800032a4  mov     eax, r14d
0x1800032a7  jmp     short loc_180003317
0x1800032a9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800032ae  xor     edx, edx; Val
0x1800032b0  mov     dword ptr [rsi], 1
0x1800032b6  lea     rcx, [rsi+22h]; void *
0x1800032ba  mov     [rsi+8], rbx
0x1800032be  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800032c3  lea     r8d, [rdx+56h]; Size
0x1800032c7  call    memset_0
0x1800032cc  xor     edx, edx; Val
0x1800032ce  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800032d4  lea     rcx, [rsi+28h]; void *
0x1800032d8  mov     dword ptr [rsi+24h], 1
0x1800032df  lea     r8d, [rdx+50h]; Size
0x1800032e3  call    memset_0
0x1800032e8  xor     ebx, ebx
0x1800032ea  mov     [r15], rsi
0x1800032ed  test    rdi, rdi
0x1800032f0  jz      short loc_180003303
0x1800032f2  mov     rcx, rdi; hMutex
0x1800032f5  call    cs:__imp_ReleaseMutex
0x1800032fb  test    eax, eax
0x1800032fd  jz      loc_1800033CE
0x180003303  test    rbx, rbx
0x180003306  jz      short loc_180003315
0x180003308  mov     rcx, rbx; hObject
0x18000330b  call    cs:__imp_CloseHandle
0x180003311  test    eax, eax
0x180003313  jz      short loc_18000333D
0x180003315  xor     eax, eax
0x180003317  mov     rcx, [rbp+180h+var_30]
0x18000331e  xor     rcx, rsp; StackCookie
0x180003321  call    __security_check_cookie
0x180003326  mov     rbx, [rsp+280h+arg_10]
0x18000332e  add     rsp, 260h
0x180003335  pop     r15
0x180003337  pop     r14
0x180003339  pop     rdi
0x18000333a  pop     rsi
0x18000333b  pop     rbp
0x18000333c  retn
0x18000333d  mov     rcx, [rbp+188h]; this
0x180003344  mov     edx, 0A0Bh; void *
0x180003349  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000334f  mov     rcx, [rbp+188h]; this
0x180003356  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000335c  mov     rcx, [rbp+188h]; this
0x180003363  mov     edx, 0A15h; void *
0x180003368  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000336e  mov     rcx, [rbp+188h]; this
0x180003375  mov     edx, 0A0Bh; void *
0x18000337a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003380  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003386  mov     rcx, [rbp+188h]; this
0x18000338d  mov     edx, 0A0Bh; void *
0x180003392  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003398  mov     rcx, [rbp+188h]; this
0x18000339f  mov     edx, 0A0Bh; void *
0x1800033a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033aa  mov     rcx, [rbp+188h]; this
0x1800033b1  mov     edx, 0A15h; void *
0x1800033b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033bc  mov     rcx, [rbp+188h]; this
0x1800033c3  mov     edx, 0A0Bh; void *
0x1800033c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033ce  mov     rcx, [rbp+188h]; this
0x1800033d5  mov     edx, 0A15h; void *
0x1800033da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
