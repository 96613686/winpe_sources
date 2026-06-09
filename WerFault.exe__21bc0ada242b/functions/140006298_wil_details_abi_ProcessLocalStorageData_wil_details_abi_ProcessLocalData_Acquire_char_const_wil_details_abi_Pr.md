# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140006298`
- end: `0x140006660`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400080b8`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140006298`
- `0x140006a60`
- `0x140006fa8`
- `0x140007e50`
- `0x140008ca8`
- `0x14000a9c4`
- `0x14000b540`
- `0x14000b9ac`
- `0x14000c59c`
- `0x14000c5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006331`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140006331`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006310`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140006310`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400063c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006505`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006575`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400063c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006505`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006575`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400064dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400064dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400064ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400064ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400062d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400062d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000658b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400064c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006516`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000658b`

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
0x140006298  mov     [rsp-8+arg_10], rbx
0x14000629d  push    rbp
0x14000629e  push    rsi
0x14000629f  push    rdi
0x1400062a0  push    r14
0x1400062a2  push    r15
0x1400062a4  lea     rbp, [rsp-160h]
0x1400062ac  sub     rsp, 260h
0x1400062b3  mov     rax, cs:__security_cookie
0x1400062ba  xor     rax, rsp
0x1400062bd  mov     [rbp+180h+var_30], rax
0x1400062c4  mov     r15, rdx
0x1400062c7  mov     qword ptr [rdx], 0
0x1400062ce  mov     rbx, rcx
0x1400062d1  call    cs:__imp_GetCurrentProcessId
0x1400062d7  mov     r14d, 78h ; 'x'
0x1400062dd  mov     [rsp+280h+var_258], rbx
0x1400062e2  mov     r9d, eax
0x1400062e5  mov     [rsp+280h+var_260], r14d; int
0x1400062ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400062f1  mov     edx, 104h; unsigned __int64
0x1400062f6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400062fb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140006300  mov     r9d, 1F0001h; dwDesiredAccess
0x140006306  lea     rdx, [rsp+280h+Name]; lpName
0x14000630b  xor     r8d, r8d; dwFlags
0x14000630e  xor     ecx, ecx; lpMutexAttributes
0x140006310  call    cs:__imp_CreateMutexExW
0x140006316  mov     rbx, rax
0x140006319  test    rax, rax
0x14000631c  jnz     short loc_140006328
0x14000631e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006323  jmp     loc_140006597
0x140006328  xor     r8d, r8d; bAlertable
0x14000632b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000632e  mov     rcx, rbx; hHandle
0x140006331  call    cs:__imp_WaitForSingleObjectEx
0x140006337  cmp     eax, 102h
0x14000633c  jz      short loc_14000634E
0x14000633e  test    eax, 0FFFFFF7Fh
0x140006343  jnz     loc_1400065CF
0x140006349  mov     rdi, rbx
0x14000634c  jmp     short loc_140006350
0x14000634e  xor     edi, edi
0x140006350  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140006355  mov     [rsp+280h+hObject], 0
0x14000635e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140006363  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140006368  mov     esi, eax
0x14000636a  test    eax, eax
0x14000636c  jns     short loc_1400063ED
0x14000636e  mov     rcx, [rbp+188h]; this
0x140006375  lea     r8, aWil; "wil"
0x14000637c  mov     r9d, eax; char *
0x14000637f  mov     edx, 66h ; 'f'; void *
0x140006384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006389  mov     rcx, [rbp+188h]; this
0x140006390  lea     r8, aWil; "wil"
0x140006397  mov     r9d, esi; char *
0x14000639a  mov     edx, 6Fh ; 'o'; void *
0x14000639f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400063a4  mov     rcx, [rbp+188h]; this
0x1400063ab  lea     r8, aWil; "wil"
0x1400063b2  mov     r9d, esi; char *
0x1400063b5  mov     edx, 12Eh; void *
0x1400063ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400063bf  test    rdi, rdi
0x1400063c2  jz      short loc_1400063D5
0x1400063c4  mov     rcx, rdi; hMutex
0x1400063c7  call    cs:__imp_ReleaseMutex
0x1400063cd  test    eax, eax
0x1400063cf  jz      loc_1400065DC
0x1400063d5  mov     rcx, rbx; hObject
0x1400063d8  call    cs:__imp_CloseHandle
0x1400063de  test    eax, eax
0x1400063e0  jz      loc_1400065EE
0x1400063e6  mov     eax, esi
0x1400063e8  jmp     loc_140006597
0x1400063ed  mov     rax, [rsp+280h+hObject]
0x1400063f2  lea     rcx, ds:0[rax*4]
0x1400063fa  test    rcx, rcx
0x1400063fd  jz      short loc_14000640D
0x1400063ff  mov     [r15], rcx
0x140006402  mov     eax, [rcx]
0x140006404  inc     eax
0x140006406  mov     [rcx], eax
0x140006408  jmp     loc_14000656D
0x14000640d  mov     rdx, r14; dwBytes
0x140006410  mov     qword ptr [r15], 0
0x140006417  mov     ecx, 8; dwFlags
0x14000641c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006421  mov     rsi, rax
0x140006424  test    rax, rax
0x140006427  jnz     short loc_14000644F
0x140006429  mov     rcx, [rbp+188h]; this
0x140006430  lea     r8, aWil; "wil"
0x140006437  mov     r14d, 8007000Eh
0x14000643d  mov     edx, 14Bh; void *
0x140006442  mov     r9d, r14d; char *
0x140006445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000644a  jmp     loc_1400064E2
0x14000644f  xorps   xmm0, xmm0
0x140006452  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140006458  test    sil, 3
0x14000645c  jnz     loc_140006600
0x140006462  mov     r9, rsi
0x140006465  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14000646a  shr     r9, 2; unsigned __int64
0x14000646e  lea     rcx, [rsp+280h+hObject]; this
0x140006473  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x140006478  mov     r14d, eax
0x14000647b  test    eax, eax
0x14000647d  jns     loc_140006529
0x140006483  mov     rcx, [rbp+188h]; this
0x14000648a  lea     r8, aWil; "wil"
0x140006491  mov     r9d, eax; char *
0x140006494  mov     edx, 14Eh; void *
0x140006499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000649e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400064a3  test    rcx, rcx
0x1400064a6  jz      short loc_1400064B6
0x1400064a8  call    cs:__imp_CloseHandle
0x1400064ae  test    eax, eax
0x1400064b0  jz      loc_140006606
0x1400064b6  mov     rcx, [rsp+280h+hObject]; hObject
0x1400064bb  test    rcx, rcx
0x1400064be  jz      short loc_1400064CE
0x1400064c0  call    cs:__imp_CloseHandle
0x1400064c6  test    eax, eax
0x1400064c8  jz      loc_140006618
0x1400064ce  call    cs:__imp_GetProcessHeap
0x1400064d4  mov     r8, rsi; lpMem
0x1400064d7  xor     edx, edx; dwFlags
0x1400064d9  mov     rcx, rax; hHeap
0x1400064dc  call    cs:__imp_HeapFree
0x1400064e2  mov     rcx, [rbp+188h]; this
0x1400064e9  lea     r8, aWil; "wil"
0x1400064f0  mov     r9d, r14d; char *
0x1400064f3  mov     edx, 137h; void *
0x1400064f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064fd  test    rdi, rdi
0x140006500  jz      short loc_140006513
0x140006502  mov     rcx, rdi; hMutex
0x140006505  call    cs:__imp_ReleaseMutex
0x14000650b  test    eax, eax
0x14000650d  jz      loc_14000662A
0x140006513  mov     rcx, rbx; hObject
0x140006516  call    cs:__imp_CloseHandle
0x14000651c  test    eax, eax
0x14000651e  jz      loc_14000663C
0x140006524  mov     eax, r14d
0x140006527  jmp     short loc_140006597
0x140006529  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000652e  xor     edx, edx; Val
0x140006530  mov     dword ptr [rsi], 1
0x140006536  lea     rcx, [rsi+22h]; void *
0x14000653a  mov     [rsi+8], rbx
0x14000653e  movdqu  xmmword ptr [rsi+10h], xmm0
0x140006543  lea     r8d, [rdx+56h]; Size
0x140006547  call    memset_0
0x14000654c  xor     edx, edx; Val
0x14000654e  mov     word ptr [rsi+20h], 58h ; 'X'
0x140006554  lea     rcx, [rsi+28h]; void *
0x140006558  mov     dword ptr [rsi+24h], 1
0x14000655f  lea     r8d, [rdx+50h]; Size
0x140006563  call    memset_0
0x140006568  xor     ebx, ebx
0x14000656a  mov     [r15], rsi
0x14000656d  test    rdi, rdi
0x140006570  jz      short loc_140006583
0x140006572  mov     rcx, rdi; hMutex
0x140006575  call    cs:__imp_ReleaseMutex
0x14000657b  test    eax, eax
0x14000657d  jz      loc_14000664E
0x140006583  test    rbx, rbx
0x140006586  jz      short loc_140006595
0x140006588  mov     rcx, rbx; hObject
0x14000658b  call    cs:__imp_CloseHandle
0x140006591  test    eax, eax
0x140006593  jz      short loc_1400065BD
0x140006595  xor     eax, eax
0x140006597  mov     rcx, [rbp+180h+var_30]
0x14000659e  xor     rcx, rsp; StackCookie
0x1400065a1  call    __security_check_cookie
0x1400065a6  mov     rbx, [rsp+280h+arg_10]
0x1400065ae  add     rsp, 260h
0x1400065b5  pop     r15
0x1400065b7  pop     r14
0x1400065b9  pop     rdi
0x1400065ba  pop     rsi
0x1400065bb  pop     rbp
0x1400065bc  retn
0x1400065bd  mov     rcx, [rbp+188h]; this
0x1400065c4  mov     edx, 0A0Bh; void *
0x1400065c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400065cf  mov     rcx, [rbp+188h]; this
0x1400065d6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400065dc  mov     rcx, [rbp+188h]; this
0x1400065e3  mov     edx, 0A15h; void *
0x1400065e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400065ee  mov     rcx, [rbp+188h]; this
0x1400065f5  mov     edx, 0A0Bh; void *
0x1400065fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006600  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006606  mov     rcx, [rbp+188h]; this
0x14000660d  mov     edx, 0A0Bh; void *
0x140006612  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006618  mov     rcx, [rbp+188h]; this
0x14000661f  mov     edx, 0A0Bh; void *
0x140006624  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000662a  mov     rcx, [rbp+188h]; this
0x140006631  mov     edx, 0A15h; void *
0x140006636  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000663c  mov     rcx, [rbp+188h]; this
0x140006643  mov     edx, 0A0Bh; void *
0x140006648  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000664e  mov     rcx, [rbp+188h]; this
0x140006655  mov     edx, 0A15h; void *
0x14000665a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
