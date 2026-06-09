# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)

- ea: `0x18000bbd0`
- end: `0x18000bc08`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ`
- size: `56`
- prototype: `char __fastcall(__int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a4f0`
- `0x18000d750`
- `0x18000d938`
- `0x18000dc90`
- `0x18000de04`
- `0x18000e16c`
- `0x18000e804`
- `0x18000f624`
- `0x18000f934`
- `0x18000fe60`
- `0x18000ff50`
- `0x1800100a4`
- `0x1800103ec`
- `0x180010488`

## callees

- `0x1800057bc`
- `0x1800087f4`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // r8
  char v3; // bl
  __int64 v4; // rdx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  LOBYTE(v2) = 3;
  v3 = v6 & 1;
  LOBYTE(v4) = v6 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::ReportUsage(a1, v4, v2);
  return v3;
}

```

## disassembly

```asm
0x18000bbd0  mov     [rsp+arg_0], rbx
0x18000bbd5  push    rdi
0x18000bbd6  sub     rsp, 20h
0x18000bbda  lea     rdx, [rsp+28h+arg_8]
0x18000bbdf  mov     rdi, rcx
0x18000bbe2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(void)
0x18000bbe7  mov     bl, [rsp+28h+arg_8]
0x18000bbeb  mov     r8b, 3
0x18000bbee  and     bl, 1
0x18000bbf1  mov     rcx, rdi
0x18000bbf4  mov     dl, bl
0x18000bbf6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000bbfb  mov     al, bl
0x18000bbfd  mov     rbx, [rsp+28h+arg_0]
0x18000bc02  add     rsp, 20h
0x18000bc06  pop     rdi
0x18000bc07  retn
```
