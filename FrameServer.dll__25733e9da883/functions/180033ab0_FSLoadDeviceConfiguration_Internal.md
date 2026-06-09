# FSLoadDeviceConfiguration_Internal

- ea: `0x180033ab0`
- end: `0x1800346f8`
- name: `FSLoadDeviceConfiguration_Internal`
- size: `3144`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180032fb4`

## callees

- `0x180003e20`
- `0x1800041f0`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180009fac`
- `0x18000a91c`
- `0x1800175bc`
- `0x180017bb4`
- `0x1800269b0`
- `0x18002a920`
- `0x18002b654`
- `0x18002db74`
- `0x18002f648`
- `0x180030f00`
- `0x180033458`
- `0x180033ab0`
- `0x1800347e4`
- `0x180034a84`
- `0x1800368c0`
- `0x180036ca4`
- `0x180036e5c`
- `0x18004d714`
- `0x18004da70`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800344f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800344f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034693`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033ef9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034626`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033ef9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034626`

## string_xrefs

- `0x18003424b`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1800342f9`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadDeviceConfiguration_Internal(struct IFSConfigurationKey *a1, struct IFSConfiguration **a2)
{
  unsigned int v2; // esi
  char v4; // r13
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 *p_pv; // rcx
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  const struct std::nothrow_t *v13; // rdx
  GuidTrace *v14; // rax
  const char *String; // rax
  int v16; // edx
  int v17; // r8d
  unsigned __int16 *v18; // rax
  char v19; // al
  __int64 v20; // rax
  void *v21; // rcx
  __int64 *v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 *v26; // rcx
  unsigned int i; // edi
  const struct std::nothrow_t *v28; // rdx
  const char *v29; // rax
  void *v30; // rdx
  struct IFSConfiguration *v31; // rcx
  struct IFSConfiguration *v32; // rax
  __int64 v33; // rdx
  __int64 v35; // rax
  char v36; // di
  _DWORD *v37; // rdi
  void *v38; // rcx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rsi
  __int64 v42; // rdi
  __int64 v43; // rbx
  int v44; // eax
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v46; // rdx
  void *v47; // rcx
  unsigned __int16 *v48; // rdi
  int v49; // eax
  const struct std::nothrow_t *v50; // rdx
  __int64 v51; // rdx
  unsigned __int16 *v52; // rax
  void *v53; // rcx
  int v54; // eax
  __int64 v55; // rdx
  void *v56; // rcx
  const struct std::nothrow_t *v57; // rdx
  const char *v58; // rax
  struct IFSConfiguration *v59; // [rsp+40h] [rbp-59h] BYREF
  struct IFSConfigurationKey *v60; // [rsp+48h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v62; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v63; // [rsp+5Ch] [rbp-3Dh] BYREF
  LPVOID v64; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v65; // [rsp+68h] [rbp-31h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v67; // [rsp+80h] [rbp-19h]
  _BYTE v68[32]; // [rsp+88h] [rbp-11h] BYREF
  struct _DEVPROPKEY v69; // [rsp+A8h] [rbp+Fh] BYREF

  v2 = 0;
  v4 = 0;
  LODWORD(v65) = 0;
  v59 = 0;
  v60 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v65 = 0;
    if ( !a1 )
    {
      v6 = -2147024809;
      v7 = -2147024809;
      if ( !g_wppLevels )
      {
LABEL_6:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
        p_pv = (__int64 *)&v65;
LABEL_7:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(p_pv);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v59);
LABEL_152:
        if ( !byte_18010EC4D )
          return (unsigned int)v7;
        v33 = 127;
        goto LABEL_64;
      }
      v8 = 101;
LABEL_5:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
      goto LABEL_6;
    }
    if ( !a2 )
    {
      v6 = -2147467261;
      v7 = -2147467261;
      if ( !g_wppLevels )
        goto LABEL_6;
      v8 = 102;
      goto LABEL_5;
    }
    *a2 = 0;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v10 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
      v11 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
      v12 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
      (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
      WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, v11, v10);
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v59);
    v69.pid = 2;
    v69.fmtid = FrameServerConfigurationFMTGUIDV2;
    v7 = FSLoadDeviceConfiguration_Base(a1, &v69, 0);
    if ( v7 < 0 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v59);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v14 = GuidTrace::GuidTrace((GuidTrace *)v68, &FrameServerConfigurationFMTGUID);
        String = GuidTrace::GetString(v14);
        WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, v17, v7, (__int64)String);
        v4 = 1;
      }
      if ( (v4 & 1) != 0 )
        FSString::~FSString((FSString *)v68, v13);
      v7 = 0;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v60);
    v18 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    if ( (int)FSLoadGlobalConfigurationByName(v18) < 0 )
    {
      v32 = v59;
    }
    else
    {
      v19 = byte_18010EC4D;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v20 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 105, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v20);
        v19 = byte_18010EC4D;
      }
      if ( v59 )
      {
        v63 = 0;
        pv = 0;
        v62 = 0;
        if ( (unsigned __int8)v19 >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 106, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids);
        *(_QWORD *)&v69.fmtid.Data1 = &pv;
        *(_QWORD *)v69.fmtid.Data4 = 0;
        LOBYTE(v69.pid) = 1;
        v7 = FSMergeCameraControlConfigurations((__int64 *)v60, (__int64 *)v59, (LPVOID *)v69.fmtid.Data4, &v63);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v69);
        if ( v7 < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v7);
          v21 = pv;
          pv = 0;
          if ( v21 )
            CoTaskMemFree(v21);
