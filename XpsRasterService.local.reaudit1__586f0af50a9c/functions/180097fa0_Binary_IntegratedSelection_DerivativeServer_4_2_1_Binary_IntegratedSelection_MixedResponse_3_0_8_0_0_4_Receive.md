# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180097fa0`
- end: `0x180098450`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$03$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099c00`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x180097fa0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  __int64 v11; // r15
  unsigned __int8 *v12; // rcx
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rdx
  unsigned __int8 *v15; // rbx
  int v16; // eax
  __int64 v18; // r13
  int v20; // esi
  int v21; // r14d
  int v22; // edi
  int v23; // edx
  int v24; // ecx
  int v25; // r11d
  __int64 v26; // r9
  int v27; // eax
  int v28; // r10d
  int v29; // r11d
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // r12
  __int64 v33; // rax
  unsigned __int8 *v34; // r11
  __int64 v35; // r10
  __int64 v36; // r8
  __int64 v37; // rax
  int v38; // ecx
  __int64 v39; // r15
  int v41; // eax
  __int64 v45; // rdx
  __int64 v96; // r15
  __int64 v97; // rdx
  unsigned __int8 *v98; // r11
  __int64 v99; // r8
  int v100; // eax
  int v101; // ecx
  __int64 v102; // rax
  __int64 v113; // [rsp+58h] [rbp+0h] BYREF
  char v114; // [rsp+770h] [rbp+718h] BYREF

  _RBP = (__int64 *)((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL);
  __asm { vmovups xmm0, xmmword ptr [r9] }
  _RBP[1] = (__int64)a3;
  *_RBP = a1;
  v11 = a1;
  __asm { vmovups xmmword ptr [rbp+750h+var_730], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 80,
    2,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
    (_DWORD *)(a1 + 8));
  v12 = a2[1];
  v13 = a2[2];
  v14 = a2[3];
  if ( *a2 <= v12 )
    v12 = *a2;
  if ( v12 <= v13 )
    v13 = v12;
  if ( v13 <= v14 )
    v14 = v13;
  v15 = &v14[*(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58)];
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v15;
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = v15 + 1;
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = v15 + 2;
  *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v15 + 3;
  LOBYTE(v16) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 12),
                  v14,
                  (unsigned __int8 **)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 16),
                  (unsigned __int8 **)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 32));
  if ( (_BYTE)v16 )
  {
    v18 = 0;
    *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 2;
    *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    if ( *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) > 0 )
    {
      __asm { vmovups ymm13, [rbp+750h+var_720] }
      v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
      v21 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
      v22 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = ++v21;
        if ( v21 == 1 )
        {
          v23 = *(_DWORD *)(v11 + 40);
          v24 = 0;
          v25 = *(_DWORD *)(v11 + 28);
          v26 = *(int *)(v11 + 52);
          if ( *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84) <= 0 )
            v24 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84);
          v27 = *(_DWORD *)(v11 + 44);
          __asm { vmovups [rbp+750h+var_720], ymm13 }
          v28 = v26 - 1;
          if ( v25 < v27 )
            v25 = v27;
          v29 = v25 - v27;
          v30 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          if ( v30 < v23 )
            v30 = v23;
          v31 = v26 * ((v30 - v23) % *(_DWORD *)(v11 + 48));
          if ( v29 <= v28 )
            v28 = v29;
          v32 = v18 + *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
          v33 = v28;
          v34 = &v15[v18];
          v35 = *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x67C);
          v36 = v33 + v31;
          v37 = *(_QWORD *)(v11 + 56);
          v38 = -v24;
          v39 = v18 + *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
          _R9 = (_WORD *)(v37 + 2 * v36);
          if ( v35 < 1 )
          {
            do
            {
              if ( v38 >= v22 )
                break;
              *_R9++ = (85
                      * (*(unsigned __int8 *)(v32 + 4 * v38)
                       + *(unsigned __int8 *)(v39 + 4 * v38)
                       + (unsigned int)v34[4 * v38])) >> 6;
              v41 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20 + 4 * v35++);
              v38 += v41;
            }
            while ( v35 < 1 );
            v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v21 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v22 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          if ( v38 < v22 - 63 )
          {
            __asm { vmovdqu ymm12, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055 }
            _R10 = 0;
            _R8 = &v15[4 * v38 + 144 + v18];
            v45 = ((unsigned int)(v22 - 63 - v38 - 1) >> 6) + 1;
            v38 += (_DWORD)v45 << 6;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [r8+r10-90h]
                vinsertf128 ymm10, ymm0, xmmword ptr [r8+r10-10h], 1
                vmovups xmm1, xmmword ptr [r8-80h]
                vinsertf128 ymm11, ymm1, xmmword ptr [r8], 1
                vmovups xmm0, xmmword ptr [r8-70h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r8+10h], 1
                vmovups xmm1, xmmword ptr [r8-60h]
                vinsertf128 ymm9, ymm1, xmmword ptr [r8+20h], 1
                vmovups xmm0, xmmword ptr [r8-50h]
                vinsertf128 ymm5, ymm0, xmmword ptr [r8+r10+30h], 1
                vmovups xmm1, xmmword ptr [r8-40h]
                vinsertf128 ymm8, ymm1, xmmword ptr [r8+40h], 1
                vmovups xmm0, xmmword ptr [r8-30h]
                vinsertf128 ymm3, ymm0, xmmword ptr [r8+50h], 1
                vmovups xmm1, xmmword ptr [r8-20h]
                vinsertf128 ymm4, ymm1, xmmword ptr [r8+60h], 1
                vpunpcklbw ymm2, ymm7, ymm3
                vpunpckhbw ymm1, ymm7, ymm3
                vpunpcklbw ymm0, ymm10, ymm5
                vpunpcklbw ymm6, ymm0, ymm2
                vpunpckhbw ymm0, ymm10, ymm5
                vpunpcklbw ymm7, ymm0, ymm1
                vpunpcklbw ymm0, ymm9, ymm4
                vpunpcklbw ymm2, ymm11, ymm8
                vpunpcklbw ymm3, ymm2, ymm0
                vpunpckhbw ymm5, ymm6, ymm3
                vpunpckhbw ymm0, ymm9, ymm4
                vpunpcklbw ymm4, ymm6, ymm3
                vpunpckhbw ymm1, ymm11, ymm8
                vpunpcklbw ymm2, ymm1, ymm0
                vpunpcklbw ymm0, ymm7, ymm2
                vpunpcklbw ymm6, ymm4, ymm0
                vpunpckhbw ymm1, ymm7, ymm2
                vpunpckhbw ymm7, ymm4, ymm0
                vpunpcklbw ymm4, ymm5, ymm1
                vpmovzxbw ymm0, xmm7
                vpmovzxbw ymm2, xmm4
                vpmovzxbw ymm1, xmm6
                vpaddw  ymm1, ymm0, ymm1
                vpaddw  ymm2, ymm1, ymm2
                vpmullw ymm3, ymm2, ymm12
                vextracti128 xmm0, ymm4, 1
                vpmovzxbw ymm4, xmm0
                vpsrlw  ymm5, ymm3, 6
                vextracti128 xmm1, ymm6, 1
                vextracti128 xmm0, ymm7, 1
                vpmovzxbw ymm2, xmm0
                vpmovzxbw ymm3, xmm1
                vpaddw  ymm1, ymm2, ymm3
                vmovdqu ymmword ptr [r9], ymm5
                vpaddw  ymm3, ymm1, ymm4
                vpmullw ymm0, ymm3, ymm12
                vpsrlw  ymm2, ymm0, 6
                vmovdqu ymmword ptr [r9+20h], ymm2
              }
              _R9 += 32;
              _R8 += 256;
              --v45;
            }
            while ( v45 );
            v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v21 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v22 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          if ( v38 < v22 )
          {
            v96 = v39 - v32;
            v97 = v32 + 4 * v38;
            v98 = &v34[-v32];
            v99 = ((unsigned int)(v22 - v38 - 1) >> 1) + 1;
            do
            {
              v100 = *(unsigned __int8 *)(v96 + v97);
              ++_R9;
              v101 = v98[v97];
              v97 += 8;
              *(_R9 - 1) = (85 * ((unsigned int)*(unsigned __int8 *)(v97 - 8) + v100 + v101)) >> 6;
              --v99;
            }
            while ( v99 );
            v20 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v21 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v22 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          v11 = *_RBP;
          v102 = v20++;
          v21 -= *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8C + 4 * v102);
          if ( v20 >= *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x66C) )
            v20 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664) = v20;
        }
        v18 += **(int **)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        v16 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) + 1;
        *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = v16;
      }
      while ( v16 < *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) );
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
    vmovaps xmm12, xmmword ptr [r11-78h]
    vmovaps xmm13, xmmword ptr [r11-88h]
  }
  return v16;
}

```

