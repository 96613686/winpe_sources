# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003bf8`
- end: `0x180003f96`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005350`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x180003bf8`
- `0x18000436c`
- `0x1800047c4`
- `0x1800050e8`
- `0x180005cd8`
- `0x180007004`
- `0x180007af8`
- `0x180007e4c`
- `0x18000862c`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003eab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec1`

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
0x180003bf8  mov     [rsp-8+arg_10], rbx
0x180003bfd  push    rbp
0x180003bfe  push    rsi
0x180003bff  push    rdi
0x180003c00  push    r14
0x180003c02  push    r15
0x180003c04  lea     rbp, [rsp-160h]
0x180003c0c  sub     rsp, 260h
0x180003c13  mov     rax, cs:__security_cookie
0x180003c1a  xor     rax, rsp
0x180003c1d  mov     [rbp+180h+var_30], rax
0x180003c24  mov     r15, rdx
0x180003c27  mov     qword ptr [rdx], 0
0x180003c2e  mov     rbx, rcx
0x180003c31  call    cs:__imp_GetCurrentProcessId
0x180003c37  mov     r14d, 78h ; 'x'
0x180003c3d  mov     [rsp+280h+var_258], rbx
0x180003c42  mov     r9d, eax
0x180003c45  mov     [rsp+280h+var_260], r14d; int
0x180003c4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c51  mov     edx, 104h; unsigned __int64
0x180003c56  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c60  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c66  lea     rdx, [rsp+280h+Name]; lpName
0x180003c6b  xor     r8d, r8d; dwFlags
0x180003c6e  xor     ecx, ecx; lpMutexAttributes
0x180003c70  call    cs:__imp_CreateMutexExW
0x180003c76  mov     rbx, rax
0x180003c79  test    rax, rax
0x180003c7c  jnz     short loc_180003C88
0x180003c7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c83  jmp     loc_180003ECD
0x180003c88  xor     r8d, r8d; bAlertable
0x180003c8b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c8e  mov     rcx, rbx; hHandle
0x180003c91  call    cs:__imp_WaitForSingleObjectEx
0x180003c97  cmp     eax, 102h
0x180003c9c  jz      short loc_180003CAE
0x180003c9e  test    eax, 0FFFFFF7Fh
0x180003ca3  jnz     loc_180003F05
0x180003ca9  mov     rdi, rbx
0x180003cac  jmp     short loc_180003CB0
0x180003cae  xor     edi, edi
0x180003cb0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003cb5  mov     [rsp+280h+hObject], 0
0x180003cbe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003cc3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003cc8  mov     esi, eax
0x180003cca  test    eax, eax
0x180003ccc  jns     short loc_180003D38
0x180003cce  mov     rcx, [rbp+188h]; this
0x180003cd5  mov     r9d, eax; char *
0x180003cd8  mov     edx, 66h ; 'f'; void *
0x180003cdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ce2  mov     rcx, [rbp+188h]; this
0x180003ce9  mov     r9d, esi; char *
0x180003cec  mov     edx, 6Fh ; 'o'; void *
0x180003cf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cf6  mov     rcx, [rbp+188h]; this
0x180003cfd  mov     r9d, esi; char *
0x180003d00  mov     edx, 12Eh; void *
0x180003d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d0a  test    rdi, rdi
0x180003d0d  jz      short loc_180003D20
0x180003d0f  mov     rcx, rdi; hMutex
0x180003d12  call    cs:__imp_ReleaseMutex
0x180003d18  test    eax, eax
0x180003d1a  jz      loc_180003F12
0x180003d20  mov     rcx, rbx; hObject
0x180003d23  call    cs:__imp_CloseHandle
0x180003d29  test    eax, eax
0x180003d2b  jz      loc_180003F24
0x180003d31  mov     eax, esi
0x180003d33  jmp     loc_180003ECD
0x180003d38  mov     rax, [rsp+280h+hObject]
0x180003d3d  lea     rcx, ds:0[rax*4]
0x180003d45  test    rcx, rcx
0x180003d48  jz      short loc_180003D58
0x180003d4a  mov     [r15], rcx
0x180003d4d  mov     eax, [rcx]
0x180003d4f  inc     eax
0x180003d51  mov     [rcx], eax
0x180003d53  jmp     loc_180003EA3
0x180003d58  mov     rdx, r14; dwBytes
0x180003d5b  mov     qword ptr [r15], 0
0x180003d62  mov     ecx, 8; dwFlags
0x180003d67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d6c  mov     rsi, rax
0x180003d6f  test    rax, rax
0x180003d72  jnz     short loc_180003D93
0x180003d74  mov     rcx, [rbp+188h]; this
0x180003d7b  mov     r14d, 8007000Eh
0x180003d81  mov     r9d, r14d; char *
0x180003d84  mov     edx, 14Bh; void *
0x180003d89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d8e  jmp     loc_180003E1F
0x180003d93  xorps   xmm0, xmm0
0x180003d96  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003d9c  test    sil, 3
0x180003da0  jnz     loc_180003F36
0x180003da6  mov     r9, rsi
0x180003da9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003dae  shr     r9, 2; unsigned __int64
0x180003db2  lea     rcx, [rsp+280h+hObject]; this
0x180003db7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003dbc  mov     r14d, eax
0x180003dbf  test    eax, eax
0x180003dc1  jns     loc_180003E5F
0x180003dc7  mov     rcx, [rbp+188h]; this
0x180003dce  mov     r9d, eax; char *
0x180003dd1  mov     edx, 14Eh; void *
0x180003dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ddb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003de0  test    rcx, rcx
0x180003de3  jz      short loc_180003DF3
0x180003de5  call    cs:__imp_CloseHandle
0x180003deb  test    eax, eax
0x180003ded  jz      loc_180003F3C
0x180003df3  mov     rcx, [rsp+280h+hObject]; hObject
0x180003df8  test    rcx, rcx
0x180003dfb  jz      short loc_180003E0B
0x180003dfd  call    cs:__imp_CloseHandle
0x180003e03  test    eax, eax
0x180003e05  jz      loc_180003F4E
0x180003e0b  call    cs:__imp_GetProcessHeap
0x180003e11  mov     r8, rsi; lpMem
0x180003e14  xor     edx, edx; dwFlags
0x180003e16  mov     rcx, rax; hHeap
0x180003e19  call    cs:__imp_HeapFree
0x180003e1f  mov     rcx, [rbp+188h]; this
0x180003e26  mov     r9d, r14d; char *
0x180003e29  mov     edx, 137h; void *
0x180003e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e33  test    rdi, rdi
0x180003e36  jz      short loc_180003E49
0x180003e38  mov     rcx, rdi; hMutex
0x180003e3b  call    cs:__imp_ReleaseMutex
0x180003e41  test    eax, eax
0x180003e43  jz      loc_180003F60
0x180003e49  mov     rcx, rbx; hObject
0x180003e4c  call    cs:__imp_CloseHandle
0x180003e52  test    eax, eax
0x180003e54  jz      loc_180003F72
0x180003e5a  mov     eax, r14d
0x180003e5d  jmp     short loc_180003ECD
0x180003e5f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e64  xor     edx, edx; Val
0x180003e66  mov     dword ptr [rsi], 1
0x180003e6c  lea     rcx, [rsi+22h]; void *
0x180003e70  mov     [rsi+8], rbx
0x180003e74  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003e79  lea     r8d, [rdx+56h]; Size
0x180003e7d  call    memset_0
0x180003e82  xor     edx, edx; Val
0x180003e84  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003e8a  lea     rcx, [rsi+28h]; void *
0x180003e8e  mov     dword ptr [rsi+24h], 1
0x180003e95  lea     r8d, [rdx+50h]; Size
0x180003e99  call    memset_0
0x180003e9e  xor     ebx, ebx
0x180003ea0  mov     [r15], rsi
0x180003ea3  test    rdi, rdi
0x180003ea6  jz      short loc_180003EB9
0x180003ea8  mov     rcx, rdi; hMutex
0x180003eab  call    cs:__imp_ReleaseMutex
0x180003eb1  test    eax, eax
0x180003eb3  jz      loc_180003F84
0x180003eb9  test    rbx, rbx
0x180003ebc  jz      short loc_180003ECB
0x180003ebe  mov     rcx, rbx; hObject
0x180003ec1  call    cs:__imp_CloseHandle
0x180003ec7  test    eax, eax
0x180003ec9  jz      short loc_180003EF3
0x180003ecb  xor     eax, eax
0x180003ecd  mov     rcx, [rbp+180h+var_30]
0x180003ed4  xor     rcx, rsp; StackCookie
0x180003ed7  call    __security_check_cookie
0x180003edc  mov     rbx, [rsp+280h+arg_10]
0x180003ee4  add     rsp, 260h
0x180003eeb  pop     r15
0x180003eed  pop     r14
0x180003eef  pop     rdi
0x180003ef0  pop     rsi
0x180003ef1  pop     rbp
0x180003ef2  retn
0x180003ef3  mov     rcx, [rbp+188h]; this
0x180003efa  mov     edx, 0A0Bh; void *
0x180003eff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f05  mov     rcx, [rbp+188h]; this
0x180003f0c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f12  mov     rcx, [rbp+188h]; this
0x180003f19  mov     edx, 0A15h; void *
0x180003f1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f24  mov     rcx, [rbp+188h]; this
0x180003f2b  mov     edx, 0A0Bh; void *
0x180003f30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f3c  mov     rcx, [rbp+188h]; this
0x180003f43  mov     edx, 0A0Bh; void *
0x180003f48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f4e  mov     rcx, [rbp+188h]; this
0x180003f55  mov     edx, 0A0Bh; void *
0x180003f5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f60  mov     rcx, [rbp+188h]; this
0x180003f67  mov     edx, 0A15h; void *
0x180003f6c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f72  mov     rcx, [rbp+188h]; this
0x180003f79  mov     edx, 0A0Bh; void *
0x180003f7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f84  mov     rcx, [rbp+188h]; this
0x180003f8b  mov     edx, 0A15h; void *
0x180003f90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
