# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::__private_IsEnabled(void)

- ea: `0x140005a78`
- end: `0x140005aad`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000e590`

## callees

- `0x140009774`
- `0x14000990c`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::__private_IsEnabled(__int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x140005a78  mov     [rsp+arg_0], rbx
0x140005a7d  push    rdi
0x140005a7e  sub     rsp, 20h
0x140005a82  lea     rdx, [rsp+28h+arg_8]
0x140005a87  mov     rdi, rcx
0x140005a8a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(void)
0x140005a8f  mov     bl, [rsp+28h+arg_8]
0x140005a93  mov     rcx, rdi
0x140005a96  and     bl, 1
0x140005a99  mov     dl, bl
0x140005a9b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140005aa0  mov     al, bl
0x140005aa2  mov     rbx, [rsp+28h+arg_0]
0x140005aa7  add     rsp, 20h
0x140005aab  pop     rdi
0x140005aac  retn
```
