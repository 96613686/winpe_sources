# std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x18000c670`
- end: `0x18000c6af`
- name: `std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `63`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x18000c670`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = &std::_Func_impl<std::_Callable_obj<_lambda_312e65f4f93bbe839a71a78ad9276a5e_,0>,std::allocator<std::_Func_class<void,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x18000c670  push    rbx
0x18000c672  sub     rsp, 20h
0x18000c676  mov     rbx, rcx
0x18000c679  test    rdx, rdx
0x18000c67c  jnz     short loc_18000C68E
0x18000c67e  lea     ecx, [rdx+18h]; Size
0x18000c681  call    ??2@YAPEAX_K@Z
0x18000c686  mov     rdx, rax
0x18000c689  test    rax, rax
0x18000c68c  jz      short loc_18000C6A9
0x18000c68e  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_312e65f4f93bbe839a71a78ad9276a5e_@@$0A@@std@@V?$allocator@V?$_Func_class@XKU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@XKU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@
0x18000c695  mov     [rdx], rax
0x18000c698  mov     rax, [rbx+8]
0x18000c69c  mov     [rdx+8], rax
0x18000c6a0  mov     rax, rdx
0x18000c6a3  add     rsp, 20h
0x18000c6a7  pop     rbx
0x18000c6a8  retn
0x18000c6a9  call    ?_Xbad_alloc@std@@YAXXZ
```
