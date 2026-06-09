# EnumerateCPUInfo

- ea: `0x1400228c4`
- end: `0x140026108`
- name: `EnumerateCPUInfo`
- size: `14404`
- prototype: `__int64 __fastcall(mlib::XmlStream *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b890`

## callees

- `0x1400039f0`
- `0x140004348`
- `0x14000449c`
- `0x140005d78`
- `0x140008064`
- `0x140008178`
- `0x1400085b4`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140013454`
- `0x14001362c`
- `0x140016d04`
- `0x140017af0`
- `0x14002093c`
- `0x1400219d0`
- `0x140021a34`
- `0x140021e6c`
- `0x1400228c4`
- `0x140113220`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140024b02`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024c11`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024d19`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024e21`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024b02`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024c11`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024d19`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140024e21`
- `msvcrt!_wcsicmp` at `0x140023420`
- `msvcrt!_wcsicmp` at `0x140023446`
- `msvcrt!_wcsicmp` at `0x140023420`
- `msvcrt!_wcsicmp` at `0x140023446`

## string_xrefs

- `0x14002307a`: `CoresAreThreaded`
- `0x1400230fc`: `CoresAreThreaded`
- `0x140023a6f`: `CompactSignature`
- `0x140023aea`: `CompactSignature`
- `0x140023c8e`: `L1Cache`
- `0x140024075`: `L1Cache`
- `0x140024166`: `L2Cache`
- `0x14002454d`: `L2Cache`
- `0x14002463e`: `L3Cache`
- `0x140024a25`: `L3Cache`
- `0x1400252bd`: `RelationCache`
- `0x1400255fc`: `RelationCache`
- `0x140025e3a`: `  Cache| Level:`
- `0x140025dd1`: `  RelationCache            `

## pseudocode

```c
// Hidden C++ exception states: #wind=86
double __fastcall EnumerateCPUInfo(mlib::XmlStream *this)
{
  mlib::XmlStream *v1; // rdi
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  const wchar_t *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // ebx
  const wchar_t *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned int v25; // ebx
  const wchar_t *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned int v31; // ebx
  const wchar_t *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned int v37; // ebx
  const wchar_t *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned int v43; // ebx
  const wchar_t *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  BOOL v49; // ebx
  const wchar_t *v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  const wchar_t *v55; // rbx
  const wchar_t *v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  const wchar_t *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  unsigned int v66; // esi
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rbx
  const wchar_t *v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  unsigned int v78; // ebx
  const wchar_t *v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  unsigned int v84; // ebx
  const wchar_t *v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  unsigned int v90; // ebx
  const wchar_t *v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  unsigned int v96; // ebx
  const wchar_t *v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  unsigned int v102; // ebx
  const wchar_t *v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  unsigned int v108; // ebx
  const wchar_t *v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // rax
  __int64 v112; // rax
  const wchar_t *v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  unsigned int v119; // ebx
  const wchar_t *v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  unsigned int v125; // ebx
  const wchar_t *v126; // rdx
  __int64 v127; // rcx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  unsigned int v131; // ebx
  const wchar_t *v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  unsigned int v137; // ebx
  const wchar_t *v138; // rdx
  __int64 v139; // rcx
  __int64 v140; // rax
  __int64 v141; // rax
  const wchar_t *v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  unsigned int v148; // ebx
  const wchar_t *v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  unsigned int v154; // ebx
  const wchar_t *v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  unsigned int v160; // ebx
  const wchar_t *v161; // rdx
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  unsigned int v166; // ebx
  const wchar_t *v167; // rdx
  __int64 v168; // rcx
  __int64 v169; // rax
  __int64 v170; // rax
  const wchar_t *v171; // rdx
  __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  unsigned int v177; // ebx
  const wchar_t *v178; // rdx
  __int64 v179; // rcx
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  unsigned int v183; // ebx
  const wchar_t *v184; // rdx
  __int64 v185; // rcx
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  unsigned int v189; // ebx
  const wchar_t *v190; // rdx
  __int64 v191; // rcx
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rax
  unsigned int v195; // ebx
  const wchar_t *v196; // rdx
  __int64 v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rax
  const wchar_t *v200; // rdx
  __int64 v201; // rcx
  __int64 v202; // rax
  __int64 v203; // rax
  BOOL v204; // esi
  __int64 v205; // rax
  const wchar_t *v206; // rbx
  const wchar_t *v207; // rdx
  const wchar_t *v208; // rdx
  __int64 v209; // rcx
  __int64 v210; // rax
  __int64 v211; // rax
  BOOL v212; // esi
  __int64 v213; // rax
  const wchar_t *v214; // rdx
  const wchar_t *v215; // rdx
  __int64 v216; // rcx
  __int64 v217; // rax
  __int64 v218; // rax
  BOOL v219; // esi
  __int64 v220; // rax
  const wchar_t *v221; // rdx
  const wchar_t *v222; // rdx
  __int64 v223; // rcx
  __int64 v224; // rax
  __int64 v225; // rax
  BOOL v226; // esi
  __int64 v227; // rax
  const wchar_t *v228; // rdx
  __int64 v229; // rcx
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rsi
  __int64 v233; // rax
  unsigned int i; // r15d
  __int64 v235; // r14
  int v236; // ecx
  int v237; // ecx
  int v238; // ecx
  __int64 v239; // rbx
  _BYTE *v240; // rcx
  __int64 v241; // rbx
  __int64 v242; // rdx
  __int64 v243; // rcx
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // rbx
  __int64 v247; // rdx
  __int64 v248; // rcx
  __int64 v249; // rax
  unsigned int v250; // ebx
  unsigned int v251; // ebx
  unsigned int v252; // ebx
  unsigned int v253; // ebx
  __int64 v254; // rbx
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rbx
  __int64 v258; // rdx
  __int64 v259; // rcx
  __int64 v260; // rax
  unsigned int v261; // ebx
  __int64 v262; // rax
  __int64 v263; // rax
  __int64 v264; // rbx
  __int64 v265; // rdx
  __int64 v266; // rcx
  const wchar_t *v267; // rdx
  __int64 v268; // rcx
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rax
  unsigned int v272; // ebx
  __int64 v273; // rdx
  __int64 v274; // rcx
  const wchar_t *v275; // rdx
  __int64 v276; // rcx
  __int64 v277; // rax
  __int64 v278; // rax
  unsigned int v279; // r14d
  __int64 v280; // rbx
  int v281; // ecx
  int v282; // ecx
  int v283; // ecx
  __int64 v284; // rax
  __int64 v285; // rax
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rax
  __int64 v290; // rax
  __int64 v291; // rax
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rax
  __int64 v296; // rax
  __int64 v297; // rax
  __int64 v298; // rax
  __int64 v299; // rax
  __int64 v300; // rax
  __int64 v301; // rax
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rax
  __int64 v308; // rax
  __int64 v309; // rax
  __int64 v310; // rax
  __int64 v311; // r8
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  __int64 v317; // rax
  __int64 v318; // rax
  __int64 v319; // rax
  __int64 v320; // rax
  __int64 v321; // rax
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // rax
  int v326; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v327[8]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v328[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v329[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v330[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v331[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v332[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v333[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v334[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v335[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v336[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v337[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v338[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v339[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v340[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v341[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v342[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v343[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v344[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v345[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v346[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v347[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v348[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v349[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v350[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v351[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v352[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v353[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v354[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v355[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v356[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v357[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v358[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v359[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v360[8]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v361[8]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v362[8]; // [rsp+140h] [rbp+40h] BYREF
  mlib::XmlStream *v363; // [rsp+148h] [rbp+48h]
  __int128 v364; // [rsp+150h] [rbp+50h] BYREF
  int v365; // [rsp+160h] [rbp+60h]

  v1 = this;
  v363 = this;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v338,
    L"Processor");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v2, v338);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v337,
    L"Instance");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v3, v337);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v326,
    L"id");
  *((_DWORD *)v1 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v4, &v326);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, L"=");
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, 0);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v326);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v338);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v337,
    L"ProcessorName");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, v337);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v7 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo) + 8;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v7);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v338,
    L"ProcessorName");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, v338);
    v9 = v11;
    v8 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_14;
    v8 = L"/>";
    v9 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, v8);
LABEL_14:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v338);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"TSCFrequency");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, v329);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v13 = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v13);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"TSCFrequency");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v16, v328);
    v15 = v17;
    v14 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_23;
    v14 = L"/>";
    v15 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, v14);
LABEL_23:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v336,
    L"NumProcs");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v18, v336);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v19 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 448);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v19);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v335,
    L"NumProcs");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v22, v335);
    v21 = v23;
    v20 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_32;
    v20 = L"/>";
    v21 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, v20);
LABEL_32:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v334,
    L"NumCores");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v24, v334);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v25 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 452);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v25);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v333,
    L"NumCores");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v28, v333);
    v27 = v29;
    v26 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_41;
    v26 = L"/>";
    v27 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, v26);
