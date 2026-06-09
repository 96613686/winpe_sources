# XHDC::DrawControl(CRectF const &,uint,uint)

- ea: `0x180b2dbb0`
- end: `0x180b2de64`
- name: `?DrawControl@XHDC@@UEBAJAEBVCRectF@@II@Z`
- size: `692`
- prototype: `__int64 __fastcall(XHDC *__hidden this, const struct CRectF *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18008681c`
- `0x180b2ab80`
- `0x180b2c71c`
- `0x180b2d1a8`
- `0x180b2dbb0`
- `0x180b2e0e0`
- `0x180b2f324`
- `0x1810c2d60`

## import_xrefs

- `GDI32!DeleteDC` at `0x180b2dde5`
- `GDI32!DeleteDC` at `0x180b2de01`
- `GDI32!DeleteDC` at `0x180b2dde5`
- `GDI32!DeleteDC` at `0x180b2de01`
- `GDI32!GetTextColor` at `0x180b2dc96`
- `GDI32!GetTextColor` at `0x180b2dc96`
- `GDI32!GetBkColor` at `0x180b2dc89`
- `GDI32!GetBkColor` at `0x180b2dc89`
- `GDI32!DeleteObject` at `0x180b2ddf0`
- `GDI32!DeleteObject` at `0x180b2ddf9`
- `GDI32!DeleteObject` at `0x180b2ddf0`
- `GDI32!DeleteObject` at `0x180b2ddf9`
- `GDI32!SelectObject` at `0x180b2dd43`
- `GDI32!SelectObject` at `0x180b2dddc`
- `GDI32!SelectObject` at `0x180b2dd43`
- `GDI32!SelectObject` at `0x180b2dddc`
- `GDI32!GetDeviceCaps` at `0x180b2dc12`
- `GDI32!GetDeviceCaps` at `0x180b2dc23`
- `GDI32!GetDeviceCaps` at `0x180b2dc12`
- `GDI32!GetDeviceCaps` at `0x180b2dc23`
- `GDI32!BitBlt` at `0x180b2dd73`
- `GDI32!BitBlt` at `0x180b2dd73`
- `GDI32!CreateCompatibleBitmap` at `0x180b2dd19`
- `GDI32!CreateCompatibleBitmap` at `0x180b2dd19`
- `GDI32!CreateCompatibleDC` at `0x180b2dce9`
- `GDI32!CreateCompatibleDC` at `0x180b2dce9`
- `GDI32!SetTextColor` at `0x180b2dcb5`
- `GDI32!SetTextColor` at `0x180b2de39`
- `GDI32!SetTextColor` at `0x180b2dcb5`
- `GDI32!SetTextColor` at `0x180b2de39`
- `GDI32!SetBkColor` at `0x180b2dca9`
- `GDI32!SetBkColor` at `0x180b2de2b`
- `GDI32!SetBkColor` at `0x180b2dca9`
- `GDI32!SetBkColor` at `0x180b2de2b`
- `USER32!DrawFrameControl` at `0x180b2dd8b`
- `USER32!DrawFrameControl` at `0x180b2dd8b`

## pseudocode

