# VsmmCreateMemoryBlock

- ea: `0x1400db3c0`
- end: `0x1400dc197`
- name: `VsmmCreateMemoryBlock`
- size: `3543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update`

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140011518`
- `0x140021c60`
- `0x14002b42c`
- `0x14002b634`
- `0x1400305c0`
- `0x140030b60`
- `0x1400347a4`
- `0x140034840`
- `0x140034b64`
- `0x140034c64`
- `0x140034fb8`
- `0x1400386a0`
- `0x1400a04a0`
- `0x1400cd2bc`
- `0x1400db3c0`
- `0x1400df644`
- `0x1400e06b0`
- `0x1400e0a30`
- `0x1400e1528`
- `0x1400eaec4`
- `0x1400f1da8`
- `0x1400f4e14`
- `0x1400f4f24`
- `0x1400f5dd8`
- `0x140101208`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1400db441`
- `ntoskrnl!EtwEventEnabled` at `0x1400dbec4`
- `ntoskrnl!EtwEventEnabled` at `0x1400dbf01`
- `ntoskrnl!EtwEventEnabled` at `0x1400db441`
- `ntoskrnl!EtwEventEnabled` at `0x1400dbec4`
- `ntoskrnl!EtwEventEnabled` at `0x1400dbf01`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400db89d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400db89d`

## string_xrefs

- `0x1400db4a2`: `VsmmCreateMemoryBlock`
- `0x1400db4dd`: `VsmmCreateMemoryBlock`
- `0x1400db519`: `VsmmCreateMemoryBlock`
- `0x1400db556`: `VsmmCreateMemoryBlock`
- `0x1400db5ad`: `VsmmCreateMemoryBlock`
- `0x1400db77f`: `VsmmCreateMemoryBlock`
- `0x1400db7a7`: `VsmmCreateMemoryBlock`
- `0x1400db7ee`: `VsmmCreateMemoryBlock`
- `0x1400db83f`: `VsmmCreateMemoryBlock`
- `0x1400db87a`: `VsmmCreateMemoryBlock`
- `0x1400db8d0`: `VsmmCreateMemoryBlock`
- `0x1400db967`: `VsmmCreateMemoryBlock`
- `0x1400db9d1`: `VsmmCreateMemoryBlock`
- `0x1400dbab1`: `VsmmCreateMemoryBlock`
- `0x1400dbaf6`: `VsmmCreateMemoryBlock`
- `0x1400dbb56`: `VsmmCreateMemoryBlock`
- `0x1400dbbe2`: `VsmmCreateMemoryBlock`
- `0x1400dbcc3`: `VsmmCreateMemoryBlock`
- `0x1400dbdba`: `VsmmCreateMemoryBlock`
- `0x1400dbe28`: `VsmmCreateMemoryBlock`
- `0x1400dbe4b`: `VsmmCreateMemoryBlock`
- `0x1400dbf5b`: `VsmmCreateMemoryBlock`

## pseudocode

```c
__int64 __fastcall VsmmCreateMemoryBlock(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r12
  _QWORD *v4; // r13
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r12
  __int64 v10; // r8
  __int64 *v11; // r9
  void *v12; // rdx
  void **v13; // r13
  __int64 v14; // r9
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  size_t v17; // r8
  void *v18; // rdx
  char *v19; // rcx
  int v20; // eax
  _QWORD *v21; // rcx
  int v22; // eax
  int v24; // [rsp+20h] [rbp-1D8h]
  char v25; // [rsp+30h] [rbp-1C8h]
  char v26; // [rsp+31h] [rbp-1C7h] BYREF
  _QWORD *v27; // [rsp+38h] [rbp-1C0h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-1B8h] BYREF
  PVOID P; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1A0h] BYREF
  int v32; // [rsp+60h] [rbp-198h] BYREF
  _QWORD *v33; // [rsp+68h] [rbp-190h] BYREF
  __int64 v34; // [rsp+70h] [rbp-188h] BYREF
  __int64 v35; // [rsp+78h] [rbp-180h] BYREF
  _BYTE *v36; // [rsp+80h] [rbp-178h] BYREF
  void *v37[2]; // [rsp+88h] [rbp-170h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-160h] BYREF
  _BYTE v39[32]; // [rsp+B0h] [rbp-148h] BYREF
  _BYTE v40[16]; // [rsp+D0h] [rbp-128h] BYREF
  _BYTE v41[16]; // [rsp+E0h] [rbp-118h] BYREF
  __int64 *v42; // [rsp+F0h] [rbp-108h]
  __int64 v43; // [rsp+F8h] [rbp-100h]
  __int64 *v44; // [rsp+100h] [rbp-F8h]
  __int64 v45; // [rsp+108h] [rbp-F0h]
  __int64 v46; // [rsp+110h] [rbp-E8h]
  __int64 v47; // [rsp+118h] [rbp-E0h]
  int *v48; // [rsp+120h] [rbp-D8h]
  __int64 v49; // [rsp+128h] [rbp-D0h]
  __int64 v50; // [rsp+130h] [rbp-C8h]
  int v51; // [rsp+138h] [rbp-C0h] BYREF
  int v52; // [rsp+13Ch] [rbp-BCh]
  __int64 *v53; // [rsp+140h] [rbp-B8h]
  __int64 v54; // [rsp+148h] [rbp-B0h]
  __int64 *v55; // [rsp+150h] [rbp-A8h]
  __int64 v56; // [rsp+158h] [rbp-A0h]
  __int64 *v57; // [rsp+160h] [rbp-98h]
  __int64 v58; // [rsp+168h] [rbp-90h]
  __int64 *v59; // [rsp+170h] [rbp-88h]
  __int64 v60; // [rsp+178h] [rbp-80h]
  _BYTE **v61; // [rsp+180h] [rbp-78h]
  __int64 v62; // [rsp+188h] [rbp-70h]
  _QWORD **v63; // [rsp+190h] [rbp-68h]
  __int64 v64; // [rsp+198h] [rbp-60h]
  char *v65; // [rsp+1A0h] [rbp-58h]
  __int64 v66; // [rsp+1A8h] [rbp-50h]
  GUID *p_ActivityId; // [rsp+1B0h] [rbp-48h]
  __int64 v68; // [rsp+1B8h] [rbp-40h]

  v3 = a3;
  v27 = a3;
  v4 = (_QWORD *)a2;
  v28 = (_QWORD *)a2;
  v31 = a2;
  v35 = a1;
  v33 = a3;
  *(_OWORD *)v37 = 0;
  v32 = 0;
  P = 0;
  VidTraceCreateAndSetActivityId(&ActivityId);
  if ( VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_CREATE_MEMBLOCK_START) )
    VidTraceInt2Routine(&VID_CREATE_MEMBLOCK_START);
  v25 = 0;
  P = 0;
  *(_OWORD *)v37 = 0;
  v36 = v4 + 2;
  v7 = v4[2];
  if ( (v7 & 0x40) != 0 )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 417);
    goto LABEL_90;
  }
  v9 = v4[2] & 4LL;
  if ( (v9 != 0) != (v4[9] != 0) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 429);
