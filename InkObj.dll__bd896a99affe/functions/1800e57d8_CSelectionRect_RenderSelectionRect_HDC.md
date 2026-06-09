# CSelectionRect::_RenderSelectionRect(HDC__ *)

- ea: `0x1800e57d8`
- end: `0x1800e5b8e`
- name: `?_RenderSelectionRect@CSelectionRect@@AEAAHPEAUHDC__@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(CSelectionRect *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x1800e5478`

## callees

- `0x1800e4e5c`
- `0x1800e54d0`
- `0x1800e55e4`
- `0x1800e57d8`
- `0x180104f30`

## import_xrefs

- `USER32!InflateRect` at `0x1800e584c`
- `USER32!InflateRect` at `0x1800e58fb`
- `USER32!InflateRect` at `0x1800e5b36`
- `USER32!InflateRect` at `0x1800e584c`
- `USER32!InflateRect` at `0x1800e58fb`
- `USER32!InflateRect` at `0x1800e5b36`
- `USER32!DrawFocusRect` at `0x1800e5b43`
- `USER32!DrawFocusRect` at `0x1800e5b43`
- `GDI32!SetMapMode` at `0x1800e58a5`
- `GDI32!SetMapMode` at `0x1800e58a5`
- `GDI32!SetBkMode` at `0x1800e5896`
- `GDI32!SetBkMode` at `0x1800e5b52`
- `GDI32!SetBkMode` at `0x1800e5896`
- `GDI32!SetBkMode` at `0x1800e5b52`
- `GDI32!RestoreDC` at `0x1800e5b5e`
- `GDI32!RestoreDC` at `0x1800e5b5e`
- `GDI32!SetViewportOrgEx` at `0x1800e58b6`
- `GDI32!SetViewportOrgEx` at `0x1800e58b6`
- `GDI32!SetWindowOrgEx` at `0x1800e58c7`
- `GDI32!SetWindowOrgEx` at `0x1800e58c7`
- `GDI32!SaveDC` at `0x1800e5887`
- `GDI32!SaveDC` at `0x1800e5887`
- `GDI32!SelectObject` at `0x1800e5947`
- `GDI32!SelectObject` at `0x1800e5969`
- `GDI32!SelectObject` at `0x1800e59be`
- `GDI32!SelectObject` at `0x1800e59e0`
- `GDI32!SelectObject` at `0x1800e5947`
- `GDI32!SelectObject` at `0x1800e5969`
- `GDI32!SelectObject` at `0x1800e59be`
- `GDI32!SelectObject` at `0x1800e59e0`
- `GDI32!Polyline` at `0x1800e595d`
- `GDI32!Polyline` at `0x1800e59d4`
- `GDI32!Polyline` at `0x1800e595d`
- `GDI32!Polyline` at `0x1800e59d4`
- `GDI32!DeleteObject` at `0x1800e5972`
- `GDI32!DeleteObject` at `0x1800e59e9`
- `GDI32!DeleteObject` at `0x1800e5972`
- `GDI32!DeleteObject` at `0x1800e59e9`
- `GDI32!CreatePenIndirect` at `0x1800e5905`
- `GDI32!CreatePenIndirect` at `0x1800e597c`
- `GDI32!CreatePenIndirect` at `0x1800e5905`
- `GDI32!CreatePenIndirect` at `0x1800e597c`

## pseudocode

