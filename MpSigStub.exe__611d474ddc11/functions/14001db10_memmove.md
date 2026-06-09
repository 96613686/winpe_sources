# memmove

- ea: `0x14001db10`
- end: `0x14001e185`
- name: `memmove`
- size: `1653`
- prototype: `void *__cdecl(void *Dst, const void *Src, size_t MaxCount)`
- caller_count: `83`
- callee_count: `2`
- tags: ``

## callers

- `0x140007c98`
- `0x14000b098`
- `0x14000f2a4`
- `0x14000f348`
- `0x14001253c`
- `0x1400127f8`
- `0x1400165a0`
- `0x1400166b0`
- `0x1400191f8`
- `0x14001f290`
- `0x14001f490`
- `0x140022f68`
- `0x140023bc8`
- `0x1400251e8`
- `0x140026868`
- `0x1400320b4`
- `0x1400325b4`
- `0x140032724`
- `0x140032a0c`
- `0x140032aac`
- `0x140037108`
- `0x14003dce8`
- `0x140041198`
- `0x140041c60`
- `0x140043d0c`
- `0x140043ec0`
- `0x140044050`
- `0x14004418c`
- `0x1400443b8`
- `0x140044908`
- `0x140045d40`
- `0x140048e04`
- `0x140049a40`
- `0x14004a370`
- `0x14004ab84`
- `0x14004ad90`
- `0x14004aed0`
- `0x14004afc0`
- `0x14004b310`
- `0x14004b614`
- `0x14004b968`
- `0x14004bc68`
- `0x14004c310`
- `0x14004f5cc`
- `0x14004f794`
- `0x14004f9d8`
- `0x1400521a8`
- `0x140054390`
- `0x1400548cc`
- `0x140056460`

## callees

