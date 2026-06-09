# ModernDeployment::Autopilot::Core::DeviceLinkInfo::PopulateJsonEnvelope(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180144ec0`
- end: `0x1801453ba`
- name: `?PopulateJsonEnvelope@DeviceLinkInfo@Core@Autopilot@ModernDeployment@@QEBAJV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@AEAV86@@Z`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801410c0`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180084574`
- `0x180086044`
- `0x18008a9c4`
- `0x18008aecc`
- `0x18008af70`
- `0x18008f570`
- `0x1800901c0`
- `0x1800964d4`
- `0x1801383d0`
- `0x180141e48`
- `0x180144ec0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801452ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801452ef`

## string_xrefs

- `0x180144f31`: `Windows.Data.Json.JsonObject`
- `0x180145027`: `linkIdCreationTimeField`
- `0x180145054`: `linkInfoCreationTimeField`
- `0x180144ffa`: `linkIdField`
- `0x1801450cc`: `jsonEnvelopeVersionFieldName`
- `0x180145090`: `jsonEnvelopeDataFieldName`
- `0x180145036`: `jsonEnvelopeLinkIdCreationTimeFieldName`
- `0x180145063`: `jsonEnvelopeDeviceLinkInfoCreationTimeFieldName`
- `0x180144fe2`: `jsonEnvelopeModelFieldName`
- `0x180145009`: `jsonEnvelopeLinkIdFieldName`
- `0x180144fa0`: `jsonEnvelopeSerialNumberFieldName`
- `0x180144fc1`: `jsonEnvelopeManufacturerFieldName`
- `0x180144f65`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145121`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145223`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x18014529a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`
- `0x180145364`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\devicelinkinfo.cpp`

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
0x180144ec0  mov     r11, rsp
0x180144ec3  push    rbx
0x180144ec4  push    rsi
0x180144ec5  push    rdi
0x180144ec6  push    r12
0x180144ec8  push    r13
0x180144eca  push    r14
0x180144ecc  push    r15
0x180144ece  sub     rsp, 130h
0x180144ed5  mov     rax, cs:__security_cookie
0x180144edc  xor     rax, rsp
0x180144edf  mov     [rsp+168h+var_40], rax
0x180144ee7  mov     r15, r9
0x180144eea  mov     r12, r8
0x180144eed  mov     rbx, rdx
0x180144ef0  mov     r14, rcx
0x180144ef3  mov     [r11-78h], rdx
0x180144ef7  mov     r13, [rsp+168h+arg_20]
0x180144eff  xor     edi, edi
0x180144f01  mov     dword ptr [rsp+168h+var_70], edi
0x180144f08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180144f0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180144f14  test    al, al
0x180144f16  jz      loc_180145354
0x180144f1c  mov     [rsp+168h+var_70], rdi
0x180144f24  mov     [rsp+168h+var_130], rdi
0x180144f29  lea     r9d, [rdi+1Ch]; unsigned int
0x180144f2d  lea     r8d, [rdi+1Dh]; unsigned int
0x180144f31  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180144f38  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x180144f3d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180144f42  lea     rdx, [rsp+168h+var_70]
0x180144f4a  mov     rcx, [rsp+168h+var_130]
0x180144f4f  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180144f54  mov     esi, eax
0x180144f56  test    eax, eax
0x180144f58  jns     short loc_180144F94
0x180144f5a  mov     rcx, [rsp+168h]; this
0x180144f62  mov     r9d, eax; char *
0x180144f65  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180144f6c  mov     edx, 2E0h; void *
0x180144f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144f76  nop
0x180144f77  lea     rcx, [rsp+168h+var_70]
0x180144f7f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180144f84  nop
0x180144f85  mov     rcx, rbx
0x180144f88  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180144f8d  mov     eax, esi
0x180144f8f  jmp     loc_180145396
0x180144f94  lea     rax, aSerialfield; "serialField"
0x180144f9b  mov     [rsp+168h+var_128], rax
0x180144fa0  lea     rax, aJsonenvelopese; "jsonEnvelopeSerialNumberFieldName"
0x180144fa7  mov     [rsp+168h+var_120], rax
0x180144fac  lea     rax, [r14+78h]
0x180144fb0  mov     [rsp+168h+var_118], rax
0x180144fb5  lea     rax, aManufacturerfi; "manufacturerField"
0x180144fbc  mov     [rsp+168h+var_110], rax
0x180144fc1  lea     rax, aJsonenvelopema; "jsonEnvelopeManufacturerFieldName"
0x180144fc8  mov     [rsp+168h+var_108], rax
0x180144fcd  lea     rax, [r14+38h]
0x180144fd1  mov     [rsp+168h+var_100], rax
0x180144fd6  lea     rax, aModelfield; "modelField"
0x180144fdd  mov     [rsp+168h+var_F8], rax
0x180144fe2  lea     rax, aJsonenvelopemo; "jsonEnvelopeModelFieldName"
0x180144fe9  mov     [rsp+168h+var_F0], rax
0x180144fee  lea     rax, [r14+58h]
0x180144ff2  mov     [rsp+168h+var_E8], rax
0x180144ffa  lea     rax, aLinkidfield; "linkIdField"
0x180145001  mov     [rsp+168h+var_E0], rax
0x180145009  lea     rax, aJsonenvelopeli; "jsonEnvelopeLinkIdFieldName"
0x180145010  mov     [rsp+168h+var_D8], rax
0x180145018  lea     rax, [r14+0B8h]
0x18014501f  mov     [rsp+168h+var_D0], rax
0x180145027  lea     rax, aLinkidcreation; "linkIdCreationTimeField"
0x18014502e  mov     [rsp+168h+var_C8], rax
0x180145036  lea     rax, aJsonenvelopeli_0; "jsonEnvelopeLinkIdCreationTimeFieldName"
0x18014503d  mov     [rsp+168h+var_C0], rax
0x180145045  lea     rax, [r14+0D8h]
0x18014504c  mov     [rsp+168h+var_B8], rax
0x180145054  lea     rax, aLinkinfocreati; "linkInfoCreationTimeField"
0x18014505b  mov     [rsp+168h+var_B0], rax
0x180145063  lea     rax, aJsonenvelopede; "jsonEnvelopeDeviceLinkInfoCreationTimeF"...
0x18014506a  mov     [rsp+168h+var_A8], rax
0x180145072  lea     rax, [r14+180h]
0x180145079  mov     [rsp+168h+var_A0], rax
0x180145081  lea     rax, aDatafield; "dataField"
0x180145088  mov     [rsp+168h+var_98], rax
0x180145090  lea     rax, aJsonenvelopeda; "jsonEnvelopeDataFieldName"
0x180145097  mov     [rsp+168h+var_90], rax
0x18014509f  mov     [rsp+168h+var_88], r15
0x1801450a7  lea     rdx, a10_2; "1.0"
0x1801450ae  lea     rcx, [rsp+168h+var_60]
0x1801450b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801450bb  nop
0x1801450bc  lea     rcx, [rsp+168h+var_60]
0x1801450c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801450c9  mov     rsi, rax
0x1801450cc  lea     rdx, aJsonenvelopeve; "jsonEnvelopeVersionFieldName"
0x1801450d3  lea     rcx, [rsp+168h+hstringHeader]
0x1801450d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801450dd  nop
0x1801450de  lea     rdx, [rsp+168h+hstringHeader]
0x1801450e3  mov     rcx, r12
0x1801450e6  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x1801450eb  mov     rcx, rax
0x1801450ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801450f3  mov     r8, rsi; unsigned __int16 *
0x1801450f6  mov     rdx, rax; unsigned __int16 *
0x1801450f9  mov     rcx, [rsp+168h+var_70]; struct Windows::Data::Json::IJsonObject *
0x180145101  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180145106  mov     esi, eax
0x180145108  lea     rcx, [rsp+168h+hstringHeader]
0x18014510d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145112  test    esi, esi
0x180145114  jns     short loc_18014515E
0x180145116  mov     rcx, [rsp+168h]; this
0x18014511e  mov     r9d, esi; char *
0x180145121  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x180145128  mov     edx, 2F6h; void *
0x18014512d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145132  nop
0x180145133  lea     rcx, [rsp+168h+var_60]
0x18014513b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145140  nop
0x180145141  lea     rcx, [rsp+168h+var_70]
0x180145149  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014514e  nop
0x18014514f  mov     rcx, rbx
0x180145152  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180145157  mov     eax, esi
0x180145159  jmp     loc_180145396
0x18014515e  xor     esi, esi
0x180145160  movsxd  rax, esi
0x180145163  cmp     rax, 7
0x180145167  jnb     loc_180145268
0x18014516d  lea     r14, [rax+rax*2]
0x180145171  mov     rax, [rbx+8]
0x180145175  cmp     [rbx], rax
0x180145178  jz      short loc_1801451A2
0x18014517a  mov     rdx, [rsp+r14*8+168h+var_128]
0x18014517f  lea     rcx, [rsp+168h+hstringHeader]
0x180145184  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180145189  or      edi, 1
0x18014518c  mov     rdx, rbx
0x18014518f  lea     rcx, [rsp+168h+hstringHeader]
0x180145194  call    ?IsStringInVector@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::IsStringInVector(std::wstring const &,std::vector<std::wstring> const &)
0x180145199  test    al, al
0x18014519b  jnz     short loc_1801451A2
0x18014519d  xor     r15b, r15b
0x1801451a0  jmp     short loc_1801451A5
0x1801451a2  mov     r15b, 1
0x1801451a5  test    dil, 1
0x1801451a9  jz      short loc_1801451B8
0x1801451ab  and     edi, 0FFFFFFFEh
0x1801451ae  lea     rcx, [rsp+168h+hstringHeader]
0x1801451b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801451b8  test    r15b, r15b
0x1801451bb  jz      loc_180145261
0x1801451c1  mov     rcx, [rsp+r14*8+168h+var_118]
0x1801451c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801451cb  mov     r15, rax
0x1801451ce  mov     rdx, [rsp+r14*8+168h+var_120]
0x1801451d3  lea     rcx, [rsp+168h+hstringHeader]
0x1801451d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801451dd  nop
0x1801451de  lea     rdx, [rsp+168h+hstringHeader]
0x1801451e3  mov     rcx, r12
0x1801451e6  call    ?at@?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV32@@Z; std::unordered_map<std::wstring,std::wstring>::at(std::wstring const &)
0x1801451eb  mov     rcx, rax
0x1801451ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801451f3  mov     r8, r15; unsigned __int16 *
0x1801451f6  mov     rdx, rax; unsigned __int16 *
0x1801451f9  mov     rcx, [rsp+168h+var_70]; struct Windows::Data::Json::IJsonObject *
0x180145201  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180145206  mov     r14d, eax
0x180145209  lea     rcx, [rsp+168h+hstringHeader]
0x18014520e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145213  test    r14d, r14d
0x180145216  jns     short loc_180145261
0x180145218  mov     rcx, [rsp+168h]; this
0x180145220  mov     r9d, r14d; char *
0x180145223  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014522a  mov     edx, 2FEh; void *
0x18014522f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145234  nop
0x180145235  lea     rcx, [rsp+168h+var_60]
0x18014523d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145242  nop
0x180145243  lea     rcx, [rsp+168h+var_70]
0x18014524b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145250  nop
0x180145251  mov     rcx, rbx
0x180145254  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180145259  mov     eax, r14d
0x18014525c  jmp     loc_180145396
0x180145261  inc     esi
0x180145263  jmp     loc_180145160
0x180145268  mov     [rsp+168h+string], 0
0x180145274  lea     rdx, [rsp+168h+string]
0x18014527c  mov     rcx, [rsp+168h+var_70]
0x180145284  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180145289  mov     edi, eax
0x18014528b  test    eax, eax
0x18014528d  jns     short loc_1801452E5
0x18014528f  mov     rcx, [rsp+168h]; this
0x180145297  mov     r9d, eax; char *
0x18014529a  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801452a1  mov     edx, 303h; void *
0x1801452a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801452ab  nop
0x1801452ac  lea     rcx, [rsp+168h+string]; this
0x1801452b4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801452b9  nop
0x1801452ba  lea     rcx, [rsp+168h+var_60]
0x1801452c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801452c7  nop
0x1801452c8  lea     rcx, [rsp+168h+var_70]
0x1801452d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801452d5  nop
0x1801452d6  mov     rcx, rbx
0x1801452d9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801452de  mov     eax, edi
0x1801452e0  jmp     loc_180145396
0x1801452e5  xor     edx, edx; length
0x1801452e7  mov     rcx, [rsp+168h+string]; string
0x1801452ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1801452f6  nop     dword ptr [rax+rax+00h]
0x1801452fb  mov     rdx, rax
0x1801452fe  lea     rcx, [rsp+168h+hstringHeader]
0x180145303  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180145308  mov     rdx, rax
0x18014530b  mov     rcx, r13
0x18014530e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180145313  lea     rcx, [rsp+168h+hstringHeader]
0x180145318  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014531d  nop
0x18014531e  lea     rcx, [rsp+168h+string]; this
0x180145326  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18014532b  nop
0x18014532c  lea     rcx, [rsp+168h+var_60]
0x180145334  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180145339  nop
0x18014533a  lea     rcx, [rsp+168h+var_70]
0x180145342  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180145347  nop
0x180145348  mov     rcx, rbx
0x18014534b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180145350  xor     eax, eax
0x180145352  jmp     short loc_180145396
0x180145354  mov     rcx, [rsp+168h]; this
0x18014535c  mov     edi, 80004001h
0x180145361  mov     r9d, edi; char *
0x180145364  lea     r8, aOnecoreuapAdmi_77; "onecoreuap\\admin\\moderndeployment\\au"...
0x18014536b  mov     edx, 2DBh; void *
0x180145370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145375  nop
0x180145376  mov     rcx, rbx
0x180145379  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014537e  mov     eax, edi
0x180145380  jmp     short loc_180145396
0x180145382  mov     rcx, [rsp+168h+var_78]
0x18014538a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014538f  mov     eax, dword ptr [rsp+168h+var_70]
0x180145396  mov     rcx, [rsp+168h+var_40]
0x18014539e  xor     rcx, rsp; StackCookie
0x1801453a1  call    __security_check_cookie
0x1801453a6  add     rsp, 130h
0x1801453ad  pop     r15
0x1801453af  pop     r14
0x1801453b1  pop     r13
0x1801453b3  pop     r12
0x1801453b5  pop     rdi
0x1801453b6  pop     rsi
0x1801453b7  pop     rbx
0x1801453b8  retn
```
