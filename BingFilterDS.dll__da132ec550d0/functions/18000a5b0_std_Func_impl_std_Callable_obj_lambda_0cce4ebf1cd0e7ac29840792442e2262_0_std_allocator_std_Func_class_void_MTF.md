# std::_Func_impl_std::_Callable_obj__lambda_0cce4ebf1cd0e7ac29840792442e2262__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move

- ea: `0x18000a5b0`
- end: `0x18000a607`
- name: `std::_Func_impl_std::_Callable_obj__lambda_0cce4ebf1cd0e7ac29840792442e2262__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move`
- size: `87`
- prototype: `char *__fastcall(__int64, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x18000a5b0`

## pseudocode

```c
char *__fastcall std::_Func_impl_std::_Callable_obj__lambda_0cce4ebf1cd0e7ac29840792442e2262__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const___IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const___IMtfSuggestionListElement___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Move(
        __int64 a1,
        char *a2)
{
  char *result; // rax

  if ( !a2 )
  {
    a2 = (char *)operator new(0x50u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)a2 = off_18000FCF8;
  result = a2;
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 8);
  *(_OWORD *)(a2 + 24) = *(_OWORD *)(a1 + 24);
  *(_OWORD *)(a2 + 40) = *(_OWORD *)(a1 + 40);
  *(_OWORD *)(a2 + 56) = *(_OWORD *)(a1 + 56);
  return result;
}

```

## disassembly

```asm
0x18000a5b0  push    rbx
0x18000a5b2  sub     rsp, 20h
0x18000a5b6  mov     rbx, rcx
0x18000a5b9  test    rdx, rdx
0x18000a5bc  jnz     short loc_18000A5CE
0x18000a5be  lea     ecx, [rdx+50h]; Size
0x18000a5c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5c6  mov     rdx, rax
0x18000a5c9  test    rax, rax
0x18000a5cc  jz      short loc_18000A601
0x18000a5ce  lea     rax, off_18000FCF8
0x18000a5d5  mov     [rdx], rax
0x18000a5d8  mov     rax, rdx
0x18000a5db  movups  xmm0, xmmword ptr [rbx+8]
0x18000a5df  movups  xmmword ptr [rdx+8], xmm0
0x18000a5e3  movups  xmm1, xmmword ptr [rbx+18h]
0x18000a5e7  movups  xmmword ptr [rdx+18h], xmm1
0x18000a5eb  movups  xmm0, xmmword ptr [rbx+28h]
0x18000a5ef  movups  xmmword ptr [rdx+28h], xmm0
0x18000a5f3  movups  xmm1, xmmword ptr [rbx+38h]
0x18000a5f7  movups  xmmword ptr [rdx+38h], xmm1
0x18000a5fb  add     rsp, 20h
0x18000a5ff  pop     rbx
0x18000a600  retn
0x18000a601  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
