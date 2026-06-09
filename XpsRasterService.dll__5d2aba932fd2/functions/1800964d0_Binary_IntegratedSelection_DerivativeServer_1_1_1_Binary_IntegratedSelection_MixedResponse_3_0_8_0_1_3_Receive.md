# Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800964d0`
- end: `0x1800968d2`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$00$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$00$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$00$02@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1026`
- prototype: `bool __fastcall(__int64, unsigned __int8 **, __int64, __int64 _R9)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099bc0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x1800964d0`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<1,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1,3>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,1,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,1>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        __int64 a3,
        __int64 _R9)
{
  __int64 v9; // r12
  unsigned __int8 *v10; // rbx
  __int64 v11; // r14
  bool v12; // al
  unsigned __int8 *v13; // r15
  unsigned __int8 *v14; // rbx
  bool v15; // di
  bool v16; // di
  unsigned __int8 *v17; // rsi
  bool result; // al
  __int64 v20; // r15
  int v21; // r13d
  int v24; // edi
  int v25; // r14d
  int v26; // esi
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
  __int64 v72; // r15
  unsigned __int8 *v73; // r8
  unsigned __int8 *v74; // r10
  __int64 v75; // r9
  int v76; // ecx
  int v77; // edx
  __int64 v78; // rax
  __int64 v85; // [rsp+58h] [rbp+0h] BYREF
  char v86; // [rsp+740h] [rbp+6E8h] BYREF

  _RBP = (unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 8) = a3;
  *(_QWORD *)_RBP = a1;
  v9 = a1;
  __asm { vmovups xmmword ptr [rbp+720h+var_700], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 80,
    1,
    1,
    a3,
    ((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 32,
    a1 + 8);
  v10 = *a2;
  v11 = *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
  v12 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          *a2,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16));
  v13 = a2[1];
  v14 = &v10[v11];
  *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v14;
  v15 = v12;
  v16 = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
          (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
          v13,
          (unsigned __int8 **)(_RBP + 32),
          (unsigned __int8 **)(_RBP + 16))
     && v15;
  v17 = a2[2];
  *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = &v13[v11];
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)(_RBP + 96),
             v17,
             (unsigned __int8 **)(_RBP + 32),
             (unsigned __int8 **)(_RBP + 16));
  if ( result && v16 )
  {
    *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 1;
    *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = &v17[v11];
    result = 0;
    v20 = 0;
    *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v21 = 0;
    if ( *(int *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) > 0 )
    {
      __asm
      {
        vmovsd  xmm9, [rbp+720h+var_6E0]
        vmovups xmm10, [rbp+720h+var_6F0]
      }
      v24 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
      v25 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
      v26 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = ++v25;
        if ( v25 == 1 )
        {
          v27 = *(_DWORD *)(v9 + 40);
          v28 = 0;
          v29 = *(_DWORD *)(v9 + 28);
          v30 = *(int *)(v9 + 52);
          if ( *(int *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84) <= 0 )
            v28 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x84);
          v31 = *(_DWORD *)(v9 + 44);
          __asm { vmovups [rbp+720h+var_6F0], xmm10 }
          if ( v29 < v31 )
            v29 = v31;
          v32 = v30 - 1;
          v33 = v29 - v31;
          v34 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          __asm { vmovsd  [rbp+720h+var_6E0], xmm9 }
          if ( v34 < v27 )
            v34 = v27;
          v35 = v30 * ((v34 - v27) % *(_DWORD *)(v9 + 48));
          if ( v33 <= v32 )
            v32 = v33;
          v36 = &v14[v20];
          v37 = v32;
          v38 = -v28;
          v39 = *(int *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x67C);
          v40 = v37 + v35;
          v41 = *(_QWORD *)(v9 + 56);
          v42 = v20 + *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
          v43 = *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) + v20;
          _RAX = (_WORD *)(v41 + 2 * v40);
          if ( v39 < 1 )
          {
            do
            {
              if ( v38 >= v26 )
                break;
              *_RAX++ = (85
                       * (v36[v38] + *(unsigned __int8 *)(v43 + v38) + (unsigned int)*(unsigned __int8 *)(v42 + v38))) >> 6;
              v45 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * v39++);
              v38 += v45;
            }
            while ( v39 < 1 );
            v24 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          v46 = v26 - 31;
          if ( v38 < (__int64)(v26 - 31) )
          {
            __asm { vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055 }
            _R8 = v42 + v38;
            _RDI = &v36[-v42];
            _RSI = v43 - v42;
            v51 = ((unsigned __int64)(v46 - (__int64)v38 - 1) >> 5) + 1;
            v38 += 32 * v51;
            do
            {
              __asm
              {
                vmovdqu ymm4, ymmword ptr [rsi+r8]
                vmovdqu ymm6, ymmword ptr [rdi+r8]
                vmovdqu ymm7, ymmword ptr [r8]
                vpmovzxbw ymm0, xmm7
                vpmovzxbw ymm2, xmm4
                vpmovzxbw ymm1, xmm6
                vpaddw  ymm1, ymm0, ymm1
                vpaddw  ymm2, ymm1, ymm2
                vpmullw ymm3, ymm2, ymm8
                vextracti128 xmm0, ymm4, 1
                vpmovzxbw ymm4, xmm0
                vpsrlw  ymm5, ymm3, 6
                vextracti128 xmm1, ymm6, 1
                vextracti128 xmm0, ymm7, 1
                vpmovzxbw ymm2, xmm0
                vpmovzxbw ymm3, xmm1
                vpaddw  ymm1, ymm2, ymm3
                vmovdqu ymmword ptr [rax], ymm5
                vpaddw  ymm3, ymm1, ymm4
                vpmullw ymm0, ymm3, ymm8
                vpsrlw  ymm2, ymm0, 6
                vmovdqu ymmword ptr [rax+20h], ymm2
              }
              _RAX += 32;
              _R8 += 32;
              --v51;
            }
            while ( v51 );
            v24 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          if ( v38 < v26 )
          {
            v72 = v43 - v42;
            v73 = (unsigned __int8 *)(v42 + v38);
            v74 = &v36[-v42];
            v75 = (unsigned int)(v26 - v38);
            do
            {
              v76 = v74[(_QWORD)v73];
              ++_RAX;
              v77 = v73[v72];
              *(_RAX - 1) = (85 * ((unsigned int)*v73++ + v76 + v77)) >> 6;
              --v75;
            }
            while ( v75 );
            v24 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664);
            v25 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            v26 = *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x54);
          }
          v20 = *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
          v9 = *(_QWORD *)_RBP;
          v78 = v24++;
          v25 -= *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8C + 4 * v78);
          if ( v24 >= *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x66C) )
            v24 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x664) = v24;
        }
        ++v21;
        v20 += **(int **)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        result = 0;
        *(_QWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v20;
      }
      while ( v21 < *(_DWORD *)(((unsigned __int64)&v85 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) );
    }
  }
  __asm { vzeroupper }
  _R11 = &v86;
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
0x1800964d0  mov     rax, rsp
0x1800964d3  push    rbp
0x1800964d4  push    rbx
0x1800964d5  push    rsi
0x1800964d6  push    rdi
0x1800964d7  push    r12
0x1800964d9  push    r13
0x1800964db  push    r14
0x1800964dd  push    r15
0x1800964df  sub     rsp, 738h
0x1800964e6  vmovaps xmmword ptr [rax-58h], xmm6
0x1800964eb  vmovaps xmmword ptr [rax-68h], xmm7
0x1800964f0  vmovaps xmmword ptr [rax-78h], xmm8
0x1800964f5  vmovaps xmmword ptr [rax-88h], xmm9
0x1800964fd  vmovaps xmmword ptr [rax-98h], xmm10
0x180096505  lea     rbp, [rsp+770h+var_720]
0x18009650a  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18009650e  mov     rax, cs:__security_cookie
0x180096515  xor     rax, rsp
0x180096518  mov     [rbp+720h+var_A0], rax
0x18009651f  vmovups xmm0, xmmword ptr [r9]
0x180096524  lea     rax, [rcx+8]
0x180096528  mov     [rbp+720h+var_718], r8
0x18009652c  mov     [rsp+770h+var_748], rax
0x180096531  mov     rsi, rdx
0x180096534  mov     edx, 1
0x180096539  mov     [rbp+720h+var_720], rcx
0x18009653d  lea     rax, [rbp+720h+var_700]
0x180096541  mov     r12, rcx
0x180096544  mov     r9, r8
0x180096547  mov     [rsp+770h+var_750], rax
0x18009654c  mov     r8d, edx
0x18009654f  lea     rcx, [rbp+720h+var_6D0]
0x180096553  vmovups xmmword ptr [rbp+720h+var_700], xmm0
0x180096558  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009655d  mov     rbx, [rsi]
0x180096560  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x180096564  mov     r14, [rbp+720h+var_6C8]
0x180096568  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x18009656c  mov     rdx, rbx; unsigned __int8 *
0x18009656f  lea     rcx, [rbp+720h+var_6C0]; this
0x180096573  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180096578  mov     r15, [rsi+8]
0x18009657c  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x180096580  add     rbx, r14
0x180096583  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x180096587  mov     rdx, r15; unsigned __int8 *
0x18009658a  mov     qword ptr [rbp+720h+var_6F0], rbx
0x18009658e  lea     rcx, [rbp+720h+var_6C0]; this
0x180096592  movzx   edi, al
0x180096595  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009659a  test    al, al
0x18009659c  jz      short loc_1800965A8
0x18009659e  test    dil, dil
0x1800965a1  jz      short loc_1800965A8
0x1800965a3  mov     dil, 1
0x1800965a6  jmp     short loc_1800965AB
0x1800965a8  xor     dil, dil
0x1800965ab  mov     rsi, [rsi+10h]
0x1800965af  lea     rax, [r15+r14]
0x1800965b3  mov     rdx, rsi; unsigned __int8 *
0x1800965b6  mov     qword ptr [rbp+720h+var_6F0+8], rax
0x1800965ba  lea     r9, [rbp+720h+var_710]; unsigned __int8 **
0x1800965be  lea     r8, [rbp+720h+var_700]; unsigned __int8 **
0x1800965c2  lea     rcx, [rbp+720h+var_6C0]; this
0x1800965c6  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800965cb  test    al, al
0x1800965cd  jz      loc_18009688A
0x1800965d3  test    dil, dil
0x1800965d6  jz      loc_18009688A
0x1800965dc  lea     rax, [rsi+r14]
0x1800965e0  mov     dword ptr [rbp+720h+var_710], 1
0x1800965e7  mov     [rbp+720h+var_6E0], rax
0x1800965eb  xor     eax, eax
0x1800965ed  mov     r15d, eax
0x1800965f0  mov     [rbp+720h+var_700], rax
0x1800965f4  mov     r13d, eax
0x1800965f7  cmp     [rbp+720h+var_6D0], eax
0x1800965fa  jle     loc_18009688A
0x180096600  vmovsd  xmm9, [rbp+720h+var_6E0]
0x180096605  vmovups xmm10, [rbp+720h+var_6F0]
0x18009660a  mov     edi, [rbp+720h+var_BC]
0x180096610  mov     r14d, [rbp+720h+var_6A0]
0x180096617  mov     esi, [rbp+720h+var_6CC]
0x18009661a  nop     word ptr [rax+rax+00h]
0x180096620  inc     r14d
0x180096623  mov     [rbp+720h+var_6A0], r14d
0x18009662a  cmp     r14d, 1
0x18009662e  jnz     loc_18009686A
0x180096634  mov     ecx, [r12+28h]
0x180096639  mov     r11d, eax
0x18009663c  mov     r10d, [r12+1Ch]
0x180096641  mov     eax, [rbp+720h+var_69C]
0x180096647  test    eax, eax
0x180096649  movsxd  r8, dword ptr [r12+34h]
0x18009664e  cmovle  r11d, eax
0x180096652  mov     eax, [r12+2Ch]
0x180096657  cmp     r10d, eax
0x18009665a  vmovups [rbp+720h+var_6F0], xmm10
0x18009665f  cmovl   r10d, eax
0x180096663  lea     r9d, [r8-1]
0x180096667  sub     r10d, eax
0x18009666a  mov     eax, [rbp+720h+var_698]
0x180096670  cmp     eax, ecx
0x180096672  vmovsd  [rbp+720h+var_6E0], xmm9
0x180096677  cmovl   eax, ecx
0x18009667a  sub     eax, ecx
0x18009667c  cdq
0x18009667d  idiv    dword ptr [r12+30h]
0x180096682  movsxd  rcx, edx
0x180096685  imul    rcx, r8
0x180096689  cmp     r10d, r9d
0x18009668c  cmovle  r9d, r10d
0x180096690  lea     r10, [rbx+r15]
0x180096694  movsxd  rax, r9d
0x180096697  neg     r11d
0x18009669a  movsxd  r9, [rbp+720h+var_A4]
0x1800966a1  add     rcx, rax
0x1800966a4  mov     rax, [r12+38h]
0x1800966a9  mov     r12, qword ptr [rbp+720h+var_6F0+8]
0x1800966ad  add     r12, r15
0x1800966b0  add     r15, [rbp+720h+var_6E0]
0x1800966b4  lea     rax, [rax+rcx*2]
0x1800966b8  cmp     r9, 1
0x1800966bc  jge     short loc_18009670C
0x1800966be  xchg    ax, ax
0x1800966c0  cmp     r11d, esi
0x1800966c3  jge     short loc_1800966FC
0x1800966c5  movsxd  rdx, r11d
0x1800966c8  movzx   ecx, byte ptr [r15+rdx]
0x1800966cd  movzx   r8d, byte ptr [r12+rdx]
0x1800966d2  add     r8d, ecx
0x1800966d5  movzx   ecx, byte ptr [r10+rdx]
0x1800966da  add     r8d, ecx
0x1800966dd  imul    ecx, r8d, 55h ; 'U'
0x1800966e1  shr     ecx, 6
0x1800966e4  mov     [rax], cx
0x1800966e7  add     rax, 2
0x1800966eb  mov     ecx, dword ptr [rbp+r9*4+720h+var_710]
0x1800966f0  inc     r9
0x1800966f3  add     r11d, ecx
0x1800966f6  cmp     r9, 1
0x1800966fa  jl      short loc_1800966C0
0x1800966fc  mov     edi, [rbp+720h+var_BC]
0x180096702  mov     r14d, [rbp+720h+var_6A0]
0x180096709  mov     esi, [rbp+720h+var_6CC]
0x18009670c  lea     ecx, [rsi-1Fh]
0x18009670f  movsxd  r9, r11d
0x180096712  movsxd  rdx, ecx
0x180096715  cmp     r9, rdx
0x180096718  jge     loc_1800967DC
0x18009671e  vmovdqu ymm8, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x180096726  sub     rdx, r9
0x180096729  lea     r8, [r12+r9]
0x18009672d  dec     rdx
0x180096730  mov     rdi, r10
0x180096733  shr     rdx, 5
0x180096737  sub     rdi, r12
0x18009673a  mov     rsi, r15
0x18009673d  sub     rsi, r12
0x180096740  inc     rdx
0x180096743  mov     ecx, edx
0x180096745  shl     ecx, 5
0x180096748  add     r11d, ecx
0x18009674b  nop     dword ptr [rax+rax+00h]
0x180096750  vmovdqu ymm4, ymmword ptr [rsi+r8]
0x180096756  vmovdqu ymm6, ymmword ptr [rdi+r8]
0x18009675c  vmovdqu ymm7, ymmword ptr [r8]
0x180096761  vpmovzxbw ymm0, xmm7
0x180096766  vpmovzxbw ymm2, xmm4
0x18009676b  vpmovzxbw ymm1, xmm6
0x180096770  vpaddw  ymm1, ymm0, ymm1
0x180096774  vpaddw  ymm2, ymm1, ymm2
0x180096778  vpmullw ymm3, ymm2, ymm8
0x18009677d  vextracti128 xmm0, ymm4, 1
0x180096783  vpmovzxbw ymm4, xmm0
0x180096788  vpsrlw  ymm5, ymm3, 6
0x18009678d  vextracti128 xmm1, ymm6, 1
0x180096793  vextracti128 xmm0, ymm7, 1
0x180096799  vpmovzxbw ymm2, xmm0
0x18009679e  vpmovzxbw ymm3, xmm1
0x1800967a3  vpaddw  ymm1, ymm2, ymm3
0x1800967a7  vmovdqu ymmword ptr [rax], ymm5
0x1800967ab  vpaddw  ymm3, ymm1, ymm4
0x1800967af  vpmullw ymm0, ymm3, ymm8
0x1800967b4  vpsrlw  ymm2, ymm0, 6
0x1800967b9  vmovdqu ymmword ptr [rax+20h], ymm2
0x1800967be  add     rax, 40h ; '@'
0x1800967c2  lea     r8, [r8+20h]
0x1800967c6  sub     rdx, 1
0x1800967ca  jnz     short loc_180096750
0x1800967cc  mov     edi, [rbp+720h+var_BC]
0x1800967d2  mov     r14d, [rbp+720h+var_6A0]
0x1800967d9  mov     esi, [rbp+720h+var_6CC]
0x1800967dc  cmp     r11d, esi
0x1800967df  jge     short loc_18009683B
0x1800967e1  movsxd  r8, r11d
0x1800967e4  sub     r15, r12
0x1800967e7  add     r8, r12
0x1800967ea  sub     r10, r12
0x1800967ed  sub     esi, r11d
0x1800967f0  mov     r9d, esi
0x1800967f3  nop     dword ptr [rax+00h]
0x1800967f7  nop     word ptr [rax+rax+00000000h]
0x180096800  movzx   ecx, byte ptr [r8+r10]
0x180096805  lea     rax, [rax+2]
0x180096809  movzx   edx, byte ptr [r8+r15]
0x18009680e  lea     r8, [r8+1]
0x180096812  add     edx, ecx
0x180096814  movzx   ecx, byte ptr [r8-1]
0x180096819  add     edx, ecx
0x18009681b  imul    ecx, edx, 55h ; 'U'
0x18009681e  shr     ecx, 6
0x180096821  mov     [rax-2], cx
0x180096825  sub     r9, 1
0x180096829  jnz     short loc_180096800
0x18009682b  mov     edi, [rbp+720h+var_BC]
0x180096831  mov     r14d, [rbp+720h+var_6A0]
0x180096838  mov     esi, [rbp+720h+var_6CC]
0x18009683b  mov     r15, [rbp+720h+var_700]
0x18009683f  mov     r12, [rbp+720h+var_720]
0x180096843  movsxd  rax, edi
0x180096846  inc     edi
0x180096848  sub     r14d, [rbp+rax*4+720h+var_694]
0x180096850  mov     eax, 0
0x180096855  cmp     edi, [rbp+720h+var_B4]
0x18009685b  cmovge  edi, eax
0x18009685e  inc     [rbp+720h+var_698]
0x180096864  mov     [rbp+720h+var_BC], edi
0x18009686a  mov     rax, [rbp+720h+var_718]
0x18009686e  inc     r13d
0x180096871  movsxd  rax, dword ptr [rax]
0x180096874  add     r15, rax
0x180096877  mov     eax, 0
0x18009687c  mov     [rbp+720h+var_700], r15
0x180096880  cmp     r13d, [rbp+720h+var_6D0]
0x180096884  jl      loc_180096620
0x18009688a  vzeroupper
0x18009688d  mov     rcx, [rbp+720h+var_A0]
0x180096894  xor     rcx, rsp; StackCookie
0x180096897  call    __security_check_cookie
0x18009689c  lea     r11, [rsp+770h+var_38]
0x1800968a4  vmovaps xmm6, xmmword ptr [r11-18h]
0x1800968aa  vmovaps xmm7, xmmword ptr [r11-28h]
0x1800968b0  vmovaps xmm8, xmmword ptr [r11-38h]
0x1800968b6  vmovaps xmm9, xmmword ptr [r11-48h]
0x1800968bc  vmovaps xmm10, xmmword ptr [r11-58h]
0x1800968c2  mov     rsp, r11
0x1800968c5  pop     r15
0x1800968c7  pop     r14
0x1800968c9  pop     r13
0x1800968cb  pop     r12
0x1800968cd  pop     rdi
0x1800968ce  pop     rsi
0x1800968cf  pop     rbx
0x1800968d0  pop     rbp
0x1800968d1  retn
```
