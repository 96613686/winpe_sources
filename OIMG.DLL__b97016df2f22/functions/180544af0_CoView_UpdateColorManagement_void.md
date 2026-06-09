# CoView::UpdateColorManagement(void)

- ea: `0x180544af0`
- end: `0x180544d7b`
- name: `?UpdateColorManagement@CoView@@UEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(CoView *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18001db0c`
- `0x1805433e8`
- `0x180544af0`
- `0x18056bd00`

## import_xrefs

- `GDI32!GetRgnBox` at `0x180544ca9`
- `GDI32!GetRgnBox` at `0x180544ca9`
- `GDI32!CreateRectRgn` at `0x180544c02`
- `GDI32!CreateRectRgn` at `0x180544c02`
- `GDI32!DeleteObject` at `0x180544d0d`
- `GDI32!DeleteObject` at `0x180544d1c`
- `GDI32!DeleteObject` at `0x180544d0d`
- `GDI32!DeleteObject` at `0x180544d1c`
- `USER32!InvalidateRgn` at `0x180544cd7`
- `USER32!InvalidateRgn` at `0x180544cd7`
- `USER32!ClientToScreen` at `0x180544ba3`
- `USER32!ClientToScreen` at `0x180544bb8`
- `USER32!ClientToScreen` at `0x180544ba3`
- `USER32!ClientToScreen` at `0x180544bb8`
- `USER32!SetWindowLongW` at `0x180544b74`
- `USER32!SetWindowLongW` at `0x180544d32`
- `USER32!SetWindowLongW` at `0x180544b74`
- `USER32!SetWindowLongW` at `0x180544d32`
- `USER32!GetWindowLongW` at `0x180544b56`
- `USER32!GetWindowLongW` at `0x180544b56`
- `USER32!GetClientRect` at `0x180544b92`
- `USER32!GetClientRect` at `0x180544b92`
- `USER32!IsWindow` at `0x180544b29`
- `USER32!IsWindow` at `0x180544b44`
- `USER32!IsWindow` at `0x180544b29`
- `USER32!IsWindow` at `0x180544b44`

## pseudocode

