# HrValidatePixelRects(WICRect const *,uint,uint,WICRect *,tagRECT *)

- ea: `0x180023620`
- end: `0x1800237c8`
- name: `?HrValidatePixelRects@@YAJPEBUWICRect@@IIPEAU1@PEAUtagRECT@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(const struct WICRect *, unsigned int, unsigned int, struct WICRect *, struct tagRECT *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180021e30`
- `0x180022730`
- `0x180022f30`
- `0x1800381f0`
- `0x18003c170`
- `0x18007ded0`

## callees

- `0x180023620`
- `0x1800bd9d4`
- `0x1800e5e60`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18002372b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18002372b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002373b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002373b`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180023753`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180023753`

## pseudocode

```c
__int64 __fastcall HrValidatePixelRects(
        const struct WICRect *a1,
        unsigned int a2,
        unsigned int a3,
        struct WICRect *a4,
        struct tagRECT *a5)
{
  int Height; // ebx
  int Width; // edi
  unsigned int v8; // ebx
  INT X; // r14d
  INT Y; // r15d
  RECT v11; // xmm0
  RECT rcSrc2; // [rsp+20h] [rbp-48h] BYREF
  RECT rcSrc1; // [rsp+30h] [rbp-38h] BYREF
  tagRECT rcDst; // [rsp+40h] [rbp-28h] BYREF

  rcSrc1.bottom = 0;
  *(_QWORD *)&rcSrc1.left = 0;
  Height = a3;
  Width = a2;
  rcDst = 0;
  if ( a2 > 0x7FFFFFFF )
  {
    rcSrc1.right = -1;
LABEL_3:
    v8 = -2147024362;
    goto LABEL_4;
  }
  rcSrc1.right = a2;
  if ( a3 > 0x7FFFFFFF )
  {
    rcSrc1.bottom = -1;
    goto LABEL_3;
  }
  rcSrc1.bottom = a3;
  if ( !a1 )
  {
    v11 = rcSrc1;
    X = 0;
    Y = 0;
    goto LABEL_23;
  }
  X = a1->X;
  Y = a1->Y;
  rcSrc2.bottom = 0;
  rcSrc2.left = X;
  rcSrc2.top = Y;
  if ( X < 0 )
    goto LABEL_18;
  Width = a1->Width;
  if ( Width < 0 || X + Width < (unsigned int)X )
    goto LABEL_18;
  if ( (unsigned int)(X + Width) > 0x7FFFFFFF )
  {
    rcSrc2.right = -1;
    goto LABEL_18;
  }
  rcSrc2.right = X + Width;
  if ( Y < 0 || (Height = a1->Height, Height < 0) || Height + Y < (unsigned int)Y )
  {
LABEL_18:
    v8 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      return v8;
    goto LABEL_5;
  }
  if ( (unsigned int)(Height + Y) > 0x7FFFFFFF )
  {
    rcSrc2.bottom = -1;
    goto LABEL_3;
  }
  rcSrc2.bottom = Height + Y;
  IntersectRect(&rcDst, &rcSrc1, &rcSrc2);
  if ( !IsRectEmpty(&rcSrc2) && EqualRect(&rcDst, &rcSrc2) )
  {
    v11 = rcDst;
LABEL_23:
    if ( a4 )
    {
      a4->X = X;
      a4->Y = Y;
      a4->Width = Width;
      a4->Height = Height;
    }
    v8 = 0;
    if ( a5 )
      *a5 = v11;
    return v8;
  }
  v8 = -2147024809;
LABEL_4:
  if ( (_DWORD)g_doStackCaptures )
LABEL_5:
    DoStackCapture(v8);
  return v8;
}

