# Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180099c50`
- end: `0x18009a042`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$00$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009d590`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x180099c50`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // r12
  unsigned __int8 *v6; // rbx
  __int64 v7; // r14
  bool v8; // al
  unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // rbx
  bool v11; // di
  bool v12; // di
  unsigned __int8 *v13; // rsi
  bool result; // al
  unsigned __int8 *v15; // r15
  int v16; // r13d
  int v17; // edi
  int v18; // r14d
  int v19; // esi
  unsigned __int8 *v20; // xmm8_8
  __int128 v21; // xmm9
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
  __m128i si128; // xmm7
  const __m128i *v42; // r8
  unsigned __int64 v43; // rdx
  __m128i v44; // xmm2
  __m128i v45; // xmm5
  __m128i v46; // xmm3
  signed __int64 v47; // r15
  unsigned __int8 *v48; // r8
  signed __int64 v49; // r10
  __int64 v50; // r9
  int v51; // ecx
  int v52; // edx
  __int64 v53; // rax
  unsigned __int8 *v56[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v57[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v58; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v59; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+80h] [rbp-80h] BYREF
  int v61; // [rsp+84h] [rbp-7Ch]
  __int64 v62; // [rsp+88h] [rbp-78h]
  _BYTE v63[32]; // [rsp+90h] [rbp-70h] BYREF
  int v64; // [rsp+B0h] [rbp-50h]
  int v65; // [rsp+B4h] [rbp-4Ch]
  int v66; // [rsp+B8h] [rbp-48h]
  _DWORD v67[374]; // [rsp+BCh] [rbp-44h]
  int v68; // [rsp+694h] [rbp+594h]
  int v69; // [rsp+69Ch] [rbp+59Ch]
  int v70; // [rsp+6ACh] [rbp+5ACh]

  *(_OWORD *)v57 = *a4;
  v5 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((__int64)&v60, 1, 1, a3, v57, (_DWORD *)(a1 + 8));
  v6 = *a2;
  v7 = v62;
  v8 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
         (Binary::IntegratedSelection::SmoothControl *)v63,
         *a2,
         v57,
         v56);
  v9 = a2[1];
  v10 = &v6[v7];
  *(_QWORD *)&v58 = v10;
  v11 = v8;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)v63,
          v9,
          v57,
          v56)
     && v11;
  v13 = a2[2];
  *((_QWORD *)&v58 + 1) = &v9[v7];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)v63,
             v13,
             v57,
             v56);
  if ( result && v12 )
  {
    v59 = &v13[v7];
    result = 0;
    v15 = 0;
    v57[0] = 0;
    v16 = 0;
    LODWORD(v56[0]) = 1;
    if ( v60 > 0 )
    {
      v17 = v68;
      v18 = v64;
      v19 = v61;
      v20 = v59;
      v21 = v58;
      do
      {
        v64 = ++v18;
        if ( v18 == 1 )
        {
          v22 = *(_DWORD *)(v5 + 40);
          v23 = 0;
          v24 = *(_DWORD *)(v5 + 28);
          v25 = *(int *)(v5 + 52);
          if ( v65 <= 0 )
            v23 = v65;
          v59 = v20;
          v26 = *(_DWORD *)(v5 + 44);
          v58 = v21;
          if ( v24 < v26 )
            v24 = v26;
          v27 = v25 - 1;
          v28 = v24 - v26;
          v29 = v66;
          if ( v66 < v22 )
            v29 = v22;
          v30 = v25 * ((v29 - v22) % *(_DWORD *)(v5 + 48));
          if ( v28 <= v27 )
            v27 = v28;
          v31 = &v15[(_QWORD)v10];
          v32 = v27;
          v33 = -v23;
          v34 = v70;
          v35 = v32 + v30;
          v36 = *(_QWORD *)(v5 + 56);
          v37 = &v15[*((_QWORD *)&v58 + 1)];
          v38 = &v15[(_QWORD)v59];
          v39 = (__m128i *)(v36 + 2 * v35);
          if ( v70 < 1LL )
          {
            do
            {
              if ( v33 >= v19 )
                break;
              v39->m128i_i16[0] = (85 * (v31[v33] + v38[v33] + (unsigned int)v37[v33])) >> 6;
              v39 = (__m128i *)((char *)v39 + 2);
              v40 = *((_DWORD *)v56 + v34++);
              v33 += v40;
            }
            while ( v34 < 1 );
            v17 = v68;
            v18 = v64;
            v19 = v61;
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
              *v39 = _mm_srli_epi16(
                       _mm_mullo_epi16(
                         _mm_add_epi16(
                           _mm_add_epi16(_mm_unpacklo_epi8(v45, (__m128i)0LL), _mm_unpacklo_epi8(v44, (__m128i)0LL)),
                           _mm_unpacklo_epi8(v46, (__m128i)0LL)),
                         si128),
                       6u);
              v39[1] = _mm_srli_epi16(
                         _mm_mullo_epi16(
                           _mm_add_epi16(
                             _mm_add_epi16(_mm_unpackhi_epi8(v45, (__m128i)0LL), _mm_unpackhi_epi8(v44, (__m128i)0LL)),
                             _mm_unpackhi_epi8(v46, (__m128i)0LL)),
                           si128),
                         6u);
              v39 += 2;
              --v43;
            }
            while ( v43 );
            v17 = v68;
            v18 = v64;
            v19 = v61;
          }
          if ( v33 < v19 )
          {
            v47 = v38 - v37;
            v48 = &v37[v33];
            v49 = v31 - v37;
            v50 = (unsigned int)(v19 - v33);
            do
            {
              v51 = v48[v49];
              v39 = (__m128i *)((char *)v39 + 2);
              v52 = v48[v47];
              v39[-1].m128i_i16[7] = (85 * ((unsigned int)*v48++ + v51 + v52)) >> 6;
              --v50;
            }
            while ( v50 );
            v17 = v68;
            v18 = v64;
            v19 = v61;
          }
          v15 = v57[0];
          v5 = a1;
          v53 = v17++;
          v18 -= v67[v53];
          if ( v17 >= v69 )
            v17 = 0;
          ++v66;
          v68 = v17;
        }
        ++v16;
        v15 += *a3;
        result = 0;
        v57[0] = v15;
      }
      while ( v16 < v60 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180099c50  push    rbp
0x180099c52  push    rbx
0x180099c53  push    rsi
0x180099c54  push    rdi
0x180099c55  push    r12
0x180099c57  push    r14
0x180099c59  push    r15
0x180099c5b  lea     rbp, [rsp-610h]
0x180099c63  sub     rsp, 710h
0x180099c6a  mov     rax, cs:__security_cookie
0x180099c71  xor     rax, rsp
0x180099c74  mov     [rbp+640h+var_90], rax
0x180099c7b  movups  xmm0, xmmword ptr [r9]
0x180099c7f  lea     rax, [rcx+8]
0x180099c83  mov     [rsp+740h+var_708], r8
0x180099c88  mov     [rsp+740h+var_718], rax
0x180099c8d  mov     rsi, rdx
0x180099c90  mov     edx, 1
0x180099c95  mov     [rsp+740h+var_710], rcx
0x180099c9a  lea     rax, [rsp+740h+var_6F0]
0x180099c9f  movaps  xmmword ptr [rsp+740h+var_6F0], xmm0
0x180099ca4  mov     r12, rcx
0x180099ca7  mov     [rsp+740h+var_720], rax
0x180099cac  mov     r9, r8
0x180099caf  lea     rcx, [rbp+640h+var_6C0]
0x180099cb3  mov     r8d, edx
0x180099cb6  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180099cbb  mov     rbx, [rsi]
0x180099cbe  lea     r9, [rsp+740h+var_700]; unsigned __int8 **
0x180099cc3  mov     r14, [rbp+640h+var_6B8]
0x180099cc7  lea     r8, [rsp+740h+var_6F0]; unsigned __int8 **
0x180099ccc  mov     rdx, rbx; unsigned __int8 *
0x180099ccf  lea     rcx, [rbp+640h+var_6B0]; this
0x180099cd3  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180099cd8  mov     r15, [rsi+8]
0x180099cdc  lea     r9, [rsp+740h+var_700]; unsigned __int8 **
0x180099ce1  add     rbx, r14
0x180099ce4  lea     r8, [rsp+740h+var_6F0]; unsigned __int8 **
0x180099ce9  mov     rdx, r15; unsigned __int8 *
0x180099cec  mov     qword ptr [rsp+740h+var_6E0], rbx
0x180099cf1  lea     rcx, [rbp+640h+var_6B0]; this
0x180099cf5  movzx   edi, al
0x180099cf8  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180099cfd  test    al, al
0x180099cff  jz      short loc_180099D0B
0x180099d01  test    dil, dil
0x180099d04  jz      short loc_180099D0B
0x180099d06  mov     dil, 1
0x180099d09  jmp     short loc_180099D0E
0x180099d0b  xor     dil, dil
0x180099d0e  mov     rsi, [rsi+10h]
0x180099d12  lea     rax, [r15+r14]
0x180099d16  mov     rdx, rsi; unsigned __int8 *
0x180099d19  mov     qword ptr [rsp+740h+var_6E0+8], rax
0x180099d1e  lea     r9, [rsp+740h+var_700]; unsigned __int8 **
0x180099d23  lea     r8, [rsp+740h+var_6F0]; unsigned __int8 **
0x180099d28  lea     rcx, [rbp+640h+var_6B0]; this
0x180099d2c  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180099d31  test    al, al
0x180099d33  jz      loc_18009A021
0x180099d39  test    dil, dil
0x180099d3c  jz      loc_18009A021
0x180099d42  lea     rax, [rsi+r14]
0x180099d46  mov     [rsp+740h+var_38], r13
0x180099d4e  mov     [rsp+740h+var_6D0], rax
0x180099d53  xor     eax, eax
0x180099d55  mov     r15d, eax
0x180099d58  mov     [rsp+740h+var_6F0], rax
0x180099d5d  mov     r13d, eax
0x180099d60  mov     dword ptr [rsp+740h+var_700], 1
0x180099d68  cmp     [rbp+640h+var_6C0], eax
0x180099d6b  jle     loc_18009A019
0x180099d71  mov     edi, [rbp+640h+var_AC]
0x180099d77  mov     r14d, [rbp+640h+var_690]
0x180099d7b  mov     esi, [rbp+640h+var_6BC]
0x180099d7e  movaps  [rsp+740h+var_50], xmm6
0x180099d86  movaps  [rsp+740h+var_60], xmm7
0x180099d8e  movaps  [rsp+740h+var_70], xmm8
0x180099d97  movsd   xmm8, [rsp+740h+var_6D0]
0x180099d9e  movaps  [rsp+740h+var_80], xmm9
0x180099da7  movups  xmm9, [rsp+740h+var_6E0]
0x180099dad  nop     dword ptr [rax]
0x180099db0  inc     r14d
0x180099db3  mov     [rbp+640h+var_690], r14d
0x180099db7  cmp     r14d, 1
0x180099dbb  jnz     loc_180099FD5
0x180099dc1  mov     ecx, [r12+28h]
0x180099dc6  mov     r11d, eax
0x180099dc9  mov     r10d, [r12+1Ch]
0x180099dce  mov     eax, [rbp+640h+var_68C]
0x180099dd1  test    eax, eax
0x180099dd3  movsxd  r8, dword ptr [r12+34h]
0x180099dd8  cmovle  r11d, eax
0x180099ddc  movsd   [rsp+740h+var_6D0], xmm8
0x180099de3  mov     eax, [r12+2Ch]
0x180099de8  cmp     r10d, eax
0x180099deb  movups  [rsp+740h+var_6E0], xmm9
0x180099df1  cmovl   r10d, eax
0x180099df5  lea     r9d, [r8-1]
0x180099df9  sub     r10d, eax
0x180099dfc  mov     eax, [rbp+640h+var_688]
0x180099dff  cmp     eax, ecx
0x180099e01  cmovl   eax, ecx
0x180099e04  sub     eax, ecx
0x180099e06  cdq
0x180099e07  idiv    dword ptr [r12+30h]
0x180099e0c  movsxd  rcx, edx
0x180099e0f  imul    rcx, r8
0x180099e13  cmp     r10d, r9d
0x180099e16  cmovle  r9d, r10d
0x180099e1a  lea     r10, [rbx+r15]
0x180099e1e  movsxd  rax, r9d
0x180099e21  neg     r11d
0x180099e24  movsxd  r9, [rbp+640h+var_94]
0x180099e2b  add     rcx, rax
0x180099e2e  mov     rax, [r12+38h]
0x180099e33  mov     r12, qword ptr [rsp+740h+var_6E0+8]
0x180099e38  add     r12, r15
0x180099e3b  add     r15, [rsp+740h+var_6D0]
0x180099e40  lea     rax, [rax+rcx*2]
0x180099e44  cmp     r9, 1
0x180099e48  jge     short loc_180099E99
0x180099e4a  nop     word ptr [rax+rax+00h]
0x180099e50  cmp     r11d, esi
0x180099e53  jge     short loc_180099E8C
0x180099e55  movsxd  rdx, r11d
0x180099e58  movzx   ecx, byte ptr [r15+rdx]
0x180099e5d  movzx   r8d, byte ptr [r12+rdx]
0x180099e62  add     r8d, ecx
0x180099e65  movzx   ecx, byte ptr [r10+rdx]
0x180099e6a  add     r8d, ecx
0x180099e6d  imul    ecx, r8d, 55h ; 'U'
0x180099e71  shr     ecx, 6
0x180099e74  mov     [rax], cx
0x180099e77  add     rax, 2
0x180099e7b  mov     ecx, dword ptr [rsp+r9*4+740h+var_700]
0x180099e80  inc     r9
0x180099e83  add     r11d, ecx
0x180099e86  cmp     r9, 1
0x180099e8a  jl      short loc_180099E50
0x180099e8c  mov     edi, [rbp+640h+var_AC]
0x180099e92  mov     r14d, [rbp+640h+var_690]
0x180099e96  mov     esi, [rbp+640h+var_6BC]
0x180099e99  lea     ecx, [rsi-0Fh]
0x180099e9c  movsxd  r9, r11d
0x180099e9f  movsxd  rdx, ecx
0x180099ea2  cmp     r9, rdx
0x180099ea5  jge     loc_180099F5B
0x180099eab  movdqa  xmm7, cs:__xmm@00550055005500550055005500550055
0x180099eb3  lea     r8, [r12+r9]
0x180099eb7  sub     rdx, r9
0x180099eba  mov     rdi, r10
0x180099ebd  dec     rdx
0x180099ec0  sub     rdi, r12
0x180099ec3  shr     rdx, 4
0x180099ec7  mov     rsi, r15
0x180099eca  sub     rsi, r12
0x180099ecd  xorps   xmm6, xmm6
0x180099ed0  inc     rdx
0x180099ed3  mov     ecx, edx
0x180099ed5  shl     ecx, 4
0x180099ed8  add     r11d, ecx
0x180099edb  nop     dword ptr [rax+rax+00h]
0x180099ee0  movdqu  xmm2, xmmword ptr [rdi+r8]
0x180099ee6  movdqu  xmm5, xmmword ptr [r8]
0x180099eeb  movdqu  xmm3, xmmword ptr [rsi+r8]
0x180099ef1  lea     r8, [r8+10h]
0x180099ef5  movdqa  xmm4, xmm5
0x180099ef9  movdqa  xmm0, xmm2
0x180099efd  punpcklbw xmm4, xmm6
0x180099f01  movdqa  xmm1, xmm3
0x180099f05  punpckhbw xmm5, xmm6
0x180099f09  punpcklbw xmm0, xmm6
0x180099f0d  paddw   xmm4, xmm0
0x180099f11  punpckhbw xmm2, xmm6
0x180099f15  paddw   xmm5, xmm2
0x180099f19  punpcklbw xmm1, xmm6
0x180099f1d  paddw   xmm4, xmm1
0x180099f21  punpckhbw xmm3, xmm6
0x180099f25  paddw   xmm5, xmm3
0x180099f29  pmullw  xmm4, xmm7
0x180099f2d  pmullw  xmm5, xmm7
0x180099f31  psrlw   xmm4, 6
0x180099f36  movdqu  xmmword ptr [rax], xmm4
0x180099f3a  psrlw   xmm5, 6
0x180099f3f  movdqu  xmmword ptr [rax+10h], xmm5
0x180099f44  add     rax, 20h ; ' '
0x180099f48  sub     rdx, 1
0x180099f4c  jnz     short loc_180099EE0
0x180099f4e  mov     edi, [rbp+640h+var_AC]
0x180099f54  mov     r14d, [rbp+640h+var_690]
0x180099f58  mov     esi, [rbp+640h+var_6BC]
0x180099f5b  cmp     r11d, esi
0x180099f5e  jge     short loc_180099FAA
0x180099f60  movsxd  r8, r11d
0x180099f63  sub     r15, r12
0x180099f66  add     r8, r12
0x180099f69  sub     r10, r12
0x180099f6c  sub     esi, r11d
0x180099f6f  mov     r9d, esi
0x180099f72  movzx   ecx, byte ptr [r8+r10]
0x180099f77  lea     rax, [rax+2]
0x180099f7b  movzx   edx, byte ptr [r8+r15]
0x180099f80  lea     r8, [r8+1]
0x180099f84  add     edx, ecx
0x180099f86  movzx   ecx, byte ptr [r8-1]
0x180099f8b  add     edx, ecx
0x180099f8d  imul    ecx, edx, 55h ; 'U'
0x180099f90  shr     ecx, 6
0x180099f93  mov     [rax-2], cx
0x180099f97  sub     r9, 1
0x180099f9b  jnz     short loc_180099F72
0x180099f9d  mov     edi, [rbp+640h+var_AC]
0x180099fa3  mov     r14d, [rbp+640h+var_690]
0x180099fa7  mov     esi, [rbp+640h+var_6BC]
0x180099faa  mov     r15, [rsp+740h+var_6F0]
0x180099faf  mov     r12, [rsp+740h+var_710]
0x180099fb4  movsxd  rax, edi
0x180099fb7  inc     edi
0x180099fb9  sub     r14d, [rbp+rax*4+640h+var_684]
0x180099fbe  mov     eax, 0
0x180099fc3  cmp     edi, [rbp+640h+var_A4]
0x180099fc9  cmovge  edi, eax
0x180099fcc  inc     [rbp+640h+var_688]
0x180099fcf  mov     [rbp+640h+var_AC], edi
0x180099fd5  mov     rax, [rsp+740h+var_708]
0x180099fda  inc     r13d
0x180099fdd  movsxd  rax, dword ptr [rax]
0x180099fe0  add     r15, rax
0x180099fe3  mov     eax, 0
0x180099fe8  mov     [rsp+740h+var_6F0], r15
0x180099fed  cmp     r13d, [rbp+640h+var_6C0]
0x180099ff1  jl      loc_180099DB0
0x180099ff7  movaps  xmm9, [rsp+740h+var_80]
0x18009a000  movaps  xmm8, [rsp+740h+var_70]
0x18009a009  movaps  xmm7, [rsp+740h+var_60]
0x18009a011  movaps  xmm6, [rsp+740h+var_50]
0x18009a019  mov     r13, [rsp+740h+var_38]
0x18009a021  mov     rcx, [rbp+640h+var_90]
0x18009a028  xor     rcx, rsp; StackCookie
0x18009a02b  call    __security_check_cookie
0x18009a030  add     rsp, 710h
0x18009a037  pop     r15
0x18009a039  pop     r14
0x18009a03b  pop     r12
0x18009a03d  pop     rdi
0x18009a03e  pop     rsi
0x18009a03f  pop     rbx
0x18009a040  pop     rbp
0x18009a041  retn
```
