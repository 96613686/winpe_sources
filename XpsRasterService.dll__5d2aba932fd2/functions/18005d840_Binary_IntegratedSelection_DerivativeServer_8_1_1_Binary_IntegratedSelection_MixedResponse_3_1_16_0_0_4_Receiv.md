# Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005d840`
- end: `0x18005e002`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$07$00$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1986`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006aad0`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x18005d840`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
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
  __int64 v12; // r15
  int v13; // r11d
  int v14; // edi
  int v15; // r13d
  __int128 v16; // xmm9
  __int64 v17; // xmm10_8
  int v18; // ecx
  unsigned __int8 *v19; // r12
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
  __int64 v31; // r15
  unsigned __int8 *v32; // rbx
  __int64 v33; // rdi
  double v34; // xmm0_8
  float v35; // xmm7_4
  double v36; // xmm0_8
  float v37; // xmm6_4
  double v38; // xmm0_8
  int v39; // eax
  unsigned __int8 *v40; // r15
  __int64 v41; // rdx
  unsigned __int8 *v42; // rdi
  __int64 v43; // rbx
  unsigned __int8 *v44; // rcx
  unsigned int v45; // eax
  unsigned __int8 *v46; // rdi
  double v47; // xmm0_8
  float v48; // xmm7_4
  double v49; // xmm0_8
  float v50; // xmm6_4
  double v51; // xmm0_8
  double v52; // xmm0_8
  float v53; // xmm7_4
  double v54; // xmm0_8
  float v55; // xmm6_4
  double v56; // xmm0_8
  double v57; // xmm0_8
  float v58; // xmm7_4
  double v59; // xmm0_8
  float v60; // xmm6_4
  double v61; // xmm0_8
  double v62; // xmm0_8
  float v63; // xmm7_4
  double v64; // xmm0_8
  float v65; // xmm6_4
  double v66; // xmm0_8
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
  double v77; // xmm0_8
  float v78; // xmm7_4
  double v79; // xmm0_8
  float v80; // xmm6_4
  double v81; // xmm0_8
  double v82; // xmm0_8
  float v83; // xmm7_4
  double v84; // xmm0_8
  float v85; // xmm6_4
  double v86; // xmm0_8
  __int64 v87; // rdi
  unsigned __int8 *v88; // r15
  unsigned __int8 *v89; // r12
  __int64 v90; // rsi
  double v91; // xmm0_8
  float v92; // xmm7_4
  double v93; // xmm0_8
  float v94; // xmm6_4
  double v95; // xmm0_8
  __int64 v96; // rax
  unsigned __int8 *v98; // [rsp+30h] [rbp-D0h]
  int v99; // [rsp+38h] [rbp-C8h]
  int v100; // [rsp+3Ch] [rbp-C4h]
  unsigned __int8 *v101; // [rsp+40h] [rbp-C0h]
  __int64 v102; // [rsp+48h] [rbp-B8h]
  __int64 v103; // [rsp+50h] [rbp-B0h]
  __int64 v104; // [rsp+58h] [rbp-A8h]
  __int64 v105; // [rsp+68h] [rbp-98h]
  __int64 v106; // [rsp+70h] [rbp-90h]
  __int64 v107; // [rsp+78h] [rbp-88h]
  __int64 v108; // [rsp+80h] [rbp-80h]
  __int64 v109; // [rsp+88h] [rbp-78h]
  __int64 v110; // [rsp+90h] [rbp-70h]
  __int64 v111; // [rsp+98h] [rbp-68h]
  __int64 v112; // [rsp+A0h] [rbp-60h]
  __int64 v113; // [rsp+A8h] [rbp-58h]
  __int64 v114; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v115; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v118; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v119[2]; // [rsp+D8h] [rbp-28h]
  __int128 v120; // [rsp+E0h] [rbp-20h]
  __int64 v121; // [rsp+F0h] [rbp-10h]
  __int64 v122; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v123[2]; // [rsp+100h] [rbp+0h] BYREF
  int v124; // [rsp+120h] [rbp+20h] BYREF
  int v125; // [rsp+124h] [rbp+24h]
  __int64 v126; // [rsp+128h] [rbp+28h]
  char v127[32]; // [rsp+130h] [rbp+30h] BYREF
  int v128; // [rsp+150h] [rbp+50h]
  int v129; // [rsp+154h] [rbp+54h]
  int v130; // [rsp+158h] [rbp+58h]
  _DWORD v131[374]; // [rsp+15Ch] [rbp+5Ch]
  int v132; // [rsp+734h] [rbp+634h]
  int v133; // [rsp+73Ch] [rbp+63Ch]
  int v134; // [rsp+74Ch] [rbp+64Ch]

  *(_OWORD *)v123 = *a4;
  v5 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v124, 1, 1, (_DWORD)a3, (__int64)v123, a1 + 8);
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
  v10 = &v8[v126];
  *(_QWORD *)&v120 = &v8[v126];
  *((_QWORD *)&v120 + 1) = &v8[v126 + 2];
  v121 = (__int64)&v8[v126 + 4];
  v122 = (__int64)&v8[v126 + 6];
  LOBYTE(v11) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v127,
                  v8,
                  &v118,
                  v123);
  if ( (_BYTE)v11 )
  {
    v12 = 0;
    v104 = 0;
    v119[0] = 1;
    v99 = 0;
    if ( v124 > 0 )
    {
      v13 = v132;
      v14 = v128;
      v15 = v125;
      v16 = v120;
      v17 = v121;
      do
      {
        v128 = ++v14;
        if ( v14 == 1 )
        {
          v18 = *(_DWORD *)(v5 + 40);
          v19 = &v10[v12];
          v20 = *(_DWORD *)(v5 + 28);
          v21 = *(int *)(v5 + 52);
          if ( v129 <= 0 )
            v9 = v129;
          v22 = *(_DWORD *)(v5 + 44);
          *(_OWORD *)v123 = v16;
          if ( v20 < v22 )
            v20 = v22;
          v23 = v20 - v22;
          v24 = v21 - 1;
          v25 = v130;
          if ( v130 < v18 )
            v25 = v18;
          v26 = v21 * ((v25 - v18) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v24 )
            v24 = v23;
          v27 = -v9;
          v28 = (_WORD *)(*(_QWORD *)(v5 + 56) + 2 * (v24 + v26));
          v29 = &v123[1][v12];
          v30 = v12 + v17;
          v101 = &v123[1][v12];
          v31 = v134;
          v102 = v30;
          if ( v134 < 1LL )
          {
            v32 = v29;
            do
            {
              if ( v27 >= v15 )
                break;
              v33 = 8 * v27;
              v34 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v32[v33]);
              v35 = *(float *)&v34;
              v36 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v33 + v102);
              v37 = *(float *)&v36;
              v38 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v19[v33]);
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v38 + v35) + v37) * (float)(1023.0 / 3.0)));
              v39 = v119[v31++];
              v27 += v39;
            }
            while ( v31 < 1 );
            v13 = v132;
            v14 = v128;
            v15 = v125;
            v10 = (unsigned __int8 *)v120;
          }
          if ( v27 >= v15 - 7 )
          {
            v40 = v101;
          }
          else
          {
            v40 = v101;
            v41 = 8 * v27 + 16;
            v42 = &v19[v41];
            v43 = 8 * v27 + 8 - v41;
            v107 = v43 - (_QWORD)v19;
            v98 = &v19[v41];
            v105 = 8 * v27 + 24 - v41;
            v108 = v105 - (_QWORD)v19;
            v110 = 8 * v27 + 32 - v41;
            v109 = v110 - (_QWORD)v19;
            v112 = 8 * v27 + 40 - v41;
            v111 = v112 - (_QWORD)v19;
            v114 = 8 * v27 + 48 - v41;
            v113 = v114 - (_QWORD)v19;
            v118 = (unsigned __int8 *)(8 * v27 + 56 - v41);
            v115 = (unsigned __int8 *)(v118 - v19);
            v106 = 8 * v27 - v41;
            v44 = (unsigned __int8 *)(v106 - (_QWORD)v19);
            v45 = ((unsigned int)(v15 - 7 - v27 - 1) >> 3) + 1;
            v123[0] = (unsigned __int8 *)(v106 - (_QWORD)v19);
            v103 = v45;
            v100 = v27 + 8 * v45;
            do
            {
              v46 = &v42[(_QWORD)v44];
              v47 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v101[(_QWORD)v46]);
              v48 = *(float *)&v47;
              v49 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v46[v102]);
              v50 = *(float *)&v49;
              v51 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v106]);
              *v28 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v51 + v48) + v50) * (float)(1023.0 / 3.0)));
              v52 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v107 + (_QWORD)v101]);
              v53 = *(float *)&v52;
              v54 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v107 + v102]);
              v55 = *(float *)&v54;
              v56 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v43]);
              v28[1] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v56 + v53) + v55) * (float)(1023.0 / 3.0)));
              v57 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v101[v98 - v19]);
              v58 = *(float *)&v57;
              v59 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v98 - v19 + v102);
              v60 = *(float *)&v59;
              v61 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v98);
              v28[2] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v61 + v58) + v60) * (float)(1023.0 / 3.0)));
              v62 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v108 + (_QWORD)v101]);
              v63 = *(float *)&v62;
              v64 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v108 + v102]);
              v65 = *(float *)&v64;
              v66 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v105]);
              v28[3] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v66 + v63) + v65) * (float)(1023.0 / 3.0)));
              v67 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v109 + (_QWORD)v101]);
              v68 = *(float *)&v67;
              v69 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v109 + v102]);
              v70 = *(float *)&v69;
              v71 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v110]);
              v28[4] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v71 + v68) + v70) * (float)(1023.0 / 3.0)));
              v72 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v111 + (_QWORD)v101]);
              v73 = *(float *)&v72;
              v74 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v111 + v102]);
              v75 = *(float *)&v74;
              v76 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v112]);
              v28[5] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v76 + v73) + v75) * (float)(1023.0 / 3.0)));
              v77 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v113 + (_QWORD)v101]);
              v78 = *(float *)&v77;
              v79 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v113 + v102]);
              v80 = *(float *)&v79;
              v81 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[v114]);
              v28[6] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v81 + v78) + v80) * (float)(1023.0 / 3.0)));
              v82 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[(_QWORD)v115
                                                                                     + (unsigned __int64)v101]);
              v83 = *(float *)&v82;
              v84 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v98[(_QWORD)v115 + v102]);
              v85 = *(float *)&v84;
              v86 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v118[(_QWORD)v98]);
              v44 = v123[0];
              v42 = v98 + 64;
              v98 += 64;
              v28[7] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v86 + v83) + v85) * (float)(1023.0 / 3.0)));
              v28 += 8;
              --v103;
            }
            while ( v103 );
            v13 = v132;
            v14 = v128;
            v15 = v125;
            v10 = (unsigned __int8 *)v120;
            v27 = v100;
          }
          if ( v27 < v15 )
          {
            v87 = v102 + 8 * v27;
            v88 = &v40[-v102];
            v89 = &v19[-v102];
            v90 = (unsigned int)(v15 - v27);
            do
            {
              v91 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v88[v87]);
              v92 = *(float *)&v91;
              v93 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v87);
              v94 = *(float *)&v93;
              v95 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v87]);
              v87 += 8;
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v95 + v92) + v94) * (float)(1023.0 / 3.0)));
              --v90;
            }
            while ( v90 );
            v13 = v132;
            v14 = v128;
            v15 = v125;
          }
          v5 = a1;
          v9 = 0;
          v12 = v104;
          v96 = v13++;
          v14 -= v131[v96];
          if ( v13 >= v133 )
            v13 = 0;
          ++v130;
          v132 = v13;
        }
        v12 += *a3;
        v11 = v99 + 1;
        v104 = v12;
        v99 = v11;
      }
      while ( v11 < v124 );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18005d840  push    rbp
0x18005d842  push    rbx
0x18005d843  push    rsi
0x18005d844  push    r14
0x18005d846  lea     rbp, [rsp-6D8h]
0x18005d84e  sub     rsp, 7D8h
0x18005d855  mov     rax, cs:__security_cookie
0x18005d85c  xor     rax, rsp
0x18005d85f  mov     [rbp+6F0h+var_A0], rax
0x18005d866  movups  xmm0, xmmword ptr [r9]
0x18005d86a  lea     rax, [rcx+8]
0x18005d86e  mov     [rbp+6F0h+var_728], r8
0x18005d872  mov     [rsp+7F0h+var_7C8], rax
0x18005d877  mov     rbx, rdx
0x18005d87a  mov     edx, 1
0x18005d87f  mov     [rbp+6F0h+var_730], rcx
0x18005d883  lea     rax, [rbp+6F0h+var_6F0]
0x18005d887  movaps  xmmword ptr [rbp+6F0h+var_6F0], xmm0
0x18005d88b  mov     r14, rcx
0x18005d88e  mov     [rsp+7F0h+var_7D0], rax
0x18005d893  mov     r9, r8
0x18005d896  lea     rcx, [rbp+6F0h+var_6D0]
0x18005d89a  mov     r8d, edx
0x18005d89d  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005d8a2  mov     rcx, [rbx+8]
0x18005d8a6  lea     r9, [rbp+6F0h+var_6F0]; unsigned __int8 **
0x18005d8aa  mov     rax, [rbx+10h]
0x18005d8ae  lea     r8, [rbp+6F0h+var_720]; unsigned __int8 **
0x18005d8b2  mov     rdx, [rbx+18h]
0x18005d8b6  xor     esi, esi
0x18005d8b8  cmp     [rbx], rcx
0x18005d8bb  cmovbe  rcx, [rbx]
0x18005d8bf  mov     rbx, [rbp+6F0h+var_6C8]
0x18005d8c3  cmp     rcx, rax
0x18005d8c6  cmovbe  rax, rcx
0x18005d8ca  lea     rcx, [rbp+6F0h+var_6C0]; this
0x18005d8ce  cmp     rax, rdx
0x18005d8d1  cmovbe  rdx, rax; unsigned __int8 *
0x18005d8d5  add     rbx, rdx
0x18005d8d8  mov     qword ptr [rbp+6F0h+var_710], rbx
0x18005d8dc  lea     rax, [rbx+2]
0x18005d8e0  mov     qword ptr [rbp+6F0h+var_710+8], rax
0x18005d8e4  lea     rax, [rbx+4]
0x18005d8e8  mov     qword ptr [rbp+6F0h+var_700], rax
0x18005d8ec  lea     rax, [rbx+6]
0x18005d8f0  mov     qword ptr [rbp+6F0h+var_700+8], rax
0x18005d8f4  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005d8f9  test    al, al
0x18005d8fb  jz      loc_18005DFE6
0x18005d901  mov     [rsp+7F0h+var_38], r15
0x18005d909  mov     r15d, esi
0x18005d90c  mov     [rsp+7F0h+var_798], rsi
0x18005d911  mov     [rbp+6F0h+var_718], 1
0x18005d918  mov     [rsp+7F0h+var_7B8], esi
0x18005d91c  cmp     [rbp+6F0h+var_6D0], esi
0x18005d91f  jle     loc_18005DFDE
0x18005d925  mov     r11d, [rbp+6F0h+var_BC]
0x18005d92c  mov     [rsp+7F0h+var_20], rdi
0x18005d934  mov     edi, [rbp+6F0h+var_6A0]
0x18005d937  mov     [rsp+7F0h+var_28], r12
0x18005d93f  mov     [rsp+7F0h+var_30], r13
0x18005d947  mov     r13d, [rbp+6F0h+var_6CC]
0x18005d94b  movaps  [rsp+7F0h+var_50], xmm6
0x18005d953  movaps  [rsp+7F0h+var_60], xmm7
0x18005d95b  movaps  [rsp+7F0h+var_70], xmm8
0x18005d964  movss   xmm8, cs:__real@447fc000
0x18005d96d  movaps  [rsp+7F0h+var_80], xmm9
0x18005d976  movups  xmm9, [rbp+6F0h+var_710]
0x18005d97b  movaps  [rsp+7F0h+var_90], xmm10
0x18005d984  movups  xmm10, [rbp+6F0h+var_700]
0x18005d989  nop     dword ptr [rax+00000000h]
0x18005d990  inc     edi
0x18005d992  mov     [rbp+6F0h+var_6A0], edi
0x18005d995  cmp     edi, 1
0x18005d998  jnz     loc_18005DF79
0x18005d99e  mov     ecx, [r14+28h]
0x18005d9a2  lea     r12, [rbx+r15]
0x18005d9a6  mov     eax, [rbp+6F0h+var_69C]
0x18005d9a9  test    eax, eax
0x18005d9ab  mov     r10d, [r14+1Ch]
0x18005d9af  movsxd  r8, dword ptr [r14+34h]
0x18005d9b3  cmovle  esi, eax
0x18005d9b6  mov     eax, [r14+2Ch]
0x18005d9ba  cmp     r10d, eax
0x18005d9bd  movups  xmmword ptr [rbp+6F0h+var_6F0], xmm9
0x18005d9c2  cmovl   r10d, eax
0x18005d9c6  sub     r10d, eax
0x18005d9c9  lea     r9d, [r8-1]
0x18005d9cd  mov     eax, [rbp+6F0h+var_698]
0x18005d9d0  cmp     eax, ecx
0x18005d9d2  cmovl   eax, ecx
0x18005d9d5  sub     eax, ecx
0x18005d9d7  cdq
0x18005d9d8  idiv    dword ptr [r14+30h]
0x18005d9dc  movsxd  rcx, edx
0x18005d9df  imul    rcx, r8
0x18005d9e3  cmp     r10d, r9d
0x18005d9e6  cmovle  r9d, r10d
0x18005d9ea  neg     esi
0x18005d9ec  movsxd  rax, r9d
0x18005d9ef  add     rcx, rax
0x18005d9f2  mov     rax, [r14+38h]
0x18005d9f6  lea     r14, [rax+rcx*2]
0x18005d9fa  mov     rcx, [rbp+6F0h+var_6F0+8]
0x18005d9fe  add     rcx, r15
0x18005da01  movq    rax, xmm10
0x18005da06  add     rax, r15
0x18005da09  mov     [rsp+7F0h+var_7B0], rcx
0x18005da0e  movsxd  r15, [rbp+6F0h+var_A4]
0x18005da15  mov     [rsp+7F0h+var_7A8], rax
0x18005da1a  cmp     r15, 1
0x18005da1e  jge     loc_18005DAB0
0x18005da24  mov     rbx, rcx
0x18005da27  cmp     esi, r13d
0x18005da2a  jge     short loc_18005DA9E
0x18005da2c  lea     eax, ds:0[rsi*8]
0x18005da33  movsxd  rdi, eax
0x18005da36  lea     rcx, [rdi+rbx]
0x18005da3a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005da3f  mov     rcx, [rsp+7F0h+var_7A8]
0x18005da44  movaps  xmm7, xmm0
0x18005da47  add     rcx, rdi
0x18005da4a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005da4f  lea     rcx, [r12+rdi]
0x18005da53  movaps  xmm6, xmm0
0x18005da56  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005da5b  addss   xmm0, xmm7
0x18005da5f  movaps  xmm1, xmm8
0x18005da63  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005da6b  addss   xmm0, xmm6
0x18005da6f  movaps  xmm2, xmm8
0x18005da73  mulss   xmm0, xmm1
0x18005da77  minss   xmm2, xmm0
0x18005da7b  xorps   xmm0, xmm0
0x18005da7e  maxss   xmm0, xmm2
0x18005da82  cvttss2si eax, xmm0
0x18005da86  mov     [r14], ax
0x18005da8a  add     r14, 2
0x18005da8e  mov     eax, [rbp+r15*4+6F0h+var_718]
0x18005da93  inc     r15
0x18005da96  add     esi, eax
0x18005da98  cmp     r15, 1
0x18005da9c  jl      short loc_18005DA27
0x18005da9e  mov     r11d, [rbp+6F0h+var_BC]
0x18005daa5  mov     edi, [rbp+6F0h+var_6A0]
0x18005daa8  mov     r13d, [rbp+6F0h+var_6CC]
0x18005daac  mov     rbx, qword ptr [rbp+6F0h+var_710]
0x18005dab0  lea     r8d, [r13-7]
0x18005dab4  cmp     esi, r8d
0x18005dab7  jge     loc_18005DEB5
0x18005dabd  mov     r15, [rsp+7F0h+var_7B0]
0x18005dac2  lea     eax, ds:10h[rsi*8]
0x18005dac9  movsxd  rdx, eax
0x18005dacc  lea     ecx, ds:0[rsi*8]
0x18005dad3  mov     r13, [rsp+7F0h+var_7A8]
0x18005dad8  lea     eax, [rcx+8]
0x18005dadb  cdqe
0x18005dadd  sub     r8d, esi
0x18005dae0  sub     rax, rdx
0x18005dae3  mov     [rsp+7F0h+var_790], rax
0x18005dae8  lea     rdi, [r12+rdx]
0x18005daec  mov     rbx, [rsp+7F0h+var_790]
0x18005daf1  sub     rax, r12
0x18005daf4  mov     [rsp+7F0h+var_778], rax
0x18005daf9  lea     eax, ds:18h[rsi*8]
0x18005db00  cdqe
0x18005db02  sub     rax, rdx
0x18005db05  mov     [rsp+7F0h+var_7C0], rdi
0x18005db0a  mov     [rsp+7F0h+var_788], rax
0x18005db0f  sub     rax, r12
0x18005db12  mov     [rbp+6F0h+var_770], rax
0x18005db16  lea     eax, ds:20h[rsi*8]
0x18005db1d  cdqe
0x18005db1f  sub     rax, rdx
0x18005db22  mov     [rbp+6F0h+var_760], rax
0x18005db26  sub     rax, r12
0x18005db29  mov     [rbp+6F0h+var_768], rax
0x18005db2d  lea     eax, ds:28h[rsi*8]
0x18005db34  cdqe
0x18005db36  sub     rax, rdx
0x18005db39  mov     [rbp+6F0h+var_750], rax
0x18005db3d  sub     rax, r12
0x18005db40  mov     [rbp+6F0h+var_758], rax
0x18005db44  lea     eax, ds:30h[rsi*8]
0x18005db4b  cdqe
0x18005db4d  sub     rax, rdx
0x18005db50  mov     [rbp+6F0h+var_740], rax
0x18005db54  sub     rax, r12
0x18005db57  mov     [rbp+6F0h+var_748], rax
0x18005db5b  lea     eax, ds:38h[rsi*8]
0x18005db62  cdqe
0x18005db64  sub     rax, rdx
0x18005db67  mov     [rbp+6F0h+var_720], rax
0x18005db6b  sub     rax, r12
0x18005db6e  mov     [rbp+6F0h+var_738], rax
0x18005db72  movsxd  rax, ecx
0x18005db75  sub     rax, rdx
0x18005db78  mov     rcx, rax
0x18005db7b  mov     [rsp+7F0h+var_780], rax
0x18005db80  sub     rcx, r12
0x18005db83  lea     eax, [r8-1]
0x18005db87  shr     eax, 3
0x18005db8a  inc     eax
0x18005db8c  mov     [rbp+6F0h+var_6F0], rcx
0x18005db90  mov     edx, eax
0x18005db92  mov     [rsp+7F0h+var_7A0], rdx
0x18005db97  lea     esi, [rsi+rax*8]
0x18005db9a  mov     [rsp+7F0h+var_7B4], esi
0x18005db9e  mov     rsi, [rsp+7F0h+var_788]
0x18005dba3  add     rdi, rcx
0x18005dba6  lea     rcx, [rdi+r15]
0x18005dbaa  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dbaf  lea     rcx, [rdi+r13]
0x18005dbb3  movaps  xmm7, xmm0
0x18005dbb6  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dbbb  mov     rcx, [rsp+7F0h+var_780]
0x18005dbc0  movaps  xmm6, xmm0
0x18005dbc3  mov     rdi, [rsp+7F0h+var_7C0]
0x18005dbc8  add     rcx, rdi
0x18005dbcb  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dbd0  add     rdi, [rsp+7F0h+var_778]
0x18005dbd5  addss   xmm0, xmm7
0x18005dbd9  movaps  xmm1, xmm8
0x18005dbdd  movaps  xmm2, xmm8
0x18005dbe1  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005dbe9  lea     rcx, [rdi+r15]
0x18005dbed  addss   xmm0, xmm6
0x18005dbf1  mulss   xmm0, xmm1
0x18005dbf5  minss   xmm2, xmm0
0x18005dbf9  xorps   xmm0, xmm0
0x18005dbfc  maxss   xmm0, xmm2
0x18005dc00  cvttss2si eax, xmm0
0x18005dc04  mov     [r14], ax
0x18005dc08  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc0d  lea     rcx, [rdi+r13]
0x18005dc11  movaps  xmm7, xmm0
0x18005dc14  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc19  mov     rdi, [rsp+7F0h+var_7C0]
0x18005dc1e  movaps  xmm6, xmm0
0x18005dc21  lea     rcx, [rbx+rdi]
0x18005dc25  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc2a  addss   xmm0, xmm7
0x18005dc2e  movaps  xmm1, xmm8
0x18005dc32  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005dc3a  sub     rdi, r12
0x18005dc3d  lea     rcx, [r15+rdi]
0x18005dc41  addss   xmm0, xmm6
0x18005dc45  movaps  xmm2, xmm8
0x18005dc49  mulss   xmm0, xmm1
0x18005dc4d  minss   xmm2, xmm0
0x18005dc51  xorps   xmm0, xmm0
0x18005dc54  maxss   xmm0, xmm2
0x18005dc58  cvttss2si eax, xmm0
0x18005dc5c  mov     [r14+2], ax
0x18005dc61  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc66  lea     rcx, [rdi+r13]
0x18005dc6a  movaps  xmm7, xmm0
0x18005dc6d  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc72  mov     rdi, [rsp+7F0h+var_7C0]
0x18005dc77  movaps  xmm6, xmm0
0x18005dc7a  mov     rcx, rdi
0x18005dc7d  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dc82  add     rdi, [rbp+6F0h+var_770]
0x18005dc86  addss   xmm0, xmm7
0x18005dc8a  movaps  xmm1, xmm8
0x18005dc8e  movaps  xmm2, xmm8
0x18005dc92  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005dc9a  lea     rcx, [rdi+r15]
0x18005dc9e  addss   xmm0, xmm6
0x18005dca2  mulss   xmm0, xmm1
0x18005dca6  minss   xmm2, xmm0
0x18005dcaa  xorps   xmm0, xmm0
0x18005dcad  maxss   xmm0, xmm2
0x18005dcb1  cvttss2si eax, xmm0
0x18005dcb5  mov     [r14+4], ax
0x18005dcba  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dcbf  lea     rcx, [rdi+r13]
0x18005dcc3  movaps  xmm7, xmm0
0x18005dcc6  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dccb  mov     rdi, [rsp+7F0h+var_7C0]
0x18005dcd0  movaps  xmm6, xmm0
0x18005dcd3  lea     rcx, [rsi+rdi]
0x18005dcd7  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dcdc  addss   xmm0, xmm7
0x18005dce0  movaps  xmm1, xmm8
0x18005dce4  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005dcec  addss   xmm0, xmm6
0x18005dcf0  movaps  xmm2, xmm8
0x18005dcf4  mulss   xmm0, xmm1
0x18005dcf8  minss   xmm2, xmm0
0x18005dcfc  add     rdi, [rbp+6F0h+var_768]
0x18005dd00  xorps   xmm0, xmm0
0x18005dd03  maxss   xmm0, xmm2
0x18005dd07  lea     rcx, [rdi+r15]
0x18005dd0b  cvttss2si eax, xmm0
0x18005dd0f  mov     [r14+6], ax
0x18005dd14  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005dd19  lea     rcx, [rdi+r13]
0x18005dd1d  movaps  xmm7, xmm0
0x18005dd20  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
  ... truncated ...
```
