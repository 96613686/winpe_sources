# FSService::InternalActivateSource(IFSSource *,IFSClientContext *,void *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,ulong,IMFAttributes *,IMFCollection *)

- ea: `0x180010a1c`
- end: `0x18001173e`
- name: `?InternalActivateSource@FSService@@IEAAJPEAUIFSSource@@PEAUIFSClientContext@@PEAXW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@KPEAUIMFAttributes@@PEAUIMFCollection@@@Z`
- size: `3362`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *, __int64, unsigned int, char, struct IMFAttributes *, __int64)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000abd0`
- `0x18000af70`
- `0x18000bf60`

## callees

- `0x1800012dc`
- `0x18000162c`
- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x18000a648`
- `0x180010a1c`
- `0x1800175bc`
- `0x180017ab8`
- `0x180017f60`
- `0x1800186a0`
- `0x180018998`
- `0x180021e3c`
- `0x18002a0ec`
- `0x18003a3cc`
- `0x18004d714`
- `0x18004d748`
- `0x18004f37c`
- `0x1800640a4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011157`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011157`
- `MFPlat!MFCreateCollection` at `0x180010ecc`
- `MFPlat!MFCreateCollection` at `0x180010ecc`

## pseudocode

```c
__int64 __fastcall FSService::InternalActivateSource(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        struct IMFAttributes *a7,
        __int64 a8)
{
  char v11; // r12
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(__int64 *, __int64 *); // rbx
  char v16; // al
  int v17; // eax
  const char *v18; // rbx
  const char *v19; // rax
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64 *, struct IMFAttributes **); // rbx
  int v22; // eax
  __int64 v23; // rdx
  FSString *v24; // rax
  const char *String; // rax
  bool v26; // r12
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // r12d
  HRESULT FSEffectSourceIdCache; // eax
  __int64 v32; // rdx
  __int64 (__fastcall ****v33)(_QWORD, GUID *, __int64 *); // rbx
  const struct _GUID *v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v37)(__int64 *, struct IMFAttributes **); // rbx
  __int64 v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 (__fastcall *v41)(__int64, _QWORD, _QWORD); // rbx
  int FSSourceActivate; // eax
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v45; // rdx
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, GUID *, _QWORD); // rbx
  LPVOID v48; // rcx
  const IID *v49; // rax
  bool v50; // r8
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, struct IMFAttributes **); // rbx
  int v53; // eax
  bool v54; // r8
  __int64 v55; // rdx
  bool v56; // zf
  unsigned int (*v57)(void); // rax
  __int64 v58; // rdx
  LPVOID v59; // rbx
  __int64 v60; // rax
  __int64 (__fastcall *v61)(LPVOID, GUID *, __int64 *); // rdi
  const unsigned __int16 *v62; // rax
  __int64 v63; // rax
  __int64 (__fastcall *v64)(__int64 *, struct IMFAttributes **); // rbx
  __int64 v65; // rcx
  __int64 v66; // rax
  struct IMFAttributes *v67; // rsi
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetAllocatedString)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rbx
  int v70; // r8d
  int v71; // r9d
  struct IMFAttributes *v72; // rcx
  __int64 v73; // rdx
  struct IMFAttributes *v75; // [rsp+60h] [rbp-81h] BYREF
  bool v76; // [rsp+68h] [rbp-79h]
  __int64 (__fastcall ***v77)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-71h] BYREF
  __int64 v78; // [rsp+78h] [rbp-69h] BYREF
  struct IMFAttributes *v79; // [rsp+80h] [rbp-61h] BYREF
  __int64 v80; // [rsp+88h] [rbp-59h] BYREF
  unsigned int v81; // [rsp+90h] [rbp-51h] BYREF
  __int64 v82; // [rsp+98h] [rbp-49h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v84; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-31h] BYREF
  struct IMFAttributes *v86; // [rsp+B8h] [rbp-29h] BYREF
  LPVOID ppv[3]; // [rsp+C0h] [rbp-21h] BYREF

  v81 = 0;
  v86 = a7;
  v11 = 0;
  v84 = a8;
  v82 = a4;
  v83 = 0;
  v80 = 0;
  v85 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      190,
      &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
      a1,
      a2,
      a3,
      a4);
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_159;
    v14 = 191;
    goto LABEL_6;
  }
  v15 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 48);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v80);
  v12 = v15(a2, &v80);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_159;
    v14 = 192;
    goto LABEL_6;
  }
  v16 = byte_18010EC4D;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 24LL))(v80);
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 193, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1, v17);
    v16 = byte_18010EC4D;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v18 = L"<nullptr>";
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 32LL))(v80)
          ? (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 32LL))(v80)
          : L"<nullptr>";
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        194,
        (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        a1,
        (__int64)v19);
      v16 = byte_18010EC4D;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 40LL))(v80) )
          v18 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 40LL))(v80);
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          195,
          (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
          a1,
          (__int64)v18);
        v16 = byte_18010EC4D;
      }
    }
  }
  if ( (unsigned __int8)v16 >= 0x10u && a3 )
  {
    v20 = *a3;
    v75 = 0;
    v21 = *(__int64 (__fastcall **)(__int64 *, struct IMFAttributes **))(v20 + 168);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
    v22 = v21(a3, &v75);
    v13 = v22;
    if ( v22 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_25:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
        goto LABEL_159;
      }
      v23 = 196;
LABEL_24:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1, v22);
      goto LABEL_25;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v24 = ClientContextInfoTrace::ClientContextInfoTrace(
              (ClientContextInfoTrace *)ppv,
              (struct IFSClientContextInfo *)v75);
      String = FSString::GetString(v24);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        197,
        (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        a1,
        (__int64)String);
      v11 = 1;
    }
    if ( (v11 & 1) != 0 )
      FSString::~FSString((FSString *)ppv);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
  }
  v26 = 0;
  v76 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 24LL))(v80) - 1;
  if ( !v27 )
  {
    v13 = -2147024846;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        a1,
        -2147024846);
    goto LABEL_159;
  }
  v28 = v27 - 1;
  if ( !v28 )
    goto LABEL_134;
  v29 = v28 - 1;
  if ( v29 )
  {
    if ( v29 != 1 )
    {
      v26 = *(_QWORD *)(a1 + 1104) != 0;
      goto LABEL_134;
    }
    v30 = 0;
  }
  else
  {
    v30 = 0;
    v76 = *(_QWORD *)(a1 + 1104) != 0;
  }
  v77 = 0;
  v81 = 0;
  v78 = 0;
  v79 = 0;
  ppv[0] = 0;
  if ( !a3 )
  {
    FSEffectSourceIdCache = -2147024809;
    v13 = -2147024809;
    if ( g_wppLevels )
    {
      v32 = 199;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  if ( !v82 )
  {
    FSEffectSourceIdCache = -2147024809;
    v13 = -2147024809;
    if ( g_wppLevels )
    {
      v32 = 200;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  v33 = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 1184);
  if ( !*(_QWORD *)(a1 + 1184) )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 1184);
    FSEffectSourceIdCache = FSEffectSourceIdCache::CreateFSEffectSourceIdCache(v34, (void **)(a1 + 1184));
    v13 = FSEffectSourceIdCache;
    if ( FSEffectSourceIdCache < 0 )
    {
      if ( g_wppLevels )
      {
        v32 = 201;
        goto LABEL_41;
      }
      goto LABEL_42;
    }
  }
  v35 = *v33;
  v36 = ***v33;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v85);
  FSEffectSourceIdCache = v36(v35, &GUID_00000000_0000_0000_c000_000000000046, &v85);
  v13 = FSEffectSourceIdCache;
  if ( FSEffectSourceIdCache < 0 )
  {
    if ( g_wppLevels )
    {
      v32 = 202;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  v37 = *(__int64 (__fastcall **)(__int64 *, struct IMFAttributes **))(*a3 + 168);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v79);
  FSEffectSourceIdCache = v37(a3, &v79);
  v13 = FSEffectSourceIdCache;
  if ( FSEffectSourceIdCache < 0 )
  {
    if ( g_wppLevels )
    {
      v32 = 203;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  v38 = v84;
  if ( !v84 )
  {
LABEL_91:
    v48 = ppv[0];
    ppv[0] = 0;
    if ( v48 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
    v49 = (const IID *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 64LL))(v80);
    FSEffectSourceIdCache = CoCreateInstance(v49, 0, 1u, &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67, ppv);
    v13 = FSEffectSourceIdCache;
    if ( FSEffectSourceIdCache < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_42;
      v32 = 213;
      goto LABEL_41;
    }
    if ( v86 )
    {
      FSEffectSourceIdCache = FSCopyAttributes(v86, (struct IMFAttributes *)ppv[0], v50);
      v13 = FSEffectSourceIdCache;
      if ( FSEffectSourceIdCache < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_42;
        v32 = 214;
        goto LABEL_41;
      }
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v80 + 24LL))(v80) == 3 )
    {
      v51 = v80;
      v75 = 0;
      v52 = *(__int64 (__fastcall **)(__int64, struct IMFAttributes **))(*(_QWORD *)v80 + 136LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
      v53 = v52(v51, &v75);
      v13 = v53;
      if ( v53 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_105:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
          goto LABEL_42;
        }
        v55 = 215;
LABEL_104:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1, v53);
        goto LABEL_105;
      }
      if ( v75 )
      {
        v53 = FSCopyAttributes(v75, (struct IMFAttributes *)ppv[0], v54);
        v13 = v53;
        if ( v53 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_105;
          v55 = 216;
          goto LABEL_104;
        }
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
    }
    FSEffectSourceIdCache = (*(__int64 (__fastcall **)(LPVOID, void *, _QWORD))(*(_QWORD *)ppv[0] + 216LL))(
                              ppv[0],
                              &MF_VIRTUALCAMERA_ASSOCIATED_CAMERA_SOURCES,
                              v77);
    v13 = FSEffectSourceIdCache;
    if ( FSEffectSourceIdCache < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_42;
      v32 = 217;
      goto LABEL_41;
    }
    v56 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) == 0;
    v57 = *(unsigned int (**)(void))(*(_QWORD *)v80 + 24LL);
    if ( v56 )
    {
      if ( v57() == 4 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v80 + 48LL))(v80) )
        {
          v62 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v80 + 56LL))(v80, 0);
          if ( FSIsOEMOptInForWindowsEffects(v62) )
          {
            FSEffectSourceIdCache = (*(__int64 (__fastcall **)(LPVOID, void *, __int64))(*(_QWORD *)ppv[0] + 168LL))(
                                      ppv[0],
                                      &MF_MEPCMS_PROFILESUPPORT_FLAG,
                                      1);
            v13 = FSEffectSourceIdCache;
            if ( FSEffectSourceIdCache < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_42;
              v32 = 220;
LABEL_41:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v32,
                &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
                a1,
                FSEffectSourceIdCache);
              goto LABEL_42;
            }
          }
        }
      }
    }
    else if ( v57() == 4 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v80 + 48LL))(v80) )
    {
      FSEffectSourceIdCache = (*(__int64 (__fastcall **)(LPVOID, void *, __int64))(*(_QWORD *)ppv[0] + 168LL))(
                                ppv[0],
                                &MF_MEPCMS_PROFILESUPPORT_FLAG,
                                1);
      v13 = FSEffectSourceIdCache;
      if ( FSEffectSourceIdCache < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_42;
        v32 = 218;
        goto LABEL_41;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 219, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1);
    }
    v58 = v83;
    v59 = ppv[0];
    v60 = *(_QWORD *)ppv[0];
    v83 = 0;
    v61 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(v60 + 264);
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    FSEffectSourceIdCache = v61(v59, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66, &v83);
    v13 = FSEffectSourceIdCache;
    if ( FSEffectSourceIdCache < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_42;
      v32 = 221;
      goto LABEL_41;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(ppv);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v78);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v77);
    v26 = v76;
