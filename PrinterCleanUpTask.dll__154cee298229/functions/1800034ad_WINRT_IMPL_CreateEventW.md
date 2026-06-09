# WINRT_IMPL_CreateEventW

- ea: `0x1800034ad`
- end: `0x1800034b3`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009710`
- `0x1800097d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800034ad`

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
0x1800034ad  jmp     cs:__imp_CreateEventW
```
