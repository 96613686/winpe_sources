# Jot::CRiffleTab::DrawTab(Jot::CHDCOrGdipGraphcs &,tagRECT const &,Jot::CRiffleTabContainer *,bool,bool)

- ea: `0x14003add4`
- end: `0x14003b12a`
- name: `?DrawTab@CRiffleTab@Jot@@AEAAXAEAVCHDCOrGdipGraphcs@2@AEBUtagRECT@@PEAVCRiffleTabContainer@2@_N3@Z`
- size: `854`
- prototype: `void __usercall(Jot::CRiffleTab *__hidden this@<rcx>, struct Jot::CHDCOrGdipGraphcs *@<rdx>, const struct tagRECT *@<r8>, struct Jot::CRiffleTabContainer *@<r9>, bool, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x140039720`

## callees

- `0x140038864`
- `0x14003add4`
- `0x14003b12c`
- `0x14003b188`
- `0x14003b1a0`
- `0x14003b374`
- `0x14003b614`
- `0x14003b678`
- `0x14003b6df`
- `0x140049270`
- `0x14004ab48`
- `0x140051f14`
- `0x140057580`
- `0x1400adb18`
- `0x1400adddc`
- `0x1400af4a4`
- `0x140149f0c`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14003aef9`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14003aef9`
- `gdiplus!GdipDrawPath` at `0x14003afa8`
- `gdiplus!GdipDrawPath` at `0x14003afa8`
- `gdiplus!GdipDeletePath` at `0x14003afc9`
- `gdiplus!GdipDeletePath` at `0x14003b114`
- `gdiplus!GdipDeletePath` at `0x14003b11e`
- `gdiplus!GdipDeletePath` at `0x14003afc9`
- `gdiplus!GdipDeletePath` at `0x14003b114`
- `gdiplus!GdipDeletePath` at `0x14003b11e`
- `gdiplus!GdipCreatePath` at `0x14003af11`
- `gdiplus!GdipCreatePath` at `0x14003b04b`
- `gdiplus!GdipCreatePath` at `0x14003b05e`
- `gdiplus!GdipCreatePath` at `0x14003af11`
- `gdiplus!GdipCreatePath` at `0x14003b04b`
- `gdiplus!GdipCreatePath` at `0x14003b05e`
- `gdiplus!GdipDeletePen` at `0x14003afbf`
- `gdiplus!GdipDeletePen` at `0x14003b10a`
- `gdiplus!GdipDeletePen` at `0x14003afbf`
- `gdiplus!GdipDeletePen` at `0x14003b10a`
- `gdiplus!GdipCreatePen1` at `0x14003af94`
- `gdiplus!GdipCreatePen1` at `0x14003af94`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x14003af74`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x14003af74`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Jot::CRiffleTab::DrawTab(
        Jot::CRiffleTab *this,
        struct Jot::CHDCOrGdipGraphcs *a2,
        const struct tagRECT *a3,
        struct Jot::CRiffleTabContainer *a4,
        bool a5,
        unsigned int a6)
{
  bool IsCurrent; // r15
  char v10; // al
  char v11; // si
  bool v12; // r14
  bool v13; // bl
  int PageLevelIndex; // eax
  struct Gdiplus::Graphics *v15; // r14
  char v16; // r12
  const struct NetUI::Element *v17; // rdx
  float ScaleFactor; // xmm0_4
  Jot *v19; // rcx
  const struct tagRECT *v20; // r8
  unsigned int v21; // edx
  unsigned int ActivePageTabBorder; // eax
  unsigned int v23; // ebx
  __int64 v24; // rdx
  int v25; // eax
  LONG v26; // eax
  const struct tagRECT *v27; // r8
  const struct tagRECT *v28; // r8
  unsigned int v29; // edx
  unsigned int AdjustedSectionColor; // eax
  struct Jot::ANavigationUIHost *v31; // [rsp+30h] [rbp-51h]
  int v32; // [rsp+30h] [rbp-51h]
  int v33; // [rsp+30h] [rbp-51h]
  struct tagRECT v34; // [rsp+38h] [rbp-49h] BYREF
  struct tagRECT v35; // [rsp+48h] [rbp-39h] BYREF
  __int64 v36; // [rsp+58h] [rbp-29h] BYREF
  int v37; // [rsp+60h] [rbp-21h]
  __int64 v38; // [rsp+68h] [rbp-19h] BYREF
  int v39; // [rsp+70h] [rbp-11h]
  __int64 v40; // [rsp+78h] [rbp-9h] BYREF
  int v41; // [rsp+80h] [rbp-1h]
  struct tagRECT v42; // [rsp+88h] [rbp+7h] BYREF

  v42 = *a3;
  IsCurrent = Jot::CRiffleTab::GetIsCurrent(this);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a4 + 36) + 8LL))(*((_QWORD *)a4 + 36));
  v11 = v10;
  v12 = !IsCurrent || v10;
  v13 = *((_BYTE *)this + 195) & 1;
  PageLevelIndex = Jot::CRiffleTab::GetPageLevelIndex(this);
  Jot::CRiffleTabStyleManager::GetTabRect(
    (struct Jot::CRiffleTabContainer *)((char *)a4 + 432),
    PageLevelIndex,
    &v42,
    v13,
    v12);
  v15 = Jot::CHDCOrGdipGraphcs::UseGraphics(a2);
  Gdiplus::Graphics::SetSmoothingMode(v15, 3);
  v34 = v42;
  v35 = v42;
  v16 = a6;
  if ( (_BYTE)a6 )
  {
    v26 = _mm_srli_si128(*(__m128i *)&v42, 8).m128i_i32[1] - 4;
    v35.bottom = v26;
    if ( IsCurrent )
    {
      if ( v11 )
        goto LABEL_5;
      v34.bottom = v26;
    }
  }
  if ( v11 )
  {
LABEL_5:
    ++v34.right;
    goto LABEL_6;
  }
  if ( Jot::CRiffleTab::FPrevPageTabCurrent(this) )
  {
    ++v34.top;
    ++v35.top;
  }