LABEL_89:
    v3 = v27;
    goto LABEL_90;
  }
  v10 = v4[5];
  if ( (v4[4] == 0) != (v10 == 0) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 437);
    goto LABEL_89;
  }
  if ( v10 && v10 != 8 * ((unsigned __int64)(*v4 + 63LL) >> 6) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 457);
    goto LABEL_89;
  }
  if ( (v4[10] || v4[11]) && (v7 & 8) == 0 )
  {
    v8 = -1073741811;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_89;
    tlgCreate1Sz_char(v40, "VsmmCreateMemoryBlock");
    tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v28) = 477;
    v42 = (__int64 *)&v28;
    v43 = 4;
    LODWORD(v30) = -1073741811;
    v44 = &v30;
    v45 = 4;
    v46 = a1 + 656;
    v48 = &v51;
    v50 = *(_QWORD *)(a1 + 128);
    v51 = *(unsigned __int16 *)(a1 + 120);
    v33 = *(_QWORD **)(a1 + 648);
    v53 = (__int64 *)&v33;
    v34 = *v11;
    v55 = &v34;
    v56 = 8;
    v35 = v4[10];
    v57 = &v35;
    v58 = 8;
    v31 = v4[11];
    v59 = &v31;
    v60 = 8;
    v24 = 13;
    v12 = &unk_140058F2F;
    goto LABEL_19;
  }
  LODWORD(v13) = 0;
  if ( *(_QWORD *)(a2 + 48) )
  {
    v14 = *(_QWORD *)(a2 + 56);
    if ( !v14 )
      goto LABEL_87;
    v15 = *(unsigned __int8 *)(a2 + 64);
    if ( !(_BYTE)v15 )
      goto LABEL_87;
    if ( (v7 & 1) != 0 )
    {
      if ( (v7 & 8) != 0 )
      {
        if ( ((*(_DWORD *)(a1 + 24) >> 9) & 0xF) != 0 && (*(_BYTE *)(a1 + 32) & 3) != 1 )
        {
          if ( v15 != ((*(_DWORD *)(a1 + 24) >> 9) & 0xF) )
          {
            v8 = -1073741811;
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 548);
            goto LABEL_88;
          }
          v4 = (_QWORD *)a2;
          v16 = ((1LL << v15) + *(_QWORD *)a2 - 1LL) / (unsigned __int64)(1LL << v15);
          if ( v14 != 8 * ((v16 + 63) >> 6) )
          {
            v8 = -1073741811;
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 562);
            goto LABEL_89;
          }
          v8 = VsmmBitmapSetup(v37, v16, 64);
          if ( v8 < 0 )
          {
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 576);
            goto LABEL_89;
          }
          v17 = *(_QWORD *)(a2 + 56);
          v18 = *(void **)(a2 + 48);
          if ( v17 && ((unsigned __int8)v18 & 7) != 0 )
            ExRaiseDatatypeMisalignment();
          RtlCopyFromUser(v37[1], v18, v17);
          v13 = v37;
        }
        *(_QWORD *)(a2 + 48) = 0;
        *(_QWORD *)(a2 + 56) = 0;
        goto LABEL_44;
      }
      v8 = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 521);
    }
    else
    {
      v8 = -1073741637;
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 511);
    }
