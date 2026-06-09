# HardwareCheck::CommandSearchHardwareRequirements::IsCommandSearchCapablePC(void)

- ea: `0x180018cfc`
- end: `0x180018d4f`
- name: `?IsCommandSearchCapablePC@CommandSearchHardwareRequirements@HardwareCheck@@SA_NXZ`
- size: `83`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013230`

## callees

- `0x18000d4f4`
- `0x180018008`
- `0x180018cfc`
- `0x180018e58`
- `0x18001cc98`

## pseudocode

```c
char HardwareCheck::CommandSearchHardwareRequirements::IsCommandSearchCapablePC(void)
{
  udk::CopilotPlusDetection *v0; // rcx
  int v2; // [rsp+30h] [rbp+8h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56484228>::GetImpl'::`2'::impl);
  if ( !udk::CopilotPlusDetection::IsCopilotPlusCapablePC(v0) )
  {
    v2 = 7;
    HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<enum HardwareCheck::HardWareCheckResult>(&v2);
    return 0;
  }
  if ( !HardwareCheck::CommandSearchHardwareRequirements::HasCommandSearchCapableNpu() )
    return 0;
  v2 = 1;
  HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<enum HardwareCheck::HardWareCheckResult>(&v2);
  return 1;
}

```

## disassembly

```asm
0x180018cfc  sub     rsp, 28h
0x180018d00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56484228@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56484228@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228> `wil::Feature<__WilFeatureTraits_Feature_56484228>::GetImpl(void)'::`2'::impl
0x180018d07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56484228@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::__private_IsEnabled(void)
0x180018d0c  call    ?IsCopilotPlusCapablePC@CopilotPlusDetection@udk@@YA_NW4HardwareRequirementOption@Profile@System@WindowsUdk@winrt@@@Z; udk::CopilotPlusDetection::IsCopilotPlusCapablePC(winrt::WindowsUdk::System::Profile::HardwareRequirementOption)
0x180018d11  test    al, al
0x180018d13  jnz     short loc_180018D29
0x180018d15  lea     rcx, [rsp+28h+arg_0]
0x180018d1a  mov     [rsp+28h+arg_0], 7
0x180018d22  call    ??$HardWareCheckResult@W40HardwareCheck@@@CommandSearchHardwareRequirementsTelemetry@HardwareCheck@@SAX$$QEAW4HardWareCheckResult@1@@Z; HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<HardwareCheck::HardWareCheckResult>(HardwareCheck::HardWareCheckResult &&)
0x180018d27  jmp     short loc_180018D32
0x180018d29  call    ?HasCommandSearchCapableNpu@CommandSearchHardwareRequirements@HardwareCheck@@CA_NXZ; HardwareCheck::CommandSearchHardwareRequirements::HasCommandSearchCapableNpu(void)
0x180018d2e  test    al, al
0x180018d30  jnz     short loc_180018D36
0x180018d32  xor     al, al
0x180018d34  jmp     short loc_180018D4A
0x180018d36  lea     rcx, [rsp+28h+arg_0]
0x180018d3b  mov     [rsp+28h+arg_0], 1
0x180018d43  call    ??$HardWareCheckResult@W40HardwareCheck@@@CommandSearchHardwareRequirementsTelemetry@HardwareCheck@@SAX$$QEAW4HardWareCheckResult@1@@Z; HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<HardwareCheck::HardWareCheckResult>(HardwareCheck::HardWareCheckResult &&)
0x180018d48  mov     al, 1
0x180018d4a  add     rsp, 28h
0x180018d4e  retn
```
