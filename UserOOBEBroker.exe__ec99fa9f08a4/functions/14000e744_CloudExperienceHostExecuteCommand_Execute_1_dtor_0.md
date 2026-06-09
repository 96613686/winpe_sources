# _CloudExperienceHostExecuteCommand::Execute_::_1_::dtor$0

- ea: `0x14000e744`
- end: `0x14000e750`
- name: `_CloudExperienceHostExecuteCommand::Execute_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007ce8`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostExecuteCommand::Execute_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x14000e744  lea     rcx, [rdx+50h]
0x14000e74b  jmp     ??1?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>(void)
```
