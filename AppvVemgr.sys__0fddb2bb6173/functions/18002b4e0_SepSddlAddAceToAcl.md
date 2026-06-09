# SepSddlAddAceToAcl

- ea: `0x18002b4e0`
- end: `0x18002b5cb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `NTSTATUS __fastcall(const void **, _DWORD *, __int64, __int64, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002b6b8`

## callees

- `0x18001bc00`
- `0x18001bf00`
- `0x18002b4e0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x18002b504`
- `ntoskrnl!RtlLengthSid` at `0x18002b504`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002b57e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002b57e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x18002b5ad`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x18002b5ad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b53e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002b53e`

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
0x18002b4e0  push    rbx
0x18002b4e2  push    rbp
0x18002b4e3  push    rsi
0x18002b4e4  push    rdi
0x18002b4e5  push    r12
0x18002b4e7  push    r13
0x18002b4e9  push    r14
0x18002b4eb  push    r15
0x18002b4ed  sub     rsp, 28h
0x18002b4f1  mov     rdi, [rcx]
0x18002b4f4  mov     r15, rcx
0x18002b4f7  mov     rcx, [rsp+68h+Sid]; Sid
0x18002b4ff  mov     r14, rdx
0x18002b502  mov     esi, [rdx]
0x18002b504  call    cs:__imp_RtlLengthSid
0x18002b50b  nop     dword ptr [rax+rax+00h]
0x18002b510  lea     r8d, [rax+8]
0x18002b514  movzx   eax, word ptr [rdi+2]
0x18002b518  lea     ebp, [r8+rsi]
0x18002b51c  cmp     ebp, eax
0x18002b51e  jbe     short loc_18002B58F
0x18002b520  imul    r8d, [rsp+68h+arg_28]
0x18002b529  mov     ecx, 1; PoolType
0x18002b52e  lea     r12d, [r8+rsi]
0x18002b532  mov     r8d, 6C416553h; Tag
0x18002b538  mov     edx, r12d; NumberOfBytes
0x18002b53b  mov     r13d, r12d
0x18002b53e  call    cs:__imp_ExAllocatePoolWithTag
0x18002b545  nop     dword ptr [rax+rax+00h]
0x18002b54a  mov     rbx, rax
0x18002b54d  test    rax, rax
0x18002b550  jnz     short loc_18002B559
0x18002b552  mov     eax, 0C000009Ah
0x18002b557  jmp     short loc_18002B5B9
0x18002b559  mov     r8, r13; Size
0x18002b55c  xor     edx, edx; Val
0x18002b55e  mov     rcx, rbx; void *
0x18002b561  call    memset
0x18002b566  mov     rdx, [r15]; Src
0x18002b569  mov     r8, rsi; Size
0x18002b56c  mov     rcx, rbx; void *
0x18002b56f  call    memmove
0x18002b574  xor     edx, edx; Tag
0x18002b576  mov     [rbx+2], r12w
0x18002b57b  mov     rcx, rdi; P
0x18002b57e  call    cs:__imp_ExFreePoolWithTag
0x18002b585  nop     dword ptr [rax+rax+00h]
0x18002b58a  mov     [r15], rbx
0x18002b58d  jmp     short loc_18002B592
0x18002b58f  mov     rbx, rdi
0x18002b592  mov     r9, [rsp+68h+Sid]; Sid
0x18002b59a  mov     edx, 2; AceRevision
0x18002b59f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x18002b5a7  mov     rcx, rbx; Acl
0x18002b5aa  mov     [r14], ebp
0x18002b5ad  call    cs:__imp_RtlAddAccessAllowedAce
0x18002b5b4  nop     dword ptr [rax+rax+00h]
0x18002b5b9  add     rsp, 28h
0x18002b5bd  pop     r15
0x18002b5bf  pop     r14
0x18002b5c1  pop     r13
0x18002b5c3  pop     r12
0x18002b5c5  pop     rdi
0x18002b5c6  pop     rsi
0x18002b5c7  pop     rbp
0x18002b5c8  pop     rbx
0x18002b5c9  retn
```
