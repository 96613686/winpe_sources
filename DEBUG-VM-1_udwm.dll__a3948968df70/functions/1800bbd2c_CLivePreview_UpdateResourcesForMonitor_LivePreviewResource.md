# CLivePreview::_UpdateResourcesForMonitor(LivePreviewResource *)

- ea: `0x1800bbd2c`
- end: `0x1800bbf83`
- name: `?_UpdateResourcesForMonitor@CLivePreview@@AEAAJPEAULivePreviewResource@@@Z`
- size: `599`
- prototype: `int(CLivePreview *__hidden this, struct LivePreviewResource *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bbc68`
- `0x1800bc0a0`

## callees

- `0x1800029e8`
- `0x180010930`
- `0x18001c2a8`
- `0x180038408`
- `0x18003a338`
- `0x18007f6b0`
- `0x18007fa18`
- `0x180081a68`
- `0x180081b58`
- `0x1800bbd2c`
- `0x1800bbf8c`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800bbd97`
- `USER32!IsRectEmpty` at `0x1800bbda2`
- `USER32!IsRectEmpty` at `0x1800bbd97`
- `USER32!IsRectEmpty` at `0x1800bbda2`
- `USER32!SetRectEmpty` at `0x1800bbd48`
- `USER32!SetRectEmpty` at `0x1800bbd55`
- `USER32!SetRectEmpty` at `0x1800bbd48`
- `USER32!SetRectEmpty` at `0x1800bbd55`

## pseudocode

```c
__int64 __fastcall CLivePreview::_UpdateResourcesForMonitor(CLivePreview *this, struct tagRECT *a2)
{
  const struct tagRECT *v2; // rbp
  const struct tagRECT *v5; // r15
  __int64 i; // rbx
  CLivePreview *v7; // rcx
  const struct CTopLevelWindow *v8; // rdx
  BOOL v9; // ebx
  BOOL v10; // eax
  CVisual *v11; // rcx
  BOOL v12; // r12d
  int v13; // ebx
  __int64 v14; // rdx
  CRectangleVisual **p_right; // rbx
  CVisual *v17; // rcx
  int v18; // eax
  unsigned int v19; // esi
  CSurfaceBrush *v20; // rsi
  int v21; // edi
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (struct tagRECT *)((char *)a2 + 24);
  SetRectEmpty((struct tagRECT *)((char *)a2 + 24));
  v5 = a2 + 4;
  SetRectEmpty(a2 + 4);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 58); i = (unsigned int)(i + 1) )
  {
    v7 = *(CLivePreview **)(*((_QWORD *)this + 26) + 40 * i);
    v8 = (const struct CTopLevelWindow *)*((_QWORD *)v7 + 55);
    if ( v8 )
      CLivePreview::_UpdateResourcesForMonitorHelper(v7, v8, (struct LivePreviewResource *)a2);
  }
  v9 = IsRectEmpty(v2);
  v10 = IsRectEmpty(a2 + 4);
  v11 = *(CVisual **)&a2->left;
  v12 = v10;
  if ( v9 )
  {
    if ( v11 )
    {
      CVisual::RemoveSelfFromParent(v11);
      wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(a2);
    }
  }
  else
  {
    if ( !v11 )
    {
      wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(a2);
      v13 = CSolidRectangleVisual::Create((struct CSolidRectangleVisual **)a2);
      if ( v13 < 0 )
      {
        v14 = 1151;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\livepreview.cpp",
          (const char *)(unsigned int)v13,
          v23);
        return (unsigned int)v13;
      }
    }
    CRectangleVisual::SetRect(*(CRectangleVisual **)&a2->left, v2);
    v13 = CVisualBrush::Reset((CVisualBrush *)&a2->right, *((struct CVisual **)this + 43), v2, 0);
    if ( v13 < 0 )
    {
      v14 = 1157;
      goto LABEL_9;
    }
    v13 = CSurfaceBrush::ApplyViewportTransformForView((CSurfaceBrush *)&a2->right, v2);
    if ( v13 < 0 )
    {
      v14 = 1158;
      goto LABEL_9;
    }
    v13 = CVisualBrush::FreezeImpl(&a2->right, 2);
    if ( v13 < 0 )
    {
      v14 = 1159;
      goto LABEL_9;
    }
    v13 = CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(
            *(_QWORD *)&a2->left,
            *(_QWORD *)&a2->right);
    if ( v13 < 0 )
    {
      v14 = 1160;
      goto LABEL_9;
    }
  }
  p_right = (CRectangleVisual **)&a2[2].right;
  v17 = *(CVisual **)&a2[2].right;
  if ( v12 )
  {
    if ( v17 )
    {
      CVisual::RemoveSelfFromParent(v17);
      wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(&a2[2].right);
    }
  }
  else
  {
    if ( !v17 )
    {
      wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(&a2[2].right);
      v18 = CSolidRectangleVisual::Create((struct CSolidRectangleVisual **)&a2[2].right);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x494,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\livepreview.cpp",
          (const char *)(unsigned int)v18,
          v23);
        return v19;
      }
    }
    CRectangleVisual::SetRect(*p_right, a2 + 4);
    v20 = (CSurfaceBrush *)&a2[3];
    v21 = CVisualBrush::Reset((CVisualBrush *)&a2[3], *((struct CVisual **)this + 45), a2 + 4, 0);
    if ( v21 < 0 )
    {
      v22 = 1178;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\livepreview.cpp",
        (const char *)(unsigned int)v21,
        v23);
      return (unsigned int)v21;
    }
    v21 = CSurfaceBrush::ApplyViewportTransformForView(v20, v5);
    if ( v21 < 0 )
    {
      v22 = 1179;
      goto LABEL_26;
    }
    v21 = CVisualBrush::FreezeImpl(v20, 2);
    if ( v21 < 0 )
    {
      v22 = 1180;
      goto LABEL_26;
    }
    v13 = CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(*p_right, *(_QWORD *)v20);
    if ( v13 < 0 )
    {
      v14 = 1181;
      goto LABEL_9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800bbd2c  push    rbx
0x1800bbd2e  push    rbp
0x1800bbd2f  push    rsi
0x1800bbd30  push    rdi
0x1800bbd31  push    r12
0x1800bbd33  push    r14
0x1800bbd35  push    r15; int
0x1800bbd37  sub     rsp, 20h
0x1800bbd3b  lea     rbp, [rdx+18h]
0x1800bbd3f  mov     r14, rcx
0x1800bbd42  mov     rcx, rbp; lprc
0x1800bbd45  mov     rdi, rdx
0x1800bbd48  call    cs:__imp_SetRectEmpty
0x1800bbd4e  lea     r15, [rdi+40h]
0x1800bbd52  mov     rcx, r15; lprc
0x1800bbd55  call    cs:__imp_SetRectEmpty
0x1800bbd5b  xor     ebx, ebx
0x1800bbd5d  cmp     [r14+0E8h], ebx
0x1800bbd64  jbe     short loc_1800BBD94
0x1800bbd66  mov     rax, [r14+0D0h]
0x1800bbd6d  lea     rcx, [rbx+rbx*4]
0x1800bbd71  mov     rcx, [rax+rcx*8]; this
0x1800bbd75  mov     rdx, [rcx+1B8h]; struct CTopLevelWindow *
0x1800bbd7c  test    rdx, rdx
0x1800bbd7f  jz      short loc_1800BBD89
0x1800bbd81  mov     r8, rdi; struct LivePreviewResource *
0x1800bbd84  call    ?_UpdateResourcesForMonitorHelper@CLivePreview@@AEAAXPEBVCTopLevelWindow@@PEAULivePreviewResource@@@Z; CLivePreview::_UpdateResourcesForMonitorHelper(CTopLevelWindow const *,LivePreviewResource *)
0x1800bbd89  inc     ebx
0x1800bbd8b  cmp     ebx, [r14+0E8h]
0x1800bbd92  jb      short loc_1800BBD66
0x1800bbd94  mov     rcx, rbp; lprc
0x1800bbd97  call    cs:__imp_IsRectEmpty
0x1800bbd9d  mov     rcx, r15; lprc
0x1800bbda0  mov     ebx, eax
0x1800bbda2  call    cs:__imp_IsRectEmpty
0x1800bbda8  mov     rcx, [rdi]; this
0x1800bbdab  mov     r12d, eax
0x1800bbdae  test    ebx, ebx
0x1800bbdb0  jnz     loc_1800BBE6F
0x1800bbdb6  test    rcx, rcx
0x1800bbdb9  jnz     short loc_1800BBDF1
0x1800bbdbb  mov     rcx, rdi
0x1800bbdbe  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x1800bbdc3  mov     rcx, rdi; struct CSolidRectangleVisual **
0x1800bbdc6  call    ?Create@CSolidRectangleVisual@@SAJPEAPEAV1@@Z; CSolidRectangleVisual::Create(CSolidRectangleVisual * *)
0x1800bbdcb  mov     ebx, eax
0x1800bbdcd  test    eax, eax
0x1800bbdcf  jns     short loc_1800BBDF1
0x1800bbdd1  mov     edx, 47Fh; void *
0x1800bbdd6  mov     rcx, [rsp+58h]; this
0x1800bbddb  lea     r8, aClientcoreWind_26; "clientcore\\windows\\dwm\\udwm\\livepre"...
0x1800bbde2  mov     r9d, ebx; char *
0x1800bbde5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbdea  mov     eax, ebx
0x1800bbdec  jmp     loc_1800BBF74
0x1800bbdf1  mov     rcx, [rdi]; this
0x1800bbdf4  mov     rdx, rbp; struct tagRECT *
0x1800bbdf7  call    ?SetRect@CRectangleVisual@@QEAAXAEBUtagRECT@@@Z; CRectangleVisual::SetRect(tagRECT const &)
0x1800bbdfc  mov     rdx, [r14+158h]; struct CVisual *
0x1800bbe03  lea     rsi, [rdi+8]
0x1800bbe07  mov     rcx, rsi; this
0x1800bbe0a  xor     r9d, r9d; struct D2D_SIZE_F *
0x1800bbe0d  mov     r8, rbp; struct tagRECT *
0x1800bbe10  call    ?Reset@CVisualBrush@@QEAAJPEAVCVisual@@AEBUtagRECT@@PEBUD2D_SIZE_F@@@Z; CVisualBrush::Reset(CVisual *,tagRECT const &,D2D_SIZE_F const *)
0x1800bbe15  mov     ebx, eax
0x1800bbe17  test    eax, eax
0x1800bbe19  jns     short loc_1800BBE22
0x1800bbe1b  mov     edx, 485h
0x1800bbe20  jmp     short loc_1800BBDD6
0x1800bbe22  mov     rdx, rbp; struct tagRECT *
0x1800bbe25  mov     rcx, rsi; this
0x1800bbe28  call    ?ApplyViewportTransformForView@CSurfaceBrush@@QEAAJAEBUtagRECT@@@Z; CSurfaceBrush::ApplyViewportTransformForView(tagRECT const &)
0x1800bbe2d  mov     ebx, eax
0x1800bbe2f  test    eax, eax
0x1800bbe31  jns     short loc_1800BBE3A
0x1800bbe33  mov     edx, 486h
0x1800bbe38  jmp     short loc_1800BBDD6
0x1800bbe3a  mov     edx, 2
0x1800bbe3f  mov     rcx, rsi
0x1800bbe42  call    ?FreezeImpl@CVisualBrush@@AEAAJW4VisualSurfaceFreezeBehavior@Internal@Composition@UI@Windows@@@Z; CVisualBrush::FreezeImpl(Windows::UI::Composition::Internal::VisualSurfaceFreezeBehavior)
0x1800bbe47  mov     ebx, eax
0x1800bbe49  test    eax, eax
0x1800bbe4b  jns     short loc_1800BBE54
0x1800bbe4d  mov     edx, 487h
0x1800bbe52  jmp     short loc_1800BBDD6
0x1800bbe54  mov     rdx, [rsi]
0x1800bbe57  mov     rcx, [rdi]
0x1800bbe5a  call    ??$SetBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CSpriteVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x1800bbe5f  mov     ebx, eax
0x1800bbe61  test    eax, eax
0x1800bbe63  jns     short loc_1800BBE81
0x1800bbe65  mov     edx, 488h
0x1800bbe6a  jmp     loc_1800BBDD6
0x1800bbe6f  test    rcx, rcx
0x1800bbe72  jz      short loc_1800BBE81
0x1800bbe74  call    ?RemoveSelfFromParent@CVisual@@QEAAJXZ; CVisual::RemoveSelfFromParent(void)
0x1800bbe79  mov     rcx, rdi
0x1800bbe7c  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x1800bbe81  lea     rbx, [rdi+28h]
0x1800bbe85  mov     rcx, [rbx]; this
0x1800bbe88  test    r12d, r12d
0x1800bbe8b  jnz     loc_1800BBF60
0x1800bbe91  test    rcx, rcx
0x1800bbe94  jnz     short loc_1800BBECC
0x1800bbe96  mov     rcx, rbx
0x1800bbe99  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x1800bbe9e  mov     rcx, rbx; struct CSolidRectangleVisual **
0x1800bbea1  call    ?Create@CSolidRectangleVisual@@SAJPEAPEAV1@@Z; CSolidRectangleVisual::Create(CSolidRectangleVisual * *)
0x1800bbea6  mov     esi, eax
0x1800bbea8  test    eax, eax
0x1800bbeaa  jns     short loc_1800BBECC
0x1800bbeac  mov     rcx, [rsp+58h]; this
0x1800bbeb1  lea     r8, aClientcoreWind_26; "clientcore\\windows\\dwm\\udwm\\livepre"...
0x1800bbeb8  mov     r9d, eax; char *
0x1800bbebb  mov     edx, 494h; void *
0x1800bbec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbec5  mov     eax, esi
0x1800bbec7  jmp     loc_1800BBF74
0x1800bbecc  mov     rcx, [rbx]; this
0x1800bbecf  mov     rdx, r15; struct tagRECT *
0x1800bbed2  call    ?SetRect@CRectangleVisual@@QEAAXAEBUtagRECT@@@Z; CRectangleVisual::SetRect(tagRECT const &)
0x1800bbed7  mov     rdx, [r14+168h]; struct CVisual *
0x1800bbede  lea     rsi, [rdi+30h]
0x1800bbee2  mov     rcx, rsi; this
0x1800bbee5  xor     r9d, r9d; struct D2D_SIZE_F *
0x1800bbee8  mov     r8, r15; struct tagRECT *
0x1800bbeeb  call    ?Reset@CVisualBrush@@QEAAJPEAVCVisual@@AEBUtagRECT@@PEBUD2D_SIZE_F@@@Z; CVisualBrush::Reset(CVisual *,tagRECT const &,D2D_SIZE_F const *)
0x1800bbef0  mov     edi, eax
0x1800bbef2  test    eax, eax
0x1800bbef4  jns     short loc_1800BBF13
0x1800bbef6  mov     edx, 49Ah; void *
0x1800bbefb  mov     rcx, [rsp+58h]; this
0x1800bbf00  lea     r8, aClientcoreWind_26; "clientcore\\windows\\dwm\\udwm\\livepre"...
0x1800bbf07  mov     r9d, edi; char *
0x1800bbf0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbf0f  mov     eax, edi
0x1800bbf11  jmp     short loc_1800BBF74
0x1800bbf13  mov     rdx, r15; struct tagRECT *
0x1800bbf16  mov     rcx, rsi; this
0x1800bbf19  call    ?ApplyViewportTransformForView@CSurfaceBrush@@QEAAJAEBUtagRECT@@@Z; CSurfaceBrush::ApplyViewportTransformForView(tagRECT const &)
0x1800bbf1e  mov     edi, eax
0x1800bbf20  test    eax, eax
0x1800bbf22  jns     short loc_1800BBF2B
0x1800bbf24  mov     edx, 49Bh
0x1800bbf29  jmp     short loc_1800BBEFB
0x1800bbf2b  mov     edx, 2
0x1800bbf30  mov     rcx, rsi
0x1800bbf33  call    ?FreezeImpl@CVisualBrush@@AEAAJW4VisualSurfaceFreezeBehavior@Internal@Composition@UI@Windows@@@Z; CVisualBrush::FreezeImpl(Windows::UI::Composition::Internal::VisualSurfaceFreezeBehavior)
0x1800bbf38  mov     edi, eax
0x1800bbf3a  test    eax, eax
0x1800bbf3c  jns     short loc_1800BBF45
0x1800bbf3e  mov     edx, 49Ch
0x1800bbf43  jmp     short loc_1800BBEFB
0x1800bbf45  mov     rdx, [rsi]
0x1800bbf48  mov     rcx, [rbx]
0x1800bbf4b  call    ??$SetBrush@PEAUICompositionColorBrush@Composition@UI@Windows@@@CSpriteVisual@@QEAAJPEAUICompositionColorBrush@Composition@UI@Windows@@@Z; CSpriteVisual::SetBrush<Windows::UI::Composition::ICompositionColorBrush *>(Windows::UI::Composition::ICompositionColorBrush *)
0x1800bbf50  mov     ebx, eax
0x1800bbf52  test    eax, eax
0x1800bbf54  jns     short loc_1800BBF72
0x1800bbf56  mov     edx, 49Dh
0x1800bbf5b  jmp     loc_1800BBDD6
0x1800bbf60  test    rcx, rcx
0x1800bbf63  jz      short loc_1800BBF72
0x1800bbf65  call    ?RemoveSelfFromParent@CVisual@@QEAAJXZ; CVisual::RemoveSelfFromParent(void)
0x1800bbf6a  mov     rcx, rbx
0x1800bbf6d  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x1800bbf72  xor     eax, eax
0x1800bbf74  add     rsp, 20h
0x1800bbf78  pop     r15
0x1800bbf7a  pop     r14
0x1800bbf7c  pop     r12
0x1800bbf7e  pop     rdi
0x1800bbf7f  pop     rsi
0x1800bbf80  pop     rbp
0x1800bbf81  pop     rbx
0x1800bbf82  retn
```
