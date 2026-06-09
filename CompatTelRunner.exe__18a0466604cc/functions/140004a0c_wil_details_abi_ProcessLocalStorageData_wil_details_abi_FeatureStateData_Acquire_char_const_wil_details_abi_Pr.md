# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004a0c`
- end: `0x140004dd3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400050a4`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140003b84`
- `0x140004a0c`
- `0x140004ddc`
- `0x1400052f8`
- `0x1400061a8`
- `0x140006e88`
- `0x1400088f4`
- `0x1400093e8`
- `0x14000986c`
- `0x14000a11c`
- `0x14000a12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004b25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004c4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004ce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004b25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004c4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004ce8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140004cb5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140004cb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004aa4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004aa4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004a83`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004a45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004cfe`

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
0x140004a0c  mov     [rsp-8+arg_10], rbx
0x140004a11  push    rbp
0x140004a12  push    rsi
0x140004a13  push    rdi
0x140004a14  push    r14
0x140004a16  push    r15
0x140004a18  lea     rbp, [rsp-160h]
0x140004a20  sub     rsp, 260h
0x140004a27  mov     rax, cs:__security_cookie
0x140004a2e  xor     rax, rsp
0x140004a31  mov     [rbp+180h+var_30], rax
0x140004a38  mov     r15, rdx
0x140004a3b  mov     qword ptr [rdx], 0
0x140004a42  mov     rbx, rcx
0x140004a45  call    cs:__imp_GetCurrentProcessId
0x140004a4b  mov     r14d, 130h
0x140004a51  mov     [rsp+280h+var_258], rbx
0x140004a56  mov     r9d, eax
0x140004a59  mov     [rsp+280h+var_260], r14d; int
0x140004a5e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004a65  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004a6a  lea     edx, [r14-2Ch]; unsigned __int64
0x140004a6e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004a73  mov     r9d, 1F0001h; dwDesiredAccess
0x140004a79  lea     rdx, [rsp+280h+Name]; lpName
0x140004a7e  xor     r8d, r8d; dwFlags
0x140004a81  xor     ecx, ecx; lpMutexAttributes
0x140004a83  call    cs:__imp_CreateMutexExW
0x140004a89  mov     rbx, rax
0x140004a8c  test    rax, rax
0x140004a8f  jnz     short loc_140004A9B
0x140004a91  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004a96  jmp     loc_140004D0A
0x140004a9b  xor     r8d, r8d; bAlertable
0x140004a9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004aa1  mov     rcx, rbx; hHandle
0x140004aa4  call    cs:__imp_WaitForSingleObjectEx
0x140004aaa  cmp     eax, 102h
0x140004aaf  jz      short loc_140004AC1
0x140004ab1  test    eax, 0FFFFFF7Fh
0x140004ab6  jnz     loc_140004D54
0x140004abc  mov     rdi, rbx
0x140004abf  jmp     short loc_140004AC3
0x140004ac1  xor     edi, edi
0x140004ac3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004ac8  mov     [rsp+280h+hObject], 0
0x140004ad1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004ad6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004adb  mov     esi, eax
0x140004add  test    eax, eax
0x140004adf  jns     short loc_140004B4B
0x140004ae1  mov     rcx, [rbp+188h]; this
0x140004ae8  mov     r9d, eax; char *
0x140004aeb  mov     edx, 66h ; 'f'; void *
0x140004af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004af5  mov     rcx, [rbp+188h]; this
0x140004afc  mov     r9d, esi; char *
0x140004aff  mov     edx, 6Fh ; 'o'; void *
0x140004b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b09  mov     rcx, [rbp+188h]; this
0x140004b10  mov     r9d, esi; char *
0x140004b13  mov     edx, 12Eh; void *
0x140004b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b1d  test    rdi, rdi
0x140004b20  jz      short loc_140004B33
0x140004b22  mov     rcx, rdi; hMutex
0x140004b25  call    cs:__imp_ReleaseMutex
0x140004b2b  test    eax, eax
0x140004b2d  jz      loc_140004D61
0x140004b33  mov     rcx, rbx; hObject
0x140004b36  call    cs:__imp_CloseHandle
0x140004b3c  test    eax, eax
0x140004b3e  jz      loc_140004D73
0x140004b44  mov     eax, esi
0x140004b46  jmp     loc_140004D0A
0x140004b4b  mov     rax, [rsp+280h+hObject]
0x140004b50  lea     rcx, ds:0[rax*4]
0x140004b58  test    rcx, rcx
0x140004b5b  jz      short loc_140004B6B
0x140004b5d  mov     [r15], rcx
0x140004b60  mov     eax, [rcx]
0x140004b62  inc     eax
0x140004b64  mov     [rcx], eax
0x140004b66  jmp     loc_140004CE0
0x140004b6b  mov     rdx, r14; dwBytes
0x140004b6e  mov     qword ptr [r15], 0
0x140004b75  mov     ecx, 8; dwFlags
0x140004b7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004b7f  mov     r14, rax
0x140004b82  test    rax, rax
0x140004b85  jnz     short loc_140004BA5
0x140004b87  mov     rcx, [rbp+188h]; this
0x140004b8e  mov     esi, 8007000Eh
0x140004b93  mov     r9d, esi; char *
0x140004b96  mov     edx, 14Bh; void *
0x140004b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ba0  jmp     loc_140004C30
0x140004ba5  xorps   xmm0, xmm0
0x140004ba8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004bae  test    r14b, 3
0x140004bb2  jnz     loc_140004D85
0x140004bb8  mov     r9, r14
0x140004bbb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004bc0  shr     r9, 2; unsigned __int64
0x140004bc4  lea     rcx, [rsp+280h+hObject]; this
0x140004bc9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140004bce  mov     esi, eax
0x140004bd0  test    eax, eax
0x140004bd2  jns     loc_140004C70
0x140004bd8  mov     rcx, [rbp+188h]; this
0x140004bdf  mov     r9d, eax; char *
0x140004be2  mov     edx, 14Eh; void *
0x140004be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004bec  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004bf1  test    rcx, rcx
0x140004bf4  jz      short loc_140004C04
0x140004bf6  call    cs:__imp_CloseHandle
0x140004bfc  test    eax, eax
0x140004bfe  jz      loc_140004D8B
0x140004c04  mov     rcx, [rsp+280h+hObject]; hObject
0x140004c09  test    rcx, rcx
0x140004c0c  jz      short loc_140004C1C
0x140004c0e  call    cs:__imp_CloseHandle
0x140004c14  test    eax, eax
0x140004c16  jz      loc_140004D9D
0x140004c1c  call    cs:__imp_GetProcessHeap
0x140004c22  mov     r8, r14; lpMem
0x140004c25  xor     edx, edx; dwFlags
0x140004c27  mov     rcx, rax; hHeap
0x140004c2a  call    cs:__imp_HeapFree
0x140004c30  mov     rcx, [rbp+188h]; this
0x140004c37  mov     r9d, esi; char *
0x140004c3a  mov     edx, 137h; void *
0x140004c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004c44  test    rdi, rdi
0x140004c47  jz      short loc_140004C5A
0x140004c49  mov     rcx, rdi; hMutex
0x140004c4c  call    cs:__imp_ReleaseMutex
0x140004c52  test    eax, eax
0x140004c54  jz      loc_140004DAF
0x140004c5a  mov     rcx, rbx; hObject
0x140004c5d  call    cs:__imp_CloseHandle
0x140004c63  test    eax, eax
0x140004c65  jz      loc_140004D42
0x140004c6b  jmp     loc_140004B44
0x140004c70  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004c75  lea     rcx, [r14+28h]; void *
0x140004c79  mov     dword ptr [r14], 1
0x140004c80  xor     edx, edx; Val
0x140004c82  mov     [r14+8], rbx
0x140004c86  mov     r8d, 108h; Size
0x140004c8c  movdqu  xmmword ptr [r14+10h], xmm0
0x140004c92  call    memset_0
0x140004c97  xor     eax, eax
0x140004c99  lea     rcx, [r14+28h]; this
0x140004c9d  mov     [r14+20h], rax
0x140004ca1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140004ca6  lea     rbx, [r14+0E8h]
0x140004cad  xor     r8d, r8d; Flags
0x140004cb0  mov     rcx, rbx; lpCriticalSection
0x140004cb3  xor     edx, edx; dwSpinCount
0x140004cb5  call    cs:__imp_InitializeCriticalSectionEx
0x140004cbb  mov     qword ptr [rbx+28h], 0
0x140004cc3  mov     qword ptr [rbx+30h], 0
0x140004ccb  mov     qword ptr [rbx+38h], 0
0x140004cd3  mov     qword ptr [rbx+40h], 0
0x140004cdb  xor     ebx, ebx
0x140004cdd  mov     [r15], r14
0x140004ce0  test    rdi, rdi
0x140004ce3  jz      short loc_140004CF6
0x140004ce5  mov     rcx, rdi; hMutex
0x140004ce8  call    cs:__imp_ReleaseMutex
0x140004cee  test    eax, eax
0x140004cf0  jz      loc_140004DC1
0x140004cf6  test    rbx, rbx
0x140004cf9  jz      short loc_140004D08
0x140004cfb  mov     rcx, rbx; hObject
0x140004cfe  call    cs:__imp_CloseHandle
0x140004d04  test    eax, eax
0x140004d06  jz      short loc_140004D30
0x140004d08  xor     eax, eax
0x140004d0a  mov     rcx, [rbp+180h+var_30]
0x140004d11  xor     rcx, rsp; StackCookie
0x140004d14  call    __security_check_cookie
0x140004d19  mov     rbx, [rsp+280h+arg_10]
0x140004d21  add     rsp, 260h
0x140004d28  pop     r15
0x140004d2a  pop     r14
0x140004d2c  pop     rdi
0x140004d2d  pop     rsi
0x140004d2e  pop     rbp
0x140004d2f  retn
0x140004d30  mov     rcx, [rbp+188h]; this
0x140004d37  mov     edx, 0A0Bh; void *
0x140004d3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d42  mov     rcx, [rbp+188h]; this
0x140004d49  mov     edx, 0A0Bh; void *
0x140004d4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d54  mov     rcx, [rbp+188h]; this
0x140004d5b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004d61  mov     rcx, [rbp+188h]; this
0x140004d68  mov     edx, 0A15h; void *
0x140004d6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d73  mov     rcx, [rbp+188h]; this
0x140004d7a  mov     edx, 0A0Bh; void *
0x140004d7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d85  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004d8b  mov     rcx, [rbp+188h]; this
0x140004d92  mov     edx, 0A0Bh; void *
0x140004d97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d9d  mov     rcx, [rbp+188h]; this
0x140004da4  mov     edx, 0A0Bh; void *
0x140004da9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004daf  mov     rcx, [rbp+188h]; this
0x140004db6  mov     edx, 0A15h; void *
0x140004dbb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004dc1  mov     rcx, [rbp+188h]; this
0x140004dc8  mov     edx, 0A15h; void *
0x140004dcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
