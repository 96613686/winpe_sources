# SepSddlAddAceToAcl

- ea: `0x140024ae0`
- end: `0x140024bcb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140024cb8`

## callees

- `0x140013d00`
- `0x140014000`
- `0x140024ae0`

## import_xrefs

- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140024bad`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140024bad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024b3e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140024b3e`
- `ntoskrnl!RtlLengthSid` at `0x140024b04`
- `ntoskrnl!RtlLengthSid` at `0x140024b04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b7e`

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
0x140024ae0  push    rbx
0x140024ae2  push    rbp
0x140024ae3  push    rsi
0x140024ae4  push    rdi
0x140024ae5  push    r12
0x140024ae7  push    r13
0x140024ae9  push    r14
0x140024aeb  push    r15
0x140024aed  sub     rsp, 28h
0x140024af1  mov     rdi, [rcx]
0x140024af4  mov     r15, rcx
0x140024af7  mov     rcx, [rsp+68h+Sid]; Sid
0x140024aff  mov     r14, rdx
0x140024b02  mov     esi, [rdx]
0x140024b04  call    cs:__imp_RtlLengthSid
0x140024b0b  nop     dword ptr [rax+rax+00h]
0x140024b10  lea     r8d, [rax+8]
0x140024b14  movzx   eax, word ptr [rdi+2]
0x140024b18  lea     ebp, [r8+rsi]
0x140024b1c  cmp     ebp, eax
0x140024b1e  jbe     short loc_140024B8F
0x140024b20  imul    r8d, [rsp+68h+arg_28]
0x140024b29  mov     ecx, 1; PoolType
0x140024b2e  lea     r12d, [r8+rsi]
0x140024b32  mov     r8d, 6C416553h; Tag
0x140024b38  mov     edx, r12d; NumberOfBytes
0x140024b3b  mov     r13d, r12d
0x140024b3e  call    cs:__imp_ExAllocatePoolWithTag
0x140024b45  nop     dword ptr [rax+rax+00h]
0x140024b4a  mov     rbx, rax
0x140024b4d  test    rax, rax
0x140024b50  jnz     short loc_140024B59
0x140024b52  mov     eax, 0C000009Ah
0x140024b57  jmp     short loc_140024BB9
0x140024b59  mov     r8, r13; Size
0x140024b5c  xor     edx, edx; Val
0x140024b5e  mov     rcx, rbx; void *
0x140024b61  call    memset
0x140024b66  mov     rdx, [r15]; Src
0x140024b69  mov     r8, rsi; Size
0x140024b6c  mov     rcx, rbx; void *
0x140024b6f  call    memmove
0x140024b74  xor     edx, edx; Tag
0x140024b76  mov     [rbx+2], r12w
0x140024b7b  mov     rcx, rdi; P
0x140024b7e  call    cs:__imp_ExFreePoolWithTag
0x140024b85  nop     dword ptr [rax+rax+00h]
0x140024b8a  mov     [r15], rbx
0x140024b8d  jmp     short loc_140024B92
0x140024b8f  mov     rbx, rdi
0x140024b92  mov     r9, [rsp+68h+Sid]; Sid
0x140024b9a  mov     edx, 2; AceRevision
0x140024b9f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140024ba7  mov     rcx, rbx; Acl
0x140024baa  mov     [r14], ebp
0x140024bad  call    cs:__imp_RtlAddAccessAllowedAce
0x140024bb4  nop     dword ptr [rax+rax+00h]
0x140024bb9  add     rsp, 28h
0x140024bbd  pop     r15
0x140024bbf  pop     r14
0x140024bc1  pop     r13
0x140024bc3  pop     r12
0x140024bc5  pop     rdi
0x140024bc6  pop     rsi
0x140024bc7  pop     rbp
0x140024bc8  pop     rbx
0x140024bc9  retn
```
