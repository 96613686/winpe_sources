# memset

- ea: `0x14001e2d0`
- end: `0x14001e658`
- name: `memset`
- size: `904`
- prototype: `void *__cdecl(void *Dst, int Val, size_t Size)`
- caller_count: `87`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003a50`
- `0x140003ad0`
- `0x140004400`
- `0x140004a8c`
- `0x140004b48`
- `0x140007c98`
- `0x14000aa78`
- `0x14000b098`
- `0x1400115ec`
- `0x140011dac`
- `0x1400120a0`
- `0x1400127f8`
- `0x140013844`
- `0x140013a94`
- `0x1400140cc`
- `0x14001481c`
- `0x1400166b0`
- `0x14001a8d8`
- `0x14001b214`
- `0x14001c570`
- `0x14001c6d4`
- `0x140023050`
- `0x140023604`
- `0x1400251e8`
- `0x140025394`
- `0x140026868`
- `0x140028d78`
- `0x1400293d8`
- `0x140029648`
- `0x14002dd38`
- `0x1400325b4`
- `0x140032c2c`
- `0x140033ec0`
- `0x140037108`
- `0x1400372ec`
- `0x14003dfa0`
- `0x14003f3d0`
- `0x14003fbec`
- `0x140040a2c`
- `0x140041198`
- `0x1400464e8`
- `0x140046ad4`
- `0x140046e3c`
- `0x140047aa4`
- `0x140049364`
- `0x14004a4bc`
- `0x14004ab84`
- `0x14004ae50`
- `0x14004aed0`
- `0x14004b310`

## callees

- `0x14001e2b0`
- `0x14001e2d0`

## pseudocode

```c
void *__cdecl memset(void *Dst, int Val, size_t Size)
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

  result = Dst;
  v5 = 0x101010101010101LL * (unsigned __int8)Val;
  v7 = (char *)Dst + Size;
  switch ( Size )
  {
    case 0uLL:
      return result;
    case 1uLL:
      goto SetSmall1;
    case 2uLL:
      goto SetSmall2;
    case 3uLL:
      goto SetSmall3;
    case 4uLL:
      goto SetSmall4;
    case 5uLL:
      goto SetSmall5;
    case 6uLL:
      goto SetSmall6;
    case 7uLL:
      goto SetSmall7;
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
SetSmall4:
      *((_DWORD *)v7 - 1) = v5;
      return result;
    case 0xDuLL:
      *(_QWORD *)(v7 - 13) = v5;
SetSmall5:
      *(_DWORD *)(v7 - 5) = v5;
      *(v7 - 1) = Val;
      return result;
    case 0xEuLL:
      *(_QWORD *)(v7 - 14) = v5;
SetSmall6:
      *(_DWORD *)(v7 - 6) = v5;
SetSmall2:
      *((_WORD *)v7 - 1) = v5;
      return result;
    case 0xFuLL:
      *(_QWORD *)(v7 - 15) = v5;
SetSmall7:
      *(_DWORD *)(v7 - 7) = v5;
SetSmall3:
      *(_WORD *)(v7 - 3) = v5;
SetSmall1:
      *(v7 - 1) = Val;
      return result;
    default:
      v8 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v5, (__m128i)(unsigned __int64)v5);
      if ( Size <= 0x20 )
      {
        *(__m128i *)Dst = v8;
        *(__m128i *)((char *)Dst + Size - 16) = v8;
        return result;
      }
      if ( (unsigned int)dword_1400D68F0 < 3 )
      {
        if ( Size <= qword_1400D68F8 || (dword_1400D7800 & 2) == 0 )
        {
          v15 = ((unsigned __int8)Dst & 0xF) - 16LL;
          v16 = (__m128i *)((char *)Dst - v15);
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
              goto Set0XmmBlocks;
            case 1uLL:
              goto Set1XmmBlocks;
            case 2uLL:
              goto Set2XmmBlocks;
            case 3uLL:
              goto Set3XmmBlocks;
            case 4uLL:
              goto Set4XmmBlocks;
            case 5uLL:
              goto Set5XmmBlocks;
            case 6uLL:
              goto Set6XmmBlocks;
            case 7uLL:
              goto Set7XmmBlocks;
            case 8uLL:
              *(__m128i *)((char *)&v16[-8] + v18) = v8;
Set7XmmBlocks:
              *(__m128i *)((char *)&v16[-7] + v18) = v8;
Set6XmmBlocks:
              *(__m128i *)((char *)&v16[-6] + v18) = v8;
Set5XmmBlocks:
              *(__m128i *)((char *)&v16[-5] + v18) = v8;
Set4XmmBlocks:
              *(__m128i *)((char *)&v16[-4] + v18) = v8;
Set3XmmBlocks:
              *(__m128i *)((char *)&v16[-3] + v18) = v8;
Set2XmmBlocks:
              *(__m128i *)((char *)&v16[-2] + v18) = v8;
Set1XmmBlocks:
              *(__m128i *)((char *)&v16[-1] + v17) = v8;
Set0XmmBlocks:
              *(__m128i *)result = v8;
              break;
          }
          return result;
        }
        return (void *)memset_repstos(Dst);
      }
      if ( Size > qword_1400D68F8 && Size <= qword_1400D6900 && (dword_1400D7800 & 2) != 0 )
        return (void *)memset_repstos(Dst);
      __asm { vinsertf128 ymm0, ymm0, xmm0, 1 }
      v10 = ((unsigned __int8)Dst & 0x1F) - 32LL;
      _RCX = (char *)Dst - v10;
      _R8 = v10 + Size;
      if ( _R8 <= 0x100 )
        goto SetUpTo256WithYMM;
      if ( _R8 <= qword_1400D6900 )
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
SetUpTo256WithYMM:
        _R9 = (_R8 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto Set0YmmBlocks;
          case 1uLL:
            goto Set1YmmBlocks;
          case 2uLL:
            goto Set2YmmBlocks;
          case 3uLL:
            goto Set3YmmBlocks;
          case 4uLL:
            goto Set4YmmBlocks;
          case 5uLL:
            goto Set5YmmBlocks;
          case 6uLL:
            goto Set6YmmBlocks;
          case 7uLL:
            goto Set7YmmBlocks;
          case 8uLL:
            __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000014001E464 case 8 }
