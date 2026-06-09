# XmlBuilder::XmlBuilder(ConfigSettings const &,std::vector<Application,std::allocator<Application>>,std::vector<File,std::allocator<File>>,ushort * *)

- ea: `0x18010bf8c`
- end: `0x18010c9f8`
- name: `??0XmlBuilder@@QEAA@AEBVConfigSettings@@V?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@V?$vector@VFile@@V?$allocator@VFile@@@std@@@3@PEAPEAG@Z`
- size: `2668`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057730`

## callees

- `0x18000a39c`
- `0x18000b364`
- `0x18000b7cc`
- `0x18000ecac`
- `0x18001716c`
- `0x1800188f4`
- `0x180018a60`
- `0x180025190`
- `0x1800403ac`
- `0x1800404c4`
- `0x180052dc0`
- `0x180059920`
- `0x1800679f8`
- `0x18010bf8c`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18010c010`
- `ole32!CoCreateInstance` at `0x18010c010`

## string_xrefs

- `0x18010c6a9`: `CompanyName`
- `0x18010c914`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c929`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c93e`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c953`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c968`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c97d`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c992`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c9a7`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c9bc`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c9d1`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c9e6`: `base\appcompat\inventory\software\inv2\lib\xmlbuilder.cpp`
- `0x18010c0a1`: `InventoryCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall XmlBuilder::XmlBuilder(
        __int64 a1,
        __int64 a2,
        const struct Application **a3,
        const struct File **a4,
        __int64 a5)
{
  HRESULT v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // r8
  const struct Application *v18; // rsi
  const struct Application *v19; // r12
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v22; // eax
  int v23; // eax
  LPVOID v24; // rcx
  LPVOID v25; // rcx
  LPVOID v26; // rcx
  LPVOID v27; // rcx
  wchar_t *v28; // rbx
  LPVOID v29; // rcx
  LPVOID v30; // rdi
  __int64 (__fastcall *v31)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v32; // eax
  int v33; // eax
  const struct File *v34; // rsi
  const struct File *v35; // r12
  LPVOID v36; // rdi
  __int64 (__fastcall *v37)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v38; // eax
  int v39; // eax
  LPVOID v40; // rcx
  LPVOID v41; // rcx
  LPVOID v42; // rcx
  LPVOID v43; // rcx
  LPVOID v44; // rcx
  LPVOID v45; // rcx
  LPVOID v46; // rcx
  int v48; // [rsp+28h] [rbp-E0h]
  LPVOID ppv; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID v51; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-98h] BYREF
  __int64 v57; // [rsp+78h] [rbp-90h] BYREF
  __int64 v58; // [rsp+80h] [rbp-88h] BYREF
  __int64 v59; // [rsp+88h] [rbp-80h] BYREF
  __int64 v60; // [rsp+90h] [rbp-78h] BYREF
  __int64 v61; // [rsp+98h] [rbp-70h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID v66; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-38h]
  __int64 v69; // [rsp+D8h] [rbp-30h]
  const struct Application **v70; // [rsp+E0h] [rbp-28h]
  const struct File **v71; // [rsp+E8h] [rbp-20h]
  unsigned __int16 v72[16]; // [rsp+F0h] [rbp-18h] BYREF
  wchar_t v73[20]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v74[56]; // [rsp+138h] [rbp+30h] BYREF
  OLECHAR v75[16]; // [rsp+170h] [rbp+68h] BYREF
  OLECHAR v76; // [rsp+190h] [rbp+88h] BYREF
  OLECHAR v77[12]; // [rsp+198h] [rbp+90h] BYREF
  OLECHAR v78; // [rsp+1B0h] [rbp+A8h] BYREF
  OLECHAR v79[12]; // [rsp+1B8h] [rbp+B0h] BYREF
  int v80; // [rsp+1D0h] [rbp+C8h] BYREF
  OLECHAR v81[28]; // [rsp+1D8h] [rbp+D0h] BYREF
  OLECHAR v82[16]; // [rsp+210h] [rbp+108h] BYREF
  OLECHAR v83[16]; // [rsp+230h] [rbp+128h] BYREF
  OLECHAR v84[92]; // [rsp+250h] [rbp+148h] BYREF
  unsigned int v85; // [rsp+308h] [rbp+200h]
  OLECHAR v86[134]; // [rsp+350h] [rbp+248h] BYREF
  char v87; // [rsp+45Dh] [rbp+355h]
  wil::details::in1diag3 *retaddr; // [rsp+570h] [rbp+468h]

  v69 = -2;
  v70 = a3;
  v71 = a4;
  v68 = a5;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
  v8 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v8,
      v48);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
  v52 = 0;
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v52);
  v11 = v10(v9, L"InventoryCache", &v52);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v11,
      v48);
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 168LL))(ppv, v52, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v12,
      v48);
  v64 = 0;
  v13 = ppv;
  v14 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v64);
  v15 = v14(v13, L"Applications", &v64);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v15,
      v48);
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v52 + 168LL))(v52, v64, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v16,
      v48);
  v18 = *a3;
  v19 = a3[1];
  while ( v18 != v19 )
  {
    Application::Application((Application *)v74, v18, v17);
    v50 = 0;
    v20 = ppv;
    v21 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v50);
    v22 = v21(v20, L"Application", &v50);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
        (const char *)(unsigned int)v22,
        v48);
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v64 + 168LL))(v64, v50, 0);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
        (const char *)(unsigned int)v23,
        v48);
    std::wstring::wstring(v72, L"Id");
    v53 = v50;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v24 = ppv;
    v54 = (__int64)ppv;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    XmlBuilder::AddAttribute((__int64)v24, &v54, &v53, v72, v75);
    std::wstring::~wstring(v72);
    std::wstring::wstring(v72, L"Name");
    v55 = v50;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v25 = ppv;
    v56 = (__int64)ppv;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    XmlBuilder::AddAttribute((__int64)v25, &v56, &v55, v72, v77);
    std::wstring::~wstring(v72);
    std::wstring::wstring(v72, L"Publisher");
    v57 = v50;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v26 = ppv;
    v58 = (__int64)ppv;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    XmlBuilder::AddAttribute((__int64)v26, &v58, &v57, v72, v79);
    std::wstring::~wstring(v72);
    std::wstring::wstring(v72, L"Version");
    v59 = v50;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v27 = ppv;
    v60 = (__int64)ppv;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    XmlBuilder::AddAttribute((__int64)v27, &v60, &v59, v72, v81);
    std::wstring::~wstring(v72);
    v28 = Utility::FormatWstring(v73, L"%d", v85);
    std::wstring::wstring(v72, L"Language");
    v61 = v50;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
    v29 = ppv;
    v62 = (__int64)ppv;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    XmlBuilder::AddAttribute((__int64)v29, &v62, &v61, v72, v28);
    std::wstring::~wstring(v72);
    std::wstring::~wstring(v73);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v50);
    Application::~Application((Application *)v74);
    v18 = (const struct Application *)((char *)v18 + 1008);
  }
  v63 = 0;
  v30 = ppv;
  v31 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v63);
  v32 = v31(v30, L"Files", &v63);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v32,
      v48);
  v33 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v52 + 168LL))(v52, v63, 0);
  if ( v33 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
      (const char *)(unsigned int)v33,
      v48);
  v34 = *a4;
  v35 = a4[1];
  while ( v34 != v35 )
  {
    File::File((File *)v74, v34);
    if ( !v87 )
    {
      v50 = 0;
      v36 = ppv;
      v37 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 376LL);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v50);
      v38 = v37(v36, L"File", &v50);
      if ( v38 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
          (const char *)(unsigned int)v38,
          v48);
      v39 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v63 + 168LL))(v63, v50, 0);
      if ( v39 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\xmlbuilder.cpp",
          (const char *)(unsigned int)v39,
          v48);
      std::wstring::wstring(v72, L"Id");
      v62 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v40 = ppv;
      v61 = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v40, &v61, &v62, v72, &v78);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"ProgramId");
      v60 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v41 = ppv;
      v59 = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v41, &v59, &v60, v72, &v76);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"Name");
      v58 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v42 = ppv;
      v57 = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v42, &v57, &v58, v72, v82);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"CompanyName");
      v56 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v43 = ppv;
      v55 = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v43, &v55, &v56, v72, v84);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"FileVersion");
      v54 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v44 = ppv;
      v53 = (__int64)ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v44, &v53, &v54, v72, v83);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"OriginalFileName");
      v65 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v45 = ppv;
      v66 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v45, (__int64 *)&v66, &v65, v72, v86);
      std::wstring::~wstring(v72);
      std::wstring::wstring(v72, L"BinaryType");
      v67 = v50;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      v46 = ppv;
      v51 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
      XmlBuilder::AddAttribute((__int64)v46, (__int64 *)&v51, &v67, v72, (OLECHAR *)&v80);
      std::wstring::~wstring(v72);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v50);
    }
    File::~File((File *)v74);
    v34 = (const struct File *)((char *)v34 + 816);
  }
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 272LL))(ppv, v68);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
  std::vector<Application>::_Tidy(a3);
  std::vector<File>::_Tidy(a4);
  return a1;
}

```

