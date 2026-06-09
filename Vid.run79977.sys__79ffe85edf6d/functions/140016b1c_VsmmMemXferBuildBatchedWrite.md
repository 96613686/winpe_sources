# VsmmMemXferBuildBatchedWrite

- ea: `0x140016b1c`
- end: `0x140017972`
- name: `VsmmMemXferBuildBatchedWrite`
- size: `3670`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400fa978`

## callees

- `0x1400029c0`
- `0x140003258`
- `0x140005a84`
- `0x140006b68`
- `0x14000a010`
- `0x140016b1c`
- `0x140021c60`
- `0x14002723c`
- `0x140028280`
- `0x140030960`
- `0x1400fc52c`
- `0x1400fd300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017674`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017674`
- `ntoskrnl!ExAllocatePool2` at `0x140016d65`
- `ntoskrnl!ExAllocatePool2` at `0x140016d65`
- `ntoskrnl!IoFreeMdl` at `0x140017629`
- `ntoskrnl!IoFreeMdl` at `0x140017629`
- `ntoskrnl!IoAllocateMdl` at `0x140016c43`
- `ntoskrnl!IoAllocateMdl` at `0x140016c43`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140016c61`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140016c61`

## string_xrefs

- `0x140016ea0`: `VsmmMemXferBuildBatchedWrite`
- `0x140016f9b`: `VsmmMemXferBuildBatchedWrite`
- `0x140016ffc`: `VsmmMemXferBuildBatchedWrite`
- `0x140017109`: `VsmmMemXferBuildBatchedWrite`
- `0x1400171f9`: `VsmmMemXferBuildBatchedWrite`
- `0x1400172e8`: `VsmmMemXferBuildBatchedWrite`
- `0x140017472`: `VsmmMemXferBuildBatchedWrite`
- `0x1400176b6`: `VsmmMemXferBuildBatchedWrite`
- `0x1400177a4`: `VsmmMemXferBuildBatchedWrite`

## pseudocode

