# _CommandParamReceiver::operator()_::_1_::dtor$1_0

- ea: `0x140011d43`
- end: `0x140011d4f`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$1_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400082e4`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_1_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140011d43  lea     rcx, [rdx+30h]
0x140011d4a  jmp     ??1?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVirtualSmartCardManager,wil::err_exception_policy>(void)
```
