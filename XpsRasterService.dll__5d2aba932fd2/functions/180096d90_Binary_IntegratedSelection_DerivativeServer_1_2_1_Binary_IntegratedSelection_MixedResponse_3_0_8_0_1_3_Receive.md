# Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180096d90`
- end: `0x1800971c2`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$00$01$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1074`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, __int64, __int64 _R9)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099bd0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x180096d90`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,2,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        __int64 a3,
        __int64 _R9)
{
  __int64 v9; // r12
  unsigned __int8 *v10; // rbx
  __int64 v11; // rsi
  bool v12; // al
  unsigned __int8 *v13; // r15
  unsigned __int8 *v14; // rbx
  bool v15; // di
  bool v16; // di
  unsigned __int8 *v17; // r14
  bool result; // al
  __int64 v20; // r15
  int v21; // r13d
  int v24; // esi
  int v25; // r14d
  int v26; // edi
  int v27; // ecx
  int v28; // r11d
  int v29; // r10d
  __int64 v30; // r8
  int v31; // eax
  int v32; // r9d
  int v33; // r10d
  int v34; // eax
  __int64 v35; // rcx
  unsigned __int8 *v36; // r10
  __int64 v37; // rax
  int v38; // r11d
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r12
  __int64 v43; // r15
  int v45; // ecx
  int v46; // ecx
  unsigned __int64 v51; // rdx
  __int64 v82; // r8
  __int64 v83; // r15
  unsigned __int8 *v84; // r10
  __int64 v85; // r9
  int v86; // ecx
  int v87; // edx
  __int64 v88; // rax
  __int64 v95; // [rsp+58h] [rbp+0h] BYREF
  char v96; // [rsp+740h] [rbp+6E8h] BYREF

  _RBP = (unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 8) = a3;
  *(_QWORD *)_RBP = a1;
  v9 = a1;
  __asm { vmovups xmmword ptr [rbp+720h+var_700], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 80,
    2,
    1,
    a3,
    ((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 32,
    a1 + 8);
  v10 = *a2;
  v11 = *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          *a2,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16));
  v13 = a2[1];
  v14 = &v10[v11];
  *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v14;
  v15 = v12;
  v16 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          v13,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16))
     && v15;
  v17 = a2[2];
  *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = &v13[v11];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
             v17,
             (unsigned __int8 **)(_RBP + 32),
             (unsigned __int8 **)(_RBP + 16));
  if ( result && v16 )
  {
    *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 2;
    *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = &v17[v11];
    result = 0;
    v20 = 0;
    *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v21 = 0;
    if ( *(int *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) > 0 )
    {
      __asm
      {
        vmovsd  xmm9, [rbp+720h+var_6E0]
        vmovups xmm10, [rbp+720h+var_6F0]
      }
      v24 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
      v25 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
      v26 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = ++v25;
        if ( v25 == 1 )
        {
          v27 = *(_DWORD *)(v9 + 40);
          v28 = 0;
          v29 = *(_DWORD *)(v9 + 28);
          v30 = *(int *)(v9 + 52);
          if ( *(int *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84) <= 0 )
            v28 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84);
          v31 = *(_DWORD *)(v9 + 44);
          __asm { vmovups [rbp+720h+var_6F0], xmm10 }
          if ( v29 < v31 )
            v29 = v31;
          v32 = v30 - 1;
          v33 = v29 - v31;
          v34 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          __asm { vmovsd  [rbp+720h+var_6E0], xmm9 }
          if ( v34 < v27 )
            v34 = v27;
          v35 = v30 * ((v34 - v27) % *(_DWORD *)(v9 + 48));
          if ( v33 <= v32 )
            v32 = v33;
          v36 = &v14[v20];
          v37 = v32;
          v38 = -v28;
          v39 = *(int *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x67C);
          v40 = v37 + v35;
          v41 = *(_QWORD *)(v9 + 56);
          v42 = v20 + *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
          v43 = *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) + v20;
          _RAX = (_WORD *)(v41 + 2 * v40);
          if ( v39 < 1 )
          {
            do
            {
              if ( v38 >= v26 )
                break;
              *_RAX++ = (85
                       * (*(unsigned __int8 *)(v38 + v43) + *(unsigned __int8 *)(v38 + v42) + (unsigned int)v36[v38])) >> 6;
              v45 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * v39++);
              v38 += v45;
            }
            while ( v39 < 1 );
            v24 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          v46 = v26 - 31;
          if ( v38 < (__int64)(v26 - 31) )
          {
            __asm { vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055 }
            _RSI = v42 + v38;
            _R9 = &v36[-v42];
            _RDI = v43 - v42;
            v51 = ((unsigned __int64)(v46 - (__int64)v38 - 1) >> 5) + 1;
            v38 += 32 * v51;
            do
            {
              __asm
              {
                vmovdqu ymm4, ymmword ptr [rdi+rsi]
                vmovdqu ymm6, ymmword ptr [r9+rsi]
                vmovdqu ymm7, ymmword ptr [rsi]
                vpmovzxbw ymm0, xmm7
                vpmovzxbw ymm2, xmm4
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
                vpunpckhdq ymm1, ymm2, ymm0
                vpunpckldq ymm0, ymm2, ymm0
                vpunpcklqdq ymm1, ymm0, ymm1
                vpermq  ymm2, ymm1, 0D8h
                vmovdqu ymmword ptr [rax], ymm2
              }
              _RAX += 16;
              _RSI += 32;
              --v51;
            }
            while ( v51 );
            v24 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          if ( v38 < v26 )
          {
            v82 = v42 + v38;
            v83 = v43 - v42;
            v84 = &v36[-v42];
            v85 = ((unsigned int)(v26 - v38 - 1) >> 1) + 1;
            do
            {
              v86 = v84[v82];
              ++_RAX;
              v87 = *(unsigned __int8 *)(v82 + v83);
              v82 += 2;
              *(_RAX - 1) = (85 * ((unsigned int)*(unsigned __int8 *)(v82 - 2) + v86 + v87)) >> 6;
              --v85;
            }
            while ( v85 );
            v24 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          v20 = *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
          v9 = *(_QWORD *)_RBP;
          v88 = v24++;
          v25 -= *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8C + 4 * v88);
          if ( v24 >= *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x66C) )
            v24 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664) = v24;
        }
        ++v21;
        v20 += **(int **)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        result = 0;
        *(_QWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v20;
      }
      while ( v21 < *(_DWORD *)(((unsigned __int64)&v95 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) );
    }
  }
  __asm { vzeroupper }
  _R11 = &v96;
  __asm
  {
    vmovaps xmm6, xmmword ptr [r11-18h]
    vmovaps xmm7, xmmword ptr [r11-28h]
    vmovaps xmm8, xmmword ptr [r11-38h]
    vmovaps xmm9, xmmword ptr [r11-48h]
    vmovaps xmm10, xmmword ptr [r11-58h]
  }
  return result;
}

