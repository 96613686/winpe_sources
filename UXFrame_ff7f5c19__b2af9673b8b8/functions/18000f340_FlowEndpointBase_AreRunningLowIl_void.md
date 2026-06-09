# FlowEndpointBase::AreRunningLowIl(void)

- ea: `0x18000f340`
- end: `0x18000f44b`
- name: `?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ`
- size: `267`
- prototype: `bool __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000fde4`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x18000dccc`
- `0x18000e1a4`
- `0x18000f340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f390`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f382`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f3c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f382`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f3c8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000f3fa`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000f3fa`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f3d5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f3d5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000f3e2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000f3e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall FlowEndpointBase::AreRunningLowIl(FlowEndpointBase *this)
{
  PSID *v1; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  char v3; // di
  PDWORD SidSubAuthority; // rax
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-20h] BYREF
  PSID *v8; // [rsp+40h] [rbp-18h] BYREF

  v6 = -4;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    goto LABEL_10;
  }
  v1 = (PSID *)operator new(TokenInformationLength);
  v8 = v1;
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFCLL,
          TokenIntegrityLevel,
          v1,
          TokenInformationLength,
          &TokenInformationLength)
    || !IsValidSid(*v1)
    || (SidSubAuthorityCount = GetSidSubAuthorityCount(*v1)) == 0
    || (v3 = 1, (SidSubAuthority = GetSidSubAuthority(*v1, (unsigned int)*SidSubAuthorityCount - 1)) == 0)
    || *SidSubAuthority != 4096 )
  {
    Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v8);
LABEL_10:
    v3 = 0;
    goto LABEL_11;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v8);
LABEL_11:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v6);
  return v3;
}

```

## disassembly

```asm
0x18000f340  mov     r11, rsp
0x18000f343  mov     [r11+8], rbx
0x18000f347  push    rdi
0x18000f348  sub     rsp, 50h
0x18000f34c  mov     rax, cs:__security_cookie
0x18000f353  xor     rax, rsp
0x18000f356  mov     [rsp+58h+var_10], rax
0x18000f35b  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x18000f362  mov     [r11-28h], rdi
0x18000f366  mov     [rsp+58h+TokenInformationLength], 0
0x18000f36e  lea     rax, [r11-20h]
0x18000f372  mov     [r11-38h], rax
0x18000f376  xor     r9d, r9d; TokenInformationLength
0x18000f379  xor     r8d, r8d; TokenInformation
0x18000f37c  lea     edx, [rdi+1Dh]; TokenInformationClass
0x18000f37f  mov     rcx, rdi; TokenHandle
0x18000f382  call    cs:__imp_GetTokenInformation
0x18000f388  test    eax, eax
0x18000f38a  jnz     loc_18000F423
0x18000f390  call    cs:__imp_GetLastError
0x18000f396  cmp     eax, 7Ah ; 'z'
0x18000f399  jnz     loc_18000F423
0x18000f39f  mov     ecx, [rsp+58h+TokenInformationLength]; Size
0x18000f3a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f3a8  mov     rbx, rax
0x18000f3ab  mov     [rsp+58h+var_18], rax
0x18000f3b0  lea     rax, [rsp+58h+TokenInformationLength]
0x18000f3b5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000f3ba  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000f3bf  mov     r8, rbx; TokenInformation
0x18000f3c2  lea     edx, [rdi+1Dh]; TokenInformationClass
0x18000f3c5  mov     rcx, rdi; TokenHandle
0x18000f3c8  call    cs:__imp_GetTokenInformation
0x18000f3ce  test    eax, eax
0x18000f3d0  jz      short loc_18000F419
0x18000f3d2  mov     rcx, [rbx]; pSid
0x18000f3d5  call    cs:__imp_IsValidSid
0x18000f3db  test    eax, eax
0x18000f3dd  jz      short loc_18000F419
0x18000f3df  mov     rcx, [rbx]; pSid
0x18000f3e2  call    cs:__imp_GetSidSubAuthorityCount
0x18000f3e8  test    rax, rax
0x18000f3eb  jz      short loc_18000F419
0x18000f3ed  movzx   edx, byte ptr [rax]
0x18000f3f0  mov     edi, 1
0x18000f3f5  sub     edx, edi; nSubAuthority
0x18000f3f7  mov     rcx, [rbx]; pSid
0x18000f3fa  call    cs:__imp_GetSidSubAuthority
0x18000f400  test    rax, rax
0x18000f403  jz      short loc_18000F419
0x18000f405  cmp     dword ptr [rax], 1000h
0x18000f40b  jnz     short loc_18000F419
0x18000f40d  lea     rcx, [rsp+58h+var_18]
0x18000f412  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x18000f417  jmp     short loc_18000F426
0x18000f419  lea     rcx, [rsp+58h+var_18]
0x18000f41e  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x18000f423  xor     dil, dil
0x18000f426  lea     rcx, [rsp+58h+var_28]
0x18000f42b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f430  mov     al, dil
0x18000f433  mov     rcx, [rsp+58h+var_10]
0x18000f438  xor     rcx, rsp; StackCookie
0x18000f43b  call    __security_check_cookie
0x18000f440  mov     rbx, [rsp+58h+arg_0]
0x18000f445  add     rsp, 50h
0x18000f449  pop     rdi
0x18000f44a  retn
```
