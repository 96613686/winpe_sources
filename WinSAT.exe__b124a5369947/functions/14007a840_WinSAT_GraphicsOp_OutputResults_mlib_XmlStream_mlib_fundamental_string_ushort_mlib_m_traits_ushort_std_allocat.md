# WinSAT::GraphicsOp::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14007a840`
- end: `0x14007da9a`
- name: `?OutputResults@GraphicsOp@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `12890`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140004650`
- `0x140004ae4`
- `0x140005d78`
- `0x140008064`
- `0x140008178`
- `0x1400083a4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x14001362c`
- `0x140016480`
- `0x140016d04`
- `0x14001bec8`
- `0x140021c58`
- `0x140079d34`
- `0x14007a840`

## string_xrefs

- `0x14007bb32`: `WorkingSetBeforeDevCreate`
- `0x14007bba1`: `WorkingSetBeforeDevCreate`
- `0x14007d468`: `WorkingSetBeforeDevCreate`
- `0x14007d4d9`: `WorkingSetBeforeDevCreate`
- `0x14007bc0f`: `WorkingSetAfterDevCreate`
- `0x14007bc7e`: `WorkingSetAfterDevCreate`
- `0x14007d4fc`: `WorkingSetAfterDevCreate`
- `0x14007d573`: `WorkingSetAfterDevCreate`
- `0x14007b7c8`: `DevCreateEndTime`
- `0x14007b835`: `DevCreateEndTime`
- `0x14007d0f1`: `DevCreateEndTime`
- `0x14007d163`: `DevCreateEndTime`
- `0x14007b6ef`: `DevCreateStartTime`
- `0x14007b75c`: `DevCreateStartTime`
- `0x14007d013`: `DevCreateStartTime`
- `0x14007d085`: `DevCreateStartTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=109
__int64 __fastcall WinSAT::GraphicsOp::OutputResults(__int64 a1, _QWORD *a2)
{
  int v5; // ecx
  unsigned int v6; // edi
  __int64 v7; // rax
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  mlib::XmlStream *v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rbx
  const wchar_t *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  const wchar_t *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  const wchar_t *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  const wchar_t *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  const wchar_t *v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  const wchar_t *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  const wchar_t *v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rax
  const wchar_t *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  const wchar_t *v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  const wchar_t *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  const wchar_t *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  const wchar_t *v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rax
  const wchar_t *v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  const wchar_t *v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rax
  const wchar_t *v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rax
  const wchar_t *v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rax
  const wchar_t *v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rax
  const wchar_t *v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // rax
  __int64 v96; // rax
  const wchar_t *v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  const wchar_t *v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rax
  const wchar_t *v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rax
  __int64 v108; // rax
  const wchar_t *v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // rax
  __int64 v112; // rax
  const wchar_t *v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  const wchar_t *v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  mlib::XmlStream *v122; // rbx
  __int64 v123; // rax
  _QWORD *v124; // rdi
  const wchar_t *v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // rax
  char v129; // bl
  __int64 v130; // rdx
  const wchar_t *v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // rax
  __int64 v134; // rax
  unsigned int v135; // ebx
  const wchar_t *v136; // rdx
  __int64 v137; // rcx
  __int64 v138; // rax
  __int64 v139; // rax
  unsigned int v140; // ebx
  const wchar_t *v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rax
  const wchar_t *v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // rax
  __int64 v148; // rax
  const wchar_t *v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // rax
  __int64 v152; // rax
  unsigned int v153; // ebx
  const wchar_t *v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // rax
  __int64 v157; // rax
  unsigned int v158; // ebx
  const wchar_t *v159; // rdx
  __int64 v160; // rcx
  __int64 v161; // rax
  __int64 v162; // rax
  const wchar_t *v163; // rdx
  __int64 v164; // rcx
  __int64 v165; // rax
  __int64 v166; // rax
  const wchar_t *v167; // rdx
  __int64 v168; // rcx
  __int64 v169; // rax
  __int64 v170; // rax
  const wchar_t *v171; // rdx
  __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rax
  const wchar_t *v175; // rdx
  __int64 v176; // rcx
  __int64 v177; // rax
  __int64 v178; // rax
  const wchar_t *v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // rax
  __int64 v182; // rax
  const wchar_t *v183; // rdx
  __int64 v184; // rcx
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rbx
  const wchar_t *v188; // rdx
  __int64 v189; // rcx
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rbx
  const wchar_t *v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rbx
  const wchar_t *v198; // rdx
  __int64 v199; // rcx
  __int64 v200; // rax
  __int64 v201; // rax
  __int64 v202; // rbx
  const wchar_t *v203; // rdx
  __int64 v204; // rcx
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rbx
  const wchar_t *v208; // rdx
  __int64 v209; // rcx
  __int64 v210; // rax
  __int64 v211; // rax
  unsigned int v212; // ebx
  const wchar_t *v213; // rdx
  __int64 v214; // rcx
  __int64 v215; // rax
  __int64 v216; // rax
  unsigned int v217; // ebx
  __int64 v218; // rax
  unsigned int v219; // ebx
  __int64 v220; // rax
  unsigned int v221; // ebx
  __int64 v222; // rax
  __int64 v223; // rbx
  __int64 v224; // rax
  __int64 v225; // rbx
  __int64 v226; // rax
  _BYTE v227[8]; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE v228[8]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v229[8]; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v230[8]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v231[8]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v232[8]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v233[8]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v234[8]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v235[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v236[8]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v237[8]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v238[8]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v239[8]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v240[8]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v241[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v242[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v243[8]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v244[8]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v245[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v246[8]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v247[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v248[8]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v249[8]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v250[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v251[8]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v252[8]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v253[8]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v254[8]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v255[8]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v256[8]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v257[8]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v258[8]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v259[8]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v260[8]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v261[8]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v262[8]; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v263[8]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v264[8]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v265[8]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v266[8]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v267[8]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v268[8]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE v269[8]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v270[8]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v271[8]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v272[8]; // [rsp+190h] [rbp+88h] BYREF
  _BYTE v273[8]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v274[8]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v275[8]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v276[8]; // [rsp+1B0h] [rbp+A8h] BYREF
  _BYTE v277[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v278[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  _BYTE v279[32]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v280; // [rsp+228h] [rbp+120h] BYREF
  char v281; // [rsp+240h] [rbp+138h] BYREF

  if ( *(_DWORD *)(a1 + 56) != 6 )
    return 2147745793LL;
  v5 = *(_DWORD *)(a1 + 296);
  if ( v5 )
  {
    if ( v5 == 1 )
      v6 = 10;
    else
      v6 = 0;
  }
  else
  {
    v6 = 9;
  }
  if ( *(_DWORD *)(a1 + 288) == 1 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v278,
      L"DXVersion");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v7, v278);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::basic_ostream<unsigned short>::operator<<(*a2, v6);
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v277,
      L"DXVersion");
    --*((_DWORD *)a2 + 3);
    if ( *((_DWORD *)a2 + 2) == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
      v9 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
             v10,
             v277);
      v8 = L">";
    }
    else
    {
      if ( *((_DWORD *)a2 + 2) != 2 )
        goto LABEL_18;
      v8 = L"/>";
      v9 = *a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, v8);
LABEL_18:
    *((_DWORD *)a2 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v276,
      L"Results");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v11, v276);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v275,
      L"CmdLine");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, v275);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    v13 = (mlib::XmlStream *)mlib::XmlStream::operator<<<void>(a2, mlib::BeginCData);
    v280 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v280,
      *(_QWORD *)(a1 + 280));
    v14 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(v13);
    v15 = (_QWORD *)mlib::XmlStream::operator<<<void>(v14, mlib::EndCData);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v274,
      L"CmdLine");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v17 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v18,
              v274);
      v16 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_29;
      v16 = L"/>";
      v17 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, v16);
LABEL_29:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v273,
      L"Valid");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v19, v273);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    LOBYTE(v20) = 1;
    std::basic_ostream<unsigned short>::operator<<(*v15, v20);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v272,
      L"Valid");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v22 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v23,
              v272);
      v21 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_38;
      v21 = L"/>";
      v22 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, v21);
LABEL_38:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v271,
      L"HRESULT");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v24, v271);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 0);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v270,
      L"HRESULT");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v26 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v27,
              v270);
      v25 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_47;
      v25 = L"/>";
      v26 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, v25);
LABEL_47:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v269,
      L"TierNum");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v28, v269);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v268,
      L"TierNum");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v30 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v31,
              v268);
      v29 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_56;
      v29 = L"/>";
      v30 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, v29);
LABEL_56:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v267,
      L"FPS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v32, v267);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v266,
      L"FPS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v34 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v35,
              v266);
      v33 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_65;
      v33 = L"/>";
      v34 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, v33);
LABEL_65:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v265,
      L"TierFPS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v36, v265);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v264,
      L"TierFPS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v38 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v39,
              v264);
      v37 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_74;
      v37 = L"/>";
      v38 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, v37);
LABEL_74:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v263,
      L"FramesRendered");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v40, v263);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v262,
      L"FramesRendered");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v42 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v43,
              v262);
      v41 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_83;
      v41 = L"/>";
      v42 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, v41);
LABEL_83:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v261,
      L"TierFramesRendered");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v44, v261);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v260,
      L"TierFramesRendered");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v46 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v47,
              v260);
      v45 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_92;
      v45 = L"/>";
      v46 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, v45);
LABEL_92:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v259,
      L"AverageFrameTimeMS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v48, v259);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v258,
      L"AverageFrameTimeMS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v50 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v51,
              v258);
      v49 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_101;
      v49 = L"/>";
      v50 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, v49);
LABEL_101:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v257,
      L"TierAverageFrameTimeMS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, v257);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v256,
      L"TierAverageFrameTimeMS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v54 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v55,
              v256);
      v53 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_110;
      v53 = L"/>";
      v54 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, v53);
LABEL_110:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v255,
      L"StDevFrameTimeMS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v56, v255);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v254,
      L"StDevFrameTimeMS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v58 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v59,
              v254);
      v57 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_119;
      v57 = L"/>";
      v58 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v58, v57);
LABEL_119:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v253,
      L"TierStDevFrameTimeMS");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, v253);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v252,
      L"TierStDevFrameTimeMS");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v62 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v63,
              v252);
      v61 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_128;
      v61 = L"/>";
      v62 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, v61);
LABEL_128:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v251,
      L"Duration");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v64, v251);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v250,
      L"Duration");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v66 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v67,
              v250);
      v65 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_137;
      v65 = L"/>";
      v66 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v66, v65);
LABEL_137:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v249,
      L"TierDuration");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v68, v249);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v248,
      L"TierDuration");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v70 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v71,
              v248);
      v69 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_146;
      v69 = L"/>";
      v70 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v70, v69);
LABEL_146:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v247,
      L"StartTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v72, v247);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v246,
      L"StartTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v74 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v75,
              v246);
      v73 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_155;
      v73 = L"/>";
      v74 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, v73);
LABEL_155:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v245,
      L"DevCreateStartTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v76, v245);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v244,
      L"DevCreateStartTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v78 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v79,
              v244);
      v77 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_164;
      v77 = L"/>";
      v78 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v78, v77);
LABEL_164:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v243,
      L"DevCreateEndTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v80, v243);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v242,
      L"DevCreateEndTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v82 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v83,
              v242);
      v81 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_173;
      v81 = L"/>";
      v82 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, v81);
LABEL_173:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v241,
      L"DevFirstPresentEndTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v84, v241);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v240,
      L"DevFirstPresentEndTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v86 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v87,
              v240);
      v85 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_182;
      v85 = L"/>";
      v86 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v86, v85);
LABEL_182:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v239,
      L"TierStartTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v88, v239);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v238,
      L"TierStartTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v90 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v91,
              v238);
      v89 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_191;
      v89 = L"/>";
      v90 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v90, v89);
LABEL_191:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v237,
      L"WorkingSetAtStart");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v92, v237);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v236,
      L"WorkingSetAtStart");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v94 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v95,
              v236);
      v93 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_200;
      v93 = L"/>";
      v94 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, v93);
LABEL_200:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v235,
      L"WorkingSetBeforeDevCreate");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v96, v235);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v234,
      L"WorkingSetBeforeDevCreate");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v98 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
              v99,
              v234);
      v97 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_209;
      v97 = L"/>";
      v98 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, v97);
LABEL_209:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v233,
      L"WorkingSetAfterDevCreate");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v100, v233);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v232,
      L"WorkingSetAfterDevCreate");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v102 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v103,
               v232);
      v101 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_218;
      v101 = L"/>";
      v102 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v102, v101);
LABEL_218:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v231,
      L"WorkingSetAtEnd");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v104, v231);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v230,
      L"WorkingSetAtEnd");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v106 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v107,
               v230);
      v105 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_227;
      v105 = L"/>";
      v106 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v106, v105);
LABEL_227:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v229,
      L"EndTime");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v108, v229);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v228,
      L"EndTime");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v110 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v111,
               v228);
      v109 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
        goto LABEL_236;
      v109 = L"/>";
      v110 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, v109);
LABEL_236:
    *((_DWORD *)v15 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v227,
      L"Frequency");
    if ( *((_DWORD *)v15 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L">");
    *((_DWORD *)v15 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v15);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v112, v227);
    ++*((_DWORD *)v15 + 3);
    *((_BYTE *)v15 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v15);
    std::basic_ostream<unsigned short>::operator<<(*v15, 42);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v281,
      L"Frequency");
    --*((_DWORD *)v15 + 3);
    if ( *((_DWORD *)v15 + 2) == 1 )
    {
      if ( !*((_BYTE *)v15 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v15);
      *((_BYTE *)v15 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v15, L"</");
      v114 = ((__int64 (__fastcall *)(__int64, char *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v115,
               &v281);
      v113 = L">";
    }
    else
    {
      if ( *((_DWORD *)v15 + 2) != 2 )
      {
LABEL_245:
        *((_DWORD *)v15 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v281);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v227);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v228);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v229);
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
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v256);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v257);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v258);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v259);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v260);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v261);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v262);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v263);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v264);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v265);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v266);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v267);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v268);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v269);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v270);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v271);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v272);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v273);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v274);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v275);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v276);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v277);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v278);
        goto LABEL_246;
      }
      v113 = L"/>";
      v114 = *v15;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, v113);
    goto LABEL_245;
  }
LABEL_246:
  if ( *(_DWORD *)(a1 + 288) == 2 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v227,
      L"DXVersion");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v116, v227);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
    std::basic_ostream<unsigned short>::operator<<(*a2, v6);
    mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v228,
      L"DXVersion");
    --*((_DWORD *)a2 + 3);
    if ( *((_DWORD *)a2 + 2) == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
      v118 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v119,
               v228);
      v117 = L">";
    }
    else
    {
      if ( *((_DWORD *)a2 + 2) != 2 )
        goto LABEL_256;
      v117 = L"/>";
      v118 = *a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, v117);
LABEL_256:
    *((_DWORD *)a2 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v229,
      L"Results");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v120, v229);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v230,
      L"CmdLine");
    if ( *((_DWORD *)a2 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
    *((_DWORD *)a2 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v121, v230);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    v122 = (mlib::XmlStream *)mlib::XmlStream::operator<<<void>(a2, mlib::BeginCData);
    v280 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v280,
      *(_QWORD *)(a1 + 280));
    v123 = mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(v122);
    v124 = (_QWORD *)mlib::XmlStream::operator<<<void>(v123, mlib::EndCData);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v231,
      L"CmdLine");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v126 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v127,
               v231);
      v125 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_267;
      v125 = L"/>";
      v126 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v126, v125);
LABEL_267:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v232,
      L"Valid");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v128, v232);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v129 = *(_BYTE *)(a1 + 260);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    LOBYTE(v130) = v129;
    std::basic_ostream<unsigned short>::operator<<(*v124, v130);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v233,
      L"Valid");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v132 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v133,
               v233);
      v131 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_276;
      v131 = L"/>";
      v132 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v132, v131);
LABEL_276:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v234,
      L"HRESULT");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v134, v234);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v135 = *(_DWORD *)(a1 + 256);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v135);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v235,
      L"HRESULT");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v137 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v138,
               v235);
      v136 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_285;
      v136 = L"/>";
      v137 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, v136);
LABEL_285:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v236,
      L"TierNum");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, v236);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v140 = *(_DWORD *)(a1 + 112);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v140);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v237,
      L"TierNum");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v142 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v143,
               v237);
      v141 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_294;
      v141 = L"/>";
      v142 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, v141);
LABEL_294:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v238,
      L"FPS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v144, v238);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v239,
      L"FPS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v146 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v147,
               v239);
      v145 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_303;
      v145 = L"/>";
      v146 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v146, v145);
LABEL_303:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v240,
      L"TierFPS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v148, v240);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v241,
      L"TierFPS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v150 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v151,
               v241);
      v149 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_312;
      v149 = L"/>";
      v150 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, v149);
LABEL_312:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v242,
      L"FramesRendered");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v152, v242);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v153 = *(_DWORD *)(a1 + 104);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v153);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v243,
      L"FramesRendered");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v155 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v156,
               v243);
      v154 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_321;
      v154 = L"/>";
      v155 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v155, v154);
LABEL_321:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v244,
      L"TierFramesRendered");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v157, v244);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v158 = *(_DWORD *)(a1 + 108);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v158);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v245,
      L"TierFramesRendered");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v160 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v161,
               v245);
      v159 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_330;
      v159 = L"/>";
      v160 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, v159);
LABEL_330:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v246,
      L"AverageFrameTimeMS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v162, v246);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v247,
      L"AverageFrameTimeMS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v164 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v165,
               v247);
      v163 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_339;
      v163 = L"/>";
      v164 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v164, v163);
LABEL_339:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v248,
      L"TierAverageFrameTimeMS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v166, v248);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v249,
      L"TierAverageFrameTimeMS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v168 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v169,
               v249);
      v167 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_348;
      v167 = L"/>";
      v168 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, v167);
LABEL_348:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v250,
      L"StDevFrameTimeMS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v170, v250);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v251,
      L"StDevFrameTimeMS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v172 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v173,
               v251);
      v171 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_357;
      v171 = L"/>";
      v172 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v172, v171);
LABEL_357:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v252,
      L"TierStDevFrameTimeMS");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v174, v252);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v253,
      L"TierStDevFrameTimeMS");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v176 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v177,
               v253);
      v175 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_366;
      v175 = L"/>";
      v176 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v176, v175);
LABEL_366:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v254,
      L"Duration");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v178, v254);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v255,
      L"Duration");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v180 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v181,
               v255);
      v179 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_375;
      v179 = L"/>";
      v180 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v180, v179);
LABEL_375:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v256,
      L"TierDuration");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v182, v256);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v257,
      L"TierDuration");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v184 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v185,
               v257);
      v183 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_384;
      v183 = L"/>";
      v184 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v184, v183);
LABEL_384:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v258,
      L"StartTime");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v186, v258);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v187 = *(_QWORD *)(a1 + 176);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v187);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v259,
      L"StartTime");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v189 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v190,
               v259);
      v188 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_393;
      v188 = L"/>";
      v189 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v189, v188);
LABEL_393:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v260,
      L"DevCreateStartTime");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v191, v260);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v192 = *(_QWORD *)(a1 + 184);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v192);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v261,
      L"DevCreateStartTime");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v194 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v195,
               v261);
      v193 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_402;
      v193 = L"/>";
      v194 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v194, v193);
LABEL_402:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v262,
      L"DevCreateEndTime");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v196, v262);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v197 = *(_QWORD *)(a1 + 192);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v197);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v263,
      L"DevCreateEndTime");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v199 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v200,
               v263);
      v198 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_411;
      v198 = L"/>";
      v199 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v199, v198);
LABEL_411:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v264,
      L"DevFirstPresentEndTime");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v201, v264);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v202 = *(_QWORD *)(a1 + 200);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v202);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v265,
      L"DevFirstPresentEndTime");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v204 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v205,
               v265);
      v203 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_420;
      v203 = L"/>";
      v204 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v204, v203);
LABEL_420:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v266,
      L"TierStartTime");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v206, v266);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v207 = *(_QWORD *)(a1 + 208);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v207);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v267,
      L"TierStartTime");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v209 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v210,
               v267);
      v208 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
        goto LABEL_429;
      v208 = L"/>";
      v209 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, v208);
LABEL_429:
    *((_DWORD *)v124 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v268,
      L"WorkingSetAtStart");
    if ( *((_DWORD *)v124 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
    *((_DWORD *)v124 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v124);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v211, v268);
    ++*((_DWORD *)v124 + 3);
    *((_BYTE *)v124 + 17) = 0;
    v212 = *(_DWORD *)(a1 + 232);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
    std::basic_ostream<unsigned short>::operator<<(*v124, v212);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v269,
      L"WorkingSetAtStart");
    --*((_DWORD *)v124 + 3);
    if ( *((_DWORD *)v124 + 2) == 1 )
    {
      if ( !*((_BYTE *)v124 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
      *((_BYTE *)v124 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"</");
      v214 = ((__int64 (__fastcall *)(__int64, _BYTE *))mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)(
               v215,
               v269);
      v213 = L">";
    }
    else
    {
      if ( *((_DWORD *)v124 + 2) != 2 )
      {
LABEL_438:
        *((_DWORD *)v124 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v270,
          L"WorkingSetBeforeDevCreate");
        if ( *((_DWORD *)v124 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
        *((_DWORD *)v124 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v216, v270);
        ++*((_DWORD *)v124 + 3);
        *((_BYTE *)v124 + 17) = 0;
        v217 = *(_DWORD *)(a1 + 236);
        mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
        std::basic_ostream<unsigned short>::operator<<(*v124, v217);
        mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v271,
          L"WorkingSetBeforeDevCreate");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v272,
          L"WorkingSetAfterDevCreate");
        if ( *((_DWORD *)v124 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
        *((_DWORD *)v124 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v218, v272);
        ++*((_DWORD *)v124 + 3);
        *((_BYTE *)v124 + 17) = 0;
        v219 = *(_DWORD *)(a1 + 240);
        mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
        std::basic_ostream<unsigned short>::operator<<(*v124, v219);
        mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v273,
          L"WorkingSetAfterDevCreate");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v274,
          L"WorkingSetAtEnd");
        if ( *((_DWORD *)v124 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
        *((_DWORD *)v124 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v220, v274);
        ++*((_DWORD *)v124 + 3);
        *((_BYTE *)v124 + 17) = 0;
        v221 = *(_DWORD *)(a1 + 244);
        mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
        std::basic_ostream<unsigned short>::operator<<(*v124, v221);
        mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v275,
          L"WorkingSetAtEnd");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v276,
          L"EndTime");
        if ( *((_DWORD *)v124 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
        *((_DWORD *)v124 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v222, v276);
        ++*((_DWORD *)v124 + 3);
        *((_BYTE *)v124 + 17) = 0;
        v223 = *(_QWORD *)(a1 + 216);
        mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
        std::basic_ostream<unsigned short>::operator<<(*v124, v223);
        mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v277,
          L"EndTime");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v278,
          L"Frequency");
        if ( *((_DWORD *)v124 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L">");
        *((_DWORD *)v124 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)v124);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v124, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v224, v278);
        ++*((_DWORD *)v124 + 3);
        *((_BYTE *)v124 + 17) = 0;
        v225 = *(_QWORD *)(a1 + 224);
        mlib::XmlStream::BeforeText((mlib::XmlStream *)v124);
        std::basic_ostream<unsigned short>::operator<<(*v124, v225);
        mlib::XmlStream::AfterText((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v281,
          L"Frequency");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v124);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v281);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v278);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v277);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v276);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v275);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v274);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v273);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v272);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v271);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v270);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v269);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v268);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v267);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v266);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v265);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v264);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v263);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v262);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v261);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v260);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v259);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v258);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v257);
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
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v229);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v228);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v227);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v279,
          L"MbVideoMemPerSecond");
        if ( *((_DWORD *)a2 + 2) == 2 )
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
        *((_DWORD *)a2 + 2) = 2;
        mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v226, v279);
        ++*((_DWORD *)a2 + 3);
        *((_BYTE *)a2 + 17) = 0;
        mlib::XmlStream::WriteText<double>((mlib::XmlStream *)a2);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v280,
          L"MbVideoMemPerSecond");
        mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v280);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v279);
        goto LABEL_451;
      }
      v213 = L"/>";
      v214 = *v124;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v214, v213);
    goto LABEL_438;
  }
LABEL_451:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v280,
    L"Results");
  mlib::XmlStream::WriteEndTag((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v280);
  return *(unsigned int *)(a1 + 300);
}

```

