# GetSystemConfigInfo(mlib::XmlStream &)

- ea: `0x14002ac4c`
- end: `0x14002b888`
- name: `?GetSystemConfigInfo@@YAXAEAVXmlStream@mlib@@@Z`
- size: `3132`
- prototype: `void __fastcall(struct mlib::XmlStream *this)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d91c`
- `0x14002b890`

## callees

- `0x140003611`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140004650`
- `0x140005d78`
- `0x140005e5c`
- `0x140005f10`
- `0x140008178`
- `0x1400085b4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016480`
- `0x140016524`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x140019bd8`
- `0x140021b58`
- `0x140021da8`
- `0x14002ac4c`
- `0x14004c884`
- `0x140053590`
- `0x140053900`
- `0x140056d9c`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14002b16b`
- `KERNEL32!GetProcAddress` at `0x14002b16b`
- `KERNEL32!LoadLibraryW` at `0x14002b156`
- `KERNEL32!LoadLibraryW` at `0x14002b156`
- `KERNEL32!GetLastError` at `0x14002b176`
- `KERNEL32!GetLastError` at `0x14002b176`
- `KERNEL32!SetLastError` at `0x14002b187`
- `KERNEL32!SetLastError` at `0x14002b187`
- `ntdll!RtlGetVersion` at `0x14002ae0e`
- `ntdll!RtlGetVersion` at `0x14002ae0e`

## string_xrefs

- `0x14002acec`: `ComputerName`
- `0x14002ad63`: `ComputerName`
- `0x14002b14f`: `ntdll.dll`
- `0x14002b766`: `HistoryVersionWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall GetSystemConfigInfo(struct mlib::XmlStream *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // rbx
  const wchar_t *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  DWORD dwMajorVersion; // ebx
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD dwMinorVersion; // ebx
  const wchar_t *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  DWORD dwBuildNumber; // ebx
  const wchar_t *v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int64 v31; // rax
  unsigned int v32; // ebx
  const wchar_t *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  _QWORD *v38; // rbx
  const wchar_t *v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  mlib::XmlStream *v44; // rbx
  __int64 v45; // rax
  _QWORD *v46; // rbx
  const wchar_t *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rbx
  const wchar_t *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  const wchar_t *v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  const wchar_t *v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v67; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v68[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v69; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v70; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v72[8]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h] BYREF
  __int64 v74; // [rsp+78h] [rbp-88h] BYREF
  __int64 v75; // [rsp+80h] [rbp-80h]
  __int64 v76; // [rsp+88h] [rbp-78h]
  _BYTE v77[72]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF

  if ( App::s_Verbose )
  {
    v2 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v2 + 240, L"> Gathering System Information");
    std::endl(v3);
  }
  if ( App::s_IsPrivateBld || App::s_DumpComputerName )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v71,
      3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v70,
      L"ComputerName");
    if ( *((_DWORD *)this + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
    *((_DWORD *)this + 2) = 2;
    mlib::XmlStream::Indent(this);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v4, &v70);
    ++*((_DWORD *)this + 3);
    *((_BYTE *)this + 17) = 0;
    v69 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v69,
      v71);
    v5 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(this);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v67,
      L"ComputerName");
    --*((_DWORD *)v5 + 3);
    if ( *((_DWORD *)v5 + 2) == 1 )
    {
      if ( !*((_BYTE *)v5 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v5);
      *((_BYTE *)v5 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v5, L"</");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v8, &v67);
      v7 = v9;
      v6 = L">";
    }
    else
    {
      if ( *((_DWORD *)v5 + 2) != 2 )
      {
LABEL_14:
        *((_DWORD *)v5 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v67);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v70);
        std::basic_ostream<unsigned short>::flush(*(_QWORD *)this);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v71);
        goto LABEL_15;
      }
      v6 = L"/>";
      v7 = *v5;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, v6);
    goto LABEL_14;
  }
