# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)

- ea: `0x14000a7e4`
- end: `0x14000a873`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14000b250`
- `0x14000d498`
- `0x14000d778`

## callees

- `0x140005824`
- `0x140009024`
- `0x14000a7e4`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(
        wil::details *a1)
{
  wil::details *v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  if ( (*(_DWORD *)Feature_Narrator_AddUpdates__descriptor & 4) == 0 )
  {
    v7 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(
            v2,
            &v7);
    v4 = v7;
  }
  LODWORD(v6) = 0;
  WORD2(v6) = 1;
  wil::details::ReportUsageToService((char *)a1 + 8, 59171042, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3);
  return v3;
}

```

## disassembly

```asm
0x14000a7e4  mov     [rsp+arg_10], rbx
0x14000a7e9  push    rdi
0x14000a7ea  sub     rsp, 40h
0x14000a7ee  lea     rdx, [rsp+48h+arg_0]
0x14000a7f3  mov     rdi, rcx
0x14000a7f6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)
0x14000a7fb  mov     rax, cs:Feature_Narrator_AddUpdates__descriptor
0x14000a802  mov     bl, byte ptr [rsp+48h+arg_0]
0x14000a806  and     bl, 1
0x14000a809  mov     r8d, [rax]
0x14000a80c  test    r8b, 4
0x14000a810  jnz     short loc_14000A827
0x14000a812  lea     rdx, [rsp+48h+arg_8]
0x14000a817  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)
0x14000a81c  mov     rcx, [rax]
0x14000a81f  mov     [rsp+48h+arg_8], rcx
0x14000a824  mov     r8d, ecx
0x14000a827  mov     r9d, r8d
0x14000a82a  movzx   edx, bl
0x14000a82d  xor     eax, eax
0x14000a82f  mov     [rsp+48h+var_20], edx
0x14000a833  mov     [rsp+48h+arg_0], eax
0x14000a837  lea     rcx, [rdi+8]
0x14000a83b  shr     r9d, 0Bh
0x14000a83f  lea     rax, [rsp+48h+arg_0]
0x14000a844  shr     r8d, 0Ah
0x14000a848  and     r9d, 1
0x14000a84c  and     r8d, 1
0x14000a850  mov     [rsp+48h+var_28], rax
0x14000a855  mov     edx, 386E0E2h
0x14000a85a  mov     [rsp+48h+arg_4], 1
0x14000a861  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000a866  mov     al, bl
0x14000a868  mov     rbx, [rsp+48h+arg_10]
0x14000a86d  add     rsp, 40h
0x14000a871  pop     rdi
0x14000a872  retn
```
