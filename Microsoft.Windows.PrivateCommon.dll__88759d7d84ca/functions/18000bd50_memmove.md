# memmove

- ea: `0x18000bd50`
- end: `0x18000c3dd`
- name: `memmove`
- size: `1677`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001530`
- `0x180002d00`
- `0x1800046d0`
- `0x180004b20`
- `0x1800064b0`
- `0x180006850`
- `0x180009218`

## callees

- `0x18000bd40`
- `0x18000bd50`

## pseudocode

```c
void *__cdecl memmove(void *_RCX, const void *Src, size_t Size)
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
  char *v22; // r9
  __int64 v25; // r9
  __m128i v58; // xmm0
  __m128i v59; // xmm5
  __int64 v60; // r9
  __m128i v61; // xmm2
  __m128i v62; // xmm3
  __m128i v63; // xmm4
  __m128i v64; // xmm2
  __m128i v65; // xmm3
  __m128i v66; // xmm4
  size_t v67; // r9
  __int128 v68; // xmm2
  signed __int64 v69; // rdx
  char *v70; // rcx
  __int128 v71; // xmm0
  unsigned __int64 v72; // rcx
  size_t v73; // r8
  _OWORD *v74; // r9
  __int128 v75; // xmm1
  size_t v76; // r9
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  size_t i; // r9

  result = _RCX;
  if ( Size <= 0xF )
  {
    switch ( Size & 0xF )
    {
      case 0uLL:
        return result;
      case 1uLL:
        *(_BYTE *)_RCX = *(_BYTE *)Src;
        break;
      case 2uLL:
        *(_WORD *)_RCX = *(_WORD *)Src;
        break;
      case 3uLL:
        v13 = *((_BYTE *)Src + 2);
        *(_WORD *)_RCX = *(_WORD *)Src;
        *((_BYTE *)_RCX + 2) = v13;
        break;
      case 4uLL:
        *(_DWORD *)_RCX = *(_DWORD *)Src;
        break;
      case 5uLL:
        v20 = *((_BYTE *)Src + 4);
        *(_DWORD *)_RCX = *(_DWORD *)Src;
        *((_BYTE *)_RCX + 4) = v20;
        break;
      case 6uLL:
        v19 = *((_WORD *)Src + 2);
        *(_DWORD *)_RCX = *(_DWORD *)Src;
        *((_WORD *)_RCX + 2) = v19;
        break;
      case 7uLL:
        v9 = *((_WORD *)Src + 2);
        v10 = *((_BYTE *)Src + 6);
        *(_DWORD *)_RCX = *(_DWORD *)Src;
        *((_WORD *)_RCX + 2) = v9;
        *((_BYTE *)_RCX + 6) = v10;
        break;
      case 8uLL:
        *(_QWORD *)_RCX = *(_QWORD *)Src;
        break;
      case 9uLL:
        v17 = *((_BYTE *)Src + 8);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_BYTE *)result + 8) = v17;
        break;
      case 0xAuLL:
        v16 = *((_WORD *)Src + 4);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_WORD *)result + 4) = v16;
        break;
      case 0xBuLL:
        v7 = *((_WORD *)Src + 4);
        v8 = *((_BYTE *)Src + 10);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_WORD *)result + 4) = v7;
        *((_BYTE *)result + 10) = v8;
        break;
      case 0xCuLL:
        v18 = *((_DWORD *)Src + 2);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_DWORD *)result + 2) = v18;
        break;
      case 0xDuLL:
        v14 = *((_DWORD *)Src + 2);
        v15 = *((_BYTE *)Src + 12);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_DWORD *)result + 2) = v14;
        *((_BYTE *)result + 12) = v15;
        break;
      case 0xEuLL:
        v11 = *((_DWORD *)Src + 2);
        v12 = *((_WORD *)Src + 6);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_DWORD *)result + 2) = v11;
        *((_WORD *)result + 6) = v12;
        break;
      case 0xFuLL:
        v4 = *((_DWORD *)Src + 2);
        v5 = *((_WORD *)Src + 6);
        v6 = *((_BYTE *)Src + 14);
        *(_QWORD *)result = *(_QWORD *)Src;
        *((_DWORD *)result + 2) = v4;
        *((_WORD *)result + 6) = v5;
        *((_BYTE *)result + 14) = v6;
        break;
    }
    return result;
  }
  if ( Size <= 0x20 )
  {
    v21 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
    *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
    *(__m128i *)((char *)_RCX + Size - 16) = v21;
    return result;
  }
  v22 = (char *)Src + Size;
  if ( _RCX <= Src )
    v22 = (char *)_RCX;
  if ( _RCX < v22 )
  {
    v68 = *(_OWORD *)Src;
    v69 = (_BYTE *)Src - (_BYTE *)_RCX;
    v70 = (char *)_RCX + Size;
    v71 = *(_OWORD *)&v70[v69 - 16];
    v72 = (unsigned __int64)(v70 - 16);
    v73 = Size - 16;
    if ( (v72 & 0xF) != 0 )
    {
      v74 = (_OWORD *)v72;
      v72 &= 0xFFFFFFFFFFFFFFF0uLL;
      v75 = v71;
      v71 = *(_OWORD *)(v72 + v69);
      *v74 = v75;
      v73 = v72 - (_QWORD)result;
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
      *(_OWORD *)result = v68;
    *(_OWORD *)v72 = v71;
    return result;
  }
  if ( (unsigned int)_isa_available < 3 )
  {
    if ( Size <= 0x800 || (_favor & 2) == 0 )
    {
      v58 = _mm_loadu_si128((const __m128i *)Src);
      v59 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
      if ( Size > 0x80 )
      {
        v60 = ((unsigned __int8)_RCX & 0xF) - 16LL;
        _RCX = (char *)_RCX - v60;
        Src = (char *)Src - v60;
        Size += v60;
        if ( Size > 0x80 )
        {
          do
          {
            v61 = _mm_loadu_si128((const __m128i *)Src + 1);
            v62 = _mm_loadu_si128((const __m128i *)Src + 2);
            v63 = _mm_loadu_si128((const __m128i *)Src + 3);
            *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
            *((__m128i *)_RCX + 1) = v61;
            *((__m128i *)_RCX + 2) = v62;
            *((__m128i *)_RCX + 3) = v63;
            v64 = _mm_loadu_si128((const __m128i *)Src + 5);
            v65 = _mm_loadu_si128((const __m128i *)Src + 6);
            v66 = _mm_loadu_si128((const __m128i *)Src + 7);
            *((__m128i *)_RCX + 4) = _mm_loadu_si128((const __m128i *)Src + 4);
            *((__m128i *)_RCX + 5) = v64;
            *((__m128i *)_RCX + 6) = v65;
            *((__m128i *)_RCX + 7) = v66;
            _RCX = (char *)_RCX + 128;
            Src = (char *)Src + 128;
            Size -= 128LL;
          }
          while ( Size >= 0x80 );
        }
      }
      v67 = (Size + 15) & 0xFFFFFFFFFFFFFFF0uLL;
      switch ( (unsigned __int8)v67 >> 4 )
      {
        case 0:
        case 9:
        case 10:
        case 11:
        case 12:
        case 13:
        case 14:
        case 15:
          goto LABEL_66;
        case 1:
          goto LABEL_65;
        case 2:
          goto LABEL_64;
        case 3:
          goto LABEL_63;
        case 4:
          goto LABEL_62;
        case 5:
          goto LABEL_61;
        case 6:
          goto LABEL_60;
        case 7:
          goto LABEL_59;
        case 8:
          *(__m128i *)((char *)_RCX + v67 - 128) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 128));
LABEL_59:
          *(__m128i *)((char *)_RCX + v67 - 112) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 112));
