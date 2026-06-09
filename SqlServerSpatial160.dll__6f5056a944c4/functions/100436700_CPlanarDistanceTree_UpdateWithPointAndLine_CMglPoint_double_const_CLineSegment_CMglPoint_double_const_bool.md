# CPlanarDistanceTree::UpdateWithPointAndLine(CMglPoint<double> const &,CLineSegment<CMglPoint<double>> const &,bool)

- ea: `0x100436700`
- end: `0x100436963`
- name: `?UpdateWithPointAndLine@CPlanarDistanceTree@@IEAAXAEBV?$CMglPoint@N@@AEBV?$CLineSegment@V?$CMglPoint@N@@@@_N@Z`
- size: `611`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100436050`
- `0x100436290`
- `0x1004364d0`

## callees

- `0x100436700`

## pseudocode

```c
void __fastcall CPlanarDistanceTree::UpdateWithPointAndLine(__int64 a1, double *a2, double *a3, char a4)
{
  double v4; // xmm2_8
  double v6; // xmm1_8
  double v7; // xmm3_8
  double v8; // xmm6_8
  double v9; // xmm8_8
  double v10; // xmm9_8
  double **v11; // r8
  double v12; // xmm9_8
  double v13; // xmm7_8
  double v14; // xmm4_8
  double *v15; // rcx
  double v16; // xmm0_8
  double v17; // xmm1_8
  double *v18; // rcx
  double v19; // xmm1_8
  double v20; // xmm3_8
  double *v21; // rcx
  double v22; // xmm0_8
  double v23; // xmm1_8
  double *v24; // rax
  double v25; // xmm7_8
  double v26; // xmm5_8
  double v27; // xmm6_8
  double v28; // xmm4_8
  double v29; // xmm5_8
  double v30; // xmm1_8
  double v31; // xmm3_8
  __int128 v32; // xmm0

  v4 = *a2;
  v6 = a2[1];
  v7 = a3[1] - v6;
  v8 = *a3 - *a2;
  v9 = a3[2] - *a2;
  v10 = a3[3];
  v11 = (double **)(a1 + 304);
  v12 = v10 - v6;
  *(_QWORD *)&v13 = COERCE_UNSIGNED_INT64((v12 - v7) * v7 + (v9 - v8) * v8) ^ _xmm;
  if ( v13 >= 0.0 && (v14 = (v12 - v7) * (v12 - v7) + (v9 - v8) * (v9 - v8), v13 <= v14) )
  {
    v24 = *v11;
    v25 = v13 / v14;
    v26 = (1.0 - v25) * v8;
    v27 = **v11;
    v28 = (1.0 - v25) * v7 + v6 + v12 * v25;
    v29 = v26 + v4 + v9 * v25;
    if ( a4 )
    {
      v30 = (v6 - v28) * (v6 - v28) + (v4 - v29) * (v4 - v29);
      if ( v27 > v30 )
      {
        *v24 = v30;
        v24[1] = v29;
        v24[2] = v28;
        *(_OWORD *)(v24 + 3) = *(_OWORD *)a2;
      }
    }
    else
    {
      v31 = (v28 - v6) * (v28 - v6) + (v29 - v4) * (v29 - v4);
      if ( v27 > v31 )
      {
        *v24 = v31;
        v32 = *(_OWORD *)a2;
        v24[3] = v29;
        *(_OWORD *)(v24 + 1) = v32;
        v24[4] = v28;
      }
    }
  }
  else
  {
    v15 = *v11;
    v16 = **v11;
    if ( a4 )
    {
      v17 = (v6 - a3[1]) * (v6 - a3[1]) + (v4 - *a3) * (v4 - *a3);
      if ( v16 > v17 )
      {
        *v15 = v17;
        *(_OWORD *)(v15 + 1) = *(_OWORD *)a3;
        *(_OWORD *)(v15 + 3) = *(_OWORD *)a2;
      }
      v18 = *v11;
      v19 = (a2[1] - a3[3]) * (a2[1] - a3[3]) + (*a2 - a3[2]) * (*a2 - a3[2]);
      if ( **v11 > v19 )
      {
        *v18 = v19;
        *(_OWORD *)(v18 + 1) = *((_OWORD *)a3 + 1);
        *(_OWORD *)(v18 + 3) = *(_OWORD *)a2;
      }
    }
    else
    {
      v20 = v7 * v7 + v8 * v8;
      if ( v16 > v20 )
      {
        *v15 = v20;
        *(_OWORD *)(v15 + 1) = *(_OWORD *)a2;
        *(_OWORD *)(v15 + 3) = *(_OWORD *)a3;
      }
      v21 = *v11;
      v22 = a3[3] - a2[1];
      v23 = (a3[2] - *a2) * (a3[2] - *a2) + v22 * v22;
      if ( **v11 > v23 )
      {
        *v21 = v23;
        *(_OWORD *)(v21 + 1) = *(_OWORD *)a2;
        *(_OWORD *)(v21 + 3) = *((_OWORD *)a3 + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x100436700  sub     rsp, 48h
0x100436704  movsd   xmm2, qword ptr [rdx]
0x100436708  mov     r10, r8
0x10043670b  movsd   xmm1, qword ptr [rdx+8]
0x100436710  movzx   r11d, r9b
0x100436714  movsd   xmm3, qword ptr [r8+8]
0x10043671a  movaps  [rsp+48h+var_18], xmm6
0x10043671f  subsd   xmm3, xmm1
0x100436723  movsd   xmm6, qword ptr [r8]
0x100436728  movaps  [rsp+48h+var_28], xmm7
0x10043672d  subsd   xmm6, xmm2
0x100436731  movaps  [rsp+48h+var_38], xmm8
0x100436737  movsd   xmm8, qword ptr [r8+10h]
0x10043673d  movaps  [rsp+48h+var_48], xmm9
0x100436742  subsd   xmm8, xmm2
0x100436747  movsd   xmm9, qword ptr [r8+18h]
0x10043674d  lea     r8, [rcx+130h]
0x100436754  subsd   xmm9, xmm1
0x100436759  movaps  xmm5, xmm8
0x10043675d  subsd   xmm5, xmm6
0x100436761  movaps  xmm4, xmm9
0x100436765  subsd   xmm4, xmm3
0x100436769  movaps  xmm0, xmm5
0x10043676c  mulsd   xmm0, xmm6
0x100436770  movaps  xmm7, xmm4
0x100436773  mulsd   xmm7, xmm3
0x100436777  addsd   xmm7, xmm0
0x10043677b  xorps   xmm0, xmm0
0x10043677e  xorps   xmm7, cs:__xmm@80000000000000008000000000000000
0x100436785  comisd  xmm0, xmm7
0x100436789  ja      short loc_1004367A1
0x10043678b  mulsd   xmm4, xmm4
0x10043678f  mulsd   xmm5, xmm5
0x100436793  addsd   xmm4, xmm5
0x100436797  comisd  xmm7, xmm4
0x10043679b  jbe     loc_1004368A0
0x1004367a1  mov     rcx, [r8]
0x1004367a4  mov     r9, r8
0x1004367a7  movsd   xmm0, qword ptr [rcx]
0x1004367ab  test    r11b, r11b
0x1004367ae  jz      short loc_10043682B
0x1004367b0  subsd   xmm1, qword ptr [r10+8]
0x1004367b6  subsd   xmm2, qword ptr [r10]
0x1004367bb  mulsd   xmm1, xmm1
0x1004367bf  mulsd   xmm2, xmm2
0x1004367c3  addsd   xmm1, xmm2
0x1004367c7  comisd  xmm0, xmm1
0x1004367cb  jbe     short loc_1004367E0
0x1004367cd  movsd   qword ptr [rcx], xmm1
0x1004367d1  movups  xmm0, xmmword ptr [r10]
0x1004367d5  movups  xmmword ptr [rcx+8], xmm0
0x1004367d9  movups  xmm0, xmmword ptr [rdx]
0x1004367dc  movups  xmmword ptr [rcx+18h], xmm0
0x1004367e0  movsd   xmm0, qword ptr [rdx]
0x1004367e4  subsd   xmm0, qword ptr [r10+10h]
0x1004367ea  movsd   xmm1, qword ptr [rdx+8]
0x1004367ef  subsd   xmm1, qword ptr [r10+18h]
0x1004367f5  mov     rcx, [r9]
0x1004367f8  mulsd   xmm0, xmm0
0x1004367fc  mulsd   xmm1, xmm1
0x100436800  addsd   xmm1, xmm0
0x100436804  movsd   xmm0, qword ptr [rcx]
0x100436808  comisd  xmm0, xmm1
0x10043680c  jbe     loc_100436949
0x100436812  movsd   qword ptr [rcx], xmm1
0x100436816  movups  xmm0, xmmword ptr [r10+10h]
0x10043681b  movups  xmmword ptr [rcx+8], xmm0
0x10043681f  movups  xmm0, xmmword ptr [rdx]
0x100436822  movups  xmmword ptr [rcx+18h], xmm0
0x100436826  jmp     loc_100436949
0x10043682b  mulsd   xmm3, xmm3
0x10043682f  mulsd   xmm6, xmm6
0x100436833  addsd   xmm3, xmm6
0x100436837  comisd  xmm0, xmm3
0x10043683b  jbe     short loc_100436855
0x10043683d  movsd   qword ptr [rcx], xmm3
0x100436841  movups  xmm0, xmmword ptr [rdx]
0x100436844  movups  xmmword ptr [rcx+8], xmm0
0x100436848  movups  xmm0, xmmword ptr [r10]
0x10043684c  movups  xmmword ptr [rcx+18h], xmm0
0x100436850  mov     rcx, [r9]
0x100436853  jmp     short loc_100436858
0x100436855  mov     rcx, [r8]
0x100436858  movsd   xmm0, qword ptr [r10+18h]
0x10043685e  subsd   xmm0, qword ptr [rdx+8]
0x100436863  movsd   xmm1, qword ptr [r10+10h]
0x100436869  subsd   xmm1, qword ptr [rdx]
0x10043686d  mulsd   xmm0, xmm0
0x100436871  mulsd   xmm1, xmm1
0x100436875  addsd   xmm1, xmm0
0x100436879  movsd   xmm0, qword ptr [rcx]
0x10043687d  comisd  xmm0, xmm1
0x100436881  jbe     loc_100436949
0x100436887  movsd   qword ptr [rcx], xmm1
0x10043688b  movups  xmm0, xmmword ptr [rdx]
0x10043688e  movups  xmmword ptr [rcx+8], xmm0
0x100436892  movups  xmm0, xmmword ptr [r10+10h]
0x100436897  movups  xmmword ptr [rcx+18h], xmm0
0x10043689b  jmp     loc_100436949
0x1004368a0  mov     rax, [r8]
0x1004368a3  divsd   xmm7, xmm4
0x1004368a7  movsd   xmm4, cs:__real@3ff0000000000000
0x1004368af  mulsd   xmm8, xmm7
0x1004368b4  subsd   xmm4, xmm7
0x1004368b8  mulsd   xmm9, xmm7
0x1004368bd  movaps  xmm5, xmm4
0x1004368c0  mulsd   xmm4, xmm3
0x1004368c4  mulsd   xmm5, xmm6
0x1004368c8  movsd   xmm6, qword ptr [rax]
0x1004368cc  addsd   xmm4, xmm1
0x1004368d0  addsd   xmm5, xmm2
0x1004368d4  addsd   xmm4, xmm9
0x1004368d9  addsd   xmm5, xmm8
0x1004368de  test    r11b, r11b
0x1004368e1  jz      short loc_100436914
0x1004368e3  subsd   xmm1, xmm4
0x1004368e7  subsd   xmm2, xmm5
0x1004368eb  mulsd   xmm1, xmm1
0x1004368ef  mulsd   xmm2, xmm2
0x1004368f3  addsd   xmm1, xmm2
0x1004368f7  comisd  xmm6, xmm1
0x1004368fb  jbe     short loc_100436949
0x1004368fd  movsd   qword ptr [rax], xmm1
0x100436901  movsd   qword ptr [rax+8], xmm5
0x100436906  movsd   qword ptr [rax+10h], xmm4
0x10043690b  movups  xmm0, xmmword ptr [rdx]
0x10043690e  movups  xmmword ptr [rax+18h], xmm0
0x100436912  jmp     short loc_100436949
0x100436914  movaps  xmm0, xmm5
0x100436917  movaps  xmm3, xmm4
0x10043691a  subsd   xmm3, xmm1
0x10043691e  subsd   xmm0, xmm2
0x100436922  mulsd   xmm3, xmm3
0x100436926  mulsd   xmm0, xmm0
0x10043692a  addsd   xmm3, xmm0
0x10043692e  comisd  xmm6, xmm3
0x100436932  jbe     short loc_100436949
0x100436934  movsd   qword ptr [rax], xmm3
0x100436938  movups  xmm0, xmmword ptr [rdx]
0x10043693b  movsd   qword ptr [rax+18h], xmm5
0x100436940  movups  xmmword ptr [rax+8], xmm0
0x100436944  movsd   qword ptr [rax+20h], xmm4
0x100436949  movaps  xmm6, [rsp+48h+var_18]
0x10043694e  movaps  xmm7, [rsp+48h+var_28]
0x100436953  movaps  xmm8, [rsp+48h+var_38]
0x100436959  movaps  xmm9, [rsp+48h+var_48]
0x10043695e  add     rsp, 48h
0x100436962  retn
```
