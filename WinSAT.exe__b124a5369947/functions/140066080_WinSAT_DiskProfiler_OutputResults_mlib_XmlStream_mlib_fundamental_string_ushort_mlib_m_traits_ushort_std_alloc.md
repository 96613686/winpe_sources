# WinSAT::DiskProfiler::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140066080`
- end: `0x1400698fa`
- name: `?OutputResults@DiskProfiler@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `14458`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140004ae4`
- `0x140005d78`
- `0x140005f4c`
- `0x140008178`
- `0x1400083a4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140013454`
- `0x14001362c`
- `0x140016480`
- `0x140016d04`
- `0x140019a1c`
- `0x14001bec8`
- `0x14002093c`
- `0x1400219d0`
- `0x140021a34`
- `0x1400530a8`
- `0x140062c30`
- `0x140065f30`
- `0x140066080`
- `0x140069e64`
- `0x14006d2e0`
- `0x140113220`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14006989b`
- `KERNEL32!SetLastError` at `0x14006989b`

## string_xrefs

- `0x140066100`: `AvailableTempFileSize`
- `0x1400661df`: `AvailableTempFileSize`
- `0x14006626e`: `UsedTempFileSize`
- `0x14006634d`: `UsedTempFileSize`
- `0x140067d71`: `ServiceTime`
- `0x14006811a`: `ServiceTime`
- `0x140068f3f`: `ServiceTime`
- `0x14006902a`: `ServiceTime`
- `0x140069284`: `ServiceTime`
- `0x140069334`: `ServiceTime`
- `0x14006945d`: `ServiceTime`
- `0x14006950b`: `ServiceTime`
- `0x14006862a`: `InterferenceCountWithReads`
- `0x1400686a8`: `InterferenceCountWithReads`
- `0x140069097`: `Writes`
- `0x140069382`: `Writes`
- `0x140068c33`: `Reads`
- `0x140069074`: `Reads`

## pseudocode

```c
// Hidden C++ exception states: #wind=124
__int64 __fastcall WinSAT::DiskProfiler::OutputResults(__int64 a1, mlib::XmlStream *a2)
{
  __int64 v4; // r12
  _DWORD *v5; // r15
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  const wchar_t *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  const wchar_t *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  const wchar_t *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  const wchar_t *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rdi
  const wchar_t *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v57; // ebx
  const wchar_t *v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 i; // rbx
  __int64 v62; // rax
  char v63; // di
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  unsigned int v67; // edi
  __int64 v68; // rdx
  __int64 v69; // rcx
  const wchar_t *v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  unsigned int v76; // edi
  const wchar_t *v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  _QWORD *v83; // rdi
  const wchar_t *v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  _QWORD *v90; // rdi
  const wchar_t *v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // rcx
  const wchar_t *v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rcx
  const wchar_t *v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  _QWORD *v118; // rdi
  const wchar_t *v119; // rdx
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  _QWORD *v125; // rdi
  const wchar_t *v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  _QWORD *v133; // rsi
  const wchar_t *v134; // rdx
  __int64 v135; // rcx
  __int64 v136; // rax
  __int64 v137; // rax
  unsigned int v138; // edi
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  _QWORD *v143; // rsi
  const wchar_t *v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rdx
  __int64 v151; // rcx
  __int64 v152; // rdx
  __int64 v153; // rcx
  const wchar_t *v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // rax
  const wchar_t *v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // rax
  __int64 v160; // rax
  unsigned int v161; // edi
  const wchar_t *v162; // rdx
  __int64 v163; // rcx
  __int64 v164; // rax
  __int64 v165; // rax
  unsigned int v166; // edi
  const wchar_t *v167; // rdx
  __int64 v168; // rcx
  __int64 v169; // rax
  __int64 v170; // rax
  unsigned int v171; // edi
  const wchar_t *v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // rax
  __int64 v175; // rax
  unsigned int v176; // edi
  const wchar_t *v177; // rdx
  __int64 v178; // rcx
  __int64 v179; // rax
  __int64 v180; // rax
  unsigned int v181; // edi
  const wchar_t *v182; // rdx
  __int64 v183; // rcx
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  _QWORD *v189; // rdi
  const wchar_t *v190; // rdx
  __int64 v191; // rcx
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // rdx
  __int64 v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rdx
  __int64 v202; // rcx
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rax
  mlib::XmlStream *v208; // rsi
  __int64 v209; // rax
  unsigned int v210; // edi
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  mlib::XmlStream *v214; // rdi
  __int64 v215; // rax
  __int64 v216; // rax
  mlib::XmlStream *v217; // rsi
  unsigned int v218; // edi
  __int64 v219; // rax
  __int64 v220; // rax
  mlib::XmlStream *v221; // rdi
  unsigned int v222; // edi
  __int64 v223; // rax
  __int64 v224; // rax
  mlib::XmlStream *v225; // rdi
  WinSAT::DiskProfiler *v226; // rcx
  char v227; // di
  __int64 v228; // rdx
  DWORD v229; // ebx
  const wchar_t *v230; // rdi
  unsigned int v231; // ebx
  __int64 v233; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v234; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v235; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v236; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v237; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v238; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v239; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v240; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v241; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v242; // [rsp+70h] [rbp-98h] BYREF
  __int64 v243; // [rsp+78h] [rbp-90h] BYREF
  __int64 v244; // [rsp+80h] [rbp-88h] BYREF
  __int64 v245; // [rsp+88h] [rbp-80h] BYREF
  __int64 v246; // [rsp+90h] [rbp-78h] BYREF
  __int64 v247; // [rsp+98h] [rbp-70h] BYREF
  __int64 v248; // [rsp+A0h] [rbp-68h] BYREF
  char v249[8]; // [rsp+A8h] [rbp-60h] BYREF
  char v250[8]; // [rsp+B0h] [rbp-58h] BYREF
  char v251[8]; // [rsp+B8h] [rbp-50h] BYREF
  char v252[8]; // [rsp+C0h] [rbp-48h] BYREF
  char v253[8]; // [rsp+C8h] [rbp-40h] BYREF
  char v254[8]; // [rsp+D0h] [rbp-38h] BYREF
  char v255[8]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v256; // [rsp+E0h] [rbp-28h] BYREF
  char v257[8]; // [rsp+E8h] [rbp-20h] BYREF
  char v258[8]; // [rsp+F0h] [rbp-18h] BYREF
  char v259[8]; // [rsp+F8h] [rbp-10h] BYREF
  char v260[8]; // [rsp+100h] [rbp-8h] BYREF
  char v261[8]; // [rsp+108h] [rbp+0h] BYREF
  char v262[8]; // [rsp+110h] [rbp+8h] BYREF
  char v263[8]; // [rsp+118h] [rbp+10h] BYREF
  char v264[8]; // [rsp+120h] [rbp+18h] BYREF
  char v265[8]; // [rsp+128h] [rbp+20h] BYREF
  char v266[8]; // [rsp+130h] [rbp+28h] BYREF
  char v267[8]; // [rsp+138h] [rbp+30h] BYREF
  char v268[8]; // [rsp+140h] [rbp+38h] BYREF
  char v269[8]; // [rsp+148h] [rbp+40h] BYREF
  char v270[8]; // [rsp+150h] [rbp+48h] BYREF
  char v271[8]; // [rsp+158h] [rbp+50h] BYREF
  char v272[8]; // [rsp+160h] [rbp+58h] BYREF
  char v273[8]; // [rsp+168h] [rbp+60h] BYREF
  char v274[8]; // [rsp+170h] [rbp+68h] BYREF
  char v275[8]; // [rsp+178h] [rbp+70h] BYREF
  char v276[8]; // [rsp+180h] [rbp+78h] BYREF
  char v277[8]; // [rsp+188h] [rbp+80h] BYREF
  char v278[8]; // [rsp+190h] [rbp+88h] BYREF
  char v279[8]; // [rsp+198h] [rbp+90h] BYREF
  char v280[8]; // [rsp+1A0h] [rbp+98h] BYREF
  char v281[8]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v282[8]; // [rsp+1B0h] [rbp+A8h] BYREF
  char v283[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  char v284[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  char v285[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  char v286[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  char v287[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  char v288[8]; // [rsp+1E0h] [rbp+D8h] BYREF
  char v289[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  char v290[8]; // [rsp+1F0h] [rbp+E8h] BYREF
  char v291[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  char v292[8]; // [rsp+200h] [rbp+F8h] BYREF
  char v293[8]; // [rsp+208h] [rbp+100h] BYREF
  char v294[8]; // [rsp+210h] [rbp+108h] BYREF
  char v295[8]; // [rsp+218h] [rbp+110h] BYREF
  char v296[8]; // [rsp+220h] [rbp+118h] BYREF
  char v297[8]; // [rsp+228h] [rbp+120h] BYREF
  char v298[8]; // [rsp+230h] [rbp+128h] BYREF
  char v299[8]; // [rsp+238h] [rbp+130h] BYREF
  __int64 v300; // [rsp+240h] [rbp+138h]
  char v301[8]; // [rsp+248h] [rbp+140h] BYREF
  char v302[8]; // [rsp+250h] [rbp+148h] BYREF
  char v303[8]; // [rsp+258h] [rbp+150h] BYREF
  char v304[8]; // [rsp+260h] [rbp+158h] BYREF
  char v305[8]; // [rsp+268h] [rbp+160h] BYREF
  char v306[8]; // [rsp+270h] [rbp+168h] BYREF
  char v307[8]; // [rsp+278h] [rbp+170h] BYREF
  char v308[8]; // [rsp+280h] [rbp+178h] BYREF
  char v309[8]; // [rsp+288h] [rbp+180h] BYREF
  char v310[8]; // [rsp+290h] [rbp+188h] BYREF
  char v311[8]; // [rsp+298h] [rbp+190h] BYREF
  char v312[8]; // [rsp+2A0h] [rbp+198h] BYREF
  char v313[8]; // [rsp+2A8h] [rbp+1A0h] BYREF
  char v314[8]; // [rsp+2B0h] [rbp+1A8h] BYREF
  char v315[8]; // [rsp+2B8h] [rbp+1B0h] BYREF
  char v316[8]; // [rsp+2C0h] [rbp+1B8h] BYREF
  char v317[8]; // [rsp+2C8h] [rbp+1C0h] BYREF
  char v318[8]; // [rsp+2D0h] [rbp+1C8h] BYREF
  char v319[8]; // [rsp+2D8h] [rbp+1D0h] BYREF
  char v320[8]; // [rsp+2E0h] [rbp+1D8h] BYREF
  char v321[8]; // [rsp+2E8h] [rbp+1E0h] BYREF
  char v322[8]; // [rsp+2F0h] [rbp+1E8h] BYREF
  char v323[8]; // [rsp+2F8h] [rbp+1F0h] BYREF
  char v324[8]; // [rsp+300h] [rbp+1F8h] BYREF
  char v325[8]; // [rsp+308h] [rbp+200h] BYREF
  char v326[8]; // [rsp+310h] [rbp+208h] BYREF
  char v327[8]; // [rsp+318h] [rbp+210h] BYREF
  char v328[8]; // [rsp+320h] [rbp+218h] BYREF
  char v329[8]; // [rsp+328h] [rbp+220h] BYREF
  char v330[8]; // [rsp+330h] [rbp+228h] BYREF
  char v331[8]; // [rsp+338h] [rbp+230h] BYREF
  char v332[8]; // [rsp+340h] [rbp+238h] BYREF
  char v333[8]; // [rsp+348h] [rbp+240h] BYREF
  char v334[8]; // [rsp+350h] [rbp+248h] BYREF
  char v335[8]; // [rsp+358h] [rbp+250h] BYREF
  char v336[8]; // [rsp+360h] [rbp+258h] BYREF
  char v337[8]; // [rsp+368h] [rbp+260h] BYREF
  __int64 v338; // [rsp+370h] [rbp+268h]
  char v339[8]; // [rsp+378h] [rbp+270h] BYREF
  char v340[8]; // [rsp+380h] [rbp+278h] BYREF
  char v341[8]; // [rsp+388h] [rbp+280h] BYREF
  char v342[8]; // [rsp+390h] [rbp+288h] BYREF
  char v343[8]; // [rsp+398h] [rbp+290h] BYREF
  char v344[8]; // [rsp+3A0h] [rbp+298h] BYREF
  _BYTE v345[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  WCHAR Buffer[256]; // [rsp+3B8h] [rbp+2B0h] BYREF
  DWORD dwErrCode; // [rsp+5B8h] [rbp+4B0h]
  char v348; // [rsp+5BCh] [rbp+4B4h]
  __int64 v349; // [rsp+5C0h] [rbp+4B8h]

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v256,
    64);
  v4 = a1 - 8;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    &v256,
    L"\\\\.\\PhysicalDrive%d",
    *(unsigned int *)(a1 - 8 + 212));
  v5 = (_DWORD *)((char *)a2 + 8);
  if ( *(_QWORD *)(a1 + 416) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v234,
      L"AvailableTempFileSize");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, &v234);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v235,
      L"units");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v8 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v7, &v235);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"MB");
    mlib::XmlStream::AfterText(a2);
    v9 = *(_QWORD *)(a1 + 416) >> 20;
    mlib::XmlStream::BeforeText(a2);
    std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v9);
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v236,
      L"AvailableTempFileSize");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent(a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
      v11 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, &v236);
      v10 = L">";
    }
    else
    {
      if ( *v5 != 2 )
      {
LABEL_11:
        *v5 = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v235);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v234);
        goto LABEL_12;
      }
      v10 = L"/>";
      v11 = *(_QWORD *)a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, v10);
    goto LABEL_11;
  }
