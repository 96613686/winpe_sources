# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::__private_IsEnabled(void)

- ea: `0x180011980`
- end: `0x180011a17`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000f418`

## callees

- `0x180008170`
- `0x18000dc68`
- `0x180011980`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Servicing_QMR_UX_Update__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_QMR_UX_Update__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 59402696, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x180011980  mov     [rsp+arg_10], rbx
0x180011985  push    rdi
0x180011986  sub     rsp, 40h
0x18001198a  lea     rdx, [rsp+48h+arg_0]
0x18001198f  mov     rdi, rcx
0x180011992  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(void)
0x180011997  mov     rax, cs:Feature_Servicing_QMR_UX_Update__descriptor
0x18001199e  mov     bl, byte ptr [rsp+48h+arg_0]
0x1800119a2  and     bl, 1
0x1800119a5  mov     r8d, [rax]
0x1800119a8  test    r8b, 4
0x1800119ac  jnz     short loc_1800119C3
0x1800119ae  lea     rdx, [rsp+48h+arg_8]
0x1800119b3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(void)
0x1800119b8  mov     rcx, [rax]
0x1800119bb  mov     [rsp+48h+arg_8], rcx
0x1800119c0  mov     r8d, ecx
0x1800119c3  mov     r9d, r8d
0x1800119c6  movzx   edx, bl
0x1800119c9  xor     eax, eax
0x1800119cb  shr     r9d, 0Bh
0x1800119cf  mov     [rsp+48h+arg_0], eax
0x1800119d3  lea     rcx, [rdi+8]
0x1800119d7  shr     r8d, 0Ah
0x1800119db  lea     rax, [rsp+48h+arg_0]
0x1800119e0  mov     [rsp+48h+var_18], 3
0x1800119e8  and     r9d, 1
0x1800119ec  mov     [rsp+48h+var_20], edx
0x1800119f0  and     r8d, 1
0x1800119f4  mov     edx, 38A69C8h
0x1800119f9  mov     [rsp+48h+var_28], rax
0x1800119fe  mov     [rsp+48h+arg_4], 2
0x180011a05  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180011a0a  mov     al, bl
0x180011a0c  mov     rbx, [rsp+48h+arg_10]
0x180011a11  add     rsp, 40h
0x180011a15  pop     rdi
0x180011a16  retn
```
