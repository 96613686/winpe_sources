# UpdateObject

- ea: `0x1800418b4`
- end: `0x18004243e`
- name: `UpdateObject`
- size: `2954`
- prototype: ``
- caller_count: `2`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041870`
- `0x1800754a0`

## callees

- `0x180005580`
- `0x180005660`
- `0x180005c94`
- `0x180006eb0`
- `0x18000a430`
- `0x18000e8ec`
- `0x18000e970`
- `0x18000fd70`
- `0x180010200`
- `0x180012108`
- `0x180013fe4`
- `0x180015f50`
- `0x1800163d0`
- `0x180016a20`
- `0x180017320`
- `0x1800177ec`
- `0x180025c18`
- `0x180026174`
- `0x180027a78`
- `0x180027ac0`
- `0x180027b38`
- `0x1800285fc`
- `0x180028db4`
- `0x180029d20`
- `0x18002b624`
- `0x180030f10`
- `0x1800418b4`
- `0x180042444`
- `0x1800425b4`
- `0x180043428`
- `0x18004490c`
- `0x18004546c`
- `0x180054604`
- `0x180059848`
- `0x18005b424`
- `0x18005b46c`
- `0x18005b4f0`
- `0x18005bb18`
- `0x180062b6c`
- `0x180064704`
- `0x180074348`
- `0x18007f894`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042415`

## string_xrefs

