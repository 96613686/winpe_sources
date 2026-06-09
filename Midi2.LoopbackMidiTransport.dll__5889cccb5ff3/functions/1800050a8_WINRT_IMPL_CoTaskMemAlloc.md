# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x1800050a8`
- end: `0x1800050ae`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010940`
- `0x1800109d0`
- `0x180010a60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800050a8`

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
0x1800050a8  jmp     cs:__imp_CoTaskMemAlloc
```
