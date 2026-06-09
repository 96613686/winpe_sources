# BInitPalDevInfo

- ea: `0x180025248`
- end: `0x180025716`
- name: `BInitPalDevInfo`
- size: `1230`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180025dc0`

## callees

- `0x180025248`
- `0x1800406e0`
- `0x18005f980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180025304`
- `KERNEL32!LocalFree` at `0x180025313`
- `KERNEL32!LocalFree` at `0x180025304`
- `KERNEL32!LocalFree` at `0x180025313`
- `KERNEL32!LocalAlloc` at `0x180025277`
- `KERNEL32!LocalAlloc` at `0x1800254f8`
- `KERNEL32!LocalAlloc` at `0x180025277`
- `KERNEL32!LocalAlloc` at `0x1800254f8`
- `GDI32!EngCreatePalette` at `0x18002567d`
- `GDI32!EngCreatePalette` at `0x18002567d`

## pseudocode

```c
__int64 __fastcall BInitPalDevInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v6; // r15
  _WORD *v7; // rax
  __int64 v8; // rbx
  _WORD *v9; // rdi
  __int16 v10; // ax
  void *v11; // rcx
  int v13; // eax
  __int16 *v14; // r15
  __int16 v15; // ax
  __int16 v16; // cx
  _DWORD *v17; // r12
  __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int16 v22; // dx
  HLOCAL v23; // rax
  __int64 v24; // r9
  __int64 v25; // r10
  unsigned __int16 v26; // cx
  __int16 v27; // ax
  __int16 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r10
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  ULONG *v36; // r8
  ULONG v37; // edx
  ULONG v38; // ecx
  HPALETTE Palette; // rax
  int v40; // ecx
  bool v41; // cc
  bool v42; // zf
  int v43; // eax

  v3 = *(_QWORD *)(a1 + 3880);
  v6 = a3;
  v7 = LocalAlloc(0x40u, 0x420u);
  v8 = (__int64)v7;
  if ( !v7 )
    return 0;
  *(_QWORD *)(a1 + 4096) = v7;
  if ( v3 )
  {
    v13 = *(_DWORD *)(v3 + 8);
    if ( *(_DWORD *)(v3 + 16) == v13
      || *(_DWORD *)(v3 + 16) == 4 && v13 == 1 && (unsigned int)(*(_DWORD *)(v3 + 4) - 3) <= 1 )
    {
      v17 = (_DWORD *)(v3 + 32);
      v14 = (__int16 *)(v8 + 10);
      if ( *(_DWORD *)(v3 + 32) )
        v18 = *(_WORD *)(v3 + 28);
      else
        v18 = 2;
      *v14 = v18;
      if ( *(_DWORD *)(v3 + 24) == 1 && *v17 )
      {
        v19 = *(_QWORD *)(a1 + 2000);
        v20 = *(unsigned int *)(*(unsigned int *)(v19 + 8) + *(_QWORD *)(v19 + 104) + 144LL);
        if ( (_DWORD)v20 == -1 || !(28 * v20 + *(unsigned int *)(v19 + 16) + *(_QWORD *)(v19 + 96)) )
          goto LABEL_6;
        *(_WORD *)(v8 + 12) |= 1u;
      }
      v21 = *(_DWORD *)(v3 + 4);
      if ( v21 == 1 )
      {
        if ( *(_DWORD *)(v3 + 8) == 8 )
        {
          if ( *(_DWORD *)(v3 + 16) == 8 )
          {
            if ( *(_DWORD *)(v3 + 28) < 0x100u )
              goto LABEL_6;
            *(_WORD *)(v8 + 12) |= 4u;
          }
        }
        else if ( *(_DWORD *)(v3 + 8) == 24 )
        {
          if ( *(_DWORD *)(v3 + 16) == 24 )
          {
            if ( (*(_DWORD *)(v3 + 28) & 0xFFFFFFF8) == 0 && *(_DWORD *)(v3 + 28) != 1 )
              goto LABEL_6;
            v22 = *(_WORD *)(v8 + 12) | 2;
            *(_WORD *)(v8 + 12) = v22;
            if ( (unsigned int)(*(_DWORD *)(a1 + 1952) - 1) <= 1 )
            {
              *(_WORD *)(v8 + 12) = v22 | 0x202;
              *(_QWORD *)(a2 + 284) = 5;
            }
          }
        }
        else if ( *(_DWORD *)(v3 + 8) == 1 && *(_DWORD *)(v3 + 16) == 1 )
        {
          if ( *(_DWORD *)(v3 + 28) < 2u )
            goto LABEL_6;
          *(_WORD *)(v8 + 12) |= 0x10u;
        }
      }
      else
      {
        if ( (unsigned int)(v21 - 3) <= 1 && *(_DWORD *)(v3 + 16) > 1u )
          *(_WORD *)(v8 + 12) |= 8u;
        if ( (*(_BYTE *)(v8 + 12) & 1) != 0 )
        {
          if ( *(_DWORD *)(v3 + 28) < 8u )
            goto LABEL_6;
          if ( *(_DWORD *)(v3 + 4) >= 4u )
            goto LABEL_6;
          v23 = LocalAlloc(0x40u, 4LL * (unsigned __int16)*v14);
          *(_QWORD *)(v8 + 16) = v23;
          if ( !v23 )
            goto LABEL_6;
        }
      }
      goto LABEL_58;
    }
    v14 = (__int16 *)(v8 + 10);
    *(_WORD *)(v8 + 10) = 1;
    switch ( *(_DWORD *)(v3 + 16) )
    {
      case 1:
        *(_WORD *)(v8 + 12) |= 0x10u;
        goto LABEL_27;
      case 4:
        v16 = 8;
        break;
      case 8:
        *(_WORD *)(v8 + 12) |= 4u;
LABEL_27:
        v17 = (_DWORD *)(v3 + 32);
LABEL_58:
        if ( (int)LSetupPalette(a1, v8, (_DWORD *)a2, a3) < 1 )
          goto LABEL_6;
        v24 = a1 + 2000;
        if ( *v17 )
        {
          v25 = *(unsigned int *)(*(unsigned int *)(*(_QWORD *)v24 + 8LL) + *(_QWORD *)(*(_QWORD *)v24 + 104LL) + 144LL);
          if ( (_DWORD)v25 != -1
            && 28 * v25 + *(unsigned int *)(*(_QWORD *)v24 + 16LL) + *(_QWORD *)(*(_QWORD *)v24 + 96LL) )
          {
            *(_DWORD *)(a1 + 112) |= 0x40000u;
          }
          v26 = *(_WORD *)(v8 + 8);
          if ( (unsigned __int16)*v14 <= v26 )
          {
            v27 = *(_WORD *)(v8 + 12);
            if ( (v27 & 0x200) == 0 )
            {
              v26 = -1;
              *(_WORD *)(v8 + 12) = v27 | 0x20;
            }
          }
          *(_WORD *)(v8 + 14) = v26;
        }
        else
        {
          *v14 = *(_WORD *)(v8 + 8);
        }
        v9 = (_WORD *)(v8 + 12);
        v28 = *(_WORD *)(v8 + 12) | 0x40;
        *(_WORD *)(v8 + 12) = v28;
        v29 = *(_QWORD *)v24;
        v30 = *(unsigned int *)(*(unsigned int *)(*(_QWORD *)v24 + 8LL) + *(_QWORD *)(*(_QWORD *)v24 + 104LL) + 136LL);
        if ( (_DWORD)v30 == -1 )
          goto LABEL_72;
        v31 = *(unsigned int *)(v29 + 16) + 28 * v30 + *(_QWORD *)(v29 + 96);
        if ( !v31 )
          goto LABEL_72;
        v32 = *(_DWORD *)(v31 + 8);
        if ( v32 == 3 )
          goto LABEL_77;
        if ( (unsigned int)(v32 - 1) > 1 )
        {
LABEL_72:
          v33 = *(_QWORD *)(a1 + 3872);
          if ( *(_DWORD *)(v33 + 16) == -1 )
            goto LABEL_77;
          v34 = *(_QWORD *)(v29 + 96) + *(unsigned int *)(v29 + 16) + 28LL * *(unsigned int *)(v33 + 16);
          if ( !v34 )
            goto LABEL_77;
          v35 = *(_DWORD *)(v34 + 8);
          if ( (unsigned int)(v35 - 4) <= 2 )
            goto LABEL_6;
          if ( v35 == 3 )
            goto LABEL_77;
        }
        *v9 = v28 & 0xFF3F | 0x80;
LABEL_77:
        if ( *(_QWORD *)(v8 + 16) && !(unsigned int)RMInitDevicePal(a1, v8) )
          goto LABEL_6;
        v6 = a3;
        goto LABEL_80;
      case 0x18:
        if ( *(_DWORD *)(v3 + 32) )
        {
          v15 = *(_WORD *)(v3 + 28);
          if ( (unsigned __int16)v15 >= 0xF8u )
            v15 = 248;
          *v14 = v15;
        }
        v16 = 514;
        break;
      default:
        goto LABEL_6;
    }
    *(_WORD *)(v8 + 12) |= v16;
    goto LABEL_27;
  }
  v9 = v7 + 6;
  v10 = v7[6];
  if ( *(_DWORD *)(a1 + 1952) == 1 )
  {
    *v9 = v10 | 0x202;
    *(_WORD *)(v8 + 10) = 0;
    *(_QWORD *)(a2 + 284) = 5;
  }
  else
  {
    *v9 = v10 | 0x10;
    if ( (int)LSetupPalette(a1, v8, (_DWORD *)a2, v6) < 1 )
      goto LABEL_6;
  }
