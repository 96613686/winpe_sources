# OSIntegration::DEH::Internal::RegistryCompatKeysHelper::Parse(void)

- ea: `0x180064ae0`
- end: `0x1800659c4`
- name: `?Parse@RegistryCompatKeysHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `3812`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::RegistryCompatKeysHelper *__hidden this)`
- caller_count: `0`
- callee_count: `56`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180012fc8`
- `0x180030848`
- `0x18003157c`
- `0x180032478`
- `0x18004eac0`
- `0x180056bd4`
- `0x180059424`
- `0x1800607dc`
- `0x180060800`
- `0x180061b58`
- `0x180064158`
- `0x180064900`
- `0x180064a88`
- `0x180064ae0`
- `0x180066780`
- `0x180066938`
- `0x180066988`
- `0x1800669b0`
- `0x180066a2c`
- `0x180066cc8`
- `0x180071178`
- `0x180072dcc`
- `0x180073fc4`
- `0x180074504`
- `0x180078760`
- `0x180081e00`
- `0x180081eb4`
- `0x1800842e8`
- `0x180084ed0`
- `0x180088c60`
- `0x18008903c`
- `0x18008c860`
- `0x18008c93c`
- `0x18008f988`
- `0x1800982a8`
- `0x18009d504`
- `0x18009d978`
- `0x18009fd38`
- `0x1800aed10`
- `0x1800af918`
- `0x1800dab58`
- `0x1800db594`
- `0x1800ef2ec`
- `0x180100cb0`
- `0x180100cfc`
- `0x180100d54`
- `0x180100d7c`
- `0x180100da4`
- `0x180100dcc`
- `0x180100e48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180065140`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180065140`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18006558a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18006558a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065223`
- `ext-ms-win-desktopappx-l1-1-7!GetRegistryPathDetokenizer` at `0x180064c79`
- `ext-ms-win-desktopappx-l1-1-7!GetRegistryPathDetokenizer` at `0x180064c79`

## string_xrefs

- `0x180064cd0`: `*[local-name()='ClassicAppCompatKey']`
- `0x180064bd2`: `*[local-name()='ClassicAppCompatKeys']`
- `0x180064c94`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x180064eaf`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x180064fea`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x1800652be`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x180065487`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x1800655ab`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x1800655e3`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x1800656f5`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x18006575c`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x18006577c`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`
- `0x18006581e`: `onecore\admin\appmodel\osim\src\deh\appx\registrycompatkeys\registrycompatkeyshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::Internal::RegistryCompatKeysHelper::Parse(
        OSIntegration::DEH::Internal::RegistryCompatKeysHelper *this)
{
  __int64 v3; // rbx
  int ScopeFromExtensionScopeString; // esi
  unsigned __int16 *PackageRoot; // rax
  int RegistryPathDetokenizer; // eax
  unsigned __int128 v7; // kr10_16
  __int64 v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  _BYTE *v13; // rax
  void *v14; // rax
  _QWORD *v15; // rcx
  _QWORD *v16; // rdi
  __int64 v17; // rsi
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rdi
  __int64 v23; // rsi
  _QWORD *v24; // rax
  int v25; // eax
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  wchar_t *j; // rcx
  wchar_t *v29; // rax
  _QWORD *v30; // rcx
  wchar_t *v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rcx
  wchar_t *v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rcx
  unsigned __int64 v37; // r12
  unsigned __int64 v38; // rsi
  _QWORD *v39; // rax
  _QWORD *v40; // r15
  unsigned __int64 v41; // rsi
  char *v42; // r14
  signed __int64 v43; // rcx
  char *v44; // rax
  unsigned __int64 v45; // rdi
  unsigned __int64 v46; // rcx
  unsigned __int64 k; // rdi
  unsigned __int64 v48; // r14
  unsigned int v49; // edx
  __int64 v51; // rax
  __int64 v52; // rax
  unsigned int ScopeFromRegistryPathString; // edi
  __int64 v54; // rdx
  __int64 (__fastcall *v55)(__int64, _QWORD, void ***, _BYTE *); // rsi
  _QWORD *v56; // rcx
  int v57; // eax
  unsigned int v58; // [rsp+20h] [rbp-2B8h]
  int v59[2]; // [rsp+20h] [rbp-2B8h]
  int v60; // [rsp+30h] [rbp-2A8h]
  _QWORD *v61; // [rsp+38h] [rbp-2A0h] BYREF
  void *v62; // [rsp+40h] [rbp-298h] BYREF
  void *v63; // [rsp+48h] [rbp-290h]
  HSTRING string; // [rsp+50h] [rbp-288h] BYREF
  _QWORD *v65; // [rsp+58h] [rbp-280h] BYREF
  _QWORD *v66; // [rsp+60h] [rbp-278h] BYREF
  unsigned __int128 v67; // [rsp+68h] [rbp-270h] BYREF
  __int64 v68; // [rsp+78h] [rbp-260h]
  wchar_t *Context; // [rsp+80h] [rbp-258h] BYREF
  wchar_t *String; // [rsp+88h] [rbp-250h] BYREF
  __int64 v71; // [rsp+90h] [rbp-248h]
  __int64 v72; // [rsp+98h] [rbp-240h] BYREF
  _BYTE v73[40]; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE v74[56]; // [rsp+C8h] [rbp-210h] BYREF
  _QWORD *v75; // [rsp+100h] [rbp-1D8h] BYREF
  _QWORD *v76; // [rsp+108h] [rbp-1D0h]
  __int64 v77; // [rsp+110h] [rbp-1C8h]
  _QWORD *i; // [rsp+118h] [rbp-1C0h]
  unsigned __int64 v79; // [rsp+120h] [rbp-1B8h]
  _BYTE v80[48]; // [rsp+128h] [rbp-1B0h] BYREF
  _BYTE v81[40]; // [rsp+158h] [rbp-180h] BYREF
  _BYTE v82[40]; // [rsp+180h] [rbp-158h] BYREF
  _BYTE v83[40]; // [rsp+1A8h] [rbp-130h] BYREF
  _QWORD v84[2]; // [rsp+1D0h] [rbp-108h] BYREF
  __int64 v85; // [rsp+1E0h] [rbp-F8h]
  unsigned __int64 v86; // [rsp+1E8h] [rbp-F0h]
  void **v87; // [rsp+1F0h] [rbp-E8h] BYREF
  int v88; // [rsp+1F8h] [rbp-E0h]
  __int64 v89; // [rsp+200h] [rbp-D8h] BYREF
  void **v90; // [rsp+210h] [rbp-C8h] BYREF
  int v91; // [rsp+218h] [rbp-C0h]
  _BYTE v92[32]; // [rsp+220h] [rbp-B8h] BYREF
  _BYTE v93[32]; // [rsp+240h] [rbp-98h] BYREF
  _QWORD v94[4]; // [rsp+260h] [rbp-78h] BYREF
  _BYTE v95[32]; // [rsp+280h] [rbp-58h] BYREF
  wchar_t v96[2]; // [rsp+2A0h] [rbp-38h] BYREF
  __int16 v97; // [rsp+2A4h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( !*(_BYTE *)(*((_QWORD *)this + 3) + 368LL) )
    return 0;
  v3 = *((_QWORD *)this + 2);
  OSIntegration::Tools::TryParseAttribute<std::wstring>(v82, v3, &stru_1801CFB48);
  OSIntegration::Tools::TryParseAttribute<std::wstring>(v81, v3, &stru_1801CFB60);
  if ( !v82[32] || (unsigned __int8)std::operator!=<unsigned short>(v82, L"classic") )
  {
    std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v81);
    std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v82);
    return 0;
  }
  if ( v81[32] )
    std::wstring::wstring(v94, v81);
  else
    std::wstring::wstring(v94, L"user");
  ScopeFromExtensionScopeString = OSIntegration::DEH::Internal::GetScopeFromExtensionScopeString(v94);
  v60 = ScopeFromExtensionScopeString;
  std::wstring::_Tidy_deallocate(v94);
  OSIntegration::Tools::QueryForElements(&v67, v3, L"*[local-name()='ClassicAppCompatKeys']");
  if ( *((_QWORD *)&v67 + 1) == (_QWORD)v67 )
  {
    if ( (_QWORD)v67 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>>>(
        v67,
        *((_QWORD *)&v67 + 1));
      std::_Deallocate<16>(v67, (v68 - v67) & 0xFFFFFFFFFFFFFFF8uLL);
      v67 = 0;
      v68 = 0;
    }
    std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v81);
    std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v82);
    return 0;
  }
  wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(
    &v72,
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 808LL) + 72LL));
  v65 = 0;
  PackageRoot = OSIntegration::Package::GetPackageRoot(*((OSIntegration::Package **)this + 3));
  RegistryPathDetokenizer = GetRegistryPathDetokenizer(PackageRoot, &v65);
  if ( RegistryPathDetokenizer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
      (const char *)(unsigned int)RegistryPathDetokenizer,
      v58);
  v7 = v67;
  v79 = *((_QWORD *)&v67 + 1);
  v8 = v72;