```c
__int64 __fastcall XHDC::DrawControl(HDC *this, const struct CRectF *a2, UINT a3, UINT a4)
{
  int DeviceCaps; // ebx
  int v6; // eax
  int v7; // r14d
  COLORREF BkColor; // r13d
  unsigned int ObjectType; // eax
  HDC hdcSrc; // rsi
  LONG cy; // r15d
  LONG v13; // r12d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v15; // rbx
  const struct CWorldTransform *v16; // r8
  const struct XHDC *v17; // rax
  COLORREF color; // [rsp+60h] [rbp-A8h]
  struct tagRECT color_8; // [rsp+68h] [rbp-A0h] BYREF
  HGDIOBJ ho; // [rsp+78h] [rbp-90h]
  struct tagRECT v23; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v24[240]; // [rsp+98h] [rbp-70h] BYREF

  DeviceCaps = GetDeviceCaps(this[4], 2);
  v6 = GetDeviceCaps(this[4], 24);
  color_8 = 0;
  v7 = v6;
  CRect::SetRect((CRect *)&color_8, *(float *)a2, *((float *)a2 + 1), *((float *)a2 + 2), *((float *)a2 + 3), 0);
  if ( DeviceCaps && DeviceCaps != 2 && DeviceCaps != 5 )
    return 1;
  if ( v7 == 2 )
  {
    BkColor = GetBkColor(this[4]);
    color = GetTextColor(this[4]);
    SetBkColor(this[4], 0xFFFFFFu);
    SetTextColor(this[4], 0);
  }
  else
  {
    BkColor = 0;
    color = 0;
  }
  ObjectType = XHDC::GetObjectType((XHDC *)this);
  if ( (ObjectType == 4 || ObjectType == 12) && v7 == 2 )
  {
    hdcSrc = CreateCompatibleDC(this[4]);
    if ( hdcSrc )
    {
      cy = color_8.bottom - color_8.top;
      v13 = color_8.right - color_8.left;
      CompatibleBitmap = CreateCompatibleBitmap(this[4], color_8.right - color_8.left, color_8.bottom - color_8.top);
      ho = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v23.right = v13;
        *(_QWORD *)&v23.left = 0;
        v23.bottom = cy;
        v15 = SelectObject(hdcSrc, CompatibleBitmap);
        BitBlt(hdcSrc, 0, 0, v13, cy, hdcSrc, 0, 0, 0xFF0062u);
        DrawFrameControl(hdcSrc, &v23, a3, a4);
        v17 = XHDC::XHDC((XHDC *)v24, hdcSrc, v16);
        XHDC::BitBlt((XHDC *)this, color_8.left, color_8.top, v13, cy, v17, 0, 0, 0xCC0020u);
        XHDC::~XHDC((XHDC *)v24);
        SelectObject(hdcSrc, v15);
        DeleteDC(hdcSrc);
        DeleteObject(ho);
        DeleteObject(v15);
LABEL_16:
        SetBkColor(this[4], BkColor);
        SetTextColor(this[4], color);
        return 0;
      }
      DeleteDC(hdcSrc);
    }
  }
  XHDC::DrawFrameControl((XHDC *)this, &color_8, a3, a4);
  if ( v7 == 2 )
    goto LABEL_16;
  return 0;
}

```

## disassembly

