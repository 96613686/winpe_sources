# ModernDeployment::Autopilot::Core::DeviceLinkInfo::PopulateJsonEnvelope(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180140dc4`
- end: `0x1801412b7`
- name: `?PopulateJsonEnvelope@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@AEAV86@@Z`
- size: `1267`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013d01c`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800839bc`
- `0x1800853a0`
- `0x180089b58`
- `0x18008a014`
- `0x18008a0a8`
- `0x18008e438`
- `0x18008f068`
- `0x1800951d0`
- `0x180134534`
- `0x18013dd98`
- `0x180140dc4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801411f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801411f3`

## string_xrefs

- `0x180140e35`: `Windows.Data.Json.JsonObject`
- `0x180140f2b`: `linkIdCreationTimeField`
- `0x180140f58`: `linkInfoCreationTimeField`
- `0x180140efe`: `linkIdField`
- `0x180140fd0`: `jsonEnvelopeVersionFieldName`
- `0x180140ea4`: `jsonEnvelopeSerialNumberFieldName`
- `0x180140f67`: `jsonEnvelopeDeviceLinkInfoCreationTimeFieldName`
- `0x180140f94`: `jsonEnvelopeDataFieldName`
- `0x180140f0d`: `jsonEnvelopeLinkIdFieldName`
- `0x180140f3a`: `jsonEnvelopeLinkIdCreationTimeFieldName`
- `0x180140ec5`: `jsonEnvelopeManufacturerFieldName`
- `0x180140ee6`: `jsonEnvelopeModelFieldName`
- `0x180140e69`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141025`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141127`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x18014119e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180141262`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkInfo::PopulateJsonEnvelope(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // edi
  int v10; // eax
  unsigned int v11; // esi
  const char *v12; // r9
  __int64 result; // rax
  const unsigned __int16 *v14; // rsi
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  int v17; // esi
  int i; // esi
  bool v19; // r15
  const unsigned __int16 *v20; // r15
  __int64 v21; // rax
  const unsigned __int16 *v22; // rax
  int v23; // r14d
  int v24; // eax
  unsigned int v25; // edi
  PCWSTR StringRawBuffer; // rdx
  __int64 v27; // rax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-148h] BYREF
  __int64 v29; // [rsp+38h] [rbp-130h]
  const wchar_t *v30; // [rsp+40h] [rbp-128h]
  const wchar_t *v31; // [rsp+48h] [rbp-120h]
  _QWORD v32[20]; // [rsp+50h] [rbp-118h]
  _QWORD *v33; // [rsp+F0h] [rbp-78h]
  struct Windows::Data::Json::IJsonObject *v34; // [rsp+F8h] [rbp-70h] BYREF
  HSTRING string; // [rsp+100h] [rbp-68h] BYREF
  _BYTE v36[32]; // [rsp+108h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  try
  {
    v33 = a2;
    v9 = 0;
    LODWORD(v34) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      v34 = 0;
      v29 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      v10 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v29, &v34);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v30 = L"serialField";
        v31 = L"jsonEnvelopeSerialNumberFieldName";
        v32[0] = a1 + 120;
        v32[1] = L"manufacturerField";
        v32[2] = L"jsonEnvelopeManufacturerFieldName";
        v32[3] = a1 + 56;
        v32[4] = L"modelField";
        v32[5] = L"jsonEnvelopeModelFieldName";
        v32[6] = a1 + 88;
        v32[7] = L"linkIdField";
        v32[8] = L"jsonEnvelopeLinkIdFieldName";
        v32[9] = a1 + 184;
        v32[10] = L"linkIdCreationTimeField";
        v32[11] = L"jsonEnvelopeLinkIdCreationTimeFieldName";
        v32[12] = a1 + 216;
        v32[13] = L"linkInfoCreationTimeField";
        v32[14] = L"jsonEnvelopeDeviceLinkInfoCreationTimeFieldName";
        v32[15] = a1 + 384;
        v32[16] = L"dataField";
        v32[17] = L"jsonEnvelopeDataFieldName";
        v32[18] = a4;
        std::wstring::wstring(v36, L"1.0");
        v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
        std::wstring::wstring(&hstringHeader, L"jsonEnvelopeVersionFieldName");
        v15 = std::unordered_map<std::wstring,std::wstring>::at(a3, &hstringHeader);
        v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        v17 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v34, v16, v14);
        std::wstring::_Tidy_deallocate(&hstringHeader);
        if ( v17 >= 0 )
        {
          for ( i = 0; (unsigned __int64)i < 7; ++i )
          {
            v19 = 1;
            if ( *a2 != a2[1] )
            {
              std::wstring::wstring(&hstringHeader, (&v30)[3 * i]);
              v9 |= 1u;
              if ( !(unsigned __int8)ModernDeployment::Autopilot::Core::DeviceLinkEncoding::IsStringInVector(
                                       &hstringHeader,
                                       a2) )
                v19 = 0;
            }
            if ( (v9 & 1) != 0 )
            {
              v9 &= ~1u;
              std::wstring::_Tidy_deallocate(&hstringHeader);
            }
            if ( v19 )
            {
              v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32[3 * i]);
              std::wstring::wstring(&hstringHeader, v32[3 * i - 1]);
              v21 = std::unordered_map<std::wstring,std::wstring>::at(a3, &hstringHeader);
              v22 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
              v23 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v34, v22, v20);
              std::wstring::_Tidy_deallocate(&hstringHeader);
              if ( v23 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2FE,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                  (const char *)(unsigned int)v23,
                  (int)hstringHeader.Reserved.Reserved1);
                std::wstring::_Tidy_deallocate(v36);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
                std::vector<std::wstring>::_Tidy(a2);
                return (unsigned int)v23;
              }
            }
          }
          string = 0;
          v24 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v34, &string);
          v25 = v24;
          if ( v24 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v27 = std::wstring::wstring(&hstringHeader, StringRawBuffer);
            std::wstring::operator=(a5, v27);
            std::wstring::_Tidy_deallocate(&hstringHeader);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            std::wstring::_Tidy_deallocate(v36);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            std::vector<std::wstring>::_Tidy(a2);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x303,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
              (const char *)(unsigned int)v24,
              (int)hstringHeader.Reserved.Reserved1);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            std::wstring::_Tidy_deallocate(v36);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            std::vector<std::wstring>::_Tidy(a2);
            result = v25;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F6,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
            (const char *)(unsigned int)v17,
            (int)hstringHeader.Reserved.Reserved1);
          std::wstring::_Tidy_deallocate(v36);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          std::vector<std::wstring>::_Tidy(a2);
          result = (unsigned int)v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
          (const char *)(unsigned int)v10,
          (int)hstringHeader.Reserved.Reserved1);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        std::vector<std::wstring>::_Tidy(a2);
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
        (const char *)0x80004001LL,
        (int)hstringHeader.Reserved.Reserved1);
      std::vector<std::wstring>::_Tidy(a2);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v34) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x309,
                     (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\devicelinkinfo.cpp",
                     v12);
    std::vector<std::wstring>::_Tidy(v33);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x180140dc4  mov     r11, rsp
0x180140dc7  push    rbx
0x180140dc8  push    rsi
0x180140dc9  push    rdi
0x180140dca  push    r12
0x180140dcc  push    r13
0x180140dce  push    r14
0x180140dd0  push    r15
0x180140dd2  sub     rsp, 130h
0x180140dd9  mov     rax, cs:__security_cookie
0x180140de0  xor     rax, rsp
0x180140de3  mov     [rsp+168h+var_40], rax
0x180140deb  mov     r15, r9
0x180140dee  mov     r12, r8
0x180140df1  mov     rbx, rdx
0x180140df4  mov     r14, rcx
0x180140df7  mov     [r11-78h], rdx
0x180140dfb  mov     r13, [rsp+168h+arg_20]
0x180140e03  xor     edi, edi
0x180140e05  mov     dword ptr [rsp+168h+var_70], edi
0x180140e0c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180140e13  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180140e18  test    al, al
0x180140e1a  jz      loc_180141252
0x180140e20  mov     [rsp+168h+var_70], rdi
0x180140e28  mov     [rsp+168h+var_130], rdi
0x180140e2d  lea     r9d, [rdi+1Ch]; unsigned int
0x180140e31  lea     r8d, [rdi+1Dh]; unsigned int
0x180140e35  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180140e3c  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180140e41  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140e46  lea     rdx, [rsp+168h+var_70]
0x180140e4e  mov     rcx, [rsp+168h+var_130]
0x180140e53  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180140e58  mov     esi, eax
0x180140e5a  test    eax, eax
0x180140e5c  jns     short loc_180140E98
0x180140e5e  mov     rcx, [rsp+168h]; this
0x180140e66  mov     r9d, eax; char *
0x180140e69  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180140e70  mov     edx, 2E0h; void *
0x180140e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140e7a  nop
0x180140e7b  lea     rcx, [rsp+168h+var_70]
0x180140e83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180140e88  nop
0x180140e89  mov     rcx, rbx
0x180140e8c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180140e91  mov     eax, esi
0x180140e93  jmp     loc_180141294
0x180140e98  lea     rax, aSerialfield; "serialField"
0x180140e9f  mov     [rsp+168h+var_128], rax
0x180140ea4  lea     rax, aJsonenvelopese; "jsonEnvelopeSerialNumberFieldName"
0x180140eab  mov     [rsp+168h+var_120], rax
0x180140eb0  lea     rax, [r14+78h]
0x180140eb4  mov     [rsp+168h+var_118], rax
0x180140eb9  lea     rax, aManufacturerfi; "manufacturerField"
0x180140ec0  mov     [rsp+168h+var_110], rax
0x180140ec5  lea     rax, aJsonenvelopema; "jsonEnvelopeManufacturerFieldName"
0x180140ecc  mov     [rsp+168h+var_108], rax
0x180140ed1  lea     rax, [r14+38h]
0x180140ed5  mov     [rsp+168h+var_100], rax
0x180140eda  lea     rax, aModelfield; "modelField"
0x180140ee1  mov     [rsp+168h+var_F8], rax
0x180140ee6  lea     rax, aJsonenvelopemo; "jsonEnvelopeModelFieldName"
0x180140eed  mov     [rsp+168h+var_F0], rax
0x180140ef2  lea     rax, [r14+58h]
0x180140ef6  mov     [rsp+168h+var_E8], rax
0x180140efe  lea     rax, aLinkidfield; "linkIdField"
0x180140f05  mov     [rsp+168h+var_E0], rax
0x180140f0d  lea     rax, aJsonenvelopeli; "jsonEnvelopeLinkIdFieldName"
0x180140f14  mov     [rsp+168h+var_D8], rax
0x180140f1c  lea     rax, [r14+0B8h]
0x180140f23  mov     [rsp+168h+var_D0], rax
0x180140f2b  lea     rax, aLinkidcreation; "linkIdCreationTimeField"
0x180140f32  mov     [rsp+168h+var_C8], rax
0x180140f3a  lea     rax, aJsonenvelopeli_0; "jsonEnvelopeLinkIdCreationTimeFieldName"
0x180140f41  mov     [rsp+168h+var_C0], rax
0x180140f49  lea     rax, [r14+0D8h]
0x180140f50  mov     [rsp+168h+var_B8], rax
0x180140f58  lea     rax, aLinkinfocreati; "linkInfoCreationTimeField"
0x180140f5f  mov     [rsp+168h+var_B0], rax
0x180140f67  lea     rax, aJsonenvelopede; "jsonEnvelopeDeviceLinkInfoCreationTimeF"...
0x180140f6e  mov     [rsp+168h+var_A8], rax
0x180140f76  lea     rax, [r14+180h]
0x180140f7d  mov     [rsp+168h+var_A0], rax
0x180140f85  lea     rax, aDatafield; "dataField"
0x180140f8c  mov     [rsp+168h+var_98], rax
0x180140f94  lea     rax, aJsonenvelopeda; "jsonEnvelopeDataFieldName"
0x180140f9b  mov     [rsp+168h+var_90], rax
0x180140fa3  mov     [rsp+168h+var_88], r15
0x180140fab  lea     rdx, a10_2; "1.0"
0x180140fb2  lea     rcx, [rsp+168h+var_60]
0x180140fba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180140fbf  nop
0x180140fc0  lea     rcx, [rsp+168h+var_60]
0x180140fc8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180140fcd  mov     rsi, rax
0x180140fd0  lea     rdx, aJsonenvelopeve; "jsonEnvelopeVersionFieldName"
0x180140fd7  lea     rcx, [rsp+168h+hstringHeader]
0x180140fdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180140fe1  nop
0x180140fe2  lea     rdx, [rsp+168h+hstringHeader]
0x180140fe7  mov     rcx, r12
0x180140fea  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x180140fef  mov     rcx, rax
0x180140ff2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180140ff7  mov     r8, rsi; unsigned __int16 *
0x180140ffa  mov     rdx, rax; unsigned __int16 *
0x180140ffd  mov     rcx, [rsp+168h+var_70]; struct Windows::Data::Json::IJsonObject *
0x180141005  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18014100a  mov     esi, eax
0x18014100c  lea     rcx, [rsp+168h+hstringHeader]
0x180141011  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141016  test    esi, esi
0x180141018  jns     short loc_180141062
0x18014101a  mov     rcx, [rsp+168h]; this
0x180141022  mov     r9d, esi; char *
0x180141025  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014102c  mov     edx, 2F6h; void *
0x180141031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141036  nop
0x180141037  lea     rcx, [rsp+168h+var_60]
0x18014103f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141044  nop
0x180141045  lea     rcx, [rsp+168h+var_70]
0x18014104d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141052  nop
0x180141053  mov     rcx, rbx
0x180141056  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014105b  mov     eax, esi
0x18014105d  jmp     loc_180141294
0x180141062  xor     esi, esi
0x180141064  movsxd  rax, esi
0x180141067  cmp     rax, 7
0x18014106b  jnb     loc_18014116C
0x180141071  lea     r14, [rax+rax*2]
0x180141075  mov     rax, [rbx+8]
0x180141079  cmp     [rbx], rax
0x18014107c  jz      short loc_1801410A6
0x18014107e  mov     rdx, [rsp+r14*8+168h+var_128]
0x180141083  lea     rcx, [rsp+168h+hstringHeader]
0x180141088  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18014108d  or      edi, 1
0x180141090  mov     rdx, rbx
0x180141093  lea     rcx, [rsp+168h+hstringHeader]
0x180141098  call    ?IsStringInVector@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::IsStringInVector(std::wstring const &,std::vector<std::wstring> const &)
0x18014109d  test    al, al
0x18014109f  jnz     short loc_1801410A6
0x1801410a1  xor     r15b, r15b
0x1801410a4  jmp     short loc_1801410A9
0x1801410a6  mov     r15b, 1
0x1801410a9  test    dil, 1
0x1801410ad  jz      short loc_1801410BC
0x1801410af  and     edi, 0FFFFFFFEh
0x1801410b2  lea     rcx, [rsp+168h+hstringHeader]
0x1801410b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801410bc  test    r15b, r15b
0x1801410bf  jz      loc_180141165
0x1801410c5  mov     rcx, [rsp+r14*8+168h+var_118]
0x1801410ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801410cf  mov     r15, rax
0x1801410d2  mov     rdx, [rsp+r14*8+168h+var_120]
0x1801410d7  lea     rcx, [rsp+168h+hstringHeader]
0x1801410dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801410e1  nop
0x1801410e2  lea     rdx, [rsp+168h+hstringHeader]
0x1801410e7  mov     rcx, r12
0x1801410ea  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x1801410ef  mov     rcx, rax
0x1801410f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801410f7  mov     r8, r15; unsigned __int16 *
0x1801410fa  mov     rdx, rax; unsigned __int16 *
0x1801410fd  mov     rcx, [rsp+168h+var_70]; struct Windows::Data::Json::IJsonObject *
0x180141105  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18014110a  mov     r14d, eax
0x18014110d  lea     rcx, [rsp+168h+hstringHeader]
0x180141112  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141117  test    r14d, r14d
0x18014111a  jns     short loc_180141165
0x18014111c  mov     rcx, [rsp+168h]; this
0x180141124  mov     r9d, r14d; char *
0x180141127  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014112e  mov     edx, 2FEh; void *
0x180141133  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141138  nop
0x180141139  lea     rcx, [rsp+168h+var_60]
0x180141141  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141146  nop
0x180141147  lea     rcx, [rsp+168h+var_70]
0x18014114f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141154  nop
0x180141155  mov     rcx, rbx
0x180141158  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014115d  mov     eax, r14d
0x180141160  jmp     loc_180141294
0x180141165  inc     esi
0x180141167  jmp     loc_180141064
0x18014116c  mov     [rsp+168h+string], 0
0x180141178  lea     rdx, [rsp+168h+string]
0x180141180  mov     rcx, [rsp+168h+var_70]
0x180141188  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18014118d  mov     edi, eax
0x18014118f  test    eax, eax
0x180141191  jns     short loc_1801411E9
0x180141193  mov     rcx, [rsp+168h]; this
0x18014119b  mov     r9d, eax; char *
0x18014119e  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801411a5  mov     edx, 303h; void *
0x1801411aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801411af  nop
0x1801411b0  lea     rcx, [rsp+168h+string]; this
0x1801411b8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801411bd  nop
0x1801411be  lea     rcx, [rsp+168h+var_60]
0x1801411c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801411cb  nop
0x1801411cc  lea     rcx, [rsp+168h+var_70]
0x1801411d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801411d9  nop
0x1801411da  mov     rcx, rbx
0x1801411dd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801411e2  mov     eax, edi
0x1801411e4  jmp     loc_180141294
0x1801411e9  xor     edx, edx; length
0x1801411eb  mov     rcx, [rsp+168h+string]; string
0x1801411f3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801411f9  mov     rdx, rax
0x1801411fc  lea     rcx, [rsp+168h+hstringHeader]
0x180141201  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180141206  mov     rdx, rax
0x180141209  mov     rcx, r13
0x18014120c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180141211  lea     rcx, [rsp+168h+hstringHeader]
0x180141216  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014121b  nop
0x18014121c  lea     rcx, [rsp+168h+string]; this
0x180141224  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180141229  nop
0x18014122a  lea     rcx, [rsp+168h+var_60]
0x180141232  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141237  nop
0x180141238  lea     rcx, [rsp+168h+var_70]
0x180141240  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180141245  nop
0x180141246  mov     rcx, rbx
0x180141249  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014124e  xor     eax, eax
0x180141250  jmp     short loc_180141294
0x180141252  mov     rcx, [rsp+168h]; this
0x18014125a  mov     edi, 80004001h
0x18014125f  mov     r9d, edi; char *
0x180141262  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180141269  mov     edx, 2DBh; void *
0x18014126e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141273  nop
0x180141274  mov     rcx, rbx
0x180141277  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014127c  mov     eax, edi
0x18014127e  jmp     short loc_180141294
0x180141280  mov     rcx, [rsp+168h+var_78]
0x180141288  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014128d  mov     eax, dword ptr [rsp+168h+var_70]
0x180141294  mov     rcx, [rsp+168h+var_40]
0x18014129c  xor     rcx, rsp; StackCookie
0x18014129f  call    __security_check_cookie
0x1801412a4  add     rsp, 130h
0x1801412ab  pop     r15
0x1801412ad  pop     r14
0x1801412af  pop     r13
0x1801412b1  pop     r12
0x1801412b3  pop     rdi
0x1801412b4  pop     rsi
0x1801412b5  pop     rbx
0x1801412b6  retn
```
