# WINRT_IMPL_CreateEventW

- ea: `0x180002f2d`
- end: `0x180002f33`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002f2d`

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
0x180002f2d  jmp     cs:__imp_CreateEventW
```
