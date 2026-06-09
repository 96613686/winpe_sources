# wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000cb60`
- end: `0x18000cbe6`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800171d8`

## callees

- `0x18000a6c4`
- `0x18000c7b8`
- `0x18000cb60`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::ReportUsage(
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
  LODWORD(v5) = *(_DWORD *)Feature_InstallServiceShutdown__descriptor;
  if ( (*(_DWORD *)Feature_InstallServiceShutdown__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x375DAD7u,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x18000cb60  mov     [rsp+arg_8], rbx
0x18000cb65  mov     [rsp+arg_18], r9
0x18000cb6a  push    rdi
0x18000cb6b  sub     rsp, 40h
0x18000cb6f  mov     rax, cs:Feature_InstallServiceShutdown__descriptor
0x18000cb76  mov     rdi, rcx
0x18000cb79  movzx   ebx, dl
0x18000cb7c  mov     r8d, [rax]
0x18000cb7f  test    r8b, 4
0x18000cb83  jnz     short loc_18000CB97
0x18000cb85  lea     rdx, [rsp+48h+arg_0]
0x18000cb8a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(void)
0x18000cb8f  mov     r8, [rax]
0x18000cb92  mov     [rsp+48h+arg_0], r8
0x18000cb97  mov     r9d, r8d
0x18000cb9a  mov     [rsp+48h+var_18], 3
0x18000cba2  xor     eax, eax
0x18000cba4  shr     r9d, 0Bh
0x18000cba8  mov     dword ptr [rsp+48h+arg_18], eax
0x18000cbac  lea     rcx, [rdi+8]
0x18000cbb0  shr     r8d, 0Ah
0x18000cbb4  lea     rax, [rsp+48h+arg_18]
0x18000cbb9  and     r9d, 1
0x18000cbbd  mov     [rsp+48h+var_20], ebx
0x18000cbc1  and     r8d, 1
0x18000cbc5  mov     [rsp+48h+var_28], rax
0x18000cbca  mov     edx, 375DAD7h
0x18000cbcf  mov     word ptr [rsp+48h+arg_18+4], 2
0x18000cbd6  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000cbdb  mov     rbx, [rsp+48h+arg_8]
0x18000cbe0  add     rsp, 40h
0x18000cbe4  pop     rdi
0x18000cbe5  retn
```
