# WINRT_IMPL_CreateEventW

- ea: `0x180005fec`
- end: `0x180005ff2`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014098`
- `0x180021a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005fec`

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
0x180005fec  jmp     cs:__imp_CreateEventW
```
