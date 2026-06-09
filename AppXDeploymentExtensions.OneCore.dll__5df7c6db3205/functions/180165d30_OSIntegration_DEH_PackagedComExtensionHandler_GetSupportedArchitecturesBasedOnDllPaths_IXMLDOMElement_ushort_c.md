# OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths(IXMLDOMElement *,ushort const *,OSIntegration::DEH::SupportedArchitectureFlags *)

- ea: `0x180165d30`
- end: `0x18016624d`
- name: `?GetSupportedArchitecturesBasedOnDllPaths@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAW4SupportedArchitectureFlags@23@@Z`
- size: `1309`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, enum OSIntegration::DEH::SupportedArchitectureFlags *)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009924c`
- `0x18009c4c0`

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
- `0x1800bf99c`
- `0x1800ccb88`
- `0x1800f0260`
- `0x180165d30`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016612d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016612d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165fde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165fde`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18016614c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18016614c`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18016619e`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18016619e`

## string_xrefs

- `0x180165dc9`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180165fbd`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166005`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016603d`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166075`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1801660ee`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180166178`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180165f9f`: `APPX_E_INVALID_MANIFEST`
- `0x1801661e2`: `APPX_E_INVALID_MANIFEST`
- `0x18016602a`: `node.query_to(&dllElement)`
- `0x180165ff2`: `dllElement->get_baseName(&elementName)`
- `0x180165fb1`: `ParseAndRetrieveAttribute(dllElement.get(), Internal::PackagedComConstants::processorArchitectureAttribute, architecture.GetAddressOf())`
- `0x1801660db`: `ParseAndRetrievePath(root, Internal::PackagedComConstants::pathAttribute, &relativePathUnspecifiedArchitecture, &pathFound)`
- `0x18016615c`: `PathAllocCombine(_sourcePackage->GetPackageRoot(), wil::str_raw_ptr(relativePathUnspecifiedArchitecture), PATHCCH_ALLOW_LONG_PATHS, &absolutePathUnspecifiedArchitecture)`
- `0x1801661ae`: `CoGetModuleArchitecture( absolutePathUnspecifiedArchitecture.get(), &moduleArchitecture)`
- `0x180165dd0`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x180165fc4`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x180165ffe`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x180166036`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x18016606e`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x1801660e7`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`
- `0x180166171`: `OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        char *a3,
        enum OSIntegration::DEH::SupportedArchitectureFlags *a4)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // edi
  const char *v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  unsigned int i; // esi
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  struct IXMLDOMElementVtbl *v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // rax
  int v21; // edx
  int v22; // ecx
  OSIntegration::DEH::PackagedComExtensionHandler *v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  HSTRING v26; // r8
  __int64 v27; // rax
  HSTRING v28; // r8
  __int64 v29; // rax
  HSTRING v30; // r8
  __int64 v31; // rax
  HSTRING v32; // r8
  const char *v33; // rax
  __int64 v34; // rdx
  OSIntegration::DEH::PackagedComExtensionHandler *v35; // rcx
  int v36; // eax
  const WCHAR *PackageRoot; // rax
  PCWSTR v38; // rdx
  HRESULT v39; // eax
  const char *v40; // rax
  __int64 v41; // rdx
  int ModuleArchitecture; // eax
  char *v44; // [rsp+28h] [rbp-51h]
  int v45; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  struct IXMLDOMElement *v47; // [rsp+40h] [rbp-39h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+48h] [rbp-31h] BYREF
  HSTRING v49; // [rsp+50h] [rbp-29h] BYREF
  char *v50; // [rsp+58h] [rbp-21h] BYREF
  PWSTR ppszPathOut; // [rsp+60h] [rbp-19h] BYREF
  int v52; // [rsp+68h] [rbp-11h] BYREF
  int v53; // [rsp+6Ch] [rbp-Dh] BYREF
  __int64 *v54; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v55[32]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_DWORD *)a4 = 0;
  lpVtbl = a2->lpVtbl;
  v54 = 0;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 **))lpVtbl->get_childNodes)(a2, &v54);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v52 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v54 + 64))(v54, &v52);
    v10 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v44) = v13;
      v11 = "childNodes->get_length(&listLength)";
      v12 = 2164;
      goto LABEL_5;
    }
    for ( i = 0; (int)i < v52; ++i )
    {
      v48 = 0;
      v15 = *v54;
      v48 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v15 + 56))(v54, i, &v48);
      v10 = v16;
      if ( v16 < 0 )
      {
        LODWORD(v44) = v16;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x879,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
          "childNodes->get_item(nodeIndex, &node)",
          v44,
          v45);
        goto LABEL_34;
      }
      v47 = 0;
      wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v47);
      v17 = (**v48)(v48, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v47);
      v10 = v17;
      if ( v17 < 0 )
      {
        LODWORD(v44) = v17;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x87F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
          "node.query_to(&dllElement)",
          v44,
          v45);
        goto LABEL_32;
      }
      v50 = 0;
      v18 = v47->lpVtbl;
      v50 = 0;
      v19 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, char **))v18->get_baseName)(v47, &v50);
      v10 = v19;
      if ( v19 < 0 )
      {
        LODWORD(v44) = v19;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x882,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
          "dllElement->get_baseName(&elementName)",
          v44,
          v45);
        goto LABEL_30;
      }
      v20 = (unsigned __int16 *)v50;
      do
      {
        v21 = *(unsigned __int16 *)((char *)v20 + a3 - v50);
        v22 = *v20 - v21;
        if ( v22 )
          break;
        ++v20;
      }
      while ( v21 );
      if ( !v22 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v24 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
                v23,
                v47,
                L"ProcessorArchitecture",
                &string,
                0);
        v10 = v24;
        if ( v24 < 0 )
        {
          LODWORD(v44) = v24;
          v33 = "ParseAndRetrieveAttribute(dllElement.get(), Internal::PackagedComConstants::processorArchitectureAttribu"
                "te, architecture.GetAddressOf())";
          v34 = 2185;
LABEL_28:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
            v33,
            v44,
            v45);
          WindowsDeleteString(string);
          string = 0;
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
LABEL_32:
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v47);
LABEL_34:
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v48);
          goto LABEL_57;
        }
        v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v55, off_1802E0A70);
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                             (Microsoft::WRL::Wrappers::Details *)string,
                             *(HSTRING *)(v25 + 24),
                             v26) )
        {
          v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v55, off_1802E0A88);
          if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                               (Microsoft::WRL::Wrappers::Details *)string,
                               *(HSTRING *)(v27 + 24),
                               v28) )
          {
            v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v55, off_1802E0A78);
            if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                 (Microsoft::WRL::Wrappers::Details *)string,
                                 *(HSTRING *)(v29 + 24),
                                 v30) )
            {
              v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v55, off_1802E0A80);
              if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                   (Microsoft::WRL::Wrappers::Details *)string,
                                   *(HSTRING *)(v31 + 24),
                                   v32) )
              {
                v10 = -2146958844;
                LODWORD(v44) = -2146958844;
                v33 = "APPX_E_INVALID_MANIFEST";
                v34 = 2205;
                goto LABEL_28;
              }
              *(_DWORD *)a4 |= 8u;
            }
            else
            {
              *(_DWORD *)a4 |= 4u;
            }
          }
          else
          {
            *(_DWORD *)a4 |= 2u;
          }
        }
        else
        {
          *(_DWORD *)a4 |= 1u;
        }
        WindowsDeleteString(string);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v47);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v48);
    }
    if ( *(_DWORD *)a4 != 15 )
    {
      v49 = 0;
      LOBYTE(v45) = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v49,
        0);
      v36 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(
              v35,
              a2,
              (const unsigned __int16 *)&stru_180231CA8,
              &v49,
              (bool *)&v45);
      v10 = v36;
      if ( v36 < 0 )
      {
        LODWORD(v44) = v36;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x8A9,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
          "ParseAndRetrievePath(root, Internal::PackagedComConstants::pathAttribute, &relativePathUnspecifiedArchitecture, &pathFound)",
          v44,
          v45);
LABEL_38:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v49);
        goto LABEL_57;
      }
      if ( (_BYTE)v45 )
      {
        ppszPathOut = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszPathOut,
          0);
        WindowsGetStringRawBuffer(v49, 0);
        PackageRoot = OSIntegration::Package::GetPackageRoot(this[5]);
        v39 = PathAllocCombine(PackageRoot, v38, 1u, &ppszPathOut);
        v10 = v39;
        if ( v39 < 0 )
        {
          LODWORD(v44) = v39;
          v40 = "PathAllocCombine(_sourcePackage->GetPackageRoot(), wil::str_raw_ptr(relativePathUnspecifiedArchitecture)"
                ", PATHCCH_ALLOW_LONG_PATHS, &absolutePathUnspecifiedArchitecture)";
          v41 = 2224;
LABEL_42:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v41,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
            v40,
            v44,
            v45);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
          goto LABEL_38;
        }
        v53 = 0;
        ModuleArchitecture = CoGetModuleArchitecture(ppszPathOut, &v53);
        v10 = ModuleArchitecture;
        if ( ModuleArchitecture < 0 )
        {
          LODWORD(v44) = ModuleArchitecture;
          v40 = "CoGetModuleArchitecture( absolutePathUnspecifiedArchitecture.get(), &moduleArchitecture)";
          v41 = 2228;
          goto LABEL_42;
        }
        switch ( v53 )
        {
          case 332:
            *(_DWORD *)a4 |= 1u;
            break;
          case 448:
            *(_DWORD *)a4 |= 4u;
            break;
          case 34404:
            *(_DWORD *)a4 |= 2u;
            break;
          case 43620:
            *(_DWORD *)a4 |= 8u;
            break;
          default:
            v10 = -2146958844;
            LODWORD(v44) = -2146958844;
            v40 = "APPX_E_INVALID_MANIFEST";
            v41 = 2249;
            goto LABEL_42;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v49);
    }
    v10 = 0;
    goto LABEL_57;
  }
  LODWORD(v44) = v9;
  v11 = "root->get_childNodes(&childNodes)";
  v12 = 2161;
LABEL_5:
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths",
    v11,
    v44,
    v45);
LABEL_57:
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v54);
  return v10;
}

```

