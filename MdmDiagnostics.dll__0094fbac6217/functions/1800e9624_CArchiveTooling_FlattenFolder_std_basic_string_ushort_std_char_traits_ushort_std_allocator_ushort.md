# CArchiveTooling::FlattenFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800e9624`
- end: `0x1800e9e57`
- name: `?FlattenFolder@CArchiveTooling@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2099`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f21ac`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e7aa8`
- `0x1800e7bac`
- `0x1800e7e80`
- `0x1800e8f70`
- `0x1800e9624`
- `0x1800ece5c`
- `0x1800ef134`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x1800f0a00`
- `0x1800f1218`
- `0x1801189ec`
- `0x180118a64`
- `0x18011b8fc`
- `0x18011ca44`
- `0x18011ce80`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800e9b89`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800e9b89`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e978b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e978b`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9b48`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9b48`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9779`
- `OLEAUT32!__imp_VariantClear` at `0x1800e97ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9b96`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9779`
- `OLEAUT32!__imp_VariantClear` at `0x1800e97ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9b96`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e96fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e96fd`

## string_xrefs

- `0x1800e9746`: `results.xml`
- `0x1800e9713`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9ada`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9b2a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9b72`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9df1`: `FlattenFolder: Unable to create HRESULT string. Folder will not be flattened.`
- `0x1800e97f9`: `FlattenFolder: Error loading results.xml from: `
- `0x1800e9867`: `FlattenFolder: Error getting root element in results.xml from `
- `0x1800e98d2`: `FlattenFolder: Error getting first child element in results.xml from `
- `0x1800e9963`: `FlattenFolder: Error selecting Collection child nodes in results.xml from `
- `0x1800e9dc9`: `FlattenFolder: Results.xml in `
- `0x1800e9c9b`: `FlattenFolder: Folder flattening aborted due to invalid XML in results.xml. Error parsing XML document in results.xml from `
- `0x1800e9c92`: `FlattenFolder: Folder flattening aborted due to an error iterating node names in results.xml. Error getting node name in results.xml from `
- `0x1800e9c2f`: `FlattenFolder: Folder flattening aborted due to an error iterating node values in results.xml. Error getting node value in results.xml from `

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CArchiveTooling::FlattenFolder(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // r12d
  const unsigned __int16 *v4; // rax
  TelemetryWriter *v5; // rcx
  int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // r13d
  HRESULT v10; // eax
  LPVOID v11; // rsi
  __int64 v12; // r15
  const OLECHAR *v13; // rdi
  const unsigned __int16 *v14; // rax
  TelemetryWriter *v15; // rcx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rax
  TelemetryWriter *v18; // rcx
  __int64 v19; // rax
  const unsigned __int16 *v20; // rax
  TelemetryWriter *v21; // rcx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, __int64 **); // rdi
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  const unsigned __int16 *v26; // rax
  TelemetryWriter *v27; // rcx
  int v28; // ecx
  unsigned int i; // r15d
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rdi
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rdi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD **); // rsi
  _QWORD *v37; // rdx
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  int v42; // edi
  int v43; // eax
  char v44; // al
  int v45; // ecx
  const wchar_t *v46; // rdx
  const unsigned __int16 *v47; // rax
  TelemetryWriter *v48; // rcx
  const unsigned __int16 *v49; // rax
  TelemetryWriter *v50; // rcx
  unsigned int v52; // ebx
  const unsigned __int16 *v53; // rax
  TelemetryWriter *v54; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v56; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v57; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v61[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD *v63; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG *v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v69; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v70[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-18h]
  _BYTE v72[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v73[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v74[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v75[336]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v71 = a1;
  std::wstring::wstring(v72);
  wil::make_bstr_nothrow(&v67, L"HRESULT");
  v2 = v67;
  v3 = 0;
  if ( v67 )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      std::wstring::append(v72, L"FlattenFolder: OutputFolder cannot be empty. Folder will not be flattened.");
      v4 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v5, v4);
      v6 = -2147418113;
LABEL_51:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(a1);
      return (unsigned int)v6;
    }
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v8 = std::wstring::wstring(&v69, v7);
    FlattenOutputFolder::FlattenOutputFolder(v75, v8);
    v56 = 0;
    v9 = 1;
    v10 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &v56);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
        (const char *)(unsigned int)v10,
        ppv);
