# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140068b4c`
- end: `0x140068f13`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140069374`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140067f20`
- `0x140068b4c`
- `0x140069088`
- `0x140069504`
- `0x140069d68`
- `0x14006ac38`
- `0x14006bf04`
- `0x14006cb6c`
- `0x14006d33c`
- `0x14006d34c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140068bc3`
- `KERNEL32!CreateMutexExW` at `0x140068bc3`
- `KERNEL32!WaitForSingleObjectEx` at `0x140068be4`
- `KERNEL32!WaitForSingleObjectEx` at `0x140068be4`
- `KERNEL32!ReleaseMutex` at `0x140068c65`
- `KERNEL32!ReleaseMutex` at `0x140068d8c`
- `KERNEL32!ReleaseMutex` at `0x140068e28`
- `KERNEL32!ReleaseMutex` at `0x140068c65`
- `KERNEL32!ReleaseMutex` at `0x140068d8c`
- `KERNEL32!ReleaseMutex` at `0x140068e28`
- `KERNEL32!GetCurrentProcessId` at `0x140068b85`
- `KERNEL32!GetCurrentProcessId` at `0x140068b85`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140068df5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140068df5`
- `KERNEL32!GetProcessHeap` at `0x140068d5c`
- `KERNEL32!GetProcessHeap` at `0x140068d5c`
- `KERNEL32!CloseHandle` at `0x140068c76`
- `KERNEL32!CloseHandle` at `0x140068d36`
- `KERNEL32!CloseHandle` at `0x140068d4e`
- `KERNEL32!CloseHandle` at `0x140068d9d`
- `KERNEL32!CloseHandle` at `0x140068e3e`
- `KERNEL32!CloseHandle` at `0x140068c76`
- `KERNEL32!CloseHandle` at `0x140068d36`
- `KERNEL32!CloseHandle` at `0x140068d4e`
- `KERNEL32!CloseHandle` at `0x140068d9d`
- `KERNEL32!CloseHandle` at `0x140068e3e`
- `KERNEL32!HeapFree` at `0x140068d6a`
- `KERNEL32!HeapFree` at `0x140068d6a`

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
  unsigned int v25; // r8d
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
          Name,
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
0x140068b4c  mov     [rsp-8+arg_10], rbx
0x140068b51  push    rbp
0x140068b52  push    rsi
0x140068b53  push    rdi
0x140068b54  push    r14
0x140068b56  push    r15
0x140068b58  lea     rbp, [rsp-160h]
0x140068b60  sub     rsp, 260h
0x140068b67  mov     rax, cs:__security_cookie
0x140068b6e  xor     rax, rsp
0x140068b71  mov     [rbp+180h+var_30], rax
0x140068b78  mov     r15, rdx
0x140068b7b  mov     qword ptr [rdx], 0
0x140068b82  mov     rbx, rcx
0x140068b85  call    cs:__imp_GetCurrentProcessId
0x140068b8b  mov     r14d, 130h
0x140068b91  mov     [rsp+280h+var_258], rbx
0x140068b96  mov     r9d, eax
0x140068b99  mov     [rsp+280h+var_260], r14d; int
0x140068b9e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140068ba5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140068baa  lea     edx, [r14-2Ch]; unsigned __int64
0x140068bae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140068bb3  mov     r9d, 1F0001h; dwDesiredAccess
0x140068bb9  lea     rdx, [rsp+280h+Name]; lpName
0x140068bbe  xor     r8d, r8d; dwFlags
0x140068bc1  xor     ecx, ecx; lpMutexAttributes
0x140068bc3  call    cs:__imp_CreateMutexExW
0x140068bc9  mov     rbx, rax
0x140068bcc  test    rax, rax
0x140068bcf  jnz     short loc_140068BDB
0x140068bd1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140068bd6  jmp     loc_140068E4A
0x140068bdb  xor     r8d, r8d; bAlertable
0x140068bde  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140068be1  mov     rcx, rbx; hHandle
0x140068be4  call    cs:__imp_WaitForSingleObjectEx
0x140068bea  cmp     eax, 102h
0x140068bef  jz      short loc_140068C01
0x140068bf1  test    eax, 0FFFFFF7Fh
0x140068bf6  jnz     loc_140068E94
0x140068bfc  mov     rdi, rbx
0x140068bff  jmp     short loc_140068C03
0x140068c01  xor     edi, edi
0x140068c03  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140068c08  mov     [rsp+280h+hObject], 0
0x140068c11  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140068c16  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140068c1b  mov     esi, eax
0x140068c1d  test    eax, eax
0x140068c1f  jns     short loc_140068C8B
0x140068c21  mov     rcx, [rbp+188h]; this
0x140068c28  mov     r9d, eax; char *
0x140068c2b  mov     edx, 66h ; 'f'; void *
0x140068c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068c35  mov     rcx, [rbp+188h]; this
0x140068c3c  mov     r9d, esi; char *
0x140068c3f  mov     edx, 6Fh ; 'o'; void *
0x140068c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068c49  mov     rcx, [rbp+188h]; this
0x140068c50  mov     r9d, esi; char *
0x140068c53  mov     edx, 12Eh; void *
0x140068c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068c5d  test    rdi, rdi
0x140068c60  jz      short loc_140068C73
0x140068c62  mov     rcx, rdi; hMutex
0x140068c65  call    cs:__imp_ReleaseMutex
0x140068c6b  test    eax, eax
0x140068c6d  jz      loc_140068EA1
0x140068c73  mov     rcx, rbx; hObject
0x140068c76  call    cs:__imp_CloseHandle
0x140068c7c  test    eax, eax
0x140068c7e  jz      loc_140068EB3
0x140068c84  mov     eax, esi
0x140068c86  jmp     loc_140068E4A
0x140068c8b  mov     rax, [rsp+280h+hObject]
0x140068c90  lea     rcx, ds:0[rax*4]
0x140068c98  test    rcx, rcx
0x140068c9b  jz      short loc_140068CAB
0x140068c9d  mov     [r15], rcx
0x140068ca0  mov     eax, [rcx]
0x140068ca2  inc     eax
0x140068ca4  mov     [rcx], eax
0x140068ca6  jmp     loc_140068E20
0x140068cab  mov     rdx, r14; dwBytes
0x140068cae  mov     qword ptr [r15], 0
0x140068cb5  mov     ecx, 8; dwFlags
0x140068cba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140068cbf  mov     r14, rax
0x140068cc2  test    rax, rax
0x140068cc5  jnz     short loc_140068CE5
0x140068cc7  mov     rcx, [rbp+188h]; this
0x140068cce  mov     esi, 8007000Eh
0x140068cd3  mov     r9d, esi; char *
0x140068cd6  mov     edx, 14Bh; void *
0x140068cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068ce0  jmp     loc_140068D70
0x140068ce5  xorps   xmm0, xmm0
0x140068ce8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140068cee  test    r14b, 3
0x140068cf2  jnz     loc_140068EC5
0x140068cf8  mov     r9, r14
0x140068cfb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140068d00  shr     r9, 2; unsigned __int64
0x140068d04  lea     rcx, [rsp+280h+hObject]; this
0x140068d09  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140068d0e  mov     esi, eax
0x140068d10  test    eax, eax
0x140068d12  jns     loc_140068DB0
0x140068d18  mov     rcx, [rbp+188h]; this
0x140068d1f  mov     r9d, eax; char *
0x140068d22  mov     edx, 14Eh; void *
0x140068d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068d2c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140068d31  test    rcx, rcx
0x140068d34  jz      short loc_140068D44
0x140068d36  call    cs:__imp_CloseHandle
0x140068d3c  test    eax, eax
0x140068d3e  jz      loc_140068ECB
0x140068d44  mov     rcx, [rsp+280h+hObject]; hObject
0x140068d49  test    rcx, rcx
0x140068d4c  jz      short loc_140068D5C
0x140068d4e  call    cs:__imp_CloseHandle
0x140068d54  test    eax, eax
0x140068d56  jz      loc_140068EDD
0x140068d5c  call    cs:__imp_GetProcessHeap
0x140068d62  mov     r8, r14; lpMem
0x140068d65  xor     edx, edx; dwFlags
0x140068d67  mov     rcx, rax; hHeap
0x140068d6a  call    cs:__imp_HeapFree
0x140068d70  mov     rcx, [rbp+188h]; this
0x140068d77  mov     r9d, esi; char *
0x140068d7a  mov     edx, 137h; void *
0x140068d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068d84  test    rdi, rdi
0x140068d87  jz      short loc_140068D9A
0x140068d89  mov     rcx, rdi; hMutex
0x140068d8c  call    cs:__imp_ReleaseMutex
0x140068d92  test    eax, eax
0x140068d94  jz      loc_140068EEF
0x140068d9a  mov     rcx, rbx; hObject
0x140068d9d  call    cs:__imp_CloseHandle
0x140068da3  test    eax, eax
0x140068da5  jz      loc_140068E82
0x140068dab  jmp     loc_140068C84
0x140068db0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140068db5  lea     rcx, [r14+28h]; void *
0x140068db9  mov     dword ptr [r14], 1
0x140068dc0  xor     edx, edx; Val
0x140068dc2  mov     [r14+8], rbx
0x140068dc6  mov     r8d, 108h; Size
0x140068dcc  movdqu  xmmword ptr [r14+10h], xmm0
0x140068dd2  call    memset_0
0x140068dd7  xor     eax, eax
0x140068dd9  lea     rcx, [r14+28h]; this
0x140068ddd  mov     [r14+20h], rax
0x140068de1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140068de6  lea     rbx, [r14+0E8h]
0x140068ded  xor     r8d, r8d; Flags
0x140068df0  mov     rcx, rbx; lpCriticalSection
0x140068df3  xor     edx, edx; dwSpinCount
0x140068df5  call    cs:__imp_InitializeCriticalSectionEx
0x140068dfb  mov     qword ptr [rbx+28h], 0
0x140068e03  mov     qword ptr [rbx+30h], 0
0x140068e0b  mov     qword ptr [rbx+38h], 0
0x140068e13  mov     qword ptr [rbx+40h], 0
0x140068e1b  xor     ebx, ebx
0x140068e1d  mov     [r15], r14
0x140068e20  test    rdi, rdi
0x140068e23  jz      short loc_140068E36
0x140068e25  mov     rcx, rdi; hMutex
0x140068e28  call    cs:__imp_ReleaseMutex
0x140068e2e  test    eax, eax
0x140068e30  jz      loc_140068F01
0x140068e36  test    rbx, rbx
0x140068e39  jz      short loc_140068E48
0x140068e3b  mov     rcx, rbx; hObject
0x140068e3e  call    cs:__imp_CloseHandle
0x140068e44  test    eax, eax
0x140068e46  jz      short loc_140068E70
0x140068e48  xor     eax, eax
0x140068e4a  mov     rcx, [rbp+180h+var_30]
0x140068e51  xor     rcx, rsp; StackCookie
0x140068e54  call    __security_check_cookie
0x140068e59  mov     rbx, [rsp+280h+arg_10]
0x140068e61  add     rsp, 260h
0x140068e68  pop     r15
0x140068e6a  pop     r14
0x140068e6c  pop     rdi
0x140068e6d  pop     rsi
0x140068e6e  pop     rbp
0x140068e6f  retn
0x140068e70  mov     rcx, [rbp+188h]; this
0x140068e77  mov     edx, 0A0Bh; void *
0x140068e7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068e82  mov     rcx, [rbp+188h]; this
0x140068e89  mov     edx, 0A0Bh; void *
0x140068e8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068e94  mov     rcx, [rbp+188h]; this
0x140068e9b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140068ea1  mov     rcx, [rbp+188h]; this
0x140068ea8  mov     edx, 0A15h; void *
0x140068ead  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068eb3  mov     rcx, [rbp+188h]; this
0x140068eba  mov     edx, 0A0Bh; void *
0x140068ebf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068ec5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140068ecb  mov     rcx, [rbp+188h]; this
0x140068ed2  mov     edx, 0A0Bh; void *
0x140068ed7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068edd  mov     rcx, [rbp+188h]; this
0x140068ee4  mov     edx, 0A0Bh; void *
0x140068ee9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068eef  mov     rcx, [rbp+188h]; this
0x140068ef6  mov     edx, 0A15h; void *
0x140068efb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068f01  mov     rcx, [rbp+188h]; this
0x140068f08  mov     edx, 0A15h; void *
0x140068f0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
