# compute_theta

- ea: `0x18000d040`
- end: `0x18000d967`
- name: `compute_theta`
- size: `2343`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fa20`
- `0x180010060`

## callees

- `0x180008950`
- `0x180008eb0`
- `0x1800090e0`
- `0x180009290`
- `0x1800092d0`
- `0x18000a920`
- `0x18000cf80`
- `0x18000d040`
- `0x18000dfd0`
- `0x180010be0`
- `0x180012860`
- `0x180015600`
- `0x1800157e0`
- `0x180015990`
- `0x1800159e0`

## pseudocode

```c
__int64 __fastcall compute_theta(
        int *a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int *a6,
        char a7,
        int a8,
        int a9,
        unsigned int a10,
        _DWORD *a11)
{
  __int64 v11; // rdx
  int v13; // r10d
  signed int v14; // edi
  __int64 v15; // rcx
  __int64 v17; // r15
  int v19; // r11d
  int *v20; // r13
  int v21; // ecx
  int v22; // eax
  int v23; // r9d
  int v24; // eax
  int v25; // ecx
  __int64 v26; // rdx
  signed int v27; // esi
  __int64 v28; // rdx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v32; // ecx
  int v33; // ecx
  signed int v34; // eax
  int v35; // ecx
  __int16 v36; // ax
  int v37; // r8d
  int v38; // r10d
  int v39; // edx
  unsigned int v40; // r12d
  int v41; // r9d
  int v42; // r12d
  unsigned int v43; // ecx
  __int64 v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // eax
  unsigned int v47; // eax
  int v48; // eax
  unsigned int v49; // edx
  int v50; // edi
  __int64 v51; // rdx
  __int64 v52; // r8
  unsigned int v53; // eax
  unsigned int v54; // eax
  int v55; // eax
  __int64 v56; // rdx
  int v57; // edx
  int v58; // ecx
  __int64 v59; // rdx
  __int64 v60; // rdx
  int v61; // eax
  __int64 v62; // rdx
  unsigned int v63; // ebx
  int v64; // esi
  __int64 v65; // r15
  int v66; // edx
  int v67; // ecx
  __m128 si128; // xmm2
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  unsigned int v73; // ecx
  unsigned int v74; // eax
  int v75; // r8d
  int v76; // r8d
  __int16 v77; // ax
  __int64 result; // rax
  unsigned int v79; // [rsp+30h] [rbp-58h]
  int v80; // [rsp+34h] [rbp-54h]
  __int64 v81; // [rsp+40h] [rbp-48h]
  int v82; // [rsp+48h] [rbp-40h]
  int v83; // [rsp+90h] [rbp+8h]
  int v86; // [rsp+B0h] [rbp+28h]
  int v87; // [rsp+D0h] [rbp+48h]
  unsigned int v88; // [rsp+D8h] [rbp+50h]

  v11 = *((_QWORD *)a1 + 1);
  v13 = *a1;
  v14 = 0;
  v15 = a1[4];
  v17 = *((_QWORD *)a1 + 4);
  v81 = *((_QWORD *)a1 + 6);
  v82 = v11;
  v79 = 0;
  v83 = v13;
  v80 = v15;
  v19 = *(__int16 *)(*(_QWORD *)(v11 + 64) + 2 * v15) + 8 * a9;
  if ( a10 && a5 == 2 )
  {
    v20 = a6;
    v21 = 2;
    v22 = (v19 >> 1) - 16;
    v23 = *a6;
  }
  else
  {
    v20 = a6;
    v22 = (v19 >> 1) - 4;
    v23 = *a6;
    if ( a10 )
    {
      v21 = 2 * a5 - 2;
      if ( a5 != 2 )
        v21 = 2 * a5 - 1;
    }
    else
    {
      v21 = 2 * a5 - 1;
    }
  }
  v24 = (v23 + v21 * v22) / v21;
  v25 = v23 - v19 - 32;
  if ( v25 >= v24 )
    v25 = v24;
  if ( v25 > 64 )
    v25 = 64;
  v26 = (unsigned int)v25;
  if ( v25 >= 4 )
  {
    v26 = v25 & 7;
    v27 = ((*((__int16 *)qword_18002D838 + v26) >> (14 - (v25 >> 3))) + 1) & 0xFFFFFFFE;
    if ( v27 > 256 )
      celt_fatal(
        "assertion failed: qn <= 256",
        "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\"
        "src\\v1.5.2-0503455b1e.clean\\celt\\bands.c",
        669);
  }
  else
  {
    v27 = 1;
  }
  if ( a10 && v80 >= a1[5] )
    v27 = 1;
  if ( v13 )
    v14 = stereo_itheta(a3, a4, a10, (unsigned int)a5, a1[15]);
  v87 = ec_tell_frac(v17, v26);
  if ( v27 == 1 )
  {
    if ( a10 )
    {
      if ( v83 )
      {
        if ( v14 <= 0x2000 || a1[17] )
        {
          v79 = 0;
        }
        else
        {
          v79 = 1;
          if ( a5 > 0 )
          {
            v67 = 0;
            if ( (unsigned int)a5 < 2 )
              goto LABEL_94;
            si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
            if ( (unsigned int)a5 < 0x10 )
              goto LABEL_116;
            do
            {
              v69 = v67;
              v67 += 16;
              *(__m128 *)(a4 + 4 * v69) = _mm_xor_ps(*(__m128 *)(a4 + 4 * v69), si128);
              *(__m128 *)(a4 + 4 * v69 + 16) = _mm_xor_ps(*(__m128 *)(a4 + 4 * v69 + 16), si128);
              *(__m128 *)(a4 + 4 * v69 + 32) = _mm_xor_ps(*(__m128 *)(a4 + 4 * v69 + 32), si128);
              *(__m128 *)(a4 + 4 * v69 + 48) = _mm_xor_ps(*(__m128 *)(a4 + 4 * v69 + 48), si128);
            }
            while ( v67 < (a5 & 0x7FFFFFF0) );
            if ( (a5 & 0xFu) >= 2 )
            {
LABEL_116:
              do
              {
                v70 = v67;
                v67 += 2;
                *(_QWORD *)(a4 + 4 * v70) ^= si128.m128_u64[0];
              }
              while ( v67 < (int)(a5 & 0xFFFFFFFE) );
            }
            if ( v67 < a5 )
            {
LABEL_94:
              if ( a5 - v67 < 4 )
                goto LABEL_115;
              do
              {
                v71 = v67;
                v67 += 4;
                *(__m128 *)(a4 + 4 * v71) = _mm_xor_ps(*(__m128 *)(a4 + 4 * v71), (__m128)_xmm);
              }
              while ( v67 < a5 - 3 );
              if ( v67 < a5 )
              {
LABEL_115:
                do
                {
                  v72 = v67++;
                  *(_DWORD *)(a4 + 4 * v72) ^= _xmm;
                }
                while ( v67 < a5 );
              }
            }
          }
        }
        intensity_stereo(v82, a3, a4, v81, v80, a5);
      }
      if ( *v20 <= 16 || a1[10] <= 16 )
      {
        v73 = 0;
      }
      else if ( v83 )
      {
        ec_enc_bit_logp(v17, v79, 2);
        v73 = v79;
      }
      else
      {
        v73 = ec_dec_bit_logp(v17, 2);
      }
      v74 = 0;
      v14 = 0;
      if ( !a1[17] )
        v74 = v73;
      v79 = v74;
      goto LABEL_108;
    }
    goto LABEL_109;
  }
  v29 = v83;
  if ( v83 )
  {
    if ( a10 && (v30 = a1[16]) != 0 )
    {
      v31 = 0x7FFF;
      if ( v14 <= 0x2000 )
        v31 = -32767;
      v32 = v14 * v27;
      v14 = v27 - 1;
      v33 = v31 / v27 + v32;
      v34 = 0;
      v35 = v33 >> 14;
      if ( v35 >= 0 )
        v34 = v35;
      if ( v14 >= v34 )
      {
        v14 = v35;
        if ( v35 < 0 )
          v14 = 0;
      }
      if ( v30 >= 0 )
        ++v14;
    }
    else
    {
      v14 = (v27 * v14 + 0x2000) >> 14;
      if ( !a10 )
      {
        if ( a1[18] && v14 > 0 && v14 < v27 )
        {
          v36 = (v14 << 14) / (unsigned int)v27;
          v37 = (v36 * v36 + 4096) >> 13;
          v38 = ((__int16)(0x4000 - v36) * (__int16)(0x4000 - v36) + 4096) >> 13;
          v39 = ((__int16)(((_WORD)a5 << 7) - 128)
               * (__int16)bitexact_log2tan(
                            (unsigned int)(__int16)((((__int16)v38
                                                    * (__int16)((((__int16)v38
                                                                * (__int16)(((0x4000 - 626 * (__int16)v38) >> 15) + 8277)
                                                                + 0x4000) >> 15)
                                                              - 7651)
                                                    + 0x4000) >> 15)
                                                  - v38
                                                  + 0x8000),
                            (unsigned int)(__int16)((((__int16)v37
                                                    * (__int16)((((__int16)v37
                                                                * (__int16)(((0x4000 - 626 * (__int16)v37) >> 15) + 8277)
                                                                + 0x4000) >> 15)
                                                              - 7651)
                                                    + 0x4000) >> 15)
                                                  - v37
                                                  + 0x8000))
               + 0x4000) >> 15;
          if ( v39 <= *v20 )
          {
            if ( v39 < -*v20 )
              v14 = 0;
          }
          else
          {
            v14 = v27;
          }
          v29 = v83;
        }
        goto LABEL_42;
      }
    }
  }
  else if ( !a10 )
  {
LABEL_42:
    if ( a8 > 1 || a10 )
    {
      v60 = (unsigned int)(v27 + 1);
      if ( v29 )
        ec_enc_uint(v17, (unsigned int)v14, (unsigned int)v60);
      else
        v14 = ec_dec_uint(v17, v60);
    }
    else
    {
      v40 = ((v27 >> 1) + 1) * ((v27 >> 1) + 1);
      if ( v29 )
      {
        if ( v14 > v27 >> 1 )
        {
          v55 = v27 - v14 + 1;
          v56 = v40 - ((v55 * (v27 - v14 + 2)) >> 1);
          ec_encode(v17, v56, (unsigned int)(v56 + v55), v40);
        }
        else
        {
          ec_encode(
            v17,
            (unsigned int)((v14 * (v14 + 1)) >> 1),
            (unsigned int)(((v14 * (v14 + 1)) >> 1) + v14 + 1),
            v40);
        }
      }
      else
      {
        v57 = ec_decode(v17, v40);
        if ( v57 >= ((v27 >> 1) * ((v27 >> 1) + 1)) >> 1 )
        {
          v14 = (2 * v27 + 2 - (unsigned int)isqrt32(8 * (v40 - v57) - 7)) >> 1;
          v58 = v27 - v14 + 1;
          v59 = v40 - ((v58 * (v27 - v14 + 2)) >> 1);
          ec_dec_update(v17, v59, (unsigned int)(v59 + v58), v40);
        }
        else
        {
          v14 = ((unsigned int)isqrt32((unsigned int)(8 * v57 + 1)) - 1) >> 1;
          ec_dec_update(
            v17,
            (unsigned int)((v14 * (v14 + 1)) >> 1),
            (unsigned int)(((v14 * (v14 + 1)) >> 1) + v14 + 1),
            v40);
        }
      }
    }
    goto LABEL_72;
  }
  if ( a5 <= 2 )
    goto LABEL_42;
  v86 = v27 / 2;
  v41 = v27 / 2;
  v42 = 3 * (v27 / 2 + 1);
  v43 = v42 + v27 / 2;
  if ( v83 )
  {
    v44 = (unsigned int)(3 * v14);
    v45 = (unsigned int)(v44 + 3);
    v46 = v42 - v27 / 2 + v14;
    if ( v14 > v41 )
      v45 = v46;
    v47 = v46 - 1;
    if ( v14 > v41 )
      v44 = v47;
    ec_encode(v17, v44, v45, v43);
  }
  else
  {
    v48 = ec_decode(v17, v43);
    v49 = v48;
    if ( v48 >= v42 )
    {
      v50 = v86 - v42 + 1;
    }
    else
    {
      v49 = (unsigned __int64)(1431655766LL * v48) >> 32;
      v50 = v49 >> 31;
    }
    v14 = v49 + v50;
    v51 = (unsigned int)(3 * v14);
    v52 = (unsigned int)(v51 + 3);
    v53 = v42 - v86 + v14;
    if ( v14 > v86 )
      v52 = v53;
    v54 = v53 - 1;
    if ( v14 > v86 )
      v51 = v54;
    ec_dec_update(v17, v51, v52, (unsigned int)(v42 + v27 / 2));
  }
LABEL_72:
  if ( v14 < 0 )
    celt_fatal(
      "assertion failed: itheta>=0",
      "D:\\os\\obj\\amd64fre\\avcore\\codecdsp\\audio\\opus\\opusliboss\\vcpkg\\objfre\\amd64\\vcpkg_buildtrees\\opus\\sr"
      "c\\v1.5.2-0503455b1e.clean\\celt\\bands.c",
      838);
  v28 = (v14 << 14) % (unsigned int)v27;
  v61 = (v14 << 14) / (unsigned int)v27;
  v14 = v61;
  if ( !v83 || !a10 )
  {
LABEL_109:
    v63 = ec_tell_frac(v17, v28) - v87;
    *v20 -= v63;
    if ( !v14 )
      goto LABEL_110;
    goto LABEL_79;
  }
  if ( !v61 )
  {
    intensity_stereo(v82, a3, a4, v81, v80, a5);
LABEL_108:
    v63 = ec_tell_frac(v17, v28) - v87;
    *v20 -= v63;
LABEL_110:
    v66 = 0;
    LODWORD(v65) = 0x7FFF;
    v64 = -16384;
    *a11 &= (1 << a7) - 1;
    goto LABEL_112;
  }
  stereo_split(a3, a4, (unsigned int)a5);
  v63 = ec_tell_frac(v17, v62) - v87;
  *v20 -= v63;
LABEL_79:
  v64 = 0x4000;
  if ( v14 == 0x4000 )
  {
    LODWORD(v65) = 0;
    v66 = 0x7FFF;
    *a11 &= ((1 << a7) - 1) << a7;
  }
  else
  {
    v75 = ((__int16)v14 * (__int16)v14 + 4096) >> 13;
    v65 = (unsigned int)(__int16)((((__int16)v75
                                  * (__int16)((((__int16)v75 * (__int16)(((0x4000 - 626 * (__int16)v75) >> 15) + 8277)
                                              + 0x4000) >> 15)
                                            - 7651)
                                  + 0x4000) >> 15)
                                - v75
                                + 0x8000);
    v76 = ((__int16)(0x4000 - v14) * (__int16)(0x4000 - v14) + 4096) >> 13;
    v88 = (__int16)((((__int16)v76
                    * (__int16)((((__int16)v76 * (__int16)(((0x4000 - 626 * (__int16)v76) >> 15) + 8277) + 0x4000) >> 15)
                              - 7651)
                    + 0x4000) >> 15)
                  - v76
                  + 0x8000);
    v77 = bitexact_log2tan(v88, v65);
    v66 = v88;
    v64 = ((__int16)(((_WORD)a5 << 7) - 128) * v77 + 0x4000) >> 15;
  }
LABEL_112:
  result = v79;
  a2[5] = v63;
  *a2 = v79;
  a2[1] = v65;
  a2[2] = v66;
  a2[3] = v64;
  a2[4] = v14;
  return result;
}