LABEL_60:
          *(__m128i *)((char *)_RCX + v67 - 96) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 96));
LABEL_61:
          *(__m128i *)((char *)_RCX + v67 - 80) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 80));
LABEL_62:
          *(__m128i *)((char *)_RCX + v67 - 64) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 64));
LABEL_63:
          *(__m128i *)((char *)_RCX + v67 - 48) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 48));
LABEL_64:
          *(__m128i *)((char *)_RCX + v67 - 32) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 32));
LABEL_65:
          *(__m128i *)((char *)_RCX + Size - 16) = v59;
LABEL_66:
          *(__m128i *)result = v58;
          break;
      }
      return result;
    }
    return (void *)memcpy_repmovs();
  }
  if ( Size > 0x2000 && Size <= 0x180000 && (_favor & 2) != 0 )
    return (void *)memcpy_repmovs();
  __asm
  {
    vmovdqu ymm0, ymmword ptr [rdx]
    vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
  }
  if ( Size <= 0x100 )
    goto LABEL_31;
  v25 = ((unsigned __int8)_RCX & 0x1F) - 32LL;
  _RCX = (char *)_RCX - v25;
  Src = (char *)Src - v25;
  Size += v25;
  if ( Size <= 0x100 )
    goto LABEL_31;
  if ( Size <= 0x180000 )
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
      _RCX = (char *)_RCX + 256;
      Src = (char *)Src + 256;
      Size -= 256LL;
    }
    while ( Size >= 0x100 );
