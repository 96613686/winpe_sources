# FadeElement::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x1800ae6a0`
- end: `0x1800ae96f`
- name: `?Paint@FadeElement@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU3@2@Z`
- size: `719`
- prototype: `void __usercall(FadeElement *__hidden this@<rcx>, HDC hdcDest@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180033370`
- `0x1800ae6a0`
- `0x1800aea44`

## import_xrefs

- `USER32!FillRect` at `0x1800ae7ba`
- `USER32!FillRect` at `0x1800ae7ba`
- `GDI32!GdiAlphaBlend` at `0x1800ae8dc`
- `GDI32!GdiAlphaBlend` at `0x1800ae8dc`
- `GDI32!DeleteObject` at `0x1800ae7c3`
- `GDI32!DeleteObject` at `0x1800ae7c3`
- `GDI32!CreateSolidBrush` at `0x1800ae7a3`
- `GDI32!CreateSolidBrush` at `0x1800ae7a3`
- `UxTheme!BeginBufferedPaint` at `0x1800ae74b`
- `UxTheme!BeginBufferedPaint` at `0x1800ae74b`
- `UxTheme!EndBufferedPaint` at `0x1800ae8e9`
- `UxTheme!EndBufferedPaint` at `0x1800ae8e9`
- `UxTheme!BufferedPaintClear` at `0x1800ae760`
- `UxTheme!BufferedPaintClear` at `0x1800ae760`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae822`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae866`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae95d`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae822`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae866`
- `DUI70!?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z` at `0x1800ae95d`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800ae6f7`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800ae6f7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae7d2`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae8f8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae907`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae7d2`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae8f8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800ae907`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae783`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae7e9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae838`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae921`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae783`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae7e9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae838`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800ae921`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800ae779`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800ae7df`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall FadeElement::Paint(
        FadeElement *this,
        HDC hdcDest,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        struct tagRECT *a5,
        struct tagRECT *a6)
{
  float v10; // xmm0_4
  HPAINTBUFFER v11; // rax
  DirectUI::Element *UIItemsView; // rax
  struct DirectUI::Value *v13; // rax
  DirectUI::Value *v14; // rbx
  COLORREF ColorFromValue; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v17; // rdi
  struct DirectUI::Value *v18; // r12
  struct DirectUI::Value *v19; // r15
  DirectUI::Value *v20; // rcx
  struct DirectUI::Value *Value; // rbx
  HDC phdc; // [rsp+60h] [rbp-78h] BYREF
  HPAINTBUFFER hBufferedPaint; // [rsp+68h] [rbp-70h]
  struct DirectUI::Value *v24; // [rsp+70h] [rbp-68h]
  BLENDFUNCTION ftn; // [rsp+E0h] [rbp+8h]