Set7YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000014001E464 case 7 }
Set6YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000014001E464 case 6 }
Set5YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000014001E464 case 5 }
Set4YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000014001E464 case 4 }
Set3YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000014001E464 case 3 }
Set2YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000014001E464 case 2 }
Set1YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000014001E464 case 1 }
Set0YmmBlocks:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001E464 case 0
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
          goto Set0YmmBlocksNT;
        case 1uLL:
          goto Set1YmmBlocksNT;
        case 2uLL:
          goto Set2YmmBlocksNT;
        case 3uLL:
          goto Set3YmmBlocksNT;
        case 4uLL:
          goto Set4YmmBlocksNT;
        case 5uLL:
          goto Set5YmmBlocksNT;
        case 6uLL:
          goto Set6YmmBlocksNT;
        case 7uLL:
          goto Set7YmmBlocksNT;
        case 8uLL:
          __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000014001E524 case 8 }
Set7YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000014001E524 case 7 }
Set6YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000014001E524 case 6 }
Set5YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000014001E524 case 5 }
Set4YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000014001E524 case 4 }
Set3YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000014001E524 case 3 }
Set2YmmBlocksNT:
          __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000014001E524 case 2 }
Set1YmmBlocksNT:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000014001E524 case 1 }
Set0YmmBlocksNT:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001E524 case 0 }
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
0x14001e2d0  mov     rax, rcx
0x14001e2d3  mov     r9, rcx
0x14001e2d6  lea     r10, cs:140000000h
0x14001e2dd  movzx   edx, dl
0x14001e2e0  mov     r11, 101010101010101h
0x14001e2ea  imul    r11, rdx
0x14001e2ee  movq    xmm0, r11
0x14001e2f3  cmp     r8, 0Fh; switch 16 cases
0x14001e2f7  ja      def_14001E30E; jumptable 000000014001E30E default case
0x14001e2fd  nop     dword ptr [rax]
0x14001e300  add     rcx, r8
0x14001e303  mov     r9d, ds:(jpt_14001E30E - 140000000h)[r10+r8*4]
0x14001e30b  add     r9, r10
0x14001e30e  jmp     r9; switch jump
0x14001e311  mov     [rcx-0Fh], r11; jumptable 000000014001E30E case 15
0x14001e315  mov     [rcx-7], r11d; jumptable 000000014001E30E case 7
0x14001e319  mov     [rcx-3], r11w; jumptable 000000014001E30E case 3
0x14001e31e  mov     [rcx-1], r11b; jumptable 000000014001E30E case 1
0x14001e322  retn; jumptable 000000014001E30E case 0
0x14001e323  mov     [rcx-0Eh], r11; jumptable 000000014001E30E case 14
0x14001e327  mov     [rcx-6], r11d; jumptable 000000014001E30E case 6
0x14001e32b  mov     [rcx-2], r11w; jumptable 000000014001E30E case 2
0x14001e330  retn
0x14001e340  mov     [rcx-0Dh], r11; jumptable 000000014001E30E case 13
0x14001e344  mov     [rcx-5], r11d; jumptable 000000014001E30E case 5
0x14001e348  mov     [rcx-1], r11b
0x14001e34c  retn
0x14001e350  mov     [rcx-0Ch], r11; jumptable 000000014001E30E case 12
0x14001e354  mov     [rcx-4], r11d; jumptable 000000014001E30E case 4
0x14001e358  retn
0x14001e359  mov     [rcx-0Bh], r11; jumptable 000000014001E30E case 11
0x14001e35d  mov     [rcx-3], r11w
0x14001e362  mov     [rcx-1], r11b
0x14001e366  retn
0x14001e367  mov     [rcx-9], r11; jumptable 000000014001E30E case 9
0x14001e36b  mov     [rcx-1], r11b
0x14001e36f  retn
0x14001e370  mov     [rcx-0Ah], r11; jumptable 000000014001E30E case 10
0x14001e374  mov     [rcx-2], r11w
0x14001e379  retn
0x14001e37a  mov     [rcx-8], r11; jumptable 000000014001E30E case 8
0x14001e37e  retn
0x14001e380  punpcklqdq xmm0, xmm0; jumptable 000000014001E30E default case
0x14001e384  cmp     r8, 20h ; ' '
0x14001e388  ja      short SetAbove32
0x14001e38a  movdqu  xmmword ptr [rcx], xmm0
0x14001e38e  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x14001e395  retn
0x14001e396  cmp     cs:dword_1400D68F0, 3
0x14001e39d  jb      NoAVX_0
0x14001e3a3  cmp     r8, cs:qword_1400D68F8
0x14001e3aa  jbe     short SetWithYMM
0x14001e3ac  cmp     r8, cs:qword_1400D6900
0x14001e3b3  ja      short SetWithYMM
0x14001e3b5  test    byte ptr cs:dword_1400D7800, 2
0x14001e3bc  jnz     memset_repstos
0x14001e3c2  vinsertf128 ymm0, ymm0, xmm0, 1
0x14001e3c8  mov     r9, rcx
0x14001e3cb  and     r9, 1Fh
0x14001e3cf  sub     r9, 20h ; ' '
0x14001e3d3  sub     rcx, r9
0x14001e3d6  sub     rdx, r9
0x14001e3d9  add     r8, r9
0x14001e3dc  cmp     r8, 100h
0x14001e3e3  jbe     short SetUpTo256WithYMM
0x14001e3e5  cmp     r8, cs:qword_1400D6900
0x14001e3ec  ja      YmmLoopNT_0
0x14001e3f2  nop     word ptr [rax+rax+00000000h]
0x14001e400  vmovdqa ymmword ptr [rcx], ymm0
0x14001e404  vmovdqa ymmword ptr [rcx+20h], ymm0
0x14001e409  vmovdqa ymmword ptr [rcx+40h], ymm0
0x14001e40e  vmovdqa ymmword ptr [rcx+60h], ymm0
0x14001e413  vmovdqa ymmword ptr [rcx+80h], ymm0
0x14001e41b  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x14001e423  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x14001e42b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x14001e433  add     rcx, 100h
0x14001e43a  sub     r8, 100h
0x14001e441  cmp     r8, 100h
0x14001e448  jnb     short YmmLoop_0
0x14001e44a  lea     r9, [r8+1Fh]
0x14001e44e  and     r9, 0FFFFFFFFFFFFFFE0h
0x14001e452  mov     r11, r9
0x14001e455  shr     r11, 5
0x14001e459  mov     r11d, ds:(jpt_14001E464 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001e461  add     r11, r10
0x14001e464  jmp     r11; switch jump
0x14001e467  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000014001E464 case 8
0x14001e471  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000014001E464 case 7
0x14001e47b  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000014001E464 case 6
0x14001e485  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000014001E464 case 5
0x14001e48f  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000014001E464 case 4
0x14001e496  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000014001E464 case 3
0x14001e49d  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000014001E464 case 2
0x14001e4a4  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000014001E464 case 1
0x14001e4ab  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001E464 case 0
0x14001e4af  vzeroupper
0x14001e4b2  retn
0x14001e4c0  vmovntdq ymmword ptr [rcx], ymm0
0x14001e4c4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x14001e4c9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x14001e4ce  vmovntdq ymmword ptr [rcx+60h], ymm0
0x14001e4d3  vmovntdq ymmword ptr [rcx+80h], ymm0
0x14001e4db  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x14001e4e3  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x14001e4eb  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x14001e4f3  add     rcx, 100h
0x14001e4fa  sub     r8, 100h
0x14001e501  cmp     r8, 100h
0x14001e508  jnb     short YmmLoopNT_0
0x14001e50a  lea     r9, [r8+1Fh]
0x14001e50e  and     r9, 0FFFFFFFFFFFFFFE0h
0x14001e512  mov     r11, r9
0x14001e515  shr     r11, 5
0x14001e519  mov     r11d, ds:(jpt_14001E524 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001e521  add     r11, r10
0x14001e524  jmp     r11; switch jump
0x14001e527  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 000000014001E524 case 8
0x14001e531  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 000000014001E524 case 7
0x14001e53b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 000000014001E524 case 6
0x14001e545  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 000000014001E524 case 5
0x14001e54f  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 000000014001E524 case 4
0x14001e556  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 000000014001E524 case 3
0x14001e55d  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 000000014001E524 case 2
0x14001e564  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 000000014001E524 case 1
0x14001e56b  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001E524 case 0
0x14001e56f  sfence
0x14001e572  vzeroupper
0x14001e575  retn
0x14001e580  cmp     r8, cs:qword_1400D68F8
0x14001e587  jbe     short SetWithXMM
0x14001e589  test    byte ptr cs:dword_1400D7800, 2
0x14001e590  jnz     memset_repstos
0x14001e596  mov     r9, rcx
0x14001e599  and     r9, 0Fh
0x14001e59d  sub     r9, 10h
0x14001e5a1  sub     rcx, r9
0x14001e5a4  sub     rdx, r9
0x14001e5a7  add     r8, r9
0x14001e5aa  cmp     r8, 80h
0x14001e5b1  jbe     short SetUpTo128WithXMM
0x14001e5b3  nop     word ptr [rax+rax+00000000h]
0x14001e5c0  movdqa  xmmword ptr [rcx], xmm0
0x14001e5c4  movdqa  xmmword ptr [rcx+10h], xmm0
0x14001e5c9  movdqa  xmmword ptr [rcx+20h], xmm0
0x14001e5ce  movdqa  xmmword ptr [rcx+30h], xmm0
0x14001e5d3  movdqa  xmmword ptr [rcx+40h], xmm0
0x14001e5d8  movdqa  xmmword ptr [rcx+50h], xmm0
0x14001e5dd  movdqa  xmmword ptr [rcx+60h], xmm0
0x14001e5e2  movdqa  xmmword ptr [rcx+70h], xmm0
0x14001e5e7  add     rcx, 80h
0x14001e5ee  sub     r8, 80h
0x14001e5f5  cmp     r8, 80h
0x14001e5fc  jnb     short XmmLoop_0
0x14001e5fe  lea     r9, [r8+0Fh]
0x14001e602  and     r9, 0FFFFFFFFFFFFFFF0h
0x14001e606  mov     r11, r9
0x14001e609  shr     r11, 4
0x14001e60d  mov     r11d, ds:(jpt_14001E618 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001e615  add     r11, r10
0x14001e618  jmp     r11; switch jump
0x14001e61b  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 000000014001E618 case 8
0x14001e622  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 000000014001E618 case 7
0x14001e629  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 000000014001E618 case 6
0x14001e630  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 000000014001E618 case 5
0x14001e637  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 000000014001E618 case 4
0x14001e63e  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 000000014001E618 case 3
0x14001e645  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 000000014001E618 case 2
0x14001e64c  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 000000014001E618 case 1
0x14001e653  movdqu  xmmword ptr [rax], xmm0; jumptable 000000014001E618 case 0
0x14001e657  retn
```
