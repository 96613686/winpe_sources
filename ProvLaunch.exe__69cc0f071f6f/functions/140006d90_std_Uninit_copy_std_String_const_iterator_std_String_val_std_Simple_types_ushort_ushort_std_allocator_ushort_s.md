# std::_Uninit_copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *,std::allocator<ushort>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *,std::_Wrap_alloc<std::allocator<ushort>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x140006d90`
- end: `0x140006db2`
- name: `??$_Uninit_copy@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAGV?$allocator@G@2@@std@@YAPEAGV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0PEAGAEAU?$_Wrap_alloc@V?$allocator@G@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `34`
- prototype: `_WORD *__fastcall(_WORD *, _WORD *, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006b5c`

## callees

- `0x140006d90`

## pseudocode

```c
_WORD *__fastcall std::_Uninit_copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short *,std::allocator<unsigned short>>(
        _WORD *a1,
        _WORD *a2,
        _WORD *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x140006d90  sub     rsp, 28h
0x140006d94  cmp     rcx, rdx
0x140006d97  jz      short loc_140006DAA
0x140006d99  movzx   eax, word ptr [rcx]
0x140006d9c  mov     [r8], ax
0x140006da0  add     r8, 2
0x140006da4  add     rcx, 2
0x140006da8  jmp     short loc_140006D94
0x140006daa  mov     rax, r8
0x140006dad  add     rsp, 28h
0x140006db1  retn
```
