# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800968e0`
- end: `0x180096d80`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$00$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$00@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099bd0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x1800968e0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  unsigned __int8 *v9; // rbx
  __int64 v10; // rdi
  unsigned __int8 *v11; // rdx
  bool v12; // al
  unsigned __int8 *v13; // r15
  unsigned __int8 *v14; // rbx
  bool v15; // si
  bool v16; // si
  unsigned __int8 *v17; // r14
  __int64 v18; // rax
  int v20; // ecx
  __int64 v21; // r13
  int v22; // r12d
  int v25; // esi
  int v26; // edx
  int v27; // edi
  __int64 v28; // r14
  int v29; // r11d
  int v30; // eax
  int v31; // ecx
  int v32; // edx
  int v33; // r10d
  __int64 v34; // r8
  int v35; // r10d
  int v36; // r9d
  int v37; // eax
  __int64 v38; // rsi
  int v39; // edx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r8
  int v43; // r11d
  unsigned __int8 *v44; // r10
  __int64 v45; // rsi
  __int64 v46; // r14
  _WORD *v47; // r9
  int v48; // r11d
  __int64 i; // r8
  unsigned int v51; // ecx
  int v52; // eax
  int v53; // r11d
  int v54; // eax
  unsigned __int64 v60; // rcx
  int v97; // r11d
  __int64 v98; // rsi
  unsigned __int8 *v99; // rdx
  unsigned __int8 *v100; // r10
  __int64 v101; // r8
  unsigned int v102; // eax
  __int64 v103; // rcx
  int v104; // ecx
  __int64 v113; // [rsp+58h] [rbp+0h] BYREF
  char v114; // [rsp+750h] [rbp+6F8h] BYREF

  _RBP = (unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 8) = a3;
  *(_QWORD *)_RBP = a1;
  __asm { vmovups xmmword ptr [rbp+730h+var_710], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 80,
    2,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
    (_DWORD *)(a1 + 8));
  v9 = *a2;
  v10 = *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
  v11 = *a2;
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          v11,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16));
  v13 = a2[1];
  v14 = &v9[v10];
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v14;
  v15 = v12;
  v16 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          v13,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16))
     && v15;
  v17 = a2[2];
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = &v13[v10];
  LOBYTE(v18) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
                  v17,
                  (unsigned __int8 **)(_RBP + 32),
                  (unsigned __int8 **)(_RBP + 16));
  if ( (_BYTE)v18 )
  {
    if ( v16 )
    {
      v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
      LOBYTE(v18) = (_BYTE)v17 + v10;
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = &v17[v10];
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 2;
      v21 = 0;
      v22 = 0;
      if ( v20 > 0 )
      {
        __asm
        {
          vmovsd  xmm10, [rbp+730h+var_6F0]
          vmovups xmm11, [rbp+730h+var_700]
        }
        v25 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
        v26 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
        v27 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
        do
        {
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = ++v26;
          if ( v26 == 1 )
          {
            v28 = *(_QWORD *)_RBP;
            v29 = 0;
            v30 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84);
            __asm { vmovsd  [rbp+730h+var_6F0], xmm10 }
            if ( v30 <= 0 )
              v29 = v30;
            v31 = *(_DWORD *)(v28 + 44);
            v32 = *(_DWORD *)(v28 + 40);
            v33 = *(_DWORD *)(v28 + 28);
            v34 = *(int *)(v28 + 52);
            if ( v33 < v31 )
              v33 = *(_DWORD *)(v28 + 44);
            v35 = v33 - v31;
            v36 = v34 - 1;
            if ( v25 < v32 )
              v25 = *(_DWORD *)(v28 + 40);
            v37 = v25 - v32;
            v38 = *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
            v39 = v37 % *(_DWORD *)(v28 + 48);
            v40 = *(_QWORD *)(v28 + 56);
            v41 = v34 * v39;
            v42 = *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x67C);
            __asm { vmovups [rbp+730h+var_700], xmm11 }
            if ( v35 <= v36 )
              v36 = v35;
            v43 = -v29;
            v44 = &v14[v21];
            v45 = v21 + v38;
            v46 = v21 + *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
            v47 = (_WORD *)(v40 + 2 * v41 + 2LL * v36);
            *v47 = (85
                  * (*(unsigned __int8 *)(v43 + v46) + *(unsigned __int8 *)(v43 + v45) + (unsigned int)v14[v21 + v43])) >> 6;
            v48 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * v42) + v43;
            _R9 = v47 + 1;
            for ( i = (int)v42 + 1; i < 1; v48 += v52 )
            {
              if ( v48 >= v27 )
                break;
              v51 = *(unsigned __int8 *)(v48 + v45) + *(unsigned __int8 *)(v48 + v46) + v44[v48];
              if ( v51 > 0x2F4 )
                v51 = *(unsigned __int8 *)(v48 + v45 - 1) + *(unsigned __int8 *)(v48 + v46 - 1) + v44[v48 - 1];
              *_R9++ = (85 * v51) >> 6;
              v52 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * i++);
            }
            v27 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
            v53 = v48 - 1;
            v54 = v27 - 31;
            if ( v53 < (__int64)(v27 - 31) )
            {
              __asm
              {
                vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
                vmovdqu ymm9, cs:__ymm@03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec
              }
              _R15 = v53 + v46;
              _R8 = &v44[-v46];
              _RDI = v45 - v46;
              v60 = ((unsigned __int64)(v54 - (__int64)v53 - 1) >> 5) + 1;
              v53 += 32 * v60;
              do
              {
                __asm
                {
                  vmovdqu ymm4, ymmword ptr [rdi+r15]
                  vmovdqu ymm6, ymmword ptr [r8+r15]
                  vmovdqu ymm7, ymmword ptr [r15]
                  vpmovzxbw ymm2, xmm4
                  vpmovzxbw ymm0, xmm7
                  vpmovzxbw ymm1, xmm6
                  vpaddw  ymm1, ymm0, ymm1
                  vpaddw  ymm2, ymm1, ymm2
                  vpmullw ymm3, ymm2, ymm8
                  vpsrlw  ymm0, ymm3, 6
                  vpshuflw ymm1, ymm0, 0D8h
                  vpshufhw ymm5, ymm1, 0D8h
                  vextracti128 xmm0, ymm4, 1
                  vpmovzxbw ymm4, xmm0
                  vextracti128 xmm0, ymm7, 1
                  vpmovzxbw ymm2, xmm0
                  vextracti128 xmm1, ymm6, 1
                  vpmovzxbw ymm3, xmm1
                  vpaddw  ymm1, ymm2, ymm3
                  vpaddw  ymm3, ymm1, ymm4
                  vpmullw ymm0, ymm3, ymm8
                  vpsrlw  ymm2, ymm0, 6
                  vpshuflw ymm1, ymm2, 0D8h
                  vpshufhw ymm3, ymm1, 0D8h
                  vpunpcklqdq ymm2, ymm5, ymm3
                  vpunpckhqdq ymm0, ymm5, ymm3
                  vpunpckldq ymm5, ymm2, ymm0
                  vpunpckhdq ymm4, ymm2, ymm0
                  vpunpckhqdq ymm0, ymm5, ymm4
                  vpermq  ymm1, ymm0, 0D8h
                  vpcmpgtw ymm2, ymm1, ymm9
                  vpandn  ymm3, ymm2, ymm1
                  vpunpcklqdq ymm0, ymm5, ymm4
                  vpermq  ymm1, ymm0, 0D8h
                  vpand   ymm2, ymm1, ymm2
                  vpaddw  ymm3, ymm2, ymm3
                  vmovdqu ymmword ptr [r9], ymm3
                }
                _R9 += 16;
                _R15 += 32;
                --v60;
              }
              while ( v60 );
              v27 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
            }
            v97 = v53 + 1;
            if ( v97 < v27 )
            {
              v98 = v45 - v46;
              v99 = (unsigned __int8 *)(v46 + v97 - 1LL);
              v100 = &v44[-v46];
              v101 = ((unsigned int)(v27 - v97 - 1) >> 1) + 1;
              do
              {
                v102 = v99[1] + v100[(_QWORD)v99 + 1] + v99[v98 + 1];
                if ( v102 > 0x2F4 )
                  v102 = *v99 + v100[(_QWORD)v99] + v99[v98];
                v99 += 2;
                *_R9++ = (85 * v102) >> 6;
                --v101;
              }
              while ( v101 );
              v27 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
            }
            v103 = *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v26 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80)
                - *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8C + 4 * v103);
            v104 = v103 + 1;
            if ( v104 >= *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x66C) )
              v104 = 0;
            v25 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) + 1;
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664) = v104;
            v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = v25;
          }
          ++v22;
          v18 = **(int **)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
          v21 += v18;
        }
        while ( v22 < v20 );
      }
    }
  }
  __asm { vzeroupper }
  _R11 = &v114;
  __asm
  {
    vmovaps xmm6, xmmword ptr [r11-18h]
    vmovaps xmm7, xmmword ptr [r11-28h]
    vmovaps xmm8, xmmword ptr [r11-38h]
    vmovaps xmm9, xmmword ptr [r11-48h]
    vmovaps xmm10, xmmword ptr [r11-58h]
    vmovaps xmm11, xmmword ptr [r11-68h]
  }
  return v18;
}

