# GetIntegrityLevel(void)

- ea: `0x14000cb10`
- end: `0x14000cc37`
- name: `?GetIntegrityLevel@@YAKXZ`
- size: `295`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d884`

## callees

- `0x14000589c`
- `0x140007764`
- `0x14000c670`
- `0x14000cb10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cb93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cb93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cb84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cb84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000cb23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000cb23`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000cb36`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000cb36`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000cbd9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14000cbd9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14000cc0b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14000cc0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000cb7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000cbb5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000cb7a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000cbb5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14000cbfd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14000cbfd`

## string_xrefs

- `0x14000cb45`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`
- `0x14000cbc4`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`
- `0x14000cbe8`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`

## pseudocode

```c
__int64 GetIntegrityLevel(void)
{
  HANDLE CurrentProcess; // rax
  const char *v1; // r9
  DWORD v2; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v4; // rbx
  const char *v5; // r9
  const char *v6; // r9
  PUCHAR SidSubAuthorityCount; // rax
  void *v8; // rdx
  DWORD v9; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
      v1);
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength);
  v2 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v4 = (PSID *)HeapAlloc(ProcessHeap, 8u, v2);
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
      v5);
  if ( !IsValidSid(*v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
      v6);
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
  v9 = *GetSidSubAuthority(*v4, (unsigned int)*SidSubAuthorityCount - 1);
  if ( v4 )
    wil::details::FreeProcessHeap((wil::details *)v4, v8);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x14000cb10  mov     [rsp+arg_10], rbx
0x14000cb15  push    rdi
0x14000cb16  sub     rsp, 30h
0x14000cb1a  mov     [rsp+38h+TokenHandle], 0
0x14000cb23  call    cs:__imp_GetCurrentProcess
0x14000cb29  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x14000cb2e  mov     edx, 8; DesiredAccess
0x14000cb33  mov     rcx, rax; ProcessHandle
0x14000cb36  call    cs:__imp_OpenProcessToken
0x14000cb3c  test    eax, eax
0x14000cb3e  jnz     short loc_14000CB57
0x14000cb40  mov     rcx, [rsp+38h]; this
0x14000cb45  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000cb4c  mov     edx, 10Ch; void *
0x14000cb51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000cb57  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x14000cb5c  lea     rax, [rsp+38h+TokenInformationLength]
0x14000cb61  xor     r9d, r9d; TokenInformationLength
0x14000cb64  mov     [rsp+38h+TokenInformationLength], 0
0x14000cb6c  xor     r8d, r8d; TokenInformation
0x14000cb6f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14000cb74  lea     edi, [r9+19h]
0x14000cb78  mov     edx, edi; TokenInformationClass
0x14000cb7a  call    cs:__imp_GetTokenInformation
0x14000cb80  mov     ebx, [rsp+38h+TokenInformationLength]
0x14000cb84  call    cs:__imp_GetProcessHeap
0x14000cb8a  mov     r8d, ebx; dwBytes
0x14000cb8d  lea     edx, [rdi-11h]; dwFlags
0x14000cb90  mov     rcx, rax; hHeap
0x14000cb93  call    cs:__imp_HeapAlloc
0x14000cb99  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14000cb9e  mov     edx, edi; TokenInformationClass
0x14000cba0  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x14000cba5  mov     rbx, rax
0x14000cba8  lea     rax, [rsp+38h+TokenInformationLength]
0x14000cbad  mov     r8, rbx; TokenInformation
0x14000cbb0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14000cbb5  call    cs:__imp_GetTokenInformation
0x14000cbbb  test    eax, eax
0x14000cbbd  jnz     short loc_14000CBD6
0x14000cbbf  mov     rcx, [rsp+38h]; this
0x14000cbc4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000cbcb  mov     edx, 115h; void *
0x14000cbd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000cbd6  mov     rcx, [rbx]; pSid
0x14000cbd9  call    cs:__imp_IsValidSid
0x14000cbdf  test    eax, eax
0x14000cbe1  jnz     short loc_14000CBFA
0x14000cbe3  mov     rcx, [rsp+38h]; this
0x14000cbe8  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000cbef  mov     edx, 117h; void *
0x14000cbf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000cbfa  mov     rcx, [rbx]; pSid
0x14000cbfd  call    cs:__imp_GetSidSubAuthorityCount
0x14000cc03  mov     rcx, [rbx]; pSid
0x14000cc06  movzx   edx, byte ptr [rax]
0x14000cc09  dec     edx; nSubAuthority
0x14000cc0b  call    cs:__imp_GetSidSubAuthority
0x14000cc11  mov     edi, [rax]
0x14000cc13  test    rbx, rbx
0x14000cc16  jz      short loc_14000CC20
0x14000cc18  mov     rcx, rbx; this
0x14000cc1b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000cc20  lea     rcx, [rsp+38h+TokenHandle]
0x14000cc25  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000cc2a  mov     rbx, [rsp+38h+arg_10]
0x14000cc2f  mov     eax, edi
0x14000cc31  add     rsp, 30h
0x14000cc35  pop     rdi
0x14000cc36  retn
```
