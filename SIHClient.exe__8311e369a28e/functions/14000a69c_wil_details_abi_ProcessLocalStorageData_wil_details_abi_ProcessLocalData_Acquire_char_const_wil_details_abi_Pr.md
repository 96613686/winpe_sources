# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000a69c`
- end: `0x14000a892`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1400094dc`

## callees

- `0x140007780`
- `0x140008140`
- `0x140008de4`
- `0x140008e28`
- `0x140008e44`
- `0x140008ff8`
- `0x14000a69c`
- `0x14000aabc`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000a713`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000a713`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a775`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a775`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a818`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a6d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a6d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a735`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  unsigned int LastErrorFailHr; // edi
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // r9
  void *v15; // rsi
  int ValueInternal; // eax
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  unsigned int v19; // r8d
  const char *v20; // r9
  int v21; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  HANDLE v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v22 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v24 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v11 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v15 = 0;
  }
  else
  {
    if ( (v11 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v12, v13, v14);
    v15 = v6;
  }
  v25 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v12, &v25, (bool *)v14);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)LastErrorFailHr, v23);
    v17 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
    goto LABEL_15;
  }
  v18 = (_DWORD *)(4 * v25);
  if ( 4 * v25 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            Name,
            &v24,
            a2);
    v6 = v24;
    LastErrorFailHr = v21;
    if ( v21 < 0 )
    {
      v17 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v15 && !ReleaseMutex(v15) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DB, v19, v20);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v8, v9);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x14000a69c  mov     [rsp-8+arg_10], rbx
0x14000a6a1  mov     [rsp-8+arg_18], rsi
0x14000a6a6  push    rbp
0x14000a6a7  push    rdi
0x14000a6a8  push    r14
0x14000a6aa  lea     rbp, [rsp-160h]
0x14000a6b2  sub     rsp, 260h
0x14000a6b9  mov     rax, cs:__security_cookie
0x14000a6c0  xor     rax, rsp
0x14000a6c3  mov     [rbp+170h+var_20], rax
0x14000a6ca  mov     r14, rdx
0x14000a6cd  mov     qword ptr [rdx], 0
0x14000a6d4  mov     rbx, rcx
0x14000a6d7  call    cs:__imp_GetCurrentProcessId
0x14000a6dd  mov     [rsp+270h+var_248], rbx
0x14000a6e2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000a6e9  mov     r9d, eax
0x14000a6ec  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000a6f4  mov     edx, 104h; unsigned __int64
0x14000a6f9  lea     rcx, [rsp+270h+Name]; Buffer
0x14000a6fe  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000a703  mov     r9d, 1F0001h; dwDesiredAccess
0x14000a709  lea     rdx, [rsp+270h+Name]; lpName
0x14000a70e  xor     r8d, r8d; dwFlags
0x14000a711  xor     ecx, ecx; lpMutexAttributes
0x14000a713  call    cs:__imp_CreateMutexExW
0x14000a719  mov     [rsp+270h+var_240], rax
0x14000a71e  mov     rbx, rax
0x14000a721  test    rax, rax
0x14000a724  jnz     short loc_14000A76C
0x14000a726  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a72b  mov     edi, eax
0x14000a72d  test    rbx, rbx
0x14000a730  jz      short loc_14000A743
0x14000a732  mov     rcx, rbx; hObject
0x14000a735  call    cs:__imp_CloseHandle
0x14000a73b  test    eax, eax
0x14000a73d  jz      loc_14000A880
0x14000a743  mov     eax, edi
0x14000a745  mov     rcx, [rbp+170h+var_20]
0x14000a74c  xor     rcx, rsp; StackCookie
0x14000a74f  call    __security_check_cookie
0x14000a754  lea     r11, [rsp+270h+var_10]
0x14000a75c  mov     rbx, [r11+30h]
0x14000a760  mov     rsi, [r11+38h]
0x14000a764  mov     rsp, r11
0x14000a767  pop     r14
0x14000a769  pop     rdi
0x14000a76a  pop     rbp
0x14000a76b  retn
0x14000a76c  xor     r8d, r8d; bAlertable
0x14000a76f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000a772  mov     rcx, rbx; hHandle
0x14000a775  call    cs:__imp_WaitForSingleObjectEx
0x14000a77b  cmp     eax, 102h
0x14000a780  jz      short loc_14000A792
0x14000a782  test    eax, 0FFFFFF7Fh
0x14000a787  jnz     loc_14000A861
0x14000a78d  mov     rsi, rbx
0x14000a790  jmp     short loc_14000A794
0x14000a792  xor     esi, esi
0x14000a794  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x14000a799  mov     [rsp+270h+var_238], 0
0x14000a7a2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14000a7a7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14000a7ac  mov     edi, eax
0x14000a7ae  test    eax, eax
0x14000a7b0  jns     short loc_14000A7EF
0x14000a7b2  mov     rcx, [rbp+178h]; this
0x14000a7b9  lea     r8, aWil; "wil"
0x14000a7c0  mov     r9d, eax; char *
0x14000a7c3  mov     edx, 64h ; 'd'; void *
0x14000a7c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a7cd  mov     rcx, [rbp+178h]; this
0x14000a7d4  lea     r8, aWil; "wil"
0x14000a7db  mov     r9d, edi; char *
0x14000a7de  mov     edx, 6Dh ; 'm'; void *
0x14000a7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a7e8  mov     edx, 12Bh
0x14000a7ed  jmp     short loc_14000A849
0x14000a7ef  mov     rax, [rsp+270h+var_238]
0x14000a7f4  lea     rcx, ds:0[rax*4]
0x14000a7fc  test    rcx, rcx
0x14000a7ff  jz      short loc_14000A827
0x14000a801  mov     [r14], rcx
0x14000a804  mov     eax, [rcx]
0x14000a806  inc     eax
0x14000a808  mov     [rcx], eax
0x14000a80a  xor     edi, edi
0x14000a80c  test    rsi, rsi
0x14000a80f  jz      loc_14000A72D
0x14000a815  mov     rcx, rsi; hMutex
0x14000a818  call    cs:__imp_ReleaseMutex
0x14000a81e  test    eax, eax
0x14000a820  jz      short loc_14000A86E
0x14000a822  jmp     loc_14000A72D
0x14000a827  mov     r8, r14
0x14000a82a  lea     rdx, [rsp+270h+var_240]
0x14000a82f  lea     rcx, [rsp+270h+Name]
0x14000a834  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000a839  mov     rbx, [rsp+270h+var_240]
0x14000a83e  mov     edi, eax
0x14000a840  test    eax, eax
0x14000a842  jns     short loc_14000A80A
0x14000a844  mov     edx, 134h; void *
0x14000a849  mov     rcx, [rbp+178h]; this
0x14000a850  lea     r8, aWil; "wil"
0x14000a857  mov     r9d, edi; char *
0x14000a85a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a85f  jmp     short loc_14000A80C
0x14000a861  mov     rcx, [rbp+178h]; this
0x14000a868  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000a86e  mov     rcx, [rbp+178h]; this
0x14000a875  mov     edx, 9DBh; void *
0x14000a87a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a880  mov     rcx, [rbp+178h]; this
0x14000a887  mov     edx, 9D1h; void *
0x14000a88c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
