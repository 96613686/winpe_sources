# LibRaw::ahd_interpolate_combine_homogeneous_pixels(int,int,ushort (*)[512][512][3],char (*)[512][2])

- ea: `0x180031430`
- end: `0x180031781`
- name: `?ahd_interpolate_combine_homogeneous_pixels@LibRaw@@IEAAXHHPEAY2CAA@CAA@2GPEAY1CAA@1D@Z`
- size: `849`
- prototype: `void __fastcall(LibRaw *__hidden this, int, int, unsigned __int16 (*)[512][512][3], char (*)[512][2])`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180030fc0`

## callees

- `0x180031430`

## pseudocode

```c
void __fastcall LibRaw::ahd_interpolate_combine_homogeneous_pixels(
        LibRaw *this,
        int a2,
        int a3,
        unsigned __int16 (*a4)[512][512][3],
        char (*a5)[512][2])
{
  int v5; // ebx
  int v6; // r10d
  int v7; // esi
  __int64 v8; // r14
  LibRaw *v9; // rdi
  unsigned __int16 *v10; // r12
  int v11; // eax
  __m128i v12; // xmm4
  __int64 v13; // rbp
  __m128i si128; // xmm3
  __int64 v15; // r11
  __m128i v16; // xmm5
  __int64 v17; // rax
  signed int v18; // r9d
  int v19; // edx
  __int64 v20; // r8
  __m128i v21; // xmm6
  __int64 v22; // r15
  __int64 v23; // r8
  __int64 v24; // r10
  __m128i v25; // xmm1
  __int64 v26; // r13
  __m128i v29; // xmm1
  __m128i *v30; // rdx
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  __int64 v33; // rbx
  __int64 v34; // r14
  int v35; // r12d
  int *v36; // rdi
  __m128i v37; // xmm0
  __int64 v38; // rsi
  __int64 v39; // rbp
  int v40; // r8d
  char *v41; // r9
  __int64 v42; // r10
  char *v43; // rdx
  __int64 v44; // rax
  int v45; // ecx
  __int64 v46; // rcx
  __int64 v47; // rdx
  unsigned __int16 *v48; // xmm0_8
  int v49; // [rsp+0h] [rbp-A8h]
  __int64 v50; // [rsp+8h] [rbp-A0h]
  int v51; // [rsp+10h] [rbp-98h] BYREF
  int v52; // [rsp+14h] [rbp-94h]
  __int64 v53; // [rsp+18h] [rbp-90h]
  __int64 v54; // [rsp+20h] [rbp-88h]
  __m128i v55; // [rsp+28h] [rbp-80h] BYREF
  _WORD *v56; // [rsp+38h] [rbp-70h]
  __int64 v57; // [rsp+40h] [rbp-68h]
  __int64 v58; // [rsp+48h] [rbp-60h]
  int v60; // [rsp+B8h] [rbp+10h]

  v5 = *((unsigned __int16 *)this + 11);
  v6 = a2 + 509;
  v7 = a2 + 3;
  v8 = a3;
  v9 = this;
  v60 = a2 + 3;
  v10 = (unsigned __int16 *)a4;
  v11 = a3 + 509;
  v12 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)a4, (__m128i)(unsigned __int64)a4);
  if ( a3 + 509 >= v5 - 5 )
    v11 = v5 - 5;
  v13 = v11;
  if ( v6 >= *((unsigned __int16 *)this + 10) - 5 )
    v6 = *((unsigned __int16 *)this + 10) - 5;
  v57 = v11;
  if ( v7 < (__int64)v6 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v15 = a3 + 3LL;
    v16 = _mm_load_si128((const __m128i *)&_xmm);
    v17 = a2;
    v18 = 3;
    v19 = _isa_available;
    v20 = v7 - v17;
    v21 = _mm_load_si128((const __m128i *)&_xmm);
    v22 = v20 - 1;
    v23 = (v20 << 9) - 512;
    v58 = v8 + 3;
    v24 = v6 - (__int64)v7;
    v49 = 3;
    v54 = v24;
    v50 = v23;
    do
    {
      v25 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v18), 0);
      v26 = *((_QWORD *)v9 + 1) + 8LL * (int)(v8 + v7 * (unsigned __int16)v5 + 2);
      if ( v19 < 6 )
      {
        v30 = &v55;
        v31 = 2;
        v32 = &v10[1536 * v18 + 6];
        do
        {
          v30->m128i_i64[0] = (__int64)v32;
          v30 = (__m128i *)((char *)v30 + 8);
          v32 += 786432;
          --v31;
        }
        while ( v31 );
        LOWORD(v5) = *((_WORD *)v9 + 11);
        v29 = _mm_loadu_si128(&v55);
      }
      else
      {
        _XMM2 = _mm_add_epi64(
                  _mm_slli_epi64(
                    _mm_add_epi64(
                      _mm_slli_epi64(_mm_cvtepi32_epi64(_mm_move_epi64(v21)), 9u),
                      _mm_cvtepi32_epi64(_mm_move_epi64(v25))),
                    9u),
                  v16);
        __asm { vpmullq xmm1, xmm2, xmm3 }
        v29 = _mm_add_epi64(_XMM1, v12);
        v55 = v29;
      }
      if ( v15 < v13 )
      {
        v33 = 2;
        v34 = v18 + 1;
        v35 = 4;
        v53 = v13 - v15;
        do
        {
          v36 = &v51;
          v56 = (_WORD *)(v26 + 8);
          v37 = _mm_add_epi64(si128, v29);
          v29 = v37;
          v38 = 0;
          v55 = v37;
          v39 = 2;
          do
          {
            v40 = 0;
            *v36 = 0;
            if ( v22 <= v34 )
            {
              v41 = &(*a5)[v33][2 * v50 + v38];
              v42 = v34 - v22 + 1;
              do
              {
                if ( v33 <= v35 )
                {
                  v43 = v41;
                  v44 = v35 - v33 + 1;
                  do
                  {
                    v45 = *v43;
                    v43 += 2;
                    v40 += v45;
                    --v44;
                  }
                  while ( v44 );
                  *v36 = v40;
                }
                v41 += 1024;
                --v42;
              }
              while ( v42 );
            }
            ++v38;
            ++v36;
            --v39;
          }
          while ( v39 );
          v26 = (__int64)v56;
          if ( v51 == v52 )
          {
            v48 = (unsigned __int16 *)_mm_srli_si128(v37, 8).m128i_u64[0];
            *v56 = (*(unsigned __int16 *)v29.m128i_i64[0] + (unsigned int)*v48) >> 1;
            *(_WORD *)(v26 + 2) = (*(unsigned __int16 *)(v29.m128i_i64[0] + 2) + (unsigned int)v48[1]) >> 1;
            *(_WORD *)(v26 + 4) = (*(unsigned __int16 *)(v29.m128i_i64[0] + 4) + (unsigned int)v48[2]) >> 1;
          }
          else
          {
            v46 = 0;
            if ( v52 > v51 )
              v46 = 1;
            v47 = v55.m128i_i64[v46];
            *(_DWORD *)v56 = *(_DWORD *)v47;
            *(_WORD *)(v26 + 4) = *(_WORD *)(v47 + 4);
          }
          ++v35;
          ++v33;
          --v53;
        }
        while ( v53 );
        v9 = this;
        v23 = v50;
        v18 = v49;
        v7 = v60;
        LOWORD(v5) = *((_WORD *)this + 11);
        v24 = v54;
        v13 = v57;
        v15 = v58;
        LODWORD(v8) = a3;
        v10 = (unsigned __int16 *)a4;
      }
      v19 = _isa_available;
      ++v7;
      ++v18;
      v60 = v7;
      v23 += 512;
      v49 = v18;
      ++v22;
      v50 = v23;
      v54 = --v24;
    }
    while ( v24 );
  }
}

