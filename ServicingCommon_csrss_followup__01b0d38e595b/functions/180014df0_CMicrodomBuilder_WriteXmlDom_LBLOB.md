# CMicrodomBuilder::WriteXmlDom(_LBLOB *)

- ea: `0x180014df0`
- end: `0x180015afc`
- name: `?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z`
- size: `3340`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800148d4`

## callees

- `0x18000d4f8`
- `0x180014df0`
- `0x180015b04`
- `0x18001628c`
- `0x18001cb40`
- `0x18001cb60`
- `0x18001cc14`
- `0x18001ccd0`
- `0x18001f840`
- `0x180020268`
- `0x180020810`
- `0x180021b70`
- `0x180021ed0`
- `0x180021ef8`
- `0x180022c90`
- `0x180026dc0`
- `0x18002d2b0`
- `0x180062470`
- `0x180063328`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800153cb`
- `ntdll!RtlRaiseStatus` at `0x180015a81`
- `ntdll!RtlRaiseStatus` at `0x180015abb`
- `ntdll!RtlRaiseStatus` at `0x1800153cb`
- `ntdll!RtlRaiseStatus` at `0x180015a81`
- `ntdll!RtlRaiseStatus` at `0x180015abb`

## string_xrefs

- `0x18001560e`: `onecore\base\xml\udom_builder.cpp`
- `0x1800158ba`: `onecore\base\xml\udom_builder.cpp`
- `0x180015a19`: `onecore\base\xml\udom_builder.cpp`
- `0x180015a30`: `CMicrodomBuilder::WriteXmlDom`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::WriteXmlDom(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  __int64 v5; // r14
  int v6; // ebx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rbx
  _DWORD *v11; // rcx
  CMicrodomBuilder *v12; // r10
  unsigned int v13; // eax
  __int64 (__fastcall *v14)(); // r11
  int **v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 **v18; // rdx
  __int64 *i; // rax
  unsigned __int64 v20; // rsi
  struct HINSTANCE__ *v21; // rbx
  struct HINSTANCE__ *v22; // rdx
  unsigned __int64 v23; // r9
  int *v24; // rsi
  char v25; // al
  int v26; // r14d
  int v27; // r13d
  int v28; // r15d
  unsigned __int64 v29; // r8
  __int64 **v30; // rdx
  __int64 *j; // rax
  _DWORD *v32; // rcx
  unsigned __int64 v33; // rbx
  __int16 *v34; // rax
  __int16 v35; // ax
  int v36; // edi
  unsigned __int64 v37; // r12
  int v38; // edi
  unsigned __int64 v39; // r12
  struct _LBLOB *v40; // rax
  unsigned __int64 v41; // r12
  struct HINSTANCE__ *v42; // rdi
  int v43; // eax
  const struct _MICRODOM_XML_ATTDEF *v44; // r9
  unsigned __int64 v45; // r15
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // r14
  int v48; // eax
  int v49; // ebx
  unsigned int v50; // ebx
  _QWORD *v51; // rdi
  bool v52; // si
  _QWORD *k; // rcx
  void *v54; // rax
  __int64 v55; // rax
  _QWORD *v56; // rbx
  __int128 v57; // xmm0
  unsigned __int64 v58; // rax
  int v59; // r8d
  int v60; // r9d
  __int64 **v61; // rdx
  __int64 *m; // rax
  __int64 *v63; // rax
  int v64; // eax
  unsigned __int64 v65; // r12
  const char *v66; // rax
  int v67; // ebx
  _QWORD *v68; // rcx
  __int64 v69; // r8
  int v70; // eax
  int v71; // eax
  __int64 v72; // r10
  __int64 (__fastcall *v73)(__int64, unsigned __int64, __int64 *, int *); // r11
  int v74; // r9d
  bool v75[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v76; // [rsp+34h] [rbp-CCh]
  int v77; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall *v78)(); // [rsp+40h] [rbp-C0h]
  CMicrodomBuilder *v79; // [rsp+48h] [rbp-B8h]
  int *v80; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v81; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v82; // [rsp+60h] [rbp-A0h]
  int **v83; // [rsp+68h] [rbp-98h]
  int v84; // [rsp+70h] [rbp-90h]
  __int64 v85; // [rsp+78h] [rbp-88h] BYREF
  const char *v86; // [rsp+80h] [rbp-80h] BYREF
  const char *v87; // [rsp+88h] [rbp-78h]
  __int64 v88; // [rsp+90h] [rbp-70h]
  const char *v89; // [rsp+98h] [rbp-68h]
  int v90; // [rsp+A0h] [rbp-60h] BYREF
  int v91; // [rsp+A4h] [rbp-5Ch] BYREF
  _DWORD v92[2]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v93[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v94; // [rsp+B8h] [rbp-48h] BYREF
  struct _LBLOB *v95; // [rsp+C8h] [rbp-38h]
  __int64 v96; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v97; // [rsp+D8h] [rbp-28h] BYREF
  int v98; // [rsp+E0h] [rbp-20h] BYREF
  int v99[3]; // [rsp+E4h] [rbp-1Ch] BYREF
  char v100[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v101; // [rsp+F8h] [rbp-8h]
  __int64 v102; // [rsp+100h] [rbp+0h]
  unsigned __int64 v103; // [rsp+108h] [rbp+8h]
  unsigned __int64 v104; // [rsp+110h] [rbp+10h]
  unsigned __int64 v105; // [rsp+118h] [rbp+18h]
  _BYTE v106[32]; // [rsp+120h] [rbp+20h] BYREF
  char v107[32]; // [rsp+140h] [rbp+40h] BYREF
  char v108[32]; // [rsp+160h] [rbp+60h] BYREF
  char v109[32]; // [rsp+180h] [rbp+80h] BYREF
  char v110[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v111[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v112[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v113[8]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE *v114; // [rsp+218h] [rbp+118h]
  __int64 v115; // [rsp+220h] [rbp+120h]
  unsigned __int64 v116; // [rsp+228h] [rbp+128h]
  __m128i v117; // [rsp+230h] [rbp+130h]
  _BYTE v118[32]; // [rsp+240h] [rbp+140h] BYREF
  char v119[32]; // [rsp+260h] [rbp+160h] BYREF
  char v120[32]; // [rsp+280h] [rbp+180h] BYREF
  char v121[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v122[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v123[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v124[48]; // [rsp+300h] [rbp+200h] BYREF
  char v125[8]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE *v126; // [rsp+338h] [rbp+238h]
  __int64 v127; // [rsp+340h] [rbp+240h]
  unsigned __int64 v128; // [rsp+348h] [rbp+248h]
  __m128i si128; // [rsp+350h] [rbp+250h]
  _BYTE v130[32]; // [rsp+360h] [rbp+260h] BYREF
  char v131[32]; // [rsp+380h] [rbp+280h] BYREF
  char v132[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v133[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v134[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  char v135[32]; // [rsp+400h] [rbp+300h] BYREF
  char v136[48]; // [rsp+420h] [rbp+320h] BYREF

  v2 = *((_QWORD *)a2 + 2);
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)a2;
  v79 = this;
  v99[0] = 0;
  v126 = v130;
  v127 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v95 = a2;
  v85 = -1;
  v128 = 7;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v130);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v131);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v132);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v133);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v134);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v135);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v136);
  v102 = 0;
  v101 = v106;
  v103 = 7;
  v104 = 0;
  v105 = 35;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v106);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v107);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v108);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v109);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v110);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v111);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v112);
  v114 = v118;
  v117 = _mm_load_si128((const __m128i *)&_xmm);
  v115 = 0;
  v116 = 7;
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v118);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v119);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v120);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v121);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v122);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v123);
  BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v124);
  v6 = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v125);
  if ( v6 < 0 )
    goto LABEL_2;
  v6 = CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize(v100);
  if ( v6 < 0 )
    goto LABEL_2;
  v6 = CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::Initialize(v113);
  if ( v6 < 0 )
    goto LABEL_2;
  v80 = 0;
  v8 = MurmurHash3_x64_64("http://www.w3.org/2000/09/xmldsig#", 0x22u, 0x22u);
  BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucketChain::Find<_LUTF8_STRING>(
    *((_DWORD *)this + 4) + 32 * (v8 % *((_QWORD *)this + 4)),
    (unsigned int)&v77,
    (unsigned int)qword_18009F1B0,
    v8,
    (__int64)&v80);
  v6 = v77;
  if ( v77 < 0 )
    goto LABEL_2;
  v84 = -1;
  if ( v80 )
    v84 = *v80;
  v80 = 0;
  v9 = MurmurHash3_x64_64("Id", 2u, 2u);
  BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucketChain::Find<_LUTF8_STRING>(
    *((_DWORD *)this + 4) + 32 * (v9 % *((_QWORD *)this + 4)),
    (unsigned int)&v77,
    (unsigned int)qword_18009F1C8,
    v9,
    (__int64)&v80);
  v6 = v77;
  if ( v77 < 0 )
  {
LABEL_2:
    BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v113);
    BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v100);
    BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v125);
    return (unsigned int)v6;
  }
  v77 = -1;
  if ( v80 )
    v77 = *v80;
  v10 = v4 + v2;
  v82 = v4 + v2;
  v11 = (_DWORD *)(v5 + v2);
  if ( (unsigned __int64)(v4 - v5) < 0x14 )
    goto LABEL_53;
  *v11 = 1816421453;
  v12 = this;
  v11[2] = *((_DWORD *)this + 324);
  v13 = *((_DWORD *)this + 324);
  if ( v13 > 0xFF )
  {
    if ( v13 > 0xFFFF )
    {
      v11[1] = 3;
      v14 = CMicrodomBuilder::WriteDomElementIndicies<unsigned long>;
    }
    else
    {
      v11[1] = 2;
      v14 = CMicrodomBuilder::WriteDomElementIndicies<unsigned short>;
    }
  }
  else
  {
    v11[1] = 1;
    v14 = CMicrodomBuilder::WriteDomElementIndicies<unsigned char>;
  }
  v15 = (int **)((char *)this + 1264);
  v78 = v14;
  v16 = *((_QWORD *)this + 158);
  v83 = (int **)((char *)this + 1264);
  if ( (CMicrodomBuilder *)v16 == (CMicrodomBuilder *)((char *)this + 1264) || !v16 || *(_WORD *)(v16 + 114) != 14 )
    goto LABEL_53;
  v17 = *(_DWORD *)(v16 + 72);
  v18 = (__int64 **)(v16 + 88);
  v11[4] = v17;
  for ( i = *v18; ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)v18 )
      goto LABEL_53;
    if ( !*((_WORD *)i + 33) )
      break;
  }
  v70 = *((_DWORD *)i + 6);
  v22 = &_ImageBase;
  v38 = 0;
  v76 = 0;
  v26 = -1;
  v11[3] = v70;
  v24 = *v15;
  v39 = ((unsigned __int64)v11 + 23) & 0xFFFFFFFFFFFFFFFCuLL;
  v28 = -1;
  v27 = -1;
  while ( 1 )
  {
    v80 = v24;
    if ( !v24 || v24 == (int *)v15 )
    {
      v40 = v95;
      v41 = v39 - *((_QWORD *)v95 + 2);
      *(_QWORD *)v95 = v41;
      if ( v41 <= *((_QWORD *)v40 + 1) )
      {
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v113);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v100);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v125);
        return 0;
      }
