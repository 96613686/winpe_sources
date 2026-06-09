# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008b94`
- end: `0x180008f91`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180008f98`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18000494c`
- `0x180004f88`
- `0x180005290`
- `0x1800058e8`
- `0x1800063c8`
- `0x180006844`
- `0x180007234`
- `0x18000730c`
- `0x18000770c`
- `0x18000771c`
- `0x180008414`
- `0x180008b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008cc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e94`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008cc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008c2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008c2c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c0b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008c0b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008e57`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008dac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008dac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008bcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eaa`

## string_xrefs

- `0x180008ee3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008efc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008f15`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008f2e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008f47`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008f66`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008f7f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x180008b94  mov     [rsp-8+arg_10], rbx
0x180008b99  push    rbp
0x180008b9a  push    rsi
0x180008b9b  push    rdi
0x180008b9c  push    r14
0x180008b9e  push    r15
0x180008ba0  lea     rbp, [rsp-160h]
0x180008ba8  sub     rsp, 260h
0x180008baf  mov     rax, cs:__security_cookie
0x180008bb6  xor     rax, rsp
0x180008bb9  mov     [rbp+180h+var_30], rax
0x180008bc0  mov     r15, rdx
0x180008bc3  mov     qword ptr [rdx], 0
0x180008bca  mov     rbx, rcx
0x180008bcd  call    cs:__imp_GetCurrentProcessId
0x180008bd3  mov     r14d, 130h
0x180008bd9  mov     [rsp+280h+var_258], rbx
0x180008bde  mov     r9d, eax
0x180008be1  mov     [rsp+280h+var_260], r14d; int
0x180008be6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008bed  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180008bf2  lea     edx, [r14-2Ch]; unsigned __int64
0x180008bf6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180008bfb  mov     r9d, 1F0001h; dwDesiredAccess
0x180008c01  lea     rdx, [rsp+280h+Name]; lpName
0x180008c06  xor     r8d, r8d; dwFlags
0x180008c09  xor     ecx, ecx; lpMutexAttributes
0x180008c0b  call    cs:__imp_CreateMutexExW
0x180008c11  mov     rbx, rax
0x180008c14  test    rax, rax
0x180008c17  jnz     short loc_180008C23
0x180008c19  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c1e  jmp     loc_180008EB6
0x180008c23  xor     r8d, r8d; bAlertable
0x180008c26  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008c29  mov     rcx, rbx; hHandle
0x180008c2c  call    cs:__imp_WaitForSingleObjectEx
0x180008c32  cmp     eax, 102h
0x180008c37  jz      short loc_180008C49
0x180008c39  test    eax, 0FFFFFF7Fh
0x180008c3e  jnz     loc_180008F0E
0x180008c44  mov     rdi, rbx
0x180008c47  jmp     short loc_180008C4B
0x180008c49  xor     edi, edi
0x180008c4b  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180008c50  mov     [rsp+280h+var_250], 0
0x180008c59  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180008c5e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180008c63  mov     esi, eax
0x180008c65  test    eax, eax
0x180008c67  jns     short loc_180008CE8
0x180008c69  mov     rcx, [rbp+188h]; this
0x180008c70  lea     r8, aWil; "wil"
0x180008c77  mov     r9d, eax; char *
0x180008c7a  mov     edx, 66h ; 'f'; void *
0x180008c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c84  mov     rcx, [rbp+188h]; this
0x180008c8b  lea     r8, aWil; "wil"
0x180008c92  mov     r9d, esi; char *
0x180008c95  mov     edx, 6Fh ; 'o'; void *
0x180008c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c9f  mov     rcx, [rbp+188h]; this
0x180008ca6  lea     r8, aWil; "wil"
0x180008cad  mov     r9d, esi; char *
0x180008cb0  mov     edx, 12Eh; void *
0x180008cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cba  test    rdi, rdi
0x180008cbd  jz      short loc_180008CD0
0x180008cbf  mov     rcx, rdi; hMutex
0x180008cc2  call    cs:__imp_ReleaseMutex
0x180008cc8  test    eax, eax
0x180008cca  jz      loc_180008F27
0x180008cd0  mov     rcx, rbx; hObject
0x180008cd3  call    cs:__imp_CloseHandle
0x180008cd9  test    eax, eax
0x180008cdb  jz      loc_180008F40
0x180008ce1  mov     eax, esi
0x180008ce3  jmp     loc_180008EB6
0x180008ce8  mov     rax, [rsp+280h+var_250]
0x180008ced  lea     rcx, ds:0[rax*4]
0x180008cf5  test    rcx, rcx
0x180008cf8  jz      short loc_180008D08
0x180008cfa  mov     [r15], rcx
0x180008cfd  mov     eax, [rcx]
0x180008cff  inc     eax
0x180008d01  mov     [rcx], eax
0x180008d03  jmp     loc_180008E8C
0x180008d08  mov     rdx, r14; dwBytes
0x180008d0b  mov     qword ptr [r15], 0
0x180008d12  mov     ecx, 8; dwFlags
0x180008d17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008d1c  mov     r14, rax
0x180008d1f  test    rax, rax
0x180008d22  jnz     short loc_180008D46
0x180008d24  mov     rcx, [rbp+188h]; this
0x180008d2b  lea     r8, aWil; "wil"
0x180008d32  mov     esi, 8007000Eh
0x180008d37  mov     edx, 14Bh; void *
0x180008d3c  mov     r9d, esi; char *
0x180008d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d44  jmp     short loc_180008DB2
0x180008d46  xorps   xmm0, xmm0
0x180008d49  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180008d4f  test    r14b, 3
0x180008d53  jnz     loc_180008F59
0x180008d59  mov     r9, r14
0x180008d5c  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180008d61  shr     r9, 2; unsigned __int64
0x180008d65  lea     rcx, [rsp+280h+var_250]; this
0x180008d6a  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180008d6f  mov     esi, eax
0x180008d71  test    eax, eax
0x180008d73  jns     loc_180008DF9
0x180008d79  mov     rcx, [rbp+188h]; this
0x180008d80  lea     r8, aWil; "wil"
0x180008d87  mov     r9d, eax; char *
0x180008d8a  mov     edx, 14Eh; void *
0x180008d8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d94  lea     rcx, [rsp+280h+var_250]; this
0x180008d99  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008d9e  call    cs:__imp_GetProcessHeap
0x180008da4  mov     r8, r14; lpMem
0x180008da7  xor     edx, edx; dwFlags
0x180008da9  mov     rcx, rax; hHeap
0x180008dac  call    cs:__imp_HeapFree
0x180008db2  mov     rcx, [rbp+188h]; this
0x180008db9  lea     r8, aWil; "wil"
0x180008dc0  mov     r9d, esi; char *
0x180008dc3  mov     edx, 137h; void *
0x180008dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dcd  test    rdi, rdi
0x180008dd0  jz      short loc_180008DE3
0x180008dd2  mov     rcx, rdi; hMutex
0x180008dd5  call    cs:__imp_ReleaseMutex
0x180008ddb  test    eax, eax
0x180008ddd  jz      loc_180008F5F
0x180008de3  mov     rcx, rbx; hObject
0x180008de6  call    cs:__imp_CloseHandle
0x180008dec  test    eax, eax
0x180008dee  jz      loc_180008EF5
0x180008df4  jmp     loc_180008CE1
0x180008df9  mov     rax, [rsp+280h+var_250]
0x180008dfe  lea     rcx, [r14+28h]; void *
0x180008e02  mov     [r14+10h], rax
0x180008e06  xor     edx, edx; Val
0x180008e08  mov     rax, [rsp+280h+var_250+8]
0x180008e0d  mov     r8d, 108h; Size
0x180008e13  mov     [r14+18h], rax
0x180008e17  mov     dword ptr [r14], 1
0x180008e1e  mov     [r14+8], rbx
0x180008e22  mov     [rsp+280h+var_250], 0
0x180008e2b  mov     [rsp+280h+var_250+8], 0
0x180008e34  call    memset_0
0x180008e39  xor     eax, eax
0x180008e3b  lea     rcx, [r14+28h]; this
0x180008e3f  mov     [r14+20h], rax
0x180008e43  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008e48  lea     rbx, [r14+0E8h]
0x180008e4f  xor     r8d, r8d; Flags
0x180008e52  mov     rcx, rbx; lpCriticalSection
0x180008e55  xor     edx, edx; dwSpinCount
0x180008e57  call    cs:__imp_InitializeCriticalSectionEx
0x180008e5d  mov     qword ptr [rbx+28h], 0
0x180008e65  lea     rcx, [rsp+280h+var_250]; this
0x180008e6a  mov     qword ptr [rbx+30h], 0
0x180008e72  mov     qword ptr [rbx+38h], 0
0x180008e7a  mov     qword ptr [rbx+40h], 0
0x180008e82  mov     [r15], r14
0x180008e85  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008e8a  xor     ebx, ebx
0x180008e8c  test    rdi, rdi
0x180008e8f  jz      short loc_180008EA2
0x180008e91  mov     rcx, rdi; hMutex
0x180008e94  call    cs:__imp_ReleaseMutex
0x180008e9a  test    eax, eax
0x180008e9c  jz      loc_180008F78
0x180008ea2  test    rbx, rbx
0x180008ea5  jz      short loc_180008EB4
0x180008ea7  mov     rcx, rbx; hObject
0x180008eaa  call    cs:__imp_CloseHandle
0x180008eb0  test    eax, eax
0x180008eb2  jz      short loc_180008EDC
0x180008eb4  xor     eax, eax
0x180008eb6  mov     rcx, [rbp+180h+var_30]
0x180008ebd  xor     rcx, rsp; StackCookie
0x180008ec0  call    __security_check_cookie
0x180008ec5  mov     rbx, [rsp+280h+arg_10]
0x180008ecd  add     rsp, 260h
0x180008ed4  pop     r15
0x180008ed6  pop     r14
0x180008ed8  pop     rdi
0x180008ed9  pop     rsi
0x180008eda  pop     rbp
0x180008edb  retn
0x180008edc  mov     rcx, [rbp+188h]; this
0x180008ee3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008eea  mov     edx, 0A0Bh; void *
0x180008eef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ef5  mov     rcx, [rbp+188h]; this
0x180008efc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f03  mov     edx, 0A0Bh; void *
0x180008f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f0e  mov     rcx, [rbp+188h]; this
0x180008f15  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f1c  mov     edx, 0E01h; void *
0x180008f21  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008f27  mov     rcx, [rbp+188h]; this
0x180008f2e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f35  mov     edx, 0A15h; void *
0x180008f3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f40  mov     rcx, [rbp+188h]; this
0x180008f47  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f4e  mov     edx, 0A0Bh; void *
0x180008f53  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f59  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008f5f  mov     rcx, [rbp+188h]; this
0x180008f66  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f6d  mov     edx, 0A15h; void *
0x180008f72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f78  mov     rcx, [rbp+188h]; this
0x180008f7f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f86  mov     edx, 0A15h; void *
0x180008f8b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
