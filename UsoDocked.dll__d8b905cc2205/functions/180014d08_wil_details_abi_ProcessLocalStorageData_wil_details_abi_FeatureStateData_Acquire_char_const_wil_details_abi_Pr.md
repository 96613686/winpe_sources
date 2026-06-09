# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180014d08`
- end: `0x1800150f9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180015584`

## callees

- `0x180007660`
- `0x18000856c`
- `0x180013e4c`
- `0x180014d08`
- `0x180015114`
- `0x1800157f4`
- `0x180016128`
- `0x180016bd8`
- `0x1800183f4`
- `0x180018f7c`
- `0x1800193fc`
- `0x180019e38`
- `0x180019e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014da0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014da0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180014fdb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180014fdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014f72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001500e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014e36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014f72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001500e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014d7f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014d41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015024`

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
0x180014d08  mov     [rsp-8+arg_10], rbx
0x180014d0d  push    rbp
0x180014d0e  push    rsi
0x180014d0f  push    rdi
0x180014d10  push    r14
0x180014d12  push    r15
0x180014d14  lea     rbp, [rsp-160h]
0x180014d1c  sub     rsp, 260h
0x180014d23  mov     rax, cs:__security_cookie
0x180014d2a  xor     rax, rsp
0x180014d2d  mov     [rbp+180h+var_30], rax
0x180014d34  mov     r15, rdx
0x180014d37  mov     qword ptr [rdx], 0
0x180014d3e  mov     rbx, rcx
0x180014d41  call    cs:__imp_GetCurrentProcessId
0x180014d47  mov     r14d, 130h
0x180014d4d  mov     [rsp+280h+var_258], rbx
0x180014d52  mov     r9d, eax
0x180014d55  mov     [rsp+280h+var_260], r14d; int
0x180014d5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014d61  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014d66  lea     edx, [r14-2Ch]; unsigned __int64
0x180014d6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014d6f  mov     r9d, 1F0001h; dwDesiredAccess
0x180014d75  lea     rdx, [rsp+280h+Name]; lpName
0x180014d7a  xor     r8d, r8d; dwFlags
0x180014d7d  xor     ecx, ecx; lpMutexAttributes
0x180014d7f  call    cs:__imp_CreateMutexExW
0x180014d85  mov     rbx, rax
0x180014d88  test    rax, rax
0x180014d8b  jnz     short loc_180014D97
0x180014d8d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014d92  jmp     loc_180015030
0x180014d97  xor     r8d, r8d; bAlertable
0x180014d9a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014d9d  mov     rcx, rbx; hHandle
0x180014da0  call    cs:__imp_WaitForSingleObjectEx
0x180014da6  cmp     eax, 102h
0x180014dab  jz      short loc_180014DBD
0x180014dad  test    eax, 0FFFFFF7Fh
0x180014db2  jnz     loc_18001507A
0x180014db8  mov     rdi, rbx
0x180014dbb  jmp     short loc_180014DBF
0x180014dbd  xor     edi, edi
0x180014dbf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180014dc4  mov     [rsp+280h+hObject], 0
0x180014dcd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014dd2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180014dd7  mov     esi, eax
0x180014dd9  test    eax, eax
0x180014ddb  jns     short loc_180014E5C
0x180014ddd  mov     rcx, [rbp+188h]; this
0x180014de4  lea     r8, aWil; "wil"
0x180014deb  mov     r9d, eax; char *
0x180014dee  mov     edx, 66h ; 'f'; void *
0x180014df3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014df8  mov     rcx, [rbp+188h]; this
0x180014dff  lea     r8, aWil; "wil"
0x180014e06  mov     r9d, esi; char *
0x180014e09  mov     edx, 6Fh ; 'o'; void *
0x180014e0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e13  mov     rcx, [rbp+188h]; this
0x180014e1a  lea     r8, aWil; "wil"
0x180014e21  mov     r9d, esi; char *
0x180014e24  mov     edx, 12Eh; void *
0x180014e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e2e  test    rdi, rdi
0x180014e31  jz      short loc_180014E44
0x180014e33  mov     rcx, rdi; hMutex
0x180014e36  call    cs:__imp_ReleaseMutex
0x180014e3c  test    eax, eax
0x180014e3e  jz      loc_180015087
0x180014e44  mov     rcx, rbx; hObject
0x180014e47  call    cs:__imp_CloseHandle
0x180014e4d  test    eax, eax
0x180014e4f  jz      loc_180015099
0x180014e55  mov     eax, esi
0x180014e57  jmp     loc_180015030
0x180014e5c  mov     rax, [rsp+280h+hObject]
0x180014e61  lea     rcx, ds:0[rax*4]
0x180014e69  test    rcx, rcx
0x180014e6c  jz      short loc_180014E7C
0x180014e6e  mov     [r15], rcx
0x180014e71  mov     eax, [rcx]
0x180014e73  inc     eax
0x180014e75  mov     [rcx], eax
0x180014e77  jmp     loc_180015006
0x180014e7c  mov     rdx, r14; dwBytes
0x180014e7f  mov     qword ptr [r15], 0
0x180014e86  mov     ecx, 8; dwFlags
0x180014e8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014e90  mov     r14, rax
0x180014e93  test    rax, rax
0x180014e96  jnz     short loc_180014EBD
0x180014e98  mov     rcx, [rbp+188h]; this
0x180014e9f  lea     r8, aWil; "wil"
0x180014ea6  mov     esi, 8007000Eh
0x180014eab  mov     edx, 14Bh; void *
0x180014eb0  mov     r9d, esi; char *
0x180014eb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014eb8  jmp     loc_180014F4F
0x180014ebd  xorps   xmm0, xmm0
0x180014ec0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180014ec6  test    r14b, 3
0x180014eca  jnz     loc_1800150AB
0x180014ed0  mov     r9, r14
0x180014ed3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180014ed8  shr     r9, 2; unsigned __int64
0x180014edc  lea     rcx, [rsp+280h+hObject]; this
0x180014ee1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180014ee6  mov     esi, eax
0x180014ee8  test    eax, eax
0x180014eea  jns     loc_180014F96
0x180014ef0  mov     rcx, [rbp+188h]; this
0x180014ef7  lea     r8, aWil; "wil"
0x180014efe  mov     r9d, eax; char *
0x180014f01  mov     edx, 14Eh; void *
0x180014f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f0b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180014f10  test    rcx, rcx
0x180014f13  jz      short loc_180014F23
0x180014f15  call    cs:__imp_CloseHandle
0x180014f1b  test    eax, eax
0x180014f1d  jz      loc_1800150B1
0x180014f23  mov     rcx, [rsp+280h+hObject]; hObject
0x180014f28  test    rcx, rcx
0x180014f2b  jz      short loc_180014F3B
0x180014f2d  call    cs:__imp_CloseHandle
0x180014f33  test    eax, eax
0x180014f35  jz      loc_1800150C3
0x180014f3b  call    cs:__imp_GetProcessHeap
0x180014f41  mov     r8, r14; lpMem
0x180014f44  xor     edx, edx; dwFlags
0x180014f46  mov     rcx, rax; hHeap
0x180014f49  call    cs:__imp_HeapFree
0x180014f4f  mov     rcx, [rbp+188h]; this
0x180014f56  lea     r8, aWil; "wil"
0x180014f5d  mov     r9d, esi; char *
0x180014f60  mov     edx, 137h; void *
0x180014f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f6a  test    rdi, rdi
0x180014f6d  jz      short loc_180014F80
0x180014f6f  mov     rcx, rdi; hMutex
0x180014f72  call    cs:__imp_ReleaseMutex
0x180014f78  test    eax, eax
0x180014f7a  jz      loc_1800150D5
0x180014f80  mov     rcx, rbx; hObject
0x180014f83  call    cs:__imp_CloseHandle
0x180014f89  test    eax, eax
0x180014f8b  jz      loc_180015068
0x180014f91  jmp     loc_180014E55
0x180014f96  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180014f9b  lea     rcx, [r14+28h]; void *
0x180014f9f  mov     dword ptr [r14], 1
0x180014fa6  xor     edx, edx; Val
0x180014fa8  mov     [r14+8], rbx
0x180014fac  mov     r8d, 108h; Size
0x180014fb2  movdqu  xmmword ptr [r14+10h], xmm0
0x180014fb8  call    memset_0
0x180014fbd  xor     eax, eax
0x180014fbf  lea     rcx, [r14+28h]; this
0x180014fc3  mov     [r14+20h], rax
0x180014fc7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180014fcc  lea     rbx, [r14+0E8h]
0x180014fd3  xor     r8d, r8d; Flags
0x180014fd6  mov     rcx, rbx; lpCriticalSection
0x180014fd9  xor     edx, edx; dwSpinCount
0x180014fdb  call    cs:__imp_InitializeCriticalSectionEx
0x180014fe1  mov     qword ptr [rbx+28h], 0
0x180014fe9  mov     qword ptr [rbx+30h], 0
0x180014ff1  mov     qword ptr [rbx+38h], 0
0x180014ff9  mov     qword ptr [rbx+40h], 0
0x180015001  xor     ebx, ebx
0x180015003  mov     [r15], r14
0x180015006  test    rdi, rdi
0x180015009  jz      short loc_18001501C
0x18001500b  mov     rcx, rdi; hMutex
0x18001500e  call    cs:__imp_ReleaseMutex
0x180015014  test    eax, eax
0x180015016  jz      loc_1800150E7
0x18001501c  test    rbx, rbx
0x18001501f  jz      short loc_18001502E
0x180015021  mov     rcx, rbx; hObject
0x180015024  call    cs:__imp_CloseHandle
0x18001502a  test    eax, eax
0x18001502c  jz      short loc_180015056
0x18001502e  xor     eax, eax
0x180015030  mov     rcx, [rbp+180h+var_30]
0x180015037  xor     rcx, rsp; StackCookie
0x18001503a  call    __security_check_cookie
0x18001503f  mov     rbx, [rsp+280h+arg_10]
0x180015047  add     rsp, 260h
0x18001504e  pop     r15
0x180015050  pop     r14
0x180015052  pop     rdi
0x180015053  pop     rsi
0x180015054  pop     rbp
0x180015055  retn
0x180015056  mov     rcx, [rbp+188h]; this
0x18001505d  mov     edx, 0A0Bh; void *
0x180015062  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015068  mov     rcx, [rbp+188h]; this
0x18001506f  mov     edx, 0A0Bh; void *
0x180015074  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001507a  mov     rcx, [rbp+188h]; this
0x180015081  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180015087  mov     rcx, [rbp+188h]; this
0x18001508e  mov     edx, 0A15h; void *
0x180015093  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015099  mov     rcx, [rbp+188h]; this
0x1800150a0  mov     edx, 0A0Bh; void *
0x1800150a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800150b1  mov     rcx, [rbp+188h]; this
0x1800150b8  mov     edx, 0A0Bh; void *
0x1800150bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150c3  mov     rcx, [rbp+188h]; this
0x1800150ca  mov     edx, 0A0Bh; void *
0x1800150cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150d5  mov     rcx, [rbp+188h]; this
0x1800150dc  mov     edx, 0A15h; void *
0x1800150e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150e7  mov     rcx, [rbp+188h]; this
0x1800150ee  mov     edx, 0A15h; void *
0x1800150f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
