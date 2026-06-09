# Binary::IntegratedSelection::DerivativeServer<8,4,3,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,4,3,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18005f4b0`
- end: `0x18005fbc2`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$00$07$03$02$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$03$02V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1810`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, __int128 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006ab00`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x18005f4b0`
- `0x180067110`
- `0x1800963a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,4,3,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<1,8,4,3,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
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
  unsigned int v42; // eax
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
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v110, 4, 3, (_DWORD)a3, (__int64)&v105, a1 + 8);
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
    *(_QWORD *)&v105 = 0x100000002LL;
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
          if ( v27 < v111 - 7 )
          {
            v38 = 8 * v27 + 24;
            v39 = &v18[v38];
            v40 = 8 * v27 + 16 - v38;
            v96 = v40 - (_QWORD)v18;
            v89 = &v18[v38];
            v94 = 8 * v27 + 32 - v38;
            v97 = v94 - (_QWORD)v18;
            v99 = 8 * v27 + 48 - v38;
            v98 = v99 - (_QWORD)v18;
            v103 = (unsigned __int8 *)(8 * v27 + 56 - v38);
            v100 = (unsigned __int8 *)(v103 - v18);
            v95 = 8 * v27 - v38;
            v41 = (unsigned __int8 *)(v95 - (_QWORD)v18);
            v42 = ((unsigned int)(v111 - 7 - v27 - 1) >> 3) + 1;
            v104 = (unsigned __int8 *)(v95 - (_QWORD)v18);
            v92 = v42;
            v87 = v27 + 8 * v42;
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
              v39 = v89 + 64;
              v89 += 64;
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
0x18005f4b0  push    rbp
0x18005f4b2  push    rbx
0x18005f4b3  push    rsi
0x18005f4b4  push    r15
0x18005f4b6  lea     rbp, [rsp-6C8h]
0x18005f4be  sub     rsp, 7C8h
0x18005f4c5  mov     rax, cs:__security_cookie
0x18005f4cc  xor     rax, rsp
0x18005f4cf  mov     [rbp+6E0h+var_A0], rax
0x18005f4d6  movups  xmm0, xmmword ptr [r9]
0x18005f4da  lea     rax, [rcx+8]
0x18005f4de  mov     [rbp+6E0h+var_738], r8
0x18005f4e2  mov     [rsp+7E0h+var_7B8], rax
0x18005f4e7  mov     rbx, rdx
0x18005f4ea  mov     edx, 4
0x18005f4ef  mov     [rbp+6E0h+var_740], rcx
0x18005f4f3  mov     r15, rcx
0x18005f4f6  movaps  [rbp+6E0h+var_720], xmm0
0x18005f4fa  lea     rax, [rbp+6E0h+var_720]
0x18005f4fe  mov     r9, r8
0x18005f501  lea     rcx, [rbp+6E0h+var_6D0]
0x18005f505  mov     [rsp+7E0h+var_7C0], rax
0x18005f50a  lea     r8d, [rdx-1]
0x18005f50e  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18005f513  mov     rcx, [rbx+8]
0x18005f517  lea     r9, [rbp+6E0h+var_728]; unsigned __int8 **
0x18005f51b  mov     rax, [rbx+10h]
0x18005f51f  lea     r8, [rbp+6E0h+var_730]; unsigned __int8 **
0x18005f523  mov     rdx, [rbx+18h]
0x18005f527  xor     esi, esi
0x18005f529  cmp     [rbx], rcx
0x18005f52c  cmovbe  rcx, [rbx]
0x18005f530  mov     rbx, [rbp+6E0h+var_6C8]
0x18005f534  cmp     rcx, rax
0x18005f537  cmovbe  rax, rcx
0x18005f53b  lea     rcx, [rbp+6E0h+var_6C0]; this
0x18005f53f  cmp     rax, rdx
0x18005f542  cmovbe  rdx, rax; unsigned __int8 *
0x18005f546  add     rbx, rdx
0x18005f549  mov     qword ptr [rbp+6E0h+var_710], rbx
0x18005f54d  lea     rax, [rbx+2]
0x18005f551  mov     qword ptr [rbp+6E0h+var_710+8], rax
0x18005f555  lea     rax, [rbx+4]
0x18005f559  mov     qword ptr [rbp+6E0h+var_700], rax
0x18005f55d  lea     rax, [rbx+6]
0x18005f561  mov     qword ptr [rbp+6E0h+var_700+8], rax
0x18005f565  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18005f56a  test    al, al
0x18005f56c  jz      loc_18005FBA6
0x18005f572  mov     dword ptr [rbp+6E0h+var_720+4], 1
0x18005f579  mov     dword ptr [rbp+6E0h+var_720], 2
0x18005f580  movsd   xmm0, qword ptr [rbp+6E0h+var_720]
0x18005f585  mov     [rsp+7E0h+var_38], r14
0x18005f58d  mov     r14d, esi
0x18005f590  movsd   qword ptr [rbp+6E0h+var_720], xmm0
0x18005f595  mov     [rsp+7E0h+var_788], rsi
0x18005f59a  mov     dword ptr [rbp+6E0h+var_720+8], 1
0x18005f5a1  mov     [rsp+7E0h+var_7A0], esi
0x18005f5a5  cmp     [rbp+6E0h+var_6D0], esi
0x18005f5a8  jle     loc_18005FB9E
0x18005f5ae  mov     r11d, [rbp+6E0h+var_BC]
0x18005f5b5  mov     [rsp+7E0h+var_20], rdi
0x18005f5bd  mov     edi, [rbp+6E0h+var_6A0]
0x18005f5c0  mov     [rsp+7E0h+var_28], r12
0x18005f5c8  mov     [rsp+7E0h+var_30], r13
0x18005f5d0  movaps  [rsp+7E0h+var_50], xmm6
0x18005f5d8  movaps  [rsp+7E0h+var_60], xmm7
0x18005f5e0  movaps  [rsp+7E0h+var_70], xmm8
0x18005f5e9  movss   xmm8, cs:__real@447fc000
0x18005f5f2  movaps  [rsp+7E0h+var_80], xmm9
0x18005f5fb  movups  xmm9, [rbp+6E0h+var_710]
0x18005f600  movaps  [rsp+7E0h+var_90], xmm10
0x18005f609  movups  xmm10, [rbp+6E0h+var_700]
0x18005f60e  xchg    ax, ax
0x18005f610  inc     edi
0x18005f612  mov     [rbp+6E0h+var_6A0], edi
0x18005f615  cmp     edi, 1
0x18005f618  jnz     loc_18005FB39
0x18005f61e  mov     ecx, [r15+28h]
0x18005f622  lea     r12, [rbx+r14]
0x18005f626  mov     eax, [rbp+6E0h+var_69C]
0x18005f629  test    eax, eax
0x18005f62b  mov     r10d, [r15+1Ch]
0x18005f62f  movsxd  r8, dword ptr [r15+34h]
0x18005f633  cmovle  esi, eax
0x18005f636  mov     eax, [r15+2Ch]
0x18005f63a  cmp     r10d, eax
0x18005f63d  movups  [rbp+6E0h+var_6F0], xmm9
0x18005f642  mov     r13, qword ptr [rbp+6E0h+var_6F0+8]
0x18005f646  cmovl   r10d, eax
0x18005f64a  sub     r10d, eax
0x18005f64d  lea     r9d, [r8-1]
0x18005f651  mov     eax, [rbp+6E0h+var_698]
0x18005f654  cmp     eax, ecx
0x18005f656  cmovl   eax, ecx
0x18005f659  sub     eax, ecx
0x18005f65b  cdq
0x18005f65c  idiv    dword ptr [r15+30h]
0x18005f660  movsxd  rcx, edx
0x18005f663  imul    rcx, r8
0x18005f667  cmp     r10d, r9d
0x18005f66a  cmovle  r9d, r10d
0x18005f66e  add     r13, r14
0x18005f671  movsxd  rax, r9d
0x18005f674  neg     esi
0x18005f676  add     rcx, rax
0x18005f679  mov     rax, [r15+38h]
0x18005f67d  lea     r15, [rax+rcx*2]
0x18005f681  movq    rax, xmm10
0x18005f686  add     rax, r14
0x18005f689  movsxd  r14, [rbp+6E0h+var_A4]
0x18005f690  mov     [rsp+7E0h+var_798], rax
0x18005f695  mov     eax, [rbp+6E0h+var_6CC]
0x18005f698  mov     [rsp+7E0h+var_7B0], eax
0x18005f69c  cmp     r14, 3
0x18005f6a0  jge     loc_18005F734
0x18005f6a6  mov     rbx, [rsp+7E0h+var_798]
0x18005f6ab  nop     dword ptr [rax+rax+00h]
0x18005f6b0  cmp     esi, eax
0x18005f6b2  jge     short loc_18005F726
0x18005f6b4  lea     eax, ds:0[rsi*8]
0x18005f6bb  movsxd  rdi, eax
0x18005f6be  lea     rcx, [rdi+r13]
0x18005f6c2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f6c7  lea     rcx, [rdi+rbx]
0x18005f6cb  movaps  xmm7, xmm0
0x18005f6ce  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f6d3  lea     rcx, [r12+rdi]
0x18005f6d7  movaps  xmm6, xmm0
0x18005f6da  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f6df  addss   xmm0, xmm7
0x18005f6e3  movaps  xmm1, xmm8
0x18005f6e7  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f6ef  addss   xmm0, xmm6
0x18005f6f3  movaps  xmm2, xmm8
0x18005f6f7  mulss   xmm0, xmm1
0x18005f6fb  minss   xmm2, xmm0
0x18005f6ff  xorps   xmm0, xmm0
0x18005f702  maxss   xmm0, xmm2
0x18005f706  cvttss2si eax, xmm0
0x18005f70a  mov     [r15], ax
0x18005f70e  add     r15, 2
0x18005f712  mov     eax, dword ptr [rbp+r14*4+6E0h+var_720]
0x18005f717  add     esi, eax
0x18005f719  mov     eax, [rsp+7E0h+var_7B0]
0x18005f71d  inc     r14
0x18005f720  cmp     r14, 3
0x18005f724  jl      short loc_18005F6B0
0x18005f726  mov     r11d, [rbp+6E0h+var_BC]
0x18005f72d  mov     edi, [rbp+6E0h+var_6A0]
0x18005f730  mov     rbx, qword ptr [rbp+6E0h+var_710]
0x18005f734  mov     edx, [rbp+6E0h+var_6CC]
0x18005f737  add     edx, 0FFFFFFF9h
0x18005f73a  cmp     esi, edx
0x18005f73c  jge     loc_18005FA52
0x18005f742  mov     r14, [rsp+7E0h+var_798]
0x18005f747  lea     eax, ds:18h[rsi*8]
0x18005f74e  movsxd  rcx, eax
0x18005f751  sub     edx, esi
0x18005f753  lea     eax, ds:10h[rsi*8]
0x18005f75a  cdqe
0x18005f75c  sub     rax, rcx
0x18005f75f  mov     [rsp+7E0h+var_780], rax
0x18005f764  lea     rdi, [r12+rcx]
0x18005f768  mov     rbx, [rsp+7E0h+var_780]
0x18005f76d  sub     rax, r12
0x18005f770  mov     [rsp+7E0h+var_768], rax
0x18005f775  lea     eax, ds:20h[rsi*8]
0x18005f77c  cdqe
0x18005f77e  sub     rax, rcx
0x18005f781  mov     [rsp+7E0h+var_7A8], rdi
0x18005f786  mov     [rsp+7E0h+var_778], rax
0x18005f78b  sub     rax, r12
0x18005f78e  mov     [rbp+6E0h+var_760], rax
0x18005f792  lea     eax, ds:30h[rsi*8]
0x18005f799  cdqe
0x18005f79b  sub     rax, rcx
0x18005f79e  mov     [rbp+6E0h+var_750], rax
0x18005f7a2  sub     rax, r12
0x18005f7a5  mov     [rbp+6E0h+var_758], rax
0x18005f7a9  lea     eax, ds:38h[rsi*8]
0x18005f7b0  cdqe
0x18005f7b2  sub     rax, rcx
0x18005f7b5  mov     [rbp+6E0h+var_730], rax
0x18005f7b9  sub     rax, r12
0x18005f7bc  mov     [rbp+6E0h+var_748], rax
0x18005f7c0  lea     eax, ds:0[rsi*8]
0x18005f7c7  cdqe
0x18005f7c9  sub     rax, rcx
0x18005f7cc  mov     rcx, rax
0x18005f7cf  mov     [rsp+7E0h+var_770], rax
0x18005f7d4  lea     eax, [rdx-1]
0x18005f7d7  sub     rcx, r12
0x18005f7da  shr     eax, 3
0x18005f7dd  inc     eax
0x18005f7df  mov     [rbp+6E0h+var_728], rcx
0x18005f7e3  mov     edx, eax
0x18005f7e5  mov     [rsp+7E0h+var_790], rdx
0x18005f7ea  lea     esi, [rsi+rax*8]
0x18005f7ed  mov     [rsp+7E0h+var_7B0], esi
0x18005f7f1  mov     rsi, [rsp+7E0h+var_778]
0x18005f7f6  nop     word ptr [rax+rax+00000000h]
0x18005f800  add     rdi, rcx
0x18005f803  lea     rcx, [rdi+r13]
0x18005f807  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f80c  lea     rcx, [rdi+r14]
0x18005f810  movaps  xmm7, xmm0
0x18005f813  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f818  mov     rcx, [rsp+7E0h+var_770]
0x18005f81d  movaps  xmm6, xmm0
0x18005f820  mov     rdi, [rsp+7E0h+var_7A8]
0x18005f825  add     rcx, rdi
0x18005f828  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f82d  add     rdi, [rsp+7E0h+var_768]
0x18005f832  addss   xmm0, xmm7
0x18005f836  movaps  xmm1, xmm8
0x18005f83a  movaps  xmm2, xmm8
0x18005f83e  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f846  lea     rcx, [rdi+r13]
0x18005f84a  addss   xmm0, xmm6
0x18005f84e  mulss   xmm0, xmm1
0x18005f852  minss   xmm2, xmm0
0x18005f856  xorps   xmm0, xmm0
0x18005f859  maxss   xmm0, xmm2
0x18005f85d  cvttss2si eax, xmm0
0x18005f861  mov     [r15], ax
0x18005f865  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f86a  lea     rcx, [rdi+r14]
0x18005f86e  movaps  xmm7, xmm0
0x18005f871  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f876  mov     rdi, [rsp+7E0h+var_7A8]
0x18005f87b  movaps  xmm6, xmm0
0x18005f87e  lea     rcx, [rbx+rdi]
0x18005f882  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f887  addss   xmm0, xmm7
0x18005f88b  movaps  xmm1, xmm8
0x18005f88f  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f897  sub     rdi, r12
0x18005f89a  lea     rcx, [rdi+r13]
0x18005f89e  addss   xmm0, xmm6
0x18005f8a2  movaps  xmm2, xmm8
0x18005f8a6  mulss   xmm0, xmm1
0x18005f8aa  minss   xmm2, xmm0
0x18005f8ae  xorps   xmm0, xmm0
0x18005f8b1  maxss   xmm0, xmm2
0x18005f8b5  cvttss2si eax, xmm0
0x18005f8b9  mov     [r15+2], ax
0x18005f8be  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f8c3  lea     rcx, [rdi+r14]
0x18005f8c7  movaps  xmm7, xmm0
0x18005f8ca  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f8cf  mov     rdi, [rsp+7E0h+var_7A8]
0x18005f8d4  movaps  xmm6, xmm0
0x18005f8d7  mov     rcx, rdi
0x18005f8da  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f8df  add     rdi, [rbp+6E0h+var_760]
0x18005f8e3  addss   xmm0, xmm7
0x18005f8e7  movaps  xmm1, xmm8
0x18005f8eb  movaps  xmm2, xmm8
0x18005f8ef  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f8f7  lea     rcx, [rdi+r13]
0x18005f8fb  addss   xmm0, xmm6
0x18005f8ff  mulss   xmm0, xmm1
0x18005f903  minss   xmm2, xmm0
0x18005f907  xorps   xmm0, xmm0
0x18005f90a  maxss   xmm0, xmm2
0x18005f90e  cvttss2si eax, xmm0
0x18005f912  mov     [r15+4], ax
0x18005f917  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f91c  lea     rcx, [rdi+r14]
0x18005f920  movaps  xmm7, xmm0
0x18005f923  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f928  mov     rdi, [rsp+7E0h+var_7A8]
0x18005f92d  movaps  xmm6, xmm0
0x18005f930  lea     rcx, [rsi+rdi]
0x18005f934  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f939  addss   xmm0, xmm7
0x18005f93d  movaps  xmm1, xmm8
0x18005f941  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18005f949  addss   xmm0, xmm6
0x18005f94d  movaps  xmm2, xmm8
0x18005f951  mulss   xmm0, xmm1
0x18005f955  minss   xmm2, xmm0
0x18005f959  add     rdi, [rbp+6E0h+var_758]
0x18005f95d  xorps   xmm0, xmm0
0x18005f960  maxss   xmm0, xmm2
0x18005f964  lea     rcx, [rdi+r13]
0x18005f968  cvttss2si eax, xmm0
0x18005f96c  mov     [r15+6], ax
0x18005f971  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f976  lea     rcx, [rdi+r14]
0x18005f97a  movaps  xmm7, xmm0
0x18005f97d  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f982  mov     rcx, [rbp+6E0h+var_750]
0x18005f986  movaps  xmm6, xmm0
0x18005f989  mov     rdi, [rsp+7E0h+var_7A8]
0x18005f98e  add     rcx, rdi
0x18005f991  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18005f996  add     rdi, [rbp+6E0h+var_748]
0x18005f99a  addss   xmm0, xmm7
  ... truncated ...
```
