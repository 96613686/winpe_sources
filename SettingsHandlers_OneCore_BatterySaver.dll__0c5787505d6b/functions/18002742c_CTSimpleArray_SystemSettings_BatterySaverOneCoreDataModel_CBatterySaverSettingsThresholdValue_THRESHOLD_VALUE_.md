# CTSimpleArray<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR,4294967294,CTPolicyCoTaskMem<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>,CSimpleArrayStandardCompareHelper<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>,CSimpleArrayStandardMergeHelper<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>>::RemoveAll(void)

- ea: `0x18002742c`
- end: `0x180027469`
- name: `?RemoveAll@?$CTSimpleArray@UTHRESHOLD_VALUE_PAIR@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UTHRESHOLD_VALUE_PAIR@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@UTHRESHOLD_VALUE_PAIR@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@UTHRESHOLD_VALUE_PAIR@CBatterySaverSettingsThresholdValue@BatterySaverOneCoreDataModel@SystemSettings@@@@@@QEAAXXZ`
- size: `61`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019e44`
- `0x18001aac8`
- `0x18002b054`

## callees

- `0x18002742c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027441`

## pseudocode

```c
void __fastcall CTSimpleArray<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR,4294967294,CTPolicyCoTaskMem<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>,CSimpleArrayStandardCompareHelper<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>,CSimpleArrayStandardMergeHelper<SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsThresholdValue::THRESHOLD_VALUE_PAIR>>::RemoveAll(
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
0x18002742c  mov     [rsp+arg_0], rbx
0x180027431  push    rdi
0x180027432  sub     rsp, 20h
0x180027436  mov     rbx, rcx
0x180027439  mov     rcx, [rcx]; pv
0x18002743c  test    rcx, rcx
0x18002743f  jz      short loc_18002744E
0x180027441  call    cs:__imp_CoTaskMemFree
0x180027447  mov     qword ptr [rbx], 0
0x18002744e  mov     qword ptr [rbx+8], 0
0x180027456  mov     qword ptr [rbx+18h], 0
0x18002745e  mov     rbx, [rsp+28h+arg_0]
0x180027463  add     rsp, 20h
0x180027467  pop     rdi
0x180027468  retn
```
