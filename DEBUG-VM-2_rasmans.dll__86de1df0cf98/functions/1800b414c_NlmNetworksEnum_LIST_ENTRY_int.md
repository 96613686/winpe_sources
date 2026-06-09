# NlmNetworksEnum(_LIST_ENTRY *,int *)

- ea: `0x1800b414c`
- end: `0x1800b4ae8`
- name: `?NlmNetworksEnum@@YAJPEAU_LIST_ENTRY@@PEAH@Z`
- size: `2460`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800af660`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x1800b3734`
- `0x1800b40a0`
- `0x1800b414c`
- `0x1800b81fc`
- `0x1800e2464`
- `0x1800e2dbc`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `msvcrt!tolower` at `0x1800b479e`
- `msvcrt!tolower` at `0x1800b479e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4643`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b46f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4643`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b46f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4706`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4706`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b437e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b437e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b41f7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b41f7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b4725`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b4725`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b42f0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b42f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b481c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b481c`
- `OLEAUT32!__imp_VariantInit` at `0x1800b450a`
- `OLEAUT32!__imp_VariantInit` at `0x1800b450a`

## string_xrefs

- `0x1800b48ee`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`

## pseudocode

```c
__int64 __fastcall NlmNetworksEnum(struct _LIST_ENTRY *a1, int *a2)
{
  int *v2; // r15
  __int64 v3; // r12
  struct _LIST_ENTRY *v4; // r14
  HRESULT v5; // eax
  int v6; // edi
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int i; // r13d
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  OLECHAR *v17; // rax
  OLECHAR *v18; // rbx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v20; // r15
  struct _LIST_ENTRY *Flink; // r9
  __int64 v22; // rbx
  __int16 v23; // ax
  struct _LIST_ENTRY *v24; // rax
  struct _LIST_ENTRY *v25; // rcx
  __int64 v26; // r8
  struct _LIST_ENTRY *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-81h] BYREF
  int v31; // [rsp+3Ch] [rbp-7Dh] BYREF
  int v32; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-75h]
  int v34; // [rsp+48h] [rbp-71h]
  int v35; // [rsp+4Ch] [rbp-6Dh]
  __int64 v36; // [rsp+50h] [rbp-69h] BYREF
  __int64 v37; // [rsp+58h] [rbp-61h] BYREF
  __int64 v38; // [rsp+60h] [rbp-59h] BYREF
  __int64 v39; // [rsp+68h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-41h] BYREF
  int *v42; // [rsp+80h] [rbp-39h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-31h] BYREF
  GUID rguid; // [rsp+A0h] [rbp-19h] BYREF
  struct _LIST_ENTRY v45; // [rsp+B0h] [rbp-9h] BYREF

  v2 = a2;
  v42 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 122, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
  LODWORD(v3) = 0;
  ppv = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  v29 = 0;
  v4 = 0;
  v32 = 0;
  v31 = 0;
  v45 = 0;
  bstrString = 0;
  v30 = 0;
  rguid = 0;
  v39 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v35 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 123;
LABEL_8:
    v9 = (unsigned int)v5;
LABEL_9:
    WPP_SF_d(v7[1].Flink, v8, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v9);
LABEL_10:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v35 = 1;
  v5 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 124;
    goto LABEL_8;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 1, &v37);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 125;
    goto LABEL_8;
  }
  for ( i = 0; ; ++i )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v37 + 64LL))(v37, 1, &v29, 0);
    if ( v6 )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  v33 = i;
  if ( !i )
    goto LABEL_10;
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 80LL))(v37);
  v6 = v12;
  if ( v12 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 126;
LABEL_47:
    v9 = (unsigned int)v12;
    goto LABEL_9;
  }
  v13 = 0;
  v34 = 0;
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v37 + 64LL))(v37, 1, &v29, 0);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_137;
      }
      v28 = 127;
      goto LABEL_136;
    }
    v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v29)(v29, &IID_IPropertyBag, &v39);
    if ( v6 >= 0 )
      break;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v14 = 128;
