# WINRT_IMPL_CreateEventW

- ea: `0x18005c26e`
- end: `0x18005c274`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001043c`
- `0x1800114f0`
- `0x180012b78`
- `0x1800411f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c26e`

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
0x18005c26e  jmp     cs:__imp_CreateEventW
```
