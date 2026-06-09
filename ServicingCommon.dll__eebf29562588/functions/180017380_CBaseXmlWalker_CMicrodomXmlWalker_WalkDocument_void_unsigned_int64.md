# CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument(void *,unsigned __int64)

- ea: `0x180017380`
- end: `0x180018974`
- name: `?WalkDocument@?$CBaseXmlWalker@VCMicrodomXmlWalker@@@@QEAAJPEAX_K@Z`
- size: `5620`
- prototype: `__int64 __fastcall(struct CXmlCursor *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015630`

## callees

- `0x180002564`
- `0x1800031e0`
- `0x1800032b0`
- `0x18000337c`
- `0x180003550`
- `0x180006420`
- `0x18000a8d0`
- `0x18000a8e0`
- `0x18000fd04`
- `0x180010418`
- `0x180010c40`
- `0x180015bf8`
- `0x1800164b0`
- `0x180017380`
- `0x18001a350`
- `0x18001e850`
- `0x18001fd10`
- `0x18001fd90`
- `0x180022eb0`
- `0x180022f08`
- `0x1800293a0`
- `0x180061ef0`
- `0x180062230`
- `0x1800623ec`
- `0x180099cb0`
- `0x18009a070`
- `0x18009a700`
- `0x1800a0020`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180017701`
- `ntdll!RtlAllocateHeap` at `0x180017911`
- `ntdll!RtlAllocateHeap` at `0x180017adf`
- `ntdll!RtlAllocateHeap` at `0x180018150`
- `ntdll!RtlAllocateHeap` at `0x1800182c1`
- `ntdll!RtlAllocateHeap` at `0x1800184ba`
- `ntdll!RtlAllocateHeap` at `0x180017701`
- `ntdll!RtlAllocateHeap` at `0x180017911`
- `ntdll!RtlAllocateHeap` at `0x180017adf`
- `ntdll!RtlAllocateHeap` at `0x180018150`
- `ntdll!RtlAllocateHeap` at `0x1800182c1`
- `ntdll!RtlAllocateHeap` at `0x1800184ba`

## string_xrefs

- `0x1800173f4`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180017657`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180017695`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180018616`: `onecore\base\xml\udom_builder.cpp`
- `0x180018643`: `onecore\base\xml\udom_builder.cpp`
- `0x180018693`: `onecore\base\xml\udom_builder.cpp`
- `0x1800186c0`: `onecore\base\xml\udom_builder.cpp`
- `0x1800186ed`: `onecore\base\xml\udom_builder.cpp`
- `0x18001871e`: `onecore\base\xml\udom_builder.cpp`
- `0x18001882c`: `onecore\base\xml\udom_builder.cpp`
- `0x1800188be`: `onecore\base\xml\udom_builder.cpp`
- `0x180018848`: `CMicrodomXmlWalker::XmlError`
- `0x180018733`: `CMicrodomBuilder::ConsumeComment`
- `0x18001873f`: `NewComment = this->AllocateStreamObject()`
- `0x18001766c`: `CXmlNamespaceManager::Initialize`
- `0x180017678`: `RtlNsInitialize(this, Comparison, pvCompareContextParam, Alloc)`
- `0x180017409`: `CXmlLogicalState::Initialize`
- `0x180017415`: `RtlXmlInitializeNextLogicalThing(this, &Init)`
- `0x180018875`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x180018891`: `CXmlCursor::Next`
- `0x1800188a5`: `RtlXmlNextLogicalThingEx( &m_State, &m_Namespaces, &m_CurrentThing, &m_AttributeList, skipXmlDeclDetect )`
- `0x1800176aa`: `CRtlGrowingList<struct _XMLDOC_ATTRIBUTE,50,4>::Initialize`

## pseudocode

```c
__int64 __fastcall CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument(struct CXmlCursor *a1, __int64 a2, __int64 a3)
{
  char *v3; // rsi
  int LogicalThing; // ebx
  const char *v6; // rax
  unsigned int v7; // edx
  unsigned int v8; // r8d
  void *v9; // r9
  __int64 v10; // rdi
  __int64 *v11; // rdx
  __int64 v12; // rbx
  __int64 result; // rax
  PVOID Heap; // rsi
  __int64 *v15; // rax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // ecx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  _DWORD *v21; // rdi
  int v22; // eax
  unsigned int v23; // ebx
  CMicrodomBuilder *v24; // rcx
  _QWORD *v25; // rdi
  __int64 *v26; // rdx
  __int64 v27; // rbx
  PVOID v28; // rsi
  __int64 *v29; // rax
  __int64 v30; // rdx
  CMicrodomBuilder *v31; // r12
  __int64 *v32; // rdx
  __int64 v33; // rbx
  PVOID v34; // rdi
  __int64 *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  bool v38; // zf
  __int64 v39; // rdx
  signed int v40; // ebx
  size_t v41; // rdi
  void *v42; // r14
  unsigned __int64 v43; // rbx
  char **v44; // rsi
  char *i; // r15
  char *v46; // rdx
  char *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  void *v50; // rbx
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // r14
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // xmm2_8
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // rax
  __int64 v58; // rdx
  unsigned __int64 v59; // rcx
  __int64 v60; // rax
  bool v61; // cf
  size_t v62; // rax
  unsigned __int64 *v63; // rax
  unsigned __int64 *v64; // rsi
  unsigned __int64 v65; // rbx
  _QWORD *j; // rdi
  unsigned __int64 *v67; // r12
  _QWORD *v68; // rdx
  __int64 v69; // r10
  CMicrodomBuilder *v70; // rax
  __int64 v71; // r9
  unsigned __int64 **v72; // rcx
  unsigned __int64 *v73; // r8
  _QWORD *v74; // rsi
  __int64 v75; // rdi
  _QWORD *k; // rbx
  _DWORD *v77; // rcx
  char v78; // al
  __int64 v79; // rdi
  _QWORD *v80; // rdi
  __int64 *v81; // rdx
  __int64 v82; // rbx
  PVOID v83; // rsi
  __int64 *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rsi
  __int64 *v87; // rdx
  __int64 v88; // rbx
  PVOID v89; // rdi
  __int64 *v90; // rax
  __int64 v91; // rax
  __int64 v92; // rdi
  _QWORD *v93; // rdx
  int v94; // ecx
  __int64 v95; // rcx
  _QWORD *v96; // r8
  __int64 v97; // rsi
  __int64 *v98; // rdx
  __int64 v99; // rbx
  PVOID v100; // rdi
  __int64 *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rdi
  unsigned int v104; // ecx
  unsigned int v105; // eax
  int v106; // ecx
  __int64 v107; // rdx
  _QWORD *v108; // r8
  const char *v109; // rax
  const char *v110; // rax
  void *v111; // rbx
  __int128 v112; // xmm0
  int v113; // ebx
  __int64 v114; // rdx
  __int64 v115; // r8
  int v116; // [rsp+20h] [rbp-E0h]
  char v117; // [rsp+40h] [rbp-C0h]
  const char *v118; // [rsp+48h] [rbp-B8h] BYREF
  const char *v119; // [rsp+50h] [rbp-B0h]
  __int64 v120; // [rsp+58h] [rbp-A8h]
  const char *v121; // [rsp+60h] [rbp-A0h]
  __int128 v122; // [rsp+68h] [rbp-98h] BYREF
  __int64 v123; // [rsp+78h] [rbp-88h]
  const char *v124; // [rsp+80h] [rbp-80h]
  _QWORD *v125; // [rsp+88h] [rbp-78h]
  CMicrodomBuilder *v126; // [rsp+90h] [rbp-70h]
  size_t Size[2]; // [rsp+98h] [rbp-68h] BYREF
  void *Buf1; // [rsp+A8h] [rbp-58h]
  __int64 v129; // [rsp+B0h] [rbp-50h]
  __int64 v130; // [rsp+B8h] [rbp-48h]
  __int64 v131; // [rsp+C0h] [rbp-40h]
  char *v132; // [rsp+C8h] [rbp-38h]
  __int64 v133; // [rsp+D0h] [rbp-30h]
  __int64 v134; // [rsp+D8h] [rbp-28h]
  __int64 v135; // [rsp+E0h] [rbp-20h]
  __int128 v136; // [rsp+E8h] [rbp-18h]
  __int128 v137; // [rsp+F8h] [rbp-8h]
  __int128 v138; // [rsp+108h] [rbp+8h]
  __int128 v139; // [rsp+120h] [rbp+20h] BYREF
  void *v140; // [rsp+130h] [rbp+30h]

  v131 = 88;
  v134 = a2;
  v3 = (char *)a1 + 9352;
  v136 = 0;
  v132 = (char *)a1 + 9352;
  v137 = 0;
  v133 = 64;
  v138 = 0;
  v135 = a3;
  LOBYTE(v136) = 1;
  LogicalThing = RtlXmlInitializeNextLogicalThing(a1);
  if ( LogicalThing < 0 )
  {
    v123 = 150;
    *(_QWORD *)&v122 = "onecore\\base\\xml\\udom_xmlwalker.h";
    *((_QWORD *)&v122 + 1) = "CXmlLogicalState::Initialize";
    v6 = "RtlXmlInitializeNextLogicalThing(this, &Init)";
LABEL_21:
    v124 = v6;
    RtlReportErrorOrigination(&v122, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)LogicalThing);
    return (unsigned int)LogicalThing;
  }
  *((_BYTE *)a1 + 2224) = 1;
  memset((char *)a1 + 2232, 0, 0x4C0u);
  if ( a1 == (struct CXmlCursor *)-2240LL )
  {
    LogicalThing = RtlXmlReportErrorFunction(-1073741811, v7, v8, v9);
    if ( LogicalThing < 0 )
      goto LABEL_18;
  }
  else
  {
    *((_QWORD *)a1 + 281) = 32;
    *((_DWORD *)a1 + 564) = 50;
    *((_OWORD *)a1 + 142) = *(_OWORD *)v3;
    *((_QWORD *)a1 + 286) = *((_QWORD *)v3 + 2);
    if ( a1 != (struct CXmlCursor *)-3288LL )
    {
      *((_QWORD *)a1 + 283) = (char *)a1 + 3288;
      *((_DWORD *)a1 + 565) = 5;
      *((_DWORD *)a1 + 561) = 5;
    }
  }
  if ( a1 == (struct CXmlCursor *)-2320LL )
  {
    LogicalThing = RtlXmlReportErrorFunction(-1073741811, v7, v8, v9);
    if ( LogicalThing >= 0 )
      goto LABEL_10;
LABEL_18:
    v123 = 105;
    *(_QWORD *)&v122 = "onecore\\base\\xml\\udom_xmlwalker.h";
    *((_QWORD *)&v122 + 1) = "CXmlNamespaceManager::Initialize";
    v6 = "RtlNsInitialize(this, Comparison, pvCompareContextParam, Alloc)";
    goto LABEL_21;
  }
  *((_QWORD *)a1 + 290) = 0;
  *(_QWORD *)((char *)a1 + 2340) = 0;
  *(_QWORD *)((char *)a1 + 2348) = 0;
  *(_QWORD *)((char *)a1 + 2356) = 0;
  *(_QWORD *)((char *)a1 + 2364) = 0;
  *(_QWORD *)((char *)a1 + 2372) = 0;
  *(_QWORD *)((char *)a1 + 2380) = 0;
  *((_DWORD *)a1 + 597) = 0;
  *((_QWORD *)a1 + 291) = 176;
  *((_DWORD *)a1 + 584) = 50;
  *((_OWORD *)a1 + 147) = *(_OWORD *)v3;
  *((_QWORD *)a1 + 296) = *((_QWORD *)v3 + 2);
  if ( a1 != (struct CXmlCursor *)-2408LL )
  {
    *((_QWORD *)a1 + 293) = (char *)a1 + 2408;
    *((_DWORD *)a1 + 585) = 5;
    *((_DWORD *)a1 + 581) = 5;
  }
