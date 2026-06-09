# DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(bool)

- ea: `0x180013c3c`
- end: `0x180013c8f`
- name: `?_UpdateSpoolerMitigations@ConfigurationManager@DeviceConfiguration@@AEAAX_N@Z`
- size: `83`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x1800128e8`
- `0x180012c70`
- `0x180013c3c`
- `0x180014114`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_UpdateSpoolerMitigations(
        DeviceConfiguration::ConfigurationManager *this,
        char a2)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( a2 )
  {
    DeviceConfiguration::ConfigurationManager::_EnableMitigations((__int64)this, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
      DeviceConfiguration::ConfigurationManager::_EnableMitigations(v2, 1);
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
      DeviceConfiguration::ConfigurationManager::_DisableMitigations(v3, 1);
    DeviceConfiguration::ConfigurationManager::_DisableMitigations(v3, 0);
  }
}

```

## disassembly

```asm
0x180013c3c  sub     rsp, 28h
0x180013c40  test    dl, dl
0x180013c42  jz      short loc_180013C69
0x180013c44  xor     edx, edx
0x180013c46  call    ?_EnableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z; DeviceConfiguration::ConfigurationManager::_EnableMitigations(DeviceConfiguration::SpoolerProcess)
0x180013c4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180013c52  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180013c57  test    al, al
0x180013c59  jz      short loc_180013C8A
0x180013c5b  mov     edx, 1
0x180013c60  add     rsp, 28h
0x180013c64  jmp     ?_EnableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z; DeviceConfiguration::ConfigurationManager::_EnableMitigations(DeviceConfiguration::SpoolerProcess)
0x180013c69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180013c70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180013c75  test    al, al
0x180013c77  jz      short loc_180013C83
0x180013c79  mov     edx, 1
0x180013c7e  call    ?_DisableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z; DeviceConfiguration::ConfigurationManager::_DisableMitigations(DeviceConfiguration::SpoolerProcess)
0x180013c83  xor     edx, edx
0x180013c85  call    ?_DisableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z; DeviceConfiguration::ConfigurationManager::_DisableMitigations(DeviceConfiguration::SpoolerProcess)
0x180013c8a  add     rsp, 28h
0x180013c8e  retn
```
