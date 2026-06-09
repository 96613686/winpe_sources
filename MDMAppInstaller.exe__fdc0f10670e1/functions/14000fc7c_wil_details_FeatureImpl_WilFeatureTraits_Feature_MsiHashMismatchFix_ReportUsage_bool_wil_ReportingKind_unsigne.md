# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x14000fc7c`
- end: `0x14000fd02`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: `__int64(wil::details *, unsigned __int8, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14000e6cc`

## callees

- `0x14000b79c`
- `0x14000fc7c`
- `0x1400101bc`

## pseudocode

```c
__int64 wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        __int64 a3,
        ...)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v4 = a2;
  LODWORD(v5) = *(_DWORD *)Feature_MsiHashMismatchFix__descriptor;
  if ( (*(_DWORD *)Feature_MsiHashMismatchFix__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 3;
  return wil::details::ReportUsageToService(
           (char *)a1 + 8,
           33280101,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64 *)va,
           v4,
           3);
}

```

## disassembly

```asm
0x14000fc7c  mov     [rsp+arg_8], rbx
0x14000fc81  mov     [rsp+arg_18], r9
0x14000fc86  push    rdi
0x14000fc87  sub     rsp, 40h
0x14000fc8b  mov     rax, cs:Feature_MsiHashMismatchFix__descriptor
0x14000fc92  mov     rdi, rcx
0x14000fc95  movzx   ebx, dl
0x14000fc98  mov     r8d, [rax]
0x14000fc9b  test    r8b, 4
0x14000fc9f  jnz     short loc_14000FCB3
0x14000fca1  lea     rdx, [rsp+48h+arg_0]
0x14000fca6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCachedFeatureEnabledState(void)
0x14000fcab  mov     r8, [rax]
0x14000fcae  mov     [rsp+48h+arg_0], r8
0x14000fcb3  mov     r9d, r8d
0x14000fcb6  mov     [rsp+48h+var_18], 3
0x14000fcbe  xor     eax, eax
0x14000fcc0  shr     r9d, 0Bh
0x14000fcc4  mov     dword ptr [rsp+48h+arg_18], eax
0x14000fcc8  lea     rcx, [rdi+8]
0x14000fccc  shr     r8d, 0Ah
0x14000fcd0  lea     rax, [rsp+48h+arg_18]
0x14000fcd5  and     r9d, 1
0x14000fcd9  mov     [rsp+48h+var_20], ebx
0x14000fcdd  and     r8d, 1
0x14000fce1  mov     [rsp+48h+var_28], rax
0x14000fce6  mov     edx, 1FBD065h
0x14000fceb  mov     word ptr [rsp+48h+arg_18+4], 3
0x14000fcf2  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000fcf7  mov     rbx, [rsp+48h+arg_8]
0x14000fcfc  add     rsp, 40h
0x14000fd00  pop     rdi
0x14000fd01  retn
```
