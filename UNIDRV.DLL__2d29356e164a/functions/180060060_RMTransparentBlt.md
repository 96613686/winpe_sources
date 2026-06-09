# RMTransparentBlt

- ea: `0x180060060`
- end: `0x1800601d9`
- name: `RMTransparentBlt`
- size: `377`
- prototype: `__int64 __usercall@<rax>(SURFOBJ *psoDst@<rcx>, SURFOBJ *psoSrc@<rdx>, RECTL *prclDst, RECTL *, ULONG TransColor, ULONG bCalledFromBitBlt)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016e6c`
- `0x180042598`
- `0x18005f378`
- `0x180060060`

## import_xrefs

- `GDI32!EngTransparentBlt` at `0x1800601d1`
- `GDI32!EngTransparentBlt` at `0x1800601d1`
- `GDI32!EngStretchBlt` at `0x18006014f`
- `GDI32!EngStretchBlt` at `0x18006014f`
- `GDI32!EngUnlockSurface` at `0x18006015c`
- `GDI32!EngUnlockSurface` at `0x18006018e`
- `GDI32!EngUnlockSurface` at `0x18006015c`
- `GDI32!EngUnlockSurface` at `0x18006018e`
- `GDI32!EngDeleteSurface` at `0x18006016b`
- `GDI32!EngDeleteSurface` at `0x18006019d`
- `GDI32!EngDeleteSurface` at `0x18006016b`
- `GDI32!EngDeleteSurface` at `0x18006019d`

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
      CreateMaskSurface(psoSrc, v17, v12);
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
  CheckBitmapSurface(psoDst, &prclDest->left);
  return EngTransparentBlt(psoDst, psoSrc, pco, a4, prclDest, prclSrc, v12, bCalledFromBitBlt);
}

```

## disassembly

```asm
0x180060060  mov     [rsp-38h+arg_8], rbx
0x180060065  mov     [rsp-38h+pco], r8
0x18006006a  push    rbp
0x18006006b  push    rsi
0x18006006c  push    rdi
0x18006006d  push    r12
0x18006006f  push    r13
0x180060071  push    r14
0x180060073  push    r15
0x180060075  mov     rbp, rsp
0x180060078  sub     rsp, 70h
0x18006007c  mov     rbx, rcx
0x18006007f  mov     r13, r9
0x180060082  mov     rcx, [rcx+10h]; int
0x180060086  mov     rsi, rdx
0x180060089  test    dword ptr [rcx+70h], 8000h
0x180060090  jz      loc_180060171
0x180060096  mov     eax, [rbx+48h]
0x180060099  mov     r15d, [rbp+TransColor]
0x18006009d  dec     eax
0x18006009f  mov     r12, [rbp+arg_28]
0x1800600a3  mov     r14, [rbp+prclDst]
0x1800600a7  cmp     eax, 1
0x1800600aa  ja      loc_1800601A3
0x1800600b0  mov     eax, [rdx+48h]
0x1800600b3  sub     eax, 2
0x1800600b6  cmp     eax, 4
0x1800600b9  ja      loc_1800601A3
0x1800600bf  mov     r9d, [rdx+24h]; int
0x1800600c3  mov     r8d, [rdx+20h]; int
0x1800600c7  lea     rdx, [rbp+hsurf]; int
0x1800600cb  mov     [rbp+hsurf], 0
0x1800600d3  mov     dword ptr [rsp+70h+pxlo], 1; iFormat
0x1800600db  call    CreateBitmapSURFOBJ
0x1800600e0  mov     rdi, rax
0x1800600e3  test    rax, rax
0x1800600e6  jz      loc_180060194
0x1800600ec  mov     r8d, r15d
0x1800600ef  mov     qword ptr [rbp+var_10.x], 0
0x1800600f7  mov     rdx, rax
0x1800600fa  mov     qword ptr [rbp+arg_0.x], 0
0x180060102  mov     rcx, rsi
0x180060105  call    CreateMaskSurface
0x18006010a  mov     r9, [rbp+pco]; pco
0x18006010e  lea     rax, [rbp+arg_0]
0x180060112  mov     [rsp+70h+iMode], 4; iMode
0x18006011a  xor     ecx, ecx
0x18006011c  mov     [rsp+70h+pptlMask], rax; pptlMask
0x180060121  mov     r8, rdi; psoMask
0x180060124  mov     [rsp+70h+prclSrc], r12; prclSrc
0x180060129  lea     rax, [rbp+var_10]
0x18006012d  mov     [rsp+70h+prclDest], r14; prclDest
0x180060132  mov     rdx, rsi; psoSrc
0x180060135  mov     [rsp+70h+pptlHTOrg], rax; pptlHTOrg
0x18006013a  mov     [rsp+70h+pca], rcx; pca
0x18006013f  mov     qword ptr [rbp+var_10.x], rcx
0x180060143  mov     qword ptr [rbp+arg_0.x], rcx
0x180060147  mov     rcx, rbx; psoDest
0x18006014a  mov     [rsp+70h+pxlo], r13; pxlo
0x18006014f  call    cs:__imp_EngStretchBlt
0x180060155  mov     rcx, rdi; pso
0x180060158  test    eax, eax
0x18006015a  jz      short loc_18006018E
0x18006015c  call    cs:__imp_EngUnlockSurface
0x180060162  mov     rcx, [rbp+hsurf]; hsurf
0x180060166  test    rcx, rcx
0x180060169  jz      short loc_180060171
0x18006016b  call    cs:__imp_EngDeleteSurface
0x180060171  mov     eax, 1
0x180060176  mov     rbx, [rsp+70h+arg_8]
0x18006017e  add     rsp, 70h
0x180060182  pop     r15
0x180060184  pop     r14
0x180060186  pop     r13
0x180060188  pop     r12
0x18006018a  pop     rdi
0x18006018b  pop     rsi
0x18006018c  pop     rbp
0x18006018d  retn
0x18006018e  call    cs:__imp_EngUnlockSurface
0x180060194  mov     rcx, [rbp+hsurf]; hsurf
0x180060198  test    rcx, rcx
0x18006019b  jz      short loc_1800601A3
0x18006019d  call    cs:__imp_EngDeleteSurface
0x1800601a3  mov     rdx, r14
0x1800601a6  mov     rcx, rbx
0x1800601a9  call    CheckBitmapSurface
0x1800601ae  mov     eax, [rbp+bCalledFromBitBlt]
0x1800601b1  mov     r9, r13; pxlo
0x1800601b4  mov     r8, [rbp+pco]; pco
0x1800601b8  mov     rdx, rsi; psoSrc
0x1800601bb  mov     dword ptr [rsp+70h+prclDest], eax; bCalledFromBitBlt
0x1800601bf  mov     rcx, rbx; psoDst
0x1800601c2  mov     dword ptr [rsp+70h+pptlHTOrg], r15d; TransColor
0x1800601c7  mov     [rsp+70h+pca], r12; prclSrc
0x1800601cc  mov     [rsp+70h+pxlo], r14; prclDst
0x1800601d1  call    cs:__imp_EngTransparentBlt
0x1800601d7  jmp     short loc_180060176
```
