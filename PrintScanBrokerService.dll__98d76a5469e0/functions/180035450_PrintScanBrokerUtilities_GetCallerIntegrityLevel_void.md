# PrintScanBrokerUtilities::GetCallerIntegrityLevel(void)

- ea: `0x180035450`
- end: `0x1800355ea`
- name: `?GetCallerIntegrityLevel@PrintScanBrokerUtilities@@YAKXZ`
- size: `410`
- prototype: `unsigned int __fastcall(PrintScanBrokerUtilities *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022b44`
- `0x180022ef0`
- `0x18002b4d0`

## callees

- `0x18001255c`
- `0x18001cfb4`
- `0x180027cb4`
- `0x18002f194`
- `0x18002f1b0`
- `0x18002f1d4`
- `0x180035450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035562`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003553a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003553a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035483`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003546d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003546d`
- `KERNELBASE!LocalAlloc` at `0x1800354df`
- `KERNELBASE!LocalAlloc` at `0x1800354df`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180035524`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180035524`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035532`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180035532`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800354b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003550f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800354b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003550f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003554b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003554b`

## string_xrefs

- `0x180035575`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x180035587`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x18003559f`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x1800355b1`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x1800355c6`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x1800355d8`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintScanBrokerUtilities::GetCallerIntegrityLevel(PrintScanBrokerUtilities *this)
{
  HANDLE CurrentThread; // rax
  const char *v2; // r9
  const char *v3; // r9
  PSID *v4; // rbx
  const char *v5; // r9
  const char *v6; // r9
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v8; // edi
  DWORD LastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-10h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v14; // [rsp+50h] [rbp+20h] BYREF
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  PSID *v17; // [rsp+68h] [rbp+38h]

  wil::CoImpersonateClient(&v14);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v2);
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      (const char *)0x80004005LL,
      ReturnLength);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v3);
  v4 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v17 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v5);
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v6);
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
  v8 = *GetSidSubAuthority(*v4, (unsigned int)*SidSubAuthorityCount - 1);
  LastError = GetLastError();
  if ( LastError )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      (const char *)LastError,
      ReturnLengtha);
  LocalFree(v4);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v14 )
    CoRevertToSelf();
  return v8;
}

```

## disassembly

```asm
0x180035450  push    rbp
0x180035452  push    rbx
0x180035453  push    rdi
0x180035454  mov     rbp, rsp
0x180035457  sub     rsp, 30h
0x18003545b  lea     rcx, [rbp+arg_0]
0x18003545f  call    ?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ; wil::CoImpersonateClient(void)
0x180035464  nop
0x180035465  mov     [rbp+TokenHandle], 0
0x18003546d  call    cs:__imp_GetCurrentThread
0x180035473  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180035477  mov     edx, 8; DesiredAccess
0x18003547c  lea     r8d, [rdx-7]; OpenAsSelf
0x180035480  mov     rcx, rax; ThreadHandle
0x180035483  call    cs:__imp_OpenThreadToken
0x180035489  mov     rcx, [rbp+18h]; this
0x18003548d  test    eax, eax
0x18003548f  jz      loc_180035587
0x180035495  mov     [rbp+TokenInformationLength], 0
0x18003549c  mov     rbx, [rbp+18h]
0x1800354a0  lea     rax, [rbp+TokenInformationLength]
0x1800354a4  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x1800354a9  xor     r9d, r9d; TokenInformationLength
0x1800354ac  xor     r8d, r8d; TokenInformation
0x1800354af  lea     edi, [r9+19h]
0x1800354b3  mov     edx, edi; TokenInformationClass
0x1800354b5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800354b9  call    cs:__imp_GetTokenInformation
0x1800354bf  test    eax, eax
0x1800354c1  jnz     loc_180035599
0x1800354c7  mov     rbx, [rbp+18h]
0x1800354cb  call    cs:__imp_GetLastError
0x1800354d1  cmp     eax, 7Ah ; 'z'
0x1800354d4  jnz     loc_1800355B1
0x1800354da  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800354dd  xor     ecx, ecx; uFlags
0x1800354df  call    cs:__imp_LocalAlloc
0x1800354e5  mov     rbx, rax
0x1800354e8  mov     [rbp+arg_18], rax
0x1800354ec  mov     rcx, [rbp+18h]; this
0x1800354f0  test    rax, rax
0x1800354f3  jz      loc_1800355C6
0x1800354f9  lea     rax, [rbp+TokenInformationLength]
0x1800354fd  mov     qword ptr [rsp+30h+ReturnLength], rax; unsigned int
0x180035502  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180035506  mov     r8, rbx; TokenInformation
0x180035509  mov     edx, edi; TokenInformationClass
0x18003550b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003550f  call    cs:__imp_GetTokenInformation
0x180035515  mov     rcx, [rbp+18h]; this
0x180035519  test    eax, eax
0x18003551b  jz      loc_1800355D8
0x180035521  mov     rcx, [rbx]; pSid
0x180035524  call    cs:__imp_GetSidSubAuthorityCount
0x18003552a  movzx   edx, byte ptr [rax]
0x18003552d  dec     edx; nSubAuthority
0x18003552f  mov     rcx, [rbx]; pSid
0x180035532  call    cs:__imp_GetSidSubAuthority
0x180035538  mov     edi, [rax]
0x18003553a  call    cs:__imp_GetLastError
0x180035540  mov     rcx, [rbp+18h]; this
0x180035544  test    eax, eax
0x180035546  jnz     short loc_180035572
0x180035548  mov     rcx, rbx; hMem
0x18003554b  call    cs:__imp_LocalFree
0x180035551  nop
0x180035552  lea     rcx, [rbp+TokenHandle]
0x180035556  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003555b  nop
0x18003555c  cmp     [rbp+arg_0], 0
0x180035560  jz      short loc_180035568
0x180035562  call    cs:__imp_CoRevertToSelf
0x180035568  mov     eax, edi
0x18003556a  add     rsp, 30h
0x18003556e  pop     rdi
0x18003556f  pop     rbx
0x180035570  pop     rbp
0x180035571  retn
0x180035572  mov     r9d, eax; char *
0x180035575  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x18003557c  mov     edx, 25h ; '%'; void *
0x180035581  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180035587  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x18003558e  mov     edx, 15h; void *
0x180035593  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180035599  mov     r9d, 80004005h; char *
0x18003559f  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x1800355a6  mov     edx, edi; void *
0x1800355a8  mov     rcx, rbx; this
0x1800355ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800355b1  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x1800355b8  mov     edx, 1Ah; void *
0x1800355bd  mov     rcx, rbx; this
0x1800355c0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800355c6  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x1800355cd  mov     edx, 1Dh; void *
0x1800355d2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800355d8  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x1800355df  mov     edx, 1Eh; void *
0x1800355e4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
