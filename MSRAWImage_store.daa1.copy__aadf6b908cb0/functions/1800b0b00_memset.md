# memset

- ea: `0x1800b0b00`
- end: `0x1800b0e88`
- name: `memset`
- size: `904`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `70`
- callee_count: `2`
- tags: ``

## callers

- `0x180001790`
- `0x1800021f0`
- `0x1800022b0`
- `0x180006710`
- `0x180006bc0`
- `0x18000adf0`
- `0x18000d370`
- `0x18000e780`
- `0x18000f5a0`
- `0x180010410`
- `0x180013a50`
- `0x180013f40`
- `0x180014020`
- `0x1800141d0`
- `0x180017ca0`
- `0x18001c700`
- `0x180021a40`
- `0x180021dc0`
- `0x180022ba0`
- `0x180026a10`
- `0x1800276f0`
- `0x180029700`
- `0x180029d00`
- `0x18002b5b0`
- `0x18002c4d0`
- `0x18002caa0`
- `0x18002cf40`
- `0x18002ea30`
- `0x180031170`
- `0x1800420e0`
- `0x1800434c0`
- `0x1800463c0`
- `0x1800471e0`
- `0x180048320`
- `0x180049730`
- `0x18004a040`
- `0x18004ad50`
- `0x18004cc00`
- `0x18004eea0`
- `0x18004ffd0`
- `0x180053cc0`
- `0x1800546b0`
- `0x1800570e0`
- `0x18005bcb0`
- `0x18005c430`
- `0x18005c6c0`
- `0x18005caa0`
- `0x18005ed30`
- `0x18005f230`
- `0x180064040`

## callees

