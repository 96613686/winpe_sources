# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(void)

- ea: `0x18000c1cc`
- end: `0x18000c204`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NXZ`
- size: `56`
- prototype: `char __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba4c`
- `0x18000c590`
- `0x1800128d0`
- `0x18001468c`
- `0x180016094`

## callees

- `0x18000b648`
- `0x18000b81c`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // r8
  char v3; // bl
  __int64 v4; // rdx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  LOBYTE(v2) = 3;
  v3 = v6 & 1;
  LOBYTE(v4) = v6 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::ReportUsage(a1, v4, v2);
  return v3;
}

```

## disassembly

```asm
0x18000c1cc  mov     [rsp+arg_0], rbx
0x18000c1d1  push    rdi
0x18000c1d2  sub     rsp, 20h
0x18000c1d6  lea     rdx, [rsp+28h+arg_8]
0x18000c1db  mov     rdi, rcx
0x18000c1de  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetCachedFeatureEnabledState(void)
0x18000c1e3  mov     bl, [rsp+28h+arg_8]
0x18000c1e7  mov     r8b, 3
0x18000c1ea  and     bl, 1
0x18000c1ed  mov     rcx, rdi
0x18000c1f0  mov     dl, bl
0x18000c1f2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000c1f7  mov     al, bl
0x18000c1f9  mov     rbx, [rsp+28h+arg_0]
0x18000c1fe  add     rsp, 20h
0x18000c202  pop     rdi
0x18000c203  retn
```
