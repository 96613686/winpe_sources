# BFixupCustomSizeDataFeedDirection

- ea: `0x18005512c`
- end: `0x18005539a`
- name: `BFixupCustomSizeDataFeedDirection`
- size: `622`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180055440`

## callees

- `0x18005512c`

## pseudocode

```c
__int64 __fastcall BFixupCustomSizeDataFeedDirection(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int16 v4; // r10
  int v6; // r9d
  unsigned __int16 v7; // dx
  unsigned int v8; // ebx
  char v9; // al
  __int16 v10; // cx
  __int16 v11; // ax
  char v12; // al
  char v13; // al
  __int16 v14; // ax
  __int64 v15; // rax
  __int64 v17; // rax

  HIBYTE(v4) = 0;
  if ( (int)a2[29] <= 3 )
  {
    v6 = 15;
    if ( (int)a2[29] > 0 )
      v6 = ~*((_DWORD *)qword_18006D6B8 + a2[29] - 1) & 0xF;
  }
  else
  {
    v6 = 0;
  }
  if ( (int)a2[30] < 3 )
    v6 &= *((_DWORD *)qword_18006D6B8 + (int)a2[30]);
  v7 = *(_WORD *)(a3 + 16);
  v8 = *(_DWORD *)(a3 + 4);
  if ( v7 )
  {
    switch ( *(_WORD *)(a3 + 16) )
    {
      case 1:
        if ( *(_DWORD *)a3 <= v8 )
        {
          if ( (v6 & 2) != 0 )
            goto LABEL_36;
          v12 = v6 & 8;
        }
        else
        {
          if ( (v6 & 1) != 0 )
            goto LABEL_36;
          v12 = v6 & 4;
        }
        v11 = 4 - (v12 != 0);
        break;
      case 2:
        if ( *(_DWORD *)a3 <= v8 )
        {
          if ( (v6 & 4) != 0 )
            goto LABEL_36;
          v11 = 4 * ((v6 & 1) == 0);
        }
        else
        {
          if ( (v6 & 8) != 0 )
            goto LABEL_36;
          v11 = ~(2 * v6) & 4;
        }
        break;
      case 3:
        if ( *(_DWORD *)a3 <= v8 )
        {
          if ( (v6 & 8) != 0 )
            goto LABEL_36;
          v9 = v6 & 2;
        }
        else
        {
          if ( (v6 & 4) != 0 )
            goto LABEL_36;
          v9 = v6 & 1;
        }
        v10 = v9 != 0 ? 0xFFFD : 0;
        goto LABEL_35;
      default:
        goto LABEL_36;
    }
    *(_WORD *)(a3 + 16) = v11;
    goto LABEL_36;
  }
  if ( *(_DWORD *)a3 <= v8 )
  {
    if ( (v6 & 1) != 0 )
      goto LABEL_36;
    v13 = v6 & 4;
  }
  else
  {
    if ( (v6 & 2) != 0 )
      goto LABEL_36;
    v13 = v6 & 8;
  }
  v10 = v13 != 0 ? 0xFFFE : 0;
LABEL_35:
  *(_WORD *)(a3 + 16) = v10 + 4;
LABEL_36:
  v14 = *(_WORD *)(a3 + 16);
  if ( (unsigned __int16)v14 >= 4u )
  {
    if ( *(_DWORD *)a3 <= v8 )
    {
      if ( (v6 & 1) != 0 )
      {
        *(_WORD *)(a3 + 16) = 0;
        goto LABEL_41;
      }
      if ( (v6 & 4) != 0 )
      {
        *(_WORD *)(a3 + 16) = 2;
        goto LABEL_41;
      }
      if ( (v6 & 2) != 0 )
        *(_WORD *)(a3 + 16) = 1;
      else
        *(_WORD *)(a3 + 16) = 3;
LABEL_57:
      v17 = *(unsigned int *)(a1 + 256);
      if ( !(_DWORD)v17 || !(v17 + *(_QWORD *)(a1 + 328)) || a2[12] == 255 || a2[13] != 255 )
        return 1;
      goto LABEL_61;
    }
    if ( (v6 & 2) != 0 )
    {
      *(_WORD *)(a3 + 16) = 0;
      v14 = 0;
    }
    else if ( (v6 & 8) != 0 )
    {
      *(_WORD *)(a3 + 16) = 2;
      v14 = 2;
    }
    else if ( (v6 & 1) != 0 )
    {
      *(_WORD *)(a3 + 16) = 1;
      v14 = 1;
    }
    else
    {
      *(_WORD *)(a3 + 16) = 3;
      v14 = 3;
    }
  }
  if ( ((v14 - 1) & 0xFFFD) == 0 )
    goto LABEL_57;
LABEL_41:
  v15 = *(unsigned int *)(a1 + 256);
  if ( !(_DWORD)v15 || !(v15 + *(_QWORD *)(a1 + 328)) || a2[12] != 255 || a2[13] == 255 )
    return 1;
LABEL_61:
  *(_WORD *)(a3 + 16) = v7;
  if ( v7 > 1u || (v6 & 3) != 0 )
  {
    if ( (unsigned __int16)(v7 - 2) <= 1u && (v6 & 0xC) == 0 )
    {
      LOBYTE(v4) = v7 != 2;
      *(_WORD *)(a3 + 16) = v4;
    }
  }
  else
  {
    *(_WORD *)(a3 + 16) = (v7 != 0) + 2;
  }
  return 0;
}

