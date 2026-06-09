# VidPartitionIoctlSetup

- ea: `0x14008e464`
- end: `0x140091036`
- name: `VidPartitionIoctlSetup`
- size: `11218`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `60`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14001346c`
- `0x14001422c`
- `0x14001429c`
- `0x140021c60`
- `0x140021db0`
- `0x140021e00`
- `0x140022340`
- `0x14002304c`
- `0x14002311c`
- `0x14002f724`
- `0x1400347a4`
- `0x140034b64`
- `0x140035290`
- `0x1400747bc`
- `0x1400750f8`
- `0x1400757a8`
- `0x140075e84`
- `0x140076328`
- `0x140076c84`
- `0x140076e8c`
- `0x14007a1e8`
- `0x14008b628`
- `0x14008e464`
- `0x1400910fc`
- `0x140091440`
- `0x140091494`
- `0x140092250`
- `0x140094b38`
- `0x14009a058`
- `0x14009a294`
- `0x14009b848`
- `0x14009d42c`
- `0x1400a05b0`
- `0x1400a3a1c`
- `0x1400a3c4c`
- `0x1400a4f60`
- `0x1400a6bb4`
- `0x1400a6c28`
- `0x1400a76e8`
- `0x1400a7c3c`
- `0x1400a8e38`
- `0x1400a8e74`
- `0x1400aef2c`
- `0x1400b0d1c`
- `0x1400b3874`
- `0x1400cef6c`
- `0x1400e6058`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140090b8e`
- `ntoskrnl!EtwEventEnabled` at `0x140090b8e`
- `ntoskrnl!HalPrivateDispatchTable` at `0x14008ed72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090c9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090c9c`
- `ntoskrnl!ExAllocatePool2` at `0x1400909eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400909eb`
- `winhvr!WinHvInitializePartition` at `0x140090167`
- `winhvr!WinHvInitializePartition` at `0x140090167`
- `winhvr!WinHvCreatePartitionEx` at `0x14008faec`
- `winhvr!WinHvCreatePartitionEx` at `0x14008faec`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x14008fec0`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x14008fec0`
- `winhvr!WinHvSetPartitionProperty` at `0x14008fe7b`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ff0d`
- `winhvr!WinHvSetPartitionProperty` at `0x14009005f`
- `winhvr!WinHvSetPartitionProperty` at `0x140090274`
- `winhvr!WinHvSetPartitionProperty` at `0x140090363`
- `winhvr!WinHvSetPartitionProperty` at `0x1400904f7`
- `winhvr!WinHvSetPartitionProperty` at `0x1400905a8`
- `winhvr!WinHvSetPartitionProperty` at `0x140090664`
- `winhvr!WinHvSetPartitionProperty` at `0x14009089f`
- `winhvr!WinHvSetPartitionProperty` at `0x14008fe7b`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ff0d`
- `winhvr!WinHvSetPartitionProperty` at `0x14009005f`
- `winhvr!WinHvSetPartitionProperty` at `0x140090274`
- `winhvr!WinHvSetPartitionProperty` at `0x140090363`
- `winhvr!WinHvSetPartitionProperty` at `0x1400904f7`
- `winhvr!WinHvSetPartitionProperty` at `0x1400905a8`
- `winhvr!WinHvSetPartitionProperty` at `0x140090664`
- `winhvr!WinHvSetPartitionProperty` at `0x14009089f`
- `winhvr!WinHvDeletePartition` at `0x140090cff`
- `winhvr!WinHvDeletePartition` at `0x140090cff`
- `winhvr!WinHvGetPartitionProperty` at `0x140090310`
- `winhvr!WinHvGetPartitionProperty` at `0x140090437`
- `winhvr!WinHvGetPartitionProperty` at `0x140090310`
- `winhvr!WinHvGetPartitionProperty` at `0x140090437`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x14008fc1e`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x14008fc1e`

## string_xrefs

