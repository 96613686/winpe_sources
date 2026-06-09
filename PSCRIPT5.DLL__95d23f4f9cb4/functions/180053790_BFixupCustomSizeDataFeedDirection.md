# BFixupCustomSizeDataFeedDirection

- ea: `0x180053790`
- end: `0x1800539f9`
- name: `BFixupCustomSizeDataFeedDirection`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180053aa0`

## callees

- `0x180053790`

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
      v6 = ~*((_DWORD *)qword_18006B6F0 + a2[29] - 1) & 0xF;
  }
  else
  {
    v6 = 0;
  }
  if ( (int)a2[30] < 3 )
    v6 &= *((_DWORD *)qword_18006B6F0 + (int)a2[30]);
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
0x180053790  push    rbx
0x180053792  push    rbp
0x180053793  push    rsi
0x180053794  push    rdi
0x180053795  push    r12
0x180053797  push    r13
0x180053799  push    r14
0x18005379b  mov     r11, rdx
0x18005379e  mov     r12d, 3
0x1800537a4  xor     r10d, r10d
0x1800537a7  lea     rdx, qword_18006B6F0
0x1800537ae  mov     rdi, rcx
0x1800537b1  cmp     [r11+74h], r12d
0x1800537b5  jle     short loc_1800537BC
0x1800537b7  mov     r9d, r10d
0x1800537ba  jmp     short loc_1800537D5
0x1800537bc  mov     r9d, 0Fh
0x1800537c2  cmp     [r11+74h], r10d
0x1800537c6  jle     short loc_1800537D5
0x1800537c8  movsxd  rax, dword ptr [r11+74h]
0x1800537cc  mov     ecx, [rdx+rax*4-4]
0x1800537d0  not     ecx
0x1800537d2  and     r9d, ecx
0x1800537d5  cmp     [r11+78h], r12d
0x1800537d9  jge     short loc_1800537E3
0x1800537db  movsxd  rax, dword ptr [r11+78h]
0x1800537df  and     r9d, [rdx+rax*4]
0x1800537e3  movzx   edx, word ptr [r8+10h]
0x1800537e8  mov     esi, 1
0x1800537ed  mov     ebx, [r8+4]
0x1800537f1  mov     ecx, edx
0x1800537f3  mov     bp, 4
0x1800537f7  mov     r13d, 0FFFDh
0x1800537fd  lea     r14d, [rsi+1]
0x180053801  test    edx, edx
0x180053803  jz      loc_1800538A6
0x180053809  sub     ecx, esi
0x18005380b  jz      short loc_180053880
0x18005380d  sub     ecx, esi
0x18005380f  jz      short loc_18005384D
0x180053811  cmp     ecx, esi
0x180053813  jnz     loc_1800538D4
0x180053819  cmp     [r8], ebx
0x18005381c  jbe     short loc_18005383B
0x18005381e  test    bpl, r9b
0x180053821  jnz     loc_1800538D4
0x180053827  mov     eax, r9d
0x18005382a  and     al, sil
0x18005382d  neg     al
0x18005382f  sbb     cx, cx
0x180053832  and     cx, r13w
0x180053836  jmp     loc_1800538CC
0x18005383b  test    r9b, 8
0x18005383f  jnz     loc_1800538D4
0x180053845  mov     eax, r9d
0x180053848  and     al, r14b
0x18005384b  jmp     short loc_18005382D
0x18005384d  cmp     [r8], ebx
0x180053850  jbe     short loc_180053867
0x180053852  test    r9b, 8
0x180053856  jnz     short loc_1800538D4
0x180053858  movzx   eax, r9w
0x18005385c  add     ax, ax
0x18005385f  not     ax
0x180053862  and     ax, bp
0x180053865  jmp     short loc_180053879
0x180053867  test    bpl, r9b
0x18005386a  jnz     short loc_1800538D4
0x18005386c  mov     eax, r9d
0x18005386f  not     ax
0x180053872  and     ax, si
0x180053875  shl     ax, 2
0x180053879  mov     [r8+10h], ax
0x18005387e  jmp     short loc_1800538D4
0x180053880  cmp     [r8], ebx
0x180053883  jbe     short loc_180053892
0x180053885  test    sil, r9b
0x180053888  jnz     short loc_1800538D4
0x18005388a  mov     eax, r9d
0x18005388d  and     al, bpl
0x180053890  jmp     short loc_18005389C
0x180053892  test    r14b, r9b
0x180053895  jnz     short loc_1800538D4
0x180053897  mov     eax, r9d
0x18005389a  and     al, 8
0x18005389c  neg     al
0x18005389e  sbb     ax, ax
0x1800538a1  add     ax, bp
0x1800538a4  jmp     short loc_180053879
0x1800538a6  cmp     [r8], ebx
0x1800538a9  jbe     short loc_1800538B7
0x1800538ab  test    r14b, r9b
0x1800538ae  jnz     short loc_1800538D4
0x1800538b0  mov     eax, r9d
0x1800538b3  and     al, 8
0x1800538b5  jmp     short loc_1800538C2
0x1800538b7  test    sil, r9b
0x1800538ba  jnz     short loc_1800538D4
0x1800538bc  mov     eax, r9d
0x1800538bf  and     al, bpl
0x1800538c2  neg     al
0x1800538c4  sbb     cx, cx
0x1800538c7  and     cx, 0FFFEh
0x1800538cc  add     cx, bp
0x1800538cf  mov     [r8+10h], cx
0x1800538d4  movzx   eax, word ptr [r8+10h]
0x1800538d9  cmp     ax, bp
0x1800538dc  jb      short loc_1800538F1
0x1800538de  cmp     [r8], ebx
0x1800538e1  jbe     short loc_180053960
0x1800538e3  test    r14b, r9b
0x1800538e6  jz      short loc_180053936
0x1800538e8  mov     [r8+10h], r10w
0x1800538ed  movzx   eax, r10w
0x1800538f1  sub     ax, si
0x1800538f4  test    r13w, ax
0x1800538f8  jz      loc_180053982
0x1800538fe  mov     eax, [rdi+100h]
0x180053904  test    eax, eax
0x180053906  jz      short loc_180053929
0x180053908  mov     rcx, [rdi+148h]
0x18005390f  add     rcx, rax
0x180053912  jz      short loc_180053929
0x180053914  mov     eax, 0FFh
0x180053919  cmp     [r11+30h], eax
0x18005391d  jnz     short loc_180053929
0x18005391f  cmp     [r11+34h], eax
0x180053923  jnz     loc_1800539A9
0x180053929  mov     eax, esi
0x18005392b  pop     r14
0x18005392d  pop     r13
0x18005392f  pop     r12
0x180053931  pop     rdi
0x180053932  pop     rsi
0x180053933  pop     rbp
0x180053934  pop     rbx
0x180053935  retn
0x180053936  test    r9b, 8
0x18005393a  jz      short loc_180053946
0x18005393c  mov     [r8+10h], r14w
0x180053941  mov     eax, r14d
0x180053944  jmp     short loc_1800538F1
0x180053946  test    sil, r9b
0x180053949  jz      short loc_180053955
0x18005394b  mov     [r8+10h], si
0x180053950  movzx   eax, si
0x180053953  jmp     short loc_1800538F1
0x180053955  mov     [r8+10h], r12w
0x18005395a  movzx   eax, r12w
0x18005395e  jmp     short loc_1800538F1
0x180053960  test    sil, r9b
0x180053963  jz      short loc_18005396C
0x180053965  mov     [r8+10h], r10w
0x18005396a  jmp     short loc_1800538FE
0x18005396c  test    bpl, r9b
0x18005396f  jz      short loc_180053978
0x180053971  mov     [r8+10h], r14w
0x180053976  jmp     short loc_1800538FE
0x180053978  test    r14b, r9b
0x18005397b  jz      short loc_1800539CC
0x18005397d  mov     [r8+10h], si
0x180053982  mov     eax, [rdi+100h]
0x180053988  test    eax, eax
0x18005398a  jz      short loc_180053929
0x18005398c  mov     rcx, [rdi+148h]
0x180053993  add     rcx, rax
0x180053996  jz      short loc_180053929
0x180053998  mov     eax, 0FFh
0x18005399d  cmp     [r11+30h], eax
0x1800539a1  jz      short loc_180053929
0x1800539a3  cmp     [r11+34h], eax
0x1800539a7  jnz     short loc_180053929
0x1800539a9  mov     [r8+10h], dx
0x1800539ae  cmp     dx, si
0x1800539b1  ja      short loc_1800539D3
0x1800539b3  test    r12b, r9b
0x1800539b6  jnz     short loc_1800539D3
0x1800539b8  neg     dx
0x1800539bb  sbb     ax, ax
0x1800539be  neg     ax
0x1800539c1  add     ax, r14w
0x1800539c5  mov     [r8+10h], ax
0x1800539ca  jmp     short loc_1800539F2
0x1800539cc  mov     [r8+10h], r12w
0x1800539d1  jmp     short loc_180053982
0x1800539d3  movzx   eax, dx
0x1800539d6  sub     ax, r14w
0x1800539da  cmp     ax, si
0x1800539dd  ja      short loc_1800539F2
0x1800539df  test    r9b, 0Ch
0x1800539e3  jnz     short loc_1800539F2
0x1800539e5  cmp     dx, r14w
0x1800539e9  setnz   r10b
0x1800539ed  mov     [r8+10h], r10w
0x1800539f2  xor     eax, eax
0x1800539f4  jmp     loc_18005392B
```
