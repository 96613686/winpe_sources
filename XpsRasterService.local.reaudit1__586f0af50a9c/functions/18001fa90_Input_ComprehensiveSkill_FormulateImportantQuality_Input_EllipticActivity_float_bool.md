# Input::ComprehensiveSkill::FormulateImportantQuality(Input::EllipticActivity &,float,bool)

- ea: `0x18001fa90`
- end: `0x1800203b8`
- name: `?FormulateImportantQuality@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@M_N@Z`
- size: `2344`
- prototype: `void __fastcall(Input::ComprehensiveSkill *__hidden this, struct Input::EllipticActivity *, float, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800232f0`

## callees

- `0x180003ca0`
- `0x18001fa90`

## pseudocode

```c
void __fastcall Input::ComprehensiveSkill::FormulateImportantQuality(
        Input::ComprehensiveSkill *this,
        struct Input::EllipticActivity *a2,
        float a3,
        char a4)
{
  char *v5; // rbx
  __int64 i; // rsi
  float v7; // xmm6_4
  float *v8; // r8
  __int64 v9; // rcx
  float *v10; // rdx
  float v11; // xmm1_4
  float v12; // xmm6_4
  float v13; // xmm6_4
  float v14; // xmm1_4
  float v15; // xmm0_4
  int v16; // eax
  float v17; // xmm6_4
  float v18; // xmm0_4
  float v19; // xmm1_4
  float v20; // xmm3_4
  __int64 v21; // rax
  float v22; // xmm1_4
  float v23; // xmm3_4
  float v24; // xmm1_4
  float v25; // xmm3_4
  float v26; // xmm0_4
  float v27; // xmm3_4
  float v28; // xmm1_4
  float v29; // xmm2_4
  float *v30; // rcx
  __int64 v31; // rdx
  float v32; // xmm2_4
  float v33; // xmm1_4
  float v34; // xmm0_4
  int v35; // eax
  float v36; // xmm2_4
  float v37; // xmm0_4
  float v38; // xmm1_4
  float v39; // xmm6_4
  float v40; // xmm3_4
  float *v41; // rax
  __int64 v42; // rcx
  float v43; // xmm6_4
  float v44; // xmm0_4
  float v45; // xmm3_4
  float v46; // xmm1_4
  float v47; // xmm0_4
  float v48; // xmm6_4

  if ( a3 > 49.0 || a4 )
  {
    v5 = byte_1800D42A1;
    for ( i = 0; ; i += 4 )
    {
      v7 = 0.0;
      v8 = (float *)((char *)a2 + i + 8);
      v9 = 0;
      v10 = v8;
      do
      {
        v11 = (float)((float)byte_1800D4251[v9 - 1] * *(v10 - 2)) + v7;
        v12 = (float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)(v11 + (float)((float)byte_1800D4251[v9] * *(v10 - 1))) + (float)((float)byte_1800D4251[v9 + 1] * *v10)) + (float)((float)byte_1800D4251[v9 + 2] * v10[1]))
                                                                                            + (float)((float)byte_1800D4251[v9 + 3] * v10[2]))
                                                                                    + (float)((float)byte_1800D4251[v9 + 4]
                                                                                            * v10[3]))
                                                                            + (float)((float)byte_1800D4251[v9 + 5]
                                                                                    * v10[4]))
                                                                    + (float)((float)byte_1800D4251[v9 + 6] * v10[5]))
                                                            + (float)((float)byte_1800D4251[v9 + 7] * v10[6]))
                                                    + (float)((float)byte_1800D4251[v9 + 8] * v10[7]))
                                            + (float)((float)byte_1800D4251[v9 + 9] * v10[8]))
                                    + (float)((float)byte_1800D4251[v9 + 10] * v10[9]))
                            + (float)((float)byte_1800D4251[v9 + 11] * v10[10]))
                    + (float)((float)byte_1800D4251[v9 + 12] * v10[11]))
            + (float)((float)byte_1800D4251[v9 + 13] * v10[12]);
        v13 = (float)((float)((float)((float)((float)((float)(v12 + (float)((float)byte_1800D4251[v9 + 14] * v10[13]))
                                                    + (float)((float)byte_1800D4251[v9 + 15] * v10[14]))
                                            + (float)((float)byte_1800D4251[v9 + 16] * v10[15]))
                                    + (float)((float)byte_1800D4251[v9 + 17] * v10[16]))
                            + (float)((float)byte_1800D4251[v9 + 18] * v10[17]))
                    + (float)((float)byte_1800D4251[v9 + 19] * v10[18]))
            + (float)((float)byte_1800D4251[v9 + 20] * v10[19]);
        v14 = (float)byte_1800D4251[v9 + 21] * v10[20];
        v15 = (float)byte_1800D4251[v9 + 22];
        v16 = byte_1800D4251[v9 + 23];
        v9 += 25;
        v17 = v13 + v14;
        v18 = v15 * v10[21];
        v19 = (float)v16 * v10[22];
        v10 += 25;
        v7 = (float)(v17 + v18) + v19;
      }
      while ( v9 < 75 );
      v20 = 0.0;
      v21 = 2;
      do
      {
        v22 = v8[19] * v8[19];
        v23 = (float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)(v20 + (float)(*(v8 - 2) * *(v8 - 2))) + (float)(*(v8 - 1) * *(v8 - 1))) + (float)(*v8 * *v8)) + (float)(v8[1] * v8[1])) + (float)(v8[2] * v8[2])) + (float)(v8[3] * v8[3])) + (float)(v8[4] * v8[4])) + (float)(v8[5] * v8[5])) + (float)(v8[6] * v8[6])) + (float)(v8[7] * v8[7])) + (float)(v8[8] * v8[8]))
                                                                                            + (float)(v8[9] * v8[9]))
                                                                                    + (float)(v8[10] * v8[10]))
                                                                            + (float)(v8[11] * v8[11]))
                                                                    + (float)(v8[12] * v8[12]))
                                                            + (float)(v8[13] * v8[13]))
                                                    + (float)(v8[14] * v8[14]))
                                            + (float)(v8[15] * v8[15]))
                                    + (float)(v8[16] * v8[16]))
                            + (float)(v8[17] * v8[17]))
                    + (float)(v8[18] * v8[18]))
            + v22;
        v24 = v8[41] * v8[41];
        v25 = (float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)(v23 + (float)(v8[20] * v8[20])) + (float)(v8[21] * v8[21])) + (float)(v8[22] * v8[22])) + (float)(v8[23] * v8[23])) + (float)(v8[24] * v8[24])) + (float)(v8[25] * v8[25])) + (float)(v8[26] * v8[26])) + (float)(v8[27] * v8[27])) + (float)(v8[28] * v8[28])) + (float)(v8[29] * v8[29])) + (float)(v8[30] * v8[30]))
                                                                                            + (float)(v8[31] * v8[31]))
                                                                                    + (float)(v8[32] * v8[32]))
                                                                            + (float)(v8[33] * v8[33]))
                                                                    + (float)(v8[34] * v8[34]))
                                                            + (float)(v8[35] * v8[35]))
                                                    + (float)(v8[36] * v8[36]))
                                            + (float)(v8[37] * v8[37]))
                                    + (float)(v8[38] * v8[38]))
                            + (float)(v8[39] * v8[39]))
                    + (float)(v8[40] * v8[40]))
            + v24;
        v26 = v8[56] * v8[56];
        v27 = (float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)(v25 + (float)(v8[42] * v8[42])) + (float)(v8[43] * v8[43])) + (float)(v8[44] * v8[44]))
                                                                                            + (float)(v8[45] * v8[45]))
                                                                                    + (float)(v8[46] * v8[46]))
                                                                            + (float)(v8[47] * v8[47]))
                                                                    + (float)(v8[48] * v8[48]))
                                                            + (float)(v8[49] * v8[49]))
                                                    + (float)(v8[50] * v8[50]))
                                            + (float)(v8[51] * v8[51]))
                                    + (float)(v8[52] * v8[52]))
                            + (float)(v8[53] * v8[53]))
                    + (float)(v8[54] * v8[54]))
            + (float)(v8[55] * v8[55]);
        v28 = v8[57] * v8[57];
        v8 += 60;
        v20 = (float)(v27 + v26) + v28;
        --v21;
      }
      while ( v21 );
      v29 = 0.0;
      v30 = (float *)((char *)a2 + 308);
      v31 = 3;
      do
      {
        v32 = (float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)((float)*(v5 - 1) * *(v30 - 2)) + v29)
                                                                                            + (float)((float)*v5 * *(v30 - 1)))
                                                                                    + (float)((float)v5[1] * *v30))
                                                                            + (float)((float)v5[2] * v30[1]))
                                                                    + (float)((float)v5[3] * v30[2]))
                                                            + (float)((float)v5[4] * v30[3]))
                                                    + (float)((float)v5[5] * v30[4]))
                                            + (float)((float)v5[6] * v30[5]))
                                    + (float)((float)v5[7] * v30[6]))
                            + (float)((float)v5[8] * v30[7]))
                    + (float)((float)v5[9] * v30[8]))
            + (float)((float)v5[10] * v30[9]);
        v33 = (float)v5[11] * v30[10];
        v34 = (float)v5[12];
        v35 = v5[13];
        v5 += 15;
        v36 = v32 + v33;
        v37 = v34 * v30[11];
        v38 = (float)v35 * v30[12];
        v30 += 15;
        v29 = (float)(v36 + v37) + v38;
        --v31;
      }
      while ( v31 );
      v39 = v7 + v20;
      v40 = 0.0;
      v41 = (float *)((char *)a2 + 8);
      v42 = 27;
      v43 = v39 + v29;
      do
      {
        v44 = v41[6] * v41[6];
        v45 = (float)((float)((float)((float)((float)((float)((float)(v40 + (float)(*(v41 - 2) * *(v41 - 2)))
                                                            + (float)(*(v41 - 1) * *(v41 - 1)))
                                                    + (float)(*v41 * *v41))
                                            + (float)(v41[1] * v41[1]))
                                    + (float)(v41[2] * v41[2]))
                            + (float)(v41[3] * v41[3]))
                    + (float)(v41[4] * v41[4]))
            + (float)(v41[5] * v41[5]);
        v46 = v41[7] * v41[7];
        v41 += 10;
        v40 = (float)(v45 + v44) + v46;
        --v42;
      }
      while ( v42 );
      if ( v40 == 0.0 )
        break;
      if ( v40 < 0.0 )
        v47 = o_sqrtf_0(v40);
      else
        v47 = fsqrt(v40);
      v48 = v43 / v47;
      if ( v48 > 0.0 )
        goto LABEL_21;
      if ( (__int64)v5 >= (__int64)&word_1800D4706 )
        return;
    }
    v48 = FLOAT_1_1754944eN38;
LABEL_21:
    *((float *)a2 + 278) = v48 / 2.5;
    *((float *)a2 + 276) = v48 / 3.0;
  }
  else
  {
    *(_QWORD *)((char *)a2 + 1124) = -1;
    *((_QWORD *)a2 + 138) = 0;
    *((_QWORD *)a2 + 139) = 0;
    *((_DWORD *)a2 + 280) = 0;
  }
}

```

