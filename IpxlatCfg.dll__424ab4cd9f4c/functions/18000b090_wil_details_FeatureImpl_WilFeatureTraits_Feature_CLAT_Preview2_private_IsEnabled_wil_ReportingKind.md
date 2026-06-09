# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)

- ea: `0x18000b090`
- end: `0x18000b123`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `147`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a8e8`
- `0x18000b648`
- `0x1800104e4`
- `0x1800106b8`
- `0x180013cb8`
- `0x180014060`

## callees

- `0x18000a714`
- `0x18000ad14`
- `0x18000b090`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_CLAT_Preview2__descriptor;
  if ( (*(_DWORD *)Feature_CLAT_Preview2__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 58583658, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 0);
  return v3;
}

```

## disassembly

```asm
0x18000b090  mov     [rsp+arg_8], rbx
0x18000b095  push    rdi
0x18000b096  sub     rsp, 40h
0x18000b09a  lea     rdx, [rsp+48h+arg_0]
0x18000b09f  mov     rdi, rcx
0x18000b0a2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(void)
0x18000b0a7  mov     rax, cs:Feature_CLAT_Preview2__descriptor
0x18000b0ae  mov     bl, byte ptr [rsp+48h+arg_0]
0x18000b0b2  and     bl, 1
0x18000b0b5  mov     r8d, [rax]
0x18000b0b8  test    r8b, 4
0x18000b0bc  jnz     short loc_18000B0D3
0x18000b0be  lea     rdx, [rsp+48h+arg_10]
0x18000b0c3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(void)
0x18000b0c8  mov     rcx, [rax]
0x18000b0cb  mov     [rsp+48h+arg_10], rcx
0x18000b0d0  mov     r8d, ecx
0x18000b0d3  xor     eax, eax
0x18000b0d5  movzx   edx, bl
0x18000b0d8  mov     r9d, r8d
0x18000b0db  mov     [rsp+48h+var_18], eax
0x18000b0df  mov     [rsp+48h+var_20], edx
0x18000b0e3  lea     rcx, [rdi+8]
0x18000b0e7  mov     [rsp+48h+arg_0], eax
0x18000b0eb  mov     edx, 37DEA6Ah
0x18000b0f0  shr     r9d, 0Bh
0x18000b0f4  lea     rax, [rsp+48h+arg_0]
0x18000b0f9  shr     r8d, 0Ah
0x18000b0fd  and     r9d, 1
0x18000b101  and     r8d, 1
0x18000b105  mov     [rsp+48h+var_28], rax
0x18000b10a  mov     [rsp+48h+arg_4], 2
0x18000b111  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000b116  mov     al, bl
0x18000b118  mov     rbx, [rsp+48h+arg_8]
0x18000b11d  add     rsp, 40h
0x18000b121  pop     rdi
0x18000b122  retn
```