- `0x14008eb45`: `ForceDeferredCommit`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlSetup(__int64 a1, unsigned int *a2, int a3)
{
  PVOID v3; // rbx
  unsigned __int64 v4; // r15
  char v5; // di
  char v6; // si
  char v7; // r14
  __int64 v10; // rdx
  __int64 v11; // xmm7_8
  __int128 v12; // xmm6
  __int64 v13; // rcx
  unsigned int v14; // eax
  _DWORD *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rsi
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned __int64 v40; // rax
  unsigned int v41; // eax
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rdx
  int v47; // eax
  __int64 v48; // rax
  __int64 v49; // r8
  unsigned __int64 v50; // rdx
  __int64 v51; // r9
  unsigned __int64 v52; // rcx
  int v53; // ecx
  __int64 v54; // r8
  int v55; // ecx
  __int16 v56; // dx
  __int64 v57; // rcx
  unsigned int v58; // r8d
  __int64 v59; // r8
  __int64 v60; // rcx
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  unsigned int v65; // r9d
  unsigned int v66; // ecx
  int v67; // r9d
  __int64 v68; // r8
  int v69; // eax
  int v70; // eax
  int v71; // eax
  __int64 v72; // rdx
  int v73; // eax
  __int64 v74; // r10
  unsigned __int8 v75; // r11
  __int64 v76; // rax
  _QWORD *v77; // rbx
  __int64 v78; // r9
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 v82; // rdx
  int v83; // eax
  __int64 v84; // rax
  unsigned __int64 v85; // rcx
  int UINT32WithDefault; // eax
  unsigned __int64 v87; // r14
  unsigned int v88; // ecx
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rsi
  unsigned int v92; // eax
  int v93; // eax
  int v94; // eax
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 (__fastcall *v97)(); // rax
  int v98; // eax
  __int128 v99; // xmm0
  unsigned int v100; // r8d
  __int64 j; // rdx
  __int64 v102; // rcx
  unsigned int v103; // r9d
  unsigned __int8 v104; // r8
  __int64 v105; // r10
  __int64 v106; // rdx
  char *v107; // r14
  unsigned int v108; // eax
  __int64 v109; // rsi
  char v110; // r9
  void *v111; // rdx
  unsigned __int64 v112; // rax
  int PagesForOverlay; // eax
  int v114; // eax
  int v115; // eax
  __int64 v116; // rcx
  bool v117; // zf
  int v118; // eax
  int v119; // eax
  __int64 v120; // rdx
  int v121; // eax
  int v122; // eax
  __int64 v123; // rcx
  int PartitionProperty; // eax
  __int64 v125; // rcx
  int v126; // eax
  int v127; // eax
  __int64 v128; // rcx
  __int64 v129; // rax
  unsigned __int64 v130; // rbx
  int v131; // eax
  __int64 v132; // r14
  __int64 v133; // rbx
  int v134; // ebx
  __int64 v135; // rax
  __int64 v136; // rdx
  int i; // ecx
  __int64 v138; // rax
  int v139; // eax
  __int64 v140; // rcx
  int v141; // eax
  int v142; // eax
  int v143; // eax
  int v144; // eax
  int v145; // eax
  __int64 Pool2; // rax
  unsigned int v147; // ebx
  int v148; // eax
  __int64 v149; // rax
  int v150; // eax
  int v151; // eax
  int v152; // eax
  int v153; // eax
  int v154; // eax
  int v155; // eax
  void *v156; // rcx
  int v157; // r9d
  unsigned __int64 v158; // r14
  unsigned __int64 v159; // rcx
  __int64 v160; // r8
  int v161; // eax
  int v163; // [rsp+28h] [rbp-E0h]
  char v164; // [rsp+58h] [rbp-B0h]
  __int64 v165; // [rsp+78h] [rbp-90h] BYREF
  PVOID v166; // [rsp+80h] [rbp-88h] BYREF
  int v167; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v168; // [rsp+90h] [rbp-78h] BYREF
  char v169; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v170; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v171; // [rsp+A8h] [rbp-60h]
  __int128 v172; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v173; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v174; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v175; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v176; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v177; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v178; // [rsp+100h] [rbp-8h] BYREF
  __int128 v179; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v180[2]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v181; // [rsp+128h] [rbp+20h]
  __int128 v182; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v183[2]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v184; // [rsp+168h] [rbp+60h]
  _QWORD v185[17]; // [rsp+178h] [rbp+70h] BYREF
  _DWORD v186[2]; // [rsp+200h] [rbp+F8h] BYREF
  __int128 *v187; // [rsp+208h] [rbp+100h]
  __int64 v188; // [rsp+210h] [rbp+108h]
  char *v189; // [rsp+218h] [rbp+110h]
  __int64 v190; // [rsp+220h] [rbp+118h]
  unsigned int *v191; // [rsp+228h] [rbp+120h]
  __int64 v192; // [rsp+230h] [rbp+128h]
  unsigned __int64 *v193; // [rsp+238h] [rbp+130h]
  __int64 v194; // [rsp+240h] [rbp+138h]
  PVOID *v195; // [rsp+248h] [rbp+140h]
  __int64 v196; // [rsp+250h] [rbp+148h]
  unsigned int *v197; // [rsp+258h] [rbp+150h]
  __int64 v198; // [rsp+260h] [rbp+158h]
  __int128 *v199; // [rsp+268h] [rbp+160h]
  __int64 v200; // [rsp+270h] [rbp+168h]
  _DWORD v201[128]; // [rsp+278h] [rbp+170h] BYREF

  v3 = VidDeviceExtension;
  v4 = 0;
  *(_QWORD *)&v175 = 0;
  memset(v183, 0, sizeof(v183));
  v184 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v173 = 0;
  v178 = 0;
  v176 = 0;
  v166 = VidDeviceExtension;
  v167 = a3;
  VidObjectLockAcquireExclusive(a1);
  VidObjectLockAcquireExclusive(a1 + 3736);
  VidRegistryOpenParametersKey(&v175);
  v11 = *(_QWORD *)(a1 + 32);
  v12 = *(_OWORD *)(a1 + 16);
  v171 = v175;
  if ( *(_DWORD *)(a1 + 48) )
  {
    if ( (a2[8] & 0x800LL) == 0 || !*(_BYTE *)(a1 + 8657) )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1782,
        3221225485LL);
    }
    goto LABEL_82;
  }
  *(_QWORD *)(a1 + 40) = 0;
  if ( (*((_QWORD *)a2 + 4) & 0xFE00000000000000uLL) != 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1796,
      3221225485LL);
    goto LABEL_82;
  }
  v13 = *(_QWORD *)(a1 + 16);
  v14 = a2[10];
  if ( (v13 & 0x8000) != 0 )
  {
    if ( v14 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1805,
        3221225485LL);
      goto LABEL_82;
    }
  }
  else if ( v14 - 1 > 0x7FF )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1815,
      3221225485LL);
    goto LABEL_82;
  }
  if ( *a2 - 1536 > 0xF900 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1828,
      3221225485LL);
    goto LABEL_82;
  }
  v15 = a2 + 16956;
  if ( (*(_QWORD *)(a1 + 16) & 0x8000LL) == 0 && (*v15 & 0x30) == 0 )
  {
    v13 |= 0x10uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  if ( *((char *)a2 + 32) < 0 )
  {
    v13 &= ~0x10uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  v16 = *((_QWORD *)a2 + 4);
  if ( (v16 & 0x40000000) != 0 )
  {
    if ( (*v15 & 0x30) != 0 || ((v16 & 0x100000000LL) == 0 || *a2 != 1541) && (int)*a2 < 1543 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1856,
        3221225485LL);
      goto LABEL_82;
    }
    v13 |= 0x20uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x31u) )
  {
    if ( (v13 & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1866,
        3221225485LL);
      goto LABEL_82;
    }
    *(_QWORD *)(a1 + 32) |= 0x4000uLL;
  }
  v17 = 0;
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x37u) )
    *(_QWORD *)(a1 + 32) |= 0x10000uLL;
  if ( (v13 & 0x30) != 0 )
    v18 = v13 | 8;
  else
    v18 = v13 | 0x40;
  *(_QWORD *)(a1 + 16) = v18;
  v19 = *((_QWORD *)a2 + 4);
  *(_QWORD *)&v172 = *((_QWORD *)&v176 + 1);
  if ( (v18 & 0x8000) != 0 )
  {
    if ( (v19 & 0xFFBED7C9FFFEFF9FuLL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1896,
        3221225485LL);
LABEL_81:
      v7 = 0;
      v5 = 0;
      goto LABEL_82;
    }
    if ( *((_OWORD *)a2 + 4236) != v176 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1909,
        3221225485LL);
      goto LABEL_81;
    }
    if ( (a2[12] & 0x180) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1919,
        3221225485LL);
      goto LABEL_81;
    }
    *(_QWORD *)(a1 + 16) = v18 | 0x200;
    v20 = (*((_QWORD *)a2 + 4) & 0x200000000LL | 0x10000000uLL) >> 20;
    v21 = *((_DWORD *)VidDeviceExtension + 162);
    if ( (v21 & 0x20) != 0 )
      v17 = 1;
    v19 = *((_QWORD *)a2 + 4);
    v4 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) >> 5) & 1 | 2;
    if ( (v21 & 0x20) == 0 )
      v4 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) >> 5) & 1;
    *(_QWORD *)&v175 = v4;
    if ( (v19 & 0x200000000000LL) != 0 )
      v20 |= 0x1000000u;
    v22 = v20 | 0x800;
    v17 |= 0x3FFEuLL;
    if ( (v19 & 0x10000) != 0 )
      v22 = v20;
  }
  else
  {
    if ( (v19 & 0x200000000000LL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1977,
        3221225485LL);
      goto LABEL_81;
    }
    v22 = 0;
    *(_QWORD *)&v175 = 0;
  }
  if ( (v19 & 8) != 0 )
  {
    if ( !(unsigned int)VidCurrentProcessIsTrusted(a1) )
    {
      LODWORD(v4) = -1073741790;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1994,
        3221225506LL);
LABEL_80:
      v3 = v166;
      goto LABEL_81;
    }
    *(_QWORD *)(a1 + 40) |= 6uLL;
  }
  if ( (a2[8] & 0x10) != 0 )
    *(_QWORD *)(a1 + 40) |= 2uLL;
  v23 = *((_QWORD *)a2 + 4);
  if ( (v23 & 0x100000000LL) != 0 )
    v22 |= 0x1000uLL;
  v24 = v22 | 1;
  if ( (v23 & 0x20) == 0 )
    v24 = v22;
  v25 = v24 | 0x4000;
  if ( (v23 & 0x800000000LL) == 0 )
    v25 = v24;
  if ( (v23 & 0x40) != 0 )
  {
    v25 |= 2uLL;
    *(_QWORD *)(a1 + 16) |= 0x100uLL;
  }
  v26 = *((_QWORD *)a2 + 4);
  v27 = v25 | 0x8000;
  v28 = 0x1000000000000LL;
  if ( (v26 & 0x1000000000LL) == 0 )
    v27 = v25;
  v29 = v27 | 0x8000000;
  if ( (v26 & 0x1000000000000LL) == 0 )
    v29 = v27;
  v30 = v29 | 0x10000;
  if ( (v26 & 0x2000000000LL) == 0 )
    v30 = v29;
  if ( (v26 & 0x4000000000LL) != 0 )
    v30 |= 0x20000uLL;
  v31 = v30 | 0x40000;
  if ( (v26 & 0x8000000000LL) == 0 )
    v31 = v30;
  if ( (v26 & 0x40000000000LL) != 0 && (v26 & 0x80000000000LL) != 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2070,
      3221225485LL);
