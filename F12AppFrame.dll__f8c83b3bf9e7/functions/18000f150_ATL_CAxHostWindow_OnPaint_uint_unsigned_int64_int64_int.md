# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x18000f150`
- end: `0x18000f3b7`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f900`

## callees

- `0x180001800`
- `0x180002678`
- `0x18000f150`
- `0x180035010`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18000f232`
- `GDI32!CreateSolidBrush` at `0x18000f378`
- `GDI32!CreateSolidBrush` at `0x18000f232`
- `GDI32!CreateSolidBrush` at `0x18000f378`
- `GDI32!CreateCompatibleDC` at `0x18000f202`
- `GDI32!CreateCompatibleDC` at `0x18000f202`
- `GDI32!CreateCompatibleBitmap` at `0x18000f1ed`
- `GDI32!CreateCompatibleBitmap` at `0x18000f1ed`
- `GDI32!SelectObject` at `0x18000f21a`
- `GDI32!SelectObject` at `0x18000f2f1`
- `GDI32!SelectObject` at `0x18000f21a`
- `GDI32!SelectObject` at `0x18000f2f1`
- `GDI32!DeleteObject` at `0x18000f257`
- `GDI32!DeleteObject` at `0x18000f399`
- `GDI32!DeleteObject` at `0x18000f257`
- `GDI32!DeleteObject` at `0x18000f399`
- `GDI32!DeleteDC` at `0x18000f2fa`
- `GDI32!DeleteDC` at `0x18000f2fa`
- `GDI32!BitBlt` at `0x18000f2e5`
- `GDI32!BitBlt` at `0x18000f2e5`
- `USER32!GetClientRect` at `0x18000f1d6`
- `USER32!GetClientRect` at `0x18000f36c`
- `USER32!GetClientRect` at `0x18000f1d6`
- `USER32!GetClientRect` at `0x18000f36c`
- `USER32!FillRect` at `0x18000f24e`
- `USER32!FillRect` at `0x18000f390`
- `USER32!FillRect` at `0x18000f24e`
- `USER32!FillRect` at `0x18000f390`
- `USER32!EndPaint` at `0x18000f3a7`
- `USER32!EndPaint` at `0x18000f3a7`
- `USER32!BeginPaint` at `0x18000f1b5`
- `USER32!BeginPaint` at `0x18000f34f`
- `USER32!BeginPaint` at `0x18000f1b5`
- `USER32!BeginPaint` at `0x18000f34f`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPaint(ATL::CAxHostWindow *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HDC v6; // rsi
  HWND v7; // rcx
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // r15
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // r12
  HBITMAP v14; // rcx
  HDC v16; // rsi
  HWND v17; // rcx
  HBRUSH v18; // rax
  HBRUSH v19; // rdi
  struct tagRECT Rect; // [rsp+60h] [rbp-41h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+70h] [rbp-31h] BYREF

  if ( *((_QWORD *)this + 28) )
  {
    if ( (*((_BYTE *)this + 280) & 8) != 0 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      v6 = BeginPaint(*((HWND *)this + 1), &Paint);
      if ( v6 )
      {
        v7 = (HWND)*((_QWORD *)this + 1);
        Rect = 0;
        GetClientRect(v7, &Rect);
        CompatibleBitmap = CreateCompatibleBitmap(v6, Rect.right - Rect.left, Rect.bottom - Rect.top);
        if ( CompatibleBitmap )
        {
          CompatibleDC = CreateCompatibleDC(v6);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            v11 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( v11 )
            {
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 85));
              v13 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v13);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  1,
                  0xFFFFFFFFLL);
                BitBlt(v6, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u);
              }
              SelectObject(hdcSrc, v11);
            }
            DeleteDC(hdcSrc);
          }
          v14 = CompatibleBitmap;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 0;
  }
  memset_0(&Paint, 0, sizeof(Paint));
  v16 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( !v16 )
    return 0;
  v17 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  GetClientRect(v17, &Rect);
  v18 = CreateSolidBrush(*((_DWORD *)this + 85));
  v19 = v18;
  if ( v18 )
  {
    FillRect(v16, &Rect, v18);
    v14 = (HBITMAP)v19;
LABEL_17:
    DeleteObject(v14);
  }
