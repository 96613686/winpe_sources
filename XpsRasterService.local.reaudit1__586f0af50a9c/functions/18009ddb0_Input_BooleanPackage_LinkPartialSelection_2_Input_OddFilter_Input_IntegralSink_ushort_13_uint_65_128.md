# Input::BooleanPackage::LinkPartialSelection<2>(Input::OddFilter<Input::IntegralSink<ushort,13,uint>,65,128> &)

- ea: `0x18009ddb0`
- end: `0x18009e44f`
- name: `??$LinkPartialSelection@$01@BooleanPackage@Input@@QEAAAEAV?$OddFilter@V?$IntegralSink@G$0M@I@Input@@$0EB@$0EA@@1@AEAV?$OddFilter@V?$IntegralSink@G$0N@I@Input@@$0EB@$0IA@@1@@Z`
- size: `1695`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009e460`

## callees

- `0x180003180`
- `0x180091f80`
- `0x18009ddb0`

## pseudocode

```c
_QWORD *__fastcall Input::BooleanPackage::LinkPartialSelection<2>(__int64 a1, __int64 *a2)
{
  __int64 v2; // r13
  __int64 v3; // r9
  __int64 v4; // r8
  int v5; // esi
  __int64 *v6; // r10
  _QWORD *v7; // r15
  __int64 v8; // r14
  __int64 v9; // rbx
  __int64 v10; // r12
  __int64 v11; // rdi
  __int64 v12; // rax
  __m128i v13; // xmm1
  __m128i v14; // xmm0
  __m128i v15; // xmm1
  union __m128i v16; // xmm0
  __m128i v17; // xmm1
  __int64 v18; // rdx
  __m128i v19; // xmm1
  bool v20; // zf
  __int64 v21; // rbx
  int v22; // r11d
  int v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  union __m128i v38; // [rsp+B0h] [rbp-50h] BYREF
  union __m128i v39; // [rsp+C0h] [rbp-40h] BYREF
  union __m128i v40; // [rsp+D0h] [rbp-30h] BYREF
  union __m128i v41; // [rsp+E0h] [rbp-20h] BYREF
  union __m128i v42; // [rsp+F0h] [rbp-10h] BYREF
  union __m128i v43; // [rsp+100h] [rbp+0h] BYREF
  union __m128i v44; // [rsp+110h] [rbp+10h] BYREF
  union __m128i v45; // [rsp+120h] [rbp+20h] BYREF

  v2 = 256;
  v3 = 1166;
  v24 = 256;
  v4 = 626;
  v25 = 1166;
  v5 = 256;
  v27 = 626;
  v6 = a2;
  v26 = -256;
  v7 = (_QWORD *)(a1 + 8320);
  do
  {
    v8 = v2;
    v29 = 8;
    v9 = v4;
    v10 = *v6 + 2 * (v5 - 256 + 64LL);
    v30 = v10;
    v31 = *v6 + 2 * (v5 - 128 + 64LL);
    v32 = *v6 + 2 * (v5 + 64LL);
    v33 = *v6 + 2 * (v5 + 128 + 64LL);
    v34 = *v6 + 2 * (v5 + 256 + 64LL);
    v35 = *v6 + 2 * (v5 + 384 + 64LL);
    v36 = *v6 + 2 * (v5 + 512 + 64LL);
    v11 = 0;
    v37 = *v6 + 2 * (v5 + 640 + 64LL);
    while ( 1 )
    {
      v12 = *v6;
      v13 = _mm_loadu_si128((const __m128i *)(v9 + *v6 - 256));
      v38 = _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v9 + *v6 - 512)), 1u);
      v40 = _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v9 + v12)), 1u);
      v14 = _mm_loadu_si128((const __m128i *)(v9 + v12 + 512));
      v39 = _mm_srli_epi16(v13, 1u);
      v15 = _mm_loadu_si128((const __m128i *)(v9 + v12 + 256));
      v42 = _mm_srli_epi16(v14, 1u);
      v16 = _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v9 + v12 + 1024)), 1u);
      v41 = _mm_srli_epi16(v15, 1u);
      v17 = _mm_loadu_si128((const __m128i *)(v9 + v12 + 768));
      v44 = v16;
      v43 = _mm_srli_epi16(v17, 1u);
      v45 = _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v4 + v9 + v12 + v3 - 512)), 1u);
      TreatCoordinatedPackage(&v38, &v39, &v40, &v41, &v42, &v43, &v44, &v45);
      v18 = v8 + v26;
      *(__m128i *)(v2 + *v7 + v18 - 256) = _mm_adds_epu16(
                                             _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v10 + v11)), 1u),
                                             v45);
      *(__m128i *)(*v7 + v8 - 128) = _mm_adds_epu16(
                                       _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v31 + v11)), 1u),
                                       v44);
      *(__m128i *)(v8 + *v7) = _mm_adds_epu16(_mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v32 + v11)), 1u), v43);
      *(__m128i *)(*v7 + v8 + 128) = _mm_adds_epu16(
                                       _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v33 + v11)), 1u),
                                       v42);
      *(__m128i *)(*v7 + v8 + 256) = _mm_adds_epu16(
                                       _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v34 + v11)), 1u),
                                       v41);
      *(__m128i *)(*v7 + v8 + 384) = _mm_adds_epu16(
                                       _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v35 + v11)), 1u),
                                       v40);
      v19 = _mm_adds_epu16(_mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v36 + v11)), 1u), v39);
      v8 += 16;
      v4 = v27;
      v11 += 16;
      v3 = v25;
      v9 += 2048;
      v6 = a2;
      *(__m128i *)(*v7 + v8 + 496) = v19;
      v20 = v29-- == 1;
      *(__m128i *)(v18 + *v7 + v2 + 640) = _mm_adds_epu16(
                                             _mm_srli_epi16(_mm_loadu_si128((const __m128i *)(v37 + v11 - 16)), 1u),
                                             v38);
      if ( v20 )
        break;
      v10 = v30;
    }
    v3 = v25 + 16;
    v5 = v24 + 1024;
    v24 += 1024;
    v4 = v27 - 16;
    v25 += 16;
    v2 += 1024;
    v26 -= 1024;
    v27 -= 16;
  }
  while ( v26 > -8448 );
  v21 = 768;
  v22 = 65;
  do
  {
    *(_WORD *)(*v7 + 2LL * v22 + 8062) = (*(_WORD *)(v21 + *a2 - 768) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16382) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8064) = (*(_WORD *)(v21 + *a2 - 512) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 0x4000) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8066) = (*(_WORD *)(*a2 + v21 - 256) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16386) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8068) = (*(_WORD *)(*a2 + v21) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16388) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8070) = (*(_WORD *)(*a2 + v21 + 256) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16390) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8072) = (*(_WORD *)(*a2 + v21 + 512) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16392) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8074) = (*(_WORD *)(*a2 + v21 + 768) >> 1) + (*(_WORD *)(*a2 + 2LL * v22 + 16394) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8076) = (*(_WORD *)(*a2 + v21 + 1024) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16396) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8078) = (*(_WORD *)(*a2 + v21 + 1280) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16398) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8080) = (*(_WORD *)(*a2 + v21 + 1536) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16400) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8082) = (*(_WORD *)(*a2 + v21 + 1792) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16402) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8084) = (*(_WORD *)(*a2 + v21 + 2048) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16404) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8086) = (*(_WORD *)(*a2 + v21 + 2304) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16406) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8088) = (*(_WORD *)(*a2 + v21 + 2560) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16408) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8090) = (*(_WORD *)(*a2 + v21 + 2816) >> 1)
                                       + (*(_WORD *)(*a2 + 2LL * v22 + 16410) >> 1);
    *(_WORD *)(*v7 + 2LL * v22 + 8092) = (*(_WORD *)(*a2 + 2LL * v22 + 16412) >> 1)
                                       + (*(_WORD *)(*a2 + v21 + 3072) >> 1);
    v22 += 16;
    v21 += 4096;
  }
  while ( v22 - 65 < 64 );
  return v7;
}

