# _CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$2

- ea: `0x180009ba5`
- end: `0x180009bb1`
- name: `_CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800088d0`

## pseudocode

```c
__int64 (__fastcall *__fastcall CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor_2(
        __int64 a1,
        __int64 a2))(int, int, int, int, __int64)
{
  return CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>((_BYTE *)(a2 + 32));
}

```

## disassembly

```asm
0x180009ba5  lea     rcx, [rdx+20h]
0x180009bac  jmp     ??1?$ScopeGuardGlobalFuncImpl@V_lambda_2b09a7e4faa30095a7d023915a4f2697_@@@CommonUtil@@QEAA@XZ; CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(void)
```
