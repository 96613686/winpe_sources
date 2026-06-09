# NlmGetNetwork(_GUID,_NETWORKPROFILE * *)

- ea: `0x1800b37c8`
- end: `0x1800b4097`
- name: `?NlmGetNetwork@@YAJU_GUID@@PEAPEAU_NETWORKPROFILE@@@Z`
- size: `2255`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, struct _NETWORKPROFILE **)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b2d30`
- `0x1800b2e60`
- `0x1800b3350`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf38`
- `0x180032424`
- `0x180065328`
- `0x1800b3734`
- `0x1800b37c8`
- `0x1800b81fc`
- `0x1800e2464`
- `0x1800e2dbc`
- `0x1800e71e2`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `msvcrt!tolower` at `0x1800b3ff4`
- `msvcrt!tolower` at `0x1800b3ff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3c3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3d4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3c3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3d4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3c4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3d61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3c4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3d61`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b38f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b38f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b387c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b387c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b3d7c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b3d7c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b3f88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b3f88`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b4019`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b4019`
- `OLEAUT32!__imp_VariantInit` at `0x1800b39cc`
- `OLEAUT32!__imp_VariantInit` at `0x1800b39cc`

## string_xrefs

- `0x1800b3cdc`: `onecoreuap\net\netio\vpnplugin\profilemgmt\nlm_handler.cpp`

## pseudocode

```c
__int64 __fastcall NlmGetNetwork(struct _GUID *Buf2, struct _NETWORKPROFILE **a2)
{
  struct _NETWORKPROFILE **v2; // r13
  __int64 v4; // r12
  char *v5; // r14
  HRESULT v6; // eax
  int v7; // edi
  int v8; // r15d
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  HANDLE ProcessHeap; // rax
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // r8
  HANDLE v15; // rax
  OLECHAR *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  struct _LIST_ENTRY *v19; // rcx
  _QWORD *v20; // r15
  int v21; // eax
  _WORD *v23; // rcx
  __int64 v24; // rbx
  __int16 v25; // ax
  __int64 v26; // [rsp+38h] [rbp-81h] BYREF
  int v27; // [rsp+40h] [rbp-79h] BYREF
  int v28; // [rsp+44h] [rbp-75h] BYREF
  int v29; // [rsp+48h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-69h] BYREF
  __int64 v31; // [rsp+58h] [rbp-61h] BYREF
  __int64 v32; // [rsp+60h] [rbp-59h] BYREF
  __int64 v33; // [rsp+68h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-49h] BYREF
  struct _NETWORKPROFILE **v35; // [rsp+78h] [rbp-41h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-39h] BYREF
  struct _GUID v37; // [rsp+A0h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+B0h] [rbp-9h] BYREF
  GUID rguid; // [rsp+C0h] [rbp+7h] BYREF

  v2 = a2;
  v35 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF__guid_(WPP_GLOBAL_Control[1].Flink, 83, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, Buf2);
  LODWORD(v4) = 0;
  Buf1 = 0;
  ppv = 0;
  v26 = 0;
  rguid = GUID_NULL;
  v33 = 0;
  v5 = 0;
  v31 = 0;
  bstrString = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v32 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 84;
LABEL_8:
      v11 = (unsigned int)v6;
LABEL_9:
      WPP_SF_d(v9[1].Flink, v10, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, v11);
LABEL_10:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_94;
    }
    goto LABEL_94;
  }
  v8 = 1;
  v6 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 85;
      goto LABEL_8;
    }
