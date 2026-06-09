# _wcslen

- ea: `0x4163ef`
- end: `0x416517`
- name: `_wcslen`
- size: `296`
- prototype: `size_t __cdecl(const wchar_t *String)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x401257`
- `0x401c2a`
- `0x401cfa`
- `0x402e3c`
- `0x403041`
- `0x404994`
- `0x4057be`
- `0x405bfc`
- `0x405df0`
- `0x4065ea`
- `0x406b17`
- `0x4074f9`
- `0x40775a`
- `0x408194`
- `0x40885e`
- `0x409593`
- `0x40a943`

## callees

- `0x4163ef`

## pseudocode

```c
size_t __cdecl wcslen(const wchar_t *String)
{
  const wchar_t *v2; // eax
  const wchar_t *i; // ecx
  int v4; // ecx
  unsigned int v5; // esi
  const wchar_t *v6; // ecx
  const wchar_t *v7; // edi
  size_t v8; // ecx
  const wchar_t *v9; // ecx
  unsigned int v13; // esi
  const wchar_t *v14; // ecx
  const wchar_t *v15; // edi
  __m128i *j; // ecx

  if ( dword_43E00C >= 5 )
  {
    v2 = String;
    if ( ((unsigned __int8)String & 1) != 0 )
    {
      for ( i = String; *i; ++i )
        ;
LABEL_6:
      v4 = (char *)i - (char *)v2;
      return v4 >> 1;
    }
    v5 = ((32 - ((unsigned __int8)String & 0x1F)) & (unsigned int)-(((unsigned __int8)String & 0x1F) != 0)) >> 1;
    v6 = String;
    v7 = &String[v5];
    if ( String != v7 )
    {
      do
      {
        if ( !*v6 )
          break;
        ++v6;
      }
      while ( v6 != v7 );
    }
    v8 = v6 - String;
    if ( v8 == v5 )
    {
      v9 = &String[v8];
      __asm { vpxor   xmm1, xmm1, xmm1 }
      while ( 1 )
      {
        __asm
        {
          vpcmpeqw ymm0, ymm1, ymmword ptr [ecx]
          vpmovmskb eax, ymm0
        }
        if ( _EAX )
          break;
        v9 += 16;
      }
      while ( *v9 )
        ++v9;
      v8 = v9 - String;
      __asm { vzeroupper }
    }
    return v8;
  }
  if ( dword_43E00C < 1 )
  {
    for ( j = (__m128i *)String; j->m128i_i16[0]; j = (__m128i *)((char *)j + 2) )
      ;
    goto LABEL_34;
  }
  v2 = String;
  if ( ((unsigned __int8)String & 1) != 0 )
  {
    for ( i = String; *i; ++i )
      ;
    goto LABEL_6;
  }
  v13 = ((16 - ((unsigned __int8)String & 0xF)) & (unsigned int)-(((unsigned __int8)String & 0xF) != 0)) >> 1;
  v14 = String;
  v15 = &String[v13];
  if ( String != v15 )
  {
    do
    {
      if ( !*v14 )
        break;
      ++v14;
    }
    while ( v14 != v15 );
  }
  v8 = v14 - String;
  if ( v8 == v13 )
  {
    for ( j = (__m128i *)&String[v8]; !_mm_movemask_epi8(_mm_cmpeq_epi16(*j, (__m128i)0LL)); ++j )
      ;
    while ( j->m128i_i16[0] )
      j = (__m128i *)((char *)j + 2);
LABEL_34:
    v4 = (char *)j - (char *)String;
    return v4 >> 1;
  }
  return v8;
}

```

## disassembly