LABEL_79:
    v6 = 0;
    goto LABEL_80;
  }
  if ( (v26 & 0x400000000000LL) != 0 && (v26 & 0x80000000000LL) == 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2078,
      3221225485LL);
    goto LABEL_79;
  }
  if ( (v26 & 0x40000000000LL) != 0 )
  {
    v31 |= 0x200000uLL;
  }
  else if ( (v26 & 0x80000000000LL) != 0 )
  {
    v31 |= 0x400000uLL;
    if ( (v26 & 0x400000000000LL) != 0 )
      v31 |= 0x2000000uLL;
  }
  v32 = *(_QWORD *)(a1 + 16);
  v168 = v31;
  if ( (v26 & 0x4000000000000LL) != 0 )
  {
    if ( (v32 & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2114,
        3221225485LL);
      goto LABEL_79;
    }
    v31 |= 0x80000000uLL;
    v168 = v31;
  }
  if ( (v32 & 0x8000) != 0 || (v26 & 0x100000000000LL) != 0 )
  {
    v31 |= 0x800000uLL;
    v168 = v31;
  }
  if ( (a2[8] & 0x100LL) != 0 )
  {
    *(_QWORD *)(a1 + 16) = v32 | 0x200;
    v33 = ((unsigned __int64)a2[12] >> 2)
        & 0x3FFFFFFFFFFFFE00LL
        ^ (*(_QWORD *)(a1 + 24)
         ^ ((unsigned __int64)a2[12] >> 2)
         & 0x3FFFFFFFFFFFFE00LL)
        & 0xFFFFFFFFFFFFE1FFuLL;
    *(_QWORD *)(a1 + 24) = v33;
    *(_QWORD *)(a1 + 24) = ((unsigned __int64)a2[12] >> 2)
                         & 0x3FFFFFFFFFFFE000LL
                         ^ (v33
                          ^ ((unsigned __int64)a2[12] >> 2)
                          & 0x3FFFFFFFFFFFE000LL)
                         & 0xFFFFFFFFFFFE1FFFuLL;
    if ( v171 )
    {
      HIDWORD(v165) = 0;
      if ( (int)VidRegistryQueryUINT32(v171, L"ForceDeferredCommit", (char *)&v165 + 4) >= 0 && HIDWORD(v165) )
        *(_QWORD *)(a1 + 24) |= 2uLL;
      if ( (int)VidRegistryQueryUINT32(v171, L"ForcePinBackingPages", (char *)&v165 + 4) >= 0 && HIDWORD(v165) )
        *(_QWORD *)(a1 + 24) |= 1uLL;
      if ( (int)VidRegistryQueryUINT32(v171, L"FaultClusterSizeShift", (char *)&v165 + 4) >= 0 && HIDWORD(v165) < 0x10 )
        *(_QWORD *)(a1 + 24) = ((unsigned __int64)HIDWORD(v165) << 9)
                             ^ (*(_QWORD *)(a1 + 24)
                              ^ ((unsigned __int64)HIDWORD(v165) << 9))
                             & 0xFFFFFFFFFFFFE1FFuLL;
      if ( (int)VidRegistryQueryUINT32(v171, L"DirectMapFaultClusterSizeShift", (char *)&v165 + 4) >= 0
        && HIDWORD(v165) < 0x10 )
      {
        *(_QWORD *)(a1 + 24) = ((unsigned __int64)HIDWORD(v165) << 13)
                             ^ (*(_QWORD *)(a1 + 24)
                              ^ ((unsigned __int64)HIDWORD(v165) << 13))
                             & 0xFFFFFFFFFFFE1FFFuLL;
      }
    }
  }
  if ( (a2[8] & 0x40000) != 0 )
    *(_QWORD *)(a1 + 24) |= 2uLL;
  if ( (a2[8] & 0x400000) != 0 )
    *(_QWORD *)(a1 + 24) |= 1uLL;
  v34 = *(_QWORD *)(a1 + 16);
  if ( (a2[8] & 0x200LL) != 0 )
  {
    v31 |= 4uLL;
    v34 |= 0x400uLL;
    v168 = v31;
    *(_QWORD *)(a1 + 16) = v34;
  }
  v35 = *((_QWORD *)a2 + 4);
  if ( (v35 & 0x38000000) != 0 )
  {
    if ( (v34 & 0x400) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2233,
        3221225485LL);
      goto LABEL_79;
    }
    v34 &= ~0x800uLL;
    v36 = v34 | (v35 >> 16) & 0x800;
    *(_QWORD *)(a1 + 16) = v36;
    *(_QWORD *)(a1 + 16) = v36 & 0xFFFFFFFFFFFFEFFFuLL | HIWORD(a2[8]) & 0x1000;
  }
  v37 = *((_QWORD *)a2 + 4);
  if ( (v37 & 0x400) != 0 )
  {
    v31 |= 0x20uLL;
    v168 = v31;
  }
  if ( (v37 & 0x1000) != 0 )
    *(_QWORD *)(a1 + 24) |= 4uLL;
  if ( (a2[8] & 0x2000LL) != 0 )
    *(_QWORD *)(a1 + 24) |= 8uLL;
  if ( (a2[8] & 0x4000LL) != 0 )
  {
    v38 = *(_QWORD *)(a1 + 24);
    if ( (v38 & 2) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2266,
        3221225485LL);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 24) = v38 | 0x10;
  }
  if ( (a2[8] & 0x8000LL) != 0 )
    *(_QWORD *)(a1 + 24) |= 0x40uLL;
  if ( (a2[8] & 0x20000) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100LL) != 0 || (int)*a2 < 1538 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2286,
        3221225485LL);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 24) |= 0x80uLL;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x33u) )
    *(_QWORD *)(a1 + 24) |= 0x20000uLL;
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x2Fu) )
  {
    if ( !HalPrivateDispatchTable[90](v34, 0x20000, 1024) && (unsigned __int8)VidpIsOsClientVersion() )
    {
      LODWORD(v4) = -1073741637;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2312,
        3221225659LL);
      goto LABEL_79;
    }
    v31 |= 0x4000000uLL;
    *(_QWORD *)(a1 + 40) |= 0x10uLL;
    v168 = v31;
  }
  v39 = *(_QWORD *)(a1 + 24);
  if ( (v39 & 1) != 0 )
  {
    v39 &= 0xFFFFFFFFFFFFFFE7uLL;
    *(_QWORD *)(a1 + 24) = v39;
  }
  if ( (v39 & 0x80u) != 0LL && ((v39 & 0xC) != 0 || (v39 & 0x10) != 0) && (int)*a2 >= 1540 )
  {
    v39 |= 0x20uLL;
    *(_QWORD *)(a1 + 24) = v39;
  }
  if ( (v39 & 2) != 0 && (v39 & 0x18) != 0 )
    *(_QWORD *)(a1 + 24) = v39 | 0x100;
  if ( (a2[8] & 0x100000) != 0 )
  {
    if ( (int)*a2 < 1538 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2388,
        3221225485LL);
      goto LABEL_79;
    }
    v40 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) << 8)
        ^ (*(_QWORD *)(a1 + 16)
         ^ ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) << 8))
        & 0xFFFFFFFFFFFFDFFFuLL;
    *(_QWORD *)(a1 + 16) = v40;
    if ( (v40 & 0x2000) != 0 )
    {
      v31 |= 0x80uLL;
      v168 = v31;
      *(_QWORD *)&v175 = v4 | 1;
    }
  }
  if ( a2[11] )
  {
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2424,
        3221225485LL);
      goto LABEL_79;
    }
    v41 = a2[11];
    if ( v41 >= 0x10 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2433,
        3221225485LL);
      goto LABEL_79;
    }
    *(_DWORD *)(a1 + 3224) = v41;
  }
  if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 || (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 )
  {
    v31 |= 0x80000uLL;
    v168 = v31;
  }
  v42 = (a2[12] >> 7) & 3;
  HIDWORD(v165) = 0;
  v43 = VidPartitionpPageSizeUnitGet(a1, v42, 0, (char *)&v165 + 4);
  LODWORD(v4) = v43;
  if ( v43 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2465,
      (unsigned int)v43);
    goto LABEL_79;
  }
  v45 = v171;
  *(_QWORD *)(a1 + 32) = SHIDWORD(v165) ^ (*(_QWORD *)(a1 + 32) ^ SHIDWORD(v165)) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v45 )
  {
    HIDWORD(v165) = 0;
    if ( (int)VidRegistryQueryUINT32(v45, L"PageBackingSize", (char *)&v165 + 4) >= 0 && HIDWORD(v165) < 3 )
      *(_QWORD *)(a1 + 32) = HIDWORD(v165) ^ (*(_QWORD *)(a1 + 32) ^ HIDWORD(v165)) & 0xFFFFFFFFFFFFFFFCuLL;
    v45 = v171;
  }
  if ( (a2[8] & 0x80000LL) != 0
    || v45
    && (HIDWORD(v165) = 0, (int)VidRegistryQueryUINT32(v45, L"ForcePageBackingSizeRequired", (char *)&v165 + 4) >= 0)
    && HIDWORD(v165) )
  {
    *(_QWORD *)(a1 + 32) |= 4uLL;
  }
  LOBYTE(v44) = 1;
  v46 = (a2[12] >> 9) & 3;
  HIDWORD(v165) = 0;
  v47 = VidPartitionpPageSizeUnitGet(a1, v46, v44, (char *)&v165 + 4);
  LODWORD(v4) = v47;
  if ( v47 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2519,
      (unsigned int)v47);
    goto LABEL_79;
  }
  v48 = v171;
  *(_QWORD *)(a1 + 32) = (8LL * SHIDWORD(v165))
                       ^ (*(_QWORD *)(a1 + 32)
                        ^ (8LL * SHIDWORD(v165)))
                       & 0xFFFFFFFFFFFFFFE7uLL;
  if ( v48 )
  {
    HIDWORD(v165) = 0;
    if ( (int)VidRegistryQueryUINT32(v48, L"PageMappingSize", (char *)&v165 + 4) >= 0 && HIDWORD(v165) < 3 )
      *(_QWORD *)(a1 + 32) = (8LL * HIDWORD(v165))
                           ^ (*(_QWORD *)(a1 + 32)
                            ^ (8LL * HIDWORD(v165)))
                           & 0xFFFFFFFFFFFFFFE7uLL;
  }
  v49 = *(_QWORD *)(a1 + 16);
  if ( (v49 & 0x200) == 0 )
  {
    v52 = *(_QWORD *)(a1 + 32);
LABEL_204:
    v51 = v49;
    goto LABEL_205;
  }
  v50 = *(_QWORD *)(a1 + 32);
  v51 = *(_QWORD *)(a1 + 16);
  if ( (v50 & 3) > 1 )
  {
    v50 = v50 & 0xFFFFFFFFFFFFFFFCuLL | 1;
    *(_QWORD *)(a1 + 32) = v50;
  }
  if ( (v50 & 0x18) <= 8 )
  {
    v51 = v49;
    LOBYTE(v52) = v50;
  }
  else
  {
    v52 = v50 & 0xFFFFFFFFFFFFFFE7uLL | 8;
    *(_QWORD *)(a1 + 32) = v52;
  }
  if ( (v52 & 3) != 1 )
    goto LABEL_204;
  if ( (*(_QWORD *)(a1 + 24) & 0x1E00LL) != 0x1200 )
    *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 24) & 0xFFFFFFFFFFFFE1FFuLL | 0x1200;
LABEL_205:
  v53 = v52 & 0x18;
  if ( v53 )
  {
    if ( v53 != 16 )
      goto LABEL_210;
    v31 |= 0x10uLL;
  }
  else
  {
    v31 |= 8uLL;
  }
  v168 = v31;
