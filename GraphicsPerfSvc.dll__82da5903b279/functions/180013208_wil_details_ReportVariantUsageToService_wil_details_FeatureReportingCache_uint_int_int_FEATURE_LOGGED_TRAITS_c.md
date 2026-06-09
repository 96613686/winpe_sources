# wil::details::ReportVariantUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,uchar,uint,wil_VariantReportingKind,unsigned __int64)

- ea: `0x180013208`
- end: `0x1800132c6`
- name: `?ReportVariantUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HEIW4wil_VariantReportingKind@@_K@Z`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180013070`
- `0x18001313c`
- `0x18001ae38`

## callees

- `0x18000ff48`
- `0x180013208`
- `0x1800133e0`
- `0x180031010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportVariantUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        unsigned int a8,
        unsigned int a9)
{
  _UNKNOWN **result; // rax
  unsigned int v11; // eax
  int v12; // r9d
  int v13; // r10d
  struct wil_details_FeatureReportingCache *v14; // r11
  __int64 v15; // [rsp+30h] [rbp-28h]
  int v16; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a9 )
  {
    LOBYTE(a3) = a7;
    v11 = wil_details_MapVariantReportingKind(a9, a6, a3);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v14, a2, v13, v12, v11, a8, v15, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v16) = a7;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, 0, &a9, v16, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013208  mov     rax, rsp
0x18001320b  mov     [rax+8], rbx
0x18001320f  mov     [rax+10h], rsi
0x180013213  push    rdi
0x180013214  sub     rsp, 50h
0x180013218  mov     r11, rcx
0x18001321b  mov     r10d, r8d
0x18001321e  mov     ecx, [rax+48h]
0x180013221  mov     ebx, edx
0x180013223  test    ecx, ecx
0x180013225  jz      loc_1800132B6
0x18001322b  mov     dil, [rsp+58h+arg_30]
0x180013233  mov     edx, [rsp+58h+arg_28]
0x18001323a  mov     r8b, dil
0x18001323d  call    wil_details_MapVariantReportingKind
0x180013242  mov     rsi, [rsp+58h+arg_20]
0x18001324a  mov     r8d, r10d
0x18001324d  mov     edx, ebx
0x18001324f  mov     cl, [rsi+4]
0x180013252  mov     byte ptr [rsp+58h+var_20], cl
0x180013256  mov     ecx, [rsp+58h+arg_38]
0x18001325d  mov     dword ptr [rsp+58h+var_30], ecx
0x180013261  mov     rcx, r11
0x180013264  mov     dword ptr [rsp+58h+var_38], eax
0x180013268  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001326d  test    eax, eax
0x18001326f  jz      short loc_1800132B6
0x180013271  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180013278  test    rax, rax
0x18001327b  jz      short loc_1800132B6
0x18001327d  mov     r9d, [rsp+58h+arg_28]
0x180013285  lea     rcx, [rsp+58h+arg_40]
0x18001328d  mov     [rsp+58h+var_20], 1
0x180013296  xor     r8d, r8d
0x180013299  mov     byte ptr [rsp+58h+var_28], dil
0x18001329e  mov     rdx, rsi
0x1800132a1  mov     [rsp+58h+var_30], rcx
0x1800132a6  mov     ecx, ebx
0x1800132a8  mov     [rsp+58h+var_38], 0
0x1800132b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132b6  mov     rbx, [rsp+58h+arg_0]
0x1800132bb  mov     rsi, [rsp+58h+arg_8]
0x1800132c0  add     rsp, 50h
0x1800132c4  pop     rdi
0x1800132c5  retn
```
