# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005e10`
- end: `0x180006006`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180005620`

## callees

- `0x180003180`
- `0x180003c94`
- `0x180004170`
- `0x180004d64`
- `0x180004d80`
- `0x180005144`
- `0x180005e10`
- `0x180006230`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e4b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005e87`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005e87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ee9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ea9`

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
0x180005e10  mov     [rsp-8+arg_10], rbx
0x180005e15  mov     [rsp-8+arg_18], rsi
0x180005e1a  push    rbp
0x180005e1b  push    rdi
0x180005e1c  push    r14
0x180005e1e  lea     rbp, [rsp-160h]
0x180005e26  sub     rsp, 260h
0x180005e2d  mov     rax, cs:__security_cookie
0x180005e34  xor     rax, rsp
0x180005e37  mov     [rbp+170h+var_20], rax
0x180005e3e  mov     r14, rdx
0x180005e41  mov     qword ptr [rdx], 0
0x180005e48  mov     rbx, rcx
0x180005e4b  call    cs:__imp_GetCurrentProcessId
0x180005e51  mov     [rsp+270h+var_248], rbx
0x180005e56  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005e5d  mov     r9d, eax
0x180005e60  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180005e68  mov     edx, 104h; unsigned __int64
0x180005e6d  lea     rcx, [rsp+270h+Name]; Buffer
0x180005e72  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005e77  mov     r9d, 1F0001h; dwDesiredAccess
0x180005e7d  lea     rdx, [rsp+270h+Name]; lpName
0x180005e82  xor     r8d, r8d; dwFlags
0x180005e85  xor     ecx, ecx; lpMutexAttributes
0x180005e87  call    cs:__imp_CreateMutexExW
0x180005e8d  mov     [rsp+270h+var_240], rax
0x180005e92  mov     rbx, rax
0x180005e95  test    rax, rax
0x180005e98  jnz     short loc_180005EE0
0x180005e9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005e9f  mov     edi, eax
0x180005ea1  test    rbx, rbx
0x180005ea4  jz      short loc_180005EB7
0x180005ea6  mov     rcx, rbx; hObject
0x180005ea9  call    cs:__imp_CloseHandle
0x180005eaf  test    eax, eax
0x180005eb1  jz      loc_180005FF4
0x180005eb7  mov     eax, edi
0x180005eb9  mov     rcx, [rbp+170h+var_20]
0x180005ec0  xor     rcx, rsp; StackCookie
0x180005ec3  call    __security_check_cookie
0x180005ec8  lea     r11, [rsp+270h+var_10]
0x180005ed0  mov     rbx, [r11+30h]
0x180005ed4  mov     rsi, [r11+38h]
0x180005ed8  mov     rsp, r11
0x180005edb  pop     r14
0x180005edd  pop     rdi
0x180005ede  pop     rbp
0x180005edf  retn
0x180005ee0  xor     r8d, r8d; bAlertable
0x180005ee3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005ee6  mov     rcx, rbx; hHandle
0x180005ee9  call    cs:__imp_WaitForSingleObjectEx
0x180005eef  cmp     eax, 102h
0x180005ef4  jz      short loc_180005F06
0x180005ef6  test    eax, 0FFFFFF7Fh
0x180005efb  jnz     loc_180005FD5
0x180005f01  mov     rsi, rbx
0x180005f04  jmp     short loc_180005F08
0x180005f06  xor     esi, esi
0x180005f08  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180005f0d  mov     [rsp+270h+var_238], 0
0x180005f16  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180005f1b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005f20  mov     edi, eax
0x180005f22  test    eax, eax
0x180005f24  jns     short loc_180005F63
0x180005f26  mov     rcx, [rbp+178h]; this
0x180005f2d  lea     r8, aWil; "wil"
0x180005f34  mov     r9d, eax; char *
0x180005f37  mov     edx, 64h ; 'd'; void *
0x180005f3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f41  mov     rcx, [rbp+178h]; this
0x180005f48  lea     r8, aWil; "wil"
0x180005f4f  mov     r9d, edi; char *
0x180005f52  mov     edx, 6Dh ; 'm'; void *
0x180005f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f5c  mov     edx, 12Bh
0x180005f61  jmp     short loc_180005FBD
0x180005f63  mov     rax, [rsp+270h+var_238]
0x180005f68  lea     rcx, ds:0[rax*4]
0x180005f70  test    rcx, rcx
0x180005f73  jz      short loc_180005F9B
0x180005f75  mov     [r14], rcx
0x180005f78  mov     eax, [rcx]
0x180005f7a  inc     eax
0x180005f7c  mov     [rcx], eax
0x180005f7e  xor     edi, edi
0x180005f80  test    rsi, rsi
0x180005f83  jz      loc_180005EA1
0x180005f89  mov     rcx, rsi; hMutex
0x180005f8c  call    cs:__imp_ReleaseMutex
0x180005f92  test    eax, eax
0x180005f94  jz      short loc_180005FE2
0x180005f96  jmp     loc_180005EA1
0x180005f9b  mov     r8, r14
0x180005f9e  lea     rdx, [rsp+270h+var_240]
0x180005fa3  lea     rcx, [rsp+270h+Name]
0x180005fa8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180005fad  mov     rbx, [rsp+270h+var_240]
0x180005fb2  mov     edi, eax
0x180005fb4  test    eax, eax
0x180005fb6  jns     short loc_180005F7E
0x180005fb8  mov     edx, 134h; void *
0x180005fbd  mov     rcx, [rbp+178h]; this
0x180005fc4  lea     r8, aWil; "wil"
0x180005fcb  mov     r9d, edi; char *
0x180005fce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fd3  jmp     short loc_180005F80
0x180005fd5  mov     rcx, [rbp+178h]; this
0x180005fdc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005fe2  mov     rcx, [rbp+178h]; this
0x180005fe9  mov     edx, 9DBh; void *
0x180005fee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ff4  mov     rcx, [rbp+178h]; this
0x180005ffb  mov     edx, 9D1h; void *
0x180006000  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