LABEL_10:
  *((_QWORD *)a1 + 300) = a1;
  *((_QWORD *)a1 + 299) = CXmlCursor::LocalCompareExtents;
  *((_DWORD *)a1 + 578) = 0;
  *((_BYTE *)a1 + 3448) = 1;
  if ( a1 == (struct CXmlCursor *)-3456LL )
  {
    LogicalThing = RtlXmlReportErrorFunction(-1073741811, v7, v8, v9);
    if ( LogicalThing < 0 )
    {
      v123 = 45;
      *(_QWORD *)&v122 = "onecore\\base\\xml\\udom_xmlwalker.h";
      *((_QWORD *)&v122 + 1) = "CRtlGrowingList<struct _XMLDOC_ATTRIBUTE,50,4>::Initialize";
      v6 = "RtlInitializeGrowingList( this, sizeof(TStoredObject), m_ulElementsPerChunk, (PVOID)m_InternalBuffer, sizeof("
           "m_InternalBuffer), AllocatorParam )";
      goto LABEL_21;
    }
  }
  else
  {
    *((_QWORD *)a1 + 432) = 0;
    *(_QWORD *)((char *)a1 + 3476) = 0;
    *(_QWORD *)((char *)a1 + 3484) = 0;
    *(_QWORD *)((char *)a1 + 3492) = 0;
    *(_QWORD *)((char *)a1 + 3500) = 0;
    *(_QWORD *)((char *)a1 + 3508) = 0;
    *(_QWORD *)((char *)a1 + 3516) = 0;
    *((_DWORD *)a1 + 881) = 0;
    *((_QWORD *)a1 + 433) = 112;
    *((_DWORD *)a1 + 868) = 4;
    *((_OWORD *)a1 + 218) = *(_OWORD *)v3;
    *((_QWORD *)a1 + 438) = *((_QWORD *)v3 + 2);
    if ( a1 != (struct CXmlCursor *)-3528LL )
    {
      *((_QWORD *)a1 + 435) = (char *)a1 + 3528;
      *((_DWORD *)a1 + 869) = 50;
      *((_DWORD *)a1 + 865) = 50;
    }
  }
  memset((char *)a1 + 9128, 0, 0xE0u);
  *((_BYTE *)a1 + 9376) = *((_DWORD *)a1 + 12) == 5;
  v10 = *((_QWORD *)a1 + 1173);
  v11 = *(__int64 **)(v10 + 1248);
  if ( v11 )
  {
    if ( *v11 != v11[1] )
      goto LABEL_29;
    v12 = 2 * *v11;
    if ( (unsigned __int64)(288 * *v11) <= 0x400000 )
    {
      if ( !v12 )
        v12 = 1;
    }
    else
    {
      v12 = 29127;
    }
  }
  else
  {
    v12 = 455;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v12);
  if ( !Heap || (v15 = (__int64 *)operator new(0x20u), (v11 = v15) == 0) )
  {
LABEL_238:
    v120 = 1134;
    v118 = "onecore\\base\\xml\\udom_builder.cpp";
    v119 = "CMicrodomBuilder::StartDocument";
    v109 = "NewDocument = this->AllocateStreamObject()";
    goto LABEL_239;
  }
  *v15 = v12;
  v15[1] = 0;
  v15[2] = (__int64)Heap;
  v15[3] = 0;
  v15[3] = *(_QWORD *)(v10 + 1248);
  *(_QWORD *)(v10 + 1248) = v15;
