# wcslen

- ea: `0x140003d3c`
- end: `0x140003e65`
- name: `wcslen`
- size: `297`
- prototype: `size_t __cdecl(const wchar_t *Str)`
- caller_count: `41`
- callee_count: `1`
- tags: ``

## callers

- `0x140001460`
- `0x1400016e4`
- `0x140001944`
- `0x140001b1c`
- `0x140002288`
- `0x140002590`
- `0x140002750`
- `0x140002960`
- `0x140002b70`
- `0x140003100`
- `0x1400033a8`
- `0x140003688`
- `0x140025394`
- `0x140025d90`
- `0x140027170`
- `0x1400271f4`
- `0x140027664`
- `0x1400279c8`
- `0x140028ac0`
- `0x140028b88`
- `0x140028c94`
- `0x14002cc40`
- `0x14002ef48`
- `0x14002efe8`
- `0x14002f134`
- `0x14002f1d4`
- `0x14002fc8c`
- `0x140031488`
- `0x140032c2c`
- `0x1400338f4`
- `0x140033a9c`
- `0x140034270`
- `0x1400344c0`
- `0x140034574`
- `0x140034a74`
- `0x140038de0`
- `0x14003988c`
- `0x14003aadc`
- `0x14003ac04`
- `0x14003acc8`
- `0x14003ae54`

## callees

- `0x140003d3c`

## pseudocode

