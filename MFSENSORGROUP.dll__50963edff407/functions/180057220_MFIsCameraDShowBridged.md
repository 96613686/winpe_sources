# MFIsCameraDShowBridged

- ea: `0x180057220`
- end: `0x180057ede`
- name: `MFIsCameraDShowBridged`
- size: `3262`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003740`
- `0x180003ac0`
- `0x180005fa0`
- `0x180008f9c`
- `0x18001b39c`
- `0x18001b3d8`
- `0x18001c854`
- `0x18001c96c`
- `0x180024070`
- `0x180028d34`
- `0x180028d5c`
- `0x180028e5c`
- `0x180028fe0`
- `0x18002ae3c`
- `0x18002b3dc`
- `0x18002c008`
- `0x18002d02c`
- `0x180037af0`
- `0x180037c04`
- `0x180044f30`
- `0x180045900`
- `0x180051de4`
- `0x180057220`
- `0x180058df0`
- `0x18006e08c`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18005761a`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18005761a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18005762b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18005762b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800576b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057739`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800577af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057828`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005789e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057914`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800576b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057739`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800577af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057828`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005789e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057914`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800574a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800574a3`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18005739d`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18005739d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057436`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057436`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057abd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057abd`
- `MFPlat!MFStartup` at `0x180057994`
- `MFPlat!MFStartup` at `0x180057994`
- `MFPlat!MFShutdown` at `0x180057db4`
- `MFPlat!MFShutdown` at `0x180057db4`
- `MFPlat!MFCreateAttributes` at `0x180057a1a`
- `MFPlat!MFCreateAttributes` at `0x180057a1a`

## string_xrefs

- `0x180057816`: `CameraDeviceMftClsid`
- `0x180057727`: `CameraPostProcessingPluginCLSID`
- `0x18005788c`: `CameraDeviceMftClsidChain`
- `0x180057902`: `CustomCaptureSourceClsid`

## pseudocode

```c
__int64 __fastcall MFIsCameraDShowBridged(LPCWSTR pszDeviceInterface, __int64 a2)
{
  _QWORD *v2; // r12
  unsigned __int64 v4; // rbx
  char v5; // r13
  __int64 v6; // rdx
  int v7; // eax
  char v8; // di
  __int64 v9; // rdx
  unsigned __int64 v10; // rdi
  CONFIGRET v11; // eax
  signed int v12; // eax
  signed int v13; // r14d
  int v14; // r8d
  const char *v15; // rdi
  const char *v16; // r9
  int v17; // r8d
  const char *v18; // r9
  int v19; // r8d
  const char *v20; // r9
  int v21; // r8d
  const char *v22; // r9
  int v23; // r8d
  const char *v24; // r9
  int v25; // r8d
  HRESULT v26; // eax
  HRESULT v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rsi
  int (__fastcall *v30)(__int64, IMFAttributes *, __int64 *); // rdi
  int v31; // esi
  int v32; // r12d
  __int64 v33; // rdi
  const char *String; // rax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  HKEY v39; // rdi
  __int64 v40; // rax
  __int64 (__fastcall *v41)(HKEY, _QWORD, _QWORD **); // rsi
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, GUID *); // rdi
  FSString *v44; // rax
  const char *v45; // rax
  FSString *v47; // rax
  const char *v48; // rax
  ULONG pulLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  bool v51; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkDeviceInterface; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v53; // [rsp+58h] [rbp-A8h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v57; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v58; // [rsp+80h] [rbp-80h] BYREF
  __int128 v59; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h]
  GUID AliasInterfaceGuid; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR String1[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszAliasDeviceInterface[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v58 = (_QWORD *)a2;
  pulLength[0] = 0;
  v2 = (_QWORD *)a2;
  *(_DWORD *)Data = 0;
  v4 = 0;
  cbData = 4;
  v56 = 0;
  v5 = 0;
  memset_0(String1, 0, 0x20Au);
  v57 = 0;
  v51 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      217,
      &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      pszDeviceInterface);
  if ( !pszDeviceInterface )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        218,
        &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
        0,
        -2147024809);
    goto LABEL_128;
  }
  if ( v2 )
    *v2 = 0;
  if ( (int)FSIsNetworkCamera(pszDeviceInterface, &v51) >= 0 && v51 )
  {
    v4 = 4096;
    v56 = 4096;
    if ( (unsigned __int8)byte_18008D62D < 8u )
      goto LABEL_128;
    v6 = 219;
    goto LABEL_12;
  }
  memset_0(pszAliasDeviceInterface, 0, 0x208u);
  pulLength[0] = 260;
  AliasInterfaceGuid = GUID_919bc09f_b93c_4d4c_80fa_8ed0017d628e;
  if ( !CM_Get_Device_Interface_AliasW(pszDeviceInterface, &AliasInterfaceGuid, pszAliasDeviceInterface, pulLength, 0) )
  {
    v4 = 0x2000;
    v56 = 0x2000;
    if ( (unsigned __int8)byte_18008D62D < 8u )
      goto LABEL_128;
    v6 = 220;
LABEL_12:
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v6,
      &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      pszDeviceInterface);
    goto LABEL_128;
  }
  v7 = FSGetDeviceNodeProperty(
         pszDeviceInterface,
         (DEVPROPKEY *)&DEVPKEY_Device_EnumeratorName,
         (PBYTE)String1,
         0x208u,
         &v57);
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v7);
    goto LABEL_128;
  }
  v8 = 0;
  if ( v57 > 2 && CompareStringOrdinal(String1, -1, L"USB", -1, 1) == 2 )
  {
    v8 = 1;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        222,
        &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
        pszDeviceInterface);
  }
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform",
          L"EnableDshowRedirection",
          0x10010u,
          0,
          Data,
          &cbData) )
  {
    if ( *(_DWORD *)Data )
    {
      v4 = 1;
      v56 = 1;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v9 = 224;
        goto LABEL_29;
      }
    }
    else
    {
      v4 = 2;
      v56 = 2;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v9 = 223;
LABEL_29:
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v9,
          &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
          pszDeviceInterface);
      }
    }
  }
  if ( v8 )
  {
    pulLength[0] = 0;
    *(_DWORD *)Data = 0;
    if ( (int)FSGetDeviceNodeRegistryEntry(pszDeviceInterface, L"EnableDshowRedirection", Data, 4u, pulLength) >= 0 )
    {
      if ( (Data[0] & 1) != 0 )
      {
        v4 |= 4u;
        v56 = v4;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            225,
            &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
            pszDeviceInterface);
        v10 = v4;
      }
      else
      {
        v4 |= 0x10u;
        v56 = v4;
        v10 = v4;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            226,
            &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
            pszDeviceInterface);
      }
      if ( (Data[0] & 2) != 0 )
      {
        v4 = v10 | 8;
        v56 = v10 | 8;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            227,
            &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
            pszDeviceInterface);
      }
    }
  }
  phkDeviceInterface = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkDeviceInterface,
    0);
  v11 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
  if ( !v11 )
    goto LABEL_48;
  v12 = CM_MapCrToWin32Err(v11, 0xDu);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 >= 0 )
  {
LABEL_48:
    cbData = 4;
    v15 = "disable";
    if ( !RegQueryValueExW(phkDeviceInterface, L"FSMEnableMsEffects", 0, 0, Data, &cbData) )
    {
      v4 = -(__int64)(*(_DWORD *)Data != 0) & 0x200 | v4 & 0xFFFFFFFFFFFFFDFFuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v16 = "disable";
        if ( (v4 & 0x200) != 0 )
          v16 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 229, v14, (_DWORD)v16, (__int64)pszDeviceInterface);
      }
    }
    if ( !RegQueryValueExW(phkDeviceInterface, L"CameraPostProcessingPluginCLSID", 0, 0, 0, &cbData) )
    {
      v4 = (cbData > 2 ? 0x20 : 0) | v4 & 0xFFFFFFFFFFFFFFDFuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v18 = "disable";
        if ( (v4 & 0x20) != 0 )
          v18 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 230, v17, (_DWORD)v18, (__int64)pszDeviceInterface);
      }
    }
    if ( !RegQueryValueExW(phkDeviceInterface, L"EnablePlatformDmft", 0, 0, 0, &cbData) )
    {
      v4 = (cbData > 2 ? 0x80 : 0) | v4 & 0xFFFFFFFFFFFFFF7FuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v20 = "disable";
        if ( (v4 & 0x80u) != 0LL )
          v20 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 231, v19, (_DWORD)v20, (__int64)pszDeviceInterface);
      }
    }
    if ( !RegQueryValueExW(phkDeviceInterface, L"CameraDeviceMftClsid", 0, 0, 0, &cbData) )
    {
      v4 = (cbData > 2 ? 0x40 : 0) | v4 & 0xFFFFFFFFFFFFFFBFuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v22 = "disable";
        if ( (v4 & 0x40) != 0 )
          v22 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 232, v21, (_DWORD)v22, (__int64)pszDeviceInterface);
      }
    }
    if ( !RegQueryValueExW(phkDeviceInterface, L"CameraDeviceMftClsidChain", 0, 0, 0, &cbData) )
    {
      v4 = (cbData > 2 ? 0x40 : 0) | v4 & 0xFFFFFFFFFFFFFFBFuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v24 = "disable";
        if ( (v4 & 0x40) != 0 )
          v24 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 233, v23, (_DWORD)v24, (__int64)pszDeviceInterface);
      }
    }
    if ( !RegQueryValueExW(phkDeviceInterface, L"CustomCaptureSourceClsid", 0, 0, 0, &cbData) )
    {
      v4 = -(__int64)(cbData > 2) & 0x400 | v4 & 0xFFFFFFFFFFFFFBFFuLL;
      v56 = v4;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        if ( (v4 & 0x400) != 0 )
          v15 = "enable";
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 27), 234, v25, (_DWORD)v15, (__int64)pszDeviceInterface);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
    *(_QWORD *)pulLength = 0;
    v53 = 0;
    ppMFAttributes = 0;
    phkDeviceInterface = 0;
    v26 = MFStartup(0x20070u, 0);
    if ( v26 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v26);
      if ( *(_QWORD *)pulLength )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pulLength + 40LL))(*(_QWORD *)pulLength);
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v53);
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(pulLength);
      wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
