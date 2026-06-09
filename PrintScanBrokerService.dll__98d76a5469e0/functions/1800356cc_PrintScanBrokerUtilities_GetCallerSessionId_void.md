# PrintScanBrokerUtilities::GetCallerSessionId(void)

- ea: `0x1800356cc`
- end: `0x180035791`
- name: `?GetCallerSessionId@PrintScanBrokerUtilities@@YAKXZ`
- size: `197`
- prototype: `unsigned int __fastcall(PrintScanBrokerUtilities *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022b44`

## callees

- `0x18001255c`
- `0x180023264`
- `0x180027cb4`
- `0x18002f194`
- `0x1800356cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003575e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003575e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035709`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035709`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003573d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003573d`

## string_xrefs

- `0x18003576d`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x18003577f`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintScanBrokerUtilities::GetCallerSessionId(PrintScanBrokerUtilities *this)
{
  HANDLE CurrentThread; // rax
  const char *v2; // r9
  const char *v3; // r9
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  char v7; // [rsp+50h] [rbp+18h] BYREF
  unsigned int TokenInformation; // [rsp+58h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+30h] BYREF

  wil::CoImpersonateClient(&v7);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v2);
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v3);
  v4 = TokenInformation;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v7 )
    CoRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x1800356cc  push    rbp
0x1800356ce  push    rbx
0x1800356cf  mov     rbp, rsp
0x1800356d2  sub     rsp, 38h
0x1800356d6  lea     rcx, [rbp+arg_0]
0x1800356da  call    ?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ; wil::CoImpersonateClient(void)
0x1800356df  nop
0x1800356e0  mov     [rbp+TokenHandle], 0
0x1800356e8  xor     edx, edx
0x1800356ea  lea     rcx, [rbp+TokenHandle]
0x1800356ee  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800356f3  call    cs:__imp_GetCurrentThread
0x1800356f9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800356fd  mov     edx, 8; DesiredAccess
0x180035702  lea     r8d, [rdx-7]; OpenAsSelf
0x180035706  mov     rcx, rax; ThreadHandle
0x180035709  call    cs:__imp_OpenThreadToken
0x18003570f  mov     rcx, [rbp+10h]; this
0x180035713  test    eax, eax
0x180035715  jz      short loc_18003577F
0x180035717  mov     [rbp+TokenInformation], 0
0x18003571e  mov     r9d, 4; TokenInformationLength
0x180035724  mov     [rbp+arg_10], r9d
0x180035728  lea     rax, [rbp+arg_10]
0x18003572c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180035731  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180035735  lea     edx, [r9+8]; TokenInformationClass
0x180035739  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003573d  call    cs:__imp_GetTokenInformation
0x180035743  mov     rcx, [rbp+10h]; this
0x180035747  test    eax, eax
0x180035749  jz      short loc_18003576D
0x18003574b  mov     ebx, [rbp+TokenInformation]
0x18003574e  lea     rcx, [rbp+TokenHandle]
0x180035752  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180035757  nop
0x180035758  cmp     [rbp+arg_0], 0
0x18003575c  jz      short loc_180035764
0x18003575e  call    cs:__imp_CoRevertToSelf
0x180035764  mov     eax, ebx
0x180035766  add     rsp, 38h
0x18003576a  pop     rbx
0x18003576b  pop     rbp
0x18003576c  retn
0x18003576d  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x180035774  mov     edx, 3Bh ; ';'; void *
0x180035779  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003577f  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x180035786  mov     edx, 37h ; '7'; void *
0x18003578b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
