# RMTransparentBlt

- ea: `0x1800614f0`
- end: `0x18006168e`
- name: `RMTransparentBlt`
- size: `414`
- prototype: `BOOL __fastcall(SURFOBJ *psoDst, SURFOBJ *psoSrc, CLIPOBJ *, XLATEOBJ *, RECTL *prclDst, RECTL *, ULONG TransColor, ULONG bCalledFromBitBlt)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017148`
- `0x18004375c`
- `0x1800607a4`
- `0x1800614f0`

## import_xrefs

- `GDI32!EngTransparentBlt` at `0x180061680`
- `GDI32!EngTransparentBlt` at `0x180061680`
- `GDI32!EngStretchBlt` at `0x1800615df`
- `GDI32!EngStretchBlt` at `0x1800615df`
- `GDI32!EngUnlockSurface` at `0x1800615f2`
- `GDI32!EngUnlockSurface` at `0x180061631`
- `GDI32!EngUnlockSurface` at `0x1800615f2`
- `GDI32!EngUnlockSurface` at `0x180061631`
- `GDI32!EngDeleteSurface` at `0x180061607`
- `GDI32!EngDeleteSurface` at `0x180061646`
- `GDI32!EngDeleteSurface` at `0x180061607`
- `GDI32!EngDeleteSurface` at `0x180061646`

## pseudocode

```c
BOOL __fastcall RMTransparentBlt(
        SURFOBJ *psoDst,
        SURFOBJ *psoSrc,
        CLIPOBJ *a3,
        XLATEOBJ *a4,
        RECTL *prclDst,
        RECTL *a6,
        ULONG TransColor,
        ULONG bCalledFromBitBlt)
{
  DHPDEV dhpdev; // rcx
  ULONG v12; // r15d
  RECTL *prclSrc; // r12
  RECTL *prclDest; // r14
  LONG cy; // r9d
  LONG cx; // r8d
  SURFOBJ *v17; // rax
  SURFOBJ *v18; // rdi
  POINTL pptlHTOrg; // [rsp+60h] [rbp-10h] BYREF
  HSURF hsurf; // [rsp+68h] [rbp-8h] BYREF
  POINTL pptlMask; // [rsp+B0h] [rbp+40h] BYREF
  CLIPOBJ *pco; // [rsp+C0h] [rbp+50h]

  pco = a3;
  dhpdev = psoDst->dhpdev;
  if ( ((_DWORD)dhpdev[28] & 0x8000) == 0 )
    return 1;
  v12 = TransColor;
  prclSrc = a6;
  prclDest = prclDst;
  if ( psoDst->iBitmapFormat - 1 <= 1 && psoSrc->iBitmapFormat - 2 <= 4 )
  {
    cy = psoSrc->sizlBitmap.cy;
    cx = psoSrc->sizlBitmap.cx;
    hsurf = 0;
    v17 = CreateBitmapSURFOBJ((__int64)dhpdev, &hsurf, cx, cy, 1u);
    v18 = v17;
    if ( v17 )
    {
      pptlMask = 0;
      CreateMaskSurface((__int64)psoSrc, (__int64)v17, v12);
      pptlHTOrg = 0;
      pptlMask = 0;
      if ( EngStretchBlt(psoDst, psoSrc, v18, pco, a4, 0, &pptlHTOrg, prclDest, prclSrc, &pptlMask, 4u) )
      {
        EngUnlockSurface(v18);
        if ( hsurf )
          EngDeleteSurface(hsurf);
        return 1;
      }
      EngUnlockSurface(v18);
    }
    if ( hsurf )
      EngDeleteSurface(hsurf);
  }
  CheckBitmapSurface(psoDst, &prclDest->left, (__int64)a3, (__int64)a4);
  return EngTransparentBlt(psoDst, psoSrc, pco, a4, prclDest, prclSrc, v12, bCalledFromBitBlt);
}

```

## disassembly

