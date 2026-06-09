# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::__private_IsEnabled(void)

- ea: `0x18000a934`
- end: `0x18000a969`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b358`

## callees

- `0x180005304`
- `0x180008dac`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // r8
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::ReportUsage(
    a1,
    v5 & 1,
    v3);
  return v2;
}

```

## disassembly

```asm
0x18000a934  mov     [rsp+arg_0], rbx
0x18000a939  push    rdi
0x18000a93a  sub     rsp, 20h
0x18000a93e  lea     rdx, [rsp+28h+arg_8]
0x18000a943  mov     rdi, rcx
0x18000a946  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCachedFeatureEnabledState(void)
0x18000a94b  mov     bl, byte ptr [rsp+28h+arg_8]
0x18000a94f  mov     rcx, rdi
0x18000a952  and     bl, 1
0x18000a955  mov     dl, bl
0x18000a957  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000a95c  mov     al, bl
0x18000a95e  mov     rbx, [rsp+28h+arg_0]
0x18000a963  add     rsp, 20h
0x18000a967  pop     rdi
0x18000a968  retn
```
