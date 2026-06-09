# ComputeGraphicsMetrics

- ea: `0x14002e924`
- end: `0x14002f404`
- name: `ComputeGraphicsMetrics`
- size: `2784`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140033bf4`
- `0x1400342b4`

## callees

- `0x140001abc`
- `0x140004348`
- `0x14000449c`
- `0x140005d78`
- `0x140005f10`
- `0x140007f14`
- `0x1400085b4`
- `0x140016d04`
- `0x140017af0`
- `0x140018968`
- `0x140021b58`
- `0x14002c48c`
- `0x14002e924`
- `0x14003c934`
- `0x14003ec14`
- `0x14004fe00`
- `0x140052fac`
- `0x14005354c`
- `0x140053590`
- `0x1400535e4`
- `0x140053618`
- `0x140053bf0`
- `0x140054d0c`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002ef12`
- `KERNEL32!GetLastError` at `0x14002ef7b`
- `KERNEL32!GetLastError` at `0x14002f009`
- `KERNEL32!GetLastError` at `0x14002f06e`
- `KERNEL32!GetLastError` at `0x14002f0d3`
- `KERNEL32!GetLastError` at `0x14002f135`
- `KERNEL32!GetLastError` at `0x14002f197`
- `KERNEL32!GetLastError` at `0x14002f1f9`
- `KERNEL32!GetLastError` at `0x14002f2b7`
- `KERNEL32!GetLastError` at `0x14002ef12`
- `KERNEL32!GetLastError` at `0x14002ef7b`
- `KERNEL32!GetLastError` at `0x14002f009`
- `KERNEL32!GetLastError` at `0x14002f06e`
- `KERNEL32!GetLastError` at `0x14002f0d3`
- `KERNEL32!GetLastError` at `0x14002f135`
- `KERNEL32!GetLastError` at `0x14002f197`
- `KERNEL32!GetLastError` at `0x14002f1f9`
- `KERNEL32!GetLastError` at `0x14002f2b7`

## string_xrefs

