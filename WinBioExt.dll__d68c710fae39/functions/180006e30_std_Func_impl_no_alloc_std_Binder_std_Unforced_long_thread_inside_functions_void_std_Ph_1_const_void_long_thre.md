# std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Delete_this(bool)

- ea: `0x180006e30`
- end: `0x180006e47`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@EEAAX_N@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800019e0`
- `0x180006e30`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180006e30  sub     rsp, 28h
0x180006e34  test    dl, dl
0x180006e36  jz      short loc_180006E42
0x180006e38  mov     edx, 20h ; ' '; unsigned __int64
0x180006e3d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006e42  add     rsp, 28h
0x180006e46  retn
```
