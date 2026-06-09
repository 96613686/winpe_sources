# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001223c`
- end: `0x1800125da`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001399c`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180003d7c`
- `0x18000c600`
- `0x18001223c`
- `0x1800129b0`
- `0x180012e14`
- `0x180013738`
- `0x180015630`
- `0x180015d78`
- `0x1800165b8`
- `0x1800165c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012505`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800122d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800122d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012356`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001247f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012356`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001247f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800122b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800122b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001245d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001245d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001244f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001244f`

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
0x18001223c  mov     [rsp-8+arg_10], rbx
0x180012241  push    rbp
0x180012242  push    rsi
0x180012243  push    rdi
0x180012244  push    r14
0x180012246  push    r15
0x180012248  lea     rbp, [rsp-160h]
0x180012250  sub     rsp, 260h
0x180012257  mov     rax, cs:__security_cookie
0x18001225e  xor     rax, rsp
0x180012261  mov     [rbp+180h+var_30], rax
0x180012268  mov     r15, rdx
0x18001226b  mov     qword ptr [rdx], 0
0x180012272  mov     rbx, rcx
0x180012275  call    cs:__imp_GetCurrentProcessId
0x18001227b  mov     r14d, 78h ; 'x'
0x180012281  mov     [rsp+280h+var_258], rbx
0x180012286  mov     r9d, eax
0x180012289  mov     [rsp+280h+var_260], r14d; int
0x18001228e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180012295  mov     edx, 104h; unsigned __int64
0x18001229a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001229f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800122a4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800122aa  lea     rdx, [rsp+280h+Name]; lpName
0x1800122af  xor     r8d, r8d; dwFlags
0x1800122b2  xor     ecx, ecx; lpMutexAttributes
0x1800122b4  call    cs:__imp_CreateMutexExW
0x1800122ba  mov     rbx, rax
0x1800122bd  test    rax, rax
0x1800122c0  jnz     short loc_1800122CC
0x1800122c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800122c7  jmp     loc_180012511
0x1800122cc  xor     r8d, r8d; bAlertable
0x1800122cf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800122d2  mov     rcx, rbx; hHandle
0x1800122d5  call    cs:__imp_WaitForSingleObjectEx
0x1800122db  cmp     eax, 102h
0x1800122e0  jz      short loc_1800122F2
0x1800122e2  test    eax, 0FFFFFF7Fh
0x1800122e7  jnz     loc_180012549
0x1800122ed  mov     rdi, rbx
0x1800122f0  jmp     short loc_1800122F4
0x1800122f2  xor     edi, edi
0x1800122f4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800122f9  mov     [rsp+280h+hObject], 0
0x180012302  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012307  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001230c  mov     esi, eax
0x18001230e  test    eax, eax
0x180012310  jns     short loc_18001237C
0x180012312  mov     rcx, [rbp+188h]; this
0x180012319  mov     r9d, eax; char *
0x18001231c  mov     edx, 66h ; 'f'; void *
0x180012321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012326  mov     rcx, [rbp+188h]; this
0x18001232d  mov     r9d, esi; char *
0x180012330  mov     edx, 6Fh ; 'o'; void *
0x180012335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001233a  mov     rcx, [rbp+188h]; this
0x180012341  mov     r9d, esi; char *
0x180012344  mov     edx, 12Eh; void *
0x180012349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001234e  test    rdi, rdi
0x180012351  jz      short loc_180012364
0x180012353  mov     rcx, rdi; hMutex
0x180012356  call    cs:__imp_ReleaseMutex
0x18001235c  test    eax, eax
0x18001235e  jz      loc_180012556
0x180012364  mov     rcx, rbx; hObject
0x180012367  call    cs:__imp_CloseHandle
0x18001236d  test    eax, eax
0x18001236f  jz      loc_180012568
0x180012375  mov     eax, esi
0x180012377  jmp     loc_180012511
0x18001237c  mov     rax, [rsp+280h+hObject]
0x180012381  lea     rcx, ds:0[rax*4]
0x180012389  test    rcx, rcx
0x18001238c  jz      short loc_18001239C
0x18001238e  mov     [r15], rcx
0x180012391  mov     eax, [rcx]
0x180012393  inc     eax
0x180012395  mov     [rcx], eax
0x180012397  jmp     loc_1800124E7
0x18001239c  mov     rdx, r14; dwBytes
0x18001239f  mov     qword ptr [r15], 0
0x1800123a6  mov     ecx, 8; dwFlags
0x1800123ab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800123b0  mov     rsi, rax
0x1800123b3  test    rax, rax
0x1800123b6  jnz     short loc_1800123D7
0x1800123b8  mov     rcx, [rbp+188h]; this
0x1800123bf  mov     r14d, 8007000Eh
0x1800123c5  mov     r9d, r14d; char *
0x1800123c8  mov     edx, 14Bh; void *
0x1800123cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123d2  jmp     loc_180012463
0x1800123d7  xorps   xmm0, xmm0
0x1800123da  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800123e0  test    sil, 3
0x1800123e4  jnz     loc_18001257A
0x1800123ea  mov     r9, rsi
0x1800123ed  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800123f2  shr     r9, 2; unsigned __int64
0x1800123f6  lea     rcx, [rsp+280h+hObject]; this
0x1800123fb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180012400  mov     r14d, eax
0x180012403  test    eax, eax
0x180012405  jns     loc_1800124A3
0x18001240b  mov     rcx, [rbp+188h]; this
0x180012412  mov     r9d, eax; char *
0x180012415  mov     edx, 14Eh; void *
0x18001241a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001241f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180012424  test    rcx, rcx
0x180012427  jz      short loc_180012437
0x180012429  call    cs:__imp_CloseHandle
0x18001242f  test    eax, eax
0x180012431  jz      loc_180012580
0x180012437  mov     rcx, [rsp+280h+hObject]; hObject
0x18001243c  test    rcx, rcx
0x18001243f  jz      short loc_18001244F
0x180012441  call    cs:__imp_CloseHandle
0x180012447  test    eax, eax
0x180012449  jz      loc_180012592
0x18001244f  call    cs:__imp_GetProcessHeap
0x180012455  mov     r8, rsi; lpMem
0x180012458  xor     edx, edx; dwFlags
0x18001245a  mov     rcx, rax; hHeap
0x18001245d  call    cs:__imp_HeapFree
0x180012463  mov     rcx, [rbp+188h]; this
0x18001246a  mov     r9d, r14d; char *
0x18001246d  mov     edx, 137h; void *
0x180012472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012477  test    rdi, rdi
0x18001247a  jz      short loc_18001248D
0x18001247c  mov     rcx, rdi; hMutex
0x18001247f  call    cs:__imp_ReleaseMutex
0x180012485  test    eax, eax
0x180012487  jz      loc_1800125A4
0x18001248d  mov     rcx, rbx; hObject
0x180012490  call    cs:__imp_CloseHandle
0x180012496  test    eax, eax
0x180012498  jz      loc_1800125B6
0x18001249e  mov     eax, r14d
0x1800124a1  jmp     short loc_180012511
0x1800124a3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800124a8  xor     edx, edx; Val
0x1800124aa  mov     dword ptr [rsi], 1
0x1800124b0  lea     rcx, [rsi+22h]; void *
0x1800124b4  mov     [rsi+8], rbx
0x1800124b8  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800124bd  lea     r8d, [rdx+56h]; Size
0x1800124c1  call    memset_0
0x1800124c6  xor     edx, edx; Val
0x1800124c8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800124ce  lea     rcx, [rsi+28h]; void *
0x1800124d2  mov     dword ptr [rsi+24h], 1
0x1800124d9  lea     r8d, [rdx+50h]; Size
0x1800124dd  call    memset_0
0x1800124e2  xor     ebx, ebx
0x1800124e4  mov     [r15], rsi
0x1800124e7  test    rdi, rdi
0x1800124ea  jz      short loc_1800124FD
0x1800124ec  mov     rcx, rdi; hMutex
0x1800124ef  call    cs:__imp_ReleaseMutex
0x1800124f5  test    eax, eax
0x1800124f7  jz      loc_1800125C8
0x1800124fd  test    rbx, rbx
0x180012500  jz      short loc_18001250F
0x180012502  mov     rcx, rbx; hObject
0x180012505  call    cs:__imp_CloseHandle
0x18001250b  test    eax, eax
0x18001250d  jz      short loc_180012537
0x18001250f  xor     eax, eax
0x180012511  mov     rcx, [rbp+180h+var_30]
0x180012518  xor     rcx, rsp; StackCookie
0x18001251b  call    __security_check_cookie
0x180012520  mov     rbx, [rsp+280h+arg_10]
0x180012528  add     rsp, 260h
0x18001252f  pop     r15
0x180012531  pop     r14
0x180012533  pop     rdi
0x180012534  pop     rsi
0x180012535  pop     rbp
0x180012536  retn
0x180012537  mov     rcx, [rbp+188h]; this
0x18001253e  mov     edx, 0A0Bh; void *
0x180012543  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012549  mov     rcx, [rbp+188h]; this
0x180012550  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012556  mov     rcx, [rbp+188h]; this
0x18001255d  mov     edx, 0A15h; void *
0x180012562  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012568  mov     rcx, [rbp+188h]; this
0x18001256f  mov     edx, 0A0Bh; void *
0x180012574  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001257a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012580  mov     rcx, [rbp+188h]; this
0x180012587  mov     edx, 0A0Bh; void *
0x18001258c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012592  mov     rcx, [rbp+188h]; this
0x180012599  mov     edx, 0A0Bh; void *
0x18001259e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800125a4  mov     rcx, [rbp+188h]; this
0x1800125ab  mov     edx, 0A15h; void *
0x1800125b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800125b6  mov     rcx, [rbp+188h]; this
0x1800125bd  mov     edx, 0A0Bh; void *
0x1800125c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800125c8  mov     rcx, [rbp+188h]; this
0x1800125cf  mov     edx, 0A15h; void *
0x1800125d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
