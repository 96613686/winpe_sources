# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18001745c`
- end: `0x1800174e3`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180017170`

## callees

- `0x18000c6ec`
- `0x180016f24`
- `0x18001745c`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(
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
  LODWORD(v5) = *(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor;
  if ( (*(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 3;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x16967CFu,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x18001745c  mov     [rsp+arg_8], rbx
0x180017461  mov     [rsp+arg_18], r9
0x180017466  push    rdi
0x180017467  sub     rsp, 40h
0x18001746b  mov     rax, cs:Feature_WVD_MultiSession_User_Configuration__descriptor
0x180017472  mov     rdi, rcx
0x180017475  movzx   ebx, dl
0x180017478  mov     r8d, [rax]
0x18001747b  test    r8b, 4
0x18001747f  jnz     short loc_180017493
0x180017481  lea     rdx, [rsp+48h+arg_0]
0x180017486  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(void)
0x18001748b  mov     r8, [rax]
0x18001748e  mov     [rsp+48h+arg_0], r8
0x180017493  mov     r9d, r8d
0x180017496  mov     [rsp+48h+var_18], 3
0x18001749e  xor     eax, eax
0x1800174a0  shr     r9d, 0Bh
0x1800174a4  mov     dword ptr [rsp+48h+arg_18], eax
0x1800174a8  lea     rcx, [rdi+8]
0x1800174ac  shr     r8d, 0Ah
0x1800174b0  lea     rax, [rsp+48h+arg_18]
0x1800174b5  and     r9d, 1
0x1800174b9  mov     [rsp+48h+var_20], ebx
0x1800174bd  and     r8d, 1
0x1800174c1  mov     [rsp+48h+var_28], rax
0x1800174c6  mov     edx, 16967CFh
0x1800174cb  mov     word ptr [rsp+48h+arg_18+4], 3
0x1800174d2  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800174d7  mov     rbx, [rsp+48h+arg_8]
0x1800174dc  add     rsp, 40h
0x1800174e0  pop     rdi
0x1800174e1  retn
```
