# std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x18000a660`
- end: `0x18000a69f`
- name: `std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x18000a660`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = off_18000FCC0;
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x18000a660  push    rbx
0x18000a662  sub     rsp, 20h
0x18000a666  mov     rbx, rcx
0x18000a669  test    rdx, rdx
0x18000a66c  jnz     short loc_18000A67E
0x18000a66e  lea     ecx, [rdx+18h]; Size
0x18000a671  call    ??2@YAPEAX_K@Z
0x18000a676  mov     rdx, rax
0x18000a679  test    rax, rax
0x18000a67c  jz      short loc_18000A699
0x18000a67e  lea     rax, off_18000FCC0
0x18000a685  mov     [rdx], rax
0x18000a688  mov     rax, [rbx+8]
0x18000a68c  mov     [rdx+8], rax
0x18000a690  mov     rax, rdx
0x18000a693  add     rsp, 20h
0x18000a697  pop     rbx
0x18000a698  retn
0x18000a699  call    ?_Xbad_alloc@std@@YAXXZ
```
