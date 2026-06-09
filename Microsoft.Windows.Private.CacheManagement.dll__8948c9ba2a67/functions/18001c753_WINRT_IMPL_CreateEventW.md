# WINRT_IMPL_CreateEventW

- ea: `0x18001c753`
- end: `0x18001c759`
- name: `WINRT_IMPL_CreateEventW`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, BOOL bManualReset, BOOL bInitialState, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007c40`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18001c753`

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
0x18001c753  jmp     cs:__imp_CreateEventW
```
