# Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)

- ea: `0x180022838`
- end: `0x180022946`
- name: `?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z`
- size: `270`
- prototype: `__int64 __fastcall(PHANDLE phNewToken, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002177c`
- `0x180022d2c`

## callees

- `0x1800142d4`
- `0x180022838`
- `0x180023690`
- `0x180023a8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800228b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800228b0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022859`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022859`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022904`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022904`

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
0x180022838  mov     [rsp+arg_0], rcx
0x18002283d  push    rbx
0x18002283e  push    rsi
0x18002283f  push    rdi
0x180022840  sub     rsp, 40h
0x180022844  mov     rdi, rcx
0x180022847  mov     [rsp+58h+var_28], 0
0x18002284f  mov     r8d, edx; dwProcessId
0x180022852  xor     edx, edx; bInheritHandle
0x180022854  mov     ecx, 1000h; dwDesiredAccess
0x180022859  call    cs:__imp_OpenProcess
0x18002285f  mov     rbx, rax
0x180022862  mov     [rsp+58h+arg_18], rax
0x180022867  mov     rcx, [rsp+58h]; this
0x18002286c  inc     rax
0x18002286f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180022875  jnz     short loc_180022889
0x180022877  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x18002287e  mov     edx, 297h; void *
0x180022883  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022889  mov     [rsp+58h+TokenHandle], 0
0x180022892  xor     edx, edx
0x180022894  lea     rcx, [rsp+58h+TokenHandle]
0x180022899  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002289e  mov     rsi, [rsp+58h]
0x1800228a3  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800228a8  mov     edx, 0Eh; DesiredAccess
0x1800228ad  mov     rcx, rbx; ProcessHandle
0x1800228b0  call    cs:__imp_OpenProcessToken
0x1800228b6  test    eax, eax
0x1800228b8  jnz     short loc_1800228CF
0x1800228ba  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800228c1  mov     edx, 299h; void *
0x1800228c6  mov     rcx, rsi; this
0x1800228c9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800228cf  mov     qword ptr [rdi], 0
0x1800228d6  mov     [rsp+58h+var_28], 1
0x1800228de  xor     edx, edx
0x1800228e0  mov     rcx, rdi
0x1800228e3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800228e8  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x1800228ed  mov     r9d, 2; ImpersonationLevel
0x1800228f3  mov     [rsp+58h+TokenType], r9d; TokenType
0x1800228f8  xor     r8d, r8d; lpTokenAttributes
0x1800228fb  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800228ff  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x180022904  call    cs:__imp_DuplicateTokenEx
0x18002290a  mov     rcx, [rsp+58h]; this
0x18002290f  test    eax, eax
0x180022911  jnz     short loc_180022925
0x180022913  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x18002291a  mov     edx, 2A3h; void *
0x18002291f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022925  lea     rcx, [rsp+58h+TokenHandle]
0x18002292a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002292f  nop
0x180022930  lea     rcx, [rsp+58h+arg_18]
0x180022935  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002293a  mov     rax, rdi
0x18002293d  add     rsp, 40h
0x180022941  pop     rdi
0x180022942  pop     rsi
0x180022943  pop     rbx
0x180022944  retn
```