LABEL_127:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&phkDeviceInterface);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v53);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)pulLength);
      goto LABEL_128;
    }
    wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v27 = MFCreateAttributes(&ppMFAttributes, 1u);
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_124:
        if ( *(_QWORD *)pulLength )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pulLength + 40LL))(*(_QWORD *)pulLength);
        wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v53);
        wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(pulLength);
        wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
        MFShutdown();
        goto LABEL_127;
      }
      v28 = 236;
LABEL_87:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v27);
      goto LABEL_124;
    }
    v27 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, LPCWSTR))ppMFAttributes->lpVtbl->SetString)(
            ppMFAttributes,
            &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
            pszDeviceInterface);
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_124;
      v28 = 237;
      goto LABEL_87;
    }
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(pulLength);
    if ( CoCreateInstance(
           &CLSID_CameraConfigurationManager,
           0,
           1u,
           &GUID_a624f617_4704_4206_8a6d_ebda4a093985,
           (LPVOID *)pulLength) >= 0 )
    {
      v29 = *(_QWORD *)pulLength;
      v30 = *(int (__fastcall **)(__int64, IMFAttributes *, __int64 *))(**(_QWORD **)pulLength + 24LL);
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v53);
      if ( v30(v29, ppMFAttributes, &v53) >= 0 )
      {
        v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 264LL))(v53);
        v32 = MFGetAttributeUINT32(v53, FRAMESERVERCLIENT_SENSOR_ORIENTATION_ADJUSTMENT, 0);
        v33 = 0;
        if ( !SGUtils_IsCurrentProcessWinBioSrvc() && !SGUtils_IsCurrentProcessBioEnrollment() )
          v33 = MFGetAttributeUINT64(v53, MF_FRAMESERVER_MANAGED_CAMERA_MODE);
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v60 = 0;
          *(_QWORD *)&AliasInterfaceGuid.Data1 = v33;
          v59 = 0;
          ManagedModeTrace::Set(
            (ManagedModeTrace *)&v59,
            (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&AliasInterfaceGuid);
          String = FSString::GetString((FSString *)&v59);
          WPP_SF_ddsS(*((_QWORD *)WPP_GLOBAL_Control + 27), v32, (__int64)String, (__int64)pszDeviceInterface);
          v5 = 1;
        }
        if ( (v5 & 1) != 0 )
        {
          v5 &= ~1u;
          FSString::~FSString((FSString *)&v59);
        }
        if ( v31 || v32 || v33 )
          v35 = 256;
        else
          v35 = 0;
        v2 = v58;
        v4 = v35 | v4 & 0xFFFFFFFFFFFFFEFFuLL;
        v56 = v4;
      }
    }
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&phkDeviceInterface);
    if ( (int)MFCreateSensorGroup(pszDeviceInterface, &phkDeviceInterface) < 0 )
      goto LABEL_124;
    v57 = 0;
    v58 = 0;
    *(_QWORD *)&AliasInterfaceGuid.Data1 = 0;
    v36 = (*(__int64 (__fastcall **)(HKEY, unsigned int *))(*(_QWORD *)phkDeviceInterface + 48LL))(
            phkDeviceInterface,
            &v57);
    if ( v36 >= 0 )
    {
      if ( v57 != 1 )
        goto LABEL_123;
      v38 = (__int64)v58;
      v39 = phkDeviceInterface;
      v40 = *(_QWORD *)phkDeviceInterface;
      v58 = 0;
      v41 = *(__int64 (__fastcall **)(HKEY, _QWORD, _QWORD **))(v40 + 56);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v36 = v41(v39, 0, &v58);
      if ( v36 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_123;
        v37 = 240;
        goto LABEL_110;
      }
      v42 = (__int64)v58;
      v43 = *(__int64 (__fastcall **)(__int64, GUID *))(*v58 + 56LL);
      wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&AliasInterfaceGuid);
      v36 = v43(v42, &AliasInterfaceGuid);
      if ( v36 >= 0 )
      {
        v4 = v4 & 0xFFFFFFFFFFFFF7FFuLL
           | -(__int64)((unsigned int)MFGetAttributeUINT32(
                                        *(_QWORD *)&AliasInterfaceGuid.Data1,
                                        MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE,
                                        0) != 0)
           & 0x800;
        v56 = v4;
        if ( (v4 & 0x800) != 0 && (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            242,
            &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
            pszDeviceInterface);
        goto LABEL_123;
      }
      if ( g_wppLevels )
      {
        v37 = 241;
        goto LABEL_110;
      }
    }
    else if ( g_wppLevels )
    {
      v37 = 239;
LABEL_110:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v36);
    }
