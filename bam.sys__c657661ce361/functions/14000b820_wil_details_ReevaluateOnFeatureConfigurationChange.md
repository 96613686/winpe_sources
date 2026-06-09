# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000b820`
- end: `0x14000b834`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14000b594`
- `0x14000b8c0`

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
0x14000b820  sub     rsp, 28h
0x14000b824  call    wil_details_UpdateFeatureConfiguredStates
0x14000b829  call    wil_details_EvaluateFeatureDependencies
0x14000b82e  add     rsp, 28h
0x14000b832  retn
```