```

## disassembly

```asm
0x18009ddb0  mov     [rsp-8+arg_0], rbx
0x18009ddb5  mov     [rsp-8+arg_8], rsi
0x18009ddba  mov     [rsp-8+arg_10], rdi
0x18009ddbf  push    rbp
0x18009ddc0  push    r12
0x18009ddc2  push    r13
0x18009ddc4  push    r14
0x18009ddc6  push    r15
0x18009ddc8  lea     rbp, [rsp-40h]
0x18009ddcd  sub     rsp, 140h
0x18009ddd4  mov     rax, cs:__security_cookie
0x18009dddb  xor     rax, rsp
0x18009ddde  mov     [rbp+60h+var_30], rax
0x18009dde2  mov     r13d, 100h
0x18009dde8  mov     [rsp+160h+var_100], rdx
0x18009dded  mov     r9d, 48Eh
0x18009ddf3  mov     [rsp+160h+var_120], r13d
0x18009ddf8  mov     r8d, 272h
0x18009ddfe  mov     [rsp+160h+var_118], r9
0x18009de03  mov     esi, r13d
0x18009de06  mov     [rsp+160h+var_108], r8
0x18009de0b  mov     r10, rdx
0x18009de0e  mov     [rsp+160h+var_110], 0FFFFFFFFFFFFFF00h
0x18009de17  lea     r15, [rcx+2080h]
0x18009de1e  xchg    ax, ax
0x18009de20  mov     rdx, [r10]
0x18009de23  lea     eax, [rsi-100h]
0x18009de29  movsxd  rcx, eax
0x18009de2c  mov     r14, r13
0x18009de2f  add     rcx, 40h ; '@'
0x18009de33  mov     [rsp+160h+var_F8], 8
0x18009de3c  lea     eax, [rsi-80h]
0x18009de3f  mov     rbx, r8
0x18009de42  lea     r12, [rdx+rcx*2]
0x18009de46  movsxd  rcx, eax
0x18009de49  add     rcx, 40h ; '@'
0x18009de4d  mov     [rsp+160h+var_F0], r12
0x18009de52  lea     rax, [rdx+rcx*2]
0x18009de56  movsxd  rcx, esi
0x18009de59  mov     [rsp+160h+var_E8], rax
0x18009de5e  add     rcx, 40h ; '@'
0x18009de62  lea     eax, [rsi+80h]
0x18009de68  cdqe
0x18009de6a  add     rax, 40h ; '@'
0x18009de6e  lea     rcx, [rdx+rcx*2]
0x18009de72  mov     [rbp+60h+var_E0], rcx
0x18009de76  lea     rax, [rdx+rax*2]
0x18009de7a  mov     [rbp+60h+var_D8], rax
0x18009de7e  lea     eax, [rsi+100h]
0x18009de84  cdqe
0x18009de86  add     rax, 40h ; '@'
0x18009de8a  lea     rax, [rdx+rax*2]
0x18009de8e  mov     [rbp+60h+var_D0], rax
0x18009de92  lea     eax, [rsi+180h]
0x18009de98  cdqe
0x18009de9a  add     rax, 40h ; '@'
0x18009de9e  lea     rax, [rdx+rax*2]
0x18009dea2  mov     [rbp+60h+var_C8], rax
0x18009dea6  lea     eax, [rsi+200h]
0x18009deac  cdqe
0x18009deae  add     rax, 40h ; '@'
0x18009deb2  lea     rax, [rdx+rax*2]
0x18009deb6  mov     [rbp+60h+var_C0], rax
0x18009deba  lea     eax, [rsi+280h]
0x18009dec0  mov     rsi, [rsp+160h+var_110]
0x18009dec5  cdqe
0x18009dec7  add     rax, 40h ; '@'
0x18009decb  xor     edi, edi
0x18009decd  lea     rax, [rdx+rax*2]
0x18009ded1  mov     [rbp+60h+var_B8], rax
0x18009ded5  mov     rax, [r10]
0x18009ded8  lea     rdx, [rbp+60h+var_A0]; union __m128i *
0x18009dedc  lea     rcx, [rbp+60h+var_B0]; union __m128i *
0x18009dee0  movdqu  xmm0, xmmword ptr [rbx+rax-200h]
0x18009dee9  movdqu  xmm1, xmmword ptr [rbx+rax-100h]
0x18009def2  psrlw   xmm0, 1
0x18009def7  movdqa  [rbp+60h+var_B0], xmm0
0x18009defc  movdqu  xmm0, xmmword ptr [rbx+rax]
0x18009df01  psrlw   xmm1, 1
0x18009df06  psrlw   xmm0, 1
0x18009df0b  movdqa  [rbp+60h+var_90], xmm0
0x18009df10  movdqu  xmm0, xmmword ptr [rbx+rax+200h]
0x18009df19  movdqa  [rbp+60h+var_A0], xmm1
0x18009df1e  movdqu  xmm1, xmmword ptr [rbx+rax+100h]
0x18009df27  psrlw   xmm0, 1
0x18009df2c  movdqa  [rbp+60h+var_70], xmm0
0x18009df31  movdqu  xmm0, xmmword ptr [rbx+rax+400h]
0x18009df3a  psrlw   xmm1, 1
0x18009df3f  psrlw   xmm0, 1
0x18009df44  movdqa  [rbp+60h+var_80], xmm1
0x18009df49  movdqu  xmm1, xmmword ptr [rbx+rax+300h]
0x18009df52  add     rax, rbx
0x18009df55  add     rax, r8
0x18009df58  movdqa  [rbp+60h+var_50], xmm0
0x18009df5d  psrlw   xmm1, 1
0x18009df62  lea     r8, [rbp+60h+var_90]; union __m128i *
0x18009df66  movdqa  [rbp+60h+var_60], xmm1
0x18009df6b  movdqu  xmm0, xmmword ptr [rax+r9-200h]
0x18009df75  lea     rax, [rbp+60h+var_40]
0x18009df79  mov     [rsp+160h+var_128], rax; union __m128i *
0x18009df7e  lea     r9, [rbp+60h+var_80]; union __m128i *
0x18009df82  lea     rax, [rbp+60h+var_50]
0x18009df86  psrlw   xmm0, 1
0x18009df8b  mov     [rsp+160h+var_130], rax; union __m128i *
0x18009df90  lea     rax, [rbp+60h+var_60]
0x18009df94  mov     [rsp+160h+var_138], rax; union __m128i *
0x18009df99  lea     rax, [rbp+60h+var_70]
0x18009df9d  mov     [rsp+160h+var_140], rax; union __m128i *
0x18009dfa2  movdqa  [rbp+60h+var_40], xmm0
0x18009dfa7  call    ?TreatCoordinatedPackage@@YAXAEAT__m128i@@0000000@Z; TreatCoordinatedPackage(__m128i &,__m128i &,__m128i &,__m128i &,__m128i &,__m128i &,__m128i &,__m128i &)
0x18009dfac  movdqu  xmm0, xmmword ptr [r12+rdi]
0x18009dfb2  mov     rcx, [r15]
0x18009dfb5  lea     rdx, [r14+rsi]
0x18009dfb9  add     rcx, r13
0x18009dfbc  psrlw   xmm0, 1
0x18009dfc1  paddusw xmm0, [rbp+60h+var_40]
0x18009dfc6  movdqu  xmmword ptr [rcx+rdx-100h], xmm0
0x18009dfcf  mov     rax, [rsp+160h+var_E8]
0x18009dfd4  movdqu  xmm0, xmmword ptr [rax+rdi]
0x18009dfd9  mov     rax, [r15]
0x18009dfdc  psrlw   xmm0, 1
0x18009dfe1  paddusw xmm0, [rbp+60h+var_50]
0x18009dfe6  movdqu  xmmword ptr [rax+r14-80h], xmm0
0x18009dfed  mov     rax, [rbp+60h+var_E0]
0x18009dff1  movdqu  xmm1, xmmword ptr [rax+rdi]
0x18009dff6  mov     rax, [r15]
0x18009dff9  psrlw   xmm1, 1
0x18009dffe  paddusw xmm1, [rbp+60h+var_60]
0x18009e003  movdqu  xmmword ptr [r14+rax], xmm1
0x18009e009  mov     rax, [rbp+60h+var_D8]
0x18009e00d  movdqu  xmm0, xmmword ptr [rax+rdi]
0x18009e012  mov     rax, [r15]
0x18009e015  psrlw   xmm0, 1
0x18009e01a  paddusw xmm0, [rbp+60h+var_70]
0x18009e01f  movdqu  xmmword ptr [rax+r14+80h], xmm0
0x18009e029  mov     rax, [rbp+60h+var_D0]
0x18009e02d  movdqu  xmm1, xmmword ptr [rax+rdi]
0x18009e032  mov     rax, [r15]
0x18009e035  psrlw   xmm1, 1
0x18009e03a  paddusw xmm1, [rbp+60h+var_80]
0x18009e03f  movdqu  xmmword ptr [rax+r14+100h], xmm1
0x18009e049  mov     rax, [rbp+60h+var_C8]
0x18009e04d  movdqu  xmm0, xmmword ptr [rax+rdi]
0x18009e052  mov     rax, [r15]
0x18009e055  psrlw   xmm0, 1
0x18009e05a  paddusw xmm0, [rbp+60h+var_90]
0x18009e05f  movdqu  xmmword ptr [rax+r14+180h], xmm0
0x18009e069  mov     rax, [rbp+60h+var_C0]
0x18009e06d  movdqu  xmm1, xmmword ptr [rax+rdi]
0x18009e072  psrlw   xmm1, 1
0x18009e077  paddusw xmm1, [rbp+60h+var_A0]
0x18009e07c  mov     rax, [r15]
0x18009e07f  lea     r14, [r14+10h]
0x18009e083  mov     r8, [rsp+160h+var_108]
0x18009e088  lea     rdi, [rdi+10h]
0x18009e08c  mov     r9, [rsp+160h+var_118]
0x18009e091  add     rbx, 800h
0x18009e098  mov     r10, [rsp+160h+var_100]
0x18009e09d  movdqu  xmmword ptr [rax+r14+1F0h], xmm1
0x18009e0a7  mov     rcx, [rbp+60h+var_B8]
0x18009e0ab  mov     rax, [r15]
0x18009e0ae  add     rax, rdx
0x18009e0b1  sub     [rsp+160h+var_F8], 1
0x18009e0b7  movdqu  xmm0, xmmword ptr [rcx+rdi-10h]
0x18009e0bd  psrlw   xmm0, 1
0x18009e0c2  paddusw xmm0, [rbp+60h+var_B0]
0x18009e0c7  movdqu  xmmword ptr [rax+r13+280h], xmm0
0x18009e0d1  jz      short loc_18009E0DD
0x18009e0d3  mov     r12, [rsp+160h+var_F0]
0x18009e0d8  jmp     loc_18009DED5
0x18009e0dd  mov     esi, [rsp+160h+var_120]
0x18009e0e1  add     r9, 10h
0x18009e0e5  mov     rax, [rsp+160h+var_110]
0x18009e0ea  add     esi, 400h
0x18009e0f0  sub     rax, 400h
0x18009e0f6  mov     [rsp+160h+var_120], esi
0x18009e0fa  sub     r8, 10h
0x18009e0fe  mov     [rsp+160h+var_118], r9
0x18009e103  add     r13, 400h
0x18009e10a  mov     [rsp+160h+var_110], rax
0x18009e10f  mov     [rsp+160h+var_108], r8
0x18009e114  cmp     rax, 0FFFFFFFFFFFFDF00h
0x18009e11a  jg      loc_18009DE20
0x18009e120  mov     ebx, 300h
0x18009e125  mov     r11d, 41h ; 'A'
0x18009e12b  nop     dword ptr [rax+rax+00h]
0x18009e130  mov     r8, [rsp+160h+var_100]
0x18009e135  movsxd  rax, r11d
0x18009e138  mov     rcx, [r8]
0x18009e13b  movzx   edx, word ptr [rcx+rax*2+3FFEh]
0x18009e143  movzx   eax, word ptr [rbx+rcx-300h]
0x18009e14b  shr     ax, 1
0x18009e14e  shr     dx, 1
0x18009e151  add     dx, ax
0x18009e154  movsxd  rcx, r11d
0x18009e157  mov     rax, [r15]
0x18009e15a  mov     [rax+rcx*2+1F7Eh], dx
0x18009e162  mov     rcx, [r8]
0x18009e165  movsxd  rax, r11d
0x18009e168  movzx   edx, word ptr [rcx+rax*2+4000h]
0x18009e170  movzx   eax, word ptr [rbx+rcx-200h]
0x18009e178  shr     ax, 1
0x18009e17b  shr     dx, 1
0x18009e17e  add     dx, ax
0x18009e181  movsxd  rcx, r11d
0x18009e184  mov     rax, [r15]
0x18009e187  mov     [rax+rcx*2+1F80h], dx
0x18009e18f  mov     rcx, [r8]
0x18009e192  movsxd  rax, r11d
0x18009e195  movzx   edx, word ptr [rcx+rax*2+4002h]
0x18009e19d  movzx   eax, word ptr [rcx+rbx-100h]
0x18009e1a5  shr     ax, 1
0x18009e1a8  shr     dx, 1
0x18009e1ab  add     dx, ax
0x18009e1ae  movsxd  rcx, r11d
0x18009e1b1  mov     rax, [r15]
0x18009e1b4  mov     [rax+rcx*2+1F82h], dx
0x18009e1bc  mov     rcx, [r8]
0x18009e1bf  movsxd  rax, r11d
0x18009e1c2  movzx   edx, word ptr [rcx+rax*2+4004h]
0x18009e1ca  movzx   eax, word ptr [rcx+rbx]
0x18009e1ce  shr     ax, 1
0x18009e1d1  shr     dx, 1
0x18009e1d4  add     dx, ax
0x18009e1d7  movsxd  rcx, r11d
0x18009e1da  mov     rax, [r15]
0x18009e1dd  mov     [rax+rcx*2+1F84h], dx
0x18009e1e5  mov     rcx, [r8]
0x18009e1e8  movsxd  rax, r11d
0x18009e1eb  movzx   edx, word ptr [rcx+rax*2+4006h]
0x18009e1f3  movzx   eax, word ptr [rcx+rbx+100h]
0x18009e1fb  shr     ax, 1
0x18009e1fe  shr     dx, 1
0x18009e201  add     dx, ax
0x18009e204  movsxd  rcx, r11d
0x18009e207  mov     rax, [r15]
0x18009e20a  mov     [rax+rcx*2+1F86h], dx
0x18009e212  mov     rcx, [r8]
0x18009e215  movsxd  rax, r11d
0x18009e218  movzx   edx, word ptr [rcx+rax*2+4008h]
0x18009e220  movzx   eax, word ptr [rcx+rbx+200h]
0x18009e228  shr     ax, 1
0x18009e22b  shr     dx, 1
0x18009e22e  add     dx, ax
0x18009e231  movsxd  rcx, r11d
0x18009e234  mov     rax, [r15]
0x18009e237  mov     [rax+rcx*2+1F88h], dx
0x18009e23f  mov     rcx, [r8]
0x18009e242  movsxd  rax, r11d
0x18009e245  movzx   edx, word ptr [rcx+rax*2+400Ah]
0x18009e24d  movzx   eax, word ptr [rcx+rbx+300h]
0x18009e255  shr     ax, 1
0x18009e258  shr     dx, 1
0x18009e25b  add     dx, ax
0x18009e25e  movsxd  rcx, r11d
0x18009e261  mov     rax, [r15]
0x18009e264  mov     [rax+rcx*2+1F8Ah], dx
0x18009e26c  mov     rcx, [r8]
0x18009e26f  movsxd  rax, r11d
0x18009e272  movzx   edx, word ptr [rcx+rax*2+400Ch]
0x18009e27a  movzx   eax, word ptr [rcx+rbx+400h]
0x18009e282  shr     ax, 1
0x18009e285  shr     dx, 1
0x18009e288  add     dx, ax
0x18009e28b  movsxd  rcx, r11d
0x18009e28e  mov     rax, [r15]
0x18009e291  mov     [rax+rcx*2+1F8Ch], dx
0x18009e299  mov     rcx, [r8]
0x18009e29c  movsxd  rax, r11d
0x18009e29f  movzx   edx, word ptr [rcx+rax*2+400Eh]
0x18009e2a7  movzx   eax, word ptr [rcx+rbx+500h]
0x18009e2af  shr     ax, 1
0x18009e2b2  shr     dx, 1
0x18009e2b5  add     dx, ax
0x18009e2b8  movsxd  rcx, r11d
0x18009e2bb  mov     rax, [r15]
0x18009e2be  mov     [rax+rcx*2+1F8Eh], dx
0x18009e2c6  mov     rcx, [r8]
0x18009e2c9  movsxd  rax, r11d
0x18009e2cc  movzx   edx, word ptr [rcx+rax*2+4010h]
0x18009e2d4  movzx   eax, word ptr [rcx+rbx+600h]
0x18009e2dc  shr     ax, 1
0x18009e2df  shr     dx, 1
0x18009e2e2  add     dx, ax
0x18009e2e5  movsxd  rcx, r11d
0x18009e2e8  mov     rax, [r15]
0x18009e2eb  mov     [rax+rcx*2+1F90h], dx
0x18009e2f3  mov     rcx, [r8]
0x18009e2f6  movsxd  rax, r11d
0x18009e2f9  movzx   edx, word ptr [rcx+rax*2+4012h]
0x18009e301  movzx   eax, word ptr [rcx+rbx+700h]
0x18009e309  shr     ax, 1
0x18009e30c  shr     dx, 1
0x18009e30f  add     dx, ax
0x18009e312  movsxd  rcx, r11d
0x18009e315  mov     rax, [r15]
0x18009e318  mov     [rax+rcx*2+1F92h], dx
0x18009e320  mov     rcx, [r8]
0x18009e323  movsxd  rax, r11d
0x18009e326  movzx   edx, word ptr [rcx+rax*2+4014h]
  ... truncated ...
```
