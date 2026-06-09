# std::_Func_impl_std::_Callable_obj__lambda_331041fad977e622cbb14e349918d272__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x180021e00`
- end: `0x180021e3f`
- name: `std::_Func_impl_std::_Callable_obj__lambda_331041fad977e622cbb14e349918d272__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180021e00`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_331041fad977e622cbb14e349918d272__0__std::allocator_std::_Func_class_long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____long_void_const___int_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = off_1800316E8;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x180021e00  push    rbx
0x180021e02  sub     rsp, 20h
0x180021e06  mov     rbx, rcx
0x180021e09  test    rdx, rdx
0x180021e0c  jnz     short loc_180021E1E
0x180021e0e  lea     ecx, [rdx+18h]; Size
0x180021e11  call    ??2@YAPEAX_K@Z
0x180021e16  mov     rdx, rax
0x180021e19  test    rax, rax
0x180021e1c  jz      short loc_180021E39
0x180021e1e  lea     rax, off_1800316E8
0x180021e25  mov     [rdx], rax
0x180021e28  mov     rax, [rbx+8]
0x180021e2c  mov     [rdx+8], rax
0x180021e30  mov     rax, rdx
0x180021e33  add     rsp, 20h
0x180021e37  pop     rbx
0x180021e38  retn
0x180021e39  call    ?_Xbad_alloc@std@@YAXXZ
```
