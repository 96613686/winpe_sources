# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::__private_IsEnabled(void)

- ea: `0x18000d248`
- end: `0x18000d27d`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000abbc`

## callees

- `0x18000b594`
- `0x18000ca94`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v4; // r8
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v2 = v6 & 1;
  LOBYTE(v3) = v6 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::ReportUsage(
    (__int64)a1,
    v3,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d248  mov     [rsp+arg_0], rbx
0x18000d24d  push    rdi
0x18000d24e  sub     rsp, 20h
0x18000d252  lea     rdx, [rsp+28h+arg_8]
0x18000d257  mov     rdi, rcx
0x18000d25a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(void)
0x18000d25f  mov     bl, byte ptr [rsp+28h+arg_8]
0x18000d263  mov     rcx, rdi
0x18000d266  and     bl, 1
0x18000d269  mov     dl, bl
0x18000d26b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000d270  mov     al, bl
0x18000d272  mov     rbx, [rsp+28h+arg_0]
0x18000d277  add     rsp, 20h
0x18000d27b  pop     rdi
0x18000d27c  retn
```
