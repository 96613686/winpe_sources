# memset

- ea: `0x180047ab0`
- end: `0x180047e38`
- name: `memset`
- size: `904`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `59`
- callee_count: `2`
- tags: ``

## callers

- `0x180004714`
- `0x180004b14`
- `0x1800054ac`
- `0x18000622c`
- `0x180006864`
- `0x180007230`
- `0x1800076f8`
- `0x180007820`
- `0x180007ef8`
- `0x1800088fc`
- `0x1800089f4`
- `0x180008af0`
- `0x180009e1c`
- `0x180009f40`
- `0x18000a2a8`
- `0x18000b024`
- `0x18000b638`
- `0x18000b9d4`
- `0x18000c510`
- `0x18000cf18`
- `0x18000d70c`
- `0x18000d908`
- `0x18000ea38`
- `0x18000f7a0`
- `0x180018f44`
- `0x18001913c`
- `0x18001a8cc`
- `0x18001af10`
- `0x18001de28`
- `0x18001e7e8`
- `0x18001ecd4`
- `0x18001ee10`
- `0x18001fcc0`
- `0x180020344`
- `0x180020a8c`
- `0x180020c6c`
- `0x180022508`
- `0x180023428`
- `0x180024dac`
- `0x180025688`
- `0x180025de8`
- `0x180026d90`
- `0x180027444`
- `0x180027598`
- `0x180030cf4`
- `0x180030e0c`
- `0x1800319f0`
- `0x180032fc8`
- `0x180033264`
- `0x180035cb0`

## callees

- `0x180047a90`
- `0x180047ab0`

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
            __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000180047C44 case 8 }
LABEL_28:
            __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000180047C44 case 7 }
LABEL_29:
            __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000180047C44 case 6 }
LABEL_30:
            __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000180047C44 case 5 }
LABEL_31:
            __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000180047C44 case 4 }
LABEL_32:
            __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000180047C44 case 3 }
LABEL_33:
            __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000180047C44 case 2 }
LABEL_34:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000180047C44 case 1 }
LABEL_35:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180047C44 case 0
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
          __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000180047D04 case 8 }
LABEL_39:
          __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000180047D04 case 7 }
LABEL_40:
          __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000180047D04 case 6 }
LABEL_41:
          __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000180047D04 case 5 }
LABEL_42:
          __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000180047D04 case 4 }
LABEL_43:
          __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000180047D04 case 3 }
LABEL_44:
          __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000180047D04 case 2 }