## disassembly

```asm
0x180165d30  mov     [rsp-8+arg_10], rbx
0x180165d35  push    rbp
0x180165d36  push    rsi
0x180165d37  push    rdi
0x180165d38  push    r12
0x180165d3a  push    r13
0x180165d3c  push    r14
0x180165d3e  push    r15
0x180165d40  lea     rbp, [rsp-27h]
0x180165d45  sub     rsp, 0A0h
0x180165d4c  mov     rax, cs:__security_cookie
0x180165d53  xor     rax, rsp
0x180165d56  mov     [rbp+57h+var_38], rax
0x180165d5a  mov     rbx, r9
0x180165d5d  mov     r15, r8
0x180165d60  mov     r14, rdx
0x180165d63  mov     r13, rcx
0x180165d66  xor     r12d, r12d
0x180165d69  mov     [r9], r12d
0x180165d6c  mov     rax, [rdx]
0x180165d6f  mov     [rbp+57h+var_60], r12
0x180165d73  lea     rdx, [rbp+57h+var_60]
0x180165d77  mov     rcx, r14
0x180165d7a  mov     rax, [rax+60h]
0x180165d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165d83  mov     edi, eax
0x180165d85  test    eax, eax
0x180165d87  jns     short loc_180165D9B
0x180165d89  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180165d8d  lea     rax, aRootGetChildno_3; "root->get_childNodes(&childNodes)"
0x180165d94  mov     edx, 871h
0x180165d99  jmp     short loc_180165DC9
0x180165d9b  mov     [rbp+57h+var_68], r12d
0x180165d9f  mov     rcx, [rbp+57h+var_60]
0x180165da3  mov     rax, [rcx]
0x180165da6  lea     rdx, [rbp+57h+var_68]
0x180165daa  mov     rax, [rax+40h]
0x180165dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165db3  mov     edi, eax
0x180165db5  test    eax, eax
0x180165db7  jns     short loc_180165DEA
0x180165db9  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180165dbd  lea     rax, aChildnodesGetL; "childNodes->get_length(&listLength)"
0x180165dc4  mov     edx, 874h; void *
0x180165dc9  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180165dd0  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x180165dd7  mov     [rsp+0D0h+var_B0], rax; char *
0x180165ddc  mov     rcx, [rbp+5Fh]; this
0x180165de0  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180165de5  jmp     loc_18016621B
0x180165dea  mov     esi, r12d
0x180165ded  cmp     esi, [rbp+57h+var_68]
0x180165df0  jge     loc_180166095
0x180165df6  mov     [rbp+57h+var_88], r12
0x180165dfa  mov     rcx, [rbp+57h+var_60]
0x180165dfe  mov     rax, [rcx]
0x180165e01  mov     [rbp+57h+var_88], r12
0x180165e05  lea     r8, [rbp+57h+var_88]
0x180165e09  mov     edx, esi
0x180165e0b  mov     rax, [rax+38h]
0x180165e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165e14  mov     edi, eax
0x180165e16  test    eax, eax
0x180165e18  js      loc_18016605A
0x180165e1e  mov     [rbp+57h+var_90], r12
0x180165e22  lea     rcx, [rbp+57h+var_90]
0x180165e26  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x180165e2b  mov     rcx, [rbp+57h+var_88]
0x180165e2f  mov     rax, [rcx]
0x180165e32  lea     r8, [rbp+57h+var_90]
0x180165e36  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180165e3d  mov     rax, [rax]
0x180165e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165e45  mov     edi, eax
0x180165e47  test    eax, eax
0x180165e49  js      loc_180166022
0x180165e4f  mov     [rbp+57h+var_78], r12
0x180165e53  mov     rcx, [rbp+57h+var_90]
0x180165e57  mov     rax, [rcx]
0x180165e5a  mov     [rbp+57h+var_78], r12
0x180165e5e  lea     rdx, [rbp+57h+var_78]
0x180165e62  mov     rax, [rax+148h]
0x180165e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165e6e  mov     edi, eax
0x180165e70  test    eax, eax
0x180165e72  js      loc_180165FEA
0x180165e78  mov     rax, [rbp+57h+var_78]
0x180165e7c  mov     r8, r15
0x180165e7f  sub     r8, rax
0x180165e82  movzx   ecx, word ptr [rax]
0x180165e85  movzx   edx, word ptr [rax+r8]
0x180165e8a  sub     ecx, edx
0x180165e8c  jnz     short loc_180165E96
0x180165e8e  add     rax, 2
0x180165e92  test    edx, edx
0x180165e94  jnz     short loc_180165E82
0x180165e96  test    ecx, ecx
0x180165e98  jnz     loc_180165F72
0x180165e9e  mov     [rbp+57h+string], r12
0x180165ea2  xor     ecx, ecx; string
0x180165ea4  call    cs:__imp_WindowsDeleteString
0x180165eaa  mov     [rbp+57h+string], r12
0x180165eae  mov     [rsp+0D0h+var_B0], r12; bool *
0x180165eb3  lea     r9, [rbp+57h+string]; HSTRING *
0x180165eb7  lea     r8, aProcessorarchi; "ProcessorArchitecture"
0x180165ebe  mov     rdx, [rbp+57h+var_90]; struct IXMLDOMElement *
0x180165ec2  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x180165ec7  mov     edi, eax
0x180165ec9  test    eax, eax
0x180165ecb  js      loc_180165FAD
0x180165ed1  lea     rdx, off_1802E0A70; "x86"
0x180165ed8  lea     rcx, [rbp+57h+var_58]
0x180165edc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180165ee1  mov     rdx, [rax+18h]; HSTRING
0x180165ee5  mov     rcx, [rbp+57h+string]; this
0x180165ee9  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180165eee  test    eax, eax
0x180165ef0  jnz     short loc_180165EF7
0x180165ef2  or      dword ptr [rbx], 1
0x180165ef5  jmp     short loc_180165F67
0x180165ef7  lea     rdx, off_1802E0A88; "x64"
0x180165efe  lea     rcx, [rbp+57h+var_58]
0x180165f02  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180165f07  mov     rdx, [rax+18h]; HSTRING
0x180165f0b  mov     rcx, [rbp+57h+string]; this
0x180165f0f  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180165f14  test    eax, eax
0x180165f16  jnz     short loc_180165F1D
0x180165f18  or      dword ptr [rbx], 2
0x180165f1b  jmp     short loc_180165F67
0x180165f1d  lea     rdx, off_1802E0A78; "arm"
0x180165f24  lea     rcx, [rbp+57h+var_58]
0x180165f28  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180165f2d  mov     rdx, [rax+18h]; HSTRING
0x180165f31  mov     rcx, [rbp+57h+string]; this
0x180165f35  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180165f3a  test    eax, eax
0x180165f3c  jnz     short loc_180165F43
0x180165f3e  or      dword ptr [rbx], 4
0x180165f41  jmp     short loc_180165F67
0x180165f43  lea     rdx, off_1802E0A80; "arm64"
0x180165f4a  lea     rcx, [rbp+57h+var_58]
0x180165f4e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180165f53  mov     rdx, [rax+18h]; HSTRING
0x180165f57  mov     rcx, [rbp+57h+string]; this
0x180165f5b  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180165f60  test    eax, eax
0x180165f62  jnz     short loc_180165F96
0x180165f64  or      dword ptr [rbx], 8
0x180165f67  mov     rcx, [rbp+57h+string]; string
0x180165f6b  call    cs:__imp_WindowsDeleteString
0x180165f71  nop
0x180165f72  lea     rcx, [rbp+57h+var_78]
0x180165f76  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180165f7b  nop
0x180165f7c  lea     rcx, [rbp+57h+var_90]
0x180165f80  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180165f85  nop
0x180165f86  lea     rcx, [rbp+57h+var_88]
0x180165f8a  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180165f8f  inc     esi
0x180165f91  jmp     loc_180165DED
0x180165f96  mov     edi, 80080204h
0x180165f9b  mov     dword ptr [rsp+0D0h+var_A8], edi
0x180165f9f  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x180165fa6  mov     edx, 89Dh
0x180165fab  jmp     short loc_180165FBD
0x180165fad  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180165fb1  lea     rax, aParseandretrie_22; "ParseAndRetrieveAttribute(dllElement.ge"...
0x180165fb8  mov     edx, 889h; void *
0x180165fbd  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180165fc4  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x180165fcb  mov     [rsp+0D0h+var_B0], rax; char *
0x180165fd0  mov     rcx, [rbp+5Fh]; this
0x180165fd4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180165fd9  nop
0x180165fda  mov     rcx, [rbp+57h+string]; string
0x180165fde  call    cs:__imp_WindowsDeleteString
0x180165fe4  mov     [rbp+57h+string], r12
0x180165fe8  jmp     short loc_180166017
0x180165fea  mov     rcx, [rbp+5Fh]; this
0x180165fee  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180165ff2  lea     rax, aDllelementGetB; "dllElement->get_baseName(&elementName)"
0x180165ff9  mov     [rsp+0D0h+var_B0], rax; char *
0x180165ffe  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x180166005  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016600c  mov     edx, 882h; void *
0x180166011  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166016  nop
0x180166017  lea     rcx, [rbp+57h+var_78]
0x18016601b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180166020  jmp     short loc_18016604F
0x180166022  mov     rcx, [rbp+5Fh]; this
0x180166026  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x18016602a  lea     rax, aNodeQueryToDll; "node.query_to(&dllElement)"
0x180166031  mov     [rsp+0D0h+var_B0], rax; char *
0x180166036  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x18016603d  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180166044  mov     edx, 87Fh; void *
0x180166049  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016604e  nop
0x18016604f  lea     rcx, [rbp+57h+var_90]
0x180166053  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180166058  jmp     short loc_180166087
0x18016605a  mov     rcx, [rbp+5Fh]; this
0x18016605e  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x180166062  lea     rax, aChildnodesGetI; "childNodes->get_item(nodeIndex, &node)"
0x180166069  mov     [rsp+0D0h+var_B0], rax; char *
0x18016606e  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x180166075  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016607c  mov     edx, 879h; void *
0x180166081  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166086  nop
0x180166087  lea     rcx, [rbp+57h+var_88]
0x18016608b  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180166090  jmp     loc_18016621B
0x180166095  cmp     dword ptr [rbx], 0Fh
0x180166098  jz      loc_180166218
0x18016609e  mov     [rbp+57h+var_80], r12
0x1801660a2  mov     byte ptr [rbp+57h+var_A0], r12b
0x1801660a6  xor     edx, edx
0x1801660a8  lea     rcx, [rbp+57h+var_80]
0x1801660ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801660b1  lea     rax, [rbp+57h+var_A0]
0x1801660b5  mov     [rsp+0D0h+var_B0], rax; bool *
0x1801660ba  lea     r9, [rbp+57h+var_80]; HSTRING *
0x1801660be  lea     r8, stru_180231CA8; unsigned __int16 *
0x1801660c5  mov     rdx, r14; struct IXMLDOMElement *
0x1801660c8  call    ?ParseAndRetrievePath@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1801660cd  mov     edi, eax
0x1801660cf  test    eax, eax
0x1801660d1  jns     short loc_18016610E
0x1801660d3  mov     rcx, [rbp+5Fh]; this
0x1801660d7  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x1801660db  lea     rax, aParseandretrie_27; "ParseAndRetrievePath(root, Internal::Pa"...
0x1801660e2  mov     [rsp+0D0h+var_B0], rax; char *
0x1801660e7  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x1801660ee  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801660f5  mov     edx, 8A9h; void *
0x1801660fa  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801660ff  nop
0x180166100  lea     rcx, [rbp+57h+var_80]
0x180166104  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180166109  jmp     loc_18016621B
0x18016610e  cmp     byte ptr [rbp+57h+var_A0], r12b
0x180166112  jz      loc_18016620F
0x180166118  mov     [rbp+57h+ppszPathOut], r12
0x18016611c  xor     edx, edx
0x18016611e  lea     rcx, [rbp+57h+ppszPathOut]
0x180166122  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180166127  xor     edx, edx; length
0x180166129  mov     rcx, [rbp+57h+var_80]; string
0x18016612d  call    cs:__imp_WindowsGetStringRawBuffer
0x180166133  mov     rdx, rax
0x180166136  mov     rcx, [r13+28h]; this
0x18016613a  call    ?GetPackageRoot@Package@OSIntegration@@QEBAPEAGXZ; OSIntegration::Package::GetPackageRoot(void)
0x18016613f  lea     r9, [rbp+57h+ppszPathOut]; ppszPathOut
0x180166143  mov     r8d, 1; dwFlags
0x180166149  mov     rcx, rax; pszPathIn
0x18016614c  call    cs:__imp_PathAllocCombine
0x180166152  mov     edi, eax
0x180166154  test    eax, eax
0x180166156  jns     short loc_180166192
0x180166158  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x18016615c  lea     rax, aPathalloccombi_2; "PathAllocCombine(_sourcePackage->GetPac"...
0x180166163  mov     edx, 8B0h; void *
0x180166168  mov     rcx, [rbp+5Fh]; this
0x18016616c  mov     [rsp+0D0h+var_B0], rax; char *
0x180166171  lea     r9, aOsintegrationD_96; "OSIntegration::DEH::PackagedComExtensio"...
0x180166178  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016617f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180166184  lea     rcx, [rbp+57h+ppszPathOut]
0x180166188  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18016618d  jmp     loc_180166100
0x180166192  mov     [rbp+57h+var_64], r12d
0x180166196  lea     rdx, [rbp+57h+var_64]
0x18016619a  mov     rcx, [rbp+57h+ppszPathOut]
0x18016619e  call    cs:__imp_CoGetModuleArchitecture
0x1801661a4  mov     edi, eax
0x1801661a6  test    eax, eax
0x1801661a8  jns     short loc_1801661BC
0x1801661aa  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1801661ae  lea     rax, aCogetmodulearc_1; "CoGetModuleArchitecture( absolutePathUn"...
0x1801661b5  mov     edx, 8B4h
0x1801661ba  jmp     short loc_180166168
0x1801661bc  mov     eax, [rbp+57h+var_64]
0x1801661bf  sub     eax, 14Ch
0x1801661c4  jz      short loc_180166202
0x1801661c6  sub     eax, 74h ; 't'
0x1801661c9  jz      short loc_1801661FD
0x1801661cb  sub     eax, 84A4h
0x1801661d0  jz      short loc_1801661F8
0x1801661d2  cmp     eax, 2400h
0x1801661d7  jz      short loc_1801661F3
0x1801661d9  mov     edi, 80080204h
0x1801661de  mov     dword ptr [rsp+0D0h+var_A8], edi
0x1801661e2  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1801661e9  mov     edx, 8C9h
0x1801661ee  jmp     loc_180166168
0x1801661f3  or      dword ptr [rbx], 8
  ... truncated ...
```
