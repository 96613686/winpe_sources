# std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::allocator<uchar>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::_Wrap_alloc<std::allocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18001d12c`
- end: `0x18001d14a`
- name: `??$_Uninit_copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0PEAEAEAU?$_Wrap_alloc@V?$allocator@E@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `30`
- prototype: `_BYTE *__fastcall(_BYTE *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cfb4`

## callees

- `0x18001d12c`

## pseudocode

```c
_BYTE *__fastcall std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,unsigned char *,std::allocator<unsigned char>>(
        _BYTE *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x18001d12c  sub     rsp, 28h
0x18001d130  cmp     rcx, rdx
0x18001d133  jz      short loc_18001D142
0x18001d135  mov     al, [rcx]
0x18001d137  mov     [r8], al
0x18001d13a  inc     r8
0x18001d13d  inc     rcx
0x18001d140  jmp     short loc_18001D130
0x18001d142  mov     rax, r8
0x18001d145  add     rsp, 28h
0x18001d149  retn
```
