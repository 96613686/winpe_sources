# _memset

- ea: `0x40d0c0`
- end: `0x40d21a`
- name: `_memset`
- size: `346`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x4091fd`
- `0x4092c3`
- `0x4099f6`
- `0x40a9eb`
- `0x40aab8`
- `0x40bd55`
- `0x40be70`
- `0x40dca8`
- `0x4106fb`
- `0x410afb`
- `0x410cee`
- `0x4116ed`
- `0x411fa6`

## callees

- `0x40d0c0`

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
    if ( _bittest(&dword_417D10, 1u) )
    {
      memset(a1, Val, Size);
      return a1;
    }
    if ( !_bittest(&dword_417010, 1u) )
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
  if ( !_bittest(&dword_417010, 1u) )
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
0x40d0c0  mov     ecx, [esp+Size]
0x40d0c4  movzx   eax, byte ptr [esp+Val]
0x40d0c9  mov     edx, edi
0x40d0cb  mov     edi, [esp+arg_0]
0x40d0cf  test    ecx, ecx
0x40d0d1  jz      toend
0x40d0d7  imul    eax, 1010101h
0x40d0dd  cmp     ecx, 20h ; ' '
0x40d0e0  jbe     SmallMov
0x40d0e6  cmp     ecx, 80h
0x40d0ec  jb      XmmMovSmall
0x40d0f2  bt      dword_417D10, 1
0x40d0fa  jnb     short XMMMov
0x40d0fc  rep stosb
0x40d0fe  mov     eax, [esp+arg_0]
0x40d102  mov     edi, edx
0x40d104  retn
0x40d105  bt      dword_417010, 1
0x40d10d  jnb     SmallMov
0x40d113  movd    xmm0, eax
0x40d117  pshufd  xmm0, xmm0, 0
0x40d11c  add     ecx, edi
0x40d11e  movups  xmmword ptr [edi], xmm0
0x40d121  add     edi, 10h
0x40d124  and     edi, 0FFFFFFF0h
0x40d127  sub     ecx, edi
0x40d129  cmp     ecx, 80h
0x40d12f  jbe     short XmmMovSmall
0x40d131  lea     esp, [esp+0]
0x40d138  lea     esp, [esp+0]
0x40d13f  nop
0x40d140  movdqa  xmmword ptr [edi], xmm0
0x40d144  movdqa  xmmword ptr [edi+10h], xmm0
0x40d149  movdqa  xmmword ptr [edi+20h], xmm0
0x40d14e  movdqa  xmmword ptr [edi+30h], xmm0
0x40d153  movdqa  xmmword ptr [edi+40h], xmm0
0x40d158  movdqa  xmmword ptr [edi+50h], xmm0
0x40d15d  movdqa  xmmword ptr [edi+60h], xmm0
0x40d162  movdqa  xmmword ptr [edi+70h], xmm0
0x40d167  lea     edi, [edi+80h]
0x40d16d  sub     ecx, 80h
0x40d173  test    ecx, 0FFFFFF00h
0x40d179  jnz     short LargeRangeBytes
0x40d17b  jmp     short XmmSmallLoop
0x40d17d  bt      dword_417010, 1
0x40d185  jnb     short SmallMov
0x40d187  movd    xmm0, eax
0x40d18b  pshufd  xmm0, xmm0, 0
0x40d190  cmp     ecx, 20h ; ' '
0x40d193  jb      short XMMTrailingBytes
0x40d195  movdqu  xmmword ptr [edi], xmm0
0x40d199  movdqu  xmmword ptr [edi+10h], xmm0
0x40d19e  add     edi, 20h ; ' '
0x40d1a1  sub     ecx, 20h ; ' '
0x40d1a4  cmp     ecx, 20h ; ' '
0x40d1a7  jnb     short MidRangeBytes
0x40d1a9  test    ecx, 1Fh
0x40d1af  jz      short toend
0x40d1b1  lea     edi, [edi+ecx-20h]
0x40d1b5  movdqu  xmmword ptr [edi], xmm0
0x40d1b9  movdqu  xmmword ptr [edi+10h], xmm0
0x40d1be  mov     eax, [esp+arg_0]
0x40d1c2  mov     edi, edx
0x40d1c4  retn
0x40d1c5  test    ecx, 3
0x40d1cb  jz      short DwordTest
0x40d1cd  mov     [edi], al
0x40d1cf  inc     edi
0x40d1d0  sub     ecx, 1
0x40d1d3  test    ecx, 3
0x40d1d9  jnz     short ByteLoop
0x40d1db  test    ecx, 4
0x40d1e1  jz      short QwordTest
0x40d1e3  mov     [edi], eax
0x40d1e5  add     edi, 4
0x40d1e8  sub     ecx, 4
0x40d1eb  test    ecx, 0FFFFFFF8h
0x40d1f1  jz      short toend
0x40d1f3  lea     esp, [esp+0]
0x40d1fa  lea     ebx, [ebx+0]
0x40d200  mov     [edi], eax
0x40d202  mov     [edi+4], eax
0x40d205  add     edi, 8
0x40d208  sub     ecx, 8
0x40d20b  test    ecx, 0FFFFFFF8h
0x40d211  jnz     short QwordLoop
0x40d213  mov     eax, [esp+arg_0]
0x40d217  mov     edi, edx
0x40d219  retn
```
