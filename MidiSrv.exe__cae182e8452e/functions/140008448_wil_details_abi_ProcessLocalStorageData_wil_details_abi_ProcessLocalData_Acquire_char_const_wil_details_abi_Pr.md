# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008448`
- end: `0x14000881c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140009458`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x140008448`
- `0x140008824`
- `0x140008b34`
- `0x14000914c`
- `0x140009a8c`
- `0x14000a6b4`
- `0x14000b0cc`
- `0x14000c10c`
- `0x14000c54c`
- `0x14000c55c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400084e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400084e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008577`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400086b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008725`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008577`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400086b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008725`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400084c0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400084c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000868c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000868c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000867e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000867e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008481`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008670`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400086c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000873b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008588`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008670`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400086c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000873b`

## string_xrefs

- `0x140008786`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x140008448  mov     [rsp-8+arg_10], rbx
0x14000844d  push    rbp
0x14000844e  push    rsi
0x14000844f  push    rdi
0x140008450  push    r14
0x140008452  push    r15
0x140008454  lea     rbp, [rsp-160h]
0x14000845c  sub     rsp, 260h
0x140008463  mov     rax, cs:__security_cookie
0x14000846a  xor     rax, rsp
0x14000846d  mov     [rbp+180h+var_30], rax
0x140008474  mov     r15, rdx
0x140008477  mov     qword ptr [rdx], 0
0x14000847e  mov     rbx, rcx
0x140008481  call    cs:__imp_GetCurrentProcessId
0x140008487  mov     r14d, 78h ; 'x'
0x14000848d  mov     [rsp+280h+var_258], rbx
0x140008492  mov     r9d, eax
0x140008495  mov     [rsp+280h+var_260], r14d; int
0x14000849a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400084a1  mov     edx, 104h; unsigned __int64
0x1400084a6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400084ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400084b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400084b6  lea     rdx, [rsp+280h+Name]; lpName
0x1400084bb  xor     r8d, r8d; dwFlags
0x1400084be  xor     ecx, ecx; lpMutexAttributes
0x1400084c0  call    cs:__imp_CreateMutexExW
0x1400084c6  mov     rbx, rax
0x1400084c9  test    rax, rax
0x1400084cc  jnz     short loc_1400084D8
0x1400084ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400084d3  jmp     loc_140008747
0x1400084d8  xor     r8d, r8d; bAlertable
0x1400084db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400084de  mov     rcx, rbx; hHandle
0x1400084e1  call    cs:__imp_WaitForSingleObjectEx
0x1400084e7  cmp     eax, 102h
0x1400084ec  jz      short loc_1400084FE
0x1400084ee  test    eax, 0FFFFFF7Fh
0x1400084f3  jnz     loc_14000877F
0x1400084f9  mov     rdi, rbx
0x1400084fc  jmp     short loc_140008500
0x1400084fe  xor     edi, edi
0x140008500  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140008505  mov     [rsp+280h+hObject], 0
0x14000850e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008513  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140008518  mov     esi, eax
0x14000851a  test    eax, eax
0x14000851c  jns     short loc_14000859D
0x14000851e  mov     rcx, [rbp+188h]; this
0x140008525  lea     r8, aWil; "wil"
0x14000852c  mov     r9d, eax; char *
0x14000852f  mov     edx, 66h ; 'f'; void *
0x140008534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008539  mov     rcx, [rbp+188h]; this
0x140008540  lea     r8, aWil; "wil"
0x140008547  mov     r9d, esi; char *
0x14000854a  mov     edx, 6Fh ; 'o'; void *
0x14000854f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008554  mov     rcx, [rbp+188h]; this
0x14000855b  lea     r8, aWil; "wil"
0x140008562  mov     r9d, esi; char *
0x140008565  mov     edx, 12Eh; void *
0x14000856a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000856f  test    rdi, rdi
0x140008572  jz      short loc_140008585
0x140008574  mov     rcx, rdi; hMutex
0x140008577  call    cs:__imp_ReleaseMutex
0x14000857d  test    eax, eax
0x14000857f  jz      loc_140008798
0x140008585  mov     rcx, rbx; hObject
0x140008588  call    cs:__imp_CloseHandle
0x14000858e  test    eax, eax
0x140008590  jz      loc_1400087AA
0x140008596  mov     eax, esi
0x140008598  jmp     loc_140008747
0x14000859d  mov     rax, [rsp+280h+hObject]
0x1400085a2  lea     rcx, ds:0[rax*4]
0x1400085aa  test    rcx, rcx
0x1400085ad  jz      short loc_1400085BD
0x1400085af  mov     [r15], rcx
0x1400085b2  mov     eax, [rcx]
0x1400085b4  inc     eax
0x1400085b6  mov     [rcx], eax
0x1400085b8  jmp     loc_14000871D
0x1400085bd  mov     rdx, r14; dwBytes
0x1400085c0  mov     qword ptr [r15], 0
0x1400085c7  mov     ecx, 8; dwFlags
0x1400085cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400085d1  mov     rsi, rax
0x1400085d4  test    rax, rax
0x1400085d7  jnz     short loc_1400085FF
0x1400085d9  mov     rcx, [rbp+188h]; this
0x1400085e0  lea     r8, aWil; "wil"
0x1400085e7  mov     r14d, 8007000Eh
0x1400085ed  mov     edx, 14Bh; void *
0x1400085f2  mov     r9d, r14d; char *
0x1400085f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400085fa  jmp     loc_140008692
0x1400085ff  xorps   xmm0, xmm0
0x140008602  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140008608  test    sil, 3
0x14000860c  jnz     loc_1400087BC
0x140008612  mov     r9, rsi
0x140008615  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000861a  shr     r9, 2; unsigned __int64
0x14000861e  lea     rcx, [rsp+280h+hObject]; this
0x140008623  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140008628  mov     r14d, eax
0x14000862b  test    eax, eax
0x14000862d  jns     loc_1400086D9
0x140008633  mov     rcx, [rbp+188h]; this
0x14000863a  lea     r8, aWil; "wil"
0x140008641  mov     r9d, eax; char *
0x140008644  mov     edx, 14Eh; void *
0x140008649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000864e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008653  test    rcx, rcx
0x140008656  jz      short loc_140008666
0x140008658  call    cs:__imp_CloseHandle
0x14000865e  test    eax, eax
0x140008660  jz      loc_1400087C2
0x140008666  mov     rcx, [rsp+280h+hObject]; hObject
0x14000866b  test    rcx, rcx
0x14000866e  jz      short loc_14000867E
0x140008670  call    cs:__imp_CloseHandle
0x140008676  test    eax, eax
0x140008678  jz      loc_1400087D4
0x14000867e  call    cs:__imp_GetProcessHeap
0x140008684  mov     r8, rsi; lpMem
0x140008687  xor     edx, edx; dwFlags
0x140008689  mov     rcx, rax; hHeap
0x14000868c  call    cs:__imp_HeapFree
0x140008692  mov     rcx, [rbp+188h]; this
0x140008699  lea     r8, aWil; "wil"
0x1400086a0  mov     r9d, r14d; char *
0x1400086a3  mov     edx, 137h; void *
0x1400086a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400086ad  test    rdi, rdi
0x1400086b0  jz      short loc_1400086C3
0x1400086b2  mov     rcx, rdi; hMutex
0x1400086b5  call    cs:__imp_ReleaseMutex
0x1400086bb  test    eax, eax
0x1400086bd  jz      loc_1400087E6
0x1400086c3  mov     rcx, rbx; hObject
0x1400086c6  call    cs:__imp_CloseHandle
0x1400086cc  test    eax, eax
0x1400086ce  jz      loc_1400087F8
0x1400086d4  mov     eax, r14d
0x1400086d7  jmp     short loc_140008747
0x1400086d9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400086de  xor     edx, edx; Val
0x1400086e0  mov     dword ptr [rsi], 1
0x1400086e6  lea     rcx, [rsi+22h]; void *
0x1400086ea  mov     [rsi+8], rbx
0x1400086ee  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400086f3  lea     r8d, [rdx+56h]; Size
0x1400086f7  call    memset_0
0x1400086fc  xor     edx, edx; Val
0x1400086fe  mov     word ptr [rsi+20h], 58h ; 'X'
0x140008704  lea     rcx, [rsi+28h]; void *
0x140008708  mov     dword ptr [rsi+24h], 1
0x14000870f  lea     r8d, [rdx+50h]; Size
0x140008713  call    memset_0
0x140008718  xor     ebx, ebx
0x14000871a  mov     [r15], rsi
0x14000871d  test    rdi, rdi
0x140008720  jz      short loc_140008733
0x140008722  mov     rcx, rdi; hMutex
0x140008725  call    cs:__imp_ReleaseMutex
0x14000872b  test    eax, eax
0x14000872d  jz      loc_14000880A
0x140008733  test    rbx, rbx
0x140008736  jz      short loc_140008745
0x140008738  mov     rcx, rbx; hObject
0x14000873b  call    cs:__imp_CloseHandle
0x140008741  test    eax, eax
0x140008743  jz      short loc_14000876D
0x140008745  xor     eax, eax
0x140008747  mov     rcx, [rbp+180h+var_30]
0x14000874e  xor     rcx, rsp; StackCookie
0x140008751  call    __security_check_cookie
0x140008756  mov     rbx, [rsp+280h+arg_10]
0x14000875e  add     rsp, 260h
0x140008765  pop     r15
0x140008767  pop     r14
0x140008769  pop     rdi
0x14000876a  pop     rsi
0x14000876b  pop     rbp
0x14000876c  retn
0x14000876d  mov     rcx, [rbp+188h]; this
0x140008774  mov     edx, 0A0Bh; void *
0x140008779  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000877f  mov     rcx, [rbp+188h]; this
0x140008786  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000878d  mov     edx, 0E01h; void *
0x140008792  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008798  mov     rcx, [rbp+188h]; this
0x14000879f  mov     edx, 0A15h; void *
0x1400087a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400087aa  mov     rcx, [rbp+188h]; this
0x1400087b1  mov     edx, 0A0Bh; void *
0x1400087b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400087bc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400087c2  mov     rcx, [rbp+188h]; this
0x1400087c9  mov     edx, 0A0Bh; void *
0x1400087ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400087d4  mov     rcx, [rbp+188h]; this
0x1400087db  mov     edx, 0A0Bh; void *
0x1400087e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400087e6  mov     rcx, [rbp+188h]; this
0x1400087ed  mov     edx, 0A15h; void *
0x1400087f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400087f8  mov     rcx, [rbp+188h]; this
0x1400087ff  mov     edx, 0A0Bh; void *
0x140008804  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000880a  mov     rcx, [rbp+188h]; this
0x140008811  mov     edx, 0A15h; void *
0x140008816  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
