# CIISProperty::get_Default(tagVARIANT *)

- ea: `0x18000c410`
- end: `0x18000c44d`
- name: `?get_Default@CIISProperty@@UEAAJPEAUtagVARIANT@@@Z`
- size: `61`
- prototype: `int(CIISProperty *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c410`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c42f`
- `OLEAUT32!__imp_VariantInit` at `0x18000c42f`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c43c`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c43c`

## pseudocode

```c
HRESULT __fastcall CIISProperty::get_Default(CIISProperty *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147467261;
  VariantInit(a2);
  return VariantCopy(a2, (const VARIANTARG *)((char *)this + 64));
}

```

## disassembly

```asm
0x18000c410  mov     [rsp+arg_0], rbx
0x18000c415  push    rdi
0x18000c416  sub     rsp, 20h
0x18000c41a  mov     rbx, rdx
0x18000c41d  mov     rdi, rcx
0x18000c420  test    rdx, rdx
0x18000c423  jnz     short loc_18000C42C
0x18000c425  mov     eax, 80004003h
0x18000c42a  jmp     short loc_18000C442
0x18000c42c  mov     rcx, rbx; pvarg
0x18000c42f  call    cs:__imp_VariantInit
0x18000c435  lea     rdx, [rdi+40h]; pvargSrc
0x18000c439  mov     rcx, rbx; pvargDest
0x18000c43c  call    cs:__imp_VariantCopy
0x18000c442  mov     rbx, [rsp+28h+arg_0]
0x18000c447  add     rsp, 20h
0x18000c44b  pop     rdi
0x18000c44c  retn
```
