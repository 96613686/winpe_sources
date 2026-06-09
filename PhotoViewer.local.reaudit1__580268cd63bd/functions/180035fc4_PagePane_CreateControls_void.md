# PagePane::CreateControls(void)

- ea: `0x180035fc4`
- end: `0x1800361a4`
- name: `?CreateControls@PagePane@@AEAAXXZ`
- size: `480`
- prototype: `void __fastcall(PagePane *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180024280`
- `0x180035f6c`

## callees

- `0x180004908`
- `0x180035fc4`
- `0x18003653c`
- `0x18003f800`
- `0x1800718ec`
- `0x180071974`
- `0x180071c50`
- `0x180076bac`
- `0x180077050`
- `0x18007a5a0`

## import_xrefs

- `USER32!MoveWindow` at `0x18003615f`
- `USER32!MoveWindow` at `0x18003615f`
- `USER32!GetClientRect` at `0x180036009`
- `USER32!GetClientRect` at `0x180036009`
- `USER32!InvalidateRect` at `0x1800360e7`
- `USER32!InvalidateRect` at `0x1800360e7`
- `USER32!SetWindowTextW` at `0x18003610a`
- `USER32!SetWindowTextW` at `0x18003610a`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003619d`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18003619d`

## pseudocode

```c
void __fastcall PagePane::CreateControls(HWND *this)
{
  HWND *v1; // rdi
  Base *v2; // rcx
  int v3; // r9d
  int v4; // r8d
  unsigned int TextColor; // eax
  LPCWSTR *PageLabel; // rax
  int nHeight; // [rsp+20h] [rbp-78h]
  BOOL bRepaint; // [rsp+28h] [rbp-70h]
  _BYTE v9[8]; // [rsp+40h] [rbp-58h] BYREF
  HWND *v10; // [rsp+48h] [rbp-50h]
  _BYTE v11[16]; // [rsp+50h] [rbp-48h] BYREF
  int X[4]; // [rsp+60h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-28h] BYREF

  v1 = this;
  v10 = this;
  if ( !*((_BYTE *)this + 1544) )
  {
    Rect = 0;
    if ( !GetClientRect(this[1], &Rect) )
    {
      Base::ThrowLastError(v2);
      JUMPOUT(0x1800361A3LL);
    }
    PagePane::CreateButton((PagePane *)v1, v1 + 56, 0x232Bu, 0x232Au, 0x2331u, 0x2332u);
    PagePane::CreateButton((PagePane *)v1, v1 + 124, 0x2329u, 0x2328u, 0x232Fu, 0x2330u);
    try
    {
      *(__m128i *)X = _mm_load_si128((const __m128i *)&_xmm);
      ATL::CWindowImpl<UIControls::StaticTextEx,ATL::CWindow,ATL::CWinTraits<1409286144,0>>::Create(
        (_DWORD)v1 + 240,
        (unsigned int)v1[1],
        (unsigned int)X,
        v3,
        nHeight,
        bRepaint,
        0);
      UIControls::StaticTextEx::SetAlignment(v1 + 30);
      TextColor = GetTextColor(v1[1], 4, v4);
      if ( *((_BYTE *)v1 + 392) || TextColor != *((_DWORD *)v1 + 100) )
      {
        *((_BYTE *)v1 + 392) = 0;
        *((_DWORD *)v1 + 100) = TextColor;
        InvalidateRect(v1[31], 0, 0);
      }
      PageLabel = (LPCWSTR *)GetPageLabel(v9, 2147483646, 0x7FFFFFFF);
      SetWindowTextW(v1[31], *PageLabel);
      Base::String::~String((Base::String *)v9);
      *((_DWORD *)v1 + 104) = -1;
      *((_DWORD *)v1 + 105) = -1;
      UIControls::StaticTextEx::EnsureSizeCalced((UIControls::StaticTextEx *)(v1 + 30));
      MoveWindow(v1[31], X[0], X[1], (int)v1[52], HIDWORD(v1[52]), 0);
    }
    catch ( Base::Exception v11 )
    {
      Base::Exception::~Exception((Base::Exception *)v11);
      v1 = v10;
    }
    PagePane::LayoutControls((PagePane *)v1);
    *((_BYTE *)v1 + 1544) = 1;
  }
}

```

## disassembly

