# FSLoadDeviceConfiguration_Internal

- ea: `0x180038f94`
- end: `0x180039bc8`
- name: `FSLoadDeviceConfiguration_Internal`
- size: `3124`
- prototype: `__int64 __fastcall(struct IFSConfigurationKey *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038564`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x18000723c`
- `0x18000d024`
- `0x18000d1e0`
- `0x18000d3b0`
- `0x18000d3d8`
- `0x18000d498`
- `0x18000e25c`
- `0x18000e66c`
- `0x180011438`
- `0x18002fa3c`
- `0x18002fd04`
- `0x180036290`
- `0x180036cb8`
- `0x18003896c`
- `0x180038f94`
- `0x180039cb4`
- `0x18003a48c`
- `0x18003beb0`
- `0x18003bf2c`
- `0x18003c178`
- `0x18003c32c`
- `0x180042988`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800393dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039afa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800393dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039afa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800392f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003944a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003961b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800392f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003944a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003961b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800399c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039b67`

## string_xrefs

- `0x180039732`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1800397e0`: `FRAMESERVER_CONFIGURATION_ALL_APPS`

## pseudocode

```c
__int64 __fastcall FSLoadDeviceConfiguration_Internal(struct IFSConfigurationKey *a1, struct IFSConfiguration **a2)
{
  char v3; // r13
  int v5; // eax
  int v6; // edi
  __int64 v7; // rdx
  __int64 *p_pv; // rcx
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  const struct std::nothrow_t *v12; // rdx
  GuidTrace *v13; // rax
  const char *String; // rax
  int v15; // edx
  int v16; // r8d
  unsigned __int16 *v17; // rax
  char v18; // al
  __int64 v19; // rax
  void *v20; // rcx
  __int64 *v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  void *v24; // rcx
  __int64 *v25; // rcx
  unsigned int i; // ebx
  const struct std::nothrow_t *v27; // rdx
  const char *v28; // rax
  void *v29; // rdx
  unsigned __int16 *v30; // rcx
  void *v31; // rax
  __int64 v32; // rdx
  __int64 v34; // rax
  char v35; // bl
  _DWORD *v36; // rbx
  void *v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rbx
  int v43; // eax
  __int64 v44; // rdx
  const struct std::nothrow_t *unique; // rax
  struct IFSConfigurationKey *v46; // rcx
  unsigned __int16 *v47; // rax
  void *v48; // rcx
  int v49; // eax
  __int64 v50; // rdx
  void *v51; // rcx
  unsigned int j; // ebx
  const struct std::nothrow_t *v53; // rdx
  const char *v54; // rax
  void *v55; // rdx
  struct IFSConfiguration *v56; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v57; // [rsp+48h] [rbp-61h] BYREF
  struct IFSConfigurationKey *v58; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v60; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v61; // [rsp+64h] [rbp-45h] BYREF
  int v62; // [rsp+68h] [rbp-41h] BYREF
  PROPVARIANT v63[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v64; // [rsp+80h] [rbp-29h]
  _BYTE v65[32]; // [rsp+90h] [rbp-19h] BYREF
  struct _GUID v66; // [rsp+B0h] [rbp+7h] BYREF
  PROPVARIANT pvar[2]; // [rsp+C0h] [rbp+17h] BYREF
  __int64 v68; // [rsp+D0h] [rbp+27h]

  v3 = 0;
  v62 = 0;
  v56 = 0;
  v58 = 0;
  v57 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( !a1 )
    {
      v5 = -2147024809;
      v6 = -2147024809;
      if ( !g_wppLevels )
      {
LABEL_6:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v57);
        p_pv = (__int64 *)&v58;
LABEL_7:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(p_pv);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v56);
LABEL_148:
        if ( !byte_18005E5A5 )
          return (unsigned int)v6;
        v32 = 127;
        goto LABEL_64;
      }
      v7 = 101;
LABEL_5:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v5);
      goto LABEL_6;
    }
    if ( !a2 )
    {
      v5 = -2147467261;
      v6 = -2147467261;
      if ( !g_wppLevels )
        goto LABEL_6;
      v7 = 102;
      goto LABEL_5;
    }
    *a2 = 0;
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v9 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
      v10 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
      v11 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
      (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
      WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v11, v10, v9);
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
    LODWORD(v68) = 2;
    *(GUID *)pvar = FrameServerConfigurationFMTGUIDV2;
    v6 = FSLoadDeviceConfiguration_Base(a1, (struct _DEVPROPKEY *)pvar, 0);
    if ( v6 < 0 )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v13 = GuidTrace::GuidTrace((GuidTrace *)v65, &FrameServerConfigurationFMTGUID);
        String = GuidTrace::GetString(v13);
        WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 27), v15, v16, v6, (__int64)String);
        v3 = 1;
      }
      if ( (v3 & 1) != 0 )
        FSString::~FSString((FSString *)v65, v12);
      v6 = 0;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v57);
    v17 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    if ( (int)FSLoadGlobalConfigurationByName(v17) < 0 )
    {
      v31 = v56;
    }
    else
    {
      v18 = byte_18005E5A5;
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v19 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 105, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v19);
        v18 = byte_18005E5A5;
      }
      if ( v56 )
      {
        v61 = 0;
        pv = 0;
        v60 = 0;
        if ( (unsigned __int8)v18 >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 106, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids);
        pvar[0] = &pv;
        pvar[1] = 0;
        LOBYTE(v68) = 1;
        v6 = FSMergeCameraControlConfigurations(v57, v56, &pvar[1], &v61);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)pvar);
        if ( v6 < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
          v20 = pv;
          pv = 0;
          if ( v20 )
            CoTaskMemFree(v20);
LABEL_30:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v57);
          v21 = (__int64 *)&v58;
          goto LABEL_146;
        }
        v22 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, unsigned int *))(*(_QWORD *)v56 + 240LL))(v56, &v60);
        v6 = v22;
        if ( v22 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_35:
            v24 = pv;
            pv = 0;
            if ( v24 )
              CoTaskMemFree(v24);
            wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v57);
            v25 = (__int64 *)&v58;
            goto LABEL_38;
          }
          v23 = 108;
