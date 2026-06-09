# UlCreateSecurityDescriptor

- ea: `0x14012feac`
- end: `0x14012ffda`
- name: `UlCreateSecurityDescriptor`
- size: `302`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ffc90`
- `0x140148aa4`

## callees

- `0x14012feac`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14012fef1`
- `ntoskrnl!RtlLengthSid` at `0x14012fef1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14012ffa7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14012ffa7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14012ff86`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14012ff86`
- `ntoskrnl!RtlCreateAcl` at `0x14012ff4d`
- `ntoskrnl!RtlCreateAcl` at `0x14012ff4d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14012fec7`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14012fec7`
- `ntoskrnl!ExAllocatePool3` at `0x14012ff24`
- `ntoskrnl!ExAllocatePool3` at `0x14012ff24`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ffbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012ffbe`

## pseudocode

```c
__int64 __fastcall UlCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2, unsigned int a3)
{
  NTSTATUS Acl; // ebx
  unsigned int v7; // ebx
  ULONG i; // edi
  ULONG v9; // eax
  struct _ACL *Pool3; // rax
  struct _ACL *v11; // rsi
  unsigned int j; // edi

  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl >= 0 )
  {
    v7 = 0;
    for ( i = 8; v7 < a3; i += v9 + 12 )
      v9 = RtlLengthSid(*(PSID *)(a2 + 16LL * v7++));
    Pool3 = (struct _ACL *)ExAllocatePool3(258, i, 1146317909, UxLowPriorityPool, 1);
    v11 = Pool3;
    if ( Pool3 )
    {
      Acl = RtlCreateAcl(Pool3, i, 2u);
      if ( Acl < 0 )
        goto LABEL_12;
      for ( j = 0; j < a3; ++j )
      {
        Acl = RtlAddAccessAllowedAceEx(
                v11,
                2u,
                *(_DWORD *)(a2 + 16LL * j + 12),
                *(_DWORD *)(a2 + 16LL * j + 8),
                *(PSID *)(a2 + 16LL * j));
        if ( Acl < 0 )
          goto LABEL_12;
      }
      Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
      if ( Acl < 0 )
LABEL_12:
        ExFreePoolWithTag(v11, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14012feac  push    rbx
0x14012feae  push    rbp
0x14012feaf  push    rsi
0x14012feb0  push    rdi
0x14012feb1  push    r14
0x14012feb3  push    r15
0x14012feb5  sub     rsp, 38h
0x14012feb9  mov     r14, rdx
0x14012febc  mov     ebp, r8d
0x14012febf  mov     edx, 1; Revision
0x14012fec4  mov     r15, rcx
0x14012fec7  call    cs:__imp_RtlCreateSecurityDescriptor
0x14012fece  nop     dword ptr [rax+rax+00h]
0x14012fed3  mov     ebx, eax
0x14012fed5  test    eax, eax
0x14012fed7  js      loc_14012FFCA
0x14012fedd  xor     ebx, ebx
0x14012fedf  mov     edi, 8
0x14012fee4  test    ebp, ebp
0x14012fee6  jz      short loc_14012FF08
0x14012fee8  mov     ecx, ebx
0x14012feea  add     rcx, rcx
0x14012feed  mov     rcx, [r14+rcx*8]; Sid
0x14012fef1  call    cs:__imp_RtlLengthSid
0x14012fef8  nop     dword ptr [rax+rax+00h]
0x14012fefd  add     edi, 0Ch
0x14012ff00  inc     ebx
0x14012ff02  add     edi, eax
0x14012ff04  cmp     ebx, ebp
0x14012ff06  jb      short loc_14012FEE8
0x14012ff08  mov     edx, edi
0x14012ff0a  lea     r9, UxLowPriorityPool
0x14012ff11  mov     ecx, 102h
0x14012ff16  mov     dword ptr [rsp+68h+Sid], 1
0x14012ff1e  mov     r8d, 44536C55h
0x14012ff24  call    cs:__imp_ExAllocatePool3
0x14012ff2b  nop     dword ptr [rax+rax+00h]
0x14012ff30  mov     rsi, rax
0x14012ff33  test    rax, rax
0x14012ff36  jnz     short loc_14012FF42
0x14012ff38  mov     ebx, 0C000009Ah
0x14012ff3d  jmp     loc_14012FFCA
0x14012ff42  mov     r8d, 2; AclRevision
0x14012ff48  mov     edx, edi; AclLength
0x14012ff4a  mov     rcx, rsi; Acl
0x14012ff4d  call    cs:__imp_RtlCreateAcl
0x14012ff54  nop     dword ptr [rax+rax+00h]
0x14012ff59  mov     ebx, eax
0x14012ff5b  test    eax, eax
0x14012ff5d  js      short loc_14012FFB9
0x14012ff5f  xor     edi, edi
0x14012ff61  cmp     edi, ebp
0x14012ff63  jnb     short loc_14012FF9C
0x14012ff65  mov     r8d, edi
0x14012ff68  mov     edx, 2; AceRevision
0x14012ff6d  add     r8, r8
0x14012ff70  mov     rcx, rsi; Acl
0x14012ff73  mov     rax, [r14+r8*8]
0x14012ff77  mov     r9d, [r14+r8*8+8]; AccessMask
0x14012ff7c  mov     r8d, [r14+r8*8+0Ch]; AceFlags
0x14012ff81  mov     [rsp+68h+Sid], rax; Sid
0x14012ff86  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14012ff8d  nop     dword ptr [rax+rax+00h]
0x14012ff92  mov     ebx, eax
0x14012ff94  test    eax, eax
0x14012ff96  js      short loc_14012FFB9
0x14012ff98  inc     edi
0x14012ff9a  jmp     short loc_14012FF61
0x14012ff9c  xor     r9d, r9d; DaclDefaulted
0x14012ff9f  mov     r8, rsi; Dacl
0x14012ffa2  mov     dl, 1; DaclPresent
0x14012ffa4  mov     rcx, r15; SecurityDescriptor
0x14012ffa7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14012ffae  nop     dword ptr [rax+rax+00h]
0x14012ffb3  mov     ebx, eax
0x14012ffb5  test    eax, eax
0x14012ffb7  jns     short loc_14012FFCA
0x14012ffb9  xor     edx, edx; Tag
0x14012ffbb  mov     rcx, rsi; P
0x14012ffbe  call    cs:__imp_ExFreePoolWithTag
0x14012ffc5  nop     dword ptr [rax+rax+00h]
0x14012ffca  mov     eax, ebx
0x14012ffcc  add     rsp, 38h
0x14012ffd0  pop     r15
0x14012ffd2  pop     r14
0x14012ffd4  pop     rdi
0x14012ffd5  pop     rsi
0x14012ffd6  pop     rbp
0x14012ffd7  pop     rbx
0x14012ffd8  retn
```
