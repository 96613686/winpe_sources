# std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this

- ea: `0x180021fa0`
- end: `0x180021fd5`
- name: `std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180021fa0`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180021fc4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021fc4`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_4cfdf45b535fb29c09cbb19e4710f131__0__std::allocator_std::_Func_class_void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this(
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
0x180021fa0  mov     [rsp+arg_0], rbx
0x180021fa5  push    rdi
0x180021fa6  sub     rsp, 20h
0x180021faa  mov     rax, [rcx]
0x180021fad  mov     bl, dl
0x180021faf  xor     edx, edx
0x180021fb1  mov     rdi, rcx
0x180021fb4  mov     rax, [rax+28h]
0x180021fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fbd  test    bl, bl
0x180021fbf  jz      short loc_180021FCA
0x180021fc1  mov     rcx, rdi
0x180021fc4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021fca  mov     rbx, [rsp+28h+arg_0]
0x180021fcf  add     rsp, 20h
0x180021fd3  pop     rdi
0x180021fd4  retn
```
