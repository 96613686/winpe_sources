# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180021c08`
- end: `0x180021ff9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800261c8`

## callees

- `0x18000a0a8`
- `0x18000a394`
- `0x18000a9e8`
- `0x18000b514`
- `0x18000b760`
- `0x18000bbb4`
- `0x18000bc5c`
- `0x18000c02c`
- `0x18000c03c`
- `0x18001efb8`
- `0x180021c08`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021ca0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021ca0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021f0e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180021c7f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180021c7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180021edb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180021edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021e49`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180021c08  mov     [rsp-8+arg_10], rbx
0x180021c0d  push    rbp
0x180021c0e  push    rsi
0x180021c0f  push    rdi
0x180021c10  push    r14
0x180021c12  push    r15
0x180021c14  lea     rbp, [rsp-160h]
0x180021c1c  sub     rsp, 260h
0x180021c23  mov     rax, cs:__security_cookie
0x180021c2a  xor     rax, rsp
0x180021c2d  mov     [rbp+180h+var_30], rax
0x180021c34  mov     r15, rdx
0x180021c37  mov     qword ptr [rdx], 0
0x180021c3e  mov     rbx, rcx
0x180021c41  call    cs:__imp_GetCurrentProcessId
0x180021c47  mov     r14d, 130h
0x180021c4d  mov     [rsp+280h+var_258], rbx
0x180021c52  mov     r9d, eax
0x180021c55  mov     [rsp+280h+var_260], r14d; int
0x180021c5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180021c61  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180021c66  lea     edx, [r14-2Ch]; unsigned __int64
0x180021c6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021c6f  mov     r9d, 1F0001h; dwDesiredAccess
0x180021c75  lea     rdx, [rsp+280h+Name]; lpName
0x180021c7a  xor     r8d, r8d; dwFlags
0x180021c7d  xor     ecx, ecx; lpMutexAttributes
0x180021c7f  call    cs:__imp_CreateMutexExW
0x180021c85  mov     rbx, rax
0x180021c88  test    rax, rax
0x180021c8b  jnz     short loc_180021C97
0x180021c8d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021c92  jmp     loc_180021F30
0x180021c97  xor     r8d, r8d; bAlertable
0x180021c9a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021c9d  mov     rcx, rbx; hHandle
0x180021ca0  call    cs:__imp_WaitForSingleObjectEx
0x180021ca6  cmp     eax, 102h
0x180021cab  jz      short loc_180021CBD
0x180021cad  test    eax, 0FFFFFF7Fh
0x180021cb2  jnz     loc_180021F7A
0x180021cb8  mov     rdi, rbx
0x180021cbb  jmp     short loc_180021CBF
0x180021cbd  xor     edi, edi
0x180021cbf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180021cc4  mov     [rsp+280h+hObject], 0
0x180021ccd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180021cd2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180021cd7  mov     esi, eax
0x180021cd9  test    eax, eax
0x180021cdb  jns     short loc_180021D5C
0x180021cdd  mov     rcx, [rbp+188h]; this
0x180021ce4  lea     r8, aWil; "wil"
0x180021ceb  mov     r9d, eax; char *
0x180021cee  mov     edx, 66h ; 'f'; void *
0x180021cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021cf8  mov     rcx, [rbp+188h]; this
0x180021cff  lea     r8, aWil; "wil"
0x180021d06  mov     r9d, esi; char *
0x180021d09  mov     edx, 6Fh ; 'o'; void *
0x180021d0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d13  mov     rcx, [rbp+188h]; this
0x180021d1a  lea     r8, aWil; "wil"
0x180021d21  mov     r9d, esi; char *
0x180021d24  mov     edx, 12Eh; void *
0x180021d29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d2e  test    rdi, rdi
0x180021d31  jz      short loc_180021D44
0x180021d33  mov     rcx, rdi; hMutex
0x180021d36  call    cs:__imp_ReleaseMutex
0x180021d3c  test    eax, eax
0x180021d3e  jz      loc_180021F87
0x180021d44  mov     rcx, rbx; hObject
0x180021d47  call    cs:__imp_CloseHandle
0x180021d4d  test    eax, eax
0x180021d4f  jz      loc_180021F99
0x180021d55  mov     eax, esi
0x180021d57  jmp     loc_180021F30
0x180021d5c  mov     rax, [rsp+280h+hObject]
0x180021d61  lea     rcx, ds:0[rax*4]
0x180021d69  test    rcx, rcx
0x180021d6c  jz      short loc_180021D7C
0x180021d6e  mov     [r15], rcx
0x180021d71  mov     eax, [rcx]
0x180021d73  inc     eax
0x180021d75  mov     [rcx], eax
0x180021d77  jmp     loc_180021F06
0x180021d7c  mov     rdx, r14; dwBytes
0x180021d7f  mov     qword ptr [r15], 0
0x180021d86  mov     ecx, 8; dwFlags
0x180021d8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180021d90  mov     r14, rax
0x180021d93  test    rax, rax
0x180021d96  jnz     short loc_180021DBD
0x180021d98  mov     rcx, [rbp+188h]; this
0x180021d9f  lea     r8, aWil; "wil"
0x180021da6  mov     esi, 8007000Eh
0x180021dab  mov     edx, 14Bh; void *
0x180021db0  mov     r9d, esi; char *
0x180021db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021db8  jmp     loc_180021E4F
0x180021dbd  xorps   xmm0, xmm0
0x180021dc0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180021dc6  test    r14b, 3
0x180021dca  jnz     loc_180021FAB
0x180021dd0  mov     r9, r14
0x180021dd3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180021dd8  shr     r9, 2; unsigned __int64
0x180021ddc  lea     rcx, [rsp+280h+hObject]; this
0x180021de1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180021de6  mov     esi, eax
0x180021de8  test    eax, eax
0x180021dea  jns     loc_180021E96
0x180021df0  mov     rcx, [rbp+188h]; this
0x180021df7  lea     r8, aWil; "wil"
0x180021dfe  mov     r9d, eax; char *
0x180021e01  mov     edx, 14Eh; void *
0x180021e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e0b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180021e10  test    rcx, rcx
0x180021e13  jz      short loc_180021E23
0x180021e15  call    cs:__imp_CloseHandle
0x180021e1b  test    eax, eax
0x180021e1d  jz      loc_180021FB1
0x180021e23  mov     rcx, [rsp+280h+hObject]; hObject
0x180021e28  test    rcx, rcx
0x180021e2b  jz      short loc_180021E3B
0x180021e2d  call    cs:__imp_CloseHandle
0x180021e33  test    eax, eax
0x180021e35  jz      loc_180021FC3
0x180021e3b  call    cs:__imp_GetProcessHeap
0x180021e41  mov     r8, r14; lpMem
0x180021e44  xor     edx, edx; dwFlags
0x180021e46  mov     rcx, rax; hHeap
0x180021e49  call    cs:__imp_HeapFree
0x180021e4f  mov     rcx, [rbp+188h]; this
0x180021e56  lea     r8, aWil; "wil"
0x180021e5d  mov     r9d, esi; char *
0x180021e60  mov     edx, 137h; void *
0x180021e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e6a  test    rdi, rdi
0x180021e6d  jz      short loc_180021E80
0x180021e6f  mov     rcx, rdi; hMutex
0x180021e72  call    cs:__imp_ReleaseMutex
0x180021e78  test    eax, eax
0x180021e7a  jz      loc_180021FD5
0x180021e80  mov     rcx, rbx; hObject
0x180021e83  call    cs:__imp_CloseHandle
0x180021e89  test    eax, eax
0x180021e8b  jz      loc_180021F68
0x180021e91  jmp     loc_180021D55
0x180021e96  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180021e9b  lea     rcx, [r14+28h]; void *
0x180021e9f  mov     dword ptr [r14], 1
0x180021ea6  xor     edx, edx; Val
0x180021ea8  mov     [r14+8], rbx
0x180021eac  mov     r8d, 108h; Size
0x180021eb2  movdqu  xmmword ptr [r14+10h], xmm0
0x180021eb8  call    memset_0
0x180021ebd  xor     eax, eax
0x180021ebf  lea     rcx, [r14+28h]; this
0x180021ec3  mov     [r14+20h], rax
0x180021ec7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180021ecc  lea     rbx, [r14+0E8h]
0x180021ed3  xor     r8d, r8d; Flags
0x180021ed6  mov     rcx, rbx; lpCriticalSection
0x180021ed9  xor     edx, edx; dwSpinCount
0x180021edb  call    cs:__imp_InitializeCriticalSectionEx
0x180021ee1  mov     qword ptr [rbx+28h], 0
0x180021ee9  mov     qword ptr [rbx+30h], 0
0x180021ef1  mov     qword ptr [rbx+38h], 0
0x180021ef9  mov     qword ptr [rbx+40h], 0
0x180021f01  xor     ebx, ebx
0x180021f03  mov     [r15], r14
0x180021f06  test    rdi, rdi
0x180021f09  jz      short loc_180021F1C
0x180021f0b  mov     rcx, rdi; hMutex
0x180021f0e  call    cs:__imp_ReleaseMutex
0x180021f14  test    eax, eax
0x180021f16  jz      loc_180021FE7
0x180021f1c  test    rbx, rbx
0x180021f1f  jz      short loc_180021F2E
0x180021f21  mov     rcx, rbx; hObject
0x180021f24  call    cs:__imp_CloseHandle
0x180021f2a  test    eax, eax
0x180021f2c  jz      short loc_180021F56
0x180021f2e  xor     eax, eax
0x180021f30  mov     rcx, [rbp+180h+var_30]
0x180021f37  xor     rcx, rsp; StackCookie
0x180021f3a  call    __security_check_cookie
0x180021f3f  mov     rbx, [rsp+280h+arg_10]
0x180021f47  add     rsp, 260h
0x180021f4e  pop     r15
0x180021f50  pop     r14
0x180021f52  pop     rdi
0x180021f53  pop     rsi
0x180021f54  pop     rbp
0x180021f55  retn
0x180021f56  mov     rcx, [rbp+188h]; this
0x180021f5d  mov     edx, 0A0Bh; void *
0x180021f62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021f68  mov     rcx, [rbp+188h]; this
0x180021f6f  mov     edx, 0A0Bh; void *
0x180021f74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021f7a  mov     rcx, [rbp+188h]; this
0x180021f81  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180021f87  mov     rcx, [rbp+188h]; this
0x180021f8e  mov     edx, 0A15h; void *
0x180021f93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021f99  mov     rcx, [rbp+188h]; this
0x180021fa0  mov     edx, 0A0Bh; void *
0x180021fa5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021fab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180021fb1  mov     rcx, [rbp+188h]; this
0x180021fb8  mov     edx, 0A0Bh; void *
0x180021fbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021fc3  mov     rcx, [rbp+188h]; this
0x180021fca  mov     edx, 0A0Bh; void *
0x180021fcf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021fd5  mov     rcx, [rbp+188h]; this
0x180021fdc  mov     edx, 0A15h; void *
0x180021fe1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021fe7  mov     rcx, [rbp+188h]; this
0x180021fee  mov     edx, 0A15h; void *
0x180021ff3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
