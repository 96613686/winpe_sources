# std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Target_type(void)

- ea: `0x180006e80`
- end: `0x180006e88`
- name: `?_Target_type@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@EEBAAEBVtype_info@@XZ`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
void ***std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Target_type()
{
  return &std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &> `RTTI Type Descriptor';
}

```

## disassembly

```asm
0x180006e80  lea     rax, ??_R0?AV?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@@8; std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &> `RTTI Type Descriptor'
0x180006e87  retn
```