LABEL_29:
  v16 = 144 * v11[1] + v11[2];
  if ( v16 )
  {
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 56) = v16 + 48;
    *(_QWORD *)(v16 + 48) = v16 + 48;
    *(_QWORD *)(v16 + 96) = v16 + 88;
    *(_QWORD *)(v16 + 88) = v16 + 88;
    *(_QWORD *)v16 = 0;
    *(_QWORD *)(v16 + 8) = 0;
    *(_QWORD *)(v16 + 40) = 0;
    *(_QWORD *)(v16 + 24) = 0;
    *(_QWORD *)(v16 + 32) = 0;
    *(_QWORD *)(v16 + 64) = 0;
    *(_QWORD *)(v16 + 72) = 0;
    *(_QWORD *)(v16 + 80) = 0;
    *(_QWORD *)(v16 + 104) = 0;
  }
  ++*(_QWORD *)(*(_QWORD *)(v10 + 1248) + 8LL);
  if ( !v16 )
    goto LABEL_238;
  v17 = *(_DWORD *)(v10 + 1296);
  *(_DWORD *)(v10 + 1296) = v17 + 1;
  *(_DWORD *)(v16 + 72) = v17;
  v18 = 1;
  *(_DWORD *)(v16 + 80) = 1;
  *(_DWORD *)(v16 + 84) = 1;
  if ( *(_DWORD *)(v10 + 1300) > 1u )
    v18 = *(_DWORD *)(v10 + 1300);
  *(_DWORD *)(v10 + 1300) = v18;
  *(_DWORD *)(v16 + 112) = 917508;
  if ( *(_QWORD *)(v10 + 1256) )
  {
LABEL_240:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  v19 = (_QWORD *)(v10 + 1264);
  *(_QWORD *)(v16 + 64) = 0;
  v20 = *(_QWORD *)(v10 + 1272);
  *(_QWORD *)(v10 + 1256) = v16;
  *(_QWORD *)(v16 + 8) = v20;
  *(_QWORD *)v16 = v10 + 1264;
  **(_QWORD **)(v10 + 1272) = v16;
  *(_QWORD *)(v10 + 1272) = v16;
  *(_QWORD *)(v16 + 16) = v10 + 1264;
LABEL_36:
  ++v19[3];
LABEL_37:
  v21 = (_DWORD *)((char *)a1 + 9128);
  while ( 2 )
  {
    if ( *v21 == 1 )
      return 0;
    LOBYTE(v116) = 0;
    v22 = RtlXmlNextLogicalThingEx(
            a1,
            (struct CXmlCursor *)((char *)a1 + 2232),
            (char *)a1 + 9128,
            (struct CXmlCursor *)((char *)a1 + 3456));
    v23 = v22;
    if ( v22 < 0 )
    {
      v120 = 64;
      v118 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
      v119 = "CXmlCursor::Next";
      v121 = "RtlXmlNextLogicalThingEx( &m_State, &m_Namespaces, &m_CurrentThing, &m_AttributeList, skipXmlDeclDetect )";
      RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v22);
      return v23;
    }
    switch ( *v21 )
    {
      case 0:
        if ( !*((_QWORD *)a1 + 1175) )
          goto LABEL_235;
        v111 = 0;
        Buf1 = 0;
        *(_OWORD *)Size = 0;
        v140 = 0;
        v139 = 0;
        if ( !*((_QWORD *)a1 + 1149) )
          goto LABEL_233;
        v112 = *((_OWORD *)a1 + 574);
        v123 = *((_QWORD *)a1 + 1150);
        v122 = v112;
        v113 = CXmlCursor::DecodeExtent(a1, &v122, Size, &v139, v116);
        if ( v113 >= 0 )
        {
          v111 = Buf1;
LABEL_233:
          (***((void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, int, __int128 *))a1 + 1175))(
            *((_QWORD *)a1 + 1175),
            *((unsigned int *)a1 + 2302),
            *((unsigned int *)a1 + 2303),
            *((unsigned int *)a1 + 2301),
            -1073700733,
            &v139);
          if ( v111 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v111, v114, v115);
LABEL_235:
          v120 = 882;
          v118 = "onecore\\base\\xml\\udom_builder.cpp";
          v121 = 0;
          v119 = "CMicrodomXmlWalker::XmlError";
          RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221266563LL);
          return 3221266563LL;
        }
        else
        {
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(Size);
          return (unsigned int)v113;
        }
      case 3:
        v24 = (CMicrodomBuilder *)*((_QWORD *)a1 + 1173);
        *((_BYTE *)a1 + 9392) = 1;
        result = CMicrodomBuilder::StartElement(v24, a1);
        if ( (int)result < 0 )
          return result;
        continue;
      case 4:
        v25 = (_QWORD *)*((_QWORD *)a1 + 1173);
        if ( !v25[157] )
          goto LABEL_240;
        v26 = (__int64 *)v25[156];
        if ( v26 )
        {
          if ( *v26 != v26[1] )
            goto LABEL_55;
          v27 = 2 * *v26;
          if ( (unsigned __int64)(288 * *v26) <= 0x400000 )
          {
            if ( !v27 )
              v27 = 1;
          }
          else
          {
            v27 = 29127;
          }
        }
        else
        {
          v27 = 455;
        }
        v28 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v27);
        if ( !v28 )
          goto LABEL_219;
        v29 = (__int64 *)operator new(0x20u);
        v26 = v29;
        if ( !v29 )
          goto LABEL_219;
        v29[2] = (__int64)v28;
        *v29 = v27;
        v29[1] = 0;
        v29[3] = 0;
        v29[3] = v25[156];
        v25[156] = v29;
LABEL_55:
        v30 = 144 * v26[1] + v26[2];
        if ( v30 )
        {
          *(_QWORD *)(v30 + 16) = 0;
          *(_QWORD *)(v30 + 56) = v30 + 48;
          *(_QWORD *)(v30 + 48) = v30 + 48;
          *(_QWORD *)(v30 + 96) = v30 + 88;
          *(_QWORD *)(v30 + 88) = v30 + 88;
          *(_QWORD *)v30 = 0;
          *(_QWORD *)(v30 + 8) = 0;
          *(_QWORD *)(v30 + 40) = 0;
          *(_QWORD *)(v30 + 24) = 0;
          *(_QWORD *)(v30 + 32) = 0;
          *(_QWORD *)(v30 + 64) = 0;
          *(_QWORD *)(v30 + 72) = 0;
          *(_QWORD *)(v30 + 80) = 0;
          *(_QWORD *)(v30 + 104) = 0;
        }
        ++*(_QWORD *)(v25[156] + 8LL);
        if ( !v30 )
        {
LABEL_219:
          v120 = 1564;
          v118 = "onecore\\base\\xml\\udom_builder.cpp";
          v119 = "CMicrodomBuilder::EndElement";
          v109 = "TheEndElement = this->AllocateStreamObject()";
          goto LABEL_239;
        }
        *(_QWORD *)(v30 + 64) = v25[157];
        *(_DWORD *)(v30 + 112) = 131076;
        *(_QWORD *)(v30 + 8) = v25[159];
        *(_QWORD *)v30 = v25 + 158;
        *(_QWORD *)v25[159] = v30;
        v25[159] = v30;
        *(_QWORD *)(v30 + 16) = v25 + 158;
        ++v25[161];
        v25[157] = *(_QWORD *)(v25[157] + 64LL);
        goto LABEL_37;
      case 5:
        v86 = *((_QWORD *)a1 + 1173);
        v87 = *(__int64 **)(v86 + 1248);
        if ( v87 )
        {
          if ( *v87 != v87[1] )
            goto LABEL_181;
          v88 = 2 * *v87;
          if ( (unsigned __int64)(288 * *v87) <= 0x400000 )
          {
            if ( !v88 )
              v88 = 1;
          }
          else
          {
            v88 = 29127;
          }
        }
        else
        {
          v88 = 455;
        }
        v89 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v88);
        if ( !v89 )
          goto LABEL_223;
        v90 = (__int64 *)operator new(0x20u);
        v87 = v90;
        if ( !v90 )
          goto LABEL_223;
        *v90 = v88;
        v90[1] = 0;
        v90[2] = (__int64)v89;
        v90[3] = 0;
        v90[3] = *(_QWORD *)(v86 + 1248);
        *(_QWORD *)(v86 + 1248) = v90;
