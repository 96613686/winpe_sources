# VsmmCreateMemoryBlockGpaRange

- ea: `0x1400dc1a0`
- end: `0x1400dd4ed`
- name: `VsmmCreateMemoryBlockGpaRange`
- size: `4941`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `29`
- tags: ``

## callers

- `0x140035708`
- `0x14008bea0`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002e270`
- `0x14002f724`
- `0x1400305c0`
- `0x1400347a4`
- `0x140034b64`
- `0x1400386a0`
- `0x14009c5e8`
- `0x14009c92c`
- `0x1400a04a0`
- `0x1400ac19c`
- `0x1400aecac`
- `0x1400b2d50`
- `0x1400d40c8`
- `0x1400dc1a0`
- `0x1400f1160`
- `0x1400f1ea0`
- `0x1400f2450`
- `0x1400f5094`
- `0x1400f610c`
- `0x1400f6da8`
- `0x1400f8228`
- `0x1400f93e4`
- `0x1400fb39c`
- `0x1400fe190`
- `0x1400fe864`

## string_xrefs

- `0x1400dc265`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc2a2`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc2d2`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc30c`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc33b`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc36c`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc3db`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc519`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc597`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc63c`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc712`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc7b7`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc834`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dc920`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcaaf`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcb06`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcbd2`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcd08`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcd5e`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcdfe`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dce7e`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dcfda`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dd139`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dd1bd`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dd20d`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dd28b`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400dd333`: `VsmmCreateMemoryBlockGpaRange`

## pseudocode

```c
__int64 __fastcall VsmmCreateMemoryBlockGpaRange(
        _DWORD *P,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int a8,
        _QWORD *a9)
{
  __int64 v10; // rsi
  __int64 v11; // r13
  __int64 v12; // r15
  __int64 v13; // rdi
  int Entry; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // r15d
  __int64 v18; // r9
  __int64 v19; // r10
  void *v20; // rdx
  __int64 *v21; // rax
  __int64 v22; // r12
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // r8d
  __int64 v26; // r8
  int v27; // ecx
  int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // r11d
  _QWORD *v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // edx
  __int64 v38; // rcx
  int v39; // r11d
  _QWORD *v40; // rcx
  __int64 v41; // r9
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // r9
  void *v44; // rdx
  int v45; // r11d
  __int64 v46; // r9
  __int64 v47; // rdx
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // r12
  __int64 v51; // rcx
  __int64 v52; // rcx
  unsigned __int64 v53; // rdx
  int v54; // r15d
  __int64 v55; // rdx
  __int64 v56; // rbx
  int v57; // eax
  int v58; // r8d
  int v59; // eax
  int v60; // eax
  __int64 v61; // r8
  __int64 v63; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  char v66; // [rsp+58h] [rbp-A8h]
  _QWORD *v67; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v74[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+B8h] [rbp-48h]
  _BYTE v76[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v77[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v78[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+108h] [rbp+8h]
  __int64 *v81; // [rsp+110h] [rbp+10h]
  __int64 v82; // [rsp+118h] [rbp+18h]
  char *v83; // [rsp+120h] [rbp+20h]
  __int64 v84; // [rsp+128h] [rbp+28h]
  int *v85; // [rsp+130h] [rbp+30h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  __int64 v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h] BYREF
  int v89; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v90; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]
  __int64 *v92; // [rsp+160h] [rbp+60h]
  __int64 v93; // [rsp+168h] [rbp+68h]
  __int64 *v94; // [rsp+170h] [rbp+70h]
  __int64 v95; // [rsp+178h] [rbp+78h]
  __int64 *v96; // [rsp+180h] [rbp+80h]
  __int64 v97; // [rsp+188h] [rbp+88h]
  __int64 *v98; // [rsp+190h] [rbp+90h]
  __int64 v99; // [rsp+198h] [rbp+98h]
  __int64 *v100; // [rsp+1A0h] [rbp+A0h]
  __int64 v101; // [rsp+1A8h] [rbp+A8h]
  __int64 *v102; // [rsp+1B0h] [rbp+B0h]
  __int64 v103; // [rsp+1B8h] [rbp+B8h]
  __int64 *v104; // [rsp+1C0h] [rbp+C0h]
  __int64 v105; // [rsp+1C8h] [rbp+C8h]

  v70 = a4;
  v75 = 0;
  v10 = 0;
  v63 = a3;
  v11 = 0;
  v68 = a2;
  v67 = a9;
  v12 = a3;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v74[0] = 0;
  *a9 = -1;
  v74[1] = 0;
  VidObjectLockAcquireExclusive(P + 934);
  v13 = a6;
  v69 = (unsigned __int8)a6 & 0x80;
  if ( ((a6 & 0x80) != 0) != (a7 != 0) )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmCreateMemoryBlockGpaRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
      1161,
      3221225485LL);
LABEL_26:
    v22 = (__int64)a7;
    goto LABEL_27;
  }
  if ( (a6 & 0x80) != 0 && !*((_BYTE *)P + 8657) )
  {
    v15 = VsmmPhuCheckObjectRestore(P);
    Entry = v15;
    if ( v15 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmCreateMemoryBlockGpaRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
        1176,
        (unsigned int)v15);
      goto LABEL_26;
    }
    if ( P[2159] != 2 )
    {
      Entry = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmCreateMemoryBlockGpaRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
        1186,
        3221225485LL);
      goto LABEL_26;
    }
  }
  v16 = VsmmGpaRangeValidatePageRange(P, v68, v12);
  Entry = v16;
  if ( v16 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmCreateMemoryBlockGpaRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
      1197,
      (unsigned int)v16);
    goto LABEL_26;
  }
  if ( (a6 & 0xFFFFFFFFFFFFFC00uLL) != 0 )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmCreateMemoryBlockGpaRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
      1204,
      3221225485LL);
    goto LABEL_26;
  }
  if ( (a6 & 4) != 0 )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmCreateMemoryBlockGpaRange",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
      1214,
      3221225485LL);
    goto LABEL_26;
  }
  if ( (a6 & 0x261) != 0 || (v17 = 0, a8 == 1) )
    v17 = 1;
  if ( (a6 & 0x100) != 0 )
  {
    if ( a8 != 1 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v65) = 1243;
      v79 = &v65;
      v20 = &unk_140058BB6;
      v21 = &v64;
      LODWORD(v64) = -1073741811;
      goto LABEL_23;
    }
    if ( (P[2194] & 4) == 0 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1250;
      v79 = &v64;
      v20 = &unk_140058908;
      v21 = &v65;
      LODWORD(v65) = -1073741811;
      goto LABEL_23;
    }
    if ( (a6 & 0x80) != 0 )
    {
      Entry = -1073741637;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1264;
      v79 = &v64;
      v20 = &unk_140058976;
      v21 = &v65;
      LODWORD(v65) = v25;
LABEL_23:
      v81 = v21;
      v83 = (char *)(P + 164);
      v85 = &v88;
      v87 = *((_QWORD *)P + 16);
      v88 = *((unsigned __int16 *)P + 60);
      v67 = (_QWORD *)*((_QWORD *)P + 81);
      v80 = v19;
      v82 = v19;
      v84 = 16;
      v86 = 2;
      v89 = v18;
      v91 = 8;
LABEL_24:
      v90 = (__int64 *)&v67;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v20, 0, v18, 10, v76);
