# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009a520`
- end: `0x18009a969`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$00$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1097`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d5a0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x18009a520`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r12
  unsigned __int8 *v6; // rbx
  __int64 v7; // rsi
  bool v8; // al
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // rbx
  bool v11; // di
  bool v12; // di
  unsigned __int8 *v13; // r14
  bool result; // al
  unsigned __int8 *v15; // r15
  int v16; // r13d
  int v17; // esi
  int v18; // r14d
  int v19; // edi
  unsigned __int8 *v20; // xmm9_8
  __int128 v21; // xmm10
  int v22; // ecx
  int v23; // r11d
  int v24; // r10d
  __int64 v25; // r8
  int v26; // eax
  int v27; // r9d
  int v28; // r10d
  int v29; // eax
  __int64 v30; // rcx
  unsigned __int8 *v31; // r10
  __int64 v32; // rax
  int v33; // r11d
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned __int8 *v37; // r12
  unsigned __int8 *v38; // r15
  __m128i *v39; // rax
  int v40; // ecx
  __m128i si128; // xmm8
  const __m128i *v42; // rsi
  unsigned __int64 v43; // rdx
  __m128i v44; // xmm4
  __m128i v45; // xmm6
  __m128i v46; // xmm5
  __m128i v47; // xmm3
  __m128i v48; // xmm1
  __m128i v49; // xmm2
  __m128i v50; // xmm3
  unsigned __int8 *v51; // r8
  signed __int64 v52; // r15
  signed __int64 v53; // r10
  __int64 v54; // r9
  int v55; // ecx
  int v56; // edx
  __int64 v57; // rax
  unsigned __int8 *v60[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v61[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v62; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v63; // [rsp+70h] [rbp-90h]
  int v64; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+84h] [rbp-7Ch]
  __int64 v66; // [rsp+88h] [rbp-78h]
  _BYTE v67[32]; // [rsp+90h] [rbp-70h] BYREF
  int v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B4h] [rbp-4Ch]
  int v70; // [rsp+B8h] [rbp-48h]
  _DWORD v71[374]; // [rsp+BCh] [rbp-44h]
  int v72; // [rsp+694h] [rbp+594h]
  int v73; // [rsp+69Ch] [rbp+59Ch]
  int v74; // [rsp+6ACh] [rbp+5ACh]

  v5 = a1;
  *(_OWORD *)v61 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v64, 2, 1, (_DWORD)a3, (__int64)v61, a1 + 8);
  v6 = *a2;
  v7 = v66;
  v8 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v67,
         *a2,
         v61,
         v60);
  v9 = a2[1];
  v10 = &v6[v7];
  *(_QWORD *)&v62 = v10;
  v11 = v8;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v67,
          v9,
          v61,
          v60)
     && v11;
  v13 = a2[2];
  *((_QWORD *)&v62 + 1) = &v9[v7];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v67,
             v13,
             v61,
             v60);
  if ( result && v12 )
  {
    v63 = &v13[v7];
    result = 0;
    v15 = 0;
    v61[0] = 0;
    v16 = 0;
    LODWORD(v60[0]) = 2;
    if ( v64 > 0 )
    {
      v17 = v72;
      v18 = v68;
      v19 = v65;
      v20 = v63;
      v21 = v62;
      do
      {
        v68 = ++v18;
        if ( v18 == 1 )
        {
          v22 = *(_DWORD *)(v5 + 40);
          v23 = 0;
          v24 = *(_DWORD *)(v5 + 28);
          v25 = *(int *)(v5 + 52);
          if ( v69 <= 0 )
            v23 = v69;
          v63 = v20;
          v26 = *(_DWORD *)(v5 + 44);
          v62 = v21;
          if ( v24 < v26 )
            v24 = v26;
          v27 = v25 - 1;
          v28 = v24 - v26;
          v29 = v70;
          if ( v70 < v22 )
            v29 = v22;
          v30 = v25 * ((v29 - v22) % *(_DWORD *)(v5 + 48));
          if ( v28 <= v27 )
            v27 = v28;
          v31 = &v15[(_QWORD)v10];
          v32 = v27;
          v33 = -v23;
          v34 = v74;
          v35 = v32 + v30;
          v36 = *(_QWORD *)(v5 + 56);
          v37 = &v15[*((_QWORD *)&v62 + 1)];
          v38 = &v15[(_QWORD)v63];
          v39 = (__m128i *)(v36 + 2 * v35);
          if ( v74 < 1LL )
          {
            do
            {
              if ( v33 >= v19 )
                break;
              v39->m128i_i16[0] = (85 * (v38[v33] + v37[v33] + (unsigned int)v31[v33])) >> 6;
              v39 = (__m128i *)((char *)v39 + 2);
              v40 = *((_DWORD *)v60 + v34++);
              v33 += v40;
            }
            while ( v34 < 1 );
            v17 = v72;
            v18 = v68;
            v19 = v65;
          }
          if ( v33 < (__int64)(v19 - 15) )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v42 = (const __m128i *)&v37[v33];
            v43 = ((unsigned __int64)(v19 - 15 - (__int64)v33 - 1) >> 4) + 1;
            v33 += 16 * v43;
            do
            {
              v44 = _mm_loadu_si128((const __m128i *)((char *)v42 + v31 - v37));
              v45 = _mm_loadu_si128(v42);
              v46 = _mm_loadu_si128((const __m128i *)((char *)v42++ + v38 - v37));
              v47 = _mm_shufflehi_epi16(
                      _mm_shufflelo_epi16(
                        _mm_srli_epi16(
                          _mm_mullo_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(_mm_unpacklo_epi8(v45, (__m128i)0LL), _mm_unpacklo_epi8(v44, (__m128i)0LL)),
                              _mm_unpacklo_epi8(v46, (__m128i)0LL)),
                            si128),
                          6u),
                        216),
                      216);
              v48 = _mm_shufflehi_epi16(
                      _mm_shufflelo_epi16(
                        _mm_srli_epi16(
                          _mm_mullo_epi16(
                            _mm_add_epi16(
                              _mm_add_epi16(_mm_unpackhi_epi8(v45, (__m128i)0LL), _mm_unpackhi_epi8(v44, (__m128i)0LL)),
                              _mm_unpackhi_epi8(v46, (__m128i)0LL)),
                            si128),
                          6u),
                        216),
                      216);
              v49 = _mm_unpacklo_epi64(v47, v48);
              v50 = _mm_unpackhi_epi64(v47, v48);
              *v39++ = _mm_unpacklo_epi64(_mm_unpacklo_epi32(v49, v50), _mm_unpackhi_epi32(v49, v50));
              --v43;
            }
            while ( v43 );
            v17 = v72;
            v18 = v68;
            v19 = v65;
          }
          if ( v33 < v19 )
          {
            v51 = &v37[v33];
            v52 = v38 - v37;
            v53 = v31 - v37;
            v54 = ((unsigned int)(v19 - v33 - 1) >> 1) + 1;
            do
            {
              v55 = v51[v52];
              v39 = (__m128i *)((char *)v39 + 2);
              v56 = v51[v53];
              v51 += 2;
              v39[-1].m128i_i16[7] = (85 * ((unsigned int)*(v51 - 2) + v55 + v56)) >> 6;
              --v54;
            }
            while ( v54 );
            v17 = v72;
            v18 = v68;
            v19 = v65;
          }
          v15 = v61[0];
          v5 = a1;
          v57 = v17++;
          v18 -= v71[v57];
          if ( v17 >= v73 )
            v17 = 0;
          ++v70;
          v72 = v17;
        }
        ++v16;
        v15 += *a3;
        result = 0;
        v61[0] = v15;
      }
      while ( v16 < v64 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009a520  push    rbp
0x18009a522  push    rbx
0x18009a523  push    rsi
0x18009a524  push    rdi
0x18009a525  push    r12
0x18009a527  push    r14
0x18009a529  push    r15
0x18009a52b  lea     rbp, [rsp-620h]
0x18009a533  sub     rsp, 720h
0x18009a53a  mov     rax, cs:__security_cookie
0x18009a541  xor     rax, rsp
0x18009a544  mov     [rbp+650h+var_A0], rax
0x18009a54b  movups  xmm0, xmmword ptr [r9]
0x18009a54f  lea     rax, [rcx+8]
0x18009a553  mov     [rsp+750h+var_718], r8
0x18009a558  mov     [rsp+750h+var_728], rax
0x18009a55d  mov     r14, rdx
0x18009a560  mov     edx, 2
0x18009a565  mov     [rsp+750h+var_720], rcx
0x18009a56a  mov     r12, rcx
0x18009a56d  movaps  xmmword ptr [rsp+750h+var_700], xmm0
0x18009a572  lea     rax, [rsp+750h+var_700]
0x18009a577  mov     r9, r8
0x18009a57a  lea     rcx, [rbp+650h+var_6D0]
0x18009a57e  mov     [rsp+750h+var_730], rax
0x18009a583  lea     r8d, [rdx-1]
0x18009a587  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009a58c  mov     rbx, [r14]
0x18009a58f  lea     r9, [rsp+750h+var_710]; unsigned __int8 **
0x18009a594  mov     rsi, [rbp+650h+var_6C8]
0x18009a598  lea     r8, [rsp+750h+var_700]; unsigned __int8 **
0x18009a59d  mov     rdx, rbx; unsigned __int8 *
0x18009a5a0  lea     rcx, [rbp+650h+var_6C0]; this
0x18009a5a4  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a5a9  mov     r15, [r14+8]
0x18009a5ad  lea     r9, [rsp+750h+var_710]; unsigned __int8 **
0x18009a5b2  add     rbx, rsi
0x18009a5b5  lea     r8, [rsp+750h+var_700]; unsigned __int8 **
0x18009a5ba  mov     rdx, r15; unsigned __int8 *
0x18009a5bd  mov     qword ptr [rsp+750h+var_6F0], rbx
0x18009a5c2  lea     rcx, [rbp+650h+var_6C0]; this
0x18009a5c6  movzx   edi, al
0x18009a5c9  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a5ce  test    al, al
0x18009a5d0  jz      short loc_18009A5DC
0x18009a5d2  test    dil, dil
0x18009a5d5  jz      short loc_18009A5DC
0x18009a5d7  mov     dil, 1
0x18009a5da  jmp     short loc_18009A5DF
0x18009a5dc  xor     dil, dil
0x18009a5df  mov     r14, [r14+10h]
0x18009a5e3  lea     rax, [r15+rsi]
0x18009a5e7  mov     rdx, r14; unsigned __int8 *
0x18009a5ea  mov     qword ptr [rsp+750h+var_6F0+8], rax
0x18009a5ef  lea     r9, [rsp+750h+var_710]; unsigned __int8 **
0x18009a5f4  lea     r8, [rsp+750h+var_700]; unsigned __int8 **
0x18009a5f9  lea     rcx, [rbp+650h+var_6C0]; this
0x18009a5fd  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009a602  test    al, al
0x18009a604  jz      loc_18009A948
0x18009a60a  test    dil, dil
0x18009a60d  jz      loc_18009A948
0x18009a613  lea     rax, [r14+rsi]
0x18009a617  mov     [rsp+750h+var_38], r13
0x18009a61f  mov     [rsp+750h+var_6E0], rax
0x18009a624  xor     eax, eax
0x18009a626  mov     r15d, eax
0x18009a629  mov     [rsp+750h+var_700], rax
0x18009a62e  mov     r13d, eax
0x18009a631  mov     dword ptr [rsp+750h+var_710], 2
0x18009a639  cmp     [rbp+650h+var_6D0], eax
0x18009a63c  jle     loc_18009A940
0x18009a642  mov     esi, [rbp+650h+var_BC]
0x18009a648  mov     r14d, [rbp+650h+var_6A0]
0x18009a64c  mov     edi, [rbp+650h+var_6CC]
0x18009a64f  movaps  [rsp+750h+var_50], xmm6
0x18009a657  movaps  [rsp+750h+var_60], xmm7
0x18009a65f  movaps  [rsp+750h+var_70], xmm8
0x18009a668  movaps  [rsp+750h+var_80], xmm9
0x18009a671  movsd   xmm9, [rsp+750h+var_6E0]
0x18009a678  movaps  [rsp+750h+var_90], xmm10
0x18009a681  movups  xmm10, [rsp+750h+var_6F0]
0x18009a687  nop     word ptr [rax+rax+00000000h]
0x18009a690  inc     r14d
0x18009a693  mov     [rbp+650h+var_6A0], r14d
0x18009a697  cmp     r14d, 1
0x18009a69b  jnz     loc_18009A8F3
0x18009a6a1  mov     ecx, [r12+28h]
0x18009a6a6  mov     r11d, eax
0x18009a6a9  mov     r10d, [r12+1Ch]
0x18009a6ae  mov     eax, [rbp+650h+var_69C]
0x18009a6b1  test    eax, eax
0x18009a6b3  movsxd  r8, dword ptr [r12+34h]
0x18009a6b8  cmovle  r11d, eax
0x18009a6bc  movsd   [rsp+750h+var_6E0], xmm9
0x18009a6c3  mov     eax, [r12+2Ch]
0x18009a6c8  cmp     r10d, eax
0x18009a6cb  movups  [rsp+750h+var_6F0], xmm10
0x18009a6d1  cmovl   r10d, eax
0x18009a6d5  lea     r9d, [r8-1]
0x18009a6d9  sub     r10d, eax
0x18009a6dc  mov     eax, [rbp+650h+var_698]
0x18009a6df  cmp     eax, ecx
0x18009a6e1  cmovl   eax, ecx
0x18009a6e4  sub     eax, ecx
0x18009a6e6  cdq
0x18009a6e7  idiv    dword ptr [r12+30h]
0x18009a6ec  movsxd  rcx, edx
0x18009a6ef  imul    rcx, r8
0x18009a6f3  cmp     r10d, r9d
0x18009a6f6  cmovle  r9d, r10d
0x18009a6fa  lea     r10, [rbx+r15]
0x18009a6fe  movsxd  rax, r9d
0x18009a701  neg     r11d
0x18009a704  movsxd  r9, [rbp+650h+var_A4]
0x18009a70b  add     rcx, rax
0x18009a70e  mov     rax, [r12+38h]
0x18009a713  mov     r12, qword ptr [rsp+750h+var_6F0+8]
0x18009a718  add     r12, r15
0x18009a71b  add     r15, [rsp+750h+var_6E0]
0x18009a720  lea     rax, [rax+rcx*2]
0x18009a724  cmp     r9, 1
0x18009a728  jge     short loc_18009A779
0x18009a72a  nop     word ptr [rax+rax+00h]
0x18009a730  cmp     r11d, edi
0x18009a733  jge     short loc_18009A76C
0x18009a735  movsxd  rdx, r11d
0x18009a738  movzx   ecx, byte ptr [rdx+r12]
0x18009a73d  movzx   r8d, byte ptr [r10+rdx]
0x18009a742  add     r8d, ecx
0x18009a745  movzx   ecx, byte ptr [rdx+r15]
0x18009a74a  add     r8d, ecx
0x18009a74d  imul    ecx, r8d, 55h ; 'U'
0x18009a751  shr     ecx, 6
0x18009a754  mov     [rax], cx
0x18009a757  add     rax, 2
0x18009a75b  mov     ecx, dword ptr [rsp+r9*4+750h+var_710]
0x18009a760  inc     r9
0x18009a763  add     r11d, ecx
0x18009a766  cmp     r9, 1
0x18009a76a  jl      short loc_18009A730
0x18009a76c  mov     esi, [rbp+650h+var_BC]
0x18009a772  mov     r14d, [rbp+650h+var_6A0]
0x18009a776  mov     edi, [rbp+650h+var_6CC]
0x18009a779  lea     ecx, [rdi-0Fh]
0x18009a77c  movsxd  r8, r11d
0x18009a77f  movsxd  rdx, ecx
0x18009a782  cmp     r8, rdx
0x18009a785  jge     loc_18009A86A
0x18009a78b  movdqa  xmm8, cs:__xmm@00550055005500550055005500550055
0x18009a794  lea     rsi, [r12+r8]
0x18009a798  sub     rdx, r8
0x18009a79b  mov     r9, r10
0x18009a79e  dec     rdx
0x18009a7a1  sub     r9, r12
0x18009a7a4  shr     rdx, 4
0x18009a7a8  mov     rdi, r15
0x18009a7ab  sub     rdi, r12
0x18009a7ae  xorps   xmm7, xmm7
0x18009a7b1  inc     rdx
0x18009a7b4  mov     ecx, edx
0x18009a7b6  shl     ecx, 4
0x18009a7b9  add     r11d, ecx
0x18009a7bc  nop     dword ptr [rax+00h]
0x18009a7c0  movdqu  xmm4, xmmword ptr [r9+rsi]
0x18009a7c6  movdqu  xmm6, xmmword ptr [rsi]
0x18009a7ca  movdqu  xmm5, xmmword ptr [rdi+rsi]
0x18009a7cf  lea     rsi, [rsi+10h]
0x18009a7d3  movdqa  xmm2, xmm6
0x18009a7d7  movdqa  xmm0, xmm4
0x18009a7db  punpcklbw xmm2, xmm7
0x18009a7df  movdqa  xmm1, xmm5
0x18009a7e3  punpcklbw xmm0, xmm7
0x18009a7e7  paddw   xmm2, xmm0
0x18009a7eb  punpckhbw xmm6, xmm7
0x18009a7ef  punpcklbw xmm1, xmm7
0x18009a7f3  paddw   xmm2, xmm1
0x18009a7f7  punpckhbw xmm4, xmm7
0x18009a7fb  pmullw  xmm2, xmm8
0x18009a800  paddw   xmm6, xmm4
0x18009a804  punpckhbw xmm5, xmm7
0x18009a808  paddw   xmm6, xmm5
0x18009a80c  pmullw  xmm6, xmm8
0x18009a811  psrlw   xmm2, 6
0x18009a816  pshuflw xmm0, xmm2, 0D8h
0x18009a81b  pshufhw xmm3, xmm0, 0D8h
0x18009a820  movdqa  xmm2, xmm3
0x18009a824  psrlw   xmm6, 6
0x18009a829  pshuflw xmm0, xmm6, 0D8h
0x18009a82e  pshufhw xmm1, xmm0, 0D8h
0x18009a833  punpcklqdq xmm2, xmm1
0x18009a837  movdqa  xmm0, xmm2
0x18009a83b  punpckhqdq xmm3, xmm1
0x18009a83f  punpckldq xmm0, xmm3
0x18009a843  punpckhdq xmm2, xmm3
0x18009a847  punpcklqdq xmm0, xmm2
0x18009a84b  movdqu  xmmword ptr [rax], xmm0
0x18009a84f  add     rax, 10h
0x18009a853  sub     rdx, 1
0x18009a857  jnz     loc_18009A7C0
0x18009a85d  mov     esi, [rbp+650h+var_BC]
0x18009a863  mov     r14d, [rbp+650h+var_6A0]
0x18009a867  mov     edi, [rbp+650h+var_6CC]
0x18009a86a  cmp     r11d, edi
0x18009a86d  jge     short loc_18009A8C8
0x18009a86f  sub     edi, r11d
0x18009a872  movsxd  r8, r11d
0x18009a875  add     r8, r12
0x18009a878  sub     r15, r12
0x18009a87b  sub     r10, r12
0x18009a87e  lea     r9d, [rdi-1]
0x18009a882  shr     r9d, 1
0x18009a885  inc     r9d
0x18009a888  nop     dword ptr [rax+rax+00000000h]
0x18009a890  movzx   ecx, byte ptr [r8+r15]
0x18009a895  lea     rax, [rax+2]
0x18009a899  movzx   edx, byte ptr [r8+r10]
0x18009a89e  lea     r8, [r8+2]
0x18009a8a2  add     edx, ecx
0x18009a8a4  movzx   ecx, byte ptr [r8-2]
0x18009a8a9  add     edx, ecx
0x18009a8ab  imul    ecx, edx, 55h ; 'U'
0x18009a8ae  shr     ecx, 6
0x18009a8b1  mov     [rax-2], cx
0x18009a8b5  sub     r9, 1
0x18009a8b9  jnz     short loc_18009A890
0x18009a8bb  mov     esi, [rbp+650h+var_BC]
0x18009a8c1  mov     r14d, [rbp+650h+var_6A0]
0x18009a8c5  mov     edi, [rbp+650h+var_6CC]
0x18009a8c8  mov     r15, [rsp+750h+var_700]
0x18009a8cd  mov     r12, [rsp+750h+var_720]
0x18009a8d2  movsxd  rax, esi
0x18009a8d5  inc     esi
0x18009a8d7  sub     r14d, [rbp+rax*4+650h+var_694]
0x18009a8dc  mov     eax, 0
0x18009a8e1  cmp     esi, [rbp+650h+var_B4]
0x18009a8e7  cmovge  esi, eax
0x18009a8ea  inc     [rbp+650h+var_698]
0x18009a8ed  mov     [rbp+650h+var_BC], esi
0x18009a8f3  mov     rax, [rsp+750h+var_718]
0x18009a8f8  inc     r13d
0x18009a8fb  movsxd  rax, dword ptr [rax]
0x18009a8fe  add     r15, rax
0x18009a901  mov     eax, 0
0x18009a906  mov     [rsp+750h+var_700], r15
0x18009a90b  cmp     r13d, [rbp+650h+var_6D0]
0x18009a90f  jl      loc_18009A690
0x18009a915  movaps  xmm10, [rsp+750h+var_90]
0x18009a91e  movaps  xmm9, [rsp+750h+var_80]
0x18009a927  movaps  xmm8, [rsp+750h+var_70]
0x18009a930  movaps  xmm7, [rsp+750h+var_60]
0x18009a938  movaps  xmm6, [rsp+750h+var_50]
0x18009a940  mov     r13, [rsp+750h+var_38]
0x18009a948  mov     rcx, [rbp+650h+var_A0]
0x18009a94f  xor     rcx, rsp; StackCookie
0x18009a952  call    __security_check_cookie
0x18009a957  add     rsp, 720h
0x18009a95e  pop     r15
0x18009a960  pop     r14
0x18009a962  pop     r12
0x18009a964  pop     rdi
0x18009a965  pop     rsi
0x18009a966  pop     rbx
0x18009a967  pop     rbp
0x18009a968  retn
```
