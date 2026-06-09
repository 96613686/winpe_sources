# CreateEventW

- ea: `0x18002cfb3`
- end: `0x18002cfb9`
- name: `CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180019a4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cfb3`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateEventW(
        LPSECURITY_ATTRIBUTES lpEventAttributes,
        BOOL bManualReset,
        BOOL bInitialState,
        LPCWSTR lpName)
{
  return __imp_CreateEventW(lpEventAttributes, bManualReset, bInitialState, lpName);
}

```

## disassembly

```asm
0x18002cfb3  jmp     cs:__imp_CreateEventW
```
