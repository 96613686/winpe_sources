# winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider::RetrieveProperties(_tagpropertykey const *,ulong,IPropertyStore * *)

- ea: `0x18005cd30`
- end: `0x18005d374`
- name: `?RetrieveProperties@PerFolderRootPropertyProvider@implementation@Storage@Internal@Windows@winrt@@UEAAJPEBU_tagpropertykey@@KPEAPEAUIPropertyStore@@@Z`
- size: `1604`
- prototype: `__int64 __fastcall(winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider *__hidden this, const struct _tagpropertykey *, unsigned int, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007900`
- `0x18000fc58`
- `0x18000ff08`
- `0x180010934`
- `0x180010958`
- `0x1800164d4`
- `0x180016b38`
- `0x18001d320`
- `0x180022648`
- `0x180029dfc`
- `0x18002c6b0`
- `0x1800348e8`
- `0x180037780`
- `0x18003bfc4`
- `0x18003d38c`
- `0x18005b640`
- `0x18005b794`
- `0x18005ba90`
- `0x18005c86c`
- `0x18005cd30`
- `0x18005d39c`
- `0x18005d4b4`
- `0x18005d5a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d1f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d1f5`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18005d0f5`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18005d0f5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005cf5f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005cf5f`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18005cde0`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18005ce27`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18005cde0`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18005ce27`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18005d192`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18005d192`

## string_xrefs

