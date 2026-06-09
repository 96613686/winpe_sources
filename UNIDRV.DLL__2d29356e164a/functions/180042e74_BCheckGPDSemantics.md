# BCheckGPDSemantics

- ea: `0x180042e74`
- end: `0x180043db3`
- name: `BCheckGPDSemantics`
- size: `3903`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005620`

## callees

- `0x180007220`
- `0x1800390a0`
- `0x180042e74`

## string_xrefs

- `0x180042fa8`: `*XMoveUnit must be > 1 if any x-move command exists.`
- `0x18004301e`: `*YMoveUnit must be > 1 if any y-move command exists.`
- `0x1800430d1`: `Must be whole number of master units per x move unit.`
- `0x1800430f9`: `Must be whole number of master units per y move unit.`
- `0x180043d89`: `master units cannot be coarser than  X or Y MoveUnit.`
- `0x18004319c`: `*JobPasscodeMinLength and *JobPasscodeMaxLength values are outside of valid [%d,%d] range.`
- `0x1800431cd`: `*DefaultCopies value is outside of valid range.`
- `0x180043214`: `XMoveRelativeRight must exist if *XMoveThreshold is *.`
- `0x180043256`: `YMoveRelativeDown must exist if *YMoveThreshold is *.`
- `0x1800438b5`: `*CmdSendMagentaData must exist.`
- `0x180043c51`: `*PrintableOrigin must be a integral number of MoveUnits.`
- `0x180043c3c`: `*CursorOrigin must be a integral number of MoveUnits.`

## pseudocode

```c
__int64 __fastcall BCheckGPDSemantics(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  __int64 v4; // rbx
  _DWORD *v5; // r14
  unsigned int v6; // edi
  __int64 v7; // r8
  unsigned int *v8; // rbp
  __int64 v9; // r9
  _QWORD *v10; // rsi
  unsigned int *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // r9
  unsigned int v23; // ecx
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // r8d
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // r9
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v52; // r9
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rax
  int v60; // edx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // edx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rax
  int v72; // edx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rax
  int v78; // edx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rax
  int v84; // edx
  __int64 v85; // rbp
  __int64 v86; // rax
  __int64 v87; // r11
  __int64 v88; // rcx
  _DWORD *v89; // rsi
  __int64 i; // rcx
  __int64 v91; // rdx
  _DWORD *v92; // rsi
  __int64 v93; // r8
  __int64 v94; // r8
  __int64 v95; // r8
  __int64 v96; // r8
  __int64 v97; // r8
  __int64 v98; // r8
  __int64 v99; // r8
  __int64 v100; // rax
  __int64 v101; // rdx
  unsigned int v102; // r8d
  __int64 v103; // r9
  unsigned int j; // ecx
  __int64 v105; // rax
  int v106; // edx
  int v107; // eax
  __int64 v108; // r8
  __int64 v109; // rax
  __int64 v110; // rdx
  unsigned int v111; // r13d
  __int64 v112; // r15
  unsigned int k; // r14d
  __int64 v114; // rax
  __int64 v115; // r8
  unsigned int *v116; // rsi
  int v117; // r12d
  int v118; // r11d
  unsigned int v119; // r9d
  int v120; // r10d
  int v121; // ecx
  int v122; // r8d
  __int64 v123; // rax
  __int64 v124; // rbx
  unsigned int v125; // r12d
  __int64 v126; // r15
  __int64 v127; // rsi
  __int64 v128; // rbp
  unsigned int v129; // r13d
  int v130; // eax
  unsigned int v131; // esi
  __int64 v132; // rbp
  int v133; // ebx
  __int64 v134; // r14
  unsigned int v136; // [rsp+20h] [rbp-48h]
  unsigned int v137; // [rsp+24h] [rbp-44h]
  unsigned int v138; // [rsp+28h] [rbp-40h]
  __int64 v139; // [rsp+28h] [rbp-40h]
  unsigned int v141; // [rsp+80h] [rbp+18h] BYREF
  unsigned int v142; // [rsp+88h] [rbp+20h]

  v141 = 0;
  v3 = a1;
  if ( !a1 )
    return 0;
  if ( !*(_DWORD *)(a1 + 60) )
    return 0;
  v4 = a1 + *(unsigned int *)(a1 + 60);
  if ( !v4 )
    return 0;
  if ( !*(_DWORD *)(a1 + 56) )
    return 0;
  v5 = (_DWORD *)(a1 + *(unsigned int *)(a1 + 56));
  if ( !v5 )
    return 0;
  v6 = 1;
  if ( v5[30] && v5[31] == -1 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PrintRateUnit must be present if *PrintRate exists.");
    v6 = 0;
  }
  if ( (unsigned int)BGIDtoFeaIndex(v3, &v141, 6) && *(_DWORD *)(v4 + 220) == -1 )
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*MemoryUsage cannot be an empty list if *Memory feature exists.");
  v7 = *(unsigned int *)(v4 + 8);
  v8 = (unsigned int *)(v4 + 16);
  v9 = *(_QWORD *)(v4 + 104);
  v10 = (_QWORD *)(v4 + 96);
  if ( *(_DWORD *)(v7 + v9 + 36) != -1 && *v8 + *v10 + 28LL * *(unsigned int *)(v7 + v9 + 36)
    || (v11 = (unsigned int *)(v4 + 16), *(_DWORD *)(v7 + v9 + 40) != -1)
    && (v8 = (unsigned int *)(v4 + 16),
        v11 = (unsigned int *)(v4 + 16),
        *v10 + *(unsigned int *)(v4 + 16) + 28LL * *(unsigned int *)(v7 + v9 + 40))
    || (v8 = v11, *(_DWORD *)(v7 + v9 + 44) != -1) && *v10 + *v11 + 28LL * *(unsigned int *)(v7 + v9 + 44) )
  {
    if ( *(int *)(v4 + 268) <= 1 )
    {
      WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*XMoveUnit must be > 1 if any x-move command exists.");
      v6 = 0;
    }
  }
  v12 = *(unsigned int *)(v4 + 8);
  v13 = *(_QWORD *)(v4 + 104);
  if ( (*(_DWORD *)(v12 + v13 + 48) != -1 && *v10 + *v8 + 28LL * *(unsigned int *)(v12 + v13 + 48)
     || *(_DWORD *)(v12 + v13 + 52) != -1 && *v10 + *v8 + 28LL * *(unsigned int *)(v12 + v13 + 52)
     || *(_DWORD *)(v12 + v13 + 56) != -1 && *v10 + *v8 + 28LL * *(unsigned int *)(v12 + v13 + 56))
    && *(int *)(v4 + 272) <= 1 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*YMoveUnit must be > 1 if any y-move command exists.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 376) != -1 && !*(_DWORD *)(v4 + 380) )
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*DefaultFont cannot be 0 if *DeviceFonts is not an empty list.");
  v14 = *(unsigned int *)(v4 + 8);
  v15 = *(_QWORD *)(v4 + 104);
  if ( *(_DWORD *)(v14 + v15 + 92) == -1
    || (v16 = *v8, !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 92)))
    || *(_DWORD *)(v14 + v15 + 96) == -1
    || !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 96))
    || *(_DWORD *)(v14 + v15 + 100) == -1
    || !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 100)) )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdCR, CmdLF, and CmdFF are always required.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 128) % *(_DWORD *)(v4 + 268) )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "Must be whole number of master units per x move unit.");
    v6 = 0;
  }
  v17 = *(_DWORD *)(v4 + 272);
  if ( *(_DWORD *)(v4 + 132) % v17 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "Must be whole number of master units per y move unit.");
    v17 = *(_DWORD *)(v4 + 272);
    v6 = 0;
  }
  v18 = *(_DWORD *)(v4 + 268);
  if ( v18 <= 1 )
    v19 = 1;
  else
    v19 = (unsigned int)(*(_DWORD *)(v4 + 128) / v18);
  v137 = v19;
  if ( v17 <= 1 )
    v20 = 1;
  else
    v20 = *(_DWORD *)(v4 + 132) / v17;
  v138 = v20;
  if ( !(_DWORD)v19 || !v20 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "master units cannot be coarser than  X or Y MoveUnit.");
    return 0;
  }
  v21 = v5[76];
  v22 = 15;
  if ( !v21 )
  {
    if ( !v5[77] )
      goto LABEL_57;
    goto LABEL_56;
  }
  if ( v21 < 4 || (v23 = v5[77], v23 > 0xF) || v21 > v23 )
  {
LABEL_56:
    WriteDbgTraceErrorGpd(
      "BCheckGPDSemantics",
      "*JobPasscodeMinLength and *JobPasscodeMaxLength values are outside of valid [%d,%d] range.",
      4,
      15);
    v6 = 0;
  }
