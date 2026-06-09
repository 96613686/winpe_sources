# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000ca94`
- end: `0x18000cb66`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000d248`

## callees

- `0x18000b594`
- `0x18000ca94`
- `0x18000cb6c`
- `0x18001b010`

## pseudocode

```c
__int64 (__fastcall *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::ReportUsage(
        __int64 a1,
        __int64 a2,
        char a3,
        ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  LOBYTE(v11) = a3;
  v4 = (unsigned __int8)a2;
  LODWORD(v5) = *(_DWORD *)Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(
            (wil::details *)a1,
            &v10);
    v10 = v5;
  }
  LODWORD(v12) = 0;
  WORD2(v12) = 2;
  v11 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     (struct wil_details_FeatureReportingCache *)(a1 + 8),
                                                                                                     a2,
                                                                                                     ((unsigned int)v5 >> 10) & 1,
                                                                                                     ((unsigned int)v5 >> 11) & 1,
                                                                                                     4 * (v4 ^ 1) + 2,
                                                                                                     v7,
                                                                                                     v8,
                                                                                                     2);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v9) = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(22235952, (__int64 *)va, 0, v4, &v11, 0, v9, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ca94  mov     r11, rsp
0x18000ca97  mov     [r11+10h], rbx
0x18000ca9b  mov     [r11+20h], r9
0x18000ca9f  mov     [r11+18h], r8b
0x18000caa3  push    rdi
0x18000caa4  sub     rsp, 50h
0x18000caa8  mov     rax, cs:Feature_Servicing_KdsSvc_DynamicCacheRefresh__descriptor
0x18000caaf  mov     rdi, rcx
0x18000cab2  movzx   ebx, dl
0x18000cab5  mov     r8d, [rax]
0x18000cab8  test    r8b, 4
0x18000cabc  jnz     short loc_18000CACF
0x18000cabe  lea     rdx, [r11+8]
0x18000cac2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetCachedFeatureEnabledState(void)
0x18000cac7  mov     r8, [rax]
0x18000caca  mov     [rsp+58h+arg_0], r8
0x18000cacf  xor     eax, eax
0x18000cad1  mov     byte ptr [rsp+58h+var_20], 2
0x18000cad6  mov     dword ptr [rsp+58h+arg_18], eax
0x18000cada  lea     rcx, [rdi+8]
0x18000cade  mov     r9d, r8d
0x18000cae1  mov     word ptr [rsp+58h+arg_18+4], 2
0x18000cae8  mov     eax, ebx
0x18000caea  shr     r9d, 0Bh
0x18000caee  xor     eax, 1
0x18000caf1  shr     r8d, 0Ah
0x18000caf5  and     r9d, 1
0x18000caf9  mov     [rsp+58h+arg_10], 3
0x18000cb01  and     r8d, 1
0x18000cb05  lea     eax, ds:2[rax*4]
0x18000cb0c  mov     dword ptr [rsp+58h+var_38], eax
0x18000cb10  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000cb15  test    eax, eax
0x18000cb17  jz      short loc_18000CB5B
0x18000cb19  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000cb20  test    rax, rax
0x18000cb23  jz      short loc_18000CB5B
0x18000cb25  mov     [rsp+58h+var_20], 1
0x18000cb2e  lea     rcx, [rsp+58h+arg_10]
0x18000cb33  mov     byte ptr [rsp+58h+var_28], 0
0x18000cb38  lea     rdx, [rsp+58h+arg_18]
0x18000cb3d  mov     [rsp+58h+var_30], 0
0x18000cb46  mov     r9d, ebx
0x18000cb49  mov     [rsp+58h+var_38], rcx
0x18000cb4e  xor     r8d, r8d
0x18000cb51  mov     ecx, 1534B30h
0x18000cb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5b  mov     rbx, [rsp+58h+arg_8]
0x18000cb60  add     rsp, 50h
0x18000cb64  pop     rdi
0x18000cb65  retn
```
