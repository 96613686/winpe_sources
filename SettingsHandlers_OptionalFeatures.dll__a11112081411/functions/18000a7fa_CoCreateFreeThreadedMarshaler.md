# CoCreateFreeThreadedMarshaler

- ea: `0x18000a7fa`
- end: `0x18000a800`
- name: `CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003d858`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000a7fa`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CoCreateFreeThreadedMarshaler(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)
{
  return __imp_CoCreateFreeThreadedMarshaler(punkOuter, ppunkMarshal);
}

```

## disassembly

```asm
0x18000a7fa  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
