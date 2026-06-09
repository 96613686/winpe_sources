# CInkOverlay::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x1800dc3d8`
- end: `0x1800dc75b`
- name: `?OnPaint@CInkOverlay@@QEAA_JI_K_JAEAH@Z`
- size: `899`
- prototype: `__int64 __usercall@<rax>(CInkOverlay *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ca60`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x1800dc3d8`
- `0x1800df4d8`
- `0x1800e0ab0`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800dc4fc`
- `USER32!IsRectEmpty` at `0x1800dc4fc`
- `USER32!GetUpdateRgn` at `0x1800dc4de`
- `USER32!GetUpdateRgn` at `0x1800dc4de`
- `USER32!RedrawWindow` at `0x1800dc6e8`
- `USER32!RedrawWindow` at `0x1800dc6e8`
- `USER32!CallWindowProcW` at `0x1800dc5b4`
- `USER32!CallWindowProcW` at `0x1800dc5b4`
- `USER32!GetDC` at `0x1800dc43f`
- `USER32!GetDC` at `0x1800dc5cb`
- `USER32!GetDC` at `0x1800dc43f`
- `USER32!GetDC` at `0x1800dc5cb`
- `USER32!ReleaseDC` at `0x1800dc569`
- `USER32!ReleaseDC` at `0x1800dc6d5`
- `USER32!ReleaseDC` at `0x1800dc569`
- `USER32!ReleaseDC` at `0x1800dc6d5`
- `USER32!MapWindowPoints` at `0x1800dc65d`
- `USER32!MapWindowPoints` at `0x1800dc65d`
- `GDI32!SetMapMode` at `0x1800dc460`
- `GDI32!SetMapMode` at `0x1800dc460`
- `GDI32!OffsetRgn` at `0x1800dc66f`
- `GDI32!OffsetRgn` at `0x1800dc66f`
- `GDI32!GetRandomRgn` at `0x1800dc4b1`
- `GDI32!GetRandomRgn` at `0x1800dc623`
- `GDI32!GetRandomRgn` at `0x1800dc4b1`
- `GDI32!GetRandomRgn` at `0x1800dc623`
- `GDI32!CombineRgn` at `0x1800dc542`
- `GDI32!CombineRgn` at `0x1800dc638`
- `GDI32!CombineRgn` at `0x1800dc684`
- `GDI32!CombineRgn` at `0x1800dc69e`
- `GDI32!CombineRgn` at `0x1800dc542`
- `GDI32!CombineRgn` at `0x1800dc638`
- `GDI32!CombineRgn` at `0x1800dc684`
- `GDI32!CombineRgn` at `0x1800dc69e`
- `GDI32!SelectClipRgn` at `0x1800dc6aa`
- `GDI32!SelectClipRgn` at `0x1800dc6aa`
- `GDI32!CreateRectRgn` at `0x1800dc492`
- `GDI32!CreateRectRgn` at `0x1800dc4c1`
- `GDI32!CreateRectRgn` at `0x1800dc520`
- `GDI32!CreateRectRgn` at `0x1800dc5ee`
- `GDI32!CreateRectRgn` at `0x1800dc492`
- `GDI32!CreateRectRgn` at `0x1800dc4c1`
- `GDI32!CreateRectRgn` at `0x1800dc520`
- `GDI32!CreateRectRgn` at `0x1800dc5ee`
- `GDI32!RestoreDC` at `0x1800dc55c`
- `GDI32!RestoreDC` at `0x1800dc6c8`
- `GDI32!RestoreDC` at `0x1800dc55c`
- `GDI32!RestoreDC` at `0x1800dc6c8`
- `GDI32!SetViewportOrgEx` at `0x1800dc471`
- `GDI32!SetViewportOrgEx` at `0x1800dc471`
- `GDI32!SetWindowOrgEx` at `0x1800dc482`
- `GDI32!SetWindowOrgEx` at `0x1800dc482`
- `GDI32!SaveDC` at `0x1800dc44b`
- `GDI32!SaveDC` at `0x1800dc5d7`
- `GDI32!SaveDC` at `0x1800dc44b`
- `GDI32!SaveDC` at `0x1800dc5d7`
- `GDI32!DeleteObject` at `0x1800dc71a`
- `GDI32!DeleteObject` at `0x1800dc728`
- `GDI32!DeleteObject` at `0x1800dc736`
- `GDI32!DeleteObject` at `0x1800dc744`
- `GDI32!DeleteObject` at `0x1800dc71a`
- `GDI32!DeleteObject` at `0x1800dc728`
- `GDI32!DeleteObject` at `0x1800dc736`
- `GDI32!DeleteObject` at `0x1800dc744`

