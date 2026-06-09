# CInkCollector::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x1800ad9a8`
- end: `0x1800add30`
- name: `?OnPaint@CInkCollector@@QEAA_JI_K_JAEAH@Z`
- size: `904`
- prototype: `__int64 __usercall@<rax>(CInkCollector *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e410`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x1800ad9a8`
- `0x1800b0d54`
- `0x1800b1810`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800adacb`
- `USER32!IsRectEmpty` at `0x1800adacb`
- `USER32!GetUpdateRgn` at `0x1800adaaa`
- `USER32!GetUpdateRgn` at `0x1800adaaa`
- `USER32!CallWindowProcW` at `0x1800adb81`
- `USER32!CallWindowProcW` at `0x1800adb81`
- `USER32!GetDC` at `0x1800ada0b`
- `USER32!GetDC` at `0x1800adb8b`
- `USER32!GetDC` at `0x1800ada0b`
- `USER32!GetDC` at `0x1800adb8b`
- `USER32!ReleaseDC` at `0x1800adb3e`
- `USER32!ReleaseDC` at `0x1800adcc2`
- `USER32!ReleaseDC` at `0x1800adb3e`
- `USER32!ReleaseDC` at `0x1800adcc2`
- `USER32!MapWindowPoints` at `0x1800adc23`
- `USER32!MapWindowPoints` at `0x1800adc23`
- `GDI32!SetMapMode` at `0x1800ada2a`
- `GDI32!SetMapMode` at `0x1800ada2a`
- `GDI32!OffsetRgn` at `0x1800adc3b`
- `GDI32!OffsetRgn` at `0x1800adc3b`
- `GDI32!GetRandomRgn` at `0x1800ada79`
- `GDI32!GetRandomRgn` at `0x1800adbe3`
- `GDI32!GetRandomRgn` at `0x1800ada79`
- `GDI32!GetRandomRgn` at `0x1800adbe3`
- `GDI32!CombineRgn` at `0x1800adb0f`
- `GDI32!CombineRgn` at `0x1800adbf8`
- `GDI32!CombineRgn` at `0x1800adc50`
- `GDI32!CombineRgn` at `0x1800adc6a`
- `GDI32!CombineRgn` at `0x1800adb0f`
- `GDI32!CombineRgn` at `0x1800adbf8`
- `GDI32!CombineRgn` at `0x1800adc50`
- `GDI32!CombineRgn` at `0x1800adc6a`
- `GDI32!SelectClipRgn` at `0x1800adc76`
- `GDI32!SelectClipRgn` at `0x1800adc76`
- `GDI32!CreateRectRgn` at `0x1800ada5c`
- `GDI32!CreateRectRgn` at `0x1800ada89`
- `GDI32!CreateRectRgn` at `0x1800adaed`
- `GDI32!CreateRectRgn` at `0x1800adbae`
- `GDI32!CreateRectRgn` at `0x1800ada5c`
- `GDI32!CreateRectRgn` at `0x1800ada89`
- `GDI32!CreateRectRgn` at `0x1800adaed`
- `GDI32!CreateRectRgn` at `0x1800adbae`
- `GDI32!RestoreDC` at `0x1800adb31`
- `GDI32!RestoreDC` at `0x1800adcb5`
- `GDI32!RestoreDC` at `0x1800adb31`
- `GDI32!RestoreDC` at `0x1800adcb5`
- `GDI32!SetViewportOrgEx` at `0x1800ada3b`
- `GDI32!SetViewportOrgEx` at `0x1800ada3b`
- `GDI32!SetWindowOrgEx` at `0x1800ada4c`
- `GDI32!SetWindowOrgEx` at `0x1800ada4c`
- `GDI32!SaveDC` at `0x1800ada17`
- `GDI32!SaveDC` at `0x1800adb97`
- `GDI32!SaveDC` at `0x1800ada17`
- `GDI32!SaveDC` at `0x1800adb97`
- `GDI32!DeleteObject` at `0x1800adcee`
- `GDI32!DeleteObject` at `0x1800adcfc`
- `GDI32!DeleteObject` at `0x1800add0a`
- `GDI32!DeleteObject` at `0x1800add18`
- `GDI32!DeleteObject` at `0x1800adcee`
- `GDI32!DeleteObject` at `0x1800adcfc`
- `GDI32!DeleteObject` at `0x1800add0a`
- `GDI32!DeleteObject` at `0x1800add18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkCollector::OnPaint(CInkCollector *this, UINT a2, WPARAM a3, LPARAM a4, int *nSavedDC)
{
  LPARAM v5; // r12
  int *v7; // r13
  HRGN v8; // r15
  HRGN v9; // rbx
  HRGN v10; // rsi
  HRGN v11; // r14
  HDC DC; // rsi
  HRGN RectRgn; // rax
  HRGN v14; // rax
  HRGN v15; // rax
  HDC v16; // r12
  HRGN v17; // rax
  struct IInkStrokes *v18; // r8
  int lParam; // [rsp+20h] [rbp-78h]
  struct IInkRenderer *v21; // [rsp+28h] [rbp-70h]
  HRGN v22; // [rsp+30h] [rbp-68h]
  HRGN v24; // [rsp+38h] [rbp-60h]
  HRGN v26; // [rsp+40h] [rbp-58h]
  HRGN v28; // [rsp+48h] [rbp-50h]
  _BYTE v30[72]; // [rsp+50h] [rbp-48h] BYREF
  struct tagPOINT Points; // [rsp+A0h] [rbp+8h] BYREF
  UINT Msg; // [rsp+A8h] [rbp+10h]
  WPARAM wParam; // [rsp+B0h] [rbp+18h]
  LPARAM v34; // [rsp+B8h] [rbp+20h]

  v34 = a4;
  wParam = a3;
  Msg = a2;
  try
  {
    v5 = a4;
    v7 = nSavedDC;
    *nSavedDC = 0;
    v8 = 0;
    v22 = 0;
    v9 = 0;
    v24 = 0;
    v10 = 0;
    v26 = 0;
    v11 = 0;
    v28 = 0;
    if ( *((_WORD *)this + 193) == 0xFFFF )
    {
      DC = GetDC(*((HWND *)this + 7));
      LODWORD(nSavedDC) = SaveDC(DC);
      SetMapMode(DC, 1);
      SetViewportOrgEx(DC, 0, 0, 0);
      SetWindowOrgEx(DC, 0, 0, 0);
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v8 = RectRgn;
      v22 = RectRgn;
      if ( RectRgn )
        GetRandomRgn(DC, RectRgn, 4);
      v14 = CreateRectRgn(0, 0, 0, 0);
      v9 = v14;
      v24 = v14;
      if ( v14 )
      {
        GetUpdateRgn(*((HWND *)this + 7), v14, 0);
        CInkAutoDataLock::CInkAutoDataLock(
          (CInkAutoDataLock *)v30,
          (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
        if ( !IsRectEmpty((const RECT *)this + 21) )
        {
          v15 = CreateRectRgn(
                  *((_DWORD *)this + 84),
                  *((_DWORD *)this + 85),
                  *((_DWORD *)this + 86),
                  *((_DWORD *)this + 87));
          v11 = v15;
          v28 = v15;
          if ( v15 )
            CombineRgn(v9, v9, v15, 1);
        }
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v30);
        v5 = v34;
      }
      RestoreDC(DC, (int)nSavedDC);
      ReleaseDC(*((HWND *)this + 7), DC);
      if ( v9 )
        CInkCollector::_InvalidateWindow(this, 0, v9, 1, 0);
      CallWindowProcW(*((WNDPROC *)this + 13), *((HWND *)this + 7), Msg, wParam, v5);
      v16 = GetDC(*((HWND *)this + 7));
      LODWORD(nSavedDC) = SaveDC(v16);
      v17 = CreateRectRgn(0, 0, 0, 0);
      v10 = v17;
      v26 = v17;
      if ( v17 && v8 && v9 )
      {
        GetRandomRgn(v16, v17, 4);
        if ( (unsigned int)CombineRgn(v10, v10, v8, 4) > 1 )
        {
          Points = 0;
          MapWindowPoints(0, *((HWND *)this + 7), &Points, 1u);
          OffsetRgn(v10, Points.x, Points.y);
          CombineRgn(v9, v9, v10, 2);
          if ( v11 )
            CombineRgn(v9, v9, v11, 1);
        }
        SelectClipRgn(v16, v9);
        CInkAutoDataLock::CInkAutoDataLock(
          (CInkAutoDataLock *)v30,
          (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
        CInkCollector::_DrawStrokes(this, v16, v18, *((_DWORD *)this + 99), lParam, v21);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v30);
      }
      RestoreDC(v16, (int)nSavedDC);
      ReleaseDC(*((HWND *)this + 7), v16);
      *v7 = 1;
    }
  }
  catch ( ... )
  {
    ReportWispException();
    v8 = v22;
    v9 = v24;
    v10 = v26;
    v11 = v28;
  }
  if ( v8 )
    DeleteObject(v8);
  if ( v9 )
    DeleteObject(v9);
  if ( v10 )
    DeleteObject(v10);
  if ( v11 )
    DeleteObject(v11);
  return 0;
}

```