LABEL_41:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v332,
    L"NumCPUs");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v30, v332);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v31 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 456);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v31);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v342,
    L"NumCPUs");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v34, v342);
    v33 = v35;
    v32 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_50;
    v32 = L"/>";
    v33 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, v32);
LABEL_50:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v341,
    L"NumCPUsPerCore");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v36, v341);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v37 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 460);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v37);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v340,
    L"NumCPUsPerCore");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v40, v340);
    v39 = v41;
    v38 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_59;
    v38 = L"/>";
    v39 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, v38);
LABEL_59:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v339,
    L"NumCoresPerProcessor");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v42, v339);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v43 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 464);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v43);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v326,
    L"NumCoresPerProcessor");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v46, &v326);
    v45 = v47;
    v44 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_68;
    v44 = L"/>";
    v45 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, v44);
LABEL_68:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v337,
    L"CoresAreThreaded");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v48, v337);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v49 = *(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                 + 468) != 0;
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v49);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v338,
    L"CoresAreThreaded");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, v338);
    v51 = v53;
    v50 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_77;
    v50 = L"/>";
    v51 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, v50);
LABEL_77:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v338);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v326);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v339);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v340);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v341);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v342);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  v364 = 0;
  v365 = 0;
  GetCPUID(&v364, 2147483649LL);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"X64Capable");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v54, v328);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v55 = L"1";
  if ( (v365 & 0x20000000) == 0 )
    v55 = L"0";
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v55);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"X64Capable");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v58, v329);
    v57 = v59;
    v56 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_88;
    v56 = L"/>";
    v57 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v57, v56);
LABEL_88:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"X64Running");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v60, v328);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"1");
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"X64Running");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v63, v329);
    v62 = v64;
    v61 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_97;
    v61 = L"/>";
    v62 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, v61);
LABEL_97:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  v65 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
  v66 = _wcsicmp((const wchar_t *)(v65 + 208), L"AMD") == 0;
  v67 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo);
  if ( !_wcsicmp((const wchar_t *)(v67 + 208), L"Intel") )
    v66 = 2;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"Signature");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v68, v327);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"Manufacturer");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v69, v331);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"friendly");
  *((_DWORD *)v1 + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v70, v330);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, L"=");
  v72 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo) + 208;
  mlib::XmlStream::BeforeText(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v72);
  mlib::XmlStream::AfterText(v1);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v66);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v326,
    L"Manufacturer");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v75, &v326);
    v74 = v76;
    v73 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_110;
    v73 = L"/>";
    v74 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, v73);
LABEL_110:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v337,
    L"Stepping");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v77, v337);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v78 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                           + 480);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v78);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v338,
    L"Stepping");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v81, v338);
    v80 = v82;
    v79 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_119;
    v79 = L"/>";
    v80 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v80, v79);
LABEL_119:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v339,
    L"Model");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v83, v339);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v84 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                           + 481);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v84);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v340,
    L"Model");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v87, v340);
    v86 = v88;
    v85 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_128;
    v85 = L"/>";
    v86 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v86, v85);
LABEL_128:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v341,
    L"Family");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v89, v341);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v90 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                           + 482);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v90);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v342,
    L"Family");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v93, v342);
    v92 = v94;
    v91 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_137;
    v91 = L"/>";
    v92 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v92, v91);
