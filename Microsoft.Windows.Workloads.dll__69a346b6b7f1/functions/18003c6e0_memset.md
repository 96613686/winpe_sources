# memset

- ea: `0x18003c6e0`
- end: `0x18003ca6c`
- name: `memset`
- size: `908`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f70`
- `0x180004590`
- `0x180007a20`
- `0x180008700`
- `0x180009a40`
- `0x18000d1f0`
- `0x18000fdc0`
- `0x180013820`
- `0x1800139b0`
- `0x1800157c0`
- `0x180016760`
- `0x18001bbb0`
- `0x18001d320`
- `0x18001e1f0`
- `0x1800277c0`
- `0x180027b20`
- `0x180029280`
- `0x18002b2e0`
- `0x18002b3b0`
- `0x18002b520`
- `0x18002d360`
- `0x18002e220`
- `0x18002ee80`
- `0x18002f2d0`
- `0x18002fee0`
- `0x180033cb8`
- `0x180033e7c`
- `0x180035e88`
- `0x18003a020`
- `0x1800407b1`

## callees

- `0x18003c6d0`
- `0x18003c6e0`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v5; // r11
  char *v6; // rcx
  __m128i v7; // xmm0
  __int64 v9; // r9
  __int64 v14; // r9
  __m128i *v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r9

  result = a1;
  v5 = 0x101010101010101LL * (unsigned __int8)Val;
  if ( Size <= 0xF )
  {
    v6 = (char *)a1 + Size;
    switch ( Size )
    {
      case 0uLL:
        return result;
      case 1uLL:
        goto LABEL_6;
      case 2uLL:
        goto LABEL_9;
      case 3uLL:
        goto LABEL_5;
      case 4uLL:
        goto LABEL_13;
      case 5uLL:
        goto LABEL_11;
      case 6uLL:
        goto LABEL_8;
      case 7uLL:
        goto LABEL_4;
      case 8uLL:
        *((_QWORD *)v6 - 1) = v5;
        return result;
      case 9uLL:
        *(_QWORD *)(v6 - 9) = v5;
        *(v6 - 1) = Val;
        return result;
      case 0xAuLL:
        *(_QWORD *)(v6 - 10) = v5;
        *((_WORD *)v6 - 1) = v5;
        return result;
      case 0xBuLL:
        *(_QWORD *)(v6 - 11) = v5;
        *(_WORD *)(v6 - 3) = v5;
        *(v6 - 1) = Val;
        return result;
      case 0xCuLL:
        *(_QWORD *)(v6 - 12) = v5;
LABEL_13:
        *((_DWORD *)v6 - 1) = v5;
        break;
      case 0xDuLL:
        *(_QWORD *)(v6 - 13) = v5;
LABEL_11:
        *(_DWORD *)(v6 - 5) = v5;
        *(v6 - 1) = Val;
        break;
      case 0xEuLL:
        *(_QWORD *)(v6 - 14) = v5;
LABEL_8:
        *(_DWORD *)(v6 - 6) = v5;
LABEL_9:
        *((_WORD *)v6 - 1) = v5;
        break;
      case 0xFuLL:
        *(_QWORD *)(v6 - 15) = v5;
LABEL_4:
        *(_DWORD *)(v6 - 7) = v5;
LABEL_5:
        *(_WORD *)(v6 - 3) = v5;
LABEL_6:
        *(v6 - 1) = Val;
        break;
    }
    return result;
  }
  v7 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v5, (__m128i)(unsigned __int64)v5);
  if ( Size <= 0x20 )
  {
    *(__m128i *)a1 = v7;
    *(__m128i *)((char *)a1 + Size - 16) = v7;
    return result;
  }
  if ( (unsigned int)_isa_available < 3 )
  {
    if ( Size <= _memset_fast_string_threshold || (_favor & 2) == 0 )
    {
      v14 = ((unsigned __int8)a1 & 0xF) - 16LL;
      v15 = (__m128i *)((char *)a1 - v14);
      v16 = v14 + Size;
      if ( v16 > 0x80 )
      {
        do
        {
          *v15 = v7;
          v15[1] = v7;
          v15[2] = v7;
          v15[3] = v7;
          v15[4] = v7;
          v15[5] = v7;
          v15[6] = v7;
          v15[7] = v7;
          v15 += 8;
          v16 -= 128LL;
        }
        while ( v16 >= 0x80 );
      }
      v17 = (v16 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
      switch ( (unsigned __int8)v17 >> 4 )
      {
        case 0:
        case 9:
        case 10:
        case 11:
        case 12:
        case 13:
        case 14:
        case 15:
          goto LABEL_61;
        case 1:
          goto LABEL_60;
        case 2:
          goto LABEL_59;
        case 3:
          goto LABEL_58;
        case 4:
          goto LABEL_57;
        case 5:
          goto LABEL_56;
        case 6:
          goto LABEL_55;
        case 7:
          goto LABEL_54;
        case 8:
          *(__m128i *)((char *)&v15[-8] + v17) = v7;
LABEL_54:
          *(__m128i *)((char *)&v15[-7] + v17) = v7;
LABEL_55:
          *(__m128i *)((char *)&v15[-6] + v17) = v7;
LABEL_56:
          *(__m128i *)((char *)&v15[-5] + v17) = v7;
LABEL_57:
          *(__m128i *)((char *)&v15[-4] + v17) = v7;
LABEL_58:
          *(__m128i *)((char *)&v15[-3] + v17) = v7;
LABEL_59:
          *(__m128i *)((char *)&v15[-2] + v17) = v7;
LABEL_60:
          *(__m128i *)((char *)&v15[-1] + v16) = v7;
LABEL_61:
          *(__m128i *)result = v7;
          break;
      }
      return result;
    }
    return (void *)memset_repstos(a1, (unsigned __int8)Val, Size, a1);
  }
  if ( Size > _memset_fast_string_threshold && Size <= _memset_nt_threshold && (_favor & 2) != 0 )
    return (void *)memset_repstos(a1, (unsigned __int8)Val, Size, a1);
  __asm { vinsertf128 ymm0, ymm0, xmm0, 1 }
  v9 = ((unsigned __int8)a1 & 0x1F) - 32LL;
  _RCX = (char *)a1 - v9;
  _R8 = v9 + Size;
  if ( _R8 <= 0x100 )
    goto LABEL_27;
  if ( _R8 <= _memset_nt_threshold )
  {
    do
    {
      __asm
      {
        vmovdqa ymmword ptr [rcx], ymm0
        vmovdqa ymmword ptr [rcx+20h], ymm0
        vmovdqa ymmword ptr [rcx+40h], ymm0
        vmovdqa ymmword ptr [rcx+60h], ymm0
        vmovdqa ymmword ptr [rcx+80h], ymm0
        vmovdqa ymmword ptr [rcx+0A0h], ymm0
        vmovdqa ymmword ptr [rcx+0C0h], ymm0
        vmovdqa ymmword ptr [rcx+0E0h], ymm0
      }
      _RCX += 256;
      _R8 -= 256LL;
    }
    while ( _R8 >= 0x100 );
LABEL_27:
    _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
    switch ( (_R9 >> 5) & 0xF )
    {
      case 0uLL:
      case 9uLL:
      case 0xAuLL:
      case 0xBuLL:
      case 0xCuLL:
      case 0xDuLL:
      case 0xEuLL:
      case 0xFuLL:
        goto LABEL_36;
      case 1uLL:
        goto LABEL_35;
      case 2uLL:
        goto LABEL_34;
      case 3uLL:
        goto LABEL_33;
      case 4uLL:
        goto LABEL_32;
      case 5uLL:
        goto LABEL_31;
      case 6uLL:
        goto LABEL_30;
      case 7uLL:
        goto LABEL_29;
      case 8uLL:
        __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018003C878 case 8 }
LABEL_29:
        __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018003C878 case 7 }
LABEL_30:
        __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018003C878 case 6 }
LABEL_31:
        __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018003C878 case 5 }
LABEL_32:
        __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018003C878 case 4 }
LABEL_33:
        __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018003C878 case 3 }
LABEL_34:
        __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018003C878 case 2 }
LABEL_35:
        __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018003C878 case 1 }
LABEL_36:
        __asm
        {
          vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018003C878 cases 0,9-15
          vzeroupper
        }
        break;
    }
    return result;
  }
  do
  {
    __asm
    {
      vmovntdq ymmword ptr [rcx], ymm0
      vmovntdq ymmword ptr [rcx+20h], ymm0
      vmovntdq ymmword ptr [rcx+40h], ymm0
      vmovntdq ymmword ptr [rcx+60h], ymm0
      vmovntdq ymmword ptr [rcx+80h], ymm0
      vmovntdq ymmword ptr [rcx+0A0h], ymm0
      vmovntdq ymmword ptr [rcx+0C0h], ymm0
      vmovntdq ymmword ptr [rcx+0E0h], ymm0
    }
    _RCX += 256;
    _R8 -= 256LL;
  }
  while ( _R8 >= 0x100 );
  _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
  switch ( (_R9 >> 5) & 0xF )
  {
    case 0uLL:
    case 9uLL:
    case 0xAuLL:
    case 0xBuLL:
    case 0xCuLL:
    case 0xDuLL:
    case 0xEuLL:
    case 0xFuLL:
      goto LABEL_47;
    case 1uLL:
      goto LABEL_46;
    case 2uLL:
      goto LABEL_45;
    case 3uLL:
      goto LABEL_44;
    case 4uLL:
      goto LABEL_43;
    case 5uLL:
      goto LABEL_42;
    case 6uLL:
      goto LABEL_41;
    case 7uLL:
      goto LABEL_40;
    case 8uLL:
      __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018003C938 case 8 }
LABEL_40:
      __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018003C938 case 7 }
LABEL_41:
      __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018003C938 case 6 }
LABEL_42:
      __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018003C938 case 5 }
LABEL_43:
      __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018003C938 case 4 }
LABEL_44:
      __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018003C938 case 3 }
LABEL_45:
      __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018003C938 case 2 }
LABEL_46:
      __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018003C938 case 1 }
LABEL_47:
      __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018003C938 cases 0,9-15 }
      _mm_sfence();
      __asm { vzeroupper }
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18003c6e0  mov     rax, rcx
0x18003c6e3  mov     r9, rcx
0x18003c6e6  lea     r10, cs:180000000h
0x18003c6ed  movzx   edx, dl
0x18003c6f0  mov     r11, 101010101010101h
0x18003c6fa  imul    r11, rdx
0x18003c6fe  movq    xmm0, r11
0x18003c703  cmp     r8, 0Fh
0x18003c707  ja      loc_18003C790
0x18003c70d  nop     dword ptr [rax]
0x18003c710  and     r8, 0Fh; switch 16 cases
0x18003c714  add     rcx, r8
0x18003c717  mov     r9d, ds:(jpt_18003C722 - 180000000h)[r10+r8*4]
0x18003c71f  add     r9, r10
0x18003c722  jmp     r9; switch jump
0x18003c725  mov     [rcx-0Fh], r11; jumptable 000000018003C722 case 15
0x18003c729  mov     [rcx-7], r11d; jumptable 000000018003C722 case 7
0x18003c72d  mov     [rcx-3], r11w; jumptable 000000018003C722 case 3
0x18003c732  mov     [rcx-1], r11b; jumptable 000000018003C722 case 1
0x18003c736  retn; jumptable 000000018003C722 case 0
0x18003c737  mov     [rcx-0Eh], r11; jumptable 000000018003C722 case 14
0x18003c73b  mov     [rcx-6], r11d; jumptable 000000018003C722 case 6
0x18003c73f  mov     [rcx-2], r11w; jumptable 000000018003C722 case 2
0x18003c744  retn
0x18003c750  mov     [rcx-0Dh], r11; jumptable 000000018003C722 case 13
0x18003c754  mov     [rcx-5], r11d; jumptable 000000018003C722 case 5
0x18003c758  mov     [rcx-1], r11b
0x18003c75c  retn
0x18003c760  mov     [rcx-0Ch], r11; jumptable 000000018003C722 case 12
0x18003c764  mov     [rcx-4], r11d; jumptable 000000018003C722 case 4
0x18003c768  retn
0x18003c769  mov     [rcx-0Bh], r11; jumptable 000000018003C722 case 11
0x18003c76d  mov     [rcx-3], r11w
0x18003c772  mov     [rcx-1], r11b
0x18003c776  retn
0x18003c777  mov     [rcx-9], r11; jumptable 000000018003C722 case 9
0x18003c77b  mov     [rcx-1], r11b
0x18003c77f  retn
0x18003c780  mov     [rcx-0Ah], r11; jumptable 000000018003C722 case 10
0x18003c784  mov     [rcx-2], r11w
0x18003c789  retn
0x18003c78a  mov     [rcx-8], r11; jumptable 000000018003C722 case 8
0x18003c78e  retn
0x18003c790  punpcklqdq xmm0, xmm0
0x18003c794  cmp     r8, 20h ; ' '
0x18003c798  ja      short loc_18003C7A6
0x18003c79a  movdqu  xmmword ptr [rcx], xmm0
0x18003c79e  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x18003c7a5  retn
0x18003c7a6  cmp     cs:__isa_available, 3
0x18003c7ad  jb      loc_18003C990
0x18003c7b3  cmp     r8, cs:__memset_fast_string_threshold
0x18003c7ba  jbe     short loc_18003C7D2
0x18003c7bc  cmp     r8, cs:__memset_nt_threshold
0x18003c7c3  ja      short loc_18003C7D2
0x18003c7c5  test    byte ptr cs:__favor, 2
0x18003c7cc  jnz     memset_repstos
0x18003c7d2  vinsertf128 ymm0, ymm0, xmm0, 1
0x18003c7d8  mov     r9, rcx
0x18003c7db  and     r9, 1Fh
0x18003c7df  sub     r9, 20h ; ' '
0x18003c7e3  sub     rcx, r9
0x18003c7e6  sub     rdx, r9
0x18003c7e9  add     r8, r9
0x18003c7ec  cmp     r8, 100h
0x18003c7f3  jbe     short loc_18003C85A
0x18003c7f5  cmp     r8, cs:__memset_nt_threshold
0x18003c7fc  ja      loc_18003C8D0
0x18003c802  nop     word ptr [rax+rax+00000000h]
0x18003c810  vmovdqa ymmword ptr [rcx], ymm0
0x18003c814  vmovdqa ymmword ptr [rcx+20h], ymm0
0x18003c819  vmovdqa ymmword ptr [rcx+40h], ymm0
0x18003c81e  vmovdqa ymmword ptr [rcx+60h], ymm0
0x18003c823  vmovdqa ymmword ptr [rcx+80h], ymm0
0x18003c82b  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x18003c833  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x18003c83b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x18003c843  add     rcx, 100h
0x18003c84a  sub     r8, 100h
0x18003c851  cmp     r8, 100h
0x18003c858  jnb     short loc_18003C810
0x18003c85a  lea     r9, [r8+1Fh]
0x18003c85e  and     r9, 0FFFFFFFFFFFFFFE0h
0x18003c862  mov     r11, r9
0x18003c865  shr     r11, 5
0x18003c869  and     r11, 0Fh; switch 16 cases
0x18003c86d  mov     r11d, ds:(jpt_18003C878 - 180000000h)[r10+r11*4]
0x18003c875  add     r11, r10
0x18003c878  jmp     r11; switch jump
0x18003c87b  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018003C878 case 8
0x18003c885  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018003C878 case 7
0x18003c88f  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018003C878 case 6
0x18003c899  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018003C878 case 5
0x18003c8a3  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018003C878 case 4
0x18003c8aa  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018003C878 case 3
0x18003c8b1  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018003C878 case 2
0x18003c8b8  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018003C878 case 1
0x18003c8bf  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018003C878 cases 0,9-15
0x18003c8c3  vzeroupper
0x18003c8c6  retn
0x18003c8d0  vmovntdq ymmword ptr [rcx], ymm0
0x18003c8d4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x18003c8d9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x18003c8de  vmovntdq ymmword ptr [rcx+60h], ymm0
0x18003c8e3  vmovntdq ymmword ptr [rcx+80h], ymm0
0x18003c8eb  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x18003c8f3  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x18003c8fb  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x18003c903  add     rcx, 100h
0x18003c90a  sub     r8, 100h
0x18003c911  cmp     r8, 100h
0x18003c918  jnb     short loc_18003C8D0
0x18003c91a  lea     r9, [r8+1Fh]
0x18003c91e  and     r9, 0FFFFFFFFFFFFFFE0h
0x18003c922  mov     r11, r9
0x18003c925  shr     r11, 5
0x18003c929  and     r11, 0Fh; switch 16 cases
0x18003c92d  mov     r11d, ds:(jpt_18003C938 - 180000000h)[r10+r11*4]
0x18003c935  add     r11, r10
0x18003c938  jmp     r11; switch jump
0x18003c93b  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000018003C938 case 8
0x18003c945  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000018003C938 case 7
0x18003c94f  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000018003C938 case 6
0x18003c959  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000018003C938 case 5
0x18003c963  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000018003C938 case 4
0x18003c96a  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000018003C938 case 3
0x18003c971  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000018003C938 case 2
0x18003c978  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000018003C938 case 1
0x18003c97f  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018003C938 cases 0,9-15
0x18003c983  sfence
0x18003c986  vzeroupper
0x18003c989  retn
0x18003c990  cmp     r8, cs:__memset_fast_string_threshold
0x18003c997  jbe     short loc_18003C9A6
0x18003c999  test    byte ptr cs:__favor, 2
0x18003c9a0  jnz     memset_repstos
0x18003c9a6  mov     r9, rcx
0x18003c9a9  and     r9, 0Fh
0x18003c9ad  sub     r9, 10h
0x18003c9b1  sub     rcx, r9
0x18003c9b4  sub     rdx, r9
0x18003c9b7  add     r8, r9
0x18003c9ba  cmp     r8, 80h
0x18003c9c1  jbe     short loc_18003CA0E
0x18003c9c3  nop     word ptr [rax+rax+00000000h]
0x18003c9d0  movdqa  xmmword ptr [rcx], xmm0
0x18003c9d4  movdqa  xmmword ptr [rcx+10h], xmm0
0x18003c9d9  movdqa  xmmword ptr [rcx+20h], xmm0
0x18003c9de  movdqa  xmmword ptr [rcx+30h], xmm0
0x18003c9e3  movdqa  xmmword ptr [rcx+40h], xmm0
0x18003c9e8  movdqa  xmmword ptr [rcx+50h], xmm0
0x18003c9ed  movdqa  xmmword ptr [rcx+60h], xmm0
0x18003c9f2  movdqa  xmmword ptr [rcx+70h], xmm0
0x18003c9f7  add     rcx, 80h
0x18003c9fe  sub     r8, 80h
0x18003ca05  cmp     r8, 80h
0x18003ca0c  jnb     short loc_18003C9D0
0x18003ca0e  lea     r9, [r8+0Fh]
0x18003ca12  and     r9, 0FFFFFFFFFFFFFFF0h
0x18003ca16  mov     r11, r9
0x18003ca19  shr     r11, 4
0x18003ca1d  and     r11, 0Fh; switch 16 cases
0x18003ca21  mov     r11d, ds:(jpt_18003CA2C - 180000000h)[r10+r11*4]
0x18003ca29  add     r11, r10
0x18003ca2c  jmp     r11; switch jump
0x18003ca2f  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 000000018003CA2C case 8
0x18003ca36  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 000000018003CA2C case 7
0x18003ca3d  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 000000018003CA2C case 6
0x18003ca44  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 000000018003CA2C case 5
0x18003ca4b  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 000000018003CA2C case 4
0x18003ca52  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 000000018003CA2C case 3
0x18003ca59  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 000000018003CA2C case 2
0x18003ca60  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 000000018003CA2C case 1
0x18003ca67  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018003CA2C cases 0,9-15
0x18003ca6b  retn
```