LABEL_57:
  v24 = v5[16];
  if ( v24 && v5[15] && v24 > v5[15] )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*DefaultCopies value is outside of valid range.", v19, v22);
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 260) == 0x80000000 )
  {
    v25 = *(unsigned int *)(v4 + 8);
    v26 = *(_QWORD *)(v4 + 104);
    if ( *(_DWORD *)(v25 + v26 + 44) == -1 || !(*v10 + *v8 + 28LL * *(unsigned int *)(v25 + v26 + 44)) )
    {
      WriteDbgTraceErrorGpd("BCheckGPDSemantics", "XMoveRelativeRight must exist if *XMoveThreshold is *.", v19, v22);
      v6 = 0;
    }
  }
  if ( *(_DWORD *)(v4 + 264) == 0x80000000 )
  {
    v27 = *(unsigned int *)(v4 + 8);
    v28 = *(_QWORD *)(v4 + 104);
    if ( *(_DWORD *)(v27 + v28 + 56) == -1 || !(*v8 + 28LL * *(unsigned int *)(v27 + v28 + 56) + *(_QWORD *)(v4 + 96)) )
    {
      WriteDbgTraceErrorGpd("BCheckGPDSemantics", "YMoveRelativeDown must exist if *YMoveThreshold is *.", v19, v22);
      v6 = 0;
    }
  }
  if ( *(_DWORD *)(v4 + 152) != 2 )
  {
    v29 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 216LL);
    if ( (_DWORD)v29 == -1 || !(28 * v29 + *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96)) )
    {
      WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendBlockData must exist if *PrinterType is not TTY.", v29, v22);
      v6 = 0;
    }
  }
  v30 = *(unsigned int *)(v4 + 8);
  v31 = *(_QWORD *)(v4 + 104);
  v32 = *(unsigned int *)(v30 + v31 + 252);
  if ( (_DWORD)v32 == -1 )
    v33 = 0;
  else
    v33 = *(_QWORD *)(v4 + 96) + 28 * v32 + *(unsigned int *)(v4 + 16);
  v34 = *(unsigned int *)(v30 + v31 + 256);
  v35 = v33 != 0;
  if ( (_DWORD)v34 != -1 && 28 * v34 + *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) )
    ++v35;
  v36 = *(unsigned int *)(v30 + v31 + 260);
  if ( (_DWORD)v36 != -1 && 28 * v36 + *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) )
    ++v35;
  if ( !v35 )
    goto LABEL_88;
  if ( v35 != 3 )
  {
    WriteDbgTraceErrorGpd(
      "BCheckGPDSemantics",
      "CmdSetFontID, CmdSelectFontID, CmdSetCharCode must be present or absent together.");
LABEL_87:
    v6 = 0;
    goto LABEL_88;
  }
  if ( *(_DWORD *)(v4 + 432) == -1 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "if font cmds exist, then *FontFormat must be defined");
    goto LABEL_87;
  }