```c
__int64 __fastcall CoView::UpdateColorManagement(HWND *this)
{
  char v2; // r14
  HWND v3; // rsi
  char v4; // r12
  LONG WindowLongW; // r15d
  __int64 v7; // rcx
  __int64 v8; // rdx
  HWND v9; // rdi
  __int64 v10; // rcx
  HWND *v12; // rax
  struct tagRECT v13; // xmm0
  void *v14; // rcx
  HRGN hrgn; // [rsp+20h] [rbp-59h] BYREF
  struct tagRECT rc; // [rsp+28h] [rbp-51h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-41h] BYREF
  LPARAM dwData[8]; // [rsp+50h] [rbp-29h] BYREF
  HWND v20; // [rsp+90h] [rbp+17h]

  v2 = 0;
  if ( !IsWindow(this[39]) )
    return 1;
  v3 = this[39];
  v4 = 0;
  if ( IsWindow(v3) )
  {
    WindowLongW = GetWindowLongW(v3, -20);
    if ( (WindowLongW & 0xFFBFFFFF) != WindowLongW )
    {
      SetWindowLongW(v3, -20, WindowLongW & 0xFFBFFFFF);
      v4 = 1;
    }
  }
  else
  {
    WindowLongW = (int)hrgn;
    v3 = *(HWND *)&rc.left;
  }
  GetClientRect(this[39], &Rect);
  if ( ClientToScreen(this[39], (LPPOINT)&Rect) )
    ClientToScreen(this[39], (LPPOINT)&Rect.right);
  if ( Rect.left != *((_DWORD *)this + 84)
    || Rect.top != *((_DWORD *)this + 85)
    || Rect.right != *((_DWORD *)this + 86)
    || Rect.bottom != *((_DWORD *)this + 87) )
  {
    hrgn = CreateRectRgn(0, 0, 0, 0);
    if ( (unsigned __int64)(Rect.left - (__int64)*((int *)this + 84) + 0x80000000LL) > 0xFFFFFFFF
      || (v7 = Rect.top - (__int64)*((int *)this + 85), (unsigned __int64)(v7 + 0x80000000LL) > 0xFFFFFFFF) )
    {
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    rc.left = Rect.left - *((_DWORD *)this + 84);
    v8 = (__int64)this[39];
    rc.top = v7;
    MultiMonitorMoveInvalidator::MultiMonitorMoveInvalidator((LPARAM)dwData, v8, &rc, (__int64)&hrgn);
    v9 = v20;
    v10 = *((_QWORD *)this[37] + 18);
    if ( v10 && *(HWND *)(v10 + 16) != v20 )
    {
      *(_BYTE *)(v10 + 24) = 1;
      *(_QWORD *)(v10 + 16) = v9;
    }
    *(_QWORD *)&rc.left = 0;
    *(_QWORD *)&rc.right = 0;
    GetRgnBox(hrgn, &rc);
    if ( rc.left < rc.right && rc.top < rc.bottom )
    {
      InvalidateRgn(this[39], hrgn, 0);
      v12 = this + 44;
    }
    else
    {
      v12 = this + 44;
      if ( this[44] == v9 )
      {
LABEL_28:
        v13 = Rect;
        v14 = (void *)dwData[5];
        *v12 = v9;
        *((struct tagRECT *)this + 21) = v13;
        if ( v14 )
          DeleteObject(v14);
        if ( hrgn )
          DeleteObject(hrgn);
        goto LABEL_32;
      }
    }
    v2 = 1;
    goto LABEL_28;
  }
LABEL_32:
  if ( v4 )
    SetWindowLongW(v3, -20, WindowLongW);
  if ( v2 )
  {
    *((_BYTE *)this + 401) = 1;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180544af0  mov     [rsp-8+arg_8], rbx
0x180544af5  mov     [rsp-8+arg_10], rsi
0x180544afa  push    rbp
0x180544afb  push    rdi
0x180544afc  push    r12
0x180544afe  push    r14
0x180544b00  push    r15
0x180544b02  lea     rbp, [rsp-37h]
0x180544b07  sub     rsp, 0B0h
0x180544b0e  mov     rax, cs:__security_cookie
0x180544b15  xor     rax, rsp
0x180544b18  mov     [rbp+57h+var_30], rax
0x180544b1c  mov     rbx, rcx
0x180544b1f  xor     r14b, r14b
0x180544b22  mov     rcx, [rcx+138h]; hWnd
0x180544b29  call    cs:__imp_IsWindow
0x180544b2f  test    eax, eax
0x180544b31  jz      loc_180544D48
0x180544b37  mov     rsi, [rbx+138h]
0x180544b3e  xor     r12b, r12b
0x180544b41  mov     rcx, rsi; hWnd
0x180544b44  call    cs:__imp_IsWindow
0x180544b4a  test    eax, eax
0x180544b4c  jz      short loc_180544B7F
0x180544b4e  mov     edx, 0FFFFFFECh; nIndex
0x180544b53  mov     rcx, rsi; hWnd
0x180544b56  call    cs:__imp_GetWindowLongW
0x180544b5c  mov     r8d, eax
0x180544b5f  mov     r15d, eax
0x180544b62  btr     r8d, 16h; dwNewLong
0x180544b67  cmp     r8d, eax
0x180544b6a  jz      short loc_180544B87
0x180544b6c  mov     edx, 0FFFFFFECh; nIndex
0x180544b71  mov     rcx, rsi; hWnd
0x180544b74  call    cs:__imp_SetWindowLongW
0x180544b7a  mov     r12b, 1
0x180544b7d  jmp     short loc_180544B87
0x180544b7f  mov     r15d, dword ptr [rbp+57h+hrgn]
0x180544b83  mov     rsi, qword ptr [rbp+57h+rc.left]
0x180544b87  mov     rcx, [rbx+138h]; hWnd
0x180544b8e  lea     rdx, [rbp+57h+Rect]; lpRect
0x180544b92  call    cs:__imp_GetClientRect
0x180544b98  mov     rcx, [rbx+138h]; hWnd
0x180544b9f  lea     rdx, [rbp+57h+Rect]; lpPoint
0x180544ba3  call    cs:__imp_ClientToScreen
0x180544ba9  test    eax, eax
0x180544bab  jz      short loc_180544BBE
0x180544bad  mov     rcx, [rbx+138h]; hWnd
0x180544bb4  lea     rdx, [rbp+57h+Rect.right]; lpPoint
0x180544bb8  call    cs:__imp_ClientToScreen
0x180544bbe  mov     eax, [rbx+150h]
0x180544bc4  cmp     [rbp+57h+Rect.left], eax
0x180544bc7  jnz     short loc_180544BEE
0x180544bc9  mov     eax, [rbx+154h]
0x180544bcf  cmp     [rbp+57h+Rect.top], eax
0x180544bd2  jnz     short loc_180544BEE
0x180544bd4  mov     eax, [rbx+158h]
0x180544bda  cmp     [rbp+57h+Rect.right], eax
0x180544bdd  jnz     short loc_180544BEE
0x180544bdf  mov     eax, [rbx+15Ch]
0x180544be5  cmp     [rbp+57h+Rect.bottom], eax
0x180544be8  jnz     short loc_180544BEE
0x180544bea  xor     al, al
0x180544bec  jmp     short loc_180544BF0
0x180544bee  mov     al, 1
0x180544bf0  test    al, al
0x180544bf2  jz      loc_180544D22
0x180544bf8  xor     r9d, r9d; y2
0x180544bfb  xor     r8d, r8d; x2
0x180544bfe  xor     edx, edx; y1
0x180544c00  xor     ecx, ecx; x1
0x180544c02  call    cs:__imp_CreateRectRgn
0x180544c08  movsxd  rdx, [rbp+57h+Rect.left]
0x180544c0c  mov     r8d, 80000000h
0x180544c12  mov     [rbp+57h+hrgn], rax
0x180544c16  mov     r9d, 0FFFFFFFFh
0x180544c1c  movsxd  rax, dword ptr [rbx+150h]
0x180544c23  sub     rdx, rax
0x180544c26  lea     rax, [rdx+r8]
0x180544c2a  cmp     rax, r9
0x180544c2d  ja      loc_180544D75
0x180544c33  movsxd  rax, dword ptr [rbx+154h]
0x180544c3a  movsxd  rcx, [rbp+57h+Rect.top]
0x180544c3e  sub     rcx, rax
0x180544c41  lea     rax, [r8+rcx]
0x180544c45  cmp     rax, r9
0x180544c48  ja      loc_180544D75
0x180544c4e  mov     [rbp+57h+rc.left], edx
0x180544c51  lea     r9, [rbp+57h+hrgn]
0x180544c55  mov     rdx, [rbx+138h]
0x180544c5c  lea     r8, [rbp+57h+rc]
0x180544c60  mov     [rbp+57h+rc.top], ecx
0x180544c63  lea     rcx, [rbp+57h+dwData]; dwData
0x180544c67  call    ??0MultiMonitorMoveInvalidator@@QEAA@PEAUHWND__@@AEBU?$PointT@UIntegerTypes@@@@PEAVRegion@@@Z; MultiMonitorMoveInvalidator::MultiMonitorMoveInvalidator(HWND__ *,PointT<IntegerTypes> const &,Region *)
0x180544c6c  mov     rax, [rbx+128h]
0x180544c73  mov     rdi, [rbp+57h+var_40]
0x180544c77  mov     rcx, [rax+90h]
0x180544c7e  test    rcx, rcx
0x180544c81  jz      short loc_180544C91
0x180544c83  cmp     [rcx+10h], rdi
0x180544c87  jz      short loc_180544C91
0x180544c89  mov     byte ptr [rcx+18h], 1
0x180544c8d  mov     [rcx+10h], rdi
0x180544c91  mov     rcx, [rbp+57h+hrgn]; hrgn
0x180544c95  lea     rdx, [rbp+57h+rc]; lprc
0x180544c99  mov     qword ptr [rbp+57h+rc.left], 0
0x180544ca1  mov     qword ptr [rbp+57h+rc.right], 0
0x180544ca9  call    cs:__imp_GetRgnBox
0x180544caf  mov     eax, [rbp+57h+rc.right]
0x180544cb2  cmp     [rbp+57h+rc.left], eax
0x180544cb5  jge     short loc_180544CC3
0x180544cb7  mov     eax, [rbp+57h+rc.bottom]
0x180544cba  cmp     [rbp+57h+rc.top], eax
0x180544cbd  jge     short loc_180544CC3
0x180544cbf  mov     al, 1
0x180544cc1  jmp     short loc_180544CC5
0x180544cc3  xor     al, al
0x180544cc5  test    al, al
0x180544cc7  jz      short loc_180544CE6
0x180544cc9  mov     rdx, [rbp+57h+hrgn]; hRgn
0x180544ccd  xor     r8d, r8d; bErase
0x180544cd0  mov     rcx, [rbx+138h]; hWnd
0x180544cd7  call    cs:__imp_InvalidateRgn
0x180544cdd  lea     rax, [rbx+160h]
0x180544ce4  jmp     short loc_180544CF2
0x180544ce6  lea     rax, [rbx+160h]
0x180544ced  cmp     [rax], rdi
0x180544cf0  jz      short loc_180544CF5
0x180544cf2  mov     r14b, 1
0x180544cf5  movups  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x180544cf9  mov     rcx, [rbp+57h+ho]; ho
0x180544cfd  mov     [rax], rdi
0x180544d00  movdqu  xmmword ptr [rbx+150h], xmm0
0x180544d08  test    rcx, rcx
0x180544d0b  jz      short loc_180544D13
0x180544d0d  call    cs:__imp_DeleteObject
0x180544d13  mov     rcx, [rbp+57h+hrgn]; ho
0x180544d17  test    rcx, rcx
0x180544d1a  jz      short loc_180544D22
0x180544d1c  call    cs:__imp_DeleteObject
0x180544d22  test    r12b, r12b
0x180544d25  jz      short loc_180544D38
0x180544d27  mov     r8d, r15d; dwNewLong
0x180544d2a  mov     edx, 0FFFFFFECh; nIndex
0x180544d2f  mov     rcx, rsi; hWnd
0x180544d32  call    cs:__imp_SetWindowLongW
0x180544d38  test    r14b, r14b
0x180544d3b  jz      short loc_180544D48
0x180544d3d  mov     byte ptr [rbx+191h], 1
0x180544d44  xor     eax, eax
0x180544d46  jmp     short loc_180544D4D
0x180544d48  mov     eax, 1
0x180544d4d  mov     rcx, [rbp+57h+var_30]
0x180544d51  xor     rcx, rsp; StackCookie
0x180544d54  call    __security_check_cookie
0x180544d59  lea     r11, [rsp+0D0h+var_20]
0x180544d61  mov     rbx, [r11+38h]
0x180544d65  mov     rsi, [r11+40h]
0x180544d69  mov     rsp, r11
0x180544d6c  pop     r15
0x180544d6e  pop     r14
0x180544d70  pop     r12
0x180544d72  pop     rdi
0x180544d73  pop     rbp
0x180544d74  retn
0x180544d75  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
```
