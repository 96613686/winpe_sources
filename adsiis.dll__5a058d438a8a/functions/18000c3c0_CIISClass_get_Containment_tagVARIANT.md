# CIISClass::get_Containment(tagVARIANT *)

- ea: `0x18000c3c0`
- end: `0x18000c400`
- name: `?get_Containment@CIISClass@@UEAAJPEAUtagVARIANT@@@Z`
- size: `64`
- prototype: `int(CIISClass *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c3c0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c3df`
- `OLEAUT32!__imp_VariantInit` at `0x18000c3df`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c3ef`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c3ef`

## pseudocode

```c
HRESULT __fastcall CIISClass::get_Containment(CIISClass *this, struct tagVARIANT *a2)
{
  if ( !a2 )
    return -2147463160;
  VariantInit(a2);
  return VariantCopy(a2, (const VARIANTARG *)((char *)this + 128));
}

```

## disassembly

```asm
0x18000c3c0  mov     [rsp+arg_0], rbx
0x18000c3c5  push    rdi
0x18000c3c6  sub     rsp, 20h
0x18000c3ca  mov     rbx, rdx
0x18000c3cd  mov     rdi, rcx
0x18000c3d0  test    rdx, rdx
0x18000c3d3  jnz     short loc_18000C3DC
0x18000c3d5  mov     eax, 80005008h
0x18000c3da  jmp     short loc_18000C3F5
0x18000c3dc  mov     rcx, rbx; pvarg
0x18000c3df  call    cs:__imp_VariantInit
0x18000c3e5  lea     rdx, [rdi+80h]; pvargSrc
0x18000c3ec  mov     rcx, rbx; pvargDest
0x18000c3ef  call    cs:__imp_VariantCopy
0x18000c3f5  mov     rbx, [rsp+28h+arg_0]
0x18000c3fa  add     rsp, 20h
0x18000c3fe  pop     rdi
0x18000c3ff  retn
```
