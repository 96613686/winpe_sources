# u8_ipps_cRealRecombine_32f

- ea: `0x1800418b0`
- end: `0x1800419ed`
- name: `u8_ipps_cRealRecombine_32f`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f820`
- `0x18000fa20`

## callees

- `0x1800418b0`

## pseudocode

```c
void __fastcall u8_ipps_cRealRecombine_32f(__int64 a1, __int64 a2, __int64 a3, __m128 *a4)
{
  __int64 v4; // r12
  __int64 v6; // r10
  double *i; // r13
  __m128 v8; // xmm1
  __m128 v9; // xmm2
  __m128 v10; // xmm0
  __m128 v11; // xmm1
  __m128 v12; // xmm4
  __m128 v13; // xmm5
  __m128 v14; // xmm3
  __m128 v15; // xmm2
  __m128 v16; // xmm0
  __m128 v17; // xmm5
  __m128 v18; // xmm4
  __m128 v19; // xmm6
  __m128 v20; // xmm7
  __m128 v21; // xmm0
  __m128 v22; // xmm7
  __m128 v23; // xmm4
  __m128 v24; // xmm6
  __m128 v25; // xmm7
  __m128 v26; // xmm0
  __m128 v27; // xmm3
  __m128 v28; // xmm6
  __m128 v29; // xmm0
  __m128 v30; // xmm5
  __m128 v31; // xmm2
  __m128 v32; // xmm5

  v4 = a1;
  v6 = a1 + 4 * a2;
  for ( i = (double *)(a1 + 8 * a2); ; _mm_storeh_ps(i, v32) )
  {
    v8 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 8), (__m128)*(unsigned __int64 *)(v4 + 16));
    v9 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 24), (__m128)*(unsigned __int64 *)(v4 + 32));
    v10 = _mm_shuffle_ps(v8, v9, 136);
    v11 = _mm_shuffle_ps(v8, v9, 221);
    v12 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 1), (__m128)*((unsigned __int64 *)i - 2));
    v13 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 3), (__m128)*((unsigned __int64 *)i - 4));
    v14 = _mm_shuffle_ps(v12, v13, 136);
    v15 = v10;
    v16 = _mm_sub_ps(v10, v14);
    v17 = _mm_shuffle_ps(v12, v13, 221);
    v18 = _mm_add_ps(v17, v11);
    v19 = _mm_mul_ps(*a4, v16);
    v20 = a4[1];
    v21 = _mm_mul_ps(v16, v20);
    v22 = _mm_mul_ps(v20, v18);
    v23 = _mm_add_ps(_mm_mul_ps(v18, *a4), v21);
    v24 = _mm_sub_ps(v22, v19);
    v25 = _mm_sub_ps(v24, v17);
    v26 = _mm_add_ps(v14, v23);
    a4 += 2;
    v27 = _mm_unpacklo_ps(v26, v25);
    v28 = _mm_sub_ps(v24, v11);
    _mm_storel_ps((double *)(v4 + 8), v27);
    _mm_storeh_ps((double *)(v4 + 16), v27);
    v29 = _mm_unpackhi_ps(v26, v25);
    _mm_storel_ps((double *)(v4 + 24), v29);
    v4 += 32;
    v30 = _mm_sub_ps(v15, v23);
    v31 = _mm_unpacklo_ps(v30, v28);
    _mm_storel_ps(i - 1, v31);
    _mm_storeh_ps(i - 2, v31);
    v32 = _mm_unpackhi_ps(v30, v28);
    _mm_storel_ps(i - 3, v32);
    i -= 4;
    if ( v4 == v6 )
      break;
    _mm_storeh_ps((double *)v4, v29);
  }
  *(_DWORD *)(v6 + 4) ^= 0x80000000;
}