LABEL_30:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
          v22 = (__int64 *)&v65;
          goto LABEL_150;
        }
        v23 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, unsigned int *))(*(_QWORD *)v59 + 240LL))(v59, &v62);
        v7 = v23;
        if ( v23 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_35:
            v25 = pv;
            pv = 0;
            if ( v25 )
              CoTaskMemFree(v25);
            wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
            v26 = (__int64 *)&v65;
            goto LABEL_38;
          }
          v24 = 108;
LABEL_34:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v23);
          goto LABEL_35;
        }
        for ( i = 0; i < v62; ++i )
        {
          v67 = 0;
          v69.fmtid = GUID_00000000_0000_0000_0000_000000000000;
          *(_OWORD *)pvar = 0;
          if ( (*(int (__fastcall **)(struct IFSConfiguration *, _QWORD, struct _DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v59 + 248LL))(
                 v59,
                 i,
                 &v69,
                 pvar) >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *, struct _DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v60 + 144LL))(
                   v60,
                   &v69,
                   pvar);
            if ( v7 < 0 )
            {
              if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
              {
                GuidTrace::GuidTrace((GuidTrace *)v68, &v69.fmtid);
                if ( byte_18010EC4D )
                {
                  v29 = GuidTrace::GetString((GuidTrace *)v68);
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    109,
                    (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                    v7,
                    (__int64)v29);
                }
                FSString::~FSString((FSString *)v68, v28);
              }
              v7 = 0;
            }
          }
          PropVariantClear(pvar);
        }
        v30 = pv;
        if ( pv && v63 )
        {
          v23 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *, __int64 *, LPVOID))(*(_QWORD *)v60 + 208LL))(
                  v60,
                  FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
                  pv);
          v7 = v23;
          if ( v23 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_35;
            v24 = 110;
            goto LABEL_34;
          }
          v30 = pv;
        }
        pv = 0;
        if ( v30 )
          CoTaskMemFree(v30);
      }
      v31 = v59;
      v32 = v60;
      v59 = v60;
      v60 = v31;
    }
    if ( !v32 )
    {
      v7 = -1072875819;
      if ( g_wppLevels >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -1072875819);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v59);
      goto LABEL_62;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v65);
    v69.pid = 2;
    v69.fmtid = FrameServerConfigurationPublicFMTGUID;
    if ( (int)FSLoadDeviceConfiguration_Base(a1, &v69, 1) >= 0 )
    {
      v64 = 0;
      v63 = 0;
      v35 = *v65;
      pvar[0] = &v64;
      pvar[1] = 0;
      LOBYTE(v67) = 1;
      if ( (*(int (__fastcall **)(__int64 *, __int64 *, PROPVARIANT *, unsigned int *))(v35 + 128))(
             v65,
             FSM_WSEOPTIN_CONFIGURATION_INFO,
             &pvar[1],
             &v63) < 0
        || (v36 = 1, v63 < 0x18) )
      {
        v36 = 0;
      }
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)pvar);
      if ( !v36 )
        goto LABEL_74;
      v37 = (char *)v64 + 8;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_ddddi(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          112,
          (*v37 >> 1) & 1,
          *(unsigned int *)v64,
          *((_DWORD *)v64 + 1),
          *v37 & 1,
          (*v37 >> 1) & 1,
          *((_QWORD *)v64 + 2));
      if ( (*(_BYTE *)v37 & 2) != 0 )
