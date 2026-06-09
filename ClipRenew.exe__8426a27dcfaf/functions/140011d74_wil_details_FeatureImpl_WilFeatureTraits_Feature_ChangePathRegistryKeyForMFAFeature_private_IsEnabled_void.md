# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::__private_IsEnabled(void)

- ea: `0x140011d74`
- end: `0x140011e03`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature@@@details@wil@@QEAA_NXZ`
- size: `143`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140007dcc`

## callees

- `0x140007140`
- `0x140011010`
- `0x140011d74`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_ChangePathRegistryKeyForMFAFeature__descriptor;
  if ( (*(_DWORD *)Feature_ChangePathRegistryKeyForMFAFeature__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 49803604, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3);
  return v3;
}

```

## disassembly

```asm
0x140011d74  mov     [rsp+arg_10], rbx
0x140011d79  push    rdi
0x140011d7a  sub     rsp, 40h
0x140011d7e  lea     rdx, [rsp+48h+arg_0]
0x140011d83  mov     rdi, rcx
0x140011d86  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(void)
0x140011d8b  mov     rax, cs:Feature_ChangePathRegistryKeyForMFAFeature__descriptor
0x140011d92  mov     bl, byte ptr [rsp+48h+arg_0]
0x140011d96  and     bl, 1
0x140011d99  mov     r8d, [rax]
0x140011d9c  test    r8b, 4
0x140011da0  jnz     short loc_140011DB7
0x140011da2  lea     rdx, [rsp+48h+arg_8]
0x140011da7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(void)
0x140011dac  mov     rcx, [rax]
0x140011daf  mov     [rsp+48h+arg_8], rcx
0x140011db4  mov     r8d, ecx
0x140011db7  mov     r9d, r8d
0x140011dba  movzx   edx, bl
0x140011dbd  xor     eax, eax
0x140011dbf  mov     [rsp+48h+var_20], edx
0x140011dc3  mov     [rsp+48h+arg_0], eax
0x140011dc7  lea     rcx, [rdi+8]
0x140011dcb  shr     r9d, 0Bh
0x140011dcf  lea     rax, [rsp+48h+arg_0]
0x140011dd4  shr     r8d, 0Ah
0x140011dd8  and     r9d, 1
0x140011ddc  and     r8d, 1
0x140011de0  mov     [rsp+48h+var_28], rax
0x140011de5  mov     edx, 2F7F154h
0x140011dea  mov     [rsp+48h+arg_4], 2
0x140011df1  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140011df6  mov     al, bl
0x140011df8  mov     rbx, [rsp+48h+arg_10]
0x140011dfd  add     rsp, 40h
0x140011e01  pop     rdi
0x140011e02  retn
```
