# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::__private_IsEnabled(void)

- ea: `0x1400056b8`
- end: `0x1400056ed`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000e590`

## callees

- `0x140007474`
- `0x14000760c`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x1400056b8  mov     [rsp+arg_0], rbx
0x1400056bd  push    rdi
0x1400056be  sub     rsp, 20h
0x1400056c2  lea     rdx, [rsp+28h+arg_8]
0x1400056c7  mov     rdi, rcx
0x1400056ca  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(void)
0x1400056cf  mov     bl, [rsp+28h+arg_8]
0x1400056d3  mov     rcx, rdi
0x1400056d6  and     bl, 1
0x1400056d9  mov     dl, bl
0x1400056db  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400056e0  mov     al, bl
0x1400056e2  mov     rbx, [rsp+28h+arg_0]
0x1400056e7  add     rsp, 20h
0x1400056eb  pop     rdi
0x1400056ec  retn
```