```

## disassembly

```asm
0x18000d040  mov     [rsp+arg_18], rbx
0x18000d045  mov     [rsp+arg_10], r8
0x18000d04a  mov     [rsp+arg_8], rdx
0x18000d04f  push    rbp
0x18000d050  push    rsi
0x18000d051  push    rdi
0x18000d052  push    r12
0x18000d054  push    r13
0x18000d056  push    r14
0x18000d058  push    r15
0x18000d05a  sub     rsp, 50h
0x18000d05e  mov     rdx, [rcx+8]
0x18000d062  mov     r12, rcx
0x18000d065  mov     r10d, [rcx]
0x18000d068  xor     edi, edi
0x18000d06a  movsxd  rcx, dword ptr [rcx+10h]
0x18000d06e  mov     rbx, r9
0x18000d071  mov     r8d, [rsp+88h+arg_48]
0x18000d079  mov     eax, [r12+14h]
0x18000d07e  mov     r15, [r12+20h]
0x18000d083  mov     ebp, [rsp+88h+arg_20]
0x18000d08a  mov     [rsp+88h+var_50], eax
0x18000d08e  mov     rax, [r12+30h]
0x18000d093  mov     [rsp+88h+var_48], rax
0x18000d098  mov     rax, [rdx+40h]
0x18000d09c  mov     qword ptr [rsp+88h+var_40], rdx
0x18000d0a1  mov     [rsp+88h+var_58], edi
0x18000d0a5  mov     [rsp+88h+arg_0], r10d
0x18000d0ad  movsx   edx, word ptr [rax+rcx*2]
0x18000d0b1  mov     eax, [rsp+88h+arg_40]
0x18000d0b8  mov     [rsp+88h+var_54], ecx
0x18000d0bc  lea     r11d, [rdx+rax*8]
0x18000d0c0  test    r8d, r8d
0x18000d0c3  jz      short loc_18000D0EF
0x18000d0c5  cmp     ebp, 2
0x18000d0c8  jnz     short loc_18000D0EF
0x18000d0ca  mov     r13, [rsp+88h+arg_28]
0x18000d0d2  lea     edx, ds:0FFFFFFFFFFFFFFFFh[rbp*2]
0x18000d0d9  mov     eax, r11d
0x18000d0dc  lea     ecx, [rdx-1]
0x18000d0df  sar     eax, 1
0x18000d0e1  sub     eax, 10h
0x18000d0e4  mov     r9d, [r13+0]
0x18000d0e8  cmp     ebp, ebp
0x18000d0ea  cmovnz  ecx, edx
0x18000d0ed  jmp     short loc_18000D11C
0x18000d0ef  mov     r13, [rsp+88h+arg_28]
0x18000d0f7  lea     edx, ds:0FFFFFFFFFFFFFFFFh[rbp*2]
0x18000d0fe  mov     eax, r11d
0x18000d101  sar     eax, 1
0x18000d103  add     eax, 0FFFFFFFCh
0x18000d106  mov     r9d, [r13+0]
0x18000d10a  test    r8d, r8d
0x18000d10d  jz      short loc_18000D11A
0x18000d10f  cmp     ebp, 2
0x18000d112  lea     ecx, [rdx-1]
0x18000d115  cmovnz  ecx, edx
0x18000d118  jmp     short loc_18000D11C
0x18000d11a  mov     ecx, edx
0x18000d11c  imul    eax, ecx
0x18000d11f  mov     r14d, 1
0x18000d125  add     eax, r9d
0x18000d128  sub     r9d, r11d
0x18000d12b  cdq
0x18000d12c  idiv    ecx
0x18000d12e  lea     ecx, [r9-20h]
0x18000d132  cmp     ecx, eax
0x18000d134  cmovge  ecx, eax
0x18000d137  mov     eax, 40h ; '@'
0x18000d13c  cmp     ecx, eax
0x18000d13e  cmovg   ecx, eax
0x18000d141  mov     edx, ecx
0x18000d143  cmp     ecx, 4
0x18000d146  jge     short loc_18000D14D
0x18000d148  mov     esi, r14d
0x18000d14b  jmp     short loc_18000D19F
0x18000d14d  mov     eax, edx
0x18000d14f  mov     ecx, 0Eh
0x18000d154  sar     eax, 3
0x18000d157  and     edx, 7
0x18000d15a  sub     cl, al
0x18000d15c  lea     rax, qword_18002D838
0x18000d163  movsx   esi, word ptr [rax+rdx*2]
0x18000d167  sar     esi, cl
0x18000d169  inc     esi
0x18000d16b  and     esi, 0FFFFFFFEh
0x18000d16e  cmp     esi, 100h
0x18000d174  jle     short loc_18000D19F
0x18000d176  mov     r8d, 29Dh
0x18000d17c  lea     rdx, aDOsObjAmd64fre_7; "D:\\os\\obj\\amd64fre\\avcore\\codecdsp"...
0x18000d183  lea     rcx, aAssertionFaile_38; "assertion failed: qn <= 256"
0x18000d18a  call    celt_fatal
0x18000d18f  mov     r8d, [rsp+88h+arg_48]
0x18000d197  mov     r10d, [rsp+88h+arg_0]
0x18000d19f  test    r8d, r8d
0x18000d1a2  jz      short loc_18000D1B0
0x18000d1a4  mov     eax, [rsp+88h+var_54]
0x18000d1a8  cmp     eax, [rsp+88h+var_50]
0x18000d1ac  cmovge  esi, r14d
0x18000d1b0  test    r10d, r10d
0x18000d1b3  jz      short loc_18000D1D3
0x18000d1b5  mov     eax, [r12+3Ch]
0x18000d1ba  mov     r9d, ebp
0x18000d1bd  mov     rcx, [rsp+88h+arg_10]
0x18000d1c5  mov     rdx, rbx
0x18000d1c8  mov     [rsp+88h+var_68], eax
0x18000d1cc  call    stereo_itheta
0x18000d1d1  mov     edi, eax
0x18000d1d3  mov     rcx, r15
0x18000d1d6  call    ec_tell_frac
0x18000d1db  mov     [rsp+88h+arg_40], eax
0x18000d1e2  mov     r11d, 4000h
0x18000d1e8  cmp     esi, r14d
0x18000d1eb  jz      loc_18000D65C
0x18000d1f1  mov     r8d, [rsp+88h+arg_0]
0x18000d1f9  test    r8d, r8d
0x18000d1fc  jz      loc_18000D3F4
0x18000d202  mov     ecx, [rsp+88h+arg_48]
0x18000d209  test    ecx, ecx
0x18000d20b  jz      short loc_18000D25D
0x18000d20d  mov     r9d, [r12+40h]
0x18000d212  test    r9d, r9d
0x18000d215  jz      short loc_18000D25D
0x18000d217  mov     eax, 7FFFh
0x18000d21c  cmp     edi, 2000h
0x18000d222  jg      short loc_18000D229
0x18000d224  mov     eax, 0FFFF8001h
0x18000d229  cdq
0x18000d22a  mov     ecx, esi
0x18000d22c  idiv    esi
0x18000d22e  imul    ecx, edi
0x18000d231  lea     edi, [rsi-1]
0x18000d234  add     ecx, eax
0x18000d236  xor     eax, eax
0x18000d238  sar     ecx, 0Eh
0x18000d23b  test    ecx, ecx
0x18000d23d  cmovns  eax, ecx
0x18000d240  cmp     edi, eax
0x18000d242  jl      short loc_18000D24D
0x18000d244  xor     eax, eax
0x18000d246  mov     edi, ecx
0x18000d248  test    ecx, ecx
0x18000d24a  cmovs   edi, eax
0x18000d24d  test    r9d, r9d
0x18000d250  js      loc_18000D3FE
0x18000d256  inc     edi
0x18000d258  jmp     loc_18000D3FE
0x18000d25d  imul    edi, esi
0x18000d260  add     edi, 2000h
0x18000d266  sar     edi, 0Eh
0x18000d269  test    ecx, ecx
0x18000d26b  jnz     loc_18000D3FE
0x18000d271  cmp     [r12+48h], ecx
0x18000d276  jz      loc_18000D389
0x18000d27c  test    edi, edi
0x18000d27e  jle     loc_18000D389
0x18000d284  cmp     edi, esi
0x18000d286  jge     loc_18000D389
0x18000d28c  xor     edx, edx
0x18000d28e  mov     ecx, r11d
0x18000d291  mov     eax, edi
0x18000d293  mov     r12d, 2055h
0x18000d299  shl     eax, 0Eh
0x18000d29c  div     esi
0x18000d29e  sub     cx, ax
0x18000d2a1  movsx   r8d, ax
0x18000d2a5  movsx   r10d, cx
0x18000d2a9  mov     ecx, r11d
0x18000d2ac  imul    r8d, r8d
0x18000d2b0  imul    r10d, r10d
0x18000d2b4  add     r8d, 1000h
0x18000d2bb  sar     r8d, 0Dh
0x18000d2bf  add     r10d, 1000h
0x18000d2c6  movsx   edx, r8w
0x18000d2ca  imul    eax, edx, 272h
0x18000d2d0  sar     r10d, 0Dh
0x18000d2d4  movsx   r9d, r10w
0x18000d2d8  sub     ecx, eax
0x18000d2da  sar     ecx, 0Fh
0x18000d2dd  lea     eax, [r12+rcx]
0x18000d2e1  mov     ecx, 1DE3h
0x18000d2e6  cwde
0x18000d2e7  imul    eax, edx
0x18000d2ea  add     eax, r11d
0x18000d2ed  sar     eax, 0Fh
0x18000d2f0  sub     ax, cx
0x18000d2f3  movsx   ecx, ax
0x18000d2f6  imul    ecx, edx
0x18000d2f9  imul    eax, r9d, 272h
0x18000d300  add     ecx, r11d
0x18000d303  sar     ecx, 0Fh
0x18000d306  sub     cx, r8w
0x18000d30a  mov     r8d, 0FFFF8000h
0x18000d310  add     cx, r8w
0x18000d314  movsx   edx, cx
0x18000d317  mov     ecx, r11d
0x18000d31a  sub     ecx, eax
0x18000d31c  sar     ecx, 0Fh
0x18000d31f  lea     eax, [r12+rcx]
0x18000d323  mov     ecx, 1DE3h
0x18000d328  cwde
0x18000d329  imul    eax, r9d
0x18000d32d  add     eax, r11d
0x18000d330  sar     eax, 0Fh
0x18000d333  sub     ax, cx
0x18000d336  movsx   ecx, ax
0x18000d339  imul    ecx, r9d
0x18000d33d  add     ecx, r11d
0x18000d340  sar     ecx, 0Fh
0x18000d343  sub     cx, r10w
0x18000d347  add     cx, r8w
0x18000d34b  movsx   ecx, cx
0x18000d34e  call    bitexact_log2tan
0x18000d353  movsx   edx, ax
0x18000d356  mov     r10d, 80h
0x18000d35c  movsx   eax, r10w
0x18000d360  movsx   ecx, bp
0x18000d363  imul    eax, ecx
0x18000d366  sub     ax, r10w
0x18000d36a  cwde
0x18000d36b  imul    edx, eax
0x18000d36e  mov     eax, [r13+0]
0x18000d372  add     edx, 4000h
0x18000d378  sar     edx, 0Fh
0x18000d37b  cmp     edx, eax
0x18000d37d  jle     short loc_18000D3EA
0x18000d37f  mov     edi, esi
0x18000d381  mov     r8d, [rsp+88h+arg_0]
0x18000d389  cmp     [rsp+88h+arg_38], r14d
0x18000d391  jg      loc_18000D56E
0x18000d397  cmp     [rsp+88h+arg_48], 0
0x18000d39f  jnz     loc_18000D56E
0x18000d3a5  mov     ecx, esi
0x18000d3a7  sar     ecx, 1
0x18000d3a9  mov     [rsp+88h+arg_20], ecx
0x18000d3b0  lea     eax, [rcx+1]
0x18000d3b3  mov     r12d, eax
0x18000d3b6  imul    r12d, eax
0x18000d3ba  test    r8d, r8d
0x18000d3bd  jz      loc_18000D4E1
0x18000d3c3  cmp     edi, ecx
0x18000d3c5  jg      loc_18000D4B7
0x18000d3cb  lea     edx, [rdi+1]
0x18000d3ce  mov     r9d, r12d
0x18000d3d1  imul    edx, edi
0x18000d3d4  lea     r8d, [rdi+1]
0x18000d3d8  mov     rcx, r15
0x18000d3db  sar     edx, 1
0x18000d3dd  add     r8d, edx
0x18000d3e0  call    ec_encode
0x18000d3e5  jmp     loc_18000D58C
0x18000d3ea  neg     eax
0x18000d3ec  cmp     edx, eax
0x18000d3ee  jge     short loc_18000D381
0x18000d3f0  xor     edi, edi
0x18000d3f2  jmp     short loc_18000D381
0x18000d3f4  cmp     [rsp+88h+arg_48], 0
0x18000d3fc  jz      short loc_18000D389
0x18000d3fe  cmp     ebp, 2
0x18000d401  jle     short loc_18000D389
0x18000d403  mov     eax, esi
0x18000d405  cdq
0x18000d406  sub     eax, edx
0x18000d408  sar     eax, 1
0x18000d40a  mov     [rsp+88h+arg_20], eax
0x18000d411  mov     r9d, eax
0x18000d414  lea     ecx, [rax+1]
0x18000d417  lea     r12d, [rcx+rcx*2]
0x18000d41b  lea     ecx, [r12+rax]
0x18000d41f  mov     dword ptr [rsp+88h+arg_28], ecx
0x18000d426  test    r8d, r8d
0x18000d429  jz      short loc_18000D458
0x18000d42b  sub     r12d, eax
0x18000d42e  lea     edx, [rdi+rdi*2]
0x18000d431  cmp     edi, r9d
0x18000d434  lea     r8d, [rdx+3]
0x18000d438  lea     eax, [r12+rdi]
0x18000d43c  cmovg   r8d, eax
0x18000d440  dec     eax
0x18000d442  cmp     edi, r9d
0x18000d445  mov     r9d, ecx
0x18000d448  mov     rcx, r15
0x18000d44b  cmovg   edx, eax
0x18000d44e  call    ec_encode
0x18000d453  jmp     loc_18000D58C
0x18000d458  mov     edx, ecx
0x18000d45a  mov     rcx, r15
0x18000d45d  call    ec_decode
0x18000d462  mov     ecx, [rsp+88h+arg_20]
0x18000d469  mov     edx, eax
0x18000d46b  cmp     eax, r12d
0x18000d46e  jge     short loc_18000D47E
0x18000d470  mov     eax, 55555556h
0x18000d475  imul    edx
0x18000d477  mov     edi, edx
0x18000d479  shr     edi, 1Fh
0x18000d47c  jmp     short loc_18000D485
0x18000d47e  mov     edi, ecx
0x18000d480  sub     edi, r12d
0x18000d483  inc     edi
  ... truncated ...
```