LABEL_74:
        (*(void (__fastcall **)(struct IFSConfiguration *, __int64 *))(*(_QWORD *)v59 + 152LL))(
          v59,
          MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS);
      v38 = v64;
      v64 = 0;
      if ( v38 )
        CoTaskMemFree(v38);
    }
    *a2 = v59;
    v59 = 0;
    goto LABEL_30;
  }
  pv = 0;
  LODWORD(v65) = 0;
  v63 = 0;
  *(_QWORD *)&v69.fmtid.Data1 = 0;
  if ( !a1 )
  {
    v39 = -2147024809;
    v7 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_82:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
      p_pv = (__int64 *)&pv;
      goto LABEL_7;
    }
    v40 = 113;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v39);
    goto LABEL_82;
  }
  if ( !a2 )
  {
    v39 = -2147467261;
    v7 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_82;
    v40 = 114;
    goto LABEL_81;
  }
  *a2 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v41 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
    v42 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v43 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
    WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v43, v42, v41);
    v2 = 0;
  }
  v62 = 0;
  v44 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v62);
  v7 = v44;
  if ( v44 >= 0 )
  {
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v64, v62);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=((void **)&v69, unique);
    v47 = v64;
    v64 = 0;
    if ( v47 )
      operator delete(v47, v46);
    v48 = *(unsigned __int16 **)&v69.fmtid.Data1;
    if ( !*(_QWORD *)&v69.fmtid.Data1 )
    {
      v7 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v69.fmtid.Data1 + 117,
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -2147024882);
      goto LABEL_82;
    }
    v49 = FSTagPackageFamilyName(
            L"FRAMESERVER_CONFIGURATION_ALL_APPS",
            *(unsigned __int16 **)&v69.fmtid.Data1,
            v62,
            &v62);
    v7 = v49;
    if ( v49 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_101;
      v51 = 118;
      goto LABEL_100;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v60);
    v52 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v49 = FSCreateConfigurationKey(v52, 0, v48, &v60);
    v7 = v49;
    if ( v49 < 0 )
    {
      if ( g_wppLevels )
      {
        v51 = 119;
LABEL_100:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v51, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v49);
        goto LABEL_101;
      }
      goto LABEL_101;
    }
    if ( !(*(unsigned int (__fastcall **)(struct IFSConfigurationKey *, struct IFSConfigurationKey *))(*(_QWORD *)v60 + 24LL))(
            v60,
            a1) )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v59);
      v49 = FSLoadDeviceConfigurationByKey_Internal(a1, &v59);
      v7 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels >= 8u )
        {
          v51 = 120;
          goto LABEL_100;
        }
