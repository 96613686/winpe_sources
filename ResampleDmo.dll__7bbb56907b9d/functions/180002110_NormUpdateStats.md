# NormUpdateStats

- ea: `0x180002110`
- end: `0x18000280c`
- name: `NormUpdateStats`
- size: `1788`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0x180002110`
- `0x180002820`
- `0x180002c00`
- `0x180002da0`
- `0x180003010`
- `0x1800031c0`
- `0x1800031e8`
- `0x180003254`
- `0x18000a1fc`
- `0x18000a500`
- `0x18000a5fc`
- `0x18000ab90`
- `0x18000b79c`
- `0x18000b8a0`
- `0x180081fcc`
- `0x18008202c`
- `0x180084690`

## pseudocode

```c
__int64 __fastcall NormUpdateStats(unsigned int *a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // esi
  __int128 v4; // xmm0
  __int64 v7; // r14
  unsigned int v8; // r13d
  unsigned int v9; // ebx
  char *v10; // r15
  __int64 v11; // rsi
  unsigned int v12; // r12d
  __int16 *v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int i; // ecx
  float v19; // xmm0_4
  double v20; // xmm1_8
  double v21; // xmm2_8
  double v22; // xmm2_8
  double v23; // xmm1_8
  __int64 v24; // r9
  __int128 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int64 v36; // rax
  __int64 v37; // rdx
  __int128 *v38; // rcx
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm1
  __int64 v46; // rdx
  __int64 v47; // rdx
  unsigned int v48; // ecx
  __int64 v49; // r8
  __int64 result; // rax
  unsigned int v51; // ebx
  __int64 v52; // r13
  unsigned int v53; // ebp
  float *v54; // r8
  char *v55; // r14
  char *v56; // rsi
  double v57; // xmm2_8
  __int64 v58; // r8
  size_t v59; // r8
  __int64 v60; // rdx
  __int16 *v61; // kr08_8
  int v62; // [rsp+20h] [rbp-188h]
  unsigned int v63; // [rsp+24h] [rbp-184h]
  unsigned int v64; // [rsp+28h] [rbp-180h]
  __int64 v65; // [rsp+30h] [rbp-178h]
  int v66; // [rsp+38h] [rbp-170h]
  unsigned int v67; // [rsp+3Ch] [rbp-16Ch]
  int v68; // [rsp+40h] [rbp-168h]
  char *v69; // [rsp+50h] [rbp-158h]
  _OWORD v70[2]; // [rsp+58h] [rbp-150h] BYREF
  _BYTE v71[112]; // [rsp+80h] [rbp-128h] BYREF

  v3 = a1[1];
  LODWORD(v4) = 0;
  v65 = a3;
  memset(v70, 0, 28);
  v7 = a3;
  WMAPCMAccSetFormat(v70, a1 + 22);
  v62 = a2 / v3;
  v8 = a2 / v3;
  if ( a2 / v3 )
  {
    v9 = a1[28];
    v63 = a1[26] * v3;
    v10 = (char *)((*((_QWORD *)a1 + 1) + 31LL + 4LL * v3 * v9) & 0xFFFFFFFFFFFFFFE0uLL);
    v67 = DWORD1(v70[1]);
    v68 = v70[1];
    v66 = v70[0];
    v69 = v10;
    do
    {
      v11 = *a1;
      v12 = v8;
      if ( v8 >= v9 - (unsigned int)v11 )
        v12 = v9 - v11;
      memset_0(v71, 0, 0x64u);
      v14 = a1[1];
      if ( v14 == 2 && v9 == 512 && ((v15 = a1[4]) != 0 || a1[27] == 1) )
      {
        v16 = *((_QWORD *)a1 + 1);
        v13 = (__int16 *)(v16 + 4 * v11);
        if ( v15 )
        {
          stereo_split_short(a1, v7, v12, v16 + 4 * v11);
        }
        else
        {
          v17 = v7;
          for ( i = v12; i; --i )
          {
            v19 = *(float *)v17;
            v20 = *(float *)v17;
            *(_DWORD *)v13 = *(_DWORD *)v17;
            v21 = *((double *)a1 + 4);
            if ( v19 > v21 || (v20 = COERCE_FLOAT(LODWORD(v19) ^ _xmm), v20 > v21) )
              *((double *)a1 + 4) = v20;
            LODWORD(v4) = *(_DWORD *)(v17 + 4);
            v17 += 8;
            v22 = *(float *)&v4;
            *((_DWORD *)v13 + 512) = v4;
            v23 = *((double *)a1 + 4);
            if ( *(float *)&v4 > v23 || (LODWORD(v4) = v4 ^ _xmm, v22 = *(float *)&v4, *(float *)&v4 > v23) )
              *((double *)a1 + 4) = v22;
            v13 += 2;
          }
        }
        if ( a1[28] == v12 + *a1 )
        {
          stereo_window(v10, *((_QWORD *)a1 + 1), a1 + 62);
          v25 = (__int128 *)(v24 + 1024);
          v26 = 8;
          v27 = v24;
          do
          {
            v27 += 128;
            v28 = *v25;
            v29 = v25[1];
            v25 += 8;
            *(_OWORD *)(v27 - 128) = v28;
            v30 = *(v25 - 6);
            *(_OWORD *)(v27 - 112) = v29;
            v31 = *(v25 - 5);
            *(_OWORD *)(v27 - 96) = v30;
            v32 = *(v25 - 4);
            *(_OWORD *)(v27 - 80) = v31;
            v33 = *(v25 - 3);
            *(_OWORD *)(v27 - 64) = v32;
            v34 = *(v25 - 2);
            *(_OWORD *)(v27 - 48) = v33;
            v35 = *(v25 - 1);
            *(_OWORD *)(v27 - 32) = v34;
            *(_OWORD *)(v27 - 16) = v35;
            --v26;
          }
          while ( v26 );
          v36 = v24 + 2048;
          v37 = 8;
          v38 = (__int128 *)(v24 + 3072);
          do
          {
            v36 += 128;
            v39 = *v38;
            v40 = v38[1];
            v38 += 8;
            *(_OWORD *)(v36 - 128) = v39;
            v41 = *(v38 - 6);
            *(_OWORD *)(v36 - 112) = v40;
            v42 = *(v38 - 5);
            *(_OWORD *)(v36 - 96) = v41;
            v43 = *(v38 - 4);
            *(_OWORD *)(v36 - 80) = v42;
            v44 = *(v38 - 3);
            *(_OWORD *)(v36 - 64) = v43;
            v4 = *(v38 - 2);
            *(_OWORD *)(v36 - 48) = v44;
            v45 = *(v38 - 1);
            *(_OWORD *)(v36 - 32) = v4;
            *(_OWORD *)(v36 - 16) = v45;
            --v37;
          }
          while ( v37 );
          v46 = *((_QWORD *)a1 + 17);
          if ( v46 )
          {
            ippsFFTFwd_RToPerm_32f_I(v10, v46, *((_QWORD *)a1 + 15));
            ippsFFTFwd_RToPerm_32f_I(v10 + 2048, *((_QWORD *)a1 + 17), *((_QWORD *)a1 + 15));
          }
          else
          {
            fftr(v10, a1[28]);
            fftr(v10 + 2048, a1[28]);
          }
          stereo_add_spectra(v10, v71);
        }
      }
      else
      {
        v51 = 0;
        v64 = 0;
        if ( v14 )
        {
          v52 = v65;
          do
          {
            v53 = 0;
            v54 = (float *)(v52 + a1[26] * v51);
            v55 = (char *)(*((_QWORD *)a1 + 1) + 4LL * a1[28] * v51);
            v56 = &v55[4 * *a1];
            if ( v12 )
            {
              do
              {
                if ( v66 )
                {
                  *(_QWORD *)&v4 = 0;
                  v61 = v13;
                  v13 = &_ImageBase;
                  switch ( v66 )
                  {
                    case 1:
                      *(double *)&v4 = (double)(*(unsigned __int8 *)v54 | (*((char *)v54 + 1) << 8)) * 0.000030517578125;
                      break;
                    case 2:
                      *(double *)&v4 = (double)(*(unsigned __int8 *)v54
                                              | ((*((unsigned __int8 *)v54 + 1) | (*((char *)v54 + 2) << 8)) << 8))
                                     * 0.0000001192092895507812;
                      break;
                    case 3:
                      *(double *)&v4 = (double)(*((unsigned __int8 *)v54 + 1)
                                              | ((*((unsigned __int8 *)v54 + 2) | (*((char *)v54 + 3) << 8)) << 8))
                                     * 0.0000001192092895507812;
                      break;
                    case 4:
                      *(double *)&v4 = (double)(*(unsigned __int8 *)v54
                                              | ((*((unsigned __int8 *)v54 + 1)
                                                | ((*((unsigned __int8 *)v54 + 2) | (*((char *)v54 + 2) << 8)) << 8)) << 8))
                                     * 4.656612873077393e-10;
                      break;
                    case 5:
                      *(double *)&v4 = (double)(char)(*(_BYTE *)v54 ^ 0x80) * 0.0078125;
                      break;
                    case 6:
                      WMAPCMAccGetPCMGenericD((unsigned int)(v68 + 7) >> 3, v67, v54);
                      break;
                    default:
                      v13 = v61;
                      break;
                  }
                }
                else
                {
                  *(double *)&v4 = *v54;
                }
                v57 = *((double *)a1 + 4);
                if ( *(double *)&v4 > v57 )
                {
                  *((_QWORD *)a1 + 4) = v4;
                }
                else if ( COERCE_DOUBLE(v4 ^ _xmm) > v57 )
                {
                  *((_QWORD *)a1 + 4) = v4 ^ _xmm;
                }
                *(float *)&v4 = *(double *)&v4;
                ++v53;
                v54 = (float *)((char *)v54 + v63);
                *(_DWORD *)v56 = v4;
                v56 += 4;
              }
              while ( v53 < v12 );
              v51 = v64;
              v52 = v65;
              v10 = v69;
            }
            v58 = a1[28];
            v13 = (__int16 *)(v12 + *a1);
            if ( (_DWORD)v58 == (_DWORD)v13 )
            {
              memcpy_0(v10, v55, 4 * v58);
              v59 = 4 * ((unsigned __int64)a1[28] >> 1);
              memcpy_0(v55, &v55[v59], v59);
              lm_wind(a1[28], v10, a1 + 62);
              v60 = *((_QWORD *)a1 + 17);
              if ( v60 )
                ippsFFTFwd_RToPerm_32f_I(v10, v60, *((_QWORD *)a1 + 15));
              else
                fftr(v10, a1[28]);
              powspec(v10, a1[28]);
              add_channel_spectrum((a1[28] >> 1) + 1, v10, v71, a1 + 36);
            }
            v64 = ++v51;
          }
          while ( v51 < a1[1] );
          v8 = v62;
          v7 = v65;
        }
      }
      spreading_function(v71, v13);
      v9 = a1[28];
      v48 = v12 + *a1;
      if ( v9 == v48 )
      {
        if ( a1[5] )
          *(float *)&v4 = loudness_SSE(v71, v47, v7);
        else
          loudness(v71, v47, v7);
        v8 -= v12;
        v7 = v49 + v12 * v63;
        v48 = v9 >> 1;
        *(double *)&v4 = fmax(*(float *)&v4, *((double *)a1 + 5));
        *((_QWORD *)a1 + 5) = v4;
      }
      else
      {
        v8 -= v12;
        v7 += v63 * v12;
      }
      v65 = v7;
      v62 = v8;
      *a1 = v48;
    }
    while ( v8 );
  }
  result = 0;
  *((_BYTE *)a1 + 81) = 0;
  return result;
}

