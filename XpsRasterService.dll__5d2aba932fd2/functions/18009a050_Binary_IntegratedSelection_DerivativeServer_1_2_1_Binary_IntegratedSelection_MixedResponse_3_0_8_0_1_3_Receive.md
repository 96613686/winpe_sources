# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009a050`
- end: `0x18009a51a`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$00$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$00@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1226`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d5a0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x18009a050`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  unsigned __int8 *v5; // rbx
  __int64 v6; // rdi
  unsigned __int8 *v7; // rdx
  bool v8; // al
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // rbx
  bool v11; // si
  bool v12; // si
  unsigned __int8 *v13; // r14
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r13
  int v17; // r12d
  int v18; // esi
  int v19; // edx
  int v20; // edi
  unsigned __int8 *v21; // xmm10_8
  __int128 v22; // xmm11
  int v23; // r11d
  int v24; // ecx
  int v25; // edx
  int v26; // r10d
  __int64 v27; // r8
  int v28; // r10d
  int v29; // r9d
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned __int8 *v33; // r10
  int v34; // r11d
  unsigned __int8 *v35; // rsi
  __int64 v36; // r14
  _WORD *v37; // r9
  int v38; // r11d
  __m128i *v39; // r9
  __int64 i; // r8
  unsigned int v41; // ecx
  int v42; // eax
  int v43; // r11d
  __m128i si128; // xmm8
  const __m128i *v45; // r15
  __m128i v46; // xmm9
  unsigned __int64 v47; // rcx
  __m128i v48; // xmm3
  __m128i v49; // xmm6
  __m128i v50; // xmm5
  __m128i v51; // xmm4
  __m128i v52; // xmm1
  __m128i v53; // xmm2
  __m128i v54; // xmm4
  __m128i v55; // xmm3
  __m128i v56; // xmm2
  __m128i v57; // xmm1
  __m128i v58; // xmm0
  int v59; // r11d
  unsigned __int8 *v60; // rsi
  unsigned __int8 *v61; // rdx
  unsigned __int8 *v62; // r10
  __int64 v63; // r8
  unsigned int v64; // eax
  int v65; // ecx
  unsigned __int8 *v69[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v70[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v71; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v72; // [rsp+70h] [rbp-90h]
  int v73; // [rsp+80h] [rbp-80h] BYREF
  int v74; // [rsp+84h] [rbp-7Ch]
  __int64 v75; // [rsp+88h] [rbp-78h]
  _BYTE v76[32]; // [rsp+90h] [rbp-70h] BYREF
  int v77; // [rsp+B0h] [rbp-50h]
  int v78; // [rsp+B4h] [rbp-4Ch]
  int v79; // [rsp+B8h] [rbp-48h]
  _DWORD v80[374]; // [rsp+BCh] [rbp-44h]
  int v81; // [rsp+694h] [rbp+594h]
  int v82; // [rsp+69Ch] [rbp+59Ch]
  int v83; // [rsp+6ACh] [rbp+5ACh]

  *(_OWORD *)v70 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v73, 2, 1, (_DWORD)a3, (__int64)v70, a1 + 8);
  v5 = *a2;
  v6 = v75;
  v7 = *a2;
  *(_QWORD *)&v71 = 0;
  v8 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v76,
         v7,
         v70,
         v69);
  v9 = a2[1];
  v10 = &v5[v6];
  *(_QWORD *)&v71 = v10;
  v11 = v8;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v76,
          v9,
          v70,
          v69)
     && v11;
  v13 = a2[2];
  *((_QWORD *)&v71 + 1) = &v9[v6];
  LOBYTE(v14) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v76,
                  v13,
                  v70,
                  v69);
  if ( (_BYTE)v14 )
  {
    if ( v12 )
    {
      v15 = v73;
      LOBYTE(v14) = (_BYTE)v13 + v6;
      v16 = 0;
      v72 = &v13[v6];
      v17 = 0;
      LODWORD(v69[0]) = 2;
      if ( v73 > 0 )
      {
        v18 = v79;
        v19 = v77;
        v20 = v74;
        v21 = v72;
        v22 = v71;
        do
        {
          v77 = ++v19;
          if ( v19 == 1 )
          {
            v23 = 0;
            v72 = v21;
            if ( v78 <= 0 )
              v23 = v78;
            v24 = *(_DWORD *)(a1 + 44);
            v25 = *(_DWORD *)(a1 + 40);
            v26 = *(_DWORD *)(a1 + 28);
            v27 = *(int *)(a1 + 52);
            if ( v26 < v24 )
              v26 = *(_DWORD *)(a1 + 44);
            v28 = v26 - v24;
            v29 = v27 - 1;
            if ( v18 < v25 )
              v18 = *(_DWORD *)(a1 + 40);
            v30 = *(_QWORD *)(a1 + 56);
            v31 = v27 * ((v18 - v25) % *(_DWORD *)(a1 + 48));
            v71 = v22;
            v32 = v83;
            if ( v28 <= v29 )
              v29 = v28;
            v33 = &v10[v16];
            v34 = -v23;
            v35 = &v72[v16];
            v36 = v16 + *((_QWORD *)&v22 + 1);
            v37 = (_WORD *)(v30 + 2 * v31 + 2LL * v29);
            *v37 = (85
                  * (*(unsigned __int8 *)(v34 + v16 + *((_QWORD *)&v22 + 1))
                   + v72[v16 + v34]
                   + (unsigned int)v10[v16 + v34])) >> 6;
            v38 = *((_DWORD *)v69 + v32) + v34;
            v39 = (__m128i *)(v37 + 1);
            for ( i = (int)v32 + 1; i < 1; v38 += v42 )
            {
              if ( v38 >= v20 )
                break;
              v41 = v35[v38] + *(unsigned __int8 *)(v38 + v36) + v33[v38];
              if ( v41 > 0x2F4 )
                v41 = v35[v38 - 1] + *(unsigned __int8 *)(v38 + v36 - 1) + v33[v38 - 1];
              v39->m128i_i16[0] = (85 * v41) >> 6;
              v39 = (__m128i *)((char *)v39 + 2);
              v42 = *((_DWORD *)v69 + i++);
            }
            v20 = v74;
            v43 = v38 - 1;
            if ( v43 < (__int64)(v74 - 15) )
            {
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              v45 = (const __m128i *)(v43 + v36);
              v46 = _mm_load_si128((const __m128i *)&_xmm);
              v47 = ((unsigned __int64)(v74 - 15 - (__int64)v43 - 1) >> 4) + 1;
              v43 += 16 * v47;
              do
              {
                v48 = _mm_loadu_si128((const __m128i *)&v33[(_QWORD)v45 - v36]);
                v49 = _mm_loadu_si128(v45);
                v50 = _mm_loadu_si128((const __m128i *)&v35[(_QWORD)v45++ - v36]);
                v51 = _mm_shufflehi_epi16(
                        _mm_shufflelo_epi16(
                          _mm_srli_epi16(
                            _mm_mullo_epi16(
                              _mm_add_epi16(
                                _mm_add_epi16(
                                  _mm_unpacklo_epi8(v49, (__m128i)0LL),
                                  _mm_unpacklo_epi8(v48, (__m128i)0LL)),
                                _mm_unpacklo_epi8(v50, (__m128i)0LL)),
                              si128),
                            6u),
                          216),
                        216);
                v52 = _mm_shufflehi_epi16(
                        _mm_shufflelo_epi16(
                          _mm_srli_epi16(
                            _mm_mullo_epi16(
                              _mm_add_epi16(
                                _mm_add_epi16(
                                  _mm_unpackhi_epi8(v49, (__m128i)0LL),
                                  _mm_unpackhi_epi8(v48, (__m128i)0LL)),
                                _mm_unpackhi_epi8(v50, (__m128i)0LL)),
                              si128),
                            6u),
                          216),
                        216);
                v53 = _mm_unpacklo_epi64(v51, v52);
                v54 = _mm_unpackhi_epi64(v51, v52);
                v55 = _mm_unpacklo_epi32(v53, v54);
                v56 = _mm_unpackhi_epi32(v53, v54);
                v57 = _mm_unpackhi_epi64(v55, v56);
                v58 = _mm_cmpgt_epi16(v57, v46);
                *v39++ = _mm_add_epi16(_mm_and_si128(_mm_unpacklo_epi64(v55, v56), v58), _mm_andnot_si128(v58, v57));
                --v47;
              }
              while ( v47 );
              v20 = v74;
            }
            v59 = v43 + 1;
            if ( v59 < v20 )
            {
              v60 = &v35[-v36];
              v61 = (unsigned __int8 *)(v36 + v59 - 1LL);
              v62 = &v33[-v36];
              v63 = ((unsigned int)(v20 - v59 - 1) >> 1) + 1;
              do
              {
                v64 = v61[1] + v61[(_QWORD)v60 + 1] + v61[(_QWORD)v62 + 1];
                if ( v64 > 0x2F4 )
                  v64 = *v61 + v61[(_QWORD)v62] + v61[(_QWORD)v60];
                v61 += 2;
                v39->m128i_i16[0] = (85 * v64) >> 6;
                v39 = (__m128i *)((char *)v39 + 2);
                --v63;
              }
              while ( v63 );
              v20 = v74;
            }
            v19 = v77 - v80[v81];
            v65 = v81 + 1;
            if ( v81 + 1 >= v82 )
              v65 = 0;
            v18 = v79 + 1;
            v81 = v65;
            v15 = v73;
            ++v79;
          }
          ++v17;
          v14 = *a3;
          v16 += v14;
        }
        while ( v17 < v15 );
      }
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18009a050  push    rbp
0x18009a052  push    rbx
0x18009a053  push    rsi
0x18009a054  push    rdi
0x18009a055  push    r14
0x18009a057  push    r15
0x18009a059  lea     rbp, [rsp-638h]
0x18009a061  sub     rsp, 738h
0x18009a068  mov     rax, cs:__security_cookie
0x18009a06f  xor     rax, rsp
0x18009a072  mov     [rbp+660h+var_B0], rax
0x18009a079  movups  xmm0, xmmword ptr [r9]
0x18009a07d  lea     rax, [rcx+8]
0x18009a081  mov     [rsp+760h+var_728], r8
0x18009a086  mov     [rsp+760h+var_738], rax
0x18009a08b  mov     r14, rdx
0x18009a08e  mov     edx, 2
0x18009a093  mov     [rsp+760h+var_730], rcx
0x18009a098  lea     rax, [rsp+760h+var_710]
0x18009a09d  movaps  xmmword ptr [rsp+760h+var_710], xmm0
0x18009a0a2  mov     r9, r8
0x18009a0a5  mov     [rsp+760h+var_740], rax
0x18009a0aa  lea     rcx, [rbp+660h+var_6E0]
0x18009a0ae  lea     r8d, [rdx-1]
0x18009a0b2  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009a0b7  mov     rbx, [r14]
0x18009a0ba  lea     r9, [rsp+760h+var_720]; unsigned __int8 **
0x18009a0bf  mov     rdi, [rbp+660h+var_6D8]
0x18009a0c3  lea     r8, [rsp+760h+var_710]; unsigned __int8 **
0x18009a0c8  mov     rdx, rbx; unsigned __int8 *
0x18009a0cb  mov     qword ptr [rsp+760h+var_700], 0
0x18009a0d4  lea     rcx, [rbp+660h+var_6D0]; this
0x18009a0d8  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a0dd  mov     r15, [r14+8]
0x18009a0e1  lea     r9, [rsp+760h+var_720]; unsigned __int8 **
0x18009a0e6  add     rbx, rdi
0x18009a0e9  lea     r8, [rsp+760h+var_710]; unsigned __int8 **
0x18009a0ee  mov     rdx, r15; unsigned __int8 *
0x18009a0f1  mov     qword ptr [rsp+760h+var_700], rbx
0x18009a0f6  lea     rcx, [rbp+660h+var_6D0]; this
0x18009a0fa  movzx   esi, al
0x18009a0fd  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a102  test    al, al
0x18009a104  jz      short loc_18009A110
0x18009a106  test    sil, sil
0x18009a109  jz      short loc_18009A110
0x18009a10b  mov     sil, 1
0x18009a10e  jmp     short loc_18009A113
0x18009a110  xor     sil, sil
0x18009a113  mov     r14, [r14+10h]
0x18009a117  lea     rax, [r15+rdi]
0x18009a11b  mov     rdx, r14; unsigned __int8 *
0x18009a11e  mov     qword ptr [rsp+760h+var_700+8], rax
0x18009a123  lea     r9, [rsp+760h+var_720]; unsigned __int8 **
0x18009a128  lea     r8, [rsp+760h+var_710]; unsigned __int8 **
0x18009a12d  lea     rcx, [rbp+660h+var_6D0]; this
0x18009a131  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a136  test    al, al
0x18009a138  jz      loc_18009A4FB
0x18009a13e  test    sil, sil
0x18009a141  jz      loc_18009A4FB
0x18009a147  mov     ecx, [rbp+660h+var_6E0]
0x18009a14a  lea     rax, [r14+rdi]
0x18009a14e  xor     r15d, r15d
0x18009a151  mov     [rsp+760h+var_30], r12
0x18009a159  mov     [rsp+760h+var_38], r13
0x18009a161  mov     r13d, r15d
0x18009a164  mov     [rsp+760h+var_6F0], rax
0x18009a169  mov     r12d, r15d
0x18009a16c  mov     dword ptr [rsp+760h+var_720], 2
0x18009a174  test    ecx, ecx
0x18009a176  jle     loc_18009A4EB
0x18009a17c  mov     esi, [rbp+660h+var_6A8]
0x18009a17f  mov     edx, [rbp+660h+var_6B0]
0x18009a182  mov     edi, [rbp+660h+var_6DC]
0x18009a185  movaps  [rsp+760h+var_50], xmm6
0x18009a18d  movaps  [rsp+760h+var_60], xmm7
0x18009a195  movaps  [rsp+760h+var_70], xmm8
0x18009a19e  movaps  [rsp+760h+var_80], xmm9
0x18009a1a7  movaps  [rsp+760h+var_90], xmm10
0x18009a1b0  movsd   xmm10, [rsp+760h+var_6F0]
0x18009a1b7  movaps  [rsp+760h+var_A0], xmm11
0x18009a1c0  movups  xmm11, [rsp+760h+var_700]
0x18009a1c6  nop     word ptr [rax+rax+00000000h]
0x18009a1d0  inc     edx
0x18009a1d2  mov     [rbp+660h+var_6B0], edx
0x18009a1d5  cmp     edx, 1
0x18009a1d8  jnz     loc_18009A4A0
0x18009a1de  mov     r14, [rsp+760h+var_730]
0x18009a1e3  mov     r11d, r15d
0x18009a1e6  mov     eax, [rbp+660h+var_6AC]
0x18009a1e9  test    eax, eax
0x18009a1eb  movsd   [rsp+760h+var_6F0], xmm10
0x18009a1f2  cmovle  r11d, eax
0x18009a1f6  mov     ecx, [r14+2Ch]
0x18009a1fa  mov     edx, [r14+28h]
0x18009a1fe  mov     r10d, [r14+1Ch]
0x18009a202  cmp     r10d, ecx
0x18009a205  movsxd  r8, dword ptr [r14+34h]
0x18009a209  cmovl   r10d, ecx
0x18009a20d  sub     r10d, ecx
0x18009a210  cmp     esi, edx
0x18009a212  lea     r9d, [r8-1]
0x18009a216  cmovl   esi, edx
0x18009a219  sub     esi, edx
0x18009a21b  mov     eax, esi
0x18009a21d  mov     rsi, [rsp+760h+var_6F0]
0x18009a222  cdq
0x18009a223  idiv    dword ptr [r14+30h]
0x18009a227  mov     rax, [r14+38h]
0x18009a22b  movsxd  rcx, edx
0x18009a22e  imul    rcx, r8
0x18009a232  movups  [rsp+760h+var_700], xmm11
0x18009a238  movsxd  r8, [rbp+660h+var_B4]
0x18009a23f  cmp     r10d, r9d
0x18009a242  mov     r14, qword ptr [rsp+760h+var_700+8]
0x18009a247  cmovle  r9d, r10d
0x18009a24b  lea     r10, [rbx+r13]
0x18009a24f  neg     r11d
0x18009a252  add     rsi, r13
0x18009a255  lea     rax, [rax+rcx*2]
0x18009a259  add     r14, r13
0x18009a25c  movsxd  rcx, r9d
0x18009a25f  lea     r9, [rax+rcx*2]
0x18009a263  movsxd  rcx, r11d
0x18009a266  movzx   eax, byte ptr [rcx+rsi]
0x18009a26a  movzx   edx, byte ptr [rcx+r10]
0x18009a26f  add     edx, eax
0x18009a271  movzx   eax, byte ptr [rcx+r14]
0x18009a276  add     edx, eax
0x18009a278  imul    eax, edx, 55h ; 'U'
0x18009a27b  shr     eax, 6
0x18009a27e  mov     [r9], ax
0x18009a282  lea     eax, [r8+1]
0x18009a286  add     r11d, dword ptr [rsp+r8*4+760h+var_720]
0x18009a28b  add     r9, 2
0x18009a28f  movsxd  r8, eax
0x18009a292  cmp     r8, 1
0x18009a296  jge     short loc_18009A2EE
0x18009a298  cmp     r11d, edi
0x18009a29b  jge     short loc_18009A2EE
0x18009a29d  movsxd  rdx, r11d
0x18009a2a0  movzx   eax, byte ptr [rdx+r14]
0x18009a2a5  movzx   ecx, byte ptr [rdx+r10]
0x18009a2aa  add     ecx, eax
0x18009a2ac  movzx   eax, byte ptr [rdx+rsi]
0x18009a2b0  add     ecx, eax
0x18009a2b2  cmp     ecx, 2F4h
0x18009a2b8  jbe     short loc_18009A2CF
0x18009a2ba  movzx   eax, byte ptr [rdx+r14-1]
0x18009a2c0  movzx   ecx, byte ptr [rdx+r10-1]
0x18009a2c6  add     ecx, eax
0x18009a2c8  movzx   eax, byte ptr [rdx+rsi-1]
0x18009a2cd  add     ecx, eax
0x18009a2cf  imul    eax, ecx, 55h ; 'U'
0x18009a2d2  shr     eax, 6
0x18009a2d5  mov     [r9], ax
0x18009a2d9  add     r9, 2
0x18009a2dd  mov     eax, dword ptr [rsp+r8*4+760h+var_720]
0x18009a2e2  inc     r8
0x18009a2e5  add     r11d, eax
0x18009a2e8  cmp     r8, 1
0x18009a2ec  jl      short loc_18009A298
0x18009a2ee  mov     edi, [rbp+660h+var_6DC]
0x18009a2f1  dec     r11d
0x18009a2f4  movsxd  rdx, r11d
0x18009a2f7  lea     eax, [rdi-0Fh]
0x18009a2fa  movsxd  rcx, eax
0x18009a2fd  cmp     rdx, rcx
0x18009a300  jge     loc_18009A403
0x18009a306  movdqa  xmm8, cs:__xmm@00550055005500550055005500550055
0x18009a30f  lea     r15, [rdx+r14]
0x18009a313  movdqa  xmm9, cs:__xmm@03ec03ec03ec03ec03ec03ec03ec03ec
0x18009a31c  sub     rcx, rdx
0x18009a31f  dec     rcx
0x18009a322  mov     r8, r10
0x18009a325  shr     rcx, 4
0x18009a329  sub     r8, r14
0x18009a32c  mov     rdi, rsi
0x18009a32f  xorps   xmm7, xmm7
0x18009a332  sub     rdi, r14
0x18009a335  inc     rcx
0x18009a338  mov     eax, ecx
0x18009a33a  shl     eax, 4
0x18009a33d  add     r11d, eax
0x18009a340  movdqu  xmm3, xmmword ptr [r8+r15]
0x18009a346  movdqu  xmm6, xmmword ptr [r15]
0x18009a34b  movdqu  xmm5, xmmword ptr [rdi+r15]
0x18009a351  lea     r15, [r15+10h]
0x18009a355  movdqa  xmm0, xmm3
0x18009a359  movdqa  xmm2, xmm6
0x18009a35d  punpcklbw xmm2, xmm7
0x18009a361  movdqa  xmm1, xmm5
0x18009a365  punpcklbw xmm0, xmm7
0x18009a369  paddw   xmm2, xmm0
0x18009a36d  punpckhbw xmm3, xmm7
0x18009a371  punpcklbw xmm1, xmm7
0x18009a375  paddw   xmm2, xmm1
0x18009a379  punpckhbw xmm6, xmm7
0x18009a37d  paddw   xmm6, xmm3
0x18009a381  pmullw  xmm2, xmm8
0x18009a386  punpckhbw xmm5, xmm7
0x18009a38a  paddw   xmm6, xmm5
0x18009a38e  pmullw  xmm6, xmm8
0x18009a393  psrlw   xmm2, 6
0x18009a398  pshuflw xmm0, xmm2, 0D8h
0x18009a39d  pshufhw xmm4, xmm0, 0D8h
0x18009a3a2  movdqa  xmm2, xmm4
0x18009a3a6  psrlw   xmm6, 6
0x18009a3ab  pshuflw xmm0, xmm6, 0D8h
0x18009a3b0  pshufhw xmm1, xmm0, 0D8h
0x18009a3b5  punpcklqdq xmm2, xmm1
0x18009a3b9  punpckhqdq xmm4, xmm1
0x18009a3bd  movdqa  xmm3, xmm2
0x18009a3c1  punpckldq xmm3, xmm4
0x18009a3c5  movdqa  xmm1, xmm3
0x18009a3c9  punpckhdq xmm2, xmm4
0x18009a3cd  punpckhqdq xmm1, xmm2
0x18009a3d1  punpcklqdq xmm3, xmm2
0x18009a3d5  movdqa  xmm0, xmm1
0x18009a3d9  pcmpgtw xmm0, xmm9
0x18009a3de  pand    xmm3, xmm0
0x18009a3e2  pandn   xmm0, xmm1
0x18009a3e6  paddw   xmm3, xmm0
0x18009a3ea  movdqu  xmmword ptr [r9], xmm3
0x18009a3ef  add     r9, 10h
0x18009a3f3  sub     rcx, 1
0x18009a3f7  jnz     loc_18009A340
0x18009a3fd  mov     edi, [rbp+660h+var_6DC]
0x18009a400  xor     r15d, r15d
0x18009a403  inc     r11d
0x18009a406  cmp     r11d, edi
0x18009a409  jge     short loc_18009A475
0x18009a40b  sub     edi, r11d
0x18009a40e  movsxd  rdx, r11d
0x18009a411  dec     rdx
0x18009a414  sub     rsi, r14
0x18009a417  add     rdx, r14
0x18009a41a  sub     r10, r14
0x18009a41d  lea     r8d, [rdi-1]
0x18009a421  shr     r8d, 1
0x18009a424  inc     r8d
0x18009a427  nop     word ptr [rax+rax+00000000h]
0x18009a430  movzx   ecx, byte ptr [rsi+rdx+1]
0x18009a435  movzx   eax, byte ptr [r10+rdx+1]
0x18009a43b  add     eax, ecx
0x18009a43d  movzx   ecx, byte ptr [rdx+1]
0x18009a441  add     eax, ecx
0x18009a443  cmp     eax, 2F4h
0x18009a448  jbe     short loc_18009A45A
0x18009a44a  movzx   ecx, byte ptr [r10+rdx]
0x18009a44f  movzx   eax, byte ptr [rsi+rdx]
0x18009a453  add     eax, ecx
0x18009a455  movzx   ecx, byte ptr [rdx]
0x18009a458  add     eax, ecx
0x18009a45a  imul    ecx, eax, 55h ; 'U'
0x18009a45d  add     rdx, 2
0x18009a461  shr     ecx, 6
0x18009a464  mov     [r9], cx
0x18009a468  add     r9, 2
0x18009a46c  sub     r8, 1
0x18009a470  jnz     short loc_18009A430
0x18009a472  mov     edi, [rbp+660h+var_6DC]
0x18009a475  movsxd  rcx, [rbp+660h+var_CC]
0x18009a47c  mov     esi, [rbp+660h+var_6A8]
0x18009a47f  mov     edx, [rbp+660h+var_6B0]
0x18009a482  sub     edx, [rbp+rcx*4+660h+var_6A4]
0x18009a486  inc     ecx
0x18009a488  cmp     ecx, [rbp+660h+var_C4]
0x18009a48e  cmovge  ecx, r15d
0x18009a492  inc     esi
0x18009a494  mov     [rbp+660h+var_CC], ecx
0x18009a49a  mov     ecx, [rbp+660h+var_6E0]
0x18009a49d  mov     [rbp+660h+var_6A8], esi
0x18009a4a0  mov     rax, [rsp+760h+var_728]
0x18009a4a5  inc     r12d
0x18009a4a8  movsxd  rax, dword ptr [rax]
0x18009a4ab  add     r13, rax
0x18009a4ae  cmp     r12d, ecx
0x18009a4b1  jl      loc_18009A1D0
0x18009a4b7  movaps  xmm11, [rsp+760h+var_A0]
0x18009a4c0  movaps  xmm10, [rsp+760h+var_90]
0x18009a4c9  movaps  xmm9, [rsp+760h+var_80]
0x18009a4d2  movaps  xmm8, [rsp+760h+var_70]
0x18009a4db  movaps  xmm7, [rsp+760h+var_60]
0x18009a4e3  movaps  xmm6, [rsp+760h+var_50]
0x18009a4eb  mov     r12, [rsp+760h+var_30]
0x18009a4f3  mov     r13, [rsp+760h+var_38]
0x18009a4fb  mov     rcx, [rbp+660h+var_B0]
0x18009a502  xor     rcx, rsp; StackCookie
0x18009a505  call    __security_check_cookie
0x18009a50a  add     rsp, 738h
0x18009a511  pop     r15
0x18009a513  pop     r14
0x18009a515  pop     rdi
0x18009a516  pop     rsi
0x18009a517  pop     rbx
0x18009a518  pop     rbp
0x18009a519  retn
```
