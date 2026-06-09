# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800061c8`
- end: `0x180006590`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007c44`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x1800061c8`
- `0x180006990`
- `0x180006fdc`
- `0x180007930`
- `0x1800088e0`
- `0x18000a0f4`
- `0x18000ac20`
- `0x18000b0ac`
- `0x18000bf6c`
- `0x18000bf7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006261`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006261`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006435`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800064a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006435`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800064a5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006240`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006240`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000640c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000640c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064bb`

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
0x1800061c8  mov     [rsp-8+arg_10], rbx
0x1800061cd  push    rbp
0x1800061ce  push    rsi
0x1800061cf  push    rdi
0x1800061d0  push    r14
0x1800061d2  push    r15
0x1800061d4  lea     rbp, [rsp-160h]
0x1800061dc  sub     rsp, 260h
0x1800061e3  mov     rax, cs:__security_cookie
0x1800061ea  xor     rax, rsp
0x1800061ed  mov     [rbp+180h+var_30], rax
0x1800061f4  mov     r15, rdx
0x1800061f7  mov     qword ptr [rdx], 0
0x1800061fe  mov     rbx, rcx
0x180006201  call    cs:__imp_GetCurrentProcessId
0x180006207  mov     r14d, 78h ; 'x'
0x18000620d  mov     [rsp+280h+var_258], rbx
0x180006212  mov     r9d, eax
0x180006215  mov     [rsp+280h+var_260], r14d; int
0x18000621a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006221  mov     edx, 104h; unsigned __int64
0x180006226  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000622b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006230  mov     r9d, 1F0001h; dwDesiredAccess
0x180006236  lea     rdx, [rsp+280h+Name]; lpName
0x18000623b  xor     r8d, r8d; dwFlags
0x18000623e  xor     ecx, ecx; lpMutexAttributes
0x180006240  call    cs:__imp_CreateMutexExW
0x180006246  mov     rbx, rax
0x180006249  test    rax, rax
0x18000624c  jnz     short loc_180006258
0x18000624e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006253  jmp     loc_1800064C7
0x180006258  xor     r8d, r8d; bAlertable
0x18000625b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000625e  mov     rcx, rbx; hHandle
0x180006261  call    cs:__imp_WaitForSingleObjectEx
0x180006267  cmp     eax, 102h
0x18000626c  jz      short loc_18000627E
0x18000626e  test    eax, 0FFFFFF7Fh
0x180006273  jnz     loc_1800064FF
0x180006279  mov     rdi, rbx
0x18000627c  jmp     short loc_180006280
0x18000627e  xor     edi, edi
0x180006280  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006285  mov     [rsp+280h+hObject], 0
0x18000628e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006293  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180006298  mov     esi, eax
0x18000629a  test    eax, eax
0x18000629c  jns     short loc_18000631D
0x18000629e  mov     rcx, [rbp+188h]; this
0x1800062a5  lea     r8, aWil; "wil"
0x1800062ac  mov     r9d, eax; char *
0x1800062af  mov     edx, 66h ; 'f'; void *
0x1800062b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062b9  mov     rcx, [rbp+188h]; this
0x1800062c0  lea     r8, aWil; "wil"
0x1800062c7  mov     r9d, esi; char *
0x1800062ca  mov     edx, 6Fh ; 'o'; void *
0x1800062cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062d4  mov     rcx, [rbp+188h]; this
0x1800062db  lea     r8, aWil; "wil"
0x1800062e2  mov     r9d, esi; char *
0x1800062e5  mov     edx, 12Eh; void *
0x1800062ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062ef  test    rdi, rdi
0x1800062f2  jz      short loc_180006305
0x1800062f4  mov     rcx, rdi; hMutex
0x1800062f7  call    cs:__imp_ReleaseMutex
0x1800062fd  test    eax, eax
0x1800062ff  jz      loc_18000650C
0x180006305  mov     rcx, rbx; hObject
0x180006308  call    cs:__imp_CloseHandle
0x18000630e  test    eax, eax
0x180006310  jz      loc_18000651E
0x180006316  mov     eax, esi
0x180006318  jmp     loc_1800064C7
0x18000631d  mov     rax, [rsp+280h+hObject]
0x180006322  lea     rcx, ds:0[rax*4]
0x18000632a  test    rcx, rcx
0x18000632d  jz      short loc_18000633D
0x18000632f  mov     [r15], rcx
0x180006332  mov     eax, [rcx]
0x180006334  inc     eax
0x180006336  mov     [rcx], eax
0x180006338  jmp     loc_18000649D
0x18000633d  mov     rdx, r14; dwBytes
0x180006340  mov     qword ptr [r15], 0
0x180006347  mov     ecx, 8; dwFlags
0x18000634c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006351  mov     rsi, rax
0x180006354  test    rax, rax
0x180006357  jnz     short loc_18000637F
0x180006359  mov     rcx, [rbp+188h]; this
0x180006360  lea     r8, aWil; "wil"
0x180006367  mov     r14d, 8007000Eh
0x18000636d  mov     edx, 14Bh; void *
0x180006372  mov     r9d, r14d; char *
0x180006375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000637a  jmp     loc_180006412
0x18000637f  xorps   xmm0, xmm0
0x180006382  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006388  test    sil, 3
0x18000638c  jnz     loc_180006530
0x180006392  mov     r9, rsi
0x180006395  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000639a  shr     r9, 2; unsigned __int64
0x18000639e  lea     rcx, [rsp+280h+hObject]; this
0x1800063a3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800063a8  mov     r14d, eax
0x1800063ab  test    eax, eax
0x1800063ad  jns     loc_180006459
0x1800063b3  mov     rcx, [rbp+188h]; this
0x1800063ba  lea     r8, aWil; "wil"
0x1800063c1  mov     r9d, eax; char *
0x1800063c4  mov     edx, 14Eh; void *
0x1800063c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063ce  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800063d3  test    rcx, rcx
0x1800063d6  jz      short loc_1800063E6
0x1800063d8  call    cs:__imp_CloseHandle
0x1800063de  test    eax, eax
0x1800063e0  jz      loc_180006536
0x1800063e6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800063eb  test    rcx, rcx
0x1800063ee  jz      short loc_1800063FE
0x1800063f0  call    cs:__imp_CloseHandle
0x1800063f6  test    eax, eax
0x1800063f8  jz      loc_180006548
0x1800063fe  call    cs:__imp_GetProcessHeap
0x180006404  mov     r8, rsi; lpMem
0x180006407  xor     edx, edx; dwFlags
0x180006409  mov     rcx, rax; hHeap
0x18000640c  call    cs:__imp_HeapFree
0x180006412  mov     rcx, [rbp+188h]; this
0x180006419  lea     r8, aWil; "wil"
0x180006420  mov     r9d, r14d; char *
0x180006423  mov     edx, 137h; void *
0x180006428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000642d  test    rdi, rdi
0x180006430  jz      short loc_180006443
0x180006432  mov     rcx, rdi; hMutex
0x180006435  call    cs:__imp_ReleaseMutex
0x18000643b  test    eax, eax
0x18000643d  jz      loc_18000655A
0x180006443  mov     rcx, rbx; hObject
0x180006446  call    cs:__imp_CloseHandle
0x18000644c  test    eax, eax
0x18000644e  jz      loc_18000656C
0x180006454  mov     eax, r14d
0x180006457  jmp     short loc_1800064C7
0x180006459  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000645e  xor     edx, edx; Val
0x180006460  mov     dword ptr [rsi], 1
0x180006466  lea     rcx, [rsi+22h]; void *
0x18000646a  mov     [rsi+8], rbx
0x18000646e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006473  lea     r8d, [rdx+56h]; Size
0x180006477  call    memset_0
0x18000647c  xor     edx, edx; Val
0x18000647e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006484  lea     rcx, [rsi+28h]; void *
0x180006488  mov     dword ptr [rsi+24h], 1
0x18000648f  lea     r8d, [rdx+50h]; Size
0x180006493  call    memset_0
0x180006498  xor     ebx, ebx
0x18000649a  mov     [r15], rsi
0x18000649d  test    rdi, rdi
0x1800064a0  jz      short loc_1800064B3
0x1800064a2  mov     rcx, rdi; hMutex
0x1800064a5  call    cs:__imp_ReleaseMutex
0x1800064ab  test    eax, eax
0x1800064ad  jz      loc_18000657E
0x1800064b3  test    rbx, rbx
0x1800064b6  jz      short loc_1800064C5
0x1800064b8  mov     rcx, rbx; hObject
0x1800064bb  call    cs:__imp_CloseHandle
0x1800064c1  test    eax, eax
0x1800064c3  jz      short loc_1800064ED
0x1800064c5  xor     eax, eax
0x1800064c7  mov     rcx, [rbp+180h+var_30]
0x1800064ce  xor     rcx, rsp; StackCookie
0x1800064d1  call    __security_check_cookie
0x1800064d6  mov     rbx, [rsp+280h+arg_10]
0x1800064de  add     rsp, 260h
0x1800064e5  pop     r15
0x1800064e7  pop     r14
0x1800064e9  pop     rdi
0x1800064ea  pop     rsi
0x1800064eb  pop     rbp
0x1800064ec  retn
0x1800064ed  mov     rcx, [rbp+188h]; this
0x1800064f4  mov     edx, 0A0Bh; void *
0x1800064f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064ff  mov     rcx, [rbp+188h]; this
0x180006506  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000650c  mov     rcx, [rbp+188h]; this
0x180006513  mov     edx, 0A15h; void *
0x180006518  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000651e  mov     rcx, [rbp+188h]; this
0x180006525  mov     edx, 0A0Bh; void *
0x18000652a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006530  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006536  mov     rcx, [rbp+188h]; this
0x18000653d  mov     edx, 0A0Bh; void *
0x180006542  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006548  mov     rcx, [rbp+188h]; this
0x18000654f  mov     edx, 0A0Bh; void *
0x180006554  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000655a  mov     rcx, [rbp+188h]; this
0x180006561  mov     edx, 0A15h; void *
0x180006566  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000656c  mov     rcx, [rbp+188h]; this
0x180006573  mov     edx, 0A0Bh; void *
0x180006578  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000657e  mov     rcx, [rbp+188h]; this
0x180006585  mov     edx, 0A15h; void *
0x18000658a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
