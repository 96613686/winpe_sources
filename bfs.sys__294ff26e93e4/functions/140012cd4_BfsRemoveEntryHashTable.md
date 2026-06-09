# BfsRemoveEntryHashTable

- ea: `0x140012cd4`
- end: `0x140012cf8`
- name: `BfsRemoveEntryHashTable`
- size: `36`
- prototype: `__int64 __fastcall(struct _RTL_DYNAMIC_HASH_TABLE *, struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400061d0`
- `0x14000be9c`
- `0x14000bfe8`
- `0x14000c4ac`
- `0x14000c7e8`
- `0x14000d734`
- `0x14000d900`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140012cdb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140012cdb`

## pseudocode

```c
__int64 __fastcall BfsRemoveEntryHashTable(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *a2)
{
  return RtlRemoveEntryHashTable(a1, a2, 0) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140012cd4  sub     rsp, 28h
0x140012cd8  xor     r8d, r8d; Context
0x140012cdb  call    cs:__imp_RtlRemoveEntryHashTable
0x140012ce2  nop     dword ptr [rax+rax+00h]
0x140012ce7  neg     al
0x140012ce9  sbb     eax, eax
0x140012ceb  not     eax
0x140012ced  and     eax, 0C0000001h
0x140012cf2  add     rsp, 28h
0x140012cf6  retn
```