LABEL_94:
    if ( !v7 )
      goto LABEL_96;
    goto LABEL_95;
  }
  v37 = *Buf2;
  v6 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v37, &v26);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 86;
      goto LABEL_8;
    }
    goto LABEL_94;
  }
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(v26, &IID_IPropertyBag, &v32);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 87;
      goto LABEL_8;
    }
    goto LABEL_94;
  }
  VariantInit(&pvarg);
  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v32 + 24LL))(
         v32,
         L"NA_NetworkClass",
         &pvarg,
         0);
  if ( v7 < 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 88, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v7);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v7 < 0 )
  {
LABEL_66:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_94;
  }
  if ( pvarg.lVal == 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 89, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids);
      goto LABEL_10;
    }
    goto LABEL_94;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v26 + 88LL))(v26, &Buf1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 90;
      goto LABEL_8;
    }
    goto LABEL_94;
  }
  if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 104LL))(v26, &v33);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 91;
        goto LABEL_8;
      }
      goto LABEL_94;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 144LL))(v26, &v28);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 92;
        goto LABEL_8;
      }
      goto LABEL_94;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 136LL))(v26, &v27);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 93;
        goto LABEL_8;
      }
      goto LABEL_94;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 56LL))(v26, &bstrString);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 94;
        goto LABEL_8;
      }
      goto LABEL_94;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_Sdd(
        WPP_GLOBAL_Control[1].Flink,
        95,
        (unsigned int)&WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
        (_DWORD)bstrString,
        v28,
        v27);
    }
    ProcessHeap = GetProcessHeap();
    v5 = (char *)HeapAlloc(ProcessHeap, 8u, 0x40u);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v33 + 64LL))(v33, 1, &v31, &v29);
        v7 = v6;
        if ( v6 < 0 )
          break;
        if ( v6 || !v29 )
        {
          v20 = v5 + 16;
          *((_DWORD *)v5 + 6) = v27;
          *((_DWORD *)v5 + 7) = v28;
          *((_OWORD *)v5 + 2) = Buf1;
          v21 = VpnStringCopy(bstrString);
          v7 = v21;
          if ( v21 >= 0 )
          {
            v23 = (_WORD *)*v20;
            if ( *(_WORD *)*v20 )
            {
              do
              {
                v24 = (unsigned int)v4;
                v25 = tolower((unsigned __int16)v23[(unsigned int)v4]);
                v4 = (unsigned int)(v4 + 1);
                *(_WORD *)(*v20 + 2 * v24) = v25;
                v23 = (_WORD *)*v20;
              }
              while ( *(_WORD *)(*v20 + 2 * v4) );
              v2 = v35;
            }
            SysFreeString(bstrString);
            *v2 = (struct _NETWORKPROFILE *)v5;
            v9 = WPP_GLOBAL_Control;
            v5 = 0;
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                103,
                &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
                (unsigned int)v21);
              v9 = WPP_GLOBAL_Control;
            }
          }
          v8 = 1;
          goto LABEL_94;
        }
        v6 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v31 + 96LL))(v31, &rguid);
        v7 = v6;
        if ( v6 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v10 = 99;
            goto LABEL_8;
          }
          goto LABEL_94;
        }
        v15 = GetProcessHeap();
        v16 = (OLECHAR *)HeapAlloc(v15, 8u, 0x220u);
        v17 = (__int64)v16;
        if ( !v16 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 100, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
              v19 = WPP_GLOBAL_Control;
            }
            if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v19[1].Blink) & 1) != 0 )
              WPP_SF_d(v19[1].Flink, 101, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          {
            v14 = 944;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        StringFromGUID2(&rguid, v16, 260);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_SS(
            WPP_GLOBAL_Control[1].Flink,
            102,
            (unsigned int)&WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids,
            (_DWORD)bstrString,
            v17);
        }
        v18 = *((_QWORD *)v5 + 7);
        if ( v18 )
          *(_QWORD *)(v17 + 536) = v18;
        ++*((_DWORD *)v5 + 12);
        *((_QWORD *)v5 + 7) = v17;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 98;
        goto LABEL_8;
      }
      goto LABEL_94;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 96, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v13[1].Blink) & 1) != 0 )
        WPP_SF_d(v13[1].Flink, 97, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v14 = 917;
LABEL_65:
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\nlm_handler.cpp",
        v14,
        "NlmGetNetwork");
    }
    goto LABEL_66;
  }
  v7 = -2147467259;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v10 = 104;
    v11 = 2147500037LL;
    goto LABEL_9;
  }
LABEL_95:
  NlmFreeNetwork((struct _NETWORKPROFILE *)v5);
  v9 = WPP_GLOBAL_Control;
