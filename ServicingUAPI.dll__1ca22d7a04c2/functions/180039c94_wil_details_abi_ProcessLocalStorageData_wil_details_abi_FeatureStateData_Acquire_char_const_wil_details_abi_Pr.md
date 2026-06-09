# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180039c94`
- end: `0x18003a0ab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18003a0b4`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800098a4`
- `0x180009f28`
- `0x18000a180`
- `0x18000a774`
- `0x18000b54c`
- `0x18000ba40`
- `0x18000c350`
- `0x18000c488`
- `0x18000c9f4`
- `0x1800396f0`
- `0x180039c94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039cd7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180039d1c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180039d1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039d44`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039d44`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180039fb6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180039fb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039de5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039de5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039ff9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ed6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ed6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a01c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a01c`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+28h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-E0h]
  unsigned __int64 v36; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C8h]
  __int64 v38; // [rsp+48h] [rbp-C0h]
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v38 = -2;
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
  v36 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36);
  if ( 4 * v36 )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  v36 = 0;
  v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  *((_QWORD *)v22 + 2) = v36;
  v36 = 0;
  *((_QWORD *)v22 + 3) = v37;
  v37 = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180039c94  mov     rax, rsp
0x180039c97  push    rbp
0x180039c98  push    rsi
0x180039c99  push    rdi
0x180039c9a  push    r14
0x180039c9c  push    r15
0x180039c9e  lea     rbp, [rax-198h]
0x180039ca5  sub     rsp, 270h
0x180039cac  mov     [rsp+290h+var_250], 0FFFFFFFFFFFFFFFEh
0x180039cb5  mov     [rax+18h], rbx
0x180039cb9  mov     rax, cs:__security_cookie
0x180039cc0  xor     rax, rsp
0x180039cc3  mov     [rbp+190h+var_30], rax
0x180039cca  mov     r15, rdx
0x180039ccd  mov     rbx, rcx
0x180039cd0  mov     qword ptr [rdx], 0
0x180039cd7  call    cs:__imp_GetCurrentProcessId
0x180039cde  nop     dword ptr [rax+rax+00h]
0x180039ce3  mov     r9d, eax
0x180039ce6  mov     [rsp+290h+var_268], rbx
0x180039ceb  mov     r14d, 130h
0x180039cf1  mov     [rsp+290h+var_270], r14d; int
0x180039cf6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180039cfd  lea     edx, [r14-2Ch]; unsigned __int64
0x180039d01  lea     rcx, [rsp+290h+Name]; wchar_t *
0x180039d06  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180039d0b  nop
0x180039d0c  mov     r9d, 1F0001h; dwDesiredAccess
0x180039d12  xor     r8d, r8d; dwFlags
0x180039d15  lea     rdx, [rsp+290h+Name]; lpName
0x180039d1a  xor     ecx, ecx; lpMutexAttributes
0x180039d1c  call    cs:__imp_CreateMutexExW
0x180039d23  nop     dword ptr [rax+rax+00h]
0x180039d28  mov     rbx, rax
0x180039d2b  test    rax, rax
0x180039d2e  jnz     short loc_180039D3B
0x180039d30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180039d35  nop
0x180039d36  jmp     loc_18003A035
0x180039d3b  xor     r8d, r8d; bAlertable
0x180039d3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180039d41  mov     rcx, rbx; hHandle
0x180039d44  call    cs:__imp_WaitForSingleObjectEx
0x180039d4b  nop     dword ptr [rax+rax+00h]
0x180039d50  cmp     eax, 102h
0x180039d55  jz      short loc_180039D67
0x180039d57  test    eax, 0FFFFFF7Fh
0x180039d5c  jnz     loc_18003A067
0x180039d62  mov     rdi, rbx
0x180039d65  jmp     short loc_180039D69
0x180039d67  xor     edi, edi
0x180039d69  mov     [rsp+290h+var_260], 0
0x180039d72  lea     r8, [rsp+290h+var_260]; unsigned __int64 *
0x180039d77  lea     rcx, [rsp+290h+Name]; wchar_t *
0x180039d7c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180039d81  mov     esi, eax
0x180039d83  test    eax, eax
0x180039d85  jns     loc_180039E25
0x180039d8b  mov     rcx, [rbp+198h]; this
0x180039d92  mov     r9d, eax; char *
0x180039d95  lea     r8, aWil; "wil"
0x180039d9c  mov     edx, 66h ; 'f'; void *
0x180039da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039da6  mov     rcx, [rbp+198h]; this
0x180039dad  mov     r9d, esi; char *
0x180039db0  lea     r8, aWil; "wil"
0x180039db7  mov     edx, 6Fh ; 'o'; void *
0x180039dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039dc1  mov     rcx, [rbp+198h]; this
0x180039dc8  mov     r9d, esi; char *
0x180039dcb  lea     r8, aWil; "wil"
0x180039dd2  mov     edx, 12Eh; void *
0x180039dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ddc  nop
0x180039ddd  test    rdi, rdi
0x180039de0  jz      short loc_180039E00
0x180039de2  mov     rcx, rdi; hMutex
0x180039de5  call    cs:__imp_ReleaseMutex
0x180039dec  nop     dword ptr [rax+rax+00h]
0x180039df1  mov     rcx, [rbp+198h]; this
0x180039df8  test    eax, eax
0x180039dfa  jz      loc_18003A074
0x180039e00  mov     rcx, rbx; hObject
0x180039e03  call    cs:__imp_CloseHandle
0x180039e0a  nop     dword ptr [rax+rax+00h]
0x180039e0f  mov     rcx, [rbp+198h]; this
0x180039e16  test    eax, eax
0x180039e18  jz      loc_18003A07F
0x180039e1e  mov     eax, esi
0x180039e20  jmp     loc_18003A035
0x180039e25  mov     rax, [rsp+290h+var_260]
0x180039e2a  lea     rcx, ds:0[rax*4]
0x180039e32  test    rcx, rcx
0x180039e35  jz      short loc_180039E45
0x180039e37  mov     [r15], rcx
0x180039e3a  mov     eax, [rcx]
0x180039e3c  inc     eax
0x180039e3e  mov     [rcx], eax
0x180039e40  jmp     loc_180039FF1
0x180039e45  mov     qword ptr [r15], 0
0x180039e4c  mov     rdx, r14; dwBytes
0x180039e4f  mov     ecx, 8; dwFlags
0x180039e54  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180039e59  mov     r14, rax
0x180039e5c  test    rax, rax
0x180039e5f  jnz     short loc_180039E83
0x180039e61  mov     rcx, [rbp+198h]; this
0x180039e68  mov     esi, 8007000Eh
0x180039e6d  mov     r9d, esi; char *
0x180039e70  lea     r8, aWil; "wil"
0x180039e77  mov     edx, 14Bh; void *
0x180039e7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e81  jmp     short loc_180039EF6
0x180039e83  mov     [rsp+290h+var_260], 0
0x180039e8c  mov     [rsp+290h+var_258], 0
0x180039e95  mov     r8, r14; void *
0x180039e98  lea     rdx, [rsp+290h+Name]; wchar_t *
0x180039e9d  lea     rcx, [rsp+290h+var_260]; this
0x180039ea2  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEB_WPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(wchar_t const *,void *)
0x180039ea7  mov     esi, eax
0x180039ea9  test    eax, eax
0x180039eab  jns     loc_180039F58
0x180039eb1  mov     rcx, [rbp+198h]; this
0x180039eb8  mov     r9d, eax; char *
0x180039ebb  lea     r8, aWil; "wil"
0x180039ec2  mov     edx, 14Eh; void *
0x180039ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ecc  lea     rcx, [rsp+290h+var_260]; this
0x180039ed1  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180039ed6  call    cs:__imp_GetProcessHeap
0x180039edd  nop     dword ptr [rax+rax+00h]
0x180039ee2  mov     rcx, rax; hHeap
0x180039ee5  mov     r8, r14; lpMem
0x180039ee8  xor     edx, edx; dwFlags
0x180039eea  call    cs:__imp_HeapFree
0x180039ef1  nop     dword ptr [rax+rax+00h]
0x180039ef6  mov     rcx, [rbp+198h]; this
0x180039efd  mov     r9d, esi; char *
0x180039f00  lea     r8, aWil; "wil"
0x180039f07  mov     edx, 137h; void *
0x180039f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f11  nop
0x180039f12  test    rdi, rdi
0x180039f15  jz      short loc_180039F35
0x180039f17  mov     rcx, rdi; hMutex
0x180039f1a  call    cs:__imp_ReleaseMutex
0x180039f21  nop     dword ptr [rax+rax+00h]
0x180039f26  mov     rcx, [rbp+198h]; this
0x180039f2d  test    eax, eax
0x180039f2f  jz      loc_18003A08A
0x180039f35  mov     rcx, rbx; hObject
0x180039f38  call    cs:__imp_CloseHandle
0x180039f3f  nop     dword ptr [rax+rax+00h]
0x180039f44  mov     rcx, [rbp+198h]; this
0x180039f4b  test    eax, eax
0x180039f4d  jz      loc_18003A095
0x180039f53  jmp     loc_180039E1E
0x180039f58  mov     dword ptr [r14], 1
0x180039f5f  mov     [r14+8], rbx
0x180039f63  mov     rax, [rsp+290h+var_260]
0x180039f68  mov     [r14+10h], rax
0x180039f6c  mov     [rsp+290h+var_260], 0
0x180039f75  mov     rax, [rsp+290h+var_258]
0x180039f7a  mov     [r14+18h], rax
0x180039f7e  mov     [rsp+290h+var_258], 0
0x180039f87  lea     rcx, [r14+28h]; void *
0x180039f8b  xor     edx, edx; Val
0x180039f8d  mov     r8d, 108h; Size
0x180039f93  call    memset_0
0x180039f98  xor     eax, eax
0x180039f9a  mov     [r14+20h], rax
0x180039f9e  lea     rcx, [r14+28h]; this
0x180039fa2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180039fa7  lea     rbx, [r14+0E8h]
0x180039fae  xor     r8d, r8d; Flags
0x180039fb1  xor     edx, edx; dwSpinCount
0x180039fb3  mov     rcx, rbx; lpCriticalSection
0x180039fb6  call    cs:__imp_InitializeCriticalSectionEx
0x180039fbd  nop     dword ptr [rax+rax+00h]
0x180039fc2  mov     qword ptr [rbx+28h], 0
0x180039fca  mov     qword ptr [rbx+30h], 0
0x180039fd2  mov     qword ptr [rbx+38h], 0
0x180039fda  mov     qword ptr [rbx+40h], 0
0x180039fe2  mov     [r15], r14
0x180039fe5  lea     rcx, [rsp+290h+var_260]; this
0x180039fea  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180039fef  xor     ebx, ebx
0x180039ff1  test    rdi, rdi
0x180039ff4  jz      short loc_18003A014
0x180039ff6  mov     rcx, rdi; hMutex
0x180039ff9  call    cs:__imp_ReleaseMutex
0x18003a000  nop     dword ptr [rax+rax+00h]
0x18003a005  mov     rcx, [rbp+198h]; this
0x18003a00c  test    eax, eax
0x18003a00e  jz      loc_18003A0A0
0x18003a014  test    rbx, rbx
0x18003a017  jz      short loc_18003A033
0x18003a019  mov     rcx, rbx; hObject
0x18003a01c  call    cs:__imp_CloseHandle
0x18003a023  nop     dword ptr [rax+rax+00h]
0x18003a028  mov     rcx, [rbp+198h]; this
0x18003a02f  test    eax, eax
0x18003a031  jz      short loc_18003A05C
0x18003a033  xor     eax, eax
0x18003a035  mov     rcx, [rbp+190h+var_30]
0x18003a03c  xor     rcx, rsp; StackCookie
0x18003a03f  call    __security_check_cookie
0x18003a044  mov     rbx, [rsp+290h+arg_10]
0x18003a04c  add     rsp, 270h
0x18003a053  pop     r15
0x18003a055  pop     r14
0x18003a057  pop     rdi
0x18003a058  pop     rsi
0x18003a059  pop     rbp
0x18003a05a  retn
0x18003a05c  mov     edx, 0A0Bh; void *
0x18003a061  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003a067  mov     rcx, [rbp+198h]; this
0x18003a06e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18003a074  mov     edx, 0A15h; void *
0x18003a079  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003a07f  mov     edx, 0A0Bh; void *
0x18003a084  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003a08a  mov     edx, 0A15h; void *
0x18003a08f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003a095  mov     edx, 0A0Bh; void *
0x18003a09a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003a0a0  mov     edx, 0A15h; void *
0x18003a0a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