```

## disassembly

```asm
0x180096d90  mov     rax, rsp
0x180096d93  push    rbp
0x180096d94  push    rbx
0x180096d95  push    rsi
0x180096d96  push    rdi
0x180096d97  push    r12
0x180096d99  push    r13
0x180096d9b  push    r14
0x180096d9d  push    r15
0x180096d9f  sub     rsp, 738h
0x180096da6  vmovaps xmmword ptr [rax-58h], xmm6
0x180096dab  vmovaps xmmword ptr [rax-68h], xmm7
0x180096db0  vmovaps xmmword ptr [rax-78h], xmm8
0x180096db5  vmovaps xmmword ptr [rax-88h], xmm9
0x180096dbd  vmovaps xmmword ptr [rax-98h], xmm10
0x180096dc5  lea     rbp, [rsp+770h+var_720]
0x180096dca  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180096dce  mov     rax, cs:__security_cookie
0x180096dd5  xor     rax, rsp
0x180096dd8  mov     [rbp+720h+var_A0], rax
0x180096ddf  vmovups xmm0, xmmword ptr [r9]
0x180096de4  lea     rax, [rcx+8]
0x180096de8  mov     [rbp+720h+var_718], r8
0x180096dec  mov     [rsp+770h+var_748], rax
0x180096df1  mov     r14, rdx
0x180096df4  mov     edx, 2
0x180096df9  mov     [rbp+720h+var_720], rcx
0x180096dfd  mov     r12, rcx
0x180096e00  lea     rax, [rbp+720h+var_700]
0x180096e04  mov     r9, r8
0x180096e07  mov     [rsp+770h+var_750], rax
0x180096e0c  lea     rcx, [rbp+720h+var_6D0]
0x180096e10  lea     r8d, [rdx-1]
0x180096e14  vmovups xmmword ptr [rbp+720h+var_700], xmm0
0x180096e19  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180096e1e  mov     rbx, [r14]
0x180096e21  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x180096e25  mov     rsi, [rbp+720h+var_6C8]
0x180096e29  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x180096e2d  mov     rdx, rbx; unsigned __int8 *
0x180096e30  lea     rcx, [rbp+720h+var_6C0]; this
0x180096e34  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180096e39  mov     r15, [r14+8]
0x180096e3d  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x180096e41  add     rbx, rsi
0x180096e44  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x180096e48  mov     rdx, r15; unsigned __int8 *
0x180096e4b  mov     qword ptr [rbp+720h+var_6F0], rbx
0x180096e4f  lea     rcx, [rbp+720h+var_6C0]; this
0x180096e53  movzx   edi, al
0x180096e56  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180096e5b  test    al, al
0x180096e5d  jz      short loc_180096E69
0x180096e5f  test    dil, dil
0x180096e62  jz      short loc_180096E69
0x180096e64  mov     dil, 1
0x180096e67  jmp     short loc_180096E6C
0x180096e69  xor     dil, dil
0x180096e6c  mov     r14, [r14+10h]
0x180096e70  lea     rax, [r15+rsi]
0x180096e74  mov     rdx, r14; unsigned __int8 *
0x180096e77  mov     qword ptr [rbp+720h+var_6F0+8], rax
0x180096e7b  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x180096e7f  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x180096e83  lea     rcx, [rbp+720h+var_6C0]; this
0x180096e87  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180096e8c  test    al, al
0x180096e8e  jz      loc_18009717A
0x180096e94  test    dil, dil
0x180096e97  jz      loc_18009717A
0x180096e9d  lea     rax, [r14+rsi]
0x180096ea1  mov     dword ptr [rbp+720h+var_710], 2
0x180096ea8  mov     [rbp+720h+var_6E0], rax
0x180096eac  xor     eax, eax
0x180096eae  mov     r15d, eax
0x180096eb1  mov     [rbp+720h+var_700], rax
0x180096eb5  mov     r13d, eax
0x180096eb8  cmp     [rbp+720h+var_6D0], eax
0x180096ebb  jle     loc_18009717A
0x180096ec1  vmovsd  xmm9, [rbp+720h+var_6E0]
0x180096ec6  vmovups xmm10, [rbp+720h+var_6F0]
0x180096ecb  mov     esi, [rbp+720h+var_BC]
0x180096ed1  mov     r14d, [rbp+720h+var_6A0]
0x180096ed8  mov     edi, [rbp+720h+var_6CC]
0x180096edb  nop     dword ptr [rax+rax+00h]
0x180096ee0  inc     r14d
0x180096ee3  mov     [rbp+720h+var_6A0], r14d
0x180096eea  cmp     r14d, 1
0x180096eee  jnz     loc_18009715A
0x180096ef4  mov     ecx, [r12+28h]
0x180096ef9  mov     r11d, eax
0x180096efc  mov     r10d, [r12+1Ch]
0x180096f01  mov     eax, [rbp+720h+var_69C]
0x180096f07  test    eax, eax
0x180096f09  movsxd  r8, dword ptr [r12+34h]
0x180096f0e  cmovle  r11d, eax
0x180096f12  mov     eax, [r12+2Ch]
0x180096f17  cmp     r10d, eax
0x180096f1a  vmovups [rbp+720h+var_6F0], xmm10
0x180096f1f  cmovl   r10d, eax
0x180096f23  lea     r9d, [r8-1]
0x180096f27  sub     r10d, eax
0x180096f2a  mov     eax, [rbp+720h+var_698]
0x180096f30  cmp     eax, ecx
0x180096f32  vmovsd  [rbp+720h+var_6E0], xmm9
0x180096f37  cmovl   eax, ecx
0x180096f3a  sub     eax, ecx
0x180096f3c  cdq
0x180096f3d  idiv    dword ptr [r12+30h]
0x180096f42  movsxd  rcx, edx
0x180096f45  imul    rcx, r8
0x180096f49  cmp     r10d, r9d
0x180096f4c  cmovle  r9d, r10d
0x180096f50  lea     r10, [rbx+r15]
0x180096f54  movsxd  rax, r9d
0x180096f57  neg     r11d
0x180096f5a  movsxd  r9, [rbp+720h+var_A4]
0x180096f61  add     rcx, rax
0x180096f64  mov     rax, [r12+38h]
0x180096f69  mov     r12, qword ptr [rbp+720h+var_6F0+8]
0x180096f6d  add     r12, r15
0x180096f70  add     r15, [rbp+720h+var_6E0]
0x180096f74  lea     rax, [rax+rcx*2]
0x180096f78  cmp     r9, 1
0x180096f7c  jge     short loc_180096FCC
0x180096f7e  xchg    ax, ax
0x180096f80  cmp     r11d, edi
0x180096f83  jge     short loc_180096FBC
0x180096f85  movsxd  rdx, r11d
0x180096f88  movzx   ecx, byte ptr [rdx+r12]
0x180096f8d  movzx   r8d, byte ptr [r10+rdx]
0x180096f92  add     r8d, ecx
0x180096f95  movzx   ecx, byte ptr [rdx+r15]
0x180096f9a  add     r8d, ecx
0x180096f9d  imul    ecx, r8d, 55h ; 'U'
0x180096fa1  shr     ecx, 6
0x180096fa4  mov     [rax], cx
0x180096fa7  add     rax, 2
0x180096fab  mov     ecx, dword ptr [rbp+r9*4+720h+var_710]
0x180096fb0  inc     r9
0x180096fb3  add     r11d, ecx
0x180096fb6  cmp     r9, 1
0x180096fba  jl      short loc_180096F80
0x180096fbc  mov     esi, [rbp+720h+var_BC]
0x180096fc2  mov     r14d, [rbp+720h+var_6A0]
0x180096fc9  mov     edi, [rbp+720h+var_6CC]
0x180096fcc  lea     ecx, [rdi-1Fh]
0x180096fcf  movsxd  r8, r11d
0x180096fd2  movsxd  rdx, ecx
0x180096fd5  cmp     r8, rdx
0x180096fd8  jge     loc_1800970C7
0x180096fde  vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x180096fe6  sub     rdx, r8
0x180096fe9  lea     rsi, [r12+r8]
0x180096fed  dec     rdx
0x180096ff0  mov     r9, r10
0x180096ff3  shr     rdx, 5
0x180096ff7  sub     r9, r12
0x180096ffa  mov     rdi, r15
0x180096ffd  sub     rdi, r12
0x180097000  inc     rdx
0x180097003  mov     ecx, edx
0x180097005  shl     ecx, 5
0x180097008  add     r11d, ecx
0x18009700b  nop     dword ptr [rax+rax+00h]
0x180097010  vmovdqu ymm4, ymmword ptr [rdi+rsi]
0x180097015  vmovdqu ymm6, ymmword ptr [r9+rsi]
0x18009701b  vmovdqu ymm7, ymmword ptr [rsi]
0x18009701f  vpmovzxbw ymm0, xmm7
0x180097024  vpmovzxbw ymm2, xmm4
0x180097029  vpmovzxbw ymm1, xmm6
0x18009702e  vpaddw  ymm1, ymm0, ymm1
0x180097032  vpaddw  ymm2, ymm1, ymm2
0x180097036  vpmullw ymm3, ymm2, ymm8
0x18009703b  vpsrlw  ymm0, ymm3, 6
0x180097040  vpshuflw ymm1, ymm0, 0D8h
0x180097045  vpshufhw ymm5, ymm1, 0D8h
0x18009704a  vextracti128 xmm0, ymm4, 1
0x180097050  vpmovzxbw ymm4, xmm0
0x180097055  vextracti128 xmm0, ymm7, 1
0x18009705b  vpmovzxbw ymm2, xmm0
0x180097060  vextracti128 xmm1, ymm6, 1
0x180097066  vpmovzxbw ymm3, xmm1
0x18009706b  vpaddw  ymm1, ymm2, ymm3
0x18009706f  vpaddw  ymm3, ymm1, ymm4
0x180097073  vpmullw ymm0, ymm3, ymm8
0x180097078  vpsrlw  ymm2, ymm0, 6
0x18009707d  vpshuflw ymm1, ymm2, 0D8h
0x180097082  vpshufhw ymm3, ymm1, 0D8h
0x180097087  vpunpcklqdq ymm2, ymm5, ymm3
0x18009708b  vpunpckhqdq ymm0, ymm5, ymm3
0x18009708f  vpunpckhdq ymm1, ymm2, ymm0
0x180097093  vpunpckldq ymm0, ymm2, ymm0
0x180097097  vpunpcklqdq ymm1, ymm0, ymm1
0x18009709b  vpermq  ymm2, ymm1, 0D8h
0x1800970a1  vmovdqu ymmword ptr [rax], ymm2
0x1800970a5  add     rax, 20h ; ' '
0x1800970a9  lea     rsi, [rsi+20h]
0x1800970ad  sub     rdx, 1
0x1800970b1  jnz     loc_180097010
0x1800970b7  mov     esi, [rbp+720h+var_BC]
0x1800970bd  mov     r14d, [rbp+720h+var_6A0]
0x1800970c4  mov     edi, [rbp+720h+var_6CC]
0x1800970c7  cmp     r11d, edi
0x1800970ca  jge     short loc_18009712B
0x1800970cc  sub     edi, r11d
0x1800970cf  movsxd  r8, r11d
0x1800970d2  add     r8, r12
0x1800970d5  sub     r15, r12
0x1800970d8  sub     r10, r12
0x1800970db  lea     r9d, [rdi-1]
0x1800970df  shr     r9d, 1
0x1800970e2  inc     r9d
0x1800970e5  nop     word ptr [rax+rax+00000000h]
0x1800970f0  movzx   ecx, byte ptr [r8+r10]
0x1800970f5  lea     rax, [rax+2]
0x1800970f9  movzx   edx, byte ptr [r8+r15]
0x1800970fe  lea     r8, [r8+2]
0x180097102  add     edx, ecx
0x180097104  movzx   ecx, byte ptr [r8-2]
0x180097109  add     edx, ecx
0x18009710b  imul    ecx, edx, 55h ; 'U'
0x18009710e  shr     ecx, 6
0x180097111  mov     [rax-2], cx
0x180097115  sub     r9, 1
0x180097119  jnz     short loc_1800970F0
0x18009711b  mov     esi, [rbp+720h+var_BC]
0x180097121  mov     r14d, [rbp+720h+var_6A0]
0x180097128  mov     edi, [rbp+720h+var_6CC]
0x18009712b  mov     r15, [rbp+720h+var_700]
0x18009712f  mov     r12, [rbp+720h+var_720]
0x180097133  movsxd  rax, esi
0x180097136  inc     esi
0x180097138  sub     r14d, [rbp+rax*4+720h+var_694]
0x180097140  mov     eax, 0
0x180097145  cmp     esi, [rbp+720h+var_B4]
0x18009714b  cmovge  esi, eax
0x18009714e  inc     [rbp+720h+var_698]
0x180097154  mov     [rbp+720h+var_BC], esi
0x18009715a  mov     rax, [rbp+720h+var_718]
0x18009715e  inc     r13d
0x180097161  movsxd  rax, dword ptr [rax]
0x180097164  add     r15, rax
0x180097167  mov     eax, 0
0x18009716c  mov     [rbp+720h+var_700], r15
0x180097170  cmp     r13d, [rbp+720h+var_6D0]
0x180097174  jl      loc_180096EE0
0x18009717a  vzeroupper
0x18009717d  mov     rcx, [rbp+720h+var_A0]
0x180097184  xor     rcx, rsp; StackCookie
0x180097187  call    __security_check_cookie
0x18009718c  lea     r11, [rsp+770h+var_38]
0x180097194  vmovaps xmm6, xmmword ptr [r11-18h]
0x18009719a  vmovaps xmm7, xmmword ptr [r11-28h]
0x1800971a0  vmovaps xmm8, xmmword ptr [r11-38h]
0x1800971a6  vmovaps xmm9, xmmword ptr [r11-48h]
0x1800971ac  vmovaps xmm10, xmmword ptr [r11-58h]
0x1800971b2  mov     rsp, r11
0x1800971b5  pop     r15
0x1800971b7  pop     r14
0x1800971b9  pop     r13
0x1800971bb  pop     r12
0x1800971bd  pop     rdi
0x1800971be  pop     rsi
0x1800971bf  pop     rbx
0x1800971c0  pop     rbp
0x1800971c1  retn
```