LABEL_88:
  v37 = *(unsigned int *)(v4 + 8);
  v38 = *(_QWORD *)(v4 + 104);
  v39 = *(unsigned int *)(v37 + v38 + 284);
  if ( (_DWORD)v39 != -1 )
  {
    v40 = *(unsigned int *)(v4 + 16);
    if ( v40 + *(_QWORD *)(v4 + 96) + 28 * v39 )
    {
      v41 = *(unsigned int *)(v37 + v38 + 288);
      if ( (_DWORD)v41 == -1 || !(v40 + *(_QWORD *)(v4 + 96) + 28 * v41) )
      {
        v42 = *(unsigned int *)(v37 + v38 + 340);
        if ( (_DWORD)v42 == -1 || !(v40 + *(_QWORD *)(v4 + 96) + 28 * v42) )
        {
          WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdBoldOn and CmdBoldOff must be paired.");
          v6 = 0;
        }
      }
    }
  }
  v43 = *(unsigned int *)(v4 + 8);
  v44 = *(_QWORD *)(v4 + 104);
  v45 = *(unsigned int *)(v43 + v44 + 292);
  if ( (_DWORD)v45 != -1 )
  {
    v46 = *(unsigned int *)(v4 + 16);
    if ( v46 + *(_QWORD *)(v4 + 96) + 28 * v45 )
    {
      v47 = *(unsigned int *)(v43 + v44 + 296);
      if ( (_DWORD)v47 == -1 || !(v46 + *(_QWORD *)(v4 + 96) + 28 * v47) )
      {
        v48 = *(unsigned int *)(v43 + v44 + 340);
        if ( (_DWORD)v48 == -1 || !(v46 + *(_QWORD *)(v4 + 96) + 28 * v48) )
        {
          WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdItalicOn & CmdItalicOff must be paired.");
          v6 = 0;
        }
      }
    }
  }
  v49 = *(unsigned int *)(v4 + 8);
  v50 = *(_QWORD *)(v4 + 104);
  v51 = *(unsigned int *)(v49 + v50 + 300);
  if ( (_DWORD)v51 != -1 )
  {
    v52 = *(unsigned int *)(v4 + 16);
    if ( v52 + *(_QWORD *)(v4 + 96) + 28 * v51 )
    {
      v53 = *(unsigned int *)(v49 + v50 + 304);
      if ( (_DWORD)v53 == -1 || !(v52 + *(_QWORD *)(v4 + 96) + 28 * v53) )
      {
        v54 = *(unsigned int *)(v49 + v50 + 340);
        if ( (_DWORD)v54 == -1 || !(v52 + *(_QWORD *)(v4 + 96) + 28 * v54) )
        {
          WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdUnderlineOn & CmdUnderlineOff must be paired.");
          v6 = 0;
        }
      }
    }
  }
  v55 = *(unsigned int *)(v4 + 8);
  v56 = *(_QWORD *)(v4 + 104);
  v57 = *(unsigned int *)(v55 + v56 + 308);
  if ( (_DWORD)v57 == -1 )
    v58 = 0;
  else
    v58 = *(_QWORD *)(v4 + 96) + *(unsigned int *)(v4 + 16) + 28 * v57;
  v59 = *(unsigned int *)(v55 + v56 + 312);
  v60 = v58 != 0;
  if ( (_DWORD)v59 != -1 && *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) + 28 * v59 )
    ++v60;
  if ( (v60 & 0xFFFFFFFD) != 0 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdStrikeThruOn & CmdStrikeThruOff must be paired.");
    v6 = 0;
  }
  v61 = *(unsigned int *)(v4 + 8);
  v62 = *(_QWORD *)(v4 + 104);
  v63 = *(unsigned int *)(v61 + v62 + 316);
  if ( (_DWORD)v63 == -1 )
    v64 = 0;
  else
    v64 = *(_QWORD *)(v4 + 96) + *(unsigned int *)(v4 + 16) + 28 * v63;
  v65 = *(unsigned int *)(v61 + v62 + 320);
  v66 = v64 != 0;
  if ( (_DWORD)v65 != -1 && *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) + 28 * v65 )
    ++v66;
  if ( (v66 & 0xFFFFFFFD) != 0 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdWhiteTextOn & CmdWhiteTextOff must be paired.");
    v6 = 0;
  }
  v67 = *(unsigned int *)(v4 + 8);
  v68 = *(_QWORD *)(v4 + 104);
  v69 = *(unsigned int *)(v67 + v68 + 324);
  if ( (_DWORD)v69 == -1 )
    v70 = 0;
  else
    v70 = *(_QWORD *)(v4 + 96) + *(unsigned int *)(v4 + 16) + 28 * v69;
  v71 = *(unsigned int *)(v67 + v68 + 328);
  v72 = v70 != 0;
  if ( (_DWORD)v71 != -1 && *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) + 28 * v71 )
    ++v72;
  if ( (v72 & 0xFFFFFFFD) != 0 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdSelectSingleByteMode & CmdSelectDoubleByteMode must be paired.");
    v6 = 0;
  }
  v73 = *(unsigned int *)(v4 + 8);
  v74 = *(_QWORD *)(v4 + 104);
  v75 = *(unsigned int *)(v73 + v74 + 332);
  if ( (_DWORD)v75 == -1 )
    v76 = 0;
  else
    v76 = *(_QWORD *)(v4 + 96) + *(unsigned int *)(v4 + 16) + 28 * v75;
  v77 = *(unsigned int *)(v73 + v74 + 336);
  v78 = v76 != 0;
  if ( (_DWORD)v77 != -1 && *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) + 28 * v77 )
    ++v78;
  if ( (v78 & 0xFFFFFFFD) != 0 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdVerticalPrintingOn/CmdVerticalPrintingOff must be paired.");
    v6 = 0;
  }
  v79 = *(unsigned int *)(v4 + 8);
  v80 = *(_QWORD *)(v4 + 104);
  v81 = *(unsigned int *)(v79 + v80 + 356);
  if ( (_DWORD)v81 == -1 )
    v82 = 0;
  else
    v82 = *(_QWORD *)(v4 + 96) + *(unsigned int *)(v4 + 16) + 28 * v81;
  v83 = *(unsigned int *)(v79 + v80 + 360);
  v84 = v82 != 0;
  if ( (_DWORD)v83 != -1 && *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96) + 28 * v83 )
    ++v84;
  if ( (v84 & 0xFFFFFFFD) != 0 )
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "CmdSetRectWidth and CmdSetRectHeight must be paired.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v3 + 56) )
    v85 = v3 + *(unsigned int *)(v3 + 56);
  else
    v85 = 0;
  v86 = *(unsigned int *)(v85 + 232);
  if ( (_DWORD)v86 && v86 + *(_QWORD *)(v85 + 328) && (unsigned int)BGIDtoFeaIndex(v3, &v141, 7) )
  {
    v88 = *(unsigned int *)(56LL * *(unsigned __int8 *)(a2 + 2LL * v141) + v87 + 44);
    v89 = (_DWORD)v88 ? (_DWORD *)(v3 + v88) : 0LL;
    if ( v89[1] > 1u )
    {
      if ( v89[3] == -1 )
      {
        WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*ColorPlaneOrder must be specified if *DevNumOfPlanes > 1.");
        v6 = 0;
      }
      if ( v89[1] > 1u && v89[2] == 1 )
      {
        for ( i = (unsigned int)v89[3]; (_DWORD)i != -1; i = (unsigned int)v92[1] )
        {
          v91 = *(_QWORD *)(v4 + 96);
          v92 = (_DWORD *)(v91 + *(unsigned int *)(v4 + 40) + 8 * i);
          if ( !v92 )
            break;
          if ( *v92 )
          {
            switch ( *v92 )
            {
              case 1:
                v98 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 240LL);
                if ( (_DWORD)v98 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v98) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendMagentaData must exist.");
                  goto LABEL_195;
                }
                break;
              case 2:
                v97 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 236LL);
                if ( (_DWORD)v97 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v97) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendCyanData must exist.");
                  goto LABEL_195;
                }
                break;
              case 3:
                v96 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 248LL);
                if ( (_DWORD)v96 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v96) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendBlackData must exist.");
                  goto LABEL_195;
                }
                break;
              case 4:
                v95 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 224LL);
                if ( (_DWORD)v95 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v95) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendRedData must exist.");
                  goto LABEL_195;
                }
                break;
              case 5:
                v94 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 228LL);
                if ( (_DWORD)v94 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v94) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendGreenData must exist.");
                  goto LABEL_195;
                }
                break;
              case 6:
                v93 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 232LL);
                if ( (_DWORD)v93 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v93) )
                {
                  WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendBlueData must exist.");
                  goto LABEL_195;
                }
                break;
              default:
                WriteDbgTraceErrorGpd("BCheckGPDSemantics", "Unrecogized color.");
