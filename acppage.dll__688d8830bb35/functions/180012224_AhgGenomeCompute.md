# AhgGenomeCompute

- ea: `0x180012224`
- end: `0x18001273c`
- name: `AhgGenomeCompute`
- size: `1304`
- prototype: `__int64 __fastcall(_DWORD *, int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011640`

## callees

- `0x180012224`
- `0x180015220`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x1800122ac`
- `KERNEL32!SystemTimeToFileTime` at `0x18001252d`
- `KERNEL32!SystemTimeToFileTime` at `0x1800122ac`
- `KERNEL32!SystemTimeToFileTime` at `0x18001252d`

## string_xrefs

- `0x180012303`: `AhgGenomeCompute`
- `0x180012587`: `AhgGenomeCompute`
- `0x180012648`: `AhgGenomeCompute`

## pseudocode

```c
__int64 __fastcall AhgGenomeCompute(_DWORD *a1, int *a2, __int64 a3)
{
  int v4; // r14d
  unsigned __int64 v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rsi
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // esi
  unsigned int v12; // edi
  int v13; // ecx
  bool v14; // zf
  bool v15; // cc
  int v16; // ecx
  bool v17; // zf
  bool v18; // cc
  int v19; // r12d
  __int64 v20; // rbx
  unsigned int v21; // r13d
  __int64 v22; // r12
  int v23; // r9d
  int v24; // r8d
  unsigned int i; // edx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // edx
  bool v29; // zf
  bool v30; // cc
  unsigned int j; // r8d
  __int64 v32; // rax
  int v34; // [rsp+20h] [rbp-38h]
  struct _FILETIME FileTime; // [rsp+28h] [rbp-30h] BYREF
  struct _FILETIME v36; // [rsp+30h] [rbp-28h]
  struct _FILETIME v37; // [rsp+38h] [rbp-20h]
  unsigned __int64 v38; // [rsp+40h] [rbp-18h]
  int v41; // [rsp+B0h] [rbp+58h]
  int v42; // [rsp+B0h] [rbp+58h]
  int v43; // [rsp+B8h] [rbp+60h]

  v34 = 4;
  FileTime = 0;
  v41 = 0;
  v4 = 0;
  v43 = 0;
  if ( (*(_BYTE *)(a3 + 636) & 1) != 0 )
  {
    v5 = *(_QWORD *)(a3 + 640);
    v6 = 0;
    v36 = (struct _FILETIME)v5;
    v43 = 1;
    while ( 1 )
    {
      v7 = v6;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)&_ImageBase[12 * dword_18001B990[v6] + 56540], &FileTime) )
        break;
      v36 = FileTime;
      v37 = (struct _FILETIME)v5;
      if ( v5 >= *(_QWORD *)&FileTime )
      {
        ++v6;
        v34 = dword_18001B990[v7];
        if ( v6 < 6 )
          continue;
      }
      goto LABEL_8;
    }
    AslLogCallPrintf(2, "AhgGenomeCompute", 247, "Failed to convert system time to file time");
    v43 = 0;
  }
LABEL_8:
  if ( (*(_BYTE *)(a3 + 732) & 1) != 0 )
  {
    v8 = *(_DWORD *)(a3 + 736);
    v9 = 0;
    while ( v8 < dword_18001B964[3 * v9] || v8 >= dword_18001B968[3 * v9] )
    {
      if ( (unsigned int)++v9 >= 4 )
        goto LABEL_15;
    }
    v10 = dword_18001B9B4[6 * dword_18001B960[3 * v9]];
    LOWORD(v41) = HIWORD(v10);
    HIWORD(v41) = v10;
LABEL_15:
    v4 = 128;
  }
  if ( (*(_BYTE *)(a3 + 780) & 1) != 0 )
  {
    v11 = *(_DWORD *)(a3 + 784);
    v12 = HIWORD(v11);
    v4 |= 0x100u;
LABEL_99:
    v27 = 0;
    goto LABEL_100;
  }
  LOWORD(v11) = HIWORD(v41);
  LOWORD(v12) = v41;
  if ( (*(_BYTE *)(a3 + 764) & 1) != 0 )
  {
    if ( (_WORD)v41 == 5 )
    {
      if ( HIWORD(v41) != 1 && HIWORD(v41) )
        goto LABEL_26;
    }
    else if ( (unsigned __int16)v41 >= 5u )
    {
      goto LABEL_26;
    }
    LOWORD(v12) = 5;
    LOWORD(v11) = 1;
LABEL_26:
    v4 |= 0x1000u;
    goto LABEL_99;
  }
  if ( (*(_BYTE *)(a3 + 700) & 1) != 0 )
  {
    v13 = *(_DWORD *)(a3 + 704);
    v14 = HIWORD(v13) == (unsigned __int16)v41;
    v15 = HIWORD(v13) <= (unsigned __int16)v41;
    if ( HIWORD(v13) == (_WORD)v41 )
    {
      if ( (_WORD)v13 == HIWORD(v41) )
      {
LABEL_34:
        LOWORD(v12) = HIWORD(v13);
        LOWORD(v11) = v13;
LABEL_35:
        v4 |= 0x20u;
        goto LABEL_36;
      }
      v14 = HIWORD(v13) == (unsigned __int16)v41;
      v15 = HIWORD(v13) <= (unsigned __int16)v41;
    }
    if ( v15 && (!v14 || (unsigned __int16)v13 <= HIWORD(v41)) )
      goto LABEL_35;
    goto LABEL_34;
  }