```

## disassembly

```asm
0x18005512c  push    rbx
0x18005512e  push    rbp
0x18005512f  push    rsi
0x180055130  push    rdi
0x180055131  push    r12
0x180055133  push    r13
0x180055135  push    r14
0x180055137  mov     r11, rdx
0x18005513a  mov     r12d, 3
0x180055140  xor     r10d, r10d
0x180055143  lea     rdx, qword_18006D6B8
0x18005514a  mov     rdi, rcx
0x18005514d  cmp     [r11+74h], r12d
0x180055151  jle     short loc_180055158
0x180055153  mov     r9d, r10d
0x180055156  jmp     short loc_180055171
0x180055158  mov     r9d, 0Fh
0x18005515e  cmp     [r11+74h], r10d
0x180055162  jle     short loc_180055171
0x180055164  movsxd  rax, dword ptr [r11+74h]
0x180055168  mov     ecx, [rdx+rax*4-4]
0x18005516c  not     ecx
0x18005516e  and     r9d, ecx
0x180055171  cmp     [r11+78h], r12d
0x180055175  jge     short loc_18005517F
0x180055177  movsxd  rax, dword ptr [r11+78h]
0x18005517b  and     r9d, [rdx+rax*4]
0x18005517f  movzx   edx, word ptr [r8+10h]
0x180055184  mov     esi, 1
0x180055189  mov     ebx, [r8+4]
0x18005518d  mov     ecx, edx
0x18005518f  mov     bp, 4
0x180055193  mov     r13d, 0FFFDh
0x180055199  lea     r14d, [rsi+1]
0x18005519d  test    edx, edx
0x18005519f  jz      loc_180055242
0x1800551a5  sub     ecx, esi
0x1800551a7  jz      short loc_18005521C
0x1800551a9  sub     ecx, esi
0x1800551ab  jz      short loc_1800551E9
0x1800551ad  cmp     ecx, esi
0x1800551af  jnz     loc_180055270
0x1800551b5  cmp     [r8], ebx
0x1800551b8  jbe     short loc_1800551D7
0x1800551ba  test    bpl, r9b
0x1800551bd  jnz     loc_180055270
0x1800551c3  mov     eax, r9d
0x1800551c6  and     al, sil
0x1800551c9  neg     al
0x1800551cb  sbb     cx, cx
0x1800551ce  and     cx, r13w
0x1800551d2  jmp     loc_180055268
0x1800551d7  test    r9b, 8
0x1800551db  jnz     loc_180055270
0x1800551e1  mov     eax, r9d
0x1800551e4  and     al, r14b
0x1800551e7  jmp     short loc_1800551C9
0x1800551e9  cmp     [r8], ebx
0x1800551ec  jbe     short loc_180055203
0x1800551ee  test    r9b, 8
0x1800551f2  jnz     short loc_180055270
0x1800551f4  movzx   eax, r9w
0x1800551f8  add     ax, ax
0x1800551fb  not     ax
0x1800551fe  and     ax, bp
0x180055201  jmp     short loc_180055215
0x180055203  test    bpl, r9b
0x180055206  jnz     short loc_180055270
0x180055208  mov     eax, r9d
0x18005520b  not     ax
0x18005520e  and     ax, si
0x180055211  shl     ax, 2
0x180055215  mov     [r8+10h], ax
0x18005521a  jmp     short loc_180055270
0x18005521c  cmp     [r8], ebx
0x18005521f  jbe     short loc_18005522E
0x180055221  test    sil, r9b
0x180055224  jnz     short loc_180055270
0x180055226  mov     eax, r9d
0x180055229  and     al, bpl
0x18005522c  jmp     short loc_180055238
0x18005522e  test    r14b, r9b
0x180055231  jnz     short loc_180055270
0x180055233  mov     eax, r9d
0x180055236  and     al, 8
0x180055238  neg     al
0x18005523a  sbb     ax, ax
0x18005523d  add     ax, bp
0x180055240  jmp     short loc_180055215
0x180055242  cmp     [r8], ebx
0x180055245  jbe     short loc_180055253
0x180055247  test    r14b, r9b
0x18005524a  jnz     short loc_180055270
0x18005524c  mov     eax, r9d
0x18005524f  and     al, 8
0x180055251  jmp     short loc_18005525E
0x180055253  test    sil, r9b
0x180055256  jnz     short loc_180055270
0x180055258  mov     eax, r9d
0x18005525b  and     al, bpl
0x18005525e  neg     al
0x180055260  sbb     cx, cx
0x180055263  and     cx, 0FFFEh
0x180055268  add     cx, bp
0x18005526b  mov     [r8+10h], cx
0x180055270  movzx   eax, word ptr [r8+10h]
0x180055275  cmp     ax, bp
0x180055278  jb      short loc_18005528D
0x18005527a  cmp     [r8], ebx
0x18005527d  jbe     short loc_1800552FD
0x18005527f  test    r14b, r9b
0x180055282  jz      short loc_1800552D3
0x180055284  mov     [r8+10h], r10w
0x180055289  movzx   eax, r10w
0x18005528d  sub     ax, si
0x180055290  test    r13w, ax
0x180055294  jz      loc_18005531F
0x18005529a  mov     eax, [rdi+100h]
0x1800552a0  test    eax, eax
0x1800552a2  jz      short loc_1800552C5
0x1800552a4  mov     rcx, [rdi+148h]
0x1800552ab  add     rcx, rax
0x1800552ae  jz      short loc_1800552C5
0x1800552b0  mov     eax, 0FFh
0x1800552b5  cmp     [r11+30h], eax
0x1800552b9  jnz     short loc_1800552C5
0x1800552bb  cmp     [r11+34h], eax
0x1800552bf  jnz     loc_18005534A
0x1800552c5  mov     eax, esi
0x1800552c7  pop     r14
0x1800552c9  pop     r13
0x1800552cb  pop     r12
0x1800552cd  pop     rdi
0x1800552ce  pop     rsi
0x1800552cf  pop     rbp
0x1800552d0  pop     rbx
0x1800552d1  retn
0x1800552d3  test    r9b, 8
0x1800552d7  jz      short loc_1800552E3
0x1800552d9  mov     [r8+10h], r14w
0x1800552de  mov     eax, r14d
0x1800552e1  jmp     short loc_18005528D
0x1800552e3  test    sil, r9b
0x1800552e6  jz      short loc_1800552F2
0x1800552e8  mov     [r8+10h], si
0x1800552ed  movzx   eax, si
0x1800552f0  jmp     short loc_18005528D
0x1800552f2  mov     [r8+10h], r12w
0x1800552f7  movzx   eax, r12w
0x1800552fb  jmp     short loc_18005528D
0x1800552fd  test    sil, r9b
0x180055300  jz      short loc_180055309
0x180055302  mov     [r8+10h], r10w
0x180055307  jmp     short loc_18005529A
0x180055309  test    bpl, r9b
0x18005530c  jz      short loc_180055315
0x18005530e  mov     [r8+10h], r14w
0x180055313  jmp     short loc_18005529A
0x180055315  test    r14b, r9b
0x180055318  jz      short loc_18005536D
0x18005531a  mov     [r8+10h], si
0x18005531f  mov     eax, [rdi+100h]
0x180055325  test    eax, eax
0x180055327  jz      short loc_1800552C5
0x180055329  mov     rcx, [rdi+148h]
0x180055330  add     rcx, rax
0x180055333  jz      short loc_1800552C5
0x180055335  mov     eax, 0FFh
0x18005533a  cmp     [r11+30h], eax
0x18005533e  jz      short loc_1800552C5
0x180055340  cmp     [r11+34h], eax
0x180055344  jnz     loc_1800552C5
0x18005534a  mov     [r8+10h], dx
0x18005534f  cmp     dx, si
0x180055352  ja      short loc_180055374
0x180055354  test    r12b, r9b
0x180055357  jnz     short loc_180055374
0x180055359  neg     dx
0x18005535c  sbb     ax, ax
0x18005535f  neg     ax
0x180055362  add     ax, r14w
0x180055366  mov     [r8+10h], ax
0x18005536b  jmp     short loc_180055393
0x18005536d  mov     [r8+10h], r12w
0x180055372  jmp     short loc_18005531F
0x180055374  movzx   eax, dx
0x180055377  sub     ax, r14w
0x18005537b  cmp     ax, si
0x18005537e  ja      short loc_180055393
0x180055380  test    r9b, 0Ch
0x180055384  jnz     short loc_180055393
0x180055386  cmp     dx, r14w
0x18005538a  setnz   r10b
0x18005538e  mov     [r8+10h], r10w
0x180055393  xor     eax, eax
0x180055395  jmp     loc_1800552C7
```