LABEL_15:
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  RtlGetVersion(&VersionInformation);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"OSVersion");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, &v66);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"Major");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v11, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwMajorVersion = VersionInformation.dwMajorVersion;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, dwMajorVersion);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v72,
    L"Major");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v15, v72);
    v14 = v16;
    v13 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_26;
    v13 = L"/>";
    v14 = *(_QWORD *)this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v14, v13);
LABEL_26:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &si128,
    L"Minor");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v17, &si128);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwMinorVersion = VersionInformation.dwMinorVersion;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, dwMinorVersion);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v69,
    L"Minor");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v21, &v69);
    v20 = v22;
    v19 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_35;
    v19 = L"/>";
    v20 = *(_QWORD *)this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, v19);
LABEL_35:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v67,
    L"Build");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v23, &v67);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  dwBuildNumber = VersionInformation.dwBuildNumber;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, dwBuildNumber);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v71,
    L"Build");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v27, &v71);
    v26 = v28;
    v25 = L">";
    goto LABEL_43;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v25 = L"/>";
    v26 = *(_QWORD *)this;
LABEL_43:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, v25);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v71);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v67);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v69);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&si128);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v72);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  v74 = 0;
  v75 = 0;
  v76 = 0;
  mlib::WinBrand::LoadLibraryW((mlib::WinBrand *)&v74);
  LibraryW = LoadLibraryW(L"ntdll.dll");
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "RtlGetProductInfo")) != 0 )
  {
    v70 = 0;
    if ( ((unsigned __int8 (__fastcall *)(__int64, __int64, __int64, __int64, unsigned int *))ProcAddress)(
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           &v70) )
    {
      goto LABEL_49;
    }
  }
  else
  {
    GetLastError();
    v70 = 0;
    SetLastError(0x32u);
  }
  v70 = 0;
LABEL_49:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"ProductType");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v32 = v70;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, v32);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"ProductType");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v35, &v66);
    v34 = v36;
    v33 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_58;
    v33 = L"/>";
    v34 = *(_QWORD *)this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, v33);
LABEL_58:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v69);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion");
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &si128.m128i_u64[1],
    v66);
  mlib::RegistryBaseKey::cleanup(&si128.m128i_u64[1]);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"ProductName");
  mlib::RstringReg::RstringReg(v77, &si128, &v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  if ( (unsigned int)mlib::MRegistryRWBase::read((mlib::MRegistryRWBase *)v77) )
    mlib::WinBrand::BrandingLoadStringZ(&v74, 13, &v69);
  else
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v69,
      v78);
  mlib::RstringReg::~RstringReg((mlib::RstringReg *)v77);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"ProductName");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v37, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v67 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v67,
    v69);
  v38 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"ProductName");
  --*((_DWORD *)v38 + 3);
  if ( *((_DWORD *)v38 + 2) == 1 )
  {
    if ( !*((_BYTE *)v38 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)v38);
    *((_BYTE *)v38 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v38, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v41, &v66);
    v40 = v42;
    v39 = L">";
  }
  else
  {
    if ( *((_DWORD *)v38 + 2) != 2 )
      goto LABEL_70;
    v39 = L"/>";
    v40 = *v38;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, v39);
LABEL_70:
  *((_DWORD *)v38 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
  v74 = 0;
  v75 = 0;
  v76 = 0;
  mlib::WinBrand::LoadLibraryW((mlib::WinBrand *)&v74);
  mlib::WinBrand::BrandingLoadStringZ(&v74, 12, &v69);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v69);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"OSName");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v44 = (mlib::XmlStream *)mlib::XmlStream::operator<<<void>(this, mlib::BeginCData);
  v67 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v67,
    v69);
  v45 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(v44);
  v46 = (_QWORD *)mlib::XmlStream::operator<<<void>(v45, mlib::EndCData);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"OSName");
  --*((_DWORD *)v46 + 3);
  if ( *((_DWORD *)v46 + 2) == 1 )
  {
    if ( !*((_BYTE *)v46 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)v46);
    *((_BYTE *)v46 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v46, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v49, &v66);
    v48 = v50;
    v47 = L">";
  }
  else
  {
    if ( *((_DWORD *)v46 + 2) != 2 )
      goto LABEL_79;
    v47 = L"/>";
    v48 = *v46;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, v47);
