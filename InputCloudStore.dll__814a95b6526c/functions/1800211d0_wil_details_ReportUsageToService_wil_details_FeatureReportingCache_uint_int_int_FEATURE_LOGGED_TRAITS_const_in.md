# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800211d0`
- end: `0x18002126d`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180021034`
- `0x1800210c0`
- `0x180021144`

## callees

- `0x1800211d0`
- `0x180021274`
- `0x180026904`
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
  unsigned int v9; // eax
  int v10; // r9d
  int v11; // r10d
  struct wil_details_FeatureReportingCache *v12; // r11
  __int64 v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h]
  int v15; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    v9 = wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v12, a2, v11, v10, v9, v13, v14, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v15) = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v15, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800211d0  mov     rax, rsp
0x1800211d3  mov     [rax+8], rbx
0x1800211d7  push    rdi
0x1800211d8  sub     rsp, 50h
0x1800211dc  mov     r11, rcx
0x1800211df  mov     r10d, r8d
0x1800211e2  mov     ecx, [rax+38h]
0x1800211e5  mov     ebx, edx
0x1800211e7  test    ecx, ecx
0x1800211e9  jz      short loc_180021262
0x1800211eb  mov     edx, [rsp+58h+arg_28]
0x1800211f2  call    wil_details_MapReportingKind
0x1800211f7  mov     rdi, [rsp+58h+arg_20]
0x1800211ff  mov     edx, ebx
0x180021201  mov     rcx, r11
0x180021204  mov     r8b, [rdi+4]
0x180021208  mov     byte ptr [rsp+58h+var_20], r8b
0x18002120d  mov     r8d, r10d
0x180021210  mov     dword ptr [rsp+58h+var_38], eax
0x180021214  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180021219  test    eax, eax
0x18002121b  jz      short loc_180021262
0x18002121d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180021224  test    rax, rax
0x180021227  jz      short loc_180021262
0x180021229  mov     r9d, [rsp+58h+arg_28]
0x180021231  lea     rcx, [rsp+58h+arg_30]
0x180021239  mov     [rsp+58h+var_20], 1
0x180021242  xor     r8d, r8d
0x180021245  mov     byte ptr [rsp+58h+var_28], 0
0x18002124a  mov     rdx, rdi
0x18002124d  mov     [rsp+58h+var_30], 0
0x180021256  mov     [rsp+58h+var_38], rcx
0x18002125b  mov     ecx, ebx
0x18002125d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021262  mov     rbx, [rsp+58h+arg_0]
0x180021267  add     rsp, 50h
0x18002126b  pop     rdi
0x18002126c  retn
```