## disassembly

```asm
0x14007a840  mov     rax, rsp
0x14007a843  mov     [rax+10h], rbx
0x14007a847  push    rbp
0x14007a848  push    rsi
0x14007a849  push    rdi
0x14007a84a  push    r12
0x14007a84c  push    r13
0x14007a84e  push    r14
0x14007a850  push    r15
0x14007a852  lea     rbp, [rax-118h]
0x14007a859  sub     rsp, 1E0h
0x14007a860  movaps  xmmword ptr [rax-48h], xmm6
0x14007a864  mov     rsi, rdx
0x14007a867  mov     r14, rcx
0x14007a86a  cmp     dword ptr [rcx+38h], 6
0x14007a86e  jz      short loc_14007A87A
0x14007a870  mov     eax, 80040001h
0x14007a875  jmp     loc_14007DA7A
0x14007a87a  mov     ecx, [rcx+128h]
0x14007a880  xor     r15d, r15d
0x14007a883  test    ecx, ecx
0x14007a885  jz      short loc_14007A898
0x14007a887  cmp     ecx, 1
0x14007a88a  jz      short loc_14007A891
0x14007a88c  mov     edi, r15d
0x14007a88f  jmp     short loc_14007A89D
0x14007a891  mov     edi, 0Ah
0x14007a896  jmp     short loc_14007A89D
0x14007a898  mov     edi, 9
0x14007a89d  mov     r12d, 2
0x14007a8a3  lea     r13, asc_14012B480; ">"
0x14007a8aa  lea     ebx, [r12-1]
0x14007a8af  cmp     [r14+120h], ebx
0x14007a8b6  jnz     loc_14007C1C4
0x14007a8bc  lea     rdx, aDxversion; "DXVersion"
0x14007a8c3  lea     rcx, [rbp+110h+var_58]
0x14007a8ca  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007a8cf  nop
0x14007a8d0  cmp     [rsi+8], r12d
0x14007a8d4  jnz     short loc_14007A8E1
0x14007a8d6  mov     rdx, r13
0x14007a8d9  mov     rcx, [rsi]
0x14007a8dc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a8e1  mov     [rsi+8], r12d
0x14007a8e5  mov     rcx, rsi; this
0x14007a8e8  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007a8ed  lea     rdx, asc_14012B484; "<"
0x14007a8f4  mov     rcx, [rsi]
0x14007a8f7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a8fc  mov     rcx, rax
0x14007a8ff  lea     rdx, [rbp+110h+var_58]
0x14007a906  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007a90b  add     [rsi+0Ch], ebx
0x14007a90e  mov     [rsi+11h], r15b
0x14007a912  mov     rcx, rsi; this
0x14007a915  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14007a91a  mov     edx, edi
0x14007a91c  mov     rcx, [rsi]
0x14007a91f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x14007a924  mov     rcx, rsi; this
0x14007a927  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14007a92c  lea     rdx, aDxversion; "DXVersion"
0x14007a933  lea     rcx, [rbp+110h+var_60]
0x14007a93a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007a93f  nop
0x14007a940  dec     dword ptr [rsi+0Ch]
0x14007a943  mov     ecx, [rsi+8]
0x14007a946  sub     ecx, 1
0x14007a949  jz      short loc_14007A95C
0x14007a94b  cmp     ecx, 1
0x14007a94e  jnz     short loc_14007A997
0x14007a950  lea     rdx, asc_14012B488; "/>"
0x14007a957  mov     rcx, [rsi]
0x14007a95a  jmp     short loc_14007A992
0x14007a95c  cmp     [rsi+11h], r15b
0x14007a960  jnz     short loc_14007A96A
0x14007a962  mov     rcx, rsi; this
0x14007a965  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007a96a  mov     [rsi+11h], r15b
0x14007a96e  lea     rdx, asc_14012B490; "</"
0x14007a975  mov     rcx, [rsi]
0x14007a978  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a97d  mov     rcx, rax
0x14007a980  lea     rdx, [rbp+110h+var_60]
0x14007a987  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007a98c  mov     rcx, rax
0x14007a98f  mov     rdx, r13
0x14007a992  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a997  mov     [rsi+8], ebx
0x14007a99a  lea     rdx, aResults; "Results"
0x14007a9a1  lea     rcx, [rbp+110h+var_68]
0x14007a9a8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007a9ad  nop
0x14007a9ae  cmp     [rsi+8], r12d
0x14007a9b2  jnz     short loc_14007A9BF
0x14007a9b4  mov     rdx, r13
0x14007a9b7  mov     rcx, [rsi]
0x14007a9ba  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a9bf  mov     [rsi+8], r12d
0x14007a9c3  mov     rcx, rsi; this
0x14007a9c6  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007a9cb  lea     rdx, asc_14012B484; "<"
0x14007a9d2  mov     rcx, [rsi]
0x14007a9d5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007a9da  mov     rcx, rax
0x14007a9dd  lea     rdx, [rbp+110h+var_68]
0x14007a9e4  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007a9e9  add     [rsi+0Ch], ebx
0x14007a9ec  mov     [rsi+11h], r15b
0x14007a9f0  lea     rdx, aCmdline; "CmdLine"
0x14007a9f7  lea     rcx, [rbp+110h+var_70]
0x14007a9fe  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007aa03  nop
0x14007aa04  cmp     [rsi+8], r12d
0x14007aa08  jnz     short loc_14007AA15
0x14007aa0a  mov     rdx, r13
0x14007aa0d  mov     rcx, [rsi]
0x14007aa10  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007aa15  mov     [rsi+8], r12d
0x14007aa19  mov     rcx, rsi; this
0x14007aa1c  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007aa21  lea     rdx, asc_14012B484; "<"
0x14007aa28  mov     rcx, [rsi]
0x14007aa2b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007aa30  mov     rcx, rax
0x14007aa33  lea     rdx, [rbp+110h+var_70]
0x14007aa3a  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007aa3f  add     [rsi+0Ch], ebx
0x14007aa42  mov     [rsi+11h], r15b
0x14007aa46  lea     rdx, ?BeginCData@mlib@@YAXAEAVXmlStream@1@@Z; mlib::BeginCData(mlib::XmlStream &)
0x14007aa4d  mov     rcx, rsi
0x14007aa50  call    ??$?6X@XmlStream@mlib@@QEAAAEAV01@P6AXAEAV01@@Z@Z; mlib::XmlStream::operator<<<void>(void (*)(mlib::XmlStream &))
0x14007aa55  mov     rbx, rax
0x14007aa58  mov     [rbp+110h+arg_0], r15
0x14007aa5f  mov     rdx, [r14+118h]
0x14007aa66  lea     rcx, [rbp+110h+arg_0]
0x14007aa6d  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14007aa72  lea     rdx, [rbp+110h+arg_0]
0x14007aa79  mov     rcx, rbx
0x14007aa7c  call    ??$?6V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@XmlStream@mlib@@QEAAAEAV01@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::XmlStream::operator<<<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x14007aa81  lea     rdx, ?EndCData@mlib@@YAXAEAVXmlStream@1@@Z; mlib::EndCData(mlib::XmlStream &)
0x14007aa88  mov     rcx, rax
0x14007aa8b  call    ??$?6X@XmlStream@mlib@@QEAAAEAV01@P6AXAEAV01@@Z@Z; mlib::XmlStream::operator<<<void>(void (*)(mlib::XmlStream &))
0x14007aa90  mov     rbx, rax
0x14007aa93  lea     rdx, aCmdline; "CmdLine"
0x14007aa9a  lea     rcx, [rbp+110h+var_78]
0x14007aaa1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007aaa6  nop
0x14007aaa7  dec     dword ptr [rbx+0Ch]
0x14007aaaa  mov     eax, [rbx+8]
0x14007aaad  sub     eax, 1
0x14007aab0  jz      short loc_14007AAC3
0x14007aab2  cmp     eax, 1
0x14007aab5  jnz     short loc_14007AAFE
0x14007aab7  lea     rdx, asc_14012B488; "/>"
0x14007aabe  mov     rcx, [rbx]
0x14007aac1  jmp     short loc_14007AAF9
0x14007aac3  cmp     [rbx+11h], r15b
0x14007aac7  jnz     short loc_14007AAD1
0x14007aac9  mov     rcx, rbx; this
0x14007aacc  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007aad1  mov     [rbx+11h], r15b
0x14007aad5  lea     rdx, asc_14012B490; "</"
0x14007aadc  mov     rcx, [rbx]
0x14007aadf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007aae4  mov     rcx, rax
0x14007aae7  lea     rdx, [rbp+110h+var_78]
0x14007aaee  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007aaf3  mov     rcx, rax
0x14007aaf6  mov     rdx, r13
0x14007aaf9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007aafe  mov     dword ptr [rbx+8], 1
0x14007ab05  lea     rdx, aValid; "Valid"
0x14007ab0c  lea     rcx, [rbp+110h+var_80]
0x14007ab13  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007ab18  nop
0x14007ab19  cmp     [rbx+8], r12d
0x14007ab1d  jnz     short loc_14007AB2A
0x14007ab1f  mov     rdx, r13
0x14007ab22  mov     rcx, [rbx]
0x14007ab25  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ab2a  mov     [rbx+8], r12d
0x14007ab2e  mov     rcx, rbx; this
0x14007ab31  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007ab36  lea     rdx, asc_14012B484; "<"
0x14007ab3d  mov     rcx, [rbx]
0x14007ab40  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ab45  mov     rcx, rax
0x14007ab48  lea     rdx, [rbp+110h+var_80]
0x14007ab4f  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007ab54  inc     dword ptr [rbx+0Ch]
0x14007ab57  mov     [rbx+11h], r15b
0x14007ab5b  mov     rcx, rbx; this
0x14007ab5e  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14007ab63  mov     dl, 1
0x14007ab65  mov     rcx, [rbx]
0x14007ab68  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_N@Z; std::basic_ostream<ushort>::operator<<(bool)
0x14007ab6d  mov     rcx, rbx; this
0x14007ab70  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14007ab75  lea     rdx, aValid; "Valid"
0x14007ab7c  lea     rcx, [rbp+110h+var_88]
0x14007ab83  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007ab88  nop
0x14007ab89  dec     dword ptr [rbx+0Ch]
0x14007ab8c  mov     ecx, [rbx+8]
0x14007ab8f  sub     ecx, 1
0x14007ab92  jz      short loc_14007ABA5
0x14007ab94  cmp     ecx, 1
0x14007ab97  jnz     short loc_14007ABE0
0x14007ab99  lea     rdx, asc_14012B488; "/>"
0x14007aba0  mov     rcx, [rbx]
0x14007aba3  jmp     short loc_14007ABDB
0x14007aba5  cmp     [rbx+11h], r15b
0x14007aba9  jnz     short loc_14007ABB3
0x14007abab  mov     rcx, rbx; this
0x14007abae  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007abb3  mov     [rbx+11h], r15b
0x14007abb7  lea     rdx, asc_14012B490; "</"
0x14007abbe  mov     rcx, [rbx]
0x14007abc1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007abc6  mov     rcx, rax
0x14007abc9  lea     rdx, [rbp+110h+var_88]
0x14007abd0  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007abd5  mov     rcx, rax
0x14007abd8  mov     rdx, r13
0x14007abdb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007abe0  mov     dword ptr [rbx+8], 1
0x14007abe7  lea     rdx, aHresult_0; "HRESULT"
0x14007abee  lea     rcx, [rbp+110h+var_90]
0x14007abf5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007abfa  nop
0x14007abfb  cmp     [rbx+8], r12d
0x14007abff  jnz     short loc_14007AC0C
0x14007ac01  mov     rdx, r13
0x14007ac04  mov     rcx, [rbx]
0x14007ac07  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ac0c  mov     [rbx+8], r12d
0x14007ac10  mov     rcx, rbx; this
0x14007ac13  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007ac18  lea     rdx, asc_14012B484; "<"
0x14007ac1f  mov     rcx, [rbx]
0x14007ac22  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ac27  mov     rcx, rax
0x14007ac2a  lea     rdx, [rbp+110h+var_90]
0x14007ac31  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007ac36  inc     dword ptr [rbx+0Ch]
0x14007ac39  mov     [rbx+11h], r15b
0x14007ac3d  mov     rcx, rbx; this
0x14007ac40  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14007ac45  xor     edx, edx
0x14007ac47  mov     rcx, [rbx]
0x14007ac4a  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x14007ac4f  mov     rcx, rbx; this
0x14007ac52  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14007ac57  lea     rdx, aHresult_0; "HRESULT"
0x14007ac5e  lea     rcx, [rbp+110h+var_98]
0x14007ac62  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007ac67  nop
0x14007ac68  dec     dword ptr [rbx+0Ch]
0x14007ac6b  mov     ecx, [rbx+8]
0x14007ac6e  sub     ecx, 1
0x14007ac71  jz      short loc_14007AC84
0x14007ac73  cmp     ecx, 1
0x14007ac76  jnz     short loc_14007ACBC
0x14007ac78  lea     rdx, asc_14012B488; "/>"
0x14007ac7f  mov     rcx, [rbx]
0x14007ac82  jmp     short loc_14007ACB7
0x14007ac84  cmp     [rbx+11h], r15b
0x14007ac88  jnz     short loc_14007AC92
0x14007ac8a  mov     rcx, rbx; this
0x14007ac8d  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007ac92  mov     [rbx+11h], r15b
0x14007ac96  lea     rdx, asc_14012B490; "</"
0x14007ac9d  mov     rcx, [rbx]
0x14007aca0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007aca5  mov     rcx, rax
0x14007aca8  lea     rdx, [rbp+110h+var_98]
0x14007acac  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007acb1  mov     rcx, rax
0x14007acb4  mov     rdx, r13
0x14007acb7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007acbc  mov     dword ptr [rbx+8], 1
0x14007acc3  lea     rdx, aTiernum; "TierNum"
0x14007acca  lea     rcx, [rbp+110h+var_A0]
0x14007acce  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14007acd3  nop
0x14007acd4  cmp     [rbx+8], r12d
0x14007acd8  jnz     short loc_14007ACE5
0x14007acda  mov     rdx, r13
0x14007acdd  mov     rcx, [rbx]
0x14007ace0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ace5  mov     [rbx+8], r12d
0x14007ace9  mov     rcx, rbx; this
0x14007acec  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14007acf1  lea     rdx, asc_14012B484; "<"
0x14007acf8  mov     rcx, [rbx]
0x14007acfb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007ad00  mov     rcx, rax
0x14007ad03  lea     rdx, [rbp+110h+var_A0]
0x14007ad07  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
  ... truncated ...
```