LABEL_195:
                v6 = 0;
                continue;
            }
          }
          else
          {
            v99 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 244LL);
            if ( (_DWORD)v99 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v99) )
            {
              WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CmdSendYellowData must exist.");
              goto LABEL_195;
            }
          }
        }
      }
    }
  }
  v136 = 1;
  v142 = 1;
  if ( (unsigned int)BGIDtoFeaIndex(v3, &v141, 0) )
  {
    v100 = *(unsigned int *)(v85 + 204);
    if ( (_DWORD)v100 )
    {
      v101 = v100 + *(_QWORD *)(v85 + 328);
      if ( v101 )
      {
        v102 = *(_DWORD *)(v101 + 52);
        if ( *(_DWORD *)(v101 + 56) )
          v103 = v3 + *(unsigned int *)(v101 + 56);
        else
          v103 = 0;
        for ( j = 0; j < v102; ++j )
        {
          v105 = 76LL * j;
          v106 = *(_DWORD *)(v105 + v103 + 56);
          if ( !v106 || (v107 = *(_DWORD *)(v105 + v103 + 60)) == 0 )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "X or Y DPI resolution value cannot be zero.");
            return 0;
          }
          if ( *(_DWORD *)(v4 + 128) < v106 )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "master units  cannot be coarser than  x res unit.");
            return 0;
          }
          if ( *(_DWORD *)(v4 + 132) < v107 )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "master units  cannot be coarser than  y res unit.");
            return 0;
          }
        }
        v108 = 76LL * *(unsigned __int8 *)(a2 + 2LL * v141);
        v142 = *(_DWORD *)(v4 + 128) / *(_DWORD *)(v108 + v103 + 56);
        v136 = *(_DWORD *)(v4 + 132) / *(_DWORD *)(v108 + v103 + 60);
      }
    }
  }
  else
  {
    WriteDbgTraceErrorGpd("BCheckGPDSemantics", "Resolution is a required feature.");
  }
  v109 = *(unsigned int *)(v85 + 208);
  if ( (_DWORD)v109 )
  {
    v110 = v109 + *(_QWORD *)(v85 + 328);
    if ( v110 )
    {
      v111 = *(_DWORD *)(v110 + 52);
      if ( *(_DWORD *)(v110 + 56) )
        v112 = v3 + *(unsigned int *)(v110 + 56);
      else
        v112 = 0;
      for ( k = 0; k < v111; ++k )
      {
        v114 = *(unsigned int *)(v85 + 240);
        if ( (_DWORD)v114 && v114 + *(_QWORD *)(v85 + 328) && !*(_DWORD *)(92LL * k + v112 + 88) )
        {
          WriteDbgTraceErrorGpd(
            "BCheckGPDSemantics",
            "*PageProtectMem must be greater than 0 if PageProtect feature exists.");
          break;
        }
        v115 = v112 + 92LL * k;
        if ( *(_DWORD *)(v115 + 44) )
          v116 = (unsigned int *)(v3 + *(unsigned int *)(v115 + 44));
        else
          v116 = 0;
        if ( *(_DWORD *)(v115 + 80) == 256 )
        {
          if ( (int)v116[6] <= 0 || (int)v116[7] <= 0 )
            WriteDbgTraceErrorGpd(
              "BCheckGPDSemantics",
              "If User Defined papersize exists *MinSize is required and must be positive.");
          if ( (int)v116[8] <= 0 || (int)v116[9] <= 0 )
          {
            WriteDbgTraceErrorGpd(
              "BCheckGPDSemantics",
              "If User Defined papersize exists *MaxSize is required and must be positive.");
            v6 = 0;
          }
          if ( (int)v116[12] <= 0 )
          {
            WriteDbgTraceErrorGpd(
              "BCheckGPDSemantics",
              "If User Defined papersize exists *MaxPrintableWidth is required and must be positive.");
            v6 = 0;
          }
        }
        else
        {
          v117 = *(_DWORD *)((v116[15] != 0 ? 4 : 0) + v115 + 56);
          if ( v117 <= 0
            || (v118 = *(_DWORD *)((-(__int64)(v116[15] != 0) & 0xFFFFFFFFFFFFFFFCuLL) + v115 + 60), v118 <= 0) )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PageDimensions is required for non-standard sizes.");
LABEL_263:
            v6 = 0;
LABEL_264:
            v3 = a1;
            break;
          }
          v119 = *v116;
          if ( (int)*v116 <= 0 || (v120 = v116[1], v120 <= 0) )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PrintableArea is required and must be positive.");
            goto LABEL_263;
          }
          v121 = v116[2];
          if ( v121 < 0 || (v122 = v116[3], v122 < 0) )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PrintableOrigin is required and cannot be negative.");
            goto LABEL_263;
          }
          if ( v119 % v142 || v120 % v136 || v121 % v142 || v122 % v136 )
            goto LABEL_264;
          if ( *(_DWORD *)(v4 + 204) )
          {
            if ( v121 % v137 || v122 % v138 )
            {
              WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PrintableOrigin must be a integral number of MoveUnits.");
              goto LABEL_264;
            }
            if ( v116[4] % v137 || v116[5] % v138 )
            {
              WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*CursorOrigin must be a integral number of MoveUnits.");
              goto LABEL_264;
            }
          }
          if ( v117 + v117 / 100 < (int)(v121 + v119) || v118 + v118 / 100 < v122 + v120 )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*PrintableArea must be contained within *PageDimensions.");
            goto LABEL_263;
          }
          v3 = a1;
        }
      }
    }
  }
  v123 = *(_QWORD *)(v3 + 48);
  v124 = v3 + *(unsigned int *)(v85 + 32);
  v125 = 0;
  v139 = v124;
  v142 = *(_DWORD *)(*(_QWORD *)(v123 + 72) + 208LL);
  if ( v142 )
  {
    v126 = 0;
    do
    {
      v127 = 84 * v126;
      if ( !*(_DWORD *)(84 * v126 + v124 + 80) )
      {
        WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*HelpIndex must be positive.");
        v6 = 0;
      }
      if ( *(_DWORD *)(v127 + v124 + 8) && *(_DWORD *)(v127 + v124 + 4) )
      {
        WriteDbgTraceErrorGpd(
          "BCheckGPDSemantics",
          "*PrintSchemaNamespace and *PrintSchemaKeywordMap cannot be specified on the same feature.");
        v6 = 0;
      }
      v128 = *(unsigned int *)(v127 + v124 + 56);
      v129 = *(_DWORD *)(v127 + v124 + 52);
      v130 = *(_DWORD *)(v127 + v124 + 48);
      v131 = 0;
      v132 = a1 + v128;
      if ( v129 )
      {
        v133 = v130;
        do
        {
          v134 = v131 * v133;
          if ( !*(_DWORD *)(v134 + v132 + 48) )
          {
            WriteDbgTraceErrorGpd("BCheckGPDSemantics", "*HelpIndex must be positive.");
            v6 = 0;
          }
          if ( *(_DWORD *)(v134 + v132 + 8) && *(_DWORD *)(v134 + v132 + 4) )
          {
            WriteDbgTraceErrorGpd(
              "BCheckGPDSemantics",
              "*PrintSchemaNamespace and *PrintSchemaKeywordMap cannot be specified on the same option.");
            v6 = 0;
          }
          ++v131;
        }
        while ( v131 < v129 );
        v124 = v139;
      }
      ++v125;
      ++v126;
    }
    while ( v125 < v142 );
  }
  return v6;
}

