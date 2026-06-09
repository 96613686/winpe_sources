# CoCreateFreeThreadedMarshaler_0

- ea: `0x1400039e6`
- end: `0x1400039ec`
- name: `CoCreateFreeThreadedMarshaler_0`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140008470`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400039e6`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CoCreateFreeThreadedMarshaler_0(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)
{
  return CoCreateFreeThreadedMarshaler(punkOuter, ppunkMarshal);
}

```

## disassembly

```asm
0x1400039e6  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