LABEL_6:
  Jot::CRiffleTab::FillTab(this, v15, &v34, a5);
  ScaleFactor = Jot::DPIUtils::GetScaleFactor(this, v17);
  a6 = (int)roundf_0(ScaleFactor);
  if ( IsCurrent && !v11 && !Jot::IsLicensedForFluentUI(v19) )
  {
    v38 = 0;
    v39 = GdipCreatePath(0, &v38);
    LOBYTE(v20) = *((_BYTE *)this + 195) & 1;
    Jot::GeneratePageTabOutlinePath(
      (Jot *)&v38,
      (struct Gdiplus::GraphicsPath *)&v35,
      v20,
      IsCurrent,
      *((_QWORD *)a4 + 36),
      v31);
    ActivePageTabBorder = Jot::SectionColor::GetActivePageTabBorder(
                            (Jot::SectionColor *)*((unsigned int *)a4 + 106),
                            v21);
    v23 = ActivePageTabBorder & 0xFF00 | BYTE2(ActivePageTabBorder) | ((ActivePageTabBorder | 0xFFFFFF00) << 16);
    MsoFCbvHighContrast();
    v40 = 0;
    v41 = GdipCreatePen1(v23, v24, 0, &v40);
    v25 = GdipDrawPath(*(_QWORD *)v15, v40, v38);
    if ( v25 )
      *((_DWORD *)v15 + 2) = v25;
    if ( v16 )
    {
      v36 = 0;
      v37 = GdipCreatePath(0, &v36);
      *(_QWORD *)&v34.left = 0;
      v34.right = GdipCreatePath(0, &v34);
      LOBYTE(v27) = *((_BYTE *)this + 195) & 1;
      Jot::GeneratePageTabPaperStackPath((Jot *)&v36, (struct Gdiplus::GraphicsPath *)&v35, v27, 0, 0, v32);
      LOBYTE(v28) = *((_BYTE *)this + 195) & 1;
      Jot::GeneratePageTabPaperStackPath((Jot *)&v34, (struct Gdiplus::GraphicsPath *)&v35, v28, 0, 1, v33);
      AdjustedSectionColor = Jot::SectionColor::GetAdjustedSectionColor(
                               (Jot::SectionColor *)*((unsigned int *)a4 + 106),
                               v29);
      a6 = AdjustedSectionColor & 0xFF00 | BYTE2(AdjustedSectionColor) | ((AdjustedSectionColor | 0xFFFFFF00) << 16);
      Gdiplus::Pen::Pen((Gdiplus::Pen *)&v42, (const struct Gdiplus::Color *)&a6, 1.0);
      Gdiplus::Graphics::DrawPath(v15, &v42, &v36);
      Gdiplus::Graphics::DrawPath(v15, &v42, &v34);
      GdipDeletePen(*(_QWORD *)&v42.left);
      GdipDeletePath(*(_QWORD *)&v34.left);
      GdipDeletePath(v36);
    }
    GdipDeletePen(v40);
    GdipDeletePath(v38);
  }
}

