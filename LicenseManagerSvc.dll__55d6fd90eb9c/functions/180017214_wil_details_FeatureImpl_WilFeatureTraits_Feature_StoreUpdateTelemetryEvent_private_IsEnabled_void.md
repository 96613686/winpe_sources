# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::__private_IsEnabled(void)

- ea: `0x180017214`
- end: `0x180017249`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cc78`

## callees

- `0x18000c898`
- `0x18000cbec`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // r8
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::ReportUsage(a1, v5 & 1, v3);
  return v2;
}

```

## disassembly

```asm
0x180017214  mov     [rsp+arg_0], rbx
0x180017219  push    rdi
0x18001721a  sub     rsp, 20h
0x18001721e  lea     rdx, [rsp+28h+arg_8]
0x180017223  mov     rdi, rcx
0x180017226  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(void)
0x18001722b  mov     bl, byte ptr [rsp+28h+arg_8]
0x18001722f  mov     rcx, rdi
0x180017232  and     bl, 1
0x180017235  mov     dl, bl
0x180017237  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001723c  mov     al, bl
0x18001723e  mov     rbx, [rsp+28h+arg_0]
0x180017243  add     rsp, 20h
0x180017247  pop     rdi
0x180017248  retn
```