LABEL_96:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v9 = WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    CoUninitialize();
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 8) != 0 )
    WPP_SF_d(v9[1].Flink, 105, &WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b37c8  mov     [rsp-8+arg_10], rbx
0x1800b37cd  push    rbp
0x1800b37ce  push    rsi
0x1800b37cf  push    rdi
0x1800b37d0  push    r12
0x1800b37d2  push    r13
0x1800b37d4  push    r14
0x1800b37d6  push    r15
0x1800b37d8  lea     rbp, [rsp-27h]
0x1800b37dd  sub     rsp, 0E0h
0x1800b37e4  mov     rax, cs:__security_cookie
0x1800b37eb  xor     rax, rsp
0x1800b37ee  mov     [rbp+57h+var_40], rax
0x1800b37f2  mov     r13, rdx
0x1800b37f5  mov     [rbp+57h+var_98], rdx
0x1800b37f9  mov     rbx, rcx
0x1800b37fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3803  lea     rax, WPP_GLOBAL_Control
0x1800b380a  cmp     rcx, rax
0x1800b380d  jz      short loc_1800B382D
0x1800b380f  test    byte ptr [rcx+1Ch], 8
0x1800b3813  jz      short loc_1800B382D
0x1800b3815  mov     rcx, [rcx+10h]
0x1800b3819  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3820  mov     edx, 53h ; 'S'
0x1800b3825  mov     r9, rbx
0x1800b3828  call    WPP_SF__guid_
0x1800b382d  xor     r12d, r12d
0x1800b3830  xorps   xmm0, xmm0
0x1800b3833  movups  [rbp+57h+Buf1], xmm0
0x1800b3837  xor     eax, eax
0x1800b3839  xor     edx, edx; dwCoInit
0x1800b383b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b3842  mov     [rbp+57h+var_A0], r12
0x1800b3846  xor     ecx, ecx; pvReserved
0x1800b3848  xorps   xmm1, xmm1
0x1800b384b  mov     [rsp+110h+var_D8], r12
0x1800b3850  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800b3855  mov     [rbp+57h+var_A8], r12
0x1800b3859  mov     r14d, r12d
0x1800b385c  mov     [rbp+57h+var_B8], r12
0x1800b3860  mov     [rbp+57h+bstrString], r12
0x1800b3864  mov     [rbp+57h+var_CC], r12d
0x1800b3868  mov     [rbp+57h+var_D0], r12d
0x1800b386c  mov     [rbp+57h+var_C8], r12d
0x1800b3870  mov     [rbp+57h+var_B0], r12
0x1800b3874  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x1800b3878  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800b387c  call    cs:__imp_CoInitializeEx
0x1800b3882  mov     edi, eax
0x1800b3884  test    eax, eax
0x1800b3886  jns     short loc_1800B38D3
0x1800b3888  mov     r15d, r12d
0x1800b388b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3892  lea     rbx, WPP_GLOBAL_Control
0x1800b3899  cmp     rcx, rbx
0x1800b389c  jz      loc_1800B3EF3
0x1800b38a2  lea     esi, [r12+1]
0x1800b38a7  test    [rcx+1Ch], sil
0x1800b38ab  jz      loc_1800B3EF3
0x1800b38b1  lea     edx, [rsi+53h]
0x1800b38b4  mov     r9d, eax
0x1800b38b7  mov     rcx, [rcx+10h]
0x1800b38bb  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b38c2  call    WPP_SF_d
0x1800b38c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b38ce  jmp     loc_1800B3EF3
0x1800b38d3  mov     esi, 1
0x1800b38d8  lea     rax, [rbp+57h+var_A0]
0x1800b38dc  lea     r9, IID_INetworkListManager; riid
0x1800b38e3  mov     [rsp+110h+ppv], rax; ppv
0x1800b38e8  xor     edx, edx; pUnkOuter
0x1800b38ea  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800b38f1  mov     r15d, esi
0x1800b38f4  lea     r8d, [rsi+16h]; dwClsContext
0x1800b38f8  call    cs:__imp_CoCreateInstance
0x1800b38fe  mov     edi, eax
0x1800b3900  test    eax, eax
0x1800b3902  jns     short loc_1800B392A
0x1800b3904  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b390b  lea     rbx, WPP_GLOBAL_Control
0x1800b3912  cmp     rcx, rbx
0x1800b3915  jz      loc_1800B3EF3
0x1800b391b  test    [rcx+1Ch], sil
0x1800b391f  jz      loc_1800B3EF3
0x1800b3925  lea     edx, [rsi+54h]
0x1800b3928  jmp     short loc_1800B38B4
0x1800b392a  mov     rcx, [rbp+57h+var_A0]
0x1800b392e  lea     r8, [rsp+110h+var_D8]
0x1800b3933  movaps  xmm0, xmmword ptr [rbx]
0x1800b3936  lea     rdx, [rbp+57h+var_70]
0x1800b393a  movdqa  [rbp+57h+var_70], xmm0
0x1800b393f  mov     rax, [rcx]
0x1800b3942  mov     rax, [rax+40h]
0x1800b3946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b394b  mov     edi, eax
0x1800b394d  test    eax, eax
0x1800b394f  jns     short loc_1800B397C
0x1800b3951  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3958  lea     rbx, WPP_GLOBAL_Control
0x1800b395f  cmp     rcx, rbx
0x1800b3962  jz      loc_1800B3EF3
0x1800b3968  test    [rcx+1Ch], sil
0x1800b396c  jz      loc_1800B3EF3
0x1800b3972  mov     edx, 56h ; 'V'
0x1800b3977  jmp     loc_1800B38B4
0x1800b397c  mov     rcx, [rsp+110h+var_D8]
0x1800b3981  lea     r8, [rbp+57h+var_B0]
0x1800b3985  lea     rdx, IID_IPropertyBag
0x1800b398c  mov     rax, [rcx]
0x1800b398f  mov     rax, [rax]
0x1800b3992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3997  mov     edi, eax
0x1800b3999  test    eax, eax
0x1800b399b  jns     short loc_1800B39C8
0x1800b399d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b39a4  lea     rbx, WPP_GLOBAL_Control
0x1800b39ab  cmp     rcx, rbx
0x1800b39ae  jz      loc_1800B3EF3
0x1800b39b4  test    [rcx+1Ch], sil
0x1800b39b8  jz      loc_1800B3EF3
0x1800b39be  mov     edx, 57h ; 'W'
0x1800b39c3  jmp     loc_1800B38B4
0x1800b39c8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b39cc  call    cs:__imp_VariantInit
0x1800b39d2  mov     rcx, [rbp+57h+var_B0]
0x1800b39d6  lea     r8, [rbp+57h+pvarg]
0x1800b39da  xor     r9d, r9d
0x1800b39dd  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800b39e4  mov     rax, [rcx]
0x1800b39e7  mov     rax, [rax+18h]
0x1800b39eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b39f0  mov     edi, eax
0x1800b39f2  test    eax, eax
0x1800b39f4  jns     short loc_1800B3A27
0x1800b39f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b39fd  lea     rax, WPP_GLOBAL_Control
0x1800b3a04  cmp     rcx, rax
0x1800b3a07  jz      short loc_1800B3A27
0x1800b3a09  test    [rcx+1Ch], sil
0x1800b3a0d  jz      short loc_1800B3A27
0x1800b3a0f  mov     rcx, [rcx+10h]
0x1800b3a13  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3a1a  mov     edx, 58h ; 'X'
0x1800b3a1f  mov     r9d, edi
0x1800b3a22  call    WPP_SF_d
0x1800b3a27  mov     rcx, [rbp+57h+var_B0]
0x1800b3a2b  mov     rax, [rcx]
0x1800b3a2e  mov     rax, [rax+10h]
0x1800b3a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a37  test    edi, edi
0x1800b3a39  js      loc_1800B3CE8
0x1800b3a3f  cmp     dword ptr [rbp+57h+pvarg+8], esi
0x1800b3a42  jnz     short loc_1800B3A7F
0x1800b3a44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3a4b  lea     rbx, WPP_GLOBAL_Control
0x1800b3a52  cmp     rcx, rbx
0x1800b3a55  jz      loc_1800B3EF3
0x1800b3a5b  test    byte ptr [rcx+1Ch], 4
0x1800b3a5f  jz      loc_1800B3EF3
0x1800b3a65  mov     rcx, [rcx+10h]
0x1800b3a69  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3a70  mov     edx, 59h ; 'Y'
0x1800b3a75  call    WPP_SF_
0x1800b3a7a  jmp     loc_1800B38C7
0x1800b3a7f  mov     rcx, [rsp+110h+var_D8]
0x1800b3a84  lea     rdx, [rbp+57h+Buf1]
0x1800b3a88  mov     rax, [rcx]
0x1800b3a8b  mov     rax, [rax+58h]
0x1800b3a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a94  mov     edi, eax
0x1800b3a96  test    eax, eax
0x1800b3a98  jns     short loc_1800B3AC5
0x1800b3a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3aa1  lea     rbx, WPP_GLOBAL_Control
0x1800b3aa8  cmp     rcx, rbx
0x1800b3aab  jz      loc_1800B3EF3
0x1800b3ab1  test    [rcx+1Ch], sil
0x1800b3ab5  jz      loc_1800B3EF3
0x1800b3abb  mov     edx, 5Ah ; 'Z'
0x1800b3ac0  jmp     loc_1800B38B4
0x1800b3ac5  mov     r8d, 10h; Size
0x1800b3acb  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b3acf  mov     rdx, rbx; Buf2
0x1800b3ad2  call    memcmp_0
0x1800b3ad7  test    eax, eax
0x1800b3ad9  jnz     loc_1800B4064
0x1800b3adf  mov     rcx, [rsp+110h+var_D8]
0x1800b3ae4  lea     rdx, [rbp+57h+var_A8]
0x1800b3ae8  mov     rax, [rcx]
0x1800b3aeb  mov     rax, [rax+68h]
0x1800b3aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3af4  mov     edi, eax
0x1800b3af6  test    eax, eax
0x1800b3af8  jns     short loc_1800B3B25
0x1800b3afa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3b01  lea     rbx, WPP_GLOBAL_Control
0x1800b3b08  cmp     rcx, rbx
0x1800b3b0b  jz      loc_1800B3EF3
0x1800b3b11  test    [rcx+1Ch], sil
0x1800b3b15  jz      loc_1800B3EF3
0x1800b3b1b  mov     edx, 5Bh ; '['
0x1800b3b20  jmp     loc_1800B38B4
0x1800b3b25  mov     rcx, [rsp+110h+var_D8]
0x1800b3b2a  lea     rdx, [rbp+57h+var_CC]
0x1800b3b2e  mov     rax, [rcx]
0x1800b3b31  mov     rax, [rax+90h]
0x1800b3b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b3d  mov     edi, eax
0x1800b3b3f  test    eax, eax
0x1800b3b41  jns     short loc_1800B3B6E
0x1800b3b43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3b4a  lea     rbx, WPP_GLOBAL_Control
0x1800b3b51  cmp     rcx, rbx
0x1800b3b54  jz      loc_1800B3EF3
0x1800b3b5a  test    [rcx+1Ch], sil
0x1800b3b5e  jz      loc_1800B3EF3
0x1800b3b64  mov     edx, 5Ch ; '\'
0x1800b3b69  jmp     loc_1800B38B4
0x1800b3b6e  mov     rcx, [rsp+110h+var_D8]
0x1800b3b73  lea     rdx, [rbp+57h+var_D0]
0x1800b3b77  mov     rax, [rcx]
0x1800b3b7a  mov     rax, [rax+88h]
0x1800b3b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b86  mov     edi, eax
0x1800b3b88  test    eax, eax
0x1800b3b8a  jns     short loc_1800B3BB7
0x1800b3b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3b93  lea     rbx, WPP_GLOBAL_Control
0x1800b3b9a  cmp     rcx, rbx
0x1800b3b9d  jz      loc_1800B3EF3
0x1800b3ba3  test    [rcx+1Ch], sil
0x1800b3ba7  jz      loc_1800B3EF3
0x1800b3bad  mov     edx, 5Dh ; ']'
0x1800b3bb2  jmp     loc_1800B38B4
0x1800b3bb7  mov     rcx, [rsp+110h+var_D8]
0x1800b3bbc  lea     rdx, [rbp+57h+bstrString]
0x1800b3bc0  mov     rax, [rcx]
0x1800b3bc3  mov     rax, [rax+38h]
0x1800b3bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bcc  mov     edi, eax
0x1800b3bce  test    eax, eax
0x1800b3bd0  jns     short loc_1800B3BFD
0x1800b3bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3bd9  lea     rbx, WPP_GLOBAL_Control
0x1800b3be0  cmp     rcx, rbx
0x1800b3be3  jz      loc_1800B3EF3
0x1800b3be9  test    [rcx+1Ch], sil
0x1800b3bed  jz      loc_1800B3EF3
0x1800b3bf3  mov     edx, 5Eh ; '^'
0x1800b3bf8  jmp     loc_1800B38B4
0x1800b3bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3c04  lea     rax, WPP_GLOBAL_Control
0x1800b3c0b  cmp     rcx, rax
0x1800b3c0e  jz      short loc_1800B3C3D
0x1800b3c10  test    byte ptr [rcx+1Ch], 4
0x1800b3c14  jz      short loc_1800B3C3D
0x1800b3c16  mov     eax, [rbp+57h+var_D0]
0x1800b3c19  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3c20  mov     r9, [rbp+57h+bstrString]
0x1800b3c24  mov     edx, 5Fh ; '_'
0x1800b3c29  mov     rcx, [rcx+10h]
0x1800b3c2d  mov     [rsp+110h+var_E8], eax
0x1800b3c31  mov     eax, [rbp+57h+var_CC]
0x1800b3c34  mov     dword ptr [rsp+110h+ppv], eax
0x1800b3c38  call    WPP_SF_Sdd
0x1800b3c3d  call    cs:__imp_GetProcessHeap
0x1800b3c43  mov     edx, 8; dwFlags
0x1800b3c48  mov     rcx, rax; hHeap
0x1800b3c4b  lea     r8d, [rdx+38h]; dwBytes
0x1800b3c4f  call    cs:__imp_HeapAlloc
0x1800b3c55  mov     r14, rax
0x1800b3c58  test    rax, rax
0x1800b3c5b  jnz     loc_1800B3CFB
0x1800b3c61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3c68  lea     r13, WPP_GLOBAL_Control
0x1800b3c6f  lea     ebx, [rax+0Eh]
0x1800b3c72  cmp     rcx, r13
0x1800b3c75  jz      short loc_1800B3CBD
0x1800b3c77  test    [rcx+1Ch], sil
0x1800b3c7b  jz      short loc_1800B3C9A
0x1800b3c7d  mov     rcx, [rcx+10h]
0x1800b3c81  lea     edx, [rax+60h]
0x1800b3c84  mov     r9d, ebx
0x1800b3c87  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3c8e  call    WPP_SF_d
0x1800b3c93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3c9a  cmp     rcx, r13
0x1800b3c9d  jz      short loc_1800B3CBD
0x1800b3c9f  test    [rcx+1Ch], sil
0x1800b3ca3  jz      short loc_1800B3CBD
0x1800b3ca5  mov     rcx, [rcx+10h]
0x1800b3ca9  lea     r8, WPP_52506ff39d753932d23e10bc38a7ac9b_Traceguids
0x1800b3cb0  mov     edx, 61h ; 'a'
0x1800b3cb5  mov     r9d, ebx
0x1800b3cb8  call    WPP_SF_d
0x1800b3cbd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800b3cc4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800b3cc9  test    al, al
0x1800b3ccb  jz      short loc_1800B3CE8
  ... truncated ...
```
