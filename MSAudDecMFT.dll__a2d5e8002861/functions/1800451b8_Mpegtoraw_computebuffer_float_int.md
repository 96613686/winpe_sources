# Mpegtoraw::computebuffer(float *,int)

- ea: `0x1800451b8`
- end: `0x180046191`
- name: `?computebuffer@Mpegtoraw@@AEAAXPEAMH@Z`
- size: `4057`
- prototype: `void __fastcall(Mpegtoraw *__hidden this, float *, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180095394`

## pseudocode

```c
void __fastcall Mpegtoraw::computebuffer(Mpegtoraw *this, float *a2, int a3)
{
  __int64 v3; // rax
  float v4; // xmm1_4
  __int64 v5; // r9
  __int64 v6; // r8
  float v7; // xmm2_4
  float v8; // xmm3_4
  float v9; // xmm7_4
  float v10; // xmm5_4
  float v11; // xmm11_4
  float v12; // xmm9_4
  float v13; // xmm15_4
  float v14; // xmm13_4
  __int64 v15; // r10
  __int64 v16; // rax
  float v17; // xmm0_4
  __int64 v18; // r9
  __int64 v19; // r8
  float v20; // xmm12_4
  float v21; // xmm10_4
  float v22; // xmm6_4
  float v23; // xmm8_4
  float v24; // xmm4_4
  float v25; // xmm14_4
  float v26; // xmm13_4
  float v27; // xmm15_4
  float v28; // xmm0_4
  float v29; // xmm3_4
  float v30; // xmm0_4
  float v31; // xmm5_4
  float v32; // xmm12_4
  float v33; // xmm10_4
  float v34; // xmm11_4
  float v35; // xmm0_4
  float v36; // xmm7_4
  float v37; // xmm14_4
  float v38; // xmm2_4
  float v39; // xmm1_4
  float v40; // xmm0_4
  float v41; // xmm6_4
  float v42; // xmm4_4
  float v43; // xmm2_4
  float v44; // xmm1_4
  float v45; // xmm12_4
  float v46; // xmm14_4
  float v47; // xmm3_4
  float v48; // xmm9_4
  float v49; // xmm13_4
  float v50; // xmm2_4
  float v51; // xmm0_4
  float v52; // xmm1_4
  float v53; // xmm5_4
  float v54; // xmm11_4
  float v55; // xmm8_4
  float v56; // xmm15_4
  float v57; // xmm12_4
  float v58; // xmm7_4
  float v59; // xmm0_4
  float v60; // xmm14_4
  float v61; // xmm11_4
  float v62; // xmm8_4
  float v63; // xmm15_4
  float v64; // xmm10_4
  float v65; // xmm4_4
  float v66; // xmm3_4
  float v67; // xmm12_4
  float v68; // xmm0_4
  float v69; // xmm9_4
  float v70; // xmm2_4
  float v71; // xmm6_4
  float v72; // xmm4_4
  float v73; // xmm13_4
  float v74; // xmm10_4
  float v75; // xmm11_4
  float v76; // xmm9_4
  float v77; // xmm6_4
  int v78; // xmm0_4
  int v79; // xmm7_4
  float v80; // xmm5_4
  float v81; // xmm1_4
  float v82; // xmm0_4
  float v83; // xmm14_4
  int v84; // xmm0_4
  float v85; // xmm1_4
  float v86; // xmm0_4
  float v87; // xmm14_4
  int v88; // xmm0_4
  int v89; // xmm0_4
  int v90; // xmm1_4
  int v91; // xmm0_4
  float v92; // xmm1_4
  float v93; // xmm2_4
  float v94; // xmm3_4
  float v95; // xmm8_4
  float v96; // xmm6_4
  float v97; // xmm11_4
  float v98; // xmm10_4
  float v99; // xmm15_4
  float v100; // xmm14_4
  float v101; // xmm0_4
  float v102; // xmm12_4
  float v103; // xmm9_4
  float v104; // xmm5_4
  float v105; // xmm7_4
  float v106; // xmm4_4
  float v107; // xmm0_4
  float v108; // xmm2_4
  float v109; // xmm14_4
  float v110; // xmm0_4
  float v111; // xmm3_4
  float v112; // xmm15_4
  float v113; // xmm10_4
  float v114; // xmm0_4
  float v115; // xmm6_4
  float v116; // xmm12_4
  float v117; // xmm0_4
  float v118; // xmm8_4
  float v119; // xmm13_4
  float v120; // xmm9_4
  float v121; // xmm1_4
  float v122; // xmm11_4
  float v123; // xmm0_4
  float v124; // xmm5_4
  float v125; // xmm4_4
  float v126; // xmm0_4
  float v127; // xmm12_4
  float v128; // xmm1_4
  float v129; // xmm2_4
  float v130; // xmm13_4
  float v131; // xmm1_4
  float v132; // xmm2_4
  float v133; // xmm14_4
  float v134; // xmm15_4
  float v135; // xmm3_4
  float v136; // xmm11_4
  float v137; // xmm6_4
  float v138; // xmm13_4
  float v139; // xmm6_4
  float v140; // xmm10_4
  float v141; // xmm4_4
  float v142; // xmm5_4
  float v143; // xmm8_4
  float v144; // xmm12_4
  float v145; // xmm2_4
  float v146; // xmm9_4
  float v147; // xmm7_4
  float v148; // xmm1_4
  float v149; // xmm10_4
  float v150; // xmm6_4
  float v151; // xmm2_4
  float v152; // xmm0_4
  float v153; // xmm1_4
  float v154; // xmm2_4
  int v155; // xmm1_4
  float v156; // xmm3_4
  int v157; // xmm1_4
  float v158; // xmm5_4
  float v159; // xmm2_4
  float v160; // xmm1_4
  float v161; // xmm9_4
  float v162; // xmm15_4
  int v163; // xmm0_4
  int v164; // xmm15_4
  float v165; // xmm0_4
  float v166; // xmm1_4
  float v167; // xmm1_4
  float v168; // [rsp+0h] [rbp-C8h]
  float v169; // [rsp+0h] [rbp-C8h]
  float v170; // [rsp+0h] [rbp-C8h]
  float v171; // [rsp+0h] [rbp-C8h]
  float v172; // [rsp+0h] [rbp-C8h]
  float v173; // [rsp+4h] [rbp-C4h]
  float v174; // [rsp+4h] [rbp-C4h]
  float v175; // [rsp+4h] [rbp-C4h]
  float v176; // [rsp+4h] [rbp-C4h]
  float v177; // [rsp+8h] [rbp-C0h]
  float v178; // [rsp+8h] [rbp-C0h]
  float v179; // [rsp+8h] [rbp-C0h]
  float v180; // [rsp+8h] [rbp-C0h]
  float v181; // [rsp+8h] [rbp-C0h]
  float v182; // [rsp+8h] [rbp-C0h]
  float v183; // [rsp+Ch] [rbp-BCh]
  float v184; // [rsp+Ch] [rbp-BCh]
  float v185; // [rsp+Ch] [rbp-BCh]
  float v186; // [rsp+Ch] [rbp-BCh]
  float v187; // [rsp+10h] [rbp-B8h]
  float v188; // [rsp+10h] [rbp-B8h]
  float v189; // [rsp+10h] [rbp-B8h]
  float v190; // [rsp+10h] [rbp-B8h]
  float v191; // [rsp+10h] [rbp-B8h]
  float v192; // [rsp+14h] [rbp-B4h]
  float v193; // [rsp+14h] [rbp-B4h]
  float v194; // [rsp+14h] [rbp-B4h]
  float v195; // [rsp+14h] [rbp-B4h]
  float v196; // [rsp+14h] [rbp-B4h]
  float v197; // [rsp+14h] [rbp-B4h]
  float v198; // [rsp+18h] [rbp-B0h]
  float v199; // [rsp+18h] [rbp-B0h]
  float v200; // [rsp+18h] [rbp-B0h]
  float v201; // [rsp+18h] [rbp-B0h]
  float v202; // [rsp+18h] [rbp-B0h]
  float v203; // [rsp+D0h] [rbp+8h]
  float v204; // [rsp+D0h] [rbp+8h]
  float v205; // [rsp+D0h] [rbp+8h]
  float v206; // [rsp+D0h] [rbp+8h]
  float v207; // [rsp+D0h] [rbp+8h]
  float v208; // [rsp+D0h] [rbp+8h]
  float v209; // [rsp+D0h] [rbp+8h]
  float v210; // [rsp+D8h] [rbp+10h]
  float v211; // [rsp+D8h] [rbp+10h]
  float v212; // [rsp+D8h] [rbp+10h]
  float v213; // [rsp+D8h] [rbp+10h]
  float v214; // [rsp+D8h] [rbp+10h]
  float v215; // [rsp+D8h] [rbp+10h]
  float v216; // [rsp+D8h] [rbp+10h]
  float v217; // [rsp+E0h] [rbp+18h]
  float v218; // [rsp+E0h] [rbp+18h]
  float v219; // [rsp+E0h] [rbp+18h]
  float v220; // [rsp+E0h] [rbp+18h]
  float v221; // [rsp+E0h] [rbp+18h]
  float v222; // [rsp+E0h] [rbp+18h]
  float v223; // [rsp+E0h] [rbp+18h]
  float v224; // [rsp+E0h] [rbp+18h]
  float v225; // [rsp+E0h] [rbp+18h]
  float v226; // [rsp+E8h] [rbp+20h]
  float v227; // [rsp+E8h] [rbp+20h]
  float v228; // [rsp+E8h] [rbp+20h]
  float v229; // [rsp+E8h] [rbp+20h]
  float v230; // [rsp+E8h] [rbp+20h]
  float v231; // [rsp+E8h] [rbp+20h]

  v3 = a3 != 0 ? 8 : 0;
  v4 = a2[14] + a2[17];
  v5 = *((int *)this + 38506);
  v6 = v5 ^ 1;
  v7 = a2[18] + a2[13];
  v8 = a2[12] + a2[19];
  v9 = a2[10] + a2[21];
  v10 = a2[11] + a2[20];
  v11 = a2[8] + a2[23];
  v12 = a2[22] + a2[9];
  v13 = a2[6] + a2[25];
  v14 = a2[7] + a2[24];
  v15 = *(_QWORD *)((char *)this + v3 + 154008);
  v16 = *((int *)this + 38507);
  v203 = *a2 + a2[31];
  v217 = a2[30] + a2[1];
  v17 = a2[15] + a2[16];
  v168 = a2[2] + a2[29];
  v173 = a2[3] + a2[28];
  v198 = a2[4] + a2[27];
  v18 = v16 + (v5 << 9);
  v192 = a2[26] + a2[5];
  v19 = v16 + (v6 << 9);
  v20 = v8 + v173;
  v21 = v10 + v198;
  v226 = v17 + v203;
  v22 = v12 + v13;
  v177 = v7 + v168;
  v210 = v4 + v217;
  v23 = v9 + v192;
  v24 = v11 + v14;
  v25 = (float)(v203 - v17) * *((float *)this + 33808);
  v26 = (float)(v14 - v11) * *((float *)this + 33815);
  v27 = (float)(v13 - v12) * *((float *)this + 33814);
  v218 = (float)(v217 - v4) * *((float *)this + 33809);
  v169 = (float)(v168 - v7) * *((float *)this + 33810);
  v28 = v173 - v8;
  v29 = *((float *)this + 33816);
  v174 = v28 * *((float *)this + 33811);
  v30 = v198 - v10;
  v31 = (float)(v10 + v198) + v20;
  v32 = v20 - v21;
  v33 = v26 + v25;
  v34 = v25 - v26;
  v199 = v30 * *((float *)this + 33812);
  v35 = v192 - v9;
  v36 = (float)(v9 + v192) + v177;
  v37 = v177 - v23;
  v204 = v34 * v29;
  v193 = v35 * *((float *)this + 33813);
  v187 = v24 + v226;
  v38 = v22 + v210;
  v39 = v210 - v22;
  v178 = v27 + v218;
  v227 = (float)(v226 - v24) * v29;
  v40 = *((float *)this + 33819);
  v41 = v193 + v169;
  v42 = v199 + v174;
  v183 = v38;
  v43 = *((float *)this + 33817);
  v219 = (float)(v218 - v27) * v43;
  v211 = v39 * v43;
  v44 = *((float *)this + 33818);
  v45 = v32 * v40;
  v46 = v37 * v44;
  v47 = (float)(v174 - v199) * v40;
  v48 = v31 + v187;
  v49 = (float)(v169 - v193) * v44;
  v50 = *((float *)this + 33820);
  v51 = v187 - v31;
  v52 = *((float *)this + 33821);
  v53 = v45 + v227;
  v54 = v36 + v183;
  v175 = v48;
  v55 = v183 - v36;
  v56 = v227 - v45;
  v188 = v51 * v50;
  v57 = v48 - (float)(v36 + v183);
  v58 = v46 + v211;
  v59 = v211 - v46;
  v194 = v54;
  v60 = v42 + v33;
  v184 = v55 * v52;
  v228 = v56 * v50;
  v61 = v56 * v50;
  v212 = v59 * v52;
  v62 = v41 + v178;
  v63 = (float)(v33 - v42) * v50;
  v64 = v47 + v204;
  v65 = v204 - v47;
  v66 = *((float *)this + 33822);
  v67 = v57 * v66;
  v179 = (float)(v178 - v41) * v52;
  v68 = v49 + v219;
  v205 = v65 * v50;
  v69 = v65 * v50;
  v70 = (float)(v63 - v179) * v66;
  v71 = (float)(v219 - v49) * v52;
  v72 = (float)(v49 + v219) + v64;
  v73 = (float)(v188 - v184) * v66;
  v220 = v71;
  v74 = (float)(v64 - v68) * v66;
  v75 = (float)(v61 - v212) * v66;
  v76 = (float)(v69 - v71) * v66;
  v77 = (float)(v53 - v58) * v66;
  v78 = COERCE_UNSIGNED_INT((float)((float)(v212 + v228) + v75) + v77) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 256) = v78;
  *(_DWORD *)(v15 + 4 * v19 + 1792) = v78;
  v79 = COERCE_UNSIGNED_INT((float)(v58 + v53) + (float)((float)(v212 + v228) + v75)) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 768) = v79;
  v80 = (float)(v220 + v205) + v76;
  *(_DWORD *)(v15 + 4 * v19 + 1280) = v79;
  *(float *)(v15 + 4 * v18 + 640) = v76 + v70;
  *(_DWORD *)(v15 + 4 * v18 + 1408) = COERCE_UNSIGNED_INT(v76 + v70) ^ _xmm;
  v81 = (float)(v76 + v70) + v74;
  v82 = v62 + v60;
  *(float *)(v15 + 4 * v18 + 384) = v81;
  *(_DWORD *)(v15 + 4 * v18 + 1664) = LODWORD(v81) ^ _xmm;
  v83 = (float)((float)(v60 - v62) * v66) + v74;
  v84 = COERCE_UNSIGNED_INT((float)(v82 + v72) + v80) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 896) = v84;
  v85 = (float)((float)(v179 + v63) + v70) + v80;
  *(_DWORD *)(v15 + 4 * v19 + 1152) = v84;
  v86 = v83 + v80;
  v87 = v83 + v76;
  v88 = LODWORD(v86) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 128) = v88;
  *(_DWORD *)(v15 + 4 * v19 + 1920) = v88;
  v89 = COERCE_UNSIGNED_INT(v85 + v74) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 384) = v89;
  v90 = COERCE_UNSIGNED_INT(v85 + v72) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 1664) = v89;
  *(_DWORD *)(v15 + 4 * v19 + 640) = v90;
  *(_DWORD *)(v15 + 4 * v19 + 1408) = v90;
  *(float *)(v15 + 4 * v18 + 128) = v87;
  *(_DWORD *)(v15 + 4 * v18 + 1920) = LODWORD(v87) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 256) = v75 + v77;
  *(_DWORD *)(v15 + 4 * v18 + 1792) = COERCE_UNSIGNED_INT(v75 + v77) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 1024) = COERCE_UNSIGNED_INT(v194 + v175) ^ _xmm;
  *(float *)(v15 + 4 * v18) = v67;
  *(_DWORD *)(v15 + 4 * v19) = LODWORD(v67) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v18 + 1536) = LODWORD(v73) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 768) = v75;
  *(float *)(v15 + 4 * v18 + 896) = v76;
  *(float *)(v15 + 4 * v18 + 512) = v73;
  *(_DWORD *)(v15 + 4 * v18 + 1280) = LODWORD(v75) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v18 + 1152) = LODWORD(v76) ^ _xmm;
  v91 = COERCE_UNSIGNED_INT((float)(v184 + v188) + v73) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 512) = v91;
  *(_DWORD *)(v15 + 4 * v19 + 1536) = v91;
  v92 = (float)(a2[14] - a2[17]) * *((float *)this + 33806);
  v93 = (float)(a2[13] - a2[18]) * *((float *)this + 33805);
  v94 = (float)(a2[12] - a2[19]) * *((float *)this + 33804);
  v95 = (float)(a2[10] - a2[21]) * *((float *)this + 33802);
  v96 = (float)(a2[11] - a2[20]) * *((float *)this + 33803);
  v97 = (float)(a2[8] - a2[23]) * *((float *)this + 33800);
  v98 = (float)(a2[9] - a2[22]) * *((float *)this + 33801);
  v99 = (float)(a2[6] - a2[25]) * *((float *)this + 33798);
  v100 = (float)(a2[7] - a2[24]) * *((float *)this + 33799);
  v221 = (float)(*a2 - a2[31]) * *((float *)this + 33792);
  v213 = (float)(a2[1] - a2[30]) * *((float *)this + 33793);
  v229 = (float)(a2[2] - a2[29]) * *((float *)this + 33794);
  v170 = (float)(a2[3] - a2[28]) * *((float *)this + 33795);
  v189 = (float)(a2[4] - a2[27]) * *((float *)this + 33796);
  v101 = (float)(a2[15] - a2[16]) * *((float *)this + 33807);
  v200 = (float)(a2[5] - a2[26]) * *((float *)this + 33797);
  v206 = v101 + v221;
  v102 = v94 + v170;
  v103 = v96 + v189;
  v104 = v98 + v99;
  v195 = v92 + v213;
  v180 = v93 + v229;
  v105 = v95 + v200;
  v106 = v97 + v100;
  v222 = (float)(v221 - v101) * *((float *)this + 33808);
  v214 = (float)(v213 - v92) * *((float *)this + 33809);
  v107 = (float)(v229 - v93) * *((float *)this + 33810);
  v108 = *((float *)this + 33817);
  v230 = v107;
  v109 = (float)(v100 - v97) * *((float *)this + 33815);
  v110 = v170 - v94;
  v111 = *((float *)this + 33816);
  v112 = (float)(v99 - v98) * *((float *)this + 33814);
  v113 = v109 + v222;
  v171 = v110 * *((float *)this + 33811);
  v114 = v189 - v96;
  v115 = (float)(v96 + v189) + v102;
  v116 = v102 - v103;
  v190 = v114 * *((float *)this + 33812);
  v117 = v200 - v95;
  v223 = (float)(v222 - v109) * v111;
  v118 = (float)(v95 + v200) + v180;
  v119 = v180 - v105;
  v120 = v105 + v180;
  v201 = v117 * *((float *)this + 33813);
  v185 = v106 + v206;
  v121 = (float)(v206 - v106) * v111;
  v122 = v104 + v195;
  v123 = v195 - v104;
  v181 = v112 + v214;
  v124 = v201 + v230;
  v125 = v190 + v171;
  v196 = v123 * v108;
  v126 = *((float *)this + 33819);
  v215 = (float)(v214 - v112) * v108;
  v127 = v116 * v126;
  v207 = v121;
  v128 = *((float *)this + 33818);
  v129 = (float)(v230 - v201) * v128;
  v130 = v119 * v128;
  v131 = *((float *)this + 33821);
  v231 = v129;
  v132 = *((float *)this + 33820);
  v172 = (float)(v171 - v190) * v126;
  v176 = v115 + v185;
  v186 = (float)(v185 - v115) * v132;
  v191 = v120 + v122;
  v133 = v127 + v207;
  v134 = v124 + v181;
  v135 = v172 + v223;
  v202 = (float)(v122 - v118) * v131;
  v208 = (float)(v207 - v127) * v132;
  v136 = v130 + v196;
  v137 = v196 - v130;
  v138 = v125 + v113;
  v224 = (float)(v223 - v172) * v132;
  v139 = v137 * v131;
  v182 = (float)(v181 - v124) * v131;
  v140 = (float)(v113 - v125) * v132;
  v141 = *((float *)this + 33822);
  v197 = v140;
  v142 = (float)(v176 - v191) * v141;
  v143 = (float)(v231 + v215) + v135;
  v144 = (float)(v186 - v202) * v141;
  v145 = (float)(v215 - v231) * v131;
  v146 = v139 + v208;
  v147 = (float)(v133 - v136) * v141;
  v148 = v208 - v139;
  v149 = (float)(v140 - v182) * v141;
  v150 = v145 + v224;
  v216 = (float)(v135 - (float)(v231 + v215)) * v141;
  v209 = v148 * v141;
  v225 = (float)(v224 - v145) * v141;
  v151 = (float)((float)(v138 - v134) * v141) + (float)(v225 + v216);
  v152 = (float)((float)((float)(v148 * v141) + v147) + v149) + (float)(v225 + v216);
  *(float *)(v15 + 4 * v18 + 320) = v152;
  *(_DWORD *)(v15 + 4 * v18 + 1728) = LODWORD(v152) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 64) = v151 + v142;
  *(_DWORD *)(v15 + 4 * v18 + 1984) = COERCE_UNSIGNED_INT(v151 + v142) ^ _xmm;
  v153 = (float)(v150 + v142) + v151;
  v154 = v151 + (float)(v209 + v147);
  v155 = LODWORD(v153) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 64) = v155;
  *(_DWORD *)(v15 + 4 * v19 + 1984) = v155;
  *(_DWORD *)(v15 + 4 * v18 + 1856) = LODWORD(v154) ^ _xmm;
  v156 = (float)(v146 + v209) + (float)(v136 + v133);
  *(float *)(v15 + 4 * v18 + 192) = v154;
  v157 = COERCE_UNSIGNED_INT((float)(v150 + v146) + v154) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 192) = v157;
  *(_DWORD *)(v15 + 4 * v19 + 1856) = v157;
  v158 = (float)((float)(v182 + v197) + (float)(v143 + v149)) + (float)((float)(v150 + v225) + v216);
  v159 = (float)(v158 + v144) + (float)(v202 + v186);
  *(float *)(v15 + 4 * v19 + 448) = v143 - v159;
  *(float *)(v15 + 4 * v19 + 1600) = v143 - v159;
  v160 = v216 - (float)(v156 + v158);
  v161 = (float)(v146 + v147) + (float)(v158 + v209);
  *(float *)(v15 + 4 * v19 + 704) = v160;
  *(float *)(v15 + 4 * v19 + 1344) = v160;
  *(float *)(v15 + 4 * v19 + 320) = v143 - v161;
  *(float *)(v15 + 4 * v19 + 1728) = v143 - v161;
  v162 = (float)((float)(v134 + v138) + v143) + (float)(v150 + v225);
  *(float *)(v15 + 4 * v19 + 576) = v216 - v159;
  *(float *)(v15 + 4 * v19 + 1472) = v216 - v159;
  v163 = COERCE_UNSIGNED_INT((float)(v191 + v176) + v162) ^ _xmm;
  v164 = COERCE_UNSIGNED_INT(v162 + v156) ^ _xmm;
  *(_DWORD *)(v15 + 4 * v19 + 960) = v163;
  *(_DWORD *)(v15 + 4 * v19 + 1088) = v163;
  *(_DWORD *)(v15 + 4 * v19 + 832) = v164;
  *(_DWORD *)(v15 + 4 * v19 + 1216) = v164;
  v165 = (float)(v225 + v149) + v209;
  v166 = (float)(v225 + v149) + v144;
  *(float *)(v15 + 4 * v18 + 704) = v165;
  *(_DWORD *)(v15 + 4 * v18 + 1344) = LODWORD(v165) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 576) = v166;
  *(_DWORD *)(v15 + 4 * v18 + 1472) = LODWORD(v166) ^ _xmm;
  v167 = v166 + v216;
  *(float *)(v15 + 4 * v18 + 960) = v225;
  *(_DWORD *)(v15 + 4 * v18 + 1088) = LODWORD(v225) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 448) = v167;
  *(_DWORD *)(v15 + 4 * v18 + 1600) = LODWORD(v167) ^ _xmm;
  *(float *)(v15 + 4 * v18 + 832) = v225 + v209;
  *(_DWORD *)(v15 + 4 * v18 + 1216) = COERCE_UNSIGNED_INT(v225 + v209) ^ _xmm;
}

```

