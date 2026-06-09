# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)

- ea: `0x18000aff4`
- end: `0x18000b087`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `147`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a714`
- `0x18000ff68`
- `0x18001013c`
- `0x180013830`
- `0x180013a04`

## callees

- `0x18000a550`
- `0x18000ad14`
- `0x18000aff4`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_CLAT_Core__descriptor;
  if ( (*(_DWORD *)Feature_CLAT_Core__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 56662908, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 0);
  return v3;
}

```

## disassembly

```asm
0x18000aff4  mov     [rsp+arg_8], rbx
0x18000aff9  push    rdi
0x18000affa  sub     rsp, 40h
0x18000affe  lea     rdx, [rsp+48h+arg_0]
0x18000b003  mov     rdi, rcx
0x18000b006  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(void)
0x18000b00b  mov     rax, cs:Feature_CLAT_Core__descriptor
0x18000b012  mov     bl, byte ptr [rsp+48h+arg_0]
0x18000b016  and     bl, 1
0x18000b019  mov     r8d, [rax]
0x18000b01c  test    r8b, 4
0x18000b020  jnz     short loc_18000B037
0x18000b022  lea     rdx, [rsp+48h+arg_10]
0x18000b027  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(void)
0x18000b02c  mov     rcx, [rax]
0x18000b02f  mov     [rsp+48h+arg_10], rcx
0x18000b034  mov     r8d, ecx
0x18000b037  xor     eax, eax
0x18000b039  movzx   edx, bl
0x18000b03c  mov     r9d, r8d
0x18000b03f  mov     [rsp+48h+var_18], eax
0x18000b043  mov     [rsp+48h+var_20], edx
0x18000b047  lea     rcx, [rdi+8]
0x18000b04b  mov     [rsp+48h+arg_0], eax
0x18000b04f  mov     edx, 3609B7Ch
0x18000b054  shr     r9d, 0Bh
0x18000b058  lea     rax, [rsp+48h+arg_0]
0x18000b05d  shr     r8d, 0Ah
0x18000b061  and     r9d, 1
0x18000b065  and     r8d, 1
0x18000b069  mov     [rsp+48h+var_28], rax
0x18000b06e  mov     [rsp+48h+arg_4], 2
0x18000b075  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000b07a  mov     al, bl
0x18000b07c  mov     rbx, [rsp+48h+arg_8]
0x18000b081  add     rsp, 40h
0x18000b085  pop     rdi
0x18000b086  retn
```
