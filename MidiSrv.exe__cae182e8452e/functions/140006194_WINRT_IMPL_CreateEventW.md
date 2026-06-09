# WINRT_IMPL_CreateEventW

- ea: `0x140006194`
- end: `0x14000619a`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001393c`
- `0x140022b88`
- `0x140022c84`
- `0x1400286f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006194`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WINRT_IMPL_CreateEventW(
        LPSECURITY_ATTRIBUTES lpEventAttributes,
        BOOL bManualReset,
        BOOL bInitialState,
        LPCWSTR lpName)
{
  return CreateEventW(lpEventAttributes, bManualReset, bInitialState, lpName);
}

```

## disassembly

```asm
0x140006194  jmp     cs:__imp_CreateEventW
```
