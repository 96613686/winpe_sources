# std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,ushort const *,ushort const *,int *>::_Delete_this(bool)

- ea: `0x18001eec0`
- end: `0x18001eed7`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_e8565040e165d3daccfd4cbfb75449a5_@@JPEBGPEBGPEAH@std@@EEAAX_N@Z`
- size: `23`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003a34`
- `0x18001eec0`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,unsigned short const *,unsigned short const *,int *>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18001eec0  sub     rsp, 28h
0x18001eec4  test    dl, dl
0x18001eec6  jz      short loc_18001EED2
0x18001eec8  mov     edx, 10h
0x18001eecd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001eed2  add     rsp, 28h
0x18001eed6  retn
```
