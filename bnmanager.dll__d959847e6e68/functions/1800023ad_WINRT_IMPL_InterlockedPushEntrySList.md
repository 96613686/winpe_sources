# WINRT_IMPL_InterlockedPushEntrySList

- ea: `0x1800023ad`
- end: `0x1800023b3`
- name: `WINRT_IMPL_InterlockedPushEntrySList`
- size: `6`
- prototype: `PSLIST_ENTRY __stdcall(PSLIST_HEADER ListHead, PSLIST_ENTRY ListEntry)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800033c0`
- `0x18000355c`
- `0x180003730`
- `0x1800038cc`
- `0x180003a28`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x1800023ad`

## pseudocode

```c
// attributes: thunk
PSLIST_ENTRY __stdcall WINRT_IMPL_InterlockedPushEntrySList(PSLIST_HEADER ListHead, PSLIST_ENTRY ListEntry)
{
  return InterlockedPushEntrySList(ListHead, ListEntry);
}

```

## disassembly

```asm
0x1800023ad  jmp     cs:__imp_InterlockedPushEntrySList
```
