# std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::_Delete_this(bool)

- ea: `0x180011b70`
- end: `0x180011b87`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@EEAAX_N@Z`
- size: `23`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x180011b70`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180011b70  sub     rsp, 28h
0x180011b74  test    dl, dl
0x180011b76  jz      short loc_180011B82
0x180011b78  mov     edx, 10h; unsigned __int64
0x180011b7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011b82  add     rsp, 28h
0x180011b86  retn
```
