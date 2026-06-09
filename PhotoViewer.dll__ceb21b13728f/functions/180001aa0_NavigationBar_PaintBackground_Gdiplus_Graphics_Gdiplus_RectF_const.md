# NavigationBar::PaintBackground(Gdiplus::Graphics &,Gdiplus::RectF const &)

- ea: `0x180001aa0`
- end: `0x180001f1b`
- name: `?PaintBackground@NavigationBar@@AEAAXAEAVGraphics@Gdiplus@@AEBVRectF@3@@Z`
- size: `1147`
- prototype: `void __fastcall(NavigationBar *__hidden this, struct Gdiplus::Graphics *, const struct Gdiplus::RectF *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a524`
- `0x18002a550`
- `0x18006ffb0`

## callees

- `0x180001aa0`
- `0x180001f30`
- `0x180001f6c`
- `0x180002000`
- `0x18000225c`
- `0x180002420`
- `0x1800024d0`

## import_xrefs

- `USER32!GetParent` at `0x180001ada`
- `USER32!GetParent` at `0x180001ada`
- `gdiplus!GdipSetTextureTransform` at `0x180001bce`
- `gdiplus!GdipSetTextureTransform` at `0x180001c7f`
- `gdiplus!GdipSetTextureTransform` at `0x180001d54`
- `gdiplus!GdipSetTextureTransform` at `0x180001e0f`
- `gdiplus!GdipSetTextureTransform` at `0x180001ec2`
- `gdiplus!GdipSetTextureTransform` at `0x180001bce`
- `gdiplus!GdipSetTextureTransform` at `0x180001c7f`
- `gdiplus!GdipSetTextureTransform` at `0x180001d54`
- `gdiplus!GdipSetTextureTransform` at `0x180001e0f`
- `gdiplus!GdipSetTextureTransform` at `0x180001ec2`
- `gdiplus!GdipTranslateMatrix` at `0x180001bc0`
- `gdiplus!GdipTranslateMatrix` at `0x180001c72`
- `gdiplus!GdipTranslateMatrix` at `0x180001d42`
- `gdiplus!GdipTranslateMatrix` at `0x180001e02`
- `gdiplus!GdipTranslateMatrix` at `0x180001eb5`
- `gdiplus!GdipTranslateMatrix` at `0x180001bc0`
- `gdiplus!GdipTranslateMatrix` at `0x180001c72`
- `gdiplus!GdipTranslateMatrix` at `0x180001d42`
- `gdiplus!GdipTranslateMatrix` at `0x180001e02`
- `gdiplus!GdipTranslateMatrix` at `0x180001eb5`
- `gdiplus!GdipDeleteMatrix` at `0x180001c06`
- `gdiplus!GdipDeleteMatrix` at `0x180001cd7`
- `gdiplus!GdipDeleteMatrix` at `0x180001da4`
- `gdiplus!GdipDeleteMatrix` at `0x180001e4b`
- `gdiplus!GdipDeleteMatrix` at `0x180001efa`
- `gdiplus!GdipDeleteMatrix` at `0x180001c06`
- `gdiplus!GdipDeleteMatrix` at `0x180001cd7`
- `gdiplus!GdipDeleteMatrix` at `0x180001da4`
- `gdiplus!GdipDeleteMatrix` at `0x180001e4b`
- `gdiplus!GdipDeleteMatrix` at `0x180001efa`
- `gdiplus!GdipCreateMatrix` at `0x180001ba1`
- `gdiplus!GdipCreateMatrix` at `0x180001c48`
- `gdiplus!GdipCreateMatrix` at `0x180001d18`
- `gdiplus!GdipCreateMatrix` at `0x180001ddb`
- `gdiplus!GdipCreateMatrix` at `0x180001e91`
- `gdiplus!GdipCreateMatrix` at `0x180001ba1`
- `gdiplus!GdipCreateMatrix` at `0x180001c48`
- `gdiplus!GdipCreateMatrix` at `0x180001d18`
- `gdiplus!GdipCreateMatrix` at `0x180001ddb`
- `gdiplus!GdipCreateMatrix` at `0x180001e91`
- `gdiplus!GdipFillRectangleI` at `0x180001bf2`
- `gdiplus!GdipFillRectangleI` at `0x180001cad`
- `gdiplus!GdipFillRectangleI` at `0x180001d93`
- `gdiplus!GdipFillRectangleI` at `0x180001e3b`
- `gdiplus!GdipFillRectangleI` at `0x180001eea`
- `gdiplus!GdipFillRectangleI` at `0x180001bf2`
- `gdiplus!GdipFillRectangleI` at `0x180001cad`
- `gdiplus!GdipFillRectangleI` at `0x180001d93`
- `gdiplus!GdipFillRectangleI` at `0x180001e3b`
- `gdiplus!GdipFillRectangleI` at `0x180001eea`

