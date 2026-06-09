# SepSddlAddAceToAcl

- ea: `0x14000d5f0`
- end: `0x14000d6db`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000d7c8`

## callees

- `0x1400027c0`
- `0x140002ac0`
- `0x14000d5f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d68e`
- `ntoskrnl!RtlLengthSid` at `0x14000d614`
- `ntoskrnl!RtlLengthSid` at `0x14000d614`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000d6bd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000d6bd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d64e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d64e`

## pseudocode

```c
NTSTATUS __fastcall SepSddlAddAceToAcl(
        const void **a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK AccessMask,
        int a6,
        PSID Sid)
{
  unsigned __int16 *v7; // rdi
  size_t v10; // rsi
  ULONG v11; // r8d
  int v12; // ebp
  unsigned int v13; // r12d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v15; // rbx

  v7 = (unsigned __int16 *)*a1;
  v10 = (unsigned int)*a2;
  v11 = RtlLengthSid(Sid) + 8;
  v12 = v11 + v10;
  if ( v11 + (unsigned int)v10 <= v7[1] )
  {
    v15 = (struct _ACL *)v7;
  }
  else
  {
    v13 = a6 * v11 + v10;
    PoolWithTag = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v13, 0x6C416553u);
    v15 = PoolWithTag;
    if ( !PoolWithTag )
      return -1073741670;
    memset(PoolWithTag, 0, v13);
    memmove(v15, *a1, v10);
    v15->AclSize = v13;
    ExFreePoolWithTag(v7, 0);
    *a1 = v15;
  }
  *a2 = v12;
  return RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
}

```

## disassembly

```asm
0x14000d5f0  push    rbx
0x14000d5f2  push    rbp
0x14000d5f3  push    rsi
0x14000d5f4  push    rdi
0x14000d5f5  push    r12
0x14000d5f7  push    r13
0x14000d5f9  push    r14
0x14000d5fb  push    r15
0x14000d5fd  sub     rsp, 28h
0x14000d601  mov     rdi, [rcx]
0x14000d604  mov     r15, rcx
0x14000d607  mov     rcx, [rsp+68h+Sid]; Sid
0x14000d60f  mov     r14, rdx
0x14000d612  mov     esi, [rdx]
0x14000d614  call    cs:__imp_RtlLengthSid
0x14000d61b  nop     dword ptr [rax+rax+00h]
0x14000d620  lea     r8d, [rax+8]
0x14000d624  movzx   eax, word ptr [rdi+2]
0x14000d628  lea     ebp, [r8+rsi]
0x14000d62c  cmp     ebp, eax
0x14000d62e  jbe     short loc_14000D69F
0x14000d630  imul    r8d, [rsp+68h+arg_28]
0x14000d639  mov     ecx, 1; PoolType
0x14000d63e  lea     r12d, [r8+rsi]
0x14000d642  mov     r8d, 6C416553h; Tag
0x14000d648  mov     edx, r12d; NumberOfBytes
0x14000d64b  mov     r13d, r12d
0x14000d64e  call    cs:__imp_ExAllocatePoolWithTag
0x14000d655  nop     dword ptr [rax+rax+00h]
0x14000d65a  mov     rbx, rax
0x14000d65d  test    rax, rax
0x14000d660  jnz     short loc_14000D669
0x14000d662  mov     eax, 0C000009Ah
0x14000d667  jmp     short loc_14000D6C9
0x14000d669  mov     r8, r13; Size
0x14000d66c  xor     edx, edx; Val
0x14000d66e  mov     rcx, rbx; void *
0x14000d671  call    memset
0x14000d676  mov     rdx, [r15]; Src
0x14000d679  mov     r8, rsi; Size
0x14000d67c  mov     rcx, rbx; void *
0x14000d67f  call    memmove
0x14000d684  xor     edx, edx; Tag
0x14000d686  mov     [rbx+2], r12w
0x14000d68b  mov     rcx, rdi; P
0x14000d68e  call    cs:__imp_ExFreePoolWithTag
0x14000d695  nop     dword ptr [rax+rax+00h]
0x14000d69a  mov     [r15], rbx
0x14000d69d  jmp     short loc_14000D6A2
0x14000d69f  mov     rbx, rdi
0x14000d6a2  mov     r9, [rsp+68h+Sid]; Sid
0x14000d6aa  mov     edx, 2; AceRevision
0x14000d6af  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14000d6b7  mov     rcx, rbx; Acl
0x14000d6ba  mov     [r14], ebp
0x14000d6bd  call    cs:__imp_RtlAddAccessAllowedAce
0x14000d6c4  nop     dword ptr [rax+rax+00h]
0x14000d6c9  add     rsp, 28h
0x14000d6cd  pop     r15
0x14000d6cf  pop     r14
0x14000d6d1  pop     r13
0x14000d6d3  pop     r12
0x14000d6d5  pop     rdi
0x14000d6d6  pop     rsi
0x14000d6d7  pop     rbp
0x14000d6d8  pop     rbx
0x14000d6d9  retn
```
