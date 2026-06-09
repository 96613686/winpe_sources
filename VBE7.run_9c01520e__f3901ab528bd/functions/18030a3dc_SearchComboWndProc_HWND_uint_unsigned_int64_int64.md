# SearchComboWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18030a3dc`
- end: `0x18030a758`
- name: `?SearchComboWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `892`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800e6178`
- `0x1802043c4`
- `0x180308cfc`
- `0x18030a3dc`
- `0x180379520`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18030a704`
- `USER32!GetSystemMetrics` at `0x18030a704`
- `USER32!FillRect` at `0x18030a579`
- `USER32!FillRect` at `0x18030a729`
- `USER32!FillRect` at `0x18030a579`
- `USER32!FillRect` at `0x18030a729`
- `USER32!GetKeyState` at `0x18030a5c9`
- `USER32!GetKeyState` at `0x18030a5c9`
- `USER32!CallWindowProcA` at `0x18030a673`
- `USER32!CallWindowProcA` at `0x18030a673`
- `USER32!GetDC` at `0x18030a6bd`
- `USER32!GetDC` at `0x18030a6bd`
- `USER32!ReleaseDC` at `0x18030a738`
- `USER32!ReleaseDC` at `0x18030a738`
- `USER32!GetClientRect` at `0x18030a565`
- `USER32!GetClientRect` at `0x18030a6d0`
- `USER32!GetClientRect` at `0x18030a565`
- `USER32!GetClientRect` at `0x18030a6d0`
- `USER32!MapWindowPoints` at `0x18030a6f9`
- `USER32!MapWindowPoints` at `0x18030a6f9`
- `USER32!GetSysColor` at `0x18030a538`
- `USER32!GetSysColor` at `0x18030a538`
- `USER32!GetWindowLongPtrA` at `0x18030a41a`
- `USER32!GetWindowLongPtrA` at `0x18030a6ae`
- `USER32!GetWindowLongPtrA` at `0x18030a41a`
- `USER32!GetWindowLongPtrA` at `0x18030a6ae`
- `USER32!SendMessageA` at `0x18030a4fd`
- `USER32!SendMessageA` at `0x18030a4fd`
- `USER32!GetWindowRect` at `0x18030a6e3`
- `USER32!GetWindowRect` at `0x18030a6e3`
- `GDI32!DeleteObject` at `0x18030a584`
- `GDI32!DeleteObject` at `0x18030a584`
- `GDI32!CreateSolidBrush` at `0x18030a540`
- `GDI32!CreateSolidBrush` at `0x18030a540`

## pseudocode

```c
LRESULT __fastcall SearchComboWndProc(LPARAM a1, UINT a2, WPARAM a3, LPARAM a4)
{
  COLORREF SysColor; // eax
  struct EBAPP *v6; // rax
  int v7; // [rsp+34h] [rbp-BCh]
  OBJBRW_TOOLBAR_PANE *WindowLongPtrA; // [rsp+40h] [rbp-B0h]
  HBRUSH hbr; // [rsp+48h] [rbp-A8h]
  BOOL v10; // [rsp+50h] [rbp-A0h]
  LRESULT v11; // [rsp+58h] [rbp-98h] BYREF
  HDC DC; // [rsp+60h] [rbp-90h]
  __int64 v13; // [rsp+68h] [rbp-88h]
  LONG_PTR v14; // [rsp+70h] [rbp-80h]
  HDC hDC; // [rsp+78h] [rbp-78h]
  LPARAM lParam; // [rsp+80h] [rbp-70h] BYREF
  UINT v17; // [rsp+88h] [rbp-68h]
  WPARAM v18; // [rsp+90h] [rbp-60h]
  LPARAM v19; // [rsp+98h] [rbp-58h]
  RECT rc; // [rsp+B0h] [rbp-40h] BYREF
  struct tagRECT v21; // [rsp+C0h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+D0h] [rbp-20h] BYREF

  v11 = 0;
  WindowLongPtrA = (OBJBRW_TOOLBAR_PANE *)GetWindowLongPtrA((HWND)a1, -21);
  v7 = 0;
  if ( a2 > 0x102 )
  {
    if ( a2 >= 0x200 && (a2 <= 0x202 || a2 > 0x203 && (a2 <= 0x205 || a2 > 0x206 && a2 <= 0x208)) )
    {
      v19 = a4;
      v18 = a3;
      v17 = a2;
      lParam = a1;
      SendMessageA(*((HWND *)WindowLongPtrA + 6), 0x407u, 0, (LPARAM)&lParam);
    }
    goto LABEL_23;
  }
  switch ( a2 )
  {
    case 0x102u:
      if ( a3 == 9 )
      {
        v10 = GetKeyState(16) < 0;
        OBJBRW_TOOLBAR_PANE::DoTabKey(WindowLongPtrA, v10);
      }
      goto LABEL_23;
    case 7u:
      ObjbrwOnObtbctlReceiveFocus(*((_QWORD *)WindowLongPtrA + 5), 1);
      v7 = 1;
      goto LABEL_23;
    case 8u:
      goto LABEL_20;
  }
  if ( a2 != 20 )
  {
    if ( a2 != 33 )
      goto LABEL_23;
LABEL_20:
    v7 = 1;
    goto LABEL_23;
  }
  if ( ((*(_DWORD *)(*((_QWORD *)PebappCur() + 1) + 1072LL) >> 5) & 1) != 0 )
  {
LABEL_23:
    if ( !v7
      || (v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)WindowLongPtrA + 3) + 32LL))(*((_QWORD *)WindowLongPtrA
                                                                                               + 3)),
          v6 = PebappCur(),
          !(*(unsigned int (__fastcall **)(__int64, LPARAM, _QWORD, WPARAM, LPARAM, LRESULT *))(*((_QWORD *)v6 + 7)
                                                                                              + 488LL))(
             v13,
             a1,
             a2,
             a3,
             a4,
             &v11)) )
    {
      v11 = CallWindowProcA(qword_180402B18, (HWND)a1, a2, a3, a4);
    }
    if ( a2 == 15 && ((*(_DWORD *)(*((_QWORD *)PebappCur() + 1) + 1072LL) >> 5) & 1) == 0 )
    {
      v14 = GetWindowLongPtrA((HWND)a1, -21);
      DC = GetDC((HWND)a1);
      GetClientRect((HWND)a1, &rc);
      GetWindowRect(*(HWND *)(v14 + 80), &v21);
      MapWindowPoints(0, (HWND)a1, (LPPOINT)&v21, 2u);
      rc.right -= GetSystemMetrics(2);
      rc.left = v21.right;
      FillRect(DC, &rc, (HBRUSH)0x10);
      ReleaseDC((HWND)a1, DC);
    }
    return v11;
  }
  hDC = (HDC)a3;
  SysColor = GetSysColor(15);
  hbr = CreateSolidBrush(SysColor);
  if ( hbr )
  {
    GetClientRect((HWND)a1, &Rect);
    FillRect(hDC, &Rect, hbr);
    DeleteObject(hbr);
    return 1;
  }
  return v11;
}