LABEL_25:
      v12 = v63;
      goto LABEL_26;
    }
  }
  else if ( (a6 & 0x80) != 0 )
  {
    if ( *((_BYTE *)P + 8657) )
    {
      v22 = (__int64)a7;
      Entry = VsmmGpaRangeLookupByPersistId(P, a7, a8, v67);
      if ( Entry < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
        tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v64) = 1287;
        v79 = &v64;
        v80 = 4;
        v81 = (__int64 *)&v67;
        v67 = a7;
        v82 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400589E4, 0, 0, 6, v76);
      }
      v12 = v63;
      goto LABEL_27;
    }
    v17 |= 2u;
  }
  if ( (unsigned int)VsmmGpaRangeListOverlapCheck((_DWORD)P, v68, v63, v17, 0) )
  {
    Entry = -1070137272;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1306;
      v79 = &v64;
      v80 = 4;
      v81 = &v65;
      LODWORD(v65) = v17;
      v82 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058A24, 0, 0, 6, v76);
    }
    goto LABEL_25;
  }
  Entry = VsmmMemoryBlockLookupByHandle((_DWORD)P, v70, a8, 1, (__int64)&v64);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1324);
    v10 = v64;
    goto LABEL_25;
  }
  v10 = v64;
  v27 = *(_DWORD *)(v64 + 264);
  if ( (v27 & 8) != 0 )
  {
    Entry = -1070137326;
    goto LABEL_25;
  }
  if ( (a6 & 0x200) != 0 )
  {
    if ( (P[4] & 0x10) != 0 )
    {
      Entry = -1073741637;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1356;
      v79 = &v64;
      v81 = &v65;
      v80 = 4;
      LODWORD(v65) = v28;
      v82 = 4;
      v29 = *(_QWORD *)(v10 + 8) + 656LL;
      v84 = 16;
      v83 = (char *)v29;
      v30 = *(_QWORD *)(v10 + 8);
      v31 = *(_QWORD *)(v30 + 128);
      v88 = *(unsigned __int16 *)(v30 + 120);
      v20 = &unk_14005873C;
      v85 = &v88;
      v86 = 2;
      v87 = v31;
      v89 = v32;
      v33 = *(_QWORD **)(*(_QWORD *)(v10 + 8) + 648LL);
      v91 = v34;
      v18 = 0;
      v67 = v33;
      goto LABEL_24;
    }
    if ( (a6 & 0xFFFFFFFFFFFFFC7FuLL) != 0 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
        tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v64) = 1374;
        v79 = &v64;
        v81 = &v65;
        v80 = 4;
        LODWORD(v65) = -1073741811;
        v82 = 4;
        v35 = *(_QWORD *)(v10 + 8) + 656LL;
        v84 = 16;
        v83 = (char *)v35;
        v36 = *(_QWORD *)(v10 + 8);
        v37 = *(unsigned __int16 *)(v36 + 120);
        v38 = *(_QWORD *)(v36 + 128);
        v85 = &v88;
        v88 = v37;
        v86 = 2;
        v87 = v38;
        v89 = v39;
        v40 = *(_QWORD **)(*(_QWORD *)(v10 + 8) + 648LL);
        v90 = (__int64 *)&v67;
        v92 = &v69;
        v91 = v41;
        v93 = v41;
        v67 = v40;
        v69 = a6;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400587AA, 0, 0, 11, v76);
      }
      goto LABEL_25;
    }
    v42 = 0;
  }
  else
  {
    v42 = a6 & 0xFFFFFFFFFFFFFC7FuLL;
  }
  LOBYTE(v26) = 32;
  if ( a8 )
  {
    v12 = v63;
    if ( a8 != 1 )
      goto LABEL_76;
    v43 = a5;
    if ( a5 || v63 != *(_QWORD *)(v64 + 40) || v42 )
      goto LABEL_76;
  }
  else
  {
    if ( ((a6 & 1) != 0 || (a6 & 0x20) != 0) && (a6 & 2) != 0 || (a6 & 8) != 0 && ((v27 & 1) == 0 || (a6 & 0x80) != 0) )
    {
      Entry = -1073741811;
      goto LABEL_25;
    }
    v12 = v63;
    if ( (a6 & 0xFFFFFFFFFFFFFF2FuLL) != 0 && (a6 & 0x40) != 0 )
    {
LABEL_76:
      Entry = -1073741811;
      goto LABEL_26;
    }
    v43 = a5;
  }
  if ( *(_QWORD *)(v64 + 232) == -1 )
  {
    Entry = -1070137322;
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1458);
    goto LABEL_26;
  }
  if ( *(_DWORD *)(v64 + 224) && (P[4] & 2) == 0 )
  {
    Entry = -1070137326;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_26;
    tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v64) = 1469;
    v44 = &unk_14005881F;
    goto LABEL_90;
  }
  if ( *(_DWORD *)(v64 + 244) == 1 && (v43 || v12 != *(_QWORD *)(v64 + 40)) )
  {
    Entry = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1490;
      v79 = &v64;
      v80 = 4;
      v81 = &v65;
      v83 = (char *)(P + 164);
      v85 = &v88;
      v87 = *((_QWORD *)P + 16);
      v88 = *((unsigned __int16 *)P + 60);
      v67 = (_QWORD *)*((_QWORD *)P + 81);
      v90 = (__int64 *)&v67;
      v92 = &v69;
      v94 = &v63;
      LODWORD(v65) = -1073741811;
      v82 = 4;
      v84 = 16;
      v86 = 2;
      v89 = v45;
      v91 = 8;
      v69 = v46;
      v93 = 8;
      v63 = v12;
      v95 = 8;
      v71 = *(_QWORD *)(v10 + 40);
      v96 = &v71;
      v97 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058874, 0, 0, 13, v76);
    }
    goto LABEL_26;
  }
  if ( (a6 & 1) != 0 )
  {
    if ( *(_QWORD *)&P[2 * *(unsigned __int8 *)(v64 + 16) + 2246] )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1504);
      goto LABEL_26;
    }
    if ( (*(_DWORD *)(v64 + 264) & 1) == 0 )
      goto LABEL_76;
    if ( *(_DWORD *)(v64 + 224) )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_26;
      tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v64) = 1529;
      v44 = &unk_1400585CD;
      goto LABEL_90;
    }
    if ( v43 )
      goto LABEL_76;
    v47 = *(_QWORD *)(v64 + 40);
    if ( v12 != v47 )
      goto LABEL_76;
    v48 = v68;
    v49 = v47 - 1;
    v50 = *(_QWORD *)(v64 + 48) + v68 - 1;
    goto LABEL_133;
  }
  if ( (*(_DWORD *)(v64 + 264) & 1) != 0 && !*(_DWORD *)(v64 + 224) )
  {
    Entry = -1073741811;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_26;
    tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v64) = 1558;
    v44 = &unk_140058622;