LABEL_45:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000180047D04 case 1 }
LABEL_46:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180047D04 case 0 }
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
0x180047ab0  mov     rax, rcx
0x180047ab3  mov     r9, rcx
0x180047ab6  lea     r10, __ImageBase
0x180047abd  movzx   edx, dl
0x180047ac0  mov     r11, 101010101010101h
0x180047aca  imul    r11, rdx
0x180047ace  movq    xmm0, r11
0x180047ad3  cmp     r8, 0Fh; switch 16 cases
0x180047ad7  ja      def_180047AEE; jumptable 0000000180047AEE default case
0x180047add  nop     dword ptr [rax]
0x180047ae0  add     rcx, r8
0x180047ae3  mov     r9d, ds:(jpt_180047AEE - 180000000h)[r10+r8*4]
0x180047aeb  add     r9, r10
0x180047aee  jmp     r9; switch jump
0x180047af1  mov     [rcx-0Fh], r11; jumptable 0000000180047AEE case 15
0x180047af5  mov     [rcx-7], r11d; jumptable 0000000180047AEE case 7
0x180047af9  mov     [rcx-3], r11w; jumptable 0000000180047AEE case 3
0x180047afe  mov     [rcx-1], r11b; jumptable 0000000180047AEE case 1
0x180047b02  retn; jumptable 0000000180047AEE case 0
0x180047b03  mov     [rcx-0Eh], r11; jumptable 0000000180047AEE case 14
0x180047b07  mov     [rcx-6], r11d; jumptable 0000000180047AEE case 6
0x180047b0b  mov     [rcx-2], r11w; jumptable 0000000180047AEE case 2
0x180047b10  retn
0x180047b20  mov     [rcx-0Dh], r11; jumptable 0000000180047AEE case 13
0x180047b24  mov     [rcx-5], r11d; jumptable 0000000180047AEE case 5
0x180047b28  mov     [rcx-1], r11b
0x180047b2c  retn
0x180047b30  mov     [rcx-0Ch], r11; jumptable 0000000180047AEE case 12
0x180047b34  mov     [rcx-4], r11d; jumptable 0000000180047AEE case 4
0x180047b38  retn
0x180047b39  mov     [rcx-0Bh], r11; jumptable 0000000180047AEE case 11
0x180047b3d  mov     [rcx-3], r11w
0x180047b42  mov     [rcx-1], r11b
0x180047b46  retn
0x180047b47  mov     [rcx-9], r11; jumptable 0000000180047AEE case 9
0x180047b4b  mov     [rcx-1], r11b
0x180047b4f  retn
0x180047b50  mov     [rcx-0Ah], r11; jumptable 0000000180047AEE case 10
0x180047b54  mov     [rcx-2], r11w
0x180047b59  retn
0x180047b5a  mov     [rcx-8], r11; jumptable 0000000180047AEE case 8
0x180047b5e  retn
0x180047b60  punpcklqdq xmm0, xmm0; jumptable 0000000180047AEE default case
0x180047b64  cmp     r8, 20h ; ' '
0x180047b68  ja      short loc_180047B76
0x180047b6a  movdqu  xmmword ptr [rcx], xmm0
0x180047b6e  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x180047b75  retn
0x180047b76  cmp     cs:__isa_available, 3
0x180047b7d  jb      loc_180047D60
0x180047b83  cmp     r8, cs:__memset_fast_string_threshold
0x180047b8a  jbe     short loc_180047BA2
0x180047b8c  cmp     r8, cs:__memset_nt_threshold
0x180047b93  ja      short loc_180047BA2
0x180047b95  test    byte ptr cs:__favor, 2
0x180047b9c  jnz     memset_repstos
0x180047ba2  vinsertf128 ymm0, ymm0, xmm0, 1
0x180047ba8  mov     r9, rcx
0x180047bab  and     r9, 1Fh
0x180047baf  sub     r9, 20h ; ' '
0x180047bb3  sub     rcx, r9
0x180047bb6  sub     rdx, r9
0x180047bb9  add     r8, r9
0x180047bbc  cmp     r8, 100h
0x180047bc3  jbe     short loc_180047C2A
0x180047bc5  cmp     r8, cs:__memset_nt_threshold
0x180047bcc  ja      loc_180047CA0
0x180047bd2  nop     word ptr [rax+rax+00000000h]
0x180047be0  vmovdqa ymmword ptr [rcx], ymm0
0x180047be4  vmovdqa ymmword ptr [rcx+20h], ymm0
0x180047be9  vmovdqa ymmword ptr [rcx+40h], ymm0
0x180047bee  vmovdqa ymmword ptr [rcx+60h], ymm0
0x180047bf3  vmovdqa ymmword ptr [rcx+80h], ymm0
0x180047bfb  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x180047c03  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x180047c0b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x180047c13  add     rcx, 100h
0x180047c1a  sub     r8, 100h
0x180047c21  cmp     r8, 100h
0x180047c28  jnb     short loc_180047BE0
0x180047c2a  lea     r9, [r8+1Fh]
0x180047c2e  and     r9, 0FFFFFFFFFFFFFFE0h
0x180047c32  mov     r11, r9
0x180047c35  shr     r11, 5
0x180047c39  mov     r11d, ds:(jpt_180047C44 - 180000000h)[r10+r11*4]; switch 9 cases
0x180047c41  add     r11, r10
0x180047c44  jmp     r11; switch jump
0x180047c47  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000180047C44 case 8
0x180047c51  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000180047C44 case 7
0x180047c5b  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000180047C44 case 6
0x180047c65  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000180047C44 case 5
0x180047c6f  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000180047C44 case 4
0x180047c76  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000180047C44 case 3
0x180047c7d  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000180047C44 case 2
0x180047c84  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000180047C44 case 1
0x180047c8b  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180047C44 case 0
0x180047c8f  vzeroupper
0x180047c92  retn
0x180047ca0  vmovntdq ymmword ptr [rcx], ymm0
0x180047ca4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x180047ca9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x180047cae  vmovntdq ymmword ptr [rcx+60h], ymm0
0x180047cb3  vmovntdq ymmword ptr [rcx+80h], ymm0
0x180047cbb  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x180047cc3  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x180047ccb  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x180047cd3  add     rcx, 100h
0x180047cda  sub     r8, 100h
0x180047ce1  cmp     r8, 100h
0x180047ce8  jnb     short loc_180047CA0
0x180047cea  lea     r9, [r8+1Fh]
0x180047cee  and     r9, 0FFFFFFFFFFFFFFE0h
0x180047cf2  mov     r11, r9
0x180047cf5  shr     r11, 5
0x180047cf9  mov     r11d, ds:(jpt_180047D04 - 180000000h)[r10+r11*4]; switch 9 cases
0x180047d01  add     r11, r10
0x180047d04  jmp     r11; switch jump
0x180047d07  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000180047D04 case 8
0x180047d11  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000180047D04 case 7
0x180047d1b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000180047D04 case 6
0x180047d25  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000180047D04 case 5
0x180047d2f  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000180047D04 case 4
0x180047d36  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000180047D04 case 3
0x180047d3d  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000180047D04 case 2
0x180047d44  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000180047D04 case 1
0x180047d4b  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180047D04 case 0
0x180047d4f  sfence
0x180047d52  vzeroupper
0x180047d55  retn
0x180047d60  cmp     r8, cs:__memset_fast_string_threshold
0x180047d67  jbe     short loc_180047D76
0x180047d69  test    byte ptr cs:__favor, 2
0x180047d70  jnz     memset_repstos
0x180047d76  mov     r9, rcx
0x180047d79  and     r9, 0Fh
0x180047d7d  sub     r9, 10h
0x180047d81  sub     rcx, r9
0x180047d84  sub     rdx, r9
0x180047d87  add     r8, r9
0x180047d8a  cmp     r8, 80h
0x180047d91  jbe     short loc_180047DDE
0x180047d93  nop     word ptr [rax+rax+00000000h]
0x180047da0  movdqa  xmmword ptr [rcx], xmm0
0x180047da4  movdqa  xmmword ptr [rcx+10h], xmm0
0x180047da9  movdqa  xmmword ptr [rcx+20h], xmm0
0x180047dae  movdqa  xmmword ptr [rcx+30h], xmm0
0x180047db3  movdqa  xmmword ptr [rcx+40h], xmm0
0x180047db8  movdqa  xmmword ptr [rcx+50h], xmm0
0x180047dbd  movdqa  xmmword ptr [rcx+60h], xmm0
0x180047dc2  movdqa  xmmword ptr [rcx+70h], xmm0
0x180047dc7  add     rcx, 80h
0x180047dce  sub     r8, 80h
0x180047dd5  cmp     r8, 80h
0x180047ddc  jnb     short loc_180047DA0
0x180047dde  lea     r9, [r8+0Fh]
0x180047de2  and     r9, 0FFFFFFFFFFFFFFF0h
0x180047de6  mov     r11, r9
0x180047de9  shr     r11, 4
0x180047ded  mov     r11d, ds:(jpt_180047DF8 - 180000000h)[r10+r11*4]; switch 9 cases
0x180047df5  add     r11, r10
0x180047df8  jmp     r11; switch jump
0x180047dfb  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 0000000180047DF8 case 8
0x180047e02  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 0000000180047DF8 case 7
0x180047e09  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 0000000180047DF8 case 6
0x180047e10  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 0000000180047DF8 case 5
0x180047e17  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 0000000180047DF8 case 4
0x180047e1e  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 0000000180047DF8 case 3
0x180047e25  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 0000000180047DF8 case 2
0x180047e2c  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 0000000180047DF8 case 1
0x180047e33  movdqu  xmmword ptr [rax], xmm0; jumptable 0000000180047DF8 case 0
0x180047e37  retn
```
