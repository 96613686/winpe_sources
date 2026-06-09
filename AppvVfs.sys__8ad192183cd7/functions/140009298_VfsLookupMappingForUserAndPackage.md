# VfsLookupMappingForUserAndPackage

- ea: `0x140009298`
- end: `0x140009331`
- name: `VfsLookupMappingForUserAndPackage`
- size: `153`
- prototype: `__int64 __fastcall(PVOID Buffer, int, int, int, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140002b4c`
- `0x1400034a0`
- `0x140007124`
- `0x140009f94`

## callees

- `0x14000559c`
- `0x1400059e8`
- `0x140009218`
- `0x140009298`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400092b1`
- `ntoskrnl!RtlLengthSid` at `0x1400092b1`

## pseudocode

```c
__int64 __fastcall VfsLookupMappingForUserAndPackage(PVOID Buffer, int a2, int a3, int a4, __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rbx

  RtlLengthSid(Buffer);
  v9 = VfsCtxTableElementLookup(&stru_14001F470, Buffer);
  v10 = v9;
  if ( !v9 )
    return VfsLookupMappingForPackage((unsigned int)&Table, a2, a3, a4, a5);
  v11 = VfsLookupMappingForPackage((int)v9 + 96, a2, a3, a4, a5);
  VfsUserCtxRelease(v10);
  if ( !v11 )
    return VfsLookupMappingForPackage((unsigned int)&Table, a2, a3, a4, a5);
  return v11;
}

```

## disassembly

```asm
0x140009298  push    rbx
0x14000929a  push    rbp
0x14000929b  push    rsi
0x14000929c  push    rdi
0x14000929d  push    r14
0x14000929f  push    r15
0x1400092a1  sub     rsp, 38h
0x1400092a5  mov     rsi, r9
0x1400092a8  mov     rbp, r8
0x1400092ab  mov     r14, rdx
0x1400092ae  mov     rbx, rcx
0x1400092b1  call    cs:__imp_RtlLengthSid
0x1400092b8  nop     dword ptr [rax+rax+00h]
0x1400092bd  mov     rdx, rbx; Buffer
0x1400092c0  lea     rcx, stru_14001F470; Table
0x1400092c7  call    VfsCtxTableElementLookup
0x1400092cc  mov     r15, [rsp+68h+arg_20]
0x1400092d4  mov     rdi, rax
0x1400092d7  test    rax, rax
0x1400092da  jz      short loc_140009303
0x1400092dc  lea     rcx, [rax+60h]
0x1400092e0  mov     [rsp+68h+var_48], r15
0x1400092e5  mov     r9, rsi
0x1400092e8  mov     r8, rbp
0x1400092eb  mov     rdx, r14
0x1400092ee  call    VfsLookupMappingForPackage
0x1400092f3  mov     rcx, rdi
0x1400092f6  mov     rbx, rax
0x1400092f9  call    VfsUserCtxRelease
0x1400092fe  test    rbx, rbx
0x140009301  jnz     short loc_140009320
0x140009303  mov     r9, rsi
0x140009306  mov     [rsp+68h+var_48], r15
0x14000930b  mov     r8, rbp
0x14000930e  lea     rcx, Table
0x140009315  mov     rdx, r14
0x140009318  call    VfsLookupMappingForPackage
0x14000931d  mov     rbx, rax
0x140009320  mov     rax, rbx
0x140009323  add     rsp, 38h
0x140009327  pop     r15
0x140009329  pop     r14
0x14000932b  pop     rdi
0x14000932c  pop     rsi
0x14000932d  pop     rbp
0x14000932e  pop     rbx
0x14000932f  retn
```