```

## disassembly

```asm
0x18030a3dc  mov     [rsp-8+arg_18], r9
0x18030a3e1  mov     [rsp-8+wParam], r8
0x18030a3e6  mov     [rsp-8+Msg], edx
0x18030a3ea  mov     [rsp-8+hWnd], rcx
0x18030a3ef  push    rbp
0x18030a3f0  mov     rbp, rsp
0x18030a3f3  sub     rsp, 0F0h
0x18030a3fa  mov     rax, cs:__security_cookie
0x18030a401  xor     rax, rsp
0x18030a404  mov     [rbp+var_10], rax
0x18030a408  mov     [rsp+0F0h+var_98], 0
0x18030a411  mov     edx, 0FFFFFFEBh; nIndex
0x18030a416  mov     rcx, [rbp+hWnd]; hWnd
0x18030a41a  call    cs:__imp_GetWindowLongPtrA
0x18030a420  mov     [rsp+0F0h+var_B0], rax
0x18030a425  mov     [rsp+0F0h+var_BC], 0
0x18030a42d  mov     eax, [rbp+Msg]
0x18030a430  mov     [rsp+0F0h+var_C0], eax
0x18030a434  cmp     [rsp+0F0h+var_C0], 102h
0x18030a43c  ja      short loc_18030A47D
0x18030a43e  cmp     [rsp+0F0h+var_C0], 102h
0x18030a446  jz      loc_18030A5BD
0x18030a44c  cmp     [rsp+0F0h+var_C0], 7
0x18030a451  jz      loc_18030A596
0x18030a457  cmp     [rsp+0F0h+var_C0], 8
0x18030a45c  jz      loc_18030A5B3
0x18030a462  cmp     [rsp+0F0h+var_C0], 14h
0x18030a467  jz      loc_18030A508
0x18030a46d  cmp     [rsp+0F0h+var_C0], 21h ; '!'
0x18030a472  jz      loc_18030A5B3
0x18030a478  jmp     loc_18030A5FC
0x18030a47d  cmp     [rsp+0F0h+var_C0], 200h
0x18030a485  jb      loc_18030A5FC
0x18030a48b  cmp     [rsp+0F0h+var_C0], 202h
0x18030a493  jbe     short loc_18030A4CA
0x18030a495  cmp     [rsp+0F0h+var_C0], 203h
0x18030a49d  jbe     loc_18030A5FC
0x18030a4a3  cmp     [rsp+0F0h+var_C0], 205h
0x18030a4ab  jbe     short loc_18030A4CA
0x18030a4ad  cmp     [rsp+0F0h+var_C0], 206h
0x18030a4b5  jbe     loc_18030A5FC
0x18030a4bb  cmp     [rsp+0F0h+var_C0], 208h
0x18030a4c3  jbe     short loc_18030A4CA
0x18030a4c5  jmp     loc_18030A5FC
0x18030a4ca  mov     rax, [rbp+arg_18]
0x18030a4ce  mov     [rbp+var_58], rax
0x18030a4d2  mov     rax, [rbp+wParam]
0x18030a4d6  mov     [rbp+var_60], rax
0x18030a4da  mov     eax, [rbp+Msg]
0x18030a4dd  mov     [rbp+var_68], eax
0x18030a4e0  mov     rax, [rbp+hWnd]
0x18030a4e4  mov     [rbp+lParam], rax
0x18030a4e8  lea     r9, [rbp+lParam]; lParam
0x18030a4ec  xor     r8d, r8d; wParam
0x18030a4ef  mov     edx, 407h; Msg
0x18030a4f4  mov     rax, [rsp+0F0h+var_B0]
0x18030a4f9  mov     rcx, [rax+30h]; hWnd
0x18030a4fd  call    cs:__imp_SendMessageA
0x18030a503  jmp     loc_18030A5FC
0x18030a508  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18030a50d  mov     rax, [rax+8]
0x18030a511  mov     eax, [rax+430h]
0x18030a517  shr     eax, 5
0x18030a51a  and     eax, 1
0x18030a51d  test    eax, eax
0x18030a51f  jnz     short loc_18030A594
0x18030a521  mov     [rsp+0F0h+hbr], 0
0x18030a52a  mov     rax, [rbp+wParam]
0x18030a52e  mov     [rsp+0F0h+hDC], rax
0x18030a533  mov     ecx, 0Fh; nIndex
0x18030a538  call    cs:__imp_GetSysColor
0x18030a53e  mov     ecx, eax; color
0x18030a540  call    cs:__imp_CreateSolidBrush
0x18030a546  mov     [rsp+0F0h+hbr], rax
0x18030a54b  cmp     [rsp+0F0h+hbr], 0
0x18030a551  jnz     short loc_18030A55D
0x18030a553  jmp     loc_18030A73E
0x18030a558  jmp     loc_18030A73E
0x18030a55d  lea     rdx, [rbp+Rect]; lpRect
0x18030a561  mov     rcx, [rbp+hWnd]; hWnd
0x18030a565  call    cs:__imp_GetClientRect
0x18030a56b  mov     r8, [rsp+0F0h+hbr]; hbr
0x18030a570  lea     rdx, [rbp+Rect]; lprc
0x18030a574  mov     rcx, [rsp+0F0h+hDC]; hDC
0x18030a579  call    cs:__imp_FillRect
0x18030a57f  mov     rcx, [rsp+0F0h+hbr]; ho
0x18030a584  call    cs:__imp_DeleteObject
0x18030a58a  mov     eax, 1
0x18030a58f  jmp     loc_18030A743
0x18030a594  jmp     short loc_18030A5FC
0x18030a596  mov     edx, 1
0x18030a59b  mov     rax, [rsp+0F0h+var_B0]
0x18030a5a0  mov     rcx, [rax+28h]
0x18030a5a4  call    ?ObjbrwOnObtbctlReceiveFocus@@YAXPEAVOBJBRW@@W4OBTBCTL@@@Z; ObjbrwOnObtbctlReceiveFocus(OBJBRW *,OBTBCTL)
0x18030a5a9  mov     [rsp+0F0h+var_BC], 1
0x18030a5b1  jmp     short loc_18030A5FC
0x18030a5b3  mov     [rsp+0F0h+var_BC], 1
0x18030a5bb  jmp     short loc_18030A5FC
0x18030a5bd  cmp     [rbp+wParam], 9
0x18030a5c2  jnz     short loc_18030A5FC
0x18030a5c4  mov     ecx, 10h; nVirtKey
0x18030a5c9  call    cs:__imp_GetKeyState
0x18030a5cf  cwde
0x18030a5d0  test    eax, eax
0x18030a5d2  jge     short loc_18030A5DE
0x18030a5d4  mov     [rsp+0F0h+var_B8], 1
0x18030a5dc  jmp     short loc_18030A5E6
0x18030a5de  mov     [rsp+0F0h+var_B8], 0
0x18030a5e6  mov     eax, [rsp+0F0h+var_B8]
0x18030a5ea  mov     [rsp+0F0h+var_A0], eax
0x18030a5ee  mov     edx, [rsp+0F0h+var_A0]; int
0x18030a5f2  mov     rcx, [rsp+0F0h+var_B0]; this
0x18030a5f7  call    ?DoTabKey@OBJBRW_TOOLBAR_PANE@@QEAAXH@Z; OBJBRW_TOOLBAR_PANE::DoTabKey(int)
0x18030a5fc  cmp     [rsp+0F0h+var_BC], 0
0x18030a601  jz      short loc_18030A657
0x18030a603  mov     rax, [rsp+0F0h+var_B0]
0x18030a608  mov     rax, [rax+18h]
0x18030a60c  mov     rcx, [rsp+0F0h+var_B0]
0x18030a611  mov     rcx, [rcx+18h]
0x18030a615  mov     rax, [rax]
0x18030a618  call    qword ptr [rax+20h]
0x18030a61b  mov     [rsp+0F0h+var_88], rax
0x18030a620  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18030a625  mov     rax, [rax+38h]
0x18030a629  lea     rcx, [rsp+0F0h+var_98]
0x18030a62e  mov     [rsp+0F0h+var_C8], rcx
0x18030a633  mov     rcx, [rbp+arg_18]
0x18030a637  mov     [rsp+0F0h+var_D0], rcx
0x18030a63c  mov     r9, [rbp+wParam]
0x18030a640  mov     r8d, [rbp+Msg]
0x18030a644  mov     rdx, [rbp+hWnd]
0x18030a648  mov     rcx, [rsp+0F0h+var_88]
0x18030a64d  call    qword ptr [rax+1E8h]
0x18030a653  test    eax, eax
0x18030a655  jnz     short loc_18030A67E
0x18030a657  mov     rax, [rbp+arg_18]
0x18030a65b  mov     [rsp+0F0h+var_D0], rax; lParam
0x18030a660  mov     r9, [rbp+wParam]; wParam
0x18030a664  mov     r8d, [rbp+Msg]; Msg
0x18030a668  mov     rdx, [rbp+hWnd]; hWnd
0x18030a66c  mov     rcx, cs:qword_180402B18; lpPrevWndFunc
0x18030a673  call    cs:__imp_CallWindowProcA
0x18030a679  mov     [rsp+0F0h+var_98], rax
0x18030a67e  cmp     [rbp+Msg], 0Fh
0x18030a682  jnz     loc_18030A73E
0x18030a688  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18030a68d  mov     rax, [rax+8]
0x18030a691  mov     eax, [rax+430h]
0x18030a697  shr     eax, 5
0x18030a69a  and     eax, 1
0x18030a69d  test    eax, eax
0x18030a69f  jnz     loc_18030A73E
0x18030a6a5  mov     edx, 0FFFFFFEBh; nIndex
0x18030a6aa  mov     rcx, [rbp+hWnd]; hWnd
0x18030a6ae  call    cs:__imp_GetWindowLongPtrA
0x18030a6b4  mov     [rsp+0F0h+var_80], rax
0x18030a6b9  mov     rcx, [rbp+hWnd]; hWnd
0x18030a6bd  call    cs:__imp_GetDC
0x18030a6c3  mov     [rsp+0F0h+var_90], rax
0x18030a6c8  lea     rdx, [rbp+rc]; lpRect
0x18030a6cc  mov     rcx, [rbp+hWnd]; hWnd
0x18030a6d0  call    cs:__imp_GetClientRect
0x18030a6d6  lea     rdx, [rbp+var_30]; lpRect
0x18030a6da  mov     rax, [rsp+0F0h+var_80]
0x18030a6df  mov     rcx, [rax+50h]; hWnd
0x18030a6e3  call    cs:__imp_GetWindowRect
0x18030a6e9  mov     r9d, 2; cPoints
0x18030a6ef  lea     r8, [rbp+var_30]; lpPoints
0x18030a6f3  mov     rdx, [rbp+hWnd]; hWndTo
0x18030a6f7  xor     ecx, ecx; hWndFrom
0x18030a6f9  call    cs:__imp_MapWindowPoints
0x18030a6ff  mov     ecx, 2; nIndex
0x18030a704  call    cs:__imp_GetSystemMetrics
0x18030a70a  mov     ecx, [rbp+rc.right]
0x18030a70d  sub     ecx, eax
0x18030a70f  mov     eax, ecx
0x18030a711  mov     [rbp+rc.right], eax
0x18030a714  mov     eax, [rbp+var_30.right]
0x18030a717  mov     [rbp+rc.left], eax
0x18030a71a  mov     r8d, 10h; hbr
0x18030a720  lea     rdx, [rbp+rc]; lprc
0x18030a724  mov     rcx, [rsp+0F0h+var_90]; hDC
0x18030a729  call    cs:__imp_FillRect
0x18030a72f  mov     rdx, [rsp+0F0h+var_90]; hDC
0x18030a734  mov     rcx, [rbp+hWnd]; hWnd
0x18030a738  call    cs:__imp_ReleaseDC
0x18030a73e  mov     rax, [rsp+0F0h+var_98]
0x18030a743  mov     rcx, [rbp+var_10]
0x18030a747  xor     rcx, rsp; StackCookie
0x18030a74a  call    __security_check_cookie
0x18030a74f  add     rsp, 0F0h
0x18030a756  pop     rbp
0x18030a757  retn
```