LABEL_134:
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, __int64))(*a2 + 320))(a2, v83, a3, v85);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v63 = *a3;
      v75 = 0;
      v64 = *(__int64 (__fastcall **)(__int64 *, struct IMFAttributes **))(v63 + 168);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
      v22 = v64(a3, &v75);
      v13 = v22;
      if ( v22 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_25;
        v23 = 223;
        goto LABEL_24;
      }
      ((void (__fastcall *)(struct IMFAttributes *, __int64))v75->lpVtbl->GetItemByIndex)(v75, v80);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
      if ( !v26
        || (v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 1104) + 48LL))(
                    *(_QWORD *)(a1 + 1104),
                    a2),
            v13 = v12,
            v12 >= 0) )
      {
        v65 = *(_QWORD *)(a1 + 944);
        if ( v65 )
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 48LL))(v65, a2);
        if ( (a6 & 1) != 0 )
        {
          v66 = *a2;
          v75 = 0;
          *(GUID *)ppv = GUID_00000000_0000_0000_0000_000000000000;
          (*(void (__fastcall **)(__int64 *, LPVOID *))(v66 + 344))(a2, ppv);
          v67 = v86;
          if ( v86 )
          {
            lpVtbl = v86->lpVtbl;
            v81 = 0;
            GetAllocatedString = lpVtbl->GetAllocatedString;
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
              &v75,
              0);
            ((void (__fastcall *)(struct IMFAttributes *, const IID *, struct IMFAttributes **, unsigned int *))GetAllocatedString)(
              v67,
              &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
              &v75,
              &v81);
          }
          if ( dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
          {
            v86 = (struct IMFAttributes *)ppv;
            v81 = v13;
            v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 64LL))(v80);
            v82 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 40))(a2);
            v72 = (struct IMFAttributes *)L"NA";
            v78 = 50333696;
            if ( v75 )
              v72 = v75;
            v77 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(a1 + 44);
            v79 = v72;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (_DWORD)v72,
              (unsigned int)&unk_180102997,
              v70,
              v71,
              (__int64)&v77,
              (__int64)&v78,
              (__int64)&v79,
              (__int64)&v82,
              (__int64)&v84,
              (__int64)&v86,
              (__int64)&v81);
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v75);
        }
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v73 = 226;
          goto LABEL_161;
        }
        goto LABEL_162;
      }
      if ( !g_wppLevels )
        goto LABEL_159;
      v14 = 224;
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_159;
      v14 = 222;
    }
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1, v12);
    goto LABEL_159;
  }
  v39 = v78;
  v78 = 0;
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  FSEffectSourceIdCache = MFCreateCollection(&v78);
  v13 = FSEffectSourceIdCache;
  if ( FSEffectSourceIdCache < 0 )
  {
    if ( g_wppLevels )
    {
      v32 = 204;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  FSEffectSourceIdCache = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 24LL))(v38, &v81);
  v13 = FSEffectSourceIdCache;
  if ( FSEffectSourceIdCache < 0 )
  {
    if ( g_wppLevels )
    {
      v32 = 205;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  if ( !v81 )
  {
    FSEffectSourceIdCache = -2147024809;
    v13 = -2147024809;
    if ( g_wppLevels )
    {
      v32 = 206;
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  while ( 1 )
  {
    v40 = *(_QWORD *)v38;
    v82 = 0;
    v75 = 0;
    v41 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v40 + 32);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v77);
    FSSourceActivate = v41(v84, v30, &v77);
    v13 = FSSourceActivate;
    if ( FSSourceActivate < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_87;
      v45 = 207;
      goto LABEL_86;
    }
    v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v77;
    v44 = **v77;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v82);
    FSSourceActivate = v44(v43, &GUID_db2eb021_b0d7_4d80_b04a_4f8d850d1bb9, &v82);
    v13 = FSSourceActivate;
    if ( FSSourceActivate < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_87;
      v45 = 208;
      goto LABEL_86;
    }
    if ( v76 )
    {
      FSSourceActivate = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 1104) + 48LL))(
                           *(_QWORD *)(a1 + 1104),
                           v82);
      v13 = FSSourceActivate;
      if ( FSSourceActivate < 0 )
      {
        if ( g_wppLevels )
        {
          v45 = 209;
          goto LABEL_86;
        }
LABEL_87:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v82);
        goto LABEL_42;
      }
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
    FSSourceActivate = FSSourceActivate::CreateFSSourceActivate(v79, a5, v82, a2);
    v13 = FSSourceActivate;
    if ( FSSourceActivate < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_87;
      v45 = 210;
      goto LABEL_86;
    }
    FSSourceActivate = (*(__int64 (__fastcall **)(__int64, struct IMFAttributes *))(*(_QWORD *)v78 + 40LL))(v78, v75);
    v13 = FSSourceActivate;
    if ( FSSourceActivate < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_87;
      v45 = 211;
LABEL_86:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v45,
        &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        a1,
        FSSourceActivate);
      goto LABEL_87;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v82);
    if ( ++v30 >= v81 )
      break;
    v38 = v84;
  }
  v46 = v78;
  v47 = **(__int64 (__fastcall ***)(__int64, GUID *, _QWORD))v78;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v77);
  FSEffectSourceIdCache = v47(v46, &GUID_00000000_0000_0000_c000_000000000046, &v77);
  v13 = FSEffectSourceIdCache;
  if ( FSEffectSourceIdCache >= 0 )
    goto LABEL_91;
  if ( g_wppLevels )
  {
    v32 = 212;
    goto LABEL_41;
  }