LABEL_31:
    _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
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
        break;
      case 1uLL:
        goto LABEL_39;
      case 2uLL:
        goto LABEL_38;
      case 3uLL:
        goto LABEL_37;
      case 4uLL:
        goto LABEL_36;
      case 5uLL:
        goto LABEL_35;
      case 6uLL:
        goto LABEL_34;
      case 7uLL:
        goto LABEL_33;
      case 8uLL:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000BFD6 case 8
          vmovdqu ymmword ptr [rcx+r9-100h], ymm1
        }
LABEL_33:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000BFD6 case 7
          vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
        }
LABEL_34:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000BFD6 case 6
          vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
        }
LABEL_35:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000BFD6 case 5
          vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
        }
LABEL_36:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000BFD6 case 4
          vmovdqu ymmword ptr [rcx+r9-80h], ymm1
        }
LABEL_37:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000BFD6 case 3
          vmovdqu ymmword ptr [rcx+r9-60h], ymm1
        }
LABEL_38:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000BFD6 case 2
          vmovdqu ymmword ptr [rcx+r9-40h], ymm1
        }
LABEL_39:
        __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000BFD6 case 1 }
        break;
    }
LABEL_40:
    __asm
    {
      vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BFD6 cases 0,9-15
      vzeroupper
    }
    return result;
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
    _RCX = (char *)_RCX + 256;
    Src = (char *)Src + 256;
    Size -= 256LL;
  }
  while ( Size >= 0x100 );
  _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
  switch ( (_R9 >> 5) & 0xF )
  {
    case 0uLL:
      goto LABEL_51;
    case 1uLL:
      goto LABEL_50;
    case 2uLL:
      goto LABEL_49;
    case 3uLL:
      goto LABEL_48;
    case 4uLL:
      goto LABEL_47;
    case 5uLL:
      goto LABEL_46;
    case 6uLL:
      goto LABEL_45;
    case 7uLL:
      goto LABEL_44;
    case 8uLL:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C116 case 8
        vmovntdq ymmword ptr [rcx+r9-100h], ymm1
      }
LABEL_44:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C116 case 7
        vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
      }
LABEL_45:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C116 case 6
        vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
      }
LABEL_46:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C116 case 5
        vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
      }
LABEL_47:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C116 case 4
        vmovntdq ymmword ptr [rcx+r9-80h], ymm1
      }
LABEL_48:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C116 case 3
        vmovntdq ymmword ptr [rcx+r9-60h], ymm1
      }