LABEL_53:
      RtlRaiseStatus(-1073741595);
    }
    v43 = *((unsigned __int16 *)v24 + 57);
    v44 = (const struct _MICRODOM_XML_ATTDEF *)(v24 + 28);
    if ( !*((_WORD *)v24 + 57) )
    {
      v45 = (unsigned int)v24[19];
      v46 = v45;
      v47 = *((_QWORD *)v24 + 13) - v45;
      v97 = 0;
      v23 = v47;
      if ( v45 >= v47 )
      {
        v23 = v45;
        v46 = v47;
      }
      v81 = v23;
      if ( v46 )
      {
        v23 |= v46 << 22;
        v81 = v23;
      }
      v20 = 0;
      if ( v103 )
      {
        do
        {
          v21 = (struct HINSTANCE__ *)&v101[32 * v20];
          v22 = *(struct HINSTANCE__ **)v21;
          if ( *(_QWORD *)v21 && v22 != v21 )
          {
            do
            {
              v42 = *(struct HINSTANCE__ **)v22;
              BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeallocateBucket(v100);
              v22 = v42;
            }
            while ( v42 != v21 );
          }
          *(_QWORD *)v21 = v21;
          ++v20;
          *((_QWORD *)v21 + 1) = v21;
          *((_QWORD *)v21 + 2) = v21;
          *((_QWORD *)v21 + 3) = 0;
        }
        while ( v20 < v103 );
        v23 = v81;
        v12 = v79;
        v14 = v78;
      }
      if ( v101 != v106 )
      {
        BUCL::Rtl::HashTable::CTableTraits<CMicrodomBuilder::FourStringIdPair,_MICRODOM_XML_ATTDEF const *,unsigned long,CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::DeleteArray<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucketChain>(
          v101,
          v22);
        v23 = v81;
        v12 = v79;
        v14 = v78;
        v101 = v106;
        v103 = 7;
      }
      v24 = v80;
      v104 = 0;
      v25 = 1;
      if ( v45 < v47 )
        v25 = -127;
      *(_BYTE *)v39 = v25;
      v26 = v24[29];
      *(_DWORD *)(v39 + 12) = v26;
      v27 = v24[30];
      *(_DWORD *)(v39 + 16) = v27;
      v28 = v24[31];
      *(_DWORD *)(v39 + 20) = v28;
      v29 = (unsigned int)(8261505 * v28 + 780587199 * v26 - 65600);
      v30 = (__int64 **)&v126[32 * (v29 % v128)];
      for ( j = *v30; ; j = (__int64 *)*j )
      {
        if ( !j || j == (__int64 *)v30 )
        {
          v32 = (_DWORD *)((v39 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
          v33 = (unsigned __int64)v32;
LABEL_34:
          v35 = -1;
          goto LABEL_35;
        }
        if ( __PAIR64__(v26, v29) == j[4]
          && v28 == *((_DWORD *)j + 10)
          && *((_DWORD *)j + 11) == -1
          && *((_DWORD *)j + 12) == -1 )
        {
          break;
        }
      }
      v32 = (_DWORD *)((v39 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
      v33 = (unsigned __int64)v32;
      v34 = (__int16 *)j + 26;
      if ( !v34 )
        goto LABEL_34;
      v35 = *v34;
LABEL_35:
      *(_WORD *)(v39 + 8) = v35;
      if ( v23 >= 0x400000 )
      {
        if ( (unsigned __int64)(v82 - (_QWORD)v32) < 4 )
          RtlRaiseStatus(-1073741595);
        *v32 = v23 & 0x3FFFFF;
        v74 = *(_DWORD *)(v39 + 4) ^ (v23 >> 22);
        *(_BYTE *)(v39 + 1) |= 1u;
        *(_DWORD *)(v39 + 4) ^= v74 & 0x3FFFFF;
        v33 = ((unsigned __int64)v32 + 7) & 0xFFFFFFFFFFFFFFFCuLL;
      }
      else
      {
        *(_DWORD *)(v39 + 4) ^= (*(_DWORD *)(v39 + 4) ^ v23) & 0x3FFFFF;
        *(_BYTE *)(v39 + 1) &= ~1u;
      }
      v36 = ((__int64 (__fastcall *)(CMicrodomBuilder *, unsigned __int64, __int64 *, int *))v14)(v12, v33, &v97, v24);
      if ( v36 < 0 )
      {
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v113);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v100);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v125);
        return (unsigned int)v36;
      }
      v37 = v33 + v97 + 3;
      goto LABEL_39;
    }
    if ( v43 == 1 )
    {
      if ( v10 - v39 < 0x14 )
        goto LABEL_53;
      v48 = v24[31];
      v49 = 780587199 * v24[30];
      LODWORD(v94) = v24[30];
      DWORD1(v94) = v48;
      v98 = 0;
      *((_QWORD *)&v94 + 1) = -1;
      v50 = 8261505 * v48 - 65600 + v49;
      v51 = &v101[32 * (v50 % v103)];
      v52 = 0;
      v75[0] = 0;
      for ( k = (_QWORD *)*v51; k && k != v51; k = (_QWORD *)*v68 )
      {
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket::Matches<CMicrodomBuilder::FourStringIdPair>(
          (_DWORD)k,
          (unsigned int)&v90,
          (unsigned int)&v94,
          v50,
          (__int64)v75);
        v69 = (unsigned int)v90;
        if ( v90 < 0 )
          goto LABEL_84;
        v52 = v75[0];
        if ( v75[0] )
        {
          v58 = v104;
          goto LABEL_65;
        }
      }
      v54 = operator new(0x38u);
      if ( v54 )
      {
        v55 = BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::CBucket::CBucket(
                v54,
                v50,
                v100);
        v81 = v55;
        v56 = (_QWORD *)v55;
        if ( v55 )
        {
          v57 = v94;
          *(_WORD *)(v55 + 52) = 0;
          v81 = 0;
          *(_OWORD *)(v55 + 36) = v57;
          BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CNewingAndDeletingPointer<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket>::~CNewingAndDeletingPointer<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket>(&v81);
          v56[1] = v51[1];
          *v56 = v51;
          *(_QWORD *)v51[1] = v56;
          v51[1] = v56;
          v56[2] = v51;
          ++v51[3];
          v58 = ++v104;
LABEL_65:
          if ( v58 > v105 )
          {
            BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::ResizeBucketTable(
              v100,
              &v91);
            v69 = (unsigned int)v91;
            if ( v91 < 0 )
            {
LABEL_84:
              v52 = 0;
              if ( (int)v69 < 0 )
              {
LABEL_85:
                v88 = 209;
                v86 = "onecore\\base\\xml\\udom_builder.cpp";
                v87 = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
                v66 = "m_StoredTable.FindOrInsertIfNotPresent(p, (USHORT)0, 0, &fExisted)";
                goto LABEL_86;
              }
            }
          }
          if ( !v52 )
          {
LABEL_67:
            v24 = v80;
            *(_BYTE *)v39 = 2;
            *(_DWORD *)(v39 + 12) = v24[31];
            *(_DWORD *)(v39 + 8) = v24[30];
            *(_DWORD *)(v39 + 4) = v24[29];
            *(_DWORD *)(v39 + 16) = v24[32];
            if ( !*((_BYTE *)v24 + 132) )
              *(_BYTE *)v39 = 34;
            v59 = v24[29];
            v60 = v24[31];
            v61 = (__int64 **)&v114[32 * ((unsigned int)(780587199 * v26 + v60 + 8261505 * v28 + 65599 * v59) % v116)];
            for ( m = *v61; m && m != (__int64 *)v61; m = (__int64 *)*m )
            {
              if ( *((_DWORD *)m + 8) == 780587199 * v26 + v60 + 8261505 * v28 + 65599 * v59
                && v26 == *((_DWORD *)m + 9)
                && v28 == *((_DWORD *)m + 10)
                && v59 == *((_DWORD *)m + 11)
                && v60 == *((_DWORD *)m + 12) )
              {
                v63 = m + 7;
                if ( v63 && *(_DWORD *)(*v63 + 12) == 1 )
                  *(_BYTE *)v39 |= 0x10u;
                break;
              }
            }
            v64 = *(_DWORD *)(v39 + 8);
            if ( (v64 == v84 || v64 == -1 && v27 == v84) && *(_DWORD *)(v39 + 12) == v77 )
              *(_BYTE *)v39 |= 0x10u;
            v37 = v39 + 23;
LABEL_39:
            v38 = v76;
            v39 = v37 & 0xFFFFFFFFFFFFFFFCuLL;
LABEL_40:
            v10 = v82;
            v22 = &_ImageBase;
            v14 = v78;
            v12 = v79;
            v15 = v83;
            goto LABEL_41;
          }
          v88 = 211;
          v86 = "onecore\\base\\xml\\udom_builder.cpp";
          v69 = 3221266563LL;
          v87 = "CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence";
          v66 = "!fExisted";
LABEL_86:
          v89 = v66;
          v67 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v98,
                  &v86,
                  v69);
          if ( v67 < 0 )
            goto LABEL_140;
          goto LABEL_67;
        }
      }
      else
      {
        v81 = 0;
      }
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CNewingAndDeletingPointer<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket>::~CNewingAndDeletingPointer<BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucket>(&v81);
      v69 = 3221225495LL;
      goto LABEL_85;
    }
    if ( v43 != 4 )
      break;
    if ( v10 - v39 < 8 )
      goto LABEL_53;
    *(_BYTE *)v39 = 3;
