# Jot::CSectionGroupTabShape::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)

- ea: `0x140145300`
- end: `0x140145af6`
- name: `?Paint@CSectionGroupTabShape@Jot@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z`
- size: `2038`
- prototype: `void __fastcall(Jot::CSectionGroupTabShape *__hidden this, const struct PaintContext *, const struct tagRECT *, const struct tagRECT *, unsigned int, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140038864`
- `0x14003b5f0`
- `0x14003b714`
- `0x14003c9a0`
- `0x140065428`
- `0x1400a08c8`
- `0x1400a2378`
- `0x1400ab9b8`
- `0x140145300`

## import_xrefs

- `gdiplus!GdipDeletePath` at `0x140145a69`
- `gdiplus!GdipDeletePath` at `0x140145a74`
- `gdiplus!GdipDeletePath` at `0x140145a7f`
- `gdiplus!GdipDeletePath` at `0x140145a8a`
- `gdiplus!GdipDeletePath` at `0x140145a95`
- `gdiplus!GdipDeletePath` at `0x140145a9f`
- `gdiplus!GdipDeletePath` at `0x140145a69`
- `gdiplus!GdipDeletePath` at `0x140145a74`
- `gdiplus!GdipDeletePath` at `0x140145a7f`
- `gdiplus!GdipDeletePath` at `0x140145a8a`
- `gdiplus!GdipDeletePath` at `0x140145a95`
- `gdiplus!GdipDeletePath` at `0x140145a9f`
- `gdiplus!GdipCreatePath` at `0x140145381`
- `gdiplus!GdipCreatePath` at `0x140145396`
- `gdiplus!GdipCreatePath` at `0x1401453ac`
- `gdiplus!GdipCreatePath` at `0x1401453c2`
- `gdiplus!GdipCreatePath` at `0x1401453d8`
- `gdiplus!GdipCreatePath` at `0x1401453ec`
- `gdiplus!GdipCreatePath` at `0x140145381`
- `gdiplus!GdipCreatePath` at `0x140145396`
- `gdiplus!GdipCreatePath` at `0x1401453ac`
- `gdiplus!GdipCreatePath` at `0x1401453c2`
- `gdiplus!GdipCreatePath` at `0x1401453d8`
- `gdiplus!GdipCreatePath` at `0x1401453ec`
- `gdiplus!GdipDeleteGraphics` at `0x140145ab5`
- `gdiplus!GdipDeleteGraphics` at `0x140145ab5`
- `gdiplus!GdipDeleteBrush` at `0x140145a37`
- `gdiplus!GdipDeleteBrush` at `0x140145a41`
- `gdiplus!GdipDeleteBrush` at `0x140145a4b`
- `gdiplus!GdipDeleteBrush` at `0x140145a55`
- `gdiplus!GdipDeleteBrush` at `0x140145a5f`
- `gdiplus!GdipDeleteBrush` at `0x140145a37`
- `gdiplus!GdipDeleteBrush` at `0x140145a41`
- `gdiplus!GdipDeleteBrush` at `0x140145a4b`
- `gdiplus!GdipDeleteBrush` at `0x140145a55`
- `gdiplus!GdipDeleteBrush` at `0x140145a5f`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140145586`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140145690`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x14014579b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401458a3`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401459ae`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140145586`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140145690`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x14014579b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401458a3`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1401459ae`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x140145a2d`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x140145a2d`

## pseudocode