LABEL_12:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v234,
    L"UsedTempFileSize");
  if ( *v5 == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
  *v5 = 2;
  mlib::XmlStream::Indent(a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v13, &v234);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v235,
    L"units");
  *v5 = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
  v15 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v14, &v235);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, L"=");
  mlib::XmlStream::BeforeText(a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"MB");
  mlib::XmlStream::AfterText(a2);
  v16 = *(_QWORD *)(a1 + 272) >> 20;
  mlib::XmlStream::BeforeText(a2);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v16);
  mlib::XmlStream::AfterText(a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v236,
    L"UsedTempFileSize");
  --*((_DWORD *)a2 + 3);
  if ( *v5 == 1 )
  {
    if ( !*((_BYTE *)a2 + 17) )
      mlib::XmlStream::Indent(a2);
    *((_BYTE *)a2 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
    v18 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v19, &v236);
    v17 = L">";
  }
  else
  {
    if ( *v5 != 2 )
      goto LABEL_21;
    v17 = L"/>";
    v18 = *(_QWORD *)a2;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, v17);
LABEL_21:
  *v5 = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v235);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v234);
  if ( !*(_DWORD *)(a1 + 192) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v254,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v20, v254);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v253,
      L"name");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v22 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v21, v253);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v252,
      L"units");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v24 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v23, v252);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v251,
      L"descrip");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v26 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v25, v251);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v250,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent(a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
      v28 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v29, v250);
      v27 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_31;
      v27 = L"/>";
      v28 = *(_QWORD *)a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, v27);
