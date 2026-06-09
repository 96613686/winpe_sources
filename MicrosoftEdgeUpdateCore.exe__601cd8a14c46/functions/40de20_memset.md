# _memset

- ea: `0x40de20`
- end: `0x40df7a`
- name: `_memset`
- size: `346`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `36`
- callee_count: `1`
- tags: ``

## callers

- `0x4018e5`
- `0x402110`
- `0x4023c6`
- `0x403b59`
- `0x403e80`
- `0x404994`
- `0x404a78`
- `0x404ad0`
- `0x4059df`
- `0x405cdb`
- `0x40637c`
- `0x40645f`
- `0x4064e1`
- `0x406d01`
- `0x407db1`
- `0x4081e3`
- `0x40831e`
- `0x4084ec`
- `0x408b48`
- `0x408d4a`
- `0x408f50`
- `0x40b888`
- `0x40b905`
- `0x40c440`
- `0x40cfc2`
- `0x40d86c`
- `0x40d987`
- `0x4101bd`
- `0x410456`
- `0x41451b`
- `0x41491b`
- `0x414b0e`
- `0x416715`
- `0x4173f6`
- `0x417986`
- `0x419c78`

## callees

- `0x40de20`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  size_t v3; // ecx
  __m128i *v4; // edi
  unsigned int v5; // eax
  __m128i v7; // xmm0
  __m128i *v8; // edi

  v3 = Size;
  v4 = (__m128i *)a1;
  if ( !Size )
    return a1;
  v5 = 16843009 * (unsigned __int8)Val;
  if ( Size <= 0x20 )
    goto SmallMov;
  if ( Size >= 0x80 )
  {
    if ( _bittest(&dword_43E010, 1u) )
    {
      memset(a1, Val, Size);
      return a1;
    }
    if ( !_bittest(&dword_43D010, 1u) )
      goto SmallMov;
    v7 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v5), 0);
    *(__m128i *)a1 = v7;
    v4 = (__m128i *)(((unsigned int)a1 + 16) & 0xFFFFFFF0);
    v3 = (_BYTE *)a1 + Size - (_BYTE *)v4;
    if ( v3 > 0x80 )
    {
      do
      {
        *v4 = v7;
        v4[1] = v7;
        v4[2] = v7;
        v4[3] = v7;
        v4[4] = v7;
        v4[5] = v7;
        v4[6] = v7;
        v4[7] = v7;
        v4 += 8;
        v3 -= 128;
      }
      while ( (v3 & 0xFFFFFF00) != 0 );
      goto XmmSmallLoop;
    }
  }
  if ( !_bittest(&dword_43D010, 1u) )
  {
SmallMov:
    while ( (v3 & 3) != 0 )
    {
      v4->m128i_i8[0] = Val;
      v4 = (__m128i *)((char *)v4 + 1);
      --v3;
    }
    if ( (v3 & 4) != 0 )
    {
      v4->m128i_i32[0] = v5;
      v4 = (__m128i *)((char *)v4 + 4);
      v3 -= 4;
    }
    for ( ; (v3 & 0xFFFFFFF8) != 0; v3 -= 8 )
    {
      v4->m128i_i32[0] = v5;
      v4->m128i_i32[1] = v5;
      v4 = (__m128i *)((char *)v4 + 8);
    }
    return a1;
  }
  v7 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v5), 0);
XmmSmallLoop:
  if ( v3 < 0x20 )
    goto XMMTrailingBytes;
  do
  {
    *v4 = v7;
    v4[1] = v7;
    v4 += 2;
    v3 -= 32;
  }
  while ( v3 >= 0x20 );
  if ( (v3 & 0x1F) != 0 )
  {
XMMTrailingBytes:
    v8 = (__m128i *)((char *)v4 + v3 - 32);
    *v8 = v7;
    v8[1] = v7;
    return a1;
  }
  return a1;
}

