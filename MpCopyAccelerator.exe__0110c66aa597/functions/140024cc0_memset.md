# memset

- ea: `0x140024cc0`
- end: `0x14002504c`
- name: `memset`
- size: `908`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x140006348`
- `0x14000bc90`
- `0x14000c7c8`
- `0x140011470`
- `0x1400116c0`
- `0x140011cfc`
- `0x1400141d0`
- `0x1400143c4`
- `0x140014650`
- `0x140014da4`
- `0x140016664`
- `0x140016a94`
- `0x140018130`
- `0x140018b74`
- `0x14001ae90`
- `0x140022568`
- `0x140022eb8`
- `0x1400232dc`
- `0x140023d3c`

## callees

- `0x140024cb0`
- `0x140024cc0`

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
        __asm { vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000140024E58 case 8 }
LABEL_29:
        __asm { vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000140024E58 case 7 }
LABEL_30:
        __asm { vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000140024E58 case 6 }
LABEL_31:
        __asm { vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000140024E58 case 5 }
LABEL_32:
        __asm { vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000140024E58 case 4 }
LABEL_33:
        __asm { vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000140024E58 case 3 }
LABEL_34:
        __asm { vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000140024E58 case 2 }
LABEL_35:
        __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000140024E58 case 1 }
LABEL_36:
        __asm
        {
          vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000140024E58 cases 0,9-15
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
      __asm { vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000140024F18 case 8 }
LABEL_40:
      __asm { vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000140024F18 case 7 }
LABEL_41:
      __asm { vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000140024F18 case 6 }
LABEL_42:
      __asm { vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000140024F18 case 5 }
LABEL_43:
      __asm { vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000140024F18 case 4 }
LABEL_44:
      __asm { vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000140024F18 case 3 }
LABEL_45:
      __asm { vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000140024F18 case 2 }
LABEL_46:
      __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000140024F18 case 1 }
LABEL_47:
      __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000140024F18 cases 0,9-15 }
      _mm_sfence();
      __asm { vzeroupper }
      break;
  }
  return result;
}

```

## disassembly

