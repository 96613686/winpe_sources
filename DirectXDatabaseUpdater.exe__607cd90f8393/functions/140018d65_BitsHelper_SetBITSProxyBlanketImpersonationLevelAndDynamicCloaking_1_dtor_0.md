# _BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking_::_1_::dtor$0

- ea: `0x140018d65`
- end: `0x140018d71`
- name: `_BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x140018d65  lea     rcx, [rdx+60h]
0x140018d6c  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
