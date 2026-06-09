# WINRT_IMPL_CoCreateFreeThreadedMarshaler

- ea: `0x1400062ec`
- end: `0x1400062f2`
- name: `WINRT_IMPL_CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140013cdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400062ec`

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
0x1400062ec  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
