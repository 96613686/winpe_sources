# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)

- ea: `0x180011a20`
- end: `0x180011ab7`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180007490`
- `0x18000a7d0`
- `0x18000a8c0`
- `0x18000c260`
- `0x18000c410`
- `0x18000f418`

## callees

- `0x180008250`
- `0x18000dc68`
- `0x180011a20`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 57665307, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x180011a20  mov     [rsp+arg_10], rbx
0x180011a25  push    rdi
0x180011a26  sub     rsp, 40h
0x180011a2a  lea     rdx, [rsp+48h+arg_0]
0x180011a2f  mov     rdi, rcx
0x180011a32  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(void)
0x180011a37  mov     rax, cs:Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor
0x180011a3e  mov     bl, byte ptr [rsp+48h+arg_0]
0x180011a42  and     bl, 1
0x180011a45  mov     r8d, [rax]
0x180011a48  test    r8b, 4
0x180011a4c  jnz     short loc_180011A63
0x180011a4e  lea     rdx, [rsp+48h+arg_8]
0x180011a53  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(void)
0x180011a58  mov     rcx, [rax]
0x180011a5b  mov     [rsp+48h+arg_8], rcx
0x180011a60  mov     r8d, ecx
0x180011a63  mov     r9d, r8d
0x180011a66  movzx   edx, bl
0x180011a69  xor     eax, eax
0x180011a6b  shr     r9d, 0Bh
0x180011a6f  mov     [rsp+48h+arg_0], eax
0x180011a73  lea     rcx, [rdi+8]
0x180011a77  shr     r8d, 0Ah
0x180011a7b  lea     rax, [rsp+48h+arg_0]
0x180011a80  mov     [rsp+48h+var_18], 3
0x180011a88  and     r9d, 1
0x180011a8c  mov     [rsp+48h+var_20], edx
0x180011a90  and     r8d, 1
0x180011a94  mov     edx, 36FE71Bh
0x180011a99  mov     [rsp+48h+var_28], rax
0x180011a9e  mov     [rsp+48h+arg_4], 2
0x180011aa5  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180011aaa  mov     al, bl
0x180011aac  mov     rbx, [rsp+48h+arg_10]
0x180011ab1  add     rsp, 40h
0x180011ab5  pop     rdi
0x180011ab6  retn
```
