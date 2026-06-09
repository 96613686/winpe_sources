# NaturalLanguage6::KeyValuePair::put_Value(tagVARIANT)

- ea: `0x18004cc90`
- end: `0x18004ccc3`
- name: `?put_Value@KeyValuePair@NaturalLanguage6@@UEAAJUtagVARIANT@@@Z`
- size: `51`
- prototype: `__int64 __fastcall(NaturalLanguage6::KeyValuePair *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019a50`
- `0x18004cc90`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18004cca1`
- `OLEAUT32!__imp_VariantCopy` at `0x18004cca1`

## pseudocode

```c
__int64 __fastcall NaturalLanguage6::KeyValuePair::put_Value(VARIANTARG *this, struct tagVARIANT *a2)
{
  HRESULT v2; // eax
  __int64 result; // rax
  _com_error *v4; // rbx
  _com_error *v6; // [rsp+28h] [rbp-10h] BYREF
  void *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    v2 = VariantCopy(this + 1, a2);
    _com_util::CheckError(v2);
    result = 0;
  }
  catch ( _com_error *v6 )
  {
    v4 = v6;
    ImxTraceCatch(1, *((unsigned int *)v6 + 2), retaddr);
    return *((unsigned int *)v4 + 2);
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147549183LL, retaddr);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004cc90  sub     rsp, 38h
0x18004cc94  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004cc9d  add     rcx, 18h; pvargDest
0x18004cca1  call    cs:__imp_VariantCopy
0x18004cca7  mov     ecx, eax; int
0x18004cca9  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x18004ccae  xor     eax, eax
0x18004ccb0  jmp     short loc_18004CCBD
0x18004ccb2  mov     eax, [rsp+38h+arg_10]
0x18004ccb6  jmp     short loc_18004CCBD
0x18004ccb8  mov     eax, 8000FFFFh
0x18004ccbd  add     rsp, 38h
0x18004ccc1  retn
```
