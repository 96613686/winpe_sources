# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180048d90`
- end: `0x180048e2f`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `159`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180048d00`
- `0x18005af5c`
- `0x18005b1d4`
- `0x18005c128`
- `0x18005c1b4`
- `0x18005c240`
- `0x18005c2d0`
- `0x18005c35c`

## callees

- `0x180048d90`
- `0x180048e38`
- `0x180048ed8`
- `0x1800960c0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  _UNKNOWN **result; // rax
  unsigned int v9; // r10d
  __int64 v10; // r11
  char v11; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v10, a2, v9);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v11 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v11, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180048d90  mov     rax, rsp
0x180048d93  mov     [rax+8], rbx
0x180048d97  push    rdi
0x180048d98  sub     rsp, 50h
0x180048d9c  mov     r11, rcx
0x180048d9f  mov     r10d, r8d
0x180048da2  mov     ecx, [rax+38h]
0x180048da5  mov     ebx, edx
0x180048da7  test    ecx, ecx
0x180048da9  jz      short loc_180048E23
0x180048dab  mov     edx, [rsp+58h+arg_28]
0x180048db2  call    wil_details_MapReportingKind
0x180048db7  mov     rdi, [rsp+58h+arg_20]
0x180048dbf  mov     edx, ebx
0x180048dc1  mov     rcx, r11
0x180048dc4  mov     r8b, [rdi+4]
0x180048dc8  mov     byte ptr [rsp+58h+var_20], r8b
0x180048dcd  mov     r8d, r10d
0x180048dd0  mov     dword ptr [rsp+58h+var_38], eax
0x180048dd4  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180048dd9  test    eax, eax
0x180048ddb  jz      short loc_180048E23
0x180048ddd  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180048de4  test    rax, rax
0x180048de7  jz      short loc_180048E23
0x180048de9  mov     r9d, [rsp+58h+arg_28]
0x180048df1  lea     rcx, [rsp+58h+arg_30]
0x180048df9  mov     [rsp+58h+var_20], 1
0x180048e02  xor     r8d, r8d
0x180048e05  mov     [rsp+58h+var_28], 0
0x180048e0a  mov     rdx, rdi
0x180048e0d  mov     [rsp+58h+var_30], 0
0x180048e16  mov     [rsp+58h+var_38], rcx
0x180048e1b  mov     ecx, ebx
0x180048e1d  call    cs:__guard_dispatch_icall_fptr
0x180048e23  mov     rbx, [rsp+58h+arg_0]
0x180048e28  add     rsp, 50h
0x180048e2c  pop     rdi
0x180048e2d  retn
```
