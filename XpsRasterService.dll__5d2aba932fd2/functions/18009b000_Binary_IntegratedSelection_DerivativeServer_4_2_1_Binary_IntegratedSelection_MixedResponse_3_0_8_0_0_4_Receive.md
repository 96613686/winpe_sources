# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009b000`
- end: `0x18009b6cb`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$03$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1739`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d5d0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x18009b000`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(
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
  int v11; // ecx
  __int64 v12; // r12
  int v13; // edx
  int v14; // esi
  int v15; // edi
  int v16; // r11d
  int v17; // ecx
  int v18; // edx
  int v19; // r10d
  __int64 v20; // r8
  int v21; // r10d
  int v22; // r9d
  int v23; // eax
  unsigned __int8 *v24; // rsi
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r15
  __int64 v28; // r14
  _WORD *v29; // r9
  __m128i *v30; // r9
  int v31; // edx
  __int64 i; // r10
  __int64 v33; // r8
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // r10d
  __m128i si128; // xmm14
  __m128i v38; // xmm15
  __int64 v39; // r11
  const __m128i *v40; // rcx
  __m128i *v41; // rax
  __int64 v42; // rdx
  __m128i v43; // xmm1
  __m128i v44; // xmm0
  __m128i v45; // xmm1
  __m128i v46; // xmm11
  const __m128i *v47; // rdx
  __m128i v48; // xmm10
  __m128i *v49; // rax
  __m128i v50; // xmm12
  __m128i v51; // xmm1
  __m128i v52; // xmm3
  __m128i v53; // xmm1
  __m128i v54; // xmm11
  __int64 v55; // r8
  __m128i v56; // xmm4
  __m128i v57; // xmm9
  __m128i v58; // xmm2
  __m128i v59; // xmm4
  __m128i v60; // xmm10
  __m128i v61; // xmm8
  __m128i v62; // xmm12
  __m128i v63; // xmm5
  __m128i v64; // xmm11
  __m128i v65; // xmm3
  __m128i v66; // xmm9
  __m128i v67; // xmm2
  __m128i v68; // xmm10
  __m128i v69; // xmm0
  __m128i v70; // xmm6
  __m128i v71; // xmm7
  __m128i v72; // xmm1
  __m128i v73; // xmm1
  __m128i v74; // xmm2
  __m128i v75; // xmm1
  __m128i v76; // xmm1
  __m128i v77; // xmm0
  __m128i v78; // xmm3
  __m128i v79; // xmm2
  __m128i v80; // xmm0
  __m128i v81; // xmm1
  int v82; // r10d
  __int64 v83; // r14
  unsigned __int8 *v84; // rsi
  unsigned __int8 *v85; // rdx
  __int64 v86; // r8
  unsigned int v87; // ecx
  int v88; // ecx
  __m128i v91; // [rsp+40h] [rbp-C0h] BYREF
  __m128i v92; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v93; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v94; // [rsp+70h] [rbp-90h] BYREF
  __m128i v95; // [rsp+80h] [rbp-80h]
  __m128i v96; // [rsp+90h] [rbp-70h]
  __m128i v97; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v98; // [rsp+B0h] [rbp-50h]
  __m128i v99; // [rsp+C0h] [rbp-40h]
  __m128i v100[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v101[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v102[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v103; // [rsp+120h] [rbp+20h]
  __int64 v104; // [rsp+130h] [rbp+30h]
  __m128i v105; // [rsp+140h] [rbp+40h]
  _OWORD v106[7]; // [rsp+150h] [rbp+50h] BYREF
  int v107; // [rsp+1C0h] [rbp+C0h] BYREF
  int v108; // [rsp+1C4h] [rbp+C4h]
  __int64 v109; // [rsp+1C8h] [rbp+C8h]
  char v110[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v111; // [rsp+1F0h] [rbp+F0h]
  int v112; // [rsp+1F4h] [rbp+F4h]
  int v113; // [rsp+1F8h] [rbp+F8h]
  _DWORD v114[374]; // [rsp+1FCh] [rbp+FCh]
  int v115; // [rsp+7D4h] [rbp+6D4h]
  int v116; // [rsp+7DCh] [rbp+6DCh]
  int v117; // [rsp+7ECh] [rbp+6ECh]

  *(_OWORD *)v102 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v107, 2, 1, (_DWORD)a3, (__int64)v102, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v109];
  *(_QWORD *)&v103 = &v8[v109];
  *((_QWORD *)&v103 + 1) = &v8[v109 + 1];
  v104 = (__int64)&v8[v109 + 2];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v110,
                  v8,
                  v101,
                  v102);
  if ( (_BYTE)v10 )
  {
    v11 = v107;
    v12 = 0;
    LODWORD(v101[0]) = 2;
    LODWORD(v102[0]) = 0;
    if ( v107 > 0 )
    {
      v13 = v111;
      v14 = v113;
      v15 = v108;
      do
      {
        v111 = ++v13;
        if ( v13 == 1 )
        {
          v16 = 0;
          v17 = *(_DWORD *)(a1 + 44);
          v18 = *(_DWORD *)(a1 + 40);
          v19 = *(_DWORD *)(a1 + 28);
          if ( v112 <= 0 )
            v16 = v112;
          v20 = *(int *)(a1 + 52);
          if ( v19 < v17 )
            v19 = *(_DWORD *)(a1 + 44);
          v21 = v19 - v17;
          v22 = v20 - 1;
          v106[5] = v103;
          if ( v14 < v18 )
            v14 = v18;
          v23 = v14 - v18;
          v24 = &v9[v12];
          v25 = v20 * (v23 % *(_DWORD *)(a1 + 48));
          v26 = v117;
          if ( v21 <= v22 )
            v22 = v21;
          v27 = v12 + *((_QWORD *)&v103 + 1);
          v28 = v12 + v104;
          v29 = (_WORD *)(*(_QWORD *)(a1 + 56) + 2 * v25 + 2LL * v22);
          *v29 = (85
                * (*(unsigned __int8 *)(-4 * v16 + v12 + *((_QWORD *)&v103 + 1))
                 + *(unsigned __int8 *)(-4 * v16 + v12 + v104)
                 + (unsigned int)v24[-4 * v16])) >> 6;
          v30 = (__m128i *)(v29 + 1);
          v31 = *((_DWORD *)v101 + v26) - v16;
          for ( i = (int)v26 + 1; i < 1; v31 += v35 )
          {
            if ( v31 >= v15 )
              break;
            v33 = 4 * v31;
            v34 = v24[v33] + *(unsigned __int8 *)(v28 + v33) + *(unsigned __int8 *)(v27 + v33);
            if ( v34 > 0x2F4 )
              v34 = v24[v33 - 4] + *(unsigned __int8 *)(v28 + v33 - 4) + *(unsigned __int8 *)(v27 + v33 - 4);
            v30->m128i_i16[0] = (85 * v34) >> 6;
            v30 = (__m128i *)((char *)v30 + 2);
            v35 = *((_DWORD *)v101 + i++);
          }
          v15 = v108;
          v36 = v31 - 1;
          if ( v31 - 1 < v108 - 31 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v38 = _mm_load_si128((const __m128i *)&_xmm);
            v39 = ((unsigned int)(v108 - 31 - v31) >> 5) + 1;
            v40 = (const __m128i *)&v24[4 * v36 + 32];
            v36 += 32 * v39;
            do
            {
              v41 = &v93;
              v42 = 2;
              do
              {
                v41 += 4;
                v43 = _mm_loadu_si128(v40 - 1);
                v41[-6] = _mm_loadu_si128(v40 - 2);
                v44 = _mm_loadu_si128(v40);
                v41[-5] = v43;
                v45 = _mm_loadu_si128(v40 + 1);
                v40 += 4;
                v41[-4] = v44;
                v41[-3] = v45;
                --v42;
              }
              while ( v42 );
              v46 = _mm_load_si128(&v91);
              v47 = (const __m128i *)v106;
              v48 = _mm_load_si128(&v92);
              v49 = &v92;
              v50 = _mm_unpacklo_epi8(v46, v95);
              v51 = _mm_load_si128(&v93);
              v52 = _mm_unpackhi_epi8(v51, v97);
              v53 = _mm_unpacklo_epi8(v51, v97);
              v54 = _mm_unpackhi_epi8(v46, v95);
              v55 = 2;
              v56 = _mm_load_si128(&v94);
              v57 = _mm_unpacklo_epi8(v48, v96);
              v58 = _mm_unpacklo_epi8(v56, v98);
              v59 = _mm_unpackhi_epi8(v56, v98);
              v60 = _mm_unpackhi_epi8(v48, v96);
              v61 = _mm_unpacklo_epi8(v50, v53);
              v62 = _mm_unpackhi_epi8(v50, v53);
              v63 = _mm_unpacklo_epi8(v54, v52);
              v64 = _mm_unpackhi_epi8(v54, v52);
              v65 = _mm_unpacklo_epi8(v57, v58);
              v66 = _mm_unpackhi_epi8(v57, v58);
              v67 = _mm_unpacklo_epi8(v60, v59);
              v68 = _mm_unpackhi_epi8(v60, v59);
              v69 = _mm_unpacklo_epi8(v63, v67);
              v70 = _mm_unpacklo_epi8(v61, v65);
              v71 = _mm_unpacklo_epi8(v62, v66);
              v72 = _mm_unpacklo_epi8(v64, v68);
              v106[2] = _mm_unpacklo_epi8(v71, v72);
              v105 = _mm_unpacklo_epi8(v70, v69);
              v106[0] = _mm_unpackhi_epi8(v70, v69);
              v106[1] = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v61, v65), _mm_unpackhi_epi8(v63, v67));
              v106[3] = _mm_unpackhi_epi8(v71, v72);
              v106[4] = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v62, v66), _mm_unpackhi_epi8(v64, v68));
              do
              {
                v73 = _mm_loadu_si128(v47 - 1);
                v49 += 6;
                v74 = _mm_loadu_si128(v47);
                v47 += 3;
                v49[-7] = _mm_unpacklo_epi8(v73, (__m128i)0LL);
                v49[-4] = _mm_unpackhi_epi8(v73, (__m128i)0LL);
                v75 = _mm_loadu_si128(v47 - 2);
                v49[-6] = _mm_unpacklo_epi8(v74, (__m128i)0LL);
                v49[-5] = _mm_unpacklo_epi8(v75, (__m128i)0LL);
                v49[-3] = _mm_unpackhi_epi8(v74, (__m128i)0LL);
                v49[-2] = _mm_unpackhi_epi8(v75, (__m128i)0LL);
                --v55;
              }
              while ( v55 );
              v76 = _mm_srli_epi16(
                      _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v97), v98), v99), si128),
                      6u);
              v77 = _mm_cmpgt_epi16(v76, v38);
              v78 = _mm_srli_epi16(
                      _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(v100), v100[1]), v100[2]), si128),
                      6u);
              v79 = _mm_add_epi16(
                      _mm_and_si128(
                        _mm_srli_epi16(
                          _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v91), v92), v93), si128),
                          6u),
                        v77),
                      _mm_andnot_si128(v77, v76));
              v80 = _mm_cmpgt_epi16(v78, v38);
              v81 = _mm_mullo_epi16(_mm_add_epi16(_mm_add_epi16(_mm_load_si128(&v94), v95), v96), si128);
              *v30 = v79;
              v30[1] = _mm_add_epi16(_mm_and_si128(_mm_srli_epi16(v81, 6u), v80), _mm_andnot_si128(v80, v78));
              v30 += 2;
              --v39;
            }
            while ( v39 );
            v15 = v108;
          }
          v82 = v36 + 1;
          if ( v82 < v15 )
          {
            v83 = v28 - v27;
            v84 = &v24[-v27];
            v85 = (unsigned __int8 *)(v27 + 4 * v82 - 4LL);
            v86 = ((unsigned int)(v15 - v82 - 1) >> 1) + 1;
            do
            {
              v87 = v85[4] + v85[(_QWORD)v84 + 4] + v85[v83 + 4];
              if ( v87 > 0x2F4 )
                v87 = *v85 + v85[v83] + v85[(_QWORD)v84];
              v85 += 8;
              v30->m128i_i16[0] = (85 * v87) >> 6;
              v30 = (__m128i *)((char *)v30 + 2);
              --v86;
            }
            while ( v86 );
            v15 = v108;
          }
          v13 = v111 - v114[v115];
          v88 = v115 + 1;
          if ( v115 + 1 >= v116 )
            v88 = 0;
          v14 = v113 + 1;
          v115 = v88;
          v11 = v107;
          ++v113;
        }
        v12 += *a3;
        v10 = LODWORD(v102[0]) + 1;
        LODWORD(v102[0]) = v10;
      }
      while ( v10 < v11 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18009b000  push    rbp
0x18009b002  push    rbx
0x18009b003  push    r13
0x18009b005  push    r14
0x18009b007  lea     rbp, [rsp-7C8h]
0x18009b00f  sub     rsp, 8C8h
0x18009b016  mov     rax, cs:__security_cookie
0x18009b01d  xor     rax, rsp
0x18009b020  mov     [rbp+7E0h+var_F0], rax
0x18009b027  movups  xmm0, xmmword ptr [r9]
0x18009b02b  lea     rax, [rcx+8]
0x18009b02f  mov     [rsp+8E0h+var_8B0], r8
0x18009b034  mov     [rsp+8E0h+var_8B8], rax
0x18009b039  mov     rbx, rdx
0x18009b03c  mov     edx, 2
0x18009b041  movaps  xmmword ptr [rbp+7E0h+var_7D0], xmm0
0x18009b045  mov     r13, rcx
0x18009b048  lea     rax, [rbp+7E0h+var_7D0]
0x18009b04c  mov     r9, r8
0x18009b04f  mov     [rsp+8E0h+var_8C0], rax
0x18009b054  lea     rcx, [rbp+7E0h+var_720]
0x18009b05b  lea     r8d, [rdx-1]
0x18009b05f  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009b064  mov     rcx, [rbx+8]
0x18009b068  lea     r9, [rbp+7E0h+var_7D0]; unsigned __int8 **
0x18009b06c  mov     rax, [rbx+10h]
0x18009b070  lea     r8, [rbp+7E0h+var_7E0]; unsigned __int8 **
0x18009b074  mov     rdx, [rbx+18h]
0x18009b078  xor     r14d, r14d
0x18009b07b  cmp     [rbx], rcx
0x18009b07e  cmovbe  rcx, [rbx]
0x18009b082  mov     rbx, [rbp+7E0h+var_718]
0x18009b089  cmp     rcx, rax
0x18009b08c  cmovbe  rax, rcx
0x18009b090  lea     rcx, [rbp+7E0h+var_710]; this
0x18009b097  cmp     rax, rdx
0x18009b09a  cmovbe  rdx, rax; unsigned __int8 *
0x18009b09e  add     rbx, rdx
0x18009b0a1  mov     qword ptr [rbp+7E0h+var_7C0], rbx
0x18009b0a5  lea     rax, [rbx+1]
0x18009b0a9  mov     qword ptr [rbp+7E0h+var_7C0+8], rax
0x18009b0ad  lea     rax, [rbx+2]
0x18009b0b1  mov     [rbp+7E0h+var_7B0], rax
0x18009b0b5  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009b0ba  test    al, al
0x18009b0bc  jz      loc_18009B6AE
0x18009b0c2  mov     ecx, [rbp+7E0h+var_720]
0x18009b0c8  mov     [rsp+8E0h+var_30], r12
0x18009b0d0  mov     r12d, r14d
0x18009b0d3  mov     dword ptr [rbp+7E0h+var_7E0], 2
0x18009b0da  mov     dword ptr [rbp+7E0h+var_7D0], r14d
0x18009b0de  test    ecx, ecx
0x18009b0e0  jle     loc_18009B6A6
0x18009b0e6  mov     edx, [rbp+7E0h+var_6F0]
0x18009b0ec  mov     [rsp+8E0h+var_20], rsi
0x18009b0f4  mov     esi, [rbp+7E0h+var_6E8]
0x18009b0fa  mov     [rsp+8E0h+var_28], rdi
0x18009b102  mov     edi, [rbp+7E0h+var_71C]
0x18009b108  mov     [rsp+8E0h+var_38], r15
0x18009b110  movaps  [rsp+8E0h+var_50], xmm6
0x18009b118  movaps  [rsp+8E0h+var_60], xmm7
0x18009b120  movaps  [rsp+8E0h+var_70], xmm8
0x18009b129  movaps  [rsp+8E0h+var_80], xmm9
0x18009b132  movaps  [rsp+8E0h+var_90], xmm10
0x18009b13b  movaps  [rsp+8E0h+var_A0], xmm11
0x18009b144  movaps  [rsp+8E0h+var_B0], xmm12
0x18009b14d  movaps  [rsp+8E0h+var_C0], xmm13
0x18009b156  movaps  [rsp+8E0h+var_D0], xmm14
0x18009b15f  movaps  [rsp+8E0h+var_E0], xmm15
0x18009b168  nop     dword ptr [rax+rax+00000000h]
0x18009b170  inc     edx
0x18009b172  mov     [rbp+7E0h+var_6F0], edx
0x18009b178  cmp     edx, 1
0x18009b17b  jnz     loc_18009B61B
0x18009b181  mov     eax, [rbp+7E0h+var_6EC]
0x18009b187  mov     r11d, r14d
0x18009b18a  mov     ecx, [r13+2Ch]
0x18009b18e  test    eax, eax
0x18009b190  mov     edx, [r13+28h]
0x18009b194  mov     r10d, [r13+1Ch]
0x18009b198  cmovle  r11d, eax
0x18009b19c  movsxd  r8, dword ptr [r13+34h]
0x18009b1a0  cmp     r10d, ecx
0x18009b1a3  movups  xmm0, [rbp+7E0h+var_7C0]
0x18009b1a7  mov     r14, [rbp+7E0h+var_7B0]
0x18009b1ab  cmovl   r10d, ecx
0x18009b1af  sub     r10d, ecx
0x18009b1b2  cmp     esi, edx
0x18009b1b4  lea     r9d, [r8-1]
0x18009b1b8  movups  [rbp+7E0h+var_740], xmm0
0x18009b1bf  mov     r15, qword ptr [rbp+7E0h+var_740+8]
0x18009b1c6  cmovl   esi, edx
0x18009b1c9  sub     esi, edx
0x18009b1cb  mov     eax, esi
0x18009b1cd  lea     rsi, [rbx+r12]
0x18009b1d1  cdq
0x18009b1d2  idiv    dword ptr [r13+30h]
0x18009b1d6  mov     rax, [r13+38h]
0x18009b1da  movsxd  rcx, edx
0x18009b1dd  imul    rcx, r8
0x18009b1e1  movsxd  r8, [rbp+7E0h+var_F4]
0x18009b1e8  cmp     r10d, r9d
0x18009b1eb  cmovle  r9d, r10d
0x18009b1ef  add     r15, r12
0x18009b1f2  add     r14, r12
0x18009b1f5  lea     rax, [rax+rcx*2]
0x18009b1f9  movsxd  rcx, r9d
0x18009b1fc  lea     r9, [rax+rcx*2]
0x18009b200  mov     eax, r11d
0x18009b203  neg     eax
0x18009b205  shl     eax, 2
0x18009b208  movsxd  rcx, eax
0x18009b20b  movzx   eax, byte ptr [rcx+r14]
0x18009b210  movzx   edx, byte ptr [rsi+rcx]
0x18009b214  add     edx, eax
0x18009b216  movzx   eax, byte ptr [rcx+r15]
0x18009b21b  add     edx, eax
0x18009b21d  imul    eax, edx, 55h ; 'U'
0x18009b220  shr     eax, 6
0x18009b223  mov     [r9], ax
0x18009b227  lea     eax, [r8+1]
0x18009b22b  mov     edx, dword ptr [rbp+r8*4+7E0h+var_7E0]
0x18009b230  add     r9, 2
0x18009b234  sub     edx, r11d
0x18009b237  movsxd  r10, eax
0x18009b23a  cmp     r10, 1
0x18009b23e  jge     short loc_18009B29D
0x18009b240  cmp     edx, edi
0x18009b242  jge     short loc_18009B29D
0x18009b244  lea     eax, ds:0[rdx*4]
0x18009b24b  movsxd  r8, eax
0x18009b24e  movzx   eax, byte ptr [r14+r8]
0x18009b253  movzx   ecx, byte ptr [r15+r8]
0x18009b258  add     ecx, eax
0x18009b25a  movzx   eax, byte ptr [r8+rsi]
0x18009b25f  add     ecx, eax
0x18009b261  cmp     ecx, 2F4h
0x18009b267  jbe     short loc_18009B27F
0x18009b269  movzx   eax, byte ptr [r14+r8-4]
0x18009b26f  movzx   ecx, byte ptr [r15+r8-4]
0x18009b275  add     ecx, eax
0x18009b277  movzx   eax, byte ptr [r8+rsi-4]
0x18009b27d  add     ecx, eax
0x18009b27f  imul    eax, ecx, 55h ; 'U'
0x18009b282  shr     eax, 6
0x18009b285  mov     [r9], ax
0x18009b289  add     r9, 2
0x18009b28d  mov     eax, dword ptr [rbp+r10*4+7E0h+var_7E0]
0x18009b292  inc     r10
0x18009b295  add     edx, eax
0x18009b297  cmp     r10, 1
0x18009b29b  jl      short loc_18009B240
0x18009b29d  mov     edi, [rbp+7E0h+var_71C]
0x18009b2a3  lea     r10d, [rdx-1]
0x18009b2a7  lea     edx, [rdi-1Fh]
0x18009b2aa  cmp     r10d, edx
0x18009b2ad  jge     loc_18009B565
0x18009b2b3  movdqa  xmm14, cs:__xmm@00550055005500550055005500550055
0x18009b2bc  sub     edx, r10d
0x18009b2bf  movdqa  xmm15, cs:__xmm@03ec03ec03ec03ec03ec03ec03ec03ec
0x18009b2c8  xorps   xmm13, xmm13
0x18009b2cc  movsxd  rcx, r10d
0x18009b2cf  add     rcx, 8
0x18009b2d3  lea     eax, [rdx-1]
0x18009b2d6  shr     eax, 5
0x18009b2d9  inc     eax
0x18009b2db  mov     r11d, eax
0x18009b2de  lea     rcx, [rsi+rcx*4]
0x18009b2e2  shl     eax, 5
0x18009b2e5  add     r10d, eax
0x18009b2e8  nop     dword ptr [rax+rax+00000000h]
0x18009b2f0  lea     rax, [rsp+8E0h+var_880]
0x18009b2f5  mov     edx, 2
0x18009b2fa  nop     word ptr [rax+rax+00h]
0x18009b300  movdqu  xmm0, xmmword ptr [rcx-20h]
0x18009b305  lea     rax, [rax+40h]
0x18009b309  movdqu  xmm1, xmmword ptr [rcx-10h]
0x18009b30e  movdqu  xmmword ptr [rax-60h], xmm0
0x18009b313  movdqu  xmm0, xmmword ptr [rcx]
0x18009b317  movdqu  xmmword ptr [rax-50h], xmm1
0x18009b31c  movdqu  xmm1, xmmword ptr [rcx+10h]
0x18009b321  add     rcx, 40h ; '@'
0x18009b325  movdqu  xmmword ptr [rax-40h], xmm0
0x18009b32a  movdqu  xmmword ptr [rax-30h], xmm1
0x18009b32f  sub     rdx, 1
0x18009b333  jnz     short loc_18009B300
0x18009b335  movdqa  xmm11, [rsp+8E0h+var_8A0]
0x18009b33c  lea     rdx, [rbp+7E0h+var_790]
0x18009b340  movdqa  xmm10, [rsp+8E0h+var_890]
0x18009b347  lea     rax, [rsp+8E0h+var_890]
0x18009b34c  movdqa  xmm3, [rsp+8E0h+var_880]
0x18009b352  movdqa  xmm12, xmm11
0x18009b357  punpcklbw xmm12, [rbp+7E0h+var_860]
0x18009b35d  movdqa  xmm1, xmm3
0x18009b361  punpckhbw xmm3, [rbp+7E0h+var_840]
0x18009b366  movdqa  xmm8, xmm12
0x18009b36b  punpcklbw xmm1, [rbp+7E0h+var_840]
0x18009b370  movdqa  xmm9, xmm10
0x18009b375  punpckhbw xmm11, [rbp+7E0h+var_860]
0x18009b37b  mov     r8d, 2
0x18009b381  movdqa  xmm4, [rsp+8E0h+var_870]
0x18009b387  movdqa  xmm5, xmm11
0x18009b38c  punpcklbw xmm9, [rbp+7E0h+var_850]
0x18009b392  movdqa  xmm2, xmm4
0x18009b396  punpcklbw xmm2, [rbp+7E0h+var_830]
0x18009b39b  punpckhbw xmm4, [rbp+7E0h+var_830]
0x18009b3a0  punpckhbw xmm10, [rbp+7E0h+var_850]
0x18009b3a6  punpcklbw xmm8, xmm1
0x18009b3ab  punpckhbw xmm12, xmm1
0x18009b3b0  movdqa  xmm6, xmm8
0x18009b3b5  punpcklbw xmm5, xmm3
0x18009b3b9  movdqa  xmm7, xmm12
0x18009b3be  punpckhbw xmm11, xmm3
0x18009b3c3  movdqa  xmm0, xmm5
0x18009b3c7  movdqa  xmm3, xmm9
0x18009b3cc  movdqa  xmm1, xmm11
0x18009b3d1  punpcklbw xmm3, xmm2
0x18009b3d5  punpckhbw xmm9, xmm2
0x18009b3da  movdqa  xmm2, xmm10
0x18009b3df  punpcklbw xmm2, xmm4
0x18009b3e3  punpckhbw xmm10, xmm4
0x18009b3e8  punpcklbw xmm0, xmm2
0x18009b3ec  punpcklbw xmm6, xmm3
0x18009b3f0  movdqa  xmm4, xmm6
0x18009b3f4  punpcklbw xmm7, xmm9
0x18009b3f9  punpcklbw xmm4, xmm0
0x18009b3fd  punpckhbw xmm6, xmm0
0x18009b401  movdqa  xmm0, xmm7
0x18009b405  punpcklbw xmm1, xmm10
0x18009b40a  punpckhbw xmm8, xmm3
0x18009b40f  punpckhbw xmm5, xmm2
0x18009b413  punpckhbw xmm12, xmm9
0x18009b418  punpckhbw xmm11, xmm10
0x18009b41d  punpcklbw xmm0, xmm1
0x18009b421  punpcklbw xmm8, xmm5
0x18009b426  punpckhbw xmm7, xmm1
0x18009b42a  punpcklbw xmm12, xmm11
0x18009b42f  movaps  [rbp+7E0h+var_770], xmm0
0x18009b433  movaps  [rbp+7E0h+var_7A0], xmm4
0x18009b437  movaps  [rbp+7E0h+var_790], xmm6
0x18009b43b  movaps  [rbp+7E0h+var_780], xmm8
0x18009b440  movaps  [rbp+7E0h+var_760], xmm7
0x18009b447  movaps  [rbp+7E0h+var_750], xmm12
0x18009b44f  nop
0x18009b450  movdqu  xmm1, xmmword ptr [rdx-10h]
0x18009b455  lea     rax, [rax+60h]
0x18009b459  movdqu  xmm2, xmmword ptr [rdx]
0x18009b45d  movdqa  xmm0, xmm1
0x18009b461  punpcklbw xmm0, xmm13
0x18009b466  lea     rdx, [rdx+30h]
0x18009b46a  movdqu  xmmword ptr [rax-70h], xmm0
0x18009b46f  movdqa  xmm0, xmm2
0x18009b473  punpckhbw xmm1, xmm13
0x18009b478  punpcklbw xmm0, xmm13
0x18009b47d  movdqu  xmmword ptr [rax-40h], xmm1
0x18009b482  movdqu  xmm1, xmmword ptr [rdx-20h]
0x18009b487  movdqu  xmmword ptr [rax-60h], xmm0
0x18009b48c  movdqa  xmm0, xmm1
0x18009b490  punpcklbw xmm0, xmm13
0x18009b495  punpckhbw xmm2, xmm13
0x18009b49a  punpckhbw xmm1, xmm13
0x18009b49f  movdqu  xmmword ptr [rax-50h], xmm0
0x18009b4a4  movdqu  xmmword ptr [rax-30h], xmm2
0x18009b4a9  movdqu  xmmword ptr [rax-20h], xmm1
0x18009b4ae  sub     r8, 1
0x18009b4b2  jnz     short loc_18009B450
0x18009b4b4  movdqa  xmm1, [rbp+7E0h+var_840]
0x18009b4b9  paddw   xmm1, [rbp+7E0h+var_830]
0x18009b4be  paddw   xmm1, [rbp+7E0h+var_820]
0x18009b4c3  movdqa  xmm2, [rsp+8E0h+var_8A0]
0x18009b4c9  paddw   xmm2, [rsp+8E0h+var_890]
0x18009b4cf  paddw   xmm2, [rsp+8E0h+var_880]
0x18009b4d5  movdqa  xmm3, [rbp+7E0h+var_810]
0x18009b4da  paddw   xmm3, [rbp+7E0h+var_800]
0x18009b4df  paddw   xmm3, [rbp+7E0h+var_7F0]
0x18009b4e4  pmullw  xmm1, xmm14
0x18009b4e9  pmullw  xmm2, xmm14
0x18009b4ee  pmullw  xmm3, xmm14
0x18009b4f3  psrlw   xmm1, 6
0x18009b4f8  movdqa  xmm0, xmm1
0x18009b4fc  psrlw   xmm2, 6
0x18009b501  pcmpgtw xmm0, xmm15
0x18009b506  psrlw   xmm3, 6
0x18009b50b  pand    xmm2, xmm0
0x18009b50f  pandn   xmm0, xmm1
0x18009b513  movdqa  xmm1, [rsp+8E0h+var_870]
0x18009b519  paddw   xmm2, xmm0
0x18009b51d  paddw   xmm1, [rbp+7E0h+var_860]
0x18009b522  movdqa  xmm0, xmm3
0x18009b526  paddw   xmm1, [rbp+7E0h+var_850]
0x18009b52b  pcmpgtw xmm0, xmm15
0x18009b530  pmullw  xmm1, xmm14
0x18009b535  movdqu  xmmword ptr [r9], xmm2
0x18009b53a  psrlw   xmm1, 6
0x18009b53f  pand    xmm1, xmm0
0x18009b543  pandn   xmm0, xmm3
0x18009b547  paddw   xmm1, xmm0
0x18009b54b  movdqu  xmmword ptr [r9+10h], xmm1
0x18009b551  add     r9, 20h ; ' '
0x18009b555  sub     r11, 1
  ... truncated ...
```