```c
__int64 __fastcall CSelectionRect::_RenderSelectionRect(CSelectionRect *this, HDC a2)
{
  unsigned int v4; // r15d
  _DWORD *v5; // r14
  int v6; // r13d
  CSelectionRect *v7; // rcx
  HPEN v8; // r12
  HGDIOBJ v9; // rbx
  HPEN v10; // r12
  HGDIOBJ v11; // rbx
  int WidgetBmpResId; // eax
  CSelectionRect *v13; // rcx
  int v14; // eax
  CSelectionRect *v15; // rcx
  int v16; // eax
  CSelectionRect *v17; // rcx
  int v18; // eax
  CSelectionRect *v19; // rcx
  int v20; // eax
  CSelectionRect *v21; // rcx
  int v22; // eax
  CSelectionRect *v23; // rcx
  int v24; // eax
  CSelectionRect *v25; // rcx
  int v26; // eax
  CSelectionRect *v27; // rcx
  CSelectionRect *v28; // rcx
  int v30; // [rsp+30h] [rbp-49h]
  int v31; // [rsp+34h] [rbp-45h]
  int mode; // [rsp+38h] [rbp-41h]
  struct tagRECT rc; // [rsp+40h] [rbp-39h] BYREF
  RECT v34; // [rsp+50h] [rbp-29h] BYREF
  LOGPEN plpen; // [rsp+60h] [rbp-19h] BYREF
  POINT apt; // [rsp+70h] [rbp-9h] BYREF
  LONG left; // [rsp+78h] [rbp-1h]
  LONG bottom; // [rsp+7Ch] [rbp+3h]
  __int64 v39; // [rsp+80h] [rbp+7h]
  LONG right; // [rsp+88h] [rbp+Fh]
  LONG top; // [rsp+8Ch] [rbp+13h]
  __int64 v42; // [rsp+90h] [rbp+17h]

  v4 = 1;
  rc = (struct tagRECT)*((_OWORD *)this + 1);
  CSelectionRect::NormalizeRect(this, &rc);
  v5 = (_DWORD *)((char *)this + 76);
  if ( !*((_DWORD *)this + 12) || *v5 == 2 )
    rc = *(struct tagRECT *)this;
  InflateRect(&rc, 8, 8);
  plpen.lopnWidth = (POINT)1LL;
  plpen.lopnStyle = 2;
  v30 = (rc.right + rc.left) / 2;
  v31 = (rc.top + rc.bottom) / 2;
  plpen.lopnColor = *((_DWORD *)this + 13) != 0 ? 0xFFFFFF : 0;
  v6 = SaveDC(a2);
  mode = SetBkMode(a2, 1);
  SetMapMode(a2, 1);
  SetViewportOrgEx(a2, 0, 0, 0);
  SetWindowOrgEx(a2, 0, 0, 0);
  if ( *((_DWORD *)this + 12) )
  {
    if ( *v5 == 3 )
    {
      v34 = *(RECT *)this;
      CSelectionRect::NormalizeRect(v7, &v34);
      InflateRect(&v34, 8, 8);
      v8 = CreatePenIndirect(&plpen);
      if ( v8 )
      {
        bottom = v34.bottom;
        top = v34.top;
        apt = *(POINT *)&v34.left;
        left = v34.left;
        v39 = *(_QWORD *)&v34.right;
        right = v34.right;
        v42 = *(_QWORD *)&v34.left;
        v9 = SelectObject(a2, v8);
        Polyline(a2, &apt, 5);
        SelectObject(a2, v9);
        DeleteObject(v8);
      }
    }
  }
  v10 = CreatePenIndirect(&plpen);
  if ( v10 )
  {
    bottom = rc.bottom;
    top = rc.top;
    apt = *(POINT *)&rc.left;
    left = rc.left;
    v39 = *(_QWORD *)&rc.right;
    right = rc.right;
    v42 = *(_QWORD *)&rc.left;
    v11 = SelectObject(a2, v10);
    Polyline(a2, &apt, 5);
    SelectObject(a2, v11);
    DeleteObject(v10);
  }
  WidgetBmpResId = CSelectionRect::_GetWidgetBmpResId(this, SHR_NW, 1);
  CSelectionRect::_DrawWidget(v13, a2, rc.left, rc.top, WidgetBmpResId);
  v14 = CSelectionRect::_GetWidgetBmpResId(this, SHR_NE, 1);
  CSelectionRect::_DrawWidget(v15, a2, rc.right, rc.top, v14);
  v16 = CSelectionRect::_GetWidgetBmpResId(this, SHR_SW, 1);
  CSelectionRect::_DrawWidget(v17, a2, rc.left, rc.bottom, v16);
  v18 = CSelectionRect::_GetWidgetBmpResId(this, SHR_SE, 1);
  CSelectionRect::_DrawWidget(v19, a2, rc.right, rc.bottom, v18);
  v20 = CSelectionRect::_GetWidgetBmpResId(this, SHR_N, 0);
  CSelectionRect::_DrawWidget(v21, a2, v30, rc.top, v20);
  v22 = CSelectionRect::_GetWidgetBmpResId(this, SHR_S, 0);
  CSelectionRect::_DrawWidget(v23, a2, v30, rc.bottom, v22);
  v24 = CSelectionRect::_GetWidgetBmpResId(this, SHR_W, 0);
  CSelectionRect::_DrawWidget(v25, a2, rc.left, v31, v24);
  v26 = CSelectionRect::_GetWidgetBmpResId(this, SHR_E, 0);
  CSelectionRect::_DrawWidget(v27, a2, rc.right, v31, v26);
  if ( *((_DWORD *)this + 12) && *v5 == 2 )
  {
    v34 = (RECT)*((_OWORD *)this + 1);
    CSelectionRect::NormalizeRect(v28, &v34);
    InflateRect(&v34, 8, 8);
    v4 = DrawFocusRect(a2, &v34);
  }
  SetBkMode(a2, mode);
  RestoreDC(a2, v6);
  return v4;
}

```