LABEL_90:
    v80 = 4;
    v79 = &v64;
    LODWORD(v65) = *(_DWORD *)(v10 + 224);
    v81 = &v65;
    v82 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v44, 0, 0, 6, v76);
    goto LABEL_26;
  }
  v48 = v68;
  v49 = *(_QWORD *)(v64 + 48) - 1LL;
  v50 = v12 + v68 - 1;
  if ( (a6 & 0x20) != 0 )
  {
    if ( (*(_DWORD *)(v64 + 264) & 0x20) == 0 )
      goto LABEL_76;
    if ( !*(_QWORD *)(v64 + 712) && P[2158] == 2 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1586);
      goto LABEL_26;
    }
    v13 = a6 | 0x2010;
  }
  else
  {
    v26 = *(unsigned int *)(v64 + 264);
    if ( (a6 & 0x40) != 0 )
    {
      if ( (v26 & 0x40) == 0 )
        goto LABEL_76;
      v13 = a6 | 0x2000;
    }
    else if ( (v26 & 0x40) != 0 )
    {
      goto LABEL_76;
    }
    if ( (v26 & 0x20) != 0 )
      goto LABEL_76;
    v51 = v13 | 0x2010;
    if ( (v13 & 0x200) == 0 )
      v51 = v13;
    v13 = v51;
    if ( a8 == 1 )
    {
      if ( (v51 & 0x200) == 0 )
      {
        v13 = v51 | 0x2000;
        if ( (P[8] & 0x1E0LL) == 0 )
          v13 = v51 | 0x12000;
      }
    }
    else if ( (P[4] & 0x40) != 0 || (v26 & 1) != 0 )
    {
LABEL_133:
      v13 |= 0x10uLL;
    }
  }
  v52 = v13 | 0x2000;
  if ( (P[4] & 1) != 0 )
    v52 = v13;
  v13 = v52;
  if ( v43 > v49 || v12 - 1 > v49 || (v53 = v49 - v12 + 1, v53 < v43) || v50 < v48 )
  {
    Entry = -1070137325;
    goto LABEL_26;
  }
  if ( (v52 & 0x48) != 0 )
  {
    v13 = v52 & 0xFFFFFFFFFFFFFFF7uLL;
    v54 = VsmmVsmAnyDefaultVtlProtectionsRequired(P, v53, v26);
  }
  else
  {
    v54 = 0;
  }
  v55 = *(unsigned __int8 *)(v10 + 16);
  if ( (_BYTE)v55 != 0xFF && *(_QWORD *)&P[4 * v55 + 544] )
    VidNumaSetGroupAffinity(P, v55, v74);
  Entry = VsmmGpaRangeAlloc(P, v63, (__int64)&v65);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1749);
    v11 = v65;
    goto LABEL_25;
  }
  v11 = v65;
  VsmmGpaRangeInitializeMbBacked(v65, v10, a5);
  v56 = v68;
  *(_QWORD *)(v11 + 264) = v50;
  if ( (v13 & 1) != 0 )
    *(_QWORD *)(v10 + 944) = v56 & 0x3FFFF;
  _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)P + 191) + 784LL));
  _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)P + 191) + ((v13 & 2) != 0 ? 800LL : 792LL)), v63);
  if ( v69 )
  {
    Entry = VsmmPhuStoreGpaRangeRestore(v11, (_DWORD)a7, v56, v63, a5, v13);
    if ( Entry < 0 )
      goto LABEL_25;
  }
  else
  {
    VsmmHvMemPreDepositForGpaRange(v11);
    if ( (v13 & 0x20) != 0 )
      *(_DWORD *)(v10 + 264) |= 0x800u;
    if ( v54 || (v57 = 8, (v13 & 0x100) != 0) )
      v57 = 9;
    Entry = VsmmAdjustGpaSpaceForMemoryBlockRange((_DWORD)P, v56, v10, a5, v50 - v56 + 1, *(_DWORD *)(v11 + 292), v57);
    if ( Entry < 0 )
      goto LABEL_25;
    *(_DWORD *)(v11 + 292) |= 0x400u;
    if ( *(_DWORD *)(v10 + 244) == 1 )
      *(_DWORD *)(v10 + 248) = 1;
  }
  Entry = VsmmGpaRangeListInsert(P, v11);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1872);
    goto LABEL_25;
  }
  v66 = 1;
  if ( v69 )
    goto LABEL_171;
  if ( v54 )
  {
    v60 = VsmmVsmApplyDefaultVtlProtectionToGpaRange(
            (_DWORD)P,
            1,
            v11,
            *(_QWORD *)(v11 + 256),
            *(_QWORD *)(v11 + 264) - *(_QWORD *)(v11 + 256) + 1LL);
    Entry = v60;
    if ( v60 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmCreateMemoryBlockGpaRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
        1904,
        (unsigned int)v60);
      goto LABEL_25;
    }
