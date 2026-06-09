# _GetJsonFromUrl_::_1_::dtor$4

- ea: `0x14001196f`
- end: `0x14001197b`
- name: `_GetJsonFromUrl_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a04c`

## pseudocode

```c
__int64 __fastcall GetJsonFromUrl_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x14001196f  lea     rcx, [rdx+70h]
0x140011976  jmp     ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
```
