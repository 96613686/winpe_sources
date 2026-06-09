# IPxlatPolicyMgrReadConfigurationWrapper

- ea: `0x18000b1a0`
- end: `0x18000b1d1`
- name: `IPxlatPolicyMgrReadConfigurationWrapper`
- size: `49`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000b12c`
- `0x18000b1a0`
- `0x18000dcc8`

## pseudocode

```c
__int64 __fastcall IPxlatPolicyMgrReadConfigurationWrapper(_DWORD *a1)
{
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl) )
    return IPxlatPolicyMgrReadConfiguration(a1);
  else
    return 50;
}

```

## disassembly

```asm
0x18000b1a0  push    rbx
0x18000b1a2  sub     rsp, 20h
0x18000b1a6  mov     rbx, rcx
0x18000b1a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x18000b1b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)
0x18000b1b5  test    al, al
0x18000b1b7  jz      short loc_18000B1C6
0x18000b1b9  mov     rcx, rbx
0x18000b1bc  add     rsp, 20h
0x18000b1c0  pop     rbx
0x18000b1c1  jmp     IPxlatPolicyMgrReadConfiguration
0x18000b1c6  mov     eax, 32h ; '2'
0x18000b1cb  add     rsp, 20h
0x18000b1cf  pop     rbx
0x18000b1d0  retn
```
