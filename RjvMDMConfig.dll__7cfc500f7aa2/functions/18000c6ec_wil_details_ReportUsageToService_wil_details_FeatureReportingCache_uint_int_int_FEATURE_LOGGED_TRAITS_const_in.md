# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000c6ec`
- end: `0x18000c78a`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `158`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015250`
- `0x1800152dc`
- `0x18001536c`
- `0x1800153f8`
- `0x18001547c`
- `0x180015500`
- `0x180015584`
- `0x180015608`
- `0x18001568c`
- `0x180015718`
- `0x1800157a4`
- `0x180015830`
- `0x1800158bc`
- `0x180015948`
- `0x18001745c`

## callees

- `0x18000c6ec`
- `0x18000c790`
- `0x18001261c`
- `0x18001e010`

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
0x18000c6ec  mov     rax, rsp
0x18000c6ef  mov     [rax+8], rbx
0x18000c6f3  push    rdi
0x18000c6f4  sub     rsp, 50h
0x18000c6f8  mov     r11, rcx
0x18000c6fb  mov     r10d, r8d
0x18000c6fe  mov     ecx, [rax+38h]
0x18000c701  mov     ebx, edx
0x18000c703  test    ecx, ecx
0x18000c705  jz      short loc_18000C77E
0x18000c707  mov     edx, [rsp+58h+arg_28]
0x18000c70e  call    wil_details_MapReportingKind
0x18000c713  mov     rdi, [rsp+58h+arg_20]
0x18000c71b  mov     edx, ebx
0x18000c71d  mov     rcx, r11
0x18000c720  mov     r8b, [rdi+4]
0x18000c724  mov     byte ptr [rsp+58h+var_20], r8b
0x18000c729  mov     r8d, r10d
0x18000c72c  mov     dword ptr [rsp+58h+var_38], eax
0x18000c730  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000c735  test    eax, eax
0x18000c737  jz      short loc_18000C77E
0x18000c739  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000c740  test    rax, rax
0x18000c743  jz      short loc_18000C77E
0x18000c745  mov     r9d, [rsp+58h+arg_28]
0x18000c74d  lea     rcx, [rsp+58h+arg_30]
0x18000c755  mov     [rsp+58h+var_20], 1
0x18000c75e  xor     r8d, r8d
0x18000c761  mov     [rsp+58h+var_28], 0
0x18000c766  mov     rdx, rdi
0x18000c769  mov     [rsp+58h+var_30], 0
0x18000c772  mov     [rsp+58h+var_38], rcx
0x18000c777  mov     ecx, ebx
0x18000c779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77e  mov     rbx, [rsp+58h+arg_0]
0x18000c783  add     rsp, 50h
0x18000c787  pop     rdi
0x18000c788  retn
```