LABEL_88:
    v4 = (_QWORD *)a2;
    goto LABEL_89;
  }
  if ( *(_QWORD *)(a2 + 56) || *(_BYTE *)(a2 + 64) )
  {
LABEL_87:
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 495);
    goto LABEL_88;
  }
LABEL_44:
  if ( *(_QWORD *)(a2 + 24) >= *(_QWORD *)(a2 + 8)
    || (*(_QWORD *)(a2 + 24) & 0x1FFLL) != 0 && (*(_QWORD *)(a2 + 24) & 0x3FFFFLL) != 0 )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 615);
    goto LABEL_49;
  }
  VidObjectLockAcquireExclusive(a1 + 3736);
  v25 = 1;
  if ( (*v36 & 1) != 0 && *(_QWORD *)(a1 + 8LL * *(unsigned __int8 *)(a2 + 65) + 8984) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 631);
LABEL_49:
    v4 = v28;
    goto LABEL_89;
  }
  if ( v9 )
  {
    if ( *(_BYTE *)(a1 + 8657) )
    {
      v8 = VsmmMemoryBlockLookupByPersistId(a1, *(_QWORD *)(a2 + 72), 0, &P);
      if ( v8 >= 0 )
      {
        v19 = (char *)P;
        v3 = v27;
        *v27 = *((_QWORD *)P + 3);
        VidOpCtrlFinish(v19 + 128);
        P = 0;
        v4 = v28;
        goto LABEL_90;
      }
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v40, "VsmmCreateMemoryBlock");
        tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v30) = 651;
        v42 = &v30;
        v43 = 4;
        v31 = *(_QWORD *)(a2 + 72);
        v44 = &v31;
        v45 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058C79, 0, 0, 6, v39);
      }
      goto LABEL_49;
    }
    v8 = VsmmPhuCheckObjectRestore(a1);
    if ( v8 < 0 )
    {
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 673);
      goto LABEL_49;
    }
  }
  v8 = VsmmMemoryBlockAlloc((unsigned int)&P, a1, a2, (_DWORD)v13, 0, (__int64)&v32);
  if ( v8 < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 688);
    goto LABEL_49;
  }
  v4 = v28;
  if ( !v9 )
  {
    v30 = 0;
    v8 = VsmmMemoryBlockDmBalloon(P, *v28, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 32), *(_QWORD *)(a2 + 40), &v30);
    if ( v8 < 0 )
    {
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 707);
      goto LABEL_89;
    }
    v20 = *((_DWORD *)P + 66);
    if ( (v20 & 8) != 0 )
    {
      v8 = VsmmMemoryBlockBackVirtually((_DWORD)P, *(_QWORD *)(a2 + 80), 0, 0, a2 + 88);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_89;
        tlgCreate1Sz_char(v40, "VsmmCreateMemoryBlock");
        tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v30) = 760;
        v42 = &v30;
        v43 = 4;
        LODWORD(v28) = v8;
        v44 = (__int64 *)&v28;
        v45 = 4;
        v46 = a1 + 656;
        v48 = &v51;
        v50 = *(_QWORD *)(a1 + 128);
        v51 = *(unsigned __int16 *)(a1 + 120);
        v31 = *(_QWORD *)(a1 + 648);
        v53 = &v31;
        v24 = 10;
        v12 = &unk_140058D0A;
