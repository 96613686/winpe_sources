# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003818`
- end: `0x180003bb6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004f70`

## callees

- `0x180001760`
- `0x180002194`
- `0x180003818`
- `0x180003f8c`
- `0x1800043e4`
- `0x180004d08`
- `0x1800058f8`
- `0x180006db4`
- `0x1800078a8`
- `0x180007c1c`
- `0x1800083fc`
- `0x18000840c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003890`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003890`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800038b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003932`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003acb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003932`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ae1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ae1`

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
0x180003818  mov     [rsp-8+arg_10], rbx
0x18000381d  push    rbp
0x18000381e  push    rsi
0x18000381f  push    rdi
0x180003820  push    r14
0x180003822  push    r15
0x180003824  lea     rbp, [rsp-160h]
0x18000382c  sub     rsp, 260h
0x180003833  mov     rax, cs:__security_cookie
0x18000383a  xor     rax, rsp
0x18000383d  mov     [rbp+180h+var_30], rax
0x180003844  mov     r15, rdx
0x180003847  mov     qword ptr [rdx], 0
0x18000384e  mov     rbx, rcx
0x180003851  call    cs:__imp_GetCurrentProcessId
0x180003857  mov     r14d, 78h ; 'x'
0x18000385d  mov     [rsp+280h+var_258], rbx
0x180003862  mov     r9d, eax
0x180003865  mov     [rsp+280h+var_260], r14d; int
0x18000386a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003871  mov     edx, 104h; unsigned __int64
0x180003876  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000387b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003880  mov     r9d, 1F0001h; dwDesiredAccess
0x180003886  lea     rdx, [rsp+280h+Name]; lpName
0x18000388b  xor     r8d, r8d; dwFlags
0x18000388e  xor     ecx, ecx; lpMutexAttributes
0x180003890  call    cs:__imp_CreateMutexExW
0x180003896  mov     rbx, rax
0x180003899  test    rax, rax
0x18000389c  jnz     short loc_1800038A8
0x18000389e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800038a3  jmp     loc_180003AED
0x1800038a8  xor     r8d, r8d; bAlertable
0x1800038ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800038ae  mov     rcx, rbx; hHandle
0x1800038b1  call    cs:__imp_WaitForSingleObjectEx
0x1800038b7  cmp     eax, 102h
0x1800038bc  jz      short loc_1800038CE
0x1800038be  test    eax, 0FFFFFF7Fh
0x1800038c3  jnz     loc_180003B25
0x1800038c9  mov     rdi, rbx
0x1800038cc  jmp     short loc_1800038D0
0x1800038ce  xor     edi, edi
0x1800038d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800038d5  mov     [rsp+280h+hObject], 0
0x1800038de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800038e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800038e8  mov     esi, eax
0x1800038ea  test    eax, eax
0x1800038ec  jns     short loc_180003958
0x1800038ee  mov     rcx, [rbp+188h]; this
0x1800038f5  mov     r9d, eax; char *
0x1800038f8  mov     edx, 66h ; 'f'; void *
0x1800038fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003902  mov     rcx, [rbp+188h]; this
0x180003909  mov     r9d, esi; char *
0x18000390c  mov     edx, 6Fh ; 'o'; void *
0x180003911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003916  mov     rcx, [rbp+188h]; this
0x18000391d  mov     r9d, esi; char *
0x180003920  mov     edx, 12Eh; void *
0x180003925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000392a  test    rdi, rdi
0x18000392d  jz      short loc_180003940
0x18000392f  mov     rcx, rdi; hMutex
0x180003932  call    cs:__imp_ReleaseMutex
0x180003938  test    eax, eax
0x18000393a  jz      loc_180003B32
0x180003940  mov     rcx, rbx; hObject
0x180003943  call    cs:__imp_CloseHandle
0x180003949  test    eax, eax
0x18000394b  jz      loc_180003B44
0x180003951  mov     eax, esi
0x180003953  jmp     loc_180003AED
0x180003958  mov     rax, [rsp+280h+hObject]
0x18000395d  lea     rcx, ds:0[rax*4]
0x180003965  test    rcx, rcx
0x180003968  jz      short loc_180003978
0x18000396a  mov     [r15], rcx
0x18000396d  mov     eax, [rcx]
0x18000396f  inc     eax
0x180003971  mov     [rcx], eax
0x180003973  jmp     loc_180003AC3
0x180003978  mov     rdx, r14; dwBytes
0x18000397b  mov     qword ptr [r15], 0
0x180003982  mov     ecx, 8; dwFlags
0x180003987  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000398c  mov     rsi, rax
0x18000398f  test    rax, rax
0x180003992  jnz     short loc_1800039B3
0x180003994  mov     rcx, [rbp+188h]; this
0x18000399b  mov     r14d, 8007000Eh
0x1800039a1  mov     r9d, r14d; char *
0x1800039a4  mov     edx, 14Bh; void *
0x1800039a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039ae  jmp     loc_180003A3F
0x1800039b3  xorps   xmm0, xmm0
0x1800039b6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800039bc  test    sil, 3
0x1800039c0  jnz     loc_180003B56
0x1800039c6  mov     r9, rsi
0x1800039c9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800039ce  shr     r9, 2; unsigned __int64
0x1800039d2  lea     rcx, [rsp+280h+hObject]; this
0x1800039d7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800039dc  mov     r14d, eax
0x1800039df  test    eax, eax
0x1800039e1  jns     loc_180003A7F
0x1800039e7  mov     rcx, [rbp+188h]; this
0x1800039ee  mov     r9d, eax; char *
0x1800039f1  mov     edx, 14Eh; void *
0x1800039f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039fb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003a00  test    rcx, rcx
0x180003a03  jz      short loc_180003A13
0x180003a05  call    cs:__imp_CloseHandle
0x180003a0b  test    eax, eax
0x180003a0d  jz      loc_180003B5C
0x180003a13  mov     rcx, [rsp+280h+hObject]; hObject
0x180003a18  test    rcx, rcx
0x180003a1b  jz      short loc_180003A2B
0x180003a1d  call    cs:__imp_CloseHandle
0x180003a23  test    eax, eax
0x180003a25  jz      loc_180003B6E
0x180003a2b  call    cs:__imp_GetProcessHeap
0x180003a31  mov     r8, rsi; lpMem
0x180003a34  xor     edx, edx; dwFlags
0x180003a36  mov     rcx, rax; hHeap
0x180003a39  call    cs:__imp_HeapFree
0x180003a3f  mov     rcx, [rbp+188h]; this
0x180003a46  mov     r9d, r14d; char *
0x180003a49  mov     edx, 137h; void *
0x180003a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a53  test    rdi, rdi
0x180003a56  jz      short loc_180003A69
0x180003a58  mov     rcx, rdi; hMutex
0x180003a5b  call    cs:__imp_ReleaseMutex
0x180003a61  test    eax, eax
0x180003a63  jz      loc_180003B80
0x180003a69  mov     rcx, rbx; hObject
0x180003a6c  call    cs:__imp_CloseHandle
0x180003a72  test    eax, eax
0x180003a74  jz      loc_180003B92
0x180003a7a  mov     eax, r14d
0x180003a7d  jmp     short loc_180003AED
0x180003a7f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003a84  xor     edx, edx; Val
0x180003a86  mov     dword ptr [rsi], 1
0x180003a8c  lea     rcx, [rsi+22h]; void *
0x180003a90  mov     [rsi+8], rbx
0x180003a94  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003a99  lea     r8d, [rdx+56h]; Size
0x180003a9d  call    memset_0
0x180003aa2  xor     edx, edx; Val
0x180003aa4  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003aaa  lea     rcx, [rsi+28h]; void *
0x180003aae  mov     dword ptr [rsi+24h], 1
0x180003ab5  lea     r8d, [rdx+50h]; Size
0x180003ab9  call    memset_0
0x180003abe  xor     ebx, ebx
0x180003ac0  mov     [r15], rsi
0x180003ac3  test    rdi, rdi
0x180003ac6  jz      short loc_180003AD9
0x180003ac8  mov     rcx, rdi; hMutex
0x180003acb  call    cs:__imp_ReleaseMutex
0x180003ad1  test    eax, eax
0x180003ad3  jz      loc_180003BA4
0x180003ad9  test    rbx, rbx
0x180003adc  jz      short loc_180003AEB
0x180003ade  mov     rcx, rbx; hObject
0x180003ae1  call    cs:__imp_CloseHandle
0x180003ae7  test    eax, eax
0x180003ae9  jz      short loc_180003B13
0x180003aeb  xor     eax, eax
0x180003aed  mov     rcx, [rbp+180h+var_30]
0x180003af4  xor     rcx, rsp; StackCookie
0x180003af7  call    __security_check_cookie
0x180003afc  mov     rbx, [rsp+280h+arg_10]
0x180003b04  add     rsp, 260h
0x180003b0b  pop     r15
0x180003b0d  pop     r14
0x180003b0f  pop     rdi
0x180003b10  pop     rsi
0x180003b11  pop     rbp
0x180003b12  retn
0x180003b13  mov     rcx, [rbp+188h]; this
0x180003b1a  mov     edx, 0A0Bh; void *
0x180003b1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b25  mov     rcx, [rbp+188h]; this
0x180003b2c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003b32  mov     rcx, [rbp+188h]; this
0x180003b39  mov     edx, 0A15h; void *
0x180003b3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b44  mov     rcx, [rbp+188h]; this
0x180003b4b  mov     edx, 0A0Bh; void *
0x180003b50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b56  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b5c  mov     rcx, [rbp+188h]; this
0x180003b63  mov     edx, 0A0Bh; void *
0x180003b68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b6e  mov     rcx, [rbp+188h]; this
0x180003b75  mov     edx, 0A0Bh; void *
0x180003b7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b80  mov     rcx, [rbp+188h]; this
0x180003b87  mov     edx, 0A15h; void *
0x180003b8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b92  mov     rcx, [rbp+188h]; this
0x180003b99  mov     edx, 0A0Bh; void *
0x180003b9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ba4  mov     rcx, [rbp+188h]; this
0x180003bab  mov     edx, 0A15h; void *
0x180003bb0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