LABEL_80:
  if ( (*(_BYTE *)v9 & 2) != 0 )
  {
    v36 = 0;
    v37 = 0;
    v38 = 4;
  }
  else
  {
    v37 = *(unsigned __int16 *)(v8 + 8);
    v36 = (ULONG *)(v8 + 32);
    v38 = 1;
  }
  Palette = EngCreatePalette(v38, v37, v36, 0, 0, 0);
  *(_QWORD *)(a2 + 296) = Palette;
  *(_QWORD *)(v8 + 24) = Palette;
  if ( !*(_QWORD *)(a2 + 296) )
  {
LABEL_6:
    v11 = *(void **)(v8 + 16);
    if ( v11 )
      LocalFree(v11);
    LocalFree((HLOCAL)v8);
    *(_QWORD *)(a1 + 4096) = 0;
    return 0;
  }
  *(_DWORD *)(v6 + 104) = *(unsigned __int16 *)(v8 + 8);
  v40 = *(_DWORD *)(*(_QWORD *)(a1 + 2936) + 344LL);
  if ( v40 )
  {
    v41 = *(_DWORD *)(a1 + 3944) < v40;
    goto LABEL_86;
  }
  v43 = *(_DWORD *)(a1 + 3944);
  if ( (*(_BYTE *)v9 & 0x10) == 0 )
  {
    if ( v43 < 300 || *(int *)(a1 + 3948) < 300 )
      return 1;
    v42 = *(_DWORD *)(*(_QWORD *)(a1 + 3984) + 24LL) == 0;
    goto LABEL_94;
  }
  if ( v43 >= 600 )
  {
    v41 = *(_DWORD *)(a1 + 3948) < 600;
LABEL_86:
    if ( !v41 )
    {
      v42 = *(_DWORD *)(*(_QWORD *)(a1 + 3984) + 24LL) == 0;
LABEL_94:
      if ( v42 )
        *(_DWORD *)a2 |= 0x10000000u;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180025248  mov     [rsp+arg_10], r8
0x18002524d  push    rbx
0x18002524e  push    rbp
0x18002524f  push    rsi
0x180025250  push    rdi
0x180025251  push    r12
0x180025253  push    r13
0x180025255  push    r14
0x180025257  push    r15
0x180025259  sub     rsp, 38h
0x18002525d  mov     rdi, [rcx+0F28h]
0x180025264  mov     r14, rdx
0x180025267  mov     rsi, rcx
0x18002526a  mov     edx, 420h; uBytes
0x18002526f  mov     ecx, 40h ; '@'; uFlags
0x180025274  mov     r15, r8
0x180025277  call    cs:__imp_LocalAlloc
0x18002527e  nop     dword ptr [rax+rax+00h]
0x180025283  mov     rbx, rax
0x180025286  test    rax, rax
0x180025289  jz      loc_18002532A
0x18002528f  mov     [rsi+1000h], rax
0x180025296  mov     edx, 4
0x18002529b  lea     r8d, [rdx-2]
0x18002529f  lea     ebp, [rdx-3]
0x1800252a2  lea     r13d, [rdx+0Ch]
0x1800252a6  test    rdi, rdi
0x1800252a9  jnz     loc_18002533E
0x1800252af  lea     rdi, [rax+0Ch]
0x1800252b3  movzx   eax, word ptr [rdi]
0x1800252b6  cmp     [rsi+7A0h], ebp
0x1800252bc  jnz     short loc_1800252DB
0x1800252be  or      ax, 202h
0x1800252c2  mov     [rdi], ax
0x1800252c5  xor     eax, eax
0x1800252c7  mov     [rbx+0Ah], ax
0x1800252cb  mov     qword ptr [r14+11Ch], 5
0x1800252d6  jmp     loc_180025654
0x1800252db  or      ax, r13w
0x1800252df  mov     r9, r15
0x1800252e2  mov     r8, r14
0x1800252e5  mov     [rdi], ax
0x1800252e8  mov     rdx, rbx
0x1800252eb  mov     rcx, rsi
0x1800252ee  call    LSetupPalette
0x1800252f3  cmp     eax, ebp
0x1800252f5  jge     loc_180025654
0x1800252fb  mov     rcx, [rbx+10h]; hMem
0x1800252ff  test    rcx, rcx
0x180025302  jz      short loc_180025310
0x180025304  call    cs:__imp_LocalFree
0x18002530b  nop     dword ptr [rax+rax+00h]
0x180025310  mov     rcx, rbx; hMem
0x180025313  call    cs:__imp_LocalFree
0x18002531a  nop     dword ptr [rax+rax+00h]
0x18002531f  mov     qword ptr [rsi+1000h], 0
0x18002532a  xor     eax, eax
0x18002532c  add     rsp, 38h
0x180025330  pop     r15
0x180025332  pop     r14
0x180025334  pop     r13
0x180025336  pop     r12
0x180025338  pop     rdi
0x180025339  pop     rsi
0x18002533a  pop     rbp
0x18002533b  pop     rbx
0x18002533c  retn
0x18002533e  mov     eax, [rdi+8]
0x180025341  cmp     [rdi+10h], eax
0x180025344  jz      short loc_1800253B6
0x180025346  cmp     [rdi+10h], edx
0x180025349  jnz     short loc_180025359
0x18002534b  cmp     eax, ebp
0x18002534d  jnz     short loc_180025359
0x18002534f  mov     eax, [rdi+4]
0x180025352  sub     eax, 3
0x180025355  cmp     eax, ebp
0x180025357  jbe     short loc_1800253B6
0x180025359  lea     r15, [rbx+0Ah]
0x18002535d  mov     [r15], bp
0x180025361  mov     ecx, [rdi+10h]
0x180025364  sub     ecx, ebp
0x180025366  jz      short loc_1800253A8
0x180025368  sub     ecx, 3
0x18002536b  jz      short loc_18002539D
0x18002536d  sub     ecx, edx
0x18002536f  jz      short loc_180025397
0x180025371  cmp     ecx, r13d
0x180025374  jnz     short loc_1800252FB
0x180025376  cmp     dword ptr [rdi+20h], 0
0x18002537a  jz      short loc_180025390
0x18002537c  movzx   eax, word ptr [rdi+1Ch]
0x180025380  mov     ecx, 0F8h
0x180025385  cmp     ax, cx
0x180025388  jb      short loc_18002538C
0x18002538a  mov     eax, ecx
0x18002538c  mov     [r15], ax
0x180025390  mov     ecx, 202h
0x180025395  jmp     short loc_1800253A2
0x180025397  or      [rbx+0Ch], dx
0x18002539b  jmp     short loc_1800253AD
0x18002539d  mov     ecx, 8
0x1800253a2  or      [rbx+0Ch], cx
0x1800253a6  jmp     short loc_1800253AD
0x1800253a8  or      [rbx+0Ch], r13w
0x1800253ad  lea     r12, [rdi+20h]
0x1800253b1  jmp     loc_180025511
0x1800253b6  lea     r12, [rdi+20h]
0x1800253ba  cmp     dword ptr [r12], 0
0x1800253bf  lea     r15, [rbx+0Ah]
0x1800253c3  jz      short loc_1800253CB
0x1800253c5  movzx   eax, word ptr [rdi+1Ch]
0x1800253c9  jmp     short loc_1800253CE
0x1800253cb  mov     eax, r8d
0x1800253ce  mov     [r15], ax
0x1800253d2  cmp     [rdi+18h], ebp
0x1800253d5  jnz     short loc_180025424
0x1800253d7  cmp     dword ptr [r12], 0
0x1800253dc  jz      short loc_180025424
0x1800253de  mov     r8, [rsi+7D0h]
0x1800253e5  mov     ecx, [r8+8]
0x1800253e9  mov     rax, [r8+68h]
0x1800253ed  mov     r9d, [rcx+rax+90h]
0x1800253f5  cmp     r9d, 0FFFFFFFFh
0x1800253f9  jz      loc_1800252FB
0x1800253ff  mov     rdx, [r8+60h]
0x180025403  mov     eax, [r8+10h]
0x180025407  imul    rcx, r9, 1Ch
0x18002540b  add     rdx, rax
0x18002540e  add     rdx, rcx
0x180025411  jz      loc_1800252FB
0x180025417  or      [rbx+0Ch], bp
0x18002541b  mov     edx, 4
0x180025420  lea     r8d, [rdx-2]
0x180025424  mov     eax, [rdi+4]
0x180025427  mov     ecx, 8
0x18002542c  cmp     eax, ebp
0x18002542e  jnz     loc_1800254C3
0x180025434  cmp     [rdi+8], ecx
0x180025437  jnz     short loc_180025458
0x180025439  cmp     [rdi+10h], ecx
0x18002543c  jnz     loc_180025511
0x180025442  cmp     dword ptr [rdi+1Ch], 100h
0x180025449  jb      loc_1800252FB
0x18002544f  or      [rbx+0Ch], dx
0x180025453  jmp     loc_180025511
0x180025458  cmp     dword ptr [rdi+8], 18h
0x18002545c  jnz     short loc_1800254A8
0x18002545e  cmp     dword ptr [rdi+10h], 18h
0x180025462  jnz     loc_180025511
0x180025468  test    dword ptr [rdi+1Ch], 0FFFFFFF8h
0x18002546f  jnz     short loc_18002547A
0x180025471  cmp     [rdi+1Ch], ebp
0x180025474  jnz     loc_1800252FB
0x18002547a  movzx   edx, word ptr [rbx+0Ch]
0x18002547e  or      dx, r8w
0x180025482  mov     [rbx+0Ch], dx
0x180025486  mov     eax, [rsi+7A0h]
0x18002548c  sub     eax, ebp
0x18002548e  cmp     eax, ebp
0x180025490  ja      short loc_180025511
0x180025492  or      dx, 202h
0x180025497  mov     [rbx+0Ch], dx
0x18002549b  mov     qword ptr [r14+11Ch], 5
0x1800254a6  jmp     short loc_180025511
0x1800254a8  cmp     [rdi+8], ebp
0x1800254ab  jnz     short loc_180025511
0x1800254ad  cmp     [rdi+10h], ebp
0x1800254b0  jnz     short loc_180025511
0x1800254b2  cmp     [rdi+1Ch], r8d
0x1800254b6  jb      loc_1800252FB
0x1800254bc  or      [rbx+0Ch], r13w
0x1800254c1  jmp     short loc_180025511
0x1800254c3  add     eax, 0FFFFFFFDh
0x1800254c6  cmp     eax, ebp
0x1800254c8  ja      short loc_1800254D3
0x1800254ca  cmp     [rdi+10h], ebp
0x1800254cd  jbe     short loc_1800254D3
0x1800254cf  or      [rbx+0Ch], cx
0x1800254d3  test    [rbx+0Ch], bpl
0x1800254d7  jz      short loc_180025511
0x1800254d9  cmp     [rdi+1Ch], ecx
0x1800254dc  jb      loc_1800252FB
0x1800254e2  cmp     [rdi+4], edx
0x1800254e5  jnb     loc_1800252FB
0x1800254eb  movzx   edx, word ptr [r15]
0x1800254ef  mov     ecx, 40h ; '@'; uFlags
0x1800254f4  shl     rdx, 2; uBytes
0x1800254f8  call    cs:__imp_LocalAlloc
0x1800254ff  nop     dword ptr [rax+rax+00h]
0x180025504  mov     [rbx+10h], rax
0x180025508  test    rax, rax
0x18002550b  jz      loc_1800252FB
0x180025511  mov     r9, [rsp+78h+arg_10]
0x180025519  mov     r8, r14
0x18002551c  mov     rdx, rbx
0x18002551f  mov     rcx, rsi
0x180025522  call    LSetupPalette
0x180025527  cmp     eax, ebp
0x180025529  jl      loc_1800252FB
0x18002552f  or      r11d, 0FFFFFFFFh
0x180025533  lea     r9, [rsi+7D0h]
0x18002553a  cmp     dword ptr [r12], 0
0x18002553f  jz      short loc_18002559A
0x180025541  mov     r8, [r9]
0x180025544  mov     ecx, [r8+8]
0x180025548  mov     rax, [r8+68h]
0x18002554c  mov     r10d, [rcx+rax+90h]
0x180025554  cmp     r10d, r11d
0x180025557  jz      short loc_180025572
0x180025559  mov     rdx, [r8+60h]
0x18002555d  mov     eax, [r8+10h]
0x180025561  imul    rcx, r10, 1Ch
0x180025565  add     rdx, rax
0x180025568  add     rdx, rcx
0x18002556b  jz      short loc_180025572
0x18002556d  bts     dword ptr [rsi+70h], 12h
0x180025572  movzx   ecx, word ptr [rbx+8]
0x180025576  cmp     [r15], cx
0x18002557a  ja      short loc_180025594
0x18002557c  movzx   eax, word ptr [rbx+0Ch]
0x180025580  bt      ax, 9
0x180025585  jb      short loc_180025594
0x180025587  or      ax, 20h
0x18002558b  mov     ecx, 0FFFFh
0x180025590  mov     [rbx+0Ch], ax
0x180025594  mov     [rbx+0Eh], cx
0x180025598  jmp     short loc_1800255A2
0x18002559a  movzx   eax, word ptr [rbx+8]
0x18002559e  mov     [r15], ax
0x1800255a2  lea     rdi, [rbx+0Ch]
0x1800255a6  movzx   r8d, word ptr [rdi]
0x1800255aa  or      r8w, 40h
0x1800255af  mov     [rdi], r8w
0x1800255b3  mov     rdx, [r9]
0x1800255b6  mov     ecx, [rdx+8]
0x1800255b9  mov     rax, [rdx+68h]
0x1800255bd  mov     r10d, [rcx+rax+88h]
0x1800255c5  cmp     r10d, r11d
0x1800255c8  jz      short loc_1800255EB
0x1800255ca  mov     eax, [rdx+10h]
0x1800255cd  imul    rcx, r10, 1Ch
0x1800255d1  add     rcx, rax
0x1800255d4  mov     rax, [rdx+60h]
0x1800255d8  add     rax, rcx
0x1800255db  jz      short loc_1800255EB
0x1800255dd  mov     eax, [rax+8]
0x1800255e0  cmp     eax, 3
0x1800255e3  jz      short loc_180025632
0x1800255e5  dec     eax
0x1800255e7  cmp     eax, ebp
0x1800255e9  jbe     short loc_18002561F
0x1800255eb  mov     rax, [rsi+0F20h]
0x1800255f2  cmp     [rax+10h], r11d
0x1800255f6  jz      short loc_180025632
0x1800255f8  mov     eax, [rax+10h]
0x1800255fb  imul    rcx, rax, 1Ch
0x1800255ff  mov     eax, [rdx+10h]
0x180025602  add     rcx, rax
0x180025605  add     rcx, [rdx+60h]
0x180025609  jz      short loc_180025632
0x18002560b  mov     ecx, [rcx+8]
0x18002560e  lea     eax, [rcx-4]
0x180025611  cmp     eax, 2
0x180025614  jbe     loc_1800252FB
0x18002561a  cmp     ecx, 3
0x18002561d  jz      short loc_180025632
0x18002561f  mov     eax, 0FFBFh
0x180025624  and     r8w, ax
0x180025628  or      r8w, 80h
0x18002562e  mov     [rdi], r8w
0x180025632  cmp     qword ptr [rbx+10h], 0
0x180025637  jz      short loc_18002564C
0x180025639  mov     rdx, rbx
0x18002563c  mov     rcx, rsi
0x18002563f  call    RMInitDevicePal
0x180025644  test    eax, eax
0x180025646  jz      loc_1800252FB
0x18002564c  mov     r15, [rsp+78h+arg_10]
0x180025654  xor     r9d, r9d; flRed
0x180025657  mov     [rsp+78h+flBlue], 0; flBlue
0x18002565f  test    byte ptr [rdi], 2
0x180025662  mov     [rsp+78h+flGreen], r9d; flGreen
0x180025667  jz      short loc_180025673
0x180025669  xor     r8d, r8d
0x18002566c  xor     edx, edx
0x18002566e  lea     ecx, [rdx+4]
0x180025671  jmp     short loc_18002567D
0x180025673  movzx   edx, word ptr [rbx+8]; cColors
0x180025677  lea     r8, [rbx+20h]; pulColors
0x18002567b  mov     ecx, ebp; iMode
0x18002567d  call    cs:__imp_EngCreatePalette
0x180025684  nop     dword ptr [rax+rax+00h]
0x180025689  mov     [r14+128h], rax
0x180025690  mov     [rbx+18h], rax
0x180025694  cmp     qword ptr [r14+128h], 0
0x18002569c  jz      loc_1800252FB
0x1800256a2  movzx   eax, word ptr [rbx+8]
0x1800256a6  mov     [r15+68h], eax
0x1800256aa  mov     rax, [rsi+0B78h]
  ... truncated ...
```