LABEL_19:
        v47 = 16;
        v49 = 2;
        v54 = 8;
        v52 = 0;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v12, 0, 0, v24, v39);
        goto LABEL_89;
      }
    }
    else if ( v30 )
    {
      if ( (v20 & 0x10) != 0 )
      {
        v8 = VsmmMemoryBlockBackNoReserve();
        if ( v8 == -1073741670 )
          v8 = -1070137301;
      }
      else
      {
        v8 = VsmmMemoryBlockBackFromReserveBucket(P, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 24));
      }
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v40, "VsmmCreateMemoryBlock");
          tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
          LODWORD(v30) = 742;
          v42 = &v30;
          v43 = 4;
          LODWORD(v28) = *((_DWORD *)P + 66);
          v44 = (__int64 *)&v28;
          v45 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058CC1, 0, 0, 6, v39);
        }
        goto LABEL_89;
      }
    }
  }
  v8 = VsmmMemoryBlockHandleTableInsert(P);
  if ( v8 < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 775);
    goto LABEL_89;
  }
  v21 = P;
  if ( *((_QWORD *)P + 89) )
  {
    v22 = *((_DWORD *)P + 66);
    if ( (v22 & 0x20) != 0 )
    {
      *((_DWORD *)P + 66) = v22 | 0x800;
      v21 = P;
    }
  }
  v3 = v27;
  *v27 = v21[3];
  if ( v32 )
  {
    VsmmHostAccessMakeMbpsSharedForVmPhuUpgrade();
    v21 = P;
  }
  VsmmMbpUpgradeAllAsync(v21);
LABEL_90:
  VsmmBitmapTeardown(v37);
  if ( v8 < 0 )
  {
    if ( P )
    {
      VsmmDmMemoryBlockUninitialize();
      VsmmMemoryBlockMetadataTeardown(P);
      VsmmMemoryBlockFree(P);
    }
    *v3 = -1;
  }
  if ( v25 )
    VidObjectLockRelease(a1 + 3736);
  if ( v8 < 0
    && VID_TRACE_ETW_GUID_Context
    && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &MSVML_VID_CREATE_MEMBLOCK_ERROR) )
  {
    VidTraceInt3Routine(&MSVML_VID_CREATE_MEMBLOCK_ERROR);
  }
  if ( VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_CREATE_MEMBLOCK_STOP) )
    VidTraceInt3Routine(&VID_CREATE_MEMBLOCK_STOP);
  if ( v8 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v40, "VsmmCreateMemoryBlock");
    tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v30) = 860;
    v42 = &v30;
    v43 = 4;
    LODWORD(v28) = v8;
    v44 = (__int64 *)&v28;
    v45 = 4;
    v46 = a1 + 656;
    v47 = 16;
    v48 = &v51;
    v49 = 2;
    v50 = *(_QWORD *)(a1 + 128);
    v51 = *(unsigned __int16 *)(a1 + 120);
    v52 = 0;
    v31 = *(_QWORD *)(a1 + 648);
    v53 = &v31;
    v54 = 8;
    v35 = *v4;
    v55 = &v35;
    v56 = 8;
    v34 = *(_QWORD *)(a2 + 8);
    v57 = &v34;
    v58 = 8;
    v33 = *(_QWORD **)v36;
    v59 = (__int64 *)&v33;
    v60 = 8;
    v36 = *(_BYTE **)(a2 + 24);
    v61 = &v36;
    v62 = 8;
    v27 = *(_QWORD **)(a2 + 40);
    v63 = &v27;
    v64 = 8;
    v26 = *(_BYTE *)(a2 + 65);
    v65 = &v26;
    v66 = 1;
    *(_QWORD *)&ActivityId.Data1 = *(_QWORD *)(a2 + 72);
    p_ActivityId = &ActivityId;
    v68 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140058D78, 0, 0, 17, v39);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400db3c0  mov     [rsp+arg_18], rbx