```c
void __fastcall Jot::CSectionGroupTabShape::Paint(
        Jot::CSectionGroupTabShape *this,
        const struct PaintContext *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        unsigned int a5,
        struct tagRECT *a6,
        struct tagRECT *a7)
{
  int v10; // eax
  int v11; // eax
  char v12; // r8
  LONG right; // eax
  char v14; // r8
  LONG left; // edx
  unsigned int v16; // esi
  LONG bottom; // ecx
  unsigned int v18; // r14d
  int v19; // r12d
  int v20; // ebx
  __int64 v21; // rax
  int v22; // r12d
  __int64 v23; // rax
  int v24; // r12d
  __int64 v25; // rax
  int v26; // r12d
  __int64 v27; // rax
  int v28; // r12d
  __int64 v29; // rax
  __int64 v30; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B8h]
  __int64 v32; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A8h]
  __int64 v34; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-98h]
  __int64 v36; // [rsp+78h] [rbp-90h] BYREF
  int v37; // [rsp+80h] [rbp-88h]
  __int64 v38; // [rsp+88h] [rbp-80h] BYREF
  int v39; // [rsp+90h] [rbp-78h]
  int v40; // [rsp+98h] [rbp-70h]
  int v41; // [rsp+9Ch] [rbp-6Ch]
  _QWORD v42[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-58h] BYREF
  int v44; // [rsp+B8h] [rbp-50h]
  __int64 v45; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v46; // [rsp+C8h] [rbp-40h]
  char v47[8]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-30h]
  char v49[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v50; // [rsp+F0h] [rbp-18h]
  char v51[8]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v52; // [rsp+108h] [rbp+0h]
  char v53[8]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v54; // [rsp+120h] [rbp+18h]
  char v55[8]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v56; // [rsp+138h] [rbp+30h]
  int v57; // [rsp+208h] [rbp+100h] BYREF
  int v58; // [rsp+210h] [rbp+108h]
  int v59; // [rsp+218h] [rbp+110h]
  const struct tagRECT *v60; // [rsp+220h] [rbp+118h]

  v60 = a4;
  *((_BYTE *)a2 + 48) = 1;
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)v42, *((HDC *)a2 + 2));
  Jot::CGdipSmoothingModeChanger::CGdipSmoothingModeChanger(&v45, v42);
  v38 = 0;
  v36 = 0;
  v39 = GdipCreatePath(0, &v38);
  v34 = 0;
  v37 = GdipCreatePath(0, &v36);
  v32 = 0;
  LODWORD(v35) = GdipCreatePath(0, &v34);
  v30 = 0;
  LODWORD(v33) = GdipCreatePath(0, &v32);
  v10 = GdipCreatePath(0, &v30);
  v43 = 0;
  LODWORD(v31) = v10;
  v11 = GdipCreatePath(0, &v43);
  v12 = *((_BYTE *)this + 195);
  v44 = v11;
  right = a3->right;
  v14 = v12 & 1;
  if ( v14 )
  {
    left = a3->left;
    v16 = right - 1;
  }
  else
  {
    v16 = a3->left;
    left = a3->left;
  }
  bottom = a3->bottom;
  v18 = left - 1;
  if ( !v14 )
    v18 = a3->right;
  v58 = bottom - 3;
  v57 = bottom + 2;
  v40 = bottom - 9;
  v59 = bottom - 4;
  v41 = bottom - 10;
  v19 = (right - left) / 2;
  Gdiplus::GraphicsPath::AddLine(&v38, v18, (unsigned int)(bottom + 1), v18, a3->top);
  Gdiplus::GraphicsPath::AddArc(&v38);
  v20 = 2 * v19;
  Gdiplus::GraphicsPath::AddLine(&v38, v16, (unsigned int)(v20 + a3->top), v16, v57 - v20 - 1);
  Gdiplus::GraphicsPath::AddArc(&v38);
  Gdiplus::GraphicsPath::CloseFigure(&v38);
  v21 = MsoCrCbvGet(2980);
  v57 = v21 & 0xFF00 | BYTE2(v21) | (((unsigned __int8)v21 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v55, (const struct Gdiplus::Color *)&v57);
  Gdiplus::Graphics::FillPath(v42, v55, &v38);
  v22 = v58;
  Gdiplus::GraphicsPath::AddLine(&v36, v18, (unsigned int)(v58 - 1), v18, a3->top);
  Gdiplus::GraphicsPath::AddArc(&v36);
  Gdiplus::GraphicsPath::AddLine(&v36, v16, (unsigned int)(v20 + a3->top), v16, v22 - v20 - 1);
  Gdiplus::GraphicsPath::AddArc(&v36);
  Gdiplus::GraphicsPath::CloseFigure(&v36);
  v23 = MsoCrCbvGet(2967);
  v57 = v23 & 0xFF00 | BYTE2(v23) | (((unsigned __int8)v23 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v53, (const struct Gdiplus::Color *)&v57);
  Gdiplus::Graphics::FillPath(v42, v53, &v36);
  v24 = v59;
  Gdiplus::GraphicsPath::AddLine(&v34, v18, (unsigned int)(v59 - 1), v18, a3->top);
  Gdiplus::GraphicsPath::AddArc(&v34);
  Gdiplus::GraphicsPath::AddLine(&v34, v16, (unsigned int)(v20 + a3->top), v16, v24 - v20 - 1);
  Gdiplus::GraphicsPath::AddArc(&v34);
  Gdiplus::GraphicsPath::CloseFigure(&v34);
  v25 = MsoCrCbvGet(2986);
  v57 = v25 & 0xFF00 | BYTE2(v25) | (((unsigned __int8)v25 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v51, (const struct Gdiplus::Color *)&v57);
  Gdiplus::Graphics::FillPath(v42, v51, &v34);
  v26 = v40;
  Gdiplus::GraphicsPath::AddLine(&v32, v18, (unsigned int)(v40 - 1), v18, a3->top);
  Gdiplus::GraphicsPath::AddArc(&v32);
  Gdiplus::GraphicsPath::AddLine(&v32, v16, (unsigned int)(v20 + a3->top), v16, v26 - v20 - 1);
  Gdiplus::GraphicsPath::AddArc(&v32);
  Gdiplus::GraphicsPath::CloseFigure(&v32);
  v27 = MsoCrCbvGet(2967);
  v57 = v27 & 0xFF00 | BYTE2(v27) | (((unsigned __int8)v27 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v49, (const struct Gdiplus::Color *)&v57);
  Gdiplus::Graphics::FillPath(v42, v49, &v32);
  v28 = v41;
  Gdiplus::GraphicsPath::AddLine(&v30, v18, (unsigned int)(v41 - 1), v18, a3->top);
  Gdiplus::GraphicsPath::AddArc(&v30);
  Gdiplus::GraphicsPath::AddLine(&v30, v16, (unsigned int)(v20 + a3->top), v16, v28 - v20 - 1);
  Gdiplus::GraphicsPath::AddArc(&v30);
  Gdiplus::GraphicsPath::CloseFigure(&v30);
  v29 = MsoCrCbvGet(2991);
  v57 = v29 & 0xFF00 | BYTE2(v29) | (((unsigned __int8)v29 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v47, (const struct Gdiplus::Color *)&v57);
  Gdiplus::Graphics::FillPath(v42, v47, &v30);
  NetUI::Element::Paint(this, a2, a3, v60, a5, a6, a7);
  GdipDeleteBrush(v48);
  GdipDeleteBrush(v50);
  GdipDeleteBrush(v52);
  GdipDeleteBrush(v54);
  GdipDeleteBrush(v56);
  GdipDeletePath(v43);
  GdipDeletePath(v30);
  GdipDeletePath(v32);
  GdipDeletePath(v34);
  GdipDeletePath(v36);
  GdipDeletePath(v38);
  Gdiplus::Graphics::SetSmoothingMode(v45, v46);
  GdipDeleteGraphics(v42[0]);
}

```

