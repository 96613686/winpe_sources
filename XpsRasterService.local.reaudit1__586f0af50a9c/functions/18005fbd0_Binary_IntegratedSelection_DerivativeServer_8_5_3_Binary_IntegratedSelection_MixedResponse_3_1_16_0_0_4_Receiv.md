# Binary::IntegratedSelection::DerivativeServer<8,5,3,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,5,3,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005fbd0`
- end: `0x1800602e2`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$07$04$02$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$04$02V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1810`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006ab10`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x18005fbd0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,5,3,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,5,3,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int64 v5; // r15
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  int v9; // esi
  unsigned __int8 *v10; // rbx
  int v11; // eax
  __int64 v12; // r14
  int v13; // r11d
  int v14; // edi
  __int128 v15; // xmm9
  __int64 v16; // xmm10_8
  int v17; // ecx
  unsigned __int8 *v18; // r12
  int v19; // r10d
  __int64 v20; // r8
  int v21; // eax
  int v22; // r10d
  int v23; // r9d
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r13
  int v27; // esi
  _WORD *v28; // r15
  __int64 v29; // rax
  __int64 v30; // r14
  int v31; // eax
  __int64 v32; // rdi
  double v33; // xmm0_8
  float v34; // xmm7_4
  double v35; // xmm0_8
  float v36; // xmm6_4
  double v37; // xmm0_8
  __int64 v38; // rcx
  unsigned __int8 *v39; // rdi
  __int64 v40; // rbx
  unsigned __int8 *v41; // rcx
  unsigned int v42; // edx
  unsigned __int8 *v43; // rdi
  double v44; // xmm0_8
  float v45; // xmm7_4
  double v46; // xmm0_8
  float v47; // xmm6_4
  double v48; // xmm0_8
  double v49; // xmm0_8
  float v50; // xmm7_4
  double v51; // xmm0_8
  float v52; // xmm6_4
  double v53; // xmm0_8
  double v54; // xmm0_8
  float v55; // xmm7_4
  double v56; // xmm0_8
  float v57; // xmm6_4
  double v58; // xmm0_8
  double v59; // xmm0_8
  float v60; // xmm7_4
  double v61; // xmm0_8
  float v62; // xmm6_4
  double v63; // xmm0_8
  double v64; // xmm0_8
  float v65; // xmm7_4
  double v66; // xmm0_8
  float v67; // xmm6_4
  double v68; // xmm0_8
  double v69; // xmm0_8
  float v70; // xmm7_4
  double v71; // xmm0_8
  float v72; // xmm6_4
  double v73; // xmm0_8
  int v74; // r14d
  __int64 v75; // rdi
  double v76; // xmm0_8
  float v77; // xmm7_4
  double v78; // xmm0_8
  float v79; // xmm6_4
  double v80; // xmm0_8
  __int64 v81; // rax
  int v82; // r14d
  unsigned int v83; // edx
  __int64 v84; // rax
  int v86; // [rsp+30h] [rbp-D0h]
  int v87; // [rsp+30h] [rbp-D0h]
  int v88; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v89; // [rsp+38h] [rbp-C8h]
  int v90; // [rsp+40h] [rbp-C0h]
  __int64 v91; // [rsp+48h] [rbp-B8h]
  __int64 v92; // [rsp+50h] [rbp-B0h]
  __int64 v93; // [rsp+58h] [rbp-A8h]
  __int64 v94; // [rsp+68h] [rbp-98h]
  __int64 v95; // [rsp+70h] [rbp-90h]
  __int64 v96; // [rsp+78h] [rbp-88h]
  __int64 v97; // [rsp+80h] [rbp-80h]
  __int64 v98; // [rsp+88h] [rbp-78h]
  __int64 v99; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v100; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v103; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v104; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v105; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v106; // [rsp+D0h] [rbp-30h]
  __int64 v107; // [rsp+E0h] [rbp-20h]
  __int64 v108; // [rsp+E8h] [rbp-18h]
  __int128 v109; // [rsp+F0h] [rbp-10h]
  int v110; // [rsp+110h] [rbp+10h] BYREF
  int v111; // [rsp+114h] [rbp+14h]
  __int64 v112; // [rsp+118h] [rbp+18h]
  char v113[32]; // [rsp+120h] [rbp+20h] BYREF
  int v114; // [rsp+140h] [rbp+40h]
  int v115; // [rsp+144h] [rbp+44h]
  int v116; // [rsp+148h] [rbp+48h]
  _DWORD v117[374]; // [rsp+14Ch] [rbp+4Ch]
  int v118; // [rsp+724h] [rbp+624h]
  int v119; // [rsp+72Ch] [rbp+62Ch]
  int v120; // [rsp+73Ch] [rbp+63Ch]

  v5 = a1;
  v105 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v110, 5, 3, a3, &v105, (_DWORD *)(a1 + 8));
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
  v10 = &v8[v112];
  *(_QWORD *)&v106 = &v8[v112];
  *((_QWORD *)&v106 + 1) = &v8[v112 + 2];
  v107 = (__int64)&v8[v112 + 4];
  v108 = (__int64)&v8[v112 + 6];
  LOBYTE(v11) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v113,
                  v8,
                  &v103,
                  &v104);
  if ( (_BYTE)v11 )
  {
    v12 = 0;
    *(_QWORD *)&v105 = 0x200000002LL;
    v93 = 0;
    DWORD2(v105) = 1;
    v90 = 0;
    if ( v110 > 0 )
    {
      v13 = v118;
      v14 = v114;
      v15 = v106;
      v16 = v107;
      do
      {
        v114 = ++v14;
        if ( v14 == 1 )
        {
          v17 = *(_DWORD *)(v5 + 40);
          v18 = &v10[v12];
          v19 = *(_DWORD *)(v5 + 28);
          v20 = *(int *)(v5 + 52);
          if ( v115 <= 0 )
            v9 = v115;
          v21 = *(_DWORD *)(v5 + 44);
          v109 = v15;
          if ( v19 < v21 )
            v19 = v21;
          v22 = v19 - v21;
          v23 = v20 - 1;
          v24 = v116;
          if ( v116 < v17 )
            v24 = v17;
          v25 = v20 * ((v24 - v17) % *(_DWORD *)(v5 + 48));
          if ( v22 <= v23 )
            v23 = v22;
          v26 = v12 + *((_QWORD *)&v15 + 1);
          v27 = -v9;
          v28 = (_WORD *)(*(_QWORD *)(v5 + 56) + 2 * (v23 + v25));
          v29 = v12 + v16;
          v30 = v120;
          v91 = v29;
          v31 = v111;
          v86 = v111;
          if ( v120 < 3LL )
          {
            do
            {
              if ( v27 >= v31 )
                break;
              v32 = 8 * v27;
              v33 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v32 + v26);
              v34 = *(float *)&v33;
              v35 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v32 + v91);
              v36 = *(float *)&v35;
              v37 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v18[v32]);
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v37 + v34) + v36) * (float)(1023.0 / 3.0)));
              v27 += *((_DWORD *)&v105 + v30);
              v31 = v86;
              ++v30;
            }
            while ( v30 < 3 );
            v13 = v118;
            v14 = v114;
            v10 = (unsigned __int8 *)v106;
          }
          if ( v27 < v111 - 9 )
          {
            v38 = 8 * v27 + 32;
            v39 = &v18[v38];
            v40 = 8 * v27 + 16 - v38;
            v96 = v40 - (_QWORD)v18;
            v89 = &v18[v38];
            v94 = 8 * v27 + 40 - v38;
            v97 = v94 - (_QWORD)v18;
            v99 = 8 * v27 + 56 - v38;
            v98 = v99 - (_QWORD)v18;
            v103 = (unsigned __int8 *)(8 * v27 + 72 - v38);
            v100 = (unsigned __int8 *)(v103 - v18);
            v95 = 8 * v27 - v38;
            v41 = (unsigned __int8 *)(v95 - (_QWORD)v18);
            v104 = (unsigned __int8 *)(v95 - (_QWORD)v18);
            v42 = (v111 - 9 - v27 - 1) / 0xAu + 1;
            v92 = v42;
            v87 = v27 + 10 * v42;
            do
            {
              v43 = &v39[(_QWORD)v41];
              v44 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v43[v26]);
              v45 = *(float *)&v44;
              v46 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v43[v91]);
              v47 = *(float *)&v46;
              v48 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v95]);
              *v28 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v48 + v45) + v47) * (float)(1023.0 / 3.0)));
              v49 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v96 + v26]);
              v50 = *(float *)&v49;
              v51 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v96 + v91]);
              v52 = *(float *)&v51;
              v53 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v40]);
              v28[1] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v53 + v50) + v52) * (float)(1023.0 / 3.0)));
              v54 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v89 - v18 + v26);
              v55 = *(float *)&v54;
              v56 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v89 - v18 + v91);
              v57 = *(float *)&v56;
              v58 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v89);
              v28[2] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v58 + v55) + v57) * (float)(1023.0 / 3.0)));
              v59 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v97 + v26]);
              v60 = *(float *)&v59;
              v61 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v97 + v91]);
              v62 = *(float *)&v61;
              v63 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v94]);
              v28[3] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v63 + v60) + v62) * (float)(1023.0 / 3.0)));
              v64 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v98 + v26]);
              v65 = *(float *)&v64;
              v66 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v98 + v91]);
              v67 = *(float *)&v66;
              v68 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[v99]);
              v28[4] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v68 + v65) + v67) * (float)(1023.0 / 3.0)));
              v69 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[(_QWORD)v100 + v26]);
              v70 = *(float *)&v69;
              v71 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v89[(_QWORD)v100 + v91]);
              v72 = *(float *)&v71;
              v73 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v103[(_QWORD)v89]);
              v41 = v104;
              v39 = v89 + 80;
              v89 += 80;
              v28[5] = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v73 + v70) + v72) * (float)(1023.0 / 3.0)));
              v28 += 6;
              --v92;
            }
            while ( v92 );
            v13 = v118;
            v14 = v114;
            v10 = (unsigned __int8 *)v106;
            v27 = v87;
          }
          v74 = 0;
          v88 = v111;
          if ( v27 < v111 )
          {
            do
            {
              v75 = 8 * v27;
              v76 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v75 + v26);
              v77 = *(float *)&v76;
              v78 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v75 + v91);
              v79 = *(float *)&v78;
              v80 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v18[v75]);
              *v28++ = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v80 + v77) + v79) * (float)(1023.0 / 3.0)));
              v81 = v74;
              v82 = v74 + 1;
              v27 += *((_DWORD *)&v105 + v81);
              v83 = ((unsigned int)(((unsigned __int64)(1431655765LL * v82) >> 32) - v82) >> 31)
                  + ((int)(((unsigned __int64)(1431655765LL * v82) >> 32) - v82) >> 1);
              v74 = v82 + v83 + 2 * v83;
            }
            while ( v27 < v88 );
            v13 = v118;
            v14 = v114;
            v10 = (unsigned __int8 *)v106;
          }
          v12 = v93;
          v9 = 0;
          v5 = a1;
          v84 = v13++;
          v14 -= v117[v84];
          if ( v13 >= v119 )
            v13 = 0;
          ++v116;
          v118 = v13;
        }
        v12 += *a3;
        v11 = v90 + 1;
        v93 = v12;
        v90 = v11;
      }
      while ( v11 < v110 );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18005fbd0  push    rbp