LABEL_54:
    WPP_SF_d(v7[1].Flink, v14, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
LABEL_55:
    v4 = 0;
LABEL_92:
    v34 = ++v13;
    if ( v13 >= i )
      goto LABEL_11;
  }
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v39 + 24LL))(
         v39,
         L"NA_NetworkClass",
         &pvarg,
         0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v14 = 129;
    goto LABEL_54;
  }
  if ( pvarg.lVal == 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 130, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
    }
    *v2 = 1;
    v4 = 0;
LABEL_91:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_92;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 144LL))(v29, &v32);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_137;
    }
    v28 = 131;
    goto LABEL_136;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 56LL))(v29, &bstrString);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_137;
    }
    v28 = 132;
    goto LABEL_136;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 104LL))(v29, &v36);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_137;
    }
    v28 = 133;
    goto LABEL_136;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 136LL))(v29, &v31);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_137;
    }
    v28 = 134;
    goto LABEL_136;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, struct _LIST_ENTRY *))(*(_QWORD *)v29 + 88LL))(v29, &v45);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_137;
    }
    v28 = 135;
LABEL_136:
    WPP_SF_d(v7[1].Flink, v28, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
LABEL_137:
    v4 = 0;
    goto LABEL_11;
  }
  ProcessHeap = GetProcessHeap();
  v4 = (struct _LIST_ENTRY *)HeapAlloc(ProcessHeap, 8u, 0x40u);
  if ( !v4 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 136, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
        v27 = WPP_GLOBAL_Control;
      }
      if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v27[1].Blink) & 1) != 0 )
        WPP_SF_d(v27[1].Flink, 137, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v26 = 1415;
LABEL_102:
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
        v26,
        "NlmNetworksEnum");
    }
    goto LABEL_10;
  }
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)v36 + 64LL))(
           v36,
           1,
           &v38,
           &v30);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v8 = 138;
        v9 = (unsigned int)v6;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v30);
    }
    if ( v6 || !v30 )
      break;
    v12 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v38 + 96LL))(v38, &rguid);
    v6 = v12;
    if ( v12 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v8 = 140;
        goto LABEL_47;
      }
      goto LABEL_11;
    }
    v16 = GetProcessHeap();
    v17 = (OLECHAR *)HeapAlloc(v16, 8u, 0x220u);
    v18 = v17;
    if ( !v17 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 141, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
          v25 = WPP_GLOBAL_Control;
        }
        if ( v25 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v25[1].Blink) & 1) != 0 )
          WPP_SF_d(v25[1].Flink, 142, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v26 = 1444;
        goto LABEL_102;
      }
      goto LABEL_10;
    }
    StringFromGUID2(&rguid, v17, 260);
    Blink = v4[3].Blink;
    if ( Blink )
      *((_QWORD *)v18 + 67) = Blink;
    ++LODWORD(v4[3].Flink);
    v4[3].Blink = (struct _LIST_ENTRY *)v18;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v20 = v4 + 1;
  LODWORD(v4[1].Blink) = v31;
  HIDWORD(v4[1].Blink) = v32;
  v4[2] = v45;
  v12 = VpnStringCopy(bstrString);
  v6 = v12;
  if ( v12 >= 0 )
  {
    Flink = v20->Flink;
    if ( LOWORD(v20->Flink->Flink) )
    {
      do
      {
        v22 = (unsigned int)v3;
        v23 = tolower(*((unsigned __int16 *)&Flink->Flink + (unsigned int)v3));
        v3 = (unsigned int)(v3 + 1);
        *((_WORD *)&v20->Flink->Flink + v22) = v23;
        Flink = v20->Flink;
      }
      while ( *((_WORD *)&v20->Flink->Flink + v3) );
      i = v33;
      LODWORD(v3) = 0;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 144, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, Flink);
    }
    v24 = g_NlmNetwork.Blink;
    if ( g_NlmNetwork.Blink->Flink != &g_NlmNetwork )
      __fastfail(3u);
    v4->Flink = &g_NlmNetwork;
    v4->Blink = v24;
    v24->Flink = v4;
    g_NlmNetwork.Blink = v4;
    v4 = 0;
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v13 = v34;
    v2 = v42;
    v29 = 0;
    goto LABEL_91;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v8 = 143;
    goto LABEL_47;
  }
