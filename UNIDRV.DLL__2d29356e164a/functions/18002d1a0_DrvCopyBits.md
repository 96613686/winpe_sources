# DrvCopyBits

- ea: `0x18002d1a0`
- end: `0x18002d45c`
- name: `DrvCopyBits`
- size: `700`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *prclDest, POINTL *pptlSrc)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180016e6c`
- `0x18002d1a0`
- `0x18002dd38`
- `0x1800491dc`
- `0x180075010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d357`
- `KERNEL32!SetLastError` at `0x18002d357`
- `GDI32!EngCopyBits` at `0x18002d3e8`
- `GDI32!EngCopyBits` at `0x18002d3e8`

## pseudocode

```c
BOOL __stdcall DrvCopyBits(
        SURFOBJ *psoDest,
        SURFOBJ *psoSrc,
        CLIPOBJ *pco,
        XLATEOBJ *pxlo,
        RECTL *prclDest,
        POINTL *pptlSrc)
{
  DHPDEV dhpdev; // rdi
  SURFOBJ *v10; // rsi
  int v11; // eax
  __int64 v12; // r10
  __int64 v13; // r10
  int v14; // r15d
  __int64 v15; // rax
  __int64 v16; // rbx
  BOOL result; // eax
  int v18; // ebx
  DHPDEV v19; // rdi
  PVOID pvBits; // rcx
  __int64 (__fastcall *v21)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax

  dhpdev = psoDest->dhpdev;
  v10 = psoDest;
  if ( !dhpdev )
  {
    if ( !psoSrc || psoSrc->iType != 1 || psoDest->iType )
      return EngCopyBits(v10, psoSrc, pco, pxlo, prclDest, pptlSrc);
    v19 = psoSrc->dhpdev;
    if ( v19 )
    {
      if ( ((_BYTE)v19[29] & 0x40) != 0 && psoSrc->iBitmapFormat == 5 )
      {
        pvBits = psoDest->pvBits;
        if ( pvBits )
        {
          if ( v10->cjBits )
          {
            memset_0(pvBits, 255, v10->cjBits);
            *((_DWORD *)v19 + 29) |= 0x80u;
            return 1;
          }
        }
      }
    }
    return 0;
  }
  if ( *((_QWORD *)dhpdev + 13) )
    v10 = (SURFOBJ *)*((_QWORD *)dhpdev + 13);
  if ( *((_DWORD *)dhpdev + 18) != 1919968374 || ((_DWORD)dhpdev[28] & 0x20000000) == 0 && (psoSrc->iType || v10->iType) )
    return EngCopyBits(v10, psoSrc, pco, pxlo, prclDest, pptlSrc);
  if ( dhpdev != *((DHPDEV *)dhpdev + 8) || dhpdev != *((DHPDEV *)dhpdev + 553) )
  {
    SetLastError(0x57u);
    return 0;
  }
  v11 = *((_DWORD *)dhpdev + 29);
  if ( (v11 & 0x40000) != 0 )
  {
    CheckDrawingExtent((__int64)v10, &prclDest->left, 2);
    v11 = *((_DWORD *)dhpdev + 29);
    if ( (v11 & 0x80000) == 0 )
      return 1;
  }
  v12 = *((_QWORD *)dhpdev + 237);
  if ( v12 )
  {
    if ( *(_QWORD *)(v12 + 32) )
    {
      v18 = *((_DWORD *)dhpdev + 476);
      if ( v18 != 2 )
      {
        *((_DWORD *)dhpdev + 476) = 2;
        *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 32LL);
        *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 40LL);
        *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 56LL);
        result = (*(__int64 (__fastcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v12 + 32))(
                   v10,
                   psoSrc,
                   pco,
                   pxlo,
                   prclDest,
                   pptlSrc);
        *((_DWORD *)dhpdev + 476) = v18;
        return result;
      }
    }
  }
  v13 = *((_QWORD *)dhpdev + 523);
  if ( v13 )
  {
    if ( *(_QWORD *)(v13 + 256) )
    {
      v14 = *((_DWORD *)dhpdev + 1048);
      if ( v14 != 2 )
      {
        v15 = *((_QWORD *)dhpdev + 522);
        v16 = *((_QWORD *)dhpdev + 1);
        *((_DWORD *)dhpdev + 1048) = 2;
        *((_QWORD *)dhpdev + 1) = v15;
        result = (*(__int64 (__fastcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v13 + 256))(
                   v10,
                   psoSrc,
                   pco,
                   pxlo,
                   prclDest,
                   pptlSrc);
        *((_DWORD *)dhpdev + 1048) = v14;
        *((_QWORD *)dhpdev + 1) = v16;
        return result;
      }
    }
  }
  if ( (v11 & 0x40000) != 0 )
    return 1;
  if ( ((_DWORD)dhpdev[28] & 0x20000000) != 0 )
    return 0;
  v21 = *(__int64 (__fastcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(*((_QWORD *)dhpdev + 521)
                                                                                                 + 80LL);
  if ( !v21 )
  {
    CheckBitmapSurface(v10, &prclDest->left);
    return 0;
  }
  return v21(v10, psoSrc, pco, pxlo, prclDest, pptlSrc);
}

```

## disassembly

```asm
0x18002d1a0  push    rbx
0x18002d1a2  push    rbp
0x18002d1a3  push    rsi
0x18002d1a4  push    rdi
0x18002d1a5  push    r12
0x18002d1a7  push    r13
0x18002d1a9  push    r14
0x18002d1ab  push    r15
0x18002d1ad  sub     rsp, 48h
0x18002d1b1  mov     rdi, [rcx+10h]
0x18002d1b5  xor     r15d, r15d
0x18002d1b8  mov     r12, r9
0x18002d1bb  mov     r13, r8
0x18002d1be  mov     rbp, rdx
0x18002d1c1  mov     rsi, rcx
0x18002d1c4  test    rdi, rdi
0x18002d1c7  jz      loc_18002D364
0x18002d1cd  cmp     [rdi+68h], r15
0x18002d1d1  cmovnz  rsi, [rdi+68h]
0x18002d1d6  cmp     dword ptr [rdi+48h], 72706476h
0x18002d1dd  jnz     loc_18002D3CB
0x18002d1e3  test    dword ptr [rdi+70h], 20000000h
0x18002d1ea  jz      loc_18002D3B9
0x18002d1f0  cmp     rdi, [rdi+40h]
0x18002d1f4  jnz     loc_18002D352
0x18002d1fa  cmp     rdi, [rdi+1148h]
0x18002d201  jnz     loc_18002D352
0x18002d207  mov     eax, [rdi+74h]
0x18002d20a  mov     ecx, 2
0x18002d20f  mov     r14, [rsp+88h+prclDest]
0x18002d217  bt      eax, 12h
0x18002d21b  jb      loc_18002D32D
0x18002d221  mov     r10, [rdi+768h]
0x18002d228  test    r10, r10
0x18002d22b  jnz     loc_18002D2B9
0x18002d231  mov     r10, [rdi+1058h]
0x18002d238  test    r10, r10
0x18002d23b  jz      loc_18002D3FD
0x18002d241  cmp     [r10+100h], r15
0x18002d248  jz      loc_18002D3FD
0x18002d24e  mov     r15d, [rdi+1060h]
0x18002d255  cmp     r15d, ecx
0x18002d258  jz      loc_18002D3FD
0x18002d25e  mov     rax, [rdi+1050h]
0x18002d265  mov     r9, r12
0x18002d268  mov     rbx, [rdi+8]
0x18002d26c  mov     r8, r13
0x18002d26f  mov     [rdi+1060h], ecx
0x18002d275  mov     rdx, rbp
0x18002d278  mov     rcx, [rsp+88h+pptlSrc]
0x18002d280  mov     [rsp+88h+var_60], rcx
0x18002d285  mov     rcx, rsi
0x18002d288  mov     [rdi+8], rax
0x18002d28c  mov     rax, [r10+100h]
0x18002d293  mov     [rsp+88h+var_68], r14
0x18002d298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29d  mov     [rdi+1060h], r15d
0x18002d2a4  mov     [rdi+8], rbx
0x18002d2a8  add     rsp, 48h
0x18002d2ac  pop     r15
0x18002d2ae  pop     r14
0x18002d2b0  pop     r13
0x18002d2b2  pop     r12
0x18002d2b4  pop     rdi
0x18002d2b5  pop     rsi
0x18002d2b6  pop     rbp
0x18002d2b7  pop     rbx
0x18002d2b8  retn
0x18002d2b9  cmp     [r10+20h], r15
0x18002d2bd  jz      loc_18002D231
0x18002d2c3  mov     ebx, [rdi+770h]
0x18002d2c9  cmp     ebx, ecx
0x18002d2cb  jz      loc_18002D231
0x18002d2d1  mov     [rdi+770h], ecx
0x18002d2d7  mov     r9, r12
0x18002d2da  mov     rax, [r10+28h]
0x18002d2de  mov     r8, r13
0x18002d2e1  mov     rdx, rbp
0x18002d2e4  mov     rcx, [rax+20h]
0x18002d2e8  mov     [rdi+20h], rcx
0x18002d2ec  mov     rax, [r10+28h]
0x18002d2f0  mov     rcx, [rax+28h]
0x18002d2f4  mov     [rdi+8], rcx
0x18002d2f8  mov     rax, [r10+28h]
0x18002d2fc  mov     rcx, [rax+38h]
0x18002d300  mov     [rdi+30h], rcx
0x18002d304  mov     rcx, [rsp+88h+pptlSrc]
0x18002d30c  mov     rax, [r10+20h]
0x18002d310  mov     [rsp+88h+var_60], rcx
0x18002d315  mov     rcx, rsi
0x18002d318  mov     [rsp+88h+var_68], r14
0x18002d31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d322  mov     [rdi+770h], ebx
0x18002d328  jmp     loc_18002D2A8
0x18002d32d  mov     r8d, ecx
0x18002d330  mov     rdx, r14
0x18002d333  mov     rcx, rsi
0x18002d336  call    CheckDrawingExtent
0x18002d33b  mov     eax, [rdi+74h]
0x18002d33e  bt      eax, 13h
0x18002d342  jb      loc_18002D3F3
0x18002d348  mov     eax, 1
0x18002d34d  jmp     loc_18002D2A8
0x18002d352  mov     ecx, 57h ; 'W'; dwErrCode
0x18002d357  call    cs:__imp_SetLastError
0x18002d35d  xor     eax, eax
0x18002d35f  jmp     loc_18002D2A8
0x18002d364  test    rbp, rbp
0x18002d367  jz      short loc_18002D3CB
0x18002d369  mov     ebx, 1
0x18002d36e  cmp     [rdx+4Ch], bx
0x18002d372  jnz     short loc_18002D3CB
0x18002d374  cmp     [rcx+4Ch], r15w
0x18002d379  jnz     short loc_18002D3CB
0x18002d37b  mov     rdi, [rdx+10h]
0x18002d37f  test    rdi, rdi
0x18002d382  jz      short loc_18002D35D
0x18002d384  test    byte ptr [rdi+74h], 40h
0x18002d388  jz      short loc_18002D35D
0x18002d38a  cmp     dword ptr [rdx+48h], 5
0x18002d38e  jnz     short loc_18002D35D
0x18002d390  mov     rcx, [rcx+30h]; void *
0x18002d394  test    rcx, rcx
0x18002d397  jz      short loc_18002D35D
0x18002d399  cmp     [rsi+28h], r15d
0x18002d39d  jbe     short loc_18002D35D
0x18002d39f  mov     r8d, [rsi+28h]; Size
0x18002d3a3  mov     edx, 0FFh; Val
0x18002d3a8  call    memset_0
0x18002d3ad  bts     dword ptr [rdi+74h], 7
0x18002d3b2  mov     eax, ebx
0x18002d3b4  jmp     loc_18002D2A8
0x18002d3b9  cmp     [rdx+4Ch], r15w
0x18002d3be  jnz     short loc_18002D3CB
0x18002d3c0  cmp     [rsi+4Ch], r15w
0x18002d3c5  jz      loc_18002D1F0
0x18002d3cb  mov     rax, [rsp+88h+pptlSrc]
0x18002d3d3  mov     rcx, rsi; psoDest
0x18002d3d6  mov     [rsp+88h+var_60], rax; pptlSrc
0x18002d3db  mov     rax, [rsp+88h+prclDest]
0x18002d3e3  mov     [rsp+88h+var_68], rax; prclDest
0x18002d3e8  call    cs:__imp_EngCopyBits
0x18002d3ee  jmp     loc_18002D2A8
0x18002d3f3  mov     ecx, 2
0x18002d3f8  jmp     loc_18002D221
0x18002d3fd  bt      eax, 12h
0x18002d401  jb      loc_18002D348
0x18002d407  test    dword ptr [rdi+70h], 20000000h
0x18002d40e  jnz     loc_18002D35D
0x18002d414  mov     rax, [rdi+1048h]
0x18002d41b  mov     rax, [rax+50h]
0x18002d41f  test    rax, rax
0x18002d422  jnz     short loc_18002D434
0x18002d424  mov     rdx, r14
0x18002d427  mov     rcx, rsi
0x18002d42a  call    CheckBitmapSurface
0x18002d42f  jmp     loc_18002D35D
0x18002d434  mov     rcx, [rsp+88h+pptlSrc]
0x18002d43c  mov     r9, r12
0x18002d43f  mov     [rsp+88h+var_60], rcx
0x18002d444  mov     r8, r13
0x18002d447  mov     rcx, rsi
0x18002d44a  mov     [rsp+88h+var_68], r14
0x18002d44f  mov     rdx, rbp
0x18002d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d457  jmp     loc_18002D2A8
```