LABEL_34:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v22);
          goto LABEL_35;
        }
        for ( i = 0; i < v60; ++i )
        {
          v68 = 0;
          v66 = GUID_00000000_0000_0000_0000_000000000000;
          *(_OWORD *)pvar = 0;
          if ( (*(int (__fastcall **)(struct IFSConfiguration *, _QWORD, struct _GUID *, PROPVARIANT *))(*(_QWORD *)v56 + 248LL))(
                 v56,
                 i,
                 &v66,
                 pvar) >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct _GUID *, PROPVARIANT *))(*(_QWORD *)v57 + 144LL))(
                   v57,
                   &v66,
                   pvar);
            if ( v6 < 0 )
            {
              if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
              {
                GuidTrace::GuidTrace((GuidTrace *)v63, &v66);
                if ( byte_18005E5A5 )
                {
                  v28 = GuidTrace::GetString((GuidTrace *)v63);
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    109,
                    (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                    v6,
                    (__int64)v28);
                }
                FSString::~FSString((FSString *)v63, v27);
              }
              v6 = 0;
            }
          }
          PropVariantClear(pvar);
        }
        v29 = pv;
        if ( pv && v61 )
        {
          v22 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64 *, LPVOID))(*(_QWORD *)v57 + 208LL))(
                  v57,
                  FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
                  pv);
          v6 = v22;
          if ( v22 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_35;
            v23 = 110;
            goto LABEL_34;
          }
          v29 = pv;
        }
        pv = 0;
        if ( v29 )
          CoTaskMemFree(v29);
      }
      v30 = (unsigned __int16 *)v56;
      v31 = v57;
      v56 = (struct IFSConfiguration *)v57;
      v57 = v30;
    }
    if ( !v31 )
    {
      v6 = -1072875819;
      if ( g_wppLevels >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -1072875819);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v57);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v58);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v56);
      goto LABEL_62;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v58);
    LODWORD(v68) = 2;
    *(GUID *)pvar = FrameServerConfigurationPublicFMTGUID;
    if ( (int)FSLoadDeviceConfiguration_Base(a1, (struct _DEVPROPKEY *)pvar, 1) >= 0 )
    {
      *(_QWORD *)&v66.Data1 = 0;
      v61 = 0;
      v34 = *(_QWORD *)v58;
      pvar[0] = &v66;
      pvar[1] = 0;
      LOBYTE(v68) = 1;
      if ( (*(int (__fastcall **)(struct IFSConfigurationKey *, __int64 *, PROPVARIANT *, unsigned int *))(v34 + 128))(
             v58,
             FSM_WSEOPTIN_CONFIGURATION_INFO,
             &pvar[1],
             &v61) < 0
        || (v35 = 1, v61 < 0x18) )
      {
        v35 = 0;
      }
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)pvar);
      if ( !v35 )
        goto LABEL_74;
      v36 = (_DWORD *)(*(_QWORD *)&v66.Data1 + 8LL);
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_ddddi(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          112,
          (*v36 >> 1) & 1,
          **(unsigned int **)&v66.Data1,
          *(_DWORD *)(*(_QWORD *)&v66.Data1 + 4LL),
          *v36 & 1,
          (*v36 >> 1) & 1,
          *(_QWORD *)(*(_QWORD *)&v66.Data1 + 16LL));
      if ( (*(_BYTE *)v36 & 2) != 0 )
