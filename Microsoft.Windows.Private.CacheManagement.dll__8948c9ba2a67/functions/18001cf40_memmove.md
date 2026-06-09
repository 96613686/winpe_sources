# memmove

- ea: `0x18001cf40`
- end: `0x18001d5cd`
- name: `memmove`
- size: `1677`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025d0`
- `0x180003c60`
- `0x1800043f0`
- `0x1800086c0`
- `0x180009cc0`
- `0x18000c0b0`
- `0x18000d8d0`
- `0x18000dac0`
- `0x18000de80`
- `0x18000fc60`
- `0x180011ce0`
- `0x1800127e0`
- `0x180012f10`
- `0x180012fc0`
- `0x180013150`
- `0x180013ff0`
- `0x180014bf0`
- `0x180015040`
- `0x180016718`
- `0x180016850`
- `0x180016974`
- `0x180016b90`
- `0x180017138`
- `0x180017788`
- `0x18001794c`
- `0x180017abc`
- `0x18001a258`
- `0x18001f209`

## callees

- `0x18001cf30`
- `0x18001cf40`

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
          vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018001D1C6 case 8
          vmovdqu ymmword ptr [rcx+r9-100h], ymm1
        }
LABEL_33:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018001D1C6 case 7
          vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
        }
LABEL_34:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018001D1C6 case 6
          vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
        }
LABEL_35:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018001D1C6 case 5
          vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
        }
LABEL_36:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018001D1C6 case 4
          vmovdqu ymmword ptr [rcx+r9-80h], ymm1
        }
LABEL_37:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018001D1C6 case 3
          vmovdqu ymmword ptr [rcx+r9-60h], ymm1
        }
LABEL_38:
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018001D1C6 case 2
          vmovdqu ymmword ptr [rcx+r9-40h], ymm1
        }
LABEL_39:
        __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018001D1C6 case 1 }
        break;
    }
LABEL_40:
    __asm
    {
      vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018001D1C6 cases 0,9-15
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
        vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018001D306 case 8
        vmovntdq ymmword ptr [rcx+r9-100h], ymm1
      }
LABEL_44:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018001D306 case 7
        vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
      }
LABEL_45:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018001D306 case 6
        vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
      }
LABEL_46:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018001D306 case 5
        vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
      }
LABEL_47:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018001D306 case 4
        vmovntdq ymmword ptr [rcx+r9-80h], ymm1
      }
LABEL_48:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018001D306 case 3
        vmovntdq ymmword ptr [rcx+r9-60h], ymm1
      }
LABEL_49:
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018001D306 case 2
        vmovntdq ymmword ptr [rcx+r9-40h], ymm1
      }
LABEL_50:
      __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018001D306 case 1 }
LABEL_51:
      __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018001D306 case 0 }
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
0x18001cf40  mov     rax, rcx
0x18001cf43  lea     r10, cs:180000000h
0x18001cf4a  cmp     r8, 0Fh
0x18001cf4e  ja      loc_18001D070
0x18001cf54  nop     word ptr [rax+rax+00000000h]
0x18001cf60  and     r8, 0Fh; switch 16 cases
0x18001cf64  mov     r9d, ds:(jpt_18001CF6F - 180000000h)[r10+r8*4]
0x18001cf6c  add     r9, r10
0x18001cf6f  jmp     r9; switch jump
0x18001cf72  retn; jumptable 000000018001CF6F case 0
0x18001cf80  mov     r8, [rdx]; jumptable 000000018001CF6F case 15
0x18001cf83  mov     ecx, [rdx+8]
0x18001cf86  movzx   r9d, word ptr [rdx+0Ch]
0x18001cf8b  movzx   r10d, byte ptr [rdx+0Eh]
0x18001cf90  mov     [rax], r8
0x18001cf93  mov     [rax+8], ecx
0x18001cf96  mov     [rax+0Ch], r9w
0x18001cf9b  mov     [rax+0Eh], r10b
0x18001cf9f  retn
0x18001cfa0  mov     r8, [rdx]; jumptable 000000018001CF6F case 11
0x18001cfa3  movzx   ecx, word ptr [rdx+8]
0x18001cfa7  movzx   r9d, byte ptr [rdx+0Ah]
0x18001cfac  mov     [rax], r8
0x18001cfaf  mov     [rax+8], cx
0x18001cfb3  mov     [rax+0Ah], r9b
0x18001cfb7  retn
0x18001cfb8  movzx   ecx, word ptr [rdx]; jumptable 000000018001CF6F case 2
0x18001cfbb  mov     [rax], cx
0x18001cfbe  retn
0x18001cfc0  mov     ecx, [rdx]; jumptable 000000018001CF6F case 7
0x18001cfc2  movzx   r8d, word ptr [rdx+4]
0x18001cfc7  movzx   r9d, byte ptr [rdx+6]
0x18001cfcc  mov     [rax], ecx
0x18001cfce  mov     [rax+4], r8w
0x18001cfd3  mov     [rax+6], r9b
0x18001cfd7  retn
0x18001cfd8  mov     r8, [rdx]; jumptable 000000018001CF6F case 14
0x18001cfdb  mov     ecx, [rdx+8]
0x18001cfde  movzx   r9d, word ptr [rdx+0Ch]
0x18001cfe3  mov     [rax], r8
0x18001cfe6  mov     [rax+8], ecx
0x18001cfe9  mov     [rax+0Ch], r9w
0x18001cfee  retn
0x18001cfef  movzx   ecx, word ptr [rdx]; jumptable 000000018001CF6F case 3
0x18001cff2  movzx   r8d, byte ptr [rdx+2]
0x18001cff7  mov     [rax], cx
0x18001cffa  mov     [rax+2], r8b
0x18001cffe  retn
0x18001d000  mov     r8, [rdx]; jumptable 000000018001CF6F case 13
0x18001d003  mov     ecx, [rdx+8]
0x18001d006  movzx   r9d, byte ptr [rdx+0Ch]
0x18001d00b  mov     [rax], r8
0x18001d00e  mov     [rax+8], ecx
0x18001d011  mov     [rax+0Ch], r9b
0x18001d015  retn
0x18001d016  mov     r8, [rdx]; jumptable 000000018001CF6F case 10
0x18001d019  movzx   ecx, word ptr [rdx+8]
0x18001d01d  mov     [rax], r8
0x18001d020  mov     [rax+8], cx
0x18001d024  retn
0x18001d025  mov     r8, [rdx]; jumptable 000000018001CF6F case 9
0x18001d028  movzx   ecx, byte ptr [rdx+8]
0x18001d02c  mov     [rax], r8
0x18001d02f  mov     [rax+8], cl
0x18001d032  retn
0x18001d033  mov     r8, [rdx]; jumptable 000000018001CF6F case 12
0x18001d036  mov     ecx, [rdx+8]
0x18001d039  mov     [rax], r8
0x18001d03c  mov     [rax+8], ecx
0x18001d03f  retn
0x18001d040  mov     ecx, [rdx]; jumptable 000000018001CF6F case 6
0x18001d042  movzx   r8d, word ptr [rdx+4]
0x18001d047  mov     [rax], ecx
0x18001d049  mov     [rax+4], r8w
0x18001d04e  retn
0x18001d04f  mov     ecx, [rdx]; jumptable 000000018001CF6F case 5
0x18001d051  movzx   r8d, byte ptr [rdx+4]
0x18001d056  mov     [rax], ecx
0x18001d058  mov     [rax+4], r8b
0x18001d05c  retn
0x18001d05d  mov     rcx, [rdx]; jumptable 000000018001CF6F case 8
0x18001d060  mov     [rax], rcx
0x18001d063  retn
0x18001d064  movzx   ecx, byte ptr [rdx]; jumptable 000000018001CF6F case 1
0x18001d067  mov     [rax], cl
0x18001d069  retn
0x18001d06a  mov     ecx, [rdx]; jumptable 000000018001CF6F case 4
0x18001d06c  mov     [rax], ecx
0x18001d06e  retn
0x18001d070  cmp     r8, 20h ; ' '
0x18001d074  ja      short loc_18001D08D
0x18001d076  movdqu  xmm1, xmmword ptr [rdx]
0x18001d07a  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x18001d081  movdqu  xmmword ptr [rcx], xmm1
0x18001d085  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x18001d08c  retn
0x18001d08d  lea     r9, [rdx+r8]
0x18001d091  cmp     rcx, rdx
0x18001d094  cmovbe  r9, rcx
0x18001d098  cmp     rcx, r9
0x18001d09b  jb      loc_18001D4F0
0x18001d0a1  cmp     cs:__isa_available, 3
0x18001d0a8  jb      loc_18001D3A0
0x18001d0ae  cmp     r8, 2000h
0x18001d0b5  jbe     short loc_18001D0CD
0x18001d0b7  cmp     r8, 180000h
0x18001d0be  ja      short loc_18001D0CD
0x18001d0c0  test    byte ptr cs:__favor, 2
0x18001d0c7  jnz     memcpy_repmovs
0x18001d0cd  vmovdqu ymm0, ymmword ptr [rdx]
0x18001d0d1  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x18001d0d8  cmp     r8, 100h
0x18001d0df  jbe     loc_18001D1A8
0x18001d0e5  mov     r9, rcx
0x18001d0e8  and     r9, 1Fh
0x18001d0ec  sub     r9, 20h ; ' '
0x18001d0f0  sub     rcx, r9
0x18001d0f3  sub     rdx, r9
0x18001d0f6  add     r8, r9
0x18001d0f9  cmp     r8, 100h
0x18001d100  jbe     loc_18001D1A8
0x18001d106  cmp     r8, 180000h
0x18001d10d  ja      loc_18001D260
0x18001d113  nop     word ptr [rax+rax+00000000h]
0x18001d120  vmovdqu ymm1, ymmword ptr [rdx]
0x18001d124  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18001d129  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18001d12e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18001d133  vmovdqa ymmword ptr [rcx], ymm1
0x18001d137  vmovdqa ymmword ptr [rcx+20h], ymm2
0x18001d13c  vmovdqa ymmword ptr [rcx+40h], ymm3
0x18001d141  vmovdqa ymmword ptr [rcx+60h], ymm4
0x18001d146  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18001d14e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18001d156  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18001d15e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18001d166  vmovdqa ymmword ptr [rcx+80h], ymm1
0x18001d16e  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x18001d176  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x18001d17e  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x18001d186  add     rcx, 100h
0x18001d18d  add     rdx, 100h
0x18001d194  sub     r8, 100h
0x18001d19b  cmp     r8, 100h
0x18001d1a2  jnb     loc_18001D120
0x18001d1a8  lea     r9, [r8+1Fh]
0x18001d1ac  and     r9, 0FFFFFFFFFFFFFFE0h
0x18001d1b0  mov     r11, r9
0x18001d1b3  shr     r11, 5
0x18001d1b7  and     r11, 0Fh; switch 16 cases
0x18001d1bb  mov     r11d, ds:(jpt_18001D1C6 - 180000000h)[r10+r11*4]
0x18001d1c3  add     r11, r10
0x18001d1c6  jmp     r11; switch jump
0x18001d1c9  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018001D1C6 case 8
0x18001d1d3  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x18001d1dd  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018001D1C6 case 7
0x18001d1e7  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18001d1f1  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018001D1C6 case 6
0x18001d1fb  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x18001d205  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018001D1C6 case 5
0x18001d20f  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x18001d219  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018001D1C6 case 4
0x18001d220  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x18001d227  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018001D1C6 case 3
0x18001d22e  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x18001d235  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018001D1C6 case 2
0x18001d23c  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x18001d243  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018001D1C6 case 1
0x18001d24a  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018001D1C6 cases 0,9-15
0x18001d24e  vzeroupper
0x18001d251  retn
0x18001d260  vmovdqu ymm1, ymmword ptr [rdx]
0x18001d264  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18001d269  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18001d26e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18001d273  vmovntdq ymmword ptr [rcx], ymm1
0x18001d277  vmovntdq ymmword ptr [rcx+20h], ymm2
0x18001d27c  vmovntdq ymmword ptr [rcx+40h], ymm3
0x18001d281  vmovntdq ymmword ptr [rcx+60h], ymm4
0x18001d286  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18001d28e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18001d296  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18001d29e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18001d2a6  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18001d2ae  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x18001d2b6  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18001d2be  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x18001d2c6  add     rcx, 100h
0x18001d2cd  add     rdx, 100h
0x18001d2d4  sub     r8, 100h
0x18001d2db  cmp     r8, 100h
0x18001d2e2  jnb     loc_18001D260
0x18001d2e8  lea     r9, [r8+1Fh]
0x18001d2ec  and     r9, 0FFFFFFFFFFFFFFE0h
0x18001d2f0  mov     r11, r9
0x18001d2f3  shr     r11, 5
0x18001d2f7  and     r11, 0Fh; switch 16 cases
0x18001d2fb  mov     r11d, ds:(jpt_18001D306 - 180000000h)[r10+r11*4]
0x18001d303  add     r11, r10
0x18001d306  jmp     r11; switch jump
0x18001d309  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018001D306 case 8
0x18001d313  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x18001d31d  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018001D306 case 7
0x18001d327  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x18001d331  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018001D306 case 6
0x18001d33b  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x18001d345  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018001D306 case 5
0x18001d34f  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x18001d359  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018001D306 case 4
0x18001d360  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x18001d367  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018001D306 case 3
0x18001d36e  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x18001d375  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018001D306 case 2
0x18001d37c  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x18001d383  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018001D306 case 1
0x18001d38a  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018001D306 case 0
0x18001d38e  sfence
0x18001d391  vzeroupper
0x18001d394  retn
0x18001d3a0  cmp     r8, 800h
0x18001d3a7  jbe     short loc_18001D3B6
0x18001d3a9  test    byte ptr cs:__favor, 2
0x18001d3b0  jnz     memcpy_repmovs
0x18001d3b6  movdqu  xmm0, xmmword ptr [rdx]
0x18001d3ba  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x18001d3c1  cmp     r8, 80h
0x18001d3c8  jbe     loc_18001D45C
0x18001d3ce  mov     r9, rcx
0x18001d3d1  and     r9, 0Fh
0x18001d3d5  sub     r9, 10h
0x18001d3d9  sub     rcx, r9
0x18001d3dc  sub     rdx, r9
0x18001d3df  add     r8, r9
0x18001d3e2  cmp     r8, 80h
0x18001d3e9  jbe     short loc_18001D45C
0x18001d3eb  nop     dword ptr [rax+rax+00h]
0x18001d3f0  movdqu  xmm1, xmmword ptr [rdx]
0x18001d3f4  movdqu  xmm2, xmmword ptr [rdx+10h]
0x18001d3f9  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18001d3fe  movdqu  xmm4, xmmword ptr [rdx+30h]
0x18001d403  movdqa  xmmword ptr [rcx], xmm1
0x18001d407  movdqa  xmmword ptr [rcx+10h], xmm2
0x18001d40c  movdqa  xmmword ptr [rcx+20h], xmm3
0x18001d411  movdqa  xmmword ptr [rcx+30h], xmm4
0x18001d416  movdqu  xmm1, xmmword ptr [rdx+40h]
0x18001d41b  movdqu  xmm2, xmmword ptr [rdx+50h]
0x18001d420  movdqu  xmm3, xmmword ptr [rdx+60h]
0x18001d425  movdqu  xmm4, xmmword ptr [rdx+70h]
0x18001d42a  movdqa  xmmword ptr [rcx+40h], xmm1
0x18001d42f  movdqa  xmmword ptr [rcx+50h], xmm2
0x18001d434  movdqa  xmmword ptr [rcx+60h], xmm3
0x18001d439  movdqa  xmmword ptr [rcx+70h], xmm4
0x18001d43e  add     rcx, 80h
0x18001d445  add     rdx, 80h
0x18001d44c  sub     r8, 80h
0x18001d453  cmp     r8, 80h
0x18001d45a  jnb     short loc_18001D3F0
0x18001d45c  lea     r9, [r8+0Fh]
0x18001d460  and     r9, 0FFFFFFFFFFFFFFF0h
0x18001d464  mov     r11, r9
0x18001d467  shr     r11, 4
0x18001d46b  and     r11, 0Fh; switch 16 cases
0x18001d46f  mov     r11d, ds:(jpt_18001D47A - 180000000h)[r10+r11*4]
0x18001d477  add     r11, r10
0x18001d47a  jmp     r11; switch jump
0x18001d47d  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 000000018001D47A case 8
0x18001d484  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x18001d48b  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 000000018001D47A case 7
0x18001d492  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x18001d499  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 000000018001D47A case 6
0x18001d4a0  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x18001d4a7  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 000000018001D47A case 5
0x18001d4ae  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x18001d4b5  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 000000018001D47A case 4
0x18001d4bc  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18001d4c3  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 000000018001D47A case 3
0x18001d4ca  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18001d4d1  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 000000018001D47A case 2
0x18001d4d8  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18001d4df  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 000000018001D47A case 1
0x18001d4e6  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018001D47A cases 0,9-15
0x18001d4ea  retn
0x18001d4f0  movups  xmm2, xmmword ptr [rdx]
0x18001d4f3  sub     rdx, rcx
0x18001d4f6  add     rcx, r8
0x18001d4f9  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18001d4fe  sub     rcx, 10h
0x18001d502  sub     r8, 10h
0x18001d506  test    cl, 0Fh
0x18001d509  jz      short loc_18001D523
0x18001d50b  mov     r9, rcx
0x18001d50e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d512  movups  xmm1, xmm0
0x18001d515  movups  xmm0, xmmword ptr [rcx+rdx]
0x18001d519  movups  xmmword ptr [r9], xmm1
0x18001d51d  mov     r8, rcx
0x18001d520  sub     r8, rax
0x18001d523  mov     r9, r8
0x18001d526  shr     r9, 7
0x18001d52a  jz      short loc_18001D59D
  ... truncated ...
```