LABEL_210:
  if ( (a2[8] & 0x200000) != 0 )
  {
    if ( (v51 & 0x200) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2591,
        3221225485LL);
      goto LABEL_79;
    }
    v51 |= 0x4000uLL;
    *(_QWORD *)(a1 + 16) = v51;
  }
  *(_QWORD *)(a1 + 11952) = 0;
  v54 = a2[16956];
  v55 = a2[16956] & 0xF;
  if ( (unsigned int)(v55 - 2) > 2 && *((_QWORD *)a2 + 8479) )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2604,
      3221225485LL);
    goto LABEL_79;
  }
  if ( (v54 & 0xC0) != 0 )
  {
    if ( v55 != 2 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2614,
        3221225485LL);
      goto LABEL_79;
    }
    if ( (a2[16956] & 0xC0) == 0x80 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2624,
        3221225485LL);
      goto LABEL_79;
    }
    goto LABEL_224;
  }
  if ( v55 || (v54 & 0x30) != 0 )
  {
LABEL_224:
    if ( (*(_BYTE *)(a1 + 40) & 6) != 0 || (v51 & 0x200) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2637,
        3221225485LL);
      goto LABEL_79;
    }
    if ( (v54 & 0xF) != 0 )
    {
      switch ( a2[16956] & 0xF )
      {
        case 1u:
          v56 = v173 & 0xFFE0 | 1;
          break;
        case 2u:
          v56 = v173 & 0xFFE0 | 2;
          break;
        case 3u:
          v56 = v173 & 0xFFE0 | 3;
          break;
        default:
          LODWORD(v4) = -1073741811;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlSetup",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            2676,
            3221225485LL);
          goto LABEL_79;
      }
      *(_QWORD *)(a1 + 32) = (32 * v54) ^ (*(_QWORD *)(a1 + 32) ^ (32 * v54)) & 0xFFFFFFFFFFFFFE1FuLL;
      v57 = *((_QWORD *)a2 + 8479);
      *(_QWORD *)(a1 + 11952) = v57;
      LODWORD(v54) = a2[16956];
      v173 = (2 * (v54 & 0xFFC0)) & 0x180 ^ (v56 & 0xE7F | (unsigned __int64)(v57 << 12));
    }
  }
  v58 = ((unsigned int)v54 >> 4) & 3;
  v10 = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFCFFFuLL | ((unsigned __int64)v58 << 12);
  *(_QWORD *)(a1 + 32) = v10;
  if ( v58 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2730,
      3221225485LL);
    goto LABEL_79;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x34u) )
  {
    if ( (v51 & 0x200) != 0 || (v10 & 0x1E0) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2740,
        3221225485LL);
      goto LABEL_79;
    }
    v31 |= 0x100000000uLL;
    v10 |= 0x8000uLL;
    v168 = v31;
    *(_QWORD *)(a1 + 32) = v10;
  }
  if ( (*((_QWORD *)a2 + 4) & 0x400000000LL) != 0 )
  {
    v10 |= 0x400uLL;
    *(_QWORD *)(a1 + 32) = v10;
  }
  v59 = *((_QWORD *)a2 + 4);
  if ( (v59 & 0x40000000000000LL) != 0 )
  {
    v31 |= 0x400000000uLL;
    v168 = v31;
  }
  if ( (v51 & 0x8000) == 0 )
  {
    v60 = v31 | 0x200;
    if ( (v51 & 0x10) != 0 )
      v60 = v31;
    v61 = v51 & 0x20;
    v62 = v60 | 0x400;
    if ( v61 )
      v62 = v60;
    v10 &= 0x4000u;
    v63 = v62 | 0x40000000;
    if ( !v10 )
      v63 = v62;
    if ( (v59 & 0x10000) != 0 )
    {
      v64 = v63 | 0x10000000;
      if ( !v61 )
        v64 = v63;
    }
    else
    {
      v64 = v63 | 0x800;
    }
    v168 = v64;
  }
  if ( (v59 & 0x20000000000000LL) != 0 )
  {
    LODWORD(v4) = -1073741637;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2818,
      3221225659LL);
    goto LABEL_79;
  }
  v65 = a2[10];
  if ( v65 )
  {
    v66 = 0;
    v10 = a2[12] & 0x7F;
    while ( *((unsigned __int8 *)a2 + v66 + 184) < (unsigned int)v10 )
    {
      if ( ++v66 >= v65 )
        goto LABEL_265;
    }
    LODWORD(v4) = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
      tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
      v167 = v67;
      v185[8] = (char *)&v165 + 4;
      HIDWORD(v165) = 2833;
      v185[10] = &v167;
      v169 = *((_BYTE *)a2 + v68 + 184);
      v185[9] = 4;
      v185[12] = &v169;
      v185[11] = 4;
      v185[13] = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140047B2E, 0, 0, 7, v185);
    }
    goto LABEL_79;
  }
LABEL_265:
  LOBYTE(v10) = a2[12] & 0x7F;
  if ( !(unsigned __int8)VsmmNumaArePartitionSettingsValid(
                           (_DWORD)v166,
                           v10,
                           (int)a2 + 52,
                           (int)a2 + 116,
                           (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0) )
  {
    LODWORD(v4) = -1070137329;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2850,
      3224829967LL);
    goto LABEL_79;
  }
  memmove((void *)(a1 + 2041), a2 + 13, a2[12] & 0x7F);
  memmove((void *)(a1 + 2105), a2 + 29, a2[12] & 0x7F);
  if ( *((_QWORD *)a2 + 8547) )
  {
    v69 = VidResourcePartitionPartitionSetup(a1);
    LODWORD(v4) = v69;
    if ( v69 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2881,
        (unsigned int)v69);
      goto LABEL_79;
    }
  }
  v70 = VsmmMemPartSetupMemoryHostingJob(a1, *((_QWORD *)a2 + 8548));
  LODWORD(v4) = v70;
  if ( v70 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2897,
      (unsigned int)v70);
    goto LABEL_79;
  }
  v71 = VsmmMemPartSetupPhysicalAllocationMemPart(a1);
  LODWORD(v4) = v71;
  if ( v71 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2904,
      (unsigned int)v71);
    goto LABEL_79;
  }
  LOBYTE(v72) = a2[12] & 0x7F;
  v73 = VsmmPartitionSetup(a1, v72);
  LODWORD(v4) = v73;
  if ( v73 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      2913,
      (unsigned int)v73);
    goto LABEL_79;
  }
  v74 = 0;
  v75 = 0;
  v76 = *(_QWORD *)(a1 + 1528);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 16) & 0xFFFFFFFFFFFFFF7FuLL | ((unsigned __int64)(a2[8] & 2) << 6);
  *(_QWORD *)(v76 + 376) = *(unsigned __int8 *)(a1 + 2041);
  if ( (a2[12] & 0x7F) != 0 )
  {
    v77 = v166;
    do
    {
      v78 = v75++;
      v79 = 2LL * (unsigned int)v78;
      v80 = *(_QWORD *)(v77[33] + 8LL * *(unsigned __int8 *)(v78 + a1 + 2105));
      *(_OWORD *)(a1 + 8 * v79 + 2176) = 0;
      *(_WORD *)(a1 + 8 * v79 + 2184) = *(_WORD *)(*(_QWORD *)(v80 + 16) + 8LL);
      *(_QWORD *)(a1 + 16 * (v78 + 136)) = **(_QWORD **)(v80 + 16);
      v74 |= 1LL << *(_BYTE *)(v78 + a1 + 2105);
    }
    while ( v75 < (a2[12] & 0x7F) );
    v28 = 0x1000000000000LL;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 912LL) = v74;
  v81 = *((_QWORD *)a2 + 4);
  if ( (v81 & 0x800) != 0 )
  {
    VsmmMemTrackerDisable(a1);
    v82 = *((_QWORD *)a2 + 4) >> 41;
    LOBYTE(v82) = (*((_QWORD *)a2 + 4) & 0x20000000000LL) != 0;
    v83 = VsmmPhuPartitionRestore(a1, v82);
    LODWORD(v4) = v83;
    if ( v83 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2969,
        (unsigned int)v83);
      goto LABEL_79;
    }
  }
  else
  {
    if ( (v81 & 0x20000000000LL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        2978,
        3221225485LL);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFBFFFFuLL
                         | ((*(_QWORD *)(a1 + 32) & 0xB1E0LL) != 0 ? 0x40000 : 0);
  }
  v84 = *(_QWORD *)(a1 + 8648);
  if ( v84 && *(_BYTE *)(v84 + 1176) )
  {
    v85 = (8LL * *(_QWORD *)(v84 + 1168))
        ^ (*(_QWORD *)(a1 + 32)
         ^ (8LL * *(_QWORD *)(v84 + 1168)))
        & 0xFFFFFFFFFFFFFDFFuLL;
  }
  else
  {
    UINT32WithDefault = 0;
    if ( v171 )
      UINT32WithDefault = VidRegistryQueryUINT32WithDefault(v171, L"ForceSmallGpaMappings", 0);
    v85 = (UINT32WithDefault != 0 ? 0x200 : 0) | *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFFDFFuLL;
  }
  *(_QWORD *)(a1 + 32) = v85;
  v87 = v168;
  if ( (v85 & 0x200) != 0 )
  {
    v87 = v168 & 0xFFFFFFFFFFFFFFE7uLL | 8;
    v168 = v87;
  }
  if ( v17 )
  {
    v87 |= 0x100000u;
    v168 = v87;
    *(_QWORD *)(a1 + 32) = v85 | 0x800;
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) == 0 && (*((_DWORD *)VidDeviceExtension + 162) & 0x800) != 0 )
  {
    v87 |= 0x20000000u;
    v168 = v87;
  }
  VidNumaSetGroupAffinity(a1, 0, v183);
  v88 = *(unsigned __int8 *)(a1 + 2105);
  v89 = *(_QWORD *)(a1 + 16);
  v90 = v88 | 0x80000000;
  v170 = 0;
  v174 = 0;
  if ( (v89 & 0x80u) != 0LL )
    v90 = v88;
  if ( *(_DWORD *)(a1 + 8632) == 2 && *(_DWORD *)(a1 + 8636) == 2 )
  {
    v91 = *(_QWORD *)(a1 + 8648);
    if ( *(_BYTE *)(v91 + 1176) )
    {
      v92 = *a2;
      v180[0] = v87;
      v180[1] = v92;
      v181 = 0;
      v182 = 0;
      VsmmPhuStoreCreationPropertiesSerialize(a2 + 2, v180, v90);
      LODWORD(v182) = a2[10];
      VsmmPhuStoreHvPartitionMakeInvariantFlags(a1 + 16, a1 + 40, (char *)&v182 + 8);
      v93 = VsmmPhuStoreHvPartitionRestore(a1, v91 + 1128, v180);
      LODWORD(v4) = v93;
      if ( v93 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3115,
          (unsigned int)v93);
        goto LABEL_79;
      }
      v6 = 1;
      v94 = VidPartitionpPrivilegesUpdate(a1, &v170, &v174);
      LODWORD(v4) = v94;
      if ( v94 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3131,
          (unsigned int)v94);
        goto LABEL_311;
      }
