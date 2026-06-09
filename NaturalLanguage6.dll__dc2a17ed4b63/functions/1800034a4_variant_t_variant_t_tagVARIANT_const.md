# _variant_t::_variant_t(tagVARIANT const &)

- ea: `0x1800034a4`
- end: `0x1800034e0`
- name: `??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z`
- size: `60`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019b10`
- `0x180057140`
- `0x180057570`

## callees

- `0x1800034a4`
- `0x180003894`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800034b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800034b4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800034c0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800034c0`

## pseudocode

```c
VARIANTARG *__fastcall _variant_t::_variant_t(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)
{
  HRESULT v4; // eax

  VariantInit(pvargDest);
  v4 = VariantCopy(pvargDest, pvargSrc);
  if ( v4 < 0 )
    _com_issue_error(v4);
  return pvargDest;
}

```

## disassembly

```asm
0x1800034a4  mov     [rsp+arg_0], rbx
0x1800034a9  push    rdi
0x1800034aa  sub     rsp, 20h
0x1800034ae  mov     rbx, rdx
0x1800034b1  mov     rdi, rcx
0x1800034b4  call    cs:__imp_VariantInit
0x1800034ba  mov     rdx, rbx; pvargSrc
0x1800034bd  mov     rcx, rdi; pvargDest
0x1800034c0  call    cs:__imp_VariantCopy
0x1800034c6  test    eax, eax
0x1800034c8  js      short loc_1800034D8
0x1800034ca  mov     rbx, [rsp+28h+arg_0]
0x1800034cf  mov     rax, rdi
0x1800034d2  add     rsp, 20h
0x1800034d6  pop     rdi
0x1800034d7  retn
0x1800034d8  mov     ecx, eax; int
0x1800034da  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
