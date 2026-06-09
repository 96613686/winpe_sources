# std::_Func_impl_std::_Callable_obj__lambda_3a0faf93a165a2ec8b1195d576202f5d__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x180021e50`
- end: `0x180021e8f`
- name: `std::_Func_impl_std::_Callable_obj__lambda_3a0faf93a165a2ec8b1195d576202f5d__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180021e50`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_3a0faf93a165a2ec8b1195d576202f5d__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = off_180031790;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x180021e50  push    rbx
0x180021e52  sub     rsp, 20h
0x180021e56  mov     rbx, rcx
0x180021e59  test    rdx, rdx
0x180021e5c  jnz     short loc_180021E6E
0x180021e5e  lea     ecx, [rdx+18h]; Size
0x180021e61  call    ??2@YAPEAX_K@Z
0x180021e66  mov     rdx, rax
0x180021e69  test    rax, rax
0x180021e6c  jz      short loc_180021E89
0x180021e6e  lea     rax, off_180031790
0x180021e75  mov     [rdx], rax
0x180021e78  mov     rax, [rbx+8]
0x180021e7c  mov     [rdx+8], rax
0x180021e80  mov     rax, rdx
0x180021e83  add     rsp, 20h
0x180021e87  pop     rbx
0x180021e88  retn
0x180021e89  call    ?_Xbad_alloc@std@@YAXXZ
```
