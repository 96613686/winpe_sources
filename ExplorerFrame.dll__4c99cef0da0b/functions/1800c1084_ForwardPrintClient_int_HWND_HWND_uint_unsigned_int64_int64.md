# ForwardPrintClient(int,HWND__ *,HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800c1084`
- end: `0x1800c12c3`
- name: `?ForwardPrintClient@@YA_JHPEAUHWND__@@0I_K_J@Z`
- size: `575`
- prototype: `__int64(int, HWND, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c0c20`

## callees

- `0x1800c1084`
- `0x18013f7d0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800c1257`
- `USER32!SendMessageW` at `0x1800c128b`
- `USER32!SendMessageW` at `0x1800c1257`
- `USER32!SendMessageW` at `0x1800c128b`
- `USER32!GetClientRect` at `0x1800c10f2`
- `USER32!GetClientRect` at `0x1800c10ff`
- `USER32!GetClientRect` at `0x1800c10f2`
- `USER32!GetClientRect` at `0x1800c10ff`
- `USER32!MapWindowPoints` at `0x1800c1119`
- `USER32!MapWindowPoints` at `0x1800c1119`
- `GDI32!DeleteObject` at `0x1800c11c6`
- `GDI32!DeleteObject` at `0x1800c12a5`
- `GDI32!DeleteObject` at `0x1800c11c6`
- `GDI32!DeleteObject` at `0x1800c12a5`
- `GDI32!CreateRectRgn` at `0x1800c1144`
- `GDI32!CreateRectRgn` at `0x1800c11a9`
- `GDI32!CreateRectRgn` at `0x1800c1144`
- `GDI32!CreateRectRgn` at `0x1800c11a9`
- `GDI32!GetClipBox` at `0x1800c1204`
- `GDI32!GetClipBox` at `0x1800c1204`
- `GDI32!GetLayout` at `0x1800c11cf`
- `GDI32!GetLayout` at `0x1800c11cf`
- `GDI32!SetLayout` at `0x1800c122f`
- `GDI32!SetLayout` at `0x1800c1276`
- `GDI32!SetLayout` at `0x1800c122f`
- `GDI32!SetLayout` at `0x1800c1276`
- `GDI32!GetViewportOrgEx` at `0x1800c11f0`
- `GDI32!GetViewportOrgEx` at `0x1800c11f0`
- `GDI32!LPtoDP` at `0x1800c1220`
- `GDI32!LPtoDP` at `0x1800c1220`
- `GDI32!SetViewportOrgEx` at `0x1800c1244`
- `GDI32!SetViewportOrgEx` at `0x1800c126a`
- `GDI32!SetViewportOrgEx` at `0x1800c12b8`
- `GDI32!SetViewportOrgEx` at `0x1800c1244`
- `GDI32!SetViewportOrgEx` at `0x1800c126a`
- `GDI32!SetViewportOrgEx` at `0x1800c12b8`
- `GDI32!SelectClipRgn` at `0x1800c11bd`
- `GDI32!SelectClipRgn` at `0x1800c129c`
- `GDI32!SelectClipRgn` at `0x1800c11bd`
- `GDI32!SelectClipRgn` at `0x1800c129c`
- `GDI32!OffsetViewportOrgEx` at `0x1800c1134`
- `GDI32!OffsetViewportOrgEx` at `0x1800c1134`
- `GDI32!GetClipRgn` at `0x1800c115d`
- `GDI32!GetClipRgn` at `0x1800c115d`
- `GDI32!GetRgnBox` at `0x1800c1175`
- `GDI32!GetRgnBox` at `0x1800c1175`

## pseudocode

