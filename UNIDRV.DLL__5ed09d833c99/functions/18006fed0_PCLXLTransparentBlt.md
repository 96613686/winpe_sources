# PCLXLTransparentBlt

- ea: `0x18006fed0`
- end: `0x1800700b3`
- name: `PCLXLTransparentBlt`
- size: `483`
- prototype: `__int64 __fastcall(__int64, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, RECTL *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000fe80`
- `0x18004375c`
- `0x1800607a4`
- `0x18006fed0`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x180070017`
- `GDI32!EngUnlockSurface` at `0x180070017`
- `GDI32!EngDeleteSurface` at `0x18007002c`
- `GDI32!EngDeleteSurface` at `0x18007002c`

## pseudocode

```c
__int64 __fastcall PCLXLTransparentBlt(
        __int64 a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *a5,
        RECTL *a6,
        int a7)
{
  __int64 v7; // r14
  __int64 v9; // r15
  int v10; // edi
  struct _RECTL *v11; // r13
  RECTL *v12; // rsi
  int v13; // r12d
  LONG cy; // r9d
  SURFOBJ *v15; // rax
  SURFOBJ *v16; // rsi
  struct _XLATEOBJ *v17; // r9
  struct _CLIPOBJ *v18; // r8
  int v19; // eax
  HSURF hsurf; // [rsp+50h] [rbp-20h] BYREF
  _XLATEOBJ v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+B0h] [rbp+40h] BYREF
  struct _CLIPOBJ *v24; // [rsp+C0h] [rbp+50h]
  struct _XLATEOBJ *v25; // [rsp+C8h] [rbp+58h]

  v25 = a4;
  v24 = a3;
  v7 = *(_QWORD *)(a1 + 16);
  v9 = *(_QWORD *)(v7 + 8);
  v23 = 0xFFFFFF00000000LL;
  v22.cEntries = 2;
  v22.flXlate = 2;
  v22.iUniq = 0;
  *(_DWORD *)&v22.iSrcType = 0;
  v22.pulXlate = (ULONG *)&v23;
  if ( !v9 || !a2 )
    return 0;
  if ( a2->iBitmapFormat == 1 )
  {
    v10 = a7;
    if ( a7 )
      v23 = 0xFFFFFF;
    v11 = a5;
    v12 = a6;
    v13 = CommonRopBlt((struct _DEVOBJ *)v7, a2, a3, &v22, 0, a6, a5, 0, 0xEEu);
  }
  else
  {
    cy = a2->sizlBitmap.cy;
    hsurf = 0;
    v13 = -2147467259;
    v15 = CreateBitmapSURFOBJ(v7, &hsurf, a2->sizlBitmap.cx, cy, 1u);
    v10 = a7;
    v16 = v15;
    v11 = a5;
    if ( v15 )
    {
      if ( (unsigned int)CreateMaskSurface((__int64)a2, (__int64)v15, a7) )
        v13 = CommonRopBlt((struct _DEVOBJ *)v7, v16, v24, &v22, 0, a6, v11, 0, 0xEEu);
      EngUnlockSurface(v16);
    }
    if ( hsurf )
      EngDeleteSurface(hsurf);
    v12 = a6;
  }
  if ( v13 >= 0
    && (v17 = v25,
        v18 = v24,
        *(_DWORD *)(v9 + 16) |= 0x40u,
        *(_DWORD *)(v9 + 184) = v10,
        v19 = CommonRopBlt((struct _DEVOBJ *)v7, a2, v18, v17, 0, v12, v11, 0, 0x88u),
        *(_DWORD *)(v9 + 16) &= ~0x40u,
        *(_DWORD *)(v9 + 184) = 0,
        v19 >= 0) )
  {
    return 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18006fed0  mov     [rsp-38h+arg_8], rbx
0x18006fed5  mov     [rsp-38h+arg_18], r9
0x18006feda  mov     [rsp-38h+arg_10], r8
0x18006fedf  push    rbp
0x18006fee0  push    rsi
0x18006fee1  push    rdi
0x18006fee2  push    r12
0x18006fee4  push    r13
0x18006fee6  push    r14
0x18006fee8  push    r15
0x18006feea  mov     rbp, rsp
0x18006feed  sub     rsp, 70h
0x18006fef1  mov     r14, [rcx+10h]
0x18006fef5  mov     rax, r8
0x18006fef8  xor     r8d, r8d
0x18006fefb  lea     rcx, [rbp+arg_0]
0x18006feff  mov     rbx, rdx
0x18006ff02  mov     r9d, 0FFFFFFh
0x18006ff08  mov     r15, [r14+8]
0x18006ff0c  mov     dword ptr [rbp+arg_0], r8d
0x18006ff10  lea     edx, [r8+2]
0x18006ff14  mov     [rbp+var_18.cEntries], edx
0x18006ff17  mov     [rbp+var_18.flXlate], edx
0x18006ff1a  mov     dword ptr [rbp+arg_0+4], r9d
0x18006ff1e  mov     [rbp+var_18.iUniq], r8d
0x18006ff22  mov     dword ptr [rbp+var_18.iSrcType], r8d
0x18006ff26  mov     [rbp+var_18.pulXlate], rcx
0x18006ff2a  test    r15, r15
0x18006ff2d  jz      loc_180070098
0x18006ff33  test    rbx, rbx
0x18006ff36  jz      loc_180070098
0x18006ff3c  cmp     dword ptr [rbx+48h], 1
0x18006ff40  jnz     short loc_18006FF90
0x18006ff42  mov     edi, [rbp+arg_30]
0x18006ff45  test    edi, edi
0x18006ff47  jz      short loc_18006FF4D
0x18006ff49  mov     [rbp+arg_0], r9
0x18006ff4d  mov     r13, [rbp+arg_20]
0x18006ff51  lea     r9, [rbp+var_18]; struct _XLATEOBJ *
0x18006ff55  mov     rsi, [rbp+arg_28]
0x18006ff59  mov     rdx, rbx; struct _SURFOBJ *
0x18006ff5c  mov     [rsp+70h+var_28], r8; struct _POINTFIX *
0x18006ff61  mov     rcx, r14; struct _DEVOBJ *
0x18006ff64  mov     [rsp+70h+var_30], 0EEh; unsigned int
0x18006ff6c  mov     [rsp+70h+var_38], r8; struct _POINTL *
0x18006ff71  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x18006ff76  mov     [rsp+70h+var_48], rsi; RECTL *
0x18006ff7b  mov     qword ptr [rsp+70h+iFormat], r8; struct _BRUSHOBJ *
0x18006ff80  mov     r8, rax; struct _CLIPOBJ *
0x18006ff83  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x18006ff88  mov     r12d, eax
0x18006ff8b  jmp     loc_18007003C
0x18006ff90  mov     r9d, [rbx+24h]; int
0x18006ff94  lea     rdx, [rbp+hsurf]; int
0x18006ff98  mov     [rbp+hsurf], r8
0x18006ff9c  mov     rcx, r14; int
0x18006ff9f  mov     r8d, [rbx+20h]; int
0x18006ffa3  mov     r12d, 80004005h
0x18006ffa9  mov     [rsp+70h+iFormat], 1; iFormat
0x18006ffb1  call    CreateBitmapSURFOBJ
0x18006ffb6  mov     edi, [rbp+arg_30]
0x18006ffb9  mov     rsi, rax
0x18006ffbc  mov     r13, [rbp+arg_20]
0x18006ffc0  test    rax, rax
0x18006ffc3  jz      short loc_180070023
0x18006ffc5  mov     r8d, edi
0x18006ffc8  mov     rdx, rax
0x18006ffcb  mov     rcx, rbx
0x18006ffce  call    CreateMaskSurface
0x18006ffd3  xor     ecx, ecx
0x18006ffd5  test    eax, eax
0x18006ffd7  jz      short loc_180070014
0x18006ffd9  mov     rax, [rbp+arg_28]
0x18006ffdd  lea     r9, [rbp+var_18]; struct _XLATEOBJ *
0x18006ffe1  mov     r8, [rbp+arg_10]; struct _CLIPOBJ *
0x18006ffe5  mov     rdx, rsi; struct _SURFOBJ *
0x18006ffe8  mov     [rsp+70h+var_28], rcx; struct _POINTFIX *
0x18006ffed  mov     [rsp+70h+var_30], 0EEh; unsigned int
0x18006fff5  mov     [rsp+70h+var_38], rcx; struct _POINTL *
0x18006fffa  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x18006ffff  mov     [rsp+70h+var_48], rax; RECTL *
0x180070004  mov     qword ptr [rsp+70h+iFormat], rcx; struct _BRUSHOBJ *
0x180070009  mov     rcx, r14; struct _DEVOBJ *
0x18007000c  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x180070011  mov     r12d, eax
0x180070014  mov     rcx, rsi; pso
0x180070017  call    cs:__imp_EngUnlockSurface
0x18007001e  nop     dword ptr [rax+rax+00h]
0x180070023  mov     rcx, [rbp+hsurf]; hsurf
0x180070027  test    rcx, rcx
0x18007002a  jz      short loc_180070038
0x18007002c  call    cs:__imp_EngDeleteSurface
0x180070033  nop     dword ptr [rax+rax+00h]
0x180070038  mov     rsi, [rbp+arg_28]
0x18007003c  test    r12d, r12d
0x18007003f  js      short loc_180070098
0x180070041  mov     r9, [rbp+arg_18]; struct _XLATEOBJ *
0x180070045  mov     rdx, rbx; struct _SURFOBJ *
0x180070048  mov     r8, [rbp+arg_10]; struct _CLIPOBJ *
0x18007004c  mov     rcx, r14; struct _DEVOBJ *
0x18007004f  or      dword ptr [r15+10h], 40h
0x180070054  mov     [r15+0B8h], edi
0x18007005b  xor     edi, edi
0x18007005d  mov     [rsp+70h+var_28], rdi; struct _POINTFIX *
0x180070062  mov     [rsp+70h+var_30], 88h; unsigned int
0x18007006a  mov     [rsp+70h+var_38], rdi; struct _POINTL *
0x18007006f  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x180070074  mov     [rsp+70h+var_48], rsi; RECTL *
0x180070079  mov     qword ptr [rsp+70h+iFormat], rdi; struct _BRUSHOBJ *
0x18007007e  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x180070083  and     dword ptr [r15+10h], 0FFFFFFBFh
0x180070088  mov     [r15+0B8h], edi
0x18007008f  test    eax, eax
0x180070091  js      short loc_180070098
0x180070093  lea     eax, [rdi+1]
0x180070096  jmp     short loc_18007009A
0x180070098  xor     eax, eax
0x18007009a  mov     rbx, [rsp+70h+arg_8]
0x1800700a2  add     rsp, 70h
0x1800700a6  pop     r15
0x1800700a8  pop     r14
0x1800700aa  pop     r13
0x1800700ac  pop     r12
0x1800700ae  pop     rdi
0x1800700af  pop     rsi
0x1800700b0  pop     rbp
0x1800700b1  retn
```