## disassembly

```asm
0x18001fa90  push    rbp
0x18001fa92  push    rdi
0x18001fa93  sub     rsp, 58h
0x18001fa97  comiss  xmm2, cs:__real@42440000
0x18001fa9e  mov     rdi, rdx
0x18001faa1  ja      short loc_18001FAD0
0x18001faa3  test    r9b, r9b
0x18001faa6  jnz     short loc_18001FAD0
0x18001faa8  xor     ebp, ebp
0x18001faaa  mov     qword ptr [rdx+464h], 0FFFFFFFFFFFFFFFFh
0x18001fab5  mov     [rdx+450h], rbp
0x18001fabc  mov     [rdx+458h], rbp
0x18001fac3  mov     [rdx+460h], ebp
0x18001fac9  add     rsp, 58h
0x18001facd  pop     rdi
0x18001face  pop     rbp
0x18001facf  retn
0x18001fad0  mov     [rsp+68h+arg_0], rbx
0x18001fad5  xor     ebp, ebp
0x18001fad7  mov     [rsp+68h+arg_10], rsi
0x18001fadf  lea     rbx, byte_1800D42A1
0x18001fae6  mov     [rsp+68h+arg_18], r12
0x18001faee  mov     esi, ebp
0x18001faf0  mov     [rsp+68h+var_18], r13
0x18001faf5  lea     r12, byte_1800D4251
0x18001fafc  mov     [rsp+68h+var_20], r14
0x18001fb01  lea     r13, word_1800D4706
0x18001fb08  mov     [rsp+68h+var_28], r15
0x18001fb0d  movaps  [rsp+68h+var_38], xmm6
0x18001fb12  movaps  [rsp+68h+var_48], xmm7
0x18001fb17  xorps   xmm7, xmm7
0x18001fb1a  nop     word ptr [rax+rax+00h]
0x18001fb20  lea     r8, [rdi+8]
0x18001fb24  movaps  xmm6, xmm7
0x18001fb27  add     r8, rsi
0x18001fb2a  mov     rcx, rbp
0x18001fb2d  mov     rdx, r8
0x18001fb30  movsx   eax, byte ptr [rcx+r12-1]
0x18001fb36  xorps   xmm1, xmm1
0x18001fb39  xorps   xmm0, xmm0
0x18001fb3c  cvtsi2ss xmm1, eax
0x18001fb40  movsx   eax, byte ptr [rcx+r12]
0x18001fb45  cvtsi2ss xmm0, eax
0x18001fb49  movsx   eax, byte ptr [rcx+r12+1]
0x18001fb4f  mulss   xmm1, dword ptr [rdx-8]
0x18001fb54  mulss   xmm0, dword ptr [rdx-4]
0x18001fb59  addss   xmm1, xmm6
0x18001fb5d  movaps  xmm6, xmm1
0x18001fb60  xorps   xmm1, xmm1
0x18001fb63  addss   xmm6, xmm0
0x18001fb67  xorps   xmm0, xmm0
0x18001fb6a  cvtsi2ss xmm1, eax
0x18001fb6e  movsx   eax, byte ptr [rcx+r12+2]
0x18001fb74  cvtsi2ss xmm0, eax
0x18001fb78  movsx   eax, byte ptr [rcx+r12+3]
0x18001fb7e  mulss   xmm1, dword ptr [rdx]
0x18001fb82  mulss   xmm0, dword ptr [rdx+4]
0x18001fb87  addss   xmm6, xmm1
0x18001fb8b  xorps   xmm1, xmm1
0x18001fb8e  cvtsi2ss xmm1, eax
0x18001fb92  movsx   eax, byte ptr [rcx+r12+4]
0x18001fb98  addss   xmm6, xmm0
0x18001fb9c  xorps   xmm0, xmm0
0x18001fb9f  mulss   xmm1, dword ptr [rdx+8]
0x18001fba4  cvtsi2ss xmm0, eax
0x18001fba8  movsx   eax, byte ptr [rcx+r12+5]
0x18001fbae  addss   xmm6, xmm1
0x18001fbb2  xorps   xmm1, xmm1
0x18001fbb5  mulss   xmm0, dword ptr [rdx+0Ch]
0x18001fbba  cvtsi2ss xmm1, eax
0x18001fbbe  movsx   eax, byte ptr [rcx+r12+6]
0x18001fbc4  addss   xmm6, xmm0
0x18001fbc8  xorps   xmm0, xmm0
0x18001fbcb  mulss   xmm1, dword ptr [rdx+10h]
0x18001fbd0  cvtsi2ss xmm0, eax
0x18001fbd4  movsx   eax, byte ptr [rcx+r12+7]
0x18001fbda  addss   xmm6, xmm1
0x18001fbde  xorps   xmm1, xmm1
0x18001fbe1  mulss   xmm0, dword ptr [rdx+14h]
0x18001fbe6  cvtsi2ss xmm1, eax
0x18001fbea  movsx   eax, byte ptr [rcx+r12+8]
0x18001fbf0  addss   xmm6, xmm0
0x18001fbf4  xorps   xmm0, xmm0
0x18001fbf7  mulss   xmm1, dword ptr [rdx+18h]
0x18001fbfc  cvtsi2ss xmm0, eax
0x18001fc00  movsx   eax, byte ptr [rcx+r12+9]
0x18001fc06  addss   xmm6, xmm1
0x18001fc0a  xorps   xmm1, xmm1
0x18001fc0d  mulss   xmm0, dword ptr [rdx+1Ch]
0x18001fc12  cvtsi2ss xmm1, eax
0x18001fc16  movsx   eax, byte ptr [rcx+r12+0Ah]
0x18001fc1c  addss   xmm6, xmm0
0x18001fc20  xorps   xmm0, xmm0
0x18001fc23  mulss   xmm1, dword ptr [rdx+20h]
0x18001fc28  cvtsi2ss xmm0, eax
0x18001fc2c  movsx   eax, byte ptr [rcx+r12+0Bh]
0x18001fc32  addss   xmm6, xmm1
0x18001fc36  xorps   xmm1, xmm1
0x18001fc39  mulss   xmm0, dword ptr [rdx+24h]
0x18001fc3e  cvtsi2ss xmm1, eax
0x18001fc42  movsx   eax, byte ptr [rcx+r12+0Ch]
0x18001fc48  addss   xmm6, xmm0
0x18001fc4c  xorps   xmm0, xmm0
0x18001fc4f  mulss   xmm1, dword ptr [rdx+28h]
0x18001fc54  cvtsi2ss xmm0, eax
0x18001fc58  movsx   eax, byte ptr [rcx+r12+0Dh]
0x18001fc5e  addss   xmm6, xmm1
0x18001fc62  xorps   xmm1, xmm1
0x18001fc65  mulss   xmm0, dword ptr [rdx+2Ch]
0x18001fc6a  cvtsi2ss xmm1, eax
0x18001fc6e  movsx   eax, byte ptr [rcx+r12+0Eh]
0x18001fc74  addss   xmm6, xmm0
0x18001fc78  xorps   xmm0, xmm0
0x18001fc7b  mulss   xmm1, dword ptr [rdx+30h]
0x18001fc80  cvtsi2ss xmm0, eax
0x18001fc84  addss   xmm6, xmm1
0x18001fc88  mulss   xmm0, dword ptr [rdx+34h]
0x18001fc8d  addss   xmm6, xmm0
0x18001fc91  movsx   eax, byte ptr [rcx+r12+0Fh]
0x18001fc97  xorps   xmm1, xmm1
0x18001fc9a  xorps   xmm0, xmm0
0x18001fc9d  cvtsi2ss xmm1, eax
0x18001fca1  movsx   eax, byte ptr [rcx+r12+10h]
0x18001fca7  cvtsi2ss xmm0, eax
0x18001fcab  movsx   eax, byte ptr [rcx+r12+11h]
0x18001fcb1  mulss   xmm1, dword ptr [rdx+38h]
0x18001fcb6  mulss   xmm0, dword ptr [rdx+3Ch]
0x18001fcbb  addss   xmm6, xmm1
0x18001fcbf  xorps   xmm1, xmm1
0x18001fcc2  cvtsi2ss xmm1, eax
0x18001fcc6  movsx   eax, byte ptr [rcx+r12+12h]
0x18001fccc  addss   xmm6, xmm0
0x18001fcd0  xorps   xmm0, xmm0
0x18001fcd3  mulss   xmm1, dword ptr [rdx+40h]
0x18001fcd8  cvtsi2ss xmm0, eax
0x18001fcdc  movsx   eax, byte ptr [rcx+r12+13h]
0x18001fce2  addss   xmm6, xmm1
0x18001fce6  xorps   xmm1, xmm1
0x18001fce9  mulss   xmm0, dword ptr [rdx+44h]
0x18001fcee  cvtsi2ss xmm1, eax
0x18001fcf2  movsx   eax, byte ptr [rcx+r12+14h]
0x18001fcf8  addss   xmm6, xmm0
0x18001fcfc  xorps   xmm0, xmm0
0x18001fcff  mulss   xmm1, dword ptr [rdx+48h]
0x18001fd04  cvtsi2ss xmm0, eax
0x18001fd08  movsx   eax, byte ptr [rcx+r12+15h]
0x18001fd0e  addss   xmm6, xmm1
0x18001fd12  xorps   xmm1, xmm1
0x18001fd15  mulss   xmm0, dword ptr [rdx+4Ch]
0x18001fd1a  cvtsi2ss xmm1, eax
0x18001fd1e  movsx   eax, byte ptr [rcx+r12+16h]
0x18001fd24  addss   xmm6, xmm0
0x18001fd28  xorps   xmm0, xmm0
0x18001fd2b  mulss   xmm1, dword ptr [rdx+50h]
0x18001fd30  cvtsi2ss xmm0, eax
0x18001fd34  movsx   eax, byte ptr [rcx+r12+17h]
0x18001fd3a  add     rcx, 19h
0x18001fd3e  addss   xmm6, xmm1
0x18001fd42  xorps   xmm1, xmm1
0x18001fd45  mulss   xmm0, dword ptr [rdx+54h]
0x18001fd4a  cvtsi2ss xmm1, eax
0x18001fd4e  addss   xmm6, xmm0
0x18001fd52  mulss   xmm1, dword ptr [rdx+58h]
0x18001fd57  add     rdx, 64h ; 'd'
0x18001fd5b  addss   xmm6, xmm1
0x18001fd5f  cmp     rcx, 4Bh ; 'K'
0x18001fd63  jl      loc_18001FB30
0x18001fd69  movaps  xmm3, xmm7
0x18001fd6c  mov     eax, 2
0x18001fd71  nop     dword ptr [rax+00h]
0x18001fd75  nop     word ptr [rax+rax+00000000h]
0x18001fd80  movss   xmm0, dword ptr [r8-8]
0x18001fd86  movss   xmm1, dword ptr [r8-4]
0x18001fd8c  mulss   xmm0, xmm0
0x18001fd90  mulss   xmm1, xmm1
0x18001fd94  addss   xmm3, xmm0
0x18001fd98  movss   xmm0, dword ptr [r8]
0x18001fd9d  mulss   xmm0, xmm0
0x18001fda1  addss   xmm3, xmm1
0x18001fda5  movss   xmm1, dword ptr [r8+4]
0x18001fdab  mulss   xmm1, xmm1
0x18001fdaf  addss   xmm3, xmm0
0x18001fdb3  movss   xmm0, dword ptr [r8+8]
0x18001fdb9  mulss   xmm0, xmm0
0x18001fdbd  addss   xmm3, xmm1
0x18001fdc1  movss   xmm1, dword ptr [r8+0Ch]
0x18001fdc7  mulss   xmm1, xmm1
0x18001fdcb  addss   xmm3, xmm0
0x18001fdcf  movss   xmm0, dword ptr [r8+10h]
0x18001fdd5  mulss   xmm0, xmm0
0x18001fdd9  addss   xmm3, xmm1
0x18001fddd  movss   xmm1, dword ptr [r8+14h]
0x18001fde3  mulss   xmm1, xmm1
0x18001fde7  addss   xmm3, xmm0
0x18001fdeb  movss   xmm0, dword ptr [r8+18h]
0x18001fdf1  mulss   xmm0, xmm0
0x18001fdf5  addss   xmm3, xmm1
0x18001fdf9  movss   xmm1, dword ptr [r8+1Ch]
0x18001fdff  mulss   xmm1, xmm1
0x18001fe03  addss   xmm3, xmm0
0x18001fe07  movss   xmm0, dword ptr [r8+20h]
0x18001fe0d  mulss   xmm0, xmm0
0x18001fe11  addss   xmm3, xmm1
0x18001fe15  movss   xmm1, dword ptr [r8+24h]
0x18001fe1b  mulss   xmm1, xmm1
0x18001fe1f  addss   xmm3, xmm0
0x18001fe23  movss   xmm0, dword ptr [r8+28h]
0x18001fe29  mulss   xmm0, xmm0
0x18001fe2d  addss   xmm3, xmm1
0x18001fe31  movss   xmm1, dword ptr [r8+2Ch]
0x18001fe37  mulss   xmm1, xmm1
0x18001fe3b  addss   xmm3, xmm0
0x18001fe3f  movss   xmm0, dword ptr [r8+30h]
0x18001fe45  mulss   xmm0, xmm0
0x18001fe49  addss   xmm3, xmm1
0x18001fe4d  movss   xmm1, dword ptr [r8+34h]
0x18001fe53  mulss   xmm1, xmm1
0x18001fe57  addss   xmm3, xmm0
0x18001fe5b  movss   xmm0, dword ptr [r8+38h]
0x18001fe61  mulss   xmm0, xmm0
0x18001fe65  addss   xmm3, xmm1
0x18001fe69  movss   xmm1, dword ptr [r8+3Ch]
0x18001fe6f  mulss   xmm1, xmm1
0x18001fe73  addss   xmm3, xmm0
0x18001fe77  movss   xmm0, dword ptr [r8+40h]
0x18001fe7d  mulss   xmm0, xmm0
0x18001fe81  addss   xmm3, xmm1
0x18001fe85  movss   xmm1, dword ptr [r8+44h]
0x18001fe8b  mulss   xmm1, xmm1
0x18001fe8f  addss   xmm3, xmm0
0x18001fe93  movss   xmm0, dword ptr [r8+48h]
0x18001fe99  mulss   xmm0, xmm0
0x18001fe9d  addss   xmm3, xmm1
0x18001fea1  movss   xmm1, dword ptr [r8+4Ch]
0x18001fea7  mulss   xmm1, xmm1
0x18001feab  addss   xmm3, xmm0
0x18001feaf  movss   xmm0, dword ptr [r8+50h]
0x18001feb5  mulss   xmm0, xmm0
0x18001feb9  addss   xmm3, xmm1
0x18001febd  movss   xmm1, dword ptr [r8+54h]
0x18001fec3  mulss   xmm1, xmm1
0x18001fec7  addss   xmm3, xmm0
0x18001fecb  movss   xmm0, dword ptr [r8+58h]
0x18001fed1  mulss   xmm0, xmm0
0x18001fed5  addss   xmm3, xmm1
0x18001fed9  movss   xmm1, dword ptr [r8+5Ch]
0x18001fedf  mulss   xmm1, xmm1
0x18001fee3  addss   xmm3, xmm0
0x18001fee7  movss   xmm0, dword ptr [r8+60h]
0x18001feed  mulss   xmm0, xmm0
0x18001fef1  addss   xmm3, xmm1
0x18001fef5  addss   xmm3, xmm0
0x18001fef9  movss   xmm1, dword ptr [r8+64h]
0x18001feff  movss   xmm0, dword ptr [r8+68h]
0x18001ff05  mulss   xmm1, xmm1
0x18001ff09  mulss   xmm0, xmm0
0x18001ff0d  addss   xmm3, xmm1
0x18001ff11  movss   xmm1, dword ptr [r8+6Ch]
0x18001ff17  mulss   xmm1, xmm1
0x18001ff1b  addss   xmm3, xmm0
0x18001ff1f  movss   xmm0, dword ptr [r8+70h]
0x18001ff25  mulss   xmm0, xmm0
0x18001ff29  addss   xmm3, xmm1
0x18001ff2d  movss   xmm1, dword ptr [r8+74h]
0x18001ff33  mulss   xmm1, xmm1
0x18001ff37  addss   xmm3, xmm0
0x18001ff3b  movss   xmm0, dword ptr [r8+78h]
0x18001ff41  mulss   xmm0, xmm0
0x18001ff45  addss   xmm3, xmm1
0x18001ff49  movss   xmm1, dword ptr [r8+7Ch]
0x18001ff4f  mulss   xmm1, xmm1
0x18001ff53  addss   xmm3, xmm0
0x18001ff57  movss   xmm0, dword ptr [r8+80h]
0x18001ff60  mulss   xmm0, xmm0
0x18001ff64  addss   xmm3, xmm1
0x18001ff68  movss   xmm1, dword ptr [r8+84h]
0x18001ff71  mulss   xmm1, xmm1
0x18001ff75  addss   xmm3, xmm0
0x18001ff79  movss   xmm0, dword ptr [r8+88h]
0x18001ff82  mulss   xmm0, xmm0
0x18001ff86  addss   xmm3, xmm1
0x18001ff8a  movss   xmm1, dword ptr [r8+8Ch]
0x18001ff93  mulss   xmm1, xmm1
0x18001ff97  addss   xmm3, xmm0
0x18001ff9b  movss   xmm0, dword ptr [r8+90h]
0x18001ffa4  mulss   xmm0, xmm0
0x18001ffa8  addss   xmm3, xmm1
0x18001ffac  movss   xmm1, dword ptr [r8+94h]
0x18001ffb5  mulss   xmm1, xmm1
0x18001ffb9  addss   xmm3, xmm0
0x18001ffbd  movss   xmm0, dword ptr [r8+98h]
0x18001ffc6  mulss   xmm0, xmm0
0x18001ffca  addss   xmm3, xmm1
0x18001ffce  movss   xmm1, dword ptr [r8+9Ch]
0x18001ffd7  mulss   xmm1, xmm1
0x18001ffdb  addss   xmm3, xmm0
0x18001ffdf  movss   xmm0, dword ptr [r8+0A0h]
0x18001ffe8  mulss   xmm0, xmm0
0x18001ffec  addss   xmm3, xmm1
0x18001fff0  movss   xmm1, dword ptr [r8+0A4h]
  ... truncated ...
```
