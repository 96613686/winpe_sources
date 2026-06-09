# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180016330`
- end: `0x1800163cd`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015bd8`
- `0x180015c64`
- `0x180015ce8`
- `0x180015d6c`
- `0x180015df0`
- `0x180015e74`
- `0x180015ef8`
- `0x180015f7c`
- `0x180016004`
- `0x18001608c`
- `0x180016114`
- `0x18001619c`
- `0x180016224`
- `0x1800162ac`
- `0x18001f824`
- `0x18001f950`
- `0x18001f9dc`

## callees

- `0x180016330`
- `0x1800163d4`
- `0x180019e4c`
- `0x18002e010`

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
0x180016330  mov     rax, rsp
0x180016333  mov     [rax+8], rbx
0x180016337  push    rdi
0x180016338  sub     rsp, 50h
0x18001633c  mov     r11, rcx
0x18001633f  mov     r10d, r8d
0x180016342  mov     ecx, [rax+38h]
0x180016345  mov     ebx, edx
0x180016347  test    ecx, ecx
0x180016349  jz      short loc_1800163C2
0x18001634b  mov     edx, [rsp+58h+arg_28]
0x180016352  call    wil_details_MapReportingKind
0x180016357  mov     rdi, [rsp+58h+arg_20]
0x18001635f  mov     edx, ebx
0x180016361  mov     rcx, r11
0x180016364  mov     r8b, [rdi+4]
0x180016368  mov     byte ptr [rsp+58h+var_20], r8b
0x18001636d  mov     r8d, r10d
0x180016370  mov     dword ptr [rsp+58h+var_38], eax
0x180016374  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180016379  test    eax, eax
0x18001637b  jz      short loc_1800163C2
0x18001637d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180016384  test    rax, rax
0x180016387  jz      short loc_1800163C2
0x180016389  mov     r9d, [rsp+58h+arg_28]
0x180016391  lea     rcx, [rsp+58h+arg_30]
0x180016399  mov     [rsp+58h+var_20], 1
0x1800163a2  xor     r8d, r8d
0x1800163a5  mov     [rsp+58h+var_28], 0
0x1800163aa  mov     rdx, rdi
0x1800163ad  mov     [rsp+58h+var_30], 0
0x1800163b6  mov     [rsp+58h+var_38], rcx
0x1800163bb  mov     ecx, ebx
0x1800163bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c2  mov     rbx, [rsp+58h+arg_0]
0x1800163c7  add     rsp, 50h
0x1800163cb  pop     rdi
0x1800163cc  retn
```
