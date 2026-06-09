# CIISProperty::put_Default(tagVARIANT)

- ea: `0x18000c800`
- end: `0x18000c85d`
- name: `?put_Default@CIISProperty@@UEAAJUtagVARIANT@@@Z`
- size: `93`
- prototype: `int(CIISProperty *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c800`
- `0x18001b5ac`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000c83f`
- `OLEAUT32!__imp_VariantClear` at `0x18000c83f`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c84c`
- `OLEAUT32!__imp_VariantCopy` at `0x18000c84c`

## pseudocode

```c
HRESULT __fastcall CIISProperty::put_Default(CIISProperty *this, struct tagVARIANT *a2)
{
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  if ( (int)IIsSchema::PropNameWToId(*((IIsSchema **)this + 16), *((const unsigned __int16 **)this + 19), &v5) >= 0 )
    return -2147467259;
  VariantClear((VARIANTARG *)((char *)this + 64));
  return VariantCopy((VARIANTARG *)((char *)this + 64), a2);
}

```

## disassembly

```asm
0x18000c800  mov     [rsp+arg_8], rbx
0x18000c805  push    rdi
0x18000c806  sub     rsp, 20h
0x18000c80a  mov     rdi, rdx
0x18000c80d  mov     [rsp+28h+arg_0], 0
0x18000c815  mov     rdx, [rcx+98h]; unsigned __int16 *
0x18000c81c  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18000c821  mov     rbx, rcx
0x18000c824  mov     rcx, [rcx+80h]; this
0x18000c82b  call    ?PropNameWToId@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::PropNameWToId(ushort const *,ulong *)
0x18000c830  test    eax, eax
0x18000c832  js      short loc_18000C83B
0x18000c834  mov     eax, 80004005h
0x18000c839  jmp     short loc_18000C852
0x18000c83b  lea     rcx, [rbx+40h]; pvarg
0x18000c83f  call    cs:__imp_VariantClear
0x18000c845  mov     rdx, rdi; pvargSrc
0x18000c848  lea     rcx, [rbx+40h]; pvargDest
0x18000c84c  call    cs:__imp_VariantCopy
0x18000c852  mov     rbx, [rsp+28h+arg_8]
0x18000c857  add     rsp, 20h
0x18000c85b  pop     rdi
0x18000c85c  retn
```