LABEL_50:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v56);
      FlattenOutputFolder::~FlattenOutputFolder((FlattenOutputFolder *)v75);
      goto LABEL_51;
    }
    std::wstring::wstring(v73, a1);
    std::wstring::append(v73, L"\\");
    std::wstring::append(v73, L"results.xml");
    v61[0] = 0;
    v11 = v56;
    v12 = *(_QWORD *)v56;
    v13 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v13);
    if ( !pvarg.llVal && v13 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v69 = pvarg;
    v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, _WORD *))(v12 + 464))(v11, &v69, v61);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error loading results.xml from: ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v15, v14, v6);
LABEL_49:
      std::wstring::_Tidy_deallocate(v73);
      goto LABEL_50;
    }
    v57 = 0;
    v16 = *(_QWORD *)v56;
    v57 = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(v16 + 360))(v56, &v57);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error getting root element in results.xml from ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v18, v17, v6);
LABEL_48:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v57);
      goto LABEL_49;
    }
    v59 = 0;
    v19 = *v57;
    v59 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 104))(v57, &v59);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error getting first child element in results.xml from ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v21, v20, v6);
LABEL_47:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v59);
      goto LABEL_48;
    }
    std::wstring::wstring(v74, L"/Collection/*");
    v58 = 0;
    v22 = v59;
    v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v59 + 288LL);
    v58 = 0;
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
    v6 = v23(v22, v24, &v58);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error selecting Collection child nodes in results.xml from ");
      std::wstring::append(v72, a1);
      v25 = L".Folder flattening aborted.Error : ";
      goto LABEL_17;
    }
    v62 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v58 + 64))(v58, &v62);
    if ( v6 < 0 || (v28 = v62) == 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Results.xml in ");
      std::wstring::append(v72, a1);
      v25 = L" contains zero nodes. There are no folders to flatten. Folder flattening aborted. Error: ";
LABEL_17:
      std::wstring::append(v72, v25);
      v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v27, v26, v6);
