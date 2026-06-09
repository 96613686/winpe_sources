# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14001eb70`
- end: `0x14001eb84`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001e944`
- `0x14001ec10`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  wil_details_UpdateFeatureConfiguredStates();
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x14001eb70  sub     rsp, 28h
0x14001eb74  call    wil_details_UpdateFeatureConfiguredStates
0x14001eb79  call    wil_details_EvaluateFeatureDependencies
0x14001eb7e  add     rsp, 28h
0x14001eb82  retn
```
