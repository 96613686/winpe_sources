# memmove

- ea: `0x14001afc0`
- end: `0x14001b26a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c190`
- `0x14000f3d0`
- `0x140016d80`
- `0x140016f30`
- `0x140017380`
- `0x1400183a0`
- `0x1400195d0`
- `0x140019848`
- `0x14001a160`
- `0x140029cd0`

## callees

- `0x14001afc0`

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
0x14001afc0  mov     rax, rcx
0x14001afc3  cmp     r8, 8
0x14001afc7  jb      short loc_14001B000
0x14001afc9  cmp     r8, 10h
0x14001afcd  ja      short loc_14001AFE0
0x14001afcf  mov     r11, [rdx]
0x14001afd2  mov     rdx, [rdx+r8-8]
0x14001afd7  mov     [rcx], r11
0x14001afda  mov     [rcx+r8-8], rdx
0x14001afdf  retn
0x14001afe0  cmp     r8, 20h ; ' '
0x14001afe4  ja      short loc_14001B040
0x14001afe6  movups  xmm0, xmmword ptr [rdx]
0x14001afe9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14001afef  movups  xmmword ptr [rcx], xmm0
0x14001aff2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14001aff8  retn
0x14001b000  test    r8, r8
0x14001b003  jz      short locret_14001B01A
0x14001b005  sub     rdx, rcx
0x14001b008  jb      short loc_14001B020
0x14001b00a  mov     r11b, [rcx+rdx]
0x14001b00e  inc     rcx
0x14001b011  dec     r8
0x14001b014  mov     [rcx-1], r11b
0x14001b018  jnz     short loc_14001B00A
0x14001b01a  retn
0x14001b020  add     rcx, r8
0x14001b023  mov     r11b, [rcx+rdx-1]
0x14001b028  dec     rcx
0x14001b02b  dec     r8
0x14001b02e  mov     [rcx], r11b
0x14001b031  jnz     short loc_14001B023
0x14001b033  retn
0x14001b040  lea     r11, [rdx+r8]
0x14001b044  sub     rdx, rcx
0x14001b047  jnb     short loc_14001B052
0x14001b049  cmp     r11, rcx
0x14001b04c  ja      loc_14001B1C0
0x14001b052  movups  xmm0, xmmword ptr [rcx+rdx]
0x14001b056  add     rcx, 10h
0x14001b05a  test    cl, 0Fh
0x14001b05d  jz      short loc_14001B071
0x14001b05f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001b063  movups  xmm1, xmmword ptr [rcx+rdx]
0x14001b067  movups  xmmword ptr [rax], xmm0
0x14001b06a  movaps  xmm0, xmm1
0x14001b06d  add     rcx, 10h
0x14001b071  add     r8, rax
0x14001b074  sub     r8, rcx
0x14001b077  mov     r9, r8
0x14001b07a  shr     r9, 6
0x14001b07e  jz      short loc_14001B0EF
0x14001b080  cmp     r9, 1000h
0x14001b087  ja      loc_14001B140
0x14001b08d  and     r8, 3Fh
0x14001b091  jmp     short loc_14001B0C0
0x14001b0c0  movups  xmm1, xmmword ptr [rcx+rdx]
0x14001b0c4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14001b0c9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14001b0ce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14001b0d3  movaps  xmmword ptr [rcx-10h], xmm0
0x14001b0d7  add     rcx, 40h ; '@'
0x14001b0db  dec     r9
0x14001b0de  movaps  xmmword ptr [rcx-40h], xmm1
0x14001b0e2  movaps  xmmword ptr [rcx-30h], xmm2
0x14001b0e6  movaps  xmmword ptr [rcx-20h], xmm3
0x14001b0ea  movaps  xmm0, xmm4
0x14001b0ed  jnz     short loc_14001B0C0
0x14001b0ef  mov     r9, r8
0x14001b0f2  shr     r9, 4
0x14001b0f6  jz      short loc_14001B111
0x14001b0f8  nop     dword ptr [rax+rax+00000000h]
0x14001b100  movaps  xmmword ptr [rcx-10h], xmm0
0x14001b104  movups  xmm0, xmmword ptr [rcx+rdx]
0x14001b108  add     rcx, 10h
0x14001b10c  dec     r9
0x14001b10f  jnz     short loc_14001B100
0x14001b111  and     r8, 0Fh
0x14001b115  jz      short loc_14001B125
0x14001b117  lea     r11, [rcx+r8-10h]
0x14001b11c  movups  xmm1, xmmword ptr [r11+rdx]
0x14001b121  movups  xmmword ptr [r11], xmm1
0x14001b125  movaps  xmmword ptr [rcx-10h], xmm0
0x14001b129  retn
0x14001b140  mov     r9, r8
0x14001b143  shr     r9, 6
0x14001b147  and     r8, 3Fh
0x14001b14b  prefetchnta byte ptr [rcx+rdx+40h]
0x14001b150  jmp     short loc_14001B180
0x14001b180  movups  xmm1, xmmword ptr [rcx+rdx]
0x14001b184  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14001b189  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14001b18e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14001b193  movntps xmmword ptr [rcx-10h], xmm0
0x14001b197  add     rcx, 40h ; '@'
0x14001b19b  prefetchnta byte ptr [rcx+rdx+40h]
0x14001b1a0  dec     r9
0x14001b1a3  movntps xmmword ptr [rcx-40h], xmm1
0x14001b1a7  movntps xmmword ptr [rcx-30h], xmm2
0x14001b1ab  movntps xmmword ptr [rcx-20h], xmm3
0x14001b1af  movaps  xmm0, xmm4
0x14001b1b2  jnz     short loc_14001B180
0x14001b1b4  sfence
0x14001b1b7  jmp     loc_14001B0EF
0x14001b1c0  add     rcx, r8
0x14001b1c3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14001b1c8  sub     rcx, 10h
0x14001b1cc  sub     r8, 10h
0x14001b1d0  test    cl, 0Fh
0x14001b1d3  jz      short loc_14001B1ED
0x14001b1d5  mov     r11, rcx
0x14001b1d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001b1dc  movups  xmm1, xmmword ptr [rcx+rdx]
0x14001b1e0  movups  xmmword ptr [r11], xmm0
0x14001b1e4  movaps  xmm0, xmm1
0x14001b1e7  mov     r8, rcx
0x14001b1ea  sub     r8, rax
0x14001b1ed  mov     r9, r8
0x14001b1f0  shr     r9, 6
0x14001b1f4  jz      short loc_14001B22F
0x14001b1f6  and     r8, 3Fh
0x14001b1fa  jmp     short loc_14001B200
0x14001b200  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14001b205  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14001b20a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14001b20f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14001b214  movaps  xmmword ptr [rcx], xmm0
0x14001b217  sub     rcx, 40h ; '@'
0x14001b21b  dec     r9
0x14001b21e  movaps  xmmword ptr [rcx+30h], xmm1
0x14001b222  movaps  xmmword ptr [rcx+20h], xmm2
0x14001b226  movaps  xmmword ptr [rcx+10h], xmm3
0x14001b22a  movaps  xmm0, xmm4
0x14001b22d  jnz     short loc_14001B200
0x14001b22f  mov     r9, r8
0x14001b232  shr     r9, 4
0x14001b236  jz      short loc_14001B251
0x14001b238  nop     dword ptr [rax+rax+00000000h]
0x14001b240  movaps  xmmword ptr [rcx], xmm0
0x14001b243  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14001b248  sub     rcx, 10h
0x14001b24c  dec     r9
0x14001b24f  jnz     short loc_14001B240
0x14001b251  and     r8, 0Fh
0x14001b255  jz      short loc_14001B266
0x14001b257  mov     r11, rcx
0x14001b25a  sub     r11, r8
0x14001b25d  movups  xmm1, xmmword ptr [r11+rdx]
0x14001b262  movups  xmmword ptr [r11], xmm1
0x14001b266  movaps  xmmword ptr [rcx], xmm0
0x14001b269  retn
```
