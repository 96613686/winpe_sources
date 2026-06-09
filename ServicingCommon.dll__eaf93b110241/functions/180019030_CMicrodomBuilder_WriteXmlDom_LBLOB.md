# CMicrodomBuilder::WriteXmlDom(_LBLOB *)

- ea: `0x180019030`
- end: `0x18001a348`
- name: `?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z`
- size: `4888`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800152ec`

## callees

- `0x1800031e0`
- `0x18000d95c`
- `0x18000fd04`
- `0x180019030`
- `0x18001e850`
- `0x18001ece4`
- `0x18001eda0`
- `0x18001fa28`
- `0x18001fd10`
- `0x18001fd90`
- `0x18001fdc8`
- `0x180020584`
- `0x180022eb0`
- `0x180022f08`
- `0x1800293a0`
- `0x18009a700`
- `0x1800a0020`

## string_xrefs

- `0x1800194cc`: `onecore\base\xml\udom_builder.cpp`
- `0x180019773`: `onecore\base\xml\udom_builder.cpp`
- `0x180019b5f`: `onecore\base\xml\udom_builder.cpp`
- `0x180019b80`: `onecore\base\xml\udom_builder.cpp`
- `0x18001a125`: `onecore\base\xml\udom_builder.cpp`
- `0x18001a170`: `onecore\base\xml\udom_builder.cpp`
- `0x18001a284`: `onecore\base\xml\udom_builder.cpp`
- `0x18001a0fa`: `CMicrodomBuilder::WriteXmlDom`
- `0x18001a29e`: `CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::WriteXmlDom(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  __int64 v2; // rax
  __int64 v4; // r13
  __int64 v5; // rax
  signed int v6; // ebx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r15
  __int64 v11; // r12
  unsigned __int64 v12; // rsi
  __int64 **v13; // rdi
  __int64 **i; // rbx
  int *v15; // rbx
  unsigned __int64 v16; // r9
  __int64 **v17; // rdx
  __int64 **j; // r8
  int *v19; // r8
  __int64 v20; // r11
  _DWORD *v21; // rcx
  CMicrodomBuilder *v22; // r14
  unsigned int v23; // eax
  __int64 (__fastcall *v24)(); // rsi
  __int64 **v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  _QWORD *v28; // rdx
  _QWORD *v29; // rax
  __int64 *v30; // r15
  int v31; // r12d
  unsigned __int64 v32; // r10
  int v33; // r13d
  unsigned __int64 v34; // r15
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // r14
  unsigned __int64 v37; // r12
  unsigned __int64 k; // rsi
  _QWORD *v39; // rdi
  _QWORD *v40; // rdx
  _QWORD *v41; // rbx
  __int64 v42; // rdi
  _BYTE *v43; // rsi
  char *m; // rbx
  bool v45; // cf
  char v46; // al
  int v47; // r14d
  int v48; // esi
  unsigned __int64 v49; // r8
  __int64 **v50; // rdx
  __int64 *v51; // rax
  _DWORD *v52; // rcx
  unsigned __int64 v53; // rdi
  __int16 *v54; // rax
  __int16 v55; // ax
  int v56; // r12d
  unsigned __int64 v57; // rbx
  unsigned __int64 v58; // rcx
  __int16 v59; // ax
  unsigned __int64 v60; // rdi
  unsigned int v61; // edi
  int v62; // esi
  unsigned __int64 v63; // r14
  __int64 **v64; // rbx
  __int64 *v65; // rax
  size_t v66; // rcx
  char v67; // r12
  char *v68; // rax
  unsigned __int64 v69; // rsi
  size_t v70; // rdx
  unsigned __int64 v71; // rax
  __int64 v72; // r15
  __int64 v73; // rdx
  unsigned __int64 v74; // rcx
  __int64 v75; // rax
  size_t v76; // rax
  unsigned __int64 *v77; // rax
  _BYTE *v78; // r14
  char *v79; // rdi
  unsigned __int64 n; // rbx
  __int64 v81; // r10
  _QWORD *v82; // r9
  _QWORD *v83; // rcx
  _BYTE *v84; // r8
  int v85; // r8d
  int v86; // r9d
  __int64 **v87; // rdx
  __int64 *ii; // rax
  __int64 *v89; // rax
  int v90; // eax
  unsigned int v91; // edi
  int v92; // esi
  unsigned __int64 v93; // r14
  __int64 **v94; // rbx
  __int64 *v95; // rax
  char v96; // r12
  char *v97; // rax
  unsigned __int64 v98; // rsi
  size_t v99; // rcx
  unsigned __int64 v100; // rax
  __int64 v101; // r15
  __int64 v102; // rdx
  unsigned __int64 v103; // rcx
  __int64 v104; // rax
  size_t v105; // rax
  unsigned __int64 *v106; // rax
  bool v107; // r8
  _BYTE *v108; // r14
  char *v109; // rdi
  unsigned __int64 jj; // rbx
  __int64 v111; // rbx
  BUCL::CDequeBase *v112; // r11
  __int64 v113; // r10
  _BYTE *v114; // rcx
  int v115; // ecx
  _QWORD *v116; // rcx
  struct _LBLOB *v118; // rax
  unsigned __int64 v119; // r10
  int v120; // [rsp+30h] [rbp-D0h]
  int v121; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v122; // [rsp+48h] [rbp-B8h]
  __int64 *v123; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v124; // [rsp+58h] [rbp-A8h]
  int v125; // [rsp+60h] [rbp-A0h]
  __int64 v126; // [rsp+68h] [rbp-98h]
  __int64 **v127; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v128)(); // [rsp+78h] [rbp-88h]
  int v129; // [rsp+80h] [rbp-80h]
  int v130; // [rsp+84h] [rbp-7Ch]
  int v131; // [rsp+88h] [rbp-78h]
  CMicrodomBuilder *v132; // [rsp+90h] [rbp-70h]
  int v133; // [rsp+98h] [rbp-68h] BYREF
  __int64 v134; // [rsp+A0h] [rbp-60h] BYREF
  int v135; // [rsp+A8h] [rbp-58h]
  int v136; // [rsp+ACh] [rbp-54h]
  struct _LBLOB *v137; // [rsp+B0h] [rbp-50h]
  _QWORD v138[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v139[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v140[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v141[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v142[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v143[4]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v144; // [rsp+178h] [rbp+78h] BYREF
  __int64 v145; // [rsp+180h] [rbp+80h] BYREF
  char v146[8]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE *v147; // [rsp+198h] [rbp+98h]
  __int64 v148; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v149; // [rsp+1A8h] [rbp+A8h]
  size_t Size; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v151; // [rsp+1B8h] [rbp+B8h]
  _BYTE v152[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v153[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v154[32]; // [rsp+200h] [rbp+100h] BYREF
  char v155[32]; // [rsp+220h] [rbp+120h] BYREF
  char v156[32]; // [rsp+240h] [rbp+140h] BYREF
  char v157[32]; // [rsp+260h] [rbp+160h] BYREF
  char v158[48]; // [rsp+280h] [rbp+180h] BYREF
  char v159[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE *v160; // [rsp+2B8h] [rbp+1B8h]
  __int64 v161; // [rsp+2C0h] [rbp+1C0h]
  unsigned __int64 v162; // [rsp+2C8h] [rbp+1C8h]
  size_t v163; // [rsp+2D0h] [rbp+1D0h]
  size_t v164; // [rsp+2D8h] [rbp+1D8h]
  _BYTE v165[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v166[32]; // [rsp+300h] [rbp+200h] BYREF
  char v167[32]; // [rsp+320h] [rbp+220h] BYREF
  char v168[32]; // [rsp+340h] [rbp+240h] BYREF
  char v169[32]; // [rsp+360h] [rbp+260h] BYREF
  char v170[32]; // [rsp+380h] [rbp+280h] BYREF
  char v171[48]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v172[8]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE *v173; // [rsp+3D8h] [rbp+2D8h]
  __int64 v174; // [rsp+3E0h] [rbp+2E0h]
  unsigned __int64 v175; // [rsp+3E8h] [rbp+2E8h]
  __m128i si128; // [rsp+3F0h] [rbp+2F0h]
  _BYTE v177[32]; // [rsp+400h] [rbp+300h] BYREF
  char v178[32]; // [rsp+420h] [rbp+320h] BYREF
  char v179[32]; // [rsp+440h] [rbp+340h] BYREF
  char v180[32]; // [rsp+460h] [rbp+360h] BYREF
  char v181[32]; // [rsp+480h] [rbp+380h] BYREF
  char v182[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  char v183[48]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v2 = *((_QWORD *)a2 + 1);
  v4 = *((_QWORD *)a2 + 2);
  v132 = this;
  v145 = v2;
  v5 = *(_QWORD *)a2;
  v160 = v165;
  v144 = v5;
  v137 = a2;
  v161 = 0;
  v162 = 7;
  v163 = 0;
  v164 = 35;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v165);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v166);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v167);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v168);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v169);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v170);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v171);
  v148 = 0;
  v147 = v152;
  v149 = 7;
  Size = 0;
  v151 = 35;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v152);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v153);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v154);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v155);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v156);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v157);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v158);
  v173 = v177;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v174 = 0;
  v175 = 7;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v177);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v178);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v179);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v180);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v181);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v182);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v183);
  v6 = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v159);
  if ( v6 < 0 )
    goto LABEL_231;
  v6 = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v146);
  if ( v6 < 0 )
    goto LABEL_231;
  if ( v173 != v177 )
  {
    __debugbreak();
    v6 = -1073741595;
    goto LABEL_230;
  }
  v7 = HIDWORD(v175);
  if ( HIDWORD(v175) )
  {
    if ( ((5 * v7) & 0xFFFFFFFF00000000uLL) != 0 )
    {
      v6 = -1073741675;
      si128.m128i_i64[1] = -1;
      goto LABEL_230;
    }
    v8 = 5LL * (unsigned int)v175;
    si128.m128i_i64[1] = 0x500000000LL * v7 + v8;
    v6 = si128.m128i_i64[1] < v8 ? 0xC0000095 : 0;
    if ( si128.m128i_i64[1] < v8 )
    {
LABEL_230:
      v143[2] = 178;
      v143[0] = "onecore\\base\\xml\\udom_builder.cpp";
      v143[1] = "CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize";
      v143[3] = "m_StoredTable.Initialize()";
      RtlReportErrorOrigination(v143, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v6);
LABEL_231:
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v172);
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v146);
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v159);
      return (unsigned int)v6;
    }
  }
  else
  {
    si128.m128i_i64[1] = 5LL * (unsigned int)v175;
  }
  v129 = -1;
  v9 = MurmurHash3_x64_64("http://www.w3.org/2000/09/xmldsig#", 0x22u, 0x22u);
  v10 = *((_QWORD *)this + 4);
  v11 = *((_QWORD *)this + 2);
  v12 = v9;
  v13 = (__int64 **)(v11 + 32 * (v9 % v10));
  for ( i = (__int64 **)*v13; i && i != v13; i = (__int64 **)*i )
  {
    if ( i[4] == (__int64 *)v12 && i[5] == (__int64 *)34 && !memcmp("http://www.w3.org/2000/09/xmldsig#", i[7], 0x22u) )
    {
      v15 = (int *)(i + 8);
      if ( v15 )
        v129 = *v15;
      break;
    }
  }
  v131 = -1;
  v16 = MurmurHash3_x64_64("Id", 2u, 2u);
  v17 = (__int64 **)(v11 + 32 * (v16 % v10));
  for ( j = (__int64 **)*v17; j && j != v17; j = (__int64 **)*j )
  {
    if ( j[4] == (__int64 *)v16 && j[5] == (__int64 *)2 && *(_WORD *)"Id" == *(_WORD *)j[7] )
    {
      v19 = (int *)(j + 8);
      if ( v19 )
        v131 = *v19;
      break;
    }
  }
  v20 = v4 + v145;
  v21 = (_DWORD *)(v4 + v144);
  v126 = v4 + v145;
  if ( (unsigned __int64)(v145 - v144) < 0x14 )
    goto LABEL_233;
  v22 = v132;
  *v21 = 1816421453;
  v21[2] = *((_DWORD *)v22 + 324);
  v23 = *((_DWORD *)v22 + 324);
  if ( v23 > 0xFF )
  {
    if ( v23 > 0xFFFF )
    {
      v21[1] = 3;
      v24 = CMicrodomBuilder::WriteDomElementIndicies<unsigned long>;
    }
    else
    {
      v21[1] = 2;
      v24 = CMicrodomBuilder::WriteDomElementIndicies<unsigned short>;
    }
  }
  else
  {
    v21[1] = 1;
    v24 = CMicrodomBuilder::WriteDomElementIndicies<unsigned char>;
  }
  v25 = (__int64 **)((char *)v22 + 1264);
  v128 = v24;
  v26 = *((_QWORD *)v22 + 158);
  v127 = (__int64 **)((char *)v22 + 1264);
  if ( (CMicrodomBuilder *)v26 == (CMicrodomBuilder *)((char *)v22 + 1264)
    || !v26
    || *(_WORD *)(v26 + 114) != 14
    || (v27 = *(_DWORD *)(v26 + 72),
        v28 = (_QWORD *)(v26 + 88),
        v21[4] = v27,
        v29 = (_QWORD *)*v28,
        (_QWORD *)*v28 == v28) )
  {
LABEL_233:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  while ( *((_WORD *)v29 + 33) )
  {
    v29 = (_QWORD *)*v29;
    if ( v29 == v28 )
      goto LABEL_233;
  }
  v21[3] = *((_DWORD *)v29 + 6);
  v30 = *v25;
  v31 = 0;
  v125 = -1;
  v32 = ((unsigned __int64)v21 + 23) & 0xFFFFFFFFFFFFFFFCuLL;
  v121 = 0;
  v122 = v32;
  v33 = -1;
  v130 = -1;
  while ( 2 )
  {
    v123 = v30;
    if ( !v30 || v30 == (__int64 *)v25 )
    {
      v118 = v137;
      v119 = v32 - *((_QWORD *)v137 + 2);
      *(_QWORD *)v137 = v119;
      if ( v119 <= *((_QWORD *)v118 + 1) )
      {
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v172);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v146);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v159);
        return 0;
      }
      goto LABEL_233;
    }
    switch ( *((_WORD *)v30 + 57) )
    {
      case 0:
        v34 = *((unsigned int *)v30 + 19);
        v35 = (unsigned int)v34;
        v144 = 0;
        v36 = v123[13] - v34;
        v37 = v36;
        if ( v34 >= v36 )
        {
          v35 = v123[13] - v34;
          v37 = v34;
        }
        if ( v35 )
          v37 |= v35 << 22;
        for ( k = 0; k < v149; v39[3] = 0 )
        {
          v39 = &v147[32 * k];
          v40 = (_QWORD *)*v39;
          if ( *v39 && v40 != v39 )
          {
            do
            {
              v41 = (_QWORD *)*v40;
              BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeallocateBucket(v146);
              v40 = v41;
            }
            while ( v41 != v39 );
          }
          ++k;
          *v39 = v39;
          v39[1] = v39;
          v39[2] = v39;
        }
        if ( v147 != v152 )
        {
          if ( v147 )
          {
            v42 = *((_QWORD *)v147 - 1);
            v43 = v147 - 8;
            for ( m = &v147[32 * v42]; v42; --v42 )
            {
              m -= 32;
              BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::~CBucketChain(m);
            }
            operator delete(v43);
          }
          v149 = 7;
          v147 = v152;
        }
        v45 = v34 < v36;
        v30 = v123;
        v46 = 1;
        Size = 0;
        if ( v45 )
          v46 = -127;
        *(_BYTE *)v122 = v46;
        v33 = *((_DWORD *)v30 + 29);
        *(_DWORD *)(v122 + 12) = v33;
        v47 = *((_DWORD *)v30 + 30);
        *(_DWORD *)(v122 + 16) = v47;
        v48 = *((_DWORD *)v30 + 31);
        *(_DWORD *)(v122 + 20) = v48;
        v130 = v47;
        v125 = v48;
        v49 = (unsigned int)(8261505 * v48 + 780587199 * v33 - 65600);
        v50 = (__int64 **)&v160[32 * (v49 % v162)];
        v51 = *v50;
        while ( 2 )
        {
          if ( !v51 || v51 == (__int64 *)v50 )
          {
            v52 = (_DWORD *)((v122 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
            v53 = (unsigned __int64)v52;
          }
          else
          {
            if ( __PAIR64__(v33, v49) != v51[4]
              || v48 != *((_DWORD *)v51 + 10)
              || *((_DWORD *)v51 + 11) != -1
              || *((_DWORD *)v51 + 12) != -1 )
            {
              v51 = (__int64 *)*v51;
              continue;
            }
            v52 = (_DWORD *)((v122 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
            v53 = (unsigned __int64)v52;
            v54 = (__int16 *)v51 + 26;
            if ( v54 )
            {
              v55 = *v54;
              goto LABEL_73;
            }
          }
          break;
        }
        v55 = -1;
LABEL_73:
        *(_WORD *)(v122 + 8) = v55;
        if ( v37 >= 0x400000 )
        {
          if ( (unsigned __int64)(v126 - (_QWORD)v52) < 4 )
          {
            INTERNAL_ERROR_ACTION(-1073741595);
            __debugbreak();
          }
          *v52 = v37 & 0x3FFFFF;
          v56 = *(_DWORD *)(v122 + 4) ^ (v37 >> 22);
          *(_BYTE *)(v122 + 1) |= 1u;
          *(_DWORD *)(v122 + 4) ^= v56 & 0x3FFFFF;
          v53 = ((unsigned __int64)v52 + 7) & 0xFFFFFFFFFFFFFFFCuLL;
        }
        else
        {
          *(_DWORD *)(v122 + 4) ^= (*(_DWORD *)(v122 + 4) ^ v37) & 0x3FFFFF;
          *(_BYTE *)(v122 + 1) &= ~1u;
        }
        v22 = v132;
        v24 = v128;
        LODWORD(v57) = ((__int64 (__fastcall *)(CMicrodomBuilder *, unsigned __int64, __int64 *, __int64 *))v128)(
                         v132,
                         v53,
                         &v144,
                         v30);
        if ( (v57 & 0x80000000) != 0LL )
          goto LABEL_226;
        v32 = (v53 + v144 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        goto LABEL_79;
      case 1:
        if ( v20 - v32 < 0x14 )
          goto LABEL_233;
        v61 = *((_DWORD *)v30 + 30);
        v62 = *((_DWORD *)v30 + 31);
        v63 = 8261505 * v62 + 780587199 * v61 - 65600;
        v64 = (__int64 **)&v147[32 * (v63 % v149)];
        v65 = *v64;
        while ( 2 )
        {
          if ( !v65 || v65 == (__int64 *)v64 )
          {
            v68 = (char *)operator new(0x38u);
            if ( !v68 )
            {
              LODWORD(v57) = -1073741801;
LABEL_143:
              v138[2] = 209;
              v138[1] = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
              v138[0] = "onecore\\base\\xml\\udom_builder.cpp";
              v138[3] = "m_StoredTable.FindOrInsertIfNotPresent(p, (USHORT)0, 0, &fExisted)";
              RtlReportErrorOrigination(v138, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v57);
              goto LABEL_226;
            }
            *((_DWORD *)v68 + 8) = v63;
            *((_QWORD *)v68 + 2) = 0;
            *(_QWORD *)v68 = 0;
            *((_QWORD *)v68 + 1) = 0;
            *((_QWORD *)v68 + 3) = v146;
            *((_DWORD *)v68 + 9) = v61;
            *((_DWORD *)v68 + 10) = v62;
            *(_QWORD *)(v68 + 44) = -1;
            *((_WORD *)v68 + 26) = 0;
            *((_QWORD *)v68 + 1) = v64[1];
            *(_QWORD *)v68 = v64;
            *v64[1] = (__int64)v68;
            v64[1] = (__int64 *)v68;
            *((_QWORD *)v68 + 2) = v64;
            v64[3] = (__int64 *)((char *)v64[3] + 1);
            v66 = ++Size;
            v67 = 0;
          }
          else
          {
            if ( __PAIR64__(v61, v63) != v65[4]
              || v62 != *((_DWORD *)v65 + 10)
              || *((_DWORD *)v65 + 11) != -1
              || *((_DWORD *)v65 + 12) != -1 )
            {
              v65 = (__int64 *)*v65;
              continue;
            }
            v66 = Size;
            v67 = 1;
          }
          break;
        }
        if ( v66 <= v151 )
          goto LABEL_140;
        if ( v66 == -1 )
        {
          v69 = -1;
        }
        else if ( HIDWORD(v66) )
        {
          if ( ((2 * HIDWORD(v66)) & 0xFFFFFFFF00000000uLL) != 0 )
          {
            LODWORD(v57) = -1073741675;
            goto LABEL_139;
          }
          v70 = HIDWORD(v66) << 33;
          v71 = 2LL * (unsigned int)v66;
          v69 = v70 + v71;
          LODWORD(v57) = v70 + v71 < v71 ? 0xC0000095 : 0;
          if ( v70 + v71 < v71 )
            goto LABEL_139;
        }
        else
        {
          v69 = 2LL * (unsigned int)v66;
        }
        if ( v69 == v66 )
          goto LABEL_140;
        if ( HIDWORD(v69) )
        {
          if ( ((5 * HIDWORD(v69)) & 0xFFFFFFFF00000000uLL) != 0 )
          {
            LODWORD(v57) = -1073741675;
            goto LABEL_139;
          }
          v73 = 0x500000000LL * HIDWORD(v69);
          v74 = 5LL * (unsigned int)v69;
          v72 = v73 + v74;
          LODWORD(v57) = v73 + v74 < v74 ? 0xC0000095 : 0;
          if ( v73 + v74 < v74 )
            goto LABEL_139;
        }
        else
        {
          v72 = 5LL * (unsigned int)v69;
        }
        v75 = 32 * v69;
        if ( !is_mul_ok(v69, 0x20u) )
          v75 = -1;
        v45 = __CFADD__(v75, 8);
        v76 = v75 + 8;
        if ( v45 )
          v76 = -1;
        v77 = (unsigned __int64 *)operator new(v76);
        if ( v77 )
        {
          *v77 = v69;
          v78 = v77 + 1;
          v79 = (char *)(v77 + 1);
          for ( n = v69; n; --n )
          {
            BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v79);
            v79 += 32;
          }
          if ( v78 )
          {
            v81 = 0;
            if ( v149 )
            {
              do
              {
                v82 = &v147[32 * v81];
                while ( 1 )
                {
                  v83 = (_QWORD *)*v82;
                  if ( (_QWORD *)*v82 == v82 )
                    break;
                  if ( v83 && (_QWORD *)v83[2] == v82 )
                  {
                    *(_QWORD *)(*v83 + 8LL) = v83[1];
                    *(_QWORD *)v83[1] = *v83;
                    v83[2] = 0;
                    --v82[3];
                  }
                  v84 = &v78[32 * (*((unsigned int *)v83 + 8) % v69)];
                  v83[1] = *((_QWORD *)v84 + 1);
                  *v83 = v84;
                  **((_QWORD **)v84 + 1) = v83;
                  *((_QWORD *)v84 + 1) = v83;
                  v83[2] = v84;
                  ++*((_QWORD *)v84 + 3);
                }
                ++v81;
              }
              while ( v81 != v149 );
            }
            if ( v152 != v147 )
              BUCL::Rtl::HashTable::CTableTraits<CMicrodomBuilder::FourStringIdPair,_MICRODOM_XML_ATTDEF const *,unsigned long,CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeleteArray<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucketChain>();
            v147 = v78;
            v149 = v69;
            v151 = v72;
            goto LABEL_140;
          }
        }
        LODWORD(v57) = -1073741801;
LABEL_139:
        if ( (v57 & 0x80000000) != 0LL )
          goto LABEL_143;
LABEL_140:
        if ( v67 )
        {
          v140[2] = 211;
          v140[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v140[1] = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
          v140[3] = "!fExisted";
          RtlReportErrorOrigination(v140, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221266563LL);
          LODWORD(v57) = -1073700733;
          goto LABEL_226;
        }
        v30 = v123;
        *(_BYTE *)v122 = 2;
        *(_DWORD *)(v122 + 12) = *((_DWORD *)v30 + 31);
        *(_DWORD *)(v122 + 8) = *((_DWORD *)v30 + 30);
        *(_DWORD *)(v122 + 4) = *((_DWORD *)v30 + 29);
        *(_DWORD *)(v122 + 16) = *((_DWORD *)v30 + 32);
        if ( !*((_BYTE *)v30 + 132) )
          *(_BYTE *)v122 = 34;
        v85 = *((_DWORD *)v30 + 29);
        v86 = *((_DWORD *)v30 + 31);
        v87 = (__int64 **)&v173[32 * ((unsigned int)(780587199 * v33 + v86 + 65599 * v85 + 8261505 * v125) % v175)];
        for ( ii = *v87; ii && ii != (__int64 *)v87; ii = (__int64 *)*ii )
        {
          if ( *((_DWORD *)ii + 8) == 780587199 * v33 + v86 + 65599 * v85 + 8261505 * v125
            && v33 == *((_DWORD *)ii + 9)
            && v125 == *((_DWORD *)ii + 10)
            && v85 == *((_DWORD *)ii + 11)
            && v86 == *((_DWORD *)ii + 12) )
          {
            v89 = ii + 7;
            if ( v89 && *(_DWORD *)(*v89 + 12) == 1 )
              *(_BYTE *)v122 |= 0x10u;
            break;
          }
        }
        v90 = *(_DWORD *)(v122 + 8);
        if ( (v90 == v129 || v90 == -1 && v130 == v129) && *(_DWORD *)(v122 + 12) == v131 )
          *(_BYTE *)v122 |= 0x10u;
        v31 = v121;
        v24 = v128;
        v32 = (v122 + 23) & 0xFFFFFFFFFFFFFFFCuLL;
        v22 = v132;
        v122 = v32;
        goto LABEL_80;
      case 2:
      case 3:
        v30 = (__int64 *)*v30;
        v33 = -1;
        v125 = -1;
        continue;
      case 4:
        if ( v20 - v32 < 8 )
          goto LABEL_233;
        *(_BYTE *)v32 = 3;
        *(_DWORD *)(v32 + 4) = *((_DWORD *)v30 + 29);
        v30 = (__int64 *)*v30;
        v32 = (v32 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        continue;
      case 5:
        if ( v20 - v32 < 8 )
          goto LABEL_233;
        *(_BYTE *)v32 = 19;
        *(_DWORD *)(v32 + 4) = *((_DWORD *)v30 + 29);
        v30 = (__int64 *)*v30;
        v32 = (v32 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        continue;
      case 7:
        v30 = (__int64 *)*v30;
        LOWORD(v31) = v31 + 1;
        v121 = v31;
        continue;
      case 8:
        v91 = *((_DWORD *)v30 + 29);
        v92 = *((_DWORD *)v30 + 30);
        v93 = 8261505 * v92 + 780587199 * v91 - 65600;
        v94 = (__int64 **)&v160[32 * (v93 % v162)];
        v95 = *v94;
        while ( 2 )
        {
          if ( v95 && v95 != (__int64 *)v94 )
          {
            if ( __PAIR64__(v91, v93) != v95[4]
              || v92 != *((_DWORD *)v95 + 10)
              || *((_DWORD *)v95 + 11) != -1
              || *((_DWORD *)v95 + 12) != -1 )
            {
              v95 = (__int64 *)*v95;
              continue;
            }
            v96 = 1;
            goto LABEL_184;
          }
          break;
        }
        v97 = (char *)operator new(0x38u);
        if ( v97 )
        {
          *((_DWORD *)v97 + 8) = v93;
          *((_QWORD *)v97 + 2) = 0;
          *(_QWORD *)v97 = 0;
          *((_QWORD *)v97 + 1) = 0;
          *((_QWORD *)v97 + 3) = v159;
          *((_WORD *)v97 + 26) = v31;
          *((_DWORD *)v97 + 9) = v91;
          *((_DWORD *)v97 + 10) = v92;
          *(_QWORD *)(v97 + 44) = -1;
          *((_QWORD *)v97 + 1) = v94[1];
          *(_QWORD *)v97 = v94;
          *v94[1] = (__int64)v97;
          v94[1] = (__int64 *)v97;
          *((_QWORD *)v97 + 2) = v94;
          v94[3] = (__int64 *)((char *)v94[3] + 1);
          ++v163;
          v96 = 0;
LABEL_184:
          if ( v163 > v164 )
          {
            if ( v163 == -1 )
            {
              v98 = -1;
            }
            else if ( HIDWORD(v163) )
            {
              if ( ((2 * HIDWORD(v163)) & 0xFFFFFFFF00000000uLL) != 0 )
                goto LABEL_213;
              v99 = HIDWORD(v163) << 33;
              v100 = 2LL * (unsigned int)v163;
              v98 = v99 + v100;
              LODWORD(v57) = v99 + v100 < v100 ? 0xC0000095 : 0;
              if ( v99 + v100 < v100 )
                goto LABEL_214;
            }
            else
            {
              v98 = 2LL * (unsigned int)v163;
            }
            if ( v98 != v163 )
            {
              if ( HIDWORD(v98) )
              {
                if ( ((5 * HIDWORD(v98)) & 0xFFFFFFFF00000000uLL) != 0 )
                {
LABEL_213:
                  LODWORD(v57) = -1073741675;
LABEL_214:
                  if ( (v57 & 0x80000000) != 0LL )
                    goto LABEL_223;
                  goto LABEL_215;
                }
                v102 = 0x500000000LL * HIDWORD(v98);
                v103 = 5LL * (unsigned int)v98;
                v101 = v102 + v103;
                LODWORD(v57) = v102 + v103 < v103 ? 0xC0000095 : 0;
                if ( v102 + v103 < v103 )
                  goto LABEL_214;
              }
              else
              {
                v101 = 5LL * (unsigned int)v98;
              }
              v104 = 32 * v98;
              if ( !is_mul_ok(v98, 0x20u) )
                v104 = -1;
              v45 = __CFADD__(v104, 8);
              v105 = v104 + 8;
              if ( v45 )
                v105 = -1;
              v106 = (unsigned __int64 *)operator new(v105);
              if ( !v106 )
                goto LABEL_212;
              *v106 = v98;
              v108 = v106 + 1;
              v109 = (char *)(v106 + 1);
              for ( jj = v98; jj; --jj )
              {
                BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v109);
                v109 += 32;
              }
              if ( !v108 )
              {
LABEL_212:
                LODWORD(v57) = -1073741801;
                goto LABEL_214;
              }
              v111 = 0;
              if ( v162 )
              {
                do
                {
                  v112 = (BUCL::CDequeBase *)&v160[32 * v111];
                  while ( *(BUCL::CDequeBase **)v112 != v112 )
                  {
                    BUCL::CDequeBase::Remove(v112, *(struct BUCL::CDequeLinkage **)v112, v107);
                    v114 = &v108[32 * (*(unsigned int *)(v113 + 32) % v98)];
                    *(_QWORD *)(v113 + 8) = *((_QWORD *)v114 + 1);
                    *(_QWORD *)v113 = v114;
                    **((_QWORD **)v114 + 1) = v113;
                    *((_QWORD *)v114 + 1) = v113;
                    *(_QWORD *)(v113 + 16) = v114;
                    ++*((_QWORD *)v114 + 3);
                  }
                  ++v111;
                }
                while ( v111 != v162 );
              }
              if ( v165 != v160 )
                BUCL::Rtl::HashTable::CTableTraits<CMicrodomBuilder::FourStringIdPair,_MICRODOM_XML_ATTDEF const *,unsigned long,CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeleteArray<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucketChain>();
              v160 = v108;
              v162 = v98;
              v164 = v101;
            }
          }
LABEL_215:
          v32 = v122;
          v30 = v123;
          v24 = v128;
          v22 = v132;
          if ( v96 )
          {
LABEL_79:
            v31 = v121;
          }
          else
          {
            HIWORD(v31) = HIWORD(v121);
            LOWORD(v31) = v121 + 1;
            v121 = v31;
          }
LABEL_80:
          v20 = v126;
          v25 = v127;
LABEL_81:
          v30 = (__int64 *)*v30;
          continue;
        }
        LODWORD(v57) = -1073741801;
LABEL_223:
        v141[2] = 297;
        v141[0] = "onecore\\base\\xml\\udom_builder.cpp";
        v116 = v141;
        v141[1] = "CMicrodomBuilder::CElementNameToAttributeListTable::MaybeInsert";
        v141[3] = "m_StoredTable.FindOrInsertIfNotPresent(Pair, Value, 0, pfExisted)";
LABEL_225:
        RtlReportErrorOrigination(v116, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v57);
LABEL_226:
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v172);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v146);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v159);
        return (unsigned int)v57;
      case 9:
        goto LABEL_81;
      case 0xA:
        v115 = *((_DWORD *)v30 + 30);
        v135 = *((_DWORD *)v30 + 29);
        v123 = v30 + 14;
        v136 = v115;
        v134 = -1;
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucketChain::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,_MICRODOM_XML_ATTDEF const *>(
          (_DWORD)v173 + 32 * ((unsigned int)(65599 * v135 + v115 - 788848704) % v175),
          (unsigned int)&v133,
          (unsigned int)v172,
          (unsigned int)&v134,
          (__int64)&v123,
          65599 * v135 + v115 - 788848704,
          v120);
        LODWORD(v57) = v133;
        if ( v133 < 0 )
        {
          v142[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v142[1] = "CMicrodomBuilder::CNamespaceNamePrefixToAttDef::Insert";
          v116 = v142;
          v142[2] = 267;
          v142[3] = "m_StoredTable.FindOrInsertIfNotPresent(Pair, pAttDef)";
          goto LABEL_225;
        }
        v32 = v122;
        LOWORD(v31) = v31 + 1;
        v121 = v31;
        goto LABEL_80;
      case 0xC:
        if ( !v30[8] )
          goto LABEL_81;
        if ( v20 - v32 < 0xC )
          goto LABEL_233;
        *(_BYTE *)v32 = 5;
        *(_DWORD *)(v32 + 4) = *((_DWORD *)v30 + 29);
        *(_DWORD *)(v32 + 8) = *((_DWORD *)v30 + 30);
        v30 = (__int64 *)*v30;
        v32 = (v32 + 15) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        continue;
      case 0xD:
        if ( v20 - v32 < 8 )
          goto LABEL_233;
        *(_BYTE *)v32 = 6;
        *(_DWORD *)(v32 + 4) = *((_DWORD *)v30 + 29);
        v30 = (__int64 *)*v30;
        v32 = (v32 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        continue;
      case 0xE:
        v145 = 0;
        if ( v20 - v32 < 4 )
        {
          INTERNAL_ERROR_ACTION(-1073741595);
          __debugbreak();
        }
        v58 = v30[13];
        v59 = 0;
        LOWORD(v124) = 0;
        HIDWORD(v124) = 0;
        if ( v58 > 0xFFFF )
        {
          HIDWORD(v124) = -1073741675;
        }
        else
        {
          v59 = v58;
          LOWORD(v124) = v58;
          if ( v58 == (unsigned __int16)v58 )
            HIDWORD(v124) = 0;
          else
            HIDWORD(v124) = -1073741595;
        }
        v57 = HIDWORD(v124);
        *(_WORD *)(v32 + 2) = v59;
        if ( (v57 & 0x80000000) != 0LL )
        {
          v139[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v139[1] = "CMicrodomBuilder::WriteXmlDom";
          v116 = v139;
          v139[2] = 2661;
          v139[3] = "BUCL::Rtl::ConvertInteger(pObject->m_cChildren, pDocument->usChildNodes)";
          goto LABEL_225;
        }
        *(_BYTE *)v32 = 7;
        v60 = (v32 + 7) & 0xFFFFFFFFFFFFFFFCuLL;
        LODWORD(v57) = ((__int64 (__fastcall *)(CMicrodomBuilder *, unsigned __int64, __int64 *, __int64 *))v24)(
                         v22,
                         v60,
                         &v145,
                         v30);
        if ( (v57 & 0x80000000) != 0LL )
          goto LABEL_226;
        v32 = (v60 + v145 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
        v122 = v32;
        goto LABEL_80;
      default:
        goto LABEL_233;
    }
  }
}

```

## disassembly

```asm
0x180019030  push    rbp
0x180019032  push    rbx
0x180019033  push    rdi
0x180019034  push    r13
0x180019036  lea     rbp, [rsp-418h]
0x18001903e  sub     rsp, 518h
0x180019045  mov     rax, cs:__security_cookie
0x18001904c  xor     rax, rsp
0x18001904f  mov     [rbp+430h+var_40], rax
0x180019056  mov     rax, [rdx+8]
0x18001905a  mov     rdi, rcx
0x18001905d  mov     r13, [rdx+10h]
0x180019061  xor     ebx, ebx
0x180019063  mov     [rbp+430h+var_4A0], rcx
0x180019067  lea     rcx, [rbp+430h+var_250]
0x18001906e  mov     [rbp+430h+var_3B0], rax
0x180019075  mov     rax, [rdx]
0x180019078  mov     [rbp+430h+var_278], rcx
0x18001907f  lea     rcx, [rbp+430h+var_250]; void *
0x180019086  mov     [rbp+430h+var_3B8], rax
0x18001908a  mov     [rbp+430h+var_480], rdx
0x18001908e  mov     [rbp+430h+var_270], rbx
0x180019095  mov     [rbp+430h+var_268], 7
0x1800190a0  mov     [rbp+430h+var_260], rbx
0x1800190a7  mov     [rbp+430h+var_258], 23h ; '#'
0x1800190b2  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190b7  lea     rcx, [rbp+430h+var_230]; void *
0x1800190be  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190c3  lea     rcx, [rbp+430h+var_210]; void *
0x1800190ca  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190cf  lea     rcx, [rbp+430h+var_1F0]; void *
0x1800190d6  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190db  lea     rcx, [rbp+430h+var_1D0]; void *
0x1800190e2  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190e7  lea     rcx, [rbp+430h+var_1B0]; void *
0x1800190ee  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190f3  lea     rcx, [rbp+430h+var_190]; void *
0x1800190fa  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800190ff  lea     rax, [rbp+430h+var_370]
0x180019106  mov     [rbp+430h+var_390], rbx
0x18001910d  lea     rcx, [rbp+430h+var_370]; void *
0x180019114  mov     [rbp+430h+var_398], rax
0x18001911b  mov     [rbp+430h+var_388], 7
0x180019126  mov     [rbp+430h+Size], rbx
0x18001912d  mov     [rbp+430h+var_378], 23h ; '#'
0x180019138  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x18001913d  lea     rcx, [rbp+430h+var_350]; void *
0x180019144  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019149  lea     rcx, [rbp+430h+var_330]; void *
0x180019150  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019155  lea     rcx, [rbp+430h+var_310]; void *
0x18001915c  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019161  lea     rcx, [rbp+430h+var_2F0]; void *
0x180019168  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x18001916d  lea     rcx, [rbp+430h+var_2D0]; void *
0x180019174  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019179  lea     rcx, [rbp+430h+var_2B0]; void *
0x180019180  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019185  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x18001918d  lea     rax, [rbp+430h+var_130]
0x180019194  lea     rcx, [rbp+430h+var_130]; void *
0x18001919b  mov     [rbp+430h+var_158], rax
0x1800191a2  movdqa  [rbp+430h+var_140], xmm0
0x1800191aa  mov     [rbp+430h+var_150], rbx
0x1800191b1  mov     [rbp+430h+var_148], 7
0x1800191bc  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191c1  lea     rcx, [rbp+430h+var_110]; void *
0x1800191c8  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191cd  lea     rcx, [rbp+430h+var_F0]; void *
0x1800191d4  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191d9  lea     rcx, [rbp+430h+var_D0]; void *
0x1800191e0  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191e5  lea     rcx, [rbp+430h+var_B0]; void *
0x1800191ec  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191f1  lea     rcx, [rbp+430h+var_90]; void *
0x1800191f8  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800191fd  lea     rcx, [rbp+430h+var_70]; void *
0x180019204  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180019209  lea     rcx, [rbp+430h+var_280]
0x180019210  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x180019215  mov     ebx, eax
0x180019217  test    eax, eax
0x180019219  js      loc_18001A2C0
0x18001921f  lea     rcx, [rbp+430h+var_3A0]
0x180019226  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x18001922b  mov     ebx, eax
0x18001922d  test    eax, eax
0x18001922f  js      loc_18001A2C0
0x180019235  lea     rax, [rbp+430h+var_130]
0x18001923c  cmp     [rbp+430h+var_158], rax
0x180019243  jz      short loc_180019250
0x180019245  int     3; Trap to Debugger
0x180019246  mov     ebx, 0C00000E5h
0x18001924b  jmp     loc_18001A284
0x180019250  mov     rcx, [rbp+430h+var_148]
0x180019257  mov     r8, 0FFFFFFFF00000000h
0x180019261  mov     rax, rcx
0x180019264  shr     rax, 20h
0x180019268  test    eax, eax
0x18001926a  jnz     short loc_18001927B
0x18001926c  mov     eax, ecx
0x18001926e  lea     rcx, [rax+rax*4]
0x180019272  mov     qword ptr [rbp+430h+var_140+8], rcx
0x180019279  jmp     short loc_1800192B1
0x18001927b  lea     rdx, [rax+rax*4]
0x18001927f  test    r8, rdx
0x180019282  jnz     loc_18001A274
0x180019288  shl     rdx, 20h
0x18001928c  mov     eax, ecx
0x18001928e  lea     rcx, [rax+rax*4]
0x180019292  lea     rax, [rdx+rcx]
0x180019296  cmp     rax, rcx
0x180019299  mov     qword ptr [rbp+430h+var_140+8], rax
0x1800192a0  sbb     ebx, ebx
0x1800192a2  and     ebx, 0C0000095h
0x1800192a8  cmp     rax, rcx
0x1800192ab  jb      loc_18001A284
0x1800192b1  mov     [rsp+530h+arg_10], rsi
0x1800192b9  mov     edx, 22h ; '"'; unsigned int
0x1800192be  mov     [rsp+530h+var_20], r12
0x1800192c6  mov     r8d, edx; unsigned __int64
0x1800192c9  mov     [rsp+530h+var_28], r14
0x1800192d1  mov     r14, cs:Buf1
0x1800192d8  mov     rcx, r14; void *
0x1800192db  mov     [rsp+530h+var_30], r15
0x1800192e3  mov     [rbp+430h+var_4B0], 0FFFFFFFFh
0x1800192ea  call    ?MurmurHash3_x64_64@@YA_KPEBXI_K@Z; MurmurHash3_x64_64(void const *,uint,unsigned __int64)
0x1800192ef  mov     r15, [rdi+20h]
0x1800192f3  xor     edx, edx
0x1800192f5  mov     r12, [rdi+10h]
0x1800192f9  mov     rsi, rax
0x1800192fc  div     r15
0x1800192ff  mov     rdi, rdx
0x180019302  shl     rdi, 5
0x180019306  add     rdi, r12
0x180019309  mov     rbx, [rdi]
0x18001930c  nop     dword ptr [rax+00h]
0x180019310  test    rbx, rbx
0x180019313  jz      short loc_18001934D
0x180019315  cmp     rbx, rdi
0x180019318  jz      short loc_18001934D
0x18001931a  cmp     [rbx+20h], rsi
0x18001931e  jnz     short loc_18001933D
0x180019320  cmp     qword ptr [rbx+28h], 22h ; '"'
0x180019325  jnz     short loc_18001933D
0x180019327  mov     rdx, [rbx+38h]; Buf2
0x18001932b  mov     r8d, 22h ; '"'; Size
0x180019331  mov     rcx, r14; Buf1
0x180019334  call    memcmp
0x180019339  test    eax, eax
0x18001933b  jz      short loc_180019342
0x18001933d  mov     rbx, [rbx]
0x180019340  jmp     short loc_180019310
0x180019342  add     rbx, 40h ; '@'
0x180019346  jz      short loc_18001934D
0x180019348  mov     eax, [rbx]
0x18001934a  mov     [rbp+430h+var_4B0], eax
0x18001934d  mov     rbx, cs:off_1800A50A8; "Id"
0x180019354  mov     edx, 2; unsigned int
0x180019359  mov     r8d, edx; unsigned __int64
0x18001935c  mov     [rbp+430h+var_4A8], 0FFFFFFFFh
0x180019363  mov     rcx, rbx; void *
0x180019366  call    ?MurmurHash3_x64_64@@YA_KPEBXI_K@Z; MurmurHash3_x64_64(void const *,uint,unsigned __int64)
0x18001936b  xor     edx, edx
0x18001936d  mov     r9, rax
0x180019370  div     r15
0x180019373  shl     rdx, 5
0x180019377  add     rdx, r12
0x18001937a  mov     r8, [rdx]
0x18001937d  nop     dword ptr [rax]
0x180019380  test    r8, r8
0x180019383  jz      short loc_1800193B4
0x180019385  cmp     r8, rdx
0x180019388  jz      short loc_1800193B4
0x18001938a  cmp     [r8+20h], r9
0x18001938e  jnz     short loc_1800193A3
0x180019390  cmp     qword ptr [r8+28h], 2
0x180019395  jnz     short loc_1800193A3
0x180019397  mov     rcx, [r8+38h]
0x18001939b  movzx   eax, word ptr [rbx]
0x18001939e  cmp     ax, [rcx]
0x1800193a1  jz      short loc_1800193A8
0x1800193a3  mov     r8, [r8]
0x1800193a6  jmp     short loc_180019380
0x1800193a8  add     r8, 40h ; '@'
0x1800193ac  jz      short loc_1800193B4
0x1800193ae  mov     eax, [r8]
0x1800193b1  mov     [rbp+430h+var_4A8], eax
0x1800193b4  mov     r11, [rbp+430h+var_3B0]
0x1800193bb  mov     rcx, [rbp+430h+var_3B8]
0x1800193bf  add     r11, r13
0x1800193c2  add     rcx, r13
0x1800193c5  mov     [rsp+530h+var_4C8], r11
0x1800193ca  mov     rax, r11
0x1800193cd  sub     rax, rcx
0x1800193d0  cmp     rax, 14h
0x1800193d4  jb      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x1800193da  mov     r14, [rbp+430h+var_4A0]
0x1800193de  mov     dword ptr [rcx], 6C44644Dh
0x1800193e4  mov     eax, [r14+510h]
0x1800193eb  mov     [rcx+8], eax
0x1800193ee  mov     eax, [r14+510h]
0x1800193f5  cmp     eax, 0FFh
0x1800193fa  ja      short loc_18001940C
0x1800193fc  mov     dword ptr [rcx+4], 1
0x180019403  lea     rsi, ??$WriteDomElementIndicies@E@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<uchar>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x18001940a  jmp     short loc_180019431
0x18001940c  cmp     eax, 0FFFFh
0x180019411  ja      short loc_180019423
0x180019413  mov     dword ptr [rcx+4], 2
0x18001941a  lea     rsi, ??$WriteDomElementIndicies@G@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ushort>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x180019421  jmp     short loc_180019431
0x180019423  mov     dword ptr [rcx+4], 3
0x18001942a  lea     rsi, ??$WriteDomElementIndicies@K@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ulong>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x180019431  lea     r9, [r14+4F0h]
0x180019438  mov     [rsp+530h+var_4B8], rsi
0x18001943d  mov     rdx, [r9]
0x180019440  mov     [rsp+530h+var_4C0], r9
0x180019445  cmp     rdx, r9
0x180019448  jz      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x18001944e  test    rdx, rdx
0x180019451  jz      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x180019457  cmp     word ptr [rdx+72h], 0Eh
0x18001945c  jnz     def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x180019462  mov     eax, [rdx+48h]
0x180019465  add     rdx, 58h ; 'X'
0x180019469  mov     [rcx+10h], eax
0x18001946c  mov     rax, [rdx]
0x18001946f  cmp     rax, rdx
0x180019472  jz      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x180019478  cmp     word ptr [rax+42h], 0
0x18001947d  jz      short loc_18001948D
0x18001947f  mov     rax, [rax]
0x180019482  cmp     rax, rdx
0x180019485  jz      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x18001948b  jmp     short loc_180019478
0x18001948d  mov     eax, [rax+18h]
0x180019490  lea     r10, [rcx+17h]
0x180019494  mov     edx, 0FFFFFFFFh
0x180019499  mov     [rcx+0Ch], eax
0x18001949c  mov     r15, [r9]
0x18001949f  lea     rbx, __ImageBase
0x1800194a6  xor     r12d, r12d
0x1800194a9  mov     [rsp+530h+var_4D0], edx
0x1800194ad  and     r10, 0FFFFFFFFFFFFFFFCh
0x1800194b1  mov     [rsp+530h+var_4F0], r12d
0x1800194b6  mov     r8d, 0C00000E5h
0x1800194bc  mov     [rsp+530h+var_4E8], r10
0x1800194c1  mov     r13d, edx
0x1800194c4  mov     [rbp+430h+var_4AC], edx
0x1800194c7  mov     [rsp+530h+var_4EC], r8d
0x1800194cc  lea     rdi, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800194d3  mov     [rsp+530h+var_4E0], r15
0x1800194d8  test    r15, r15
0x1800194db  jz      loc_18001A237
0x1800194e1  cmp     r15, r9
0x1800194e4  jz      loc_18001A237
0x1800194ea  movzx   eax, word ptr [r15+72h]
0x1800194ef  lea     rdx, [r15+70h]
0x1800194f3  cmp     eax, 0Eh; switch 15 cases
0x1800194f6  ja      def_180019506; jumptable 0000000180019506 default case, cases 6,11
0x1800194fc  mov     ecx, ds:(jpt_180019506 - 180000000h)[rbx+rax*4]
0x180019503  add     rcx, rbx
0x180019506  jmp     rcx; switch jump
0x18001950c  mov     r15d, [r15+4Ch]; jumptable 0000000180019506 case 0
0x180019510  xor     r13d, r13d
0x180019513  mov     r14, [rsp+530h+var_4E0]
0x180019518  mov     eax, r15d
0x18001951b  mov     [rbp+430h+var_3B8], r13
0x18001951f  mov     r14, [r14+68h]
0x180019523  sub     r14, r15
0x180019526  cmp     r15, r14
0x180019529  mov     r12, r14
0x18001952c  cmovnb  rax, r14
0x180019530  cmovnb  r12, r15
0x180019534  test    rax, rax
0x180019537  jz      short loc_180019540
0x180019539  shl     rax, 16h
0x18001953d  or      r12, rax
0x180019540  mov     rsi, r13
0x180019543  cmp     [rbp+430h+var_388], r13
0x18001954a  jbe     short loc_1800195A2
0x18001954c  nop     dword ptr [rax+00h]
0x180019550  mov     rdi, rsi
0x180019553  shl     rdi, 5
0x180019557  add     rdi, [rbp+430h+var_398]
0x18001955e  mov     rdx, [rdi]
0x180019561  test    rdx, rdx
0x180019564  jz      short loc_180019587
0x180019566  cmp     rdx, rdi
0x180019569  jz      short loc_180019587
0x18001956b  nop     dword ptr [rax+rax+00h]
0x180019570  mov     rbx, [rdx]
0x180019573  lea     rcx, [rbp+430h+var_3A0]
0x18001957a  call    ?DeallocateBucket@?$CTable@VCTableTraits@?$CFourStringIdTable@PEBU_MICRODOM_XML_ATTDEF@@@CMicrodomBuilder@@@HashTable@BUCL@@AEBAXPEAVCBucket@123@@Z; BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeallocateBucket(BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket *)
0x18001957f  mov     rdx, rbx
0x180019582  cmp     rbx, rdi
0x180019585  jnz     short loc_180019570
0x180019587  inc     rsi
0x18001958a  mov     [rdi], rdi
  ... truncated ...
```
