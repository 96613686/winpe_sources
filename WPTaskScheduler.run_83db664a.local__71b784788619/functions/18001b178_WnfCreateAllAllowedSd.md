# WnfCreateAllAllowedSd

- ea: `0x18001b178`
- end: `0x18001b32b`
- name: `WnfCreateAllAllowedSd`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001af50`

## callees

- `0x18001b178`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001b2d6`
- `msvcrt!free` at `0x18001b2d6`
- `msvcrt!malloc` at `0x18001b2a5`
- `msvcrt!malloc` at `0x18001b2a5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001b210`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001b210`
- `ntdll!RtlCreateAcl` at `0x18001b230`
- `ntdll!RtlCreateAcl` at `0x18001b230`
- `ntdll!RtlFreeHeap` at `0x18001b2fc`
- `ntdll!RtlFreeHeap` at `0x18001b2fc`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001b251`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001b251`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001b1f7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001b1f7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001b26f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001b26f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001b288`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001b288`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001b299`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001b299`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001b2c7`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001b2c7`

## pseudocode

```c
__int64 __fastcall WnfCreateAllAllowedSd(_QWORD *a1)
{
  NTSTATUS v2; // ebx
  void *v3; // rax
  void *v4; // rdi
  ULONG BufferLength; // [rsp+60h] [rbp-A0h] BYREF
  PSID Owner; // [rsp+68h] [rbp-98h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-90h] BYREF
  _BYTE SecurityDescriptor[40]; // [rsp+78h] [rbp-88h] BYREF
  _ACL Acl; // [rsp+A0h] [rbp-60h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Owner = 0;
  BufferLength = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Owner);
  if ( v2 >= 0 )
  {
    v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v2 >= 0 )
    {
      v2 = RtlCreateAcl(&Acl, 0x400u, 2u);
      if ( v2 >= 0 )
      {
        v2 = RtlAddAccessAllowedAce(&Acl, 2u, 0x10000000u, Owner);
        if ( v2 >= 0 )
        {
          v2 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
          if ( v2 >= 0 )
          {
            v2 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
            if ( v2 >= 0 )
            {
              BufferLength = RtlLengthSecurityDescriptor(SecurityDescriptor);
              v3 = malloc(BufferLength);
              v4 = v3;
              if ( v3 )
              {
                v2 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v3, &BufferLength);
                if ( v2 >= 0 )
                  *a1 = v4;
                else
                  free(v4);
              }
              else
              {
                v2 = -1073741801;
              }
            }
          }
        }
      }
    }
  }
  if ( Owner )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Owner);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001b178  mov     [rsp-8+arg_8], rbx
