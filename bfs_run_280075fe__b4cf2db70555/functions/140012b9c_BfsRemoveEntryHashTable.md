# BfsRemoveEntryHashTable

- ea: `0x140012b9c`
- end: `0x140012bc0`
- name: `BfsRemoveEntryHashTable`
- size: `36`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140006040`
- `0x14000bd0c`
- `0x14000be58`
- `0x14000c31c`
- `0x14000c658`
- `0x14000d5a0`
- `0x14000d76c`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140012ba3`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140012ba3`

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
0x140012b9c  sub     rsp, 28h
0x140012ba0  xor     r8d, r8d; Context
0x140012ba3  call    cs:__imp_RtlRemoveEntryHashTable
0x140012baa  nop     dword ptr [rax+rax+00h]
0x140012baf  neg     al
0x140012bb1  sbb     eax, eax
0x140012bb3  not     eax
0x140012bb5  and     eax, 0C0000001h
0x140012bba  add     rsp, 28h
0x140012bbe  retn
```
