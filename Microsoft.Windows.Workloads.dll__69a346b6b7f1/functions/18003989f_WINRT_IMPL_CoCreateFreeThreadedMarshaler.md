# WINRT_IMPL_CoCreateFreeThreadedMarshaler

- ea: `0x18003989f`
- end: `0x1800398a5`
- name: `WINRT_IMPL_CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800107a0`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18003989f`

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
0x18003989f  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
