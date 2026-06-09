# TokenUtility::CreateUserTokenForSplWoW64(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180030cb0`
- end: `0x180030de7`
- name: `?CreateUserTokenForSplWoW64@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `311`
- prototype: `void **__fastcall(__int64, void **, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800329dc`

## callees

- `0x18001255c`
- `0x18001d058`
- `0x18001d0a0`
- `0x180023264`
- `0x1800291d0`
- `0x1800321f8`
- `0x180032738`
- `0x1800327ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030d36`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180030d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180030d1f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030dbf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030dbf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030d88`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030d88`

## string_xrefs

- `0x180030ce5`: `ImpersonateUser failed!`
- `0x180030cf4`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030d50`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030da2`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030d93`: `DuplicateTokenEx failed!`
- `0x180030d41`: `OpenThreadToken failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall TokenUtility::CreateUserTokenForSplWoW64(__int64 a1, void **a2, __int64 a3)
{
  unsigned int v4; // eax
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  TokenUtility *v8; // rcx
  TokenUtility *v9; // rcx
  TokenUtility *v10; // rcx
  const char *phNewToken; // [rsp+28h] [rbp-20h]
  const char *phNewTokena; // [rsp+28h] [rbp-20h]
  const char *phNewTokenb; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  v4 = PrintCore::UserImpersonationHelpers::ImpersonateUser(a3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1F,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v4,
    (int)"ImpersonateUser failed!",
    phNewToken);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x26,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v6,
    (int)"OpenThreadToken failed!",
    phNewTokena);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  v7 = DuplicateTokenEx(TokenHandle, 0x8Fu, 0, SecurityImpersonation, TokenImpersonation, a2);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v7,
    (int)"DuplicateTokenEx failed!",
    phNewTokenb);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  RevertToSelf();
  TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(v8, *a2);
  TokenUtility::_ElevateTokenToMedium(v9, *a2);
  TokenUtility::_RemoveAttributesForSplWoW64Token(v10, *a2);
  return a2;
}

```

## disassembly

```asm
0x180030cb0  mov     rax, rsp
0x180030cb3  mov     [rax+10h], rdx
0x180030cb7  mov     [rax+8], rcx
0x180030cbb  push    rbx
0x180030cbc  sub     rsp, 40h
0x180030cc0  mov     rbx, rdx
0x180030cc3  mov     dword ptr [rax-18h], 0
0x180030cca  mov     qword ptr [rdx], 0
0x180030cd1  mov     dword ptr [rax-18h], 1
0x180030cd8  mov     rcx, r8
0x180030cdb  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180030ce0  mov     rcx, [rsp+48h]; this
0x180030ce5  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180030cec  mov     qword ptr [rsp+48h+TokenType], rdx; int
0x180030cf1  mov     r9d, eax; char *
0x180030cf4  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030cfb  mov     edx, 1Fh; void *
0x180030d00  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030d05  mov     [rsp+48h+arg_1], 1
0x180030d0a  mov     [rsp+48h+TokenHandle], 0
0x180030d13  xor     edx, edx
0x180030d15  lea     rcx, [rsp+48h+TokenHandle]
0x180030d1a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030d1f  call    cs:__imp_GetCurrentThread
0x180030d25  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180030d2a  mov     edx, 0Eh; DesiredAccess
0x180030d2f  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180030d33  mov     rcx, rax; ThreadHandle
0x180030d36  call    cs:__imp_OpenThreadToken
0x180030d3c  mov     rcx, [rsp+48h]; this
0x180030d41  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed!"
0x180030d48  mov     qword ptr [rsp+48h+TokenType], rdx; int
0x180030d4d  mov     r9d, eax; char *
0x180030d50  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030d57  mov     edx, 26h ; '&'; void *
0x180030d5c  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180030d61  xor     edx, edx
0x180030d63  mov     rcx, rbx
0x180030d66  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030d6b  mov     [rsp+48h+phNewToken], rbx; char *
0x180030d70  mov     r9d, 2; ImpersonationLevel
0x180030d76  mov     [rsp+48h+TokenType], r9d; TokenType
0x180030d7b  xor     r8d, r8d; lpTokenAttributes
0x180030d7e  mov     edx, 8Fh; dwDesiredAccess
0x180030d83  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x180030d88  call    cs:__imp_DuplicateTokenEx
0x180030d8e  mov     rcx, [rsp+48h]; this
0x180030d93  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed!"
0x180030d9a  mov     qword ptr [rsp+48h+TokenType], rdx; int
0x180030d9f  mov     r9d, eax; char *
0x180030da2  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030da9  mov     edx, 2Ch ; ','; void *
0x180030dae  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180030db3  nop
0x180030db4  lea     rcx, [rsp+48h+TokenHandle]
0x180030db9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030dbe  nop
0x180030dbf  call    cs:__imp_RevertToSelf
0x180030dc5  mov     rdx, [rbx]; void *
0x180030dc8  call    ?_SetTokenAsEnterpriseExemptIfNeeded@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(void *)
0x180030dcd  mov     rdx, [rbx]; void *
0x180030dd0  call    ?_ElevateTokenToMedium@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_ElevateTokenToMedium(void *)
0x180030dd5  mov     rdx, [rbx]; void *
0x180030dd8  call    ?_RemoveAttributesForSplWoW64Token@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_RemoveAttributesForSplWoW64Token(void *)
0x180030ddd  mov     rax, rbx
0x180030de0  add     rsp, 40h
0x180030de4  pop     rbx
0x180030de5  retn
```
