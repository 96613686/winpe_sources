# CTouchSelectionHandle::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1801ffbe8`
- end: `0x1801ffe2f`
- name: `?WndProc@CTouchSelectionHandle@@IEAA_JPEAUHWND__@@I_K_J@Z`
- size: `583`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM lParam)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1801fd030`

## callees

- `0x1800d0ce8`
- `0x18013bad0`
- `0x18013c916`
- `0x1801fab54`
- `0x1801faba0`
- `0x1801fc570`
- `0x1801fd0d4`
- `0x1801fd354`
- `0x1801fea58`
- `0x1801fed50`
- `0x1801ff9b8`
- `0x1801ffbe8`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1801ffdc9`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1801ffdc9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongW` at `0x1801ffcba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1801ffc97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1801ffc97`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x1801ffce8`
- `ext-ms-win-ntuser-draw-l1-1-0!GetUpdateRect` at `0x1801ffce8`

## pseudocode

```c
LRESULT __fastcall CTouchSelectionHandle::WndProc(
        CTouchSelectionHandle *this,
        HWND hWnd,
        unsigned int a3,
        unsigned __int64 a4,
        LPARAM lParam)
{
  _BOOL8 v9; // rcx
  __int64 v10; // rax
  LONG WindowLongW; // ebx
  HDC v12; // rbx
  bool v13; // r8
  unsigned int v15; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-A4h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v18[80]; // [rsp+70h] [rbp-88h] BYREF

  v9 = CTouchTracker::HandleTouchWindowMessage(this, a3, a4, a4);
  v10 = *((_QWORD *)this + 15);
  if ( v10 && a3 == *(_DWORD *)(v10 + 64) )
  {
    CTouchSelectionHandle::Show(this, (struct tagPOINT *)this + 7, *((_BYTE *)this + 112), 1);
    return 0;
  }
  if ( a3 > 0x21 )
  {
    if ( a3 == 256 || a3 == 513 || a3 == 516 || a3 == 519 )
    {
      ShowGrippersCore(0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      return 0;
    }
    if ( a3 != 587 )
      goto LABEL_22;
    return 3;
  }
  switch ( a3 )
  {
    case 0x21u:
      return 3;
    case 1u:
      (*(void (__fastcall **)(CTouchSelectionHandle *))(*(_QWORD *)this + 8LL))(this);
      CTouchSelectionHandle::InitializeAnimation(this);
      return 0;
    case 2u:
      CTouchSelectionHandle::CleanUpAnimationController(this);
      return 0;
    case 0xFu:
      Rect = 0;
      if ( GetUpdateRect(hWnd, &Rect, 0) )
      {
        memset_0(v18, 0, 0x48u);
        v16 = 0;
        v15 = 0;
        v12 = (HDC)((__int64 (__fastcall *)(HWND, _BYTE *))g_pfnBeginPaint)(hWnd, v18);
        CTouchSelectionHandle::GetGripperColorsFromTextHost(this, &v16, &v15);
        CTouchSelectionHandle::RenderHandle(this, v12, v13, v16, v15);
        ((void (__fastcall *)(HWND, _BYTE *))g_pfnEndPaint)(hWnd, v18);
      }
      return 0;
    case 0x15u:
    case 0x1Au:
      CTouchSelectionHandle::CheckGripperBitmapColors(this);
      if ( *((_BYTE *)this + 100) )
      {
        WindowLongW = GetWindowLongW(hWnd, -20);
        SetWindowLongW(hWnd, -20, WindowLongW & 0xFFF7FFFF);
        SetWindowLongW(hWnd, -20, WindowLongW);
        CTouchSelectionHandle::UpdateLayeredWindow(this, 0, 0xFFu);
      }
      return 0;
  }
LABEL_22:
  if ( v9 )
    return !v9;
  else
    return DefWindowProcW(hWnd, a3, a4, lParam);
}

```

## disassembly

