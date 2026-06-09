# SlideshowUserInterface::OnContextMenu(HWND__ *,tagPOINT)

- ea: `0x180064a90`
- end: `0x18006500f`
- name: `?OnContextMenu@SlideshowUserInterface@@UEAAJPEAUHWND__@@UtagPOINT@@@Z`
- size: `1407`
- prototype: `int(SlideshowUserInterface *__hidden this, HWND, struct tagPOINT)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180003b20`
- `0x180004908`
- `0x180026724`
- `0x180035650`
- `0x18003f800`
- `0x180062e6c`
- `0x1800643c0`
- `0x180064a90`
- `0x180080010`

## import_xrefs

- `USER32!TrackPopupMenuEx` at `0x180064dd0`
- `USER32!TrackPopupMenuEx` at `0x180064dd0`
- `USER32!CreatePopupMenu` at `0x180064b7d`
- `USER32!CreatePopupMenu` at `0x180064b7d`
- `USER32!PtInRect` at `0x180064b49`
- `USER32!PtInRect` at `0x180064b49`
- `USER32!GetMessagePos` at `0x180064b0e`
- `USER32!GetMessagePos` at `0x180064b0e`
- `USER32!SendMessageW` at `0x180064dab`
- `USER32!SendMessageW` at `0x180064dab`
- `USER32!GetWindowRect` at `0x180064b35`
- `USER32!GetWindowRect` at `0x180064b35`
- `USER32!InvalidateRect` at `0x180064fbb`
- `USER32!InvalidateRect` at `0x180064fbb`
- `USER32!UpdateWindow` at `0x180064fc4`
- `USER32!UpdateWindow` at `0x180064fc4`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180064d4d`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180064d4d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e39`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e60`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e87`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064eae`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064ed5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064efc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f39`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f5c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f7f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064fa2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e39`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e60`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064e87`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064eae`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064ed5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064efc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f39`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f5c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064f7f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180064fa2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SlideshowUserInterface::OnContextMenu(SlideshowUserInterface *this, HWND a2, struct tagPOINT a3)
{
  LONG x; // ebx
  LONG y; // esi
  SlideshowUserInterface *v7; // r13
  DWORD MessagePos; // eax
  HMENU PopupMenu; // rax
  HMENU v11; // r14
  __int64 BaseStringManager; // rdx
  unsigned int v13; // r9d
  HWND Tooltip; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  int v24; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // edx
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax
  int v36; // edx
  int v37; // eax
  int v38; // edx
  int v39; // eax
  int v40; // edx
  int v41; // eax
  int v42; // edx
  SlideshowUserInterface *v43; // rbx
  const unsigned __int16 *lptpm; // [rsp+28h] [rbp-90h]
  bool v45; // [rsp+38h] [rbp-80h]
  bool v46; // [rsp+38h] [rbp-80h]
  bool v47; // [rsp+38h] [rbp-80h]
  bool v48; // [rsp+38h] [rbp-80h]
  bool v49; // [rsp+38h] [rbp-80h]
  bool v50; // [rsp+38h] [rbp-80h]
  bool v51; // [rsp+38h] [rbp-80h]
  bool v52; // [rsp+38h] [rbp-80h]
  bool v53; // [rsp+38h] [rbp-80h]
  bool v54; // [rsp+38h] [rbp-80h]
  POINT pt; // [rsp+40h] [rbp-78h] BYREF
  SlideshowUserInterface *v56; // [rsp+48h] [rbp-70h]
  _BYTE v57[16]; // [rsp+50h] [rbp-68h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-58h] BYREF

  x = a3.x;
  v56 = this;
  y = a3.y;
  v7 = (SlideshowUserInterface *)((char *)this - 32);
  if ( !*((_BYTE *)this + 32) )
    return 2147500037LL;
  if ( !*((_QWORD *)this + 21) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 80LL))(*((_QWORD *)this + 12));
    pt.x = x;
    pt.y = y;
    if ( x == -1 && y == -1 )
    {
      MessagePos = GetMessagePos();
      x = (__int16)MessagePos;
      pt.x = (__int16)MessagePos;
      MessagePos >>= 16;
      y = (__int16)MessagePos;
      pt.y = (__int16)MessagePos;
    }
    Rect = 0;
    if ( GetWindowRect(a2, &Rect) && !PtInRect(&Rect, pt) )
    {
      x = (Rect.right + Rect.left) / 2;
      y = (Rect.top + Rect.bottom) / 2;
    }
    PopupMenu = CreatePopupMenu();
    v11 = PopupMenu;
    *(_QWORD *)&Rect.left = PopupMenu;
    if ( !PopupMenu )
      goto LABEL_48;
    SlideshowUserInterface::InsertMenuItemW(v7, PopupMenu, 0xBB8u, 0xA028u, 0, *((_BYTE *)this + 128), 0, v45);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBB9u, 0xA029u, 0, *((_BYTE *)this + 129), 0, v46);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBBAu, 0xA02Au, 0, *((_BYTE *)this + 130), 0, v47);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBBBu, 0xA02Bu, 0, *((_BYTE *)this + 131), 0, v48);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBC7u, 0xA224u, *((_BYTE *)this + 132), 1, 1, v49);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBCCu, 0xA228u, *((_BYTE *)this + 133), 1, 0, v50);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBC8u, 0xA225u, *((_DWORD *)this + 34) == 0, 1, 1, v51);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBC9u, 0xA226u, *((_DWORD *)this + 34) == 1, 1, 0, v52);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBCAu, 0xA227u, *((_DWORD *)this + 34) == 2, 1, 0, v53);
    SlideshowUserInterface::InsertMenuItemW(v7, v11, 0xBBCu, 0xA02Cu, 0, 1, 1, v54);
    try
    {
      BaseStringManager = Base::String::GetBaseStringManager();
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&pt, BaseStringManager);
      ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        &pt,
        3006);
      Tooltip = UIBase::CreateTooltip(a2, (HWND)0x43, 0x120u, v13, *(_QWORD *)&pt, lptpm);
      *((_QWORD *)this + 23) = Tooltip;
      if ( Tooltip )
        SendMessageW(Tooltip, 0x418u, 0, 400);
      *((_BYTE *)this + 135) = 1;
      v15 = TrackPopupMenuEx(v11, 0x102u, x, y, a2, 0);
      if ( !v15 )
        goto LABEL_47;
      if ( v15 <= 0xA224 )
      {
        if ( v15 != 41508 )
        {
          v16 = v15 - 41000;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( v18 )
              {
                v19 = v18 - 1;
                if ( v19 )
                {
                  if ( v19 != 1 )
                    goto LABEL_47;
                  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                          *((_QWORD *)this + 13),
                          30);
                  if ( v20 >= 0 )
                    goto LABEL_47;
                  Base::Throw((Base *)(unsigned int)v20, v21);
                }
                v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                        *((_QWORD *)this + 13),
                        29);
                if ( v22 >= 0 )
                  goto LABEL_47;
                Base::Throw((Base *)(unsigned int)v22, v23);
              }
              v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                      *((_QWORD *)this + 13),
                      28);
              if ( v24 >= 0 )
                goto LABEL_47;
              Base::Throw((Base *)(unsigned int)v24, v25);
            }
            v26 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                    *((_QWORD *)this + 13),
                    27);
            if ( v26 >= 0 )
              goto LABEL_47;
            Base::Throw((Base *)(unsigned int)v26, v27);
          }
          v28 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                  *((_QWORD *)this + 13),
                  26);
          if ( v28 >= 0 )
            goto LABEL_47;
          Base::Throw((Base *)(unsigned int)v28, v29);
        }
        v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(*((_QWORD *)this + 13), 31);
        if ( v30 >= 0 )
          goto LABEL_47;
        Base::Throw((Base *)(unsigned int)v30, v31);
      }
      v32 = v15 - 41509;
      if ( !v32 )
        goto LABEL_45;
      v33 = v32 - 1;
      if ( !v33 )
        goto LABEL_43;
      v34 = v33 - 1;
      if ( v34 )
      {
        if ( v34 != 1 )
          goto LABEL_47;
        v35 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(*((_QWORD *)this + 13), 38);
        if ( v35 >= 0 )
          goto LABEL_47;
        Base::Throw((Base *)(unsigned int)v35, v36);
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(*((_QWORD *)this + 13), 37);
      if ( v37 < 0 )
      {
        Base::Throw((Base *)(unsigned int)v37, v38);
LABEL_43:
        v39 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(*((_QWORD *)this + 13), 36);
        if ( v39 < 0 )
        {
          Base::Throw((Base *)(unsigned int)v39, v40);
LABEL_45:
          v41 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 56LL))(
                  *((_QWORD *)this + 13),
                  35);
          if ( v41 < 0 )
            Base::Throw((Base *)(unsigned int)v41, v42);
        }
      }
LABEL_47:
      SlideshowUserInterface::CleanUpContextMenuAndToolTip(v7, v11);
      InvalidateRect(a2, 0, 0);
      UpdateWindow(a2);
      Base::String::~String((Base::String *)&pt);
    }
    catch ( Base::Exception v57 )
    {
      v43 = v56;
      if ( *(_QWORD *)&Rect.left )
        SlideshowUserInterface::CleanUpContextMenuAndToolTip(
          (SlideshowUserInterface *)((char *)v56 - 32),
          *(HMENU *)&Rect.left);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v43 + 12) + 88LL))(*((_QWORD *)v43 + 12));
      pt.x = Base::Exception::operator long(v57);
      Base::Exception::~Exception((Base::Exception *)v57);
      return (unsigned int)pt.x;
    }
LABEL_48:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 88LL))(*((_QWORD *)this + 12));
  }
  return 0;
}

```

