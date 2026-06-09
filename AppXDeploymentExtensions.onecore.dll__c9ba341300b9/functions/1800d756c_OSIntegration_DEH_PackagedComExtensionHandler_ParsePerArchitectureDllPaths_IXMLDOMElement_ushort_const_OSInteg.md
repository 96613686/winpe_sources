# OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths(IXMLDOMElement *,ushort const *,OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths &,bool)

- ea: `0x1800d756c`
- end: `0x1800d7c3b`
- name: `?ParsePerArchitectureDllPaths@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGAEAUPerArchitectureDllPaths@123@_N@Z`
- size: `1743`
- prototype: `__int64 __fastcall(OSIntegration::Package **this, struct IXMLDOMElement *, char *, struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *, bool)`
- caller_count: `3`
- callee_count: `18`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cb324`
- `0x180169474`
- `0x180169c50`

## callees

- `0x180008a7c`
- `0x18000b9e0`
- `0x18003a300`
- `0x180067050`
- `0x180077608`
- `0x180080b84`
- `0x18008892c`
- `0x180089c5c`
- `0x18008d84c`
- `0x18008f690`
- `0x18009aff4`
- `0x1800b8300`
- `0x1800bf99c`
- `0x1800ccb88`
- `0x1800d756c`
- `0x1800d7c44`
- `0x1800f0260`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d76ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d784e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d7928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d76ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d784e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d7928`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d7ac1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d7ac1`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1800d7b13`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1800d7b13`

## string_xrefs

- `0x1800d7600`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d78cf`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d7912`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d796f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d79a7`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d79df`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d7a54`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d7add`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d7b6a`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d7bea`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d78b1`: `APPX_E_INVALID_MANIFEST`
- `0x1800d7b57`: `APPX_E_INVALID_MANIFEST`
- `0x1800d7994`: `node.query_to(&dllElement)`
- `0x1800d795c`: `dllElement->get_baseName(&elementName)`
- `0x1800d78ff`: `ParseAndRetrieveAttribute(dllElement.get(), Internal::PackagedComConstants::processorArchitectureAttribute, architecture.GetAddressOf())`
- `0x1800d78c3`: `ParseAndRetrievePath(dllElement.get(), Internal::PackagedComConstants::pathAttribute, &pathForArchitecture)`
- `0x1800d7883`: `dllPaths.Path_x86`
- `0x1800d77b6`: `dllPaths.Path_x64`
- `0x1800d77fa`: `dllPaths.Path_arm`
- `0x1800d789a`: `dllPaths.Path_arm64`
- `0x1800d7a41`: `ParseAndRetrievePath(root, Internal::PackagedComConstants::pathAttribute, &relativePathUnspecifiedArchitecture, &pathFound)`
- `0x1800d7acd`: `PathAllocCombine(_sourcePackage->GetPackageRoot(), wil::str_raw_ptr(relativePathUnspecifiedArchitecture), PATHCCH_ALLOW_LONG_PATHS, &absolutePathUnspecifiedArchitecture)`
- `0x1800d7b1f`: `CoGetModuleArchitecture( absolutePathUnspecifiedArchitecture.get(), &moduleArchitecture)`
- `0x1800d7bd7`: `!hasAnyPerArchitecturePaths && !pathFound`
- `0x1800d7607`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d78d6`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d790b`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d7968`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d79a0`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d79d8`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d7a4d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d7ae4`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d7b63`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`
- `0x1800d7be3`: `OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        char *a3,
        struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *a4,
        bool a5)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  char v15; // bl
  unsigned int i; // r14d
  __int64 v17; // rax
  int v18; // eax
  HRESULT ModuleArchitecture; // esi
  int v20; // eax
  struct IXMLDOMElementVtbl *v21; // rax
  int v22; // eax
  unsigned __int16 *v23; // rax
  int v24; // edx
  int v25; // ecx
  OSIntegration::DEH::PackagedComExtensionHandler *v26; // rcx
  int v27; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  HSTRING v31; // r8
  struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *v32; // rcx
  __int64 v33; // rax
  HSTRING v34; // r8
  const char *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  HSTRING v38; // r8
  __int64 v39; // rax
  HSTRING v40; // r8
  OSIntegration::DEH::PackagedComExtensionHandler *v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  char v44; // r14
  const WCHAR *PackageRoot; // rax
  PCWSTR v46; // rdx
  const char *v47; // rax
  __int64 v48; // rdx
  struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *v49; // rcx
  char *v51; // [rsp+28h] [rbp-69h]
  int v52; // [rsp+30h] [rbp-61h] BYREF
  HSTRING string; // [rsp+38h] [rbp-59h] BYREF
  HSTRING v54; // [rsp+40h] [rbp-51h] BYREF
  struct IXMLDOMElement *v55; // [rsp+48h] [rbp-49h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+50h] [rbp-41h] BYREF
  HSTRING v57; // [rsp+58h] [rbp-39h] BYREF
  char *v58; // [rsp+60h] [rbp-31h] BYREF
  PWSTR ppszPathOut; // [rsp+68h] [rbp-29h] BYREF
  int v60; // [rsp+70h] [rbp-21h] BYREF
  __int64 *v61; // [rsp+78h] [rbp-19h] BYREF
  _BYTE v62[32]; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+57h]

  lpVtbl = a2->lpVtbl;
  v61 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 **))lpVtbl->get_childNodes)(a2, &v61);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v60 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v61 + 64))(v61, &v60);
    v11 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v51) = v14;
      v12 = "childNodes->get_length(&listLength)";
      v13 = 2025;
      goto LABEL_5;
    }
    v15 = 0;
    for ( i = 0; (int)i < v60; ++i )
    {
      v56 = 0;
      v17 = *v61;
      v56 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v17 + 56))(v61, i, &v56);
      ModuleArchitecture = v18;
      if ( v18 < 0 )
      {
        LODWORD(v51) = v18;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x7EE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
          "childNodes->get_item(nodeIndex, &node)",
          v51,
          v52);
        goto LABEL_41;
      }
      v55 = 0;
      wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v55);
      v20 = (**v56)(v56, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v55);
      ModuleArchitecture = v20;
      if ( v20 < 0 )
      {
        LODWORD(v51) = v20;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x7F4,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
          "node.query_to(&dllElement)",
          v51,
          v52);
LABEL_39:
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v55);
LABEL_41:
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v56);
LABEL_42:
        v11 = ModuleArchitecture;
        goto LABEL_74;
      }
      v58 = 0;
      v21 = v55->lpVtbl;
      v58 = 0;
      v22 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, char **))v21->get_baseName)(v55, &v58);
      ModuleArchitecture = v22;
      if ( v22 < 0 )
      {
        LODWORD(v51) = v22;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x7F7,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
          "dllElement->get_baseName(&elementName)",
          v51,
          v52);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        goto LABEL_39;
      }
      v23 = (unsigned __int16 *)v58;
      do
      {
        v24 = *(unsigned __int16 *)((char *)v23 + a3 - v58);
        v25 = *v23 - v24;
        if ( v25 )
          break;
        ++v23;
      }
      while ( v24 );
      if ( !v25 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v27 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
                v26,
                v55,
                L"ProcessorArchitecture",
                &string,
                0);
        v11 = v27;
        if ( v27 < 0 )
        {
          LODWORD(v51) = v27;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x7FE,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
            "ParseAndRetrieveAttribute(dllElement.get(), Internal::PackagedComConstants::processorArchitectureAttribute, "
            "architecture.GetAddressOf())",
            v51,
            v52);
          goto LABEL_36;
        }
        v54 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v54,
          0);
        v29 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(
                v28,
                v55,
                (struct IXMLDOMElement *)&stru_180231CA8,
                &v54,
                0);
        v11 = v29;
        if ( v29 < 0 )
        {
          LODWORD(v51) = v29;
          v35 = "ParseAndRetrievePath(dllElement.get(), Internal::PackagedComConstants::pathAttribute, &pathForArchitecture)";
          v36 = 2050;
LABEL_34:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v36,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
            v35,
            v51,
            v52);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v54);
LABEL_36:
          WindowsDeleteString(string);
          string = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v55);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v56);
          goto LABEL_74;
        }
        v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v62, off_1802E0A70);
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                             (Microsoft::WRL::Wrappers::Details *)string,
                             *(HSTRING *)(v30 + 24),
                             v31) )
        {
          v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v62, off_1802E0A88);
          if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                               (Microsoft::WRL::Wrappers::Details *)string,
                               *(HSTRING *)(v33 + 24),
                               v34) )
          {
            v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v62, off_1802E0A78);
            if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                 (Microsoft::WRL::Wrappers::Details *)string,
                                 *(HSTRING *)(v37 + 24),
                                 v38) )
            {
              v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v62, off_1802E0A80);
              if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                   (Microsoft::WRL::Wrappers::Details *)string,
                                   *(HSTRING *)(v39 + 24),
                                   v40) )
              {
                v11 = -2146958844;
                LODWORD(v51) = -2146958844;
                v35 = "APPX_E_INVALID_MANIFEST";
                v36 = 2078;
                goto LABEL_34;
              }
              v32 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 24);
              if ( *((_QWORD *)a4 + 3) )
              {
                v11 = -2146958844;
                LODWORD(v51) = -2146958844;
                v35 = "dllPaths.Path_arm64";
                v36 = 2072;
                goto LABEL_34;
              }
            }
            else
            {
              v32 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 16);
              if ( *((_QWORD *)a4 + 2) )
              {
                v11 = -2146958844;
                LODWORD(v51) = -2146958844;
                v35 = "dllPaths.Path_arm";
                v36 = 2066;
                goto LABEL_34;
              }
            }
          }
          else
          {
            v32 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 8);
            if ( *((_QWORD *)a4 + 1) )
            {
              v11 = -2146958844;
              LODWORD(v51) = -2146958844;
              v35 = "dllPaths.Path_x64";
              v36 = 2060;
              goto LABEL_34;
            }
          }
        }
        else
        {
          if ( *(_QWORD *)a4 )
          {
            v11 = -2146958844;
            LODWORD(v51) = -2146958844;
            v35 = "dllPaths.Path_x86";
            v36 = 2054;
            goto LABEL_34;
          }
          v32 = a4;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
          v32,
          &v54);
        v15 = 1;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v54);
        WindowsDeleteString(string);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v55);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v56);
    }
    v57 = 0;
    LOBYTE(v52) = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v57,
      0);
    v42 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(
            v41,
            a2,
            (struct IXMLDOMElement *)&stru_180231CA8,
            &v57,
            (bool *)&v52);
    ModuleArchitecture = v42;
    if ( v42 < 0 )
    {
      LODWORD(v51) = v42;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x82A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
        "ParseAndRetrievePath(root, Internal::PackagedComConstants::pathAttribute, &relativePathUnspecifiedArchitecture, &pathFound)",
        v51,
        v52);
LABEL_45:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v57);
      goto LABEL_42;
    }
    v44 = v52;
    if ( !(_BYTE)v52 )
      goto LABEL_70;
    if ( v15 && !a5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v43);
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    WindowsGetStringRawBuffer(v57, 0);
    PackageRoot = OSIntegration::Package::GetPackageRoot(this[5]);
    ModuleArchitecture = PathAllocCombine(PackageRoot, v46, 1u, &ppszPathOut);
    if ( ModuleArchitecture < 0 )
    {
      v47 = "PathAllocCombine(_sourcePackage->GetPackageRoot(), wil::str_raw_ptr(relativePathUnspecifiedArchitecture), PA"
            "THCCH_ALLOW_LONG_PATHS, &absolutePathUnspecifiedArchitecture)";
      v48 = 2107;
LABEL_52:
      LODWORD(v51) = ModuleArchitecture;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v48,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
        v47,
        v51,
        v52);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
      goto LABEL_45;
    }
    LODWORD(v54) = 0;
    ModuleArchitecture = CoGetModuleArchitecture(ppszPathOut, &v54);
    if ( ModuleArchitecture < 0 )
    {
      v47 = "CoGetModuleArchitecture( absolutePathUnspecifiedArchitecture.get(), &moduleArchitecture)";
      v48 = 2111;
      goto LABEL_52;
    }
    if ( (_DWORD)v54 == 332 )
    {
      if ( *(_QWORD *)a4 )
      {
LABEL_69:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
LABEL_70:
        if ( v15 || v44 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v57);
          v11 = 0;
          goto LABEL_74;
        }
        v11 = -2146958844;
        LODWORD(v51) = -2146958844;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x864,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
          "!hasAnyPerArchitecturePaths && !pathFound",
          v51,
          v52);
        goto LABEL_60;
      }
      v49 = a4;
    }
    else
    {
      switch ( (_DWORD)v54 )
      {
        case 0x1C0:
          v49 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 16);
          break;
        case 0x8664:
          v49 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 8);
          break;
        case 0xAA64:
          v49 = (struct OSIntegration::DEH::PackagedComExtensionHandler::PerArchitectureDllPaths *)((char *)a4 + 24);
          break;
        default:
          v11 = -2146958844;
          LODWORD(v51) = -2146958844;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x860,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
            "APPX_E_INVALID_MANIFEST",
            v51,
            v52);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
LABEL_60:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v57);
          goto LABEL_74;
      }
      if ( *(_QWORD *)v49 )
        goto LABEL_69;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(
      v49,
      &v57);
    goto LABEL_69;
  }
  LODWORD(v51) = v10;
  v12 = "root->get_childNodes(&childNodes)";
  v13 = 2022;
LABEL_5:
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParsePerArchitectureDllPaths",
    v12,
    v51,
    v52);
LABEL_74:
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v61);
  return v11;
}

```

