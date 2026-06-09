# std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x1400061e0`
- end: `0x140006221`
- name: `std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const_&_Command_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `65`
- prototype: `char *__fastcall(__int64, char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001864`
- `0x1400061e0`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400061fe`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400061fe`

## pseudocode

```c
char *__fastcall std::_Func_impl_std::_Callable_obj__lambda_20453a175cf9b24fd14dd35e8a5747be__0__std::allocator_std::_Func_class_void_CommandSet_const___Command_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_CommandSet_const___Command_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        char *a2)
{
  char *result; // rax

  if ( !a2 )
  {
    a2 = (char *)operator new(0x20u);
    if ( !a2 )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
  }
  *(_QWORD *)a2 = off_14000C0E0;
  result = a2;
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x1400061e0  push    rbx
0x1400061e2  sub     rsp, 20h
0x1400061e6  mov     rbx, rcx
0x1400061e9  test    rdx, rdx
0x1400061ec  jnz     short loc_140006205
0x1400061ee  lea     ecx, [rdx+20h]; Size
0x1400061f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400061f6  mov     rdx, rax
0x1400061f9  test    rax, rax
0x1400061fc  jnz     short loc_140006205
0x1400061fe  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140006204  int     3; Trap to Debugger
0x140006205  lea     rax, off_14000C0E0
0x14000620c  mov     [rdx], rax
0x14000620f  mov     rax, rdx
0x140006212  movups  xmm0, xmmword ptr [rbx+8]
0x140006216  movdqu  xmmword ptr [rdx+8], xmm0
0x14000621b  add     rsp, 20h
0x14000621f  pop     rbx
0x140006220  retn
```