```asm
0x1801ffbe8  push    rbx
0x1801ffbea  push    rbp
0x1801ffbeb  push    rsi
0x1801ffbec  push    rdi
0x1801ffbed  sub     rsp, 0D8h
0x1801ffbf4  mov     rax, cs:__security_cookie
0x1801ffbfb  xor     rax, rsp
0x1801ffbfe  mov     [rsp+0F8h+var_38], rax
0x1801ffc06  mov     ebx, r8d
0x1801ffc09  mov     rsi, rdx
0x1801ffc0c  mov     edx, ebx; unsigned int
0x1801ffc0e  mov     r8, r9; unsigned __int64
0x1801ffc11  mov     rbp, r9
0x1801ffc14  mov     rdi, rcx
0x1801ffc17  call    ?HandleTouchWindowMessage@CTouchTracker@@QEAA_NI_K_J@Z; CTouchTracker::HandleTouchWindowMessage(uint,unsigned __int64,__int64)
0x1801ffc1c  movzx   ecx, al
0x1801ffc1f  mov     rax, [rdi+78h]
0x1801ffc23  test    rax, rax
0x1801ffc26  jz      short loc_1801FFC45
0x1801ffc28  cmp     ebx, [rax+40h]
0x1801ffc2b  jnz     short loc_1801FFC45
0x1801ffc2d  mov     r8b, [rdi+70h]; bool
0x1801ffc31  lea     rdx, [rdi+38h]; struct tagPOINT *
0x1801ffc35  mov     r9b, 1; bool
0x1801ffc38  mov     rcx, rdi; this
0x1801ffc3b  call    ?Show@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@_N1@Z; CTouchSelectionHandle::Show(tagPOINT *,bool,bool)
0x1801ffc40  jmp     loc_1801FFE11
0x1801ffc45  cmp     ebx, 21h ; '!'
0x1801ffc48  ja      loc_1801FFD96
0x1801ffc4e  jz      loc_1801FFDDA
0x1801ffc54  mov     eax, ebx
0x1801ffc56  sub     eax, 1
0x1801ffc59  jz      loc_1801FFD7D
0x1801ffc5f  sub     eax, 1
0x1801ffc62  jz      loc_1801FFD70
0x1801ffc68  sub     eax, 0Dh
0x1801ffc6b  jz      short loc_1801FFCD5
0x1801ffc6d  sub     eax, 6
0x1801ffc70  jz      short loc_1801FFC7B
0x1801ffc72  cmp     eax, 5
0x1801ffc75  jnz     loc_1801FFDB5
0x1801ffc7b  mov     rcx, rdi; this
0x1801ffc7e  call    ?CheckGripperBitmapColors@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::CheckGripperBitmapColors(void)
0x1801ffc83  cmp     byte ptr [rdi+64h], 0
0x1801ffc87  jz      loc_1801FFE11
0x1801ffc8d  mov     ebp, 0FFFFFFECh
0x1801ffc92  mov     rcx, rsi; hWnd
0x1801ffc95  mov     edx, ebp; nIndex
0x1801ffc97  call    cs:__imp_GetWindowLongW
0x1801ffc9d  mov     edx, ebp; nIndex
0x1801ffc9f  mov     rcx, rsi; hWnd
0x1801ffca2  mov     r8d, eax
0x1801ffca5  mov     ebx, eax
0x1801ffca7  btr     r8d, 13h; dwNewLong
0x1801ffcac  call    cs:__imp_SetWindowLongW
0x1801ffcb2  mov     r8d, ebx; dwNewLong
0x1801ffcb5  mov     edx, ebp; nIndex
0x1801ffcb7  mov     rcx, rsi; hWnd
0x1801ffcba  call    cs:__imp_SetWindowLongW
0x1801ffcc0  xor     edx, edx; pptDst
0x1801ffcc2  mov     r8d, 0FFh; int
0x1801ffcc8  mov     rcx, rdi; this
0x1801ffccb  call    ?UpdateLayeredWindow@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@H@Z; CTouchSelectionHandle::UpdateLayeredWindow(tagPOINT *,int)
0x1801ffcd0  jmp     loc_1801FFE11
0x1801ffcd5  xorps   xmm0, xmm0
0x1801ffcd8  lea     rdx, [rsp+0F8h+Rect]; lpRect
0x1801ffcdd  xor     r8d, r8d; bErase
0x1801ffce0  mov     rcx, rsi; hWnd
0x1801ffce3  movups  xmmword ptr [rsp+0F8h+Rect.left], xmm0
0x1801ffce8  call    cs:__imp_GetUpdateRect
0x1801ffcee  test    eax, eax
0x1801ffcf0  jz      loc_1801FFE11
0x1801ffcf6  xor     edx, edx; Val
0x1801ffcf8  lea     rcx, [rsp+0F8h+var_88]; void *
0x1801ffcfd  lea     r8d, [rdx+48h]; Size
0x1801ffd01  call    memset_0
0x1801ffd06  mov     rax, cs:?g_pfnBeginPaint@@3P6A_JXZEA; __int64 (*g_pfnBeginPaint)(void)
0x1801ffd0d  lea     rdx, [rsp+0F8h+var_88]
0x1801ffd12  mov     rcx, rsi
0x1801ffd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffd1a  lea     r8, [rsp+0F8h+var_A8]; unsigned int *
0x1801ffd1f  mov     [rsp+0F8h+var_A4], 0
0x1801ffd27  lea     rdx, [rsp+0F8h+var_A4]; unsigned int *
0x1801ffd2c  mov     [rsp+0F8h+var_A8], 0
0x1801ffd34  mov     rcx, rdi; this
0x1801ffd37  mov     rbx, rax
0x1801ffd3a  call    ?GetGripperColorsFromTextHost@CTouchSelectionHandle@@IEBAXAEAK0@Z; CTouchSelectionHandle::GetGripperColorsFromTextHost(ulong &,ulong &)
0x1801ffd3f  mov     ecx, [rsp+0F8h+var_A8]
0x1801ffd43  mov     rdx, rbx; HDC
0x1801ffd46  mov     r9d, [rsp+0F8h+var_A4]; unsigned int
0x1801ffd4b  mov     dword ptr [rsp+0F8h+var_D8], ecx; unsigned int
0x1801ffd4f  mov     rcx, rdi; this
0x1801ffd52  call    ?RenderHandle@CTouchSelectionHandle@@IEBAXPEAUHDC__@@_NKK@Z; CTouchSelectionHandle::RenderHandle(HDC__ *,bool,ulong,ulong)
0x1801ffd57  mov     rax, cs:?g_pfnEndPaint@@3P6A_JXZEA; __int64 (*g_pfnEndPaint)(void)
0x1801ffd5e  lea     rdx, [rsp+0F8h+var_88]
0x1801ffd63  mov     rcx, rsi
0x1801ffd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffd6b  jmp     loc_1801FFE11
0x1801ffd70  mov     rcx, rdi; this
0x1801ffd73  call    ?CleanUpAnimationController@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::CleanUpAnimationController(void)
0x1801ffd78  jmp     loc_1801FFE11
0x1801ffd7d  mov     rax, [rdi]
0x1801ffd80  mov     rcx, rdi
0x1801ffd83  mov     rax, [rax+8]
0x1801ffd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ffd8c  mov     rcx, rdi; this
0x1801ffd8f  call    ?InitializeAnimation@CTouchSelectionHandle@@IEAAJXZ; CTouchSelectionHandle::InitializeAnimation(void)
0x1801ffd94  jmp     short loc_1801FFE11
0x1801ffd96  mov     eax, ebx
0x1801ffd98  sub     eax, 100h
0x1801ffd9d  jz      short loc_1801FFDE1
0x1801ffd9f  sub     eax, 101h
0x1801ffda4  jz      short loc_1801FFDE1
0x1801ffda6  sub     eax, 3
0x1801ffda9  jz      short loc_1801FFDE1
0x1801ffdab  sub     eax, 3
0x1801ffdae  jz      short loc_1801FFDE1
0x1801ffdb0  cmp     eax, 44h ; 'D'
0x1801ffdb3  jz      short loc_1801FFDDA
0x1801ffdb5  test    cl, cl
0x1801ffdb7  jnz     short loc_1801FFDD1
0x1801ffdb9  mov     r9, [rsp+0F8h+lParam]; lParam
0x1801ffdc1  mov     r8, rbp; wParam
0x1801ffdc4  mov     edx, ebx; Msg
0x1801ffdc6  mov     rcx, rsi; hWnd
0x1801ffdc9  call    cs:__imp_DefWindowProcW
0x1801ffdcf  jmp     short loc_1801FFE13
0x1801ffdd1  mov     rax, rcx
0x1801ffdd4  xor     rax, 1
0x1801ffdd8  jmp     short loc_1801FFE13
0x1801ffdda  mov     eax, 3
0x1801ffddf  jmp     short loc_1801FFE13
0x1801ffde1  mov     [rsp+0F8h+var_B0], 0; unsigned int
0x1801ffde9  xor     r9d, r9d; struct tagPOINT *
0x1801ffdec  mov     [rsp+0F8h+var_B8], 0; bool
0x1801ffdf1  xor     r8d, r8d; struct tagPOINT *
0x1801ffdf4  mov     [rsp+0F8h+var_C0], 0; bool
0x1801ffdf9  xor     edx, edx; HWND
0x1801ffdfb  mov     [rsp+0F8h+var_C8], 0; bool
0x1801ffe00  xor     ecx, ecx; struct ITouchSelectionHandlesHost *
0x1801ffe02  mov     [rsp+0F8h+var_D0], 0; bool
0x1801ffe07  mov     [rsp+0F8h+var_D8], 0; bool
0x1801ffe0c  call    ?ShowGrippersCore@@YAJPEAUITouchSelectionHandlesHost@@PEAUHWND__@@PEAUtagPOINT@@2_N3333I@Z; ShowGrippersCore(ITouchSelectionHandlesHost *,HWND__ *,tagPOINT *,tagPOINT *,bool,bool,bool,bool,bool,uint)
0x1801ffe11  xor     eax, eax
0x1801ffe13  mov     rcx, [rsp+0F8h+var_38]
0x1801ffe1b  xor     rcx, rsp; StackCookie
0x1801ffe1e  call    __security_check_cookie
0x1801ffe23  add     rsp, 0D8h
0x1801ffe2a  pop     rdi
0x1801ffe2b  pop     rsi
0x1801ffe2c  pop     rbp
0x1801ffe2d  pop     rbx
0x1801ffe2e  retn
```
