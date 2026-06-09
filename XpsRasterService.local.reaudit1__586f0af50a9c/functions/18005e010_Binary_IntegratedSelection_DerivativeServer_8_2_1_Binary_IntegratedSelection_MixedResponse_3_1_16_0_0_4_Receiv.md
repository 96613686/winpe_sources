# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005e010`
- end: `0x18005ecc4`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$07$01$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `3252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006aae0`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x18005e010`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rdi
  int v12; // r8d
  int v13; // r11d
  int v14; // edx
  int v15; // edx
  int v16; // r15d
  int v17; // ecx
  int v18; // r10d
  __int64 v19; // r8
  int v20; // r9d
  int v21; // r10d
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r13
  __int64 v26; // r12
  __int64 v27; // r14
  __int64 v28; // rbx
  __int64 v29; // rdi
  double v30; // xmm0_8
  float v31; // xmm7_4
  double v32; // xmm0_8
  float v33; // xmm6_4
  double v34; // xmm0_8
  _WORD *v35; // rdi
  int v36; // r14d
  __int64 v37; // r15
  __int64 v38; // rbx
  double v39; // xmm0_8
  float v40; // xmm7_4
  double v41; // xmm0_8
  float v42; // xmm6_4
  double v43; // xmm0_8
  int v44; // eax
  __int64 v45; // rbx
  double v46; // xmm0_8
  float v47; // xmm7_4
  double v48; // xmm0_8
  float v49; // xmm6_4
  double v50; // xmm0_8
  _DWORD *v51; // rax
  int v52; // edx
  int v53; // r9d
  __int64 v54; // rbx
  __int64 v55; // rsi
  __int64 v56; // r12
  __int64 v57; // r13
  __int64 v58; // r14
  __int64 v59; // r15
  __int64 v60; // rcx
  double v61; // xmm0_8
  float v62; // xmm7_4
  double v63; // xmm0_8
  float v64; // xmm6_4
  double v65; // xmm0_8
  int v66; // eax
  double v67; // xmm0_8
  float v68; // xmm7_4
  double v69; // xmm0_8
  float v70; // xmm6_4
  double v71; // xmm0_8
  double v72; // xmm0_8
  float v73; // xmm7_4
  double v74; // xmm0_8
  float v75; // xmm6_4
  double v76; // xmm0_8
  int v77; // eax
  double v78; // xmm0_8
  float v79; // xmm7_4
  double v80; // xmm0_8
  float v81; // xmm6_4
  double v82; // xmm0_8
  double v83; // xmm0_8
  float v84; // xmm7_4
  double v85; // xmm0_8
  float v86; // xmm6_4
  double v87; // xmm0_8
  int v88; // eax
  double v89; // xmm0_8
  float v90; // xmm7_4
  double v91; // xmm0_8
  float v92; // xmm6_4
  double v93; // xmm0_8
  double v94; // xmm0_8
  float v95; // xmm7_4
  double v96; // xmm0_8
  float v97; // xmm6_4
  double v98; // xmm0_8
  int v99; // eax
  double v100; // xmm0_8
  float v101; // xmm7_4
  double v102; // xmm0_8
  float v103; // xmm6_4
  double v104; // xmm0_8
  double v105; // xmm0_8
  float v106; // xmm7_4
  double v107; // xmm0_8
  float v108; // xmm6_4
  double v109; // xmm0_8
  int v110; // eax
  double v111; // xmm0_8
  float v112; // xmm7_4
  double v113; // xmm0_8
  float v114; // xmm6_4
  double v115; // xmm0_8
  double v116; // xmm0_8
  float v117; // xmm7_4
  double v118; // xmm0_8
  float v119; // xmm6_4
  double v120; // xmm0_8
  int v121; // eax
  double v122; // xmm0_8
  float v123; // xmm7_4
  double v124; // xmm0_8
  float v125; // xmm6_4
  double v126; // xmm0_8
  double v127; // xmm0_8
  float v128; // xmm7_4
  double v129; // xmm0_8
  float v130; // xmm6_4
  double v131; // xmm0_8
  int v132; // eax
  double v133; // xmm0_8
  float v134; // xmm7_4
  double v135; // xmm0_8
  float v136; // xmm6_4
  double v137; // xmm0_8
  double v138; // xmm0_8
  float v139; // xmm7_4
  double v140; // xmm0_8
  float v141; // xmm6_4
  double v142; // xmm0_8
  int v143; // eax
  double v144; // xmm0_8
  float v145; // xmm7_4
  double v146; // xmm0_8
  float v147; // xmm6_4
  double v148; // xmm0_8
  bool v149; // zf
  __int64 v150; // r15
  __int64 v151; // r14
  int v152; // r8d
  __int64 v153; // rsi
  __int64 v154; // r15
  __int64 v155; // rbx
  __int64 v156; // r14
  __int64 v157; // r12
  double v158; // xmm0_8
  float v159; // xmm7_4
  double v160; // xmm0_8
  float v161; // xmm6_4
  double v162; // xmm0_8
  int v163; // eax
  double v164; // xmm0_8
  float v165; // xmm7_4
  double v166; // xmm0_8
  float v167; // xmm6_4
  double v168; // xmm0_8
  int v169; // ecx
  int v171; // [rsp+30h] [rbp-D0h]
  __int64 v172; // [rsp+30h] [rbp-D0h]
  __int64 v173; // [rsp+38h] [rbp-C8h]
  __int64 v174; // [rsp+38h] [rbp-C8h]
  _DWORD *v175; // [rsp+40h] [rbp-C0h]
  __int64 v176; // [rsp+40h] [rbp-C0h]
  __int64 v177; // [rsp+48h] [rbp-B8h]
  __int64 v178; // [rsp+48h] [rbp-B8h]
  int v179; // [rsp+50h] [rbp-B0h]
  __int64 v180; // [rsp+58h] [rbp-A8h]
  __int64 v181; // [rsp+60h] [rbp-A0h]
  __int64 v182; // [rsp+68h] [rbp-98h]
  __int64 v183; // [rsp+70h] [rbp-90h]
  __int64 v184; // [rsp+78h] [rbp-88h]
  __int64 v185; // [rsp+80h] [rbp-80h]
  __int64 v186; // [rsp+88h] [rbp-78h]
  __int64 v187; // [rsp+90h] [rbp-70h]
  __int64 v188; // [rsp+98h] [rbp-68h]
  __int64 v189; // [rsp+98h] [rbp-68h]
  int v190; // [rsp+A0h] [rbp-60h]
  __int64 v191; // [rsp+A8h] [rbp-58h]
  __int128 v194; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 *v195; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v196; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v197[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v198; // [rsp+E8h] [rbp-18h]
  __int128 v199; // [rsp+F8h] [rbp-8h]
  __int128 v200; // [rsp+108h] [rbp+8h]
  __int128 v201; // [rsp+118h] [rbp+18h]
  int v202; // [rsp+130h] [rbp+30h] BYREF
  int v203; // [rsp+134h] [rbp+34h]
  __int64 v204; // [rsp+138h] [rbp+38h]
  char v205[32]; // [rsp+140h] [rbp+40h] BYREF
  int v206; // [rsp+160h] [rbp+60h]
  int v207; // [rsp+164h] [rbp+64h]
  int v208; // [rsp+168h] [rbp+68h]
  _DWORD v209[374]; // [rsp+16Ch] [rbp+6Ch]
  int v210; // [rsp+744h] [rbp+644h]
  int v211; // [rsp+74Ch] [rbp+64Ch]
  int v212; // [rsp+75Ch] [rbp+65Ch]

  v5 = a1;
  v194 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v202, 2, 1, a3, &v194, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  *(_QWORD *)&v200 = &v8[v204];
  *((_QWORD *)&v200 + 1) = &v8[v204 + 2];
  *(_QWORD *)&v201 = &v8[v204 + 4];
  *((_QWORD *)&v201 + 1) = &v8[v204 + 6];
  LOBYTE(v9) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                 (Binary::IntegratedSelection::SmoothControl *)v205,
                 v8,
                 &v196,
                 &v195);
  if ( (_BYTE)v9 )
  {
    v10 = v202;
    v11 = 0;
    v191 = 0;
    v12 = 0;
    v197[0] = 2;
    v179 = 0;
    if ( v202 > 0 )
    {
      v13 = v208;
      v14 = v206;
      v171 = v203;
      do
      {
        v206 = ++v14;
        if ( v14 == 1 )
        {
          v15 = *(_DWORD *)(v5 + 40);
          v16 = 0;
          v17 = *(_DWORD *)(v5 + 44);
          v18 = *(_DWORD *)(v5 + 28);
          v19 = *(int *)(v5 + 52);
          if ( v207 <= 0 )
            v16 = v207;
          if ( v18 < v17 )
            v18 = *(_DWORD *)(v5 + 44);
          v20 = v19 - 1;
          v21 = v18 - v17;
          v198 = v200;
          if ( v13 < v15 )
            v13 = v15;
          v22 = (v13 - v15) % *(_DWORD *)(v5 + 48);
          v23 = *(_QWORD *)(v5 + 56);
          v24 = v212;
          v199 = v201;
          if ( v21 <= v20 )
            v20 = v21;
          v25 = v11 + v200;
          v26 = v11 + *((_QWORD *)&v200 + 1);
          v27 = v20;
          v28 = v23 + 2 * v19 * v22;
          v188 = v11 + v200;
          *(_QWORD *)&v198 = v11 + v200;
          v173 = v26;
          *((_QWORD *)&v198 + 1) = v11 + *((_QWORD *)&v200 + 1);
          v177 = v11 + v201;
          *(_QWORD *)&v199 = v11 + v201;
          v29 = -8 * v16;
          v30 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v29 + v26);
          v31 = *(float *)&v30;
          v32 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v29 + v177);
          v33 = *(float *)&v32;
          v34 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v29 + v25);
          v35 = (_WORD *)(v28 + 2 * (v27 + 1));
          *(_WORD *)(v28 + 2 * v27) = (int)fmaxf(
                                             0.0,
                                             fminf(
                                               1023.0,
                                               (float)((float)(*(float *)&v34 + v31) + v33) * (float)(1023.0 / 3.0)));
          v36 = v197[v24] - v16;
          v37 = (int)v24 + 1;
          if ( v37 < 1 )
          {
            v175 = &v197[v37];
            do
            {
              if ( v36 >= v171 )
                break;
              v38 = 8 * v36;
              v39 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v26 + v38);
              v40 = *(float *)&v39;
              v41 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + v177);
              v42 = *(float *)&v41;
              v43 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + v25);
              v44 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v43 + v40) + v42) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v44 > 0x3ECu )
              {
                _mm_lfence();
                v45 = 8 * v36 - 8;
                v173 = *((_QWORD *)&v198 + 1);
                v46 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(*((_QWORD *)&v198 + 1) + v45);
                v47 = *(float *)&v46;
                v48 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v45 + v199);
                v49 = *(float *)&v48;
                v188 = v198;
                v50 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v198 + v45);
                v44 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v50 + v47) + v49) * (float)(1023.0 / 3.0)));
              }
              ++v37;
              *v35 = v44;
              v51 = v175;
              ++v35;
              ++v175;
              v36 += *v51;
            }
            while ( v37 < 1 );
          }
          v52 = v203;
          v53 = v36 - 1;
          v171 = v203;
          if ( v36 - 1 >= v203 - 15 )
          {
            v151 = v188;
            v150 = v173;
          }
          else
          {
            v54 = v177 + 8 * v53;
            v176 = v177 + 8 * v53 + 120;
            v55 = v177 + 8 * v53 + 112;
            v56 = v26 - v177;
            v57 = v25 - v177;
            v58 = v177 + 8 * v53 + 96;
            v174 = v177 + 8 * v53 + 104;
            v59 = v177 + 8 * v53 + 80;
            v187 = v177 + 8 * v53 + 88;
            v186 = v177 + 8 * v53 + 64;
            v185 = v177 + 8 * v53 + 72;
            v184 = v177 + 8 * v53 + 48;
            v183 = v177 + 8 * v53 + 56;
            v182 = v177 + 8 * v53 + 32;
            v181 = v177 + 8 * v53 + 40;
            v180 = v177 + 8 * v53 + 16;
            v172 = v177 + 8 * v53 + 24;
            v60 = v177 + 8 * v53 + 8;
            v178 = v60;
            v189 = ((unsigned int)(v203 - 15 - v53 - 1) >> 4) + 1;
            v190 = 16 * v189 + v53;
            do
            {
              v61 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v60);
              v62 = *(float *)&v61;
              v63 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v178);
              v64 = *(float *)&v63;
              v65 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v178);
              v66 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v65 + v62) + v64) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v66 > 0x3ECu )
              {
                _mm_lfence();
                v67 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v54 + v56);
                v68 = *(float *)&v67;
                v69 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v54);
                v70 = *(float *)&v69;
                v71 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v54 + v57);
                v66 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v71 + v68) + v70) * (float)(1023.0 / 3.0)));
              }
              *v35 = v66;
              v72 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v172);
              v73 = *(float *)&v72;
              v74 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v172);
              v75 = *(float *)&v74;
              v76 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v172);
              v77 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v76 + v73) + v75) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v77 > 0x3ECu )
              {
                _mm_lfence();
                v78 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v180);
                v79 = *(float *)&v78;
                v80 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v180);
                v81 = *(float *)&v80;
                v82 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v180);
                v77 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v82 + v79) + v81) * (float)(1023.0 / 3.0)));
              }
              v35[1] = v77;
              v83 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v181);
              v84 = *(float *)&v83;
              v85 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v181);
              v86 = *(float *)&v85;
              v87 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v181);
              v88 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v87 + v84) + v86) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v88 > 0x3ECu )
              {
                _mm_lfence();
                v89 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v182);
                v90 = *(float *)&v89;
                v91 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v182);
                v92 = *(float *)&v91;
                v93 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v182);
                v88 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v93 + v90) + v92) * (float)(1023.0 / 3.0)));
              }
              v35[2] = v88;
              v94 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v183);
              v95 = *(float *)&v94;
              v96 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v183);
              v97 = *(float *)&v96;
              v98 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v183);
              v99 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v98 + v95) + v97) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v99 > 0x3ECu )
              {
                _mm_lfence();
                v100 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v184);
                v101 = *(float *)&v100;
                v102 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v184);
                v103 = *(float *)&v102;
                v104 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v184);
                v99 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v104 + v101) + v103) * (float)(1023.0 / 3.0)));
              }
              v35[3] = v99;
              v105 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v185);
              v106 = *(float *)&v105;
              v107 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v185);
              v108 = *(float *)&v107;
              v109 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v185);
              v110 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v109 + v106) + v108) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v110 > 0x3ECu )
              {
                _mm_lfence();
                v111 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v186);
                v112 = *(float *)&v111;
                v113 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v186);
                v114 = *(float *)&v113;
                v115 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v186);
                v110 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v115 + v112) + v114) * (float)(1023.0 / 3.0)));
              }
              v35[4] = v110;
              v116 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v187);
              v117 = *(float *)&v116;
              v118 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v187);
              v119 = *(float *)&v118;
              v120 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v187);
              v121 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v120 + v117) + v119) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v121 > 0x3ECu )
              {
                _mm_lfence();
                v122 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v59);
                v123 = *(float *)&v122;
                v124 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v59);
                v125 = *(float *)&v124;
                v126 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v59 + v57);
                v121 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v126 + v123) + v125) * (float)(1023.0 / 3.0)));
              }
              v35[5] = v121;
              v127 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v174);
              v128 = *(float *)&v127;
              v129 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v174);
              v130 = *(float *)&v129;
              v131 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v174);
              v132 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v131 + v128) + v130) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v132 > 0x3ECu )
              {
                _mm_lfence();
                v133 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v58);
                v134 = *(float *)&v133;
                v135 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v58);
                v136 = *(float *)&v135;
                v137 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v58 + v57);
                v132 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v137 + v134) + v136) * (float)(1023.0 / 3.0)));
              }
              v35[6] = v132;
              v138 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v176);
              v139 = *(float *)&v138;
              v140 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v176);
              v141 = *(float *)&v140;
              v142 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v57 + v176);
              v143 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v142 + v139) + v141) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v143 > 0x3ECu )
              {
                _mm_lfence();
                v144 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v56 + v55);
                v145 = *(float *)&v144;
                v146 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v55);
                v147 = *(float *)&v146;
                v148 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v55 + v57);
                v143 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v148 + v145) + v147) * (float)(1023.0 / 3.0)));
              }
              v54 += 128;
              v172 += 128;
              v60 = v178 + 128;
              v180 += 128;
              v59 += 128;
              v181 += 128;
              v58 += 128;
              v182 += 128;
              v55 += 128;
              v183 += 128;
              v184 += 128;
              v185 += 128;
              v186 += 128;
              v187 += 128;
              v174 += 128;
              v176 += 128;
              v35[7] = v143;
              v35 += 8;
              v149 = v189-- == 1;
              v178 += 128;
            }
            while ( !v149 );
            v52 = v203;
            v150 = *((_QWORD *)&v198 + 1);
            v151 = v198;
            v53 = v190;
            v171 = v203;
          }
          v152 = v53 + 1;
          if ( v53 + 1 < v52 )
          {
            v153 = v199 + 8 * v152;
            v154 = v150 - v199;
            v155 = v199 + 8 * v152 - 8;
            v156 = v151 - v199;
            v157 = ((unsigned int)(v52 - v152 - 1) >> 1) + 1;
            do
            {
              v158 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v154 + v153);
              v159 = *(float *)&v158;
              v160 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v153);
              v161 = *(float *)&v160;
              v162 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v156 + v153);
              v163 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v162 + v159) + v161) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v163 > 0x3ECu )
              {
                _mm_lfence();
                v164 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v154 + v155);
                v165 = *(float *)&v164;
                v166 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v155);
                v167 = *(float *)&v166;
                v168 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v156 + v155);
                v163 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v168 + v165) + v167) * (float)(1023.0 / 3.0)));
              }
              *v35 = v163;
              v153 += 16;
              ++v35;
              v155 += 16;
              --v157;
            }
            while ( v157 );
            v171 = v203;
          }
          v12 = v179;
          v14 = v206 - v209[v210];
          v169 = v210 + 1;
          v11 = v191;
          v5 = a1;
          if ( v210 + 1 >= v211 )
            v169 = 0;
          v13 = v208 + 1;
          v210 = v169;
          v10 = v202;
          ++v208;
        }
        v179 = ++v12;
        v9 = *a3;
        v11 += v9;
        v191 = v11;
      }
      while ( v12 < v10 );
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18005e010  push    rbp
0x18005e012  push    rbx
0x18005e013  push    rsi
0x18005e014  lea     rbp, [rsp-6D0h]
0x18005e01c  sub     rsp, 7D0h
0x18005e023  mov     rax, cs:__security_cookie
0x18005e02a  xor     rax, rsp
0x18005e02d  mov     [rbp+6E0h+var_80], rax
0x18005e034  movups  xmm0, xmmword ptr [r9]
0x18005e038  lea     rax, [rcx+8]
0x18005e03c  mov     [rbp+6E0h+var_728], r8
0x18005e040  mov     [rsp+7E0h+var_7B8], rax
0x18005e045  mov     rbx, rdx
0x18005e048  mov     edx, 2
0x18005e04d  mov     [rbp+6E0h+var_730], rcx
0x18005e051  mov     rsi, rcx
0x18005e054  movaps  [rbp+6E0h+var_720], xmm0
0x18005e058  lea     rax, [rbp+6E0h+var_720]
0x18005e05c  mov     r9, r8
0x18005e05f  lea     rcx, [rbp+6E0h+var_6B0]
0x18005e063  mov     [rsp+7E0h+var_7C0], rax
0x18005e068  lea     r8d, [rdx-1]
0x18005e06c  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005e071  mov     rcx, [rbx+8]
0x18005e075  lea     r9, [rbp+6E0h+var_710]; unsigned __int8 **
0x18005e079  cmp     [rbx], rcx
0x18005e07c  lea     r8, [rbp+6E0h+var_708]; unsigned __int8 **
0x18005e080  mov     rax, [rbx+10h]
0x18005e084  cmovbe  rcx, [rbx]
0x18005e088  mov     rdx, [rbx+18h]
0x18005e08c  cmp     rcx, rax
0x18005e08f  cmovbe  rax, rcx
0x18005e093  mov     rcx, [rbp+6E0h+var_6A8]
0x18005e097  cmp     rax, rdx
0x18005e09a  cmovbe  rdx, rax; unsigned __int8 *
0x18005e09e  add     rcx, rdx
0x18005e0a1  mov     qword ptr [rbp+6E0h+var_6D8], rcx
0x18005e0a5  lea     rax, [rcx+2]
0x18005e0a9  mov     qword ptr [rbp+6E0h+var_6D8+8], rax
0x18005e0ad  lea     rax, [rcx+4]
0x18005e0b1  mov     qword ptr [rbp+6E0h+var_6C8], rax
0x18005e0b5  lea     rax, [rcx+6]
0x18005e0b9  lea     rcx, [rbp+6E0h+var_6A0]; this
0x18005e0bd  mov     qword ptr [rbp+6E0h+var_6C8+8], rax
0x18005e0c1  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005e0c6  test    al, al
0x18005e0c8  jz      loc_18005ECAA
0x18005e0ce  mov     ecx, [rbp+6E0h+var_6B0]
0x18005e0d1  xor     r9d, r9d
0x18005e0d4  mov     [rsp+7E0h+var_18], rdi
0x18005e0dc  mov     edi, r9d
0x18005e0df  mov     [rbp+6E0h+var_738], r9
0x18005e0e3  mov     r8d, r9d
0x18005e0e6  mov     [rbp+6E0h+var_700], 2
0x18005e0ed  mov     [rsp+7E0h+var_790], r9d
0x18005e0f2  test    ecx, ecx
0x18005e0f4  jle     loc_18005ECA2
0x18005e0fa  mov     eax, [rbp+6E0h+var_6AC]
0x18005e0fd  mov     r11d, [rbp+6E0h+var_678]
0x18005e101  mov     edx, [rbp+6E0h+var_680]
0x18005e104  mov     [rsp+7E0h+var_20], r12
0x18005e10c  mov     [rsp+7E0h+var_28], r13
0x18005e114  mov     [rsp+7E0h+var_30], r14
0x18005e11c  mov     [rsp+7E0h+var_38], r15
0x18005e124  movaps  [rsp+7E0h+var_50], xmm6
0x18005e12c  movaps  [rsp+7E0h+var_60], xmm7
0x18005e134  movaps  [rsp+7E0h+var_70], xmm8
0x18005e13d  movss   xmm8, cs:__real@447fc000
0x18005e146  mov     dword ptr [rsp+7E0h+var_7B0], eax
0x18005e14a  nop     word ptr [rax+rax+00h]
0x18005e150  inc     edx
0x18005e152  mov     [rbp+6E0h+var_680], edx
0x18005e155  cmp     edx, 1
0x18005e158  jnz     loc_18005EC4A
0x18005e15e  mov     edx, [rsi+28h]
0x18005e161  mov     r15d, r9d
0x18005e164  mov     ecx, [rsi+2Ch]
0x18005e167  mov     eax, [rbp+6E0h+var_67C]
0x18005e16a  test    eax, eax
0x18005e16c  mov     r10d, [rsi+1Ch]
0x18005e170  movsxd  r8, dword ptr [rsi+34h]
0x18005e174  cmovle  r15d, eax
0x18005e178  movups  xmm1, [rbp+6E0h+var_6C8]
0x18005e17c  mov     r13, qword ptr [rbp+6E0h+var_6D8]
0x18005e180  cmp     r10d, ecx
0x18005e183  movups  xmm0, [rbp+6E0h+var_6D8]
0x18005e187  cmovl   r10d, ecx
0x18005e18b  lea     r9d, [r8-1]
0x18005e18f  sub     r10d, ecx
0x18005e192  cmp     r11d, edx
0x18005e195  movups  [rbp+6E0h+var_6F8], xmm0
0x18005e199  mov     r12, qword ptr [rbp+6E0h+var_6F8+8]
0x18005e19d  cmovl   r11d, edx
0x18005e1a1  sub     r11d, edx
0x18005e1a4  mov     eax, r11d
0x18005e1a7  cdq
0x18005e1a8  idiv    dword ptr [rsi+30h]
0x18005e1ab  mov     rax, [rsi+38h]
0x18005e1af  movsxd  rsi, [rbp+6E0h+var_84]
0x18005e1b6  movsxd  rcx, edx
0x18005e1b9  imul    rcx, r8
0x18005e1bd  movups  [rbp+6E0h+var_6E8], xmm1
0x18005e1c1  cmp     r10d, r9d
0x18005e1c4  cmovle  r9d, r10d
0x18005e1c8  add     r13, rdi
0x18005e1cb  add     r12, rdi
0x18005e1ce  movsxd  r14, r9d
0x18005e1d1  lea     rbx, [rax+rcx*2]
0x18005e1d5  mov     rax, r13
0x18005e1d8  mov     [rbp+6E0h+var_748], rax
0x18005e1dc  mov     qword ptr [rbp+6E0h+var_6F8], rax
0x18005e1e0  mov     rax, r12
0x18005e1e3  mov     [rsp+7E0h+var_7A8], rax
0x18005e1e8  mov     qword ptr [rbp+6E0h+var_6F8+8], rax
0x18005e1ec  movq    rax, xmm1
0x18005e1f1  add     rax, rdi
0x18005e1f4  mov     [rsp+7E0h+var_798], rax
0x18005e1f9  mov     qword ptr [rbp+6E0h+var_6E8], rax
0x18005e1fd  mov     eax, r15d
0x18005e200  neg     eax
0x18005e202  shl     eax, 3
0x18005e205  movsxd  rdi, eax
0x18005e208  lea     rcx, [rdi+r12]
0x18005e20c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e211  mov     rcx, [rsp+7E0h+var_798]
0x18005e216  movaps  xmm7, xmm0
0x18005e219  add     rcx, rdi
0x18005e21c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e221  lea     rcx, [rdi+r13]
0x18005e225  movaps  xmm6, xmm0
0x18005e228  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e22d  addss   xmm0, xmm7
0x18005e231  movaps  xmm1, xmm8
0x18005e235  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005e23d  lea     rdi, [r14+1]
0x18005e241  lea     rdi, [rbx+rdi*2]
0x18005e245  addss   xmm0, xmm6
0x18005e249  movaps  xmm2, xmm8
0x18005e24d  mulss   xmm0, xmm1
0x18005e251  minss   xmm2, xmm0
0x18005e255  xorps   xmm0, xmm0
0x18005e258  maxss   xmm0, xmm2
0x18005e25c  cvttss2si eax, xmm0
0x18005e260  mov     [rbx+r14*2], ax
0x18005e265  lea     eax, [rsi+1]
0x18005e268  mov     r14d, [rbp+rsi*4+6E0h+var_700]
0x18005e26d  sub     r14d, r15d
0x18005e270  movsxd  r15, eax
0x18005e273  cmp     r15, 1
0x18005e277  jge     loc_18005E397
0x18005e27d  mov     esi, dword ptr [rsp+7E0h+var_7B0]
0x18005e281  lea     rax, [rbp+6E0h+var_700]
0x18005e285  lea     rax, [rax+r15*4]
0x18005e289  mov     [rsp+7E0h+var_7A0], rax
0x18005e28e  xchg    ax, ax
0x18005e290  cmp     r14d, esi
0x18005e293  jge     loc_18005E397
0x18005e299  lea     eax, ds:0[r14*8]
0x18005e2a1  movsxd  rbx, eax
0x18005e2a4  lea     rcx, [r12+rbx]
0x18005e2a8  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e2ad  mov     rcx, [rsp+7E0h+var_798]
0x18005e2b2  movaps  xmm7, xmm0
0x18005e2b5  add     rcx, rbx
0x18005e2b8  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e2bd  lea     rcx, [rbx+r13]
0x18005e2c1  movaps  xmm6, xmm0
0x18005e2c4  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e2c9  addss   xmm0, xmm7
0x18005e2cd  movaps  xmm1, xmm8
0x18005e2d1  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005e2d9  mov     ecx, 3ECh
0x18005e2de  addss   xmm0, xmm6
0x18005e2e2  movaps  xmm2, xmm8
0x18005e2e6  mulss   xmm0, xmm1
0x18005e2ea  minss   xmm2, xmm0
0x18005e2ee  xorps   xmm0, xmm0
0x18005e2f1  maxss   xmm0, xmm2
0x18005e2f5  cvttss2si eax, xmm0
0x18005e2f9  cmp     ax, cx
0x18005e2fc  jbe     short loc_18005E36F
0x18005e2fe  lfence
0x18005e301  lea     eax, ds:0[r14*8]
0x18005e309  add     eax, 0FFFFFFF8h
0x18005e30c  movsxd  rbx, eax
0x18005e30f  mov     rax, qword ptr [rbp+6E0h+var_6F8+8]
0x18005e313  mov     [rsp+7E0h+var_7A8], rax
0x18005e318  lea     rcx, [rax+rbx]
0x18005e31c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e321  mov     rcx, qword ptr [rbp+6E0h+var_6E8]
0x18005e325  movaps  xmm7, xmm0
0x18005e328  add     rcx, rbx
0x18005e32b  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e330  mov     rax, qword ptr [rbp+6E0h+var_6F8]
0x18005e334  movaps  xmm6, xmm0
0x18005e337  mov     [rbp+6E0h+var_748], rax
0x18005e33b  lea     rcx, [rax+rbx]
0x18005e33f  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e344  addss   xmm0, xmm7
0x18005e348  movaps  xmm1, xmm8
0x18005e34c  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005e354  addss   xmm0, xmm6
0x18005e358  movaps  xmm2, xmm8
0x18005e35c  mulss   xmm0, xmm1
0x18005e360  minss   xmm2, xmm0
0x18005e364  xorps   xmm0, xmm0
0x18005e367  maxss   xmm0, xmm2
0x18005e36b  cvttss2si eax, xmm0
0x18005e36f  mov     rcx, [rsp+7E0h+var_7A0]
0x18005e374  inc     r15
0x18005e377  mov     [rdi], ax
0x18005e37a  mov     rax, rcx
0x18005e37d  add     rcx, 4
0x18005e381  add     rdi, 2
0x18005e385  mov     [rsp+7E0h+var_7A0], rcx
0x18005e38a  add     r14d, [rax]
0x18005e38d  cmp     r15, 1
0x18005e391  jl      loc_18005E290
0x18005e397  mov     edx, [rbp+6E0h+var_6AC]
0x18005e39a  lea     r9d, [r14-1]
0x18005e39e  mov     dword ptr [rsp+7E0h+var_7B0], edx
0x18005e3a2  lea     r8d, [rdx-0Fh]
0x18005e3a6  cmp     r9d, r8d
0x18005e3a9  jge     loc_18005EB02
0x18005e3af  mov     rdx, [rsp+7E0h+var_798]
0x18005e3b4  lea     eax, ds:70h[r9*8]
0x18005e3bc  movsxd  rsi, eax
0x18005e3bf  lea     ecx, ds:0[r9*8]
0x18005e3c7  lea     eax, ds:78h[r9*8]
0x18005e3cf  movsxd  rbx, ecx
0x18005e3d2  cdqe
0x18005e3d4  sub     r8d, r9d
0x18005e3d7  add     rax, rdx
0x18005e3da  add     rbx, rdx
0x18005e3dd  mov     [rsp+7E0h+var_7A0], rax
0x18005e3e2  add     rsi, rdx
0x18005e3e5  lea     eax, ds:60h[r9*8]
0x18005e3ed  sub     r12, rdx
0x18005e3f0  movsxd  r14, eax
0x18005e3f3  sub     r13, rdx
0x18005e3f6  lea     eax, ds:68h[r9*8]
0x18005e3fe  add     r14, rdx
0x18005e401  cdqe
0x18005e403  add     rax, rdx
0x18005e406  mov     [rsp+7E0h+var_7A8], rax
0x18005e40b  lea     eax, ds:50h[r9*8]
0x18005e413  movsxd  r15, eax
0x18005e416  lea     eax, ds:58h[r9*8]
0x18005e41e  cdqe
0x18005e420  add     r15, rdx
0x18005e423  add     rax, rdx
0x18005e426  mov     [rbp+6E0h+var_750], rax
0x18005e42a  lea     eax, ds:40h[r9*8]
0x18005e432  cdqe
0x18005e434  add     rax, rdx
0x18005e437  mov     [rbp+6E0h+var_758], rax
0x18005e43b  lea     eax, ds:48h[r9*8]
0x18005e443  cdqe
0x18005e445  add     rax, rdx
0x18005e448  mov     [rbp+6E0h+var_760], rax
0x18005e44c  lea     eax, ds:30h[r9*8]
0x18005e454  cdqe
0x18005e456  add     rax, rdx
0x18005e459  mov     [rsp+7E0h+var_768], rax
0x18005e45e  lea     eax, ds:38h[r9*8]
0x18005e466  cdqe
0x18005e468  add     rax, rdx
0x18005e46b  mov     [rsp+7E0h+var_770], rax
0x18005e470  lea     eax, ds:20h[r9*8]
0x18005e478  cdqe
0x18005e47a  add     rax, rdx
0x18005e47d  mov     [rsp+7E0h+var_778], rax
0x18005e482  lea     eax, ds:28h[r9*8]
0x18005e48a  cdqe
0x18005e48c  add     rax, rdx
0x18005e48f  mov     [rsp+7E0h+var_780], rax
0x18005e494  lea     eax, ds:10h[r9*8]
0x18005e49c  cdqe
0x18005e49e  add     rax, rdx
0x18005e4a1  mov     [rsp+7E0h+var_788], rax
0x18005e4a6  lea     eax, ds:18h[r9*8]
0x18005e4ae  cdqe
0x18005e4b0  add     rax, rdx
0x18005e4b3  mov     [rsp+7E0h+var_7B0], rax
0x18005e4b8  lea     eax, [rcx+8]
0x18005e4bb  movsxd  rcx, eax
0x18005e4be  lea     eax, [r8-1]
0x18005e4c2  shr     eax, 4
0x18005e4c5  add     rcx, rdx
0x18005e4c8  inc     eax
0x18005e4ca  mov     [rsp+7E0h+var_798], rcx
0x18005e4cf  mov     edx, eax
0x18005e4d1  shl     eax, 4
0x18005e4d4  add     r9d, eax
0x18005e4d7  mov     [rbp+6E0h+var_748], rdx
0x18005e4db  mov     [rbp+6E0h+var_740], r9d
0x18005e4df  nop
0x18005e4e0  add     rcx, r12
0x18005e4e3  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005e4e8  mov     rcx, [rsp+7E0h+var_798]
  ... truncated ...
```
