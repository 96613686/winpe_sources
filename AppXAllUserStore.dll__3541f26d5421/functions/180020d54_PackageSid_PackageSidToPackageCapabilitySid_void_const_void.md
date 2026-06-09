# PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)

- ea: `0x180020d54`
- end: `0x180020e8f`
- name: `?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(PSID pSid, PSID *Sid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020c90`

## callees

- `0x180020d54`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180020e55`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180020e55`
- `ntdll!RtlValidSid` at `0x180020d8a`
- `ntdll!RtlValidSid` at `0x180020d8a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020dbe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020dcf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020de0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020df0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e00`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e10`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e20`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020dbe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020dcf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020de0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020df0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e00`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e10`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020e20`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020da1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020da1`

## pseudocode

```c
__int64 __fastcall PackageSid::PackageSidToPackageCapabilitySid(PSID pSid, PSID *Sid)
{
  __int64 result; // rax
  ULONG SubAuthority7; // r15d
  ULONG SubAuthority6; // r14d
  ULONG SubAuthority5; // ebp
  ULONG SubAuthority4; // esi
  ULONG SubAuthority3; // edi
  ULONG SubAuthority2; // ebx
  ULONG *SidSubAuthority; // rax
  NTSTATUS v12; // edx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-48h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( !RtlValidSid(pSid) )
    return 2147942487LL;
  if ( *GetSidSubAuthorityCount(pSid) != 8 )
    return 2147549183LL;
  SubAuthority7 = *GetSidSubAuthority(pSid, 7u);
  SubAuthority6 = *GetSidSubAuthority(pSid, 6u);
  SubAuthority5 = *GetSidSubAuthority(pSid, 5u);
  SubAuthority4 = *GetSidSubAuthority(pSid, 4u);
  SubAuthority3 = *GetSidSubAuthority(pSid, 3u);
  SubAuthority2 = *GetSidSubAuthority(pSid, 2u);
  SidSubAuthority = GetSidSubAuthority(pSid, 1u);
  v12 = RtlAllocateAndInitializeSid(
          &IdentifierAuthority,
          8u,
          3u,
          *SidSubAuthority,
          SubAuthority2,
          SubAuthority3,
          SubAuthority4,
          SubAuthority5,
          SubAuthority6,
          SubAuthority7,
          Sid);
  result = 0;
  if ( v12 < 0 )
    return v12 | 0x10000000u;
  return result;
}

```

## disassembly

```asm
0x180020d54  mov     [rsp+arg_10], rbx
0x180020d59  push    rbp
0x180020d5a  push    rsi
0x180020d5b  push    rdi
0x180020d5c  push    r12
0x180020d5e  push    r13
0x180020d60  push    r14
0x180020d62  push    r15
0x180020d64  sub     rsp, 70h
0x180020d68  mov     rax, cs:__security_cookie
0x180020d6f  xor     rax, rsp
0x180020d72  mov     [rsp+0A8h+var_40], rax
0x180020d77  xor     ebx, ebx
0x180020d79  mov     word ptr [rsp+0A8h+IdentifierAuthority.Value+4], 0F00h
0x180020d80  mov     dword ptr [rsp+0A8h+IdentifierAuthority.Value], ebx
0x180020d84  mov     r13, rdx
0x180020d87  mov     r12, rcx
0x180020d8a  call    cs:__imp_RtlValidSid
0x180020d90  test    al, al
0x180020d92  jnz     short loc_180020D9E
0x180020d94  mov     eax, 80070057h
0x180020d99  jmp     loc_180020E6A
0x180020d9e  mov     rcx, r12; pSid
0x180020da1  call    cs:__imp_GetSidSubAuthorityCount
0x180020da7  cmp     byte ptr [rax], 8
0x180020daa  jz      short loc_180020DB6
0x180020dac  mov     eax, 8000FFFFh
0x180020db1  jmp     loc_180020E6A
0x180020db6  mov     edx, 7; nSubAuthority
0x180020dbb  mov     rcx, r12; pSid
0x180020dbe  call    cs:__imp_GetSidSubAuthority
0x180020dc4  mov     edx, 6; nSubAuthority
0x180020dc9  mov     rcx, r12; pSid
0x180020dcc  mov     r15d, [rax]
0x180020dcf  call    cs:__imp_GetSidSubAuthority
0x180020dd5  mov     edx, 5; nSubAuthority
0x180020dda  mov     rcx, r12; pSid
0x180020ddd  mov     r14d, [rax]
0x180020de0  call    cs:__imp_GetSidSubAuthority
0x180020de6  mov     edx, 4; nSubAuthority
0x180020deb  mov     rcx, r12; pSid
0x180020dee  mov     ebp, [rax]
0x180020df0  call    cs:__imp_GetSidSubAuthority
0x180020df6  mov     edx, 3; nSubAuthority
0x180020dfb  mov     rcx, r12; pSid
0x180020dfe  mov     esi, [rax]
0x180020e00  call    cs:__imp_GetSidSubAuthority
0x180020e06  mov     edx, 2; nSubAuthority
0x180020e0b  mov     rcx, r12; pSid
0x180020e0e  mov     edi, [rax]
0x180020e10  call    cs:__imp_GetSidSubAuthority
0x180020e16  mov     edx, 1; nSubAuthority
0x180020e1b  mov     rcx, r12; pSid
0x180020e1e  mov     ebx, [rax]
0x180020e20  call    cs:__imp_GetSidSubAuthority
0x180020e26  mov     [rsp+0A8h+Sid], r13; Sid
0x180020e2b  lea     rcx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x180020e30  mov     [rsp+0A8h+SubAuthority7], r15d; SubAuthority7
0x180020e35  mov     r8d, 3; SubAuthority0
0x180020e3b  mov     [rsp+0A8h+SubAuthority6], r14d; SubAuthority6
0x180020e40  mov     dl, 8; SubAuthorityCount
0x180020e42  mov     r9d, [rax]; SubAuthority1
0x180020e45  mov     [rsp+0A8h+SubAuthority5], ebp; SubAuthority5
0x180020e49  mov     [rsp+0A8h+SubAuthority4], esi; SubAuthority4
0x180020e4d  mov     [rsp+0A8h+SubAuthority3], edi; SubAuthority3
0x180020e51  mov     [rsp+0A8h+SubAuthority2], ebx; SubAuthority2
0x180020e55  call    cs:__imp_RtlAllocateAndInitializeSid
0x180020e5b  mov     ecx, eax
0x180020e5d  mov     edx, eax
0x180020e5f  bts     ecx, 1Ch
0x180020e63  xor     eax, eax
0x180020e65  test    edx, edx
0x180020e67  cmovs   eax, ecx
0x180020e6a  mov     rcx, [rsp+0A8h+var_40]
0x180020e6f  xor     rcx, rsp; StackCookie
0x180020e72  call    __security_check_cookie
0x180020e77  mov     rbx, [rsp+0A8h+arg_10]
0x180020e7f  add     rsp, 70h
0x180020e83  pop     r15
0x180020e85  pop     r14
0x180020e87  pop     r13
0x180020e89  pop     r12
0x180020e8b  pop     rdi
0x180020e8c  pop     rsi
0x180020e8d  pop     rbp
0x180020e8e  retn
```
