# _CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor$1

- ea: `0x14000e78c`
- end: `0x14000e798`
- name: `_CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007ce8`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x14000e78c  lea     rcx, [rdx+60h]
0x14000e793  jmp     ??1?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>(void)
```
