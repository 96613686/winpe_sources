# _IsEnterprisePolicyConfigured_::_1_::dtor$0

- ea: `0x1800148a4`
- end: `0x1800148b0`
- name: `_IsEnterprisePolicyConfigured_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005850`

## pseudocode

```c
__int64 __fastcall IsEnterprisePolicyConfigured_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)(a2 + 136));
}

```

## disassembly

```asm
0x1800148a4  lea     rcx, [rdx+88h]
0x1800148ab  jmp     ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
```