LABEL_36:
  if ( (*(_BYTE *)(a3 + 716) & 1) == 0 )
    goto LABEL_45;
  v16 = *(_DWORD *)(a3 + 720);
  v17 = HIWORD(v16) == (unsigned __int16)v12;
  v18 = HIWORD(v16) <= (unsigned __int16)v12;
  if ( HIWORD(v16) != (_WORD)v12 )
  {
LABEL_40:
    if ( v18 && (!v17 || (unsigned __int16)v16 <= (unsigned __int16)v11) )
      goto LABEL_44;
    goto LABEL_43;
  }
  if ( (_WORD)v16 != (_WORD)v11 )
  {
    v17 = HIWORD(v16) == (unsigned __int16)v12;
    v18 = HIWORD(v16) <= (unsigned __int16)v12;
    goto LABEL_40;
  }
LABEL_43:
  LOWORD(v12) = HIWORD(v16);
  LOWORD(v11) = v16;
LABEL_44:
  v4 |= 0x40u;
LABEL_45:
  if ( (*(_BYTE *)(a3 + 796) & 1) != 0 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_50;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_50:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 0x200u;
  }
  if ( (*(_BYTE *)(a3 + 652) & 1) != 0 && *(_WORD *)(a3 + 656) == 0x8664 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_58;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_58:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 2u;
  }
  if ( (*(_BYTE *)(a3 + 668) & 1) != 0 && *(_DWORD *)(a3 + 672) == 1 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_66;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_66:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 4u;
  }
  v19 = 4;
  if ( (*(_BYTE *)(a3 + 636) & 1) != 0 )
  {
    v20 = *(_QWORD *)(a3 + 640);
    v21 = 0;
    v36 = (struct _FILETIME)v20;
    while ( SystemTimeToFileTime((const SYSTEMTIME *)&_ImageBase[12 * dword_18001B990[v21] + 56540], &FileTime) )
    {
      v37 = FileTime;
      v38 = __PAIR64__(v36.dwHighDateTime, v20);
      if ( __PAIR64__(v36.dwHighDateTime, v20) >= *(_QWORD *)&FileTime )
      {
        v22 = v21++;
        v19 = dword_18001B990[v22];
        if ( v21 < 6 )
          continue;
      }
      goto LABEL_75;
    }
    AslLogCallPrintf(2, "AhgGenomeCompute", 369, "Failed to convert system time to file time");
LABEL_75:
    v23 = 1;
    v4 |= 1u;
  }
  else
  {
    v23 = 0;
  }
  v24 = 4;
  if ( (*(_BYTE *)(a3 + 684) & 1) != 0 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( *(_DWORD *)(a3 + 688) <= (unsigned int)(unsigned __int16)word_18001B9B8[12 * dword_18001B990[i]] )
        break;
      v24 = dword_18001B990[i];
    }
    v4 |= 0x10u;
    v26 = 1;
  }
  else
  {
    v26 = 0;
  }
  if ( v23 == 1 )
  {
    if ( v26 == 1 && v19 >= v24 )
      v19 = v24;
  }
  else
  {
    v19 = 4;
    if ( v26 == 1 )
      v19 = v24;
  }
  if ( v4 )
  {
    v28 = dword_18001B9B4[6 * v19];
    v29 = HIWORD(v28) == (unsigned __int16)v12;
    v30 = HIWORD(v28) <= (unsigned __int16)v12;
    if ( HIWORD(v28) == (_WORD)v12 )
    {
      if ( (_WORD)v28 == (_WORD)v11 )
      {
LABEL_98:
        LOWORD(v12) = HIWORD(v28);
        LOWORD(v11) = v28;
        goto LABEL_99;
      }
      v29 = HIWORD(v28) == (unsigned __int16)v12;
      v30 = HIWORD(v28) <= (unsigned __int16)v12;
    }
    if ( v30 && (!v29 || (unsigned __int16)v28 <= (unsigned __int16)v11) )
      goto LABEL_99;
    goto LABEL_98;
  }
  v27 = 1006;
  AslLogCallPrintf(1, "AhgGenomeCompute", 416, "Bad timestamp");
