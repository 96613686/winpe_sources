# DrvCopyBits

- ea: `0x18002da20`
- end: `0x18002dce9`
- name: `DrvCopyBits`
- size: `713`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *prclDest, POINTL *pptlSrc)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180017148`
- `0x18002da20`
- `0x18002e5c8`
- `0x18004a71c`
- `0x180077010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002dbd8`
- `KERNEL32!SetLastError` at `0x18002dbd8`
- `GDI32!EngCopyBits` at `0x18002dc6f`
- `GDI32!EngCopyBits` at `0x18002dc6f`

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
    CheckBitmapSurface(v10, &prclDest->left, (__int64)pco, (__int64)pxlo);
    return 0;
  }
  return v21(v10, psoSrc, pco, pxlo, prclDest, pptlSrc);
}

```

## disassembly

```asm
0x18002da20  push    rbx
0x18002da22  push    rbp
0x18002da23  push    rsi
0x18002da24  push    rdi
0x18002da25  push    r12
0x18002da27  push    r13
0x18002da29  push    r14
0x18002da2b  push    r15
0x18002da2d  sub     rsp, 48h
0x18002da31  mov     rdi, [rcx+10h]
0x18002da35  xor     r15d, r15d
0x18002da38  mov     r12, r9
0x18002da3b  mov     r13, r8
0x18002da3e  mov     rbp, rdx
0x18002da41  mov     rsi, rcx
0x18002da44  test    rdi, rdi
0x18002da47  jz      loc_18002DBEB
0x18002da4d  cmp     [rdi+68h], r15
0x18002da51  cmovnz  rsi, [rdi+68h]
0x18002da56  cmp     dword ptr [rdi+48h], 72706476h
0x18002da5d  jnz     loc_18002DC52
0x18002da63  test    dword ptr [rdi+70h], 20000000h
0x18002da6a  jz      loc_18002DC40
0x18002da70  cmp     rdi, [rdi+40h]
0x18002da74  jnz     loc_18002DBD3
0x18002da7a  cmp     rdi, [rdi+1148h]
0x18002da81  jnz     loc_18002DBD3
0x18002da87  mov     eax, [rdi+74h]
0x18002da8a  mov     ecx, 2
0x18002da8f  mov     r14, [rsp+88h+prclDest]
0x18002da97  bt      eax, 12h
0x18002da9b  jb      loc_18002DBAE
0x18002daa1  mov     r10, [rdi+768h]
0x18002daa8  test    r10, r10
0x18002daab  jnz     loc_18002DB3A
0x18002dab1  mov     r10, [rdi+1058h]
0x18002dab8  test    r10, r10
0x18002dabb  jz      loc_18002DC8A
0x18002dac1  cmp     [r10+100h], r15
0x18002dac8  jz      loc_18002DC8A
0x18002dace  mov     r15d, [rdi+1060h]
0x18002dad5  cmp     r15d, ecx
0x18002dad8  jz      loc_18002DC8A
0x18002dade  mov     rax, [rdi+1050h]
0x18002dae5  mov     r9, r12
0x18002dae8  mov     rbx, [rdi+8]
0x18002daec  mov     r8, r13
0x18002daef  mov     [rdi+1060h], ecx
0x18002daf5  mov     rdx, rbp
0x18002daf8  mov     rcx, [rsp+88h+pptlSrc]
0x18002db00  mov     [rsp+88h+var_60], rcx
0x18002db05  mov     rcx, rsi
0x18002db08  mov     [rdi+8], rax
0x18002db0c  mov     rax, [r10+100h]
0x18002db13  mov     [rsp+88h+var_68], r14
0x18002db18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db1d  mov     [rdi+1060h], r15d
0x18002db24  mov     [rdi+8], rbx
0x18002db28  add     rsp, 48h
0x18002db2c  pop     r15
0x18002db2e  pop     r14
0x18002db30  pop     r13
0x18002db32  pop     r12
0x18002db34  pop     rdi
0x18002db35  pop     rsi
0x18002db36  pop     rbp
0x18002db37  pop     rbx
0x18002db38  retn
0x18002db3a  cmp     [r10+20h], r15
0x18002db3e  jz      loc_18002DAB1
0x18002db44  mov     ebx, [rdi+770h]
0x18002db4a  cmp     ebx, ecx
0x18002db4c  jz      loc_18002DAB1
0x18002db52  mov     [rdi+770h], ecx
0x18002db58  mov     r9, r12
0x18002db5b  mov     rax, [r10+28h]
0x18002db5f  mov     r8, r13
0x18002db62  mov     rdx, rbp
0x18002db65  mov     rcx, [rax+20h]
0x18002db69  mov     [rdi+20h], rcx
0x18002db6d  mov     rax, [r10+28h]
0x18002db71  mov     rcx, [rax+28h]
0x18002db75  mov     [rdi+8], rcx
0x18002db79  mov     rax, [r10+28h]
0x18002db7d  mov     rcx, [rax+38h]
0x18002db81  mov     [rdi+30h], rcx
0x18002db85  mov     rcx, [rsp+88h+pptlSrc]
0x18002db8d  mov     rax, [r10+20h]
0x18002db91  mov     [rsp+88h+var_60], rcx
0x18002db96  mov     rcx, rsi
0x18002db99  mov     [rsp+88h+var_68], r14
0x18002db9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dba3  mov     [rdi+770h], ebx
0x18002dba9  jmp     loc_18002DB28
0x18002dbae  mov     r8d, ecx
0x18002dbb1  mov     rdx, r14
0x18002dbb4  mov     rcx, rsi
0x18002dbb7  call    CheckDrawingExtent
0x18002dbbc  mov     eax, [rdi+74h]
0x18002dbbf  bt      eax, 13h
0x18002dbc3  jb      loc_18002DC80
0x18002dbc9  mov     eax, 1
0x18002dbce  jmp     loc_18002DB28
0x18002dbd3  mov     ecx, 57h ; 'W'; dwErrCode
0x18002dbd8  call    cs:__imp_SetLastError
0x18002dbdf  nop     dword ptr [rax+rax+00h]
0x18002dbe4  xor     eax, eax
0x18002dbe6  jmp     loc_18002DB28
0x18002dbeb  test    rbp, rbp
0x18002dbee  jz      short loc_18002DC52
0x18002dbf0  mov     ebx, 1
0x18002dbf5  cmp     [rdx+4Ch], bx
0x18002dbf9  jnz     short loc_18002DC52
0x18002dbfb  cmp     [rcx+4Ch], r15w
0x18002dc00  jnz     short loc_18002DC52
0x18002dc02  mov     rdi, [rdx+10h]
0x18002dc06  test    rdi, rdi
0x18002dc09  jz      short loc_18002DBE4
0x18002dc0b  test    byte ptr [rdi+74h], 40h
0x18002dc0f  jz      short loc_18002DBE4
0x18002dc11  cmp     dword ptr [rdx+48h], 5
0x18002dc15  jnz     short loc_18002DBE4
0x18002dc17  mov     rcx, [rcx+30h]; void *
0x18002dc1b  test    rcx, rcx
0x18002dc1e  jz      short loc_18002DBE4
0x18002dc20  cmp     [rsi+28h], r15d
0x18002dc24  jbe     short loc_18002DBE4
0x18002dc26  mov     r8d, [rsi+28h]; Size
0x18002dc2a  mov     edx, 0FFh; Val
0x18002dc2f  call    memset_0
0x18002dc34  bts     dword ptr [rdi+74h], 7
0x18002dc39  mov     eax, ebx
0x18002dc3b  jmp     loc_18002DB28
0x18002dc40  cmp     [rdx+4Ch], r15w
0x18002dc45  jnz     short loc_18002DC52
0x18002dc47  cmp     [rsi+4Ch], r15w
0x18002dc4c  jz      loc_18002DA70
0x18002dc52  mov     rax, [rsp+88h+pptlSrc]
0x18002dc5a  mov     rcx, rsi; psoDest
0x18002dc5d  mov     [rsp+88h+var_60], rax; pptlSrc
0x18002dc62  mov     rax, [rsp+88h+prclDest]
0x18002dc6a  mov     [rsp+88h+var_68], rax; prclDest
0x18002dc6f  call    cs:__imp_EngCopyBits
0x18002dc76  nop     dword ptr [rax+rax+00h]
0x18002dc7b  jmp     loc_18002DB28
0x18002dc80  mov     ecx, 2
0x18002dc85  jmp     loc_18002DAA1
0x18002dc8a  bt      eax, 12h
0x18002dc8e  jb      loc_18002DBC9
0x18002dc94  test    dword ptr [rdi+70h], 20000000h
0x18002dc9b  jnz     loc_18002DBE4
0x18002dca1  mov     rax, [rdi+1048h]
0x18002dca8  mov     rax, [rax+50h]
0x18002dcac  test    rax, rax
0x18002dcaf  jnz     short loc_18002DCC1
0x18002dcb1  mov     rdx, r14
0x18002dcb4  mov     rcx, rsi
0x18002dcb7  call    CheckBitmapSurface
0x18002dcbc  jmp     loc_18002DBE4
0x18002dcc1  mov     rcx, [rsp+88h+pptlSrc]
0x18002dcc9  mov     r9, r12
0x18002dccc  mov     [rsp+88h+var_60], rcx
0x18002dcd1  mov     r8, r13
0x18002dcd4  mov     rcx, rsi
0x18002dcd7  mov     [rsp+88h+var_68], r14
0x18002dcdc  mov     rdx, rbp
0x18002dcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dce4  jmp     loc_18002DB28
```
