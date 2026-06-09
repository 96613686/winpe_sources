# _std::_Uninit_copy_std::_String_const_iterator_std::_String_val_std::_Simple_types_unsigned_short______unsigned_short___std::allocator_unsigned_short____::_1_::catch$0

- ea: `0x14000aa7c`
- end: `0x14000aa93`
- name: `_std::_Uninit_copy_std::_String_const_iterator_std::_String_val_std::_Simple_types_unsigned_short______unsigned_short___std::allocator_unsigned_short____::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000a21a`

## pseudocode

```c
void __noreturn std::_Uninit_copy_std::_String_const_iterator_std::_String_val_std::_Simple_types_unsigned_short______unsigned_short___std::allocator_unsigned_short____::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x14000aa7c  mov     [rsp+arg_8], rdx
0x14000aa81  push    rbp
0x14000aa82  sub     rsp, 20h
0x14000aa86  mov     rbp, rdx
0x14000aa89  xor     edx, edx; pThrowInfo
0x14000aa8b  xor     ecx, ecx; pExceptionObject
0x14000aa8d  call    _CxxThrowException_0
```