```asm
0x140024cc0  mov     rax, rcx
0x140024cc3  mov     r9, rcx
0x140024cc6  lea     r10, cs:140000000h
0x140024ccd  movzx   edx, dl
0x140024cd0  mov     r11, 101010101010101h
0x140024cda  imul    r11, rdx
0x140024cde  movq    xmm0, r11
0x140024ce3  cmp     r8, 0Fh
0x140024ce7  ja      loc_140024D70
0x140024ced  nop     dword ptr [rax]
0x140024cf0  and     r8, 0Fh; switch 16 cases
0x140024cf4  add     rcx, r8
0x140024cf7  mov     r9d, ds:(jpt_140024D02 - 140000000h)[r10+r8*4]
0x140024cff  add     r9, r10
0x140024d02  jmp     r9; switch jump
0x140024d05  mov     [rcx-0Fh], r11; jumptable 0000000140024D02 case 15
0x140024d09  mov     [rcx-7], r11d; jumptable 0000000140024D02 case 7
0x140024d0d  mov     [rcx-3], r11w; jumptable 0000000140024D02 case 3
0x140024d12  mov     [rcx-1], r11b; jumptable 0000000140024D02 case 1
0x140024d16  retn; jumptable 0000000140024D02 case 0
0x140024d17  mov     [rcx-0Eh], r11; jumptable 0000000140024D02 case 14
0x140024d1b  mov     [rcx-6], r11d; jumptable 0000000140024D02 case 6
0x140024d1f  mov     [rcx-2], r11w; jumptable 0000000140024D02 case 2
0x140024d24  retn
0x140024d30  mov     [rcx-0Dh], r11; jumptable 0000000140024D02 case 13
0x140024d34  mov     [rcx-5], r11d; jumptable 0000000140024D02 case 5
0x140024d38  mov     [rcx-1], r11b
0x140024d3c  retn
0x140024d40  mov     [rcx-0Ch], r11; jumptable 0000000140024D02 case 12
0x140024d44  mov     [rcx-4], r11d; jumptable 0000000140024D02 case 4
0x140024d48  retn
0x140024d49  mov     [rcx-0Bh], r11; jumptable 0000000140024D02 case 11
0x140024d4d  mov     [rcx-3], r11w
0x140024d52  mov     [rcx-1], r11b
0x140024d56  retn
0x140024d57  mov     [rcx-9], r11; jumptable 0000000140024D02 case 9
0x140024d5b  mov     [rcx-1], r11b
0x140024d5f  retn
0x140024d60  mov     [rcx-0Ah], r11; jumptable 0000000140024D02 case 10
0x140024d64  mov     [rcx-2], r11w
0x140024d69  retn
0x140024d6a  mov     [rcx-8], r11; jumptable 0000000140024D02 case 8
0x140024d6e  retn
0x140024d70  punpcklqdq xmm0, xmm0
0x140024d74  cmp     r8, 20h ; ' '
0x140024d78  ja      short loc_140024D86
0x140024d7a  movdqu  xmmword ptr [rcx], xmm0
0x140024d7e  movdqu  xmmword ptr [rcx+r8-10h], xmm0
0x140024d85  retn
0x140024d86  cmp     cs:__isa_available, 3
0x140024d8d  jb      loc_140024F70
0x140024d93  cmp     r8, cs:__memset_fast_string_threshold
0x140024d9a  jbe     short loc_140024DB2
0x140024d9c  cmp     r8, cs:__memset_nt_threshold
0x140024da3  ja      short loc_140024DB2
0x140024da5  test    byte ptr cs:__favor, 2
0x140024dac  jnz     memset_repstos
0x140024db2  vinsertf128 ymm0, ymm0, xmm0, 1
0x140024db8  mov     r9, rcx
0x140024dbb  and     r9, 1Fh
0x140024dbf  sub     r9, 20h ; ' '
0x140024dc3  sub     rcx, r9
0x140024dc6  sub     rdx, r9
0x140024dc9  add     r8, r9
0x140024dcc  cmp     r8, 100h
0x140024dd3  jbe     short loc_140024E3A
0x140024dd5  cmp     r8, cs:__memset_nt_threshold
0x140024ddc  ja      loc_140024EB0
0x140024de2  nop     word ptr [rax+rax+00000000h]
0x140024df0  vmovdqa ymmword ptr [rcx], ymm0
0x140024df4  vmovdqa ymmword ptr [rcx+20h], ymm0
0x140024df9  vmovdqa ymmword ptr [rcx+40h], ymm0
0x140024dfe  vmovdqa ymmword ptr [rcx+60h], ymm0
0x140024e03  vmovdqa ymmword ptr [rcx+80h], ymm0
0x140024e0b  vmovdqa ymmword ptr [rcx+0A0h], ymm0
0x140024e13  vmovdqa ymmword ptr [rcx+0C0h], ymm0
0x140024e1b  vmovdqa ymmword ptr [rcx+0E0h], ymm0
0x140024e23  add     rcx, 100h
0x140024e2a  sub     r8, 100h
0x140024e31  cmp     r8, 100h
0x140024e38  jnb     short loc_140024DF0
0x140024e3a  lea     r9, [r8+1Fh]
0x140024e3e  and     r9, 0FFFFFFFFFFFFFFE0h
0x140024e42  mov     r11, r9
0x140024e45  shr     r11, 5
0x140024e49  and     r11, 0Fh; switch 16 cases
0x140024e4d  mov     r11d, ds:(jpt_140024E58 - 140000000h)[r10+r11*4]
0x140024e55  add     r11, r10
0x140024e58  jmp     r11; switch jump
0x140024e5b  vmovdqu ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000140024E58 case 8
0x140024e65  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000140024E58 case 7
0x140024e6f  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000140024E58 case 6
0x140024e79  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000140024E58 case 5
0x140024e83  vmovdqu ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000140024E58 case 4
0x140024e8a  vmovdqu ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000140024E58 case 3
0x140024e91  vmovdqu ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000140024E58 case 2
0x140024e98  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000140024E58 case 1
0x140024e9f  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000140024E58 cases 0,9-15
0x140024ea3  vzeroupper
0x140024ea6  retn
0x140024eb0  vmovntdq ymmword ptr [rcx], ymm0
0x140024eb4  vmovntdq ymmword ptr [rcx+20h], ymm0
0x140024eb9  vmovntdq ymmword ptr [rcx+40h], ymm0
0x140024ebe  vmovntdq ymmword ptr [rcx+60h], ymm0
0x140024ec3  vmovntdq ymmword ptr [rcx+80h], ymm0
0x140024ecb  vmovntdq ymmword ptr [rcx+0A0h], ymm0
0x140024ed3  vmovntdq ymmword ptr [rcx+0C0h], ymm0
0x140024edb  vmovntdq ymmword ptr [rcx+0E0h], ymm0
0x140024ee3  add     rcx, 100h
0x140024eea  sub     r8, 100h
0x140024ef1  cmp     r8, 100h
0x140024ef8  jnb     short loc_140024EB0
0x140024efa  lea     r9, [r8+1Fh]
0x140024efe  and     r9, 0FFFFFFFFFFFFFFE0h
0x140024f02  mov     r11, r9
0x140024f05  shr     r11, 5
0x140024f09  and     r11, 0Fh; switch 16 cases
0x140024f0d  mov     r11d, ds:(jpt_140024F18 - 140000000h)[r10+r11*4]
0x140024f15  add     r11, r10
0x140024f18  jmp     r11; switch jump
0x140024f1b  vmovntdq ymmword ptr [rcx+r9-100h], ymm0; jumptable 0000000140024F18 case 8
0x140024f25  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm0; jumptable 0000000140024F18 case 7
0x140024f2f  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm0; jumptable 0000000140024F18 case 6
0x140024f39  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm0; jumptable 0000000140024F18 case 5
0x140024f43  vmovntdq ymmword ptr [rcx+r9-80h], ymm0; jumptable 0000000140024F18 case 4
0x140024f4a  vmovntdq ymmword ptr [rcx+r9-60h], ymm0; jumptable 0000000140024F18 case 3
0x140024f51  vmovntdq ymmword ptr [rcx+r9-40h], ymm0; jumptable 0000000140024F18 case 2
0x140024f58  vmovdqu ymmword ptr [rcx+r8-20h], ymm0; jumptable 0000000140024F18 case 1
0x140024f5f  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000140024F18 cases 0,9-15
0x140024f63  sfence
0x140024f66  vzeroupper
0x140024f69  retn
0x140024f70  cmp     r8, cs:__memset_fast_string_threshold
0x140024f77  jbe     short loc_140024F86
0x140024f79  test    byte ptr cs:__favor, 2
0x140024f80  jnz     memset_repstos
0x140024f86  mov     r9, rcx
0x140024f89  and     r9, 0Fh
0x140024f8d  sub     r9, 10h
0x140024f91  sub     rcx, r9
0x140024f94  sub     rdx, r9
0x140024f97  add     r8, r9
0x140024f9a  cmp     r8, 80h
0x140024fa1  jbe     short loc_140024FEE
0x140024fa3  nop     word ptr [rax+rax+00000000h]
0x140024fb0  movdqa  xmmword ptr [rcx], xmm0
0x140024fb4  movdqa  xmmword ptr [rcx+10h], xmm0
0x140024fb9  movdqa  xmmword ptr [rcx+20h], xmm0
0x140024fbe  movdqa  xmmword ptr [rcx+30h], xmm0
0x140024fc3  movdqa  xmmword ptr [rcx+40h], xmm0
0x140024fc8  movdqa  xmmword ptr [rcx+50h], xmm0
0x140024fcd  movdqa  xmmword ptr [rcx+60h], xmm0
0x140024fd2  movdqa  xmmword ptr [rcx+70h], xmm0
0x140024fd7  add     rcx, 80h
0x140024fde  sub     r8, 80h
0x140024fe5  cmp     r8, 80h
0x140024fec  jnb     short loc_140024FB0
0x140024fee  lea     r9, [r8+0Fh]
0x140024ff2  and     r9, 0FFFFFFFFFFFFFFF0h
0x140024ff6  mov     r11, r9
0x140024ff9  shr     r11, 4
0x140024ffd  and     r11, 0Fh; switch 16 cases
0x140025001  mov     r11d, ds:(jpt_14002500C - 140000000h)[r10+r11*4]
0x140025009  add     r11, r10
0x14002500c  jmp     r11; switch jump
0x14002500f  movdqu  xmmword ptr [rcx+r9-80h], xmm0; jumptable 000000014002500C case 8
0x140025016  movdqu  xmmword ptr [rcx+r9-70h], xmm0; jumptable 000000014002500C case 7
0x14002501d  movdqu  xmmword ptr [rcx+r9-60h], xmm0; jumptable 000000014002500C case 6
0x140025024  movdqu  xmmword ptr [rcx+r9-50h], xmm0; jumptable 000000014002500C case 5
0x14002502b  movdqu  xmmword ptr [rcx+r9-40h], xmm0; jumptable 000000014002500C case 4
0x140025032  movdqu  xmmword ptr [rcx+r9-30h], xmm0; jumptable 000000014002500C case 3
0x140025039  movdqu  xmmword ptr [rcx+r9-20h], xmm0; jumptable 000000014002500C case 2
0x140025040  movdqu  xmmword ptr [rcx+r8-10h], xmm0; jumptable 000000014002500C case 1
0x140025047  movdqu  xmmword ptr [rax], xmm0; jumptable 000000014002500C cases 0,9-15
0x14002504b  retn
```
