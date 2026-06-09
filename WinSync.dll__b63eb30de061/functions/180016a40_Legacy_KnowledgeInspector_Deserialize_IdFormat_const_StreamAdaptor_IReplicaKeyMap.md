# Legacy::KnowledgeInspector::Deserialize(IdFormat const &,StreamAdaptor &,IReplicaKeyMap *)

- ea: `0x180016a40`
- end: `0x180017ce4`
- name: `?Deserialize@KnowledgeInspector@Legacy@@QEAAJAEBUIdFormat@@AEAVStreamAdaptor@@PEAUIReplicaKeyMap@@@Z`
- size: `4772`
- prototype: `__int64 __fastcall(Legacy::KnowledgeInspector *this, const struct IdFormat *, struct StreamAdaptor *, struct IReplicaKeyMap *)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config`

## callers

- `0x180001278`

## callees

- `0x180005d80`
- `0x1800068a4`
- `0x18000724c`
- `0x180007d6c`
- `0x180007fa0`
- `0x180008728`
- `0x180008a00`
- `0x1800095bc`
- `0x180009840`
- `0x180009d7c`
- `0x180009ffc`
- `0x18000a9e0`
- `0x18000bad8`
- `0x18000c524`
- `0x18000c920`
- `0x18000c958`
- `0x18000e740`
- `0x18000e81c`
- `0x18000eaf4`
- `0x18000eb28`
- `0x18000f810`
- `0x18000fd70`
- `0x180011f60`
- `0x180011fd0`
- `0x180015140`
- `0x1800164e4`
- `0x180016a40`
- `0x180017d50`
- `0x180018170`
- `0x180018abc`
- `0x180018dd0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001bf08`
- `0x18001e43c`
- `0x18001f530`
- `0x180020080`
- `0x1800237b4`
- `0x1800823e8`
- `0x180082458`
- `0x180083a94`
- `0x1800884a8`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016b8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ccb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016f93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001718e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800172d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016b8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ccb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016f93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001718e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800172d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a3f`

## string_xrefs

- `0x180016b56`: `Legacy::KnowledgeInspector::Deserialize`
- `0x180016f4c`: `Legacy::KnowledgeInspector::Deserialize`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::Deserialize(
        Legacy::KnowledgeInspector *this,
        const struct IdFormat *a2,
        struct StreamAdaptor *a3,
        struct IReplicaKeyMap *a4)
{
  struct StreamAdaptor *v5; // r13
  __int64 v6; // rcx
  unsigned __int64 v7; // r9
  __int64 v8; // r8
  unsigned __int8 *v9; // rcx
  int v10; // edx
  unsigned int v11; // r14d
  struct IReplicaKeyMap *v12; // rsi
  unsigned __int64 v13; // rcx
  RangeSet *v14; // rdi
  ReplicaKeyMap *v15; // rax
  ReplicaKeyMap *v16; // rax
  ClockVector *v17; // rax
  ClockVector *v18; // rax
  ClockVector *v19; // rbx
  unsigned int v20; // r12d
  unsigned int v21; // ebx
  ClockVector *v22; // rax
  ClockVector *v23; // rax
  ClockVector *v24; // r13
  unsigned int v25; // ebx
  unsigned int i; // r12d
  __int64 v27; // rbx
  __int64 NextElement; // rax
  const struct SyncId *v29; // r13
  unsigned int v31; // r12d
  RangeSet *v32; // rax
  RangeSet *v33; // rax
  struct IReplicaKeyMapVtbl *lpVtbl; // rax
  unsigned int Count; // eax
  unsigned int v36; // ebx
  unsigned int v37; // eax
  RangeSet *v38; // r13
  int v39; // r11d
  __int64 v40; // rdx
  int v41; // r8d
  _QWORD *v42; // r10
  int v43; // edx
  RangeSet *v44; // rax
  const struct SyncId *v45; // rdx
  unsigned int v46; // r9d
  unsigned __int64 v47; // rdx
  int v48; // r8d
  __int64 v49; // rbx
  __int64 v50; // rax
  bool v51; // cf
  SIZE_T v52; // rax
  _QWORD *v53; // rax
  ClockVector *v54; // rax
  ClockVector *v55; // r12
  ClockVector **v56; // rbx
  int v57; // eax
  char *v58; // r11
  unsigned int v59; // ecx
  unsigned int v60; // edx
  char *v61; // r8
  char *v62; // r10
  char *v63; // rax
  unsigned int v64; // ecx
  unsigned int v65; // edx
  unsigned __int16 *v66; // rcx
  unsigned __int8 *v67; // r11
  unsigned __int8 *v68; // r8
  unsigned __int8 *v69; // r9
  unsigned __int8 *v70; // r10
  int v71; // edx
  int v72; // ecx
  unsigned __int16 *v73; // rax
  unsigned __int16 v74; // ax
  ClockVector *v75; // r11
  unsigned int v76; // edx
  unsigned int v77; // r8d
  __int64 v78; // r11
  __int64 v79; // r10
  unsigned int v80; // ecx
  unsigned int v81; // eax
  unsigned int v82; // r9d
  unsigned int v83; // eax
  unsigned __int64 v84; // r8
  int v85; // edx
  unsigned __int8 *v86; // rcx
  int v87; // eax
  int v88; // r9d
  int v89; // ecx
  __int64 v90; // rdx
  unsigned __int64 v91; // rax
  int v92; // r8d
  int v93; // edx
  void *v94; // r13
  void *v95; // r12
  unsigned __int8 *v96; // rcx
  bool v97; // zf
  __int64 v98; // rdx
  int v99; // r9d
  int v100; // edx
  __int64 v101; // rdx
  int v102; // r9d
  int v103; // edx
  unsigned __int64 v104; // r8
  int v105; // edx
  ClockVector *v106; // rax
  ClockVector *v107; // rax
  unsigned int v108; // eax
  unsigned int HashValue; // eax
  RangeSet *v110; // rbx
  unsigned int v111; // eax
  __int64 v112; // [rsp+48h] [rbp-C0h] BYREF
  void *v113; // [rsp+50h] [rbp-B8h]
  ClockVector *v114; // [rsp+58h] [rbp-B0h]
  int v115; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v116; // [rsp+64h] [rbp-A4h] BYREF
  int v117; // [rsp+68h] [rbp-A0h] BYREF
  int v118; // [rsp+6Ch] [rbp-9Ch]
  int v119; // [rsp+70h] [rbp-98h]
  unsigned int v120; // [rsp+74h] [rbp-94h] BYREF
  ClockVector *v121; // [rsp+78h] [rbp-90h] BYREF
  int v122; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 v123; // [rsp+84h] [rbp-84h]
  unsigned int v124; // [rsp+88h] [rbp-80h] BYREF
  RangeSet *v125; // [rsp+90h] [rbp-78h] BYREF
  ClockVector *v126; // [rsp+98h] [rbp-70h]
  int v127; // [rsp+A0h] [rbp-68h]
  __int64 v128; // [rsp+A8h] [rbp-60h] BYREF
  __int128 *v129; // [rsp+B0h] [rbp-58h] BYREF
  void *v130; // [rsp+B8h] [rbp-50h]
  int v131; // [rsp+C0h] [rbp-48h]
  __int16 v132; // [rsp+C4h] [rbp-44h]
  struct IReplicaKeyMap *v133; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v134[4]; // [rsp+D0h] [rbp-38h] BYREF
  int v135; // [rsp+D4h] [rbp-34h]
  __int64 v136; // [rsp+D8h] [rbp-30h]
  int v137; // [rsp+E0h] [rbp-28h]
  _QWORD *v138; // [rsp+E8h] [rbp-20h]
  ClockVector *v139; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v140[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v141; // [rsp+108h] [rbp+0h]
  int v142; // [rsp+110h] [rbp+8h]
  __int128 v143; // [rsp+118h] [rbp+10h] BYREF
  __int64 v144; // [rsp+128h] [rbp+20h]
  int v145; // [rsp+130h] [rbp+28h]
  _BYTE v146[16]; // [rsp+138h] [rbp+30h] BYREF
  char v147[24]; // [rsp+148h] [rbp+40h] BYREF
  char v148[40]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v149[232]; // [rsp+188h] [rbp+80h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::Deserialize");
  }
  v6 = *((unsigned int *)v5 + 4);
  v7 = *((unsigned int *)v5 + 5);
  if ( v6 + 4 > v7 || (v8 = (unsigned int)(v6 + 4), (unsigned int)v8 < (unsigned int)v6) )
  {
    v119 = 0;
    LOWORD(v118) = 0;
    v115 = 0;
    v123 = 0;
    goto LABEL_6;
  }
  v9 = (unsigned __int8 *)(*((_QWORD *)v5 + 1) + v6);
  v138 = (_QWORD *)((char *)v5 + 8);
  v10 = v9[3] | ((v9[2] | (((*v9 << 8) | v9[1]) << 8)) << 8);
  *((_DWORD *)v5 + 4) = v8;
  if ( v10 != 3 || v8 + 4 > v7 || (int)v8 + 4 < (unsigned int)v8 )
  {
    v119 = 0;
    LOWORD(v118) = 0;
    v115 = 0;
    v123 = 0;
LABEL_6:
    v133 = 0;
    v11 = -2147217396;
    v117 = 0;
    v12 = 0;
    v122 = 0;
    ClockVectorManager::ClockVectorManager((ClockVectorManager *)v146);
    v14 = 0;
    v112 = 0;
LABEL_14:
    v126 = 0;
    v136 = 0;
    v135 = 0;
    v128 = 0;
    goto LABEL_21;
  }
  v96 = (unsigned __int8 *)(*((_QWORD *)v5 + 1) + (unsigned int)v8);
  v14 = 0;
  v127 = 0;
  v115 = 0;
  v12 = 0;
  v133 = 0;
  v97 = (v96[3] | ((v96[2] | (((*v96 << 8) | v96[1]) << 8)) << 8)) == 0;
  *((_DWORD *)v5 + 4) = v8 + 4;
  if ( !v97 )
  {
    v117 = 0;
    v119 = 0;
    LOWORD(v118) = 0;
    v11 = -2147217396;
    v115 = 0;
    v123 = 0;
    v122 = 0;
    ClockVectorManager::ClockVectorManager((ClockVectorManager *)v146);
    v112 = v98;
    goto LABEL_14;
  }
  if ( a4 )
  {
    lpVtbl = a4->lpVtbl;
    v12 = a4;
    v133 = a4;
    ((void (__fastcall *)(struct IReplicaKeyMap *))lpVtbl->AddRef)(a4);
    Count = ReplicaKeyMap::GetCount(&v133, &v115);
    LODWORD(v14) = v115;
    v11 = Count;
    v127 = v115;
    goto LABEL_65;
  }
  v15 = (ReplicaKeyMap *)HeapAlloc(hHeap, 0, 0xB0u);
  if ( !v15
    || (v16 = ReplicaKeyMap::ReplicaKeyMap(v15),
        v133 = (struct IReplicaKeyMap *)v16,
        (v12 = (struct IReplicaKeyMap *)v16) == 0) )
  {
    v117 = 0;
    v119 = 0;
    LOWORD(v118) = 0;
    v11 = -2147024882;
    v115 = 0;
    v123 = 0;
    v122 = 0;
    ClockVectorManager::ClockVectorManager((ClockVectorManager *)v146);
    v112 = 0;
    goto LABEL_14;
  }
  v138 = (_QWORD *)((char *)v5 + 8);
  v11 = ReplicaKeyMap::InitializeByDeserializing(v16, v5);
  if ( v11 )
  {
LABEL_65:
    v117 = 0;
    v119 = 0;
    LOWORD(v118) = 0;
    if ( v11 )
      goto LABEL_67;
    goto LABEL_66;
  }
  LODWORD(v14) = v12[5].lpVtbl;
  v127 = (int)v14;
  v117 = 0;
  LOWORD(v118) = 0;
LABEL_66:
  v11 = IdFormat::Deserialize((IdFormat *)&v117, v5);
  v119 = (unsigned __int16)v118;
LABEL_67:
  v122 = 0;
  v115 = 0;
  v123 = 0;
  if ( !v11 )
  {
    v11 = IdFormat::Deserialize((IdFormat *)&v122, v5);
    v115 = v123;
  }
  ClockVectorManager::ClockVectorManager((ClockVectorManager *)v146);
  if ( !v11 )
    v11 = ClockVectorManager::Initialize((ClockVectorManager *)v146, 4u);
  v126 = 0;
  v121 = 0;
  if ( !v11 )
  {
    v106 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
    if ( !v106 )
    {
      v11 = -2147024882;
      v112 = 0;
      v14 = 0;
      v136 = 0;
      v135 = 0;
      v128 = 0;
      goto LABEL_21;
    }
    v107 = ClockVector::ClockVector(v106);
    v126 = v107;
    v121 = v107;
    if ( v107 )
      v11 = ClockVector::InitializeByDeserializing(v107, v5, (int)v14 - 1);
    else
      v11 = -2147024882;
  }
  v36 = 0;
  v116 = 0;
  if ( !v11 )
  {
    v37 = ClockVectorManager::FindByKeyOrAdd(v146, &v121, &v116);
    v36 = v116;
    v11 = v37;
  }
  v128 = 0;
  v14 = 0;
  v38 = 0;
  if ( !v11 )
  {
    v44 = (RangeSet *)HeapAlloc(hHeap, 0, 0x38u);
    if ( v44 )
      v14 = RangeSet::RangeSet(v44);
    v128 = (__int64)v14;
    v11 = 0;
    v38 = v14;
    if ( !v14 )
      v11 = -2147024882;
  }
  v135 = 0;
  v136 = 0;
  if ( !v11 )
  {
    v11 = SyncId::InitializeWithZeroId((SyncId *)v134, (const struct IdFormat *)&v117);
    if ( !v11 )
    {
      v11 = RangeSet::Initialize(v14, (const struct SyncId *)v134);
      if ( !v11 )
      {
        v45 = (const struct SyncId *)*((_QWORD *)v38 + 3);
        HIDWORD(v129) = 0;
        v130 = 0;
        v11 = RangeSet::InjectRange(v14, v45, (const struct SyncId *)&v129, v36);
        SyncId::~SyncId((SyncId *)&v129);
        if ( v11 == -2147217398 )
        {
          v5 = a3;
          LODWORD(v113) = 16;
          v11 = -2147217396;
          v112 = 0;
          v114 = 0;
          goto LABEL_31;
        }
      }
    }
  }
  v5 = a3;
  v39 = 3;
  if ( v11 )
  {
    v42 = v138;
  }
  else
  {
    v40 = *((unsigned int *)a3 + 4);
    v13 = v40 + 4;
    if ( v40 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) )
      goto LABEL_82;
    v41 = v40 + 4;
    if ( (int)v40 + 4 < (unsigned int)v40 )
      goto LABEL_82;
    v42 = v138;
    v13 = v40 + *v138;
    v43 = *(unsigned __int8 *)(v13 + 3)
        | ((*(unsigned __int8 *)(v13 + 2) | (((*(unsigned __int8 *)v13 << 8) | *(unsigned __int8 *)(v13 + 1)) << 8)) << 8);
    *((_DWORD *)a3 + 4) = v41;
    if ( v43 != 3 )
      goto LABEL_82;
    v13 = *((unsigned int *)a3 + 4);
    v84 = *((unsigned int *)a3 + 5);
    if ( v13 + 4 > v84 )
      goto LABEL_82;
    v85 = v13 + 4;
    if ( (int)v13 + 4 < (unsigned int)v13 )
      goto LABEL_82;
    v86 = (unsigned __int8 *)(*v42 + v13);
    v87 = v86[3];
    v88 = (v86[2] | (((*v86 << 8) | v86[1]) << 8)) << 8;
    v89 = 3;
    v82 = v87 | v88;
    *((_DWORD *)a3 + 4) = v85;
    LODWORD(v125) = v82;
    if ( !v117 )
      v89 = (unsigned __int16)v119;
    v13 = (unsigned int)(2 * v89 + 8);
    if ( v82 > ((int)v84 - v85) / (unsigned int)v13 )
    {
      v11 = -2147217396;
      v112 = 0;
      goto LABEL_21;
    }
    v83 = 0;
LABEL_184:
    v90 = *((unsigned int *)v5 + 4);
    v51 = v83 < v82;
    v120 = v83;
    v91 = *((unsigned int *)v5 + 5);
    v13 = v90 + 4;
    if ( v51 )
    {
      if ( v13 > v91 )
        goto LABEL_82;
      v92 = v90 + 4;
      if ( (int)v90 + 4 < (unsigned int)v90 )
        goto LABEL_82;
      v13 = v90 + *v42;
      v93 = *(unsigned __int8 *)(v13 + 3)
          | ((*(unsigned __int8 *)(v13 + 2) | (((*(unsigned __int8 *)v13 << 8) | *(unsigned __int8 *)(v13 + 1)) << 8)) << 8);
      *((_DWORD *)v5 + 4) = v92;
      if ( v93 != 2 )
        goto LABEL_82;
      HIDWORD(v112) = 0;
      v113 = 0;
      v11 = SyncId::InitializeByDeserializing((SyncId *)&v112, (const struct IdFormat *)&v117, v5);
      if ( v11 )
        goto LABEL_238;
      HIDWORD(v129) = 0;
      v130 = 0;
      v11 = SyncId::InitializeByDeserializing((SyncId *)&v129, (const struct IdFormat *)&v117, v5);
      if ( !v11 )
      {
        v94 = v113;
        v61 = (char *)v113;
        v116 = (HIDWORD(v112) >> 17) & 1;
        if ( !v116 )
          v61 = (char *)v113 + 4;
        v74 = WORD2(v129);
        v95 = v130;
        v62 = (char *)v130;
        v137 = (HIDWORD(v129) >> 17) & 1;
        if ( !v137 )
          v62 = (char *)v130 + 4;
        if ( v61 == v62 )
          goto LABEL_131;
        if ( (v112 & 0x1000000000000LL) != 0 )
        {
          v66 = (unsigned __int16 *)v113;
          if ( ((HIDWORD(v112) >> 17) & 1) == 0 )
            v66 = (unsigned __int16 *)((char *)v113 + 4);
          v67 = (unsigned __int8 *)&v61[*v66];
          if ( (HIDWORD(v129) & 0x10000) != 0 )
          {
            v73 = (unsigned __int16 *)v130;
            if ( ((HIDWORD(v129) >> 17) & 1) == 0 )
              v73 = (unsigned __int16 *)((char *)v130 + 4);
            v74 = *v73;
          }
          v68 = (unsigned __int8 *)(v61 + 2);
          v69 = (unsigned __int8 *)&v62[v74];
          v70 = (unsigned __int8 *)(v62 + 2);
          while ( v68 < v67 )
          {
            if ( v70 >= v69 )
              goto LABEL_131;
            v71 = *v70;
            v72 = *v68;
            if ( v72 != v71 )
            {
              if ( (unsigned __int8)v72 > (unsigned __int8)v71 )
                goto LABEL_131;
LABEL_16:
              v17 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
              if ( !v17 )
              {
                v121 = 0;
LABEL_18:
                v11 = -2147024882;
LABEL_19:
                SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v121);
                goto LABEL_20;
              }
              v18 = ClockVector::ClockVector(v17);
              v121 = v18;
              v19 = v18;
              if ( !v18 )
                goto LABEL_18;
              v11 = ClockVector::InitializeByDeserializing(v18, a3, v127 - 1);
              if ( v11 )
                goto LABEL_19;
              v75 = v126;
              if ( v126 != v19 )
              {
                v76 = 0;
                v77 = 0;
                while ( v76 < *((_DWORD *)v19 + 7) && v77 < *((_DWORD *)v75 + 7) )
                {
                  v78 = *((_QWORD *)v75 + 5);
                  v79 = *((_QWORD *)v19 + 5) + 16LL * v76;
                  if ( *(_DWORD *)(v78 + 16LL * v77) > *(_DWORD *)v79 )
                  {
                    v75 = v126;
                    ++v76;
                  }
                  else
                  {
                    if ( *(_DWORD *)(v78 + 16LL * v77) != *(_DWORD *)v79
                      || *(_QWORD *)(v79 + 8) < *(_QWORD *)(v78 + 16LL * v77 + 8) )
                    {
                      goto LABEL_224;
                    }
                    v75 = v126;
                    ++v76;
                    ++v77;
                  }
                }
                v80 = *((_DWORD *)v75 + 7);
                if ( v77 < v80 )
                {
                  do
                  {
                    if ( *(_QWORD *)(*((_QWORD *)v75 + 5) + 16LL * v77 + 8) )
                      break;
                    ++v77;
                  }
                  while ( v77 < v80 );
                  if ( v77 < v80 )
                  {
LABEL_224:
                    v11 = -2147217396;
                    goto LABEL_19;
                  }
                }
              }
              v124 = 0;
              v11 = ClockVectorManager::FindByKeyOrAdd(v146, &v121, &v124);
              if ( v11 )
                goto LABEL_19;
              v81 = RangeSet::InjectRange(v14, (const struct SyncId *)&v112, (const struct SyncId *)&v129, v124);
              v11 = v81;
              if ( v81 != -2147217398 )
              {
                if ( v81 )
                  goto LABEL_195;
                (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v19 + 16LL))(v19);
                if ( !v137 && v95 && _InterlockedExchangeAdd((volatile signed __int32 *)v95, 0xFFFFFFFF) == 1 )
                {
                  SeFree(v95);
                  v130 = 0;
                }
                if ( !v116 && v94 && _InterlockedExchangeAdd((volatile signed __int32 *)v94, 0xFFFFFFFF) == 1 )
                {
                  SeFree(v94);
                  v113 = 0;
                }
                v82 = (unsigned int)v125;
                v83 = v120 + 1;
                v5 = a3;
                v42 = v138;
                goto LABEL_184;
              }
              v11 = -2147217396;
LABEL_195:
              (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_20:
              SyncId::~SyncId((SyncId *)&v129);
              SyncId::~SyncId((SyncId *)&v112);
              v5 = a3;
              v112 = 0;
LABEL_21:
              v114 = 0;
              LODWORD(v113) = 16;
              goto LABEL_31;
            }
            ++v68;
            ++v70;
          }
          if ( v70 < v69 )
            goto LABEL_16;
        }
        else
        {
          v58 = &v61[4 * ((unsigned __int64)WORD2(v112) >> 2)];
          while ( v61 < v58 )
          {
            v59 = *(_DWORD *)v62;
            v60 = *(_DWORD *)v61;
            if ( *(_DWORD *)v61 != *(_DWORD *)v62 )
            {
              if ( (unsigned __int8)v60 > (unsigned __int8)v59 )
                goto LABEL_131;
              if ( (unsigned __int8)v60 < (unsigned __int8)v59 || BYTE1(v60) < BYTE1(v59) )
                goto LABEL_16;
              if ( BYTE1(v60) > BYTE1(v59) || BYTE2(v60) > BYTE2(v59) )
                goto LABEL_131;
              if ( BYTE2(v60) < BYTE2(v59) )
                goto LABEL_16;
              v64 = HIBYTE(v59);
              v65 = HIBYTE(v60);
              if ( (unsigned __int8)v65 > (unsigned __int8)v64 )
                goto LABEL_131;
              if ( (unsigned __int8)v65 < (unsigned __int8)v64 )
                goto LABEL_16;
            }
            v61 += 4;
            v62 += 4;
          }
          if ( (v112 & 0x300000000LL) != 0 )
          {
            v63 = (char *)v113;
            if ( !v116 )
              v63 = (char *)v113 + 4;
            while ( v61 < &v63[WORD2(v112)] && (unsigned __int8)*v61 <= (unsigned __int8)*v62 )
            {
              if ( (unsigned __int8)*v61 < (unsigned __int8)*v62 )
                goto LABEL_16;
              ++v61;
              ++v62;
            }
          }
        }
LABEL_131:
        v11 = -2147217396;
        goto LABEL_20;
      }
      SyncId::~SyncId((SyncId *)&v129);
LABEL_238:
      SyncId::~SyncId((SyncId *)&v112);
      v112 = 0;
      goto LABEL_21;
    }
    if ( v13 > v91 )
      goto LABEL_82;
    v99 = v90 + 4;
    if ( (int)v90 + 4 < (unsigned int)v90 )
      goto LABEL_82;
    v13 = v90 + *v42;
    v100 = *(unsigned __int8 *)(v13 + 3)
         | ((*(unsigned __int8 *)(v13 + 2) | (((*(unsigned __int8 *)v13 << 8) | *(unsigned __int8 *)(v13 + 1)) << 8)) << 8);
    *((_DWORD *)v5 + 4) = v99;
    if ( v100 != 6 )
    {
      v112 = 0;
      LODWORD(v113) = 16;
      v11 = -2147217396;
      v114 = 0;
LABEL_31:
      v25 = 0;
      goto LABEL_32;
    }
    v101 = *((unsigned int *)v5 + 4);
    v13 = v101 + 4;
    if ( v101 + 4 > (unsigned __int64)*((unsigned int *)v5 + 5) || (v102 = v101 + 4, (int)v101 + 4 < (unsigned int)v101) )
    {
LABEL_82:
      v112 = 0;
      LODWORD(v113) = 16;
      v11 = -2147217396;
      v114 = 0;
      goto LABEL_31;
    }
    v13 = v101 + *v42;
    v138 = v42;
    v103 = *(unsigned __int8 *)(v13 + 3)
         | ((*(unsigned __int8 *)(v13 + 2) | (((*(unsigned __int8 *)v13 << 8) | *(unsigned __int8 *)(v13 + 1)) << 8)) << 8);
    *((_DWORD *)v5 + 4) = v102;
    if ( v103 != 4 )
    {
      v112 = 0;
      LODWORD(v113) = 16;
      v11 = -2147217396;
      v114 = 0;
      goto LABEL_31;
    }
    v11 = 0;
    v39 = 3;
  }
  v120 = 0;
  v46 = 0;
  if ( !v11 )
  {
    v13 = *((unsigned int *)v5 + 4);
    v47 = *((unsigned int *)v5 + 5);
    if ( v13 + 4 > v47 || (v48 = v13 + 4, (int)v13 + 4 < (unsigned int)v13) )
    {
      v11 = -2147217396;
      v112 = 0;
      goto LABEL_21;
    }
    v13 += *v42;
    v46 = *(unsigned __int8 *)(v13 + 3)
        | ((*(unsigned __int8 *)(v13 + 2) | (((*(unsigned __int8 *)v13 << 8) | *(unsigned __int8 *)(v13 + 1)) << 8)) << 8);
    *((_DWORD *)v5 + 4) = v48;
    v120 = v46;
    if ( v46 > (unsigned int)(v47 - v48) >> 3 )
    {
      v112 = 0;
      LODWORD(v113) = 16;
      v11 = -2147217396;
      v114 = 0;
      goto LABEL_31;
    }
    v11 = 0;
  }
  v20 = 0;
  v121 = 0;
  v114 = 0;
  LODWORD(v113) = 16;
  v112 = 0;
  if ( !v11 )
  {
    v13 = v46;
    v21 = 0;
    if ( !v46 )
      v13 = 16;
    v116 = v13;
    LODWORD(v113) = v13;
    while ( 1 )
    {
      v124 = v21;
      if ( v21 >= v46 )
      {
        v5 = a3;
        v39 = 3;
        v42 = v138;
        break;
      }
      v22 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
      if ( !v22 )
      {
        v139 = 0;
LABEL_29:
        v11 = -2147024882;
LABEL_30:
        SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v139);
        v5 = a3;
        goto LABEL_31;
      }
      v23 = ClockVector::ClockVector(v22);
      v139 = v23;
      v24 = v23;
      if ( !v23 )
        goto LABEL_29;
      v11 = ClockVector::InitializeByDeserializing(v23, a3, v127 - 1);
      if ( v11 )
      {
        (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v24 + 16LL))(v24);
        v5 = a3;
        goto LABEL_31;
      }
      v11 = 0;
      if ( v121 )
      {
        if ( v20 + 1 > HIDWORD(v112) )
        {
          v57 = Vector<SharedRefPtr<ClockVector>,1>::IncreaseCapacity(&v112, (unsigned int)(2 * HIDWORD(v112)));
          v20 = v112;
          v11 = v57;
          v121 = v114;
          v116 = (unsigned int)v113;
          if ( v57 < 0 )
            goto LABEL_114;
        }
      }
      else
      {
        v49 = v116;
        v50 = 8LL * v116;
        if ( !is_mul_ok(v116, 8u) )
          v50 = -1;
        v51 = __CFADD__(v50, 8);
        v52 = v50 + 8;
        if ( v51 )
          v52 = -1;
        v53 = HeapAlloc(hHeap, 0, v52);
        if ( !v53 )
        {
          v114 = 0;
          goto LABEL_29;
        }
        *v53 = v49;
        v54 = (ClockVector *)(v53 + 1);
        v121 = v54;
        v55 = v54;
        if ( v49 )
        {
          do
          {
            SharedRefPtr<Legacy::Override>::`default constructor closure'(v55);
            v55 = (ClockVector *)((char *)v55 + 8);
            --v49;
          }
          while ( v49 );
          v54 = v121;
        }
        v114 = v54;
        if ( !v54 )
          goto LABEL_29;
        v20 = v112;
        HIDWORD(v112) = v116;
      }
      v56 = (ClockVector **)((char *)v121 + 8 * v20++);
      LODWORD(v112) = v20;
      if ( v56 != &v139 )
      {
        if ( *v56 )
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)*v56 + 16LL))(*v56);
        *v56 = v24;
        (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v24 + 8LL))(v24);
      }
      v21 = v124;
