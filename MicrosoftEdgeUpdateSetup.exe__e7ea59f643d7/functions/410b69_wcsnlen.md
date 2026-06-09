# _wcsnlen

- ea: `0x410b69`
- end: `0x410d19`
- name: `_wcsnlen`
- size: `432`
- prototype: `size_t __cdecl(const wchar_t *Source, size_t MaxCount)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x403355`
- `0x4036c1`
- `0x403a79`
- `0x404d09`
- `0x40d893`

## callees

- `0x410b69`

## pseudocode

```c
size_t __cdecl wcsnlen(const wchar_t *Source, size_t MaxCount)
{
  const wchar_t *v3; // ecx
  const wchar_t *v4; // esi
  const wchar_t *v5; // edx
  int v6; // ecx
  size_t v7; // edx
  const wchar_t *v8; // edi
  size_t v9; // ecx
  const wchar_t *v10; // edi
  const wchar_t *v12; // ecx
  const wchar_t *j; // ecx
  const wchar_t *v16; // edx
  size_t v17; // edx
  const wchar_t *v18; // edi
  __m128i *v19; // edi
  const wchar_t *v20; // ecx
  const wchar_t *i; // ecx
  const wchar_t *v22; // ecx
  const wchar_t *v23; // esi

  if ( dword_426964 < 5 )
  {
    if ( dword_426964 < 1 )
    {
      v22 = Source;
      v23 = &Source[MaxCount];
      if ( Source != v23 )
      {
        do
        {
          if ( !*v22 )
            break;
          ++v22;
        }
        while ( v22 != v23 );
      }
      v6 = (char *)v22 - (char *)Source;
      return v6 >> 1;
    }
    v3 = Source;
    if ( ((unsigned __int8)Source & 1) != 0 )
    {
      v4 = Source;
      v16 = &Source[MaxCount];
      if ( Source != v16 )
      {
        do
        {
          if ( !*v3 )
            break;
          ++v3;
        }
        while ( v3 != v16 );
      }
      goto LABEL_6;
    }
    v17 = ((16 - ((unsigned __int8)Source & 0xF)) & (unsigned int)-(((unsigned __int8)Source & 0xF) != 0)) >> 1;
    if ( MaxCount < v17 )
      v17 = MaxCount;
    v4 = Source;
    v18 = &Source[v17];
    if ( Source != v18 )
    {
      do
      {
        if ( !*v3 )
          break;
        ++v3;
      }
      while ( v3 != v18 );
    }
    v9 = v3 - Source;
    if ( v9 == v17 )
    {
      v19 = (__m128i *)&Source[v9];
      v20 = &Source[v9 + ((MaxCount - v17) & 0xFFFFFFF0)];
      while ( v19 != (__m128i *)v20 && !_mm_movemask_epi8(_mm_cmpeq_epi16(*v19, (__m128i)0LL)) )
        ++v19;
      for ( i = &Source[MaxCount]; v19 != (__m128i *)i; v19 = (__m128i *)((char *)v19 + 2) )
      {
        if ( !v19->m128i_i16[0] )
          break;
      }
      v3 = (const wchar_t *)v19;
      goto LABEL_6;
    }
  }
  else
  {
    v3 = Source;
    if ( ((unsigned __int8)Source & 1) != 0 )
    {
      v4 = Source;
      v5 = &Source[MaxCount];
      if ( Source != v5 )
      {
        do
        {
          if ( !*v3 )
            break;
          ++v3;
        }
        while ( v3 != v5 );
      }
LABEL_6:
      v6 = (char *)v3 - (char *)v4;
      return v6 >> 1;
    }
    v7 = ((32 - ((unsigned __int8)Source & 0x1F)) & (unsigned int)-(((unsigned __int8)Source & 0x1F) != 0)) >> 1;
    if ( MaxCount < v7 )
      v7 = MaxCount;
    v8 = &Source[v7];
    if ( Source != v8 )
    {
      do
      {
        if ( !*v3 )
          break;
        ++v3;
      }
      while ( v3 != v8 );
    }
    v9 = v3 - Source;
    if ( v9 == v7 )
    {
      v10 = &Source[v9];
      __asm { vpxor   xmm1, xmm1, xmm1 }
      v12 = &Source[v9 + ((MaxCount - v7) & 0xFFFFFFE0)];
      while ( v10 != v12 )
      {
        __asm
        {
          vpcmpeqw ymm0, ymm1, ymmword ptr [edi]
          vpmovmskb eax, ymm0
        }
        if ( _EAX )
          break;
        v10 += 16;
      }
      for ( j = &Source[MaxCount]; v10 != j; ++v10 )
      {
        if ( !*v10 )
          break;
      }
      v9 = v10 - Source;
      __asm { vzeroupper }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x410b69  mov     edi, edi
0x410b6b  push    ebp
0x410b6c  mov     ebp, esp
0x410b6e  mov     eax, dword_426964
0x410b73  push    esi
0x410b74  push    edi
0x410b75  cmp     eax, 5
0x410b78  jl      loc_410C35
0x410b7e  mov     ecx, [ebp+Source]
0x410b81  test    cl, 1
0x410b84  jz      short loc_410BA7
0x410b86  mov     eax, [ebp+MaxCount]
0x410b89  mov     esi, ecx
0x410b8b  lea     edx, [ecx+eax*2]
0x410b8e  cmp     esi, edx
0x410b90  jz      short loc_410BA0
0x410b92  xor     eax, eax
0x410b94  cmp     [ecx], ax
0x410b97  jz      short loc_410BA0
0x410b99  add     ecx, 2
0x410b9c  cmp     ecx, edx
0x410b9e  jnz     short loc_410B94
0x410ba0  sub     ecx, esi
0x410ba2  jmp     loc_410D11
0x410ba7  mov     edx, ecx
0x410ba9  and     edx, 1Fh
0x410bac  push    20h ; ' '
0x410bae  pop     eax
0x410baf  sub     eax, edx
0x410bb1  neg     edx
0x410bb3  sbb     edx, edx
0x410bb5  and     edx, eax
0x410bb7  mov     eax, [ebp+MaxCount]
0x410bba  shr     edx, 1
0x410bbc  cmp     eax, edx
0x410bbe  jnb     short loc_410BC2
0x410bc0  mov     edx, eax
0x410bc2  mov     esi, [ebp+Source]
0x410bc5  lea     edi, [ecx+edx*2]
0x410bc8  xor     eax, eax
0x410bca  cmp     esi, edi
0x410bcc  jz      short loc_410BDA
0x410bce  cmp     [ecx], ax
0x410bd1  jz      short loc_410BDA
0x410bd3  add     ecx, 2
0x410bd6  cmp     ecx, edi
0x410bd8  jnz     short loc_410BCE
0x410bda  sub     ecx, esi
0x410bdc  sar     ecx, 1
0x410bde  cmp     ecx, edx
0x410be0  jnz     loc_410D13
0x410be6  mov     eax, [ebp+MaxCount]
0x410be9  lea     edi, [esi+ecx*2]
0x410bec  sub     eax, edx
0x410bee  and     eax, 0FFFFFFE0h
0x410bf1  add     eax, ecx
0x410bf3  vpxor   xmm1, xmm1, xmm1
0x410bf7  lea     ecx, [esi+eax*2]
0x410bfa  jmp     short loc_410C0B
0x410bfc  vpcmpeqw ymm0, ymm1, ymmword ptr [edi]
0x410c00  vpmovmskb eax, ymm0
0x410c04  test    eax, eax
0x410c06  jnz     short loc_410C0F
0x410c08  add     edi, 20h ; ' '
0x410c0b  cmp     edi, ecx
0x410c0d  jnz     short loc_410BFC
0x410c0f  mov     eax, [ebp+MaxCount]
0x410c12  lea     ecx, [esi+eax*2]
0x410c15  cmp     edi, ecx
0x410c17  jz      short loc_410C27
0x410c19  xor     eax, eax
0x410c1b  cmp     [edi], ax
0x410c1e  jz      short loc_410C27
0x410c20  add     edi, 2
0x410c23  cmp     edi, ecx
0x410c25  jnz     short loc_410C1B
0x410c27  mov     ecx, edi
0x410c29  sub     ecx, esi
0x410c2b  sar     ecx, 1
0x410c2d  vzeroupper
0x410c30  jmp     loc_410D13
0x410c35  cmp     eax, 1
0x410c38  jl      loc_410CF2
0x410c3e  mov     ecx, [ebp+Source]
0x410c41  test    cl, 1
0x410c44  jz      short loc_410C6D
0x410c46  mov     eax, [ebp+MaxCount]
0x410c49  mov     esi, ecx
0x410c4b  lea     edx, [ecx+eax*2]
0x410c4e  cmp     esi, edx
0x410c50  jz      loc_410BA0
0x410c56  xor     eax, eax
0x410c58  cmp     [ecx], ax
0x410c5b  jz      loc_410BA0
0x410c61  add     ecx, 2
0x410c64  cmp     ecx, edx
0x410c66  jnz     short loc_410C58
0x410c68  jmp     loc_410BA0
0x410c6d  mov     edx, ecx
0x410c6f  and     edx, 0Fh
0x410c72  push    10h
0x410c74  pop     eax
0x410c75  sub     eax, edx
0x410c77  neg     edx
0x410c79  sbb     edx, edx
0x410c7b  and     edx, eax
0x410c7d  mov     eax, [ebp+MaxCount]
0x410c80  shr     edx, 1
0x410c82  cmp     eax, edx
0x410c84  jnb     short loc_410C88
0x410c86  mov     edx, eax
0x410c88  mov     esi, [ebp+Source]
0x410c8b  lea     edi, [ecx+edx*2]
0x410c8e  xor     eax, eax
0x410c90  cmp     esi, edi
0x410c92  jz      short loc_410CA0
0x410c94  cmp     [ecx], ax
0x410c97  jz      short loc_410CA0
0x410c99  add     ecx, 2
0x410c9c  cmp     ecx, edi
0x410c9e  jnz     short loc_410C94
0x410ca0  sub     ecx, esi
0x410ca2  sar     ecx, 1
0x410ca4  cmp     ecx, edx
0x410ca6  jnz     short loc_410D13
0x410ca8  mov     eax, [ebp+MaxCount]
0x410cab  lea     edi, [esi+ecx*2]
0x410cae  sub     eax, edx
0x410cb0  xorps   xmm1, xmm1
0x410cb3  and     eax, 0FFFFFFF0h
0x410cb6  add     eax, ecx
0x410cb8  lea     ecx, [esi+eax*2]
0x410cbb  jmp     short loc_410CCF
0x410cbd  movups  xmm0, xmmword ptr [edi]
0x410cc0  pcmpeqw xmm0, xmm1
0x410cc4  pmovmskb eax, xmm0
0x410cc8  test    eax, eax
0x410cca  jnz     short loc_410CD3
0x410ccc  add     edi, 10h
0x410ccf  cmp     edi, ecx
0x410cd1  jnz     short loc_410CBD
0x410cd3  mov     eax, [ebp+MaxCount]
0x410cd6  lea     ecx, [esi+eax*2]
0x410cd9  cmp     edi, ecx
0x410cdb  jz      short loc_410CEB
0x410cdd  xor     eax, eax
0x410cdf  cmp     [edi], ax
0x410ce2  jz      short loc_410CEB
0x410ce4  add     edi, 2
0x410ce7  cmp     edi, ecx
0x410ce9  jnz     short loc_410CDF
0x410ceb  mov     ecx, edi
0x410ced  jmp     loc_410BA0
0x410cf2  mov     edx, [ebp+Source]
0x410cf5  mov     ecx, edx
0x410cf7  mov     eax, [ebp+MaxCount]
0x410cfa  lea     esi, [edx+eax*2]
0x410cfd  cmp     edx, esi
0x410cff  jz      short loc_410D0F
0x410d01  xor     eax, eax
0x410d03  cmp     [ecx], ax
0x410d06  jz      short loc_410D0F
0x410d08  add     ecx, 2
0x410d0b  cmp     ecx, esi
0x410d0d  jnz     short loc_410D03
0x410d0f  sub     ecx, edx
0x410d11  sar     ecx, 1
0x410d13  pop     edi
0x410d14  mov     eax, ecx
0x410d16  pop     esi
0x410d17  pop     ebp
0x410d18  retn
```
