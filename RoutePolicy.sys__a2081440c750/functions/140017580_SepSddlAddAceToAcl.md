# SepSddlAddAceToAcl

- ea: `0x140017580`
- end: `0x14001766b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140017758`

## callees

- `0x14000a780`
- `0x14000aa80`
- `0x140017580`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400175de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400175de`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001764d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001764d`
- `ntoskrnl!RtlLengthSid` at `0x1400175a4`
- `ntoskrnl!RtlLengthSid` at `0x1400175a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001761e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001761e`

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
0x140017580  push    rbx
0x140017582  push    rbp
0x140017583  push    rsi
0x140017584  push    rdi
0x140017585  push    r12
0x140017587  push    r13
0x140017589  push    r14
0x14001758b  push    r15
0x14001758d  sub     rsp, 28h
0x140017591  mov     rdi, [rcx]
0x140017594  mov     r15, rcx
0x140017597  mov     rcx, [rsp+68h+Sid]; Sid
0x14001759f  mov     r14, rdx
0x1400175a2  mov     esi, [rdx]
0x1400175a4  call    cs:__imp_RtlLengthSid
0x1400175ab  nop     dword ptr [rax+rax+00h]
0x1400175b0  lea     r8d, [rax+8]
0x1400175b4  movzx   eax, word ptr [rdi+2]
0x1400175b8  lea     ebp, [r8+rsi]
0x1400175bc  cmp     ebp, eax
0x1400175be  jbe     short loc_14001762F
0x1400175c0  imul    r8d, [rsp+68h+arg_28]
0x1400175c9  mov     ecx, 1; PoolType
0x1400175ce  lea     r12d, [r8+rsi]
0x1400175d2  mov     r8d, 6C416553h; Tag
0x1400175d8  mov     edx, r12d; NumberOfBytes
0x1400175db  mov     r13d, r12d
0x1400175de  call    cs:__imp_ExAllocatePoolWithTag
0x1400175e5  nop     dword ptr [rax+rax+00h]
0x1400175ea  mov     rbx, rax
0x1400175ed  test    rax, rax
0x1400175f0  jnz     short loc_1400175F9
0x1400175f2  mov     eax, 0C000009Ah
0x1400175f7  jmp     short loc_140017659
0x1400175f9  mov     r8, r13; Size
0x1400175fc  xor     edx, edx; Val
0x1400175fe  mov     rcx, rbx; void *
0x140017601  call    memset
0x140017606  mov     rdx, [r15]; Src
0x140017609  mov     r8, rsi; Size
0x14001760c  mov     rcx, rbx; void *
0x14001760f  call    memmove
0x140017614  xor     edx, edx; Tag
0x140017616  mov     [rbx+2], r12w
0x14001761b  mov     rcx, rdi; P
0x14001761e  call    cs:__imp_ExFreePoolWithTag
0x140017625  nop     dword ptr [rax+rax+00h]
0x14001762a  mov     [r15], rbx
0x14001762d  jmp     short loc_140017632
0x14001762f  mov     rbx, rdi
0x140017632  mov     r9, [rsp+68h+Sid]; Sid
0x14001763a  mov     edx, 2; AceRevision
0x14001763f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140017647  mov     rcx, rbx; Acl
0x14001764a  mov     [r14], ebp
0x14001764d  call    cs:__imp_RtlAddAccessAllowedAce
0x140017654  nop     dword ptr [rax+rax+00h]
0x140017659  add     rsp, 28h
0x14001765d  pop     r15
0x14001765f  pop     r14
0x140017661  pop     r13
0x140017663  pop     r12
0x140017665  pop     rdi
0x140017666  pop     rsi
0x140017667  pop     rbp
0x140017668  pop     rbx
0x140017669  retn
```
