# CIconicAnimatedVisual::SetupVisuals(void)

- ea: `0x1800920e0`
- end: `0x180092302`
- name: `?SetupVisuals@CIconicAnimatedVisual@@AEAAJXZ`
- size: `546`
- prototype: `__int64 __fastcall(CIconicAnimatedVisual *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b9220`

## callees

- `0x1800029e8`
- `0x180004a44`
- `0x18000e41c`
- `0x18000e98c`
- `0x18000eeac`
- `0x18000fb00`
- `0x180010930`
- `0x18001ce98`
- `0x180038408`
- `0x18003a338`
- `0x180052df0`
- `0x180081a68`
- `0x180081b58`
- `0x1800920e0`
- `0x180092308`
- `0x1800ea010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x180092102`
- `USER32!IsRectEmpty` at `0x180092102`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIconicAnimatedVisual::SetupVisuals(CIconicAnimatedVisual *this)
{
  const struct tagRECT *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, _QWORD, CRectangleVisual **); // r14
  CRectangleVisual *v8; // rcx
  unsigned int v9; // eax
  int updated; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const struct tagRECT *v13; // r14
  int v14; // eax
  __int64 v15; // rdx
  CRectangleVisual *v16; // rbx
  int v17; // eax
  int v18; // esi
  bool v19; // r8
  int v21; // [rsp+20h] [rbp-20h]
  struct _D3DCOLORVALUE v22; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  CRectangleVisual *v24; // [rsp+60h] [rbp+20h] BYREF

  v2 = (const struct tagRECT *)((char *)this + 264);
  if ( IsRectEmpty((const RECT *)((char *)this + 264)) )
  {
    v13 = (const struct tagRECT *)((char *)this + 248);
    goto LABEL_15;
  }
  v24 = 0;
  *(struct _D3DCOLORVALUE *)&v22.r = 0;
  CImmersiveState::GetPillarBoxColor(&v22);
  v6 = *(_QWORD *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 40LL);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, CRectangleVisual **))(*(_QWORD *)v6 + 64LL);
  v8 = v24;
  v24 = 0;
  if ( v8 )
    (*(void (__fastcall **)(CRectangleVisual *))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = WUColorFromD2DColor(&v22, v3, v4, v5);
  updated = v7(v6, v9, &v24);
  v11 = updated;
  if ( updated >= 0 )
  {
    updated = CNineGridVisual::UpdateInnerBrush<Windows::UI::Composition::ICompositionColorBrush *>(this);
    v11 = updated;
    if ( updated < 0 )
    {
      v12 = 143;
      goto LABEL_12;
    }
    v13 = (const struct tagRECT *)((char *)this + 248);
    updated = CNineGridVisual::UpdateInsets(
                this,
                (float)(*((_DWORD *)this + 62) - v2->left),
                0.0,
                (float)(*((_DWORD *)this + 68) - *((_DWORD *)this + 64)),
                0.0);
    v11 = updated;
    if ( updated < 0 )
    {
      v12 = 147;
      goto LABEL_12;
    }
    updated = CNineGridVisual::UpdateIsCenterHollow(this, 1);
    v11 = updated;
    if ( updated < 0 )
    {
      v12 = 148;
      goto LABEL_12;
    }
    CRectangleVisual::SetRect(this, v2);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v24);
LABEL_15:
    v24 = 0;
    wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(&v24);
    v14 = CSolidRectangleVisual::Create(&v24);
    v11 = v14;
    if ( v14 >= 0 )
    {
      v14 = CSurfaceBrush::ApplyViewportTransformForView((CIconicAnimatedVisual *)((char *)this + 232), v13);
      v11 = v14;
      if ( v14 >= 0 )
      {
        v16 = v24;
        v17 = CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(v24, *((_QWORD *)this + 29));
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9C,
            (unsigned int)"clientcore\\windows\\dwm\\udwm\\iconicanimatedvisual.cpp",
            (const char *)(unsigned int)v17,
            v21);
          v11 = v18;
          goto LABEL_25;
        }
        CRectangleVisual::SetRect(v16, v13);
        v14 = CContainerVisual::AddChild(this, v16, v19);
        v11 = v14;
        if ( v14 >= 0 )
        {
          v11 = 0;
          goto LABEL_25;
        }
        v15 = 159;
      }
      else
      {
        v15 = 155;
      }
    }
    else
    {
      v15 = 154;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\iconicanimatedvisual.cpp",
      (const char *)(unsigned int)v14,
      v21);