## disassembly

```asm
0x140145300  mov     rax, rsp
0x140145303  mov     [rax+20h], r9
0x140145307  push    rbp
0x140145308  push    rbx
0x140145309  push    rsi
0x14014530a  push    rdi
0x14014530b  push    r12
0x14014530d  push    r13
0x14014530f  push    r14
0x140145311  push    r15
0x140145313  lea     rbp, [rax-0F8h]
0x14014531a  sub     rsp, 1B8h
0x140145321  movaps  xmmword ptr [rax-58h], xmm6
0x140145325  mov     r15, rdx
0x140145328  movaps  xmmword ptr [rax-68h], xmm7
0x14014532c  mov     r13, rcx
0x14014532f  movaps  xmmword ptr [rax-78h], xmm8
0x140145334  lea     rcx, [rbp+0F0h+var_158]; this
0x140145338  movaps  xmmword ptr [rax-88h], xmm9
0x140145340  mov     rdi, r8
0x140145343  movaps  xmmword ptr [rax-98h], xmm10
0x14014534b  mov     byte ptr [rdx+30h], 1
0x14014534f  mov     rdx, [rdx+10h]; HDC
0x140145353  movaps  xmmword ptr [rax-0A8h], xmm11
0x14014535b  movaps  xmmword ptr [rax-0B8h], xmm12
0x140145363  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x140145368  lea     rdx, [rbp+0F0h+var_158]
0x14014536c  lea     rcx, [rbp+0F0h+var_138]
0x140145370  call    ??0CGdipSmoothingModeChanger@Jot@@QEAA@PEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; Jot::CGdipSmoothingModeChanger::CGdipSmoothingModeChanger(Gdiplus::Graphics *,Gdiplus::SmoothingMode)
0x140145375  xor     ebx, ebx
0x140145377  lea     rdx, [rbp+0F0h+var_170]
0x14014537b  xor     ecx, ecx
0x14014537d  mov     [rbp+0F0h+var_170], rbx
0x140145381  call    cs:__imp_GdipCreatePath
0x140145387  lea     rdx, [rsp+1F0h+var_180]
0x14014538c  mov     [rsp+1F0h+var_180], rbx
0x140145391  xor     ecx, ecx
0x140145393  mov     [rbp+0F0h+var_168], eax
0x140145396  call    cs:__imp_GdipCreatePath
0x14014539c  lea     rdx, [rsp+1F0h+var_190]
0x1401453a1  mov     [rsp+1F0h+var_190], rbx
0x1401453a6  xor     ecx, ecx
0x1401453a8  mov     [rsp+1F0h+var_178], eax
0x1401453ac  call    cs:__imp_GdipCreatePath
0x1401453b2  lea     rdx, [rsp+1F0h+var_1A0]
0x1401453b7  mov     [rsp+1F0h+var_1A0], rbx
0x1401453bc  xor     ecx, ecx
0x1401453be  mov     dword ptr [rsp+1F0h+var_188], eax
0x1401453c2  call    cs:__imp_GdipCreatePath
0x1401453c8  lea     rdx, [rsp+1F0h+var_1B0]
0x1401453cd  mov     [rsp+1F0h+var_1B0], rbx
0x1401453d2  xor     ecx, ecx
0x1401453d4  mov     dword ptr [rsp+1F0h+var_198], eax
0x1401453d8  call    cs:__imp_GdipCreatePath
0x1401453de  lea     rdx, [rbp+0F0h+var_148]
0x1401453e2  mov     [rbp+0F0h+var_148], rbx
0x1401453e6  xor     ecx, ecx
0x1401453e8  mov     dword ptr [rsp+1F0h+var_1A8], eax
0x1401453ec  call    cs:__imp_GdipCreatePath
0x1401453f2  mov     r8b, [r13+0C3h]
0x1401453f9  mov     [rbp+0F0h+var_140], eax
0x1401453fc  mov     eax, [rdi+8]
0x1401453ff  and     r8b, 1
0x140145403  jz      short loc_14014540C
0x140145405  mov     edx, [rdi]
0x140145407  lea     esi, [rax-1]
0x14014540a  jmp     short loc_140145410
0x14014540c  mov     esi, [rdi]
0x14014540e  mov     edx, esi
0x140145410  mov     ecx, [rdi+0Ch]
0x140145413  lea     r14d, [rdx-1]
0x140145417  test    r8b, r8b
0x14014541a  mov     ebx, esi
0x14014541c  cmovz   r14d, eax
0x140145420  sub     eax, edx
0x140145422  lea     r10d, [rcx-3]
0x140145426  cdq
0x140145427  lea     r9d, [rcx+2]
0x14014542b  mov     [rbp+0F0h+arg_8], r10d
0x140145432  lea     r10d, [rcx-9]
0x140145436  mov     [rbp+0F0h+arg_0], r9d
0x14014543d  lea     r11d, [rcx-4]
0x140145441  mov     [rbp+0F0h+var_160], r10d
0x140145445  add     ecx, 0FFFFFFF6h
0x140145448  mov     [rbp+0F0h+arg_10], r11d
0x14014544f  mov     [rbp+0F0h+var_15C], ecx
0x140145452  mov     ecx, 2
0x140145457  idiv    ecx
0x140145459  mov     r12d, eax
0x14014545c  test    r8b, r8b
0x14014545f  jz      short loc_140145473
0x140145461  sub     ebx, eax
0x140145463  test    r8b, r8b
0x140145466  jz      short loc_140145473
0x140145468  movss   xmm12, cs:__real@439d8000
0x140145471  jmp     short loc_14014547C
0x140145473  movss   xmm12, cs:__real@43610000
0x14014547c  test    r8b, r8b
0x14014547f  jz      short loc_140145487
0x140145481  xorps   xmm11, xmm11
0x140145485  jmp     short loc_140145490
0x140145487  movss   xmm11, cs:__real@43340000
0x140145490  test    r8b, r8b
0x140145493  jz      short loc_1401454A0
0x140145495  movss   xmm10, cs:__real@42340000
0x14014549e  jmp     short loc_1401454A9
0x1401454a0  movss   xmm10, cs:__real@c2340000
0x1401454a9  mov     eax, [rdi+4]
0x1401454ac  lea     r8d, [r9-1]
0x1401454b0  mov     r9d, r14d
0x1401454b3  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1401454b7  mov     edx, r14d
0x1401454ba  lea     rcx, [rbp+0F0h+var_170]
0x1401454be  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x1401454c3  movd    xmm2, dword ptr [rdi+4]
0x1401454c8  lea     rcx, [rbp+0F0h+var_170]
0x1401454cc  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x1401454d3  cvtdq2ps xmm2, xmm2
0x1401454d6  movss   dword ptr [rsp+1F0h+var_1C8], xmm12
0x1401454dd  movd    xmm8, r12d
0x1401454e2  cvtdq2ps xmm8, xmm8
0x1401454e6  movd    xmm9, ebx
0x1401454eb  cvtdq2ps xmm9, xmm9
0x1401454ef  addss   xmm2, xmm8
0x1401454f4  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x1401454fb  movaps  xmm3, xmm8
0x1401454ff  movaps  xmm1, xmm9
0x140145503  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x140145508  mov     r8d, [rdi+4]
0x14014550c  lea     ebx, [r12+r12]
0x140145510  mov     r12d, [rbp+0F0h+arg_0]
0x140145517  add     r8d, ebx
0x14014551a  mov     ecx, r12d
0x14014551d  mov     r9d, esi
0x140145520  sub     ecx, ebx
0x140145522  mov     edx, esi
0x140145524  dec     ecx
0x140145526  mov     dword ptr [rsp+1F0h+var_1D0], ecx
0x14014552a  lea     rcx, [rbp+0F0h+var_170]
0x14014552e  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x140145533  movss   xmm6, cs:__real@3f800000
0x14014553b  lea     rcx, [rbp+0F0h+var_170]
0x14014553f  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x140145546  movaps  xmm3, xmm8
0x14014554a  movd    xmm2, r12d
0x14014554f  movaps  xmm1, xmm9
0x140145553  cvtdq2ps xmm2, xmm2
0x140145556  movss   dword ptr [rsp+1F0h+var_1C8], xmm11
0x14014555d  movd    xmm7, ebx
0x140145561  cvtdq2ps xmm7, xmm7
0x140145564  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x14014556b  subss   xmm2, xmm7
0x14014556f  subss   xmm2, xmm6
0x140145573  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x140145578  lea     rcx, [rbp+0F0h+var_170]
0x14014557c  call    ?CloseFigure@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::CloseFigure(void)
0x140145581  mov     ecx, 0BA4h
0x140145586  call    cs:__imp_MsoCrCbvGet
0x14014558c  movzx   edx, al
0x14014558f  mov     r8d, 0FFFFFF00h
0x140145595  movzx   ecx, ax
0x140145598  or      edx, r8d
0x14014559b  shl     edx, 10h
0x14014559e  and     ecx, r8d
0x1401455a1  shr     eax, 10h
0x1401455a4  movzx   eax, al
0x1401455a7  or      edx, eax
0x1401455a9  or      edx, ecx
0x1401455ab  lea     rcx, [rbp+0F0h+var_C8]; this
0x1401455af  mov     [rbp+0F0h+arg_0], edx
0x1401455b5  lea     rdx, [rbp+0F0h+arg_0]; struct Gdiplus::Color *
0x1401455bc  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1401455c1  lea     r8, [rbp+0F0h+var_170]
0x1401455c5  lea     rdx, [rbp+0F0h+var_C8]
0x1401455c9  lea     rcx, [rbp+0F0h+var_158]
0x1401455cd  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x1401455d2  mov     eax, [rdi+4]
0x1401455d5  lea     rcx, [rsp+1F0h+var_180]
0x1401455da  mov     r12d, [rbp+0F0h+arg_8]
0x1401455e1  mov     r9d, r14d
0x1401455e4  mov     edx, r14d
0x1401455e7  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1401455eb  lea     r8d, [r12-1]
0x1401455f0  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x1401455f5  movd    xmm2, dword ptr [rdi+4]
0x1401455fa  cvtdq2ps xmm2, xmm2
0x1401455fd  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x140145604  addss   xmm2, xmm8
0x140145609  movss   dword ptr [rsp+1F0h+var_1C8], xmm12
0x140145610  lea     rcx, [rsp+1F0h+var_180]
0x140145615  movaps  xmm3, xmm8
0x140145619  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x140145620  movaps  xmm1, xmm9
0x140145624  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x140145629  mov     r8d, [rdi+4]
0x14014562d  mov     ecx, r12d
0x140145630  sub     ecx, ebx
0x140145632  add     r8d, ebx
0x140145635  dec     ecx
0x140145637  mov     r9d, esi
0x14014563a  mov     dword ptr [rsp+1F0h+var_1D0], ecx
0x14014563e  mov     edx, esi
0x140145640  lea     rcx, [rsp+1F0h+var_180]
0x140145645  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x14014564a  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x140145651  lea     rcx, [rsp+1F0h+var_180]
0x140145656  movd    xmm2, r12d
0x14014565b  movaps  xmm3, xmm8
0x14014565f  cvtdq2ps xmm2, xmm2
0x140145662  movss   dword ptr [rsp+1F0h+var_1C8], xmm11
0x140145669  movaps  xmm1, xmm9
0x14014566d  subss   xmm2, xmm7
0x140145671  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x140145678  subss   xmm2, xmm6
0x14014567c  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x140145681  lea     rcx, [rsp+1F0h+var_180]
0x140145686  call    ?CloseFigure@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::CloseFigure(void)
0x14014568b  mov     ecx, 0B97h
0x140145690  call    cs:__imp_MsoCrCbvGet
0x140145696  movzx   edx, al
0x140145699  mov     r8d, 0FFFFFF00h
0x14014569f  movzx   ecx, ax
0x1401456a2  or      edx, r8d
0x1401456a5  shl     edx, 10h
0x1401456a8  and     ecx, r8d
0x1401456ab  shr     eax, 10h
0x1401456ae  movzx   eax, al
0x1401456b1  or      edx, eax
0x1401456b3  or      edx, ecx
0x1401456b5  lea     rcx, [rbp+0F0h+var_E0]; this
0x1401456b9  mov     [rbp+0F0h+arg_0], edx
0x1401456bf  lea     rdx, [rbp+0F0h+arg_0]; struct Gdiplus::Color *
0x1401456c6  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1401456cb  lea     r8, [rsp+1F0h+var_180]
0x1401456d0  lea     rdx, [rbp+0F0h+var_E0]
0x1401456d4  lea     rcx, [rbp+0F0h+var_158]
0x1401456d8  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x1401456dd  mov     eax, [rdi+4]
0x1401456e0  lea     rcx, [rsp+1F0h+var_190]
0x1401456e5  mov     r12d, [rbp+0F0h+arg_10]
0x1401456ec  mov     r9d, r14d
0x1401456ef  mov     edx, r14d
0x1401456f2  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x1401456f6  lea     r8d, [r12-1]
0x1401456fb  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x140145700  movd    xmm2, dword ptr [rdi+4]
0x140145705  lea     rcx, [rsp+1F0h+var_190]
0x14014570a  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x140145711  movaps  xmm3, xmm8
0x140145715  cvtdq2ps xmm2, xmm2
0x140145718  movss   dword ptr [rsp+1F0h+var_1C8], xmm12
0x14014571f  movaps  xmm1, xmm9
0x140145723  addss   xmm2, xmm8
0x140145728  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x14014572f  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x140145734  mov     r8d, [rdi+4]
0x140145738  mov     ecx, r12d
0x14014573b  sub     ecx, ebx
0x14014573d  add     r8d, ebx
0x140145740  dec     ecx
0x140145742  mov     r9d, esi
0x140145745  mov     dword ptr [rsp+1F0h+var_1D0], ecx
0x140145749  mov     edx, esi
0x14014574b  lea     rcx, [rsp+1F0h+var_190]
0x140145750  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x140145755  movd    xmm2, r12d
0x14014575a  cvtdq2ps xmm2, xmm2
0x14014575d  subss   xmm2, xmm7
0x140145761  subss   xmm2, xmm6
0x140145765  movss   dword ptr [rsp+1F0h+var_1C0], xmm10
0x14014576c  lea     rcx, [rsp+1F0h+var_190]
0x140145771  movss   dword ptr [rsp+1F0h+var_1C8], xmm11
0x140145778  movaps  xmm3, xmm8
0x14014577c  movaps  xmm1, xmm9
0x140145780  movss   dword ptr [rsp+1F0h+var_1D0], xmm8
0x140145787  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@MMMMMM@Z; Gdiplus::GraphicsPath::AddArc(float,float,float,float,float,float)
0x14014578c  lea     rcx, [rsp+1F0h+var_190]
0x140145791  call    ?CloseFigure@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::CloseFigure(void)
0x140145796  mov     ecx, 0BAAh
0x14014579b  call    cs:__imp_MsoCrCbvGet
0x1401457a1  movzx   edx, al
0x1401457a4  mov     r8d, 0FFFFFF00h
0x1401457aa  movzx   ecx, ax
0x1401457ad  or      edx, r8d
0x1401457b0  shl     edx, 10h
0x1401457b3  and     ecx, r8d
0x1401457b6  shr     eax, 10h
0x1401457b9  movzx   eax, al
0x1401457bc  or      edx, eax
0x1401457be  or      edx, ecx
0x1401457c0  lea     rcx, [rbp+0F0h+var_F8]; this
0x1401457c4  mov     [rbp+0F0h+arg_0], edx
0x1401457ca  lea     rdx, [rbp+0F0h+arg_0]; struct Gdiplus::Color *
0x1401457d1  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1401457d6  lea     r8, [rsp+1F0h+var_190]
0x1401457db  lea     rdx, [rbp+0F0h+var_F8]
0x1401457df  lea     rcx, [rbp+0F0h+var_158]
0x1401457e3  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x1401457e8  mov     eax, [rdi+4]
0x1401457eb  lea     rcx, [rsp+1F0h+var_1A0]
  ... truncated ...
```
