# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180008dac`
- end: `0x180008e32`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a934`

## callees

- `0x180005304`
- `0x180008dac`
- `0x180009164`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::ReportUsage(
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
  LODWORD(v5) = *(_DWORD *)Feature_StateRepository_SRCacheContextCacheLeak__descriptor;
  if ( (*(_DWORD *)Feature_StateRepository_SRCacheContextCacheLeak__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x274777Du,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x180008dac  mov     [rsp+arg_8], rbx
0x180008db1  mov     [rsp+arg_18], r9
0x180008db6  push    rdi
0x180008db7  sub     rsp, 40h
0x180008dbb  mov     rax, cs:Feature_StateRepository_SRCacheContextCacheLeak__descriptor
0x180008dc2  mov     rdi, rcx
0x180008dc5  movzx   ebx, dl
0x180008dc8  mov     r8d, [rax]
0x180008dcb  test    r8b, 4
0x180008dcf  jnz     short loc_180008DE3
0x180008dd1  lea     rdx, [rsp+48h+arg_0]
0x180008dd6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCachedFeatureEnabledState(void)
0x180008ddb  mov     r8, [rax]
0x180008dde  mov     [rsp+48h+arg_0], r8
0x180008de3  mov     r9d, r8d
0x180008de6  mov     [rsp+48h+var_18], 3
0x180008dee  xor     eax, eax
0x180008df0  shr     r9d, 0Bh
0x180008df4  mov     dword ptr [rsp+48h+arg_18], eax
0x180008df8  lea     rcx, [rdi+8]
0x180008dfc  shr     r8d, 0Ah
0x180008e00  lea     rax, [rsp+48h+arg_18]
0x180008e05  and     r9d, 1
0x180008e09  mov     [rsp+48h+var_20], ebx
0x180008e0d  and     r8d, 1
0x180008e11  mov     [rsp+48h+var_28], rax
0x180008e16  mov     edx, 274777Dh
0x180008e1b  mov     word ptr [rsp+48h+arg_18+4], 2
0x180008e22  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180008e27  mov     rbx, [rsp+48h+arg_8]
0x180008e2c  add     rsp, 40h
0x180008e30  pop     rdi
0x180008e31  retn
```
