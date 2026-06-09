# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000a6c4`
- end: `0x18000a761`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a424`
- `0x18000a4b0`
- `0x18000a534`
- `0x18000a5b8`
- `0x18000a640`
- `0x18000cb60`
- `0x18000cbec`

## callees

- `0x18000a6c4`
- `0x18000a768`
- `0x18000bc58`
- `0x180018010`

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
0x18000a6c4  mov     rax, rsp
0x18000a6c7  mov     [rax+8], rbx
0x18000a6cb  push    rdi
0x18000a6cc  sub     rsp, 50h
0x18000a6d0  mov     r11, rcx
0x18000a6d3  mov     r10d, r8d
0x18000a6d6  mov     ecx, [rax+38h]
0x18000a6d9  mov     ebx, edx
0x18000a6db  test    ecx, ecx
0x18000a6dd  jz      short loc_18000A756
0x18000a6df  mov     edx, [rsp+58h+arg_28]
0x18000a6e6  call    wil_details_MapReportingKind
0x18000a6eb  mov     rdi, [rsp+58h+arg_20]
0x18000a6f3  mov     edx, ebx
0x18000a6f5  mov     rcx, r11
0x18000a6f8  mov     r8b, [rdi+4]
0x18000a6fc  mov     byte ptr [rsp+58h+var_20], r8b
0x18000a701  mov     r8d, r10d
0x18000a704  mov     dword ptr [rsp+58h+var_38], eax
0x18000a708  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000a70d  test    eax, eax
0x18000a70f  jz      short loc_18000A756
0x18000a711  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000a718  test    rax, rax
0x18000a71b  jz      short loc_18000A756
0x18000a71d  mov     r9d, [rsp+58h+arg_28]
0x18000a725  lea     rcx, [rsp+58h+arg_30]
0x18000a72d  mov     [rsp+58h+var_20], 1
0x18000a736  xor     r8d, r8d
0x18000a739  mov     [rsp+58h+var_28], 0
0x18000a73e  mov     rdx, rdi
0x18000a741  mov     [rsp+58h+var_30], 0
0x18000a74a  mov     [rsp+58h+var_38], rcx
0x18000a74f  mov     ecx, ebx
0x18000a751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a756  mov     rbx, [rsp+58h+arg_0]
0x18000a75b  add     rsp, 50h
0x18000a75f  pop     rdi
0x18000a760  retn
```
