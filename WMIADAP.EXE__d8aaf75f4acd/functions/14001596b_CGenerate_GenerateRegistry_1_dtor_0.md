# _CGenerate::GenerateRegistry_::_1_::dtor$0

- ea: `0x14001596b`
- end: `0x140015977`
- name: `_CGenerate::GenerateRegistry_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000af5c`

## pseudocode

```c
__int64 __fastcall CGenerate::GenerateRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::~CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>(a2 + 96);
}

```

## disassembly

```asm
0x14001596b  lea     rcx, [rdx+60h]
0x140015972  jmp     ??1?$CPerformanceStructureManipulator@U_WMI_PERFORMANCE@@U1@U_WMI_PERF_NAMESPACE@@@@QEAA@XZ; CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::~CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>(void)
```
