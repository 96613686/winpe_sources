# ATL::CComVariant::~CComVariant(void)

- ea: `0x140011a90`
- end: `0x140011aa0`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014f13`
- `0x1400150ef`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140011a94`
- `OLEAUT32!__imp_VariantClear` at `0x140011a94`

## pseudocode

```c
void __fastcall ATL::CComVariant::~CComVariant(VARIANTARG *this)
{
  VariantClear(this);
}

```

## disassembly

```asm
0x140011a90  sub     rsp, 28h
0x140011a94  call    cs:__imp_VariantClear
0x140011a9a  nop
0x140011a9b  add     rsp, 28h
0x140011a9f  retn
```
