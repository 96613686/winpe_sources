# DrvCopyBits

- ea: `0x1800068c0`
- end: `0x180006a74`
- name: `DrvCopyBits`
- size: `436`
- prototype: `BOOL __stdcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *prclDest, POINTL *pptlSrc)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002938`
- `0x180005d44`
- `0x1800068c0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006926`
- `KERNEL32!SetLastError` at `0x180006926`
- `GDI32!EngEraseSurface` at `0x180006905`
- `GDI32!EngEraseSurface` at `0x180006905`

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
        return BCommonDIBBlt(dhpdev, psoSrc, (__int64)pco, (__int64)pxlo, v17, &prclDest->left, 0, (__int64)v18, 0, 0);
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
0x1800068c0  push    rbx
0x1800068c2  push    rbp
0x1800068c3  push    rsi
0x1800068c4  push    rdi
0x1800068c5  push    r14
0x1800068c7  sub     rsp, 0A0h
0x1800068ce  mov     rsi, rdx
0x1800068d1  mov     r14, r8
0x1800068d4  xor     edx, edx; Val
0x1800068d6  mov     rdi, rcx
0x1800068d9  lea     rcx, [rsp+0C8h+var_68]; void *
0x1800068de  mov     rbp, r9
0x1800068e1  lea     r8d, [rdx+40h]; Size
0x1800068e5  call    memset_0
0x1800068ea  xor     r9d, r9d
0x1800068ed  cmp     [rsi+4Ch], r9w
0x1800068f2  jz      short loc_180006916
0x1800068f4  mov     rdx, [rsp+0C8h+prclDest]; prcl
0x1800068fc  mov     r8d, 0FFFFFFh; iColor
0x180006902  mov     rcx, rdi; pso
0x180006905  call    cs:__imp_EngEraseSurface
0x18000690c  nop     dword ptr [rax+rax+00h]
0x180006911  jmp     loc_180006A65
0x180006916  mov     ecx, 1
0x18000691b  cmp     [rdi+4Ch], cx
0x18000691f  jz      short loc_180006939
0x180006921  mov     ecx, 57h ; 'W'; dwErrCode
0x180006926  call    cs:__imp_SetLastError
0x18000692d  nop     dword ptr [rax+rax+00h]
0x180006932  xor     eax, eax
0x180006934  jmp     loc_180006A65
0x180006939  mov     rbx, [rdi+10h]
0x18000693d  mov     rax, [rbx+60h]
0x180006941  cmp     dword ptr [rax+7Ch], 2
0x180006945  jnz     short loc_180006953
0x180006947  cmp     [rbx+87Ch], ecx
0x18000694d  ja      loc_180006A63
0x180006953  test    dword ptr [rbx+868h], 0C0000000h
0x18000695d  jnz     loc_180006A63
0x180006963  cmp     dword ptr [rbx+2C0h], 3
0x18000696a  jz      loc_180006A63
0x180006970  mov     r10, [rbx+0D90h]
0x180006977  test    r10, r10
0x18000697a  jz      short loc_1800069F0
0x18000697c  cmp     [r10+20h], r9
0x180006980  jz      short loc_1800069F0
0x180006982  mov     eax, [rbx+0D98h]
0x180006988  test    cl, al
0x18000698a  jnz     short loc_1800069F0
0x18000698c  or      eax, ecx
0x18000698e  mov     r9, rbp
0x180006991  mov     [rbx+0D98h], eax
0x180006997  mov     r8, r14
0x18000699a  mov     rax, [r10+28h]
0x18000699e  mov     rdx, rsi
0x1800069a1  mov     rcx, [rax+20h]
0x1800069a5  mov     [rbx+20h], rcx
0x1800069a9  mov     rax, [r10+28h]
0x1800069ad  mov     rcx, [rax+28h]
0x1800069b1  mov     [rbx+8], rcx
0x1800069b5  mov     rax, [r10+28h]
0x1800069b9  mov     rcx, [rax+38h]
0x1800069bd  mov     [rbx+30h], rcx
0x1800069c1  mov     rcx, [rsp+0C8h+pptlSrc]
0x1800069c9  mov     rax, [r10+20h]
0x1800069cd  mov     [rsp+0C8h+var_A0], rcx
0x1800069d2  mov     rcx, [rsp+0C8h+prclDest]
0x1800069da  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x1800069df  mov     rcx, rdi
0x1800069e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e7  and     dword ptr [rbx+0D98h], 0FFFFFFFEh
0x1800069ee  jmp     short loc_180006A65
0x1800069f0  mov     r8, [rsp+0C8h+prclDest]
0x1800069f8  mov     rax, [rsp+0C8h+pptlSrc]
0x180006a00  mov     [rsp+0C8h+var_80], r9; __int64
0x180006a05  mov     [rsp+0C8h+var_88], r9d; int
0x180006a0a  mov     ecx, [rax+4]
0x180006a0d  mov     edx, [rax]
0x180006a0f  mov     eax, [r8+0Ch]
0x180006a13  sub     eax, [r8+4]
0x180006a17  add     eax, ecx
0x180006a19  mov     [rsp+0C8h+var_74], ecx
0x180006a1d  mov     [rsp+0C8h+var_6C], eax
0x180006a21  mov     rcx, rbx; int
0x180006a24  mov     eax, [r8+8]
0x180006a28  sub     eax, [r8]
0x180006a2b  add     eax, edx
0x180006a2d  mov     [rsp+0C8h+var_78], edx
0x180006a31  mov     [rsp+0C8h+var_70], eax
0x180006a35  mov     rdx, rsi
0x180006a38  lea     rax, [rsp+0C8h+var_68]
0x180006a3d  mov     qword ptr [rsp+0C8h+var_90], rax; int
0x180006a42  lea     rax, [rsp+0C8h+var_78]
0x180006a47  mov     [rsp+0C8h+var_98], r9; __int64
0x180006a4c  mov     r9, rbp
0x180006a4f  mov     [rsp+0C8h+var_A0], r8; __int64
0x180006a54  mov     r8, r14
0x180006a57  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180006a5c  call    BCommonDIBBlt
0x180006a61  jmp     short loc_180006A65
0x180006a63  mov     eax, ecx
0x180006a65  add     rsp, 0A0h
0x180006a6c  pop     r14
0x180006a6e  pop     rdi
0x180006a6f  pop     rsi
0x180006a70  pop     rbp
0x180006a71  pop     rbx
0x180006a72  retn
```