LABEL_15:
  v71 = v7;
  if ( (_QWORD)v7 != *((_QWORD *)&v7 + 1) )
  {
    OSIntegration::Tools::QueryForElements(&v75, *(_QWORD *)v7, L"*[local-name()='ClassicAppCompatKey']");
    v9 = v75;
    v10 = v75;
    v11 = v76;
    v12 = v76;
    for ( i = v76; ; v12 = i )
    {
      v61 = v10;
      if ( v10 == v12 )
      {
        if ( v9 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>>>(v9, v11);
          std::_Deallocate<16>(v75, (v77 - (_QWORD)v75) & 0xFFFFFFFFFFFFFFF8uLL);
        }
        v7 = __PAIR128__(v79, v71 + 8);
        goto LABEL_15;
      }
      OSIntegration::Tools::TryParseAttribute<std::wstring>(v83, *v10, L"Name");
      v13 = (_BYTE *)OSIntegration::Tools::TryParseAttribute<std::wstring>(&v90, *v10, L"ValueName");
      if ( v13[32] )
        std::wstring::wstring(v93, v13);
      else
        std::wstring::wstring(v93, &Value);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(&v90);
      OSIntegration::Tools::TryParseAttribute<std::wstring>(v73, *v10, L"Value");
      v14 = (void *)OSIntegration::Tools::TryParseAttribute<std::wstring>(&v90, *v10, L"ValueType");
      std::optional<std::wstring>::value_or<unsigned short const (&)[7]>(v14, v84);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(&v90);
      if ( !v83[32] )
      {
        std::wstring::_Tidy_deallocate(v84);
        std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v73);
        std::wstring::_Tidy_deallocate(v93);
        goto LABEL_101;
      }
      OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v80);
      if ( v73[32] )
      {
        v15 = v84;
        if ( v86 > 7 )
          v15 = (_QWORD *)v84[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v15, v85, L"REG_SZ", 6) )
        {
          v61 = 0;
          v16 = v65;
          v17 = *v65;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v61,
            0);
          v18 = (_QWORD *)std::optional<std::wstring>::value(v73);
          if ( v18[3] > 7u )
            v18 = (_QWORD *)*v18;
          v19 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, _QWORD **))(v17 + 24))(v16, v18, &v61);
          if ( v19 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD1,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
              (const char *)(unsigned int)v19,
              v58);
          v66 = v61;
          v20 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                  &v90,
                  &v66);
          OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(v74, v20);
          OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v87, v93);
          OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v87, v74);
          std::wstring::_Tidy_deallocate(&v87);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
          std::wstring::_Tidy_deallocate(v92);
          goto LABEL_32;
        }
        v21 = v84;
        if ( v86 > 7 )
          v21 = (_QWORD *)v84[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v21, v85, L"REG_EXPAND_SZ", 13) )
        {
          v61 = 0;
          v22 = v65;
          v23 = *v65;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v61,
            0);
          v24 = (_QWORD *)std::optional<std::wstring>::value(v73);
          if ( v24[3] > 7u )
            v24 = (_QWORD *)*v24;
          v25 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, _QWORD **))(v23 + 24))(v22, v24, &v61);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD8,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
              (const char *)(unsigned int)v25,
              v58);
          v91 = 2;
          v90 = &OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::`vftable';
          std::wstring::wstring(v92, v61);
          OSIntegration::DEH::RegistryCompatibility::Details::GetStringByteCountIncludingTerminator<OSIntegration::DEH::RegistryCompatibility::Details::String>(v92);
          OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(v74, &v90);
          OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v87, v93);
          OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v87, v74);
          std::wstring::_Tidy_deallocate(&v87);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
          std::wstring::_Tidy_deallocate(v92);
LABEL_32:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
LABEL_90:
          ScopeFromExtensionScopeString = v60;
          goto LABEL_91;
        }
        v26 = v84;
        if ( v86 > 7 )
          v26 = (_QWORD *)v84[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v26, v85, L"REG_MULTI_SZ", 12) )
        {
          v27 = (_QWORD *)std::optional<std::wstring>::value(v73);
          if ( v27[3] > 7u )
            v27 = (_QWORD *)*v27;
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &String,
            v27);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(&v87);
          Context = 0;
          for ( j = String; ; j = 0 )
          {
            v29 = wcstok_s(j, L"[~]", &Context);
            if ( !v29 )
              break;
            std::wstring::wstring(&v90, v29);
            std::vector<std::wstring>::push_back(&v87, &v90);
            std::wstring::_Tidy_deallocate(&v90);
          }
          LODWORD(v63) = 7;
          v62 = &OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData::`vftable';
          OSIntegration::DEH::RegistryCompatibility::Details::MultiString::MultiString(&string);
          OSIntegration::DEH::RegistryCompatibility::Details::GetStringByteCountIncludingTerminator<OSIntegration::DEH::RegistryCompatibility::Details::MultiString>(&string);
          OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(
            (OSIntegration::DEH::RegistryCompatibility::AnyValueData *)v74,
            (struct OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData *)&v62);
          OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v90, v93);
          OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v90, v74);
          std::wstring::_Tidy_deallocate(&v90);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
          WindowsDeleteString(string);
          string = 0;
          std::vector<std::wstring>::_Tidy(&v87);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
          goto LABEL_91;
        }
        v30 = v84;
        if ( v86 > 7 )
          v30 = (_QWORD *)v84[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v30, v85, L"REG_DWORD", 9) )
        {
          v31 = (wchar_t *)std::optional<std::wstring>::value(v73);
          v32 = std::stoll(v31);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEE,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
              (const char *)0x8000000BLL,
              v58);
          v88 = 4;
          v87 = &OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>::`vftable';
          LODWORD(v89) = v32;
          OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(v74, &v87);
          OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v90, v93);
          OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v90, v74);
          std::wstring::_Tidy_deallocate(&v90);
        }
        else
        {
          v33 = v84;
          if ( v86 > 7 )
            v33 = (_QWORD *)v84[0];
          if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v33, v85, L"REG_QWORD", 9) )
          {
            v36 = v84;
            if ( v86 > 7 )
              v36 = (_QWORD *)v84[0];
            if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v36, v85, L"REG_BINARY", 10) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x117,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
                (const char *)0x65E,
                v58);
            if ( (*(_BYTE *)(std::optional<std::wstring>::value(v73) + 16) & 1) != 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xFE,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
                (const char *)0x80070057LL,
                v58);
            v37 = *(_QWORD *)(std::optional<std::wstring>::value(v73) + 16);
            v38 = *(_QWORD *)(std::optional<std::wstring>::value(v73) + 16);
            v39 = (_QWORD *)std::optional<std::wstring>::value(v73);
            v40 = v39;
            v41 = v38 >> 1;
            if ( v39[3] > 7u )
              v40 = (_QWORD *)*v39;
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> const,std::variant<OSIntegration::DEH::RegistryCompatibility::EntryTree,OSIntegration::DEH::RegistryCompatibility::Key>>>>>>>(&v62);
            v42 = (char *)v63;
            v43 = (_BYTE *)v63 - (_BYTE *)v62;
            if ( v41 < (_BYTE *)v63 - (_BYTE *)v62 )
            {
              v44 = (char *)v62 + v41;
              goto LABEL_74;
            }
            if ( v41 > (_BYTE *)v63 - (_BYTE *)v62 )
            {
              if ( v41 <= (char *)string - (_BYTE *)v62 )
              {
                v45 = v41 - v43;
                memset_0(v63, 0, v41 - v43);
                v44 = &v42[v45];
LABEL_74:
                v63 = v44;
              }
              else
              {
                std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v62, v41);
              }
            }
            *(_DWORD *)v96 = 0;
            v97 = 0;
            v46 = 0;
            for ( k = 0; v46 < v37 && k < v41; ++k )
            {
              v48 = v46 + 1;
              v96[0] = *((_WORD *)v40 + v46);
              v96[1] = *((_WORD *)v40 + v46 + 1);
              v49 = wcstoul(v96, 0, 16);
              if ( v49 == -1 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x10C,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
                  (const char *)0x8000000BLL,
                  v58);
              if ( !v49 && v96[1] != 48 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x110,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
                  (const char *)0x80070057LL,
                  v58);
              v46 = v48 + 1;
              *((_BYTE *)v62 + k) = v49;
            }
            v51 = OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::RegBinaryValueData(
                    (OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData *)&v87,
                    v41,
                    v62);
            OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(v74, v51);
            OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v90, v93);
            OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v90, v74);
            std::wstring::_Tidy_deallocate(&v90);
            std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
            wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(&v89);
            if ( v62 )
              std::_Deallocate<16>(v62, (char *)string - (_BYTE *)v62);
            v10 = v61;
            goto LABEL_90;
          }
          v34 = (wchar_t *)std::optional<std::wstring>::value(v73);
          v35 = std::stoull(v34);
          v88 = 11;
          v87 = &OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>::`vftable';
          v89 = v35;
          OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(v74, &v87);
          OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(&v90, v93);
          OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v80, &v90, v74);
          std::wstring::_Tidy_deallocate(&v90);
        }
        std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
      }
