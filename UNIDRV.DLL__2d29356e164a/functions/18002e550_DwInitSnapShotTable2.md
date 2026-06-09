# DwInitSnapShotTable2

- ea: `0x18002e550`
- end: `0x180030c62`
- name: `DwInitSnapShotTable2`
- size: `10002`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800271d4`

## callees

- `0x18002e550`

## string_xrefs

- `0x18002e672`: `*UpdateQualityMacro?`
- `0x18002ee31`: `*Command (CmdSelect)`
- `0x18002f73f`: `*MemoryConfigKB`
- `0x18002f636`: `*MemoryConfigMB`
- `0x180030b78`: `*InvalidCombination`

## pseudocode

```c
__int64 __fastcall DwInitSnapShotTable2(__int64 a1, unsigned int a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // rdx
  unsigned int v75; // r8d
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rdx
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rdx
  __int64 v92; // rdx
  unsigned int v93; // r8d
  __int64 v94; // rdx
  __int64 v95; // rdx
  __int64 v96; // rax
  __int64 v97; // rdx
  int v98; // r8d
  __int64 v99; // rax
  __int64 v100; // rdx
  int v101; // r8d
  __int64 v102; // rax
  __int64 v103; // rdx
  int v104; // r8d
  __int64 v105; // rax
  __int64 v106; // rdx
  int v107; // r8d
  __int64 v108; // rax

  v2 = *(_QWORD *)(a1 + 176);
  if ( !v2 )
    return 0;
  v4 = 32LL * (a2 + 1);
  *(_DWORD *)(32LL * a2 + v2 + 12) = 0;
  *(_QWORD *)(v4 + *(_QWORD *)(a1 + 176)) = "*Priority - synthesized";
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 16) = 12;
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 20) = 40;
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v4 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v5 = 32LL * (a2 + 2);
  *(_QWORD *)(v5 + *(_QWORD *)(a1 + 176)) = "*FeatureType";
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 16) = 0;
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 20) = 44;
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v5 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v6 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 208) = a2 + 2;
  v7 = 32LL * (a2 + 3);
  *(_QWORD *)(v7 + v6) = "*ConcealFromUI?";
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 16) = 56;
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 24) = 0x40000;
  *(_DWORD *)(v7 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v8 = a2 + 4;
  v9 = a2 + 5;
  v8 *= 32;
  *(_QWORD *)(v8 + *(_QWORD *)(a1 + 176)) = "*UpdateQualityMacro?";
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 16) = 60;
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 8) = 4;
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 24) = 0x40000;
  *(_DWORD *)(v8 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v10 = 32LL * v9;
  *(_QWORD *)(v10 + *(_QWORD *)(a1 + 176)) = "*rcNameID (Fea)";
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 16) = 36;
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 20) = 12;
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 24) = 16400;
  *(_DWORD *)(v10 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v11 = 32LL * (v9 + 1);
  *(_QWORD *)(v11 + *(_QWORD *)(a1 + 176)) = "*Name (Fea)";
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 16) = 32;
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 20) = 12;
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 24) = 38;
  *(_DWORD *)(v11 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v12 = 32LL * (v9 + 2);
  *(_QWORD *)(v12 + *(_QWORD *)(a1 + 176)) = "*PrintSchemaKeywordMap (fea)";
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 16) = 44;
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 20) = 4;
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 24) = 4;
  *(_DWORD *)(v12 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v13 = v9 + 3;
  v9 += 4;
  v13 *= 32;
  *(_QWORD *)(v13 + *(_QWORD *)(a1 + 176)) = "*PrintSchemaNamespace (fea)";
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 16) = 48;
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 20) = 8;
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 24) = 4;
  *(_DWORD *)(v13 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v14 = 32LL * v9;
  *(_QWORD *)(v14 + *(_QWORD *)(a1 + 176)) = "*HelpIndex (Fea)";
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 16) = 64;
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 20) = 80;
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 24) = 0x20000;
  *(_DWORD *)(v14 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v15 = 32LL * (v9 + 1);
  *(_QWORD *)(v15 + *(_QWORD *)(a1 + 176)) = "*FeaKeyWord - Synthesized";
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 16) = 28;
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 24) = 5;
  *(_DWORD *)(v15 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v16 = 32LL * (v9 + 2);
  *(_QWORD *)(v16 + *(_QWORD *)(a1 + 176)) = "*UIType";
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 16) = 4;
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 20) = 32;
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v16 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v17 = v9 + 4;
  *(_DWORD *)(32LL * (v9 + 3) + *(_QWORD *)(a1 + 176) + 12) = 0;
  v18 = v9 + 4;
  v9 += 5;
  v18 *= 32;
  *(_QWORD *)(v18 + *(_QWORD *)(a1 + 176)) = "*DefaultOption";
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 16) = 8;
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 20) = 20;
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v18 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v19 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 212) = v17;
  v20 = 32LL * v9;
  *(_QWORD *)(v20 + v19) = "*rcIconID (Fea)";
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 16) = 40;
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 20) = 68;
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 24) = 0x10000;
  *(_DWORD *)(v20 + *(_QWORD *)(a1 + 176) + 28) = 0;
  *(_DWORD *)(32LL * (v9 + 1) + *(_QWORD *)(a1 + 176) + 12) = 0;
  v21 = 32LL * (v9 + 2);
  *(_QWORD *)(v21 + *(_QWORD *)(a1 + 176)) = "*OptKeyWord - synth";
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 16) = 100;
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 24) = 4;
  *(_DWORD *)(v21 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v22 = 32LL * (v9 + 3);
  *(_QWORD *)(v22 + *(_QWORD *)(a1 + 176)) = "*rcNameID (Opt)";
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 16) = 108;
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 20) = 12;
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 24) = 16400;
  *(_DWORD *)(v22 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v23 = v9 + 4;
  v9 += 5;
  v23 *= 32;
  *(_QWORD *)(v23 + *(_QWORD *)(a1 + 176)) = "*Name (Opt)";
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 16) = 104;
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 20) = 12;
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 24) = 38;
  *(_DWORD *)(v23 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v24 = 32LL * v9;
  *(_QWORD *)(v24 + *(_QWORD *)(a1 + 176)) = "*PrintSchemaKeywordMap (opt)";
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 16) = 116;
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 20) = 4;
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 24) = 4;
  *(_DWORD *)(v24 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v25 = 32LL * (v9 + 1);
  *(_QWORD *)(v25 + *(_QWORD *)(a1 + 176)) = "*PrintSchemaNamespace (opt)";
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 16) = 120;
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 20) = 8;
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 24) = 4;
  *(_DWORD *)(v25 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v26 = 32LL * (v9 + 2);
  *(_QWORD *)(v26 + *(_QWORD *)(a1 + 176)) = "*HelpIndex (Opt)";
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 16) = 128;
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 20) = 48;
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 24) = 0x20000;
  *(_DWORD *)(v26 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v27 = 32LL * (v9 + 3);
  *(_QWORD *)(v27 + *(_QWORD *)(a1 + 176)) = "*DisabledFeatures";
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 16) = 152;
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 20) = 52;
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v27 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v28 = v9 + 4;
  v9 += 5;
  v28 *= 32;
  *(_QWORD *)(v28 + *(_QWORD *)(a1 + 176)) = "*Command (CmdSelect)";
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 16) = 132;
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 24) = 256;
  *(_DWORD *)(v28 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v29 = 32LL * v9;
  *(_QWORD *)(v29 + *(_QWORD *)(a1 + 176)) = "*DPI";
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 16) = 248;
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v29 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v30 = 32LL * (v9 + 1);
  *(_QWORD *)(v30 + *(_QWORD *)(a1 + 176)) = "*DPI";
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 16) = 248;
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 24) = 65;
  *(_DWORD *)(v30 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v31 = 32LL * (v9 + 2);
  *(_QWORD *)(v31 + *(_QWORD *)(a1 + 176)) = "*OptionID";
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 20) = 72;
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 8) = -5;
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v31 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v32 = v9 + 3;
  v9 += 4;
  v32 *= 32;
  *(_QWORD *)(v32 + *(_QWORD *)(a1 + 176)) = "*rcHTPatternID";
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 16) = 336;
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 24) = 0x20000;
  *(_DWORD *)(v32 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v33 = 32LL * v9;
  *(_QWORD *)(v33 + *(_QWORD *)(a1 + 176)) = "*HTPatternSize";
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 16) = 340;
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 20) = 64;
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v33 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v34 = 32LL * (v9 + 1);
  *(_QWORD *)(v34 + *(_QWORD *)(a1 + 176)) = "*HTNumPatterns";
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 16) = 344;
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 20) = 76;
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v34 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v35 = 32LL * (v9 + 2);
  *(_QWORD *)(v35 + *(_QWORD *)(a1 + 176)) = "*HTCallbackID";
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 16) = 348;
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 20) = 80;
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v35 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v36 = 32LL * (v9 + 3);
  *(_QWORD *)(v36 + *(_QWORD *)(a1 + 176)) = "*Luminance";
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 16) = 352;
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 20) = 72;
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 8) = 100;
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v36 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v37 = v9 + 4;
  v9 += 5;
  v37 *= 32;
  *(_QWORD *)(v37 + *(_QWORD *)(a1 + 176)) = "*dwHalftoneID - synth";
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v37 + *(_QWORD *)(a1 + 176) + 28) = 4096;
  v38 = 32LL * v9;
  *(_QWORD *)(v38 + *(_QWORD *)(a1 + 176)) = "*dwDuplexID - synth";
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v38 + *(_QWORD *)(a1 + 176) + 28) = 8;
  v39 = 32LL * (v9 + 1);
  *(_QWORD *)(v39 + *(_QWORD *)(a1 + 176)) = "*dwRotationAngle - synth";
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v39 + *(_QWORD *)(a1 + 176) + 28) = 256;
  v40 = 32LL * (v9 + 2);
  *(_QWORD *)(v40 + *(_QWORD *)(a1 + 176)) = "*dwPageProtectID - synth";
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v40 + *(_QWORD *)(a1 + 176) + 28) = 512;
  v41 = v9 + 3;
  v9 += 4;
  v41 *= 32;
  *(_QWORD *)(v41 + *(_QWORD *)(a1 + 176)) = "*PageDimensions";
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 16) = 200;
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v41 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v42 = 32LL * v9;
  *(_QWORD *)(v42 + *(_QWORD *)(a1 + 176)) = "*dwPaperSizeID - synth";
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 20) = 80;
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v42 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v43 = 32LL * (v9 + 1);
  *(_QWORD *)(v43 + *(_QWORD *)(a1 + 176)) = "*dwPaperSourceID - synth";
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v43 + *(_QWORD *)(a1 + 176) + 28) = 16;
  v44 = 32LL * (v9 + 2);
  *(_QWORD *)(v44 + *(_QWORD *)(a1 + 176)) = "*dwMediaTypeID - synth";
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v44 + *(_QWORD *)(a1 + 176) + 28) = 32;
  v45 = 32LL * (v9 + 3);
  *(_QWORD *)(v45 + *(_QWORD *)(a1 + 176)) = "*dwCollateID - synth";
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 16) = 360;
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v45 + *(_QWORD *)(a1 + 176) + 28) = 1024;
  v46 = v9 + 4;
  v9 += 5;
  v46 *= 32;
  *(_QWORD *)(v46 + *(_QWORD *)(a1 + 176)) = "*MemoryConfigMB";
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 16) = 332;
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 24) = 2048;
  *(_DWORD *)(v46 + *(_QWORD *)(a1 + 176) + 28) = 64;
  v47 = 32LL * v9;
  *(_QWORD *)(v47 + *(_QWORD *)(a1 + 176)) = "*MemoryConfigMB";
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 16) = 332;
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 24) = 2112;
  *(_DWORD *)(v47 + *(_QWORD *)(a1 + 176) + 28) = 64;
  v48 = 32LL * (v9 + 1);
  *(_QWORD *)(v48 + *(_QWORD *)(a1 + 176)) = "*MemoryConfigKB";
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 16) = 328;
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 24) = 162;
  *(_DWORD *)(v48 + *(_QWORD *)(a1 + 176) + 28) = 64;
  v49 = 32LL * (v9 + 2);
  *(_QWORD *)(v49 + *(_QWORD *)(a1 + 176)) = "*MemoryConfigKB";
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 16) = 328;
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 24) = 226;
  *(_DWORD *)(v49 + *(_QWORD *)(a1 + 176) + 28) = 64;
  v50 = 32LL * (v9 + 3);
  *(_QWORD *)(v50 + *(_QWORD *)(a1 + 176)) = "*OutputOrderReversed? (option level)";
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 16) = 356;
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v50 + *(_QWORD *)(a1 + 176) + 28) = 2048;
  v51 = v9 + 4;
  v9 += 5;
  *(_DWORD *)(32 * v51 + *(_QWORD *)(a1 + 176) + 12) = 0;
  v52 = 32LL * v9;
  *(_QWORD *)(v52 + *(_QWORD *)(a1 + 176)) = "*rcIconID (Opt)";
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 16) = 112;
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 20) = 28;
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 24) = 0x10000;
  *(_DWORD *)(v52 + *(_QWORD *)(a1 + 176) + 28) = -1;
  v53 = 32LL * (v9 + 1);
  *(_QWORD *)(v53 + *(_QWORD *)(a1 + 176)) = "*PageProtectMem (Opt)";
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 16) = 212;
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 20) = 88;
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v53 + *(_QWORD *)(a1 + 176) + 28) = 2;
  *(_DWORD *)(32LL * (v9 + 2) + *(_QWORD *)(a1 + 176) + 12) = 0;
  v54 = 32LL * (v9 + 3);
  *(_QWORD *)(v54 + *(_QWORD *)(a1 + 176)) = "*DPI";
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 16) = 248;
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v54 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v55 = 32LL * (v9 + 4);
  *(_QWORD *)(v55 + *(_QWORD *)(a1 + 176)) = "*TextDPI";
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 16) = 256;
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 20) = 8;
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v55 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v56 = v9 + 5;
  v9 += 6;
  v56 *= 32;
  *(_QWORD *)(v56 + *(_QWORD *)(a1 + 176)) = "*MinStripBlankPixels";
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 16) = 272;
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v56 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v57 = 32LL * v9;
  *(_QWORD *)(v57 + *(_QWORD *)(a1 + 176)) = "*RedDeviceGamma";
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 16) = 276;
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 20) = 36;
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v57 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v58 = 32LL * (v9 + 1);
  *(_QWORD *)(v58 + *(_QWORD *)(a1 + 176)) = "*GreenDeviceGamma";
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 16) = 280;
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 20) = 40;
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v58 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v59 = 32LL * (v9 + 2);
  *(_QWORD *)(v59 + *(_QWORD *)(a1 + 176)) = "*BlueDeviceGamma";
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 16) = 284;
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 20) = 44;
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v59 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v60 = v9 + 3;
  v9 += 4;
  v60 *= 32;
  *(_QWORD *)(v60 + *(_QWORD *)(a1 + 176)) = "*PinsPerPhysPass";
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 16) = 260;
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 20) = 20;
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v60 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v61 = 32LL * v9;
  *(_QWORD *)(v61 + *(_QWORD *)(a1 + 176)) = "*PinsPerLogPass";
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 16) = 264;
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 20) = 24;
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v61 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v62 = 32LL * (v9 + 1);
  *(_QWORD *)(v62 + *(_QWORD *)(a1 + 176)) = "*SpotDiameter";
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 16) = 252;
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 20) = 28;
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 24) = 1;
  *(_DWORD *)(v62 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v63 = 32LL * (v9 + 2);
  *(_QWORD *)(v63 + *(_QWORD *)(a1 + 176)) = "*RequireUniDir?";
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 16) = 268;
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 20) = 32;
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v63 + *(_QWORD *)(a1 + 176) + 28) = 1;
  v64 = 32LL * (v9 + 3);
  *(_QWORD *)(v64 + *(_QWORD *)(a1 + 176)) = "*Color?";
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 16) = 288;
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v64 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v65 = v9 + 4;
  v9 += 5;
  v65 *= 32;
  *(_QWORD *)(v65 + *(_QWORD *)(a1 + 176)) = "*DevNumOfPlanes";
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 16) = 292;
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 20) = 4;
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v65 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v66 = 32LL * v9;
  *(_QWORD *)(v66 + *(_QWORD *)(a1 + 176)) = "*DevBPP";
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 16) = 296;
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 20) = 8;
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v66 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v67 = 32LL * (v9 + 1);
  *(_QWORD *)(v67 + *(_QWORD *)(a1 + 176)) = "*ColorPlaneOrder";
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 16) = 300;
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 20) = 12;
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v67 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v68 = 32LL * (v9 + 2);
  *(_QWORD *)(v68 + *(_QWORD *)(a1 + 176)) = "*DrvBPP";
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 16) = 304;
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v68 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v69 = v9 + 3;
  v9 += 4;
  v69 *= 32;
  *(_QWORD *)(v69 + *(_QWORD *)(a1 + 176)) = "*IPCallbackID";
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 16) = 308;
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 20) = 20;
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v69 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v70 = 32LL * v9;
  *(_QWORD *)(v70 + *(_QWORD *)(a1 + 176)) = "*RasterMode";
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 16) = 316;
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 20) = 24;
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 8) = 1;
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v70 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v71 = 32LL * (v9 + 1);
  *(_QWORD *)(v71 + *(_QWORD *)(a1 + 176)) = "*PaletteSize";
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 16) = 320;
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 20) = 28;
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 8) = 2;
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v71 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v72 = 32LL * (v9 + 2);
  *(_QWORD *)(v72 + *(_QWORD *)(a1 + 176)) = "*PaletteProgrammable?";
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 16) = 324;
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 20) = 32;
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v72 + *(_QWORD *)(a1 + 176) + 28) = 128;
  v73 = v9 + 3;
  v9 += 4;
  v73 *= 32;
  *(_QWORD *)(v73 + *(_QWORD *)(a1 + 176)) = "*PrintableArea";
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 16) = 156;
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v73 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v74 = 32LL * v9;
  *(_QWORD *)(v74 + *(_QWORD *)(a1 + 176)) = "*PrintableOrigin";
  v75 = v9 + 1;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 16) = 160;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 20) = 8;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v74 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v76 = 32LL * (v9 + 1);
  v9 += 2;
  *(_QWORD *)(v76 + *(_QWORD *)(a1 + 176)) = "*MinSize";
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 16) = 172;
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 20) = 24;
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v76 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v77 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 216) = v75;
  v78 = 32LL * v9;
  *(_QWORD *)(v78 + v77) = "*MaxSize";
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 16) = 176;
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 20) = 32;
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v78 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v79 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 220) = v9;
  v80 = 32LL * (v9 + 1);
  *(_QWORD *)(v80 + v79) = "*TopMargin";
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 16) = 180;
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 20) = 40;
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v80 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v81 = v9 + 2;
  v9 += 3;
  v81 *= 32;
  *(_QWORD *)(v81 + *(_QWORD *)(a1 + 176)) = "*BottomMargin";
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 16) = 184;
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 20) = 44;
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v81 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v82 = 32LL * v9;
  *(_QWORD *)(v82 + *(_QWORD *)(a1 + 176)) = "*MaxPrintableWidth";
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 16) = 188;
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 20) = 48;
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v82 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v83 = 32LL * (v9 + 1);
  *(_QWORD *)(v83 + *(_QWORD *)(a1 + 176)) = "*MinLeftMargin";
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 16) = 192;
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 20) = 52;
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v83 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v84 = 32LL * (v9 + 2);
  *(_QWORD *)(v84 + *(_QWORD *)(a1 + 176)) = "*CenterPrintable?";
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 16) = 196;
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 20) = 56;
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v84 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v85 = v9 + 3;
  v9 += 4;
  v85 *= 32;
  *(_QWORD *)(v85 + *(_QWORD *)(a1 + 176)) = "*RotateSize?";
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 16) = 204;
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 20) = 60;
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v85 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v86 = 32LL * v9;
  *(_QWORD *)(v86 + *(_QWORD *)(a1 + 176)) = "*PortRotationAngle";
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 16) = 208;
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 20) = 64;
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v86 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v87 = 32LL * (v9 + 1);
  *(_QWORD *)(v87 + *(_QWORD *)(a1 + 176)) = "*CustCursorOriginX";
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 16) = 216;
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 20) = 68;
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v87 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v88 = 32LL * (v9 + 2);
  *(_QWORD *)(v88 + *(_QWORD *)(a1 + 176)) = "*CustCursorOriginY";
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 16) = 220;
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 20) = 76;
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v88 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v89 = 32LL * (v9 + 3);
  *(_QWORD *)(v89 + *(_QWORD *)(a1 + 176)) = "*CustPrintableOriginX";
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 16) = 224;
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 20) = 84;
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v89 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v90 = 32LL * (v9 + 4);
  *(_QWORD *)(v90 + *(_QWORD *)(a1 + 176)) = "*CustPrintableOriginY";
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 16) = 228;
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 20) = 92;
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v90 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v91 = 32LL * (v9 + 5);
  *(_QWORD *)(v91 + *(_QWORD *)(a1 + 176)) = "*CustPrintableSizeX";
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 16) = 232;
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 20) = 100;
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v91 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v92 = 32LL * (v9 + 6);
  *(_QWORD *)(v92 + *(_QWORD *)(a1 + 176)) = "*CustPrintableSizeY";
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 16) = 236;
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 20) = 108;
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v92 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v93 = v9 + 8;
  v94 = 32LL * (v9 + 7);
  v9 += 9;
  *(_DWORD *)(v94 + *(_QWORD *)(a1 + 176) + 12) = 0;
  *(_DWORD *)(32LL * v93 + *(_QWORD *)(a1 + 176) + 12) = 0;
  v95 = 32LL * v9;
  *(_QWORD *)(v95 + *(_QWORD *)(a1 + 176)) = "*dwSSTableCmdIndex - synth";
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 16) = 0;
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 24) = 256;
  *(_DWORD *)(v95 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v96 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 224) = v9++;
  v97 = 32LL * v9;
  v98 = v9++;
  *(_QWORD *)(v97 + v96) = "*dwSSCmdSelectIndex - synth";
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 16) = 132;
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 24) = 256;
  *(_DWORD *)(v97 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v99 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 228) = v98;
  v100 = 32LL * v9;
  v101 = v9++;
  *(_QWORD *)(v100 + v99) = "*CursorOrigin";
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 16) = 164;
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 20) = 16;
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 12) = 8;
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 8) = 0;
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 24) = 512;
  *(_DWORD *)(v100 + *(_QWORD *)(a1 + 176) + 28) = 2;
  v102 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 232) = v101;
  v103 = 32LL * v9;
  v104 = v9++;
  *(_QWORD *)(v103 + v102) = "*Constraints";
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 16) = 136;
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v103 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v105 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 236) = v104;
  v106 = 32LL * v9;
  v107 = v9++;
  *(_QWORD *)(v106 + v105) = "*InvalidCombination";
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 16) = 140;
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 20) = 0;
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 12) = 4;
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 8) = -1;
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 24) = 0;
  *(_DWORD *)(v106 + *(_QWORD *)(a1 + 176) + 28) = 0;
  v108 = *(_QWORD *)(a1 + 176);
  *(_DWORD *)(a1 + 240) = v107;
  *(_DWORD *)(32LL * v9 + v108 + 12) = 0;
  return v9 + 1;
}

