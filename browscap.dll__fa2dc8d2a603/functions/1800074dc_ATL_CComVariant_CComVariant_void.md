# ATL::CComVariant::~CComVariant(void)

- ea: `0x1800074dc`
- end: `0x1800074e3`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000bd6d`
- `0x18000bdb5`
- `0x18000be4e`
- `0x18000be72`
- `0x18000be84`
- `0x18000be96`
- `0x18000bea8`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800074dc`

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
0x1800074dc  jmp     cs:__imp_VariantClear
```