```

## disassembly

```asm
0x180031430  mov     [rsp+arg_18], r9
0x180031435  mov     [rsp+arg_10], r8d
0x18003143a  mov     [rsp+arg_0], rcx
0x18003143f  push    rbx
0x180031440  push    rbp
0x180031441  push    rsi
0x180031442  push    rdi
0x180031443  push    r12
0x180031445  push    r14
0x180031447  sub     rsp, 78h
0x18003144b  movzx   ebx, word ptr [rcx+16h]
0x18003144f  lea     r10d, [rdx+1FDh]
0x180031456  movzx   r11d, word ptr [rcx+14h]
0x18003145b  lea     esi, [rdx+3]
0x18003145e  add     r11d, 0FFFFFFFBh
0x180031462  movsxd  r14, r8d
0x180031465  mov     rdi, rcx
0x180031468  mov     [rsp+0A8h+arg_8], esi
0x18003146f  lea     r8d, [rbx-5]
0x180031473  movsxd  rcx, esi
0x180031476  movq    xmm4, r9
0x18003147b  mov     r12, r9
0x18003147e  lea     eax, [r14+1FDh]
0x180031485  punpcklqdq xmm4, xmm4
0x180031489  cmp     eax, r8d
0x18003148c  cmovge  eax, r8d
0x180031490  cmp     r10d, r11d
0x180031493  movsxd  rbp, eax
0x180031496  cmovge  r10d, r11d
0x18003149a  mov     [rsp+0A8h+var_68], rbp
0x18003149f  movsxd  r10, r10d
0x1800314a2  cmp     rcx, r10
0x1800314a5  jge     loc_180031774
0x1800314ab  movdqa  xmm3, cs:__xmm@00000000000000060000000000000006
0x1800314b3  lea     r11, [r14+3]
0x1800314b7  movdqa  xmm5, cs:__xmm@00000000000000020000000000000002
0x1800314bf  mov     r8, rcx
0x1800314c2  movsxd  rax, edx
0x1800314c5  mov     r9d, 3
0x1800314cb  mov     edx, cs:__isa_available
0x1800314d1  sub     r8, rax
0x1800314d4  mov     [rsp+0A8h+var_38], r13
0x1800314d9  mov     [rsp+0A8h+var_40], r15
0x1800314de  movaps  [rsp+0A8h+var_58], xmm6
0x1800314e3  movdqa  xmm6, cs:__xmm@00000003000000020000000100000000
0x1800314eb  lea     r15, [r8-1]
0x1800314ef  shl     r8, 9
0x1800314f3  sub     r8, 200h
0x1800314fa  mov     [rsp+0A8h+var_60], r11
0x1800314ff  sub     r10, rcx
0x180031502  mov     [rsp+0A8h+var_A8], r9d
0x180031506  mov     [rsp+0A8h+var_88], r10
0x18003150b  mov     [rsp+0A8h+var_A0], r8
0x180031510  movzx   eax, bx
0x180031513  imul    eax, esi
0x180031516  movd    xmm1, r9d
0x18003151b  pshufd  xmm1, xmm1, 0
0x180031520  add     eax, 2
0x180031523  add     eax, r14d
0x180031526  movsxd  rcx, eax
0x180031529  mov     rax, [rdi+8]
0x18003152d  lea     r13, [rax+rcx*8]
0x180031531  cmp     edx, 6
0x180031534  jl      short loc_18003156C
0x180031536  movq    xmm0, xmm6
0x18003153a  pmovsxdq xmm2, xmm0
0x18003153f  movq    xmm0, xmm1
0x180031543  psllq   xmm2, 9
0x180031548  pmovsxdq xmm1, xmm0
0x18003154d  paddq   xmm2, xmm1
0x180031551  psllq   xmm2, 9
0x180031556  paddq   xmm2, xmm5
0x18003155a  vpmullq xmm1, xmm2, xmm3
0x180031560  paddq   xmm1, xmm4
0x180031564  movdqu  [rsp+0A8h+var_80], xmm1
0x18003156a  jmp     short loc_1800315AD
0x18003156c  movsxd  rax, r9d
0x18003156f  lea     rdx, [rsp+0A8h+var_80]
0x180031574  mov     ecx, 2
0x180031579  lea     rax, [rax+rax*2]
0x18003157d  shl     rax, 0Ah
0x180031581  add     rax, 0Ch
0x180031585  add     rax, r12
0x180031588  nop     dword ptr [rax+rax+00000000h]
0x180031590  mov     [rdx], rax
0x180031593  lea     rdx, [rdx+8]
0x180031597  add     rax, 180000h
0x18003159d  sub     rcx, 1
0x1800315a1  jnz     short loc_180031590
0x1800315a3  movzx   ebx, word ptr [rdi+16h]
0x1800315a7  movdqu  xmm1, [rsp+0A8h+var_80]
0x1800315ad  cmp     r11, rbp
0x1800315b0  jge     loc_180031731
0x1800315b6  lea     eax, [r9+1]
0x1800315ba  mov     ebx, 2
0x1800315bf  movsxd  r14, eax
0x1800315c2  mov     r12d, 4
0x1800315c8  mov     rax, rbp
0x1800315cb  sub     rax, r11
0x1800315ce  mov     [rsp+0A8h+var_90], rax
0x1800315d3  add     r13, 8
0x1800315d7  lea     rdi, [rsp+0A8h+var_98]
0x1800315dc  movdqa  xmm0, xmm3
0x1800315e0  mov     [rsp+0A8h+var_70], r13
0x1800315e5  mov     r13, [rsp+0A8h+var_A0]
0x1800315ea  paddq   xmm0, xmm1
0x1800315ee  movdqa  xmm1, xmm0
0x1800315f2  xor     esi, esi
0x1800315f4  movdqu  [rsp+0A8h+var_80], xmm0
0x1800315fa  mov     ebp, 2
0x1800315ff  nop
0x180031600  xor     r8d, r8d
0x180031603  mov     [rdi], r8d
0x180031606  cmp     r15, r14
0x180031609  jg      short loc_180031660
0x18003160b  lea     rax, [rbx+r13]
0x18003160f  movsxd  r11, r12d
0x180031612  lea     r9, [rsi+rax*2]
0x180031616  mov     r10, r14
0x180031619  add     r9, [rsp+0A8h+arg_20]
0x180031621  sub     r10, r15
0x180031624  inc     r10
0x180031627  cmp     rbx, r11
0x18003162a  jg      short loc_180031653
0x18003162c  mov     rax, r11
0x18003162f  mov     rdx, r9
0x180031632  sub     rax, rbx
0x180031635  inc     rax
0x180031638  nop     dword ptr [rax+rax+00000000h]
0x180031640  movsx   ecx, byte ptr [rdx]
0x180031643  lea     rdx, [rdx+2]
0x180031647  add     r8d, ecx
0x18003164a  sub     rax, 1
0x18003164e  jnz     short loc_180031640
0x180031650  mov     [rdi], r8d
0x180031653  add     r9, 400h
0x18003165a  sub     r10, 1
0x18003165e  jnz     short loc_180031627
0x180031660  inc     rsi
0x180031663  add     rdi, 4
0x180031667  sub     rbp, 1
0x18003166b  jnz     short loc_180031600
0x18003166d  mov     rax, [rsp+0A8h+var_98]
0x180031672  mov     edx, dword ptr [rsp+0A8h+var_98+4]
0x180031676  mov     r13, [rsp+0A8h+var_70]
0x18003167b  cmp     eax, edx
0x18003167d  jz      short loc_1800316A1
0x18003167f  xor     ecx, ecx
0x180031681  cmp     edx, eax
0x180031683  mov     eax, 8
0x180031688  cmovg   ecx, eax
0x18003168b  mov     rdx, qword ptr [rsp+rcx+0A8h+var_80]
0x180031690  mov     eax, [rdx]
0x180031692  mov     [r13+0], eax
0x180031696  movzx   eax, word ptr [rdx+4]
0x18003169a  mov     [r13+4], ax
0x18003169f  jmp     short loc_1800316E4
0x1800316a1  movq    rdx, xmm1
0x1800316a6  psrldq  xmm0, 8
0x1800316ab  movq    r8, xmm0
0x1800316b0  movzx   eax, word ptr [rdx]
0x1800316b3  movzx   ecx, word ptr [r8]
0x1800316b7  add     ecx, eax
0x1800316b9  shr     ecx, 1
0x1800316bb  mov     [r13+0], cx
0x1800316c0  movzx   eax, word ptr [rdx+2]
0x1800316c4  movzx   ecx, word ptr [r8+2]
0x1800316c9  add     ecx, eax
0x1800316cb  shr     ecx, 1
0x1800316cd  mov     [r13+2], cx
0x1800316d2  movzx   ecx, word ptr [r8+4]
0x1800316d7  movzx   eax, word ptr [rdx+4]
0x1800316db  add     ecx, eax
0x1800316dd  shr     ecx, 1
0x1800316df  mov     [r13+4], cx
0x1800316e4  inc     r12d
0x1800316e7  inc     rbx
0x1800316ea  sub     [rsp+0A8h+var_90], 1
0x1800316f0  jnz     loc_1800315D3
0x1800316f6  mov     rdi, [rsp+0A8h+arg_0]
0x1800316fe  mov     r8, [rsp+0A8h+var_A0]
0x180031703  mov     r9d, [rsp+0A8h+var_A8]
0x180031707  mov     esi, [rsp+0A8h+arg_8]
0x18003170e  movzx   ebx, word ptr [rdi+16h]
0x180031712  mov     r10, [rsp+0A8h+var_88]
0x180031717  mov     rbp, [rsp+0A8h+var_68]
0x18003171c  mov     r11, [rsp+0A8h+var_60]
0x180031721  mov     r14d, [rsp+0A8h+arg_10]
0x180031729  mov     r12, [rsp+0A8h+arg_18]
0x180031731  mov     edx, cs:__isa_available
0x180031737  inc     esi
0x180031739  inc     r9d
0x18003173c  mov     [rsp+0A8h+arg_8], esi
0x180031743  add     r8, 200h
0x18003174a  mov     [rsp+0A8h+var_A8], r9d
0x18003174e  inc     r15
0x180031751  mov     [rsp+0A8h+var_A0], r8
0x180031756  sub     r10, 1
0x18003175a  mov     [rsp+0A8h+var_88], r10
0x18003175f  jnz     loc_180031510
0x180031765  movaps  xmm6, [rsp+0A8h+var_58]
0x18003176a  mov     r15, [rsp+0A8h+var_40]
0x18003176f  mov     r13, [rsp+0A8h+var_38]
0x180031774  add     rsp, 78h
0x180031778  pop     r14
0x18003177a  pop     r12
0x18003177c  pop     rdi
0x18003177d  pop     rsi
0x18003177e  pop     rbp
0x18003177f  pop     rbx
0x180031780  retn
```
