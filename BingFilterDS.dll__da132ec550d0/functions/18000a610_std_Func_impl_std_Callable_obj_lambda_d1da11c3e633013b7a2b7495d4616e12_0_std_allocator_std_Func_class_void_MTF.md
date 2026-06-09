# std::_Func_impl_std::_Callable_obj__lambda_d1da11c3e633013b7a2b7495d4616e12__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x18000a610`
- end: `0x18000a650`
- name: `std::_Func_impl_std::_Callable_obj__lambda_d1da11c3e633013b7a2b7495d4616e12__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `64`
- prototype: `char *__fastcall(__int64, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x18000a610`

## pseudocode

```c
char *__fastcall std::_Func_impl_std::_Callable_obj__lambda_d1da11c3e633013b7a2b7495d4616e12__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const___IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const___IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        char *a2)
{
  char *result; // rax

  if ( !a2 )
  {
    a2 = (char *)operator new(0x20u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)a2 = off_18000FC28;
  result = a2;
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000a610  push    rbx
0x18000a612  sub     rsp, 20h
0x18000a616  mov     rbx, rcx
0x18000a619  test    rdx, rdx
0x18000a61c  jnz     short loc_18000A62E
0x18000a61e  lea     ecx, [rdx+20h]; Size
0x18000a621  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a626  mov     rdx, rax
0x18000a629  test    rax, rax
0x18000a62c  jz      short loc_18000A64A
0x18000a62e  lea     rax, off_18000FC28
0x18000a635  mov     [rdx], rax
0x18000a638  mov     rax, rdx
0x18000a63b  movups  xmm0, xmmword ptr [rbx+8]
0x18000a63f  movdqu  xmmword ptr [rdx+8], xmm0
0x18000a644  add     rsp, 20h
0x18000a648  pop     rbx
0x18000a649  retn
0x18000a64a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
