# Mpegtoraw::computebuffer(float *,int)

- ea: `0x18002c920`
- end: `0x18002d8fe`
- name: `?computebuffer@Mpegtoraw@@AEAAXPEAMH@Z`
- size: `4062`
- prototype: `void __fastcall(Mpegtoraw *__hidden this, float *, int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ea70`
- `0x180031960`

## pseudocode

```c
void __fastcall Mpegtoraw::computebuffer(Mpegtoraw *this, float *a2, int a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  float v5; // xmm1_4
  float v6; // xmm2_4
  float v7; // xmm3_4
  float v8; // xmm7_4
  float v9; // xmm5_4
  float v10; // xmm11_4
  float v11; // xmm9_4
  float v12; // xmm15_4
  float v13; // xmm13_4
  __int64 v14; // r10
  __int64 v15; // rax
  float v16; // xmm0_4
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  float v20; // xmm12_4
  float v21; // xmm10_4
  float v22; // xmm6_4
  float v23; // xmm8_4
  float v24; // xmm4_4
  float v25; // xmm14_4
  float v26; // xmm0_4
  float v27; // xmm1_4
  float v28; // xmm14_4
  float v29; // xmm13_4
  float v30; // xmm15_4
  float v31; // xmm0_4
  float v32; // xmm3_4
  float v33; // xmm0_4
  float v34; // xmm5_4
  float v35; // xmm12_4
  float v36; // xmm10_4
  float v37; // xmm11_4
  float v38; // xmm0_4
  float v39; // xmm7_4
  float v40; // xmm14_4
  float v41; // xmm2_4
  float v42; // xmm1_4
  float v43; // xmm0_4
  float v44; // xmm6_4
  float v45; // xmm4_4
  float v46; // xmm2_4
  float v47; // xmm1_4
  float v48; // xmm12_4
  float v49; // xmm14_4
  float v50; // xmm3_4
  float v51; // xmm13_4
  float v52; // xmm2_4
  float v53; // xmm9_4
  float v54; // xmm1_4
  float v55; // xmm0_4
  float v56; // xmm5_4
  float v57; // xmm15_4
  float v58; // xmm11_4
  float v59; // xmm8_4
  float v60; // xmm12_4
  float v61; // xmm7_4
  float v62; // xmm0_4
  float v63; // xmm14_4
  float v64; // xmm11_4
  float v65; // xmm8_4
  float v66; // xmm15_4
  float v67; // xmm10_4
  float v68; // xmm4_4
  float v69; // xmm3_4
  float v70; // xmm12_4
  float v71; // xmm0_4
  float v72; // xmm9_4
  float v73; // xmm2_4
  float v74; // xmm6_4
  float v75; // xmm4_4
  float v76; // xmm13_4
  float v77; // xmm10_4
  float v78; // xmm11_4
  float v79; // xmm9_4
  float v80; // xmm6_4
  int v81; // xmm0_4
  float v82; // xmm7_4
  float v83; // xmm5_4
  int v84; // xmm7_4
  float v85; // xmm1_4
  float v86; // xmm0_4
  float v87; // xmm14_4
  int v88; // xmm0_4
  float v89; // xmm1_4
  float v90; // xmm0_4
  float v91; // xmm14_4
  int v92; // xmm0_4
  int v93; // xmm0_4
  int v94; // xmm1_4
  int v95; // xmm0_4
  float v96; // xmm1_4
  float v97; // xmm2_4
  float v98; // xmm3_4
  float v99; // xmm8_4
  float v100; // xmm6_4
  float v101; // xmm11_4
  float v102; // xmm10_4
  float v103; // xmm15_4
  float v104; // xmm14_4
  float v105; // xmm0_4
  float v106; // xmm12_4
  float v107; // xmm9_4
  float v108; // xmm5_4
  float v109; // xmm7_4
  float v110; // xmm4_4
  float v111; // xmm0_4
  float v112; // xmm2_4
  float v113; // xmm14_4
  float v114; // xmm15_4
  float v115; // xmm10_4
  float v116; // xmm0_4
  float v117; // xmm3_4
  float v118; // xmm0_4
  float v119; // xmm6_4
  float v120; // xmm12_4
  float v121; // xmm0_4
  float v122; // xmm8_4
  float v123; // xmm13_4
  float v124; // xmm9_4
  float v125; // xmm1_4
  float v126; // xmm11_4
  float v127; // xmm0_4
  float v128; // xmm5_4
  float v129; // xmm4_4
  float v130; // xmm0_4
  float v131; // xmm12_4
  float v132; // xmm1_4
  float v133; // xmm2_4
  float v134; // xmm13_4
  float v135; // xmm1_4
  float v136; // xmm14_4
  float v137; // xmm15_4
  float v138; // xmm3_4
  float v139; // xmm11_4
  float v140; // xmm6_4
  float v141; // xmm13_4
  float v142; // xmm6_4
  float v143; // xmm10_4
  float v144; // xmm4_4
  float v145; // xmm5_4
  float v146; // xmm8_4
  float v147; // xmm12_4
  float v148; // xmm2_4
  float v149; // xmm9_4
  float v150; // xmm7_4
  float v151; // xmm1_4
  float v152; // xmm10_4
  float v153; // xmm6_4
  float v154; // xmm2_4
  float v155; // xmm0_4
  float v156; // xmm1_4
  float v157; // xmm2_4
  int v158; // xmm1_4
  float v159; // xmm3_4
  int v160; // xmm1_4
  float v161; // xmm5_4
  float v162; // xmm2_4
  float v163; // xmm1_4
  float v164; // xmm9_4
  float v165; // xmm15_4
  int v166; // xmm0_4
  int v167; // xmm15_4
  float v168; // xmm0_4
  float v169; // xmm1_4
  float v170; // xmm1_4
  float v171; // [rsp+0h] [rbp-C8h]
  float v172; // [rsp+0h] [rbp-C8h]
  float v173; // [rsp+0h] [rbp-C8h]
  float v174; // [rsp+0h] [rbp-C8h]
  float v175; // [rsp+0h] [rbp-C8h]
  float v176; // [rsp+4h] [rbp-C4h]
  float v177; // [rsp+4h] [rbp-C4h]
  float v178; // [rsp+4h] [rbp-C4h]
  float v179; // [rsp+4h] [rbp-C4h]
  float v180; // [rsp+8h] [rbp-C0h]
  float v181; // [rsp+8h] [rbp-C0h]
  float v182; // [rsp+8h] [rbp-C0h]
  float v183; // [rsp+8h] [rbp-C0h]
  float v184; // [rsp+8h] [rbp-C0h]
  float v185; // [rsp+8h] [rbp-C0h]
  float v186; // [rsp+Ch] [rbp-BCh]
  float v187; // [rsp+Ch] [rbp-BCh]
  float v188; // [rsp+Ch] [rbp-BCh]
  float v189; // [rsp+Ch] [rbp-BCh]
  float v190; // [rsp+10h] [rbp-B8h]
  float v191; // [rsp+10h] [rbp-B8h]
  float v192; // [rsp+10h] [rbp-B8h]
  float v193; // [rsp+10h] [rbp-B8h]
  float v194; // [rsp+10h] [rbp-B8h]
  float v195; // [rsp+14h] [rbp-B4h]
  float v196; // [rsp+14h] [rbp-B4h]
  float v197; // [rsp+14h] [rbp-B4h]
  float v198; // [rsp+14h] [rbp-B4h]
  float v199; // [rsp+14h] [rbp-B4h]
  float v200; // [rsp+14h] [rbp-B4h]
  float v201; // [rsp+18h] [rbp-B0h]
  float v202; // [rsp+18h] [rbp-B0h]
  float v203; // [rsp+18h] [rbp-B0h]
  float v204; // [rsp+18h] [rbp-B0h]
  float v205; // [rsp+18h] [rbp-B0h]
  float v206; // [rsp+D0h] [rbp+8h]
  float v207; // [rsp+D0h] [rbp+8h]
  float v208; // [rsp+D0h] [rbp+8h]
  float v209; // [rsp+D0h] [rbp+8h]
  float v210; // [rsp+D0h] [rbp+8h]
  float v211; // [rsp+D0h] [rbp+8h]
  float v212; // [rsp+D0h] [rbp+8h]
  float v213; // [rsp+D8h] [rbp+10h]
  float v214; // [rsp+D8h] [rbp+10h]
  float v215; // [rsp+D8h] [rbp+10h]
  float v216; // [rsp+D8h] [rbp+10h]
  float v217; // [rsp+D8h] [rbp+10h]
  float v218; // [rsp+D8h] [rbp+10h]
  float v219; // [rsp+D8h] [rbp+10h]
  float v220; // [rsp+E0h] [rbp+18h]
  float v221; // [rsp+E0h] [rbp+18h]
  float v222; // [rsp+E0h] [rbp+18h]
  float v223; // [rsp+E0h] [rbp+18h]
  float v224; // [rsp+E0h] [rbp+18h]
  float v225; // [rsp+E0h] [rbp+18h]
  float v226; // [rsp+E0h] [rbp+18h]
  float v227; // [rsp+E0h] [rbp+18h]
  float v228; // [rsp+E0h] [rbp+18h]
  float v229; // [rsp+E8h] [rbp+20h]
  float v230; // [rsp+E8h] [rbp+20h]
  float v231; // [rsp+E8h] [rbp+20h]
  float v232; // [rsp+E8h] [rbp+20h]
  float v233; // [rsp+E8h] [rbp+20h]
  float v234; // [rsp+E8h] [rbp+20h]

  v3 = 154008;
  if ( a3 )
    v3 = 154016;
  v4 = *((int *)this + 38506);
  v5 = a2[14] + a2[17];
  v6 = a2[18] + a2[13];
  v7 = a2[12] + a2[19];
  v8 = a2[10] + a2[21];
  v9 = a2[11] + a2[20];
  v10 = a2[8] + a2[23];
  v11 = a2[22] + a2[9];
  v12 = a2[6] + a2[25];
  v13 = a2[7] + a2[24];
  v14 = *(_QWORD *)((char *)this + v3);
  v15 = *((int *)this + 38507);
  v220 = a2[30] + a2[1];
  v16 = a2[15] + a2[16];
  v206 = *a2 + a2[31];
  v171 = a2[2] + a2[29];
  v176 = a2[3] + a2[28];
  v201 = a2[4] + a2[27];
  v195 = a2[26] + a2[5];
  v17 = (v4 ^ 1) << 9;
  v18 = v15 + (v4 << 9);
  v19 = v15 + v17;
  v20 = v7 + v176;
  v229 = v16 + v206;
  v21 = v9 + v201;
  v180 = v6 + v171;
  v22 = v11 + v12;
  v213 = v5 + v220;
  v23 = v8 + v195;
  v24 = v10 + v13;
  v25 = v206 - v16;
  v26 = v220 - v5;
  v27 = v10 + v13;
  v28 = v25 * *((float *)this + 33808);
  v29 = (float)(v13 - v10) * *((float *)this + 33815);
  v30 = (float)(v12 - v11) * *((float *)this + 33814);
  v221 = v26 * *((float *)this + 33809);
  v172 = (float)(v171 - v6) * *((float *)this + 33810);
  v31 = v176 - v7;
  v32 = *((float *)this + 33816);
  v177 = v31 * *((float *)this + 33811);
  v33 = v201 - v9;
  v34 = (float)(v9 + v201) + v20;
  v35 = v20 - v21;
  v36 = v29 + v28;
  v37 = v28 - v29;
  v202 = v33 * *((float *)this + 33812);
  v38 = v195 - v8;
  v39 = (float)(v8 + v195) + v180;
  v40 = v180 - v23;
  v207 = v37 * v32;
  v196 = v38 * *((float *)this + 33813);
  v190 = v27 + v229;
  v41 = v22 + v213;
  v42 = v213 - v22;
  v181 = v30 + v221;
  v230 = (float)(v229 - v24) * v32;
  v43 = *((float *)this + 33819);
  v44 = v196 + v172;
  v45 = v202 + v177;
  v186 = v41;
  v46 = *((float *)this + 33817);
  v222 = (float)(v221 - v30) * v46;
  v214 = v42 * v46;
  v47 = *((float *)this + 33818);
  v48 = v35 * v43;
  v49 = v40 * v47;
  v50 = (float)(v177 - v202) * v43;
  v51 = (float)(v172 - v196) * v47;
  v52 = *((float *)this + 33820);
  v53 = v34 + v190;
  v54 = *((float *)this + 33821);
  v55 = v190 - v34;
  v56 = v48 + v230;
  v57 = v230 - v48;
  v58 = v39 + v186;
  v178 = v53;
  v59 = v186 - v39;
  v191 = v55 * v52;
  v60 = v53 - (float)(v39 + v186);
  v61 = v49 + v214;
  v62 = v214 - v49;
  v197 = v58;
  v231 = v57 * v52;
  v63 = v45 + v36;
  v187 = v59 * v54;
  v64 = v57 * v52;
  v215 = v62 * v54;
  v65 = v44 + v181;
  v66 = (float)(v36 - v45) * v52;
  v67 = v50 + v207;
  v68 = v207 - v50;
  v69 = *((float *)this + 33822);
  v70 = v60 * v69;
  v182 = (float)(v181 - v44) * v54;
  v71 = v51 + v222;
  v208 = v68 * v52;
  v72 = v68 * v52;
  v73 = (float)(v66 - v182) * v69;
  v74 = (float)(v222 - v51) * v54;
  v75 = (float)(v51 + v222) + v67;
  v76 = (float)(v191 - v187) * v69;
  v223 = v74;
  v77 = (float)(v67 - v71) * v69;
  v78 = (float)(v64 - v215) * v69;
  v79 = (float)(v72 - v74) * v69;
  v80 = (float)(v56 - v61) * v69;
  v81 = COERCE_UNSIGNED_INT((float)((float)(v215 + v231) + v78) + v80) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 256) = v81;
  *(_DWORD *)(v14 + 4 * v19 + 1792) = v81;
  v82 = (float)(v61 + v56) + (float)((float)(v215 + v231) + v78);
  v83 = (float)(v223 + v208) + v79;
  v84 = LODWORD(v82) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 768) = v84;
  *(_DWORD *)(v14 + 4 * v19 + 1280) = v84;
  *(float *)(v14 + 4 * v18 + 640) = v79 + v73;
  *(_DWORD *)(v14 + 4 * v18 + 1408) = COERCE_UNSIGNED_INT(v79 + v73) ^ _xmm;
  v85 = (float)(v79 + v73) + v77;
  v86 = v65 + v63;
  *(float *)(v14 + 4 * v18 + 384) = v85;
  *(_DWORD *)(v14 + 4 * v18 + 1664) = LODWORD(v85) ^ _xmm;
  v87 = (float)((float)(v63 - v65) * v69) + v77;
  v88 = COERCE_UNSIGNED_INT((float)(v86 + v75) + v83) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 896) = v88;
  v89 = (float)((float)(v182 + v66) + v73) + v83;
  *(_DWORD *)(v14 + 4 * v19 + 1152) = v88;
  v90 = v87 + v83;
  v91 = v87 + v79;
  v92 = LODWORD(v90) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 128) = v92;
  *(_DWORD *)(v14 + 4 * v19 + 1920) = v92;
  v93 = COERCE_UNSIGNED_INT(v89 + v77) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 384) = v93;
  v94 = COERCE_UNSIGNED_INT(v89 + v75) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 1664) = v93;
  *(_DWORD *)(v14 + 4 * v19 + 640) = v94;
  *(_DWORD *)(v14 + 4 * v19 + 1408) = v94;
  *(float *)(v14 + 4 * v18 + 128) = v91;
  *(_DWORD *)(v14 + 4 * v18 + 1920) = LODWORD(v91) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 256) = v78 + v80;
  *(_DWORD *)(v14 + 4 * v18 + 1792) = COERCE_UNSIGNED_INT(v78 + v80) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 1024) = COERCE_UNSIGNED_INT(v197 + v178) ^ _xmm;
  *(float *)(v14 + 4 * v18) = v70;
  *(_DWORD *)(v14 + 4 * v19) = LODWORD(v70) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v18 + 1536) = LODWORD(v76) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 768) = v78;
  *(float *)(v14 + 4 * v18 + 896) = v79;
  *(float *)(v14 + 4 * v18 + 512) = v76;
  *(_DWORD *)(v14 + 4 * v18 + 1280) = LODWORD(v78) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v18 + 1152) = LODWORD(v79) ^ _xmm;
  v95 = COERCE_UNSIGNED_INT((float)(v187 + v191) + v76) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 512) = v95;
  *(_DWORD *)(v14 + 4 * v19 + 1536) = v95;
  v96 = (float)(a2[14] - a2[17]) * *((float *)this + 33806);
  v97 = (float)(a2[13] - a2[18]) * *((float *)this + 33805);
  v98 = (float)(a2[12] - a2[19]) * *((float *)this + 33804);
  v99 = (float)(a2[10] - a2[21]) * *((float *)this + 33802);
  v100 = (float)(a2[11] - a2[20]) * *((float *)this + 33803);
  v101 = (float)(a2[8] - a2[23]) * *((float *)this + 33800);
  v102 = (float)(a2[9] - a2[22]) * *((float *)this + 33801);
  v103 = (float)(a2[6] - a2[25]) * *((float *)this + 33798);
  v104 = (float)(a2[7] - a2[24]) * *((float *)this + 33799);
  v224 = (float)(*a2 - a2[31]) * *((float *)this + 33792);
  v216 = (float)(a2[1] - a2[30]) * *((float *)this + 33793);
  v232 = (float)(a2[2] - a2[29]) * *((float *)this + 33794);
  v173 = (float)(a2[3] - a2[28]) * *((float *)this + 33795);
  v192 = (float)(a2[4] - a2[27]) * *((float *)this + 33796);
  v105 = (float)(a2[15] - a2[16]) * *((float *)this + 33807);
  v203 = (float)(a2[5] - a2[26]) * *((float *)this + 33797);
  v209 = v105 + v224;
  v106 = v98 + v173;
  v107 = v100 + v192;
  v108 = v102 + v103;
  v198 = v96 + v216;
  v183 = v97 + v232;
  v109 = v99 + v203;
  v110 = v101 + v104;
  v225 = (float)(v224 - v105) * *((float *)this + 33808);
  v217 = (float)(v216 - v96) * *((float *)this + 33809);
  v111 = (float)(v232 - v97) * *((float *)this + 33810);
  v112 = *((float *)this + 33817);
  v113 = (float)(v104 - v101) * *((float *)this + 33815);
  v114 = (float)(v103 - v102) * *((float *)this + 33814);
  v233 = v111;
  v115 = v113 + v225;
  v116 = v173 - v98;
  v117 = *((float *)this + 33816);
  v174 = v116 * *((float *)this + 33811);
  v118 = v192 - v100;
  v119 = (float)(v100 + v192) + v106;
  v120 = v106 - v107;
  v193 = v118 * *((float *)this + 33812);
  v121 = v203 - v99;
  v226 = (float)(v225 - v113) * v117;
  v122 = (float)(v99 + v203) + v183;
  v123 = v183 - v109;
  v124 = v109 + v183;
  v204 = v121 * *((float *)this + 33813);
  v188 = v110 + v209;
  v125 = (float)(v209 - v110) * v117;
  v126 = v108 + v198;
  v127 = v198 - v108;
  v184 = v114 + v217;
  v128 = v204 + v233;
  v129 = v193 + v174;
  v199 = v127 * v112;
  v130 = *((float *)this + 33819);
  v218 = (float)(v217 - v114) * v112;
  v131 = v120 * v130;
  v210 = v125;
  v132 = *((float *)this + 33818);
  v175 = (float)(v174 - v193) * v130;
  v194 = v124 + v126;
  v234 = (float)(v233 - v204) * v132;
  v133 = *((float *)this + 33820);
  v179 = v119 + v188;
  v134 = v123 * v132;
  v189 = (float)(v188 - v119) * v133;
  v135 = *((float *)this + 33821);
  v136 = v131 + v210;
  v137 = v128 + v184;
  v138 = v175 + v226;
  v205 = (float)(v126 - v122) * v135;
  v211 = (float)(v210 - v131) * v133;
  v139 = v134 + v199;
  v140 = v199 - v134;
  v141 = v129 + v115;
  v227 = (float)(v226 - v175) * v133;
  v142 = v140 * v135;
  v185 = (float)(v184 - v128) * v135;
  v143 = (float)(v115 - v129) * v133;
  v144 = *((float *)this + 33822);
  v200 = v143;
  v145 = (float)(v179 - v194) * v144;
  v146 = (float)(v234 + v218) + v138;
  v147 = (float)(v189 - v205) * v144;
  v148 = (float)(v218 - v234) * v135;
  v149 = v142 + v211;
  v150 = (float)(v136 - v139) * v144;
  v151 = v211 - v142;
  v152 = (float)(v143 - v185) * v144;
  v153 = v148 + v227;
  v219 = (float)(v138 - (float)(v234 + v218)) * v144;
  v212 = v151 * v144;
  v228 = (float)(v227 - v148) * v144;
  v154 = (float)((float)(v141 - v137) * v144) + (float)(v228 + v219);
  v155 = (float)((float)((float)(v151 * v144) + v150) + v152) + (float)(v228 + v219);
  *(float *)(v14 + 4 * v18 + 320) = v155;
  *(_DWORD *)(v14 + 4 * v18 + 1728) = LODWORD(v155) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 64) = v154 + v145;
  *(_DWORD *)(v14 + 4 * v18 + 1984) = COERCE_UNSIGNED_INT(v154 + v145) ^ _xmm;
  v156 = (float)(v153 + v145) + v154;
  v157 = v154 + (float)(v212 + v150);
  v158 = LODWORD(v156) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 64) = v158;
  *(_DWORD *)(v14 + 4 * v19 + 1984) = v158;
  *(_DWORD *)(v14 + 4 * v18 + 1856) = LODWORD(v157) ^ _xmm;
  v159 = (float)(v149 + v212) + (float)(v139 + v136);
  *(float *)(v14 + 4 * v18 + 192) = v157;
  v160 = COERCE_UNSIGNED_INT((float)(v153 + v149) + v157) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 192) = v160;
  *(_DWORD *)(v14 + 4 * v19 + 1856) = v160;
  v161 = (float)((float)(v185 + v200) + (float)(v146 + v152)) + (float)((float)(v153 + v228) + v219);
  v162 = (float)(v161 + v147) + (float)(v205 + v189);
  *(float *)(v14 + 4 * v19 + 448) = v146 - v162;
  *(float *)(v14 + 4 * v19 + 1600) = v146 - v162;
  v163 = v219 - (float)(v159 + v161);
  v164 = (float)(v149 + v150) + (float)(v161 + v212);
  *(float *)(v14 + 4 * v19 + 704) = v163;
  *(float *)(v14 + 4 * v19 + 1344) = v163;
  *(float *)(v14 + 4 * v19 + 320) = v146 - v164;
  *(float *)(v14 + 4 * v19 + 1728) = v146 - v164;
  v165 = (float)((float)(v137 + v141) + v146) + (float)(v153 + v228);
  *(float *)(v14 + 4 * v19 + 576) = v219 - v162;
  *(float *)(v14 + 4 * v19 + 1472) = v219 - v162;
  v166 = COERCE_UNSIGNED_INT((float)(v194 + v179) + v165) ^ _xmm;
  v167 = COERCE_UNSIGNED_INT(v165 + v159) ^ _xmm;
  *(_DWORD *)(v14 + 4 * v19 + 960) = v166;
  *(_DWORD *)(v14 + 4 * v19 + 832) = v167;
  *(_DWORD *)(v14 + 4 * v19 + 1216) = v167;
  *(_DWORD *)(v14 + 4 * v19 + 1088) = v166;
  v168 = (float)(v228 + v152) + v212;
  v169 = (float)(v228 + v152) + v147;
  *(float *)(v14 + 4 * v18 + 704) = v168;
  *(_DWORD *)(v14 + 4 * v18 + 1344) = LODWORD(v168) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 576) = v169;
  *(_DWORD *)(v14 + 4 * v18 + 1472) = LODWORD(v169) ^ _xmm;
  v170 = v169 + v219;
  *(float *)(v14 + 4 * v18 + 960) = v228;
  *(_DWORD *)(v14 + 4 * v18 + 1088) = LODWORD(v228) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 448) = v170;
  *(_DWORD *)(v14 + 4 * v18 + 1600) = LODWORD(v170) ^ _xmm;
  *(float *)(v14 + 4 * v18 + 832) = v228 + v212;
  *(_DWORD *)(v14 + 4 * v18 + 1216) = COERCE_UNSIGNED_INT(v228 + v212) ^ _xmm;
}

```

