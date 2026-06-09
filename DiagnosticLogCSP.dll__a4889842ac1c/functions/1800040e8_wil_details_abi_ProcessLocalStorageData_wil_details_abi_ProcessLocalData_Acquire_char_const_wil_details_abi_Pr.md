# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800040e8`
- end: `0x1800044b0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004fb0`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x1800040e8`
- `0x1800044b8`
- `0x180004700`
- `0x180004d48`
- `0x180005828`
- `0x180005b04`
- `0x180006518`
- `0x1800065dc`
- `0x1800069ac`
- `0x1800069bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004121`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004217`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004355`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004217`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004355`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004181`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004181`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004160`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004160`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000431e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000431e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000432c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000432c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043db`

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
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x1800040e8  mov     [rsp-8+arg_10], rbx
0x1800040ed  push    rbp
0x1800040ee  push    rsi
0x1800040ef  push    rdi
0x1800040f0  push    r14
0x1800040f2  push    r15
0x1800040f4  lea     rbp, [rsp-160h]
0x1800040fc  sub     rsp, 260h
0x180004103  mov     rax, cs:__security_cookie
0x18000410a  xor     rax, rsp
0x18000410d  mov     [rbp+180h+var_30], rax
0x180004114  mov     r15, rdx
0x180004117  mov     qword ptr [rdx], 0
0x18000411e  mov     rbx, rcx
0x180004121  call    cs:__imp_GetCurrentProcessId
0x180004127  mov     r14d, 78h ; 'x'
0x18000412d  mov     [rsp+280h+var_258], rbx
0x180004132  mov     r9d, eax
0x180004135  mov     [rsp+280h+var_260], r14d; int
0x18000413a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004141  mov     edx, 104h; unsigned __int64
0x180004146  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000414b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004150  mov     r9d, 1F0001h; dwDesiredAccess
0x180004156  lea     rdx, [rsp+280h+Name]; lpName
0x18000415b  xor     r8d, r8d; dwFlags
0x18000415e  xor     ecx, ecx; lpMutexAttributes
0x180004160  call    cs:__imp_CreateMutexExW
0x180004166  mov     rbx, rax
0x180004169  test    rax, rax
0x18000416c  jnz     short loc_180004178
0x18000416e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004173  jmp     loc_1800043E7
0x180004178  xor     r8d, r8d; bAlertable
0x18000417b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000417e  mov     rcx, rbx; hHandle
0x180004181  call    cs:__imp_WaitForSingleObjectEx
0x180004187  cmp     eax, 102h
0x18000418c  jz      short loc_18000419E
0x18000418e  test    eax, 0FFFFFF7Fh
0x180004193  jnz     loc_18000441F
0x180004199  mov     rdi, rbx
0x18000419c  jmp     short loc_1800041A0
0x18000419e  xor     edi, edi
0x1800041a0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800041a5  mov     [rsp+280h+hObject], 0
0x1800041ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800041b3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800041b8  mov     esi, eax
0x1800041ba  test    eax, eax
0x1800041bc  jns     short loc_18000423D
0x1800041be  mov     rcx, [rbp+188h]; this
0x1800041c5  lea     r8, aWil; "wil"
0x1800041cc  mov     r9d, eax; char *
0x1800041cf  mov     edx, 66h ; 'f'; void *
0x1800041d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041d9  mov     rcx, [rbp+188h]; this
0x1800041e0  lea     r8, aWil; "wil"
0x1800041e7  mov     r9d, esi; char *
0x1800041ea  mov     edx, 6Fh ; 'o'; void *
0x1800041ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041f4  mov     rcx, [rbp+188h]; this
0x1800041fb  lea     r8, aWil; "wil"
0x180004202  mov     r9d, esi; char *
0x180004205  mov     edx, 12Eh; void *
0x18000420a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000420f  test    rdi, rdi
0x180004212  jz      short loc_180004225
0x180004214  mov     rcx, rdi; hMutex
0x180004217  call    cs:__imp_ReleaseMutex
0x18000421d  test    eax, eax
0x18000421f  jz      loc_18000442C
0x180004225  mov     rcx, rbx; hObject
0x180004228  call    cs:__imp_CloseHandle
0x18000422e  test    eax, eax
0x180004230  jz      loc_18000443E
0x180004236  mov     eax, esi
0x180004238  jmp     loc_1800043E7
0x18000423d  mov     rax, [rsp+280h+hObject]
0x180004242  lea     rcx, ds:0[rax*4]
0x18000424a  test    rcx, rcx
0x18000424d  jz      short loc_18000425D
0x18000424f  mov     [r15], rcx
0x180004252  mov     eax, [rcx]
0x180004254  inc     eax
0x180004256  mov     [rcx], eax
0x180004258  jmp     loc_1800043BD
0x18000425d  mov     rdx, r14; dwBytes
0x180004260  mov     qword ptr [r15], 0
0x180004267  mov     ecx, 8; dwFlags
0x18000426c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004271  mov     rsi, rax
0x180004274  test    rax, rax
0x180004277  jnz     short loc_18000429F
0x180004279  mov     rcx, [rbp+188h]; this
0x180004280  lea     r8, aWil; "wil"
0x180004287  mov     r14d, 8007000Eh
0x18000428d  mov     edx, 14Bh; void *
0x180004292  mov     r9d, r14d; char *
0x180004295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000429a  jmp     loc_180004332
0x18000429f  xorps   xmm0, xmm0
0x1800042a2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800042a8  test    sil, 3
0x1800042ac  jnz     loc_180004450
0x1800042b2  mov     r9, rsi
0x1800042b5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800042ba  shr     r9, 2; unsigned __int64
0x1800042be  lea     rcx, [rsp+280h+hObject]; this
0x1800042c3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800042c8  mov     r14d, eax
0x1800042cb  test    eax, eax
0x1800042cd  jns     loc_180004379
0x1800042d3  mov     rcx, [rbp+188h]; this
0x1800042da  lea     r8, aWil; "wil"
0x1800042e1  mov     r9d, eax; char *
0x1800042e4  mov     edx, 14Eh; void *
0x1800042e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042ee  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800042f3  test    rcx, rcx
0x1800042f6  jz      short loc_180004306
0x1800042f8  call    cs:__imp_CloseHandle
0x1800042fe  test    eax, eax
0x180004300  jz      loc_180004456
0x180004306  mov     rcx, [rsp+280h+hObject]; hObject
0x18000430b  test    rcx, rcx
0x18000430e  jz      short loc_18000431E
0x180004310  call    cs:__imp_CloseHandle
0x180004316  test    eax, eax
0x180004318  jz      loc_180004468
0x18000431e  call    cs:__imp_GetProcessHeap
0x180004324  mov     r8, rsi; lpMem
0x180004327  xor     edx, edx; dwFlags
0x180004329  mov     rcx, rax; hHeap
0x18000432c  call    cs:__imp_HeapFree
0x180004332  mov     rcx, [rbp+188h]; this
0x180004339  lea     r8, aWil; "wil"
0x180004340  mov     r9d, r14d; char *
0x180004343  mov     edx, 137h; void *
0x180004348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000434d  test    rdi, rdi
0x180004350  jz      short loc_180004363
0x180004352  mov     rcx, rdi; hMutex
0x180004355  call    cs:__imp_ReleaseMutex
0x18000435b  test    eax, eax
0x18000435d  jz      loc_18000447A
0x180004363  mov     rcx, rbx; hObject
0x180004366  call    cs:__imp_CloseHandle
0x18000436c  test    eax, eax
0x18000436e  jz      loc_18000448C
0x180004374  mov     eax, r14d
0x180004377  jmp     short loc_1800043E7
0x180004379  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000437e  xor     edx, edx; Val
0x180004380  mov     dword ptr [rsi], 1
0x180004386  lea     rcx, [rsi+22h]; void *
0x18000438a  mov     [rsi+8], rbx
0x18000438e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004393  lea     r8d, [rdx+56h]; Size
0x180004397  call    memset_0
0x18000439c  xor     edx, edx; Val
0x18000439e  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800043a4  lea     rcx, [rsi+28h]; void *
0x1800043a8  mov     dword ptr [rsi+24h], 1
0x1800043af  lea     r8d, [rdx+50h]; Size
0x1800043b3  call    memset_0
0x1800043b8  xor     ebx, ebx
0x1800043ba  mov     [r15], rsi
0x1800043bd  test    rdi, rdi
0x1800043c0  jz      short loc_1800043D3
0x1800043c2  mov     rcx, rdi; hMutex
0x1800043c5  call    cs:__imp_ReleaseMutex
0x1800043cb  test    eax, eax
0x1800043cd  jz      loc_18000449E
0x1800043d3  test    rbx, rbx
0x1800043d6  jz      short loc_1800043E5
0x1800043d8  mov     rcx, rbx; hObject
0x1800043db  call    cs:__imp_CloseHandle
0x1800043e1  test    eax, eax
0x1800043e3  jz      short loc_18000440D
0x1800043e5  xor     eax, eax
0x1800043e7  mov     rcx, [rbp+180h+var_30]
0x1800043ee  xor     rcx, rsp; StackCookie
0x1800043f1  call    __security_check_cookie
0x1800043f6  mov     rbx, [rsp+280h+arg_10]
0x1800043fe  add     rsp, 260h
0x180004405  pop     r15
0x180004407  pop     r14
0x180004409  pop     rdi
0x18000440a  pop     rsi
0x18000440b  pop     rbp
0x18000440c  retn
0x18000440d  mov     rcx, [rbp+188h]; this
0x180004414  mov     edx, 0A0Bh; void *
0x180004419  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000441f  mov     rcx, [rbp+188h]; this
0x180004426  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000442c  mov     rcx, [rbp+188h]; this
0x180004433  mov     edx, 0A15h; void *
0x180004438  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000443e  mov     rcx, [rbp+188h]; this
0x180004445  mov     edx, 0A0Bh; void *
0x18000444a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004450  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004456  mov     rcx, [rbp+188h]; this
0x18000445d  mov     edx, 0A0Bh; void *
0x180004462  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004468  mov     rcx, [rbp+188h]; this
0x18000446f  mov     edx, 0A0Bh; void *
0x180004474  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000447a  mov     rcx, [rbp+188h]; this
0x180004481  mov     edx, 0A15h; void *
0x180004486  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000448c  mov     rcx, [rbp+188h]; this
0x180004493  mov     edx, 0A0Bh; void *
0x180004498  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000449e  mov     rcx, [rbp+188h]; this
0x1800044a5  mov     edx, 0A15h; void *
0x1800044aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
