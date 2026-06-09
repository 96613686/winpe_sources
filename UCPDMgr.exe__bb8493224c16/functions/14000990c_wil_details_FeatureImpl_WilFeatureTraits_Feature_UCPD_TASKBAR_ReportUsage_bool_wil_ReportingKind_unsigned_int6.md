# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x14000990c`
- end: `0x14000999d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140005a78`

## callees

- `0x14000452c`
- `0x140009774`
- `0x14000990c`
- `0x14000a390`

## pseudocode

```c
__int64 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::ReportUsage(
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
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(a1, &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 1;
  return wil::details::ReportUsageToService((char *)a1 + 8, 47443885, (v2 >> 10) & 1, (v2 >> 11) & 1, &v7, v4);
}

```

## disassembly

```asm
0x14000990c  mov     [rsp+arg_8], rbx
0x140009911  push    rdi
0x140009912  sub     rsp, 60h
0x140009916  mov     rax, cs:__security_cookie
0x14000991d  xor     rax, rsp
0x140009920  mov     [rsp+68h+var_18], rax
0x140009925  mov     r8d, [rcx]
0x140009928  mov     rbx, rcx
0x14000992b  movzx   edi, dl
0x14000992e  test    r8b, 4
0x140009932  jnz     short loc_140009949
0x140009934  lea     rdx, [rsp+68h+var_28]
0x140009939  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_TASKBAR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_TASKBAR>::GetCachedFeatureEnabledState(void)
0x14000993e  mov     rcx, [rax]
0x140009941  mov     [rsp+68h+var_28], rcx
0x140009946  mov     r8d, ecx
0x140009949  mov     r9d, r8d
0x14000994c  mov     [rsp+68h+var_40], edi
0x140009950  xor     eax, eax
0x140009952  shr     r9d, 0Bh
0x140009956  mov     [rsp+68h+var_20], eax
0x14000995a  lea     rcx, [rbx+8]
0x14000995e  shr     r8d, 0Ah
0x140009962  lea     rax, [rsp+68h+var_20]
0x140009967  and     r9d, 1
0x14000996b  mov     [rsp+68h+var_48], rax
0x140009970  and     r8d, 1
0x140009974  mov     [rsp+68h+var_1C], 1
0x14000997b  mov     edx, 2D3EFADh
0x140009980  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140009985  mov     rcx, [rsp+68h+var_18]
0x14000998a  xor     rcx, rsp; StackCookie
0x14000998d  call    __security_check_cookie
0x140009992  mov     rbx, [rsp+68h+arg_8]
0x140009997  add     rsp, 60h
0x14000999b  pop     rdi
0x14000999c  retn
```
