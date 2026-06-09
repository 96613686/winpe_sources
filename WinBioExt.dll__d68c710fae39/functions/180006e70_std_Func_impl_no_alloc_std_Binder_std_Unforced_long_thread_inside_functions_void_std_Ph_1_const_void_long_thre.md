# std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Get(void)

- ea: `0x180006e70`
- end: `0x180006e75`
- name: `?_Get@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@EEBAPEBXXZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Get(
        __int64 a1)
{
  return a1 + 8;
}

```

## disassembly

```asm
0x180006e70  lea     rax, [rcx+8]
0x180006e74  retn
```