```asm
0x1800614f0  mov     [rsp-38h+arg_8], rbx
0x1800614f5  mov     [rsp-38h+pco], r8
0x1800614fa  push    rbp
0x1800614fb  push    rsi
0x1800614fc  push    rdi
0x1800614fd  push    r12
0x1800614ff  push    r13
0x180061501  push    r14
0x180061503  push    r15
0x180061505  mov     rbp, rsp
0x180061508  sub     rsp, 70h
0x18006150c  mov     rbx, rcx
0x18006150f  mov     r13, r9
0x180061512  mov     rcx, [rcx+10h]; int
0x180061516  mov     rsi, rdx
0x180061519  test    dword ptr [rcx+70h], 8000h
0x180061520  jz      loc_180061613
0x180061526  mov     eax, [rbx+48h]
0x180061529  mov     r15d, [rbp+TransColor]
0x18006152d  dec     eax
0x18006152f  mov     r12, [rbp+arg_28]
0x180061533  mov     r14, [rbp+prclDst]
0x180061537  cmp     eax, 1
0x18006153a  ja      loc_180061652
0x180061540  mov     eax, [rdx+48h]
0x180061543  sub     eax, 2
0x180061546  cmp     eax, 4
0x180061549  ja      loc_180061652
0x18006154f  mov     r9d, [rdx+24h]; int
0x180061553  mov     r8d, [rdx+20h]; int
0x180061557  lea     rdx, [rbp+hsurf]; int
0x18006155b  mov     [rbp+hsurf], 0
0x180061563  mov     dword ptr [rsp+70h+pxlo], 1; iFormat
0x18006156b  call    CreateBitmapSURFOBJ
0x180061570  mov     rdi, rax
0x180061573  test    rax, rax
0x180061576  jz      loc_18006163D
0x18006157c  mov     r8d, r15d
0x18006157f  mov     qword ptr [rbp+var_10.x], 0
0x180061587  mov     rdx, rax
0x18006158a  mov     qword ptr [rbp+arg_0.x], 0
0x180061592  mov     rcx, rsi
0x180061595  call    CreateMaskSurface
0x18006159a  mov     r9, [rbp+pco]; pco
0x18006159e  lea     rax, [rbp+arg_0]
0x1800615a2  mov     [rsp+70h+iMode], 4; iMode
0x1800615aa  xor     ecx, ecx
0x1800615ac  mov     [rsp+70h+pptlMask], rax; pptlMask
0x1800615b1  mov     r8, rdi; psoMask
0x1800615b4  mov     [rsp+70h+prclSrc], r12; prclSrc
0x1800615b9  lea     rax, [rbp+var_10]
0x1800615bd  mov     [rsp+70h+prclDest], r14; prclDest
0x1800615c2  mov     rdx, rsi; psoSrc
0x1800615c5  mov     [rsp+70h+pptlHTOrg], rax; pptlHTOrg
0x1800615ca  mov     [rsp+70h+pca], rcx; pca
0x1800615cf  mov     qword ptr [rbp+var_10.x], rcx
0x1800615d3  mov     qword ptr [rbp+arg_0.x], rcx
0x1800615d7  mov     rcx, rbx; psoDest
0x1800615da  mov     [rsp+70h+pxlo], r13; pxlo
0x1800615df  call    cs:__imp_EngStretchBlt
0x1800615e6  nop     dword ptr [rax+rax+00h]
0x1800615eb  mov     rcx, rdi; pso
0x1800615ee  test    eax, eax
0x1800615f0  jz      short loc_180061631
0x1800615f2  call    cs:__imp_EngUnlockSurface
0x1800615f9  nop     dword ptr [rax+rax+00h]
0x1800615fe  mov     rcx, [rbp+hsurf]; hsurf
0x180061602  test    rcx, rcx
0x180061605  jz      short loc_180061613
0x180061607  call    cs:__imp_EngDeleteSurface
0x18006160e  nop     dword ptr [rax+rax+00h]
0x180061613  mov     eax, 1
0x180061618  mov     rbx, [rsp+70h+arg_8]
0x180061620  add     rsp, 70h
0x180061624  pop     r15
0x180061626  pop     r14
0x180061628  pop     r13
0x18006162a  pop     r12
0x18006162c  pop     rdi
0x18006162d  pop     rsi
0x18006162e  pop     rbp
0x18006162f  retn
0x180061631  call    cs:__imp_EngUnlockSurface
0x180061638  nop     dword ptr [rax+rax+00h]
0x18006163d  mov     rcx, [rbp+hsurf]; hsurf
0x180061641  test    rcx, rcx
0x180061644  jz      short loc_180061652
0x180061646  call    cs:__imp_EngDeleteSurface
0x18006164d  nop     dword ptr [rax+rax+00h]
0x180061652  mov     rdx, r14
0x180061655  mov     rcx, rbx
0x180061658  call    CheckBitmapSurface
0x18006165d  mov     eax, [rbp+bCalledFromBitBlt]
0x180061660  mov     r9, r13; pxlo
0x180061663  mov     r8, [rbp+pco]; pco
0x180061667  mov     rdx, rsi; psoSrc
0x18006166a  mov     dword ptr [rsp+70h+prclDest], eax; bCalledFromBitBlt
0x18006166e  mov     rcx, rbx; psoDst
0x180061671  mov     dword ptr [rsp+70h+pptlHTOrg], r15d; TransColor
0x180061676  mov     [rsp+70h+pca], r12; prclSrc
0x18006167b  mov     [rsp+70h+pxlo], r14; prclDst
0x180061680  call    cs:__imp_EngTransparentBlt
0x180061687  nop     dword ptr [rax+rax+00h]
0x18006168c  jmp     short loc_180061618
```
