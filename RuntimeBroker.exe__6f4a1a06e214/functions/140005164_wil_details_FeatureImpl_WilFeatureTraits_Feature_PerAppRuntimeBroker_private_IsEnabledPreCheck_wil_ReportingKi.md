# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x140005164`
- end: `0x140005232`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400060d0`

## callees

- `0x140005164`
- `0x140005238`
- `0x14000548c`
- `0x14000d9a4`
- `0x140010010`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::__private_IsEnabledPreCheck(
        __int64 a1,
        char a2)
{
  unsigned int v3; // eax
  unsigned int v4; // r10d
  __int64 v5; // rdx
  char v6; // r11
  __int64 v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+30h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+60h] [rbp+8h] BYREF
  __int16 v12; // [rsp+64h] [rbp+Ch]
  int v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  LOBYTE(v13) = a2;
  if ( (*(_DWORD *)Feature_PerAppRuntimeBroker__descriptor & 4) == 0 )
    v14 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCachedFeatureEnabledState(
                       a1,
                       &v14);
  v11 = 0;
  v12 = 3;
  v13 = 3;
  v3 = wil_details_MapReportingKind(3, 1);
  if ( (unsigned int)wil::details::ReportUsageToServiceDirect(
                       (struct wil_details_FeatureReportingCache *)(a1 + 8),
                       v5,
                       (v4 >> 10) & 1,
                       (v4 >> 11) & 1,
                       v3,
                       v8,
                       v9,
                       v6)
    && g_wil_details_pfnFeatureLoggingHook )
  {
    LOBYTE(v10) = 0;
    g_wil_details_pfnFeatureLoggingHook(8482243, &v11, 0, 1, &v13, 0, v10, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x140005164  mov     byte ptr [rsp+arg_8], dl
0x140005168  push    rbx
0x140005169  sub     rsp, 50h
0x14000516d  mov     rax, cs:Feature_PerAppRuntimeBroker__descriptor
0x140005174  mov     rbx, rcx
0x140005177  mov     r10d, [rax]
0x14000517a  test    r10b, 4
0x14000517e  jz      short loc_1400051E0
0x140005180  xor     eax, eax
0x140005182  mov     [rsp+58h+arg_0], eax
0x140005186  lea     r11d, [rax+3]
0x14000518a  mov     ecx, r11d
0x14000518d  mov     [rsp+58h+arg_4], r11w
0x140005193  lea     edx, [rax+1]
0x140005196  mov     [rsp+58h+arg_8], r11d
0x14000519b  call    wil_details_MapReportingKind
0x1400051a0  mov     r9d, r10d
0x1400051a3  mov     byte ptr [rsp+58h+var_20], r11b
0x1400051a8  shr     r10d, 0Ah
0x1400051ac  lea     rcx, [rbx+8]
0x1400051b0  and     r10d, 1
0x1400051b4  shr     r9d, 0Bh
0x1400051b8  mov     r8d, r10d
0x1400051bb  mov     dword ptr [rsp+58h+var_38], eax
0x1400051bf  and     r9d, 1
0x1400051c3  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1400051c8  test    eax, eax
0x1400051ca  jz      short loc_1400051D8
0x1400051cc  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400051d3  test    rax, rax
0x1400051d6  jnz     short loc_1400051F7
0x1400051d8  mov     al, 1
0x1400051da  add     rsp, 50h
0x1400051de  pop     rbx
0x1400051df  retn
0x1400051e0  lea     rdx, [rsp+58h+arg_10]
0x1400051e5  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCachedFeatureEnabledState(void)
0x1400051ea  mov     rdx, [rax]
0x1400051ed  mov     [rsp+58h+arg_10], rdx
0x1400051f2  mov     r10d, edx
0x1400051f5  jmp     short loc_140005180
0x1400051f7  mov     [rsp+58h+var_20], 1
0x140005200  lea     rcx, [rsp+58h+arg_8]
0x140005205  mov     byte ptr [rsp+58h+var_28], 0
0x14000520a  lea     rdx, [rsp+58h+arg_0]
0x14000520f  mov     [rsp+58h+var_30], 0
0x140005218  mov     r9d, 1
0x14000521e  mov     [rsp+58h+var_38], rcx
0x140005223  xor     r8d, r8d
0x140005226  mov     ecx, 816DC3h
0x14000522b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005230  jmp     short loc_1400051D8
```
