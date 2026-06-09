# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000d1ac`
- end: `0x14000d5a2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000ec64`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140007920`
- `0x140007c44`
- `0x140008298`
- `0x140008f98`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14000a1dc`
- `0x14000a698`
- `0x14000a6a8`
- `0x14000bec0`
- `0x14000d1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d2da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d416`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d4b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d2da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d416`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000d4b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000d244`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000d244`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d223`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d223`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000d47f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000d47f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d3ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d3ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d3df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d3df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000d1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000d1e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d2eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d3b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d3d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d2eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d3b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d3d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4c8`

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
  bool v9; // dl
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
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x14000d1ac  mov     [rsp-8+arg_10], rbx
0x14000d1b1  push    rbp
0x14000d1b2  push    rsi
0x14000d1b3  push    rdi
0x14000d1b4  push    r14
0x14000d1b6  push    r15
0x14000d1b8  lea     rbp, [rsp-160h]
0x14000d1c0  sub     rsp, 260h
0x14000d1c7  mov     rax, cs:__security_cookie
0x14000d1ce  xor     rax, rsp
0x14000d1d1  mov     [rbp+180h+var_30], rax
0x14000d1d8  mov     r15, rdx
0x14000d1db  mov     qword ptr [rdx], 0
0x14000d1e2  mov     rbx, rcx
0x14000d1e5  call    cs:__imp_GetCurrentProcessId
0x14000d1eb  mov     r14d, 130h
0x14000d1f1  mov     [rsp+280h+var_258], rbx
0x14000d1f6  mov     r9d, eax
0x14000d1f9  mov     [rsp+280h+var_260], r14d; int
0x14000d1fe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000d205  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d20a  lea     edx, [r14-2Ch]; unsigned __int64
0x14000d20e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d213  mov     r9d, 1F0001h; dwDesiredAccess
0x14000d219  lea     rdx, [rsp+280h+Name]; lpName
0x14000d21e  xor     r8d, r8d; dwFlags
0x14000d221  xor     ecx, ecx; lpMutexAttributes
0x14000d223  call    cs:__imp_CreateMutexExW
0x14000d229  mov     rbx, rax
0x14000d22c  test    rax, rax
0x14000d22f  jnz     short loc_14000D23B
0x14000d231  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000d236  jmp     loc_14000D4D4
0x14000d23b  xor     r8d, r8d; bAlertable
0x14000d23e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000d241  mov     rcx, rbx; hHandle
0x14000d244  call    cs:__imp_WaitForSingleObjectEx
0x14000d24a  cmp     eax, 102h
0x14000d24f  jz      short loc_14000D261
0x14000d251  test    eax, 0FFFFFF7Fh
0x14000d256  jnz     loc_14000D51E
0x14000d25c  mov     rdi, rbx
0x14000d25f  jmp     short loc_14000D263
0x14000d261  xor     edi, edi
0x14000d263  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000d268  mov     [rsp+280h+hObject], 0
0x14000d271  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d276  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000d27b  mov     esi, eax
0x14000d27d  test    eax, eax
0x14000d27f  jns     short loc_14000D300
0x14000d281  mov     rcx, [rbp+188h]; this
0x14000d288  lea     r8, aWil; "wil"
0x14000d28f  mov     r9d, eax; char *
0x14000d292  mov     edx, 66h ; 'f'; void *
0x14000d297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d29c  mov     rcx, [rbp+188h]; this
0x14000d2a3  lea     r8, aWil; "wil"
0x14000d2aa  mov     r9d, esi; char *
0x14000d2ad  mov     edx, 6Fh ; 'o'; void *
0x14000d2b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d2b7  mov     rcx, [rbp+188h]; this
0x14000d2be  lea     r8, aWil; "wil"
0x14000d2c5  mov     r9d, esi; char *
0x14000d2c8  mov     edx, 12Eh; void *
0x14000d2cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d2d2  test    rdi, rdi
0x14000d2d5  jz      short loc_14000D2E8
0x14000d2d7  mov     rcx, rdi; hMutex
0x14000d2da  call    cs:__imp_ReleaseMutex
0x14000d2e0  test    eax, eax
0x14000d2e2  jz      loc_14000D530
0x14000d2e8  mov     rcx, rbx; hObject
0x14000d2eb  call    cs:__imp_CloseHandle
0x14000d2f1  test    eax, eax
0x14000d2f3  jz      loc_14000D542
0x14000d2f9  mov     eax, esi
0x14000d2fb  jmp     loc_14000D4D4
0x14000d300  mov     rax, [rsp+280h+hObject]
0x14000d305  lea     rcx, ds:0[rax*4]
0x14000d30d  test    rcx, rcx
0x14000d310  jz      short loc_14000D320
0x14000d312  mov     [r15], rcx
0x14000d315  mov     eax, [rcx]
0x14000d317  inc     eax
0x14000d319  mov     [rcx], eax
0x14000d31b  jmp     loc_14000D4AA
0x14000d320  mov     rdx, r14; dwBytes
0x14000d323  mov     qword ptr [r15], 0
0x14000d32a  mov     ecx, 8; dwFlags
0x14000d32f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000d334  mov     r14, rax
0x14000d337  test    rax, rax
0x14000d33a  jnz     short loc_14000D361
0x14000d33c  mov     rcx, [rbp+188h]; this
0x14000d343  lea     r8, aWil; "wil"
0x14000d34a  mov     esi, 8007000Eh
0x14000d34f  mov     edx, 14Bh; void *
0x14000d354  mov     r9d, esi; char *
0x14000d357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d35c  jmp     loc_14000D3F3
0x14000d361  xorps   xmm0, xmm0
0x14000d364  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000d36a  test    r14b, 3
0x14000d36e  jnz     loc_14000D554
0x14000d374  mov     r9, r14
0x14000d377  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000d37c  shr     r9, 2; unsigned __int64
0x14000d380  lea     rcx, [rsp+280h+hObject]; this
0x14000d385  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000d38a  mov     esi, eax
0x14000d38c  test    eax, eax
0x14000d38e  jns     loc_14000D43A
0x14000d394  mov     rcx, [rbp+188h]; this
0x14000d39b  lea     r8, aWil; "wil"
0x14000d3a2  mov     r9d, eax; char *
0x14000d3a5  mov     edx, 14Eh; void *
0x14000d3aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d3af  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000d3b4  test    rcx, rcx
0x14000d3b7  jz      short loc_14000D3C7
0x14000d3b9  call    cs:__imp_CloseHandle
0x14000d3bf  test    eax, eax
0x14000d3c1  jz      loc_14000D55A
0x14000d3c7  mov     rcx, [rsp+280h+hObject]; hObject
0x14000d3cc  test    rcx, rcx
0x14000d3cf  jz      short loc_14000D3DF
0x14000d3d1  call    cs:__imp_CloseHandle
0x14000d3d7  test    eax, eax
0x14000d3d9  jz      loc_14000D56C
0x14000d3df  call    cs:__imp_GetProcessHeap
0x14000d3e5  mov     r8, r14; lpMem
0x14000d3e8  xor     edx, edx; dwFlags
0x14000d3ea  mov     rcx, rax; hHeap
0x14000d3ed  call    cs:__imp_HeapFree
0x14000d3f3  mov     rcx, [rbp+188h]; this
0x14000d3fa  lea     r8, aWil; "wil"
0x14000d401  mov     r9d, esi; char *
0x14000d404  mov     edx, 137h; void *
0x14000d409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d40e  test    rdi, rdi
0x14000d411  jz      short loc_14000D424
0x14000d413  mov     rcx, rdi; hMutex
0x14000d416  call    cs:__imp_ReleaseMutex
0x14000d41c  test    eax, eax
0x14000d41e  jz      loc_14000D57E
0x14000d424  mov     rcx, rbx; hObject
0x14000d427  call    cs:__imp_CloseHandle
0x14000d42d  test    eax, eax
0x14000d42f  jz      loc_14000D50C
0x14000d435  jmp     loc_14000D2F9
0x14000d43a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000d43f  lea     rcx, [r14+28h]; void *
0x14000d443  mov     dword ptr [r14], 1
0x14000d44a  xor     edx, edx; Val
0x14000d44c  mov     [r14+8], rbx
0x14000d450  mov     r8d, 108h; Size
0x14000d456  movdqu  xmmword ptr [r14+10h], xmm0
0x14000d45c  call    memset_0
0x14000d461  xor     eax, eax
0x14000d463  lea     rcx, [r14+28h]; this
0x14000d467  mov     [r14+20h], rax
0x14000d46b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000d470  lea     rbx, [r14+0E8h]
0x14000d477  xor     r8d, r8d; Flags
0x14000d47a  mov     rcx, rbx; lpCriticalSection
0x14000d47d  xor     edx, edx; dwSpinCount
0x14000d47f  call    cs:__imp_InitializeCriticalSectionEx
0x14000d485  mov     qword ptr [rbx+28h], 0
0x14000d48d  mov     qword ptr [rbx+30h], 0
0x14000d495  mov     qword ptr [rbx+38h], 0
0x14000d49d  mov     qword ptr [rbx+40h], 0
0x14000d4a5  xor     ebx, ebx
0x14000d4a7  mov     [r15], r14
0x14000d4aa  test    rdi, rdi
0x14000d4ad  jz      short loc_14000D4C0
0x14000d4af  mov     rcx, rdi; hMutex
0x14000d4b2  call    cs:__imp_ReleaseMutex
0x14000d4b8  test    eax, eax
0x14000d4ba  jz      loc_14000D590
0x14000d4c0  test    rbx, rbx
0x14000d4c3  jz      short loc_14000D4D2
0x14000d4c5  mov     rcx, rbx; hObject
0x14000d4c8  call    cs:__imp_CloseHandle
0x14000d4ce  test    eax, eax
0x14000d4d0  jz      short loc_14000D4FA
0x14000d4d2  xor     eax, eax
0x14000d4d4  mov     rcx, [rbp+180h+var_30]
0x14000d4db  xor     rcx, rsp; StackCookie
0x14000d4de  call    __security_check_cookie
0x14000d4e3  mov     rbx, [rsp+280h+arg_10]
0x14000d4eb  add     rsp, 260h
0x14000d4f2  pop     r15
0x14000d4f4  pop     r14
0x14000d4f6  pop     rdi
0x14000d4f7  pop     rsi
0x14000d4f8  pop     rbp
0x14000d4f9  retn
0x14000d4fa  mov     rcx, [rbp+188h]; this
0x14000d501  mov     edx, 0A0Bh; void *
0x14000d506  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d50c  mov     rcx, [rbp+188h]; this
0x14000d513  mov     edx, 0A0Bh; void *
0x14000d518  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d51e  mov     rcx, [rbp+188h]; this
0x14000d525  mov     edx, 0E01h; void *
0x14000d52a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000d530  mov     rcx, [rbp+188h]; this
0x14000d537  mov     edx, 0A15h; void *
0x14000d53c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d542  mov     rcx, [rbp+188h]; this
0x14000d549  mov     edx, 0A0Bh; void *
0x14000d54e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d554  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000d55a  mov     rcx, [rbp+188h]; this
0x14000d561  mov     edx, 0A0Bh; void *
0x14000d566  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d56c  mov     rcx, [rbp+188h]; this
0x14000d573  mov     edx, 0A0Bh; void *
0x14000d578  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d57e  mov     rcx, [rbp+188h]; this
0x14000d585  mov     edx, 0A15h; void *
0x14000d58a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d590  mov     rcx, [rbp+188h]; this
0x14000d597  mov     edx, 0A15h; void *
0x14000d59c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
