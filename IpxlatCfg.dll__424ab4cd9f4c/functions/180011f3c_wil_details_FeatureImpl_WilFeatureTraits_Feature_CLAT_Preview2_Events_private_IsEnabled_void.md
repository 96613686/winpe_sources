# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(void)

- ea: `0x180011f3c`
- end: `0x180011fd3`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f668`
- `0x1800128d0`
- `0x18001468c`
- `0x180016094`
- `0x1800172a4`

## callees

- `0x18000ad14`
- `0x1800104e4`
- `0x180011f3c`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_CLAT_Preview2_Events__descriptor;
  if ( (*(_DWORD *)Feature_CLAT_Preview2_Events__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 58687608, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x180011f3c  mov     [rsp+arg_10], rbx
0x180011f41  push    rdi
0x180011f42  sub     rsp, 40h
0x180011f46  lea     rdx, [rsp+48h+arg_0]
0x180011f4b  mov     rdi, rcx
0x180011f4e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(void)
0x180011f53  mov     rax, cs:Feature_CLAT_Preview2_Events__descriptor
0x180011f5a  mov     bl, byte ptr [rsp+48h+arg_0]
0x180011f5e  and     bl, 1
0x180011f61  mov     r8d, [rax]
0x180011f64  test    r8b, 4
0x180011f68  jnz     short loc_180011F7F
0x180011f6a  lea     rdx, [rsp+48h+arg_8]
0x180011f6f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(void)
0x180011f74  mov     rcx, [rax]
0x180011f77  mov     [rsp+48h+arg_8], rcx
0x180011f7c  mov     r8d, ecx
0x180011f7f  mov     r9d, r8d
0x180011f82  movzx   edx, bl
0x180011f85  xor     eax, eax
0x180011f87  shr     r9d, 0Bh
0x180011f8b  mov     [rsp+48h+arg_0], eax
0x180011f8f  lea     rcx, [rdi+8]
0x180011f93  shr     r8d, 0Ah
0x180011f97  lea     rax, [rsp+48h+arg_0]
0x180011f9c  mov     [rsp+48h+var_18], 3
0x180011fa4  and     r9d, 1
0x180011fa8  mov     [rsp+48h+var_20], edx
0x180011fac  and     r8d, 1
0x180011fb0  mov     edx, 37F8078h
0x180011fb5  mov     [rsp+48h+var_28], rax
0x180011fba  mov     [rsp+48h+arg_4], 2
0x180011fc1  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180011fc6  mov     al, bl
0x180011fc8  mov     rbx, [rsp+48h+arg_10]
0x180011fcd  add     rsp, 40h
0x180011fd1  pop     rdi
0x180011fd2  retn
```
