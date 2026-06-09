# VfsScbTableElementFree

- ea: `0x14000dde0`
- end: `0x14000ddfd`
- name: `VfsScbTableElementFree`
- size: `29`
- prototype: `void __fastcall(struct _RTL_AVL_TABLE *Table, PVOID Buffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000ddeb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000ddeb`

## pseudocode

```c
void __fastcall VfsScbTableElementFree(struct _RTL_AVL_TABLE *Table, PVOID Buffer)
{
  ExFreeToPagedLookasideList(&stru_14001F600, Buffer);
}

```

## disassembly

```asm
0x14000dde0  sub     rsp, 28h
0x14000dde4  lea     rcx, stru_14001F600; Lookaside
0x14000ddeb  call    cs:__imp_ExFreeToPagedLookasideList
0x14000ddf2  nop     dword ptr [rax+rax+00h]
0x14000ddf7  add     rsp, 28h
0x14000ddfb  retn
```