LABEL_100:
  if ( v43 == 1 && LOWORD(dword_18001B9B4[6 * v34]) == (_WORD)v11 && HIWORD(dword_18001B9B4[6 * v34]) == (_WORD)v12 )
    v4 |= 0x2000u;
  for ( j = 1; j < 6; ++j )
  {
    if ( (unsigned __int16)v11 + ((unsigned __int16)v12 << 16) < (unsigned int)dword_18001B9B4[6 * dword_18001B990[j]] )
      break;
  }
  v32 = dword_18001B990[j - 1];
  *a2 = v4;
  HIWORD(v42) = dword_18001B9B4[6 * v32];
  LOWORD(v42) = HIWORD(dword_18001B9B4[6 * v32]);
  *a1 = v42;
  return v27;
}

```

## disassembly

```asm
0x180012224  mov     [rsp-40h+arg_8], rdx
0x180012229  mov     [rsp-40h+arg_0], rcx
0x18001222e  push    rbp
0x18001222f  push    rbx
0x180012230  push    rsi
0x180012231  push    rdi
0x180012232  push    r12
0x180012234  push    r13
0x180012236  push    r14
0x180012238  push    r15
0x18001223a  mov     rbp, rsp
0x18001223d  sub     rsp, 58h
0x180012241  xor     r11d, r11d
0x180012244  mov     [rbp+var_38], 4
0x18001224b  mov     r15, r8
0x18001224e  mov     qword ptr [rbp+FileTime.dwLowDateTime], r11
0x180012252  mov     [rbp+arg_10], r11d
0x180012256  lea     r9, __ImageBase
0x18001225d  mov     r14d, r11d
0x180012260  mov     [rbp+arg_18], r11d
0x180012264  lea     r10d, [r11+1]
0x180012268  lea     ebx, [r11+6]
0x18001226c  test    [r8+27Ch], r10b
0x180012273  jz      loc_18001232B
0x180012279  mov     rbx, [r8+280h]
0x180012280  mov     edi, r11d
0x180012283  mov     [rbp+var_28], rbx
0x180012287  mov     r12d, dword ptr [rbp+var_28+4]
0x18001228b  mov     [rbp+arg_18], r10d
0x18001228f  mov     esi, edi
0x180012291  lea     rdx, [rbp+FileTime]; lpFileTime
0x180012295  movsxd  rax, ds:rva dword_18001B990[r9+rsi*4]
0x18001229d  lea     rcx, [rax+rax*2]
0x1800122a1  lea     rcx, ds:1B9B8h[rcx*8]
0x1800122a9  add     rcx, r9; lpSystemTime
0x1800122ac  call    cs:__imp_SystemTimeToFileTime
0x1800122b2  xor     r11d, r11d
0x1800122b5  test    eax, eax
0x1800122b7  jz      short loc_1800122F6
0x1800122b9  mov     eax, [rbp+FileTime.dwLowDateTime]
0x1800122bc  lea     r9, __ImageBase
0x1800122c3  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x1800122c6  lea     r10d, [r11+1]
0x1800122ca  mov     dword ptr [rbp+var_28], eax
0x1800122cd  mov     dword ptr [rbp+var_28+4], ecx
0x1800122d0  mov     rax, [rbp+var_28]
0x1800122d4  mov     dword ptr [rbp+var_20], ebx
0x1800122d7  mov     dword ptr [rbp+var_20+4], r12d
0x1800122db  cmp     [rbp+var_20], rax
0x1800122df  jb      short loc_180012326
0x1800122e1  mov     eax, ds:rva dword_18001B990[r9+rsi*4]
0x1800122e9  add     edi, r10d
0x1800122ec  mov     [rbp+var_38], eax
0x1800122ef  cmp     edi, 6
0x1800122f2  jb      short loc_18001228F
0x1800122f4  jmp     short loc_180012326
0x1800122f6  lea     r9, aFailedToConver_1; "Failed to convert system time to file t"...
0x1800122fd  mov     r8d, 0F7h
0x180012303  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18001230a  mov     ecx, 2
0x18001230f  call    AslLogCallPrintf
0x180012314  xor     r11d, r11d
0x180012317  lea     r9, __ImageBase
0x18001231e  mov     [rbp+arg_18], r11d
0x180012322  lea     r10d, [r11+1]
0x180012326  mov     ebx, 6
0x18001232b  test    [r15+2DCh], r10b
0x180012332  jz      short loc_1800123A6
0x180012334  mov     r8d, [r15+2E0h]
0x18001233b  mov     ecx, r11d
0x18001233e  mov     eax, ecx
0x180012340  lea     rdx, [rax+rax*2]
0x180012344  cmp     r8d, ds:rva dword_18001B964[r9+rdx*4]
0x18001234c  jb      short loc_180012358
0x18001234e  cmp     r8d, ds:rva dword_18001B968[r9+rdx*4]
0x180012356  jb      short loc_180012362
0x180012358  add     ecx, r10d
0x18001235b  cmp     ecx, 4
0x18001235e  jb      short loc_18001233E
0x180012360  jmp     short loc_1800123A0
0x180012362  movsxd  rax, ds:rva dword_18001B960[r9+rdx*4]
0x18001236a  lea     rcx, [rax+rax*2]
0x18001236e  mov     eax, ds:rva dword_18001B9B4[r9+rcx*8]
0x180012376  mov     ecx, eax
0x180012378  shr     ecx, 10h
0x18001237b  mov     word ptr [rbp+arg_10+2], ax
0x18001237f  mov     word ptr [rbp+arg_10], cx
0x180012383  test    cx, cx
0x180012386  jnz     short loc_18001239A
0x180012388  test    ax, ax
0x18001238b  jz      short loc_18001239A
0x18001238d  test    cx, cx
0x180012390  jnz     short loc_18001239A
0x180012392  test    ax, ax
0x180012395  mov     eax, r11d
0x180012398  jz      short loc_18001239D
0x18001239a  mov     eax, [rbp+arg_10]
0x18001239d  mov     [rbp+arg_10], eax
0x1800123a0  mov     r14d, 80h
0x1800123a6  test    [r15+30Ch], r10b
0x1800123ad  jz      short loc_1800123CC
0x1800123af  mov     esi, [r15+310h]
0x1800123b6  mov     edi, esi
0x1800123b8  shr     edi, 10h
0x1800123bb  bts     r14d, 8
0x1800123c0  lea     r15, __ImageBase
0x1800123c7  jmp     loc_180012692
0x1800123cc  movzx   esi, word ptr [rbp+arg_10+2]
0x1800123d0  movzx   edi, word ptr [rbp+arg_10]
0x1800123d4  test    [r15+2FCh], r10b
0x1800123db  jz      short loc_180012405
0x1800123dd  mov     eax, 5
0x1800123e2  cmp     ax, di
0x1800123e5  jnz     short loc_1800123EF
0x1800123e7  cmp     r10w, si
0x1800123eb  jnz     short loc_1800123F7
0x1800123ed  jmp     short loc_1800123F9
0x1800123ef  ja      short loc_1800123F9
0x1800123f1  jnz     short loc_1800123FE
0x1800123f3  cmp     r10w, si
0x1800123f7  jbe     short loc_1800123FE
0x1800123f9  mov     edi, eax
0x1800123fb  mov     esi, r10d
0x1800123fe  bts     r14d, 0Ch
0x180012403  jmp     short loc_1800123C0
0x180012405  test    [r15+2BCh], r10b
0x18001240c  jz      short loc_18001243A
0x18001240e  mov     ecx, [r15+2C0h]
0x180012415  mov     eax, ecx
0x180012417  shr     eax, 10h
0x18001241a  cmp     ax, di
0x18001241d  jnz     short loc_180012427
0x18001241f  cmp     cx, si
0x180012422  jz      short loc_180012430
0x180012424  cmp     ax, di
0x180012427  ja      short loc_180012430
0x180012429  jnz     short loc_180012436
0x18001242b  cmp     cx, si
0x18001242e  jbe     short loc_180012436
0x180012430  movzx   edi, ax
0x180012433  movzx   esi, cx
0x180012436  or      r14d, 20h
0x18001243a  test    [r15+2CCh], r10b
0x180012441  jz      short loc_18001246F
0x180012443  mov     ecx, [r15+2D0h]
0x18001244a  mov     eax, ecx
0x18001244c  shr     eax, 10h
0x18001244f  cmp     ax, di
0x180012452  jnz     short loc_18001245C
0x180012454  cmp     cx, si
0x180012457  jz      short loc_180012465
0x180012459  cmp     ax, di
0x18001245c  ja      short loc_180012465
0x18001245e  jnz     short loc_18001246B
0x180012460  cmp     cx, si
0x180012463  jbe     short loc_18001246B
0x180012465  movzx   edi, ax
0x180012468  movzx   esi, cx
0x18001246b  or      r14d, 40h
0x18001246f  test    [r15+31Ch], r10b
0x180012476  jz      short loc_180012492
0x180012478  cmp     bx, di
0x18001247b  jnz     short loc_180012485
0x18001247d  cmp     r11w, si
0x180012481  jnz     short loc_18001248D
0x180012483  jmp     short loc_180012487
0x180012485  jbe     short loc_18001248D
0x180012487  movzx   edi, bx
0x18001248a  mov     esi, r11d
0x18001248d  bts     r14d, 9
0x180012492  test    [r15+28Ch], r10b
0x180012499  jz      short loc_1800124C3
0x18001249b  mov     eax, 8664h
0x1800124a0  cmp     [r15+290h], ax
0x1800124a8  jnz     short loc_1800124C3
0x1800124aa  cmp     bx, di
0x1800124ad  jnz     short loc_1800124B7
0x1800124af  cmp     r11w, si
0x1800124b3  jnz     short loc_1800124BF
0x1800124b5  jmp     short loc_1800124B9
0x1800124b7  jbe     short loc_1800124BF
0x1800124b9  movzx   edi, bx
0x1800124bc  mov     esi, r11d
0x1800124bf  or      r14d, 2
0x1800124c3  test    [r15+29Ch], r10b
0x1800124ca  jz      short loc_1800124EE
0x1800124cc  cmp     [r15+2A0h], r10d
0x1800124d3  jnz     short loc_1800124EE
0x1800124d5  cmp     bx, di
0x1800124d8  jnz     short loc_1800124E2
0x1800124da  cmp     r11w, si
0x1800124de  jnz     short loc_1800124EA
0x1800124e0  jmp     short loc_1800124E4
0x1800124e2  jbe     short loc_1800124EA
0x1800124e4  movzx   edi, bx
0x1800124e7  mov     esi, r11d
0x1800124ea  or      r14d, 4
0x1800124ee  mov     r12d, 4
0x1800124f4  test    [r15+27Ch], r10b
0x1800124fb  jz      loc_1800125A9
0x180012501  mov     rbx, [r15+280h]
0x180012508  mov     r13d, r11d
0x18001250b  mov     [rbp+var_28], rbx
0x18001250f  mov     eax, r13d
0x180012512  lea     rdx, [rbp+FileTime]; lpFileTime
0x180012516  movsxd  rax, ds:rva dword_18001B990[r9+rax*4]
0x18001251e  lea     rcx, [rax+rax*2]
0x180012522  lea     rcx, ds:1B9B8h[rcx*8]
0x18001252a  add     rcx, r9; lpSystemTime
0x18001252d  call    cs:__imp_SystemTimeToFileTime
0x180012533  xor     r11d, r11d
0x180012536  test    eax, eax
0x180012538  jz      short loc_18001257A
0x18001253a  mov     eax, dword ptr [rbp+var_28+4]
0x18001253d  lea     r10d, [r11+1]
0x180012541  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x180012544  mov     dword ptr [rbp+var_18+4], eax
0x180012547  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18001254a  mov     dword ptr [rbp+var_20], eax
0x18001254d  mov     dword ptr [rbp+var_20+4], ecx
0x180012550  mov     rax, [rbp+var_20]
0x180012554  mov     dword ptr [rbp+var_18], ebx
0x180012557  cmp     [rbp+var_18], rax
0x18001255b  jb      short loc_1800125A1
0x18001255d  mov     r12d, r13d
0x180012560  lea     r9, __ImageBase
0x180012567  add     r13d, r10d
0x18001256a  mov     r12d, ds:rva dword_18001B990[r9+r12*4]
0x180012572  cmp     r13d, 6
0x180012576  jb      short loc_18001250F
0x180012578  jmp     short loc_1800125A1
0x18001257a  lea     r9, aFailedToConver_1; "Failed to convert system time to file t"...
0x180012581  mov     r8d, 171h
0x180012587  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18001258e  mov     ecx, 2
0x180012593  call    AslLogCallPrintf
0x180012598  mov     r10d, 1
0x18001259e  xor     r11d, r11d
0x1800125a1  mov     r9d, r10d
0x1800125a4  or      r14d, r10d
0x1800125a7  jmp     short loc_1800125AC
0x1800125a9  mov     r9d, r11d
0x1800125ac  mov     ebx, 4
0x1800125b1  mov     r8d, ebx
0x1800125b4  test    [r15+2ACh], r10b
0x1800125bb  jz      short loc_18001260F
0x1800125bd  mov     edx, r11d
0x1800125c0  mov     r11d, [r15+2B0h]
0x1800125c7  lea     r15, __ImageBase
0x1800125ce  mov     eax, edx
0x1800125d0  movsxd  r10, ds:rva dword_18001B990[r15+rax*4]
0x1800125d8  lea     rcx, [r10+r10*2]
0x1800125dc  movzx   eax, ds:rva word_18001B9B8[r15+rcx*8]
0x1800125e5  cmp     r11d, eax
0x1800125e8  jbe     short loc_1800125FD
0x1800125ea  mov     r8d, r10d
0x1800125ed  mov     r10d, 1
0x1800125f3  add     edx, r10d
0x1800125f6  cmp     edx, 6
0x1800125f9  jb      short loc_1800125CE
0x1800125fb  jmp     short loc_180012603
0x1800125fd  mov     r10d, 1
0x180012603  or      r14d, 10h
0x180012607  mov     eax, r10d
0x18001260a  xor     r11d, r11d
0x18001260d  jmp     short loc_180012619
0x18001260f  mov     eax, r11d
0x180012612  lea     r15, __ImageBase
0x180012619  cmp     r9d, r10d
0x18001261c  jnz     short loc_18001262C
0x18001261e  cmp     eax, r10d
0x180012621  jnz     short loc_180012636
0x180012623  cmp     r12d, r8d
0x180012626  cmovge  r12d, r8d
0x18001262a  jmp     short loc_180012636
0x18001262c  cmp     eax, r10d
0x18001262f  mov     r12d, ebx
0x180012632  cmovz   r12d, r8d
0x180012636  test    r14d, r14d
0x180012639  jnz     short loc_180012662
0x18001263b  lea     r9, aBadTimestamp; "Bad timestamp"
0x180012642  mov     r8d, 1A0h
0x180012648  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18001264f  mov     ecx, r10d
0x180012652  mov     ebx, 3EEh
0x180012657  call    AslLogCallPrintf
0x18001265c  lea     r10d, [r14+1]
0x180012660  jmp     short loc_180012695
0x180012662  movsxd  rax, r12d
0x180012665  lea     rcx, [rax+rax*2]
0x180012669  mov     edx, ds:rva dword_18001B9B4[r15+rcx*8]
0x180012671  mov     eax, edx
0x180012673  shr     eax, 10h
0x180012676  cmp     ax, di
0x180012679  jnz     short loc_180012683
0x18001267b  cmp     dx, si
0x18001267e  jz      short loc_18001268C
0x180012680  cmp     ax, di
0x180012683  ja      short loc_18001268C
0x180012685  jnz     short loc_180012692
  ... truncated ...
```