LABEL_74:
        (*(void (__fastcall **)(struct IFSConfiguration *, __int64 *))(*(_QWORD *)v56 + 152LL))(
          v56,
          MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS);
      v37 = *(void **)&v66.Data1;
      *(_QWORD *)&v66.Data1 = 0;
      if ( v37 )
        CoTaskMemFree(v37);
    }
    *a2 = v56;
    v56 = 0;
    goto LABEL_30;
  }
  pv = 0;
  v62 = 0;
  v61 = 0;
  if ( !a1 )
  {
    v38 = -2147024809;
    v6 = -2147024809;
    if ( !g_wppLevels )
    {
LABEL_82:
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v57);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v58);
      p_pv = (__int64 *)&pv;
      goto LABEL_7;
    }
    v39 = 113;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v38);
    goto LABEL_82;
  }
  if ( !a2 )
  {
    v38 = -2147467261;
    v6 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_82;
    v39 = 114;
    goto LABEL_81;
  }
  *a2 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v40 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 72LL))(a1);
    v41 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v42 = (*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 64LL))(a1);
    (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 48LL))(a1);
    WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v42, v41, v40);
  }
  v60 = 0;
  v43 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", 0, 0, &v60);
  v6 = v43;
  if ( v43 >= 0 )
  {
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v66, v60);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v57, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v66);
    if ( !v57 )
    {
      v6 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)v57 + 117),
          &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
          0,
          -2147024882);
      goto LABEL_82;
    }
    v43 = FSTagPackageFamilyName(L"FRAMESERVER_CONFIGURATION_ALL_APPS", v57, v60, &v60);
    v6 = v43;
    if ( v43 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_92;
      v44 = 118;
      goto LABEL_91;
    }
    v46 = v58;
    v58 = 0;
    if ( v46 )
      (*(void (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)v46 + 16LL))(v46);
    v47 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFSConfigurationKey *))(*(_QWORD *)a1 + 56LL))(a1);
    v43 = FSCreateConfigurationKey(v47);
    v6 = v43;
    if ( v43 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_92;
      v44 = 119;
      goto LABEL_91;
    }
    if ( !(*(unsigned int (__fastcall **)(struct IFSConfigurationKey *, struct IFSConfigurationKey *))(*(_QWORD *)v58 + 24LL))(
            v58,
            a1) )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
      v43 = FSLoadDeviceConfigurationByKey_Internal(a1, (LPVOID *)&v56);
      v6 = v43;
      if ( v43 < 0 )
      {
        if ( g_wppLevels < 8u )
          goto LABEL_92;
        v44 = 120;
        goto LABEL_91;
      }
      goto LABEL_144;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
    if ( (int)FSLoadDeviceConfigurationByKey_Internal(v58, (LPVOID *)&v56) < 0 )
    {
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v56);
      v43 = FSLoadDeviceConfigurationByKey_Internal(a1, (LPVOID *)&v56);
      v6 = v43;
      if ( v43 < 0 )
      {
        if ( g_wppLevels < 8u )
          goto LABEL_92;
        v44 = 121;
        goto LABEL_91;
      }
      goto LABEL_144;
    }
    v43 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, int *))(*(_QWORD *)v56 + 240LL))(v56, &v62);
    v6 = v43;
    if ( v43 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_92;
      v44 = 122;
      goto LABEL_91;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&pv);
    if ( (int)FSLoadDeviceConfigurationByKey_Internal(a1, &pv) < 0 )
      goto LABEL_144;
    pvar[0] = &v66;
    v60 = 0;
    *(_QWORD *)&v66.Data1 = 0;
    pvar[1] = 0;
    LOBYTE(v68) = 1;
    v6 = FSMergeCameraControlConfigurations(v56, pv, &pvar[1], &v60);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)pvar);
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
      v48 = *(void **)&v66.Data1;
      *(_QWORD *)&v66.Data1 = 0;
      if ( v48 )
        CoTaskMemFree(v48);
      goto LABEL_145;
    }
    v49 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)pv + 240LL))(pv, &v61);
    v6 = v49;
    if ( v49 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_125;
      v50 = 124;
      goto LABEL_124;
    }
    for ( j = 0; j < v61; ++j )
    {
      v64 = 0;
      *(GUID *)pvar = GUID_00000000_0000_0000_0000_000000000000;
      *(_OWORD *)v63 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, PROPVARIANT *, PROPVARIANT *))(*(_QWORD *)pv + 248LL))(
             pv,
             j,
             pvar,
             v63) >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, PROPVARIANT *, PROPVARIANT *))(*(_QWORD *)v56 + 144LL))(
               v56,
               pvar,
               v63);
        if ( v6 < 0 )
        {
          if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
          {
            GuidTrace::GuidTrace((GuidTrace *)v65, (const struct _GUID *)pvar);
            if ( byte_18005E5A5 )
            {
              v54 = GuidTrace::GetString((GuidTrace *)v65);
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                125,
                (unsigned int)&WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
                v6,
                (__int64)v54);
            }
            FSString::~FSString((FSString *)v65, v53);
          }
          v6 = 0;
        }
      }
      PropVariantClear(v63);
    }
    v55 = *(void **)&v66.Data1;
    if ( *(_QWORD *)&v66.Data1 && v60 )
    {
      v49 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, __int64 *, _QWORD))(*(_QWORD *)v56 + 208LL))(
              v56,
              FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
              *(_QWORD *)&v66.Data1);
      v6 = v49;
      if ( v49 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_125:
          v51 = *(void **)&v66.Data1;
          *(_QWORD *)&v66.Data1 = 0;
          if ( v51 )
            CoTaskMemFree(v51);
          goto LABEL_92;
        }
        v50 = 126;
