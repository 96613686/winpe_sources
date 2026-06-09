# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x18000b813`
- end: `0x18000b819`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800064b0`
- `0x180006850`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b813`

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
0x18000b813  jmp     cs:__imp_CoTaskMemAlloc
```
