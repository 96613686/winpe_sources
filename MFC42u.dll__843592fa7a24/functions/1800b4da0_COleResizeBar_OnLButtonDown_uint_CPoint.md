# COleResizeBar::OnLButtonDown(uint,CPoint)

- ea: `0x1800b4da0`
- end: `0x1800b4eb9`
- name: `?OnLButtonDown@COleResizeBar@@IEAAXIVCPoint@@@Z`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180011a40`
- `0x180011c90`
- `0x180011e80`
- `0x1800206b0`
- `0x180020710`
- `0x1800509c0`
- `0x1800b4da0`
- `0x1800d1fe0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800b4e98`
- `USER32!SendMessageW` at `0x1800b4e98`
- `USER32!GetDlgCtrlID` at `0x1800b4e80`
- `USER32!GetDlgCtrlID` at `0x1800b4e80`
- `USER32!GetClientRect` at `0x1800b4df8`
- `USER32!GetClientRect` at `0x1800b4df8`
- `USER32!UpdateWindow` at `0x1800b4dda`
- `USER32!UpdateWindow` at `0x1800b4de9`
- `USER32!UpdateWindow` at `0x1800b4dda`
- `USER32!UpdateWindow` at `0x1800b4de9`
- `USER32!ClipCursor` at `0x1800b4e10`
- `USER32!ClipCursor` at `0x1800b4e4d`
- `USER32!ClipCursor` at `0x1800b4e10`
- `USER32!ClipCursor` at `0x1800b4e4d`

## pseudocode

```c
int __fastcall COleResizeBar::OnLButtonDown(__int64 a1, __int64 a2, __int64 a3)
{
  HWND *ParentFrame; // rdi
  HWND *Parent; // rsi
  __int128 v7; // xmm6
  int v8; // eax
  __int128 v9; // xmm0
  int v10; // ebx
  int result; // eax
  HWND *Owner; // rbx
  unsigned __int16 DlgCtrlID; // ax
  LPARAM lParam[2]; // [rsp+30h] [rbp-68h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-58h] BYREF

  ParentFrame = (HWND *)CWnd::GetParentFrame((CWnd *)a1);
  Parent = (HWND *)CWnd::GetParent((CWnd *)ParentFrame);
  UpdateWindow(ParentFrame[8]);
  if ( Parent )
  {
    UpdateWindow(Parent[8]);
    GetClientRect(Parent[8], &Rect);
    CWnd::ClientToScreen((CWnd *)Parent, &Rect);
    ClipCursor(&Rect);
  }
  v7 = *(_OWORD *)(a1 + 220);
  v8 = CRectTracker::Track(a1 + 208, a1, a3, 0, Parent);
  v9 = *(_OWORD *)(a1 + 220);
  v10 = v8;
  *(_OWORD *)(a1 + 220) = v7;
  *(_OWORD *)lParam = v9;
  result = ClipCursor(0);
  if ( v10 )
  {
    Owner = (HWND *)CWnd::GetOwner((CWnd *)a1);
    CWnd::ClientToScreen((CWnd *)a1, (struct tagRECT *)lParam);
    CWnd::ScreenToClient((CWnd *)Owner, (struct tagRECT *)lParam);
    DlgCtrlID = GetDlgCtrlID(*(HWND *)(a1 + 64));
    return SendMessageW(Owner[8], 0x369u, DlgCtrlID, (LPARAM)lParam);
  }
  return result;
}

