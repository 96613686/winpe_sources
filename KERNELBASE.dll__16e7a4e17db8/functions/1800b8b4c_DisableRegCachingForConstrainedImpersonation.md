# DisableRegCachingForConstrainedImpersonation

- ea: `0x1800b8b4c`
- end: `0x1800b8bb4`
- name: `DisableRegCachingForConstrainedImpersonation`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b88a4`

## callees

- `0x1800b8b4c`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1801932a5`
- `ntdll!RtlInitializeSid` at `0x1801932a5`
- `ntdll!RtlSubAuthoritySid` at `0x1801932b2`
- `ntdll!RtlSubAuthoritySid` at `0x1801932c8`
- `ntdll!RtlSubAuthoritySid` at `0x1801932b2`
- `ntdll!RtlSubAuthoritySid` at `0x1801932c8`
- `ntdll!RtlInitUnicodeString` at `0x180193230`
- `ntdll!RtlInitUnicodeString` at `0x180193230`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b8b89`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b8b89`
- `ntdll!NtQueryInformationToken` at `0x180193216`
- `ntdll!NtQueryInformationToken` at `0x180193216`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019327c`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1801932e4`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18019327c`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1801932e4`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180193262`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180193262`
- `ntdll!RtlCapabilityCheck` at `0x180193249`
- `ntdll!RtlCapabilityCheck` at `0x180193249`

## string_xrefs

- `0x180193224`: `constrainedImpersonation`

## pseudocode

```c
NTSTATUS DisableRegCachingForConstrainedImpersonation()
{
  NTSTATUS result; // eax
  _BYTE v1[4]; // [rsp+30h] [rbp-D0h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-CCh] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Sid[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v7[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v8[80]; // [rsp+C0h] [rbp-40h] BYREF

  v1[0] = 0;
  DestinationString = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  result = RtlIsMultiSessionSku();
  if ( !(_BYTE)result )
  {
    v1[0] = 0;
    result = NtQueryInformationToken(
               (HANDLE)0xFFFFFFFFFFFFFFFCLL,
               TokenIsAppContainer,
               &TokenInformation,
               4u,
               &ReturnLength);
    if ( result >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"constrainedImpersonation");
      if ( TokenInformation )
      {
        RtlCapabilityCheck(0, &DestinationString, v1);
      }
      else
      {
        if ( (int)RtlDeriveCapabilitySidsFromName(&DestinationString, v7, v8) >= 0 )
          RtlCheckTokenMembershipEx(-4, v7, 0, v1);
        if ( !v1[0] )
        {
          *(_DWORD *)IdentifierAuthority.Value = 0;
          *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
          RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
          *RtlSubAuthoritySid(Sid, 0) = 32;
          *RtlSubAuthoritySid(Sid, 1u) = 581;
          RtlCheckTokenMembershipEx(-4, Sid, 0, v1);
        }
      }
      result = v1[0];
      g_DisableCachingWhileImpersonated = v1[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b8b4c  mov     [rsp-8+arg_0], rdi
0x1800b8b51  push    rbp
0x1800b8b52  lea     rbp, [rsp-20h]
0x1800b8b57  sub     rsp, 120h
0x1800b8b5e  mov     rax, cs:__security_cookie
0x1800b8b65  xor     rax, rsp
0x1800b8b68  mov     [rbp+20h+var_10], rax
0x1800b8b6c  xorps   xmm0, xmm0
0x1800b8b6f  mov     [rsp+120h+var_F0], 0
0x1800b8b74  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1800b8b79  mov     [rsp+120h+TokenInformation], 0
0x1800b8b81  mov     [rsp+120h+var_E8], 0
0x1800b8b89  call    cs:__imp_RtlIsMultiSessionSku
0x1800b8b8f  test    al, al
0x1800b8b91  jz      loc_1801931EE
0x1800b8b97  mov     rcx, [rbp+20h+var_10]
0x1800b8b9b  xor     rcx, rsp; StackCookie
0x1800b8b9e  call    __security_check_cookie
0x1800b8ba3  mov     rdi, [rsp+120h+arg_0]
0x1800b8bab  add     rsp, 120h
0x1800b8bb2  pop     rbp
0x1800b8bb3  retn
0x1801931ee  mov     r9d, 4; TokenInformationLength
0x1801931f4  mov     [rsp+120h+var_F0], 0
0x1801931f9  lea     rax, [rsp+120h+var_E8]
0x1801931fe  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x180193205  lea     r8, [rsp+120h+TokenInformation]; TokenInformation
0x18019320a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18019320f  mov     rcx, rdi; TokenHandle
0x180193212  lea     edx, [r9+19h]; TokenInformationClass
0x180193216  call    cs:__imp_NtQueryInformationToken
0x18019321c  test    eax, eax
0x18019321e  js      loc_1800B8B97
0x180193224  lea     rdx, aConstrainedimp; "constrainedImpersonation"
0x18019322b  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180193230  call    cs:__imp_RtlInitUnicodeString
0x180193236  cmp     [rsp+120h+TokenInformation], 0
0x18019323b  jz      short loc_180193254
0x18019323d  lea     r8, [rsp+120h+var_F0]
0x180193242  xor     ecx, ecx
0x180193244  lea     rdx, [rsp+120h+DestinationString]
0x180193249  call    cs:__imp_RtlCapabilityCheck
0x18019324f  jmp     loc_1801932EA
0x180193254  lea     r8, [rbp+20h+var_60]
0x180193258  lea     rdx, [rsp+120h+var_B0]
0x18019325d  lea     rcx, [rsp+120h+DestinationString]
0x180193262  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180193268  test    eax, eax
0x18019326a  js      short loc_180193282
0x18019326c  lea     r9, [rsp+120h+var_F0]
0x180193271  xor     r8d, r8d
0x180193274  lea     rdx, [rsp+120h+var_B0]
0x180193279  mov     rcx, rdi
0x18019327c  call    cs:__imp_RtlCheckTokenMembershipEx
0x180193282  cmp     [rsp+120h+var_F0], 0
0x180193287  jnz     short loc_1801932EA
0x180193289  mov     r8b, 2; SubAuthorityCount
0x18019328c  mov     dword ptr [rsp+120h+IdentifierAuthority.Value], 0
0x180193294  lea     rdx, [rsp+120h+IdentifierAuthority]; IdentifierAuthority
0x180193299  mov     word ptr [rsp+120h+IdentifierAuthority.Value+4], 500h
0x1801932a0  lea     rcx, [rsp+120h+Sid]; Sid
0x1801932a5  call    cs:__imp_RtlInitializeSid
0x1801932ab  xor     edx, edx; SubAuthority
0x1801932ad  lea     rcx, [rsp+120h+Sid]; Sid
0x1801932b2  call    cs:__imp_RtlSubAuthoritySid
0x1801932b8  mov     edx, 1; SubAuthority
0x1801932bd  lea     rcx, [rsp+120h+Sid]; Sid
0x1801932c2  mov     dword ptr [rax], 20h ; ' '
0x1801932c8  call    cs:__imp_RtlSubAuthoritySid
0x1801932ce  lea     r9, [rsp+120h+var_F0]
0x1801932d3  xor     r8d, r8d
0x1801932d6  lea     rdx, [rsp+120h+Sid]
0x1801932db  mov     rcx, rdi
0x1801932de  mov     dword ptr [rax], 245h
0x1801932e4  call    cs:__imp_RtlCheckTokenMembershipEx
0x1801932ea  movzx   eax, [rsp+120h+var_F0]
0x1801932ef  mov     cs:g_DisableCachingWhileImpersonated, eax
0x1801932f5  jmp     loc_1800B8B97
```
