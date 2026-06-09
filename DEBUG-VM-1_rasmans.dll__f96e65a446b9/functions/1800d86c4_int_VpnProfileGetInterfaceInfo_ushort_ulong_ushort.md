# int_VpnProfileGetInterfaceInfo(ushort *,ulong *,ushort *)

- ea: `0x1800d86c4`
- end: `0x1800d8b65`
- name: `?int_VpnProfileGetInterfaceInfo@@YAKPEAGPEAK0@Z`
- size: `1185`
- prototype: `unsigned int __fastcall(wchar_t *String1, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bfad0`

## callees

- `0x180002f4c`
- `0x180005e34`
- `0x180005e74`
- `0x18000bf70`
- `0x18000e5f0`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800d86c4`
- `0x1800e0d0c`
- `0x1800e2464`
- `0x1800e2578`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800d8853`
- `msvcrt!_wcsicmp` at `0x1800d8853`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d873c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d873c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8a78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d8a78`

## string_xrefs

- `0x1800d880e`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d8951`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d89f0`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d8a4e`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d8ae3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d8b3d`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`

## pseudocode

```c
__int64 __fastcall int_VpnProfileGetInterfaceInfo(wchar_t *String1, unsigned int *a2, unsigned __int16 *a3)
{
  const char *v5; // r9
  ULONG v6; // eax
  int v7; // edi
  IP_ADAPTER_ADDRESSES_LH *v8; // r15
  ULONG AdaptersAddresses_0; // ebx
  struct _LIST_ENTRY *v10; // rcx
  int v11; // edi
  char v12; // r14
  IP_ADAPTER_ADDRESSES_LH *v13; // rsi
  int v14; // eax
  int v15; // r8d
  __int64 v16; // r9
  struct _LIST_ENTRY *v17; // rcx
  unsigned int IfIndex; // eax
  unsigned __int16 *v19; // rax
  int v20; // eax
  ULONG SizePointer; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v5 = (const char *)String1;
    if ( !String1 )
      v5 = L"<NULL>";
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 103, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v5);
  }
  v6 = 15000;
  v7 = 0;
  for ( SizePointer = 15000; ; v6 = SizePointer )
  {
    v8 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, v6);
    if ( !v8 )
      break;
    AdaptersAddresses_0 = GetAdaptersAddresses_0(0, 0, 0, v8, &SizePointer);
    if ( AdaptersAddresses_0 != 111 )
    {
      if ( AdaptersAddresses_0 )
      {
        v10 = WPP_GLOBAL_Control;
LABEL_16:
        v11 = 0;
        if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 1) != 0 )
          WPP_SF_d(v10[1].Flink, 106, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, AdaptersAddresses_0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            AdaptersAddresses_0,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            1178,
            "int_VpnProfileGetInterfaceInfo");
        if ( v8 )
        {
LABEL_58:
          LocalFree(v8);
          if ( v11 < 0 )
          {
            AdaptersAddresses_0 = (unsigned __int16)v11;
            if ( (v11 & 0x1FFF0000) != 0x70000 )
              AdaptersAddresses_0 = v11;
          }
        }
        if ( (AdaptersAddresses_0 & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              112,
              &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              AdaptersAddresses_0);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorHRImpl(
              AdaptersAddresses_0,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1244,
              "int_VpnProfileGetInterfaceInfo");
        }
        return AdaptersAddresses_0;
      }
      v12 = 0;
      v13 = v8;
      while ( 1 )
      {
        v14 = VpnStringCopy(v13->Description);
        v11 = v14;
        if ( v14 < 0 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              107,
              &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              (unsigned int)v14);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorHRImpl(
              (unsigned int)v11,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1185,
              "int_VpnProfileGetInterfaceInfo");
          goto LABEL_58;
        }
        if ( !_wcsicmp(String1, 0) )
          break;
        MprCommonFree(0);
        v13 = v13->Next;
        if ( !v13 )
          goto LABEL_29;
      }
      v12 = 1;
LABEL_29:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        LOBYTE(v16) = v12;
        WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 108, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v16);
        v17 = WPP_GLOBAL_Control;
      }
      if ( v12 )
      {
        if ( a2 )
        {
          IfIndex = v13->IfIndex;
          if ( !IfIndex )
            IfIndex = v13->Ipv6IfIndex;
          *a2 = IfIndex;
          v17 = WPP_GLOBAL_Control;
        }
        v19 = a3;
        if ( a3 )
        {
          v20 = VpnStringCopyAtoW(v13->AdapterName);
          v11 = v20;
          if ( v20 < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                109,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)v20);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorHRImpl(
                (unsigned int)v11,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                1212,
                "int_VpnProfileGetInterfaceInfo");
            goto LABEL_58;
          }
          v17 = WPP_GLOBAL_Control;
          v19 = a3;
        }
        if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v17[1].Blink) & 4) != 0 )
          WPP_SF_SdS(v17[1].Flink, (unsigned int)&WPP_GLOBAL_Control, v15, (_DWORD)String1, *a2, (__int64)v19);
      }
      else
      {
        AdaptersAddresses_0 = 1168;
        if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v17[1].Blink) & 1) != 0 )
          WPP_SF_d(v17[1].Flink, 111, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            1168,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            1221,
            "int_VpnProfileGetInterfaceInfo");
      }
      goto LABEL_58;
    }
    LocalFree(v8);
    v8 = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 105, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 111, v7);
      v10 = WPP_GLOBAL_Control;
    }
    if ( (unsigned int)++v7 >= 3 )
      goto LABEL_16;
  }
  AdaptersAddresses_0 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 104, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      1160,
      "int_VpnProfileGetInterfaceInfo");
  return AdaptersAddresses_0;
}

```