LABEL_91:
      v52 = std::optional<std::wstring>::value(v83);
      std::filesystem::path::path(v95, v52);
      ScopeFromRegistryPathString = OSIntegration::DEH::Internal::GetScopeFromRegistryPathString(v95);
      if ( ScopeFromRegistryPathString != ScopeFromExtensionScopeString )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
          (const char *)0x80070057LL,
          v58);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0dz_EventWriteTransfer(
            &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
            RegistryCompatKeysScopeMustMatch,
            2147942487LL,
            *(_QWORD *)(*((_QWORD *)this + 3) + 448LL));
        *(_QWORD *)v59 = *(_QWORD *)(*((_QWORD *)this + 3) + 448LL);
        details::appxLog<long,unsigned short const *>(2147942487LL, v54, RegistryCompatKeysScopeMustMatch, 2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x129,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
          (const char *)0x80070057LL,
          v59[0]);
      }
      std::wstring::wstring(&v90, v95);
      StripFirstComponentFromPath(v94);
      v55 = *(__int64 (__fastcall **)(__int64, _QWORD, void ***, _BYTE *))(*(_QWORD *)v8 + 48LL);
      v56 = v94;
      if ( v94[3] > 7u )
        v56 = (_QWORD *)v94[0];
      v66 = v56;
      OSIntegration::DEH::RegistryCompatibility::KeyPath::KeyPath(&v87, &v66);
      v57 = v55(v8, ScopeFromRegistryPathString, &v87, v80);
      if ( v57 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\registrycompatkeys\\registrycompatkeyshelper.cpp",
          (const char *)(unsigned int)v57,
          v58);
      std::wstring::_Tidy_deallocate(&v87);
      std::wstring::_Tidy_deallocate(v94);
      std::wstring::_Tidy_deallocate(v95);
      OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v80);
      std::wstring::_Tidy_deallocate(v84);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v73);
      std::wstring::_Tidy_deallocate(v93);
      ScopeFromExtensionScopeString = v60;
