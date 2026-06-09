# ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceInfoModel::Serialize(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180145b34`
- end: `0x1801466aa`
- name: `?Serialize@DeviceInfoModel@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `2934`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180141f94`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x1800829ec`
- `0x180084574`
- `0x180086044`
- `0x18008a9c4`
- `0x18008f120`
- `0x1801377e4`
- `0x180137e50`
- `0x180141e48`
- `0x18014228c`
- `0x1801422c4`
- `0x180142a54`
- `0x180145850`
- `0x180145b34`
- `0x180200010`

## string_xrefs

- `0x180145c9b`: `Windows.Data.Json.JsonObject`
- `0x180145bac`: `Windows.Data.Json.JsonArray`
- `0x1801464a5`: `deviceInfoLinkIdFieldName`
- `0x180146555`: `deviceInfoLinkIdCreationTimeUtcFieldName`
- `0x180145be0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145c38`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145ccf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145d3a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145dae`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145e2b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145ed1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145f9e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x18014603e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x1801460dc`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180146185`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180146231`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x1801462dd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180146389`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180146439`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x1801464e9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180146599`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x18014666c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceInfoModel::Serialize(
        __int64 *a1,
        __int64 a2,
        char a3,
        __int64 *a4)
{
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  __int64 v13; // r15
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // esi
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  unsigned int v22; // esi
  int v23; // eax
  unsigned int v24; // edi
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64); // r15
  __int64 v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // edi
  BOOL v31; // esi
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  int v38; // edi
  int v39; // edi
  int v40; // ebx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-128h] BYREF
  __int64 v45; // [rsp+38h] [rbp-110h]
  _QWORD v46[3]; // [rsp+40h] [rbp-108h] BYREF
  _BYTE v47[24]; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-D8h]
  char v49; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-A8h] BYREF
  _OWORD v55[2]; // [rsp+A8h] [rbp-A0h] BYREF
  _OWORD v56[2]; // [rsp+C8h] [rbp-80h] BYREF
  _OWORD v57[2]; // [rsp+E8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v49 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v46[0] = &v49;
    v46[1] = a4;
    v46[2] = a2;
    v50 = 0;
    v45 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v45, &v50);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v51 = 0;
      v10 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
              &v50,
              &v51);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v12 = *a1;
        v13 = a1[1];
        while ( v12 != v13 )
        {
          v53 = 0;
          v45 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Data.Json.JsonObject",
            0x1Du,
            0x1Cu);
          v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                  v45,
                  &v53);
          v16 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v14,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            return v16;
          }
          LOBYTE(v15) = v49;
          v17 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize(v12, a2, v15, &v53);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB7,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v17,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            return v18;
          }
          v54 = 0;
          v19 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(&v53, &v54);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v19,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            return v20;
          }
          v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v51 + 104LL))(v51, v54);
          v22 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBB,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v21,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            return v22;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
          v12 += 104;
        }
        v52 = 0;
        v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(&v50, &v52);
        v24 = v23;
        if ( v23 >= 0 )
        {
          v25 = *a4;
          v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a4 + 56LL);
          v27 = v52;
          std::wstring::wstring(&hstringHeader, L"deviceInfoDeviceIdKeyListFieldName");
          v28 = std::unordered_map<std::wstring,std::wstring>::at(a2, &hstringHeader);
          v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
          v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &v54);
          v30 = v26(v25, *(_QWORD *)(v29 + 24), v27);
          v48 = 0;
          std::wstring::_Tidy_deallocate(&hstringHeader);
          if ( v30 >= 0 )
          {
            v31 = v49 != 0;
            v55[0] = 0;
            v55[1] = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v55[0]) = 0;
            v32 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureTimeFormat(a1 + 23, v49 != 0, v55);
            v33 = v32;
            if ( v32 >= 0 )
            {
              v56[0] = 0;
              v56[1] = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v56[0]) = 0;
              v34 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(
                      a1 + 19,
                      (unsigned int)(v31 + 1),
                      v56);
              v35 = v34;
              if ( v34 >= 0 )
              {
                v57[0] = 0;
                v57[1] = _mm_load_si128((const __m128i *)&_xmm);
                LOWORD(v57[0]) = 0;
                v36 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(
                        a1 + 15,
                        (unsigned int)(v31 + 1),
                        v57);
                v37 = v36;
                if ( v36 >= 0 )
                {
                  std::wstring::wstring(&hstringHeader, L"deviceInfoManufacturerFieldName");
                  v38 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                          v46,
                          &hstringHeader,
                          a1 + 3);
                  std::wstring::_Tidy_deallocate(&hstringHeader);
                  if ( v38 >= 0 )
                  {
                    std::wstring::wstring(&hstringHeader, L"deviceInfoModelNameFieldName");
                    v39 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                            v46,
                            &hstringHeader,
                            a1 + 7);
                    std::wstring::_Tidy_deallocate(&hstringHeader);
                    if ( v39 >= 0 )
                    {
                      std::wstring::wstring(&hstringHeader, L"deviceInfoSerialNumberFieldName");
                      v40 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                              v46,
                              &hstringHeader,
                              a1 + 11);
                      std::wstring::_Tidy_deallocate(&hstringHeader);
                      if ( v40 >= 0 )
                      {
                        std::wstring::wstring(&hstringHeader, L"deviceInfoSmbiosUuidFieldName");
                        v41 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                                v46,
                                &hstringHeader,
                                v57);
                        std::wstring::_Tidy_deallocate(&hstringHeader);
                        if ( v41 >= 0 )
                        {
                          std::wstring::wstring(&hstringHeader, L"deviceInfoLinkIdFieldName");
                          v42 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                                  v46,
                                  &hstringHeader,
                                  v56);
                          std::wstring::_Tidy_deallocate(&hstringHeader);
                          if ( v42 >= 0 )
                          {
                            std::wstring::wstring(&hstringHeader, L"deviceInfoLinkIdCreationTimeUtcFieldName");
                            v43 = ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize_::_3_::_lambda_2_::operator()(
                                    v46,
                                    &hstringHeader,
                                    v55);
                            std::wstring::_Tidy_deallocate(&hstringHeader);
                            if ( v43 >= 0 )
                            {
                              std::wstring::_Tidy_deallocate(v57);
                              std::wstring::_Tidy_deallocate(v56);
                              std::wstring::_Tidy_deallocate(v55);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                              return 0;
                            }
                            else
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0xD3,
                                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\de"
                                              "vicelinkinfo.cpp",
                                (const char *)(unsigned int)v43,
                                (int)hstringHeader.Reserved.Reserved1);
                              std::wstring::_Tidy_deallocate(v57);
                              std::wstring::_Tidy_deallocate(v56);
                              std::wstring::_Tidy_deallocate(v55);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                              return (unsigned int)v43;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xD2,
                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                              (const char *)(unsigned int)v42,
                              (int)hstringHeader.Reserved.Reserved1);
                            std::wstring::_Tidy_deallocate(v57);
                            std::wstring::_Tidy_deallocate(v56);
                            std::wstring::_Tidy_deallocate(v55);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                            return (unsigned int)v42;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xD1,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                            (const char *)(unsigned int)v41,
                            (int)hstringHeader.Reserved.Reserved1);
                          std::wstring::_Tidy_deallocate(v57);
                          std::wstring::_Tidy_deallocate(v56);
                          std::wstring::_Tidy_deallocate(v55);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                          return (unsigned int)v41;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xD0,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                          (const char *)(unsigned int)v40,
                          (int)hstringHeader.Reserved.Reserved1);
                        std::wstring::_Tidy_deallocate(v57);
                        std::wstring::_Tidy_deallocate(v56);
                        std::wstring::_Tidy_deallocate(v55);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                        return (unsigned int)v40;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xCF,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                        (const char *)(unsigned int)v39,
                        (int)hstringHeader.Reserved.Reserved1);
                      std::wstring::_Tidy_deallocate(v57);
                      std::wstring::_Tidy_deallocate(v56);
                      std::wstring::_Tidy_deallocate(v55);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                      return (unsigned int)v39;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xCE,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                      (const char *)(unsigned int)v38,
                      (int)hstringHeader.Reserved.Reserved1);
                    std::wstring::_Tidy_deallocate(v57);
                    std::wstring::_Tidy_deallocate(v56);
                    std::wstring::_Tidy_deallocate(v55);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                    return (unsigned int)v38;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xCC,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                    (const char *)(unsigned int)v36,
                    (int)hstringHeader.Reserved.Reserved1);
                  std::wstring::_Tidy_deallocate(v57);
                  std::wstring::_Tidy_deallocate(v56);
                  std::wstring::_Tidy_deallocate(v55);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                  return v37;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                  (const char *)(unsigned int)v34,
                  (int)hstringHeader.Reserved.Reserved1);
                std::wstring::_Tidy_deallocate(v56);
                std::wstring::_Tidy_deallocate(v55);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                return v35;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                (const char *)(unsigned int)v32,
                (int)hstringHeader.Reserved.Reserved1);
              std::wstring::_Tidy_deallocate(v55);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
              return v33;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v30,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            return (unsigned int)v30;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
            (const char *)(unsigned int)v23,
            (int)hstringHeader.Reserved.Reserved1);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          return v24;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
          (const char *)(unsigned int)v10,
          (int)hstringHeader.Reserved.Reserved1);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        return v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
        (const char *)(unsigned int)v7,
        (int)hstringHeader.Reserved.Reserved1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
      (const char *)0x80004001LL,
      (int)hstringHeader.Reserved.Reserved1);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180145b34  push    rbx
