# DrvStrokeAndFillPath

- ea: `0x18004db20`
- end: `0x18004ddd7`
- name: `DrvStrokeAndFillPath`
- size: `695`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pboStroke, LINEATTRS *plineattrs, BRUSHOBJ *pboFill, POINTL *pptlBrushOrg, MIX mixFill, FLONG flOptions)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017148`
- `0x18002e5c8`
- `0x18004db20`
- `0x180077010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18004ddb9`
- `KERNEL32!SetLastError` at `0x18004ddb9`
- `GDI32!EngStrokeAndFillPath` at `0x18004dda6`
- `GDI32!EngStrokeAndFillPath` at `0x18004dda6`

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
      CheckBitmapSurface(v14, &pco->rclBounds.left, (__int64)pco, (__int64)pxo);
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
0x18004db20  push    rbx
0x18004db22  push    rbp
0x18004db23  push    rsi
0x18004db24  push    rdi
0x18004db25  push    r12
0x18004db27  push    r14
0x18004db29  push    r15
0x18004db2b  sub     rsp, 60h
0x18004db2f  mov     rdi, [rcx+10h]
0x18004db33  mov     r15, r9
0x18004db36  mov     rbp, r8
0x18004db39  mov     r12, rdx
0x18004db3c  mov     rsi, rcx
0x18004db3f  test    rdi, rdi
0x18004db42  jz      loc_18004DDB4
0x18004db48  cmp     rdi, [rdi+40h]
0x18004db4c  jnz     loc_18004DDB4
0x18004db52  cmp     rdi, [rdi+1148h]
0x18004db59  jnz     loc_18004DDB4
0x18004db5f  cmp     dword ptr [rdi+48h], 72706476h
0x18004db66  jnz     loc_18004DDB4
0x18004db6c  cmp     qword ptr [rdi+68h], 0
0x18004db71  mov     eax, [rdi+74h]
0x18004db74  cmovnz  rsi, [rdi+68h]
0x18004db79  bt      eax, 12h
0x18004db7d  jnb     short loc_18004DB9E
0x18004db7f  mov     r8d, 6
0x18004db85  lea     rdx, [rbp+4]
0x18004db89  mov     rcx, rsi
0x18004db8c  call    CheckDrawingExtent
0x18004db91  mov     eax, [rdi+74h]
0x18004db94  bt      eax, 13h
0x18004db98  jnb     loc_18004DD2D
0x18004db9e  mov     r10, [rdi+768h]
0x18004dba5  mov     ecx, 0Dh
0x18004dbaa  test    r10, r10
0x18004dbad  jz      loc_18004DC72
0x18004dbb3  cmp     qword ptr [r10+0D0h], 0
0x18004dbbb  jz      loc_18004DC72
0x18004dbc1  mov     r14d, [rdi+770h]
0x18004dbc8  cmp     r14d, ecx
0x18004dbcb  jz      loc_18004DC72
0x18004dbd1  mov     edx, [rsp+98h+mixFill]
0x18004dbd8  mov     r9, r15
0x18004dbdb  mov     [rdi+770h], ecx
0x18004dbe1  mov     r8, rbp
0x18004dbe4  mov     rax, [r10+0D8h]
0x18004dbeb  mov     rcx, [rax+20h]
0x18004dbef  mov     [rdi+20h], rcx
0x18004dbf3  mov     rax, [r10+0D8h]
0x18004dbfa  mov     rcx, [rax+28h]
0x18004dbfe  mov     [rdi+8], rcx
0x18004dc02  mov     rax, [r10+0D8h]
0x18004dc09  mov     rcx, [rax+38h]
0x18004dc0d  mov     eax, [rsp+98h+flOptions]
0x18004dc14  mov     [rsp+98h+var_50], eax
0x18004dc18  mov     [rsp+98h+var_58], edx
0x18004dc1c  mov     rdx, [rsp+98h+pptlBrushOrg]
0x18004dc24  mov     [rsp+98h+var_60], rdx
0x18004dc29  mov     rdx, [rsp+98h+pboFill]
0x18004dc31  mov     [rsp+98h+var_68], rdx
0x18004dc36  mov     rdx, [rsp+98h+plineattrs]
0x18004dc3e  mov     [rsp+98h+var_70], rdx
0x18004dc43  mov     rdx, [rsp+98h+pboStroke]
0x18004dc4b  mov     [rdi+30h], rcx
0x18004dc4f  mov     rcx, rsi
0x18004dc52  mov     rax, [r10+0D0h]
0x18004dc59  mov     [rsp+98h+var_78], rdx
0x18004dc5e  mov     rdx, r12
0x18004dc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc66  mov     [rdi+770h], r14d
0x18004dc6d  jmp     loc_18004DDC7
0x18004dc72  mov     r10, [rdi+1058h]
0x18004dc79  test    r10, r10
0x18004dc7c  jz      loc_18004DD27
0x18004dc82  cmp     qword ptr [r10+130h], 0
0x18004dc8a  jz      loc_18004DD27
0x18004dc90  mov     r14d, [rdi+1060h]
0x18004dc97  cmp     r14d, ecx
0x18004dc9a  jz      loc_18004DD27
0x18004dca0  mov     rax, [rdi+1050h]
0x18004dca7  mov     r9, r15
0x18004dcaa  mov     rbx, [rdi+8]
0x18004dcae  mov     r8, rbp
0x18004dcb1  mov     [rdi+1060h], ecx
0x18004dcb7  mov     rdx, r12
0x18004dcba  mov     ecx, [rsp+98h+mixFill]
0x18004dcc1  mov     [rdi+8], rax
0x18004dcc5  mov     eax, [rsp+98h+flOptions]
0x18004dccc  mov     [rsp+98h+var_50], eax
0x18004dcd0  mov     rax, [r10+130h]
0x18004dcd7  mov     [rsp+98h+var_58], ecx
0x18004dcdb  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18004dce3  mov     [rsp+98h+var_60], rcx
0x18004dce8  mov     rcx, [rsp+98h+pboFill]
0x18004dcf0  mov     [rsp+98h+var_68], rcx
0x18004dcf5  mov     rcx, [rsp+98h+plineattrs]
0x18004dcfd  mov     [rsp+98h+var_70], rcx
0x18004dd02  mov     rcx, [rsp+98h+pboStroke]
0x18004dd0a  mov     [rsp+98h+var_78], rcx
0x18004dd0f  mov     rcx, rsi
0x18004dd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd17  mov     [rdi+1060h], r14d
0x18004dd1e  mov     [rdi+8], rbx
0x18004dd22  jmp     loc_18004DDC7
0x18004dd27  bt      eax, 12h
0x18004dd2b  jnb     short loc_18004DD37
0x18004dd2d  mov     eax, 1
0x18004dd32  jmp     loc_18004DDC7
0x18004dd37  test    dword ptr [rdi+70h], 20000000h
0x18004dd3e  jnz     loc_18004DDC5
0x18004dd44  lea     rdx, [rbp+4]
0x18004dd48  mov     rcx, rsi
0x18004dd4b  call    CheckBitmapSurface
0x18004dd50  mov     eax, [rsp+98h+flOptions]
0x18004dd57  mov     r9, r15; pxo
0x18004dd5a  mov     [rsp+98h+var_50], eax; flOptions
0x18004dd5e  mov     r8, rbp; pco
0x18004dd61  mov     eax, [rsp+98h+mixFill]
0x18004dd68  mov     rdx, r12; ppo
0x18004dd6b  mov     [rsp+98h+var_58], eax; mixFill
0x18004dd6f  mov     rcx, rsi; pso
0x18004dd72  mov     rax, [rsp+98h+pptlBrushOrg]
0x18004dd7a  mov     [rsp+98h+var_60], rax; pptlBrushOrg
0x18004dd7f  mov     rax, [rsp+98h+pboFill]
0x18004dd87  mov     [rsp+98h+var_68], rax; pboFill
0x18004dd8c  mov     rax, [rsp+98h+plineattrs]
0x18004dd94  mov     [rsp+98h+var_70], rax; plineattrs
0x18004dd99  mov     rax, [rsp+98h+pboStroke]
0x18004dda1  mov     [rsp+98h+var_78], rax; pboStroke
0x18004dda6  call    cs:__imp_EngStrokeAndFillPath
0x18004ddad  nop     dword ptr [rax+rax+00h]
0x18004ddb2  jmp     short loc_18004DDC7
0x18004ddb4  mov     ecx, 57h ; 'W'; dwErrCode
0x18004ddb9  call    cs:__imp_SetLastError
0x18004ddc0  nop     dword ptr [rax+rax+00h]
0x18004ddc5  xor     eax, eax
0x18004ddc7  add     rsp, 60h
0x18004ddcb  pop     r15
0x18004ddcd  pop     r14
0x18004ddcf  pop     r12
0x18004ddd1  pop     rdi
0x18004ddd2  pop     rsi
0x18004ddd3  pop     rbp
0x18004ddd4  pop     rbx
0x18004ddd5  retn
```
