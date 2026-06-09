# CreateEventW_0

- ea: `0x1800023e7`
- end: `0x1800023ed`
- name: `CreateEventW_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013c68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800023e7`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateEventW_0(
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
0x1800023e7  jmp     cs:__imp_CreateEventW
```
