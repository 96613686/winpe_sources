# DrvStrokePath

- ea: `0x18002e050`
- end: `0x18002e349`
- name: `DrvStrokePath`
- size: `761`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, LINEATTRS *plineattrs, MIX mix)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180017148`
- `0x18002e050`
- `0x18002e5c8`
- `0x18004e06c`
- `0x180077010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e336`
- `KERNEL32!SetLastError` at `0x18002e336`
- `GDI32!EngStrokePath` at `0x18002e319`
- `GDI32!EngStrokePath` at `0x18002e319`

## pseudocode

```c
BOOL __stdcall DrvStrokePath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        LINEATTRS *plineattrs,
        MIX mix)
{
  DHPDEV dhpdev; // rdi
  SURFOBJ *v9; // rsi
  int v10; // ecx
  int v14; // eax
  __int64 v15; // r10
  __int64 v16; // r10
  int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // rbx
  BOOL result; // eax
  int v21; // ebx

  dhpdev = pso->dhpdev;
  v9 = pso;
  v10 = 0;
  if ( dhpdev
    && dhpdev == *((DHPDEV *)dhpdev + 8)
    && dhpdev == *((DHPDEV *)dhpdev + 553)
    && *((_DWORD *)dhpdev + 18) == 1919968374 )
  {
    v14 = *((_DWORD *)dhpdev + 29);
    if ( *((_QWORD *)dhpdev + 13) )
      v9 = (SURFOBJ *)*((_QWORD *)dhpdev + 13);
    if ( (v14 & 0x40000) != 0 )
    {
      CheckDrawingExtent((__int64)v9, &pco->rclBounds.left, 2);
      v14 = *((_DWORD *)dhpdev + 29);
      if ( (v14 & 0x80000) == 0 )
        return 1;
      v10 = 0;
    }
    v15 = *((_QWORD *)dhpdev + 237);
    if ( v15 )
    {
      if ( *(_QWORD *)(v15 + 176) )
      {
        v21 = *((_DWORD *)dhpdev + 476);
        if ( v21 != 11 )
        {
          *((_DWORD *)dhpdev + 476) = 11;
          *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v15 + 184) + 32LL);
          *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v15 + 184) + 40LL);
          *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v15 + 184) + 56LL);
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, XFORMOBJ *, BRUSHOBJ *, POINTL *, LINEATTRS *, MIX))(v15 + 176))(
                     v9,
                     ppo,
                     pco,
                     pxo,
                     pbo,
                     pptlBrushOrg,
                     plineattrs,
                     mix);
          *((_DWORD *)dhpdev + 476) = v21;
          return result;
        }
      }
    }
    v16 = *((_QWORD *)dhpdev + 523);
    if ( v16 )
    {
      if ( *(_QWORD *)(v16 + 288) )
      {
        v17 = *((_DWORD *)dhpdev + 1048);
        if ( v17 != 11 )
        {
          v18 = *((_QWORD *)dhpdev + 522);
          v19 = *((_QWORD *)dhpdev + 1);
          *((_DWORD *)dhpdev + 1048) = 11;
          *((_QWORD *)dhpdev + 1) = v18;
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, XFORMOBJ *, BRUSHOBJ *, POINTL *, LINEATTRS *, MIX))(v16 + 288))(
                     v9,
                     ppo,
                     pco,
                     pxo,
                     pbo,
                     pptlBrushOrg,
                     plineattrs,
                     mix);
          *((_DWORD *)dhpdev + 1048) = v17;
          *((_QWORD *)dhpdev + 1) = v19;
          return result;
        }
      }
    }
    if ( (v14 & 0x40000) != 0 )
      return 1;
    if ( ((_DWORD)dhpdev[28] & 0x20000000) == 0 )
    {
      if ( ppo->cCurves != 4
        || ppo->fl
        || !*((_QWORD *)dhpdev + 220)
        || *((_DWORD *)dhpdev + 442) >= 0xFCu
        || mix != 3341
        || !pbo
        || pco && pco->iDComplexity == 3 )
      {
        goto LABEL_33;
      }
      if ( v9->iBitmapFormat != 5 )
        v10 = *(_DWORD *)(*((_QWORD *)dhpdev + 512) + 4LL);
      if ( pbo->iSolidColor != v10
        || (plineattrs->fl & 0xB) != 0
        || !(unsigned int)TestStrokeRectangle((__int64)dhpdev, ppo, (__int64)pco, plineattrs->elWidth.l) )
      {
LABEL_33:
        CheckBitmapSurface(
          v9,
          (int *)((unsigned __int64)&pco->rclBounds & ((unsigned __int128)-(__int128)(unsigned __int64)pco >> 64)),
          (__int64)pco,
          (__int64)pxo);
        return EngStrokePath(v9, ppo, pco, pxo, pbo, pptlBrushOrg, plineattrs, mix);
      }
      return 1;
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e050  push    rbx
0x18002e052  push    rbp
0x18002e053  push    rsi
0x18002e054  push    rdi
0x18002e055  push    r12
0x18002e057  push    r13
0x18002e059  push    r14
0x18002e05b  push    r15
0x18002e05d  sub     rsp, 58h
0x18002e061  mov     rdi, [rcx+10h]
0x18002e065  mov     rsi, rcx
0x18002e068  xor     ecx, ecx
0x18002e06a  mov     r13, r9
0x18002e06d  mov     rbp, r8
0x18002e070  mov     r14, rdx
0x18002e073  test    rdi, rdi
0x18002e076  jz      loc_18002E331
0x18002e07c  cmp     rdi, [rdi+40h]
0x18002e080  jnz     loc_18002E331
0x18002e086  cmp     rdi, [rdi+1148h]
0x18002e08d  jnz     loc_18002E331
0x18002e093  cmp     dword ptr [rdi+48h], 72706476h
0x18002e09a  jnz     loc_18002E331
0x18002e0a0  cmp     [rdi+68h], rcx
0x18002e0a4  mov     eax, [rdi+74h]
0x18002e0a7  cmovnz  rsi, [rdi+68h]
0x18002e0ac  bt      eax, 12h
0x18002e0b0  jb      loc_18002E174
0x18002e0b6  mov     r10, [rdi+768h]
0x18002e0bd  mov     edx, 0Bh
0x18002e0c2  test    r10, r10
0x18002e0c5  jnz     loc_18002E19A
0x18002e0cb  mov     r10, [rdi+1058h]
0x18002e0d2  test    r10, r10
0x18002e0d5  jz      loc_18002E23D
0x18002e0db  cmp     [r10+120h], rcx
0x18002e0e2  jz      loc_18002E23D
0x18002e0e8  mov     r15d, [rdi+1060h]
0x18002e0ef  cmp     r15d, edx
0x18002e0f2  jz      loc_18002E23D
0x18002e0f8  mov     rax, [rdi+1050h]
0x18002e0ff  mov     r9, r13
0x18002e102  mov     ecx, [rsp+98h+mix]
0x18002e109  mov     r8, rbp
0x18002e10c  mov     rbx, [rdi+8]
0x18002e110  mov     [rsp+98h+var_60], ecx
0x18002e114  mov     rcx, [rsp+98h+plineattrs]
0x18002e11c  mov     [rsp+98h+var_68], rcx
0x18002e121  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18002e129  mov     [rsp+98h+var_70], rcx
0x18002e12e  mov     rcx, [rsp+98h+pbo]
0x18002e136  mov     [rdi+1060h], edx
0x18002e13c  mov     rdx, r14
0x18002e13f  mov     [rsp+98h+var_78], rcx
0x18002e144  mov     rcx, rsi
0x18002e147  mov     [rdi+8], rax
0x18002e14b  mov     rax, [r10+120h]
0x18002e152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e157  mov     [rdi+1060h], r15d
0x18002e15e  mov     [rdi+8], rbx
0x18002e162  add     rsp, 58h
0x18002e166  pop     r15
0x18002e168  pop     r14
0x18002e16a  pop     r13
0x18002e16c  pop     r12
0x18002e16e  pop     rdi
0x18002e16f  pop     rsi
0x18002e170  pop     rbp
0x18002e171  pop     rbx
0x18002e172  retn
0x18002e174  lea     rdx, [r8+4]
0x18002e178  mov     rcx, rsi
0x18002e17b  mov     r8d, 2
0x18002e181  call    CheckDrawingExtent
0x18002e186  mov     eax, [rdi+74h]
0x18002e189  bt      eax, 13h
0x18002e18d  jb      loc_18002E32A
0x18002e193  mov     eax, 1
0x18002e198  jmp     short loc_18002E162
0x18002e19a  cmp     [r10+0B0h], rcx
0x18002e1a1  jz      loc_18002E0CB
0x18002e1a7  mov     ebx, [rdi+770h]
0x18002e1ad  cmp     ebx, edx
0x18002e1af  jz      loc_18002E0CB
0x18002e1b5  mov     [rdi+770h], edx
0x18002e1bb  mov     r9, r13
0x18002e1be  mov     rax, [r10+0B8h]
0x18002e1c5  mov     r8, rbp
0x18002e1c8  mov     rdx, r14
0x18002e1cb  mov     rcx, [rax+20h]
0x18002e1cf  mov     [rdi+20h], rcx
0x18002e1d3  mov     rax, [r10+0B8h]
0x18002e1da  mov     rcx, [rax+28h]
0x18002e1de  mov     [rdi+8], rcx
0x18002e1e2  mov     rax, [r10+0B8h]
0x18002e1e9  mov     rcx, [rax+38h]
0x18002e1ed  mov     [rdi+30h], rcx
0x18002e1f1  mov     ecx, [rsp+98h+mix]
0x18002e1f8  mov     rax, [r10+0B0h]
0x18002e1ff  mov     [rsp+98h+var_60], ecx
0x18002e203  mov     rcx, [rsp+98h+plineattrs]
0x18002e20b  mov     [rsp+98h+var_68], rcx
0x18002e210  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18002e218  mov     [rsp+98h+var_70], rcx
0x18002e21d  mov     rcx, [rsp+98h+pbo]
0x18002e225  mov     [rsp+98h+var_78], rcx
0x18002e22a  mov     rcx, rsi
0x18002e22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e232  mov     [rdi+770h], ebx
0x18002e238  jmp     loc_18002E162
0x18002e23d  bt      eax, 12h
0x18002e241  jb      loc_18002E193
0x18002e247  test    dword ptr [rdi+70h], 20000000h
0x18002e24e  jnz     loc_18002E342
0x18002e254  cmp     dword ptr [r14+4], 4
0x18002e259  mov     r12d, [rsp+98h+mix]
0x18002e261  mov     r15, [rsp+98h+plineattrs]
0x18002e269  mov     rbx, [rsp+98h+pbo]
0x18002e271  jnz     short loc_18002E2D9
0x18002e273  cmp     [r14], ecx
0x18002e276  jnz     short loc_18002E2D9
0x18002e278  cmp     [rdi+6E0h], rcx
0x18002e27f  jz      short loc_18002E2D9
0x18002e281  cmp     dword ptr [rdi+6E8h], 0FCh
0x18002e28b  jnb     short loc_18002E2D9
0x18002e28d  cmp     r12d, 0D0Dh
0x18002e294  jnz     short loc_18002E2D9
0x18002e296  test    rbx, rbx
0x18002e299  jz      short loc_18002E2D9
0x18002e29b  test    rbp, rbp
0x18002e29e  jz      short loc_18002E2A6
0x18002e2a0  cmp     byte ptr [rbp+14h], 3
0x18002e2a4  jz      short loc_18002E2D9
0x18002e2a6  cmp     dword ptr [rsi+48h], 5
0x18002e2aa  jz      short loc_18002E2B6
0x18002e2ac  mov     rax, [rdi+1000h]
0x18002e2b3  mov     ecx, [rax+4]
0x18002e2b6  cmp     [rbx], ecx
0x18002e2b8  jnz     short loc_18002E2D9
0x18002e2ba  test    [r15], dl
0x18002e2bd  jnz     short loc_18002E2D9
0x18002e2bf  mov     r9d, [r15+0Ch]
0x18002e2c3  mov     r8, rbp
0x18002e2c6  mov     rdx, r14
0x18002e2c9  mov     rcx, rdi
0x18002e2cc  call    TestStrokeRectangle
0x18002e2d1  test    eax, eax
0x18002e2d3  jnz     loc_18002E193
0x18002e2d9  lea     rcx, [rbp+4]
0x18002e2dd  mov     rax, rbp
0x18002e2e0  neg     rax
0x18002e2e3  sbb     rdx, rdx
0x18002e2e6  and     rdx, rcx
0x18002e2e9  mov     rcx, rsi
0x18002e2ec  call    CheckBitmapSurface
0x18002e2f1  mov     rax, [rsp+98h+pptlBrushOrg]
0x18002e2f9  mov     r9, r13; pxo
0x18002e2fc  mov     [rsp+98h+var_60], r12d; mix
0x18002e301  mov     r8, rbp; pco
0x18002e304  mov     [rsp+98h+var_68], r15; plineattrs
0x18002e309  mov     rdx, r14; ppo
0x18002e30c  mov     [rsp+98h+var_70], rax; pptlBrushOrg
0x18002e311  mov     rcx, rsi; pso
0x18002e314  mov     [rsp+98h+var_78], rbx; pbo
0x18002e319  call    cs:__imp_EngStrokePath
0x18002e320  nop     dword ptr [rax+rax+00h]
0x18002e325  jmp     loc_18002E162
0x18002e32a  xor     ecx, ecx
0x18002e32c  jmp     loc_18002E0B6
0x18002e331  mov     ecx, 57h ; 'W'; dwErrCode
0x18002e336  call    cs:__imp_SetLastError
0x18002e33d  nop     dword ptr [rax+rax+00h]
0x18002e342  xor     eax, eax
0x18002e344  jmp     loc_18002E162
```
