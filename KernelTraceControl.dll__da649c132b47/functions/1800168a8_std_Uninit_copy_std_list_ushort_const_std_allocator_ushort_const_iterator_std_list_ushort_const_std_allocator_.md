# std::_Uninit_copy<std::list<ushort const *,std::allocator<ushort const *>>::iterator *,std::list<ushort const *,std::allocator<ushort const *>>::iterator *,std::allocator<std::list<ushort const *,std::allocator<ushort const *>>::iterator>>(std::list<ushort const *,std::allocator<ushort const *>>::iterator *,std::list<ushort const *,std::allocator<ushort const *>>::iterator *,std::list<ushort const *,std::allocator<ushort const *>>::iterator *,std::allocator<std::list<ushort const *,std::allocator<ushort const *>>::iterator> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x1800168a8`
- end: `0x1800168f8`
- name: `??$_Uninit_copy@PEAViterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@PEAV123@V?$allocator@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@@3@@std@@YAPEAViterator@?$list@PEBGV?$allocator@PEBG@std@@@0@PEAV120@00AEAV?$allocator@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016418`

## callees

- `0x1800168a8`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_copy<std::list<unsigned short const *>::iterator *,std::list<unsigned short const *>::iterator *,std::allocator<std::list<unsigned short const *>::iterator>>(
        unsigned __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // r10
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // rcx

  try
  {
    v3 = 0;
    v4 = (a2 - a1 + 7) >> 3;
    if ( a1 > a2 )
      v4 = 0;
    if ( v4 )
    {
      v5 = a1 - (_QWORD)a3;
      do
      {
        if ( a3 )
          *a3 = *(_QWORD *)((char *)a3 + v5);
        ++a3;
        ++v3;
      }
      while ( v3 != v4 );
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
0x1800168a8  sub     rsp, 38h
0x1800168ac  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800168b5  xor     r11d, r11d
0x1800168b8  mov     r10d, r11d
0x1800168bb  mov     r9, rdx
0x1800168be  sub     r9, rcx
0x1800168c1  add     r9, 7
0x1800168c5  shr     r9, 3
0x1800168c9  cmp     rcx, rdx
0x1800168cc  cmova   r9, r11
0x1800168d0  test    r9, r9
0x1800168d3  jz      short loc_1800168F0
0x1800168d5  sub     rcx, r8
0x1800168d8  test    r8, r8
0x1800168db  jz      short loc_1800168E4
0x1800168dd  mov     rax, [rcx+r8]
0x1800168e1  mov     [r8], rax
0x1800168e4  add     r8, 8
0x1800168e8  inc     r10
0x1800168eb  cmp     r10, r9
0x1800168ee  jnz     short loc_1800168D8
0x1800168f0  mov     rax, r8
0x1800168f3  add     rsp, 38h
0x1800168f7  retn
```
