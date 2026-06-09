# _TaskHelper::SaveLogonTriggerChange_::_1_::dtor$1

- ea: `0x140018f64`
- end: `0x140018f70`
- name: `_TaskHelper::SaveLogonTriggerChange_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall TaskHelper::SaveLogonTriggerChange_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 376));
}

```

## disassembly

```asm
0x140018f64  lea     rcx, [rdx+178h]
0x140018f6b  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