```

## disassembly

```asm
0x40de20  mov     ecx, [esp+Size]
0x40de24  movzx   eax, byte ptr [esp+Val]
0x40de29  mov     edx, edi
0x40de2b  mov     edi, [esp+arg_0]
0x40de2f  test    ecx, ecx
0x40de31  jz      toend
0x40de37  imul    eax, 1010101h
0x40de3d  cmp     ecx, 20h ; ' '
0x40de40  jbe     SmallMov
0x40de46  cmp     ecx, 80h
0x40de4c  jb      XmmMovSmall
0x40de52  bt      dword_43E010, 1
0x40de5a  jnb     short XMMMov
0x40de5c  rep stosb
0x40de5e  mov     eax, [esp+arg_0]
0x40de62  mov     edi, edx
0x40de64  retn
0x40de65  bt      dword_43D010, 1
0x40de6d  jnb     SmallMov
0x40de73  movd    xmm0, eax
0x40de77  pshufd  xmm0, xmm0, 0
0x40de7c  add     ecx, edi
0x40de7e  movups  xmmword ptr [edi], xmm0
0x40de81  add     edi, 10h
0x40de84  and     edi, 0FFFFFFF0h
0x40de87  sub     ecx, edi
0x40de89  cmp     ecx, 80h
0x40de8f  jbe     short XmmMovSmall
0x40de91  lea     esp, [esp+0]
0x40de98  lea     esp, [esp+0]
0x40de9f  nop
0x40dea0  movdqa  xmmword ptr [edi], xmm0
0x40dea4  movdqa  xmmword ptr [edi+10h], xmm0
0x40dea9  movdqa  xmmword ptr [edi+20h], xmm0
0x40deae  movdqa  xmmword ptr [edi+30h], xmm0
0x40deb3  movdqa  xmmword ptr [edi+40h], xmm0
0x40deb8  movdqa  xmmword ptr [edi+50h], xmm0
0x40debd  movdqa  xmmword ptr [edi+60h], xmm0
0x40dec2  movdqa  xmmword ptr [edi+70h], xmm0
0x40dec7  lea     edi, [edi+80h]
0x40decd  sub     ecx, 80h
0x40ded3  test    ecx, 0FFFFFF00h
0x40ded9  jnz     short LargeRangeBytes
0x40dedb  jmp     short XmmSmallLoop
0x40dedd  bt      dword_43D010, 1
0x40dee5  jnb     short SmallMov
0x40dee7  movd    xmm0, eax
0x40deeb  pshufd  xmm0, xmm0, 0
0x40def0  cmp     ecx, 20h ; ' '
0x40def3  jb      short XMMTrailingBytes
0x40def5  movdqu  xmmword ptr [edi], xmm0
0x40def9  movdqu  xmmword ptr [edi+10h], xmm0
0x40defe  add     edi, 20h ; ' '
0x40df01  sub     ecx, 20h ; ' '
0x40df04  cmp     ecx, 20h ; ' '
0x40df07  jnb     short MidRangeBytes
0x40df09  test    ecx, 1Fh
0x40df0f  jz      short toend
0x40df11  lea     edi, [edi+ecx-20h]
0x40df15  movdqu  xmmword ptr [edi], xmm0
0x40df19  movdqu  xmmword ptr [edi+10h], xmm0
0x40df1e  mov     eax, [esp+arg_0]
0x40df22  mov     edi, edx
0x40df24  retn
0x40df25  test    ecx, 3
0x40df2b  jz      short DwordTest
0x40df2d  mov     [edi], al
0x40df2f  inc     edi
0x40df30  sub     ecx, 1
0x40df33  test    ecx, 3
0x40df39  jnz     short ByteLoop
0x40df3b  test    ecx, 4
0x40df41  jz      short QwordTest
0x40df43  mov     [edi], eax
0x40df45  add     edi, 4
0x40df48  sub     ecx, 4
0x40df4b  test    ecx, 0FFFFFFF8h
0x40df51  jz      short toend
0x40df53  lea     esp, [esp+0]
0x40df5a  lea     ebx, [ebx+0]
0x40df60  mov     [edi], eax
0x40df62  mov     [edi+4], eax
0x40df65  add     edi, 8
0x40df68  sub     ecx, 8
0x40df6b  test    ecx, 0FFFFFFF8h
0x40df71  jnz     short QwordLoop
0x40df73  mov     eax, [esp+arg_0]
0x40df77  mov     edi, edx
0x40df79  retn
```