- `0x18005d30d`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootpropertyprovider.cpp`
- `0x18005d322`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootpropertyprovider.cpp`
- `0x18005d337`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootpropertyprovider.cpp`
- `0x18005d34c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootpropertyprovider.cpp`
- `0x18005d361`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootpropertyprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider::RetrieveProperties(
        winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider *this,
        const struct _tagpropertykey *a2,
        unsigned int a3,
        struct IPropertyStore **a4)
{
  __int64 v5; // rsi
  unsigned int i; // ebx
  __int64 v9; // rax
  __int64 *v10; // rcx
  HRESULT v11; // eax
  __int64 v12; // rax
  const char *v13; // r9
  __int64 result; // rax
  HRESULT v15; // eax
  unsigned int v16; // eax
  PWSTR v17; // r14
  unsigned int v18; // esi
  struct IUnknown *v19; // rdx
  int v20; // esi
  __int64 (__fastcall *v21)(PWSTR, void **); // rbx
  void **v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // esi
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, IUnknown **); // rbx
  unsigned int v27; // eax
  const WCHAR *v28; // rax
  HRESULT v29; // eax
  unsigned int v30; // esi
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, void **); // rbx
  struct IUnknown *v33; // rdx
  void **v34; // rax
  unsigned int v35; // eax
  HRESULT v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  struct IPropertyStore *v39; // rax
  int v40; // [rsp+20h] [rbp-108h] BYREF
  unsigned int v41; // [rsp+24h] [rbp-104h] BYREF
  PWSTR ppszCanonicalName; // [rsp+28h] [rbp-100h] BYREF
  IUnknown *punkPropertyValue; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v44; // [rsp+38h] [rbp-F0h] BYREF
  __int128 v45; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-D8h]
  WCHAR *v47; // [rsp+58h] [rbp-D0h] BYREF
  void *ppv[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+70h] [rbp-B8h] BYREF
  int v50; // [rsp+78h] [rbp-B0h]
  _BYTE v51[8]; // [rsp+80h] [rbp-A8h] BYREF
  PROPVARIANT ppropvar[3]; // [rsp+88h] [rbp-A0h] BYREF
  int v53; // [rsp+A0h] [rbp-88h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-80h]
  _BYTE v55[4]; // [rsp+B8h] [rbp-70h] BYREF
  _BYTE v56[4]; // [rsp+BCh] [rbp-6Ch] BYREF
  _BYTE v57[8]; // [rsp+C0h] [rbp-68h] BYREF
  PROPERTYKEY ppropkey; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v5 = a3;
  v41 = 0;
  try
  {
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled)() )
      *a4 = 0;
    v45 = 0;
    v46 = 0;
    v49 = v5;
    if ( (_DWORD)v5 )
      std::vector<winrt::hstring>::_Reallocate<0>(&v45, &v49);
    for ( i = 0; i < (unsigned int)v5; ++i )
    {
      ppszCanonicalName = 0;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl'::`2'::impl) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszCanonicalName,
          0);
        v11 = PSGetNameFromPropertyKey(&a2[i], &ppszCanonicalName);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootpropertyprovider.cpp",
            (const char *)(unsigned int)v11,
            v40);
        v12 = winrt::hstring::hstring((winrt::hstring *)&v44, ppszCanonicalName);
        std::vector<winrt::hstring>::push_back(&v45, v12);
        v10 = &v44;
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszCanonicalName,
        0);
      if ( PSGetNameFromPropertyKey(&a2[i], &ppszCanonicalName) >= 0 && ppszCanonicalName && *ppszCanonicalName )
      {
        v9 = winrt::hstring::hstring((winrt::hstring *)&v49, ppszCanonicalName);
        std::vector<winrt::hstring>::push_back(&v45, v9);
        v10 = &v49;
LABEL_15:
        winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszCanonicalName);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl'::`2'::impl)
      && (_QWORD)v45 == *((_QWORD *)&v45 + 1) )
    {
      if ( (_QWORD)v45 )
      {
        std::_Destroy_range<std::allocator<winrt::hstring>>(v45, *((_QWORD *)&v45 + 1));
        std::_Deallocate<16>(v45, (v46 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      result = 0;
    }
    else
    {
      v49 = v45;
      v50 = (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 3;
      winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider::GetPropertiesAsPropertySet(
        this,
        v51,
        &v49);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl'::`2'::impl)
        || (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(v51) )
      {
        ppv[0] = 0;
        v15 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, ppv);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4C,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootpropertyprovider.cpp",
            (const char *)(unsigned int)v15,
            v40);
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IPropertySet,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::First(
          v51,
          &ppszCanonicalName);
        LOBYTE(v40) = 0;
        LODWORD(ppropvar[0]) = 0;
        *(_OWORD *)&ppropvar[1] = 0;
        v16 = (*(__int64 (__fastcall **)(PWSTR, int *))(*(_QWORD *)ppszCanonicalName + 56LL))(ppszCanonicalName, &v40);
        winrt::check_hresult(&v41, v16, ppropvar);
        if ( (_BYTE)v40 )
        {
          v17 = ppszCanonicalName;
          ppszCanonicalName = 0;
          v47 = v17;
        }
        else
        {
          v17 = 0;
          v47 = 0;
        }
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&ppszCanonicalName);
        v18 = 3;
        v49 = 0;
        while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v47, &v49) )
        {
          v44 = 0;
          v20 = v18 | 8;
          v41 = v20;
          LODWORD(ppropvar[0]) = 0;
          *(_OWORD *)&ppropvar[1] = 0;
          v21 = *(__int64 (__fastcall **)(PWSTR, void **))(*(_QWORD *)v17 + 48LL);
          v22 = winrt::put_abi((winrt *)&v44, v19);
          v23 = v21(v17, v22);
          winrt::check_hresult(v55, v23, ppropvar);
          memset(&ppropkey, 0, sizeof(ppropkey));
          punkPropertyValue = 0;
          v24 = v20 & 0xFFFFFFE3 | 0x14;
          v41 = v24;
          v25 = v44;
          v53 = 0;
          v54 = 0;
          v26 = *(__int64 (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v44 + 48LL);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&punkPropertyValue);
          v27 = v26(v25, &punkPropertyValue);
          winrt::check_hresult(v56, v27, &v53);
          v28 = winrt::hstring::c_str((winrt::hstring *)&punkPropertyValue);
          v29 = PSGetPropertyKeyFromName(v28, &ppropkey);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x50,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootpropertyprovider.cpp",
              (const char *)(unsigned int)v29,
              v40);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&punkPropertyValue);
          memset(ppropvar, 0, sizeof(ppropvar));
          punkPropertyValue = 0;
          v30 = v24 & 0xFFFFFFCF | 0x20;
          v41 = v30;
          v31 = v44;
          v53 = 0;
          v54 = 0;
          v32 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v44 + 56LL);
          v34 = winrt::put_abi((winrt *)&punkPropertyValue, v33);
          v35 = v32(v31, v34);
          winrt::check_hresult(v57, v35, &v53);
          v36 = WinRTPropertyValueToPropVariant(punkPropertyValue, ppropvar);
          if ( v36 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x52,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootpropertyprovider.cpp",
              (const char *)(unsigned int)v36,
              v40);
          v18 = v30 & 0xFFFFFFDF;
          if ( punkPropertyValue )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&punkPropertyValue);
          v37 = (*(__int64 (__fastcall **)(void *, PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv[0] + 48LL))(
                  ppv[0],
                  &ppropkey,
                  ppropvar);
          if ( v37 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x53,
              (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootpropertyprovider.cpp",
              (const char *)(unsigned int)v37,
              v40);
          PropVariantClear(ppropvar);
          winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v44);
          LOBYTE(v40) = 0;
          v53 = 0;
          v54 = 0;
          v38 = (*(__int64 (__fastcall **)(PWSTR, int *))(*(_QWORD *)v17 + 64LL))(v17, &v40);
          winrt::check_hresult(&ppszCanonicalName, v38, &v53);
          if ( !(_BYTE)v40 )
          {
            v44 = 0;
            winrt::Windows::Foundation::IUnknown::operator=(&v47, &v44);
            winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v44);
            v17 = v47;
          }
        }
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v49);
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(&v47);
        v39 = (struct IPropertyStore *)ppv[0];
        ppv[0] = 0;
        *a4 = v39;
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(ppv);
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v51);
        if ( (_QWORD)v45 )
        {
          std::_Destroy_range<std::allocator<winrt::hstring>>(v45, *((_QWORD *)&v45 + 1));
          std::_Deallocate<16>(v45, (v46 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
        }
        result = 0;
      }
      else
      {
        winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v51);
        if ( (_QWORD)v45 )
        {
          std::_Destroy_range<std::allocator<winrt::hstring>>(v45, *((_QWORD *)&v45 + 1));
          std::_Deallocate<16>(v45, (v46 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
        }
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x59,
                           (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderro"
                                         "otpropertyprovider.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18005cd30  push    rbx
0x18005cd32  push    rsi
0x18005cd33  push    rdi
0x18005cd34  push    r12
0x18005cd36  push    r13
0x18005cd38  push    r14
0x18005cd3a  push    r15
0x18005cd3c  sub     rsp, 0F0h
0x18005cd43  mov     rax, cs:__security_cookie
0x18005cd4a  xor     rax, rsp
0x18005cd4d  mov     [rsp+128h+var_48], rax
0x18005cd55  mov     r15, r9
0x18005cd58  mov     esi, r8d
0x18005cd5b  mov     r14, rdx
0x18005cd5e  mov     r12, rcx
0x18005cd61  xor     r13d, r13d
0x18005cd64  mov     [rsp+128h+var_104], r13d
0x18005cd69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise> `wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl(void)'::`2'::impl
0x18005cd70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(void)
0x18005cd75  test    al, al
0x18005cd77  jz      short loc_18005CD7C
0x18005cd79  mov     [r15], r13
0x18005cd7c  xorps   xmm0, xmm0
0x18005cd7f  movdqu  [rsp+128h+var_E8], xmm0
0x18005cd85  mov     [rsp+128h+var_D8], r13
0x18005cd8a  mov     [rsp+128h+var_B8], rsi
0x18005cd8f  test    esi, esi
0x18005cd91  jz      short loc_18005CDA2
0x18005cd93  lea     rdx, [rsp+128h+var_B8]
0x18005cd98  lea     rcx, [rsp+128h+var_E8]
0x18005cd9d  call    ??$_Reallocate@$0A@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAXAEA_K@Z; std::vector<winrt::hstring>::_Reallocate<0>(unsigned __int64 &)
0x18005cda2  mov     ebx, r13d
0x18005cda5  cmp     ebx, esi
0x18005cda7  jnb     loc_18005CE77
0x18005cdad  mov     [rsp+128h+ppszCanonicalName], r13
0x18005cdb2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise> `wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl(void)'::`2'::impl
0x18005cdb9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(void)
0x18005cdbe  mov     ecx, ebx
0x18005cdc0  lea     rdx, [rcx+rcx*4]
0x18005cdc4  lea     rdi, [r14+rdx*4]
0x18005cdc8  xor     edx, edx
0x18005cdca  lea     rcx, [rsp+128h+ppszCanonicalName]
0x18005cdcf  test    al, al
0x18005cdd1  jz      short loc_18005CE1A
0x18005cdd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005cdd8  lea     rdx, [rsp+128h+ppszCanonicalName]; ppszCanonicalName
0x18005cddd  mov     rcx, rdi; propkey
0x18005cde0  call    cs:__imp_PSGetNameFromPropertyKey
0x18005cde6  test    eax, eax
0x18005cde8  js      short loc_18005CE66
0x18005cdea  mov     rdx, [rsp+128h+ppszCanonicalName]; unsigned __int16 *
0x18005cdef  test    rdx, rdx
0x18005cdf2  jz      short loc_18005CE66
0x18005cdf4  cmp     [rdx], r13w
0x18005cdf8  jz      short loc_18005CE66
0x18005cdfa  lea     rcx, [rsp+128h+var_B8]; this
0x18005cdff  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18005ce04  nop
0x18005ce05  mov     rdx, rax
0x18005ce08  lea     rcx, [rsp+128h+var_E8]
0x18005ce0d  call    ?push_back@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAAX$$QEAUhstring@winrt@@@Z; std::vector<winrt::hstring>::push_back(winrt::hstring &&)
0x18005ce12  nop
0x18005ce13  lea     rcx, [rsp+128h+var_B8]
0x18005ce18  jmp     short loc_18005CE60
0x18005ce1a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005ce1f  lea     rdx, [rsp+128h+ppszCanonicalName]; ppszCanonicalName
0x18005ce24  mov     rcx, rdi; propkey
0x18005ce27  call    cs:__imp_PSGetNameFromPropertyKey
0x18005ce2d  mov     rcx, [rsp+128h]; this
0x18005ce35  test    eax, eax
0x18005ce37  js      loc_18005D30A
0x18005ce3d  mov     rdx, [rsp+128h+ppszCanonicalName]; unsigned __int16 *
0x18005ce42  lea     rcx, [rsp+128h+var_F0]; this
0x18005ce47  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18005ce4c  nop
0x18005ce4d  mov     rdx, rax
0x18005ce50  lea     rcx, [rsp+128h+var_E8]
0x18005ce55  call    ?push_back@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAAX$$QEAUhstring@winrt@@@Z; std::vector<winrt::hstring>::push_back(winrt::hstring &&)
0x18005ce5a  nop
0x18005ce5b  lea     rcx, [rsp+128h+var_F0]
0x18005ce60  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18005ce65  nop
0x18005ce66  lea     rcx, [rsp+128h+ppszCanonicalName]; void *
0x18005ce6b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18005ce70  inc     ebx
0x18005ce72  jmp     loc_18005CDA5
0x18005ce77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise> `wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl(void)'::`2'::impl
0x18005ce7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(void)
0x18005ce83  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18005ce88  test    al, al
0x18005ce8a  mov     rax, qword ptr [rsp+128h+var_E8+8]
0x18005ce8f  jz      short loc_18005CEC0
0x18005ce91  cmp     rcx, rax
0x18005ce94  jnz     short loc_18005CEC0
0x18005ce96  test    rcx, rcx
0x18005ce99  jz      short loc_18005CEB9
0x18005ce9b  mov     rdx, rax
0x18005ce9e  call    ??$_Destroy_range@V?$allocator@Uhstring@winrt@@@std@@@std@@YAXPEAUhstring@winrt@@QEAU12@AEAV?$allocator@Uhstring@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::hstring>>(winrt::hstring *,winrt::hstring * const,std::allocator<winrt::hstring> &)
0x18005cea3  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18005cea8  mov     rdx, [rsp+128h+var_D8]
0x18005cead  sub     rdx, rcx
0x18005ceb0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005ceb4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005ceb9  xor     eax, eax
0x18005cebb  jmp     loc_18005D2E7
0x18005cec0  mov     [rsp+128h+var_B8], rcx
0x18005cec5  sub     rax, rcx
0x18005cec8  sar     rax, 3
0x18005cecc  mov     [rsp+128h+var_B0], eax
0x18005ced0  mov     eax, [rsp+128h+var_AC]
0x18005ced4  mov     [rsp+128h+var_AC], eax
0x18005ced8  lea     r8, [rsp+128h+var_B8]
0x18005cedd  lea     rdx, [rsp+128h+var_A8]
0x18005cee5  mov     rcx, r12
0x18005cee8  call    ?GetPropertiesAsPropertySet@PerFolderRootPropertyProvider@implementation@Storage@Internal@Windows@winrt@@QEAA?AUIPropertySet@Collections@Foundation@56@U?$array_view@$$CBUhstring@winrt@@@6@@Z; winrt::Windows::Internal::Storage::implementation::PerFolderRootPropertyProvider::GetPropertiesAsPropertySet(winrt::array_view<winrt::hstring const>)
0x18005ceed  nop
0x18005ceee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise> `wil::Feature<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::GetImpl(void)'::`2'::impl
0x18005cef5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerFolderRootPropertyTestNoise>::__private_IsEnabled(void)
0x18005cefa  test    al, al
0x18005cefc  jz      short loc_18005CF4E
0x18005cefe  lea     rcx, [rsp+128h+var_A8]
0x18005cf06  call    ?Size@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(void)
0x18005cf0b  test    eax, eax
0x18005cf0d  jnz     short loc_18005CF4E
0x18005cf0f  lea     rcx, [rsp+128h+var_A8]
0x18005cf17  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18005cf1c  nop
0x18005cf1d  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18005cf22  test    rcx, rcx
0x18005cf25  jz      short loc_18005CF47
0x18005cf27  mov     rdx, qword ptr [rsp+128h+var_E8+8]
0x18005cf2c  call    ??$_Destroy_range@V?$allocator@Uhstring@winrt@@@std@@@std@@YAXPEAUhstring@winrt@@QEAU12@AEAV?$allocator@Uhstring@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::hstring>>(winrt::hstring *,winrt::hstring * const,std::allocator<winrt::hstring> &)
0x18005cf31  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18005cf36  mov     rdx, [rsp+128h+var_D8]
0x18005cf3b  sub     rdx, rcx
0x18005cf3e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005cf42  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005cf47  xor     eax, eax
0x18005cf49  jmp     loc_18005D2E7
0x18005cf4e  mov     [rsp+128h+ppv], r13
0x18005cf53  lea     rdx, [rsp+128h+ppv]; ppv
0x18005cf58  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005cf5f  call    cs:__imp_PSCreateMemoryPropertyStore
0x18005cf65  mov     rcx, [rsp+128h]; this
0x18005cf6d  test    eax, eax
0x18005cf6f  js      loc_18005D31F
0x18005cf75  lea     rdx, [rsp+128h+ppszCanonicalName]
0x18005cf7a  lea     rcx, [rsp+128h+var_A8]
0x18005cf82  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@UIPropertySet@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IPropertySet,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::First(void)
0x18005cf87  nop
0x18005cf88  mov     byte ptr [rsp+128h+var_108], r13b; int
0x18005cf8d  mov     rcx, [rsp+128h+ppszCanonicalName]
0x18005cf92  mov     dword ptr [rsp+128h+ppropvar], r13d
0x18005cf9a  xorps   xmm0, xmm0
0x18005cf9d  movdqu  xmmword ptr [rsp+128h+ppropvar+8], xmm0
0x18005cfa6  mov     rax, [rcx]
0x18005cfa9  lea     rdx, [rsp+128h+var_108]
0x18005cfae  mov     rax, [rax+38h]
0x18005cfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfb7  lea     r8, [rsp+128h+ppropvar]
0x18005cfbf  mov     edx, eax
0x18005cfc1  lea     rcx, [rsp+128h+var_104]
0x18005cfc6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005cfcb  cmp     byte ptr [rsp+128h+var_108], r13b
0x18005cfd0  jnz     short loc_18005CFDC
0x18005cfd2  mov     r14, r13
0x18005cfd5  mov     [rsp+128h+var_D0], r13
0x18005cfda  jmp     short loc_18005CFEB
0x18005cfdc  mov     r14, [rsp+128h+ppszCanonicalName]
0x18005cfe1  mov     [rsp+128h+ppszCanonicalName], r13
0x18005cfe6  mov     [rsp+128h+var_D0], r14
0x18005cfeb  lea     rcx, [rsp+128h+ppszCanonicalName]
0x18005cff0  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18005cff5  mov     esi, 3
0x18005cffa  mov     [rsp+128h+var_B8], r13
0x18005cfff  lea     rdx, [rsp+128h+var_B8]
0x18005d004  lea     rcx, [rsp+128h+var_D0]
0x18005d009  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18005d00e  test    al, al
0x18005d010  jnz     loc_18005D27A
0x18005d016  mov     [rsp+128h+var_F0], r13
0x18005d01b  or      esi, 8
0x18005d01e  mov     [rsp+128h+var_104], esi
0x18005d022  mov     dword ptr [rsp+128h+ppropvar], r13d
0x18005d02a  xorps   xmm0, xmm0
0x18005d02d  movdqu  xmmword ptr [rsp+128h+ppropvar+8], xmm0
0x18005d036  mov     rax, [r14]
0x18005d039  mov     rbx, [rax+30h]
0x18005d03d  lea     rcx, [rsp+128h+var_F0]; this
0x18005d042  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18005d047  mov     rdx, rax
0x18005d04a  mov     rcx, r14
0x18005d04d  mov     rax, rbx
0x18005d050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d055  lea     r8, [rsp+128h+ppropvar]
0x18005d05d  mov     edx, eax
0x18005d05f  lea     rcx, [rsp+128h+var_70]
0x18005d067  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005d06c  and     esi, 0FFFFFFF7h
0x18005d06f  or      esi, 4
0x18005d072  xorps   xmm0, xmm0
0x18005d075  xor     eax, eax
0x18005d077  movups  xmmword ptr [rsp+128h+ppropkey.fmtid.Data1], xmm0
0x18005d07f  mov     [rsp+128h+ppropkey.pid], eax
0x18005d086  mov     [rsp+128h+punkPropertyValue], r13
0x18005d08b  or      esi, 10h
0x18005d08e  mov     [rsp+128h+var_104], esi
0x18005d092  mov     rdi, [rsp+128h+var_F0]
0x18005d097  mov     [rsp+128h+var_88], r13d
0x18005d09f  movdqu  [rsp+128h+var_80], xmm0
0x18005d0a8  mov     rax, [rdi]
0x18005d0ab  mov     rbx, [rax+30h]
0x18005d0af  lea     rcx, [rsp+128h+punkPropertyValue]
0x18005d0b4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18005d0b9  lea     rdx, [rsp+128h+punkPropertyValue]
0x18005d0be  mov     rcx, rdi
0x18005d0c1  mov     rax, rbx
0x18005d0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0c9  lea     r8, [rsp+128h+var_88]
0x18005d0d1  mov     edx, eax
0x18005d0d3  lea     rcx, [rsp+128h+var_6C]
0x18005d0db  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005d0e0  lea     rcx, [rsp+128h+punkPropertyValue]; this
0x18005d0e5  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18005d0ea  mov     rcx, rax; pszName
0x18005d0ed  lea     rdx, [rsp+128h+ppropkey]; ppropkey
0x18005d0f5  call    cs:__imp_PSGetPropertyKeyFromName
0x18005d0fb  mov     rcx, [rsp+128h]; this
0x18005d103  test    eax, eax
0x18005d105  js      loc_18005D334
0x18005d10b  and     esi, 0FFFFFFEFh
0x18005d10e  lea     rcx, [rsp+128h+punkPropertyValue]
0x18005d113  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18005d118  xorps   xmm0, xmm0
0x18005d11b  xor     eax, eax
0x18005d11d  movups  xmmword ptr [rsp+128h+ppropvar], xmm0
0x18005d125  mov     [rsp+128h+var_90], rax
0x18005d12d  mov     [rsp+128h+punkPropertyValue], r13
0x18005d132  or      esi, 20h
0x18005d135  mov     [rsp+128h+var_104], esi
0x18005d139  mov     rdi, [rsp+128h+var_F0]
0x18005d13e  mov     [rsp+128h+var_88], r13d
0x18005d146  movdqu  [rsp+128h+var_80], xmm0
0x18005d14f  mov     rax, [rdi]
0x18005d152  mov     rbx, [rax+38h]
0x18005d156  lea     rcx, [rsp+128h+punkPropertyValue]; this
0x18005d15b  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18005d160  mov     rdx, rax
0x18005d163  mov     rcx, rdi
0x18005d166  mov     rax, rbx
0x18005d169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d16e  lea     r8, [rsp+128h+var_88]
0x18005d176  mov     edx, eax
0x18005d178  lea     rcx, [rsp+128h+var_68]
0x18005d180  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005d185  lea     rdx, [rsp+128h+ppropvar]; ppropvar
0x18005d18d  mov     rcx, [rsp+128h+punkPropertyValue]; punkPropertyValue
0x18005d192  call    cs:__imp_WinRTPropertyValueToPropVariant
0x18005d198  mov     rcx, [rsp+128h]; this
0x18005d1a0  test    eax, eax
0x18005d1a2  js      loc_18005D349
0x18005d1a8  and     esi, 0FFFFFFDFh
0x18005d1ab  cmp     [rsp+128h+punkPropertyValue], r13
0x18005d1b0  jz      short loc_18005D1BC
0x18005d1b2  lea     rcx, [rsp+128h+punkPropertyValue]
0x18005d1b7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18005d1bc  mov     rcx, [rsp+128h+ppv]
0x18005d1c1  mov     rax, [rcx]
0x18005d1c4  lea     r8, [rsp+128h+ppropvar]
0x18005d1cc  lea     rdx, [rsp+128h+ppropkey]
0x18005d1d4  mov     rax, [rax+30h]
0x18005d1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1dd  mov     rcx, [rsp+128h]; this
0x18005d1e5  test    eax, eax
0x18005d1e7  js      loc_18005D35E
0x18005d1ed  lea     rcx, [rsp+128h+ppropvar]; pvar
0x18005d1f5  call    cs:__imp_PropVariantClear
0x18005d1fb  nop
0x18005d1fc  lea     rcx, [rsp+128h+var_F0]
0x18005d201  call    ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18005d206  mov     byte ptr [rsp+128h+var_108], r13b
0x18005d20b  mov     [rsp+128h+var_88], r13d
0x18005d213  xorps   xmm0, xmm0
0x18005d216  movdqu  [rsp+128h+var_80], xmm0
0x18005d21f  mov     rax, [r14]
0x18005d222  lea     rdx, [rsp+128h+var_108]
0x18005d227  mov     rcx, r14
0x18005d22a  mov     rax, [rax+40h]
0x18005d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d233  lea     r8, [rsp+128h+var_88]
0x18005d23b  mov     edx, eax
0x18005d23d  lea     rcx, [rsp+128h+ppszCanonicalName]
0x18005d242  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005d247  cmp     byte ptr [rsp+128h+var_108], r13b
0x18005d24c  jnz     loc_18005CFFF
0x18005d252  mov     [rsp+128h+var_F0], r13
0x18005d257  lea     rdx, [rsp+128h+var_F0]
0x18005d25c  lea     rcx, [rsp+128h+var_D0]
0x18005d261  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18005d266  lea     rcx, [rsp+128h+var_F0]
  ... truncated ...
```
