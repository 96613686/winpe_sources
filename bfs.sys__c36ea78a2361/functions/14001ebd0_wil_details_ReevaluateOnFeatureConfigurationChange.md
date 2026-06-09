# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14001ebd0`
- end: `0x14001ebe4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001e944`
- `0x14001ec70`

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
0x14001ebd0  sub     rsp, 28h
0x14001ebd4  call    wil_details_UpdateFeatureConfiguredStates
0x14001ebd9  call    wil_details_EvaluateFeatureDependencies
0x14001ebde  add     rsp, 28h
0x14001ebe2  retn
```