LABEL_18:
  EndPaint(*((HWND *)this + 1), &Paint);
  return 1;
}

```

## disassembly

```asm
0x18000f150  mov     [rsp-8+arg_8], rbx
0x18000f155  mov     [rsp-8+arg_10], rsi
0x18000f15a  push    rbp
0x18000f15b  push    rdi
0x18000f15c  push    r12
0x18000f15e  push    r14
0x18000f160  push    r15
0x18000f162  lea     rbp, [rsp-2Fh]
0x18000f167  sub     rsp, 0D0h
0x18000f16e  mov     rax, cs:__security_cookie
0x18000f175  xor     rax, rsp
0x18000f178  mov     [rbp+4Fh+var_30], rax
0x18000f17c  cmp     qword ptr [rcx+0E0h], 0
0x18000f184  mov     rbx, rcx
0x18000f187  mov     rax, [rbp+4Fh+arg_20]
0x18000f18b  jz      loc_18000F338
0x18000f191  test    byte ptr [rcx+118h], 8
0x18000f198  jz      loc_18000F308
0x18000f19e  xor     edx, edx; Val
0x18000f1a0  lea     rcx, [rbp+4Fh+Paint]; void *
0x18000f1a4  lea     r8d, [rdx+48h]; Size
0x18000f1a8  call    memset_0
0x18000f1ad  mov     rcx, [rbx+8]; hWnd
0x18000f1b1  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x18000f1b5  call    cs:__imp_BeginPaint
0x18000f1bb  mov     rsi, rax
0x18000f1be  test    rax, rax
0x18000f1c1  jz      loc_18000F30E
0x18000f1c7  mov     rcx, [rbx+8]; hWnd
0x18000f1cb  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x18000f1cf  xorps   xmm0, xmm0
0x18000f1d2  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x18000f1d6  call    cs:__imp_GetClientRect
0x18000f1dc  mov     r8d, [rbp+4Fh+Rect.bottom]
0x18000f1e0  mov     rcx, rsi; hdc
0x18000f1e3  mov     edx, [rbp+4Fh+Rect.right]
0x18000f1e6  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x18000f1ea  sub     edx, [rbp+4Fh+Rect.left]; cx
0x18000f1ed  call    cs:__imp_CreateCompatibleBitmap
0x18000f1f3  mov     r14, rax
0x18000f1f6  test    rax, rax
0x18000f1f9  jz      loc_18000F39F
0x18000f1ff  mov     rcx, rsi; hdc
0x18000f202  call    cs:__imp_CreateCompatibleDC
0x18000f208  mov     rdi, rax
0x18000f20b  test    rax, rax
0x18000f20e  jz      loc_18000F300
0x18000f214  mov     rdx, r14; h
0x18000f217  mov     rcx, rax; hdc
0x18000f21a  call    cs:__imp_SelectObject
0x18000f220  mov     r15, rax
0x18000f223  test    rax, rax
0x18000f226  jz      loc_18000F2F7
0x18000f22c  mov     ecx, [rbx+154h]; color
0x18000f232  call    cs:__imp_CreateSolidBrush
0x18000f238  mov     r12, rax
0x18000f23b  test    rax, rax
0x18000f23e  jz      loc_18000F2EB
0x18000f244  mov     r8, rax; hbr
0x18000f247  lea     rdx, [rbp+4Fh+Rect]; lprc
0x18000f24b  mov     rcx, rdi; hDC
0x18000f24e  call    cs:__imp_FillRect
0x18000f254  mov     rcx, r12; ho
0x18000f257  call    cs:__imp_DeleteObject
0x18000f25d  mov     rcx, [rbx+0E0h]
0x18000f264  lea     rdx, [rbx+134h]
0x18000f26b  mov     [rsp+0F0h+var_A0], 0
0x18000f274  xor     r9d, r9d
0x18000f277  mov     [rsp+0F0h+var_A8], 0
0x18000f280  or      r8d, 0FFFFFFFFh
0x18000f284  mov     qword ptr [rsp+0F0h+rop], rdx
0x18000f289  mov     rax, [rcx]
0x18000f28c  mov     qword ptr [rsp+0F0h+y1], rdx
0x18000f291  lea     edx, [r9+1]
0x18000f295  mov     qword ptr [rsp+0F0h+x1], rdi
0x18000f29a  mov     [rsp+0F0h+hdcSrc], 0
0x18000f2a3  mov     rax, [rax+18h]
0x18000f2a7  mov     qword ptr [rsp+0F0h+cy], 0
0x18000f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b5  mov     eax, [rbp+4Fh+Rect.bottom]
0x18000f2b8  xor     r8d, r8d; y
0x18000f2bb  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x18000f2bf  xor     edx, edx; x
0x18000f2c1  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18000f2c9  mov     rcx, rsi; hdc
0x18000f2cc  mov     [rsp+0F0h+y1], 0; y1
0x18000f2d4  mov     [rsp+0F0h+x1], 0; x1
0x18000f2dc  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x18000f2e1  mov     [rsp+0F0h+cy], eax; cy
0x18000f2e5  call    cs:__imp_BitBlt
0x18000f2eb  mov     rdx, r15; h
0x18000f2ee  mov     rcx, rdi; hdc
0x18000f2f1  call    cs:__imp_SelectObject
0x18000f2f7  mov     rcx, rdi; hdc
0x18000f2fa  call    cs:__imp_DeleteDC
0x18000f300  mov     rcx, r14
0x18000f303  jmp     loc_18000F399
0x18000f308  mov     dword ptr [rax], 0
0x18000f30e  xor     eax, eax
0x18000f310  mov     rcx, [rbp+4Fh+var_30]
0x18000f314  xor     rcx, rsp; StackCookie
0x18000f317  call    __security_check_cookie
0x18000f31c  lea     r11, [rsp+0F0h+var_20]
0x18000f324  mov     rbx, [r11+38h]
0x18000f328  mov     rsi, [r11+40h]
0x18000f32c  mov     rsp, r11
0x18000f32f  pop     r15
0x18000f331  pop     r14
0x18000f333  pop     r12
0x18000f335  pop     rdi
0x18000f336  pop     rbp
0x18000f337  retn
0x18000f338  xor     edx, edx; Val
0x18000f33a  lea     rcx, [rbp+4Fh+Paint]; void *
0x18000f33e  lea     r8d, [rdx+48h]; Size
0x18000f342  call    memset_0
0x18000f347  mov     rcx, [rbx+8]; hWnd
0x18000f34b  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x18000f34f  call    cs:__imp_BeginPaint
0x18000f355  mov     rsi, rax
0x18000f358  test    rax, rax
0x18000f35b  jz      short loc_18000F30E
0x18000f35d  mov     rcx, [rbx+8]; hWnd
0x18000f361  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x18000f365  xorps   xmm0, xmm0
0x18000f368  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x18000f36c  call    cs:__imp_GetClientRect
0x18000f372  mov     ecx, [rbx+154h]; color
0x18000f378  call    cs:__imp_CreateSolidBrush
0x18000f37e  mov     rdi, rax
0x18000f381  test    rax, rax
0x18000f384  jz      short loc_18000F39F
0x18000f386  mov     r8, rax; hbr
0x18000f389  lea     rdx, [rbp+4Fh+Rect]; lprc
0x18000f38d  mov     rcx, rsi; hDC
0x18000f390  call    cs:__imp_FillRect
0x18000f396  mov     rcx, rdi; ho
0x18000f399  call    cs:__imp_DeleteObject
0x18000f39f  mov     rcx, [rbx+8]; hWnd
0x18000f3a3  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x18000f3a7  call    cs:__imp_EndPaint
0x18000f3ad  mov     eax, 1
0x18000f3b2  jmp     loc_18000F310
```
