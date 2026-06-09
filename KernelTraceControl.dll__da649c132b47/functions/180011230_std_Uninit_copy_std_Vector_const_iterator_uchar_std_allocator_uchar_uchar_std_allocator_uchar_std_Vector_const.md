# std::_Uninit_copy<std::_Vector_const_iterator<uchar,std::allocator<uchar>>,uchar *,std::allocator<uchar>>(std::_Vector_const_iterator<uchar,std::allocator<uchar>>,std::_Vector_const_iterator<uchar,std::allocator<uchar>>,uchar *,std::allocator<uchar> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x180011230`
- end: `0x18001125c`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@EV?$allocator@E@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_const_iterator@EV?$allocator@E@std@@@0@0PEAEAEAV?$allocator@E@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d62c`

## callees

- `0x180011230`

## pseudocode

```c
_BYTE *__fastcall std::_Uninit_copy<std::_Vector_const_iterator<unsigned char>,unsigned char *,std::allocator<unsigned char>>(
        _BYTE *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  try
  {
    while ( a1 != a2 )
    {
      if ( a3 )
        *a3 = *a1;
      ++a3;
      ++a1;
    }
  }
  catch ( ... )
  {
    throw;
  }
  return a3;
}

```

## disassembly

```asm
0x180011230  sub     rsp, 38h
0x180011234  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001123d  jmp     short loc_18001124F
0x18001123f  test    r8, r8
0x180011242  jz      short loc_180011249
0x180011244  mov     al, [rcx]
0x180011246  mov     [r8], al
0x180011249  inc     r8
0x18001124c  inc     rcx
0x18001124f  cmp     rcx, rdx
0x180011252  jnz     short loc_18001123F
0x180011254  mov     rax, r8
0x180011257  add     rsp, 38h
0x18001125b  retn
```
