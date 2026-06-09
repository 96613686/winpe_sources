# UIControls::SplitButtonEx::OnLButtonUp(uint,unsigned __int64,__int64,int &)

- ea: `0x1800758e8`
- end: `0x1800759f8`
- name: `?OnLButtonUp@SplitButtonEx@UIControls@@AEAA_JI_K_JAEAH@Z`
- size: `272`
- prototype: `__int64 __fastcall(UIControls::SplitButtonEx *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800084d0`
- `0x1800088c0`

## callees

- `0x180031688`
- `0x1800357ac`
- `0x180037cf8`
- `0x18003f800`
- `0x1800747c8`
- `0x1800755d0`
- `0x1800758e8`

## import_xrefs

- `USER32!PtInRect` at `0x180075948`
- `USER32!PtInRect` at `0x180075997`
- `USER32!PtInRect` at `0x180075948`
- `USER32!PtInRect` at `0x180075997`
- `USER32!GetClientRect` at `0x18007593a`
- `USER32!GetClientRect` at `0x18007593a`
- `gdiplus!GdipDeleteGraphics` at `0x1800759b4`
- `gdiplus!GdipDeleteGraphics` at `0x1800759b4`

## pseudocode

```c
__int64 __fastcall UIControls::SplitButtonEx::OnLButtonUp(HWND *this, __int64 a2, __int64 a3, int a4)
{
  int v6; // r8d
  int v7; // eax
  int v8; // eax
  POINT pt; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  int v12; // [rsp+30h] [rbp-30h]
  struct tagRECT Rect; // [rsp+38h] [rbp-28h] BYREF
  RECT rc; // [rsp+48h] [rbp-18h] BYREF

  if ( UIControls::ButtonEx::SafeReleaseCapture((UIControls::ButtonEx *)this) )
  {
    pt.x = (__int16)a4;
    pt.y = SHIWORD(a4);
    Rect = 0;
    GetClientRect(this[1], &Rect);
    if ( PtInRect(&Rect, pt) )
    {
      v7 = *((_DWORD *)this + 151);
      if ( v7 )
      {
        if ( v7 == 1 )
        {
          UIControls::SplitButtonEx::SendDropDownNotification((UIControls::SplitButtonEx *)this);
        }
        else if ( v7 == 2 )
        {
          UIControls::ButtonEx::Accessible_DoDefaultAction((UIControls::ButtonEx *)this);
        }
      }
      else
      {
        Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v11, this[1], v6);
        v8 = v12;
        v12 = 0;
        if ( !v8 )
        {
          UIControls::SplitButtonEx::GetSplitAreaRect(
            (UIControls::SplitButtonEx *)this,
            &rc,
            (const struct Gdiplus::Graphics *)&v11,
            &Rect);
          if ( PtInRect(&rc, pt) )
            UIControls::SplitButtonEx::SendDropDownNotification((UIControls::SplitButtonEx *)this);
          else
            UIControls::ButtonEx::Accessible_DoDefaultAction((UIControls::ButtonEx *)this);
        }
        GdipDeleteGraphics(v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800758e8  mov     [rsp-8+arg_8], rbx
0x1800758ed  mov     [rsp-8+arg_10], rdi
0x1800758f2  push    rbp
0x1800758f3  mov     rbp, rsp
0x1800758f6  sub     rsp, 60h
0x1800758fa  mov     rax, cs:__security_cookie
0x180075901  xor     rax, rsp
0x180075904  mov     [rbp+var_8], rax
0x180075908  mov     rdi, r9
0x18007590b  mov     rbx, rcx
0x18007590e  call    ?SafeReleaseCapture@ButtonEx@UIControls@@IEAA_NXZ; UIControls::ButtonEx::SafeReleaseCapture(void)
0x180075913  test    al, al
0x180075915  jz      loc_1800759D8
0x18007591b  movsx   eax, di
0x18007591e  mov     [rbp+pt.x], eax
0x180075921  shr     rdi, 10h
0x180075925  movsx   eax, di
0x180075928  mov     [rbp+pt.y], eax
0x18007592b  xorps   xmm0, xmm0
0x18007592e  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180075932  lea     rdx, [rbp+Rect]; lpRect
0x180075936  mov     rcx, [rbx+8]; hWnd
0x18007593a  call    cs:__imp_GetClientRect
0x180075940  mov     rdx, qword ptr [rbp+pt.x]; pt
0x180075944  lea     rcx, [rbp+Rect]; lprc
0x180075948  call    cs:__imp_PtInRect
0x18007594e  test    eax, eax
0x180075950  jz      loc_1800759D8
0x180075956  mov     eax, [rbx+25Ch]
0x18007595c  test    eax, eax
0x18007595e  jnz     short loc_1800759BC
0x180075960  mov     rdx, [rbx+8]; HWND
0x180075964  lea     rcx, [rbp+var_38]; this
0x180075968  call    ??0Graphics@Gdiplus@@QEAA@PEAUHWND__@@H@Z; Gdiplus::Graphics::Graphics(HWND__ *,int)
0x18007596d  mov     eax, [rbp+var_30]
0x180075970  mov     [rbp+var_30], 0
0x180075977  test    eax, eax
0x180075979  jnz     short loc_1800759B0
0x18007597b  lea     r9, [rbp+Rect]; struct tagRECT *
0x18007597f  lea     r8, [rbp+var_38]; struct Gdiplus::Graphics *
0x180075983  lea     rdx, [rbp+rc]; retstr
0x180075987  mov     rcx, rbx; this
0x18007598a  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x18007598f  mov     rdx, qword ptr [rbp+pt.x]; pt
0x180075993  lea     rcx, [rbp+rc]; lprc
0x180075997  call    cs:__imp_PtInRect
0x18007599d  mov     rcx, rbx; this
0x1800759a0  test    eax, eax
0x1800759a2  jz      short loc_1800759AB
0x1800759a4  call    ?SendDropDownNotification@SplitButtonEx@UIControls@@QEAAXXZ; UIControls::SplitButtonEx::SendDropDownNotification(void)
0x1800759a9  jmp     short loc_1800759B0
0x1800759ab  call    ?Accessible_DoDefaultAction@ButtonEx@UIControls@@QEAAJXZ; UIControls::ButtonEx::Accessible_DoDefaultAction(void)
0x1800759b0  mov     rcx, [rbp+var_38]
0x1800759b4  call    cs:__imp_GdipDeleteGraphics
0x1800759ba  jmp     short loc_1800759D8
0x1800759bc  cmp     eax, 1
0x1800759bf  jnz     short loc_1800759CB
0x1800759c1  mov     rcx, rbx; this
0x1800759c4  call    ?SendDropDownNotification@SplitButtonEx@UIControls@@QEAAXXZ; UIControls::SplitButtonEx::SendDropDownNotification(void)
0x1800759c9  jmp     short loc_1800759D8
0x1800759cb  cmp     eax, 2
0x1800759ce  jnz     short loc_1800759D8
0x1800759d0  mov     rcx, rbx; this
0x1800759d3  call    ?Accessible_DoDefaultAction@ButtonEx@UIControls@@QEAAJXZ; UIControls::ButtonEx::Accessible_DoDefaultAction(void)
0x1800759d8  xor     eax, eax
0x1800759da  mov     rcx, [rbp+var_8]
0x1800759de  xor     rcx, rsp; StackCookie
0x1800759e1  call    __security_check_cookie
0x1800759e6  lea     r11, [rsp+60h+var_s0]
0x1800759eb  mov     rbx, [r11+18h]
0x1800759ef  mov     rdi, [r11+20h]
0x1800759f3  mov     rsp, r11
0x1800759f6  pop     rbp
0x1800759f7  retn
```
