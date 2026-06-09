# _variant_t::operator=(_variant_t const &)

- ea: `0x180032118`
- end: `0x180032137`
- name: `??4_variant_t@@QEAAAEAV0@AEBV0@@Z`
- size: `31`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *, const VARIANTARG *)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180031f88`
- `0x180031ff0`
- `0x1800366a4`
- `0x18003707c`
- `0x180052b00`
- `0x180052cf0`
- `0x180052df0`
- `0x180052fb0`
- `0x1800531b0`
- `0x1800532c0`
- `0x180053430`
- `0x180057570`
- `0x180057ec0`
- `0x18006b1d4`
- `0x18006b38c`
- `0x18006b554`

## callees

- `0x180019a50`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180032121`
- `OLEAUT32!__imp_VariantCopy` at `0x180032121`

## pseudocode

```c
VARIANTARG *__fastcall _variant_t::operator=(VARIANTARG *a1, const VARIANTARG *a2)
{
  HRESULT v3; // eax

  v3 = VariantCopy(a1, a2);
  _com_util::CheckError(v3);
  return a1;
}

```

## disassembly

```asm
0x180032118  push    rbx
0x18003211a  sub     rsp, 20h
0x18003211e  mov     rbx, rcx
0x180032121  call    cs:__imp_VariantCopy
0x180032127  mov     ecx, eax; int
0x180032129  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x18003212e  mov     rax, rbx
0x180032131  add     rsp, 20h
0x180032135  pop     rbx
0x180032136  retn
```
