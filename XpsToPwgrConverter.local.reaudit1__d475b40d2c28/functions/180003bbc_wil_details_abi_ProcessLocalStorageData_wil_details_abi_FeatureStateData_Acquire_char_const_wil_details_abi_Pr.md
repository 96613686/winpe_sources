# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003bbc`
- end: `0x180003f83`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004254`

## callees

- `0x180001760`
- `0x180002194`
- `0x180002eb0`
- `0x180003bbc`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c33`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c54`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e98`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003e65`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003e65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003bf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eae`

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
0x180003bbc  mov     [rsp-8+arg_10], rbx
0x180003bc1  push    rbp
0x180003bc2  push    rsi
0x180003bc3  push    rdi
0x180003bc4  push    r14
0x180003bc6  push    r15
0x180003bc8  lea     rbp, [rsp-160h]
0x180003bd0  sub     rsp, 260h
0x180003bd7  mov     rax, cs:__security_cookie
0x180003bde  xor     rax, rsp
0x180003be1  mov     [rbp+180h+var_30], rax
0x180003be8  mov     r15, rdx
0x180003beb  mov     qword ptr [rdx], 0
0x180003bf2  mov     rbx, rcx
0x180003bf5  call    cs:__imp_GetCurrentProcessId
0x180003bfb  mov     r14d, 130h
0x180003c01  mov     [rsp+280h+var_258], rbx
0x180003c06  mov     r9d, eax
0x180003c09  mov     [rsp+280h+var_260], r14d; int
0x180003c0e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c15  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c1a  lea     edx, [r14-2Ch]; unsigned __int64
0x180003c1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c23  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c29  lea     rdx, [rsp+280h+Name]; lpName
0x180003c2e  xor     r8d, r8d; dwFlags
0x180003c31  xor     ecx, ecx; lpMutexAttributes
0x180003c33  call    cs:__imp_CreateMutexExW
0x180003c39  mov     rbx, rax
0x180003c3c  test    rax, rax
0x180003c3f  jnz     short loc_180003C4B
0x180003c41  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c46  jmp     loc_180003EBA
0x180003c4b  xor     r8d, r8d; bAlertable
0x180003c4e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c51  mov     rcx, rbx; hHandle
0x180003c54  call    cs:__imp_WaitForSingleObjectEx
0x180003c5a  cmp     eax, 102h
0x180003c5f  jz      short loc_180003C71
0x180003c61  test    eax, 0FFFFFF7Fh
0x180003c66  jnz     loc_180003F04
0x180003c6c  mov     rdi, rbx
0x180003c6f  jmp     short loc_180003C73
0x180003c71  xor     edi, edi
0x180003c73  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003c78  mov     [rsp+280h+hObject], 0
0x180003c81  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c86  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003c8b  mov     esi, eax
0x180003c8d  test    eax, eax
0x180003c8f  jns     short loc_180003CFB
0x180003c91  mov     rcx, [rbp+188h]; this
0x180003c98  mov     r9d, eax; char *
0x180003c9b  mov     edx, 66h ; 'f'; void *
0x180003ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ca5  mov     rcx, [rbp+188h]; this
0x180003cac  mov     r9d, esi; char *
0x180003caf  mov     edx, 6Fh ; 'o'; void *
0x180003cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cb9  mov     rcx, [rbp+188h]; this
0x180003cc0  mov     r9d, esi; char *
0x180003cc3  mov     edx, 12Eh; void *
0x180003cc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ccd  test    rdi, rdi
0x180003cd0  jz      short loc_180003CE3
0x180003cd2  mov     rcx, rdi; hMutex
0x180003cd5  call    cs:__imp_ReleaseMutex
0x180003cdb  test    eax, eax
0x180003cdd  jz      loc_180003F11
0x180003ce3  mov     rcx, rbx; hObject
0x180003ce6  call    cs:__imp_CloseHandle
0x180003cec  test    eax, eax
0x180003cee  jz      loc_180003F23
0x180003cf4  mov     eax, esi
0x180003cf6  jmp     loc_180003EBA
0x180003cfb  mov     rax, [rsp+280h+hObject]
0x180003d00  lea     rcx, ds:0[rax*4]
0x180003d08  test    rcx, rcx
0x180003d0b  jz      short loc_180003D1B
0x180003d0d  mov     [r15], rcx
0x180003d10  mov     eax, [rcx]
0x180003d12  inc     eax
0x180003d14  mov     [rcx], eax
0x180003d16  jmp     loc_180003E90
0x180003d1b  mov     rdx, r14; dwBytes
0x180003d1e  mov     qword ptr [r15], 0
0x180003d25  mov     ecx, 8; dwFlags
0x180003d2a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d2f  mov     r14, rax
0x180003d32  test    rax, rax
0x180003d35  jnz     short loc_180003D55
0x180003d37  mov     rcx, [rbp+188h]; this
0x180003d3e  mov     esi, 8007000Eh
0x180003d43  mov     r9d, esi; char *
0x180003d46  mov     edx, 14Bh; void *
0x180003d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d50  jmp     loc_180003DE0
0x180003d55  xorps   xmm0, xmm0
0x180003d58  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003d5e  test    r14b, 3
0x180003d62  jnz     loc_180003F35
0x180003d68  mov     r9, r14
0x180003d6b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d70  shr     r9, 2; unsigned __int64
0x180003d74  lea     rcx, [rsp+280h+hObject]; this
0x180003d79  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003d7e  mov     esi, eax
0x180003d80  test    eax, eax
0x180003d82  jns     loc_180003E20
0x180003d88  mov     rcx, [rbp+188h]; this
0x180003d8f  mov     r9d, eax; char *
0x180003d92  mov     edx, 14Eh; void *
0x180003d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d9c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003da1  test    rcx, rcx
0x180003da4  jz      short loc_180003DB4
0x180003da6  call    cs:__imp_CloseHandle
0x180003dac  test    eax, eax
0x180003dae  jz      loc_180003F3B
0x180003db4  mov     rcx, [rsp+280h+hObject]; hObject
0x180003db9  test    rcx, rcx
0x180003dbc  jz      short loc_180003DCC
0x180003dbe  call    cs:__imp_CloseHandle
0x180003dc4  test    eax, eax
0x180003dc6  jz      loc_180003F4D
0x180003dcc  call    cs:__imp_GetProcessHeap
0x180003dd2  mov     r8, r14; lpMem
0x180003dd5  xor     edx, edx; dwFlags
0x180003dd7  mov     rcx, rax; hHeap
0x180003dda  call    cs:__imp_HeapFree
0x180003de0  mov     rcx, [rbp+188h]; this
0x180003de7  mov     r9d, esi; char *
0x180003dea  mov     edx, 137h; void *
0x180003def  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003df4  test    rdi, rdi
0x180003df7  jz      short loc_180003E0A
0x180003df9  mov     rcx, rdi; hMutex
0x180003dfc  call    cs:__imp_ReleaseMutex
0x180003e02  test    eax, eax
0x180003e04  jz      loc_180003F5F
0x180003e0a  mov     rcx, rbx; hObject
0x180003e0d  call    cs:__imp_CloseHandle
0x180003e13  test    eax, eax
0x180003e15  jz      loc_180003EF2
0x180003e1b  jmp     loc_180003CF4
0x180003e20  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e25  lea     rcx, [r14+28h]; void *
0x180003e29  mov     dword ptr [r14], 1
0x180003e30  xor     edx, edx; Val
0x180003e32  mov     [r14+8], rbx
0x180003e36  mov     r8d, 108h; Size
0x180003e3c  movdqu  xmmword ptr [r14+10h], xmm0
0x180003e42  call    memset_0
0x180003e47  xor     eax, eax
0x180003e49  lea     rcx, [r14+28h]; this
0x180003e4d  mov     [r14+20h], rax
0x180003e51  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003e56  lea     rbx, [r14+0E8h]
0x180003e5d  xor     r8d, r8d; Flags
0x180003e60  mov     rcx, rbx; lpCriticalSection
0x180003e63  xor     edx, edx; dwSpinCount
0x180003e65  call    cs:__imp_InitializeCriticalSectionEx
0x180003e6b  mov     qword ptr [rbx+28h], 0
0x180003e73  mov     qword ptr [rbx+30h], 0
0x180003e7b  mov     qword ptr [rbx+38h], 0
0x180003e83  mov     qword ptr [rbx+40h], 0
0x180003e8b  xor     ebx, ebx
0x180003e8d  mov     [r15], r14
0x180003e90  test    rdi, rdi
0x180003e93  jz      short loc_180003EA6
0x180003e95  mov     rcx, rdi; hMutex
0x180003e98  call    cs:__imp_ReleaseMutex
0x180003e9e  test    eax, eax
0x180003ea0  jz      loc_180003F71
0x180003ea6  test    rbx, rbx
0x180003ea9  jz      short loc_180003EB8
0x180003eab  mov     rcx, rbx; hObject
0x180003eae  call    cs:__imp_CloseHandle
0x180003eb4  test    eax, eax
0x180003eb6  jz      short loc_180003EE0
0x180003eb8  xor     eax, eax
0x180003eba  mov     rcx, [rbp+180h+var_30]
0x180003ec1  xor     rcx, rsp; StackCookie
0x180003ec4  call    __security_check_cookie
0x180003ec9  mov     rbx, [rsp+280h+arg_10]
0x180003ed1  add     rsp, 260h
0x180003ed8  pop     r15
0x180003eda  pop     r14
0x180003edc  pop     rdi
0x180003edd  pop     rsi
0x180003ede  pop     rbp
0x180003edf  retn
0x180003ee0  mov     rcx, [rbp+188h]; this
0x180003ee7  mov     edx, 0A0Bh; void *
0x180003eec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ef2  mov     rcx, [rbp+188h]; this
0x180003ef9  mov     edx, 0A0Bh; void *
0x180003efe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f04  mov     rcx, [rbp+188h]; this
0x180003f0b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f11  mov     rcx, [rbp+188h]; this
0x180003f18  mov     edx, 0A15h; void *
0x180003f1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f23  mov     rcx, [rbp+188h]; this
0x180003f2a  mov     edx, 0A0Bh; void *
0x180003f2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f35  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f3b  mov     rcx, [rbp+188h]; this
0x180003f42  mov     edx, 0A0Bh; void *
0x180003f47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f4d  mov     rcx, [rbp+188h]; this
0x180003f54  mov     edx, 0A0Bh; void *
0x180003f59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f5f  mov     rcx, [rbp+188h]; this
0x180003f66  mov     edx, 0A15h; void *
0x180003f6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f71  mov     rcx, [rbp+188h]; this
0x180003f78  mov     edx, 0A15h; void *
0x180003f7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
