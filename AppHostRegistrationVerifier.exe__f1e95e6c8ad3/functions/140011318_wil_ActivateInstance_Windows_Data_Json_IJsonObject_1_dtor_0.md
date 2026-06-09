# _wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor$0

- ea: `0x140011318`
- end: `0x140011324`
- name: `_wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a04c`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>((__int64 *)(a2 + 32));
}

```

## disassembly

```asm
0x140011318  lea     rcx, [rdx+20h]
0x14001131f  jmp     ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
```