LABEL_181:
        v91 = v87[1];
        v38 = v87[2] + 144 * v91 == 0;
        v92 = v87[2] + 144 * v91;
        v93 = (_QWORD *)(v92 + 48);
        if ( !v38 )
        {
          *(_QWORD *)(v92 + 16) = 0;
          *(_QWORD *)(v92 + 96) = v92 + 88;
          *(_QWORD *)(v92 + 88) = v92 + 88;
          *(_QWORD *)v92 = 0;
          *(_QWORD *)(v92 + 8) = 0;
          *(_QWORD *)(v92 + 40) = 0;
          *(_QWORD *)(v92 + 24) = 0;
          *(_QWORD *)(v92 + 32) = 0;
          *(_QWORD *)(v92 + 64) = 0;
          *(_QWORD *)(v92 + 72) = 0;
          *(_QWORD *)(v92 + 80) = 0;
          *(_QWORD *)(v92 + 104) = 0;
          *(_QWORD *)(v92 + 56) = v93;
          *v93 = v93;
        }
        ++*(_QWORD *)(*(_QWORD *)(v86 + 1248) + 8LL);
        if ( !v92 )
        {
LABEL_223:
          v120 = 2072;
          v118 = "onecore\\base\\xml\\udom_builder.cpp";
          v119 = "CMicrodomBuilder::ConsumeProcessingInstruction";
          v110 = "NewProcessingInstruction = this->AllocateStreamObject()";
          goto LABEL_226;
        }
        *(_QWORD *)(v92 + 64) = *(_QWORD *)(v86 + 1256);
        *(_DWORD *)(v92 + 112) = 786444;
        if ( *(_QWORD *)(v86 + 1256) )
        {
          v94 = *(_DWORD *)(v86 + 1296);
          *(_DWORD *)(v86 + 1296) = v94 + 1;
          *(_DWORD *)(v92 + 72) = v94;
          v95 = *(_QWORD *)(v86 + 1256);
          v96 = *(_QWORD **)(v95 + 96);
          if ( *v96 != v95 + 88 )
            goto LABEL_224;
          *v93 = v95 + 88;
          *(_QWORD *)(v92 + 56) = v96;
          *v96 = v93;
          *(_QWORD *)(v95 + 96) = v93;
          ++*(_QWORD *)(v95 + 104);
        }
        v40 = CMicrodomBuilder::DecodeAndAddString(
                (CMicrodomBuilder *)v86,
                a1,
                (struct CXmlCursor *)((char *)a1 + 9184),
                (unsigned int *)(v92 + 116));
        if ( v40 < 0 )
          return (unsigned int)v40;
        if ( *((_QWORD *)a1 + 1152) )
        {
          v40 = CMicrodomBuilder::DecodeAndAddString(
                  (CMicrodomBuilder *)v86,
                  a1,
                  (struct CXmlCursor *)((char *)a1 + 9208),
                  (unsigned int *)(v92 + 120));
          if ( v40 < 0 )
            return (unsigned int)v40;
        }
        else
        {
          *(_DWORD *)(v92 + 120) = -1;
        }
        *(_QWORD *)(v92 + 8) = *(_QWORD *)(v86 + 1272);
        *(_QWORD *)v92 = v86 + 1264;
        **(_QWORD **)(v86 + 1272) = v92;
        *(_QWORD *)(v86 + 1272) = v92;
        *(_QWORD *)(v92 + 16) = v86 + 1264;
        ++*(_QWORD *)(v86 + 1288);
        goto LABEL_37;
      case 7:
        result = CMicrodomBuilder::ConsumePCData(*((CMicrodomBuilder **)a1 + 1173), a1);
        if ( (int)result < 0 )
          return result;
        continue;
      case 8:
        result = CMicrodomBuilder::ConsumeCData(*((CMicrodomBuilder **)a1 + 1173), a1);
        if ( (int)result < 0 )
          return result;
        continue;
      case 9:
        result = CMicrodomBuilder::ConsumeEntityDecl(*((CMicrodomBuilder **)a1 + 1173), a1);
        if ( (int)result < 0 )
          return result;
        continue;
      case 0xA:
        v31 = (CMicrodomBuilder *)*((_QWORD *)a1 + 1173);
        v126 = v31;
        v32 = (__int64 *)*((_QWORD *)v31 + 156);
        if ( v32 )
        {
          if ( *v32 != v32[1] )
            goto LABEL_76;
          v33 = 2 * *v32;
          if ( (unsigned __int64)(288 * *v32) <= 0x400000 )
          {
            if ( !v33 )
              v33 = 1;
          }
          else
          {
            v33 = 29127;
          }
        }
        else
        {
          v33 = 455;
        }
        v34 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v33);
        if ( !v34 )
          goto LABEL_221;
        v35 = (__int64 *)operator new(0x20u);
        v32 = v35;
        if ( !v35 )
          goto LABEL_221;
        *v35 = v33;
        v35[1] = 0;
        v35[2] = (__int64)v34;
        v35[3] = 0;
        v35[3] = *((_QWORD *)v31 + 156);
        *((_QWORD *)v31 + 156) = v35;
