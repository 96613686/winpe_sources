# InterlockedPushEntrySList

- ea: `0x18002cc97`
- end: `0x18002cc9d`
- name: `InterlockedPushEntrySList`
- size: `6`
- prototype: `PSLIST_ENTRY __stdcall(PSLIST_HEADER ListHead, PSLIST_ENTRY ListEntry)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180006cbc`
- `0x18000972c`
- `0x180017300`
- `0x180018248`
- `0x180019e58`
- `0x18001a310`
- `0x18001e9b4`
- `0x180020ee8`
- `0x18002130c`
- `0x180021528`
- `0x1800216b4`
- `0x180021970`
- `0x180021afc`
- `0x180021dc0`
- `0x180021ff0`
- `0x180022124`
- `0x180022404`
- `0x1800225dc`
- `0x180022840`
- `0x18002605c`
- `0x1800277a4`
- `0x180027974`
- `0x180027b38`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18002cc97`

## pseudocode

```c
// attributes: thunk
PSLIST_ENTRY __stdcall InterlockedPushEntrySList(PSLIST_HEADER ListHead, PSLIST_ENTRY ListEntry)
{
  return __imp_InterlockedPushEntrySList(ListHead, ListEntry);
}

```

## disassembly

```asm
0x18002cc97  jmp     cs:__imp_InterlockedPushEntrySList
```