```

## disassembly

```asm
0x14003add4  mov     rax, rsp
0x14003add7  mov     [rax+8], rbx
0x14003addb  mov     [rax+10h], rsi
0x14003addf  mov     [rax+18h], rdi
0x14003ade3  push    rbp
0x14003ade4  push    r12
0x14003ade6  push    r13
0x14003ade8  push    r14
0x14003adea  push    r15
0x14003adec  lea     rbp, [rax-4Fh]
0x14003adf0  sub     rsp, 0A0h
0x14003adf7  movaps  xmmword ptr [rax-38h], xmm6
0x14003adfb  mov     r13, r9
0x14003adfe  mov     r12, rdx
0x14003ae01  mov     rdi, rcx
0x14003ae04  movups  xmm0, xmmword ptr [r8]
0x14003ae08  movdqu  xmmword ptr [rbp+47h+var_40.left], xmm0
0x14003ae0d  call    ?GetIsCurrent@CRiffleTab@Jot@@QEBA_NXZ; Jot::CRiffleTab::GetIsCurrent(void)
0x14003ae12  mov     r15b, al
0x14003ae15  mov     rcx, [r13+120h]
0x14003ae1c  mov     r8, [rcx]
0x14003ae1f  mov     rax, [r8+8]
0x14003ae23  call    cs:__guard_dispatch_icall_fptr
0x14003ae29  mov     sil, al
0x14003ae2c  test    r15b, r15b
0x14003ae2f  jnz     loc_14003AFD4
0x14003ae35  mov     r14b, 1
0x14003ae38  mov     bl, [rdi+0C3h]
0x14003ae3e  and     bl, 1
0x14003ae41  mov     rcx, rdi; this
0x14003ae44  call    ?GetPageLevelIndex@CRiffleTab@Jot@@QEAAHXZ; Jot::CRiffleTab::GetPageLevelIndex(void)
0x14003ae49  lea     rcx, [r13+1B0h]; this
0x14003ae50  mov     [rsp+0C0h+var_A0], r14b; bool
0x14003ae55  mov     r9b, bl; bool
0x14003ae58  lea     r8, [rbp+47h+var_40]; struct tagRECT *
0x14003ae5c  mov     edx, eax; int
0x14003ae5e  call    ?GetTabRect@CRiffleTabStyleManager@Jot@@QEAAXHAEAUtagRECT@@_N1@Z; Jot::CRiffleTabStyleManager::GetTabRect(int,tagRECT &,bool,bool)
0x14003ae63  mov     rcx, r12; this
0x14003ae66  call    ?UseGraphics@CHDCOrGdipGraphcs@Jot@@QEAAPEAVGraphics@Gdiplus@@XZ; Jot::CHDCOrGdipGraphcs::UseGraphics(void)
0x14003ae6b  mov     r14, rax
0x14003ae6e  mov     edx, 3
0x14003ae73  mov     rcx, rax
0x14003ae76  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x14003ae7b  movaps  xmm0, xmmword ptr [rbp+47h+var_40.left]
0x14003ae7f  movdqa  xmmword ptr [rbp+47h+var_90.left], xmm0
0x14003ae84  movdqa  [rbp+47h+var_80], xmm0
0x14003ae89  mov     r12b, byte ptr [rbp+47h+arg_28]
0x14003ae8d  test    r12b, r12b
0x14003ae90  jnz     loc_14003AFE5
0x14003ae96  test    sil, sil
0x14003ae99  jz      loc_14003B019
0x14003ae9f  inc     [rbp+47h+var_90.right]
0x14003aea2  mov     r9b, [rbp+47h+arg_20]; bool
0x14003aea6  lea     r8, [rbp+47h+var_90]; struct tagRECT *
0x14003aeaa  mov     rdx, r14; struct Gdiplus::Graphics *
0x14003aead  mov     rcx, rdi; this
0x14003aeb0  call    ?FillTab@CRiffleTab@Jot@@AEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@_N@Z; Jot::CRiffleTab::FillTab(Gdiplus::Graphics *,tagRECT const &,bool)
0x14003aeb5  mov     rcx, rdi; this
0x14003aeb8  call    ?GetScaleFactor@DPIUtils@Jot@@YAMPEBVElement@NetUI@@@Z; Jot::DPIUtils::GetScaleFactor(NetUI::Element const *)
0x14003aebd  call    roundf_0
0x14003aec2  cvttss2si eax, xmm0
0x14003aec6  mov     [rbp+47h+arg_28], eax
0x14003aec9  test    r15b, r15b
0x14003aecc  jnz     short loc_14003AEF4
0x14003aece  lea     r11, [rsp+0C0h+var_20]
0x14003aed6  mov     rbx, [r11+30h]
0x14003aeda  mov     rsi, [r11+38h]
0x14003aede  mov     rdi, [r11+40h]
0x14003aee2  movaps  xmm6, xmmword ptr [r11-10h]
0x14003aee7  mov     rsp, r11
0x14003aeea  pop     r15
0x14003aeec  pop     r14
0x14003aeee  pop     r13
0x14003aef0  pop     r12
0x14003aef2  pop     rbp
0x14003aef3  retn
0x14003aef4  test    sil, sil
0x14003aef7  jnz     short loc_14003AECE
0x14003aef9  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x14003aeff  test    al, al
0x14003af01  jnz     short loc_14003AECE
0x14003af03  mov     [rbp+47h+var_60], 0
0x14003af0b  lea     rdx, [rbp+47h+var_60]
0x14003af0f  xor     ecx, ecx
0x14003af11  call    cs:__imp_GdipCreatePath
0x14003af17  mov     [rbp+47h+var_58], eax
0x14003af1a  mov     rax, [r13+120h]
0x14003af21  mov     r8b, [rdi+0C3h]
0x14003af28  and     r8b, 1; struct tagRECT *
0x14003af2c  mov     qword ptr [rsp+0C0h+var_A0], rax; bool
0x14003af31  mov     r9b, r15b; bool
0x14003af34  lea     rdx, [rbp+47h+var_80]; struct Gdiplus::GraphicsPath *
0x14003af38  lea     rcx, [rbp+47h+var_60]; this
0x14003af3c  call    ?GeneratePageTabOutlinePath@Jot@@YAXAEAVGraphicsPath@Gdiplus@@AEBUtagRECT@@_N2PEAUANavigationUIHost@1@@Z; Jot::GeneratePageTabOutlinePath(Gdiplus::GraphicsPath &,tagRECT const &,bool,bool,Jot::ANavigationUIHost *)
0x14003af41  mov     ecx, [r13+1A8h]; this
0x14003af48  call    ?GetActivePageTabBorder@SectionColor@Jot@@YAKK@Z; Jot::SectionColor::GetActivePageTabBorder(ulong)
0x14003af4d  movzx   ecx, ax
0x14003af50  movzx   ebx, al
0x14003af53  mov     r15d, 0FFFFFF00h
0x14003af59  or      ebx, r15d
0x14003af5c  shl     ebx, 10h
0x14003af5f  shr     eax, 10h
0x14003af62  movzx   eax, al
0x14003af65  or      ebx, eax
0x14003af67  and     ecx, r15d
0x14003af6a  or      ebx, ecx
0x14003af6c  movd    xmm6, [rbp+47h+arg_28]
0x14003af71  cvtdq2ps xmm6, xmm6
0x14003af74  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x14003af7a  xor     esi, esi
0x14003af7c  test    eax, eax
0x14003af7e  jnz     loc_14003B034
0x14003af84  mov     [rbp+47h+var_50], rsi
0x14003af88  lea     r9, [rbp+47h+var_50]
0x14003af8c  xor     r8d, r8d
0x14003af8f  movaps  xmm1, xmm6
0x14003af92  mov     ecx, ebx
0x14003af94  call    cs:__imp_GdipCreatePen1
0x14003af9a  mov     [rbp+47h+var_48], eax
0x14003af9d  mov     r8, [rbp+47h+var_60]
0x14003afa1  mov     rdx, [rbp+47h+var_50]
0x14003afa5  mov     rcx, [r14]
0x14003afa8  call    cs:__imp_GdipDrawPath
0x14003afae  test    eax, eax
0x14003afb0  jnz     short loc_14003B013
0x14003afb2  test    r12b, r12b
0x14003afb5  jnz     loc_14003B041
0x14003afbb  mov     rcx, [rbp+47h+var_50]
0x14003afbf  call    cs:__imp_GdipDeletePen
0x14003afc5  mov     rcx, [rbp+47h+var_60]
0x14003afc9  call    cs:__imp_GdipDeletePath
0x14003afcf  jmp     loc_14003AECE
0x14003afd4  test    sil, sil
0x14003afd7  jnz     loc_14003AE35
0x14003afdd  xor     r14d, r14d
0x14003afe0  jmp     loc_14003AE38
0x14003afe5  psrldq  xmm0, 8
0x14003afea  movq    rax, xmm0
0x14003afef  shr     rax, 20h
0x14003aff3  add     eax, 0FFFFFFFCh
0x14003aff6  mov     dword ptr [rbp+47h+var_80+0Ch], eax
0x14003aff9  test    r15b, r15b
0x14003affc  jz      loc_14003AE96
0x14003b002  test    sil, sil
0x14003b005  jnz     loc_14003AE9F
0x14003b00b  mov     [rbp+47h+var_90.bottom], eax
0x14003b00e  jmp     loc_14003AE96
0x14003b013  mov     [r14+8], eax
0x14003b017  jmp     short loc_14003AFB2
0x14003b019  mov     rcx, rdi; this
0x14003b01c  call    ?FPrevPageTabCurrent@CRiffleTab@Jot@@AEAA_NXZ; Jot::CRiffleTab::FPrevPageTabCurrent(void)
0x14003b021  test    al, al
0x14003b023  jz      loc_14003AEA2
0x14003b029  inc     [rbp+47h+var_90.top]
0x14003b02c  inc     dword ptr [rbp+47h+var_80+4]
0x14003b02f  jmp     loc_14003AEA2
0x14003b034  maxss   xmm6, cs:__real@40000000
0x14003b03c  jmp     loc_14003AF84
0x14003b041  mov     [rbp+47h+var_70], rsi
0x14003b045  lea     rdx, [rbp+47h+var_70]
0x14003b049  xor     ecx, ecx
0x14003b04b  call    cs:__imp_GdipCreatePath
0x14003b051  mov     [rbp+47h+var_68], eax
0x14003b054  mov     qword ptr [rbp+47h+var_90.left], rsi
0x14003b058  lea     rdx, [rbp+47h+var_90]
0x14003b05c  xor     ecx, ecx
0x14003b05e  call    cs:__imp_GdipCreatePath
0x14003b064  mov     [rbp+47h+var_90.right], eax
0x14003b067  mov     r8b, [rdi+0C3h]
0x14003b06e  and     r8b, 1; struct tagRECT *
0x14003b072  mov     dword ptr [rsp+0C0h+var_A0], esi; bool
0x14003b076  xor     r9d, r9d; bool
0x14003b079  lea     rdx, [rbp+47h+var_80]; struct Gdiplus::GraphicsPath *
0x14003b07d  lea     rcx, [rbp+47h+var_70]; this
0x14003b081  call    ?GeneratePageTabPaperStackPath@Jot@@YAXAEAVGraphicsPath@Gdiplus@@AEBUtagRECT@@_N2H@Z; Jot::GeneratePageTabPaperStackPath(Gdiplus::GraphicsPath &,tagRECT const &,bool,bool,int)
0x14003b086  mov     r8b, [rdi+0C3h]
0x14003b08d  and     r8b, 1; struct tagRECT *
0x14003b091  mov     dword ptr [rsp+0C0h+var_A0], 1; bool
0x14003b099  xor     r9d, r9d; bool
0x14003b09c  lea     rdx, [rbp+47h+var_80]; struct Gdiplus::GraphicsPath *
0x14003b0a0  lea     rcx, [rbp+47h+var_90]; this
0x14003b0a4  call    ?GeneratePageTabPaperStackPath@Jot@@YAXAEAVGraphicsPath@Gdiplus@@AEBUtagRECT@@_N2H@Z; Jot::GeneratePageTabPaperStackPath(Gdiplus::GraphicsPath &,tagRECT const &,bool,bool,int)
0x14003b0a9  mov     ecx, [r13+1A8h]; this
0x14003b0b0  call    ?GetAdjustedSectionColor@SectionColor@Jot@@YAKK@Z; Jot::SectionColor::GetAdjustedSectionColor(ulong)
0x14003b0b5  movzx   ecx, ax
0x14003b0b8  movzx   edx, al
0x14003b0bb  or      edx, r15d
0x14003b0be  shl     edx, 10h
0x14003b0c1  shr     eax, 10h
0x14003b0c4  movzx   eax, al
0x14003b0c7  or      edx, eax
0x14003b0c9  and     ecx, r15d
0x14003b0cc  or      edx, ecx
0x14003b0ce  mov     [rbp+47h+arg_28], edx
0x14003b0d1  movss   xmm2, cs:__real@3f800000; float
0x14003b0d9  lea     rdx, [rbp+47h+arg_28]; struct Gdiplus::Color *
0x14003b0dd  lea     rcx, [rbp+47h+var_40]; this
0x14003b0e1  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x14003b0e6  lea     r8, [rbp+47h+var_70]
0x14003b0ea  lea     rdx, [rbp+47h+var_40]
0x14003b0ee  mov     rcx, r14
0x14003b0f1  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x14003b0f6  lea     r8, [rbp+47h+var_90]
0x14003b0fa  lea     rdx, [rbp+47h+var_40]
0x14003b0fe  mov     rcx, r14
0x14003b101  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x14003b106  mov     rcx, qword ptr [rbp+47h+var_40.left]
0x14003b10a  call    cs:__imp_GdipDeletePen
0x14003b110  mov     rcx, qword ptr [rbp+47h+var_90.left]
0x14003b114  call    cs:__imp_GdipDeletePath
0x14003b11a  mov     rcx, [rbp+47h+var_70]
0x14003b11e  call    cs:__imp_GdipDeletePath
0x14003b124  jmp     loc_14003AFBB
```
