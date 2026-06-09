# MpCreateSecurityDescriptor

- ea: `0x14008ee7c`
- end: `0x14008efe6`
- name: `MpCreateSecurityDescriptor`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008e860`

## callees

- `0x1400026c0`
- `0x14008ee7c`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14008eefc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14008eefc`
- `ntoskrnl!RtlCreateAcl` at `0x14008ef25`
- `ntoskrnl!RtlCreateAcl` at `0x14008ef25`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008ef4c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008ef6d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008ef4c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008ef6d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14008ef8d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14008ef8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008efb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094b0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008efb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094b0e`

## pseudocode

```c
__int64 __fastcall MpCreateSecurityDescriptor(__int64 a1, __int64 a2, struct _ACL **a3)
{
  unsigned __int8 *v4; // r12
  void *v5; // r13
  unsigned int v6; // r15d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v8; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  struct _ACL *v10; // rsi

  v4 = *(unsigned __int8 **)(MpData + 2376);
  v5 = *(void **)(MpData + 2392);
  v6 = 8 * v4[1] + 100;
  PoolWithTag = (struct _ACL *)MpAllocatePoolWithTag(1, v6, 1685278797);
  v8 = PoolWithTag;
  if ( PoolWithTag )
  {
    v10 = PoolWithTag + 5;
    SecurityDescriptor = RtlCreateSecurityDescriptor(PoolWithTag, 1u);
    if ( SecurityDescriptor >= 0 )
    {
      _mm_lfence();
      SecurityDescriptor = RtlCreateAcl(v10, v6 - 40, 2u);
      if ( SecurityDescriptor >= 0 )
      {
        _mm_lfence();
        SecurityDescriptor = RtlAddAccessAllowedAce(v10, 2u, 0x1F0001u, v4);
        if ( SecurityDescriptor >= 0 )
        {
          _mm_lfence();
          SecurityDescriptor = RtlAddAccessAllowedAce(v10, 2u, 0x1F0001u, v5);
          if ( SecurityDescriptor >= 0 )
          {
            _mm_lfence();
            SecurityDescriptor = RtlSetDaclSecurityDescriptor(v8, 1u, v10, 0);
            if ( SecurityDescriptor >= 0 )
            {
              *a3 = v8;
              v8 = 0;
              SecurityDescriptor = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    SecurityDescriptor = -1073741670;
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x6473504Du);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14008ee7c  mov     rax, rsp
0x14008ee7f  mov     [rax+8], rbx
0x14008ee83  mov     [rax+10h], rsi
0x14008ee87  mov     [rax+18h], rdi
0x14008ee8b  mov     [rax+20h], r12
0x14008ee8f  push    r13
0x14008ee91  push    r14
0x14008ee93  push    r15
0x14008ee95  sub     rsp, 30h
0x14008ee99  mov     r14, r8
0x14008ee9c  mov     qword ptr [rax-28h], 0
0x14008eea4  mov     rax, cs:MpData
0x14008eeab  mov     r12, [rax+948h]
0x14008eeb2  mov     r13, [rax+958h]
0x14008eeb9  movzx   eax, byte ptr [r12+1]
0x14008eebf  lea     r15d, ds:64h[rax*8]
0x14008eec7  mov     edx, r15d
0x14008eeca  mov     ebx, 1
0x14008eecf  mov     r8d, 6473504Dh
0x14008eed5  mov     ecx, ebx
0x14008eed7  call    MpAllocatePoolWithTag
0x14008eedc  mov     rdi, rax
0x14008eedf  mov     [rsp+48h+var_28], rax
0x14008eee4  test    rax, rax
0x14008eee7  jnz     short loc_14008EEF3
0x14008eee9  mov     ebx, 0C000009Ah
0x14008eeee  jmp     loc_14008EFAB
0x14008eef3  lea     rsi, [rax+28h]
0x14008eef7  mov     edx, ebx; Revision
0x14008eef9  mov     rcx, rdi; SecurityDescriptor
0x14008eefc  call    cs:__imp_RtlCreateSecurityDescriptor
0x14008ef03  nop     dword ptr [rax+rax+00h]
0x14008ef08  mov     ebx, eax
0x14008ef0a  test    eax, eax
0x14008ef0c  js      loc_14008EFAB
0x14008ef12  lfence
0x14008ef15  lea     edx, [r15-28h]; AclLength
0x14008ef19  mov     r15d, 2
0x14008ef1f  mov     r8d, r15d; AclRevision
0x14008ef22  mov     rcx, rsi; Acl
0x14008ef25  call    cs:__imp_RtlCreateAcl
0x14008ef2c  nop     dword ptr [rax+rax+00h]
0x14008ef31  mov     ebx, eax
0x14008ef33  test    eax, eax
0x14008ef35  js      short loc_14008EFAB
0x14008ef37  lfence
0x14008ef3a  mov     r9, r12; Sid
0x14008ef3d  mov     r12d, 1F0001h
0x14008ef43  mov     r8d, r12d; AccessMask
0x14008ef46  mov     edx, r15d; AceRevision
0x14008ef49  mov     rcx, rsi; Acl
0x14008ef4c  call    cs:__imp_RtlAddAccessAllowedAce
0x14008ef53  nop     dword ptr [rax+rax+00h]
0x14008ef58  mov     ebx, eax
0x14008ef5a  test    eax, eax
0x14008ef5c  js      short loc_14008EFAB
0x14008ef5e  lfence
0x14008ef61  mov     r9, r13; Sid
0x14008ef64  mov     r8d, r12d; AccessMask
0x14008ef67  mov     edx, r15d; AceRevision
0x14008ef6a  mov     rcx, rsi; Acl
0x14008ef6d  call    cs:__imp_RtlAddAccessAllowedAce
0x14008ef74  nop     dword ptr [rax+rax+00h]
0x14008ef79  mov     ebx, eax
0x14008ef7b  test    eax, eax
0x14008ef7d  js      short loc_14008EFAB
0x14008ef7f  lfence
0x14008ef82  xor     r9d, r9d; DaclDefaulted
0x14008ef85  mov     r8, rsi; Dacl
0x14008ef88  mov     dl, 1; DaclPresent
0x14008ef8a  mov     rcx, rdi; SecurityDescriptor
0x14008ef8d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14008ef94  nop     dword ptr [rax+rax+00h]
0x14008ef99  mov     ebx, eax
0x14008ef9b  test    eax, eax
0x14008ef9d  js      short loc_14008EFAB
0x14008ef9f  mov     [r14], rdi
0x14008efa2  xor     edi, edi
0x14008efa4  mov     [rsp+48h+var_28], rdi
0x14008efa9  xor     ebx, ebx
0x14008efab  test    rdi, rdi
0x14008efae  jz      short loc_14008EFC4
0x14008efb0  mov     edx, 6473504Dh; Tag
0x14008efb5  mov     rcx, rdi; P
0x14008efb8  call    cs:__imp_ExFreePoolWithTag
0x14008efbf  nop     dword ptr [rax+rax+00h]
0x14008efc4  mov     eax, ebx
0x14008efc6  mov     rbx, [rsp+48h+arg_0]
0x14008efcb  mov     rsi, [rsp+48h+arg_8]
0x14008efd0  mov     rdi, [rsp+48h+arg_10]
0x14008efd5  mov     r12, [rsp+48h+arg_18]
0x14008efda  add     rsp, 30h
0x14008efde  pop     r15
0x14008efe0  pop     r14
0x14008efe2  pop     r13
0x14008efe4  retn
0x140094af7  push    rbp
0x140094af9  sub     rsp, 20h
0x140094afd  mov     rbp, rdx
0x140094b00  mov     rcx, [rbp+20h]; P
0x140094b04  test    rcx, rcx
0x140094b07  jz      short loc_140094B1B
0x140094b09  mov     edx, 6473504Dh; Tag
0x140094b0e  call    cs:__imp_ExFreePoolWithTag
0x140094b15  nop     dword ptr [rax+rax+00h]
0x140094b1a  nop
0x140094b1b  add     rsp, 20h
0x140094b1f  pop     rbp
0x140094b20  retn
```