LABEL_82:
    *(_DWORD *)(v39 + 4) = v24[29];
    v65 = v39 + 11;
LABEL_83:
    v39 = v65 & 0xFFFFFFFFFFFFFFFCuLL;
LABEL_41:
    v24 = *(int **)v24;
  }
  if ( v43 == 3 )
  {
LABEL_75:
    v26 = -1;
    v28 = -1;
    goto LABEL_41;
  }
  switch ( *((_WORD *)v24 + 57) )
  {
    case 2:
      goto LABEL_75;
    case 5:
      if ( v10 - v39 < 8 )
        goto LABEL_53;
      *(_BYTE *)v39 = 19;
      goto LABEL_82;
    case 7:
      LOWORD(v38) = v38 + 1;
      v76 = v38;
      goto LABEL_41;
    case 8:
      v92[0] = v24[29];
      v92[1] = v24[30];
      v75[0] = 0;
      v67 = CMicrodomBuilder::CElementNameToAttributeListTable::MaybeInsert(
              (CMicrodomBuilder::CElementNameToAttributeListTable *)v125,
              (const struct CMicrodomBuilder::TwoStringIdPair *)v92,
              v38,
              v75);
      if ( v67 < 0 )
        goto LABEL_140;
      if ( !v75[0] )
      {
        LOWORD(v38) = v38 + 1;
        v76 = v38;
      }
      goto LABEL_40;
    case 9:
      v85 = -1;
      goto LABEL_41;
    case 0xA:
      v93[0] = v24[29];
      v93[1] = v24[30];
      v67 = CMicrodomBuilder::CNamespaceNamePrefixToAttDef::Insert(
              (CMicrodomBuilder::CNamespaceNamePrefixToAttDef *)v113,
              (const struct CMicrodomBuilder::TwoStringIdPair *)&v85,
              (const struct CMicrodomBuilder::TwoStringIdPair *)v93,
              v44);
      if ( v67 < 0 )
        goto LABEL_140;
      LOWORD(v38) = v38 + 1;
      v76 = v38;
      goto LABEL_40;
    case 0xC:
      if ( !*((_QWORD *)v24 + 8) )
        goto LABEL_41;
      if ( v10 - v39 < 0xC )
        goto LABEL_53;
      *(_BYTE *)v39 = 5;
      *(_DWORD *)(v39 + 4) = v24[29];
      *(_DWORD *)(v39 + 8) = v24[30];
      v65 = v39 + 15;
      goto LABEL_83;
    case 0xD:
      if ( v10 - v39 < 8 )
        goto LABEL_53;
      *(_BYTE *)v39 = 6;
      goto LABEL_82;
    case 0xE:
      v96 = 0;
      if ( v10 - v39 < 4 )
        RtlRaiseStatus(-1073741595);
      v71 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned short>(*((_QWORD *)v24 + 13), v39 + 2, v15, v44);
      if ( v71 >= 0 )
      {
        *(_BYTE *)v39 = 7;
        v67 = v73(v72, (v39 + 7) & 0xFFFFFFFFFFFFFFFCuLL, &v96, v24);
        if ( v67 < 0 )
          goto LABEL_140;
        v37 = ((v39 + 7) & 0xFFFFFFFFFFFFFFFCuLL) + v96 + 3;
        goto LABEL_39;
      }
      v88 = 2661;
      v86 = "onecore\\base\\xml\\udom_builder.cpp";
      v87 = "CMicrodomBuilder::WriteXmlDom";
      v89 = "BUCL::Rtl::ConvertInteger(pObject->m_cChildren, pDocument->usChildNodes)";
      v67 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              v99,
              &v86,
              (unsigned int)v71);
