# CTSimpleArray<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR,4294967294,CTPolicyCoTaskMem<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>,CSimpleArrayStandardCompareHelper<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>,CSimpleArrayStandardMergeHelper<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>>::RemoveAll(void)

- ea: `0x180026d44`
- end: `0x180026d81`
- name: `?RemoveAll@?$CTSimpleArray@UDURATION_VALUE_PAIR@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UDURATION_VALUE_PAIR@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@UDURATION_VALUE_PAIR@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@UDURATION_VALUE_PAIR@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@@@@@QEAAXXZ`
- size: `61`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026754`
- `0x180026760`
- `0x180026f8c`
- `0x1800271a0`
- `0x180027690`
- `0x1800277f4`
- `0x180027d40`
- `0x1800376c0`
- `0x180037b98`

## callees

- `0x180026d44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026d59`

## pseudocode

```c
void __fastcall CTSimpleArray<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR,4294967294,CTPolicyCoTaskMem<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>,CSimpleArrayStandardCompareHelper<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>,CSimpleArrayStandardMergeHelper<SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR>>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180026d44  mov     [rsp+arg_0], rbx
0x180026d49  push    rdi
0x180026d4a  sub     rsp, 20h
0x180026d4e  mov     rbx, rcx
0x180026d51  mov     rcx, [rcx]; pv
0x180026d54  test    rcx, rcx
0x180026d57  jz      short loc_180026D66
0x180026d59  call    cs:__imp_CoTaskMemFree
0x180026d5f  mov     qword ptr [rbx], 0
0x180026d66  mov     qword ptr [rbx+8], 0
0x180026d6e  mov     qword ptr [rbx+18h], 0
0x180026d76  mov     rbx, [rsp+28h+arg_0]
0x180026d7b  add     rsp, 20h
0x180026d7f  pop     rdi
0x180026d80  retn
```