LABEL_49:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C116 case 2
        vmovntdq ymmword ptr [rcx+r9-40h], ymm1
      }
LABEL_50:
      __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C116 case 1 }
LABEL_51:
      __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C116 case 0 }
      _mm_sfence();
      __asm { vzeroupper }
      break;
    case 9uLL:
    case 0xAuLL:
    case 0xBuLL:
    case 0xCuLL:
    case 0xDuLL:
    case 0xEuLL:
    case 0xFuLL:
      goto LABEL_40;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd50  mov     rax, rcx
0x18000bd53  lea     r10, cs:180000000h
0x18000bd5a  cmp     r8, 0Fh
0x18000bd5e  ja      loc_18000BE80
0x18000bd64  nop     word ptr [rax+rax+00000000h]
0x18000bd70  and     r8, 0Fh; switch 16 cases
0x18000bd74  mov     r9d, ds:(jpt_18000BD7F - 180000000h)[r10+r8*4]
0x18000bd7c  add     r9, r10
0x18000bd7f  jmp     r9; switch jump
0x18000bd82  retn; jumptable 000000018000BD7F case 0
0x18000bd90  mov     r8, [rdx]; jumptable 000000018000BD7F case 15
0x18000bd93  mov     ecx, [rdx+8]
0x18000bd96  movzx   r9d, word ptr [rdx+0Ch]
0x18000bd9b  movzx   r10d, byte ptr [rdx+0Eh]
0x18000bda0  mov     [rax], r8
0x18000bda3  mov     [rax+8], ecx
0x18000bda6  mov     [rax+0Ch], r9w
0x18000bdab  mov     [rax+0Eh], r10b
0x18000bdaf  retn
0x18000bdb0  mov     r8, [rdx]; jumptable 000000018000BD7F case 11
0x18000bdb3  movzx   ecx, word ptr [rdx+8]
0x18000bdb7  movzx   r9d, byte ptr [rdx+0Ah]
0x18000bdbc  mov     [rax], r8
0x18000bdbf  mov     [rax+8], cx
0x18000bdc3  mov     [rax+0Ah], r9b
0x18000bdc7  retn
0x18000bdc8  movzx   ecx, word ptr [rdx]; jumptable 000000018000BD7F case 2
0x18000bdcb  mov     [rax], cx
0x18000bdce  retn
0x18000bdd0  mov     ecx, [rdx]; jumptable 000000018000BD7F case 7
0x18000bdd2  movzx   r8d, word ptr [rdx+4]
0x18000bdd7  movzx   r9d, byte ptr [rdx+6]
0x18000bddc  mov     [rax], ecx
0x18000bdde  mov     [rax+4], r8w
0x18000bde3  mov     [rax+6], r9b
0x18000bde7  retn
0x18000bde8  mov     r8, [rdx]; jumptable 000000018000BD7F case 14
0x18000bdeb  mov     ecx, [rdx+8]
0x18000bdee  movzx   r9d, word ptr [rdx+0Ch]
0x18000bdf3  mov     [rax], r8
0x18000bdf6  mov     [rax+8], ecx
0x18000bdf9  mov     [rax+0Ch], r9w
0x18000bdfe  retn
0x18000bdff  movzx   ecx, word ptr [rdx]; jumptable 000000018000BD7F case 3
0x18000be02  movzx   r8d, byte ptr [rdx+2]
0x18000be07  mov     [rax], cx
0x18000be0a  mov     [rax+2], r8b
0x18000be0e  retn
0x18000be10  mov     r8, [rdx]; jumptable 000000018000BD7F case 13
0x18000be13  mov     ecx, [rdx+8]
0x18000be16  movzx   r9d, byte ptr [rdx+0Ch]
0x18000be1b  mov     [rax], r8
0x18000be1e  mov     [rax+8], ecx
0x18000be21  mov     [rax+0Ch], r9b
0x18000be25  retn
0x18000be26  mov     r8, [rdx]; jumptable 000000018000BD7F case 10
0x18000be29  movzx   ecx, word ptr [rdx+8]
0x18000be2d  mov     [rax], r8
0x18000be30  mov     [rax+8], cx
0x18000be34  retn
0x18000be35  mov     r8, [rdx]; jumptable 000000018000BD7F case 9
0x18000be38  movzx   ecx, byte ptr [rdx+8]
0x18000be3c  mov     [rax], r8
0x18000be3f  mov     [rax+8], cl
0x18000be42  retn
0x18000be43  mov     r8, [rdx]; jumptable 000000018000BD7F case 12
0x18000be46  mov     ecx, [rdx+8]
0x18000be49  mov     [rax], r8
0x18000be4c  mov     [rax+8], ecx
0x18000be4f  retn
0x18000be50  mov     ecx, [rdx]; jumptable 000000018000BD7F case 6
0x18000be52  movzx   r8d, word ptr [rdx+4]
0x18000be57  mov     [rax], ecx
0x18000be59  mov     [rax+4], r8w
0x18000be5e  retn
0x18000be5f  mov     ecx, [rdx]; jumptable 000000018000BD7F case 5
0x18000be61  movzx   r8d, byte ptr [rdx+4]
0x18000be66  mov     [rax], ecx
0x18000be68  mov     [rax+4], r8b
0x18000be6c  retn
0x18000be6d  mov     rcx, [rdx]; jumptable 000000018000BD7F case 8
0x18000be70  mov     [rax], rcx
0x18000be73  retn
0x18000be74  movzx   ecx, byte ptr [rdx]; jumptable 000000018000BD7F case 1
0x18000be77  mov     [rax], cl
0x18000be79  retn
0x18000be7a  mov     ecx, [rdx]; jumptable 000000018000BD7F case 4
0x18000be7c  mov     [rax], ecx
0x18000be7e  retn
0x18000be80  cmp     r8, 20h ; ' '
0x18000be84  ja      short loc_18000BE9D
0x18000be86  movdqu  xmm1, xmmword ptr [rdx]
0x18000be8a  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x18000be91  movdqu  xmmword ptr [rcx], xmm1
0x18000be95  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x18000be9c  retn
0x18000be9d  lea     r9, [rdx+r8]
0x18000bea1  cmp     rcx, rdx
0x18000bea4  cmovbe  r9, rcx
0x18000bea8  cmp     rcx, r9
0x18000beab  jb      loc_18000C300
0x18000beb1  cmp     cs:__isa_available, 3
0x18000beb8  jb      loc_18000C1B0
0x18000bebe  cmp     r8, 2000h
0x18000bec5  jbe     short loc_18000BEDD
0x18000bec7  cmp     r8, 180000h
0x18000bece  ja      short loc_18000BEDD
0x18000bed0  test    byte ptr cs:__favor, 2
0x18000bed7  jnz     memcpy_repmovs
0x18000bedd  vmovdqu ymm0, ymmword ptr [rdx]
0x18000bee1  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x18000bee8  cmp     r8, 100h
0x18000beef  jbe     loc_18000BFB8
0x18000bef5  mov     r9, rcx
0x18000bef8  and     r9, 1Fh
0x18000befc  sub     r9, 20h ; ' '
0x18000bf00  sub     rcx, r9
0x18000bf03  sub     rdx, r9
0x18000bf06  add     r8, r9
0x18000bf09  cmp     r8, 100h
0x18000bf10  jbe     loc_18000BFB8
0x18000bf16  cmp     r8, 180000h
0x18000bf1d  ja      loc_18000C070
0x18000bf23  nop     word ptr [rax+rax+00000000h]
0x18000bf30  vmovdqu ymm1, ymmword ptr [rdx]
0x18000bf34  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000bf39  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000bf3e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000bf43  vmovdqa ymmword ptr [rcx], ymm1
0x18000bf47  vmovdqa ymmword ptr [rcx+20h], ymm2
0x18000bf4c  vmovdqa ymmword ptr [rcx+40h], ymm3
0x18000bf51  vmovdqa ymmword ptr [rcx+60h], ymm4
0x18000bf56  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000bf5e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000bf66  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000bf6e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000bf76  vmovdqa ymmword ptr [rcx+80h], ymm1
0x18000bf7e  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x18000bf86  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x18000bf8e  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x18000bf96  add     rcx, 100h
0x18000bf9d  add     rdx, 100h
0x18000bfa4  sub     r8, 100h
0x18000bfab  cmp     r8, 100h
0x18000bfb2  jnb     loc_18000BF30
0x18000bfb8  lea     r9, [r8+1Fh]
0x18000bfbc  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000bfc0  mov     r11, r9
0x18000bfc3  shr     r11, 5
0x18000bfc7  and     r11, 0Fh; switch 16 cases
0x18000bfcb  mov     r11d, ds:(jpt_18000BFD6 - 180000000h)[r10+r11*4]
0x18000bfd3  add     r11, r10
0x18000bfd6  jmp     r11; switch jump
0x18000bfd9  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000BFD6 case 8
0x18000bfe3  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x18000bfed  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000BFD6 case 7
0x18000bff7  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18000c001  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000BFD6 case 6
0x18000c00b  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x18000c015  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000BFD6 case 5
0x18000c01f  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x18000c029  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000BFD6 case 4
0x18000c030  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x18000c037  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000BFD6 case 3
0x18000c03e  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x18000c045  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000BFD6 case 2
0x18000c04c  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x18000c053  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000BFD6 case 1
0x18000c05a  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BFD6 cases 0,9-15
0x18000c05e  vzeroupper
0x18000c061  retn
0x18000c070  vmovdqu ymm1, ymmword ptr [rdx]
0x18000c074  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000c079  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000c07e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000c083  vmovntdq ymmword ptr [rcx], ymm1
0x18000c087  vmovntdq ymmword ptr [rcx+20h], ymm2
0x18000c08c  vmovntdq ymmword ptr [rcx+40h], ymm3
0x18000c091  vmovntdq ymmword ptr [rcx+60h], ymm4
0x18000c096  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000c09e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000c0a6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000c0ae  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000c0b6  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18000c0be  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x18000c0c6  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18000c0ce  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x18000c0d6  add     rcx, 100h
0x18000c0dd  add     rdx, 100h
0x18000c0e4  sub     r8, 100h
0x18000c0eb  cmp     r8, 100h
0x18000c0f2  jnb     loc_18000C070
0x18000c0f8  lea     r9, [r8+1Fh]
0x18000c0fc  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000c100  mov     r11, r9
0x18000c103  shr     r11, 5
0x18000c107  and     r11, 0Fh; switch 16 cases
0x18000c10b  mov     r11d, ds:(jpt_18000C116 - 180000000h)[r10+r11*4]
0x18000c113  add     r11, r10
0x18000c116  jmp     r11; switch jump
0x18000c119  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C116 case 8
0x18000c123  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x18000c12d  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C116 case 7
0x18000c137  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x18000c141  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C116 case 6
0x18000c14b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x18000c155  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C116 case 5
0x18000c15f  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x18000c169  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C116 case 4
0x18000c170  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x18000c177  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C116 case 3
0x18000c17e  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x18000c185  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C116 case 2
0x18000c18c  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x18000c193  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C116 case 1
0x18000c19a  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C116 case 0
0x18000c19e  sfence
0x18000c1a1  vzeroupper
0x18000c1a4  retn
0x18000c1b0  cmp     r8, 800h
0x18000c1b7  jbe     short loc_18000C1C6
0x18000c1b9  test    byte ptr cs:__favor, 2
0x18000c1c0  jnz     memcpy_repmovs
0x18000c1c6  movdqu  xmm0, xmmword ptr [rdx]
0x18000c1ca  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x18000c1d1  cmp     r8, 80h
0x18000c1d8  jbe     loc_18000C26C
0x18000c1de  mov     r9, rcx
0x18000c1e1  and     r9, 0Fh
0x18000c1e5  sub     r9, 10h
0x18000c1e9  sub     rcx, r9
0x18000c1ec  sub     rdx, r9
0x18000c1ef  add     r8, r9
0x18000c1f2  cmp     r8, 80h
0x18000c1f9  jbe     short loc_18000C26C
0x18000c1fb  nop     dword ptr [rax+rax+00h]
0x18000c200  movdqu  xmm1, xmmword ptr [rdx]
0x18000c204  movdqu  xmm2, xmmword ptr [rdx+10h]
0x18000c209  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18000c20e  movdqu  xmm4, xmmword ptr [rdx+30h]
0x18000c213  movdqa  xmmword ptr [rcx], xmm1
0x18000c217  movdqa  xmmword ptr [rcx+10h], xmm2
0x18000c21c  movdqa  xmmword ptr [rcx+20h], xmm3
0x18000c221  movdqa  xmmword ptr [rcx+30h], xmm4
0x18000c226  movdqu  xmm1, xmmword ptr [rdx+40h]
0x18000c22b  movdqu  xmm2, xmmword ptr [rdx+50h]
0x18000c230  movdqu  xmm3, xmmword ptr [rdx+60h]
0x18000c235  movdqu  xmm4, xmmword ptr [rdx+70h]
0x18000c23a  movdqa  xmmword ptr [rcx+40h], xmm1
0x18000c23f  movdqa  xmmword ptr [rcx+50h], xmm2
0x18000c244  movdqa  xmmword ptr [rcx+60h], xmm3
0x18000c249  movdqa  xmmword ptr [rcx+70h], xmm4
0x18000c24e  add     rcx, 80h
0x18000c255  add     rdx, 80h
0x18000c25c  sub     r8, 80h
0x18000c263  cmp     r8, 80h
0x18000c26a  jnb     short loc_18000C200
0x18000c26c  lea     r9, [r8+0Fh]
0x18000c270  and     r9, 0FFFFFFFFFFFFFFF0h
0x18000c274  mov     r11, r9
0x18000c277  shr     r11, 4
0x18000c27b  and     r11, 0Fh; switch 16 cases
0x18000c27f  mov     r11d, ds:(jpt_18000C28A - 180000000h)[r10+r11*4]
0x18000c287  add     r11, r10
0x18000c28a  jmp     r11; switch jump
0x18000c28d  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 000000018000C28A case 8
0x18000c294  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x18000c29b  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 000000018000C28A case 7
0x18000c2a2  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x18000c2a9  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 000000018000C28A case 6
0x18000c2b0  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x18000c2b7  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 000000018000C28A case 5
0x18000c2be  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x18000c2c5  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 000000018000C28A case 4
0x18000c2cc  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18000c2d3  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 000000018000C28A case 3
0x18000c2da  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18000c2e1  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 000000018000C28A case 2
0x18000c2e8  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18000c2ef  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 000000018000C28A case 1
0x18000c2f6  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018000C28A cases 0,9-15
0x18000c2fa  retn
0x18000c300  movups  xmm2, xmmword ptr [rdx]
0x18000c303  sub     rdx, rcx
0x18000c306  add     rcx, r8
0x18000c309  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18000c30e  sub     rcx, 10h
0x18000c312  sub     r8, 10h
0x18000c316  test    cl, 0Fh
0x18000c319  jz      short loc_18000C333
0x18000c31b  mov     r9, rcx
0x18000c31e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c322  movups  xmm1, xmm0
0x18000c325  movups  xmm0, xmmword ptr [rcx+rdx]
0x18000c329  movups  xmmword ptr [r9], xmm1
0x18000c32d  mov     r8, rcx
0x18000c330  sub     r8, rax
0x18000c333  mov     r9, r8
0x18000c336  shr     r9, 7
0x18000c33a  jz      short loc_18000C3AD
  ... truncated ...
```
