# COleControl::OnSetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x180025430`
- end: `0x18002558e`
- name: `?OnSetObjectRects@COleControl@@UEAAHPEBUtagRECT@@0@Z`
- size: `350`
- prototype: `__int64 __fastcall(COleControl *__hidden this, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800250a0`
- `0x180025430`
- `0x180025594`
- `0x1800d1fe0`

## import_xrefs

- `USER32!OffsetRect` at `0x1800254b1`
- `USER32!OffsetRect` at `0x1800254b1`
- `USER32!CopyRect` at `0x18002545c`
- `USER32!CopyRect` at `0x18002548d`
- `USER32!CopyRect` at `0x18002545c`
- `USER32!CopyRect` at `0x18002548d`
- `USER32!InflateRect` at `0x1800254da`
- `USER32!InflateRect` at `0x1800254da`
- `USER32!MoveWindow` at `0x18002553f`
- `USER32!MoveWindow` at `0x18002553f`

## pseudocode

```c
__int64 __fastcall COleControl::OnSetObjectRects(HWND *this, const struct tagRECT *a2, struct tagRECT *a3)
{
  RECT *v3; // rbx
  bool v6; // zf
  struct tagRECT v7; // xmm0
  struct tagRECT *v8; // rcx
  int v9; // r8d
  HWND *v10; // rbx
  RECT rcSrc; // [rsp+30h] [rbp-40h] BYREF
  struct tagRECT X; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+50h] [rbp-20h] BYREF

  v3 = (RECT *)(this + 23);
  CopyRect((LPRECT)(this + 23), a2);
  v6 = ((_DWORD)this[31] & 0x800) == 0;
  v7 = *v3;
  rcSrc = *v3;
  if ( !v6 )
  {
    v8 = (struct tagRECT *)this[22];
    if ( v8 )
    {
      if ( a3 )
      {
        CopyRect(v8 + 5, a3);
        v7 = rcSrc;
      }
      rc = v7;
      OffsetRect(&rc, -v7.left, -v7.top);
      *(struct tagRECT *)(this[22] + 3) = rc;
      v9 = *((_DWORD *)this[22] + 9) - 1;
      InflateRect(&rcSrc, v9, v9);
    }
  }
  _GetClippingCoordinates(&rcSrc, a3, &X, (struct tagPOINT *)this + 27);
  if ( ((_DWORD)this[31] & 0x400000) == 0 )
  {
    v10 = (HWND *)this[29];
    if ( v10 || (v10 = this) != 0 )
      MoveWindow(v10[8], X.left, X.top, X.right - X.left, X.bottom - X.top, 1);
    if ( v10 != this )
      CWnd::MoveWindow(
        (CWnd *)this,
        *((_DWORD *)this + 54),
        *((_DWORD *)this + 55),
        rcSrc.right - rcSrc.left,
        rcSrc.bottom - rcSrc.top,
        1);
  }
  return 1;
}

```

## disassembly

