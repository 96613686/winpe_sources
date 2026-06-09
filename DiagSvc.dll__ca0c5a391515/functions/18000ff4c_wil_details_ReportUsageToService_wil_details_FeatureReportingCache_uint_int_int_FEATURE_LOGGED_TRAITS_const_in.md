# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000ff4c`
- end: `0x18000ffe9`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f900`
- `0x18000f98c`
- `0x18000fa10`
- `0x18000fa94`
- `0x18000fb18`
- `0x18000fb9c`
- `0x18000fc20`
- `0x18000fca8`
- `0x18000fd30`
- `0x18000fdb8`
- `0x18000fe40`
- `0x18000fec8`

## callees

- `0x18000ff4c`
- `0x18000fff0`
- `0x180013708`
- `0x180027010`

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
0x18000ff4c  mov     rax, rsp
0x18000ff4f  mov     [rax+8], rbx
0x18000ff53  push    rdi
0x18000ff54  sub     rsp, 50h
0x18000ff58  mov     r11, rcx
0x18000ff5b  mov     r10d, r8d
0x18000ff5e  mov     ecx, [rax+38h]
0x18000ff61  mov     ebx, edx
0x18000ff63  test    ecx, ecx
0x18000ff65  jz      short loc_18000FFDE
0x18000ff67  mov     edx, [rsp+58h+arg_28]
0x18000ff6e  call    wil_details_MapReportingKind
0x18000ff73  mov     rdi, [rsp+58h+arg_20]
0x18000ff7b  mov     edx, ebx
0x18000ff7d  mov     rcx, r11
0x18000ff80  mov     r8b, [rdi+4]
0x18000ff84  mov     byte ptr [rsp+58h+var_20], r8b
0x18000ff89  mov     r8d, r10d
0x18000ff8c  mov     dword ptr [rsp+58h+var_38], eax
0x18000ff90  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000ff95  test    eax, eax
0x18000ff97  jz      short loc_18000FFDE
0x18000ff99  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000ffa0  test    rax, rax
0x18000ffa3  jz      short loc_18000FFDE
0x18000ffa5  mov     r9d, [rsp+58h+arg_28]
0x18000ffad  lea     rcx, [rsp+58h+arg_30]
0x18000ffb5  mov     [rsp+58h+var_20], 1
0x18000ffbe  xor     r8d, r8d
0x18000ffc1  mov     [rsp+58h+var_28], 0
0x18000ffc6  mov     rdx, rdi
0x18000ffc9  mov     [rsp+58h+var_30], 0
0x18000ffd2  mov     [rsp+58h+var_38], rcx
0x18000ffd7  mov     ecx, ebx
0x18000ffd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffde  mov     rbx, [rsp+58h+arg_0]
0x18000ffe3  add     rsp, 50h
0x18000ffe7  pop     rdi
0x18000ffe8  retn
```