## pseudocode

```c
void __fastcall NavigationBar::PaintBackground(
        unsigned __int64 this,
        struct Gdiplus::Graphics *a2,
        const struct Gdiplus::RectF *a3)
{
  HWND Parent; // rax
  __int64 DpiOffset; // rbx
  __int64 v7; // r14
  Gdiplus::Image *v8; // rcx
  unsigned int Width; // eax
  Gdiplus::Image *v10; // rcx
  Gdiplus::Image *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  _DWORD *v16; // rbx
  __int64 *v17; // r12
  int v18; // eax
  Gdiplus::Image *v19; // r14
  __int64 v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  _DWORD *v25; // r14
  Gdiplus::Image **v26; // r15
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // ecx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // r15
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // eax
  int v36; // eax
  unsigned int Height; // eax
  Gdiplus::Image *v38; // rcx
  Gdiplus::Image *v39; // rbx
  __int64 v40; // r14
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // eax
  int v44; // eax
  __int64 v45; // [rsp+38h] [rbp-30h]
  Gdiplus::Image *v46; // [rsp+38h] [rbp-30h]
  __int64 v47; // [rsp+48h] [rbp-20h] BYREF
  __int64 v48; // [rsp+50h] [rbp-18h]
  __int64 v49; // [rsp+58h] [rbp-10h]
  __int64 v50; // [rsp+B8h] [rbp+50h] BYREF
  const struct Gdiplus::RectF *v51; // [rsp+C0h] [rbp+58h]
  int v52; // [rsp+C8h] [rbp+60h]

  v51 = a3;
  NavigationBar::EnsureGraphicalObjects((NavigationBar *)this);
  Parent = GetParent(*(HWND *)((this & -(__int64)(this != -168)) + 8));
  UIControls::TransparentBackControlBase<NavigationBar>::PaintBackground(this + 168, Parent, a2);
  DpiOffset = GetDpiOffset();
  Gdiplus::Image::GetWidth(*(Gdiplus::Image **)(this + 296));
  Gdiplus::Image::GetWidth(*(Gdiplus::Image **)(this + 304));
  v49 = DpiOffset;
  v7 = (unsigned int)DpiOffset;
  LODWORD(DpiOffset) = dword_18008B108[DpiOffset] / 2
                     - (Gdiplus::Image::GetWidth(*(Gdiplus::Image **)(this + 320)) >> 1);
  v8 = *(Gdiplus::Image **)(this + 320);
  LODWORD(v51) = DpiOffset;
  Width = Gdiplus::Image::GetWidth(v8);
  v10 = *(Gdiplus::Image **)(this + 296);
  v52 = DpiOffset + Width;
  Gdiplus::Image::GetHeight(v10);
  Gdiplus::Image::GetWidth(*(Gdiplus::Image **)(this + 296));
  v11 = *(Gdiplus::Image **)(this + 336);
  v50 = 0;
  GdipCreateMatrix(&v50);
  v45 = v50;
  GdipTranslateMatrix(v50, v12, v13, 0);
  v14 = GdipSetTextureTransform(*((_QWORD *)v11 + 1), v45);
  if ( v14 )
    *((_DWORD *)v11 + 4) = v14;
  v15 = GdipFillRectangleI(*(_QWORD *)a2, *((_QWORD *)v11 + 1));
  v16 = (_DWORD *)((char *)a2 + 8);
  if ( v15 )
    *v16 = v15;
  GdipDeleteMatrix(v45);
  Gdiplus::Image::GetHeight(*(Gdiplus::Image **)(this + 312));
  v17 = (__int64 *)(this + 352);
  v47 = 0;
  v18 = dword_18008B1C8[v7];
  v19 = *(Gdiplus::Image **)(this + 352);
  LODWORD(v50) = v18;
  GdipCreateMatrix(&v47);
  v20 = v47;
  v48 = v47;
  GdipTranslateMatrix(v47, v21, v22, 0);
  v23 = GdipSetTextureTransform(*((_QWORD *)v19 + 1), v20);
  if ( v23 )
    *((_DWORD *)v19 + 4) = v23;
  v24 = GdipFillRectangleI(*(_QWORD *)a2, *((_QWORD *)v19 + 1));
  if ( v24 )
  {
    *v16 = v24;
    v25 = (_DWORD *)((char *)a2 + 8);
    v26 = (Gdiplus::Image **)(this + 312);
    v17 = (__int64 *)(this + 352);
  }
  else
  {
    v26 = (Gdiplus::Image **)(this + 312);
    v25 = (_DWORD *)((char *)a2 + 8);
  }
  GdipDeleteMatrix(v48);
  LODWORD(v50) = Gdiplus::Image::GetHeight(*(Gdiplus::Image **)(this + 320));
  v47 = 0;
  v46 = *(Gdiplus::Image **)(this + 360);
  GdipCreateMatrix(&v47);
  v48 = v47;
  GdipTranslateMatrix(v47, v27, v28, 0);
  v29 = GdipSetTextureTransform(*((_QWORD *)v46 + 1), v48);
  if ( v29 )
  {
    *((_DWORD *)v46 + 4) = v29;
  }
  else
  {
    v26 = (Gdiplus::Image **)(this + 312);
    v17 = (__int64 *)(this + 352);
    v25 = (_DWORD *)((char *)a2 + 8);
  }
  v30 = GdipFillRectangleI(*(_QWORD *)a2, *((_QWORD *)v46 + 1));
  if ( v30 )
    *v25 = v30;
  GdipDeleteMatrix(v48);
  Gdiplus::Image::GetHeight(*v26);
  v31 = *v17;
  v50 = 0;
  LODWORD(v51) = dword_18008B1C8[v49];
  GdipCreateMatrix(&v50);
  v32 = v50;
  GdipTranslateMatrix(v50, v33, v34, 0);
  v35 = GdipSetTextureTransform(*(_QWORD *)(v31 + 8), v32);
  if ( v35 )
    *(_DWORD *)(v31 + 16) = v35;
  v36 = GdipFillRectangleI(*(_QWORD *)a2, *(_QWORD *)(v31 + 8));
  if ( v36 )
    *v25 = v36;
  GdipDeleteMatrix(v32);
  Height = Gdiplus::Image::GetHeight(*(Gdiplus::Image **)(this + 304));
  v38 = *(Gdiplus::Image **)(this + 304);
  LODWORD(v51) = Height;
  Gdiplus::Image::GetWidth(v38);
  v39 = *(Gdiplus::Image **)(this + 344);
  v50 = 0;
  GdipCreateMatrix(&v50);
  v40 = v50;
  GdipTranslateMatrix(v50, v41, v42, 0);
  v43 = GdipSetTextureTransform(*((_QWORD *)v39 + 1), v40);
  if ( v43 )
    *((_DWORD *)v39 + 4) = v43;
  v44 = GdipFillRectangleI(*(_QWORD *)a2, *((_QWORD *)v39 + 1));
  if ( v44 )
    *((_DWORD *)a2 + 2) = v44;
  GdipDeleteMatrix(v40);
  NavigationBar::DrawDivider((NavigationBar *)this, a2);
}

```