0x1400db3c5  push    rsi
0x1400db3c6  push    rdi
0x1400db3c7  push    r12
0x1400db3c9  push    r13
0x1400db3cb  push    r14
0x1400db3cd  sub     rsp, 1D0h
0x1400db3d4  mov     rax, cs:__security_cookie
0x1400db3db  xor     rax, rsp
0x1400db3de  mov     [rsp+1F8h+var_38], rax
0x1400db3e6  mov     r12, r8
0x1400db3e9  mov     [rsp+1F8h+var_1C0], r8
0x1400db3ee  mov     r13, rdx
0x1400db3f1  mov     [rsp+1F8h+var_1B8], rdx
0x1400db3f6  mov     r14, rcx
0x1400db3f9  mov     [rsp+1F8h+var_1A0], rdx
0x1400db3fe  mov     [rsp+1F8h+var_180], rcx
0x1400db403  mov     rsi, rdx
0x1400db406  mov     [rsp+1F8h+var_190], r8
0x1400db40b  xorps   xmm0, xmm0
0x1400db40e  movups  xmmword ptr [rsp+1F8h+var_170], xmm0
0x1400db416  xor     ebx, ebx
0x1400db418  mov     [rsp+1F8h+var_198], ebx
0x1400db41c  mov     [rsp+1F8h+P], rbx
0x1400db421  lea     rcx, [rsp+1F8h+ActivityId]; ActivityId
0x1400db429  call    VidTraceCreateAndSetActivityId
0x1400db42e  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400db435  test    rcx, rcx
0x1400db438  jz      short loc_1400DB468
0x1400db43a  lea     rdx, VID_CREATE_MEMBLOCK_START; EventDescriptor
0x1400db441  call    cs:__imp_EtwEventEnabled
0x1400db448  nop     dword ptr [rax+rax+00h]
0x1400db44d  test    al, al
0x1400db44f  jz      short loc_1400DB468
0x1400db451  mov     r8, [rsi+8]
0x1400db455  mov     rdx, [r14+288h]
0x1400db45c  lea     rcx, VID_CREATE_MEMBLOCK_START; EventDescriptor
0x1400db463  call    VidTraceInt2Routine
0x1400db468  mov     [rsp+1F8h+var_1C8], bl
0x1400db46c  mov     [rsp+1F8h+P], rbx
0x1400db471  xorps   xmm0, xmm0
0x1400db474  movups  xmmword ptr [rsp+1F8h+var_170], xmm0
0x1400db47c  lea     r9, [r13+10h]
0x1400db480  mov     [rsp+1F8h+var_178], r9
0x1400db488  mov     rdx, [r9]
0x1400db48b  test    dl, 40h
0x1400db48e  jz      short loc_1400DB4B3
0x1400db490  mov     edi, 0C000000Dh
0x1400db495  mov     r8d, 1A1h
0x1400db49b  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db4a2  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db4a9  call    VidTraceErrorInternal0
0x1400db4ae  jmp     loc_1400DBE5F
0x1400db4b3  mov     r12, rdx
0x1400db4b6  and     r12d, 4
0x1400db4ba  cmp     [r13+48h], rbx
0x1400db4be  setnz   cl
0x1400db4c1  test    r12, r12
0x1400db4c4  setnz   al
0x1400db4c7  cmp     al, cl
0x1400db4c9  jz      short loc_1400DB4EE
0x1400db4cb  mov     edi, 0C000000Dh
0x1400db4d0  mov     r8d, 1ADh
0x1400db4d6  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db4dd  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db4e4  call    VidTraceErrorInternal0
0x1400db4e9  jmp     loc_1400DBE5A
0x1400db4ee  mov     r8, [r13+28h]
0x1400db4f2  mov     ecx, ebx
0x1400db4f4  test    r8, r8
0x1400db4f7  setz    cl
0x1400db4fa  mov     eax, ebx
0x1400db4fc  cmp     [r13+20h], rbx
0x1400db500  setz    al
0x1400db503  cmp     eax, ecx
0x1400db505  jz      short loc_1400DB52A
0x1400db507  mov     edi, 0C000000Dh
0x1400db50c  mov     r8d, 1B5h
0x1400db512  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db519  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db520  call    VidTraceErrorInternal0
0x1400db525  jmp     loc_1400DBE5A
0x1400db52a  test    r8, r8
0x1400db52d  jz      short loc_1400DB567
0x1400db52f  mov     rax, [r13+0]
0x1400db533  add     rax, 3Fh ; '?'
0x1400db537  shr     rax, 6
0x1400db53b  shl     rax, 3
0x1400db53f  cmp     r8, rax
0x1400db542  jz      short loc_1400DB567
0x1400db544  mov     edi, 0C000000Dh
0x1400db549  mov     r8d, 1C9h
0x1400db54f  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db556  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db55d  call    VidTraceErrorInternal0
0x1400db562  jmp     loc_1400DBE5A
0x1400db567  cmp     [r13+50h], rbx
0x1400db56b  jnz     short loc_1400DB577
0x1400db56d  cmp     [r13+58h], rbx
0x1400db571  jz      loc_1400DB729
0x1400db577  test    dl, 8
0x1400db57a  jnz     loc_1400DB729
0x1400db580  mov     edi, 0C000000Dh
0x1400db585  mov     eax, cs:dword_140065110
0x1400db58b  cmp     eax, 2
0x1400db58e  jbe     loc_1400DBE5A
0x1400db594  mov     edx, 100h
0x1400db599  lea     rcx, dword_140065110
0x1400db5a0  call    _tlgKeywordOn
0x1400db5a5  test    al, al
0x1400db5a7  jz      loc_1400DBE5A
0x1400db5ad  lea     rdx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db5b4  lea     rcx, [rsp+1F8h+var_128]
0x1400db5bc  call    _tlgCreate1Sz_char
0x1400db5c1  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db5c8  lea     rcx, [rsp+1F8h+var_118]
0x1400db5d0  call    _tlgCreate1Sz_char
0x1400db5d5  mov     dword ptr [rsp+1F8h+var_1B8], 1DDh
0x1400db5dd  lea     rax, [rsp+1F8h+var_1B8]
0x1400db5e2  mov     [rsp+1F8h+var_108], rax
0x1400db5ea  mov     [rsp+1F8h+var_100], 4
0x1400db5f6  mov     dword ptr [rsp+1F8h+var_1A8], edi
0x1400db5fa  lea     rax, [rsp+1F8h+var_1A8]
0x1400db5ff  mov     [rsp+1F8h+var_F8], rax
0x1400db607  mov     [rsp+1F8h+var_F0], 4
0x1400db613  lea     rax, [r14+290h]
0x1400db61a  mov     [rsp+1F8h+var_E8], rax
0x1400db622  lea     rax, [rsp+1F8h+var_C0]
0x1400db62a  mov     [rsp+1F8h+var_D8], rax
0x1400db632  mov     rax, [r14+80h]
0x1400db639  mov     [rsp+1F8h+var_C8], rax
0x1400db641  movzx   eax, word ptr [r14+78h]
0x1400db646  mov     [rsp+1F8h+var_C0], eax
0x1400db64d  mov     rax, [r14+288h]
0x1400db654  mov     [rsp+1F8h+var_190], rax
0x1400db659  lea     rax, [rsp+1F8h+var_190]
0x1400db65e  mov     [rsp+1F8h+var_B8], rax
0x1400db666  mov     rax, [r9]
0x1400db669  mov     [rsp+1F8h+var_188], rax
0x1400db66e  lea     rax, [rsp+1F8h+var_188]
0x1400db673  mov     [rsp+1F8h+var_A8], rax
0x1400db67b  mov     [rsp+1F8h+var_A0], 8
0x1400db687  mov     rax, [r13+50h]
0x1400db68b  mov     [rsp+1F8h+var_180], rax
0x1400db690  lea     rax, [rsp+1F8h+var_180]
0x1400db695  mov     [rsp+1F8h+var_98], rax
0x1400db69d  mov     [rsp+1F8h+var_90], 8
0x1400db6a9  mov     rax, [r13+58h]
0x1400db6ad  mov     [rsp+1F8h+var_1A0], rax
0x1400db6b2  lea     rax, [rsp+1F8h+var_1A0]
0x1400db6b7  mov     [rsp+1F8h+var_88], rax
0x1400db6bf  mov     [rsp+1F8h+var_80], 8
0x1400db6cb  lea     rax, [rsp+1F8h+var_148]
0x1400db6d3  mov     [rsp+1F8h+var_1D0], rax
0x1400db6d8  mov     dword ptr [rsp+1F8h+var_1D8], 0Dh
0x1400db6e0  lea     rdx, unk_140058F2F
0x1400db6e7  mov     [rsp+1F8h+var_E0], 10h
0x1400db6f3  mov     [rsp+1F8h+var_D0], 2
0x1400db6ff  mov     [rsp+1F8h+var_B0], 8
0x1400db70b  mov     [rsp+1F8h+var_BC], ebx
0x1400db712  xor     r9d, r9d
0x1400db715  xor     r8d, r8d
0x1400db718  lea     rcx, dword_140065110
0x1400db71f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400db724  jmp     loc_1400DBE5A
0x1400db729  mov     r13, rbx
0x1400db72c  mov     rax, [rsi+30h]
0x1400db730  test    rax, rax
0x1400db733  jnz     short loc_1400DB74D
0x1400db735  cmp     [rsi+38h], rbx
0x1400db739  jnz     short loc_1400DB744
0x1400db73b  cmp     [rsi+40h], bl
0x1400db73e  jz      loc_1400DB901
0x1400db744  test    rax, rax
0x1400db747  jz      loc_1400DBE39
0x1400db74d  mov     r9, [rsi+38h]
0x1400db751  test    r9, r9
0x1400db754  jz      loc_1400DBE39
0x1400db75a  movzx   r8d, byte ptr [rsi+40h]
0x1400db75f  test    r8b, r8b
0x1400db762  jz      loc_1400DBE39
0x1400db768  test    dl, 1
0x1400db76b  jnz     short loc_1400DB790
0x1400db76d  mov     edi, 0C00000BBh
0x1400db772  mov     r8d, 1FFh
0x1400db778  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db77f  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db786  call    VidTraceErrorInternal0
0x1400db78b  jmp     loc_1400DBE57
0x1400db790  test    dl, 8
0x1400db793  jnz     short loc_1400DB7B8
0x1400db795  mov     edi, 0C000000Dh
0x1400db79a  mov     r8d, 209h
0x1400db7a0  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db7a7  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db7ae  call    VidTraceErrorInternal0
0x1400db7b3  jmp     loc_1400DBE57
0x1400db7b8  mov     ecx, [r14+18h]
0x1400db7bc  shr     rcx, 9
0x1400db7c0  and     ecx, 0Fh
0x1400db7c3  jz      loc_1400DB8F9
0x1400db7c9  mov     al, [r14+20h]
0x1400db7cd  and     al, 3
0x1400db7cf  cmp     al, 1
0x1400db7d1  jz      loc_1400DB8F9
0x1400db7d7  cmp     r8, rcx
0x1400db7da  jz      short loc_1400DB7FF
0x1400db7dc  mov     edi, 0C000000Dh
0x1400db7e1  mov     r8d, 224h
0x1400db7e7  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db7ee  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db7f5  call    VidTraceErrorInternal0
0x1400db7fa  jmp     loc_1400DBE57
0x1400db7ff  mov     cl, r8b
0x1400db802  mov     r8d, 1
0x1400db808  shl     r8, cl
0x1400db80b  mov     r13, rsi
0x1400db80e  mov     rax, [rsi]
0x1400db811  dec     rax
0x1400db814  add     rax, r8
0x1400db817  xor     edx, edx
0x1400db819  div     r8
0x1400db81c  lea     rcx, [rax+3Fh]
0x1400db820  shr     rcx, 6
0x1400db824  shl     rcx, 3
0x1400db828  cmp     r9, rcx
0x1400db82b  jz      short loc_1400DB850
0x1400db82d  mov     edi, 0C000000Dh
0x1400db832  mov     r8d, 232h
0x1400db838  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db83f  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db846  call    VidTraceErrorInternal0
0x1400db84b  jmp     loc_1400DBE5A
0x1400db850  xor     r9d, r9d
0x1400db853  lea     r8d, [r9+40h]
0x1400db857  mov     rdx, rax
0x1400db85a  lea     rcx, [rsp+1F8h+var_170]
0x1400db862  call    VsmmBitmapSetup
0x1400db867  mov     edi, eax
0x1400db869  test    eax, eax
0x1400db86b  jns     short loc_1400DB88B
0x1400db86d  mov     r8d, 240h
0x1400db873  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db87a  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db881  call    VidTraceErrorInternal0
0x1400db886  jmp     loc_1400DBE5A
0x1400db88b  mov     r8, [rsi+38h]
0x1400db88f  mov     rdx, [rsi+30h]
0x1400db893  test    r8, r8
0x1400db896  jz      short loc_1400DB8A9
0x1400db898  test    dl, 7
0x1400db89b  jz      short loc_1400DB8A9
0x1400db89d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400db8a4  nop     dword ptr [rax+rax+00h]
0x1400db8a9  mov     rcx, [rsp+1F8h+var_170+8]; void *
0x1400db8b1  call    RtlCopyFromUser
0x1400db8b6  nop
0x1400db8b7  lea     r13, [rsp+1F8h+var_170]
0x1400db8bf  jmp     short loc_1400DB8F9
0x1400db8c1  mov     edi, eax
0x1400db8c3  mov     r8d, 24Fh
0x1400db8c9  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db8d0  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db8d7  call    VidTraceErrorInternal0
0x1400db8dc  xor     ebx, ebx
0x1400db8de  mov     [rsp+1F8h+var_1C8], bl
0x1400db8e2  mov     r13, [rsp+1F8h+var_1A0]
0x1400db8e7  mov     r14, [rsp+1F8h+var_180]
0x1400db8ec  mov     rsi, r13
0x1400db8ef  mov     r12, [rsp+1F8h+var_190]
0x1400db8f4  jmp     loc_1400DBE5F
0x1400db8f9  mov     [rsi+30h], rbx
0x1400db8fd  mov     [rsi+38h], rbx
0x1400db901  mov     rax, [rsi+18h]
0x1400db905  cmp     rax, [rsi+8]
0x1400db909  jnb     loc_1400DBE16
0x1400db90f  test    rax, 1FFh
0x1400db915  setnz   cl
0x1400db918  test    rax, 3FFFFh
0x1400db91e  setnz   al
0x1400db921  test    al, cl
0x1400db923  jnz     loc_1400DBE16
0x1400db929  lea     rcx, [r14+0E98h]
0x1400db930  call    VidObjectLockAcquireExclusive
0x1400db935  mov     [rsp+1F8h+var_1C8], 1
0x1400db93a  mov     rax, [rsp+1F8h+var_178]
0x1400db942  test    byte ptr [rax], 1
0x1400db945  jz      short loc_1400DB97D
0x1400db947  movzx   eax, byte ptr [rsi+41h]
0x1400db94b  cmp     [r14+rax*8+2318h], rbx
0x1400db953  jz      short loc_1400DB97D
0x1400db955  mov     edi, 0C000000Dh
0x1400db95a  mov     r8d, 277h
0x1400db960  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400db967  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400db96e  call    VidTraceErrorInternal0
0x1400db973  mov     r13, [rsp+1F8h+var_1B8]
0x1400db978  jmp     loc_1400DBE5A
0x1400db97d  test    r12, r12
0x1400db980  jz      loc_1400DBAC2
  ... truncated ...
```