```

## disassembly

```asm
0x1800968e0  mov     rax, rsp
0x1800968e3  push    rbp
0x1800968e4  push    rbx
0x1800968e5  push    rsi
0x1800968e6  push    rdi
0x1800968e7  push    r12
0x1800968e9  push    r13
0x1800968eb  push    r14
0x1800968ed  push    r15
0x1800968ef  sub     rsp, 748h
0x1800968f6  vmovaps xmmword ptr [rax-58h], xmm6
0x1800968fb  vmovaps xmmword ptr [rax-68h], xmm7
0x180096900  vmovaps xmmword ptr [rax-78h], xmm8
0x180096905  vmovaps xmmword ptr [rax-88h], xmm9
0x18009690d  vmovaps xmmword ptr [rax-98h], xmm10
0x180096915  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18009691d  lea     rbp, [rsp+780h+var_730]
0x180096922  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180096926  mov     rax, cs:__security_cookie
0x18009692d  xor     rax, rsp
0x180096930  mov     [rbp+730h+var_B0], rax
0x180096937  vmovups xmm0, xmmword ptr [r9]
0x18009693c  lea     rax, [rcx+8]
0x180096940  mov     [rbp+730h+var_728], r8
0x180096944  mov     [rsp+780h+var_758], rax
0x180096949  mov     r14, rdx
0x18009694c  mov     edx, 2
0x180096951  mov     [rbp+730h+var_730], rcx
0x180096955  lea     rax, [rbp+730h+var_710]
0x180096959  mov     r9, r8
0x18009695c  lea     rcx, [rbp+730h+var_6E0]
0x180096960  mov     [rsp+780h+var_760], rax
0x180096965  vmovups xmmword ptr [rbp+730h+var_710], xmm0
0x18009696a  lea     r8d, [rdx-1]
0x18009696e  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180096973  mov     rbx, [r14]
0x180096976  lea     r9, [rbp+730h+var_720]; unsigned __int8 **
0x18009697a  mov     rdi, [rbp+730h+var_6D8]
0x18009697e  lea     r8, [rbp+730h+var_710]; unsigned __int8 **
0x180096982  mov     rdx, rbx; unsigned __int8 *
0x180096985  mov     qword ptr [rbp+730h+var_700], 0
0x18009698d  lea     rcx, [rbp+730h+var_6D0]; this
0x180096991  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180096996  mov     r15, [r14+8]
0x18009699a  lea     r9, [rbp+730h+var_720]; unsigned __int8 **
0x18009699e  add     rbx, rdi
0x1800969a1  lea     r8, [rbp+730h+var_710]; unsigned __int8 **
0x1800969a5  mov     rdx, r15; unsigned __int8 *
0x1800969a8  mov     qword ptr [rbp+730h+var_700], rbx
0x1800969ac  lea     rcx, [rbp+730h+var_6D0]; this
0x1800969b0  movzx   esi, al
0x1800969b3  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800969b8  test    al, al
0x1800969ba  jz      short loc_1800969C6
0x1800969bc  test    sil, sil
0x1800969bf  jz      short loc_1800969C6
0x1800969c1  mov     sil, 1
0x1800969c4  jmp     short loc_1800969C9
0x1800969c6  xor     sil, sil
0x1800969c9  mov     r14, [r14+10h]
0x1800969cd  lea     rax, [r15+rdi]
0x1800969d1  mov     rdx, r14; unsigned __int8 *
0x1800969d4  mov     qword ptr [rbp+730h+var_700+8], rax
0x1800969d8  lea     r9, [rbp+730h+var_720]; unsigned __int8 **
0x1800969dc  lea     r8, [rbp+730h+var_710]; unsigned __int8 **
0x1800969e0  lea     rcx, [rbp+730h+var_6D0]; this
0x1800969e4  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800969e9  test    al, al
0x1800969eb  jz      loc_180096D32
0x1800969f1  test    sil, sil
0x1800969f4  jz      loc_180096D32
0x1800969fa  mov     ecx, [rbp+730h+var_6E0]
0x1800969fd  lea     rax, [r14+rdi]
0x180096a01  xor     r15d, r15d
0x180096a04  mov     [rbp+730h+var_6F0], rax
0x180096a08  mov     dword ptr [rbp+730h+var_720], 2
0x180096a0f  mov     r13d, r15d
0x180096a12  mov     r12d, r15d
0x180096a15  test    ecx, ecx
0x180096a17  jle     loc_180096D32
0x180096a1d  vmovsd  xmm10, [rbp+730h+var_6F0]
0x180096a22  vmovups xmm11, [rbp+730h+var_700]
0x180096a27  mov     esi, [rbp+730h+var_6A8]
0x180096a2d  mov     edx, [rbp+730h+var_6B0]
0x180096a33  mov     edi, [rbp+730h+var_6DC]
0x180096a36  nop     word ptr [rax+rax+00000000h]
0x180096a40  inc     edx
0x180096a42  mov     [rbp+730h+var_6B0], edx
0x180096a48  cmp     edx, 1
0x180096a4b  jnz     loc_180096D1C
0x180096a51  mov     r14, [rbp+730h+var_730]
0x180096a55  mov     r11d, r15d
0x180096a58  mov     eax, [rbp+730h+var_6AC]
0x180096a5e  test    eax, eax
0x180096a60  vmovsd  [rbp+730h+var_6F0], xmm10
0x180096a65  cmovle  r11d, eax
0x180096a69  mov     ecx, [r14+2Ch]
0x180096a6d  mov     edx, [r14+28h]
0x180096a71  mov     r10d, [r14+1Ch]
0x180096a75  cmp     r10d, ecx
0x180096a78  movsxd  r8, dword ptr [r14+34h]
0x180096a7c  cmovl   r10d, ecx
0x180096a80  sub     r10d, ecx
0x180096a83  cmp     esi, edx
0x180096a85  lea     r9d, [r8-1]
0x180096a89  cmovl   esi, edx
0x180096a8c  sub     esi, edx
0x180096a8e  mov     eax, esi
0x180096a90  mov     rsi, [rbp+730h+var_6F0]
0x180096a94  cdq
0x180096a95  idiv    dword ptr [r14+30h]
0x180096a99  mov     rax, [r14+38h]
0x180096a9d  movsxd  rcx, edx
0x180096aa0  imul    rcx, r8
0x180096aa4  movsxd  r8, [rbp+730h+var_B4]
0x180096aab  cmp     r10d, r9d
0x180096aae  vmovups [rbp+730h+var_700], xmm11
0x180096ab3  mov     r14, qword ptr [rbp+730h+var_700+8]
0x180096ab7  cmovle  r9d, r10d
0x180096abb  neg     r11d
0x180096abe  lea     r10, [rbx+r13]
0x180096ac2  lea     rax, [rax+rcx*2]
0x180096ac6  add     rsi, r13
0x180096ac9  movsxd  rcx, r9d
0x180096acc  add     r14, r13
0x180096acf  lea     r9, [rax+rcx*2]
0x180096ad3  movsxd  rcx, r11d
0x180096ad6  movzx   eax, byte ptr [rcx+rsi]
0x180096ada  movzx   edx, byte ptr [rcx+r10]
0x180096adf  add     edx, eax
0x180096ae1  movzx   eax, byte ptr [rcx+r14]
0x180096ae6  add     edx, eax
0x180096ae8  imul    eax, edx, 55h ; 'U'
0x180096aeb  shr     eax, 6
0x180096aee  mov     [r9], ax
0x180096af2  lea     eax, [r8+1]
0x180096af6  add     r11d, dword ptr [rbp+r8*4+730h+var_720]
0x180096afb  add     r9, 2
0x180096aff  movsxd  r8, eax
0x180096b02  cmp     r8, 1
0x180096b06  jge     short loc_180096B5E
0x180096b08  cmp     r11d, edi
0x180096b0b  jge     short loc_180096B5E
0x180096b0d  movsxd  rdx, r11d
0x180096b10  movzx   eax, byte ptr [rdx+r14]
0x180096b15  movzx   ecx, byte ptr [rdx+r10]
0x180096b1a  add     ecx, eax
0x180096b1c  movzx   eax, byte ptr [rdx+rsi]
0x180096b20  add     ecx, eax
0x180096b22  cmp     ecx, 2F4h
0x180096b28  jbe     short loc_180096B3F
0x180096b2a  movzx   eax, byte ptr [rdx+r14-1]
0x180096b30  movzx   ecx, byte ptr [rdx+r10-1]
0x180096b36  add     ecx, eax
0x180096b38  movzx   eax, byte ptr [rdx+rsi-1]
0x180096b3d  add     ecx, eax
0x180096b3f  imul    eax, ecx, 55h ; 'U'
0x180096b42  shr     eax, 6
0x180096b45  mov     [r9], ax
0x180096b49  add     r9, 2
0x180096b4d  mov     eax, dword ptr [rbp+r8*4+730h+var_720]
0x180096b52  inc     r8
0x180096b55  add     r11d, eax
0x180096b58  cmp     r8, 1
0x180096b5c  jl      short loc_180096B08
0x180096b5e  mov     edi, [rbp+730h+var_6DC]
0x180096b61  dec     r11d
0x180096b64  movsxd  rdx, r11d
0x180096b67  lea     eax, [rdi-1Fh]
0x180096b6a  movsxd  rcx, eax
0x180096b6d  cmp     rdx, rcx
0x180096b70  jge     loc_180096C7B
0x180096b76  vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x180096b7e  vmovdqu ymm9, cs:__ymm@03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec
0x180096b86  sub     rcx, rdx
0x180096b89  lea     r15, [rdx+r14]
0x180096b8d  dec     rcx
0x180096b90  mov     r8, r10
0x180096b93  shr     rcx, 5
0x180096b97  sub     r8, r14
0x180096b9a  mov     rdi, rsi
0x180096b9d  sub     rdi, r14
0x180096ba0  inc     rcx
0x180096ba3  mov     eax, ecx
0x180096ba5  shl     eax, 5
0x180096ba8  add     r11d, eax
0x180096bab  nop     dword ptr [rax+rax+00h]
0x180096bb0  vmovdqu ymm4, ymmword ptr [rdi+r15]
0x180096bb6  vmovdqu ymm6, ymmword ptr [r8+r15]
0x180096bbc  vmovdqu ymm7, ymmword ptr [r15]
0x180096bc1  vpmovzxbw ymm2, xmm4
0x180096bc6  vpmovzxbw ymm0, xmm7
0x180096bcb  vpmovzxbw ymm1, xmm6
0x180096bd0  vpaddw  ymm1, ymm0, ymm1
0x180096bd4  vpaddw  ymm2, ymm1, ymm2
0x180096bd8  vpmullw ymm3, ymm2, ymm8
0x180096bdd  vpsrlw  ymm0, ymm3, 6
0x180096be2  vpshuflw ymm1, ymm0, 0D8h
0x180096be7  vpshufhw ymm5, ymm1, 0D8h
0x180096bec  vextracti128 xmm0, ymm4, 1
0x180096bf2  vpmovzxbw ymm4, xmm0
0x180096bf7  vextracti128 xmm0, ymm7, 1
0x180096bfd  vpmovzxbw ymm2, xmm0
0x180096c02  vextracti128 xmm1, ymm6, 1
0x180096c08  vpmovzxbw ymm3, xmm1
0x180096c0d  vpaddw  ymm1, ymm2, ymm3
0x180096c11  vpaddw  ymm3, ymm1, ymm4
0x180096c15  vpmullw ymm0, ymm3, ymm8
0x180096c1a  vpsrlw  ymm2, ymm0, 6
0x180096c1f  vpshuflw ymm1, ymm2, 0D8h
0x180096c24  vpshufhw ymm3, ymm1, 0D8h
0x180096c29  vpunpcklqdq ymm2, ymm5, ymm3
0x180096c2d  vpunpckhqdq ymm0, ymm5, ymm3
0x180096c31  vpunpckldq ymm5, ymm2, ymm0
0x180096c35  vpunpckhdq ymm4, ymm2, ymm0
0x180096c39  vpunpckhqdq ymm0, ymm5, ymm4
0x180096c3d  vpermq  ymm1, ymm0, 0D8h
0x180096c43  vpcmpgtw ymm2, ymm1, ymm9
0x180096c48  vpandn  ymm3, ymm2, ymm1
0x180096c4c  vpunpcklqdq ymm0, ymm5, ymm4
0x180096c50  vpermq  ymm1, ymm0, 0D8h
0x180096c56  vpand   ymm2, ymm1, ymm2
0x180096c5a  vpaddw  ymm3, ymm2, ymm3
0x180096c5e  vmovdqu ymmword ptr [r9], ymm3
0x180096c63  add     r9, 20h ; ' '
0x180096c67  lea     r15, [r15+20h]
0x180096c6b  sub     rcx, 1
0x180096c6f  jnz     loc_180096BB0
0x180096c75  mov     edi, [rbp+730h+var_6DC]
0x180096c78  xor     r15d, r15d
0x180096c7b  inc     r11d
0x180096c7e  cmp     r11d, edi
0x180096c81  jge     short loc_180096CE5
0x180096c83  sub     edi, r11d
0x180096c86  movsxd  rdx, r11d
0x180096c89  dec     rdx
0x180096c8c  sub     rsi, r14
0x180096c8f  add     rdx, r14
0x180096c92  sub     r10, r14
0x180096c95  lea     r8d, [rdi-1]
0x180096c99  shr     r8d, 1
0x180096c9c  inc     r8d
0x180096c9f  nop
0x180096ca0  movzx   ecx, byte ptr [rdx+r10+1]
0x180096ca6  movzx   eax, byte ptr [rdx+rsi+1]
0x180096cab  add     eax, ecx
0x180096cad  movzx   ecx, byte ptr [rdx+1]
0x180096cb1  add     eax, ecx
0x180096cb3  cmp     eax, 2F4h
0x180096cb8  jbe     short loc_180096CCA
0x180096cba  movzx   ecx, byte ptr [rdx+r10]
0x180096cbf  movzx   eax, byte ptr [rdx+rsi]
0x180096cc3  add     eax, ecx
0x180096cc5  movzx   ecx, byte ptr [rdx]
0x180096cc8  add     eax, ecx
0x180096cca  imul    ecx, eax, 55h ; 'U'
0x180096ccd  add     rdx, 2
0x180096cd1  shr     ecx, 6
0x180096cd4  mov     [r9], cx
0x180096cd8  add     r9, 2
0x180096cdc  sub     r8, 1
0x180096ce0  jnz     short loc_180096CA0
0x180096ce2  mov     edi, [rbp+730h+var_6DC]
0x180096ce5  movsxd  rcx, [rbp+730h+var_CC]
0x180096cec  mov     esi, [rbp+730h+var_6A8]
0x180096cf2  mov     edx, [rbp+730h+var_6B0]
0x180096cf8  sub     edx, [rbp+rcx*4+730h+var_6A4]
0x180096cff  inc     ecx
0x180096d01  cmp     ecx, [rbp+730h+var_C4]
0x180096d07  cmovge  ecx, r15d
0x180096d0b  inc     esi
0x180096d0d  mov     [rbp+730h+var_CC], ecx
0x180096d13  mov     ecx, [rbp+730h+var_6E0]
0x180096d16  mov     [rbp+730h+var_6A8], esi
0x180096d1c  mov     rax, [rbp+730h+var_728]
0x180096d20  inc     r12d
0x180096d23  movsxd  rax, dword ptr [rax]
0x180096d26  add     r13, rax
0x180096d29  cmp     r12d, ecx
0x180096d2c  jl      loc_180096A40
0x180096d32  vzeroupper
0x180096d35  mov     rcx, [rbp+730h+var_B0]
0x180096d3c  xor     rcx, rsp; StackCookie
0x180096d3f  call    __security_check_cookie
0x180096d44  lea     r11, [rsp+780h+var_38]
0x180096d4c  vmovaps xmm6, xmmword ptr [r11-18h]
0x180096d52  vmovaps xmm7, xmmword ptr [r11-28h]
0x180096d58  vmovaps xmm8, xmmword ptr [r11-38h]
0x180096d5e  vmovaps xmm9, xmmword ptr [r11-48h]
0x180096d64  vmovaps xmm10, xmmword ptr [r11-58h]
0x180096d6a  vmovaps xmm11, xmmword ptr [r11-68h]
0x180096d70  mov     rsp, r11
0x180096d73  pop     r15
0x180096d75  pop     r14
0x180096d77  pop     r13
0x180096d79  pop     r12
0x180096d7b  pop     rdi
0x180096d7c  pop     rsi
0x180096d7d  pop     rbx
0x180096d7e  pop     rbp
  ... truncated ...
```