## disassembly

```asm
0x1800451b8  mov     r11, rsp
0x1800451bb  sub     rsp, 0C8h
0x1800451c2  movss   xmm0, dword ptr [rdx+78h]
0x1800451c7  neg     r8d
0x1800451ca  addss   xmm0, dword ptr [rdx+4]
0x1800451cf  movss   xmm1, dword ptr [rdx+38h]
0x1800451d4  sbb     rax, rax
0x1800451d7  movss   xmm2, dword ptr [rdx+48h]
0x1800451dc  and     eax, 8
0x1800451df  movss   xmm3, dword ptr [rdx+30h]
0x1800451e4  movss   xmm5, dword ptr [rdx+2Ch]
0x1800451e9  movss   xmm4, dword ptr [rdx+68h]
0x1800451ee  addss   xmm4, dword ptr [rdx+14h]
0x1800451f3  movsxd  r8, dword ptr [rcx+259A8h]
0x1800451fa  addss   xmm1, dword ptr [rdx+44h]
0x1800451ff  movaps  xmmword ptr [r11-18h], xmm6
0x180045204  movaps  xmmword ptr [r11-28h], xmm7
0x180045209  movaps  xmmword ptr [r11-38h], xmm8
0x18004520e  movaps  xmmword ptr [r11-48h], xmm9
0x180045213  movaps  xmmword ptr [r11-58h], xmm10
0x180045218  movaps  xmmword ptr [r11-68h], xmm11
0x18004521d  movaps  xmmword ptr [r11-78h], xmm12
0x180045222  movaps  [rsp+0C8h+var_88], xmm13
0x180045228  movaps  [rsp+0C8h+var_98], xmm14
0x18004522e  movaps  [rsp+0C8h+var_A8], xmm15
0x180045234  mov     r9, r8
0x180045237  movss   xmm6, dword ptr [rdx+10h]
0x18004523c  xor     r8, 1
0x180045240  addss   xmm6, dword ptr [rdx+6Ch]
0x180045245  movss   xmm14, dword ptr [rdx]
0x18004524a  addss   xmm14, dword ptr [rdx+7Ch]
0x180045250  movss   xmm12, dword ptr [rdx+8]
0x180045256  addss   xmm12, dword ptr [rdx+74h]
0x18004525c  movss   xmm10, dword ptr [rdx+0Ch]
0x180045262  addss   xmm10, dword ptr [rdx+70h]
0x180045268  movss   xmm7, dword ptr [rdx+28h]
0x18004526d  movss   xmm11, dword ptr [rdx+20h]
0x180045273  movss   xmm9, dword ptr [rdx+58h]
0x180045279  addss   xmm2, dword ptr [rdx+34h]
0x18004527e  addss   xmm3, dword ptr [rdx+4Ch]
0x180045283  addss   xmm7, dword ptr [rdx+54h]
0x180045288  addss   xmm5, dword ptr [rdx+50h]
0x18004528d  movss   xmm15, dword ptr [rdx+18h]
0x180045293  movss   xmm13, dword ptr [rdx+1Ch]
0x180045299  addss   xmm11, dword ptr [rdx+5Ch]
0x18004529f  addss   xmm9, dword ptr [rdx+24h]
0x1800452a5  addss   xmm15, dword ptr [rdx+64h]
0x1800452ab  addss   xmm13, dword ptr [rdx+60h]
0x1800452b1  mov     r10, [rax+rcx+25998h]
0x1800452b9  movsxd  rax, dword ptr [rcx+259ACh]
0x1800452c0  movss   [rsp+0C8h+arg_0], xmm14
0x1800452ca  movss   [rsp+0C8h+arg_10], xmm0
0x1800452d3  movss   xmm0, dword ptr [rdx+3Ch]
0x1800452d8  addss   xmm0, dword ptr [rdx+40h]
0x1800452dd  movss   [rsp+0C8h+var_C8], xmm12
0x1800452e3  movss   [rsp+0C8h+var_C4], xmm10
0x1800452ea  shl     r9, 9
0x1800452ee  movss   [rsp+0C8h+var_B0], xmm6
0x1800452f4  add     r9, rax
0x1800452f7  movaps  xmm8, xmm0
0x1800452fb  movss   [rsp+0C8h+var_B4], xmm4
0x180045301  addss   xmm8, xmm14
0x180045306  shl     r8, 9
0x18004530a  movaps  xmm14, xmm2
0x18004530e  add     r8, rax
0x180045311  addss   xmm14, xmm12
0x180045316  movaps  xmm12, xmm3
0x18004531a  addss   xmm12, xmm10
0x18004531f  movaps  xmm10, xmm5
0x180045323  addss   xmm10, xmm6
0x180045328  movaps  xmm6, xmm9
0x18004532c  movss   [rsp+0C8h+arg_18], xmm8
0x180045336  addss   xmm6, xmm15
0x18004533b  movaps  xmm8, xmm1
0x18004533f  addss   xmm8, [rsp+0C8h+arg_10]
0x180045349  movss   [rsp+0C8h+var_C0], xmm14
0x180045350  movss   xmm14, [rsp+0C8h+arg_0]
0x18004535a  subss   xmm14, xmm0
0x18004535f  movss   [rsp+0C8h+arg_8], xmm8
0x180045369  movaps  xmm8, xmm7
0x18004536d  addss   xmm8, xmm4
0x180045372  movaps  xmm4, xmm11
0x180045376  addss   xmm4, xmm13
0x18004537b  movss   xmm0, [rsp+0C8h+arg_10]
0x180045384  subss   xmm13, xmm11
0x180045389  mulss   xmm14, dword ptr [rcx+21040h]
0x180045392  subss   xmm0, xmm1
0x180045396  movaps  xmm1, xmm4
0x180045399  subss   xmm15, xmm9
0x18004539e  mulss   xmm13, dword ptr [rcx+2105Ch]
0x1800453a7  mulss   xmm0, dword ptr [rcx+21044h]
0x1800453af  mulss   xmm15, dword ptr [rcx+21058h]
0x1800453b8  movss   [rsp+0C8h+arg_10], xmm0
0x1800453c1  movss   xmm0, [rsp+0C8h+var_C8]
0x1800453c6  subss   xmm0, xmm2
0x1800453ca  movss   [rsp+0C8h+arg_0], xmm14
0x1800453d4  movss   xmm11, [rsp+0C8h+arg_0]
0x1800453de  movaps  xmm2, xmm6
0x1800453e1  movss   xmm14, [rsp+0C8h+var_C0]
0x1800453e8  mulss   xmm0, dword ptr [rcx+21048h]
0x1800453f0  movss   [rsp+0C8h+var_C8], xmm0
0x1800453f5  movss   xmm0, [rsp+0C8h+var_C4]
0x1800453fb  subss   xmm0, xmm3
0x1800453ff  movss   xmm3, dword ptr [rcx+21060h]
0x180045407  mulss   xmm0, dword ptr [rcx+2104Ch]
0x18004540f  movss   [rsp+0C8h+var_C4], xmm0
0x180045415  movss   xmm0, [rsp+0C8h+var_B0]
0x18004541b  subss   xmm0, xmm5
0x18004541f  movaps  xmm5, xmm10
0x180045423  addss   xmm5, xmm12
0x180045428  subss   xmm12, xmm10
0x18004542d  movaps  xmm10, xmm13
0x180045431  addss   xmm10, xmm11
0x180045436  subss   xmm11, xmm13
0x18004543b  movss   xmm13, [rsp+0C8h+var_C8]
0x180045441  mulss   xmm0, dword ptr [rcx+21050h]
0x180045449  movss   [rsp+0C8h+var_B0], xmm0
0x18004544f  movss   xmm0, [rsp+0C8h+var_B4]
0x180045455  movss   xmm9, [rsp+0C8h+var_B0]
0x18004545c  subss   xmm0, xmm7
0x180045460  mulss   xmm11, xmm3
0x180045465  movaps  xmm7, xmm8
0x180045469  addss   xmm7, xmm14
0x18004546e  subss   xmm14, xmm8
0x180045473  mulss   xmm0, dword ptr [rcx+21054h]
0x18004547b  movss   [rsp+0C8h+arg_0], xmm11
0x180045485  movss   [rsp+0C8h+var_B4], xmm0
0x18004548b  movss   xmm0, [rsp+0C8h+arg_18]
0x180045494  movss   xmm8, [rsp+0C8h+var_B4]
0x18004549b  addss   xmm1, xmm0
0x18004549f  subss   xmm0, xmm4
0x1800454a3  movaps  xmm4, xmm15
0x1800454a7  addss   xmm4, [rsp+0C8h+arg_10]
0x1800454b0  subss   xmm13, xmm8
0x1800454b5  movss   [rsp+0C8h+var_B8], xmm1
0x1800454bb  movss   xmm1, [rsp+0C8h+arg_8]
0x1800454c4  mulss   xmm0, xmm3
0x1800454c8  addss   xmm2, xmm1
0x1800454cc  movss   xmm3, [rsp+0C8h+arg_10]
0x1800454d5  subss   xmm1, xmm6
0x1800454d9  subss   xmm3, xmm15
0x1800454de  movss   [rsp+0C8h+var_C0], xmm4
0x1800454e4  movaps  xmm4, xmm9
0x1800454e8  movss   [rsp+0C8h+arg_18], xmm0
0x1800454f1  movss   xmm0, dword ptr [rcx+2106Ch]
0x1800454f9  movaps  xmm6, xmm8
0x1800454fd  addss   xmm6, [rsp+0C8h+var_C8]
0x180045502  addss   xmm4, [rsp+0C8h+var_C4]
0x180045508  movss   [rsp+0C8h+var_BC], xmm2
0x18004550e  movss   xmm2, dword ptr [rcx+21064h]
0x180045516  mulss   xmm3, xmm2
0x18004551a  mulss   xmm1, xmm2
0x18004551e  movss   [rsp+0C8h+arg_10], xmm3
0x180045527  movss   xmm3, [rsp+0C8h+var_C4]
0x18004552d  subss   xmm3, xmm9
0x180045532  movss   [rsp+0C8h+arg_8], xmm1
0x18004553b  movss   xmm1, dword ptr [rcx+21068h]
0x180045543  movaps  xmm9, xmm5
0x180045547  mulss   xmm12, xmm0
0x18004554c  mulss   xmm14, xmm1
0x180045551  mulss   xmm3, xmm0
0x180045555  movss   xmm0, [rsp+0C8h+var_B8]
0x18004555b  addss   xmm9, xmm0
0x180045560  mulss   xmm13, xmm1
0x180045565  movss   xmm2, dword ptr [rcx+21070h]
0x18004556d  subss   xmm0, xmm5
0x180045571  movss   xmm1, dword ptr [rcx+21074h]
0x180045579  movaps  xmm11, xmm7
0x18004557d  movss   xmm15, [rsp+0C8h+arg_18]
0x180045587  movaps  xmm5, xmm12
0x18004558b  movss   xmm8, [rsp+0C8h+var_BC]
0x180045592  addss   xmm5, xmm15
0x180045597  addss   xmm11, xmm8
0x18004559c  movss   [rsp+0C8h+var_C4], xmm9
0x1800455a3  mulss   xmm0, xmm2
0x1800455a7  subss   xmm8, xmm7
0x1800455ac  subss   xmm15, xmm12
0x1800455b1  movaps  xmm7, xmm14
0x1800455b5  movaps  xmm12, xmm9
0x1800455b9  movss   [rsp+0C8h+var_B8], xmm0
0x1800455bf  subss   xmm12, xmm11
0x1800455c4  movss   xmm0, [rsp+0C8h+arg_8]
0x1800455cd  addss   xmm7, xmm0
0x1800455d1  mulss   xmm8, xmm1
0x1800455d6  subss   xmm0, xmm14
0x1800455db  mulss   xmm15, xmm2
0x1800455e0  movaps  xmm14, xmm4
0x1800455e4  movss   [rsp+0C8h+var_B4], xmm11
0x1800455eb  addss   xmm14, xmm10
0x1800455f0  movss   [rsp+0C8h+var_BC], xmm8
0x1800455f7  subss   xmm10, xmm4
0x1800455fc  movss   [rsp+0C8h+arg_18], xmm15
0x180045606  movss   xmm4, [rsp+0C8h+arg_0]
0x18004560f  movaps  xmm8, xmm6
0x180045613  mulss   xmm0, xmm1
0x180045617  movaps  xmm11, xmm15
0x18004561b  mulss   xmm10, xmm2
0x180045620  movss   [rsp+0C8h+arg_8], xmm0
0x180045629  movss   xmm0, [rsp+0C8h+var_C0]
0x18004562f  addss   xmm8, xmm0
0x180045634  movss   [rsp+0C8h+var_B0], xmm10
0x18004563b  movss   xmm15, [rsp+0C8h+var_B0]
0x180045642  subss   xmm0, xmm6
0x180045646  movss   xmm6, [rsp+0C8h+arg_10]
0x18004564f  movaps  xmm10, xmm3
0x180045653  addss   xmm10, xmm4
0x180045658  subss   xmm4, xmm3
0x18004565c  movss   xmm3, dword ptr [rcx+21078h]
0x180045664  mulss   xmm12, xmm3
0x180045669  mulss   xmm0, xmm1
0x18004566d  mulss   xmm4, xmm2
0x180045671  movaps  xmm2, xmm15
0x180045675  movss   [rsp+0C8h+var_C0], xmm0
0x18004567b  movaps  xmm0, xmm13
0x18004567f  subss   xmm2, [rsp+0C8h+var_C0]
0x180045685  addss   xmm0, xmm6
0x180045689  movss   [rsp+0C8h+arg_0], xmm4
0x180045692  movss   xmm9, [rsp+0C8h+arg_0]
0x18004569c  subss   xmm6, xmm13
0x1800456a1  movss   xmm13, [rsp+0C8h+var_B8]
0x1800456a8  subss   xmm13, [rsp+0C8h+var_BC]
0x1800456af  mulss   xmm2, xmm3
0x1800456b3  mulss   xmm6, xmm1
0x1800456b7  movaps  xmm4, xmm0
0x1800456ba  movss   xmm1, [rsp+0C8h+arg_8]
0x1800456c3  addss   xmm4, xmm10
0x1800456c8  subss   xmm10, xmm0
0x1800456cd  mulss   xmm13, xmm3
0x1800456d2  movss   [rsp+0C8h+arg_10], xmm6
0x1800456db  subss   xmm11, xmm1
0x1800456e0  addss   xmm1, [rsp+0C8h+arg_18]
0x1800456e9  subss   xmm9, [rsp+0C8h+arg_10]
0x1800456f3  movaps  xmm6, xmm5
0x1800456f6  mulss   xmm10, xmm3
0x1800456fb  subss   xmm6, xmm7
0x1800456ff  mulss   xmm11, xmm3
0x180045704  mulss   xmm9, xmm3
0x180045709  addss   xmm7, xmm5
0x18004570d  addss   xmm1, xmm11
0x180045712  mulss   xmm6, xmm3
0x180045716  movaps  xmm0, xmm1
0x180045719  addss   xmm0, xmm6
0x18004571d  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180045724  movss   dword ptr [r10+r8*4+100h], xmm0
0x18004572e  movss   dword ptr [r10+r8*4+700h], xmm0
0x180045738  movss   xmm5, [rsp+0C8h+arg_10]
0x180045741  addss   xmm7, xmm1
0x180045745  addss   xmm5, [rsp+0C8h+arg_0]
0x18004574e  movaps  xmm1, xmm9
0x180045752  addss   xmm1, xmm2
0x180045756  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x18004575d  movss   dword ptr [r10+r8*4+300h], xmm7
0x180045767  addss   xmm5, xmm9
0x18004576c  movss   dword ptr [r10+r8*4+500h], xmm7
0x180045776  movss   xmm7, dword ptr cs:__xmm@80000000800000008000000080000000
0x18004577e  movaps  xmm0, xmm1
0x180045781  xorps   xmm0, xmm7
0x180045784  movss   dword ptr [r10+r9*4+280h], xmm1
0x18004578e  movss   dword ptr [r10+r9*4+580h], xmm0
0x180045798  addss   xmm1, xmm10
0x18004579d  movaps  xmm0, xmm8
0x1800457a1  addss   xmm0, xmm14
0x1800457a6  subss   xmm14, xmm8
0x1800457ab  movss   dword ptr [r10+r9*4+180h], xmm1
0x1800457b5  xorps   xmm1, xmm7
0x1800457b8  movss   dword ptr [r10+r9*4+680h], xmm1
0x1800457c2  movss   xmm1, [rsp+0C8h+var_C0]
0x1800457c8  addss   xmm0, xmm4
0x1800457cc  addss   xmm1, xmm15
0x1800457d1  mulss   xmm14, xmm3
0x1800457d6  addss   xmm0, xmm5
0x1800457da  addss   xmm1, xmm2
0x1800457de  addss   xmm14, xmm10
0x1800457e3  xorps   xmm0, xmm7
0x1800457e6  movss   dword ptr [r10+r8*4+380h], xmm0
0x1800457f0  addss   xmm1, xmm5
0x1800457f4  movss   dword ptr [r10+r8*4+480h], xmm0
0x1800457fe  movaps  xmm0, xmm14
0x180045802  addss   xmm0, xmm5
0x180045806  addss   xmm14, xmm9
0x18004580b  xorps   xmm0, xmm7
0x18004580e  movss   dword ptr [r10+r8*4+80h], xmm0
0x180045818  movss   dword ptr [r10+r8*4+780h], xmm0
0x180045822  movaps  xmm0, xmm1
0x180045825  addss   xmm0, xmm10
0x18004582a  addss   xmm1, xmm4
0x18004582e  xorps   xmm0, xmm7
0x180045831  movss   dword ptr [r10+r8*4+180h], xmm0
0x18004583b  xorps   xmm1, xmm7
0x18004583e  movss   dword ptr [r10+r8*4+680h], xmm0
0x180045848  movaps  xmm0, xmm11
0x18004584c  addss   xmm0, xmm6
0x180045850  movss   dword ptr [r10+r8*4+280h], xmm1
0x18004585a  movss   dword ptr [r10+r8*4+580h], xmm1
0x180045864  movss   dword ptr [r10+r9*4+80h], xmm14
0x18004586e  xorps   xmm14, xmm7
0x180045872  movss   dword ptr [r10+r9*4+780h], xmm14
0x18004587c  movss   dword ptr [r10+r9*4+100h], xmm0
0x180045886  xorps   xmm0, xmm7
0x180045889  movss   dword ptr [r10+r9*4+700h], xmm0
  ... truncated ...
```
