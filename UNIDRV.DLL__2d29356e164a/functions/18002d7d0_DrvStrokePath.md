# DrvStrokePath

- ea: `0x18002d7d0`
- end: `0x18002dabc`
- name: `DrvStrokePath`
- size: `748`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, LINEATTRS *plineattrs, MIX mix)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180016e6c`
- `0x18002d7d0`
- `0x18002dd38`
- `0x18004c9ec`
- `0x180075010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002daaf`
- `KERNEL32!SetLastError` at `0x18002daaf`
- `GDI32!EngStrokePath` at `0x18002da98`
- `GDI32!EngStrokePath` at `0x18002da98`

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
          (int *)((unsigned __int64)&pco->rclBounds & ((unsigned __int128)-(__int128)(unsigned __int64)pco >> 64)));
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
0x18002d7d0  push    rbx
0x18002d7d2  push    rbp
0x18002d7d3  push    rsi
0x18002d7d4  push    rdi
0x18002d7d5  push    r12
0x18002d7d7  push    r13
0x18002d7d9  push    r14
0x18002d7db  push    r15
0x18002d7dd  sub     rsp, 58h
0x18002d7e1  mov     rdi, [rcx+10h]
0x18002d7e5  mov     rsi, rcx
0x18002d7e8  xor     ecx, ecx
0x18002d7ea  mov     r13, r9
0x18002d7ed  mov     rbp, r8
0x18002d7f0  mov     r14, rdx
0x18002d7f3  test    rdi, rdi
0x18002d7f6  jz      loc_18002DAAA
0x18002d7fc  cmp     rdi, [rdi+40h]
0x18002d800  jnz     loc_18002DAAA
0x18002d806  cmp     rdi, [rdi+1148h]
0x18002d80d  jnz     loc_18002DAAA
0x18002d813  cmp     dword ptr [rdi+48h], 72706476h
0x18002d81a  jnz     loc_18002DAAA
0x18002d820  cmp     [rdi+68h], rcx
0x18002d824  mov     eax, [rdi+74h]
0x18002d827  cmovnz  rsi, [rdi+68h]
0x18002d82c  bt      eax, 12h
0x18002d830  jb      loc_18002D8F3
0x18002d836  mov     r10, [rdi+768h]
0x18002d83d  mov     edx, 0Bh
0x18002d842  test    r10, r10
0x18002d845  jnz     loc_18002D919
0x18002d84b  mov     r10, [rdi+1058h]
0x18002d852  test    r10, r10
0x18002d855  jz      loc_18002D9BC
0x18002d85b  cmp     [r10+120h], rcx
0x18002d862  jz      loc_18002D9BC
0x18002d868  mov     r15d, [rdi+1060h]
0x18002d86f  cmp     r15d, edx
0x18002d872  jz      loc_18002D9BC
0x18002d878  mov     rax, [rdi+1050h]
0x18002d87f  mov     r9, r13
0x18002d882  mov     ecx, [rsp+98h+mix]
0x18002d889  mov     r8, rbp
0x18002d88c  mov     rbx, [rdi+8]
0x18002d890  mov     [rsp+98h+var_60], ecx
0x18002d894  mov     rcx, [rsp+98h+plineattrs]
0x18002d89c  mov     [rsp+98h+var_68], rcx
0x18002d8a1  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18002d8a9  mov     [rsp+98h+var_70], rcx
0x18002d8ae  mov     rcx, [rsp+98h+pbo]
0x18002d8b6  mov     [rdi+1060h], edx
0x18002d8bc  mov     rdx, r14
0x18002d8bf  mov     [rsp+98h+var_78], rcx
0x18002d8c4  mov     rcx, rsi
0x18002d8c7  mov     [rdi+8], rax
0x18002d8cb  mov     rax, [r10+120h]
0x18002d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8d7  mov     [rdi+1060h], r15d
0x18002d8de  mov     [rdi+8], rbx
0x18002d8e2  add     rsp, 58h
0x18002d8e6  pop     r15
0x18002d8e8  pop     r14
0x18002d8ea  pop     r13
0x18002d8ec  pop     r12
0x18002d8ee  pop     rdi
0x18002d8ef  pop     rsi
0x18002d8f0  pop     rbp
0x18002d8f1  pop     rbx
0x18002d8f2  retn
0x18002d8f3  lea     rdx, [r8+4]
0x18002d8f7  mov     rcx, rsi
0x18002d8fa  mov     r8d, 2
0x18002d900  call    CheckDrawingExtent
0x18002d905  mov     eax, [rdi+74h]
0x18002d908  bt      eax, 13h
0x18002d90c  jb      loc_18002DAA3
0x18002d912  mov     eax, 1
0x18002d917  jmp     short loc_18002D8E2
0x18002d919  cmp     [r10+0B0h], rcx
0x18002d920  jz      loc_18002D84B
0x18002d926  mov     ebx, [rdi+770h]
0x18002d92c  cmp     ebx, edx
0x18002d92e  jz      loc_18002D84B
0x18002d934  mov     [rdi+770h], edx
0x18002d93a  mov     r9, r13
0x18002d93d  mov     rax, [r10+0B8h]
0x18002d944  mov     r8, rbp
0x18002d947  mov     rdx, r14
0x18002d94a  mov     rcx, [rax+20h]
0x18002d94e  mov     [rdi+20h], rcx
0x18002d952  mov     rax, [r10+0B8h]
0x18002d959  mov     rcx, [rax+28h]
0x18002d95d  mov     [rdi+8], rcx
0x18002d961  mov     rax, [r10+0B8h]
0x18002d968  mov     rcx, [rax+38h]
0x18002d96c  mov     [rdi+30h], rcx
0x18002d970  mov     ecx, [rsp+98h+mix]
0x18002d977  mov     rax, [r10+0B0h]
0x18002d97e  mov     [rsp+98h+var_60], ecx
0x18002d982  mov     rcx, [rsp+98h+plineattrs]
0x18002d98a  mov     [rsp+98h+var_68], rcx
0x18002d98f  mov     rcx, [rsp+98h+pptlBrushOrg]
0x18002d997  mov     [rsp+98h+var_70], rcx
0x18002d99c  mov     rcx, [rsp+98h+pbo]
0x18002d9a4  mov     [rsp+98h+var_78], rcx
0x18002d9a9  mov     rcx, rsi
0x18002d9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9b1  mov     [rdi+770h], ebx
0x18002d9b7  jmp     loc_18002D8E2
0x18002d9bc  bt      eax, 12h
0x18002d9c0  jb      loc_18002D912
0x18002d9c6  test    dword ptr [rdi+70h], 20000000h
0x18002d9cd  jnz     loc_18002DAB5
0x18002d9d3  cmp     dword ptr [r14+4], 4
0x18002d9d8  mov     r12d, [rsp+98h+mix]
0x18002d9e0  mov     r15, [rsp+98h+plineattrs]
0x18002d9e8  mov     rbx, [rsp+98h+pbo]
0x18002d9f0  jnz     short loc_18002DA58
0x18002d9f2  cmp     [r14], ecx
0x18002d9f5  jnz     short loc_18002DA58
0x18002d9f7  cmp     [rdi+6E0h], rcx
0x18002d9fe  jz      short loc_18002DA58
0x18002da00  cmp     dword ptr [rdi+6E8h], 0FCh
0x18002da0a  jnb     short loc_18002DA58
0x18002da0c  cmp     r12d, 0D0Dh
0x18002da13  jnz     short loc_18002DA58
0x18002da15  test    rbx, rbx
0x18002da18  jz      short loc_18002DA58
0x18002da1a  test    rbp, rbp
0x18002da1d  jz      short loc_18002DA25
0x18002da1f  cmp     byte ptr [rbp+14h], 3
0x18002da23  jz      short loc_18002DA58
0x18002da25  cmp     dword ptr [rsi+48h], 5
0x18002da29  jz      short loc_18002DA35
0x18002da2b  mov     rax, [rdi+1000h]
0x18002da32  mov     ecx, [rax+4]
0x18002da35  cmp     [rbx], ecx
0x18002da37  jnz     short loc_18002DA58
0x18002da39  test    [r15], dl
0x18002da3c  jnz     short loc_18002DA58
0x18002da3e  mov     r9d, [r15+0Ch]
0x18002da42  mov     r8, rbp
0x18002da45  mov     rdx, r14
0x18002da48  mov     rcx, rdi
0x18002da4b  call    TestStrokeRectangle
0x18002da50  test    eax, eax
0x18002da52  jnz     loc_18002D912
0x18002da58  lea     rcx, [rbp+4]
0x18002da5c  mov     rax, rbp
0x18002da5f  neg     rax
0x18002da62  sbb     rdx, rdx
0x18002da65  and     rdx, rcx
0x18002da68  mov     rcx, rsi
0x18002da6b  call    CheckBitmapSurface
0x18002da70  mov     rax, [rsp+98h+pptlBrushOrg]
0x18002da78  mov     r9, r13; pxo
0x18002da7b  mov     [rsp+98h+var_60], r12d; mix
0x18002da80  mov     r8, rbp; pco
0x18002da83  mov     [rsp+98h+var_68], r15; plineattrs
0x18002da88  mov     rdx, r14; ppo
0x18002da8b  mov     [rsp+98h+var_70], rax; pptlBrushOrg
0x18002da90  mov     rcx, rsi; pso
0x18002da93  mov     [rsp+98h+var_78], rbx; pbo
0x18002da98  call    cs:__imp_EngStrokePath
0x18002da9e  jmp     loc_18002D8E2
0x18002daa3  xor     ecx, ecx
0x18002daa5  jmp     loc_18002D836
0x18002daaa  mov     ecx, 57h ; 'W'; dwErrCode
0x18002daaf  call    cs:__imp_SetLastError
0x18002dab5  xor     eax, eax
0x18002dab7  jmp     loc_18002D8E2
```
