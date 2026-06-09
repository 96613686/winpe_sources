# Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)

- ea: `0x180042c4c`
- end: `0x180042d5a`
- name: `?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z`
- size: `270`
- prototype: `__int64 __fastcall(PHANDLE phNewToken, DWORD dwProcessId)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003fdf4`
- `0x180043538`
- `0x180044590`
- `0x180044614`
- `0x18004f7d4`
- `0x18005ef00`
- `0x180064304`
- `0x18006ae88`
- `0x18006c6f4`
- `0x1800901e0`

## callees

- `0x180039e9c`
- `0x18003f4a0`
- `0x180042c4c`
- `0x1800464d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042cc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042cc4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042c6d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042c6d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180042d18`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180042d18`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PHANDLE __fastcall Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(
        PHANDLE phNewToken,
        DWORD dwProcessId)
{
  HANDLE v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  HANDLE v10; // [rsp+78h] [rbp+20h] BYREF

  v3 = OpenProcess(0x1000u, 0, dwProcessId);
  v10 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( !OpenProcessToken(v3, 0xEu, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  *phNewToken = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    phNewToken,
    0);
  if ( !DuplicateTokenEx(TokenHandle, 0xEu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v6);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  return phNewToken;
}

```

## disassembly

```asm
0x180042c4c  mov     [rsp+arg_0], rcx
0x180042c51  push    rbx
0x180042c52  push    rsi
0x180042c53  push    rdi
0x180042c54  sub     rsp, 40h
0x180042c58  mov     rdi, rcx
0x180042c5b  mov     [rsp+58h+var_28], 0
0x180042c63  mov     r8d, edx; dwProcessId
0x180042c66  xor     edx, edx; bInheritHandle
0x180042c68  mov     ecx, 1000h; dwDesiredAccess
0x180042c6d  call    cs:__imp_OpenProcess
0x180042c73  mov     rbx, rax
0x180042c76  mov     [rsp+58h+arg_18], rax
0x180042c7b  mov     rcx, [rsp+58h]; this
0x180042c80  inc     rax
0x180042c83  test    rax, 0FFFFFFFFFFFFFFFEh
0x180042c89  jnz     short loc_180042C9D
0x180042c8b  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042c92  mov     edx, 297h; void *
0x180042c97  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042c9d  mov     [rsp+58h+TokenHandle], 0
0x180042ca6  xor     edx, edx
0x180042ca8  lea     rcx, [rsp+58h+TokenHandle]
0x180042cad  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042cb2  mov     rsi, [rsp+58h]
0x180042cb7  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180042cbc  mov     edx, 0Eh; DesiredAccess
0x180042cc1  mov     rcx, rbx; ProcessHandle
0x180042cc4  call    cs:__imp_OpenProcessToken
0x180042cca  test    eax, eax
0x180042ccc  jnz     short loc_180042CE3
0x180042cce  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042cd5  mov     edx, 299h; void *
0x180042cda  mov     rcx, rsi; this
0x180042cdd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042ce3  mov     qword ptr [rdi], 0
0x180042cea  mov     [rsp+58h+var_28], 1
0x180042cf2  xor     edx, edx
0x180042cf4  mov     rcx, rdi
0x180042cf7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042cfc  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x180042d01  mov     r9d, 2; ImpersonationLevel
0x180042d07  mov     [rsp+58h+TokenType], r9d; TokenType
0x180042d0c  xor     r8d, r8d; lpTokenAttributes
0x180042d0f  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180042d13  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x180042d18  call    cs:__imp_DuplicateTokenEx
0x180042d1e  mov     rcx, [rsp+58h]; this
0x180042d23  test    eax, eax
0x180042d25  jnz     short loc_180042D39
0x180042d27  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042d2e  mov     edx, 2A3h; void *
0x180042d33  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042d39  lea     rcx, [rsp+58h+TokenHandle]
0x180042d3e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042d43  nop
0x180042d44  lea     rcx, [rsp+58h+arg_18]
0x180042d49  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042d4e  mov     rax, rdi
0x180042d51  add     rsp, 40h
0x180042d55  pop     rdi
0x180042d56  pop     rsi
0x180042d57  pop     rbx
0x180042d58  retn
```