LABEL_376:
      *(_QWORD *)(a1 + 672) = v87;
      *(_DWORD *)(a1 + 680) = *a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qiddd(
          WPP_GLOBAL_Control->AttachedDevice,
          a2[12] & 0x7F,
          v95,
          a1,
          *(_QWORD *)(a1 + 648),
          a2[10],
          a2[12] & 0x7F,
          *((unsigned __int8 *)a2 + 52));
      }
      v120 = *(_QWORD *)(a1 + 16);
      if ( (v120 & 0x8000) == 0 && (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0 )
        *(_QWORD *)(a1 + 16) = (v170 >> 50) & 0x3FFC ^ (v120 ^ (v170 >> 50) & 0x3FFC) & 0xFFFFFFFFFFFFFFFBuLL;
      if ( (((*(_DWORD *)(a1 + 32) & 0x1E0) - 64LL) & 0xFFFFFFFFFFFFFFDFuLL) == 0 && !*(_BYTE *)(a1 + 8760) )
      {
        if ( *((_QWORD *)a2 + 8480) )
        {
          v121 = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
          LODWORD(v4) = v121;
          if ( v121 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3473,
              (unsigned int)v121);
            goto LABEL_352;
          }
        }
      }
      v122 = VidPdcNotifyPartitionCreation(a1);
      LODWORD(v4) = v122;
      if ( v122 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3485,
          (unsigned int)v122);
        goto LABEL_352;
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x8010LL) == 0 && (int)*a2 >= 1536 )
      {
        v123 = *(_QWORD *)(a1 + 648);
        v168 = 0;
        PartitionProperty = WinHvGetPartitionProperty(v123, 327681, &v168);
        LODWORD(v4) = PartitionProperty;
        if ( PartitionProperty < 0 )
        {
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlSetup",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            3503,
            (unsigned int)PartitionProperty);
          goto LABEL_352;
        }
        if ( *(_BYTE *)(a1 + 8760) )
        {
          if ( (v168 & 0xF) != 0 )
          {
            LODWORD(v4) = -1070268335;
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              goto LABEL_352;
            tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
            tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
            v167 = 3529;
            v185[8] = &v167;
            v111 = &unk_140047980;
            v185[10] = (char *)&v165 + 4;
            v112 = v168;
LABEL_339:
            *(_QWORD *)&v172 = v112;
            goto LABEL_340;
          }
        }
        else
        {
          v125 = *(_QWORD *)(a1 + 648);
          v168 &= 0xFFFFFFFFFFFFFFF0uLL;
          v126 = WinHvSetPartitionProperty(v125);
          LODWORD(v4) = v126;
          if ( v126 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3518,
              (unsigned int)v126);
            goto LABEL_352;
          }
        }
      }
      v127 = WinHvGetPartitionProperty(*(_QWORD *)(a1 + 648), 393236, &v178);
      LODWORD(v4) = v127;
      if ( v127 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3541,
          (unsigned int)v127);
        goto LABEL_352;
      }
      if ( v178 > 0x34 )
      {
        LODWORD(v4) = -1070268406;
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3550,
          3224698890LL);
        goto LABEL_352;
      }
      v128 = *(_QWORD *)(a1 + 32);
      v129 = (1LL << ((unsigned __int8)v178 - 12)) - 1;
      *(_QWORD *)(a1 + 10456) = v129;
      if ( (v128 & 0x4000) != 0 )
        *(_QWORD *)(a1 + 10464) = v129;
      v130 = *(_QWORD *)(a1 + 16);
      if ( (v130 & 0x8000) != 0 )
      {
        *(_DWORD *)(a1 + 10652) = (v128 & 0x18) != 0;
        v131 = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
        LODWORD(v4) = v131;
        if ( v131 < 0 )
        {
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlSetup",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            3604,
            (unsigned int)v131);
          goto LABEL_352;
        }
        v130 = *(_QWORD *)(a1 + 16);
      }
      v132 = v176;
      if ( (v130 & 0x200) == 0 && (*((_QWORD *)a2 + 8472) != (_QWORD)v176 || *((_QWORD *)a2 + 8473) != (_QWORD)v172) )
      {
        LODWORD(v4) = -1073741811;
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3621,
          3221225485LL);
        goto LABEL_352;
      }
      if ( (v130 & 0x400) != 0 && !*(_BYTE *)(a1 + 8762) )
      {
        v133 = (v130 >> 11) & 3;
        LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
        if ( (v4 & 0x80000000) != 0LL )
        {
          if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            goto LABEL_352;
          tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
          tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
          v167 = 3647;
          v185[8] = &v167;
          v111 = &unk_140047921;
          *(_QWORD *)&v172 = (unsigned int)v133;
          v185[10] = (char *)&v165 + 4;
LABEL_340:
          v185[12] = &v172;
          v163 = 7;
LABEL_341:
          v185[13] = 8;
          goto LABEL_342;
        }
      }
      if ( (a2[8] & 0x20000000) != 0 && !*(_BYTE *)(a1 + 8762) )
      {
        v134 = 0;
        while ( 1 )
        {
          LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
          if ( (v4 & 0x80000000) != 0LL )
            break;
          if ( (unsigned int)++v134 >= 4 )
            goto LABEL_426;
        }
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_352;
        tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v167 = 3675;
        v185[8] = &v167;
        v111 = &unk_1400478D9;
        LODWORD(v170) = v134;
        v185[10] = (char *)&v165 + 4;
        v185[12] = &v170;
        v163 = 7;
        v185[13] = 4;
LABEL_342:
        v185[9] = 4;
        HIDWORD(v165) = v4;
        v185[11] = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v111, 0, 0, v163, v185);
        goto LABEL_352;
      }
LABEL_426:
      v135 = *(_QWORD *)(a1 + 32);
      if ( (v135 & 0x31E0) == 0 )
      {
        v136 = *(_QWORD *)(a1 + 16);
        if ( (v136 & 0x210) == 0 && (v135 & 0x8000) == 0 && !_bittest64((const signed __int64 *)a2 + 4, 0x38u) )
        {
          for ( i = 0; i < 2; ++i )
          {
            v138 = (unsigned int)i;
            v136 |= v138 + 1;
          }
          *(_QWORD *)(a1 + 16) = v136;
        }
      }
      v139 = VsmmProcessHostingProcessNamePopulate(a1, a2 + 16962);
      LODWORD(v4) = v139;
      if ( v139 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3709,
          (unsigned int)v139);
        goto LABEL_352;
      }
      v140 = *(_QWORD *)(a1 + 16);
      if ( (v140 & 0x200) != 0 )
      {
        if ( *((_QWORD *)a2 + 8472) != v132 || *((_QWORD *)a2 + 8473) != (_QWORD)v172 )
        {
          v172 = *((_OWORD *)a2 + 4236);
          v142 = VsmmCloneTemplateApply(a1, &v172);
          LODWORD(v4) = v142;
          if ( v142 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3743,
              (unsigned int)v142);
            goto LABEL_352;
          }
          v7 = 1;
LABEL_448:
          v143 = VsmmProcessVpThreadHostingSetup(a1);
          LODWORD(v4) = v143;
          if ( v143 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3758,
              (unsigned int)v143);
            goto LABEL_450;
          }
          if ( v17 )
          {
            LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
            if ( (v4 & 0x80000000) != 0LL )
            {
              if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              {
                tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
                tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
                LODWORD(v170) = 3775;
                v185[8] = &v170;
                v185[9] = 4;
                v185[10] = &v167;
                v167 = v4;
                v185[12] = &v172;
                v185[11] = 4;
                *(_QWORD *)&v172 = v17;
                v185[13] = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140047877, 0, 0, 7, v185);
              }
              goto LABEL_450;
            }
          }
          v144 = VidThreadPoolThreadAdd(a1 + 3488);
          LODWORD(v4) = v144;
          if ( v144 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3793,
              (unsigned int)v144);
            goto LABEL_450;
          }
          v145 = *(_DWORD *)(a1 + 16);
          *(_BYTE *)(a1 + 3728) = 1;
          if ( (v145 & 0x8000) == 0 )
          {
            VsmmHvMemPreDepositForVps(a1, a2[10]);
            Pool2 = ExAllocatePool2(64, 2512LL * a2[10], 1917084758);
            *(_QWORD *)(a1 + 3208) = Pool2;
            if ( !Pool2 )
            {
              LODWORD(v4) = -1073741670;
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3814,
                3221225626LL);
              goto LABEL_450;
            }
            v147 = 0;
            if ( a2[10] )
            {
              while ( 1 )
              {
                v148 = VidVpCreate(a1, v147, a2 + 46);
                LODWORD(v4) = v148;
                if ( v148 < 0 )
                  break;
                if ( ++v147 >= a2[10] )
                  goto LABEL_465;
              }
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3832,
                (unsigned int)v148);
              goto LABEL_450;
            }
          }
