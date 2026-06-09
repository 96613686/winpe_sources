# ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceInfoModel::Serialize(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180141a34`
- end: `0x1801425aa`
- name: `?Serialize@DeviceInfoModel@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `2934`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013dedc`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x180081f1c`
- `0x1800839bc`
- `0x1800853a0`
- `0x180089b58`
- `0x18008e008`
- `0x18013395c`
- `0x180133fc8`
- `0x18013dd98`
- `0x18013e1cc`
- `0x18013e204`
- `0x18013e968`
- `0x180141750`
- `0x180141a34`
- `0x1801fa010`

## string_xrefs

- `0x180141b9b`: `Windows.Data.Json.JsonObject`
- `0x180141aac`: `Windows.Data.Json.JsonArray`
- `0x180142455`: `deviceInfoLinkIdCreationTimeUtcFieldName`
- `0x1801423a5`: `deviceInfoLinkIdFieldName`
- `0x180141ae0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141b38`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141bcf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141c3a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141cae`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141d2b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141dd1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141e9e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141f3e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141fdc`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180142085`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180142131`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x1801421dd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180142289`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180142339`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x1801423e9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180142499`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x18014256c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`

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
0x180141a34  push    rbx
0x180141a36  push    rsi
0x180141a37  push    rdi
0x180141a38  push    r12
0x180141a3a  push    r14
0x180141a3c  push    r15
0x180141a3e  sub     rsp, 118h
0x180141a45  mov     rax, cs:__security_cookie
0x180141a4c  xor     rax, rsp
0x180141a4f  mov     [rsp+148h+var_40], rax
0x180141a57  mov     r12, r9
0x180141a5a  mov     r14, rdx
0x180141a5d  mov     rbx, rcx
0x180141a60  mov     [rsp+148h+var_D0], r8b
0x180141a65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180141a6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180141a71  test    al, al
0x180141a73  jz      loc_18014255C
0x180141a79  lea     rax, [rsp+148h+var_D0]
0x180141a7e  mov     [rsp+148h+var_108], rax
0x180141a83  mov     [rsp+148h+var_100], r12
0x180141a88  mov     [rsp+148h+var_F8], r14
0x180141a8d  mov     [rsp+148h+var_C8], 0
0x180141a99  mov     [rsp+148h+var_110], 0
0x180141aa2  mov     r9d, 1Bh; unsigned int
0x180141aa8  lea     r8d, [r9+1]; unsigned int
0x180141aac  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180141ab3  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180141ab8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180141abd  lea     rdx, [rsp+148h+var_C8]
0x180141ac5  mov     rcx, [rsp+148h+var_110]
0x180141aca  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x180141acf  mov     edi, eax
0x180141ad1  test    eax, eax
0x180141ad3  jns     short loc_180141B06
0x180141ad5  mov     rcx, [rsp+148h]; this
0x180141add  mov     r9d, eax; char *
0x180141ae0  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141ae7  mov     edx, 0AEh; void *
0x180141aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141af1  nop
0x180141af2  lea     rcx, [rsp+148h+var_C8]
0x180141afa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141aff  mov     eax, edi
0x180141b01  jmp     loc_180142588
0x180141b06  mov     [rsp+148h+var_C0], 0
0x180141b12  lea     rdx, [rsp+148h+var_C0]
0x180141b1a  lea     rcx, [rsp+148h+var_C8]
0x180141b22  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180141b27  mov     edi, eax
0x180141b29  test    eax, eax
0x180141b2b  jns     short loc_180141B6C
0x180141b2d  mov     rcx, [rsp+148h]; this
0x180141b35  mov     r9d, eax; char *
0x180141b38  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141b3f  mov     edx, 0B1h; void *
0x180141b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141b49  nop
0x180141b4a  lea     rcx, [rsp+148h+var_C0]
0x180141b52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141b57  nop
0x180141b58  lea     rcx, [rsp+148h+var_C8]
0x180141b60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141b65  mov     eax, edi
0x180141b67  jmp     loc_180142588
0x180141b6c  mov     rdi, [rbx]
0x180141b6f  mov     r15, [rbx+8]
0x180141b73  cmp     rdi, r15
0x180141b76  jz      loc_180141D9F
0x180141b7c  mov     [rsp+148h+var_B0], 0
0x180141b88  mov     [rsp+148h+var_110], 0
0x180141b91  mov     r9d, 1Ch; unsigned int
0x180141b97  lea     r8d, [r9+1]; unsigned int
0x180141b9b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180141ba2  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180141ba7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180141bac  lea     rdx, [rsp+148h+var_B0]
0x180141bb4  mov     rcx, [rsp+148h+var_110]
0x180141bb9  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180141bbe  mov     esi, eax
0x180141bc0  test    eax, eax
0x180141bc2  jns     short loc_180141C11
0x180141bc4  mov     rcx, [rsp+148h]; this
0x180141bcc  mov     r9d, eax; char *
0x180141bcf  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141bd6  mov     edx, 0B6h; void *
0x180141bdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141be0  nop
0x180141be1  lea     rcx, [rsp+148h+var_B0]
0x180141be9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141bee  nop
0x180141bef  lea     rcx, [rsp+148h+var_C0]
0x180141bf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141bfc  nop
0x180141bfd  lea     rcx, [rsp+148h+var_C8]
0x180141c05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141c0a  mov     eax, esi
0x180141c0c  jmp     loc_180142588
0x180141c11  lea     r9, [rsp+148h+var_B0]
0x180141c19  mov     r8b, [rsp+148h+var_D0]
0x180141c1e  mov     rdx, r14
0x180141c21  mov     rcx, rdi
0x180141c24  call    ?Serialize@DeviceIdKeyInfoModel@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_NAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkInfo::DeviceIdKeyInfoModel::Serialize(std::unordered_map<std::wstring,std::wstring> const &,bool,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180141c29  mov     esi, eax
0x180141c2b  test    eax, eax
0x180141c2d  jns     short loc_180141C7C
0x180141c2f  mov     rcx, [rsp+148h]; this
0x180141c37  mov     r9d, eax; char *
0x180141c3a  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141c41  mov     edx, 0B7h; void *
0x180141c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141c4b  nop
0x180141c4c  lea     rcx, [rsp+148h+var_B0]
0x180141c54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141c59  nop
0x180141c5a  lea     rcx, [rsp+148h+var_C0]
0x180141c62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141c67  nop
0x180141c68  lea     rcx, [rsp+148h+var_C8]
0x180141c70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141c75  mov     eax, esi
0x180141c77  jmp     loc_180142588
0x180141c7c  mov     [rsp+148h+var_A8], 0
0x180141c88  lea     rdx, [rsp+148h+var_A8]
0x180141c90  lea     rcx, [rsp+148h+var_B0]
0x180141c98  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180141c9d  mov     esi, eax
0x180141c9f  test    eax, eax
0x180141ca1  jns     short loc_180141CFE
0x180141ca3  mov     rcx, [rsp+148h]; this
0x180141cab  mov     r9d, eax; char *
0x180141cae  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141cb5  mov     edx, 0BAh; void *
0x180141cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141cbf  nop
0x180141cc0  lea     rcx, [rsp+148h+var_A8]
0x180141cc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141ccd  nop
0x180141cce  lea     rcx, [rsp+148h+var_B0]
0x180141cd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141cdb  nop
0x180141cdc  lea     rcx, [rsp+148h+var_C0]
0x180141ce4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141ce9  nop
0x180141cea  lea     rcx, [rsp+148h+var_C8]
0x180141cf2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141cf7  mov     eax, esi
0x180141cf9  jmp     loc_180142588
0x180141cfe  mov     rcx, [rsp+148h+var_C0]
0x180141d06  mov     rax, [rcx]
0x180141d09  mov     rdx, [rsp+148h+var_A8]
0x180141d11  mov     rax, [rax+68h]
0x180141d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141d1a  mov     esi, eax
0x180141d1c  test    eax, eax
0x180141d1e  jns     short loc_180141D7B
0x180141d20  mov     rcx, [rsp+148h]; this
0x180141d28  mov     r9d, eax; char *
0x180141d2b  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141d32  mov     edx, 0BBh; void *
0x180141d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141d3c  nop
0x180141d3d  lea     rcx, [rsp+148h+var_A8]
0x180141d45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d4a  nop
0x180141d4b  lea     rcx, [rsp+148h+var_B0]
0x180141d53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d58  nop
0x180141d59  lea     rcx, [rsp+148h+var_C0]
0x180141d61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d66  nop
0x180141d67  lea     rcx, [rsp+148h+var_C8]
0x180141d6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d74  mov     eax, esi
0x180141d76  jmp     loc_180142588
0x180141d7b  lea     rcx, [rsp+148h+var_A8]
0x180141d83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d88  nop
0x180141d89  lea     rcx, [rsp+148h+var_B0]
0x180141d91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141d96  add     rdi, 68h ; 'h'
0x180141d9a  jmp     loc_180141B73
0x180141d9f  mov     [rsp+148h+var_B8], 0
0x180141dab  lea     rdx, [rsp+148h+var_B8]
0x180141db3  lea     rcx, [rsp+148h+var_C8]
0x180141dbb  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180141dc0  mov     edi, eax
0x180141dc2  test    eax, eax
0x180141dc4  jns     short loc_180141E13
0x180141dc6  mov     rcx, [rsp+148h]; this
0x180141dce  mov     r9d, eax; char *
0x180141dd1  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141dd8  mov     edx, 0BFh; void *
0x180141ddd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141de2  nop
0x180141de3  lea     rcx, [rsp+148h+var_B8]
0x180141deb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141df0  nop
0x180141df1  lea     rcx, [rsp+148h+var_C0]
0x180141df9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141dfe  nop
0x180141dff  lea     rcx, [rsp+148h+var_C8]
0x180141e07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141e0c  mov     eax, edi
0x180141e0e  jmp     loc_180142588
0x180141e13  mov     rdi, [r12]
0x180141e17  mov     rax, [rdi]
0x180141e1a  mov     r15, [rax+38h]
0x180141e1e  mov     rsi, [rsp+148h+var_B8]
0x180141e26  lea     rdx, aDeviceinfodevi; "deviceInfoDeviceIdKeyListFieldName"
0x180141e2d  lea     rcx, [rsp+148h+hstringHeader]
0x180141e32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180141e37  nop
0x180141e38  lea     rdx, [rsp+148h+hstringHeader]
0x180141e3d  mov     rcx, r14
0x180141e40  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x180141e45  mov     rcx, rax
0x180141e48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180141e4d  mov     [rsp+148h+var_A8], rax
0x180141e55  lea     rdx, [rsp+148h+var_A8]
0x180141e5d  lea     rcx, [rsp+148h+var_F0]
0x180141e62  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180141e67  nop
0x180141e68  mov     r8, rsi
0x180141e6b  mov     rdx, [rax+18h]
0x180141e6f  mov     rcx, rdi
0x180141e72  mov     rax, r15
0x180141e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141e7a  mov     edi, eax
0x180141e7c  mov     [rsp+148h+var_D8], 0
0x180141e85  lea     rcx, [rsp+148h+hstringHeader]
0x180141e8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141e8f  test    edi, edi
0x180141e91  jns     short loc_180141EE0
0x180141e93  mov     rcx, [rsp+148h]; this
0x180141e9b  mov     r9d, edi; char *
0x180141e9e  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141ea5  mov     edx, 0C0h; void *
0x180141eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141eaf  nop
0x180141eb0  lea     rcx, [rsp+148h+var_B8]
0x180141eb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141ebd  nop
0x180141ebe  lea     rcx, [rsp+148h+var_C0]
0x180141ec6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141ecb  nop
0x180141ecc  lea     rcx, [rsp+148h+var_C8]
0x180141ed4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141ed9  mov     eax, edi
0x180141edb  jmp     loc_180142588
0x180141ee0  mov     cl, [rsp+148h+var_D0]
0x180141ee4  mov     al, cl
0x180141ee6  neg     al
0x180141ee8  sbb     esi, esi
0x180141eea  neg     esi
0x180141eec  xor     edx, edx
0x180141eee  test    cl, cl
0x180141ef0  setnz   dl
0x180141ef3  xorps   xmm0, xmm0
0x180141ef6  movups  [rsp+148h+var_A0], xmm0
0x180141efe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180141f06  movdqu  [rsp+148h+var_90], xmm1
0x180141f0f  xor     eax, eax
0x180141f11  mov     word ptr [rsp+148h+var_A0], ax
0x180141f19  lea     rcx, [rbx+0B8h]
0x180141f20  lea     r8, [rsp+148h+var_A0]
0x180141f28  call    ?EnsureTimeFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureTimeFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::TimeFormat,std::wstring &)
0x180141f2d  mov     edi, eax
0x180141f2f  test    eax, eax
0x180141f31  jns     short loc_180141F8E
0x180141f33  mov     rcx, [rsp+148h]; this
0x180141f3b  mov     r9d, eax; char *
0x180141f3e  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141f45  mov     edx, 0C6h; void *
0x180141f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141f4f  nop
0x180141f50  lea     rcx, [rsp+148h+var_A0]
0x180141f58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141f5d  nop
0x180141f5e  lea     rcx, [rsp+148h+var_B8]
0x180141f66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141f6b  nop
0x180141f6c  lea     rcx, [rsp+148h+var_C0]
0x180141f74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141f79  nop
0x180141f7a  lea     rcx, [rsp+148h+var_C8]
0x180141f82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141f87  mov     eax, edi
0x180141f89  jmp     loc_180142588
0x180141f8e  xorps   xmm0, xmm0
0x180141f91  movups  [rsp+148h+var_80], xmm0
0x180141f99  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180141fa1  movdqu  [rsp+148h+var_70], xmm1
0x180141faa  xor     eax, eax
0x180141fac  mov     word ptr [rsp+148h+var_80], ax
0x180141fb4  lea     rcx, [rbx+98h]
0x180141fbb  lea     r8, [rsp+148h+var_80]
0x180141fc3  lea     edx, [rsi+1]
0x180141fc6  call    ?EnsureGuidFormat@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4GuidFormat@1234@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::EnsureGuidFormat(std::wstring const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x180141fcb  mov     edi, eax
  ... truncated ...
```