- `0x1800b0ae0`
- `0x1800b0b00`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v5; // r11
  char *v7; // rcx
  __m128i v8; // xmm0
  __int64 v10; // r9
  __int64 v15; // r9
  __m128i *v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r9

  result = a1;
  v5 = 0x101010101010101LL * (unsigned __int8)Val;
  v7 = (char *)a1 + Size;
  switch ( Size )
  {
    case 0uLL:
      return result;
    case 1uLL:
      goto LABEL_5;
    case 2uLL:
      goto LABEL_8;
    case 3uLL:
      goto LABEL_4;
    case 4uLL:
      goto LABEL_12;
    case 5uLL:
      goto LABEL_10;
    case 6uLL:
      goto LABEL_7;
    case 7uLL:
      goto LABEL_3;
    case 8uLL:
      *((_QWORD *)v7 - 1) = v5;
      return result;
    case 9uLL:
      *(_QWORD *)(v7 - 9) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xAuLL:
      *(_QWORD *)(v7 - 10) = v5;
      *((_WORD *)v7 - 1) = v5;
      return result;
    case 0xBuLL:
      *(_QWORD *)(v7 - 11) = v5;
      *(_WORD *)(v7 - 3) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xCuLL:
      *(_QWORD *)(v7 - 12) = v5;
LABEL_12:
      *((_DWORD *)v7 - 1) = v5;
      return result;
    case 0xDuLL:
      *(_QWORD *)(v7 - 13) = v5;
LABEL_10:
      *(_DWORD *)(v7 - 5) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xEuLL:
      *(_QWORD *)(v7 - 14) = v5;
LABEL_7:
      *(_DWORD *)(v7 - 6) = v5;
LABEL_8:
      *((_WORD *)v7 - 1) = v5;
      return result;
    case 0xFuLL:
      *(_QWORD *)(v7 - 15) = v5;
LABEL_3:
      *(_DWORD *)(v7 - 7) = v5;
LABEL_4:
      *(_WORD *)(v7 - 3) = v5;
LABEL_5:
      *(v7 - 1) = Val;
      return result;
    default:
      v8 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v5, (__m128i)(unsigned __int64)v5);
      if ( Size <= 0x20 )
      {
        *(__m128i *)a1 = v8;
        *(__m128i *)((char *)a1 + Size - 16) = v8;
        return result;
      }
      if ( (unsigned int)_isa_available < 3 )
      {
        if ( Size <= _memset_fast_string_threshold || (_favor & 2) == 0 )
        {
          v15 = ((unsigned __int8)a1 & 0xF) - 16LL;
          v16 = (__m128i *)((char *)a1 - v15);
          v17 = v15 + Size;
          if ( v17 > 0x80 )
          {
            do
            {
              *v16 = v8;
              v16[1] = v8;
              v16[2] = v8;
              v16[3] = v8;
              v16[4] = v8;
              v16[5] = v8;
              v16[6] = v8;
              v16[7] = v8;
              v16 += 8;
              v17 -= 128LL;
            }
            while ( v17 >= 0x80 );
          }
          v18 = (v17 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v18 >> 4 )
          {
            case 0uLL:
              goto LABEL_60;
            case 1uLL:
              goto LABEL_59;
            case 2uLL:
              goto LABEL_58;
            case 3uLL:
              goto LABEL_57;
            case 4uLL:
              goto LABEL_56;
            case 5uLL:
              goto LABEL_55;
            case 6uLL:
              goto LABEL_54;
            case 7uLL:
              goto LABEL_53;
            case 8uLL:
              *(__m128i *)((char *)&v16[-8] + v18) = v8;
LABEL_53:
              *(__m128i *)((char *)&v16[-7] + v18) = v8;
LABEL_54:
              *(__m128i *)((char *)&v16[-6] + v18) = v8;
LABEL_55:
              *(__m128i *)((char *)&v16[-5] + v18) = v8;
LABEL_56:
              *(__m128i *)((char *)&v16[-4] + v18) = v8;
LABEL_57:
              *(__m128i *)((char *)&v16[-3] + v18) = v8;
LABEL_58:
              *(__m128i *)((char *)&v16[-2] + v18) = v8;
LABEL_59:
              *(__m128i *)((char *)&v16[-1] + v17) = v8;
LABEL_60:
              *(__m128i *)result = v8;
              break;
          }
          return result;
        }
        return (void *)memset_repstos(a1);
      }
      if ( Size > _memset_fast_string_threshold && Size <= _memset_nt_threshold && (_favor & 2) != 0 )
        return (void *)memset_repstos(a1);
      __asm { vinsertf128 ymm0, ymm0, xmm0, 1 }
      v10 = ((unsigned __int8)a1 & 0x1F) - 32LL;
      _RCX = (char *)a1 - v10;
      _R8 = v10 + Size;
      if ( _R8 <= 0x100 )
        goto LABEL_26;
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
LABEL_26:
        _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto LABEL_35;
          case 1uLL:
            goto LABEL_34;
          case 2uLL:
            goto LABEL_33;
          case 3uLL:
            goto LABEL_32;
          case 4uLL:
            goto LABEL_31;
          case 5uLL:
            goto LABEL_30;
          case 6uLL:
            goto LABEL_29;
          case 7uLL:
            goto LABEL_28;
          case 8uLL:
            __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 00000001800B0C94 case 8 }
LABEL_28:
            __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 00000001800B0C94 case 7 }
LABEL_29:
            __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 00000001800B0C94 case 6 }
LABEL_30:
            __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 00000001800B0C94 case 5 }
LABEL_31:
            __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 00000001800B0C94 case 4 }
LABEL_32:
            __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 00000001800B0C94 case 3 }
LABEL_33:
            __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 00000001800B0C94 case 2 }
LABEL_34:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 00000001800B0C94 case 1 }
LABEL_35:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 00000001800B0C94 case 0
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
      switch ( _R9 >> 5 )
      {
        case 0uLL:
          goto LABEL_46;
        case 1uLL:
          goto LABEL_45;
        case 2uLL:
          goto LABEL_44;
        case 3uLL:
          goto LABEL_43;
        case 4uLL:
          goto LABEL_42;
        case 5uLL:
          goto LABEL_41;
        case 6uLL:
          goto LABEL_40;
        case 7uLL:
          goto LABEL_39;
        case 8uLL:
          __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 00000001800B0D54 case 8 }