LABEL_140:
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v113);
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v100);
      BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(v125);
      return (unsigned int)v67;
    default:
      goto LABEL_53;
  }
}

```

## disassembly

```asm
0x180014df0  push    rbp
0x180014df2  push    rbx
0x180014df3  push    rsi
0x180014df4  push    rdi
0x180014df5  push    r12
0x180014df7  push    r14
0x180014df9  push    r15
0x180014dfb  lea     rbp, [rsp-360h]
0x180014e03  sub     rsp, 460h
0x180014e0a  mov     rax, cs:__security_cookie
0x180014e11  xor     rax, rsp
0x180014e14  mov     [rbp+390h+var_40], rax
0x180014e1b  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x180014e23  lea     rax, [rbp+390h+var_130]
0x180014e2a  mov     rdi, [rdx+10h]
0x180014e2e  mov     r15, rcx
0x180014e31  mov     rsi, [rdx+8]
0x180014e35  xor     r12d, r12d
0x180014e38  mov     r14, [rdx]
0x180014e3b  mov     [rsp+490h+var_448], rcx
0x180014e40  lea     rcx, [rbp+390h+var_130]; void *
0x180014e47  mov     [rbp+390h+var_3AC], r12d
0x180014e4b  mov     [rbp+390h+var_158], rax
0x180014e52  mov     [rbp+390h+var_150], r12
0x180014e59  movdqa  [rbp+390h+var_140], xmm0
0x180014e61  mov     [rbp+390h+var_3C8], rdx
0x180014e65  mov     [rsp+490h+var_418], 0FFFFFFFFFFFFFFFFh
0x180014e6e  mov     [rbp+390h+var_148], 7
0x180014e79  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014e7e  lea     rcx, [rbp+390h+var_110]; void *
0x180014e85  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014e8a  lea     rcx, [rbp+390h+var_F0]; void *
0x180014e91  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014e96  lea     rcx, [rbp+390h+var_D0]; void *
0x180014e9d  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014ea2  lea     rcx, [rbp+390h+var_B0]; void *
0x180014ea9  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014eae  lea     rcx, [rbp+390h+var_90]; void *
0x180014eb5  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014eba  lea     rcx, [rbp+390h+var_70]; void *
0x180014ec1  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014ec6  lea     rax, [rbp+390h+var_370]
0x180014eca  mov     [rbp+390h+var_390], r12
0x180014ece  lea     rcx, [rbp+390h+var_370]; void *
0x180014ed2  mov     [rbp+390h+var_398], rax
0x180014ed6  mov     [rbp+390h+var_388], 7
0x180014ede  mov     [rbp+390h+var_380], r12
0x180014ee2  mov     [rbp+390h+var_378], 23h ; '#'
0x180014eea  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014eef  lea     rcx, [rbp+390h+var_350]; void *
0x180014ef3  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014ef8  lea     rcx, [rbp+390h+var_330]; void *
0x180014efc  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f01  lea     rcx, [rbp+390h+var_310]; void *
0x180014f08  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f0d  lea     rcx, [rbp+390h+var_2F0]; void *
0x180014f14  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f19  lea     rcx, [rbp+390h+var_2D0]; void *
0x180014f20  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f25  lea     rcx, [rbp+390h+var_2B0]; void *
0x180014f2c  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f31  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x180014f39  lea     rax, [rbp+390h+var_250]
0x180014f40  lea     rcx, [rbp+390h+var_250]; void *
0x180014f47  mov     [rbp+390h+var_278], rax
0x180014f4e  movdqa  [rbp+390h+var_260], xmm0
0x180014f56  mov     [rbp+390h+var_270], r12
0x180014f5d  mov     [rbp+390h+var_268], 7
0x180014f68  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f6d  lea     rcx, [rbp+390h+var_230]; void *
0x180014f74  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f79  lea     rcx, [rbp+390h+var_210]; void *
0x180014f80  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f85  lea     rcx, [rbp+390h+var_1F0]; void *
0x180014f8c  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f91  lea     rcx, [rbp+390h+var_1D0]; void *
0x180014f98  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014f9d  lea     rcx, [rbp+390h+var_1B0]; void *
0x180014fa4  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014fa9  lea     rcx, [rbp+390h+var_190]; void *
0x180014fb0  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180014fb5  lea     rcx, [rbp+390h+var_160]
0x180014fbc  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x180014fc1  mov     ebx, eax
0x180014fc3  test    eax, eax
0x180014fc5  jns     short loc_18001500C
0x180014fc7  lea     rcx, [rbp+390h+var_280]
0x180014fce  call    ??1?$CTable@VCTableTraits@?$CFourStringIdTable@G@CMicrodomBuilder@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>(void)
0x180014fd3  lea     rcx, [rbp+390h+var_3A0]
0x180014fd7  call    ??1?$CTable@VCTableTraits@?$CFourStringIdTable@G@CMicrodomBuilder@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>(void)
0x180014fdc  lea     rcx, [rbp+390h+var_160]
0x180014fe3  call    ??1?$CTable@VCTableTraits@?$CFourStringIdTable@G@CMicrodomBuilder@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<ushort>::CTableTraits>(void)
0x180014fe8  mov     eax, ebx
0x180014fea  mov     rcx, [rbp+390h+var_40]
0x180014ff1  xor     rcx, rsp; StackCookie
0x180014ff4  call    __security_check_cookie
0x180014ff9  add     rsp, 460h
0x180015000  pop     r15
0x180015002  pop     r14
0x180015004  pop     r12
0x180015006  pop     rdi
0x180015007  pop     rsi
0x180015008  pop     rbx
0x180015009  pop     rbp
0x18001500a  retn
0x18001500c  lea     rcx, [rbp+390h+var_3A0]
0x180015010  call    ?Initialize@?$CFourStringIdTable@G@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<ushort>::Initialize(void)
0x180015015  lea     rcx, [rbp+390h+var_280]
0x18001501c  mov     ebx, eax
0x18001501e  test    eax, eax
0x180015020  js      short loc_180014FCE
0x180015022  call    ?Initialize@?$CFourStringIdTable@PEBU_MICRODOM_XML_ATTDEF@@@CMicrodomBuilder@@IEAAJXZ; CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::Initialize(void)
0x180015027  mov     ebx, eax
0x180015029  test    eax, eax
0x18001502b  js      short loc_180014FC7
0x18001502d  mov     rcx, cs:off_18009F1C0; void *
0x180015034  mov     edx, 22h ; '"'; unsigned int
0x180015039  mov     r8d, edx; unsigned __int64
0x18001503c  mov     [rsp+490h+var_440], r12
0x180015041  call    ?MurmurHash3_x64_64@@YA_KPEBXI_K@Z; MurmurHash3_x64_64(void const *,uint,unsigned __int64)
0x180015046  xor     edx, edx
0x180015048  lea     r8, qword_18009F1B0
0x18001504f  mov     r9, rax
0x180015052  div     qword ptr [r15+20h]
0x180015056  lea     rax, [rsp+490h+var_440]
0x18001505b  mov     rcx, rdx
0x18001505e  mov     [rsp+490h+var_470], rax
0x180015063  shl     rcx, 5
0x180015067  lea     rdx, [rsp+490h+var_458]
0x18001506c  add     rcx, [r15+10h]
0x180015070  call    ??$Find@U_LUTF8_STRING@@@CBucketChain@?$CTable@VCIntermediateStringTableTraits@CMicrodomBuilder@@@HashTable@BUCL@@QEAA?AVCCallDisposition@Rtl@3@AEBU_LUTF8_STRING@@_KPEAPEAK@Z; BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucketChain::Find<_LUTF8_STRING>(_LUTF8_STRING const &,unsigned __int64,ulong * *)
0x180015075  mov     ebx, [rsp+490h+var_458]
0x180015079  test    ebx, ebx
0x18001507b  js      loc_180014FC7
0x180015081  mov     rax, [rsp+490h+var_440]
0x180015086  mov     [rsp+490h+var_420], 0FFFFFFFFh
0x18001508e  test    rax, rax
0x180015091  jz      short loc_180015099
0x180015093  mov     eax, [rax]
0x180015095  mov     [rsp+490h+var_420], eax
0x180015099  mov     rcx, cs:off_18009F1D8; void *
0x1800150a0  mov     edx, 2; unsigned int
0x1800150a5  mov     r8d, edx; unsigned __int64
0x1800150a8  mov     [rsp+490h+var_440], r12
0x1800150ad  call    ?MurmurHash3_x64_64@@YA_KPEBXI_K@Z; MurmurHash3_x64_64(void const *,uint,unsigned __int64)
0x1800150b2  xor     edx, edx
0x1800150b4  lea     r8, qword_18009F1C8
0x1800150bb  mov     r9, rax
0x1800150be  div     qword ptr [r15+20h]
0x1800150c2  lea     rax, [rsp+490h+var_440]
0x1800150c7  mov     rcx, rdx
0x1800150ca  mov     [rsp+490h+var_470], rax
0x1800150cf  shl     rcx, 5
0x1800150d3  lea     rdx, [rsp+490h+var_458]
0x1800150d8  add     rcx, [r15+10h]
0x1800150dc  call    ??$Find@U_LUTF8_STRING@@@CBucketChain@?$CTable@VCIntermediateStringTableTraits@CMicrodomBuilder@@@HashTable@BUCL@@QEAA?AVCCallDisposition@Rtl@3@AEBU_LUTF8_STRING@@_KPEAPEAK@Z; BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucketChain::Find<_LUTF8_STRING>(_LUTF8_STRING const &,unsigned __int64,ulong * *)
0x1800150e1  mov     ebx, [rsp+490h+var_458]
0x1800150e5  test    ebx, ebx
0x1800150e7  js      loc_180014FC7
0x1800150ed  mov     rax, [rsp+490h+var_440]
0x1800150f2  mov     [rsp+490h+var_458], 0FFFFFFFFh
0x1800150fa  test    rax, rax
0x1800150fd  jz      short loc_180015105
0x1800150ff  mov     eax, [rax]
0x180015101  mov     [rsp+490h+var_458], eax
0x180015105  lea     rbx, [rsi+rdi]
0x180015109  mov     [rsp+490h+arg_10], r13
0x180015111  mov     rax, rbx
0x180015114  mov     [rsp+490h+var_430], rbx
0x180015119  lea     rcx, [r14+rdi]
0x18001511d  sub     rax, rcx
0x180015120  cmp     rax, 14h
0x180015124  jb      def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
0x18001512a  mov     dword ptr [rcx], 6C44644Dh
0x180015130  mov     r10, r15
0x180015133  mov     eax, [r15+510h]
0x18001513a  mov     [rcx+8], eax
0x18001513d  mov     eax, [r15+510h]
0x180015144  cmp     eax, 0FFh
0x180015149  ja      loc_1800156C1
0x18001514f  mov     dword ptr [rcx+4], 1
0x180015156  lea     r11, ??$WriteDomElementIndicies@E@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<uchar>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x18001515d  lea     r8, [r15+4F0h]
0x180015164  mov     [rsp+490h+var_450], r11
0x180015169  mov     rdx, [r8]
0x18001516c  mov     [rsp+490h+var_428], r8
0x180015171  cmp     rdx, r8
0x180015174  jz      def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
0x18001517a  test    rdx, rdx
0x18001517d  jz      def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
0x180015183  cmp     word ptr [rdx+72h], 0Eh
0x180015188  jnz     def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
0x18001518e  mov     eax, [rdx+48h]
0x180015191  add     rdx, 58h ; 'X'
0x180015195  mov     [rcx+10h], eax
0x180015198  mov     rax, [rdx]
0x18001519b  cmp     rax, rdx
0x18001519e  jz      def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
0x1800151a4  cmp     [rax+42h], r12w
0x1800151a9  jz      loc_1800156EE
0x1800151af  mov     rax, [rax]
0x1800151b2  jmp     short loc_18001519B
0x1800151b4  mov     rsi, r13
0x1800151b7  cmp     [rbp+390h+var_388], r13
0x1800151bb  jbe     short loc_1800151FE
0x1800151bd  nop     dword ptr [rax]
0x1800151c0  mov     rbx, rsi
0x1800151c3  shl     rbx, 5
0x1800151c7  add     rbx, [rbp+390h+var_398]
0x1800151cb  mov     rdx, [rbx]
0x1800151ce  test    rdx, rdx
0x1800151d1  jnz     loc_18001537A
0x1800151d7  mov     [rbx], rbx
0x1800151da  inc     rsi
0x1800151dd  mov     [rbx+8], rbx
0x1800151e1  mov     [rbx+10h], rbx
0x1800151e5  mov     [rbx+18h], r13
0x1800151e9  cmp     rsi, [rbp+390h+var_388]
0x1800151ed  jb      short loc_1800151C0
0x1800151ef  mov     r9, [rsp+490h+var_438]
0x1800151f4  mov     r10, [rsp+490h+var_448]
0x1800151f9  mov     r11, [rsp+490h+var_450]
0x1800151fe  mov     rcx, [rbp+390h+var_398]
0x180015202  lea     rax, [rbp+390h+var_370]
0x180015206  cmp     rcx, rax
0x180015209  jnz     loc_180015977
0x18001520f  mov     rsi, [rsp+490h+var_440]
0x180015214  cmp     r15, r14
0x180015217  mov     [rbp+390h+var_380], r13
0x18001521b  mov     eax, 1
0x180015220  mov     ecx, 81h
0x180015225  cmovb   eax, ecx
0x180015228  xor     edx, edx
0x18001522a  mov     [r12], al
0x18001522e  mov     r14d, [rsi+74h]
0x180015232  mov     [r12+0Ch], r14d
0x180015237  mov     r13d, [rsi+78h]
0x18001523b  mov     [r12+10h], r13d
0x180015240  mov     r15d, [rsi+7Ch]
0x180015244  mov     [r12+14h], r15d
0x180015249  imul    r8d, r14d, 2E86D0BFh
0x180015250  imul    ecx, r15d, 7E0F81h
0x180015257  add     r8d, 0FFFEFFC0h
0x18001525e  add     r8d, ecx
0x180015261  mov     eax, r8d
0x180015264  div     [rbp+390h+var_148]
0x18001526b  shl     rdx, 5
0x18001526f  add     rdx, [rbp+390h+var_158]
0x180015276  mov     rax, [rdx]
0x180015279  test    rax, rax
0x18001527c  jz      short loc_180015287
0x18001527e  cmp     rax, rdx
0x180015281  jnz     loc_180015653
0x180015287  lea     rcx, [r12+1Bh]
0x18001528c  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180015290  mov     rbx, rcx
0x180015293  jmp     short loc_1800152AB
0x180015295  lea     rcx, [r12+1Bh]
0x18001529a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18001529e  mov     rbx, rcx
0x1800152a1  add     rax, 34h ; '4'
0x1800152a5  jnz     loc_1800159CD
0x1800152ab  mov     eax, 0FFFFh
0x1800152b0  mov     [r12+8], ax
0x1800152b6  cmp     r9, 400000h
0x1800152bd  jnb     loc_1800159D5
0x1800152c3  xor     r9d, [r12+4]
0x1800152c8  and     r9d, 3FFFFFh
0x1800152cf  xor     [r12+4], r9d
0x1800152d4  and     byte ptr [r12+1], 0FEh
0x1800152da  mov     r9, rsi
0x1800152dd  lea     r8, [rbp+390h+var_3B8]
0x1800152e1  mov     rdx, rbx
0x1800152e4  mov     rcx, r10
0x1800152e7  mov     rax, r11
0x1800152ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ef  mov     edi, eax
0x1800152f1  test    eax, eax
0x1800152f3  js      loc_180015A8E
0x1800152f9  mov     r12, [rbp+390h+var_3B8]
0x1800152fd  add     r12, 3
0x180015301  add     r12, rbx
0x180015304  mov     edi, [rsp+490h+var_45C]
0x180015308  and     r12, 0FFFFFFFFFFFFFFFCh
0x18001530c  mov     rbx, [rsp+490h+var_430]
0x180015311  lea     rdx, __ImageBase
0x180015318  mov     r11, [rsp+490h+var_450]
0x18001531d  mov     r10, [rsp+490h+var_448]
0x180015322  mov     r8, [rsp+490h+var_428]
0x180015327  mov     rsi, [rsi]
0x18001532a  mov     [rsp+490h+var_440], rsi
0x18001532f  test    rsi, rsi
0x180015332  jz      short loc_180015339
0x180015334  cmp     rsi, r8
0x180015337  jnz     short loc_18001539C
0x180015339  mov     rax, [rbp+390h+var_3C8]
0x18001533d  sub     r12, [rax+10h]
0x180015341  mov     [rax], r12
0x180015344  cmp     r12, [rax+8]
0x180015348  ja      short def_180015737; jumptable 0000000180015737 default case, cases 3,4,6,11
  ... truncated ...
```