## disassembly

```asm
0x1800d86c4  mov     [rsp+arg_0], rbx
0x1800d86c9  mov     [rsp+arg_10], r8
0x1800d86ce  push    rbp
0x1800d86cf  push    rsi
0x1800d86d0  push    rdi
0x1800d86d1  push    r12
0x1800d86d3  push    r13
0x1800d86d5  push    r14
0x1800d86d7  push    r15
0x1800d86d9  sub     rsp, 40h
0x1800d86dd  mov     r13, rdx
0x1800d86e0  mov     r12, rcx
0x1800d86e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d86ea  lea     rbp, WPP_GLOBAL_Control
0x1800d86f1  cmp     rcx, rbp
0x1800d86f4  jz      short loc_1800D8722
0x1800d86f6  test    byte ptr [rcx+1Ch], 8
0x1800d86fa  jz      short loc_1800D8722
0x1800d86fc  mov     rcx, [rcx+10h]
0x1800d8700  lea     rax, aNull_5; "<NULL>"
0x1800d8707  test    r12, r12
0x1800d870a  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8711  mov     r9, r12
0x1800d8714  mov     edx, 67h ; 'g'
0x1800d8719  cmovz   r9, rax
0x1800d871d  call    WPP_SF_S
0x1800d8722  mov     eax, 3A98h
0x1800d8727  xor     edi, edi
0x1800d8729  mov     [rsp+78h+arg_18], eax
0x1800d8730  mov     [rsp+78h+String2], rdi
0x1800d8735  mov     edx, eax; uBytes
0x1800d8737  mov     ecx, 40h ; '@'; uFlags
0x1800d873c  call    cs:__imp_LocalAlloc
0x1800d8742  mov     r15, rax
0x1800d8745  test    rax, rax
0x1800d8748  jz      loc_1800D8AF3
0x1800d874e  lea     rax, [rsp+78h+arg_18]
0x1800d8756  mov     r9, r15; AdapterAddresses
0x1800d8759  xor     r8d, r8d; Reserved
0x1800d875c  mov     [rsp+78h+SizePointer], rax; SizePointer
0x1800d8761  xor     edx, edx; Flags
0x1800d8763  xor     ecx, ecx; Family
0x1800d8765  call    GetAdaptersAddresses_0
0x1800d876a  mov     ebx, eax
0x1800d876c  cmp     eax, 6Fh ; 'o'
0x1800d876f  jnz     short loc_1800D87C3
0x1800d8771  mov     rcx, r15; hMem
0x1800d8774  call    cs:__imp_LocalFree
0x1800d877a  xor     r15d, r15d
0x1800d877d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8784  cmp     rcx, rbp
0x1800d8787  jz      short loc_1800D87B0
0x1800d8789  test    byte ptr [rcx+1Ch], 4
0x1800d878d  jz      short loc_1800D87B0
0x1800d878f  mov     rcx, [rcx+10h]
0x1800d8793  lea     edx, [rbx-6]
0x1800d8796  mov     r9d, ebx
0x1800d8799  mov     dword ptr [rsp+78h+SizePointer], edi
0x1800d879d  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d87a4  call    WPP_SF_Dd
0x1800d87a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d87b0  inc     edi
0x1800d87b2  cmp     edi, 3
0x1800d87b5  jnb     short loc_1800D87CE
0x1800d87b7  mov     eax, [rsp+78h+arg_18]
0x1800d87be  jmp     loc_1800D8735
0x1800d87c3  test    ebx, ebx
0x1800d87c5  jz      short loc_1800D882A
0x1800d87c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d87ce  xor     edi, edi
0x1800d87d0  cmp     rcx, rbp
0x1800d87d3  jz      short loc_1800D87F1
0x1800d87d5  test    byte ptr [rcx+1Ch], 1
0x1800d87d9  jz      short loc_1800D87F1
0x1800d87db  mov     rcx, [rcx+10h]
0x1800d87df  lea     edx, [rdi+6Ah]
0x1800d87e2  mov     r9d, ebx
0x1800d87e5  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d87ec  call    WPP_SF_d
0x1800d87f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d87f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d87fd  test    al, al
0x1800d87ff  jz      short loc_1800D881C
0x1800d8801  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d8808  mov     r8d, 49Ah
0x1800d880e  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d8815  mov     ecx, ebx
0x1800d8817  call    TraceVpnWppErrorW32Impl
0x1800d881c  test    r15, r15
0x1800d881f  jz      loc_1800D8A94
0x1800d8825  jmp     loc_1800D8A75
0x1800d882a  xor     r14b, r14b
0x1800d882d  mov     rsi, r15
0x1800d8830  mov     rcx, [rsi+40h]; Src
0x1800d8834  lea     rdx, [rsp+78h+String2]
0x1800d8839  call    VpnStringCopy
0x1800d883e  mov     edi, eax
0x1800d8840  test    eax, eax
0x1800d8842  js      loc_1800D8A00
0x1800d8848  mov     rbp, [rsp+78h+String2]
0x1800d884d  mov     rcx, r12; String1
0x1800d8850  mov     rdx, rbp; String2
0x1800d8853  call    cs:__imp__wcsicmp
0x1800d8859  test    eax, eax
0x1800d885b  jz      short loc_1800D8877
0x1800d885d  mov     rcx, rbp; lpMem
0x1800d8860  call    MprCommonFree
0x1800d8865  mov     rsi, [rsi+8]
0x1800d8869  xor     ebp, ebp
0x1800d886b  mov     [rsp+78h+String2], rbp
0x1800d8870  test    rsi, rsi
0x1800d8873  jnz     short loc_1800D8830
0x1800d8875  jmp     short loc_1800D887A
0x1800d8877  mov     r14b, 1
0x1800d887a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8881  lea     rax, WPP_GLOBAL_Control
0x1800d8888  cmp     rcx, rax
0x1800d888b  jz      short loc_1800D88B9
0x1800d888d  test    byte ptr [rcx+1Ch], 4
0x1800d8891  jz      short loc_1800D88B9
0x1800d8893  mov     rcx, [rcx+10h]
0x1800d8897  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d889e  mov     edx, 6Ch ; 'l'
0x1800d88a3  mov     r9b, r14b
0x1800d88a6  call    WPP_SF_c
0x1800d88ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d88b2  lea     rax, WPP_GLOBAL_Control
0x1800d88b9  test    r14b, r14b
0x1800d88bc  jz      loc_1800D89AB
0x1800d88c2  test    r13, r13
0x1800d88c5  jz      short loc_1800D88DC
0x1800d88c7  mov     eax, [rsi+4]
0x1800d88ca  test    eax, eax
0x1800d88cc  jnz     short loc_1800D88D1
0x1800d88ce  mov     eax, [rsi+6Ch]
0x1800d88d1  mov     [r13+0], eax
0x1800d88d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d88dc  mov     rax, [rsp+78h+arg_10]
0x1800d88e4  test    rax, rax
0x1800d88e7  jz      loc_1800D8973
0x1800d88ed  mov     rcx, [rsi+10h]; lpMultiByteStr
0x1800d88f1  mov     r8, rax
0x1800d88f4  call    VpnStringCopyAtoW
0x1800d88f9  mov     edi, eax
0x1800d88fb  test    eax, eax
0x1800d88fd  jns     short loc_1800D8964
0x1800d88ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8906  lea     rdx, WPP_GLOBAL_Control
0x1800d890d  cmp     rcx, rdx
0x1800d8910  jz      short loc_1800D8930
0x1800d8912  test    byte ptr [rcx+1Ch], 1
0x1800d8916  jz      short loc_1800D8930
0x1800d8918  mov     rcx, [rcx+10h]
0x1800d891c  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8923  mov     edx, 6Dh ; 'm'
0x1800d8928  mov     r9d, eax
0x1800d892b  call    WPP_SF_d
0x1800d8930  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d8937  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d893c  test    al, al
0x1800d893e  jz      loc_1800D8A61
0x1800d8944  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d894b  mov     r8d, 4BCh
0x1800d8951  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d8958  mov     ecx, edi
0x1800d895a  call    TraceVpnWppErrorHRImpl
0x1800d895f  jmp     loc_1800D8A61
0x1800d8964  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d896b  mov     rax, [rsp+78h+arg_10]
0x1800d8973  lea     rdx, WPP_GLOBAL_Control
0x1800d897a  cmp     rcx, rdx
0x1800d897d  jz      loc_1800D8A61
0x1800d8983  test    byte ptr [rcx+1Ch], 4
0x1800d8987  jz      loc_1800D8A61
0x1800d898d  mov     rcx, [rcx+10h]
0x1800d8991  mov     r9, r12
0x1800d8994  mov     [rsp+78h+var_50], rax
0x1800d8999  mov     eax, [r13+0]
0x1800d899d  mov     dword ptr [rsp+78h+SizePointer], eax
0x1800d89a1  call    WPP_SF_SdS
0x1800d89a6  jmp     loc_1800D8A61
0x1800d89ab  mov     ebx, 490h
0x1800d89b0  cmp     rcx, rax
0x1800d89b3  jz      short loc_1800D89D3
0x1800d89b5  test    byte ptr [rcx+1Ch], 1
0x1800d89b9  jz      short loc_1800D89D3
0x1800d89bb  mov     rcx, [rcx+10h]
0x1800d89bf  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d89c6  mov     edx, 6Fh ; 'o'
0x1800d89cb  mov     r9d, ebx
0x1800d89ce  call    WPP_SF_d
0x1800d89d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d89da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d89df  test    al, al
0x1800d89e1  jz      short loc_1800D8A61
0x1800d89e3  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d89ea  mov     r8d, 4C5h
0x1800d89f0  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d89f7  mov     ecx, ebx
0x1800d89f9  call    TraceVpnWppErrorW32Impl
0x1800d89fe  jmp     short loc_1800D8A61
0x1800d8a00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8a07  lea     rdx, WPP_GLOBAL_Control
0x1800d8a0e  cmp     rcx, rdx
0x1800d8a11  jz      short loc_1800D8A31
0x1800d8a13  test    byte ptr [rcx+1Ch], 1
0x1800d8a17  jz      short loc_1800D8A31
0x1800d8a19  mov     rcx, [rcx+10h]
0x1800d8a1d  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8a24  mov     edx, 6Bh ; 'k'
0x1800d8a29  mov     r9d, edi
0x1800d8a2c  call    WPP_SF_d
0x1800d8a31  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d8a38  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d8a3d  test    al, al
0x1800d8a3f  jz      short loc_1800D8A5C
0x1800d8a41  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d8a48  mov     r8d, 4A1h
0x1800d8a4e  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d8a55  mov     ecx, edi
0x1800d8a57  call    TraceVpnWppErrorHRImpl
0x1800d8a5c  mov     rbp, [rsp+78h+String2]
0x1800d8a61  test    rbp, rbp
0x1800d8a64  jz      short loc_1800D8A6E
0x1800d8a66  mov     rcx, rbp; lpMem
0x1800d8a69  call    MprCommonFree
0x1800d8a6e  lea     rbp, WPP_GLOBAL_Control
0x1800d8a75  mov     rcx, r15; hMem
0x1800d8a78  call    cs:__imp_LocalFree
0x1800d8a7e  test    edi, edi
0x1800d8a80  jns     short loc_1800D8A94
0x1800d8a82  mov     eax, edi
0x1800d8a84  movzx   ebx, di
0x1800d8a87  and     eax, 1FFF0000h
0x1800d8a8c  cmp     eax, 70000h
0x1800d8a91  cmovnz  ebx, edi
0x1800d8a94  test    ebx, ebx
0x1800d8a96  jns     loc_1800D8B4B
0x1800d8a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8aa3  cmp     rcx, rbp
0x1800d8aa6  jz      short loc_1800D8AC6
0x1800d8aa8  test    byte ptr [rcx+1Ch], 8
0x1800d8aac  jz      short loc_1800D8AC6
0x1800d8aae  mov     rcx, [rcx+10h]
0x1800d8ab2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8ab9  mov     edx, 70h ; 'p'
0x1800d8abe  mov     r9d, ebx
0x1800d8ac1  call    WPP_SF_d
0x1800d8ac6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d8acd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d8ad2  test    al, al
0x1800d8ad4  jz      short loc_1800D8B4B
0x1800d8ad6  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d8add  mov     r8d, 4DCh
0x1800d8ae3  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d8aea  mov     ecx, ebx
0x1800d8aec  call    TraceVpnWppErrorHRImpl
0x1800d8af1  jmp     short loc_1800D8B4B
0x1800d8af3  mov     ebx, 0Eh
0x1800d8af8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8aff  cmp     rcx, rbp
0x1800d8b02  jz      short loc_1800D8B20
0x1800d8b04  test    byte ptr [rcx+1Ch], 1
0x1800d8b08  jz      short loc_1800D8B20
0x1800d8b0a  mov     rcx, [rcx+10h]
0x1800d8b0e  lea     edx, [rbx+5Ah]
0x1800d8b11  mov     r9d, ebx
0x1800d8b14  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8b1b  call    WPP_SF_d
0x1800d8b20  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d8b27  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d8b2c  test    al, al
0x1800d8b2e  jz      short loc_1800D8B4B
0x1800d8b30  lea     r9, aIntVpnprofileg_0; "int_VpnProfileGetInterfaceInfo"
0x1800d8b37  mov     r8d, 488h
0x1800d8b3d  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d8b44  mov     ecx, ebx
0x1800d8b46  call    TraceVpnWppErrorW32Impl
0x1800d8b4b  mov     eax, ebx
0x1800d8b4d  mov     rbx, [rsp+78h+arg_0]
0x1800d8b55  add     rsp, 40h
0x1800d8b59  pop     r15
0x1800d8b5b  pop     r14
0x1800d8b5d  pop     r13
0x1800d8b5f  pop     r12
0x1800d8b61  pop     rdi
0x1800d8b62  pop     rsi
0x1800d8b63  pop     rbp
0x1800d8b64  retn
```
