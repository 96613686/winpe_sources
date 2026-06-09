# __dynamic_initializer_for__gs_missCache___::_1_::dtor$2

- ea: `0x18000bb03`
- end: `0x18000bb13`
- name: `__dynamic_initializer_for__gs_missCache___::_1_::dtor$2`
- size: `16`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003cd8`

## pseudocode

```c
__int64 _dynamic_initializer_for__gs_missCache___::_1_::dtor_2()
{
  return std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>>>(&xmmword_180012C20);
}

```

## disassembly

```asm
0x18000bb03  lea     rcx, qword_180012C10
0x18000bb0a  add     rcx, 10h
0x18000bb0e  jmp     ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>>(void)
```