LABEL_137:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v332,
    L"ExtendedModel");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v95, v332);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v96 = *(unsigned __int8 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                           + 483);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v96);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v333,
    L"ExtendedModel");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v99, v333);
    v98 = v100;
    v97 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_146;
    v97 = L"/>";
    v98 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, v97);
LABEL_146:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v334,
    L"ExtendedFamily");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v101, v334);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v102 = *(unsigned __int16 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                             + 484);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v102);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v335,
    L"ExtendedFamily");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v105, v335);
    v104 = v106;
    v103 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_155;
    v103 = L"/>";
    v104 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v104, v103);
LABEL_155:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v336,
    L"CompactSignature");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v107, v336);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v108 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 486);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v108);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"CompactSignature");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v111, v328);
    v110 = v112;
    v109 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_164;
    v109 = L"/>";
    v110 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, v109);
LABEL_164:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"Signature");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v115, v329);
    v114 = v116;
    v113 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_171;
    v113 = L"/>";
    v114 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, v113);
LABEL_171:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v342);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v341);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v340);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v339);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v338);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v326);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 408) )
    goto LABEL_218;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v332,
    L"L1Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v117, v332);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v333,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v118, v333);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v119 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 408);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v119);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v334,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v122, v334);
    v121 = v123;
    v120 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_183;
    v120 = L"/>";
    v121 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v121, v120);
LABEL_183:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v335,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v124, v335);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v125 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 416);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v125);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v336,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v128, v336);
    v127 = v129;
    v126 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_192;
    v126 = L"/>";
    v127 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, v126);
LABEL_192:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v130, v328);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v131 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 412);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v131);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v134, v329);
    v133 = v135;
    v132 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_201;
    v132 = L"/>";
    v133 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v133, v132);
LABEL_201:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v136, v330);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v137 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 408);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v137);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v140, v331);
    v139 = v141;
    v138 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_210;
    v138 = L"/>";
    v139 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v139, v138);
LABEL_210:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"L1Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v144, v327);
    v143 = v145;
    v142 = L">";
    goto LABEL_216;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v142 = L"/>";
    v143 = *(_QWORD *)v1;
LABEL_216:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v143, v142);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
LABEL_218:
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 420) )
    goto LABEL_265;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v332,
    L"L2Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v146, v332);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v333,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v147, v333);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v148 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 420);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v148);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v334,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v151, v334);
    v150 = v152;
    v149 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_230;
    v149 = L"/>";
    v150 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, v149);
LABEL_230:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v335,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v153, v335);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v154 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 428);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v154);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v336,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v157, v336);
    v156 = v158;
    v155 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_239;
    v155 = L"/>";
    v156 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, v155);
LABEL_239:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v159, v328);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v160 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 424);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v160);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v163, v329);
    v162 = v164;
    v161 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_248;
    v161 = L"/>";
    v162 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, v161);
LABEL_248:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v165, v330);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v166 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 420);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v166);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v169, v331);
    v168 = v170;
    v167 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_257;
    v167 = L"/>";
    v168 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, v167);
LABEL_257:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"L2Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v173, v327);
    v172 = v174;
    v171 = L">";
    goto LABEL_263;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v171 = L"/>";
    v172 = *(_QWORD *)v1;
LABEL_263:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v172, v171);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
LABEL_265:
  if ( !*(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                  + 432) )
    goto LABEL_312;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v332,
    L"L3Cache");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v175, v332);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v333,
    L"Size");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v176, v333);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v177 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 432);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v177);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v334,
    L"Size");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v180, v334);
    v179 = v181;
    v178 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_277;
    v178 = L"/>";
    v179 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v179, v178);
LABEL_277:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v335,
    L"Ways");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v182, v335);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v183 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 440);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v183);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v336,
    L"Ways");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v186, v336);
    v185 = v187;
    v184 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_286;
    v184 = L"/>";
    v185 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v185, v184);
LABEL_286:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v328,
    L"LineSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v188, v328);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v189 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 436);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v189);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v329,
    L"LineSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v192, v329);
    v191 = v193;
    v190 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_295;
    v190 = L"/>";
    v191 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v191, v190);
LABEL_295:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"SectorSize");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v194, v330);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  v195 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 432);
  mlib::XmlStream::BeforeText(v1);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v195);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"SectorSize");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v198, v331);
    v197 = v199;
    v196 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_304;
    v196 = L"/>";
    v197 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v197, v196);
LABEL_304:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"L3Cache");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v202, v327);
    v201 = v203;
    v200 = L">";
    goto LABEL_310;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v200 = L"/>";
    v201 = *(_QWORD *)v1;
LABEL_310:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v201, v200);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v336);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v332);
LABEL_312:
  v204 = IsProcessorFeaturePresent(3u);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"MMX");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v205, v331);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v206 = L"Yes";
  v207 = L"Yes";
  if ( !v204 )
    v207 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v207);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"MMX");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v210, v327);
    v209 = v211;
    v208 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_323;
    v208 = L"/>";
    v209 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, v208);
LABEL_323:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  v212 = IsProcessorFeaturePresent(6u);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"SSE");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v213, v330);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v214 = L"Yes";
  if ( !v212 )
    v214 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v214);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"SSE");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v217, v327);
    v216 = v218;
    v215 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_334;
    v215 = L"/>";
    v216 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v216, v215);
LABEL_334:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  v219 = IsProcessorFeaturePresent(0xAu);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v331,
    L"SSE2");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v220, v331);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  v221 = L"Yes";
  if ( !v219 )
    v221 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v221);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"SSE2");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v224, v327);
    v223 = v225;
    v222 = L">";
  }
  else
  {
    if ( *((_DWORD *)v1 + 2) != 2 )
      goto LABEL_345;
    v222 = L"/>";
    v223 = *(_QWORD *)v1;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v223, v222);