## disassembly

```asm
0x1800d756c  mov     [rsp-8+arg_10], rbx
0x1800d7571  push    rbp
0x1800d7572  push    rsi
0x1800d7573  push    rdi
0x1800d7574  push    r12
0x1800d7576  push    r13
0x1800d7578  push    r14
0x1800d757a  push    r15
0x1800d757c  lea     rbp, [rsp-1Fh]
0x1800d7581  sub     rsp, 0B0h
0x1800d7588  mov     rax, cs:__security_cookie
0x1800d758f  xor     rax, rsp
0x1800d7592  mov     [rbp+4Fh+var_40], rax
0x1800d7596  mov     rdi, r9
0x1800d7599  mov     r12, r8
0x1800d759c  mov     r15, rdx
0x1800d759f  mov     r13, rcx
0x1800d75a2  mov     rax, [rdx]
0x1800d75a5  xor     esi, esi
0x1800d75a7  mov     [rbp+4Fh+var_68], rsi
0x1800d75ab  lea     rdx, [rbp+4Fh+var_68]
0x1800d75af  mov     rcx, r15
0x1800d75b2  mov     rax, [rax+60h]
0x1800d75b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d75bb  mov     ebx, eax
0x1800d75bd  test    eax, eax
0x1800d75bf  jns     short loc_1800D75D3
0x1800d75c1  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800d75c5  lea     rax, aRootGetChildno_3; "root->get_childNodes(&childNodes)"
0x1800d75cc  mov     edx, 7E6h
0x1800d75d1  jmp     short loc_1800D7600
0x1800d75d3  mov     [rbp+4Fh+var_70], esi
0x1800d75d6  mov     rcx, [rbp+4Fh+var_68]
0x1800d75da  mov     rax, [rcx]
0x1800d75dd  lea     rdx, [rbp+4Fh+var_70]
0x1800d75e1  mov     rax, [rax+40h]
0x1800d75e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d75ea  mov     ebx, eax
0x1800d75ec  test    eax, eax
0x1800d75ee  jns     short loc_1800D7621
0x1800d75f0  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1800d75f4  lea     rax, aChildnodesGetL; "childNodes->get_length(&listLength)"
0x1800d75fb  mov     edx, 7E9h; void *
0x1800d7600  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d7607  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d760e  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d7613  mov     rcx, [rbp+57h]; this
0x1800d7617  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d761c  jmp     loc_1800D7C09
0x1800d7621  mov     bl, sil
0x1800d7624  mov     r14d, esi
0x1800d7627  cmp     r14d, [rbp+4Fh+var_70]
0x1800d762b  jge     loc_1800D7A01
0x1800d7631  mov     [rbp+4Fh+var_90], rsi
0x1800d7635  mov     rcx, [rbp+4Fh+var_68]
0x1800d7639  mov     rax, [rcx]
0x1800d763c  mov     [rbp+4Fh+var_90], rsi
0x1800d7640  lea     r8, [rbp+4Fh+var_90]
0x1800d7644  mov     edx, r14d
0x1800d7647  mov     rax, [rax+38h]
0x1800d764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7650  mov     esi, eax
0x1800d7652  test    eax, eax
0x1800d7654  js      loc_1800D79C4
0x1800d765a  mov     [rbp+4Fh+var_98], 0
0x1800d7662  lea     rcx, [rbp+4Fh+var_98]
0x1800d7666  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x1800d766b  mov     rcx, [rbp+4Fh+var_90]
0x1800d766f  mov     rax, [rcx]
0x1800d7672  lea     r8, [rbp+4Fh+var_98]
0x1800d7676  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800d767d  mov     rax, [rax]
0x1800d7680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7685  mov     esi, eax
0x1800d7687  test    eax, eax
0x1800d7689  js      loc_1800D798C
0x1800d768f  mov     [rbp+4Fh+var_80], 0
0x1800d7697  mov     rcx, [rbp+4Fh+var_98]
0x1800d769b  mov     rax, [rcx]
0x1800d769e  mov     [rbp+4Fh+var_80], 0
0x1800d76a6  lea     rdx, [rbp+4Fh+var_80]
0x1800d76aa  mov     rax, [rax+148h]
0x1800d76b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76b6  mov     esi, eax
0x1800d76b8  test    eax, eax
0x1800d76ba  js      loc_1800D7954
0x1800d76c0  mov     rax, [rbp+4Fh+var_80]
0x1800d76c4  mov     r8, r12
0x1800d76c7  sub     r8, rax
0x1800d76ca  movzx   ecx, word ptr [rax]
0x1800d76cd  movzx   edx, word ptr [rax+r8]
0x1800d76d2  sub     ecx, edx
0x1800d76d4  jnz     short loc_1800D76DE
0x1800d76d6  add     rax, 2
0x1800d76da  test    edx, edx
0x1800d76dc  jnz     short loc_1800D76CA
0x1800d76de  xor     esi, esi
0x1800d76e0  test    ecx, ecx
0x1800d76e2  jnz     loc_1800D7855
0x1800d76e8  mov     [rbp+4Fh+string], rsi
0x1800d76ec  xor     ecx, ecx; string
0x1800d76ee  call    cs:__imp_WindowsDeleteString
0x1800d76f4  mov     [rbp+4Fh+string], rsi
0x1800d76f8  mov     [rsp+0E0h+var_C0], rsi; bool *
0x1800d76fd  lea     r9, [rbp+4Fh+string]; HSTRING *
0x1800d7701  lea     r8, aProcessorarchi; "ProcessorArchitecture"
0x1800d7708  mov     rdx, [rbp+4Fh+var_98]; struct IXMLDOMElement *
0x1800d770c  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d7711  mov     ebx, eax
0x1800d7713  test    eax, eax
0x1800d7715  js      loc_1800D78F7
0x1800d771b  mov     [rbp+4Fh+var_A0], rsi
0x1800d771f  xor     edx, edx
0x1800d7721  lea     rcx, [rbp+4Fh+var_A0]
0x1800d7725  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800d772a  mov     [rsp+0E0h+var_C0], rsi; bool *
0x1800d772f  lea     r9, [rbp+4Fh+var_A0]; HSTRING *
0x1800d7733  lea     r8, stru_180231CA8; unsigned __int16 *
0x1800d773a  mov     rdx, [rbp+4Fh+var_98]; struct IXMLDOMElement *
0x1800d773e  call    ?ParseAndRetrievePath@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d7743  mov     ebx, eax
0x1800d7745  test    eax, eax
0x1800d7747  js      loc_1800D78BF
0x1800d774d  lea     rdx, off_1802E0A70; "x86"
0x1800d7754  lea     rcx, [rbp+4Fh+var_60]
0x1800d7758  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d775d  mov     rdx, [rax+18h]; HSTRING
0x1800d7761  mov     rcx, [rbp+4Fh+string]; this
0x1800d7765  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800d776a  test    eax, eax
0x1800d776c  jnz     short loc_1800D777F
0x1800d776e  cmp     [rdi], rsi
0x1800d7771  jnz     loc_1800D787A
0x1800d7777  mov     rcx, rdi
0x1800d777a  jmp     loc_1800D7835
0x1800d777f  lea     rdx, off_1802E0A88; "x64"
0x1800d7786  lea     rcx, [rbp+4Fh+var_60]
0x1800d778a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d778f  mov     rdx, [rax+18h]; HSTRING
0x1800d7793  mov     rcx, [rbp+4Fh+string]; this
0x1800d7797  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800d779c  test    eax, eax
0x1800d779e  jnz     short loc_1800D77C7
0x1800d77a0  lea     rcx, [rdi+8]
0x1800d77a4  cmp     [rcx], rsi
0x1800d77a7  jz      loc_1800D7835
0x1800d77ad  mov     ebx, 80080204h
0x1800d77b2  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800d77b6  lea     rax, aDllpathsPathX6; "dllPaths.Path_x64"
0x1800d77bd  mov     edx, 80Ch
0x1800d77c2  jmp     loc_1800D78CF
0x1800d77c7  lea     rdx, off_1802E0A78; "arm"
0x1800d77ce  lea     rcx, [rbp+4Fh+var_60]
0x1800d77d2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d77d7  mov     rdx, [rax+18h]; HSTRING
0x1800d77db  mov     rcx, [rbp+4Fh+string]; this
0x1800d77df  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800d77e4  test    eax, eax
0x1800d77e6  jnz     short loc_1800D780B
0x1800d77e8  lea     rcx, [rdi+10h]
0x1800d77ec  cmp     [rcx], rsi
0x1800d77ef  jz      short loc_1800D7835
0x1800d77f1  mov     ebx, 80080204h
0x1800d77f6  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800d77fa  lea     rax, aDllpathsPathAr_0; "dllPaths.Path_arm"
0x1800d7801  mov     edx, 812h
0x1800d7806  jmp     loc_1800D78CF
0x1800d780b  lea     rdx, off_1802E0A80; "arm64"
0x1800d7812  lea     rcx, [rbp+4Fh+var_60]
0x1800d7816  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d781b  mov     rdx, [rax+18h]; HSTRING
0x1800d781f  mov     rcx, [rbp+4Fh+string]; this
0x1800d7823  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800d7828  test    eax, eax
0x1800d782a  jnz     short loc_1800D78A8
0x1800d782c  lea     rcx, [rdi+18h]
0x1800d7830  cmp     [rcx], rsi
0x1800d7833  jnz     short loc_1800D7891
0x1800d7835  lea     rdx, [rbp+4Fh+var_A0]
0x1800d7839  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&)
0x1800d783e  mov     bl, 1
0x1800d7840  lea     rcx, [rbp+4Fh+var_A0]
0x1800d7844  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800d7849  nop
0x1800d784a  mov     rcx, [rbp+4Fh+string]; string
0x1800d784e  call    cs:__imp_WindowsDeleteString
0x1800d7854  nop
0x1800d7855  lea     rcx, [rbp+4Fh+var_80]
0x1800d7859  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d785e  nop
0x1800d785f  lea     rcx, [rbp+4Fh+var_98]
0x1800d7863  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d7868  nop
0x1800d7869  lea     rcx, [rbp+4Fh+var_90]
0x1800d786d  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d7872  inc     r14d
0x1800d7875  jmp     loc_1800D7627
0x1800d787a  mov     ebx, 80080204h
0x1800d787f  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800d7883  lea     rax, aDllpathsPathX8; "dllPaths.Path_x86"
0x1800d788a  mov     edx, 806h
0x1800d788f  jmp     short loc_1800D78CF
0x1800d7891  mov     ebx, 80080204h
0x1800d7896  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800d789a  lea     rax, aDllpathsPathAr; "dllPaths.Path_arm64"
0x1800d78a1  mov     edx, 818h
0x1800d78a6  jmp     short loc_1800D78CF
0x1800d78a8  mov     ebx, 80080204h
0x1800d78ad  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1800d78b1  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800d78b8  mov     edx, 81Eh
0x1800d78bd  jmp     short loc_1800D78CF
0x1800d78bf  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1800d78c3  lea     rax, aParseandretrie_48; "ParseAndRetrievePath(dllElement.get(), "...
0x1800d78ca  mov     edx, 802h; void *
0x1800d78cf  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d78d6  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d78dd  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d78e2  mov     rcx, [rbp+57h]; this
0x1800d78e6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d78eb  nop
0x1800d78ec  lea     rcx, [rbp+4Fh+var_A0]
0x1800d78f0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800d78f5  jmp     short loc_1800D7924
0x1800d78f7  mov     rcx, [rbp+57h]; this
0x1800d78fb  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1800d78ff  lea     rax, aParseandretrie_22; "ParseAndRetrieveAttribute(dllElement.ge"...
0x1800d7906  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d790b  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d7912  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d7919  mov     edx, 7FEh; void *
0x1800d791e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d7923  nop
0x1800d7924  mov     rcx, [rbp+4Fh+string]; string
0x1800d7928  call    cs:__imp_WindowsDeleteString
0x1800d792e  mov     [rbp+4Fh+string], rsi
0x1800d7932  lea     rcx, [rbp+4Fh+var_80]
0x1800d7936  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d793b  nop
0x1800d793c  lea     rcx, [rbp+4Fh+var_98]
0x1800d7940  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d7945  nop
0x1800d7946  lea     rcx, [rbp+4Fh+var_90]
0x1800d794a  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d794f  jmp     loc_1800D7C09
0x1800d7954  mov     rcx, [rbp+57h]; this
0x1800d7958  mov     dword ptr [rsp+0E0h+var_B8], esi; char *
0x1800d795c  lea     rax, aDllelementGetB; "dllElement->get_baseName(&elementName)"
0x1800d7963  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d7968  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d796f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d7976  mov     edx, 7F7h; void *
0x1800d797b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d7980  nop
0x1800d7981  lea     rcx, [rbp+4Fh+var_80]
0x1800d7985  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d798a  jmp     short loc_1800D79B9
0x1800d798c  mov     rcx, [rbp+57h]; this
0x1800d7990  mov     dword ptr [rsp+0E0h+var_B8], esi; char *
0x1800d7994  lea     rax, aNodeQueryToDll; "node.query_to(&dllElement)"
0x1800d799b  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d79a0  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d79a7  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d79ae  mov     edx, 7F4h; void *
0x1800d79b3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d79b8  nop
0x1800d79b9  lea     rcx, [rbp+4Fh+var_98]
0x1800d79bd  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d79c2  jmp     short loc_1800D79F1
0x1800d79c4  mov     rcx, [rbp+57h]; this
0x1800d79c8  mov     dword ptr [rsp+0E0h+var_B8], esi; char *
0x1800d79cc  lea     rax, aChildnodesGetI; "childNodes->get_item(nodeIndex, &node)"
0x1800d79d3  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d79d8  lea     r9, aOsintegrationD_452; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d79df  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d79e6  mov     edx, 7EEh; void *
0x1800d79eb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d79f0  nop
0x1800d79f1  lea     rcx, [rbp+4Fh+var_90]
0x1800d79f5  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800d79fa  mov     ebx, esi
0x1800d79fc  jmp     loc_1800D7C09
0x1800d7a01  mov     [rbp+4Fh+var_88], rsi
0x1800d7a05  mov     byte ptr [rbp+4Fh+var_B0], sil
0x1800d7a09  xor     edx, edx
0x1800d7a0b  lea     rcx, [rbp+4Fh+var_88]
0x1800d7a0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800d7a14  lea     rax, [rbp+4Fh+var_B0]
0x1800d7a18  mov     [rsp+0E0h+var_C0], rax; bool *
0x1800d7a1d  lea     r9, [rbp+4Fh+var_88]; HSTRING *
0x1800d7a21  lea     r8, stru_180231CA8; unsigned __int16 *
0x1800d7a28  mov     rdx, r15; struct IXMLDOMElement *
0x1800d7a2b  call    ?ParseAndRetrievePath@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d7a30  mov     esi, eax
0x1800d7a32  xor     r15d, r15d
0x1800d7a35  test    eax, eax
0x1800d7a37  jns     short loc_1800D7A71
0x1800d7a39  mov     rcx, [rbp+57h]; this
0x1800d7a3d  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1800d7a41  lea     rax, aParseandretrie_27; "ParseAndRetrievePath(root, Internal::Pa"...
  ... truncated ...
```