LABEL_11:
  if ( v6 )
  {
    NlmFreeNetwork((struct _NETWORKPROFILE *)v4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v7 = WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v35 )
  {
    CoUninitialize();
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
  {
    NlmNetworkListFree(v7);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v7[1].Blink) & 8) != 0 )
    WPP_SF_d(v7[1].Flink, 145, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b414c  push    rbp
0x1800b414e  push    rbx
0x1800b414f  push    rsi
0x1800b4150  push    rdi
0x1800b4151  push    r12
0x1800b4153  push    r13
0x1800b4155  push    r14
0x1800b4157  push    r15
0x1800b4159  lea     rbp, [rsp-1Fh]
0x1800b415e  sub     rsp, 0D8h
0x1800b4165  mov     rax, cs:__security_cookie
0x1800b416c  xor     rax, rsp
0x1800b416f  mov     [rbp+57h+var_50], rax
0x1800b4173  mov     r15, rdx
0x1800b4176  mov     [rbp+57h+var_90], rdx
0x1800b417a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4181  lea     rbx, WPP_GLOBAL_Control
0x1800b4188  lea     r13, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b418f  cmp     rcx, rbx
0x1800b4192  jz      short loc_1800B41AB
0x1800b4194  test    byte ptr [rcx+1Ch], 8
0x1800b4198  jz      short loc_1800B41AB
0x1800b419a  mov     rcx, [rcx+10h]
0x1800b419e  mov     edx, 7Ah ; 'z'
0x1800b41a3  mov     r8, r13
0x1800b41a6  call    WPP_SF_
0x1800b41ab  xor     r12d, r12d
0x1800b41ae  xorps   xmm0, xmm0
0x1800b41b1  xorps   xmm1, xmm1
0x1800b41b4  mov     [rbp+57h+var_98], r12
0x1800b41b8  xor     eax, eax
0x1800b41ba  mov     [rbp+57h+var_B8], r12
0x1800b41be  xor     edx, edx; dwCoInit
0x1800b41c0  mov     [rbp+57h+var_C0], r12
0x1800b41c4  xor     ecx, ecx; pvReserved
0x1800b41c6  mov     [rbp+57h+var_B0], r12
0x1800b41ca  mov     [rsp+110h+var_E0], r12
0x1800b41cf  mov     r14d, r12d
0x1800b41d2  mov     [rbp+57h+var_D0], r12d
0x1800b41d6  mov     [rbp+57h+var_D4], r12d
0x1800b41da  movups  [rbp+57h+var_60], xmm0
0x1800b41de  mov     [rbp+57h+bstrString], r12
0x1800b41e2  mov     [rsp+110h+var_D8], r12d
0x1800b41e7  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800b41eb  mov     [rbp+57h+var_A8], r12
0x1800b41ef  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x1800b41f3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800b41f7  call    cs:__imp_CoInitializeEx
0x1800b41fd  mov     edi, eax
0x1800b41ff  test    eax, eax
0x1800b4201  jns     loc_1800B4359
0x1800b4207  mov     [rbp+57h+var_C4], r12d
0x1800b420b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4212  cmp     rcx, rbx
0x1800b4215  jz      short loc_1800B423B
0x1800b4217  lea     esi, [r12+1]
0x1800b421c  test    [rcx+1Ch], sil
0x1800b4220  jz      short loc_1800B423B
0x1800b4222  lea     edx, [rsi+7Ah]
0x1800b4225  mov     r9d, eax
0x1800b4228  mov     r8, r13
0x1800b422b  mov     rcx, [rcx+10h]
0x1800b422f  call    WPP_SF_d
0x1800b4234  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b423b  test    edi, edi
0x1800b423d  jz      short loc_1800B424E
0x1800b423f  mov     rcx, r14; lpMem
0x1800b4242  call    ?NlmFreeNetwork@@YAXPEAU_NETWORKPROFILE@@@Z; NlmFreeNetwork(_NETWORKPROFILE *)
0x1800b4247  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b424e  mov     rdx, [rbp+57h+var_B0]
0x1800b4252  test    rdx, rdx
0x1800b4255  jz      short loc_1800B426D
0x1800b4257  mov     rax, [rdx]
0x1800b425a  mov     rcx, rdx
0x1800b425d  mov     rax, [rax+10h]
0x1800b4261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4266  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b426d  mov     rdx, [rbp+57h+var_C0]
0x1800b4271  test    rdx, rdx
0x1800b4274  jz      short loc_1800B428C
0x1800b4276  mov     rax, [rdx]
0x1800b4279  mov     rcx, rdx
0x1800b427c  mov     rax, [rax+10h]
0x1800b4280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4285  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b428c  mov     rdx, [rsp+110h+var_E0]
0x1800b4291  test    rdx, rdx
0x1800b4294  jz      short loc_1800B42AC
0x1800b4296  mov     rax, [rdx]
0x1800b4299  mov     rcx, rdx
0x1800b429c  mov     rax, [rax+10h]
0x1800b42a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b42a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b42ac  mov     rdx, [rbp+57h+var_B8]
0x1800b42b0  test    rdx, rdx
0x1800b42b3  jz      short loc_1800B42CB
0x1800b42b5  mov     rax, [rdx]
0x1800b42b8  mov     rcx, rdx
0x1800b42bb  mov     rax, [rax+10h]
0x1800b42bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b42c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b42cb  mov     rdx, [rbp+57h+var_98]
0x1800b42cf  test    rdx, rdx
0x1800b42d2  jz      short loc_1800B42EA
0x1800b42d4  mov     rax, [rdx]
0x1800b42d7  mov     rcx, rdx
0x1800b42da  mov     rax, [rax+10h]
0x1800b42de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b42e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b42ea  cmp     [rbp+57h+var_C4], r12d
0x1800b42ee  jz      short loc_1800B42FD
0x1800b42f0  call    cs:__imp_CoUninitialize
0x1800b42f6  mov     rcx, cs:WPP_GLOBAL_Control; struct _LIST_ENTRY *
0x1800b42fd  test    edi, edi
0x1800b42ff  jns     short loc_1800B430D
0x1800b4301  call    ?NlmNetworkListFree@@YAXPEAU_LIST_ENTRY@@@Z; NlmNetworkListFree(_LIST_ENTRY *)
0x1800b4306  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b430d  lea     rax, WPP_GLOBAL_Control
0x1800b4314  cmp     rcx, rax
0x1800b4317  jz      short loc_1800B4337
0x1800b4319  test    byte ptr [rcx+1Ch], 8
0x1800b431d  jz      short loc_1800B4337
0x1800b431f  mov     rcx, [rcx+10h]
0x1800b4323  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b432a  mov     edx, 91h
0x1800b432f  mov     r9d, edi
0x1800b4332  call    WPP_SF_d
0x1800b4337  mov     eax, edi
0x1800b4339  mov     rcx, [rbp+57h+var_50]
0x1800b433d  xor     rcx, rsp; StackCookie
0x1800b4340  call    __security_check_cookie
0x1800b4345  add     rsp, 0D8h
0x1800b434c  pop     r15
0x1800b434e  pop     r14
0x1800b4350  pop     r13
0x1800b4352  pop     r12
0x1800b4354  pop     rdi
0x1800b4355  pop     rsi
0x1800b4356  pop     rbx
0x1800b4357  pop     rbp
0x1800b4358  retn
0x1800b4359  mov     esi, 1
0x1800b435e  lea     rax, [rbp+57h+var_98]
0x1800b4362  lea     r9, IID_INetworkListManager; riid
0x1800b4369  mov     [rbp+57h+var_C4], esi
0x1800b436c  xor     edx, edx; pUnkOuter
0x1800b436e  mov     [rsp+110h+ppv], rax; ppv
0x1800b4373  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800b437a  lea     r8d, [rsi+16h]; dwClsContext
0x1800b437e  call    cs:__imp_CoCreateInstance
0x1800b4384  mov     edi, eax
0x1800b4386  test    eax, eax
0x1800b4388  jns     short loc_1800B43AC
0x1800b438a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4391  cmp     rcx, rbx
0x1800b4394  jz      loc_1800B423B
0x1800b439a  test    [rcx+1Ch], sil
0x1800b439e  jz      loc_1800B423B
0x1800b43a4  lea     edx, [rsi+7Bh]
0x1800b43a7  jmp     loc_1800B4225
0x1800b43ac  mov     rcx, [rbp+57h+var_98]
0x1800b43b0  lea     r8, [rbp+57h+var_B8]
0x1800b43b4  mov     edx, esi
0x1800b43b6  mov     rax, [rcx]
0x1800b43b9  mov     rax, [rax+38h]
0x1800b43bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b43c2  mov     edi, eax
0x1800b43c4  test    eax, eax
0x1800b43c6  jns     short loc_1800B43EC
0x1800b43c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b43cf  cmp     rcx, rbx
0x1800b43d2  jz      loc_1800B423B
0x1800b43d8  test    [rcx+1Ch], sil
0x1800b43dc  jz      loc_1800B423B
0x1800b43e2  mov     edx, 7Dh ; '}'
0x1800b43e7  jmp     loc_1800B4225
0x1800b43ec  mov     r13d, r12d
0x1800b43ef  mov     rcx, [rbp+57h+var_B8]
0x1800b43f3  lea     r8, [rsp+110h+var_E0]
0x1800b43f8  xor     r9d, r9d
0x1800b43fb  mov     edx, esi
0x1800b43fd  mov     rax, [rcx]
0x1800b4400  mov     rax, [rax+40h]
0x1800b4404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4409  mov     edi, eax
0x1800b440b  test    eax, eax
0x1800b440d  jnz     short loc_1800B442A
0x1800b440f  mov     rcx, [rsp+110h+var_E0]
0x1800b4414  mov     rax, [rcx]
0x1800b4417  mov     rax, [rax+10h]
0x1800b441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4420  add     r13d, esi
0x1800b4423  mov     [rsp+110h+var_E0], r12
0x1800b4428  jmp     short loc_1800B43EF
0x1800b442a  mov     [rbp+57h+var_CC], r13d
0x1800b442e  test    r13d, r13d
0x1800b4431  jz      loc_1800B4234
0x1800b4437  mov     rcx, [rbp+57h+var_B8]
0x1800b443b  mov     rax, [rcx]
0x1800b443e  mov     rax, [rax+50h]
0x1800b4442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4447  mov     edi, eax
0x1800b4449  test    eax, eax
0x1800b444b  jns     short loc_1800B447B
0x1800b444d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4454  cmp     rcx, rbx
0x1800b4457  jz      loc_1800B423B
0x1800b445d  test    [rcx+1Ch], sil
0x1800b4461  jz      loc_1800B423B
0x1800b4467  mov     edx, 7Eh ; '~'
0x1800b446c  mov     r9d, eax
0x1800b446f  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b4476  jmp     loc_1800B422B
0x1800b447b  mov     ebx, r12d
0x1800b447e  mov     [rbp+57h+var_C8], ebx
0x1800b4481  mov     rcx, [rbp+57h+var_B8]
0x1800b4485  lea     r8, [rsp+110h+var_E0]
0x1800b448a  xor     r9d, r9d
0x1800b448d  mov     edx, esi
0x1800b448f  mov     rax, [rcx]
0x1800b4492  mov     rax, [rax+40h]
0x1800b4496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b449b  mov     edi, eax
0x1800b449d  test    eax, eax
0x1800b449f  jnz     loc_1800B4AC8
0x1800b44a5  mov     rcx, [rsp+110h+var_E0]
0x1800b44aa  lea     r8, [rbp+57h+var_A8]
0x1800b44ae  lea     rdx, IID_IPropertyBag
0x1800b44b5  mov     rax, [rcx]
0x1800b44b8  mov     rax, [rax]
0x1800b44bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b44c0  mov     edi, eax
0x1800b44c2  test    eax, eax
0x1800b44c4  jns     short loc_1800B4506
0x1800b44c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b44cd  lea     rax, WPP_GLOBAL_Control
0x1800b44d4  cmp     rcx, rax
0x1800b44d7  jz      short loc_1800B44FE
0x1800b44d9  test    [rcx+1Ch], sil
0x1800b44dd  jz      short loc_1800B44FE
0x1800b44df  mov     edx, 80h
0x1800b44e4  mov     rcx, [rcx+10h]
0x1800b44e8  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b44ef  mov     r9d, edi
0x1800b44f2  call    WPP_SF_d
0x1800b44f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b44fe  mov     r14, r12
0x1800b4501  jmp     loc_1800B485A
0x1800b4506  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b450a  call    cs:__imp_VariantInit
0x1800b4510  mov     rcx, [rbp+57h+var_A8]
0x1800b4514  lea     r8, [rbp+57h+pvarg]
0x1800b4518  xor     r9d, r9d
0x1800b451b  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800b4522  mov     rax, [rcx]
0x1800b4525  mov     rax, [rax+18h]
0x1800b4529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b452e  mov     rcx, [rbp+57h+var_A8]
0x1800b4532  mov     edi, eax
0x1800b4534  mov     rax, [rcx]
0x1800b4537  mov     rax, [rax+10h]
0x1800b453b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4540  test    edi, edi
0x1800b4542  jns     short loc_1800B4564
0x1800b4544  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b454b  lea     rax, WPP_GLOBAL_Control
0x1800b4552  cmp     rcx, rax
0x1800b4555  jz      short loc_1800B44FE
0x1800b4557  test    [rcx+1Ch], sil
0x1800b455b  jz      short loc_1800B44FE
0x1800b455d  mov     edx, 81h
0x1800b4562  jmp     short loc_1800B44E4
0x1800b4564  cmp     dword ptr [rbp+57h+pvarg+8], esi
0x1800b4567  jnz     short loc_1800B45A2
0x1800b4569  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4570  lea     rax, WPP_GLOBAL_Control
0x1800b4577  cmp     rcx, rax
0x1800b457a  jz      short loc_1800B4597
0x1800b457c  test    byte ptr [rcx+1Ch], 4
0x1800b4580  jz      short loc_1800B4597
0x1800b4582  mov     rcx, [rcx+10h]
0x1800b4586  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b458d  mov     edx, 82h
0x1800b4592  call    WPP_SF_
0x1800b4597  mov     [r15], esi
0x1800b459a  mov     r14, r12
0x1800b459d  jmp     loc_1800B4853
0x1800b45a2  mov     rcx, [rsp+110h+var_E0]
0x1800b45a7  lea     rdx, [rbp+57h+var_D0]
0x1800b45ab  mov     rax, [rcx]
0x1800b45ae  mov     rax, [rax+90h]
0x1800b45b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b45ba  mov     edi, eax
0x1800b45bc  test    eax, eax
0x1800b45be  js      loc_1800B4A88
0x1800b45c4  mov     rcx, [rsp+110h+var_E0]
0x1800b45c9  lea     rdx, [rbp+57h+bstrString]
0x1800b45cd  mov     rax, [rcx]
0x1800b45d0  mov     rax, [rax+38h]
0x1800b45d4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