## disassembly

```asm
0x180001aa0  mov     [rsp-40h+arg_10], r8
0x180001aa5  push    rbp
0x180001aa6  push    rbx
0x180001aa7  push    rsi
0x180001aa8  push    rdi
0x180001aa9  push    r12
0x180001aab  push    r13
0x180001aad  push    r14
0x180001aaf  push    r15
0x180001ab1  mov     rbp, rsp
0x180001ab4  sub     rsp, 68h
0x180001ab8  mov     rdi, rdx
0x180001abb  mov     rsi, rcx
0x180001abe  call    ?EnsureGraphicalObjects@NavigationBar@@AEAAXXZ; NavigationBar::EnsureGraphicalObjects(void)
0x180001ac3  lea     rbx, [rsi+0A8h]
0x180001aca  mov     rax, rbx
0x180001acd  neg     rax
0x180001ad0  sbb     rcx, rcx
0x180001ad3  and     rcx, rsi
0x180001ad6  mov     rcx, [rcx+8]; hWnd
0x180001ada  call    cs:__imp_GetParent
0x180001ae0  mov     r8, rdi
0x180001ae3  mov     rcx, rbx
0x180001ae6  mov     rdx, rax
0x180001ae9  call    ?PaintBackground@?$TransparentBackControlBase@VNavigationBar@@@UIControls@@IEBAXPEAUHWND__@@AEAVGraphics@Gdiplus@@@Z; UIControls::TransparentBackControlBase<NavigationBar>::PaintBackground(HWND__ *,Gdiplus::Graphics &)
0x180001aee  call    ?GetDpiOffset@@YAIXZ; GetDpiOffset(void)
0x180001af3  mov     rcx, [rsi+128h]; this
0x180001afa  mov     ebx, eax
0x180001afc  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001b01  mov     rcx, [rsi+130h]; this
0x180001b08  mov     [rbp+arg_0], eax
0x180001b0b  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001b10  lea     r15, __ImageBase
0x180001b17  mov     [rbp+var_10], rbx
0x180001b1b  mov     ecx, ds:rva dword_18008B108[r15+rbx*4]
0x180001b23  mov     r14d, ebx
0x180001b26  sub     ecx, eax
0x180001b28  mov     [rbp+var_38], ecx
0x180001b2b  mov     rcx, [rsi+140h]; this
0x180001b32  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001b37  mov     ecx, eax
0x180001b39  mov     r8d, 2
0x180001b3f  mov     eax, ds:rva dword_18008B108[r15+rbx*4]
0x180001b47  cdq
0x180001b48  shr     ecx, 1
0x180001b4a  idiv    r8d
0x180001b4d  mov     ebx, eax
0x180001b4f  sub     ebx, ecx
0x180001b51  mov     rcx, [rsi+140h]; this
0x180001b58  mov     dword ptr [rbp+arg_10], ebx
0x180001b5b  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001b60  mov     rcx, [rsi+128h]; this
0x180001b67  mov     [rbp+var_28], eax
0x180001b6a  add     eax, ebx
0x180001b6c  mov     [rbp+arg_18], eax
0x180001b6f  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180001b74  mov     rcx, [rsi+128h]; this
0x180001b7b  mov     r12d, eax
0x180001b7e  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001b83  mov     r15d, ds:rva dword_18008B1C8[r15+r14*4]
0x180001b8b  lea     rcx, [rbp+arg_8]
0x180001b8f  mov     rbx, [rsi+150h]
0x180001b96  mov     r13d, eax
0x180001b99  mov     [rbp+arg_8], 0
0x180001ba1  call    cs:__imp_GdipCreateMatrix
0x180001ba7  mov     rax, [rbp+arg_8]
0x180001bab  xorps   xmm2, xmm2
0x180001bae  cvtsi2ss xmm2, r15
0x180001bb3  xor     r9d, r9d
0x180001bb6  mov     [rbp+var_30], rax
0x180001bba  mov     rcx, rax
0x180001bbd  xorps   xmm1, xmm1
0x180001bc0  call    cs:__imp_GdipTranslateMatrix
0x180001bc6  mov     rdx, [rbp+var_30]
0x180001bca  mov     rcx, [rbx+8]
0x180001bce  call    cs:__imp_GdipSetTextureTransform
0x180001bd4  test    eax, eax
0x180001bd6  jz      short loc_180001BDB
0x180001bd8  mov     [rbx+10h], eax
0x180001bdb  mov     rdx, [rbx+8]
0x180001bdf  mov     r9d, r15d
0x180001be2  mov     rcx, [rdi]
0x180001be5  xor     r8d, r8d
0x180001be8  mov     [rsp+68h+var_40], r12d
0x180001bed  mov     [rsp+68h+var_48], r13d
0x180001bf2  call    cs:__imp_GdipFillRectangleI
0x180001bf8  lea     rbx, [rdi+8]
0x180001bfc  test    eax, eax
0x180001bfe  jz      short loc_180001C02
0x180001c00  mov     [rbx], eax
0x180001c02  mov     rcx, [rbp+var_30]
0x180001c06  call    cs:__imp_GdipDeleteMatrix
0x180001c0c  lea     r13, [rsi+138h]
0x180001c13  mov     rcx, [r13+0]; this
0x180001c17  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180001c1c  mov     dword ptr [rbp+var_30], eax
0x180001c1f  lea     r12, [rsi+160h]
0x180001c26  lea     rax, __ImageBase
0x180001c2d  mov     [rbp+var_20], 0
0x180001c35  mov     eax, ds:rva dword_18008B1C8[rax+r14*4]
0x180001c3d  lea     rcx, [rbp+var_20]
0x180001c41  mov     r14, [r12]
0x180001c45  mov     dword ptr [rbp+arg_8], eax
0x180001c48  call    cs:__imp_GdipCreateMatrix
0x180001c4e  mov     r15, [rbp+var_20]
0x180001c52  xorps   xmm2, xmm2
0x180001c55  mov     ecx, dword ptr [rbp+arg_8]
0x180001c58  xorps   xmm1, xmm1
0x180001c5b  xor     r9d, r9d
0x180001c5e  mov     [rbp+var_18], r15
0x180001c62  cvtsi2ss xmm2, rcx
0x180001c67  mov     ecx, [rbp+arg_0]
0x180001c6a  cvtsi2ss xmm1, rcx
0x180001c6f  mov     rcx, r15
0x180001c72  call    cs:__imp_GdipTranslateMatrix
0x180001c78  mov     rcx, [r14+8]
0x180001c7c  mov     rdx, r15
0x180001c7f  call    cs:__imp_GdipSetTextureTransform
0x180001c85  test    eax, eax
0x180001c87  jz      short loc_180001C8D
0x180001c89  mov     [r14+10h], eax
0x180001c8d  mov     eax, dword ptr [rbp+arg_10]
0x180001c90  mov     edx, dword ptr [rbp+var_30]
0x180001c93  sub     eax, [rbp+arg_0]
0x180001c96  mov     r9d, dword ptr [rbp+arg_8]
0x180001c9a  mov     r8d, [rbp+arg_0]
0x180001c9e  mov     rcx, [rdi]
0x180001ca1  mov     [rsp+68h+var_40], edx
0x180001ca5  mov     rdx, [r14+8]
0x180001ca9  mov     [rsp+68h+var_48], eax
0x180001cad  call    cs:__imp_GdipFillRectangleI
0x180001cb3  test    eax, eax
0x180001cb5  jz      short loc_180001CCD
0x180001cb7  mov     [rbx], eax
0x180001cb9  lea     r14, [rdi+8]
0x180001cbd  lea     r15, [rsi+138h]
0x180001cc4  lea     r12, [rsi+160h]
0x180001ccb  jmp     short loc_180001CD3
0x180001ccd  mov     r15, r13
0x180001cd0  mov     r14, rbx
0x180001cd3  mov     rcx, [rbp+var_18]
0x180001cd7  call    cs:__imp_GdipDeleteMatrix
0x180001cdd  mov     rcx, [rsi+140h]; this
0x180001ce4  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180001ce9  mov     rcx, [rbp+var_10]
0x180001ced  mov     dword ptr [rbp+arg_8], eax
0x180001cf0  lea     rax, __ImageBase
0x180001cf7  mov     [rbp+var_20], 0
0x180001cff  mov     eax, ds:rva dword_18008B1D8[rax+rcx*4]
0x180001d06  lea     rcx, [rbp+var_20]
0x180001d0a  mov     [rbp+arg_0], eax
0x180001d0d  mov     rax, [rsi+168h]
0x180001d14  mov     [rbp+var_30], rax
0x180001d18  call    cs:__imp_GdipCreateMatrix
0x180001d1e  mov     rax, [rbp+var_20]
0x180001d22  xorps   xmm2, xmm2
0x180001d25  mov     ecx, [rbp+arg_0]
0x180001d28  xorps   xmm1, xmm1
0x180001d2b  xor     r9d, r9d
0x180001d2e  mov     [rbp+var_18], rax
0x180001d32  cvtsi2ss xmm2, rcx
0x180001d37  mov     ecx, dword ptr [rbp+arg_10]
0x180001d3a  cvtsi2ss xmm1, rcx
0x180001d3f  mov     rcx, rax
0x180001d42  call    cs:__imp_GdipTranslateMatrix
0x180001d48  mov     rcx, [rbp+var_30]
0x180001d4c  mov     rdx, [rbp+var_18]
0x180001d50  mov     rcx, [rcx+8]
0x180001d54  call    cs:__imp_GdipSetTextureTransform
0x180001d5a  mov     ecx, eax
0x180001d5c  test    eax, eax
0x180001d5e  mov     rax, [rbp+var_30]
0x180001d62  jz      short loc_180001D69
0x180001d64  mov     [rax+10h], ecx
0x180001d67  jmp     short loc_180001D76
0x180001d69  mov     r15, r13
0x180001d6c  lea     r12, [rsi+160h]
0x180001d73  mov     r14, rbx
0x180001d76  mov     ecx, dword ptr [rbp+arg_8]
0x180001d79  mov     r9d, [rbp+arg_0]
0x180001d7d  mov     r8d, dword ptr [rbp+arg_10]
0x180001d81  mov     rdx, [rax+8]
0x180001d85  mov     [rsp+68h+var_40], ecx
0x180001d89  mov     ecx, [rbp+var_28]
0x180001d8c  mov     [rsp+68h+var_48], ecx
0x180001d90  mov     rcx, [rdi]
0x180001d93  call    cs:__imp_GdipFillRectangleI
0x180001d99  test    eax, eax
0x180001d9b  jz      short loc_180001DA0
0x180001d9d  mov     [r14], eax
0x180001da0  mov     rcx, [rbp+var_18]
0x180001da4  call    cs:__imp_GdipDeleteMatrix
0x180001daa  mov     rcx, [r15]; this
0x180001dad  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180001db2  mov     r13, [rbp+var_10]
0x180001db6  lea     rcx, [rbp+arg_8]
0x180001dba  mov     rbx, [r12]
0x180001dbe  mov     [rbp+arg_0], eax
0x180001dc1  lea     rax, __ImageBase
0x180001dc8  mov     [rbp+arg_8], 0
0x180001dd0  mov     eax, ds:rva dword_18008B1C8[rax+r13*4]
0x180001dd8  mov     dword ptr [rbp+arg_10], eax
0x180001ddb  call    cs:__imp_GdipCreateMatrix
0x180001de1  mov     ecx, [rbp+arg_18]
0x180001de4  xorps   xmm2, xmm2
0x180001de7  mov     r15, [rbp+arg_8]
0x180001deb  xorps   xmm1, xmm1
0x180001dee  mov     r12d, dword ptr [rbp+arg_10]
0x180001df2  xor     r9d, r9d
0x180001df5  cvtsi2ss xmm1, rcx
0x180001dfa  mov     rcx, r15
0x180001dfd  cvtsi2ss xmm2, r12
0x180001e02  call    cs:__imp_GdipTranslateMatrix
0x180001e08  mov     rcx, [rbx+8]
0x180001e0c  mov     rdx, r15
0x180001e0f  call    cs:__imp_GdipSetTextureTransform
0x180001e15  test    eax, eax
0x180001e17  jz      short loc_180001E1C
0x180001e19  mov     [rbx+10h], eax
0x180001e1c  mov     eax, [rbp+var_38]
0x180001e1f  mov     r9d, r12d
0x180001e22  mov     edx, [rbp+arg_0]
0x180001e25  sub     eax, [rbp+arg_18]
0x180001e28  mov     r8d, [rbp+arg_18]
0x180001e2c  mov     rcx, [rdi]
0x180001e2f  mov     [rsp+68h+var_40], edx
0x180001e33  mov     rdx, [rbx+8]
0x180001e37  mov     [rsp+68h+var_48], eax
0x180001e3b  call    cs:__imp_GdipFillRectangleI
0x180001e41  test    eax, eax
0x180001e43  jz      short loc_180001E48
0x180001e45  mov     [r14], eax
0x180001e48  mov     rcx, r15
0x180001e4b  call    cs:__imp_GdipDeleteMatrix
0x180001e51  mov     rcx, [rsi+130h]; this
0x180001e58  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180001e5d  mov     rcx, [rsi+130h]; this
0x180001e64  mov     dword ptr [rbp+arg_10], eax
0x180001e67  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180001e6c  mov     rbx, [rsi+158h]
0x180001e73  lea     rcx, [rbp+arg_8]
0x180001e77  mov     [rbp+arg_0], eax
0x180001e7a  lea     rax, __ImageBase
0x180001e81  mov     r15d, ds:rva dword_18008B1C8[rax+r13*4]
0x180001e89  mov     [rbp+arg_8], 0
0x180001e91  call    cs:__imp_GdipCreateMatrix
0x180001e97  mov     r14, [rbp+arg_8]
0x180001e9b  xorps   xmm2, xmm2
0x180001e9e  mov     r12d, [rbp+var_38]
0x180001ea2  xorps   xmm1, xmm1
0x180001ea5  cvtsi2ss xmm2, r15
0x180001eaa  xor     r9d, r9d
0x180001ead  mov     rcx, r14
0x180001eb0  cvtsi2ss xmm1, r12
0x180001eb5  call    cs:__imp_GdipTranslateMatrix
0x180001ebb  mov     rcx, [rbx+8]
0x180001ebf  mov     rdx, r14
0x180001ec2  call    cs:__imp_GdipSetTextureTransform
0x180001ec8  test    eax, eax
0x180001eca  jz      short loc_180001ECF
0x180001ecc  mov     [rbx+10h], eax
0x180001ecf  mov     eax, dword ptr [rbp+arg_10]
0x180001ed2  mov     r9d, r15d
0x180001ed5  mov     rdx, [rbx+8]
0x180001ed9  mov     r8d, r12d
0x180001edc  mov     rcx, [rdi]
0x180001edf  mov     [rsp+68h+var_40], eax
0x180001ee3  mov     eax, [rbp+arg_0]
0x180001ee6  mov     [rsp+68h+var_48], eax
0x180001eea  call    cs:__imp_GdipFillRectangleI
0x180001ef0  test    eax, eax
0x180001ef2  jz      short loc_180001EF7
0x180001ef4  mov     [rdi+8], eax
0x180001ef7  mov     rcx, r14
0x180001efa  call    cs:__imp_GdipDeleteMatrix
0x180001f00  mov     rdx, rdi; struct Gdiplus::Graphics *
0x180001f03  mov     rcx, rsi; this
0x180001f06  add     rsp, 68h
0x180001f0a  pop     r15
0x180001f0c  pop     r14
0x180001f0e  pop     r13
0x180001f10  pop     r12
0x180001f12  pop     rdi
0x180001f13  pop     rsi
0x180001f14  pop     rbx
0x180001f15  pop     rbp
0x180001f16  jmp     ?DrawDivider@NavigationBar@@AEAAXAEAVGraphics@Gdiplus@@@Z; NavigationBar::DrawDivider(Gdiplus::Graphics &)
```
