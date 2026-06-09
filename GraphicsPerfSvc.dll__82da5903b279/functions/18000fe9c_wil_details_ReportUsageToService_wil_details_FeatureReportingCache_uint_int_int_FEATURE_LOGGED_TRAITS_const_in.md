# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000fe9c`
- end: `0x18000ff41`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `165`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000fbbc`
- `0x18000fc54`
- `0x18000fcec`
- `0x18000fd78`
- `0x18000fe04`
- `0x18001ac94`
- `0x18001ad20`
- `0x18001adac`
- `0x18002d3e4`

## callees

- `0x18000fe9c`
- `0x18000ff48`
- `0x180011ea0`
- `0x180031010`

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
0x18000fe9c  mov     rax, rsp
0x18000fe9f  mov     [rax+8], rbx
0x18000fea3  push    rdi
0x18000fea4  sub     rsp, 50h
0x18000fea8  mov     r11, rcx
0x18000feab  mov     r10d, r8d
0x18000feae  mov     ecx, [rax+38h]
0x18000feb1  mov     ebx, edx
0x18000feb3  test    ecx, ecx
0x18000feb5  jz      short loc_18000FF36
0x18000feb7  mov     edx, [rsp+58h+arg_28]
0x18000febe  call    wil_details_MapReportingKind
0x18000fec3  mov     rdi, [rsp+58h+arg_20]
0x18000fecb  mov     edx, ebx
0x18000fecd  mov     rcx, r11
0x18000fed0  mov     r8b, [rdi+4]
0x18000fed4  mov     byte ptr [rsp+58h+var_20], r8b
0x18000fed9  mov     r8d, r10d
0x18000fedc  mov     dword ptr [rsp+58h+var_30], 0
0x18000fee4  mov     dword ptr [rsp+58h+var_38], eax
0x18000fee8  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000feed  test    eax, eax
0x18000feef  jz      short loc_18000FF36
0x18000fef1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fef8  test    rax, rax
0x18000fefb  jz      short loc_18000FF36
0x18000fefd  mov     r9d, [rsp+58h+arg_28]
0x18000ff05  lea     rcx, [rsp+58h+arg_30]
0x18000ff0d  mov     [rsp+58h+var_20], 1
0x18000ff16  xor     r8d, r8d
0x18000ff19  mov     [rsp+58h+var_28], 0
0x18000ff1e  mov     rdx, rdi
0x18000ff21  mov     [rsp+58h+var_30], 0
0x18000ff2a  mov     [rsp+58h+var_38], rcx
0x18000ff2f  mov     ecx, ebx
0x18000ff31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff36  mov     rbx, [rsp+58h+arg_0]
0x18000ff3b  add     rsp, 50h
0x18000ff3f  pop     rdi
0x18000ff40  retn
```