LABEL_42:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(ppv);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v78);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v77);
LABEL_159:
  if ( byte_18010EC4D )
  {
    v73 = 225;
LABEL_161:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v73, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, a1, v13);
  }
LABEL_162:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v85);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v80);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v83);
  return v13;
}

```

## disassembly

```asm
0x180010a1c  push    rbp
0x180010a1e  push    rbx
0x180010a1f  push    rsi
0x180010a20  push    rdi
0x180010a21  push    r12
0x180010a23  push    r13
0x180010a25  push    r14
0x180010a27  push    r15
0x180010a29  lea     rbp, [rsp-7]
0x180010a2e  sub     rsp, 0E8h
0x180010a35  mov     rax, cs:__security_cookie
0x180010a3c  xor     rax, rsp
0x180010a3f  mov     [rbp+3Fh+var_48], rax
0x180010a43  xor     esi, esi
0x180010a45  mov     r14, rcx
0x180010a48  mov     rcx, [rbp+3Fh+arg_30]
0x180010a4c  mov     rax, r9
0x180010a4f  mov     [rbp+3Fh+var_90], esi
0x180010a52  mov     r13, r8
0x180010a55  mov     [rbp+3Fh+var_68], rcx
0x180010a59  mov     r15, rdx
0x180010a5c  mov     rcx, [rbp+3Fh+arg_38]
0x180010a63  mov     r12d, esi
0x180010a66  mov     [rbp+3Fh+var_78], rcx
0x180010a6a  mov     [rbp+3Fh+var_88], rax
0x180010a6e  mov     [rbp+3Fh+var_80], rsi
0x180010a72  mov     [rbp+3Fh+var_98], rsi
0x180010a76  mov     [rbp+3Fh+var_70], rsi
0x180010a7a  cmp     cs:byte_18010EC4D, 8
0x180010a81  jb      short loc_180010AB4
0x180010a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a8a  mov     edx, 0BEh
0x180010a8f  mov     [rsp+120h+var_F0], rax
0x180010a94  mov     r9, r14
0x180010a97  mov     [rsp+120h+var_F8], r8
0x180010a9c  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010aa3  mov     [rsp+120h+ppv], r15
0x180010aa8  mov     rcx, [rcx+0D8h]
0x180010aaf  call    WPP_SF_qqqq
0x180010ab4  test    r15, r15
0x180010ab7  jnz     short loc_180010ADF
0x180010ab9  mov     eax, 80070057h
0x180010abe  mov     edi, eax
0x180010ac0  lea     esi, [r15+1]
0x180010ac4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010acb  jb      loc_1800116D2
0x180010ad1  mov     edx, 0BFh
0x180010ad6  mov     dword ptr [rsp+120h+ppv], eax
0x180010ada  jmp     loc_1800116B8
0x180010adf  mov     rax, [r15]
0x180010ae2  lea     rcx, [rbp+3Fh+var_98]
0x180010ae6  mov     rbx, [rax+30h]
0x180010aea  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010aef  lea     rdx, [rbp+3Fh+var_98]
0x180010af3  mov     rcx, r15
0x180010af6  mov     rax, rbx
0x180010af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010afe  mov     edi, eax
0x180010b00  test    eax, eax
0x180010b02  jns     short loc_180010B1D
0x180010b04  mov     esi, 1
0x180010b09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010b10  jb      loc_1800116D2
0x180010b16  mov     edx, 0C0h
0x180010b1b  jmp     short loc_180010AD6
0x180010b1d  mov     al, cs:byte_18010EC4D
0x180010b23  cmp     al, 8
0x180010b25  jb      loc_180010C21
0x180010b2b  mov     rcx, [rbp+3Fh+var_98]
0x180010b2f  mov     rax, [rcx]
0x180010b32  mov     rax, [rax+18h]
0x180010b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b42  lea     rdi, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010b49  mov     edx, 0C1h
0x180010b4e  mov     dword ptr [rsp+120h+ppv], eax
0x180010b52  mov     r9, r14
0x180010b55  mov     r8, rdi
0x180010b58  mov     rcx, [rcx+0D8h]
0x180010b5f  call    WPP_SF_qD
0x180010b64  mov     al, cs:byte_18010EC4D
0x180010b6a  cmp     al, 8
0x180010b6c  jb      loc_180010C21
0x180010b72  mov     rcx, [rbp+3Fh+var_98]
0x180010b76  mov     rax, [rcx]
0x180010b79  mov     rax, [rax+20h]
0x180010b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b82  lea     rbx, aNullptr_0; "<nullptr>"
0x180010b89  test    rax, rax
0x180010b8c  jnz     short loc_180010B93
0x180010b8e  mov     rax, rbx
0x180010b91  jmp     short loc_180010BA3
0x180010b93  mov     rcx, [rbp+3Fh+var_98]
0x180010b97  mov     rax, [rcx]
0x180010b9a  mov     rax, [rax+20h]
0x180010b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010baa  mov     edx, 0C2h
0x180010baf  mov     r9, r14
0x180010bb2  mov     [rsp+120h+ppv], rax
0x180010bb7  mov     r8, rdi
0x180010bba  mov     rcx, [rcx+0D8h]
0x180010bc1  call    WPP_SF_qS
0x180010bc6  mov     al, cs:byte_18010EC4D
0x180010bcc  cmp     al, 8
0x180010bce  jb      short loc_180010C21
0x180010bd0  mov     rcx, [rbp+3Fh+var_98]
0x180010bd4  mov     rax, [rcx]
0x180010bd7  mov     rax, [rax+28h]
0x180010bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be0  test    rax, rax
0x180010be3  jz      short loc_180010BF8
0x180010be5  mov     rcx, [rbp+3Fh+var_98]
0x180010be9  mov     rax, [rcx]
0x180010bec  mov     rax, [rax+28h]
0x180010bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bf5  mov     rbx, rax
0x180010bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bff  mov     edx, 0C3h
0x180010c04  mov     r9, r14
0x180010c07  mov     [rsp+120h+ppv], rbx
0x180010c0c  mov     r8, rdi
0x180010c0f  mov     rcx, [rcx+0D8h]
0x180010c16  call    WPP_SF_qS
0x180010c1b  mov     al, cs:byte_18010EC4D
0x180010c21  mov     esi, 1
0x180010c26  cmp     al, 10h
0x180010c28  jb      loc_180010D03
0x180010c2e  test    r13, r13
0x180010c31  jz      loc_180010D03
0x180010c37  mov     rax, [r13+0]
0x180010c3b  lea     rcx, [rsp+120h+var_C0]
0x180010c40  mov     [rsp+120h+var_C0], r12
0x180010c45  mov     rbx, [rax+0A8h]
0x180010c4c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010c51  lea     rdx, [rsp+120h+var_C0]
0x180010c56  mov     rcx, r13
0x180010c59  mov     rax, rbx
0x180010c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c61  mov     edi, eax
0x180010c63  test    eax, eax
0x180010c65  jns     short loc_180010CA2
0x180010c67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010c6e  jb      short loc_180010C93
0x180010c70  mov     edx, 0C4h
0x180010c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c7c  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010c83  mov     r9, r14
0x180010c86  mov     dword ptr [rsp+120h+ppv], eax
0x180010c8a  mov     rcx, [rcx+10h]
0x180010c8e  call    WPP_SF_qD
0x180010c93  lea     rcx, [rsp+120h+var_C0]; void *
0x180010c98  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010c9d  jmp     loc_1800116D2
0x180010ca2  cmp     cs:byte_18010EC4D, 8
0x180010ca9  jb      short loc_180010CEB
0x180010cab  mov     rdx, [rsp+120h+var_C0]; struct IFSClientContextInfo *
0x180010cb0  lea     rcx, [rbp+3Fh+var_60]; this
0x180010cb4  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x180010cb9  mov     rcx, rax; this
0x180010cbc  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180010cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cc8  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010ccf  mov     edx, 0C5h
0x180010cd4  mov     [rsp+120h+ppv], rax
0x180010cd9  mov     r9, r14
0x180010cdc  mov     rcx, [rcx+0D8h]
0x180010ce3  call    WPP_SF_qs
0x180010ce8  mov     r12d, esi
0x180010ceb  test    sil, r12b
0x180010cee  jz      short loc_180010CF9
0x180010cf0  lea     rcx, [rbp+3Fh+var_60]; this
0x180010cf4  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180010cf9  lea     rcx, [rsp+120h+var_C0]; void *
0x180010cfe  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010d03  mov     rcx, [rbp+3Fh+var_98]
0x180010d07  xor     r12b, r12b
0x180010d0a  mov     [rbp+3Fh+var_B8], r12b
0x180010d0e  mov     rax, [rcx]
0x180010d11  mov     rax, [rax+18h]
0x180010d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d1a  sub     eax, esi
0x180010d1c  jz      loc_1800116A1
0x180010d22  sub     eax, esi
0x180010d24  jz      loc_18001144A
0x180010d2a  sub     eax, esi
0x180010d2c  jz      short loc_180010D43
0x180010d2e  cmp     eax, esi
0x180010d30  jz      short loc_180010D53
0x180010d32  cmp     qword ptr [r14+450h], 0
0x180010d3a  setnz   r12b
0x180010d3e  jmp     loc_18001144A
0x180010d43  xor     r12d, r12d
0x180010d46  cmp     [r14+450h], r12
0x180010d4d  setnz   [rbp+3Fh+var_B8]
0x180010d51  jmp     short loc_180010D56
0x180010d53  xor     r12d, r12d
0x180010d56  mov     [rbp+3Fh+var_B0], r12
0x180010d5a  mov     [rbp+3Fh+var_90], r12d
0x180010d5e  mov     [rbp+3Fh+var_A8], r12
0x180010d62  mov     [rbp+3Fh+var_A0], r12
0x180010d66  mov     [rbp+3Fh+var_60], r12
0x180010d6a  test    r13, r13
0x180010d6d  jnz     short loc_180010DCB
0x180010d6f  mov     eax, 80070057h
0x180010d74  mov     edi, eax
0x180010d76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010d7d  jb      short loc_180010DA2
0x180010d7f  mov     edx, 0C7h
0x180010d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d8b  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010d92  mov     r9, r14
0x180010d95  mov     dword ptr [rsp+120h+ppv], eax
0x180010d99  mov     rcx, [rcx+10h]
0x180010d9d  call    WPP_SF_qD
0x180010da2  lea     rcx, [rbp+3Fh+var_60]; void *
0x180010da6  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010dab  lea     rcx, [rbp+3Fh+var_A0]; void *
0x180010daf  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010db4  lea     rcx, [rbp+3Fh+var_A8]; void *
0x180010db8  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010dbd  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180010dc1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180010dc6  jmp     loc_1800116D2
0x180010dcb  cmp     [rbp+3Fh+var_88], r12
0x180010dcf  jnz     short loc_180010DE8
0x180010dd1  mov     eax, 80070057h
0x180010dd6  mov     edi, eax
0x180010dd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010ddf  jb      short loc_180010DA2
0x180010de1  mov     edx, 0C8h
0x180010de6  jmp     short loc_180010D84
0x180010de8  lea     rbx, [r14+4A0h]
0x180010def  cmp     [rbx], r12
0x180010df2  jnz     short loc_180010E1D
0x180010df4  mov     rcx, rbx
0x180010df7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010dfc  mov     rdx, rbx; void **
0x180010dff  call    ?CreateFSEffectSourceIdCache@FSEffectSourceIdCache@@SAJAEBU_GUID@@PEAPEAX@Z; FSEffectSourceIdCache::CreateFSEffectSourceIdCache(_GUID const &,void * *)
0x180010e04  mov     edi, eax
0x180010e06  test    eax, eax
0x180010e08  jns     short loc_180010E1D
0x180010e0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010e11  jb      short loc_180010DA2
0x180010e13  mov     edx, 0C9h
0x180010e18  jmp     loc_180010D84
0x180010e1d  mov     rdi, [rbx]
0x180010e20  lea     rcx, [rbp+3Fh+var_70]
0x180010e24  mov     rax, [rdi]
0x180010e27  mov     rbx, [rax]
0x180010e2a  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010e2f  lea     r8, [rbp+3Fh+var_70]
0x180010e33  mov     rcx, rdi
0x180010e36  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180010e3d  mov     rax, rbx
0x180010e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e45  mov     edi, eax
0x180010e47  test    eax, eax
0x180010e49  jns     short loc_180010E62
0x180010e4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010e52  jb      loc_180010DA2
0x180010e58  mov     edx, 0CAh
0x180010e5d  jmp     loc_180010D84
0x180010e62  mov     rax, [r13+0]
0x180010e66  lea     rcx, [rbp+3Fh+var_A0]
0x180010e6a  mov     rbx, [rax+0A8h]
0x180010e71  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010e76  lea     rdx, [rbp+3Fh+var_A0]
0x180010e7a  mov     rcx, r13
0x180010e7d  mov     rax, rbx
0x180010e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e85  mov     edi, eax
0x180010e87  test    eax, eax
0x180010e89  jns     short loc_180010EA2
0x180010e8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010e92  jb      loc_180010DA2
0x180010e98  mov     edx, 0CBh
0x180010e9d  jmp     loc_180010D84
0x180010ea2  mov     rbx, [rbp+3Fh+var_78]
0x180010ea6  test    rbx, rbx
0x180010ea9  jz      loc_180011116
0x180010eaf  mov     rcx, [rbp+3Fh+var_A8]
0x180010eb3  mov     [rbp+3Fh+var_A8], r12
0x180010eb7  test    rcx, rcx
0x180010eba  jz      short loc_180010EC8
0x180010ebc  mov     rax, [rcx]
0x180010ebf  mov     rax, [rax+10h]
0x180010ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ec8  lea     rcx, [rbp+3Fh+var_A8]
0x180010ecc  call    cs:__imp_MFCreateCollection
0x180010ed2  mov     edi, eax
0x180010ed4  test    eax, eax
0x180010ed6  jns     short loc_180010EEF
0x180010ed8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180010edf  jb      loc_180010DA2
0x180010ee5  mov     edx, 0CCh
0x180010eea  jmp     loc_180010D84
0x180010eef  mov     rax, [rbx]
0x180010ef2  lea     rdx, [rbp+3Fh+var_90]
0x180010ef6  mov     rcx, rbx
  ... truncated ...
```
