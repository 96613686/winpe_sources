# std::_Func_impl_std::_Callable_obj__lambda_15d541137d4be77a5b277dd450570d22__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x180021db0`
- end: `0x180021def`
- name: `std::_Func_impl_std::_Callable_obj__lambda_15d541137d4be77a5b277dd450570d22__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180021db0`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_15d541137d4be77a5b277dd450570d22__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = off_1800316B0;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x180021db0  push    rbx
0x180021db2  sub     rsp, 20h
0x180021db6  mov     rbx, rcx
0x180021db9  test    rdx, rdx
0x180021dbc  jnz     short loc_180021DCE
0x180021dbe  lea     ecx, [rdx+18h]; Size
0x180021dc1  call    ??2@YAPEAX_K@Z
0x180021dc6  mov     rdx, rax
0x180021dc9  test    rax, rax
0x180021dcc  jz      short loc_180021DE9
0x180021dce  lea     rax, off_1800316B0
0x180021dd5  mov     [rdx], rax
0x180021dd8  mov     rax, [rbx+8]
0x180021ddc  mov     [rdx+8], rax
0x180021de0  mov     rax, rdx
0x180021de3  add     rsp, 20h
0x180021de7  pop     rbx
0x180021de8  retn
0x180021de9  call    ?_Xbad_alloc@std@@YAXXZ
```