0x180145b36  push    rsi
0x180145b37  push    rdi
0x180145b38  push    r12
0x180145b3a  push    r14
0x180145b3c  push    r15
0x180145b3e  sub     rsp, 118h
0x180145b45  mov     rax, cs:__security_cookie
0x180145b4c  xor     rax, rsp
0x180145b4f  mov     [rsp+148h+var_40], rax
0x180145b57  mov     r12, r9
0x180145b5a  mov     r14, rdx
0x180145b5d  mov     rbx, rcx
0x180145b60  mov     [rsp+148h+var_D0], r8b
0x180145b65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180145b6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180145b71  test    al, al
0x180145b73  jz      loc_18014665C
0x180145b79  lea     rax, [rsp+148h+var_D0]
0x180145b7e  mov     [rsp+148h+var_108], rax
0x180145b83  mov     [rsp+148h+var_100], r12
0x180145b88  mov     [rsp+148h+var_F8], r14
0x180145b8d  mov     [rsp+148h+var_C8], 0
0x180145b99  mov     [rsp+148h+var_110], 0
0x180145ba2  mov     r9d, 1Bh; unsigned int
0x180145ba8  lea     r8d, [r9+1]; unsigned int
0x180145bac  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180145bb3  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180145bb8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180145bbd  lea     rdx, [rsp+148h+var_C8]
0x180145bc5  mov     rcx, [rsp+148h+var_110]
0x180145bca  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x180145bcf  mov     edi, eax
0x180145bd1  test    eax, eax
0x180145bd3  jns     short loc_180145C06
0x180145bd5  mov     rcx, [rsp+148h]; this
0x180145bdd  mov     r9d, eax; char *
0x180145be0  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145be7  mov     edx, 0AEh; void *
0x180145bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145bf1  nop
0x180145bf2  lea     rcx, [rsp+148h+var_C8]
0x180145bfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145bff  mov     eax, edi
0x180145c01  jmp     loc_180146688
0x180145c06  mov     [rsp+148h+var_C0], 0
0x180145c12  lea     rdx, [rsp+148h+var_C0]
0x180145c1a  lea     rcx, [rsp+148h+var_C8]
0x180145c22  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180145c27  mov     edi, eax
0x180145c29  test    eax, eax
0x180145c2b  jns     short loc_180145C6C
0x180145c2d  mov     rcx, [rsp+148h]; this
0x180145c35  mov     r9d, eax; char *
0x180145c38  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145c3f  mov     edx, 0B1h; void *
0x180145c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145c49  nop
0x180145c4a  lea     rcx, [rsp+148h+var_C0]
0x180145c52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145c57  nop
0x180145c58  lea     rcx, [rsp+148h+var_C8]
0x180145c60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145c65  mov     eax, edi
0x180145c67  jmp     loc_180146688
0x180145c6c  mov     rdi, [rbx]
0x180145c6f  mov     r15, [rbx+8]
0x180145c73  cmp     rdi, r15
0x180145c76  jz      loc_180145E9F
0x180145c7c  mov     [rsp+148h+var_B0], 0
0x180145c88  mov     [rsp+148h+var_110], 0
0x180145c91  mov     r9d, 1Ch; unsigned int
0x180145c97  lea     r8d, [r9+1]; unsigned int
0x180145c9b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180145ca2  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180145ca7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180145cac  lea     rdx, [rsp+148h+var_B0]
0x180145cb4  mov     rcx, [rsp+148h+var_110]
0x180145cb9  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180145cbe  mov     esi, eax
0x180145cc0  test    eax, eax
0x180145cc2  jns     short loc_180145D11
0x180145cc4  mov     rcx, [rsp+148h]; this
0x180145ccc  mov     r9d, eax; char *
0x180145ccf  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145cd6  mov     edx, 0B6h; void *
0x180145cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145ce0  nop
0x180145ce1  lea     rcx, [rsp+148h+var_B0]
0x180145ce9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145cee  nop
0x180145cef  lea     rcx, [rsp+148h+var_C0]
0x180145cf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145cfc  nop
0x180145cfd  lea     rcx, [rsp+148h+var_C8]
0x180145d05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145d0a  mov     eax, esi
0x180145d0c  jmp     loc_180146688
0x180145d11  lea     r9, [rsp+148h+var_B0]
0x180145d19  mov     r8b, [rsp+148h+var_D0]
0x180145d1e  mov     rdx, r14
0x180145d21  mov     rcx, rdi
0x180145d24  call    ?Serialize@DeviceIdKeyInfoModel@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180145d29  mov     esi, eax
0x180145d2b  test    eax, eax
0x180145d2d  jns     short loc_180145D7C
0x180145d2f  mov     rcx, [rsp+148h]; this
0x180145d37  mov     r9d, eax; char *
0x180145d3a  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145d41  mov     edx, 0B7h; void *
0x180145d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145d4b  nop
0x180145d4c  lea     rcx, [rsp+148h+var_B0]
0x180145d54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145d59  nop
0x180145d5a  lea     rcx, [rsp+148h+var_C0]
0x180145d62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145d67  nop
0x180145d68  lea     rcx, [rsp+148h+var_C8]
0x180145d70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145d75  mov     eax, esi
0x180145d77  jmp     loc_180146688
0x180145d7c  mov     [rsp+148h+var_A8], 0
0x180145d88  lea     rdx, [rsp+148h+var_A8]
0x180145d90  lea     rcx, [rsp+148h+var_B0]
0x180145d98  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180145d9d  mov     esi, eax
0x180145d9f  test    eax, eax
0x180145da1  jns     short loc_180145DFE
0x180145da3  mov     rcx, [rsp+148h]; this
0x180145dab  mov     r9d, eax; char *
0x180145dae  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145db5  mov     edx, 0BAh; void *
0x180145dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145dbf  nop
0x180145dc0  lea     rcx, [rsp+148h+var_A8]
0x180145dc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145dcd  nop
0x180145dce  lea     rcx, [rsp+148h+var_B0]
0x180145dd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145ddb  nop
0x180145ddc  lea     rcx, [rsp+148h+var_C0]
0x180145de4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145de9  nop
0x180145dea  lea     rcx, [rsp+148h+var_C8]
0x180145df2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145df7  mov     eax, esi
0x180145df9  jmp     loc_180146688
0x180145dfe  mov     rcx, [rsp+148h+var_C0]
0x180145e06  mov     rax, [rcx]
0x180145e09  mov     rdx, [rsp+148h+var_A8]
0x180145e11  mov     rax, [rax+68h]
0x180145e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145e1a  mov     esi, eax
0x180145e1c  test    eax, eax
0x180145e1e  jns     short loc_180145E7B
0x180145e20  mov     rcx, [rsp+148h]; this
0x180145e28  mov     r9d, eax; char *
0x180145e2b  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145e32  mov     edx, 0BBh; void *
0x180145e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145e3c  nop
0x180145e3d  lea     rcx, [rsp+148h+var_A8]
0x180145e45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e4a  nop
0x180145e4b  lea     rcx, [rsp+148h+var_B0]
0x180145e53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e58  nop
0x180145e59  lea     rcx, [rsp+148h+var_C0]
0x180145e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e66  nop
0x180145e67  lea     rcx, [rsp+148h+var_C8]
0x180145e6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e74  mov     eax, esi
0x180145e76  jmp     loc_180146688
0x180145e7b  lea     rcx, [rsp+148h+var_A8]
0x180145e83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e88  nop
0x180145e89  lea     rcx, [rsp+148h+var_B0]
0x180145e91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145e96  add     rdi, 68h ; 'h'
0x180145e9a  jmp     loc_180145C73
0x180145e9f  mov     [rsp+148h+var_B8], 0
0x180145eab  lea     rdx, [rsp+148h+var_B8]
0x180145eb3  lea     rcx, [rsp+148h+var_C8]
0x180145ebb  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180145ec0  mov     edi, eax
0x180145ec2  test    eax, eax
0x180145ec4  jns     short loc_180145F13
0x180145ec6  mov     rcx, [rsp+148h]; this
0x180145ece  mov     r9d, eax; char *
0x180145ed1  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145ed8  mov     edx, 0BFh; void *
0x180145edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145ee2  nop
0x180145ee3  lea     rcx, [rsp+148h+var_B8]
0x180145eeb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145ef0  nop
0x180145ef1  lea     rcx, [rsp+148h+var_C0]
0x180145ef9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145efe  nop
0x180145eff  lea     rcx, [rsp+148h+var_C8]
0x180145f07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145f0c  mov     eax, edi
0x180145f0e  jmp     loc_180146688
0x180145f13  mov     rdi, [r12]
0x180145f17  mov     rax, [rdi]
0x180145f1a  mov     r15, [rax+38h]
0x180145f1e  mov     rsi, [rsp+148h+var_B8]
0x180145f26  lea     rdx, aDeviceinfodevi; "deviceInfoDeviceIdKeyListFieldName"
0x180145f2d  lea     rcx, [rsp+148h+hstringHeader]
0x180145f32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180145f37  nop
0x180145f38  lea     rdx, [rsp+148h+hstringHeader]
0x180145f3d  mov     rcx, r14
0x180145f40  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x180145f45  mov     rcx, rax
0x180145f48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180145f4d  mov     [rsp+148h+var_A8], rax
0x180145f55  lea     rdx, [rsp+148h+var_A8]
0x180145f5d  lea     rcx, [rsp+148h+var_F0]
0x180145f62  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180145f67  nop
0x180145f68  mov     r8, rsi
0x180145f6b  mov     rdx, [rax+18h]
0x180145f6f  mov     rcx, rdi
0x180145f72  mov     rax, r15
0x180145f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145f7a  mov     edi, eax
0x180145f7c  mov     [rsp+148h+var_D8], 0
0x180145f85  lea     rcx, [rsp+148h+hstringHeader]
0x180145f8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145f8f  test    edi, edi
0x180145f91  jns     short loc_180145FE0
0x180145f93  mov     rcx, [rsp+148h]; this
0x180145f9b  mov     r9d, edi; char *
0x180145f9e  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145fa5  mov     edx, 0C0h; void *
0x180145faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145faf  nop
0x180145fb0  lea     rcx, [rsp+148h+var_B8]
0x180145fb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145fbd  nop
0x180145fbe  lea     rcx, [rsp+148h+var_C0]
0x180145fc6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145fcb  nop
0x180145fcc  lea     rcx, [rsp+148h+var_C8]
0x180145fd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145fd9  mov     eax, edi
0x180145fdb  jmp     loc_180146688
0x180145fe0  mov     cl, [rsp+148h+var_D0]
0x180145fe4  mov     al, cl
0x180145fe6  neg     al
0x180145fe8  sbb     esi, esi
0x180145fea  neg     esi
0x180145fec  xor     edx, edx
0x180145fee  test    cl, cl
0x180145ff0  setnz   dl
0x180145ff3  xorps   xmm0, xmm0
0x180145ff6  movups  [rsp+148h+var_A0], xmm0
0x180145ffe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180146006  movdqu  [rsp+148h+var_90], xmm1
0x18014600f  xor     eax, eax
0x180146011  mov     word ptr [rsp+148h+var_A0], ax
0x180146019  lea     rcx, [rbx+0B8h]
0x180146020  lea     r8, [rsp+148h+var_A0]
0x180146028  call    ?EnsureTimeFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureTimeFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::TimeFormat,std::wstring &)
0x18014602d  mov     edi, eax
0x18014602f  test    eax, eax
0x180146031  jns     short loc_18014608E
0x180146033  mov     rcx, [rsp+148h]; this
0x18014603b  mov     r9d, eax; char *
0x18014603e  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180146045  mov     edx, 0C6h; void *
0x18014604a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014604f  nop
0x180146050  lea     rcx, [rsp+148h+var_A0]
0x180146058  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014605d  nop
0x18014605e  lea     rcx, [rsp+148h+var_B8]
0x180146066  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014606b  nop
0x18014606c  lea     rcx, [rsp+148h+var_C0]
0x180146074  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180146079  nop
0x18014607a  lea     rcx, [rsp+148h+var_C8]
0x180146082  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180146087  mov     eax, edi
0x180146089  jmp     loc_180146688
0x18014608e  xorps   xmm0, xmm0
0x180146091  movups  [rsp+148h+var_80], xmm0
0x180146099  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801460a1  movdqu  [rsp+148h+var_70], xmm1
0x1801460aa  xor     eax, eax
0x1801460ac  mov     word ptr [rsp+148h+var_80], ax
0x1801460b4  lea     rcx, [rbx+98h]
0x1801460bb  lea     r8, [rsp+148h+var_80]
0x1801460c3  lea     edx, [rsi+1]
0x1801460c6  call    ?EnsureGuidFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4GuidFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x1801460cb  mov     edi, eax
  ... truncated ...
```
