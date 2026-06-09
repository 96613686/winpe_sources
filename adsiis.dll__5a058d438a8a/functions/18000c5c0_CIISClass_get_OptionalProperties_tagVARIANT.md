# CIISClass::get_OptionalProperties(tagVARIANT *)

- ea: `0x18000c5c0`
- end: `0x18000c5fd`
- name: `?get_OptionalProperties@CIISClass@@UEAAJPEAUtagVARIANT@@@Z`
- size: `61`
- prototype: `int(CIISClass *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c5c0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c5df`
- `OLEAUT32!__imp_VariantInit` at `0x18000c5df`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c5ec`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c5ec`

## pseudocode

```c
HRESULT __fastcall CIISClass::get_OptionalProperties(CIISClass *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147463160;
  VariantInit(a2);
  return VariantCopy(a2, (const VARIANTARG *)((char *)this + 80));
}

```

## disassembly

```asm
0x18000c5c0  mov     [rsp+arg_0], rbx
0x18000c5c5  push    rdi
0x18000c5c6  sub     rsp, 20h
0x18000c5ca  mov     rbx, rdx
0x18000c5cd  mov     rdi, rcx
0x18000c5d0  test    rdx, rdx
0x18000c5d3  jnz     short loc_18000C5DC
0x18000c5d5  mov     eax, 80005008h
0x18000c5da  jmp     short loc_18000C5F2
0x18000c5dc  mov     rcx, rbx; pvarg
0x18000c5df  call    cs:__imp_VariantInit
0x18000c5e5  lea     rdx, [rdi+50h]; pvargSrc
0x18000c5e9  mov     rcx, rbx; pvargDest
0x18000c5ec  call    cs:__imp_VariantCopy
0x18000c5f2  mov     rbx, [rsp+28h+arg_0]
0x18000c5f7  add     rsp, 20h
0x18000c5fb  pop     rdi
0x18000c5fc  retn
```
