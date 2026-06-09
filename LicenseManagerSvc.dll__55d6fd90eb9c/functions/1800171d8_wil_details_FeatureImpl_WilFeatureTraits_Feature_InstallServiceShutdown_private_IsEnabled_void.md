# wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)

- ea: `0x1800171d8`
- end: `0x18001720d`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000c780`
- `0x18000cb08`

## callees

- `0x18000c7b8`
- `0x18000cb60`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // r8
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::ReportUsage(a1, v5 & 1, v3);
  return v2;
}

```

## disassembly

```asm
0x1800171d8  mov     [rsp+arg_0], rbx
0x1800171dd  push    rdi
0x1800171de  sub     rsp, 20h
0x1800171e2  lea     rdx, [rsp+28h+arg_8]
0x1800171e7  mov     rdi, rcx
0x1800171ea  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(void)
0x1800171ef  mov     bl, byte ptr [rsp+28h+arg_8]
0x1800171f3  mov     rcx, rdi
0x1800171f6  and     bl, 1
0x1800171f9  mov     dl, bl
0x1800171fb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017200  mov     al, bl
0x180017202  mov     rbx, [rsp+28h+arg_0]
0x180017207  add     rsp, 20h
0x18001720b  pop     rdi
0x18001720c  retn
```