LABEL_345:
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
  v226 = IsProcessorFeaturePresent(0xDu);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v330,
    L"SSE3");
  if ( *((_DWORD *)v1 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
  *((_DWORD *)v1 + 2) = 2;
  mlib::XmlStream::Indent(v1);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v227, v330);
  ++*((_DWORD *)v1 + 3);
  *((_BYTE *)v1 + 17) = 0;
  mlib::XmlStream::BeforeText(v1);
  if ( !v226 )
    v206 = L"No";
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v206);
  mlib::XmlStream::AfterText(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v327,
    L"SSE3");
  --*((_DWORD *)v1 + 3);
  if ( *((_DWORD *)v1 + 2) == 1 )
  {
    if ( !*((_BYTE *)v1 + 17) )
      mlib::XmlStream::Indent(v1);
    *((_BYTE *)v1 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v230, v327);
    v229 = v231;
    v228 = L">";
    goto LABEL_355;
  }
  if ( *((_DWORD *)v1 + 2) == 2 )
  {
    v228 = L"/>";
    v229 = *(_QWORD *)v1;
LABEL_355:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v229, v228);
  }
  *((_DWORD *)v1 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
  if ( *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                 + 1024) )
  {
    v232 = *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                     + 1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v327,
      L"LogicalProcessorInfo");
    if ( *((_DWORD *)v1 + 2) == 2 )
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
    *((_DWORD *)v1 + 2) = 2;
    mlib::XmlStream::Indent(v1);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v233, v327);
    ++*((_DWORD *)v1 + 3);
    *((_BYTE *)v1 + 17) = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
    for ( i = 0;
          (unsigned __int64)i < *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                                          + 1032);
          ++i )
    {
      v235 = 32LL * i;
      v236 = *(_DWORD *)(v235 + v232 + 8);
      if ( v236 )
      {
        v237 = v236 - 1;
        if ( v237 )
        {
          v238 = v237 - 1;
          if ( v238 )
          {
            if ( v238 == 1 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v332,
                L"RelationProcessorPackage");
              mlib::XmlStream::WriteBeginTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v333,
                L"Mask");
              mlib::XmlStream::WriteBeginTag(v1);
              v326 = 16;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
              mlib::XmlStream::AfterText(v1);
              v241 = *(_QWORD *)(v235 + v232);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v241);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::BeforeText(v1);
              v242 = *(_QWORD *)v1;
              v243 = *(int *)(**(_QWORD **)v1 + 4LL);
              *(_DWORD *)(v243 + v242 + 24) |= 0x201u;
              *(_WORD *)(*(int *)(*(_QWORD *)v242 + 4LL) + v242 + 88) = 32;
              *(_QWORD *)(*(int *)(*(_QWORD *)v242 + 4LL) + v242 + 40) = 0;
              mlib::XmlStream::AfterText(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v334,
                L"Mask");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v335,
                L"RelationProcessorPackage");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v335);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v334);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v333);
              v240 = v332;
            }
            else
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v336,
                L"RelationUnknown");
              mlib::XmlStream::WriteBeginTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v328,
                L"Mask");
              mlib::XmlStream::WriteBeginTag(v1);
              v326 = 16;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
              mlib::XmlStream::AfterText(v1);
              v239 = *(_QWORD *)(v235 + v232);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v239);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::WriteText<mlib::_normobj>(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v329,
                L"Mask");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v330,
                L"Relationship");
              mlib::XmlStream::WriteBeginTag(v1);
              v326 = 8;
              mlib::XmlStream::BeforeText(v1);
              mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
              mlib::XmlStream::AfterText(v1);
              LODWORD(v239) = *(_DWORD *)(v235 + v232 + 8);
              mlib::XmlStream::BeforeText(v1);
              std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, (unsigned int)v239);
              mlib::XmlStream::AfterText(v1);
              mlib::XmlStream::WriteText<mlib::_normobj>(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v331,
                L"Relationship");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                v327,
                L"RelationUnknown");
              mlib::XmlStream::WriteEndTag(v1);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v327);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v331);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v330);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v329);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v328);
              v240 = v336;
            }
          }
          else
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v350,
              L"RelationCache");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v244, v350);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v349,
              L"Mask");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v245, v349);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            v326 = 16;
            mlib::XmlStream::BeforeText(v1);
            mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
            mlib::XmlStream::AfterText(v1);
            v246 = *(_QWORD *)(v235 + v232);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v246);
            mlib::XmlStream::AfterText(v1);
            mlib::XmlStream::BeforeText(v1);
            v247 = *(_QWORD *)v1;
            v248 = *(int *)(**(_QWORD **)v1 + 4LL);
            *(_DWORD *)(v248 + v247 + 24) |= 0x201u;
            *(_WORD *)(*(int *)(*(_QWORD *)v247 + 4LL) + v247 + 88) = 32;
            *(_QWORD *)(*(int *)(*(_QWORD *)v247 + 4LL) + v247 + 40) = 0;
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v348,
              L"Mask");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v347,
              L"Level");
            if ( *((_DWORD *)v1 + 2) == 2 )
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
            *((_DWORD *)v1 + 2) = 2;
            mlib::XmlStream::Indent(v1);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v249, v347);
            ++*((_DWORD *)v1 + 3);
            *((_BYTE *)v1 + 17) = 0;
            v250 = *(unsigned __int8 *)(v235 + v232 + 16);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v250);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v346,
              L"Level");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v345,
              L"Size");
            mlib::XmlStream::WriteBeginTag(v1);
            v251 = *(_DWORD *)(v235 + v232 + 20);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v251);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v362,
              L"Size");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v361,
              L"LineSize");
            mlib::XmlStream::WriteBeginTag(v1);
            v252 = *(unsigned __int16 *)(v235 + v232 + 18);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v252);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v337,
              L"LineSize");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v338,
              L"Associativity");
            mlib::XmlStream::WriteBeginTag(v1);
            v253 = *(unsigned __int8 *)(v235 + v232 + 17);
            mlib::XmlStream::BeforeText(v1);
            std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v253);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v339,
              L"Associativity");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v340,
              L"Type");
            mlib::XmlStream::WriteBeginTag(v1);
            v254 = CachTypeStr(*(unsigned int *)(v235 + v232 + 24));
            mlib::XmlStream::BeforeText(v1);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, v254);
            mlib::XmlStream::AfterText(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v341,
              L"Type");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              v342,
              L"RelationCache");
            mlib::XmlStream::WriteEndTag(v1);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v342);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v341);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v340);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v339);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v338);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v337);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v361);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v362);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v345);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v346);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v347);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v348);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v349);
            v240 = v350;
          }
        }
        else
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v356,
            L"RelationNumaNode");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v255, v356);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v355,
            L"Mask");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v256, v355);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          v326 = 16;
          mlib::XmlStream::BeforeText(v1);
          mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
          mlib::XmlStream::AfterText(v1);
          v257 = *(_QWORD *)(v235 + v232);
          mlib::XmlStream::BeforeText(v1);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v257);
          mlib::XmlStream::AfterText(v1);
          mlib::XmlStream::BeforeText(v1);
          v258 = *(_QWORD *)v1;
          v259 = *(int *)(**(_QWORD **)v1 + 4LL);
          *(_DWORD *)(v259 + v258 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v258 + 4LL) + v258 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v258 + 4LL) + v258 + 40) = 0;
          mlib::XmlStream::AfterText(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v354,
            L"Mask");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v353,
            L"NodeNum");
          if ( *((_DWORD *)v1 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
          *((_DWORD *)v1 + 2) = 2;
          mlib::XmlStream::Indent(v1);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v260, v353);
          ++*((_DWORD *)v1 + 3);
          *((_BYTE *)v1 + 17) = 0;
          v261 = *(_DWORD *)(v235 + v232 + 16);
          mlib::XmlStream::BeforeText(v1);
          std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v261);
          mlib::XmlStream::AfterText(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v352,
            L"NodeNum");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v351,
            L"RelationNumaNode");
          mlib::XmlStream::WriteEndTag(v1);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v351);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v352);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v353);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v354);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v355);
          v240 = v356;
        }
        goto LABEL_401;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v343,
        L"RelationProcessorCore");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v262, v343);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v344,
        L"Mask");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v263, v344);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      v326 = 16;
      mlib::XmlStream::BeforeText(v1);
      mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
      mlib::XmlStream::AfterText(v1);
      v264 = *(_QWORD *)(v235 + v232);
      mlib::XmlStream::BeforeText(v1);
      std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v264);
      mlib::XmlStream::AfterText(v1);
      mlib::XmlStream::BeforeText(v1);
      v265 = *(_QWORD *)v1;
      v266 = *(int *)(**(_QWORD **)v1 + 4LL);
      *(_DWORD *)(v266 + v265 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v265 + 4LL) + v265 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v265 + 4LL) + v265 + 40) = 0;
      mlib::XmlStream::AfterText(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v360,
        L"Mask");
      --*((_DWORD *)v1 + 3);
      if ( *((_DWORD *)v1 + 2) == 1 )
      {
        if ( !*((_BYTE *)v1 + 17) )
          mlib::XmlStream::Indent(v1);
        *((_BYTE *)v1 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v269, v360);
        v268 = v270;
        v267 = L">";
      }
      else
      {
        if ( *((_DWORD *)v1 + 2) != 2 )
          goto LABEL_391;
        v267 = L"/>";
        v268 = *(_QWORD *)v1;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v268, v267);
