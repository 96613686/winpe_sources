# crxReadImageHeaders(crx_data_header_t *,CrxImage *,uchar *,int)

- ea: `0x180022ba0`
- end: `0x18002360a`
- name: `?crxReadImageHeaders@@YAHPEAUcrx_data_header_t@@PEAUCrxImage@@PEAEH@Z`
- size: `2666`
- prototype: `__int64 __fastcall(struct crx_data_header_t *, struct CrxImage *, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023e90`

## callees

- `0x180002a00`
- `0x180002e18`
- `0x180003e4c`
- `0x180006363`
- `0x180009000`
- `0x180015db0`
- `0x180022150`
- `0x180022780`
- `0x180022ba0`
- `0x180023610`
- `0x180023c40`
- `0x180095170`
- `0x1800a4510`
- `0x1800b0b00`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall crxReadImageHeaders(
        struct crx_data_header_t *a1,
        struct CrxImage *a2,
        unsigned __int8 *a3,
        char *a4)
{
  int v4; // r13d
  unsigned __int8 *v5; // rbx
  struct crx_data_header_t *v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdi
  char *v10; // rax
  char *v11; // r12
  unsigned int v12; // r11d
  char *v13; // r13
  signed int v14; // ebx
  char *v15; // r8
  signed int v16; // r15d
  __int16 v17; // cx
  char v18; // r10
  int v19; // eax
  char *v20; // rax
  int v21; // r10d
  int v22; // edx
  unsigned int v23; // r10d
  __int64 *v24; // r15
  int v25; // edx
  int v26; // ecx
  int v27; // r8d
  bool v28; // zf
  int v29; // ecx
  bool v30; // zf
  int v31; // edx
  unsigned __int16 v32; // cx
  __int64 v33; // rsi
  int v34; // r12d
  int v35; // ecx
  int v36; // ecx
  int v37; // edx
  int v38; // r8d
  int v39; // edx
  struct crx_data_header_t *v40; // rbx
  struct CrxTile *v41; // rbx
  int v42; // eax
  __m128i si128; // xmm6
  unsigned __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r9
  unsigned int v47; // esi
  __int64 v48; // r12
  size_t v49; // r15
  __m128i *v50; // r13
  int *v51; // rax
  int v52; // r12d
  unsigned int v53; // r11d
  __m128i *v54; // rbx
  int *v55; // r13
  int *v56; // r8
  int *v57; // r15
  int v58; // r9d
  int v59; // eax
  int *v60; // rcx
  int QP; // eax
  unsigned int v62; // r8d
  unsigned int v63; // edx
  int *v64; // rdx
  __int64 v65; // rcx
  char *v66; // r13
  unsigned __int64 v67; // r15
  char *v68; // rax
  unsigned __int64 v70; // r15
  char *v71; // rax
  int v72; // [rsp+30h] [rbp-100E8h] BYREF
  int v73; // [rsp+34h] [rbp-100E4h] BYREF
  int v74; // [rsp+38h] [rbp-100E0h]
  unsigned int v75; // [rsp+3Ch] [rbp-100DCh]
  unsigned int v76; // [rsp+40h] [rbp-100D8h]
  unsigned __int8 *v77; // [rsp+48h] [rbp-100D0h] BYREF
  struct crx_data_header_t *v78; // [rsp+50h] [rbp-100C8h]
  struct CrxTile *v79; // [rsp+58h] [rbp-100C0h]
  int pExceptionObject; // [rsp+60h] [rbp-100B8h] BYREF
  __int128 v81; // [rsp+68h] [rbp-100B0h]
  __int8 *v82; // [rsp+78h] [rbp-100A0h]
  int *v83; // [rsp+80h] [rbp-10098h]
  void *v84; // [rsp+88h] [rbp-10090h]
  __int64 v85; // [rsp+90h] [rbp-10088h]
  _BYTE v86[65536]; // [rsp+A0h] [rbp-10078h] BYREF
  unsigned __int64 v87; // [rsp+100A0h] [rbp-78h]
  __int64 v88; // [rsp+100A8h] [rbp-70h]
  __int64 v89; // [rsp+100B0h] [rbp-68h]
  __int64 v90; // [rsp+100B8h] [rbp-60h]
  __int64 v91; // [rsp+100C0h] [rbp-58h]

  v85 = -2;
  v4 = (int)a4;
  v74 = (int)a4;
  v5 = a3;
  v77 = a3;
  v7 = a1;
  v78 = a1;
  v8 = *((unsigned __int8 *)a2 + 12) * (unsigned int)*((unsigned __int8 *)a2 + 13);
  v75 = v8;
  if ( !(_DWORD)v8 )
    return 0xFFFFFFFFLL;
  if ( !*((_QWORD *)a2 + 2) )
  {
    v9 = (unsigned int)v8;
    v10 = (char *)libraw_memmgr::calloc(
                    (struct CrxImage *)((char *)a2 + 88),
                    (unsigned int)v8 * (*(unsigned __int8 *)a2 * (88LL * *((unsigned __int8 *)a2 + 8) + 56) + 56),
                    1u);
    a4 = v10;
    *((_QWORD *)a2 + 2) = v10;
    if ( v10 )
    {
      v11 = &v10[56 * v9];
      v8 = v75;
      v12 = 0;
      if ( v75 )
      {
        v13 = &v11[56 * v75 * *(unsigned __int8 *)a2];
        v14 = v75;
        while ( 1 )
        {
          a4[8] = 0;
          a4[9] = v12;
          *((_DWORD *)a4 + 6) = 0;
          v15 = &v11[56 * v12 * *(unsigned __int8 *)a2];
          *(_QWORD *)a4 = v15;
          v16 = v12 + 1;
          v17 = *((_WORD *)v7 + 6);
          if ( (int)(v12 + 1) % *((unsigned __int8 *)a2 + 12) )
          {
            *((_WORD *)a4 + 14) = v17;
            v18 = 0;
            if ( *((_BYTE *)a2 + 12) > 1u )
            {
              a4[8] = 1;
              v18 = 1;
              if ( v12 % *((unsigned __int8 *)a2 + 12) )
              {
                a4[8] = 3;
                v18 = 3;
              }
            }
          }
          else
          {
            *((_WORD *)a4 + 14) = *((_WORD *)a2 + 1) - v17 * (*((unsigned __int8 *)a2 + 12) - 1);
            v18 = 0;
            if ( *((_BYTE *)a2 + 12) > 1u )
            {
              a4[8] = 2;
              v18 = 2;
            }
          }
          if ( (int)v12 < v14 - *((unsigned __int8 *)a2 + 12) )
            break;
          *((_WORD *)a4 + 15) = *((_WORD *)a2 + 2) - *((_WORD *)v7 + 8) * (*((unsigned __int8 *)a2 + 13) - 1);
          if ( *((_BYTE *)a2 + 13) > 1u )
            goto LABEL_17;
LABEL_18:
          v19 = *(unsigned __int8 *)a2;
          if ( (_BYTE)v19 )
          {
            v20 = &v13[88 * v12 * v19 * *((unsigned __int8 *)a2 + 8)];
            v21 = 0;
            do
            {
              v15[24] = v21;
              v15[44] = 1;
              v15[52] = a4[8];
              *((_QWORD *)v15 + 1) = v20;
              *(_QWORD *)v15 = 0;
              *((_QWORD *)v15 + 2) = 0;
              if ( *((_BYTE *)a2 + 8) )
              {
                v22 = 0;
                do
                {
                  v20[44] = 0;
                  *((_DWORD *)v20 + 7) = 4;
                  *(_QWORD *)v20 = 0;
                  *((_QWORD *)v20 + 7) = 0;
                  ++v22;
                  v20 += 88;
                }
                while ( v22 < *((unsigned __int8 *)a2 + 8) );
              }
              ++v21;
              v15 += 56;
            }
            while ( v21 < *(unsigned __int8 *)a2 );
          }
          ++v12;
          a4 += 56;
          if ( v16 >= v14 )
          {
            v23 = 0;
            v24 = (__int64 *)*((_QWORD *)a2 + 2);
            v25 = 0;
            v72 = 0;
            v5 = v77;
            v4 = v74;
            goto LABEL_27;
          }
        }
        *((_WORD *)a4 + 15) = *((_WORD *)v7 + 8);
        if ( *((_BYTE *)a2 + 13) <= 1u )
          goto LABEL_18;
        v18 |= 4u;
        a4[8] = v18;
        if ( v12 < *((unsigned __int8 *)a2 + 12) )
          goto LABEL_18;
LABEL_17:
        a4[8] = v18 | 8;
        goto LABEL_18;
      }
      goto LABEL_26;
    }
    return 0xFFFFFFFFLL;
  }
LABEL_26:
  v23 = 0;
  v24 = (__int64 *)*((_QWORD *)a2 + 2);
  v25 = 0;
  v72 = 0;
  if ( (_DWORD)v8 )
  {
    while ( 1 )
    {
LABEL_27:
      if ( v4 < 4 )
        return 0xFFFFFFFFLL;
      v26 = v5[1] | (*v5 << 8);
      v27 = v5[3] | (v5[2] << 8);
      if ( v26 == 65281 )
      {
        v28 = v27 == 8;
      }
      else
      {
        if ( v26 != 65297 )
          return 0xFFFFFFFFLL;
        v28 = ((v27 - 8) & 0xFFFFFFF7) == 0;
      }
      if ( !v28 || v4 < v27 + 4 )
        return 0xFFFFFFFFLL;
      v29 = v5[11] | (v5[10] << 8);
      if ( v27 == 8 )
      {
        v30 = v29 == 0;
      }
      else
      {
        if ( v27 != 16 )
          goto LABEL_39;
        v30 = v29 == 0x4000;
      }
      if ( !v30 )
        return 0xFFFFFFFFLL;
LABEL_39:
      if ( ((v5[8] << 8) | v5[9]) != v25 )
        return 0xFFFFFFFFLL;
      v4 += -4 - v27;
      v31 = v5[7] | ((v5[6] | ((v5[5] | (v5[4] << 8)) << 8)) << 8);
      *((_DWORD *)v24 + 6) = v31;
      v24[2] = v23;
      v24[5] = 0;
      if ( v27 == 16 )
      {
        if ( v5[19] | (v5[18] << 8) )
          return 0xFFFFFFFFLL;
        *((_BYTE *)v24 + 32) = 1;
        *((_DWORD *)v24 + 12) = v5[15] | ((v5[14] | (((v5[12] << 8) | v5[13]) << 8)) << 8);
        v32 = _byteswap_ushort(*((_WORD *)v5 + 8));
      }
      else
      {
        *((_BYTE *)v24 + 32) = 0;
        *((_DWORD *)v24 + 12) = 0;
        v32 = 0;
      }
      *((_WORD *)v24 + 26) = v32;
      v5 += (unsigned int)(v27 + 4);
      v23 += v31;
      v76 = v23;
      a4 = 0;
      v33 = *v24;
      v34 = 0;
      if ( *(_BYTE *)a2 )
      {
        while ( v4 >= 12 )
        {
          v35 = v5[1] | (*v5 << 8);
          if ( v35 != 65282 && v35 != 65298 )
            break;
          if ( (v5[3] | (v5[2] << 8)) != 8 || v34 != v5[8] >> 4 || v5[11] | (((v5[9] << 8) | v5[10]) << 8) )
            break;
          v36 = v5[7] | ((v5[6] | ((v5[5] | (v5[4] << 8)) << 8)) << 8);
          *(_DWORD *)(v33 + 40) = v36;
          v37 = v5[8] >> 1;
          v38 = v5[8] & 8;
          *(_BYTE *)(v33 + 44) = v38 != 0;
          *(_QWORD *)(v33 + 32) = (unsigned int)a4;
          *(_BYTE *)(v33 + 52) = *((_BYTE *)v24 + 8);
          v74 = v36 + (_DWORD)a4;
          v73 = v4 - 12;
          v77 = v5 + 12;
          *(_DWORD *)(v33 + 48) = 0;
          v39 = v37 & 3;
          if ( v39 )
          {
            if ( *((_BYTE *)a2 + 9) || !v38 )
              return 0xFFFFFFFFLL;
            *(_DWORD *)(v33 + 48) = 1 << (v39 - 1);
          }
          v40 = v78;
          if ( (unsigned int)crxReadSubbandHeaders(
                               v78,
                               a2,
                               (struct CrxTile *)v24,
                               (struct CrxPlaneComp *)v33,
                               &v77,
                               &v73)
            || (unsigned int)crxProcessSubbands(v40, a2, (struct CrxTile *)v24, (struct CrxPlaneComp *)v33) )
          {
            return 0xFFFFFFFFLL;
          }
          ++v34;
          v33 += 56;
          v4 = v73;
          v5 = v77;
          if ( v34 >= *(unsigned __int8 *)a2 )
          {
            v23 = v76;
            goto LABEL_60;
          }
          LODWORD(a4) = v74;
        }
        return 0xFFFFFFFFLL;
      }
LABEL_60:
      v25 = v72 + 1;
      v72 = v25;
      v24 += 7;
      v8 = v75;
      if ( v25 >= (int)v75 )
      {
        v7 = v78;
        break;
      }
    }
  }
  if ( *(_DWORD *)v7 == 512 )
  {
    v41 = (struct CrxTile *)*((_QWORD *)a2 + 2);
    v42 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v74 = v42;
      v79 = v41;
      if ( v42 >= (int)v8 )
        break;
      if ( *((_BYTE *)v41 + 32) )
      {
        v90 = 0;
        v89 = 0;
        v44 = *((unsigned int *)v41 + 12);
        v87 = v44;
        v88 = *((_QWORD *)v41 + 2) + *((_QWORD *)a2 + 3);
        v45 = *((_QWORD *)a2 + 10);
        v91 = v45;
        if ( v44 )
        {
          (*(void (__fastcall **)(__int64, unsigned __int64, __int64, char *))(*(_QWORD *)v45 + 96LL))(v45, v44, v8, a4);
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v91 + 24LL))(v91, v88, 0);
          v46 = 0x10000;
          if ( v87 < 0x10000 )
            v46 = v87;
          HIDWORD(v89) = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)v91 + 16LL))(
                           v91,
                           v86,
                           1,
                           v46);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 104LL))(v91);
          if ( !HIDWORD(v89) )
          {
            pExceptionObject = 4;
            throw (LibRaw_exceptions *)&pExceptionObject;
          }
          v87 -= HIDWORD(v89);
        }
        v47 = ((*((_WORD *)v41 + 14) & 7) != 0) + (*((unsigned __int16 *)v41 + 14) >> 3);
        LODWORD(v78) = v47;
        v76 = (*((_WORD *)v41 + 15) & 1) + (*((unsigned __int16 *)v41 + 15) >> 1);
        v48 = v47 * v76;
        LODWORD(v77) = v47 * v76;
        v81 = 0;
        v82 = 0;
        v49 = 4LL * ((unsigned int)v48 + 2 * (v47 + 2));
        v50 = (__m128i *)std::_Allocate<16,std::_Default_allocate_traits>(v49);
        v84 = v50;
        *(_QWORD *)&v81 = v50;
        v82 = &v50->m128i_i8[v49];
        memset(v50, 0, v49);
        *((_QWORD *)&v81 + 1) = (char *)v50 + v49;
        v51 = &v50->m128i_i32[v48];
        v83 = v51;
        v52 = 0;
        v72 = 0;
        v53 = 0;
        v73 = 0;
        v54 = v50;
        while ( v53 < v76 )
        {
          if ( (v53 & 1) != 0 )
          {
            v55 = v51;
            v56 = &v51[v47 + 2];
          }
          else
          {
            v55 = &v51[v47 + 2];
            v56 = v51;
          }
          if ( v53 )
          {
            crxDecodeGolombNormal((struct CrxBitstream *)v86, v47, v56, v55, &v72);
            v52 = v72;
          }
          else
          {
            v57 = v55;
            *v55 = 0;
            v58 = 0;
            while ( 1 )
            {
              v59 = v47--;
              v60 = ++v57;
              if ( v59 <= 0 )
                break;
              *v60 = v58;
              QP = crxReadQP((struct CrxBitstream *)v86, v52);
              v58 = *v57 + (-(QP & 1) ^ ((unsigned int)QP >> 1));
              *v57 = v58;
              v52 += (QP >> v52 > 2) + (QP >> v52 > 5) - (QP < 1 << v52 >> 1);
              if ( v52 >= 7 )
                v52 = 7;
              v72 = v52;
            }
            *v60 = v58 + 1;
            v47 = (unsigned int)v78;
          }
          v62 = 0;
          if ( v47 )
          {
            if ( v47 < 0x10 || v54 <= (__m128i *)&v55[v47] && (char *)v54 + 4 * v47 - 4 >= (char *)(v55 + 1) )
              goto LABEL_91;
            v63 = 5;
            do
            {
              *v54 = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v55[v63 - 4]), si128);
              v54[1] = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v55[v63]), si128);
              v54[2] = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v55[v63 + 4]), si128);
              v54[3] = _mm_add_epi32(_mm_loadu_si128((const __m128i *)&v55[v63 + 8]), si128);
              v54 += 4;
              v62 += 16;
              v63 += 16;
            }
            while ( v62 < (v47 & 0xFFFFFFF0) );
            if ( v62 < v47 )
            {
LABEL_91:
              v64 = &v55[v62 + 1];
              v65 = v47 - v62;
              do
              {
                v54->m128i_i32[0] = *v64 + 4;
                v54 = (__m128i *)((char *)v54 + 4);
                ++v64;
                --v65;
              }
              while ( v65 );
            }
          }
          v53 = ++v73;
          v51 = v83;
        }
        v66 = (char *)v84;
        v41 = v79;
        if ( (unsigned int)crxMakeQStep(a2, v79, (int *)v84, (unsigned int)v77) )
        {
          if ( v66 )
          {
            v67 = (v82 - v66) & 0xFFFFFFFFFFFFFFFCuLL;
            v68 = v66;
            if ( v67 >= 0x1000 )
            {
              v67 += 39LL;
              v66 = (char *)*((_QWORD *)v66 - 1);
              if ( (unsigned __int64)(v68 - v66 - 8) > 0x1F )
LABEL_109:
                invoke_watson_0(0, 0, 0, 0, 0);
            }
            operator delete(v66, v67);
          }
          return 0xFFFFFFFFLL;
        }
        if ( v66 )
        {
          v70 = (v82 - v66) & 0xFFFFFFFFFFFFFFFCuLL;
          v71 = v66;
          if ( v70 >= 0x1000 )
          {
            v70 += 39LL;
            v66 = (char *)*((_QWORD *)v66 - 1);
            if ( (unsigned __int64)(v71 - v66 - 8) > 0x1F )
              goto LABEL_109;
          }
          operator delete(v66, v70);
        }
        v42 = v74;
        v8 = v75;
      }
      ++v42;
      v41 = (struct CrxTile *)((char *)v41 + 56);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180022ba0  push    rdi