## disassembly

```asm
0x1800e57d8  mov     [rsp-8+arg_10], rbx
0x1800e57dd  push    rbp
0x1800e57de  push    rsi
0x1800e57df  push    rdi
0x1800e57e0  push    r12
0x1800e57e2  push    r13
0x1800e57e4  push    r14
0x1800e57e6  push    r15
0x1800e57e8  lea     rbp, [rsp-27h]
0x1800e57ed  sub     rsp, 0A0h
0x1800e57f4  mov     rax, cs:__security_cookie
0x1800e57fb  xor     rax, rsp
0x1800e57fe  mov     [rbp+57h+var_38], rax
0x1800e5802  movups  xmm0, xmmword ptr [rcx+10h]
0x1800e5806  mov     rdi, rdx
0x1800e5809  mov     rsi, rcx
0x1800e580c  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x1800e5810  mov     r15d, 1
0x1800e5816  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800e581b  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e5820  xor     r12d, r12d
0x1800e5823  lea     r14, [rsi+4Ch]
0x1800e5827  lea     r13d, [r15+1]
0x1800e582b  cmp     [rsi+30h], r12d
0x1800e582f  jz      short loc_1800E5836
0x1800e5831  cmp     [r14], r13d
0x1800e5834  jnz     short loc_1800E583E
0x1800e5836  movups  xmm0, xmmword ptr [rsi]
0x1800e5839  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800e583e  mov     ebx, 8
0x1800e5843  lea     rcx, [rbp+57h+rc]; lprc
0x1800e5847  mov     r8d, ebx; dy
0x1800e584a  mov     edx, ebx; dx
0x1800e584c  call    cs:__imp_InflateRect
0x1800e5852  mov     eax, [rbp+57h+rc.left]
0x1800e5855  add     eax, [rbp+57h+rc.right]
0x1800e5858  cdq
0x1800e5859  mov     qword ptr [rbp+57h+plpen.lopnWidth.x], r15
0x1800e585d  idiv    r13d
0x1800e5860  mov     [rbp+57h+plpen.lopnStyle], r13d
0x1800e5864  mov     [rbp+57h+var_A0], eax
0x1800e5867  mov     eax, [rbp+57h+rc.bottom]
0x1800e586a  add     eax, [rbp+57h+rc.top]
0x1800e586d  cdq
0x1800e586e  idiv    r13d
0x1800e5871  mov     [rbp+57h+var_9C], eax
0x1800e5874  mov     eax, [rsi+34h]
0x1800e5877  neg     eax
0x1800e5879  sbb     ecx, ecx
0x1800e587b  and     ecx, 0FFFFFFh
0x1800e5881  mov     [rbp+57h+plpen.lopnColor], ecx
0x1800e5884  mov     rcx, rdi; hdc
0x1800e5887  call    cs:__imp_SaveDC
0x1800e588d  mov     edx, r15d; mode
0x1800e5890  mov     rcx, rdi; hdc
0x1800e5893  mov     r13d, eax
0x1800e5896  call    cs:__imp_SetBkMode
0x1800e589c  mov     edx, r15d; iMode
0x1800e589f  mov     rcx, rdi; hdc
0x1800e58a2  mov     [rbp+57h+mode], eax
0x1800e58a5  call    cs:__imp_SetMapMode
0x1800e58ab  xor     r9d, r9d; lppt
0x1800e58ae  xor     r8d, r8d; y
0x1800e58b1  xor     edx, edx; x
0x1800e58b3  mov     rcx, rdi; hdc
0x1800e58b6  call    cs:__imp_SetViewportOrgEx
0x1800e58bc  xor     r9d, r9d; lppt
0x1800e58bf  xor     r8d, r8d; y
0x1800e58c2  xor     edx, edx; x
0x1800e58c4  mov     rcx, rdi; hdc
0x1800e58c7  call    cs:__imp_SetWindowOrgEx
0x1800e58cd  cmp     [rsi+30h], r12d
0x1800e58d1  jz      loc_1800E5978
0x1800e58d7  cmp     dword ptr [r14], 3
0x1800e58db  jnz     loc_1800E5978
0x1800e58e1  movups  xmm0, xmmword ptr [rsi]
0x1800e58e4  lea     rdx, [rbp+57h+var_80]; struct tagRECT *
0x1800e58e8  movdqu  xmmword ptr [rbp+57h+var_80.left], xmm0
0x1800e58ed  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e58f2  lea     rcx, [rbp+57h+var_80]; lprc
0x1800e58f6  mov     r8d, ebx; dy
0x1800e58f9  mov     edx, ebx; dx
0x1800e58fb  call    cs:__imp_InflateRect
0x1800e5901  lea     rcx, [rbp+57h+plpen]; plpen
0x1800e5905  call    cs:__imp_CreatePenIndirect
0x1800e590b  mov     r12, rax
0x1800e590e  test    rax, rax
0x1800e5911  jz      short loc_1800E5978
0x1800e5913  mov     edx, [rbp+57h+var_80.top]
0x1800e5916  mov     ecx, [rbp+57h+var_80.bottom]
0x1800e5919  mov     r8d, [rbp+57h+var_80.left]
0x1800e591d  mov     eax, [rbp+57h+var_80.right]
0x1800e5920  mov     [rbp+57h+apt.y], edx
0x1800e5923  mov     [rbp+57h+var_54], ecx
0x1800e5926  mov     dword ptr [rbp+57h+var_50+4], ecx
0x1800e5929  mov     rcx, rdi; hdc
0x1800e592c  mov     [rbp+57h+var_44], edx
0x1800e592f  mov     dword ptr [rbp+57h+var_40+4], edx
0x1800e5932  mov     rdx, r12; h
0x1800e5935  mov     [rbp+57h+apt.x], r8d
0x1800e5939  mov     [rbp+57h+var_58], r8d
0x1800e593d  mov     dword ptr [rbp+57h+var_50], eax
0x1800e5940  mov     [rbp+57h+var_48], eax
0x1800e5943  mov     dword ptr [rbp+57h+var_40], r8d
0x1800e5947  call    cs:__imp_SelectObject
0x1800e594d  mov     r8d, 5; cpt
0x1800e5953  lea     rdx, [rbp+57h+apt]; apt
0x1800e5957  mov     rcx, rdi; hdc
0x1800e595a  mov     rbx, rax
0x1800e595d  call    cs:__imp_Polyline
0x1800e5963  mov     rdx, rbx; h
0x1800e5966  mov     rcx, rdi; hdc
0x1800e5969  call    cs:__imp_SelectObject
0x1800e596f  mov     rcx, r12; ho
0x1800e5972  call    cs:__imp_DeleteObject
0x1800e5978  lea     rcx, [rbp+57h+plpen]; plpen
0x1800e597c  call    cs:__imp_CreatePenIndirect
0x1800e5982  mov     r12, rax
0x1800e5985  test    rax, rax
0x1800e5988  jz      short loc_1800E59EF
0x1800e598a  mov     edx, [rbp+57h+rc.top]
0x1800e598d  mov     ecx, [rbp+57h+rc.bottom]
0x1800e5990  mov     r8d, [rbp+57h+rc.left]
0x1800e5994  mov     eax, [rbp+57h+rc.right]
0x1800e5997  mov     [rbp+57h+apt.y], edx
0x1800e599a  mov     [rbp+57h+var_54], ecx
0x1800e599d  mov     dword ptr [rbp+57h+var_50+4], ecx
0x1800e59a0  mov     rcx, rdi; hdc
0x1800e59a3  mov     [rbp+57h+var_44], edx
0x1800e59a6  mov     dword ptr [rbp+57h+var_40+4], edx
0x1800e59a9  mov     rdx, r12; h
0x1800e59ac  mov     [rbp+57h+apt.x], r8d
0x1800e59b0  mov     [rbp+57h+var_58], r8d
0x1800e59b4  mov     dword ptr [rbp+57h+var_50], eax
0x1800e59b7  mov     [rbp+57h+var_48], eax
0x1800e59ba  mov     dword ptr [rbp+57h+var_40], r8d
0x1800e59be  call    cs:__imp_SelectObject
0x1800e59c4  mov     r8d, 5; cpt
0x1800e59ca  lea     rdx, [rbp+57h+apt]; apt
0x1800e59ce  mov     rcx, rdi; hdc
0x1800e59d1  mov     rbx, rax
0x1800e59d4  call    cs:__imp_Polyline
0x1800e59da  mov     rdx, rbx; h
0x1800e59dd  mov     rcx, rdi; hdc
0x1800e59e0  call    cs:__imp_SelectObject
0x1800e59e6  mov     rcx, r12; ho
0x1800e59e9  call    cs:__imp_DeleteObject
0x1800e59ef  mov     r8d, r15d; int
0x1800e59f2  mov     edx, r15d; enum SelectionHitResult
0x1800e59f5  mov     rcx, rsi; this
0x1800e59f8  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e59fd  mov     r8d, [rbp+57h+rc.left]; int
0x1800e5a01  mov     rdx, rdi; HDC
0x1800e5a04  mov     r9d, [rbp+57h+rc.top]; int
0x1800e5a08  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5a0c  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5a11  mov     r8d, r15d; int
0x1800e5a14  mov     edx, 3; enum SelectionHitResult
0x1800e5a19  mov     rcx, rsi; this
0x1800e5a1c  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5a21  mov     r8d, [rbp+57h+rc.right]; int
0x1800e5a25  mov     rdx, rdi; HDC
0x1800e5a28  mov     r9d, [rbp+57h+rc.top]; int
0x1800e5a2c  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5a30  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5a35  mov     r8d, r15d; int
0x1800e5a38  mov     edx, 4; enum SelectionHitResult
0x1800e5a3d  mov     rcx, rsi; this
0x1800e5a40  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5a45  mov     r8d, [rbp+57h+rc.left]; int
0x1800e5a49  mov     rdx, rdi; HDC
0x1800e5a4c  mov     r9d, [rbp+57h+rc.bottom]; int
0x1800e5a50  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5a54  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5a59  mov     r8d, r15d; int
0x1800e5a5c  mov     edx, 2; enum SelectionHitResult
0x1800e5a61  mov     rcx, rsi; this
0x1800e5a64  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5a69  mov     r8d, [rbp+57h+rc.right]; int
0x1800e5a6d  mov     rdx, rdi; HDC
0x1800e5a70  mov     r9d, [rbp+57h+rc.bottom]; int
0x1800e5a74  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5a78  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5a7d  xor     r8d, r8d; int
0x1800e5a80  mov     rcx, rsi; this
0x1800e5a83  lea     edx, [r8+7]; enum SelectionHitResult
0x1800e5a87  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5a8c  mov     r8d, [rbp+57h+var_A0]; int
0x1800e5a90  mov     rdx, rdi; HDC
0x1800e5a93  mov     r9d, [rbp+57h+rc.top]; int
0x1800e5a97  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5a9b  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5aa0  xor     r8d, r8d; int
0x1800e5aa3  mov     rcx, rsi; this
0x1800e5aa6  lea     r12d, [r8+8]
0x1800e5aaa  mov     edx, r12d; enum SelectionHitResult
0x1800e5aad  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5ab2  mov     r8d, [rbp+57h+var_A0]; int
0x1800e5ab6  mov     rdx, rdi; HDC
0x1800e5ab9  mov     r9d, [rbp+57h+rc.bottom]; int
0x1800e5abd  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5ac1  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5ac6  xor     r8d, r8d; int
0x1800e5ac9  lea     edx, [r12-2]; enum SelectionHitResult
0x1800e5ace  mov     rcx, rsi; this
0x1800e5ad1  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5ad6  mov     r8d, [rbp+57h+rc.left]; int
0x1800e5ada  mov     rdx, rdi; HDC
0x1800e5add  mov     r9d, [rbp+57h+var_9C]; int
0x1800e5ae1  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5ae5  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5aea  xor     r8d, r8d; int
0x1800e5aed  lea     edx, [r12-3]; enum SelectionHitResult
0x1800e5af2  mov     rcx, rsi; this
0x1800e5af5  call    ?_GetWidgetBmpResId@CSelectionRect@@AEAAHW4SelectionHitResult@@H@Z; CSelectionRect::_GetWidgetBmpResId(SelectionHitResult,int)
0x1800e5afa  mov     r8d, [rbp+57h+rc.right]; int
0x1800e5afe  mov     rdx, rdi; HDC
0x1800e5b01  mov     r9d, [rbp+57h+var_9C]; int
0x1800e5b05  mov     [rsp+0D0h+var_B0], eax; int
0x1800e5b09  call    ?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z; CSelectionRect::_DrawWidget(HDC__ *,int,int,int)
0x1800e5b0e  cmp     dword ptr [rsi+30h], 0
0x1800e5b12  jz      short loc_1800E5B4C
0x1800e5b14  cmp     dword ptr [r14], 2
0x1800e5b18  jnz     short loc_1800E5B4C
0x1800e5b1a  movups  xmm0, xmmword ptr [rsi+10h]
0x1800e5b1e  lea     rdx, [rbp+57h+var_80]; struct tagRECT *
0x1800e5b22  movdqu  xmmword ptr [rbp+57h+var_80.left], xmm0
0x1800e5b27  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e5b2c  lea     rcx, [rbp+57h+var_80]; lprc
0x1800e5b30  mov     r8d, r12d; dy
0x1800e5b33  mov     edx, r12d; dx
0x1800e5b36  call    cs:__imp_InflateRect
0x1800e5b3c  lea     rdx, [rbp+57h+var_80]; lprc
0x1800e5b40  mov     rcx, rdi; hDC
0x1800e5b43  call    cs:__imp_DrawFocusRect
0x1800e5b49  mov     r15d, eax
0x1800e5b4c  mov     edx, [rbp+57h+mode]; mode
0x1800e5b4f  mov     rcx, rdi; hdc
0x1800e5b52  call    cs:__imp_SetBkMode
0x1800e5b58  mov     edx, r13d; nSavedDC
0x1800e5b5b  mov     rcx, rdi; hdc
0x1800e5b5e  call    cs:__imp_RestoreDC
0x1800e5b64  mov     eax, r15d
0x1800e5b67  mov     rcx, [rbp+57h+var_38]
0x1800e5b6b  xor     rcx, rsp; StackCookie
0x1800e5b6e  call    __security_check_cookie
0x1800e5b73  mov     rbx, [rsp+0D0h+arg_10]
0x1800e5b7b  add     rsp, 0A0h
0x1800e5b82  pop     r15
0x1800e5b84  pop     r14
0x1800e5b86  pop     r13
0x1800e5b88  pop     r12
0x1800e5b8a  pop     rdi
0x1800e5b8b  pop     rsi
0x1800e5b8c  pop     rbp
0x1800e5b8d  retn
```
