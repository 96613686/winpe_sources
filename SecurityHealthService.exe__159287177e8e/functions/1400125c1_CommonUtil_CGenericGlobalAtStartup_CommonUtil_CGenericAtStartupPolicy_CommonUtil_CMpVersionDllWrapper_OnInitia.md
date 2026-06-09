# _CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$2

- ea: `0x1400125c1`
- end: `0x1400125cd`
- name: `_CommonUtil::CGenericGlobalAtStartup_CommonUtil::CGenericAtStartupPolicy_CommonUtil::CMpVersionDllWrapper___::OnInitializeCallback_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64))(int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140010144`

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
0x1400125c1  lea     rcx, [rdx+20h]
0x1400125c8  jmp     ??1?$ScopeGuardGlobalFuncImpl@V_lambda_2b09a7e4faa30095a7d023915a4f2697_@@@CommonUtil@@QEAA@XZ; CommonUtil::ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>::~ScopeGuardGlobalFuncImpl<_lambda_2b09a7e4faa30095a7d023915a4f2697_>(void)
```