LABEL_101:
        if ( v48 )
          operator delete(v48, v50);
        goto LABEL_91;
      }
      goto LABEL_146;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v59);
    if ( (int)FSLoadDeviceConfigurationByKey_Internal(v60, &v59) < 0 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v59);
      v49 = FSLoadDeviceConfigurationByKey_Internal(a1, &v59);
      v7 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels >= 8u )
        {
          v51 = 121;
          goto LABEL_100;
        }
        goto LABEL_101;
      }
      goto LABEL_146;
    }
    v49 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 **))(*(_QWORD *)v59 + 240LL))(v59, &v65);
    v7 = v49;
    if ( v49 < 0 )
    {
      if ( g_wppLevels )
      {
        v51 = 122;
        goto LABEL_100;
      }
      goto LABEL_101;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&pv);
    if ( (int)FSLoadDeviceConfigurationByKey_Internal(a1, (struct IFSConfiguration **)&pv) >= 0 )
    {
      pvar[0] = &v64;
      v62 = 0;
      v64 = 0;
      pvar[1] = 0;
      LOBYTE(v67) = 1;
      v7 = FSMergeCameraControlConfigurations((__int64 *)v59, (__int64 *)pv, &pvar[1], &v62);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)pvar);
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v7);
        v53 = v64;
        v64 = 0;
        if ( v53 )
          CoTaskMemFree(v53);
        goto LABEL_147;
      }
      v54 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)pv + 240LL))(pv, &v63);
      v7 = v54;
      if ( v54 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_127;
        v55 = 124;
        goto LABEL_126;
      }
      if ( v63 )
      {
        do
        {
          v67 = 0;
          v69.fmtid = GUID_00000000_0000_0000_0000_000000000000;
          *(_OWORD *)pvar = 0;
          if ( (*(int (__fastcall **)(LPVOID, _QWORD, struct _DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)pv + 248LL))(
                 pv,
                 v2,
                 &v69,
                 pvar) >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, struct _DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v59 + 144LL))(
                   v59,
                   &v69,
                   pvar);
            if ( v7 < 0 )
            {
              if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
              {
                GuidTrace::GuidTrace((GuidTrace *)v68, &v69.fmtid);
                if ( byte_18010EC4D )
                {
                  v58 = GuidTrace::GetString((GuidTrace *)v68);
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    125,
                    (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                    v7,
                    (__int64)v58);
                }
                FSString::~FSString((FSString *)v68, v57);
              }
              v7 = 0;
            }
          }
          PropVariantClear(pvar);
          ++v2;
        }
        while ( v2 < v63 );
      }
      v50 = (const struct std::nothrow_t *)v64;
      if ( v64 && v62 )
      {
        v54 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 *, LPVOID))(*(_QWORD *)v59 + 208LL))(
                v59,
                FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
                v64);
        v7 = v54;
        if ( v54 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_127:
            v56 = v64;
            v64 = 0;
            if ( v56 )
              CoTaskMemFree(v56);
            goto LABEL_101;
          }
          v55 = 126;
LABEL_126:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v54);
          goto LABEL_127;
        }
        v50 = (const struct std::nothrow_t *)v64;
      }
      v64 = 0;
      if ( v50 )
        CoTaskMemFree(v50);
    }
LABEL_146:
    *a2 = v59;
    v59 = 0;
LABEL_147:
    if ( v48 )
      operator delete(v48, v50);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
    v22 = (__int64 *)&pv;
LABEL_150:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v22);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v59);
    if ( v7 >= 0 )
      goto LABEL_62;
    goto LABEL_151;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v44);
LABEL_91:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v60);
  v26 = (__int64 *)&pv;
LABEL_38:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v26);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v59);
LABEL_151:
  if ( v7 != -1072875819 )
    goto LABEL_152;
