# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009ac4`
- end: `0x180009cba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800081a8`

## callees

- `0x1800060f8`
- `0x180006b60`
- `0x180007804`
- `0x180007848`
- `0x180007864`
- `0x180007cc4`
- `0x180009ac4`
- `0x180009ee4`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009b9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009b9d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009b3b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009b3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c40`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009aff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009aff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b5d`

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
0x180009ac4  mov     [rsp-8+arg_10], rbx
0x180009ac9  mov     [rsp-8+arg_18], rsi
0x180009ace  push    rbp
0x180009acf  push    rdi
0x180009ad0  push    r14
0x180009ad2  lea     rbp, [rsp-160h]
0x180009ada  sub     rsp, 260h
0x180009ae1  mov     rax, cs:__security_cookie
0x180009ae8  xor     rax, rsp
0x180009aeb  mov     [rbp+170h+var_20], rax
0x180009af2  mov     r14, rdx
0x180009af5  mov     qword ptr [rdx], 0
0x180009afc  mov     rbx, rcx
0x180009aff  call    cs:__imp_GetCurrentProcessId
0x180009b05  mov     [rsp+270h+var_248], rbx
0x180009b0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009b11  mov     r9d, eax
0x180009b14  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009b1c  mov     edx, 104h; unsigned __int64
0x180009b21  lea     rcx, [rsp+270h+Name]; Buffer
0x180009b26  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009b2b  mov     r9d, 1F0001h; dwDesiredAccess
0x180009b31  lea     rdx, [rsp+270h+Name]; lpName
0x180009b36  xor     r8d, r8d; dwFlags
0x180009b39  xor     ecx, ecx; lpMutexAttributes
0x180009b3b  call    cs:__imp_CreateMutexExW
0x180009b41  mov     [rsp+270h+var_240], rax
0x180009b46  mov     rbx, rax
0x180009b49  test    rax, rax
0x180009b4c  jnz     short loc_180009B94
0x180009b4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009b53  mov     edi, eax
0x180009b55  test    rbx, rbx
0x180009b58  jz      short loc_180009B6B
0x180009b5a  mov     rcx, rbx; hObject
0x180009b5d  call    cs:__imp_CloseHandle
0x180009b63  test    eax, eax
0x180009b65  jz      loc_180009CA8
0x180009b6b  mov     eax, edi
0x180009b6d  mov     rcx, [rbp+170h+var_20]
0x180009b74  xor     rcx, rsp; StackCookie
0x180009b77  call    __security_check_cookie
0x180009b7c  lea     r11, [rsp+270h+var_10]
0x180009b84  mov     rbx, [r11+30h]
0x180009b88  mov     rsi, [r11+38h]
0x180009b8c  mov     rsp, r11
0x180009b8f  pop     r14
0x180009b91  pop     rdi
0x180009b92  pop     rbp
0x180009b93  retn
0x180009b94  xor     r8d, r8d; bAlertable
0x180009b97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009b9a  mov     rcx, rbx; hHandle
0x180009b9d  call    cs:__imp_WaitForSingleObjectEx
0x180009ba3  cmp     eax, 102h
0x180009ba8  jz      short loc_180009BBA
0x180009baa  test    eax, 0FFFFFF7Fh
0x180009baf  jnz     loc_180009C89
0x180009bb5  mov     rsi, rbx
0x180009bb8  jmp     short loc_180009BBC
0x180009bba  xor     esi, esi
0x180009bbc  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180009bc1  mov     [rsp+270h+var_238], 0
0x180009bca  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009bcf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180009bd4  mov     edi, eax
0x180009bd6  test    eax, eax
0x180009bd8  jns     short loc_180009C17
0x180009bda  mov     rcx, [rbp+178h]; this
0x180009be1  lea     r8, aWil; "wil"
0x180009be8  mov     r9d, eax; char *
0x180009beb  mov     edx, 64h ; 'd'; void *
0x180009bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bf5  mov     rcx, [rbp+178h]; this
0x180009bfc  lea     r8, aWil; "wil"
0x180009c03  mov     r9d, edi; char *
0x180009c06  mov     edx, 6Dh ; 'm'; void *
0x180009c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c10  mov     edx, 12Bh
0x180009c15  jmp     short loc_180009C71
0x180009c17  mov     rax, [rsp+270h+var_238]
0x180009c1c  lea     rcx, ds:0[rax*4]
0x180009c24  test    rcx, rcx
0x180009c27  jz      short loc_180009C4F
0x180009c29  mov     [r14], rcx
0x180009c2c  mov     eax, [rcx]
0x180009c2e  inc     eax
0x180009c30  mov     [rcx], eax
0x180009c32  xor     edi, edi
0x180009c34  test    rsi, rsi
0x180009c37  jz      loc_180009B55
0x180009c3d  mov     rcx, rsi; hMutex
0x180009c40  call    cs:__imp_ReleaseMutex
0x180009c46  test    eax, eax
0x180009c48  jz      short loc_180009C96
0x180009c4a  jmp     loc_180009B55
0x180009c4f  mov     r8, r14
0x180009c52  lea     rdx, [rsp+270h+var_240]
0x180009c57  lea     rcx, [rsp+270h+Name]
0x180009c5c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009c61  mov     rbx, [rsp+270h+var_240]
0x180009c66  mov     edi, eax
0x180009c68  test    eax, eax
0x180009c6a  jns     short loc_180009C32
0x180009c6c  mov     edx, 134h; void *
0x180009c71  mov     rcx, [rbp+178h]; this
0x180009c78  lea     r8, aWil; "wil"
0x180009c7f  mov     r9d, edi; char *
0x180009c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c87  jmp     short loc_180009C34
0x180009c89  mov     rcx, [rbp+178h]; this
0x180009c90  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009c96  mov     rcx, [rbp+178h]; this
0x180009c9d  mov     edx, 9DBh; void *
0x180009ca2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ca8  mov     rcx, [rbp+178h]; this
0x180009caf  mov     edx, 9D1h; void *
0x180009cb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
