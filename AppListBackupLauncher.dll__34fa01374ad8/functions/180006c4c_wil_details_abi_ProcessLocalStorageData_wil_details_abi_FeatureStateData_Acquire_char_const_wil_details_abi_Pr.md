# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006c4c`
- end: `0x180007013`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800077a0`

## callees

- `0x180002300`
- `0x180002de0`
- `0x180004fdc`
- `0x180006c4c`
- `0x180007084`
- `0x1800079f4`
- `0x180008930`
- `0x180009ccc`
- `0x18000bfb4`
- `0x18000d290`
- `0x18000d71c`
- `0x18000e804`
- `0x18000e814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006e8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006e8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006ce4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006ce4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006cc3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006cc3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006ef5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006ef5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006c85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f3e`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
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
0x180006c4c  mov     [rsp-8+arg_10], rbx
0x180006c51  push    rbp
0x180006c52  push    rsi
0x180006c53  push    rdi
0x180006c54  push    r14
0x180006c56  push    r15
0x180006c58  lea     rbp, [rsp-160h]
0x180006c60  sub     rsp, 260h
0x180006c67  mov     rax, cs:__security_cookie
0x180006c6e  xor     rax, rsp
0x180006c71  mov     [rbp+180h+var_30], rax
0x180006c78  mov     r15, rdx
0x180006c7b  mov     qword ptr [rdx], 0
0x180006c82  mov     rbx, rcx
0x180006c85  call    cs:__imp_GetCurrentProcessId
0x180006c8b  mov     r14d, 130h
0x180006c91  mov     [rsp+280h+var_258], rbx
0x180006c96  mov     r9d, eax
0x180006c99  mov     [rsp+280h+var_260], r14d; int
0x180006c9e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006ca5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006caa  lea     edx, [r14-2Ch]; unsigned __int64
0x180006cae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006cb3  mov     r9d, 1F0001h; dwDesiredAccess
0x180006cb9  lea     rdx, [rsp+280h+Name]; lpName
0x180006cbe  xor     r8d, r8d; dwFlags
0x180006cc1  xor     ecx, ecx; lpMutexAttributes
0x180006cc3  call    cs:__imp_CreateMutexExW
0x180006cc9  mov     rbx, rax
0x180006ccc  test    rax, rax
0x180006ccf  jnz     short loc_180006CDB
0x180006cd1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006cd6  jmp     loc_180006F4A
0x180006cdb  xor     r8d, r8d; bAlertable
0x180006cde  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006ce1  mov     rcx, rbx; hHandle
0x180006ce4  call    cs:__imp_WaitForSingleObjectEx
0x180006cea  cmp     eax, 102h
0x180006cef  jz      short loc_180006D01
0x180006cf1  test    eax, 0FFFFFF7Fh
0x180006cf6  jnz     loc_180006F94
0x180006cfc  mov     rdi, rbx
0x180006cff  jmp     short loc_180006D03
0x180006d01  xor     edi, edi
0x180006d03  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006d08  mov     [rsp+280h+hObject], 0
0x180006d11  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006d16  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006d1b  mov     esi, eax
0x180006d1d  test    eax, eax
0x180006d1f  jns     short loc_180006D8B
0x180006d21  mov     rcx, [rbp+188h]; this
0x180006d28  mov     r9d, eax; char *
0x180006d2b  mov     edx, 66h ; 'f'; void *
0x180006d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d35  mov     rcx, [rbp+188h]; this
0x180006d3c  mov     r9d, esi; char *
0x180006d3f  mov     edx, 6Fh ; 'o'; void *
0x180006d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d49  mov     rcx, [rbp+188h]; this
0x180006d50  mov     r9d, esi; char *
0x180006d53  mov     edx, 12Eh; void *
0x180006d58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d5d  test    rdi, rdi
0x180006d60  jz      short loc_180006D73
0x180006d62  mov     rcx, rdi; hMutex
0x180006d65  call    cs:__imp_ReleaseMutex
0x180006d6b  test    eax, eax
0x180006d6d  jz      loc_180006FA1
0x180006d73  mov     rcx, rbx; hObject
0x180006d76  call    cs:__imp_CloseHandle
0x180006d7c  test    eax, eax
0x180006d7e  jz      loc_180006FB3
0x180006d84  mov     eax, esi
0x180006d86  jmp     loc_180006F4A
0x180006d8b  mov     rax, [rsp+280h+hObject]
0x180006d90  lea     rcx, ds:0[rax*4]
0x180006d98  test    rcx, rcx
0x180006d9b  jz      short loc_180006DAB
0x180006d9d  mov     [r15], rcx
0x180006da0  mov     eax, [rcx]
0x180006da2  inc     eax
0x180006da4  mov     [rcx], eax
0x180006da6  jmp     loc_180006F20
0x180006dab  mov     rdx, r14; dwBytes
0x180006dae  mov     qword ptr [r15], 0
0x180006db5  mov     ecx, 8; dwFlags
0x180006dba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006dbf  mov     r14, rax
0x180006dc2  test    rax, rax
0x180006dc5  jnz     short loc_180006DE5
0x180006dc7  mov     rcx, [rbp+188h]; this
0x180006dce  mov     esi, 8007000Eh
0x180006dd3  mov     r9d, esi; char *
0x180006dd6  mov     edx, 14Bh; void *
0x180006ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006de0  jmp     loc_180006E70
0x180006de5  xorps   xmm0, xmm0
0x180006de8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006dee  test    r14b, 3
0x180006df2  jnz     loc_180006FC5
0x180006df8  mov     r9, r14
0x180006dfb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006e00  shr     r9, 2; unsigned __int64
0x180006e04  lea     rcx, [rsp+280h+hObject]; this
0x180006e09  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006e0e  mov     esi, eax
0x180006e10  test    eax, eax
0x180006e12  jns     loc_180006EB0
0x180006e18  mov     rcx, [rbp+188h]; this
0x180006e1f  mov     r9d, eax; char *
0x180006e22  mov     edx, 14Eh; void *
0x180006e27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e2c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006e31  test    rcx, rcx
0x180006e34  jz      short loc_180006E44
0x180006e36  call    cs:__imp_CloseHandle
0x180006e3c  test    eax, eax
0x180006e3e  jz      loc_180006FCB
0x180006e44  mov     rcx, [rsp+280h+hObject]; hObject
0x180006e49  test    rcx, rcx
0x180006e4c  jz      short loc_180006E5C
0x180006e4e  call    cs:__imp_CloseHandle
0x180006e54  test    eax, eax
0x180006e56  jz      loc_180006FDD
0x180006e5c  call    cs:__imp_GetProcessHeap
0x180006e62  mov     r8, r14; lpMem
0x180006e65  xor     edx, edx; dwFlags
0x180006e67  mov     rcx, rax; hHeap
0x180006e6a  call    cs:__imp_HeapFree
0x180006e70  mov     rcx, [rbp+188h]; this
0x180006e77  mov     r9d, esi; char *
0x180006e7a  mov     edx, 137h; void *
0x180006e7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e84  test    rdi, rdi
0x180006e87  jz      short loc_180006E9A
0x180006e89  mov     rcx, rdi; hMutex
0x180006e8c  call    cs:__imp_ReleaseMutex
0x180006e92  test    eax, eax
0x180006e94  jz      loc_180006FEF
0x180006e9a  mov     rcx, rbx; hObject
0x180006e9d  call    cs:__imp_CloseHandle
0x180006ea3  test    eax, eax
0x180006ea5  jz      loc_180006F82
0x180006eab  jmp     loc_180006D84
0x180006eb0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006eb5  lea     rcx, [r14+28h]; void *
0x180006eb9  mov     dword ptr [r14], 1
0x180006ec0  xor     edx, edx; Val
0x180006ec2  mov     [r14+8], rbx
0x180006ec6  mov     r8d, 108h; Size
0x180006ecc  movdqu  xmmword ptr [r14+10h], xmm0
0x180006ed2  call    memset_0
0x180006ed7  xor     eax, eax
0x180006ed9  lea     rcx, [r14+28h]; this
0x180006edd  mov     [r14+20h], rax
0x180006ee1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006ee6  lea     rbx, [r14+0E8h]
0x180006eed  xor     r8d, r8d; Flags
0x180006ef0  mov     rcx, rbx; lpCriticalSection
0x180006ef3  xor     edx, edx; dwSpinCount
0x180006ef5  call    cs:__imp_InitializeCriticalSectionEx
0x180006efb  mov     qword ptr [rbx+28h], 0
0x180006f03  mov     qword ptr [rbx+30h], 0
0x180006f0b  mov     qword ptr [rbx+38h], 0
0x180006f13  mov     qword ptr [rbx+40h], 0
0x180006f1b  xor     ebx, ebx
0x180006f1d  mov     [r15], r14
0x180006f20  test    rdi, rdi
0x180006f23  jz      short loc_180006F36
0x180006f25  mov     rcx, rdi; hMutex
0x180006f28  call    cs:__imp_ReleaseMutex
0x180006f2e  test    eax, eax
0x180006f30  jz      loc_180007001
0x180006f36  test    rbx, rbx
0x180006f39  jz      short loc_180006F48
0x180006f3b  mov     rcx, rbx; hObject
0x180006f3e  call    cs:__imp_CloseHandle
0x180006f44  test    eax, eax
0x180006f46  jz      short loc_180006F70
0x180006f48  xor     eax, eax
0x180006f4a  mov     rcx, [rbp+180h+var_30]
0x180006f51  xor     rcx, rsp; StackCookie
0x180006f54  call    __security_check_cookie
0x180006f59  mov     rbx, [rsp+280h+arg_10]
0x180006f61  add     rsp, 260h
0x180006f68  pop     r15
0x180006f6a  pop     r14
0x180006f6c  pop     rdi
0x180006f6d  pop     rsi
0x180006f6e  pop     rbp
0x180006f6f  retn
0x180006f70  mov     rcx, [rbp+188h]; this
0x180006f77  mov     edx, 0A0Bh; void *
0x180006f7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f82  mov     rcx, [rbp+188h]; this
0x180006f89  mov     edx, 0A0Bh; void *
0x180006f8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f94  mov     rcx, [rbp+188h]; this
0x180006f9b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006fa1  mov     rcx, [rbp+188h]; this
0x180006fa8  mov     edx, 0A15h; void *
0x180006fad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fb3  mov     rcx, [rbp+188h]; this
0x180006fba  mov     edx, 0A0Bh; void *
0x180006fbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fc5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006fcb  mov     rcx, [rbp+188h]; this
0x180006fd2  mov     edx, 0A0Bh; void *
0x180006fd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fdd  mov     rcx, [rbp+188h]; this
0x180006fe4  mov     edx, 0A0Bh; void *
0x180006fe9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fef  mov     rcx, [rbp+188h]; this
0x180006ff6  mov     edx, 0A15h; void *
0x180006ffb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007001  mov     rcx, [rbp+188h]; this
0x180007008  mov     edx, 0A15h; void *
0x18000700d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
