# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400030b0`
- end: `0x14000344e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400040ac`

## callees

- `0x1400030b0`
- `0x140003474`
- `0x1400037f4`
- `0x140003e48`
- `0x140004a94`
- `0x140004ce0`
- `0x1400050ac`
- `0x140005138`
- `0x1400054ec`
- `0x1400054fc`
- `0x14001346e`
- `0x1400134a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003149`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003149`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400031ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400032f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003363`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400031ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400032f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003363`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003128`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400031db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000329d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400031db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000329d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003379`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1400030b0  mov     [rsp-8+arg_10], rbx
0x1400030b5  push    rbp
0x1400030b6  push    rsi
0x1400030b7  push    rdi
0x1400030b8  push    r14
0x1400030ba  push    r15
0x1400030bc  lea     rbp, [rsp-160h]
0x1400030c4  sub     rsp, 260h
0x1400030cb  mov     rax, cs:__security_cookie
0x1400030d2  xor     rax, rsp
0x1400030d5  mov     [rbp+180h+var_30], rax
0x1400030dc  mov     r15, rdx
0x1400030df  mov     qword ptr [rdx], 0
0x1400030e6  mov     rbx, rcx
0x1400030e9  call    cs:__imp_GetCurrentProcessId
0x1400030ef  mov     r14d, 78h ; 'x'
0x1400030f5  mov     [rsp+280h+var_258], rbx
0x1400030fa  mov     r9d, eax
0x1400030fd  mov     [rsp+280h+var_260], r14d; int
0x140003102  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003109  mov     edx, 104h; unsigned __int64
0x14000310e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003113  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003118  mov     r9d, 1F0001h; dwDesiredAccess
0x14000311e  lea     rdx, [rsp+280h+Name]; lpName
0x140003123  xor     r8d, r8d; dwFlags
0x140003126  xor     ecx, ecx; lpMutexAttributes
0x140003128  call    cs:__imp_CreateMutexExW
0x14000312e  mov     rbx, rax
0x140003131  test    rax, rax
0x140003134  jnz     short loc_140003140
0x140003136  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000313b  jmp     loc_140003385
0x140003140  xor     r8d, r8d; bAlertable
0x140003143  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003146  mov     rcx, rbx; hHandle
0x140003149  call    cs:__imp_WaitForSingleObjectEx
0x14000314f  cmp     eax, 102h
0x140003154  jz      short loc_140003166
0x140003156  test    eax, 0FFFFFF7Fh
0x14000315b  jnz     loc_1400033BD
0x140003161  mov     rdi, rbx
0x140003164  jmp     short loc_140003168
0x140003166  xor     edi, edi
0x140003168  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000316d  mov     [rsp+280h+hObject], 0
0x140003176  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000317b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003180  mov     esi, eax
0x140003182  test    eax, eax
0x140003184  jns     short loc_1400031F0
0x140003186  mov     rcx, [rbp+188h]; this
0x14000318d  mov     r9d, eax; char *
0x140003190  mov     edx, 66h ; 'f'; void *
0x140003195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000319a  mov     rcx, [rbp+188h]; this
0x1400031a1  mov     r9d, esi; char *
0x1400031a4  mov     edx, 6Fh ; 'o'; void *
0x1400031a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031ae  mov     rcx, [rbp+188h]; this
0x1400031b5  mov     r9d, esi; char *
0x1400031b8  mov     edx, 12Eh; void *
0x1400031bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031c2  test    rdi, rdi
0x1400031c5  jz      short loc_1400031D8
0x1400031c7  mov     rcx, rdi; hMutex
0x1400031ca  call    cs:__imp_ReleaseMutex
0x1400031d0  test    eax, eax
0x1400031d2  jz      loc_1400033CA
0x1400031d8  mov     rcx, rbx; hObject
0x1400031db  call    cs:__imp_CloseHandle
0x1400031e1  test    eax, eax
0x1400031e3  jz      loc_1400033DC
0x1400031e9  mov     eax, esi
0x1400031eb  jmp     loc_140003385
0x1400031f0  mov     rax, [rsp+280h+hObject]
0x1400031f5  lea     rcx, ds:0[rax*4]
0x1400031fd  test    rcx, rcx
0x140003200  jz      short loc_140003210
0x140003202  mov     [r15], rcx
0x140003205  mov     eax, [rcx]
0x140003207  inc     eax
0x140003209  mov     [rcx], eax
0x14000320b  jmp     loc_14000335B
0x140003210  mov     rdx, r14; dwBytes
0x140003213  mov     qword ptr [r15], 0
0x14000321a  mov     ecx, 8; dwFlags
0x14000321f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003224  mov     rsi, rax
0x140003227  test    rax, rax
0x14000322a  jnz     short loc_14000324B
0x14000322c  mov     rcx, [rbp+188h]; this
0x140003233  mov     r14d, 8007000Eh
0x140003239  mov     r9d, r14d; char *
0x14000323c  mov     edx, 14Bh; void *
0x140003241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003246  jmp     loc_1400032D7
0x14000324b  xorps   xmm0, xmm0
0x14000324e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003254  test    sil, 3
0x140003258  jnz     loc_1400033EE
0x14000325e  mov     r9, rsi
0x140003261  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003266  shr     r9, 2; unsigned __int64
0x14000326a  lea     rcx, [rsp+280h+hObject]; this
0x14000326f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003274  mov     r14d, eax
0x140003277  test    eax, eax
0x140003279  jns     loc_140003317
0x14000327f  mov     rcx, [rbp+188h]; this
0x140003286  mov     r9d, eax; char *
0x140003289  mov     edx, 14Eh; void *
0x14000328e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003293  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003298  test    rcx, rcx
0x14000329b  jz      short loc_1400032AB
0x14000329d  call    cs:__imp_CloseHandle
0x1400032a3  test    eax, eax
0x1400032a5  jz      loc_1400033F4
0x1400032ab  mov     rcx, [rsp+280h+hObject]; hObject
0x1400032b0  test    rcx, rcx
0x1400032b3  jz      short loc_1400032C3
0x1400032b5  call    cs:__imp_CloseHandle
0x1400032bb  test    eax, eax
0x1400032bd  jz      loc_140003406
0x1400032c3  call    cs:__imp_GetProcessHeap
0x1400032c9  mov     r8, rsi; lpMem
0x1400032cc  xor     edx, edx; dwFlags
0x1400032ce  mov     rcx, rax; hHeap
0x1400032d1  call    cs:__imp_HeapFree
0x1400032d7  mov     rcx, [rbp+188h]; this
0x1400032de  mov     r9d, r14d; char *
0x1400032e1  mov     edx, 137h; void *
0x1400032e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400032eb  test    rdi, rdi
0x1400032ee  jz      short loc_140003301
0x1400032f0  mov     rcx, rdi; hMutex
0x1400032f3  call    cs:__imp_ReleaseMutex
0x1400032f9  test    eax, eax
0x1400032fb  jz      loc_140003418
0x140003301  mov     rcx, rbx; hObject
0x140003304  call    cs:__imp_CloseHandle
0x14000330a  test    eax, eax
0x14000330c  jz      loc_14000342A
0x140003312  mov     eax, r14d
0x140003315  jmp     short loc_140003385
0x140003317  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000331c  xor     edx, edx; Val
0x14000331e  mov     dword ptr [rsi], 1
0x140003324  lea     rcx, [rsi+22h]; void *
0x140003328  mov     [rsi+8], rbx
0x14000332c  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003331  lea     r8d, [rdx+56h]; Size
0x140003335  call    memset_0
0x14000333a  xor     edx, edx; Val
0x14000333c  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003342  lea     rcx, [rsi+28h]; void *
0x140003346  mov     dword ptr [rsi+24h], 1
0x14000334d  lea     r8d, [rdx+50h]; Size
0x140003351  call    memset_0
0x140003356  xor     ebx, ebx
0x140003358  mov     [r15], rsi
0x14000335b  test    rdi, rdi
0x14000335e  jz      short loc_140003371
0x140003360  mov     rcx, rdi; hMutex
0x140003363  call    cs:__imp_ReleaseMutex
0x140003369  test    eax, eax
0x14000336b  jz      loc_14000343C
0x140003371  test    rbx, rbx
0x140003374  jz      short loc_140003383
0x140003376  mov     rcx, rbx; hObject
0x140003379  call    cs:__imp_CloseHandle
0x14000337f  test    eax, eax
0x140003381  jz      short loc_1400033AB
0x140003383  xor     eax, eax
0x140003385  mov     rcx, [rbp+180h+var_30]
0x14000338c  xor     rcx, rsp; StackCookie
0x14000338f  call    __security_check_cookie
0x140003394  mov     rbx, [rsp+280h+arg_10]
0x14000339c  add     rsp, 260h
0x1400033a3  pop     r15
0x1400033a5  pop     r14
0x1400033a7  pop     rdi
0x1400033a8  pop     rsi
0x1400033a9  pop     rbp
0x1400033aa  retn
0x1400033ab  mov     rcx, [rbp+188h]; this
0x1400033b2  mov     edx, 0A0Bh; void *
0x1400033b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400033bd  mov     rcx, [rbp+188h]; this
0x1400033c4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400033ca  mov     rcx, [rbp+188h]; this
0x1400033d1  mov     edx, 0A15h; void *
0x1400033d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400033dc  mov     rcx, [rbp+188h]; this
0x1400033e3  mov     edx, 0A0Bh; void *
0x1400033e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400033ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400033f4  mov     rcx, [rbp+188h]; this
0x1400033fb  mov     edx, 0A0Bh; void *
0x140003400  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003406  mov     rcx, [rbp+188h]; this
0x14000340d  mov     edx, 0A0Bh; void *
0x140003412  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003418  mov     rcx, [rbp+188h]; this
0x14000341f  mov     edx, 0A15h; void *
0x140003424  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000342a  mov     rcx, [rbp+188h]; this
0x140003431  mov     edx, 0A0Bh; void *
0x140003436  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000343c  mov     rcx, [rbp+188h]; this
0x140003443  mov     edx, 0A15h; void *
0x140003448  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
