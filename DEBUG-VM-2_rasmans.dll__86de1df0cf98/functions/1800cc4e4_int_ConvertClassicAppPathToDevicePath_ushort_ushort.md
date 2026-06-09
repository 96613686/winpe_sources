# int_ConvertClassicAppPathToDevicePath(ushort *,ushort * *)

- ea: `0x1800cc4e4`
- end: `0x1800cc9a8`
- name: `?int_ConvertClassicAppPathToDevicePath@@YAKPEAGPEAPEAG@Z`
- size: `1220`
- prototype: `unsigned int __fastcall(LPCWSTR lpSrc, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dc964`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800a5770`
- `0x1800b72f8`
- `0x1800b81fc`
- `0x1800cc4e4`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cc6f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cc6f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cc708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cc708`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800cc7bb`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800cc7bb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cc553`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cc66f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cc553`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cc66f`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800cc876`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800cc876`

## string_xrefs

- `0x1800cc613`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc75c`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc820`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc914`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc973`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800cc606`: `int_ConvertClassicAppPathToDevicePath`
- `0x1800cc74f`: `int_ConvertClassicAppPathToDevicePath`
- `0x1800cc813`: `int_ConvertClassicAppPathToDevicePath`
- `0x1800cc850`: `int_ConvertClassicAppPathToDevicePath`
- `0x1800cc90d`: `int_ConvertClassicAppPathToDevicePath`
- `0x1800cc966`: `int_ConvertClassicAppPathToDevicePath`

## pseudocode

```c
__int64 __fastcall int_ConvertClassicAppPathToDevicePath(LPCWSTR lpSrc, unsigned __int16 **a2)
{
  WCHAR *v4; // rbp
  DWORD v5; // eax
  DWORD v6; // ebx
  WCHAR *v7; // r14
  DWORD LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // rcx
  DWORD v13; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rax
  unsigned __int64 v16; // rdx
  int v17; // eax
  int v18; // edi
  int v19; // eax
  DWORD v21; // eax
  WCHAR DeviceName[2]; // [rsp+20h] [rbp-48h] BYREF
  __int16 v24; // [rsp+24h] [rbp-44h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 383, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  *(_DWORD *)DeviceName = 0;
  v24 = 0;
  v4 = 0;
  v5 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v6 = v5;
  if ( !v5 )
  {
    v7 = 0;
    LastError = GetLastError();
    v9 = LastError;
    if ( !LastError )
      goto LABEL_71;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 384, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3839;
    goto LABEL_68;
  }
  v11 = (WCHAR *)VpnAlloc(2LL * v5);
  v7 = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 385, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3847,
        "int_ConvertClassicAppPathToDevicePath");
    v9 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 386, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3849;
    goto LABEL_22;
  }
  if ( !ExpandEnvironmentStringsW(lpSrc, v11, v6) )
  {
    v13 = GetLastError();
    v9 = v13;
    if ( !v13 )
      goto LABEL_71;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 387, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v13);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3855;
    goto LABEL_68;
  }
  if ( v7[1] != 58 )
  {
    v9 = 3;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 392, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 3);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3891;
    goto LABEL_68;
  }
  DeviceName[0] = *v7;
  DeviceName[1] = v7[1];
  v24 = 0;
  ProcessHeap = GetProcessHeap();
  v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  v4 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 388, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3870,
        "int_ConvertClassicAppPathToDevicePath");
    v9 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 389, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3872;
LABEL_22:
    v12 = 14;
LABEL_69:
    TraceVpnWppErrorW32Impl(
      v12,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v10,
      "int_ConvertClassicAppPathToDevicePath");
LABEL_70:
    MprCommonFree(v4);
    goto LABEL_71;
  }
  if ( !QueryDosDeviceW(DeviceName, v15, 0x104u) )
  {
    v21 = GetLastError();
    v9 = v21;
    if ( !v21 )
      goto LABEL_71;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 391, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v21);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_70;
    v10 = 3885;
