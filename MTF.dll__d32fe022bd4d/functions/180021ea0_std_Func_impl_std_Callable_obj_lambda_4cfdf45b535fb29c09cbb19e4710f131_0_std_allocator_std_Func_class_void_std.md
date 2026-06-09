# std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x180021ea0`
- end: `0x180021edf`
- name: `std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180021ea0`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = off_180031720;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x180021ea0  push    rbx
0x180021ea2  sub     rsp, 20h
0x180021ea6  mov     rbx, rcx
0x180021ea9  test    rdx, rdx
0x180021eac  jnz     short loc_180021EBE
0x180021eae  lea     ecx, [rdx+18h]; Size
0x180021eb1  call    ??2@YAPEAX_K@Z
0x180021eb6  mov     rdx, rax
0x180021eb9  test    rax, rax
0x180021ebc  jz      short loc_180021ED9
0x180021ebe  lea     rax, off_180031720
0x180021ec5  mov     [rdx], rax
0x180021ec8  mov     rax, [rbx+8]
0x180021ecc  mov     [rdx+8], rax
0x180021ed0  mov     rax, rdx
0x180021ed3  add     rsp, 20h
0x180021ed7  pop     rbx
0x180021ed8  retn
0x180021ed9  call    ?_Xbad_alloc@std@@YAXXZ
```
