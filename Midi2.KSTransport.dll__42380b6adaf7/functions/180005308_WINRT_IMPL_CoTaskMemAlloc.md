# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x180005308`
- end: `0x18000530e`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011b20`
- `0x180011bb0`
- `0x180011c40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005308`

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
0x180005308  jmp     cs:__imp_CoTaskMemAlloc
```
