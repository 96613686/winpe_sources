# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180009164`
- end: `0x180009201`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180008b18`
- `0x180008b9c`
- `0x180008c20`
- `0x180008ca4`
- `0x180008d28`
- `0x180008dac`
- `0x180008e38`
- `0x180008ec0`
- `0x180008f48`
- `0x180008fd0`
- `0x180009058`
- `0x1800090e0`

## callees

- `0x180009164`
- `0x180009208`
- `0x18000ba68`
- `0x180011010`

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
0x180009164  mov     rax, rsp
0x180009167  mov     [rax+8], rbx
0x18000916b  push    rdi
0x18000916c  sub     rsp, 50h
0x180009170  mov     r11, rcx
0x180009173  mov     r10d, r8d
0x180009176  mov     ecx, [rax+38h]
0x180009179  mov     ebx, edx
0x18000917b  test    ecx, ecx
0x18000917d  jz      short loc_1800091F6
0x18000917f  mov     edx, [rsp+58h+arg_28]
0x180009186  call    wil_details_MapReportingKind
0x18000918b  mov     rdi, [rsp+58h+arg_20]
0x180009193  mov     edx, ebx
0x180009195  mov     rcx, r11
0x180009198  mov     r8b, [rdi+4]
0x18000919c  mov     byte ptr [rsp+58h+var_20], r8b
0x1800091a1  mov     r8d, r10d
0x1800091a4  mov     dword ptr [rsp+58h+var_38], eax
0x1800091a8  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800091ad  test    eax, eax
0x1800091af  jz      short loc_1800091F6
0x1800091b1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800091b8  test    rax, rax
0x1800091bb  jz      short loc_1800091F6
0x1800091bd  mov     r9d, [rsp+58h+arg_28]
0x1800091c5  lea     rcx, [rsp+58h+arg_30]
0x1800091cd  mov     [rsp+58h+var_20], 1
0x1800091d6  xor     r8d, r8d
0x1800091d9  mov     [rsp+58h+var_28], 0
0x1800091de  mov     rdx, rdi
0x1800091e1  mov     [rsp+58h+var_30], 0
0x1800091ea  mov     [rsp+58h+var_38], rcx
0x1800091ef  mov     ecx, ebx
0x1800091f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f6  mov     rbx, [rsp+58h+arg_0]
0x1800091fb  add     rsp, 50h
0x1800091ff  pop     rdi
0x180009200  retn
```
