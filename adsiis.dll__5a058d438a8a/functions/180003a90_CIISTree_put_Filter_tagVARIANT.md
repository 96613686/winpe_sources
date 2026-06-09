# CIISTree::put_Filter(tagVARIANT)

- ea: `0x180003a90`
- end: `0x180003aa3`
- name: `?put_Filter@CIISTree@@UEAAJUtagVARIANT@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(CIISTree *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180003a98`
- `OLEAUT32!__imp_VariantCopy` at `0x180003a98`

## pseudocode

```c
HRESULT __fastcall CIISTree::put_Filter(CIISTree *this, struct tagVARIANT *a2)
{
  return VariantCopy((VARIANTARG *)((char *)this + 16), a2);
}

```

## disassembly

```asm
0x180003a90  sub     rsp, 28h
0x180003a94  add     rcx, 10h; pvargDest
0x180003a98  call    cs:__imp_VariantCopy
0x180003a9e  add     rsp, 28h
0x180003aa2  retn
```
