# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800076b0`
- end: `0x180007782`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `210`
- prototype: `__int64 (__fastcall *(wil::details *, __int64, char, ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800091e4`

## callees

- `0x180004b44`
- `0x1800076b0`
- `0x180007788`
- `0x180014010`

## pseudocode

```c
__int64 (__fastcall *wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::ReportUsage(
        wil::details *a1,
        __int64 a2,
        char a3,
        ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  __int64 v9; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  LOBYTE(v8) = a3;
  v4 = (unsigned __int8)a2;
  LODWORD(v5) = *(_DWORD *)Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor;
  if ( (*(_DWORD *)Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v9) = 0;
  WORD2(v9) = 2;
  v8 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     (char *)a1 + 8,
                                                                                                     a2,
                                                                                                     ((unsigned int)v5 >> 10) & 1,
                                                                                                     ((unsigned int)v5 >> 11) & 1,
                                                                                                     4 * (v4 ^ 1) + 2);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(60900037, (__int64 *)va, 0, v4, &v8, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800076b0  mov     r11, rsp
0x1800076b3  mov     [r11+10h], rbx
0x1800076b7  mov     [r11+20h], r9
0x1800076bb  mov     [r11+18h], r8b
0x1800076bf  push    rdi
0x1800076c0  sub     rsp, 50h
0x1800076c4  mov     rax, cs:Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow__descriptor
0x1800076cb  mov     rdi, rcx
0x1800076ce  movzx   ebx, dl
0x1800076d1  mov     r8d, [rax]
0x1800076d4  test    r8b, 4
0x1800076d8  jnz     short loc_1800076EB
0x1800076da  lea     rdx, [r11+8]
0x1800076de  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanProfile_Fix_Profile_TokenizeBufferOverflow>::GetCachedFeatureEnabledState(void)
0x1800076e3  mov     r8, [rax]
0x1800076e6  mov     [rsp+58h+arg_0], r8
0x1800076eb  xor     eax, eax
0x1800076ed  mov     byte ptr [rsp+58h+var_20], 2
0x1800076f2  mov     dword ptr [rsp+58h+arg_18], eax
0x1800076f6  lea     rcx, [rdi+8]
0x1800076fa  mov     r9d, r8d
0x1800076fd  mov     word ptr [rsp+58h+arg_18+4], 2
0x180007704  mov     eax, ebx
0x180007706  shr     r9d, 0Bh
0x18000770a  xor     eax, 1
0x18000770d  shr     r8d, 0Ah
0x180007711  and     r9d, 1
0x180007715  mov     [rsp+58h+arg_10], 3
0x18000771d  and     r8d, 1
0x180007721  lea     eax, ds:2[rax*4]
0x180007728  mov     dword ptr [rsp+58h+var_38], eax
0x18000772c  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180007731  test    eax, eax
0x180007733  jz      short loc_180007777
0x180007735  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000773c  test    rax, rax
0x18000773f  jz      short loc_180007777
0x180007741  mov     [rsp+58h+var_20], 1
0x18000774a  lea     rcx, [rsp+58h+arg_10]
0x18000774f  mov     [rsp+58h+var_28], 0
0x180007754  lea     rdx, [rsp+58h+arg_18]
0x180007759  mov     [rsp+58h+var_30], 0
0x180007762  mov     r9d, ebx
0x180007765  mov     [rsp+58h+var_38], rcx
0x18000776a  xor     r8d, r8d
0x18000776d  mov     ecx, 3A142C5h
0x180007772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007777  mov     rbx, [rsp+58h+arg_8]
0x18000777c  add     rsp, 50h
0x180007780  pop     rdi
0x180007781  retn
```