LABEL_39:
          __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 00000001800B0D54 case 7 }
LABEL_40:
          __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 00000001800B0D54 case 6 }
LABEL_41:
          __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 00000001800B0D54 case 5 }
LABEL_42:
          __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 00000001800B0D54 case 4 }
LABEL_43:
          __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 00000001800B0D54 case 3 }
LABEL_44:
          __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 00000001800B0D54 case 2 }
LABEL_45:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 00000001800B0D54 case 1 }
LABEL_46:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 00000001800B0D54 case 0 }
          _mm_sfence();
          __asm { vzeroupper }
          break;
      }
      return result;
  }
}

```

## disassembly

```asm
0x1800b0b00  mov     rax, rcx
0x1800b0b03  mov     r9, rcx
0x1800b0b06  lea     r10, __ImageBase
0x1800b0b0d  movzx   edx, dl
0x1800b0b10  mov     r11, 101010101010101h
0x1800b0b1a  imul    r11, rdx
0x1800b0b1e  movq    xmm0, r11
0x1800b0b23  cmp     r8, 0Fh; switch 16 cases
0x1800b0b27  ja      def_1800B0B3E; jumptable 00000001800B0B3E default case
0x1800b0b2d  nop     dword ptr [rax]
0x1800b0b30  add     rcx, r8
0x1800b0b33  mov     r9d, ds:(jpt_1800B0B3E - 180000000h)[r10+r8*4]
0x1800b0b3b  add     r9, r10
0x1800b0b3e  jmp     r9; switch jump
0x1800b0b41  mov     [rcx-0Fh], r11; jumptable 00000001800B0B3E case 15
0x1800b0b45  mov     [rcx-7], r11d; jumptable 00000001800B0B3E case 7
0x1800b0b49  mov     [rcx-3], r11w; jumptable 00000001800B0B3E case 3
0x1800b0b4e  mov     [rcx-1], r11b; jumptable 00000001800B0B3E case 1
0x1800b0b52  retn; jumptable 00000001800B0B3E case 0
0x1800b0b53  mov     [rcx-0Eh], r11; jumptable 00000001800B0B3E case 14
0x1800b0b57  mov     [rcx-6], r11d; jumptable 00000001800B0B3E case 6
0x1800b0b5b  mov     [rcx-2], r11w; jumptable 00000001800B0B3E case 2
0x1800b0b60  retn
0x1800b0b70  mov     [rcx-0Dh], r11; jumptable 00000001800B0B3E case 13
0x1800b0b74  mov     [rcx-5], r11d; jumptable 00000001800B0B3E case 5
0x1800b0b78  mov     [rcx-1], r11b
0x1800b0b7c  retn
0x1800b0b80  mov     [rcx-0Ch], r11; jumptable 00000001800B0B3E case 12
0x1800b0b84  mov     [rcx-4], r11d; jumptable 00000001800B0B3E case 4
0x1800b0b88  retn
0x1800b0b89  mov     [rcx-0Bh], r11; jumptable 00000001800B0B3E case 11
0x1800b0b8d  mov     [rcx-3], r11w
0x1800b0b92  mov     [rcx-1], r11b
0x1800b0b96  retn
0x1800b0b97  mov     [rcx-9], r11; jumptable 00000001800B0B3E case 9
0x1800b0b9b  mov     [rcx-1], r11b
0x1800b0b9f  retn
0x1800b0ba0  mov     [rcx-0Ah], r11; jumptable 00000001800B0B3E case 10
0x1800b0ba4  mov     [rcx-2], r11w
0x1800b0ba9  retn
0x1800b0baa  mov     [rcx-8], r11; jumptable 00000001800B0B3E case 8
0x1800b0bae  retn
0x1800b0bb0  punpcklqdq xmm0, xmm0; jumptable 00000001800B0B3E default case
0x1800b0bb4  cmp     r8, 20h ; ' '
0x1800b0bb8  ja      short loc_1800B0BC6
0x1800b0bba  movdqu  xmmword ptr [rcx], xmm0
0x1800b0bbe  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x1800b0bc5  retn
0x1800b0bc6  cmp     cs:__isa_available, 3
0x1800b0bcd  jb      loc_1800B0DB0
0x1800b0bd3  cmp     r8, cs:__memset_fast_string_threshold
0x1800b0bda  jbe     short loc_1800B0BF2
0x1800b0bdc  cmp     r8, cs:__memset_nt_threshold
0x1800b0be3  ja      short loc_1800B0BF2
0x1800b0be5  test    byte ptr cs:__favor, 2
0x1800b0bec  jnz     memset_repstos
0x1800b0bf2  vinsertf128 ymm0, ymm0, xmm0, 1
0x1800b0bf8  mov     r9, rcx
0x1800b0bfb  and     r9, 1Fh
0x1800b0bff  sub     r9, 20h ; ' '
0x1800b0c03  sub     rcx, r9
0x1800b0c06  sub     rdx, r9
0x1800b0c09  add     r8, r9
0x1800b0c0c  cmp     r8, 100h
0x1800b0c13  jbe     short loc_1800B0C7A
0x1800b0c15  cmp     r8, cs:__memset_nt_threshold
0x1800b0c1c  ja      loc_1800B0CF0
0x1800b0c22  nop     word ptr [rax+rax+00000000h]
0x1800b0c30  vmovdqa ymmword ptr [rcx], ymm0
0x1800b0c34  vmovdqa ymmword ptr [rcx+20h], ymm0
0x1800b0c39  vmovdqa ymmword ptr [rcx+40h], ymm0
0x1800b0c3e  vmovdqa ymmword ptr [rcx+60h], ymm0
0x1800b0c43  vmovdqa ymmword ptr [rcx+80h], ymm0
0x1800b0c4b  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x1800b0c53  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x1800b0c5b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x1800b0c63  add     rcx, 100h
0x1800b0c6a  sub     r8, 100h
0x1800b0c71  cmp     r8, 100h
0x1800b0c78  jnb     short loc_1800B0C30
0x1800b0c7a  lea     r9, [r8+1Fh]
0x1800b0c7e  and     r9, 0FFFFFFFFFFFFFFE0h
0x1800b0c82  mov     r11, r9
0x1800b0c85  shr     r11, 5
0x1800b0c89  mov     r11d, ds:(jpt_1800B0C94 - 180000000h)[r10+r11*4]; switch 9 cases
0x1800b0c91  add     r11, r10
0x1800b0c94  jmp     r11; switch jump
0x1800b0c97  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 00000001800B0C94 case 8
0x1800b0ca1  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 00000001800B0C94 case 7
0x1800b0cab  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 00000001800B0C94 case 6
0x1800b0cb5  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 00000001800B0C94 case 5
0x1800b0cbf  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 00000001800B0C94 case 4
0x1800b0cc6  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 00000001800B0C94 case 3
0x1800b0ccd  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 00000001800B0C94 case 2
0x1800b0cd4  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 00000001800B0C94 case 1
0x1800b0cdb  vmovdqu ymmword ptr [rax], ymm0; jumptable 00000001800B0C94 case 0
0x1800b0cdf  vzeroupper
0x1800b0ce2  retn
0x1800b0cf0  vmovntdq ymmword ptr [rcx], ymm0
0x1800b0cf4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x1800b0cf9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x1800b0cfe  vmovntdq ymmword ptr [rcx+60h], ymm0
0x1800b0d03  vmovntdq ymmword ptr [rcx+80h], ymm0
0x1800b0d0b  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x1800b0d13  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x1800b0d1b  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x1800b0d23  add     rcx, 100h
0x1800b0d2a  sub     r8, 100h
0x1800b0d31  cmp     r8, 100h
0x1800b0d38  jnb     short loc_1800B0CF0
0x1800b0d3a  lea     r9, [r8+1Fh]
0x1800b0d3e  and     r9, 0FFFFFFFFFFFFFFE0h
0x1800b0d42  mov     r11, r9
0x1800b0d45  shr     r11, 5
0x1800b0d49  mov     r11d, ds:(jpt_1800B0D54 - 180000000h)[r10+r11*4]; switch 9 cases
0x1800b0d51  add     r11, r10
0x1800b0d54  jmp     r11; switch jump
0x1800b0d57  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 00000001800B0D54 case 8
0x1800b0d61  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 00000001800B0D54 case 7
0x1800b0d6b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 00000001800B0D54 case 6
0x1800b0d75  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 00000001800B0D54 case 5
0x1800b0d7f  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 00000001800B0D54 case 4
0x1800b0d86  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 00000001800B0D54 case 3
0x1800b0d8d  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 00000001800B0D54 case 2
0x1800b0d94  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 00000001800B0D54 case 1
0x1800b0d9b  vmovdqu ymmword ptr [rax], ymm0; jumptable 00000001800B0D54 case 0
0x1800b0d9f  sfence
0x1800b0da2  vzeroupper
0x1800b0da5  retn
0x1800b0db0  cmp     r8, cs:__memset_fast_string_threshold
0x1800b0db7  jbe     short loc_1800B0DC6
0x1800b0db9  test    byte ptr cs:__favor, 2
0x1800b0dc0  jnz     memset_repstos
0x1800b0dc6  mov     r9, rcx
0x1800b0dc9  and     r9, 0Fh
0x1800b0dcd  sub     r9, 10h
0x1800b0dd1  sub     rcx, r9
0x1800b0dd4  sub     rdx, r9
0x1800b0dd7  add     r8, r9
0x1800b0dda  cmp     r8, 80h
0x1800b0de1  jbe     short loc_1800B0E2E
0x1800b0de3  nop     word ptr [rax+rax+00000000h]
0x1800b0df0  movdqa  xmmword ptr [rcx], xmm0
0x1800b0df4  movdqa  xmmword ptr [rcx+10h], xmm0
0x1800b0df9  movdqa  xmmword ptr [rcx+20h], xmm0
0x1800b0dfe  movdqa  xmmword ptr [rcx+30h], xmm0
0x1800b0e03  movdqa  xmmword ptr [rcx+40h], xmm0
0x1800b0e08  movdqa  xmmword ptr [rcx+50h], xmm0
0x1800b0e0d  movdqa  xmmword ptr [rcx+60h], xmm0
0x1800b0e12  movdqa  xmmword ptr [rcx+70h], xmm0
0x1800b0e17  add     rcx, 80h
0x1800b0e1e  sub     r8, 80h
0x1800b0e25  cmp     r8, 80h
0x1800b0e2c  jnb     short loc_1800B0DF0
0x1800b0e2e  lea     r9, [r8+0Fh]
0x1800b0e32  and     r9, 0FFFFFFFFFFFFFFF0h
0x1800b0e36  mov     r11, r9
0x1800b0e39  shr     r11, 4
0x1800b0e3d  mov     r11d, ds:(jpt_1800B0E48 - 180000000h)[r10+r11*4]; switch 9 cases
0x1800b0e45  add     r11, r10
0x1800b0e48  jmp     r11; switch jump
0x1800b0e4b  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 00000001800B0E48 case 8
0x1800b0e52  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 00000001800B0E48 case 7
0x1800b0e59  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 00000001800B0E48 case 6
0x1800b0e60  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 00000001800B0E48 case 5
0x1800b0e67  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 00000001800B0E48 case 4
0x1800b0e6e  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 00000001800B0E48 case 3
0x1800b0e75  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 00000001800B0E48 case 2
0x1800b0e7c  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 00000001800B0E48 case 1
0x1800b0e83  movdqu  xmmword ptr [rax], xmm0; jumptable 00000001800B0E48 case 0
0x1800b0e87  retn
```
