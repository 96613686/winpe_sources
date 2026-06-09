# PhotoMediaHandlerCanvas::RecalculateBestFitZoom(void)

- ea: `0x18000bca0`
- end: `0x18000c062`
- name: `?RecalculateBestFitZoom@PhotoMediaHandlerCanvas@@AEAAXXZ`
- size: `962`
- prototype: `void __fastcall(PhotoMediaHandlerCanvas *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b880`
- `0x18002e720`
- `0x18002f0f0`
- `0x18005c51c`
- `0x18005cec0`
- `0x18005e0b0`

## callees

- `0x18000bca0`
- `0x18000c1e4`
- `0x18003f800`
- `0x18005ac8c`
- `0x18005bbec`
- `0x180080010`

## import_xrefs

- `USER32!SendMessageW` at `0x18000bfc2`
- `USER32!SendMessageW` at `0x18000bfc2`
- `USER32!GetClientRect` at `0x18000bd54`
- `USER32!GetClientRect` at `0x18000bd54`
- `USER32!GetCursorPos` at `0x18000bf9a`
- `USER32!GetCursorPos` at `0x18000bf9a`
- `USER32!WindowFromPoint` at `0x18000bfa8`
- `USER32!WindowFromPoint` at `0x18000bfa8`
- `USER32!IsRectEmpty` at `0x18000bd37`
- `USER32!IsRectEmpty` at `0x18000bd6e`
- `USER32!IsRectEmpty` at `0x18000bd37`
- `USER32!IsRectEmpty` at `0x18000bd6e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bd08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bd63`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bf2e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bd08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bd63`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000bf2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PhotoMediaHandlerCanvas::RecalculateBestFitZoom(PhotoMediaHandlerCanvas *this)
{
  int v2; // edi
  int v3; // esi
  float v4; // xmm6_4
  __int64 v5; // rcx
  int v6; // eax
  int v7; // edx
  char v8; // r15
  int v9; // edx
  LONG left; // edi
  LONG top; // esi
  LONG right; // r8d
  int v13; // eax
  int v14; // r10d
  float v15; // xmm2_4
  float v16; // xmm4_4
  float v17; // xmm5_4
  float v18; // xmm3_4
  int v19; // eax
  _DWORD *v20; // r14
  float *v21; // rdi
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  HWND v25; // rax
  HWND v26; // rcx
  __int64 v27; // rcx
  struct tagPOINT Point; // [rsp+20h] [rbp-58h] BYREF
  RECT rc; // [rsp+28h] [rbp-50h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-40h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = FLOAT_1_0;
  v5 = *((_QWORD *)this + 335);
  if ( !v5 )
  {
LABEL_17:
    v8 = 1;
    goto LABEL_18;
  }
  Point = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, struct tagPOINT *))(*(_QWORD *)v5 + 160LL))(v5, &Point);
  if ( v6 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v6, v7);
    __debugbreak();
  }
  v8 = 0;
  if ( Point.x > 0 && Point.y > 0 )
  {
    *(_QWORD *)&rc.left = 0;
    *(struct tagPOINT *)&rc.right = Point;
    if ( !IsRectEmpty(&rc) )
    {
      Rect = 0;
      if ( !GetClientRect(*((HWND *)this + 1), &Rect) )
      {
        Base::Throw((Base *)0x80004005LL, v9);
        __debugbreak();
      }
      if ( !IsRectEmpty(&Rect) )
      {
        left = Rect.left;
        top = Rect.top;
        right = Rect.right;
        v13 = Rect.right - Rect.left;
        v14 = rc.right - rc.left;
        if ( rc.right - rc.left > Rect.right - Rect.left || rc.bottom - rc.top > Rect.bottom - Rect.top )
        {
          v16 = (float)(Rect.bottom - Rect.top);
          v17 = (float)v13;
          v18 = (float)(rc.bottom - rc.top);
          v15 = (float)v14;
          if ( (float)((float)v14 / v18) <= (float)((float)v13 / v16) )
          {
            v19 = (int)(float)((float)(v17 - (float)((float)(v15 * v16) / v18)) * 0.5);
            left = v19 + Rect.left;
            right = Rect.right - v19;
          }
          else
          {
            top = (int)(float)((float)(v16 - (float)((float)(v18 * v17) / v15)) * 0.5) + Rect.top;
          }
        }
        else
        {
          left = (rc.left + v13 - rc.right) / 2 + Rect.left;
          right = rc.right + left - rc.left;
          top = (rc.top + Rect.bottom - Rect.top - rc.bottom) / 2 + Rect.top;
          v15 = (float)v14;
        }
        v4 = (float)(right - left) / v15;
        v2 = -left;
        v3 = -top;
        goto LABEL_17;
      }
    }
  }
LABEL_18:
  v20 = (_DWORD *)((char *)this + 2512);
  *((_DWORD *)this + 628) = v2;
  *((_DWORD *)this + 629) = v3;
  v21 = (float *)((char *)this + 2520);
  if ( *((float *)this + 630) != v4 )
  {
    *v21 = v4;
    ___NotifySinks_P8IZoomableEventSink__EAAJPEAVIZoomable__M__EPEAVPhotoMediaHandlerCanvas__M___EventSinkHelper_VIZoomableEventSink___MiscUtil__QEAAXP8IZoomableEventSink__EAAJPEAVIZoomable__M__EPEAVPhotoMediaHandlerCanvas__M_Z(
      (char *)this + 232,
       ISlideshowCustomEventHandler::`vcall'{40,{flat}},
      this);
  }
  if ( *((_QWORD *)this + 332)
    && v8
    && *((_BYTE *)this + 2508)
    && (*v20 != *((_DWORD *)this + 617)
     || *((_DWORD *)this + 629) != *((_DWORD *)this + 618)
     || *v21 != *((float *)this + 620)) )
  {
    v22 = s_engineWrapper;
    if ( !s_engineWrapper )
    {
      PhotoEngine::Initialize(0);
      v22 = s_engineWrapper;
    }
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 120LL))(v22);
    if ( v23 < 0 )
      Base::Throw((Base *)(unsigned int)v23, v24);
    if ( *((float *)this + 620) != *v21
      || *((_DWORD *)this + 617) != *v20
      || *((_DWORD *)this + 618) != *((_DWORD *)this + 629) )
    {
      (*(void (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 332) + 128LL))(
        *((_QWORD *)this + 332),
        (char *)this + 2512,
        (char *)this + 2520);
    }
    if ( *((float *)this + 620) != *v21 )
    {
      *((float *)this + 620) = *v21;
      Point = 0;
      if ( GetCursorPos(&Point) )
      {
        v25 = WindowFromPoint(Point);
        v26 = (HWND)*((_QWORD *)this + 1);
        if ( v26 == v25 )
          SendMessageW(v26, 0x20u, *((_QWORD *)this + 1), 0);
      }
      ___NotifySinks_P8IZoomableEventSink__EAAJPEAVIZoomable__M__EPEAVPhotoMediaHandlerCanvas__M___EventSinkHelper_VIZoomableEventSink___MiscUtil__QEAAXP8IZoomableEventSink__EAAJPEAVIZoomable__M__EPEAVPhotoMediaHandlerCanvas__M_Z(
        (char *)this + 232,
         IMultiPageEventSink::`vcall'{32,{flat}},
        this);
    }
    if ( *((_DWORD *)this + 617) != *v20 || *((_DWORD *)this + 618) != *((_DWORD *)this + 629) )
      *(_QWORD *)((char *)this + 2468) = *(_QWORD *)v20;
    PhotoMediaHandlerCanvas::UpdateOverlay(this);
    v27 = s_engineWrapper;
    if ( !s_engineWrapper )
    {
      PhotoEngine::Initialize(0);
      v27 = s_engineWrapper;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 128LL))(v27);
  }
}

```

## disassembly

```asm
0x18000bca0  push    rbp
0x18000bca2  push    rbx
0x18000bca3  push    rsi
0x18000bca4  push    rdi
0x18000bca5  push    r12
0x18000bca7  push    r13
0x18000bca9  push    r14
0x18000bcab  push    r15
0x18000bcad  mov     rbp, rsp
0x18000bcb0  sub     rsp, 78h
0x18000bcb4  movaps  [rsp+78h+var_18], xmm6
0x18000bcb9  mov     rax, cs:__security_cookie
0x18000bcc0  xor     rax, rsp
0x18000bcc3  mov     [rbp+var_28], rax
0x18000bcc7  mov     rbx, rcx
0x18000bcca  xor     r13d, r13d
0x18000bccd  mov     edi, r13d
0x18000bcd0  mov     esi, r13d
0x18000bcd3  movss   xmm6, cs:__real@3f800000
0x18000bcdb  mov     rcx, [rcx+0A78h]
0x18000bce2  test    rcx, rcx
0x18000bce5  jz      loc_18000BE6D
0x18000bceb  mov     qword ptr [rbp+Point.x], r13
0x18000bcef  mov     rax, [rcx]
0x18000bcf2  lea     rdx, [rbp+Point]
0x18000bcf6  mov     rax, [rax+0A0h]
0x18000bcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd02  test    eax, eax
0x18000bd04  jns     short loc_18000BD0F
0x18000bd06  mov     ecx, eax
0x18000bd08  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000bd0e  int     3; Trap to Debugger
0x18000bd0f  xor     r15b, r15b
0x18000bd12  mov     rax, qword ptr [rbp+Point.x]
0x18000bd16  test    eax, eax
0x18000bd18  jle     loc_18000BE70
0x18000bd1e  mov     ecx, [rbp+Point.y]
0x18000bd21  test    ecx, ecx
0x18000bd23  jle     loc_18000BE70
0x18000bd29  mov     qword ptr [rbp+rc.left], r13
0x18000bd2d  mov     [rbp+rc.right], eax
0x18000bd30  mov     [rbp+rc.bottom], ecx
0x18000bd33  lea     rcx, [rbp+rc]; lprc
0x18000bd37  call    cs:__imp_IsRectEmpty
0x18000bd3d  test    eax, eax
0x18000bd3f  jnz     loc_18000BE70
0x18000bd45  xorps   xmm0, xmm0
0x18000bd48  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18000bd4c  lea     rdx, [rbp+Rect]; lpRect
0x18000bd50  mov     rcx, [rbx+8]; hWnd
0x18000bd54  call    cs:__imp_GetClientRect
0x18000bd5a  test    eax, eax
0x18000bd5c  jnz     short loc_18000BD6A
0x18000bd5e  mov     ecx, 80004005h
0x18000bd63  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000bd69  int     3; Trap to Debugger
0x18000bd6a  lea     rcx, [rbp+Rect]; lprc
0x18000bd6e  call    cs:__imp_IsRectEmpty
0x18000bd74  test    eax, eax
0x18000bd76  jnz     loc_18000BE70
0x18000bd7c  mov     edi, [rbp+Rect.left]
0x18000bd7f  mov     esi, [rbp+Rect.top]
0x18000bd82  mov     r8d, [rbp+Rect.right]
0x18000bd86  mov     eax, r8d
0x18000bd89  sub     eax, edi
0x18000bd8b  mov     r11d, [rbp+rc.right]
0x18000bd8f  mov     r10d, r11d
0x18000bd92  mov     r14d, [rbp+rc.left]
0x18000bd96  sub     r10d, r14d
0x18000bd99  mov     edx, [rbp+Rect.bottom]
0x18000bd9c  mov     r15d, [rbp+rc.bottom]
0x18000bda0  mov     r12d, [rbp+rc.top]
0x18000bda4  cmp     r10d, eax
0x18000bda7  jg      short loc_18000BDE8
0x18000bda9  mov     r9d, edx
0x18000bdac  sub     r9d, esi
0x18000bdaf  mov     ecx, r15d
0x18000bdb2  sub     ecx, r12d
0x18000bdb5  cmp     ecx, r9d
0x18000bdb8  jg      short loc_18000BDE8
0x18000bdba  sub     eax, r11d
0x18000bdbd  add     eax, r14d
0x18000bdc0  cdq
0x18000bdc1  sub     eax, edx
0x18000bdc3  sar     eax, 1
0x18000bdc5  add     edi, eax
0x18000bdc7  mov     r8d, edi
0x18000bdca  sub     r8d, r14d
0x18000bdcd  add     r8d, r11d
0x18000bdd0  sub     r9d, r15d
0x18000bdd3  lea     eax, [r12+r9]
0x18000bdd7  cdq
0x18000bdd8  sub     eax, edx
0x18000bdda  sar     eax, 1
0x18000bddc  add     esi, eax
0x18000bdde  movd    xmm2, r10d
0x18000bde3  cvtdq2ps xmm2, xmm2
0x18000bde6  jmp     short loc_18000BE5A
0x18000bde8  sub     edx, esi
0x18000bdea  movd    xmm4, edx
0x18000bdee  cvtdq2ps xmm4, xmm4
0x18000bdf1  movd    xmm5, eax
0x18000bdf5  cvtdq2ps xmm5, xmm5
0x18000bdf8  sub     r15d, r12d
0x18000bdfb  movd    xmm3, r15d
0x18000be00  cvtdq2ps xmm3, xmm3
0x18000be03  movd    xmm2, r10d
0x18000be08  cvtdq2ps xmm2, xmm2
0x18000be0b  movaps  xmm1, xmm2
0x18000be0e  divss   xmm1, xmm3
0x18000be12  movaps  xmm0, xmm5
0x18000be15  divss   xmm0, xmm4
0x18000be19  comiss  xmm1, xmm0
0x18000be1c  jbe     short loc_18000BE3A
0x18000be1e  mulss   xmm3, xmm5
0x18000be22  divss   xmm3, xmm2
0x18000be26  subss   xmm4, xmm3
0x18000be2a  mulss   xmm4, cs:__real@3f000000
0x18000be32  cvttss2si eax, xmm4
0x18000be36  add     esi, eax
0x18000be38  jmp     short loc_18000BE5A
0x18000be3a  movaps  xmm0, xmm2
0x18000be3d  mulss   xmm0, xmm4
0x18000be41  divss   xmm0, xmm3
0x18000be45  subss   xmm5, xmm0
0x18000be49  mulss   xmm5, cs:__real@3f000000
0x18000be51  cvttss2si eax, xmm5
0x18000be55  add     edi, eax
0x18000be57  sub     r8d, eax
0x18000be5a  sub     r8d, edi
0x18000be5d  movd    xmm6, r8d
0x18000be62  cvtdq2ps xmm6, xmm6
0x18000be65  divss   xmm6, xmm2
0x18000be69  neg     edi
0x18000be6b  neg     esi
0x18000be6d  mov     r15b, 1
0x18000be70  lea     r14, [rbx+9D0h]
0x18000be77  mov     [r14], edi
0x18000be7a  mov     [r14+4], esi
0x18000be7e  lea     rdi, [rbx+9D8h]
0x18000be85  movss   xmm0, dword ptr [rdi]
0x18000be89  ucomiss xmm0, xmm6
0x18000be8c  jp      short loc_18000BE90
0x18000be8e  jz      short loc_18000BEB5
0x18000be90  movss   dword ptr [rdi], xmm6
0x18000be94  mulss   xmm6, cs:__real@42c80000
0x18000be9c  lea     rcx, [rbx+0E8h]
0x18000bea3  movaps  xmm3, xmm6
0x18000bea6  mov     r8, rbx
0x18000bea9  lea     rdx, ??_9ISlideshowCustomEventHandler@@$BCI@AA; [thunk]: ISlideshowCustomEventHandler::`vcall'{40,{flat}}
0x18000beb0  call    ??$NotifySinks@P8IZoomableEventSink@@EAAJPEAVIZoomable@@M@_EPEAVPhotoMediaHandlerCanvas@@M@?$EventSinkHelper@VIZoomableEventSink@@@MiscUtil@@QEAAXP8IZoomableEventSink@@EAAJPEAVIZoomable@@M@_EPEAVPhotoMediaHandlerCanvas@@M@Z
0x18000beb5  cmp     [rbx+0A60h], r13
0x18000bebc  jz      loc_18000C040
0x18000bec2  test    r15b, r15b
0x18000bec5  jz      loc_18000C040
0x18000becb  cmp     [rbx+9CCh], r13b
0x18000bed2  jz      loc_18000C040
0x18000bed8  mov     eax, [rbx+9A4h]
0x18000bede  cmp     [r14], eax
0x18000bee1  jnz     short loc_18000BF04
0x18000bee3  mov     eax, [rbx+9A8h]
0x18000bee9  cmp     [rbx+9D4h], eax
0x18000beef  jnz     short loc_18000BF04
0x18000bef1  movss   xmm0, dword ptr [rdi]
0x18000bef5  ucomiss xmm0, dword ptr [rbx+9B0h]
0x18000befc  jp      short loc_18000BF04
0x18000befe  jz      loc_18000C040
0x18000bf04  mov     rcx, cs:?s_engineWrapper@@3VPhotoEngine@@A; this
0x18000bf0b  test    rcx, rcx
0x18000bf0e  jnz     short loc_18000BF1C
0x18000bf10  call    ?Initialize@PhotoEngine@@QEAAXXZ; PhotoEngine::Initialize(void)
0x18000bf15  mov     rcx, cs:?s_engineWrapper@@3VPhotoEngine@@A; PhotoEngine s_engineWrapper
0x18000bf1c  mov     rax, [rcx]
0x18000bf1f  mov     rax, [rax+78h]
0x18000bf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf28  test    eax, eax
0x18000bf2a  jns     short loc_18000BF35
0x18000bf2c  mov     ecx, eax
0x18000bf2e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000bf34  nop
0x18000bf35  movss   xmm0, dword ptr [rbx+9B0h]
0x18000bf3d  ucomiss xmm0, dword ptr [rdi]
0x18000bf40  jp      short loc_18000BF5B
0x18000bf42  jnz     short loc_18000BF5B
0x18000bf44  mov     eax, [r14]
0x18000bf47  cmp     [rbx+9A4h], eax
0x18000bf4d  jnz     short loc_18000BF5B
0x18000bf4f  mov     eax, [r14+4]
0x18000bf53  cmp     [rbx+9A8h], eax
0x18000bf59  jz      short loc_18000BF77
0x18000bf5b  mov     rcx, [rbx+0A60h]
0x18000bf62  mov     rax, [rcx]
0x18000bf65  mov     r8, rdi
0x18000bf68  mov     rdx, r14
0x18000bf6b  mov     rax, [rax+80h]
0x18000bf72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf77  movss   xmm1, dword ptr [rdi]
0x18000bf7b  movss   xmm0, dword ptr [rbx+9B0h]
0x18000bf83  ucomiss xmm0, xmm1
0x18000bf86  jp      short loc_18000BF8A
0x18000bf88  jz      short loc_18000BFEE
0x18000bf8a  movss   dword ptr [rbx+9B0h], xmm1
0x18000bf92  mov     qword ptr [rbp+Point.x], r13
0x18000bf96  lea     rcx, [rbp+Point]; lpPoint
0x18000bf9a  call    cs:__imp_GetCursorPos
0x18000bfa0  test    eax, eax
0x18000bfa2  jz      short loc_18000BFC8
0x18000bfa4  mov     rcx, qword ptr [rbp+Point.x]; Point
0x18000bfa8  call    cs:__imp_WindowFromPoint
0x18000bfae  mov     rcx, [rbx+8]; hWnd
0x18000bfb2  cmp     rcx, rax
0x18000bfb5  jnz     short loc_18000BFC8
0x18000bfb7  xor     r9d, r9d; lParam
0x18000bfba  mov     r8, rcx; wParam
0x18000bfbd  mov     edx, 20h ; ' '; Msg
0x18000bfc2  call    cs:__imp_SendMessageW
0x18000bfc8  movss   xmm3, dword ptr [rbx+9B0h]
0x18000bfd0  mulss   xmm3, cs:__real@42c80000
0x18000bfd8  lea     rcx, [rbx+0E8h]
0x18000bfdf  mov     r8, rbx
0x18000bfe2  lea     rdx, ??_9IMultiPageEventSink@@$BCA@AA; [thunk]: IMultiPageEventSink::`vcall'{32,{flat}}
0x18000bfe9  call    ??$NotifySinks@P8IZoomableEventSink@@EAAJPEAVIZoomable@@M@_EPEAVPhotoMediaHandlerCanvas@@M@?$EventSinkHelper@VIZoomableEventSink@@@MiscUtil@@QEAAXP8IZoomableEventSink@@EAAJPEAVIZoomable@@M@_EPEAVPhotoMediaHandlerCanvas@@M@Z
0x18000bfee  mov     eax, [r14]
0x18000bff1  cmp     [rbx+9A4h], eax
0x18000bff7  jnz     short loc_18000C005
0x18000bff9  mov     eax, [r14+4]
0x18000bffd  cmp     [rbx+9A8h], eax
0x18000c003  jz      short loc_18000C00F
0x18000c005  mov     rax, [r14]
0x18000c008  mov     [rbx+9A4h], rax
0x18000c00f  mov     rcx, rbx; this
0x18000c012  call    ?UpdateOverlay@PhotoMediaHandlerCanvas@@AEAAXXZ; PhotoMediaHandlerCanvas::UpdateOverlay(void)
0x18000c017  nop
0x18000c018  mov     rcx, cs:?s_engineWrapper@@3VPhotoEngine@@A; this
0x18000c01f  test    rcx, rcx
0x18000c022  jnz     short loc_18000C030
0x18000c024  call    ?Initialize@PhotoEngine@@QEAAXXZ; PhotoEngine::Initialize(void)
0x18000c029  mov     rcx, cs:?s_engineWrapper@@3VPhotoEngine@@A; PhotoEngine s_engineWrapper
0x18000c030  mov     rax, [rcx]
0x18000c033  mov     rax, [rax+80h]
0x18000c03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c03f  nop
0x18000c040  mov     rcx, [rbp+var_28]
0x18000c044  xor     rcx, rsp; StackCookie
0x18000c047  call    __security_check_cookie
0x18000c04c  movaps  xmm6, [rsp+78h+var_18]
0x18000c051  add     rsp, 78h
0x18000c055  pop     r15
0x18000c057  pop     r14
0x18000c059  pop     r13
0x18000c05b  pop     r12
0x18000c05d  pop     rdi
0x18000c05e  pop     rsi
0x18000c05f  pop     rbx
0x18000c060  pop     rbp
0x18000c061  retn
```
