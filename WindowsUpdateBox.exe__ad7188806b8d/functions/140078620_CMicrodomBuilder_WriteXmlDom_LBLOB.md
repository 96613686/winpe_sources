# CMicrodomBuilder::WriteXmlDom(_LBLOB *)

- ea: `0x140078620`
- end: `0x1400790ef`
- name: `?WriteXmlDom@CMicrodomBuilder@@AEAAJPEAU_LBLOB@@@Z`
- size: `2767`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400754c0`

## callees

- `0x14006261c`
- `0x140066b40`
- `0x140066c80`
- `0x140072764`
- `0x14007395c`
- `0x140073c34`
- `0x140074c68`
- `0x14007511c`
- `0x1400764b0`
- `0x140078620`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1400789db`
- `ntdll!RtlRaiseStatus` at `0x140078fa3`
- `ntdll!RtlRaiseStatus` at `0x14007903b`
- `ntdll!RtlRaiseStatus` at `0x1400789db`
- `ntdll!RtlRaiseStatus` at `0x140078fa3`
- `ntdll!RtlRaiseStatus` at `0x14007903b`

## string_xrefs

- `0x1400787cb`: `onecore\base\xml\udom_builder.cpp`
- `0x14007883f`: `onecore\base\xml\udom_builder.cpp`
- `0x1400788ba`: `onecore\base\xml\udom_builder.cpp`
- `0x140078fb0`: `onecore\base\xml\udom_builder.cpp`
- `0x140079048`: `onecore\base\xml\udom_builder.cpp`
- `0x14007907a`: `onecore\base\xml\udom_builder.cpp`
- `0x140078fc7`: `CMicrodomBuilder::WriteXmlDom`
- `0x1400788d1`: `CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::WriteXmlDom(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // r12
  _DWORD *v4; // rsi
  int v5; // r15d
  __int64 v6; // rdi
  _QWORD *v7; // rbx
  CMicrodomBuilder *v8; // r14
  __int64 v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // r8
  int StringId; // eax
  unsigned int v16; // eax
  __int64 (__fastcall *v17)(CMicrodomBuilder *, _DWORD *, __int64 *, __int64 *); // r13
  __int64 **v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rdi
  int v21; // eax
  __int64 **v22; // rcx
  __int64 *i; // rax
  unsigned int v24; // r14d
  __int64 *v25; // rsi
  __int64 *v26; // rdx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned __int64 v32; // rdi
  int v33; // r9d
  int v34; // r10d
  unsigned __int64 v35; // r8
  __int64 **v36; // rdx
  __int64 *j; // rax
  __int64 *v38; // rax
  unsigned __int64 v39; // r15
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // r14
  unsigned __int64 v42; // rbx
  bool v43; // cf
  _DWORD *v44; // r14
  int v45; // eax
  int v46; // r9d
  unsigned __int64 v47; // r8
  __int64 **v48; // rdx
  __int64 *k; // rax
  __int16 *v50; // rax
  __int16 v51; // ax
  int v52; // ebx
  unsigned __int64 v53; // rdi
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  __int64 v59; // rcx
  CMicrodomBuilder *v60; // rcx
  unsigned __int64 v61; // rdi
  int v62; // ecx
  int v63; // eax
  int v64; // edx
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  struct _LBLOB *v71; // rax
  unsigned __int64 v72; // rdi
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // r8
  unsigned __int64 v77; // [rsp+30h] [rbp-D0h]
  __int16 v78; // [rsp+40h] [rbp-C0h]
  int v79; // [rsp+44h] [rbp-BCh]
  int v80; // [rsp+4Ch] [rbp-B4h]
  int v81; // [rsp+54h] [rbp-ACh]
  __int16 v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+60h] [rbp-A0h]
  unsigned int v84; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v85; // [rsp+68h] [rbp-98h] BYREF
  int v86; // [rsp+6Ch] [rbp-94h]
  int v87; // [rsp+70h] [rbp-90h] BYREF
  int v88; // [rsp+74h] [rbp-8Ch] BYREF
  int v89; // [rsp+78h] [rbp-88h] BYREF
  int v90; // [rsp+7Ch] [rbp-84h] BYREF
  int v91; // [rsp+80h] [rbp-80h] BYREF
  CMicrodomBuilder *v92; // [rsp+88h] [rbp-78h]
  _DWORD v93[2]; // [rsp+90h] [rbp-70h] BYREF
  int v94; // [rsp+98h] [rbp-68h]
  int v95; // [rsp+9Ch] [rbp-64h]
  _DWORD v96[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v97; // [rsp+B0h] [rbp-50h] BYREF
  __int64 **v98; // [rsp+B8h] [rbp-48h]
  struct _LBLOB *v99; // [rsp+C0h] [rbp-40h]
  _QWORD v100[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v101[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v102[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v103[4]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v104[4]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v105[4]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v106; // [rsp+188h] [rbp+88h] BYREF
  __int64 v107; // [rsp+190h] [rbp+90h] BYREF
  __int64 v108; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE *v109; // [rsp+1A8h] [rbp+A8h]
  __int64 v110; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v111; // [rsp+1B8h] [rbp+B8h]
  __m128i v112; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v113[240]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v114[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE *v115; // [rsp+2C8h] [rbp+1C8h]
  __int64 v116; // [rsp+2D0h] [rbp+1D0h]
  unsigned __int64 v117; // [rsp+2D8h] [rbp+1D8h]
  __m128i si128; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v119[240]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v120[8]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE *v121; // [rsp+3E8h] [rbp+2E8h]
  __m128i v122; // [rsp+3F0h] [rbp+2F0h]
  __m128i v123; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v124[240]; // [rsp+410h] [rbp+310h] BYREF

  v2 = v119;
  v3 = *((_QWORD *)a2 + 2) + *((_QWORD *)a2 + 1);
  v4 = (_DWORD *)(*((_QWORD *)a2 + 2) + *(_QWORD *)a2);
  v98 = (__int64 **)((char *)this + 1264);
  v86 = -1;
  v5 = -1;
  v79 = -1;
  v83 = -1;
  v115 = v119;
  v117 = 7;
  v6 = 7;
  v99 = a2;
  v92 = this;
  v78 = 0;
  v84 = 0;
  v85 = 0;
  v116 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v2);
    v2 += 4;
    --v6;
  }
  while ( v6 );
  v7 = v124;
  v8 = v92;
  v9 = 7;
  v121 = v124;
  v122 = _mm_load_si128((const __m128i *)&_xmm);
  v123 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v7);
    v7 += 4;
    --v9;
  }
  while ( v9 );
  v109 = v113;
  v10 = v113;
  v110 = 0;
  v111 = 7;
  v11 = 7;
  v112 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v10);
    v10 += 4;
    --v11;
  }
  while ( v11 );
  if ( v115 == v119 )
  {
    BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
      (unsigned int *)&v87,
      v117,
      5u,
      &si128.m128i_u64[1]);
    v13 = v87;
    if ( v87 >= 0 )
      goto LABEL_11;
  }
  else
  {
    __debugbreak();
    v13 = -1073741595;
  }
  v100[3] = "m_StoredTable.Initialize()";
  v100[0] = "onecore\\base\\xml\\udom_builder.cpp";
  v100[2] = 178;
  v100[1] = "CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize";
  RtlReportErrorOrigination(v100, v12, (unsigned int)v13);
  if ( v13 < 0 )
    goto LABEL_126;
LABEL_11:
  if ( v121 == v124 )
  {
    BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
      (unsigned int *)&v88,
      v122.m128i_u64[1],
      5u,
      &v123.m128i_u64[1]);
    v13 = v88;
    if ( v88 >= 0 )
      goto LABEL_15;
  }
  else
  {
    __debugbreak();
    v13 = -1073741595;
  }
  v101[2] = 178;
  v101[0] = "onecore\\base\\xml\\udom_builder.cpp";
  v101[1] = "CMicrodomBuilder::CFourStringIdTable<unsigned short>::Initialize";
  v101[3] = "m_StoredTable.Initialize()";
  RtlReportErrorOrigination(v101, v12, (unsigned int)v13);
  if ( v13 < 0 )
    goto LABEL_126;
LABEL_15:
  if ( v109 != v113 )
  {
    __debugbreak();
    v13 = -1073741595;
    goto LABEL_18;
  }
  BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
    (unsigned int *)&v89,
    v111,
    5u,
    &v112.m128i_u64[1]);
  v13 = v89;
  if ( v89 < 0 )
  {
LABEL_18:
    v102[2] = 178;
    v102[0] = "onecore\\base\\xml\\udom_builder.cpp";
    v102[1] = "CMicrodomBuilder::CFourStringIdTable<struct _MICRODOM_XML_ATTDEF const *>::Initialize";
    v102[3] = "m_StoredTable.Initialize()";
    RtlReportErrorOrigination(v102, v12, (unsigned int)v13);
    if ( v13 < 0 )
      goto LABEL_126;
  }
  StringId = CMicrodomBuilder::FindStringId(v8, (const struct _LUTF8_STRING *)qword_140084908, &v84);
  if ( StringId < 0
    || (StringId = CMicrodomBuilder::FindStringId(v8, (const struct _LUTF8_STRING *)qword_1400848C0, &v85), StringId < 0) )
  {
LABEL_20:
    v13 = StringId;
    goto LABEL_126;
  }
  if ( (unsigned __int64)(v3 - (_QWORD)v4) < 0x14 )
    goto LABEL_35;
  *v4 = 1816421453;
  v4[2] = *((_DWORD *)v8 + 324);
  v16 = *((_DWORD *)v8 + 324);
  if ( v16 > 0xFF )
  {
    if ( v16 > 0xFFFF )
    {
      v4[1] = 3;
      v17 = (__int64 (__fastcall *)(CMicrodomBuilder *, _DWORD *, __int64 *, __int64 *))CMicrodomBuilder::WriteDomElementIndicies<unsigned long>;
    }
    else
    {
      v4[1] = 2;
      v17 = (__int64 (__fastcall *)(CMicrodomBuilder *, _DWORD *, __int64 *, __int64 *))CMicrodomBuilder::WriteDomElementIndicies<unsigned short>;
    }
  }
  else
  {
    v4[1] = 1;
    v17 = (__int64 (__fastcall *)(CMicrodomBuilder *, _DWORD *, __int64 *, __int64 *))CMicrodomBuilder::WriteDomElementIndicies<unsigned char>;
  }
  v18 = (__int64 **)((char *)v8 + 1264);
  v19 = *((_QWORD *)v8 + 158);
  v20 = ((unsigned __int64)v4 + 23) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( (CMicrodomBuilder *)v19 == (CMicrodomBuilder *)((char *)v8 + 1264) || !v19 || *(_WORD *)(v19 + 114) != 14 )
    goto LABEL_35;
  v21 = *(_DWORD *)(v19 + 72);
  v22 = (__int64 **)(v19 + 88);
  v4[4] = v21;
  for ( i = *v22; ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)v22 )
      goto LABEL_35;
    if ( !*((_WORD *)i + 33) )
      break;
  }
  v24 = v84;
  v4[3] = *((_DWORD *)i + 6);
  v25 = *v18;
  while ( 1 )
  {
    if ( !v25 || v25 == (__int64 *)v18 )
    {
      v71 = v99;
      v72 = v20 - *((_QWORD *)v99 + 2);
      *(_QWORD *)v99 = v72;
      if ( v72 <= *((_QWORD *)v71 + 1) )
      {
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
          &v108,
          v18,
          0);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
          v120,
          v73,
          v74);
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
          v114,
          v75,
          v76);
        return 0;
      }
LABEL_35:
      RtlRaiseStatus(-1073741595);
    }
    v26 = v25 + 14;
    v27 = *((unsigned __int16 *)v25 + 57);
    if ( v27 > 7 )
      break;
    if ( v27 == 7 )
    {
      ++v78;
LABEL_97:
      v5 = v79;
      goto LABEL_122;
    }
    if ( *((_WORD *)v25 + 57) )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
        if ( v3 - v20 < 0x14 )
          goto LABEL_35;
        StringId = CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence(
                     (CMicrodomBuilder::CNamespaceNameExistenceCheck *)v120,
                     *((_DWORD *)v25 + 30),
                     *((_DWORD *)v25 + 31));
        if ( StringId < 0 )
          goto LABEL_20;
        *(_BYTE *)v20 = 2;
        *(_DWORD *)(v20 + 12) = *((_DWORD *)v25 + 31);
        *(_DWORD *)(v20 + 8) = *((_DWORD *)v25 + 30);
        *(_DWORD *)(v20 + 4) = *((_DWORD *)v25 + 29);
        *(_DWORD *)(v20 + 16) = *((_DWORD *)v25 + 32);
        if ( !*((_BYTE *)v25 + 132) )
          *(_BYTE *)v20 = 34;
        v33 = *((_DWORD *)v25 + 29);
        v34 = *((_DWORD *)v25 + 31);
        v35 = (unsigned int)(8261505 * v83 + v34 + 65599 * v33 + 780587199 * v5);
        v36 = (__int64 **)&v109[32 * (v35 % v111)];
        for ( j = *v36; j && j != (__int64 *)v36; j = (__int64 *)*j )
        {
          if ( __PAIR64__(v5, v35) == j[4]
            && v83 == *((_DWORD *)j + 10)
            && v33 == *((_DWORD *)j + 11)
            && v34 == *((_DWORD *)j + 12) )
          {
            v38 = j + 7;
            if ( v38 && *(_DWORD *)(*v38 + 12) == 1 )
              *(_BYTE *)v20 |= 0x10u;
            break;
          }
        }
        if ( (*(_DWORD *)(v20 + 8) == v24 || *(_DWORD *)(v20 + 8) == -1 && v86 == v24) && *(_DWORD *)(v20 + 12) == v85 )
          *(_BYTE *)v20 |= 0x10u;
        v32 = v20 + 23;
        goto LABEL_74;
      }
      v29 = v28 - 1;
      if ( !v29 || (v30 = v29 - 1) == 0 )
      {
        v5 = -1;
        v79 = -1;
        v83 = -1;
        goto LABEL_122;
      }
      v31 = v30 - 1;
      if ( v31 )
      {
        if ( v31 != 1 || v3 - v20 < 8 )
          goto LABEL_35;
        *(_BYTE *)v20 = 19;
      }
      else
      {
        if ( v3 - v20 < 8 )
          goto LABEL_35;
        *(_BYTE *)v20 = 3;
      }
      goto LABEL_49;
    }
    v39 = *((unsigned int *)v25 + 19);
    v40 = v39;
    v41 = v25[13] - v39;
    v106 = 0;
    v42 = v41;
    if ( v39 >= v41 )
    {
      v40 = v41;
      v42 = v39;
    }
    if ( v40 )
      v42 |= v40 << 22;
    CMicrodomBuilder::CNamespaceNameExistenceCheck::Clear((CMicrodomBuilder::CNamespaceNameExistenceCheck *)v120);
    v43 = v39 < v41;
    v44 = (_DWORD *)((v20 + 27) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_BYTE *)v20 = v43 ? -127 : 1;
    v5 = *((_DWORD *)v25 + 29);
    *(_DWORD *)(v20 + 12) = v5;
    v45 = *((_DWORD *)v25 + 30);
    *(_DWORD *)(v20 + 16) = v45;
    v46 = *((_DWORD *)v25 + 31);
    v86 = v45;
    *(_DWORD *)(v20 + 20) = v46;
    v79 = v5;
    v83 = v46;
    v47 = (unsigned int)(8261505 * v46 + 780587199 * v5 - 65600);
    v48 = (__int64 **)&v115[32 * (v47 % v117)];
    for ( k = *v48; k && k != (__int64 *)v48; k = (__int64 *)*k )
    {
      if ( __PAIR64__(v5, v47) == k[4]
        && v46 == *((_DWORD *)k + 10)
        && *((_DWORD *)k + 11) == -1
        && *((_DWORD *)k + 12) == -1 )
      {
        v50 = (__int16 *)k + 26;
        if ( v50 )
        {
          v51 = *v50;
          goto LABEL_90;
        }
        break;
      }
    }
    v51 = -1;
LABEL_90:
    *(_WORD *)(v20 + 8) = v51;
    if ( v42 >= 0x400000 )
    {
      if ( (unsigned __int64)(v3 - (_QWORD)v44) < 4 )
        RtlRaiseStatus(-1073741595);
      *v44 = v42 & 0x3FFFFF;
      v52 = *(_DWORD *)(v20 + 4) ^ (v42 >> 22);
      *(_BYTE *)(v20 + 1) |= 1u;
      *(_DWORD *)(v20 + 4) ^= v52 & 0x3FFFFF;
      v44 = (_DWORD *)(((unsigned __int64)v44 + 7) & 0xFFFFFFFFFFFFFFFCuLL);
    }
    else
    {
      *(_DWORD *)(v20 + 4) ^= (*(_DWORD *)(v20 + 4) ^ v42) & 0x3FFFFF;
      *(_BYTE *)(v20 + 1) &= ~1u;
    }
    StringId = v17(v92, v44, &v106, v25);
    v14 = 0;
    if ( StringId < 0 )
      goto LABEL_20;
    v53 = (unsigned __int64)v44 + v106 + 3;
    v24 = v84;
    v20 = v53 & 0xFFFFFFFFFFFFFFFCuLL;
LABEL_122:
    v25 = (__int64 *)*v25;
    v18 = v98;
  }
  v54 = v27 - 8;
  if ( v54 )
  {
    v55 = v54 - 1;
    if ( v55 )
    {
      v56 = v55 - 1;
      if ( v56 )
      {
        v57 = v56 - 2;
        if ( v57 )
        {
          v58 = v57 - 1;
          if ( !v58 )
          {
            if ( v3 - v20 < 8 )
              goto LABEL_35;
            *(_BYTE *)v20 = 6;
LABEL_49:
            *(_DWORD *)(v20 + 4) = *((_DWORD *)v25 + 29);
            v32 = v20 + 11;
LABEL_74:
            v20 = v32 & 0xFFFFFFFFFFFFFFFCuLL;
            goto LABEL_122;
          }
          if ( v58 != 1 )
            goto LABEL_35;
          v107 = 0;
          if ( v3 - v20 < 4 )
            RtlRaiseStatus(-1073741595);
          LOWORD(v59) = 0;
          if ( (unsigned __int64)v25[13] > 0xFFFF )
          {
            v80 = -1073741675;
            LOBYTE(v81) = -107;
          }
          else
          {
            v59 = *((unsigned __int16 *)v25 + 52);
            if ( v25[13] == v59 )
            {
              v80 = 0;
              LOBYTE(v81) = 0;
            }
            else
            {
              v80 = -1073741595;
              LOBYTE(v81) = -27;
            }
          }
          *(_WORD *)((char *)&v81 + 1) = *(_WORD *)((char *)&v80 + 1);
          HIBYTE(v81) = HIBYTE(v80);
          v13 = v81;
          *(_WORD *)(v20 + 2) = v59;
          if ( v81 < 0 )
          {
            v103[2] = 2661;
            v103[0] = "onecore\\base\\xml\\udom_builder.cpp";
            v65 = v103;
            v103[1] = "CMicrodomBuilder::WriteXmlDom";
            v103[3] = "BUCL::Rtl::ConvertInteger(pObject->m_cChildren, pDocument->usChildNodes)";
            goto LABEL_125;
          }
          v60 = v92;
          *(_BYTE *)v20 = 7;
          v61 = (v20 + 7) & 0xFFFFFFFFFFFFFFFCuLL;
          StringId = v17(v60, (_DWORD *)v61, &v107, v25);
          v14 = 0;
          if ( StringId < 0 )
            goto LABEL_20;
          v20 = (v107 + 3 + v61) & 0xFFFFFFFFFFFFFFFCuLL;
        }
        else if ( v25[8] )
        {
          if ( v3 - v20 < 0xC )
            goto LABEL_35;
          *(_BYTE *)v20 = 5;
          *(_DWORD *)(v20 + 4) = *((_DWORD *)v25 + 29);
          *(_DWORD *)(v20 + 8) = *((_DWORD *)v25 + 30);
          v32 = v20 + 15;
          goto LABEL_74;
        }
      }
      else
      {
        v62 = *((_DWORD *)v25 + 30);
        v94 = *((_DWORD *)v25 + 29);
        v97 = v25 + 14;
        v93[0] = -1;
        v93[1] = -1;
        v95 = v62;
        BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<_MICRODOM_XML_ATTDEF const *>::CTableTraits>::CBucketChain::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,_MICRODOM_XML_ATTDEF const *>(
          (__int64 **)&v109[32 * ((unsigned int)(65599 * v94 + v62 - 788848704) % v111)],
          &v90,
          &v108,
          v93,
          &v97,
          65599 * v94 + v62 - 788848704,
          v77);
        v13 = v90;
        if ( v90 < 0 )
        {
          v104[2] = 267;
          v104[0] = "onecore\\base\\xml\\udom_builder.cpp";
          v65 = v104;
          v104[1] = "CMicrodomBuilder::CNamespaceNamePrefixToAttDef::Insert";
          v104[3] = "m_StoredTable.FindOrInsertIfNotPresent(Pair, pAttDef)";
          goto LABEL_125;
        }
        ++v78;
      }
    }
    goto LABEL_122;
  }
  v63 = *((_DWORD *)v25 + 30);
  v64 = *((_DWORD *)v25 + 29);
  v96[2] = -1;
  v96[3] = -1;
  v96[1] = v63;
  v96[0] = v64;
  v82 = v78;
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::CBucketChain::FindOrInsertIfNotPresent<CMicrodomBuilder::FourStringIdPair,unsigned short>(
    (_DWORD)v115 + 32 * ((unsigned int)(8261505 * v63 - 65600 + 780587199 * v64) % v117),
    (unsigned int)&v91,
    (unsigned int)v114,
    (unsigned int)v96,
    (__int64)&v82,
    8261505 * v63 - 65600 + 780587199 * v64);
  v13 = v91;
  if ( v91 >= 0 )
  {
    ++v78;
    goto LABEL_97;
  }
  v105[2] = 297;
  v105[0] = "onecore\\base\\xml\\udom_builder.cpp";
  v65 = v105;
  v105[1] = "CMicrodomBuilder::CElementNameToAttributeListTable::MaybeInsert";
  v105[3] = "m_StoredTable.FindOrInsertIfNotPresent(Pair, Value, 0, pfExisted)";
LABEL_125:
  RtlReportErrorOrigination(v65, v26, (unsigned int)v13);
LABEL_126:
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    &v108,
    v12,
    v14);
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    v120,
    v66,
    v67);
  BUCL::HashTable::CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>::~CTable<CMicrodomBuilder::CFourStringIdTable<unsigned short>::CTableTraits>(
    v114,
    v68,
    v69);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140078620  mov     [rsp-8+arg_10], rbx
0x140078625  push    rbp
0x140078626  push    rsi
0x140078627  push    rdi
0x140078628  push    r12
0x14007862a  push    r13
0x14007862c  push    r14
0x14007862e  push    r15
0x140078630  lea     rbp, [rsp-410h]
0x140078638  sub     rsp, 510h
0x14007863f  mov     rax, cs:__security_cookie
0x140078646  xor     rax, rsp
0x140078649  mov     [rbp+440h+var_40], rax
0x140078650  mov     r12, [rdx+8]
0x140078654  lea     rax, [rcx+4F0h]
0x14007865b  mov     rsi, [rdx]
0x14007865e  lea     rbx, [rbp+440h+var_250]
0x140078665  add     r12, [rdx+10h]
0x140078669  xor     r13d, r13d
0x14007866c  add     rsi, [rdx+10h]
0x140078670  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x140078678  mov     [rbp+440h+var_488], rax
0x14007867c  or      eax, 0FFFFFFFFh
0x14007867f  mov     [rsp+540h+var_4D4], eax
0x140078683  lea     r14d, [r13+1]
0x140078687  mov     r15d, eax
0x14007868a  mov     [rsp+540h+var_4FC], eax
0x14007868e  mov     [rsp+540h+var_4E0], eax
0x140078692  lea     rax, [rbp+440h+var_250]
0x140078699  mov     [rbp+440h+var_278], rax
0x1400786a0  lea     eax, [r13+7]
0x1400786a4  mov     [rbp+440h+var_268], rax
0x1400786ab  mov     edi, eax
0x1400786ad  mov     [rbp+440h+var_480], rdx
0x1400786b1  mov     [rbp+440h+var_4B8], rcx
0x1400786b5  mov     [rsp+540h+var_500], r13w
0x1400786bb  mov     [rsp+540h+var_4DC], r13d
0x1400786c0  mov     [rsp+540h+var_4D8], r13d
0x1400786c5  mov     [rbp+440h+var_270], r13
0x1400786cc  movdqa  [rbp+440h+var_260], xmm0
0x1400786d4  mov     rcx, rbx
0x1400786d7  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1400786dc  add     rbx, 20h ; ' '
0x1400786e0  sub     rdi, r14
0x1400786e3  jnz     short loc_1400786D4
0x1400786e5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1400786ed  lea     rax, [rbp+440h+var_130]
0x1400786f4  movdqa  xmm1, cs:__xmm@00000000000000230000000000000000
0x1400786fc  lea     rbx, [rbp+440h+var_130]
0x140078703  mov     r14, [rbp+440h+var_4B8]
0x140078707  mov     edi, 7
0x14007870c  mov     [rbp+440h+var_158], rax
0x140078713  movdqa  [rbp+440h+var_150], xmm0
0x14007871b  movdqa  [rbp+440h+var_140], xmm1
0x140078723  mov     rcx, rbx
0x140078726  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x14007872b  add     rbx, 20h ; ' '
0x14007872f  sub     rdi, 1
0x140078733  jnz     short loc_140078723
0x140078735  movdqa  xmm0, cs:__xmm@00000000000000230000000000000000
0x14007873d  lea     rax, [rbp+440h+var_370]
0x140078744  mov     [rbp+440h+var_398], rax
0x14007874b  lea     rbx, [rbp+440h+var_370]
0x140078752  lea     eax, [rdi+7]
0x140078755  mov     [rbp+440h+var_390], r13
0x14007875c  mov     [rbp+440h+var_388], rax
0x140078763  mov     edi, eax
0x140078765  movdqa  [rbp+440h+var_380], xmm0
0x14007876d  mov     rcx, rbx
0x140078770  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x140078775  add     rbx, 20h ; ' '
0x140078779  sub     rdi, 1
0x14007877d  jnz     short loc_14007876D
0x14007877f  lea     rax, [rbp+440h+var_250]
0x140078786  lea     rcx, aMStoredtableIn; "m_StoredTable.Initialize()"
0x14007878d  cmp     [rbp+440h+var_278], rax
0x140078794  jz      short loc_14007879E
0x140078796  int     3; Trap to Debugger
0x140078797  mov     ebx, 0C00000E5h
0x14007879c  jmp     short loc_1400787CB
0x14007879e  mov     rdx, [rbp+440h+var_268]
0x1400787a5  lea     r9, [rbp+440h+var_260+8]
0x1400787ac  mov     r8d, 5
0x1400787b2  lea     rcx, [rsp+540h+var_4D0]
0x1400787b7  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x1400787bc  mov     ebx, [rsp+540h+var_4D0]
0x1400787c0  test    ebx, ebx
0x1400787c2  jns     short loc_140078801
0x1400787c4  lea     rcx, aMStoredtableIn; "m_StoredTable.Initialize()"
0x1400787cb  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400787d2  mov     [rbp+440h+var_460], rcx
0x1400787d6  mov     [rbp+440h+var_478], rax
0x1400787da  lea     rcx, [rbp+440h+var_478]
0x1400787de  lea     rax, aCmicrodombuild_2; "CMicrodomBuilder::CFourStringIdTable<un"...
0x1400787e5  mov     [rbp+440h+var_468], 0B2h
0x1400787ed  mov     r8d, ebx
0x1400787f0  mov     [rbp+440h+var_470], rax
0x1400787f4  call    RtlReportErrorOrigination
0x1400787f9  test    ebx, ebx
0x1400787fb  js      loc_140078FE5
0x140078801  lea     rax, [rbp+440h+var_130]
0x140078808  cmp     [rbp+440h+var_158], rax
0x14007880f  jz      short loc_140078819
0x140078811  int     3; Trap to Debugger
0x140078812  mov     ebx, 0C00000E5h
0x140078817  jmp     short loc_14007883F
0x140078819  mov     rdx, qword ptr [rbp+440h+var_150+8]
0x140078820  lea     r9, [rbp+440h+var_140+8]
0x140078827  mov     r8d, 5
0x14007882d  lea     rcx, [rsp+540h+var_4CC]
0x140078832  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x140078837  mov     ebx, [rsp+540h+var_4CC]
0x14007883b  test    ebx, ebx
0x14007883d  jns     short loc_14007887C
0x14007883f  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x140078846  mov     [rbp+440h+var_448], 0B2h
0x14007884e  mov     [rbp+440h+var_458], rax
0x140078852  lea     rcx, [rbp+440h+var_458]
0x140078856  lea     rax, aCmicrodombuild_2; "CMicrodomBuilder::CFourStringIdTable<un"...
0x14007885d  mov     r8d, ebx
0x140078860  mov     [rbp+440h+var_450], rax
0x140078864  lea     rax, aMStoredtableIn; "m_StoredTable.Initialize()"
0x14007886b  mov     [rbp+440h+var_440], rax
0x14007886f  call    RtlReportErrorOrigination
0x140078874  test    ebx, ebx
0x140078876  js      loc_140078FE5
0x14007887c  lea     rax, [rbp+440h+var_370]
0x140078883  cmp     [rbp+440h+var_398], rax
0x14007888a  jz      short loc_140078894
0x14007888c  int     3; Trap to Debugger
0x14007888d  mov     ebx, 0C00000E5h
0x140078892  jmp     short loc_1400788BA
0x140078894  mov     rdx, [rbp+440h+var_388]
0x14007889b  lea     r9, [rbp+440h+var_380+8]
0x1400788a2  mov     r8d, 5
0x1400788a8  lea     rcx, [rsp+540h+var_4C8]
0x1400788ad  call    ??$Multiply@VCCallDisposition@Rtl@BUCL@@_K@Implementation@BUCL@@YA?A_P_K0AEA_K@Z
0x1400788b2  mov     ebx, [rsp+540h+var_4C8]
0x1400788b6  test    ebx, ebx
0x1400788b8  jns     short loc_1400788F7
0x1400788ba  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_builder.cpp"
0x1400788c1  mov     [rbp+440h+var_428], 0B2h
0x1400788c9  mov     [rbp+440h+var_438], rax
0x1400788cd  lea     rcx, [rbp+440h+var_438]
0x1400788d1  lea     rax, aCmicrodombuild_7; "CMicrodomBuilder::CFourStringIdTable<st"...
0x1400788d8  mov     r8d, ebx
0x1400788db  mov     [rbp+440h+var_430], rax
0x1400788df  lea     rax, aMStoredtableIn; "m_StoredTable.Initialize()"
0x1400788e6  mov     [rbp+440h+var_420], rax
0x1400788ea  call    RtlReportErrorOrigination
0x1400788ef  test    ebx, ebx
0x1400788f1  js      loc_140078FE5
0x1400788f7  lea     r8, [rsp+540h+var_4DC]; unsigned int *
0x1400788fc  mov     rcx, r14; this
0x1400788ff  lea     rdx, qword_140084908; struct _LUTF8_STRING *
0x140078906  call    ?FindStringId@CMicrodomBuilder@@AEAAJAEBU_LUTF8_STRING@@PEAK@Z; CMicrodomBuilder::FindStringId(_LUTF8_STRING const &,ulong *)
0x14007890b  test    eax, eax
0x14007890d  jns     short loc_140078916
0x14007890f  mov     ebx, eax
0x140078911  jmp     loc_140078FE5
0x140078916  lea     r8, [rsp+540h+var_4D8]; unsigned int *
0x14007891b  mov     rcx, r14; this
0x14007891e  lea     rdx, qword_1400848C0; struct _LUTF8_STRING *
0x140078925  call    ?FindStringId@CMicrodomBuilder@@AEAAJAEBU_LUTF8_STRING@@PEAK@Z; CMicrodomBuilder::FindStringId(_LUTF8_STRING const &,ulong *)
0x14007892a  test    eax, eax
0x14007892c  js      short loc_14007890F
0x14007892e  mov     rax, r12
0x140078931  sub     rax, rsi
0x140078934  cmp     rax, 14h
0x140078938  jb      loc_1400789D6
0x14007893e  mov     dword ptr [rsi], 6C44644Dh
0x140078944  mov     ebx, 1
0x140078949  mov     eax, [r14+510h]
0x140078950  mov     [rsi+8], eax
0x140078953  mov     eax, [r14+510h]
0x14007895a  cmp     eax, 0FFh
0x14007895f  ja      short loc_14007896D
0x140078961  mov     [rsi+4], ebx
0x140078964  lea     r13, ??$WriteDomElementIndicies@E@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<uchar>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x14007896b  jmp     short loc_140078992
0x14007896d  cmp     eax, 0FFFFh
0x140078972  ja      short loc_140078984
0x140078974  mov     dword ptr [rsi+4], 2
0x14007897b  lea     r13, ??$WriteDomElementIndicies@G@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ushort>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x140078982  jmp     short loc_140078992
0x140078984  mov     dword ptr [rsi+4], 3
0x14007898b  lea     r13, ??$WriteDomElementIndicies@K@CMicrodomBuilder@@AEAAJPEAXAEA_KPEBVCXmlStreamObject@0@@Z; CMicrodomBuilder::WriteDomElementIndicies<ulong>(void *,unsigned __int64 &,CMicrodomBuilder::CXmlStreamObject const *)
0x140078992  lea     rdx, [r14+4F0h]
0x140078999  mov     rcx, [rdx]
0x14007899c  lea     rdi, [rsi+17h]
0x1400789a0  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400789a4  cmp     rcx, rdx
0x1400789a7  jz      short loc_1400789D6
0x1400789a9  xor     r8d, r8d
0x1400789ac  test    rcx, rcx
0x1400789af  jz      short loc_1400789D6
0x1400789b1  cmp     word ptr [rcx+72h], 0Eh
0x1400789b6  jnz     short loc_1400789D6
0x1400789b8  mov     eax, [rcx+48h]
0x1400789bb  add     rcx, 58h ; 'X'
0x1400789bf  mov     [rsi+10h], eax
0x1400789c2  mov     rax, [rcx]
0x1400789c5  jmp     short loc_1400789D1
0x1400789c7  cmp     [rax+42h], r8w
0x1400789cc  jz      short loc_1400789E8
0x1400789ce  mov     rax, [rax]
0x1400789d1  cmp     rax, rcx
0x1400789d4  jnz     short loc_1400789C7
0x1400789d6  mov     ecx, 0C00000E5h; Status
0x1400789db  call    cs:__imp_RtlRaiseStatus
0x1400789e2  nop     dword ptr [rax+rax+00h]
0x1400789e7  int     3; Trap to Debugger
0x1400789e8  mov     eax, [rax+18h]
0x1400789eb  mov     r14d, [rsp+540h+var_4DC]
0x1400789f0  mov     [rsi+0Ch], eax
0x1400789f3  mov     rsi, [rdx]
0x1400789f6  test    rsi, rsi
0x1400789f9  jz      loc_1400790AF
0x1400789ff  cmp     rsi, rdx
0x140078a02  jz      loc_1400790AF
0x140078a08  lea     rdx, [rsi+70h]
0x140078a0c  movzx   ecx, word ptr [rdx+2]
0x140078a10  cmp     ecx, 7
0x140078a13  ja      loc_140078D15
0x140078a19  jz      loc_140078D06
0x140078a1f  test    ecx, ecx
0x140078a21  jz      loc_140078B91
0x140078a27  sub     ecx, 1
0x140078a2a  jz      short loc_140078A86
0x140078a2c  sub     ecx, 1
0x140078a2f  jz      short loc_140078A73
0x140078a31  sub     ecx, 1
0x140078a34  jz      short loc_140078A73
0x140078a36  sub     ecx, 1
0x140078a39  jz      short loc_140078A5E
0x140078a3b  cmp     ecx, 1
0x140078a3e  jnz     short loc_1400789D6
0x140078a40  mov     rax, r12
0x140078a43  sub     rax, rdi
0x140078a46  cmp     rax, 8
0x140078a4a  jb      short loc_1400789D6
0x140078a4c  mov     byte ptr [rdi], 13h
0x140078a4f  mov     eax, [rsi+74h]
0x140078a52  mov     [rdi+4], eax
0x140078a55  add     rdi, 0Bh
0x140078a59  jmp     loc_140078B88
0x140078a5e  mov     rax, r12
0x140078a61  sub     rax, rdi
0x140078a64  cmp     rax, 8
0x140078a68  jb      loc_1400789D6
0x140078a6e  mov     byte ptr [rdi], 3
0x140078a71  jmp     short loc_140078A4F
0x140078a73  or      eax, 0FFFFFFFFh
0x140078a76  mov     r15d, eax
0x140078a79  mov     [rsp+540h+var_4FC], eax
0x140078a7d  mov     [rsp+540h+var_4E0], eax
0x140078a81  jmp     loc_140078F92
0x140078a86  mov     rax, r12
0x140078a89  sub     rax, rdi
0x140078a8c  cmp     rax, 14h
0x140078a90  jb      loc_1400789D6
0x140078a96  mov     r8d, [rsi+7Ch]; unsigned int
0x140078a9a  lea     rcx, [rbp+440h+var_160]; this
0x140078aa1  mov     edx, [rsi+78h]; unsigned int
0x140078aa4  call    ?AddAndCheckExistence@CNamespaceNameExistenceCheck@CMicrodomBuilder@@QEAAJKK@Z; CMicrodomBuilder::CNamespaceNameExistenceCheck::AddAndCheckExistence(ulong,ulong)
0x140078aa9  test    eax, eax
0x140078aab  js      loc_14007890F
0x140078ab1  mov     byte ptr [rdi], 2
0x140078ab4  mov     eax, [rsi+7Ch]
0x140078ab7  mov     [rdi+0Ch], eax
0x140078aba  mov     eax, [rsi+78h]
0x140078abd  mov     [rdi+8], eax
0x140078ac0  mov     eax, [rsi+74h]
0x140078ac3  mov     [rdi+4], eax
0x140078ac6  mov     eax, [rsi+80h]
0x140078acc  mov     [rdi+10h], eax
0x140078acf  cmp     byte ptr [rsi+84h], 0
0x140078ad6  jnz     short loc_140078ADB
0x140078ad8  mov     byte ptr [rdi], 22h ; '"'
0x140078adb  mov     r9d, [rsi+74h]
0x140078adf  xor     edx, edx
0x140078ae1  mov     r11d, [rsp+540h+var_4E0]
0x140078ae6  mov     r10d, [rsi+7Ch]
0x140078aea  imul    eax, r11d, 7E0F81h
0x140078af1  imul    ecx, r9d, 1003Fh
0x140078af8  imul    r8d, r15d, 2E86D0BFh
0x140078aff  add     ecx, r10d
0x140078b02  add     ecx, eax
0x140078b04  add     r8d, ecx
0x140078b07  mov     eax, r8d
0x140078b0a  div     [rbp+440h+var_388]
0x140078b11  shl     rdx, 5
0x140078b15  add     rdx, [rbp+440h+var_398]
0x140078b1c  mov     rax, [rdx]
0x140078b1f  test    rax, rax
0x140078b22  jz      short loc_140078B62
0x140078b24  cmp     rax, rdx
0x140078b27  jz      short loc_140078B62
0x140078b29  cmp     [rax+20h], r8d
0x140078b2d  jnz     short loc_140078B47
  ... truncated ...
```
