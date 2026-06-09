# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009b6e0`
- end: `0x18009bbb6`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$03$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d5d0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x18009b6e0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r15
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  unsigned __int8 *v9; // rbx
  int v10; // eax
  __int64 v11; // r13
  int v12; // esi
  int v13; // edi
  int v14; // r14d
  __int128 v15; // xmm11
  __int64 v16; // xmm12_8
  int v17; // ecx
  int v18; // r11d
  int v19; // r10d
  __int64 v20; // r8
  int v21; // eax
  int v22; // r9d
  int v23; // r10d
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r12
  __int64 v27; // rax
  unsigned __int8 *v28; // r10
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // r11d
  __int64 v33; // r15
  __m128i *v34; // r8
  int v35; // eax
  __m128i si128; // xmm10
  __int64 v37; // rax
  __int64 v38; // r9
  const __m128i *v39; // rax
  __m128i *v40; // rcx
  __int64 v41; // rdx
  __m128i v42; // xmm1
  __m128i v43; // xmm0
  __m128i v44; // xmm1
  __m128i v45; // xmm6
  __m128i v46; // xmm0
  __m128i v47; // xmm8
  __m128i v48; // xmm4
  __m128i v49; // xmm6
  __m128i v50; // xmm0
  __m128i v51; // xmm5
  __m128i v52; // xmm4
  __m128i v53; // xmm0
  __m128i v54; // xmm3
  __m128i v55; // xmm7
  __m128i v56; // xmm3
  __m128i v57; // xmm8
  __int64 v58; // r15
  __int64 v59; // rdx
  unsigned __int8 *v60; // r10
  __int64 v61; // r9
  int v62; // eax
  int v63; // ecx
  __int64 v64; // rax
  __m128i v68; // [rsp+40h] [rbp-C0h] BYREF
  __m128i v69; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v70; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v71; // [rsp+70h] [rbp-90h] BYREF
  __m128i v72; // [rsp+80h] [rbp-80h]
  __m128i v73; // [rsp+90h] [rbp-70h]
  __m128i v74; // [rsp+A0h] [rbp-60h]
  __m128i v75; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v76; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 *v77[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-20h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  int v81; // [rsp+100h] [rbp+0h] BYREF
  int v82; // [rsp+104h] [rbp+4h]
  __int64 v83; // [rsp+108h] [rbp+8h]
  char v84[32]; // [rsp+110h] [rbp+10h] BYREF
  int v85; // [rsp+130h] [rbp+30h]
  int v86; // [rsp+134h] [rbp+34h]
  int v87; // [rsp+138h] [rbp+38h]
  _DWORD v88[374]; // [rsp+13Ch] [rbp+3Ch]
  int v89; // [rsp+714h] [rbp+614h]
  int v90; // [rsp+71Ch] [rbp+61Ch]
  int v91; // [rsp+72Ch] [rbp+62Ch]

  v5 = a1;
  *(_OWORD *)v77 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v81, 2, 1, a3, v77, (_DWORD *)(a1 + 8));
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v9 = &v8[v83];
  *(_QWORD *)&v78 = &v8[v83];
  *((_QWORD *)&v78 + 1) = &v8[v83 + 1];
  v79 = (__int64)&v8[v83 + 2];
  v80 = (__int64)&v8[v83 + 3];
  LOBYTE(v10) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v84,
                  v8,
                  &v76,
                  v77);
  if ( (_BYTE)v10 )
  {
    v11 = 0;
    LODWORD(v77[0]) = 2;
    LODWORD(v76) = 0;
    if ( v81 > 0 )
    {
      v12 = v89;
      v13 = v82;
      v14 = v85;
      v15 = v78;
      v16 = v79;
      do
      {
        v85 = ++v14;
        if ( v14 == 1 )
        {
          v17 = *(_DWORD *)(v5 + 40);
          v18 = 0;
          v19 = *(_DWORD *)(v5 + 28);
          v20 = *(int *)(v5 + 52);
          if ( v86 <= 0 )
            v18 = v86;
          v21 = *(_DWORD *)(v5 + 44);
          v78 = v15;
          v22 = v20 - 1;
          if ( v19 < v21 )
            v19 = v21;
          v23 = v19 - v21;
          v24 = v87;
          if ( v87 < v17 )
            v24 = v17;
          v25 = v20 * ((v24 - v17) % *(_DWORD *)(v5 + 48));
          if ( v23 <= v22 )
            v22 = v23;
          v26 = v11 + *((_QWORD *)&v15 + 1);
          v27 = v22;
          v28 = &v9[v11];
          v29 = v91;
          v30 = v27 + v25;
          v31 = *(_QWORD *)(v5 + 56);
          v32 = -v18;
          v33 = v11 + v16;
          v34 = (__m128i *)(v31 + 2 * v30);
          if ( v91 < 1LL )
          {
            do
            {
              if ( v32 >= v13 )
                break;
              v34->m128i_i16[0] = (85
                                 * (*(unsigned __int8 *)(v33 + 4 * v32)
                                  + *(unsigned __int8 *)(v26 + 4 * v32)
                                  + (unsigned int)v28[4 * v32])) >> 6;
              v34 = (__m128i *)((char *)v34 + 2);
              v35 = *((_DWORD *)v77 + v29++);
              v32 += v35;
            }
            while ( v29 < 1 );
            v12 = v89;
            v14 = v85;
            v13 = v82;
          }
          if ( v32 < v13 - 31 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v37 = v32 + 8LL;
            v38 = ((unsigned int)(v13 - 31 - v32 - 1) >> 5) + 1;
            v32 += 32 * v38;
            v39 = (const __m128i *)&v28[4 * v37];
            do
            {
              v40 = &v70;
              v41 = 2;
              do
              {
                v40 += 4;
                v42 = _mm_loadu_si128(v39 - 1);
                v40[-6] = _mm_loadu_si128(v39 - 2);
                v43 = _mm_loadu_si128(v39);
                v40[-5] = v42;
                v44 = _mm_loadu_si128(v39 + 1);
                v39 += 4;
                v40[-4] = v43;
                v40[-3] = v44;
                --v41;
              }
              while ( v41 );
              v45 = _mm_load_si128(&v68);
              v46 = _mm_load_si128(&v70);
              v47 = _mm_unpacklo_epi8(_mm_unpacklo_epi8(v45, v72), _mm_unpacklo_epi8(v46, v74));
              v48 = _mm_load_si128(&v69);
              v49 = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v45, v72), _mm_unpackhi_epi8(v46, v74));
              v50 = _mm_load_si128(&v71);
              v51 = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v48, v73), _mm_unpackhi_epi8(v50, v75));
              v52 = _mm_unpacklo_epi8(_mm_unpacklo_epi8(v48, v73), _mm_unpacklo_epi8(v50, v75));
              v53 = _mm_unpacklo_epi8(v49, v51);
              v54 = _mm_unpacklo_epi8(v47, v52);
              v55 = _mm_unpacklo_epi8(v54, v53);
              v56 = _mm_unpackhi_epi8(v54, v53);
              v57 = _mm_unpacklo_epi8(_mm_unpackhi_epi8(v47, v52), _mm_unpackhi_epi8(v49, v51));
              *v34 = _mm_srli_epi16(
                       _mm_mullo_epi16(
                         _mm_add_epi16(
                           _mm_add_epi16(_mm_unpacklo_epi8(v55, (__m128i)0LL), _mm_unpacklo_epi8(v56, (__m128i)0LL)),
                           _mm_unpacklo_epi8(v57, (__m128i)0LL)),
                         si128),
                       6u);
              v34[1] = _mm_srli_epi16(
                         _mm_mullo_epi16(
                           _mm_add_epi16(
                             _mm_add_epi16(_mm_unpackhi_epi8(v55, (__m128i)0LL), _mm_unpackhi_epi8(v56, (__m128i)0LL)),
                             _mm_unpackhi_epi8(v57, (__m128i)0LL)),
                           si128),
                         6u);
              v34 += 2;
              --v38;
            }
            while ( v38 );
            v12 = v89;
            v14 = v85;
            v13 = v82;
          }
          if ( v32 < v13 )
          {
            v58 = v33 - v26;
            v59 = v26 + 4 * v32;
            v60 = &v28[-v26];
            v61 = ((unsigned int)(v13 - v32 - 1) >> 1) + 1;
            do
            {
              v62 = *(unsigned __int8 *)(v58 + v59);
              v34 = (__m128i *)((char *)v34 + 2);
              v63 = v60[v59];
              v59 += 8;
              v34[-1].m128i_i16[7] = (85 * ((unsigned int)*(unsigned __int8 *)(v59 - 8) + v62 + v63)) >> 6;
              --v61;
            }
            while ( v61 );
            v12 = v89;
            v14 = v85;
            v13 = v82;
          }
          v5 = a1;
          v64 = v12++;
          v14 -= v88[v64];
          if ( v12 >= v90 )
            v12 = 0;
          ++v87;
          v89 = v12;
        }
        v11 += *a3;
        v10 = (_DWORD)v76 + 1;
        LODWORD(v76) = v10;
      }
      while ( v10 < v81 );
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18009b6e0  push    rbp
0x18009b6e2  push    rbx
0x18009b6e3  push    r12
0x18009b6e5  push    r15
0x18009b6e7  lea     rbp, [rsp-6D8h]
0x18009b6ef  sub     rsp, 7D8h
0x18009b6f6  mov     rax, cs:__security_cookie
0x18009b6fd  xor     rax, rsp
0x18009b700  mov     [rbp+6F0h+var_C0], rax
0x18009b707  movups  xmm0, xmmword ptr [r9]
0x18009b70b  lea     rax, [rcx+8]
0x18009b70f  mov     [rsp+7F0h+var_7B8], r8
0x18009b714  mov     [rsp+7F0h+var_7C8], rax
0x18009b719  mov     rbx, rdx
0x18009b71c  mov     edx, 2
0x18009b721  mov     [rsp+7F0h+var_7C0], rcx
0x18009b726  mov     r15, rcx
0x18009b729  movaps  xmmword ptr [rbp+6F0h+var_720], xmm0
0x18009b72d  lea     rax, [rbp+6F0h+var_720]
0x18009b731  mov     r9, r8
0x18009b734  lea     rcx, [rbp+6F0h+var_6F0]
0x18009b738  mov     [rsp+7F0h+var_7D0], rax
0x18009b73d  lea     r8d, [rdx-1]
0x18009b741  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009b746  mov     rcx, [rbx+8]
0x18009b74a  lea     r9, [rbp+6F0h+var_720]; unsigned __int8 **
0x18009b74e  mov     rax, [rbx+10h]
0x18009b752  lea     r8, [rbp+6F0h+var_730]; unsigned __int8 **
0x18009b756  mov     rdx, [rbx+18h]
0x18009b75a  xor     r12d, r12d
0x18009b75d  cmp     [rbx], rcx
0x18009b760  cmovbe  rcx, [rbx]
0x18009b764  mov     rbx, [rbp+6F0h+var_6E8]
0x18009b768  cmp     rcx, rax
0x18009b76b  cmovbe  rax, rcx
0x18009b76f  lea     rcx, [rbp+6F0h+var_6E0]; this
0x18009b773  cmp     rax, rdx
0x18009b776  cmovbe  rdx, rax; unsigned __int8 *
0x18009b77a  add     rbx, rdx
0x18009b77d  mov     qword ptr [rbp+6F0h+var_710], rbx
0x18009b781  lea     rax, [rbx+1]
0x18009b785  mov     qword ptr [rbp+6F0h+var_710+8], rax
0x18009b789  lea     rax, [rbx+2]
0x18009b78d  mov     qword ptr [rbp+6F0h+var_700], rax
0x18009b791  lea     rax, [rbx+3]
0x18009b795  mov     qword ptr [rbp+6F0h+var_700+8], rax
0x18009b799  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009b79e  test    al, al
0x18009b7a0  jz      loc_18009BB99
0x18009b7a6  mov     [rsp+7F0h+var_30], r13
0x18009b7ae  mov     r13d, r12d
0x18009b7b1  mov     dword ptr [rbp+6F0h+var_720], 2
0x18009b7b8  mov     dword ptr [rbp+6F0h+var_730], r12d
0x18009b7bc  cmp     [rbp+6F0h+var_6F0], r12d
0x18009b7c0  jle     loc_18009BB91
0x18009b7c6  mov     [rsp+7F0h+var_20], rsi
0x18009b7ce  mov     esi, [rbp+6F0h+var_DC]
0x18009b7d4  mov     [rsp+7F0h+var_28], rdi
0x18009b7dc  mov     edi, [rbp+6F0h+var_6EC]
0x18009b7df  mov     [rsp+7F0h+var_38], r14
0x18009b7e7  mov     r14d, [rbp+6F0h+var_6C0]
0x18009b7eb  movaps  [rsp+7F0h+var_50], xmm6
0x18009b7f3  movaps  [rsp+7F0h+var_60], xmm7
0x18009b7fb  movaps  [rsp+7F0h+var_70], xmm8
0x18009b804  movaps  [rsp+7F0h+var_80], xmm9
0x18009b80d  movaps  [rsp+7F0h+var_90], xmm10
0x18009b816  movaps  [rsp+7F0h+var_A0], xmm11
0x18009b81f  movups  xmm11, [rbp+6F0h+var_710]
0x18009b824  movaps  [rsp+7F0h+var_B0], xmm12
0x18009b82d  movups  xmm12, [rbp+6F0h+var_700]
0x18009b832  inc     r14d
0x18009b835  mov     [rbp+6F0h+var_6C0], r14d
0x18009b839  cmp     r14d, 1
0x18009b83d  jnz     loc_18009BB20
0x18009b843  mov     ecx, [r15+28h]
0x18009b847  mov     r11d, r12d
0x18009b84a  mov     r10d, [r15+1Ch]
0x18009b84e  mov     eax, [rbp+6F0h+var_6BC]
0x18009b851  test    eax, eax
0x18009b853  movsxd  r8, dword ptr [r15+34h]
0x18009b857  cmovle  r11d, eax
0x18009b85b  mov     eax, [r15+2Ch]
0x18009b85f  cmp     r10d, eax
0x18009b862  movups  [rbp+6F0h+var_710], xmm11
0x18009b867  mov     r12, qword ptr [rbp+6F0h+var_710+8]
0x18009b86b  lea     r9d, [r8-1]
0x18009b86f  cmovl   r10d, eax
0x18009b873  sub     r10d, eax
0x18009b876  mov     eax, [rbp+6F0h+var_6B8]
0x18009b879  cmp     eax, ecx
0x18009b87b  cmovl   eax, ecx
0x18009b87e  sub     eax, ecx
0x18009b880  cdq
0x18009b881  idiv    dword ptr [r15+30h]
0x18009b885  movsxd  rcx, edx
0x18009b888  imul    rcx, r8
0x18009b88c  cmp     r10d, r9d
0x18009b88f  cmovle  r9d, r10d
0x18009b893  add     r12, r13
0x18009b896  movsxd  rax, r9d
0x18009b899  lea     r10, [rbx+r13]
0x18009b89d  movsxd  r9, [rbp+6F0h+var_C4]
0x18009b8a4  add     rcx, rax
0x18009b8a7  mov     rax, [r15+38h]
0x18009b8ab  neg     r11d
0x18009b8ae  movq    r15, xmm12
0x18009b8b3  add     r15, r13
0x18009b8b6  lea     r8, [rax+rcx*2]
0x18009b8ba  cmp     r9, 1
0x18009b8be  jge     short loc_18009B90F
0x18009b8c0  cmp     r11d, edi
0x18009b8c3  jge     short loc_18009B902
0x18009b8c5  lea     eax, ds:0[r11*4]
0x18009b8cd  movsxd  rcx, eax
0x18009b8d0  movzx   eax, byte ptr [r12+rcx]
0x18009b8d5  movzx   edx, byte ptr [r10+rcx]
0x18009b8da  add     edx, eax
0x18009b8dc  movzx   eax, byte ptr [r15+rcx]
0x18009b8e1  add     edx, eax
0x18009b8e3  imul    eax, edx, 55h ; 'U'
0x18009b8e6  shr     eax, 6
0x18009b8e9  mov     [r8], ax
0x18009b8ed  add     r8, 2
0x18009b8f1  mov     eax, dword ptr [rbp+r9*4+6F0h+var_720]
0x18009b8f6  inc     r9
0x18009b8f9  add     r11d, eax
0x18009b8fc  cmp     r9, 1
0x18009b900  jl      short loc_18009B8C0
0x18009b902  mov     esi, [rbp+6F0h+var_DC]
0x18009b908  mov     r14d, [rbp+6F0h+var_6C0]
0x18009b90c  mov     edi, [rbp+6F0h+var_6EC]
0x18009b90f  lea     ecx, [rdi-1Fh]
0x18009b912  cmp     r11d, ecx
0x18009b915  jge     loc_18009BA99
0x18009b91b  movdqa  xmm10, cs:__xmm@00550055005500550055005500550055
0x18009b924  sub     ecx, r11d
0x18009b927  dec     ecx
0x18009b929  movsxd  rax, r11d
0x18009b92c  shr     ecx, 5
0x18009b92f  add     rax, 8
0x18009b933  inc     ecx
0x18009b935  xorps   xmm9, xmm9
0x18009b939  mov     r9d, ecx
0x18009b93c  shl     ecx, 5
0x18009b93f  add     r11d, ecx
0x18009b942  lea     rax, [r10+rax*4]
0x18009b946  nop     word ptr [rax+rax+00000000h]
0x18009b950  lea     rcx, [rsp+7F0h+var_790]
0x18009b955  mov     edx, 2
0x18009b95a  nop     word ptr [rax+rax+00h]
0x18009b960  movdqu  xmm0, xmmword ptr [rax-20h]
0x18009b965  lea     rcx, [rcx+40h]
0x18009b969  movdqu  xmm1, xmmword ptr [rax-10h]
0x18009b96e  movdqu  xmmword ptr [rcx-60h], xmm0
0x18009b973  movdqu  xmm0, xmmword ptr [rax]
0x18009b977  movdqu  xmmword ptr [rcx-50h], xmm1
0x18009b97c  movdqu  xmm1, xmmword ptr [rax+10h]
0x18009b981  add     rax, 40h ; '@'
0x18009b985  movdqu  xmmword ptr [rcx-40h], xmm0
0x18009b98a  movdqu  xmmword ptr [rcx-30h], xmm1
0x18009b98f  sub     rdx, 1
0x18009b993  jnz     short loc_18009B960
0x18009b995  movdqa  xmm6, [rsp+7F0h+var_7B0]
0x18009b99b  movdqa  xmm3, [rsp+7F0h+var_790]
0x18009b9a1  movdqa  xmm8, xmm6
0x18009b9a6  punpcklbw xmm8, [rbp+6F0h+var_770]
0x18009b9ac  movdqa  xmm0, xmm3
0x18009b9b0  punpckhbw xmm3, [rbp+6F0h+var_750]
0x18009b9b5  punpcklbw xmm0, [rbp+6F0h+var_750]
0x18009b9ba  punpckhbw xmm6, [rbp+6F0h+var_770]
0x18009b9bf  movdqa  xmm5, [rsp+7F0h+var_7A0]
0x18009b9c5  punpcklbw xmm8, xmm0
0x18009b9ca  movdqa  xmm4, xmm5
0x18009b9ce  punpckhbw xmm5, [rbp+6F0h+var_760]
0x18009b9d3  punpcklbw xmm4, [rbp+6F0h+var_760]
0x18009b9d8  punpcklbw xmm6, xmm3
0x18009b9dc  movdqa  xmm3, [rsp+7F0h+var_780]
0x18009b9e2  movdqa  xmm0, xmm3
0x18009b9e6  punpckhbw xmm3, [rbp+6F0h+var_740]
0x18009b9eb  punpcklbw xmm0, [rbp+6F0h+var_740]
0x18009b9f0  punpcklbw xmm5, xmm3
0x18009b9f4  movdqa  xmm3, xmm8
0x18009b9f9  punpcklbw xmm4, xmm0
0x18009b9fd  movdqa  xmm0, xmm6
0x18009ba01  punpcklbw xmm0, xmm5
0x18009ba05  punpcklbw xmm3, xmm4
0x18009ba09  movdqa  xmm7, xmm3
0x18009ba0d  punpckhbw xmm8, xmm4
0x18009ba12  punpcklbw xmm7, xmm0
0x18009ba16  movdqa  xmm2, xmm7
0x18009ba1a  punpckhbw xmm3, xmm0
0x18009ba1e  punpcklbw xmm2, xmm9
0x18009ba23  movdqa  xmm0, xmm3
0x18009ba27  punpckhbw xmm7, xmm9
0x18009ba2c  punpckhbw xmm6, xmm5
0x18009ba30  punpcklbw xmm8, xmm6
0x18009ba35  movdqa  xmm1, xmm8
0x18009ba3a  punpcklbw xmm0, xmm9
0x18009ba3f  paddw   xmm2, xmm0
0x18009ba43  punpckhbw xmm3, xmm9
0x18009ba48  paddw   xmm7, xmm3
0x18009ba4c  punpcklbw xmm1, xmm9
0x18009ba51  paddw   xmm2, xmm1
0x18009ba55  punpckhbw xmm8, xmm9
0x18009ba5a  paddw   xmm7, xmm8
0x18009ba5f  pmullw  xmm2, xmm10
0x18009ba64  pmullw  xmm7, xmm10
0x18009ba69  psrlw   xmm2, 6
0x18009ba6e  movdqu  xmmword ptr [r8], xmm2
0x18009ba73  psrlw   xmm7, 6
0x18009ba78  movdqu  xmmword ptr [r8+10h], xmm7
0x18009ba7e  add     r8, 20h ; ' '
0x18009ba82  sub     r9, 1
0x18009ba86  jnz     loc_18009B950
0x18009ba8c  mov     esi, [rbp+6F0h+var_DC]
0x18009ba92  mov     r14d, [rbp+6F0h+var_6C0]
0x18009ba96  mov     edi, [rbp+6F0h+var_6EC]
0x18009ba99  cmp     r11d, edi
0x18009ba9c  jge     short loc_18009BAF8
0x18009ba9e  sub     edi, r11d
0x18009baa1  lea     eax, ds:0[r11*4]
0x18009baa9  movsxd  rdx, eax
0x18009baac  sub     r15, r12
0x18009baaf  add     rdx, r12
0x18009bab2  sub     r10, r12
0x18009bab5  lea     r9d, [rdi-1]
0x18009bab9  shr     r9d, 1
0x18009babc  inc     r9d
0x18009babf  nop
0x18009bac0  movzx   eax, byte ptr [r15+rdx]
0x18009bac5  lea     r8, [r8+2]
0x18009bac9  movzx   ecx, byte ptr [r10+rdx]
0x18009bace  lea     rdx, [rdx+8]
0x18009bad2  add     ecx, eax
0x18009bad4  movzx   eax, byte ptr [rdx-8]
0x18009bad8  add     ecx, eax
0x18009bada  imul    eax, ecx, 55h ; 'U'
0x18009badd  shr     eax, 6
0x18009bae0  mov     [r8-2], ax
0x18009bae5  sub     r9, 1
0x18009bae9  jnz     short loc_18009BAC0
0x18009baeb  mov     esi, [rbp+6F0h+var_DC]
0x18009baf1  mov     r14d, [rbp+6F0h+var_6C0]
0x18009baf5  mov     edi, [rbp+6F0h+var_6EC]
0x18009baf8  mov     r15, [rsp+7F0h+var_7C0]
0x18009bafd  mov     r12d, 0
0x18009bb03  movsxd  rax, esi
0x18009bb06  inc     esi
0x18009bb08  sub     r14d, [rbp+rax*4+6F0h+var_6B4]
0x18009bb0d  cmp     esi, [rbp+6F0h+var_D4]
0x18009bb13  cmovge  esi, r12d
0x18009bb17  inc     [rbp+6F0h+var_6B8]
0x18009bb1a  mov     [rbp+6F0h+var_DC], esi
0x18009bb20  mov     rax, [rsp+7F0h+var_7B8]
0x18009bb25  movsxd  rax, dword ptr [rax]
0x18009bb28  add     r13, rax
0x18009bb2b  mov     eax, dword ptr [rbp+6F0h+var_730]
0x18009bb2e  inc     eax
0x18009bb30  mov     dword ptr [rbp+6F0h+var_730], eax
0x18009bb33  cmp     eax, [rbp+6F0h+var_6F0]
0x18009bb36  jl      loc_18009B832
0x18009bb3c  movaps  xmm12, [rsp+7F0h+var_B0]
0x18009bb45  movaps  xmm11, [rsp+7F0h+var_A0]
0x18009bb4e  movaps  xmm10, [rsp+7F0h+var_90]
0x18009bb57  movaps  xmm9, [rsp+7F0h+var_80]
0x18009bb60  movaps  xmm8, [rsp+7F0h+var_70]
0x18009bb69  movaps  xmm7, [rsp+7F0h+var_60]
0x18009bb71  movaps  xmm6, [rsp+7F0h+var_50]
0x18009bb79  mov     r14, [rsp+7F0h+var_38]
0x18009bb81  mov     rdi, [rsp+7F0h+var_28]
0x18009bb89  mov     rsi, [rsp+7F0h+var_20]
0x18009bb91  mov     r13, [rsp+7F0h+var_30]
0x18009bb99  mov     rcx, [rbp+6F0h+var_C0]
0x18009bba0  xor     rcx, rsp; StackCookie
0x18009bba3  call    __security_check_cookie
0x18009bba8  add     rsp, 7D8h
0x18009bbaf  pop     r15
0x18009bbb1  pop     r12
0x18009bbb3  pop     rbx
0x18009bbb4  pop     rbp
0x18009bbb5  retn
```