- `0x180041ce0`: `Services\`
- `0x180041afd`: `ComponentId`
- `0x180041ed1`: `ComponentId`
- `0x180041f0b`: `InfPath`
- `0x18004203c`: `TemporaryInstallStage`
- `0x1800422c4`: `ComponentDll`
- `0x1800422a7`: `ClsId`
- `0x18004228a`: `Service`
- `0x1800422fe`: `CoServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall UpdateObject(void **a1, __int64 a2, __int64 a3)
{
  int v6; // esi
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdx
  bool v11; // zf
  char v12; // al
  int v13; // esi
  char v14; // bl
  HKEY CurrentControlSetRegistryHandle; // rbx
  bool v16; // r8
  void **v17; // rdx
  __int64 v18; // rdx
  const WCHAR *v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  void *KtmHandle; // rbx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  const WCHAR *v28; // r8
  const WCHAR *v29; // r8
  const wchar_t *v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  void **v35; // r9
  int v36; // [rsp+20h] [rbp-208h]
  HKEY hKey; // [rsp+48h] [rbp-1E0h] BYREF
  HKEY v38; // [rsp+50h] [rbp-1D8h] BYREF
  HKEY v39; // [rsp+58h] [rbp-1D0h] BYREF
  _QWORD v40[3]; // [rsp+60h] [rbp-1C8h] BYREF
  HKEY v41; // [rsp+78h] [rbp-1B0h] BYREF
  HKEY v42; // [rsp+80h] [rbp-1A8h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-1A0h] BYREF
  __int64 v44; // [rsp+98h] [rbp-190h]
  unsigned __int64 v45; // [rsp+A0h] [rbp-188h]
  GUID v46; // [rsp+A8h] [rbp-180h] BYREF
  int v47; // [rsp+B8h] [rbp-170h]
  __int128 v48; // [rsp+BCh] [rbp-16Ch] BYREF
  void *v49[2]; // [rsp+D8h] [rbp-150h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-140h]
  unsigned __int64 v51; // [rsp+F0h] [rbp-138h]
  _QWORD v52[3]; // [rsp+F8h] [rbp-130h] BYREF
  unsigned __int64 v53; // [rsp+110h] [rbp-118h]
  wchar_t *v54[3]; // [rsp+118h] [rbp-110h] BYREF
  unsigned __int64 v55; // [rsp+130h] [rbp-F8h]
  void **v56; // [rsp+138h] [rbp-F0h] BYREF
  __int64 v57; // [rsp+140h] [rbp-E8h] BYREF
  int v58; // [rsp+148h] [rbp-E0h]
  __int128 v59; // [rsp+14Ch] [rbp-DCh] BYREF
  _QWORD v60[3]; // [rsp+168h] [rbp-C0h] BYREF
  unsigned __int64 v61; // [rsp+180h] [rbp-A8h]
  __int128 v62; // [rsp+188h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+198h] [rbp-90h]
  _BYTE v64[24]; // [rsp+1A0h] [rbp-88h] BYREF
  __int128 v65; // [rsp+1B8h] [rbp-70h] BYREF
  __int64 v66; // [rsp+1C8h] [rbp-60h]
  _BYTE v67[24]; // [rsp+1D0h] [rbp-58h] BYREF

  v6 = 0;
  LODWORD(v38) = 0;
  GetDriverNetworkKey(&v39, a1, a2);
  if ( v39 )
  {
    v40[0] = &v39;
    v40[1] = a2;
    v40[2] = a3;
    if ( *(_DWORD *)(a2 + 16) == 2 )
    {
      StringFromGuid(v54, a2 + 20);
      std::wstring::wstring(v49, L"\\Device\\");
      std::wstring::append(v49, v54, 0, -1);
      v62 = 0;
      v63 = 0;
      std::vector<std::wstring>::_Reserve(&v62);
      v7 = *((_QWORD *)&v62 + 1);
      std::wstring::wstring(*((_QWORD *)&v62 + 1));
      *((_QWORD *)&v62 + 1) = v7 + 32;
      v65 = 0;
      v66 = 0;
      std::vector<std::wstring>::_Reserve(&v65);
      v8 = *((_QWORD *)&v65 + 1);
      std::wstring::wstring(*((_QWORD *)&v65 + 1));
      *((_QWORD *)&v65 + 1) = v8 + 32;
      RegistryKey::CreateSubKey(&v39, (HKEY)&v41, L"Connection", 2u, 0, 0);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v41,
        L"Name",
        (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Interface_IfAlias);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v41,
        L"PnPInstanceId",
        (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Interface_PnpInstance);
      v56 = *(void ***)a2;
      v57 = 0;
      v58 = *(_DWORD *)(a2 + 16);
      v59 = *(_OWORD *)(a2 + 20);
      LOBYTE(v36) = 1;
      OpenDeviceSoftwareKey(&hKey, a1, &v56, 7, v36);
      if ( !NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber((NetSetup2::NetworkInterface *)&v56) && hKey )
      {
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&hKey,
          L"DeviceInstanceID",
          (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Interface_PnpInstance);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&hKey,
          L"ComponentId",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Interface_PnpMatchingHardwareId);
        TimidUpdateMultiSZValueUnderSubKey(&hKey, v9, L"RootDevice", &v65);
        TimidUpdateMultiSZValueUnderSubKey(&hKey, v10, L"Export", &v62);
        if ( !a3
          || (v6 = 1,
              v11 = *(_BYTE *)(NetSetup2::PropertyArray::TryGetProperty(a3, v40, &NETSETUPPKEY_Interface_PnpInstance) + 8) == 0,
              v12 = 0,
              !v11) )
        {
          v12 = 1;
        }
        if ( (v6 & 1) != 0 )
          v6 &= ~1u;
        if ( v12 )
        {
          MarkNicAsNeedingLinkageUpdates(a1, a2 + 20);
          NetSetup2::ActiveObject::GetProperty(&v56, &v46, &NETSETUPPKEY_Interface_PnpInstance, 0);
          v13 = v6 | 0xC;
          if ( (_DWORD)v48 )
          {
            NetSetup2::Property::GetString(&v46, Block);
          }
          else
          {
            v45 = 7;
            v44 = 0;
            LOWORD(Block[0]) = 0;
          }
          std::vector<_NETSETUPPROPKEY>::_Tidy((char *)&v48 + 4);
          if ( !NetSetup2::NetworkInterface::get_IsPhysical((NetSetup2::NetworkInterface *)&v56)
            || !v44
            || (*(_QWORD *)&v46.Data1 = a1,
                *(_QWORD *)v46.Data4 = 0,
                v47 = 9,
                v48 = 0,
                v13 |= 2u,
                LODWORD(v38) = v13,
                v14 = 1,
                !NetSetup2::TransactionObject::get_IsOnline((NetSetup2::TransactionObject *)&v46)) )
          {
            v14 = 0;
          }
          if ( (v13 & 2) != 0 )
            std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v46.Data4);
          if ( v14 )
          {
            *(_QWORD *)&v46.Data1 = a1;
            *(_QWORD *)v46.Data4 = 0;
            v47 = 9;
            v48 = 0;
            CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v46);
            std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v46.Data4);
            RegistryKey::DuplicateFrom(&v42, CurrentControlSetRegistryHandle);
            v17 = Block;
            if ( v45 >= 8 )
              v17 = (void **)Block[0];
            try
            {
              NetSetupDevice::NetSetupDevice((NetSetupDevice *)v40, (const wchar_t *)v17, v16);
              std::wstring::wstring(&v46, L"Services\\");
              v53 = 7;
              v52[2] = 0;
              LOWORD(v52[0]) = 0;
              if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v40, &DEVPKEY_Device_Service, v52) )
              {
                std::operator+<wchar_t>(v60, &v46, v52);
                v19 = (const WCHAR *)v60;
                if ( v61 >= 8 )
                  v19 = (const WCHAR *)v60[0];
                RegistryKey::OpenSubKey(&v42, (HKEY)&v38, v19, 2u, 0);
                RegistryKey::SetValue(&v38, L"BootFlags", 1, 0);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
                LOBYTE(v20) = 1;
                std::wstring::_Tidy(v60, v20, 0);
              }
              LOBYTE(v18) = 1;
              std::wstring::_Tidy(v52, v18, 0);
              LOBYTE(v21) = 1;
              std::wstring::_Tidy(&v46, v21, 0);
            }
            catch ( ... )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v35 = Block;
                if ( v45 >= 8 )
                  v35 = (void **)Block[0];
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a18bd0ae1243b4e4f2d041cc2746c1f_Traceguids, v35);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
          }
          if ( v45 >= 8 )
            operator delete(Block[0]);
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v57);
      if ( v41 )
        RegCloseKey(v41);
      std::vector<std::wstring>::_Tidy(&v65);
      std::vector<std::wstring>::_Tidy(&v62);
      if ( v51 >= 8 )
        operator delete(v49[0]);
      v51 = 7;
      v50 = 0;
      LOWORD(v49[0]) = 0;
      if ( v55 >= 8 )
        operator delete(v54[0]);
    }
    else
    {
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"Characteristics",
        (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_INF_Characteristics);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"ComponentId",
        (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Driver_Identifier);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"Description",
        (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_FriendlyName);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"InfPath",
        (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_INF_Name);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"InfSection",
        (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_INF_Section);
      ObjectUpdateContext::SetValue(
        (ObjectUpdateContext *)v40,
        (struct RegistryKey *)&v39,
        L"LocDescription",
        (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_FriendlyName);
      RegistryKey::CreateSubKey(&v39, (HKEY)&v38, L"Ndi", 6u, 0, 0);
      NetSetup2::ActiveObject::GetProperty((NetSetup2::ActiveObject *)a2, (const struct _NETSETUPPROPKEY *)&v62);
      NetSetup2::ActiveObject::GetProperty((NetSetup2::ActiveObject *)a2, (const struct _NETSETUPPROPKEY *)&v65);
      if ( HIDWORD(v63) )
      {
        NetSetup2::Property::GetString(&v62, v49);
        v56 = a1;
        v57 = 0;
        v58 = 9;
        v59 = 0;
        KtmHandle = NetSetup2::TransactionObject::get_KtmHandle((NetSetup2::TransactionObject *)&v56);
        std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v57);
        if ( v50 )
        {
          std::wstring::wstring(v52, L"SYSTEM\\CurrentControlSet\\Control\\Network");
          std::wstring::wstring(Block, L"TemporaryInstallStage");
          v24 = std::operator+<wchar_t>(v54, v52);
          v25 = std::operator+<wchar_t>(&v46, v24, Block);
          std::operator+<wchar_t>(v60, v25, v49);
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(&v46, v26, 0);
          LOBYTE(v27) = 1;
          std::wstring::_Tidy(v54, v27, 0);
          hKey = HKEY_LOCAL_MACHINE;
          v28 = (const WCHAR *)v60;
          if ( v61 >= 8 )
            v28 = (const WCHAR *)v60[0];
          RegistryKey::TryOpenSubKey(&hKey, (HKEY)&v41, v28, 0x20019u, KtmHandle);
          if ( v41 )
          {
            std::operator+<wchar_t>(v54, Block, v49);
            RegistryKey::CopyTreeTo((RegistryKey *)&v41, (struct RegistryKey *)&v39);
            v29 = (const WCHAR *)v52;
            if ( v53 >= 8 )
              v29 = (const WCHAR *)v52[0];
            RegistryKey::OpenSubKey(&hKey, (HKEY)&v42, v29, 0xF003Fu, KtmHandle);
            v30 = (const wchar_t *)v54;
            if ( v55 >= 8 )
              v30 = v54[0];
            RegistryKey::DeleteSubKey((RegistryKey *)&v42, v30);
            NetSetup2::Property::Property(
              (NetSetup2::Property *)&v56,
              (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_NetCfg_StagingKeyInstalledFromTempKey,
              1);
            NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property>(a2, &v56);
            std::vector<_NETSETUPPROPKEY>::_Tidy((char *)&v59 + 4);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
            LOBYTE(v31) = 1;
            std::wstring::_Tidy(v54, v31, 0);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v60, v32, 0);
          LOBYTE(v33) = 1;
          std::wstring::_Tidy(Block, v33, 0);
          LOBYTE(v34) = 1;
          std::wstring::_Tidy(v52, v34, 0);
        }
        LOBYTE(v23) = 1;
        std::wstring::_Tidy(v49, v23, 0);
      }
      else if ( !NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v65) )
      {
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"HelpText",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_Description);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"Service",
          (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Driver_NtServiceName);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"ClsId",
          (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_NetCfg_NotifyObjectClsid);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"ComponentDll",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_NetCfg_NotifyObjectDllName);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"BindForm",
          (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Driver_BindName);
        ObjectUpdateContext::SetValue(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&v38,
          L"CoServices",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_INF_LegacyCoServices);
        RegistryKey::CreateSubKey(&v38, (HKEY)&hKey, L"Interfaces", 2u, 0, 0);
        ObjectUpdateContext::SetRanges(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&hKey,
          L"LowerRange",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Bind_LowerRange,
          L"nolower");
        ObjectUpdateContext::SetRanges(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&hKey,
          L"UpperRange",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Bind_UpperRange,
          L"noupper");
        ObjectUpdateContext::SetRanges(
          (ObjectUpdateContext *)v40,
          (struct RegistryKey *)&hKey,
          L"LowerExclude",
          (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Bind_LowerExclude,
          0);
        if ( *(_DWORD *)(a2 + 16) == 3 )
          ObjectUpdateContext::SetRanges(
            (ObjectUpdateContext *)v40,
            (struct RegistryKey *)&hKey,
            L"FilterMediaTypes",
            (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Bind_BottomRange,
            0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      }
      std::vector<_NETSETUPPROPKEY>::_Tidy(v67);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v64);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
    }
    if ( v39 )
      RegCloseKey(v39);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
  }
}

