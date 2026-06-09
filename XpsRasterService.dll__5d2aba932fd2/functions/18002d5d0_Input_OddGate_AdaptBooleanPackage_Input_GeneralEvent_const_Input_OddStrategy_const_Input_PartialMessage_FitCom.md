# Input::OddGate::AdaptBooleanPackage(Input::GeneralEvent const &,Input::OddStrategy const &,Input::PartialMessage::FitComprehensiveDefinition &)

- ea: `0x18002d5d0`
- end: `0x18002d9e7`
- name: `?AdaptBooleanPackage@OddGate@Input@@SAXAEBVGeneralEvent@2@AEBUOddStrategy@2@AEAUFitComprehensiveDefinition@PartialMessage@2@@Z`
- size: `1047`
- prototype: `void __fastcall(const struct Input::GeneralEvent *, const struct Input::OddStrategy *, struct Input::PartialMessage::FitComprehensiveDefinition *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d9f0`
- `0x18002db00`
- `0x180031d50`

## callees

- `0x180003c10`
- `0x180003c34`
- `0x180003c88`
- `0x18002d5d0`

## pseudocode

```c
void __fastcall Input::OddGate::AdaptBooleanPackage(
        const struct Input::GeneralEvent *a1,
        const struct Input::OddStrategy *a2,
        struct Input::PartialMessage::FitComprehensiveDefinition *a3)
{
  __int64 v3; // rdi
  __int64 v6; // r11
  float v7; // xmm11_4
  float v8; // xmm10_4
  int v9; // r8d
  int v10; // ecx
  int v11; // r12d
  int v12; // r9d
  __int64 v13; // rsi
  int v14; // edx
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // r15
  __int16 *v18; // rdi
  int v19; // ecx
  float v20; // xmm12_4
  float v21; // xmm13_4
  int v22; // eax
  float v23; // xmm15_4
  float v24; // xmm7_4
  float v25; // xmm2_4
  float v26; // xmm1_4
  float v27; // xmm7_4
  float v28; // xmm0_4
  float v29; // xmm1_4
  float v30; // xmm6_4
  float v31; // xmm7_4
  float v32; // xmm11_4
  float v33; // xmm0_4
  int v34; // ecx
  float v35; // xmm13_4
  int v36; // eax
  float v37; // xmm12_4
  float v38; // xmm10_4
  float v39; // xmm7_4
  float v40; // xmm2_4
  float v41; // xmm1_4
  float v42; // xmm7_4
  float v43; // xmm0_4
  float v44; // xmm1_4
  float v45; // xmm6_4
  float v46; // xmm7_4
  float v47; // xmm0_4

  v3 = *(int *)a2;
  if ( (unsigned int)(v3 + 64) > 0x7E || (v6 = *((int *)a2 + 1), (unsigned int)v6 > 0x3F) )
  {
    *((_BYTE *)a3 + 12) = 0;
    v47 = 0.0;
    v8 = 0.0;
    v7 = 0.0;
  }
  else
  {
    v7 = 0.0;
    v8 = 0.0;
    *((_BYTE *)a3 + 12) = 1;
    v9 = 63;
    v10 = 63;
    v11 = *((__int16 *)a2 + 6);
    v12 = (int)(float)((float)((float)*((unsigned __int16 *)a2 + 5) * 0.000030517578) * 64.0);
    if ( (int)(float)((float)((float)*((unsigned __int16 *)a2 + 4) * 0.000030517578) * 64.0) <= 63 )
      v10 = (int)(float)((float)((float)*((unsigned __int16 *)a2 + 4) * 0.000030517578) * 64.0);
    v13 = 0;
    v14 = 0;
    v15 = 0;
    if ( v10 > 0 )
      v14 = v10;
    v16 = v14;
    if ( v12 <= 63 )
      v9 = v12;
    if ( v9 > 0 )
      v15 = v9;
    v17 = v15;
    v18 = (__int16 *)((char *)a1 + 256 * v6 + 2 * v3 + 16770);
    do
    {
      v19 = *(v18 - 1);
      v20 = *(float *)&dword_1800C9480[v17 + v13];
      v21 = *(float *)&dword_1800C9680[v17 + v13];
      v22 = *(v18 - 8321);
      v23 = (float)v11;
      if ( *(v18 - 1) )
      {
        v25 = (float)v22 * 0.015625;
        LODWORD(v26) = COERCE_UNSIGNED_INT((float)v19 * 0.015625) & _xmm;
        if ( (v22 & 0x8000u) != 0 )
        {
          v27 = FLOAT_2_3561945;
          v28 = v26 + v25;
          v29 = v26 - v25;
        }
        else
        {
          v27 = FLOAT_0_78539819;
          v28 = v25 - v26;
          v29 = v26 + v25;
        }
        v24 = v27 - (float)((float)(v28 / v29) * 0.78539819);
        if ( (v19 & 0x8000u) != 0 )
          LODWORD(v24) ^= _xmm;
      }
      else if ( (v22 & 0x8000u) != 0 )
      {
        v24 = FLOAT_3_1415927;
      }
      else
      {
        v24 = 0.0;
      }
      v30 = (float)((float)(unsigned __int16)v18[8319] * 0.015625)
          * (float)(*(float *)&dword_1800C9680[v17 + v13] * *(float *)&dword_1800C9680[v16]);
      v31 = (float)((float)((float)(v24 / 6.2831855)
                          + (float)(*(float *)&dword_1800C9480[v17 + v13] + *(float *)&dword_1800C9480[v16]))
                  * v23)
          * 6.2831855;
      v32 = v7 + (float)(cosf(v31) * v30);
      v33 = o_sinf_0(v31);
      v34 = *v18;
      v35 = v21 * *(float *)&dword_1800C9780[v16];
      v36 = *(v18 - 8320);
      v37 = v20 + *(float *)&dword_1800C9580[v16];
      v38 = v8 + (float)(v33 * v30);
      if ( *v18 )
      {
        v40 = (float)v36 * 0.015625;
        LODWORD(v41) = COERCE_UNSIGNED_INT((float)v34 * 0.015625) & _xmm;
        if ( (v36 & 0x8000u) != 0 )
        {
          v42 = FLOAT_2_3561945;
          v43 = v41 + v40;
          v44 = v41 - v40;
        }
        else
        {
          v42 = FLOAT_0_78539819;
          v43 = v40 - v41;
          v44 = v41 + v40;
        }
        v39 = v42 - (float)((float)(v43 / v44) * 0.78539819);
        if ( (v34 & 0x8000u) != 0 )
          LODWORD(v39) ^= _xmm;
      }
      else if ( (v36 & 0x8000u) != 0 )
      {
        v39 = FLOAT_3_1415927;
      }
      else
      {
        v39 = 0.0;
      }
      v45 = (float)((float)(unsigned __int16)v18[8320] * 0.015625) * v35;
      v46 = (float)((float)((float)(v39 / 6.2831855) + v37) * v23) * 6.2831855;
      v7 = v32 + (float)(cosf(v46) * v45);
      v18 += 128;
      v13 += 64;
      v8 = v38 + (float)(o_sinf_0(v46) * v45);
    }
    while ( v13 < 128 );
    v47 = o_atan2f_0() / 6.2831855;
  }
  *(float *)a3 = v7;
  *((float *)a3 + 1) = v8;
  *((float *)a3 + 2) = v47;
}

```

