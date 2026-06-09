# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x14000fbf0`
- end: `0x14000fc76`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: `__int64(wil::details *, unsigned __int8, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x140011b64`

## callees

- `0x14000b65c`
- `0x14000fbf0`
- `0x1400101bc`

## pseudocode

```c
__int64 wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::ReportUsage(
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
  LODWORD(v5) = *(_DWORD *)Feature_MDMAppInstallerFix__descriptor;
  if ( (*(_DWORD *)Feature_MDMAppInstallerFix__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 2;
  return wil::details::ReportUsageToService(
           (char *)a1 + 8,
           58785338,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64 *)va,
           v4,
           3);
}

```

## disassembly

```asm
0x14000fbf0  mov     [rsp+arg_8], rbx
0x14000fbf5  mov     [rsp+arg_18], r9
0x14000fbfa  push    rdi
0x14000fbfb  sub     rsp, 40h
0x14000fbff  mov     rax, cs:Feature_MDMAppInstallerFix__descriptor
0x14000fc06  mov     rdi, rcx
0x14000fc09  movzx   ebx, dl
0x14000fc0c  mov     r8d, [rax]
0x14000fc0f  test    r8b, 4
0x14000fc13  jnz     short loc_14000FC27
0x14000fc15  lea     rdx, [rsp+48h+arg_0]
0x14000fc1a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(void)
0x14000fc1f  mov     r8, [rax]
0x14000fc22  mov     [rsp+48h+arg_0], r8
0x14000fc27  mov     r9d, r8d
0x14000fc2a  mov     [rsp+48h+var_18], 3
0x14000fc32  xor     eax, eax
0x14000fc34  shr     r9d, 0Bh
0x14000fc38  mov     dword ptr [rsp+48h+arg_18], eax
0x14000fc3c  lea     rcx, [rdi+8]
0x14000fc40  shr     r8d, 0Ah
0x14000fc44  lea     rax, [rsp+48h+arg_18]
0x14000fc49  and     r9d, 1
0x14000fc4d  mov     [rsp+48h+var_20], ebx
0x14000fc51  and     r8d, 1
0x14000fc55  mov     [rsp+48h+var_28], rax
0x14000fc5a  mov     edx, 380FE3Ah
0x14000fc5f  mov     word ptr [rsp+48h+arg_18+4], 2
0x14000fc66  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000fc6b  mov     rbx, [rsp+48h+arg_8]
0x14000fc70  add     rsp, 40h
0x14000fc74  pop     rdi
0x14000fc75  retn
```