LABEL_391:
      *((_DWORD *)v1 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v359,
        L"Flags");
      if ( *((_DWORD *)v1 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L">");
      *((_DWORD *)v1 + 2) = 2;
      mlib::XmlStream::Indent(v1);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v271, v359);
      ++*((_DWORD *)v1 + 3);
      *((_BYTE *)v1 + 17) = 0;
      v326 = 2;
      mlib::XmlStream::BeforeText(v1);
      mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, &v326);
      mlib::XmlStream::AfterText(v1);
      v272 = *(unsigned __int8 *)(v235 + v232 + 16);
      mlib::XmlStream::BeforeText(v1);
      std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)v1, v272);
      mlib::XmlStream::AfterText(v1);
      mlib::XmlStream::BeforeText(v1);
      v273 = *(_QWORD *)v1;
      v274 = *(int *)(**(_QWORD **)v1 + 4LL);
      *(_DWORD *)(v274 + v273 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v273 + 4LL) + v273 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v273 + 4LL) + v273 + 40) = 0;
      mlib::XmlStream::AfterText(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v358,
        L"Flags");
      --*((_DWORD *)v1 + 3);
      if ( *((_DWORD *)v1 + 2) == 1 )
      {
        if ( !*((_BYTE *)v1 + 17) )
          mlib::XmlStream::Indent(v1);
        *((_BYTE *)v1 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)v1, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v277, v358);
        v276 = v278;
        v275 = L">";
        goto LABEL_399;
      }
      if ( *((_DWORD *)v1 + 2) == 2 )
      {
        v275 = L"/>";
        v276 = *(_QWORD *)v1;
LABEL_399:
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v276, v275);
      }
      *((_DWORD *)v1 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v357,
        L"RelationProcessorCore");
      mlib::XmlStream::WriteEndTag(v1);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v357);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v358);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v359);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v360);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v344);
      v240 = v343;
