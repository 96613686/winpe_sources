# WinSAT::MemAssessment1::OutputResults(mlib::XmlStream &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14005ccd0`
- end: `0x14005ed77`
- name: `?OutputResults@MemAssessment1@WinSAT@@UEBAJAEAVXmlStream@mlib@@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@4@@Z`
- size: `8359`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config`

## callees

- `0x140001abc`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x140005d78`
- `0x14000695c`
- `0x140007e3c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x140008730`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016480`
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
- `0x14005ccd0`
- `0x1400603d4`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005cf52`
- `KERNEL32!GetLastError` at `0x14005cf52`
- `KERNEL32!GetExitCodeThread` at `0x14005ce8a`
- `KERNEL32!GetExitCodeThread` at `0x14005ce8a`

## string_xrefs

- `0x14005d65b`: `NumThreads`
- `0x14005d6d0`: `NumThreads`
- `0x14005d8d8`: `UnCachedMemSpace`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall WinSAT::MemAssessment1::OutputResults(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rbx
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int16 v12; // dx
  __int64 v13; // rax
  unsigned int v14; // r14d
  char v15; // bl
  unsigned int i; // r14d
  __int64 v17; // rcx
  __int64 v18; // rbx
  const unsigned __int16 *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  unsigned __int16 v26; // r9
  const unsigned __int16 *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  double v32; // xmm6_8
  double v33; // xmm7_8
  unsigned int v34; // edx
  _QWORD *j; // r13
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rbx
  void **v42; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  const wchar_t *v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  const wchar_t *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  unsigned int v66; // ebx
  const wchar_t *v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  unsigned int v72; // ebx
  const wchar_t *v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  unsigned int v80; // ebx
  const wchar_t *v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  const wchar_t *v88; // rbx
  __int64 v89; // rax
  __int64 v90; // rax
  unsigned int v91; // ebx
  const wchar_t *v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  unsigned int v99; // ebx
  const wchar_t *v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // rcx
  const wchar_t *v111; // rdx
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // rcx
  const wchar_t *v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  unsigned int v127; // r12d
  __int64 v128; // r15
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rbx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // rdx
  __int64 v140; // rcx
  const wchar_t *v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
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
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rdx
  __int64 v162; // rcx
  __int64 v163; // rdx
  __int64 v164; // rcx
  const wchar_t *v165; // rdx
  __int64 v166; // rcx
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // rdx
  __int64 v175; // rcx
  const wchar_t *v176; // rdx
  __int64 v177; // rcx
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  const wchar_t *v181; // rdx
  __int64 v182; // rcx
  __int64 v183; // rax
  __int64 v184; // rax
  const wchar_t *v185; // rdx
  __int64 v186; // rcx
  __int64 v187; // rax
  __int64 v188; // rax
  const wchar_t *v189; // rdx
  __int64 v190; // rcx
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v194; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v195; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v196; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v197[8]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v198[8]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v199[8]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v200[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v201[8]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v202[8]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v203[8]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v204[8]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v205[8]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v206[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v207[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v208[8]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v209[8]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v210[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v211[8]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v212[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v213[8]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v214[8]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v215[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v216[8]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v217[8]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v218[8]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v219[8]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v220[8]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v221[8]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v222[8]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v223[8]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v224[8]; // [rsp+128h] [rbp+20h] BYREF
  void *Block[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v226; // [rsp+140h] [rbp+38h]
  _QWORD Buffer[30]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v228[272]; // [rsp+248h] [rbp+140h] BYREF
  DWORD LastError; // [rsp+358h] [rbp+250h]
  char v230; // [rsp+35Ch] [rbp+254h]
  __int64 v231; // [rsp+360h] [rbp+258h]

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v197,
    L"TestName");
  if ( *((_DWORD *)a2 + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
  *((_DWORD *)a2 + 2) = 2;
  mlib::XmlStream::Indent((mlib::XmlStream *)a2);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, v197);
  ++*((_DWORD *)a2 + 3);
  *((_BYTE *)a2 + 17) = 0;
  v195 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v195,
    *(_QWORD *)(a1 + 728));
  v7 = (_QWORD *)mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>((mlib::XmlStream *)a2);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v196,
    L"TestName");
  --*((_DWORD *)v7 + 3);
  if ( *((_DWORD *)v7 + 2) == 1 )
  {
    if ( !*((_BYTE *)v7 + 17) )
      mlib::XmlStream::Indent((mlib::XmlStream *)v7);
    *((_BYTE *)v7 + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*v7, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v10, &v196);
    v9 = v11;
    v8 = L">";
    goto LABEL_9;
  }
  if ( *((_DWORD *)v7 + 2) == 2 )
  {
    v8 = L"/>";
    v9 = *v7;
LABEL_9:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, v8);
  }
  *((_DWORD *)v7 + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v196);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v197);
  if ( !*(_QWORD *)(a1 + 80) )
  {
    v12 = 620;
LABEL_12:
    v13 = mlib::MUILoader::MUILoader((mlib::MUILoader *)Block, v12);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=(
      a3,
      v13);
    return (unsigned int)-2147221503;
  }
  if ( *(_BYTE *)(a1 + 738) )
  {
    v12 = 619;
    goto LABEL_12;
  }
  v15 = 1;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 68) )
    {
      if ( !v15 )
      {
        v12 = 623;
        goto LABEL_12;
      }
      v14 = 0;
      *(_DWORD *)(a1 + 56) = 6;
      v32 = 0.0;
      v33 = 0.0;
      *(_OWORD *)Block = 0;
      v226 = 0;
      v194 = 0;
      std::vector<SampleManager const *>::resize(Block, *(unsigned int *)(a1 + 68), &v194);
      v34 = 0;
      for ( j = Block[0]; v34 < *(_DWORD *)(a1 + 68); ++v34 )
      {
        v36 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * v34);
        v32 = v32 + *(double *)(v36 + 72);
        v33 = v33 + *(double *)(v36 + 96);
        j[v34] = v36 + 152;
      }
      if ( *(_BYTE *)(a1 + 33) )
      {
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          *(_QWORD *)(a1 + 16) + 240LL,
          L"> Total BytesPerSecond        = ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 32) = 0;
        *(_QWORD *)(*(int *)(*(_QWORD *)v37 + 4LL) + v37 + 40) = 11;
        v38 = std::basic_ostream<unsigned short>::operator<<(v37);
        std::endl(v38);
        if ( *(_BYTE *)(a1 + 32) )
        {
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            *(_QWORD *)(a1 + 16) + 240LL,
            L"> Total BytesPerSecond (mean) = ");
          *(_DWORD *)(*(int *)(*(_QWORD *)v39 + 4LL) + v39 + 24) |= 0x2090u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v39 + 4LL) + v39 + 32) = 0;
          *(_QWORD *)(*(int *)(*(_QWORD *)v39 + 4LL) + v39 + 40) = 11;
          v40 = std::basic_ostream<unsigned short>::operator<<(v39);
          std::endl(v40);
        }
      }
      if ( *(_WORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40)
                    + 498) )
      {
        v196 = 0;
        v41 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a1 + 40);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v197,
          L"MemBandwidth");
        KeyInfo::GenDumpFileName(v41, &v195, v197);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v197);
        if ( !mlib::MCreateFile(*(LPCWSTR *)(v195 + 24), (const unsigned __int16 *)0x22, (unsigned int)&v196, v42) )
        {
          mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(Buffer, v196);
          SampleManager::DumpSamples(Block, v228);
          mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(Buffer);
        }
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v195);
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v205,
        L"Units");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v43, v205);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v204,
        L"name");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v44, v204);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v203,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v46, v203);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"B/s");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v202,
        L"descrip");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v48, v202);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v49, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes per second");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v201,
        L"Units");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v52, v201);
        v51 = v53;
        v50 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_43;
        v50 = L"/>";
        v51 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, v50);
