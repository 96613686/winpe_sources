# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005ecd0`
- end: `0x18005f4a4`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$07$01$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `2004`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006aae0`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x18005ecd0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r14
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  int v9; // esi
  unsigned __int8 *v10; // rbx
  int v11; // eax
  __int64 v12; // r12
  int v13; // r11d
  int v14; // edi
  int v15; // r15d
  __int128 v16; // xmm9
  __int64 v17; // xmm10_8
  int v18; // ecx
  unsigned __int8 *v19; // r13
  int v20; // r10d
  __int64 v21; // r8
  int v22; // eax
  int v23; // r10d
  int v24; // r9d
  int v25; // eax
  __int64 v26; // rcx
  int v27; // esi
  _WORD *v28; // r14
  unsigned __int8 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r12
  unsigned __int8 *v32; // rbx
  __int64 v33; // rdi
  double v34; // xmm0_8
  float v35; // xmm7_4
  double v36; // xmm0_8
  float v37; // xmm6_4
  double v38; // xmm0_8
  int v39; // eax
  unsigned __int8 *v40; // r12
  __int64 v41; // rcx
  unsigned __int8 *v42; // rdi
  __int64 v43; // rbx
  unsigned __int8 *v44; // rcx
  unsigned __int8 *v45; // rdi
  double v46; // xmm0_8
  float v47; // xmm7_4
  double v48; // xmm0_8
  float v49; // xmm6_4
  double v50; // xmm0_8
  double v51; // xmm0_8
  float v52; // xmm7_4
  double v53; // xmm0_8
  float v54; // xmm6_4
  double v55; // xmm0_8
  double v56; // xmm0_8
  float v57; // xmm7_4
  double v58; // xmm0_8
  float v59; // xmm6_4
  double v60; // xmm0_8
  double v61; // xmm0_8
  float v62; // xmm7_4
  double v63; // xmm0_8
  float v64; // xmm6_4
  double v65; // xmm0_8
  double v66; // xmm0_8
  float v67; // xmm7_4
  double v68; // xmm0_8
  float v69; // xmm6_4
  double v70; // xmm0_8
  double v71; // xmm0_8
  float v72; // xmm7_4
  double v73; // xmm0_8
  float v74; // xmm6_4
  double v75; // xmm0_8
  double v76; // xmm0_8
  float v77; // xmm7_4
  double v78; // xmm0_8
  float v79; // xmm6_4
  double v80; // xmm0_8
  double v81; // xmm0_8
  float v82; // xmm7_4
  double v83; // xmm0_8
  float v84; // xmm6_4
  double v85; // xmm0_8
  __int64 v86; // rdi
  unsigned __int8 *v87; // r12
  unsigned __int8 *v88; // r13
  __int64 v89; // rsi
  double v90; // xmm0_8
  float v91; // xmm7_4
  double v92; // xmm0_8
  float v93; // xmm6_4
  double v94; // xmm0_8
  __int64 v95; // rax
  unsigned __int8 *v97; // [rsp+30h] [rbp-D0h]
  int v98; // [rsp+38h] [rbp-C8h]
  int v99; // [rsp+3Ch] [rbp-C4h]
  unsigned __int8 *v100; // [rsp+40h] [rbp-C0h]
  __int64 v101; // [rsp+48h] [rbp-B8h]
  __int64 v102; // [rsp+50h] [rbp-B0h]
  __int64 v103; // [rsp+58h] [rbp-A8h]
  __int64 v104; // [rsp+68h] [rbp-98h]
  __int64 v105; // [rsp+70h] [rbp-90h]
  __int64 v106; // [rsp+78h] [rbp-88h]
  __int64 v107; // [rsp+80h] [rbp-80h]
  __int64 v108; // [rsp+88h] [rbp-78h]
  __int64 v109; // [rsp+90h] [rbp-70h]
  __int64 v110; // [rsp+98h] [rbp-68h]
  __int64 v111; // [rsp+A0h] [rbp-60h]
  __int64 v112; // [rsp+A8h] [rbp-58h]
  __int64 v113; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v114; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v117; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v118[2]; // [rsp+D8h] [rbp-28h]
  __int128 v119; // [rsp+E0h] [rbp-20h]
  __int64 v120; // [rsp+F0h] [rbp-10h]
  __int64 v121; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v122[2]; // [rsp+100h] [rbp+0h] BYREF
  int v123; // [rsp+120h] [rbp+20h] BYREF
  int v124; // [rsp+124h] [rbp+24h]
  __int64 v125; // [rsp+128h] [rbp+28h]
  char v126[32]; // [rsp+130h] [rbp+30h] BYREF
  int v127; // [rsp+150h] [rbp+50h]
  int v128; // [rsp+154h] [rbp+54h]
  int v129; // [rsp+158h] [rbp+58h]
  _DWORD v130[374]; // [rsp+15Ch] [rbp+5Ch]
  int v131; // [rsp+734h] [rbp+634h]
  int v132; // [rsp+73Ch] [rbp+63Ch]
  int v133; // [rsp+74Ch] [rbp+64Ch]

  v5 = a1;
  *(_OWORD *)v122 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v123, 2, 1, a3, v122, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  v9 = 0;
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v10 = &v8[v125];
  *(_QWORD *)&v119 = &v8[v125];
  *((_QWORD *)&v119 + 1) = &v8[v125 + 2];
  v120 = (__int64)&v8[v125 + 4];
  v121 = (__int64)&v8[v125 + 6];
  LOBYTE(v11) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v126,
                  v8,
                  &v117,
                  v122);
  if ( (_BYTE)v11 )
  {
    v12 = 0;
    v103 = 0;
    v118[0] = 2;
    v98 = 0;
    if ( v123 > 0 )
    {
      v13 = v131;
      v14 = v127;
      v15 = v124;
      v16 = v119;
      v17 = v120;
      do
      {
        v127 = ++v14;
        if ( v14 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = &v10[v12];
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v128 <= 0 )
            v9 = v128;
          v22 = *(_DWORD *)(v5 + 44);
          *(_OWORD *)v122 = v16;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v20 - v22;
          v24 = v21 - 1;
          v25 = v129;
          if ( v129 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v24 )
            v24 = v23;
          v27 = -v9;
          v28 = (_WORD *)(*(_QWORD *)(v5 + 56) + 2 * (v24 + v26));
          v29 = &v122[1][v12];
          v30 = v12 + v17;
          v100 = &v122[1][v12];
          v31 = v133;
          v101 = v30;
          if ( v133 < 1LL )
          {
            v32 = v29;
            do
            {
              if ( v27 >= v15 )
                break;
              v33 = 8 * v27;
              v34 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v32[v33]);
              v35 = *(float *)&v34;
              v36 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v33 + v101);
              v37 = *(float *)&v36;
              v38 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v19[v33]);
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v38 + v35) + v37) * (float)(1023.0 / 3.0)));
              v39 = v118[v31++];
              v27 += v39;
            }
            while ( v31 < 1 );
            v13 = v131;
            v14 = v127;
            v15 = v124;
            v10 = (unsigned __int8 *)v119;
          }
          if ( v27 >= v15 - 15 )
          {
            v40 = v100;
          }
          else
          {
            v40 = v100;
            v41 = 8 * v27 + 32;
            v42 = &v19[v41];
            v43 = 8 * v27 + 16 - v41;
            v106 = v43 - (_QWORD)v19;
            v97 = &v19[v41];
            v104 = 8 * v27 + 48 - v41;
            v107 = v104 - (_QWORD)v19;
            v109 = 8 * v27 + 64 - v41;
            v108 = v109 - (_QWORD)v19;
            v111 = 8 * v27 + 80 - v41;
            v110 = v111 - (_QWORD)v19;
            v113 = 8 * v27 + 96 - v41;
            v112 = v113 - (_QWORD)v19;
            v117 = (unsigned __int8 *)(8 * v27 + 112 - v41);
            v114 = (unsigned __int8 *)(v117 - v19);
            v105 = 8 * v27 - v41;
            v44 = (unsigned __int8 *)(v105 - (_QWORD)v19);
            v122[0] = (unsigned __int8 *)(v105 - (_QWORD)v19);
            v102 = ((unsigned int)(v15 - 15 - v27 - 1) >> 4) + 1;
            v99 = v27 + 16 * v102;
            do
            {
              v45 = &v42[(_QWORD)v44];
              v46 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v100[(_QWORD)v45]);
              v47 = *(float *)&v46;
              v48 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v45[v101]);
              v49 = *(float *)&v48;
              v50 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v105]);
              *v28 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v50 + v47) + v49) * (float)(1023.0 / 3.0)));
              v51 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v106 + (_QWORD)v100]);
              v52 = *(float *)&v51;
              v53 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v106 + v101]);
              v54 = *(float *)&v53;
              v55 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v43]);
              v28[1] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v55 + v52) + v54) * (float)(1023.0 / 3.0)));
              v56 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v100[v97 - v19]);
              v57 = *(float *)&v56;
              v58 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v101 + v97 - v19);
              v59 = *(float *)&v58;
              v60 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v97);
              v28[2] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v60 + v57) + v59) * (float)(1023.0 / 3.0)));
              v61 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v107 + (_QWORD)v100]);
              v62 = *(float *)&v61;
              v63 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v107 + v101]);
              v64 = *(float *)&v63;
              v65 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v104]);
              v28[3] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v65 + v62) + v64) * (float)(1023.0 / 3.0)));
              v66 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v108 + (_QWORD)v100]);
              v67 = *(float *)&v66;
              v68 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v108 + v101]);
              v69 = *(float *)&v68;
              v70 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v109]);
              v28[4] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v70 + v67) + v69) * (float)(1023.0 / 3.0)));
              v71 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v110 + (_QWORD)v100]);
              v72 = *(float *)&v71;
              v73 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v110 + v101]);
              v74 = *(float *)&v73;
              v75 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v111]);
              v28[5] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v75 + v72) + v74) * (float)(1023.0 / 3.0)));
              v76 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v112 + (_QWORD)v100]);
              v77 = *(float *)&v76;
              v78 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v112 + v101]);
              v79 = *(float *)&v78;
              v80 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[v113]);
              v28[6] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v80 + v77) + v79) * (float)(1023.0 / 3.0)));
              v81 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[(_QWORD)v114
                                                                                     + (unsigned __int64)v100]);
              v82 = *(float *)&v81;
              v83 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v97[(_QWORD)v114 + v101]);
              v84 = *(float *)&v83;
              v85 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v117[(_QWORD)v97]);
              v44 = v122[0];
              v42 = v97 + 128;
              v97 += 128;
              v28[7] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v85 + v82) + v84) * (float)(1023.0 / 3.0)));
              v28 += 8;
              --v102;
            }
            while ( v102 );
            v13 = v131;
            v14 = v127;
            v15 = v124;
            v10 = (unsigned __int8 *)v119;
            v27 = v99;
          }
          if ( v27 < v15 )
          {
            v86 = v101 + 8 * v27;
            v87 = &v40[-v101];
            v88 = &v19[-v101];
            v89 = ((unsigned int)(v15 - v27 - 1) >> 1) + 1;
            do
            {
              v90 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v87[v86]);
              v91 = *(float *)&v90;
              v92 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v86);
              v93 = *(float *)&v92;
              v94 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v88[v86]);
              v86 += 16;
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v94 + v91) + v93) * (float)(1023.0 / 3.0)));
              --v89;
            }
            while ( v89 );
            v13 = v131;
            v14 = v127;
            v15 = v124;
          }
          v5 = a1;
          v9 = 0;
          v12 = v103;
          v95 = v13++;
          v14 -= v130[v95];
          if ( v13 >= v132 )
            v13 = 0;
          ++v129;
          v131 = v13;
        }
        v12 += *a3;
        v11 = v98 + 1;
        v103 = v12;
        v98 = v11;
      }
      while ( v11 < v123 );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18005ecd0  push    rbp
0x18005ecd2  push    rbx
0x18005ecd3  push    rsi
0x18005ecd4  push    r14
0x18005ecd6  lea     rbp, [rsp-6D8h]
0x18005ecde  sub     rsp, 7D8h
0x18005ece5  mov     rax, cs:__security_cookie
0x18005ecec  xor     rax, rsp
0x18005ecef  mov     [rbp+6F0h+var_A0], rax
0x18005ecf6  movups  xmm0, xmmword ptr [r9]
0x18005ecfa  lea     rax, [rcx+8]
0x18005ecfe  mov     [rbp+6F0h+var_728], r8
0x18005ed02  mov     [rsp+7F0h+var_7C8], rax
0x18005ed07  mov     rbx, rdx
0x18005ed0a  mov     edx, 2
0x18005ed0f  mov     [rbp+6F0h+var_730], rcx
0x18005ed13  mov     r14, rcx
0x18005ed16  movaps  xmmword ptr [rbp+6F0h+var_6F0], xmm0
0x18005ed1a  lea     rax, [rbp+6F0h+var_6F0]
0x18005ed1e  mov     r9, r8
0x18005ed21  lea     rcx, [rbp+6F0h+var_6D0]
0x18005ed25  mov     [rsp+7F0h+var_7D0], rax
0x18005ed2a  lea     r8d, [rdx-1]
0x18005ed2e  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005ed33  mov     rcx, [rbx+8]
0x18005ed37  lea     r9, [rbp+6F0h+var_6F0]; unsigned __int8 **
0x18005ed3b  mov     rax, [rbx+10h]
0x18005ed3f  lea     r8, [rbp+6F0h+var_720]; unsigned __int8 **
0x18005ed43  mov     rdx, [rbx+18h]
0x18005ed47  xor     esi, esi
0x18005ed49  cmp     [rbx], rcx
0x18005ed4c  cmovbe  rcx, [rbx]
0x18005ed50  mov     rbx, [rbp+6F0h+var_6C8]
0x18005ed54  cmp     rcx, rax
0x18005ed57  cmovbe  rax, rcx
0x18005ed5b  lea     rcx, [rbp+6F0h+var_6C0]; this
0x18005ed5f  cmp     rax, rdx
0x18005ed62  cmovbe  rdx, rax; unsigned __int8 *
0x18005ed66  add     rbx, rdx
0x18005ed69  mov     qword ptr [rbp+6F0h+var_710], rbx
0x18005ed6d  lea     rax, [rbx+2]
0x18005ed71  mov     qword ptr [rbp+6F0h+var_710+8], rax
0x18005ed75  lea     rax, [rbx+4]
0x18005ed79  mov     qword ptr [rbp+6F0h+var_700], rax
0x18005ed7d  lea     rax, [rbx+6]
0x18005ed81  mov     qword ptr [rbp+6F0h+var_700+8], rax
0x18005ed85  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005ed8a  test    al, al
0x18005ed8c  jz      loc_18005F488
0x18005ed92  mov     [rsp+7F0h+var_28], r12
0x18005ed9a  mov     r12d, esi
0x18005ed9d  mov     [rsp+7F0h+var_798], rsi
0x18005eda2  mov     [rbp+6F0h+var_718], 2
0x18005eda9  mov     [rsp+7F0h+var_7B8], esi
0x18005edad  cmp     [rbp+6F0h+var_6D0], esi
0x18005edb0  jle     loc_18005F480
0x18005edb6  mov     r11d, [rbp+6F0h+var_BC]
0x18005edbd  mov     [rsp+7F0h+var_20], rdi
0x18005edc5  mov     edi, [rbp+6F0h+var_6A0]
0x18005edc8  mov     [rsp+7F0h+var_30], r13
0x18005edd0  mov     [rsp+7F0h+var_38], r15
0x18005edd8  mov     r15d, [rbp+6F0h+var_6CC]
0x18005eddc  movaps  [rsp+7F0h+var_50], xmm6
0x18005ede4  movaps  [rsp+7F0h+var_60], xmm7
0x18005edec  movaps  [rsp+7F0h+var_70], xmm8
0x18005edf5  movss   xmm8, cs:__real@447fc000
0x18005edfe  movaps  [rsp+7F0h+var_80], xmm9
0x18005ee07  movups  xmm9, [rbp+6F0h+var_710]
0x18005ee0c  movaps  [rsp+7F0h+var_90], xmm10
0x18005ee15  movups  xmm10, [rbp+6F0h+var_700]
0x18005ee1a  nop     word ptr [rax+rax+00h]
0x18005ee20  inc     edi
0x18005ee22  mov     [rbp+6F0h+var_6A0], edi
0x18005ee25  cmp     edi, 1
0x18005ee28  jnz     loc_18005F41B
0x18005ee2e  mov     ecx, [r14+28h]
0x18005ee32  lea     r13, [rbx+r12]
0x18005ee36  mov     eax, [rbp+6F0h+var_69C]
0x18005ee39  test    eax, eax
0x18005ee3b  mov     r10d, [r14+1Ch]
0x18005ee3f  movsxd  r8, dword ptr [r14+34h]
0x18005ee43  cmovle  esi, eax
0x18005ee46  mov     eax, [r14+2Ch]
0x18005ee4a  cmp     r10d, eax
0x18005ee4d  movups  xmmword ptr [rbp+6F0h+var_6F0], xmm9
0x18005ee52  cmovl   r10d, eax
0x18005ee56  sub     r10d, eax
0x18005ee59  lea     r9d, [r8-1]
0x18005ee5d  mov     eax, [rbp+6F0h+var_698]
0x18005ee60  cmp     eax, ecx
0x18005ee62  cmovl   eax, ecx
0x18005ee65  sub     eax, ecx
0x18005ee67  cdq
0x18005ee68  idiv    dword ptr [r14+30h]
0x18005ee6c  movsxd  rcx, edx
0x18005ee6f  imul    rcx, r8
0x18005ee73  cmp     r10d, r9d
0x18005ee76  cmovle  r9d, r10d
0x18005ee7a  neg     esi
0x18005ee7c  movsxd  rax, r9d
0x18005ee7f  add     rcx, rax
0x18005ee82  mov     rax, [r14+38h]
0x18005ee86  lea     r14, [rax+rcx*2]
0x18005ee8a  mov     rcx, [rbp+6F0h+var_6F0+8]
0x18005ee8e  add     rcx, r12
0x18005ee91  movq    rax, xmm10
0x18005ee96  add     rax, r12
0x18005ee99  mov     [rsp+7F0h+var_7B0], rcx
0x18005ee9e  movsxd  r12, [rbp+6F0h+var_A4]
0x18005eea5  mov     [rsp+7F0h+var_7A8], rax
0x18005eeaa  cmp     r12, 1
0x18005eeae  jge     loc_18005EF40
0x18005eeb4  mov     rbx, rcx
0x18005eeb7  cmp     esi, r15d
0x18005eeba  jge     short loc_18005EF2E
0x18005eebc  lea     eax, ds:0[rsi*8]
0x18005eec3  movsxd  rdi, eax
0x18005eec6  lea     rcx, [rdi+rbx]
0x18005eeca  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005eecf  mov     rcx, [rsp+7F0h+var_7A8]
0x18005eed4  movaps  xmm7, xmm0
0x18005eed7  add     rcx, rdi
0x18005eeda  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005eedf  lea     rcx, [rdi+r13]
0x18005eee3  movaps  xmm6, xmm0
0x18005eee6  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005eeeb  addss   xmm0, xmm7
0x18005eeef  movaps  xmm1, xmm8
0x18005eef3  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005eefb  addss   xmm0, xmm6
0x18005eeff  movaps  xmm2, xmm8
0x18005ef03  mulss   xmm0, xmm1
0x18005ef07  minss   xmm2, xmm0
0x18005ef0b  xorps   xmm0, xmm0
0x18005ef0e  maxss   xmm0, xmm2
0x18005ef12  cvttss2si eax, xmm0
0x18005ef16  mov     [r14], ax
0x18005ef1a  add     r14, 2
0x18005ef1e  mov     eax, [rbp+r12*4+6F0h+var_718]
0x18005ef23  inc     r12
0x18005ef26  add     esi, eax
0x18005ef28  cmp     r12, 1
0x18005ef2c  jl      short loc_18005EEB7
0x18005ef2e  mov     r11d, [rbp+6F0h+var_BC]
0x18005ef35  mov     edi, [rbp+6F0h+var_6A0]
0x18005ef38  mov     r15d, [rbp+6F0h+var_6CC]
0x18005ef3c  mov     rbx, qword ptr [rbp+6F0h+var_710]
0x18005ef40  lea     edx, [r15-0Fh]
0x18005ef44  cmp     esi, edx
0x18005ef46  jge     loc_18005F352
0x18005ef4c  mov     r12, [rsp+7F0h+var_7B0]
0x18005ef51  lea     eax, ds:20h[rsi*8]
0x18005ef58  movsxd  rcx, eax
0x18005ef5b  sub     edx, esi
0x18005ef5d  mov     r15, [rsp+7F0h+var_7A8]
0x18005ef62  lea     eax, ds:10h[rsi*8]
0x18005ef69  cdqe
0x18005ef6b  sub     rax, rcx
0x18005ef6e  mov     [rsp+7F0h+var_790], rax
0x18005ef73  lea     rdi, [rcx+r13]
0x18005ef77  mov     rbx, [rsp+7F0h+var_790]
0x18005ef7c  sub     rax, r13
0x18005ef7f  mov     [rsp+7F0h+var_778], rax
0x18005ef84  lea     eax, ds:30h[rsi*8]
0x18005ef8b  cdqe
0x18005ef8d  sub     rax, rcx
0x18005ef90  mov     [rsp+7F0h+var_7C0], rdi
0x18005ef95  mov     [rsp+7F0h+var_788], rax
0x18005ef9a  sub     rax, r13
0x18005ef9d  mov     [rbp+6F0h+var_770], rax
0x18005efa1  lea     eax, ds:40h[rsi*8]
0x18005efa8  cdqe
0x18005efaa  sub     rax, rcx
0x18005efad  mov     [rbp+6F0h+var_760], rax
0x18005efb1  sub     rax, r13
0x18005efb4  mov     [rbp+6F0h+var_768], rax
0x18005efb8  lea     eax, ds:50h[rsi*8]
0x18005efbf  cdqe
0x18005efc1  sub     rax, rcx
0x18005efc4  mov     [rbp+6F0h+var_750], rax
0x18005efc8  sub     rax, r13
0x18005efcb  mov     [rbp+6F0h+var_758], rax
0x18005efcf  lea     eax, ds:60h[rsi*8]
0x18005efd6  cdqe
0x18005efd8  sub     rax, rcx
0x18005efdb  mov     [rbp+6F0h+var_740], rax
0x18005efdf  sub     rax, r13
0x18005efe2  mov     [rbp+6F0h+var_748], rax
0x18005efe6  lea     eax, ds:70h[rsi*8]
0x18005efed  cdqe
0x18005efef  sub     rax, rcx
0x18005eff2  mov     [rbp+6F0h+var_720], rax
0x18005eff6  sub     rax, r13
0x18005eff9  mov     [rbp+6F0h+var_738], rax
0x18005effd  lea     eax, ds:0[rsi*8]
0x18005f004  cdqe
0x18005f006  sub     rax, rcx
0x18005f009  mov     rcx, rax
0x18005f00c  mov     [rsp+7F0h+var_780], rax
0x18005f011  lea     eax, [rdx-1]
0x18005f014  sub     rcx, r13
0x18005f017  shr     eax, 4
0x18005f01a  inc     eax
0x18005f01c  mov     [rbp+6F0h+var_6F0], rcx
0x18005f020  mov     edx, eax
0x18005f022  shl     eax, 4
0x18005f025  add     eax, esi
0x18005f027  mov     [rsp+7F0h+var_7A0], rdx
0x18005f02c  mov     rsi, [rsp+7F0h+var_788]
0x18005f031  mov     [rsp+7F0h+var_7B4], eax
0x18005f035  nop     word ptr [rax+rax+00000000h]
0x18005f040  add     rdi, rcx
0x18005f043  lea     rcx, [rdi+r12]
0x18005f047  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f04c  lea     rcx, [rdi+r15]
0x18005f050  movaps  xmm7, xmm0
0x18005f053  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f058  mov     rcx, [rsp+7F0h+var_780]
0x18005f05d  movaps  xmm6, xmm0
0x18005f060  mov     rdi, [rsp+7F0h+var_7C0]
0x18005f065  add     rcx, rdi
0x18005f068  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f06d  add     rdi, [rsp+7F0h+var_778]
0x18005f072  addss   xmm0, xmm7
0x18005f076  movaps  xmm1, xmm8
0x18005f07a  movaps  xmm2, xmm8
0x18005f07e  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f086  lea     rcx, [rdi+r12]
0x18005f08a  addss   xmm0, xmm6
0x18005f08e  mulss   xmm0, xmm1
0x18005f092  minss   xmm2, xmm0
0x18005f096  xorps   xmm0, xmm0
0x18005f099  maxss   xmm0, xmm2
0x18005f09d  cvttss2si eax, xmm0
0x18005f0a1  mov     [r14], ax
0x18005f0a5  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f0aa  lea     rcx, [rdi+r15]
0x18005f0ae  movaps  xmm7, xmm0
0x18005f0b1  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f0b6  mov     rdi, [rsp+7F0h+var_7C0]
0x18005f0bb  movaps  xmm6, xmm0
0x18005f0be  lea     rcx, [rbx+rdi]
0x18005f0c2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f0c7  addss   xmm0, xmm7
0x18005f0cb  movaps  xmm1, xmm8
0x18005f0cf  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f0d7  sub     rdi, r13
0x18005f0da  lea     rcx, [r12+rdi]
0x18005f0de  addss   xmm0, xmm6
0x18005f0e2  movaps  xmm2, xmm8
0x18005f0e6  mulss   xmm0, xmm1
0x18005f0ea  minss   xmm2, xmm0
0x18005f0ee  xorps   xmm0, xmm0
0x18005f0f1  maxss   xmm0, xmm2
0x18005f0f5  cvttss2si eax, xmm0
0x18005f0f9  mov     [r14+2], ax
0x18005f0fe  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f103  lea     rcx, [r15+rdi]
0x18005f107  movaps  xmm7, xmm0
0x18005f10a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f10f  mov     rdi, [rsp+7F0h+var_7C0]
0x18005f114  movaps  xmm6, xmm0
0x18005f117  mov     rcx, rdi
0x18005f11a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f11f  add     rdi, [rbp+6F0h+var_770]
0x18005f123  addss   xmm0, xmm7
0x18005f127  movaps  xmm1, xmm8
0x18005f12b  movaps  xmm2, xmm8
0x18005f12f  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f137  lea     rcx, [rdi+r12]
0x18005f13b  addss   xmm0, xmm6
0x18005f13f  mulss   xmm0, xmm1
0x18005f143  minss   xmm2, xmm0
0x18005f147  xorps   xmm0, xmm0
0x18005f14a  maxss   xmm0, xmm2
0x18005f14e  cvttss2si eax, xmm0
0x18005f152  mov     [r14+4], ax
0x18005f157  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f15c  lea     rcx, [rdi+r15]
0x18005f160  movaps  xmm7, xmm0
0x18005f163  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f168  mov     rdi, [rsp+7F0h+var_7C0]
0x18005f16d  movaps  xmm6, xmm0
0x18005f170  lea     rcx, [rsi+rdi]
0x18005f174  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f179  addss   xmm0, xmm7
0x18005f17d  movaps  xmm1, xmm8
0x18005f181  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f189  addss   xmm0, xmm6
0x18005f18d  movaps  xmm2, xmm8
0x18005f191  mulss   xmm0, xmm1
0x18005f195  minss   xmm2, xmm0
0x18005f199  add     rdi, [rbp+6F0h+var_768]
0x18005f19d  xorps   xmm0, xmm0
0x18005f1a0  maxss   xmm0, xmm2
0x18005f1a4  lea     rcx, [rdi+r12]
0x18005f1a8  cvttss2si eax, xmm0
0x18005f1ac  mov     [r14+6], ax
0x18005f1b1  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f1b6  lea     rcx, [rdi+r15]
  ... truncated ...
```