LABEL_79:
  *((_DWORD *)v46 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"BuildLab");
  mlib::RstringReg::RstringReg(v77, &si128, &v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  if ( (unsigned int)mlib::MRegistryRWBase::read((mlib::MRegistryRWBase *)v77) )
    goto LABEL_90;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"BuildLab");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  v67 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v67,
    v78);
  v52 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"BuildLab");
  --*((_DWORD *)v52 + 3);
  if ( *((_DWORD *)v52 + 2) == 1 )
  {
    if ( !*((_BYTE *)v52 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)v52);
    *((_BYTE *)v52 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v52, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, &v66);
    v54 = v56;
    v53 = L">";
    goto LABEL_88;
  }
  if ( *((_DWORD *)v52 + 2) == 2 )
  {
    v53 = L"/>";
    v54 = *v52;
LABEL_88:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, v53);
  }
  *((_DWORD *)v52 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
LABEL_90:
  mlib::RstringReg::~RstringReg((mlib::RstringReg *)v77);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"OSVersion");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v59, &v66);
    v58 = v60;
    v57 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_97;
    v57 = L"/>";
    v58 = *(_QWORD *)this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v58, v57);
LABEL_97:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&si128.m128i_u64[1]);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v69);
  v70 = 0;
  if ( (int)DataStoreReader::GetHistoryVersion(L"HistoryVersionWrite", &v70) < 0 )
    return;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v68,
    L"HistoryVersion");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v61, v68);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, v70);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v66,
    L"HistoryVersion");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v64, &v66);
    v63 = v65;
    v62 = L">";
    goto LABEL_106;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v62 = L"/>";
    v63 = *(_QWORD *)this;
LABEL_106:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v63, v62);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v66);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v68);
}