```

## disassembly

```asm
0x1800418b4  push    rbx
0x1800418b6  push    rsi
0x1800418b7  push    rdi
0x1800418b8  push    r12
0x1800418ba  push    r13
0x1800418bc  push    r14
0x1800418be  push    r15
0x1800418c0  sub     rsp, 1F0h
0x1800418c7  mov     [rsp+228h+var_1E8], 0FFFFFFFFFFFFFFFEh
0x1800418d0  mov     rax, cs:__security_cookie
0x1800418d7  xor     rax, rsp
0x1800418da  mov     [rsp+228h+var_40], rax
0x1800418e2  mov     r12, r8
0x1800418e5  mov     r14, rdx
0x1800418e8  mov     r15, rcx
0x1800418eb  xor     edi, edi
0x1800418ed  mov     esi, edi
0x1800418ef  mov     dword ptr [rsp+228h+var_1D8], edi
0x1800418f3  mov     r8, rdx
0x1800418f6  mov     rdx, rcx
0x1800418f9  lea     rcx, [rsp+228h+var_1D0]
0x1800418fe  call    ?GetDriverNetworkKey@@YA?AVRegistryKey@@AEAVTransaction@NetSetup2@@AEBVActiveObject@3@K@Z; GetDriverNetworkKey(NetSetup2::Transaction &,NetSetup2::ActiveObject const &,ulong)
0x180041903  nop
0x180041904  cmp     [rsp+228h+var_1D0], rdi
0x180041909  jnz     short loc_18004191A
0x18004190b  lea     rcx, [rsp+228h+var_1D0]
0x180041910  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041915  jmp     loc_18004241B
0x18004191a  lea     rax, [rsp+228h+var_1D0]
0x18004191f  mov     [rsp+228h+var_1C8], rax
0x180041924  mov     [rsp+228h+var_1C0], r14
0x180041929  mov     [rsp+228h+var_1B8], r12
0x18004192e  cmp     dword ptr [r14+10h], 2
0x180041933  jnz     loc_180041EAD
0x180041939  lea     r13, [r14+14h]
0x18004193d  mov     rdx, r13
0x180041940  lea     rcx, [rsp+228h+var_110]
0x180041948  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x18004194d  nop
0x18004194e  lea     rdx, aDevice_1; "\\Device\\"
0x180041955  lea     rcx, [rsp+228h+var_150]
0x18004195d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180041962  nop
0x180041963  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041967  xor     r8d, r8d
0x18004196a  lea     rdx, [rsp+228h+var_110]
0x180041972  lea     rcx, [rsp+228h+var_150]
0x18004197a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18004197f  xorps   xmm0, xmm0
0x180041982  movdqu  [rsp+228h+var_A0], xmm0
0x18004198b  mov     [rsp+228h+var_90], rdi
0x180041993  lea     rcx, [rsp+228h+var_A0]
0x18004199b  call    ?_Reserve@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800419a0  lea     rdx, [rsp+228h+var_150]
0x1800419a8  mov     rbx, qword ptr [rsp+228h+var_A0+8]
0x1800419b0  mov     rcx, rbx
0x1800419b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800419b8  add     rbx, 20h ; ' '
0x1800419bc  mov     qword ptr [rsp+228h+var_A0+8], rbx
0x1800419c4  xorps   xmm0, xmm0
0x1800419c7  movdqu  [rsp+228h+var_70], xmm0
0x1800419d0  mov     [rsp+228h+var_60], rdi
0x1800419d8  lea     rcx, [rsp+228h+var_70]
0x1800419e0  call    ?_Reserve@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800419e5  lea     rdx, [rsp+228h+var_110]
0x1800419ed  mov     rbx, qword ptr [rsp+228h+var_70+8]
0x1800419f5  mov     rcx, rbx
0x1800419f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800419fd  add     rbx, 20h ; ' '
0x180041a01  mov     qword ptr [rsp+228h+var_70+8], rbx
0x180041a09  mov     [rsp+228h+var_200], rdi
0x180041a0e  mov     [rsp+228h+var_208], rdi
0x180041a13  mov     r9d, 2
0x180041a19  lea     r8, aConnection; "Connection"
0x180041a20  lea     rdx, [rsp+228h+var_1B0]
0x180041a25  lea     rcx, [rsp+228h+var_1D0]
0x180041a2a  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180041a2f  nop
0x180041a30  lea     r9, NETSETUPPKEY_Interface_IfAlias; struct _NETSETUPPROPKEY *
0x180041a37  lea     r8, aName; "Name"
0x180041a3e  lea     rdx, [rsp+228h+var_1B0]; struct RegistryKey *
0x180041a43  lea     rcx, [rsp+228h+var_1C8]; this
0x180041a48  call    ?SetValue@ObjectUpdateContext@@QEAAXAEAVRegistryKey@@PEB_WAEBU_NETSETUPPROPKEY@@@Z; ObjectUpdateContext::SetValue(RegistryKey &,wchar_t const *,_NETSETUPPROPKEY const &)
0x180041a4d  lea     rbx, NETSETUPPKEY_Interface_PnpInstance
0x180041a54  mov     r9, rbx; struct _NETSETUPPROPKEY *
0x180041a57  lea     r8, aPnpinstanceid; "PnPInstanceId"
0x180041a5e  lea     rdx, [rsp+228h+var_1B0]; struct RegistryKey *
0x180041a63  lea     rcx, [rsp+228h+var_1C8]; this
0x180041a68  call    ?SetValue@ObjectUpdateContext@@QEAAXAEAVRegistryKey@@PEB_WAEBU_NETSETUPPROPKEY@@@Z; ObjectUpdateContext::SetValue(RegistryKey &,wchar_t const *,_NETSETUPPROPKEY const &)
0x180041a6d  mov     rax, [r14]
0x180041a70  mov     [rsp+228h+var_F0], rax
0x180041a78  mov     [rsp+228h+var_E8], rdi
0x180041a80  mov     eax, [r14+10h]
0x180041a84  mov     [rsp+228h+var_E0], eax
0x180041a8b  movups  xmm0, xmmword ptr [r13+0]
0x180041a90  movdqu  [rsp+228h+var_DC], xmm0
0x180041a99  mov     byte ptr [rsp+228h+var_208], 1
0x180041a9e  mov     r14d, 7
0x180041aa4  mov     r9d, r14d
0x180041aa7  lea     r8, [rsp+228h+var_F0]
0x180041aaf  mov     rdx, r15
0x180041ab2  lea     rcx, [rsp+228h+hKey]
0x180041ab7  call    ?OpenDeviceSoftwareKey@@YA?AVRegistryKey@@AEAVTransaction@NetSetup2@@AEBVNetworkInterface@3@K_N@Z; OpenDeviceSoftwareKey(NetSetup2::Transaction &,NetSetup2::NetworkInterface const &,ulong,bool)
0x180041abc  nop
0x180041abd  lea     rcx, [rsp+228h+var_F0]; this
0x180041ac5  call    ?get_PnpDeviceInterfaceNumber@NetworkInterface@NetSetup2@@QEBAKXZ; NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber(void)
0x180041aca  test    eax, eax
0x180041acc  jnz     loc_180041E10
0x180041ad2  cmp     [rsp+228h+hKey], rdi
0x180041ad7  jz      loc_180041E10
0x180041add  mov     r9, rbx; struct _NETSETUPPROPKEY *
0x180041ae0  lea     r8, aDeviceinstance; "DeviceInstanceID"
0x180041ae7  lea     rdx, [rsp+228h+hKey]; struct RegistryKey *
0x180041aec  lea     rcx, [rsp+228h+var_1C8]; this
0x180041af1  call    ?SetValue@ObjectUpdateContext@@QEAAXAEAVRegistryKey@@PEB_WAEBU_NETSETUPPROPKEY@@@Z; ObjectUpdateContext::SetValue(RegistryKey &,wchar_t const *,_NETSETUPPROPKEY const &)
0x180041af6  lea     r9, NETSETUPPKEY_Interface_PnpMatchingHardwareId; struct _NETSETUPPROPKEY *
0x180041afd  lea     r8, aComponentid; "ComponentId"
0x180041b04  lea     rdx, [rsp+228h+hKey]; struct RegistryKey *
0x180041b09  lea     rcx, [rsp+228h+var_1C8]; this
0x180041b0e  call    ?SetValue@ObjectUpdateContext@@QEAAXAEAVRegistryKey@@PEB_WAEBU_NETSETUPPROPKEY@@@Z; ObjectUpdateContext::SetValue(RegistryKey &,wchar_t const *,_NETSETUPPROPKEY const &)
0x180041b13  lea     r9, [rsp+228h+var_70]
0x180041b1b  lea     r8, aRootdevice; "RootDevice"
0x180041b22  lea     rcx, [rsp+228h+hKey]
0x180041b27  call    TimidUpdateMultiSZValueUnderSubKey
0x180041b2c  lea     r9, [rsp+228h+var_A0]
0x180041b34  lea     r8, aExport; "Export"
0x180041b3b  lea     rcx, [rsp+228h+hKey]
0x180041b40  call    TimidUpdateMultiSZValueUnderSubKey
0x180041b45  test    r12, r12
0x180041b48  jz      short loc_180041B67
0x180041b4a  mov     r8, rbx
0x180041b4d  lea     rdx, [rsp+228h+var_1C8]
0x180041b52  mov     rcx, r12
0x180041b55  call    ?TryGetProperty@PropertyArray@NetSetup2@@QEBA?AV?$Optional@AEBVProperty@NetSetup2@@@details@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::PropertyArray::TryGetProperty(_NETSETUPPROPKEY const &)
0x180041b5a  lea     esi, [r14-6]
0x180041b5e  cmp     [rax+8], dil
0x180041b62  mov     al, dil
0x180041b65  jz      short loc_180041B69
0x180041b67  mov     al, 1
0x180041b69  test    sil, 1
0x180041b6d  jz      short loc_180041B72
0x180041b6f  and     esi, 0FFFFFFFEh
0x180041b72  test    al, al
0x180041b74  jz      loc_180041E10
0x180041b7a  mov     rdx, r13
0x180041b7d  mov     rcx, r15
0x180041b80  call    MarkNicAsNeedingLinkageUpdates
0x180041b85  xor     r9d, r9d
0x180041b88  mov     r8, rbx; unsigned int
0x180041b8b  lea     rdx, [rsp+228h+var_180]; struct _NETSETUPPROPKEY *
0x180041b93  lea     rcx, [rsp+228h+var_F0]; this
0x180041b9b  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x180041ba0  or      esi, 8
0x180041ba3  or      esi, 4
0x180041ba6  cmp     dword ptr [rsp+228h+var_16C], edi
0x180041bad  jnz     short loc_180041BC9
0x180041baf  mov     [rsp+228h+var_188], r14
0x180041bb7  mov     [rsp+228h+var_190], rdi
0x180041bbf  mov     word ptr [rsp+228h+Block], di
0x180041bc7  jmp     short loc_180041BDF
0x180041bc9  lea     rdx, [rsp+228h+Block]
0x180041bd1  lea     rcx, [rsp+228h+var_180]
0x180041bd9  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x180041bde  nop
0x180041bdf  lea     rcx, [rsp+228h+var_16C+4]
0x180041be7  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180041bec  nop
0x180041bed  lea     rcx, [rsp+228h+var_F0]; this
0x180041bf5  call    ?get_IsPhysical@NetworkInterface@NetSetup2@@QEBA_NXZ; NetSetup2::NetworkInterface::get_IsPhysical(void)
0x180041bfa  test    al, al
0x180041bfc  jz      short loc_180041C49
0x180041bfe  cmp     [rsp+228h+var_190], rdi
0x180041c06  jz      short loc_180041C49
0x180041c08  xorps   xmm0, xmm0
0x180041c0b  mov     [rsp+228h+var_180], r15
0x180041c13  mov     [rsp+228h+var_178], rdi
0x180041c1b  mov     [rsp+228h+var_170], 9
0x180041c26  movdqu  [rsp+228h+var_16C], xmm0
0x180041c2f  or      esi, 2
0x180041c32  mov     dword ptr [rsp+228h+var_1D8], esi
0x180041c36  lea     rcx, [rsp+228h+var_180]; this
0x180041c3e  call    ?get_IsOnline@TransactionObject@NetSetup2@@QEBA_NXZ; NetSetup2::TransactionObject::get_IsOnline(void)
0x180041c43  test    al, al
0x180041c45  mov     bl, 1
0x180041c47  jnz     short loc_180041C4C
0x180041c49  mov     bl, dil
0x180041c4c  test    sil, 2
0x180041c50  jz      short loc_180041C5F
0x180041c52  lea     rcx, [rsp+228h+var_178]
0x180041c5a  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180041c5f  test    bl, bl
0x180041c61  jz      loc_180041DF7
0x180041c67  xorps   xmm0, xmm0
0x180041c6a  mov     [rsp+228h+var_180], r15
0x180041c72  mov     [rsp+228h+var_178], rdi
0x180041c7a  mov     [rsp+228h+var_170], 9
0x180041c85  movdqu  [rsp+228h+var_16C], xmm0
0x180041c8e  lea     rcx, [rsp+228h+var_180]; this
0x180041c96  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180041c9b  mov     rbx, rax
0x180041c9e  lea     rcx, [rsp+228h+var_178]
0x180041ca6  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180041cab  mov     rdx, rbx
0x180041cae  lea     rcx, [rsp+228h+var_1A8]
0x180041cb6  call    ?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z; RegistryKey::DuplicateFrom(HKEY__ *)
0x180041cbb  nop
0x180041cbc  lea     rdx, [rsp+228h+Block]
0x180041cc4  cmp     [rsp+228h+var_188], 8
0x180041ccd  cmovnb  rdx, [rsp+228h+Block]; wchar_t *
0x180041cd6  lea     rcx, [rsp+228h+var_1C8]; this
0x180041cdb  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x180041ce0  lea     rdx, aServices_0; "Services\\"
0x180041ce7  lea     rcx, [rsp+228h+var_180]
0x180041cef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180041cf4  nop
0x180041cf5  mov     [rsp+228h+var_118], r14
0x180041cfd  mov     [rsp+228h+var_120], rdi
0x180041d05  mov     word ptr [rsp+228h+var_130], di
0x180041d0d  lea     r8, [rsp+228h+var_130]
0x180041d15  lea     rdx, DEVPKEY_Device_Service
0x180041d1c  lea     rcx, [rsp+228h+var_1C8]
0x180041d21  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180041d26  test    al, al
0x180041d28  jz      loc_180041DBB
0x180041d2e  lea     r8, [rsp+228h+var_130]
0x180041d36  lea     rdx, [rsp+228h+var_180]
0x180041d3e  lea     rcx, [rsp+228h+var_C0]
0x180041d46  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x180041d4b  nop
0x180041d4c  lea     r8, [rsp+228h+var_C0]
0x180041d54  cmp     [rsp+228h+var_A8], 8
0x180041d5d  cmovnb  r8, [rsp+228h+var_C0]
0x180041d66  mov     [rsp+228h+var_208], rdi
0x180041d6b  mov     r9d, 2
0x180041d71  lea     rdx, [rsp+228h+var_1D8]
0x180041d76  lea     rcx, [rsp+228h+var_1A8]
0x180041d7e  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x180041d83  nop
0x180041d84  xor     r9d, r9d
0x180041d87  lea     r8d, [r9+1]
0x180041d8b  lea     rdx, aBootflags; "BootFlags"
0x180041d92  lea     rcx, [rsp+228h+var_1D8]
0x180041d97  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180041d9c  nop
0x180041d9d  lea     rcx, [rsp+228h+var_1D8]
0x180041da2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041da7  nop
0x180041da8  xor     r8d, r8d
0x180041dab  mov     dl, 1
0x180041dad  lea     rcx, [rsp+228h+var_C0]
0x180041db5  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180041dba  nop
0x180041dbb  xor     r8d, r8d
0x180041dbe  mov     dl, 1
0x180041dc0  lea     rcx, [rsp+228h+var_130]
0x180041dc8  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180041dcd  nop
0x180041dce  xor     r8d, r8d
0x180041dd1  mov     dl, 1
0x180041dd3  lea     rcx, [rsp+228h+var_180]
0x180041ddb  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180041de0  nop
0x180041de1  jmp     short loc_180041DE9
0x180041de3  xor     edi, edi
0x180041de5  lea     r14d, [rdi+7]
0x180041de9  lea     rcx, [rsp+228h+var_1A8]
0x180041df1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041df6  nop
0x180041df7  cmp     [rsp+228h+var_188], 8
0x180041e00  jb      short loc_180041E10
0x180041e02  mov     rcx, [rsp+228h+Block]; Block
0x180041e0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041e0f  nop
0x180041e10  mov     rcx, [rsp+228h+hKey]; hKey
0x180041e15  test    rcx, rcx
0x180041e18  jz      short loc_180041E21
0x180041e1a  call    cs:__imp_RegCloseKey
0x180041e20  nop
0x180041e21  lea     rcx, [rsp+228h+var_E8]
0x180041e29  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180041e2e  nop
0x180041e2f  mov     rcx, [rsp+228h+var_1B0]; hKey
0x180041e34  test    rcx, rcx
0x180041e37  jz      short loc_180041E40
0x180041e39  call    cs:__imp_RegCloseKey
0x180041e3f  nop
0x180041e40  lea     rcx, [rsp+228h+var_70]
0x180041e48  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041e4d  nop
0x180041e4e  lea     rcx, [rsp+228h+var_A0]
0x180041e56  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041e5b  nop
0x180041e5c  cmp     [rsp+228h+var_138], 8
0x180041e65  jb      short loc_180041E74
0x180041e67  mov     rcx, [rsp+228h+var_150]; Block
0x180041e6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041e74  mov     [rsp+228h+var_138], r14
0x180041e7c  mov     [rsp+228h+var_140], rdi
0x180041e84  mov     word ptr [rsp+228h+var_150], di
0x180041e8c  cmp     [rsp+228h+var_F8], 8
  ... truncated ...
```
