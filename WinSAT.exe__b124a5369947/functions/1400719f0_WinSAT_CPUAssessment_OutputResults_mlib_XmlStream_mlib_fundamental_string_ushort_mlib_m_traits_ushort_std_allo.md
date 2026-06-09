# WinSAT::CPUAssessment::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400719f0`
- end: `0x14007406a`
- name: `?OutputResults@CPUAssessment@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `9850`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001abc`
- `0x140004348`
- `0x14000449c`
- `0x140005b80`
- `0x140005d78`
- `0x140005f4c`
- `0x14000695c`
- `0x140007e3c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x1400086f8`
- `0x140008730`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016264`
- `0x140016d04`
- `0x140017af0`
- `0x14002093c`
- `0x14004fce4`
- `0x14004fe00`
- `0x1400530a8`
- `0x140056f94`
- `0x140058be8`
- `0x14005c1f0`
- `0x14005ca70`
- `0x1400603d4`
- `0x1400719f0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140071b39`
- `KERNEL32!GetLastError` at `0x140071b39`
- `KERNEL32!GetExitCodeThread` at `0x140071a90`
- `KERNEL32!GetExitCodeThread` at `0x140071a90`

## string_xrefs

- `0x14007253c`: `NumThreads`
- `0x1400725b3`: `NumThreads`
- `0x140071ce7`: `CPU-Compression2`
- `0x140071ce0`: `CPU-Compression`
- `0x140072441`: `MaxThreads`
- `0x1400724cc`: `MaxThreads`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
__int64 __fastcall WinSAT::CPUAssessment::OutputResults(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // r15d
  char v7; // bl
  unsigned int i; // r14d
  __int64 v9; // rax
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 v17; // r9
  const unsigned __int16 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  unsigned __int16 v23; // r9
  const unsigned __int16 *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  double v29; // xmm6_8
  double v30; // xmm7_8
  unsigned __int64 v31; // r12
  unsigned int v32; // ebx
  _QWORD *v33; // r14
  __int64 v34; // rcx
  unsigned __int64 v35; // rax
  int v36; // ecx
  __int64 v37; // rax
  const wchar_t *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  void **v45; // r9
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  const wchar_t *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  const wchar_t *v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  const wchar_t *v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  const wchar_t *v80; // rbx
  const wchar_t *v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  unsigned int v86; // ebx
  const wchar_t *v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  unsigned int v94; // ebx
  const wchar_t *v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // rcx
  const wchar_t *v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // r8
  __int64 v116; // rcx
  const wchar_t *v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  DWORD v122; // r8d
  __int64 v123; // r13
  __int64 v124; // r14
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rbx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // rdx
  __int64 v136; // rcx
  const wchar_t *v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // rcx
  const wchar_t *v150; // rdx
  __int64 v151; // rcx
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // rdx
  __int64 v160; // rcx
  const wchar_t *v161; // rdx
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // rdx
  __int64 v171; // rcx
  const wchar_t *v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  unsigned __int64 v181; // rbx
  __int64 v182; // rdx
  __int64 v183; // rcx
  const wchar_t *v184; // rdx
  __int64 v185; // rcx
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rax
  unsigned __int64 v193; // rbx
  __int64 v194; // rdx
  __int64 v195; // rcx
  const wchar_t *v196; // rdx
  __int64 v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rax
  __int64 v202; // rax
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rbx
  __int64 v206; // rdx
  __int64 v207; // rcx
  const wchar_t *v208; // rdx
  __int64 v209; // rcx
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // rax
  const wchar_t *v213; // rdx
  __int64 v214; // rcx
  __int64 v215; // rax
  __int64 v216; // rax
  const wchar_t *v217; // rdx
  __int64 v218; // rcx
  __int64 v219; // rax
  __int64 v220; // rax
  const wchar_t *v221; // rdx
  __int64 v222; // rcx
  __int64 v223; // rax
  __int64 v224; // rax
  DWORD ExitCode[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v227; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v228; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v229[8]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v230[8]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v231[8]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v232[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v233[8]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v234[8]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v235[8]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v236[8]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v237[8]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v238[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v239[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v240[8]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v241[8]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v242[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v243[8]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v244[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v245[8]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v246[8]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v247[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v248[8]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v249[8]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v250[8]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v251[8]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v252[8]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v253[8]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v254[8]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v255[8]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v256[8]; // [rsp+128h] [rbp+20h] BYREF
  unsigned int v257; // [rsp+130h] [rbp+28h]
  _BYTE v258[8]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v259[8]; // [rsp+140h] [rbp+38h] BYREF
  void *Block[2]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v261; // [rsp+158h] [rbp+50h]
  _BYTE v262[240]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v263[112]; // [rsp+268h] [rbp+160h] BYREF
  WCHAR Buffer[256]; // [rsp+2D8h] [rbp+1D0h] BYREF
  DWORD LastError; // [rsp+4D8h] [rbp+3D0h]
  char v266; // [rsp+4DCh] [rbp+3D4h]
  __int64 v267; // [rsp+4E0h] [rbp+3D8h]

  if ( *(_BYTE *)(a1 + 8296) )
    return (unsigned int)-2147221503;
  v7 = 1;
  for ( i = 0; ; ++i )
  {
    v9 = *(unsigned int *)(a1 + 8300);
    if ( i >= (unsigned int)v9 )
      break;
    ExitCode[0] = 0;
    if ( !GetExitCodeThread(*(HANDLE *)(*(_QWORD *)(a1 + 8LL * i + 104) + 816LL), ExitCode) )
    {
      LastError = GetLastError();
      v266 = 1;
      v267 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v262,
        a3);
      v18 = mlib::MUIStr_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x278, 524, v17);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v262, v18);
      v20 = std::basic_ostream<unsigned short>::operator<<(v19, 10);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, Buffer);
      std::endl(v21);
      v22 = *(_QWORD *)(a1 + 24);
      v24 = mlib::MUIStr_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x27A, 524, v23);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22 + 240, v24);
      v26 = std::basic_ostream<unsigned short>::operator<<(v25, 10);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, Buffer);
      std::endl(v27);
      v6 = -2147221503;
      mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v262);
      return v6;
    }
    if ( ExitCode[0] )
    {
      LastError = ExitCode[0];
      v266 = 1;
      v267 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v10 = *(_QWORD *)(a1 + 24);
      v11 = mlib::MUISpf_((mlib *)"base\\winsat\\cpu\\cpuat.cpp", (const char *)0x284, 525, i);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10 + 240, v11);
      v13 = std::endl(v12);
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v13,
        *(_QWORD *)(a1 + 8LL * i + 104) + 104LL);
      v15 = std::endl(v14);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, Buffer);
      std::endl(v16);
      v7 = 0;
    }
  }
  if ( !v7 )
  {
    v28 = mlib::MUILoader::MUILoader((mlib::MUILoader *)Block, 0x20Eu);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      a3,
      v28);
    return (unsigned int)-2147221503;
  }
  v6 = 0;
  v257 = 0;
  *(_DWORD *)(a1 + 56) = 6;
  v29 = 0.0;
  v30 = 0.0;
  *(_OWORD *)Block = 0;
  v261 = 0;
  v228 = 0;
  std::vector<SampleManager const *>::resize(Block, v9, &v228);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v229,
    64);
  v31 = -1;
  v32 = 0;
  if ( *(_DWORD *)(a1 + 8300) )
  {
    v33 = Block[0];
    while ( 1 )
    {
      v34 = *(_QWORD *)(a1 + 8LL * v32 + 104);
      v35 = *(_QWORD *)(v34 + 792);
      if ( v31 < v35 )
        v35 = v31;
      v31 = v35;
      v33[v32] = v34 + 648;
      v36 = *(_DWORD *)(a1 + 8428);
      if ( (unsigned int)(v36 - 1) <= 2 )
        break;
      if ( (unsigned int)(v36 - 4) <= 1 )
      {
        v37 = *(_QWORD *)(a1 + 8LL * v32 + 104);
        v29 = v29 + *(double *)(v37 + 824);
        v30 = v30 + *(double *)(v37 + 832);
        v38 = L"CPU-Compression2";
        if ( v36 != 5 )
          v38 = L"CPU-Compression";
LABEL_25:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          v229,
          v38);
      }
      if ( ++v32 >= *(_DWORD *)(a1 + 8300) )
        goto LABEL_27;
    }
    v39 = *(_QWORD *)(a1 + 8LL * v32 + 104);
    v29 = v29 + *(double *)(v39 + 824);
    v30 = v30 + *(double *)(v39 + 832);
    if ( v36 == 2 )
    {
      v38 = L"CPU-Encryption2";
    }
    else
    {
      v38 = L"CPU-CRC32";
      if ( v36 != 3 )
        v38 = L"CPU-Encryption";
    }
    goto LABEL_25;
  }
LABEL_27:
  if ( *(_BYTE *)(a1 + 8297) )
  {
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(
      *(_QWORD *)(a1 + 16) + 240LL,
      L"> Total BytesPerSecond        = ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v40 + 4LL) + v40 + 24) |= 0x2080u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v40 + 4LL) + v40 + 32) = 0;
    *(_QWORD *)(*(int *)(*(_QWORD *)v40 + 4LL) + v40 + 40) = 10;
    v41 = std::basic_ostream<unsigned short>::operator<<(v40);
    std::endl(v41);
    if ( *(_BYTE *)(a1 + 8297) )
    {
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(
        *(_QWORD *)(a1 + 16) + 240LL,
        L"> Total BytesPerSecond (mean) = ");
      *(_DWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 24) |= 0x2080u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 32) = 0;
      *(_QWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 40) = 10;
      v43 = std::basic_ostream<unsigned short>::operator<<(v42);
      std::endl(v43);
    }
  }
  if ( *(_WORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40)
                + 498) )
  {
    *(_QWORD *)ExitCode = 0;
    v44 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
    KeyInfo::GenDumpFileName(v44, &v227, v229);
    if ( !mlib::MCreateFile(*(LPCWSTR *)(v227 + 24), (const unsigned __int16 *)0x22, (unsigned int)ExitCode, v45) )
    {
      mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(
        v262,
        *(_QWORD *)ExitCode);
      SampleManager::DumpSamples(Block, v263);
      mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(v262);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v227);
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v255,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v46, v255);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v254,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v47, v254);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v253,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v49, v253);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"B/s");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v252,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, v252);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes per second");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v251,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, v251);
    v54 = v56;
    v53 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_43;
    v53 = L"/>";
    v54 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, v53);
LABEL_43:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v250,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v57, v250);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v249,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v58, v249);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v248,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, v248);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v61, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v247,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, v247);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v63, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v246,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v66, v246);
    v65 = v67;
    v64 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_52;
    v64 = L"/>";
    v65 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, v64);
LABEL_52:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v245,
    L"Units");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v68, v245);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v244,
    L"name");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v69, v244);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v243,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v71, v243);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v72, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v242,
    L"descrip");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v73, v242);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"cpu clock ticks");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v241,
    L"Units");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v77, v241);
    v76 = v78;
    v75 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_61;
    v75 = L"/>";
    v76 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v76, v75);
LABEL_61:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v240,
    L"MaxThreads");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v79, v240);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v80 = L"1";
  if ( !*(_BYTE *)(a1 + 8336) )
    v80 = L"NumberOfSchedulableUnits";
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, v80);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v239,
    L"MaxThreads");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v83, v239);
    v82 = v84;
    v81 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_72;
    v81 = L"/>";
    v82 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, v81);
LABEL_72:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v238,
    L"NumThreads");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v85, v238);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v86 = *(_DWORD *)(a1 + 8300);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v86);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v237,
    L"NumThreads");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v89, v237);
    v88 = v90;
    v87 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_81;
    v87 = L"/>";
    v88 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, v87);
LABEL_81:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v236,
    L"WorkingBufferSize");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v91, v236);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v235,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v92, v235);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v93, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  v94 = *(_DWORD *)(a1 + 8424);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2, v94);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v234,
    L"WorkingBufferSize");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v97, v234);
    v96 = v98;
    v95 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_90;
    v95 = L"/>";
    v96 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, v95);
LABEL_90:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v233,
    L"TotalBytesPerSecond");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v99, v233);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v232,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v100, v232);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v102 = *a2;
  v103 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)(v103 + v102 + 24) |= 0x2080u;
  *(_QWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 32) = 5;
  *(_QWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v104 = *a2;
  v105 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)(v105 + v104 + 24) |= 0x201u;
  *(_WORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 88) = 32;
  *(_QWORD *)(*(int *)(*(_QWORD *)v104 + 4LL) + v104 + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v231,
    L"TotalBytesPerSecond");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v108, v231);
    v107 = v109;
    v106 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_99;
    v106 = L"/>";
    v107 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, v106);
LABEL_99:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v230,
    L"TotalBytesPerSecondMean");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v110, v230);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    ExitCode,
    L"units");
  *((_DWORD *)a2 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v111, ExitCode);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, L"=");
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v113 = *a2;
  v114 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)(v114 + v113 + 24) |= 0x2080u;
  *(_QWORD *)(*(int *)(*(_QWORD *)v113 + 4LL) + v113 + 32) = 5;
  *(_QWORD *)(*(int *)(*(_QWORD *)v113 + 4LL) + v113 + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  std::basic_ostream<unsigned short>::operator<<(*a2);
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
  v115 = *a2;
  v116 = *(int *)(*(_QWORD *)*a2 + 4LL);
  *(_DWORD *)(v116 + v115 + 24) |= 0x201u;
  *(_WORD *)(*(int *)(*(_QWORD *)v115 + 4LL) + v115 + 88) = 32;
  *(_QWORD *)(*(int *)(*(_QWORD *)v115 + 4LL) + v115 + 40) = 0;
  mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v227,
    L"TotalBytesPerSecondMean");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v119, &v227);
    v118 = v120;
    v117 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_108;
    v117 = L"/>";
    v118 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, v117);
LABEL_108:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v227);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(ExitCode);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v230);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v231);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v232);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v233);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v234);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v235);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v236);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v237);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v238);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v239);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v240);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v241);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v242);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v243);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v244);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v245);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v246);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v247);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v248);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v249);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v250);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v251);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v252);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v253);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v254);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v255);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v256,
    L"PerCPUData");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v121, v256);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v256);
  CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
  if ( *(_DWORD *)(a1 + 8300) )
  {
    v122 = 0;
    ExitCode[0] = 0;
    while ( 1 )
    {
      v123 = v122;
      v124 = *(_QWORD *)(a1 + 8LL * v122 + 104);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v227,
        L"CPUData");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v125, &v227);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v230,
        L"CPUIndex");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v126, v230);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, ExitCode[0]);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v231,
        L"Repetitions");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v128, v231);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v129 = (__int64)(*(_QWORD *)(v124 + 656) - *(_QWORD *)(v124 + 648)) >> 3;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v129);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v232,
        L"Repetitions");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, v232);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, L">");
      }
      else if ( *((_DWORD *)a2 + 2) == 2 )
      {
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"/>");
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v233,
        L"Min");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v130, v233);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v234,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v131, v234);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v132, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v133 = *a2;
      v134 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v134 + v133 + 24) |= 0x2080u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v135 = *a2;
      v136 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v136 + v135 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v135 + 4LL) + v135 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v135 + 4LL) + v135 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v235,
        L"Min");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v141, v235);
        v138 = v142;
        v137 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_131;
        v137 = L"/>";
        v138 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v138, v137);
LABEL_131:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v236,
        L"Max");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v143, v236);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v237,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v144, v237);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v146 = *a2;
      v147 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v147 + v146 + 24) |= 0x2080u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v146 + 4LL) + v146 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v146 + 4LL) + v146 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v148 = *a2;
      v149 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v149 + v148 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v148 + 4LL) + v148 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v148 + 4LL) + v148 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v238,
        L"Max");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v152, v238);
        v151 = v153;
        v150 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_140;
        v150 = L"/>";
        v151 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, v150);
LABEL_140:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v239,
        L"Median");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v154, v239);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v240,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v155, v240);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v157 = *a2;
      v158 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v158 + v157 + 24) |= 0x2080u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v157 + 4LL) + v157 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v157 + 4LL) + v157 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v159 = *a2;
      v160 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v160 + v159 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v241,
        L"Median");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v163, v241);
        v162 = v164;
        v161 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_149;
        v161 = L"/>";
        v162 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, v161);
LABEL_149:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v242,
        L"Mean");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v165, v242);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v243,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v166, v243);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v167, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v168 = *a2;
      v169 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v169 + v168 + 24) |= 0x2080u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v170 = *a2;
      v171 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v171 + v170 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v170 + 4LL) + v170 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v170 + 4LL) + v170 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v244,
        L"Mean");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v174, v244);
        v173 = v175;
        v172 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_158;
        v172 = L"/>";
        v173 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, v172);
LABEL_158:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v245,
        L"StartTick");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v176, v245);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v246,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v177, v246);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v178, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v247,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v179, v247);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v180, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v181 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v123 + 104) + 792LL) - v31;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v181);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v182 = *a2;
      v183 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v183 + v182 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v248,
        L"StartTick");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v186, v248);
        v185 = v187;
        v184 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_167;
        v184 = L"/>";
        v185 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v185, v184);
LABEL_167:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v249,
        L"EndTick");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v188, v249);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v250,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v189, v250);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v190, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v251,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v191, v251);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v192, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v193 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v123 + 104) + 800LL) - v31;
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v193);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v194 = *a2;
      v195 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v195 + v194 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v252,
        L"EndTick");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v198, v252);
        v197 = v199;
        v196 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_176;
        v196 = L"/>";
        v197 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v197, v196);
LABEL_176:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v253,
        L"Duration");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v200, v253);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v254,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v201, v254);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v202, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"ticks");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v255,
        L"microseconds");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v203, v255);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v204, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v205 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v123 + 104) + 800LL)
           - *(_QWORD *)(*(_QWORD *)(a1 + 8 * v123 + 104) + 792LL);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v205);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v206 = *a2;
      v207 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v207 + v206 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v206 + 4LL) + v206 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v206 + 4LL) + v206 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v256,
        L"Duration");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v210, v256);
        v209 = v211;
        v208 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_185;
        v208 = L"/>";
        v209 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, v208);
LABEL_185:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v256);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v255);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v254);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v253);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v252);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v251);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v250);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v249);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v248);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v247);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v246);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v245);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v244);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v243);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v242);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v241);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v240);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v239);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v238);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v237);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v236);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v235);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v234);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v233);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v232);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v231);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v230);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v227);
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 8 * v123 + 104) + 808LL) )
        goto LABEL_196;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v259,
        L"RDTSCDeltaViolation");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v212, v259);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v258,
        L"RDTSCDeltaViolation");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v215, v258);
        v214 = v216;
        v213 = L">";
        goto LABEL_194;
      }
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        v213 = L"/>";
        v214 = *a2;
LABEL_194:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v214, v213);
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v258);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v259);
LABEL_196:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v228,
        L"CPUData");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v219, &v228);
        v218 = v220;
        v217 = L">";
        goto LABEL_202;
      }
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        v217 = L"/>";
        v218 = *a2;
LABEL_202:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v218, v217);
      }
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v228);
      v122 = ExitCode[0] + 1;
      ExitCode[0] = v122;
      if ( v122 >= *(_DWORD *)(a1 + 8300) )
      {
        v6 = v257;
        break;
      }
    }
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v228,
    L"PerCPUData");
  --*((_DWORD *)a2 + 3);
  if ( *((_DWORD *)a2 + 2) == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v223, &v228);
    v222 = v224;
    v221 = L">";
  }
  else
  {
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_212;
    v221 = L"/>";
    v222 = *a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v222, v221);
LABEL_212:
  *((_DWORD *)a2 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v228);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v229);
  if ( Block[0] )
    operator delete(Block[0]);
  return v6;
}

```