```

## disassembly

```asm
0x180023620  push    rbp
0x180023622  push    rbx
0x180023623  push    rsi
0x180023624  push    rdi
0x180023625  push    r12
0x180023627  push    r13
0x180023629  push    r14
0x18002362b  push    r15
0x18002362d  mov     rbp, rsp
0x180023630  sub     rsp, 68h
0x180023634  mov     rax, cs:__security_cookie
0x18002363b  xor     rax, rsp
0x18002363e  mov     [rbp+var_18], rax
0x180023642  mov     r12, [rbp+arg_20]
0x180023646  xor     r13d, r13d
0x180023649  mov     [rbp+rcSrc1.bottom], r13d
0x18002364d  xorps   xmm0, xmm0
0x180023650  mov     qword ptr [rbp+rcSrc1.left], r13
0x180023654  mov     rsi, r9
0x180023657  mov     ebx, r8d
0x18002365a  mov     edi, edx
0x18002365c  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180023660  cmp     edx, 7FFFFFFFh
0x180023666  jbe     short loc_18002368D
0x180023668  mov     [rbp+rcSrc1.right], 0FFFFFFFFh
0x18002366f  mov     ebx, 80070216h
0x180023674  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18002367b  jz      loc_180023786
0x180023681  mov     ecx, ebx; int
0x180023683  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023688  jmp     loc_180023786
0x18002368d  mov     [rbp+rcSrc1.right], edx
0x180023690  cmp     ebx, 7FFFFFFFh
0x180023696  ja      loc_1800237A6
0x18002369c  mov     [rbp+rcSrc1.bottom], ebx
0x18002369f  test    rcx, rcx
0x1800236a2  jz      loc_1800237BC
0x1800236a8  mov     r14d, [rcx]
0x1800236ab  mov     r15d, [rcx+4]
0x1800236af  mov     [rbp+rcSrc2.bottom], r13d
0x1800236b3  mov     [rbp+rcSrc2.left], r14d
0x1800236b7  mov     [rbp+rcSrc2.top], r15d
0x1800236bb  test    r14d, r14d
0x1800236be  js      short loc_180023709
0x1800236c0  mov     edi, [rcx+8]
0x1800236c3  test    edi, edi
0x1800236c5  js      short loc_180023709
0x1800236c7  lea     eax, [r14+rdi]
0x1800236cb  cmp     eax, r14d
0x1800236ce  jb      short loc_180023709
0x1800236d0  cmp     eax, 7FFFFFFFh
0x1800236d5  ja      short loc_180023702
0x1800236d7  mov     [rbp+rcSrc2.right], eax
0x1800236da  test    r15d, r15d
0x1800236dd  js      short loc_180023709
0x1800236df  mov     ebx, [rcx+0Ch]
0x1800236e2  test    ebx, ebx
0x1800236e4  js      short loc_180023709
0x1800236e6  lea     eax, [rbx+r15]
0x1800236ea  cmp     eax, r15d
0x1800236ed  jb      short loc_180023709
0x1800236ef  cmp     eax, 7FFFFFFFh
0x1800236f4  jbe     short loc_18002371C
0x1800236f6  mov     [rbp+rcSrc2.bottom], 0FFFFFFFFh
0x1800236fd  jmp     loc_18002366F
0x180023702  mov     [rbp+rcSrc2.right], 0FFFFFFFFh
0x180023709  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180023710  mov     ebx, 80070216h
0x180023715  jz      short loc_180023786
0x180023717  jmp     loc_180023681
0x18002371c  lea     r8, [rbp+rcSrc2]; lprcSrc2
0x180023720  mov     [rbp+rcSrc2.bottom], eax
0x180023723  lea     rdx, [rbp+rcSrc1]; lprcSrc1
0x180023727  lea     rcx, [rbp+rcDst]; lprcDst
0x18002372b  call    cs:__imp_IntersectRect
0x180023732  nop     dword ptr [rax+rax+00h]
0x180023737  lea     rcx, [rbp+rcSrc2]; lprc
0x18002373b  call    cs:__imp_IsRectEmpty
0x180023742  nop     dword ptr [rax+rax+00h]
0x180023747  test    eax, eax
0x180023749  jnz     short loc_1800237B2
0x18002374b  lea     rdx, [rbp+rcSrc2]; lprc2
0x18002374f  lea     rcx, [rbp+rcDst]; lprc1
0x180023753  call    cs:__imp_EqualRect
0x18002375a  nop     dword ptr [rax+rax+00h]
0x18002375f  test    eax, eax
0x180023761  jz      short loc_1800237B2
0x180023763  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x180023767  test    rsi, rsi
0x18002376a  jz      short loc_180023779
0x18002376c  mov     [rsi], r14d
0x18002376f  mov     [rsi+4], r15d
0x180023773  mov     [rsi+8], edi
0x180023776  mov     [rsi+0Ch], ebx
0x180023779  mov     ebx, r13d
0x18002377c  test    r12, r12
0x18002377f  jz      short loc_180023786
0x180023781  movups  xmmword ptr [r12], xmm0
0x180023786  mov     eax, ebx
0x180023788  mov     rcx, [rbp+var_18]
0x18002378c  xor     rcx, rsp; StackCookie
0x18002378f  call    __security_check_cookie
0x180023794  add     rsp, 68h
0x180023798  pop     r15
0x18002379a  pop     r14
0x18002379c  pop     r13
0x18002379e  pop     r12
0x1800237a0  pop     rdi
0x1800237a1  pop     rsi
0x1800237a2  pop     rbx
0x1800237a3  pop     rbp
0x1800237a4  retn
0x1800237a6  mov     [rbp+rcSrc1.bottom], 0FFFFFFFFh
0x1800237ad  jmp     loc_18002366F
0x1800237b2  mov     ebx, 80070057h
0x1800237b7  jmp     loc_180023674
0x1800237bc  movaps  xmm0, xmmword ptr [rbp+rcSrc1.left]
0x1800237c0  mov     r14d, r13d
0x1800237c3  mov     r15d, r13d
0x1800237c6  jmp     short loc_180023767
```