LABEL_31:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v249,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v30, v249);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v237,
      L"name");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v32 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v31, &v237);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"mbs");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v239,
      L"units");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v34 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v33, &v239);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"MB/s");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v240,
      L"descrip");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v36 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v35, &v240);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"megabytes per second");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v241,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent(a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
      v38 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v39, &v241);
      v37 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_40;
      v37 = L"/>";
      v38 = *(_QWORD *)a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, v37);
LABEL_40:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v242,
      L"Units");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v40, &v242);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v243,
      L"name");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v42 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v41, &v243);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v244,
      L"units");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v44 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, &v244);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v245,
      L"descrip");
    *v5 = 3;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
    v46 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v45, &v245);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, L"=");
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"microseconds");
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v246,
      L"Units");
    --*((_DWORD *)a2 + 3);
    if ( *v5 == 1 )
    {
      if ( !*((_BYTE *)a2 + 17) )
        mlib::XmlStream::Indent(a2);
      *((_BYTE *)a2 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
      v48 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v49, &v246);
      v47 = L">";
    }
    else
    {
      if ( *v5 != 2 )
        goto LABEL_49;
      v47 = L"/>";
      v48 = *(_QWORD *)a2;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, v47);
LABEL_49:
    *v5 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v247,
      L"PerDiskData");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, &v247);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v248,
      L"Disk");
    if ( *v5 == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
    *v5 = 2;
    mlib::XmlStream::Indent(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v51, &v248);
    ++*((_DWORD *)a2 + 3);
    *((_BYTE *)a2 + 17) = 0;
    v233 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      &v233,
      v256);
    v52 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v234,
      L"Disk");
    --*((_DWORD *)v52 + 3);
    if ( *((_DWORD *)v52 + 2) == 1 )
    {
      if ( !*((_BYTE *)v52 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v52);
      *((_BYTE *)v52 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v52, L"</");
      v54 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, &v234);
      v53 = L">";
    }
    else
    {
      if ( *((_DWORD *)v52 + 2) != 2 )
        goto LABEL_60;
      v53 = L"/>";
      v54 = *v52;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, v53);
LABEL_60:
    *((_DWORD *)v52 + 2) = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v235,
      L"RandomSeed");
    if ( *((_DWORD *)v52 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v52, L">");
    *((_DWORD *)v52 + 2) = 2;
    mlib::XmlStream::Indent((mlib::XmlStream *)v52);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v52, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v56, &v235);
    ++*((_DWORD *)v52 + 3);
    *((_BYTE *)v52 + 17) = 0;
    v57 = *(_DWORD *)(a1 + 268);
    mlib::XmlStream::BeforeText((mlib::XmlStream *)v52);
    std::basic_ostream<unsigned short>::operator<<(*v52, v57);
    mlib::XmlStream::AfterText((mlib::XmlStream *)v52);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v236,
      L"RandomSeed");
    --*((_DWORD *)v52 + 3);
    if ( *((_DWORD *)v52 + 2) == 1 )
    {
      if ( !*((_BYTE *)v52 + 17) )
        mlib::XmlStream::Indent((mlib::XmlStream *)v52);
      *((_BYTE *)v52 + 17) = 0;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v52, L"</");
      v59 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, &v236);
      v58 = L">";
    }
    else
    {
      if ( *((_DWORD *)v52 + 2) != 2 )
      {
LABEL_69:
        *((_DWORD *)v52 + 2) = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v235);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v234);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v248);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v247);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v246);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v245);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v244);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v243);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v242);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v241);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v240);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v239);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v237);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v249);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v250);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v251);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v252);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v253);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v254);
        for ( i = *(_QWORD *)(a1 + 64); ; i += 488 )
        {
          if ( i == *(_QWORD *)(a1 + 72) )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v238,
              L"PerDiskData");
            mlib::XmlStream::WriteEndTag(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
            v4 = a1 - 8;
            goto LABEL_277;
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v233,
            32);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v236,
            32);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v254,
            L"Zone");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v62, v254);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v254);
          v63 = WinSAT::DiskProfiler::OpModeToString(*(unsigned int *)(i + 208), &v236);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v253,
            L"ModeFlags");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v64, v253);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v253);
          if ( v63 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v252,
              L"friendlyName");
            *v5 = 3;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
            v66 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v65,
                    v252);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v66, L"=");
            v239 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v239,
              v236);
            mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v252);
          }
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"0x");
          mlib::XmlStream::AfterText(a2);
          LODWORD(v237) = 8;
          mlib::XmlStream::BeforeText(a2);
          mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, &v237);
          mlib::XmlStream::AfterText(a2);
          v67 = *(_DWORD *)(i + 208);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v67);
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          v68 = *(_QWORD *)a2;
          v69 = *(int *)(**(_QWORD **)a2 + 4LL);
          *(_DWORD *)(v69 + v68 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v68 + 4LL) + v68 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v68 + 4LL) + v68 + 40) = 0;
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v251,
            L"ModeFlags");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v71 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v72,
                    v251);
            v70 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_84;
            v70 = L"/>";
            v71 = *(_QWORD *)a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, v70);
LABEL_84:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v251);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v344,
            L"IoSize");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v73, v344);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v249,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v75 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v74,
                  v249);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
          mlib::XmlStream::AfterText(a2);
          v76 = *(_DWORD *)(i + 212);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v76);
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v250,
            L"IoSize");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v78 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v79,
                    v250);
            v77 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_93;
            v77 = L"/>";
            v78 = *(_QWORD *)a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v78, v77);
LABEL_93:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v250);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v249);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v344);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"0x%010I64x",
            *(_QWORD *)(i + 176));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v258,
            L"ZoneStart");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v80, v258);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v257,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v82 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v81,
                  v257);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
          mlib::XmlStream::AfterText(a2);
          v240 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v240,
            v233);
          v83 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v345,
            L"ZoneStart");
          --*((_DWORD *)v83 + 3);
          if ( *((_DWORD *)v83 + 2) == 1 )
          {
            if ( !*((_BYTE *)v83 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v83);
            *((_BYTE *)v83 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v83, L"</");
            v85 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v86,
                    v345);
            v84 = L">";
          }
          else
          {
            if ( *((_DWORD *)v83 + 2) != 2 )
              goto LABEL_102;
            v84 = L"/>";
            v85 = *v83;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, v84);