LABEL_401:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v240);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v343,
      L"LogicalProcessorInfo");
    mlib::XmlStream::WriteEndTag(v1);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v343);
    if ( App::s_VVerbose )
    {
      v279 = 0;
      if ( *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                     + 1032) )
      {
        while ( 1 )
        {
          v280 = 32LL * v279;
          v281 = *(_DWORD *)(v280 + v232 + 8);
          if ( !v281 )
            break;
          v282 = v281 - 1;
          if ( v282 )
          {
            v283 = v282 - 1;
            if ( v283 )
            {
              if ( v283 != 1 )
              {
                v284 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  v284 + 240,
                  L"  Relation UNKNOWN         ");
                v326 = 16;
                v286 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v285, &v326);
                v287 = std::basic_ostream<unsigned short>::operator<<(v286, *(_QWORD *)(v280 + v232));
                *(_DWORD *)(*(int *)(*(_QWORD *)v287 + 4LL) + v287 + 24) |= 0x201u;
                *(_WORD *)(*(int *)(*(_QWORD *)v287 + 4LL) + v287 + 88) = 32;
                *(_QWORD *)(*(int *)(*(_QWORD *)v287 + 4LL) + v287 + 40) = 0;
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v287, L"  ");
                std::operator<<<unsigned short,std::char_traits<unsigned short>>(v288, L"  Relation=");
                v326 = 8;
                v290 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v289, &v326);
                v291 = std::basic_ostream<unsigned short>::operator<<(v290, *(unsigned int *)(v280 + v232 + 8));
LABEL_413:
                *(_DWORD *)(*(int *)(*(_QWORD *)v291 + 4LL) + v291 + 24) |= 0x201u;
                *(_WORD *)(*(int *)(*(_QWORD *)v291 + 4LL) + v291 + 88) = 32;
                *(_QWORD *)(*(int *)(*(_QWORD *)v291 + 4LL) + v291 + 40) = 0;
                goto LABEL_414;
              }
              v292 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                v292 + 240,
                L"  RelationProcessorPackage ");
              v326 = 16;
              v294 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v293, &v326);
              v295 = std::basic_ostream<unsigned short>::operator<<(v294, *(_QWORD *)(v280 + v232));
              *(_DWORD *)(*(int *)(*(_QWORD *)v295 + 4LL) + v295 + 24) |= 0x201u;
              *(_WORD *)(*(int *)(*(_QWORD *)v295 + 4LL) + v295 + 88) = 32;
              *(_QWORD *)(*(int *)(*(_QWORD *)v295 + 4LL) + v295 + 40) = 0;
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v295, L"  ");
            }
            else
            {
              v296 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                v296 + 240,
                L"  RelationCache            ");
              v326 = 16;
              v298 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v297, &v326);
              v299 = std::basic_ostream<unsigned short>::operator<<(v298, *(_QWORD *)(v280 + v232));
              *(_DWORD *)(*(int *)(*(_QWORD *)v299 + 4LL) + v299 + 24) |= 0x201u;
              *(_WORD *)(*(int *)(*(_QWORD *)v299 + 4LL) + v299 + 88) = 32;
              *(_QWORD *)(*(int *)(*(_QWORD *)v299 + 4LL) + v299 + 40) = 0;
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v299, L"  ");
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v300, L"  Cache| Level:");
              v302 = std::basic_ostream<unsigned short>::operator<<(v301, *(unsigned __int8 *)(v280 + v232 + 16));
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v302, L" Assoc:");
              v326 = 2;
              v304 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v303, &v326);
              v305 = std::basic_ostream<unsigned short>::operator<<(v304, *(unsigned __int8 *)(v280 + v232 + 17));
              *(_DWORD *)(*(int *)(*(_QWORD *)v305 + 4LL) + v305 + 24) |= 0x201u;
              *(_WORD *)(*(int *)(*(_QWORD *)v305 + 4LL) + v305 + 88) = 32;
              *(_QWORD *)(*(int *)(*(_QWORD *)v305 + 4LL) + v305 + 40) = 0;
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v305, L" LineSize:");
              v307 = std::basic_ostream<unsigned short>::operator<<(v306, *(unsigned __int16 *)(v280 + v232 + 18));
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v307, L" Size:");
              v309 = std::basic_ostream<unsigned short>::operator<<(v308, *(unsigned int *)(v280 + v232 + 20));
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v309, L" Type:");
              v310 = CachTypeStr(*(unsigned int *)(v280 + v232 + 24));
              std::operator<<<unsigned short,std::char_traits<unsigned short>>(v311, v310);
            }
          }
          else
          {
            v312 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v312 + 240, L"  RelationNumaNode         ");
            v326 = 16;
            v314 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v313, &v326);
            v315 = std::basic_ostream<unsigned short>::operator<<(v314, *(_QWORD *)(v280 + v232));
            *(_DWORD *)(*(int *)(*(_QWORD *)v315 + 4LL) + v315 + 24) |= 0x201u;
            *(_WORD *)(*(int *)(*(_QWORD *)v315 + 4LL) + v315 + 88) = 32;
            *(_QWORD *)(*(int *)(*(_QWORD *)v315 + 4LL) + v315 + 40) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v315, L"  ");
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v316, L"  NodeNum=");
            v291 = std::basic_ostream<unsigned short>::operator<<(v317, *(unsigned int *)(v280 + v232 + 16));
          }
LABEL_414:
          std::endl(v291);
          if ( (unsigned __int64)++v279 >= *(_QWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                                                     + 1032) )
          {
            v1 = v363;
            goto LABEL_416;
          }
        }
        v318 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v318 + 240, L"  RelationProcessorCore    ");
        v326 = 16;
        v320 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v319, &v326);
        v321 = std::basic_ostream<unsigned short>::operator<<(v320, *(_QWORD *)(v280 + v232));
        *(_DWORD *)(*(int *)(*(_QWORD *)v321 + 4LL) + v321 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v321 + 4LL) + v321 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v321 + 4LL) + v321 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v321, L"  ");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v322, L"  Flags=");
        v326 = 2;
        v324 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v323, &v326);
        v291 = std::basic_ostream<unsigned short>::operator<<(v324, *(unsigned __int8 *)(v280 + v232 + 16));
        goto LABEL_413;
      }
    }
  }
LABEL_416:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v344,
    L"Instance");
  mlib::XmlStream::WriteEndTag(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v343,
    L"Processor");
  mlib::XmlStream::WriteEndTag(v1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v343);
  return mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v344);
}

