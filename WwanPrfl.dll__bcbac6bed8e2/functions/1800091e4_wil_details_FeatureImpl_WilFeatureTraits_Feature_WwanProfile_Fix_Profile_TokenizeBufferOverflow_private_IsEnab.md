# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::__private_IsEnabled(void)

- ea: `0x1800091e4`
- end: `0x180009219`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e520`

## callees

- `0x180004b44`
- `0x1800076b0`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::ReportUsage(
    a1,
    v3);
  return v2;
}

```

## disassembly

```asm
0x1800091e4  mov     [rsp+arg_0], rbx
0x1800091e9  push    rdi
0x1800091ea  sub     rsp, 20h
0x1800091ee  lea     rdx, [rsp+28h+arg_8]
0x1800091f3  mov     rdi, rcx
0x1800091f6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(void)
0x1800091fb  mov     bl, [rsp+28h+arg_8]
0x1800091ff  mov     rcx, rdi
0x180009202  and     bl, 1
0x180009205  mov     dl, bl
0x180009207  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000920c  mov     al, bl
0x18000920e  mov     rbx, [rsp+28h+arg_0]
0x180009213  add     rsp, 20h
0x180009217  pop     rdi
0x180009218  retn
```
