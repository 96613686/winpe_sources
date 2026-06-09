# _wcslen

- ea: `0x410a41`
- end: `0x410b69`
- name: `_wcslen`
- size: `296`
- prototype: `size_t __cdecl(const wchar_t *String)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x401938`
- `0x40207e`
- `0x4029d6`
- `0x403675`
- `0x403d65`
- `0x403e90`
- `0x403fc4`
- `0x404d09`
- `0x4063fc`
- `0x406616`

## callees

- `0x410a41`

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

  if ( dword_426964 >= 5 )
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
  if ( dword_426964 < 1 )
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
0x410a41  mov     edi, edi
0x410a43  push    ebp
0x410a44  mov     ebp, esp
0x410a46  mov     eax, dword_426964
0x410a4b  push    esi
0x410a4c  push    edi
0x410a4d  cmp     eax, 5
0x410a50  jl      loc_410AD9
0x410a56  mov     eax, [ebp+String]
0x410a59  test    al, 1
0x410a5b  jz      short loc_410A72
0x410a5d  mov     ecx, eax
0x410a5f  xor     edx, edx
0x410a61  cmp     [ecx], dx
0x410a64  jz      short loc_410A6B
0x410a66  add     ecx, 2
0x410a69  jmp     short loc_410A61
0x410a6b  sub     ecx, eax
0x410a6d  jmp     loc_410B61
0x410a72  mov     esi, eax
0x410a74  and     esi, 1Fh
0x410a77  push    20h ; ' '
0x410a79  pop     eax
0x410a7a  sub     eax, esi
0x410a7c  neg     esi
0x410a7e  sbb     esi, esi
0x410a80  xor     edx, edx
0x410a82  and     esi, eax
0x410a84  mov     eax, [ebp+String]
0x410a87  shr     esi, 1
0x410a89  mov     ecx, eax
0x410a8b  lea     edi, [eax+esi*2]
0x410a8e  cmp     eax, edi
0x410a90  jz      short loc_410A9E
0x410a92  cmp     [ecx], dx
0x410a95  jz      short loc_410A9E
0x410a97  add     ecx, 2
0x410a9a  cmp     ecx, edi
0x410a9c  jnz     short loc_410A92
0x410a9e  sub     ecx, eax
0x410aa0  sar     ecx, 1
0x410aa2  cmp     ecx, esi
0x410aa4  jnz     loc_410B63
0x410aaa  lea     ecx, [eax+ecx*2]
0x410aad  vpxor   xmm1, xmm1, xmm1
0x410ab1  vpcmpeqw ymm0, ymm1, ymmword ptr [ecx]
0x410ab5  vpmovmskb eax, ymm0
0x410ab9  test    eax, eax
0x410abb  jnz     short loc_410AC2
0x410abd  add     ecx, 20h ; ' '
0x410ac0  jmp     short loc_410AB1
0x410ac2  cmp     [ecx], dx
0x410ac5  jz      short loc_410ACC
0x410ac7  add     ecx, 2
0x410aca  jmp     short loc_410AC2
0x410acc  sub     ecx, [ebp+String]
0x410acf  sar     ecx, 1
0x410ad1  vzeroupper
0x410ad4  jmp     loc_410B63
0x410ad9  cmp     eax, 1
0x410adc  jl      short loc_410B4F
0x410ade  mov     eax, [ebp+String]
0x410ae1  test    al, 1
0x410ae3  jz      short loc_410AF7
0x410ae5  mov     ecx, eax
0x410ae7  xor     edx, edx
0x410ae9  cmp     [ecx], dx
0x410aec  jz      loc_410A6B
0x410af2  add     ecx, 2
0x410af5  jmp     short loc_410AE9
0x410af7  mov     esi, eax
0x410af9  and     esi, 0Fh
0x410afc  push    10h
0x410afe  pop     eax
0x410aff  sub     eax, esi
0x410b01  neg     esi
0x410b03  sbb     esi, esi
0x410b05  xor     edx, edx
0x410b07  and     esi, eax
0x410b09  mov     eax, [ebp+String]
0x410b0c  shr     esi, 1
0x410b0e  mov     ecx, eax
0x410b10  lea     edi, [eax+esi*2]
0x410b13  cmp     eax, edi
0x410b15  jz      short loc_410B23
0x410b17  cmp     [ecx], dx
0x410b1a  jz      short loc_410B23
0x410b1c  add     ecx, 2
0x410b1f  cmp     ecx, edi
0x410b21  jnz     short loc_410B17
0x410b23  sub     ecx, eax
0x410b25  sar     ecx, 1
0x410b27  cmp     ecx, esi
0x410b29  jnz     short loc_410B63
0x410b2b  lea     ecx, [eax+ecx*2]
0x410b2e  xorps   xmm1, xmm1
0x410b31  movups  xmm0, xmmword ptr [ecx]
0x410b34  pcmpeqw xmm0, xmm1
0x410b38  pmovmskb eax, xmm0
0x410b3c  test    eax, eax
0x410b3e  jnz     short loc_410B45
0x410b40  add     ecx, 10h
0x410b43  jmp     short loc_410B31
0x410b45  cmp     [ecx], dx
0x410b48  jz      short loc_410B5E
0x410b4a  add     ecx, 2
0x410b4d  jmp     short loc_410B45
0x410b4f  mov     ecx, [ebp+String]
0x410b52  xor     edx, edx
0x410b54  cmp     [ecx], dx
0x410b57  jz      short loc_410B5E
0x410b59  add     ecx, 2
0x410b5c  jmp     short loc_410B54
0x410b5e  sub     ecx, [ebp+String]
0x410b61  sar     ecx, 1
0x410b63  pop     edi
0x410b64  mov     eax, ecx
0x410b66  pop     esi
0x410b67  pop     ebp
0x410b68  retn
```
