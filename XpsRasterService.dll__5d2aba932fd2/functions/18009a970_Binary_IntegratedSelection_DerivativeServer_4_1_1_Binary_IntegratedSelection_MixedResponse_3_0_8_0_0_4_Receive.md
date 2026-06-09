# Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009a970`
- end: `0x18009aff5`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$03$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1669`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d5c0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x18009a970`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  int v10; // eax
  unsigned __int8 *v11; // r15
  int v12; // esi
  int v13; // edi
  int v14; // r14d
  __int128 v15; // xmm15
  int v16; // r11d
  int v17; // ecx
  int v18; // r10d
  __int64 v19; // r8
  int v20; // eax
  int v21; // r10d
  int v22; // r9d
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int8 *v25; // r12
  unsigned __int8 *v26; // r10
  unsigned __int8 *v27; // r15
  __int64 v28; // rcx
  int v29; // r11d
  __int64 v30; // r9
  __m128i *v31; // r8
  int v32; // eax
  __m128i si128; // xmm14
  const __m128i *v34; // rcx
  __int64 v35; // rdi
  __m128i *v36; // rax
  __int64 v37; // rdx
  __m128i v38; // xmm1
  __m128i v39; // xmm0
  __m128i v40; // xmm1
  __m128i v41; // xmm10
  const __m128i *v42; // rdx
  __m128i v43; // xmm9
  __m128i *v44; // rax
  __m128i v45; // xmm3
  __m128i v46; // xmm12
  __m128i v47; // xmm1
  __m128i v48; // xmm3
  __m128i v49; // xmm10
  __int64 v50; // r9
  __m128i v51; // xmm4
  __m128i v52; // xmm8
  __m128i v53; // xmm2
  __m128i v54; // xmm4
  __m128i v55; // xmm9
  __m128i v56; // xmm11
  __m128i v57; // xmm12
  __m128i v58; // xmm5
  __m128i v59; // xmm10
  __m128i v60; // xmm3
  __m128i v61; // xmm8
  __m128i v62; // xmm2
  __m128i v63; // xmm0
  __m128i v64; // xmm9
  __m128i v65; // xmm1
  __m128i v66; // xmm7
  __m128i v67; // xmm6
  __m128i v68; // xmm7
  __m128i v69; // xmm4
  __m128i v70; // xmm0
  __m128i v71; // xmm4
  __m128i v72; // xmm11
  __m128i v73; // xmm12
  __m128i v74; // xmm1
  __m128i v75; // xmm2
  __m128i v76; // xmm1
  __m128i v77; // xmm2
  __m128i v78; // xmm1
  __m128i v79; // xmm0
  signed __int64 v80; // r15
  signed __int64 v81; // r10
  unsigned __int8 *v82; // rdx
  __int64 v83; // r9
  int v84; // eax
  int v85; // ecx
  __int64 v86; // rax
  int v88; // [rsp+30h] [rbp-D0h]
  __m128i v90; // [rsp+40h] [rbp-C0h] BYREF
  __m128i v91; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v92; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v93; // [rsp+70h] [rbp-90h] BYREF
  __m128i v94; // [rsp+80h] [rbp-80h]
  __m128i v95; // [rsp+90h] [rbp-70h]
  __m128i v96; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v97; // [rsp+B0h] [rbp-50h]
  __m128i v98; // [rsp+C0h] [rbp-40h]
  __m128i v99[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v100[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v101[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v102; // [rsp+120h] [rbp+20h]
  __int64 v103; // [rsp+130h] [rbp+30h]
  __m128i v104; // [rsp+140h] [rbp+40h]
  _OWORD v105[7]; // [rsp+150h] [rbp+50h] BYREF
  int v106; // [rsp+1C0h] [rbp+C0h] BYREF
  int v107; // [rsp+1C4h] [rbp+C4h]
  __int64 v108; // [rsp+1C8h] [rbp+C8h]
  char v109[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v110; // [rsp+1F0h] [rbp+F0h]
  int v111; // [rsp+1F4h] [rbp+F4h]
  int v112; // [rsp+1F8h] [rbp+F8h]
  _DWORD v113[374]; // [rsp+1FCh] [rbp+FCh]
  int v114; // [rsp+7D4h] [rbp+6D4h]
  int v115; // [rsp+7DCh] [rbp+6DCh]
  int v116; // [rsp+7ECh] [rbp+6ECh]

  *(_OWORD *)v101 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v106, 1, 1, (_DWORD)a3, (__int64)v101, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v108];
  *(_QWORD *)&v102 = &v8[v108];
  *((_QWORD *)&v102 + 1) = &v8[v108 + 1];
  v103 = (__int64)&v8[v108 + 2];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v109,
                  v8,
                  v100,
                  v101);
  if ( (_BYTE)v10 )
  {
    v11 = 0;
    v101[0] = 0;
    LODWORD(v100[0]) = 1;
    v88 = 0;
    if ( v106 > 0 )
    {
      v12 = v107;
      v13 = v114;
      v14 = v110;
      v15 = v102;
      do
      {
        v110 = ++v14;
        if ( v14 == 1 )
        {
          v16 = 0;
          v17 = *(_DWORD *)(a1 + 40);
          v18 = *(_DWORD *)(a1 + 28);
          v19 = *(int *)(a1 + 52);
          if ( v111 <= 0 )
            v16 = v111;
          v20 = *(_DWORD *)(a1 + 44);
          v105[5] = v15;
          if ( v18 < v20 )
            v18 = v20;
          v21 = v18 - v20;
          v22 = v19 - 1;
          v23 = v112;
          if ( v112 < v17 )
            v23 = v17;
          v24 = v19 * ((v23 - v17) % *(_DWORD *)(a1 + 48));
          if ( v21 <= v22 )
            v22 = v21;
          v25 = &v11[*((_QWORD *)&v15 + 1)];
          v26 = &v11[(_QWORD)v9];
          v27 = &v11[v103];
          v28 = v22 + v24;
          v29 = -v16;
          v30 = v116;
          v31 = (__m128i *)(*(_QWORD *)(a1 + 56) + 2 * v28);
          if ( v116 < 1LL )
          {
            do
            {
              if ( v29 >= v12 )
                break;
              v31->m128i_i16[0] = (85 * (v26[4 * v29] + v27[4 * v29] + (unsigned int)v25[4 * v29])) >> 6;
              v31 = (__m128i *)((char *)v31 + 2);
              v32 = *((_DWORD *)v100 + v30++);
              v29 += v32;
            }
            while ( v30 < 1 );
            v13 = v114;
            v14 = v110;
            v12 = v107;
          }
          if ( v29 < v12 - 31 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v34 = (const __m128i *)&v26[4 * v29 + 32];
            v35 = ((unsigned int)(v12 - 31 - v29 - 1) >> 5) + 1;
            v29 += 32 * v35;
            do
            {
              v36 = &v92;
              v37 = 2;
              do
              {
                v36 += 4;
                v38 = _mm_loadu_si128(v34 - 1);
                v36[-6] = _mm_loadu_si128(v34 - 2);
                v39 = _mm_loadu_si128(v34);
                v36[-5] = v38;
                v40 = _mm_loadu_si128(v34 + 1);
                v34 += 4;
                v36[-4] = v39;
                v36[-3] = v40;
                --v37;
              }
              while ( v37 );
              v41 = _mm_load_si128(&v90);
              v42 = (const __m128i *)v105;
              v43 = _mm_load_si128(&v91);
              v44 = &v91;
              v45 = _mm_load_si128(&v92);
              v46 = _mm_unpacklo_epi8(v41, v94);
              v47 = _mm_unpacklo_epi8(v45, v96);
              v48 = _mm_unpackhi_epi8(v45, v96);
              v49 = _mm_unpackhi_epi8(v41, v94);
              v50 = 2;
              v51 = _mm_load_si128(&v93);
              v52 = _mm_unpacklo_epi8(v43, v95);
              v53 = _mm_unpacklo_epi8(v51, v97);
              v54 = _mm_unpackhi_epi8(v51, v97);
              v55 = _mm_unpackhi_epi8(v43, v95);
              v56 = _mm_unpacklo_epi8(v46, v47);
              v57 = _mm_unpackhi_epi8(v46, v47);
              v58 = _mm_unpacklo_epi8(v49, v48);
              v59 = _mm_unpackhi_epi8(v49, v48);
              v60 = _mm_unpacklo_epi8(v52, v53);
              v61 = _mm_unpackhi_epi8(v52, v53);
              v62 = _mm_unpacklo_epi8(v55, v54);
              v63 = _mm_unpacklo_epi8(v58, v62);
              v64 = _mm_unpackhi_epi8(v55, v54);
              v65 = _mm_unpacklo_epi8(v59, v64);
              v66 = _mm_unpacklo_epi8(v56, v60);
              v67 = _mm_unpacklo_epi8(v66, v63);
              v68 = _mm_unpackhi_epi8(v66, v63);
              v69 = _mm_unpacklo_epi8(v57, v61);
              v70 = _mm_unpacklo_epi8(v69, v65);
              v71 = _mm_unpackhi_epi8(v69, v65);
              v72 = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v56, v60), _mm_unpackhi_epi8(v58, v62));
              v73 = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v57, v61), _mm_unpackhi_epi8(v59, v64));
              v105[1] = _mm_unpacklo_epi8(v72, v73);
              v104 = _mm_unpacklo_epi8(v67, v70);
              v105[0] = _mm_unpacklo_epi8(v68, v71);
              v105[2] = _mm_unpackhi_epi8(v67, v70);
              v105[3] = _mm_unpackhi_epi8(v68, v71);
              v105[4] = _mm_unpackhi_epi8(v72, v73);
              do
              {
                v74 = _mm_loadu_si128(v42 - 1);
                v44 += 6;
                v75 = _mm_loadu_si128(v42);
                v42 += 3;
                v44[-7] = _mm_unpacklo_epi8(v74, (__m128i)0LL);
                v44[-4] = _mm_unpackhi_epi8(v74, (__m128i)0LL);
                v76 = _mm_loadu_si128(v42 - 2);
                v44[-6] = _mm_unpacklo_epi8(v75, (__m128i)0LL);
                v44[-5] = _mm_unpacklo_epi8(v76, (__m128i)0LL);
                v44[-3] = _mm_unpackhi_epi8(v75, (__m128i)0LL);
                v44[-2] = _mm_unpackhi_epi8(v76, (__m128i)0LL);
                --v50;
              }
              while ( v50 );
              v77 = _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v93), v94), v95), si128);
              v78 = _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v96), v97), v98), si128);
              v79 = _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(v99), v99[1]), v99[2]), si128);
              *v31 = _mm_srli_epi16(
                       _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v90), v91), v92), si128),
                       6u);
              v31[1] = _mm_srli_epi16(v77, 6u);
              v31[2] = _mm_srli_epi16(v78, 6u);
              v31[3] = _mm_srli_epi16(v79, 6u);
              v31 += 4;
              --v35;
            }
            while ( v35 );
            v13 = v114;
            v14 = v110;
            v12 = v107;
          }
          if ( v29 < v12 )
          {
            v80 = v27 - v25;
            v81 = v26 - v25;
            v82 = &v25[4 * v29];
            v83 = (unsigned int)(v12 - v29);
            do
            {
              v84 = v82[v80];
              v31 = (__m128i *)((char *)v31 + 2);
              v85 = v82[v81];
              v82 += 4;
              v31[-1].m128i_i16[7] = (85 * ((unsigned int)*(v82 - 4) + v84 + v85)) >> 6;
              --v83;
            }
            while ( v83 );
            v13 = v114;
            v14 = v110;
            v12 = v107;
          }
          v11 = v101[0];
          v86 = v13++;
          v14 -= v113[v86];
          if ( v13 >= v115 )
            v13 = 0;
          ++v112;
          v114 = v13;
        }
        v11 += *a3;
        v10 = v88 + 1;
        v101[0] = v11;
        v88 = v10;
      }
      while ( v10 < v106 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18009a970  push    rbp
0x18009a972  push    rbx
0x18009a973  push    r12
0x18009a975  push    r13
0x18009a977  lea     rbp, [rsp-7C8h]
0x18009a97f  sub     rsp, 8C8h
0x18009a986  mov     rax, cs:__security_cookie
0x18009a98d  xor     rax, rsp
0x18009a990  mov     [rbp+7E0h+var_F0], rax
0x18009a997  movups  xmm0, xmmword ptr [r9]
0x18009a99b  lea     rax, [rcx+8]
0x18009a99f  mov     [rsp+8E0h+var_8A8], r8
0x18009a9a4  mov     [rsp+8E0h+var_8B8], rax
0x18009a9a9  mov     rbx, rdx
0x18009a9ac  mov     edx, 1
0x18009a9b1  movaps  xmmword ptr [rbp+7E0h+var_7D0], xmm0
0x18009a9b5  lea     rax, [rbp+7E0h+var_7D0]
0x18009a9b9  mov     r13, rcx
0x18009a9bc  mov     r9, r8
0x18009a9bf  mov     [rsp+8E0h+var_8C0], rax
0x18009a9c4  mov     r8d, edx
0x18009a9c7  lea     rcx, [rbp+7E0h+var_720]
0x18009a9ce  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009a9d3  mov     rcx, [rbx+8]
0x18009a9d7  lea     r9, [rbp+7E0h+var_7D0]; unsigned __int8 **
0x18009a9db  mov     rax, [rbx+10h]
0x18009a9df  lea     r8, [rbp+7E0h+var_7E0]; unsigned __int8 **
0x18009a9e3  mov     rdx, [rbx+18h]
0x18009a9e7  xor     r12d, r12d
0x18009a9ea  cmp     [rbx], rcx
0x18009a9ed  cmovbe  rcx, [rbx]
0x18009a9f1  mov     rbx, [rbp+7E0h+var_718]
0x18009a9f8  cmp     rcx, rax
0x18009a9fb  cmovbe  rax, rcx
0x18009a9ff  lea     rcx, [rbp+7E0h+var_710]; this
0x18009aa06  cmp     rax, rdx
0x18009aa09  cmovbe  rdx, rax; unsigned __int8 *
0x18009aa0d  add     rbx, rdx
0x18009aa10  mov     qword ptr [rbp+7E0h+var_7C0], rbx
0x18009aa14  lea     rax, [rbx+1]
0x18009aa18  mov     qword ptr [rbp+7E0h+var_7C0+8], rax
0x18009aa1c  lea     rax, [rbx+2]
0x18009aa20  mov     [rbp+7E0h+var_7B0], rax
0x18009aa24  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009aa29  test    al, al
0x18009aa2b  jz      loc_18009AFD8
0x18009aa31  mov     [rsp+8E0h+var_38], r15
0x18009aa39  mov     r15d, r12d
0x18009aa3c  mov     [rbp+7E0h+var_7D0], r12
0x18009aa40  mov     dword ptr [rbp+7E0h+var_7E0], 1
0x18009aa47  mov     [rsp+8E0h+var_8B0], r12d
0x18009aa4c  cmp     [rbp+7E0h+var_720], r12d
0x18009aa53  jle     loc_18009AFD0
0x18009aa59  mov     [rsp+8E0h+var_20], rsi
0x18009aa61  mov     esi, [rbp+7E0h+var_71C]
0x18009aa67  mov     [rsp+8E0h+var_28], rdi
0x18009aa6f  mov     edi, [rbp+7E0h+var_10C]
0x18009aa75  mov     [rsp+8E0h+var_30], r14
0x18009aa7d  mov     r14d, [rbp+7E0h+var_6F0]
0x18009aa84  movaps  [rsp+8E0h+var_50], xmm6
0x18009aa8c  movaps  [rsp+8E0h+var_60], xmm7
0x18009aa94  movaps  [rsp+8E0h+var_70], xmm8
0x18009aa9d  movaps  [rsp+8E0h+var_80], xmm9
0x18009aaa6  movaps  [rsp+8E0h+var_90], xmm10
0x18009aaaf  movaps  [rsp+8E0h+var_A0], xmm11
0x18009aab8  movaps  [rsp+8E0h+var_B0], xmm12
0x18009aac1  movaps  [rsp+8E0h+var_C0], xmm13
0x18009aaca  movaps  [rsp+8E0h+var_D0], xmm14
0x18009aad3  movaps  [rsp+8E0h+var_E0], xmm15
0x18009aadc  movups  xmm15, [rbp+7E0h+var_7C0]
0x18009aae1  inc     r14d
0x18009aae4  mov     [rbp+7E0h+var_6F0], r14d
0x18009aaeb  cmp     r14d, 1
0x18009aaef  jnz     loc_18009AF3B
0x18009aaf5  mov     eax, [rbp+7E0h+var_6EC]
0x18009aafb  mov     r11d, r12d
0x18009aafe  mov     ecx, [r13+28h]
0x18009ab02  test    eax, eax
0x18009ab04  mov     r10d, [r13+1Ch]
0x18009ab08  movsxd  r8, dword ptr [r13+34h]
0x18009ab0c  cmovle  r11d, eax
0x18009ab10  mov     eax, [r13+2Ch]
0x18009ab14  cmp     r10d, eax
0x18009ab17  movups  [rbp+7E0h+var_740], xmm15
0x18009ab1f  mov     r12, qword ptr [rbp+7E0h+var_740+8]
0x18009ab26  cmovl   r10d, eax
0x18009ab2a  sub     r10d, eax
0x18009ab2d  lea     r9d, [r8-1]
0x18009ab31  mov     eax, [rbp+7E0h+var_6E8]
0x18009ab37  cmp     eax, ecx
0x18009ab39  cmovl   eax, ecx
0x18009ab3c  sub     eax, ecx
0x18009ab3e  cdq
0x18009ab3f  idiv    dword ptr [r13+30h]
0x18009ab43  movsxd  rcx, edx
0x18009ab46  imul    rcx, r8
0x18009ab4a  cmp     r10d, r9d
0x18009ab4d  cmovle  r9d, r10d
0x18009ab51  add     r12, r15
0x18009ab54  movsxd  rax, r9d
0x18009ab57  lea     r10, [rbx+r15]
0x18009ab5b  add     r15, [rbp+7E0h+var_7B0]
0x18009ab5f  add     rcx, rax
0x18009ab62  mov     rax, [r13+38h]
0x18009ab66  neg     r11d
0x18009ab69  movsxd  r9, [rbp+7E0h+var_F4]
0x18009ab70  lea     r8, [rax+rcx*2]
0x18009ab74  cmp     r9, 1
0x18009ab78  jge     short loc_18009ABD5
0x18009ab7a  nop     word ptr [rax+rax+00h]
0x18009ab80  cmp     r11d, esi
0x18009ab83  jge     short loc_18009ABC2
0x18009ab85  lea     eax, ds:0[r11*4]
0x18009ab8d  movsxd  rcx, eax
0x18009ab90  movzx   eax, byte ptr [r15+rcx]
0x18009ab95  movzx   edx, byte ptr [r12+rcx]
0x18009ab9a  add     edx, eax
0x18009ab9c  movzx   eax, byte ptr [rcx+r10]
0x18009aba1  add     edx, eax
0x18009aba3  imul    eax, edx, 55h ; 'U'
0x18009aba6  shr     eax, 6
0x18009aba9  mov     [r8], ax
0x18009abad  add     r8, 2
0x18009abb1  mov     eax, dword ptr [rbp+r9*4+7E0h+var_7E0]
0x18009abb6  inc     r9
0x18009abb9  add     r11d, eax
0x18009abbc  cmp     r9, 1
0x18009abc0  jl      short loc_18009AB80
0x18009abc2  mov     edi, [rbp+7E0h+var_10C]
0x18009abc8  mov     r14d, [rbp+7E0h+var_6F0]
0x18009abcf  mov     esi, [rbp+7E0h+var_71C]
0x18009abd5  lea     edx, [rsi-1Fh]
0x18009abd8  cmp     r11d, edx
0x18009abdb  jge     loc_18009AEA4
0x18009abe1  movdqa  xmm14, cs:__xmm@00550055005500550055005500550055
0x18009abea  sub     edx, r11d
0x18009abed  movsxd  rcx, r11d
0x18009abf0  xorps   xmm13, xmm13
0x18009abf4  add     rcx, 8
0x18009abf8  lea     eax, [rdx-1]
0x18009abfb  shr     eax, 5
0x18009abfe  inc     eax
0x18009ac00  lea     rcx, [r10+rcx*4]
0x18009ac04  mov     edi, eax
0x18009ac06  shl     eax, 5
0x18009ac09  add     r11d, eax
0x18009ac0c  nop     dword ptr [rax+00h]
0x18009ac10  lea     rax, [rsp+8E0h+var_880]
0x18009ac15  mov     edx, 2
0x18009ac1a  nop     word ptr [rax+rax+00h]
0x18009ac20  movdqu  xmm0, xmmword ptr [rcx-20h]
0x18009ac25  lea     rax, [rax+40h]
0x18009ac29  movdqu  xmm1, xmmword ptr [rcx-10h]
0x18009ac2e  movdqu  xmmword ptr [rax-60h], xmm0
0x18009ac33  movdqu  xmm0, xmmword ptr [rcx]
0x18009ac37  movdqu  xmmword ptr [rax-50h], xmm1
0x18009ac3c  movdqu  xmm1, xmmword ptr [rcx+10h]
0x18009ac41  add     rcx, 40h ; '@'
0x18009ac45  movdqu  xmmword ptr [rax-40h], xmm0
0x18009ac4a  movdqu  xmmword ptr [rax-30h], xmm1
0x18009ac4f  sub     rdx, 1
0x18009ac53  jnz     short loc_18009AC20
0x18009ac55  movdqa  xmm10, [rsp+8E0h+var_8A0]
0x18009ac5c  lea     rdx, [rbp+7E0h+var_790]
0x18009ac60  movdqa  xmm9, [rsp+8E0h+var_890]
0x18009ac67  lea     rax, [rsp+8E0h+var_890]
0x18009ac6c  movdqa  xmm3, [rsp+8E0h+var_880]
0x18009ac72  movdqa  xmm12, xmm10
0x18009ac77  punpcklbw xmm12, [rbp+7E0h+var_860]
0x18009ac7d  movdqa  xmm1, xmm3
0x18009ac81  punpcklbw xmm1, [rbp+7E0h+var_840]
0x18009ac86  movdqa  xmm11, xmm12
0x18009ac8b  punpckhbw xmm3, [rbp+7E0h+var_840]
0x18009ac90  movdqa  xmm8, xmm9
0x18009ac95  punpckhbw xmm10, [rbp+7E0h+var_860]
0x18009ac9b  mov     r9d, 2
0x18009aca1  movdqa  xmm4, [rsp+8E0h+var_870]
0x18009aca7  movdqa  xmm5, xmm10
0x18009acac  punpcklbw xmm8, [rbp+7E0h+var_850]
0x18009acb2  movdqa  xmm2, xmm4
0x18009acb6  punpcklbw xmm2, [rbp+7E0h+var_830]
0x18009acbb  punpckhbw xmm4, [rbp+7E0h+var_830]
0x18009acc0  punpckhbw xmm9, [rbp+7E0h+var_850]
0x18009acc6  punpcklbw xmm11, xmm1
0x18009accb  punpckhbw xmm12, xmm1
0x18009acd0  movdqa  xmm7, xmm11
0x18009acd5  punpcklbw xmm5, xmm3
0x18009acd9  punpckhbw xmm10, xmm3
0x18009acde  movdqa  xmm0, xmm5
0x18009ace2  movdqa  xmm3, xmm8
0x18009ace7  movdqa  xmm1, xmm10
0x18009acec  punpcklbw xmm3, xmm2
0x18009acf0  punpckhbw xmm8, xmm2
0x18009acf5  movdqa  xmm2, xmm9
0x18009acfa  punpcklbw xmm2, xmm4
0x18009acfe  punpcklbw xmm0, xmm2
0x18009ad02  punpckhbw xmm9, xmm4
0x18009ad07  movdqa  xmm4, xmm12
0x18009ad0c  punpcklbw xmm1, xmm9
0x18009ad11  punpcklbw xmm7, xmm3
0x18009ad15  movdqa  xmm6, xmm7
0x18009ad19  punpckhbw xmm5, xmm2
0x18009ad1d  punpcklbw xmm6, xmm0
0x18009ad21  punpckhbw xmm7, xmm0
0x18009ad25  movdqa  xmm2, xmm6
0x18009ad29  punpcklbw xmm4, xmm8
0x18009ad2e  movdqa  xmm0, xmm4
0x18009ad32  punpckhbw xmm11, xmm3
0x18009ad37  punpcklbw xmm0, xmm1
0x18009ad3b  punpcklbw xmm2, xmm0
0x18009ad3f  punpckhbw xmm6, xmm0
0x18009ad43  punpckhbw xmm4, xmm1
0x18009ad47  movdqa  xmm1, xmm7
0x18009ad4b  punpcklbw xmm11, xmm5
0x18009ad50  movdqa  xmm0, xmm11
0x18009ad55  punpckhbw xmm12, xmm8
0x18009ad5a  punpckhbw xmm10, xmm9
0x18009ad5f  punpcklbw xmm12, xmm10
0x18009ad64  punpcklbw xmm0, xmm12
0x18009ad69  punpcklbw xmm1, xmm4
0x18009ad6d  punpckhbw xmm7, xmm4
0x18009ad71  punpckhbw xmm11, xmm12
0x18009ad76  movaps  [rbp+7E0h+var_780], xmm0
0x18009ad7a  movaps  [rbp+7E0h+var_7A0], xmm2
0x18009ad7e  movaps  [rbp+7E0h+var_790], xmm1
0x18009ad82  movaps  [rbp+7E0h+var_770], xmm6
0x18009ad86  movaps  [rbp+7E0h+var_760], xmm7
0x18009ad8d  movaps  [rbp+7E0h+var_750], xmm11
0x18009ad95  nop     word ptr [rax+rax+00000000h]
0x18009ada0  movdqu  xmm1, xmmword ptr [rdx-10h]
0x18009ada5  lea     rax, [rax+60h]
0x18009ada9  movdqu  xmm2, xmmword ptr [rdx]
0x18009adad  movdqa  xmm0, xmm1
0x18009adb1  punpcklbw xmm0, xmm13
0x18009adb6  lea     rdx, [rdx+30h]
0x18009adba  movdqu  xmmword ptr [rax-70h], xmm0
0x18009adbf  movdqa  xmm0, xmm2
0x18009adc3  punpckhbw xmm1, xmm13
0x18009adc8  punpcklbw xmm0, xmm13
0x18009adcd  movdqu  xmmword ptr [rax-40h], xmm1
0x18009add2  movdqu  xmm1, xmmword ptr [rdx-20h]
0x18009add7  movdqu  xmmword ptr [rax-60h], xmm0
0x18009addc  movdqa  xmm0, xmm1
0x18009ade0  punpcklbw xmm0, xmm13
0x18009ade5  punpckhbw xmm2, xmm13
0x18009adea  punpckhbw xmm1, xmm13
0x18009adef  movdqu  xmmword ptr [rax-50h], xmm0
0x18009adf4  movdqu  xmmword ptr [rax-30h], xmm2
0x18009adf9  movdqu  xmmword ptr [rax-20h], xmm1
0x18009adfe  sub     r9, 1
0x18009ae02  jnz     short loc_18009ADA0
0x18009ae04  movdqa  xmm3, [rsp+8E0h+var_8A0]
0x18009ae0a  paddw   xmm3, [rsp+8E0h+var_890]
0x18009ae10  paddw   xmm3, [rsp+8E0h+var_880]
0x18009ae16  movdqa  xmm2, [rsp+8E0h+var_870]
0x18009ae1c  paddw   xmm2, [rbp+7E0h+var_860]
0x18009ae21  paddw   xmm2, [rbp+7E0h+var_850]
0x18009ae26  movdqa  xmm1, [rbp+7E0h+var_840]
0x18009ae2b  paddw   xmm1, [rbp+7E0h+var_830]
0x18009ae30  paddw   xmm1, [rbp+7E0h+var_820]
0x18009ae35  movdqa  xmm0, [rbp+7E0h+var_810]
0x18009ae3a  paddw   xmm0, [rbp+7E0h+var_800]
0x18009ae3f  paddw   xmm0, [rbp+7E0h+var_7F0]
0x18009ae44  pmullw  xmm3, xmm14
0x18009ae49  pmullw  xmm2, xmm14
0x18009ae4e  pmullw  xmm1, xmm14
0x18009ae53  pmullw  xmm0, xmm14
0x18009ae58  psrlw   xmm3, 6
0x18009ae5d  movdqu  xmmword ptr [r8], xmm3
0x18009ae62  psrlw   xmm2, 6
0x18009ae67  movdqu  xmmword ptr [r8+10h], xmm2
0x18009ae6d  psrlw   xmm1, 6
0x18009ae72  movdqu  xmmword ptr [r8+20h], xmm1
0x18009ae78  psrlw   xmm0, 6
0x18009ae7d  movdqu  xmmword ptr [r8+30h], xmm0
0x18009ae83  add     r8, 40h ; '@'
0x18009ae87  sub     rdi, 1
0x18009ae8b  jnz     loc_18009AC10
0x18009ae91  mov     edi, [rbp+7E0h+var_10C]
0x18009ae97  mov     r14d, [rbp+7E0h+var_6F0]
0x18009ae9e  mov     esi, [rbp+7E0h+var_71C]
0x18009aea4  cmp     r11d, esi
0x18009aea7  jge     short loc_18009AF0E
0x18009aea9  lea     eax, ds:0[r11*4]
0x18009aeb1  sub     r15, r12
0x18009aeb4  movsxd  rdx, eax
0x18009aeb7  sub     r10, r12
0x18009aeba  add     rdx, r12
0x18009aebd  sub     esi, r11d
0x18009aec0  mov     r9d, esi
0x18009aec3  nop     dword ptr [rax+00h]
0x18009aec7  nop     word ptr [rax+rax+00000000h]
0x18009aed0  movzx   eax, byte ptr [r15+rdx]
0x18009aed5  lea     r8, [r8+2]
0x18009aed9  movzx   ecx, byte ptr [r10+rdx]
0x18009aede  lea     rdx, [rdx+4]
0x18009aee2  add     ecx, eax
0x18009aee4  movzx   eax, byte ptr [rdx-4]
0x18009aee8  add     ecx, eax
0x18009aeea  imul    eax, ecx, 55h ; 'U'
  ... truncated ...
```
