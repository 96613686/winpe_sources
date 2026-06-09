# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009ce70`
- end: `0x18009d582`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$07$01$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1810`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009d600`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x180067110`
- `0x1800963a0`
- `0x18009ce70`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
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
  unsigned __int8 *v12; // r12
  int v13; // r11d
  int v14; // edi
  int v15; // r15d
  int v16; // ecx
  unsigned __int8 *v17; // r13
  int v18; // r10d
  __int64 v19; // r8
  int v20; // eax
  int v21; // r10d
  int v22; // r9d
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int8 *v25; // r8
  int v26; // esi
  __m128i *v27; // r14
  unsigned __int8 *v28; // rcx
  __int64 v29; // r12
  unsigned __int8 *v30; // rbx
  __int64 v31; // rdi
  double v32; // xmm0_8
  float v33; // xmm7_4
  double v34; // xmm0_8
  float v35; // xmm6_4
  double v36; // xmm0_8
  int v37; // eax
  __m128i si128; // xmm12
  __m128i v39; // xmm13
  __m128i v40; // xmm14
  const __m128i *v41; // rcx
  __int64 v42; // r9
  __m128i *v43; // rax
  __int64 v44; // rdx
  __m128i v45; // xmm1
  __m128i v46; // xmm0
  __m128i v47; // xmm1
  __m128i v48; // xmm8
  __m128i v49; // xmm4
  __m128i v50; // xmm2
  __m128i v51; // xmm1
  __m128i v52; // xmm0
  __m128i v53; // xmm3
  __m128i v54; // xmm5
  __m128i v55; // xmm3
  __m128i v56; // xmm8
  __m128i v57; // xmm1
  __m128i v58; // xmm2
  __m128i v59; // xmm0
  __m128i v60; // xmm1
  __m128i v61; // xmm9
  __m128 v62; // xmm7
  __m128 v63; // xmm9
  __m128i v64; // xmm1
  __m128i v65; // xmm2
  __m128i v66; // xmm0
  __m128i v67; // xmm1
  __m128i v68; // xmm6
  __m128 v69; // xmm5
  __m128 v70; // xmm6
  __m128i v71; // xmm2
  __m128i v72; // xmm3
  __m128i v73; // xmm0
  __m128i v74; // xmm2
  __m128i v75; // xmm4
  unsigned __int8 *v76; // rdi
  unsigned __int8 *v77; // rbx
  __int64 v78; // r13
  __int64 v79; // rsi
  double v80; // xmm0_8
  float v81; // xmm7_4
  double v82; // xmm0_8
  float v83; // xmm6_4
  double v84; // xmm0_8
  __int64 v85; // rax
  int v87; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v88; // [rsp+38h] [rbp-C8h]
  __m128i v91; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v92; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v93; // [rsp+70h] [rbp-90h] BYREF
  __m128i v94[5]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v95; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v96[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v97[2]; // [rsp+F0h] [rbp-10h]
  __int128 v98; // [rsp+F8h] [rbp-8h]
  __int64 v99; // [rsp+108h] [rbp+8h]
  __int128 v100; // [rsp+118h] [rbp+18h]
  int v101; // [rsp+140h] [rbp+40h] BYREF
  int v102; // [rsp+144h] [rbp+44h]
  __int64 v103; // [rsp+148h] [rbp+48h]
  char v104[32]; // [rsp+150h] [rbp+50h] BYREF
  int v105; // [rsp+170h] [rbp+70h]
  int v106; // [rsp+174h] [rbp+74h]
  int v107; // [rsp+178h] [rbp+78h]
  _DWORD v108[374]; // [rsp+17Ch] [rbp+7Ch]
  int v109; // [rsp+754h] [rbp+654h]
  int v110; // [rsp+75Ch] [rbp+65Ch]
  int v111; // [rsp+76Ch] [rbp+66Ch]

  v5 = a1;
  *(_OWORD *)v96 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v101, 2, 1, (_DWORD)a3, (__int64)v96, a1 + 8);
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
  v10 = &v8[v103];
  *(_QWORD *)&v98 = &v8[v103];
  *((_QWORD *)&v98 + 1) = &v8[v103 + 2];
  v99 = (__int64)&v8[v103 + 4];
  LOBYTE(v11) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v104,
                  v8,
                  &v95,
                  v96);
  if ( (_BYTE)v11 )
  {
    v12 = 0;
    v96[0] = 0;
    v97[0] = 2;
    v87 = 0;
    if ( v101 > 0 )
    {
      v13 = v109;
      v14 = v105;
      v15 = v102;
      do
      {
        v105 = ++v14;
        if ( v14 == 1 )
        {
          v16 = *(_DWORD *)(v5 + 40);
          v17 = &v12[(_QWORD)v10];
          v18 = *(_DWORD *)(v5 + 28);
          v19 = *(int *)(v5 + 52);
          if ( v106 <= 0 )
            v9 = v106;
          v20 = *(_DWORD *)(v5 + 44);
          if ( v18 < v20 )
            v18 = *(_DWORD *)(v5 + 44);
          v21 = v18 - v20;
          v22 = v19 - 1;
          v23 = v107;
          v100 = v98;
          if ( v107 < v16 )
            v23 = v16;
          v24 = v19 * ((v23 - v16) % *(_DWORD *)(v5 + 48));
          if ( v21 <= v22 )
            v22 = v21;
          v25 = &v12[v99];
          v26 = -v9;
          v88 = &v12[v99];
          v27 = (__m128i *)(*(_QWORD *)(v5 + 56) + 2 * (v22 + v24));
          v28 = &v12[*((_QWORD *)&v100 + 1)];
          v29 = v111;
          v95 = v28;
          if ( v111 < 1LL )
          {
            v30 = v28;
            do
            {
              if ( v26 >= v15 )
                break;
              v31 = 8 * v26;
              v32 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v30[v31]);
              v33 = *(float *)&v32;
              v34 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v88[v31]);
              v35 = *(float *)&v34;
              v36 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v17[v31]);
              v27->m128i_i16[0] = (int)fmaxf(
                                         0.0,
                                         fminf(
                                           1023.0,
                                           (float)((float)(*(float *)&v36 + v33) + v35) * (float)(1023.0 / 3.0)));
              v27 = (__m128i *)((char *)v27 + 2);
              v37 = v97[v29++];
              v26 += v37;
            }
            while ( v29 < 1 );
            v13 = v109;
            v14 = v105;
            v15 = v102;
            v10 = (unsigned __int8 *)v98;
            v25 = v88;
          }
          if ( v26 < v15 - 15 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v39 = _mm_load_si128((const __m128i *)&_xmm);
            v40 = _mm_load_si128((const __m128i *)&_xmm);
            v41 = (const __m128i *)&v17[8 * v26 + 32];
            v42 = ((unsigned int)(v15 - 15 - v26 - 1) >> 4) + 1;
            v26 += 16 * v42;
            do
            {
              v43 = &v93;
              v44 = 2;
              do
              {
                v43 += 4;
                v45 = _mm_loadu_si128(v41 - 1);
                v43[-6] = _mm_loadu_si128(v41 - 2);
                v46 = _mm_loadu_si128(v41);
                v43[-5] = v45;
                v47 = _mm_loadu_si128(v41 + 1);
                v41 += 4;
                v43[-4] = v46;
                v43[-3] = v47;
                --v44;
              }
              while ( v44 );
              v48 = _mm_unpacklo_epi16(_mm_load_si128(&v91), v94[1]);
              v49 = _mm_unpacklo_epi16(_mm_load_si128(&v92), v94[2]);
              v50 = _mm_unpacklo_epi16(_mm_load_si128(&v93), v94[3]);
              v51 = _mm_unpacklo_epi16(_mm_load_si128(v94), v94[4]);
              v52 = _mm_unpacklo_epi16(v49, v51);
              v53 = _mm_unpacklo_epi16(v48, v50);
              v54 = _mm_unpackhi_epi16(v53, v52);
              v55 = _mm_unpacklo_epi16(v53, v52);
              v56 = _mm_unpacklo_epi16(_mm_unpackhi_epi16(v48, v50), _mm_unpackhi_epi16(v49, v51));
              v57 = _mm_andnot_si128(_mm_cmpeq_epi16(v55, v40), v55);
              v58 = _mm_and_si128(v57, v39);
              v59 = _mm_srli_epi16(_mm_slli_epi16(v57, 1u), 0xBu);
              v60 = _mm_slli_epi16(v57, 6u);
              v61 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v59, (__m128i)0LL), si128), v59);
              v62 = (__m128)_mm_or_si128(
                              _mm_or_si128(
                                _mm_slli_epi32(_mm_unpacklo_epi16(v61, (__m128i)0LL), 0x17u),
                                _mm_slli_epi32(_mm_unpacklo_epi16(v60, (__m128i)0LL), 7u)),
                              _mm_unpacklo_epi16((__m128i)0LL, v58));
              v63 = (__m128)_mm_or_si128(
                              _mm_or_si128(
                                _mm_slli_epi32(_mm_unpackhi_epi16(v61, (__m128i)0LL), 0x17u),
                                _mm_slli_epi32(_mm_unpackhi_epi16(v60, (__m128i)0LL), 7u)),
                              _mm_unpackhi_epi16((__m128i)0LL, v58));
              v64 = _mm_andnot_si128(_mm_cmpeq_epi16(v54, v40), v54);
              v65 = _mm_and_si128(v64, v39);
              v66 = _mm_srli_epi16(_mm_slli_epi16(v64, 1u), 0xBu);
              v67 = _mm_slli_epi16(v64, 6u);
              v68 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v66, (__m128i)0LL), si128), v66);
              v69 = _mm_add_ps(
                      (__m128)_mm_or_si128(
                                _mm_or_si128(
                                  _mm_slli_epi32(_mm_unpacklo_epi16(v68, (__m128i)0LL), 0x17u),
                                  _mm_slli_epi32(_mm_unpacklo_epi16(v67, (__m128i)0LL), 7u)),
                                _mm_unpacklo_epi16((__m128i)0LL, v65)),
                      v62);
              v70 = _mm_add_ps(
                      (__m128)_mm_or_si128(
                                _mm_or_si128(
                                  _mm_slli_epi32(_mm_unpackhi_epi16(v68, (__m128i)0LL), 0x17u),
                                  _mm_slli_epi32(_mm_unpackhi_epi16(v67, (__m128i)0LL), 7u)),
                                _mm_unpackhi_epi16((__m128i)0LL, v65)),
                      v63);
              v71 = _mm_andnot_si128(_mm_cmpeq_epi16(v56, v40), v56);
              v72 = _mm_and_si128(v71, v39);
              v73 = _mm_srli_epi16(_mm_slli_epi16(v71, 1u), 0xBu);
              v74 = _mm_slli_epi16(v71, 6u);
              v75 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v73, (__m128i)0LL), si128), v73);
              *v27++ = _mm_packs_epi32(
                         _mm_cvttps_epi32(
                           _mm_max_ps(
                             _mm_min_ps(
                               _mm_mul_ps(
                                 _mm_add_ps(
                                   v69,
                                   (__m128)_mm_or_si128(
                                             _mm_or_si128(
                                               _mm_slli_epi32(_mm_unpacklo_epi16(v75, (__m128i)0LL), 0x17u),
                                               _mm_slli_epi32(_mm_unpacklo_epi16(v74, (__m128i)0LL), 7u)),
                                             _mm_unpacklo_epi16((__m128i)0LL, v72))),
                                 (__m128)_xmm),
                               (__m128)_xmm),
                             (__m128)0LL)),
                         _mm_cvttps_epi32(
                           _mm_max_ps(
                             _mm_min_ps(
                               _mm_mul_ps(
                                 _mm_add_ps(
                                   v70,
                                   (__m128)_mm_or_si128(
                                             _mm_or_si128(
                                               _mm_slli_epi32(_mm_unpackhi_epi16(v75, (__m128i)0LL), 0x17u),
                                               _mm_slli_epi32(_mm_unpackhi_epi16(v74, (__m128i)0LL), 7u)),
                                             _mm_unpackhi_epi16((__m128i)0LL, v72))),
                                 (__m128)_xmm),
                               (__m128)_xmm),
                             (__m128)0LL)));
              --v42;
            }
            while ( v42 );
            v13 = v109;
            v14 = v105;
            v15 = v102;
          }
          if ( v26 < v15 )
          {
            v76 = &v25[8 * v26];
            v77 = (unsigned __int8 *)(v95 - v25);
            v78 = v17 - v25;
            v79 = ((unsigned int)(v15 - v26 - 1) >> 1) + 1;
            do
            {
              v80 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v76[(_QWORD)v77]);
              v81 = *(float *)&v80;
              v82 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v76);
              v83 = *(float *)&v82;
              v84 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v76[v78]);
              v76 += 16;
              v27->m128i_i16[0] = (int)fmaxf(
                                         0.0,
                                         fminf(
                                           1023.0,
                                           (float)((float)(*(float *)&v84 + v81) + v83) * (float)(1023.0 / 3.0)));
              v27 = (__m128i *)((char *)v27 + 2);
              --v79;
            }
            while ( v79 );
            v13 = v109;
            v14 = v105;
            v15 = v102;
            v10 = (unsigned __int8 *)v98;
          }
          v5 = a1;
          v9 = 0;
          v12 = v96[0];
          v85 = v13++;
          v14 -= v108[v85];
          if ( v13 >= v110 )
            v13 = 0;
          ++v107;
          v109 = v13;
        }
        v12 += *a3;
        v11 = v87 + 1;
        v96[0] = v12;
        v87 = v11;
      }
      while ( v11 < v101 );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18009ce70  push    rbp
0x18009ce72  push    rbx
0x18009ce73  push    rsi
0x18009ce74  push    r14
0x18009ce76  lea     rbp, [rsp-748h]
0x18009ce7e  sub     rsp, 848h
0x18009ce85  mov     rax, cs:__security_cookie
0x18009ce8c  xor     rax, rsp
0x18009ce8f  mov     [rbp+760h+var_F0], rax
0x18009ce96  movups  xmm0, xmmword ptr [r9]
0x18009ce9a  lea     rax, [rcx+8]
0x18009ce9e  mov     [rsp+860h+var_818], r8
0x18009cea3  mov     [rsp+860h+var_838], rax
0x18009cea8  mov     rbx, rdx
0x18009ceab  mov     edx, 2
0x18009ceb0  mov     [rsp+860h+var_820], rcx
0x18009ceb5  mov     r14, rcx
0x18009ceb8  movaps  xmmword ptr [rbp+760h+var_780], xmm0
0x18009cebc  lea     rax, [rbp+760h+var_780]
0x18009cec0  mov     r9, r8
0x18009cec3  lea     rcx, [rbp+760h+var_720]
0x18009cec7  mov     [rsp+860h+var_840], rax
0x18009cecc  lea     r8d, [rdx-1]
0x18009ced0  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009ced5  mov     rcx, [rbx+8]
0x18009ced9  lea     r9, [rbp+760h+var_780]; unsigned __int8 **
0x18009cedd  mov     rax, [rbx+10h]
0x18009cee1  lea     r8, [rbp+760h+var_790]; unsigned __int8 **
0x18009cee5  mov     rdx, [rbx+18h]
0x18009cee9  xor     esi, esi
0x18009ceeb  cmp     [rbx], rcx
0x18009ceee  cmovbe  rcx, [rbx]
0x18009cef2  mov     rbx, [rbp+760h+var_718]
0x18009cef6  cmp     rcx, rax
0x18009cef9  cmovbe  rax, rcx
0x18009cefd  lea     rcx, [rbp+760h+var_710]; this
0x18009cf01  cmp     rax, rdx
0x18009cf04  cmovbe  rdx, rax; unsigned __int8 *
0x18009cf08  add     rbx, rdx
0x18009cf0b  mov     qword ptr [rbp+760h+var_768], rbx
0x18009cf0f  lea     rax, [rbx+2]
0x18009cf13  mov     qword ptr [rbp+760h+var_768+8], rax
0x18009cf17  lea     rax, [rbx+4]
0x18009cf1b  mov     [rbp+760h+var_758], rax
0x18009cf1f  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009cf24  test    al, al
0x18009cf26  jz      loc_18009D566
0x18009cf2c  mov     [rsp+860h+var_28], r12
0x18009cf34  mov     r12d, esi
0x18009cf37  mov     [rbp+760h+var_780], rsi
0x18009cf3b  mov     [rbp+760h+var_770], 2
0x18009cf42  mov     [rsp+860h+var_830], esi
0x18009cf46  cmp     [rbp+760h+var_720], esi
0x18009cf49  jle     loc_18009D55E
0x18009cf4f  mov     r11d, [rbp+760h+var_10C]
0x18009cf56  mov     [rsp+860h+var_20], rdi
0x18009cf5e  mov     edi, [rbp+760h+var_6F0]
0x18009cf61  mov     [rsp+860h+var_30], r13
0x18009cf69  mov     [rsp+860h+var_38], r15
0x18009cf71  mov     r15d, [rbp+760h+var_71C]
0x18009cf75  movaps  [rsp+860h+var_50], xmm6
0x18009cf7d  movaps  [rsp+860h+var_60], xmm7
0x18009cf85  movaps  [rsp+860h+var_70], xmm8
0x18009cf8e  movaps  [rsp+860h+var_80], xmm9
0x18009cf97  movaps  [rsp+860h+var_90], xmm10
0x18009cfa0  movss   xmm10, cs:__real@447fc000
0x18009cfa9  movaps  [rsp+860h+var_A0], xmm11
0x18009cfb2  movaps  [rsp+860h+var_B0], xmm12
0x18009cfbb  movaps  [rsp+860h+var_C0], xmm13
0x18009cfc4  movaps  [rsp+860h+var_D0], xmm14
0x18009cfcd  movaps  [rsp+860h+var_E0], xmm15
0x18009cfd6  nop     word ptr [rax+rax+00000000h]
0x18009cfe0  inc     edi
0x18009cfe2  mov     [rbp+760h+var_6F0], edi
0x18009cfe5  cmp     edi, 1
0x18009cfe8  jnz     loc_18009D4CC
0x18009cfee  mov     ecx, [r14+28h]
0x18009cff2  lea     r13, [rbx+r12]
0x18009cff6  mov     eax, [rbp+760h+var_6EC]
0x18009cff9  test    eax, eax
0x18009cffb  mov     r10d, [r14+1Ch]
0x18009cfff  movsxd  r8, dword ptr [r14+34h]
0x18009d003  cmovle  esi, eax
0x18009d006  mov     eax, [r14+2Ch]
0x18009d00a  cmp     r10d, eax
0x18009d00d  movups  xmm0, [rbp+760h+var_768]
0x18009d011  cmovl   r10d, eax
0x18009d015  sub     r10d, eax
0x18009d018  lea     r9d, [r8-1]
0x18009d01c  mov     eax, [rbp+760h+var_6E8]
0x18009d01f  cmp     eax, ecx
0x18009d021  movups  [rbp+760h+var_748], xmm0
0x18009d025  cmovl   eax, ecx
0x18009d028  sub     eax, ecx
0x18009d02a  cdq
0x18009d02b  idiv    dword ptr [r14+30h]
0x18009d02f  movsxd  rcx, edx
0x18009d032  imul    rcx, r8
0x18009d036  mov     r8, [rbp+760h+var_758]
0x18009d03a  cmp     r10d, r9d
0x18009d03d  cmovle  r9d, r10d
0x18009d041  add     r8, r12
0x18009d044  movsxd  rax, r9d
0x18009d047  neg     esi
0x18009d049  add     rcx, rax
0x18009d04c  mov     [rsp+860h+var_828], r8
0x18009d051  mov     rax, [r14+38h]
0x18009d055  lea     r14, [rax+rcx*2]
0x18009d059  mov     rcx, qword ptr [rbp+760h+var_748+8]
0x18009d05d  add     rcx, r12
0x18009d060  movsxd  r12, [rbp+760h+var_F4]
0x18009d067  mov     [rbp+760h+var_790], rcx
0x18009d06b  cmp     r12, 1
0x18009d06f  jge     loc_18009D106
0x18009d075  mov     rbx, rcx
0x18009d078  cmp     esi, r15d
0x18009d07b  jge     short loc_18009D0EF
0x18009d07d  lea     eax, ds:0[rsi*8]
0x18009d084  movsxd  rdi, eax
0x18009d087  lea     rcx, [rbx+rdi]
0x18009d08b  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009d090  mov     rcx, [rsp+860h+var_828]
0x18009d095  movaps  xmm7, xmm0
0x18009d098  add     rcx, rdi
0x18009d09b  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009d0a0  lea     rcx, [rdi+r13]
0x18009d0a4  movaps  xmm6, xmm0
0x18009d0a7  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009d0ac  addss   xmm0, xmm7
0x18009d0b0  movaps  xmm1, xmm10
0x18009d0b4  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18009d0bc  addss   xmm0, xmm6
0x18009d0c0  movaps  xmm2, xmm10
0x18009d0c4  mulss   xmm0, xmm1
0x18009d0c8  minss   xmm2, xmm0
0x18009d0cc  xorps   xmm0, xmm0
0x18009d0cf  maxss   xmm0, xmm2
0x18009d0d3  cvttss2si eax, xmm0
0x18009d0d7  mov     [r14], ax
0x18009d0db  add     r14, 2
0x18009d0df  mov     eax, [rbp+r12*4+760h+var_770]
0x18009d0e4  inc     r12
0x18009d0e7  add     esi, eax
0x18009d0e9  cmp     r12, 1
0x18009d0ed  jl      short loc_18009D078
0x18009d0ef  mov     r11d, [rbp+760h+var_10C]
0x18009d0f6  mov     edi, [rbp+760h+var_6F0]
0x18009d0f9  mov     r15d, [rbp+760h+var_71C]
0x18009d0fd  mov     rbx, qword ptr [rbp+760h+var_768]
0x18009d101  mov     r8, [rsp+860h+var_828]
0x18009d106  lea     edx, [r15-0Fh]
0x18009d10a  cmp     esi, edx
0x18009d10c  jge     loc_18009D405
0x18009d112  movdqa  xmm12, cs:__xmm@00700070007000700070007000700070
0x18009d11b  sub     edx, esi
0x18009d11d  movdqa  xmm13, cs:__xmm@80008000800080008000800080008000
0x18009d126  xorps   xmm11, xmm11
0x18009d12a  movdqa  xmm14, cs:__xmm@7fff7fff7fff7fff7fff7fff7fff7fff
0x18009d133  movaps  xmm15, cs:__xmm@43aa800043aa800043aa800043aa8000
0x18009d13b  movsxd  rax, esi
0x18009d13e  lea     rcx, ds:20h[rax*8]
0x18009d146  lea     eax, [rdx-1]
0x18009d149  add     rcx, r13
0x18009d14c  shr     eax, 4
0x18009d14f  inc     eax
0x18009d151  mov     r9d, eax
0x18009d154  shl     eax, 4
0x18009d157  add     esi, eax
0x18009d159  nop     dword ptr [rax+00000000h]
0x18009d160  lea     rax, [rsp+860h+var_7F0]
0x18009d165  mov     edx, 2
0x18009d16a  nop     word ptr [rax+rax+00h]
0x18009d170  movdqu  xmm0, xmmword ptr [rcx-20h]
0x18009d175  lea     rax, [rax+40h]
0x18009d179  movdqu  xmm1, xmmword ptr [rcx-10h]
0x18009d17e  movdqu  xmmword ptr [rax-60h], xmm0
0x18009d183  movdqu  xmm0, xmmword ptr [rcx]
0x18009d187  movdqu  xmmword ptr [rax-50h], xmm1
0x18009d18c  movdqu  xmm1, xmmword ptr [rcx+10h]
0x18009d191  add     rcx, 40h ; '@'
0x18009d195  movdqu  xmmword ptr [rax-40h], xmm0
0x18009d19a  movdqu  xmmword ptr [rax-30h], xmm1
0x18009d19f  sub     rdx, 1
0x18009d1a3  jnz     short loc_18009D170
0x18009d1a5  movdqa  xmm8, [rsp+860h+var_810]
0x18009d1ac  punpcklwd xmm8, [rbp+760h+var_7D0]
0x18009d1b2  movdqa  xmm4, [rsp+860h+var_800]
0x18009d1b8  movdqa  xmm5, xmm8
0x18009d1bd  punpcklwd xmm4, [rbp+760h+var_7C0]
0x18009d1c2  movdqa  xmm2, [rsp+860h+var_7F0]
0x18009d1c8  movdqa  xmm0, xmm4
0x18009d1cc  punpcklwd xmm2, [rbp+760h+var_7B0]
0x18009d1d1  movdqa  xmm1, [rbp+760h+var_7E0]
0x18009d1d6  punpcklwd xmm1, [rbp+760h+var_7A0]
0x18009d1db  punpcklwd xmm0, xmm1
0x18009d1df  punpcklwd xmm5, xmm2
0x18009d1e3  punpckhwd xmm8, xmm2
0x18009d1e8  movdqa  xmm3, xmm5
0x18009d1ec  punpckhwd xmm5, xmm0
0x18009d1f0  punpcklwd xmm3, xmm0
0x18009d1f4  punpckhwd xmm4, xmm1
0x18009d1f8  movdqa  xmm2, xmm3
0x18009d1fc  pcmpeqw xmm2, xmm14
0x18009d201  punpcklwd xmm8, xmm4
0x18009d206  pandn   xmm2, xmm3
0x18009d20a  movdqa  xmm3, xmm8
0x18009d20f  movdqa  xmm0, xmm2
0x18009d213  movdqa  xmm1, xmm2
0x18009d217  psllw   xmm0, 1
0x18009d21c  pand    xmm2, xmm13
0x18009d221  psrlw   xmm0, 0Bh
0x18009d226  movdqa  xmm9, xmm0
0x18009d22b  psllw   xmm1, 6
0x18009d230  pcmpgtw xmm9, xmm11
0x18009d235  pand    xmm9, xmm12
0x18009d23a  paddw   xmm9, xmm0
0x18009d23f  movdqa  xmm0, xmm1
0x18009d243  punpcklwd xmm0, xmm11
0x18009d248  movdqa  xmm7, xmm9
0x18009d24d  pslld   xmm0, 7
0x18009d252  punpckhwd xmm1, xmm11
0x18009d257  pslld   xmm1, 7
0x18009d25c  punpcklwd xmm7, xmm11
0x18009d261  punpckhwd xmm9, xmm11
0x18009d266  pslld   xmm7, 17h
0x18009d26b  por     xmm7, xmm0
0x18009d26f  pslld   xmm9, 17h
0x18009d275  por     xmm9, xmm1
0x18009d27a  movdqa  xmm0, xmm11
0x18009d27f  punpcklwd xmm0, xmm2
0x18009d283  por     xmm7, xmm0
0x18009d287  movdqa  xmm0, xmm11
0x18009d28c  punpckhwd xmm0, xmm2
0x18009d290  movdqa  xmm2, xmm5
0x18009d294  por     xmm9, xmm0
0x18009d299  pcmpeqw xmm2, xmm14
0x18009d29e  pandn   xmm2, xmm5
0x18009d2a2  movdqa  xmm0, xmm2
0x18009d2a6  movdqa  xmm1, xmm2
0x18009d2aa  psllw   xmm0, 1
0x18009d2af  pand    xmm2, xmm13
0x18009d2b4  psrlw   xmm0, 0Bh
0x18009d2b9  movdqa  xmm6, xmm0
0x18009d2bd  psllw   xmm1, 6
0x18009d2c2  pcmpgtw xmm6, xmm11
0x18009d2c7  pand    xmm6, xmm12
0x18009d2cc  paddw   xmm6, xmm0
0x18009d2d0  movdqa  xmm0, xmm1
0x18009d2d4  movdqa  xmm5, xmm6
0x18009d2d8  punpcklwd xmm0, xmm11
0x18009d2dd  pslld   xmm0, 7
0x18009d2e2  punpcklwd xmm5, xmm11
0x18009d2e7  punpckhwd xmm6, xmm11
0x18009d2ec  pslld   xmm5, 17h
0x18009d2f1  por     xmm5, xmm0
0x18009d2f5  pslld   xmm6, 17h
0x18009d2fa  movdqa  xmm0, xmm11
0x18009d2ff  punpckhwd xmm1, xmm11
0x18009d304  punpcklwd xmm0, xmm2
0x18009d308  por     xmm5, xmm0
0x18009d30c  pslld   xmm1, 7
0x18009d311  movdqa  xmm0, xmm11
0x18009d316  por     xmm6, xmm1
0x18009d31a  punpckhwd xmm0, xmm2
0x18009d31e  por     xmm6, xmm0
0x18009d322  addps   xmm5, xmm7
0x18009d325  pcmpeqw xmm3, xmm14
0x18009d32a  addps   xmm6, xmm9
0x18009d32e  pandn   xmm3, xmm8
0x18009d333  movdqa  xmm0, xmm3
0x18009d337  movdqa  xmm2, xmm3
0x18009d33b  psllw   xmm0, 1
0x18009d340  pand    xmm3, xmm13
0x18009d345  psrlw   xmm0, 0Bh
0x18009d34a  movdqa  xmm4, xmm0
0x18009d34e  psllw   xmm2, 6
0x18009d353  pcmpgtw xmm4, xmm11
0x18009d358  pand    xmm4, xmm12
0x18009d35d  paddw   xmm4, xmm0
0x18009d361  movdqa  xmm0, xmm2
0x18009d365  punpcklwd xmm0, xmm11
0x18009d36a  movdqa  xmm1, xmm4
0x18009d36e  pslld   xmm0, 7
0x18009d373  punpcklwd xmm1, xmm11
0x18009d378  pslld   xmm1, 17h
0x18009d37d  por     xmm1, xmm0
0x18009d381  punpckhwd xmm4, xmm11
0x18009d386  punpckhwd xmm2, xmm11
0x18009d38b  movdqa  xmm0, xmm11
0x18009d390  punpcklwd xmm0, xmm3
0x18009d394  por     xmm1, xmm0
0x18009d398  pslld   xmm4, 17h
0x18009d39d  addps   xmm5, xmm1
0x18009d3a0  pslld   xmm2, 7
0x18009d3a5  por     xmm4, xmm2
0x18009d3a9  movdqa  xmm0, xmm11
0x18009d3ae  punpckhwd xmm0, xmm3
0x18009d3b2  xorps   xmm2, xmm2
0x18009d3b5  por     xmm4, xmm0
0x18009d3b9  addps   xmm6, xmm4
  ... truncated ...
```