LABEL_102:
          *((_DWORD *)v83 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v345);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v257);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v258);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"0x%010I64x",
            *(_QWORD *)(i + 184));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v261,
            L"ZoneEnd");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v87, v261);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v260,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v89 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v88,
                  v260);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
          mlib::XmlStream::AfterText(a2);
          v241 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v241,
            v233);
          v90 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v259,
            L"ZoneEnd");
          --*((_DWORD *)v90 + 3);
          if ( *((_DWORD *)v90 + 2) == 1 )
          {
            if ( !*((_BYTE *)v90 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v90);
            *((_BYTE *)v90 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v90, L"</");
            v92 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v93,
                    v259);
            v91 = L">";
          }
          else
          {
            if ( *((_DWORD *)v90 + 2) != 2 )
              goto LABEL_111;
            v91 = L"/>";
            v92 = *v90;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v92, v91);
LABEL_111:
          *((_DWORD *)v90 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v259);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v260);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v261);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v267,
            L"Throughput");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v94, v267);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v266,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v96 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v95,
                  v266);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v96, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"mbs");
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          v97 = *(_QWORD *)a2;
          v98 = *(int *)(**(_QWORD **)a2 + 4LL);
          *(_DWORD *)(v98 + v97 + 24) |= 0x2080u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v97 + 4LL) + v97 + 32) = 2;
          *(_QWORD *)(*(int *)(*(_QWORD *)v97 + 4LL) + v97 + 40) = 4;
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2);
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          v99 = *(_QWORD *)a2;
          v100 = *(int *)(**(_QWORD **)a2 + 4LL);
          *(_DWORD *)(v100 + v99 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v99 + 4LL) + v99 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v99 + 4LL) + v99 + 40) = 0;
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v265,
            L"Throughput");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v102 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v103,
                     v265);
            v101 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_120;
            v101 = L"/>";
            v102 = *(_QWORD *)a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v102, v101);
LABEL_120:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v264,
            L"IssueTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v104, v264);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v263,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v106 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v105,
                   v263);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v106, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          v107 = *(_QWORD *)a2;
          v108 = *(int *)(**(_QWORD **)a2 + 4LL);
          *(_DWORD *)(v108 + v107 + 24) |= 0x2080u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 32) = 4;
          *(_QWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 40) = 4;
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2);
          mlib::XmlStream::AfterText(a2);
          mlib::XmlStream::BeforeText(a2);
          v109 = *(_QWORD *)a2;
          v110 = *(int *)(**(_QWORD **)a2 + 4LL);
          *(_DWORD *)(v110 + v109 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 40) = 0;
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v262,
            L"IssueTime");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v112 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v113,
                     v262);
            v111 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_129;
            v111 = L"/>";
            v112 = *(_QWORD *)a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, v111);
LABEL_129:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v262);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v263);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v264);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v265);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v266);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v267);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v268,
            L"ETWData");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v114, v268);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v268);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"0x%010I64x",
            *(_QWORD *)i);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v271,
            L"MinOffset");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v115, v271);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v270,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v117 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v116,
                   v270);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v117, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, "bytes");
          mlib::XmlStream::AfterText(a2);
          v242 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v242,
            v233);
          v118 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v269,
            L"MinOffset");
          --*((_DWORD *)v118 + 3);
          if ( *((_DWORD *)v118 + 2) == 1 )
          {
            if ( !*((_BYTE *)v118 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v118);
            *((_BYTE *)v118 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v118, L"</");
            v120 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v121,
                     v269);
            v119 = L">";
          }
          else
          {
            if ( *((_DWORD *)v118 + 2) != 2 )
              goto LABEL_140;
            v119 = L"/>";
            v120 = *v118;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v120, v119);
LABEL_140:
          *((_DWORD *)v118 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v269);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v270);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v271);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"0x%010I64x",
            *(_QWORD *)(i + 8));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v277,
            L"MaxOffset");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v122, v277);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v276,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v124 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v123,
                   v276);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, "bytes");
          mlib::XmlStream::AfterText(a2);
          v243 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v243,
            v233);
          v125 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v275,
            L"MaxOffset");
          --*((_DWORD *)v125 + 3);
          if ( *((_DWORD *)v125 + 2) == 1 )
          {
            if ( !*((_BYTE *)v125 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v125);
            *((_BYTE *)v125 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L"</");
            v127 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v128,
                     v275);
            v126 = L">";
          }
          else
          {
            if ( *((_DWORD *)v125 + 2) != 2 )
              goto LABEL_149;
            v126 = L"/>";
            v127 = *v125;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, v126);
LABEL_149:
          *((_DWORD *)v125 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v274,
            L"AssessmentIOs");
          if ( *((_DWORD *)v125 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L">");
          *((_DWORD *)v125 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v125);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v129, v274);
          ++*((_DWORD *)v125 + 3);
          *((_BYTE *)v125 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v273,
            L"TotalData");
          if ( *((_DWORD *)v125 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L">");
          *((_DWORD *)v125 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v125);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v130, v273);
          ++*((_DWORD *)v125 + 3);
          *((_BYTE *)v125 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v272,
            L"units");
          *((_DWORD *)v125 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, L" ");
          v132 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v131,
                   v272);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v132, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v125);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v125, "bytes");
          mlib::XmlStream::AfterText((mlib::XmlStream *)v125);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v272);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v273);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v274);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v275);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v276);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v277);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"%I64u",
            *(_QWORD *)(i + 16));
          v237 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v237,
            v233);
          v133 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v280,
            L"TotalData");
          --*((_DWORD *)v133 + 3);
          if ( *((_DWORD *)v133 + 2) == 1 )
          {
            if ( !*((_BYTE *)v133 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v133);
            *((_BYTE *)v133 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v133, L"</");
            v135 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v136,
                     v280);
            v134 = L">";
          }
          else
          {
            if ( *((_DWORD *)v133 + 2) != 2 )
              goto LABEL_160;
            v134 = L"/>";
            v135 = *v133;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, v134);
LABEL_160:
          *((_DWORD *)v133 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v279,
            L"Count");
          if ( *((_DWORD *)v133 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v133, L">");
          *((_DWORD *)v133 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v133);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v133, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v137, v279);
          ++*((_DWORD *)v133 + 3);
          *((_BYTE *)v133 + 17) = 0;
          v138 = *(_DWORD *)(i + 112);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v133);
          std::basic_ostream<unsigned short>::operator<<(*v133, v138);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v133);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v278,
            L"Count");
          --*((_DWORD *)v133 + 3);
          if ( *((_DWORD *)v133 + 2) == 1 )
          {
            if ( !*((_BYTE *)v133 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v133);
            *((_BYTE *)v133 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v133, L"</");
            v147 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v146,
                     v278);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v147, L">");
          }
          else if ( *((_DWORD *)v133 + 2) == 2 )
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v133, L"/>");
          }
          *((_DWORD *)v133 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v278);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v279);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v280);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v282,
            L"ServiceTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v139, v282);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v281,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v141 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v140,
                   v281);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v141, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v281);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v282);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"%I64u",
            *(_QWORD *)(i + 40));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v293,
            L"Total");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v142, v293);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v244 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v244,
            v233);
          v143 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v292,
            L"Total");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v145 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v148,
                     v292);
            v144 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_179;
            v144 = L"/>";
            v145 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, v144);