LABEL_43:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v200,
        L"Units");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v54, v200);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v199,
        L"name");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v55, v199);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v56, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v198,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v57, v198);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v58, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v215,
        L"descrip");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v59, v215);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v60, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v214,
        L"Units");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v63, v214);
        v62 = v64;
        v61 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_52;
        v61 = L"/>";
        v62 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, v61);
LABEL_52:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v213,
        L"NumProcessors");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v65, v213);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v66 = *(_DWORD *)(a1 + 64);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v66);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v212,
        L"NumProcessors");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v69, v212);
        v68 = v70;
        v67 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_61;
        v67 = L"/>";
        v68 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v68, v67);
LABEL_61:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v211,
        L"NumThreads");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v71, v211);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      v72 = *(_DWORD *)(a1 + 68);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v72);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v210,
        L"NumThreads");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v75, v210);
        v74 = v76;
        v73 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_70;
        v73 = L"/>";
        v74 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, v73);
LABEL_70:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v209,
        L"PageSize");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v77, v209);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v208,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v78, v208);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v79, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v80 = *(_DWORD *)(a1 + 72);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v80);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v207,
        L"PageSize");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v83, v207);
        v82 = v84;
        v81 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_79;
        v81 = L"/>";
        v82 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, v81);
LABEL_79:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v206,
        L"MemBlockSize");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v85, v206);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v224,
        L"UnCachedMemSpace");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v86, v224);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v87, L"=");
      v88 = L"YES";
      if ( !*(_BYTE *)(a1 + 736) )
        v88 = L"NO";
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, v88);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v223,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v89, v223);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v90, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v91 = *(_DWORD *)(a1 + 708);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v91);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v222,
        L"MemBlockSize");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v94, v222);
        v93 = v95;
        v92 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_90;
        v92 = L"/>";
        v93 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v93, v92);
