# std::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>(std::_One_then_variadic_args_t,std::allocator<uchar> const &)

- ea: `0x14000dc6c`
- end: `0x14000dc7d`
- name: `??$?0AEBV?$allocator@E@std@@$$V@?$_Compressed_pair@V?$allocator@E@std@@V?$_Vector_val@U?$_Simple_types@E@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBV?$allocator@E@1@@Z`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000e324`
- `0x14000e7e4`

## pseudocode

```c
_QWORD *__fastcall std::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x14000dc6c  xor     eax, eax
0x14000dc6e  mov     [rcx], rax
0x14000dc71  mov     [rcx+8], rax
0x14000dc75  mov     [rcx+10h], rax
0x14000dc79  mov     rax, rcx
0x14000dc7c  retn
```
