# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x14000760c`
- end: `0x14000769d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400056b8`

## callees

- `0x14000452c`
- `0x140007474`
- `0x14000760c`
- `0x14000a390`

## pseudocode

```c
__int64 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2)
{
  unsigned int v2; // r8d
  int v4; // edi
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF
  __int16 v8; // [rsp+4Ch] [rbp-1Ch]

  v2 = *(_DWORD *)a1;
  v4 = a2;
  if ( (*(_DWORD *)a1 & 4) == 0 )
  {
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 1;
  return wil::details::ReportUsageToService((char *)a1 + 8, 57398953, (v2 >> 10) & 1, (v2 >> 11) & 1, &v7, v4);
}

```

## disassembly

```asm
0x14000760c  mov     [rsp+arg_8], rbx
0x140007611  push    rdi
0x140007612  sub     rsp, 60h
0x140007616  mov     rax, cs:__security_cookie
0x14000761d  xor     rax, rsp
0x140007620  mov     [rsp+68h+var_18], rax
0x140007625  mov     r8d, [rcx]
0x140007628  mov     rbx, rcx
0x14000762b  movzx   edi, dl
0x14000762e  test    r8b, 4
0x140007632  jnz     short loc_140007649
0x140007634  lea     rdx, [rsp+68h+var_28]
0x140007639  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR_REVISED>::GetCachedFeatureEnabledState(void)
0x14000763e  mov     rcx, [rax]
0x140007641  mov     [rsp+68h+var_28], rcx
0x140007646  mov     r8d, ecx
0x140007649  mov     r9d, r8d
0x14000764c  mov     [rsp+68h+var_40], edi
0x140007650  xor     eax, eax
0x140007652  shr     r9d, 0Bh
0x140007656  mov     [rsp+68h+var_20], eax
0x14000765a  lea     rcx, [rbx+8]
0x14000765e  shr     r8d, 0Ah
0x140007662  lea     rax, [rsp+68h+var_20]
0x140007667  and     r9d, 1
0x14000766b  mov     [rsp+68h+var_48], rax
0x140007670  and     r8d, 1
0x140007674  mov     [rsp+68h+var_1C], 1
0x14000767b  mov     edx, 36BD6A9h
0x140007680  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140007685  mov     rcx, [rsp+68h+var_18]
0x14000768a  xor     rcx, rsp; StackCookie
0x14000768d  call    __security_check_cookie
0x140007692  mov     rbx, [rsp+68h+arg_8]
0x140007697  add     rsp, 60h
0x14000769b  pop     rdi
0x14000769c  retn
```