## pseudocode

```c
__int64 __fastcall CInkOverlay::OnPaint(CInkOverlay *this, UINT a2, WPARAM a3, LPARAM a4, int *a5)
{
  HRGN v6; // r12
  HRGN v7; // rdi
  HRGN v8; // r14
  HRGN v9; // r15
  HDC DC; // r13
  HRGN RectRgn; // rax
  HRGN v12; // rax
  HRGN v13; // rax
  HWND v14; // rcx
  HDC v15; // r13
  HRGN v16; // rax
  struct IInkRenderer *v17; // r9
  struct tagPOINT Points; // [rsp+30h] [rbp-68h] BYREF
  HRGN v20; // [rsp+40h] [rbp-58h]
  HRGN v21; // [rsp+48h] [rbp-50h]
  HRGN v22; // [rsp+50h] [rbp-48h]
  HRGN v23; // [rsp+58h] [rbp-40h]
  int nSavedDC; // [rsp+A0h] [rbp+8h]
  int nSavedDCa; // [rsp+A0h] [rbp+8h]

  *a5 = 0;
  v6 = 0;
  v20 = 0;
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  v23 = 0;
  if ( *((_WORD *)this + 193) == 0xFFFF || *((_DWORD *)this + 215) )
  {
    DC = GetDC(*((HWND *)this + 7));
    nSavedDC = SaveDC(DC);
    SetMapMode(DC, 1);
    SetViewportOrgEx(DC, 0, 0, 0);
    SetWindowOrgEx(DC, 0, 0, 0);
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v6 = RectRgn;
    v20 = RectRgn;
    if ( RectRgn )
      GetRandomRgn(DC, RectRgn, 4);
    v12 = CreateRectRgn(0, 0, 0, 0);
    v7 = v12;
    v21 = v12;
    if ( v12 )
    {
      GetUpdateRgn(*((HWND *)this + 7), v12, 0);
      CInkAutoDataLock::CInkAutoDataLock(
        (CInkAutoDataLock *)&Points,
        (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
      if ( !IsRectEmpty((const RECT *)this + 21) )
      {
        v13 = CreateRectRgn(
                *((_DWORD *)this + 84),
                *((_DWORD *)this + 85),
                *((_DWORD *)this + 86),
                *((_DWORD *)this + 87));
        v9 = v13;
        v23 = v13;
        if ( v13 )
          CombineRgn(v7, v7, v13, 1);
      }
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&Points);
    }
    RestoreDC(DC, nSavedDC);
    ReleaseDC(*((HWND *)this + 7), DC);
    try
    {
      if ( v7 )
        CInkOverlay::_InvalidateWindow(this, 0, v7, 1, 0);
      CallWindowProcW(*((WNDPROC *)this + 13), *((HWND *)this + 7), a2, a3, a4);
      v14 = (HWND)*((_QWORD *)this + 7);
      if ( *((_DWORD *)this + 213) )
      {
        RedrawWindow(v14, 0, v7, 0x180u);
      }
      else
      {
        v15 = GetDC(v14);
        nSavedDCa = SaveDC(v15);
        v16 = CreateRectRgn(0, 0, 0, 0);
        v8 = v16;
        v22 = v16;
        if ( v16 && v6 && v7 )
        {
          GetRandomRgn(v15, v16, 4);
          if ( (unsigned int)CombineRgn(v8, v8, v6, 4) > 1 )
          {
            Points = 0;
            MapWindowPoints(0, *((HWND *)this + 7), &Points, 1u);
            OffsetRgn(v8, Points.x, Points.y);
            CombineRgn(v7, v7, v8, 2);
            if ( v9 )
              CombineRgn(v7, v7, v9, 1);
          }
          SelectClipRgn(v15, v7);
          CInkOverlay::_DrawInk(this, v15, 0, v17);
        }
        RestoreDC(v15, nSavedDCa);
        ReleaseDC(*((HWND *)this + 7), v15);
      }
      *a5 = 1;
    }
    catch ( ... )
    {
      ReportWispException();
      v6 = v20;
      v7 = v21;
      v8 = v22;
      v9 = v23;
    }
  }
  if ( v6 )
    DeleteObject(v6);
  if ( v7 )
    DeleteObject(v7);
  if ( v8 )
    DeleteObject(v8);
  if ( v9 )
    DeleteObject(v9);
  return 0;
}

```

## disassembly