LABEL_170:
    Entry = VsmmAdjustGpaSpaceForMemoryBlockRange((_DWORD)P, v68, v10, a5, v50 - v68 + 1, *(_DWORD *)(v11 + 292), 0);
    if ( Entry < 0 )
      goto LABEL_25;
    goto LABEL_171;
  }
  if ( (v13 & 0x100) != 0 )
  {
    LOBYTE(v58) = 2;
    v59 = VsmmVsmModifyGpaRangeVtlProtection(
            (_DWORD)P,
            0,
            v58,
            0,
            v11,
            *(_QWORD *)(v11 + 256),
            *(_QWORD *)(v11 + 264) - *(_QWORD *)(v11 + 256) + 1LL,
            0);
    Entry = v59;
    if ( v59 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmCreateMemoryBlockGpaRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
        1923,
        (unsigned int)v59);
      goto LABEL_25;
    }
    goto LABEL_170;
  }
LABEL_171:
  Entry = VidHandleTableAllocateEntry(P + 816, v11, v11 + 248);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1959);
    goto LABEL_25;
  }
  v12 = v63;
  v22 = (__int64)a7;
  *v67 = *(_QWORD *)(v11 + 248);
  if ( *(_QWORD *)(v10 + 40) != *(_QWORD *)(v10 + 48) )
    *(_QWORD *)&P[2 * *(unsigned __int8 *)(v10 + 16) + 2246] = *(_QWORD *)(v11 + 264) + 1LL;
