# GdipUtil::DrawFocusRect(Gdiplus::Graphics &,Gdiplus::Rect const &,ulong,ulong)

- ea: `0x18003628c`
- end: `0x18003634a`
- name: `?DrawFocusRect@GdipUtil@@YAXAEAVGraphics@Gdiplus@@AEBVRect@3@KK@Z`
- size: `190`
- prototype: `void __fastcall(GdipUtil *__hidden this, struct Gdiplus::Graphics *, const struct Gdiplus::Rect *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180028630`
- `0x18006df00`
- `0x1800751b0`
- `0x180075a00`

## callees

- `0x18003628c`
- `0x180036350`

## import_xrefs

- `gdiplus!GdipDeletePen` at `0x18003632e`
- `gdiplus!GdipDeletePen` at `0x18003632e`
- `gdiplus!GdipDrawRectangleI` at `0x18003631c`
- `gdiplus!GdipDrawRectangleI` at `0x18003631c`
- `gdiplus!GdipCreatePen2` at `0x1800362df`
- `gdiplus!GdipCreatePen2` at `0x1800362df`
- `gdiplus!GdipCreateHatchBrush` at `0x1800362bb`
- `gdiplus!GdipCreateHatchBrush` at `0x1800362bb`
- `gdiplus!GdipDeleteBrush` at `0x180036339`
- `gdiplus!GdipDeleteBrush` at `0x180036339`

## pseudocode

```c
void __fastcall GdipUtil::DrawFocusRect(
        GdipUtil *this,
        struct Gdiplus::Graphics *a2,
        const struct Gdiplus::Rect *a3,
        unsigned int a4)
{
  __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h]

  v9 = 0;
  GdipCreateHatchBrush(12, (unsigned int)a3, a4, &v9);
  v10 = 0;
  v7 = GdipCreatePen2(v9, v6, 0, &v10);
  v11 = 0;
  if ( !v7 )
  {
    Gdiplus::Pen::SetAlignment(&v10);
    v8 = GdipDrawRectangleI(
           *(_QWORD *)this,
           v10,
           *(unsigned int *)a2,
           *((unsigned int *)a2 + 1),
           *((_DWORD *)a2 + 2) - 1,
           *((_DWORD *)a2 + 3) - 1);
    if ( v8 )
      *((_DWORD *)this + 2) = v8;
  }
  GdipDeletePen(v10);
  GdipDeleteBrush(v9);
}

```

## disassembly

```asm
0x18003628c  mov     [rsp+arg_0], rsi
0x180036291  push    rdi
0x180036292  sub     rsp, 50h
0x180036296  mov     eax, r9d
0x180036299  mov     [rsp+58h+var_28], 0
0x1800362a2  mov     r10d, r8d
0x1800362a5  lea     r9, [rsp+58h+var_28]
0x1800362aa  mov     rdi, rdx
0x1800362ad  mov     rsi, rcx
0x1800362b0  mov     r8d, eax
0x1800362b3  mov     edx, r10d
0x1800362b6  mov     ecx, 0Ch
0x1800362bb  call    cs:__imp_GdipCreateHatchBrush
0x1800362c1  movss   xmm1, cs:__real@3f800000
0x1800362c9  lea     r9, [rsp+58h+var_20]
0x1800362ce  mov     rcx, [rsp+58h+var_28]
0x1800362d3  xor     r8d, r8d
0x1800362d6  mov     [rsp+58h+var_20], 0
0x1800362df  call    cs:__imp_GdipCreatePen2
0x1800362e5  mov     [rsp+58h+var_18], 0
0x1800362ed  test    eax, eax
0x1800362ef  jnz     short loc_180036329
0x1800362f1  lea     rcx, [rsp+58h+var_20]
0x1800362f6  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x1800362fb  mov     ecx, [rdi+0Ch]
0x1800362fe  mov     eax, [rdi+8]
0x180036301  dec     ecx
0x180036303  mov     r9d, [rdi+4]
0x180036307  dec     eax
0x180036309  mov     r8d, [rdi]
0x18003630c  mov     rdx, [rsp+58h+var_20]
0x180036311  mov     [rsp+58h+var_30], ecx
0x180036315  mov     rcx, [rsi]
0x180036318  mov     [rsp+58h+var_38], eax
0x18003631c  call    cs:__imp_GdipDrawRectangleI
0x180036322  test    eax, eax
0x180036324  jz      short loc_180036329
0x180036326  mov     [rsi+8], eax
0x180036329  mov     rcx, [rsp+58h+var_20]
0x18003632e  call    cs:__imp_GdipDeletePen
0x180036334  mov     rcx, [rsp+58h+var_28]
0x180036339  call    cs:__imp_GdipDeleteBrush
0x18003633f  mov     rsi, [rsp+58h+arg_0]
0x180036344  add     rsp, 50h
0x180036348  pop     rdi
0x180036349  retn
```