LABEL_25:
    wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(&v24);
    return v11;
  }
  v12 = 141;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\iconicanimatedvisual.cpp",
    (const char *)(unsigned int)updated,
    v21);
  wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v24);
  return v11;
}

```

## disassembly

```asm
0x1800920e0  mov     [rsp-18h+arg_8], rbx
0x1800920e5  mov     [rsp-18h+arg_10], rsi
0x1800920ea  push    rbp
0x1800920eb  push    rdi
0x1800920ec  push    r14
0x1800920ee  mov     rbp, rsp
0x1800920f1  sub     rsp, 40h
0x1800920f5  mov     rdi, rcx
0x1800920f8  lea     rsi, [rcx+108h]
0x1800920ff  mov     rcx, rsi; lprc
0x180092102  call    cs:__imp_IsRectEmpty
0x180092108  test    eax, eax
0x18009210a  jnz     loc_18009222E
0x180092110  mov     [rbp+arg_0], 0
0x180092118  xorps   xmm0, xmm0
0x18009211b  movups  xmmword ptr [rbp+var_10], xmm0
0x18009211f  lea     rcx, [rbp+var_10]; struct _D3DCOLORVALUE *
0x180092123  call    ?GetPillarBoxColor@CImmersiveState@@SAXPEAU_D3DCOLORVALUE@@@Z; CImmersiveState::GetPillarBoxColor(_D3DCOLORVALUE *)
0x180092128  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18009212f  mov     rcx, [rax+30h]
0x180092133  mov     rbx, [rcx+28h]
0x180092137  mov     rax, [rbx]
0x18009213a  mov     r14, [rax+40h]
0x18009213e  mov     rcx, [rbp+arg_0]
0x180092142  mov     [rbp+arg_0], 0
0x18009214a  test    rcx, rcx
0x18009214d  jz      short loc_18009215C
0x18009214f  mov     rax, [rcx]
0x180092152  mov     rax, [rax+10h]
0x180092156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009215b  nop
0x18009215c  lea     rcx, [rbp+var_10]
0x180092160  call    ?WUColorFromD2DColor@@YA?AUColor@UI@Windows@@AEBU_D3DCOLORVALUE@@@Z; WUColorFromD2DColor(_D3DCOLORVALUE const &)
0x180092165  lea     r8, [rbp+arg_0]
0x180092169  mov     edx, eax
0x18009216b  mov     rcx, rbx
0x18009216e  mov     rax, r14
0x180092171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092176  mov     ebx, eax
0x180092178  test    eax, eax
0x18009217a  jns     short loc_180092183
0x18009217c  mov     edx, 8Dh
0x180092181  jmp     short loc_1800921F5
0x180092183  mov     rdx, [rbp+arg_0]
0x180092187  mov     rcx, rdi
0x18009218a  call    ??$UpdateInnerBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CNineGridVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CNineGridVisual::UpdateInnerBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x18009218f  mov     ebx, eax
0x180092191  test    eax, eax
0x180092193  jns     short loc_18009219C
0x180092195  mov     edx, 8Fh
0x18009219a  jmp     short loc_1800921F5
0x18009219c  lea     r14, [rdi+0F8h]
0x1800921a3  mov     eax, [rdi+110h]
0x1800921a9  sub     eax, [rdi+100h]
0x1800921af  movd    xmm3, eax
0x1800921b3  cvtdq2ps xmm3, xmm3; float
0x1800921b6  mov     eax, [r14]
0x1800921b9  sub     eax, [rsi]
0x1800921bb  movd    xmm1, eax
0x1800921bf  cvtdq2ps xmm1, xmm1; float
0x1800921c2  xorps   xmm2, xmm2; float
0x1800921c5  movss   [rsp+40h+var_20], xmm2; int
0x1800921cb  mov     rcx, rdi; this
0x1800921ce  call    ?UpdateInsets@CNineGridVisual@@QEAAJMMMM@Z; CNineGridVisual::UpdateInsets(float,float,float,float)
0x1800921d3  mov     ebx, eax
0x1800921d5  test    eax, eax
0x1800921d7  jns     short loc_1800921E0
0x1800921d9  mov     edx, 93h
0x1800921de  jmp     short loc_1800921F5
0x1800921e0  mov     dl, 1; bool
0x1800921e2  mov     rcx, rdi; this
0x1800921e5  call    ?UpdateIsCenterHollow@CNineGridVisual@@QEAAJ_N@Z; CNineGridVisual::UpdateIsCenterHollow(bool)
0x1800921ea  mov     ebx, eax
0x1800921ec  test    eax, eax
0x1800921ee  jns     short loc_180092217
0x1800921f0  mov     edx, 94h; void *
0x1800921f5  mov     r9d, eax; char *
0x1800921f8  lea     r8, aClientcoreWind_81; "clientcore\\windows\\dwm\\udwm\\iconica"...
0x1800921ff  mov     rcx, [rbp+18h]; this
0x180092203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092208  nop
0x180092209  lea     rcx, [rbp+arg_0]
0x18009220d  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x180092212  jmp     loc_1800922ED
0x180092217  mov     rdx, rsi; struct tagRECT *
0x18009221a  mov     rcx, rdi; this
0x18009221d  call    ?SetRect@CRectangleVisual@@QEAAXAEBUtagRECT@@@Z; CRectangleVisual::SetRect(tagRECT const &)
0x180092222  nop
0x180092223  lea     rcx, [rbp+arg_0]
0x180092227  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18009222c  jmp     short loc_180092235
0x18009222e  lea     r14, [rdi+0F8h]
0x180092235  mov     [rbp+arg_0], 0
0x18009223d  lea     rcx, [rbp+arg_0]
0x180092241  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x180092246  lea     rcx, [rbp+arg_0]; struct CSolidRectangleVisual **
0x18009224a  call    ?Create@CSolidRectangleVisual@@SAJPEAPEAV1@@Z; CSolidRectangleVisual::Create(CSolidRectangleVisual * *)
0x18009224f  mov     ebx, eax
0x180092251  test    eax, eax
0x180092253  jns     short loc_18009225C
0x180092255  mov     edx, 9Ah
0x18009225a  jmp     short loc_180092279
0x18009225c  lea     rsi, [rdi+0E8h]
0x180092263  mov     rdx, r14; struct tagRECT *
0x180092266  mov     rcx, rsi; this
0x180092269  call    ?ApplyViewportTransformForView@CSurfaceBrush@@QEAAJAEBUtagRECT@@@Z; CSurfaceBrush::ApplyViewportTransformForView(tagRECT const &)
0x18009226e  mov     ebx, eax
0x180092270  test    eax, eax
0x180092272  jns     short loc_18009228E
0x180092274  mov     edx, 9Bh; void *
0x180092279  mov     rcx, [rbp+18h]; this
0x18009227d  mov     r9d, eax; char *
0x180092280  lea     r8, aClientcoreWind_81; "clientcore\\windows\\dwm\\udwm\\iconica"...
0x180092287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009228c  jmp     short loc_1800922E4
0x18009228e  mov     rdx, [rsi]
0x180092291  mov     rbx, [rbp+arg_0]
0x180092295  mov     rcx, rbx
0x180092298  call    ??$SetBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CSpriteVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x18009229d  mov     esi, eax
0x18009229f  test    eax, eax
0x1800922a1  jns     short loc_1800922BF
0x1800922a3  mov     rcx, [rbp+18h]; this
0x1800922a7  mov     r9d, eax; char *
0x1800922aa  lea     r8, aClientcoreWind_81; "clientcore\\windows\\dwm\\udwm\\iconica"...
0x1800922b1  mov     edx, 9Ch; void *
0x1800922b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800922bb  mov     ebx, esi
0x1800922bd  jmp     short loc_1800922E4
0x1800922bf  mov     rdx, r14; struct tagRECT *
0x1800922c2  mov     rcx, rbx; this
0x1800922c5  call    ?SetRect@CRectangleVisual@@QEAAXAEBUtagRECT@@@Z; CRectangleVisual::SetRect(tagRECT const &)
0x1800922ca  mov     rdx, rbx; struct CVisual *
0x1800922cd  mov     rcx, rdi; this
0x1800922d0  call    ?AddChild@CContainerVisual@@QEAAJPEAVCVisual@@_N@Z; CContainerVisual::AddChild(CVisual *,bool)
0x1800922d5  mov     ebx, eax
0x1800922d7  test    eax, eax
0x1800922d9  jns     short loc_1800922E2
0x1800922db  mov     edx, 9Fh
0x1800922e0  jmp     short loc_180092279
0x1800922e2  xor     ebx, ebx
0x1800922e4  lea     rcx, [rbp+arg_0]
0x1800922e8  call    ??1?$com_ptr_t@VCDisplaySecondaryOnlyToExtendAnimatedVisual@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(void)
0x1800922ed  mov     eax, ebx
0x1800922ef  mov     rbx, [rsp+40h+arg_8]
0x1800922f4  mov     rsi, [rsp+40h+arg_10]
0x1800922f9  add     rsp, 40h
0x1800922fd  pop     r14
0x1800922ff  pop     rdi
0x180092300  pop     rbp
0x180092301  retn
```
