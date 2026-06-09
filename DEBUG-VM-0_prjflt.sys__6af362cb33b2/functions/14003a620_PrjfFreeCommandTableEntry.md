# PrjfFreeCommandTableEntry

- ea: `0x14003a620`
- end: `0x14003a63e`
- name: `PrjfFreeCommandTableEntry`
- size: `30`
- prototype: `RTL_AVL_FREE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a62c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a62c`

## pseudocode

```c
void __fastcall PrjfFreeCommandTableEntry(struct _RTL_AVL_TABLE *Table, PVOID Buffer)
{
  ExFreePoolWithTag(Buffer, 0x6F634A50u);
}

```

## disassembly

```asm
0x14003a620  sub     rsp, 28h
0x14003a624  mov     rcx, rdx; P
0x14003a627  mov     edx, 6F634A50h; Tag
0x14003a62c  call    cs:__imp_ExFreePoolWithTag
0x14003a633  nop     dword ptr [rax+rax+00h]
0x14003a638  add     rsp, 28h
0x14003a63c  retn
```
