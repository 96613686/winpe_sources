# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x180008e45`
- end: `0x180008e4b`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800147d0`
- `0x180014860`
- `0x1800148f0`
- `0x180028770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008e45`

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
0x180008e45  jmp     cs:__imp_CoTaskMemAlloc
```