0x18001b17d  mov     [rsp-8+arg_10], rsi
0x18001b182  push    rbp
0x18001b183  push    rdi
0x18001b184  push    r14
0x18001b186  lea     rbp, [rsp-3B0h]
0x18001b18e  sub     rsp, 4B0h
0x18001b195  mov     rax, cs:__security_cookie
0x18001b19c  xor     rax, rsp
0x18001b19f  mov     [rbp+3C0h+var_20], rax
0x18001b1a6  xor     r14d, r14d
0x18001b1a9  mov     word ptr [rsp+4C0h+IdentifierAuthority.Value+4], 100h
0x18001b1b0  lea     rax, [rsp+4C0h+Owner]
0x18001b1b5  mov     dword ptr [rsp+4C0h+IdentifierAuthority.Value], r14d
0x18001b1ba  mov     [rsp+4C0h+Sid], rax; Sid
0x18001b1bf  mov     rsi, rcx
0x18001b1c2  mov     [rsp+4C0h+SubAuthority7], r14d; SubAuthority7
0x18001b1c7  lea     rcx, [rsp+4C0h+IdentifierAuthority]; IdentifierAuthority
0x18001b1cc  mov     [rsp+4C0h+SubAuthority6], r14d; SubAuthority6
0x18001b1d1  xor     r9d, r9d; SubAuthority1
0x18001b1d4  mov     [rsp+4C0h+SubAuthority5], r14d; SubAuthority5
0x18001b1d9  xor     r8d, r8d; SubAuthority0
0x18001b1dc  mov     [rsp+4C0h+SubAuthority4], r14d; SubAuthority4
0x18001b1e1  mov     dl, 1; SubAuthorityCount
0x18001b1e3  mov     [rsp+4C0h+SubAuthority3], r14d; SubAuthority3
0x18001b1e8  mov     [rsp+4C0h+SubAuthority2], r14d; SubAuthority2
0x18001b1ed  mov     [rsp+4C0h+Owner], r14
0x18001b1f2  mov     [rsp+4C0h+BufferLength], r14d
0x18001b1f7  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001b1fd  mov     ebx, eax
0x18001b1ff  test    eax, eax
0x18001b201  js      loc_18001B2E1
0x18001b207  lea     edx, [r14+1]; Revision
0x18001b20b  lea     rcx, [rsp+4C0h+SecurityDescriptor]; SecurityDescriptor
0x18001b210  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001b216  mov     ebx, eax
0x18001b218  test    eax, eax
0x18001b21a  js      loc_18001B2E1
0x18001b220  lea     edi, [r14+2]
0x18001b224  mov     edx, 400h; AclSize
0x18001b229  mov     r8d, edi; AclRevision
0x18001b22c  lea     rcx, [rbp+3C0h+Acl]; Acl
0x18001b230  call    cs:__imp_RtlCreateAcl
0x18001b236  mov     ebx, eax
0x18001b238  test    eax, eax
0x18001b23a  js      loc_18001B2E1
0x18001b240  mov     r9, [rsp+4C0h+Owner]; Sid
0x18001b245  lea     rcx, [rbp+3C0h+Acl]; Acl
0x18001b249  mov     r8d, 10000000h; AccessMask
0x18001b24f  mov     edx, edi; Revision
0x18001b251  call    cs:__imp_RtlAddAccessAllowedAce
0x18001b257  mov     ebx, eax
0x18001b259  test    eax, eax
0x18001b25b  js      loc_18001B2E1
0x18001b261  xor     r9d, r9d; DaclDefaulted
0x18001b264  lea     r8, [rbp+3C0h+Acl]; Dacl
0x18001b268  mov     dl, 1; DaclPresent
0x18001b26a  lea     rcx, [rsp+4C0h+SecurityDescriptor]; SecurityDescriptor
0x18001b26f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001b275  mov     ebx, eax
0x18001b277  test    eax, eax
0x18001b279  js      short loc_18001B2E1
0x18001b27b  mov     rdx, [rsp+4C0h+Owner]; Owner
0x18001b280  lea     rcx, [rsp+4C0h+SecurityDescriptor]; SecurityDescriptor
0x18001b285  xor     r8d, r8d; OwnerDefaulted
0x18001b288  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18001b28e  mov     ebx, eax
0x18001b290  test    eax, eax
0x18001b292  js      short loc_18001B2E1
0x18001b294  lea     rcx, [rsp+4C0h+SecurityDescriptor]; SecurityDescriptor
0x18001b299  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001b29f  mov     ecx, eax; Size
0x18001b2a1  mov     [rsp+4C0h+BufferLength], ecx
0x18001b2a5  call    cs:__imp_malloc
0x18001b2ab  mov     rdi, rax
0x18001b2ae  test    rax, rax
0x18001b2b1  jnz     short loc_18001B2BA
0x18001b2b3  mov     ebx, 0C0000017h
0x18001b2b8  jmp     short loc_18001B2E1
0x18001b2ba  lea     r8, [rsp+4C0h+BufferLength]; BufferLength
0x18001b2bf  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x18001b2c2  lea     rcx, [rsp+4C0h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001b2c7  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18001b2cd  mov     ebx, eax
0x18001b2cf  test    eax, eax
0x18001b2d1  jns     short loc_18001B2DE
0x18001b2d3  mov     rcx, rdi; Block
0x18001b2d6  call    cs:__imp_free
0x18001b2dc  jmp     short loc_18001B2E1
0x18001b2de  mov     [rsi], rdi
0x18001b2e1  cmp     [rsp+4C0h+Owner], r14
0x18001b2e6  jz      short loc_18001B302
0x18001b2e8  mov     rcx, gs:60h
0x18001b2f1  xor     edx, edx; Flags
0x18001b2f3  mov     r8, [rsp+4C0h+Owner]; P
0x18001b2f8  mov     rcx, [rcx+30h]; HeapHandle
0x18001b2fc  call    cs:__imp_RtlFreeHeap
0x18001b302  mov     eax, ebx
0x18001b304  mov     rcx, [rbp+3C0h+var_20]
0x18001b30b  xor     rcx, rsp; StackCookie
0x18001b30e  call    __security_check_cookie
0x18001b313  lea     r11, [rsp+4C0h+var_10]
0x18001b31b  mov     rbx, [r11+28h]
0x18001b31f  mov     rsi, [r11+30h]
0x18001b323  mov     rsp, r11
0x18001b326  pop     r14
0x18001b328  pop     rdi
0x18001b329  pop     rbp
0x18001b32a  retn
```
