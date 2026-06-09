# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800298b4`
- end: `0x180029c99`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `997`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18002ac1c`

## callees

- `0x180005de8`
- `0x18000a7b0`
- `0x18000ace0`
- `0x18000b320`
- `0x18000b85c`
- `0x18000cfe8`
- `0x18000d5a4`
- `0x18000e238`
- `0x18000e248`
- `0x1800298b4`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029b17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800298ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800298ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800299ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029b4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029bd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800299ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029b4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029bd8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002994f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002994f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002992d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002992d`

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
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE v43; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h]
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
  v43 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)&v43,
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4LL * (_QWORD)v43);
  if ( 4LL * (_QWORD)v43 )
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
    v43 = 0;
    hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)&v43,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      v24[2] = v43;
      v24[3] = hObject;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      *a2 = v24;
      v6 = 0;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( v43 && !CloseHandle(v43) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v42);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x1800298b4  mov     [rsp-8+arg_10], rbx
0x1800298b9  push    rbp
0x1800298ba  push    rsi
0x1800298bb  push    rdi
0x1800298bc  push    r14
0x1800298be  push    r15
0x1800298c0  lea     rbp, [rsp-160h]
0x1800298c8  sub     rsp, 260h
0x1800298cf  mov     rax, cs:__security_cookie
0x1800298d6  xor     rax, rsp
0x1800298d9  mov     [rbp+180h+var_30], rax
0x1800298e0  mov     r15, rdx
0x1800298e3  mov     rbx, rcx
0x1800298e6  mov     qword ptr [rdx], 0
0x1800298ed  call    cs:__imp_GetCurrentProcessId
0x1800298f3  mov     r9d, eax
0x1800298f6  mov     [rsp+280h+var_258], rbx
0x1800298fb  mov     r14d, 78h ; 'x'
0x180029901  mov     [rsp+280h+var_260], r14d; int
0x180029906  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002990d  mov     edx, 104h; unsigned __int64
0x180029912  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180029917  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002991c  nop
0x18002991d  mov     r9d, 1F0001h; dwDesiredAccess
0x180029923  xor     r8d, r8d; dwFlags
0x180029926  lea     rdx, [rsp+280h+Name]; lpName
0x18002992b  xor     ecx, ecx; lpMutexAttributes
0x18002992d  call    cs:__imp_CreateMutexExW
0x180029933  mov     rbx, rax
0x180029936  test    rax, rax
0x180029939  jnz     short loc_180029946
0x18002993b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029940  nop
0x180029941  jmp     loc_180029C08
0x180029946  xor     r8d, r8d; bAlertable
0x180029949  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002994c  mov     rcx, rbx; hHandle
0x18002994f  call    cs:__imp_WaitForSingleObjectEx
0x180029955  cmp     eax, 102h
0x18002995a  jz      short loc_18002996C
0x18002995c  test    eax, 0FFFFFF7Fh
0x180029961  jnz     loc_180029C39
0x180029967  mov     rdi, rbx
0x18002996a  jmp     short loc_18002996E
0x18002996c  xor     edi, edi
0x18002996e  mov     [rsp+280h+var_250], 0
0x180029977  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18002997c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180029981  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180029986  mov     esi, eax
0x180029988  test    eax, eax
0x18002998a  jns     loc_180029A1E
0x180029990  mov     rcx, [rbp+188h]; this
0x180029997  mov     r9d, eax; char *
0x18002999a  lea     r8, aWil; "wil"
0x1800299a1  mov     edx, 66h ; 'f'; void *
0x1800299a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299ab  mov     rcx, [rbp+188h]; this
0x1800299b2  mov     r9d, esi; char *
0x1800299b5  lea     r8, aWil; "wil"
0x1800299bc  mov     edx, 6Fh ; 'o'; void *
0x1800299c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299c6  mov     rcx, [rbp+188h]; this
0x1800299cd  mov     r9d, esi; char *
0x1800299d0  lea     r8, aWil; "wil"
0x1800299d7  mov     edx, 12Eh; void *
0x1800299dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299e1  nop
0x1800299e2  test    rdi, rdi
0x1800299e5  jz      short loc_1800299FF
0x1800299e7  mov     rcx, rdi; hMutex
0x1800299ea  call    cs:__imp_ReleaseMutex
0x1800299f0  mov     rcx, [rbp+188h]; this
0x1800299f7  test    eax, eax
0x1800299f9  jz      loc_180029C46
0x1800299ff  mov     rcx, rbx; hObject
0x180029a02  call    cs:__imp_CloseHandle
0x180029a08  mov     rcx, [rbp+188h]; this
0x180029a0f  test    eax, eax
0x180029a11  jz      loc_180029C51
0x180029a17  mov     eax, esi
0x180029a19  jmp     loc_180029C08
0x180029a1e  mov     rax, [rsp+280h+var_250]
0x180029a23  lea     rcx, ds:0[rax*4]
0x180029a2b  test    rcx, rcx
0x180029a2e  jz      short loc_180029A3E
0x180029a30  mov     [r15], rcx
0x180029a33  mov     eax, [rcx]
0x180029a35  inc     eax
0x180029a37  mov     [rcx], eax
0x180029a39  jmp     loc_180029BD0
0x180029a3e  mov     qword ptr [r15], 0
0x180029a45  mov     rdx, r14; dwBytes
0x180029a48  mov     ecx, 8; dwFlags
0x180029a4d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180029a52  mov     rsi, rax
0x180029a55  test    rax, rax
0x180029a58  jnz     short loc_180029A80
0x180029a5a  mov     rcx, [rbp+188h]; this
0x180029a61  mov     r14d, 8007000Eh
0x180029a67  mov     r9d, r14d; char *
0x180029a6a  lea     r8, aWil; "wil"
0x180029a71  mov     edx, 14Bh; void *
0x180029a76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a7b  jmp     loc_180029B2B
0x180029a80  mov     [rsp+280h+var_250], 0
0x180029a89  mov     [rsp+280h+hObject], 0
0x180029a92  test    sil, 3
0x180029a96  jnz     loc_180029C5C
0x180029a9c  mov     r9, rsi
0x180029a9f  shr     r9, 2; unsigned __int64
0x180029aa3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180029aa8  lea     rcx, [rsp+280h+var_250]; this
0x180029aad  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180029ab2  mov     r14d, eax
0x180029ab5  test    eax, eax
0x180029ab7  jns     loc_180029B84
0x180029abd  mov     rcx, [rbp+188h]; this
0x180029ac4  mov     r9d, eax; char *
0x180029ac7  lea     r8, aWil; "wil"
0x180029ace  mov     edx, 14Eh; void *
0x180029ad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ad8  nop
0x180029ad9  mov     rcx, [rsp+280h+hObject]; hObject
0x180029ade  test    rcx, rcx
0x180029ae1  jz      short loc_180029AF8
0x180029ae3  call    cs:__imp_CloseHandle
0x180029ae9  mov     rcx, [rbp+188h]; this
0x180029af0  test    eax, eax
0x180029af2  jz      loc_180029C62
0x180029af8  mov     rcx, [rsp+280h+var_250]; hObject
0x180029afd  test    rcx, rcx
0x180029b00  jz      short loc_180029B17
0x180029b02  call    cs:__imp_CloseHandle
0x180029b08  mov     rcx, [rbp+188h]; this
0x180029b0f  test    eax, eax
0x180029b11  jz      loc_180029C6D
0x180029b17  call    cs:__imp_GetProcessHeap
0x180029b1d  mov     rcx, rax; hHeap
0x180029b20  mov     r8, rsi; lpMem
0x180029b23  xor     edx, edx; dwFlags
0x180029b25  call    cs:__imp_HeapFree
0x180029b2b  mov     rcx, [rbp+188h]; this
0x180029b32  mov     r9d, r14d; char *
0x180029b35  lea     r8, aWil; "wil"
0x180029b3c  mov     edx, 137h; void *
0x180029b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b46  nop
0x180029b47  test    rdi, rdi
0x180029b4a  jz      short loc_180029B64
0x180029b4c  mov     rcx, rdi; hMutex
0x180029b4f  call    cs:__imp_ReleaseMutex
0x180029b55  mov     rcx, [rbp+188h]; this
0x180029b5c  test    eax, eax
0x180029b5e  jz      loc_180029C78
0x180029b64  mov     rcx, rbx; hObject
0x180029b67  call    cs:__imp_CloseHandle
0x180029b6d  mov     rcx, [rbp+188h]; this
0x180029b74  test    eax, eax
0x180029b76  jz      loc_180029C83
0x180029b7c  mov     eax, r14d
0x180029b7f  jmp     loc_180029C08
0x180029b84  mov     dword ptr [rsi], 1
0x180029b8a  mov     [rsi+8], rbx
0x180029b8e  mov     rax, [rsp+280h+var_250]
0x180029b93  mov     [rsi+10h], rax
0x180029b97  mov     rax, [rsp+280h+hObject]
0x180029b9c  mov     [rsi+18h], rax
0x180029ba0  lea     rcx, [rsi+22h]; void *
0x180029ba4  xor     edx, edx; Val
0x180029ba6  lea     r8d, [rdx+56h]; Size
0x180029baa  call    memset_0
0x180029baf  mov     word ptr [rsi+20h], 58h ; 'X'
0x180029bb5  mov     dword ptr [rsi+24h], 1
0x180029bbc  lea     rcx, [rsi+28h]; void *
0x180029bc0  xor     edx, edx; Val
0x180029bc2  lea     r8d, [rdx+50h]; Size
0x180029bc6  call    memset_0
0x180029bcb  mov     [r15], rsi
0x180029bce  xor     ebx, ebx
0x180029bd0  test    rdi, rdi
0x180029bd3  jz      short loc_180029BED
0x180029bd5  mov     rcx, rdi; hMutex
0x180029bd8  call    cs:__imp_ReleaseMutex
0x180029bde  mov     rcx, [rbp+188h]; this
0x180029be5  test    eax, eax
0x180029be7  jz      loc_180029C8E
0x180029bed  test    rbx, rbx
0x180029bf0  jz      short loc_180029C06
0x180029bf2  mov     rcx, rbx; hObject
0x180029bf5  call    cs:__imp_CloseHandle
0x180029bfb  mov     rcx, [rbp+188h]; this
0x180029c02  test    eax, eax
0x180029c04  jz      short loc_180029C2E
0x180029c06  xor     eax, eax
0x180029c08  mov     rcx, [rbp+180h+var_30]
0x180029c0f  xor     rcx, rsp; StackCookie
0x180029c12  call    __security_check_cookie
0x180029c17  mov     rbx, [rsp+280h+arg_10]
0x180029c1f  add     rsp, 260h
0x180029c26  pop     r15
0x180029c28  pop     r14
0x180029c2a  pop     rdi
0x180029c2b  pop     rsi
0x180029c2c  pop     rbp
0x180029c2d  retn
0x180029c2e  mov     edx, 0A0Bh; void *
0x180029c33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c39  mov     rcx, [rbp+188h]; this
0x180029c40  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180029c46  mov     edx, 0A15h; void *
0x180029c4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c51  mov     edx, 0A0Bh; void *
0x180029c56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180029c62  mov     edx, 0A0Bh; void *
0x180029c67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c6d  mov     edx, 0A0Bh; void *
0x180029c72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c78  mov     edx, 0A15h; void *
0x180029c7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c83  mov     edx, 0A0Bh; void *
0x180029c88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029c8e  mov     edx, 0A15h; void *
0x180029c93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
