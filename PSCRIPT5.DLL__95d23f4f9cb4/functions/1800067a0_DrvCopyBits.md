# DrvCopyBits

- ea: `0x1800067a0`
- end: `0x180006947`
- name: `DrvCopyBits`
- size: `423`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *prclDest, POINTL *pptlSrc)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800028d8`
- `0x180005c48`
- `0x1800067a0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006800`
- `KERNEL32!SetLastError` at `0x180006800`
- `GDI32!EngEraseSurface` at `0x1800067e5`
- `GDI32!EngEraseSurface` at `0x1800067e5`

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
  BOOL result; // eax
  DHPDEV dhpdev; // rbx
  __int64 v12; // r10
  int v13; // eax
  LONG x; // edx
  int v15; // eax
  int v16; // eax
  int v17[4]; // [rsp+50h] [rbp-78h] BYREF
  int v18[26]; // [rsp+60h] [rbp-68h] BYREF

  memset_0(v18, 0, 0x40u);
  if ( psoSrc->iType )
    return EngEraseSurface(psoDest, prclDest, 0xFFFFFFu);
  if ( psoDest->iType == 1 )
  {
    dhpdev = psoDest->dhpdev;
    if ( *(_DWORD *)(*((_QWORD *)dhpdev + 12) + 124LL) == 2 && *((_DWORD *)dhpdev + 543) > 1u
      || ((_DWORD)dhpdev[538] & 0xC0000000) != 0
      || *((_DWORD *)dhpdev + 176) == 3 )
    {
      return 1;
    }
    else
    {
      v12 = *((_QWORD *)dhpdev + 434);
      if ( v12 && *(_QWORD *)(v12 + 32) && (v13 = *((_DWORD *)dhpdev + 870), (v13 & 1) == 0) )
      {
        *((_DWORD *)dhpdev + 870) = v13 | 1;
        *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 32LL);
        *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 40LL);
        *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 56LL);
        result = (*(__int64 (__fastcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v12 + 32))(
                   psoDest,
                   psoSrc,
                   pco,
                   pxlo,
                   prclDest,
                   pptlSrc);
        *((_DWORD *)dhpdev + 870) &= ~1u;
      }
      else
      {
        x = pptlSrc->x;
        v15 = pptlSrc->y + prclDest->bottom - prclDest->top;
        v17[1] = pptlSrc->y;
        v17[3] = v15;
        v16 = prclDest->right - prclDest->left;
        v17[0] = x;
        v17[2] = x + v16;
        return BCommonDIBBlt(
                 dhpdev,
                 (__int64)psoSrc,
                 (__int64)pco,
                 (__int64)pxlo,
                 v17,
                 &prclDest->left,
                 0,
                 (__int64)v18,
                 0,
                 0);
      }
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800067a0  push    rbx
0x1800067a2  push    rbp
0x1800067a3  push    rsi
0x1800067a4  push    rdi
0x1800067a5  push    r14
0x1800067a7  sub     rsp, 0A0h
0x1800067ae  mov     rsi, rdx
0x1800067b1  mov     r14, r8
0x1800067b4  xor     edx, edx; Val
0x1800067b6  mov     rdi, rcx
0x1800067b9  lea     rcx, [rsp+0C8h+var_68]; void *
0x1800067be  mov     rbp, r9
0x1800067c1  lea     r8d, [rdx+40h]; Size
0x1800067c5  call    memset_0
0x1800067ca  xor     r9d, r9d
0x1800067cd  cmp     [rsi+4Ch], r9w
0x1800067d2  jz      short loc_1800067F0
0x1800067d4  mov     rdx, [rsp+0C8h+prclDest]; prcl
0x1800067dc  mov     r8d, 0FFFFFFh; iColor
0x1800067e2  mov     rcx, rdi; pso
0x1800067e5  call    cs:__imp_EngEraseSurface
0x1800067eb  jmp     loc_180006939
0x1800067f0  mov     ecx, 1
0x1800067f5  cmp     [rdi+4Ch], cx
0x1800067f9  jz      short loc_18000680D
0x1800067fb  mov     ecx, 57h ; 'W'; dwErrCode
0x180006800  call    cs:__imp_SetLastError
0x180006806  xor     eax, eax
0x180006808  jmp     loc_180006939
0x18000680d  mov     rbx, [rdi+10h]
0x180006811  mov     rax, [rbx+60h]
0x180006815  cmp     dword ptr [rax+7Ch], 2
0x180006819  jnz     short loc_180006827
0x18000681b  cmp     [rbx+87Ch], ecx
0x180006821  ja      loc_180006937
0x180006827  test    dword ptr [rbx+868h], 0C0000000h
0x180006831  jnz     loc_180006937
0x180006837  cmp     dword ptr [rbx+2C0h], 3
0x18000683e  jz      loc_180006937
0x180006844  mov     r10, [rbx+0D90h]
0x18000684b  test    r10, r10
0x18000684e  jz      short loc_1800068C4
0x180006850  cmp     [r10+20h], r9
0x180006854  jz      short loc_1800068C4
0x180006856  mov     eax, [rbx+0D98h]
0x18000685c  test    cl, al
0x18000685e  jnz     short loc_1800068C4
0x180006860  or      eax, ecx
0x180006862  mov     r9, rbp
0x180006865  mov     [rbx+0D98h], eax
0x18000686b  mov     r8, r14
0x18000686e  mov     rax, [r10+28h]
0x180006872  mov     rdx, rsi
0x180006875  mov     rcx, [rax+20h]
0x180006879  mov     [rbx+20h], rcx
0x18000687d  mov     rax, [r10+28h]
0x180006881  mov     rcx, [rax+28h]
0x180006885  mov     [rbx+8], rcx
0x180006889  mov     rax, [r10+28h]
0x18000688d  mov     rcx, [rax+38h]
0x180006891  mov     [rbx+30h], rcx
0x180006895  mov     rcx, [rsp+0C8h+pptlSrc]
0x18000689d  mov     rax, [r10+20h]
0x1800068a1  mov     [rsp+0C8h+var_A0], rcx
0x1800068a6  mov     rcx, [rsp+0C8h+prclDest]
0x1800068ae  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x1800068b3  mov     rcx, rdi
0x1800068b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068bb  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x1800068c2  jmp     short loc_180006939
0x1800068c4  mov     r8, [rsp+0C8h+prclDest]
0x1800068cc  mov     rax, [rsp+0C8h+pptlSrc]
0x1800068d4  mov     [rsp+0C8h+var_80], r9; __int64
0x1800068d9  mov     [rsp+0C8h+var_88], r9d; int
0x1800068de  mov     ecx, [rax+4]
0x1800068e1  mov     edx, [rax]
0x1800068e3  mov     eax, [r8+0Ch]
0x1800068e7  sub     eax, [r8+4]
0x1800068eb  add     eax, ecx
0x1800068ed  mov     [rsp+0C8h+var_74], ecx
0x1800068f1  mov     [rsp+0C8h+var_6C], eax
0x1800068f5  mov     rcx, rbx; int
0x1800068f8  mov     eax, [r8+8]
0x1800068fc  sub     eax, [r8]
0x1800068ff  add     eax, edx
0x180006901  mov     [rsp+0C8h+var_78], edx
0x180006905  mov     [rsp+0C8h+var_70], eax
0x180006909  mov     rdx, rsi
0x18000690c  lea     rax, [rsp+0C8h+var_68]
0x180006911  mov     qword ptr [rsp+0C8h+var_90], rax; int
0x180006916  lea     rax, [rsp+0C8h+var_78]
0x18000691b  mov     [rsp+0C8h+var_98], r9; __int64
0x180006920  mov     r9, rbp
0x180006923  mov     [rsp+0C8h+var_A0], r8; __int64
0x180006928  mov     r8, r14
0x18000692b  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180006930  call    BCommonDIBBlt
0x180006935  jmp     short loc_180006939
0x180006937  mov     eax, ecx
0x180006939  add     rsp, 0A0h
0x180006940  pop     r14
0x180006942  pop     rdi
0x180006943  pop     rsi
0x180006944  pop     rbp
0x180006945  pop     rbx
0x180006946  retn
```