LABEL_62:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v33 = 128;
LABEL_64:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v33,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033ab0  mov     [rsp-8+arg_10], rbx
0x180033ab5  mov     [rsp-8+arg_18], rsi
0x180033aba  push    rbp
0x180033abb  push    rdi
0x180033abc  push    r12
0x180033abe  push    r13
0x180033ac0  push    r14
0x180033ac2  lea     rbp, [rsp-37h]
0x180033ac7  sub     rsp, 0D0h
0x180033ace  mov     rax, cs:__security_cookie
0x180033ad5  xor     rax, rsp
0x180033ad8  mov     [rbp+57h+var_30], rax
0x180033adc  xor     esi, esi
0x180033ade  mov     r12, rdx
0x180033ae1  mov     r13d, esi
0x180033ae4  mov     dword ptr [rbp+57h+var_88], esi
0x180033ae7  mov     r14, rcx
0x180033aea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x180033af1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x180033af6  mov     [rbp+57h+var_B0], rsi
0x180033afa  mov     [rbp+57h+var_A8], rsi
0x180033afe  test    al, al
0x180033b00  jz      loc_180034150
0x180033b06  mov     [rbp+57h+var_88], rsi
0x180033b0a  test    r14, r14
0x180033b0d  jnz     short loc_180033B60
0x180033b0f  mov     eax, 80070057h
0x180033b14  mov     ebx, eax
0x180033b16  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033b1d  jb      short loc_180033B40
0x180033b1f  lea     edx, [rsi+65h]
0x180033b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b29  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033b30  xor     r9d, r9d
0x180033b33  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180033b37  mov     rcx, [rcx+10h]
0x180033b3b  call    WPP_SF_qD
0x180033b40  lea     rcx, [rbp+57h+var_A8]; void *
0x180033b44  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033b49  lea     rcx, [rbp+57h+var_88]; void *
0x180033b4d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033b52  lea     rcx, [rbp+57h+var_B0]; void *
0x180033b56  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033b5b  jmp     loc_1800346E1
0x180033b60  test    r12, r12
0x180033b63  jnz     short loc_180033B7C
0x180033b65  mov     eax, 80004003h
0x180033b6a  mov     ebx, eax
0x180033b6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033b73  jb      short loc_180033B40
0x180033b75  lea     edx, [r12+66h]
0x180033b7a  jmp     short loc_180033B22
0x180033b7c  mov     [r12], rsi
0x180033b80  cmp     cs:byte_18010EC4D, 8
0x180033b87  jb      short loc_180033BFA
0x180033b89  mov     rax, [r14]
0x180033b8c  mov     rcx, r14
0x180033b8f  mov     rax, [rax+48h]
0x180033b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b98  mov     rcx, [r14]
0x180033b9b  mov     rsi, rax
0x180033b9e  mov     rax, [rcx+38h]
0x180033ba2  mov     rcx, r14
0x180033ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033baa  mov     rcx, [r14]
0x180033bad  mov     rdi, rax
0x180033bb0  mov     rax, [rcx+40h]
0x180033bb4  mov     rcx, r14
0x180033bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bbc  mov     rcx, [r14]
0x180033bbf  mov     rbx, rax
0x180033bc2  mov     rax, [rcx+30h]
0x180033bc6  mov     rcx, r14
0x180033bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bd5  mov     edx, 67h ; 'g'
0x180033bda  mov     [rsp+0F0h+var_C0], rsi; __int64
0x180033bdf  mov     r9, rax
0x180033be2  mov     [rsp+0F0h+var_C8], rdi; __int64
0x180033be7  mov     [rsp+0F0h+var_D0], rbx; __int64
0x180033bec  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180033bf3  call    WPP_SF_SSSS
0x180033bf8  xor     esi, esi
0x180033bfa  lea     rcx, [rbp+57h+var_B0]
0x180033bfe  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180033c03  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationFMTGUIDV2@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationFMTGUIDV2 ...
0x180033c0a  lea     r9, [rbp+57h+var_B0]
0x180033c0e  mov     [rbp+57h+var_38], 2
0x180033c15  xor     r8d, r8d; bool
0x180033c18  lea     rdx, [rbp+57h+var_48]; struct _DEVPROPKEY *
0x180033c1c  mov     rcx, r14; struct IFSConfigurationKey *
0x180033c1f  movdqu  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x180033c24  call    FSLoadDeviceConfiguration_Base
0x180033c29  mov     ebx, eax
0x180033c2b  test    eax, eax
0x180033c2d  jns     short loc_180033C8B
0x180033c2f  lea     rcx, [rbp+57h+var_B0]
0x180033c33  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180033c38  cmp     cs:byte_18010EC4D, 8
0x180033c3f  jb      short loc_180033C7A
0x180033c41  lea     rdx, ?FrameServerConfigurationFMTGUID@@3U_GUID@@B; struct _GUID *
0x180033c48  lea     rcx, [rbp+57h+var_68]; this
0x180033c4c  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180033c51  mov     rcx, rax; this
0x180033c54  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180033c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c60  mov     r9d, ebx
0x180033c63  mov     [rsp+0F0h+var_D0], rax
0x180033c68  mov     rcx, [rcx+0D8h]
0x180033c6f  call    WPP_SF_Dsd
0x180033c74  mov     r13d, 1
0x180033c7a  test    r13b, 1
0x180033c7e  jz      short loc_180033C89
0x180033c80  lea     rcx, [rbp+57h+var_68]; this
0x180033c84  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180033c89  mov     ebx, esi
0x180033c8b  lea     rcx, [rbp+57h+var_A8]
0x180033c8f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180033c94  mov     rax, [r14]
0x180033c97  mov     rcx, r14
0x180033c9a  mov     rax, [rax+38h]
0x180033c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ca3  lea     r9, [rbp+57h+var_A8]
0x180033ca7  mov     rcx, rax; unsigned __int16 *
0x180033caa  call    FSLoadGlobalConfigurationByName
0x180033caf  test    eax, eax
0x180033cb1  js      loc_180033F7E
0x180033cb7  mov     al, cs:byte_18010EC4D
0x180033cbd  cmp     al, 8
0x180033cbf  jb      short loc_180033CF8
0x180033cc1  mov     rax, [r14]
0x180033cc4  mov     rcx, r14
0x180033cc7  mov     rax, [rax+38h]
0x180033ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cd7  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033cde  mov     edx, 69h ; 'i'
0x180033ce3  mov     r9, rax
0x180033ce6  mov     rcx, [rcx+0D8h]
0x180033ced  call    WPP_SF_S
0x180033cf2  mov     al, cs:byte_18010EC4D
0x180033cf8  cmp     [rbp+57h+var_B0], rsi
0x180033cfc  jz      loc_180033F6C
0x180033d02  mov     [rbp+57h+var_94], esi
0x180033d05  mov     [rbp+57h+pv], rsi
0x180033d09  mov     [rbp+57h+var_98], esi
0x180033d0c  cmp     al, 8
0x180033d0e  jb      short loc_180033D2F
0x180033d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d17  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033d1e  mov     edx, 6Ah ; 'j'
0x180033d23  mov     rcx, [rcx+0D8h]
0x180033d2a  call    WPP_SF_
0x180033d2f  mov     rdx, [rbp+57h+var_B0]
0x180033d33  lea     rax, [rbp+57h+pv]
0x180033d37  mov     rcx, [rbp+57h+var_A8]
0x180033d3b  lea     r9, [rbp+57h+var_94]
0x180033d3f  lea     r8, [rbp+57h+var_48.Data4]
0x180033d43  mov     qword ptr [rbp+57h+var_48.Data1], rax
0x180033d47  mov     qword ptr [rbp+57h+var_48.Data4], rsi
0x180033d4b  mov     byte ptr [rbp+57h+var_38], 1
0x180033d4f  call    FSMergeCameraControlConfigurations
0x180033d54  lea     rcx, [rbp+57h+var_48]
0x180033d58  mov     ebx, eax
0x180033d5a  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180033d5f  mov     eax, ebx
0x180033d61  shr     eax, 1Fh
0x180033d64  test    al, al
0x180033d66  jz      short loc_180033DB9
0x180033d68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033d6f  jb      short loc_180033D94
0x180033d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d78  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033d7f  mov     edx, 6Bh ; 'k'
0x180033d84  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180033d88  xor     r9d, r9d
0x180033d8b  mov     rcx, [rcx+10h]
0x180033d8f  call    WPP_SF_qD
0x180033d94  mov     rcx, [rbp+57h+pv]; pv
0x180033d98  mov     [rbp+57h+pv], rsi
0x180033d9c  test    rcx, rcx
0x180033d9f  jz      short loc_180033DA7
0x180033da1  call    cs:__imp_CoTaskMemFree
0x180033da7  lea     rcx, [rbp+57h+var_A8]; void *
0x180033dab  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033db0  lea     rcx, [rbp+57h+var_88]
0x180033db4  jmp     loc_1800346BF
0x180033db9  mov     rcx, [rbp+57h+var_B0]
0x180033dbd  lea     rdx, [rbp+57h+var_98]
0x180033dc1  mov     rax, [rcx]
0x180033dc4  mov     rax, [rax+0F0h]
0x180033dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dd0  mov     ebx, eax
0x180033dd2  test    eax, eax
0x180033dd4  jns     short loc_180033E35
0x180033dd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033ddd  jb      short loc_180033E02
0x180033ddf  mov     edx, 6Ch ; 'l'
0x180033de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180033deb  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033df2  xor     r9d, r9d
0x180033df5  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180033df9  mov     rcx, [rcx+10h]
0x180033dfd  call    WPP_SF_qD
0x180033e02  mov     rcx, [rbp+57h+pv]; pv
0x180033e06  mov     [rbp+57h+pv], rsi
0x180033e0a  test    rcx, rcx
0x180033e0d  jz      short loc_180033E15
0x180033e0f  call    cs:__imp_CoTaskMemFree
0x180033e15  lea     rcx, [rbp+57h+var_A8]; void *
0x180033e19  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033e1e  lea     rcx, [rbp+57h+var_88]; void *
0x180033e22  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033e27  lea     rcx, [rbp+57h+var_B0]; void *
0x180033e2b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180033e30  jmp     loc_1800346D5
0x180033e35  mov     edi, esi
0x180033e37  cmp     [rbp+57h+var_98], esi
0x180033e3a  jbe     loc_180033F0A
0x180033e40  mov     rcx, [rbp+57h+var_B0]
0x180033e44  lea     r9, [rbp+57h+pvar]
0x180033e48  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180033e4f  lea     r8, [rbp+57h+var_48]
0x180033e53  xor     eax, eax
0x180033e55  xorps   xmm1, xmm1
0x180033e58  mov     [rbp+57h+var_70], rax
0x180033e5c  mov     edx, edi
0x180033e5e  movdqu  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x180033e63  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x180033e67  mov     rax, [rcx]
0x180033e6a  mov     rax, [rax+0F8h]
0x180033e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e76  test    eax, eax
0x180033e78  js      short loc_180033EF5
0x180033e7a  mov     rcx, [rbp+57h+var_A8]
0x180033e7e  lea     r8, [rbp+57h+pvar]
0x180033e82  lea     rdx, [rbp+57h+var_48]
0x180033e86  mov     rax, [rcx]
0x180033e89  mov     rax, [rax+90h]
0x180033e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e95  mov     ebx, eax
0x180033e97  test    eax, eax
0x180033e99  jns     short loc_180033EF5
0x180033e9b  cmp     cs:byte_18010EC4D, 10h
0x180033ea2  jb      short loc_180033EF3
0x180033ea4  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x180033ea8  lea     rcx, [rbp+57h+var_68]; this
0x180033eac  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180033eb1  cmp     cs:byte_18010EC4D, 1
0x180033eb8  jb      short loc_180033EEA
0x180033eba  lea     rcx, [rbp+57h+var_68]; this
0x180033ebe  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180033ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180033eca  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180033ed1  mov     edx, 6Dh ; 'm'
0x180033ed6  mov     [rsp+0F0h+var_D0], rax
0x180033edb  mov     r9d, ebx
0x180033ede  mov     rcx, [rcx+0D8h]
0x180033ee5  call    WPP_SF_Ds
0x180033eea  lea     rcx, [rbp+57h+var_68]; this
0x180033eee  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180033ef3  mov     ebx, esi
0x180033ef5  lea     rcx, [rbp+57h+pvar]; pvar
0x180033ef9  call    cs:__imp_PropVariantClear
0x180033eff  inc     edi
0x180033f01  cmp     edi, [rbp+57h+var_98]
0x180033f04  jb      loc_180033E40
0x180033f0a  mov     rdx, [rbp+57h+pv]
0x180033f0e  test    rdx, rdx
0x180033f11  jz      short loc_180033F5A
0x180033f13  mov     r9d, [rbp+57h+var_94]
0x180033f17  test    r9d, r9d
0x180033f1a  jz      short loc_180033F5A
0x180033f1c  mov     rcx, [rbp+57h+var_A8]
0x180033f20  mov     r8, rdx
0x180033f23  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x180033f2a  mov     rax, [rcx]
0x180033f2d  mov     rax, [rax+0D0h]
0x180033f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f39  mov     ebx, eax
0x180033f3b  test    eax, eax
0x180033f3d  jns     short loc_180033F56
0x180033f3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033f46  jb      loc_180033E02
0x180033f4c  mov     edx, 6Eh ; 'n'
0x180033f51  jmp     loc_180033DE4
0x180033f56  mov     rdx, [rbp+57h+pv]
0x180033f5a  mov     [rbp+57h+pv], rsi
0x180033f5e  test    rdx, rdx
0x180033f61  jz      short loc_180033F6C
0x180033f63  mov     rcx, rdx; pv
0x180033f66  call    cs:__imp_CoTaskMemFree
0x180033f6c  mov     rcx, [rbp+57h+var_B0]
0x180033f70  mov     rax, [rbp+57h+var_A8]
0x180033f74  mov     [rbp+57h+var_B0], rax
0x180033f78  mov     [rbp+57h+var_A8], rcx
0x180033f7c  jmp     short loc_180033F82
0x180033f7e  mov     rax, [rbp+57h+var_B0]
0x180033f82  test    rax, rax
0x180033f85  jnz     loc_18003402A
  ... truncated ...
```