LABEL_76:
        v36 = v32[1];
        v37 = v32[2];
        v38 = 144 * v36 + v37 == 0;
        v39 = 144 * v36 + v37;
        v130 = v39;
        if ( !v38 )
        {
          *(_QWORD *)(v39 + 16) = 0;
          *(_QWORD *)(v39 + 56) = v39 + 48;
          *(_QWORD *)(v39 + 48) = v39 + 48;
          *(_QWORD *)(v39 + 96) = v39 + 88;
          *(_QWORD *)(v39 + 88) = v39 + 88;
          *(_QWORD *)v39 = 0;
          *(_QWORD *)(v39 + 8) = 0;
          *(_QWORD *)(v39 + 40) = 0;
          *(_QWORD *)(v39 + 24) = 0;
          *(_QWORD *)(v39 + 32) = 0;
          *(_QWORD *)(v39 + 64) = 0;
          *(_QWORD *)(v39 + 72) = 0;
          *(_QWORD *)(v39 + 80) = 0;
          *(_QWORD *)(v39 + 104) = 0;
        }
        ++*(_QWORD *)(*((_QWORD *)v31 + 156) + 8LL);
        if ( !v39 )
        {
LABEL_221:
          v120 = 1790;
          v118 = "onecore\\base\\xml\\udom_builder.cpp";
          v119 = "CMicrodomBuilder::StartAttlist";
          v110 = "NewAttlist = this->AllocateStreamObject()";
          goto LABEL_226;
        }
        *(_QWORD *)(v39 + 64) = *((_QWORD *)v31 + 157);
        *(_DWORD *)(v39 + 112) = 524300;
        *(_DWORD *)(v39 + 120) = -1;
        Buf1 = 0;
        *(_OWORD *)Size = 0;
        v40 = CXmlCursor::DecodeExtent(a1, (char *)a1 + 9208, (char *)v31 + 1584, Size, v116);
        if ( v40 < 0 )
          return (unsigned int)v40;
        v41 = Size[0];
        v42 = Buf1;
        v43 = MurmurHash3_x64_64(Buf1, Size[0], Size[0]);
        v125 = (_QWORD *)((char *)v31 + 8);
        v44 = (char **)(*((_QWORD *)v31 + 2) + 32 * (v43 % *((_QWORD *)v31 + 4)));
        for ( i = *v44; i && i != (char *)v44; i = *(char **)i )
        {
          if ( *((_QWORD *)i + 4) == v43 && v41 == *((_QWORD *)i + 5) && !memcmp(v42, *((const void **)i + 7), v41) )
          {
            v117 = 1;
            v46 = (char *)v31 + 8;
            goto LABEL_95;
          }
        }
        v47 = (char *)operator new(0x48u);
        i = v47;
        if ( !v47 )
          return (unsigned int)-1073741801;
        *((_QWORD *)v47 + 4) = v43;
        *((_QWORD *)v47 + 2) = 0;
        *(_QWORD *)v47 = 0;
        v50 = 0;
        *((_QWORD *)v47 + 1) = 0;
        *((_QWORD *)v47 + 3) = (char *)v31 + 8;
        *(_OWORD *)(v47 + 40) = 0;
        *((_QWORD *)v47 + 7) = 0;
        *((_DWORD *)v47 + 16) = -1;
        v140 = 0;
        v139 = 0u;
        if ( v41 > Size[1] )
          goto LABEL_92;
        if ( v42 )
        {
          if ( v41 )
          {
            v40 = RtlAllocateLBlob(v41, &v139);
            if ( v40 < 0 )
            {
              if ( v140 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v140, v53, v54);
              goto LABEL_143;
            }
            v50 = v140;
            memmove(v140, v42, v41);
            *(_QWORD *)&v139 = v41;
          }
        }
        else if ( v41 )
        {
LABEL_92:
          v120 = 139;
          v118 = "onecore\\base\\lstring\\lutf8_string.cpp";
          v119 = "RtlDuplicateLUtf8String";
          v121 = "RtlIsLUtf8StringValid(Source)";
          RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
          v40 = -1073741811;
LABEL_143:
          BUCL::HashTable::CTable<CMicrodomBuilder::CIntermediateStringTableTraits>::CBucket::`scalar deleting destructor'(i);
          return (unsigned int)v40;
        }
        v55 = *((_QWORD *)i + 7);
        v122 = *(_OWORD *)(i + 40);
        *(_OWORD *)(i + 40) = v139;
        *((_QWORD *)i + 7) = v50;
        if ( v55 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v55, v48, v49);
        v46 = (char *)v31 + 8;
        *((_DWORD *)i + 16) = *(_DWORD *)v31;
        *((_QWORD *)i + 1) = v44[1];
        *(_QWORD *)i = v44;
        v117 = 0;
        *(_QWORD *)v44[1] = i;
        v44[1] = i;
        *((_QWORD *)i + 2) = v44;
        ++v44[3];
        ++*((_QWORD *)v31 + 5);
LABEL_95:
        v51 = *((_QWORD *)v46 + 4);
        if ( v51 <= *((_QWORD *)v46 + 5) )
          goto LABEL_142;
        if ( v51 == -1 )
        {
          v52 = -1;
        }
        else if ( HIDWORD(v51) )
        {
          if ( ((2 * HIDWORD(v51)) & 0xFFFFFFFF00000000uLL) != 0 )
            goto LABEL_139;
          v56 = HIDWORD(v51) << 33;
          v57 = 2LL * (unsigned int)v51;
          v52 = v56 + v57;
          v40 = v56 + v57 < v57 ? 0xC0000095 : 0;
          if ( v56 + v57 < v57 )
            goto LABEL_140;
        }
        else
        {
          v52 = 2LL * (unsigned int)v51;
        }
        if ( v52 == *((_QWORD *)v46 + 4) )
          goto LABEL_141;
        if ( HIDWORD(v52) )
        {
          if ( ((5 * HIDWORD(v52)) & 0xFFFFFFFF00000000uLL) != 0 )
          {
LABEL_139:
            v40 = -1073741675;
            goto LABEL_140;
          }
          v58 = 0x500000000LL * HIDWORD(v52);
          v59 = 5LL * (unsigned int)v52;
          v129 = v58 + v59;
          v40 = v58 + v59 < v59 ? 0xC0000095 : 0;
          if ( v58 + v59 < v59 )
            goto LABEL_140;
        }
        else
        {
          v129 = 5LL * (unsigned int)v52;
        }
        v60 = 32 * v52;
        if ( !is_mul_ok(v52, 0x20u) )
          v60 = -1;
        v61 = __CFADD__(v60, 8);
        v62 = v60 + 8;
        if ( v61 )
          v62 = -1;
        v63 = (unsigned __int64 *)operator new(v62);
        v64 = v63;
        if ( v63 )
        {
          *v63 = v52;
          v65 = v52;
          for ( j = v63 + 1; v65; --v65 )
          {
            BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(j);
            j += 4;
          }
          v67 = v64 + 1;
          if ( v64 != (unsigned __int64 *)-8LL )
          {
            v68 = v125;
            v69 = 0;
            if ( v125[3] )
            {
              v70 = v126;
              do
              {
                v71 = *((_QWORD *)v70 + 2) + 32 * v69;
                while ( 1 )
                {
                  v72 = *(unsigned __int64 ***)v71;
                  if ( *(_QWORD *)v71 == v71 )
                    break;
                  if ( v72 && v72[2] == (unsigned __int64 *)v71 )
                  {
                    (*v72)[1] = (unsigned __int64)v72[1];
                    *v72[1] = (unsigned __int64)*v72;
                    v72[2] = 0;
                    --*(_QWORD *)(v71 + 24);
                  }
                  v73 = &v67[4 * ((unsigned __int64)v72[4] % v52)];
                  v72[1] = (unsigned __int64 *)v73[1];
                  *v72 = v73;
                  *(_QWORD *)v73[1] = v72;
                  v73[1] = (unsigned __int64)v72;
                  v72[2] = v73;
                  ++v73[3];
                }
                v70 = v126;
                ++v69;
              }
              while ( v69 != *((_QWORD *)v126 + 4) );
              v68 = v125;
            }
            v74 = (_QWORD *)v68[1];
            if ( v68 + 6 != v74 && v74 )
            {
              v75 = *(v74 - 1);
              for ( k = &v74[4 * v75]; v75; --v75 )
              {
                k -= 4;
                BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::~CBucketChain(k);
              }
              operator delete(v74 - 1);
              v68 = v125;
            }
            v77 = i + 64;
            v68[5] = v129;
            v78 = v117;
            v68[1] = v67;
            v31 = v126;
            v68[3] = v52;
            goto LABEL_145;
          }
        }
        v40 = -1073741801;
LABEL_140:
        if ( v40 < 0 )
          return (unsigned int)v40;
LABEL_141:
        v31 = v126;
LABEL_142:
        v78 = v117;
        v77 = i + 64;
LABEL_145:
        if ( !v78 )
        {
          if ( *(_DWORD *)v31 == -1 )
          {
            v120 = 395;
            v118 = "onecore\\base\\xml\\udom_builder.cpp";
            v119 = "CMicrodomBuilder::AddString";
            v121 = "BUCL::Rtl::Increment(m_NextStringId)";
            RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
            return 3221225621LL;
          }
          ++*(_DWORD *)v31;
        }
        v79 = v130;
        *(_DWORD *)(v130 + 120) = *v77;
        if ( *((_DWORD *)a1 + 2301) )
        {
          v40 = CMicrodomBuilder::DecodeAndAddString(
                  v31,
                  a1,
                  (struct CXmlCursor *)((char *)a1 + 9184),
                  (unsigned int *)(v79 + 116));
          if ( v40 < 0 )
            return (unsigned int)v40;
        }
        else
        {
          *(_DWORD *)(v79 + 116) = -1;
        }
        v19 = (_QWORD *)((char *)v31 + 1264);
        *((_QWORD *)v31 + 157) = v79;
        *(_QWORD *)(v79 + 8) = *((_QWORD *)v31 + 159);
        *(_QWORD *)v79 = (char *)v31 + 1264;
        **((_QWORD **)v31 + 159) = v79;
        *((_QWORD *)v31 + 159) = v79;
        *(_QWORD *)(v79 + 16) = (char *)v31 + 1264;
        goto LABEL_36;
      case 0xB:
        result = CMicrodomBuilder::ConsumeAttdef(*((CMicrodomBuilder **)a1 + 1173), a1);
        if ( (int)result < 0 )
          return result;
        continue;
      case 0xC:
        v80 = (_QWORD *)*((_QWORD *)a1 + 1173);
        v81 = (__int64 *)v80[156];
        if ( v81 )
        {
          if ( *v81 != v81[1] )
            goto LABEL_166;
          v82 = 2 * *v81;
          if ( (unsigned __int64)(288 * *v81) <= 0x400000 )
          {
            if ( !v82 )
              v82 = 1;
          }
          else
          {
            v82 = 29127;
          }
        }
        else
        {
          v82 = 455;
        }
        v83 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v82);
        if ( !v83 )
          goto LABEL_222;
        v84 = (__int64 *)operator new(0x20u);
        v81 = v84;
        if ( !v84 )
          goto LABEL_222;
        v84[2] = (__int64)v83;
        *v84 = v82;
        v84[1] = 0;
        v84[3] = 0;
        v84[3] = v80[156];
        v80[156] = v84;
LABEL_166:
        v85 = 144 * v81[1] + v81[2];
        if ( v85 )
        {
          *(_QWORD *)(v85 + 16) = 0;
          *(_QWORD *)(v85 + 56) = v85 + 48;
          *(_QWORD *)(v85 + 48) = v85 + 48;
          *(_QWORD *)(v85 + 96) = v85 + 88;
          *(_QWORD *)(v85 + 88) = v85 + 88;
          *(_QWORD *)v85 = 0;
          *(_QWORD *)(v85 + 8) = 0;
          *(_QWORD *)(v85 + 40) = 0;
          *(_QWORD *)(v85 + 24) = 0;
          *(_QWORD *)(v85 + 32) = 0;
          *(_QWORD *)(v85 + 64) = 0;
          *(_QWORD *)(v85 + 72) = 0;
          *(_QWORD *)(v85 + 80) = 0;
          *(_QWORD *)(v85 + 104) = 0;
        }
        ++*(_QWORD *)(v80[156] + 8LL);
        if ( !v85 )
        {
LABEL_222:
          v120 = 1992;
          v118 = "onecore\\base\\xml\\udom_builder.cpp";
          v119 = "CMicrodomBuilder::EndAttlist";
          v109 = "NewAttlistClose = this->AllocateStreamObject()";
LABEL_239:
          v121 = v109;
          RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
          return 3221225495LL;
        }
        *(_QWORD *)(v85 + 64) = v80[157];
        *(_DWORD *)(v85 + 112) = 589828;
        v80[157] = *(_QWORD *)(v80[157] + 64LL);
        v19 = v80 + 158;
        *(_QWORD *)(v85 + 8) = v80[159];
        *(_QWORD *)v85 = v80 + 158;
        *(_QWORD *)v80[159] = v85;
        v80[159] = v85;
        *(_QWORD *)(v85 + 16) = v80 + 158;
        goto LABEL_36;
      case 0xD:
        v97 = *((_QWORD *)a1 + 1173);
        v98 = *(__int64 **)(v97 + 1248);
        if ( v98 )
        {
          if ( *v98 != v98[1] )
            goto LABEL_204;
          v99 = 2 * *v98;
          if ( (unsigned __int64)(288 * *v98) <= 0x400000 )
          {
            if ( !v99 )
              v99 = 1;
          }
          else
          {
            v99 = 29127;
          }
        }
        else
        {
          v99 = 455;
        }
        v100 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 144 * v99);
        if ( !v100 )
          goto LABEL_225;
        v101 = (__int64 *)operator new(0x20u);
        v98 = v101;
        if ( !v101 )
          goto LABEL_225;
        *v101 = v99;
        v101[1] = 0;
        v101[2] = (__int64)v100;
        v101[3] = 0;
        v101[3] = *(_QWORD *)(v97 + 1248);
        *(_QWORD *)(v97 + 1248) = v101;
LABEL_204:
        v102 = v98[1];
        v103 = v98[2] + 144 * v102;
        if ( v103 )
          CMicrodomBuilder::CXmlStreamObject::CXmlStreamObject((CMicrodomBuilder::CXmlStreamObject *)(v98[2] + 144 * v102));
        ++*(_QWORD *)(*(_QWORD *)(v97 + 1248) + 8LL);
        if ( v103 )
        {
          *(_QWORD *)(v103 + 64) = *(_QWORD *)(v97 + 1256);
          v104 = *((_DWORD *)a1 + 2302);
          *(_DWORD *)(v103 + 80) = v104;
          v105 = *((_DWORD *)a1 + 2303);
          *(_DWORD *)(v103 + 84) = v105;
          if ( v104 <= v105 )
            v104 = v105;
          if ( *(_DWORD *)(v97 + 1300) > v104 )
            v104 = *(_DWORD *)(v97 + 1300);
          *(_DWORD *)(v97 + 1300) = v104;
          if ( *(_QWORD *)(v97 + 1256) )
          {
            v106 = *(_DWORD *)(v97 + 1296);
            *(_DWORD *)(v97 + 1296) = v106 + 1;
            *(_DWORD *)(v103 + 72) = v106;
            v107 = *(_QWORD *)(v97 + 1256);
            v108 = *(_QWORD **)(v107 + 96);
            if ( *v108 != v107 + 88 )
LABEL_224:
              __fastfail(3u);
            *(_QWORD *)(v103 + 48) = v107 + 88;
            *(_QWORD *)(v103 + 56) = v108;
            *v108 = v103 + 48;
            *(_QWORD *)(v107 + 96) = v103 + 48;
            ++*(_QWORD *)(v107 + 104);
          }
          *(_DWORD *)(v103 + 112) = 851976;
          if ( *((_QWORD *)a1 + 1149) )
          {
            v40 = CMicrodomBuilder::DecodeAndAddString(
                    (CMicrodomBuilder *)v97,
                    a1,
                    (struct CXmlCursor *)((char *)a1 + 9184),
                    (unsigned int *)(v103 + 116));
            if ( v40 < 0 )
              return (unsigned int)v40;
          }
          else
          {
            *(_DWORD *)(v103 + 116) = -1;
          }
          v19 = (_QWORD *)(v97 + 1264);
          *(_QWORD *)(v103 + 8) = *(_QWORD *)(v97 + 1272);
          *(_QWORD *)v103 = v97 + 1264;
          **(_QWORD **)(v97 + 1272) = v103;
          *(_QWORD *)(v97 + 1272) = v103;
          *(_QWORD *)(v103 + 16) = v97 + 1264;
          goto LABEL_36;
        }
LABEL_225:
        v120 = 2019;
        v118 = "onecore\\base\\xml\\udom_builder.cpp";
        v119 = "CMicrodomBuilder::ConsumeComment";
        v110 = "NewComment = this->AllocateStreamObject()";
LABEL_226:
        v121 = v110;
        RtlReportErrorOrigination(&v118, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        return (unsigned int)-1073741801;
      default:
        continue;
    }
  }
}

```

## disassembly

```asm
0x180017380  push    rbp
0x180017382  push    rbx
0x180017383  push    rsi
0x180017384  push    rdi
0x180017385  push    r12
0x180017387  push    r13
0x180017389  push    r14
0x18001738b  lea     rbp, [rsp-40h]
0x180017390  sub     rsp, 140h
0x180017397  mov     rax, cs:__security_cookie
0x18001739e  xor     rax, rsp
0x1800173a1  mov     [rbp+70h+var_38], rax
0x1800173a5  xorps   xmm0, xmm0
0x1800173a8  mov     [rbp+70h+var_B0], 58h ; 'X'
0x1800173b0  movups  [rbp+70h+var_98], xmm0
0x1800173b4  mov     qword ptr [rbp+70h+var_98], rdx
0x1800173b8  lea     rsi, [rcx+2488h]
0x1800173bf  movups  [rbp+70h+var_A8], xmm0
0x1800173c3  lea     rdx, [rbp+70h+var_B0]
0x1800173c7  mov     r13, rcx
0x1800173ca  movups  [rbp+70h+var_88], xmm0
0x1800173ce  mov     qword ptr [rbp+70h+var_A8], rsi
0x1800173d2  movups  [rbp+70h+var_78], xmm0
0x1800173d6  mov     dword ptr [rbp+70h+var_A8+8], 40h ; '@'
0x1800173dd  movups  [rbp+70h+var_68], xmm0
0x1800173e1  mov     qword ptr [rbp+70h+var_98+8], r8
0x1800173e5  mov     byte ptr [rbp+70h+var_88], 1
0x1800173e9  call    RtlXmlInitializeNextLogicalThing
0x1800173ee  mov     ebx, eax
0x1800173f0  test    eax, eax
0x1800173f2  jns     short loc_180017421
0x1800173f4  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_xmlwalker.h"
0x1800173fb  mov     [rsp+170h+var_F8], 96h
0x180017404  mov     qword ptr [rsp+170h+var_108], rax
0x180017409  lea     rax, aCxmllogicalsta; "CXmlLogicalState::Initialize"
0x180017410  mov     qword ptr [rsp+170h+var_108+8], rax
0x180017415  lea     rax, aRtlxmlinitiali_1; "RtlXmlInitializeNextLogicalThing(this, "...
0x18001741c  jmp     loc_1800176BD
0x180017421  lea     rdi, [r13+8B8h]
0x180017428  mov     byte ptr [r13+8B0h], 1
0x180017430  mov     rcx, rdi; void *
0x180017433  xor     edx, edx; Val
0x180017435  mov     r8d, 4C0h; Size
0x18001743b  call    memset
0x180017440  lea     rax, [rdi+8]
0x180017444  test    rax, rax
0x180017447  jz      short loc_180017489
0x180017449  mov     qword ptr [rax+8], 20h ; ' '
0x180017451  lea     rcx, [rdi+420h]
0x180017458  mov     dword ptr [rax+10h], 32h ; '2'
0x18001745f  movups  xmm0, xmmword ptr [rsi]
0x180017462  movups  xmmword ptr [rax+20h], xmm0
0x180017466  movsd   xmm1, qword ptr [rsi+10h]
0x18001746b  movsd   qword ptr [rax+30h], xmm1
0x180017470  test    rcx, rcx
0x180017473  jz      short loc_18001749D
0x180017475  mov     [rax+18h], rcx
0x180017479  mov     dword ptr [rax+14h], 5
0x180017480  mov     dword ptr [rax+4], 5
0x180017487  jmp     short loc_18001749D
0x180017489  mov     ecx, 0C000000Dh; int
0x18001748e  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x180017493  mov     ebx, eax
0x180017495  test    eax, eax
0x180017497  js      loc_180017657
0x18001749d  lea     rax, [rdi+58h]
0x1800174a1  xor     r14d, r14d
0x1800174a4  test    rax, rax
0x1800174a7  jz      loc_180017643
0x1800174ad  mov     [r13+910h], r14
0x1800174b4  lea     rcx, [rdi+0B0h]
0x1800174bb  mov     [r13+924h], r14
0x1800174c2  mov     [r13+92Ch], r14
0x1800174c9  mov     [r13+934h], r14
0x1800174d0  mov     [r13+93Ch], r14
0x1800174d7  mov     [r13+944h], r14
0x1800174de  mov     [r13+94Ch], r14
0x1800174e5  mov     [r13+954h], r14d
0x1800174ec  mov     qword ptr [rax+8], 0B0h
0x1800174f4  mov     dword ptr [rax+10h], 32h ; '2'
0x1800174fb  movups  xmm0, xmmword ptr [rsi]
0x1800174fe  movups  xmmword ptr [rax+20h], xmm0
0x180017502  movsd   xmm1, qword ptr [rsi+10h]
0x180017507  movsd   qword ptr [rax+30h], xmm1
0x18001750c  test    rcx, rcx
0x18001750f  jz      short loc_180017523
0x180017511  mov     [rax+18h], rcx
0x180017515  mov     dword ptr [rax+14h], 5
0x18001751c  mov     dword ptr [rax+4], 5
0x180017523  lea     rax, ?LocalCompareExtents@CXmlCursor@@KAJPEAXPEBU_XML_EXTENT@@1PEAW4XML_STRING_COMPARE@@@Z; CXmlCursor::LocalCompareExtents(void *,_XML_EXTENT const *,_XML_EXTENT const *,XML_STRING_COMPARE *)
0x18001752a  mov     [rdi+0A8h], r13
0x180017531  mov     [rdi+0A0h], rax
0x180017538  mov     r12d, 4
0x18001753e  lea     rax, [r13+0D80h]
0x180017545  mov     [rdi+50h], r14d
0x180017549  mov     byte ptr [rdi+4C0h], 1
0x180017550  test    rax, rax
0x180017553  jz      loc_180017681
0x180017559  mov     [r13+0D80h], r14
0x180017560  lea     rcx, [rax+48h]
0x180017564  mov     [r13+0D94h], r14
0x18001756b  mov     [r13+0D9Ch], r14
0x180017572  mov     [r13+0DA4h], r14
0x180017579  mov     [r13+0DACh], r14
0x180017580  mov     [r13+0DB4h], r14
0x180017587  mov     [r13+0DBCh], r14
0x18001758e  mov     [r13+0DC4h], r14d
0x180017595  mov     qword ptr [rax+8], 70h ; 'p'
0x18001759d  mov     [rax+10h], r12d
0x1800175a1  movups  xmm0, xmmword ptr [rsi]
0x1800175a4  movups  xmmword ptr [rax+20h], xmm0
0x1800175a8  movsd   xmm1, qword ptr [rsi+10h]
0x1800175ad  movsd   qword ptr [rax+30h], xmm1
0x1800175b2  test    rcx, rcx
0x1800175b5  jz      short loc_1800175C9
0x1800175b7  mov     [rax+18h], rcx
0x1800175bb  mov     dword ptr [rax+14h], 32h ; '2'
0x1800175c2  mov     dword ptr [rax+4], 32h ; '2'
0x1800175c9  lea     rcx, [r13+23A8h]; void *
0x1800175d0  mov     [rsp+170h+arg_18], r15
0x1800175d8  xor     edx, edx; Val
0x1800175da  mov     r8d, 0E0h; Size
0x1800175e0  call    memset
0x1800175e5  cmp     dword ptr [r13+30h], 5
0x1800175ea  mov     r15d, 1
0x1800175f0  setz    al
0x1800175f3  mov     [r13+24A0h], al
0x1800175fa  mov     rdi, [r13+24A8h]
0x180017601  mov     rdx, [rdi+4E0h]
0x180017608  test    rdx, rdx
0x18001760b  jz      loc_1800176E5
0x180017611  mov     rax, [rdx+8]
0x180017615  cmp     [rdx], rax
0x180017618  jnz     loc_180017750
0x18001761e  mov     rax, [rdx]
0x180017621  lea     rbx, [rax+rax]
0x180017625  lea     rax, [rbx+rbx*8]
0x180017629  shl     rax, 4
0x18001762d  cmp     rax, 400000h
0x180017633  jbe     loc_1800176DC
0x180017639  mov     ebx, 71C7h
0x18001763e  jmp     loc_1800176EA
0x180017643  mov     ecx, 0C000000Dh; int
0x180017648  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x18001764d  mov     ebx, eax
0x18001764f  test    eax, eax
0x180017651  jns     loc_180017523
0x180017657  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_xmlwalker.h"
0x18001765e  mov     [rsp+170h+var_F8], 69h ; 'i'
0x180017667  mov     qword ptr [rsp+170h+var_108], rax
0x18001766c  lea     rax, aCxmlnamespacem; "CXmlNamespaceManager::Initialize"
0x180017673  mov     qword ptr [rsp+170h+var_108+8], rax
0x180017678  lea     rax, aRtlnsinitializ_0; "RtlNsInitialize(this, Comparison, pvCom"...
0x18001767f  jmp     short loc_1800176BD
0x180017681  mov     ecx, 0C000000Dh; int
0x180017686  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x18001768b  mov     ebx, eax
0x18001768d  test    eax, eax
0x18001768f  jns     loc_1800175C9
0x180017695  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_xmlwalker.h"
0x18001769c  mov     [rsp+170h+var_F8], 2Dh ; '-'
0x1800176a5  mov     qword ptr [rsp+170h+var_108], rax
0x1800176aa  lea     rax, aCrtlgrowinglis; "CRtlGrowingList<struct _XMLDOC_ATTRIBUT"...
0x1800176b1  mov     qword ptr [rsp+170h+var_108+8], rax
0x1800176b6  lea     rax, aRtlinitializeg_0; "RtlInitializeGrowingList( this, sizeof("...
0x1800176bd  mov     r8d, ebx
0x1800176c0  mov     [rbp+70h+var_F0], rax
0x1800176c4  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800176cb  lea     rcx, [rsp+170h+var_108]
0x1800176d0  call    RtlReportErrorOrigination
0x1800176d5  mov     eax, ebx
0x1800176d7  jmp     loc_18001890F
0x1800176dc  test    rbx, rbx
0x1800176df  cmovz   rbx, r15
0x1800176e3  jmp     short loc_1800176EA
0x1800176e5  mov     ebx, 1C7h
0x1800176ea  mov     rcx, gs:60h
0x1800176f3  lea     r8, [rbx+rbx*8]
0x1800176f7  shl     r8, 4; Size
0x1800176fb  xor     edx, edx; Flags
0x1800176fd  mov     rcx, [rcx+30h]; HeapHandle
0x180017701  call    cs:__imp_RtlAllocateHeap
0x180017708  nop     dword ptr [rax+rax+00h]
0x18001770d  mov     rsi, rax
0x180017710  test    rax, rax
0x180017713  jz      loc_1800188BE
0x180017719  mov     ecx, 20h ; ' '; Size
0x18001771e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017723  mov     rdx, rax
0x180017726  test    rax, rax
0x180017729  jz      loc_1800188BE
0x18001772f  mov     [rax], rbx
0x180017732  mov     [rax+8], r14
0x180017736  mov     [rax+10h], rsi
0x18001773a  mov     [rax+18h], r14
0x18001773e  mov     rcx, [rdi+4E0h]
0x180017745  mov     [rax+18h], rcx
0x180017749  mov     [rdi+4E0h], rax
0x180017750  mov     rax, [rdx+8]
0x180017754  mov     rdx, [rdx+10h]
0x180017758  lea     rcx, [rax+rax*8]
0x18001775c  shl     rcx, 4
0x180017760  add     rdx, rcx
0x180017763  jz      short loc_1800177A2
0x180017765  lea     rax, [rdx+30h]
0x180017769  mov     [rdx+10h], r14
0x18001776d  mov     [rax+8], rax
0x180017771  mov     [rax], rax
0x180017774  lea     rax, [rdx+58h]
0x180017778  mov     [rax+8], rax
0x18001777c  mov     [rax], rax
0x18001777f  mov     [rdx], r14
0x180017782  mov     [rdx+8], r14
0x180017786  mov     [rdx+28h], r14
0x18001778a  mov     [rdx+18h], r14
0x18001778e  mov     [rdx+20h], r14
0x180017792  mov     [rdx+40h], r14
0x180017796  mov     [rdx+48h], r14
0x18001779a  mov     [rdx+50h], r14
0x18001779e  mov     [rdx+68h], r14
0x1800177a2  mov     rax, [rdi+4E0h]
0x1800177a9  inc     qword ptr [rax+8]
0x1800177ad  test    rdx, rdx
0x1800177b0  jz      loc_1800188BE
0x1800177b6  mov     ecx, [rdi+510h]
0x1800177bc  lea     eax, [rcx+1]
0x1800177bf  mov     [rdi+510h], eax
0x1800177c5  mov     [rdx+48h], ecx
0x1800177c8  mov     ecx, r15d
0x1800177cb  mov     [rdx+50h], r15d
0x1800177cf  mov     [rdx+54h], r15d
0x1800177d3  mov     eax, [rdi+514h]
0x1800177d9  cmp     eax, r15d
0x1800177dc  cmova   ecx, eax
0x1800177df  mov     [rdi+514h], ecx
0x1800177e5  mov     dword ptr [rdx+70h], 0E0004h
0x1800177ec  cmp     [rdi+4E8h], r14
0x1800177f3  jnz     loc_18001892E
0x1800177f9  lea     rcx, [rdi+4F0h]
0x180017800  mov     [rdx+40h], r14
0x180017804  mov     rax, [rcx+8]
0x180017808  mov     [rdi+4E8h], rdx
0x18001780f  mov     [rdx+8], rax
0x180017813  mov     [rdx], rcx
0x180017816  mov     rax, [rcx+8]
0x18001781a  mov     [rax], rdx
0x18001781d  mov     [rcx+8], rdx
0x180017821  mov     [rdx+10h], rcx
0x180017825  lea     rsi, __ImageBase
0x18001782c  inc     qword ptr [rcx+18h]
0x180017830  lea     rdi, [r13+23A8h]
0x180017837  cmp     dword ptr [rdi], 1; jumptable 000000018001787A default case, cases 1,2,6
0x18001783a  jz      loc_1800188BA
0x180017840  lea     r9, [r13+0D80h]; struct _RTL_GROWING_LIST *
0x180017847  mov     byte ptr [rsp+170h+var_150], 0
0x18001784c  lea     rdx, [r13+8B8h]; struct _NS_MANAGER *
0x180017853  mov     r8, rdi; void *
0x180017856  mov     rcx, r13; struct _XML_TOKENIZATION_STATE *
0x180017859  call    RtlXmlNextLogicalThingEx
0x18001785e  mov     ebx, eax
0x180017860  test    eax, eax
0x180017862  js      loc_180018875
0x180017868  movsxd  rax, dword ptr [rdi]
0x18001786b  cmp     eax, 0Dh; switch 14 cases
0x18001786e  ja      short def_18001787A; jumptable 000000018001787A default case, cases 1,2,6
0x180017870  mov     ecx, ds:(jpt_18001787A - 180000000h)[rsi+rax*4]
0x180017877  add     rcx, rsi
0x18001787a  jmp     rcx; switch jump
0x180017880  mov     rcx, [r13+24A8h]; jumptable 000000018001787A case 3
0x180017887  mov     rdx, r13; struct CXmlCursor *
0x18001788a  mov     byte ptr [r13+24B0h], 1
0x180017892  call    ?StartElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::StartElement(CXmlCursor *)
0x180017897  test    eax, eax
0x180017899  jns     short def_18001787A; jumptable 000000018001787A default case, cases 1,2,6
0x18001789b  jmp     loc_180018907
0x1800178a0  mov     rdi, [r13+24A8h]; jumptable 000000018001787A case 4
0x1800178a7  cmp     qword ptr [rdi+4E8h], 0
0x1800178af  jz      loc_18001892E
0x1800178b5  mov     rdx, [rdi+4E0h]
0x1800178bc  test    rdx, rdx
0x1800178bf  jz      short loc_1800178F5
0x1800178c1  mov     rax, [rdx+8]
0x1800178c5  cmp     [rdx], rax
0x1800178c8  jnz     loc_180017967
0x1800178ce  mov     rax, [rdx]
0x1800178d1  lea     rbx, [rax+rax]
0x1800178d5  lea     rax, [rbx+rbx*8]
0x1800178d9  shl     rax, 4
0x1800178dd  cmp     rax, 400000h
0x1800178e3  jbe     short loc_1800178EC
0x1800178e5  mov     ebx, 71C7h
0x1800178ea  jmp     short loc_1800178FA
0x1800178ec  test    rbx, rbx
0x1800178ef  cmovz   rbx, r15
0x1800178f3  jmp     short loc_1800178FA
0x1800178f5  mov     ebx, 1C7h
0x1800178fa  mov     rcx, gs:60h
0x180017903  lea     r8, [rbx+rbx*8]
0x180017907  shl     r8, 4; Size
0x18001790b  xor     edx, edx; Flags
  ... truncated ...
```
