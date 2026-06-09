# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180015474`
- end: `0x18001550f`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `155`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180014f70`
- `0x180015018`
- `0x1800150b4`
- `0x180015150`
- `0x1800151ec`
- `0x180015290`
- `0x180015334`
- `0x1800153d8`
- `0x18001fc30`
- `0x1800246c4`
- `0x18002476c`
- `0x180024808`

## callees

- `0x180015474`
- `0x180015518`
- `0x180017428`
- `0x180028010`

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
0x180015474  mov     rax, rsp
0x180015477  mov     [rax+18h], rbx
0x18001547b  push    rdi
0x18001547c  sub     rsp, 50h
0x180015480  mov     rdi, [rsp+58h+arg_20]
0x180015488  mov     r11, rcx
0x18001548b  mov     ecx, [rax+38h]
0x18001548e  mov     r10d, r8d
0x180015491  mov     ebx, edx
0x180015493  test    ecx, ecx
0x180015495  jz      short loc_180015504
0x180015497  mov     edx, [rsp+58h+arg_28]
0x18001549e  call    wil_details_MapReportingKind
0x1800154a3  mov     dl, [rdi+4]
0x1800154a6  mov     r8d, r10d
0x1800154a9  mov     byte ptr [rsp+58h+var_20], dl
0x1800154ad  mov     rcx, r11
0x1800154b0  mov     edx, ebx
0x1800154b2  mov     dword ptr [rsp+58h+var_38], eax
0x1800154b6  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800154bb  test    eax, eax
0x1800154bd  jz      short loc_180015504
0x1800154bf  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800154c6  test    rax, rax
0x1800154c9  jz      short loc_180015504
0x1800154cb  mov     r9d, [rsp+58h+arg_28]
0x1800154d3  lea     rcx, [rsp+58h+arg_30]
0x1800154db  mov     [rsp+58h+var_20], 1
0x1800154e4  xor     r8d, r8d
0x1800154e7  mov     [rsp+58h+var_28], 0
0x1800154ec  mov     rdx, rdi
0x1800154ef  mov     [rsp+58h+var_30], 0
0x1800154f8  mov     [rsp+58h+var_38], rcx
0x1800154fd  mov     ecx, ebx
0x1800154ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015504  mov     rbx, [rsp+58h+arg_10]
0x180015509  add     rsp, 50h
0x18001550d  pop     rdi
0x18001550e  retn
```
