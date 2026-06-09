# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(void)

- ea: `0x180017930`
- end: `0x1800179c7`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800128d0`
- `0x1800133ac`
- `0x180015340`
- `0x1800172a4`
- `0x180017c70`

## callees

- `0x18000ad14`
- `0x180013cb8`
- `0x180017930`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_CLAT_Preview2_RandomLocalAddress__descriptor;
  if ( (*(_DWORD *)Feature_CLAT_Preview2_RandomLocalAddress__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 61736939, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x180017930  mov     [rsp+arg_10], rbx
0x180017935  push    rdi
0x180017936  sub     rsp, 40h
0x18001793a  lea     rdx, [rsp+48h+arg_0]
0x18001793f  mov     rdi, rcx
0x180017942  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(void)
0x180017947  mov     rax, cs:Feature_CLAT_Preview2_RandomLocalAddress__descriptor
0x18001794e  mov     bl, byte ptr [rsp+48h+arg_0]
0x180017952  and     bl, 1
0x180017955  mov     r8d, [rax]
0x180017958  test    r8b, 4
0x18001795c  jnz     short loc_180017973
0x18001795e  lea     rdx, [rsp+48h+arg_8]
0x180017963  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(void)
0x180017968  mov     rcx, [rax]
0x18001796b  mov     [rsp+48h+arg_8], rcx
0x180017970  mov     r8d, ecx
0x180017973  mov     r9d, r8d
0x180017976  movzx   edx, bl
0x180017979  xor     eax, eax
0x18001797b  shr     r9d, 0Bh
0x18001797f  mov     [rsp+48h+arg_0], eax
0x180017983  lea     rcx, [rdi+8]
0x180017987  shr     r8d, 0Ah
0x18001798b  lea     rax, [rsp+48h+arg_0]
0x180017990  mov     [rsp+48h+var_18], 3
0x180017998  and     r9d, 1
0x18001799c  mov     [rsp+48h+var_20], edx
0x1800179a0  and     r8d, 1
0x1800179a4  mov     edx, 3AE07EBh
0x1800179a9  mov     [rsp+48h+var_28], rax
0x1800179ae  mov     [rsp+48h+arg_4], 2
0x1800179b5  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800179ba  mov     al, bl
0x1800179bc  mov     rbx, [rsp+48h+arg_10]
0x1800179c1  add     rsp, 40h
0x1800179c5  pop     rdi
0x1800179c6  retn
```
