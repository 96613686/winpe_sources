# memmove

- ea: `0x14000dec0`
- end: `0x14000e16a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400085b4`
- `0x14000b338`
- `0x14000c908`
- `0x140017f30`
- `0x14001c0f0`

## callees

- `0x14000dec0`

## pseudocode

```c
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  void *result; // rax
  __int64 v4; // r11
  __int64 v5; // rdx
  __int128 v6; // xmm1
  bool v7; // cf
  signed __int64 v8; // rdx
  char v9; // r11
  _BYTE *v10; // rcx
  char v11; // r11
  char *v12; // r11
  signed __int64 v13; // rdx
  __m128 v14; // xmm0
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  __m128 v17; // xmm1
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r9
  __int128 v20; // xmm1
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __m128 v23; // xmm4
  unsigned __int64 j; // r9
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  __m128 v27; // xmm1
  __m128 v28; // xmm2
  __m128 v29; // xmm3
  __m128 v30; // xmm4
  char *v31; // rcx
  __int128 v32; // xmm0
  unsigned __int64 v33; // rcx
  size_t v34; // r8
  _OWORD *v35; // r11
  __int128 v36; // xmm1
  size_t v37; // r9
  __int128 v38; // xmm1
  __int128 v39; // xmm2
  __int128 v40; // xmm3
  __int128 v41; // xmm4
  size_t i; // r9
  size_t v43; // r8

  result = a1;
  if ( Size < 8 )
  {
    if ( Size )
    {
      v7 = Src < a1;
      v8 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 )
      {
        v10 = (char *)a1 + Size;
        do
        {
          v11 = v10[v8 - 1];
          --v10;
          --Size;
          *v10 = v11;
        }
        while ( Size );
      }
      else
      {
        do
        {
          v9 = *((_BYTE *)a1 + v8);
          a1 = (char *)a1 + 1;
          --Size;
          *((char *)a1 - 1) = v9;
        }
        while ( Size );
      }
    }
  }
  else if ( Size > 0x10 )
  {
    if ( Size > 0x20 )
    {
      v12 = (char *)Src + Size;
      v7 = Src < a1;
      v13 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 && v12 > a1 )
      {
        v31 = (char *)a1 + Size;
        v32 = *(_OWORD *)&v31[v13 - 16];
        v33 = (unsigned __int64)(v31 - 16);
        v34 = Size - 16;
        if ( (v33 & 0xF) != 0 )
        {
          v35 = (_OWORD *)v33;
          v33 &= 0xFFFFFFFFFFFFFFF0uLL;
          v36 = *(_OWORD *)(v33 + v13);
          *v35 = v32;
          v32 = v36;
          v34 = v33 - (_QWORD)result;
        }
        v37 = v34 >> 6;
        if ( v34 >> 6 )
        {
          v34 &= 0x3Fu;
          do
          {
            v38 = *(_OWORD *)(v33 + v13 - 16);
            v39 = *(_OWORD *)(v33 + v13 - 32);
            v40 = *(_OWORD *)(v33 + v13 - 48);
            v41 = *(_OWORD *)(v33 + v13 - 64);
            *(_OWORD *)v33 = v32;
            v33 -= 64LL;
            --v37;
            *(_OWORD *)(v33 + 48) = v38;
            *(_OWORD *)(v33 + 32) = v39;
            *(_OWORD *)(v33 + 16) = v40;
            v32 = v41;
          }
          while ( v37 );
        }
        for ( i = v34 >> 4; i; --i )
        {
          *(_OWORD *)v33 = v32;
          v32 = *(_OWORD *)(v33 + v13 - 16);
          v33 -= 16LL;
        }
        v43 = v34 & 0xF;
        if ( v43 )
          *(_OWORD *)(v33 - v43) = *(_OWORD *)(v33 - v43 + v13);
        *(_OWORD *)v33 = v32;
      }
      else
      {
        v14 = *(__m128 *)((char *)a1 + v13);
        v15 = (unsigned __int64)a1 + 16;
        if ( (v15 & 0xF) != 0 )
        {
          v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
          v17 = *(__m128 *)(v16 + v13);
          *(__m128 *)result = v14;
          v14 = v17;
          v15 = v16 + 16;
        }
        v18 = (unsigned __int64)result + Size - v15;
        v19 = v18 >> 6;
        if ( v18 >> 6 )
        {
          if ( v19 > 0x1000 )
          {
            v26 = v18 >> 6;
            v18 &= 0x3Fu;
            _mm_prefetch((const char *)(v15 + v13 + 64), 0);
            do
            {
              v27 = *(__m128 *)(v15 + v13);
              v28 = *(__m128 *)(v15 + v13 + 16);
              v29 = *(__m128 *)(v15 + v13 + 32);
              v30 = *(__m128 *)(v15 + v13 + 48);
              _mm_stream_ps((float *)(v15 - 16), v14);
              v15 += 64LL;
              _mm_prefetch((const char *)(v15 + v13 + 64), 0);
              --v26;
              _mm_stream_ps((float *)(v15 - 64), v27);
              _mm_stream_ps((float *)(v15 - 48), v28);
              _mm_stream_ps((float *)(v15 - 32), v29);
              v14 = v30;
            }
            while ( v26 );
            _mm_sfence();
          }
          else
          {
            v18 &= 0x3Fu;
            do
            {
              v20 = *(_OWORD *)(v15 + v13);
              v21 = *(_OWORD *)(v15 + v13 + 16);
              v22 = *(_OWORD *)(v15 + v13 + 32);
              v23 = *(__m128 *)(v15 + v13 + 48);
              *(__m128 *)(v15 - 16) = v14;
              v15 += 64LL;
              --v19;
              *(_OWORD *)(v15 - 64) = v20;
              *(_OWORD *)(v15 - 48) = v21;
              *(_OWORD *)(v15 - 32) = v22;
              v14 = v23;
            }
            while ( v19 );
          }
        }
        for ( j = v18 >> 4; j; --j )
        {
          *(__m128 *)(v15 - 16) = v14;
          v14 = *(__m128 *)(v15 + v13);
          v15 += 16LL;
        }
        v25 = v18 & 0xF;
        if ( v25 )
          *(_OWORD *)(v15 + v25 - 16) = *(_OWORD *)(v15 + v25 - 16 + v13);
        *(__m128 *)(v15 - 16) = v14;
      }
    }
    else
    {
      v6 = *(_OWORD *)((char *)Src + Size - 16);
      *(_OWORD *)a1 = *(_OWORD *)Src;
      *(_OWORD *)((char *)a1 + Size - 16) = v6;
    }
  }
  else
  {
    v4 = *(_QWORD *)Src;
    v5 = *(_QWORD *)((char *)Src + Size - 8);
    *(_QWORD *)a1 = v4;
    *(_QWORD *)((char *)a1 + Size - 8) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000dec0  mov     rax, rcx
0x14000dec3  cmp     r8, 8
0x14000dec7  jb      short loc_14000DF00
0x14000dec9  cmp     r8, 10h
0x14000decd  ja      short loc_14000DEE0
0x14000decf  mov     r11, [rdx]
0x14000ded2  mov     rdx, [rdx+r8-8]
0x14000ded7  mov     [rcx], r11
0x14000deda  mov     [rcx+r8-8], rdx
0x14000dedf  retn
0x14000dee0  cmp     r8, 20h ; ' '
0x14000dee4  ja      short loc_14000DF40
0x14000dee6  movups  xmm0, xmmword ptr [rdx]
0x14000dee9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14000deef  movups  xmmword ptr [rcx], xmm0
0x14000def2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14000def8  retn
0x14000df00  test    r8, r8
0x14000df03  jz      short locret_14000DF1A
0x14000df05  sub     rdx, rcx
0x14000df08  jb      short loc_14000DF20
0x14000df0a  mov     r11b, [rcx+rdx]
0x14000df0e  inc     rcx
0x14000df11  dec     r8
0x14000df14  mov     [rcx-1], r11b
0x14000df18  jnz     short loc_14000DF0A
0x14000df1a  retn
0x14000df20  add     rcx, r8
0x14000df23  mov     r11b, [rcx+rdx-1]
0x14000df28  dec     rcx
0x14000df2b  dec     r8
0x14000df2e  mov     [rcx], r11b
0x14000df31  jnz     short loc_14000DF23
0x14000df33  retn
0x14000df40  lea     r11, [rdx+r8]
0x14000df44  sub     rdx, rcx
0x14000df47  jnb     short loc_14000DF52
0x14000df49  cmp     r11, rcx
0x14000df4c  ja      loc_14000E0C0
0x14000df52  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000df56  add     rcx, 10h
0x14000df5a  test    cl, 0Fh
0x14000df5d  jz      short loc_14000DF71
0x14000df5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000df63  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000df67  movups  xmmword ptr [rax], xmm0
0x14000df6a  movaps  xmm0, xmm1
0x14000df6d  add     rcx, 10h
0x14000df71  add     r8, rax
0x14000df74  sub     r8, rcx
0x14000df77  mov     r9, r8
0x14000df7a  shr     r9, 6
0x14000df7e  jz      short loc_14000DFEF
0x14000df80  cmp     r9, 1000h
0x14000df87  ja      loc_14000E040
0x14000df8d  and     r8, 3Fh
0x14000df91  jmp     short loc_14000DFC0
0x14000dfc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000dfc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000dfc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000dfce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000dfd3  movaps  xmmword ptr [rcx-10h], xmm0
0x14000dfd7  add     rcx, 40h ; '@'
0x14000dfdb  dec     r9
0x14000dfde  movaps  xmmword ptr [rcx-40h], xmm1
0x14000dfe2  movaps  xmmword ptr [rcx-30h], xmm2
0x14000dfe6  movaps  xmmword ptr [rcx-20h], xmm3
0x14000dfea  movaps  xmm0, xmm4
0x14000dfed  jnz     short loc_14000DFC0
0x14000dfef  mov     r9, r8
0x14000dff2  shr     r9, 4
0x14000dff6  jz      short loc_14000E011
0x14000dff8  nop     dword ptr [rax+rax+00000000h]
0x14000e000  movaps  xmmword ptr [rcx-10h], xmm0
0x14000e004  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000e008  add     rcx, 10h
0x14000e00c  dec     r9
0x14000e00f  jnz     short loc_14000E000
0x14000e011  and     r8, 0Fh
0x14000e015  jz      short loc_14000E025
0x14000e017  lea     r11, [rcx+r8-10h]
0x14000e01c  movups  xmm1, xmmword ptr [r11+rdx]
0x14000e021  movups  xmmword ptr [r11], xmm1
0x14000e025  movaps  xmmword ptr [rcx-10h], xmm0
0x14000e029  retn
0x14000e040  mov     r9, r8
0x14000e043  shr     r9, 6
0x14000e047  and     r8, 3Fh
0x14000e04b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000e050  jmp     short loc_14000E080
0x14000e080  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000e084  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000e089  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000e08e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000e093  movntps xmmword ptr [rcx-10h], xmm0
0x14000e097  add     rcx, 40h ; '@'
0x14000e09b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000e0a0  dec     r9
0x14000e0a3  movntps xmmword ptr [rcx-40h], xmm1
0x14000e0a7  movntps xmmword ptr [rcx-30h], xmm2
0x14000e0ab  movntps xmmword ptr [rcx-20h], xmm3
0x14000e0af  movaps  xmm0, xmm4
0x14000e0b2  jnz     short loc_14000E080
0x14000e0b4  sfence
0x14000e0b7  jmp     loc_14000DFEF
0x14000e0c0  add     rcx, r8
0x14000e0c3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000e0c8  sub     rcx, 10h
0x14000e0cc  sub     r8, 10h
0x14000e0d0  test    cl, 0Fh
0x14000e0d3  jz      short loc_14000E0ED
0x14000e0d5  mov     r11, rcx
0x14000e0d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000e0dc  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000e0e0  movups  xmmword ptr [r11], xmm0
0x14000e0e4  movaps  xmm0, xmm1
0x14000e0e7  mov     r8, rcx
0x14000e0ea  sub     r8, rax
0x14000e0ed  mov     r9, r8
0x14000e0f0  shr     r9, 6
0x14000e0f4  jz      short loc_14000E12F
0x14000e0f6  and     r8, 3Fh
0x14000e0fa  jmp     short loc_14000E100
0x14000e100  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14000e105  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000e10a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000e10f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14000e114  movaps  xmmword ptr [rcx], xmm0
0x14000e117  sub     rcx, 40h ; '@'
0x14000e11b  dec     r9
0x14000e11e  movaps  xmmword ptr [rcx+30h], xmm1
0x14000e122  movaps  xmmword ptr [rcx+20h], xmm2
0x14000e126  movaps  xmmword ptr [rcx+10h], xmm3
0x14000e12a  movaps  xmm0, xmm4
0x14000e12d  jnz     short loc_14000E100
0x14000e12f  mov     r9, r8
0x14000e132  shr     r9, 4
0x14000e136  jz      short loc_14000E151
0x14000e138  nop     dword ptr [rax+rax+00000000h]
0x14000e140  movaps  xmmword ptr [rcx], xmm0
0x14000e143  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000e148  sub     rcx, 10h
0x14000e14c  dec     r9
0x14000e14f  jnz     short loc_14000E140
0x14000e151  and     r8, 0Fh
0x14000e155  jz      short loc_14000E166
0x14000e157  mov     r11, rcx
0x14000e15a  sub     r11, r8
0x14000e15d  movups  xmm1, xmmword ptr [r11+rdx]
0x14000e162  movups  xmmword ptr [r11], xmm1
0x14000e166  movaps  xmmword ptr [rcx], xmm0
0x14000e169  retn
```
