# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800030a0`
- end: `0x180003468`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003f60`

## callees

- `0x1800030a0`
- `0x180003470`
- `0x180003754`
- `0x180003cf8`
- `0x1800047d8`
- `0x180004a34`
- `0x180005264`
- `0x18000531c`
- `0x1800057d4`
- `0x1800057e4`
- `0x18001143a`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003139`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003139`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000330d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000337d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000330d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000337d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003118`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000331e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000331e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003393`

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
0x1800030a0  mov     [rsp-8+arg_10], rbx
0x1800030a5  push    rbp
0x1800030a6  push    rsi
0x1800030a7  push    rdi
0x1800030a8  push    r14
0x1800030aa  push    r15
0x1800030ac  lea     rbp, [rsp-160h]
0x1800030b4  sub     rsp, 260h
0x1800030bb  mov     rax, cs:__security_cookie
0x1800030c2  xor     rax, rsp
0x1800030c5  mov     [rbp+180h+var_30], rax
0x1800030cc  mov     r15, rdx
0x1800030cf  mov     qword ptr [rdx], 0
0x1800030d6  mov     rbx, rcx
0x1800030d9  call    cs:__imp_GetCurrentProcessId
0x1800030df  mov     r14d, 78h ; 'x'
0x1800030e5  mov     [rsp+280h+var_258], rbx
0x1800030ea  mov     r9d, eax
0x1800030ed  mov     [rsp+280h+var_260], r14d; int
0x1800030f2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800030f9  mov     edx, 104h; unsigned __int64
0x1800030fe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003103  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003108  mov     r9d, 1F0001h; dwDesiredAccess
0x18000310e  lea     rdx, [rsp+280h+Name]; lpName
0x180003113  xor     r8d, r8d; dwFlags
0x180003116  xor     ecx, ecx; lpMutexAttributes
0x180003118  call    cs:__imp_CreateMutexExW
0x18000311e  mov     rbx, rax
0x180003121  test    rax, rax
0x180003124  jnz     short loc_180003130
0x180003126  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000312b  jmp     loc_18000339F
0x180003130  xor     r8d, r8d; bAlertable
0x180003133  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003136  mov     rcx, rbx; hHandle
0x180003139  call    cs:__imp_WaitForSingleObjectEx
0x18000313f  cmp     eax, 102h
0x180003144  jz      short loc_180003156
0x180003146  test    eax, 0FFFFFF7Fh
0x18000314b  jnz     loc_1800033D7
0x180003151  mov     rdi, rbx
0x180003154  jmp     short loc_180003158
0x180003156  xor     edi, edi
0x180003158  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000315d  mov     [rsp+280h+hObject], 0
0x180003166  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000316b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003170  mov     esi, eax
0x180003172  test    eax, eax
0x180003174  jns     short loc_1800031F5
0x180003176  mov     rcx, [rbp+188h]; this
0x18000317d  lea     r8, aWil; "wil"
0x180003184  mov     r9d, eax; char *
0x180003187  mov     edx, 66h ; 'f'; void *
0x18000318c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003191  mov     rcx, [rbp+188h]; this
0x180003198  lea     r8, aWil; "wil"
0x18000319f  mov     r9d, esi; char *
0x1800031a2  mov     edx, 6Fh ; 'o'; void *
0x1800031a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031ac  mov     rcx, [rbp+188h]; this
0x1800031b3  lea     r8, aWil; "wil"
0x1800031ba  mov     r9d, esi; char *
0x1800031bd  mov     edx, 12Eh; void *
0x1800031c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031c7  test    rdi, rdi
0x1800031ca  jz      short loc_1800031DD
0x1800031cc  mov     rcx, rdi; hMutex
0x1800031cf  call    cs:__imp_ReleaseMutex
0x1800031d5  test    eax, eax
0x1800031d7  jz      loc_1800033E4
0x1800031dd  mov     rcx, rbx; hObject
0x1800031e0  call    cs:__imp_CloseHandle
0x1800031e6  test    eax, eax
0x1800031e8  jz      loc_1800033F6
0x1800031ee  mov     eax, esi
0x1800031f0  jmp     loc_18000339F
0x1800031f5  mov     rax, [rsp+280h+hObject]
0x1800031fa  lea     rcx, ds:0[rax*4]
0x180003202  test    rcx, rcx
0x180003205  jz      short loc_180003215
0x180003207  mov     [r15], rcx
0x18000320a  mov     eax, [rcx]
0x18000320c  inc     eax
0x18000320e  mov     [rcx], eax
0x180003210  jmp     loc_180003375
0x180003215  mov     rdx, r14; dwBytes
0x180003218  mov     qword ptr [r15], 0
0x18000321f  mov     ecx, 8; dwFlags
0x180003224  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003229  mov     rsi, rax
0x18000322c  test    rax, rax
0x18000322f  jnz     short loc_180003257
0x180003231  mov     rcx, [rbp+188h]; this
0x180003238  lea     r8, aWil; "wil"
0x18000323f  mov     r14d, 8007000Eh
0x180003245  mov     edx, 14Bh; void *
0x18000324a  mov     r9d, r14d; char *
0x18000324d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003252  jmp     loc_1800032EA
0x180003257  xorps   xmm0, xmm0
0x18000325a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003260  test    sil, 3
0x180003264  jnz     loc_180003408
0x18000326a  mov     r9, rsi
0x18000326d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003272  shr     r9, 2; unsigned __int64
0x180003276  lea     rcx, [rsp+280h+hObject]; this
0x18000327b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003280  mov     r14d, eax
0x180003283  test    eax, eax
0x180003285  jns     loc_180003331
0x18000328b  mov     rcx, [rbp+188h]; this
0x180003292  lea     r8, aWil; "wil"
0x180003299  mov     r9d, eax; char *
0x18000329c  mov     edx, 14Eh; void *
0x1800032a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032a6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800032ab  test    rcx, rcx
0x1800032ae  jz      short loc_1800032BE
0x1800032b0  call    cs:__imp_CloseHandle
0x1800032b6  test    eax, eax
0x1800032b8  jz      loc_18000340E
0x1800032be  mov     rcx, [rsp+280h+hObject]; hObject
0x1800032c3  test    rcx, rcx
0x1800032c6  jz      short loc_1800032D6
0x1800032c8  call    cs:__imp_CloseHandle
0x1800032ce  test    eax, eax
0x1800032d0  jz      loc_180003420
0x1800032d6  call    cs:__imp_GetProcessHeap
0x1800032dc  mov     r8, rsi; lpMem
0x1800032df  xor     edx, edx; dwFlags
0x1800032e1  mov     rcx, rax; hHeap
0x1800032e4  call    cs:__imp_HeapFree
0x1800032ea  mov     rcx, [rbp+188h]; this
0x1800032f1  lea     r8, aWil; "wil"
0x1800032f8  mov     r9d, r14d; char *
0x1800032fb  mov     edx, 137h; void *
0x180003300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003305  test    rdi, rdi
0x180003308  jz      short loc_18000331B
0x18000330a  mov     rcx, rdi; hMutex
0x18000330d  call    cs:__imp_ReleaseMutex
0x180003313  test    eax, eax
0x180003315  jz      loc_180003432
0x18000331b  mov     rcx, rbx; hObject
0x18000331e  call    cs:__imp_CloseHandle
0x180003324  test    eax, eax
0x180003326  jz      loc_180003444
0x18000332c  mov     eax, r14d
0x18000332f  jmp     short loc_18000339F
0x180003331  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003336  xor     edx, edx; Val
0x180003338  mov     dword ptr [rsi], 1
0x18000333e  lea     rcx, [rsi+22h]; void *
0x180003342  mov     [rsi+8], rbx
0x180003346  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000334b  lea     r8d, [rdx+56h]; Size
0x18000334f  call    memset_0
0x180003354  xor     edx, edx; Val
0x180003356  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000335c  lea     rcx, [rsi+28h]; void *
0x180003360  mov     dword ptr [rsi+24h], 1
0x180003367  lea     r8d, [rdx+50h]; Size
0x18000336b  call    memset_0
0x180003370  xor     ebx, ebx
0x180003372  mov     [r15], rsi
0x180003375  test    rdi, rdi
0x180003378  jz      short loc_18000338B
0x18000337a  mov     rcx, rdi; hMutex
0x18000337d  call    cs:__imp_ReleaseMutex
0x180003383  test    eax, eax
0x180003385  jz      loc_180003456
0x18000338b  test    rbx, rbx
0x18000338e  jz      short loc_18000339D
0x180003390  mov     rcx, rbx; hObject
0x180003393  call    cs:__imp_CloseHandle
0x180003399  test    eax, eax
0x18000339b  jz      short loc_1800033C5
0x18000339d  xor     eax, eax
0x18000339f  mov     rcx, [rbp+180h+var_30]
0x1800033a6  xor     rcx, rsp; StackCookie
0x1800033a9  call    __security_check_cookie
0x1800033ae  mov     rbx, [rsp+280h+arg_10]
0x1800033b6  add     rsp, 260h
0x1800033bd  pop     r15
0x1800033bf  pop     r14
0x1800033c1  pop     rdi
0x1800033c2  pop     rsi
0x1800033c3  pop     rbp
0x1800033c4  retn
0x1800033c5  mov     rcx, [rbp+188h]; this
0x1800033cc  mov     edx, 0A0Bh; void *
0x1800033d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033d7  mov     rcx, [rbp+188h]; this
0x1800033de  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800033e4  mov     rcx, [rbp+188h]; this
0x1800033eb  mov     edx, 0A15h; void *
0x1800033f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800033f6  mov     rcx, [rbp+188h]; this
0x1800033fd  mov     edx, 0A0Bh; void *
0x180003402  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003408  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000340e  mov     rcx, [rbp+188h]; this
0x180003415  mov     edx, 0A0Bh; void *
0x18000341a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003420  mov     rcx, [rbp+188h]; this
0x180003427  mov     edx, 0A0Bh; void *
0x18000342c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003432  mov     rcx, [rbp+188h]; this
0x180003439  mov     edx, 0A15h; void *
0x18000343e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003444  mov     rcx, [rbp+188h]; this
0x18000344b  mov     edx, 0A0Bh; void *
0x180003450  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003456  mov     rcx, [rbp+188h]; this
0x18000345d  mov     edx, 0A15h; void *
0x180003462  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