```

## disassembly

```asm
0x18002e550  mov     r8, [rcx+0B0h]
0x18002e557  mov     r9d, edx
0x18002e55a  test    r8, r8
0x18002e55d  jz      loc_180030C5F
0x18002e563  xor     r11d, r11d
0x18002e566  lea     r10, aFeaturetype; "*FeatureType"
0x18002e56d  mov     eax, r9d
0x18002e570  inc     r9d
0x18002e573  shl     rax, 5
0x18002e577  mov     edx, r9d
0x18002e57a  inc     r9d
0x18002e57d  shl     rdx, 5
0x18002e581  mov     [rax+r8+0Ch], r11d
0x18002e586  lea     r8, aPrioritySynthe; "*Priority - synthesized"
0x18002e58d  mov     rax, [rcx+0B0h]
0x18002e594  mov     [rdx+rax], r8
0x18002e598  mov     rax, [rcx+0B0h]
0x18002e59f  mov     r8d, r9d
0x18002e5a2  mov     dword ptr [rdx+rax+10h], 0Ch
0x18002e5aa  mov     rax, [rcx+0B0h]
0x18002e5b1  mov     dword ptr [rdx+rax+14h], 28h ; '('
0x18002e5b9  mov     rax, [rcx+0B0h]
0x18002e5c0  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e5c8  mov     rax, [rcx+0B0h]
0x18002e5cf  mov     [rdx+rax+8], r11d
0x18002e5d4  mov     rax, [rcx+0B0h]
0x18002e5db  mov     [rdx+rax+18h], r11d
0x18002e5e0  mov     rax, [rcx+0B0h]
0x18002e5e7  mov     [rdx+rax+1Ch], r11d
0x18002e5ec  mov     rax, [rcx+0B0h]
0x18002e5f3  mov     edx, r9d
0x18002e5f6  inc     r9d
0x18002e5f9  shl     rdx, 5
0x18002e5fd  mov     [rdx+rax], r10
0x18002e601  mov     rax, [rcx+0B0h]
0x18002e608  mov     [rdx+rax+10h], r11d
0x18002e60d  mov     rax, [rcx+0B0h]
0x18002e614  mov     dword ptr [rdx+rax+14h], 2Ch ; ','
0x18002e61c  mov     rax, [rcx+0B0h]
0x18002e623  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e62b  mov     rax, [rcx+0B0h]
0x18002e632  mov     [rdx+rax+8], r11d
0x18002e637  mov     rax, [rcx+0B0h]
0x18002e63e  mov     [rdx+rax+18h], r11d
0x18002e643  mov     rax, [rcx+0B0h]
0x18002e64a  mov     [rdx+rax+1Ch], r11d
0x18002e64f  mov     rax, [rcx+0B0h]
0x18002e656  mov     [rcx+0D0h], r8d
0x18002e65d  lea     r8, aConcealfromui; "*ConcealFromUI?"
0x18002e664  mov     edx, r9d
0x18002e667  inc     r9d
0x18002e66a  shl     rdx, 5
0x18002e66e  mov     [rdx+rax], r8
0x18002e672  lea     r8, aUpdatequalitym_0; "*UpdateQualityMacro?"
0x18002e679  mov     rax, [rcx+0B0h]
0x18002e680  mov     dword ptr [rdx+rax+10h], 38h ; '8'
0x18002e688  mov     rax, [rcx+0B0h]
0x18002e68f  mov     dword ptr [rdx+rax+14h], 10h
0x18002e697  mov     rax, [rcx+0B0h]
0x18002e69e  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e6a6  mov     rax, [rcx+0B0h]
0x18002e6ad  mov     dword ptr [rdx+rax+8], 1
0x18002e6b5  mov     rax, [rcx+0B0h]
0x18002e6bc  mov     dword ptr [rdx+rax+18h], 40000h
0x18002e6c4  mov     rax, [rcx+0B0h]
0x18002e6cb  mov     [rdx+rax+1Ch], r11d
0x18002e6d0  mov     rax, [rcx+0B0h]
0x18002e6d7  mov     edx, r9d
0x18002e6da  inc     r9d
0x18002e6dd  shl     rdx, 5
0x18002e6e1  mov     [rdx+rax], r8
0x18002e6e5  mov     rax, [rcx+0B0h]
0x18002e6ec  mov     dword ptr [rdx+rax+10h], 3Ch ; '<'
0x18002e6f4  mov     rax, [rcx+0B0h]
0x18002e6fb  mov     dword ptr [rdx+rax+14h], 10h
0x18002e703  mov     rax, [rcx+0B0h]
0x18002e70a  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e712  mov     rax, [rcx+0B0h]
0x18002e719  mov     dword ptr [rdx+rax+8], 4
0x18002e721  mov     rax, [rcx+0B0h]
0x18002e728  mov     dword ptr [rdx+rax+18h], 40000h
0x18002e730  mov     rax, [rcx+0B0h]
0x18002e737  mov     [rdx+rax+1Ch], r11d
0x18002e73c  mov     edx, r9d
0x18002e73f  shl     rdx, 5
0x18002e743  mov     rax, [rcx+0B0h]
0x18002e74a  lea     r8, aRcnameidFea; "*rcNameID (Fea)"
0x18002e751  inc     r9d
0x18002e754  mov     [rdx+rax], r8
0x18002e758  lea     r8, aNameFea; "*Name (Fea)"
0x18002e75f  mov     rax, [rcx+0B0h]
0x18002e766  mov     dword ptr [rdx+rax+10h], 24h ; '$'
0x18002e76e  mov     rax, [rcx+0B0h]
0x18002e775  mov     dword ptr [rdx+rax+14h], 0Ch
0x18002e77d  mov     rax, [rcx+0B0h]
0x18002e784  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e78c  mov     rax, [rcx+0B0h]
0x18002e793  mov     [rdx+rax+8], r11d
0x18002e798  mov     rax, [rcx+0B0h]
0x18002e79f  mov     dword ptr [rdx+rax+18h], 4010h
0x18002e7a7  mov     rax, [rcx+0B0h]
0x18002e7ae  mov     [rdx+rax+1Ch], r11d
0x18002e7b3  mov     rax, [rcx+0B0h]
0x18002e7ba  mov     edx, r9d
0x18002e7bd  inc     r9d
0x18002e7c0  shl     rdx, 5
0x18002e7c4  mov     [rdx+rax], r8
0x18002e7c8  lea     r8, aPrintschemakey; "*PrintSchemaKeywordMap (fea)"
0x18002e7cf  mov     rax, [rcx+0B0h]
0x18002e7d6  mov     dword ptr [rdx+rax+10h], 20h ; ' '
0x18002e7de  mov     rax, [rcx+0B0h]
0x18002e7e5  mov     dword ptr [rdx+rax+14h], 0Ch
0x18002e7ed  mov     rax, [rcx+0B0h]
0x18002e7f4  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e7fc  mov     rax, [rcx+0B0h]
0x18002e803  mov     [rdx+rax+8], r11d
0x18002e808  mov     rax, [rcx+0B0h]
0x18002e80f  mov     dword ptr [rdx+rax+18h], 26h ; '&'
0x18002e817  mov     rax, [rcx+0B0h]
0x18002e81e  mov     [rdx+rax+1Ch], r11d
0x18002e823  mov     rax, [rcx+0B0h]
0x18002e82a  mov     edx, r9d
0x18002e82d  inc     r9d
0x18002e830  shl     rdx, 5
0x18002e834  mov     [rdx+rax], r8
0x18002e838  lea     r8, aPrintschemanam_1; "*PrintSchemaNamespace (fea)"
0x18002e83f  mov     rax, [rcx+0B0h]
0x18002e846  mov     dword ptr [rdx+rax+10h], 2Ch ; ','
0x18002e84e  mov     rax, [rcx+0B0h]
0x18002e855  mov     dword ptr [rdx+rax+14h], 4
0x18002e85d  mov     rax, [rcx+0B0h]
0x18002e864  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e86c  mov     rax, [rcx+0B0h]
0x18002e873  mov     [rdx+rax+8], r11d
0x18002e878  mov     rax, [rcx+0B0h]
0x18002e87f  mov     dword ptr [rdx+rax+18h], 4
0x18002e887  mov     rax, [rcx+0B0h]
0x18002e88e  mov     [rdx+rax+1Ch], r11d
0x18002e893  mov     rax, [rcx+0B0h]
0x18002e89a  mov     edx, r9d
0x18002e89d  inc     r9d
0x18002e8a0  shl     rdx, 5
0x18002e8a4  mov     [rdx+rax], r8
0x18002e8a8  lea     r8, aHelpindexFea; "*HelpIndex (Fea)"
0x18002e8af  mov     rax, [rcx+0B0h]
0x18002e8b6  mov     dword ptr [rdx+rax+10h], 30h ; '0'
0x18002e8be  mov     rax, [rcx+0B0h]
0x18002e8c5  mov     dword ptr [rdx+rax+14h], 8
0x18002e8cd  mov     rax, [rcx+0B0h]
0x18002e8d4  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e8dc  mov     rax, [rcx+0B0h]
0x18002e8e3  mov     [rdx+rax+8], r11d
0x18002e8e8  mov     rax, [rcx+0B0h]
0x18002e8ef  mov     dword ptr [rdx+rax+18h], 4
0x18002e8f7  mov     rax, [rcx+0B0h]
0x18002e8fe  mov     [rdx+rax+1Ch], r11d
0x18002e903  mov     rax, [rcx+0B0h]
0x18002e90a  mov     edx, r9d
0x18002e90d  shl     rdx, 5
0x18002e911  mov     [rdx+rax], r8
0x18002e915  mov     rax, [rcx+0B0h]
0x18002e91c  mov     dword ptr [rdx+rax+10h], 40h ; '@'
0x18002e924  mov     rax, [rcx+0B0h]
0x18002e92b  mov     dword ptr [rdx+rax+14h], 50h ; 'P'
0x18002e933  mov     rax, [rcx+0B0h]
0x18002e93a  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e942  mov     rax, [rcx+0B0h]
0x18002e949  lea     r8, aFeakeywordSynt; "*FeaKeyWord - Synthesized"
0x18002e950  inc     r9d
0x18002e953  lea     r10, aDefaultoption; "*DefaultOption"
0x18002e95a  mov     dword ptr [rdx+rax+8], 0FFFFFFFFh
0x18002e962  mov     rax, [rcx+0B0h]
0x18002e969  mov     dword ptr [rdx+rax+18h], 20000h
0x18002e971  mov     rax, [rcx+0B0h]
0x18002e978  mov     [rdx+rax+1Ch], r11d
0x18002e97d  mov     rax, [rcx+0B0h]
0x18002e984  mov     edx, r9d
0x18002e987  inc     r9d
0x18002e98a  shl     rdx, 5
0x18002e98e  mov     [rdx+rax], r8
0x18002e992  lea     r8, aUitype; "*UIType"
0x18002e999  mov     rax, [rcx+0B0h]
0x18002e9a0  mov     dword ptr [rdx+rax+10h], 1Ch
0x18002e9a8  mov     rax, [rcx+0B0h]
0x18002e9af  mov     [rdx+rax+14h], r11d
0x18002e9b4  mov     rax, [rcx+0B0h]
0x18002e9bb  mov     dword ptr [rdx+rax+0Ch], 4
0x18002e9c3  mov     rax, [rcx+0B0h]
0x18002e9ca  mov     [rdx+rax+8], r11d
0x18002e9cf  mov     rax, [rcx+0B0h]
0x18002e9d6  mov     dword ptr [rdx+rax+18h], 5
0x18002e9de  mov     rax, [rcx+0B0h]
0x18002e9e5  mov     [rdx+rax+1Ch], r11d
0x18002e9ea  mov     rax, [rcx+0B0h]
0x18002e9f1  mov     edx, r9d
0x18002e9f4  inc     r9d
0x18002e9f7  shl     rdx, 5
0x18002e9fb  mov     [rdx+rax], r8
0x18002e9ff  mov     rax, [rcx+0B0h]
0x18002ea06  mov     dword ptr [rdx+rax+10h], 4
0x18002ea0e  mov     rax, [rcx+0B0h]
0x18002ea15  mov     dword ptr [rdx+rax+14h], 20h ; ' '
0x18002ea1d  mov     rax, [rcx+0B0h]
0x18002ea24  mov     dword ptr [rdx+rax+0Ch], 4
0x18002ea2c  mov     rax, [rcx+0B0h]
0x18002ea33  mov     [rdx+rax+8], r11d
0x18002ea38  mov     rax, [rcx+0B0h]
0x18002ea3f  mov     [rdx+rax+18h], r11d
0x18002ea44  mov     rax, [rcx+0B0h]
0x18002ea4b  mov     [rdx+rax+1Ch], r11d
0x18002ea50  mov     rax, [rcx+0B0h]
0x18002ea57  mov     edx, r9d
0x18002ea5a  inc     r9d
0x18002ea5d  shl     rdx, 5
0x18002ea61  mov     r8d, r9d
0x18002ea64  mov     [rdx+rax+0Ch], r11d
0x18002ea69  mov     rax, [rcx+0B0h]
0x18002ea70  mov     edx, r9d
0x18002ea73  inc     r9d
0x18002ea76  shl     rdx, 5
0x18002ea7a  mov     [rdx+rax], r10
0x18002ea7e  mov     rax, [rcx+0B0h]
0x18002ea85  mov     dword ptr [rdx+rax+10h], 8
0x18002ea8d  mov     rax, [rcx+0B0h]
0x18002ea94  mov     dword ptr [rdx+rax+14h], 14h
0x18002ea9c  mov     rax, [rcx+0B0h]
0x18002eaa3  mov     dword ptr [rdx+rax+0Ch], 4
0x18002eaab  mov     rax, [rcx+0B0h]
0x18002eab2  mov     [rdx+rax+8], r11d
0x18002eab7  mov     rax, [rcx+0B0h]
0x18002eabe  mov     [rdx+rax+18h], r11d
0x18002eac3  mov     rax, [rcx+0B0h]
0x18002eaca  mov     [rdx+rax+1Ch], r11d
0x18002eacf  mov     rax, [rcx+0B0h]
0x18002ead6  mov     [rcx+0D4h], r8d
0x18002eadd  lea     r8, aRciconidFea; "*rcIconID (Fea)"
0x18002eae4  mov     edx, r9d
0x18002eae7  shl     rdx, 5
0x18002eaeb  mov     [rdx+rax], r8
0x18002eaef  mov     rax, [rcx+0B0h]
0x18002eaf6  mov     dword ptr [rdx+rax+10h], 28h ; '('
0x18002eafe  mov     rax, [rcx+0B0h]
0x18002eb05  mov     dword ptr [rdx+rax+14h], 44h ; 'D'
0x18002eb0d  mov     rax, [rcx+0B0h]
0x18002eb14  mov     dword ptr [rdx+rax+0Ch], 4
0x18002eb1c  mov     rax, [rcx+0B0h]
0x18002eb23  mov     [rdx+rax+8], r11d
0x18002eb28  mov     rax, [rcx+0B0h]
0x18002eb2f  lea     r8, aOptkeywordSynt; "*OptKeyWord - synth"
0x18002eb36  inc     r9d
0x18002eb39  mov     dword ptr [rdx+rax+18h], 10000h
0x18002eb41  mov     rax, [rcx+0B0h]
0x18002eb48  mov     [rdx+rax+1Ch], r11d
0x18002eb4d  mov     rax, [rcx+0B0h]
0x18002eb54  mov     edx, r9d
0x18002eb57  inc     r9d
0x18002eb5a  shl     rdx, 5
0x18002eb5e  mov     [rdx+rax+0Ch], r11d
0x18002eb63  mov     rax, [rcx+0B0h]
0x18002eb6a  mov     edx, r9d
0x18002eb6d  inc     r9d
0x18002eb70  shl     rdx, 5
0x18002eb74  mov     [rdx+rax], r8
0x18002eb78  lea     r8, aRcnameidOpt; "*rcNameID (Opt)"
0x18002eb7f  mov     rax, [rcx+0B0h]
0x18002eb86  mov     dword ptr [rdx+rax+10h], 64h ; 'd'
0x18002eb8e  mov     rax, [rcx+0B0h]
0x18002eb95  mov     [rdx+rax+14h], r11d
0x18002eb9a  mov     rax, [rcx+0B0h]
0x18002eba1  mov     dword ptr [rdx+rax+0Ch], 4
0x18002eba9  mov     rax, [rcx+0B0h]
0x18002ebb0  mov     [rdx+rax+8], r11d
0x18002ebb5  mov     rax, [rcx+0B0h]
0x18002ebbc  mov     dword ptr [rdx+rax+18h], 4
0x18002ebc4  mov     rax, [rcx+0B0h]
0x18002ebcb  mov     dword ptr [rdx+rax+1Ch], 0FFFFFFFFh
0x18002ebd3  mov     rax, [rcx+0B0h]
0x18002ebda  mov     edx, r9d
0x18002ebdd  inc     r9d
0x18002ebe0  shl     rdx, 5
0x18002ebe4  mov     [rdx+rax], r8
0x18002ebe8  lea     r8, aNameOpt; "*Name (Opt)"
0x18002ebef  mov     rax, [rcx+0B0h]
0x18002ebf6  mov     dword ptr [rdx+rax+10h], 6Ch ; 'l'
0x18002ebfe  mov     rax, [rcx+0B0h]
0x18002ec05  mov     dword ptr [rdx+rax+14h], 0Ch
0x18002ec0d  mov     rax, [rcx+0B0h]
0x18002ec14  mov     dword ptr [rdx+rax+0Ch], 4
0x18002ec1c  mov     rax, [rcx+0B0h]
0x18002ec23  mov     [rdx+rax+8], r11d
0x18002ec28  mov     rax, [rcx+0B0h]
0x18002ec2f  mov     dword ptr [rdx+rax+18h], 4010h
0x18002ec37  mov     rax, [rcx+0B0h]
0x18002ec3e  mov     dword ptr [rdx+rax+1Ch], 0FFFFFFFFh
0x18002ec46  mov     rax, [rcx+0B0h]
0x18002ec4d  mov     edx, r9d
0x18002ec50  inc     r9d
0x18002ec53  shl     rdx, 5
0x18002ec57  mov     [rdx+rax], r8
0x18002ec5b  lea     r8, aPrintschemakey_1; "*PrintSchemaKeywordMap (opt)"
  ... truncated ...
```
