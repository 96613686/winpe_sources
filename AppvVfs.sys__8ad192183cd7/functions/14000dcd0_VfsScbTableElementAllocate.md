# VfsScbTableElementAllocate

- ea: `0x14000dcd0`
- end: `0x14000dd0b`
- name: `VfsScbTableElementAllocate`
- size: `59`
- prototype: `PVOID __fastcall(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000dcd0`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000dcdd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000dcdd`

## pseudocode

```c
PVOID __fastcall VfsScbTableElementAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  PVOID v2; // rax
  PVOID v3; // rbx

  v2 = ExAllocateFromPagedLookasideList(&stru_14001F600);
  v3 = v2;
  if ( v2 )
    memset(v2, 0, 0xA0u);
  return v3;
}

```

## disassembly

```asm
0x14000dcd0  push    rbx
0x14000dcd2  sub     rsp, 20h
0x14000dcd6  lea     rcx, stru_14001F600; Lookaside
0x14000dcdd  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000dce4  nop     dword ptr [rax+rax+00h]
0x14000dce9  mov     rbx, rax
0x14000dcec  test    rax, rax
0x14000dcef  jz      short loc_14000DD01
0x14000dcf1  xor     edx, edx; Val
0x14000dcf3  mov     r8d, 0A0h; Size
0x14000dcf9  mov     rcx, rax; void *
0x14000dcfc  call    memset
0x14000dd01  mov     rax, rbx
0x14000dd04  add     rsp, 20h
0x14000dd08  pop     rbx
0x14000dd09  retn
```