```

## disassembly

```asm
0x14002ac4c  push    rbp
0x14002ac4e  push    rbx
0x14002ac4f  push    rsi
0x14002ac50  push    rdi
0x14002ac51  push    r12
0x14002ac53  push    r13
0x14002ac55  push    r14
0x14002ac57  push    r15
0x14002ac59  lea     rbp, [rsp-128h]
0x14002ac61  sub     rsp, 228h
0x14002ac68  mov     rax, cs:__security_cookie
0x14002ac6f  xor     rax, rsp
0x14002ac72  mov     [rbp+160h+var_50], rax
0x14002ac79  mov     rdi, rcx
0x14002ac7c  xor     esi, esi
0x14002ac7e  cmp     cs:?s_Verbose@App@@2_NA, sil; bool App::s_Verbose
0x14002ac85  jz      short loc_14002ACAE
0x14002ac87  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002ac8e  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ac93  lea     rcx, [rax+0F0h]
0x14002ac9a  lea     rdx, aGatheringSyste; "> Gathering System Information"
0x14002aca1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aca6  mov     rcx, rax
0x14002aca9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14002acae  mov     r15d, 2
0x14002acb4  lea     r14, asc_14012B480; ">"
0x14002acbb  lea     r12d, [r15-1]
0x14002acbf  lea     r13, asc_14012B488; "/>"
0x14002acc6  cmp     cs:?s_IsPrivateBld@App@@2_NA, sil; bool App::s_IsPrivateBld
0x14002accd  jnz     short loc_14002ACDC
0x14002accf  cmp     cs:?s_DumpComputerName@App@@2_NA, sil; bool App::s_DumpComputerName
0x14002acd6  jz      loc_14002ADF2
0x14002acdc  mov     edx, 3
0x14002ace1  lea     rcx, [rsp+260h+var_208]
0x14002ace6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@W4CreationID@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::CreationID)
0x14002aceb  nop
0x14002acec  lea     rdx, aComputername; "ComputerName"
0x14002acf3  lea     rcx, [rsp+260h+var_210]
0x14002acf8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002acfd  nop
0x14002acfe  cmp     [rdi+8], r15d
0x14002ad02  jnz     short loc_14002AD0F
0x14002ad04  mov     rdx, r14
0x14002ad07  mov     rcx, [rdi]
0x14002ad0a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ad0f  mov     [rdi+8], r15d
0x14002ad13  mov     rcx, rdi; this
0x14002ad16  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ad1b  lea     rdx, asc_14012B484; "<"
0x14002ad22  mov     rcx, [rdi]
0x14002ad25  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ad2a  mov     rcx, rax
0x14002ad2d  lea     rdx, [rsp+260h+var_210]
0x14002ad32  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ad37  add     [rdi+0Ch], r12d
0x14002ad3b  mov     [rdi+11h], sil
0x14002ad3f  mov     [rsp+260h+var_218], rsi
0x14002ad44  mov     rdx, [rsp+260h+var_208]
0x14002ad49  lea     rcx, [rsp+260h+var_218]
0x14002ad4e  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002ad53  lea     rdx, [rsp+260h+var_218]
0x14002ad58  mov     rcx, rdi
0x14002ad5b  call    ??$?6V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@XmlStream@mlib@@QEAAAEAV01@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::XmlStream::operator<<<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x14002ad60  mov     rbx, rax
0x14002ad63  lea     rdx, aComputername; "ComputerName"
0x14002ad6a  lea     rcx, [rsp+260h+var_228]
0x14002ad6f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ad74  nop
0x14002ad75  dec     dword ptr [rbx+0Ch]
0x14002ad78  mov     eax, [rbx+8]
0x14002ad7b  sub     eax, 1
0x14002ad7e  jz      short loc_14002AD8D
0x14002ad80  cmp     eax, 1
0x14002ad83  jnz     short loc_14002ADC6
0x14002ad85  mov     rdx, r13
0x14002ad88  mov     rcx, [rbx]
0x14002ad8b  jmp     short loc_14002ADC1
0x14002ad8d  cmp     [rbx+11h], sil
0x14002ad91  jnz     short loc_14002AD9B
0x14002ad93  mov     rcx, rbx; this
0x14002ad96  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ad9b  mov     [rbx+11h], sil
0x14002ad9f  lea     rdx, asc_14012B490; "</"
0x14002ada6  mov     rcx, [rbx]
0x14002ada9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002adae  mov     rcx, rax
0x14002adb1  lea     rdx, [rsp+260h+var_228]
0x14002adb6  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002adbb  mov     rcx, rax
0x14002adbe  mov     rdx, r14
0x14002adc1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002adc6  mov     [rbx+8], r12d
0x14002adca  lea     rcx, [rsp+260h+var_228]
0x14002adcf  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002add4  nop
0x14002add5  lea     rcx, [rsp+260h+var_210]
0x14002adda  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002addf  mov     rcx, [rdi]
0x14002ade2  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x14002ade7  nop
0x14002ade8  lea     rcx, [rsp+260h+var_208]
0x14002aded  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002adf2  xor     edx, edx; Val
0x14002adf4  mov     r8d, 118h; Size
0x14002adfa  lea     rcx, [rbp+160h+VersionInformation.dwMajorVersion]; void *
0x14002adfe  call    memset_0
0x14002ae03  mov     [rbp+160h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14002ae0a  lea     rcx, [rbp+160h+VersionInformation]; lpVersionInformation
0x14002ae0e  call    cs:__imp_RtlGetVersion
0x14002ae14  lea     rdx, aOsversion; "OSVersion"
0x14002ae1b  lea     rcx, [rsp+260h+var_230]
0x14002ae20  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ae25  nop
0x14002ae26  cmp     [rdi+8], r15d
0x14002ae2a  jnz     short loc_14002AE37
0x14002ae2c  mov     rdx, r14
0x14002ae2f  mov     rcx, [rdi]
0x14002ae32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae37  mov     [rdi+8], r15d
0x14002ae3b  mov     rcx, rdi; this
0x14002ae3e  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ae43  lea     rdx, asc_14012B484; "<"
0x14002ae4a  mov     rcx, [rdi]
0x14002ae4d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae52  mov     rcx, rax
0x14002ae55  lea     rdx, [rsp+260h+var_230]
0x14002ae5a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ae5f  add     [rdi+0Ch], r12d
0x14002ae63  mov     [rdi+11h], sil
0x14002ae67  lea     rdx, aMajor; "Major"
0x14002ae6e  lea     rcx, [rsp+260h+var_220]
0x14002ae73  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ae78  nop
0x14002ae79  cmp     [rdi+8], r15d
0x14002ae7d  jnz     short loc_14002AE8A
0x14002ae7f  mov     rdx, r14
0x14002ae82  mov     rcx, [rdi]
0x14002ae85  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ae8a  mov     [rdi+8], r15d
0x14002ae8e  mov     rcx, rdi; this
0x14002ae91  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002ae96  lea     rdx, asc_14012B484; "<"
0x14002ae9d  mov     rcx, [rdi]
0x14002aea0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aea5  mov     rcx, rax
0x14002aea8  lea     rdx, [rsp+260h+var_220]
0x14002aead  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002aeb2  add     [rdi+0Ch], r12d
0x14002aeb6  mov     [rdi+11h], sil
0x14002aeba  mov     ebx, [rbp+160h+VersionInformation.dwMajorVersion]
0x14002aebd  mov     rcx, rdi; this
0x14002aec0  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002aec5  mov     edx, ebx
0x14002aec7  mov     rcx, [rdi]
0x14002aeca  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002aecf  mov     rcx, rdi; this
0x14002aed2  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002aed7  lea     rdx, aMajor; "Major"
0x14002aede  lea     rcx, [rsp+260h+var_200]
0x14002aee3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002aee8  nop
0x14002aee9  dec     dword ptr [rdi+0Ch]
0x14002aeec  mov     ecx, [rdi+8]
0x14002aeef  sub     ecx, 1
0x14002aef2  jz      short loc_14002AF01
0x14002aef4  cmp     ecx, 1
0x14002aef7  jnz     short loc_14002AF3A
0x14002aef9  mov     rdx, r13
0x14002aefc  mov     rcx, [rdi]
0x14002aeff  jmp     short loc_14002AF35
0x14002af01  cmp     [rdi+11h], sil
0x14002af05  jnz     short loc_14002AF0F
0x14002af07  mov     rcx, rdi; this
0x14002af0a  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002af0f  mov     [rdi+11h], sil
0x14002af13  lea     rdx, asc_14012B490; "</"
0x14002af1a  mov     rcx, [rdi]
0x14002af1d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af22  mov     rcx, rax
0x14002af25  lea     rdx, [rsp+260h+var_200]
0x14002af2a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002af2f  mov     rcx, rax
0x14002af32  mov     rdx, r14
0x14002af35  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af3a  mov     [rdi+8], r12d
0x14002af3e  lea     rdx, aMinor; "Minor"
0x14002af45  lea     rcx, [rsp+260h+var_1F8]
0x14002af4a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002af4f  nop
0x14002af50  cmp     [rdi+8], r15d
0x14002af54  jnz     short loc_14002AF61
0x14002af56  mov     rdx, r14
0x14002af59  mov     rcx, [rdi]
0x14002af5c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af61  mov     [rdi+8], r15d
0x14002af65  mov     rcx, rdi; this
0x14002af68  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002af6d  lea     rdx, asc_14012B484; "<"
0x14002af74  mov     rcx, [rdi]
0x14002af77  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002af7c  mov     rcx, rax
0x14002af7f  lea     rdx, [rsp+260h+var_1F8]
0x14002af84  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002af89  add     [rdi+0Ch], r12d
0x14002af8d  mov     [rdi+11h], sil
0x14002af91  mov     ebx, [rbp+160h+VersionInformation.dwMinorVersion]
0x14002af94  mov     rcx, rdi; this
0x14002af97  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002af9c  mov     edx, ebx
0x14002af9e  mov     rcx, [rdi]
0x14002afa1  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002afa6  mov     rcx, rdi; this
0x14002afa9  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002afae  lea     rdx, aMinor; "Minor"
0x14002afb5  lea     rcx, [rsp+260h+var_218]
0x14002afba  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002afbf  nop
0x14002afc0  dec     dword ptr [rdi+0Ch]
0x14002afc3  mov     ecx, [rdi+8]
0x14002afc6  sub     ecx, 1
0x14002afc9  jz      short loc_14002AFD8
0x14002afcb  cmp     ecx, 1
0x14002afce  jnz     short loc_14002B011
0x14002afd0  mov     rdx, r13
0x14002afd3  mov     rcx, [rdi]
0x14002afd6  jmp     short loc_14002B00C
0x14002afd8  cmp     [rdi+11h], sil
0x14002afdc  jnz     short loc_14002AFE6
0x14002afde  mov     rcx, rdi; this
0x14002afe1  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002afe6  mov     [rdi+11h], sil
0x14002afea  lea     rdx, asc_14012B490; "</"
0x14002aff1  mov     rcx, [rdi]
0x14002aff4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002aff9  mov     rcx, rax
0x14002affc  lea     rdx, [rsp+260h+var_218]
0x14002b001  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b006  mov     rcx, rax
0x14002b009  mov     rdx, r14
0x14002b00c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b011  mov     [rdi+8], r12d
0x14002b015  lea     rdx, aBuild_0; "Build"
0x14002b01c  lea     rcx, [rsp+260h+var_228]
0x14002b021  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002b026  nop
0x14002b027  cmp     [rdi+8], r15d
0x14002b02b  jnz     short loc_14002B038
0x14002b02d  mov     rdx, r14
0x14002b030  mov     rcx, [rdi]
0x14002b033  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b038  mov     [rdi+8], r15d
0x14002b03c  mov     rcx, rdi; this
0x14002b03f  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002b044  lea     rdx, asc_14012B484; "<"
0x14002b04b  mov     rcx, [rdi]
0x14002b04e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b053  mov     rcx, rax
0x14002b056  lea     rdx, [rsp+260h+var_228]
0x14002b05b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b060  add     [rdi+0Ch], r12d
0x14002b064  mov     [rdi+11h], sil
0x14002b068  mov     ebx, [rbp+160h+VersionInformation.dwBuildNumber]
0x14002b06b  mov     rcx, rdi; this
0x14002b06e  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14002b073  mov     edx, ebx
0x14002b075  mov     rcx, [rdi]
0x14002b078  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14002b07d  mov     rcx, rdi; this
0x14002b080  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14002b085  lea     rdx, aBuild_0; "Build"
0x14002b08c  lea     rcx, [rsp+260h+var_208]
0x14002b091  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002b096  nop
0x14002b097  dec     dword ptr [rdi+0Ch]
0x14002b09a  mov     ecx, [rdi+8]
0x14002b09d  sub     ecx, 1
0x14002b0a0  jz      short loc_14002B0AF
0x14002b0a2  cmp     ecx, 1
0x14002b0a5  jnz     short loc_14002B0E8
0x14002b0a7  mov     rdx, r13
0x14002b0aa  mov     rcx, [rdi]
0x14002b0ad  jmp     short loc_14002B0E3
0x14002b0af  cmp     [rdi+11h], sil
0x14002b0b3  jnz     short loc_14002B0BD
0x14002b0b5  mov     rcx, rdi; this
0x14002b0b8  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002b0bd  mov     [rdi+11h], sil
0x14002b0c1  lea     rdx, asc_14012B490; "</"
0x14002b0c8  mov     rcx, [rdi]
0x14002b0cb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b0d0  mov     rcx, rax
0x14002b0d3  lea     rdx, [rsp+260h+var_208]
0x14002b0d8  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002b0dd  mov     rcx, rax
0x14002b0e0  mov     rdx, r14
0x14002b0e3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002b0e8  mov     [rdi+8], r12d
0x14002b0ec  lea     rcx, [rsp+260h+var_208]
0x14002b0f1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002b0f6  nop
  ... truncated ...
```
