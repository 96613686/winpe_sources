# _variant_t::_variant_t(_variant_t const &)

- ea: `0x1800036c4`
- end: `0x1800036fb`
- name: `??0_variant_t@@QEAA@AEBV0@@Z`
- size: `55`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003704`
- `0x180050738`

## callees

- `0x180019a50`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800036d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800036d4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800036e0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800036e0`

## pseudocode

```c
VARIANTARG *__fastcall _variant_t::_variant_t(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)
{
  HRESULT v4; // eax

  VariantInit(pvargDest);
  v4 = VariantCopy(pvargDest, pvargSrc);
  _com_util::CheckError(v4);
  return pvargDest;
}

```

## disassembly

```asm
0x1800036c4  mov     [rsp+arg_0], rbx
0x1800036c9  push    rdi
0x1800036ca  sub     rsp, 20h
0x1800036ce  mov     rbx, rdx
0x1800036d1  mov     rdi, rcx
0x1800036d4  call    cs:__imp_VariantInit
0x1800036da  mov     rdx, rbx; pvargSrc
0x1800036dd  mov     rcx, rdi; pvargDest
0x1800036e0  call    cs:__imp_VariantCopy
0x1800036e6  mov     ecx, eax; int
0x1800036e8  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x1800036ed  mov     rbx, [rsp+28h+arg_0]
0x1800036f2  mov     rax, rdi
0x1800036f5  add     rsp, 20h
0x1800036f9  pop     rdi
0x1800036fa  retn
```
