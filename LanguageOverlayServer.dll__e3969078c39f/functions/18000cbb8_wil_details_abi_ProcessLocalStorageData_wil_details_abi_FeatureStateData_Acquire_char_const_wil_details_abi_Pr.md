# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000cbb8`
- end: `0x18000cfa9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18000d348`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180006ec8`
- `0x18000753c`
- `0x180007840`
- `0x180007ed8`
- `0x1800088bc`
- `0x180009084`
- `0x180009a74`
- `0x180009b4c`
- `0x180009ff8`
- `0x18000a008`
- `0x18000ba44`
- `0x18000cbb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cc50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cc50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000cc2f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000cc2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cce6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cdf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ceb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cce6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cdf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ceb8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ce7b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ce7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cdc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cbf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cbf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cece`

## string_xrefs

- `0x18000cf07`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cf20`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cf46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cf5f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cf7e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cf97`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v32[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v32, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v32[0]);
  if ( 4 * v32[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = (_DWORD *)v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v32 = 0;
  if ( (v19 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v32,
          Name,
          v21,
          v19 >> 2);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v32[0];
  *((_QWORD *)v22 + 3) = v32[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v32[0] = 0;
  v32[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  return 0;
}

```

## disassembly

```asm
0x18000cbb8  mov     [rsp-8+arg_10], rbx
0x18000cbbd  push    rbp
0x18000cbbe  push    rsi
0x18000cbbf  push    rdi
0x18000cbc0  push    r14
0x18000cbc2  push    r15
0x18000cbc4  lea     rbp, [rsp-160h]
0x18000cbcc  sub     rsp, 260h
0x18000cbd3  mov     rax, cs:__security_cookie
0x18000cbda  xor     rax, rsp
0x18000cbdd  mov     [rbp+180h+var_30], rax
0x18000cbe4  mov     r15, rdx
0x18000cbe7  mov     qword ptr [rdx], 0
0x18000cbee  mov     rbx, rcx
0x18000cbf1  call    cs:__imp_GetCurrentProcessId
0x18000cbf7  mov     r14d, 130h
0x18000cbfd  mov     [rsp+280h+var_258], rbx
0x18000cc02  mov     r9d, eax
0x18000cc05  mov     [rsp+280h+var_260], r14d; int
0x18000cc0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000cc11  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cc16  lea     edx, [r14-2Ch]; unsigned __int64
0x18000cc1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cc1f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000cc25  lea     rdx, [rsp+280h+Name]; lpName
0x18000cc2a  xor     r8d, r8d; dwFlags
0x18000cc2d  xor     ecx, ecx; lpMutexAttributes
0x18000cc2f  call    cs:__imp_CreateMutexExW
0x18000cc35  mov     rbx, rax
0x18000cc38  test    rax, rax
0x18000cc3b  jnz     short loc_18000CC47
0x18000cc3d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000cc42  jmp     loc_18000CEDA
0x18000cc47  xor     r8d, r8d; bAlertable
0x18000cc4a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cc4d  mov     rcx, rbx; hHandle
0x18000cc50  call    cs:__imp_WaitForSingleObjectEx
0x18000cc56  cmp     eax, 102h
0x18000cc5b  jz      short loc_18000CC6D
0x18000cc5d  test    eax, 0FFFFFF7Fh
0x18000cc62  jnz     loc_18000CF32
0x18000cc68  mov     rdi, rbx
0x18000cc6b  jmp     short loc_18000CC6F
0x18000cc6d  xor     edi, edi
0x18000cc6f  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000cc74  mov     [rsp+280h+var_250], 0
0x18000cc7d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cc82  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000cc87  mov     esi, eax
0x18000cc89  test    eax, eax
0x18000cc8b  jns     short loc_18000CD0C
0x18000cc8d  mov     rcx, [rbp+188h]; this
0x18000cc94  lea     r8, aWil; "wil"
0x18000cc9b  mov     r9d, eax; char *
0x18000cc9e  mov     edx, 66h ; 'f'; void *
0x18000cca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cca8  mov     rcx, [rbp+188h]; this
0x18000ccaf  lea     r8, aWil; "wil"
0x18000ccb6  mov     r9d, esi; char *
0x18000ccb9  mov     edx, 6Fh ; 'o'; void *
0x18000ccbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccc3  mov     rcx, [rbp+188h]; this
0x18000ccca  lea     r8, aWil; "wil"
0x18000ccd1  mov     r9d, esi; char *
0x18000ccd4  mov     edx, 12Eh; void *
0x18000ccd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccde  test    rdi, rdi
0x18000cce1  jz      short loc_18000CCF4
0x18000cce3  mov     rcx, rdi; hMutex
0x18000cce6  call    cs:__imp_ReleaseMutex
0x18000ccec  test    eax, eax
0x18000ccee  jz      loc_18000CF3F
0x18000ccf4  mov     rcx, rbx; hObject
0x18000ccf7  call    cs:__imp_CloseHandle
0x18000ccfd  test    eax, eax
0x18000ccff  jz      loc_18000CF58
0x18000cd05  mov     eax, esi
0x18000cd07  jmp     loc_18000CEDA
0x18000cd0c  mov     rax, [rsp+280h+var_250]
0x18000cd11  lea     rcx, ds:0[rax*4]
0x18000cd19  test    rcx, rcx
0x18000cd1c  jz      short loc_18000CD2C
0x18000cd1e  mov     [r15], rcx
0x18000cd21  mov     eax, [rcx]
0x18000cd23  inc     eax
0x18000cd25  mov     [rcx], eax
0x18000cd27  jmp     loc_18000CEB0
0x18000cd2c  mov     rdx, r14; dwBytes
0x18000cd2f  mov     qword ptr [r15], 0
0x18000cd36  mov     ecx, 8; dwFlags
0x18000cd3b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cd40  mov     r14, rax
0x18000cd43  test    rax, rax
0x18000cd46  jnz     short loc_18000CD6A
0x18000cd48  mov     rcx, [rbp+188h]; this
0x18000cd4f  lea     r8, aWil; "wil"
0x18000cd56  mov     esi, 8007000Eh
0x18000cd5b  mov     edx, 14Bh; void *
0x18000cd60  mov     r9d, esi; char *
0x18000cd63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd68  jmp     short loc_18000CDD6
0x18000cd6a  xorps   xmm0, xmm0
0x18000cd6d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000cd73  test    r14b, 3
0x18000cd77  jnz     loc_18000CF71
0x18000cd7d  mov     r9, r14
0x18000cd80  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000cd85  shr     r9, 2; unsigned __int64
0x18000cd89  lea     rcx, [rsp+280h+var_250]; this
0x18000cd8e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000cd93  mov     esi, eax
0x18000cd95  test    eax, eax
0x18000cd97  jns     loc_18000CE1D
0x18000cd9d  mov     rcx, [rbp+188h]; this
0x18000cda4  lea     r8, aWil; "wil"
0x18000cdab  mov     r9d, eax; char *
0x18000cdae  mov     edx, 14Eh; void *
0x18000cdb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdb8  lea     rcx, [rsp+280h+var_250]; this
0x18000cdbd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000cdc2  call    cs:__imp_GetProcessHeap
0x18000cdc8  mov     r8, r14; lpMem
0x18000cdcb  xor     edx, edx; dwFlags
0x18000cdcd  mov     rcx, rax; hHeap
0x18000cdd0  call    cs:__imp_HeapFree
0x18000cdd6  mov     rcx, [rbp+188h]; this
0x18000cddd  lea     r8, aWil; "wil"
0x18000cde4  mov     r9d, esi; char *
0x18000cde7  mov     edx, 137h; void *
0x18000cdec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdf1  test    rdi, rdi
0x18000cdf4  jz      short loc_18000CE07
0x18000cdf6  mov     rcx, rdi; hMutex
0x18000cdf9  call    cs:__imp_ReleaseMutex
0x18000cdff  test    eax, eax
0x18000ce01  jz      loc_18000CF77
0x18000ce07  mov     rcx, rbx; hObject
0x18000ce0a  call    cs:__imp_CloseHandle
0x18000ce10  test    eax, eax
0x18000ce12  jz      loc_18000CF19
0x18000ce18  jmp     loc_18000CD05
0x18000ce1d  mov     rax, [rsp+280h+var_250]
0x18000ce22  lea     rcx, [r14+28h]; void *
0x18000ce26  mov     [r14+10h], rax
0x18000ce2a  xor     edx, edx; Val
0x18000ce2c  mov     rax, [rsp+280h+var_250+8]
0x18000ce31  mov     r8d, 108h; Size
0x18000ce37  mov     [r14+18h], rax
0x18000ce3b  mov     dword ptr [r14], 1
0x18000ce42  mov     [r14+8], rbx
0x18000ce46  mov     [rsp+280h+var_250], 0
0x18000ce4f  mov     [rsp+280h+var_250+8], 0
0x18000ce58  call    memset_0
0x18000ce5d  xor     eax, eax
0x18000ce5f  lea     rcx, [r14+28h]; this
0x18000ce63  mov     [r14+20h], rax
0x18000ce67  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ce6c  lea     rbx, [r14+0E8h]
0x18000ce73  xor     r8d, r8d; Flags
0x18000ce76  mov     rcx, rbx; lpCriticalSection
0x18000ce79  xor     edx, edx; dwSpinCount
0x18000ce7b  call    cs:__imp_InitializeCriticalSectionEx
0x18000ce81  mov     qword ptr [rbx+28h], 0
0x18000ce89  lea     rcx, [rsp+280h+var_250]; this
0x18000ce8e  mov     qword ptr [rbx+30h], 0
0x18000ce96  mov     qword ptr [rbx+38h], 0
0x18000ce9e  mov     qword ptr [rbx+40h], 0
0x18000cea6  mov     [r15], r14
0x18000cea9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ceae  xor     ebx, ebx
0x18000ceb0  test    rdi, rdi
0x18000ceb3  jz      short loc_18000CEC6
0x18000ceb5  mov     rcx, rdi; hMutex
0x18000ceb8  call    cs:__imp_ReleaseMutex
0x18000cebe  test    eax, eax
0x18000cec0  jz      loc_18000CF90
0x18000cec6  test    rbx, rbx
0x18000cec9  jz      short loc_18000CED8
0x18000cecb  mov     rcx, rbx; hObject
0x18000cece  call    cs:__imp_CloseHandle
0x18000ced4  test    eax, eax
0x18000ced6  jz      short loc_18000CF00
0x18000ced8  xor     eax, eax
0x18000ceda  mov     rcx, [rbp+180h+var_30]
0x18000cee1  xor     rcx, rsp; StackCookie
0x18000cee4  call    __security_check_cookie
0x18000cee9  mov     rbx, [rsp+280h+arg_10]
0x18000cef1  add     rsp, 260h
0x18000cef8  pop     r15
0x18000cefa  pop     r14
0x18000cefc  pop     rdi
0x18000cefd  pop     rsi
0x18000cefe  pop     rbp
0x18000ceff  retn
0x18000cf00  mov     rcx, [rbp+188h]; this
0x18000cf07  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf0e  mov     edx, 0A0Bh; void *
0x18000cf13  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cf19  mov     rcx, [rbp+188h]; this
0x18000cf20  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf27  mov     edx, 0A0Bh; void *
0x18000cf2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cf32  mov     rcx, [rbp+188h]; this
0x18000cf39  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000cf3f  mov     rcx, [rbp+188h]; this
0x18000cf46  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf4d  mov     edx, 0A15h; void *
0x18000cf52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cf58  mov     rcx, [rbp+188h]; this
0x18000cf5f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf66  mov     edx, 0A0Bh; void *
0x18000cf6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cf71  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cf77  mov     rcx, [rbp+188h]; this
0x18000cf7e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf85  mov     edx, 0A15h; void *
0x18000cf8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cf90  mov     rcx, [rbp+188h]; this
0x18000cf97  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cf9e  mov     edx, 0A15h; void *
0x18000cfa3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
