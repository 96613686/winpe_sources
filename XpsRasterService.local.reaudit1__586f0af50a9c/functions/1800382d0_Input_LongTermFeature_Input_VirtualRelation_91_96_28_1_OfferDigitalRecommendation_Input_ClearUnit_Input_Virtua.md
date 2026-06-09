# Input::LongTermFeature<Input::VirtualRelation<91,96,28,1>>::OfferDigitalRecommendation(Input::ClearUnit &,Input::VirtualRelation<91,96,28,1> &)

- ea: `0x1800382d0`
- end: `0x1800386e3`
- name: `?OfferDigitalRecommendation@?$LongTermFeature@V?$VirtualRelation@$0FL@$0GA@$0BM@$00@Input@@@Input@@SAXAEAVClearUnit@2@AEAV?$VirtualRelation@$0FL@$0GA@$0BM@$00@2@@Z`
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
- `0x1800382d0`

## pseudocode

```c
unsigned __int64 __fastcall Input::LongTermFeature<Input::VirtualRelation<91,96,28,1>>::OfferDigitalRecommendation(
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
      v9 = _mm_shuffle_ps(v7, v7, 85).m128_f32[0] + 48.0;
      v10 = (float)((float)(v8 + 0.0) * 90.0) / 90.0;
      v11 = (float)((float)((float)((float)((float)(v10 * 0.000001017) * v10) * v10)
                          + (float)((float)(v10 * 0.000042750002) * v10))
                  + (float)(v10 * 0.008525))
          + 0.43643188;
      if ( v9 >= 96.0 )
        v9 = v9 + -96.0;
      if ( v9 < 0.0 )
        v9 = v9 + 96.0;
      v12 = v9 * 0.016362462;
      v13 = cosf(v12) * v11;
      v14 = o_sinf_0(v12) * v11;
      v15 = (float *)&Input::VirtualRelation<91,96,28,1>::TemporaryInstruction[2 * v36.m128_i32[3]];
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
0x1800382d0  mov     r11, rsp
0x1800382d3  push    rsi
0x1800382d4  push    rdi
0x1800382d5  push    r15
0x1800382d7  sub     rsp, 0D0h
0x1800382de  mov     eax, [rcx+1DD0h]
0x1800382e4  mov     edi, 8
0x1800382e9  cmp     eax, edi
0x1800382eb  mov     r15, rcx
0x1800382ee  cmovg   eax, edi
0x1800382f1  movsxd  rsi, eax
0x1800382f4  test    eax, eax
0x1800382f6  jle     loc_1800385D9
0x1800382fc  mov     [r11+8], rbx
0x180038300  lea     rbx, [rcx+2]
0x180038304  mov     [r11+10h], rbp
0x180038308  lea     rbp, [rcx+1D48h]
0x18003830f  mov     [r11+18h], r12
0x180038313  lea     r12, ?TemporaryInstruction@?$VirtualRelation@$0FL@$0GA@$0BM@$00@Input@@0V?$StripedCategory@V?$StripedCategory@M$03@Data@@$00@Data@@B; Data::StripedCategory<Data::StripedCategory<float,4>,1> const Input::VirtualRelation<91,96,28,1>::TemporaryInstruction
0x18003831a  mov     [r11+20h], r14
0x18003831e  mov     r14, rsi
0x180038321  movaps  xmmword ptr [r11-28h], xmm6
0x180038326  movaps  xmmword ptr [r11-38h], xmm7
0x18003832b  movaps  xmmword ptr [r11-48h], xmm8
0x180038330  movaps  xmmword ptr [r11-58h], xmm9
0x180038335  xorps   xmm9, xmm9
0x180038339  movaps  xmmword ptr [r11-68h], xmm10
0x18003833e  movss   xmm10, cs:__real@bf000000
0x180038347  movaps  xmmword ptr [r11-78h], xmm11
0x18003834c  movss   xmm11, cs:__real@3f000000
0x180038355  movaps  [rsp+0E8h+var_88], xmm12
0x18003835b  movss   xmm12, cs:__real@45000000
0x180038364  movaps  [rsp+0E8h+var_98], xmm13
0x18003836a  movss   xmm13, cs:__real@42c00000
0x180038373  movaps  [rsp+0E8h+var_A8], xmm14
0x180038379  movss   xmm14, cs:__real@42b40000
0x180038382  movaps  [rsp+0E8h+var_B8], xmm15
0x180038388  movss   xmm15, cs:__real@c2c00000
0x180038391  nop     dword ptr [rax+00h]
0x180038395  nop     word ptr [rax+rax+00000000h]
0x1800383a0  movups  xmm7, xmmword ptr [rbp+0]
0x1800383a4  movaps  xmm1, xmm7
0x1800383a7  shufps  xmm1, xmm7, 0AAh
0x1800383ab  addss   xmm1, xmm9
0x1800383b0  movups  [rsp+0E8h+var_C8], xmm7
0x1800383b5  shufps  xmm7, xmm7, 55h ; 'U'
0x1800383b9  addss   xmm7, cs:__real@42400000
0x1800383c1  mulss   xmm1, xmm14
0x1800383c6  comiss  xmm7, xmm13
0x1800383ca  divss   xmm1, xmm14
0x1800383cf  movaps  xmm8, xmm1
0x1800383d3  movaps  xmm0, xmm1
0x1800383d6  mulss   xmm8, cs:__real@35887fdb
0x1800383df  mulss   xmm0, cs:__real@38334e77
0x1800383e7  mulss   xmm8, xmm1
0x1800383ec  mulss   xmm0, xmm1
0x1800383f0  mulss   xmm8, xmm1
0x1800383f5  mulss   xmm1, cs:__real@3c0bac71
0x1800383fd  addss   xmm8, xmm0
0x180038402  addss   xmm8, xmm1
0x180038407  addss   xmm8, cs:__real@3edf7400
0x180038410  jb      short loc_180038417
0x180038412  addss   xmm7, xmm15
0x180038417  comiss  xmm9, xmm7
0x18003841b  jbe     short loc_180038422
0x18003841d  addss   xmm7, xmm13
0x180038422  mulss   xmm7, cs:__real@3c860a92
0x18003842a  movaps  xmm0, xmm7; X
0x18003842d  call    cosf
0x180038432  movaps  xmm6, xmm0
0x180038435  movaps  xmm0, xmm7; X
0x180038438  mulss   xmm6, xmm8
0x18003843d  call    _o_sinf_0
0x180038442  mov     r9, qword ptr [rsp+0E8h+var_C8+8]
0x180038447  movaps  xmm3, xmm0
0x18003844a  mulss   xmm3, xmm8
0x18003844f  shr     r9, 20h
0x180038453  movsxd  rax, r9d
0x180038456  shl     rax, 4
0x18003845a  add     rax, r12
0x18003845d  movaps  xmm4, xmm3
0x180038460  mulss   xmm4, cs:__real@bf800000
0x180038468  movss   xmm1, dword ptr [rax]
0x18003846c  movss   xmm5, dword ptr [rax+4]
0x180038471  movaps  xmm0, xmm1
0x180038474  movss   xmm2, dword ptr [rax+8]
0x180038479  movaps  xmm7, xmm4
0x18003847c  movss   xmm8, dword ptr [rax+0Ch]
0x180038482  movzx   eax, word ptr [rsp+0E8h+var_C8]
0x180038487  mulss   xmm0, xmm6
0x18003848b  mulss   xmm4, xmm8
0x180038490  mulss   xmm7, xmm5
0x180038494  mulss   xmm8, xmm6
0x180038499  addss   xmm7, xmm0
0x18003849d  mulss   xmm5, xmm6
0x1800384a1  movaps  xmm0, xmm2
0x1800384a4  mulss   xmm1, xmm3
0x1800384a8  mulss   xmm0, xmm6
0x1800384ac  mulss   xmm2, xmm3
0x1800384b0  addss   xmm5, xmm1
0x1800384b4  addss   xmm4, xmm0
0x1800384b8  xorps   xmm0, xmm0
0x1800384bb  cvtsi2ss xmm0, eax
0x1800384bf  addss   xmm8, xmm2
0x1800384c4  mulss   xmm0, cs:__real@3c000000
0x1800384cc  mulss   xmm8, xmm12
0x1800384d1  movss   dword ptr [rbx+0Eh], xmm0
0x1800384d6  comiss  xmm9, xmm8
0x1800384da  jbe     short loc_1800384E2
0x1800384dc  movaps  xmm0, xmm10
0x1800384e0  jmp     short loc_1800384E6
0x1800384e2  movaps  xmm0, xmm11
0x1800384e6  addss   xmm0, xmm8
0x1800384eb  mulss   xmm4, xmm12
0x1800384f0  comiss  xmm9, xmm4
0x1800384f4  cvttss2si r8d, xmm0
0x1800384f9  jbe     short loc_180038501
0x1800384fb  movaps  xmm0, xmm10
0x1800384ff  jmp     short loc_180038505
0x180038501  movaps  xmm0, xmm11
0x180038505  addss   xmm0, xmm4
0x180038509  mulss   xmm5, xmm12
0x18003850e  comiss  xmm9, xmm5
0x180038512  cvttss2si edx, xmm0
0x180038516  jbe     short loc_18003851E
0x180038518  movaps  xmm0, xmm10
0x18003851c  jmp     short loc_180038522
0x18003851e  movaps  xmm0, xmm11
0x180038522  addss   xmm0, xmm5
0x180038526  mulss   xmm7, xmm12
0x18003852b  comiss  xmm9, xmm7
0x18003852f  cvttss2si ecx, xmm0
0x180038533  jbe     short loc_18003853B
0x180038535  movaps  xmm0, xmm10
0x180038539  jmp     short loc_18003853F
0x18003853b  movaps  xmm0, xmm11
0x18003853f  mov     [rbx], cx
0x180038542  addss   xmm0, xmm7
0x180038546  mov     [rbx+2], dx
0x18003854a  add     rbp, 10h
0x18003854e  mov     [rbx+4], r8w
0x180038553  cvttss2si eax, xmm0
0x180038557  mov     [rbx-2], ax
0x18003855b  mov     [rbx+1Ah], r9d
0x18003855f  add     rbx, 3A0h
0x180038566  sub     r14, 1
0x18003856a  jnz     loc_1800383A0
0x180038570  movaps  xmm15, [rsp+0E8h+var_B8]
0x180038576  movaps  xmm14, [rsp+0E8h+var_A8]
0x18003857c  movaps  xmm13, [rsp+0E8h+var_98]
0x180038582  movaps  xmm12, [rsp+0E8h+var_88]
0x180038588  movaps  xmm11, [rsp+0E8h+var_78]
0x18003858e  movaps  xmm10, [rsp+0E8h+var_68]
0x180038597  movaps  xmm9, [rsp+0E8h+var_58]
0x1800385a0  movaps  xmm8, [rsp+0E8h+var_48]
0x1800385a9  movaps  xmm7, [rsp+0E8h+var_38]
0x1800385b1  movaps  xmm6, [rsp+0E8h+var_28]
0x1800385b9  mov     r14, [rsp+0E8h+arg_18]
0x1800385c1  mov     r12, [rsp+0E8h+arg_10]
0x1800385c9  mov     rbp, [rsp+0E8h+arg_8]
0x1800385d1  mov     rbx, [rsp+0E8h+arg_0]
0x1800385d9  cmp     rsi, rdi
0x1800385dc  jge     loc_1800386D7
0x1800385e2  mov     rax, rdi
0x1800385e5  xor     edx, edx
0x1800385e7  sub     rax, rsi
0x1800385ea  cmp     rax, 4
0x1800385ee  jl      loc_1800386A5
0x1800385f4  imul    rcx, rsi, 3A0h
0x1800385fb  mov     eax, 4
0x180038600  sub     rax, rsi
0x180038603  add     rcx, 3A4h
0x18003860a  add     rcx, r15
0x18003860d  shr     rax, 2
0x180038611  inc     rax
0x180038614  lea     rsi, [rsi+rax*4]
0x180038618  nop     dword ptr [rax+rax+00000000h]
0x180038620  mov     [rcx-394h], edx
0x180038626  mov     dword ptr [rcx-3A4h], 800h
0x180038630  mov     dword ptr [rcx-3A0h], 8000000h
0x18003863a  mov     [rcx-388h], edx
0x180038640  mov     [rcx+0Ch], edx
0x180038643  mov     dword ptr [rcx-4], 800h
0x18003864a  mov     dword ptr [rcx], 8000000h
0x180038650  mov     [rcx+18h], edx
0x180038653  mov     [rcx+3ACh], edx
0x180038659  mov     dword ptr [rcx+39Ch], 800h
0x180038663  mov     dword ptr [rcx+3A0h], 8000000h
0x18003866d  mov     [rcx+3B8h], edx
0x180038673  mov     [rcx+74Ch], edx
0x180038679  mov     dword ptr [rcx+73Ch], 800h
0x180038683  mov     dword ptr [rcx+740h], 8000000h
0x18003868d  mov     [rcx+758h], edx
0x180038693  lea     rcx, [rcx+0E80h]
0x18003869a  sub     rax, 1
0x18003869e  jnz     short loc_180038620
0x1800386a0  cmp     rsi, rdi
0x1800386a3  jge     short loc_1800386D7
0x1800386a5  imul    rcx, rsi, 3A0h
0x1800386ac  add     rcx, 2
0x1800386b0  add     rcx, r15
0x1800386b3  sub     rdi, rsi
0x1800386b6  mov     [rcx+0Eh], edx
0x1800386b9  mov     dword ptr [rcx-2], 800h
0x1800386c0  mov     dword ptr [rcx+2], 8000000h
0x1800386c7  mov     [rcx+1Ah], edx
0x1800386ca  lea     rcx, [rcx+3A0h]
0x1800386d1  sub     rdi, 1
0x1800386d5  jnz     short loc_1800386B6
0x1800386d7  add     rsp, 0D0h
0x1800386de  pop     r15
0x1800386e0  pop     rdi
0x1800386e1  pop     rsi
0x1800386e2  retn
```
