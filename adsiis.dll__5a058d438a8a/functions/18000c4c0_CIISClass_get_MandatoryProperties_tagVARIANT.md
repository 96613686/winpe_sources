# CIISClass::get_MandatoryProperties(tagVARIANT *)

- ea: `0x18000c4c0`
- end: `0x18000c4fd`
- name: `?get_MandatoryProperties@CIISClass@@UEAAJPEAUtagVARIANT@@@Z`
- size: `61`
- prototype: `int(CIISClass *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c4c0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c4df`
- `OLEAUT32!__imp_VariantInit` at `0x18000c4df`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c4ec`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c4ec`

## pseudocode

```c
HRESULT __fastcall CIISClass::get_MandatoryProperties(CIISClass *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147463160;
  VariantInit(a2);
  return VariantCopy(a2, (const VARIANTARG *)((char *)this + 56));
}

```

## disassembly

```asm
0x18000c4c0  mov     [rsp+arg_0], rbx
0x18000c4c5  push    rdi
0x18000c4c6  sub     rsp, 20h
0x18000c4ca  mov     rbx, rdx
0x18000c4cd  mov     rdi, rcx
0x18000c4d0  test    rdx, rdx
0x18000c4d3  jnz     short loc_18000C4DC
0x18000c4d5  mov     eax, 80005008h
0x18000c4da  jmp     short loc_18000C4F2
0x18000c4dc  mov     rcx, rbx; pvarg
0x18000c4df  call    cs:__imp_VariantInit
0x18000c4e5  lea     rdx, [rdi+38h]; pvargSrc
0x18000c4e9  mov     rcx, rbx; pvargDest
0x18000c4ec  call    cs:__imp_VariantCopy
0x18000c4f2  mov     rbx, [rsp+28h+arg_0]
0x18000c4f7  add     rsp, 20h
0x18000c4fb  pop     rdi
0x18000c4fc  retn
```
