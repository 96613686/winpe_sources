# _UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$1

- ea: `0x140011b7b`
- end: `0x140011b87`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a04c`

## pseudocode

```c
__int64 __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>((__int64 *)(a2 + 120));
}

```

## disassembly

```asm
0x140011b7b  lea     rcx, [rdx+78h]
0x140011b82  jmp     ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
```
