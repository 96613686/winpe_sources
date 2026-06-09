# VfsUserCtxTableElementAllocate

- ea: `0x140005a30`
- end: `0x140005a6b`
- name: `VfsUserCtxTableElementAllocate`
- size: `59`
- prototype: `PVOID __fastcall(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140005a30`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140005a3d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140005a3d`

## pseudocode

```c
PVOID __fastcall VfsUserCtxTableElementAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  PVOID v2; // rax
  PVOID v3; // rbx

  v2 = ExAllocateFromPagedLookasideList(&stru_14001F580);
  v3 = v2;
  if ( v2 )
    memset(v2, 0, 0x110u);
  return v3;
}

```

## disassembly

```asm
0x140005a30  push    rbx
0x140005a32  sub     rsp, 20h
0x140005a36  lea     rcx, stru_14001F580; Lookaside
0x140005a3d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140005a44  nop     dword ptr [rax+rax+00h]
0x140005a49  mov     rbx, rax
0x140005a4c  test    rax, rax
0x140005a4f  jz      short loc_140005A61
0x140005a51  xor     edx, edx; Val
0x140005a53  mov     r8d, 110h; Size
0x140005a59  mov     rcx, rax; void *
0x140005a5c  call    memset
0x140005a61  mov     rax, rbx
0x140005a64  add     rsp, 20h
0x140005a68  pop     rbx
0x140005a69  retn
```
