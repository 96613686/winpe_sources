# UIControls::SplitButtonEx::OnMouseMove(uint,unsigned __int64,__int64,int &)

- ea: `0x180033e94`
- end: `0x180033f9c`
- name: `?OnMouseMove@SplitButtonEx@UIControls@@AEAA_JI_K_JAEAH@Z`
- size: `264`
- prototype: `__int64 __fastcall(UIControls::SplitButtonEx *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800084d0`
- `0x1800088c0`

## callees

- `0x180026f98`
- `0x180031688`
- `0x180033e94`
- `0x18003f800`

## import_xrefs

- `USER32!PtInRect` at `0x180033eed`
- `USER32!PtInRect` at `0x180033f47`
- `USER32!PtInRect` at `0x180033f69`
- `USER32!PtInRect` at `0x180033eed`
- `USER32!PtInRect` at `0x180033f47`
- `USER32!PtInRect` at `0x180033f69`
- `USER32!GetClientRect` at `0x180033edf`
- `USER32!GetClientRect` at `0x180033edf`
- `gdiplus!GdipCreateFromHWND` at `0x180033f07`
- `gdiplus!GdipCreateFromHWND` at `0x180033f07`
- `gdiplus!GdipDeleteGraphics` at `0x180033f23`
- `gdiplus!GdipDeleteGraphics` at `0x180033f5b`
- `gdiplus!GdipDeleteGraphics` at `0x180033f23`
- `gdiplus!GdipDeleteGraphics` at `0x180033f5b`

## pseudocode

```c
__int64 __fastcall UIControls::SplitButtonEx::OnMouseMove(
        UIControls::SplitButtonEx *this,
        __int64 a2,
        __int64 a3,
        int a4)
{
  HWND v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rsi
  BOOL v9; // eax
  POINT pt; // [rsp+20h] [rbp-40h]
  __int64 v12; // [rsp+28h] [rbp-38h] BYREF
  int v13; // [rsp+30h] [rbp-30h]
  struct tagRECT Rect; // [rsp+38h] [rbp-28h] BYREF
  RECT rc; // [rsp+48h] [rbp-18h] BYREF

  pt.x = (__int16)a4;
  *((_BYTE *)this + 576) = 0;
  v5 = (HWND)*((_QWORD *)this + 1);
  pt.y = SHIWORD(a4);
  Rect = 0;
  GetClientRect(v5, &Rect);
  if ( !PtInRect(&Rect, pt) )
  {
LABEL_7:
    v9 = PtInRect(&Rect, pt);
    UIControls::SplitButtonEx::SetHotState(this, v9);
    return 0;
  }
  v6 = *((_QWORD *)this + 1);
  v12 = 0;
  v7 = GdipCreateFromHWND(v6, &v12);
  v8 = v12;
  v13 = 0;
  if ( !v7 )
  {
    UIControls::SplitButtonEx::GetSplitAreaRect(this, &rc, (const struct Gdiplus::Graphics *)&v12, &Rect);
    if ( PtInRect(&rc, pt) )
      *((_BYTE *)this + 576) = 1;
    GdipDeleteGraphics(v8);
    goto LABEL_7;
  }
  GdipDeleteGraphics(v12);
  return 0;
}

```

## disassembly

```asm
0x180033e94  mov     [rsp-8+arg_8], rsi
0x180033e99  mov     [rsp-8+arg_10], rdi
0x180033e9e  push    rbp
0x180033e9f  mov     rbp, rsp
0x180033ea2  sub     rsp, 60h
0x180033ea6  mov     rax, cs:__security_cookie
0x180033ead  xor     rax, rsp
0x180033eb0  mov     [rbp+var_8], rax
0x180033eb4  movsx   eax, r9w
0x180033eb8  lea     rdx, [rbp+Rect]; lpRect
0x180033ebc  shr     r9, 10h
0x180033ec0  mov     rdi, rcx
0x180033ec3  mov     [rbp+pt.x], eax
0x180033ec6  xorps   xmm0, xmm0
0x180033ec9  movsx   eax, r9w
0x180033ecd  mov     byte ptr [rcx+240h], 0
0x180033ed4  mov     rcx, [rcx+8]; hWnd
0x180033ed8  mov     [rbp+pt.y], eax
0x180033edb  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180033edf  call    cs:__imp_GetClientRect
0x180033ee5  mov     rdx, qword ptr [rbp+pt.x]; pt
0x180033ee9  lea     rcx, [rbp+Rect]; lprc
0x180033eed  call    cs:__imp_PtInRect
0x180033ef3  test    eax, eax
0x180033ef5  jz      short loc_180033F61
0x180033ef7  mov     rcx, [rdi+8]
0x180033efb  lea     rdx, [rbp+var_38]
0x180033eff  mov     [rbp+var_38], 0
0x180033f07  call    cs:__imp_GdipCreateFromHWND
0x180033f0d  mov     rsi, [rbp+var_38]
0x180033f11  mov     [rbp+var_38], rsi
0x180033f15  mov     [rbp+var_30], 0
0x180033f1c  test    eax, eax
0x180033f1e  jz      short loc_180033F2B
0x180033f20  mov     rcx, rsi
0x180033f23  call    cs:__imp_GdipDeleteGraphics
0x180033f29  jmp     short loc_180033F7C
0x180033f2b  lea     r9, [rbp+Rect]; struct tagRECT *
0x180033f2f  mov     rcx, rdi; this
0x180033f32  lea     r8, [rbp+var_38]; struct Gdiplus::Graphics *
0x180033f36  lea     rdx, [rbp+rc]; retstr
0x180033f3a  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x180033f3f  mov     rdx, qword ptr [rbp+pt.x]; pt
0x180033f43  lea     rcx, [rbp+rc]; lprc
0x180033f47  call    cs:__imp_PtInRect
0x180033f4d  test    eax, eax
0x180033f4f  jz      short loc_180033F58
0x180033f51  mov     byte ptr [rdi+240h], 1
0x180033f58  mov     rcx, rsi
0x180033f5b  call    cs:__imp_GdipDeleteGraphics
0x180033f61  mov     rdx, qword ptr [rbp+pt.x]; pt
0x180033f65  lea     rcx, [rbp+Rect]; lprc
0x180033f69  call    cs:__imp_PtInRect
0x180033f6f  test    eax, eax
0x180033f71  mov     rcx, rdi; this
0x180033f74  setnz   dl; bool
0x180033f77  call    ?SetHotState@SplitButtonEx@UIControls@@QEAAX_N@Z; UIControls::SplitButtonEx::SetHotState(bool)
0x180033f7c  xor     eax, eax
0x180033f7e  mov     rcx, [rbp+var_8]
0x180033f82  xor     rcx, rsp; StackCookie
0x180033f85  call    __security_check_cookie
0x180033f8a  lea     r11, [rsp+60h+var_s0]
0x180033f8f  mov     rsi, [r11+18h]
0x180033f93  mov     rdi, [r11+20h]
0x180033f97  mov     rsp, r11
0x180033f9a  pop     rbp
0x180033f9b  retn
```
