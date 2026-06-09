# CheckBitmapSurface

- ea: `0x180017148`
- end: `0x180017643`
- name: `CheckBitmapSurface`
- size: `1275`
- prototype: `unsigned __int64 __fastcall(SURFOBJ *, int *, __int64, __int64 bottom)`
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x180015880`
- `0x180016b20`
- `0x180017148`
- `0x180017650`
- `0x18001cda0`
- `0x18001e978`
- `0x18002da20`
- `0x18002dcf0`
- `0x18002e050`
- `0x18002e350`
- `0x1800388f0`
- `0x180041bf0`
- `0x18004c7a0`
- `0x18004c9d0`
- `0x18004cc70`
- `0x18004cfc0`
- `0x18004d1d0`
- `0x18004d7d0`
- `0x18004db20`
- `0x18004dde0`
- `0x180060da0`
- `0x180060f30`
- `0x180060fe0`
- `0x1800613d0`
- `0x1800614f0`

## callees

- `0x180017148`
- `0x180049d00`
- `0x18004a71c`
- `0x18004c238`
- `0x18004e2f0`

## import_xrefs

- `GDI32!EngBitBlt` at `0x18001753b`
- `GDI32!EngBitBlt` at `0x18001753b`
- `GDI32!EngEraseSurface` at `0x1800173f3`
- `GDI32!EngEraseSurface` at `0x1800173f3`

## pseudocode

```c
unsigned __int64 __fastcall CheckBitmapSurface(SURFOBJ *a1, int *a2, __int64 a3, __int64 bottom)
{
  DHPDEV dhpdev; // rbx
  int *v5; // r13
  SURFOBJ *v6; // r15
  unsigned __int64 result; // rax
  bool v8; // zf
  __int64 v9; // rbp
  __int64 lDelta; // r14
  char *pvBits; // r12
  int v12; // ecx
  int v13; // edi
  bool v14; // sf
  unsigned int v15; // esi
  int v16; // eax
  bool v17; // cc
  __int64 v18; // rsi
  unsigned int v19; // edi
  int v20; // ebp
  int v21; // edx
  unsigned int v22; // edi
  LONG v23; // r14d
  LONG v24; // r15d
  LONG v25; // r12d
  unsigned int v26; // ecx
  RECTL *prclTrg; // rsi
  int v28; // edi
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  ULONG *v31; // rax
  ULONG v32; // r8d
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  char v42; // al
  LONG top; // r10d
  int i; // r8d
  LONG v45; // eax
  LONG v46; // [rsp+60h] [rbp-78h]
  unsigned int v47; // [rsp+64h] [rbp-74h]
  RECTL prcl; // [rsp+78h] [rbp-60h] BYREF
  int v51; // [rsp+88h] [rbp-50h]

  dhpdev = a1->dhpdev;
  v5 = a2;
  v6 = a1;
  result = *((unsigned int *)dhpdev + 28);
  if ( (result & 0x20000000) == 0 )
  {
    if ( (result & 0x800000) == 0 )
    {
      v8 = *((_QWORD *)dhpdev + 219) == 0;
      *((_DWORD *)dhpdev + 28) = result | 0x800000;
      if ( v8 )
      {
        v31 = (ULONG *)*((_QWORD *)dhpdev + 512);
        prcl = 0;
        v32 = *v31;
        prcl.right = (int)dhpdev[493];
        prcl.bottom = (int)dhpdev[494];
        EngEraseSurface(a1, &prcl, v32);
        *((_DWORD *)dhpdev + 28) |= 0x2000000u;
      }
    }
    v9 = *((_QWORD *)dhpdev + 220);
    if ( v9 )
    {
      v22 = *((_DWORD *)dhpdev + 442);
      if ( v22 )
      {
        v23 = *((_DWORD *)dhpdev + 494);
        *((_QWORD *)dhpdev + 220) = 0;
        if ( v5 )
        {
          v33 = v5[1];
          v34 = v5[3];
          v35 = v5[2];
          if ( v33 <= v34 )
          {
            v33 = v5[3];
            v34 = v5[1];
          }
          v36 = *v5;
          v24 = 0;
          if ( v34 >= 0 )
            v24 = v34;
          v46 = *((_DWORD *)dhpdev + 493);
          if ( v33 <= v23 )
            v23 = v33;
          if ( v36 <= v35 )
          {
            v36 = v5[2];
            v35 = *v5;
          }
          v25 = 0;
          if ( v35 >= 0 )
            v25 = v35;
          if ( v36 <= *((_DWORD *)dhpdev + 493) )
            v46 = v36;
        }
        else
        {
          v24 = 0;
          v25 = 0;
          v46 = *((_DWORD *)dhpdev + 493);
        }
        v26 = 0;
        v47 = 0;
        do
        {
          if ( *(_DWORD *)(v9 + 16LL * v26 + 8) <= v25
            || (prclTrg = (RECTL *)(v9 + 16LL * v26), prclTrg->left >= v46)
            || prclTrg->bottom <= v24
            || prclTrg->top >= v23 )
          {
            v47 = ++v26;
          }
          else
          {
            if ( prclTrg->top < v24 && v22 < 0x100 )
            {
              v37 = 2LL * v22++;
              *(RECTL *)(v9 + 8 * v37) = *prclTrg;
              *(_DWORD *)(v9 + 8 * v37 + 12) = v24;
              prclTrg->top = v24;
            }
            if ( prclTrg->bottom > v23 && v22 < 0x100 )
            {
              v38 = 2LL * v22++;
              *(RECTL *)(v9 + 8 * v38) = *prclTrg;
              *(_DWORD *)(v9 + 8 * v38 + 4) = v23;
              prclTrg->bottom = v23;
            }
            if ( prclTrg->right > v46 && v22 < 0x100 )
            {
              v39 = 2LL * v22++;
              *(RECTL *)(v9 + 8 * v39) = *prclTrg;
              *(_DWORD *)(v9 + 8 * v39) = v46;
              prclTrg->right = v46;
            }
            if ( prclTrg->left < v25 && v22 < 0x100 )
            {
              v40 = 2LL * v22++;
              *(RECTL *)(v9 + 8 * v40) = *prclTrg;
              *(_DWORD *)(v9 + 8 * v40 + 8) = v25;
              prclTrg->left = v25;
            }
            CheckBitmapSurface(*((SURFOBJ **)dhpdev + 13), &prclTrg->left, 256, bottom);
            EngBitBlt(*((SURFOBJ **)dhpdev + 13), 0, 0, 0, 0, prclTrg, 0, 0, 0, 0, 0);
            v41 = *((_QWORD *)dhpdev + 250);
            bottom = *(unsigned int *)(*(unsigned int *)(v41 + 8) + *(_QWORD *)(v41 + 104) + 372LL);
            if ( (_DWORD)bottom != -1
              && 28 * bottom + *(unsigned int *)(v41 + 16) + *(_QWORD *)(v41 + 96)
              && ((_DWORD)dhpdev[28] & 0x80000) != 0 )
            {
              v42 = BGetMask((__int64)dhpdev, &prclTrg->left);
              top = prclTrg->top;
              bottom = (unsigned int)prclTrg->bottom;
              for ( i = top; i < (int)bottom; ++i )
              {
                if ( ((unsigned __int8)v42 & *(_BYTE *)(i + *((_QWORD *)dhpdev + 218))) != 0 )
                {
                  v45 = prclTrg->right - prclTrg->left;
                  prcl.left = prclTrg->left;
                  prcl.right = v45;
                  v51 = 1;
                  prcl.top = top;
                  prcl.bottom = bottom - top;
                  DrawPatternRect((__int64)dhpdev, (__int64)&prcl);
                  break;
                }
              }
            }
            v26 = v47;
            *prclTrg = *(RECTL *)(v9 + 16LL * --v22);
          }
        }
        while ( v26 < v22 );
        v5 = a2;
        v6 = a1;
        *((_DWORD *)dhpdev + 442) = v22;
        *((_QWORD *)dhpdev + 220) = v9;
      }
    }
    result = *((unsigned int *)dhpdev + 28);
    if ( (result & 0x2000000) == 0 )
    {
      lDelta = v6->lDelta;
      pvBits = (char *)v6->pvBits;
      if ( v5 )
      {
        v12 = v5[3];
        v13 = v5[1];
        if ( v13 > v12 )
        {
          v15 = v5[3];
          if ( v12 < 0 )
            v15 = 0;
          v16 = *((_DWORD *)dhpdev + 494) - 1;
          v17 = v16 < v13;
        }
        else
        {
          v14 = v13 < 0;
          v15 = v5[1];
          v13 = v5[3];
          if ( v14 )
            v15 = 0;
          v16 = *((_DWORD *)dhpdev + 494) - 1;
          v17 = v16 < v12;
        }
        if ( v17 )
          v13 = v16;
      }
      else
      {
        v28 = *((_DWORD *)dhpdev + 494);
        v15 = 0;
        *((_DWORD *)dhpdev + 28) = result | 0x2000000;
        v13 = v28 - 1;
      }
      result = *((unsigned __int16 *)dhpdev + 1300);
      v18 = v15 >> 5;
      v19 = (unsigned int)v13 >> 5;
      if ( (_WORD)result == 4 )
      {
        LOBYTE(v20) = 119;
      }
      else if ( (_WORD)result == 8 )
      {
        result = *((_QWORD *)dhpdev + 512);
        v20 = *(_DWORD *)result;
      }
      else
      {
        LOBYTE(v20) = -1;
      }
      for ( ; (unsigned int)v18 <= v19; v18 = (unsigned int)(v18 + 1) )
      {
        result = *((_QWORD *)dhpdev + 219);
        if ( !*(_BYTE *)(v18 + result) )
        {
          *(_BYTE *)(v18 + result) = 1;
          v21 = *((_DWORD *)dhpdev + 494) - 32 * v18;
          if ( v21 > 32 )
            v21 = 32;
          result = 32LL * (unsigned int)v18;
          if ( result <= 0xFFFFFFFF && v21 >= 0 )
          {
            v29 = (unsigned int)(result + v21);
            if ( (unsigned int)v29 >= (unsigned int)result )
            {
              result = (unsigned int)lDelta;
              v30 = (unsigned int)lDelta * v29;
              if ( v30 <= 0xFFFFFFFF && (unsigned int)v30 <= v6->cjBits )
                result = (unsigned __int64)memset_0(
                                             &pvBits[32 * (unsigned int)v18 * lDelta],
                                             (unsigned __int8)v20,
                                             lDelta * v21);
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017148  mov     [rsp+arg_10], rbx
0x18001714d  push    rbp
0x18001714e  push    rsi
0x18001714f  push    rdi
0x180017150  push    r12
0x180017152  push    r13
0x180017154  push    r14
0x180017156  push    r15
0x180017158  sub     rsp, 0A0h
0x18001715f  mov     rax, cs:__security_cookie
0x180017166  xor     rax, rsp
0x180017169  mov     [rsp+0D8h+var_48], rax
0x180017171  mov     rbx, [rcx+10h]
0x180017175  mov     r13, rdx
0x180017178  mov     [rsp+0D8h+var_70], rdx
0x18001717d  mov     r15, rcx
0x180017180  mov     [rsp+0D8h+var_68], rcx
0x180017185  mov     eax, [rbx+70h]
0x180017188  bt      eax, 1Dh
0x18001718c  jb      loc_180017252
0x180017192  mov     ecx, 800000h
0x180017197  mov     esi, 2000000h
0x18001719c  test    ecx, eax
0x18001719e  jnz     short loc_1800171B3
0x1800171a0  or      eax, ecx
0x1800171a2  cmp     qword ptr [rbx+6D8h], 0
0x1800171aa  mov     [rbx+70h], eax
0x1800171ad  jz      loc_1800173BF
0x1800171b3  mov     rbp, [rbx+6E0h]
0x1800171ba  mov     edx, 1
0x1800171bf  mov     r8d, 0FFFFFFFFh
0x1800171c5  test    rbp, rbp
0x1800171c8  jnz     loc_1800172BE
0x1800171ce  mov     eax, [rbx+70h]
0x1800171d1  test    esi, eax
0x1800171d3  jnz     short loc_180017252
0x1800171d5  movsxd  r14, dword ptr [r15+40h]
0x1800171d9  mov     r12, [r15+30h]
0x1800171dd  test    r13, r13
0x1800171e0  jz      loc_180017363
0x1800171e6  mov     ecx, [r13+0Ch]
0x1800171ea  xor     eax, eax
0x1800171ec  mov     edi, [r13+4]
0x1800171f0  cmp     edi, ecx
0x1800171f2  jg      loc_180017620
0x1800171f8  test    edi, edi
0x1800171fa  mov     esi, edi
0x1800171fc  mov     edi, ecx
0x1800171fe  cmovs   esi, eax
0x180017201  mov     eax, [rbx+7B8h]
0x180017207  dec     eax
0x180017209  cmp     eax, ecx
0x18001720b  cmovl   edi, eax
0x18001720e  movzx   eax, word ptr [rbx+0A28h]
0x180017215  shr     esi, 5
0x180017218  shr     edi, 5
0x18001721b  cmp     ax, 4
0x18001721f  jz      short loc_180017289
0x180017221  cmp     ax, 8
0x180017225  jz      short loc_18001727E
0x180017227  mov     ebp, 0FFh
0x18001722c  cmp     esi, edi
0x18001722e  ja      short loc_180017252
0x180017230  mov     r13d, 20h ; ' '
0x180017236  mov     rax, [rbx+6D8h]
0x18001723d  mov     r9d, esi
0x180017240  cmp     byte ptr [rsi+rax], 0
0x180017244  jz      short loc_180017290
0x180017246  add     esi, edx
0x180017248  mov     r8d, 0FFFFFFFFh
0x18001724e  cmp     esi, edi
0x180017250  jbe     short loc_180017236
0x180017252  mov     rcx, [rsp+0D8h+var_48]
0x18001725a  xor     rcx, rsp; StackCookie
0x18001725d  call    __security_check_cookie
0x180017262  mov     rbx, [rsp+0D8h+arg_10]
0x18001726a  add     rsp, 0A0h
0x180017271  pop     r15
0x180017273  pop     r14
0x180017275  pop     r13
0x180017277  pop     r12
0x180017279  pop     rdi
0x18001727a  pop     rsi
0x18001727b  pop     rbp
0x18001727c  retn
0x18001727e  mov     rax, [rbx+1000h]
0x180017285  mov     ebp, [rax]
0x180017287  jmp     short loc_18001722C
0x180017289  mov     ebp, 77h ; 'w'
0x18001728e  jmp     short loc_18001722C
0x180017290  mov     [rsi+rax], dl
0x180017293  mov     eax, esi
0x180017295  mov     edx, [rbx+7B8h]
0x18001729b  shl     eax, 5
0x18001729e  sub     edx, eax
0x1800172a0  mov     rax, r9
0x1800172a3  cmp     edx, r13d
0x1800172a6  cmovg   edx, r13d
0x1800172aa  shl     rax, 5
0x1800172ae  cmp     rax, r8
0x1800172b1  jbe     loc_180017636
0x1800172b7  mov     edx, 1
0x1800172bc  jmp     short loc_180017246
0x1800172be  mov     edi, [rbx+6E8h]
0x1800172c4  test    edi, edi
0x1800172c6  jz      loc_1800171CE
0x1800172cc  mov     r14d, [rbx+7B8h]
0x1800172d3  mov     qword ptr [rbx+6E0h], 0
0x1800172de  test    r13, r13
0x1800172e1  jnz     loc_180017407
0x1800172e7  mov     ecx, [rbx+7B4h]
0x1800172ed  xor     r15d, r15d
0x1800172f0  xor     r12d, r12d
0x1800172f3  mov     [rsp+0D8h+var_78], ecx
0x1800172f7  test    edi, edi
0x1800172f9  jz      short loc_180017346
0x1800172fb  mov     r13d, [rsp+0D8h+var_78]
0x180017300  xor     ecx, ecx
0x180017302  mov     [rsp+0D8h+var_74], ecx
0x180017306  mov     r8d, 100h
0x18001730c  mov     eax, ecx
0x18001730e  add     rax, rax
0x180017311  cmp     [rbp+rax*8+8], r12d
0x180017316  jle     short loc_180017332
0x180017318  lea     rsi, ds:0[rax*8]
0x180017320  add     rsi, rbp
0x180017323  cmp     [rsi], r13d
0x180017326  jge     short loc_180017332
0x180017328  cmp     [rsi+0Ch], r15d
0x18001732c  jg      loc_180017467
0x180017332  add     ecx, edx
0x180017334  mov     [rsp+0D8h+var_74], ecx
0x180017338  cmp     ecx, edi
0x18001733a  jb      short loc_18001730C
0x18001733c  mov     r13, [rsp+0D8h+var_70]
0x180017341  mov     esi, 2000000h
0x180017346  mov     r15, [rsp+0D8h+var_68]
0x18001734b  mov     r8d, 0FFFFFFFFh
0x180017351  mov     [rbx+6E8h], edi
0x180017357  mov     [rbx+6E0h], rbp
0x18001735e  jmp     loc_1800171CE
0x180017363  mov     edi, [rbx+7B8h]
0x180017369  or      eax, esi
0x18001736b  xor     esi, esi
0x18001736d  mov     [rbx+70h], eax
0x180017370  sub     edi, edx
0x180017372  jmp     loc_18001720E
0x180017377  lea     ecx, [rax+rdx]
0x18001737a  cmp     ecx, eax
0x18001737c  jb      loc_1800172B7
0x180017382  mov     eax, r14d
0x180017385  imul    rcx, rax
0x180017389  cmp     rcx, r8
0x18001738c  ja      loc_1800172B7
0x180017392  cmp     ecx, [r15+28h]
0x180017396  ja      loc_1800172B7
0x18001739c  movsxd  r8, edx
0x18001739f  mov     rcx, r14
0x1800173a2  imul    rcx, r9
0x1800173a6  imul    r8, r14; Size
0x1800173aa  shl     rcx, 5
0x1800173ae  add     rcx, r12; void *
0x1800173b1  movzx   edx, bpl; Val
0x1800173b5  call    memset_0
0x1800173ba  jmp     loc_1800172B7
0x1800173bf  mov     rax, [rbx+1000h]
0x1800173c6  lea     rdx, [rsp+0D8h+prcl]; prcl
0x1800173cb  xorps   xmm0, xmm0
0x1800173ce  mov     rcx, r15; pso
0x1800173d1  movups  xmmword ptr [rsp+0D8h+prcl.left], xmm0
0x1800173d6  mov     r8d, [rax]; iColor
0x1800173d9  mov     eax, [rbx+7B4h]
0x1800173df  mov     [rsp+0D8h+prcl.right], eax
0x1800173e6  mov     eax, [rbx+7B8h]
0x1800173ec  mov     [rsp+0D8h+prcl.bottom], eax
0x1800173f3  call    cs:__imp_EngEraseSurface
0x1800173fa  nop     dword ptr [rax+rax+00h]
0x1800173ff  or      [rbx+70h], esi
0x180017402  jmp     loc_1800171B3
0x180017407  mov     eax, [r13+4]
0x18001740b  mov     edx, eax
0x18001740d  mov     ecx, [r13+0Ch]
0x180017411  cmp     eax, ecx
0x180017413  mov     r8d, [r13+8]
0x180017417  cmovle  edx, ecx
0x18001741a  cmovle  ecx, eax
0x18001741d  mov     eax, [r13+0]
0x180017421  xor     r15d, r15d
0x180017424  test    ecx, ecx
0x180017426  cmovns  r15d, ecx
0x18001742a  mov     ecx, [rbx+7B4h]
0x180017430  cmp     edx, r14d
0x180017433  mov     [rsp+0D8h+var_78], ecx
0x180017437  cmovle  r14d, edx
0x18001743b  cmp     eax, r8d
0x18001743e  mov     edx, 1
0x180017443  cmovle  eax, r8d
0x180017447  cmovle  r8d, [r13+0]
0x18001744c  xor     r12d, r12d
0x18001744f  test    r8d, r8d
0x180017452  cmovns  r12d, r8d
0x180017456  cmp     eax, ecx
0x180017458  jg      loc_1800172F7
0x18001745e  mov     [rsp+0D8h+var_78], eax
0x180017462  jmp     loc_1800172F7
0x180017467  cmp     [rsi+4], r14d
0x18001746b  jge     loc_180017332
0x180017471  cmp     [rsi+4], r15d
0x180017475  jge     short loc_180017495
0x180017477  cmp     edi, r8d
0x18001747a  jnb     short loc_180017495
0x18001747c  movups  xmm0, xmmword ptr [rsi]
0x18001747f  mov     eax, edi
0x180017481  add     rax, rax
0x180017484  add     edi, edx
0x180017486  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x18001748c  mov     [rbp+rax*8+0Ch], r15d
0x180017491  mov     [rsi+4], r15d
0x180017495  cmp     [rsi+0Ch], r14d
0x180017499  jle     short loc_1800174B9
0x18001749b  cmp     edi, r8d
0x18001749e  jnb     short loc_1800174B9
0x1800174a0  movups  xmm0, xmmword ptr [rsi]
0x1800174a3  mov     eax, edi
0x1800174a5  add     rax, rax
0x1800174a8  add     edi, edx
0x1800174aa  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800174b0  mov     [rbp+rax*8+4], r14d
0x1800174b5  mov     [rsi+0Ch], r14d
0x1800174b9  cmp     [rsi+8], r13d
0x1800174bd  jle     short loc_1800174DD
0x1800174bf  cmp     edi, r8d
0x1800174c2  jnb     short loc_1800174DD
0x1800174c4  movups  xmm0, xmmword ptr [rsi]
0x1800174c7  mov     eax, edi
0x1800174c9  add     rax, rax
0x1800174cc  add     edi, edx
0x1800174ce  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800174d4  mov     [rbp+rax*8+0], r13d
0x1800174d9  mov     [rsi+8], r13d
0x1800174dd  cmp     [rsi], r12d
0x1800174e0  jge     short loc_1800174FF
0x1800174e2  cmp     edi, r8d
0x1800174e5  jnb     short loc_1800174FF
0x1800174e7  movups  xmm0, xmmword ptr [rsi]
0x1800174ea  mov     eax, edi
0x1800174ec  add     rax, rax
0x1800174ef  add     edi, edx
0x1800174f1  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800174f7  mov     [rbp+rax*8+8], r12d
0x1800174fc  mov     [rsi], r12d
0x1800174ff  mov     rcx, [rbx+68h]
0x180017503  mov     rdx, rsi
0x180017506  call    CheckBitmapSurface
0x18001750b  mov     rcx, [rbx+68h]; psoTrg
0x18001750f  xor     eax, eax
0x180017511  mov     [rsp+0D8h+rop4], eax; rop4
0x180017515  xor     r9d, r9d; pco
0x180017518  mov     [rsp+0D8h+pptlBrush], rax; pptlBrush
0x18001751d  xor     r8d, r8d; psoMask
0x180017520  mov     [rsp+0D8h+pbo], rax; pbo
0x180017525  xor     edx, edx; psoSrc
0x180017527  mov     [rsp+0D8h+pptlMask], rax; pptlMask
0x18001752c  mov     [rsp+0D8h+pptlSrc], rax; pptlSrc
0x180017531  mov     [rsp+0D8h+prclTrg], rsi; prclTrg
0x180017536  mov     [rsp+0D8h+pxlo], rax; pxlo
0x18001753b  call    cs:__imp_EngBitBlt
0x180017542  nop     dword ptr [rax+rax+00h]
0x180017547  mov     r8, [rbx+7D0h]
0x18001754e  mov     rax, [r8+68h]
0x180017552  mov     ecx, [r8+8]
0x180017556  mov     r9d, [rcx+rax+174h]
0x18001755e  mov     eax, 0FFFFFFFFh
0x180017563  cmp     r9d, eax
0x180017566  jz      loc_1800175F5
0x18001756c  mov     rdx, [r8+60h]
0x180017570  mov     eax, [r8+10h]
0x180017574  imul    rcx, r9, 1Ch
0x180017578  add     rdx, rax
0x18001757b  add     rdx, rcx
0x18001757e  jz      short loc_1800175F5
0x180017580  test    dword ptr [rbx+70h], 80000h
0x180017587  jz      short loc_1800175F5
0x180017589  mov     rdx, rsi
0x18001758c  mov     rcx, rbx
0x18001758f  call    BGetMask
0x180017594  mov     r10d, [rsi+4]
0x180017598  mov     r11d, 1
0x18001759e  mov     r9d, [rsi+0Ch]
0x1800175a2  mov     r8d, r10d
0x1800175a5  cmp     r8d, r9d
0x1800175a8  jge     short loc_1800175F5
0x1800175aa  mov     rcx, [rbx+6D0h]
0x1800175b1  movsxd  rdx, r8d
0x1800175b4  test    [rdx+rcx], al
0x1800175b7  jnz     short loc_1800175BE
0x1800175b9  add     r8d, r11d
0x1800175bc  jmp     short loc_1800175A5
0x1800175be  mov     ecx, [rsi]
0x1800175c0  lea     rdx, [rsp+0D8h+prcl]
  ... truncated ...
```
