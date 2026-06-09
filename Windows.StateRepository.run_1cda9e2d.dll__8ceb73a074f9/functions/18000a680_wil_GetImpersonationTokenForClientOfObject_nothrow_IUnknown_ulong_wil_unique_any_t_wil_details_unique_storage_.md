# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18000a680`
- end: `0x18000a82b`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `427`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ad70`
- `0x1800fb6f0`
- `0x180135750`
- `0x180138130`

## callees

- `0x18000a680`
- `0x18000e8dc`
- `0x18001a9e0`
- `0x18004f534`
- `0x1800b4dbc`
- `0x1800bee58`
- `0x1801cff44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a6cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a6cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a7a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a7a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a6e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a6e3`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000a69d`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18000a69d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a7de`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a7de`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a6f5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a75d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a6f5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a75d`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v6; // bl
  HANDLE CurrentThread; // rax
  unsigned int v9; // edi
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v17; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v17);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v6 = v17 != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, a3) )
    goto LABEL_5;
  LastError = GetLastError();
  if ( !v6 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x2000Au, &TokenHandle) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a3,
        0);
      if ( DuplicateTokenEx(TokenHandle, 0x20008u, 0, SecurityImpersonation, TokenImpersonation, a3) )
      {
        wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return 0;
      }
      v13 = 388;
    }
    else
    {
      v13 = 386;
    }
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v13,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
           v12);
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v5;
  }
  if ( !LastError )
  {
LABEL_5:
    if ( v6 )
      CoRevertToSelf();
    return 0;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x188,
         (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
         (const char *)LastError,
         TokenType);
  if ( v6 )
    CoRevertToSelf();
  return v9;
}

```

## disassembly

```asm
0x18000a680  mov     rax, rsp
0x18000a683  mov     [rax+8], rbx
0x18000a687  mov     [rax+10h], edx
0x18000a68a  push    rdi
0x18000a68b  sub     rsp, 30h
0x18000a68f  lea     rdx, [rax+10h]
0x18000a693  mov     dword ptr [rax+10h], 0
0x18000a69a  mov     rdi, r8
0x18000a69d  call    cs:__imp_CoImpersonateClientOfObject
0x18000a6a3  mov     ebx, eax
0x18000a6a5  test    eax, eax
0x18000a6a7  js      short loc_18000A708
0x18000a6a9  xor     bl, bl
0x18000a6ab  cmp     [rsp+38h+arg_8], 0
0x18000a6b0  jz      short loc_18000A6B4
0x18000a6b2  mov     bl, 1
0x18000a6b4  mov     rcx, [rdi]; hObject
0x18000a6b7  lea     rax, [rcx-1]
0x18000a6bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a6bf  jbe     loc_18000A767
0x18000a6c5  mov     qword ptr [rdi], 0
0x18000a6cc  call    cs:__imp_GetCurrentThread
0x18000a6d2  mov     r9, rdi; TokenHandle
0x18000a6d5  mov     edx, 20008h; DesiredAccess
0x18000a6da  mov     rcx, rax; ThreadHandle
0x18000a6dd  mov     r8d, 1; OpenAsSelf
0x18000a6e3  call    cs:__imp_OpenThreadToken
0x18000a6e9  test    eax, eax
0x18000a6eb  jz      loc_18000A771
0x18000a6f1  test    bl, bl
0x18000a6f3  jz      short loc_18000A6FB
0x18000a6f5  call    cs:__imp_CoRevertToSelf
0x18000a6fb  xor     eax, eax
0x18000a6fd  mov     rbx, [rsp+38h+arg_0]
0x18000a702  add     rsp, 30h
0x18000a706  pop     rdi
0x18000a707  retn
0x18000a708  mov     rcx, [rsp+38h]; this
0x18000a70d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18000a714  mov     r9d, ebx; char *
0x18000a717  mov     edx, 157h; void *
0x18000a71c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a721  mov     rcx, [rsp+38h]; this
0x18000a726  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18000a72d  mov     r9d, ebx; char *
0x18000a730  mov     edx, 177h; void *
0x18000a735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a73a  mov     eax, ebx
0x18000a73c  jmp     short loc_18000A6FD
0x18000a73e  mov     rcx, [rsp+38h]; this
0x18000a743  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18000a74a  mov     r9d, eax; char *
0x18000a74d  mov     edx, 188h; void *
0x18000a752  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a757  mov     edi, eax
0x18000a759  test    bl, bl
0x18000a75b  jz      short loc_18000A763
0x18000a75d  call    cs:__imp_CoRevertToSelf
0x18000a763  mov     eax, edi
0x18000a765  jmp     short loc_18000A6FD
0x18000a767  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000a76c  jmp     loc_18000A6C5
0x18000a771  call    cs:__imp_GetLastError
0x18000a777  test    bl, bl
0x18000a779  jnz     loc_18000A81E
0x18000a77f  cmp     eax, 3F0h
0x18000a784  jnz     loc_18000A81E
0x18000a78a  mov     [rsp+38h+TokenHandle], 0
0x18000a793  call    cs:__imp_GetCurrentProcess
0x18000a799  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18000a79e  mov     edx, 2000Ah; DesiredAccess
0x18000a7a3  mov     rcx, rax; ProcessHandle
0x18000a7a6  call    cs:__imp_OpenProcessToken
0x18000a7ac  test    eax, eax
0x18000a7ae  jnz     short loc_18000A7B7
0x18000a7b0  mov     edx, 182h
0x18000a7b5  jmp     short loc_18000A7ED
0x18000a7b7  xor     edx, edx
0x18000a7b9  mov     rcx, rdi
0x18000a7bc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000a7c1  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18000a7c6  mov     r9d, 2; ImpersonationLevel
0x18000a7cc  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18000a7d1  xor     r8d, r8d; lpTokenAttributes
0x18000a7d4  mov     edx, 20008h; dwDesiredAccess
0x18000a7d9  mov     [rsp+38h+TokenType], r9d; TokenType
0x18000a7de  call    cs:__imp_DuplicateTokenEx
0x18000a7e4  test    eax, eax
0x18000a7e6  jnz     short loc_18000A80F
0x18000a7e8  mov     edx, 184h; void *
0x18000a7ed  mov     rcx, [rsp+38h]; this
0x18000a7f2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18000a7f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a7fe  lea     rcx, [rsp+38h+TokenHandle]
0x18000a803  mov     ebx, eax
0x18000a805  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a80a  jmp     loc_18000A73A
0x18000a80f  lea     rcx, [rsp+38h+TokenHandle]
0x18000a814  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a819  jmp     loc_18000A6FB
0x18000a81e  test    eax, eax
0x18000a820  jz      loc_18000A6F1
0x18000a826  jmp     loc_18000A73E
```
