# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::__private_IsEnabled(void)

- ea: `0x18000ac14`
- end: `0x18000ac49`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000a210`

## callees

- `0x180005054`
- `0x1800085a8`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::ReportUsage(
    a1,
    v3);
  return v2;
}

```

## disassembly

```asm
0x18000ac14  mov     [rsp+arg_0], rbx
0x18000ac19  push    rdi
0x18000ac1a  sub     rsp, 20h
0x18000ac1e  lea     rdx, [rsp+28h+arg_8]
0x18000ac23  mov     rdi, rcx
0x18000ac26  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(void)
0x18000ac2b  mov     bl, [rsp+28h+arg_8]
0x18000ac2f  mov     rcx, rdi
0x18000ac32  and     bl, 1
0x18000ac35  mov     dl, bl
0x18000ac37  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ac3c  mov     al, bl
0x18000ac3e  mov     rbx, [rsp+28h+arg_0]
0x18000ac43  add     rsp, 20h
0x18000ac47  pop     rdi
0x18000ac48  retn
```
