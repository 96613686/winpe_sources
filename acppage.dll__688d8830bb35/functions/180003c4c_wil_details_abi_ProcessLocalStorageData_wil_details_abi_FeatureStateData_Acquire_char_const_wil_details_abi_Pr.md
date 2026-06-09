# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003c4c`
- end: `0x180004013`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004430`

## callees

- `0x180002f20`
- `0x180003c4c`
- `0x180004044`
- `0x180004684`
- `0x180005024`
- `0x180005d58`
- `0x180007274`
- `0x1800079e0`
- `0x1800082c4`
- `0x1800082d4`
- `0x18000893c`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003e6a`
- `KERNEL32!HeapFree` at `0x180003e6a`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180003ef5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180003ef5`
- `KERNEL32!ReleaseMutex` at `0x180003d65`
- `KERNEL32!ReleaseMutex` at `0x180003e8c`
- `KERNEL32!ReleaseMutex` at `0x180003f28`
- `KERNEL32!ReleaseMutex` at `0x180003d65`
- `KERNEL32!ReleaseMutex` at `0x180003e8c`
- `KERNEL32!ReleaseMutex` at `0x180003f28`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003ce4`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003ce4`
- `KERNEL32!CloseHandle` at `0x180003d76`
- `KERNEL32!CloseHandle` at `0x180003e36`
- `KERNEL32!CloseHandle` at `0x180003e4e`
- `KERNEL32!CloseHandle` at `0x180003e9d`
- `KERNEL32!CloseHandle` at `0x180003f3e`
- `KERNEL32!CloseHandle` at `0x180003d76`
- `KERNEL32!CloseHandle` at `0x180003e36`
- `KERNEL32!CloseHandle` at `0x180003e4e`
- `KERNEL32!CloseHandle` at `0x180003e9d`
- `KERNEL32!CloseHandle` at `0x180003f3e`
- `KERNEL32!CreateMutexExW` at `0x180003cc3`
- `KERNEL32!CreateMutexExW` at `0x180003cc3`
- `KERNEL32!GetCurrentProcessId` at `0x180003c85`
- `KERNEL32!GetCurrentProcessId` at `0x180003c85`
- `KERNEL32!GetProcessHeap` at `0x180003e5c`
- `KERNEL32!GetProcessHeap` at `0x180003e5c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          pszDest,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180003c4c  mov     [rsp-8+arg_10], rbx
0x180003c51  push    rbp
0x180003c52  push    rsi
0x180003c53  push    rdi
0x180003c54  push    r14
0x180003c56  push    r15
0x180003c58  lea     rbp, [rsp-160h]
0x180003c60  sub     rsp, 260h
0x180003c67  mov     rax, cs:__security_cookie
0x180003c6e  xor     rax, rsp
0x180003c71  mov     [rbp+180h+var_30], rax
0x180003c78  mov     r15, rdx
0x180003c7b  mov     qword ptr [rdx], 0
0x180003c82  mov     rbx, rcx
0x180003c85  call    cs:__imp_GetCurrentProcessId
0x180003c8b  mov     r14d, 130h
0x180003c91  mov     [rsp+280h+var_258], rbx
0x180003c96  mov     r9d, eax
0x180003c99  mov     [rsp+280h+var_260], r14d; int
0x180003c9e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ca5  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180003caa  lea     edx, [r14-2Ch]; cchDest
0x180003cae  call    StringCchPrintfW
0x180003cb3  mov     r9d, 1F0001h; dwDesiredAccess
0x180003cb9  lea     rdx, [rsp+280h+pszDest]; lpName
0x180003cbe  xor     r8d, r8d; dwFlags
0x180003cc1  xor     ecx, ecx; lpMutexAttributes
0x180003cc3  call    cs:__imp_CreateMutexExW
0x180003cc9  mov     rbx, rax
0x180003ccc  test    rax, rax
0x180003ccf  jnz     short loc_180003CDB
0x180003cd1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003cd6  jmp     loc_180003F4A
0x180003cdb  xor     r8d, r8d; bAlertable
0x180003cde  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003ce1  mov     rcx, rbx; hHandle
0x180003ce4  call    cs:__imp_WaitForSingleObjectEx
0x180003cea  cmp     eax, 102h
0x180003cef  jz      short loc_180003D01
0x180003cf1  test    eax, 0FFFFFF7Fh
0x180003cf6  jnz     loc_180003F94
0x180003cfc  mov     rdi, rbx
0x180003cff  jmp     short loc_180003D03
0x180003d01  xor     edi, edi
0x180003d03  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003d08  mov     [rsp+280h+hObject], 0
0x180003d11  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180003d16  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003d1b  mov     esi, eax
0x180003d1d  test    eax, eax
0x180003d1f  jns     short loc_180003D8B
0x180003d21  mov     rcx, [rbp+188h]; this
0x180003d28  mov     r9d, eax; char *
0x180003d2b  mov     edx, 66h ; 'f'; void *
0x180003d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d35  mov     rcx, [rbp+188h]; this
0x180003d3c  mov     r9d, esi; char *
0x180003d3f  mov     edx, 6Fh ; 'o'; void *
0x180003d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d49  mov     rcx, [rbp+188h]; this
0x180003d50  mov     r9d, esi; char *
0x180003d53  mov     edx, 12Eh; void *
0x180003d58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d5d  test    rdi, rdi
0x180003d60  jz      short loc_180003D73
0x180003d62  mov     rcx, rdi; hMutex
0x180003d65  call    cs:__imp_ReleaseMutex
0x180003d6b  test    eax, eax
0x180003d6d  jz      loc_180003FA1
0x180003d73  mov     rcx, rbx; hObject
0x180003d76  call    cs:__imp_CloseHandle
0x180003d7c  test    eax, eax
0x180003d7e  jz      loc_180003FB3
0x180003d84  mov     eax, esi
0x180003d86  jmp     loc_180003F4A
0x180003d8b  mov     rax, [rsp+280h+hObject]
0x180003d90  lea     rcx, ds:0[rax*4]
0x180003d98  test    rcx, rcx
0x180003d9b  jz      short loc_180003DAB
0x180003d9d  mov     [r15], rcx
0x180003da0  mov     eax, [rcx]
0x180003da2  inc     eax
0x180003da4  mov     [rcx], eax
0x180003da6  jmp     loc_180003F20
0x180003dab  mov     rdx, r14; dwBytes
0x180003dae  mov     qword ptr [r15], 0
0x180003db5  mov     ecx, 8; dwFlags
0x180003dba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003dbf  mov     r14, rax
0x180003dc2  test    rax, rax
0x180003dc5  jnz     short loc_180003DE5
0x180003dc7  mov     rcx, [rbp+188h]; this
0x180003dce  mov     esi, 8007000Eh
0x180003dd3  mov     r9d, esi; char *
0x180003dd6  mov     edx, 14Bh; void *
0x180003ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003de0  jmp     loc_180003E70
0x180003de5  xorps   xmm0, xmm0
0x180003de8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003dee  test    r14b, 3
0x180003df2  jnz     loc_180003FC5
0x180003df8  mov     r9, r14
0x180003dfb  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180003e00  shr     r9, 2; unsigned __int64
0x180003e04  lea     rcx, [rsp+280h+hObject]; this
0x180003e09  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003e0e  mov     esi, eax
0x180003e10  test    eax, eax
0x180003e12  jns     loc_180003EB0
0x180003e18  mov     rcx, [rbp+188h]; this
0x180003e1f  mov     r9d, eax; char *
0x180003e22  mov     edx, 14Eh; void *
0x180003e27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e2c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003e31  test    rcx, rcx
0x180003e34  jz      short loc_180003E44
0x180003e36  call    cs:__imp_CloseHandle
0x180003e3c  test    eax, eax
0x180003e3e  jz      loc_180003FCB
0x180003e44  mov     rcx, [rsp+280h+hObject]; hObject
0x180003e49  test    rcx, rcx
0x180003e4c  jz      short loc_180003E5C
0x180003e4e  call    cs:__imp_CloseHandle
0x180003e54  test    eax, eax
0x180003e56  jz      loc_180003FDD
0x180003e5c  call    cs:__imp_GetProcessHeap
0x180003e62  mov     r8, r14; lpMem
0x180003e65  xor     edx, edx; dwFlags
0x180003e67  mov     rcx, rax; hHeap
0x180003e6a  call    cs:__imp_HeapFree
0x180003e70  mov     rcx, [rbp+188h]; this
0x180003e77  mov     r9d, esi; char *
0x180003e7a  mov     edx, 137h; void *
0x180003e7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e84  test    rdi, rdi
0x180003e87  jz      short loc_180003E9A
0x180003e89  mov     rcx, rdi; hMutex
0x180003e8c  call    cs:__imp_ReleaseMutex
0x180003e92  test    eax, eax
0x180003e94  jz      loc_180003FEF
0x180003e9a  mov     rcx, rbx; hObject
0x180003e9d  call    cs:__imp_CloseHandle
0x180003ea3  test    eax, eax
0x180003ea5  jz      loc_180003F82
0x180003eab  jmp     loc_180003D84
0x180003eb0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003eb5  lea     rcx, [r14+28h]; void *
0x180003eb9  mov     dword ptr [r14], 1
0x180003ec0  xor     edx, edx; Val
0x180003ec2  mov     [r14+8], rbx
0x180003ec6  mov     r8d, 108h; Size
0x180003ecc  movdqu  xmmword ptr [r14+10h], xmm0
0x180003ed2  call    memset_0
0x180003ed7  xor     eax, eax
0x180003ed9  lea     rcx, [r14+28h]; this
0x180003edd  mov     [r14+20h], rax
0x180003ee1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ee6  lea     rbx, [r14+0E8h]
0x180003eed  xor     r8d, r8d; Flags
0x180003ef0  mov     rcx, rbx; lpCriticalSection
0x180003ef3  xor     edx, edx; dwSpinCount
0x180003ef5  call    cs:__imp_InitializeCriticalSectionEx
0x180003efb  mov     qword ptr [rbx+28h], 0
0x180003f03  mov     qword ptr [rbx+30h], 0
0x180003f0b  mov     qword ptr [rbx+38h], 0
0x180003f13  mov     qword ptr [rbx+40h], 0
0x180003f1b  xor     ebx, ebx
0x180003f1d  mov     [r15], r14
0x180003f20  test    rdi, rdi
0x180003f23  jz      short loc_180003F36
0x180003f25  mov     rcx, rdi; hMutex
0x180003f28  call    cs:__imp_ReleaseMutex
0x180003f2e  test    eax, eax
0x180003f30  jz      loc_180004001
0x180003f36  test    rbx, rbx
0x180003f39  jz      short loc_180003F48
0x180003f3b  mov     rcx, rbx; hObject
0x180003f3e  call    cs:__imp_CloseHandle
0x180003f44  test    eax, eax
0x180003f46  jz      short loc_180003F70
0x180003f48  xor     eax, eax
0x180003f4a  mov     rcx, [rbp+180h+var_30]
0x180003f51  xor     rcx, rsp; StackCookie
0x180003f54  call    __security_check_cookie
0x180003f59  mov     rbx, [rsp+280h+arg_10]
0x180003f61  add     rsp, 260h
0x180003f68  pop     r15
0x180003f6a  pop     r14
0x180003f6c  pop     rdi
0x180003f6d  pop     rsi
0x180003f6e  pop     rbp
0x180003f6f  retn
0x180003f70  mov     rcx, [rbp+188h]; this
0x180003f77  mov     edx, 0A0Bh; void *
0x180003f7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f82  mov     rcx, [rbp+188h]; this
0x180003f89  mov     edx, 0A0Bh; void *
0x180003f8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f94  mov     rcx, [rbp+188h]; this
0x180003f9b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003fa1  mov     rcx, [rbp+188h]; this
0x180003fa8  mov     edx, 0A15h; void *
0x180003fad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fb3  mov     rcx, [rbp+188h]; this
0x180003fba  mov     edx, 0A0Bh; void *
0x180003fbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fc5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003fcb  mov     rcx, [rbp+188h]; this
0x180003fd2  mov     edx, 0A0Bh; void *
0x180003fd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fdd  mov     rcx, [rbp+188h]; this
0x180003fe4  mov     edx, 0A0Bh; void *
0x180003fe9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fef  mov     rcx, [rbp+188h]; this
0x180003ff6  mov     edx, 0A15h; void *
0x180003ffb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004001  mov     rcx, [rbp+188h]; this
0x180004008  mov     edx, 0A15h; void *
0x18000400d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
