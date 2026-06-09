# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1400101bc`
- end: `0x140010259`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000fbf0`
- `0x14000fc7c`
- `0x14000fd08`
- `0x14000fd8c`
- `0x14000fe10`
- `0x14000fe94`
- `0x14000ff18`
- `0x14000ffa0`
- `0x140010028`
- `0x1400100b0`
- `0x140010138`
- `0x1400180b4`

## callees

- `0x1400101bc`
- `0x140010260`
- `0x1400138f8`
- `0x14001c010`

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
0x1400101bc  mov     rax, rsp
0x1400101bf  mov     [rax+8], rbx
0x1400101c3  push    rdi
0x1400101c4  sub     rsp, 50h
0x1400101c8  mov     r11, rcx
0x1400101cb  mov     r10d, r8d
0x1400101ce  mov     ecx, [rax+38h]
0x1400101d1  mov     ebx, edx
0x1400101d3  test    ecx, ecx
0x1400101d5  jz      short loc_14001024E
0x1400101d7  mov     edx, [rsp+58h+arg_28]
0x1400101de  call    wil_details_MapReportingKind
0x1400101e3  mov     rdi, [rsp+58h+arg_20]
0x1400101eb  mov     edx, ebx
0x1400101ed  mov     rcx, r11
0x1400101f0  mov     r8b, [rdi+4]
0x1400101f4  mov     byte ptr [rsp+58h+var_20], r8b
0x1400101f9  mov     r8d, r10d
0x1400101fc  mov     dword ptr [rsp+58h+var_38], eax
0x140010200  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140010205  test    eax, eax
0x140010207  jz      short loc_14001024E
0x140010209  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140010210  test    rax, rax
0x140010213  jz      short loc_14001024E
0x140010215  mov     r9d, [rsp+58h+arg_28]
0x14001021d  lea     rcx, [rsp+58h+arg_30]
0x140010225  mov     [rsp+58h+var_20], 1
0x14001022e  xor     r8d, r8d
0x140010231  mov     [rsp+58h+var_28], 0
0x140010236  mov     rdx, rdi
0x140010239  mov     [rsp+58h+var_30], 0
0x140010242  mov     [rsp+58h+var_38], rcx
0x140010247  mov     ecx, ebx
0x140010249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001024e  mov     rbx, [rsp+58h+arg_0]
0x140010253  add     rsp, 50h
0x140010257  pop     rdi
0x140010258  retn
```