- `0x14002f376`: `Skipping Registry Entry for Graphics score`
- `0x14002ef57`: `ERROR: Can't write primary video adapter string to the registry '%s': %s`
- `0x14002efbe`: `ERROR: Can't write video memory bandwidth to the registry %u: %s`
- `0x14002efe5`: `> Wrote video memory bandwidth to the registry %u`
- `0x14002f04a`: `ERROR: Can't write video memory size to the registry %u: %s\n`
- `0x14002f0af`: `ERROR: Can't write dedicated video memory size to the registry %u: %s\n`
- `0x14002f114`: `ERROR: Can't write dedicated system memory size to the registry %u: %s\n`
- `0x14002f176`: `ERROR: Can't write shared video memory size to the registry %u: %s\n`
- `0x14002f1d8`: `ERROR: Can't write num moniotrs to the registry %u: %s\n`
- `0x14002f23a`: `ERROR:Can't write total desktop pixels to the registry %u: %s\n`
- `0x14002f2f6`: `ERROR:Can't write graphics FPS to the registry %u: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall ComputeGraphicsMetrics(__int64 a1, char a2, char a3)
{
  int NodesValues; // esi
  __int64 v7; // rbx
  unsigned __int16 v8; // r9
  const unsigned __int16 *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  void *v15; // rsi
  __int64 v16; // rbx
  unsigned __int16 v17; // r9
  const unsigned __int16 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int16 v21; // r9
  const unsigned __int16 *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  KeyInfo *v25; // rax
  int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  _BYTE v42[8]; // [rsp+38h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-C8h] BYREF
  void *Block_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-B0h]
  _BYTE v46[80]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v47[80]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v48[80]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v49[80]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v50[80]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v51[80]; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v52[80]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v53[80]; // [rsp+298h] [rbp+190h] BYREF
  CHAR v54[96]; // [rsp+2E8h] [rbp+1E0h] BYREF
  CHAR Buffer[256]; // [rsp+348h] [rbp+240h] BYREF
  DWORD LastError; // [rsp+448h] [rbp+340h]
  char v57; // [rsp+44Ch] [rbp+344h]
  __int64 v58; // [rsp+450h] [rbp+348h]

  *(_OWORD *)Block_8 = 0;
  v45 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(Block);
  qword_140168888 = *(_QWORD *)&DOUBLE_1_797693134862316e308;
  dbl_140168980 = DOUBLE_1_797693134862316e308;
  if ( a2 )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v42,
      L"/DWMAssessment/Results/FPS");
  else
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v42,
      L"/WinSAT/DWMAssessment/Results/FPS");
  NodesValues = mlib::XmlDOM::GetNodesValues(a1, v42, Block_8, Block);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
  if ( NodesValues < 0 )
  {
    v7 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
       + 240;
    v9 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\processresults.cpp", (const char *)0xFBF, 10109, v8);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, v9);
    v11 = std::endl(v10);
LABEL_6:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"       ");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, Block);
    std::endl(v13);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(Block);
    if ( Block_8[0] )
      operator delete(Block_8[0]);
    return (unsigned int)NodesValues;
  }
  v15 = Block_8[0];
  if ( Block_8[1] != Block_8[0] )
  {
    if ( (void *)((char *)Block_8[1] - (char *)Block_8[0]) != (void *)8 )
    {
      v16 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
          + 240;
      v18 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\processresults.cpp", (const char *)0xFCA, 10109, v17);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, v18);
      std::endl(v19);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(Block);
      if ( v15 )
        operator delete(v15);
      return 2147500037LL;
    }
    qword_140168888 = *(_QWORD *)Block_8[0];
    Block_8[1] = Block_8[0];
    if ( a2 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v42,
        L"/DWMAssessment/Results/MbVideoMemPerSecond");
    else
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v42,
        L"/WinSAT/DWMAssessment/Results/MbVideoMemPerSecond");
    NodesValues = mlib::XmlDOM::GetNodesValues(a1, v42, Block_8, Block);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
    if ( NodesValues < 0 )
    {
      v20 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
          + 240;
      v22 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\processresults.cpp", (const char *)0xFE2, 10109, v21);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, v22);
      v11 = std::basic_ostream<unsigned short>::operator<<(v23, 10);
      goto LABEL_6;
    }
    v15 = Block_8[0];
    if ( Block_8[1] != Block_8[0] )
    {
      dbl_140168980 = *(double *)Block_8[0];
      if ( App::s_isAxeMode
        || (v24 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&App::s_xmlTestFile),
            !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v24))
        || App::s_WsSwapTest
        || !App::s_RegistryCreated )
      {
        Log_Text_F("base\\winsat\\exe\\processresults.cpp", 4080, "Skipping Registry Entry for Graphics score");
      }
      else if ( a3 )
      {
        if ( !*(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                       + 1056) )
        {
          v25 = (KeyInfo *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          v26 = KeyInfo::EnumerateMonitorsAndGraphics(v25);
          if ( v26 < 0 )
          {
LABEL_57:
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(Block);
            operator delete(v15);
            return (unsigned int)v26;
          }
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"PrimaryAdapterString");
        mlib::RstringReg::RstringReg(v54, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"VideoMemoryBandwidth");
        mlib::DWORDReg::DWORDReg(v53, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"VideoMemorySize");
        mlib::DWORDReg::DWORDReg(v52, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"DedicatedVideoMemory");
        mlib::DWORDReg::DWORDReg(v51, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"DedicatedSystemMemory");
        mlib::DWORDReg::DWORDReg(v50, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"SharedVideoMemory");
        mlib::DWORDReg::DWORDReg(v49, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"NumMonitors");
        mlib::DWORDReg::DWORDReg(v48, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v42,
          L"TotalMonitorPixels");
        mlib::DWORDReg::DWORDReg(v47, qword_1401C6370, v42);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
        v27 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::RstringReg::operator=(v54, v27 + 1112);
        mlib::DWORDReg::operator=(v53, (unsigned int)(int)(dbl_140168980 * 1000.0));
        v28 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        LODWORD(v28) = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                                 + 1496)
                     + *(_DWORD *)(v28 + 1504);
        v29 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v52, (unsigned int)(v28 + *(_DWORD *)(v29 + 1488)));
        v30 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v51, *(unsigned int *)(v30 + 1488));
        v31 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v50, *(unsigned int *)(v31 + 1496));
        v32 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v49, *(unsigned int *)(v32 + 1504));
        v33 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v48, *(unsigned int *)(v33 + 1068));
        v34 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
        mlib::DWORDReg::operator=(v47, *(unsigned int *)(v34 + 1072));
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v54) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v35 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4115,
            "ERROR: Can't write primary video adapter string to the registry '%s': %s",
            *(const char **)(*(_QWORD *)(v35 + 1104) + 24LL),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v53) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4121,
            "ERROR: Can't write video memory bandwidth to the registry %u: %s",
            (int)(dbl_140168980 * 1000.0),
            Buffer);
        }
        else
        {
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4125,
            "> Wrote video memory bandwidth to the registry %u",
            (int)(dbl_140168980 * 1000.0));
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v52) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v36 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4130,
            "ERROR: Can't write video memory size to the registry %u: %s\n",
            *(_DWORD *)(v36 + 1488),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v51) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v37 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4135,
            "ERROR: Can't write dedicated video memory size to the registry %u: %s\n",
            *(_DWORD *)(v37 + 1488),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v50) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v38 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4140,
            "ERROR: Can't write dedicated system memory size to the registry %u: %s\n",
            *(_DWORD *)(v38 + 1496),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v49) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v39 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4145,
            "ERROR: Can't write shared video memory size to the registry %u: %s\n",
            *(_DWORD *)(v39 + 1504),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v48) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v40 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4150,
            "ERROR: Can't write num moniotrs to the registry %u: %s\n",
            *(_DWORD *)(v40 + 1068),
            Buffer);
        }
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v47) )
        {
          LastError = GetLastError();
          v57 = 1;
          v58 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          v41 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4155,
            "ERROR:Can't write total desktop pixels to the registry %u: %s\n",
            *(_DWORD *)(v41 + 1072),
            Buffer);
        }
        if ( App::s_isFormal )
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v42,
            L"GraphicsFPS");
          mlib::DWORDReg::DWORDReg(v46, qword_1401C6370, v42);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
          mlib::DWORDReg::operator=(v46, (unsigned int)(int)(*(double *)&qword_140168888 * 1000.0));
          if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v46) )
          {
            LastError = GetLastError();
            v57 = 1;
            v58 = 0;
            mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
            Log_Text_F(
              "base\\winsat\\exe\\processresults.cpp",
              4166,
              "ERROR:Can't write graphics FPS to the registry %u: %s\n",
              qword_140168888,
              Buffer);
          }
          mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v46);
        }
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v47);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v48);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v49);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v50);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v51);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v52);
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v53);
        mlib::RstringReg::~RstringReg((mlib::RstringReg *)v54);
      }
      if ( App::s_isFormal && qword_1401C6668 )
        qword_1401C6668(qword_1401689B8, 1883, (unsigned int)(int)(dbl_140168980 * 1000.0));
      v26 = 0;
      goto LABEL_57;
    }
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(Block);
  if ( v15 )
    operator delete(v15);
  return 0;
}

```