## disassembly

```asm
0x18010bf8c  mov     rax, rsp
0x18010bf8f  push    rbp
0x18010bf90  push    rsi
0x18010bf91  push    rdi
0x18010bf92  push    r12
0x18010bf94  push    r13
0x18010bf96  push    r14
0x18010bf98  push    r15
0x18010bf9a  lea     rbp, [rax-468h]
0x18010bfa1  sub     rsp, 530h
0x18010bfa8  mov     [rbp+460h+var_490], 0FFFFFFFFFFFFFFFEh
0x18010bfb0  mov     [rax+10h], rbx
0x18010bfb4  mov     rax, cs:__security_cookie
0x18010bfbb  xor     rax, rsp
0x18010bfbe  mov     [rbp+460h+var_40], rax
0x18010bfc5  mov     r15, r9
0x18010bfc8  mov     r14, r8
0x18010bfcb  mov     r13, rcx
0x18010bfce  mov     [rbp+460h+var_488], r8
0x18010bfd2  mov     [rbp+460h+var_480], r9
0x18010bfd6  mov     rax, [rbp+460h+arg_20]
0x18010bfdd  mov     [rbp+460h+var_498], rax
0x18010bfe1  xor     esi, esi
0x18010bfe3  mov     [rsp+560h+ppv], rsi
0x18010bfe8  lea     rcx, [rsp+560h+ppv]
0x18010bfed  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010bff2  lea     rax, [rsp+560h+ppv]
0x18010bff7  mov     [rsp+20h], rax; int
0x18010bffc  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18010c003  xor     edx, edx; pUnkOuter
0x18010c005  lea     r8d, [rsi+1]; dwClsContext
0x18010c009  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18010c010  call    cs:__imp_CoCreateInstance
0x18010c016  mov     rcx, [rbp+468h]; this
0x18010c01d  test    eax, eax
0x18010c01f  js      loc_18010C93B
0x18010c025  mov     rcx, [rsp+560h+ppv]
0x18010c02a  mov     rax, [rcx]
0x18010c02d  xor     edx, edx
0x18010c02f  mov     rax, [rax+1F8h]
0x18010c036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c03b  mov     rcx, [rsp+560h+ppv]
0x18010c040  mov     rax, [rcx]
0x18010c043  xor     edx, edx
0x18010c045  mov     rax, [rax+220h]
0x18010c04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c051  mov     rcx, [rsp+560h+ppv]
0x18010c056  mov     rax, [rcx]
0x18010c059  xor     edx, edx
0x18010c05b  mov     rax, [rax+230h]
0x18010c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c067  mov     rcx, [rsp+560h+ppv]
0x18010c06c  mov     rax, [rcx]
0x18010c06f  or      edx, 0FFFFFFFFh
0x18010c072  mov     rax, [rax+240h]
0x18010c079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c07e  mov     [rsp+560h+var_518], rsi
0x18010c083  mov     rdi, [rsp+560h+ppv]
0x18010c088  mov     rax, [rdi]
0x18010c08b  mov     rbx, [rax+178h]
0x18010c092  lea     rcx, [rsp+560h+var_518]
0x18010c097  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010c09c  lea     r8, [rsp+560h+var_518]
0x18010c0a1  lea     rdx, aInventorycache_4; "InventoryCache"
0x18010c0a8  mov     rcx, rdi
0x18010c0ab  mov     rax, rbx
0x18010c0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c0b3  mov     rcx, [rbp+468h]; this
0x18010c0ba  test    eax, eax
0x18010c0bc  js      loc_18010C950
0x18010c0c2  mov     rcx, [rsp+560h+ppv]
0x18010c0c7  mov     rax, [rcx]
0x18010c0ca  xor     r8d, r8d
0x18010c0cd  mov     rdx, [rsp+560h+var_518]
0x18010c0d2  mov     rax, [rax+0A8h]
0x18010c0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c0de  mov     rcx, [rbp+468h]; this
0x18010c0e5  test    eax, eax
0x18010c0e7  js      loc_18010C965
0x18010c0ed  mov     [rbp+460h+var_4B8], rsi
0x18010c0f1  mov     rdi, [rsp+560h+ppv]
0x18010c0f6  mov     rax, [rdi]
0x18010c0f9  mov     rbx, [rax+178h]
0x18010c100  lea     rcx, [rbp+460h+var_4B8]
0x18010c104  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010c109  lea     r8, [rbp+460h+var_4B8]
0x18010c10d  lea     rdx, aApplications; "Applications"
0x18010c114  mov     rcx, rdi
0x18010c117  mov     rax, rbx
0x18010c11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c11f  mov     rcx, [rbp+468h]; this
0x18010c126  test    eax, eax
0x18010c128  js      loc_18010C97A
0x18010c12e  mov     rcx, [rsp+560h+var_518]
0x18010c133  mov     rax, [rcx]
0x18010c136  xor     r8d, r8d
0x18010c139  mov     rdx, [rbp+460h+var_4B8]
0x18010c13d  mov     rax, [rax+0A8h]
0x18010c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c149  mov     rcx, [rbp+468h]; this
0x18010c150  test    eax, eax
0x18010c152  js      loc_18010C98F
0x18010c158  mov     rsi, [r14]
0x18010c15b  mov     r12, [r14+8]
0x18010c15f  jmp     loc_18010C44B
0x18010c164  mov     rdx, rsi; struct Application *
0x18010c167  lea     rcx, [rbp+460h+var_430]; this
0x18010c16b  call    ??0Application@@QEAA@AEBV0@@Z; Application::Application(Application const &)
0x18010c170  nop
0x18010c171  mov     [rsp+560h+var_528], 0
0x18010c17a  mov     rdi, [rsp+560h+ppv]
0x18010c17f  mov     rax, [rdi]
0x18010c182  mov     rbx, [rax+178h]
0x18010c189  lea     rcx, [rsp+560h+var_528]
0x18010c18e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010c193  lea     r8, [rsp+560h+var_528]
0x18010c198  lea     rdx, aApplication; "Application"
0x18010c19f  mov     rcx, rdi
0x18010c1a2  mov     rax, rbx
0x18010c1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c1aa  mov     rcx, [rbp+468h]; this
0x18010c1b1  test    eax, eax
0x18010c1b3  js      loc_18010C9CE
0x18010c1b9  mov     rcx, [rbp+460h+var_4B8]
0x18010c1bd  mov     rax, [rcx]
0x18010c1c0  xor     r8d, r8d
0x18010c1c3  mov     rdx, [rsp+560h+var_528]
0x18010c1c8  mov     rax, [rax+0A8h]
0x18010c1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c1d4  mov     rcx, [rbp+468h]; this
0x18010c1db  test    eax, eax
0x18010c1dd  js      loc_18010C9B9
0x18010c1e3  lea     rdx, aId; "Id"
0x18010c1ea  lea     rcx, [rbp+460h+var_478]
0x18010c1ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c1f3  nop
0x18010c1f4  mov     rcx, [rsp+560h+var_528]
0x18010c1f9  mov     [rsp+560h+var_510], rcx
0x18010c1fe  test    rcx, rcx
0x18010c201  jz      short loc_18010C210
0x18010c203  mov     rax, [rcx]
0x18010c206  mov     rax, [rax+8]
0x18010c20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c20f  nop
0x18010c210  mov     rcx, [rsp+560h+ppv]
0x18010c215  mov     [rsp+560h+var_508], rcx
0x18010c21a  test    rcx, rcx
0x18010c21d  jz      short loc_18010C22C
0x18010c21f  mov     rax, [rcx]
0x18010c222  mov     rax, [rax+8]
0x18010c226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c22b  nop
0x18010c22c  lea     rax, [rbp+460h+var_3F8]
0x18010c230  mov     [rsp+20h], rax
0x18010c235  lea     r9, [rbp+460h+var_478]
0x18010c239  lea     r8, [rsp+560h+var_510]
0x18010c23e  lea     rdx, [rsp+560h+var_508]
0x18010c243  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010c248  nop
0x18010c249  lea     rcx, [rbp+460h+var_478]
0x18010c24d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c252  lea     rdx, aName; "Name"
0x18010c259  lea     rcx, [rbp+460h+var_478]
0x18010c25d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c262  nop
0x18010c263  mov     rcx, [rsp+560h+var_528]
0x18010c268  mov     [rsp+560h+var_500], rcx
0x18010c26d  test    rcx, rcx
0x18010c270  jz      short loc_18010C27F
0x18010c272  mov     rax, [rcx]
0x18010c275  mov     rax, [rax+8]
0x18010c279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c27e  nop
0x18010c27f  mov     rcx, [rsp+560h+ppv]
0x18010c284  mov     [rsp+560h+var_4F8], rcx
0x18010c289  test    rcx, rcx
0x18010c28c  jz      short loc_18010C29B
0x18010c28e  mov     rax, [rcx]
0x18010c291  mov     rax, [rax+8]
0x18010c295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c29a  nop
0x18010c29b  lea     rax, [rbp+460h+var_3D0]
0x18010c2a2  mov     [rsp+20h], rax
0x18010c2a7  lea     r9, [rbp+460h+var_478]
0x18010c2ab  lea     r8, [rsp+560h+var_500]
0x18010c2b0  lea     rdx, [rsp+560h+var_4F8]
0x18010c2b5  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010c2ba  nop
0x18010c2bb  lea     rcx, [rbp+460h+var_478]
0x18010c2bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c2c4  lea     rdx, aPublisher; "Publisher"
0x18010c2cb  lea     rcx, [rbp+460h+var_478]
0x18010c2cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c2d4  nop
0x18010c2d5  mov     rcx, [rsp+560h+var_528]
0x18010c2da  mov     [rsp+560h+var_4F0], rcx
0x18010c2df  test    rcx, rcx
0x18010c2e2  jz      short loc_18010C2F1
0x18010c2e4  mov     rax, [rcx]
0x18010c2e7  mov     rax, [rax+8]
0x18010c2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c2f0  nop
0x18010c2f1  mov     rcx, [rsp+560h+ppv]
0x18010c2f6  mov     [rsp+560h+var_4E8], rcx
0x18010c2fb  test    rcx, rcx
0x18010c2fe  jz      short loc_18010C30D
0x18010c300  mov     rax, [rcx]
0x18010c303  mov     rax, [rax+8]
0x18010c307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c30c  nop
0x18010c30d  lea     rax, [rbp+460h+var_3B0]
0x18010c314  mov     [rsp+20h], rax
0x18010c319  lea     r9, [rbp+460h+var_478]
0x18010c31d  lea     r8, [rsp+560h+var_4F0]
0x18010c322  lea     rdx, [rsp+560h+var_4E8]
0x18010c327  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010c32c  nop
0x18010c32d  lea     rcx, [rbp+460h+var_478]
0x18010c331  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c336  lea     rdx, aVersion; "Version"
0x18010c33d  lea     rcx, [rbp+460h+var_478]
0x18010c341  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c346  nop
0x18010c347  mov     rcx, [rsp+560h+var_528]
0x18010c34c  mov     [rbp+460h+var_4E0], rcx
0x18010c350  test    rcx, rcx
0x18010c353  jz      short loc_18010C362
0x18010c355  mov     rax, [rcx]
0x18010c358  mov     rax, [rax+8]
0x18010c35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c361  nop
0x18010c362  mov     rcx, [rsp+560h+ppv]
0x18010c367  mov     [rbp+460h+var_4D8], rcx
0x18010c36b  test    rcx, rcx
0x18010c36e  jz      short loc_18010C37D
0x18010c370  mov     rax, [rcx]
0x18010c373  mov     rax, [rax+8]
0x18010c377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c37c  nop
0x18010c37d  lea     rax, [rbp+460h+var_390]
0x18010c384  mov     [rsp+20h], rax
0x18010c389  lea     r9, [rbp+460h+var_478]
0x18010c38d  lea     r8, [rbp+460h+var_4E0]
0x18010c391  lea     rdx, [rbp+460h+var_4D8]
0x18010c395  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010c39a  nop
0x18010c39b  lea     rcx, [rbp+460h+var_478]
0x18010c39f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c3a4  mov     r8d, [rbp+460h+var_260]
0x18010c3ab  lea     rdx, aD; "%d"
0x18010c3b2  lea     rcx, [rbp+460h+var_458]
0x18010c3b6  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x18010c3bb  mov     rbx, rax
0x18010c3be  lea     rdx, aLanguage; "Language"
0x18010c3c5  lea     rcx, [rbp+460h+var_478]
0x18010c3c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c3ce  nop
0x18010c3cf  mov     rcx, [rsp+560h+var_528]
0x18010c3d4  mov     [rbp+460h+var_4D0], rcx
0x18010c3d8  test    rcx, rcx
0x18010c3db  jz      short loc_18010C3EA
0x18010c3dd  mov     rax, [rcx]
0x18010c3e0  mov     rax, [rax+8]
0x18010c3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c3e9  nop
0x18010c3ea  mov     rcx, [rsp+560h+ppv]
0x18010c3ef  mov     [rbp+460h+var_4C8], rcx
0x18010c3f3  test    rcx, rcx
0x18010c3f6  jz      short loc_18010C405
0x18010c3f8  mov     rax, [rcx]
0x18010c3fb  mov     rax, [rax+8]
0x18010c3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c404  nop
0x18010c405  mov     [rsp+20h], rbx; int
0x18010c40a  lea     r9, [rbp+460h+var_478]
0x18010c40e  lea     r8, [rbp+460h+var_4D0]
0x18010c412  lea     rdx, [rbp+460h+var_4C8]
0x18010c416  call    ?AddAttribute@XmlBuilder@@AEAAXV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@V?$ComPtr@UIXMLDOMElement@@@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; XmlBuilder::AddAttribute(Microsoft::WRL::ComPtr<IXMLDOMDocument>,Microsoft::WRL::ComPtr<IXMLDOMElement>,std::wstring const &,std::wstring const &)
0x18010c41b  nop
0x18010c41c  lea     rcx, [rbp+460h+var_478]
0x18010c420  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c425  nop
0x18010c426  lea     rcx, [rbp+460h+var_458]
0x18010c42a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010c42f  nop
0x18010c430  lea     rcx, [rsp+560h+var_528]
0x18010c435  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010c43a  nop
0x18010c43b  lea     rcx, [rbp+460h+var_430]; this
0x18010c43f  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x18010c444  add     rsi, 3F0h
0x18010c44b  cmp     rsi, r12
0x18010c44e  jnz     loc_18010C164
0x18010c454  mov     [rbp+460h+var_4C0], 0
0x18010c45c  mov     rdi, [rsp+560h+ppv]
0x18010c461  mov     rax, [rdi]
0x18010c464  mov     rbx, [rax+178h]
0x18010c46b  lea     rcx, [rbp+460h+var_4C0]
0x18010c46f  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18010c474  lea     r8, [rbp+460h+var_4C0]
  ... truncated ...
```
