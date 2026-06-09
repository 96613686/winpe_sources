# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::__private_IsEnabled(void)

- ea: `0x140011b64`
- end: `0x140011b99`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400098b0`
- `0x140009964`

## callees

- `0x14000b65c`
- `0x14000fbf0`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x140011b64  mov     [rsp+arg_0], rbx
0x140011b69  push    rdi
0x140011b6a  sub     rsp, 20h
0x140011b6e  lea     rdx, [rsp+28h+arg_8]
0x140011b73  mov     rdi, rcx
0x140011b76  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(void)
0x140011b7b  mov     bl, [rsp+28h+arg_8]
0x140011b7f  mov     rcx, rdi
0x140011b82  and     bl, 1
0x140011b85  mov     dl, bl
0x140011b87  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140011b8c  mov     al, bl
0x140011b8e  mov     rbx, [rsp+28h+arg_0]
0x140011b93  add     rsp, 20h
0x140011b97  pop     rdi
0x140011b98  retn
```
