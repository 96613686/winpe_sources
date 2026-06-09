# CTitleBar::_ComputeTitleBarRects(tagRECT const *)

- ea: `0x180017a90`
- end: `0x180017b81`
- name: `?_ComputeTitleBarRects@CTitleBar@@AEAAJPEBUtagRECT@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025614`

## callees

- `0x180017a90`
- `0x180017e6c`
- `0x180017ef0`
- `0x180018cf0`
- `0x180018e5c`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017ab7`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017ac7`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017ab7`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017ac7`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180017b76`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180017b76`

## pseudocode

```c
__int64 __fastcall CTitleBar::_ComputeTitleBarRects(HWND *this, const struct tagRECT *a2)
{
  struct tagRECT *v4; // rdi
  struct tagRECT *v5; // r14
  LONG top; // ecx
  LONG right; // edx
  LONG bottom; // r8d
  int v9; // eax
  int v10; // ecx

  if ( !*((_BYTE *)this + 576) )
  {
    v4 = (struct tagRECT *)((char *)this + 836);
    SetRectEmpty((LPRECT)((char *)this + 836));
    v5 = (struct tagRECT *)((char *)this + 852);
    SetRectEmpty((LPRECT)((char *)this + 852));
    CTitleBar::UpdateBorderVisibilityAndMargins((CTitleBar *)this);
    if ( a2 )
    {
      top = a2->top;
      right = a2->right;
      bottom = a2->bottom;
      v4->left = a2->left;
      v4->top = top;
      v4->right = right;
      v4->bottom = bottom;
    }
    else
    {
      GetClientRect(this[63], v4);
    }
    v9 = 32 * *((_DWORD *)this + 132);
    *v5 = *v4;
    *((_DWORD *)this + 216) = *((_DWORD *)this + 214) - (int)(float)((float)v9 / -100.0);
    v10 = *((_DWORD *)this + 157);
    *((_DWORD *)this + 215) -= *((_DWORD *)this + 213);
    *((_DWORD *)this + 216) += v10 - *((_DWORD *)this + 214);
    *((_DWORD *)this + 214) = v10;
    v5->left = 0;
    CTitleBar::_ComputeLayoutRects((CTitleBar *)this);
    CTitleBar::_ComputeHitTestRects((CTitleBar *)this);
    CTitleBar::_UpdateDwmFrameInset((CTitleBar *)this);
  }
  return 0;
}

```

## disassembly

```asm
0x180017a90  push    rbx
0x180017a92  push    rsi
0x180017a93  push    rdi
0x180017a94  push    r14
0x180017a96  sub     rsp, 28h
0x180017a9a  cmp     byte ptr [rcx+240h], 0
0x180017aa1  mov     rsi, rdx
0x180017aa4  mov     rbx, rcx
0x180017aa7  jnz     loc_180017B60
0x180017aad  lea     rdi, [rcx+344h]
0x180017ab4  mov     rcx, rdi; lprc
0x180017ab7  call    cs:__imp_SetRectEmpty
0x180017abd  lea     r14, [rbx+354h]
0x180017ac4  mov     rcx, r14; lprc
0x180017ac7  call    cs:__imp_SetRectEmpty
0x180017acd  mov     rcx, rbx; this
0x180017ad0  call    ?UpdateBorderVisibilityAndMargins@CTitleBar@@AEAA_NXZ; CTitleBar::UpdateBorderVisibilityAndMargins(void)
0x180017ad5  test    rsi, rsi
0x180017ad8  jz      loc_180017B6C
0x180017ade  mov     ecx, [rsi+4]
0x180017ae1  mov     edx, [rsi+8]
0x180017ae4  mov     r8d, [rsi+0Ch]
0x180017ae8  mov     eax, [rsi]
0x180017aea  mov     [rdi], eax
0x180017aec  mov     [rdi+4], ecx
0x180017aef  mov     [rdi+8], edx
0x180017af2  mov     [rdi+0Ch], r8d
0x180017af6  movups  xmm0, xmmword ptr [rdi]
0x180017af9  mov     eax, [rbx+210h]
0x180017aff  shl     eax, 5
0x180017b02  movdqu  xmmword ptr [r14], xmm0
0x180017b07  mov     ecx, [rbx+358h]
0x180017b0d  movd    xmm0, eax
0x180017b11  cvtdq2ps xmm0, xmm0
0x180017b14  divss   xmm0, cs:__real@c2c80000
0x180017b1c  cvttss2si eax, xmm0
0x180017b20  sub     ecx, eax
0x180017b22  mov     [r14+0Ch], ecx
0x180017b26  mov     ecx, [rbx+274h]
0x180017b2c  mov     eax, [r14]
0x180017b2f  sub     [r14+8], eax
0x180017b33  mov     eax, ecx
0x180017b35  sub     eax, [r14+4]
0x180017b39  add     [r14+0Ch], eax
0x180017b3d  mov     [r14+4], ecx
0x180017b41  mov     rcx, rbx; this
0x180017b44  mov     dword ptr [r14], 0
0x180017b4b  call    ?_ComputeLayoutRects@CTitleBar@@AEAAXXZ; CTitleBar::_ComputeLayoutRects(void)
0x180017b50  mov     rcx, rbx; this
0x180017b53  call    ?_ComputeHitTestRects@CTitleBar@@AEAAXXZ; CTitleBar::_ComputeHitTestRects(void)
0x180017b58  mov     rcx, rbx; this
0x180017b5b  call    ?_UpdateDwmFrameInset@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateDwmFrameInset(void)
0x180017b60  xor     eax, eax
0x180017b62  add     rsp, 28h
0x180017b66  pop     r14
0x180017b68  pop     rdi
0x180017b69  pop     rsi
0x180017b6a  pop     rbx
0x180017b6b  retn
0x180017b6c  mov     rcx, [rbx+1F8h]; hWnd
0x180017b73  mov     rdx, rdi; lpRect
0x180017b76  call    cs:__imp_GetClientRect
0x180017b7c  jmp     loc_180017AF6
```