- `0x14001daf0`
- `0x14001db10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__cdecl memmove(void *Dst, const void *Src, size_t MaxCount)
{
  void *result; // rax
  int v4; // ecx
  __int16 v5; // r9
  char v6; // r10
  __int16 v7; // cx
  char v8; // r9
  __int16 v9; // r8
  char v10; // r9
  int v11; // ecx
  __int16 v12; // r9
  char v13; // r8
  int v14; // ecx
  char v15; // r9
  __int16 v16; // cx
  char v17; // cl
  int v18; // ecx
  __int16 v19; // r8
  char v20; // r8
  __m128i v21; // xmm2
  __int64 v24; // r9
  __m128i v57; // xmm0
  __m128i v58; // xmm5
  __int64 v59; // r9
  __m128i v60; // xmm2
  __m128i v61; // xmm3
  __m128i v62; // xmm4
  __m128i v63; // xmm2
  __m128i v64; // xmm3
  __m128i v65; // xmm4
  size_t v66; // r9
  char *v67; // r11
  _OWORD *v68; // r10
  signed __int64 v69; // rdx
  char *v70; // rcx
  __int128 v71; // xmm0
  unsigned __int64 v72; // rcx
  size_t v73; // r8
  _OWORD *v74; // rax
  __int128 v75; // xmm1
  size_t v76; // r9
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  size_t i; // r9

  result = Dst;
  switch ( MaxCount )
  {
    case 0uLL:
      return result;
    case 1uLL:
      *(_BYTE *)Dst = *(_BYTE *)Src;
      return result;
    case 2uLL:
      *(_WORD *)Dst = *(_WORD *)Src;
      return result;
    case 3uLL:
      v13 = *((_BYTE *)Src + 2);
      *(_WORD *)Dst = *(_WORD *)Src;
      *((_BYTE *)Dst + 2) = v13;
      return result;
    case 4uLL:
      *(_DWORD *)Dst = *(_DWORD *)Src;
      return result;
    case 5uLL:
      v20 = *((_BYTE *)Src + 4);
      *(_DWORD *)Dst = *(_DWORD *)Src;
      *((_BYTE *)Dst + 4) = v20;
      return result;
    case 6uLL:
      v19 = *((_WORD *)Src + 2);
      *(_DWORD *)Dst = *(_DWORD *)Src;
      *((_WORD *)Dst + 2) = v19;
      return result;
    case 7uLL:
      v9 = *((_WORD *)Src + 2);
      v10 = *((_BYTE *)Src + 6);
      *(_DWORD *)Dst = *(_DWORD *)Src;
      *((_WORD *)Dst + 2) = v9;
      *((_BYTE *)Dst + 6) = v10;
      return result;
    case 8uLL:
      *(_QWORD *)Dst = *(_QWORD *)Src;
      return result;
    case 9uLL:
      v17 = *((_BYTE *)Src + 8);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_BYTE *)result + 8) = v17;
      return result;
    case 0xAuLL:
      v16 = *((_WORD *)Src + 4);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v16;
      return result;
    case 0xBuLL:
      v7 = *((_WORD *)Src + 4);
      v8 = *((_BYTE *)Src + 10);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v7;
      *((_BYTE *)result + 10) = v8;
      return result;
    case 0xCuLL:
      v18 = *((_DWORD *)Src + 2);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v18;
      return result;
    case 0xDuLL:
      v14 = *((_DWORD *)Src + 2);
      v15 = *((_BYTE *)Src + 12);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v14;
      *((_BYTE *)result + 12) = v15;
      return result;
    case 0xEuLL:
      v11 = *((_DWORD *)Src + 2);
      v12 = *((_WORD *)Src + 6);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v11;
      *((_WORD *)result + 6) = v12;
      return result;
    case 0xFuLL:
      v4 = *((_DWORD *)Src + 2);
      v5 = *((_WORD *)Src + 6);
      v6 = *((_BYTE *)Src + 14);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v4;
      *((_WORD *)result + 6) = v5;
      *((_BYTE *)result + 14) = v6;
      return result;
    default:
      if ( MaxCount <= 0x20 )
      {
        v21 = _mm_loadu_si128((const __m128i *)((char *)Src + MaxCount - 16));
        *(__m128i *)Dst = _mm_loadu_si128((const __m128i *)Src);
        *(__m128i *)((char *)Dst + MaxCount - 16) = v21;
        return result;
      }
      if ( Src < Dst && Dst < (char *)Src + MaxCount )
      {
        v67 = (char *)Dst;
        v68 = Src;
        v69 = (_BYTE *)Src - (_BYTE *)Dst;
        v70 = (char *)Dst + MaxCount;
        v71 = *(_OWORD *)&v70[v69 - 16];
        v72 = (unsigned __int64)(v70 - 16);
        v73 = MaxCount - 16;
        if ( (v72 & 0xF) != 0 )
        {
          v74 = (_OWORD *)v72;
          v72 &= 0xFFFFFFFFFFFFFFF0uLL;
          v75 = v71;
          v71 = *(_OWORD *)(v72 + v69);
          *v74 = v75;
          v73 = v72 - (_QWORD)v67;
        }
        v76 = v73 >> 7;
        if ( v73 >> 7 )
        {
          for ( *(_OWORD *)v72 = v71; ; *(_OWORD *)v72 = v82 )
          {
            v77 = *(_OWORD *)(v72 + v69 - 16);
            v78 = *(_OWORD *)(v72 + v69 - 32);
            v72 -= 128LL;
            *(_OWORD *)(v72 + 112) = v77;
            *(_OWORD *)(v72 + 96) = v78;
            v79 = *(_OWORD *)(v72 + v69 + 64);
            --v76;
            *(_OWORD *)(v72 + 80) = *(_OWORD *)(v72 + v69 + 80);
            *(_OWORD *)(v72 + 64) = v79;
            v80 = *(_OWORD *)(v72 + v69 + 32);
            *(_OWORD *)(v72 + 48) = *(_OWORD *)(v72 + v69 + 48);
            *(_OWORD *)(v72 + 32) = v80;
            v81 = *(_OWORD *)(v72 + v69 + 16);
            v82 = *(_OWORD *)(v72 + v69);
            if ( !v76 )
              break;
            *(_OWORD *)(v72 + 16) = v81;
          }
          *(_OWORD *)(v72 + 16) = v81;
          v73 &= 0x7Fu;
          v71 = v82;
        }
        for ( i = v73 >> 4; i; --i )
        {
          *(_OWORD *)v72 = v71;
          v72 -= 16LL;
          v71 = *(_OWORD *)(v72 + v69);
        }
        if ( (v73 & 0xF) != 0 )
          *(_OWORD *)v67 = *v68;
        *(_OWORD *)v72 = v71;
        return v67;
      }
      if ( (unsigned int)dword_1400D68F0 < 3 )
      {
        if ( MaxCount <= 0x800 || (dword_1400D7800 & 2) == 0 )
        {
          v57 = _mm_loadu_si128((const __m128i *)Src);
          v58 = _mm_loadu_si128((const __m128i *)((char *)Src + MaxCount - 16));
          if ( MaxCount > 0x80 )
          {
            v59 = ((unsigned __int8)Dst & 0xF) - 16LL;
            Dst = (char *)Dst - v59;
            Src = (char *)Src - v59;
            MaxCount += v59;
            if ( MaxCount > 0x80 )
            {
              do
              {
                v60 = _mm_loadu_si128((const __m128i *)Src + 1);
                v61 = _mm_loadu_si128((const __m128i *)Src + 2);
                v62 = _mm_loadu_si128((const __m128i *)Src + 3);
                *(__m128i *)Dst = _mm_loadu_si128((const __m128i *)Src);
                *((__m128i *)Dst + 1) = v60;
                *((__m128i *)Dst + 2) = v61;
                *((__m128i *)Dst + 3) = v62;
                v63 = _mm_loadu_si128((const __m128i *)Src + 5);
                v64 = _mm_loadu_si128((const __m128i *)Src + 6);
                v65 = _mm_loadu_si128((const __m128i *)Src + 7);
                *((__m128i *)Dst + 4) = _mm_loadu_si128((const __m128i *)Src + 4);
                *((__m128i *)Dst + 5) = v63;
                *((__m128i *)Dst + 6) = v64;
                *((__m128i *)Dst + 7) = v65;
                Dst = (char *)Dst + 128;
                Src = (char *)Src + 128;
                MaxCount -= 128LL;
              }
              while ( MaxCount >= 0x80 );
            }
          }
          v66 = (MaxCount + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v66 >> 4 )
          {
            case 0uLL:
              goto Mov0XmmBlocks;
            case 1uLL:
              goto Mov1XmmBlocks;
            case 2uLL:
              goto Mov2XmmBlocks;
            case 3uLL:
              goto Mov3XmmBlocks;
            case 4uLL:
              goto Mov4XmmBlocks;
            case 5uLL:
              goto Mov5XmmBlocks;
            case 6uLL:
              goto Mov6XmmBlocks;
            case 7uLL:
              goto Mov7XmmBlocks;
            case 8uLL:
              *(__m128i *)((char *)Dst + v66 - 128) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 128));
Mov7XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 112) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 112));
Mov6XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 96) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 96));
Mov5XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 80) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 80));
Mov4XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 64) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 64));
Mov3XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 48) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 48));
Mov2XmmBlocks:
              *(__m128i *)((char *)Dst + v66 - 32) = _mm_loadu_si128((const __m128i *)((char *)Src + v66 - 32));
Mov1XmmBlocks:
              *(__m128i *)((char *)Dst + MaxCount - 16) = v58;
Mov0XmmBlocks:
              *(__m128i *)result = v57;
              break;
          }
          return result;
        }
        return (void *)memcpy_repmovs();
      }
      if ( MaxCount > 0x2000 && MaxCount <= 0x180000 && (dword_1400D7800 & 2) != 0 )
        return (void *)memcpy_repmovs();
      __asm
      {
        vmovdqu ymm0, ymmword ptr [rdx]
        vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
      }
      if ( MaxCount <= 0x100
        || (v24 = ((unsigned __int8)Dst & 0x1F) - 32LL,
            Dst = (char *)Dst - v24,
            Src = (char *)Src - v24,
            MaxCount += v24,
            MaxCount <= 0x100) )
      {
MovUpTo256WithYMM:
        _R9 = (MaxCount + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto Mov0YmmBlocks;
          case 1uLL:
            goto Mov1YmmBlocks;
          case 2uLL:
            goto Mov2YmmBlocks;
          case 3uLL:
            goto Mov3YmmBlocks;
          case 4uLL:
            goto Mov4YmmBlocks;
          case 5uLL:
            goto Mov5YmmBlocks;
          case 6uLL:
            goto Mov6YmmBlocks;
          case 7uLL:
            goto Mov7YmmBlocks;
          case 8uLL:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000014001DD82 case 8
              vmovdqu ymmword ptr [rcx+r9-100h], ymm1
            }
Mov7YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000014001DD82 case 7
              vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
            }
Mov6YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000014001DD82 case 6
              vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
            }
Mov5YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000014001DD82 case 5
              vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
            }
Mov4YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000014001DD82 case 4
              vmovdqu ymmword ptr [rcx+r9-80h], ymm1
            }
Mov3YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000014001DD82 case 3
              vmovdqu ymmword ptr [rcx+r9-60h], ymm1
            }
Mov2YmmBlocks:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000014001DD82 case 2
              vmovdqu ymmword ptr [rcx+r9-40h], ymm1
            }
Mov1YmmBlocks:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000014001DD82 case 1 }
Mov0YmmBlocks:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001DD82 case 0
              vzeroupper
            }
            break;
        }
        return result;
      }
      if ( MaxCount <= 0x180000 )
      {
        do
        {
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx]
            vmovdqu ymm2, ymmword ptr [rdx+20h]
            vmovdqu ymm3, ymmword ptr [rdx+40h]
            vmovdqu ymm4, ymmword ptr [rdx+60h]
            vmovdqa ymmword ptr [rcx], ymm1
            vmovdqa ymmword ptr [rcx+20h], ymm2
            vmovdqa ymmword ptr [rcx+40h], ymm3
            vmovdqa ymmword ptr [rcx+60h], ymm4
            vmovdqu ymm1, ymmword ptr [rdx+80h]
            vmovdqu ymm2, ymmword ptr [rdx+0A0h]
            vmovdqu ymm3, ymmword ptr [rdx+0C0h]
            vmovdqu ymm4, ymmword ptr [rdx+0E0h]
            vmovdqa ymmword ptr [rcx+80h], ymm1
            vmovdqa ymmword ptr [rcx+0A0h], ymm2
            vmovdqa ymmword ptr [rcx+0C0h], ymm3
            vmovdqa ymmword ptr [rcx+0E0h], ymm4
          }
          Dst = (char *)Dst + 256;
          Src = (char *)Src + 256;
          MaxCount -= 256LL;
        }
        while ( MaxCount >= 0x100 );
        goto MovUpTo256WithYMM;
      }
      do
      {
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx]
          vmovdqu ymm2, ymmword ptr [rdx+20h]
          vmovdqu ymm3, ymmword ptr [rdx+40h]
          vmovdqu ymm4, ymmword ptr [rdx+60h]
          vmovntdq ymmword ptr [rcx], ymm1
          vmovntdq ymmword ptr [rcx+20h], ymm2
          vmovntdq ymmword ptr [rcx+40h], ymm3
          vmovntdq ymmword ptr [rcx+60h], ymm4
          vmovdqu ymm1, ymmword ptr [rdx+80h]
          vmovdqu ymm2, ymmword ptr [rdx+0A0h]
          vmovdqu ymm3, ymmword ptr [rdx+0C0h]
          vmovdqu ymm4, ymmword ptr [rdx+0E0h]
          vmovntdq ymmword ptr [rcx+80h], ymm1
          vmovntdq ymmword ptr [rcx+0A0h], ymm2
          vmovntdq ymmword ptr [rcx+0C0h], ymm3
          vmovntdq ymmword ptr [rcx+0E0h], ymm4
        }
        Dst = (char *)Dst + 256;
        Src = (char *)Src + 256;
        MaxCount -= 256LL;
      }
      while ( MaxCount >= 0x100 );
      _R9 = (MaxCount + 31) & 0xFFFFFFFFFFFFFFE0uLL;
      switch ( _R9 >> 5 )
      {
        case 0uLL:
          goto Mov0YmmBlocksNT;
        case 1uLL:
          goto Mov1YmmBlocksNT;
        case 2uLL:
          goto Mov2YmmBlocksNT;
        case 3uLL:
          goto Mov3YmmBlocksNT;
        case 4uLL:
          goto Mov4YmmBlocksNT;
        case 5uLL:
          goto Mov5YmmBlocksNT;
        case 6uLL:
          goto Mov6YmmBlocksNT;
        case 7uLL:
          goto Mov7YmmBlocksNT;
        case 8uLL:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000014001DEB2 case 8
            vmovntdq ymmword ptr [rcx+r9-100h], ymm1
          }
Mov7YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000014001DEB2 case 7
            vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
          }
Mov6YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000014001DEB2 case 6
            vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
          }
Mov5YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000014001DEB2 case 5
            vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
          }
Mov4YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000014001DEB2 case 4
            vmovntdq ymmword ptr [rcx+r9-80h], ymm1
          }
Mov3YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000014001DEB2 case 3
            vmovntdq ymmword ptr [rcx+r9-60h], ymm1
          }
Mov2YmmBlocksNT:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000014001DEB2 case 2
            vmovntdq ymmword ptr [rcx+r9-40h], ymm1
          }
Mov1YmmBlocksNT:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000014001DEB2 case 1 }
Mov0YmmBlocksNT:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001DEB2 case 0 }
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
0x14001db10  mov     rax, rcx
0x14001db13  lea     r10, cs:140000000h
0x14001db1a  cmp     r8, 0Fh; switch 16 cases
0x14001db1e  ja      def_14001DB3B; jumptable 000000014001DB3B default case
0x14001db24  nop     word ptr [rax+rax+00000000h]
0x14001db30  mov     r9d, ds:(jpt_14001DB3B - 140000000h)[r10+r8*4]
0x14001db38  add     r9, r10
0x14001db3b  jmp     r9; switch jump
0x14001db3e  retn; jumptable 000000014001DB3B case 0
0x14001db40  mov     r8, [rdx]; jumptable 000000014001DB3B case 15
0x14001db43  mov     ecx, [rdx+8]
0x14001db46  movzx   r9d, word ptr [rdx+0Ch]
0x14001db4b  movzx   r10d, byte ptr [rdx+0Eh]
0x14001db50  mov     [rax], r8
0x14001db53  mov     [rax+8], ecx
0x14001db56  mov     [rax+0Ch], r9w
0x14001db5b  mov     [rax+0Eh], r10b
0x14001db5f  retn
0x14001db60  mov     r8, [rdx]; jumptable 000000014001DB3B case 11
0x14001db63  movzx   ecx, word ptr [rdx+8]
0x14001db67  movzx   r9d, byte ptr [rdx+0Ah]
0x14001db6c  mov     [rax], r8
0x14001db6f  mov     [rax+8], cx
0x14001db73  mov     [rax+0Ah], r9b
0x14001db77  retn
0x14001db78  movzx   ecx, word ptr [rdx]; jumptable 000000014001DB3B case 2
0x14001db7b  mov     [rax], cx
0x14001db7e  retn
0x14001db80  mov     ecx, [rdx]; jumptable 000000014001DB3B case 7
0x14001db82  movzx   r8d, word ptr [rdx+4]
0x14001db87  movzx   r9d, byte ptr [rdx+6]
0x14001db8c  mov     [rax], ecx
0x14001db8e  mov     [rax+4], r8w
0x14001db93  mov     [rax+6], r9b
0x14001db97  retn
0x14001db98  mov     r8, [rdx]; jumptable 000000014001DB3B case 14
0x14001db9b  mov     ecx, [rdx+8]
0x14001db9e  movzx   r9d, word ptr [rdx+0Ch]
0x14001dba3  mov     [rax], r8
0x14001dba6  mov     [rax+8], ecx
0x14001dba9  mov     [rax+0Ch], r9w
0x14001dbae  retn
0x14001dbaf  movzx   ecx, word ptr [rdx]; jumptable 000000014001DB3B case 3
0x14001dbb2  movzx   r8d, byte ptr [rdx+2]
0x14001dbb7  mov     [rax], cx
0x14001dbba  mov     [rax+2], r8b
0x14001dbbe  retn
0x14001dbc0  mov     r8, [rdx]; jumptable 000000014001DB3B case 13
0x14001dbc3  mov     ecx, [rdx+8]
0x14001dbc6  movzx   r9d, byte ptr [rdx+0Ch]
0x14001dbcb  mov     [rax], r8
0x14001dbce  mov     [rax+8], ecx
0x14001dbd1  mov     [rax+0Ch], r9b
0x14001dbd5  retn
0x14001dbd6  mov     r8, [rdx]; jumptable 000000014001DB3B case 10
0x14001dbd9  movzx   ecx, word ptr [rdx+8]
0x14001dbdd  mov     [rax], r8
0x14001dbe0  mov     [rax+8], cx
0x14001dbe4  retn
0x14001dbe5  mov     r8, [rdx]; jumptable 000000014001DB3B case 9
0x14001dbe8  movzx   ecx, byte ptr [rdx+8]
0x14001dbec  mov     [rax], r8
0x14001dbef  mov     [rax+8], cl
0x14001dbf2  retn
0x14001dbf3  mov     r8, [rdx]; jumptable 000000014001DB3B case 12
0x14001dbf6  mov     ecx, [rdx+8]
0x14001dbf9  mov     [rax], r8
0x14001dbfc  mov     [rax+8], ecx
0x14001dbff  retn
0x14001dc00  mov     ecx, [rdx]; jumptable 000000014001DB3B case 6
0x14001dc02  movzx   r8d, word ptr [rdx+4]
0x14001dc07  mov     [rax], ecx
0x14001dc09  mov     [rax+4], r8w
0x14001dc0e  retn
0x14001dc0f  mov     ecx, [rdx]; jumptable 000000014001DB3B case 5
0x14001dc11  movzx   r8d, byte ptr [rdx+4]
0x14001dc16  mov     [rax], ecx
0x14001dc18  mov     [rax+4], r8b
0x14001dc1c  retn
0x14001dc1d  mov     rcx, [rdx]; jumptable 000000014001DB3B case 8
0x14001dc20  mov     [rax], rcx
0x14001dc23  retn
0x14001dc24  movzx   ecx, byte ptr [rdx]; jumptable 000000014001DB3B case 1
0x14001dc27  mov     [rax], cl
0x14001dc29  retn
0x14001dc2a  mov     ecx, [rdx]; jumptable 000000014001DB3B case 4
0x14001dc2c  mov     [rax], ecx
0x14001dc2e  retn
0x14001dc30  cmp     r8, 20h ; ' '; jumptable 000000014001DB3B default case
0x14001dc34  ja      short MoveAbove32
0x14001dc36  movdqu  xmm1, xmmword ptr [rdx]
0x14001dc3a  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x14001dc41  movdqu  xmmword ptr [rcx], xmm1
0x14001dc45  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x14001dc4c  retn
0x14001dc4d  cmp     rdx, rcx
0x14001dc50  jnb     short CopyUp
0x14001dc52  lea     r9, [rdx+r8]
0x14001dc56  cmp     rcx, r9
0x14001dc59  jb      CopyDown
0x14001dc5f  nop
0x14001dc60  cmp     cs:dword_1400D68F0, 3
0x14001dc67  jb      NoAVX
0x14001dc6d  cmp     r8, 2000h
0x14001dc74  jbe     short MoveWithYMM
0x14001dc76  cmp     r8, 180000h
0x14001dc7d  ja      short MoveWithYMM
0x14001dc7f  test    byte ptr cs:dword_1400D7800, 2
0x14001dc86  jnz     memcpy_repmovs
0x14001dc8c  vmovdqu ymm0, ymmword ptr [rdx]
0x14001dc90  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x14001dc97  cmp     r8, 100h
0x14001dc9e  jbe     MovUpTo256WithYMM
0x14001dca4  mov     r9, rcx
0x14001dca7  and     r9, 1Fh
0x14001dcab  sub     r9, 20h ; ' '
0x14001dcaf  sub     rcx, r9
0x14001dcb2  sub     rdx, r9
0x14001dcb5  add     r8, r9
0x14001dcb8  cmp     r8, 100h
0x14001dcbf  jbe     MovUpTo256WithYMM
0x14001dcc5  cmp     r8, 180000h
0x14001dccc  ja      YmmLoopNT
0x14001dcd2  nop     word ptr [rax+rax+00000000h]
0x14001dce0  vmovdqu ymm1, ymmword ptr [rdx]
0x14001dce4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x14001dce9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x14001dcee  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x14001dcf3  vmovdqa ymmword ptr [rcx], ymm1
0x14001dcf7  vmovdqa ymmword ptr [rcx+20h], ymm2
0x14001dcfc  vmovdqa ymmword ptr [rcx+40h], ymm3
0x14001dd01  vmovdqa ymmword ptr [rcx+60h], ymm4
0x14001dd06  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x14001dd0e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x14001dd16  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x14001dd1e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x14001dd26  vmovdqa ymmword ptr [rcx+80h], ymm1
0x14001dd2e  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x14001dd36  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x14001dd3e  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x14001dd46  add     rcx, 100h
0x14001dd4d  add     rdx, 100h
0x14001dd54  sub     r8, 100h
0x14001dd5b  cmp     r8, 100h
0x14001dd62  jnb     YmmLoop
0x14001dd68  lea     r9, [r8+1Fh]
0x14001dd6c  and     r9, 0FFFFFFFFFFFFFFE0h
0x14001dd70  mov     r11, r9
0x14001dd73  shr     r11, 5
0x14001dd77  mov     r11d, ds:(jpt_14001DD82 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001dd7f  add     r11, r10
0x14001dd82  jmp     r11; switch jump
0x14001dd85  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000014001DD82 case 8
0x14001dd8f  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x14001dd99  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000014001DD82 case 7
0x14001dda3  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x14001ddad  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000014001DD82 case 6
0x14001ddb7  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x14001ddc1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000014001DD82 case 5
0x14001ddcb  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x14001ddd5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000014001DD82 case 4
0x14001dddc  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x14001dde3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000014001DD82 case 3
0x14001ddea  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x14001ddf1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000014001DD82 case 2
0x14001ddf8  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x14001ddff  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000014001DD82 case 1
0x14001de06  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001DD82 case 0
0x14001de0a  vzeroupper
0x14001de0d  retn
0x14001de10  vmovdqu ymm1, ymmword ptr [rdx]
0x14001de14  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x14001de19  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x14001de1e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x14001de23  vmovntdq ymmword ptr [rcx], ymm1
0x14001de27  vmovntdq ymmword ptr [rcx+20h], ymm2
0x14001de2c  vmovntdq ymmword ptr [rcx+40h], ymm3
0x14001de31  vmovntdq ymmword ptr [rcx+60h], ymm4
0x14001de36  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x14001de3e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x14001de46  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x14001de4e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x14001de56  vmovntdq ymmword ptr [rcx+80h], ymm1
0x14001de5e  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x14001de66  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x14001de6e  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x14001de76  add     rcx, 100h
0x14001de7d  add     rdx, 100h
0x14001de84  sub     r8, 100h
0x14001de8b  cmp     r8, 100h
0x14001de92  jnb     YmmLoopNT
0x14001de98  lea     r9, [r8+1Fh]
0x14001de9c  and     r9, 0FFFFFFFFFFFFFFE0h
0x14001dea0  mov     r11, r9
0x14001dea3  shr     r11, 5
0x14001dea7  mov     r11d, ds:(jpt_14001DEB2 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001deaf  add     r11, r10
0x14001deb2  jmp     r11; switch jump
0x14001deb5  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000014001DEB2 case 8
0x14001debf  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x14001dec9  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000014001DEB2 case 7
0x14001ded3  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x14001dedd  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000014001DEB2 case 6
0x14001dee7  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x14001def1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000014001DEB2 case 5
0x14001defb  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x14001df05  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000014001DEB2 case 4
0x14001df0c  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x14001df13  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000014001DEB2 case 3
0x14001df1a  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x14001df21  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000014001DEB2 case 2
0x14001df28  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x14001df2f  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000014001DEB2 case 1
0x14001df36  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000014001DEB2 case 0
0x14001df3a  sfence
0x14001df3d  vzeroupper
0x14001df40  retn
0x14001df50  cmp     r8, 800h
0x14001df57  jbe     short MoveWithXMM
0x14001df59  test    byte ptr cs:dword_1400D7800, 2
0x14001df60  jnz     memcpy_repmovs
0x14001df66  movdqu  xmm0, xmmword ptr [rdx]
0x14001df6a  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x14001df71  cmp     r8, 80h
0x14001df78  jbe     MovUpTo128WithXMM
0x14001df7e  mov     r9, rcx
0x14001df81  and     r9, 0Fh
0x14001df85  sub     r9, 10h
0x14001df89  sub     rcx, r9
0x14001df8c  sub     rdx, r9
0x14001df8f  add     r8, r9
0x14001df92  cmp     r8, 80h
0x14001df99  jbe     short MovUpTo128WithXMM
0x14001df9b  nop     dword ptr [rax+rax+00h]
0x14001dfa0  movdqu  xmm1, xmmword ptr [rdx]
0x14001dfa4  movdqu  xmm2, xmmword ptr [rdx+10h]
0x14001dfa9  movdqu  xmm3, xmmword ptr [rdx+20h]
0x14001dfae  movdqu  xmm4, xmmword ptr [rdx+30h]
0x14001dfb3  movdqa  xmmword ptr [rcx], xmm1
0x14001dfb7  movdqa  xmmword ptr [rcx+10h], xmm2
0x14001dfbc  movdqa  xmmword ptr [rcx+20h], xmm3
0x14001dfc1  movdqa  xmmword ptr [rcx+30h], xmm4
0x14001dfc6  movdqu  xmm1, xmmword ptr [rdx+40h]
0x14001dfcb  movdqu  xmm2, xmmword ptr [rdx+50h]
0x14001dfd0  movdqu  xmm3, xmmword ptr [rdx+60h]
0x14001dfd5  movdqu  xmm4, xmmword ptr [rdx+70h]
0x14001dfda  movdqa  xmmword ptr [rcx+40h], xmm1
0x14001dfdf  movdqa  xmmword ptr [rcx+50h], xmm2
0x14001dfe4  movdqa  xmmword ptr [rcx+60h], xmm3
0x14001dfe9  movdqa  xmmword ptr [rcx+70h], xmm4
0x14001dfee  add     rcx, 80h
0x14001dff5  add     rdx, 80h
0x14001dffc  sub     r8, 80h
0x14001e003  cmp     r8, 80h
0x14001e00a  jnb     short XmmLoop
0x14001e00c  lea     r9, [r8+0Fh]
0x14001e010  and     r9, 0FFFFFFFFFFFFFFF0h
0x14001e014  mov     r11, r9
0x14001e017  shr     r11, 4
0x14001e01b  mov     r11d, ds:(jpt_14001E026 - 140000000h)[r10+r11*4]; switch 9 cases
0x14001e023  add     r11, r10
0x14001e026  jmp     r11; switch jump
0x14001e029  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 000000014001E026 case 8
0x14001e030  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x14001e037  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 000000014001E026 case 7
0x14001e03e  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x14001e045  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 000000014001E026 case 6
0x14001e04c  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x14001e053  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 000000014001E026 case 5
0x14001e05a  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x14001e061  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 000000014001E026 case 4
0x14001e068  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x14001e06f  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 000000014001E026 case 3
0x14001e076  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x14001e07d  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 000000014001E026 case 2
0x14001e084  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x14001e08b  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 000000014001E026 case 1
0x14001e092  movdqu  xmmword ptr [rax], xmm0; jumptable 000000014001E026 case 0
0x14001e096  retn
0x14001e0a0  mov     r11, rcx
0x14001e0a3  mov     r10, rdx
0x14001e0a6  sub     rdx, rcx
0x14001e0a9  add     rcx, r8
0x14001e0ac  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14001e0b1  sub     rcx, 10h
0x14001e0b5  sub     r8, 10h
0x14001e0b9  test    cl, 0Fh
0x14001e0bc  jz      short XmmMovLargeTest
0x14001e0be  mov     rax, rcx
0x14001e0c1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001e0c5  movups  xmm1, xmm0
0x14001e0c8  movups  xmm0, xmmword ptr [rcx+rdx]
0x14001e0cc  movups  xmmword ptr [rax], xmm1
0x14001e0cf  mov     r8, rcx
0x14001e0d2  sub     r8, r11
0x14001e0d5  mov     r9, r8
0x14001e0d8  shr     r9, 7
0x14001e0dc  jz      short XmmMovSmallTest
0x14001e0de  movaps  xmmword ptr [rcx], xmm0
0x14001e0e1  jmp     short XmmMovLargeInner
  ... truncated ...
```
