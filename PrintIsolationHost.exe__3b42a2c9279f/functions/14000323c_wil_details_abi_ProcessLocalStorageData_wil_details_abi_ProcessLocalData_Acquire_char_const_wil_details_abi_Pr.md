# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000323c`
- end: `0x1400035da`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400040fc`

## callees

- `0x140001cd0`
- `0x140002690`
- `0x14000323c`
- `0x1400035e0`
- `0x140003810`
- `0x140003e98`
- `0x140004abc`
- `0x140005108`
- `0x140005460`
- `0x1400054ec`
- `0x14000589c`
- `0x1400058ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000345d`
- `KERNEL32!HeapFree` at `0x14000345d`
- `KERNEL32!ReleaseMutex` at `0x140003356`
- `KERNEL32!ReleaseMutex` at `0x14000347f`
- `KERNEL32!ReleaseMutex` at `0x1400034ef`
- `KERNEL32!ReleaseMutex` at `0x140003356`
- `KERNEL32!ReleaseMutex` at `0x14000347f`
- `KERNEL32!ReleaseMutex` at `0x1400034ef`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400032d5`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400032d5`
- `KERNEL32!CloseHandle` at `0x140003367`
- `KERNEL32!CloseHandle` at `0x140003429`
- `KERNEL32!CloseHandle` at `0x140003441`
- `KERNEL32!CloseHandle` at `0x140003490`
- `KERNEL32!CloseHandle` at `0x140003505`
- `KERNEL32!CloseHandle` at `0x140003367`
- `KERNEL32!CloseHandle` at `0x140003429`
- `KERNEL32!CloseHandle` at `0x140003441`
- `KERNEL32!CloseHandle` at `0x140003490`
- `KERNEL32!CloseHandle` at `0x140003505`
- `KERNEL32!CreateMutexExW` at `0x1400032b4`
- `KERNEL32!CreateMutexExW` at `0x1400032b4`
- `KERNEL32!GetCurrentProcessId` at `0x140003275`
- `KERNEL32!GetCurrentProcessId` at `0x140003275`
- `KERNEL32!GetProcessHeap` at `0x14000344f`
- `KERNEL32!GetProcessHeap` at `0x14000344f`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x14000323c  mov     [rsp-8+arg_10], rbx
0x140003241  push    rbp
0x140003242  push    rsi
0x140003243  push    rdi
0x140003244  push    r14
0x140003246  push    r15
0x140003248  lea     rbp, [rsp-160h]
0x140003250  sub     rsp, 260h
0x140003257  mov     rax, cs:__security_cookie
0x14000325e  xor     rax, rsp
0x140003261  mov     [rbp+180h+var_30], rax
0x140003268  mov     r15, rdx
0x14000326b  mov     qword ptr [rdx], 0
0x140003272  mov     rbx, rcx
0x140003275  call    cs:__imp_GetCurrentProcessId
0x14000327b  mov     r14d, 78h ; 'x'
0x140003281  mov     [rsp+280h+var_258], rbx
0x140003286  mov     r9d, eax
0x140003289  mov     [rsp+280h+var_260], r14d; int
0x14000328e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003295  mov     edx, 104h; unsigned __int64
0x14000329a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000329f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400032a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1400032aa  lea     rdx, [rsp+280h+Name]; lpName
0x1400032af  xor     r8d, r8d; dwFlags
0x1400032b2  xor     ecx, ecx; lpMutexAttributes
0x1400032b4  call    cs:__imp_CreateMutexExW
0x1400032ba  mov     rbx, rax
0x1400032bd  test    rax, rax
0x1400032c0  jnz     short loc_1400032CC
0x1400032c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400032c7  jmp     loc_140003511
0x1400032cc  xor     r8d, r8d; bAlertable
0x1400032cf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400032d2  mov     rcx, rbx; hHandle
0x1400032d5  call    cs:__imp_WaitForSingleObjectEx
0x1400032db  cmp     eax, 102h
0x1400032e0  jz      short loc_1400032F2
0x1400032e2  test    eax, 0FFFFFF7Fh
0x1400032e7  jnz     loc_140003549
0x1400032ed  mov     rdi, rbx
0x1400032f0  jmp     short loc_1400032F4
0x1400032f2  xor     edi, edi
0x1400032f4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400032f9  mov     [rsp+280h+hObject], 0
0x140003302  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003307  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000330c  mov     esi, eax
0x14000330e  test    eax, eax
0x140003310  jns     short loc_14000337C
0x140003312  mov     rcx, [rbp+188h]; this
0x140003319  mov     r9d, eax; char *
0x14000331c  mov     edx, 66h ; 'f'; void *
0x140003321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003326  mov     rcx, [rbp+188h]; this
0x14000332d  mov     r9d, esi; char *
0x140003330  mov     edx, 6Fh ; 'o'; void *
0x140003335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000333a  mov     rcx, [rbp+188h]; this
0x140003341  mov     r9d, esi; char *
0x140003344  mov     edx, 12Eh; void *
0x140003349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000334e  test    rdi, rdi
0x140003351  jz      short loc_140003364
0x140003353  mov     rcx, rdi; hMutex
0x140003356  call    cs:__imp_ReleaseMutex
0x14000335c  test    eax, eax
0x14000335e  jz      loc_140003556
0x140003364  mov     rcx, rbx; hObject
0x140003367  call    cs:__imp_CloseHandle
0x14000336d  test    eax, eax
0x14000336f  jz      loc_140003568
0x140003375  mov     eax, esi
0x140003377  jmp     loc_140003511
0x14000337c  mov     rax, [rsp+280h+hObject]
0x140003381  lea     rcx, ds:0[rax*4]
0x140003389  test    rcx, rcx
0x14000338c  jz      short loc_14000339C
0x14000338e  mov     [r15], rcx
0x140003391  mov     eax, [rcx]
0x140003393  inc     eax
0x140003395  mov     [rcx], eax
0x140003397  jmp     loc_1400034E7
0x14000339c  mov     rdx, r14; dwBytes
0x14000339f  mov     qword ptr [r15], 0
0x1400033a6  mov     ecx, 8; dwFlags
0x1400033ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400033b0  mov     rsi, rax
0x1400033b3  test    rax, rax
0x1400033b6  jnz     short loc_1400033D7
0x1400033b8  mov     rcx, [rbp+188h]; this
0x1400033bf  mov     r14d, 8007000Eh
0x1400033c5  mov     r9d, r14d; char *
0x1400033c8  mov     edx, 14Bh; void *
0x1400033cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400033d2  jmp     loc_140003463
0x1400033d7  xorps   xmm0, xmm0
0x1400033da  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400033e0  test    sil, 3
0x1400033e4  jnz     loc_14000357A
0x1400033ea  mov     r9, rsi
0x1400033ed  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400033f2  shr     r9, 2; unsigned __int64
0x1400033f6  lea     rcx, [rsp+280h+hObject]; this
0x1400033fb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003400  mov     r14d, eax
0x140003403  test    eax, eax
0x140003405  jns     loc_1400034A3
0x14000340b  mov     rcx, [rbp+188h]; this
0x140003412  mov     r9d, eax; char *
0x140003415  mov     edx, 14Eh; void *
0x14000341a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000341f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003424  test    rcx, rcx
0x140003427  jz      short loc_140003437
0x140003429  call    cs:__imp_CloseHandle
0x14000342f  test    eax, eax
0x140003431  jz      loc_140003580
0x140003437  mov     rcx, [rsp+280h+hObject]; hObject
0x14000343c  test    rcx, rcx
0x14000343f  jz      short loc_14000344F
0x140003441  call    cs:__imp_CloseHandle
0x140003447  test    eax, eax
0x140003449  jz      loc_140003592
0x14000344f  call    cs:__imp_GetProcessHeap
0x140003455  mov     r8, rsi; lpMem
0x140003458  xor     edx, edx; dwFlags
0x14000345a  mov     rcx, rax; hHeap
0x14000345d  call    cs:__imp_HeapFree
0x140003463  mov     rcx, [rbp+188h]; this
0x14000346a  mov     r9d, r14d; char *
0x14000346d  mov     edx, 137h; void *
0x140003472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003477  test    rdi, rdi
0x14000347a  jz      short loc_14000348D
0x14000347c  mov     rcx, rdi; hMutex
0x14000347f  call    cs:__imp_ReleaseMutex
0x140003485  test    eax, eax
0x140003487  jz      loc_1400035A4
0x14000348d  mov     rcx, rbx; hObject
0x140003490  call    cs:__imp_CloseHandle
0x140003496  test    eax, eax
0x140003498  jz      loc_1400035B6
0x14000349e  mov     eax, r14d
0x1400034a1  jmp     short loc_140003511
0x1400034a3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400034a8  xor     edx, edx; Val
0x1400034aa  mov     dword ptr [rsi], 1
0x1400034b0  lea     rcx, [rsi+22h]; void *
0x1400034b4  mov     [rsi+8], rbx
0x1400034b8  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400034bd  lea     r8d, [rdx+56h]; Size
0x1400034c1  call    memset_0
0x1400034c6  xor     edx, edx; Val
0x1400034c8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400034ce  lea     rcx, [rsi+28h]; void *
0x1400034d2  mov     dword ptr [rsi+24h], 1
0x1400034d9  lea     r8d, [rdx+50h]; Size
0x1400034dd  call    memset_0
0x1400034e2  xor     ebx, ebx
0x1400034e4  mov     [r15], rsi
0x1400034e7  test    rdi, rdi
0x1400034ea  jz      short loc_1400034FD
0x1400034ec  mov     rcx, rdi; hMutex
0x1400034ef  call    cs:__imp_ReleaseMutex
0x1400034f5  test    eax, eax
0x1400034f7  jz      loc_1400035C8
0x1400034fd  test    rbx, rbx
0x140003500  jz      short loc_14000350F
0x140003502  mov     rcx, rbx; hObject
0x140003505  call    cs:__imp_CloseHandle
0x14000350b  test    eax, eax
0x14000350d  jz      short loc_140003537
0x14000350f  xor     eax, eax
0x140003511  mov     rcx, [rbp+180h+var_30]
0x140003518  xor     rcx, rsp; StackCookie
0x14000351b  call    __security_check_cookie
0x140003520  mov     rbx, [rsp+280h+arg_10]
0x140003528  add     rsp, 260h
0x14000352f  pop     r15
0x140003531  pop     r14
0x140003533  pop     rdi
0x140003534  pop     rsi
0x140003535  pop     rbp
0x140003536  retn
0x140003537  mov     rcx, [rbp+188h]; this
0x14000353e  mov     edx, 0A0Bh; void *
0x140003543  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003549  mov     rcx, [rbp+188h]; this
0x140003550  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003556  mov     rcx, [rbp+188h]; this
0x14000355d  mov     edx, 0A15h; void *
0x140003562  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003568  mov     rcx, [rbp+188h]; this
0x14000356f  mov     edx, 0A0Bh; void *
0x140003574  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000357a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003580  mov     rcx, [rbp+188h]; this
0x140003587  mov     edx, 0A0Bh; void *
0x14000358c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003592  mov     rcx, [rbp+188h]; this
0x140003599  mov     edx, 0A0Bh; void *
0x14000359e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035a4  mov     rcx, [rbp+188h]; this
0x1400035ab  mov     edx, 0A15h; void *
0x1400035b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035b6  mov     rcx, [rbp+188h]; this
0x1400035bd  mov     edx, 0A0Bh; void *
0x1400035c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035c8  mov     rcx, [rbp+188h]; this
0x1400035cf  mov     edx, 0A15h; void *
0x1400035d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
