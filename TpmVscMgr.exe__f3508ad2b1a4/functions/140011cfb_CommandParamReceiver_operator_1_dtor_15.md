# _CommandParamReceiver::operator()_::_1_::dtor$15

- ea: `0x140011cfb`
- end: `0x140011d07`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$15`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400082e4`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>((__int64 *)(a2 + 200));
}

```

## disassembly

```asm
0x140011cfb  lea     rcx, [rdx+0C8h]
0x140011d02  jmp     ??1?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(void)
```
