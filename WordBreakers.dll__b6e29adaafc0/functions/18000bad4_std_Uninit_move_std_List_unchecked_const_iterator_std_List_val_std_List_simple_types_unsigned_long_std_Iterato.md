# _std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____::_1_::catch$0

- ea: `0x18000bad4`
- end: `0x18000baeb`
- name: `_std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000278c`

## pseudocode

```c
void __noreturn std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_long____std::_Iterator_base0____::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x18000bad4  mov     [rsp+arg_8], rdx
0x18000bad9  push    rbp
0x18000bada  sub     rsp, 20h
0x18000bade  mov     rbp, rdx
0x18000bae1  xor     edx, edx; pThrowInfo
0x18000bae3  xor     ecx, ecx; pExceptionObject
0x18000bae5  call    _CxxThrowException_0
```