```

## disassembly

```asm
0x1400228c4  push    rbp
0x1400228c6  push    rbx
0x1400228c7  push    rsi
0x1400228c8  push    rdi
0x1400228c9  push    r12
0x1400228cb  push    r13
0x1400228cd  push    r14
0x1400228cf  push    r15
0x1400228d1  lea     rbp, [rsp-78h]
0x1400228d6  sub     rsp, 178h
0x1400228dd  mov     rax, cs:__security_cookie
0x1400228e4  xor     rax, rsp
0x1400228e7  mov     [rbp+0B0h+var_48], rax
0x1400228eb  mov     rdi, rcx
0x1400228ee  mov     [rbp+0B0h+var_68], rcx
0x1400228f2  lea     rdx, aProcessor_0; "Processor"
0x1400228f9  lea     rcx, [rbp+0B0h+var_130]
0x1400228fd  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022902  nop
0x140022903  lea     r14, asc_14012B480; ">"
0x14002290a  mov     r13d, 2
0x140022910  cmp     [rdi+8], r13d
0x140022914  jnz     short loc_140022921
0x140022916  mov     rdx, r14
0x140022919  mov     rcx, [rdi]
0x14002291c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022921  mov     [rdi+8], r13d
0x140022925  mov     rcx, rdi; this
0x140022928  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002292d  lea     rsi, asc_14012B484; "<"
0x140022934  mov     rdx, rsi
0x140022937  mov     rcx, [rdi]
0x14002293a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002293f  mov     rcx, rax
0x140022942  lea     rdx, [rbp+0B0h+var_130]
0x140022946  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002294b  mov     r15d, 1
0x140022951  add     [rdi+0Ch], r15d
0x140022955  xor     r12d, r12d
0x140022958  mov     [rdi+11h], r12b
0x14002295c  lea     rdx, aInstance; "Instance"
0x140022963  lea     rcx, [rsp+1B0h+var_138]
0x140022968  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002296d  nop
0x14002296e  cmp     [rdi+8], r13d
0x140022972  jnz     short loc_14002297F
0x140022974  mov     rdx, r14
0x140022977  mov     rcx, [rdi]
0x14002297a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002297f  mov     [rdi+8], r13d
0x140022983  mov     rcx, rdi; this
0x140022986  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002298b  mov     rdx, rsi
0x14002298e  mov     rcx, [rdi]
0x140022991  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022996  mov     rcx, rax
0x140022999  lea     rdx, [rsp+1B0h+var_138]
0x14002299e  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400229a3  add     [rdi+0Ch], r15d
0x1400229a7  mov     [rdi+11h], r12b
0x1400229ab  lea     rdx, aId; "id"
0x1400229b2  lea     rcx, [rsp+1B0h+var_190]
0x1400229b7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400229bc  nop
0x1400229bd  mov     dword ptr [rdi+8], 3
0x1400229c4  lea     rdx, asc_14012B49C; " "
0x1400229cb  mov     rcx, [rdi]
0x1400229ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400229d3  mov     rcx, rax
0x1400229d6  lea     rdx, [rsp+1B0h+var_190]
0x1400229db  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400229e0  mov     rcx, rax
0x1400229e3  lea     rdx, asc_14012B498; "="
0x1400229ea  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400229ef  mov     rcx, rdi; this
0x1400229f2  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x1400229f7  xor     edx, edx
0x1400229f9  mov     rcx, [rdi]
0x1400229fc  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x140022a01  mov     rcx, rdi; this
0x140022a04  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022a09  nop
0x140022a0a  lea     rcx, [rsp+1B0h+var_190]
0x140022a0f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a14  nop
0x140022a15  lea     rcx, [rsp+1B0h+var_138]
0x140022a1a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a1f  nop
0x140022a20  lea     rcx, [rbp+0B0h+var_130]
0x140022a24  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022a29  lea     rdx, aProcessorname; "ProcessorName"
0x140022a30  lea     rcx, [rsp+1B0h+var_138]
0x140022a35  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022a3a  nop
0x140022a3b  cmp     [rdi+8], r13d
0x140022a3f  jnz     short loc_140022A4C
0x140022a41  mov     rdx, r14
0x140022a44  mov     rcx, [rdi]
0x140022a47  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a4c  mov     [rdi+8], r13d
0x140022a50  mov     rcx, rdi; this
0x140022a53  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022a58  mov     rdx, rsi
0x140022a5b  mov     rcx, [rdi]
0x140022a5e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a63  mov     rcx, rax
0x140022a66  lea     rdx, [rsp+1B0h+var_138]
0x140022a6b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022a70  add     [rdi+0Ch], r15d
0x140022a74  mov     [rdi+11h], r12b
0x140022a78  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022a7f  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022a84  lea     rbx, [rax+8]
0x140022a88  mov     rcx, rdi; this
0x140022a8b  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022a90  mov     rdx, rbx
0x140022a93  mov     rcx, [rdi]
0x140022a96  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022a9b  mov     rcx, rdi; this
0x140022a9e  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022aa3  lea     rdx, aProcessorname; "ProcessorName"
0x140022aaa  lea     rcx, [rbp+0B0h+var_130]
0x140022aae  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022ab3  nop
0x140022ab4  dec     dword ptr [rdi+0Ch]
0x140022ab7  mov     ecx, [rdi+8]
0x140022aba  sub     ecx, 1
0x140022abd  jz      short loc_140022AD0
0x140022abf  cmp     ecx, 1
0x140022ac2  jnz     short loc_140022B08
0x140022ac4  lea     rdx, asc_14012B488; "/>"
0x140022acb  mov     rcx, [rdi]
0x140022ace  jmp     short loc_140022B03
0x140022ad0  cmp     [rdi+11h], r12b
0x140022ad4  jnz     short loc_140022ADE
0x140022ad6  mov     rcx, rdi; this
0x140022ad9  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022ade  mov     [rdi+11h], r12b
0x140022ae2  lea     rdx, asc_14012B490; "</"
0x140022ae9  mov     rcx, [rdi]
0x140022aec  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022af1  mov     rcx, rax
0x140022af4  lea     rdx, [rbp+0B0h+var_130]
0x140022af8  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022afd  mov     rcx, rax
0x140022b00  mov     rdx, r14
0x140022b03  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b08  mov     [rdi+8], r15d
0x140022b0c  lea     rcx, [rbp+0B0h+var_130]
0x140022b10  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022b15  nop
0x140022b16  lea     rcx, [rsp+1B0h+var_138]
0x140022b1b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140022b20  lea     rdx, aTscfrequency; "TSCFrequency"
0x140022b27  lea     rcx, [rsp+1B0h+var_178]
0x140022b2c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022b31  nop
0x140022b32  cmp     [rdi+8], r13d
0x140022b36  jnz     short loc_140022B43
0x140022b38  mov     rdx, r14
0x140022b3b  mov     rcx, [rdi]
0x140022b3e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b43  mov     [rdi+8], r13d
0x140022b47  mov     rcx, rdi; this
0x140022b4a  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022b4f  mov     rdx, rsi
0x140022b52  mov     rcx, [rdi]
0x140022b55  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022b5a  mov     rcx, rax
0x140022b5d  lea     rdx, [rsp+1B0h+var_178]
0x140022b62  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022b67  add     [rdi+0Ch], r15d
0x140022b6b  mov     [rdi+11h], r12b
0x140022b6f  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022b76  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022b7b  mov     rbx, [rax]
0x140022b7e  mov     rcx, rdi; this
0x140022b81  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022b86  mov     rdx, rbx
0x140022b89  mov     rcx, [rdi]
0x140022b8c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x140022b91  mov     rcx, rdi; this
0x140022b94  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022b99  lea     rdx, aTscfrequency; "TSCFrequency"
0x140022ba0  lea     rcx, [rsp+1B0h+var_180]
0x140022ba5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022baa  nop
0x140022bab  dec     dword ptr [rdi+0Ch]
0x140022bae  mov     ecx, [rdi+8]
0x140022bb1  sub     ecx, 1
0x140022bb4  jz      short loc_140022BC7
0x140022bb6  cmp     ecx, 1
0x140022bb9  jnz     short loc_140022C00
0x140022bbb  lea     rdx, asc_14012B488; "/>"
0x140022bc2  mov     rcx, [rdi]
0x140022bc5  jmp     short loc_140022BFB
0x140022bc7  cmp     [rdi+11h], r12b
0x140022bcb  jnz     short loc_140022BD5
0x140022bcd  mov     rcx, rdi; this
0x140022bd0  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022bd5  mov     [rdi+11h], r12b
0x140022bd9  lea     rdx, asc_14012B490; "</"
0x140022be0  mov     rcx, [rdi]
0x140022be3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022be8  mov     rcx, rax
0x140022beb  lea     rdx, [rsp+1B0h+var_180]
0x140022bf0  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022bf5  mov     rcx, rax
0x140022bf8  mov     rdx, r14
0x140022bfb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c00  mov     [rdi+8], r15d
0x140022c04  lea     rdx, aNumprocs; "NumProcs"
0x140022c0b  lea     rcx, [rsp+1B0h+var_140]
0x140022c10  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022c15  nop
0x140022c16  cmp     [rdi+8], r13d
0x140022c1a  jnz     short loc_140022C27
0x140022c1c  mov     rdx, r14
0x140022c1f  mov     rcx, [rdi]
0x140022c22  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c27  mov     [rdi+8], r13d
0x140022c2b  mov     rcx, rdi; this
0x140022c2e  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022c33  mov     rdx, rsi
0x140022c36  mov     rcx, [rdi]
0x140022c39  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022c3e  mov     rcx, rax
0x140022c41  lea     rdx, [rsp+1B0h+var_140]
0x140022c46  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022c4b  add     [rdi+0Ch], r15d
0x140022c4f  mov     [rdi+11h], r12b
0x140022c53  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022c5a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022c5f  mov     ebx, [rax+1C0h]
0x140022c65  mov     rcx, rdi; this
0x140022c68  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022c6d  mov     edx, ebx
0x140022c6f  mov     rcx, [rdi]
0x140022c72  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140022c77  mov     rcx, rdi; this
0x140022c7a  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022c7f  lea     rdx, aNumprocs; "NumProcs"
0x140022c86  lea     rcx, [rsp+1B0h+var_148]
0x140022c8b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022c90  nop
0x140022c91  dec     dword ptr [rdi+0Ch]
0x140022c94  mov     ecx, [rdi+8]
0x140022c97  sub     ecx, 1
0x140022c9a  jz      short loc_140022CAD
0x140022c9c  cmp     ecx, 1
0x140022c9f  jnz     short loc_140022CE6
0x140022ca1  lea     rdx, asc_14012B488; "/>"
0x140022ca8  mov     rcx, [rdi]
0x140022cab  jmp     short loc_140022CE1
0x140022cad  cmp     [rdi+11h], r12b
0x140022cb1  jnz     short loc_140022CBB
0x140022cb3  mov     rcx, rdi; this
0x140022cb6  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022cbb  mov     [rdi+11h], r12b
0x140022cbf  lea     rdx, asc_14012B490; "</"
0x140022cc6  mov     rcx, [rdi]
0x140022cc9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022cce  mov     rcx, rax
0x140022cd1  lea     rdx, [rsp+1B0h+var_148]
0x140022cd6  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022cdb  mov     rcx, rax
0x140022cde  mov     rdx, r14
0x140022ce1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022ce6  mov     [rdi+8], r15d
0x140022cea  lea     rdx, aNumcores; "NumCores"
0x140022cf1  lea     rcx, [rsp+1B0h+var_150]
0x140022cf6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140022cfb  nop
0x140022cfc  cmp     [rdi+8], r13d
0x140022d00  jnz     short loc_140022D0D
0x140022d02  mov     rdx, r14
0x140022d05  mov     rcx, [rdi]
0x140022d08  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022d0d  mov     [rdi+8], r13d
0x140022d11  mov     rcx, rdi; this
0x140022d14  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140022d19  mov     rdx, rsi
0x140022d1c  mov     rcx, [rdi]
0x140022d1f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140022d24  mov     rcx, rax
0x140022d27  lea     rdx, [rsp+1B0h+var_150]
0x140022d2c  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140022d31  add     [rdi+0Ch], r15d
0x140022d35  mov     [rdi+11h], r12b
0x140022d39  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140022d40  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140022d45  mov     ebx, [rax+1C4h]
0x140022d4b  mov     rcx, rdi; this
0x140022d4e  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140022d53  mov     edx, ebx
0x140022d55  mov     rcx, [rdi]
0x140022d58  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140022d5d  mov     rcx, rdi; this
0x140022d60  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140022d65  lea     rdx, aNumcores; "NumCores"
  ... truncated ...
```
