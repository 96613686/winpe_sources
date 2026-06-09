# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)

- ea: `0x18000b12c`
- end: `0x18000b164`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ`
- size: `56`
- prototype: `char __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b170`
- `0x18000b1a0`
- `0x18000b1e0`
- `0x18000b250`
- `0x18000b280`
- `0x18000ea3c`
- `0x18000f4f8`
- `0x18000f9f0`
- `0x1800128d0`

## callees

- `0x18000a8e8`
- `0x18000ac7c`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // r8
  char v3; // bl
  __int64 v4; // rdx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetCachedFeatureEnabledState(a1, &v6);
  LOBYTE(v2) = 3;
  v3 = v6 & 1;
  LOBYTE(v4) = v6 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::ReportUsage(a1, v4, v2);
  return v3;
}

```

## disassembly

```asm
0x18000b12c  mov     [rsp+arg_0], rbx
0x18000b131  push    rdi
0x18000b132  sub     rsp, 20h
0x18000b136  lea     rdx, [rsp+28h+arg_8]
0x18000b13b  mov     rdi, rcx
0x18000b13e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetCachedFeatureEnabledState(void)
0x18000b143  mov     bl, [rsp+28h+arg_8]
0x18000b147  mov     r8b, 3
0x18000b14a  and     bl, 1
0x18000b14d  mov     rcx, rdi
0x18000b150  mov     dl, bl
0x18000b152  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000b157  mov     al, bl
0x18000b159  mov     rbx, [rsp+28h+arg_0]
0x18000b15e  add     rsp, 20h
0x18000b162  pop     rdi
0x18000b163  retn
```
