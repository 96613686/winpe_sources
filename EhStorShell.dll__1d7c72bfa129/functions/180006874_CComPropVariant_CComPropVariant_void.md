# CComPropVariant::~CComPropVariant(void)

- ea: `0x180006874`
- end: `0x18000687b`
- name: `??1CComPropVariant@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b8da`

## import_xrefs

- `ole32!PropVariantClear` at `0x180006874`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CComPropVariant::~CComPropVariant(PROPVARIANT *pvar)
{
  return PropVariantClear(pvar);
}

```

## disassembly

```asm
0x180006874  jmp     cs:__imp_PropVariantClear
```
