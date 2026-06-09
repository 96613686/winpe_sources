# std::_Uninit_copy<std::_Vector_const_iterator<uint,std::allocator<uint>>,uint *,std::allocator<uint>>(std::_Vector_const_iterator<uint,std::allocator<uint>>,std::_Vector_const_iterator<uint,std::allocator<uint>>,uint *,std::allocator<uint> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)

- ea: `0x18001be58`
- end: `0x18001be86`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@IV?$allocator@I@std@@@std@@PEAIV?$allocator@I@2@@std@@YAPEAIV?$_Vector_const_iterator@IV?$allocator@I@std@@@0@0PEAIAEAV?$allocator@I@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b4e8`

## callees

- `0x18001be58`

## pseudocode

```c
_DWORD *__fastcall std::_Uninit_copy<std::_Vector_const_iterator<unsigned int>,unsigned int *,std::allocator<unsigned int>>(
        _DWORD *a1,
        _DWORD *a2,
        _DWORD *a3)
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
0x18001be58  sub     rsp, 38h
0x18001be5c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001be65  jmp     short loc_18001BE79
0x18001be67  test    r8, r8
0x18001be6a  jz      short loc_18001BE71
0x18001be6c  mov     eax, [rcx]
0x18001be6e  mov     [r8], eax
0x18001be71  add     r8, 4
0x18001be75  add     rcx, 4
0x18001be79  cmp     rcx, rdx
0x18001be7c  jnz     short loc_18001BE67
0x18001be7e  mov     rax, r8
0x18001be81  add     rsp, 38h
0x18001be85  retn
```
