# XmlBuilder::XmlBuilder(ConfigSettings const &,std::vector<File,std::allocator<File>>,ushort * *)

- ea: `0x18010ca00`
- end: `0x18010db23`
- name: `??0XmlBuilder@@QEAA@AEBVConfigSettings@@V?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@PEAPEAG@Z`
- size: `4387`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800629a0`

## callees

- `0x18000a39c`
- `0x18000ecac`
- `0x18001716c`
- `0x1800188f4`
- `0x180018a60`
- `0x180025190`
- `0x1800403ac`
- `0x1800404c4`
- `0x180043640`
- `0x180059920`
- `0x1800679f8`
- `0x18010ca00`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18010ca7b`
- `ole32!CoCreateInstance` at `0x18010ca7b`

## string_xrefs

- `0x18010d727`: `LowerCaseLongPath`
- `0x18010cdd4`: `CompanyName`
- `0x18010d594`: `LegalCopyright`
- `0x18010d60b`: `LinkDate`
- `0x18010da93`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010daa8`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010dabd`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010dad2`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010dae7`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010dafc`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010db11`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=67
__int64 __fastcall XmlBuilder::XmlBuilder(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HRESULT v7; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  const struct File *v16; // rsi
  const struct File *v17; // r15
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  LPVOID v22; // rcx
  LPVOID v23; // rcx
  LPVOID v24; // rcx
  LPVOID v25; // rcx
  LPVOID v26; // rcx
  wchar_t *v27; // rbx
  LPVOID v28; // rcx
  LPVOID v29; // rcx
  LPVOID v30; // rcx
  LPVOID v31; // rcx
  LPVOID v32; // rcx
  wchar_t *v33; // rbx
  LPVOID v34; // rcx
  wchar_t *v35; // rbx
  LPVOID v36; // rcx
  LPVOID v37; // rcx
  wchar_t *v38; // rbx
  LPVOID v39; // rcx
  wchar_t *v40; // rbx
  LPVOID v41; // rcx
  LPVOID v42; // rcx
  LPVOID v43; // rcx
  LPVOID v44; // rcx
  LPVOID v45; // rcx
  LPVOID v46; // rcx
  LPVOID v47; // rcx
  OLECHAR *v48; // rbx
  LPVOID v49; // rcx
  LPVOID v50; // rcx
  wchar_t *v51; // rbx
  LPVOID v52; // rcx
  wchar_t *v53; // rbx
  LPVOID v54; // rcx
  LPVOID v55; // rcx
  int v57; // [rsp+28h] [rbp-E0h]
  LPVOID ppv; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v61; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v62; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID v63; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v64; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v65; // [rsp+70h] [rbp-98h] BYREF
  __int64 v66; // [rsp+78h] [rbp-90h] BYREF
  LPVOID v67; // [rsp+80h] [rbp-88h] BYREF
  __int64 v68; // [rsp+88h] [rbp-80h] BYREF
  LPVOID v69; // [rsp+90h] [rbp-78h] BYREF
  __int64 v70; // [rsp+98h] [rbp-70h] BYREF
  LPVOID v71; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v73; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID v75; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-40h] BYREF
  LPVOID v77; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-30h] BYREF
  LPVOID v79; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v80; // [rsp+E8h] [rbp-20h] BYREF
  LPVOID v81; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v82; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID v83; // [rsp+100h] [rbp-8h] BYREF
  __int64 v84; // [rsp+108h] [rbp+0h] BYREF
  LPVOID v85; // [rsp+110h] [rbp+8h] BYREF
  __int64 v86; // [rsp+118h] [rbp+10h] BYREF
  LPVOID v87; // [rsp+120h] [rbp+18h] BYREF
  __int64 v88; // [rsp+128h] [rbp+20h] BYREF
  LPVOID v89; // [rsp+130h] [rbp+28h] BYREF
  __int64 v90; // [rsp+138h] [rbp+30h] BYREF
  LPVOID v91; // [rsp+140h] [rbp+38h] BYREF
  __int64 v92; // [rsp+148h] [rbp+40h] BYREF
  LPVOID v93; // [rsp+150h] [rbp+48h] BYREF
  __int64 v94; // [rsp+158h] [rbp+50h] BYREF
  LPVOID v95; // [rsp+160h] [rbp+58h] BYREF
  __int64 v96; // [rsp+168h] [rbp+60h] BYREF
  LPVOID v97; // [rsp+170h] [rbp+68h] BYREF
  __int64 v98; // [rsp+178h] [rbp+70h] BYREF
  LPVOID v99; // [rsp+180h] [rbp+78h] BYREF
  __int64 v100; // [rsp+188h] [rbp+80h] BYREF
  LPVOID v101; // [rsp+190h] [rbp+88h] BYREF
  __int64 v102; // [rsp+198h] [rbp+90h] BYREF
  LPVOID v103; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v104; // [rsp+1A8h] [rbp+A0h] BYREF
  LPVOID v105; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v106; // [rsp+1B8h] [rbp+B0h] BYREF
  LPVOID v107; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v108; // [rsp+1C8h] [rbp+C0h] BYREF
  LPVOID v109; // [rsp+1D0h] [rbp+C8h] BYREF
  __int64 v110; // [rsp+1D8h] [rbp+D0h] BYREF
  LPVOID v111; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v112; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v113[3]; // [rsp+1F0h] [rbp+E8h] BYREF
  OLECHAR v114[16]; // [rsp+208h] [rbp+100h] BYREF
  wchar_t v115[16]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v116[24]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v117[96]; // [rsp+260h] [rbp+158h] BYREF
  OLECHAR v118[16]; // [rsp+2C0h] [rbp+1B8h] BYREF
  OLECHAR v119[16]; // [rsp+2E0h] [rbp+1D8h] BYREF
  OLECHAR v120[16]; // [rsp+300h] [rbp+1F8h] BYREF
  OLECHAR v121[16]; // [rsp+320h] [rbp+218h] BYREF
  OLECHAR v122[16]; // [rsp+340h] [rbp+238h] BYREF
  OLECHAR v123[16]; // [rsp+360h] [rbp+258h] BYREF
  OLECHAR v124[16]; // [rsp+380h] [rbp+278h] BYREF
  OLECHAR v125[32]; // [rsp+3A0h] [rbp+298h] BYREF
  OLECHAR v126[32]; // [rsp+3E0h] [rbp+2D8h] BYREF
  OLECHAR v127[16]; // [rsp+420h] [rbp+318h] BYREF
  OLECHAR v128[16]; // [rsp+440h] [rbp+338h] BYREF
  OLECHAR v129[16]; // [rsp+460h] [rbp+358h] BYREF
  OLECHAR v130[16]; // [rsp+480h] [rbp+378h] BYREF
  OLECHAR v131[16]; // [rsp+4A0h] [rbp+398h] BYREF
  OLECHAR v132[48]; // [rsp+4C0h] [rbp+3B8h] BYREF
  int v133[14]; // [rsp+520h] [rbp+418h] BYREF
  __int64 v134; // [rsp+558h] [rbp+450h]
  unsigned int v135; // [rsp+568h] [rbp+460h]
  char v136; // [rsp+56Dh] [rbp+465h]
  wil::details::in1diag3 *retaddr; // [rsp+5C0h] [rbp+4B8h]

  v113[1] = -2;
  v113[2] = a3;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
  v7 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v7,
      v57);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  v61 = 0;
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v61);
  v10 = v9(v8, L"OrphanFiles", &v61);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v10,
      v57);
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 168LL))(ppv, v61, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v11,
      v57);
  v60 = 0;
  v12 = ppv;
  v13 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v60);
  v14 = v13(v12, L"Files", &v60);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v14,
      v57);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v61 + 168LL))(v61, v60, 0);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v15,
      v57);
  v16 = *(const struct File **)a3;
  v17 = *(const struct File **)(a3 + 8);
  while ( v16 != v17 )
  {
    File::File((File *)v116, v16);
    if ( !v136 )
    {
      v59 = 0;
      v18 = ppv;
      v19 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v59);
      v20 = v19(v18, L"File", &v59);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x136,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
          (const char *)(unsigned int)v20,
          v57);
      v21 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v60 + 168LL))(v60, v59, 0);
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
          (const char *)(unsigned int)v21,
          v57);
      std::wstring::wstring(v115, L"Id");
      v62 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v22 = ppv;
      v63 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v22, (__int64 *)&v63, &v62, v115, v118);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v115, L"Name");
      v64 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v23 = ppv;
      v65 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v23, (__int64 *)&v65, &v64, v115, v121);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v115, L"ProductName");
      v66 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v24 = ppv;
      v67 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v24, (__int64 *)&v67, &v66, v115, v124);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v115, L"CompanyName");
      v68 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v25 = ppv;
      v69 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v25, (__int64 *)&v69, &v68, v115, v123);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v115, L"ProductVersion");
      v70 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v26 = ppv;
      v71 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v26, (__int64 *)&v71, &v70, v115, v125);
      std::wstring::~wstring(v115);
      v27 = Utility::FormatWstring(v114, L"%u", v135);
      std::wstring::wstring(v115, L"VerLanguage");
      v72 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v28 = ppv;
      v73 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v28, (__int64 *)&v73, &v72, v115, v27);
      std::wstring::~wstring(v115);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"0");
      std::wstring::wstring(v115, L"SwitchBackContext");
      v74 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v29 = ppv;
      v75 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v29, (__int64 *)&v75, &v74, v115, v114);
      std::wstring::~wstring(v115);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"FileVersion");
      v76 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v30 = ppv;
      v77 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v30, (__int64 *)&v77, &v76, v114, v122);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"OriginalFileName");
      v78 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v31 = ppv;
      v79 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v31, (__int64 *)&v79, &v78, v114, v129);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"InternalName");
      v80 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v32 = ppv;
      v81 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v32, (__int64 *)&v81, &v80, v114, v127);
      std::wstring::~wstring(v114);
      v33 = Utility::FormatWstring(v115, L"%llu", v134);
      std::wstring::wstring(v114, L"Size");
      v82 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v34 = ppv;
      v83 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v34, (__int64 *)&v83, &v82, v114, v33);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      v35 = Utility::FormatWstring(v115, L"%u", (unsigned int)v133[9]);
      std::wstring::wstring(v114, L"SizeOfImage");
      v84 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v36 = ppv;
      v85 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v36, (__int64 *)&v85, &v84, v114, v35);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v114, L"PeHeaderHash");
      v86 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v37 = ppv;
      v87 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v37, (__int64 *)&v87, &v86, v114, v131);
      std::wstring::~wstring(v114);
      v38 = Utility::FormatWstring(v115, L"%u", (unsigned int)v133[10]);
      std::wstring::wstring(v114, L"PeChecksum");
      v88 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v39 = ppv;
      v89 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v39, (__int64 *)&v89, &v88, v114, v38);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      v40 = Utility::FormatWstring(v115, L"%u", (unsigned int)v133[11]);
      std::wstring::wstring(v114, L"CrcChecksum");
      v90 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v41 = ppv;
      v91 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v41, (__int64 *)&v91, &v90, v114, v40);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v114, L"BinProductVersion");
      v92 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v42 = ppv;
      v93 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v42, (__int64 *)&v93, &v92, v114, v125);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"BinFileVersion");
      v94 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v43 = ppv;
      v95 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v43, (__int64 *)&v95, &v94, v114, v120);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"FileDescription");
      v96 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v44 = ppv;
      v97 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v44, (__int64 *)&v97, &v96, v114, v126);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"LegalCopyright");
      v98 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v45 = ppv;
      v99 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v45, (__int64 *)&v99, &v98, v114, v128);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"LinkDate");
      v100 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v46 = ppv;
      v101 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v46, (__int64 *)&v101, &v100, v114, v130);
      std::wstring::~wstring(v114);
      std::wstring::wstring(v114, L"BinaryType");
      v102 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v47 = ppv;
      v103 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v47, (__int64 *)&v103, &v102, v114, v119);
      std::wstring::~wstring(v114);
      v48 = (OLECHAR *)Utility::RemovePiiFromPath((__int64)v115, (__int64)v117);
      std::wstring::wstring(v114, L"LowerCaseLongPath");
      v104 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v49 = ppv;
      v105 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v49, (__int64 *)&v105, &v104, v114, v48);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v114, L"SigPublisherName");
      v106 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v50 = ppv;
      v107 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v50, (__int64 *)&v107, &v106, v114, v132);
      std::wstring::~wstring(v114);
      v51 = Utility::FormatWstring(v115, L"%u", (unsigned int)v133[12]);
      std::wstring::wstring(v114, L"PeSubsystem");
      v108 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v52 = ppv;
      v109 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v52, (__int64 *)&v109, &v108, v114, v51);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      v53 = Utility::FormatWstring(v115, L"%u", (unsigned int)v133[13]);
      std::wstring::wstring(v114, L"PeCharacteristics");
      v110 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v54 = ppv;
      v111 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v54, (__int64 *)&v111, &v110, v114, v53);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v115);
      std::wstring::wstring(v114, L"Sha256");
      v112 = v59;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
      v55 = ppv;
      v113[0] = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v55, v113, &v112, v114, (OLECHAR *)v133);
      std::wstring::~wstring(v114);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v59);
    }
    File::~File((File *)v116);
    v16 = (const struct File *)((char *)v16 + 816);
  }
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 272LL))(ppv, a4);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
  std::vector<File>::_Tidy(a3);
  return a1;
}

