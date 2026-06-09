# PCLXLTransparentBlt

- ea: `0x18006dfb0`
- end: `0x18006e186`
- name: `PCLXLTransparentBlt`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000fde0`
- `0x180042598`
- `0x18005f378`
- `0x18006dfb0`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x18006e0f7`
- `GDI32!EngUnlockSurface` at `0x18006e0f7`
- `GDI32!EngDeleteSurface` at `0x18006e106`
- `GDI32!EngDeleteSurface` at `0x18006e106`

## pseudocode

```c
__int64 __fastcall PCLXLTransparentBlt(
        __int64 a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *a5,
        RECTL *a6,
        unsigned int a7)
{
  __int64 v7; // r14
  __int64 v9; // r15
  unsigned int v10; // edi
  struct _RECTL *v11; // r13
  RECTL *v12; // rsi
  int v13; // r12d
  unsigned int cy; // r9d
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
      if ( (unsigned int)CreateMaskSurface(a2, v15, a7) )
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
0x18006dfb0  mov     [rsp-38h+arg_8], rbx
0x18006dfb5  mov     [rsp-38h+arg_18], r9
0x18006dfba  mov     [rsp-38h+arg_10], r8
0x18006dfbf  push    rbp
0x18006dfc0  push    rsi
0x18006dfc1  push    rdi
0x18006dfc2  push    r12
0x18006dfc4  push    r13
0x18006dfc6  push    r14
0x18006dfc8  push    r15
0x18006dfca  mov     rbp, rsp
0x18006dfcd  sub     rsp, 70h
0x18006dfd1  mov     r14, [rcx+10h]
0x18006dfd5  mov     rax, r8
0x18006dfd8  xor     r8d, r8d
0x18006dfdb  lea     rcx, [rbp+arg_0]
0x18006dfdf  mov     rbx, rdx
0x18006dfe2  mov     r9d, 0FFFFFFh
0x18006dfe8  mov     r15, [r14+8]
0x18006dfec  mov     dword ptr [rbp+arg_0], r8d
0x18006dff0  lea     edx, [r8+2]
0x18006dff4  mov     [rbp+var_18.cEntries], edx
0x18006dff7  mov     [rbp+var_18.flXlate], edx
0x18006dffa  mov     dword ptr [rbp+arg_0+4], r9d
0x18006dffe  mov     [rbp+var_18.iUniq], r8d
0x18006e002  mov     dword ptr [rbp+var_18.iSrcType], r8d
0x18006e006  mov     [rbp+var_18.pulXlate], rcx
0x18006e00a  test    r15, r15
0x18006e00d  jz      loc_18006E16C
0x18006e013  test    rbx, rbx
0x18006e016  jz      loc_18006E16C
0x18006e01c  cmp     dword ptr [rbx+48h], 1
0x18006e020  jnz     short loc_18006E070
0x18006e022  mov     edi, [rbp+arg_30]
0x18006e025  test    edi, edi
0x18006e027  jz      short loc_18006E02D
0x18006e029  mov     [rbp+arg_0], r9
0x18006e02d  mov     r13, [rbp+arg_20]
0x18006e031  lea     r9, [rbp+var_18]; struct _XLATEOBJ *
0x18006e035  mov     rsi, [rbp+arg_28]
0x18006e039  mov     rdx, rbx; struct _SURFOBJ *
0x18006e03c  mov     [rsp+70h+var_28], r8; struct _POINTFIX *
0x18006e041  mov     rcx, r14; struct _DEVOBJ *
0x18006e044  mov     [rsp+70h+var_30], 0EEh; unsigned int
0x18006e04c  mov     [rsp+70h+var_38], r8; struct _POINTL *
0x18006e051  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x18006e056  mov     [rsp+70h+var_48], rsi; RECTL *
0x18006e05b  mov     qword ptr [rsp+70h+iFormat], r8; struct _BRUSHOBJ *
0x18006e060  mov     r8, rax; struct _CLIPOBJ *
0x18006e063  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x18006e068  mov     r12d, eax
0x18006e06b  jmp     loc_18006E110
0x18006e070  mov     r9d, [rbx+24h]; int
0x18006e074  lea     rdx, [rbp+hsurf]; int
0x18006e078  mov     [rbp+hsurf], r8
0x18006e07c  mov     rcx, r14; int
0x18006e07f  mov     r8d, [rbx+20h]; int
0x18006e083  mov     r12d, 80004005h
0x18006e089  mov     [rsp+70h+iFormat], 1; iFormat
0x18006e091  call    CreateBitmapSURFOBJ
0x18006e096  mov     edi, [rbp+arg_30]
0x18006e099  mov     rsi, rax
0x18006e09c  mov     r13, [rbp+arg_20]
0x18006e0a0  test    rax, rax
0x18006e0a3  jz      short loc_18006E0FD
0x18006e0a5  mov     r8d, edi
0x18006e0a8  mov     rdx, rax
0x18006e0ab  mov     rcx, rbx
0x18006e0ae  call    CreateMaskSurface
0x18006e0b3  xor     ecx, ecx
0x18006e0b5  test    eax, eax
0x18006e0b7  jz      short loc_18006E0F4
0x18006e0b9  mov     rax, [rbp+arg_28]
0x18006e0bd  lea     r9, [rbp+var_18]; struct _XLATEOBJ *
0x18006e0c1  mov     r8, [rbp+arg_10]; struct _CLIPOBJ *
0x18006e0c5  mov     rdx, rsi; struct _SURFOBJ *
0x18006e0c8  mov     [rsp+70h+var_28], rcx; struct _POINTFIX *
0x18006e0cd  mov     [rsp+70h+var_30], 0EEh; unsigned int
0x18006e0d5  mov     [rsp+70h+var_38], rcx; struct _POINTL *
0x18006e0da  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x18006e0df  mov     [rsp+70h+var_48], rax; RECTL *
0x18006e0e4  mov     qword ptr [rsp+70h+iFormat], rcx; struct _BRUSHOBJ *
0x18006e0e9  mov     rcx, r14; struct _DEVOBJ *
0x18006e0ec  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x18006e0f1  mov     r12d, eax
0x18006e0f4  mov     rcx, rsi; pso
0x18006e0f7  call    cs:__imp_EngUnlockSurface
0x18006e0fd  mov     rcx, [rbp+hsurf]; hsurf
0x18006e101  test    rcx, rcx
0x18006e104  jz      short loc_18006E10C
0x18006e106  call    cs:__imp_EngDeleteSurface
0x18006e10c  mov     rsi, [rbp+arg_28]
0x18006e110  test    r12d, r12d
0x18006e113  js      short loc_18006E16C
0x18006e115  mov     r9, [rbp+arg_18]; struct _XLATEOBJ *
0x18006e119  mov     rdx, rbx; struct _SURFOBJ *
0x18006e11c  mov     r8, [rbp+arg_10]; struct _CLIPOBJ *
0x18006e120  mov     rcx, r14; struct _DEVOBJ *
0x18006e123  or      dword ptr [r15+10h], 40h
0x18006e128  mov     [r15+0B8h], edi
0x18006e12f  xor     edi, edi
0x18006e131  mov     [rsp+70h+var_28], rdi; struct _POINTFIX *
0x18006e136  mov     [rsp+70h+var_30], 88h; unsigned int
0x18006e13e  mov     [rsp+70h+var_38], rdi; struct _POINTL *
0x18006e143  mov     [rsp+70h+var_40], r13; struct _RECTL *
0x18006e148  mov     [rsp+70h+var_48], rsi; RECTL *
0x18006e14d  mov     qword ptr [rsp+70h+iFormat], rdi; struct _BRUSHOBJ *
0x18006e152  call    ?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z; CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)
0x18006e157  and     dword ptr [r15+10h], 0FFFFFFBFh
0x18006e15c  mov     [r15+0B8h], edi
0x18006e163  test    eax, eax
0x18006e165  js      short loc_18006E16C
0x18006e167  lea     eax, [rdi+1]
0x18006e16a  jmp     short loc_18006E16E
0x18006e16c  xor     eax, eax
0x18006e16e  mov     rbx, [rsp+70h+arg_8]
0x18006e176  add     rsp, 70h
0x18006e17a  pop     r15
0x18006e17c  pop     r14
0x18006e17e  pop     r13
0x18006e180  pop     r12
0x18006e182  pop     rdi
0x18006e183  pop     rsi
0x18006e184  pop     rbp
0x18006e185  retn
```
