# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000cbec`
- end: `0x18000cc72`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180017214`

## callees

- `0x18000a6c4`
- `0x18000c898`
- `0x18000cbec`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        __int64 a3,
        ...)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v4 = a2;
  LODWORD(v5) = *(_DWORD *)Feature_StoreUpdateTelemetryEvent__descriptor;
  if ( (*(_DWORD *)Feature_StoreUpdateTelemetryEvent__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x3772E01u,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x18000cbec  mov     [rsp+arg_8], rbx
0x18000cbf1  mov     [rsp+arg_18], r9
0x18000cbf6  push    rdi
0x18000cbf7  sub     rsp, 40h
0x18000cbfb  mov     rax, cs:Feature_StoreUpdateTelemetryEvent__descriptor
0x18000cc02  mov     rdi, rcx
0x18000cc05  movzx   ebx, dl
0x18000cc08  mov     r8d, [rax]
0x18000cc0b  test    r8b, 4
0x18000cc0f  jnz     short loc_18000CC23
0x18000cc11  lea     rdx, [rsp+48h+arg_0]
0x18000cc16  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(void)
0x18000cc1b  mov     r8, [rax]
0x18000cc1e  mov     [rsp+48h+arg_0], r8
0x18000cc23  mov     r9d, r8d
0x18000cc26  mov     [rsp+48h+var_18], 3
0x18000cc2e  xor     eax, eax
0x18000cc30  shr     r9d, 0Bh
0x18000cc34  mov     dword ptr [rsp+48h+arg_18], eax
0x18000cc38  lea     rcx, [rdi+8]
0x18000cc3c  shr     r8d, 0Ah
0x18000cc40  lea     rax, [rsp+48h+arg_18]
0x18000cc45  and     r9d, 1
0x18000cc49  mov     [rsp+48h+var_20], ebx
0x18000cc4d  and     r8d, 1
0x18000cc51  mov     [rsp+48h+var_28], rax
0x18000cc56  mov     edx, 3772E01h
0x18000cc5b  mov     word ptr [rsp+48h+arg_18+4], 2
0x18000cc62  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000cc67  mov     rbx, [rsp+48h+arg_8]
0x18000cc6c  add     rsp, 40h
0x18000cc70  pop     rdi
0x18000cc71  retn
```