LABEL_90:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v221,
        L"MemDestOffset");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v96, v221);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v220,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v97, v220);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bytes");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      v99 = *(_DWORD *)(a1 + 712);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2, v99);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v219,
        L"MemDestOffset");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v102, v219);
        v101 = v103;
        v100 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_99;
        v100 = L"/>";
        v101 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, v100);
LABEL_99:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v218,
        L"TotalBytesPerSecond");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v104, v218);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v217,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v105, v217);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v106, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v107 = *a2;
      v108 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v108 + v107 + 24) |= 0x2090u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v107 + 4LL) + v107 + 40) = 6;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v109 = *a2;
      v110 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v110 + v109 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v216,
        L"TotalBytesPerSecond");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v113, v216);
        v112 = v114;
        v111 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_108;
        v111 = L"/>";
        v112 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, v111);
LABEL_108:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v195,
        L"TotalBytesPerSecondMean");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v115, &v195);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v196,
        L"units");
      *((_DWORD *)a2 + 2) = 3;
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v116, &v196);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v117, L"=");
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v118 = *a2;
      v119 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v119 + v118 + 24) |= 0x2090u;
      *(_QWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 32) = 5;
      *(_QWORD *)(*(int *)(*(_QWORD *)v118 + 4LL) + v118 + 40) = 6;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      std::basic_ostream<unsigned short>::operator<<(*a2);
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
      v120 = *a2;
      v121 = *(int *)(*(_QWORD *)*a2 + 4LL);
      *(_DWORD *)(v121 + v120 + 24) |= 0x201u;
      *(_WORD *)(*(int *)(*(_QWORD *)v120 + 4LL) + v120 + 88) = 32;
      *(_QWORD *)(*(int *)(*(_QWORD *)v120 + 4LL) + v120 + 40) = 0;
      mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v197,
        L"TotalBytesPerSecondMean");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v124, v197);
        v123 = v125;
        v122 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_117;
        v122 = L"/>";
        v123 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v123, v122);
LABEL_117:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v197);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v196);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v195);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v216);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v217);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v218);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v219);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v220);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v221);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v222);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v223);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v224);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v206);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v207);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v208);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v209);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v210);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v211);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v212);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v213);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v214);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v215);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v198);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v199);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v200);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v201);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v202);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v203);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v204);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v205);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v194,
        L"PerCPUData");
      if ( *((_DWORD *)a2 + 2) == 2 )
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
      *((_DWORD *)a2 + 2) = 2;
      mlib::XmlStream::Indent((mlib::XmlStream *)a2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v126, &v194);
      ++*((_DWORD *)a2 + 3);
      *((_BYTE *)a2 + 17) = 0;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v194);
      if ( *(_DWORD *)(a1 + 68) )
      {
        v127 = 0;
        while ( 1 )
        {
          v128 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * v127);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v209,
            L"CPUData");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v129, v209);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v210,
            L"CPUIndex");
          *((_DWORD *)a2 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v130, v210);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v127);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v211,
            L"Repetitions");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v132, v211);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          v133 = (__int64)(*(_QWORD *)(v128 + 160) - *(_QWORD *)(v128 + 152)) >> 3;
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2, v133);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v212,
            L"Repetitions");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v143, v212);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v144, L">");
          }
          else if ( *((_DWORD *)a2 + 2) == 2 )
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"/>");
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v213,
            L"Min");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v134, v213);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v214,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v135, v214);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v136, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v137 = *a2;
          v138 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v138 + v137 + 24) |= 0x2090u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v137 + 4LL) + v137 + 32) = 5;
          *(_QWORD *)(*(int *)(*(_QWORD *)v137 + 4LL) + v137 + 40) = 6;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v139 = *a2;
          v140 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v140 + v139 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v215,
            L"Min");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v145, v215);
            v142 = v146;
            v141 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_140;
            v141 = L"/>";
            v142 = *a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, v141);