LABEL_27:
  VidObjectLockRelease(P + 934);
  if ( Entry < 0 )
  {
    if ( v11 )
    {
      if ( v66 )
      {
        LOBYTE(v23) = 1;
        VidOpCtrlBlock(v11 + 8, v23);
      }
      VsmmGpaRangeRelease(v24, v11, 0);
    }
    else if ( v10 )
    {
      VidOpCtrlFinish(v10 + 128);
    }
  }
  VidNumaRevertGroupAffinity(v74);
  if ( Entry < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v77, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v78, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v64) = 2063;
    v79 = &v64;
    v80 = 4;
    v81 = &v65;
    LODWORD(v65) = Entry;
    v83 = (char *)(P + 164);
    v82 = 4;
    v85 = &v88;
    v87 = *((_QWORD *)P + 16);
    v88 = *((unsigned __int16 *)P + 60);
    v71 = *((_QWORD *)P + 81);
    v90 = &v71;
    v67 = (_QWORD *)v68;
    v92 = (__int64 *)&v67;
    v94 = &v69;
    v96 = &v70;
    v68 = a5;
    v98 = &v68;
    v100 = &v72;
    v102 = &v73;
    LODWORD(v63) = a8;
    v104 = &v63;
    v84 = 16;
    v86 = 2;
    v89 = v61;
    v91 = 8;
    v93 = 8;
    v69 = v12;
    v95 = 8;
    v97 = 8;
    v99 = 8;
    v72 = v13;
    v101 = 8;
    v73 = v22;
    v103 = 8;
    v105 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058677, v61, 0, 17, v76);
  }
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1400dc1a0  push    rbp
0x1400dc1a2  push    rbx
0x1400dc1a3  push    rsi
0x1400dc1a4  push    rdi
0x1400dc1a5  push    r12
0x1400dc1a7  push    r13
0x1400dc1a9  push    r14
0x1400dc1ab  push    r15
0x1400dc1ad  lea     rbp, [rsp-0E8h]
0x1400dc1b5  sub     rsp, 1E8h
0x1400dc1bc  mov     rax, cs:__security_cookie
0x1400dc1c3  xor     rax, rsp
0x1400dc1c6  mov     [rbp+120h+var_50], rax
0x1400dc1cd  mov     rax, [rbp+120h+arg_40]
0x1400dc1d4  mov     r14, rcx
0x1400dc1d7  xor     ecx, ecx
0x1400dc1d9  mov     [rsp+220h+var_1A8], r9
0x1400dc1de  xorps   xmm0, xmm0
0x1400dc1e1  mov     [rbp+120h+var_168], rcx
0x1400dc1e5  xor     esi, esi
0x1400dc1e7  mov     [rsp+220h+var_1E0], r8
0x1400dc1ec  xor     r13d, r13d
0x1400dc1ef  mov     [rsp+220h+var_1B8], rdx
0x1400dc1f4  lea     rcx, [r14+0E98h]
0x1400dc1fb  mov     [rsp+220h+var_1C0], rax
0x1400dc200  mov     r15, r8
0x1400dc203  mov     [rsp+220h+var_1D8], rsi
0x1400dc208  mov     [rsp+220h+var_1D0], r13
0x1400dc20d  mov     [rsp+220h+var_1C8], sil
0x1400dc212  movups  [rbp+120h+var_188], xmm0
0x1400dc216  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400dc21d  movups  [rbp+120h+var_178], xmm0
0x1400dc221  call    VidObjectLockAcquireExclusive
0x1400dc226  mov     rdi, [rbp+120h+arg_28]
0x1400dc22d  mov     rdx, [rbp+120h+arg_30]
0x1400dc234  mov     r12, rdi
0x1400dc237  and     r12d, 80h
0x1400dc23e  mov     [rsp+220h+var_1B0], r12
0x1400dc243  setnz   cl
0x1400dc246  test    rdx, rdx
0x1400dc249  setnz   al
0x1400dc24c  cmp     cl, al
0x1400dc24e  jz      short loc_1400DC276
0x1400dc250  mov     ebx, 0C000000Dh
0x1400dc255  mov     r9d, ebx
0x1400dc258  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc25f  mov     r8d, 489h
0x1400dc265  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc26c  call    VidTraceErrorStatusInternal0
0x1400dc271  jmp     loc_1400DC4A4
0x1400dc276  test    r12, r12
0x1400dc279  jz      short loc_1400DC2E3
0x1400dc27b  cmp     [r14+21D1h], sil
0x1400dc282  jnz     short loc_1400DC2E3
0x1400dc284  mov     rcx, r14
0x1400dc287  call    VsmmPhuCheckObjectRestore
0x1400dc28c  mov     ebx, eax
0x1400dc28e  test    eax, eax
0x1400dc290  jns     short loc_1400DC2B3
0x1400dc292  mov     r9d, eax
0x1400dc295  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc29c  mov     r8d, 498h
0x1400dc2a2  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc2a9  call    VidTraceErrorStatusInternal0
0x1400dc2ae  jmp     loc_1400DC4A4
0x1400dc2b3  cmp     dword ptr [r14+21BCh], 2
0x1400dc2bb  jz      short loc_1400DC2E3
0x1400dc2bd  mov     ebx, 0C000000Dh
0x1400dc2c2  mov     r9d, ebx
0x1400dc2c5  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc2cc  mov     r8d, 4A2h
0x1400dc2d2  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc2d9  call    VidTraceErrorStatusInternal0
0x1400dc2de  jmp     loc_1400DC4A4
0x1400dc2e3  mov     rdx, [rsp+220h+var_1B8]
0x1400dc2e8  mov     r8, r15
0x1400dc2eb  mov     rcx, r14
0x1400dc2ee  call    VsmmGpaRangeValidatePageRange
0x1400dc2f3  xor     r9d, r9d
0x1400dc2f6  mov     ebx, eax
0x1400dc2f8  test    eax, eax
0x1400dc2fa  jns     short loc_1400DC31D
0x1400dc2fc  mov     r9d, eax
0x1400dc2ff  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc306  mov     r8d, 4ADh
0x1400dc30c  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc313  call    VidTraceErrorStatusInternal0
0x1400dc318  jmp     loc_1400DC4A4
0x1400dc31d  test    rdi, 0FFFFFFFFFFFFFC00h
0x1400dc324  jz      short loc_1400DC34C
0x1400dc326  mov     ebx, 0C000000Dh
0x1400dc32b  mov     r9d, ebx
0x1400dc32e  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc335  mov     r8d, 4B4h
0x1400dc33b  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc342  call    VidTraceErrorStatusInternal0
0x1400dc347  jmp     loc_1400DC4A4
0x1400dc34c  mov     r10d, 4
0x1400dc352  test    r10b, dil
0x1400dc355  jz      short loc_1400DC37D
0x1400dc357  mov     ebx, 0C000000Dh
0x1400dc35c  mov     r9d, ebx
0x1400dc35f  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc366  mov     r8d, 4BEh
0x1400dc36c  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc373  call    VidTraceErrorStatusInternal0
0x1400dc378  jmp     loc_1400DC4A4
0x1400dc37d  mov     ebx, [rbp+120h+arg_38]
0x1400dc383  test    rdi, 261h
0x1400dc38a  jnz     short loc_1400DC394
0x1400dc38c  mov     r15d, r9d
0x1400dc38f  cmp     ebx, 1
0x1400dc392  jnz     short loc_1400DC39A
0x1400dc394  mov     r15d, 1
0x1400dc39a  mov     ecx, 100h
0x1400dc39f  test    rcx, rdi
0x1400dc3a2  jz      loc_1400DC5DE
0x1400dc3a8  cmp     ebx, 1
0x1400dc3ab  jz      loc_1400DC4EA
0x1400dc3b1  mov     eax, cs:dword_140065110
0x1400dc3b7  mov     ebx, 0C000000Dh
0x1400dc3bc  cmp     eax, 2
0x1400dc3bf  jbe     loc_1400DC49F
0x1400dc3c5  mov     edx, ecx
0x1400dc3c7  lea     rcx, dword_140065110
0x1400dc3ce  call    _tlgKeywordOn
0x1400dc3d3  test    al, al
0x1400dc3d5  jz      loc_1400DC49F
0x1400dc3db  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc3e2  lea     rcx, [rbp+120h+var_140]
0x1400dc3e6  call    _tlgCreate1Sz_char
0x1400dc3eb  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc3f2  lea     rcx, [rbp+120h+var_130]
0x1400dc3f6  call    _tlgCreate1Sz_char
0x1400dc3fb  lea     rax, [rsp+220h+var_1D0]
0x1400dc400  mov     dword ptr [rsp+220h+var_1D0], 4DBh
0x1400dc408  mov     [rbp+120h+var_120], rax
0x1400dc40c  lea     rdx, unk_140058BB6
0x1400dc413  lea     rax, [rsp+220h+var_1D8]
0x1400dc418  mov     dword ptr [rsp+220h+var_1D8], ebx
0x1400dc41c  mov     [rbp+120h+var_110], rax
0x1400dc420  lea     rax, [r14+290h]
0x1400dc427  mov     [rbp+120h+var_100], rax
0x1400dc42b  lea     rax, [rbp+120h+var_D8]
0x1400dc42f  mov     [rbp+120h+var_F0], rax
0x1400dc433  mov     rax, [r14+80h]
0x1400dc43a  mov     [rbp+120h+var_E0], rax
0x1400dc43e  movzx   eax, word ptr [r14+78h]
0x1400dc443  mov     [rbp+120h+var_D8], eax
0x1400dc446  mov     rax, [r14+288h]
0x1400dc44d  mov     [rsp+220h+var_1C0], rax
0x1400dc452  mov     [rbp+120h+var_118], r10
0x1400dc456  mov     [rbp+120h+var_108], r10
0x1400dc45a  mov     [rbp+120h+var_F8], 10h
0x1400dc462  mov     [rbp+120h+var_E8], 2
0x1400dc46a  mov     [rbp+120h+var_D4], r9d
0x1400dc46e  mov     [rbp+120h+var_C8], 8
0x1400dc476  lea     rax, [rsp+220h+var_1C0]
0x1400dc47b  mov     [rbp+120h+var_D0], rax
0x1400dc47f  lea     rax, [rbp+120h+var_160]
0x1400dc483  mov     [rsp+220h+var_1F8], rax
0x1400dc488  mov     dword ptr [rsp+220h+var_200], 0Ah
0x1400dc490  xor     r8d, r8d
0x1400dc493  lea     rcx, dword_140065110
0x1400dc49a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400dc49f  mov     r15, [rsp+220h+var_1E0]
0x1400dc4a4  mov     r12, [rbp+120h+arg_30]
0x1400dc4ab  lea     rcx, [r14+0E98h]
0x1400dc4b2  call    VidObjectLockRelease
0x1400dc4b7  test    ebx, ebx
0x1400dc4b9  jns     loc_1400DD2F7
0x1400dc4bf  test    r13, r13
0x1400dc4c2  jz      loc_1400DD2E6
0x1400dc4c8  cmp     [rsp+220h+var_1C8], 0
0x1400dc4cd  jz      short loc_1400DC4DA
0x1400dc4cf  lea     rcx, [r13+8]
0x1400dc4d3  mov     dl, 1
0x1400dc4d5  call    VidOpCtrlBlock
0x1400dc4da  xor     r8d, r8d
0x1400dc4dd  mov     rdx, r13
0x1400dc4e0  call    VsmmGpaRangeRelease
0x1400dc4e5  jmp     loc_1400DD2F7
0x1400dc4ea  mov     eax, [r14+2248h]
0x1400dc4f1  test    r10b, al
0x1400dc4f4  jnz     short loc_1400DC55F
0x1400dc4f6  mov     eax, cs:dword_140065110
0x1400dc4fc  mov     ebx, 0C000000Dh
0x1400dc501  cmp     eax, 2
0x1400dc504  jbe     short loc_1400DC49F
0x1400dc506  mov     rdx, rcx
0x1400dc509  lea     rcx, dword_140065110
0x1400dc510  call    _tlgKeywordOn
0x1400dc515  test    al, al
0x1400dc517  jz      short loc_1400DC49F
0x1400dc519  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc520  lea     rcx, [rbp+120h+var_140]
0x1400dc524  call    _tlgCreate1Sz_char
0x1400dc529  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc530  lea     rcx, [rbp+120h+var_130]
0x1400dc534  call    _tlgCreate1Sz_char
0x1400dc539  lea     rax, [rsp+220h+var_1D8]
0x1400dc53e  mov     dword ptr [rsp+220h+var_1D8], 4E2h
0x1400dc546  mov     [rbp+120h+var_120], rax
0x1400dc54a  lea     rdx, unk_140058908
0x1400dc551  lea     rax, [rsp+220h+var_1D0]
0x1400dc556  mov     dword ptr [rsp+220h+var_1D0], ebx
0x1400dc55a  jmp     loc_1400DC41C
0x1400dc55f  test    r12, r12
0x1400dc562  jz      loc_1400DC6C3
0x1400dc568  mov     eax, cs:dword_140065110
0x1400dc56e  mov     r8d, 0C00000BBh
0x1400dc574  mov     ebx, r8d
0x1400dc577  cmp     eax, 2
0x1400dc57a  jbe     loc_1400DC49F
0x1400dc580  mov     rdx, rcx
0x1400dc583  lea     rcx, dword_140065110
0x1400dc58a  call    _tlgKeywordOn
0x1400dc58f  test    al, al
0x1400dc591  jz      loc_1400DC49F
0x1400dc597  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc59e  lea     rcx, [rbp+120h+var_140]
0x1400dc5a2  call    _tlgCreate1Sz_char
0x1400dc5a7  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc5ae  lea     rcx, [rbp+120h+var_130]
0x1400dc5b2  call    _tlgCreate1Sz_char
0x1400dc5b7  lea     rax, [rsp+220h+var_1D8]
0x1400dc5bc  mov     dword ptr [rsp+220h+var_1D8], 4F0h
0x1400dc5c4  mov     [rbp+120h+var_120], rax
0x1400dc5c8  lea     rdx, unk_140058976
0x1400dc5cf  lea     rax, [rsp+220h+var_1D0]
0x1400dc5d4  mov     dword ptr [rsp+220h+var_1D0], r8d
0x1400dc5d9  jmp     loc_1400DC41C
0x1400dc5de  test    r12, r12
0x1400dc5e1  jz      loc_1400DC6C3
0x1400dc5e7  cmp     [r14+21D1h], r9b
0x1400dc5ee  jz      loc_1400DC6BF
0x1400dc5f4  mov     r12, [rbp+120h+arg_30]
0x1400dc5fb  mov     r8d, ebx
0x1400dc5fe  mov     r9, [rsp+220h+var_1C0]
0x1400dc603  mov     rdx, r12
0x1400dc606  mov     rcx, r14
0x1400dc609  call    VsmmGpaRangeLookupByPersistId
0x1400dc60e  mov     ebx, eax
0x1400dc610  test    eax, eax
0x1400dc612  jns     loc_1400DC6B5
0x1400dc618  mov     eax, cs:dword_140065110
0x1400dc61e  cmp     eax, 2
0x1400dc621  jbe     loc_1400DC6B5
0x1400dc627  mov     edx, 100h
0x1400dc62c  lea     rcx, dword_140065110
0x1400dc633  call    _tlgKeywordOn
0x1400dc638  test    al, al
0x1400dc63a  jz      short loc_1400DC6B5
0x1400dc63c  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc643  lea     rcx, [rbp+120h+var_140]
0x1400dc647  call    _tlgCreate1Sz_char
0x1400dc64c  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc653  lea     rcx, [rbp+120h+var_130]
0x1400dc657  call    _tlgCreate1Sz_char
0x1400dc65c  lea     rax, [rsp+220h+var_1D8]
0x1400dc661  mov     dword ptr [rsp+220h+var_1D8], 507h
0x1400dc669  mov     [rbp+120h+var_120], rax
0x1400dc66d  lea     rdx, unk_1400589E4
0x1400dc674  lea     rax, [rsp+220h+var_1C0]
0x1400dc679  mov     [rbp+120h+var_118], 4
0x1400dc681  mov     [rbp+120h+var_110], rax
0x1400dc685  lea     rcx, dword_140065110
0x1400dc68c  lea     rax, [rbp+120h+var_160]
0x1400dc690  mov     [rsp+220h+var_1C0], r12
0x1400dc695  mov     [rsp+220h+var_1F8], rax
0x1400dc69a  xor     r9d, r9d
0x1400dc69d  xor     r8d, r8d
0x1400dc6a0  mov     dword ptr [rsp+220h+var_200], 6
0x1400dc6a8  mov     [rbp+120h+var_108], 8
0x1400dc6b0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400dc6b5  mov     r15, [rsp+220h+var_1E0]
0x1400dc6ba  jmp     loc_1400DC4AB
0x1400dc6bf  or      r15d, 2
0x1400dc6c3  mov     r8, [rsp+220h+var_1E0]
0x1400dc6c8  mov     rcx, r14
0x1400dc6cb  mov     rdx, [rsp+220h+var_1B8]
0x1400dc6d0  mov     [rsp+220h+var_200], r9
0x1400dc6d5  mov     r9d, r15d
0x1400dc6d8  call    VsmmGpaRangeListOverlapCheck
0x1400dc6dd  test    eax, eax
0x1400dc6df  jz      loc_1400DC781
0x1400dc6e5  mov     eax, cs:dword_140065110
0x1400dc6eb  mov     ebx, 0C0370048h
0x1400dc6f0  cmp     eax, 2
0x1400dc6f3  jbe     loc_1400DC49F
0x1400dc6f9  mov     edx, 100h
0x1400dc6fe  lea     rcx, dword_140065110
0x1400dc705  call    _tlgKeywordOn
0x1400dc70a  test    al, al
0x1400dc70c  jz      loc_1400DC49F
0x1400dc712  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400dc719  lea     rcx, [rbp+120h+var_140]
0x1400dc71d  call    _tlgCreate1Sz_char
0x1400dc722  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dc729  lea     rcx, [rbp+120h+var_130]
  ... truncated ...
```