0x180022ba2  push    r12
0x180022ba4  push    r13
0x180022ba6  push    r14
0x180022ba8  push    r15
0x180022baa  mov     eax, 100F0h
0x180022baf  call    _alloca_probe
0x180022bb4  sub     rsp, rax
0x180022bb7  mov     [rsp+10118h+var_10088], 0FFFFFFFFFFFFFFFEh
0x180022bc3  mov     [rsp+10118h+arg_0], rbx
0x180022bcb  mov     [rsp+10118h+arg_18], rsi
0x180022bd3  movaps  [rsp+10118h+var_38], xmm6
0x180022bdb  mov     rax, cs:__security_cookie
0x180022be2  xor     rax, rsp
0x180022be5  mov     [rsp+10118h+var_48], rax
0x180022bed  mov     r13d, r9d
0x180022bf0  mov     [rsp+10118h+var_100E0], r9d
0x180022bf5  mov     rbx, r8
0x180022bf8  mov     [rsp+10118h+var_100D0], rbx
0x180022bfd  mov     r14, rdx
0x180022c00  mov     rsi, rcx
0x180022c03  mov     [rsp+10118h+var_100C8], rcx
0x180022c08  movzx   r8d, byte ptr [rdx+0Dh]
0x180022c0d  movzx   eax, byte ptr [rdx+0Ch]
0x180022c11  imul    r8d, eax
0x180022c15  mov     [rsp+10118h+var_100DC], r8d
0x180022c1a  test    r8d, r8d
0x180022c1d  jz      loc_180023594
0x180022c23  cmp     qword ptr [rdx+10h], 0
0x180022c28  jnz     loc_180022E4A
0x180022c2e  mov     edi, r8d
0x180022c31  movzx   eax, byte ptr [rdx+8]
0x180022c35  imul    rdx, rax, 58h ; 'X'
0x180022c39  add     rdx, 38h ; '8'
0x180022c3d  movzx   eax, byte ptr [r14]
0x180022c41  imul    rdx, rax
0x180022c45  add     rdx, 38h ; '8'
0x180022c49  imul    rdx, rdi; unsigned __int64
0x180022c4d  lea     rcx, [r14+58h]; this
0x180022c51  mov     r8d, 1; unsigned __int64
0x180022c57  call    ?calloc@libraw_memmgr@@QEAAPEAX_K0@Z; libraw_memmgr::calloc(unsigned __int64,unsigned __int64)
0x180022c5c  mov     r9, rax
0x180022c5f  mov     [r14+10h], rax
0x180022c63  test    rax, rax
0x180022c66  jz      loc_180023594
0x180022c6c  imul    r12, rdi, 38h ; '8'
0x180022c70  add     r12, rax
0x180022c73  movzx   ecx, byte ptr [r14]
0x180022c77  mov     r8d, [rsp+10118h+var_100DC]
0x180022c7c  imul    ecx, r8d
0x180022c80  imul    rax, rcx, 38h ; '8'
0x180022c84  add     rax, r12
0x180022c87  xor     edi, edi
0x180022c89  mov     r11d, edi
0x180022c8c  test    r8d, r8d
0x180022c8f  jz      loc_180022E4C
0x180022c95  mov     r13, rax
0x180022c98  mov     ebx, r8d
0x180022c9b  nop     dword ptr [rax+rax+00h]
0x180022ca0  mov     [r9+8], dil
0x180022ca4  mov     [r9+9], r11b
0x180022ca8  mov     [r9+18h], edi
0x180022cac  movzx   eax, byte ptr [r14]
0x180022cb0  imul    eax, r11d
0x180022cb4  cdqe
0x180022cb6  imul    r8, rax, 38h ; '8'
0x180022cba  add     r8, r12
0x180022cbd  mov     [r9], r8
0x180022cc0  movzx   r10d, byte ptr [r14+0Ch]
0x180022cc5  lea     r15d, [r11+1]
0x180022cc9  movzx   ecx, word ptr [rsi+0Ch]
0x180022ccd  mov     eax, r15d
0x180022cd0  cdq
0x180022cd1  idiv    r10d
0x180022cd4  test    edx, edx
0x180022cd6  jz      short loc_180022D09
0x180022cd8  mov     [r9+1Ch], cx
0x180022cdd  xor     r10b, r10b
0x180022ce0  cmp     byte ptr [r14+0Ch], 1
0x180022ce5  jbe     short loc_180022D32
0x180022ce7  mov     byte ptr [r9+8], 1
0x180022cec  mov     r10b, 1
0x180022cef  movzx   ecx, byte ptr [r14+0Ch]
0x180022cf4  xor     edx, edx
0x180022cf6  mov     eax, r11d
0x180022cf9  div     ecx
0x180022cfb  test    edx, edx
0x180022cfd  jz      short loc_180022D32
0x180022cff  mov     byte ptr [r9+8], 3
0x180022d04  mov     r10b, 3
0x180022d07  jmp     short loc_180022D32
0x180022d09  lea     eax, [r10-1]
0x180022d0d  movzx   edx, ax
0x180022d10  imul    edx, ecx
0x180022d13  movzx   eax, word ptr [r14+2]
0x180022d18  sub     ax, dx
0x180022d1b  mov     [r9+1Ch], ax
0x180022d20  xor     r10b, r10b
0x180022d23  cmp     byte ptr [r14+0Ch], 1
0x180022d28  jbe     short loc_180022D32
0x180022d2a  mov     byte ptr [r9+8], 2
0x180022d2f  mov     r10b, 2
0x180022d32  movzx   eax, byte ptr [r14+0Ch]
0x180022d37  mov     ecx, ebx
0x180022d39  sub     ecx, eax
0x180022d3b  cmp     r11d, ecx
0x180022d3e  jge     short loc_180022D64
0x180022d40  movzx   eax, word ptr [rsi+10h]
0x180022d44  mov     [r9+1Eh], ax
0x180022d49  cmp     byte ptr [r14+0Dh], 1
0x180022d4e  jbe     short loc_180022D92
0x180022d50  or      r10b, 4
0x180022d54  mov     [r9+8], r10b
0x180022d58  movzx   eax, byte ptr [r14+0Ch]
0x180022d5d  cmp     r11d, eax
0x180022d60  jb      short loc_180022D92
0x180022d62  jmp     short loc_180022D8A
0x180022d64  movzx   eax, byte ptr [r14+0Dh]
0x180022d69  dec     ax
0x180022d6c  movzx   ecx, word ptr [rsi+10h]
0x180022d70  movzx   edx, ax
0x180022d73  imul    edx, ecx
0x180022d76  movzx   eax, word ptr [r14+4]
0x180022d7b  sub     ax, dx
0x180022d7e  mov     [r9+1Eh], ax
0x180022d83  cmp     byte ptr [r14+0Dh], 1
0x180022d88  jbe     short loc_180022D92
0x180022d8a  or      r10b, 8
0x180022d8e  mov     [r9+8], r10b
0x180022d92  movzx   eax, byte ptr [r14]
0x180022d96  test    al, al
0x180022d98  jz      loc_180022E21
0x180022d9e  mov     ecx, eax
0x180022da0  movzx   eax, byte ptr [r14+8]
0x180022da5  imul    eax, ecx
0x180022da8  imul    eax, r11d
0x180022dac  cdqe
0x180022dae  imul    rax, 58h ; 'X'
0x180022db2  add     rax, r13
0x180022db5  mov     r10d, edi
0x180022db8  test    ecx, ecx
0x180022dba  jz      short loc_180022E21
0x180022dbc  nop     dword ptr [rax+00h]
0x180022dc0  mov     [r8+18h], r10b
0x180022dc4  mov     byte ptr [r8+2Ch], 1
0x180022dc9  movzx   ecx, byte ptr [r9+8]
0x180022dce  mov     [r8+34h], cl
0x180022dd2  mov     [r8+8], rax
0x180022dd6  mov     [r8], rdi
0x180022dd9  mov     [r8+10h], rdi
0x180022ddd  movzx   ecx, byte ptr [r14+8]
0x180022de2  test    cl, cl
0x180022de4  jz      short loc_180022E11
0x180022de6  mov     edx, edi
0x180022de8  nop     dword ptr [rax+rax+00000000h]
0x180022df0  mov     [rax+2Ch], dil
0x180022df4  mov     dword ptr [rax+1Ch], 4
0x180022dfb  mov     [rax], rdi
0x180022dfe  mov     [rax+38h], rdi
0x180022e02  inc     edx
0x180022e04  add     rax, 58h ; 'X'
0x180022e08  movzx   ecx, byte ptr [r14+8]
0x180022e0d  cmp     edx, ecx
0x180022e0f  jl      short loc_180022DF0
0x180022e11  inc     r10d
0x180022e14  add     r8, 38h ; '8'
0x180022e18  movzx   ecx, byte ptr [r14]
0x180022e1c  cmp     r10d, ecx
0x180022e1f  jl      short loc_180022DC0
0x180022e21  mov     r11d, r15d
0x180022e24  add     r9, 38h ; '8'
0x180022e28  cmp     r15d, ebx
0x180022e2b  jl      loc_180022CA0
0x180022e31  mov     r10d, edi
0x180022e34  mov     r15, [r14+10h]
0x180022e38  mov     edx, edi
0x180022e3a  mov     [rsp+10118h+var_100E8], edx
0x180022e3e  mov     rbx, [rsp+10118h+var_100D0]
0x180022e43  mov     r13d, [rsp+10118h+var_100E0]
0x180022e48  jmp     short loc_180022E62
0x180022e4a  xor     edi, edi
0x180022e4c  mov     r10d, edi
0x180022e4f  mov     r15, [r14+10h]
0x180022e53  mov     edx, edi
0x180022e55  mov     [rsp+10118h+var_100E8], edx
0x180022e59  test    r8d, r8d
0x180022e5c  jz      loc_180023149
0x180022e62  cmp     r13d, 4
0x180022e66  jl      loc_180023594
0x180022e6c  movzx   ecx, byte ptr [rbx]
0x180022e6f  shl     ecx, 8
0x180022e72  movzx   eax, byte ptr [rbx+1]
0x180022e76  or      ecx, eax
0x180022e78  movzx   r8d, byte ptr [rbx+2]
0x180022e7d  shl     r8d, 8
0x180022e81  movzx   eax, byte ptr [rbx+3]
0x180022e85  or      r8d, eax
0x180022e88  cmp     ecx, 0FF01h
0x180022e8e  jnz     short loc_180022E96
0x180022e90  cmp     r8d, 8
0x180022e94  jmp     short loc_180022EAB
0x180022e96  cmp     ecx, 0FF11h
0x180022e9c  jnz     loc_180023594
0x180022ea2  lea     eax, [r8-8]
0x180022ea6  test    eax, 0FFFFFFF7h
0x180022eab  jnz     loc_180023594
0x180022eb1  lea     r9d, [r8+4]
0x180022eb5  cmp     r13d, r9d
0x180022eb8  jl      loc_180023594
0x180022ebe  movzx   ecx, byte ptr [rbx+0Ah]
0x180022ec2  shl     ecx, 8
0x180022ec5  movzx   eax, byte ptr [rbx+0Bh]
0x180022ec9  or      ecx, eax
0x180022ecb  cmp     r8d, 8
0x180022ecf  jnz     short loc_180022ED5
0x180022ed1  test    ecx, ecx
0x180022ed3  jmp     short loc_180022EE1
0x180022ed5  cmp     r8d, 10h
0x180022ed9  jnz     short loc_180022EE7
0x180022edb  cmp     ecx, 4000h
0x180022ee1  jnz     loc_180023594
0x180022ee7  movzx   ecx, byte ptr [rbx+9]
0x180022eeb  movzx   eax, byte ptr [rbx+8]
0x180022eef  shl     eax, 8
0x180022ef2  or      ecx, eax
0x180022ef4  cmp     ecx, edx
0x180022ef6  jnz     loc_180023594
0x180022efc  mov     eax, 0FFFFFFFCh
0x180022f01  sub     eax, r8d
0x180022f04  add     r13d, eax
0x180022f07  movzx   edx, byte ptr [rbx+4]
0x180022f0b  shl     edx, 8
0x180022f0e  movzx   eax, byte ptr [rbx+5]
0x180022f12  or      edx, eax
0x180022f14  shl     edx, 8
0x180022f17  movzx   eax, byte ptr [rbx+6]
0x180022f1b  or      edx, eax
0x180022f1d  shl     edx, 8
0x180022f20  movzx   eax, byte ptr [rbx+7]
0x180022f24  or      edx, eax
0x180022f26  mov     [r15+18h], edx
0x180022f2a  mov     eax, r10d
0x180022f2d  mov     [r15+10h], rax
0x180022f31  mov     [r15+28h], rdi
0x180022f35  cmp     r8d, 10h
0x180022f39  jnz     short loc_180022F87
0x180022f3b  movzx   ecx, byte ptr [rbx+12h]
0x180022f3f  shl     ecx, 8
0x180022f42  movzx   eax, byte ptr [rbx+13h]
0x180022f46  or      ecx, eax
0x180022f48  jnz     loc_180023594
0x180022f4e  mov     byte ptr [r15+20h], 1
0x180022f53  movzx   ecx, byte ptr [rbx+0Dh]
0x180022f57  movzx   eax, byte ptr [rbx+0Ch]
0x180022f5b  shl     eax, 8
0x180022f5e  or      ecx, eax
0x180022f60  shl     ecx, 8
0x180022f63  movzx   eax, byte ptr [rbx+0Eh]
0x180022f67  or      ecx, eax
0x180022f69  shl     ecx, 8
0x180022f6c  movzx   eax, byte ptr [rbx+0Fh]
0x180022f70  or      ecx, eax
0x180022f72  mov     [r15+30h], ecx
0x180022f76  movzx   ecx, byte ptr [rbx+11h]
0x180022f7a  movzx   eax, byte ptr [rbx+10h]
0x180022f7e  shl     ax, 8
0x180022f82  or      cx, ax
0x180022f85  jmp     short loc_180022F92
0x180022f87  mov     byte ptr [r15+20h], 0
0x180022f8c  mov     [r15+30h], edi
0x180022f90  mov     ecx, edi
0x180022f92  mov     [r15+34h], cx
0x180022f97  mov     eax, r9d
0x180022f9a  add     rbx, rax
0x180022f9d  add     r10d, edx
0x180022fa0  mov     [rsp+10118h+var_100D8], r10d
0x180022fa5  mov     r9d, edi
0x180022fa8  mov     rsi, [r15]
0x180022fab  mov     r12d, edi
0x180022fae  cmp     byte ptr [r14], 0
0x180022fb2  jbe     loc_180023128
0x180022fb8  nop     dword ptr [rax+rax+00000000h]
0x180022fc0  cmp     r13d, 0Ch
0x180022fc4  jl      loc_180023594
0x180022fca  movzx   ecx, byte ptr [rbx]
0x180022fcd  shl     ecx, 8
0x180022fd0  movzx   eax, byte ptr [rbx+1]
0x180022fd4  or      ecx, eax
0x180022fd6  movzx   edx, byte ptr [rbx+2]
0x180022fda  shl     edx, 8
0x180022fdd  movzx   eax, byte ptr [rbx+3]
0x180022fe1  or      edx, eax
0x180022fe3  cmp     ecx, 0FF02h
0x180022fe9  jz      short loc_180022FF7
0x180022feb  cmp     ecx, 0FF12h
0x180022ff1  jnz     loc_180023594
0x180022ff7  cmp     edx, 8
0x180022ffa  jnz     loc_180023594
0x180023000  movzx   eax, byte ptr [rbx+8]
0x180023004  shr     eax, 4
  ... truncated ...
```
