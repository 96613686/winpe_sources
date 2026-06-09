# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140025b50`
- end: `0x140025b64`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400258cc`
- `0x140025bf0`

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
0x140025b50  sub     rsp, 28h
0x140025b54  call    wil_details_UpdateFeatureConfiguredStates
0x140025b59  call    wil_details_EvaluateFeatureDependencies
0x140025b5e  add     rsp, 28h
0x140025b62  retn
```