## disassembly

```asm
0x180097fa0  mov     rax, rsp
0x180097fa3  push    rbp
0x180097fa4  push    rbx
0x180097fa5  push    rsi
0x180097fa6  push    rdi
0x180097fa7  push    r12
0x180097fa9  push    r13
0x180097fab  push    r14
0x180097fad  push    r15
0x180097faf  sub     rsp, 768h
0x180097fb6  vmovaps xmmword ptr [rax-58h], xmm6
0x180097fbb  vmovaps xmmword ptr [rax-68h], xmm7
0x180097fc0  vmovaps xmmword ptr [rax-78h], xmm8
0x180097fc5  vmovaps xmmword ptr [rax-88h], xmm9
0x180097fcd  vmovaps xmmword ptr [rax-98h], xmm10
0x180097fd5  vmovaps xmmword ptr [rax-0A8h], xmm11
0x180097fdd  vmovaps xmmword ptr [rax-0B8h], xmm12
0x180097fe5  vmovaps xmmword ptr [rax-0C8h], xmm13
0x180097fed  lea     rbp, [rsp+7A0h+var_750]
0x180097ff2  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180097ff6  mov     rax, cs:__security_cookie
0x180097ffd  xor     rax, rsp
0x180098000  mov     [rbp+750h+var_D0], rax
0x180098007  vmovups xmm0, xmmword ptr [r9]
0x18009800c  lea     rax, [rcx+8]
0x180098010  mov     [rbp+750h+var_748], r8
0x180098014  mov     [rsp+7A0h+var_778], rax
0x180098019  mov     rbx, rdx
0x18009801c  mov     edx, 2
0x180098021  mov     [rbp+750h+var_750], rcx
0x180098025  mov     r15, rcx
0x180098028  lea     rax, [rbp+750h+var_730]
0x18009802c  mov     r9, r8
0x18009802f  mov     [rsp+7A0h+var_780], rax
0x180098034  lea     rcx, [rbp+750h+var_700]
0x180098038  lea     r8d, [rdx-1]
0x18009803c  vmovups xmmword ptr [rbp+750h+var_730], xmm0
0x180098041  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180098046  mov     rcx, [rbx+8]
0x18009804a  lea     r9, [rbp+750h+var_730]; unsigned __int8 **
0x18009804e  mov     rax, [rbx+10h]
0x180098052  lea     r8, [rbp+750h+var_740]; unsigned __int8 **
0x180098056  mov     rdx, [rbx+18h]
0x18009805a  xor     r12d, r12d
0x18009805d  cmp     [rbx], rcx
0x180098060  cmovbe  rcx, [rbx]
0x180098064  mov     rbx, [rbp+750h+var_6F8]
0x180098068  cmp     rcx, rax
0x18009806b  cmovbe  rax, rcx
0x18009806f  lea     rcx, [rbp+750h+var_6F0]; this
0x180098073  cmp     rax, rdx
0x180098076  cmovbe  rdx, rax; unsigned __int8 *
0x18009807a  add     rbx, rdx
0x18009807d  mov     qword ptr [rbp+750h+var_720], rbx
0x180098081  lea     rax, [rbx+1]
0x180098085  mov     qword ptr [rbp+750h+var_720+8], rax
0x180098089  lea     rax, [rbx+2]
0x18009808d  mov     qword ptr [rbp+750h+var_720+10h], rax
0x180098091  lea     rax, [rbx+3]
0x180098095  mov     qword ptr [rbp+750h+var_720+18h], rax
0x180098099  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009809e  test    al, al
0x1800980a0  jz      loc_1800983F3
0x1800980a6  mov     r13d, r12d
0x1800980a9  mov     dword ptr [rbp+750h+var_730], 2
0x1800980b0  mov     dword ptr [rbp+750h+var_740], r12d
0x1800980b4  cmp     [rbp+750h+var_700], r12d
0x1800980b8  jle     loc_1800983F3
0x1800980be  vmovups ymm13, [rbp+750h+var_720]
0x1800980c3  mov     esi, [rbp+750h+var_EC]
0x1800980c9  mov     r14d, [rbp+750h+var_6D0]
0x1800980d0  mov     edi, [rbp+750h+var_6FC]
0x1800980d3  nop     dword ptr [rax+00h]
0x1800980d7  nop     word ptr [rax+rax+00000000h]
0x1800980e0  inc     r14d
0x1800980e3  mov     [rbp+750h+var_6D0], r14d
0x1800980ea  cmp     r14d, 1
0x1800980ee  jnz     loc_1800983D8
0x1800980f4  mov     edx, [r15+28h]
0x1800980f8  mov     ecx, r12d
0x1800980fb  mov     r11d, [r15+1Ch]
0x1800980ff  mov     eax, [rbp+750h+var_6CC]
0x180098105  test    eax, eax
0x180098107  movsxd  r9, dword ptr [r15+34h]
0x18009810b  cmovle  ecx, eax
0x18009810e  mov     eax, [r15+2Ch]
0x180098112  cmp     r11d, eax
0x180098115  vmovups [rbp+750h+var_720], ymm13
0x18009811a  mov     r12, qword ptr [rbp+750h+var_720+8]
0x18009811e  lea     r10d, [r9-1]
0x180098122  cmovl   r11d, eax
0x180098126  sub     r11d, eax
0x180098129  mov     eax, [rbp+750h+var_6C8]
0x18009812f  cmp     eax, edx
0x180098131  cmovl   eax, edx
0x180098134  sub     eax, edx
0x180098136  cdq
0x180098137  idiv    dword ptr [r15+30h]
0x18009813b  movsxd  r8, edx
0x18009813e  imul    r8, r9
0x180098142  cmp     r11d, r10d
0x180098145  cmovle  r10d, r11d
0x180098149  add     r12, r13
0x18009814c  movsxd  rax, r10d
0x18009814f  lea     r11, [rbx+r13]
0x180098153  movsxd  r10, [rbp+750h+var_D4]
0x18009815a  add     r8, rax
0x18009815d  mov     rax, [r15+38h]
0x180098161  neg     ecx
0x180098163  mov     r15, qword ptr [rbp+750h+var_720+10h]
0x180098167  add     r15, r13
0x18009816a  lea     r9, [rax+r8*2]
0x18009816e  cmp     r10, 1
0x180098172  jge     short loc_1800981C6
0x180098174  cmp     ecx, edi
0x180098176  jge     short loc_1800981B6
0x180098178  lea     eax, ds:0[rcx*4]
0x18009817f  movsxd  rdx, eax
0x180098182  movzx   eax, byte ptr [r15+rdx]
0x180098187  movzx   r8d, byte ptr [r11+rdx]
0x18009818c  add     r8d, eax
0x18009818f  movzx   eax, byte ptr [r12+rdx]
0x180098194  add     r8d, eax
0x180098197  imul    eax, r8d, 55h ; 'U'
0x18009819b  shr     eax, 6
0x18009819e  mov     [r9], ax
0x1800981a2  add     r9, 2
0x1800981a6  mov     eax, dword ptr [rbp+r10*4+750h+var_730]
0x1800981ab  inc     r10
0x1800981ae  add     ecx, eax
0x1800981b0  cmp     r10, 1
0x1800981b4  jl      short loc_180098174
0x1800981b6  mov     esi, [rbp+750h+var_EC]
0x1800981bc  mov     r14d, [rbp+750h+var_6D0]
0x1800981c3  mov     edi, [rbp+750h+var_6FC]
0x1800981c6  lea     edx, [rdi-3Fh]
0x1800981c9  cmp     ecx, edx
0x1800981cb  jge     loc_180098340
0x1800981d1  vmovdqu ymm12, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x1800981d9  sub     edx, ecx
0x1800981db  movsxd  r8, ecx
0x1800981de  add     r8, 24h ; '$'
0x1800981e2  mov     r10, r11
0x1800981e5  sub     r10, rbx
0x1800981e8  sub     r10, r13
0x1800981eb  lea     eax, [rdx-1]
0x1800981ee  shr     eax, 6
0x1800981f1  lea     r8, [rbx+r8*4]
0x1800981f5  inc     eax
0x1800981f7  add     r8, r13
0x1800981fa  mov     edx, eax
0x1800981fc  shl     eax, 6
0x1800981ff  add     ecx, eax
0x180098201  vmovups xmm0, xmmword ptr [r8+r10-90h]
0x18009820b  vinsertf128 ymm10, ymm0, xmmword ptr [r8+r10-10h], 1
0x180098213  vmovups xmm1, xmmword ptr [r8-80h]
0x180098219  vinsertf128 ymm11, ymm1, xmmword ptr [r8], 1
0x18009821f  vmovups xmm0, xmmword ptr [r8-70h]
0x180098225  vinsertf128 ymm7, ymm0, xmmword ptr [r8+10h], 1
0x18009822c  vmovups xmm1, xmmword ptr [r8-60h]
0x180098232  vinsertf128 ymm9, ymm1, xmmword ptr [r8+20h], 1
0x180098239  vmovups xmm0, xmmword ptr [r8-50h]
0x18009823f  vinsertf128 ymm5, ymm0, xmmword ptr [r8+r10+30h], 1
0x180098247  vmovups xmm1, xmmword ptr [r8-40h]
0x18009824d  vinsertf128 ymm8, ymm1, xmmword ptr [r8+40h], 1
0x180098254  vmovups xmm0, xmmword ptr [r8-30h]
0x18009825a  vinsertf128 ymm3, ymm0, xmmword ptr [r8+50h], 1
0x180098261  vmovups xmm1, xmmword ptr [r8-20h]
0x180098267  vinsertf128 ymm4, ymm1, xmmword ptr [r8+60h], 1
0x18009826e  vpunpcklbw ymm2, ymm7, ymm3
0x180098272  vpunpckhbw ymm1, ymm7, ymm3
0x180098276  vpunpcklbw ymm0, ymm10, ymm5
0x18009827a  vpunpcklbw ymm6, ymm0, ymm2
0x18009827e  vpunpckhbw ymm0, ymm10, ymm5
0x180098282  vpunpcklbw ymm7, ymm0, ymm1
0x180098286  vpunpcklbw ymm0, ymm9, ymm4
0x18009828a  vpunpcklbw ymm2, ymm11, ymm8
0x18009828f  vpunpcklbw ymm3, ymm2, ymm0
0x180098293  vpunpckhbw ymm5, ymm6, ymm3
0x180098297  vpunpckhbw ymm0, ymm9, ymm4
0x18009829b  vpunpcklbw ymm4, ymm6, ymm3
0x18009829f  vpunpckhbw ymm1, ymm11, ymm8
0x1800982a4  vpunpcklbw ymm2, ymm1, ymm0
0x1800982a8  vpunpcklbw ymm0, ymm7, ymm2
0x1800982ac  vpunpcklbw ymm6, ymm4, ymm0
0x1800982b0  vpunpckhbw ymm1, ymm7, ymm2
0x1800982b4  vpunpckhbw ymm7, ymm4, ymm0
0x1800982b8  vpunpcklbw ymm4, ymm5, ymm1
0x1800982bc  vpmovzxbw ymm0, xmm7
0x1800982c1  vpmovzxbw ymm2, xmm4
0x1800982c6  vpmovzxbw ymm1, xmm6
0x1800982cb  vpaddw  ymm1, ymm0, ymm1
0x1800982cf  vpaddw  ymm2, ymm1, ymm2
0x1800982d3  vpmullw ymm3, ymm2, ymm12
0x1800982d8  vextracti128 xmm0, ymm4, 1
0x1800982de  vpmovzxbw ymm4, xmm0
0x1800982e3  vpsrlw  ymm5, ymm3, 6
0x1800982e8  vextracti128 xmm1, ymm6, 1
0x1800982ee  vextracti128 xmm0, ymm7, 1
0x1800982f4  vpmovzxbw ymm2, xmm0
0x1800982f9  vpmovzxbw ymm3, xmm1
0x1800982fe  vpaddw  ymm1, ymm2, ymm3
0x180098302  vmovdqu ymmword ptr [r9], ymm5
0x180098307  vpaddw  ymm3, ymm1, ymm4
0x18009830b  vpmullw ymm0, ymm3, ymm12
0x180098310  vpsrlw  ymm2, ymm0, 6
0x180098315  vmovdqu ymmword ptr [r9+20h], ymm2
0x18009831b  add     r9, 40h ; '@'
0x18009831f  lea     r8, [r8+100h]
0x180098326  sub     rdx, 1
0x18009832a  jnz     loc_180098201
0x180098330  mov     esi, [rbp+750h+var_EC]
0x180098336  mov     r14d, [rbp+750h+var_6D0]
0x18009833d  mov     edi, [rbp+750h+var_6FC]
0x180098340  cmp     ecx, edi
0x180098342  jge     short loc_1800983AB
0x180098344  sub     edi, ecx
0x180098346  lea     eax, ds:0[rcx*4]
0x18009834d  movsxd  rdx, eax
0x180098350  sub     r15, r12
0x180098353  add     rdx, r12
0x180098356  sub     r11, r12
0x180098359  lea     r8d, [rdi-1]
0x18009835d  shr     r8d, 1
0x180098360  inc     r8d
0x180098363  nop     dword ptr [rax+00h]
0x180098367  nop     word ptr [rax+rax+00000000h]
0x180098370  movzx   eax, byte ptr [r15+rdx]
0x180098375  lea     r9, [r9+2]
0x180098379  movzx   ecx, byte ptr [r11+rdx]
0x18009837e  lea     rdx, [rdx+8]
0x180098382  add     ecx, eax
0x180098384  movzx   eax, byte ptr [rdx-8]
0x180098388  add     ecx, eax
0x18009838a  imul    eax, ecx, 55h ; 'U'
0x18009838d  shr     eax, 6
0x180098390  mov     [r9-2], ax
0x180098395  sub     r8, 1
0x180098399  jnz     short loc_180098370
0x18009839b  mov     esi, [rbp+750h+var_EC]
0x1800983a1  mov     r14d, [rbp+750h+var_6D0]
0x1800983a8  mov     edi, [rbp+750h+var_6FC]
0x1800983ab  mov     r15, [rbp+750h+var_750]
0x1800983af  mov     r12d, 0
0x1800983b5  movsxd  rax, esi
0x1800983b8  inc     esi
0x1800983ba  sub     r14d, [rbp+rax*4+750h+var_6C4]
0x1800983c2  cmp     esi, [rbp+750h+var_E4]
0x1800983c8  cmovge  esi, r12d
0x1800983cc  inc     [rbp+750h+var_6C8]
0x1800983d2  mov     [rbp+750h+var_EC], esi
0x1800983d8  mov     rax, [rbp+750h+var_748]
0x1800983dc  movsxd  rax, dword ptr [rax]
0x1800983df  add     r13, rax
0x1800983e2  mov     eax, dword ptr [rbp+750h+var_740]
0x1800983e5  inc     eax
0x1800983e7  mov     dword ptr [rbp+750h+var_740], eax
0x1800983ea  cmp     eax, [rbp+750h+var_700]
0x1800983ed  jl      loc_1800980E0
0x1800983f3  vzeroupper
0x1800983f6  mov     rcx, [rbp+750h+var_D0]
0x1800983fd  xor     rcx, rsp; StackCookie
0x180098400  call    __security_check_cookie
0x180098405  lea     r11, [rsp+7A0h+var_38]
0x18009840d  vmovaps xmm6, xmmword ptr [r11-18h]
0x180098413  vmovaps xmm7, xmmword ptr [r11-28h]
0x180098419  vmovaps xmm8, xmmword ptr [r11-38h]
0x18009841f  vmovaps xmm9, xmmword ptr [r11-48h]
0x180098425  vmovaps xmm10, xmmword ptr [r11-58h]
0x18009842b  vmovaps xmm11, xmmword ptr [r11-68h]
0x180098431  vmovaps xmm12, xmmword ptr [r11-78h]
0x180098437  vmovaps xmm13, xmmword ptr [r11-88h]
0x180098440  mov     rsp, r11
0x180098443  pop     r15
0x180098445  pop     r14
0x180098447  pop     r13
0x180098449  pop     r12
0x18009844b  pop     rdi
0x18009844c  pop     rsi
0x18009844d  pop     rbx
0x18009844e  pop     rbp
0x18009844f  retn
```