```c
__int64 __fastcall ForwardPrintClient(__int64 a1, HWND a2, HWND a3, UINT a4, HDC hdc, LPARAM lParam)
{
  __int64 v6; // rsi
  HRGN RectRgn; // rax
  HRGN v12; // rdi
  HRGN v13; // rax
  HRGN v14; // r14
  DWORD Layout; // r14d
  struct tagPOINT v16; // [rsp+20h] [rbp-60h] BYREF
  struct tagPOINT pt; // [rsp+28h] [rbp-58h] BYREF
  struct tagRECT rc; // [rsp+30h] [rbp-50h] BYREF
  struct tagRECT v19; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT rect; // [rsp+60h] [rbp-20h] BYREF

  v6 = 0;
  if ( (lParam & 0x10) != 0 )
  {
    Rect = 0;
    v19 = 0;
    GetClientRect(a2, &Rect);
    GetClientRect(a3, &v19);
    pt = 0;
    MapWindowPoints(a3, a2, (LPPOINT)&v19, 2u);
    OffsetViewportOrgEx(hdc, v19.left - Rect.left, v19.top - Rect.top, &pt);
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v12 = RectRgn;
    v6 = 1;
    if ( RectRgn )
    {
      if ( GetClipRgn(hdc, RectRgn) == 1 )
      {
        rc = 0;
        if ( GetRgnBox(v12, &rc) )
        {
          v13 = CreateRectRgn(
                  v19.left + rc.left - Rect.left,
                  v19.top + rc.top - Rect.top,
                  rc.right + v19.right - Rect.right,
                  rc.bottom + Rect.bottom - v19.bottom);
          v14 = v13;
          if ( v13 )
          {
            SelectClipRgn(hdc, v13);
            DeleteObject(v14);
          }
        }
      }
    }
    Layout = GetLayout(hdc);
    if ( (Layout & 1) != 0 )
    {
      *(_QWORD *)&rc.left = 0;
      GetViewportOrgEx(hdc, (LPPOINT)&rc);
      rect = 0;
      GetClipBox(hdc, &rect);
      v16.x = rect.right;
      v16.y = rect.top;
      LPtoDP(hdc, &v16, 1);
      SetLayout(hdc, Layout & 0xFFFFFFFE);
      SetViewportOrgEx(hdc, v16.x + 1, v16.y, 0);
      SendMessageW(a3, a4, (WPARAM)hdc, lParam);
      SetViewportOrgEx(hdc, rc.left, rc.top, 0);
      SetLayout(hdc, Layout);
    }
    else
    {
      SendMessageW(a3, a4, (WPARAM)hdc, lParam);
    }
    if ( v12 )
    {
      SelectClipRgn(hdc, v12);
      DeleteObject(v12);
    }
    SetViewportOrgEx(hdc, pt.x, pt.y, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x1800c1084  push    rbp
0x1800c1086  push    rbx
0x1800c1087  push    rsi
0x1800c1088  push    rdi
0x1800c1089  push    r13
0x1800c108b  push    r14
0x1800c108d  push    r15
0x1800c108f  mov     rbp, rsp
0x1800c1092  sub     rsp, 80h
0x1800c1099  mov     rax, cs:__security_cookie
0x1800c10a0  xor     rax, rsp
0x1800c10a3  mov     [rbp+var_10], rax
0x1800c10a7  mov     rbx, [rbp+hdc]
0x1800c10ab  xor     esi, esi
0x1800c10ad  test    byte ptr [rbp+lParam], 10h
0x1800c10b1  mov     r13d, r9d
0x1800c10b4  mov     r15, r8
0x1800c10b7  mov     rdi, rdx
0x1800c10ba  jnz     short loc_1800C10DD
0x1800c10bc  mov     rax, rsi
0x1800c10bf  mov     rcx, [rbp+var_10]
0x1800c10c3  xor     rcx, rsp; StackCookie
0x1800c10c6  call    __security_check_cookie
0x1800c10cb  add     rsp, 80h
0x1800c10d2  pop     r15
0x1800c10d4  pop     r14
0x1800c10d6  pop     r13
0x1800c10d8  pop     rdi
0x1800c10d9  pop     rsi
0x1800c10da  pop     rbx
0x1800c10db  pop     rbp
0x1800c10dc  retn
0x1800c10dd  xorps   xmm0, xmm0
0x1800c10e0  lea     rdx, [rbp+Rect]; lpRect
0x1800c10e4  xorps   xmm1, xmm1
0x1800c10e7  mov     rcx, rdi; hWnd
0x1800c10ea  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800c10ee  movups  xmmword ptr [rbp+var_40.left], xmm1
0x1800c10f2  call    cs:__imp_GetClientRect
0x1800c10f8  lea     rdx, [rbp+var_40]; lpRect
0x1800c10fc  mov     rcx, r15; hWnd
0x1800c10ff  call    cs:__imp_GetClientRect
0x1800c1105  mov     r9d, 2; cPoints
0x1800c110b  mov     qword ptr [rbp+pt.x], rsi
0x1800c110f  lea     r8, [rbp+var_40]; lpPoints
0x1800c1113  mov     rdx, rdi; hWndTo
0x1800c1116  mov     rcx, r15; hWndFrom
0x1800c1119  call    cs:__imp_MapWindowPoints
0x1800c111f  mov     r8d, [rbp+var_40.top]
0x1800c1123  lea     r9, [rbp+pt]; lppt
0x1800c1127  mov     edx, [rbp+var_40.left]
0x1800c112a  mov     rcx, rbx; hdc
0x1800c112d  sub     r8d, [rbp+Rect.top]; y
0x1800c1131  sub     edx, [rbp+Rect.left]; x
0x1800c1134  call    cs:__imp_OffsetViewportOrgEx
0x1800c113a  xor     r9d, r9d; y2
0x1800c113d  xor     r8d, r8d; x2
0x1800c1140  xor     edx, edx; y1
0x1800c1142  xor     ecx, ecx; x1
0x1800c1144  call    cs:__imp_CreateRectRgn
0x1800c114a  mov     rdi, rax
0x1800c114d  mov     esi, 1
0x1800c1152  test    rax, rax
0x1800c1155  jz      short loc_1800C11CC
0x1800c1157  mov     rdx, rax; hrgn
0x1800c115a  mov     rcx, rbx; hdc
0x1800c115d  call    cs:__imp_GetClipRgn
0x1800c1163  cmp     eax, esi
0x1800c1165  jnz     short loc_1800C11CC
0x1800c1167  xorps   xmm0, xmm0
0x1800c116a  lea     rdx, [rbp+rc]; lprc
0x1800c116e  mov     rcx, rdi; hrgn
0x1800c1171  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800c1175  call    cs:__imp_GetRgnBox
0x1800c117b  test    eax, eax
0x1800c117d  jz      short loc_1800C11CC
0x1800c117f  mov     r9d, [rbp+Rect.bottom]
0x1800c1183  mov     r8d, [rbp+var_40.right]
0x1800c1187  mov     edx, [rbp+rc.top]
0x1800c118a  mov     ecx, [rbp+rc.left]
0x1800c118d  sub     r9d, [rbp+var_40.bottom]
0x1800c1191  sub     r8d, [rbp+Rect.right]
0x1800c1195  sub     edx, [rbp+Rect.top]
0x1800c1198  sub     ecx, [rbp+Rect.left]
0x1800c119b  add     r9d, [rbp+rc.bottom]; y2
0x1800c119f  add     r8d, [rbp+rc.right]; x2
0x1800c11a3  add     edx, [rbp+var_40.top]; y1
0x1800c11a6  add     ecx, [rbp+var_40.left]; x1
0x1800c11a9  call    cs:__imp_CreateRectRgn
0x1800c11af  mov     r14, rax
0x1800c11b2  test    rax, rax
0x1800c11b5  jz      short loc_1800C11CC
0x1800c11b7  mov     rdx, rax; hrgn
0x1800c11ba  mov     rcx, rbx; hdc
0x1800c11bd  call    cs:__imp_SelectClipRgn
0x1800c11c3  mov     rcx, r14; ho
0x1800c11c6  call    cs:__imp_DeleteObject
0x1800c11cc  mov     rcx, rbx; hdc
0x1800c11cf  call    cs:__imp_GetLayout
0x1800c11d5  mov     r14d, eax
0x1800c11d8  test    sil, al
0x1800c11db  jz      loc_1800C127E
0x1800c11e1  lea     rdx, [rbp+rc]; lppoint
0x1800c11e5  mov     qword ptr [rbp+rc.left], 0
0x1800c11ed  mov     rcx, rbx; hdc
0x1800c11f0  call    cs:__imp_GetViewportOrgEx
0x1800c11f6  xorps   xmm0, xmm0
0x1800c11f9  lea     rdx, [rbp+rect]; lprect
0x1800c11fd  mov     rcx, rbx; hdc
0x1800c1200  movups  xmmword ptr [rbp+rect.left], xmm0
0x1800c1204  call    cs:__imp_GetClipBox
0x1800c120a  mov     eax, [rbp+rect.right]
0x1800c120d  lea     rdx, [rbp+var_60]; lppt
0x1800c1211  mov     [rbp+var_60.x], eax
0x1800c1214  mov     r8d, esi; c
0x1800c1217  mov     eax, [rbp+rect.top]
0x1800c121a  mov     rcx, rbx; hdc
0x1800c121d  mov     [rbp+var_60.y], eax
0x1800c1220  call    cs:__imp_LPtoDP
0x1800c1226  mov     edx, r14d
0x1800c1229  mov     rcx, rbx; hdc
0x1800c122c  and     edx, 0FFFFFFFEh; l
0x1800c122f  call    cs:__imp_SetLayout
0x1800c1235  mov     edx, [rbp+var_60.x]
0x1800c1238  xor     r9d, r9d; lppt
0x1800c123b  mov     r8d, [rbp+var_60.y]; y
0x1800c123f  inc     edx; x
0x1800c1241  mov     rcx, rbx; hdc
0x1800c1244  call    cs:__imp_SetViewportOrgEx
0x1800c124a  mov     r9, [rbp+lParam]; lParam
0x1800c124e  mov     r8, rbx; wParam
0x1800c1251  mov     edx, r13d; Msg
0x1800c1254  mov     rcx, r15; hWnd
0x1800c1257  call    cs:__imp_SendMessageW
0x1800c125d  mov     r8d, [rbp+rc.top]; y
0x1800c1261  xor     r9d, r9d; lppt
0x1800c1264  mov     edx, [rbp+rc.left]; x
0x1800c1267  mov     rcx, rbx; hdc
0x1800c126a  call    cs:__imp_SetViewportOrgEx
0x1800c1270  mov     edx, r14d; l
0x1800c1273  mov     rcx, rbx; hdc
0x1800c1276  call    cs:__imp_SetLayout
0x1800c127c  jmp     short loc_1800C1291
0x1800c127e  mov     r9, [rbp+lParam]; lParam
0x1800c1282  mov     r8, rbx; wParam
0x1800c1285  mov     edx, r13d; Msg
0x1800c1288  mov     rcx, r15; hWnd
0x1800c128b  call    cs:__imp_SendMessageW
0x1800c1291  test    rdi, rdi
0x1800c1294  jz      short loc_1800C12AB
0x1800c1296  mov     rdx, rdi; hrgn
0x1800c1299  mov     rcx, rbx; hdc
0x1800c129c  call    cs:__imp_SelectClipRgn
0x1800c12a2  mov     rcx, rdi; ho
0x1800c12a5  call    cs:__imp_DeleteObject
0x1800c12ab  mov     r8d, [rbp+pt.y]; y
0x1800c12af  xor     r9d, r9d; lppt
0x1800c12b2  mov     edx, [rbp+pt.x]; x
0x1800c12b5  mov     rcx, rbx; hdc
0x1800c12b8  call    cs:__imp_SetViewportOrgEx
0x1800c12be  jmp     loc_1800C10BC
```