## disassembly

```asm
0x1800ad9a8  mov     [rsp+arg_18], r9
0x1800ad9ad  mov     [rsp+wParam], r8
0x1800ad9b2  mov     [rsp+Msg], edx
0x1800ad9b6  push    rbx
0x1800ad9b7  push    rsi
0x1800ad9b8  push    rdi
0x1800ad9b9  push    r12
0x1800ad9bb  push    r13
0x1800ad9bd  push    r14
0x1800ad9bf  push    r15
0x1800ad9c1  sub     rsp, 60h
0x1800ad9c5  mov     r12, r9
0x1800ad9c8  mov     rdi, rcx
0x1800ad9cb  mov     r13, qword ptr [rsp+98h+nSavedDC]
0x1800ad9d3  mov     dword ptr [r13+0], 0
0x1800ad9db  xor     r15d, r15d
0x1800ad9de  mov     [rsp+98h+var_68], r15
0x1800ad9e3  xor     ebx, ebx
0x1800ad9e5  mov     [rsp+98h+var_60], rbx
0x1800ad9ea  xor     esi, esi
0x1800ad9ec  mov     [rsp+98h+var_58], rsi
0x1800ad9f1  xor     r14d, r14d
0x1800ad9f4  mov     [rsp+98h+var_50], r14
0x1800ad9f9  cmp     word ptr [rcx+182h], 0FFFFh
0x1800ada01  jnz     loc_1800ADCD0
0x1800ada07  mov     rcx, [rcx+38h]; hWnd
0x1800ada0b  call    cs:__imp_GetDC
0x1800ada11  mov     rsi, rax
0x1800ada14  mov     rcx, rax; hdc
0x1800ada17  call    cs:__imp_SaveDC
0x1800ada1d  mov     [rsp+98h+nSavedDC], eax
0x1800ada24  lea     edx, [rbx+1]; iMode
0x1800ada27  mov     rcx, rsi; hdc
0x1800ada2a  call    cs:__imp_SetMapMode
0x1800ada30  xor     r9d, r9d; lppt
0x1800ada33  xor     r8d, r8d; y
0x1800ada36  xor     edx, edx; x
0x1800ada38  mov     rcx, rsi; hdc
0x1800ada3b  call    cs:__imp_SetViewportOrgEx
0x1800ada41  xor     r9d, r9d; lppt
0x1800ada44  xor     r8d, r8d; y
0x1800ada47  xor     edx, edx; x
0x1800ada49  mov     rcx, rsi; hdc
0x1800ada4c  call    cs:__imp_SetWindowOrgEx
0x1800ada52  xor     r9d, r9d; y2
0x1800ada55  xor     r8d, r8d; x2
0x1800ada58  xor     edx, edx; y1
0x1800ada5a  xor     ecx, ecx; x1
0x1800ada5c  call    cs:__imp_CreateRectRgn
0x1800ada62  mov     r15, rax
0x1800ada65  mov     [rsp+98h+var_68], rax
0x1800ada6a  test    rax, rax
0x1800ada6d  jz      short loc_1800ADA7F
0x1800ada6f  lea     r8d, [rbx+4]; i
0x1800ada73  mov     rdx, rax; hrgn
0x1800ada76  mov     rcx, rsi; hdc
0x1800ada79  call    cs:__imp_GetRandomRgn
0x1800ada7f  xor     r9d, r9d; y2
0x1800ada82  xor     r8d, r8d; x2
0x1800ada85  xor     edx, edx; y1
0x1800ada87  xor     ecx, ecx; x1
0x1800ada89  call    cs:__imp_CreateRectRgn
0x1800ada8f  mov     rbx, rax
0x1800ada92  mov     [rsp+98h+var_60], rax
0x1800ada97  test    rax, rax
0x1800ada9a  jz      loc_1800ADB27
0x1800adaa0  xor     r8d, r8d; bErase
0x1800adaa3  mov     rdx, rax; hRgn
0x1800adaa6  mov     rcx, [rdi+38h]; hWnd
0x1800adaaa  call    cs:__imp_GetUpdateRgn
0x1800adab0  lea     rdx, [rdi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800adab7  lea     rcx, [rsp+98h+var_48]; this
0x1800adabc  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800adac1  lea     r12, [rdi+150h]
0x1800adac8  mov     rcx, r12; lprc
0x1800adacb  call    cs:__imp_IsRectEmpty
0x1800adad1  test    eax, eax
0x1800adad3  jnz     short loc_1800ADB15
0x1800adad5  mov     r9d, [rdi+15Ch]; y2
0x1800adadc  mov     r8d, [rdi+158h]; x2
0x1800adae3  mov     edx, [rdi+154h]; y1
0x1800adae9  mov     ecx, [r12]; x1
0x1800adaed  call    cs:__imp_CreateRectRgn
0x1800adaf3  mov     r14, rax
0x1800adaf6  mov     [rsp+98h+var_50], rax
0x1800adafb  test    rax, rax
0x1800adafe  jz      short loc_1800ADB15
0x1800adb00  mov     r9d, 1; iMode
0x1800adb06  mov     r8, rax; hrgnSrc2
0x1800adb09  mov     rdx, rbx; hrgnSrc1
0x1800adb0c  mov     rcx, rbx; hrgnDst
0x1800adb0f  call    cs:__imp_CombineRgn
0x1800adb15  lea     rcx, [rsp+98h+var_48]; this
0x1800adb1a  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800adb1f  mov     r12, [rsp+98h+arg_18]
0x1800adb27  mov     edx, [rsp+98h+nSavedDC]; nSavedDC
0x1800adb2e  mov     rcx, rsi; hdc
0x1800adb31  call    cs:__imp_RestoreDC
0x1800adb37  mov     rdx, rsi; hDC
0x1800adb3a  mov     rcx, [rdi+38h]; hWnd
0x1800adb3e  call    cs:__imp_ReleaseDC
0x1800adb44  test    rbx, rbx
0x1800adb47  jz      short loc_1800ADB64
0x1800adb49  mov     dword ptr [rsp+98h+lParam], 0; int
0x1800adb51  mov     r9d, 1; int
0x1800adb57  mov     r8, rbx; HRGN
0x1800adb5a  xor     edx, edx; struct tagRECT *
0x1800adb5c  mov     rcx, rdi; this
0x1800adb5f  call    ?_InvalidateWindow@CInkCollector@@AEAAHPEAUtagRECT@@PEAUHRGN__@@HH@Z; CInkCollector::_InvalidateWindow(tagRECT *,HRGN__ *,int,int)
0x1800adb64  mov     [rsp+98h+lParam], r12; int
0x1800adb69  mov     r9, [rsp+98h+wParam]; wParam
0x1800adb71  mov     r8d, [rsp+98h+Msg]; Msg
0x1800adb79  mov     rdx, [rdi+38h]; hWnd
0x1800adb7d  mov     rcx, [rdi+68h]; lpPrevWndFunc
0x1800adb81  call    cs:__imp_CallWindowProcW
0x1800adb87  mov     rcx, [rdi+38h]; hWnd
0x1800adb8b  call    cs:__imp_GetDC
0x1800adb91  mov     r12, rax
0x1800adb94  mov     rcx, rax; hdc
0x1800adb97  call    cs:__imp_SaveDC
0x1800adb9d  mov     [rsp+98h+nSavedDC], eax
0x1800adba4  xor     r9d, r9d; y2
0x1800adba7  xor     r8d, r8d; x2
0x1800adbaa  xor     edx, edx; y1
0x1800adbac  xor     ecx, ecx; x1
0x1800adbae  call    cs:__imp_CreateRectRgn
0x1800adbb4  mov     rsi, rax
0x1800adbb7  mov     [rsp+98h+var_58], rax
0x1800adbbc  test    rax, rax
0x1800adbbf  jz      loc_1800ADCAB
0x1800adbc5  test    r15, r15
0x1800adbc8  jz      loc_1800ADCAB
0x1800adbce  test    rbx, rbx
0x1800adbd1  jz      loc_1800ADCAB
0x1800adbd7  mov     r8d, 4; i
0x1800adbdd  mov     rdx, rax; hrgn
0x1800adbe0  mov     rcx, r12; hdc
0x1800adbe3  call    cs:__imp_GetRandomRgn
0x1800adbe9  mov     r9d, 4; iMode
0x1800adbef  mov     r8, r15; hrgnSrc2
0x1800adbf2  mov     rdx, rsi; hrgnSrc1
0x1800adbf5  mov     rcx, rsi; hrgnDst
0x1800adbf8  call    cs:__imp_CombineRgn
0x1800adbfe  cmp     eax, 1
0x1800adc01  jbe     short loc_1800ADC70
0x1800adc03  mov     qword ptr [rsp+98h+Points.x], 0
0x1800adc0f  mov     r9d, 1; cPoints
0x1800adc15  lea     r8, [rsp+98h+Points]; lpPoints
0x1800adc1d  mov     rdx, [rdi+38h]; hWndTo
0x1800adc21  xor     ecx, ecx; hWndFrom
0x1800adc23  call    cs:__imp_MapWindowPoints
0x1800adc29  mov     r8d, [rsp+98h+Points.y]; y
0x1800adc31  mov     edx, [rsp+98h+Points.x]; x
0x1800adc38  mov     rcx, rsi; hrgn
0x1800adc3b  call    cs:__imp_OffsetRgn
0x1800adc41  mov     r9d, 2; iMode
0x1800adc47  mov     r8, rsi; hrgnSrc2
0x1800adc4a  mov     rdx, rbx; hrgnSrc1
0x1800adc4d  mov     rcx, rbx; hrgnDst
0x1800adc50  call    cs:__imp_CombineRgn
0x1800adc56  test    r14, r14
0x1800adc59  jz      short loc_1800ADC70
0x1800adc5b  mov     r9d, 1; iMode
0x1800adc61  mov     r8, r14; hrgnSrc2
0x1800adc64  mov     rdx, rbx; hrgnSrc1
0x1800adc67  mov     rcx, rbx; hrgnDst
0x1800adc6a  call    cs:__imp_CombineRgn
0x1800adc70  mov     rdx, rbx; hrgn
0x1800adc73  mov     rcx, r12; hdc
0x1800adc76  call    cs:__imp_SelectClipRgn
0x1800adc7c  lea     rdx, [rdi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800adc83  lea     rcx, [rsp+98h+var_48]; this
0x1800adc88  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800adc8d  nop
0x1800adc8e  mov     r9d, [rdi+18Ch]; int
0x1800adc95  mov     rdx, r12; HDC
0x1800adc98  mov     rcx, rdi; this
0x1800adc9b  call    ?_DrawStrokes@CInkCollector@@AEAAJPEAUHDC__@@PEAUIInkStrokes@@HHPEAUIInkRenderer@@@Z; CInkCollector::_DrawStrokes(HDC__ *,IInkStrokes *,int,int,IInkRenderer *)
0x1800adca0  nop
0x1800adca1  lea     rcx, [rsp+98h+var_48]; this
0x1800adca6  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800adcab  mov     edx, [rsp+98h+nSavedDC]; nSavedDC
0x1800adcb2  mov     rcx, r12; hdc
0x1800adcb5  call    cs:__imp_RestoreDC
0x1800adcbb  mov     rdx, r12; hDC
0x1800adcbe  mov     rcx, [rdi+38h]; hWnd
0x1800adcc2  call    cs:__imp_ReleaseDC
0x1800adcc8  mov     dword ptr [r13+0], 1
0x1800adcd0  jmp     short loc_1800ADCE6
0x1800adcd2  mov     r15, [rsp+98h+var_68]
0x1800adcd7  mov     rbx, [rsp+98h+var_60]
0x1800adcdc  mov     rsi, [rsp+98h+var_58]
0x1800adce1  mov     r14, [rsp+98h+var_50]
0x1800adce6  test    r15, r15
0x1800adce9  jz      short loc_1800ADCF4
0x1800adceb  mov     rcx, r15; ho
0x1800adcee  call    cs:__imp_DeleteObject
0x1800adcf4  test    rbx, rbx
0x1800adcf7  jz      short loc_1800ADD02
0x1800adcf9  mov     rcx, rbx; ho
0x1800adcfc  call    cs:__imp_DeleteObject
0x1800add02  test    rsi, rsi
0x1800add05  jz      short loc_1800ADD10
0x1800add07  mov     rcx, rsi; ho
0x1800add0a  call    cs:__imp_DeleteObject
0x1800add10  test    r14, r14
0x1800add13  jz      short loc_1800ADD1E
0x1800add15  mov     rcx, r14; ho
0x1800add18  call    cs:__imp_DeleteObject
0x1800add1e  xor     eax, eax
0x1800add20  add     rsp, 60h
0x1800add24  pop     r15
0x1800add26  pop     r14
0x1800add28  pop     r13
0x1800add2a  pop     r12
0x1800add2c  pop     rdi
0x1800add2d  pop     rsi
0x1800add2e  pop     rbx
0x1800add2f  retn
```
