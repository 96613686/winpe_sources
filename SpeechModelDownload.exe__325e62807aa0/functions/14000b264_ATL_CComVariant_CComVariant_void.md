# ATL::CComVariant::~CComVariant(void)

- ea: `0x14000b264`
- end: `0x14000b26b`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bee7`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x14000b264`

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
0x14000b264  jmp     cs:__imp_VariantClear
```
