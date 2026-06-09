# BCheckGPDSemantics

- ea: `0x180043d98`
- end: `0x180044cd8`
- name: `BCheckGPDSemantics`
- size: `3904`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005544`

## callees

- `0x180007150`
- `0x1800390b4`
- `0x180043d98`

## string_xrefs

- `0x180043ecc`: `*XMoveUnit must be > 1 if any x-move command exists.`
- `0x180043f42`: `*YMoveUnit must be > 1 if any y-move command exists.`
- `0x180043ff5`: `Must be whole number of master units per x move unit.`
- `0x18004401d`: `Must be whole number of master units per y move unit.`
- `0x180044cad`: `master units cannot be coarser than  X or Y MoveUnit.`
- `0x1800440c0`: `*JobPasscodeMinLength and *JobPasscodeMaxLength values are outside of valid [%d,%d] range.`
- `0x1800440f1`: `*DefaultCopies value is outside of valid range.`
- `0x180044138`: `XMoveRelativeRight must exist if *XMoveThreshold is *.`
- `0x18004417a`: `YMoveRelativeDown must exist if *YMoveThreshold is *.`
- `0x1800447d9`: `*CmdSendMagentaData must exist.`
- `0x180044b75`: `*PrintableOrigin must be a integral number of MoveUnits.`
- `0x180044b60`: `*CursorOrigin must be a integral number of MoveUnits.`

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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*PrintRateUnit must be present if *PrintRate exists.");
    v6 = 0;
  }
  if ( (unsigned int)BGIDtoFeaIndex(v3, &v141, 6u) && *(_DWORD *)(v4 + 220) == -1 )
    WriteDbgTraceErrorGpd(
      (__int64)"BCheckGPDSemantics",
      "*MemoryUsage cannot be an empty list if *Memory feature exists.");
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
      WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*XMoveUnit must be > 1 if any x-move command exists.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*YMoveUnit must be > 1 if any y-move command exists.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 376) != -1 && !*(_DWORD *)(v4 + 380) )
    WriteDbgTraceErrorGpd(
      (__int64)"BCheckGPDSemantics",
      "*DefaultFont cannot be 0 if *DeviceFonts is not an empty list.");
  v14 = *(unsigned int *)(v4 + 8);
  v15 = *(_QWORD *)(v4 + 104);
  if ( *(_DWORD *)(v14 + v15 + 92) == -1
    || (v16 = *v8, !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 92)))
    || *(_DWORD *)(v14 + v15 + 96) == -1
    || !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 96))
    || *(_DWORD *)(v14 + v15 + 100) == -1
    || !(v16 + *v10 + 28LL * *(unsigned int *)(v14 + v15 + 100)) )
  {
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdCR, CmdLF, and CmdFF are always required.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 128) % *(_DWORD *)(v4 + 268) )
  {
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "Must be whole number of master units per x move unit.");
    v6 = 0;
  }
  v17 = *(_DWORD *)(v4 + 272);
  if ( *(_DWORD *)(v4 + 132) % v17 )
  {
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "Must be whole number of master units per y move unit.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "master units cannot be coarser than  X or Y MoveUnit.");
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
      (__int64)"BCheckGPDSemantics",
      "*JobPasscodeMinLength and *JobPasscodeMaxLength values are outside of valid [%d,%d] range.",
      4,
      15);
    v6 = 0;
  }
LABEL_57:
  v24 = v5[16];
  if ( v24 && v5[15] && v24 > v5[15] )
  {
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*DefaultCopies value is outside of valid range.", v19, v22);
    v6 = 0;
  }
  if ( *(_DWORD *)(v4 + 260) == 0x80000000 )
  {
    v25 = *(unsigned int *)(v4 + 8);
    v26 = *(_QWORD *)(v4 + 104);
    if ( *(_DWORD *)(v25 + v26 + 44) == -1 || !(*v10 + *v8 + 28LL * *(unsigned int *)(v25 + v26 + 44)) )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BCheckGPDSemantics",
        "XMoveRelativeRight must exist if *XMoveThreshold is *.",
        v19,
        v22);
      v6 = 0;
    }
  }
  if ( *(_DWORD *)(v4 + 264) == 0x80000000 )
  {
    v27 = *(unsigned int *)(v4 + 8);
    v28 = *(_QWORD *)(v4 + 104);
    if ( *(_DWORD *)(v27 + v28 + 56) == -1 || !(*v8 + 28LL * *(unsigned int *)(v27 + v28 + 56) + *(_QWORD *)(v4 + 96)) )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BCheckGPDSemantics",
        "YMoveRelativeDown must exist if *YMoveThreshold is *.",
        v19,
        v22);
      v6 = 0;
    }
  }
  if ( *(_DWORD *)(v4 + 152) != 2 )
  {
    v29 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 216LL);
    if ( (_DWORD)v29 == -1 || !(28 * v29 + *(unsigned int *)(v4 + 16) + *(_QWORD *)(v4 + 96)) )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BCheckGPDSemantics",
        "*CmdSendBlockData must exist if *PrinterType is not TTY.",
        v29,
        v22);
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
      (__int64)"BCheckGPDSemantics",
      "CmdSetFontID, CmdSelectFontID, CmdSetCharCode must be present or absent together.");
LABEL_87:
    v6 = 0;
    goto LABEL_88;
  }
  if ( *(_DWORD *)(v4 + 432) == -1 )
  {
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "if font cmds exist, then *FontFormat must be defined");
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
          WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdBoldOn and CmdBoldOff must be paired.");
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
          WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdItalicOn & CmdItalicOff must be paired.");
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
          WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdUnderlineOn & CmdUnderlineOff must be paired.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdStrikeThruOn & CmdStrikeThruOff must be paired.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdWhiteTextOn & CmdWhiteTextOff must be paired.");
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
    WriteDbgTraceErrorGpd(
      (__int64)"BCheckGPDSemantics",
      "CmdSelectSingleByteMode & CmdSelectDoubleByteMode must be paired.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdVerticalPrintingOn/CmdVerticalPrintingOff must be paired.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "CmdSetRectWidth and CmdSetRectHeight must be paired.");
    v6 = 0;
  }
  if ( *(_DWORD *)(v3 + 56) )
    v85 = v3 + *(unsigned int *)(v3 + 56);
  else
    v85 = 0;
  v86 = *(unsigned int *)(v85 + 232);
  if ( (_DWORD)v86 && v86 + *(_QWORD *)(v85 + 328) && (unsigned int)BGIDtoFeaIndex(v3, &v141, 7u) )
  {
    v88 = *(unsigned int *)(56LL * *(unsigned __int8 *)(a2 + 2LL * v141) + v87 + 44);
    v89 = (_DWORD)v88 ? (_DWORD *)(v3 + v88) : 0LL;
    if ( v89[1] > 1u )
    {
      if ( v89[3] == -1 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BCheckGPDSemantics",
          "*ColorPlaneOrder must be specified if *DevNumOfPlanes > 1.");
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
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendMagentaData must exist.");
                  goto LABEL_195;
                }
                break;
              case 2:
                v97 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 236LL);
                if ( (_DWORD)v97 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v97) )
                {
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendCyanData must exist.");
                  goto LABEL_195;
                }
                break;
              case 3:
                v96 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 248LL);
                if ( (_DWORD)v96 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v96) )
                {
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendBlackData must exist.");
                  goto LABEL_195;
                }
                break;
              case 4:
                v95 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 224LL);
                if ( (_DWORD)v95 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v95) )
                {
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendRedData must exist.");
                  goto LABEL_195;
                }
                break;
              case 5:
                v94 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 228LL);
                if ( (_DWORD)v94 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v94) )
                {
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendGreenData must exist.");
                  goto LABEL_195;
                }
                break;
              case 6:
                v93 = *(unsigned int *)(*(unsigned int *)(v4 + 8) + *(_QWORD *)(v4 + 104) + 232LL);
                if ( (_DWORD)v93 == -1 || !(v91 + *(unsigned int *)(v4 + 16) + 28 * v93) )
                {
                  WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendBlueData must exist.");
                  goto LABEL_195;
                }
                break;
              default:
                WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "Unrecogized color.");
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
              WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*CmdSendYellowData must exist.");
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
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "X or Y DPI resolution value cannot be zero.");
            return 0;
          }
          if ( *(_DWORD *)(v4 + 128) < v106 )
          {
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "master units  cannot be coarser than  x res unit.");
            return 0;
          }
          if ( *(_DWORD *)(v4 + 132) < v107 )
          {
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "master units  cannot be coarser than  y res unit.");
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
    WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "Resolution is a required feature.");
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
            (__int64)"BCheckGPDSemantics",
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
              (__int64)"BCheckGPDSemantics",
              "If User Defined papersize exists *MinSize is required and must be positive.");
          if ( (int)v116[8] <= 0 || (int)v116[9] <= 0 )
          {
            WriteDbgTraceErrorGpd(
              (__int64)"BCheckGPDSemantics",
              "If User Defined papersize exists *MaxSize is required and must be positive.");
            v6 = 0;
          }
          if ( (int)v116[12] <= 0 )
          {
            WriteDbgTraceErrorGpd(
              (__int64)"BCheckGPDSemantics",
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
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*PageDimensions is required for non-standard sizes.");
LABEL_263:
            v6 = 0;
LABEL_264:
            v3 = a1;
            break;
          }
          v119 = *v116;
          if ( (int)*v116 <= 0 || (v120 = v116[1], v120 <= 0) )
          {
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*PrintableArea is required and must be positive.");
            goto LABEL_263;
          }
          v121 = v116[2];
          if ( v121 < 0 || (v122 = v116[3], v122 < 0) )
          {
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*PrintableOrigin is required and cannot be negative.");
            goto LABEL_263;
          }
          if ( v119 % v142 || v120 % v136 || v121 % v142 || v122 % v136 )
            goto LABEL_264;
          if ( *(_DWORD *)(v4 + 204) )
          {
            if ( v121 % v137 || v122 % v138 )
            {
              WriteDbgTraceErrorGpd(
                (__int64)"BCheckGPDSemantics",
                "*PrintableOrigin must be a integral number of MoveUnits.");
              goto LABEL_264;
            }
            if ( v116[4] % v137 || v116[5] % v138 )
            {
              WriteDbgTraceErrorGpd(
                (__int64)"BCheckGPDSemantics",
                "*CursorOrigin must be a integral number of MoveUnits.");
              goto LABEL_264;
            }
          }
          if ( v117 + v117 / 100 < (int)(v121 + v119) || v118 + v118 / 100 < v122 + v120 )
          {
            WriteDbgTraceErrorGpd(
              (__int64)"BCheckGPDSemantics",
              "*PrintableArea must be contained within *PageDimensions.");
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
        WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*HelpIndex must be positive.");
        v6 = 0;
      }
      if ( *(_DWORD *)(v127 + v124 + 8) && *(_DWORD *)(v127 + v124 + 4) )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BCheckGPDSemantics",
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
            WriteDbgTraceErrorGpd((__int64)"BCheckGPDSemantics", "*HelpIndex must be positive.");
            v6 = 0;
          }
          if ( *(_DWORD *)(v134 + v132 + 8) && *(_DWORD *)(v134 + v132 + 4) )
          {
            WriteDbgTraceErrorGpd(
              (__int64)"BCheckGPDSemantics",
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
0x180043d98  mov     rax, rsp
0x180043d9b  mov     [rax+10h], rbx
0x180043d9f  mov     [rax+8], rcx
0x180043da3  push    rbp
0x180043da4  push    rsi
0x180043da5  push    rdi
0x180043da6  push    r12
0x180043da8  push    r13
0x180043daa  push    r14
0x180043dac  push    r15
0x180043dae  sub     rsp, 30h
0x180043db2  mov     dword ptr [rax+18h], 0
0x180043db9  mov     r15, rdx
0x180043dbc  mov     r12, rcx
0x180043dbf  test    rcx, rcx
0x180043dc2  jz      loc_180044CC0
0x180043dc8  cmp     dword ptr [rcx+3Ch], 0
0x180043dcc  jz      loc_180044CC0
0x180043dd2  mov     ebx, [rcx+3Ch]
0x180043dd5  add     rbx, rcx
0x180043dd8  jz      loc_180044CC0
0x180043dde  cmp     dword ptr [rcx+38h], 0
0x180043de2  jz      loc_180044CC0
0x180043de8  mov     r14d, [rcx+38h]
0x180043dec  add     r14, rcx
0x180043def  jz      loc_180044CC0
0x180043df5  or      r13d, 0FFFFFFFFh
0x180043df9  mov     edi, 1
0x180043dfe  cmp     dword ptr [r14+78h], 0
0x180043e03  jz      short loc_180043E20
0x180043e05  cmp     [r14+7Ch], r13d
0x180043e09  jnz     short loc_180043E20
0x180043e0b  lea     rdx, aPrintrateunitM; "*PrintRateUnit must be present if *Prin"...
0x180043e12  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043e19  call    WriteDbgTraceErrorGpd
0x180043e1e  xor     edi, edi
0x180043e20  mov     r8d, 6
0x180043e26  lea     rdx, [rsp+68h+arg_10]
0x180043e2e  mov     rcx, r12
0x180043e31  call    BGIDtoFeaIndex
0x180043e36  test    eax, eax
0x180043e38  jz      short loc_180043E56
0x180043e3a  cmp     [rbx+0DCh], r13d
0x180043e41  jnz     short loc_180043E56
0x180043e43  lea     rdx, aMemoryusageCan; "*MemoryUsage cannot be an empty list if"...
0x180043e4a  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043e51  call    WriteDbgTraceErrorGpd
0x180043e56  mov     r8d, [rbx+8]
0x180043e5a  lea     rbp, [rbx+10h]
0x180043e5e  mov     r9, [rbx+68h]
0x180043e62  lea     rsi, [rbx+60h]
0x180043e66  cmp     [r8+r9+24h], r13d
0x180043e6b  jz      short loc_180043E81
0x180043e6d  mov     eax, [r8+r9+24h]
0x180043e72  imul    rcx, rax, 1Ch
0x180043e76  mov     eax, [rbp+0]
0x180043e79  add     rcx, [rsi]
0x180043e7c  add     rcx, rax
0x180043e7f  jnz     short loc_180043EC3
0x180043e81  mov     rdx, rbp
0x180043e84  cmp     [r8+r9+28h], r13d
0x180043e89  jz      short loc_180043EA6
0x180043e8b  mov     eax, [r8+r9+28h]
0x180043e90  lea     rbp, [rbx+10h]
0x180043e94  imul    rcx, rax, 1Ch
0x180043e98  mov     eax, [rbp+0]
0x180043e9b  mov     rdx, rbp
0x180043e9e  add     rcx, rax
0x180043ea1  add     rcx, [rsi]
0x180043ea4  jnz     short loc_180043EC3
0x180043ea6  mov     rbp, rdx
0x180043ea9  cmp     [r8+r9+2Ch], r13d
0x180043eae  jz      short loc_180043EE1
0x180043eb0  mov     eax, [r8+r9+2Ch]
0x180043eb5  imul    rcx, rax, 1Ch
0x180043eb9  mov     eax, [rdx]
0x180043ebb  add     rcx, rax
0x180043ebe  add     rcx, [rsi]
0x180043ec1  jz      short loc_180043EE1
0x180043ec3  cmp     dword ptr [rbx+10Ch], 1
0x180043eca  jg      short loc_180043EE1
0x180043ecc  lea     rdx, aXmoveunitMustB; "*XMoveUnit must be > 1 if any x-move co"...
0x180043ed3  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043eda  call    WriteDbgTraceErrorGpd
0x180043edf  xor     edi, edi
0x180043ee1  mov     edx, [rbx+8]
0x180043ee4  mov     r8, [rbx+68h]
0x180043ee8  cmp     [rdx+r8+30h], r13d
0x180043eed  jz      short loc_180043F03
0x180043eef  mov     eax, [rdx+r8+30h]
0x180043ef4  imul    rcx, rax, 1Ch
0x180043ef8  mov     eax, [rbp+0]
0x180043efb  add     rcx, rax
0x180043efe  add     rcx, [rsi]
0x180043f01  jnz     short loc_180043F39
0x180043f03  cmp     [rdx+r8+34h], r13d
0x180043f08  jz      short loc_180043F1E
0x180043f0a  mov     eax, [rdx+r8+34h]
0x180043f0f  imul    rcx, rax, 1Ch
0x180043f13  mov     eax, [rbp+0]
0x180043f16  add     rcx, rax
0x180043f19  add     rcx, [rsi]
0x180043f1c  jnz     short loc_180043F39
0x180043f1e  cmp     [rdx+r8+38h], r13d
0x180043f23  jz      short loc_180043F57
0x180043f25  mov     eax, [rdx+r8+38h]
0x180043f2a  imul    rcx, rax, 1Ch
0x180043f2e  mov     eax, [rbp+0]
0x180043f31  add     rcx, rax
0x180043f34  add     rcx, [rsi]
0x180043f37  jz      short loc_180043F57
0x180043f39  cmp     dword ptr [rbx+110h], 1
0x180043f40  jg      short loc_180043F57
0x180043f42  lea     rdx, aYmoveunitMustB; "*YMoveUnit must be > 1 if any y-move co"...
0x180043f49  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043f50  call    WriteDbgTraceErrorGpd
0x180043f55  xor     edi, edi
0x180043f57  cmp     [rbx+178h], r13d
0x180043f5e  jz      short loc_180043F7C
0x180043f60  cmp     dword ptr [rbx+17Ch], 0
0x180043f67  jnz     short loc_180043F7C
0x180043f69  lea     rdx, aDefaultfontCan; "*DefaultFont cannot be 0 if *DeviceFont"...
0x180043f70  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043f77  call    WriteDbgTraceErrorGpd
0x180043f7c  mov     edx, [rbx+8]
0x180043f7f  mov     r8, [rbx+68h]
0x180043f83  cmp     [rdx+r8+5Ch], r13d
0x180043f88  jz      short loc_180043FCF
0x180043f8a  mov     eax, [rdx+r8+5Ch]
0x180043f8f  mov     r9d, [rbp+0]
0x180043f93  imul    rcx, rax, 1Ch
0x180043f97  add     rcx, [rsi]
0x180043f9a  add     rcx, r9
0x180043f9d  jz      short loc_180043FCF
0x180043f9f  cmp     [rdx+r8+60h], r13d
0x180043fa4  jz      short loc_180043FCF
0x180043fa6  mov     eax, [rdx+r8+60h]
0x180043fab  imul    rcx, rax, 1Ch
0x180043faf  add     rcx, [rsi]
0x180043fb2  add     rcx, r9
0x180043fb5  jz      short loc_180043FCF
0x180043fb7  cmp     [rdx+r8+64h], r13d
0x180043fbc  jz      short loc_180043FCF
0x180043fbe  mov     eax, [rdx+r8+64h]
0x180043fc3  imul    rcx, rax, 1Ch
0x180043fc7  add     rcx, [rsi]
0x180043fca  add     rcx, r9
0x180043fcd  jnz     short loc_180043FE4
0x180043fcf  lea     rdx, aCmdcrCmdlfAndC; "CmdCR, CmdLF, and CmdFF are always requ"...
0x180043fd6  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180043fdd  call    WriteDbgTraceErrorGpd
0x180043fe2  xor     edi, edi
0x180043fe4  mov     eax, [rbx+80h]
0x180043fea  cdq
0x180043feb  idiv    dword ptr [rbx+10Ch]
0x180043ff1  test    edx, edx
0x180043ff3  jz      short loc_18004400A
0x180043ff5  lea     rdx, aMustBeWholeNum; "Must be whole number of master units pe"...
0x180043ffc  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x180044003  call    WriteDbgTraceErrorGpd
0x180044008  xor     edi, edi
0x18004400a  mov     eax, [rbx+84h]
0x180044010  mov     ecx, [rbx+110h]
0x180044016  cdq
0x180044017  idiv    ecx
0x180044019  test    edx, edx
0x18004401b  jz      short loc_180044038
0x18004401d  lea     rdx, aMustBeWholeNum_0; "Must be whole number of master units pe"...
0x180044024  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x18004402b  call    WriteDbgTraceErrorGpd
0x180044030  mov     ecx, [rbx+110h]
0x180044036  xor     edi, edi
0x180044038  mov     r8d, [rbx+10Ch]
0x18004403f  mov     r9d, 1
0x180044045  cmp     r8d, r9d
0x180044048  jle     short loc_180044059
0x18004404a  mov     eax, [rbx+80h]
0x180044050  cdq
0x180044051  idiv    r8d
0x180044054  mov     r8d, eax
0x180044057  jmp     short loc_18004405C
0x180044059  mov     r8d, r9d
0x18004405c  mov     [rsp+68h+var_44], r8d
0x180044061  cmp     ecx, r9d
0x180044064  jle     short loc_180044071
0x180044066  mov     eax, [rbx+84h]
0x18004406c  cdq
0x18004406d  idiv    ecx
0x18004406f  jmp     short loc_180044074
0x180044071  mov     eax, r9d
0x180044074  mov     [rsp+68h+var_40], eax
0x180044078  test    r8d, r8d
0x18004407b  jz      loc_180044CAD
0x180044081  test    eax, eax
0x180044083  jz      loc_180044CAD
0x180044089  mov     eax, [r14+130h]
0x180044090  mov     r9d, 0Fh
0x180044096  test    eax, eax
0x180044098  jnz     short loc_1800440A5
0x18004409a  cmp     [r14+134h], eax
0x1800440a1  jnz     short loc_1800440BA
0x1800440a3  jmp     short loc_1800440D5
0x1800440a5  cmp     eax, 4
0x1800440a8  jb      short loc_1800440BA
0x1800440aa  mov     ecx, [r14+134h]
0x1800440b1  cmp     ecx, r9d
0x1800440b4  ja      short loc_1800440BA
0x1800440b6  cmp     eax, ecx
0x1800440b8  jbe     short loc_1800440D5
0x1800440ba  mov     r8d, 4
0x1800440c0  lea     rdx, aJobpasscodemin_1; "*JobPasscodeMinLength and *JobPasscodeM"...
0x1800440c7  lea     rcx, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800440ce  call    WriteDbgTraceErrorGpd
0x1800440d3  xor     edi, edi
0x1800440d5  mov     eax, [r14+40h]
0x1800440d9  test    eax, eax
0x1800440db  jz      short loc_180044104
0x1800440dd  cmp     dword ptr [r14+3Ch], 0
0x1800440e2  jz      short loc_180044104
0x1800440e4  cmp     eax, [r14+3Ch]
0x1800440e8  lea     r14, aBcheckgpdseman; "BCheckGPDSemantics"
0x1800440ef  jbe     short loc_18004410B
0x1800440f1  lea     rdx, aDefaultcopiesV; "*DefaultCopies value is outside of vali"...
0x1800440f8  mov     rcx, r14
0x1800440fb  call    WriteDbgTraceErrorGpd
0x180044100  xor     edi, edi
0x180044102  jmp     short loc_18004410B
0x180044104  lea     r14, aBcheckgpdseman; "BCheckGPDSemantics"
0x18004410b  cmp     dword ptr [rbx+104h], 80000000h
0x180044115  jnz     short loc_180044149
0x180044117  mov     ecx, [rbx+8]
0x18004411a  mov     rax, [rbx+68h]
0x18004411e  cmp     [rcx+rax+2Ch], r13d
0x180044123  jz      short loc_180044138
0x180044125  mov     eax, [rcx+rax+2Ch]
0x180044129  imul    rcx, rax, 1Ch
0x18004412d  mov     eax, [rbp+0]
0x180044130  add     rcx, rax
0x180044133  add     rcx, [rsi]
0x180044136  jnz     short loc_180044149
0x180044138  lea     rdx, aXmoverelativer; "XMoveRelativeRight must exist if *XMove"...
0x18004413f  mov     rcx, r14
0x180044142  call    WriteDbgTraceErrorGpd
0x180044147  xor     edi, edi
0x180044149  cmp     dword ptr [rbx+108h], 80000000h
0x180044153  jnz     short loc_18004418B
0x180044155  mov     ecx, [rbx+8]
0x180044158  mov     rax, [rbx+68h]
0x18004415c  cmp     [rcx+rax+38h], r13d
0x180044161  jz      short loc_18004417A
0x180044163  mov     eax, [rcx+rax+38h]
0x180044167  mov     rdx, [rbx+60h]
0x18004416b  imul    rcx, rax, 1Ch
0x18004416f  mov     eax, [rbp+0]
0x180044172  add     rdx, rcx
0x180044175  add     rdx, rax
0x180044178  jnz     short loc_18004418B
0x18004417a  lea     rdx, aYmoverelatived; "YMoveRelativeDown must exist if *YMoveT"...
0x180044181  mov     rcx, r14
0x180044184  call    WriteDbgTraceErrorGpd
0x180044189  xor     edi, edi
0x18004418b  cmp     dword ptr [rbx+98h], 2
0x180044192  jz      short loc_1800441CC
0x180044194  mov     ecx, [rbx+8]
0x180044197  mov     rax, [rbx+68h]
0x18004419b  mov     r8d, [rcx+rax+0D8h]
0x1800441a3  cmp     r8d, r13d
0x1800441a6  jz      short loc_1800441BB
0x1800441a8  mov     rdx, [rbx+60h]
0x1800441ac  mov     eax, [rbx+10h]
0x1800441af  imul    rcx, r8, 1Ch
0x1800441b3  add     rdx, rax
0x1800441b6  add     rdx, rcx
0x1800441b9  jnz     short loc_1800441CC
0x1800441bb  lea     rdx, aCmdsendblockda; "*CmdSendBlockData must exist if *Printe"...
0x1800441c2  mov     rcx, r14
0x1800441c5  call    WriteDbgTraceErrorGpd
0x1800441ca  xor     edi, edi
0x1800441cc  mov     r9d, [rbx+8]
0x1800441d0  mov     r10, [rbx+68h]
0x1800441d4  mov     eax, [r9+r10+0FCh]
0x1800441dc  cmp     eax, r13d
0x1800441df  jnz     short loc_1800441E5
0x1800441e1  xor     edx, edx
0x1800441e3  jmp     short loc_1800441F3
0x1800441e5  mov     edx, [rbx+10h]
0x1800441e8  imul    rcx, rax, 1Ch
0x1800441ec  add     rdx, rcx
0x1800441ef  add     rdx, [rbx+60h]
0x1800441f3  mov     ecx, [r9+r10+100h]
0x1800441fb  xor     r8d, r8d
0x1800441fe  test    rdx, rdx
0x180044201  setnz   r8b
0x180044205  cmp     ecx, r13d
0x180044208  jz      short loc_180044220
0x18004420a  mov     rdx, [rbx+60h]
0x18004420e  mov     eax, [rbx+10h]
0x180044211  imul    rcx, 1Ch
0x180044215  add     rdx, rax
0x180044218  add     rdx, rcx
  ... truncated ...
```
