# ATL::CComVariant::~CComVariant(void)

- ea: `0x18000a8c4`
- end: `0x18000a8cb`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013973`
- `0x1800139f1`
- `0x180013a15`
- `0x180013ac9`
- `0x180013c83`
- `0x180013c95`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000a8c4`

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
0x18000a8c4  jmp     cs:__imp_VariantClear
```
