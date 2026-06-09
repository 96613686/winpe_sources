# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000896c`
- end: `0x180008d5d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180008d84`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x180004988`
- `0x180004c74`
- `0x1800052d8`
- `0x180005e58`
- `0x180006244`
- `0x180006c34`
- `0x180006d0c`
- `0x180007198`
- `0x1800071a8`
- `0x18000800c`
- `0x18000896c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008c72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008a04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008a04`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800089e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800089e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008c3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008c3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800089a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800089a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008be7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008be7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c88`

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
0x18000896c  mov     [rsp-8+arg_10], rbx
0x180008971  push    rbp
0x180008972  push    rsi
0x180008973  push    rdi
0x180008974  push    r14
0x180008976  push    r15
0x180008978  lea     rbp, [rsp-160h]
0x180008980  sub     rsp, 260h
0x180008987  mov     rax, cs:__security_cookie
0x18000898e  xor     rax, rsp
0x180008991  mov     [rbp+180h+var_30], rax
0x180008998  mov     r15, rdx
0x18000899b  mov     qword ptr [rdx], 0
0x1800089a2  mov     rbx, rcx
0x1800089a5  call    cs:__imp_GetCurrentProcessId
0x1800089ab  mov     r14d, 130h
0x1800089b1  mov     [rsp+280h+var_258], rbx
0x1800089b6  mov     r9d, eax
0x1800089b9  mov     [rsp+280h+var_260], r14d; int
0x1800089be  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800089c5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800089ca  lea     edx, [r14-2Ch]; unsigned __int64
0x1800089ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800089d3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800089d9  lea     rdx, [rsp+280h+Name]; lpName
0x1800089de  xor     r8d, r8d; dwFlags
0x1800089e1  xor     ecx, ecx; lpMutexAttributes
0x1800089e3  call    cs:__imp_CreateMutexExW
0x1800089e9  mov     rbx, rax
0x1800089ec  test    rax, rax
0x1800089ef  jnz     short loc_1800089FB
0x1800089f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800089f6  jmp     loc_180008C94
0x1800089fb  xor     r8d, r8d; bAlertable
0x1800089fe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008a01  mov     rcx, rbx; hHandle
0x180008a04  call    cs:__imp_WaitForSingleObjectEx
0x180008a0a  cmp     eax, 102h
0x180008a0f  jz      short loc_180008A21
0x180008a11  test    eax, 0FFFFFF7Fh
0x180008a16  jnz     loc_180008CDE
0x180008a1c  mov     rdi, rbx
0x180008a1f  jmp     short loc_180008A23
0x180008a21  xor     edi, edi
0x180008a23  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008a28  mov     [rsp+280h+hObject], 0
0x180008a31  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008a36  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008a3b  mov     esi, eax
0x180008a3d  test    eax, eax
0x180008a3f  jns     short loc_180008AC0
0x180008a41  mov     rcx, [rbp+188h]; this
0x180008a48  lea     r8, aWil; "wil"
0x180008a4f  mov     r9d, eax; char *
0x180008a52  mov     edx, 66h ; 'f'; void *
0x180008a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a5c  mov     rcx, [rbp+188h]; this
0x180008a63  lea     r8, aWil; "wil"
0x180008a6a  mov     r9d, esi; char *
0x180008a6d  mov     edx, 6Fh ; 'o'; void *
0x180008a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a77  mov     rcx, [rbp+188h]; this
0x180008a7e  lea     r8, aWil; "wil"
0x180008a85  mov     r9d, esi; char *
0x180008a88  mov     edx, 12Eh; void *
0x180008a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a92  test    rdi, rdi
0x180008a95  jz      short loc_180008AA8
0x180008a97  mov     rcx, rdi; hMutex
0x180008a9a  call    cs:__imp_ReleaseMutex
0x180008aa0  test    eax, eax
0x180008aa2  jz      loc_180008CEB
0x180008aa8  mov     rcx, rbx; hObject
0x180008aab  call    cs:__imp_CloseHandle
0x180008ab1  test    eax, eax
0x180008ab3  jz      loc_180008CFD
0x180008ab9  mov     eax, esi
0x180008abb  jmp     loc_180008C94
0x180008ac0  mov     rax, [rsp+280h+hObject]
0x180008ac5  lea     rcx, ds:0[rax*4]
0x180008acd  test    rcx, rcx
0x180008ad0  jz      short loc_180008AE0
0x180008ad2  mov     [r15], rcx
0x180008ad5  mov     eax, [rcx]
0x180008ad7  inc     eax
0x180008ad9  mov     [rcx], eax
0x180008adb  jmp     loc_180008C6A
0x180008ae0  mov     rdx, r14; dwBytes
0x180008ae3  mov     qword ptr [r15], 0
0x180008aea  mov     ecx, 8; dwFlags
0x180008aef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008af4  mov     r14, rax
0x180008af7  test    rax, rax
0x180008afa  jnz     short loc_180008B21
0x180008afc  mov     rcx, [rbp+188h]; this
0x180008b03  lea     r8, aWil; "wil"
0x180008b0a  mov     esi, 8007000Eh
0x180008b0f  mov     edx, 14Bh; void *
0x180008b14  mov     r9d, esi; char *
0x180008b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b1c  jmp     loc_180008BB3
0x180008b21  xorps   xmm0, xmm0
0x180008b24  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008b2a  test    r14b, 3
0x180008b2e  jnz     loc_180008D0F
0x180008b34  mov     r9, r14
0x180008b37  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008b3c  shr     r9, 2; unsigned __int64
0x180008b40  lea     rcx, [rsp+280h+hObject]; this
0x180008b45  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008b4a  mov     esi, eax
0x180008b4c  test    eax, eax
0x180008b4e  jns     loc_180008BFA
0x180008b54  mov     rcx, [rbp+188h]; this
0x180008b5b  lea     r8, aWil; "wil"
0x180008b62  mov     r9d, eax; char *
0x180008b65  mov     edx, 14Eh; void *
0x180008b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b6f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008b74  test    rcx, rcx
0x180008b77  jz      short loc_180008B87
0x180008b79  call    cs:__imp_CloseHandle
0x180008b7f  test    eax, eax
0x180008b81  jz      loc_180008D15
0x180008b87  mov     rcx, [rsp+280h+hObject]; hObject
0x180008b8c  test    rcx, rcx
0x180008b8f  jz      short loc_180008B9F
0x180008b91  call    cs:__imp_CloseHandle
0x180008b97  test    eax, eax
0x180008b99  jz      loc_180008D27
0x180008b9f  call    cs:__imp_GetProcessHeap
0x180008ba5  mov     r8, r14; lpMem
0x180008ba8  xor     edx, edx; dwFlags
0x180008baa  mov     rcx, rax; hHeap
0x180008bad  call    cs:__imp_HeapFree
0x180008bb3  mov     rcx, [rbp+188h]; this
0x180008bba  lea     r8, aWil; "wil"
0x180008bc1  mov     r9d, esi; char *
0x180008bc4  mov     edx, 137h; void *
0x180008bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bce  test    rdi, rdi
0x180008bd1  jz      short loc_180008BE4
0x180008bd3  mov     rcx, rdi; hMutex
0x180008bd6  call    cs:__imp_ReleaseMutex
0x180008bdc  test    eax, eax
0x180008bde  jz      loc_180008D39
0x180008be4  mov     rcx, rbx; hObject
0x180008be7  call    cs:__imp_CloseHandle
0x180008bed  test    eax, eax
0x180008bef  jz      loc_180008CCC
0x180008bf5  jmp     loc_180008AB9
0x180008bfa  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008bff  lea     rcx, [r14+28h]; void *
0x180008c03  mov     dword ptr [r14], 1
0x180008c0a  xor     edx, edx; Val
0x180008c0c  mov     [r14+8], rbx
0x180008c10  mov     r8d, 108h; Size
0x180008c16  movdqu  xmmword ptr [r14+10h], xmm0
0x180008c1c  call    memset_0
0x180008c21  xor     eax, eax
0x180008c23  lea     rcx, [r14+28h]; this
0x180008c27  mov     [r14+20h], rax
0x180008c2b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008c30  lea     rbx, [r14+0E8h]
0x180008c37  xor     r8d, r8d; Flags
0x180008c3a  mov     rcx, rbx; lpCriticalSection
0x180008c3d  xor     edx, edx; dwSpinCount
0x180008c3f  call    cs:__imp_InitializeCriticalSectionEx
0x180008c45  mov     qword ptr [rbx+28h], 0
0x180008c4d  mov     qword ptr [rbx+30h], 0
0x180008c55  mov     qword ptr [rbx+38h], 0
0x180008c5d  mov     qword ptr [rbx+40h], 0
0x180008c65  xor     ebx, ebx
0x180008c67  mov     [r15], r14
0x180008c6a  test    rdi, rdi
0x180008c6d  jz      short loc_180008C80
0x180008c6f  mov     rcx, rdi; hMutex
0x180008c72  call    cs:__imp_ReleaseMutex
0x180008c78  test    eax, eax
0x180008c7a  jz      loc_180008D4B
0x180008c80  test    rbx, rbx
0x180008c83  jz      short loc_180008C92
0x180008c85  mov     rcx, rbx; hObject
0x180008c88  call    cs:__imp_CloseHandle
0x180008c8e  test    eax, eax
0x180008c90  jz      short loc_180008CBA
0x180008c92  xor     eax, eax
0x180008c94  mov     rcx, [rbp+180h+var_30]
0x180008c9b  xor     rcx, rsp; StackCookie
0x180008c9e  call    __security_check_cookie
0x180008ca3  mov     rbx, [rsp+280h+arg_10]
0x180008cab  add     rsp, 260h
0x180008cb2  pop     r15
0x180008cb4  pop     r14
0x180008cb6  pop     rdi
0x180008cb7  pop     rsi
0x180008cb8  pop     rbp
0x180008cb9  retn
0x180008cba  mov     rcx, [rbp+188h]; this
0x180008cc1  mov     edx, 0A0Bh; void *
0x180008cc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ccc  mov     rcx, [rbp+188h]; this
0x180008cd3  mov     edx, 0A0Bh; void *
0x180008cd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008cde  mov     rcx, [rbp+188h]; this
0x180008ce5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008ceb  mov     rcx, [rbp+188h]; this
0x180008cf2  mov     edx, 0A15h; void *
0x180008cf7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008cfd  mov     rcx, [rbp+188h]; this
0x180008d04  mov     edx, 0A0Bh; void *
0x180008d09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d0f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008d15  mov     rcx, [rbp+188h]; this
0x180008d1c  mov     edx, 0A0Bh; void *
0x180008d21  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d27  mov     rcx, [rbp+188h]; this
0x180008d2e  mov     edx, 0A0Bh; void *
0x180008d33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d39  mov     rcx, [rbp+188h]; this
0x180008d40  mov     edx, 0A15h; void *
0x180008d45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008d4b  mov     rcx, [rbp+188h]; this
0x180008d52  mov     edx, 0A15h; void *
0x180008d57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