```asm
0x4163ef  mov     edi, edi
0x4163f1  push    ebp
0x4163f2  mov     ebp, esp
0x4163f4  mov     eax, dword_43E00C
0x4163f9  push    esi
0x4163fa  push    edi
0x4163fb  cmp     eax, 5
0x4163fe  jl      loc_416487
0x416404  mov     eax, [ebp+String]
0x416407  test    al, 1
0x416409  jz      short loc_416420
0x41640b  mov     ecx, eax
0x41640d  xor     edx, edx
0x41640f  cmp     [ecx], dx
0x416412  jz      short loc_416419
0x416414  add     ecx, 2
0x416417  jmp     short loc_41640F
0x416419  sub     ecx, eax
0x41641b  jmp     loc_41650F
0x416420  mov     esi, eax
0x416422  and     esi, 1Fh
0x416425  push    20h ; ' '
0x416427  pop     eax
0x416428  sub     eax, esi
0x41642a  neg     esi
0x41642c  sbb     esi, esi
0x41642e  xor     edx, edx
0x416430  and     esi, eax
0x416432  mov     eax, [ebp+String]
0x416435  shr     esi, 1
0x416437  mov     ecx, eax
0x416439  lea     edi, [eax+esi*2]
0x41643c  cmp     eax, edi
0x41643e  jz      short loc_41644C
0x416440  cmp     [ecx], dx
0x416443  jz      short loc_41644C
0x416445  add     ecx, 2
0x416448  cmp     ecx, edi
0x41644a  jnz     short loc_416440
0x41644c  sub     ecx, eax
0x41644e  sar     ecx, 1
0x416450  cmp     ecx, esi
0x416452  jnz     loc_416511
0x416458  lea     ecx, [eax+ecx*2]
0x41645b  vpxor   xmm1, xmm1, xmm1
0x41645f  vpcmpeqw ymm0, ymm1, ymmword ptr [ecx]
0x416463  vpmovmskb eax, ymm0
0x416467  test    eax, eax
0x416469  jnz     short loc_416470
0x41646b  add     ecx, 20h ; ' '
0x41646e  jmp     short loc_41645F
0x416470  cmp     [ecx], dx
0x416473  jz      short loc_41647A
0x416475  add     ecx, 2
0x416478  jmp     short loc_416470
0x41647a  sub     ecx, [ebp+String]
0x41647d  sar     ecx, 1
0x41647f  vzeroupper
0x416482  jmp     loc_416511
0x416487  cmp     eax, 1
0x41648a  jl      short loc_4164FD
0x41648c  mov     eax, [ebp+String]
0x41648f  test    al, 1
0x416491  jz      short loc_4164A5
0x416493  mov     ecx, eax
0x416495  xor     edx, edx
0x416497  cmp     [ecx], dx
0x41649a  jz      loc_416419
0x4164a0  add     ecx, 2
0x4164a3  jmp     short loc_416497
0x4164a5  mov     esi, eax
0x4164a7  and     esi, 0Fh
0x4164aa  push    10h
0x4164ac  pop     eax
0x4164ad  sub     eax, esi
0x4164af  neg     esi
0x4164b1  sbb     esi, esi
0x4164b3  xor     edx, edx
0x4164b5  and     esi, eax
0x4164b7  mov     eax, [ebp+String]
0x4164ba  shr     esi, 1
0x4164bc  mov     ecx, eax
0x4164be  lea     edi, [eax+esi*2]
0x4164c1  cmp     eax, edi
0x4164c3  jz      short loc_4164D1
0x4164c5  cmp     [ecx], dx
0x4164c8  jz      short loc_4164D1
0x4164ca  add     ecx, 2
0x4164cd  cmp     ecx, edi
0x4164cf  jnz     short loc_4164C5
0x4164d1  sub     ecx, eax
0x4164d3  sar     ecx, 1
0x4164d5  cmp     ecx, esi
0x4164d7  jnz     short loc_416511
0x4164d9  lea     ecx, [eax+ecx*2]
0x4164dc  xorps   xmm1, xmm1
0x4164df  movups  xmm0, xmmword ptr [ecx]
0x4164e2  pcmpeqw xmm0, xmm1
0x4164e6  pmovmskb eax, xmm0
0x4164ea  test    eax, eax
0x4164ec  jnz     short loc_4164F3
0x4164ee  add     ecx, 10h
0x4164f1  jmp     short loc_4164DF
0x4164f3  cmp     [ecx], dx
0x4164f6  jz      short loc_41650C
0x4164f8  add     ecx, 2
0x4164fb  jmp     short loc_4164F3
0x4164fd  mov     ecx, [ebp+String]
0x416500  xor     edx, edx
0x416502  cmp     [ecx], dx
0x416505  jz      short loc_41650C
0x416507  add     ecx, 2
0x41650a  jmp     short loc_416502
0x41650c  sub     ecx, [ebp+String]
0x41650f  sar     ecx, 1
0x416511  pop     edi
0x416512  mov     eax, ecx
0x416514  pop     esi
0x416515  pop     ebp
0x416516  retn
```