  v10 = *((float *)this + 50);
  if ( v10 == 1.0 )
  {
    DirectUI::Element::Paint(this, hdcDest, a3, a4, a5, a6);
    return;
  }
  if ( v10 == 0.0 )
  {
    Value = DirectUI::Element::GetValue(this, FadeElement::InitialBackgroundProp, 2, 0);
    DirectUI::Element::PaintBackground(this, hdcDest, Value, a3, a4, a5, a6);
    if ( Value )
    {
      v20 = Value;
      goto LABEL_16;
    }
  }
  else
  {
    phdc = 0;
    v11 = BeginBufferedPaint(hdcDest, a4, BPBF_TOPDOWNDIB, 0, &phdc);
    hBufferedPaint = v11;
    if ( v11 )
    {
      BufferedPaintClear(v11, 0);
      UIItemsView = GetUIItemsView(this);
      if ( UIItemsView )
      {
        v13 = DirectUI::Element::GetValue(
                UIItemsView,
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp,
                2,
                0);
        v14 = v13;
        if ( v13 )
        {
          ColorFromValue = GetColorFromValue(v13);
          SolidBrush = CreateSolidBrush(ColorFromValue);
          v17 = SolidBrush;
          if ( SolidBrush )
          {
            FillRect(hdcDest, a4, SolidBrush);
            DeleteObject(v17);
          }
        }
        if ( v14 )
          DirectUI::Value::Release(v14);
      }
      v18 = DirectUI::Element::GetValue(
              this,
              (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp,
              2,
              0);
      v24 = v18;
      DirectUI::Element::PaintBackground(this, hdcDest, v18, a3, a4, a5, a6);
      v19 = DirectUI::Element::GetValue(this, FadeElement::InitialBackgroundProp, 2, 0);
      DirectUI::Element::PaintBackground(this, phdc, v19, a3, a4, a5, a6);
      *(_WORD *)&ftn.BlendOp = 0;
      ftn.SourceConstantAlpha = (int)(float)((float)(1.0 - *((float *)this + 50)) * 255.0);
      ftn.AlphaFormat = 1;
      GdiAlphaBlend(
        hdcDest,
        a4->left,
        a4->top,
        a4->right - a4->left,
        a4->bottom - a4->top,
        phdc,
        a4->left,
        a4->top,
        a4->right - a4->left,
        a4->bottom - a4->top,
        ftn);
      EndBufferedPaint(hBufferedPaint, 0);
      if ( v19 )
        DirectUI::Value::Release(v19);
      if ( v18 )
      {
        v20 = v18;
LABEL_16:
        DirectUI::Value::Release(v20);
      }
    }
  }
}

```

## disassembly

```asm
0x1800ae6a0  mov     rax, rsp
0x1800ae6a3  push    rbx
0x1800ae6a4  push    rbp
0x1800ae6a5  push    rsi
0x1800ae6a6  push    rdi
0x1800ae6a7  push    r12
0x1800ae6a9  push    r13
0x1800ae6ab  push    r14
0x1800ae6ad  push    r15
0x1800ae6af  sub     rsp, 98h
0x1800ae6b6  movaps  xmmword ptr [rax-58h], xmm6
0x1800ae6ba  mov     r14, r9
0x1800ae6bd  mov     r13, r8
0x1800ae6c0  mov     rbp, rdx
0x1800ae6c3  mov     rsi, rcx
0x1800ae6c6  movss   xmm0, dword ptr [rcx+0C8h]
0x1800ae6ce  movss   xmm6, cs:__real@3f800000
0x1800ae6d6  ucomiss xmm0, xmm6
0x1800ae6d9  jp      short loc_1800AE719
0x1800ae6db  jnz     short loc_1800AE719
0x1800ae6dd  mov     rax, [rsp+0D8h+arg_28]
0x1800ae6e5  mov     [rsp+0D8h+hdcSrc], rax
0x1800ae6ea  mov     rax, [rsp+0D8h+arg_20]
0x1800ae6f2  mov     [rsp+0D8h+phdc], rax
0x1800ae6f7  call    cs:__imp_?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z; DirectUI::Element::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)
0x1800ae6fd  movaps  xmm6, [rsp+0D8h+var_58]
0x1800ae705  add     rsp, 98h
0x1800ae70c  pop     r15
0x1800ae70e  pop     r14
0x1800ae710  pop     r13
0x1800ae712  pop     r12
0x1800ae714  pop     rdi
0x1800ae715  pop     rsi
0x1800ae716  pop     rbp
0x1800ae717  pop     rbx
0x1800ae718  retn
0x1800ae719  ucomiss xmm0, cs:__real@00000000
0x1800ae720  jp      short loc_1800AE728
0x1800ae722  jz      loc_1800AE913
0x1800ae728  mov     [rsp+0D8h+var_78], 0
0x1800ae731  lea     rax, [rsp+0D8h+var_78]
0x1800ae736  mov     [rsp+0D8h+phdc], rax; phdc
0x1800ae73b  xor     r9d, r9d; pPaintParams
0x1800ae73e  lea     r15d, [r9+2]
0x1800ae742  mov     r8d, r15d; dwFormat
0x1800ae745  mov     rdx, r14; prcTarget
0x1800ae748  mov     rcx, rbp; hdcTarget
0x1800ae74b  call    cs:__imp_BeginBufferedPaint
0x1800ae751  mov     [rsp+0D8h+hBufferedPaint], rax
0x1800ae756  test    rax, rax
0x1800ae759  jz      short loc_1800AE6FD
0x1800ae75b  xor     edx, edx; prc
0x1800ae75d  mov     rcx, rax; hBufferedPaint
0x1800ae760  call    cs:__imp_BufferedPaintClear
0x1800ae766  mov     rcx, rsi; struct DirectUI::Element *
0x1800ae769  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x1800ae76e  test    rax, rax
0x1800ae771  jz      short loc_1800AE7D9
0x1800ae773  xor     r9d, r9d
0x1800ae776  mov     r8d, r15d
0x1800ae779  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x1800ae780  mov     rcx, rax
0x1800ae783  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae789  mov     rbx, rax
0x1800ae78c  mov     qword ptr [rsp+0D8h+arg_0.BlendOp], rax
0x1800ae794  test    rax, rax
0x1800ae797  jz      short loc_1800AE7CA
0x1800ae799  mov     rcx, rax; struct DirectUI::Value *
0x1800ae79c  call    ?GetColorFromValue@@YAKPEAVValue@DirectUI@@@Z; GetColorFromValue(DirectUI::Value *)
0x1800ae7a1  mov     ecx, eax; color
0x1800ae7a3  call    cs:__imp_CreateSolidBrush
0x1800ae7a9  mov     rdi, rax
0x1800ae7ac  test    rax, rax
0x1800ae7af  jz      short loc_1800AE7CA
0x1800ae7b1  mov     r8, rax; hbr
0x1800ae7b4  mov     rdx, r14; lprc
0x1800ae7b7  mov     rcx, rbp; hDC
0x1800ae7ba  call    cs:__imp_FillRect
0x1800ae7c0  mov     rcx, rdi; ho
0x1800ae7c3  call    cs:__imp_DeleteObject
0x1800ae7c9  nop
0x1800ae7ca  test    rbx, rbx
0x1800ae7cd  jz      short loc_1800AE7D9
0x1800ae7cf  mov     rcx, rbx
0x1800ae7d2  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae7d8  nop
0x1800ae7d9  xor     r9d, r9d
0x1800ae7dc  mov     r8d, r15d
0x1800ae7df  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x1800ae7e6  mov     rcx, rsi
0x1800ae7e9  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae7ef  mov     r12, rax
0x1800ae7f2  mov     [rsp+0D8h+var_68], rax
0x1800ae7f7  mov     rdi, [rsp+0D8h+arg_28]
0x1800ae7ff  mov     qword ptr [rsp+0D8h+xoriginSrc], rdi
0x1800ae804  mov     rbx, [rsp+0D8h+arg_20]
0x1800ae80c  mov     [rsp+0D8h+hdcSrc], rbx
0x1800ae811  mov     [rsp+0D8h+phdc], r14
0x1800ae816  mov     r9, r13
0x1800ae819  mov     r8, rax
0x1800ae81c  mov     rdx, rbp
0x1800ae81f  mov     rcx, rsi
0x1800ae822  call    cs:__imp_?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z; DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)
0x1800ae828  xor     r9d, r9d
0x1800ae82b  mov     r8d, r15d
0x1800ae82e  lea     rdx, ?InitialBackgroundProp@FadeElement@@SAPEBUPropertyInfo@DirectUI@@XZ; FadeElement::InitialBackgroundProp(void)
0x1800ae835  mov     rcx, rsi
0x1800ae838  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae83e  mov     r15, rax
0x1800ae841  mov     qword ptr [rsp+0D8h+arg_0.BlendOp], rax
0x1800ae849  mov     qword ptr [rsp+0D8h+xoriginSrc], rdi
0x1800ae84e  mov     [rsp+0D8h+hdcSrc], rbx
0x1800ae853  mov     [rsp+0D8h+phdc], r14
0x1800ae858  mov     r9, r13
0x1800ae85b  mov     r8, rax
0x1800ae85e  mov     rdx, [rsp+0D8h+var_78]
0x1800ae863  mov     rcx, rsi
0x1800ae866  call    cs:__imp_?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z; DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)
0x1800ae86c  mov     word ptr [rsp+0D8h+arg_0.BlendOp], 0
0x1800ae876  subss   xmm6, dword ptr [rsi+0C8h]
0x1800ae87e  mulss   xmm6, cs:__real@437f0000
0x1800ae886  cvttss2si eax, xmm6
0x1800ae88a  mov     [rsp+0D8h+arg_0.SourceConstantAlpha], al
0x1800ae891  mov     [rsp+0D8h+arg_0.AlphaFormat], 1
0x1800ae899  mov     r8d, [r14+4]; yoriginDest
0x1800ae89d  mov     ecx, [r14+0Ch]
0x1800ae8a1  sub     ecx, r8d
0x1800ae8a4  mov     edx, [r14]; xoriginDest
0x1800ae8a7  mov     r9d, [r14+8]
0x1800ae8ab  sub     r9d, edx; wDest
0x1800ae8ae  mov     eax, dword ptr [rsp+0D8h+arg_0.BlendOp]
0x1800ae8b5  mov     dword ptr [rsp+0D8h+ftn.BlendOp], eax; ftn
0x1800ae8b9  mov     [rsp+0D8h+hSrc], ecx; hSrc
0x1800ae8bd  mov     [rsp+0D8h+wSrc], r9d; wSrc
0x1800ae8c2  mov     [rsp+0D8h+yoriginSrc], r8d; yoriginSrc
0x1800ae8c7  mov     [rsp+0D8h+xoriginSrc], edx; xoriginSrc
0x1800ae8cb  mov     rax, [rsp+0D8h+var_78]
0x1800ae8d0  mov     [rsp+0D8h+hdcSrc], rax; hdcSrc
0x1800ae8d5  mov     dword ptr [rsp+0D8h+phdc], ecx; hDest
0x1800ae8d9  mov     rcx, rbp; hdcDest
0x1800ae8dc  call    cs:__imp_GdiAlphaBlend
0x1800ae8e2  xor     edx, edx; fUpdateTarget
0x1800ae8e4  mov     rcx, [rsp+0D8h+hBufferedPaint]; hBufferedPaint
0x1800ae8e9  call    cs:__imp_EndBufferedPaint
0x1800ae8ef  nop
0x1800ae8f0  test    r15, r15
0x1800ae8f3  jz      short loc_1800AE8FF
0x1800ae8f5  mov     rcx, r15
0x1800ae8f8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae8fe  nop
0x1800ae8ff  test    r12, r12
0x1800ae902  jz      short loc_1800AE90E
0x1800ae904  mov     rcx, r12
0x1800ae907  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800ae90d  nop
0x1800ae90e  jmp     loc_1800AE6FD
0x1800ae913  xor     r9d, r9d
0x1800ae916  lea     r8d, [r9+2]
0x1800ae91a  lea     rdx, ?InitialBackgroundProp@FadeElement@@SAPEBUPropertyInfo@DirectUI@@XZ; FadeElement::InitialBackgroundProp(void)
0x1800ae921  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800ae927  mov     rbx, rax
0x1800ae92a  mov     qword ptr [rsp+0D8h+arg_0.BlendOp], rax
0x1800ae932  mov     rcx, [rsp+0D8h+arg_28]
0x1800ae93a  mov     qword ptr [rsp+0D8h+xoriginSrc], rcx
0x1800ae93f  mov     rcx, [rsp+0D8h+arg_20]
0x1800ae947  mov     [rsp+0D8h+hdcSrc], rcx
0x1800ae94c  mov     [rsp+0D8h+phdc], r14
0x1800ae951  mov     r9, r13
0x1800ae954  mov     r8, rax
0x1800ae957  mov     rdx, rbp
0x1800ae95a  mov     rcx, rsi
0x1800ae95d  call    cs:__imp_?PaintBackground@Element@DirectUI@@QEAAXPEAUHDC__@@PEAVValue@2@AEBUtagRECT@@222@Z; DirectUI::Element::PaintBackground(HDC__ *,DirectUI::Value *,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)
0x1800ae963  nop
0x1800ae964  test    rbx, rbx
0x1800ae967  jz      short loc_1800AE90E
0x1800ae969  mov     rcx, rbx
0x1800ae96c  jmp     short loc_1800AE907
```
