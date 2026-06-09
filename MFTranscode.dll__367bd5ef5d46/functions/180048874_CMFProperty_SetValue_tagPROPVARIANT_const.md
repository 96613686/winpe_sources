# CMFProperty::SetValue(tagPROPVARIANT const &)

- ea: `0x180048874`
- end: `0x1800488a9`
- name: `?SetValue@CMFProperty@@AEAAJAEBUtagPROPVARIANT@@@Z`
- size: `53`
- prototype: `int(CMFProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048480`

## callees

- `0x180048874`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048888`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180048888`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048898`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048898`

## pseudocode

```c
int __fastcall CMFProperty::SetValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  PROPVARIANT *v2; // rbx
  int result; // eax

  v2 = this + 4;
  result = PropVariantClear(this + 4);
  if ( result >= 0 )
    return PropVariantCopy(v2, a2);
  return result;
}

```

## disassembly

```asm
0x180048874  mov     [rsp+arg_0], rbx
0x180048879  push    rdi
0x18004887a  sub     rsp, 20h
0x18004887e  lea     rbx, [rcx+60h]
0x180048882  mov     rdi, rdx
0x180048885  mov     rcx, rbx; pvar
0x180048888  call    cs:__imp_PropVariantClear
0x18004888e  test    eax, eax
0x180048890  js      short loc_18004889E
0x180048892  mov     rdx, rdi; pvarSrc
0x180048895  mov     rcx, rbx; pvarDest
0x180048898  call    cs:__imp_PropVariantCopy
0x18004889e  mov     rbx, [rsp+28h+arg_0]
0x1800488a3  add     rsp, 20h
0x1800488a7  pop     rdi
0x1800488a8  retn
```