## disassembly

```asm
0x1400719f0  mov     rax, rsp
0x1400719f3  mov     [rax+20h], rbx
0x1400719f7  push    rbp
0x1400719f8  push    rsi
0x1400719f9  push    rdi
0x1400719fa  push    r12
0x1400719fc  push    r13
0x1400719fe  push    r14
0x140071a00  push    r15
0x140071a02  lea     rbp, [rax-488h]
0x140071a09  sub     rsp, 550h
0x140071a10  movaps  xmmword ptr [rax-48h], xmm6
0x140071a14  movaps  xmmword ptr [rax-58h], xmm7
0x140071a18  movaps  xmmword ptr [rax-68h], xmm8
0x140071a1d  movaps  xmmword ptr [rax-78h], xmm9
0x140071a22  movaps  xmmword ptr [rax-88h], xmm10
0x140071a2a  movaps  xmmword ptr [rax-98h], xmm11
0x140071a32  mov     rax, cs:__security_cookie
0x140071a39  xor     rax, rsp
0x140071a3c  mov     [rbp+480h+var_A0], rax
0x140071a43  mov     r12, r8
0x140071a46  mov     rdi, rdx
0x140071a49  mov     rsi, rcx
0x140071a4c  xor     r13d, r13d
0x140071a4f  cmp     [rcx+2068h], r13b
0x140071a56  jz      short loc_140071A63
0x140071a58  mov     r15d, 80040001h
0x140071a5e  jmp     loc_14007401F
0x140071a63  mov     bl, 1
0x140071a65  mov     r14d, r13d
0x140071a68  mov     eax, [rsi+206Ch]
0x140071a6e  cmp     r14d, eax
0x140071a71  jnb     loc_140071C12
0x140071a77  mov     [rsp+580h+ExitCode], r13d
0x140071a7c  mov     r15d, r14d
0x140071a7f  mov     rcx, [rsi+r15*8+68h]
0x140071a84  lea     rdx, [rsp+580h+ExitCode]; lpExitCode
0x140071a89  mov     rcx, [rcx+330h]; hThread
0x140071a90  call    cs:__imp_GetExitCodeThread
0x140071a96  test    eax, eax
0x140071a98  jz      loc_140071B39
0x140071a9e  mov     eax, [rsp+580h+ExitCode]
0x140071aa2  test    eax, eax
0x140071aa4  jz      loc_140071B31
0x140071aaa  mov     [rbp+480h+var_B0], eax
0x140071ab0  mov     [rbp+480h+var_AC], 1
0x140071ab7  mov     [rbp+480h+var_A8], r13
0x140071abe  lea     rcx, [rbp+480h+Buffer]; lpBuffer
0x140071ac5  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140071aca  mov     rbx, [rsi+18h]
0x140071ace  mov     r8d, 20Dh; int
0x140071ad4  mov     r9d, r14d; unsigned __int16
0x140071ad7  lea     edx, [r8+77h]; char *
0x140071adb  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071ae2  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140071ae7  mov     rdx, rax
0x140071aea  lea     rcx, [rbx+0F0h]
0x140071af1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071af6  mov     rcx, rax
0x140071af9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071afe  mov     rdx, [rsi+r15*8+68h]
0x140071b03  add     rdx, 68h ; 'h'
0x140071b07  mov     rcx, rax
0x140071b0a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071b0f  mov     rcx, rax
0x140071b12  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071b17  lea     rdx, [rbp+480h+Buffer]
0x140071b1e  mov     rcx, rax
0x140071b21  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071b26  mov     rcx, rax
0x140071b29  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071b2e  mov     bl, r13b
0x140071b31  inc     r14d
0x140071b34  jmp     loc_140071A68
0x140071b39  call    cs:__imp_GetLastError
0x140071b3f  mov     [rbp+480h+var_B0], eax
0x140071b45  mov     [rbp+480h+var_AC], 1
0x140071b4c  mov     [rbp+480h+var_A8], r13
0x140071b53  lea     rcx, [rbp+480h+Buffer]; lpBuffer
0x140071b5a  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140071b5f  mov     rdx, r12
0x140071b62  lea     rcx, [rbp+480h+var_410]
0x140071b66  call    ??0?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAA@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x140071b6b  nop
0x140071b6c  mov     edi, 20Ch
0x140071b71  mov     r8d, edi; int
0x140071b74  lea     edx, [rdi+6Ch]; char *
0x140071b77  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071b7e  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140071b83  mov     rdx, rax
0x140071b86  lea     rcx, [rbp+480h+var_410]
0x140071b8a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071b8f  mov     r14d, 0Ah
0x140071b95  mov     edx, r14d
0x140071b98  mov     rcx, rax
0x140071b9b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140071ba0  lea     rdx, [rbp+480h+Buffer]
0x140071ba7  mov     rcx, rax
0x140071baa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071baf  mov     rcx, rax
0x140071bb2  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071bb7  mov     rbx, [rsi+18h]
0x140071bbb  mov     r8d, edi; int
0x140071bbe  lea     edx, [rdi+6Eh]; char *
0x140071bc1  lea     rcx, aBaseWinsatCpuC; "base\\winsat\\cpu\\cpuat.cpp"
0x140071bc8  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140071bcd  mov     rdx, rax
0x140071bd0  lea     rcx, [rbx+0F0h]
0x140071bd7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071bdc  mov     edx, r14d
0x140071bdf  mov     rcx, rax
0x140071be2  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140071be7  lea     rdx, [rbp+480h+Buffer]
0x140071bee  mov     rcx, rax
0x140071bf1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071bf6  mov     rcx, rax
0x140071bf9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071bfe  mov     r15d, 80040001h
0x140071c04  lea     rcx, [rbp+480h+var_410]
0x140071c08  call    ??_D?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAAXXZ; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x140071c0d  jmp     loc_14007401F
0x140071c12  test    bl, bl
0x140071c14  jnz     short loc_140071C34
0x140071c16  mov     edx, 20Eh; unsigned __int16
0x140071c1b  lea     rcx, [rbp+480h+Block]; this
0x140071c1f  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x140071c24  mov     rdx, rax
0x140071c27  mov     rcx, r12
0x140071c2a  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x140071c2f  jmp     loc_140071A58
0x140071c34  mov     r15d, r13d
0x140071c37  mov     [rbp+480h+var_458], r13d
0x140071c3b  mov     dword ptr [rsi+38h], 6
0x140071c42  xorps   xmm6, xmm6
0x140071c45  xorps   xmm7, xmm7
0x140071c48  xorps   xmm0, xmm0
0x140071c4b  movdqu  xmmword ptr [rbp+480h+Block], xmm0
0x140071c50  mov     [rbp+480h+var_430], r13
0x140071c54  mov     [rsp+580h+var_540], r13
0x140071c59  mov     rdx, rax
0x140071c5c  lea     r8, [rsp+580h+var_540]
0x140071c61  lea     rcx, [rbp+480h+Block]
0x140071c65  call    ?resize@?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@QEAAX_KAEBQEBVSampleManager@@@Z; std::vector<SampleManager const *>::resize(unsigned __int64,SampleManager const * const &)
0x140071c6a  mov     edx, 40h ; '@'
0x140071c6f  lea     rcx, [rsp+580h+var_538]
0x140071c74  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140071c79  nop
0x140071c7a  or      r12, 0FFFFFFFFFFFFFFFFh
0x140071c7e  mov     ebx, r13d
0x140071c81  cmp     [rsi+206Ch], r13d
0x140071c88  jbe     loc_140071D45
0x140071c8e  mov     r14, [rbp+480h+Block]
0x140071c92  mov     edx, ebx
0x140071c94  mov     rcx, [rsi+rdx*8+68h]
0x140071c99  mov     rax, [rcx+318h]
0x140071ca0  cmp     r12, rax
0x140071ca3  cmovb   rax, r12
0x140071ca7  mov     r12, rax
0x140071caa  lea     rax, [rcx+288h]
0x140071cb1  mov     [r14+rdx*8], rax
0x140071cb5  mov     ecx, [rsi+20ECh]
0x140071cbb  lea     eax, [rcx-1]
0x140071cbe  cmp     eax, 2
0x140071cc1  jbe     short loc_140071CF7
0x140071cc3  lea     eax, [rcx-4]
0x140071cc6  cmp     eax, 1
0x140071cc9  ja      short loc_140071D37
0x140071ccb  mov     rax, [rsi+rdx*8+68h]
0x140071cd0  addsd   xmm6, qword ptr [rax+338h]
0x140071cd8  addsd   xmm7, qword ptr [rax+340h]
0x140071ce0  lea     rax, aCpuCompression; "CPU-Compression"
0x140071ce7  lea     rdx, aCpuCompression_1; "CPU-Compression2"
0x140071cee  cmp     ecx, 5
0x140071cf1  cmovnz  rdx, rax
0x140071cf5  jmp     short loc_140071D2D
0x140071cf7  mov     rax, [rsi+rdx*8+68h]
0x140071cfc  addsd   xmm6, qword ptr [rax+338h]
0x140071d04  addsd   xmm7, qword ptr [rax+340h]
0x140071d0c  cmp     ecx, 2
0x140071d0f  jnz     short loc_140071D1A
0x140071d11  lea     rdx, aCpuEncryption2; "CPU-Encryption2"
0x140071d18  jmp     short loc_140071D2D
0x140071d1a  cmp     ecx, 3
0x140071d1d  lea     rdx, aCpuCrc32; "CPU-CRC32"
0x140071d24  jz      short loc_140071D2D
0x140071d26  lea     rdx, aCpuEncryption; "CPU-Encryption"
0x140071d2d  lea     rcx, [rsp+580h+var_538]
0x140071d32  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x140071d37  inc     ebx
0x140071d39  cmp     ebx, [rsi+206Ch]
0x140071d3f  jb      loc_140071C92
0x140071d45  cmp     [rsi+2069h], r13b
0x140071d4c  jz      loc_140071E06
0x140071d52  mov     rcx, [rsi+10h]
0x140071d56  mov     ebx, 0F0h
0x140071d5b  add     rcx, rbx
0x140071d5e  lea     rdx, aTotalBytespers_0; "> Total BytesPerSecond        = "
0x140071d65  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071d6a  mov     rdx, rax
0x140071d6d  mov     rax, [rax]
0x140071d70  movsxd  rcx, dword ptr [rax+4]
0x140071d74  or      dword ptr [rcx+rdx+18h], 2080h
0x140071d7c  mov     rax, [rdx]
0x140071d7f  movsxd  rcx, dword ptr [rax+4]
0x140071d83  mov     [rcx+rdx+20h], r13
0x140071d88  mov     rax, [rdx]
0x140071d8b  movsxd  rcx, dword ptr [rax+4]
0x140071d8f  mov     r14d, 0Ah
0x140071d95  mov     [rcx+rdx+28h], r14
0x140071d9a  movaps  xmm1, xmm6
0x140071d9d  mov     rcx, rdx
0x140071da0  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x140071da5  mov     rcx, rax
0x140071da8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071dad  cmp     [rsi+2069h], r13b
0x140071db4  jz      short loc_140071E06
0x140071db6  mov     rcx, [rsi+10h]
0x140071dba  add     rcx, rbx
0x140071dbd  lea     rdx, aTotalBytespers; "> Total BytesPerSecond (mean) = "
0x140071dc4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071dc9  mov     rdx, rax
0x140071dcc  mov     rax, [rax]
0x140071dcf  movsxd  rcx, dword ptr [rax+4]
0x140071dd3  or      dword ptr [rcx+rdx+18h], 2080h
0x140071ddb  mov     rax, [rdx]
0x140071dde  movsxd  rcx, dword ptr [rax+4]
0x140071de2  mov     [rcx+rdx+20h], r13
0x140071de7  mov     rax, [rdx]
0x140071dea  movsxd  rcx, dword ptr [rax+4]
0x140071dee  mov     [rcx+rdx+28h], r14
0x140071df3  movaps  xmm1, xmm7
0x140071df6  mov     rcx, rdx
0x140071df9  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x140071dfe  mov     rcx, rax
0x140071e01  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140071e06  lea     r14, [rsi+28h]
0x140071e0a  mov     rcx, r14
0x140071e0d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140071e12  cmp     [rax+1F2h], r13w
0x140071e1a  jz      short loc_140071E8C
0x140071e1c  mov     qword ptr [rsp+580h+ExitCode], r13
0x140071e21  mov     rcx, r14
0x140071e24  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140071e29  lea     r8, [rsp+580h+var_538]
0x140071e2e  lea     rdx, [rsp+580h+var_548]
0x140071e33  mov     rcx, rax
0x140071e36  call    ?GenDumpFileName@KeyInfo@@QEBA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBV23@@Z; KeyInfo::GenDumpFileName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071e3b  nop
0x140071e3c  lea     r8, [rsp+580h+ExitCode]; unsigned int
0x140071e41  mov     edx, 22h ; '"'; unsigned __int16 *
0x140071e46  mov     rcx, [rsp+580h+var_548]
0x140071e4b  mov     rcx, [rcx+18h]; lpFileName
0x140071e4f  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x140071e54  test    eax, eax
0x140071e56  jnz     short loc_140071E82
0x140071e58  mov     rdx, qword ptr [rsp+580h+ExitCode]
0x140071e5d  lea     rcx, [rbp+480h+var_410]
0x140071e61  call    ??0?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAA@PEAX_N_K@Z; mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(void *,bool,unsigned __int64)
0x140071e66  nop
0x140071e67  lea     rdx, [rbp+480h+var_320]
0x140071e6e  lea     rcx, [rbp+480h+Block]
0x140071e72  call    ?DumpSamples@SampleManager@@SAXAEAV?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@3@@Z; SampleManager::DumpSamples(std::vector<SampleManager const *> &,std::ostream &)
0x140071e77  nop
0x140071e78  lea     rcx, [rbp+480h+var_410]
0x140071e7c  call    ??_D?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAAXXZ; mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(void)
0x140071e81  nop
0x140071e82  lea     rcx, [rsp+580h+var_548]
0x140071e87  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140071e8c  lea     rdx, aUnits; "Units"
0x140071e93  lea     rcx, [rbp+480h+var_468]
0x140071e97  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140071e9c  nop
0x140071e9d  cmp     dword ptr [rdi+8], 2
0x140071ea1  jnz     short loc_140071EB2
0x140071ea3  lea     rdx, asc_14012B480; ">"
0x140071eaa  mov     rcx, [rdi]
0x140071ead  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071eb2  mov     dword ptr [rdi+8], 2
0x140071eb9  mov     rcx, rdi; this
0x140071ebc  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140071ec1  lea     rdx, asc_14012B484; "<"
0x140071ec8  mov     rcx, [rdi]
0x140071ecb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071ed0  mov     rcx, rax
0x140071ed3  lea     rdx, [rbp+480h+var_468]
0x140071ed7  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140071edc  mov     ebx, 1
0x140071ee1  add     [rdi+0Ch], ebx
0x140071ee4  mov     [rdi+11h], r13b
0x140071ee8  lea     rdx, aName_0; "name"
0x140071eef  lea     rcx, [rbp+480h+var_470]
0x140071ef3  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140071ef8  nop
0x140071ef9  mov     dword ptr [rdi+8], 3
0x140071f00  lea     rdx, asc_14012B49C; " "
0x140071f07  mov     rcx, [rdi]
0x140071f0a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140071f0f  mov     rcx, rax
0x140071f12  lea     rdx, [rbp+480h+var_470]
0x140071f16  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
  ... truncated ...
```
