# ATL::CComVariant::~CComVariant(void)

- ea: `0x180003264`
- end: `0x18000326b`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800330ab`
- `0x1800330bd`
- `0x180033ae7`
- `0x180033b88`
- `0x180033c06`
- `0x180033ccb`
- `0x180034029`
- `0x18003405f`
- `0x180034083`
- `0x180034101`
- `0x180034137`
- `0x180034149`
- `0x18003416d`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180003264`

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
0x180003264  jmp     cs:__imp_VariantClear
```
