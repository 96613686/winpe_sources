# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::__private_IsEnabled(void)

- ea: `0x180009a28`
- end: `0x180009abf`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008ed8`
- `0x180009300`
- `0x18000a080`
- `0x18000bb10`
- `0x18000c600`
- `0x18000c754`
- `0x18000c870`
- `0x18000cf20`

## callees

- `0x1800090fc`
- `0x18000974c`
- `0x180009a28`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_ClipWindowsUpgrade__descriptor;
  if ( (*(_DWORD *)Feature_ClipWindowsUpgrade__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 1;
  wil::details::ReportUsageToService(a1 + 8, 52298135, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x180009a28  mov     [rsp+arg_10], rbx
0x180009a2d  push    rdi
0x180009a2e  sub     rsp, 40h
0x180009a32  lea     rdx, [rsp+48h+arg_0]
0x180009a37  mov     rdi, rcx
0x180009a3a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(void)
0x180009a3f  mov     rax, cs:Feature_ClipWindowsUpgrade__descriptor
0x180009a46  mov     bl, byte ptr [rsp+48h+arg_0]
0x180009a4a  and     bl, 1
0x180009a4d  mov     r8d, [rax]
0x180009a50  test    r8b, 4
0x180009a54  jnz     short loc_180009A6B
0x180009a56  lea     rdx, [rsp+48h+arg_8]
0x180009a5b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(void)
0x180009a60  mov     rcx, [rax]
0x180009a63  mov     [rsp+48h+arg_8], rcx
0x180009a68  mov     r8d, ecx
0x180009a6b  mov     r9d, r8d
0x180009a6e  movzx   edx, bl
0x180009a71  xor     eax, eax
0x180009a73  shr     r9d, 0Bh
0x180009a77  mov     [rsp+48h+arg_0], eax
0x180009a7b  lea     rcx, [rdi+8]
0x180009a7f  shr     r8d, 0Ah
0x180009a83  lea     rax, [rsp+48h+arg_0]
0x180009a88  mov     [rsp+48h+var_18], 3
0x180009a90  and     r9d, 1
0x180009a94  mov     [rsp+48h+var_20], edx
0x180009a98  and     r8d, 1
0x180009a9c  mov     edx, 31E0197h
0x180009aa1  mov     [rsp+48h+var_28], rax
0x180009aa6  mov     [rsp+48h+arg_4], 1
0x180009aad  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009ab2  mov     al, bl
0x180009ab4  mov     rbx, [rsp+48h+arg_10]
0x180009ab9  add     rsp, 40h
0x180009abd  pop     rdi
0x180009abe  retn
```
