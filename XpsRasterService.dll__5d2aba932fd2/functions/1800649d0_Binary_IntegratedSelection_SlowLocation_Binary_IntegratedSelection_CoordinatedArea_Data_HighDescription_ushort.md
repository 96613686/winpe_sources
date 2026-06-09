# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,1,16,0>>::ReduceComprehensiveSDK<Data::HighDescription<ushort *>>(Binary::Definition::GeneralQuality<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>> &,Binary::Definition::GeneralQuality<Data::HighDescription<ushort *>> &)

- ea: `0x1800649d0`
- end: `0x1800653b3`
- name: `??$ReduceComprehensiveSDK@V?$HighDescription@PEAG@Data@@@?$SlowLocation@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@V?$MixedResponse@$02$00$0BA@$0A@@23@@IntegratedSelection@Binary@@AEAAXAEAV?$GeneralQuality@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@Definition@2@AEAV?$GeneralQuality@V?$HighDescription@PEAG@Data@@@42@@Z`
- size: `2531`
- prototype: `char __fastcall(_DWORD *, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057d00`

## callees

- `0x180058b20`
- `0x1800649d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,1,16,0>>::ReduceComprehensiveSDK<Data::HighDescription<unsigned short *>>(
        _DWORD *a1,
        __int64 a2,
        int *a3)
{
  int v3; // r10d
  __int64 v5; // rdi
  int v8; // r10d
  __int64 v9; // rcx
  int v10; // r11d
  __int64 v11; // rcx
  __int64 v12; // r12
  int v13; // r8d
  __int64 v14; // rcx
  int v15; // r14d
  __int64 v16; // rax
  int v17; // esi
  __int128 v18; // xmm1
  __int128 v19; // xmm2
  __int64 v20; // rcx
  int v21; // edx
  __int128 v22; // xmm1
  __int128 v23; // xmm2
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // esi
  __int64 v29; // r13
  __int64 v30; // r14
  __int128 v31; // xmm1
  __int128 v32; // xmm2
  __int64 v33; // rcx
  int v34; // ecx
  __int128 v35; // xmm1
  __int128 v36; // xmm2
  __int64 v37; // rcx
  int v38; // r12d
  __int128 v39; // xmm1
  __int128 v40; // xmm2
  __int64 v41; // rcx
  int v42; // ecx
  __int128 v43; // xmm1
  __int128 v44; // xmm2
  __int64 v45; // rcx
  __int128 v46; // xmm1
  __int128 v47; // xmm2
  __int64 v48; // rcx
  int v49; // ecx
  __int128 v50; // xmm1
  __int128 v51; // xmm2
  __int64 v52; // rcx
  int v53; // r12d
  __int128 v54; // xmm1
  __int128 v55; // xmm2
  __int64 v56; // rcx
  int v57; // ecx
  __int128 v58; // xmm1
  __int128 v59; // xmm2
  __int64 v60; // rcx
  int v61; // r12d
  __int128 v62; // xmm1
  __int128 v63; // xmm2
  __int64 v64; // rcx
  int v65; // ecx
  __int128 v66; // xmm1
  __int128 v67; // xmm2
  __int64 v68; // rcx
  int v69; // r12d
  __int128 v70; // xmm1
  __int128 v71; // xmm2
  __int64 v72; // rcx
  int v73; // ecx
  __int128 v74; // xmm1
  __int128 v75; // xmm2
  __int64 v76; // rcx
  int v77; // r12d
  __int128 v78; // xmm1
  __int128 v79; // xmm2
  __int64 v80; // rcx
  int v81; // ecx
  __int128 v82; // xmm1
  __int128 v83; // xmm2
  __int64 v84; // rcx
  int v85; // r12d
  __int128 v86; // xmm1
  __int128 v87; // xmm2
  __int64 v88; // rcx
  int v89; // ecx
  __int128 v90; // xmm1
  __int128 v91; // xmm2
  __int64 v92; // rcx
  __int64 v93; // rsi
  __int64 i; // r14
  __int128 v95; // xmm1
  __int128 v96; // xmm2
  __int64 v97; // rcx
  int v98; // ecx
  __int128 v99; // xmm1
  __int128 v100; // xmm2
  __int64 v101; // rcx
  int v102; // r8d
  int v103; // r12d
  __int64 v104; // rsi
  int v105; // r14d
  int v106; // r9d
  char v107; // al
  int v108; // r9d
  __int64 v109; // rdx
  int v110; // ecx
  int v111; // esi
  int v112; // ecx
  __int128 v113; // xmm1
  __int128 v114; // xmm2
  __int64 v115; // rcx
  int v116; // edx
  __int128 v117; // xmm1
  __int128 v118; // xmm2
  __int64 v119; // rcx
  __int64 v120; // rcx
  int v121; // ecx
  __int64 v123; // [rsp+20h] [rbp-30h] BYREF
  __int64 v124; // [rsp+28h] [rbp-28h]
  __int64 v125; // [rsp+30h] [rbp-20h]
  __int64 v126; // [rsp+38h] [rbp-18h]
  int v127; // [rsp+40h] [rbp-10h]
  __int64 v128; // [rsp+48h] [rbp-8h]

  v3 = a1[8];
  v5 = 0;
  if ( v3 > 0 )
    v3 = 0;
  v8 = -v3;
  *(_QWORD *)(a2 + 8) += 2 * *(_QWORD *)(a2 + 32) * v8;
  v9 = 2 * *(_QWORD *)(a2 + 32) * v8;
  *(_QWORD *)(a2 + 16) += v9;
  *(_QWORD *)(a2 + 24) += v9;
  v10 = a1[11];
  if ( v10 == 1 )
  {
    v11 = *a3;
    v12 = (int)a1[388];
    v13 = *(_DWORD *)a2 - v8;
    if ( (_DWORD)v12 == 1 )
    {
      v26 = a1[3];
      if ( v26 > (int)v11 )
        v26 = v11;
      if ( v26 <= v13 )
        v13 = v26;
      v127 = v13;
      v27 = 8LL * (v13 / 8);
      LOBYTE(v16) = 8 * (v13 / 8);
      if ( (unsigned __int64)(v27 + 0x80000000LL) <= 0xFFFFFFFF )
      {
        LOBYTE(v16) = 8 * (v13 / 8);
        v128 = (int)v27;
        if ( (int)v27 > 0 )
        {
          v28 = 2;
          v29 = 0;
          v30 = 6;
          do
          {
            v31 = *(_OWORD *)(a2 + 8);
            v32 = *(_OWORD *)(a2 + 24);
            v33 = v29 * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v32 + 1);
            v33 *= 2;
            v124 += v33;
            v123 = v33 + v31;
            v125 = v33 + v32;
            v34 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v34 > 0x3ECu && (int)v5 > 0 )
            {
              v35 = *(_OWORD *)(a2 + 8);
              v36 = *(_OWORD *)(a2 + 24);
              v37 = (v29 - 1) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v36 + 1);
              v37 *= 2;
              v124 += v37;
              v123 = v37 + v35;
              v125 = v37 + v36;
              v34 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v38 = v28 - 1;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) - 6) = v34;
            v39 = *(_OWORD *)(a2 + 8);
            v40 = *(_OWORD *)(a2 + 24);
            v41 = (v28 - 1) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v40 + 1);
            v41 *= 2;
            v124 += v41;
            v123 = v41 + v39;
            v125 = v41 + v40;
            v42 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v42 > 0x3ECu && v38 > 0 )
            {
              v43 = *(_OWORD *)(a2 + 8);
              v44 = *(_OWORD *)(a2 + 24);
              v45 = (v38 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v44 + 1);
              v45 *= 2;
              v124 += v45;
              v123 = v45 + v43;
              v125 = v45 + v44;
              v42 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) - 4) = v42;
            v46 = *(_OWORD *)(a2 + 8);
            v47 = *(_OWORD *)(a2 + 24);
            v48 = v28 * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v47 + 1);
            v48 *= 2;
            v124 += v48;
            v123 = v48 + v46;
            v125 = v48 + v47;
            v49 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v49 > 0x3ECu && v28 > 0 )
            {
              v50 = *(_OWORD *)(a2 + 8);
              v51 = *(_OWORD *)(a2 + 24);
              v52 = (v28 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v51 + 1);
              v52 *= 2;
              v124 += v52;
              v123 = v52 + v50;
              v125 = v52 + v51;
              v49 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v53 = v28 + 1;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) - 2) = v49;
            v54 = *(_OWORD *)(a2 + 8);
            v55 = *(_OWORD *)(a2 + 24);
            v56 = (v28 + 1) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v55 + 1);
            v56 *= 2;
            v124 += v56;
            v123 = v56 + v54;
            v125 = v56 + v55;
            v57 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v57 > 0x3ECu && v53 > 0 )
            {
              v58 = *(_OWORD *)(a2 + 8);
              v59 = *(_OWORD *)(a2 + 24);
              v60 = (v53 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v59 + 1);
              v60 *= 2;
              v124 += v60;
              v123 = v60 + v58;
              v125 = v60 + v59;
              v57 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v61 = v28 + 2;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1)) = v57;
            v62 = *(_OWORD *)(a2 + 8);
            v63 = *(_OWORD *)(a2 + 24);
            v64 = (v28 + 2) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v63 + 1);
            v64 *= 2;
            v124 += v64;
            v123 = v64 + v62;
            v125 = v64 + v63;
            v65 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v65 > 0x3ECu && v61 > 0 )
            {
              v66 = *(_OWORD *)(a2 + 8);
              v67 = *(_OWORD *)(a2 + 24);
              v68 = (v61 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v67 + 1);
              v68 *= 2;
              v124 += v68;
              v123 = v68 + v66;
              v125 = v68 + v67;
              v65 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v69 = v28 + 3;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) + 2) = v65;
            v70 = *(_OWORD *)(a2 + 8);
            v71 = *(_OWORD *)(a2 + 24);
            v72 = (v28 + 3) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v71 + 1);
            v72 *= 2;
            v124 += v72;
            v123 = v72 + v70;
            v125 = v72 + v71;
            v73 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v73 > 0x3ECu && v69 > 0 )
            {
              v74 = *(_OWORD *)(a2 + 8);
              v75 = *(_OWORD *)(a2 + 24);
              v76 = (v69 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v75 + 1);
              v76 *= 2;
              v124 += v76;
              v123 = v76 + v74;
              v125 = v76 + v75;
              v73 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v77 = v28 + 4;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) + 4) = v73;
            v78 = *(_OWORD *)(a2 + 8);
            v79 = *(_OWORD *)(a2 + 24);
            v80 = (v28 + 4) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v79 + 1);
            v80 *= 2;
            v124 += v80;
            v123 = v80 + v78;
            v125 = v80 + v79;
            v81 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v81 > 0x3ECu && v77 > 0 )
            {
              v82 = *(_OWORD *)(a2 + 8);
              v83 = *(_OWORD *)(a2 + 24);
              v84 = (v77 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v83 + 1);
              v84 *= 2;
              v124 += v84;
              v123 = v84 + v82;
              v125 = v84 + v83;
              v81 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v85 = v28 + 5;
            *(_WORD *)(v30 + *((_QWORD *)a3 + 1) + 6) = v81;
            v86 = *(_OWORD *)(a2 + 8);
            v87 = *(_OWORD *)(a2 + 24);
            v88 = (v28 + 5) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v87 + 1);
            v88 *= 2;
            v124 += v88;
            v123 = v88 + v86;
            v125 = v88 + v87;
            v89 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            if ( (unsigned __int16)v89 > 0x3ECu && v85 > 0 )
            {
              v90 = *(_OWORD *)(a2 + 8);
              v91 = *(_OWORD *)(a2 + 24);
              v92 = (v85 - 1LL) * *(_QWORD *)(a2 + 32);
              v124 = *(_QWORD *)(a2 + 16);
              v126 = *((_QWORD *)&v91 + 1);
              v92 *= 2;
              v124 += v92;
              v123 = v92 + v90;
              v125 = v92 + v91;
              v89 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
            }
            v16 = *((_QWORD *)a3 + 1);
            LODWORD(v5) = v5 + 8;
            v28 += 8;
            v29 = (int)v5;
            *(_WORD *)(v30 + v16 + 8) = v89;
            v30 += 16;
          }
          while ( (int)v5 < v128 );
          v13 = v127;
        }
      }
      v93 = (int)v5;
      for ( i = v13; v93 < i; ++v93 )
      {
        v95 = *(_OWORD *)(a2 + 8);
        v96 = *(_OWORD *)(a2 + 24);
        v97 = (int)v5 * *(_QWORD *)(a2 + 32);
        v124 = *(_QWORD *)(a2 + 16);
        v126 = *((_QWORD *)&v96 + 1);
        v97 *= 2;
        v124 += v97;
        v123 = v97 + v95;
        v125 = v97 + v96;
        v98 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
        if ( (unsigned __int16)v98 > 0x3ECu && (int)v5 > 0 )
        {
          v99 = *(_OWORD *)(a2 + 8);
          v100 = *(_OWORD *)(a2 + 24);
          v101 = ((int)v5 - 1LL) * *(_QWORD *)(a2 + 32);
          v124 = *(_QWORD *)(a2 + 16);
          v126 = *((_QWORD *)&v100 + 1);
          v101 *= 2;
          v124 += v101;
          v123 = v101 + v99;
          v125 = v101 + v100;
          v98 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
        }
        v16 = *((_QWORD *)a3 + 1);
        LODWORD(v5) = v5 + 1;
        *(_WORD *)(v16 + 2 * v93) = v98;
      }
    }
    else
    {
      v14 = v12 * v11;
      v15 = 0;
      if ( (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF )
      {
        LOBYTE(v16) = 0;
      }
      else
      {
        v15 = v14;
        LOBYTE(v16) = 1;
      }
      v17 = 0;
      if ( !(_BYTE)v16 )
        v15 = 0;
      if ( a1[3] <= v15 )
        v15 = a1[3];
      if ( v15 > v13 )
        v15 = *(_DWORD *)a2 - v8;
      if ( v15 > 0 )
      {
        do
        {
          v18 = *(_OWORD *)(a2 + 8);
          v19 = *(_OWORD *)(a2 + 24);
          v20 = v17 * *(_QWORD *)(a2 + 32);
          v124 = *(_QWORD *)(a2 + 16);
          v126 = *((_QWORD *)&v19 + 1);
          v20 *= 2;
          v124 += v20;
          v123 = v20 + v18;
          v125 = v20 + v19;
          v21 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
          if ( (unsigned __int16)v21 > 0x3ECu && v17 > 0 )
          {
            v22 = *(_OWORD *)(a2 + 8);
            v23 = *(_OWORD *)(a2 + 24);
            v24 = (v17 - 1LL) * *(_QWORD *)(a2 + 32);
            v124 = *(_QWORD *)(a2 + 16);
            v126 = *((_QWORD *)&v23 + 1);
            v24 *= 2;
            v124 += v24;
            v123 = v24 + v22;
            v125 = v24 + v23;
            v21 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
          }
          v16 = *((_QWORD *)a3 + 1);
          v25 = v5++;
          v17 += v12;
          *(_WORD *)(v16 + 2 * v25) = v21;
        }
        while ( v17 < v15 );
      }
    }
  }
  else
  {
    v102 = a1[9];
    v103 = a1[11];
    if ( v10 <= 0 )
      v103 = 1;
    if ( v102 < 0 || v102 >= v103 )
    {
      v102 %= v103;
      if ( v102 < 0 )
        v102 += v103;
    }
    v104 = *a3;
    v105 = v102;
    v106 = 0;
    if ( (unsigned __int64)(v104 * (int)a1[762] + 0x80000000LL) > 0xFFFFFFFF )
    {
      v107 = 0;
    }
    else
    {
      v106 = v104 * a1[762];
      v107 = 1;
    }
    if ( !v107 )
      v106 = 0;
    v108 = v106 / v10;
    v109 = (unsigned int)((int)v104 >> 31);
    LODWORD(v109) = (int)v104 % v10;
    LODWORD(v16) = (int)v104 / v10;
    if ( (int)v104 % v10 > 0 )
    {
      do
      {
        v108 += a1[v102 + 388];
        v110 = v102 + 1;
        v102 = 0;
        if ( v110 < v103 )
          v102 = v110;
        --v109;
      }
      while ( v109 );
    }
    v111 = 0;
    v112 = *(_DWORD *)a2 - v8;
    if ( v108 > a1[3] )
      v108 = a1[3];
    if ( v108 <= v112 )
      v112 = v108;
    v127 = v112;
    if ( v112 > 0 )
    {
      v128 = 0;
      do
      {
        v113 = *(_OWORD *)(a2 + 8);
        v114 = *(_OWORD *)(a2 + 24);
        v115 = v111 * *(_QWORD *)(a2 + 32);
        v124 = *(_QWORD *)(a2 + 16);
        v126 = *((_QWORD *)&v114 + 1);
        v115 *= 2;
        v124 += v115;
        v123 = v115 + v113;
        v125 = v115 + v114;
        v116 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
        if ( (unsigned __int16)v116 > 0x3ECu && v111 > 0 )
        {
          v117 = *(_OWORD *)(a2 + 8);
          v118 = *(_OWORD *)(a2 + 24);
          v119 = (v111 - 1LL) * *(_QWORD *)(a2 + 32);
          v124 = *(_QWORD *)(a2 + 16);
          v126 = *((_QWORD *)&v118 + 1);
          v119 *= 2;
          v124 += v119;
          v123 = v119 + v117;
          v125 = v119 + v118;
          v116 = (int)Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned short *>,3,0>>(&v123);
        }
        v120 = v128;
        *(_WORD *)(v128 + *((_QWORD *)a3 + 1)) = v116;
        v16 = v105;
        v128 = v120 + 2;
        v121 = v105 + 1;
        v105 = 0;
        v111 += a1[v16 + 388];
        if ( v121 < v103 )
          v105 = v121;
      }
      while ( v111 < v127 );
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800649d0  mov     [rsp-28h+arg_0], rbx
0x1800649d5  mov     [rsp-28h+arg_10], rsi
0x1800649da  mov     [rsp-28h+arg_18], rdi
0x1800649df  push    rbp
0x1800649e0  push    r12
0x1800649e2  push    r13
0x1800649e4  push    r14
0x1800649e6  push    r15
0x1800649e8  mov     rbp, rsp
0x1800649eb  sub     rsp, 50h
0x1800649ef  mov     r10d, [rcx+20h]
0x1800649f3  mov     r13, rcx
0x1800649f6  xor     edi, edi
0x1800649f8  mov     r15, r8
0x1800649fb  test    r10d, r10d
0x1800649fe  mov     rbx, rdx
0x180064a01  cmovg   r10d, edi
0x180064a05  neg     r10d
0x180064a08  movsxd  rcx, r10d
0x180064a0b  mov     rax, rcx
0x180064a0e  imul    rax, [rdx+20h]
0x180064a13  add     rax, rax
0x180064a16  add     [rdx+8], rax
0x180064a1a  imul    rcx, [rdx+20h]
0x180064a1f  add     rcx, rcx
0x180064a22  add     [rdx+10h], rcx
0x180064a26  add     [rdx+18h], rcx
0x180064a2a  mov     r11d, [r13+2Ch]
0x180064a2e  cmp     r11d, 1
0x180064a32  jnz     loc_1800651F4
0x180064a38  movsxd  rcx, dword ptr [r8]
0x180064a3b  mov     r8d, [rdx]
0x180064a3e  movsxd  r12, dword ptr [r13+610h]
0x180064a45  sub     r8d, r10d
0x180064a48  cmp     r12d, r11d
0x180064a4b  jz      loc_180064B5C
0x180064a51  imul    rcx, r12
0x180064a55  mov     eax, 80000000h
0x180064a5a  mov     edx, 0FFFFFFFFh
0x180064a5f  add     rax, rcx
0x180064a62  mov     r14d, edi
0x180064a65  cmp     rax, rdx
0x180064a68  ja      short loc_180064A73
0x180064a6a  mov     r14d, ecx
0x180064a6d  movzx   eax, r11b
0x180064a71  jmp     short loc_180064A75
0x180064a73  xor     al, al
0x180064a75  test    al, al
0x180064a77  mov     esi, edi
0x180064a79  cmovz   r14d, edi
0x180064a7d  cmp     [r13+0Ch], r14d
0x180064a81  cmovle  r14d, [r13+0Ch]
0x180064a86  cmp     r14d, r8d
0x180064a89  cmovg   r14d, r8d
0x180064a8d  test    r14d, r14d
0x180064a90  jle     loc_180065395
0x180064a96  nop     word ptr [rax+rax+00000000h]
0x180064aa0  movups  xmm1, xmmword ptr [rbx+8]
0x180064aa4  mov     rcx, [rbx+20h]
0x180064aa8  movups  xmm2, xmmword ptr [rbx+18h]
0x180064aac  movsxd  r13, esi
0x180064aaf  imul    rcx, r13
0x180064ab3  movups  [rbp+var_30], xmm1
0x180064ab7  movq    rax, xmm1
0x180064abc  movups  [rbp+var_20], xmm2
0x180064ac0  add     rcx, rcx
0x180064ac3  add     qword ptr [rbp+var_30+8], rcx
0x180064ac7  add     rax, rcx
0x180064aca  mov     qword ptr [rbp+var_30], rax
0x180064ace  movq    rax, xmm2
0x180064ad3  add     rax, rcx
0x180064ad6  lea     rcx, [rbp+var_30]
0x180064ada  mov     qword ptr [rbp+var_20], rax
0x180064ade  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064ae3  cvttss2si edx, xmm0
0x180064ae7  mov     eax, 3ECh
0x180064aec  cmp     dx, ax
0x180064aef  jbe     short loc_180064B3D
0x180064af1  test    esi, esi
0x180064af3  jle     short loc_180064B3D
0x180064af5  movups  xmm1, xmmword ptr [rbx+8]
0x180064af9  mov     rcx, [rbx+20h]
0x180064afd  lea     rax, [r13-1]
0x180064b01  movups  xmm2, xmmword ptr [rbx+18h]
0x180064b05  imul    rcx, rax
0x180064b09  movups  [rbp+var_30], xmm1
0x180064b0d  movq    rax, xmm1
0x180064b12  movups  [rbp+var_20], xmm2
0x180064b16  add     rcx, rcx
0x180064b19  add     qword ptr [rbp+var_30+8], rcx
0x180064b1d  add     rax, rcx
0x180064b20  mov     qword ptr [rbp+var_30], rax
0x180064b24  movq    rax, xmm2
0x180064b29  add     rax, rcx
0x180064b2c  lea     rcx, [rbp+var_30]
0x180064b30  mov     qword ptr [rbp+var_20], rax
0x180064b34  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064b39  cvttss2si edx, xmm0
0x180064b3d  mov     rax, [r15+8]
0x180064b41  mov     rcx, rdi
0x180064b44  inc     rdi
0x180064b47  add     esi, r12d
0x180064b4a  mov     [rax+rcx*2], dx
0x180064b4e  cmp     esi, r14d
0x180064b51  jl      loc_180064AA0
0x180064b57  jmp     loc_180065395
0x180064b5c  mov     eax, [r13+0Ch]
0x180064b60  mov     r12d, 3ECh
0x180064b66  cmp     eax, ecx
0x180064b68  cmovg   eax, ecx
0x180064b6b  cmp     eax, r8d
0x180064b6e  cmovle  r8d, eax
0x180064b72  mov     eax, r8d
0x180064b75  mov     [rbp+var_10], r8d
0x180064b79  cdq
0x180064b7a  and     edx, 7
0x180064b7d  add     eax, edx
0x180064b7f  mov     edx, 0FFFFFFFFh
0x180064b84  sar     eax, 3
0x180064b87  movsxd  rcx, eax
0x180064b8a  mov     eax, 80000000h
0x180064b8f  shl     rcx, 3
0x180064b93  add     rax, rcx
0x180064b96  cmp     rax, rdx
0x180064b99  ja      loc_180065126
0x180064b9f  movsxd  rax, ecx
0x180064ba2  mov     [rbp+var_8], rax
0x180064ba6  test    ecx, ecx
0x180064ba8  jle     loc_180065126
0x180064bae  mov     esi, 2
0x180064bb3  mov     r13, rdi
0x180064bb6  lea     r14d, [rsi+4]
0x180064bba  nop     word ptr [rax+rax+00h]
0x180064bc0  movups  xmm1, xmmword ptr [rbx+8]
0x180064bc4  mov     rcx, [rbx+20h]
0x180064bc8  movups  xmm2, xmmword ptr [rbx+18h]
0x180064bcc  imul    rcx, r13
0x180064bd0  movups  [rbp+var_30], xmm1
0x180064bd4  movq    rax, xmm1
0x180064bd9  movups  [rbp+var_20], xmm2
0x180064bdd  add     rcx, rcx
0x180064be0  add     qword ptr [rbp+var_30+8], rcx
0x180064be4  add     rax, rcx
0x180064be7  mov     qword ptr [rbp+var_30], rax
0x180064beb  movq    rax, xmm2
0x180064bf0  add     rax, rcx
0x180064bf3  lea     rcx, [rbp+var_30]
0x180064bf7  mov     qword ptr [rbp+var_20], rax
0x180064bfb  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064c00  cvttss2si ecx, xmm0
0x180064c04  cmp     cx, r12w
0x180064c08  jbe     short loc_180064C56
0x180064c0a  test    edi, edi
0x180064c0c  jle     short loc_180064C56
0x180064c0e  movups  xmm1, xmmword ptr [rbx+8]
0x180064c12  mov     rcx, [rbx+20h]
0x180064c16  lea     rax, [r13-1]
0x180064c1a  movups  xmm2, xmmword ptr [rbx+18h]
0x180064c1e  imul    rcx, rax
0x180064c22  movups  [rbp+var_30], xmm1
0x180064c26  movq    rax, xmm1
0x180064c2b  movups  [rbp+var_20], xmm2
0x180064c2f  add     rcx, rcx
0x180064c32  add     qword ptr [rbp+var_30+8], rcx
0x180064c36  add     rax, rcx
0x180064c39  mov     qword ptr [rbp+var_30], rax
0x180064c3d  movq    rax, xmm2
0x180064c42  add     rax, rcx
0x180064c45  lea     rcx, [rbp+var_30]
0x180064c49  mov     qword ptr [rbp+var_20], rax
0x180064c4d  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064c52  cvttss2si ecx, xmm0
0x180064c56  mov     rax, [r15+8]
0x180064c5a  lea     r12d, [rsi-1]
0x180064c5e  mov     [r14+rax-6], cx
0x180064c64  movups  xmm1, xmmword ptr [rbx+8]
0x180064c68  mov     rcx, [rbx+20h]
0x180064c6c  movups  xmm2, xmmword ptr [rbx+18h]
0x180064c70  movsxd  rax, r12d
0x180064c73  imul    rcx, rax
0x180064c77  movups  [rbp+var_30], xmm1
0x180064c7b  movq    rax, xmm1
0x180064c80  movups  [rbp+var_20], xmm2
0x180064c84  add     rcx, rcx
0x180064c87  add     qword ptr [rbp+var_30+8], rcx
0x180064c8b  add     rax, rcx
0x180064c8e  mov     qword ptr [rbp+var_30], rax
0x180064c92  movq    rax, xmm2
0x180064c97  add     rax, rcx
0x180064c9a  lea     rcx, [rbp+var_30]
0x180064c9e  mov     qword ptr [rbp+var_20], rax
0x180064ca2  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064ca7  cvttss2si ecx, xmm0
0x180064cab  mov     r13d, 3ECh
0x180064cb1  cmp     cx, r13w
0x180064cb5  jbe     short loc_180064D06
0x180064cb7  test    r12d, r12d
0x180064cba  jle     short loc_180064D06
0x180064cbc  movups  xmm1, xmmword ptr [rbx+8]
0x180064cc0  mov     rcx, [rbx+20h]
0x180064cc4  movups  xmm2, xmmword ptr [rbx+18h]
0x180064cc8  movsxd  rax, r12d
0x180064ccb  dec     rax
0x180064cce  imul    rcx, rax
0x180064cd2  movups  [rbp+var_30], xmm1
0x180064cd6  movq    rax, xmm1
0x180064cdb  movups  [rbp+var_20], xmm2
0x180064cdf  add     rcx, rcx
0x180064ce2  add     qword ptr [rbp+var_30+8], rcx
0x180064ce6  add     rax, rcx
0x180064ce9  mov     qword ptr [rbp+var_30], rax
0x180064ced  movq    rax, xmm2
0x180064cf2  add     rax, rcx
0x180064cf5  lea     rcx, [rbp+var_30]
0x180064cf9  mov     qword ptr [rbp+var_20], rax
0x180064cfd  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064d02  cvttss2si ecx, xmm0
0x180064d06  mov     rax, [r15+8]
0x180064d0a  movsxd  r12, esi
0x180064d0d  mov     [r14+rax-4], cx
0x180064d13  movups  xmm1, xmmword ptr [rbx+8]
0x180064d17  mov     rcx, [rbx+20h]
0x180064d1b  movups  xmm2, xmmword ptr [rbx+18h]
0x180064d1f  imul    rcx, r12
0x180064d23  movups  [rbp+var_30], xmm1
0x180064d27  movq    rax, xmm1
0x180064d2c  movups  [rbp+var_20], xmm2
0x180064d30  add     rcx, rcx
0x180064d33  add     qword ptr [rbp+var_30+8], rcx
0x180064d37  add     rax, rcx
0x180064d3a  mov     qword ptr [rbp+var_30], rax
0x180064d3e  movq    rax, xmm2
0x180064d43  add     rax, rcx
0x180064d46  lea     rcx, [rbp+var_30]
0x180064d4a  mov     qword ptr [rbp+var_20], rax
0x180064d4e  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064d53  cvttss2si ecx, xmm0
0x180064d57  cmp     cx, r13w
0x180064d5b  jbe     short loc_180064DAA
0x180064d5d  test    esi, esi
0x180064d5f  jle     short loc_180064DAA
0x180064d61  movups  xmm1, xmmword ptr [rbx+8]
0x180064d65  mov     rcx, [rbx+20h]
0x180064d69  lea     rax, [r12-1]
0x180064d6e  movups  xmm2, xmmword ptr [rbx+18h]
0x180064d72  imul    rcx, rax
0x180064d76  movups  [rbp+var_30], xmm1
0x180064d7a  movq    rax, xmm1
0x180064d7f  movups  [rbp+var_20], xmm2
0x180064d83  add     rcx, rcx
0x180064d86  add     qword ptr [rbp+var_30+8], rcx
0x180064d8a  add     rax, rcx
0x180064d8d  mov     qword ptr [rbp+var_30], rax
0x180064d91  movq    rax, xmm2
0x180064d96  add     rax, rcx
0x180064d99  lea     rcx, [rbp+var_30]
0x180064d9d  mov     qword ptr [rbp+var_20], rax
0x180064da1  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064da6  cvttss2si ecx, xmm0
0x180064daa  mov     rax, [r15+8]
0x180064dae  lea     r12d, [rsi+1]
0x180064db2  mov     [r14+rax-2], cx
0x180064db8  movups  xmm1, xmmword ptr [rbx+8]
0x180064dbc  mov     rcx, [rbx+20h]
0x180064dc0  movups  xmm2, xmmword ptr [rbx+18h]
0x180064dc4  movsxd  rax, r12d
0x180064dc7  imul    rcx, rax
0x180064dcb  movups  [rbp+var_30], xmm1
0x180064dcf  movq    rax, xmm1
0x180064dd4  movups  [rbp+var_20], xmm2
0x180064dd8  add     rcx, rcx
0x180064ddb  add     qword ptr [rbp+var_30+8], rcx
0x180064ddf  add     rax, rcx
0x180064de2  mov     qword ptr [rbp+var_30], rax
0x180064de6  movq    rax, xmm2
0x180064deb  add     rax, rcx
0x180064dee  lea     rcx, [rbp+var_30]
0x180064df2  mov     qword ptr [rbp+var_20], rax
0x180064df6  call    ??$Convert@V?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@IntegratedSelection@Binary@@@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@SAMAEBV?$CoordinatedArea@V?$HighDescription@PEAG@Data@@$02$0A@@12@@Z; Binary::IntegratedSelection::MixedResponse<3,1,16,0>::Convert<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0>>(Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<ushort *>,3,0> const &)
0x180064dfb  cvttss2si ecx, xmm0
0x180064dff  cmp     cx, r13w
0x180064e03  jbe     short loc_180064E54
0x180064e05  test    r12d, r12d
0x180064e08  jle     short loc_180064E54
0x180064e0a  movups  xmm1, xmmword ptr [rbx+8]
0x180064e0e  mov     rcx, [rbx+20h]
0x180064e12  movups  xmm2, xmmword ptr [rbx+18h]
0x180064e16  movsxd  rax, r12d
0x180064e19  dec     rax
0x180064e1c  imul    rcx, rax
0x180064e20  movups  [rbp+var_30], xmm1
0x180064e24  movq    rax, xmm1
0x180064e29  movups  [rbp+var_20], xmm2
0x180064e2d  add     rcx, rcx
0x180064e30  add     qword ptr [rbp+var_30+8], rcx
0x180064e34  add     rax, rcx
0x180064e37  mov     qword ptr [rbp+var_30], rax
0x180064e3b  movq    rax, xmm2
0x180064e40  add     rax, rcx
0x180064e43  lea     rcx, [rbp+var_30]
  ... truncated ...
```
