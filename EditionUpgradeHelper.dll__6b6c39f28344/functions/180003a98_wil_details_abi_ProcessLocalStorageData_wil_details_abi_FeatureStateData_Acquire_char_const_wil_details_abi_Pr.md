# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003a98`
- end: `0x180003e5f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004134`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x180002f9c`
- `0x180003a98`
- `0x180003e68`
- `0x1800042c4`
- `0x180004be8`
- `0x1800057d8`
- `0x180006ae0`
- `0x180007020`
- `0x180007348`
- `0x180007b2c`
- `0x180007b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b30`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003d41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003d41`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b0f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ca8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d8a`

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
0x180003a98  mov     [rsp-8+arg_10], rbx
0x180003a9d  push    rbp
0x180003a9e  push    rsi
0x180003a9f  push    rdi
0x180003aa0  push    r14
0x180003aa2  push    r15
0x180003aa4  lea     rbp, [rsp-160h]
0x180003aac  sub     rsp, 260h
0x180003ab3  mov     rax, cs:__security_cookie
0x180003aba  xor     rax, rsp
0x180003abd  mov     [rbp+180h+var_30], rax
0x180003ac4  mov     r15, rdx
0x180003ac7  mov     qword ptr [rdx], 0
0x180003ace  mov     rbx, rcx
0x180003ad1  call    cs:__imp_GetCurrentProcessId
0x180003ad7  mov     r14d, 130h
0x180003add  mov     [rsp+280h+var_258], rbx
0x180003ae2  mov     r9d, eax
0x180003ae5  mov     [rsp+280h+var_260], r14d; int
0x180003aea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003af1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003af6  lea     edx, [r14-2Ch]; unsigned __int64
0x180003afa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003aff  mov     r9d, 1F0001h; dwDesiredAccess
0x180003b05  lea     rdx, [rsp+280h+Name]; lpName
0x180003b0a  xor     r8d, r8d; dwFlags
0x180003b0d  xor     ecx, ecx; lpMutexAttributes
0x180003b0f  call    cs:__imp_CreateMutexExW
0x180003b15  mov     rbx, rax
0x180003b18  test    rax, rax
0x180003b1b  jnz     short loc_180003B27
0x180003b1d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b22  jmp     loc_180003D96
0x180003b27  xor     r8d, r8d; bAlertable
0x180003b2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b2d  mov     rcx, rbx; hHandle
0x180003b30  call    cs:__imp_WaitForSingleObjectEx
0x180003b36  cmp     eax, 102h
0x180003b3b  jz      short loc_180003B4D
0x180003b3d  test    eax, 0FFFFFF7Fh
0x180003b42  jnz     loc_180003DE0
0x180003b48  mov     rdi, rbx
0x180003b4b  jmp     short loc_180003B4F
0x180003b4d  xor     edi, edi
0x180003b4f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b54  mov     [rsp+280h+hObject], 0
0x180003b5d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b62  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b67  mov     esi, eax
0x180003b69  test    eax, eax
0x180003b6b  jns     short loc_180003BD7
0x180003b6d  mov     rcx, [rbp+188h]; this
0x180003b74  mov     r9d, eax; char *
0x180003b77  mov     edx, 66h ; 'f'; void *
0x180003b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b81  mov     rcx, [rbp+188h]; this
0x180003b88  mov     r9d, esi; char *
0x180003b8b  mov     edx, 6Fh ; 'o'; void *
0x180003b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b95  mov     rcx, [rbp+188h]; this
0x180003b9c  mov     r9d, esi; char *
0x180003b9f  mov     edx, 12Eh; void *
0x180003ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ba9  test    rdi, rdi
0x180003bac  jz      short loc_180003BBF
0x180003bae  mov     rcx, rdi; hMutex
0x180003bb1  call    cs:__imp_ReleaseMutex
0x180003bb7  test    eax, eax
0x180003bb9  jz      loc_180003DED
0x180003bbf  mov     rcx, rbx; hObject
0x180003bc2  call    cs:__imp_CloseHandle
0x180003bc8  test    eax, eax
0x180003bca  jz      loc_180003DFF
0x180003bd0  mov     eax, esi
0x180003bd2  jmp     loc_180003D96
0x180003bd7  mov     rax, [rsp+280h+hObject]
0x180003bdc  lea     rcx, ds:0[rax*4]
0x180003be4  test    rcx, rcx
0x180003be7  jz      short loc_180003BF7
0x180003be9  mov     [r15], rcx
0x180003bec  mov     eax, [rcx]
0x180003bee  inc     eax
0x180003bf0  mov     [rcx], eax
0x180003bf2  jmp     loc_180003D6C
0x180003bf7  mov     rdx, r14; dwBytes
0x180003bfa  mov     qword ptr [r15], 0
0x180003c01  mov     ecx, 8; dwFlags
0x180003c06  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c0b  mov     r14, rax
0x180003c0e  test    rax, rax
0x180003c11  jnz     short loc_180003C31
0x180003c13  mov     rcx, [rbp+188h]; this
0x180003c1a  mov     esi, 8007000Eh
0x180003c1f  mov     r9d, esi; char *
0x180003c22  mov     edx, 14Bh; void *
0x180003c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c2c  jmp     loc_180003CBC
0x180003c31  xorps   xmm0, xmm0
0x180003c34  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c3a  test    r14b, 3
0x180003c3e  jnz     loc_180003E11
0x180003c44  mov     r9, r14
0x180003c47  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003c4c  shr     r9, 2; unsigned __int64
0x180003c50  lea     rcx, [rsp+280h+hObject]; this
0x180003c55  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003c5a  mov     esi, eax
0x180003c5c  test    eax, eax
0x180003c5e  jns     loc_180003CFC
0x180003c64  mov     rcx, [rbp+188h]; this
0x180003c6b  mov     r9d, eax; char *
0x180003c6e  mov     edx, 14Eh; void *
0x180003c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c78  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003c7d  test    rcx, rcx
0x180003c80  jz      short loc_180003C90
0x180003c82  call    cs:__imp_CloseHandle
0x180003c88  test    eax, eax
0x180003c8a  jz      loc_180003E17
0x180003c90  mov     rcx, [rsp+280h+hObject]; hObject
0x180003c95  test    rcx, rcx
0x180003c98  jz      short loc_180003CA8
0x180003c9a  call    cs:__imp_CloseHandle
0x180003ca0  test    eax, eax
0x180003ca2  jz      loc_180003E29
0x180003ca8  call    cs:__imp_GetProcessHeap
0x180003cae  mov     r8, r14; lpMem
0x180003cb1  xor     edx, edx; dwFlags
0x180003cb3  mov     rcx, rax; hHeap
0x180003cb6  call    cs:__imp_HeapFree
0x180003cbc  mov     rcx, [rbp+188h]; this
0x180003cc3  mov     r9d, esi; char *
0x180003cc6  mov     edx, 137h; void *
0x180003ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cd0  test    rdi, rdi
0x180003cd3  jz      short loc_180003CE6
0x180003cd5  mov     rcx, rdi; hMutex
0x180003cd8  call    cs:__imp_ReleaseMutex
0x180003cde  test    eax, eax
0x180003ce0  jz      loc_180003E3B
0x180003ce6  mov     rcx, rbx; hObject
0x180003ce9  call    cs:__imp_CloseHandle
0x180003cef  test    eax, eax
0x180003cf1  jz      loc_180003DCE
0x180003cf7  jmp     loc_180003BD0
0x180003cfc  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d01  lea     rcx, [r14+28h]; void *
0x180003d05  mov     dword ptr [r14], 1
0x180003d0c  xor     edx, edx; Val
0x180003d0e  mov     [r14+8], rbx
0x180003d12  mov     r8d, 108h; Size
0x180003d18  movdqu  xmmword ptr [r14+10h], xmm0
0x180003d1e  call    memset_0
0x180003d23  xor     eax, eax
0x180003d25  lea     rcx, [r14+28h]; this
0x180003d29  mov     [r14+20h], rax
0x180003d2d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003d32  lea     rbx, [r14+0E8h]
0x180003d39  xor     r8d, r8d; Flags
0x180003d3c  mov     rcx, rbx; lpCriticalSection
0x180003d3f  xor     edx, edx; dwSpinCount
0x180003d41  call    cs:__imp_InitializeCriticalSectionEx
0x180003d47  mov     qword ptr [rbx+28h], 0
0x180003d4f  mov     qword ptr [rbx+30h], 0
0x180003d57  mov     qword ptr [rbx+38h], 0
0x180003d5f  mov     qword ptr [rbx+40h], 0
0x180003d67  xor     ebx, ebx
0x180003d69  mov     [r15], r14
0x180003d6c  test    rdi, rdi
0x180003d6f  jz      short loc_180003D82
0x180003d71  mov     rcx, rdi; hMutex
0x180003d74  call    cs:__imp_ReleaseMutex
0x180003d7a  test    eax, eax
0x180003d7c  jz      loc_180003E4D
0x180003d82  test    rbx, rbx
0x180003d85  jz      short loc_180003D94
0x180003d87  mov     rcx, rbx; hObject
0x180003d8a  call    cs:__imp_CloseHandle
0x180003d90  test    eax, eax
0x180003d92  jz      short loc_180003DBC
0x180003d94  xor     eax, eax
0x180003d96  mov     rcx, [rbp+180h+var_30]
0x180003d9d  xor     rcx, rsp; StackCookie
0x180003da0  call    __security_check_cookie
0x180003da5  mov     rbx, [rsp+280h+arg_10]
0x180003dad  add     rsp, 260h
0x180003db4  pop     r15
0x180003db6  pop     r14
0x180003db8  pop     rdi
0x180003db9  pop     rsi
0x180003dba  pop     rbp
0x180003dbb  retn
0x180003dbc  mov     rcx, [rbp+188h]; this
0x180003dc3  mov     edx, 0A0Bh; void *
0x180003dc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dce  mov     rcx, [rbp+188h]; this
0x180003dd5  mov     edx, 0A0Bh; void *
0x180003dda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003de0  mov     rcx, [rbp+188h]; this
0x180003de7  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003ded  mov     rcx, [rbp+188h]; this
0x180003df4  mov     edx, 0A15h; void *
0x180003df9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dff  mov     rcx, [rbp+188h]; this
0x180003e06  mov     edx, 0A0Bh; void *
0x180003e0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e11  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e17  mov     rcx, [rbp+188h]; this
0x180003e1e  mov     edx, 0A0Bh; void *
0x180003e23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e29  mov     rcx, [rbp+188h]; this
0x180003e30  mov     edx, 0A0Bh; void *
0x180003e35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e3b  mov     rcx, [rbp+188h]; this
0x180003e42  mov     edx, 0A15h; void *
0x180003e47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e4d  mov     rcx, [rbp+188h]; this
0x180003e54  mov     edx, 0A15h; void *
0x180003e59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
