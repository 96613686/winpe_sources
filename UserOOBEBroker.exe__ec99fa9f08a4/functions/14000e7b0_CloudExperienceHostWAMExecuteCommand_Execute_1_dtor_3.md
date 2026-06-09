# _CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor$3

- ea: `0x14000e7b0`
- end: `0x14000e7bc`
- name: `_CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007ce8`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostWAMExecuteCommand::Execute_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x14000e7b0  lea     rcx, [rdx+30h]
0x14000e7b7  jmp     ??1?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>(void)
```
