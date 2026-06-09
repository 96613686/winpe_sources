# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(void)

- ea: `0x180011274`
- end: `0x1800112ac`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAA_NXZ`
- size: `56`
- prototype: `char __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180011630`
- `0x180013b70`
- `0x1800193d4`
- `0x1800258a0`

## callees

- `0x18000f220`
- `0x18000fe04`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // r8
  char v3; // bl
  __int64 v4; // rdx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(a1, &v6);
  LOBYTE(v2) = 3;
  v3 = v6 & 1;
  LOBYTE(v4) = v6 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::ReportUsage(a1, v4, v2);
  return v3;
}

```

## disassembly

```asm
0x180011274  mov     [rsp+arg_0], rbx
0x180011279  push    rdi
0x18001127a  sub     rsp, 20h
0x18001127e  lea     rdx, [rsp+28h+arg_8]
0x180011283  mov     rdi, rcx
0x180011286  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(void)
0x18001128b  mov     bl, [rsp+28h+arg_8]
0x18001128f  mov     r8b, 3
0x180011292  and     bl, 1
0x180011295  mov     rcx, rdi
0x180011298  mov     dl, bl
0x18001129a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001129f  mov     al, bl
0x1800112a1  mov     rbx, [rsp+28h+arg_0]
0x1800112a6  add     rsp, 20h
0x1800112aa  pop     rdi
0x1800112ab  retn
```