LABEL_465:
          v149 = *(_QWORD *)(a1 + 32) & 0x1E0LL;
          switch ( v149 )
          {
            case ' ':
              if ( v6 )
              {
                *(_BYTE *)(a1 + 8848) = 1;
              }
              else
              {
                v150 = VsmmSvcPartitionSetup(a1);
                LODWORD(v4) = v150;
                if ( v150 < 0 )
                {
                  VidTraceErrorStatusInternal0(
                    "VidPartitionIoctlSetup",
                    "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                    3849,
                    (unsigned int)v150);
                  goto LABEL_450;
                }
              }
              goto LABEL_471;
            case '@':
              v152 = VidSnpPartitionInitialize(a1);
              LODWORD(v4) = v152;
              if ( v152 < 0 )
              {
                VidTraceErrorStatusInternal0(
                  "VidPartitionIoctlSetup",
                  "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                  3877,
                  (unsigned int)v152);
                goto LABEL_450;
              }
              if ( !_bittest64((const signed __int64 *)a2 + 2, 0x34u) )
                *(_QWORD *)(a1 + 32) |= 0x20000uLL;
              break;
            case '`':
              break;
            default:
LABEL_471:
              v151 = VsmmVsmPartitionHypervisorSetup(a1);
              LODWORD(v4) = v151;
              if ( v151 >= 0 )
              {
                if ( VID_TRACE_ETW_GUID_Context
                  && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &MSVML_VID_PARTITION_INFORMATION) )
                {
                  VidTraceStr1Int1Routine(&MSVML_VID_PARTITION_INFORMATION);
                }
                v3 = v166;
                v154 = VidPartitionTableInsertById(v166, a1);
                LODWORD(v4) = v154;
                if ( v154 >= 0 )
                {
                  v6 = 1;
                  v10 = 1;
                  v5 = 1;
                  *(_DWORD *)(a1 + 48) = 1;
                  goto LABEL_82;
                }
                VidTraceErrorStatusInternal0(
                  "VidPartitionIoctlSetup",
                  "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                  3921,
                  (unsigned int)v154);
LABEL_451:
                v6 = 1;
                v5 = 0;
                goto LABEL_82;
              }
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3899,
                (unsigned int)v151);
LABEL_450:
              v3 = v166;
              goto LABEL_451;
          }
          v153 = VsmmHwIsoPartitionSetup(a1);
          LODWORD(v4) = v153;
          if ( v153 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3891,
              (unsigned int)v153);
            goto LABEL_450;
          }
          goto LABEL_471;
        }
        if ( (v140 & 0x8000) == 0 )
        {
          v141 = VsmmProcessMemoryHostingSetup(a1);
          LODWORD(v4) = v141;
          if ( v141 < 0 )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3731,
              (unsigned int)v141);
            goto LABEL_352;
          }
        }
      }
      v7 = 0;
      goto LABEL_448;
    }
  }
  v96 = *a2;
  v97 = VidExoVpInterceptIsrCallback;
  v177 = -1;
  if ( (v89 & 0x8000) == 0 )
    v97 = VidInterceptIsrCallback;
  v98 = WinHvCreatePartitionEx(v87, v175, v90, v96, a2 + 2, &v173, &v177, v97, a1, VidHvMemLowMemPolicyCallback, a1);
  LODWORD(v4) = v98;
  if ( v98 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      3165,
      (unsigned int)v98);
    goto LABEL_79;
  }
  v99 = *(_OWORD *)(a1 + 656);
  *(_QWORD *)(a1 + 648) = v177;
  v175 = v99;
  v6 = 1;
  VidTraceRoutineGuidWithUint64(&VID_EVT_HV_PARTITION_ID);
  if ( (*(_DWORD *)(a1 + 32) & 0x8000LL) != 0 )
  {
    memset(v201, 0, sizeof(v201));
    memset(v185, 0, 0x80u);
    v100 = a2[10];
    for ( j = 0; (unsigned int)j < v100; ++*((_WORD *)v185 + v102) )
    {
      v102 = *((unsigned __int8 *)a2 + j + 184);
      j = (unsigned int)(j + 1);
    }
    v103 = a2[12] & 0x7F;
    if ( v103 )
    {
      v104 = 0;
      v105 = *((_QWORD *)v166 + 33);
      do
      {
        v106 = v104++;
        v201[2 * v106] = *(_DWORD *)(*(_QWORD *)(v105 + 8LL * *((unsigned __int8 *)a2 + v106 + 116)) + 416LL);
        LOWORD(v201[2 * v106 + 1]) = *((_WORD *)v185 + v106);
      }
      while ( v104 < v103 );
    }
    LODWORD(v4) = WinHvSetPartitionPropertyEx(*(_QWORD *)(a1 + 648), 589828, 0, v201, 8 * (a2[12] & 0x7F));
    if ( (v4 & 0x80000000) != 0LL )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v167 = 3215;
        v185[8] = &v167;
        v185[9] = 4;
        v185[10] = (char *)&v165 + 4;
        HIDWORD(v165) = v4;
        v185[12] = &v172;
        v185[11] = 4;
        *(_QWORD *)&v172 = 589828;
        v185[13] = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140047AC8, 0, 0, 7, v185);
      }
      goto LABEL_311;
    }
  }
  if ( !a2[17098] )
  {
LABEL_346:
    if ( (v87 & 0x100000) != 0 && (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
    {
      PagesForOverlay = VidHvMemAllocatePagesForOverlay(a1, 2, a1 + 10888);
      LODWORD(v4) = PagesForOverlay;
      if ( PagesForOverlay < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3311,
          (unsigned int)PagesForOverlay);
        goto LABEL_352;
      }
      v114 = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
      LODWORD(v4) = v114;
      if ( v114 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3322,
          (unsigned int)v114);
        goto LABEL_352;
      }
    }
    if ( (*(_DWORD *)(a1 + 24) & 0x40000LL) != 0 )
    {
      v115 = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
      LODWORD(v4) = v115;
      if ( v115 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3336,
          (unsigned int)v115);
        goto LABEL_352;
      }
    }
    v116 = *(_QWORD *)(a1 + 16);
    if ( (v116 & 0x8000) == 0 )
    {
      v117 = (a2[8] & 1) == 0;
      v170 = 0x3000000000LL;
      if ( !v117 )
      {
        if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
        {
          LODWORD(v4) = -1073741811;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlSetup",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            3367,
            3221225485LL);
          goto LABEL_352;
        }
        v170 = 0x83000000000LL;
      }
      if ( (v116 & 0x10) == 0 && (int)*a2 >= 1536 )
      {
        v174 = 0x1000000000000LL;
        if ( (v116 & 0x20) == 0 )
        {
          if ( (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0 )
            v28 = 0x3000000000000LL;
          v174 = v28;
        }
      }
      v118 = VidPartitionpPrivilegesUpdate(a1, &v170, &v174);
      LODWORD(v4) = v118;
      if ( v118 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSetup",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          3412,
          (unsigned int)v118);
        goto LABEL_352;
      }
    }
    v119 = WinHvInitializePartition(*(_QWORD *)(a1 + 648));
    LODWORD(v4) = v119;
    if ( v119 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        3424,
        (unsigned int)v119);
      goto LABEL_352;
    }
    v6 = 0;
    goto LABEL_376;
  }
  v107 = (char *)a2 + a2[17099];
  v108 = 0;
  HIDWORD(v165) = 0;
  while ( 1 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x8000LL) != 0 && *(_DWORD *)&v107[16 * v108] == 589828 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSetup",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        3261,
        3221225485LL);
      goto LABEL_352;
    }
    v109 = 2LL * v108;
    v110 = 0;
    if ( *(_DWORD *)&v107[16 * v108] == 589831
      || *(_DWORD *)&v107[16 * v108] == 589833
      || *(_DWORD *)&v107[16 * v108] == 589838 )
    {
      v110 = 1;
    }
    if ( !v110 )
      break;
    LODWORD(v4) = VidPartitionpSetPropertyWithPayload(
                    a1,
                    (_DWORD)a2,
                    v167,
                    *(_DWORD *)&v107[16 * v108],
                    *(_QWORD *)&v107[16 * v108 + 8]);
    if ( (v4 & 0x80000000) != 0LL )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v167 = 3278;
        v185[8] = &v167;
        v111 = &unk_1400479D6;
        v185[10] = (char *)&v165 + 4;
        v112 = *(int *)&v107[8 * v109];
        goto LABEL_339;
      }
      goto LABEL_352;
    }
LABEL_344:
    v108 = HIDWORD(v165) + 1;
    HIDWORD(v165) = v108;
    if ( v108 >= a2[17098] )
    {
      v87 = v168;
      goto LABEL_346;
    }
  }
  LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
  if ( (v4 & 0x80000000) == 0LL )
    goto LABEL_344;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
    tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
    v167 = 3293;
    v185[8] = &v167;
    v111 = &unk_140047A3B;
    v185[15] = 8;
    v185[10] = (char *)&v165 + 4;
    *(_QWORD *)&v172 = *(int *)&v107[8 * v109];
    v185[12] = &v172;
    *(_QWORD *)&v176 = *(_QWORD *)&v107[8 * v109 + 8];
    v185[14] = &v176;
    v163 = 8;
    goto LABEL_341;
  }
LABEL_352:
  v6 = 1;
LABEL_311:
  v5 = 0;
  v3 = v166;
  v7 = 0;