LABEL_140:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v198,
            L"Max");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v147, v198);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v199,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v148, v199);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v149, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v150 = *a2;
          v151 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v151 + v150 + 24) |= 0x2090u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 32) = 5;
          *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 6;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v152 = *a2;
          v153 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v153 + v152 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v152 + 4LL) + v152 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v200,
            L"Max");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v156, v200);
            v155 = v157;
            v154 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_149;
            v154 = L"/>";
            v155 = *a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v155, v154);
LABEL_149:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v201,
            L"Median");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v158, v201);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v202,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v159, v202);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v161 = *a2;
          v162 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v162 + v161 + 24) |= 0x2090u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v161 + 4LL) + v161 + 32) = 5;
          *(_QWORD *)(*(int *)(*(_QWORD *)v161 + 4LL) + v161 + 40) = 6;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v163 = *a2;
          v164 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v164 + v163 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v163 + 4LL) + v163 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v163 + 4LL) + v163 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v203,
            L"Median");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v167, v203);
            v166 = v168;
            v165 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_158;
            v165 = L"/>";
            v166 = *a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, v165);
LABEL_158:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v204,
            L"Mean");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v169, v204);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v205,
            L"units");
          *((_DWORD *)a2 + 2) = 3;
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L" ");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v170, v205);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v171, L"=");
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"bs");
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v172 = *a2;
          v173 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v173 + v172 + 24) |= 0x2090u;
          *(_QWORD *)(*(int *)(*(_QWORD *)v172 + 4LL) + v172 + 32) = 5;
          *(_QWORD *)(*(int *)(*(_QWORD *)v172 + 4LL) + v172 + 40) = 6;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          std::basic_ostream<unsigned short>::operator<<(*a2);
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::XmlStream::BeforeText((mlib::XmlStream *)a2);
          v174 = *a2;
          v175 = *(int *)(*(_QWORD *)*a2 + 4LL);
          *(_DWORD *)(v175 + v174 + 24) |= 0x201u;
          *(_WORD *)(*(int *)(*(_QWORD *)v174 + 4LL) + v174 + 88) = 32;
          *(_QWORD *)(*(int *)(*(_QWORD *)v174 + 4LL) + v174 + 40) = 0;
          mlib::XmlStream::AfterText((mlib::XmlStream *)a2);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v194,
            L"Mean");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v178, &v194);
            v177 = v179;
            v176 = L">";
          }
          else
          {
            if ( *((_DWORD *)a2 + 2) != 2 )
              goto LABEL_167;
            v176 = L"/>";
            v177 = *a2;
          }
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v177, v176);
LABEL_167:
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v194);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v205);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v204);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v203);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v202);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v201);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v200);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v199);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v198);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v215);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v214);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v213);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v212);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v211);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v210);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v209);
          if ( !*(_BYTE *)(v128 + 336) )
            goto LABEL_178;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v207,
            L"RDTSCDeltaViolation");
          if ( *((_DWORD *)a2 + 2) == 2 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L">");
          *((_DWORD *)a2 + 2) = 2;
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"<");
          mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v180, v207);
          ++*((_DWORD *)a2 + 3);
          *((_BYTE *)a2 + 17) = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v208,
            L"RDTSCDeltaViolation");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v183, v208);
            v182 = v184;
            v181 = L">";
            goto LABEL_176;
          }
          if ( *((_DWORD *)a2 + 2) == 2 )
          {
            v181 = L"/>";
            v182 = *a2;
LABEL_176:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v182, v181);
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v208);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v207);
LABEL_178:
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v206,
            L"CPUData");
          --*((_DWORD *)a2 + 3);
          if ( *((_DWORD *)a2 + 2) == 1 )
          {
            if ( !*((_BYTE *)a2 + 17) )
              mlib::XmlStream::Indent((mlib::XmlStream *)a2);
            *((_BYTE *)a2 + 17) = 0;
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
            mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v187, v206);
            v186 = v188;
            v185 = L">";
            goto LABEL_184;
          }
          if ( *((_DWORD *)a2 + 2) == 2 )
          {
            v185 = L"/>";
            v186 = *a2;
LABEL_184:
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v186, v185);
          }
          *((_DWORD *)a2 + 2) = 1;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v206);
          if ( ++v127 >= *(_DWORD *)(a1 + 68) )
          {
            j = Block[0];
            break;
          }
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v194,
        L"PerCPUData");
      --*((_DWORD *)a2 + 3);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        if ( !*((_BYTE *)a2 + 17) )
          mlib::XmlStream::Indent((mlib::XmlStream *)a2);
        *((_BYTE *)a2 + 17) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(*a2, L"</");
        mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v191, &v194);
        v190 = v192;
        v189 = L">";
      }
      else
      {
        if ( *((_DWORD *)a2 + 2) != 2 )
          goto LABEL_194;
        v189 = L"/>";
        v190 = *a2;
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v190, v189);
LABEL_194:
      *((_DWORD *)a2 + 2) = 1;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v194);
      if ( j )
        operator delete(j);
      return v14;
    }
    if ( !GetExitCodeThread(
            *(HANDLE *)(a1 + 8LL * i + 96),
            (LPDWORD)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i) + 112LL)) )
      break;
    v17 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i);
    if ( *(_DWORD *)(v17 + 112) )
    {
      LastError = *(_DWORD *)(v17 + 112);
      v230 = 1;
      v231 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v18 = *(_QWORD *)(a1 + 24);
      v19 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x8F6, 622, i);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18 + 240, v19);
      v21 = std::basic_ostream<unsigned short>::operator<<(v20, 10);
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        v21,
        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * i) + 408LL);
      v23 = std::basic_ostream<unsigned short>::operator<<(v22, 10);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, Buffer);
      std::endl(v24);
      v15 = 0;
    }
  }
  LastError = GetLastError();
  v230 = 1;
  v231 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  v25 = *(_QWORD *)(a1 + 24);
  v27 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x8EA, 621, v26);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v25 + 240, v27);
  v29 = std::basic_ostream<unsigned short>::operator<<(v28, 10);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, Buffer);
  v31 = std::basic_ostream<unsigned short>::operator<<(v30, 10);
  std::endl(v31);
  return (unsigned int)-2147221503;
}