LABEL_114:
      if ( v11 )
        goto LABEL_30;
      (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v24 + 16LL))(v24);
      v46 = v120;
      ++v21;
    }
  }
  v25 = 0;
  if ( !v11 )
  {
    v13 = *((unsigned int *)v5 + 4);
    v104 = *((unsigned int *)v5 + 5);
    if ( v13 + 4 > v104 )
      goto LABEL_215;
    v105 = v13 + 4;
    if ( (int)v13 + 4 < (unsigned int)v13 )
      goto LABEL_215;
    v25 = *(unsigned __int8 *)(*v42 + v13 + 3)
        | ((*(unsigned __int8 *)(*v42 + v13 + 2)
          | ((*(unsigned __int8 *)(*v42 + v13 + 1) | (*(unsigned __int8 *)(*v42 + v13) << 8)) << 8)) << 8);
    *((_DWORD *)v5 + 4) = v105;
    if ( !v117 )
      v39 = (unsigned __int16)v119;
    v13 = (unsigned int)(v39 + 4);
    if ( v25 <= ((int)v104 - v105) / (unsigned int)v13 )
      v11 = 0;
    else
LABEL_215:
      v11 = -2147217396;
  }
LABEL_32:
  v144 = 0;
  v143 = 0;
  LODWORD(v143) = 11;
  v145 = 1;
  if ( !v11 )
  {
    for ( i = 0; i < v25; ++i )
    {
      v11 = Legacy::KnowledgeInspector::DeserializeItemOverride(v13, v5, &v117, &v122, &v112, v146, &v128, &v143);
      if ( v11 )
        break;
    }
  }
  v141 = 0;
  *(_OWORD *)v140 = 0;
  LODWORD(v140[0]) = 11;
  v142 = 1;
  if ( !v11 )
  {
    v27 = v140[1];
    if ( v140[1] )
    {
      TableBucket<SyncId,SharedRefPtr<RangeSet>,SimpleHashTableContext>::`vector deleting destructor'(v140[1]);
      v27 = 0;
      LODWORD(v141) = 0;
      v140[1] = 0;
    }
    LODWORD(v140[0]) = GetNextPrimeNumber(0xBu);
    v129 = &v143;
    v130 = 0;
    while ( 1 )
    {
      NextElement = TableEnumerator<Tuple<SyncId,SyncId>,unsigned long,SimpleHashTableContext>::GetNextElement(&v129);
      v29 = (const struct SyncId *)NextElement;
      if ( !NextElement )
        break;
      v31 = *(_DWORD *)(NextElement + 32);
      v125 = 0;
      v120 = 0;
      if ( !v27
        || (HashValue = SyncId::GetHashValue((SyncId *)(NextElement + 16)),
            (unsigned int)HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::FindExistingBucket(
                            v140[0],
                            HashValue,
                            (int)v29 + 16,
                            v27,
                            v140[0],
                            (__int64)&v120)) )
      {
        v32 = (RangeSet *)HeapAlloc(hHeap, 0, 0x38u);
        if ( v32 )
          v33 = RangeSet::RangeSet(v32);
        else
          v33 = 0;
        v11 = SharedRefPtr<RangeSet>::Attach(&v125, v33);
        if ( v11 )
          goto LABEL_255;
        v110 = v125;
        v11 = RangeSet::InitializeByCloning(v125, v14);
        if ( v11 )
          goto LABEL_255;
        v111 = HashTable<SyncId,SharedRefPtr<RangeSet>,SimpleHashTableContext>::AddItem(v140, (char *)v29 + 16, &v125);
        v11 = v111;
        if ( v111 == -2147024809 )
        {
          v11 = -2147217396;
LABEL_255:
          TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::~TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>(&v125);
          break;
        }
        if ( v111 )
          goto LABEL_255;
      }
      else
      {
        SharedRefPtr<RangeSet>::operator=(&v125, v27 + 32LL * v120 + 16);
        v110 = v125;
      }
      v108 = RangeSet::InjectRangeOfOne(v110, v29, v31);
      v11 = v108;
      if ( v108 == -2147217398 )
      {
        v11 = -2147217396;
LABEL_227:
        if ( v110 )
          RangeSet::Release(v110);
        break;
      }
      if ( v108 )
        goto LABEL_227;
      if ( v110 )
        RangeSet::Release(v110);
      v27 = v140[1];
    }
  }
  LODWORD(v129) = *(_DWORD *)a2;
  WORD2(v129) = *((_WORD *)a2 + 2);
  LODWORD(v130) = v117;
  WORD2(v130) = v119;
  v131 = v122;
  v132 = v115;
  CoreKnowledge::CoreKnowledge((CoreKnowledge *)v149);
  if ( !v11 )
  {
    v11 = CoreKnowledge::InitializeByBuildingFromParts((CoreKnowledge *)v149, (__int64)&v128, (__int64)v140);
    if ( !v11 )
      CoreKnowledge::Swap((CoreKnowledge *)(*(_QWORD *)this + 48LL), (struct CoreKnowledge *)v149);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::Deserialize",
      v11);
  }
  CoreKnowledge::~CoreKnowledge((CoreKnowledge *)v149);
  if ( v140[1] )
  {
    TableBucket<SyncId,SharedRefPtr<RangeSet>,SimpleHashTableContext>::`vector deleting destructor'(v140[1]);
    v140[1] = 0;
    LODWORD(v141) = 0;
  }
  if ( *((_QWORD *)&v143 + 1) )
  {
    TableBucket<Tuple<SyncId,SyncId>,unsigned long,SimpleHashTableContext>::`vector deleting destructor'();
    *((_QWORD *)&v143 + 1) = 0;
    LODWORD(v144) = 0;
  }
  Vector<SharedRefPtr<ClockVector>,1>::~Vector<SharedRefPtr<ClockVector>,1>(&v112);
  SyncId::~SyncId((SyncId *)v134);
  if ( v14 )
    RangeSet::Release(v14);
  if ( v126 )
    (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v126 + 16LL))(v126);
  HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::FreeHashTable(v148);
  Vector<SharedRefPtr<ClockVector>,1>::~Vector<SharedRefPtr<ClockVector>,1>(v147);
  if ( v12 )
    ((void (__fastcall *)(struct IReplicaKeyMap *))v12->lpVtbl->Release)(v12);
  return v11;
}

```

## disassembly

```asm
0x180016a40  mov     rax, rsp
0x180016a43  mov     [rax+18h], r8
0x180016a47  mov     [rax+10h], rdx
0x180016a4b  mov     [rax+8], rcx
0x180016a4f  push    rbp
0x180016a50  push    rsi
0x180016a51  push    r14
0x180016a53  lea     rbp, [rax-1A8h]
0x180016a5a  sub     rsp, 290h
0x180016a61  mov     [rax+20h], rbx
0x180016a65  mov     rbx, r9
0x180016a68  mov     [rax-20h], rdi
0x180016a6c  mov     [rax-30h], r13
0x180016a70  mov     r13, r8
0x180016a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a7a  lea     rax, WPP_GLOBAL_Control
0x180016a81  cmp     rcx, rax
0x180016a84  jnz     loc_180016B3E
0x180016a8a  mov     ecx, [r13+10h]
0x180016a8e  mov     r9d, [r13+14h]
0x180016a92  mov     [rsp+2A0h+var_20], r12
0x180016a9a  mov     [rsp+2A0h+var_30], r15
0x180016aa2  lea     rax, [rcx+4]
0x180016aa6  cmp     rax, r9
0x180016aa9  ja      loc_180017BC7
0x180016aaf  lea     r8d, [rcx+4]
0x180016ab3  cmp     r8d, ecx
0x180016ab6  jb      loc_180017BC7
0x180016abc  add     rcx, [r13+8]
0x180016ac0  lea     r12, [r13+8]
0x180016ac4  mov     [rbp+1A0h+var_1C0], r12
0x180016ac8  movzx   eax, byte ptr [rcx]
0x180016acb  movzx   edx, byte ptr [rcx+1]
0x180016acf  shl     eax, 8
0x180016ad2  or      edx, eax
0x180016ad4  movzx   eax, byte ptr [rcx+2]
0x180016ad8  shl     edx, 8
0x180016adb  or      edx, eax
0x180016add  movzx   eax, byte ptr [rcx+3]
0x180016ae1  shl     edx, 8
0x180016ae4  or      edx, eax
0x180016ae6  mov     [r13+10h], r8d
0x180016aea  cmp     edx, 3
0x180016aed  jz      loc_180017849
0x180016af3  xor     r15d, r15d
0x180016af6  movzx   edx, r15w
0x180016afa  mov     [rsp+2A0h+var_248], r15d
0x180016aff  mov     dword ptr [rsp+2A0h+var_238], edx
0x180016b03  mov     word ptr [rsp+2A0h+var_23C], dx
0x180016b08  mov     [rsp+2A0h+var_248], edx
0x180016b0c  mov     [rsp+2A0h+var_224], dx
0x180016b11  lea     rcx, [rbp+1A0h+var_170]; this
0x180016b15  mov     [rbp+1A0h+var_1E0], r15
0x180016b19  mov     r14d, 8004100Ch
0x180016b1f  mov     [rsp+2A0h+var_240], r15d
0x180016b24  mov     rsi, r15
0x180016b27  mov     [rsp+2A0h+var_228], r15d
0x180016b2c  call    ??0ClockVectorManager@@QEAA@XZ; ClockVectorManager::ClockVectorManager(void)
0x180016b31  mov     rdi, r15
0x180016b34  mov     [rsp+2A0h+var_260], r15
0x180016b39  jmp     loc_180016BE2
0x180016b3e  test    byte ptr [rcx+1Ch], 40h
0x180016b42  jz      loc_180016A8A
0x180016b48  cmp     byte ptr [rcx+19h], 5
0x180016b4c  jb      loc_180016A8A
0x180016b52  mov     rcx, [rcx+10h]
0x180016b56  lea     r9, aLegacyKnowledg_13; "Legacy::KnowledgeInspector::Deserialize"
0x180016b5d  mov     edx, 1Ch
0x180016b62  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x180016b69  call    WPP_SF_s
0x180016b6e  jmp     loc_180016A8A
0x180016b73  test    rbx, rbx
0x180016b76  jnz     loc_180016FC2
0x180016b7c  mov     rcx, cs:hHeap; hHeap
0x180016b83  xor     edx, edx; dwFlags
0x180016b85  mov     r8d, 0B0h; dwBytes
0x180016b8b  call    cs:__imp_HeapAlloc
0x180016b91  test    rax, rax
0x180016b94  jz      short loc_180016BAE
0x180016b96  mov     rcx, rax; this
0x180016b99  call    ??0ReplicaKeyMap@@QEAA@XZ; ReplicaKeyMap::ReplicaKeyMap(void)
0x180016b9e  mov     [rbp+1A0h+var_1E0], rax
0x180016ba2  mov     rsi, rax
0x180016ba5  test    rax, rax
0x180016ba8  jnz     loc_180017A9E
0x180016bae  movzx   edx, r15w
0x180016bb2  mov     [rsp+2A0h+var_240], r15d
0x180016bb7  lea     rcx, [rbp+1A0h+var_170]; this
0x180016bbb  mov     dword ptr [rsp+2A0h+var_238], edx
0x180016bbf  mov     word ptr [rsp+2A0h+var_23C], dx
0x180016bc4  mov     r14d, 8007000Eh
0x180016bca  mov     [rsp+2A0h+var_248], edx
0x180016bce  mov     [rsp+2A0h+var_224], dx
0x180016bd3  mov     [rsp+2A0h+var_228], r15d
0x180016bd8  call    ??0ClockVectorManager@@QEAA@XZ; ClockVectorManager::ClockVectorManager(void)
0x180016bdd  mov     [rsp+2A0h+var_260], rdi
0x180016be2  mov     [rbp+1A0h+var_210], r15
0x180016be6  mov     [rbp+1A0h+var_1D0], r15
0x180016bea  mov     [rbp+1A0h+var_1D4], r15d
0x180016bee  mov     [rbp+1A0h+var_200], r15
0x180016bf2  jmp     short loc_180016C62
0x180016bf4  cmp     cl, dl
0x180016bf6  ja      loc_180017489
0x180016bfc  mov     rcx, cs:hHeap; hHeap
0x180016c03  xor     edx, edx; dwFlags
0x180016c05  mov     r8d, 40h ; '@'; dwBytes
0x180016c0b  call    cs:__imp_HeapAlloc
0x180016c11  test    rax, rax
0x180016c14  jz      loc_180016FAF
0x180016c1a  mov     rcx, rax; this
0x180016c1d  call    ??0ClockVector@@QEAA@XZ; ClockVector::ClockVector(void)
0x180016c22  mov     qword ptr [rsp+2A0h+var_230], rax
0x180016c27  mov     rbx, rax
0x180016c2a  test    rax, rax
0x180016c2d  jnz     loc_180017559
0x180016c33  mov     r14d, 8007000Eh
0x180016c39  lea     rcx, [rsp+2A0h+var_230]
0x180016c3e  call    ??1?$SharedRefPtr@VClockVector@@@@QEAA@XZ; SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(void)
0x180016c43  lea     rcx, [rbp+1A0h+var_1F8]; this
0x180016c47  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180016c4c  lea     rcx, [rsp+2A0h+var_260]; this
0x180016c51  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180016c56  mov     r13, [rbp+1A0h+arg_10]
0x180016c5d  mov     [rsp+2A0h+var_260], r15
0x180016c62  mov     eax, 10h
0x180016c67  mov     qword ptr [rsp+2A0h+var_250], r15
0x180016c6c  mov     dword ptr [rsp+2A0h+var_258], eax
0x180016c70  jmp     loc_180016D08
0x180016c75  mov     rax, r15
0x180016c78  mov     r12d, r15d
0x180016c7b  mov     qword ptr [rsp+2A0h+var_230], rax
0x180016c80  mov     qword ptr [rsp+2A0h+var_250], rax
0x180016c85  mov     eax, 10h
0x180016c8a  mov     dword ptr [rsp+2A0h+var_258], eax
0x180016c8e  mov     [rsp+2A0h+var_260], r12
0x180016c93  test    r14d, r14d
0x180016c96  jnz     loc_1800179B9
0x180016c9c  test    r9d, r9d
0x180016c9f  mov     ecx, r9d
0x180016ca2  mov     ebx, r15d
0x180016ca5  cmovz   ecx, eax
0x180016ca8  mov     [rsp+2A0h+var_244], ecx
0x180016cac  mov     dword ptr [rsp+2A0h+var_258], ecx
0x180016cb0  mov     [rbp+1A0h+var_220], ebx
0x180016cb3  cmp     ebx, r9d
0x180016cb6  jnb     loc_180017BA9
0x180016cbc  mov     rcx, cs:hHeap; hHeap
0x180016cc3  xor     edx, edx; dwFlags
0x180016cc5  mov     r8d, 40h ; '@'; dwBytes
0x180016ccb  call    cs:__imp_HeapAlloc
0x180016cd1  test    rax, rax
0x180016cd4  jz      loc_180016FB9
0x180016cda  mov     rcx, rax; this
0x180016cdd  call    ??0ClockVector@@QEAA@XZ; ClockVector::ClockVector(void)
0x180016ce2  mov     [rbp+1A0h+var_1B8], rax
0x180016ce6  mov     r13, rax
0x180016ce9  test    rax, rax
0x180016cec  jnz     loc_180017329
0x180016cf2  mov     r14d, 8007000Eh
0x180016cf8  lea     rcx, [rbp+1A0h+var_1B8]
0x180016cfc  call    ??1?$SharedRefPtr@VClockVector@@@@QEAA@XZ; SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(void)
0x180016d01  mov     r13, [rbp+1A0h+arg_10]
0x180016d08  mov     ebx, r15d
0x180016d0b  xor     eax, eax
0x180016d0d  xorps   xmm0, xmm0
0x180016d10  mov     [rbp+1A0h+var_180], rax
0x180016d14  movups  [rbp+1A0h+var_190], xmm0
0x180016d18  mov     dword ptr [rbp+1A0h+var_190], 0Bh
0x180016d1f  mov     [rbp+1A0h+var_178], 1
0x180016d26  test    r14d, r14d
0x180016d29  jnz     short loc_180016D78
0x180016d2b  mov     r12d, r15d
0x180016d2e  test    ebx, ebx
0x180016d30  jz      short loc_180016D78
0x180016d32  lea     rax, [rbp+1A0h+var_190]
0x180016d36  mov     rdx, r13
0x180016d39  mov     [rsp+2A0h+var_268], rax
0x180016d3e  lea     r9, [rsp+2A0h+var_228]
0x180016d43  lea     rax, [rbp+1A0h+var_200]
0x180016d47  mov     [rsp+2A0h+var_270], rax
0x180016d4c  lea     r8, [rsp+2A0h+var_240]
0x180016d51  lea     rax, [rbp+1A0h+var_170]
0x180016d55  mov     [rsp+2A0h+var_278], rax
0x180016d5a  lea     rax, [rsp+2A0h+var_260]
0x180016d5f  mov     [rsp+2A0h+var_280], rax
0x180016d64  call    ?DeserializeItemOverride@KnowledgeInspector@Legacy@@AEAAJAEAVStreamAdaptor@@AEBUIdFormat@@1AEBV?$Vector@V?$SharedRefPtr@VClockVector@@@@$00@@AEAVClockVectorManager@@AEAV?$SharedRefPtr@VRangeSet@@@@AEAV?$RefCountedHashTable@U?$Tuple@VSyncId@@V1@@@K@@@Z; Legacy::KnowledgeInspector::DeserializeItemOverride(StreamAdaptor &,IdFormat const &,IdFormat const &,Vector<SharedRefPtr<ClockVector>,1> const &,ClockVectorManager &,SharedRefPtr<RangeSet> &,RefCountedHashTable<Tuple<SyncId,SyncId>,ulong> &)
0x180016d69  mov     r14d, eax
0x180016d6c  test    eax, eax
0x180016d6e  jnz     short loc_180016D78
0x180016d70  inc     r12d
0x180016d73  cmp     r12d, ebx
0x180016d76  jb      short loc_180016D32
0x180016d78  xor     eax, eax
0x180016d7a  xorps   xmm0, xmm0
0x180016d7d  mov     [rbp+1A0h+var_1A0], rax
0x180016d81  movups  xmmword ptr [rbp+1A0h+var_1B0], xmm0
0x180016d85  mov     dword ptr [rbp+1A0h+var_1B0], 0Bh
0x180016d8c  mov     [rbp+1A0h+var_198], 1
0x180016d93  test    r14d, r14d
0x180016d96  jnz     short loc_180016DD7
0x180016d98  mov     rbx, [rbp+1A0h+var_1B0+8]
0x180016d9c  test    rbx, rbx
0x180016d9f  jnz     loc_180017BEA
0x180016da5  mov     ecx, 0Bh; unsigned int
0x180016daa  call    ?GetNextPrimeNumber@@YAKK@Z; GetNextPrimeNumber(ulong)
0x180016daf  mov     dword ptr [rbp+1A0h+var_1B0], eax
0x180016db2  lea     rax, [rbp+1A0h+var_190]
0x180016db6  mov     [rbp+1A0h+var_1F8], rax
0x180016dba  mov     [rbp+1A0h+var_1F0], 0
0x180016dc2  lea     rcx, [rbp+1A0h+var_1F8]
0x180016dc6  call    ?GetNextElement@?$TableEnumerator@U?$Tuple@VSyncId@@V1@@@KVSimpleHashTableContext@@@@QEAAPEAV?$TableElement@U?$Tuple@VSyncId@@V1@@@KVSimpleHashTableContext@@@@XZ; TableEnumerator<Tuple<SyncId,SyncId>,ulong,SimpleHashTableContext>::GetNextElement(void)
0x180016dcb  mov     r13, rax
0x180016dce  test    rax, rax
0x180016dd1  jnz     loc_180016F6E
0x180016dd7  mov     rcx, [rbp+1A0h+arg_8]
0x180016dde  mov     eax, [rcx]
0x180016de0  mov     dword ptr [rbp+1A0h+var_1F8], eax
0x180016de3  movzx   eax, word ptr [rcx+4]
0x180016de7  lea     rcx, [rbp+1A0h+var_120]; this
0x180016dee  mov     word ptr [rbp+1A0h+var_1F8+4], ax
0x180016df2  mov     eax, [rsp+2A0h+var_240]
0x180016df6  mov     dword ptr [rbp+1A0h+var_1F0], eax
0x180016df9  mov     eax, dword ptr [rsp+2A0h+var_238]
0x180016dfd  mov     word ptr [rbp+1A0h+var_1F0+4], ax
0x180016e01  mov     eax, [rsp+2A0h+var_228]
0x180016e05  mov     [rbp+1A0h+var_1E8], eax
0x180016e08  mov     eax, [rsp+2A0h+var_248]
0x180016e0c  mov     [rbp+1A0h+var_1E4], ax
0x180016e10  call    ??0CoreKnowledge@@QEAA@XZ; CoreKnowledge::CoreKnowledge(void)
0x180016e15  mov     r13, [rsp+2A0h+var_28]
0x180016e1d  mov     r12, [rsp+2A0h+var_20]
0x180016e25  mov     rbx, [rsp+2A0h+arg_18]
0x180016e2d  test    r14d, r14d
0x180016e30  jnz     short loc_180016E7D
0x180016e32  lea     rax, [rbp+1A0h+var_1B0]
0x180016e36  mov     [rsp+2A0h+var_278], rax; __int64
0x180016e3b  lea     r9, [rbp+1A0h+var_170]
0x180016e3f  lea     rax, [rbp+1A0h+var_200]
0x180016e43  lea     r8, [rbp+1A0h+var_1E0]
0x180016e47  mov     [rsp+2A0h+var_280], rax; __int64
0x180016e4c  lea     rdx, [rbp+1A0h+var_1F8]
0x180016e50  lea     rcx, [rbp+1A0h+var_120]; this
0x180016e57  call    ?InitializeByBuildingFromParts@CoreKnowledge@@QEAAJAEBUIdDescription@@AEAV?$SharedRefPtr@UIReplicaKeyMap@@@@AEAVClockVectorManager@@AEAV?$SharedRefPtr@VRangeSet@@@@AEAV?$RefCountedHashTable@VSyncId@@V?$SharedRefPtr@VRangeSet@@@@@@@Z; CoreKnowledge::InitializeByBuildingFromParts(IdDescription const &,SharedRefPtr<IReplicaKeyMap> &,ClockVectorManager &,SharedRefPtr<RangeSet> &,RefCountedHashTable<SyncId,SharedRefPtr<RangeSet>> &)
0x180016e5c  mov     r14d, eax
0x180016e5f  test    eax, eax
0x180016e61  jnz     short loc_180016E7D
0x180016e63  mov     rcx, [rbp+1A0h+arg_0]
0x180016e6a  lea     rdx, [rbp+1A0h+var_120]; struct CoreKnowledge *
0x180016e71  mov     rcx, [rcx]
0x180016e74  add     rcx, 30h ; '0'; this
0x180016e78  call    ?Swap@CoreKnowledge@@QEAAXAEAV1@@Z; CoreKnowledge::Swap(CoreKnowledge &)
0x180016e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e84  lea     rax, WPP_GLOBAL_Control
0x180016e8b  cmp     rcx, rax
0x180016e8e  jnz     loc_180016F34
0x180016e94  lea     rcx, [rbp+1A0h+var_120]; this
0x180016e9b  call    ??1CoreKnowledge@@QEAA@XZ; CoreKnowledge::~CoreKnowledge(void)
0x180016ea0  mov     rcx, [rbp+1A0h+var_1B0+8]
0x180016ea4  test    rcx, rcx
0x180016ea7  jnz     loc_180017CC0
0x180016ead  mov     rcx, qword ptr [rbp+1A0h+var_190+8]
0x180016eb1  test    rcx, rcx
0x180016eb4  jnz     loc_180017CD2
0x180016eba  lea     rcx, [rsp+2A0h+var_260]
0x180016ebf  call    ??1?$Vector@V?$SharedRefPtr@VClockVector@@@@$00@@QEAA@XZ; Vector<SharedRefPtr<ClockVector>,1>::~Vector<SharedRefPtr<ClockVector>,1>(void)
0x180016ec4  lea     rcx, [rbp+1A0h+var_1D8]; this
0x180016ec8  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180016ecd  mov     r15, [rsp+2A0h+var_30]
0x180016ed5  test    rdi, rdi
0x180016ed8  jz      short loc_180016EE2
0x180016eda  mov     rcx, rdi; this
0x180016edd  call    ?Release@RangeSet@@QEAAKXZ; RangeSet::Release(void)
0x180016ee2  mov     rcx, [rbp+1A0h+var_210]
0x180016ee6  mov     rdi, [rsp+288h]
0x180016eee  test    rcx, rcx
0x180016ef1  jz      short loc_180016EFF
0x180016ef3  mov     rax, [rcx]
0x180016ef6  mov     rax, [rax+10h]
0x180016efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eff  lea     rcx, [rbp+1A0h+var_148]
0x180016f03  call    ?FreeHashTable@?$HashTable@V?$SharedRefPtr@VClockVector@@@@KVSimpleHashTableContext@@@@AEAAXXZ; HashTable<SharedRefPtr<ClockVector>,ulong,SimpleHashTableContext>::FreeHashTable(void)
0x180016f08  lea     rcx, [rbp+1A0h+var_160]
0x180016f0c  call    ??1?$Vector@V?$SharedRefPtr@VClockVector@@@@$00@@QEAA@XZ; Vector<SharedRefPtr<ClockVector>,1>::~Vector<SharedRefPtr<ClockVector>,1>(void)
0x180016f11  test    rsi, rsi
0x180016f14  jz      short loc_180016F25
0x180016f16  mov     rax, [rsi]
0x180016f19  mov     rcx, rsi
0x180016f1c  mov     rax, [rax+10h]
0x180016f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f25  mov     eax, r14d
0x180016f28  add     rsp, 290h
0x180016f2f  pop     r14
0x180016f31  pop     rsi
0x180016f32  pop     rbp
0x180016f33  retn
0x180016f34  test    byte ptr [rcx+1Ch], 40h
0x180016f38  jz      loc_180016E94
0x180016f3e  cmp     byte ptr [rcx+19h], 5
0x180016f42  jb      loc_180016E94
0x180016f48  mov     rcx, [rcx+10h]
  ... truncated ...
```
