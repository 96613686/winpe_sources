# IsTIFileDescriptor

- ea: `0x1800edc4c`
- end: `0x1800edd71`
- name: `IsTIFileDescriptor`
- size: `293`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800eda38`

## callees

- `0x180020880`
- `0x1800220f0`
- `0x1800edc4c`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800edcac`
- `ntdll!RtlInitializeSid` at `0x1800edcac`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcb7`
- `ntdll!RtlSubAuthoritySid` at `0x1800edccd`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcdf`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcf1`
- `ntdll!RtlSubAuthoritySid` at `0x1800edd03`
- `ntdll!RtlSubAuthoritySid` at `0x1800edd15`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcb7`
- `ntdll!RtlSubAuthoritySid` at `0x1800edccd`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcdf`
- `ntdll!RtlSubAuthoritySid` at `0x1800edcf1`
- `ntdll!RtlSubAuthoritySid` at `0x1800edd03`
- `ntdll!RtlSubAuthoritySid` at `0x1800edd15`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800edd2c`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800edd2c`
- `ntdll!RtlLengthRequiredSid` at `0x1800edc7a`
- `ntdll!RtlLengthRequiredSid` at `0x1800edc7a`
- `ntdll!RtlEqualSid` at `0x1800edd42`
- `ntdll!RtlEqualSid` at `0x1800edd42`

## pseudocode

```c
HLOCAL __fastcall IsTIFileDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  ULONG v2; // eax
  HLOCAL result; // rax
  HLOCAL v4; // rbx
  unsigned int v5; // edi
  unsigned __int8 OwnerDefaulted[8]; // [rsp+20h] [rbp-28h] BYREF
  PSID Owner; // [rsp+28h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  Owner = 0;
  OwnerDefaulted[0] = 0;
  v2 = RtlLengthRequiredSid(6u);
  result = LocalAlloc(0, v2);
  v4 = result;
  if ( result )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(result, &IdentifierAuthority, 6u);
    v5 = 1;
    *RtlSubAuthoritySid(v4, 0) = 80;
    *RtlSubAuthoritySid(v4, 1u) = 956008885;
    *RtlSubAuthoritySid(v4, 2u) = -876444647;
    *RtlSubAuthoritySid(v4, 3u) = 1831038044;
    *RtlSubAuthoritySid(v4, 4u) = 1853292631;
    *RtlSubAuthoritySid(v4, 5u) = -2023488832;
    if ( RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, OwnerDefaulted) < 0
      || !Owner
      || !RtlEqualSid(v4, Owner) )
    {
      v5 = 0;
    }
    LocalFree(v4);
    return (HLOCAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800edc4c  push    rbp
0x1800edc4e  push    rbx
0x1800edc4f  push    rsi
0x1800edc50  push    rdi
0x1800edc51  mov     rbp, rsp
0x1800edc54  sub     rsp, 48h
0x1800edc58  mov     rax, cs:__security_cookie
0x1800edc5f  xor     rax, rsp
0x1800edc62  mov     [rbp+var_10], rax
0x1800edc66  mov     rsi, rcx
0x1800edc69  mov     [rbp+Owner], 0
0x1800edc71  mov     ecx, 6; SubAuthorityCount
0x1800edc76  mov     [rbp+OwnerDefaulted], 0
0x1800edc7a  call    cs:__imp_RtlLengthRequiredSid
0x1800edc80  mov     edx, eax; uBytes
0x1800edc82  xor     ecx, ecx; uFlags
0x1800edc84  call    LocalAlloc
0x1800edc89  mov     rbx, rax
0x1800edc8c  test    rax, rax
0x1800edc8f  jz      loc_1800EDD6B
0x1800edc95  mov     r8b, 6; SubAuthorityCount
0x1800edc98  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1800edc9f  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1800edca3  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1800edca9  mov     rcx, rax; Sid
0x1800edcac  call    cs:__imp_RtlInitializeSid
0x1800edcb2  xor     edx, edx; SubAuthority
0x1800edcb4  mov     rcx, rbx; Sid
0x1800edcb7  call    cs:__imp_RtlSubAuthoritySid
0x1800edcbd  mov     edi, 1
0x1800edcc2  mov     rcx, rbx; Sid
0x1800edcc5  mov     edx, edi; SubAuthority
0x1800edcc7  mov     dword ptr [rax], 50h ; 'P'
0x1800edccd  call    cs:__imp_RtlSubAuthoritySid
0x1800edcd3  lea     edx, [rdi+1]; SubAuthority
0x1800edcd6  mov     rcx, rbx; Sid
0x1800edcd9  mov     dword ptr [rax], 38FB89B5h
0x1800edcdf  call    cs:__imp_RtlSubAuthoritySid
0x1800edce5  lea     edx, [rdi+2]; SubAuthority
0x1800edce8  mov     rcx, rbx; Sid
0x1800edceb  mov     dword ptr [rax], 0CBC28419h
0x1800edcf1  call    cs:__imp_RtlSubAuthoritySid
0x1800edcf7  lea     edx, [rdi+3]; SubAuthority
0x1800edcfa  mov     rcx, rbx; Sid
0x1800edcfd  mov     dword ptr [rax], 6D236C5Ch
0x1800edd03  call    cs:__imp_RtlSubAuthoritySid
0x1800edd09  lea     edx, [rdi+4]; SubAuthority
0x1800edd0c  mov     rcx, rbx; Sid
0x1800edd0f  mov     dword ptr [rax], 6E770057h
0x1800edd15  call    cs:__imp_RtlSubAuthoritySid
0x1800edd1b  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1800edd1f  mov     rcx, rsi; SecurityDescriptor
0x1800edd22  lea     rdx, [rbp+Owner]; Owner
0x1800edd26  mov     dword ptr [rax], 876402C0h
0x1800edd2c  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800edd32  test    eax, eax
0x1800edd34  js      short loc_1800EDD6D
0x1800edd36  mov     rdx, [rbp+Owner]; Sid2
0x1800edd3a  test    rdx, rdx
0x1800edd3d  jz      short loc_1800EDD6D
0x1800edd3f  mov     rcx, rbx; Sid1
0x1800edd42  call    cs:__imp_RtlEqualSid
0x1800edd48  test    al, al
0x1800edd4a  jz      short loc_1800EDD6D
0x1800edd4c  mov     rcx, rbx; hMem
0x1800edd4f  call    LocalFree
0x1800edd54  mov     eax, edi
0x1800edd56  mov     rcx, [rbp+var_10]
0x1800edd5a  xor     rcx, rsp; StackCookie
0x1800edd5d  call    __security_check_cookie
0x1800edd62  add     rsp, 48h
0x1800edd66  pop     rdi
0x1800edd67  pop     rsi
0x1800edd68  pop     rbx
0x1800edd69  pop     rbp
0x1800edd6a  retn
0x1800edd6b  jmp     short loc_1800EDD56
0x1800edd6d  xor     edi, edi
0x1800edd6f  jmp     short loc_1800EDD4C
```