```

## disassembly

```asm
0x180042e74  mov     rax, rsp
0x180042e77  mov     [rax+10h], rbx
0x180042e7b  mov     [rax+8], rcx
0x180042e7f  push    rbp
0x180042e80  push    rsi
0x180042e81  push    rdi
0x180042e82  push    r12
0x180042e84  push    r13
0x180042e86  push    r14
0x180042e88  push    r15
0x180042e8a  sub     rsp, 30h
0x180042e8e  mov     dword ptr [rax+18h], 0
0x180042e95  mov     r15, rdx
0x180042e98  mov     r12, rcx
0x180042e9b  test    rcx, rcx
0x180042e9e  jz      loc_180043D9C
0x180042ea4  cmp     dword ptr [rcx+3Ch], 0
0x180042ea8  jz      loc_180043D9C
0x180042eae  mov     ebx, [rcx+3Ch]
0x180042eb1  add     rbx, rcx
0x180042eb4  jz      loc_180043D9C
0x180042eba  cmp     dword ptr [rcx+38h], 0
0x180042ebe  jz      loc_180043D9C
0x180042ec4  mov     r14d, [rcx+38h]
0x180042ec8  add     r14, rcx
0x180042ecb  jz      loc_180043D9C
0x180042ed1  or      r13d, 0FFFFFFFFh
0x180042ed5  mov     edi, 1
0x180042eda  cmp     dword ptr [r14+78h], 0
0x180042edf  jz      short loc_180042EFC
0x180042ee1  cmp     [r14+7Ch], r13d
0x180042ee5  jnz     short loc_180042EFC
0x180042ee7  lea     rdx, aPrintrateunitM; "*PrintRateUnit must be present if *Prin"...
0x180042eee  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180042ef5  call    WriteDbgTraceErrorGpd
0x180042efa  xor     edi, edi
0x180042efc  mov     r8d, 6
0x180042f02  lea     rdx, [rsp+68h+arg_10]
0x180042f0a  mov     rcx, r12
0x180042f0d  call    BGIDtoFeaIndex
0x180042f12  test    eax, eax
0x180042f14  jz      short loc_180042F32
0x180042f16  cmp     [rbx+0DCh], r13d
0x180042f1d  jnz     short loc_180042F32
0x180042f1f  lea     rdx, aMemoryusageCan; "*MemoryUsage cannot be an empty list if"...
0x180042f26  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180042f2d  call    WriteDbgTraceErrorGpd
0x180042f32  mov     r8d, [rbx+8]
0x180042f36  lea     rbp, [rbx+10h]
0x180042f3a  mov     r9, [rbx+68h]
0x180042f3e  lea     rsi, [rbx+60h]
0x180042f42  cmp     [r8+r9+24h], r13d
0x180042f47  jz      short loc_180042F5D
0x180042f49  mov     eax, [r8+r9+24h]
0x180042f4e  imul    rcx, rax, 1Ch
0x180042f52  mov     eax, [rbp+0]
0x180042f55  add     rcx, [rsi]
0x180042f58  add     rcx, rax
0x180042f5b  jnz     short loc_180042F9F
0x180042f5d  mov     rdx, rbp
0x180042f60  cmp     [r8+r9+28h], r13d
0x180042f65  jz      short loc_180042F82
0x180042f67  mov     eax, [r8+r9+28h]
0x180042f6c  lea     rbp, [rbx+10h]
0x180042f70  imul    rcx, rax, 1Ch
0x180042f74  mov     eax, [rbp+0]
0x180042f77  mov     rdx, rbp
0x180042f7a  add     rcx, rax
0x180042f7d  add     rcx, [rsi]
0x180042f80  jnz     short loc_180042F9F
0x180042f82  mov     rbp, rdx
0x180042f85  cmp     [r8+r9+2Ch], r13d
0x180042f8a  jz      short loc_180042FBD
0x180042f8c  mov     eax, [r8+r9+2Ch]
0x180042f91  imul    rcx, rax, 1Ch
0x180042f95  mov     eax, [rdx]
0x180042f97  add     rcx, rax
0x180042f9a  add     rcx, [rsi]
0x180042f9d  jz      short loc_180042FBD
0x180042f9f  cmp     dword ptr [rbx+10Ch], 1
0x180042fa6  jg      short loc_180042FBD
0x180042fa8  lea     rdx, aXmoveunitMustB; "*XMoveUnit must be > 1 if any x-move co"...
0x180042faf  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180042fb6  call    WriteDbgTraceErrorGpd
0x180042fbb  xor     edi, edi
0x180042fbd  mov     edx, [rbx+8]
0x180042fc0  mov     r8, [rbx+68h]
0x180042fc4  cmp     [rdx+r8+30h], r13d
0x180042fc9  jz      short loc_180042FDF
0x180042fcb  mov     eax, [rdx+r8+30h]
0x180042fd0  imul    rcx, rax, 1Ch
0x180042fd4  mov     eax, [rbp+0]
0x180042fd7  add     rcx, rax
0x180042fda  add     rcx, [rsi]
0x180042fdd  jnz     short loc_180043015
0x180042fdf  cmp     [rdx+r8+34h], r13d
0x180042fe4  jz      short loc_180042FFA
0x180042fe6  mov     eax, [rdx+r8+34h]
0x180042feb  imul    rcx, rax, 1Ch
0x180042fef  mov     eax, [rbp+0]
0x180042ff2  add     rcx, rax
0x180042ff5  add     rcx, [rsi]
0x180042ff8  jnz     short loc_180043015
0x180042ffa  cmp     [rdx+r8+38h], r13d
0x180042fff  jz      short loc_180043033
0x180043001  mov     eax, [rdx+r8+38h]
0x180043006  imul    rcx, rax, 1Ch
0x18004300a  mov     eax, [rbp+0]
0x18004300d  add     rcx, rax
0x180043010  add     rcx, [rsi]
0x180043013  jz      short loc_180043033
0x180043015  cmp     dword ptr [rbx+110h], 1
0x18004301c  jg      short loc_180043033
0x18004301e  lea     rdx, aYmoveunitMustB; "*YMoveUnit must be > 1 if any y-move co"...
0x180043025  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x18004302c  call    WriteDbgTraceErrorGpd
0x180043031  xor     edi, edi
0x180043033  cmp     [rbx+178h], r13d
0x18004303a  jz      short loc_180043058
0x18004303c  cmp     dword ptr [rbx+17Ch], 0
0x180043043  jnz     short loc_180043058
0x180043045  lea     rdx, aDefaultfontCan; "*DefaultFont cannot be 0 if *DeviceFont"...
0x18004304c  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043053  call    WriteDbgTraceErrorGpd
0x180043058  mov     edx, [rbx+8]
0x18004305b  mov     r8, [rbx+68h]
0x18004305f  cmp     [rdx+r8+5Ch], r13d
0x180043064  jz      short loc_1800430AB
0x180043066  mov     eax, [rdx+r8+5Ch]
0x18004306b  mov     r9d, [rbp+0]
0x18004306f  imul    rcx, rax, 1Ch
0x180043073  add     rcx, [rsi]
0x180043076  add     rcx, r9
0x180043079  jz      short loc_1800430AB
0x18004307b  cmp     [rdx+r8+60h], r13d
0x180043080  jz      short loc_1800430AB
0x180043082  mov     eax, [rdx+r8+60h]
0x180043087  imul    rcx, rax, 1Ch
0x18004308b  add     rcx, [rsi]
0x18004308e  add     rcx, r9
0x180043091  jz      short loc_1800430AB
0x180043093  cmp     [rdx+r8+64h], r13d
0x180043098  jz      short loc_1800430AB
0x18004309a  mov     eax, [rdx+r8+64h]
0x18004309f  imul    rcx, rax, 1Ch
0x1800430a3  add     rcx, [rsi]
0x1800430a6  add     rcx, r9
0x1800430a9  jnz     short loc_1800430C0
0x1800430ab  lea     rdx, aCmdcrCmdlfAndC; "CmdCR, CmdLF, and CmdFF are always requ"...
0x1800430b2  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800430b9  call    WriteDbgTraceErrorGpd
0x1800430be  xor     edi, edi
0x1800430c0  mov     eax, [rbx+80h]
0x1800430c6  cdq
0x1800430c7  idiv    dword ptr [rbx+10Ch]
0x1800430cd  test    edx, edx
0x1800430cf  jz      short loc_1800430E6
0x1800430d1  lea     rdx, aMustBeWholeNum; "Must be whole number of master units pe"...
0x1800430d8  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800430df  call    WriteDbgTraceErrorGpd
0x1800430e4  xor     edi, edi
0x1800430e6  mov     eax, [rbx+84h]
0x1800430ec  mov     ecx, [rbx+110h]
0x1800430f2  cdq
0x1800430f3  idiv    ecx
0x1800430f5  test    edx, edx
0x1800430f7  jz      short loc_180043114
0x1800430f9  lea     rdx, aMustBeWholeNum_0; "Must be whole number of master units pe"...
0x180043100  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043107  call    WriteDbgTraceErrorGpd
0x18004310c  mov     ecx, [rbx+110h]
0x180043112  xor     edi, edi
0x180043114  mov     r8d, [rbx+10Ch]
0x18004311b  mov     r9d, 1
0x180043121  cmp     r8d, r9d
0x180043124  jle     short loc_180043135
0x180043126  mov     eax, [rbx+80h]
0x18004312c  cdq
0x18004312d  idiv    r8d
0x180043130  mov     r8d, eax
0x180043133  jmp     short loc_180043138
0x180043135  mov     r8d, r9d
0x180043138  mov     [rsp+68h+var_44], r8d
0x18004313d  cmp     ecx, r9d
0x180043140  jle     short loc_18004314D
0x180043142  mov     eax, [rbx+84h]
0x180043148  cdq
0x180043149  idiv    ecx
0x18004314b  jmp     short loc_180043150
0x18004314d  mov     eax, r9d
0x180043150  mov     [rsp+68h+var_40], eax
0x180043154  test    r8d, r8d
0x180043157  jz      loc_180043D89
0x18004315d  test    eax, eax
0x18004315f  jz      loc_180043D89
0x180043165  mov     eax, [r14+130h]
0x18004316c  mov     r9d, 0Fh
0x180043172  test    eax, eax
0x180043174  jnz     short loc_180043181
0x180043176  cmp     [r14+134h], eax
0x18004317d  jnz     short loc_180043196
0x18004317f  jmp     short loc_1800431B1
0x180043181  cmp     eax, 4
0x180043184  jb      short loc_180043196
0x180043186  mov     ecx, [r14+134h]
0x18004318d  cmp     ecx, r9d
0x180043190  ja      short loc_180043196
0x180043192  cmp     eax, ecx
0x180043194  jbe     short loc_1800431B1
0x180043196  mov     r8d, 4
0x18004319c  lea     rdx, aJobpasscodemin_1; "*JobPasscodeMinLength and *JobPasscodeM"...
0x1800431a3  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800431aa  call    WriteDbgTraceErrorGpd
0x1800431af  xor     edi, edi
0x1800431b1  mov     eax, [r14+40h]
0x1800431b5  test    eax, eax
0x1800431b7  jz      short loc_1800431E0
0x1800431b9  cmp     dword ptr [r14+3Ch], 0
0x1800431be  jz      short loc_1800431E0
0x1800431c0  cmp     eax, [r14+3Ch]
0x1800431c4  lea     r14, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800431cb  jbe     short loc_1800431E7
0x1800431cd  lea     rdx, aDefaultcopiesV; "*DefaultCopies value is outside of vali"...
0x1800431d4  mov     rcx, r14
0x1800431d7  call    WriteDbgTraceErrorGpd
0x1800431dc  xor     edi, edi
0x1800431de  jmp     short loc_1800431E7
0x1800431e0  lea     r14, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800431e7  cmp     dword ptr [rbx+104h], 80000000h
0x1800431f1  jnz     short loc_180043225
0x1800431f3  mov     ecx, [rbx+8]
0x1800431f6  mov     rax, [rbx+68h]
0x1800431fa  cmp     [rcx+rax+2Ch], r13d
0x1800431ff  jz      short loc_180043214
0x180043201  mov     eax, [rcx+rax+2Ch]
0x180043205  imul    rcx, rax, 1Ch
0x180043209  mov     eax, [rbp+0]
0x18004320c  add     rcx, rax
0x18004320f  add     rcx, [rsi]
0x180043212  jnz     short loc_180043225
0x180043214  lea     rdx, aXmoverelativer; "XMoveRelativeRight must exist if *XMove"...
0x18004321b  mov     rcx, r14
0x18004321e  call    WriteDbgTraceErrorGpd
0x180043223  xor     edi, edi
0x180043225  cmp     dword ptr [rbx+108h], 80000000h
0x18004322f  jnz     short loc_180043267
0x180043231  mov     ecx, [rbx+8]
0x180043234  mov     rax, [rbx+68h]
0x180043238  cmp     [rcx+rax+38h], r13d
0x18004323d  jz      short loc_180043256
0x18004323f  mov     eax, [rcx+rax+38h]
0x180043243  mov     rdx, [rbx+60h]
0x180043247  imul    rcx, rax, 1Ch
0x18004324b  mov     eax, [rbp+0]
0x18004324e  add     rdx, rcx
0x180043251  add     rdx, rax
0x180043254  jnz     short loc_180043267
0x180043256  lea     rdx, aYmoverelatived; "YMoveRelativeDown must exist if *YMoveT"...
0x18004325d  mov     rcx, r14
0x180043260  call    WriteDbgTraceErrorGpd
0x180043265  xor     edi, edi
0x180043267  cmp     dword ptr [rbx+98h], 2
0x18004326e  jz      short loc_1800432A8
0x180043270  mov     ecx, [rbx+8]
0x180043273  mov     rax, [rbx+68h]
0x180043277  mov     r8d, [rcx+rax+0D8h]
0x18004327f  cmp     r8d, r13d
0x180043282  jz      short loc_180043297
0x180043284  mov     rdx, [rbx+60h]
0x180043288  mov     eax, [rbx+10h]
0x18004328b  imul    rcx, r8, 1Ch
0x18004328f  add     rdx, rax
0x180043292  add     rdx, rcx
0x180043295  jnz     short loc_1800432A8
0x180043297  lea     rdx, aCmdsendblockda; "*CmdSendBlockData must exist if *Printe"...
0x18004329e  mov     rcx, r14
0x1800432a1  call    WriteDbgTraceErrorGpd
0x1800432a6  xor     edi, edi
0x1800432a8  mov     r9d, [rbx+8]
0x1800432ac  mov     r10, [rbx+68h]
0x1800432b0  mov     eax, [r9+r10+0FCh]
0x1800432b8  cmp     eax, r13d
0x1800432bb  jnz     short loc_1800432C1
0x1800432bd  xor     edx, edx
0x1800432bf  jmp     short loc_1800432CF
0x1800432c1  mov     edx, [rbx+10h]
0x1800432c4  imul    rcx, rax, 1Ch
0x1800432c8  add     rdx, rcx
0x1800432cb  add     rdx, [rbx+60h]
0x1800432cf  mov     ecx, [r9+r10+100h]
0x1800432d7  xor     r8d, r8d
0x1800432da  test    rdx, rdx
0x1800432dd  setnz   r8b
0x1800432e1  cmp     ecx, r13d
0x1800432e4  jz      short loc_1800432FC
0x1800432e6  mov     rdx, [rbx+60h]
0x1800432ea  mov     eax, [rbx+10h]
0x1800432ed  imul    rcx, 1Ch
0x1800432f1  add     rdx, rax
0x1800432f4  add     rdx, rcx
  ... truncated ...
```