LABEL_179:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v291,
            L"Average");
          if ( *((_DWORD *)v143 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L">");
          *((_DWORD *)v143 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v143);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v149, v291);
          ++*((_DWORD *)v143 + 3);
          *((_BYTE *)v143 + 17) = 0;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          v150 = *v143;
          v151 = *(int *)(*(_QWORD *)*v143 + 4LL);
          *(_DWORD *)(v151 + v150 + 24) |= 0x2080u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 32) = 2;
          *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 4;
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          std::basic_ostream<unsigned short>::operator<<(*v143);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          v152 = *v143;
          v153 = *(int *)(*(_QWORD *)*v143 + 4LL);
          *(_DWORD *)(v153 + v152 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v290,
            L"Average");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v155 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v156,
                     v290);
            v154 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_188;
            v154 = L"/>";
            v155 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v155, v154);
LABEL_188:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v289,
            L"ServiceTime");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v158 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v159,
                     v289);
            v157 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_195;
            v157 = L"/>";
            v158 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v158, v157);
LABEL_195:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v288,
            L"AllowedInterference");
          if ( *((_DWORD *)v143 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L">");
          *((_DWORD *)v143 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v143);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v160, v288);
          ++*((_DWORD *)v143 + 3);
          *((_BYTE *)v143 + 17) = 0;
          v161 = *(_DWORD *)(a1 + 424) * *(_DWORD *)(i + 112) / 0x64u;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          std::basic_ostream<unsigned short>::operator<<(*v143, v161);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v287,
            L"AllowedInterference");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v163 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v164,
                     v287);
            v162 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_204;
            v162 = L"/>";
            v163 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, v162);
LABEL_204:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v286,
            L"InterferenceCount");
          if ( *((_DWORD *)v143 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L">");
          *((_DWORD *)v143 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v143);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v165, v286);
          ++*((_DWORD *)v143 + 3);
          *((_BYTE *)v143 + 17) = 0;
          v166 = *(_DWORD *)(i + 140);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          std::basic_ostream<unsigned short>::operator<<(*v143, v166);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v285,
            L"InterferenceCount");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v168 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v169,
                     v285);
            v167 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_213;
            v167 = L"/>";
            v168 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, v167);
LABEL_213:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v284,
            L"PermittedInterferencePercentage");
          if ( *((_DWORD *)v143 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L">");
          *((_DWORD *)v143 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v143);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v170, v284);
          ++*((_DWORD *)v143 + 3);
          *((_BYTE *)v143 + 17) = 0;
          v171 = *(_DWORD *)(a1 + 424);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v143);
          std::basic_ostream<unsigned short>::operator<<(*v143, v171);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v143);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v283,
            L"PermittedInterferencePercentage");
          --*((_DWORD *)v143 + 3);
          if ( *((_DWORD *)v143 + 2) == 1 )
          {
            if ( !*((_BYTE *)v143 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v143);
            *((_BYTE *)v143 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v143, L"</");
            v173 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v174,
                     v283);
            v172 = L">";
          }
          else
          {
            if ( *((_DWORD *)v143 + 2) != 2 )
              goto LABEL_222;
            v172 = L"/>";
            v173 = *v143;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, v172);
LABEL_222:
          *((_DWORD *)v143 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v283);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v284);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v285);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v286);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v287);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v288);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v289);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v290);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v291);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v292);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v293);
          if ( !*(_DWORD *)(i + 112) )
            goto LABEL_233;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v295,
            L"ActualInterferencePercentage");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v175, v295);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v176 = (unsigned int)(100 * *(_DWORD *)(i + 140)) / *(_DWORD *)(i + 112);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v176);
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v294,
            L"ActualInterferencePercentage");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v178 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v179,
                     v294);
            v177 = L">";
            goto LABEL_231;
          }
          if ( *v5 == 2 )
          {
            v177 = L"/>";
            v178 = *(_QWORD *)a2;
LABEL_231:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v178, v177);
          }
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v294);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v295);
LABEL_233:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v297,
            L"InterferenceCountWithReads");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v180, v297);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v181 = *(_DWORD *)(i + 144);
          mlib::XmlStream::BeforeText(a2);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v181);
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v296,
            L"InterferenceCountWithReads");
          --*((_DWORD *)a2 + 3);
          if ( *v5 == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent(a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"</");
            v183 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v184,
                     v296);
            v182 = L">";
          }
          else
          {
            if ( *v5 != 2 )
              goto LABEL_242;
            v182 = L"/>";
            v183 = *(_QWORD *)a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v183, v182);
LABEL_242:
          *v5 = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v296);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v297);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v299,
            L"IOTime");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v185, v299);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v298,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v187 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v186,
                   v298);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v187, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v298);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v299);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"%I64u",
            *(_QWORD *)(i + 48));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v311,
            L"Total");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v188, v311);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v245 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v245,
            v233);
          v189 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v310,
            L"Total");
          --*((_DWORD *)v189 + 3);
          if ( *((_DWORD *)v189 + 2) == 1 )
          {
            if ( !*((_BYTE *)v189 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)v189);
            *((_BYTE *)v189 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"</");
            v191 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v192,
                     v310);
            v190 = L">";
          }
          else
          {
            if ( *((_DWORD *)v189 + 2) != 2 )
              goto LABEL_253;
            v190 = L"/>";
            v191 = *v189;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v191, v190);
