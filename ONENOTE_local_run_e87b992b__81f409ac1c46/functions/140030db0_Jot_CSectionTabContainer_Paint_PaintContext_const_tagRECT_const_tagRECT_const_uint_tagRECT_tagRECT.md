# Jot::CSectionTabContainer::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)

- ea: `0x140030db0`
- end: `0x140030fea`
- name: `?Paint@CSectionTabContainer@Jot@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z`
- size: `570`
- prototype: `void __usercall(Jot::CSectionTabContainer *__hidden this@<rcx>, const struct PaintContext *@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, unsigned int, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1400197f8`
- `0x140030db0`
- `0x14003b714`
- `0x14003d740`
- `0x14003f27c`
- `0x140049270`
- `0x1400a08c8`
- `0x1400a2378`
- `0x1400ab9b8`
- `0x1400b3970`
- `0x14014b9a8`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140030e1f`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140030e81`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140030e1f`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x140030e81`
- `gdiplus!GdipDeletePath` at `0x140030fb8`
- `gdiplus!GdipDeletePath` at `0x140030fb8`
- `gdiplus!GdipCreatePath` at `0x140030f4f`
- `gdiplus!GdipCreatePath` at `0x140030f4f`
- `gdiplus!GdipDeleteGraphics` at `0x140030fc2`
- `gdiplus!GdipDeleteGraphics` at `0x140030fc2`
- `gdiplus!GdipDeleteBrush` at `0x140030fae`
- `gdiplus!GdipDeleteBrush` at `0x140030fae`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140030eff`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x140030eff`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z` at `0x140030ea5`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z` at `0x140030ea5`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x140030eeb`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x140030eeb`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x140030ed5`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x140030ed5`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x140030df2`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x140030df2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140030ee4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140030ee4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Jot::CSectionTabContainer::Paint(
        Jot::CSectionTabContainer *this,
        const struct PaintContext *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        unsigned int a5,
        struct tagRECT *a6,
        struct tagRECT *a7)
{
  char v10; // bl
  LONG left; // ebx
  int v12; // ebx
  Jot *v13; // rcx
  int v14; // ebx
  unsigned int top; // r12d
  __int64 v16; // rdi
  unsigned int v17; // r14d
  Jot *v18; // rcx
  NetUI::Fill *ForegroundColor; // rax
  unsigned int PrimaryARGBColor; // eax
  const struct NetUI::Element *v21; // rdx
  int v22; // eax
  __int64 v23; // rcx
  unsigned __int8 v24; // eax^2
  __int16 v25; // ax
  int ScaledValue; // edi
  struct NetUI::Value *v27; // [rsp+40h] [rbp-40h] BYREF
  __int64 v28; // [rsp+48h] [rbp-38h] BYREF
  int v29; // [rsp+50h] [rbp-30h]
  _QWORD v30[2]; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v32; // [rsp+70h] [rbp-10h]

  v10 = a5;
  NetUI::Element::Paint(this, a2, a3, a4, a5, a6, a7);
  if ( (v10 & 0x10) != 0 && (int)Jot::CSectionTabContainer::GetDragInsertionPtX(this) > -1 )
  {
    left = a3->left;
    v12 = Jot::CSectionTabContainer::GetDragInsertionPtX(this) + left;
    v14 = v12 - 1 + 2 * Jot::IsLicensedForFluentUI(v13);
    top = a3->top;
    v16 = *((unsigned int *)this + 90);
    v17 = v14;
    if ( (int)v16 > -1 && (int)v16 < (int)Jot::CSectionTabContainer::GetTabCount(this) )
    {
      if ( (unsigned int)v16 >= *((_DWORD *)this + 78) )
      {
        CrashWithRecovery(0x1E892496u, 0);
        goto LABEL_12;
      }
      if ( Jot::CSectionTabBase::GetIsCurrent(*(Jot::CSectionTabBase **)(*((_QWORD *)this + 38) + 8 * v16)) )
        v17 = v14 - 1;
    }
    *((_BYTE *)a2 + 48) = 1;
    Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)v30, *((HDC *)a2 + 2));
    if ( Jot::IsLicensedForFluentUI(v18) )
    {
      v27 = 0;
      ForegroundColor = NetUI::Element::GetForegroundColor(this, &v27);
      PrimaryARGBColor = NetUI::Fill::GetPrimaryARGBColor(ForegroundColor, this);
      v21 = (const struct NetUI::Element *)(PrimaryARGBColor & 0xFF00
                                          | ((PrimaryARGBColor & 0xFFFFFF) >> 16)
                                          | ((PrimaryARGBColor | 0xFFFFFF00) << 16));
      a5 = PrimaryARGBColor & 0xFF00 | ((PrimaryARGBColor & 0xFFFFFF) >> 16) | ((PrimaryARGBColor | 0xFFFFFF00) << 16);
      if ( v27 )
        NetUI::BaseValue::Release(v27);
LABEL_15:
      Jot::DPIUtils::GetScaleFactor(this, v21);
      ScaledValue = Jot::GetScaledValue(4, 5);
      v28 = 0;
      v29 = GdipCreatePath(0, &v28);
      Gdiplus::GraphicsPath::AddLine(&v28, v17 - ScaledValue, top, v17, ScaledValue + top);
      Gdiplus::GraphicsPath::AddLine(&v28, v17, ScaledValue + top, ScaledValue + v17, top);
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v31, (const struct Gdiplus::Color *)&a5);
      Gdiplus::Graphics::FillPath(v30, v31, &v28);
      GdipDeleteBrush(v32);
      GdipDeletePath(v28);
      GdipDeleteGraphics(v30[0]);
      return;
    }
LABEL_12:
    v22 = MsoFCbvHighContrast();
    v23 = 1894;
    if ( !v22 )
      v23 = 2993;
    MsoCrCbvGet(v23);
    v21 = (const struct NetUI::Element *)(v25 & 0xFF00 | v24 | (((unsigned __int8)v25 | 0xFFFFFF00) << 16));
    a5 = v25 & 0xFF00 | v24 | ((v25 | 0xFFFFFF00) << 16);
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x140030db0  mov     r11, rsp
0x140030db3  mov     [r11+8], rbx
0x140030db7  mov     [r11+10h], rsi
0x140030dbb  mov     [r11+18h], rdi
0x140030dbf  mov     [r11+20h], r12
0x140030dc3  push    rbp
0x140030dc4  push    r14
0x140030dc6  push    r15
0x140030dc8  mov     rbp, rsp
0x140030dcb  sub     rsp, 80h
0x140030dd2  mov     r14, r8
0x140030dd5  mov     r15, rdx
0x140030dd8  mov     rsi, rcx
0x140030ddb  mov     rax, [rbp+arg_30]
0x140030ddf  mov     [r11-68h], rax
0x140030de3  mov     rax, [rbp+arg_28]
0x140030de7  mov     [r11-70h], rax
0x140030deb  mov     ebx, [rbp+arg_20]
0x140030dee  mov     [rsp+80h+var_60], ebx
0x140030df2  call    cs:__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z; NetUI::Element::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)
0x140030df8  test    bl, 10h
0x140030dfb  jz      loc_140030FC9
0x140030e01  mov     rcx, rsi; this
0x140030e04  call    ?GetDragInsertionPtX@CSectionTabContainer@Jot@@QEBAHXZ; Jot::CSectionTabContainer::GetDragInsertionPtX(void)
0x140030e09  cmp     eax, 0FFFFFFFFh
0x140030e0c  jle     loc_140030FC9
0x140030e12  mov     ebx, [r14]
0x140030e15  mov     rcx, rsi; this
0x140030e18  call    ?GetDragInsertionPtX@CSectionTabContainer@Jot@@QEBAHXZ; Jot::CSectionTabContainer::GetDragInsertionPtX(void)
0x140030e1d  add     ebx, eax
0x140030e1f  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x140030e25  movzx   ecx, al
0x140030e28  dec     ebx
0x140030e2a  lea     ebx, [rbx+rcx*2]
0x140030e2d  mov     r12d, [r14+4]
0x140030e31  mov     edi, [rsi+168h]
0x140030e37  mov     r14d, ebx
0x140030e3a  cmp     edi, 0FFFFFFFFh
0x140030e3d  jle     short loc_140030E6F
0x140030e3f  mov     rcx, rsi; this
0x140030e42  call    ?GetTabCount@CSectionTabContainer@Jot@@QEBAHXZ; Jot::CSectionTabContainer::GetTabCount(void)
0x140030e47  cmp     edi, eax
0x140030e49  jge     short loc_140030E6F
0x140030e4b  cmp     edi, [rsi+138h]
0x140030e51  jnb     loc_140030EDD
0x140030e57  mov     rcx, [rsi+130h]
0x140030e5e  mov     rcx, [rcx+rdi*8]; this
0x140030e62  call    ?GetIsCurrent@CSectionTabBase@Jot@@QEBA_NXZ; Jot::CSectionTabBase::GetIsCurrent(void)
0x140030e67  test    al, al
0x140030e69  jz      short loc_140030E6F
0x140030e6b  lea     r14d, [rbx-1]
0x140030e6f  mov     byte ptr [r15+30h], 1
0x140030e74  mov     rdx, [r15+10h]; HDC
0x140030e78  lea     rcx, [rbp+var_28]; this
0x140030e7c  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x140030e81  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x140030e87  test    al, al
0x140030e89  jz      short loc_140030EEB
0x140030e8b  mov     [rbp+var_40], 0
0x140030e93  lea     rdx, [rbp+var_40]; struct NetUI::Value **
0x140030e97  mov     rcx, rsi; this
0x140030e9a  call    ?GetForegroundColor@Element@NetUI@@QEBAPEBUFill@2@PEAPEAVValue@2@@Z; NetUI::Element::GetForegroundColor(NetUI::Value * *)
0x140030e9f  mov     rdx, rsi
0x140030ea2  mov     rcx, rax
0x140030ea5  call    cs:__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKPEBVElement@2@@Z; NetUI::Fill::GetPrimaryARGBColor(NetUI::Element const *)
0x140030eab  and     eax, 0FFFFFFh
0x140030eb0  mov     edx, eax
0x140030eb2  or      edx, 0FFFFFF00h
0x140030eb8  shl     edx, 10h
0x140030ebb  mov     ecx, eax
0x140030ebd  shr     ecx, 10h
0x140030ec0  or      edx, ecx
0x140030ec2  and     eax, 0FF00h
0x140030ec7  or      edx, eax
0x140030ec9  mov     [rbp+arg_20], edx
0x140030ecc  mov     rcx, [rbp+var_40]
0x140030ed0  test    rcx, rcx
0x140030ed3  jz      short loc_140030F27
0x140030ed5  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x140030edb  jmp     short loc_140030F27
0x140030edd  xor     edx, edx
0x140030edf  mov     ecx, 1E892496h
0x140030ee4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140030eea  nop
0x140030eeb  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x140030ef1  test    eax, eax
0x140030ef3  mov     ecx, 766h
0x140030ef8  jnz     short loc_140030EFF
0x140030efa  mov     ecx, 0BB1h
0x140030eff  call    cs:__imp_MsoCrCbvGet
0x140030f05  movzx   ecx, ax
0x140030f08  movzx   edx, al
0x140030f0b  mov     r8d, 0FFFFFF00h
0x140030f11  shr     eax, 10h
0x140030f14  or      edx, r8d
0x140030f17  movzx   eax, al
0x140030f1a  shl     edx, 10h
0x140030f1d  and     ecx, r8d
0x140030f20  or      edx, eax
0x140030f22  or      edx, ecx; struct NetUI::Element *
0x140030f24  mov     [rbp+arg_20], edx
0x140030f27  mov     rcx, rsi; this
0x140030f2a  call    ?GetScaleFactor@DPIUtils@Jot@@YAMPEBVElement@NetUI@@@Z; Jot::DPIUtils::GetScaleFactor(NetUI::Element const *)
0x140030f2f  movaps  xmm2, xmm0
0x140030f32  mov     edx, 5
0x140030f37  lea     ecx, [rdx-1]
0x140030f3a  call    ?GetScaledValue@Jot@@YAHHW4ScaleFactor@1@M@Z; Jot::GetScaledValue(int,Jot::ScaleFactor,float)
0x140030f3f  mov     edi, eax
0x140030f41  mov     [rbp+var_38], 0
0x140030f49  lea     rdx, [rbp+var_38]
0x140030f4d  xor     ecx, ecx
0x140030f4f  call    cs:__imp_GdipCreatePath
0x140030f55  mov     [rbp+var_30], eax
0x140030f58  lea     ebx, [rdi+r12]
0x140030f5c  mov     edx, r14d
0x140030f5f  sub     edx, edi
0x140030f61  mov     [rsp+80h+var_60], ebx
0x140030f65  mov     r9d, r14d
0x140030f68  mov     r8d, r12d
0x140030f6b  lea     rcx, [rbp+var_38]
0x140030f6f  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x140030f74  lea     r9d, [rdi+r14]
0x140030f78  mov     [rsp+80h+var_60], r12d
0x140030f7d  mov     r8d, ebx
0x140030f80  mov     edx, r14d
0x140030f83  lea     rcx, [rbp+var_38]
0x140030f87  call    ?AddLine@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHH@Z; Gdiplus::GraphicsPath::AddLine(int,int,int,int)
0x140030f8c  lea     rdx, [rbp+arg_20]; struct Gdiplus::Color *
0x140030f90  lea     rcx, [rbp+var_18]; this
0x140030f94  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x140030f99  lea     r8, [rbp+var_38]
0x140030f9d  lea     rdx, [rbp+var_18]
0x140030fa1  lea     rcx, [rbp+var_28]
0x140030fa5  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x140030faa  mov     rcx, [rbp+var_10]
0x140030fae  call    cs:__imp_GdipDeleteBrush
0x140030fb4  mov     rcx, [rbp+var_38]
0x140030fb8  call    cs:__imp_GdipDeletePath
0x140030fbe  mov     rcx, [rbp+var_28]
0x140030fc2  call    cs:__imp_GdipDeleteGraphics
0x140030fc8  nop
0x140030fc9  lea     r11, [rsp+80h+var_s0]
0x140030fd1  mov     rbx, [r11+20h]
0x140030fd5  mov     rsi, [r11+28h]
0x140030fd9  mov     rdi, [r11+30h]
0x140030fdd  mov     r12, [r11+38h]
0x140030fe1  mov     rsp, r11
0x140030fe4  pop     r15
0x140030fe6  pop     r14
0x140030fe8  pop     rbp
0x140030fe9  retn
```
