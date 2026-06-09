# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800085a8`
- end: `0x180008648`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `160`
- prototype: `__int64 __fastcall(wil::details *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000ac14`

## callees

- `0x180005054`
- `0x1800085a8`
- `0x180008650`
- `0x18000c610`

## pseudocode

```c
__int64 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2)
{
  int v3; // ebx
  unsigned int v4; // r8d
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF
  __int16 v8; // [rsp+4Ch] [rbp-1Ch]

  v3 = a2;
  v4 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor & 4) == 0 )
  {
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v4 = v6;
  }
  v7 = 0;
  v8 = 2;
  return wil::details::ReportUsageToService((char *)a1 + 8, 60337618, (v4 >> 10) & 1, (v4 >> 11) & 1, &v7, v3, 3);
}

```

## disassembly

```asm
0x1800085a8  mov     [rsp+arg_8], rbx
0x1800085ad  push    rdi
0x1800085ae  sub     rsp, 60h
0x1800085b2  mov     rax, cs:__security_cookie
0x1800085b9  xor     rax, rsp
0x1800085bc  mov     [rsp+68h+var_18], rax
0x1800085c1  mov     rax, cs:Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor
0x1800085c8  mov     rdi, rcx
0x1800085cb  movzx   ebx, dl
0x1800085ce  mov     r8d, [rax]
0x1800085d1  test    r8b, 4
0x1800085d5  jnz     short loc_1800085EC
0x1800085d7  lea     rdx, [rsp+68h+var_28]
0x1800085dc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(void)
0x1800085e1  mov     rdx, [rax]
0x1800085e4  mov     [rsp+68h+var_28], rdx
0x1800085e9  mov     r8d, edx
0x1800085ec  mov     r9d, r8d
0x1800085ef  mov     [rsp+68h+var_38], 3
0x1800085f7  xor     eax, eax
0x1800085f9  shr     r9d, 0Bh
0x1800085fd  mov     [rsp+68h+var_20], eax
0x180008601  lea     rcx, [rdi+8]
0x180008605  shr     r8d, 0Ah
0x180008609  lea     rax, [rsp+68h+var_20]
0x18000860e  and     r9d, 1
0x180008612  mov     [rsp+68h+var_40], ebx
0x180008616  and     r8d, 1
0x18000861a  mov     [rsp+68h+var_48], rax
0x18000861f  mov     edx, 398ADD2h
0x180008624  mov     [rsp+68h+var_1C], 2
0x18000862b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180008630  mov     rcx, [rsp+68h+var_18]
0x180008635  xor     rcx, rsp; StackCookie
0x180008638  call    __security_check_cookie
0x18000863d  mov     rbx, [rsp+68h+arg_8]
0x180008642  add     rsp, 60h
0x180008646  pop     rdi
0x180008647  retn
```