LABEL_82:
  if ( v171 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v171);
  if ( (v4 & 0x80000000) != 0LL && !*(_DWORD *)(a1 + 48) )
  {
    *(_DWORD *)(a1 + 48) = 2;
    if ( v6 )
    {
      if ( v5 )
        VidPartitionTableRemoveById(v3, a1);
      while ( 1 )
      {
        v155 = *(_DWORD *)(a1 + 3200);
        if ( !v155 )
          break;
        LOBYTE(v10) = 1;
        VidVpDelete(*(_QWORD *)(a1 + 3208) + 2512LL * (unsigned int)(v155 - 1), v10);
      }
      v156 = *(void **)(a1 + 3208);
      if ( v156 )
      {
        ExFreePoolWithTag(v156, 0x72446456u);
        *(_QWORD *)(a1 + 3208) = 0;
      }
      if ( *(_BYTE *)(a1 + 3728) )
      {
        VidThreadPoolThreadRemove(a1 + 3488, 0);
        *(_BYTE *)(a1 + 3728) = 0;
      }
      if ( v7 )
        VsmmClonePartitionTeardown(a1);
      VidHypercallDoorbellFree(a1);
      VsmmProcessTeardown(a1);
      VsmmPhuHvPartitionTeardown(a1);
      if ( *(_QWORD *)(a1 + 648) != -1 )
      {
        WinHvDeletePartition();
        *(_QWORD *)(a1 + 648) = -1;
      }
    }
    VsmmPhuPartitionTeardown(a1);
    VsmmPartitionSetupUndo(a1);
    VsmmMemPartTeardownPhysicalAllocationMemPart(a1);
    VsmmMemPartTeardownMemoryHostingJob(a1);
    *(_OWORD *)(a1 + 16) = v12;
    *(_QWORD *)(a1 + 32) = v11;
  }
  VidNumaRevertGroupAffinity(v183);
  if ( (*(_DWORD *)(a1 + 16) & 0x200LL) != 0 )
  {
    v158 = *(_QWORD *)(a1 + 24);
    v159 = v158 >> 9;
    v164 = *(_BYTE *)(a1 + 32) & 3;
    LOBYTE(v157) = *(_BYTE *)(a1 + 24) & 1;
    LOBYTE(v159) = (v158 & 4) != 0;
    v179 = *(_OWORD *)(a1 + 656);
    VidTraceGuidString_7Uint8_3Uint64(
      v159,
      (unsigned int)&v179,
      a1 + 120,
      v157,
      (v158 & 2) != 0,
      (v158 & 0x40) != 0,
      v159,
      (v158 & 8) != 0,
      (v158 & 0x10) != 0,
      (unsigned __int8)v158 >> 7,
      v164,
      1LL << ((v158 >> 9) & 0xF),
      1LL << ((v158 >> 13) & 0xF));
    *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 2256LL) = *(_QWORD *)(a1 + 24);
  }
  VidObjectLockRelease(a1 + 3736);
  VidObjectLockRelease(a1);
  if ( (v4 & 0x80000000) != 0LL
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(&v185[4], "VidPartitionIoctlSetup");
    tlgCreate1Sz_char(&v185[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
    LODWORD(v170) = 4079;
    v185[13] = (unsigned int)(v160 + 16);
    v185[8] = &v170;
    v192 = v185[13];
    v185[10] = &v167;
    v198 = v185[13];
    v185[12] = a1 + 656;
    v185[14] = v186;
    v185[16] = *(_QWORD *)(a1 + 128);
    v186[0] = *(unsigned __int16 *)(a1 + 120);
    *(_QWORD *)&v179 = *(_QWORD *)(a1 + 648);
    v187 = &v179;
    HIDWORD(v165) = *a2;
    v189 = (char *)&v165 + 4;
    v191 = a2 + 2;
    v161 = a2[12] & 0x7F;
    v185[9] = 4;
    LODWORD(v168) = v161;
    v193 = &v168;
    LODWORD(v166) = a2[10];
    v195 = &v166;
    v197 = a2 + 16944;
    *(_QWORD *)&v172 = *((_QWORD *)a2 + 4);
    v199 = &v172;
    v167 = v4;
    v185[11] = 4;
    v185[15] = 2;
    v186[1] = v160;
    v188 = 8;
    v190 = 4;
    v194 = 4;
    v196 = 4;
    v200 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004779E, v160, 0, v160 + 16, v185);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14008e464  mov     rax, rsp
0x14008e467  mov     [rax+20h], rbx
0x14008e46b  push    rbp
0x14008e46c  push    rsi
0x14008e46d  push    rdi
0x14008e46e  push    r12
0x14008e470  push    r13
0x14008e472  push    r14
0x14008e474  push    r15
0x14008e476  lea     rbp, [rax-3D8h]
0x14008e47d  sub     rsp, 4A0h
0x14008e484  movaps  xmmword ptr [rax-48h], xmm6
0x14008e488  movaps  xmmword ptr [rax-58h], xmm7
0x14008e48c  mov     rax, cs:__security_cookie
0x14008e493  xor     rax, rsp
0x14008e496  mov     [rbp+3D0h+var_60], rax
0x14008e49d  mov     rbx, cs:VidDeviceExtension
0x14008e4a4  xor     r15d, r15d
0x14008e4a7  xorps   xmm0, xmm0
0x14008e4aa  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008e4ae  xor     eax, eax
0x14008e4b0  mov     byte ptr [rsp+4D0h+var_460], r15b
0x14008e4b5  movups  [rbp+3D0h+var_390], xmm0
0x14008e4b9  mov     [rbp+3D0h+var_370], rax
0x14008e4bd  mov     dil, r15b
0x14008e4c0  movups  [rbp+3D0h+var_380], xmm0
0x14008e4c4  mov     sil, r15b
0x14008e4c7  mov     byte ptr [rsp+4D0h+var_460+1], r15b
0x14008e4cc  mov     r14b, r15b
0x14008e4cf  mov     byte ptr [rsp+4D0h+var_460+2], r15b
0x14008e4d4  mov     [rbp+3D0h+var_410], r15
0x14008e4d8  mov     r12, rdx
0x14008e4db  mov     [rbp+3D0h+var_3D8], r15
0x14008e4df  mov     r13, rcx
0x14008e4e2  movups  [rbp+3D0h+var_3F0], xmm0
0x14008e4e6  mov     [rsp+4D0h+var_458], rbx
0x14008e4eb  mov     [rbp+3D0h+var_450], r8d
0x14008e4ef  call    VidObjectLockAcquireExclusive
0x14008e4f4  lea     rcx, [r13+0E98h]
0x14008e4fb  call    VidObjectLockAcquireExclusive
0x14008e500  lea     rcx, [rbp+3D0h+var_400]
0x14008e504  call    VidRegistryOpenParametersKey
0x14008e509  lea     r10, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e510  mov     rax, qword ptr [rbp+3D0h+var_400]
0x14008e514  lea     r11, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008e51b  movsd   xmm7, qword ptr [r13+20h]
0x14008e521  movups  xmm6, xmmword ptr [r13+10h]
0x14008e526  mov     [rbp+3D0h+var_430], rax
0x14008e52a  cmp     [r13+30h], r15d
0x14008e52e  jz      short loc_14008E568
0x14008e530  mov     eax, [r12+20h]
0x14008e535  bt      rax, 0Bh
0x14008e53a  jnb     short loc_14008E549
0x14008e53c  cmp     [r13+21D1h], r15b
0x14008e543  jnz     loc_14008E9A8
0x14008e549  mov     r9d, 0C000000Dh
0x14008e54f  mov     r15d, r9d
0x14008e552  mov     r8d, 6F6h
0x14008e558  mov     rdx, r10
0x14008e55b  mov     rcx, r11
0x14008e55e  call    VidTraceErrorStatusInternal0
0x14008e563  jmp     loc_14008E9A8
0x14008e568  mov     rcx, 0FE00000000000000h
0x14008e572  mov     [r13+28h], r15
0x14008e576  test    [r12+20h], rcx
0x14008e57b  jz      short loc_14008E59C
0x14008e57d  mov     r9d, 0C000000Dh
0x14008e583  mov     r15d, r9d
0x14008e586  mov     r8d, 704h
0x14008e58c  mov     rdx, r10
0x14008e58f  mov     rcx, r11
0x14008e592  call    VidTraceErrorStatusInternal0
0x14008e597  jmp     loc_14008E9A8
0x14008e59c  mov     rcx, [r13+10h]
0x14008e5a0  mov     eax, [r12+28h]
0x14008e5a5  mov     rdx, rcx
0x14008e5a8  and     edx, 8000h
0x14008e5ae  jz      short loc_14008E5D3
0x14008e5b0  test    eax, eax
0x14008e5b2  jz      short loc_14008E5E0
0x14008e5b4  mov     r9d, 0C000000Dh
0x14008e5ba  mov     r15d, r9d
0x14008e5bd  mov     r8d, 70Dh
0x14008e5c3  mov     rdx, r10
0x14008e5c6  mov     rcx, r11
0x14008e5c9  call    VidTraceErrorStatusInternal0
0x14008e5ce  jmp     loc_14008E9A8
0x14008e5d3  dec     eax
0x14008e5d5  cmp     eax, 7FFh
0x14008e5da  ja      loc_140090C49
0x14008e5e0  mov     eax, [r12]
0x14008e5e4  sub     eax, 600h
0x14008e5e9  cmp     eax, 0F900h
0x14008e5ee  ja      loc_140090C2A
0x14008e5f4  test    rdx, rdx
0x14008e5f7  mov     r9b, 30h ; '0'
0x14008e5fa  lea     rdx, [r12+108F0h]
0x14008e602  jnz     short loc_14008E613
0x14008e604  mov     eax, [rdx]
0x14008e606  test    r9b, al
0x14008e609  jnz     short loc_14008E613
0x14008e60b  or      rcx, 10h
0x14008e60f  mov     [r13+10h], rcx
0x14008e613  mov     al, [r12+20h]
0x14008e618  test    al, al
0x14008e61a  jns     short loc_14008E624
0x14008e61c  and     rcx, 0FFFFFFFFFFFFFFEFh
0x14008e620  mov     [r13+10h], rcx
0x14008e624  mov     r8, [r12+20h]
0x14008e629  bt      r8, 1Eh
0x14008e62e  jnb     short loc_14008E65A
0x14008e630  mov     eax, [rdx]
0x14008e632  test    r9b, al
0x14008e635  jnz     short loc_14008E687
0x14008e637  bt      r8, 20h ; ' '
0x14008e63c  jnb     short loc_14008E648
0x14008e63e  cmp     dword ptr [r12], 605h
0x14008e646  jz      short loc_14008E652
0x14008e648  cmp     dword ptr [r12], 607h
0x14008e650  jl      short loc_14008E687
0x14008e652  or      rcx, 20h
0x14008e656  mov     [r13+10h], rcx
0x14008e65a  bt      qword ptr [r12+20h], 31h ; '1'
0x14008e661  jnb     short loc_14008E6AC
0x14008e663  test    cl, 20h
0x14008e666  jnz     short loc_14008E6A6
0x14008e668  mov     r9d, 0C000000Dh
0x14008e66e  mov     r15d, r9d
0x14008e671  mov     r8d, 74Ah
0x14008e677  mov     rdx, r10
0x14008e67a  mov     rcx, r11
0x14008e67d  call    VidTraceErrorStatusInternal0
0x14008e682  jmp     loc_14008E9A8
0x14008e687  mov     r9d, 0C000000Dh
0x14008e68d  mov     r15d, r9d
0x14008e690  mov     r8d, 740h
0x14008e696  mov     rdx, r10
0x14008e699  mov     rcx, r11
0x14008e69c  call    VidTraceErrorStatusInternal0
0x14008e6a1  jmp     loc_14008E9A8
0x14008e6a6  bts     qword ptr [r13+20h], 0Eh
0x14008e6ac  bt      qword ptr [r12+20h], 37h ; '7'
0x14008e6b3  mov     rdi, r15
0x14008e6b6  jnb     short loc_14008E6BE
0x14008e6b8  bts     qword ptr [r13+20h], 10h
0x14008e6be  test    r9b, cl
0x14008e6c1  jnz     short loc_14008E6C9
0x14008e6c3  or      rcx, 40h
0x14008e6c7  jmp     short loc_14008E6CD
0x14008e6c9  or      rcx, 8
0x14008e6cd  mov     [r13+10h], rcx
0x14008e6d1  mov     r14d, 800h
0x14008e6d7  mov     r9, qword ptr [rbp+3D0h+var_3F0+8]
0x14008e6db  mov     rdx, qword ptr [rbp+3D0h+var_3F0]
0x14008e6df  mov     r8, [r12+20h]
0x14008e6e4  mov     qword ptr [rbp+3D0h+var_420], r9
0x14008e6e8  mov     qword ptr [rbp+3D0h+var_3F0], rdx
0x14008e6ec  bt      rcx, 0Fh
0x14008e6f1  jnb     loc_14008E81F
0x14008e6f7  mov     rax, 0FFBED7C9FFFEFF9Fh
0x14008e701  test    rax, r8
0x14008e704  jz      short loc_14008E725
0x14008e706  mov     r9d, 0C000000Dh
0x14008e70c  mov     r15d, r9d
0x14008e70f  mov     r8d, 768h
0x14008e715  mov     rdx, r10
0x14008e718  mov     rcx, r11
0x14008e71b  call    VidTraceErrorStatusInternal0
0x14008e720  jmp     loc_14008E9A2
0x14008e725  cmp     [r12+108C0h], rdx
0x14008e72d  jnz     loc_14008E800
0x14008e733  cmp     [r12+108C8h], r9
0x14008e73b  jnz     loc_14008E800
0x14008e741  test    dword ptr [r12+30h], 180h
0x14008e74a  jz      short loc_14008E76B
0x14008e74c  mov     r9d, 0C000000Dh
0x14008e752  mov     r15d, r9d
0x14008e755  mov     r8d, 77Fh
0x14008e75b  mov     rdx, r10
0x14008e75e  mov     rcx, r11
0x14008e761  call    VidTraceErrorStatusInternal0
0x14008e766  jmp     loc_14008E9A2
0x14008e76b  bts     rcx, 9
0x14008e770  mov     r8d, 1
0x14008e776  mov     [r13+10h], rcx
0x14008e77a  mov     rax, 200000000h
0x14008e784  mov     rdx, [r12+20h]
0x14008e789  and     rdx, rax
0x14008e78c  mov     rax, cs:VidDeviceExtension
0x14008e793  bts     rdx, 1Ch
0x14008e798  shr     rdx, 14h
0x14008e79c  mov     ecx, [rax+288h]
0x14008e7a2  mov     rax, cs:VidDeviceExtension
0x14008e7a9  shr     rcx, 5
0x14008e7ad  and     rcx, r8
0x14008e7b0  mov     r15, rcx
0x14008e7b3  mov     eax, [rax+288h]
0x14008e7b9  bt      eax, 5
0x14008e7bd  cmovb   rdi, r8
0x14008e7c1  mov     r8, [r12+20h]
0x14008e7c6  or      r15, 2
0x14008e7ca  bt      eax, 5
0x14008e7ce  cmovnb  r15, rcx
0x14008e7d2  bt      r8, 2Dh ; '-'
0x14008e7d7  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008e7db  jnb     short loc_14008E7E2
0x14008e7dd  bts     rdx, 18h
0x14008e7e2  mov     rax, r8
0x14008e7e5  mov     rbx, rdx
0x14008e7e8  or      rbx, r14
0x14008e7eb  and     eax, 10000h
0x14008e7f0  or      rdi, 3FFEh
0x14008e7f7  test    rax, rax
0x14008e7fa  cmovnz  rbx, rdx
0x14008e7fe  jmp     short loc_14008E84C
0x14008e800  mov     r9d, 0C000000Dh
0x14008e806  mov     r15d, r9d
0x14008e809  mov     r8d, 775h
0x14008e80f  mov     rdx, r10
0x14008e812  mov     rcx, r11
0x14008e815  call    VidTraceErrorStatusInternal0
0x14008e81a  jmp     loc_14008E9A2
0x14008e81f  bt      r8, 2Dh ; '-'
0x14008e824  jnb     short loc_14008E845
0x14008e826  mov     r9d, 0C000000Dh
0x14008e82c  mov     r15d, r9d
0x14008e82f  mov     r8d, 7B9h
0x14008e835  mov     rdx, r10
0x14008e838  mov     rcx, r11
0x14008e83b  call    VidTraceErrorStatusInternal0
0x14008e840  jmp     loc_14008E9A2
0x14008e845  mov     rbx, r15
0x14008e848  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008e84c  test    r8b, 8
0x14008e850  jz      short loc_14008E898
0x14008e852  mov     rcx, r13
0x14008e855  call    VidCurrentProcessIsTrusted
0x14008e85a  test    eax, eax
0x14008e85c  jnz     short loc_14008E885
0x14008e85e  mov     r15d, 0C0000022h
0x14008e864  mov     r9d, r15d
0x14008e867  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e86e  mov     r8d, 7CAh
0x14008e874  lea     rcx, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008e87b  call    VidTraceErrorStatusInternal0
0x14008e880  jmp     loc_14008E99D
0x14008e885  or      qword ptr [r13+28h], 6
0x14008e88a  lea     r10, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e891  lea     r11, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008e898  test    byte ptr [r12+20h], 10h
0x14008e89e  jz      short loc_14008E8A5
0x14008e8a0  or      qword ptr [r13+28h], 2
0x14008e8a5  mov     rdx, [r12+20h]
0x14008e8aa  bt      rdx, 20h ; ' '
0x14008e8af  jnb     short loc_14008E8B6
0x14008e8b1  bts     rbx, 0Ch
0x14008e8b6  mov     r8, 800000000h
0x14008e8c0  mov     rcx, rbx
0x14008e8c3  or      rcx, 1
0x14008e8c7  mov     rax, rdx
0x14008e8ca  test    dl, 20h
0x14008e8cd  cmovz   rcx, rbx
0x14008e8d1  and     rax, r8
0x14008e8d4  mov     r8, rcx
0x14008e8d7  bts     r8, 0Eh
0x14008e8dc  test    rax, rax
0x14008e8df  cmovz   r8, rcx
0x14008e8e3  test    dl, 40h
0x14008e8e6  jz      short loc_14008E8F2
0x14008e8e8  or      r8, 2
0x14008e8ec  bts     qword ptr [r13+10h], 8
0x14008e8f2  mov     r9, [r12+20h]
0x14008e8f7  mov     rdx, r8
0x14008e8fa  bts     rdx, 0Fh
0x14008e8ff  mov     rbx, 1000000000000h
0x14008e909  bt      r9, 24h ; '$'
0x14008e90e  mov     rax, r9
0x14008e911  cmovnb  rdx, r8
0x14008e915  mov     rcx, rdx
0x14008e918  bts     rcx, 1Bh
0x14008e91d  test    rbx, r9
0x14008e920  cmovz   rcx, rdx
0x14008e924  mov     rdx, 2000000000h
0x14008e92e  and     rax, rdx
0x14008e931  mov     rdx, rcx
0x14008e934  bts     rdx, 10h
0x14008e939  test    rax, rax
0x14008e93c  cmovz   rdx, rcx
0x14008e940  bt      r9, 26h ; '&'
0x14008e945  jnb     short loc_14008E94C
0x14008e947  bts     rdx, 11h
0x14008e94c  mov     rsi, rdx
0x14008e94f  mov     rax, 40000000000h
0x14008e959  bts     rsi, 12h
0x14008e95e  mov     rcx, r9
0x14008e961  bt      r9, 27h ; '''
0x14008e966  cmovnb  rsi, rdx
0x14008e96a  and     rcx, rax
0x14008e96d  jz      loc_14008EA0E
0x14008e973  bt      r9, 2Bh ; '+'
  ... truncated ...
```
