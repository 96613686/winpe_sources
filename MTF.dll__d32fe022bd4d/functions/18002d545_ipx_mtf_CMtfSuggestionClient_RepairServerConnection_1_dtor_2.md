# _ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor$2

- ea: `0x18002d545`
- end: `0x18002d551`
- name: `_ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800143d0`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>::~com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18002d545  lea     rcx, [rdx+80h]
0x18002d54c  jmp     ??1?$com_ptr_t@UIMtfTransportServerPrivate@mtf@ipx@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>::~com_ptr_t<ipx::mtf::IMtfTransportServerPrivate,wil::err_exception_policy>(void)
```
