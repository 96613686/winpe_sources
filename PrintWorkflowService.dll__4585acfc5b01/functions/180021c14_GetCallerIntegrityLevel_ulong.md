# GetCallerIntegrityLevel(ulong &)

- ea: `0x180021c14`
- end: `0x180021dee`
- name: `?GetCallerIntegrityLevel@@YAJAEAK@Z`
- size: `474`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800239c8`
- `0x180042dc8`

## callees

- `0x1800127a4`
- `0x1800127c4`
- `0x1800166a8`
- `0x18001a704`
- `0x180021c14`
- `0x180023664`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180021d48`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180021d48`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180021c21`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180021c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021c42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021c42`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021c59`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021c59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021cba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021cba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d36`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021d16`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021d16`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180021d08`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180021d08`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021cf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021cf2`

## string_xrefs

- `0x180021d64`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180021d76`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021d8d`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021da1`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021db6`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021dc7`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021ddb`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
__int64 __fastcall GetCallerIntegrityLevel(unsigned int *a1)
{
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  const char *v5; // r9
  PSID *v6; // rbx
  const char *v7; // r9
  const char *v8; // r9
  PUCHAR SidSubAuthorityCount; // rax
  DWORD LastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  unsigned int ReturnLengthb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      ReturnLength);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v4);
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)0x80004005LL,
      ReturnLengtha);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v5);
  v6 = (PSID *)LocalAlloc(0, TokenInformationLength);
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v7);
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v8);
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v6);
  *a1 = *GetSidSubAuthority(*v6, (unsigned int)*SidSubAuthorityCount - 1);
  LastError = GetLastError();
  if ( LastError )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)LastError,
      ReturnLengthb);
  LocalFree(v6);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180021c14  mov     [rsp+arg_0], rbx
0x180021c19  push    rdi
0x180021c1a  sub     rsp, 40h
0x180021c1e  mov     rdi, rcx
0x180021c21  call    cs:__imp_CoImpersonateClient
0x180021c27  mov     rcx, [rsp+48h]; this
0x180021c2c  test    eax, eax
0x180021c2e  js      loc_180021D61
0x180021c34  mov     byte ptr [rsp+48h+arg_8], 1
0x180021c39  mov     [rsp+48h+TokenHandle], 0
0x180021c42  call    cs:__imp_GetCurrentThread
0x180021c48  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180021c4d  mov     edx, 8; DesiredAccess
0x180021c52  lea     r8d, [rdx-7]; OpenAsSelf
0x180021c56  mov     rcx, rax; ThreadHandle
0x180021c59  call    cs:__imp_OpenThreadToken
0x180021c5f  mov     rcx, [rsp+48h]; this
0x180021c64  test    eax, eax
0x180021c66  jz      loc_180021D76
0x180021c6c  mov     [rsp+48h+TokenInformationLength], 0
0x180021c74  mov     rbx, [rsp+48h]
0x180021c79  lea     rax, [rsp+48h+TokenInformationLength]
0x180021c7e  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x180021c83  xor     r9d, r9d; TokenInformationLength
0x180021c86  xor     r8d, r8d; TokenInformation
0x180021c89  lea     edx, [r9+19h]; TokenInformationClass
0x180021c8d  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180021c92  call    cs:__imp_GetTokenInformation
0x180021c98  test    eax, eax
0x180021c9a  jnz     loc_180021D87
0x180021ca0  mov     rbx, [rsp+48h]
0x180021ca5  call    cs:__imp_GetLastError
0x180021cab  cmp     eax, 7Ah ; 'z'
0x180021cae  jnz     loc_180021DA1
0x180021cb4  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x180021cb8  xor     ecx, ecx; uFlags
0x180021cba  call    cs:__imp_LocalAlloc
0x180021cc0  mov     rbx, rax
0x180021cc3  mov     [rsp+48h+var_18], rax
0x180021cc8  mov     rcx, [rsp+48h]; this
0x180021ccd  test    rax, rax
0x180021cd0  jz      loc_180021DB6
0x180021cd6  lea     rax, [rsp+48h+TokenInformationLength]
0x180021cdb  mov     qword ptr [rsp+48h+ReturnLength], rax; unsigned int
0x180021ce0  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180021ce5  mov     r8, rbx; TokenInformation
0x180021ce8  mov     edx, 19h; TokenInformationClass
0x180021ced  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180021cf2  call    cs:__imp_GetTokenInformation
0x180021cf8  mov     rcx, [rsp+48h]; this
0x180021cfd  test    eax, eax
0x180021cff  jz      loc_180021DC7
0x180021d05  mov     rcx, [rbx]; pSid
0x180021d08  call    cs:__imp_GetSidSubAuthorityCount
0x180021d0e  movzx   edx, byte ptr [rax]
0x180021d11  dec     edx; nSubAuthority
0x180021d13  mov     rcx, [rbx]; pSid
0x180021d16  call    cs:__imp_GetSidSubAuthority
0x180021d1c  mov     ecx, [rax]
0x180021d1e  mov     [rdi], ecx
0x180021d20  call    cs:__imp_GetLastError
0x180021d26  mov     rcx, [rsp+48h]; this
0x180021d2b  test    eax, eax
0x180021d2d  jnz     loc_180021DD8
0x180021d33  mov     rcx, rbx; hMem
0x180021d36  call    cs:__imp_LocalFree
0x180021d3c  nop
0x180021d3d  lea     rcx, [rsp+48h+TokenHandle]
0x180021d42  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021d47  nop
0x180021d48  call    cs:__imp_CoRevertToSelf
0x180021d4e  xor     eax, eax
0x180021d50  jmp     short loc_180021D56
0x180021d52  mov     eax, [rsp+48h+arg_8]
0x180021d56  mov     rbx, [rsp+48h+arg_0]
0x180021d5b  add     rsp, 40h
0x180021d5f  pop     rdi
0x180021d60  retn
0x180021d61  mov     r9d, eax; char *
0x180021d64  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d6b  mov     edx, 14B1h; void *
0x180021d70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021d76  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021d7d  mov     edx, 232h; void *
0x180021d82  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180021d87  mov     r9d, 80004005h; char *
0x180021d8d  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021d94  mov     edx, 236h; void *
0x180021d99  mov     rcx, rbx; this
0x180021d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021da1  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021da8  mov     edx, 238h; void *
0x180021dad  mov     rcx, rbx; this
0x180021db0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180021db6  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021dbd  mov     edx, 23Bh; void *
0x180021dc2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021dc7  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021dce  mov     edx, 23Dh; void *
0x180021dd3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180021dd8  mov     r9d, eax; char *
0x180021ddb  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021de2  mov     edx, 245h; void *
0x180021de7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
