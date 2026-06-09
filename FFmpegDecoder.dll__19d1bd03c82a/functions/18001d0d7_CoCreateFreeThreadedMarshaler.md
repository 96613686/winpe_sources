# CoCreateFreeThreadedMarshaler

- ea: `0x18001d0d7`
- end: `0x18001d0dd`
- name: `CoCreateFreeThreadedMarshaler`
- size: `6`
- prototype: `HRESULT __stdcall(LPUNKNOWN punkOuter, LPUNKNOWN *ppunkMarshal)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a84c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001d0d7`

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
0x18001d0d7  jmp     cs:__imp_CoCreateFreeThreadedMarshaler
```
