# Common::AutoVariant::~AutoVariant(void)

- ea: `0x140011774`
- end: `0x14001177b`
- name: `??1AutoVariant@Common@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400138d8`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140011774`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall Common::AutoVariant::~AutoVariant(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x140011774  jmp     cs:__imp_VariantClear
```
