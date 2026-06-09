# CPropertyAttribute::put_Default(tagVARIANT)

- ea: `0x18000fd20`
- end: `0x18000fd54`
- name: `?put_Default@CPropertyAttribute@@UEAAJUtagVARIANT@@@Z`
- size: `52`
- prototype: `int(CPropertyAttribute *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000fd37`
- `OLEAUT32!__imp_VariantClear` at `0x18000fd37`
- `OLEAUT32!__imp_VariantCopy` at `0x18000fd43`
- `OLEAUT32!__imp_VariantCopy` at `0x18000fd43`

## pseudocode

```c
HRESULT __fastcall CPropertyAttribute::put_Default(VARIANTARG *this, struct tagVARIANT *a2)
{
  VARIANTARG *v2; // rbx

  v2 = this + 24;
  VariantClear(this + 24);
  return VariantCopy(v2, a2);
}

```

## disassembly

```asm
0x18000fd20  mov     [rsp+arg_0], rbx
0x18000fd25  push    rdi
0x18000fd26  sub     rsp, 20h
0x18000fd2a  lea     rbx, [rcx+240h]
0x18000fd31  mov     rdi, rdx
0x18000fd34  mov     rcx, rbx; pvarg
0x18000fd37  call    cs:__imp_VariantClear
0x18000fd3d  mov     rdx, rdi; pvargSrc
0x18000fd40  mov     rcx, rbx; pvargDest
0x18000fd43  call    cs:__imp_VariantCopy
0x18000fd49  mov     rbx, [rsp+28h+arg_0]
0x18000fd4e  add     rsp, 20h
0x18000fd52  pop     rdi
0x18000fd53  retn
```
