# memmove

- ea: `0x18001bc00`
- end: `0x18001beaa`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b0c`
- `0x1800040dc`
- `0x180009434`
- `0x18000a864`
- `0x18000a9e4`
- `0x18000acbc`
- `0x18000ce9c`
- `0x18000da60`
- `0x18000e8d4`
- `0x18001ad74`
- `0x18002b41c`
- `0x18002b4e0`
- `0x18002c7e0`

## callees

- `0x18001bc00`

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
0x18001bc00  mov     rax, rcx
0x18001bc03  cmp     r8, 8
0x18001bc07  jb      short loc_18001BC40
0x18001bc09  cmp     r8, 10h
0x18001bc0d  ja      short loc_18001BC20
0x18001bc0f  mov     r11, [rdx]
0x18001bc12  mov     rdx, [rdx+r8-8]
0x18001bc17  mov     [rcx], r11
0x18001bc1a  mov     [rcx+r8-8], rdx
0x18001bc1f  retn
0x18001bc20  cmp     r8, 20h ; ' '
0x18001bc24  ja      short loc_18001BC80
0x18001bc26  movups  xmm0, xmmword ptr [rdx]
0x18001bc29  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x18001bc2f  movups  xmmword ptr [rcx], xmm0
0x18001bc32  movups  xmmword ptr [rcx+r8-10h], xmm1
0x18001bc38  retn
0x18001bc40  test    r8, r8
0x18001bc43  jz      short locret_18001BC5A
0x18001bc45  sub     rdx, rcx
0x18001bc48  jb      short loc_18001BC60
0x18001bc4a  mov     r11b, [rcx+rdx]
0x18001bc4e  inc     rcx
0x18001bc51  dec     r8
0x18001bc54  mov     [rcx-1], r11b
0x18001bc58  jnz     short loc_18001BC4A
0x18001bc5a  retn
0x18001bc60  add     rcx, r8
0x18001bc63  mov     r11b, [rcx+rdx-1]
0x18001bc68  dec     rcx
0x18001bc6b  dec     r8
0x18001bc6e  mov     [rcx], r11b
0x18001bc71  jnz     short loc_18001BC63
0x18001bc73  retn
0x18001bc80  lea     r11, [rdx+r8]
0x18001bc84  sub     rdx, rcx
0x18001bc87  jnb     short loc_18001BC92
0x18001bc89  cmp     r11, rcx
0x18001bc8c  ja      loc_18001BE00
0x18001bc92  movups  xmm0, xmmword ptr [rcx+rdx]
0x18001bc96  add     rcx, 10h
0x18001bc9a  test    cl, 0Fh
0x18001bc9d  jz      short loc_18001BCB1
0x18001bc9f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001bca3  movups  xmm1, xmmword ptr [rcx+rdx]
0x18001bca7  movups  xmmword ptr [rax], xmm0
0x18001bcaa  movaps  xmm0, xmm1
0x18001bcad  add     rcx, 10h
0x18001bcb1  add     r8, rax
0x18001bcb4  sub     r8, rcx
0x18001bcb7  mov     r9, r8
0x18001bcba  shr     r9, 6
0x18001bcbe  jz      short loc_18001BD2F
0x18001bcc0  cmp     r9, 1000h
0x18001bcc7  ja      loc_18001BD80
0x18001bccd  and     r8, 3Fh
0x18001bcd1  jmp     short loc_18001BD00
0x18001bd00  movups  xmm1, xmmword ptr [rcx+rdx]
0x18001bd04  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x18001bd09  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x18001bd0e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x18001bd13  movaps  xmmword ptr [rcx-10h], xmm0
0x18001bd17  add     rcx, 40h ; '@'
0x18001bd1b  dec     r9
0x18001bd1e  movaps  xmmword ptr [rcx-40h], xmm1
0x18001bd22  movaps  xmmword ptr [rcx-30h], xmm2
0x18001bd26  movaps  xmmword ptr [rcx-20h], xmm3
0x18001bd2a  movaps  xmm0, xmm4
0x18001bd2d  jnz     short loc_18001BD00
0x18001bd2f  mov     r9, r8
0x18001bd32  shr     r9, 4
0x18001bd36  jz      short loc_18001BD51
0x18001bd38  nop     dword ptr [rax+rax+00000000h]
0x18001bd40  movaps  xmmword ptr [rcx-10h], xmm0
0x18001bd44  movups  xmm0, xmmword ptr [rcx+rdx]
0x18001bd48  add     rcx, 10h
0x18001bd4c  dec     r9
0x18001bd4f  jnz     short loc_18001BD40
0x18001bd51  and     r8, 0Fh
0x18001bd55  jz      short loc_18001BD65
0x18001bd57  lea     r11, [rcx+r8-10h]
0x18001bd5c  movups  xmm1, xmmword ptr [r11+rdx]
0x18001bd61  movups  xmmword ptr [r11], xmm1
0x18001bd65  movaps  xmmword ptr [rcx-10h], xmm0
0x18001bd69  retn
0x18001bd80  mov     r9, r8
0x18001bd83  shr     r9, 6
0x18001bd87  and     r8, 3Fh
0x18001bd8b  prefetchnta byte ptr [rcx+rdx+40h]
0x18001bd90  jmp     short loc_18001BDC0
0x18001bdc0  movups  xmm1, xmmword ptr [rcx+rdx]
0x18001bdc4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x18001bdc9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x18001bdce  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x18001bdd3  movntps xmmword ptr [rcx-10h], xmm0
0x18001bdd7  add     rcx, 40h ; '@'
0x18001bddb  prefetchnta byte ptr [rcx+rdx+40h]
0x18001bde0  dec     r9
0x18001bde3  movntps xmmword ptr [rcx-40h], xmm1
0x18001bde7  movntps xmmword ptr [rcx-30h], xmm2
0x18001bdeb  movntps xmmword ptr [rcx-20h], xmm3
0x18001bdef  movaps  xmm0, xmm4
0x18001bdf2  jnz     short loc_18001BDC0
0x18001bdf4  sfence
0x18001bdf7  jmp     loc_18001BD2F
0x18001be00  add     rcx, r8
0x18001be03  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18001be08  sub     rcx, 10h
0x18001be0c  sub     r8, 10h
0x18001be10  test    cl, 0Fh
0x18001be13  jz      short loc_18001BE2D
0x18001be15  mov     r11, rcx
0x18001be18  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001be1c  movups  xmm1, xmmword ptr [rcx+rdx]
0x18001be20  movups  xmmword ptr [r11], xmm0
0x18001be24  movaps  xmm0, xmm1
0x18001be27  mov     r8, rcx
0x18001be2a  sub     r8, rax
0x18001be2d  mov     r9, r8
0x18001be30  shr     r9, 6
0x18001be34  jz      short loc_18001BE6F
0x18001be36  and     r8, 3Fh
0x18001be3a  jmp     short loc_18001BE40
0x18001be40  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x18001be45  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x18001be4a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x18001be4f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x18001be54  movaps  xmmword ptr [rcx], xmm0
0x18001be57  sub     rcx, 40h ; '@'
0x18001be5b  dec     r9
0x18001be5e  movaps  xmmword ptr [rcx+30h], xmm1
0x18001be62  movaps  xmmword ptr [rcx+20h], xmm2
0x18001be66  movaps  xmmword ptr [rcx+10h], xmm3
0x18001be6a  movaps  xmm0, xmm4
0x18001be6d  jnz     short loc_18001BE40
0x18001be6f  mov     r9, r8
0x18001be72  shr     r9, 4
0x18001be76  jz      short loc_18001BE91
0x18001be78  nop     dword ptr [rax+rax+00000000h]
0x18001be80  movaps  xmmword ptr [rcx], xmm0
0x18001be83  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18001be88  sub     rcx, 10h
0x18001be8c  dec     r9
0x18001be8f  jnz     short loc_18001BE80
0x18001be91  and     r8, 0Fh
0x18001be95  jz      short loc_18001BEA6
0x18001be97  mov     r11, rcx
0x18001be9a  sub     r11, r8
0x18001be9d  movups  xmm1, xmmword ptr [r11+rdx]
0x18001bea2  movups  xmmword ptr [r11], xmm1
0x18001bea6  movaps  xmmword ptr [rcx], xmm0
0x18001bea9  retn
```
