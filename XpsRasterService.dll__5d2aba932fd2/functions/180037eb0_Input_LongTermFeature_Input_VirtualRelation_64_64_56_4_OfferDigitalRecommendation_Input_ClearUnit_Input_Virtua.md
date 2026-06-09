# Input::LongTermFeature<Input::VirtualRelation<64,64,56,4>>::OfferDigitalRecommendation(Input::ClearUnit &,Input::VirtualRelation<64,64,56,4> &)

- ea: `0x180037eb0`
- end: `0x1800382c3`
- name: `?OfferDigitalRecommendation@?$LongTermFeature@V?$VirtualRelation@$0EA@$0EA@$0DI@$03@Input@@@Input@@SAXAEAVClearUnit@2@AEAV?$VirtualRelation@$0EA@$0EA@$0DI@$03@2@@Z`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800386f0`

## callees

- `0x180003c34`
- `0x180003c88`
- `0x180037eb0`

## pseudocode

```c
unsigned __int64 __fastcall Input::LongTermFeature<Input::VirtualRelation<64,64,56,4>>::OfferDigitalRecommendation(
        __int64 a1)
{
  unsigned __int64 result; // rax
  __int64 v3; // rsi
  __int64 v4; // rbx
  __m128 *v5; // rbp
  __int64 v6; // r14
  __m128 v7; // xmm7
  float v8; // xmm1_4
  float v9; // xmm7_4
  float v10; // xmm1_4
  float v11; // xmm8_4
  float v12; // xmm7_4
  float v13; // xmm6_4
  float v14; // xmm3_4
  float *v15; // rax
  float v16; // xmm5_4
  float v17; // xmm2_4
  float v18; // xmm8_4
  float v19; // xmm7_4
  float v20; // xmm5_4
  float v21; // xmm4_4
  float v22; // xmm8_4
  float v23; // xmm0_4
  float v24; // xmm4_4
  int v25; // r8d
  float v26; // xmm0_4
  float v27; // xmm5_4
  int v28; // edx
  float v29; // xmm0_4
  float v30; // xmm7_4
  int v31; // ecx
  float v32; // xmm0_4
  _DWORD *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdi
  __m128 v36; // [rsp+20h] [rbp-C8h]

  result = *(unsigned int *)(a1 + 7632);
  if ( (int)result > 8 )
    result = 8;
  v3 = (int)result;
  if ( (int)result > 0 )
  {
    v4 = a1 + 2;
    v5 = (__m128 *)(a1 + 7496);
    v6 = (int)result;
    do
    {
      v7 = *v5;
      v8 = _mm_shuffle_ps(v7, v7, 170).m128_f32[0];
      v36 = *v5;
      v9 = _mm_shuffle_ps(v7, v7, 85).m128_f32[0] + 32.0;
      v10 = (float)((float)(v8 + 0.0) * 90.0) / 63.0;
      v11 = (float)((float)((float)((float)((float)(v10 * 0.000001017) * v10) * v10)
                          + (float)((float)(v10 * 0.000042750002) * v10))
                  + (float)(v10 * 0.008525))
          + 0.43643188;
      if ( v9 >= 64.0 )
        v9 = v9 + -64.0;
      if ( v9 < 0.0 )
        v9 = v9 + 64.0;
      v12 = v9 * 0.024543693;
      v13 = cosf(v12) * v11;
      v14 = o_sinf_0(v12) * v11;
      v15 = (float *)&Input::VirtualRelation<64,64,56,4>::TemporaryInstruction[2 * v36.m128_i32[3]];
      v16 = v15[1];
      v17 = v15[2];
      v18 = v15[3];
      v19 = (float)((float)(v14 * -1.0) * v16) + (float)(*v15 * v13);
      v20 = (float)(v16 * v13) + (float)(*v15 * v14);
      v21 = (float)((float)(v14 * -1.0) * v18) + (float)(v17 * v13);
      v22 = (float)((float)(v18 * v13) + (float)(v17 * v14)) * 2048.0;
      *(float *)(v4 + 14) = (float)v36.m128_u16[0] * 0.0078125;
      if ( v22 >= 0.0 )
        v23 = FLOAT_0_5;
      else
        v23 = FLOAT_N0_5;
      v24 = v21 * 2048.0;
      v25 = (int)(float)(v23 + v22);
      if ( v24 >= 0.0 )
        v26 = FLOAT_0_5;
      else
        v26 = FLOAT_N0_5;
      v27 = v20 * 2048.0;
      v28 = (int)(float)(v26 + v24);
      if ( v27 >= 0.0 )
        v29 = FLOAT_0_5;
      else
        v29 = FLOAT_N0_5;
      v30 = v19 * 2048.0;
      v31 = (int)(float)(v29 + v27);
      if ( v30 >= 0.0 )
        v32 = FLOAT_0_5;
      else
        v32 = FLOAT_N0_5;
      *(_WORD *)v4 = v31;
      *(_WORD *)(v4 + 2) = v28;
      ++v5;
      *(_WORD *)(v4 + 4) = v25;
      result = (unsigned int)(int)(float)(v32 + v30);
      *(_WORD *)(v4 - 2) = result;
      *(_DWORD *)(v4 + 26) = v36.m128_i32[3];
      v4 += 928;
      --v6;
    }
    while ( v6 );
  }
  if ( v3 < 8 )
  {
    result = 8 - v3;
    if ( 8 - v3 < 4 )
      goto LABEL_27;
    v33 = (_DWORD *)(a1 + 928 * v3 + 932);
    result = ((unsigned __int64)(4 - v3) >> 2) + 1;
    v3 += 4 * result;
    do
    {
      *(v33 - 229) = 0;
      *(v33 - 233) = 2048;
      *(v33 - 232) = 0x8000000;
      *(v33 - 226) = 0;
      v33[3] = 0;
      *(v33 - 1) = 2048;
      *v33 = 0x8000000;
      v33[6] = 0;
      v33[235] = 0;
      v33[231] = 2048;
      v33[232] = 0x8000000;
      v33[238] = 0;
      v33[467] = 0;
      v33[463] = 2048;
      v33[464] = 0x8000000;
      v33[470] = 0;
      v33 += 928;
      --result;
    }
    while ( result );
    if ( v3 < 8 )
    {
LABEL_27:
      v34 = a1 + 928 * v3 + 2;
      v35 = 8 - v3;
      do
      {
        *(_DWORD *)(v34 + 14) = 0;
        *(_DWORD *)(v34 - 2) = 2048;
        *(_DWORD *)(v34 + 2) = 0x8000000;
        *(_DWORD *)(v34 + 26) = 0;
        v34 += 928;
        --v35;
      }
      while ( v35 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037eb0  mov     r11, rsp
0x180037eb3  push    rsi
0x180037eb4  push    rdi
0x180037eb5  push    r15
0x180037eb7  sub     rsp, 0D0h
0x180037ebe  mov     eax, [rcx+1DD0h]
0x180037ec4  mov     edi, 8
0x180037ec9  cmp     eax, edi
0x180037ecb  mov     r15, rcx
0x180037ece  cmovg   eax, edi
0x180037ed1  movsxd  rsi, eax
0x180037ed4  test    eax, eax
0x180037ed6  jle     loc_1800381BC
0x180037edc  mov     [r11+8], rbx
0x180037ee0  lea     rbx, [rcx+2]
0x180037ee4  mov     [r11+10h], rbp
0x180037ee8  lea     rbp, [rcx+1D48h]
0x180037eef  mov     [r11+18h], r12
0x180037ef3  lea     r12, ?TemporaryInstruction@?$VirtualRelation@$0EA@$0EA@$0DI@$03@Input@@0V?$StripedCategory@V?$StripedCategory@M$03@Data@@$03@Data@@B; Data::StripedCategory<Data::StripedCategory<float,4>,4> const Input::VirtualRelation<64,64,56,4>::TemporaryInstruction
0x180037efa  mov     [r11+20h], r14
0x180037efe  mov     r14, rsi
0x180037f01  movaps  xmmword ptr [r11-28h], xmm6
0x180037f06  movaps  xmmword ptr [r11-38h], xmm7
0x180037f0b  movaps  xmmword ptr [r11-48h], xmm8
0x180037f10  movaps  xmmword ptr [r11-58h], xmm9
0x180037f15  xorps   xmm9, xmm9
0x180037f19  movaps  xmmword ptr [r11-68h], xmm10
0x180037f1e  movss   xmm10, cs:__real@bf000000
0x180037f27  movaps  xmmword ptr [r11-78h], xmm11
0x180037f2c  movss   xmm11, cs:__real@3f000000
0x180037f35  movaps  [rsp+0E8h+var_88], xmm12
0x180037f3b  movss   xmm12, cs:__real@45000000
0x180037f44  movaps  [rsp+0E8h+var_98], xmm13
0x180037f4a  movss   xmm13, cs:__real@42800000
0x180037f53  movaps  [rsp+0E8h+var_A8], xmm14
0x180037f59  movss   xmm14, cs:__real@c2800000
0x180037f62  movaps  [rsp+0E8h+var_B8], xmm15
0x180037f68  movss   xmm15, cs:__real@42b40000
0x180037f71  nop     dword ptr [rax+00h]
0x180037f75  nop     word ptr [rax+rax+00000000h]
0x180037f80  movups  xmm7, xmmword ptr [rbp+0]
0x180037f84  movaps  xmm1, xmm7
0x180037f87  shufps  xmm1, xmm7, 0AAh
0x180037f8b  addss   xmm1, xmm9
0x180037f90  movups  [rsp+0E8h+var_C8], xmm7
0x180037f95  shufps  xmm7, xmm7, 55h ; 'U'
0x180037f99  addss   xmm7, cs:__real@42000000
0x180037fa1  mulss   xmm1, xmm15
0x180037fa6  comiss  xmm7, xmm13
0x180037faa  divss   xmm1, cs:__real@427c0000
0x180037fb2  movaps  xmm8, xmm1
0x180037fb6  movaps  xmm0, xmm1
0x180037fb9  mulss   xmm8, cs:__real@35887fdb
0x180037fc2  mulss   xmm0, cs:__real@38334e77
0x180037fca  mulss   xmm8, xmm1
0x180037fcf  mulss   xmm0, xmm1
0x180037fd3  mulss   xmm8, xmm1
0x180037fd8  mulss   xmm1, cs:__real@3c0bac71
0x180037fe0  addss   xmm8, xmm0
0x180037fe5  addss   xmm8, xmm1
0x180037fea  addss   xmm8, cs:__real@3edf7400
0x180037ff3  jb      short loc_180037FFA
0x180037ff5  addss   xmm7, xmm14
0x180037ffa  comiss  xmm9, xmm7
0x180037ffe  jbe     short loc_180038005
0x180038000  addss   xmm7, xmm13
0x180038005  mulss   xmm7, cs:__real@3cc90fdb
0x18003800d  movaps  xmm0, xmm7; X
0x180038010  call    cosf
0x180038015  movaps  xmm6, xmm0
0x180038018  movaps  xmm0, xmm7; X
0x18003801b  mulss   xmm6, xmm8
0x180038020  call    _o_sinf_0
0x180038025  mov     r9, qword ptr [rsp+0E8h+var_C8+8]
0x18003802a  movaps  xmm3, xmm0
0x18003802d  mulss   xmm3, xmm8
0x180038032  shr     r9, 20h
0x180038036  movsxd  rax, r9d
0x180038039  shl     rax, 4
0x18003803d  add     rax, r12
0x180038040  movaps  xmm4, xmm3
0x180038043  mulss   xmm4, cs:__real@bf800000
0x18003804b  movss   xmm1, dword ptr [rax]
0x18003804f  movss   xmm5, dword ptr [rax+4]
0x180038054  movaps  xmm0, xmm1
0x180038057  movss   xmm2, dword ptr [rax+8]
0x18003805c  movaps  xmm7, xmm4
0x18003805f  movss   xmm8, dword ptr [rax+0Ch]
0x180038065  movzx   eax, word ptr [rsp+0E8h+var_C8]
0x18003806a  mulss   xmm0, xmm6
0x18003806e  mulss   xmm4, xmm8
0x180038073  mulss   xmm7, xmm5
0x180038077  mulss   xmm8, xmm6
0x18003807c  addss   xmm7, xmm0
0x180038080  mulss   xmm5, xmm6
0x180038084  movaps  xmm0, xmm2
0x180038087  mulss   xmm1, xmm3
0x18003808b  mulss   xmm0, xmm6
0x18003808f  mulss   xmm2, xmm3
0x180038093  addss   xmm5, xmm1
0x180038097  addss   xmm4, xmm0
0x18003809b  xorps   xmm0, xmm0
0x18003809e  cvtsi2ss xmm0, eax
0x1800380a2  addss   xmm8, xmm2
0x1800380a7  mulss   xmm0, cs:__real@3c000000
0x1800380af  mulss   xmm8, xmm12
0x1800380b4  movss   dword ptr [rbx+0Eh], xmm0
0x1800380b9  comiss  xmm9, xmm8
0x1800380bd  jbe     short loc_1800380C5
0x1800380bf  movaps  xmm0, xmm10
0x1800380c3  jmp     short loc_1800380C9
0x1800380c5  movaps  xmm0, xmm11
0x1800380c9  addss   xmm0, xmm8
0x1800380ce  mulss   xmm4, xmm12
0x1800380d3  comiss  xmm9, xmm4
0x1800380d7  cvttss2si r8d, xmm0
0x1800380dc  jbe     short loc_1800380E4
0x1800380de  movaps  xmm0, xmm10
0x1800380e2  jmp     short loc_1800380E8
0x1800380e4  movaps  xmm0, xmm11
0x1800380e8  addss   xmm0, xmm4
0x1800380ec  mulss   xmm5, xmm12
0x1800380f1  comiss  xmm9, xmm5
0x1800380f5  cvttss2si edx, xmm0
0x1800380f9  jbe     short loc_180038101
0x1800380fb  movaps  xmm0, xmm10
0x1800380ff  jmp     short loc_180038105
0x180038101  movaps  xmm0, xmm11
0x180038105  addss   xmm0, xmm5
0x180038109  mulss   xmm7, xmm12
0x18003810e  comiss  xmm9, xmm7
0x180038112  cvttss2si ecx, xmm0
0x180038116  jbe     short loc_18003811E
0x180038118  movaps  xmm0, xmm10
0x18003811c  jmp     short loc_180038122
0x18003811e  movaps  xmm0, xmm11
0x180038122  mov     [rbx], cx
0x180038125  addss   xmm0, xmm7
0x180038129  mov     [rbx+2], dx
0x18003812d  add     rbp, 10h
0x180038131  mov     [rbx+4], r8w
0x180038136  cvttss2si eax, xmm0
0x18003813a  mov     [rbx-2], ax
0x18003813e  mov     [rbx+1Ah], r9d
0x180038142  add     rbx, 3A0h
0x180038149  sub     r14, 1
0x18003814d  jnz     loc_180037F80
0x180038153  movaps  xmm15, [rsp+0E8h+var_B8]
0x180038159  movaps  xmm14, [rsp+0E8h+var_A8]
0x18003815f  movaps  xmm13, [rsp+0E8h+var_98]
0x180038165  movaps  xmm12, [rsp+0E8h+var_88]
0x18003816b  movaps  xmm11, [rsp+0E8h+var_78]
0x180038171  movaps  xmm10, [rsp+0E8h+var_68]
0x18003817a  movaps  xmm9, [rsp+0E8h+var_58]
0x180038183  movaps  xmm8, [rsp+0E8h+var_48]
0x18003818c  movaps  xmm7, [rsp+0E8h+var_38]
0x180038194  movaps  xmm6, [rsp+0E8h+var_28]
0x18003819c  mov     r14, [rsp+0E8h+arg_18]
0x1800381a4  mov     r12, [rsp+0E8h+arg_10]
0x1800381ac  mov     rbp, [rsp+0E8h+arg_8]
0x1800381b4  mov     rbx, [rsp+0E8h+arg_0]
0x1800381bc  cmp     rsi, rdi
0x1800381bf  jge     loc_1800382B7
0x1800381c5  mov     rax, rdi
0x1800381c8  xor     edx, edx
0x1800381ca  sub     rax, rsi
0x1800381cd  cmp     rax, 4
0x1800381d1  jl      loc_180038285
0x1800381d7  imul    rcx, rsi, 3A0h
0x1800381de  mov     eax, 4
0x1800381e3  sub     rax, rsi
0x1800381e6  add     rcx, 3A4h
0x1800381ed  add     rcx, r15
0x1800381f0  shr     rax, 2
0x1800381f4  inc     rax
0x1800381f7  lea     rsi, [rsi+rax*4]
0x1800381fb  nop     dword ptr [rax+rax+00h]
0x180038200  mov     [rcx-394h], edx
0x180038206  mov     dword ptr [rcx-3A4h], 800h
0x180038210  mov     dword ptr [rcx-3A0h], 8000000h
0x18003821a  mov     [rcx-388h], edx
0x180038220  mov     [rcx+0Ch], edx
0x180038223  mov     dword ptr [rcx-4], 800h
0x18003822a  mov     dword ptr [rcx], 8000000h
0x180038230  mov     [rcx+18h], edx
0x180038233  mov     [rcx+3ACh], edx
0x180038239  mov     dword ptr [rcx+39Ch], 800h
0x180038243  mov     dword ptr [rcx+3A0h], 8000000h
0x18003824d  mov     [rcx+3B8h], edx
0x180038253  mov     [rcx+74Ch], edx
0x180038259  mov     dword ptr [rcx+73Ch], 800h
0x180038263  mov     dword ptr [rcx+740h], 8000000h
0x18003826d  mov     [rcx+758h], edx
0x180038273  lea     rcx, [rcx+0E80h]
0x18003827a  sub     rax, 1
0x18003827e  jnz     short loc_180038200
0x180038280  cmp     rsi, rdi
0x180038283  jge     short loc_1800382B7
0x180038285  imul    rcx, rsi, 3A0h
0x18003828c  add     rcx, 2
0x180038290  add     rcx, r15
0x180038293  sub     rdi, rsi
0x180038296  mov     [rcx+0Eh], edx
0x180038299  mov     dword ptr [rcx-2], 800h
0x1800382a0  mov     dword ptr [rcx+2], 8000000h
0x1800382a7  mov     [rcx+1Ah], edx
0x1800382aa  lea     rcx, [rcx+3A0h]
0x1800382b1  sub     rdi, 1
0x1800382b5  jnz     short loc_180038296
0x1800382b7  add     rsp, 0D0h
0x1800382be  pop     r15
0x1800382c0  pop     rdi
0x1800382c1  pop     rsi
0x1800382c2  retn
```
