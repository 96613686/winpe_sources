# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180019b14`
- end: `0x180019edb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18001b0a0`

## callees

- `0x180003850`
- `0x180018ec8`
- `0x180019b14`
- `0x18001a64c`
- `0x18001b230`
- `0x18001be4c`
- `0x18001f350`
- `0x180021f38`
- `0x180023518`
- `0x1800247e4`
- `0x1800247f4`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180019dbd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180019dbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019c2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019df0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019c2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019df0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019bac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019bac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019b8b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019b8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019b4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d32`

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
0x180019b14  mov     [rsp-8+arg_10], rbx
0x180019b19  push    rbp
0x180019b1a  push    rsi
0x180019b1b  push    rdi
0x180019b1c  push    r14
0x180019b1e  push    r15
0x180019b20  lea     rbp, [rsp-160h]
0x180019b28  sub     rsp, 260h
0x180019b2f  mov     rax, cs:__security_cookie
0x180019b36  xor     rax, rsp
0x180019b39  mov     [rbp+180h+var_30], rax
0x180019b40  mov     r15, rdx
0x180019b43  mov     qword ptr [rdx], 0
0x180019b4a  mov     rbx, rcx
0x180019b4d  call    cs:__imp_GetCurrentProcessId
0x180019b53  mov     r14d, 130h
0x180019b59  mov     [rsp+280h+var_258], rbx
0x180019b5e  mov     r9d, eax
0x180019b61  mov     [rsp+280h+var_260], r14d; int
0x180019b66  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180019b6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019b72  lea     edx, [r14-2Ch]; unsigned __int64
0x180019b76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019b7b  mov     r9d, 1F0001h; dwDesiredAccess
0x180019b81  lea     rdx, [rsp+280h+Name]; lpName
0x180019b86  xor     r8d, r8d; dwFlags
0x180019b89  xor     ecx, ecx; lpMutexAttributes
0x180019b8b  call    cs:__imp_CreateMutexExW
0x180019b91  mov     rbx, rax
0x180019b94  test    rax, rax
0x180019b97  jnz     short loc_180019BA3
0x180019b99  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019b9e  jmp     loc_180019E12
0x180019ba3  xor     r8d, r8d; bAlertable
0x180019ba6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019ba9  mov     rcx, rbx; hHandle
0x180019bac  call    cs:__imp_WaitForSingleObjectEx
0x180019bb2  cmp     eax, 102h
0x180019bb7  jz      short loc_180019BC9
0x180019bb9  test    eax, 0FFFFFF7Fh
0x180019bbe  jnz     loc_180019E5C
0x180019bc4  mov     rdi, rbx
0x180019bc7  jmp     short loc_180019BCB
0x180019bc9  xor     edi, edi
0x180019bcb  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180019bd0  mov     [rsp+280h+hObject], 0
0x180019bd9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019bde  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180019be3  mov     esi, eax
0x180019be5  test    eax, eax
0x180019be7  jns     short loc_180019C53
0x180019be9  mov     rcx, [rbp+188h]; this
0x180019bf0  mov     r9d, eax; char *
0x180019bf3  mov     edx, 66h ; 'f'; void *
0x180019bf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019bfd  mov     rcx, [rbp+188h]; this
0x180019c04  mov     r9d, esi; char *
0x180019c07  mov     edx, 6Fh ; 'o'; void *
0x180019c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c11  mov     rcx, [rbp+188h]; this
0x180019c18  mov     r9d, esi; char *
0x180019c1b  mov     edx, 12Eh; void *
0x180019c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c25  test    rdi, rdi
0x180019c28  jz      short loc_180019C3B
0x180019c2a  mov     rcx, rdi; hMutex
0x180019c2d  call    cs:__imp_ReleaseMutex
0x180019c33  test    eax, eax
0x180019c35  jz      loc_180019E69
0x180019c3b  mov     rcx, rbx; hObject
0x180019c3e  call    cs:__imp_CloseHandle
0x180019c44  test    eax, eax
0x180019c46  jz      loc_180019E7B
0x180019c4c  mov     eax, esi
0x180019c4e  jmp     loc_180019E12
0x180019c53  mov     rax, [rsp+280h+hObject]
0x180019c58  lea     rcx, ds:0[rax*4]
0x180019c60  test    rcx, rcx
0x180019c63  jz      short loc_180019C73
0x180019c65  mov     [r15], rcx
0x180019c68  mov     eax, [rcx]
0x180019c6a  inc     eax
0x180019c6c  mov     [rcx], eax
0x180019c6e  jmp     loc_180019DE8
0x180019c73  mov     rdx, r14; dwBytes
0x180019c76  mov     qword ptr [r15], 0
0x180019c7d  mov     ecx, 8; dwFlags
0x180019c82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019c87  mov     r14, rax
0x180019c8a  test    rax, rax
0x180019c8d  jnz     short loc_180019CAD
0x180019c8f  mov     rcx, [rbp+188h]; this
0x180019c96  mov     esi, 8007000Eh
0x180019c9b  mov     r9d, esi; char *
0x180019c9e  mov     edx, 14Bh; void *
0x180019ca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ca8  jmp     loc_180019D38
0x180019cad  xorps   xmm0, xmm0
0x180019cb0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180019cb6  test    r14b, 3
0x180019cba  jnz     loc_180019E8D
0x180019cc0  mov     r9, r14
0x180019cc3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180019cc8  shr     r9, 2; unsigned __int64
0x180019ccc  lea     rcx, [rsp+280h+hObject]; this
0x180019cd1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180019cd6  mov     esi, eax
0x180019cd8  test    eax, eax
0x180019cda  jns     loc_180019D78
0x180019ce0  mov     rcx, [rbp+188h]; this
0x180019ce7  mov     r9d, eax; char *
0x180019cea  mov     edx, 14Eh; void *
0x180019cef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019cf4  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180019cf9  test    rcx, rcx
0x180019cfc  jz      short loc_180019D0C
0x180019cfe  call    cs:__imp_CloseHandle
0x180019d04  test    eax, eax
0x180019d06  jz      loc_180019E93
0x180019d0c  mov     rcx, [rsp+280h+hObject]; hObject
0x180019d11  test    rcx, rcx
0x180019d14  jz      short loc_180019D24
0x180019d16  call    cs:__imp_CloseHandle
0x180019d1c  test    eax, eax
0x180019d1e  jz      loc_180019EA5
0x180019d24  call    cs:__imp_GetProcessHeap
0x180019d2a  mov     r8, r14; lpMem
0x180019d2d  xor     edx, edx; dwFlags
0x180019d2f  mov     rcx, rax; hHeap
0x180019d32  call    cs:__imp_HeapFree
0x180019d38  mov     rcx, [rbp+188h]; this
0x180019d3f  mov     r9d, esi; char *
0x180019d42  mov     edx, 137h; void *
0x180019d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d4c  test    rdi, rdi
0x180019d4f  jz      short loc_180019D62
0x180019d51  mov     rcx, rdi; hMutex
0x180019d54  call    cs:__imp_ReleaseMutex
0x180019d5a  test    eax, eax
0x180019d5c  jz      loc_180019EB7
0x180019d62  mov     rcx, rbx; hObject
0x180019d65  call    cs:__imp_CloseHandle
0x180019d6b  test    eax, eax
0x180019d6d  jz      loc_180019E4A
0x180019d73  jmp     loc_180019C4C
0x180019d78  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180019d7d  lea     rcx, [r14+28h]; void *
0x180019d81  mov     dword ptr [r14], 1
0x180019d88  xor     edx, edx; Val
0x180019d8a  mov     [r14+8], rbx
0x180019d8e  mov     r8d, 108h; Size
0x180019d94  movdqu  xmmword ptr [r14+10h], xmm0
0x180019d9a  call    memset_0
0x180019d9f  xor     eax, eax
0x180019da1  lea     rcx, [r14+28h]; this
0x180019da5  mov     [r14+20h], rax
0x180019da9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180019dae  lea     rbx, [r14+0E8h]
0x180019db5  xor     r8d, r8d; Flags
0x180019db8  mov     rcx, rbx; lpCriticalSection
0x180019dbb  xor     edx, edx; dwSpinCount
0x180019dbd  call    cs:__imp_InitializeCriticalSectionEx
0x180019dc3  mov     qword ptr [rbx+28h], 0
0x180019dcb  mov     qword ptr [rbx+30h], 0
0x180019dd3  mov     qword ptr [rbx+38h], 0
0x180019ddb  mov     qword ptr [rbx+40h], 0
0x180019de3  xor     ebx, ebx
0x180019de5  mov     [r15], r14
0x180019de8  test    rdi, rdi
0x180019deb  jz      short loc_180019DFE
0x180019ded  mov     rcx, rdi; hMutex
0x180019df0  call    cs:__imp_ReleaseMutex
0x180019df6  test    eax, eax
0x180019df8  jz      loc_180019EC9
0x180019dfe  test    rbx, rbx
0x180019e01  jz      short loc_180019E10
0x180019e03  mov     rcx, rbx; hObject
0x180019e06  call    cs:__imp_CloseHandle
0x180019e0c  test    eax, eax
0x180019e0e  jz      short loc_180019E38
0x180019e10  xor     eax, eax
0x180019e12  mov     rcx, [rbp+180h+var_30]
0x180019e19  xor     rcx, rsp; StackCookie
0x180019e1c  call    __security_check_cookie
0x180019e21  mov     rbx, [rsp+280h+arg_10]
0x180019e29  add     rsp, 260h
0x180019e30  pop     r15
0x180019e32  pop     r14
0x180019e34  pop     rdi
0x180019e35  pop     rsi
0x180019e36  pop     rbp
0x180019e37  retn
0x180019e38  mov     rcx, [rbp+188h]; this
0x180019e3f  mov     edx, 0A0Bh; void *
0x180019e44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e4a  mov     rcx, [rbp+188h]; this
0x180019e51  mov     edx, 0A0Bh; void *
0x180019e56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e5c  mov     rcx, [rbp+188h]; this
0x180019e63  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180019e69  mov     rcx, [rbp+188h]; this
0x180019e70  mov     edx, 0A15h; void *
0x180019e75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e7b  mov     rcx, [rbp+188h]; this
0x180019e82  mov     edx, 0A0Bh; void *
0x180019e87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e8d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180019e93  mov     rcx, [rbp+188h]; this
0x180019e9a  mov     edx, 0A0Bh; void *
0x180019e9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019ea5  mov     rcx, [rbp+188h]; this
0x180019eac  mov     edx, 0A0Bh; void *
0x180019eb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019eb7  mov     rcx, [rbp+188h]; this
0x180019ebe  mov     edx, 0A15h; void *
0x180019ec3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019ec9  mov     rcx, [rbp+188h]; this
0x180019ed0  mov     edx, 0A15h; void *
0x180019ed5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