## disassembly

```asm
0x14002e924  mov     rax, rsp
0x14002e927  push    rbp
0x14002e928  push    rbx
0x14002e929  push    rsi
0x14002e92a  push    rdi
0x14002e92b  push    r14
0x14002e92d  push    r15
0x14002e92f  lea     rbp, [rax-3A8h]
0x14002e936  sub     rsp, 478h
0x14002e93d  movaps  xmmword ptr [rax-48h], xmm6
0x14002e941  mov     rax, cs:__security_cookie
0x14002e948  xor     rax, rsp
0x14002e94b  mov     [rbp+3A0h+var_50], rax
0x14002e952  mov     r14b, r8b
0x14002e955  mov     dil, dl
0x14002e958  mov     rbx, rcx
0x14002e95b  xorps   xmm0, xmm0
0x14002e95e  movdqu  xmmword ptr [rsp+4A0h+Block+8], xmm0
0x14002e964  xor     r15d, r15d
0x14002e967  mov     [rsp+4A0h+var_450], r15
0x14002e96c  lea     rcx, [rsp+4A0h+Block]
0x14002e971  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14002e976  nop
0x14002e977  movsd   xmm0, cs:__real@7fefffffffffffff
0x14002e97f  movsd   cs:qword_140168888, xmm0
0x14002e987  movsd   cs:dbl_140168980, xmm0
0x14002e98f  lea     rcx, [rsp+4A0h+var_470]
0x14002e994  test    dil, dil
0x14002e997  jz      short loc_14002E9C1
0x14002e999  lea     rdx, aDwmassessmentR_0; "/DWMAssessment/Results/FPS"
0x14002e9a0  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002e9a5  nop
0x14002e9a6  lea     r9, [rsp+4A0h+Block]
0x14002e9ab  lea     r8, [rsp+4A0h+Block+8]
0x14002e9b0  lea     rdx, [rsp+4A0h+var_470]
0x14002e9b5  mov     rcx, rbx
0x14002e9b8  call    ?GetNodesValues@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@NV?$allocator@N@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesValues(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<double> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002e9bd  mov     esi, eax
0x14002e9bf  jmp     short loc_14002E9E7
0x14002e9c1  lea     rdx, aWinsatDwmasses_0; "/WinSAT/DWMAssessment/Results/FPS"
0x14002e9c8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002e9cd  nop
0x14002e9ce  lea     r9, [rsp+4A0h+Block]
0x14002e9d3  lea     r8, [rsp+4A0h+Block+8]
0x14002e9d8  lea     rdx, [rsp+4A0h+var_470]
0x14002e9dd  mov     rcx, rbx
0x14002e9e0  call    ?GetNodesValues@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@NV?$allocator@N@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesValues(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<double> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002e9e5  mov     esi, eax
0x14002e9e7  lea     rcx, [rsp+4A0h+var_470]
0x14002e9ec  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002e9f1  test    esi, esi
0x14002e9f3  jns     loc_14002EA7C
0x14002e9f9  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002ea00  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ea05  lea     rbx, [rax+0F0h]
0x14002ea0c  mov     edx, 0FBFh; char *
0x14002ea11  mov     r8d, 277Dh; int
0x14002ea17  lea     rcx, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002ea1e  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14002ea23  mov     rdx, rax
0x14002ea26  mov     rcx, rbx
0x14002ea29  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ea2e  mov     rcx, rax
0x14002ea31  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14002ea36  mov     rcx, rax
0x14002ea39  lea     rdx, asc_14012C5C8; "       "
0x14002ea40  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002ea45  mov     rcx, rax
0x14002ea48  lea     rdx, [rsp+4A0h+Block]
0x14002ea4d  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ea52  mov     rcx, rax
0x14002ea55  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14002ea5a  nop
0x14002ea5b  lea     rcx, [rsp+4A0h+Block]
0x14002ea60  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ea65  nop
0x14002ea66  mov     rcx, [rsp+4A0h+Block+8]; Block
0x14002ea6b  test    rcx, rcx
0x14002ea6e  jz      short loc_14002EA75
0x14002ea70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ea75  mov     eax, esi
0x14002ea77  jmp     loc_14002F3DD
0x14002ea7c  mov     rax, [rsp+4A0h+var_458]
0x14002ea81  mov     rsi, [rsp+4A0h+Block+8]
0x14002ea86  sub     rax, rsi
0x14002ea89  jz      loc_14002EBBF
0x14002ea8f  cmp     rax, 8
0x14002ea93  jz      short loc_14002EAF5
0x14002ea95  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002ea9c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002eaa1  lea     rbx, [rax+0F0h]
0x14002eaa8  mov     edx, 0FCAh; char *
0x14002eaad  mov     r8d, 277Dh; int
0x14002eab3  lea     rcx, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002eaba  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14002eabf  mov     rdx, rax
0x14002eac2  mov     rcx, rbx
0x14002eac5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002eaca  mov     rcx, rax
0x14002eacd  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14002ead2  nop
0x14002ead3  lea     rcx, [rsp+4A0h+Block]
0x14002ead8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002eadd  nop
0x14002eade  test    rsi, rsi
0x14002eae1  jz      short loc_14002EAEB
0x14002eae3  mov     rcx, rsi; Block
0x14002eae6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002eaeb  mov     eax, 80004005h
0x14002eaf0  jmp     loc_14002F3DD
0x14002eaf5  movsd   xmm0, qword ptr [rsi]
0x14002eaf9  movsd   cs:qword_140168888, xmm0
0x14002eb01  mov     [rsp+4A0h+var_458], rsi
0x14002eb06  lea     rcx, [rsp+4A0h+var_470]
0x14002eb0b  test    dil, dil
0x14002eb0e  jz      short loc_14002EB38
0x14002eb10  lea     rdx, aDwmassessmentR; "/DWMAssessment/Results/MbVideoMemPerSec"...
0x14002eb17  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002eb1c  nop
0x14002eb1d  lea     r9, [rsp+4A0h+Block]
0x14002eb22  lea     r8, [rsp+4A0h+Block+8]
0x14002eb27  lea     rdx, [rsp+4A0h+var_470]
0x14002eb2c  mov     rcx, rbx
0x14002eb2f  call    ?GetNodesValues@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@NV?$allocator@N@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesValues(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<double> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002eb34  mov     esi, eax
0x14002eb36  jmp     short loc_14002EB5E
0x14002eb38  lea     rdx, aWinsatDwmasses; "/WinSAT/DWMAssessment/Results/MbVideoMe"...
0x14002eb3f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002eb44  nop
0x14002eb45  lea     r9, [rsp+4A0h+Block]
0x14002eb4a  lea     r8, [rsp+4A0h+Block+8]
0x14002eb4f  lea     rdx, [rsp+4A0h+var_470]
0x14002eb54  mov     rcx, rbx
0x14002eb57  call    ?GetNodesValues@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@NV?$allocator@N@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesValues(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<double> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002eb5c  mov     esi, eax
0x14002eb5e  lea     rcx, [rsp+4A0h+var_470]
0x14002eb63  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002eb68  test    esi, esi
0x14002eb6a  jns     short loc_14002EBB3
0x14002eb6c  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14002eb73  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002eb78  lea     rbx, [rax+0F0h]
0x14002eb7f  mov     edx, 0FE2h; char *
0x14002eb84  mov     r8d, 277Dh; int
0x14002eb8a  lea     rcx, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002eb91  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14002eb96  mov     rdx, rax
0x14002eb99  mov     rcx, rbx
0x14002eb9c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002eba1  mov     edx, 0Ah
0x14002eba6  mov     rcx, rax
0x14002eba9  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14002ebae  jmp     loc_14002EA36
0x14002ebb3  mov     rsi, [rsp+4A0h+Block+8]
0x14002ebb8  cmp     [rsp+4A0h+var_458], rsi
0x14002ebbd  jnz     short loc_14002EBDE
0x14002ebbf  lea     rcx, [rsp+4A0h+Block]
0x14002ebc4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ebc9  nop
0x14002ebca  test    rsi, rsi
0x14002ebcd  jz      short loc_14002EBD7
0x14002ebcf  mov     rcx, rsi; Block
0x14002ebd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ebd7  xor     eax, eax
0x14002ebd9  jmp     loc_14002F3DD
0x14002ebde  movsd   xmm0, qword ptr [rsi]
0x14002ebe2  movsd   cs:dbl_140168980, xmm0
0x14002ebea  movsd   xmm6, cs:__real@408f400000000000
0x14002ebf2  cmp     cs:?s_isAxeMode@App@@2_NA, r15b; bool App::s_isAxeMode
0x14002ebf9  jnz     loc_14002F376
0x14002ebff  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x14002ec06  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ec0b  mov     rcx, rax
0x14002ec0e  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14002ec13  test    al, al
0x14002ec15  jz      loc_14002F376
0x14002ec1b  cmp     cs:?s_WsSwapTest@App@@2_NA, r15b; bool App::s_WsSwapTest
0x14002ec22  jnz     loc_14002F376
0x14002ec28  cmp     cs:?s_RegistryCreated@App@@2_NA, r15b; bool App::s_RegistryCreated
0x14002ec2f  jz      loc_14002F376
0x14002ec35  test    r14b, r14b
0x14002ec38  jz      loc_14002F38E
0x14002ec3e  lea     r14, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14002ec45  mov     rcx, r14
0x14002ec48  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ec4d  cmp     [rax+420h], r15b
0x14002ec54  jnz     short loc_14002EC70
0x14002ec56  mov     rcx, r14
0x14002ec59  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ec5e  mov     rcx, rax; this
0x14002ec61  call    ?EnumerateMonitorsAndGraphics@KeyInfo@@QEAAJXZ; KeyInfo::EnumerateMonitorsAndGraphics(void)
0x14002ec66  mov     ebx, eax
0x14002ec68  test    eax, eax
0x14002ec6a  js      loc_14002F3C8
0x14002ec70  lea     rdx, aPrimaryadapter; "PrimaryAdapterString"
0x14002ec77  lea     rcx, [rsp+4A0h+var_470]
0x14002ec7c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ec81  nop
0x14002ec82  lea     r8, [rsp+4A0h+var_470]
0x14002ec87  mov     rdx, cs:qword_1401C6370
0x14002ec8e  lea     rcx, [rbp+3A0h+var_1C0]
0x14002ec95  call    ??0RstringReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::RstringReg::RstringReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002ec9a  nop
0x14002ec9b  lea     rcx, [rsp+4A0h+var_470]
0x14002eca0  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002eca5  lea     rdx, aVideomemoryban; "VideoMemoryBandwidth"
0x14002ecac  lea     rcx, [rsp+4A0h+var_470]
0x14002ecb1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ecb6  nop
0x14002ecb7  lea     r8, [rsp+4A0h+var_470]
0x14002ecbc  mov     rdx, cs:qword_1401C6370
0x14002ecc3  lea     rcx, [rbp+3A0h+var_210]
0x14002ecca  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002eccf  nop
0x14002ecd0  lea     rcx, [rsp+4A0h+var_470]
0x14002ecd5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ecda  lea     rdx, aVideomemorysiz; "VideoMemorySize"
0x14002ece1  lea     rcx, [rsp+4A0h+var_470]
0x14002ece6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002eceb  nop
0x14002ecec  lea     r8, [rsp+4A0h+var_470]
0x14002ecf1  mov     rdx, cs:qword_1401C6370
0x14002ecf8  lea     rcx, [rbp+3A0h+var_260]
0x14002ecff  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002ed04  nop
0x14002ed05  lea     rcx, [rsp+4A0h+var_470]
0x14002ed0a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ed0f  lea     rdx, aDedicatedvideo; "DedicatedVideoMemory"
0x14002ed16  lea     rcx, [rsp+4A0h+var_470]
0x14002ed1b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ed20  nop
0x14002ed21  lea     r8, [rsp+4A0h+var_470]
0x14002ed26  mov     rdx, cs:qword_1401C6370
0x14002ed2d  lea     rcx, [rbp+3A0h+var_2B0]
0x14002ed34  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002ed39  nop
0x14002ed3a  lea     rcx, [rsp+4A0h+var_470]
0x14002ed3f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ed44  lea     rdx, aDedicatedsyste; "DedicatedSystemMemory"
0x14002ed4b  lea     rcx, [rsp+4A0h+var_470]
0x14002ed50  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ed55  nop
0x14002ed56  lea     r8, [rsp+4A0h+var_470]
0x14002ed5b  mov     rdx, cs:qword_1401C6370
0x14002ed62  lea     rcx, [rbp+3A0h+var_300]
0x14002ed69  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002ed6e  nop
0x14002ed6f  lea     rcx, [rsp+4A0h+var_470]
0x14002ed74  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ed79  lea     rdx, aSharedvideomem; "SharedVideoMemory"
0x14002ed80  lea     rcx, [rsp+4A0h+var_470]
0x14002ed85  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ed8a  nop
0x14002ed8b  lea     r8, [rsp+4A0h+var_470]
0x14002ed90  mov     rdx, cs:qword_1401C6370
0x14002ed97  lea     rcx, [rbp+3A0h+var_350]
0x14002ed9b  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002eda0  nop
0x14002eda1  lea     rcx, [rsp+4A0h+var_470]
0x14002eda6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002edab  lea     rdx, aNummonitors; "NumMonitors"
0x14002edb2  lea     rcx, [rsp+4A0h+var_470]
0x14002edb7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002edbc  nop
0x14002edbd  lea     r8, [rsp+4A0h+var_470]
0x14002edc2  mov     rdx, cs:qword_1401C6370
0x14002edc9  lea     rcx, [rbp+3A0h+var_3A0]
0x14002edcd  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002edd2  nop
0x14002edd3  lea     rcx, [rsp+4A0h+var_470]
0x14002edd8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002eddd  lea     rdx, aTotalmonitorpi; "TotalMonitorPixels"
0x14002ede4  lea     rcx, [rsp+4A0h+var_470]
0x14002ede9  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002edee  nop
0x14002edef  lea     r8, [rsp+4A0h+var_470]
0x14002edf4  mov     rdx, cs:qword_1401C6370
0x14002edfb  lea     rcx, [rbp+3A0h+var_3F0]
0x14002edff  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002ee04  nop
0x14002ee05  lea     rcx, [rsp+4A0h+var_470]
0x14002ee0a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ee0f  mov     rcx, r14
0x14002ee12  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ee17  lea     rdx, [rax+458h]
0x14002ee1e  lea     rcx, [rbp+3A0h+var_1C0]
0x14002ee25  call    ??4RstringReg@mlib@@QEAAAEAV01@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::RstringReg::operator=(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002ee2a  movsd   xmm0, cs:dbl_140168980
0x14002ee32  mulsd   xmm0, xmm6
0x14002ee36  cvttsd2si rdx, xmm0
0x14002ee3b  lea     rcx, [rbp+3A0h+var_210]
0x14002ee42  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x14002ee47  mov     rcx, r14
0x14002ee4a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ee4f  mov     rbx, rax
0x14002ee52  mov     rcx, r14
0x14002ee55  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002ee5a  mov     ebx, [rbx+5E0h]
0x14002ee60  add     ebx, [rax+5D8h]
0x14002ee66  mov     rcx, r14
  ... truncated ...
```
