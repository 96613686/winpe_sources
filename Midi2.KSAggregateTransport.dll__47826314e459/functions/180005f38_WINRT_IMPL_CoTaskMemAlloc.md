# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x180005f38`
- end: `0x180005f3e`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800159a0`
- `0x180015a30`
- `0x180015ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f38`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall WINRT_IMPL_CoTaskMemAlloc(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x180005f38  jmp     cs:__imp_CoTaskMemAlloc
```
