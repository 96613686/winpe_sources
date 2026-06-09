# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000fe04`
- end: `0x18000fe96`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180011274`
- `0x18001599c`

## callees

- `0x18000f220`
- `0x18000fe04`
- `0x18000fe9c`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        unsigned __int8 a3,
        ...)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  unsigned int v6; // r8d
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  v4 = a3;
  v5 = a2;
  v6 = *(_DWORD *)Feature_GPM_ResidencyTracking__descriptor;
  if ( (*(_DWORD *)Feature_GPM_ResidencyTracking__descriptor & 4) == 0 )
  {
    v8 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(
            a1,
            &v8);
    v6 = v8;
  }
  LODWORD(v9) = 0;
  WORD2(v9) = 1;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x2C7B397u,
           (v6 >> 10) & 1,
           (v6 >> 11) & 1,
           (__int64)va,
           v5,
           v4);
}

```

## disassembly

```asm
0x18000fe04  mov     r11, rsp
0x18000fe07  mov     [r11+10h], rbx
0x18000fe0b  mov     [r11+18h], rsi
0x18000fe0f  mov     [r11+20h], r9
0x18000fe13  push    rdi
0x18000fe14  sub     rsp, 40h
0x18000fe18  mov     rax, cs:Feature_GPM_ResidencyTracking__descriptor
0x18000fe1f  mov     rsi, rcx
0x18000fe22  movzx   ebx, r8b
0x18000fe26  movzx   edi, dl
0x18000fe29  mov     r8d, [rax]
0x18000fe2c  test    r8b, 4
0x18000fe30  jnz     short loc_18000FE46
0x18000fe32  lea     rdx, [r11+8]
0x18000fe36  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(void)
0x18000fe3b  mov     r9, [rax]
0x18000fe3e  mov     [rsp+48h+arg_0], r9
0x18000fe43  mov     r8d, r9d
0x18000fe46  mov     r9d, r8d
0x18000fe49  mov     [rsp+48h+var_18], ebx
0x18000fe4d  xor     eax, eax
0x18000fe4f  shr     r9d, 0Bh
0x18000fe53  mov     dword ptr [rsp+48h+arg_18], eax
0x18000fe57  lea     rcx, [rsi+8]
0x18000fe5b  shr     r8d, 0Ah
0x18000fe5f  lea     rax, [rsp+48h+arg_18]
0x18000fe64  and     r9d, 1
0x18000fe68  mov     [rsp+48h+var_20], edi
0x18000fe6c  and     r8d, 1
0x18000fe70  mov     [rsp+48h+var_28], rax
0x18000fe75  mov     edx, 2C7B397h
0x18000fe7a  mov     word ptr [rsp+48h+arg_18+4], 1
0x18000fe81  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000fe86  mov     rbx, [rsp+48h+arg_8]
0x18000fe8b  mov     rsi, [rsp+48h+arg_10]
0x18000fe90  add     rsp, 40h
0x18000fe94  pop     rdi
0x18000fe95  retn
```