```

## disassembly

```asm
0x1800418b0  push    rsi
0x1800418b1  push    rdi
0x1800418b2  push    r12
0x1800418b4  push    r13
0x1800418b6  sub     rsp, 28h
0x1800418ba  movdqa  [rsp+48h+var_48], xmm7
0x1800418bf  movdqa  [rsp+48h+var_38], xmm6
0x1800418c5  mov     rdi, rcx
0x1800418c8  mov     rsi, rdx
0x1800418cb  mov     rdx, r8
0x1800418ce  mov     rcx, r9
0x1800418d1  mov     r12, rdi
0x1800418d4  mov     r11, rcx
0x1800418d7  lea     r10, [r12+rsi*4]
0x1800418db  lea     r13, [r12+rsi*8]
0x1800418df  jmp     short loc_1800418FA
0x1800418f0  movhps  qword ptr [r12], xmm0
0x1800418f5  movhps  qword ptr [r13+0], xmm5
0x1800418fa  movsd   xmm0, qword ptr [r12+8]
0x180041901  movsd   xmm7, qword ptr [r12+10h]
0x180041908  movlhps xmm0, xmm7
0x18004190b  movaps  xmm1, xmm0
0x18004190e  movsd   xmm2, qword ptr [r12+18h]
0x180041915  movsd   xmm7, qword ptr [r12+20h]
0x18004191c  movlhps xmm2, xmm7
0x18004191f  shufps  xmm0, xmm2, 88h
0x180041923  shufps  xmm1, xmm2, 0DDh
0x180041927  movsd   xmm3, qword ptr [r13-8]
0x18004192d  movsd   xmm7, qword ptr [r13-10h]
0x180041933  movlhps xmm3, xmm7
0x180041936  movaps  xmm4, xmm3
0x180041939  movsd   xmm5, qword ptr [r13-18h]
0x18004193f  movsd   xmm7, qword ptr [r13-20h]
0x180041945  movlhps xmm5, xmm7
0x180041948  shufps  xmm3, xmm5, 88h
0x18004194c  shufps  xmm4, xmm5, 0DDh
0x180041950  movaps  xmm2, xmm0
0x180041953  subps   xmm0, xmm3
0x180041956  movaps  xmm6, xmmword ptr [r11]
0x18004195a  movaps  xmm5, xmm4
0x18004195d  addps   xmm4, xmm1
0x180041960  mulps   xmm6, xmm0
0x180041963  movaps  xmm7, xmmword ptr [r11+10h]
0x180041968  mulps   xmm0, xmm7
0x18004196b  mulps   xmm7, xmm4
0x18004196e  mulps   xmm4, xmmword ptr [r11]
0x180041972  subps   xmm7, xmm6
0x180041975  addps   xmm4, xmm0
0x180041978  movaps  xmm6, xmm7
0x18004197b  subps   xmm7, xmm5
0x18004197e  addps   xmm3, xmm4
0x180041981  subps   xmm2, xmm4
0x180041984  movaps  xmm0, xmm3
0x180041987  add     r11, 20h ; ' '
0x18004198b  unpcklps xmm3, xmm7
0x18004198e  subps   xmm6, xmm1
0x180041991  movlps  qword ptr [r12+8], xmm3
0x180041997  movhps  qword ptr [r12+10h], xmm3
0x18004199d  unpckhps xmm0, xmm7
0x1800419a0  movlps  qword ptr [r12+18h], xmm0
0x1800419a6  add     r12, 20h ; ' '
0x1800419aa  movaps  xmm5, xmm2
0x1800419ad  unpcklps xmm2, xmm6
0x1800419b0  movlps  qword ptr [r13-8], xmm2
0x1800419b5  movhps  qword ptr [r13-10h], xmm2
0x1800419ba  unpckhps xmm5, xmm6
0x1800419bd  movlps  qword ptr [r13-18h], xmm5
0x1800419c2  sub     r13, 20h ; ' '
0x1800419c6  cmp     r12, r10
0x1800419c9  jnz     loc_1800418F0
0x1800419cf  xor     dword ptr [r10+4], 80000000h
0x1800419d7  movdqa  xmm7, [rsp+48h+var_48]
0x1800419dc  movdqa  xmm6, [rsp+48h+var_38]
0x1800419e2  add     rsp, 28h
0x1800419e6  pop     r13
0x1800419e8  pop     r12
0x1800419ea  pop     rdi
0x1800419eb  pop     rsi
0x1800419ec  retn
```