LABEL_124:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v50, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v49);
        goto LABEL_125;
      }
      v55 = *(void **)&v66.Data1;
    }
    *(_QWORD *)&v66.Data1 = 0;
    if ( v55 )
      CoTaskMemFree(v55);
LABEL_144:
    *a2 = v56;
    v56 = 0;
LABEL_145:
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v57);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v58);
    v21 = (__int64 *)&pv;
LABEL_146:
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(v21);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v56);
    if ( v6 >= 0 )
      goto LABEL_62;
    goto LABEL_147;
  }
  if ( g_wppLevels )
  {
    v44 = 116;
LABEL_91:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v43);
  }
LABEL_92:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v57);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v58);
  v25 = (__int64 *)&pv;
LABEL_38:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(v25);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v56);
LABEL_147:
  if ( v6 != -1072875819 )
    goto LABEL_148;
LABEL_62:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v32 = 128;
LABEL_64:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v32,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180038f94  mov     [rsp-8+arg_10], rbx
0x180038f99  mov     [rsp-8+arg_18], rsi
0x180038f9e  push    rbp
0x180038f9f  push    rdi
0x180038fa0  push    r12
0x180038fa2  push    r13
0x180038fa4  push    r14
0x180038fa6  lea     rbp, [rsp-37h]
0x180038fab  sub     rsp, 0E0h
0x180038fb2  mov     rax, cs:__security_cookie
0x180038fb9  xor     rax, rsp
0x180038fbc  mov     [rbp+57h+var_28], rax
0x180038fc0  xor     esi, esi
0x180038fc2  mov     r12, rdx
0x180038fc5  mov     r13d, esi
0x180038fc8  mov     [rbp+57h+var_98], esi
0x180038fcb  mov     r14, rcx
0x180038fce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x180038fd5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x180038fda  mov     [rbp+57h+var_C0], rsi
0x180038fde  mov     [rbp+57h+var_B0], rsi
0x180038fe2  mov     [rbp+57h+var_B8], rsi
0x180038fe6  test    al, al
0x180038fe8  jz      loc_180039632
0x180038fee  test    r14, r14
0x180038ff1  jnz     short loc_180039044
0x180038ff3  mov     eax, 80070057h
0x180038ff8  mov     edi, eax
0x180038ffa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039001  jb      short loc_180039024
0x180039003  lea     edx, [rsi+65h]
0x180039006  mov     rcx, cs:WPP_GLOBAL_Control
0x18003900d  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180039014  xor     r9d, r9d
0x180039017  mov     dword ptr [rsp+100h+var_E0], eax
0x18003901b  mov     rcx, [rcx+10h]
0x18003901f  call    WPP_SF_qD
0x180039024  lea     rcx, [rbp+57h+var_B8]
0x180039028  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003902d  lea     rcx, [rbp+57h+var_B0]
0x180039031  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180039036  lea     rcx, [rbp+57h+var_C0]
0x18003903a  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003903f  jmp     loc_180039BB1
0x180039044  test    r12, r12
0x180039047  jnz     short loc_180039060
0x180039049  mov     eax, 80004003h
0x18003904e  mov     edi, eax
0x180039050  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039057  jb      short loc_180039024
0x180039059  lea     edx, [r12+66h]
0x18003905e  jmp     short loc_180039006
0x180039060  mov     [r12], rsi
0x180039064  cmp     cs:byte_18005E5A5, 8
0x18003906b  jb      short loc_1800390DE
0x18003906d  mov     rax, [r14]
0x180039070  mov     rcx, r14
0x180039073  mov     rax, [rax+48h]
0x180039077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003907c  mov     rcx, [r14]
0x18003907f  mov     rsi, rax
0x180039082  mov     rax, [rcx+38h]
0x180039086  mov     rcx, r14
0x180039089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003908e  mov     rcx, [r14]
0x180039091  mov     rdi, rax
0x180039094  mov     rax, [rcx+40h]
0x180039098  mov     rcx, r14
0x18003909b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390a0  mov     rcx, [r14]
0x1800390a3  mov     rbx, rax
0x1800390a6  mov     rax, [rcx+30h]
0x1800390aa  mov     rcx, r14
0x1800390ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390b9  mov     edx, 67h ; 'g'
0x1800390be  mov     [rsp+100h+var_D0], rsi; __int64
0x1800390c3  mov     r9, rax
0x1800390c6  mov     [rsp+100h+var_D8], rdi; __int64
0x1800390cb  mov     [rsp+100h+var_E0], rbx; __int64
0x1800390d0  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800390d7  call    WPP_SF_SSSS
0x1800390dc  xor     esi, esi
0x1800390de  lea     rcx, [rbp+57h+var_C0]
0x1800390e2  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x1800390e7  movups  xmm0, xmmword ptr cs:?FrameServerConfigurationFMTGUIDV2@@3U_GUID@@B.Data1; _GUID const FrameServerConfigurationFMTGUIDV2 ...
0x1800390ee  lea     r9, [rbp+57h+var_C0]
0x1800390f2  mov     dword ptr [rbp+57h+var_30], 2
0x1800390f9  xor     r8d, r8d; bool
0x1800390fc  lea     rdx, [rbp+57h+pvar]; struct _DEVPROPKEY *
0x180039100  mov     rcx, r14; struct IFSConfigurationKey *
0x180039103  movdqu  xmmword ptr [rbp+57h+pvar], xmm0
0x180039108  call    FSLoadDeviceConfiguration_Base
0x18003910d  mov     edi, eax
0x18003910f  test    eax, eax
0x180039111  jns     short loc_18003916F
0x180039113  lea     rcx, [rbp+57h+var_C0]
0x180039117  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003911c  cmp     cs:byte_18005E5A5, 8
0x180039123  jb      short loc_18003915E
0x180039125  lea     rdx, ?FrameServerConfigurationFMTGUID@@3U_GUID@@B; struct _GUID *
0x18003912c  lea     rcx, [rbp+57h+var_70]; this
0x180039130  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180039135  mov     rcx, rax; this
0x180039138  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18003913d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039144  mov     r9d, edi
0x180039147  mov     [rsp+100h+var_E0], rax
0x18003914c  mov     rcx, [rcx+0D8h]
0x180039153  call    WPP_SF_Dsd
0x180039158  mov     r13d, 1
0x18003915e  test    r13b, 1
0x180039162  jz      short loc_18003916D
0x180039164  lea     rcx, [rbp+57h+var_70]; this
0x180039168  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003916d  mov     edi, esi
0x18003916f  lea     rcx, [rbp+57h+var_B8]
0x180039173  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180039178  mov     rax, [r14]
0x18003917b  mov     rcx, r14
0x18003917e  mov     rax, [rax+38h]
0x180039182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039187  lea     r9, [rbp+57h+var_B8]
0x18003918b  mov     rcx, rax; unsigned __int16 *
0x18003918e  call    FSLoadGlobalConfigurationByName
0x180039193  test    eax, eax
0x180039195  js      loc_180039462
0x18003919b  mov     al, cs:byte_18005E5A5
0x1800391a1  cmp     al, 8
0x1800391a3  jb      short loc_1800391DC
0x1800391a5  mov     rax, [r14]
0x1800391a8  mov     rcx, r14
0x1800391ab  mov     rax, [rax+38h]
0x1800391af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391bb  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800391c2  mov     edx, 69h ; 'i'
0x1800391c7  mov     r9, rax
0x1800391ca  mov     rcx, [rcx+0D8h]
0x1800391d1  call    WPP_SF_S
0x1800391d6  mov     al, cs:byte_18005E5A5
0x1800391dc  cmp     [rbp+57h+var_C0], rsi
0x1800391e0  jz      loc_180039450
0x1800391e6  mov     [rbp+57h+var_9C], esi
0x1800391e9  mov     [rbp+57h+pv], rsi
0x1800391ed  mov     [rbp+57h+var_A0], esi
0x1800391f0  cmp     al, 8
0x1800391f2  jb      short loc_180039213
0x1800391f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391fb  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180039202  mov     edx, 6Ah ; 'j'
0x180039207  mov     rcx, [rcx+0D8h]
0x18003920e  call    WPP_SF_
0x180039213  mov     rdx, [rbp+57h+var_C0]
0x180039217  lea     rax, [rbp+57h+pv]
0x18003921b  mov     rcx, [rbp+57h+var_B8]
0x18003921f  lea     r9, [rbp+57h+var_9C]
0x180039223  lea     r8, [rbp+57h+pvar+8]
0x180039227  mov     [rbp+57h+pvar], rax
0x18003922b  mov     [rbp+57h+pvar+8], rsi
0x18003922f  mov     byte ptr [rbp+57h+var_30], 1
0x180039233  call    FSMergeCameraControlConfigurations
0x180039238  lea     rcx, [rbp+57h+pvar]
0x18003923c  mov     edi, eax
0x18003923e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180039243  mov     eax, edi
0x180039245  shr     eax, 1Fh
0x180039248  test    al, al
0x18003924a  jz      short loc_18003929D
0x18003924c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039253  jb      short loc_180039278
0x180039255  mov     rcx, cs:WPP_GLOBAL_Control
0x18003925c  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180039263  mov     edx, 6Bh ; 'k'
0x180039268  mov     dword ptr [rsp+100h+var_E0], edi
0x18003926c  xor     r9d, r9d
0x18003926f  mov     rcx, [rcx+10h]
0x180039273  call    WPP_SF_qD
0x180039278  mov     rcx, [rbp+57h+pv]; pv
0x18003927c  mov     [rbp+57h+pv], rsi
0x180039280  test    rcx, rcx
0x180039283  jz      short loc_18003928B
0x180039285  call    cs:__imp_CoTaskMemFree
0x18003928b  lea     rcx, [rbp+57h+var_B8]
0x18003928f  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180039294  lea     rcx, [rbp+57h+var_B0]
0x180039298  jmp     loc_180039B8F
0x18003929d  mov     rcx, [rbp+57h+var_C0]
0x1800392a1  lea     rdx, [rbp+57h+var_A0]
0x1800392a5  mov     rax, [rcx]
0x1800392a8  mov     rax, [rax+0F0h]
0x1800392af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392b4  mov     edi, eax
0x1800392b6  test    eax, eax
0x1800392b8  jns     short loc_180039319
0x1800392ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800392c1  jb      short loc_1800392E6
0x1800392c3  mov     edx, 6Ch ; 'l'
0x1800392c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392cf  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800392d6  xor     r9d, r9d
0x1800392d9  mov     dword ptr [rsp+100h+var_E0], eax
0x1800392dd  mov     rcx, [rcx+10h]
0x1800392e1  call    WPP_SF_qD
0x1800392e6  mov     rcx, [rbp+57h+pv]; pv
0x1800392ea  mov     [rbp+57h+pv], rsi
0x1800392ee  test    rcx, rcx
0x1800392f1  jz      short loc_1800392F9
0x1800392f3  call    cs:__imp_CoTaskMemFree
0x1800392f9  lea     rcx, [rbp+57h+var_B8]
0x1800392fd  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180039302  lea     rcx, [rbp+57h+var_B0]
0x180039306  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003930b  lea     rcx, [rbp+57h+var_C0]
0x18003930f  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180039314  jmp     loc_180039BA5
0x180039319  mov     ebx, esi
0x18003931b  cmp     [rbp+57h+var_A0], esi
0x18003931e  jbe     loc_1800393EE
0x180039324  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003932b  mov     rcx, [rbp+57h+var_C0]
0x18003932f  lea     r9, [rbp+57h+pvar]
0x180039333  xor     eax, eax
0x180039335  lea     r8, [rbp+57h+var_50]
0x180039339  mov     [rbp+57h+var_30], rax
0x18003933d  xorps   xmm1, xmm1
0x180039340  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180039345  mov     edx, ebx
0x180039347  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x18003934b  mov     rax, [rcx]
0x18003934e  mov     rax, [rax+0F8h]
0x180039355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003935a  test    eax, eax
0x18003935c  js      short loc_1800393D9
0x18003935e  mov     rcx, [rbp+57h+var_B8]
0x180039362  lea     r8, [rbp+57h+pvar]
0x180039366  lea     rdx, [rbp+57h+var_50]
0x18003936a  mov     rax, [rcx]
0x18003936d  mov     rax, [rax+90h]
0x180039374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039379  mov     edi, eax
0x18003937b  test    eax, eax
0x18003937d  jns     short loc_1800393D9
0x18003937f  cmp     cs:byte_18005E5A5, 10h
0x180039386  jb      short loc_1800393D7
0x180039388  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x18003938c  lea     rcx, [rbp+57h+var_90]; this
0x180039390  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180039395  cmp     cs:byte_18005E5A5, 1
0x18003939c  jb      short loc_1800393CE
0x18003939e  lea     rcx, [rbp+57h+var_90]; this
0x1800393a2  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800393a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393ae  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x1800393b5  mov     edx, 6Dh ; 'm'
0x1800393ba  mov     [rsp+100h+var_E0], rax
0x1800393bf  mov     r9d, edi
0x1800393c2  mov     rcx, [rcx+0D8h]
0x1800393c9  call    WPP_SF_Ds
0x1800393ce  lea     rcx, [rbp+57h+var_90]; this
0x1800393d2  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800393d7  mov     edi, esi
0x1800393d9  lea     rcx, [rbp+57h+pvar]; pvar
0x1800393dd  call    cs:__imp_PropVariantClear
0x1800393e3  inc     ebx
0x1800393e5  cmp     ebx, [rbp+57h+var_A0]
0x1800393e8  jb      loc_180039324
0x1800393ee  mov     rdx, [rbp+57h+pv]
0x1800393f2  test    rdx, rdx
0x1800393f5  jz      short loc_18003943E
0x1800393f7  mov     r9d, [rbp+57h+var_9C]
0x1800393fb  test    r9d, r9d
0x1800393fe  jz      short loc_18003943E
0x180039400  mov     rcx, [rbp+57h+var_B8]
0x180039404  mov     r8, rdx
0x180039407  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x18003940e  mov     rax, [rcx]
0x180039411  mov     rax, [rax+0D0h]
0x180039418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003941d  mov     edi, eax
0x18003941f  test    eax, eax
0x180039421  jns     short loc_18003943A
0x180039423  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003942a  jb      loc_1800392E6
0x180039430  mov     edx, 6Eh ; 'n'
0x180039435  jmp     loc_1800392C8
0x18003943a  mov     rdx, [rbp+57h+pv]
0x18003943e  mov     [rbp+57h+pv], rsi
0x180039442  test    rdx, rdx
0x180039445  jz      short loc_180039450
0x180039447  mov     rcx, rdx; pv
0x18003944a  call    cs:__imp_CoTaskMemFree
0x180039450  mov     rcx, [rbp+57h+var_C0]
0x180039454  mov     rax, [rbp+57h+var_B8]
0x180039458  mov     [rbp+57h+var_C0], rax
0x18003945c  mov     [rbp+57h+var_B8], rcx
0x180039460  jmp     short loc_180039466
0x180039462  mov     rax, [rbp+57h+var_C0]
0x180039466  test    rax, rax
0x180039469  jnz     loc_18003950E
  ... truncated ...
```