```

## disassembly

```asm
0x18010ca00  mov     rax, rsp
0x18010ca03  push    rbp
0x18010ca04  push    rsi
0x18010ca05  push    rdi
0x18010ca06  push    r12
0x18010ca08  push    r13
0x18010ca0a  push    r14
0x18010ca0c  push    r15
0x18010ca0e  lea     rbp, [rax-4B8h]
0x18010ca15  sub     rsp, 580h
0x18010ca1c  mov     [rbp+4B0h+var_3C0], 0FFFFFFFFFFFFFFFEh
0x18010ca27  mov     [rax+10h], rbx
0x18010ca2b  mov     rax, cs:__security_cookie
0x18010ca32  xor     rax, rsp
0x18010ca35  mov     [rbp+4B0h+var_40], rax
0x18010ca3c  mov     r13, r9
0x18010ca3f  mov     r14, r8
0x18010ca42  mov     r12, rcx
0x18010ca45  mov     [rbp+4B0h+var_3B8], r8
0x18010ca4c  xor     esi, esi
0x18010ca4e  mov     [rsp+5B0h+ppv], rsi
0x18010ca53  lea     rcx, [rsp+5B0h+ppv]
0x18010ca58  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010ca5d  lea     rax, [rsp+5B0h+ppv]
0x18010ca62  mov     [rsp+20h], rax; int
0x18010ca67  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18010ca6e  xor     edx, edx; pUnkOuter
0x18010ca70  lea     r8d, [rsi+1]; dwClsContext
0x18010ca74  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18010ca7b  call    cs:__imp_CoCreateInstance
0x18010ca81  mov     rcx, [rbp+4B8h]; this
0x18010ca88  test    eax, eax
0x18010ca8a  js      loc_18010DABA
0x18010ca90  mov     rcx, [rsp+5B0h+ppv]
0x18010ca95  mov     rax, [rcx]
0x18010ca98  xor     edx, edx
0x18010ca9a  mov     rax, [rax+1F8h]
0x18010caa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010caa6  mov     rcx, [rsp+5B0h+ppv]
0x18010caab  mov     rax, [rcx]
0x18010caae  xor     edx, edx
0x18010cab0  mov     rax, [rax+220h]
0x18010cab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cabc  mov     rcx, [rsp+5B0h+ppv]
0x18010cac1  mov     rax, [rcx]
0x18010cac4  xor     edx, edx
0x18010cac6  mov     rax, [rax+230h]
0x18010cacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cad2  mov     rcx, [rsp+5B0h+ppv]
0x18010cad7  mov     rax, [rcx]
0x18010cada  or      edx, 0FFFFFFFFh
0x18010cadd  mov     rax, [rax+240h]
0x18010cae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cae9  mov     [rsp+5B0h+var_568], rsi
0x18010caee  mov     rdi, [rsp+5B0h+ppv]
0x18010caf3  mov     rax, [rdi]
0x18010caf6  mov     rbx, [rax+178h]
0x18010cafd  lea     rcx, [rsp+5B0h+var_568]
0x18010cb02  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010cb07  lea     r8, [rsp+5B0h+var_568]
0x18010cb0c  lea     rdx, aOrphanfiles; "OrphanFiles"
0x18010cb13  mov     rcx, rdi
0x18010cb16  mov     rax, rbx
0x18010cb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cb1e  mov     rcx, [rbp+4B8h]; this
0x18010cb25  test    eax, eax
0x18010cb27  js      loc_18010DACF
0x18010cb2d  mov     rcx, [rsp+5B0h+ppv]
0x18010cb32  mov     rax, [rcx]
0x18010cb35  xor     r8d, r8d
0x18010cb38  mov     rdx, [rsp+5B0h+var_568]
0x18010cb3d  mov     rax, [rax+0A8h]
0x18010cb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cb49  mov     rcx, [rbp+4B8h]; this
0x18010cb50  test    eax, eax
0x18010cb52  js      loc_18010DAE4
0x18010cb58  mov     [rsp+5B0h+var_570], rsi
0x18010cb5d  mov     rdi, [rsp+5B0h+ppv]
0x18010cb62  mov     rax, [rdi]
0x18010cb65  mov     rbx, [rax+178h]
0x18010cb6c  lea     rcx, [rsp+5B0h+var_570]
0x18010cb71  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010cb76  lea     r8, [rsp+5B0h+var_570]
0x18010cb7b  lea     rdx, aFiles; "Files"
0x18010cb82  mov     rcx, rdi
0x18010cb85  mov     rax, rbx
0x18010cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cb8d  mov     rcx, [rbp+4B8h]; this
0x18010cb94  test    eax, eax
0x18010cb96  js      loc_18010DAF9
0x18010cb9c  mov     rcx, [rsp+5B0h+var_568]
0x18010cba1  mov     rax, [rcx]
0x18010cba4  xor     r8d, r8d
0x18010cba7  mov     rdx, [rsp+5B0h+var_570]
0x18010cbac  mov     rax, [rax+0A8h]
0x18010cbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cbb8  mov     rcx, [rbp+4B8h]; this
0x18010cbbf  test    eax, eax
0x18010cbc1  js      loc_18010DB0E
0x18010cbc7  mov     rsi, [r14]
0x18010cbca  mov     r15, [r14+8]
0x18010cbce  jmp     loc_18010DA19
0x18010cbd3  mov     rdx, rsi; struct File *
0x18010cbd6  lea     rcx, [rbp+4B0h+var_370]; this
0x18010cbdd  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x18010cbe2  nop
0x18010cbe3  cmp     [rbp+4B0h+var_4B], 0
0x18010cbea  jnz     loc_18010DA06
0x18010cbf0  mov     [rsp+5B0h+var_578], 0
0x18010cbf9  mov     rdi, [rsp+5B0h+ppv]
0x18010cbfe  mov     rax, [rdi]
0x18010cc01  mov     rbx, [rax+178h]
0x18010cc08  lea     rcx, [rsp+5B0h+var_578]
0x18010cc0d  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010cc12  lea     r8, [rsp+5B0h+var_578]
0x18010cc17  lea     rdx, aFile_0; "File"
0x18010cc1e  mov     rcx, rdi
0x18010cc21  mov     rax, rbx
0x18010cc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc29  mov     rcx, [rbp+4B8h]; this
0x18010cc30  test    eax, eax
0x18010cc32  js      loc_18010DAA5
0x18010cc38  mov     rcx, [rsp+5B0h+var_570]
0x18010cc3d  mov     rax, [rcx]
0x18010cc40  xor     r8d, r8d
0x18010cc43  mov     rdx, [rsp+5B0h+var_578]
0x18010cc48  mov     rax, [rax+0A8h]
0x18010cc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc54  mov     rcx, [rbp+4B8h]; this
0x18010cc5b  test    eax, eax
0x18010cc5d  js      loc_18010DA90
0x18010cc63  lea     rdx, aId; "Id"
0x18010cc6a  lea     rcx, [rbp+4B0h+var_390]
0x18010cc71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010cc76  nop
0x18010cc77  mov     rcx, [rsp+5B0h+var_578]
0x18010cc7c  mov     [rsp+5B0h+var_560], rcx
0x18010cc81  test    rcx, rcx
0x18010cc84  jz      short loc_18010CC93
0x18010cc86  mov     rax, [rcx]
0x18010cc89  mov     rax, [rax+8]
0x18010cc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cc92  nop
0x18010cc93  mov     rcx, [rsp+5B0h+ppv]
0x18010cc98  mov     [rsp+5B0h+var_558], rcx
0x18010cc9d  test    rcx, rcx
0x18010cca0  jz      short loc_18010CCAF
0x18010cca2  mov     rax, [rcx]
0x18010cca5  mov     rax, [rax+8]
0x18010cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ccae  nop
0x18010ccaf  lea     rax, [rbp+4B0h+var_2F8]
0x18010ccb6  mov     [rsp+20h], rax
0x18010ccbb  lea     r9, [rbp+4B0h+var_390]
0x18010ccc2  lea     r8, [rsp+5B0h+var_560]
0x18010ccc7  lea     rdx, [rsp+5B0h+var_558]
0x18010cccc  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010ccd1  nop
0x18010ccd2  lea     rcx, [rbp+4B0h+var_390]
0x18010ccd9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010ccde  lea     rdx, aName; "Name"
0x18010cce5  lea     rcx, [rbp+4B0h+var_390]
0x18010ccec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010ccf1  nop
0x18010ccf2  mov     rcx, [rsp+5B0h+var_578]
0x18010ccf7  mov     [rsp+5B0h+var_550], rcx
0x18010ccfc  test    rcx, rcx
0x18010ccff  jz      short loc_18010CD0E
0x18010cd01  mov     rax, [rcx]
0x18010cd04  mov     rax, [rax+8]
0x18010cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cd0d  nop
0x18010cd0e  mov     rcx, [rsp+5B0h+ppv]
0x18010cd13  mov     [rsp+5B0h+var_548], rcx
0x18010cd18  test    rcx, rcx
0x18010cd1b  jz      short loc_18010CD2A
0x18010cd1d  mov     rax, [rcx]
0x18010cd20  mov     rax, [rax+8]
0x18010cd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cd29  nop
0x18010cd2a  lea     rax, [rbp+4B0h+var_298]
0x18010cd31  mov     [rsp+20h], rax
0x18010cd36  lea     r9, [rbp+4B0h+var_390]
0x18010cd3d  lea     r8, [rsp+5B0h+var_550]
0x18010cd42  lea     rdx, [rsp+5B0h+var_548]
0x18010cd47  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010cd4c  nop
0x18010cd4d  lea     rcx, [rbp+4B0h+var_390]
0x18010cd54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010cd59  lea     rdx, aProductname; "ProductName"
0x18010cd60  lea     rcx, [rbp+4B0h+var_390]
0x18010cd67  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010cd6c  nop
0x18010cd6d  mov     rcx, [rsp+5B0h+var_578]
0x18010cd72  mov     [rsp+5B0h+var_540], rcx
0x18010cd77  test    rcx, rcx
0x18010cd7a  jz      short loc_18010CD89
0x18010cd7c  mov     rax, [rcx]
0x18010cd7f  mov     rax, [rax+8]
0x18010cd83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cd88  nop
0x18010cd89  mov     rcx, [rsp+5B0h+ppv]
0x18010cd8e  mov     [rsp+5B0h+var_538], rcx
0x18010cd93  test    rcx, rcx
0x18010cd96  jz      short loc_18010CDA5
0x18010cd98  mov     rax, [rcx]
0x18010cd9b  mov     rax, [rax+8]
0x18010cd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cda4  nop
0x18010cda5  lea     rax, [rbp+4B0h+var_238]
0x18010cdac  mov     [rsp+20h], rax
0x18010cdb1  lea     r9, [rbp+4B0h+var_390]
0x18010cdb8  lea     r8, [rsp+5B0h+var_540]
0x18010cdbd  lea     rdx, [rsp+5B0h+var_538]
0x18010cdc2  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010cdc7  nop
0x18010cdc8  lea     rcx, [rbp+4B0h+var_390]
0x18010cdcf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010cdd4  lea     rdx, aCompanyname; "CompanyName"
0x18010cddb  lea     rcx, [rbp+4B0h+var_390]
0x18010cde2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010cde7  nop
0x18010cde8  mov     rcx, [rsp+5B0h+var_578]
0x18010cded  mov     [rbp+4B0h+var_530], rcx
0x18010cdf1  test    rcx, rcx
0x18010cdf4  jz      short loc_18010CE03
0x18010cdf6  mov     rax, [rcx]
0x18010cdf9  mov     rax, [rax+8]
0x18010cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ce02  nop
0x18010ce03  mov     rcx, [rsp+5B0h+ppv]
0x18010ce08  mov     [rbp+4B0h+var_528], rcx
0x18010ce0c  test    rcx, rcx
0x18010ce0f  jz      short loc_18010CE1E
0x18010ce11  mov     rax, [rcx]
0x18010ce14  mov     rax, [rax+8]
0x18010ce18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ce1d  nop
0x18010ce1e  lea     rax, [rbp+4B0h+var_258]
0x18010ce25  mov     [rsp+20h], rax
0x18010ce2a  lea     r9, [rbp+4B0h+var_390]
0x18010ce31  lea     r8, [rbp+4B0h+var_530]
0x18010ce35  lea     rdx, [rbp+4B0h+var_528]
0x18010ce39  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010ce3e  nop
0x18010ce3f  lea     rcx, [rbp+4B0h+var_390]
0x18010ce46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010ce4b  lea     rdx, aProductversion; "ProductVersion"
0x18010ce52  lea     rcx, [rbp+4B0h+var_390]
0x18010ce59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010ce5e  nop
0x18010ce5f  mov     rcx, [rsp+5B0h+var_578]
0x18010ce64  mov     [rbp+4B0h+var_520], rcx
0x18010ce68  test    rcx, rcx
0x18010ce6b  jz      short loc_18010CE7A
0x18010ce6d  mov     rax, [rcx]
0x18010ce70  mov     rax, [rax+8]
0x18010ce74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ce79  nop
0x18010ce7a  mov     rcx, [rsp+5B0h+ppv]
0x18010ce7f  mov     [rbp+4B0h+var_518], rcx
0x18010ce83  test    rcx, rcx
0x18010ce86  jz      short loc_18010CE95
0x18010ce88  mov     rax, [rcx]
0x18010ce8b  mov     rax, [rax+8]
0x18010ce8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ce94  nop
0x18010ce95  lea     rax, [rbp+4B0h+var_218]
0x18010ce9c  mov     [rsp+20h], rax
0x18010cea1  lea     r9, [rbp+4B0h+var_390]
0x18010cea8  lea     r8, [rbp+4B0h+var_520]
0x18010ceac  lea     rdx, [rbp+4B0h+var_518]
0x18010ceb0  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010ceb5  nop
0x18010ceb6  lea     rcx, [rbp+4B0h+var_390]
0x18010cebd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010cec2  mov     r8d, [rbp+4B0h+var_50]
0x18010cec9  lea     rdi, aU_0; "%u"
0x18010ced0  mov     rdx, rdi
0x18010ced3  lea     rcx, [rbp+4B0h+var_3B0]
0x18010ceda  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x18010cedf  mov     rbx, rax
0x18010cee2  lea     rdx, aVerlanguage; "VerLanguage"
0x18010cee9  lea     rcx, [rbp+4B0h+var_390]
0x18010cef0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010cef5  nop
0x18010cef6  mov     rcx, [rsp+5B0h+var_578]
0x18010cefb  mov     [rbp+4B0h+var_510], rcx
0x18010ceff  test    rcx, rcx
0x18010cf02  jz      short loc_18010CF11
0x18010cf04  mov     rax, [rcx]
0x18010cf07  mov     rax, [rax+8]
0x18010cf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010cf10  nop
0x18010cf11  mov     rcx, [rsp+5B0h+ppv]
0x18010cf16  mov     [rbp+4B0h+var_508], rcx
0x18010cf1a  test    rcx, rcx
0x18010cf1d  jz      short loc_18010CF2C
0x18010cf1f  mov     rax, [rcx]
0x18010cf22  mov     rax, [rax+8]
  ... truncated ...
```
