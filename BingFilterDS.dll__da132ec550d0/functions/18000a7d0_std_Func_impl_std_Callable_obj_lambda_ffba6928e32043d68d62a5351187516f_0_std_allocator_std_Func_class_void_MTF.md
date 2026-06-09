# std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this

- ea: `0x18000a7d0`
- end: `0x18000a805`
- name: `std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const_&_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this`
- size: `53`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000a7d0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a7f4`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_ffba6928e32043d68d62a5351187516f__0__std::allocator_std::_Func_class_void__MTF_FORMER_RESULT_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void__MTF_FORMER_RESULT_const___std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18000a7d0  mov     [rsp+arg_0], rbx
0x18000a7d5  push    rdi
0x18000a7d6  sub     rsp, 20h
0x18000a7da  mov     rax, [rcx]
0x18000a7dd  mov     bl, dl
0x18000a7df  xor     edx, edx
0x18000a7e1  mov     rdi, rcx
0x18000a7e4  mov     rax, [rax+28h]
0x18000a7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7ed  test    bl, bl
0x18000a7ef  jz      short loc_18000A7FA
0x18000a7f1  mov     rcx, rdi
0x18000a7f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a7fa  mov     rbx, [rsp+28h+arg_0]
0x18000a7ff  add     rsp, 20h
0x18000a803  pop     rdi
0x18000a804  retn
```