LABEL_101:
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v83);
      ++v10;
      v11 = v76;
      v9 = v75;
    }
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v65);
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v72);
  if ( (_QWORD)v67 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>>>(
      v67,
      *((_QWORD *)&v67 + 1));
    std::_Deallocate<16>(v67, (v68 - v67) & 0xFFFFFFFFFFFFFFF8uLL);
    v67 = 0;
    v68 = 0;
  }
  std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v81);
  std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v82);
  return 0;
}

```

## disassembly

```asm
0x180064ae0  mov     [rsp+arg_8], rbx
0x180064ae5  mov     [rsp+arg_10], rsi
0x180064aea  push    rdi
0x180064aeb  push    r12
0x180064aed  push    r13
0x180064aef  push    r14
0x180064af1  push    r15
0x180064af3  sub     rsp, 2B0h
0x180064afa  mov     rax, cs:__security_cookie
0x180064b01  xor     rax, rsp
0x180064b04  mov     [rsp+2D8h+var_30], rax
0x180064b0c  mov     r13, rcx
0x180064b0f  xor     r15d, r15d
0x180064b12  mov     rax, [rcx+18h]
0x180064b16  cmp     [rax+170h], r15b
0x180064b1d  jnz     short loc_180064B26
0x180064b1f  xor     eax, eax
0x180064b21  jmp     loc_180065996
0x180064b26  mov     rbx, [rcx+10h]
0x180064b2a  lea     r8, stru_1801CFB48
0x180064b31  mov     rdx, rbx
0x180064b34  lea     rcx, [rsp+2D8h+var_158]
0x180064b3c  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064b41  nop
0x180064b42  lea     r8, stru_1801CFB60
0x180064b49  mov     rdx, rbx
0x180064b4c  lea     rcx, [rsp+2D8h+var_180]
0x180064b54  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064b59  nop
0x180064b5a  cmp     [rsp+2D8h+var_138], r15b
0x180064b62  jz      loc_180065973
0x180064b68  lea     rdx, aClassic; "classic"
0x180064b6f  lea     rcx, [rsp+2D8h+var_158]
0x180064b77  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180064b7c  test    al, al
0x180064b7e  jnz     loc_180065973
0x180064b84  lea     rcx, [rsp+2D8h+var_78]
0x180064b8c  cmp     [rsp+2D8h+var_160], r15b
0x180064b94  jz      short loc_180064BA5
0x180064b96  lea     rdx, [rsp+2D8h+var_180]
0x180064b9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180064ba3  jmp     short loc_180064BB2
0x180064ba5  lea     rdx, aUser; "user"
0x180064bac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180064bb1  nop
0x180064bb2  lea     rcx, [rsp+2D8h+var_78]
0x180064bba  call    OSIntegration__DEH__Internal__GetScopeFromExtensionScopeString
0x180064bbf  mov     esi, eax
0x180064bc1  mov     [rsp+2D8h+var_2A8], eax
0x180064bc5  lea     rcx, [rsp+2D8h+var_78]
0x180064bcd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064bd2  lea     r8, aLocalNameClass_0; "*[local-name()='ClassicAppCompatKeys']"
0x180064bd9  mov     rdx, rbx
0x180064bdc  lea     rcx, [rsp+2D8h+var_270]
0x180064be1  call    ?QueryForElements@Tools@OSIntegration@@YA?AV?$vector@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::QueryForElements(IXMLDOMElement *,ushort const *)
0x180064be6  nop
0x180064be7  mov     rcx, qword ptr [rsp+2D8h+var_270]
0x180064bec  mov     rdx, qword ptr [rsp+2D8h+var_270+8]
0x180064bf1  cmp     rdx, rcx
0x180064bf4  jnz     short loc_180064C46
0x180064bf6  test    rcx, rcx
0x180064bf9  jz      short loc_180064C24
0x180064bfb  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>>>(wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy> *,wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>> &)
0x180064c00  mov     rcx, qword ptr [rsp+2D8h+var_270]
0x180064c05  mov     rdx, [rsp+2D8h+var_260]
0x180064c0a  sub     rdx, rcx
0x180064c0d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180064c11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180064c16  xorps   xmm0, xmm0
0x180064c19  movdqu  [rsp+2D8h+var_270], xmm0
0x180064c1f  mov     [rsp+2D8h+var_260], r15
0x180064c24  lea     rcx, [rsp+2D8h+var_180]
0x180064c2c  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x180064c31  nop
0x180064c32  lea     rcx, [rsp+2D8h+var_158]
0x180064c3a  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x180064c3f  xor     eax, eax
0x180064c41  jmp     loc_180065996
0x180064c46  mov     rax, [r13+18h]
0x180064c4a  mov     rdx, [rax+328h]
0x180064c51  mov     rdx, [rdx+48h]
0x180064c55  lea     rcx, [rsp+2D8h+var_240]
0x180064c5d  call    ??0?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIXMLDOMElement@@@Z; wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(IXMLDOMElement *)
0x180064c62  nop
0x180064c63  mov     [rsp+2D8h+var_280], r15
0x180064c68  mov     rcx, [r13+18h]; this
0x180064c6c  call    ?GetPackageRoot@Package@OSIntegration@@QEBAPEAGXZ; OSIntegration::Package::GetPackageRoot(void)
0x180064c71  lea     rdx, [rsp+2D8h+var_280]
0x180064c76  mov     rcx, rax
0x180064c79  call    cs:__imp_GetRegistryPathDetokenizer
0x180064c80  nop     dword ptr [rax+rax+00h]
0x180064c85  mov     rcx, [rsp+2D8h]; this
0x180064c8d  test    eax, eax
0x180064c8f  jns     short loc_180064CA5
0x180064c91  mov     r9d, eax; char *
0x180064c94  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180064c9b  mov     edx, 0B3h; void *
0x180064ca0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064ca5  mov     rdi, qword ptr [rsp+2D8h+var_270]
0x180064caa  mov     rax, qword ptr [rsp+2D8h+var_270+8]
0x180064caf  mov     [rsp+2D8h+var_1B8], rax
0x180064cb7  mov     rbx, [rsp+2D8h+var_240]
0x180064cbf  mov     [rsp+2D8h+var_248], rdi
0x180064cc7  cmp     rdi, rax
0x180064cca  jz      loc_180065903
0x180064cd0  lea     r8, aLocalNameClass; "*[local-name()='ClassicAppCompatKey']"
0x180064cd7  mov     rdx, [rdi]
0x180064cda  lea     rcx, [rsp+2D8h+var_1D8]
0x180064ce2  call    ?QueryForElements@Tools@OSIntegration@@YA?AV?$vector@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::QueryForElements(IXMLDOMElement *,ushort const *)
0x180064ce7  nop
0x180064ce8  mov     rcx, [rsp+2D8h+var_1D8]
0x180064cf0  mov     r14, rcx
0x180064cf3  mov     rdx, [rsp+2D8h+var_1D0]
0x180064cfb  mov     rax, rdx
0x180064cfe  mov     [rsp+2D8h+var_1C0], rdx
0x180064d06  mov     [rsp+2D8h+var_2A0], r14
0x180064d0b  cmp     r14, rax
0x180064d0e  jz      loc_1800658C4
0x180064d14  lea     r8, aName; "Name"
0x180064d1b  mov     rdx, [r14]
0x180064d1e  lea     rcx, [rsp+2D8h+var_130]
0x180064d26  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064d2b  nop
0x180064d2c  lea     r8, aValuename; "ValueName"
0x180064d33  mov     rdx, [r14]
0x180064d36  lea     rcx, [rsp+2D8h+var_C8]
0x180064d3e  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064d43  nop
0x180064d44  lea     rcx, [rsp+2D8h+var_98]; void *
0x180064d4c  cmp     [rax+20h], r15b
0x180064d50  jz      short loc_180064D5C
0x180064d52  mov     rdx, rax; void *
0x180064d55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180064d5a  jmp     short loc_180064D69
0x180064d5c  lea     rdx, Value
0x180064d63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180064d68  nop
0x180064d69  lea     rcx, [rsp+2D8h+var_C8]
0x180064d71  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x180064d76  lea     r8, aValue_0; "Value"
0x180064d7d  mov     rdx, [r14]
0x180064d80  lea     rcx, [rsp+2D8h+var_238]
0x180064d88  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064d8d  nop
0x180064d8e  lea     r8, aValuetype; "ValueType"
0x180064d95  mov     rdx, [r14]
0x180064d98  lea     rcx, [rsp+2D8h+var_C8]
0x180064da0  call    ??$TryParseAttribute@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Tools@OSIntegration@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUIXMLDOMElement@@PEBG@Z; OSIntegration::Tools::TryParseAttribute<std::wstring>(IXMLDOMElement *,ushort const *)
0x180064da5  nop
0x180064da6  lea     r8, aRegSz; "REG_SZ"
0x180064dad  lea     rdx, [rsp+2D8h+var_108]; void *
0x180064db5  mov     rcx, rax; void *
0x180064db8  call    ??$value_or@AEAY06$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEHAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY06$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[7]>(ushort const (&)[7])
0x180064dbd  nop
0x180064dbe  lea     rcx, [rsp+2D8h+var_C8]
0x180064dc6  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x180064dcb  cmp     [rsp+2D8h+var_110], r15b
0x180064dd3  jnz     short loc_180064E04
0x180064dd5  lea     rcx, [rsp+2D8h+var_108]
0x180064ddd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064de2  nop
0x180064de3  lea     rcx, [rsp+2D8h+var_238]
0x180064deb  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x180064df0  nop
0x180064df1  lea     rcx, [rsp+2D8h+var_98]
0x180064df9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064dfe  nop
0x180064dff  jmp     loc_180065896
0x180064e04  lea     rcx, [rsp+2D8h+var_1B0]; this
0x180064e0c  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x180064e11  nop
0x180064e12  cmp     [rsp+2D8h+var_218], r15b
0x180064e1a  jz      loc_1800656B0
0x180064e20  lea     rcx, [rsp+2D8h+var_108]
0x180064e28  cmp     [rsp+2D8h+var_F0], 7
0x180064e31  cmova   rcx, [rsp+2D8h+var_108]
0x180064e3a  mov     r9d, 6
0x180064e40  lea     r8, aRegSz; "REG_SZ"
0x180064e47  mov     rdx, [rsp+2D8h+var_F8]
0x180064e4f  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180064e54  test    al, al
0x180064e56  jz      loc_180064F5B
0x180064e5c  mov     [rsp+2D8h+var_2A0], r15
0x180064e61  mov     rdi, [rsp+2D8h+var_280]
0x180064e66  mov     rsi, [rdi]
0x180064e69  xor     edx, edx
0x180064e6b  lea     rcx, [rsp+2D8h+var_2A0]
0x180064e70  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180064e75  lea     rcx, [rsp+2D8h+var_238]
0x180064e7d  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180064e82  cmp     qword ptr [rax+18h], 7
0x180064e87  jbe     short loc_180064E8C
0x180064e89  mov     rax, [rax]
0x180064e8c  lea     r8, [rsp+2D8h+var_2A0]
0x180064e91  mov     rdx, rax
0x180064e94  mov     rcx, rdi
0x180064e97  mov     rax, [rsi+18h]
0x180064e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ea0  mov     rcx, [rsp+2D8h]; this
0x180064ea8  test    eax, eax
0x180064eaa  jns     short loc_180064EC0
0x180064eac  mov     r9d, eax; char *
0x180064eaf  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180064eb6  mov     edx, 0D1h; void *
0x180064ebb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064ec0  mov     rax, [rsp+2D8h+var_2A0]
0x180064ec5  mov     [rsp+2D8h+var_278], rax
0x180064eca  lea     rdx, [rsp+2D8h+var_278]
0x180064ecf  lea     rcx, [rsp+2D8h+var_C8]
0x180064ed7  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x180064edc  nop
0x180064edd  mov     rdx, rax
0x180064ee0  lea     rcx, [rsp+2D8h+var_210]
0x180064ee8  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180064eed  nop
0x180064eee  lea     rdx, [rsp+2D8h+var_98]
0x180064ef6  lea     rcx, [rsp+2D8h+var_E8]
0x180064efe  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(std::wstring &)
0x180064f03  nop
0x180064f04  lea     r8, [rsp+2D8h+var_210]
0x180064f0c  lea     rdx, [rsp+2D8h+var_E8]
0x180064f14  lea     rcx, [rsp+2D8h+var_1B0]
0x180064f1c  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180064f21  nop
0x180064f22  lea     rcx, [rsp+2D8h+var_E8]
0x180064f2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064f2f  nop
0x180064f30  lea     rcx, [rsp+2D8h+var_210]
0x180064f38  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180064f3d  nop
0x180064f3e  lea     rcx, [rsp+2D8h+var_B8]
0x180064f46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064f4b  nop
0x180064f4c  lea     rcx, [rsp+2D8h+var_2A0]
0x180064f51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064f56  jmp     loc_1800656AC
0x180064f5b  lea     rcx, [rsp+2D8h+var_108]
0x180064f63  cmp     [rsp+2D8h+var_F0], 7
0x180064f6c  cmova   rcx, [rsp+2D8h+var_108]
0x180064f75  mov     r9d, 0Dh
0x180064f7b  lea     r8, aRegExpandSz; "REG_EXPAND_SZ"
0x180064f82  mov     rdx, [rsp+2D8h+var_F8]
0x180064f8a  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180064f8f  test    al, al
0x180064f91  jz      loc_1800650AF
0x180064f97  mov     [rsp+2D8h+var_2A0], r15
0x180064f9c  mov     rdi, [rsp+2D8h+var_280]
0x180064fa1  mov     rsi, [rdi]
0x180064fa4  xor     edx, edx
0x180064fa6  lea     rcx, [rsp+2D8h+var_2A0]
0x180064fab  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180064fb0  lea     rcx, [rsp+2D8h+var_238]
0x180064fb8  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180064fbd  cmp     qword ptr [rax+18h], 7
0x180064fc2  jbe     short loc_180064FC7
0x180064fc4  mov     rax, [rax]
0x180064fc7  lea     r8, [rsp+2D8h+var_2A0]
0x180064fcc  mov     rdx, rax
0x180064fcf  mov     rcx, rdi
0x180064fd2  mov     rax, [rsi+18h]
0x180064fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fdb  mov     rcx, [rsp+2D8h]; this
0x180064fe3  test    eax, eax
0x180064fe5  jns     short loc_180064FFB
0x180064fe7  mov     r9d, eax; char *
0x180064fea  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180064ff1  mov     edx, 0D8h; void *
0x180064ff6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064ffb  mov     [rsp+2D8h+var_C0], 2
0x180065006  lea     rax, ??_7?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@6B@; const OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::`vftable'
0x18006500d  mov     [rsp+2D8h+var_C8], rax
0x180065015  mov     rdx, [rsp+2D8h+var_2A0]
0x18006501a  lea     rcx, [rsp+2D8h+var_B8]
0x180065022  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180065027  nop
0x180065028  lea     rcx, [rsp+2D8h+var_B8]
0x180065030  call    ??$GetStringByteCountIncludingTerminator@VString@Details@RegistryCompatibility@DEH@OSIntegration@@@Details@RegistryCompatibility@DEH@OSIntegration@@YAIAEBVString@0123@@Z; OSIntegration::DEH::RegistryCompatibility::Details::GetStringByteCountIncludingTerminator<OSIntegration::DEH::RegistryCompatibility::Details::String>(OSIntegration::DEH::RegistryCompatibility::Details::String const &)
0x180065035  nop
0x180065036  lea     rdx, [rsp+2D8h+var_C8]
0x18006503e  lea     rcx, [rsp+2D8h+var_210]
0x180065046  call    ??$?0V?$StringTypeValueData@$01@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$01@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2> &&)
0x18006504b  nop
0x18006504c  lea     rdx, [rsp+2D8h+var_98]
0x180065054  lea     rcx, [rsp+2D8h+var_E8]
0x18006505c  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(std::wstring &)
0x180065061  nop
0x180065062  lea     r8, [rsp+2D8h+var_210]
0x18006506a  lea     rdx, [rsp+2D8h+var_E8]
0x180065072  lea     rcx, [rsp+2D8h+var_1B0]
0x18006507a  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x18006507f  nop
0x180065080  lea     rcx, [rsp+2D8h+var_E8]
0x180065088  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006508d  nop
0x18006508e  lea     rcx, [rsp+2D8h+var_210]
0x180065096  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x18006509b  nop
0x18006509c  lea     rcx, [rsp+2D8h+var_B8]
0x1800650a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800650a9  nop
  ... truncated ...
```
