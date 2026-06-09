# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000d82c`
- end: `0x18000da40`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180005700`

## callees

- `0x180006390`
- `0x18000d82c`
- `0x18000dcdc`
- `0x18000e124`
- `0x18000e150`
- `0x18000e49c`
- `0x18002477c`
- `0x1800264cc`
- `0x18002a030`
- `0x18002c138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d8a3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d8a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d8c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d8c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d867`

## string_xrefs

- `0x18000d8e4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  void *v15; // rdx
  _DWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
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
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v21);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v15);
    wil::details::CloseHandle(v6, v15);
    return v14;
  }
  v16 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    *a2 = v16;
    ++*v16;
LABEL_21:
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v6 = v22;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 120);
  if ( v11 )
    wil::details::ReleaseMutex(v11, v19);
  if ( v22 )
    wil::details::CloseHandle(v22, v19);
  return v18;
}

```

## disassembly

```asm
0x18000d82c  mov     [rsp-8+arg_10], rbx
0x18000d831  mov     [rsp-8+arg_18], rsi
0x18000d836  push    rbp
0x18000d837  push    rdi
0x18000d838  push    r14
0x18000d83a  lea     rbp, [rsp-160h]
0x18000d842  sub     rsp, 260h
0x18000d849  mov     rax, cs:__security_cookie
0x18000d850  xor     rax, rsp
0x18000d853  mov     [rbp+170h+var_20], rax
0x18000d85a  mov     r14, rdx
0x18000d85d  mov     qword ptr [rdx], 0
0x18000d864  mov     rbx, rcx
0x18000d867  call    cs:__imp_GetCurrentProcessId
0x18000d86d  mov     [rsp+270h+var_248], rbx
0x18000d872  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d879  mov     r9d, eax
0x18000d87c  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000d884  mov     edx, 104h; unsigned __int64
0x18000d889  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d88e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d893  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d899  lea     rdx, [rsp+270h+Name]; lpName
0x18000d89e  xor     r8d, r8d; dwFlags
0x18000d8a1  xor     ecx, ecx; lpMutexAttributes
0x18000d8a3  call    cs:__imp_CreateMutexExW
0x18000d8a9  mov     [rsp+270h+var_240], rax
0x18000d8ae  mov     rbx, rax
0x18000d8b1  test    rax, rax
0x18000d8b4  jnz     short loc_18000D8C0
0x18000d8b6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d8bb  jmp     loc_18000DA19
0x18000d8c0  xor     r8d, r8d; bAlertable
0x18000d8c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d8c6  mov     rcx, rbx; hHandle
0x18000d8c9  call    cs:__imp_WaitForSingleObjectEx
0x18000d8cf  cmp     eax, 102h
0x18000d8d4  jz      short loc_18000D8FB
0x18000d8d6  test    eax, 0FFFFFF7Fh
0x18000d8db  jz      short loc_18000D8F6
0x18000d8dd  mov     rcx, [rbp+178h]; this
0x18000d8e4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d8eb  mov     edx, 0E01h; void *
0x18000d8f0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d8f6  mov     rdi, rbx
0x18000d8f9  jmp     short loc_18000D8FD
0x18000d8fb  xor     edi, edi
0x18000d8fd  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000d902  mov     [rsp+270h+var_238], 0
0x18000d90b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d910  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000d915  mov     esi, eax
0x18000d917  test    eax, eax
0x18000d919  jns     short loc_18000D988
0x18000d91b  mov     rcx, [rbp+178h]; this
0x18000d922  lea     r8, aWil; "wil"
0x18000d929  mov     r9d, eax; char *
0x18000d92c  mov     edx, 66h ; 'f'; void *
0x18000d931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d936  mov     rcx, [rbp+178h]; this
0x18000d93d  lea     r8, aWil; "wil"
0x18000d944  mov     r9d, esi; char *
0x18000d947  mov     edx, 6Fh ; 'o'; void *
0x18000d94c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d951  mov     rcx, [rbp+178h]; this
0x18000d958  lea     r8, aWil; "wil"
0x18000d95f  mov     r9d, esi; char *
0x18000d962  mov     edx, 12Eh; void *
0x18000d967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d96c  test    rdi, rdi
0x18000d96f  jz      short loc_18000D979
0x18000d971  mov     rcx, rdi; this
0x18000d974  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000d979  mov     rcx, rbx; this
0x18000d97c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d981  mov     eax, esi
0x18000d983  jmp     loc_18000DA19
0x18000d988  mov     rax, [rsp+270h+var_238]
0x18000d98d  lea     rcx, ds:0[rax*4]
0x18000d995  test    rcx, rcx
0x18000d998  jz      short loc_18000D9A5
0x18000d99a  mov     [r14], rcx
0x18000d99d  mov     eax, [rcx]
0x18000d99f  inc     eax
0x18000d9a1  mov     [rcx], eax
0x18000d9a3  jmp     short loc_18000D9FD
0x18000d9a5  mov     r8, r14
0x18000d9a8  lea     rdx, [rsp+270h+var_240]
0x18000d9ad  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d9b2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d9b7  mov     ebx, eax
0x18000d9b9  test    eax, eax
0x18000d9bb  jns     short loc_18000D9F8
0x18000d9bd  mov     rcx, [rbp+178h]; this
0x18000d9c4  lea     r8, aWil; "wil"
0x18000d9cb  mov     r9d, eax; char *
0x18000d9ce  mov     edx, 137h; void *
0x18000d9d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9d8  test    rdi, rdi
0x18000d9db  jz      short loc_18000D9E5
0x18000d9dd  mov     rcx, rdi; this
0x18000d9e0  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000d9e5  mov     rcx, [rsp+270h+var_240]; this
0x18000d9ea  test    rcx, rcx
0x18000d9ed  jz      short loc_18000D9F4
0x18000d9ef  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d9f4  mov     eax, ebx
0x18000d9f6  jmp     short loc_18000DA19
0x18000d9f8  mov     rbx, [rsp+270h+var_240]
0x18000d9fd  test    rdi, rdi
0x18000da00  jz      short loc_18000DA0A
0x18000da02  mov     rcx, rdi; this
0x18000da05  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000da0a  test    rbx, rbx
0x18000da0d  jz      short loc_18000DA17
0x18000da0f  mov     rcx, rbx; this
0x18000da12  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000da17  xor     eax, eax
0x18000da19  mov     rcx, [rbp+170h+var_20]
0x18000da20  xor     rcx, rsp; StackCookie
0x18000da23  call    __security_check_cookie
0x18000da28  lea     r11, [rsp+270h+var_10]
0x18000da30  mov     rbx, [r11+30h]
0x18000da34  mov     rsi, [r11+38h]
0x18000da38  mov     rsp, r11
0x18000da3b  pop     r14
0x18000da3d  pop     rdi
0x18000da3e  pop     rbp
0x18000da3f  retn
```