LABEL_46:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v58);
      std::wstring::_Tidy_deallocate(v74);
      goto LABEL_47;
    }
    for ( i = 0; (int)i < v28; ++i )
    {
      v60 = 0;
      v30 = *v58;
      v60 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v30 + 56))(v58, i, &v60);
      if ( v6 < 0 )
      {
        std::wstring::append(
          v72,
          L"FlattenFolder: Folder flattening aborted due to invalid XML in results.xml. Error parsing XML document in results.xml from ");
        std::wstring::append(v72, a1);
        std::wstring::append(v72, L". Error: ");
        v49 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
        TelemetryWriter::Write(v50, v49, v6);
        goto LABEL_45;
      }
      v66 = 0;
      v65 = 0;
      v63 = 0;
      v31 = v60;
      v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 56LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v66,
        0);
      v6 = v32(v31, &v66);
      if ( v6 < 0 )
      {
        v46 = L"FlattenFolder: Folder flattening aborted due to an error iterating node names in results.xml. Error gettin"
               "g node name in results.xml from ";
LABEL_42:
        std::wstring::append(v72, v46);
        std::wstring::append(v72, a1);
        std::wstring::append(v72, L". Error: ");
        v47 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
        TelemetryWriter::Write(v48, v47, v6);
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v63);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
LABEL_45:
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v60);
        goto LABEL_46;
      }
      v33 = v60;
      v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 208LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v65,
        0);
      v6 = v34(v33, &v65);
      if ( v6 < 0 )
      {
        v46 = L"FlattenFolder: Folder flattening aborted due to an error iterating node values in results.xml. Error getti"
               "ng node value in results.xml from ";
        goto LABEL_42;
      }
      v35 = v60;
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v60 + 136LL);
      v37 = v63;
      v63 = 0;
      if ( v37 )
        (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
      v38 = v36(v35, &v63);
      if ( v38 >= 0 )
      {
        if ( v63 )
        {
          v64 = 0;
          v39 = *v63;
          v64 = 0;
          v40 = (*(__int64 (__fastcall **)(_QWORD *, __int64, VARIANTARG **))(v39 + 56))(v63, v2, &v64);
          if ( v40 >= 0 )
          {
            if ( v64 )
            {
              VariantInit(&pvarg);
              v41 = (*(__int64 (__fastcall **)(VARIANTARG *, VARIANTARG *))(*(_QWORD *)&v64->vt + 64LL))(v64, &pvarg);
              if ( v41 >= 0 )
                v3 = _o__wtol(pvarg.llVal);
              else
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x33C,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
                  (const char *)(unsigned int)v41,
                  ppv);
              VariantClear(&pvarg);
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x338,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
              (const char *)(unsigned int)v40,
              ppv);
          }
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v64);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x334,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
          (const char *)(unsigned int)v38,
          ppv);
      }
      v64 = &v69;
      v42 = std::wstring::wstring(&v69, v65);
      v43 = std::wstring::wstring(v70, v66);
      v44 = FlattenOutputFolder::ProcessDirectiveNode((unsigned int)v75, v9, v43, v42, v3);
      v45 = v9 + 1;
      if ( v44 != 1 )
        v45 = v9;
      v9 = v45;
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v63);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v60);
      v28 = v62;
      v3 = 0;
    }
    v52 = FlattenOutputFolder::PerformFolderFlattening((FlattenOutputFolder *)v75);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v58);
    std::wstring::_Tidy_deallocate(v74);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v59);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v57);
    std::wstring::_Tidy_deallocate(v73);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v56);
    FlattenOutputFolder::~FlattenOutputFolder((FlattenOutputFolder *)v75);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(a1);
    return v52;
  }
  else
  {
    std::wstring::append(v72, L"FlattenFolder: Unable to create HRESULT string. Folder will not be flattened.");
    v53 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
    TelemetryWriter::Write(v54, v53);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(a1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800e9624  push    rbp
0x1800e9626  push    rbx
0x1800e9627  push    rsi
0x1800e9628  push    rdi
0x1800e9629  push    r12
0x1800e962b  push    r13
0x1800e962d  push    r14
0x1800e962f  push    r15
0x1800e9631  lea     rbp, [rsp-1B8h]
0x1800e9639  sub     rsp, 2B8h
0x1800e9640  mov     rax, cs:__security_cookie
0x1800e9647  xor     rax, rsp
0x1800e964a  mov     [rbp+1F0h+var_50], rax
0x1800e9651  mov     r14, rcx
0x1800e9654  mov     [rbp+1F0h+var_208], rcx
0x1800e9658  lea     rcx, [rbp+1F0h+var_200]
0x1800e965c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e9661  nop
0x1800e9662  lea     rdx, aHresult; "HRESULT"
0x1800e9669  lea     rcx, [rbp+1F0h+var_270]
0x1800e966d  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800e9672  nop
0x1800e9673  mov     rbx, [rbp+1F0h+var_270]
0x1800e9677  xor     r12d, r12d
0x1800e967a  test    rbx, rbx
0x1800e967d  jz      loc_1800E9DF1
0x1800e9683  cmp     [r14+10h], r12
0x1800e9687  jnz     short loc_1800E96B4
0x1800e9689  lea     rdx, aFlattenfolderO; "FlattenFolder: OutputFolder cannot be e"...
0x1800e9690  lea     rcx, [rbp+1F0h+var_200]
0x1800e9694  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9699  lea     rcx, [rbp+1F0h+var_200]
0x1800e969d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e96a2  mov     rdx, rax; unsigned __int16 *
0x1800e96a5  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x1800e96aa  mov     edi, 8000FFFFh
0x1800e96af  jmp     loc_1800E9D31
0x1800e96b4  mov     rcx, r14
0x1800e96b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e96bc  mov     rdx, rax
0x1800e96bf  lea     rcx, [rbp+1F0h+var_250]
0x1800e96c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e96c8  mov     rdx, rax
0x1800e96cb  lea     rcx, [rbp+1F0h+var_1A0]
0x1800e96cf  call    ??0FlattenOutputFolder@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FlattenOutputFolder::FlattenOutputFolder(std::wstring)
0x1800e96d4  nop
0x1800e96d5  mov     [rsp+2F0h+var_2C0], r12
0x1800e96da  lea     rax, [rsp+2F0h+var_2C0]
0x1800e96df  mov     qword ptr [rsp+2F0h+ppv], rax; int
0x1800e96e4  lea     r9, IID_IXMLDOMDocument; riid
0x1800e96eb  mov     r13d, 1
0x1800e96f1  mov     r8d, r13d; dwClsContext
0x1800e96f4  xor     edx, edx; pUnkOuter
0x1800e96f6  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800e96fd  call    cs:__imp_CoCreateInstance
0x1800e9703  mov     edi, eax
0x1800e9705  test    eax, eax
0x1800e9707  jns     short loc_1800E9729
0x1800e9709  mov     rcx, [rbp+1F8h]; this
0x1800e9710  mov     r9d, eax; char *
0x1800e9713  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800e971a  mov     edx, 2C8h; void *
0x1800e971f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9724  jmp     loc_1800E9D1C
0x1800e9729  mov     rdx, r14
0x1800e972c  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9730  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e9735  nop
0x1800e9736  lea     rdx, psz; "\\"
0x1800e973d  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9741  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9746  lea     rdx, aResultsXml; "results.xml"
0x1800e974d  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9751  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9756  mov     [rsp+2F0h+var_298], r12w
0x1800e975c  mov     rsi, [rsp+2F0h+var_2C0]
0x1800e9761  mov     r15, [rsi]
0x1800e9764  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9768  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e976d  mov     rdi, rax
0x1800e9770  mov     word ptr [rbp+1F0h+pvarg], r12w
0x1800e9775  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x1800e9779  call    cs:__imp_VariantClear
0x1800e977f  mov     eax, 8
0x1800e9784  mov     word ptr [rbp+1F0h+pvarg], ax
0x1800e9788  mov     rcx, rdi; psz
0x1800e978b  call    cs:__imp_SysAllocString
0x1800e9791  mov     dword ptr [rbp+1F0h+pvarg+8], eax
0x1800e9794  mov     rcx, rax
0x1800e9797  sar     rcx, 20h
0x1800e979b  mov     dword ptr [rbp+1F0h+pvarg+0Ch], ecx
0x1800e979e  test    rax, rax
0x1800e97a1  jnz     short loc_1800E97BF
0x1800e97a3  test    rdi, rdi
0x1800e97a6  jz      short loc_1800E97BF
0x1800e97a8  mov     eax, 0Ah
0x1800e97ad  mov     word ptr [rbp+1F0h+pvarg], ax
0x1800e97b1  mov     ecx, 8007000Eh; int
0x1800e97b6  mov     dword ptr [rbp+1F0h+pvarg+8], ecx
0x1800e97b9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800e97bf  movups  xmm0, xmmword ptr [rbp+1F0h+pvarg]
0x1800e97c3  movaps  [rbp+1F0h+var_250], xmm0
0x1800e97c7  movsd   xmm1, qword ptr [rbp+1F0h+pvarg+10h]
0x1800e97cc  movsd   [rbp+1F0h+var_240], xmm1
0x1800e97d1  lea     r8, [rsp+2F0h+var_298]
0x1800e97d6  lea     rdx, [rbp+1F0h+var_250]
0x1800e97da  mov     rcx, rsi
0x1800e97dd  mov     rax, [r15+1D0h]
0x1800e97e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e97e9  mov     edi, eax
0x1800e97eb  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x1800e97ef  call    cs:__imp_VariantClear
0x1800e97f5  test    edi, edi
0x1800e97f7  jns     short loc_1800E983E
0x1800e97f9  lea     rdx, aFlattenfolderE; "FlattenFolder: Error loading results.xm"...
0x1800e9800  lea     rcx, [rbp+1F0h+var_200]
0x1800e9804  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9809  mov     rdx, r14
0x1800e980c  lea     rcx, [rbp+1F0h+var_200]
0x1800e9810  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9815  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e981c  lea     rcx, [rbp+1F0h+var_200]
0x1800e9820  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9825  lea     rcx, [rbp+1F0h+var_200]
0x1800e9829  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e982e  mov     rdx, rax; unsigned __int16 *
0x1800e9831  mov     r8d, edi; int
0x1800e9834  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9839  jmp     loc_1800E9D12
0x1800e983e  mov     [rsp+2F0h+var_2B8], r12
0x1800e9843  mov     rcx, [rsp+2F0h+var_2C0]
0x1800e9848  mov     rax, [rcx]
0x1800e984b  mov     [rsp+2F0h+var_2B8], r12
0x1800e9850  lea     rdx, [rsp+2F0h+var_2B8]
0x1800e9855  mov     rax, [rax+168h]
0x1800e985c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9861  mov     edi, eax
0x1800e9863  test    eax, eax
0x1800e9865  jns     short loc_1800E98AC
0x1800e9867  lea     rdx, aFlattenfolderE_0; "FlattenFolder: Error getting root eleme"...
0x1800e986e  lea     rcx, [rbp+1F0h+var_200]
0x1800e9872  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9877  mov     rdx, r14
0x1800e987a  lea     rcx, [rbp+1F0h+var_200]
0x1800e987e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9883  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e988a  lea     rcx, [rbp+1F0h+var_200]
0x1800e988e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9893  lea     rcx, [rbp+1F0h+var_200]
0x1800e9897  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e989c  mov     rdx, rax; unsigned __int16 *
0x1800e989f  mov     r8d, edi; int
0x1800e98a2  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e98a7  jmp     loc_1800E9D07
0x1800e98ac  mov     [rsp+2F0h+var_2A8], r12
0x1800e98b1  mov     rcx, [rsp+2F0h+var_2B8]
0x1800e98b6  mov     rax, [rcx]
0x1800e98b9  mov     [rsp+2F0h+var_2A8], r12
0x1800e98be  lea     rdx, [rsp+2F0h+var_2A8]
0x1800e98c3  mov     rax, [rax+68h]
0x1800e98c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e98cc  mov     edi, eax
0x1800e98ce  test    eax, eax
0x1800e98d0  jns     short loc_1800E9917
0x1800e98d2  lea     rdx, aFlattenfolderE_2; "FlattenFolder: Error getting first chil"...
0x1800e98d9  lea     rcx, [rbp+1F0h+var_200]
0x1800e98dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e98e2  mov     rdx, r14
0x1800e98e5  lea     rcx, [rbp+1F0h+var_200]
0x1800e98e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e98ee  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e98f5  lea     rcx, [rbp+1F0h+var_200]
0x1800e98f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e98fe  lea     rcx, [rbp+1F0h+var_200]
0x1800e9902  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9907  mov     rdx, rax; unsigned __int16 *
0x1800e990a  mov     r8d, edi; int
0x1800e990d  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9912  jmp     loc_1800E9CFC
0x1800e9917  lea     rdx, aCollection; "/Collection/*"
0x1800e991e  lea     rcx, [rbp+1F0h+var_1C0]
0x1800e9922  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e9927  nop
0x1800e9928  mov     [rsp+2F0h+var_2B0], r12
0x1800e992d  mov     rsi, [rsp+2F0h+var_2A8]
0x1800e9932  mov     rax, [rsi]
0x1800e9935  mov     rdi, [rax+120h]
0x1800e993c  mov     [rsp+2F0h+var_2B0], r12
0x1800e9941  lea     rcx, [rbp+1F0h+var_1C0]
0x1800e9945  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e994a  mov     rdx, rax
0x1800e994d  lea     r8, [rsp+2F0h+var_2B0]
0x1800e9952  mov     rcx, rsi
0x1800e9955  mov     rax, rdi
0x1800e9958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e995d  mov     edi, eax
0x1800e995f  test    eax, eax
0x1800e9961  jns     short loc_1800E99A8
0x1800e9963  lea     rdx, aFlattenfolderE_1; "FlattenFolder: Error selecting Collecti"...
0x1800e996a  lea     rcx, [rbp+1F0h+var_200]
0x1800e996e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9973  mov     rdx, r14
0x1800e9976  lea     rcx, [rbp+1F0h+var_200]
0x1800e997a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e997f  lea     rdx, aFolderFlatteni; ".Folder flattening aborted.Error : "
0x1800e9986  lea     rcx, [rbp+1F0h+var_200]
0x1800e998a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e998f  lea     rcx, [rbp+1F0h+var_200]
0x1800e9993  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9998  mov     rdx, rax; unsigned __int16 *
0x1800e999b  mov     r8d, edi; int
0x1800e999e  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e99a3  jmp     loc_1800E9CE7
0x1800e99a8  mov     [rsp+2F0h+var_294], r12d
0x1800e99ad  mov     rcx, [rsp+2F0h+var_2B0]
0x1800e99b2  mov     rax, [rcx]
0x1800e99b5  lea     rdx, [rsp+2F0h+var_294]
0x1800e99ba  mov     rax, [rax+40h]
0x1800e99be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e99c3  mov     edi, eax
0x1800e99c5  test    eax, eax
0x1800e99c7  js      loc_1800E9DC9
0x1800e99cd  mov     ecx, [rsp+2F0h+var_294]
0x1800e99d1  test    ecx, ecx
0x1800e99d3  jz      loc_1800E9DC9
0x1800e99d9  mov     r15d, r12d
0x1800e99dc  cmp     r15d, ecx
0x1800e99df  jge     loc_1800E9D54
0x1800e99e5  mov     [rsp+2F0h+var_2A0], r12
0x1800e99ea  mov     rcx, [rsp+2F0h+var_2B0]
0x1800e99ef  mov     rax, [rcx]
0x1800e99f2  mov     [rsp+2F0h+var_2A0], r12
0x1800e99f7  lea     r8, [rsp+2F0h+var_2A0]
0x1800e99fc  mov     edx, r15d
0x1800e99ff  mov     rax, [rax+38h]
0x1800e9a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9a08  mov     edi, eax
0x1800e9a0a  test    eax, eax
0x1800e9a0c  js      loc_1800E9C9B
0x1800e9a12  mov     [rsp+2F0h+var_278], r12
0x1800e9a17  mov     [rsp+2F0h+var_280], r12
0x1800e9a1c  mov     [rsp+2F0h+var_290], r12
0x1800e9a21  mov     rsi, [rsp+2F0h+var_2A0]
0x1800e9a26  mov     rax, [rsi]
0x1800e9a29  mov     rdi, [rax+38h]
0x1800e9a2d  xor     edx, edx
0x1800e9a2f  lea     rcx, [rsp+2F0h+var_278]
0x1800e9a34  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800e9a39  lea     rdx, [rsp+2F0h+var_278]
0x1800e9a3e  mov     rcx, rsi
0x1800e9a41  mov     rax, rdi
0x1800e9a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9a49  mov     edi, eax
0x1800e9a4b  test    eax, eax
0x1800e9a4d  js      loc_1800E9C92
0x1800e9a53  mov     rsi, [rsp+2F0h+var_2A0]
0x1800e9a58  mov     rax, [rsi]
0x1800e9a5b  mov     rdi, [rax+0D0h]
0x1800e9a62  xor     edx, edx
0x1800e9a64  lea     rcx, [rsp+2F0h+var_280]
0x1800e9a69  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800e9a6e  lea     rdx, [rsp+2F0h+var_280]
0x1800e9a73  mov     rcx, rsi
0x1800e9a76  mov     rax, rdi
0x1800e9a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9a7e  mov     edi, eax
0x1800e9a80  test    eax, eax
0x1800e9a82  js      loc_1800E9C2F
0x1800e9a88  mov     rdi, [rsp+2F0h+var_2A0]
0x1800e9a8d  mov     rax, [rdi]
0x1800e9a90  mov     rsi, [rax+88h]
0x1800e9a97  mov     rdx, [rsp+2F0h+var_290]
0x1800e9a9c  mov     [rsp+2F0h+var_290], 0
0x1800e9aa5  test    rdx, rdx
0x1800e9aa8  jz      short loc_1800E9ABA
0x1800e9aaa  mov     rcx, [rdx]
0x1800e9aad  mov     rax, [rcx+10h]
0x1800e9ab1  mov     rcx, rdx
0x1800e9ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9ab9  nop
0x1800e9aba  lea     rdx, [rsp+2F0h+var_290]
0x1800e9abf  mov     rcx, rdi
0x1800e9ac2  mov     rax, rsi
0x1800e9ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9aca  mov     rcx, [rbp+1F8h]; this
0x1800e9ad1  xor     edi, edi
0x1800e9ad3  test    eax, eax
0x1800e9ad5  jns     short loc_1800E9AF0
0x1800e9ad7  mov     r9d, eax; char *
0x1800e9ada  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800e9ae1  mov     edx, 334h; void *
0x1800e9ae6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e9aeb  jmp     loc_1800E9BA7
0x1800e9af0  mov     rcx, [rsp+2F0h+var_290]
0x1800e9af5  test    rcx, rcx
0x1800e9af8  jz      loc_1800E9BA7
0x1800e9afe  mov     [rsp+2F0h+var_288], rdi
0x1800e9b03  mov     rax, [rcx]
0x1800e9b06  mov     [rsp+2F0h+var_288], rdi
0x1800e9b0b  lea     r8, [rsp+2F0h+var_288]
  ... truncated ...
```
