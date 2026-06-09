# std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Delete_this

- ea: `0x180011b90`
- end: `0x180011ba7`
- name: `std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x180011b90`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180011b90  sub     rsp, 28h
0x180011b94  test    dl, dl
0x180011b96  jz      short loc_180011BA2
0x180011b98  mov     edx, 10h; unsigned __int64
0x180011b9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ba2  add     rsp, 28h
0x180011ba6  retn
```