```

## disassembly

```asm
0x1800b4da0  push    rbx
0x1800b4da2  push    rbp
0x1800b4da3  push    rsi
0x1800b4da4  push    rdi
0x1800b4da5  sub     rsp, 78h
0x1800b4da9  movaps  [rsp+98h+var_38], xmm6
0x1800b4dae  mov     rax, cs:__security_cookie
0x1800b4db5  xor     rax, rsp
0x1800b4db8  mov     [rsp+98h+var_48], rax
0x1800b4dbd  mov     rbx, r8
0x1800b4dc0  mov     rbp, rcx
0x1800b4dc3  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x1800b4dc8  mov     rcx, rax; this
0x1800b4dcb  mov     rdi, rax
0x1800b4dce  call    ?GetParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetParent(void)
0x1800b4dd3  mov     rcx, [rdi+40h]; hWnd
0x1800b4dd7  mov     rsi, rax
0x1800b4dda  call    cs:__imp_UpdateWindow
0x1800b4de0  test    rsi, rsi
0x1800b4de3  jz      short loc_1800B4E16
0x1800b4de5  mov     rcx, [rsi+40h]; hWnd
0x1800b4de9  call    cs:__imp_UpdateWindow
0x1800b4def  mov     rcx, [rsi+40h]; hWnd
0x1800b4df3  lea     rdx, [rsp+98h+Rect]; lpRect
0x1800b4df8  call    cs:__imp_GetClientRect
0x1800b4dfe  lea     rdx, [rsp+98h+Rect]; struct tagRECT *
0x1800b4e03  mov     rcx, rsi; this
0x1800b4e06  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1800b4e0b  lea     rcx, [rsp+98h+Rect]; lpRect
0x1800b4e10  call    cs:__imp_ClipCursor
0x1800b4e16  lea     rcx, [rbp+0D0h]
0x1800b4e1d  mov     [rsp+98h+var_78], rsi
0x1800b4e22  movups  xmm6, xmmword ptr [rcx+0Ch]
0x1800b4e26  xor     r9d, r9d
0x1800b4e29  mov     r8, rbx
0x1800b4e2c  mov     rdx, rbp
0x1800b4e2f  call    ?Track@CRectTracker@@QEAAHPEAVCWnd@@VCPoint@@H0@Z; CRectTracker::Track(CWnd *,CPoint,int,CWnd *)
0x1800b4e34  movups  xmm0, xmmword ptr [rbp+0DCh]
0x1800b4e3b  xor     ecx, ecx; lpRect
0x1800b4e3d  mov     ebx, eax
0x1800b4e3f  movdqu  xmmword ptr [rbp+0DCh], xmm6
0x1800b4e47  movdqu  xmmword ptr [rsp+98h+lParam], xmm0
0x1800b4e4d  call    cs:__imp_ClipCursor
0x1800b4e53  test    ebx, ebx
0x1800b4e55  jz      short loc_1800B4E9E
0x1800b4e57  mov     rcx, rbp; this
0x1800b4e5a  call    ?GetOwner@CWnd@@QEBAPEAV1@XZ; CWnd::GetOwner(void)
0x1800b4e5f  lea     rdx, [rsp+98h+lParam]; struct tagRECT *
0x1800b4e64  mov     rcx, rbp; this
0x1800b4e67  mov     rbx, rax
0x1800b4e6a  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1800b4e6f  lea     rdx, [rsp+98h+lParam]; struct tagRECT *
0x1800b4e74  mov     rcx, rbx; this
0x1800b4e77  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800b4e7c  mov     rcx, [rbp+40h]; hWnd
0x1800b4e80  call    cs:__imp_GetDlgCtrlID
0x1800b4e86  mov     rcx, [rbx+40h]; hWnd
0x1800b4e8a  lea     r9, [rsp+98h+lParam]; lParam
0x1800b4e8f  movzx   r8d, ax; wParam
0x1800b4e93  mov     edx, 369h; Msg
0x1800b4e98  call    cs:__imp_SendMessageW
0x1800b4e9e  mov     rcx, [rsp+98h+var_48]
0x1800b4ea3  xor     rcx, rsp; StackCookie
0x1800b4ea6  call    __security_check_cookie
0x1800b4eab  movaps  xmm6, [rsp+98h+var_38]
0x1800b4eb0  add     rsp, 78h
0x1800b4eb4  pop     rdi
0x1800b4eb5  pop     rsi
0x1800b4eb6  pop     rbp
0x1800b4eb7  pop     rbx
0x1800b4eb8  retn
```