```asm
0x1800dc3d8  mov     [rsp+arg_18], r9
0x1800dc3dd  mov     [rsp+wParam], r8
0x1800dc3e2  mov     [rsp+Msg], edx
0x1800dc3e6  push    rsi
0x1800dc3e7  push    rdi
0x1800dc3e8  push    r12
0x1800dc3ea  push    r13
0x1800dc3ec  push    r14
0x1800dc3ee  push    r15
0x1800dc3f0  sub     rsp, 68h
0x1800dc3f4  mov     rsi, rcx
0x1800dc3f7  mov     rax, [rsp+98h+arg_20]
0x1800dc3ff  mov     dword ptr [rax], 0
0x1800dc405  xor     r12d, r12d
0x1800dc408  mov     [rsp+98h+var_58], r12
0x1800dc40d  xor     edi, edi
0x1800dc40f  mov     [rsp+98h+var_50], rdi
0x1800dc414  xor     r14d, r14d
0x1800dc417  mov     [rsp+98h+var_48], r14
0x1800dc41c  xor     r15d, r15d
0x1800dc41f  mov     [rsp+98h+var_40], r15
0x1800dc424  cmp     word ptr [rcx+182h], 0FFFFh
0x1800dc42c  jz      short loc_1800DC43B
0x1800dc42e  cmp     [rcx+35Ch], r15d
0x1800dc435  jz      loc_1800DC6FC
0x1800dc43b  mov     rcx, [rcx+38h]; hWnd
0x1800dc43f  call    cs:__imp_GetDC
0x1800dc445  mov     r13, rax
0x1800dc448  mov     rcx, rax; hdc
0x1800dc44b  call    cs:__imp_SaveDC
0x1800dc451  mov     [rsp+98h+nSavedDC], eax
0x1800dc458  mov     edx, 1; iMode
0x1800dc45d  mov     rcx, r13; hdc
0x1800dc460  call    cs:__imp_SetMapMode
0x1800dc466  xor     r9d, r9d; lppt
0x1800dc469  xor     r8d, r8d; y
0x1800dc46c  xor     edx, edx; x
0x1800dc46e  mov     rcx, r13; hdc
0x1800dc471  call    cs:__imp_SetViewportOrgEx
0x1800dc477  xor     r9d, r9d; lppt
0x1800dc47a  xor     r8d, r8d; y
0x1800dc47d  xor     edx, edx; x
0x1800dc47f  mov     rcx, r13; hdc
0x1800dc482  call    cs:__imp_SetWindowOrgEx
0x1800dc488  xor     r9d, r9d; y2
0x1800dc48b  xor     r8d, r8d; x2
0x1800dc48e  xor     edx, edx; y1
0x1800dc490  xor     ecx, ecx; x1
0x1800dc492  call    cs:__imp_CreateRectRgn
0x1800dc498  mov     r12, rax
0x1800dc49b  mov     [rsp+98h+var_58], rax
0x1800dc4a0  test    rax, rax
0x1800dc4a3  jz      short loc_1800DC4B7
0x1800dc4a5  mov     r8d, 4; i
0x1800dc4ab  mov     rdx, rax; hrgn
0x1800dc4ae  mov     rcx, r13; hdc
0x1800dc4b1  call    cs:__imp_GetRandomRgn
0x1800dc4b7  xor     r9d, r9d; y2
0x1800dc4ba  xor     r8d, r8d; x2
0x1800dc4bd  xor     edx, edx; y1
0x1800dc4bf  xor     ecx, ecx; x1
0x1800dc4c1  call    cs:__imp_CreateRectRgn
0x1800dc4c7  mov     rdi, rax
0x1800dc4ca  mov     [rsp+98h+var_50], rax
0x1800dc4cf  test    rax, rax
0x1800dc4d2  jz      short loc_1800DC552
0x1800dc4d4  xor     r8d, r8d; bErase
0x1800dc4d7  mov     rdx, rax; hRgn
0x1800dc4da  mov     rcx, [rsi+38h]; hWnd
0x1800dc4de  call    cs:__imp_GetUpdateRgn
0x1800dc4e4  lea     rdx, [rsi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800dc4eb  lea     rcx, [rsp+98h+Points]; this
0x1800dc4f0  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800dc4f5  lea     rcx, [rsi+150h]; lprc
0x1800dc4fc  call    cs:__imp_IsRectEmpty
0x1800dc502  test    eax, eax
0x1800dc504  jnz     short loc_1800DC548
0x1800dc506  mov     r9d, [rsi+15Ch]; y2
0x1800dc50d  mov     r8d, [rsi+158h]; x2
0x1800dc514  mov     edx, [rsi+154h]; y1
0x1800dc51a  mov     ecx, [rsi+150h]; x1
0x1800dc520  call    cs:__imp_CreateRectRgn
0x1800dc526  mov     r15, rax
0x1800dc529  mov     [rsp+98h+var_40], rax
0x1800dc52e  test    rax, rax
0x1800dc531  jz      short loc_1800DC548
0x1800dc533  mov     r9d, 1; iMode
0x1800dc539  mov     r8, rax; hrgnSrc2
0x1800dc53c  mov     rdx, rdi; hrgnSrc1
0x1800dc53f  mov     rcx, rdi; hrgnDst
0x1800dc542  call    cs:__imp_CombineRgn
0x1800dc548  lea     rcx, [rsp+98h+Points]; this
0x1800dc54d  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800dc552  mov     edx, [rsp+98h+nSavedDC]; nSavedDC
0x1800dc559  mov     rcx, r13; hdc
0x1800dc55c  call    cs:__imp_RestoreDC
0x1800dc562  mov     rdx, r13; hDC
0x1800dc565  mov     rcx, [rsi+38h]; hWnd
0x1800dc569  call    cs:__imp_ReleaseDC
0x1800dc56f  test    rdi, rdi
0x1800dc572  jz      short loc_1800DC58F
0x1800dc574  mov     dword ptr [rsp+98h+lParam], 0; int
0x1800dc57c  mov     r9d, 1; int
0x1800dc582  mov     r8, rdi; HRGN
0x1800dc585  xor     edx, edx; struct tagRECT *
0x1800dc587  mov     rcx, rsi; this
0x1800dc58a  call    ?_InvalidateWindow@CInkOverlay@@AEAAHPEAUtagRECT@@PEAUHRGN__@@HH@Z; CInkOverlay::_InvalidateWindow(tagRECT *,HRGN__ *,int,int)
0x1800dc58f  mov     rax, [rsp+98h+arg_18]
0x1800dc597  mov     [rsp+98h+lParam], rax; lParam
0x1800dc59c  mov     r9, [rsp+98h+wParam]; wParam
0x1800dc5a4  mov     r8d, [rsp+98h+Msg]; Msg
0x1800dc5ac  mov     rdx, [rsi+38h]; hWnd
0x1800dc5b0  mov     rcx, [rsi+68h]; lpPrevWndFunc
0x1800dc5b4  call    cs:__imp_CallWindowProcW
0x1800dc5ba  mov     rcx, [rsi+38h]; hWnd
0x1800dc5be  cmp     dword ptr [rsi+354h], 0
0x1800dc5c5  jnz     loc_1800DC6DD
0x1800dc5cb  call    cs:__imp_GetDC
0x1800dc5d1  mov     r13, rax
0x1800dc5d4  mov     rcx, rax; hdc
0x1800dc5d7  call    cs:__imp_SaveDC
0x1800dc5dd  mov     [rsp+98h+nSavedDC], eax
0x1800dc5e4  xor     r9d, r9d; y2
0x1800dc5e7  xor     r8d, r8d; x2
0x1800dc5ea  xor     edx, edx; y1
0x1800dc5ec  xor     ecx, ecx; x1
0x1800dc5ee  call    cs:__imp_CreateRectRgn
0x1800dc5f4  mov     r14, rax
0x1800dc5f7  mov     [rsp+98h+var_48], rax
0x1800dc5fc  test    rax, rax
0x1800dc5ff  jz      loc_1800DC6BE
0x1800dc605  test    r12, r12
0x1800dc608  jz      loc_1800DC6BE
0x1800dc60e  test    rdi, rdi
0x1800dc611  jz      loc_1800DC6BE
0x1800dc617  mov     r8d, 4; i
0x1800dc61d  mov     rdx, rax; hrgn
0x1800dc620  mov     rcx, r13; hdc
0x1800dc623  call    cs:__imp_GetRandomRgn
0x1800dc629  mov     r9d, 4; iMode
0x1800dc62f  mov     r8, r12; hrgnSrc2
0x1800dc632  mov     rdx, r14; hrgnSrc1
0x1800dc635  mov     rcx, r14; hrgnDst
0x1800dc638  call    cs:__imp_CombineRgn
0x1800dc63e  cmp     eax, 1
0x1800dc641  jbe     short loc_1800DC6A4
0x1800dc643  mov     qword ptr [rsp+98h+Points.x], 0
0x1800dc64c  mov     r9d, 1; cPoints
0x1800dc652  lea     r8, [rsp+98h+Points]; lpPoints
0x1800dc657  mov     rdx, [rsi+38h]; hWndTo
0x1800dc65b  xor     ecx, ecx; hWndFrom
0x1800dc65d  call    cs:__imp_MapWindowPoints
0x1800dc663  mov     r8d, [rsp+98h+Points.y]; y
0x1800dc668  mov     edx, [rsp+98h+Points.x]; x
0x1800dc66c  mov     rcx, r14; hrgn
0x1800dc66f  call    cs:__imp_OffsetRgn
0x1800dc675  mov     r9d, 2; iMode
0x1800dc67b  mov     r8, r14; hrgnSrc2
0x1800dc67e  mov     rdx, rdi; hrgnSrc1
0x1800dc681  mov     rcx, rdi; hrgnDst
0x1800dc684  call    cs:__imp_CombineRgn
0x1800dc68a  test    r15, r15
0x1800dc68d  jz      short loc_1800DC6A4
0x1800dc68f  mov     r9d, 1; iMode
0x1800dc695  mov     r8, r15; hrgnSrc2
0x1800dc698  mov     rdx, rdi; hrgnSrc1
0x1800dc69b  mov     rcx, rdi; hrgnDst
0x1800dc69e  call    cs:__imp_CombineRgn
0x1800dc6a4  mov     rdx, rdi; hrgn
0x1800dc6a7  mov     rcx, r13; hdc
0x1800dc6aa  call    cs:__imp_SelectClipRgn
0x1800dc6b0  xor     r8d, r8d; struct IInkRectangle *
0x1800dc6b3  mov     rdx, r13; HDC
0x1800dc6b6  mov     rcx, rsi; this
0x1800dc6b9  call    ?_DrawInk@CInkOverlay@@AEAAJPEAUHDC__@@PEAUIInkRectangle@@PEAUIInkRenderer@@@Z; CInkOverlay::_DrawInk(HDC__ *,IInkRectangle *,IInkRenderer *)
0x1800dc6be  mov     edx, [rsp+98h+nSavedDC]; nSavedDC
0x1800dc6c5  mov     rcx, r13; hdc
0x1800dc6c8  call    cs:__imp_RestoreDC
0x1800dc6ce  mov     rdx, r13; hDC
0x1800dc6d1  mov     rcx, [rsi+38h]; hWnd
0x1800dc6d5  call    cs:__imp_ReleaseDC
0x1800dc6db  jmp     short loc_1800DC6EE
0x1800dc6dd  mov     r9d, 180h; flags
0x1800dc6e3  mov     r8, rdi; hrgnUpdate
0x1800dc6e6  xor     edx, edx; lprcUpdate
0x1800dc6e8  call    cs:__imp_RedrawWindow
0x1800dc6ee  mov     rax, [rsp+98h+arg_20]
0x1800dc6f6  mov     dword ptr [rax], 1
0x1800dc6fc  jmp     short loc_1800DC712
0x1800dc6fe  mov     r12, [rsp+98h+var_58]
0x1800dc703  mov     rdi, [rsp+98h+var_50]
0x1800dc708  mov     r14, [rsp+98h+var_48]
0x1800dc70d  mov     r15, [rsp+98h+var_40]
0x1800dc712  test    r12, r12
0x1800dc715  jz      short loc_1800DC720
0x1800dc717  mov     rcx, r12; ho
0x1800dc71a  call    cs:__imp_DeleteObject
0x1800dc720  test    rdi, rdi
0x1800dc723  jz      short loc_1800DC72E
0x1800dc725  mov     rcx, rdi; ho
0x1800dc728  call    cs:__imp_DeleteObject
0x1800dc72e  test    r14, r14
0x1800dc731  jz      short loc_1800DC73C
0x1800dc733  mov     rcx, r14; ho
0x1800dc736  call    cs:__imp_DeleteObject
0x1800dc73c  test    r15, r15
0x1800dc73f  jz      short loc_1800DC74A
0x1800dc741  mov     rcx, r15; ho
0x1800dc744  call    cs:__imp_DeleteObject
0x1800dc74a  xor     eax, eax
0x1800dc74c  add     rsp, 68h
0x1800dc750  pop     r15
0x1800dc752  pop     r14
0x1800dc754  pop     r13
0x1800dc756  pop     r12
0x1800dc758  pop     rdi
0x1800dc759  pop     rsi
0x1800dc75a  retn
```
