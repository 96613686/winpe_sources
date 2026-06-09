# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000d264`
- end: `0x18000d661`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18000d668`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x1800093a0`
- `0x1800099e8`
- `0x180009cf0`
- `0x18000a348`
- `0x18000abc8`
- `0x18000b064`
- `0x18000ba68`
- `0x18000bb4c`
- `0x18000c008`
- `0x18000c018`
- `0x18000caac`
- `0x18000d264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d2fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d2fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d392`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d4a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d564`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d392`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d4a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d564`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000d527`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000d527`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d2db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d2db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d46e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d46e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d47c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d47c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d29d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d29d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d57a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d57a`

## string_xrefs

- `0x18000d5b3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d5cc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d5e5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d5fe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d617`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d636`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d64f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x18000d264  mov     [rsp-8+arg_10], rbx
0x18000d269  push    rbp
0x18000d26a  push    rsi
0x18000d26b  push    rdi
0x18000d26c  push    r14
0x18000d26e  push    r15
0x18000d270  lea     rbp, [rsp-160h]
0x18000d278  sub     rsp, 260h
0x18000d27f  mov     rax, cs:__security_cookie
0x18000d286  xor     rax, rsp
0x18000d289  mov     [rbp+180h+var_30], rax
0x18000d290  mov     r15, rdx
0x18000d293  mov     qword ptr [rdx], 0
0x18000d29a  mov     rbx, rcx
0x18000d29d  call    cs:__imp_GetCurrentProcessId
0x18000d2a3  mov     r14d, 130h
0x18000d2a9  mov     [rsp+280h+var_258], rbx
0x18000d2ae  mov     r9d, eax
0x18000d2b1  mov     [rsp+280h+var_260], r14d; int
0x18000d2b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d2bd  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000d2c2  lea     edx, [r14-2Ch]; unsigned __int64
0x18000d2c6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000d2cb  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d2d1  lea     rdx, [rsp+280h+Name]; lpName
0x18000d2d6  xor     r8d, r8d; dwFlags
0x18000d2d9  xor     ecx, ecx; lpMutexAttributes
0x18000d2db  call    cs:__imp_CreateMutexExW
0x18000d2e1  mov     rbx, rax
0x18000d2e4  test    rax, rax
0x18000d2e7  jnz     short loc_18000D2F3
0x18000d2e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d2ee  jmp     loc_18000D586
0x18000d2f3  xor     r8d, r8d; bAlertable
0x18000d2f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d2f9  mov     rcx, rbx; hHandle
0x18000d2fc  call    cs:__imp_WaitForSingleObjectEx
0x18000d302  cmp     eax, 102h
0x18000d307  jz      short loc_18000D319
0x18000d309  test    eax, 0FFFFFF7Fh
0x18000d30e  jnz     loc_18000D5DE
0x18000d314  mov     rdi, rbx
0x18000d317  jmp     short loc_18000D31B
0x18000d319  xor     edi, edi
0x18000d31b  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000d320  mov     [rsp+280h+var_250], 0
0x18000d329  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000d32e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000d333  mov     esi, eax
0x18000d335  test    eax, eax
0x18000d337  jns     short loc_18000D3B8
0x18000d339  mov     rcx, [rbp+188h]; this
0x18000d340  lea     r8, aWil; "wil"
0x18000d347  mov     r9d, eax; char *
0x18000d34a  mov     edx, 66h ; 'f'; void *
0x18000d34f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d354  mov     rcx, [rbp+188h]; this
0x18000d35b  lea     r8, aWil; "wil"
0x18000d362  mov     r9d, esi; char *
0x18000d365  mov     edx, 6Fh ; 'o'; void *
0x18000d36a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d36f  mov     rcx, [rbp+188h]; this
0x18000d376  lea     r8, aWil; "wil"
0x18000d37d  mov     r9d, esi; char *
0x18000d380  mov     edx, 12Eh; void *
0x18000d385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d38a  test    rdi, rdi
0x18000d38d  jz      short loc_18000D3A0
0x18000d38f  mov     rcx, rdi; hMutex
0x18000d392  call    cs:__imp_ReleaseMutex
0x18000d398  test    eax, eax
0x18000d39a  jz      loc_18000D5F7
0x18000d3a0  mov     rcx, rbx; hObject
0x18000d3a3  call    cs:__imp_CloseHandle
0x18000d3a9  test    eax, eax
0x18000d3ab  jz      loc_18000D610
0x18000d3b1  mov     eax, esi
0x18000d3b3  jmp     loc_18000D586
0x18000d3b8  mov     rax, [rsp+280h+var_250]
0x18000d3bd  lea     rcx, ds:0[rax*4]
0x18000d3c5  test    rcx, rcx
0x18000d3c8  jz      short loc_18000D3D8
0x18000d3ca  mov     [r15], rcx
0x18000d3cd  mov     eax, [rcx]
0x18000d3cf  inc     eax
0x18000d3d1  mov     [rcx], eax
0x18000d3d3  jmp     loc_18000D55C
0x18000d3d8  mov     rdx, r14; dwBytes
0x18000d3db  mov     qword ptr [r15], 0
0x18000d3e2  mov     ecx, 8; dwFlags
0x18000d3e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d3ec  mov     r14, rax
0x18000d3ef  test    rax, rax
0x18000d3f2  jnz     short loc_18000D416
0x18000d3f4  mov     rcx, [rbp+188h]; this
0x18000d3fb  lea     r8, aWil; "wil"
0x18000d402  mov     esi, 8007000Eh
0x18000d407  mov     edx, 14Bh; void *
0x18000d40c  mov     r9d, esi; char *
0x18000d40f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d414  jmp     short loc_18000D482
0x18000d416  xorps   xmm0, xmm0
0x18000d419  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000d41f  test    r14b, 3
0x18000d423  jnz     loc_18000D629
0x18000d429  mov     r9, r14
0x18000d42c  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000d431  shr     r9, 2; unsigned __int64
0x18000d435  lea     rcx, [rsp+280h+var_250]; this
0x18000d43a  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000d43f  mov     esi, eax
0x18000d441  test    eax, eax
0x18000d443  jns     loc_18000D4C9
0x18000d449  mov     rcx, [rbp+188h]; this
0x18000d450  lea     r8, aWil; "wil"
0x18000d457  mov     r9d, eax; char *
0x18000d45a  mov     edx, 14Eh; void *
0x18000d45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d464  lea     rcx, [rsp+280h+var_250]; this
0x18000d469  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000d46e  call    cs:__imp_GetProcessHeap
0x18000d474  mov     r8, r14; lpMem
0x18000d477  xor     edx, edx; dwFlags
0x18000d479  mov     rcx, rax; hHeap
0x18000d47c  call    cs:__imp_HeapFree
0x18000d482  mov     rcx, [rbp+188h]; this
0x18000d489  lea     r8, aWil; "wil"
0x18000d490  mov     r9d, esi; char *
0x18000d493  mov     edx, 137h; void *
0x18000d498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d49d  test    rdi, rdi
0x18000d4a0  jz      short loc_18000D4B3
0x18000d4a2  mov     rcx, rdi; hMutex
0x18000d4a5  call    cs:__imp_ReleaseMutex
0x18000d4ab  test    eax, eax
0x18000d4ad  jz      loc_18000D62F
0x18000d4b3  mov     rcx, rbx; hObject
0x18000d4b6  call    cs:__imp_CloseHandle
0x18000d4bc  test    eax, eax
0x18000d4be  jz      loc_18000D5C5
0x18000d4c4  jmp     loc_18000D3B1
0x18000d4c9  mov     rax, [rsp+280h+var_250]
0x18000d4ce  lea     rcx, [r14+28h]; void *
0x18000d4d2  mov     [r14+10h], rax
0x18000d4d6  xor     edx, edx; Val
0x18000d4d8  mov     rax, [rsp+280h+var_250+8]
0x18000d4dd  mov     r8d, 108h; Size
0x18000d4e3  mov     [r14+18h], rax
0x18000d4e7  mov     dword ptr [r14], 1
0x18000d4ee  mov     [r14+8], rbx
0x18000d4f2  mov     [rsp+280h+var_250], 0
0x18000d4fb  mov     [rsp+280h+var_250+8], 0
0x18000d504  call    memset_0
0x18000d509  xor     eax, eax
0x18000d50b  lea     rcx, [r14+28h]; this
0x18000d50f  mov     [r14+20h], rax
0x18000d513  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000d518  lea     rbx, [r14+0E8h]
0x18000d51f  xor     r8d, r8d; Flags
0x18000d522  mov     rcx, rbx; lpCriticalSection
0x18000d525  xor     edx, edx; dwSpinCount
0x18000d527  call    cs:__imp_InitializeCriticalSectionEx
0x18000d52d  mov     qword ptr [rbx+28h], 0
0x18000d535  lea     rcx, [rsp+280h+var_250]; this
0x18000d53a  mov     qword ptr [rbx+30h], 0
0x18000d542  mov     qword ptr [rbx+38h], 0
0x18000d54a  mov     qword ptr [rbx+40h], 0
0x18000d552  mov     [r15], r14
0x18000d555  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000d55a  xor     ebx, ebx
0x18000d55c  test    rdi, rdi
0x18000d55f  jz      short loc_18000D572
0x18000d561  mov     rcx, rdi; hMutex
0x18000d564  call    cs:__imp_ReleaseMutex
0x18000d56a  test    eax, eax
0x18000d56c  jz      loc_18000D648
0x18000d572  test    rbx, rbx
0x18000d575  jz      short loc_18000D584
0x18000d577  mov     rcx, rbx; hObject
0x18000d57a  call    cs:__imp_CloseHandle
0x18000d580  test    eax, eax
0x18000d582  jz      short loc_18000D5AC
0x18000d584  xor     eax, eax
0x18000d586  mov     rcx, [rbp+180h+var_30]
0x18000d58d  xor     rcx, rsp; StackCookie
0x18000d590  call    __security_check_cookie
0x18000d595  mov     rbx, [rsp+280h+arg_10]
0x18000d59d  add     rsp, 260h
0x18000d5a4  pop     r15
0x18000d5a6  pop     r14
0x18000d5a8  pop     rdi
0x18000d5a9  pop     rsi
0x18000d5aa  pop     rbp
0x18000d5ab  retn
0x18000d5ac  mov     rcx, [rbp+188h]; this
0x18000d5b3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d5ba  mov     edx, 0A0Bh; void *
0x18000d5bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5c5  mov     rcx, [rbp+188h]; this
0x18000d5cc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d5d3  mov     edx, 0A0Bh; void *
0x18000d5d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5de  mov     rcx, [rbp+188h]; this
0x18000d5e5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d5ec  mov     edx, 0E01h; void *
0x18000d5f1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000d5f7  mov     rcx, [rbp+188h]; this
0x18000d5fe  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d605  mov     edx, 0A15h; void *
0x18000d60a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d610  mov     rcx, [rbp+188h]; this
0x18000d617  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d61e  mov     edx, 0A0Bh; void *
0x18000d623  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d629  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d62f  mov     rcx, [rbp+188h]; this
0x18000d636  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d63d  mov     edx, 0A15h; void *
0x18000d642  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d648  mov     rcx, [rbp+188h]; this
0x18000d64f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d656  mov     edx, 0A15h; void *
0x18000d65b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
