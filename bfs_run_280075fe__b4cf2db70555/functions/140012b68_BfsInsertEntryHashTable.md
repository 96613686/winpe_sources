# BfsInsertEntryHashTable

- ea: `0x140012b68`
- end: `0x140012b95`
- name: `BfsInsertEntryHashTable`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007890`
- `0x140007b60`
- `0x140007e5c`
- `0x140008598`
- `0x14000b4c4`
- `0x14000bf64`
- `0x14000d848`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140012b78`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140012b78`

## pseudocode

```c
__int64 __fastcall BfsInsertEntryHashTable(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        ULONG_PTR a2,
        struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *a3)
{
  return RtlInsertEntryHashTable(a1, a3, a2, 0) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140012b68  sub     rsp, 28h
0x140012b6c  mov     rax, r8
0x140012b6f  xor     r9d, r9d; Context
0x140012b72  mov     r8, rdx; Signature
0x140012b75  mov     rdx, rax; Entry
0x140012b78  call    cs:__imp_RtlInsertEntryHashTable
0x140012b7f  nop     dword ptr [rax+rax+00h]
0x140012b84  neg     al
0x140012b86  sbb     eax, eax
0x140012b88  not     eax
0x140012b8a  and     eax, 0C0000001h
0x140012b8f  add     rsp, 28h
0x140012b93  retn
```
