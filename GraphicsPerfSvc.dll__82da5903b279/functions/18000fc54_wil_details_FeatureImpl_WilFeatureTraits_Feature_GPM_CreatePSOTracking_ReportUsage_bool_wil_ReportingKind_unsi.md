# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000fc54`
- end: `0x18000fce6`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011630`
- `0x180013b70`
- `0x1800148d0`
- `0x180015040`
- `0x1800193d4`
- `0x18001a3a4`
- `0x18001a850`
- `0x1800258a0`

## callees

- `0x18000ee60`
- `0x18000fc54`
- `0x18000fe9c`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2,
        unsigned __int8 a3,
        ...)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  unsigned int v6; // r8d
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  v4 = a3;
  v5 = a2;
  v6 = *(_DWORD *)Feature_GPM_CreatePSOTracking__descriptor;
  if ( (*(_DWORD *)Feature_GPM_CreatePSOTracking__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCachedFeatureEnabledState(
                      a1,
                      &v8);
    v6 = v8;
  }
  LODWORD(v9) = 0;
  WORD2(v9) = 3;
  return wil::details::ReportUsageToService(a1 + 8, 0x2BDD13Bu, (v6 >> 10) & 1, (v6 >> 11) & 1, (__int64)va, v5, v4);
}

```

## disassembly

```asm
0x18000fc54  mov     r11, rsp
0x18000fc57  mov     [r11+10h], rbx
0x18000fc5b  mov     [r11+18h], rsi
0x18000fc5f  mov     [r11+20h], r9
0x18000fc63  push    rdi
0x18000fc64  sub     rsp, 40h
0x18000fc68  mov     rax, cs:Feature_GPM_CreatePSOTracking__descriptor
0x18000fc6f  mov     rsi, rcx
0x18000fc72  movzx   ebx, r8b
0x18000fc76  movzx   edi, dl
0x18000fc79  mov     r8d, [rax]
0x18000fc7c  test    r8b, 4
0x18000fc80  jnz     short loc_18000FC96
0x18000fc82  lea     rdx, [r11+8]
0x18000fc86  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCachedFeatureEnabledState(void)
0x18000fc8b  mov     r9, [rax]
0x18000fc8e  mov     [rsp+48h+arg_0], r9
0x18000fc93  mov     r8d, r9d
0x18000fc96  mov     r9d, r8d
0x18000fc99  mov     [rsp+48h+var_18], ebx
0x18000fc9d  xor     eax, eax
0x18000fc9f  shr     r9d, 0Bh
0x18000fca3  mov     dword ptr [rsp+48h+arg_18], eax
0x18000fca7  lea     rcx, [rsi+8]
0x18000fcab  shr     r8d, 0Ah
0x18000fcaf  lea     rax, [rsp+48h+arg_18]
0x18000fcb4  and     r9d, 1
0x18000fcb8  mov     [rsp+48h+var_20], edi
0x18000fcbc  and     r8d, 1
0x18000fcc0  mov     [rsp+48h+var_28], rax
0x18000fcc5  mov     edx, 2BDD13Bh
0x18000fcca  mov     word ptr [rsp+48h+arg_18+4], 3
0x18000fcd1  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000fcd6  mov     rbx, [rsp+48h+arg_8]
0x18000fcdb  mov     rsi, [rsp+48h+arg_10]
0x18000fce0  add     rsp, 40h
0x18000fce4  pop     rdi
0x18000fce5  retn
```