LABEL_68:
    v12 = v9;
    goto LABEL_69;
  }
  v9 = 0;
  v17 = StringCchCatW(v4, v16, v7 + 2);
  v18 = v17;
  if ( v17 >= 0 )
    goto LABEL_56;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 390, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v17);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      (unsigned int)v18,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      3877,
      "int_ConvertClassicAppPathToDevicePath");
  v19 = (v18 >> 16) & 0x1FFF;
  if ( v19 == 7 ? (unsigned __int16)v18 : v18 )
  {
    if ( v19 == 7 )
      v18 = (unsigned __int16)v18;
    VpnReportError("int_ConvertClassicAppPathToDevicePath", "StringCchCat for AppName", (unsigned int)v18);
  }
  else
  {
LABEL_56:
    CharLowerBuffW(v4, 0x104u);
    *a2 = v4;
  }
LABEL_71:
  MprCommonFree(v7);
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 393, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v9,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3903,
        "int_ConvertClassicAppPathToDevicePath");
  }
  return v9;
}

```

## disassembly

```asm
0x1800cc4e4  mov     [rsp+arg_10], rbx
0x1800cc4e9  push    rbp
0x1800cc4ea  push    rsi
0x1800cc4eb  push    rdi
0x1800cc4ec  push    r12
0x1800cc4ee  push    r13
0x1800cc4f0  push    r14
0x1800cc4f2  push    r15
0x1800cc4f4  sub     rsp, 30h
0x1800cc4f8  mov     rax, cs:__security_cookie
0x1800cc4ff  xor     rax, rsp
0x1800cc502  mov     [rsp+68h+var_40], rax
0x1800cc507  mov     rsi, rdx
0x1800cc50a  mov     rdi, rcx
0x1800cc50d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc514  lea     r15, WPP_GLOBAL_Control
0x1800cc51b  lea     r13, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800cc522  cmp     rcx, r15
0x1800cc525  jz      short loc_1800CC53E
0x1800cc527  test    byte ptr [rcx+1Ch], 8
0x1800cc52b  jz      short loc_1800CC53E
0x1800cc52d  mov     rcx, [rcx+10h]
0x1800cc531  mov     edx, 17Fh
0x1800cc536  mov     r8, r13
0x1800cc539  call    WPP_SF_
0x1800cc53e  xor     eax, eax
0x1800cc540  xor     r8d, r8d; nSize
0x1800cc543  xor     edx, edx; lpDst
0x1800cc545  mov     dword ptr [rsp+68h+DeviceName], eax
0x1800cc549  mov     rcx, rdi; lpSrc
0x1800cc54c  mov     [rsp+68h+var_44], ax
0x1800cc551  xor     ebp, ebp
0x1800cc553  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cc559  mov     ebx, eax
0x1800cc55b  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800cc562  test    eax, eax
0x1800cc564  jnz     short loc_1800CC5BA
0x1800cc566  xor     r14d, r14d
0x1800cc569  call    cs:__imp_GetLastError
0x1800cc56f  mov     ebx, eax
0x1800cc571  test    eax, eax
0x1800cc573  jz      loc_1800CC928
0x1800cc579  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc580  cmp     rcx, r15
0x1800cc583  jz      short loc_1800CC59F
0x1800cc585  test    byte ptr [rcx+1Ch], 1
0x1800cc589  jz      short loc_1800CC59F
0x1800cc58b  mov     rcx, [rcx+10h]
0x1800cc58f  mov     edx, 180h
0x1800cc594  mov     r9d, eax
0x1800cc597  mov     r8, r13
0x1800cc59a  call    WPP_SF_d
0x1800cc59f  mov     rcx, r12
0x1800cc5a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc5a7  test    al, al
0x1800cc5a9  jz      loc_1800CC920
0x1800cc5af  mov     r8d, 0EFFh
0x1800cc5b5  jmp     loc_1800CC90B
0x1800cc5ba  mov     rcx, rbx
0x1800cc5bd  add     rcx, rcx
0x1800cc5c0  call    VpnAlloc
0x1800cc5c5  mov     r14, rax
0x1800cc5c8  test    rax, rax
0x1800cc5cb  jnz     loc_1800CC666
0x1800cc5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc5d8  lea     edi, [rax+0Eh]
0x1800cc5db  cmp     rcx, r15
0x1800cc5de  jz      short loc_1800CC5FA
0x1800cc5e0  test    byte ptr [rcx+1Ch], 1
0x1800cc5e4  jz      short loc_1800CC5FA
0x1800cc5e6  mov     rcx, [rcx+10h]
0x1800cc5ea  mov     edx, 181h
0x1800cc5ef  mov     r9d, edi
0x1800cc5f2  mov     r8, r13
0x1800cc5f5  call    WPP_SF_d
0x1800cc5fa  mov     rcx, r12
0x1800cc5fd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc602  test    al, al
0x1800cc604  jz      short loc_1800CC621
0x1800cc606  lea     r9, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc60d  mov     r8d, 0F07h
0x1800cc613  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc61a  mov     ecx, edi
0x1800cc61c  call    TraceVpnWppErrorW32Impl
0x1800cc621  mov     ebx, edi
0x1800cc623  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc62a  cmp     rcx, r15
0x1800cc62d  jz      short loc_1800CC649
0x1800cc62f  test    byte ptr [rcx+1Ch], 1
0x1800cc633  jz      short loc_1800CC649
0x1800cc635  mov     rcx, [rcx+10h]
0x1800cc639  mov     edx, 182h
0x1800cc63e  mov     r9d, edi
0x1800cc641  mov     r8, r13
0x1800cc644  call    WPP_SF_d
0x1800cc649  mov     rcx, r12
0x1800cc64c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc651  test    al, al
0x1800cc653  jz      loc_1800CC920
0x1800cc659  mov     r8d, 0F09h
0x1800cc65f  mov     ecx, edi
0x1800cc661  jmp     loc_1800CC90D
0x1800cc666  mov     r8d, ebx; nSize
0x1800cc669  mov     rdx, r14; lpDst
0x1800cc66c  mov     rcx, rdi; lpSrc
0x1800cc66f  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cc675  test    eax, eax
0x1800cc677  jnz     short loc_1800CC6CA
0x1800cc679  call    cs:__imp_GetLastError
0x1800cc67f  mov     ebx, eax
0x1800cc681  test    eax, eax
0x1800cc683  jz      loc_1800CC928
0x1800cc689  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc690  cmp     rcx, r15
0x1800cc693  jz      short loc_1800CC6AF
0x1800cc695  test    byte ptr [rcx+1Ch], 1
0x1800cc699  jz      short loc_1800CC6AF
0x1800cc69b  mov     rcx, [rcx+10h]
0x1800cc69f  mov     edx, 183h
0x1800cc6a4  mov     r9d, eax
0x1800cc6a7  mov     r8, r13
0x1800cc6aa  call    WPP_SF_d
0x1800cc6af  mov     rcx, r12
0x1800cc6b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc6b7  test    al, al
0x1800cc6b9  jz      loc_1800CC920
0x1800cc6bf  mov     r8d, 0F0Fh
0x1800cc6c5  jmp     loc_1800CC90B
0x1800cc6ca  mov     eax, 3Ah ; ':'
0x1800cc6cf  cmp     ax, [r14+2]
0x1800cc6d4  jnz     loc_1800CC8CE
0x1800cc6da  movzx   eax, word ptr [r14]
0x1800cc6de  mov     [rsp+68h+DeviceName], ax
0x1800cc6e3  movzx   eax, word ptr [r14+2]
0x1800cc6e8  mov     [rsp+68h+DeviceName+2], ax
0x1800cc6ed  xor     eax, eax
0x1800cc6ef  mov     [rsp+68h+var_44], ax
0x1800cc6f4  call    cs:__imp_GetProcessHeap
0x1800cc6fa  mov     edx, 8; dwFlags
0x1800cc6ff  mov     r8d, 208h; dwBytes
0x1800cc705  mov     rcx, rax; hHeap
0x1800cc708  call    cs:__imp_HeapAlloc
0x1800cc70e  mov     rbp, rax
0x1800cc711  test    rax, rax
0x1800cc714  jnz     loc_1800CC7AD
0x1800cc71a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc721  lea     edi, [rax+0Eh]
0x1800cc724  cmp     rcx, r15
0x1800cc727  jz      short loc_1800CC743
0x1800cc729  test    byte ptr [rcx+1Ch], 1
0x1800cc72d  jz      short loc_1800CC743
0x1800cc72f  mov     rcx, [rcx+10h]
0x1800cc733  mov     edx, 184h
0x1800cc738  mov     r9d, edi
0x1800cc73b  mov     r8, r13
0x1800cc73e  call    WPP_SF_d
0x1800cc743  mov     rcx, r12
0x1800cc746  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc74b  test    al, al
0x1800cc74d  jz      short loc_1800CC76A
0x1800cc74f  lea     r9, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc756  mov     r8d, 0F1Eh
0x1800cc75c  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc763  mov     ecx, edi
0x1800cc765  call    TraceVpnWppErrorW32Impl
0x1800cc76a  mov     ebx, edi
0x1800cc76c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc773  cmp     rcx, r15
0x1800cc776  jz      short loc_1800CC792
0x1800cc778  test    byte ptr [rcx+1Ch], 1
0x1800cc77c  jz      short loc_1800CC792
0x1800cc77e  mov     rcx, [rcx+10h]
0x1800cc782  mov     edx, 185h
0x1800cc787  mov     r9d, edi
0x1800cc78a  mov     r8, r13
0x1800cc78d  call    WPP_SF_d
0x1800cc792  mov     rcx, r12
0x1800cc795  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc79a  test    al, al
0x1800cc79c  jz      loc_1800CC920
0x1800cc7a2  mov     r8d, 0F20h
0x1800cc7a8  jmp     loc_1800CC65F
0x1800cc7ad  mov     r8d, 104h; ucchMax
0x1800cc7b3  lea     rcx, [rsp+68h+DeviceName]; lpDeviceName
0x1800cc7b8  mov     rdx, rbp; lpTargetPath
0x1800cc7bb  call    cs:__imp_QueryDosDeviceW
0x1800cc7c1  test    eax, eax
0x1800cc7c3  jz      loc_1800CC884
0x1800cc7c9  lea     r8, [r14+4]; unsigned __int16 *
0x1800cc7cd  mov     rcx, rbp; unsigned __int16 *
0x1800cc7d0  xor     ebx, ebx
0x1800cc7d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800cc7d7  mov     edi, eax
0x1800cc7d9  test    eax, eax
0x1800cc7db  jns     loc_1800CC86E
0x1800cc7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc7e8  cmp     rcx, r15
0x1800cc7eb  jz      short loc_1800CC807
0x1800cc7ed  test    byte ptr [rcx+1Ch], 1
0x1800cc7f1  jz      short loc_1800CC807
0x1800cc7f3  mov     rcx, [rcx+10h]
0x1800cc7f7  mov     edx, 186h
0x1800cc7fc  mov     r9d, eax
0x1800cc7ff  mov     r8, r13
0x1800cc802  call    WPP_SF_d
0x1800cc807  mov     rcx, r12
0x1800cc80a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc80f  test    al, al
0x1800cc811  jz      short loc_1800CC82E
0x1800cc813  lea     r9, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc81a  mov     r8d, 0F25h
0x1800cc820  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc827  mov     ecx, edi
0x1800cc829  call    TraceVpnWppErrorHRImpl
0x1800cc82e  mov     eax, edi
0x1800cc830  sar     eax, 10h
0x1800cc833  and     eax, 1FFFh
0x1800cc838  cmp     eax, 7
0x1800cc83b  jnz     short loc_1800CC844
0x1800cc83d  movzx   ecx, di
0x1800cc840  mov     edx, ecx
0x1800cc842  jmp     short loc_1800CC849
0x1800cc844  mov     ecx, edi
0x1800cc846  movzx   edx, di
0x1800cc849  test    ecx, ecx
0x1800cc84b  jz      short loc_1800CC86E
0x1800cc84d  cmp     eax, 7
0x1800cc850  lea     rcx, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc857  cmovz   edi, edx
0x1800cc85a  lea     rdx, aStringcchcatFo; "StringCchCat for AppName"
0x1800cc861  mov     r8d, edi
0x1800cc864  call    VpnReportError
0x1800cc869  jmp     loc_1800CC928
0x1800cc86e  mov     edx, 104h; cchLength
0x1800cc873  mov     rcx, rbp; lpsz
0x1800cc876  call    cs:__imp_CharLowerBuffW
0x1800cc87c  mov     [rsi], rbp
0x1800cc87f  jmp     loc_1800CC928
0x1800cc884  call    cs:__imp_GetLastError
0x1800cc88a  mov     ebx, eax
0x1800cc88c  test    eax, eax
0x1800cc88e  jz      loc_1800CC928
0x1800cc894  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc89b  cmp     rcx, r15
0x1800cc89e  jz      short loc_1800CC8BA
0x1800cc8a0  test    byte ptr [rcx+1Ch], 1
0x1800cc8a4  jz      short loc_1800CC8BA
0x1800cc8a6  mov     rcx, [rcx+10h]
0x1800cc8aa  mov     edx, 187h
0x1800cc8af  mov     r9d, eax
0x1800cc8b2  mov     r8, r13
0x1800cc8b5  call    WPP_SF_d
0x1800cc8ba  mov     rcx, r12
0x1800cc8bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc8c2  test    al, al
0x1800cc8c4  jz      short loc_1800CC920
0x1800cc8c6  mov     r8d, 0F2Dh
0x1800cc8cc  jmp     short loc_1800CC90B
0x1800cc8ce  mov     ebx, 3
0x1800cc8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc8da  cmp     rcx, r15
0x1800cc8dd  jz      short loc_1800CC8F9
0x1800cc8df  test    byte ptr [rcx+1Ch], 1
0x1800cc8e3  jz      short loc_1800CC8F9
0x1800cc8e5  mov     rcx, [rcx+10h]
0x1800cc8e9  mov     edx, 188h
0x1800cc8ee  mov     r9d, ebx
0x1800cc8f1  mov     r8, r13
0x1800cc8f4  call    WPP_SF_d
0x1800cc8f9  mov     rcx, r12
0x1800cc8fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc901  test    al, al
0x1800cc903  jz      short loc_1800CC920
0x1800cc905  mov     r8d, 0F33h
0x1800cc90b  mov     ecx, ebx
0x1800cc90d  lea     r9, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc914  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800cc91b  call    TraceVpnWppErrorW32Impl
0x1800cc920  mov     rcx, rbp; lpMem
0x1800cc923  call    MprCommonFree
0x1800cc928  mov     rcx, r14; lpMem
0x1800cc92b  call    MprCommonFree
0x1800cc930  test    ebx, ebx
0x1800cc932  jns     short loc_1800CC981
0x1800cc934  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cc93b  cmp     rcx, r15
0x1800cc93e  jz      short loc_1800CC95A
0x1800cc940  test    byte ptr [rcx+1Ch], 8
0x1800cc944  jz      short loc_1800CC95A
0x1800cc946  mov     rcx, [rcx+10h]
0x1800cc94a  mov     edx, 189h
0x1800cc94f  mov     r9d, ebx
0x1800cc952  mov     r8, r13
0x1800cc955  call    WPP_SF_d
0x1800cc95a  mov     rcx, r12
0x1800cc95d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800cc962  test    al, al
0x1800cc964  jz      short loc_1800CC981
0x1800cc966  lea     r9, aIntConvertclas; "int_ConvertClassicAppPathToDevicePath"
0x1800cc96d  mov     r8d, 0F3Fh
  ... truncated ...
```
