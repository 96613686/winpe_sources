# ATL::CComVariant::~CComVariant(void)

- ea: `0x18000a6f8`
- end: `0x18000a6ff`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000bd8c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000a6f8`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall ATL::CComVariant::~CComVariant(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x18000a6f8  jmp     cs:__imp_VariantClear
```