```c
__int64 __fastcall VsmmMemXferBuildBatchedWrite(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  unsigned int v6; // ecx
  __int64 v7; // r9
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r13
  int v12; // esi
  __int64 v13; // rcx
  struct _MDL *Mdl; // rax
  unsigned __int64 Pool2; // rdi
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  char v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // edx
  int v27; // ecx
  int v28; // eax
  char v29; // r8
  __int64 v30; // r10
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r13
  __int64 v34; // r9
  __int64 v35; // r10
  __int64 v36; // r11
  unsigned __int64 v37; // r13
  void *v38; // rdx
  int v39; // r10d
  __int64 v40; // r8
  void *v41; // rdx
  char v42; // al
  unsigned __int64 v43; // r13
  char v44; // cl
  unsigned int v45; // r8d
  __int64 v46; // r9
  int v47; // r10d
  __int64 v48; // r8
  __int64 v49; // r8
  unsigned __int64 v50; // rcx
  unsigned int v51; // r8d
  int v52; // r10d
  __int64 v53; // r8
  int v54; // r10d
  int Irp; // [rsp+20h] [rbp-E0h]
  unsigned int v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+54h] [rbp-ACh] BYREF
  char v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v70; // [rsp+B8h] [rbp-48h]
  __int128 v71; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v72[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v73[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v74[16]; // [rsp+110h] [rbp+10h] BYREF
  int *v75; // [rsp+120h] [rbp+20h]
  __int64 v76; // [rsp+128h] [rbp+28h]
  unsigned int *v77; // [rsp+130h] [rbp+30h]
  __int64 v78; // [rsp+138h] [rbp+38h]
  __int64 v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  int *v81; // [rsp+150h] [rbp+50h]
  __int64 v82; // [rsp+158h] [rbp+58h]
  __int64 v83; // [rsp+160h] [rbp+60h]
  int v84; // [rsp+168h] [rbp+68h] BYREF
  int v85; // [rsp+16Ch] [rbp+6Ch]
  __int64 *v86; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+178h] [rbp+78h]
  __int64 *v88; // [rsp+180h] [rbp+80h]
  __int64 v89; // [rsp+188h] [rbp+88h]
  unsigned __int64 *v90; // [rsp+190h] [rbp+90h]
  __int64 v91; // [rsp+198h] [rbp+98h]
  unsigned __int64 *v92; // [rsp+1A0h] [rbp+A0h]
  __int64 v93; // [rsp+1A8h] [rbp+A8h]
  __int64 *v94; // [rsp+1B0h] [rbp+B0h]
  __int64 v95; // [rsp+1B8h] [rbp+B8h]
  __int64 *v96; // [rsp+1C0h] [rbp+C0h]
  __int64 v97; // [rsp+1C8h] [rbp+C8h]
  __int64 *v98; // [rsp+1D0h] [rbp+D0h]
  __int64 v99; // [rsp+1D8h] [rbp+D8h]

  v69 = a1;
  v66 = a4;
  v60 = a3;
  v62 = a2;
  v6 = 0;
  v58 = 0;
  v7 = a3;
  v71 = 0;
  v68 = 0;
  v70 = 0;
  if ( !v66 )
  {
LABEL_67:
    v12 = 0;
    goto LABEL_68;
  }
  while ( 1 )
  {
    v64 = *(_QWORD *)(a2 + 8LL * v6);
    v68 = *(_OWORD *)(v7 + 16LL * v6);
    if ( *(_DWORD *)(v64 + 288) )
    {
      v12 = -1073741811;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_68;
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1804;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v38 = &unk_14004D418;
      v57 = -1073741811;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v67 = *(_QWORD *)(a1 + 648);
      v86 = &v67;
      v60 = v68;
      v88 = &v60;
      v62 = *((_QWORD *)&v68 + 1);
      v90 = &v62;
      v66 = *(_QWORD *)(v53 + 248);
      v92 = &v66;
      v65 = *(_QWORD *)(v53 + 256);
      v94 = (__int64 *)&v65;
      v63 = *(_QWORD *)(v53 + 264);
      v96 = &v63;
      v64 = *(int *)(v53 + 292);
      v98 = &v64;
      Irp = 16;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v54;
      v87 = 8;
      v91 = 8;
      v93 = 8;
      v95 = 8;
      v97 = 8;
      v99 = 8;
      goto LABEL_65;
    }
    v8 = *((_QWORD *)&v68 + 1);
    v9 = a5[8];
    v10 = a5[6];
    v11 = *((_QWORD *)&v68 + 1) << 12;
    v65 = v9;
    v61 = *((_QWORD *)&v68 + 1);
    v57 = DWORD2(v68) << 12;
    if ( v9 < v10 )
      goto LABEL_6;
    v12 = VsmmMemXferpBatchedWriteAlloc(a5, 2 * v10);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_68;
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1838;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v38 = &unk_14004D4C6;
      v57 = v12;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v60 = *(_QWORD *)(a1 + 648);
      v86 = &v60;
      v88 = (__int64 *)&v62;
      Irp = 11;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v39;
      v87 = 8;
      v62 = v9;
LABEL_65:
      v89 = 8;
      goto LABEL_66;
    }
    v8 = v61;
LABEL_6:
    if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
      break;
    v24 = a5[11];
    v25 = (unsigned int)(8 * v8 + 48);
    if ( (unsigned __int64)(v25 + v24) > a5[10] )
    {
      Pool2 = ExAllocatePool2(64, (unsigned int)(8 * v8 + 48), 1833788502);
      if ( !Pool2 )
      {
        v12 = -1073741670;
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_68;
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 1962;
        v75 = &v58;
        v76 = 4;
        v79 = a1 + 656;
        v38 = &unk_14004D2FC;
        v57 = v51;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v67 = *(_QWORD *)(a1 + 648);
        v86 = &v67;
        Irp = 10;
        v77 = &v57;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v52;
        v87 = 8;
LABEL_66:
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v38, 0, 0, Irp, v72);
        goto LABEL_68;
      }
    }
    else
    {
      Pool2 = v24 + a5[9];
      a5[11] = v25 + v24;
    }
    *(_QWORD *)(Pool2 + 12) = 0;
    *(_QWORD *)(Pool2 + 20) = 0;
    *(_DWORD *)(Pool2 + 28) = 0;
    v26 = v68;
    v27 = v64;
    *(_QWORD *)Pool2 = 0;
    *(_WORD *)(Pool2 + 8) = 8 * ((v11 >> 12) + 6);
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)(Pool2 + 44) = 0;
    *(_DWORD *)(Pool2 + 40) = v11;
    *(_WORD *)(Pool2 + 10) = 2;
    v28 = VsmmLockGpaRange(v27, v26, v8, 0, Pool2);
    v29 = 0;
    v12 = v28;
    if ( v28 < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v43 = v61;
        v75 = &v58;
        v77 = &v57;
        v79 = a1 + 656;
        v58 = 1986;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v60 = *(_QWORD *)(a1 + 648);
        v86 = &v60;
        v62 = v68;
        v88 = (__int64 *)&v62;
        v90 = &v66;
        v65 = *(_QWORD *)(v64 + 248);
        v92 = &v65;
        v63 = *(_QWORD *)(v64 + 256);
        v94 = &v63;
        v61 = *(_QWORD *)(v64 + 264);
        v96 = (__int64 *)&v61;
        v67 = *(int *)(v64 + 292);
        v98 = &v67;
        v76 = 4;
        v57 = v12;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v49;
        v87 = 8;
        v89 = 8;
        v66 = v43;
        v91 = 8;
        v93 = 8;
        v95 = 8;
        v97 = 8;
        v99 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004D36A, v49, 0, 16, v72);
        v29 = 0;
      }
      else
      {
        LODWORD(v43) = v61;
      }
      v44 = v29;
      goto LABEL_51;
    }
    v59 = 1;
LABEL_19:
    v30 = a5[7];
    v31 = 5 * v65;
    *(_DWORD *)(v30 + 8 * v31 + 24) = 1;
    *(_DWORD *)(v30 + 8 * v31 + 28) = *(_DWORD *)(Pool2 + 40);
    v32 = v68;
    *(_QWORD *)(v30 + 8 * v31 + 32) = Pool2;
    *(_DWORD *)(v30 + 8 * v31 + 52) = v11;
    v33 = v64;
    *(_QWORD *)(v30 + 8 * v31 + 40) = v32 << 12;
    if ( !(unsigned __int8)VidOpCtrlStart(v33 + 8, v23, 0, v31) )
    {
      v12 = -1070137310;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 2013;
        v75 = &v58;
        v77 = &v57;
        v79 = a1 + 656;
        v76 = 4;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v60 = *(_QWORD *)(a1 + 648);
        v86 = &v60;
        v62 = *(_QWORD *)(v33 + 248);
        v88 = (__int64 *)&v62;
        v66 = *(_QWORD *)(v33 + 256);
        v90 = &v66;
        v65 = *(_QWORD *)(v33 + 264);
        v92 = &v65;
        v63 = *(int *)(v33 + 292);
        v94 = &v63;
        v57 = -1070137310;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v48;
        v87 = 8;
        v89 = 8;
        v91 = 8;
        v93 = 8;
        v95 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004D182, v48, 0, 14, v72);
      }
      v44 = v59;
      LODWORD(v43) = v61;
LABEL_51:
      if ( !Pool2 )
        goto LABEL_68;
      goto LABEL_52;
    }
    *(_QWORD *)(a5[12] + 8 * v36) = v33;
    if ( v36 )
      *(_DWORD *)(v35 + 8 * v34 - 24) = 40;
    v37 = v61;
    v6 = v58 + 1;
    ++a5[8];
    a5[3] += v37;
    v58 = v6;
    if ( v6 >= v66 )
      goto LABEL_67;
    a2 = v62;
    v7 = v60;
  }
  v13 = a5[15];
  if ( v13 + (unsigned __int64)(unsigned int)v11 > a5[14] )
  {
    v12 = -1073741789;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_68;
    tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
    tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v58 = 1853;
    v75 = &v58;
    v76 = 4;
    v79 = a1 + 656;
    v38 = &unk_14004D540;
    v57 = -1073741789;
    v81 = &v84;
    v83 = *(_QWORD *)(a1 + 128);
    v84 = *(unsigned __int16 *)(a1 + 120);
    v60 = *(_QWORD *)(a1 + 648);
    v86 = &v60;
    Irp = 10;
    v77 = &v57;
    v78 = 4;
    v80 = 16;
    v82 = 2;
    v85 = v47;
    v87 = 8;
    goto LABEL_66;
  }
  v63 = v13 + a5[13];
  Mdl = IoAllocateMdl((PVOID)v63, v11, 0, 0, 0);
  Pool2 = (unsigned __int64)Mdl;
  if ( !Mdl )
  {
    v12 = -1073741670;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1871;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v57 = v45;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v60 = *(_QWORD *)(a1 + 648);
      v86 = &v60;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v46;
      v87 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004D5AE, 0, v46, 10, v72);
    }
    goto LABEL_68;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  v16 = *(_QWORD *)(v64 + 384);
  v17 = v68 + *(_QWORD *)(v64 + 392) - *(_QWORD *)(v64 + 256);
  v18 = *(_QWORD *)(v16 + 48);
  if ( v17 < v18 && v8 <= v18 - v17 )
  {
    v19 = VsmmMemoryBlockCopyByteRange((unsigned int)&v69, v16, (_DWORD)v17 << 12, v11, v63, 0, 0, 0, 0, 0);
    v21 = 0;
    v12 = v19;
    if ( v19 < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 1913;
        v41 = &unk_14004D28E;
        goto LABEL_33;
      }
      goto LABEL_35;
    }
    *(_QWORD *)&v71 = v68;
    v22 = VsmmCryptPack(a1, v20, (unsigned int)&v71, v63, (__int64)&v57, v63, v11);
    v21 = 0;
    v12 = v22;
    if ( v22 < 0 )
      goto LABEL_35;
    LODWORD(v11) = v57;
    a5[15] += v57;
    v59 = 0;
    goto LABEL_19;
  }
  v12 = -1073741808;
  if ( (unsigned int)dword_140065110 <= 2 )
    goto LABEL_34;
  v42 = tlgKeywordOn(&dword_140065110, 256);
  v21 = 0;
  if ( v42 )
  {
    tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
    tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v58 = 1892;
    v41 = &unk_14004D220;
LABEL_33:
    v87 = 8;
    v75 = &v58;
    v77 = &v57;
    v79 = a1 + 656;
    v85 = v40;
    v81 = &v84;
    v83 = *(_QWORD *)(a1 + 128);
    v84 = *(unsigned __int16 *)(a1 + 120);
    v60 = *(_QWORD *)(a1 + 648);
    v86 = &v60;
    v82 = 2;
    v80 = 16;
    v78 = 4;
    v57 = v12;
    v76 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v41, v40, 0, 10, v72);
LABEL_34:
    v21 = 0;
  }
LABEL_35:
  LODWORD(v43) = v61;
  v44 = v21;
LABEL_52:
  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    IoFreeMdl((PMDL)Pool2);
  }
  else
  {
    if ( v44 )
      VsmmUnlockGpaRange(v64, v68, v43, 0, Pool2);
    v50 = a5[9];
    if ( Pool2 < v50 || Pool2 >= a5[10] + v50 )
      ExFreePoolWithTag((PVOID)Pool2, 0x6D4D6456u);
  }
LABEL_68:
  VsmmMemoryBlockMbpRangeVaDestroy(&v69);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140016b1c  mov     [rsp-8+arg_18], rbx
0x140016b21  push    rbp
0x140016b22  push    rsi
0x140016b23  push    rdi
0x140016b24  push    r12
0x140016b26  push    r13
0x140016b28  push    r14
0x140016b2a  push    r15
0x140016b2c  lea     rbp, [rsp-0F0h]
0x140016b34  sub     rsp, 1F0h
0x140016b3b  mov     rax, cs:__security_cookie
0x140016b42  xor     rax, rsp
0x140016b45  mov     [rbp+120h+var_40], rax
0x140016b4c  mov     r14, [rbp+120h+arg_20]
0x140016b53  xor     r10d, r10d
0x140016b56  mov     rax, r9
0x140016b59  mov     [rbp+120h+var_170], rcx
0x140016b5d  mov     [rbp+120h+var_190], rax
0x140016b61  xorps   xmm0, xmm0
0x140016b64  mov     [rsp+220h+var_1C0], r8
0x140016b69  mov     r15, rcx
0x140016b6c  mov     [rsp+220h+var_1B0], rdx
0x140016b71  mov     ecx, r10d
0x140016b74  mov     [rsp+220h+var_1CC], ecx
0x140016b78  xorps   xmm1, xmm1
0x140016b7b  mov     r9, r8
0x140016b7e  mov     ebx, r10d
0x140016b81  movups  [rbp+120h+var_158], xmm0
0x140016b85  movups  [rbp+120h+var_180], xmm1
0x140016b89  movdqu  [rbp+120h+var_168], xmm0
0x140016b8e  test    rax, rax
0x140016b91  jz      loc_140017939
0x140016b97  mov     eax, ecx
0x140016b99  mov     r11d, 2
0x140016b9f  mov     r8, [rdx+rax*8]
0x140016ba3  add     rax, rax
0x140016ba6  mov     [rbp+120h+var_1A0], r8
0x140016baa  movups  xmm0, xmmword ptr [r9+rax*8]
0x140016baf  movdqu  [rbp+120h+var_180], xmm0
0x140016bb4  cmp     [r8+120h], r10d
0x140016bbb  jnz     loc_140017777
0x140016bc1  mov     rsi, qword ptr [rbp+120h+var_180+8]
0x140016bc5  mov     rdi, [r14+40h]
0x140016bc9  mov     r13, rsi
0x140016bcc  mov     rdx, [r14+30h]
0x140016bd0  shl     r13, 0Ch
0x140016bd4  mov     [rbp+120h+var_198], rdi
0x140016bd8  mov     [rsp+220h+var_1B8], rsi
0x140016bdd  mov     [rsp+220h+var_1D0], r13d
0x140016be2  cmp     rdi, rdx
0x140016be5  jb      short loc_140016C08
0x140016be7  add     rdx, rdx
0x140016bea  mov     rcx, r14
0x140016bed  call    VsmmMemXferpBatchedWriteAlloc
0x140016bf2  xor     r10d, r10d
0x140016bf5  mov     esi, eax
0x140016bf7  test    eax, eax
0x140016bf9  js      loc_140016E78
0x140016bff  mov     rsi, [rsp+220h+var_1B8]
0x140016c04  lea     r11d, [r10+2]
0x140016c08  test    [r15+28h], r11b
0x140016c0c  jz      loc_140016D32
0x140016c12  mov     rcx, [r14+78h]
0x140016c16  mov     eax, r13d
0x140016c19  add     rax, rcx
0x140016c1c  cmp     rax, [r14+70h]
0x140016c20  ja      loc_1400171CC
0x140016c26  mov     rax, [r14+68h]
0x140016c2a  xor     r9d, r9d; ChargeQuota
0x140016c2d  add     rax, rcx
0x140016c30  mov     [rsp+220h+Irp], r10; Irp
0x140016c35  mov     rcx, rax; VirtualAddress
0x140016c38  mov     [rsp+220h+var_1A8], rax
0x140016c3d  xor     r8d, r8d; SecondaryBuffer
0x140016c40  mov     edx, r13d; Length
0x140016c43  call    cs:__imp_IoAllocateMdl
0x140016c4a  nop     dword ptr [rax+rax+00h]
0x140016c4f  xor     r9d, r9d
0x140016c52  mov     rdi, rax
0x140016c55  test    rax, rax
0x140016c58  jz      loc_1400170D8
0x140016c5e  mov     rcx, rax; MemoryDescriptorList
0x140016c61  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140016c68  nop     dword ptr [rax+rax+00h]
0x140016c6d  mov     rax, [rbp+120h+var_1A0]
0x140016c71  mov     r8, [rax+188h]
0x140016c78  sub     r8, [rax+100h]
0x140016c7f  mov     rdx, [rax+180h]
0x140016c86  add     r8, qword ptr [rbp+120h+var_180]
0x140016c8a  mov     rax, [rdx+30h]
0x140016c8e  cmp     r8, rax
0x140016c91  jnb     loc_140016FCC
0x140016c97  sub     rax, r8
0x140016c9a  cmp     rsi, rax
0x140016c9d  ja      loc_140016FCC
0x140016ca3  mov     rax, [rsp+220h+var_1A8]
0x140016ca8  xor     ecx, ecx
0x140016caa  mov     [rsp+220h+var_1D8], rcx
0x140016caf  mov     r9, r13
0x140016cb2  mov     [rsp+220h+var_1E0], cl
0x140016cb6  mov     [rsp+220h+var_1E8], cl
0x140016cba  mov     [rsp+220h+var_1F0], ecx
0x140016cbe  mov     [rsp+220h+var_1F8], rcx
0x140016cc3  lea     rcx, [rbp+120h+var_170]
0x140016cc7  shl     r8, 0Ch
0x140016ccb  mov     [rsp+220h+Irp], rax
0x140016cd0  call    VsmmMemoryBlockCopyByteRange
0x140016cd5  xor     r8d, r8d
0x140016cd8  mov     esi, eax
0x140016cda  test    eax, eax
0x140016cdc  js      loc_140016F73
0x140016ce2  mov     rax, qword ptr [rbp+120h+var_180]
0x140016ce6  lea     rcx, [rsp+220h+var_1D0]
0x140016ceb  mov     qword ptr [rbp+120h+var_158], rax
0x140016cef  lea     r8, [rbp+120h+var_158]
0x140016cf3  mov     rax, [rsp+220h+var_1A8]
0x140016cf8  mov     [rsp+220h+var_1F0], r13d
0x140016cfd  mov     r9, rax
0x140016d00  mov     [rsp+220h+var_1F8], rax
0x140016d05  mov     [rsp+220h+Irp], rcx
0x140016d0a  mov     rcx, r15
0x140016d0d  call    VsmmCryptPack
0x140016d12  xor     r8d, r8d
0x140016d15  mov     esi, eax
0x140016d17  test    eax, eax
0x140016d19  js      loc_1400170CB
0x140016d1f  mov     r13d, [rsp+220h+var_1D0]
0x140016d24  add     [r14+78h], r13
0x140016d28  mov     [rsp+220h+var_1C8], r8b
0x140016d2d  jmp     loc_140016DE1
0x140016d32  mov     rcx, [r14+58h]
0x140016d36  lea     eax, ds:30h[rsi*8]
0x140016d3d  mov     r9d, eax
0x140016d40  lea     rdx, [rax+rcx]
0x140016d44  cmp     rdx, [r14+50h]
0x140016d48  ja      short loc_140016D57
0x140016d4a  mov     rdi, [r14+48h]
0x140016d4e  add     rdi, rcx
0x140016d51  mov     [r14+58h], rdx
0x140016d55  jmp     short loc_140016D84
0x140016d57  mov     r8d, 6D4D6456h
0x140016d5d  mov     rdx, r9
0x140016d60  mov     ecx, 40h ; '@'
0x140016d65  call    cs:__imp_ExAllocatePool2
0x140016d6c  nop     dword ptr [rax+rax+00h]
0x140016d71  xor     r10d, r10d
0x140016d74  mov     rdi, rax
0x140016d77  test    rax, rax
0x140016d7a  jz      loc_140017685
0x140016d80  lea     r11d, [r10+2]
0x140016d84  mov     [rdi+0Ch], r10
0x140016d88  mov     rax, r13
0x140016d8b  mov     [rdi+14h], r10
0x140016d8f  mov     r9d, ebx
0x140016d92  mov     [rdi+1Ch], r10d
0x140016d96  mov     r8, rsi
0x140016d99  mov     rdx, qword ptr [rbp+120h+var_180]
0x140016d9d  mov     rcx, [rbp+120h+var_1A0]
0x140016da1  shr     rax, 0Ch
0x140016da5  add     ax, 6
0x140016da9  mov     [rdi], r10
0x140016dac  shl     ax, 3
0x140016db0  mov     [rdi+8], ax
0x140016db4  mov     [rdi+20h], r10
0x140016db8  mov     [rdi+2Ch], r10d
0x140016dbc  mov     [rdi+28h], r13d
0x140016dc0  mov     [rdi+0Ah], r11w
0x140016dc5  mov     [rsp+220h+Irp], rdi
0x140016dca  call    VsmmLockGpaRange
0x140016dcf  xor     r8d, r8d
0x140016dd2  mov     esi, eax
0x140016dd4  test    eax, eax
0x140016dd6  js      loc_14001744A
0x140016ddc  mov     [rsp+220h+var_1C8], 1
0x140016de1  mov     r10, [r14+38h]
0x140016de5  mov     r11, [rbp+120h+var_198]
0x140016de9  lea     r9, [r11+r11*4]
0x140016ded  mov     dword ptr [r10+r9*8+18h], 1
0x140016df6  mov     eax, [rdi+28h]
0x140016df9  mov     [r10+r9*8+1Ch], eax
0x140016dfe  mov     rax, qword ptr [rbp+120h+var_180]
0x140016e02  mov     [r10+r9*8+20h], rdi
0x140016e07  mov     [r10+r9*8+34h], r13d
0x140016e0c  mov     r13, [rbp+120h+var_1A0]
0x140016e10  shl     rax, 0Ch
0x140016e14  mov     [r10+r9*8+28h], rax
0x140016e19  lea     rcx, [r13+8]
0x140016e1d  call    VidOpCtrlStart
0x140016e22  xor     r8d, r8d
0x140016e25  test    al, al
0x140016e27  jz      loc_1400172BB
0x140016e2d  mov     rax, [r14+60h]
0x140016e31  mov     [rax+r11*8], r13
0x140016e35  test    r11, r11
0x140016e38  jz      short loc_140016E43
0x140016e3a  mov     dword ptr [r10+r9*8-18h], 28h ; '('
0x140016e43  mov     ecx, [rsp+220h+var_1CC]
0x140016e47  xor     r10d, r10d
0x140016e4a  mov     r13, [rsp+220h+var_1B8]
0x140016e4f  inc     ecx
0x140016e51  inc     qword ptr [r14+40h]
0x140016e55  add     [r14+18h], r13
0x140016e59  mov     eax, ecx
0x140016e5b  mov     [rsp+220h+var_1CC], ecx
0x140016e5f  cmp     rax, [rbp+120h+var_190]
0x140016e63  jnb     loc_140017939
0x140016e69  mov     rdx, [rsp+220h+var_1B0]
0x140016e6e  mov     r9, [rsp+220h+var_1C0]
0x140016e73  jmp     loc_140016B97
0x140016e78  mov     eax, cs:dword_140065110
0x140016e7e  cmp     eax, 2
0x140016e81  jbe     loc_14001793C
0x140016e87  mov     edx, 100h
0x140016e8c  lea     rcx, dword_140065110
0x140016e93  call    _tlgKeywordOn
0x140016e98  test    al, al
0x140016e9a  jz      loc_14001793C
0x140016ea0  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x140016ea7  lea     rcx, [rbp+120h+var_120]
0x140016eab  call    _tlgCreate1Sz_char
0x140016eb0  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140016eb7  lea     rcx, [rbp+120h+var_110]
0x140016ebb  call    _tlgCreate1Sz_char
0x140016ec0  lea     rax, [rsp+220h+var_1CC]
0x140016ec5  mov     [rsp+220h+var_1CC], 72Eh
0x140016ecd  mov     [rbp+120h+var_100], rax
0x140016ed1  lea     rcx, [rsp+220h+var_1D0]
0x140016ed6  lea     rax, [r15+290h]
0x140016edd  mov     [rbp+120h+var_F8], 4
0x140016ee5  mov     [rbp+120h+var_E0], rax
0x140016ee9  lea     rdx, unk_14004D4C6
0x140016ef0  lea     rax, [rbp+120h+var_B8]
0x140016ef4  mov     [rsp+220h+var_1D0], esi
0x140016ef8  mov     [rbp+120h+var_D0], rax
0x140016efc  mov     rax, [r15+80h]
0x140016f03  mov     [rbp+120h+var_C0], rax
0x140016f07  movzx   eax, word ptr [r15+78h]
0x140016f0c  mov     [rbp+120h+var_B8], eax
0x140016f0f  mov     rax, [r15+288h]
0x140016f16  mov     [rsp+220h+var_1C0], rax
0x140016f1b  lea     rax, [rsp+220h+var_1C0]
0x140016f20  mov     [rbp+120h+var_B0], rax
0x140016f24  lea     rax, [rsp+220h+var_1B0]
0x140016f29  mov     [rbp+120h+var_A0], rax
0x140016f30  lea     rax, [rbp+120h+var_140]
0x140016f34  mov     [rsp+220h+var_1F8], rax
0x140016f39  mov     dword ptr [rsp+220h+Irp], 0Bh
0x140016f41  mov     [rbp+120h+var_F0], rcx
0x140016f45  mov     [rbp+120h+var_E8], 4
0x140016f4d  mov     [rbp+120h+var_D8], 10h
0x140016f55  mov     [rbp+120h+var_C8], 2
0x140016f5d  mov     [rbp+120h+var_B4], r10d
0x140016f61  mov     [rbp+120h+var_A8], 8
0x140016f69  mov     [rsp+220h+var_1B0], rdi
0x140016f6e  jmp     loc_14001791A
0x140016f73  mov     eax, cs:dword_140065110
0x140016f79  cmp     eax, 2
0x140016f7c  jbe     loc_1400170CB
0x140016f82  mov     edx, 100h
0x140016f87  lea     rcx, dword_140065110
0x140016f8e  call    _tlgKeywordOn
0x140016f93  test    al, al
0x140016f95  jz      loc_1400170CB
0x140016f9b  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x140016fa2  lea     rcx, [rbp+120h+var_120]
0x140016fa6  call    _tlgCreate1Sz_char
0x140016fab  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140016fb2  lea     rcx, [rbp+120h+var_110]
0x140016fb6  call    _tlgCreate1Sz_char
0x140016fbb  mov     [rsp+220h+var_1CC], 779h
0x140016fc3  lea     rdx, unk_14004D28E
0x140016fca  jmp     short loc_14001702B
0x140016fcc  mov     eax, cs:dword_140065110
0x140016fd2  mov     esi, 0C0000010h
0x140016fd7  cmp     eax, 2
0x140016fda  jbe     loc_1400170C8
0x140016fe0  mov     edx, 100h
0x140016fe5  lea     rcx, dword_140065110
0x140016fec  call    _tlgKeywordOn
0x140016ff1  xor     r8d, r8d
0x140016ff4  test    al, al
0x140016ff6  jz      loc_1400170CB
0x140016ffc  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x140017003  lea     rcx, [rbp+120h+var_120]
0x140017007  call    _tlgCreate1Sz_char
0x14001700c  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017013  lea     rcx, [rbp+120h+var_110]
0x140017017  call    _tlgCreate1Sz_char
0x14001701c  mov     [rsp+220h+var_1CC], 764h
0x140017024  lea     rdx, unk_14004D220
0x14001702b  lea     rax, [rsp+220h+var_1CC]
0x140017030  mov     [rbp+120h+var_A8], 8
0x140017038  mov     [rbp+120h+var_100], rax
0x14001703c  lea     rcx, [rsp+220h+var_1D0]
0x140017041  lea     rax, [r15+290h]
0x140017048  mov     [rbp+120h+var_F0], rcx
0x14001704c  mov     [rbp+120h+var_E0], rax
0x140017050  lea     rcx, dword_140065110
0x140017057  lea     rax, [rbp+120h+var_B8]
0x14001705b  mov     [rbp+120h+var_B4], r8d
  ... truncated ...
```
