# CIISTree::get_Filter(tagVARIANT *)

- ea: `0x180003950`
- end: `0x18000398d`
- name: `?get_Filter@CIISTree@@UEAAJPEAUtagVARIANT@@@Z`
- size: `61`
- prototype: `int(CIISTree *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003950`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000396f`
- `OLEAUT32!__imp_VariantInit` at `0x18000396f`
- `OLEAUT32!__imp_VariantCopy` at `0x18000397c`
- `OLEAUT32!__imp_VariantCopy` at `0x18000397c`

## pseudocode

```c
HRESULT __fastcall CIISTree::get_Filter(CIISTree *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147467261;
  VariantInit(a2);
  return VariantCopy(a2, (const VARIANTARG *)((char *)this + 16));
}

```

## disassembly

```asm
0x180003950  mov     [rsp+arg_0], rbx
0x180003955  push    rdi
0x180003956  sub     rsp, 20h
0x18000395a  mov     rbx, rdx
0x18000395d  mov     rdi, rcx
0x180003960  test    rdx, rdx
0x180003963  jnz     short loc_18000396C
0x180003965  mov     eax, 80004003h
0x18000396a  jmp     short loc_180003982
0x18000396c  mov     rcx, rbx; pvarg
0x18000396f  call    cs:__imp_VariantInit
0x180003975  lea     rdx, [rdi+10h]; pvargSrc
0x180003979  mov     rcx, rbx; pvargDest
0x18000397c  call    cs:__imp_VariantCopy
0x180003982  mov     rbx, [rsp+28h+arg_0]
0x180003987  add     rsp, 20h
0x18000398b  pop     rdi
0x18000398c  retn
```