```asm
0x180025430  push    rbp
0x180025432  push    rbx
0x180025433  push    rsi
0x180025434  push    rdi
0x180025435  push    r14
0x180025437  mov     rbp, rsp
0x18002543a  sub     rsp, 70h
0x18002543e  mov     rax, cs:__security_cookie
0x180025445  xor     rax, rsp
0x180025448  mov     [rbp+var_10], rax
0x18002544c  lea     rbx, [rcx+0B8h]
0x180025453  mov     rdi, rcx
0x180025456  mov     rcx, rbx; lprcDst
0x180025459  mov     rsi, r8
0x18002545c  call    cs:__imp_CopyRect
0x180025462  test    dword ptr [rdi+0F8h], 800h
0x18002546c  movups  xmm0, xmmword ptr [rbx]
0x18002546f  movaps  xmmword ptr [rbp+rcSrc.left], xmm0
0x180025473  jz      short loc_1800254E0
0x180025475  mov     rcx, [rdi+0B0h]
0x18002547c  test    rcx, rcx
0x18002547f  jz      short loc_1800254E0
0x180025481  test    rsi, rsi
0x180025484  jz      short loc_180025497
0x180025486  add     rcx, 50h ; 'P'; lprcDst
0x18002548a  mov     rdx, rsi; lprcSrc
0x18002548d  call    cs:__imp_CopyRect
0x180025493  movaps  xmm0, xmmword ptr [rbp+rcSrc.left]
0x180025497  movq    rdx, xmm0
0x18002549c  movdqa  xmmword ptr [rbp+rc.left], xmm0
0x1800254a1  mov     r8, rdx
0x1800254a4  lea     rcx, [rbp+rc]; lprc
0x1800254a8  shr     r8, 20h
0x1800254ac  neg     edx; dx
0x1800254ae  neg     r8d; dy
0x1800254b1  call    cs:__imp_OffsetRect
0x1800254b7  mov     rax, [rdi+0B0h]
0x1800254be  lea     rcx, [rbp+rcSrc]; lprc
0x1800254c2  movaps  xmm0, xmmword ptr [rbp+rc.left]
0x1800254c6  movdqu  xmmword ptr [rax+0Ch], xmm0
0x1800254cb  mov     rax, [rdi+0B0h]
0x1800254d2  mov     edx, [rax+24h]
0x1800254d5  dec     edx; dx
0x1800254d7  mov     r8d, edx; dy
0x1800254da  call    cs:__imp_InflateRect
0x1800254e0  lea     r14, [rdi+0D8h]
0x1800254e7  mov     rdx, rsi; lprcSrc2
0x1800254ea  mov     r9, r14; struct tagPOINT *
0x1800254ed  lea     r8, [rbp+X]; lprcDst
0x1800254f1  lea     rcx, [rbp+rcSrc]; lprcSrc
0x1800254f5  call    ?_GetClippingCoordinates@@YAXPEBUtagRECT@@0PEAU1@PEAUtagPOINT@@@Z; _GetClippingCoordinates(tagRECT const *,tagRECT const *,tagRECT *,tagPOINT *)
0x1800254fa  test    dword ptr [rdi+0F8h], 400000h
0x180025504  mov     esi, 1
0x180025509  jnz     short loc_180025575
0x18002550b  mov     rbx, [rdi+0E8h]
0x180025512  test    rbx, rbx
0x180025515  jnz     short loc_18002551F
0x180025517  mov     rbx, rdi
0x18002551a  test    rdi, rdi
0x18002551d  jz      short loc_180025545
0x18002551f  mov     eax, [rbp+var_24]
0x180025522  mov     r8d, [rbp+Y]; Y
0x180025526  sub     eax, r8d
0x180025529  mov     r9d, [rbp+var_28]
0x18002552d  mov     edx, [rbp+X]; X
0x180025530  sub     r9d, edx; nWidth
0x180025533  mov     rcx, [rbx+40h]; hWnd
0x180025537  mov     [rsp+70h+bRepaint], esi; bRepaint
0x18002553b  mov     [rsp+70h+nHeight], eax; nHeight
0x18002553f  call    cs:__imp_MoveWindow
0x180025545  cmp     rbx, rdi
0x180025548  jz      short loc_180025575
0x18002554a  mov     r8d, [rbp+rcSrc.bottom]
0x18002554e  mov     rcx, rdi; this
0x180025551  sub     r8d, [rbp+rcSrc.top]
0x180025555  mov     r9d, [rbp+rcSrc.right]
0x180025559  sub     r9d, [rbp+rcSrc.left]; int
0x18002555d  mov     edx, [r14]; int
0x180025560  mov     [rsp+70h+bRepaint], esi; int
0x180025564  mov     [rsp+70h+nHeight], r8d; int
0x180025569  mov     r8d, [rdi+0DCh]; int
0x180025570  call    ?MoveWindow@CWnd@@QEAAXHHHHH@Z; CWnd::MoveWindow(int,int,int,int,int)
0x180025575  mov     eax, esi
0x180025577  mov     rcx, [rbp+var_10]
0x18002557b  xor     rcx, rsp; StackCookie
0x18002557e  call    __security_check_cookie
0x180025583  add     rsp, 70h
0x180025587  pop     r14
0x180025589  pop     rdi
0x18002558a  pop     rsi
0x18002558b  pop     rbx
0x18002558c  pop     rbp
0x18002558d  retn
```