## disassembly

```asm
0x180064a90  push    rbx
0x180064a92  push    rsi
0x180064a93  push    rdi
0x180064a94  push    r12
0x180064a96  push    r13
0x180064a98  push    r14
0x180064a9a  push    r15
0x180064a9c  sub     rsp, 80h
0x180064aa3  mov     rax, cs:__security_cookie
0x180064aaa  xor     rax, rsp
0x180064aad  mov     [rsp+0B8h+var_48], rax
0x180064ab2  mov     rbx, r8
0x180064ab5  mov     r15, rdx
0x180064ab8  mov     rdi, rcx
0x180064abb  mov     [rsp+0B8h+var_70], rcx
0x180064ac0  mov     rsi, r8
0x180064ac3  shr     rsi, 20h
0x180064ac7  lea     r13, [rcx-20h]
0x180064acb  cmp     byte ptr [r13+40h], 0
0x180064ad0  jnz     short loc_180064ADC
0x180064ad2  mov     eax, 80004005h
0x180064ad7  jmp     loc_180064FEF
0x180064adc  cmp     qword ptr [rcx+0A8h], 0
0x180064ae4  jz      short loc_180064AED
0x180064ae6  xor     eax, eax
0x180064ae8  jmp     loc_180064FEF
0x180064aed  mov     rcx, [rcx+60h]
0x180064af1  mov     rax, [rcx]
0x180064af4  mov     rax, [rax+50h]
0x180064af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064afd  mov     [rsp+0B8h+pt.x], ebx
0x180064b01  mov     [rsp+0B8h+pt.y], esi
0x180064b05  cmp     ebx, 0FFFFFFFFh
0x180064b08  jnz     short loc_180064B25
0x180064b0a  cmp     esi, ebx
0x180064b0c  jnz     short loc_180064B25
0x180064b0e  call    cs:__imp_GetMessagePos
0x180064b14  movsx   ebx, ax
0x180064b17  mov     [rsp+0B8h+pt.x], ebx
0x180064b1b  shr     eax, 10h
0x180064b1e  movsx   esi, ax
0x180064b21  mov     [rsp+0B8h+pt.y], esi
0x180064b25  xorps   xmm0, xmm0
0x180064b28  movups  xmmword ptr [rsp+0B8h+Rect.left], xmm0
0x180064b2d  lea     rdx, [rsp+0B8h+Rect]; lpRect
0x180064b32  mov     rcx, r15; hWnd
0x180064b35  call    cs:__imp_GetWindowRect
0x180064b3b  test    eax, eax
0x180064b3d  jz      short loc_180064B77
0x180064b3f  mov     rdx, qword ptr [rsp+0B8h+pt.x]; pt
0x180064b44  lea     rcx, [rsp+0B8h+Rect]; lprc
0x180064b49  call    cs:__imp_PtInRect
0x180064b4f  test    eax, eax
0x180064b51  jnz     short loc_180064B77
0x180064b53  mov     eax, [rsp+0B8h+Rect.left]
0x180064b57  add     eax, [rsp+0B8h+Rect.right]
0x180064b5b  cdq
0x180064b5c  mov     r12d, 2
0x180064b62  idiv    r12d
0x180064b65  mov     ebx, eax
0x180064b67  mov     eax, [rsp+0B8h+Rect.bottom]
0x180064b6b  add     eax, [rsp+0B8h+Rect.top]
0x180064b6f  cdq
0x180064b70  idiv    r12d
0x180064b73  mov     esi, eax
0x180064b75  jmp     short loc_180064B7D
0x180064b77  mov     r12d, 2
0x180064b7d  call    cs:__imp_CreatePopupMenu
0x180064b83  mov     r14, rax
0x180064b86  mov     qword ptr [rsp+0B8h+Rect.left], rax
0x180064b8b  test    rax, rax
0x180064b8e  jz      loc_180064FD6
0x180064b94  mov     [rsp+0B8h+var_88], 0; bool
0x180064b99  mov     cl, [rdi+80h]
0x180064b9f  mov     byte ptr [rsp+0B8h+lptpm], cl; bool
0x180064ba3  mov     byte ptr [rsp+0B8h+hwnd], 0; bool
0x180064ba8  mov     r9d, 0A028h; unsigned int
0x180064bae  mov     r8d, 0BB8h; unsigned int
0x180064bb4  mov     rdx, rax; HMENU
0x180064bb7  mov     rcx, r13; this
0x180064bba  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064bbf  mov     [rsp+0B8h+var_88], 0; bool
0x180064bc4  mov     al, [rdi+81h]
0x180064bca  mov     byte ptr [rsp+0B8h+lptpm], al; bool
0x180064bce  mov     byte ptr [rsp+0B8h+hwnd], 0; bool
0x180064bd3  mov     r9d, 0A029h; unsigned int
0x180064bd9  mov     r8d, 0BB9h; unsigned int
0x180064bdf  mov     rdx, r14; HMENU
0x180064be2  mov     rcx, r13; this
0x180064be5  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064bea  mov     [rsp+0B8h+var_88], 0; bool
0x180064bef  mov     al, [rdi+82h]
0x180064bf5  mov     byte ptr [rsp+0B8h+lptpm], al; bool
0x180064bf9  mov     byte ptr [rsp+0B8h+hwnd], 0; bool
0x180064bfe  mov     r9d, 0A02Ah; unsigned int
0x180064c04  mov     r8d, 0BBAh; unsigned int
0x180064c0a  mov     rdx, r14; HMENU
0x180064c0d  mov     rcx, r13; this
0x180064c10  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064c15  mov     [rsp+0B8h+var_88], 0; bool
0x180064c1a  mov     al, [rdi+83h]
0x180064c20  mov     byte ptr [rsp+0B8h+lptpm], al; bool
0x180064c24  mov     byte ptr [rsp+0B8h+hwnd], 0; bool
0x180064c29  mov     r9d, 0A02Bh; unsigned int
0x180064c2f  mov     r8d, 0BBBh; unsigned int
0x180064c35  mov     rdx, r14; HMENU
0x180064c38  mov     rcx, r13; this
0x180064c3b  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064c40  mov     [rsp+0B8h+var_88], 1; bool
0x180064c45  mov     byte ptr [rsp+0B8h+lptpm], 1; bool
0x180064c4a  mov     al, [rdi+84h]
0x180064c50  mov     byte ptr [rsp+0B8h+hwnd], al; bool
0x180064c54  mov     r9d, 0A224h; unsigned int
0x180064c5a  mov     r8d, 0BC7h; unsigned int
0x180064c60  mov     rdx, r14; HMENU
0x180064c63  mov     rcx, r13; this
0x180064c66  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064c6b  mov     [rsp+0B8h+var_88], 0; bool
0x180064c70  mov     byte ptr [rsp+0B8h+lptpm], 1; bool
0x180064c75  mov     al, [rdi+85h]
0x180064c7b  mov     byte ptr [rsp+0B8h+hwnd], al; bool
0x180064c7f  mov     r9d, 0A228h; unsigned int
0x180064c85  mov     r8d, 0BCCh; unsigned int
0x180064c8b  mov     rdx, r14; HMENU
0x180064c8e  mov     rcx, r13; this
0x180064c91  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064c96  cmp     dword ptr [rdi+88h], 0
0x180064c9d  setz    al
0x180064ca0  mov     [rsp+0B8h+var_88], 1; bool
0x180064ca5  mov     byte ptr [rsp+0B8h+lptpm], 1; bool
0x180064caa  mov     byte ptr [rsp+0B8h+hwnd], al; bool
0x180064cae  mov     r9d, 0A225h; unsigned int
0x180064cb4  mov     r8d, 0BC8h; unsigned int
0x180064cba  mov     rdx, r14; HMENU
0x180064cbd  mov     rcx, r13; this
0x180064cc0  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064cc5  cmp     dword ptr [rdi+88h], 1
0x180064ccc  setz    al
0x180064ccf  mov     [rsp+0B8h+var_88], 0; bool
0x180064cd4  mov     byte ptr [rsp+0B8h+lptpm], 1; bool
0x180064cd9  mov     byte ptr [rsp+0B8h+hwnd], al; bool
0x180064cdd  mov     r9d, 0A226h; unsigned int
0x180064ce3  mov     r8d, 0BC9h; unsigned int
0x180064ce9  mov     rdx, r14; HMENU
0x180064cec  mov     rcx, r13; this
0x180064cef  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064cf4  cmp     [rdi+88h], r12d
0x180064cfb  setz    al
0x180064cfe  xor     r12d, r12d
0x180064d01  mov     [rsp+0B8h+var_88], r12b; bool
0x180064d06  mov     byte ptr [rsp+0B8h+lptpm], 1; bool
0x180064d0b  mov     byte ptr [rsp+0B8h+hwnd], al; bool
0x180064d0f  mov     r9d, 0A227h; unsigned int
0x180064d15  mov     r8d, 0BCAh; unsigned int
0x180064d1b  mov     rdx, r14; HMENU
0x180064d1e  mov     rcx, r13; this
0x180064d21  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064d26  mov     [rsp+0B8h+var_88], 1; bool
0x180064d2b  mov     byte ptr [rsp+0B8h+lptpm], 1; unsigned __int16 *
0x180064d30  mov     byte ptr [rsp+0B8h+hwnd], r12b; bool
0x180064d35  mov     r9d, 0A02Ch; unsigned int
0x180064d3b  mov     r8d, 0BBCh; unsigned int
0x180064d41  mov     rdx, r14; HMENU
0x180064d44  mov     rcx, r13; this
0x180064d47  call    ?InsertMenuItemW@SlideshowUserInterface@@AEAAXPEAUHMENU__@@II_N111@Z; SlideshowUserInterface::InsertMenuItemW(HMENU__ *,uint,uint,bool,bool,bool,bool)
0x180064d4c  nop
0x180064d4d  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x180064d53  nop
0x180064d54  mov     rdx, rax
0x180064d57  lea     rcx, [rsp+0B8h+pt]
0x180064d5c  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180064d61  nop
0x180064d62  mov     edx, 0BBEh
0x180064d67  lea     rcx, [rsp+0B8h+pt]
0x180064d6c  call    ?LoadStringW@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180064d71  mov     rax, qword ptr [rsp+0B8h+pt.x]
0x180064d76  mov     [rsp+0B8h+hwnd], rax; unsigned __int64
0x180064d7b  lea     edx, [r12+43h]; HWND
0x180064d80  mov     r8d, 120h; unsigned int
0x180064d86  mov     rcx, r15; this
0x180064d89  call    ?CreateTooltip@UIBase@@YAPEAUHWND__@@PEAU2@KI_KPEBG@Z; UIBase::CreateTooltip(HWND__ *,ulong,uint,unsigned __int64,ushort const *)
0x180064d8e  mov     [rdi+0B8h], rax
0x180064d95  test    rax, rax
0x180064d98  jz      short loc_180064DB1
0x180064d9a  mov     r9d, 190h; lParam
0x180064da0  xor     r8d, r8d; wParam
0x180064da3  mov     edx, 418h; Msg
0x180064da8  mov     rcx, rax; hWnd
0x180064dab  call    cs:__imp_SendMessageW
0x180064db1  mov     byte ptr [rdi+87h], 1
0x180064db8  mov     [rsp+0B8h+lptpm], r12; lptpm
0x180064dbd  mov     [rsp+0B8h+hwnd], r15; hwnd
0x180064dc2  mov     r9d, esi; y
0x180064dc5  mov     r8d, ebx; x
0x180064dc8  mov     edx, 102h; uFlags
0x180064dcd  mov     rcx, r14; hMenu
0x180064dd0  call    cs:__imp_TrackPopupMenuEx
0x180064dd6  test    eax, eax
0x180064dd8  jz      loc_180064FA8
0x180064dde  mov     ecx, 0A224h
0x180064de3  cmp     eax, ecx
0x180064de5  ja      loc_180064F02
0x180064deb  jz      loc_180064EDB
0x180064df1  sub     eax, 0A028h
0x180064df6  jz      loc_180064EB4
0x180064dfc  sub     eax, 1
0x180064dff  jz      loc_180064E8D
0x180064e05  sub     eax, 1
0x180064e08  jz      short loc_180064E66
0x180064e0a  sub     eax, 1
0x180064e0d  jz      short loc_180064E3F
0x180064e0f  cmp     eax, 1
0x180064e12  jnz     loc_180064FA8
0x180064e18  mov     rcx, [rdi+68h]
0x180064e1c  mov     rax, [rcx]
0x180064e1f  xor     r8d, r8d
0x180064e22  lea     edx, [r8+1Eh]
0x180064e26  mov     rax, [rax+38h]
0x180064e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e2f  test    eax, eax
0x180064e31  jns     loc_180064FA8
0x180064e37  mov     ecx, eax
0x180064e39  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064e3f  mov     rcx, [rdi+68h]
0x180064e43  mov     rax, [rcx]
0x180064e46  xor     r8d, r8d
0x180064e49  lea     edx, [r8+1Dh]
0x180064e4d  mov     rax, [rax+38h]
0x180064e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e56  test    eax, eax
0x180064e58  jns     loc_180064FA8
0x180064e5e  mov     ecx, eax
0x180064e60  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064e66  mov     rcx, [rdi+68h]
0x180064e6a  mov     rax, [rcx]
0x180064e6d  xor     r8d, r8d
0x180064e70  lea     edx, [r8+1Ch]
0x180064e74  mov     rax, [rax+38h]
0x180064e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e7d  test    eax, eax
0x180064e7f  jns     loc_180064FA8
0x180064e85  mov     ecx, eax
0x180064e87  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064e8d  mov     rcx, [rdi+68h]
0x180064e91  mov     rax, [rcx]
0x180064e94  xor     r8d, r8d
0x180064e97  lea     edx, [r8+1Bh]
0x180064e9b  mov     rax, [rax+38h]
0x180064e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ea4  test    eax, eax
0x180064ea6  jns     loc_180064FA8
0x180064eac  mov     ecx, eax
0x180064eae  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064eb4  mov     rcx, [rdi+68h]
0x180064eb8  mov     rax, [rcx]
0x180064ebb  xor     r8d, r8d
0x180064ebe  lea     edx, [r8+1Ah]
0x180064ec2  mov     rax, [rax+38h]
0x180064ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ecb  test    eax, eax
0x180064ecd  jns     loc_180064FA8
0x180064ed3  mov     ecx, eax
0x180064ed5  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064edb  mov     rcx, [rdi+68h]
0x180064edf  mov     rax, [rcx]
0x180064ee2  xor     r8d, r8d
0x180064ee5  lea     edx, [r8+1Fh]
0x180064ee9  mov     rax, [rax+38h]
0x180064eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ef2  test    eax, eax
0x180064ef4  jns     loc_180064FA8
0x180064efa  mov     ecx, eax
0x180064efc  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064f02  sub     eax, 0A225h
0x180064f07  jz      short loc_180064F85
0x180064f09  sub     eax, 1
0x180064f0c  jz      short loc_180064F62
0x180064f0e  sub     eax, 1
0x180064f11  jz      short loc_180064F3F
0x180064f13  cmp     eax, 1
0x180064f16  jnz     loc_180064FA8
0x180064f1c  mov     rcx, [rdi+68h]
0x180064f20  mov     rax, [rcx]
0x180064f23  xor     r8d, r8d
0x180064f26  lea     edx, [r8+26h]
0x180064f2a  mov     rax, [rax+38h]
0x180064f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f33  test    eax, eax
0x180064f35  jns     short loc_180064FA8
0x180064f37  mov     ecx, eax
0x180064f39  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180064f3f  mov     rcx, [rdi+68h]
0x180064f43  mov     rax, [rcx]
0x180064f46  xor     r8d, r8d
0x180064f49  lea     edx, [r8+25h]
0x180064f4d  mov     rax, [rax+38h]
0x180064f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f56  test    eax, eax
0x180064f58  jns     short loc_180064FA8
0x180064f5a  mov     ecx, eax
  ... truncated ...
```