```

## disassembly

```asm
0x180002110  push    rbx
0x180002112  push    rbp
0x180002113  push    rsi
0x180002114  push    rdi
0x180002115  push    r13
0x180002117  push    r14
0x180002119  sub     rsp, 178h
0x180002120  mov     rax, cs:__security_cookie
0x180002127  xor     rax, rsp
0x18000212a  mov     [rsp+1A8h+var_B8], rax
0x180002132  mov     esi, [rcx+4]
0x180002135  xorps   xmm0, xmm0
0x180002138  mov     ebx, edx
0x18000213a  mov     [rsp+1A8h+var_178], r8
0x18000213f  lea     rdx, [rcx+58h]
0x180002143  mov     rdi, rcx
0x180002146  movups  [rsp+1A8h+var_150], xmm0
0x18000214b  lea     rcx, [rsp+1A8h+var_150]
0x180002150  mov     r14, r8
0x180002153  movups  [rsp+1A8h+var_150+0Ch], xmm0
0x180002158  call    WMAPCMAccSetFormat
0x18000215d  xor     edx, edx
0x18000215f  mov     eax, ebx
0x180002161  div     esi
0x180002163  mov     [rsp+1A8h+var_188], eax
0x180002167  mov     r13d, eax
0x18000216a  test    eax, eax
0x18000216c  jz      loc_180002507
0x180002172  mov     ebx, [rdi+70h]
0x180002175  mov     eax, esi
0x180002177  imul    eax, [rdi+68h]
0x18000217b  mov     [rsp+1A8h+arg_18], r12
0x180002183  mov     [rsp+1A8h+var_38], r15
0x18000218b  mov     r15, [rdi+8]
0x18000218f  movaps  [rsp+1A8h+var_48], xmm6
0x180002197  add     r15, 1Fh
0x18000219b  movss   xmm6, dword ptr cs:__xmm@80000000800000008000000080000000
0x1800021a3  movaps  [rsp+1A8h+var_58], xmm7
0x1800021ab  movsd   xmm7, cs:__real@3e80000000000000
0x1800021b3  mov     [rsp+1A8h+var_184], eax
0x1800021b7  mov     eax, ebx
0x1800021b9  imul    eax, esi
0x1800021bc  movaps  [rsp+1A8h+var_68], xmm8
0x1800021c5  xorps   xmm8, xmm8
0x1800021c9  movaps  [rsp+1A8h+var_78], xmm9
0x1800021d2  movsd   xmm9, qword ptr cs:__xmm@80000000000000008000000000000000
0x1800021db  movaps  [rsp+1A8h+var_88], xmm10
0x1800021e4  movsd   xmm10, cs:__real@3f80000000000000
0x1800021ed  movaps  [rsp+1A8h+var_98], xmm11
0x1800021f6  movsd   xmm11, cs:__real@3f00000000000000
0x1800021ff  lea     r15, [r15+rax*4]
0x180002203  movaps  [rsp+1A8h+var_A8], xmm12
0x18000220c  mov     eax, [rsp+1A8h+var_13C]
0x180002210  and     r15, 0FFFFFFFFFFFFFFE0h
0x180002214  movsd   xmm12, cs:__real@3e00000000000000
0x18000221d  mov     [rsp+1A8h+var_16C], eax
0x180002221  mov     eax, [rsp+1A8h+var_140]
0x180002225  mov     [rsp+1A8h+var_168], eax
0x180002229  mov     eax, dword ptr [rsp+1A8h+var_150]
0x18000222d  mov     [rsp+1A8h+var_170], eax
0x180002231  mov     [rsp+1A8h+var_158], r15
0x180002236  nop     word ptr [rax+rax+00000000h]
0x180002240  mov     esi, [rdi]
0x180002242  lea     rcx, [rsp+1A8h+var_128]; void *
0x18000224a  mov     eax, ebx
0x18000224c  mov     r12d, r13d
0x18000224f  sub     eax, esi
0x180002251  mov     r8d, 64h ; 'd'; Size
0x180002257  cmp     r13d, eax
0x18000225a  cmovnb  r12d, eax
0x18000225e  xor     edx, edx; Val
0x180002260  call    memset_0
0x180002265  mov     eax, [rdi+4]
0x180002268  cmp     eax, 2
0x18000226b  jnz     loc_18000257C
0x180002271  cmp     ebx, 200h
0x180002277  jnz     loc_18000257C
0x18000227d  mov     r8d, [rdi+10h]
0x180002281  test    r8d, r8d
0x180002284  jnz     short loc_180002290
0x180002286  cmp     dword ptr [rdi+6Ch], 1
0x18000228a  jnz     loc_18000257C
0x180002290  mov     rax, [rdi+8]
0x180002294  lea     rdx, [rax+rsi*4]
0x180002298  test    r8d, r8d
0x18000229b  jnz     loc_18000254A
0x1800022a1  mov     rax, r14
0x1800022a4  mov     ecx, r12d
0x1800022a7  test    r12d, r12d
0x1800022aa  jz      short loc_18000231B
0x1800022ac  nop     dword ptr [rax+00h]
0x1800022b0  movss   xmm0, dword ptr [rax]
0x1800022b4  cvtps2pd xmm1, xmm0
0x1800022b7  movss   dword ptr [rdx], xmm0
0x1800022bb  movsd   xmm2, qword ptr [rdi+20h]
0x1800022c0  comisd  xmm1, xmm2
0x1800022c4  ja      short loc_1800022D6
0x1800022c6  xorps   xmm0, xmm6
0x1800022c9  xorps   xmm1, xmm1
0x1800022cc  cvtss2sd xmm1, xmm0
0x1800022d0  comisd  xmm1, xmm2
0x1800022d4  jbe     short loc_1800022DB
0x1800022d6  movsd   qword ptr [rdi+20h], xmm1
0x1800022db  movss   xmm0, dword ptr [rax+4]
0x1800022e0  add     rax, 8
0x1800022e4  cvtps2pd xmm2, xmm0
0x1800022e7  movss   dword ptr [rdx+800h], xmm0
0x1800022ef  movsd   xmm1, qword ptr [rdi+20h]
0x1800022f4  comisd  xmm2, xmm1
0x1800022f8  ja      loc_18000252C
0x1800022fe  xorps   xmm0, xmm6
0x180002301  xorps   xmm2, xmm2
0x180002304  cvtss2sd xmm2, xmm0
0x180002308  comisd  xmm2, xmm1
0x18000230c  ja      loc_18000252C
0x180002312  add     rdx, 4
0x180002316  add     ecx, 0FFFFFFFFh
0x180002319  jnz     short loc_1800022B0
0x18000231b  mov     ecx, [rdi]
0x18000231d  add     ecx, r12d
0x180002320  cmp     [rdi+70h], ecx
0x180002323  jnz     loc_18000244A
0x180002329  mov     r9, [rdi+8]
0x18000232d  lea     r8, [rdi+0F8h]
0x180002334  mov     rdx, r9
0x180002337  mov     rcx, r15
0x18000233a  call    stereo_window
0x18000233f  lea     rax, [r9+400h]
0x180002346  mov     edx, 8
0x18000234b  mov     rcx, r9
0x18000234e  lea     rcx, [rcx+80h]
0x180002355  movups  xmm0, xmmword ptr [rax]
0x180002358  movups  xmm1, xmmword ptr [rax+10h]
0x18000235c  lea     rax, [rax+80h]
0x180002363  movups  xmmword ptr [rcx-80h], xmm0
0x180002367  movups  xmm0, xmmword ptr [rax-60h]
0x18000236b  movups  xmmword ptr [rcx-70h], xmm1
0x18000236f  movups  xmm1, xmmword ptr [rax-50h]
0x180002373  movups  xmmword ptr [rcx-60h], xmm0
0x180002377  movups  xmm0, xmmword ptr [rax-40h]
0x18000237b  movups  xmmword ptr [rcx-50h], xmm1
0x18000237f  movups  xmm1, xmmword ptr [rax-30h]
0x180002383  movups  xmmword ptr [rcx-40h], xmm0
0x180002387  movups  xmm0, xmmword ptr [rax-20h]
0x18000238b  movups  xmmword ptr [rcx-30h], xmm1
0x18000238f  movups  xmm1, xmmword ptr [rax-10h]
0x180002393  movups  xmmword ptr [rcx-20h], xmm0
0x180002397  movups  xmmword ptr [rcx-10h], xmm1
0x18000239b  sub     rdx, 1
0x18000239f  jnz     short loc_18000234E
0x1800023a1  lea     rax, [r9+800h]
0x1800023a8  mov     edx, 8
0x1800023ad  lea     rcx, [r9+0C00h]
0x1800023b4  lea     rax, [rax+80h]
0x1800023bb  movups  xmm0, xmmword ptr [rcx]
0x1800023be  movups  xmm1, xmmword ptr [rcx+10h]
0x1800023c2  lea     rcx, [rcx+80h]
0x1800023c9  movups  xmmword ptr [rax-80h], xmm0
0x1800023cd  movups  xmm0, xmmword ptr [rcx-60h]
0x1800023d1  movups  xmmword ptr [rax-70h], xmm1
0x1800023d5  movups  xmm1, xmmword ptr [rcx-50h]
0x1800023d9  movups  xmmword ptr [rax-60h], xmm0
0x1800023dd  movups  xmm0, xmmword ptr [rcx-40h]
0x1800023e1  movups  xmmword ptr [rax-50h], xmm1
0x1800023e5  movups  xmm1, xmmword ptr [rcx-30h]
0x1800023e9  movups  xmmword ptr [rax-40h], xmm0
0x1800023ed  movups  xmm0, xmmword ptr [rcx-20h]
0x1800023f1  movups  xmmword ptr [rax-30h], xmm1
0x1800023f5  movups  xmm1, xmmword ptr [rcx-10h]
0x1800023f9  movups  xmmword ptr [rax-20h], xmm0
0x1800023fd  movups  xmmword ptr [rax-10h], xmm1
0x180002401  sub     rdx, 1
0x180002405  jnz     short loc_1800023B4
0x180002407  mov     rdx, [rdi+88h]
0x18000240e  mov     rcx, r15
0x180002411  test    rdx, rdx
0x180002414  jz      loc_180002560
0x18000241a  mov     r8, [rdi+78h]
0x18000241e  call    ippsFFTFwd_RToPerm_32f_I
0x180002423  mov     r8, [rdi+78h]
0x180002427  lea     rcx, [r15+800h]
0x18000242e  mov     rdx, [rdi+88h]
0x180002435  call    ippsFFTFwd_RToPerm_32f_I
0x18000243a  lea     rdx, [rsp+1A8h+var_128]
0x180002442  mov     rcx, r15
0x180002445  call    stereo_add_spectra
0x18000244a  lea     rcx, [rsp+1A8h+var_128]
0x180002452  call    spreading_function
0x180002457  mov     ecx, [rdi]
0x180002459  mov     ebx, [rdi+70h]
0x18000245c  add     ecx, r12d
0x18000245f  cmp     ebx, ecx
0x180002461  jnz     loc_180002536
0x180002467  cmp     dword ptr [rdi+14h], 0
0x18000246b  lea     rcx, [rsp+1A8h+var_128]
0x180002473  mov     r8, r14
0x180002476  jz      loc_1800027E9
0x18000247c  call    loudness_SSE
0x180002481  mov     r14d, [rsp+1A8h+var_184]
0x180002486  sub     r13d, r12d
0x180002489  imul    r14d, r12d
0x18000248d  mov     ecx, ebx
0x18000248f  cvtss2sd xmm0, xmm0
0x180002493  add     r14, r8
0x180002496  shr     ecx, 1
0x180002498  maxsd   xmm0, qword ptr [rdi+28h]
0x18000249d  movsd   qword ptr [rdi+28h], xmm0
0x1800024a2  mov     [rsp+1A8h+var_178], r14
0x1800024a7  mov     rax, rdi
0x1800024aa  mov     [rsp+1A8h+var_188], r13d
0x1800024af  mov     [rax], ecx
0x1800024b1  test    r13d, r13d
0x1800024b4  jnz     loc_180002240
0x1800024ba  movaps  xmm12, [rsp+1A8h+var_A8]
0x1800024c3  movaps  xmm11, [rsp+1A8h+var_98]
0x1800024cc  movaps  xmm10, [rsp+1A8h+var_88]
0x1800024d5  movaps  xmm9, [rsp+1A8h+var_78]
0x1800024de  movaps  xmm8, [rsp+1A8h+var_68]
0x1800024e7  movaps  xmm7, [rsp+1A8h+var_58]
0x1800024ef  movaps  xmm6, [rsp+1A8h+var_48]
0x1800024f7  mov     r15, [rsp+1A8h+var_38]
0x1800024ff  mov     r12, [rsp+1A8h+arg_18]
0x180002507  xor     eax, eax
0x180002509  mov     [rdi+51h], al
0x18000250c  mov     rcx, [rsp+1A8h+var_B8]
0x180002514  xor     rcx, rsp; StackCookie
0x180002517  call    __security_check_cookie
0x18000251c  add     rsp, 178h
0x180002523  pop     r14
0x180002525  pop     r13
0x180002527  pop     rdi
0x180002528  pop     rsi
0x180002529  pop     rbp
0x18000252a  pop     rbx
0x18000252b  retn
0x18000252c  movsd   qword ptr [rdi+20h], xmm2
0x180002531  jmp     loc_180002312
0x180002536  sub     r13d, r12d
0x180002539  imul    r12d, [rsp+1A8h+var_184]
0x18000253f  mov     eax, r12d
0x180002542  add     r14, rax
0x180002545  jmp     loc_1800024A2
0x18000254a  mov     r9, rdx
0x18000254d  mov     r8d, r12d
0x180002550  mov     rdx, r14
0x180002553  mov     rcx, rdi
0x180002556  call    stereo_split_short
0x18000255b  jmp     loc_18000231B
0x180002560  mov     edx, [rdi+70h]
0x180002563  call    fftr
0x180002568  mov     edx, [rdi+70h]
0x18000256b  lea     rcx, [r15+800h]
0x180002572  call    fftr
0x180002577  jmp     loc_18000243A
0x18000257c  xor     ebx, ebx
0x18000257e  mov     [rsp+1A8h+var_180], ebx
0x180002582  test    eax, eax
0x180002584  jz      loc_18000244A
0x18000258a  mov     r13, [rsp+1A8h+var_178]
0x18000258f  nop
0x180002590  mov     rax, [rdi+8]
0x180002594  mov     ecx, ebx
0x180002596  imul    ecx, [rdi+70h]
0x18000259a  mov     r8d, ebx
0x18000259d  imul    r8d, [rdi+68h]
0x1800025a2  xor     ebp, ebp
0x1800025a4  add     r8, r13
0x1800025a7  lea     r14, [rax+rcx*4]
0x1800025ab  mov     eax, [rdi]
0x1800025ad  mov     [rsp+1A8h+var_160], r14
0x1800025b2  lea     rsi, [r14+rax*4]
0x1800025b6  test    r12d, r12d
0x1800025b9  jz      short loc_18000262A
0x1800025bb  mov     r15d, [rsp+1A8h+var_184]
0x1800025c0  mov     r14d, [rsp+1A8h+var_170]
0x1800025c5  mov     r13d, [rsp+1A8h+var_16C]
0x1800025ca  mov     ebx, [rsp+1A8h+var_168]
0x1800025ce  xchg    ax, ax
0x1800025d0  test    r14d, r14d
0x1800025d3  jnz     loc_1800026D2
0x1800025d9  movss   xmm0, dword ptr [r8]
0x1800025de  cvtps2pd xmm0, xmm0
0x1800025e1  movsd   xmm2, qword ptr [rdi+20h]; jumptable 00000001800026F6 default case
0x1800025e6  comisd  xmm0, xmm2
0x1800025ea  ja      loc_1800027D5
0x1800025f0  movaps  xmm1, xmm0
0x1800025f3  xorps   xmm1, xmm9
0x1800025f7  comisd  xmm1, xmm2
0x1800025fb  ja      loc_1800027DF
0x180002601  cvtsd2ss xmm0, xmm0
0x180002605  inc     ebp
0x180002607  add     r8, r15
0x18000260a  movss   dword ptr [rsi], xmm0
0x18000260e  add     rsi, 4
0x180002612  cmp     ebp, r12d
0x180002615  jb      short loc_1800025D0
0x180002617  mov     ebx, [rsp+1A8h+var_180]
0x18000261b  mov     r14, [rsp+1A8h+var_160]
0x180002620  mov     r13, [rsp+1A8h+var_178]
0x180002625  mov     r15, [rsp+1A8h+var_158]
  ... truncated ...
```
