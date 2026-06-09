# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003bc4`
- end: `0x180003f8c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000545c`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180003bc4`
- `0x18000438c`
- `0x1800048c8`
- `0x1800051f8`
- `0x180005ea8`
- `0x180007434`
- `0x180007970`
- `0x180007e20`
- `0x1800086ec`
- `0x1800086fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c3c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c5d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb7`

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
0x180003bc4  mov     [rsp-8+arg_10], rbx
0x180003bc9  push    rbp
0x180003bca  push    rsi
0x180003bcb  push    rdi
0x180003bcc  push    r14
0x180003bce  push    r15
0x180003bd0  lea     rbp, [rsp-160h]
0x180003bd8  sub     rsp, 260h
0x180003bdf  mov     rax, cs:__security_cookie
0x180003be6  xor     rax, rsp
0x180003be9  mov     [rbp+180h+var_30], rax
0x180003bf0  mov     r15, rdx
0x180003bf3  mov     qword ptr [rdx], 0
0x180003bfa  mov     rbx, rcx
0x180003bfd  call    cs:__imp_GetCurrentProcessId
0x180003c03  mov     r14d, 78h ; 'x'
0x180003c09  mov     [rsp+280h+var_258], rbx
0x180003c0e  mov     r9d, eax
0x180003c11  mov     [rsp+280h+var_260], r14d; int
0x180003c16  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c1d  mov     edx, 104h; unsigned __int64
0x180003c22  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c2c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c32  lea     rdx, [rsp+280h+Name]; lpName
0x180003c37  xor     r8d, r8d; dwFlags
0x180003c3a  xor     ecx, ecx; lpMutexAttributes
0x180003c3c  call    cs:__imp_CreateMutexExW
0x180003c42  mov     rbx, rax
0x180003c45  test    rax, rax
0x180003c48  jnz     short loc_180003C54
0x180003c4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c4f  jmp     loc_180003EC3
0x180003c54  xor     r8d, r8d; bAlertable
0x180003c57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c5a  mov     rcx, rbx; hHandle
0x180003c5d  call    cs:__imp_WaitForSingleObjectEx
0x180003c63  cmp     eax, 102h
0x180003c68  jz      short loc_180003C7A
0x180003c6a  test    eax, 0FFFFFF7Fh
0x180003c6f  jnz     loc_180003EFB
0x180003c75  mov     rdi, rbx
0x180003c78  jmp     short loc_180003C7C
0x180003c7a  xor     edi, edi
0x180003c7c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003c81  mov     [rsp+280h+hObject], 0
0x180003c8a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c8f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c94  mov     esi, eax
0x180003c96  test    eax, eax
0x180003c98  jns     short loc_180003D19
0x180003c9a  mov     rcx, [rbp+188h]; this
0x180003ca1  lea     r8, aWil; "wil"
0x180003ca8  mov     r9d, eax; char *
0x180003cab  mov     edx, 66h ; 'f'; void *
0x180003cb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cb5  mov     rcx, [rbp+188h]; this
0x180003cbc  lea     r8, aWil; "wil"
0x180003cc3  mov     r9d, esi; char *
0x180003cc6  mov     edx, 6Fh ; 'o'; void *
0x180003ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cd0  mov     rcx, [rbp+188h]; this
0x180003cd7  lea     r8, aWil; "wil"
0x180003cde  mov     r9d, esi; char *
0x180003ce1  mov     edx, 12Eh; void *
0x180003ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ceb  test    rdi, rdi
0x180003cee  jz      short loc_180003D01
0x180003cf0  mov     rcx, rdi; hMutex
0x180003cf3  call    cs:__imp_ReleaseMutex
0x180003cf9  test    eax, eax
0x180003cfb  jz      loc_180003F08
0x180003d01  mov     rcx, rbx; hObject
0x180003d04  call    cs:__imp_CloseHandle
0x180003d0a  test    eax, eax
0x180003d0c  jz      loc_180003F1A
0x180003d12  mov     eax, esi
0x180003d14  jmp     loc_180003EC3
0x180003d19  mov     rax, [rsp+280h+hObject]
0x180003d1e  lea     rcx, ds:0[rax*4]
0x180003d26  test    rcx, rcx
0x180003d29  jz      short loc_180003D39
0x180003d2b  mov     [r15], rcx
0x180003d2e  mov     eax, [rcx]
0x180003d30  inc     eax
0x180003d32  mov     [rcx], eax
0x180003d34  jmp     loc_180003E99
0x180003d39  mov     rdx, r14; dwBytes
0x180003d3c  mov     qword ptr [r15], 0
0x180003d43  mov     ecx, 8; dwFlags
0x180003d48  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d4d  mov     rsi, rax
0x180003d50  test    rax, rax
0x180003d53  jnz     short loc_180003D7B
0x180003d55  mov     rcx, [rbp+188h]; this
0x180003d5c  lea     r8, aWil; "wil"
0x180003d63  mov     r14d, 8007000Eh
0x180003d69  mov     edx, 14Bh; void *
0x180003d6e  mov     r9d, r14d; char *
0x180003d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d76  jmp     loc_180003E0E
0x180003d7b  xorps   xmm0, xmm0
0x180003d7e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003d84  test    sil, 3
0x180003d88  jnz     loc_180003F2C
0x180003d8e  mov     r9, rsi
0x180003d91  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d96  shr     r9, 2; unsigned __int64
0x180003d9a  lea     rcx, [rsp+280h+hObject]; this
0x180003d9f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003da4  mov     r14d, eax
0x180003da7  test    eax, eax
0x180003da9  jns     loc_180003E55
0x180003daf  mov     rcx, [rbp+188h]; this
0x180003db6  lea     r8, aWil; "wil"
0x180003dbd  mov     r9d, eax; char *
0x180003dc0  mov     edx, 14Eh; void *
0x180003dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dca  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003dcf  test    rcx, rcx
0x180003dd2  jz      short loc_180003DE2
0x180003dd4  call    cs:__imp_CloseHandle
0x180003dda  test    eax, eax
0x180003ddc  jz      loc_180003F32
0x180003de2  mov     rcx, [rsp+280h+hObject]; hObject
0x180003de7  test    rcx, rcx
0x180003dea  jz      short loc_180003DFA
0x180003dec  call    cs:__imp_CloseHandle
0x180003df2  test    eax, eax
0x180003df4  jz      loc_180003F44
0x180003dfa  call    cs:__imp_GetProcessHeap
0x180003e00  mov     r8, rsi; lpMem
0x180003e03  xor     edx, edx; dwFlags
0x180003e05  mov     rcx, rax; hHeap
0x180003e08  call    cs:__imp_HeapFree
0x180003e0e  mov     rcx, [rbp+188h]; this
0x180003e15  lea     r8, aWil; "wil"
0x180003e1c  mov     r9d, r14d; char *
0x180003e1f  mov     edx, 137h; void *
0x180003e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e29  test    rdi, rdi
0x180003e2c  jz      short loc_180003E3F
0x180003e2e  mov     rcx, rdi; hMutex
0x180003e31  call    cs:__imp_ReleaseMutex
0x180003e37  test    eax, eax
0x180003e39  jz      loc_180003F56
0x180003e3f  mov     rcx, rbx; hObject
0x180003e42  call    cs:__imp_CloseHandle
0x180003e48  test    eax, eax
0x180003e4a  jz      loc_180003F68
0x180003e50  mov     eax, r14d
0x180003e53  jmp     short loc_180003EC3
0x180003e55  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e5a  xor     edx, edx; Val
0x180003e5c  mov     dword ptr [rsi], 1
0x180003e62  lea     rcx, [rsi+22h]; void *
0x180003e66  mov     [rsi+8], rbx
0x180003e6a  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003e6f  lea     r8d, [rdx+56h]; Size
0x180003e73  call    memset_0
0x180003e78  xor     edx, edx; Val
0x180003e7a  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003e80  lea     rcx, [rsi+28h]; void *
0x180003e84  mov     dword ptr [rsi+24h], 1
0x180003e8b  lea     r8d, [rdx+50h]; Size
0x180003e8f  call    memset_0
0x180003e94  xor     ebx, ebx
0x180003e96  mov     [r15], rsi
0x180003e99  test    rdi, rdi
0x180003e9c  jz      short loc_180003EAF
0x180003e9e  mov     rcx, rdi; hMutex
0x180003ea1  call    cs:__imp_ReleaseMutex
0x180003ea7  test    eax, eax
0x180003ea9  jz      loc_180003F7A
0x180003eaf  test    rbx, rbx
0x180003eb2  jz      short loc_180003EC1
0x180003eb4  mov     rcx, rbx; hObject
0x180003eb7  call    cs:__imp_CloseHandle
0x180003ebd  test    eax, eax
0x180003ebf  jz      short loc_180003EE9
0x180003ec1  xor     eax, eax
0x180003ec3  mov     rcx, [rbp+180h+var_30]
0x180003eca  xor     rcx, rsp; StackCookie
0x180003ecd  call    __security_check_cookie
0x180003ed2  mov     rbx, [rsp+280h+arg_10]
0x180003eda  add     rsp, 260h
0x180003ee1  pop     r15
0x180003ee3  pop     r14
0x180003ee5  pop     rdi
0x180003ee6  pop     rsi
0x180003ee7  pop     rbp
0x180003ee8  retn
0x180003ee9  mov     rcx, [rbp+188h]; this
0x180003ef0  mov     edx, 0A0Bh; void *
0x180003ef5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003efb  mov     rcx, [rbp+188h]; this
0x180003f02  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f08  mov     rcx, [rbp+188h]; this
0x180003f0f  mov     edx, 0A15h; void *
0x180003f14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f1a  mov     rcx, [rbp+188h]; this
0x180003f21  mov     edx, 0A0Bh; void *
0x180003f26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f2c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f32  mov     rcx, [rbp+188h]; this
0x180003f39  mov     edx, 0A0Bh; void *
0x180003f3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f44  mov     rcx, [rbp+188h]; this
0x180003f4b  mov     edx, 0A0Bh; void *
0x180003f50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f56  mov     rcx, [rbp+188h]; this
0x180003f5d  mov     edx, 0A15h; void *
0x180003f62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f68  mov     rcx, [rbp+188h]; this
0x180003f6f  mov     edx, 0A0Bh; void *
0x180003f74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f7a  mov     rcx, [rbp+188h]; this
0x180003f81  mov     edx, 0A15h; void *
0x180003f86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