## disassembly

```asm
0x18002d5d0  push    rbp
0x18002d5d2  push    rdi
0x18002d5d3  push    r14
0x18002d5d5  sub     rsp, 0D0h
0x18002d5dc  movsxd  rdi, dword ptr [rdx]
0x18002d5df  mov     r14, r8
0x18002d5e2  movaps  [rsp+0E8h+var_78], xmm10
0x18002d5e8  mov     r10, rdx
0x18002d5eb  movaps  [rsp+0E8h+var_88], xmm11
0x18002d5f1  mov     rbp, rcx
0x18002d5f4  lea     eax, [rdi+40h]
0x18002d5f7  cmp     eax, 7Eh ; '~'
0x18002d5fa  ja      loc_18002D9AE
0x18002d600  movsxd  r11, dword ptr [rdx+4]
0x18002d604  cmp     r11d, 3Fh ; '?'
0x18002d608  ja      loc_18002D9AE
0x18002d60e  mov     [rsp+0E8h+arg_0], rbx
0x18002d616  xorps   xmm11, xmm11
0x18002d61a  mov     [rsp+0E8h+arg_8], rsi
0x18002d622  xorps   xmm10, xmm10
0x18002d626  mov     [rsp+0E8h+arg_18], r12
0x18002d62e  mov     [rsp+0E8h+var_20], r13
0x18002d636  lea     r13, cs:180000000h
0x18002d63d  mov     [rsp+0E8h+var_28], r15
0x18002d645  mov     byte ptr [r8+0Ch], 1
0x18002d64a  mov     r8d, 3Fh ; '?'
0x18002d650  movzx   eax, word ptr [rdx+0Ah]
0x18002d654  mov     ecx, r8d
0x18002d657  movsx   r12d, word ptr [r10+0Ch]
0x18002d65c  movaps  [rsp+0E8h+var_38], xmm6
0x18002d664  movaps  [rsp+0E8h+var_48], xmm7
0x18002d66c  movd    xmm0, eax
0x18002d670  movzx   eax, word ptr [rdx+8]
0x18002d674  cvtdq2ps xmm0, xmm0
0x18002d677  movaps  [rsp+0E8h+var_58], xmm8
0x18002d680  mulss   xmm0, cs:__real@38000000
0x18002d688  movss   xmm8, cs:__real@3f490fdb
0x18002d691  movaps  [rsp+0E8h+var_68], xmm9
0x18002d69a  mulss   xmm0, cs:__real@42800000
0x18002d6a2  movss   xmm9, cs:__real@3c800000
0x18002d6ab  movaps  [rsp+0E8h+var_98], xmm12
0x18002d6b1  cvttss2si r9d, xmm0
0x18002d6b6  movd    xmm0, eax
0x18002d6ba  cvtdq2ps xmm0, xmm0
0x18002d6bd  movaps  [rsp+0E8h+var_A8], xmm13
0x18002d6c3  mulss   xmm0, cs:__real@38000000
0x18002d6cb  movaps  [rsp+0E8h+var_B8], xmm14
0x18002d6d1  movss   xmm14, cs:__real@40c90fdb
0x18002d6da  mulss   xmm0, cs:__real@42800000
0x18002d6e2  movaps  [rsp+0E8h+var_C8], xmm15
0x18002d6e8  cvttss2si eax, xmm0
0x18002d6ec  cmp     eax, ecx
0x18002d6ee  cmovle  ecx, eax
0x18002d6f1  xor     esi, esi
0x18002d6f3  test    ecx, ecx
0x18002d6f5  mov     edx, esi
0x18002d6f7  mov     eax, esi
0x18002d6f9  cmovg   edx, ecx
0x18002d6fc  cmp     r9d, r8d
0x18002d6ff  mov     rcx, r11
0x18002d702  movsxd  rbx, edx
0x18002d705  cmovle  r8d, r9d
0x18002d709  test    r8d, r8d
0x18002d70c  cmovg   eax, r8d
0x18002d710  shl     rcx, 7
0x18002d714  add     rcx, rdi
0x18002d717  movsxd  r15, eax
0x18002d71a  lea     rdi, [rbp+4182h]
0x18002d721  lea     rdi, [rdi+rcx*2]
0x18002d725  movsx   ecx, word ptr [rdi-2]
0x18002d729  lea     rax, [rsi+r15*4]
0x18002d72d  movss   xmm12, dword ptr [rax+r13+0C9480h]
0x18002d737  lea     rax, [rsi+r15*4]
0x18002d73b  movss   xmm13, dword ptr [rax+r13+0C9680h]
0x18002d745  movaps  xmm3, xmm12
0x18002d749  movsx   eax, word ptr [rdi-4102h]
0x18002d750  movaps  xmm4, xmm13
0x18002d754  mulss   xmm4, ds:rva dword_1800C9680[r13+rbx*4]
0x18002d75e  movd    xmm15, r12d
0x18002d763  addss   xmm3, ds:rva dword_1800C9480[r13+rbx*4]
0x18002d76d  cvtdq2ps xmm15, xmm15
0x18002d771  test    cx, cx
0x18002d774  jnz     short loc_18002D78A
0x18002d776  test    ax, ax
0x18002d779  js      short loc_18002D780
0x18002d77b  xorps   xmm7, xmm7
0x18002d77e  jmp     short loc_18002D7EB
0x18002d780  movss   xmm7, cs:__real@40490fdb
0x18002d788  jmp     short loc_18002D7EB
0x18002d78a  movd    xmm1, ecx
0x18002d78e  movd    xmm2, eax
0x18002d792  cvtdq2ps xmm1, xmm1
0x18002d795  cvtdq2ps xmm2, xmm2
0x18002d798  mulss   xmm1, xmm9
0x18002d79d  mulss   xmm2, xmm9
0x18002d7a2  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18002d7a9  test    ax, ax
0x18002d7ac  js      short loc_18002D7BF
0x18002d7ae  movaps  xmm0, xmm2
0x18002d7b1  movaps  xmm7, xmm8
0x18002d7b5  subss   xmm0, xmm1
0x18002d7b9  addss   xmm1, xmm2
0x18002d7bd  jmp     short loc_18002D7D2
0x18002d7bf  movss   xmm7, cs:__real@4016cbe4
0x18002d7c7  movaps  xmm0, xmm1
0x18002d7ca  addss   xmm0, xmm2
0x18002d7ce  subss   xmm1, xmm2
0x18002d7d2  divss   xmm0, xmm1
0x18002d7d6  mulss   xmm0, xmm8
0x18002d7db  subss   xmm7, xmm0
0x18002d7df  test    cx, cx
0x18002d7e2  jns     short loc_18002D7EB
0x18002d7e4  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x18002d7eb  movzx   eax, word ptr [rdi+40FEh]
0x18002d7f2  xorps   xmm6, xmm6
0x18002d7f5  divss   xmm7, xmm14
0x18002d7fa  cvtsi2ss xmm6, eax
0x18002d7fe  addss   xmm7, xmm3
0x18002d802  mulss   xmm6, xmm9
0x18002d807  mulss   xmm7, xmm15
0x18002d80c  mulss   xmm6, xmm4
0x18002d810  mulss   xmm7, xmm14
0x18002d815  movaps  xmm0, xmm7; X
0x18002d818  call    cosf
0x18002d81d  mulss   xmm0, xmm6
0x18002d821  addss   xmm11, xmm0
0x18002d826  movaps  xmm0, xmm7; X
0x18002d829  call    _o_sinf_0
0x18002d82e  movsx   ecx, word ptr [rdi]
0x18002d831  mulss   xmm13, ds:rva dword_1800C9780[r13+rbx*4]
0x18002d83b  movsx   eax, word ptr [rdi-4100h]
0x18002d842  mulss   xmm0, xmm6
0x18002d846  addss   xmm12, ds:rva dword_1800C9580[r13+rbx*4]
0x18002d850  addss   xmm10, xmm0
0x18002d855  test    cx, cx
0x18002d858  jnz     short loc_18002D86E
0x18002d85a  test    ax, ax
0x18002d85d  js      short loc_18002D864
0x18002d85f  xorps   xmm7, xmm7
0x18002d862  jmp     short loc_18002D8CF
0x18002d864  movss   xmm7, cs:__real@40490fdb
0x18002d86c  jmp     short loc_18002D8CF
0x18002d86e  movd    xmm1, ecx
0x18002d872  movd    xmm2, eax
0x18002d876  cvtdq2ps xmm1, xmm1
0x18002d879  cvtdq2ps xmm2, xmm2
0x18002d87c  mulss   xmm1, xmm9
0x18002d881  mulss   xmm2, xmm9
0x18002d886  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18002d88d  test    ax, ax
0x18002d890  js      short loc_18002D8A3
0x18002d892  movaps  xmm0, xmm2
0x18002d895  movaps  xmm7, xmm8
0x18002d899  subss   xmm0, xmm1
0x18002d89d  addss   xmm1, xmm2
0x18002d8a1  jmp     short loc_18002D8B6
0x18002d8a3  movss   xmm7, cs:__real@4016cbe4
0x18002d8ab  movaps  xmm0, xmm1
0x18002d8ae  addss   xmm0, xmm2
0x18002d8b2  subss   xmm1, xmm2
0x18002d8b6  divss   xmm0, xmm1
0x18002d8ba  mulss   xmm0, xmm8
0x18002d8bf  subss   xmm7, xmm0
0x18002d8c3  test    cx, cx
0x18002d8c6  jns     short loc_18002D8CF
0x18002d8c8  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x18002d8cf  movzx   eax, word ptr [rdi+4100h]
0x18002d8d6  xorps   xmm6, xmm6
0x18002d8d9  divss   xmm7, xmm14
0x18002d8de  cvtsi2ss xmm6, eax
0x18002d8e2  addss   xmm7, xmm12
0x18002d8e7  mulss   xmm6, xmm9
0x18002d8ec  mulss   xmm7, xmm15
0x18002d8f1  mulss   xmm6, xmm13
0x18002d8f6  mulss   xmm7, xmm14
0x18002d8fb  movaps  xmm0, xmm7; X
0x18002d8fe  call    cosf
0x18002d903  mulss   xmm0, xmm6
0x18002d907  addss   xmm11, xmm0
0x18002d90c  movaps  xmm0, xmm7; X
0x18002d90f  call    _o_sinf_0
0x18002d914  mulss   xmm0, xmm6
0x18002d918  add     rdi, 100h
0x18002d91f  add     rsi, 100h
0x18002d926  addss   xmm10, xmm0
0x18002d92b  cmp     rsi, 200h
0x18002d932  jl      loc_18002D725
0x18002d938  movaps  xmm1, xmm11
0x18002d93c  movaps  xmm0, xmm10
0x18002d940  call    _o_atan2f_0
0x18002d945  movaps  xmm15, [rsp+0E8h+var_C8]
0x18002d94b  movaps  xmm13, [rsp+0E8h+var_A8]
0x18002d951  movaps  xmm12, [rsp+0E8h+var_98]
0x18002d957  movaps  xmm9, [rsp+0E8h+var_68]
0x18002d960  movaps  xmm8, [rsp+0E8h+var_58]
0x18002d969  movaps  xmm7, [rsp+0E8h+var_48]
0x18002d971  movaps  xmm6, [rsp+0E8h+var_38]
0x18002d979  mov     r15, [rsp+0E8h+var_28]
0x18002d981  mov     r13, [rsp+0E8h+var_20]
0x18002d989  mov     r12, [rsp+0E8h+arg_18]
0x18002d991  mov     rsi, [rsp+0E8h+arg_8]
0x18002d999  mov     rbx, [rsp+0E8h+arg_0]
0x18002d9a1  divss   xmm0, xmm14
0x18002d9a6  movaps  xmm14, [rsp+0E8h+var_B8]
0x18002d9ac  jmp     short loc_18002D9BE
0x18002d9ae  mov     byte ptr [r8+0Ch], 0
0x18002d9b3  xorps   xmm0, xmm0
0x18002d9b6  xorps   xmm10, xmm10
0x18002d9ba  xorps   xmm11, xmm11
0x18002d9be  movss   dword ptr [r14], xmm11
0x18002d9c3  movss   dword ptr [r14+4], xmm10
0x18002d9c9  movss   dword ptr [r14+8], xmm0
0x18002d9cf  movaps  xmm10, [rsp+0E8h+var_78]
0x18002d9d5  movaps  xmm11, [rsp+0E8h+var_88]
0x18002d9db  add     rsp, 0D0h
0x18002d9e2  pop     r14
0x18002d9e4  pop     rdi
0x18002d9e5  pop     rbp
0x18002d9e6  retn
```