```asm
0x180b2dbb0  mov     rax, rsp
0x180b2dbb3  mov     [rax+20h], r9d
0x180b2dbb7  mov     [rax+18h], r8d
0x180b2dbbb  mov     [rax+10h], rdx
0x180b2dbbf  mov     [rax+8], rcx
0x180b2dbc3  push    rbp
0x180b2dbc4  push    rbx
0x180b2dbc5  push    rsi
0x180b2dbc6  push    rdi
0x180b2dbc7  push    r12
0x180b2dbc9  push    r13
0x180b2dbcb  push    r14
0x180b2dbcd  push    r15
0x180b2dbcf  lea     rbp, [rax-0D8h]
0x180b2dbd6  sub     rsp, 198h
0x180b2dbdd  mov     rax, cs:__security_cookie
0x180b2dbe4  xor     rax, rsp
0x180b2dbe7  mov     [rbp+0D0h+var_50], rax
0x180b2dbee  mov     eax, [rbp+0D0h+arg_10]
0x180b2dbf4  mov     edx, 2; index
0x180b2dbf9  mov     rdi, [rbp+0D0h+arg_0]
0x180b2dc00  mov     [rsp+54h], eax
0x180b2dc04  mov     eax, [rbp+0D0h+arg_18]
0x180b2dc0a  mov     [rsp+1D0h+var_180], eax
0x180b2dc0e  mov     rcx, [rdi+20h]; hdc
0x180b2dc12  call    cs:__imp_GetDeviceCaps
0x180b2dc18  mov     rcx, [rdi+20h]; hdc
0x180b2dc1c  mov     edx, 18h; index
0x180b2dc21  mov     ebx, eax
0x180b2dc23  call    cs:__imp_GetDeviceCaps
0x180b2dc29  mov     rcx, [rbp+0D0h+arg_8]
0x180b2dc30  xorps   xmm0, xmm0
0x180b2dc33  movdqu  xmmword ptr [rsp+1D0h+color+8], xmm0
0x180b2dc39  mov     dword ptr [rsp+1D0h+hdcSrc], 0; int
0x180b2dc41  mov     r14d, eax
0x180b2dc44  movss   xmm0, dword ptr [rcx+0Ch]
0x180b2dc49  movss   xmm3, dword ptr [rcx+8]; float
0x180b2dc4e  movss   xmm2, dword ptr [rcx+4]; float
0x180b2dc53  movss   xmm1, dword ptr [rcx]; float
0x180b2dc57  lea     rcx, [rsp+1D0h+color+8]; this
0x180b2dc5c  movss   [rsp+1D0h+cy], xmm0; float
0x180b2dc62  call    ?SetRect@CRect@@QEAAXMMMMH@Z; CRect::SetRect(float,float,float,float,int)
0x180b2dc67  test    ebx, ebx
0x180b2dc69  jz      short loc_180B2DC7F
0x180b2dc6b  cmp     ebx, 2
0x180b2dc6e  jz      short loc_180B2DC7F
0x180b2dc70  cmp     ebx, 5
0x180b2dc73  jz      short loc_180B2DC7F
0x180b2dc75  mov     eax, 1
0x180b2dc7a  jmp     loc_180B2DE41
0x180b2dc7f  cmp     r14d, 2
0x180b2dc83  jnz     short loc_180B2DCBD
0x180b2dc85  mov     rcx, [rdi+20h]; hdc
0x180b2dc89  call    cs:__imp_GetBkColor
0x180b2dc8f  mov     rcx, [rdi+20h]; hdc
0x180b2dc93  mov     r13d, eax
0x180b2dc96  call    cs:__imp_GetTextColor
0x180b2dc9c  mov     rcx, [rdi+20h]; hdc
0x180b2dca0  mov     edx, 0FFFFFFh; color
0x180b2dca5  mov     [rsp+1D0h+color], eax
0x180b2dca9  call    cs:__imp_SetBkColor
0x180b2dcaf  mov     rcx, [rdi+20h]; hdc
0x180b2dcb3  xor     edx, edx; color
0x180b2dcb5  call    cs:__imp_SetTextColor
0x180b2dcbb  jmp     short loc_180B2DCC5
0x180b2dcbd  xor     r13d, r13d
0x180b2dcc0  mov     [rsp+1D0h+color], r13d
0x180b2dcc5  mov     rcx, rdi; this
0x180b2dcc8  call    ?GetObjectType@XHDC@@QEBAKXZ; XHDC::GetObjectType(void)
0x180b2dccd  cmp     eax, 4
0x180b2dcd0  jz      short loc_180B2DCDB
0x180b2dcd2  cmp     eax, 0Ch
0x180b2dcd5  jnz     loc_180B2DE07
0x180b2dcdb  cmp     r14d, 2
0x180b2dcdf  jnz     loc_180B2DE07
0x180b2dce5  mov     rcx, [rdi+20h]; hdc
0x180b2dce9  call    cs:__imp_CreateCompatibleDC
0x180b2dcef  mov     rsi, rax
0x180b2dcf2  test    rax, rax
0x180b2dcf5  jz      loc_180B2DE07
0x180b2dcfb  mov     r15d, dword ptr [rsp+1D0h+var_168+4]
0x180b2dd00  mov     r12d, dword ptr [rsp+1D0h+var_168]
0x180b2dd05  sub     r15d, [rsp+1D0h+color+0Ch]
0x180b2dd0a  sub     r12d, [rsp+1D0h+color+8]
0x180b2dd0f  mov     r8d, r15d; cy
0x180b2dd12  mov     rcx, [rdi+20h]; hdc
0x180b2dd16  mov     edx, r12d; cx
0x180b2dd19  call    cs:__imp_CreateCompatibleBitmap
0x180b2dd1f  mov     [rsp+1D0h+ho], rax
0x180b2dd24  mov     rcx, rsi; hdc
0x180b2dd27  test    rax, rax
0x180b2dd2a  jz      loc_180B2DE01
0x180b2dd30  xor     r14d, r14d
0x180b2dd33  mov     [rbp+0D0h+var_158.right], r12d
0x180b2dd37  mov     rdx, rax; h
0x180b2dd3a  mov     qword ptr [rsp+1D0h+var_158.left], r14
0x180b2dd3f  mov     [rbp+0D0h+var_158.bottom], r15d
0x180b2dd43  call    cs:__imp_SelectObject
0x180b2dd49  mov     dword ptr [rsp+40h], 0FF0062h; rop
0x180b2dd51  mov     r9d, r12d; cx
0x180b2dd54  mov     [rsp+1D0h+y1], r14d; y1
0x180b2dd59  xor     r8d, r8d; y
0x180b2dd5c  mov     [rsp+1D0h+x1], r14d; x1
0x180b2dd61  xor     edx, edx; x
0x180b2dd63  mov     [rsp+1D0h+hdcSrc], rsi; hdcSrc
0x180b2dd68  mov     rcx, rsi; hdc
0x180b2dd6b  mov     [rsp+1D0h+cy], r15d; cy
0x180b2dd70  mov     rbx, rax
0x180b2dd73  call    cs:__imp_BitBlt
0x180b2dd79  mov     r9d, [rsp+1D0h+var_180]; UINT
0x180b2dd7e  lea     rdx, [rsp+1D0h+var_158]; LPRECT
0x180b2dd83  mov     r8d, [rsp+54h]; UINT
0x180b2dd88  mov     rcx, rsi; HDC
0x180b2dd8b  call    cs:__imp_DrawFrameControl
0x180b2dd91  mov     rdx, rsi; HDC
0x180b2dd94  lea     rcx, [rbp+0D0h+var_140]; this
0x180b2dd98  call    ??0XHDC@@QEAA@PEAUHDC__@@PEBVCWorldTransform@@@Z; XHDC::XHDC(HDC__ *,CWorldTransform const *)
0x180b2dd9d  mov     r8d, [rsp+1D0h+color+0Ch]; int
0x180b2dda2  mov     r9d, r12d; int
0x180b2dda5  mov     edx, [rsp+1D0h+color+8]; int
0x180b2dda9  mov     rcx, rdi; this
0x180b2ddac  mov     dword ptr [rsp+40h], 0CC0020h; unsigned int
0x180b2ddb4  mov     [rsp+1D0h+y1], r14d; int
0x180b2ddb9  mov     [rsp+1D0h+x1], r14d; int
0x180b2ddbe  mov     [rsp+1D0h+hdcSrc], rax; struct XHDC *
0x180b2ddc3  mov     [rsp+1D0h+cy], r15d; int
0x180b2ddc8  call    ?BitBlt@XHDC@@QEBAHHHHHAEBV1@HHK@Z; XHDC::BitBlt(int,int,int,int,XHDC const &,int,int,ulong)
0x180b2ddcd  lea     rcx, [rbp+0D0h+var_140]; this
0x180b2ddd1  call    ??1XHDC@@QEAA@XZ; XHDC::~XHDC(void)
0x180b2ddd6  mov     rdx, rbx; h
0x180b2ddd9  mov     rcx, rsi; hdc
0x180b2dddc  call    cs:__imp_SelectObject
0x180b2dde2  mov     rcx, rsi; hdc
0x180b2dde5  call    cs:__imp_DeleteDC
0x180b2ddeb  mov     rcx, [rsp+1D0h+ho]; ho
0x180b2ddf0  call    cs:__imp_DeleteObject
0x180b2ddf6  mov     rcx, rbx; ho
0x180b2ddf9  call    cs:__imp_DeleteObject
0x180b2ddff  jmp     short loc_180B2DE24
0x180b2de01  call    cs:__imp_DeleteDC
0x180b2de07  mov     r9d, [rsp+1D0h+var_180]; unsigned int
0x180b2de0c  lea     rdx, [rsp+1D0h+color+8]; struct tagRECT *
0x180b2de11  mov     r8d, [rsp+54h]; unsigned int
0x180b2de16  mov     rcx, rdi; this
0x180b2de19  call    ?DrawFrameControl@XHDC@@QEBAHPEAUtagRECT@@II@Z; XHDC::DrawFrameControl(tagRECT *,uint,uint)
0x180b2de1e  cmp     r14d, 2
0x180b2de22  jnz     short loc_180B2DE3F
0x180b2de24  mov     rcx, [rdi+20h]; hdc
0x180b2de28  mov     edx, r13d; color
0x180b2de2b  call    cs:__imp_SetBkColor
0x180b2de31  mov     edx, [rsp+1D0h+color]; color
0x180b2de35  mov     rcx, [rdi+20h]; hdc
0x180b2de39  call    cs:__imp_SetTextColor
0x180b2de3f  xor     eax, eax
0x180b2de41  mov     rcx, [rbp+0D0h+var_50]
0x180b2de48  xor     rcx, rsp; StackCookie
0x180b2de4b  call    __security_check_cookie
0x180b2de50  add     rsp, 198h
0x180b2de57  pop     r15
0x180b2de59  pop     r14
0x180b2de5b  pop     r13
0x180b2de5d  pop     r12
0x180b2de5f  pop     rdi
0x180b2de60  pop     rsi
0x180b2de61  pop     rbx
0x180b2de62  pop     rbp
0x180b2de63  retn
```
