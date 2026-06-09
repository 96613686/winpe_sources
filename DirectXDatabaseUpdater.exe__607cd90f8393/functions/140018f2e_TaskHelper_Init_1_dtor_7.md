# _TaskHelper::Init_::_1_::dtor$7

- ea: `0x140018f2e`
- end: `0x140018f3a`
- name: `_TaskHelper::Init_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall TaskHelper::Init_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 448));
}

```

## disassembly

```asm
0x140018f2e  lea     rcx, [rdx+1C0h]
0x140018f35  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
