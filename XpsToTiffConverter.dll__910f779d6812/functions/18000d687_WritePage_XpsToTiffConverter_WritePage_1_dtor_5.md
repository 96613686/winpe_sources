# _WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$5

- ea: `0x18000d687`
- end: `0x18000d693`
- name: `_WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009d5c`

## pseudocode

```c
HRESULT __fastcall WritePage::XpsToTiffConverter::WritePage_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::~unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>((VARIANTARG *)(a2 + 136));
}

```

## disassembly

```asm
0x18000d687  lea     rcx, [rdx+88h]; pvarg
0x18000d68e  jmp     ??1?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAA@XZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::~unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>(void)
```