0x18005fbd2  push    rbx
0x18005fbd3  push    rsi
0x18005fbd4  push    r15
0x18005fbd6  lea     rbp, [rsp-6C8h]
0x18005fbde  sub     rsp, 7C8h
0x18005fbe5  mov     rax, cs:__security_cookie
0x18005fbec  xor     rax, rsp
0x18005fbef  mov     [rbp+6E0h+var_A0], rax
0x18005fbf6  movups  xmm0, xmmword ptr [r9]
0x18005fbfa  lea     rax, [rcx+8]
0x18005fbfe  mov     [rbp+6E0h+var_738], r8
0x18005fc02  mov     [rsp+7E0h+var_7B8], rax
0x18005fc07  mov     rbx, rdx
0x18005fc0a  mov     edx, 5
0x18005fc0f  mov     [rbp+6E0h+var_740], rcx
0x18005fc13  mov     r15, rcx
0x18005fc16  movaps  [rbp+6E0h+var_720], xmm0
0x18005fc1a  lea     rax, [rbp+6E0h+var_720]
0x18005fc1e  mov     r9, r8
0x18005fc21  lea     rcx, [rbp+6E0h+var_6D0]
0x18005fc25  mov     [rsp+7E0h+var_7C0], rax
0x18005fc2a  lea     r8d, [rdx-2]
0x18005fc2e  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005fc33  mov     rcx, [rbx+8]
0x18005fc37  lea     r9, [rbp+6E0h+var_728]; unsigned __int8 **
0x18005fc3b  mov     rax, [rbx+10h]
0x18005fc3f  lea     r8, [rbp+6E0h+var_730]; unsigned __int8 **
0x18005fc43  mov     rdx, [rbx+18h]
0x18005fc47  xor     esi, esi
0x18005fc49  cmp     [rbx], rcx
0x18005fc4c  cmovbe  rcx, [rbx]
0x18005fc50  mov     rbx, [rbp+6E0h+var_6C8]
0x18005fc54  cmp     rcx, rax
0x18005fc57  cmovbe  rax, rcx
0x18005fc5b  lea     rcx, [rbp+6E0h+var_6C0]; this
0x18005fc5f  cmp     rax, rdx
0x18005fc62  cmovbe  rdx, rax; unsigned __int8 *
0x18005fc66  add     rbx, rdx
0x18005fc69  mov     qword ptr [rbp+6E0h+var_710], rbx
0x18005fc6d  lea     rax, [rbx+2]
0x18005fc71  mov     qword ptr [rbp+6E0h+var_710+8], rax
0x18005fc75  lea     rax, [rbx+4]
0x18005fc79  mov     qword ptr [rbp+6E0h+var_700], rax
0x18005fc7d  lea     rax, [rbx+6]
0x18005fc81  mov     qword ptr [rbp+6E0h+var_700+8], rax
0x18005fc85  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005fc8a  test    al, al
0x18005fc8c  jz      loc_1800602C6
0x18005fc92  mov     dword ptr [rbp+6E0h+var_720+4], 2
0x18005fc99  mov     dword ptr [rbp+6E0h+var_720], 2
0x18005fca0  movsd   xmm0, qword ptr [rbp+6E0h+var_720]
0x18005fca5  mov     [rsp+7E0h+var_38], r14
0x18005fcad  mov     r14d, esi
0x18005fcb0  movsd   qword ptr [rbp+6E0h+var_720], xmm0
0x18005fcb5  mov     [rsp+7E0h+var_788], rsi
0x18005fcba  mov     dword ptr [rbp+6E0h+var_720+8], 1
0x18005fcc1  mov     [rsp+7E0h+var_7A0], esi
0x18005fcc5  cmp     [rbp+6E0h+var_6D0], esi
0x18005fcc8  jle     loc_1800602BE
0x18005fcce  mov     r11d, [rbp+6E0h+var_BC]
0x18005fcd5  mov     [rsp+7E0h+var_20], rdi
0x18005fcdd  mov     edi, [rbp+6E0h+var_6A0]
0x18005fce0  mov     [rsp+7E0h+var_28], r12
0x18005fce8  mov     [rsp+7E0h+var_30], r13
0x18005fcf0  movaps  [rsp+7E0h+var_50], xmm6
0x18005fcf8  movaps  [rsp+7E0h+var_60], xmm7
0x18005fd00  movaps  [rsp+7E0h+var_70], xmm8
0x18005fd09  movss   xmm8, cs:__real@447fc000
0x18005fd12  movaps  [rsp+7E0h+var_80], xmm9
0x18005fd1b  movups  xmm9, [rbp+6E0h+var_710]
0x18005fd20  movaps  [rsp+7E0h+var_90], xmm10
0x18005fd29  movups  xmm10, [rbp+6E0h+var_700]
0x18005fd2e  xchg    ax, ax
0x18005fd30  inc     edi
0x18005fd32  mov     [rbp+6E0h+var_6A0], edi
0x18005fd35  cmp     edi, 1
0x18005fd38  jnz     loc_180060259
0x18005fd3e  mov     ecx, [r15+28h]
0x18005fd42  lea     r12, [rbx+r14]
0x18005fd46  mov     eax, [rbp+6E0h+var_69C]
0x18005fd49  test    eax, eax
0x18005fd4b  mov     r10d, [r15+1Ch]
0x18005fd4f  movsxd  r8, dword ptr [r15+34h]
0x18005fd53  cmovle  esi, eax
0x18005fd56  mov     eax, [r15+2Ch]
0x18005fd5a  cmp     r10d, eax
0x18005fd5d  movups  [rbp+6E0h+var_6F0], xmm9
0x18005fd62  mov     r13, qword ptr [rbp+6E0h+var_6F0+8]
0x18005fd66  cmovl   r10d, eax
0x18005fd6a  sub     r10d, eax
0x18005fd6d  lea     r9d, [r8-1]
0x18005fd71  mov     eax, [rbp+6E0h+var_698]
0x18005fd74  cmp     eax, ecx
0x18005fd76  cmovl   eax, ecx
0x18005fd79  sub     eax, ecx
0x18005fd7b  cdq
0x18005fd7c  idiv    dword ptr [r15+30h]
0x18005fd80  movsxd  rcx, edx
0x18005fd83  imul    rcx, r8
0x18005fd87  cmp     r10d, r9d
0x18005fd8a  cmovle  r9d, r10d
0x18005fd8e  add     r13, r14
0x18005fd91  movsxd  rax, r9d
0x18005fd94  neg     esi
0x18005fd96  add     rcx, rax
0x18005fd99  mov     rax, [r15+38h]
0x18005fd9d  lea     r15, [rax+rcx*2]
0x18005fda1  movq    rax, xmm10
0x18005fda6  add     rax, r14
0x18005fda9  movsxd  r14, [rbp+6E0h+var_A4]
0x18005fdb0  mov     [rsp+7E0h+var_798], rax
0x18005fdb5  mov     eax, [rbp+6E0h+var_6CC]
0x18005fdb8  mov     [rsp+7E0h+var_7B0], eax
0x18005fdbc  cmp     r14, 3
0x18005fdc0  jge     loc_18005FE54
0x18005fdc6  mov     rbx, [rsp+7E0h+var_798]
0x18005fdcb  nop     dword ptr [rax+rax+00h]
0x18005fdd0  cmp     esi, eax
0x18005fdd2  jge     short loc_18005FE46
0x18005fdd4  lea     eax, ds:0[rsi*8]
0x18005fddb  movsxd  rdi, eax
0x18005fdde  lea     rcx, [rdi+r13]
0x18005fde2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005fde7  lea     rcx, [rdi+rbx]
0x18005fdeb  movaps  xmm7, xmm0
0x18005fdee  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005fdf3  lea     rcx, [r12+rdi]
0x18005fdf7  movaps  xmm6, xmm0
0x18005fdfa  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005fdff  addss   xmm0, xmm7
0x18005fe03  movaps  xmm1, xmm8
0x18005fe07  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005fe0f  addss   xmm0, xmm6
0x18005fe13  movaps  xmm2, xmm8
0x18005fe17  mulss   xmm0, xmm1
0x18005fe1b  minss   xmm2, xmm0
0x18005fe1f  xorps   xmm0, xmm0
0x18005fe22  maxss   xmm0, xmm2
0x18005fe26  cvttss2si eax, xmm0
0x18005fe2a  mov     [r15], ax
0x18005fe2e  add     r15, 2
0x18005fe32  mov     eax, dword ptr [rbp+r14*4+6E0h+var_720]
0x18005fe37  add     esi, eax
0x18005fe39  mov     eax, [rsp+7E0h+var_7B0]
0x18005fe3d  inc     r14
0x18005fe40  cmp     r14, 3
0x18005fe44  jl      short loc_18005FDD0
0x18005fe46  mov     r11d, [rbp+6E0h+var_BC]
0x18005fe4d  mov     edi, [rbp+6E0h+var_6A0]
0x18005fe50  mov     rbx, qword ptr [rbp+6E0h+var_710]
0x18005fe54  mov     edx, [rbp+6E0h+var_6CC]
0x18005fe57  add     edx, 0FFFFFFF7h
0x18005fe5a  cmp     esi, edx
0x18005fe5c  jge     loc_180060172
0x18005fe62  mov     r14, [rsp+7E0h+var_798]
0x18005fe67  lea     eax, ds:20h[rsi*8]
0x18005fe6e  movsxd  rcx, eax
0x18005fe71  sub     edx, esi
0x18005fe73  lea     eax, ds:10h[rsi*8]
0x18005fe7a  dec     edx
0x18005fe7c  cdqe
0x18005fe7e  sub     rax, rcx
0x18005fe81  mov     [rsp+7E0h+var_780], rax
0x18005fe86  lea     rdi, [r12+rcx]
0x18005fe8a  mov     rbx, [rsp+7E0h+var_780]
0x18005fe8f  sub     rax, r12
0x18005fe92  mov     [rsp+7E0h+var_768], rax
0x18005fe97  lea     eax, ds:28h[rsi*8]
0x18005fe9e  cdqe
0x18005fea0  sub     rax, rcx
0x18005fea3  mov     [rsp+7E0h+var_7A8], rdi
0x18005fea8  mov     [rsp+7E0h+var_778], rax
0x18005fead  sub     rax, r12
0x18005feb0  mov     [rbp+6E0h+var_760], rax
0x18005feb4  lea     eax, ds:38h[rsi*8]
0x18005febb  cdqe
0x18005febd  sub     rax, rcx
0x18005fec0  mov     [rbp+6E0h+var_750], rax
0x18005fec4  sub     rax, r12
0x18005fec7  mov     [rbp+6E0h+var_758], rax
0x18005fecb  lea     eax, ds:48h[rsi*8]
0x18005fed2  cdqe
0x18005fed4  sub     rax, rcx
0x18005fed7  mov     [rbp+6E0h+var_730], rax
0x18005fedb  sub     rax, r12
0x18005fede  mov     [rbp+6E0h+var_748], rax
0x18005fee2  lea     eax, ds:0[rsi*8]
0x18005fee9  cdqe
0x18005feeb  sub     rax, rcx
0x18005feee  mov     rcx, rax
0x18005fef1  mov     [rsp+7E0h+var_770], rax
0x18005fef6  mov     eax, 0CCCCCCCDh
0x18005fefb  sub     rcx, r12
0x18005fefe  mul     edx
0x18005ff00  mov     [rbp+6E0h+var_728], rcx
0x18005ff04  shr     edx, 3
0x18005ff07  inc     edx
0x18005ff09  mov     eax, edx
0x18005ff0b  mov     [rsp+7E0h+var_790], rax
0x18005ff10  lea     eax, [rdx+rdx*4]
0x18005ff13  lea     esi, [rsi+rax*2]
0x18005ff16  mov     [rsp+7E0h+var_7B0], esi
0x18005ff1a  mov     rsi, [rsp+7E0h+var_778]
0x18005ff1f  nop
0x18005ff20  add     rdi, rcx
0x18005ff23  lea     rcx, [rdi+r13]
0x18005ff27  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ff2c  lea     rcx, [rdi+r14]
0x18005ff30  movaps  xmm7, xmm0
0x18005ff33  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ff38  mov     rcx, [rsp+7E0h+var_770]
0x18005ff3d  movaps  xmm6, xmm0
0x18005ff40  mov     rdi, [rsp+7E0h+var_7A8]
0x18005ff45  add     rcx, rdi
0x18005ff48  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ff4d  add     rdi, [rsp+7E0h+var_768]
0x18005ff52  addss   xmm0, xmm7
0x18005ff56  movaps  xmm1, xmm8
0x18005ff5a  movaps  xmm2, xmm8
0x18005ff5e  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005ff66  lea     rcx, [rdi+r13]
0x18005ff6a  addss   xmm0, xmm6
0x18005ff6e  mulss   xmm0, xmm1
0x18005ff72  minss   xmm2, xmm0
0x18005ff76  xorps   xmm0, xmm0
0x18005ff79  maxss   xmm0, xmm2
0x18005ff7d  cvttss2si eax, xmm0
0x18005ff81  mov     [r15], ax
0x18005ff85  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ff8a  lea     rcx, [rdi+r14]
0x18005ff8e  movaps  xmm7, xmm0
0x18005ff91  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ff96  mov     rdi, [rsp+7E0h+var_7A8]
0x18005ff9b  movaps  xmm6, xmm0
0x18005ff9e  lea     rcx, [rbx+rdi]
0x18005ffa2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ffa7  addss   xmm0, xmm7
0x18005ffab  movaps  xmm1, xmm8
0x18005ffaf  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005ffb7  sub     rdi, r12
0x18005ffba  lea     rcx, [rdi+r13]
0x18005ffbe  addss   xmm0, xmm6
0x18005ffc2  movaps  xmm2, xmm8
0x18005ffc6  mulss   xmm0, xmm1
0x18005ffca  minss   xmm2, xmm0
0x18005ffce  xorps   xmm0, xmm0
0x18005ffd1  maxss   xmm0, xmm2
0x18005ffd5  cvttss2si eax, xmm0
0x18005ffd9  mov     [r15+2], ax
0x18005ffde  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ffe3  lea     rcx, [rdi+r14]
0x18005ffe7  movaps  xmm7, xmm0
0x18005ffea  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ffef  mov     rdi, [rsp+7E0h+var_7A8]
0x18005fff4  movaps  xmm6, xmm0
0x18005fff7  mov     rcx, rdi
0x18005fffa  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005ffff  add     rdi, [rbp+6E0h+var_760]
0x180060003  addss   xmm0, xmm7
0x180060007  movaps  xmm1, xmm8
0x18006000b  movaps  xmm2, xmm8
0x18006000f  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180060017  lea     rcx, [rdi+r13]
0x18006001b  addss   xmm0, xmm6
0x18006001f  mulss   xmm0, xmm1
0x180060023  minss   xmm2, xmm0
0x180060027  xorps   xmm0, xmm0
0x18006002a  maxss   xmm0, xmm2
0x18006002e  cvttss2si eax, xmm0
0x180060032  mov     [r15+4], ax
0x180060037  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18006003c  lea     rcx, [rdi+r14]
0x180060040  movaps  xmm7, xmm0
0x180060043  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180060048  mov     rdi, [rsp+7E0h+var_7A8]
0x18006004d  movaps  xmm6, xmm0
0x180060050  lea     rcx, [rsi+rdi]
0x180060054  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180060059  addss   xmm0, xmm7
0x18006005d  movaps  xmm1, xmm8
0x180060061  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180060069  addss   xmm0, xmm6
0x18006006d  movaps  xmm2, xmm8
0x180060071  mulss   xmm0, xmm1
0x180060075  minss   xmm2, xmm0
0x180060079  add     rdi, [rbp+6E0h+var_758]
0x18006007d  xorps   xmm0, xmm0
0x180060080  maxss   xmm0, xmm2
0x180060084  lea     rcx, [rdi+r13]
0x180060088  cvttss2si eax, xmm0
0x18006008c  mov     [r15+6], ax
0x180060091  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180060096  lea     rcx, [rdi+r14]
0x18006009a  movaps  xmm7, xmm0
0x18006009d  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x1800600a2  mov     rcx, [rbp+6E0h+var_750]
0x1800600a6  movaps  xmm6, xmm0
0x1800600a9  mov     rdi, [rsp+7E0h+var_7A8]
0x1800600ae  add     rcx, rdi
  ... truncated ...
```