LABEL_253:
          *((_DWORD *)v189 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v309,
            L"Average");
          if ( *((_DWORD *)v189 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L">");
          *((_DWORD *)v189 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v189);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v193, v309);
          ++*((_DWORD *)v189 + 3);
          *((_BYTE *)v189 + 17) = 0;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v189);
          v194 = *v189;
          v195 = *(int *)(*(_QWORD *)*v189 + 4LL);
          *(_DWORD *)(v195 + v194 + 24) |= 0x2080u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 32) = 2;
          *(_QWORD *)(*(int *)(*(_QWORD *)v194 + 4LL) + v194 + 40) = 4;
          mlib::XmlStream::AfterText((mlib::XmlStream *)v189);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v189);
          std::basic_ostream<unsigned short>::operator<<(*v189);
          mlib::XmlStream::AfterText((mlib::XmlStream *)v189);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v189);
          v196 = *v189;
          v197 = *(int *)(*(_QWORD *)*v189 + 4LL);
          *(_DWORD *)(v197 + v196 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v196 + 4LL) + v196 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v196 + 4LL) + v196 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v308,
            L"Average");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v307,
            L"IOTime");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v306,
            L"AvgIOTimeToSrvTimeDelta");
          if ( *((_DWORD *)v189 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L">");
          *((_DWORD *)v189 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v189);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v198, v306);
          ++*((_DWORD *)v189 + 3);
          *((_BYTE *)v189 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v305,
            L"units");
          *((_DWORD *)v189 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L" ");
          v200 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v199,
                   v305);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v200, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v189);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"us");
          mlib::XmlStream::AfterText((mlib::XmlStream *)v189);
          v300 = 0x200000004LL;
          mlib::XmlStream::WriteText<mlib::_ffixedobj>((mlib::XmlStream *)v189);
          mlib::XmlStream::WriteText<double>((mlib::XmlStream *)v189);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)v189);
          v201 = *v189;
          v202 = *(int *)(*(_QWORD *)*v189 + 4LL);
          *(_DWORD *)(v202 + v201 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v201 + 4LL) + v201 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v201 + 4LL) + v201 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v304,
            L"AvgIOTimeToSrvTimeDelta");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v303,
            L"AssessmentIOs");
          mlib::XmlStream::WriteEndTag((mlib::XmlStream *)v189);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v302,
            L"NonAssessmentIOs");
          if ( *((_DWORD *)v189 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L">");
          *((_DWORD *)v189 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v189);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v203, v302);
          ++*((_DWORD *)v189 + 3);
          *((_BYTE *)v189 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v301,
            L"Reads");
          if ( *((_DWORD *)v189 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L">");
          *((_DWORD *)v189 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)v189);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v189, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v204, v301);
          ++*((_DWORD *)v189 + 3);
          *((_BYTE *)v189 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v301);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v302);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v303);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v304);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v305);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v306);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v307);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v308);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v309);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v310);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v311);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"%I64u",
            *(_QWORD *)(i + 24));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v316,
            L"TotalData");
          if ( *v5 == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
          *v5 = 2;
          mlib::XmlStream::Indent(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v205, v316);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v315,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v207 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v206,
                   v315);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v207, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
          mlib::XmlStream::AfterText(a2);
          v246 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v246,
            v233);
          v208 = (mlib::XmlStream *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v314,
            L"TotalData");
          mlib::XmlStream::WriteEndTag(v208);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v313,
            L"Count");
          if ( *((_DWORD *)v208 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v208, L">");
          *((_DWORD *)v208 + 2) = 2;
          mlib::XmlStream::Indent(v208);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v208, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v209, v313);
          ++*((_DWORD *)v208 + 3);
          *((_BYTE *)v208 + 17) = 0;
          v210 = *(_DWORD *)(i + 116);
          mlib::XmlStream::BeforeText(v208);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v208, v210);
          mlib::XmlStream::AfterText(v208);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v312,
            L"Count");
          mlib::XmlStream::WriteEndTag(v208);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v312);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v313);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v314);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v315);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v316);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v233,
              L"%I64u",
              *(_QWORD *)(i + 56));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v319,
              L"ServiceTime");
            if ( *v5 == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L">");
            *v5 = 2;
            mlib::XmlStream::Indent(a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v211, v319);
            ++*((_DWORD *)a2 + 3);
            *((_BYTE *)a2 + 17) = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v318,
              L"units");
            *v5 = 3;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
            v213 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v212,
                     v318);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v213, L"=");
            mlib::XmlStream::BeforeText(a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
            mlib::XmlStream::AfterText(a2);
            v247 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v247,
              v233);
            v214 = (mlib::XmlStream *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v317,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v214);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v317);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v318);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v319);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v321,
            L"Reads");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v320,
            L"Writes");
          mlib::XmlStream::WriteBeginTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v320);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v321);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v233,
            L"%I64u",
            *(_QWORD *)(i + 32));
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v326,
            L"TotalData");
          mlib::XmlStream::WriteBeginTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v325,
            L"units");
          *v5 = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
          v216 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                   v215,
                   v325);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v216, L"=");
          mlib::XmlStream::BeforeText(a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"bytes");
          mlib::XmlStream::AfterText(a2);
          v248 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v248,
            v233);
          v217 = (mlib::XmlStream *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v324,
            L"TotalData");
          mlib::XmlStream::WriteEndTag(v217);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v323,
            L"Count");
          mlib::XmlStream::WriteBeginTag(v217);
          v218 = *(_DWORD *)(i + 120);
          mlib::XmlStream::BeforeText(v217);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v217, v218);
          mlib::XmlStream::AfterText(v217);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v322,
            L"Count");
          mlib::XmlStream::WriteEndTag(v217);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v322);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v323);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v324);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v325);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v326);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v233,
              L"%I64u",
              *(_QWORD *)(i + 64));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v329,
              L"ServiceTime");
            mlib::XmlStream::WriteBeginTag(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v328,
              L"units");
            *v5 = 3;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
            v220 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v219,
                     v328);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v220, L"=");
            mlib::XmlStream::BeforeText(a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
            mlib::XmlStream::AfterText(a2);
            v234 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v234,
              v233);
            v221 = (mlib::XmlStream *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v327,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v221);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v330,
            L"Writes");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
          if ( (*(_DWORD *)(i + 208) & 0x10000000) != 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
              &v233,
              L"%I64u",
              *(_QWORD *)(i + 72));
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v337,
              L"Flushes");
            mlib::XmlStream::WriteBeginTag(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v336,
              L"Count");
            mlib::XmlStream::WriteBeginTag(a2);
            v222 = *(_DWORD *)(i + 124);
            mlib::XmlStream::BeforeText(a2);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v222);
            mlib::XmlStream::AfterText(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v335,
              L"Count");
            mlib::XmlStream::WriteEndTag(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v334,
              L"ServiceTime");
            mlib::XmlStream::WriteBeginTag(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v333,
              L"units");
            *v5 = 3;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L" ");
            v224 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                     v223,
                     v333);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v224, L"=");
            mlib::XmlStream::BeforeText(a2);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, L"us");
            mlib::XmlStream::AfterText(a2);
            v235 = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
              &v235,
              v233);
            v225 = (mlib::XmlStream *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(a2);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v332,
              L"ServiceTime");
            mlib::XmlStream::WriteEndTag(v225);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v331,
              L"Flushes");
            mlib::XmlStream::WriteEndTag(v225);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
          }
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v341,
            L"NonAssessmentIOs");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v340,
            L"Throughput");
          mlib::XmlStream::WriteBeginTag(a2);
          v338 = 0x200000004LL;
          mlib::XmlStream::WriteText<mlib::_ffixedobj>(a2);
          mlib::XmlStream::WriteText<double>(a2);
          mlib::XmlStream::WriteText<mlib::_normobj>(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v339,
            L"Throughput");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v339);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v340);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v341);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v342,
            L"ETWData");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v342);
          if ( (*(_DWORD *)(i + 208) & 0xC000000) != 0 )
            WinSAT::DiskProfiler::OutputResultsForFlushProfile(
              v226,
              a2,
              (const struct WinSAT::DiskProfiler::DiskProfResult *)i);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v255,
            L"Interference");
          mlib::XmlStream::WriteBeginTag(a2);
          v227 = *(_BYTE *)(i + 149);
          mlib::XmlStream::BeforeText(a2);
          LOBYTE(v228) = v227;
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)a2, v228);
          mlib::XmlStream::AfterText(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v343,
            L"Interference");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v343);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v255);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v238,
            L"Zone");
          mlib::XmlStream::WriteEndTag(a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v236);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v233);
        }
      }
      v58 = L"/>";
      v59 = *v52;
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, v58);
    goto LABEL_69;
  }