```c
size_t __cdecl wcslen(const wchar_t *Str)
{
  __m128i *i; // rdx
  unsigned __int64 v4; // r9
  const wchar_t *v5; // rax
  size_t v6; // rdx
  unsigned __int64 v10; // r9
  const wchar_t *v11; // rax

  i = (__m128i *)Str;
  if ( dword_1400D68F0 < 5 )
  {
    if ( dword_1400D68F0 < 1 )
    {
      while ( i->m128i_i16[0] )
        i = (__m128i *)((char *)i + 2);
      return ((char *)i - (char *)Str) >> 1;
    }
    if ( ((unsigned __int8)Str & 1) != 0 )
    {
      while ( i->m128i_i16[0] )
        i = (__m128i *)((char *)i + 2);
      return ((char *)i - (char *)Str) >> 1;
    }
    v10 = ((16LL - ((unsigned __int8)Str & 0xF)) & (unsigned __int64)-(__int64)(((unsigned __int8)Str & 0xF) != 0)) >> 1;
    v11 = &Str[v10];
    if ( Str != v11 )
    {
      do
      {
        if ( !i->m128i_i16[0] )
          break;
        i = (__m128i *)((char *)i + 2);
      }
      while ( i != (__m128i *)v11 );
    }
    v6 = ((char *)i - (char *)Str) >> 1;
    if ( v6 == v10 )
    {
      for ( i = (__m128i *)&Str[v6]; !_mm_movemask_epi8(_mm_cmpeq_epi16((__m128i)0LL, *i)); ++i )
        ;
      while ( i->m128i_i16[0] )
        i = (__m128i *)((char *)i + 2);
      return ((char *)i - (char *)Str) >> 1;
    }
  }
  else
  {
    if ( ((unsigned __int8)Str & 1) != 0 )
    {
      while ( i->m128i_i16[0] )
        i = (__m128i *)((char *)i + 2);
      return ((char *)i - (char *)Str) >> 1;
    }
    v4 = ((32LL - ((unsigned __int8)Str & 0x1F)) & (unsigned __int64)-(__int64)(((unsigned __int8)Str & 0x1F) != 0)) >> 1;
    v5 = &Str[v4];
    if ( Str != v5 )
    {
      do
      {
        if ( !i->m128i_i16[0] )
          break;
        i = (__m128i *)((char *)i + 2);
      }
      while ( i != (__m128i *)v5 );
    }
    v6 = ((char *)i - (char *)Str) >> 1;
    if ( v6 == v4 )
    {
      i = (__m128i *)&Str[v6];
      __asm { vpxor   xmm2, xmm2, xmm2 }
      while ( 1 )
      {
        __asm
        {
          vpcmpeqw ymm1, ymm2, ymmword ptr [rdx]
          vpmovmskb eax, ymm1
        }
        if ( _EAX )
          break;
        i += 2;
      }
      __asm { vzeroupper }
      while ( i->m128i_i16[0] )
        i = (__m128i *)((char *)i + 2);
      return ((char *)i - (char *)Str) >> 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140003d3c  mov     eax, cs:dword_1400D68F0
0x140003d42  mov     r8, rcx
0x140003d45  mov     rdx, rcx
0x140003d48  cmp     eax, 5
0x140003d4b  jl      loc_140003DD3
0x140003d51  test    r8b, 1
0x140003d55  jz      short loc_140003D68
0x140003d57  xor     ecx, ecx
0x140003d59  cmp     [rdx], cx
0x140003d5c  jz      loc_140003E5B
0x140003d62  add     rdx, 2
0x140003d66  jmp     short loc_140003D59
0x140003d68  and     ecx, 1Fh
0x140003d6b  mov     eax, 20h ; ' '
0x140003d70  sub     rax, rcx
0x140003d73  neg     rcx
0x140003d76  sbb     r9, r9
0x140003d79  xor     ecx, ecx
0x140003d7b  and     r9, rax
0x140003d7e  shr     r9, 1
0x140003d81  lea     rax, [r8+r9*2]
0x140003d85  cmp     r8, rax
0x140003d88  jz      short loc_140003D98
0x140003d8a  cmp     [rdx], cx
0x140003d8d  jz      short loc_140003D98
0x140003d8f  add     rdx, 2
0x140003d93  cmp     rdx, rax
0x140003d96  jnz     short loc_140003D8A
0x140003d98  sub     rdx, r8
0x140003d9b  sar     rdx, 1
0x140003d9e  cmp     rdx, r9
0x140003da1  jnz     loc_140003E61
0x140003da7  lea     rdx, [r8+rdx*2]
0x140003dab  vpxor   xmm2, xmm2, xmm2
0x140003daf  vpcmpeqw ymm1, ymm2, ymmword ptr [rdx]
0x140003db3  vpmovmskb eax, ymm1
0x140003db7  test    eax, eax
0x140003db9  jnz     short loc_140003DC1
0x140003dbb  add     rdx, 20h ; ' '
0x140003dbf  jmp     short loc_140003DAF
0x140003dc1  vzeroupper
0x140003dc4  cmp     [rdx], cx
0x140003dc7  jz      loc_140003E5B
0x140003dcd  add     rdx, 2
0x140003dd1  jmp     short loc_140003DC4
0x140003dd3  cmp     eax, 1
0x140003dd6  jl      short loc_140003E4E
0x140003dd8  test    r8b, 1
0x140003ddc  jz      short loc_140003DEB
0x140003dde  xor     ecx, ecx
0x140003de0  cmp     [rdx], cx
0x140003de3  jz      short loc_140003E5B
0x140003de5  add     rdx, 2
0x140003de9  jmp     short loc_140003DE0
0x140003deb  and     ecx, 0Fh
0x140003dee  mov     eax, 10h
0x140003df3  sub     rax, rcx
0x140003df6  neg     rcx
0x140003df9  sbb     r9, r9
0x140003dfc  xor     ecx, ecx
0x140003dfe  and     r9, rax
0x140003e01  shr     r9, 1
0x140003e04  lea     rax, [r8+r9*2]
0x140003e08  cmp     r8, rax
0x140003e0b  jz      short loc_140003E1B
0x140003e0d  cmp     [rdx], cx
0x140003e10  jz      short loc_140003E1B
0x140003e12  add     rdx, 2
0x140003e16  cmp     rdx, rax
0x140003e19  jnz     short loc_140003E0D
0x140003e1b  sub     rdx, r8
0x140003e1e  sar     rdx, 1
0x140003e21  cmp     rdx, r9
0x140003e24  jnz     short loc_140003E61
0x140003e26  lea     rdx, [r8+rdx*2]
0x140003e2a  xorps   xmm1, xmm1
0x140003e2d  movdqa  xmm0, xmm1
0x140003e31  pcmpeqw xmm0, xmmword ptr [rdx]
0x140003e35  pmovmskb eax, xmm0
0x140003e39  test    eax, eax
0x140003e3b  jnz     short loc_140003E43
0x140003e3d  add     rdx, 10h
0x140003e41  jmp     short loc_140003E2D
0x140003e43  cmp     [rdx], cx
0x140003e46  jz      short loc_140003E5B
0x140003e48  add     rdx, 2
0x140003e4c  jmp     short loc_140003E43
0x140003e4e  xor     ecx, ecx
0x140003e50  cmp     [rdx], cx
0x140003e53  jz      short loc_140003E5B
0x140003e55  add     rdx, 2
0x140003e59  jmp     short loc_140003E50
0x140003e5b  sub     rdx, r8
0x140003e5e  sar     rdx, 1
0x140003e61  mov     rax, rdx
0x140003e64  retn
```