## disassembly

```asm
0x18002c920  mov     r11, rsp
0x18002c923  sub     rsp, 0C8h
0x18002c92a  movss   xmm0, dword ptr [rdx+78h]
0x18002c92f  test    r8d, r8d
0x18002c932  addss   xmm0, dword ptr [rdx+4]
0x18002c937  movss   xmm1, dword ptr [rdx+38h]
0x18002c93c  mov     r9d, 259A0h
0x18002c942  movss   xmm2, dword ptr [rdx+48h]
0x18002c947  mov     eax, 25998h
0x18002c94c  movss   xmm3, dword ptr [rdx+30h]
0x18002c951  cmovnz  eax, r9d
0x18002c955  movss   xmm5, dword ptr [rdx+2Ch]
0x18002c95a  movss   xmm4, dword ptr [rdx+68h]
0x18002c95f  addss   xmm4, dword ptr [rdx+14h]
0x18002c964  movsxd  r8, dword ptr [rcx+259A8h]
0x18002c96b  movaps  xmmword ptr [r11-18h], xmm6
0x18002c970  movaps  xmmword ptr [r11-28h], xmm7
0x18002c975  movaps  xmmword ptr [r11-38h], xmm8
0x18002c97a  movaps  xmmword ptr [r11-48h], xmm9
0x18002c97f  movaps  xmmword ptr [r11-58h], xmm10
0x18002c984  movaps  xmmword ptr [r11-68h], xmm11
0x18002c989  movaps  xmmword ptr [r11-78h], xmm12
0x18002c98e  movaps  [rsp+0C8h+var_88], xmm13
0x18002c994  movaps  [rsp+0C8h+var_98], xmm14
0x18002c99a  movaps  [rsp+0C8h+var_A8], xmm15
0x18002c9a0  mov     r9, r8
0x18002c9a3  movss   xmm6, dword ptr [rdx+10h]
0x18002c9a8  xor     r8, 1
0x18002c9ac  addss   xmm6, dword ptr [rdx+6Ch]
0x18002c9b1  movss   xmm14, dword ptr [rdx]
0x18002c9b6  addss   xmm14, dword ptr [rdx+7Ch]
0x18002c9bc  movss   xmm12, dword ptr [rdx+8]
0x18002c9c2  addss   xmm12, dword ptr [rdx+74h]
0x18002c9c8  movss   xmm10, dword ptr [rdx+0Ch]
0x18002c9ce  addss   xmm10, dword ptr [rdx+70h]
0x18002c9d4  movss   xmm7, dword ptr [rdx+28h]
0x18002c9d9  movss   xmm11, dword ptr [rdx+20h]
0x18002c9df  movss   xmm9, dword ptr [rdx+58h]
0x18002c9e5  addss   xmm1, dword ptr [rdx+44h]
0x18002c9ea  addss   xmm2, dword ptr [rdx+34h]
0x18002c9ef  addss   xmm3, dword ptr [rdx+4Ch]
0x18002c9f4  addss   xmm7, dword ptr [rdx+54h]
0x18002c9f9  addss   xmm5, dword ptr [rdx+50h]
0x18002c9fe  movss   xmm15, dword ptr [rdx+18h]
0x18002ca04  movss   xmm13, dword ptr [rdx+1Ch]
0x18002ca0a  addss   xmm11, dword ptr [rdx+5Ch]
0x18002ca10  addss   xmm9, dword ptr [rdx+24h]
0x18002ca16  addss   xmm15, dword ptr [rdx+64h]
0x18002ca1c  addss   xmm13, dword ptr [rdx+60h]
0x18002ca22  mov     r10, [rax+rcx]
0x18002ca26  movsxd  rax, dword ptr [rcx+259ACh]
0x18002ca2d  movss   [rsp+0C8h+arg_10], xmm0
0x18002ca36  movss   xmm0, dword ptr [rdx+3Ch]
0x18002ca3b  addss   xmm0, dword ptr [rdx+40h]
0x18002ca40  movss   [rsp+0C8h+arg_0], xmm14
0x18002ca4a  movss   [rsp+0C8h+var_C8], xmm12
0x18002ca50  movss   [rsp+0C8h+var_C4], xmm10
0x18002ca57  shl     r9, 9
0x18002ca5b  movaps  xmm8, xmm0
0x18002ca5f  movss   [rsp+0C8h+var_B0], xmm6
0x18002ca65  addss   xmm8, xmm14
0x18002ca6a  movss   [rsp+0C8h+var_B4], xmm4
0x18002ca70  movaps  xmm14, xmm2
0x18002ca74  shl     r8, 9
0x18002ca78  addss   xmm14, xmm12
0x18002ca7d  add     r9, rax
0x18002ca80  movaps  xmm12, xmm3
0x18002ca84  add     r8, rax
0x18002ca87  addss   xmm12, xmm10
0x18002ca8c  movaps  xmm10, xmm5
0x18002ca90  movss   [rsp+0C8h+arg_18], xmm8
0x18002ca9a  addss   xmm10, xmm6
0x18002ca9f  movaps  xmm8, xmm1
0x18002caa3  movaps  xmm6, xmm9
0x18002caa7  addss   xmm8, [rsp+0C8h+arg_10]
0x18002cab1  movss   [rsp+0C8h+var_C0], xmm14
0x18002cab8  addss   xmm6, xmm15
0x18002cabd  movss   xmm14, [rsp+0C8h+arg_0]
0x18002cac7  movss   [rsp+0C8h+arg_8], xmm8
0x18002cad1  movaps  xmm8, xmm7
0x18002cad5  addss   xmm8, xmm4
0x18002cada  movaps  xmm4, xmm11
0x18002cade  addss   xmm4, xmm13
0x18002cae3  subss   xmm14, xmm0
0x18002cae8  movss   xmm0, [rsp+0C8h+arg_10]
0x18002caf1  subss   xmm0, xmm1
0x18002caf5  movaps  xmm1, xmm4
0x18002caf8  subss   xmm13, xmm11
0x18002cafd  subss   xmm15, xmm9
0x18002cb02  mulss   xmm14, dword ptr [rcx+21040h]
0x18002cb0b  mulss   xmm0, dword ptr [rcx+21044h]
0x18002cb13  mulss   xmm13, dword ptr [rcx+2105Ch]
0x18002cb1c  mulss   xmm15, dword ptr [rcx+21058h]
0x18002cb25  movss   [rsp+0C8h+arg_10], xmm0
0x18002cb2e  movss   xmm0, [rsp+0C8h+var_C8]
0x18002cb33  subss   xmm0, xmm2
0x18002cb37  movss   [rsp+0C8h+arg_0], xmm14
0x18002cb41  movss   xmm11, [rsp+0C8h+arg_0]
0x18002cb4b  movaps  xmm2, xmm6
0x18002cb4e  movss   xmm14, [rsp+0C8h+var_C0]
0x18002cb55  mulss   xmm0, dword ptr [rcx+21048h]
0x18002cb5d  movss   [rsp+0C8h+var_C8], xmm0
0x18002cb62  movss   xmm0, [rsp+0C8h+var_C4]
0x18002cb68  subss   xmm0, xmm3
0x18002cb6c  movss   xmm3, dword ptr [rcx+21060h]
0x18002cb74  mulss   xmm0, dword ptr [rcx+2104Ch]
0x18002cb7c  movss   [rsp+0C8h+var_C4], xmm0
0x18002cb82  movss   xmm0, [rsp+0C8h+var_B0]
0x18002cb88  subss   xmm0, xmm5
0x18002cb8c  movaps  xmm5, xmm10
0x18002cb90  addss   xmm5, xmm12
0x18002cb95  subss   xmm12, xmm10
0x18002cb9a  movaps  xmm10, xmm13
0x18002cb9e  addss   xmm10, xmm11
0x18002cba3  subss   xmm11, xmm13
0x18002cba8  movss   xmm13, [rsp+0C8h+var_C8]
0x18002cbae  mulss   xmm0, dword ptr [rcx+21050h]
0x18002cbb6  movss   [rsp+0C8h+var_B0], xmm0
0x18002cbbc  movss   xmm0, [rsp+0C8h+var_B4]
0x18002cbc2  movss   xmm9, [rsp+0C8h+var_B0]
0x18002cbc9  subss   xmm0, xmm7
0x18002cbcd  mulss   xmm11, xmm3
0x18002cbd2  movaps  xmm7, xmm8
0x18002cbd6  addss   xmm7, xmm14
0x18002cbdb  subss   xmm14, xmm8
0x18002cbe0  mulss   xmm0, dword ptr [rcx+21054h]
0x18002cbe8  movss   [rsp+0C8h+arg_0], xmm11
0x18002cbf2  movss   [rsp+0C8h+var_B4], xmm0
0x18002cbf8  movss   xmm0, [rsp+0C8h+arg_18]
0x18002cc01  movss   xmm8, [rsp+0C8h+var_B4]
0x18002cc08  addss   xmm1, xmm0
0x18002cc0c  subss   xmm0, xmm4
0x18002cc10  movaps  xmm4, xmm15
0x18002cc14  addss   xmm4, [rsp+0C8h+arg_10]
0x18002cc1d  subss   xmm13, xmm8
0x18002cc22  movss   [rsp+0C8h+var_B8], xmm1
0x18002cc28  movss   xmm1, [rsp+0C8h+arg_8]
0x18002cc31  mulss   xmm0, xmm3
0x18002cc35  addss   xmm2, xmm1
0x18002cc39  movss   xmm3, [rsp+0C8h+arg_10]
0x18002cc42  subss   xmm1, xmm6
0x18002cc46  subss   xmm3, xmm15
0x18002cc4b  movss   [rsp+0C8h+var_C0], xmm4
0x18002cc51  movss   [rsp+0C8h+arg_18], xmm0
0x18002cc5a  movaps  xmm4, xmm9
0x18002cc5e  movss   xmm0, dword ptr [rcx+2106Ch]
0x18002cc66  movaps  xmm6, xmm8
0x18002cc6a  addss   xmm6, [rsp+0C8h+var_C8]
0x18002cc6f  addss   xmm4, [rsp+0C8h+var_C4]
0x18002cc75  movss   [rsp+0C8h+var_BC], xmm2
0x18002cc7b  movss   xmm2, dword ptr [rcx+21064h]
0x18002cc83  mulss   xmm3, xmm2
0x18002cc87  mulss   xmm1, xmm2
0x18002cc8b  movss   [rsp+0C8h+arg_10], xmm3
0x18002cc94  movss   xmm3, [rsp+0C8h+var_C4]
0x18002cc9a  subss   xmm3, xmm9
0x18002cc9f  movss   [rsp+0C8h+arg_8], xmm1
0x18002cca8  movss   xmm1, dword ptr [rcx+21068h]
0x18002ccb0  movaps  xmm9, xmm5
0x18002ccb4  mulss   xmm12, xmm0
0x18002ccb9  mulss   xmm14, xmm1
0x18002ccbe  mulss   xmm3, xmm0
0x18002ccc2  movss   xmm0, [rsp+0C8h+var_B8]
0x18002ccc8  mulss   xmm13, xmm1
0x18002cccd  movss   xmm2, dword ptr [rcx+21070h]
0x18002ccd5  addss   xmm9, xmm0
0x18002ccda  movss   xmm1, dword ptr [rcx+21074h]
0x18002cce2  subss   xmm0, xmm5
0x18002cce6  movss   xmm15, [rsp+0C8h+arg_18]
0x18002ccf0  movaps  xmm5, xmm12
0x18002ccf4  movss   xmm8, [rsp+0C8h+var_BC]
0x18002ccfb  addss   xmm5, xmm15
0x18002cd00  subss   xmm15, xmm12
0x18002cd05  movaps  xmm11, xmm7
0x18002cd09  addss   xmm11, xmm8
0x18002cd0e  movss   [rsp+0C8h+var_C4], xmm9
0x18002cd15  mulss   xmm0, xmm2
0x18002cd19  subss   xmm8, xmm7
0x18002cd1e  movaps  xmm7, xmm14
0x18002cd22  movaps  xmm12, xmm9
0x18002cd26  mulss   xmm15, xmm2
0x18002cd2b  movss   [rsp+0C8h+var_B8], xmm0
0x18002cd31  subss   xmm12, xmm11
0x18002cd36  movss   xmm0, [rsp+0C8h+arg_8]
0x18002cd3f  addss   xmm7, xmm0
0x18002cd43  mulss   xmm8, xmm1
0x18002cd48  subss   xmm0, xmm14
0x18002cd4d  movss   [rsp+0C8h+var_B4], xmm11
0x18002cd54  movaps  xmm14, xmm4
0x18002cd58  movss   [rsp+0C8h+arg_18], xmm15
0x18002cd62  addss   xmm14, xmm10
0x18002cd67  movss   [rsp+0C8h+var_BC], xmm8
0x18002cd6e  subss   xmm10, xmm4
0x18002cd73  movaps  xmm8, xmm6
0x18002cd77  movss   xmm4, [rsp+0C8h+arg_0]
0x18002cd80  movaps  xmm11, xmm15
0x18002cd84  mulss   xmm0, xmm1
0x18002cd88  mulss   xmm10, xmm2
0x18002cd8d  movss   [rsp+0C8h+arg_8], xmm0
0x18002cd96  movss   xmm0, [rsp+0C8h+var_C0]
0x18002cd9c  addss   xmm8, xmm0
0x18002cda1  movss   [rsp+0C8h+var_B0], xmm10
0x18002cda8  movss   xmm15, [rsp+0C8h+var_B0]
0x18002cdaf  subss   xmm0, xmm6
0x18002cdb3  movss   xmm6, [rsp+0C8h+arg_10]
0x18002cdbc  movaps  xmm10, xmm3
0x18002cdc0  addss   xmm10, xmm4
0x18002cdc5  subss   xmm4, xmm3
0x18002cdc9  movss   xmm3, dword ptr [rcx+21078h]
0x18002cdd1  mulss   xmm12, xmm3
0x18002cdd6  mulss   xmm0, xmm1
0x18002cdda  mulss   xmm4, xmm2
0x18002cdde  movaps  xmm2, xmm15
0x18002cde2  movss   [rsp+0C8h+var_C0], xmm0
0x18002cde8  movaps  xmm0, xmm13
0x18002cdec  subss   xmm2, [rsp+0C8h+var_C0]
0x18002cdf2  addss   xmm0, xmm6
0x18002cdf6  movss   [rsp+0C8h+arg_0], xmm4
0x18002cdff  movss   xmm9, [rsp+0C8h+arg_0]
0x18002ce09  subss   xmm6, xmm13
0x18002ce0e  movss   xmm13, [rsp+0C8h+var_B8]
0x18002ce15  subss   xmm13, [rsp+0C8h+var_BC]
0x18002ce1c  mulss   xmm2, xmm3
0x18002ce20  mulss   xmm6, xmm1
0x18002ce24  movaps  xmm4, xmm0
0x18002ce27  movss   xmm1, [rsp+0C8h+arg_8]
0x18002ce30  addss   xmm4, xmm10
0x18002ce35  subss   xmm10, xmm0
0x18002ce3a  mulss   xmm13, xmm3
0x18002ce3f  movss   [rsp+0C8h+arg_10], xmm6
0x18002ce48  subss   xmm11, xmm1
0x18002ce4d  addss   xmm1, [rsp+0C8h+arg_18]
0x18002ce56  subss   xmm9, [rsp+0C8h+arg_10]
0x18002ce60  movaps  xmm6, xmm5
0x18002ce63  mulss   xmm10, xmm3
0x18002ce68  mulss   xmm11, xmm3
0x18002ce6d  subss   xmm6, xmm7
0x18002ce71  mulss   xmm9, xmm3
0x18002ce76  addss   xmm1, xmm11
0x18002ce7b  mulss   xmm6, xmm3
0x18002ce7f  movaps  xmm0, xmm1
0x18002ce82  addss   xmm0, xmm6
0x18002ce86  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18002ce8d  movss   dword ptr [r10+r8*4+100h], xmm0
0x18002ce97  movss   dword ptr [r10+r8*4+700h], xmm0
0x18002cea1  addss   xmm7, xmm5
0x18002cea5  movss   xmm5, [rsp+0C8h+arg_10]
0x18002ceae  addss   xmm5, [rsp+0C8h+arg_0]
0x18002ceb7  addss   xmm7, xmm1
0x18002cebb  movaps  xmm1, xmm9
0x18002cebf  addss   xmm1, xmm2
0x18002cec3  addss   xmm5, xmm9
0x18002cec8  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x18002cecf  movss   dword ptr [r10+r8*4+300h], xmm7
0x18002ced9  movaps  xmm0, xmm1
0x18002cedc  movss   dword ptr [r10+r8*4+500h], xmm7
0x18002cee6  movss   xmm7, dword ptr cs:__xmm@80000000800000008000000080000000
0x18002ceee  xorps   xmm0, xmm7
0x18002cef1  movss   dword ptr [r10+r9*4+280h], xmm1
0x18002cefb  movss   dword ptr [r10+r9*4+580h], xmm0
0x18002cf05  addss   xmm1, xmm10
0x18002cf0a  movaps  xmm0, xmm8
0x18002cf0e  addss   xmm0, xmm14
0x18002cf13  subss   xmm14, xmm8
0x18002cf18  movss   dword ptr [r10+r9*4+180h], xmm1
0x18002cf22  xorps   xmm1, xmm7
0x18002cf25  movss   dword ptr [r10+r9*4+680h], xmm1
0x18002cf2f  movss   xmm1, [rsp+0C8h+var_C0]
0x18002cf35  addss   xmm0, xmm4
0x18002cf39  addss   xmm1, xmm15
0x18002cf3e  mulss   xmm14, xmm3
0x18002cf43  addss   xmm0, xmm5
0x18002cf47  addss   xmm1, xmm2
0x18002cf4b  addss   xmm14, xmm10
0x18002cf50  xorps   xmm0, xmm7
0x18002cf53  movss   dword ptr [r10+r8*4+380h], xmm0
0x18002cf5d  addss   xmm1, xmm5
0x18002cf61  movss   dword ptr [r10+r8*4+480h], xmm0
0x18002cf6b  movaps  xmm0, xmm14
0x18002cf6f  addss   xmm0, xmm5
0x18002cf73  addss   xmm14, xmm9
0x18002cf78  xorps   xmm0, xmm7
0x18002cf7b  movss   dword ptr [r10+r8*4+80h], xmm0
0x18002cf85  movss   dword ptr [r10+r8*4+780h], xmm0
0x18002cf8f  movaps  xmm0, xmm1
0x18002cf92  addss   xmm0, xmm10
0x18002cf97  addss   xmm1, xmm4
0x18002cf9b  xorps   xmm0, xmm7
0x18002cf9e  movss   dword ptr [r10+r8*4+180h], xmm0
0x18002cfa8  xorps   xmm1, xmm7
0x18002cfab  movss   dword ptr [r10+r8*4+680h], xmm0
0x18002cfb5  movaps  xmm0, xmm11
0x18002cfb9  addss   xmm0, xmm6
0x18002cfbd  movss   dword ptr [r10+r8*4+280h], xmm1
0x18002cfc7  movss   dword ptr [r10+r8*4+580h], xmm1
0x18002cfd1  movss   dword ptr [r10+r9*4+80h], xmm14
0x18002cfdb  xorps   xmm14, xmm7
0x18002cfdf  movss   dword ptr [r10+r9*4+780h], xmm14
0x18002cfe9  movss   dword ptr [r10+r9*4+100h], xmm0
0x18002cff3  xorps   xmm0, xmm7
  ... truncated ...
```