```asm
0x180035fc4  mov     [rsp+arg_8], rbx
0x180035fc9  push    rdi
0x180035fca  sub     rsp, 90h
0x180035fd1  mov     rax, cs:__security_cookie
0x180035fd8  xor     rax, rsp
0x180035fdb  mov     [rsp+98h+var_18], rax
0x180035fe3  mov     rdi, rcx
0x180035fe6  mov     [rsp+98h+var_50], rcx
0x180035feb  cmp     byte ptr [rcx+608h], 0
0x180035ff2  jnz     loc_18003617C
0x180035ff8  xorps   xmm0, xmm0
0x180035ffb  movups  xmmword ptr [rsp+98h+Rect.left], xmm0
0x180036000  lea     rdx, [rsp+98h+Rect]; lpRect
0x180036005  mov     rcx, [rcx+8]; hWnd
0x180036009  call    cs:__imp_GetClientRect
0x18003600f  test    eax, eax
0x180036011  jz      loc_18003619D
0x180036017  lea     rdx, [rdi+1C0h]; struct UIControls::BitMapOnlyButtonTransparentBack *
0x18003601e  mov     [rsp+98h+var_68], 0BF69h; unsigned int
0x180036026  mov     [rsp+98h+bRepaint], 2332h; unsigned int
0x18003602e  mov     [rsp+98h+nHeight], 2331h; unsigned int
0x180036036  mov     r9d, 232Ah; unsigned int
0x18003603c  lea     r8d, [r9+1]; unsigned int
0x180036040  mov     rcx, rdi; this
0x180036043  call    ?CreateButton@PagePane@@AEAAXPEAVBitMapOnlyButtonTransparentBack@UIControls@@IIIII@Z; PagePane::CreateButton(UIControls::BitMapOnlyButtonTransparentBack *,uint,uint,uint,uint,uint)
0x180036048  lea     rdx, [rdi+3E0h]; struct UIControls::BitMapOnlyButtonTransparentBack *
0x18003604f  mov     [rsp+98h+var_68], 0BF68h; unsigned int
0x180036057  mov     [rsp+98h+bRepaint], 2330h; unsigned int
0x18003605f  mov     [rsp+98h+nHeight], 232Fh; unsigned int
0x180036067  mov     r9d, 2328h; unsigned int
0x18003606d  lea     r8d, [r9+1]; unsigned int
0x180036071  mov     rcx, rdi; this
0x180036074  call    ?CreateButton@PagePane@@AEAAXPEAVBitMapOnlyButtonTransparentBack@UIControls@@IIIII@Z; PagePane::CreateButton(UIControls::BitMapOnlyButtonTransparentBack *,uint,uint,uint,uint,uint)
0x180036079  nop
0x18003607a  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x180036082  movdqu  xmmword ptr [rsp+98h+X], xmm0
0x180036088  lea     rbx, [rdi+0F0h]
0x18003608f  xor     eax, eax
0x180036091  mov     qword ptr [rsp+98h+var_68], rax
0x180036096  lea     r8, [rsp+98h+X]
0x18003609b  mov     rdx, [rdi+8]
0x18003609f  mov     rcx, rbx
0x1800360a2  call    ?Create@?$CWindowImpl@VStaticTextEx@UIControls@@VCWindow@ATL@@V?$CWinTraits@$0FEAAAAAA@$0A@@4@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@PEAX@Z; ATL::CWindowImpl<UIControls::StaticTextEx,ATL::CWindow,ATL::CWinTraits<1409286144,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,void *)
0x1800360a7  mov     rcx, rbx
0x1800360aa  call    ?SetAlignment@StaticTextEx@UIControls@@QEAAXW4StringAlignment@Gdiplus@@@Z; UIControls::StaticTextEx::SetAlignment(Gdiplus::StringAlignment)
0x1800360af  mov     edx, 4; int
0x1800360b4  mov     rcx, [rdi+8]; HWND
0x1800360b8  call    ?GetTextColor@@YAKPEAUHWND__@@HH@Z; GetTextColor(HWND__ *,int,int)
0x1800360bd  cmp     byte ptr [rdi+188h], 0
0x1800360c4  jnz     short loc_1800360CE
0x1800360c6  cmp     eax, [rdi+190h]
0x1800360cc  jz      short loc_1800360ED
0x1800360ce  mov     byte ptr [rdi+188h], 0
0x1800360d5  mov     [rdi+190h], eax
0x1800360db  xor     r8d, r8d; bErase
0x1800360de  xor     edx, edx; lpRect
0x1800360e0  mov     rcx, [rdi+0F8h]; hWnd
0x1800360e7  call    cs:__imp_InvalidateRect
0x1800360ed  mov     edx, 7FFFFFFEh
0x1800360f2  lea     r8d, [rdx+1]
0x1800360f6  lea     rcx, [rsp+98h+var_58]
0x1800360fb  call    GetPageLabel
0x180036100  mov     rdx, [rax]; lpString
0x180036103  mov     rcx, [rdi+0F8h]; hWnd
0x18003610a  call    cs:__imp_SetWindowTextW
0x180036110  lea     rcx, [rsp+98h+var_58]; this
0x180036115  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18003611a  or      eax, 0FFFFFFFFh
0x18003611d  mov     [rdi+1A0h], eax
0x180036123  mov     [rdi+1A4h], eax
0x180036129  lea     rcx, [rdi+0F0h]; this
0x180036130  call    ?EnsureSizeCalced@StaticTextEx@UIControls@@AEAAXXZ; UIControls::StaticTextEx::EnsureSizeCalced(void)
0x180036135  mov     r9, [rdi+1A0h]; nWidth
0x18003613c  mov     rax, r9
0x18003613f  shr     rax, 20h
0x180036143  mov     [rsp+98h+bRepaint], 0; bRepaint
0x18003614b  mov     [rsp+98h+nHeight], eax; nHeight
0x18003614f  mov     r8d, [rsp+98h+X+4]; Y
0x180036154  mov     edx, [rsp+98h+X]; X
0x180036158  mov     rcx, [rdi+0F8h]; hWnd
0x18003615f  call    cs:__imp_MoveWindow
0x180036165  nop
0x180036166  jmp     short loc_18003616D
0x180036168  mov     rdi, [rsp+98h+var_50]
0x18003616d  mov     rcx, rdi; this
0x180036170  call    ?LayoutControls@PagePane@@AEAAXXZ; PagePane::LayoutControls(void)
0x180036175  mov     byte ptr [rdi+608h], 1
0x18003617c  mov     rcx, [rsp+98h+var_18]
0x180036184  xor     rcx, rsp; StackCookie
0x180036187  call    __security_check_cookie
0x18003618c  mov     rbx, [rsp+98h+arg_8]
0x180036194  add     rsp, 90h
0x18003619b  pop     rdi
0x18003619c  retn
0x18003619d  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
```
