# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14002a3f0`
- end: `0x14002a404`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002a174`
- `0x14002a490`

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
0x14002a3f0  sub     rsp, 28h
0x14002a3f4  call    wil_details_UpdateFeatureConfiguredStates
0x14002a3f9  call    wil_details_EvaluateFeatureDependencies
0x14002a3fe  add     rsp, 28h
0x14002a402  retn
```