LABEL_277:
  v229 = *(_DWORD *)(a1 + 192);
  if ( v229 == 33619978 || v229 == 33619970 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v255,
      L"SuccessReason");
    mlib::XmlStream::WriteBeginTag(a2);
    if ( v229 == 33619978 )
      v230 = L"NotEnoughSpace";
    else
      v230 = L"TooFragmented";
    mlib::XmlStream::BeforeText(a2);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)a2, v230);
    mlib::XmlStream::AfterText(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v238,
      L"SuccessReason");
    mlib::XmlStream::WriteEndTag(a2);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v238);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v255);
    v229 = 0;
  }
  dwErrCode = v229;
  v348 = 1;
  v349 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  if ( *(_DWORD *)(a1 + 192) )
    WinSAT::DiskProfiler::PropogateWin32Error(v4, Buffer);
  SetLastError(dwErrCode);
  if ( v229 == 33619979 )
    v231 = -2147221502;
  else
    v231 = dwErrCode != 0 ? 0x80040001 : 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v256);
  return v231;
}

```

## disassembly

```asm
0x140066080  mov     rax, rsp
0x140066083  mov     [rax+18h], rbx
0x140066087  push    rbp
0x140066088  push    rsi
0x140066089  push    rdi
0x14006608a  push    r12
0x14006608c  push    r13
0x14006608e  push    r14
0x140066090  push    r15
0x140066092  lea     rbp, [rax-518h]
0x140066099  sub     rsp, 5E0h
0x1400660a0  movaps  xmmword ptr [rax-48h], xmm6
0x1400660a4  mov     rax, cs:__security_cookie
0x1400660ab  xor     rax, rsp
0x1400660ae  mov     [rbp+510h+var_50], rax
0x1400660b5  mov     r14, rdx
0x1400660b8  mov     r13, rcx
0x1400660bb  mov     edx, 40h ; '@'
0x1400660c0  lea     rcx, [rbp+510h+var_538]
0x1400660c4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400660c9  nop
0x1400660ca  lea     r12, [r13-8]
0x1400660ce  mov     r8d, [r12+0D4h]
0x1400660d6  lea     rdx, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x1400660dd  lea     rcx, [rbp+510h+var_538]
0x1400660e1  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1400660e6  lea     r15, [r14+8]
0x1400660ea  lea     rdi, asc_14012B480; ">"
0x1400660f1  xor     esi, esi
0x1400660f3  cmp     [r13+1A0h], rsi
0x1400660fa  jz      loc_14006626E
0x140066100  lea     rdx, aAvailabletempf; "AvailableTempFileSize"
0x140066107  lea     rcx, [rsp+610h+var_5E8]
0x14006610c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066111  nop
0x140066112  cmp     dword ptr [r15], 2
0x140066116  jnz     short loc_140066123
0x140066118  mov     rdx, rdi
0x14006611b  mov     rcx, [r14]
0x14006611e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066123  mov     dword ptr [r15], 2
0x14006612a  mov     rcx, r14; this
0x14006612d  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140066132  lea     rdx, asc_14012B484; "<"
0x140066139  mov     rcx, [r14]
0x14006613c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066141  mov     rcx, rax
0x140066144  lea     rdx, [rsp+610h+var_5E8]
0x140066149  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006614e  inc     dword ptr [r14+0Ch]
0x140066152  mov     [r14+11h], sil
0x140066156  lea     rdx, aUnits_0; "units"
0x14006615d  lea     rcx, [rsp+610h+var_5E0]
0x140066162  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066167  nop
0x140066168  mov     dword ptr [r15], 3
0x14006616f  lea     rdx, asc_14012B49C; " "
0x140066176  mov     rcx, [r14]
0x140066179  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006617e  mov     rcx, rax
0x140066181  lea     rdx, [rsp+610h+var_5E0]
0x140066186  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006618b  mov     rcx, rax
0x14006618e  lea     rdx, asc_14012B498; "="
0x140066195  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006619a  mov     rcx, r14; this
0x14006619d  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400661a2  lea     rdx, aMb_0; "MB"
0x1400661a9  mov     rcx, [r14]
0x1400661ac  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400661b1  mov     rcx, r14; this
0x1400661b4  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400661b9  mov     rbx, [r13+1A0h]
0x1400661c0  shr     rbx, 14h
0x1400661c4  mov     rcx, r14; this
0x1400661c7  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400661cc  mov     rdx, rbx
0x1400661cf  mov     rcx, [r14]
0x1400661d2  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x1400661d7  mov     rcx, r14; this
0x1400661da  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400661df  lea     rdx, aAvailabletempf; "AvailableTempFileSize"
0x1400661e6  lea     rcx, [rsp+610h+var_5D8]
0x1400661eb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400661f0  nop
0x1400661f1  dec     dword ptr [r14+0Ch]
0x1400661f5  mov     ecx, [r15]
0x1400661f8  sub     ecx, 1
0x1400661fb  jz      short loc_14006620E
0x1400661fd  cmp     ecx, 1
0x140066200  jnz     short loc_140066247
0x140066202  lea     rdx, asc_14012B488; "/>"
0x140066209  mov     rcx, [r14]
0x14006620c  jmp     short loc_140066242
0x14006620e  cmp     [r14+11h], sil
0x140066212  jnz     short loc_14006621C
0x140066214  mov     rcx, r14; this
0x140066217  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006621c  mov     [r14+11h], sil
0x140066220  lea     rdx, asc_14012B490; "</"
0x140066227  mov     rcx, [r14]
0x14006622a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006622f  mov     rcx, rax
0x140066232  lea     rdx, [rsp+610h+var_5D8]
0x140066237  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14006623c  mov     rcx, rax
0x14006623f  mov     rdx, rdi
0x140066242  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066247  mov     dword ptr [r15], 1
0x14006624e  lea     rcx, [rsp+610h+var_5D8]
0x140066253  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140066258  nop
0x140066259  lea     rcx, [rsp+610h+var_5E0]
0x14006625e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140066263  nop
0x140066264  lea     rcx, [rsp+610h+var_5E8]
0x140066269  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14006626e  lea     rdx, aUsedtempfilesi; "UsedTempFileSize"
0x140066275  lea     rcx, [rsp+610h+var_5E8]
0x14006627a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006627f  nop
0x140066280  cmp     dword ptr [r15], 2
0x140066284  jnz     short loc_140066291
0x140066286  mov     rdx, rdi
0x140066289  mov     rcx, [r14]
0x14006628c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066291  mov     dword ptr [r15], 2
0x140066298  mov     rcx, r14; this
0x14006629b  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x1400662a0  lea     rdx, asc_14012B484; "<"
0x1400662a7  mov     rcx, [r14]
0x1400662aa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400662af  mov     rcx, rax
0x1400662b2  lea     rdx, [rsp+610h+var_5E8]
0x1400662b7  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400662bc  inc     dword ptr [r14+0Ch]
0x1400662c0  mov     [r14+11h], sil
0x1400662c4  lea     rdx, aUnits_0; "units"
0x1400662cb  lea     rcx, [rsp+610h+var_5E0]
0x1400662d0  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400662d5  nop
0x1400662d6  mov     dword ptr [r15], 3
0x1400662dd  lea     rdx, asc_14012B49C; " "
0x1400662e4  mov     rcx, [r14]
0x1400662e7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400662ec  mov     rcx, rax
0x1400662ef  lea     rdx, [rsp+610h+var_5E0]
0x1400662f4  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400662f9  mov     rcx, rax
0x1400662fc  lea     rdx, asc_14012B498; "="
0x140066303  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066308  mov     rcx, r14; this
0x14006630b  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066310  lea     rdx, aMb_0; "MB"
0x140066317  mov     rcx, [r14]
0x14006631a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006631f  mov     rcx, r14; this
0x140066322  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140066327  mov     rbx, [r13+110h]
0x14006632e  shr     rbx, 14h
0x140066332  mov     rcx, r14; this
0x140066335  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x14006633a  mov     rdx, rbx
0x14006633d  mov     rcx, [r14]
0x140066340  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x140066345  mov     rcx, r14; this
0x140066348  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14006634d  lea     rdx, aUsedtempfilesi; "UsedTempFileSize"
0x140066354  lea     rcx, [rsp+610h+var_5D8]
0x140066359  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006635e  nop
0x14006635f  dec     dword ptr [r14+0Ch]
0x140066363  mov     ecx, [r15]
0x140066366  sub     ecx, 1
0x140066369  jz      short loc_14006637C
0x14006636b  cmp     ecx, 1
0x14006636e  jnz     short loc_1400663B5
0x140066370  lea     rdx, asc_14012B488; "/>"
0x140066377  mov     rcx, [r14]
0x14006637a  jmp     short loc_1400663B0
0x14006637c  cmp     [r14+11h], sil
0x140066380  jnz     short loc_14006638A
0x140066382  mov     rcx, r14; this
0x140066385  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006638a  mov     [r14+11h], sil
0x14006638e  lea     rdx, asc_14012B490; "</"
0x140066395  mov     rcx, [r14]
0x140066398  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006639d  mov     rcx, rax
0x1400663a0  lea     rdx, [rsp+610h+var_5D8]
0x1400663a5  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400663aa  mov     rcx, rax
0x1400663ad  mov     rdx, rdi
0x1400663b0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400663b5  mov     dword ptr [r15], 1
0x1400663bc  lea     rcx, [rsp+610h+var_5D8]
0x1400663c1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663c6  nop
0x1400663c7  lea     rcx, [rsp+610h+var_5E0]
0x1400663cc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663d1  nop
0x1400663d2  lea     rcx, [rsp+610h+var_5E8]
0x1400663d7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400663dc  cmp     [r13+0C0h], esi
0x1400663e3  jnz     loc_1400697B0
0x1400663e9  lea     rdx, aUnits; "Units"
0x1400663f0  lea     rcx, [rbp+510h+var_548]
0x1400663f4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400663f9  nop
0x1400663fa  mov     ebx, 2
0x1400663ff  cmp     [r15], ebx
0x140066402  jnz     short loc_14006640F
0x140066404  mov     rdx, rdi
0x140066407  mov     rcx, [r14]
0x14006640a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006640f  mov     [r15], ebx
0x140066412  mov     rcx, r14; this
0x140066415  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14006641a  lea     rdx, asc_14012B484; "<"
0x140066421  mov     rcx, [r14]
0x140066424  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066429  mov     rcx, rax
0x14006642c  lea     rdx, [rbp+510h+var_548]
0x140066430  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066435  inc     dword ptr [r14+0Ch]
0x140066439  mov     [r14+11h], sil
0x14006643d  lea     rdx, aName_0; "name"
0x140066444  lea     rcx, [rbp+510h+var_550]
0x140066448  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006644d  nop
0x14006644e  mov     dword ptr [r15], 3
0x140066455  lea     rdx, asc_14012B49C; " "
0x14006645c  mov     rcx, [r14]
0x14006645f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066464  mov     rcx, rax
0x140066467  lea     rdx, [rbp+510h+var_550]
0x14006646b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066470  mov     rcx, rax
0x140066473  lea     rdx, asc_14012B498; "="
0x14006647a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006647f  mov     rcx, r14; this
0x140066482  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066487  lea     rdx, aBytes_4; "bytes"
0x14006648e  mov     rcx, [r14]
0x140066491  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066496  mov     rcx, r14; this
0x140066499  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x14006649e  lea     rdx, aUnits_0; "units"
0x1400664a5  lea     rcx, [rbp+510h+var_558]
0x1400664a9  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400664ae  nop
0x1400664af  mov     dword ptr [r15], 3
0x1400664b6  lea     rdx, asc_14012B49C; " "
0x1400664bd  mov     rcx, [r14]
0x1400664c0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664c5  mov     rcx, rax
0x1400664c8  lea     rdx, [rbp+510h+var_558]
0x1400664cc  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400664d1  mov     rcx, rax
0x1400664d4  lea     rdx, asc_14012B498; "="
0x1400664db  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664e0  mov     rcx, r14; this
0x1400664e3  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400664e8  lea     rdx, aBytes_4; "bytes"
0x1400664ef  mov     rcx, [r14]
0x1400664f2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400664f7  mov     rcx, r14; this
0x1400664fa  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x1400664ff  lea     rdx, aDescrip; "descrip"
0x140066506  lea     rcx, [rbp+510h+var_560]
0x14006650a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14006650f  nop
0x140066510  mov     dword ptr [r15], 3
0x140066517  lea     rdx, asc_14012B49C; " "
0x14006651e  mov     rcx, [r14]
0x140066521  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066526  mov     rcx, rax
0x140066529  lea     rdx, [rbp+510h+var_560]
0x14006652d  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140066532  mov     rcx, rax
0x140066535  lea     rdx, asc_14012B498; "="
0x14006653c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066541  mov     rcx, r14; this
0x140066544  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140066549  lea     rdx, aBytes_4; "bytes"
0x140066550  mov     rcx, [r14]
0x140066553  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140066558  mov     rcx, r14; this
0x14006655b  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140066560  lea     rdx, aUnits; "Units"
0x140066567  lea     rcx, [rbp+510h+var_568]
0x14006656b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140066570  nop
0x140066571  dec     dword ptr [r14+0Ch]
0x140066575  mov     ecx, [r15]
0x140066578  sub     ecx, 1
0x14006657b  jz      short loc_14006658E
0x14006657d  cmp     ecx, 1
0x140066580  jnz     short loc_1400665C6
0x140066582  lea     rdx, asc_14012B488; "/>"
  ... truncated ...
```
