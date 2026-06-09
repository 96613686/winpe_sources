# CheckBitmapSurface

- ea: `0x180016e6c`
- end: `0x18001735a`
- name: `CheckBitmapSurface`
- size: `1262`
- prototype: `unsigned __int64 __fastcall(SURFOBJ *, int *)`
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x180015620`
- `0x180016870`
- `0x180016e6c`
- `0x180017360`
- `0x18001ca08`
- `0x18001e5b0`
- `0x18002d1a0`
- `0x18002d470`
- `0x18002d7d0`
- `0x18002dad0`
- `0x180037e80`
- `0x180040a70`
- `0x18004b1a0`
- `0x18004b3c0`
- `0x18004b650`
- `0x18004b990`
- `0x18004bb90`
- `0x18004c170`
- `0x18004c4c0`
- `0x18004c770`
- `0x18005f960`
- `0x18005fae0`
- `0x18005fb90`
- `0x18005ff50`
- `0x180060060`

## callees

- `0x180016e6c`
- `0x1800487e0`
- `0x1800491dc`
- `0x18004ac30`
- `0x18004cc60`

## import_xrefs

- `GDI32!EngBitBlt` at `0x180017258`
- `GDI32!EngBitBlt` at `0x180017258`
- `GDI32!EngEraseSurface` at `0x180017116`
- `GDI32!EngEraseSurface` at `0x180017116`

## pseudocode

```c
unsigned __int64 __fastcall CheckBitmapSurface(SURFOBJ *a1, int *a2)
{
  DHPDEV dhpdev; // rbx
  int *v3; // r13
  SURFOBJ *v4; // r15
  unsigned __int64 result; // rax
  bool v6; // zf
  __int64 v7; // rbp
  __int64 lDelta; // r14
  char *pvBits; // r12
  int v10; // ecx
  int v11; // edi
  bool v12; // sf
  unsigned int v13; // esi
  int v14; // eax
  bool v15; // cc
  __int64 v16; // rsi
  unsigned int v17; // edi
  int v18; // ebp
  int v19; // edx
  unsigned int v20; // edi
  LONG v21; // r14d
  LONG v22; // r15d
  LONG v23; // r12d
  unsigned int v24; // ecx
  RECTL *prclTrg; // rsi
  int v26; // edi
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  ULONG *v29; // rax
  ULONG v30; // r8d
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned __int8 v41; // al
  LONG top; // r10d
  LONG bottom; // r9d
  LONG i; // r8d
  LONG v45; // eax
  LONG v46; // [rsp+60h] [rbp-78h]
  unsigned int v47; // [rsp+64h] [rbp-74h]
  RECTL prcl; // [rsp+78h] [rbp-60h] BYREF
  int v51; // [rsp+88h] [rbp-50h]

  dhpdev = a1->dhpdev;
  v3 = a2;
  v4 = a1;
  result = *((unsigned int *)dhpdev + 28);
  if ( (result & 0x20000000) == 0 )
  {
    if ( (result & 0x800000) == 0 )
    {
      v6 = *((_QWORD *)dhpdev + 219) == 0;
      *((_DWORD *)dhpdev + 28) = result | 0x800000;
      if ( v6 )
      {
        v29 = (ULONG *)*((_QWORD *)dhpdev + 512);
        prcl = 0;
        v30 = *v29;
        prcl.right = (int)dhpdev[493];
        prcl.bottom = (int)dhpdev[494];
        EngEraseSurface(a1, &prcl, v30);
        *((_DWORD *)dhpdev + 28) |= 0x2000000u;
      }
    }
    v7 = *((_QWORD *)dhpdev + 220);
    if ( v7 )
    {
      v20 = *((_DWORD *)dhpdev + 442);
      if ( v20 )
      {
        v21 = *((_DWORD *)dhpdev + 494);
        *((_QWORD *)dhpdev + 220) = 0;
        if ( v3 )
        {
          v31 = v3[1];
          v32 = v3[3];
          v33 = v3[2];
          if ( v31 <= v32 )
          {
            v31 = v3[3];
            v32 = v3[1];
          }
          v34 = *v3;
          v22 = 0;
          if ( v32 >= 0 )
            v22 = v32;
          v46 = *((_DWORD *)dhpdev + 493);
          if ( v31 <= v21 )
            v21 = v31;
          if ( v34 <= v33 )
          {
            v34 = v3[2];
            v33 = *v3;
          }
          v23 = 0;
          if ( v33 >= 0 )
            v23 = v33;
          if ( v34 <= *((_DWORD *)dhpdev + 493) )
            v46 = v34;
        }
        else
        {
          v22 = 0;
          v23 = 0;
          v46 = *((_DWORD *)dhpdev + 493);
        }
        v24 = 0;
        v47 = 0;
        do
        {
          if ( *(_DWORD *)(v7 + 16LL * v24 + 8) <= v23
            || (prclTrg = (RECTL *)(v7 + 16LL * v24), prclTrg->left >= v46)
            || prclTrg->bottom <= v22
            || prclTrg->top >= v21 )
          {
            v47 = ++v24;
          }
          else
          {
            if ( prclTrg->top < v22 && v20 < 0x100 )
            {
              v35 = 2LL * v20++;
              *(RECTL *)(v7 + 8 * v35) = *prclTrg;
              *(_DWORD *)(v7 + 8 * v35 + 12) = v22;
              prclTrg->top = v22;
            }
            if ( prclTrg->bottom > v21 && v20 < 0x100 )
            {
              v36 = 2LL * v20++;
              *(RECTL *)(v7 + 8 * v36) = *prclTrg;
              *(_DWORD *)(v7 + 8 * v36 + 4) = v21;
              prclTrg->bottom = v21;
            }
            if ( prclTrg->right > v46 && v20 < 0x100 )
            {
              v37 = 2LL * v20++;
              *(RECTL *)(v7 + 8 * v37) = *prclTrg;
              *(_DWORD *)(v7 + 8 * v37) = v46;
              prclTrg->right = v46;
            }
            if ( prclTrg->left < v23 && v20 < 0x100 )
            {
              v38 = 2LL * v20++;
              *(RECTL *)(v7 + 8 * v38) = *prclTrg;
              *(_DWORD *)(v7 + 8 * v38 + 8) = v23;
              prclTrg->left = v23;
            }
            CheckBitmapSurface(*((_QWORD *)dhpdev + 13), prclTrg);
            EngBitBlt(*((SURFOBJ **)dhpdev + 13), 0, 0, 0, 0, prclTrg, 0, 0, 0, 0, 0);
            v39 = *((_QWORD *)dhpdev + 250);
            v40 = *(unsigned int *)(*(unsigned int *)(v39 + 8) + *(_QWORD *)(v39 + 104) + 372LL);
            if ( (_DWORD)v40 != -1
              && 28 * v40 + *(unsigned int *)(v39 + 16) + *(_QWORD *)(v39 + 96)
              && ((_DWORD)dhpdev[28] & 0x80000) != 0 )
            {
              v41 = BGetMask(dhpdev, prclTrg);
              top = prclTrg->top;
              bottom = prclTrg->bottom;
              for ( i = top; i < bottom; ++i )
              {
                if ( (v41 & *(_BYTE *)(i + *((_QWORD *)dhpdev + 218))) != 0 )
                {
                  v45 = prclTrg->right - prclTrg->left;
                  prcl.left = prclTrg->left;
                  prcl.right = v45;
                  v51 = 1;
                  prcl.top = top;
                  prcl.bottom = bottom - top;
                  DrawPatternRect(dhpdev, &prcl);
                  break;
                }
              }
            }
            v24 = v47;
            *prclTrg = *(RECTL *)(v7 + 16LL * --v20);
          }
        }
        while ( v24 < v20 );
        v3 = a2;
        v4 = a1;
        *((_DWORD *)dhpdev + 442) = v20;
        *((_QWORD *)dhpdev + 220) = v7;
      }
    }
    result = *((unsigned int *)dhpdev + 28);
    if ( (result & 0x2000000) == 0 )
    {
      lDelta = v4->lDelta;
      pvBits = (char *)v4->pvBits;
      if ( v3 )
      {
        v10 = v3[3];
        v11 = v3[1];
        if ( v11 > v10 )
        {
          v13 = v3[3];
          if ( v10 < 0 )
            v13 = 0;
          v14 = *((_DWORD *)dhpdev + 494) - 1;
          v15 = v14 < v11;
        }
        else
        {
          v12 = v11 < 0;
          v13 = v3[1];
          v11 = v3[3];
          if ( v12 )
            v13 = 0;
          v14 = *((_DWORD *)dhpdev + 494) - 1;
          v15 = v14 < v10;
        }
        if ( v15 )
          v11 = v14;
      }
      else
      {
        v26 = *((_DWORD *)dhpdev + 494);
        v13 = 0;
        *((_DWORD *)dhpdev + 28) = result | 0x2000000;
        v11 = v26 - 1;
      }
      result = *((unsigned __int16 *)dhpdev + 1300);
      v16 = v13 >> 5;
      v17 = (unsigned int)v11 >> 5;
      if ( (_WORD)result == 4 )
      {
        LOBYTE(v18) = 119;
      }
      else if ( (_WORD)result == 8 )
      {
        result = *((_QWORD *)dhpdev + 512);
        v18 = *(_DWORD *)result;
      }
      else
      {
        LOBYTE(v18) = -1;
      }
      for ( ; (unsigned int)v16 <= v17; v16 = (unsigned int)(v16 + 1) )
      {
        result = *((_QWORD *)dhpdev + 219);
        if ( !*(_BYTE *)(v16 + result) )
        {
          *(_BYTE *)(v16 + result) = 1;
          v19 = *((_DWORD *)dhpdev + 494) - 32 * v16;
          if ( v19 > 32 )
            v19 = 32;
          result = 32LL * (unsigned int)v16;
          if ( result <= 0xFFFFFFFF && v19 >= 0 )
          {
            v27 = (unsigned int)(result + v19);
            if ( (unsigned int)v27 >= (unsigned int)result )
            {
              result = (unsigned int)lDelta;
              v28 = (unsigned int)lDelta * v27;
              if ( v28 <= 0xFFFFFFFF && (unsigned int)v28 <= v4->cjBits )
                result = (unsigned __int64)memset_0(
                                             &pvBits[32 * (unsigned int)v16 * lDelta],
                                             (unsigned __int8)v18,
                                             lDelta * v19);
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
0x180016e6c  mov     [rsp+arg_10], rbx
0x180016e71  push    rbp
0x180016e72  push    rsi
0x180016e73  push    rdi
0x180016e74  push    r12
0x180016e76  push    r13
0x180016e78  push    r14
0x180016e7a  push    r15
0x180016e7c  sub     rsp, 0A0h
0x180016e83  mov     rax, cs:__security_cookie
0x180016e8a  xor     rax, rsp
0x180016e8d  mov     [rsp+0D8h+var_48], rax
0x180016e95  mov     rbx, [rcx+10h]
0x180016e99  mov     r13, rdx
0x180016e9c  mov     [rsp+0D8h+var_70], rdx
0x180016ea1  mov     r15, rcx
0x180016ea4  mov     [rsp+0D8h+var_68], rcx
0x180016ea9  mov     eax, [rbx+70h]
0x180016eac  bt      eax, 1Dh
0x180016eb0  jb      loc_180016F76
0x180016eb6  mov     ecx, 800000h
0x180016ebb  mov     esi, 2000000h
0x180016ec0  test    ecx, eax
0x180016ec2  jnz     short loc_180016ED7
0x180016ec4  or      eax, ecx
0x180016ec6  cmp     qword ptr [rbx+6D8h], 0
0x180016ece  mov     [rbx+70h], eax
0x180016ed1  jz      loc_1800170E2
0x180016ed7  mov     rbp, [rbx+6E0h]
0x180016ede  mov     edx, 1
0x180016ee3  mov     r8d, 0FFFFFFFFh
0x180016ee9  test    rbp, rbp
0x180016eec  jnz     loc_180016FE1
0x180016ef2  mov     eax, [rbx+70h]
0x180016ef5  test    esi, eax
0x180016ef7  jnz     short loc_180016F76
0x180016ef9  movsxd  r14, dword ptr [r15+40h]
0x180016efd  mov     r12, [r15+30h]
0x180016f01  test    r13, r13
0x180016f04  jz      loc_180017086
0x180016f0a  mov     ecx, [r13+0Ch]
0x180016f0e  xor     eax, eax
0x180016f10  mov     edi, [r13+4]
0x180016f14  cmp     edi, ecx
0x180016f16  jg      loc_180017337
0x180016f1c  test    edi, edi
0x180016f1e  mov     esi, edi
0x180016f20  mov     edi, ecx
0x180016f22  cmovs   esi, eax
0x180016f25  mov     eax, [rbx+7B8h]
0x180016f2b  dec     eax
0x180016f2d  cmp     eax, ecx
0x180016f2f  cmovl   edi, eax
0x180016f32  movzx   eax, word ptr [rbx+0A28h]
0x180016f39  shr     esi, 5
0x180016f3c  shr     edi, 5
0x180016f3f  cmp     ax, 4
0x180016f43  jz      short loc_180016FAC
0x180016f45  cmp     ax, 8
0x180016f49  jz      short loc_180016FA1
0x180016f4b  mov     ebp, 0FFh
0x180016f50  cmp     esi, edi
0x180016f52  ja      short loc_180016F76
0x180016f54  mov     r13d, 20h ; ' '
0x180016f5a  mov     rax, [rbx+6D8h]
0x180016f61  mov     r9d, esi
0x180016f64  cmp     byte ptr [rsi+rax], 0
0x180016f68  jz      short loc_180016FB3
0x180016f6a  add     esi, edx
0x180016f6c  mov     r8d, 0FFFFFFFFh
0x180016f72  cmp     esi, edi
0x180016f74  jbe     short loc_180016F5A
0x180016f76  mov     rcx, [rsp+0D8h+var_48]
0x180016f7e  xor     rcx, rsp; StackCookie
0x180016f81  call    __security_check_cookie
0x180016f86  mov     rbx, [rsp+0D8h+arg_10]
0x180016f8e  add     rsp, 0A0h
0x180016f95  pop     r15
0x180016f97  pop     r14
0x180016f99  pop     r13
0x180016f9b  pop     r12
0x180016f9d  pop     rdi
0x180016f9e  pop     rsi
0x180016f9f  pop     rbp
0x180016fa0  retn
0x180016fa1  mov     rax, [rbx+1000h]
0x180016fa8  mov     ebp, [rax]
0x180016faa  jmp     short loc_180016F50
0x180016fac  mov     ebp, 77h ; 'w'
0x180016fb1  jmp     short loc_180016F50
0x180016fb3  mov     [rsi+rax], dl
0x180016fb6  mov     eax, esi
0x180016fb8  mov     edx, [rbx+7B8h]
0x180016fbe  shl     eax, 5
0x180016fc1  sub     edx, eax
0x180016fc3  mov     rax, r9
0x180016fc6  cmp     edx, r13d
0x180016fc9  cmovg   edx, r13d
0x180016fcd  shl     rax, 5
0x180016fd1  cmp     rax, r8
0x180016fd4  jbe     loc_18001734D
0x180016fda  mov     edx, 1
0x180016fdf  jmp     short loc_180016F6A
0x180016fe1  mov     edi, [rbx+6E8h]
0x180016fe7  test    edi, edi
0x180016fe9  jz      loc_180016EF2
0x180016fef  mov     r14d, [rbx+7B8h]
0x180016ff6  mov     qword ptr [rbx+6E0h], 0
0x180017001  test    r13, r13
0x180017004  jnz     loc_180017124
0x18001700a  mov     ecx, [rbx+7B4h]
0x180017010  xor     r15d, r15d
0x180017013  xor     r12d, r12d
0x180017016  mov     [rsp+0D8h+var_78], ecx
0x18001701a  test    edi, edi
0x18001701c  jz      short loc_180017069
0x18001701e  mov     r13d, [rsp+0D8h+var_78]
0x180017023  xor     ecx, ecx
0x180017025  mov     [rsp+0D8h+var_74], ecx
0x180017029  mov     r8d, 100h
0x18001702f  mov     eax, ecx
0x180017031  add     rax, rax
0x180017034  cmp     [rbp+rax*8+8], r12d
0x180017039  jle     short loc_180017055
0x18001703b  lea     rsi, ds:0[rax*8]
0x180017043  add     rsi, rbp
0x180017046  cmp     [rsi], r13d
0x180017049  jge     short loc_180017055
0x18001704b  cmp     [rsi+0Ch], r15d
0x18001704f  jg      loc_180017184
0x180017055  add     ecx, edx
0x180017057  mov     [rsp+0D8h+var_74], ecx
0x18001705b  cmp     ecx, edi
0x18001705d  jb      short loc_18001702F
0x18001705f  mov     r13, [rsp+0D8h+var_70]
0x180017064  mov     esi, 2000000h
0x180017069  mov     r15, [rsp+0D8h+var_68]
0x18001706e  mov     r8d, 0FFFFFFFFh
0x180017074  mov     [rbx+6E8h], edi
0x18001707a  mov     [rbx+6E0h], rbp
0x180017081  jmp     loc_180016EF2
0x180017086  mov     edi, [rbx+7B8h]
0x18001708c  or      eax, esi
0x18001708e  xor     esi, esi
0x180017090  mov     [rbx+70h], eax
0x180017093  sub     edi, edx
0x180017095  jmp     loc_180016F32
0x18001709a  lea     ecx, [rax+rdx]
0x18001709d  cmp     ecx, eax
0x18001709f  jb      loc_180016FDA
0x1800170a5  mov     eax, r14d
0x1800170a8  imul    rcx, rax
0x1800170ac  cmp     rcx, r8
0x1800170af  ja      loc_180016FDA
0x1800170b5  cmp     ecx, [r15+28h]
0x1800170b9  ja      loc_180016FDA
0x1800170bf  movsxd  r8, edx
0x1800170c2  mov     rcx, r14
0x1800170c5  imul    rcx, r9
0x1800170c9  imul    r8, r14; Size
0x1800170cd  shl     rcx, 5
0x1800170d1  add     rcx, r12; void *
0x1800170d4  movzx   edx, bpl; Val
0x1800170d8  call    memset_0
0x1800170dd  jmp     loc_180016FDA
0x1800170e2  mov     rax, [rbx+1000h]
0x1800170e9  lea     rdx, [rsp+0D8h+prcl]; prcl
0x1800170ee  xorps   xmm0, xmm0
0x1800170f1  mov     rcx, r15; pso
0x1800170f4  movups  xmmword ptr [rsp+0D8h+prcl.left], xmm0
0x1800170f9  mov     r8d, [rax]; iColor
0x1800170fc  mov     eax, [rbx+7B4h]
0x180017102  mov     [rsp+0D8h+prcl.right], eax
0x180017109  mov     eax, [rbx+7B8h]
0x18001710f  mov     [rsp+0D8h+prcl.bottom], eax
0x180017116  call    cs:__imp_EngEraseSurface
0x18001711c  or      [rbx+70h], esi
0x18001711f  jmp     loc_180016ED7
0x180017124  mov     eax, [r13+4]
0x180017128  mov     edx, eax
0x18001712a  mov     ecx, [r13+0Ch]
0x18001712e  cmp     eax, ecx
0x180017130  mov     r8d, [r13+8]
0x180017134  cmovle  edx, ecx
0x180017137  cmovle  ecx, eax
0x18001713a  mov     eax, [r13+0]
0x18001713e  xor     r15d, r15d
0x180017141  test    ecx, ecx
0x180017143  cmovns  r15d, ecx
0x180017147  mov     ecx, [rbx+7B4h]
0x18001714d  cmp     edx, r14d
0x180017150  mov     [rsp+0D8h+var_78], ecx
0x180017154  cmovle  r14d, edx
0x180017158  cmp     eax, r8d
0x18001715b  mov     edx, 1
0x180017160  cmovle  eax, r8d
0x180017164  cmovle  r8d, [r13+0]
0x180017169  xor     r12d, r12d
0x18001716c  test    r8d, r8d
0x18001716f  cmovns  r12d, r8d
0x180017173  cmp     eax, ecx
0x180017175  jg      loc_18001701A
0x18001717b  mov     [rsp+0D8h+var_78], eax
0x18001717f  jmp     loc_18001701A
0x180017184  cmp     [rsi+4], r14d
0x180017188  jge     loc_180017055
0x18001718e  cmp     [rsi+4], r15d
0x180017192  jge     short loc_1800171B2
0x180017194  cmp     edi, r8d
0x180017197  jnb     short loc_1800171B2
0x180017199  movups  xmm0, xmmword ptr [rsi]
0x18001719c  mov     eax, edi
0x18001719e  add     rax, rax
0x1800171a1  add     edi, edx
0x1800171a3  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800171a9  mov     [rbp+rax*8+0Ch], r15d
0x1800171ae  mov     [rsi+4], r15d
0x1800171b2  cmp     [rsi+0Ch], r14d
0x1800171b6  jle     short loc_1800171D6
0x1800171b8  cmp     edi, r8d
0x1800171bb  jnb     short loc_1800171D6
0x1800171bd  movups  xmm0, xmmword ptr [rsi]
0x1800171c0  mov     eax, edi
0x1800171c2  add     rax, rax
0x1800171c5  add     edi, edx
0x1800171c7  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800171cd  mov     [rbp+rax*8+4], r14d
0x1800171d2  mov     [rsi+0Ch], r14d
0x1800171d6  cmp     [rsi+8], r13d
0x1800171da  jle     short loc_1800171FA
0x1800171dc  cmp     edi, r8d
0x1800171df  jnb     short loc_1800171FA
0x1800171e1  movups  xmm0, xmmword ptr [rsi]
0x1800171e4  mov     eax, edi
0x1800171e6  add     rax, rax
0x1800171e9  add     edi, edx
0x1800171eb  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x1800171f1  mov     [rbp+rax*8+0], r13d
0x1800171f6  mov     [rsi+8], r13d
0x1800171fa  cmp     [rsi], r12d
0x1800171fd  jge     short loc_18001721C
0x1800171ff  cmp     edi, r8d
0x180017202  jnb     short loc_18001721C
0x180017204  movups  xmm0, xmmword ptr [rsi]
0x180017207  mov     eax, edi
0x180017209  add     rax, rax
0x18001720c  add     edi, edx
0x18001720e  movdqu  xmmword ptr [rbp+rax*8+0], xmm0
0x180017214  mov     [rbp+rax*8+8], r12d
0x180017219  mov     [rsi], r12d
0x18001721c  mov     rcx, [rbx+68h]
0x180017220  mov     rdx, rsi
0x180017223  call    CheckBitmapSurface
0x180017228  mov     rcx, [rbx+68h]; psoTrg
0x18001722c  xor     eax, eax
0x18001722e  mov     [rsp+0D8h+rop4], eax; rop4
0x180017232  xor     r9d, r9d; pco
0x180017235  mov     [rsp+0D8h+pptlBrush], rax; pptlBrush
0x18001723a  xor     r8d, r8d; psoMask
0x18001723d  mov     [rsp+0D8h+pbo], rax; pbo
0x180017242  xor     edx, edx; psoSrc
0x180017244  mov     [rsp+0D8h+pptlMask], rax; pptlMask
0x180017249  mov     [rsp+0D8h+pptlSrc], rax; pptlSrc
0x18001724e  mov     [rsp+0D8h+prclTrg], rsi; prclTrg
0x180017253  mov     [rsp+0D8h+pxlo], rax; pxlo
0x180017258  call    cs:__imp_EngBitBlt
0x18001725e  mov     r8, [rbx+7D0h]
0x180017265  mov     rax, [r8+68h]
0x180017269  mov     ecx, [r8+8]
0x18001726d  mov     r9d, [rcx+rax+174h]
0x180017275  mov     eax, 0FFFFFFFFh
0x18001727a  cmp     r9d, eax
0x18001727d  jz      loc_18001730C
0x180017283  mov     rdx, [r8+60h]
0x180017287  mov     eax, [r8+10h]
0x18001728b  imul    rcx, r9, 1Ch
0x18001728f  add     rdx, rax
0x180017292  add     rdx, rcx
0x180017295  jz      short loc_18001730C
0x180017297  test    dword ptr [rbx+70h], 80000h
0x18001729e  jz      short loc_18001730C
0x1800172a0  mov     rdx, rsi
0x1800172a3  mov     rcx, rbx
0x1800172a6  call    BGetMask
0x1800172ab  mov     r10d, [rsi+4]
0x1800172af  mov     r11d, 1
0x1800172b5  mov     r9d, [rsi+0Ch]
0x1800172b9  mov     r8d, r10d
0x1800172bc  cmp     r8d, r9d
0x1800172bf  jge     short loc_18001730C
0x1800172c1  mov     rcx, [rbx+6D0h]
0x1800172c8  movsxd  rdx, r8d
0x1800172cb  test    [rdx+rcx], al
0x1800172ce  jnz     short loc_1800172D5
0x1800172d0  add     r8d, r11d
0x1800172d3  jmp     short loc_1800172BC
0x1800172d5  mov     ecx, [rsi]
0x1800172d7  lea     rdx, [rsp+0D8h+prcl]
0x1800172dc  mov     eax, [rsi+8]
0x1800172df  sub     r9d, r10d
  ... truncated ...
```
