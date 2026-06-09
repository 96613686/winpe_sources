# std::_Func_impl_no_alloc<_lambda_758cc192c2b6814ec8090745d2a6079d_,void,wchar_t const *,wchar_t const *,long>::_Delete_this(bool)

- ea: `0x180011500`
- end: `0x18001150f`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_758cc192c2b6814ec8090745d2a6079d_@@XPEB_WPEB_WJ@std@@EEAAX_N@Z`
- size: `15`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180011500`
- `0x180018238`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc<_lambda_758cc192c2b6814ec8090745d2a6079d_,void,wchar_t const *,wchar_t const *,long>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180011500  test    dl, dl
0x180011502  jz      short locret_18001150E
0x180011504  mov     edx, 10h; unsigned __int64
0x180011509  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001150e  retn
```