LABEL_123:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&AliasInterfaceGuid);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v58);
    goto LABEL_124;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
LABEL_128:
  if ( v2 )
    *v2 = v4;
  if ( !v4 || (v4 & 0x10) != 0 || (v4 & 2) != 0 )
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v5 |= 2u;
      v47 = MFDShowBridgeFlagTrace::MFDShowBridgeFlagTrace(
              (MFDShowBridgeFlagTrace *)&v59,
              (const union MFDShowBridgeFlags *)&v56);
      v48 = FSString::GetString(v47);
      WPP_SF_DsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v48, (__int64)pszDeviceInterface);
    }
    if ( (v5 & 2) != 0 )
      FSString::~FSString((FSString *)&v59);
    return 0;
  }
  else
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v5 |= 4u;
      v44 = MFDShowBridgeFlagTrace::MFDShowBridgeFlagTrace(
              (MFDShowBridgeFlagTrace *)&v59,
              (const union MFDShowBridgeFlags *)&v56);
      v45 = FSString::GetString(v44);
      WPP_SF_DsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v45, (__int64)pszDeviceInterface);
    }
    if ( (v5 & 4) != 0 )
      FSString::~FSString((FSString *)&v59);
    return 1;
  }
}

```

## disassembly

```asm
0x180057220  mov     [rsp-8+arg_10], rbx
0x180057225  push    rbp
0x180057226  push    rsi
0x180057227  push    rdi
0x180057228  push    r12
0x18005722a  push    r13
0x18005722c  push    r14
0x18005722e  push    r15
0x180057230  lea     rbp, [rsp-3E0h]
0x180057238  sub     rsp, 4E0h
0x18005723f  mov     rax, cs:__security_cookie
0x180057246  xor     rax, rsp
0x180057249  mov     [rbp+410h+var_40], rax
0x180057250  xor     esi, esi
0x180057252  mov     [rbp+410h+var_490], rdx
0x180057256  mov     [rsp+510h+pulLength], esi
0x18005725a  mov     r12, rdx
0x18005725d  mov     r15, rcx
0x180057260  mov     dword ptr [rsp+510h+Data], esi
0x180057264  mov     ebx, esi
0x180057266  mov     [rsp+510h+cbData], 4
0x18005726e  xor     edx, edx; Val
0x180057270  mov     [rsp+510h+var_4A0], rbx
0x180057275  mov     r8d, 20Ah; Size
0x18005727b  lea     rcx, [rbp+410h+String1]; void *
0x18005727f  mov     r13d, esi
0x180057282  call    memset_0
0x180057287  mov     [rsp+510h+var_498], esi
0x18005728b  mov     [rsp+510h+var_4C4], sil
0x180057290  cmp     cs:byte_18008D62D, 8
0x180057297  lea     rdi, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18005729e  jb      short loc_1800572BE
0x1800572a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572a7  mov     edx, 0D9h
0x1800572ac  mov     r9, r15
0x1800572af  mov     r8, rdi
0x1800572b2  mov     rcx, [rcx+0D8h]
0x1800572b9  call    WPP_SF_S
0x1800572be  mov     eax, 2
0x1800572c3  test    r15, r15
0x1800572c6  jnz     short loc_180057300
0x1800572c8  mov     r14d, 80070057h
0x1800572ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800572d5  jb      loc_180057DE7
0x1800572db  mov     edx, 0DAh
0x1800572e0  mov     [rsp+510h+ulFlags], r14d
0x1800572e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572ec  xor     r9d, r9d
0x1800572ef  mov     r8, rdi
0x1800572f2  mov     rcx, [rcx+10h]
0x1800572f6  call    WPP_SF_qD
0x1800572fb  jmp     loc_180057DE2
0x180057300  mov     r14d, esi
0x180057303  test    r12, r12
0x180057306  jz      short loc_18005730C
0x180057308  mov     [r12], rsi
0x18005730c  lea     rdx, [rsp+510h+var_4C4]; bool *
0x180057311  mov     rcx, r15; pszDeviceInterface
0x180057314  call    ?FSIsNetworkCamera@@YAJPEBGPEA_N@Z; FSIsNetworkCamera(ushort const *,bool *)
0x180057319  test    eax, eax
0x18005731b  js      short loc_18005735E
0x18005731d  cmp     [rsp+510h+var_4C4], sil
0x180057322  jz      short loc_18005735E
0x180057324  mov     ebx, 1000h
0x180057329  mov     [rsp+510h+var_4A0], rbx
0x18005732e  cmp     cs:byte_18008D62D, 8
0x180057335  jb      loc_180057DE2
0x18005733b  mov     edx, 0DBh
0x180057340  mov     rcx, cs:WPP_GLOBAL_Control
0x180057347  mov     r9, r15
0x18005734a  mov     r8, rdi
0x18005734d  mov     rcx, [rcx+0D8h]
0x180057354  call    WPP_SF_S
0x180057359  jmp     loc_180057DE2
0x18005735e  xor     edx, edx; Val
0x180057360  lea     rcx, [rbp+410h+pszAliasDeviceInterface]; void *
0x180057367  mov     r8d, 208h; Size
0x18005736d  call    memset_0
0x180057372  movups  xmm0, xmmword ptr cs:_GUID_919bc09f_b93c_4d4c_80fa_8ed0017d628e.Data1
0x180057379  lea     r9, [rsp+510h+pulLength]; pulLength
0x18005737e  mov     [rsp+510h+pulLength], 104h
0x180057386  lea     r8, [rbp+410h+pszAliasDeviceInterface]; pszAliasDeviceInterface
0x18005738d  mov     [rsp+510h+ulFlags], esi; ulFlags
0x180057391  lea     rdx, [rbp+410h+AliasInterfaceGuid]; AliasInterfaceGuid
0x180057395  mov     rcx, r15; pszDeviceInterface
0x180057398  movdqu  xmmword ptr [rbp+410h+AliasInterfaceGuid.Data1], xmm0
0x18005739d  call    cs:__imp_CM_Get_Device_Interface_AliasW
0x1800573a3  test    eax, eax
0x1800573a5  jnz     short loc_1800573C8
0x1800573a7  mov     ebx, 2000h
0x1800573ac  mov     [rsp+510h+var_4A0], rbx
0x1800573b1  cmp     cs:byte_18008D62D, 8
0x1800573b8  jb      loc_180057DE2
0x1800573be  mov     edx, 0DCh
0x1800573c3  jmp     loc_180057340
0x1800573c8  lea     rax, [rsp+510h+var_498]
0x1800573cd  mov     r9d, 208h; unsigned int
0x1800573d3  lea     r8, [rbp+410h+String1]; PropertyBuffer
0x1800573d7  mov     qword ptr [rsp+510h+ulFlags], rax; unsigned int *
0x1800573dc  lea     rdx, DEVPKEY_Device_EnumeratorName; PropertyKey
0x1800573e3  mov     rcx, r15; pszDeviceInterface
0x1800573e6  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x1800573eb  mov     r14d, eax
0x1800573ee  test    eax, eax
0x1800573f0  jns     short loc_18005740D
0x1800573f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800573f9  jb      loc_180057DE2
0x1800573ff  mov     edx, 0DDh
0x180057404  mov     [rsp+510h+ulFlags], eax
0x180057408  jmp     loc_1800572E5
0x18005740d  mov     r14d, 2
0x180057413  mov     dil, sil
0x180057416  cmp     [rsp+510h+var_498], r14d
0x18005741b  jbe     short loc_18005746F
0x18005741d  or      edx, 0FFFFFFFFh; cchCount1
0x180057420  mov     [rsp+510h+ulFlags], 1; bIgnoreCase
0x180057428  mov     r9d, edx; cchCount2
0x18005742b  lea     r8, String2; "USB"
0x180057432  lea     rcx, [rbp+410h+String1]; lpString1
0x180057436  call    cs:__imp_CompareStringOrdinal
0x18005743c  cmp     eax, r14d
0x18005743f  jnz     short loc_18005746F
0x180057441  mov     dil, 1
0x180057444  cmp     cs:byte_18008D62D, 8
0x18005744b  jb      short loc_18005746F
0x18005744d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057454  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18005745b  mov     edx, 0DEh
0x180057460  mov     r9, r15
0x180057463  mov     rcx, [rcx+0D8h]
0x18005746a  call    WPP_SF_S
0x18005746f  lea     rax, [rsp+510h+cbData]
0x180057474  mov     r9d, 10010h; dwFlags
0x18005747a  mov     [rsp+510h+pcbData], rax; pcbData
0x18005747f  lea     r8, aEnabledshowred; "EnableDshowRedirection"
0x180057486  lea     rax, [rsp+510h+Data]
0x18005748b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180057492  mov     [rsp+510h+pvData], rax; pvData
0x180057497  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows Media Foun"...
0x18005749e  mov     qword ptr [rsp+510h+ulFlags], rsi; pdwType
0x1800574a3  call    cs:__imp_RegGetValueW
0x1800574a9  test    eax, eax
0x1800574ab  jnz     short loc_180057500
0x1800574ad  cmp     dword ptr [rsp+510h+Data], esi
0x1800574b1  jnz     short loc_1800574CB
0x1800574b3  mov     rbx, r14
0x1800574b6  mov     [rsp+510h+var_4A0], rbx
0x1800574bb  cmp     cs:byte_18008D62D, 8
0x1800574c2  jb      short loc_180057500
0x1800574c4  mov     edx, 0DFh
0x1800574c9  jmp     short loc_1800574E3
0x1800574cb  mov     ebx, 1
0x1800574d0  mov     [rsp+510h+var_4A0], rbx
0x1800574d5  cmp     cs:byte_18008D62D, 8
0x1800574dc  jb      short loc_180057500
0x1800574de  mov     edx, 0E0h
0x1800574e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574ea  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800574f1  mov     r9, r15
0x1800574f4  mov     rcx, [rcx+0D8h]
0x1800574fb  call    WPP_SF_S
0x180057500  test    dil, dil
0x180057503  jz      loc_1800575F2
0x180057509  lea     rax, [rsp+510h+pulLength]
0x18005750e  mov     [rsp+510h+pulLength], esi
0x180057512  mov     r9d, 4; unsigned int
0x180057518  mov     qword ptr [rsp+510h+ulFlags], rax; unsigned int *
0x18005751d  lea     r8, [rsp+510h+Data]; lpData
0x180057522  mov     dword ptr [rsp+510h+Data], esi
0x180057526  lea     rdx, aEnabledshowred; "EnableDshowRedirection"
0x18005752d  mov     rcx, r15; pszDeviceInterface
0x180057530  call    ?FSGetDeviceNodeRegistryEntry@@YAJPEBG0PEAEKPEAK@Z; FSGetDeviceNodeRegistryEntry(ushort const *,ushort const *,uchar *,ulong,ulong *)
0x180057535  test    eax, eax
0x180057537  js      loc_1800575F2
0x18005753d  test    [rsp+510h+Data], 1
0x180057542  jz      short loc_18005757D
0x180057544  or      rbx, 4
0x180057548  mov     [rsp+510h+var_4A0], rbx
0x18005754d  cmp     cs:byte_18008D62D, 8
0x180057554  jb      short loc_180057578
0x180057556  mov     rcx, cs:WPP_GLOBAL_Control
0x18005755d  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180057564  mov     edx, 0E1h
0x180057569  mov     r9, r15
0x18005756c  mov     rcx, [rcx+0D8h]
0x180057573  call    WPP_SF_S
0x180057578  mov     rdi, rbx
0x18005757b  jmp     short loc_1800575B4
0x18005757d  or      rbx, 10h
0x180057581  mov     [rsp+510h+var_4A0], rbx
0x180057586  mov     rdi, rbx
0x180057589  cmp     cs:byte_18008D62D, 8
0x180057590  jb      short loc_1800575B4
0x180057592  mov     rcx, cs:WPP_GLOBAL_Control
0x180057599  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800575a0  mov     edx, 0E2h
0x1800575a5  mov     r9, r15
0x1800575a8  mov     rcx, [rcx+0D8h]
0x1800575af  call    WPP_SF_S
0x1800575b4  test    [rsp+510h+Data], r14b
0x1800575b9  jz      short loc_1800575F2
0x1800575bb  mov     rbx, rdi
0x1800575be  or      rbx, 8
0x1800575c2  mov     [rsp+510h+var_4A0], rbx
0x1800575c7  cmp     cs:byte_18008D62D, 8
0x1800575ce  jb      short loc_1800575F2
0x1800575d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800575d7  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800575de  mov     edx, 0E3h
0x1800575e3  mov     r9, r15
0x1800575e6  mov     rcx, [rcx+0D8h]
0x1800575ed  call    WPP_SF_S
0x1800575f2  xor     edx, edx
0x1800575f4  mov     [rsp+510h+phkDeviceInterface], rsi
0x1800575f9  lea     rcx, [rsp+510h+phkDeviceInterface]
0x1800575fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180057603  lea     r9, [rsp+510h+phkDeviceInterface]; phkDeviceInterface
0x180057608  mov     [rsp+510h+ulFlags], esi; ulFlags
0x18005760c  mov     edx, 20019h; samDesired
0x180057611  mov     r8d, 1; Disposition
0x180057617  mov     rcx, r15; pszDeviceInterface
0x18005761a  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x180057620  test    eax, eax
0x180057622  jz      short loc_180057684
0x180057624  mov     edx, 0Dh; DefaultErr
0x180057629  mov     ecx, eax; CmReturnCode
0x18005762b  call    cs:__imp_CM_MapCrToWin32Err
0x180057631  mov     r14d, eax
0x180057634  test    eax, eax
0x180057636  jle     short loc_180057643
0x180057638  movzx   r14d, ax
0x18005763c  or      r14d, 80070000h
0x180057643  test    r14d, r14d
0x180057646  jns     short loc_180057684
0x180057648  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005764f  jb      short loc_180057675
0x180057651  mov     rcx, cs:WPP_GLOBAL_Control
0x180057658  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18005765f  mov     edx, 0E4h
0x180057664  mov     [rsp+510h+ulFlags], r14d
0x180057669  xor     r9d, r9d
0x18005766c  mov     rcx, [rcx+10h]
0x180057670  call    WPP_SF_qD
0x180057675  lea     rcx, [rsp+510h+phkDeviceInterface]
0x18005767a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005767f  jmp     loc_180057DE2
0x180057684  mov     rcx, [rsp+510h+phkDeviceInterface]; hKey
0x180057689  lea     rax, [rsp+510h+cbData]
0x18005768e  mov     [rsp+510h+pvData], rax; lpcbData
0x180057693  lea     rdx, aFsmenablemseff; "FSMEnableMsEffects"
0x18005769a  lea     rax, [rsp+510h+Data]
0x18005769f  mov     [rsp+510h+cbData], 4
0x1800576a7  xor     r9d, r9d; lpType
0x1800576aa  mov     qword ptr [rsp+510h+ulFlags], rax; lpData
0x1800576af  xor     r8d, r8d; lpReserved
0x1800576b2  call    cs:__imp_RegQueryValueExW
0x1800576b8  lea     r14, aEnable; "enable"
0x1800576bf  lea     rdi, aDisable; "disable"
0x1800576c6  test    eax, eax
0x1800576c8  jnz     short loc_180057718
0x1800576ca  mov     eax, dword ptr [rsp+510h+Data]
0x1800576ce  neg     eax
0x1800576d0  mov     eax, 200h
0x1800576d5  sbb     rcx, rcx
0x1800576d8  btr     rbx, 9
0x1800576dd  and     rcx, rax
0x1800576e0  or      rbx, rcx
0x1800576e3  mov     [rsp+510h+var_4A0], rbx
0x1800576e8  cmp     cs:byte_18008D62D, 8
0x1800576ef  jb      short loc_180057718
0x1800576f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800576f8  test    rax, rbx
0x1800576fb  mov     r9, rdi
0x1800576fe  mov     qword ptr [rsp+510h+ulFlags], r15
0x180057703  cmovnz  r9, r14
0x180057707  mov     edx, 0E5h
0x18005770c  mov     rcx, [rcx+0D8h]
0x180057713  call    WPP_SF_sS
0x180057718  mov     rcx, [rsp+510h+phkDeviceInterface]; hKey
0x18005771d  lea     rax, [rsp+510h+cbData]
0x180057722  mov     [rsp+510h+pvData], rax; lpcbData
0x180057727  lea     rdx, aCamerapostproc; "CameraPostProcessingPluginCLSID"
0x18005772e  xor     r9d, r9d; lpType
0x180057731  mov     qword ptr [rsp+510h+ulFlags], rsi; lpData
0x180057736  xor     r8d, r8d; lpReserved
0x180057739  call    cs:__imp_RegQueryValueExW
0x18005773f  test    eax, eax
0x180057741  jnz     short loc_18005778E
0x180057743  mov     eax, 2
0x180057748  cmp     eax, [rsp+510h+cbData]
0x18005774c  sbb     rax, rax
0x18005774f  and     rbx, 0FFFFFFFFFFFFFFDFh
0x180057753  and     eax, 20h
0x180057756  or      rbx, rax
0x180057759  mov     [rsp+510h+var_4A0], rbx
0x18005775e  cmp     cs:byte_18008D62D, 8
0x180057765  jb      short loc_18005778E
0x180057767  mov     rcx, cs:WPP_GLOBAL_Control
0x18005776e  test    bl, 20h
0x180057771  mov     r9, rdi
  ... truncated ...
```