```

## disassembly

```asm
0x14005ccd0  mov     rax, rsp
0x14005ccd3  mov     [rax+20h], rbx
0x14005ccd7  push    rbp
0x14005ccd8  push    rsi
0x14005ccd9  push    rdi
0x14005ccda  push    r12
0x14005ccdc  push    r13
0x14005ccde  push    r14
0x14005cce0  push    r15
0x14005cce2  lea     rbp, [rax-2F8h]
0x14005cce9  sub     rsp, 3C0h
0x14005ccf0  movaps  xmmword ptr [rax-48h], xmm6
0x14005ccf4  movaps  xmmword ptr [rax-58h], xmm7
0x14005ccf8  movaps  xmmword ptr [rax-68h], xmm8
0x14005ccfd  movaps  xmmword ptr [rax-78h], xmm9
0x14005cd02  movaps  xmmword ptr [rax-88h], xmm10
0x14005cd0a  mov     rax, cs:__security_cookie
0x14005cd11  xor     rax, rsp
0x14005cd14  mov     [rbp+2F0h+var_90], rax
0x14005cd1b  mov     r12, r8
0x14005cd1e  mov     rdi, rdx
0x14005cd21  mov     rsi, rcx
0x14005cd24  lea     rdx, aTestname; "TestName"
0x14005cd2b  lea     rcx, [rsp+3F0h+var_3A8]
0x14005cd30  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005cd35  nop
0x14005cd36  cmp     dword ptr [rdi+8], 2
0x14005cd3a  jnz     short loc_14005CD4B
0x14005cd3c  lea     rdx, asc_14012B480; ">"
0x14005cd43  mov     rcx, [rdi]
0x14005cd46  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cd4b  mov     dword ptr [rdi+8], 2
0x14005cd52  mov     rcx, rdi; this
0x14005cd55  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14005cd5a  lea     rdx, asc_14012B484; "<"
0x14005cd61  mov     rcx, [rdi]
0x14005cd64  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cd69  mov     rcx, rax
0x14005cd6c  lea     rdx, [rsp+3F0h+var_3A8]
0x14005cd71  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005cd76  inc     dword ptr [rdi+0Ch]
0x14005cd79  xor     r15d, r15d
0x14005cd7c  mov     [rdi+11h], r15b
0x14005cd80  mov     [rsp+3F0h+var_3B8], r15
0x14005cd85  mov     rdx, [rsi+2D8h]
0x14005cd8c  lea     rcx, [rsp+3F0h+var_3B8]
0x14005cd91  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14005cd96  lea     rdx, [rsp+3F0h+var_3B8]
0x14005cd9b  mov     rcx, rdi
0x14005cd9e  call    ??$?6V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@XmlStream@mlib@@QEAAAEAV01@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::XmlStream::operator<<<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>)
0x14005cda3  mov     rbx, rax
0x14005cda6  lea     rdx, aTestname; "TestName"
0x14005cdad  lea     rcx, [rsp+3F0h+var_3B0]
0x14005cdb2  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005cdb7  nop
0x14005cdb8  dec     dword ptr [rbx+0Ch]
0x14005cdbb  mov     eax, [rbx+8]
0x14005cdbe  sub     eax, 1
0x14005cdc1  jz      short loc_14005CDD4
0x14005cdc3  cmp     eax, 1
0x14005cdc6  jnz     short loc_14005CE11
0x14005cdc8  lea     rdx, asc_14012B488; "/>"
0x14005cdcf  mov     rcx, [rbx]
0x14005cdd2  jmp     short loc_14005CE0C
0x14005cdd4  cmp     [rbx+11h], r15b
0x14005cdd8  jnz     short loc_14005CDE2
0x14005cdda  mov     rcx, rbx; this
0x14005cddd  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14005cde2  mov     [rbx+11h], r15b
0x14005cde6  lea     rdx, asc_14012B490; "</"
0x14005cded  mov     rcx, [rbx]
0x14005cdf0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cdf5  mov     rcx, rax
0x14005cdf8  lea     rdx, [rsp+3F0h+var_3B0]
0x14005cdfd  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005ce02  mov     rcx, rax
0x14005ce05  lea     rdx, asc_14012B480; ">"
0x14005ce0c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005ce11  mov     dword ptr [rbx+8], 1
0x14005ce18  lea     rcx, [rsp+3F0h+var_3B0]
0x14005ce1d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005ce22  nop
0x14005ce23  lea     rcx, [rsp+3F0h+var_3A8]
0x14005ce28  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005ce2d  cmp     [rsi+50h], r15
0x14005ce31  jnz     short loc_14005CE57
0x14005ce33  mov     edx, 26Ch; unsigned __int16
0x14005ce38  lea     rcx, [rbp+2F0h+Block]; this
0x14005ce3c  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x14005ce41  mov     rdx, rax
0x14005ce44  mov     rcx, r12
0x14005ce47  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x14005ce4c  mov     r14d, 80040001h
0x14005ce52  jmp     loc_14005ED31
0x14005ce57  cmp     [rsi+2E2h], r15b
0x14005ce5e  jz      short loc_14005CE67
0x14005ce60  mov     edx, 26Bh
0x14005ce65  jmp     short loc_14005CE38
0x14005ce67  mov     bl, 1
0x14005ce69  mov     r14d, r15d
0x14005ce6c  cmp     r14d, [rsi+44h]
0x14005ce70  jnb     loc_14005CFD2
0x14005ce76  mov     r15d, r14d
0x14005ce79  mov     rax, [rsi+50h]
0x14005ce7d  mov     rdx, [rax+r15*8]
0x14005ce81  add     rdx, 70h ; 'p'; lpExitCode
0x14005ce85  mov     rcx, [rsi+r15*8+60h]; hThread
0x14005ce8a  call    cs:__imp_GetExitCodeThread
0x14005ce90  xor     r13d, r13d
0x14005ce93  test    eax, eax
0x14005ce95  jz      loc_14005CF52
0x14005ce9b  mov     rax, [rsi+50h]
0x14005ce9f  mov     rcx, [rax+r15*8]
0x14005cea3  mov     eax, [rcx+70h]
0x14005cea6  test    eax, eax
0x14005cea8  jz      loc_14005CF47
0x14005ceae  mov     [rbp+2F0h+var_A0], eax
0x14005ceb4  mov     [rbp+2F0h+var_9C], 1
0x14005cebb  mov     [rbp+2F0h+var_98], r13
0x14005cec2  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x14005cec6  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005cecb  mov     rbx, [rsi+18h]
0x14005cecf  mov     r8d, 26Eh; int
0x14005ced5  mov     r9d, r14d; unsigned __int16
0x14005ced8  mov     edx, 8F6h; char *
0x14005cedd  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005cee4  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x14005cee9  mov     rdx, rax
0x14005ceec  lea     rcx, [rbx+0F0h]
0x14005cef3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cef8  mov     r13d, 0Ah
0x14005cefe  mov     edx, r13d
0x14005cf01  mov     rcx, rax
0x14005cf04  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cf09  mov     rcx, [rsi+50h]
0x14005cf0d  mov     rdx, [rcx+r15*8]
0x14005cf11  add     rdx, 198h
0x14005cf18  mov     rcx, rax
0x14005cf1b  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005cf20  mov     edx, r13d
0x14005cf23  mov     rcx, rax
0x14005cf26  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cf2b  lea     rdx, [rbp+2F0h+Buffer]
0x14005cf2f  mov     rcx, rax
0x14005cf32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cf37  mov     rcx, rax
0x14005cf3a  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005cf3f  xor     r15d, r15d
0x14005cf42  mov     bl, r15b
0x14005cf45  jmp     short loc_14005CF4A
0x14005cf47  xor     r15d, r15d
0x14005cf4a  inc     r14d
0x14005cf4d  jmp     loc_14005CE6C
0x14005cf52  call    cs:__imp_GetLastError
0x14005cf58  mov     [rbp+2F0h+var_A0], eax
0x14005cf5e  mov     [rbp+2F0h+var_9C], 1
0x14005cf65  mov     [rbp+2F0h+var_98], r13
0x14005cf6c  lea     rcx, [rbp+2F0h+Buffer]; lpBuffer
0x14005cf70  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005cf75  mov     rbx, [rsi+18h]
0x14005cf79  mov     edx, 8EAh; char *
0x14005cf7e  mov     r8d, 26Dh; int
0x14005cf84  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005cf8b  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14005cf90  mov     rdx, rax
0x14005cf93  lea     rcx, [rbx+0F0h]
0x14005cf9a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cf9f  mov     edx, 0Ah
0x14005cfa4  mov     rcx, rax
0x14005cfa7  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cfac  lea     rdx, [rbp+2F0h+Buffer]
0x14005cfb0  mov     rcx, rax
0x14005cfb3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005cfb8  mov     edx, 0Ah
0x14005cfbd  mov     rcx, rax
0x14005cfc0  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005cfc5  mov     rcx, rax
0x14005cfc8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005cfcd  jmp     loc_14005CE4C
0x14005cfd2  test    bl, bl
0x14005cfd4  jnz     short loc_14005CFE0
0x14005cfd6  mov     edx, 26Fh
0x14005cfdb  jmp     loc_14005CE38
0x14005cfe0  mov     r14d, r15d
0x14005cfe3  mov     dword ptr [rsi+38h], 6
0x14005cfea  xorps   xmm6, xmm6
0x14005cfed  xorps   xmm7, xmm7
0x14005cff0  xorps   xmm0, xmm0
0x14005cff3  movdqu  xmmword ptr [rbp+2F0h+Block], xmm0
0x14005cff8  mov     [rbp+2F0h+var_2B8], r15
0x14005cffc  mov     [rsp+3F0h+var_3C0], r15
0x14005d001  mov     edx, [rsi+44h]
0x14005d004  lea     r8, [rsp+3F0h+var_3C0]
0x14005d009  lea     rcx, [rbp+2F0h+Block]
0x14005d00d  call    ?resize@?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@QEAAX_KAEBQEBVSampleManager@@@Z; std::vector<SampleManager const *>::resize(unsigned __int64,SampleManager const * const &)
0x14005d012  mov     edx, r15d
0x14005d015  mov     r13, [rbp+2F0h+Block]
0x14005d019  mov     r12d, 1
0x14005d01f  cmp     [rsi+44h], r15d
0x14005d023  jbe     short loc_14005D04C
0x14005d025  mov     ecx, edx
0x14005d027  mov     rax, [rsi+50h]
0x14005d02b  mov     rax, [rax+rcx*8]
0x14005d02f  addsd   xmm6, qword ptr [rax+48h]
0x14005d034  addsd   xmm7, qword ptr [rax+60h]
0x14005d039  add     rax, 98h
0x14005d03f  mov     [r13+rcx*8+0], rax
0x14005d044  add     edx, r12d
0x14005d047  cmp     edx, [rsi+44h]
0x14005d04a  jb      short loc_14005D025
0x14005d04c  cmp     [rsi+21h], r15b
0x14005d050  jz      loc_14005D103
0x14005d056  mov     rcx, [rsi+10h]
0x14005d05a  mov     ebx, 0F0h
0x14005d05f  add     rcx, rbx
0x14005d062  lea     rdx, aTotalBytespers_0; "> Total BytesPerSecond        = "
0x14005d069  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005d06e  mov     rcx, [rax]
0x14005d071  movsxd  rdx, dword ptr [rcx+4]
0x14005d075  or      dword ptr [rdx+rax+18h], 2090h
0x14005d07d  mov     rcx, [rax]
0x14005d080  movsxd  rdx, dword ptr [rcx+4]
0x14005d084  mov     [rdx+rax+20h], r15
0x14005d089  mov     rcx, [rax]
0x14005d08c  movsxd  rdx, dword ptr [rcx+4]
0x14005d090  mov     qword ptr [rdx+rax+28h], 0Bh
0x14005d099  movaps  xmm1, xmm6
0x14005d09c  mov     rcx, rax
0x14005d09f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x14005d0a4  mov     rcx, rax
0x14005d0a7  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005d0ac  cmp     [rsi+20h], r15b
0x14005d0b0  jz      short loc_14005D103
0x14005d0b2  mov     rcx, [rsi+10h]
0x14005d0b6  add     rcx, rbx
0x14005d0b9  lea     rdx, aTotalBytespers; "> Total BytesPerSecond (mean) = "
0x14005d0c0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005d0c5  mov     rcx, [rax]
0x14005d0c8  movsxd  rdx, dword ptr [rcx+4]
0x14005d0cc  or      dword ptr [rdx+rax+18h], 2090h
0x14005d0d4  mov     rcx, [rax]
0x14005d0d7  movsxd  rdx, dword ptr [rcx+4]
0x14005d0db  mov     [rdx+rax+20h], r15
0x14005d0e0  mov     rcx, [rax]
0x14005d0e3  movsxd  rdx, dword ptr [rcx+4]
0x14005d0e7  mov     qword ptr [rdx+rax+28h], 0Bh
0x14005d0f0  movaps  xmm1, xmm7
0x14005d0f3  mov     rcx, rax
0x14005d0f6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@N@Z; std::basic_ostream<ushort>::operator<<(double)
0x14005d0fb  mov     rcx, rax
0x14005d0fe  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005d103  lea     rcx, [rsi+28h]
0x14005d107  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005d10c  cmp     [rax+1F2h], r15w
0x14005d114  jz      loc_14005D1AA
0x14005d11a  mov     [rsp+3F0h+var_3B0], r15
0x14005d11f  lea     rcx, [rsi+28h]
0x14005d123  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005d128  mov     rbx, rax
0x14005d12b  lea     rdx, aMembandwidth; "MemBandwidth"
0x14005d132  lea     rcx, [rsp+3F0h+var_3A8]
0x14005d137  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005d13c  nop
0x14005d13d  lea     r8, [rsp+3F0h+var_3A8]
0x14005d142  lea     rdx, [rsp+3F0h+var_3B8]
0x14005d147  mov     rcx, rbx
0x14005d14a  call    ?GenDumpFileName@KeyInfo@@QEBA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBV23@@Z; KeyInfo::GenDumpFileName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005d14f  nop
0x14005d150  lea     rcx, [rsp+3F0h+var_3A8]
0x14005d155  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005d15a  lea     r8, [rsp+3F0h+var_3B0]; unsigned int
0x14005d15f  mov     edx, 22h ; '"'; unsigned __int16 *
0x14005d164  mov     rcx, [rsp+3F0h+var_3B8]
0x14005d169  mov     rcx, [rcx+18h]; lpFileName
0x14005d16d  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x14005d172  test    eax, eax
0x14005d174  jnz     short loc_14005D1A0
0x14005d176  mov     rdx, [rsp+3F0h+var_3B0]
0x14005d17b  lea     rcx, [rbp+2F0h+Buffer]
0x14005d17f  call    ??0?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAA@PEAX_N_K@Z; mlib::handle_ostreamT<char,std::char_traits<char>>::handle_ostreamT<char,std::char_traits<char>>(void *,bool,unsigned __int64)
0x14005d184  nop
0x14005d185  lea     rdx, [rbp+2F0h+var_1B0]
0x14005d18c  lea     rcx, [rbp+2F0h+Block]
0x14005d190  call    ?DumpSamples@SampleManager@@SAXAEAV?$vector@PEBVSampleManager@@V?$allocator@PEBVSampleManager@@@std@@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@3@@Z; SampleManager::DumpSamples(std::vector<SampleManager const *> &,std::ostream &)
0x14005d195  nop
0x14005d196  lea     rcx, [rbp+2F0h+Buffer]
0x14005d19a  call    ??_D?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@QEAAXXZ; mlib::handle_ostreamT<char,std::char_traits<char>>::`vbase destructor'(void)
0x14005d19f  nop
0x14005d1a0  lea     rcx, [rsp+3F0h+var_3B8]
0x14005d1a5  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005d1aa  lea     rdx, aUnits; "Units"
0x14005d1b1  lea     rcx, [rbp+2F0h+var_368]
0x14005d1b5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14005d1ba  nop
0x14005d1bb  lea     rbx, asc_14012B480; ">"
0x14005d1c2  cmp     dword ptr [rdi+8], 2
0x14005d1c6  jnz     short loc_14005D1D3
0x14005d1c8  mov     rdx, rbx
0x14005d1cb  mov     rcx, [rdi]
0x14005d1ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
  ... truncated ...
```
