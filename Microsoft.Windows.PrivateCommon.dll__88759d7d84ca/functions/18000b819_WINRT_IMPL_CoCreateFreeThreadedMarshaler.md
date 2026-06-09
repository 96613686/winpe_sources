# WINRT_IMPL_CoCreateFreeThreadedMarshaler

- ea: `0x18000b819`
- end: `0x18000b81f`
- name: `WINRT_IMPL_CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000b819`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WINRT_IMPL_CoCreateFreeThreadedMarshaler(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)
{
  return CoCreateFreeThreadedMarshaler(punkOuter, ppunkMarshal);
}

```

## disassembly

```asm
0x18000b819  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
