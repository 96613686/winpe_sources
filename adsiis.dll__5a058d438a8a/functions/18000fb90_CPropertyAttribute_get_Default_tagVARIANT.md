# CPropertyAttribute::get_Default(tagVARIANT *)

- ea: `0x18000fb90`
- end: `0x18000fbd0`
- name: `?get_Default@CPropertyAttribute@@UEAAJPEAUtagVARIANT@@@Z`
- size: `64`
- prototype: `int(CPropertyAttribute *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fb90`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000fbaf`
- `OLEAUT32!__imp_VariantInit` at `0x18000fbaf`
- `OLEAUT32!__imp_VariantCopy` at `0x18000fbbf`
- `OLEAUT32!__imp_VariantCopy` at `0x18000fbbf`

## pseudocode

```c
HRESULT __fastcall CPropertyAttribute::get_Default(const VARIANTARG *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147467261;
  VariantInit(a2);
  return VariantCopy(a2, this + 24);
}

```

## disassembly

```asm
0x18000fb90  mov     [rsp+arg_0], rbx
0x18000fb95  push    rdi
0x18000fb96  sub     rsp, 20h
0x18000fb9a  mov     rbx, rdx
0x18000fb9d  mov     rdi, rcx
0x18000fba0  test    rdx, rdx
0x18000fba3  jnz     short loc_18000FBAC
0x18000fba5  mov     eax, 80004003h
0x18000fbaa  jmp     short loc_18000FBC5
0x18000fbac  mov     rcx, rbx; pvarg
0x18000fbaf  call    cs:__imp_VariantInit
0x18000fbb5  lea     rdx, [rdi+240h]; pvargSrc
0x18000fbbc  mov     rcx, rbx; pvargDest
0x18000fbbf  call    cs:__imp_VariantCopy
0x18000fbc5  mov     rbx, [rsp+28h+arg_0]
0x18000fbca  add     rsp, 20h
0x18000fbce  pop     rdi
0x18000fbcf  retn
```
