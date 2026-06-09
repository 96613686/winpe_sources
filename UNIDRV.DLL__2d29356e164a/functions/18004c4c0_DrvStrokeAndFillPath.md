# DrvStrokeAndFillPath

- ea: `0x18004c4c0`
- end: `0x18004c766`
- name: `DrvStrokeAndFillPath`
- size: `678`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pboStroke, LINEATTRS *plineattrs, BRUSHOBJ *pboFill, POINTL *pptlBrushOrg, MIX mixFill, FLONG flOptions)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016e6c`
- `0x18002dd38`
- `0x18004c4c0`
- `0x180075010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18004c74f`
- `KERNEL32!SetLastError` at `0x18004c74f`
- `GDI32!EngStrokeAndFillPath` at `0x18004c742`
- `GDI32!EngStrokeAndFillPath` at `0x18004c742`

## pseudocode

```c
BOOL __stdcall DrvStrokeAndFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pboStroke,
        LINEATTRS *plineattrs,
        BRUSHOBJ *pboFill,
        POINTL *pptlBrushOrg,
        MIX mixFill,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rdi
  SURFOBJ *v14; // rsi
  int v15; // eax
  __int64 v16; // r10
  int v17; // r14d
  BOOL result; // eax
  __int64 v19; // r10
  int v20; // r14d
  __int64 v21; // rax
  __int64 v22; // rbx

  dhpdev = pso->dhpdev;
  v14 = pso;
  if ( dhpdev
    && dhpdev == *((DHPDEV *)dhpdev + 8)
    && dhpdev == *((DHPDEV *)dhpdev + 553)
    && *((_DWORD *)dhpdev + 18) == 1919968374 )
  {
    v15 = *((_DWORD *)dhpdev + 29);
    if ( *((_QWORD *)dhpdev + 13) )
      v14 = (SURFOBJ *)*((_QWORD *)dhpdev + 13);
    if ( (v15 & 0x40000) != 0 )
    {
      CheckDrawingExtent((__int64)v14, &pco->rclBounds.left, 6);
      v15 = *((_DWORD *)dhpdev + 29);
      if ( (v15 & 0x80000) == 0 )
        return 1;
    }
    v16 = *((_QWORD *)dhpdev + 237);
    if ( v16 )
    {
      if ( *(_QWORD *)(v16 + 208) )
      {
        v17 = *((_DWORD *)dhpdev + 476);
        if ( v17 != 13 )
        {
          *((_DWORD *)dhpdev + 476) = 13;
          *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v16 + 216) + 32LL);
          *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v16 + 216) + 40LL);
          *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v16 + 216) + 56LL);
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, XFORMOBJ *, BRUSHOBJ *, LINEATTRS *, BRUSHOBJ *, POINTL *, MIX, FLONG))(v16 + 208))(
                     v14,
                     ppo,
                     pco,
                     pxo,
                     pboStroke,
                     plineattrs,
                     pboFill,
                     pptlBrushOrg,
                     mixFill,
                     flOptions);
          *((_DWORD *)dhpdev + 476) = v17;
          return result;
        }
      }
    }
    v19 = *((_QWORD *)dhpdev + 523);
    if ( v19 )
    {
      if ( *(_QWORD *)(v19 + 304) )
      {
        v20 = *((_DWORD *)dhpdev + 1048);
        if ( v20 != 13 )
        {
          v21 = *((_QWORD *)dhpdev + 522);
          v22 = *((_QWORD *)dhpdev + 1);
          *((_DWORD *)dhpdev + 1048) = 13;
          *((_QWORD *)dhpdev + 1) = v21;
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, XFORMOBJ *, BRUSHOBJ *, LINEATTRS *, BRUSHOBJ *, POINTL *, MIX, FLONG))(v19 + 304))(
                     v14,
                     ppo,
                     pco,
                     pxo,
                     pboStroke,
                     plineattrs,
                     pboFill,
                     pptlBrushOrg,
                     mixFill,
                     flOptions);
          *((_DWORD *)dhpdev + 1048) = v20;
          *((_QWORD *)dhpdev + 1) = v22;
          return result;
        }
      }
    }
    if ( (v15 & 0x40000) != 0 )
      return 1;
    if ( ((_DWORD)dhpdev[28] & 0x20000000) == 0 )
    {
      CheckBitmapSurface(v14, &pco->rclBounds.left);
      return EngStrokeAndFillPath(v14, ppo, pco, pxo, pboStroke, plineattrs, pboFill, pptlBrushOrg, mixFill, flOptions);
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
0x18004c4c0  push    rbx
0x18004c4c2  push    rbp
0x18004c4c3  push    rsi
0x18004c4c4  push    rdi
0x18004c4c5  push    r12
0x18004c4c7  push    r14
0x18004c4c9  push    r15
0x18004c4cb  sub     rsp, 60h
0x18004c4cf  mov     rdi, [rcx+10h]
0x18004c4d3  mov     r15, r9
0x18004c4d6  mov     rbp, r8
0x18004c4d9  mov     r12, rdx
0x18004c4dc  mov     rsi, rcx
0x18004c4df  test    rdi, rdi
0x18004c4e2  jz      loc_18004C74A
0x18004c4e8  cmp     rdi, [rdi+40h]
0x18004c4ec  jnz     loc_18004C74A
0x18004c4f2  cmp     rdi, [rdi+1148h]
0x18004c4f9  jnz     loc_18004C74A
0x18004c4ff  cmp     dword ptr [rdi+48h], 72706476h
0x18004c506  jnz     loc_18004C74A
0x18004c50c  cmp     qword ptr [rdi+68h], 0
0x18004c511  mov     eax, [rdi+74h]
0x18004c514  cmovnz  rsi, [rdi+68h]
0x18004c519  bt      eax, 12h
0x18004c51d  jnb     short loc_18004C53E
0x18004c51f  mov     r8d, 6
0x18004c525  lea     rdx, [rbp+4]
0x18004c529  mov     rcx, rsi
0x18004c52c  call    CheckDrawingExtent
0x18004c531  mov     eax, [rdi+74h]
0x18004c534  bt      eax, 13h
0x18004c538  jnb     loc_18004C6CD
0x18004c53e  mov     r10, [rdi+768h]
0x18004c545  mov     ecx, 0Dh
0x18004c54a  test    r10, r10
0x18004c54d  jz      loc_18004C612
0x18004c553  cmp     qword ptr [r10+0D0h], 0
0x18004c55b  jz      loc_18004C612
0x18004c561  mov     r14d, [rdi+770h]
0x18004c568  cmp     r14d, ecx
0x18004c56b  jz      loc_18004C612
0x18004c571  mov     edx, [rsp+98h+mixFill]
0x18004c578  mov     r9, r15
0x18004c57b  mov     [rdi+770h], ecx
0x18004c581  mov     r8, rbp
0x18004c584  mov     rax, [r10+0D8h]
0x18004c58b  mov     rcx, [rax+20h]
0x18004c58f  mov     [rdi+20h], rcx
0x18004c593  mov     rax, [r10+0D8h]
0x18004c59a  mov     rcx, [rax+28h]
0x18004c59e  mov     [rdi+8], rcx
0x18004c5a2  mov     rax, [r10+0D8h]
0x18004c5a9  mov     rcx, [rax+38h]
0x18004c5ad  mov     eax, [rsp+98h+flOptions]
0x18004c5b4  mov     [rsp+98h+var_50], eax
0x18004c5b8  mov     [rsp+98h+var_58], edx
0x18004c5bc  mov     rdx, [rsp+98h+pptlBrushOrg]
0x18004c5c4  mov     [rsp+98h+var_60], rdx
0x18004c5c9  mov     rdx, [rsp+98h+pboFill]
0x18004c5d1  mov     [rsp+98h+var_68], rdx
0x18004c5d6  mov     rdx, [rsp+98h+plineattrs]
0x18004c5de  mov     [rsp+98h+var_70], rdx
0x18004c5e3  mov     rdx, [rsp+98h+pboStroke]
0x18004c5eb  mov     [rdi+30h], rcx
0x18004c5ef  mov     rcx, rsi
0x18004c5f2  mov     rax, [r10+0D0h]
0x18004c5f9  mov     [rsp+98h+var_78], rdx
0x18004c5fe  mov     rdx, r12
0x18004c601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c606  mov     [rdi+770h], r14d
0x18004c60d  jmp     loc_18004C757
0x18004c612  mov     r10, [rdi+1058h]
0x18004c619  test    r10, r10
0x18004c61c  jz      loc_18004C6C7
0x18004c622  cmp     qword ptr [r10+130h], 0
0x18004c62a  jz      loc_18004C6C7
0x18004c630  mov     r14d, [rdi+1060h]
0x18004c637  cmp     r14d, ecx
0x18004c63a  jz      loc_18004C6C7
0x18004c640  mov     rax, [rdi+1050h]
0x18004c647  mov     r9, r15
0x18004c64a  mov     rbx, [rdi+8]
0x18004c64e  mov     r8, rbp
0x18004c651  mov     [rdi+1060h], ecx
0x18004c657  mov     rdx, r12
0x18004c65a  mov     ecx, [rsp+98h+mixFill]
0x18004c661  mov     [rdi+8], rax
0x18004c665  mov     eax, [rsp+98h+flOptions]
0x18004c66c  mov     [rsp+98h+var_50], eax
0x18004c670  mov     rax, [r10+130h]
0x18004c677  mov     [rsp+98h+var_58], ecx
0x18004c67b  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18004c683  mov     [rsp+98h+var_60], rcx
0x18004c688  mov     rcx, [rsp+98h+pboFill]
0x18004c690  mov     [rsp+98h+var_68], rcx
0x18004c695  mov     rcx, [rsp+98h+plineattrs]
0x18004c69d  mov     [rsp+98h+var_70], rcx
0x18004c6a2  mov     rcx, [rsp+98h+pboStroke]
0x18004c6aa  mov     [rsp+98h+var_78], rcx
0x18004c6af  mov     rcx, rsi
0x18004c6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6b7  mov     [rdi+1060h], r14d
0x18004c6be  mov     [rdi+8], rbx
0x18004c6c2  jmp     loc_18004C757
0x18004c6c7  bt      eax, 12h
0x18004c6cb  jnb     short loc_18004C6D7
0x18004c6cd  mov     eax, 1
0x18004c6d2  jmp     loc_18004C757
0x18004c6d7  test    dword ptr [rdi+70h], 20000000h
0x18004c6de  jnz     short loc_18004C755
0x18004c6e0  lea     rdx, [rbp+4]
0x18004c6e4  mov     rcx, rsi
0x18004c6e7  call    CheckBitmapSurface
0x18004c6ec  mov     eax, [rsp+98h+flOptions]
0x18004c6f3  mov     r9, r15; pxo
0x18004c6f6  mov     [rsp+98h+var_50], eax; flOptions
0x18004c6fa  mov     r8, rbp; pco
0x18004c6fd  mov     eax, [rsp+98h+mixFill]
0x18004c704  mov     rdx, r12; ppo
0x18004c707  mov     [rsp+98h+var_58], eax; mixFill
0x18004c70b  mov     rcx, rsi; pso
0x18004c70e  mov     rax, [rsp+98h+pptlBrushOrg]
0x18004c716  mov     [rsp+98h+var_60], rax; pptlBrushOrg
0x18004c71b  mov     rax, [rsp+98h+pboFill]
0x18004c723  mov     [rsp+98h+var_68], rax; pboFill
0x18004c728  mov     rax, [rsp+98h+plineattrs]
0x18004c730  mov     [rsp+98h+var_70], rax; plineattrs
0x18004c735  mov     rax, [rsp+98h+pboStroke]
0x18004c73d  mov     [rsp+98h+var_78], rax; pboStroke
0x18004c742  call    cs:__imp_EngStrokeAndFillPath
0x18004c748  jmp     short loc_18004C757
0x18004c74a  mov     ecx, 57h ; 'W'; dwErrCode
0x18004c74f  call    cs:__imp_SetLastError
0x18004c755  xor     eax, eax
0x18004c757  add     rsp, 60h
0x18004c75b  pop     r15
0x18004c75d  pop     r14
0x18004c75f  pop     r12
0x18004c761  pop     rdi
0x18004c762  pop     rsi
0x18004c763  pop     rbp
0x18004c764  pop     rbx
0x18004c765  retn
```
