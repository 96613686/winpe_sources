# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800104d0`
- end: `0x18001056e`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `158`
- prototype: ``
- caller_count: `14`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010440`
- `0x18001cfe4`
- `0x18001d074`
- `0x18001d0f8`
- `0x18001d17c`
- `0x18001d208`
- `0x18001d294`
- `0x18002c740`
- `0x18002c7d0`
- `0x18002c854`
- `0x18002c8d8`
- `0x18002c95c`
- `0x18002c9e8`
- `0x18002ca74`

## callees

- `0x1800104d0`
- `0x180010574`
- `0x180010c00`
- `0x18003f010`

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
0x1800104d0  mov     rax, rsp
0x1800104d3  mov     [rax+8], rbx
0x1800104d7  push    rdi
0x1800104d8  sub     rsp, 50h
0x1800104dc  mov     r11, rcx
0x1800104df  mov     r10d, r8d
0x1800104e2  mov     ecx, [rax+38h]
0x1800104e5  mov     ebx, edx
0x1800104e7  test    ecx, ecx
0x1800104e9  jz      short loc_180010562
0x1800104eb  mov     edx, [rsp+58h+arg_28]
0x1800104f2  call    wil_details_MapReportingKind
0x1800104f7  mov     rdi, [rsp+58h+arg_20]
0x1800104ff  mov     edx, ebx
0x180010501  mov     rcx, r11
0x180010504  mov     r8b, [rdi+4]
0x180010508  mov     byte ptr [rsp+58h+var_20], r8b
0x18001050d  mov     r8d, r10d
0x180010510  mov     dword ptr [rsp+58h+var_38], eax
0x180010514  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180010519  test    eax, eax
0x18001051b  jz      short loc_180010562
0x18001051d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180010524  test    rax, rax
0x180010527  jz      short loc_180010562
0x180010529  mov     r9d, [rsp+58h+arg_28]
0x180010531  lea     rcx, [rsp+58h+arg_30]
0x180010539  mov     [rsp+58h+var_20], 1
0x180010542  xor     r8d, r8d
0x180010545  mov     [rsp+58h+var_28], 0
0x18001054a  mov     rdx, rdi
0x18001054d  mov     [rsp+58h+var_30], 0
0x180010556  mov     [rsp+58h+var_38], rcx
0x18001055b  mov     ecx, ebx
0x18001055d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010562  mov     rbx, [rsp+58h+arg_0]
0x180010567  add     rsp, 50h
0x18001056b  pop     rdi
0x18001056c  retn
```
