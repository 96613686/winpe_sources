# HrValidatePixelRects(WICRect const *,uint,uint,WICRect *,tagRECT *)

- ea: `0x180050250`
- end: `0x1800503e5`
- name: `?HrValidatePixelRects@@YAJPEBUWICRect@@IIPEAU1@PEAUtagRECT@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(const struct WICRect *, unsigned int, unsigned int, struct WICRect *, struct tagRECT *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18004ec30`
- `0x18004f3a0`
- `0x18004fb70`
- `0x180069a08`
- `0x1800782b0`
- `0x180097400`

## callees

- `0x180050250`
- `0x1800bb784`
- `0x1800e2f90`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18005035b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x18005035b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180050365`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180050365`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180050377`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180050377`

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
0x180050250  push    rbp
0x180050252  push    rbx
0x180050253  push    rsi
0x180050254  push    rdi
0x180050255  push    r12
0x180050257  push    r13
0x180050259  push    r14
0x18005025b  push    r15
0x18005025d  mov     rbp, rsp
0x180050260  sub     rsp, 68h
0x180050264  mov     rax, cs:__security_cookie
0x18005026b  xor     rax, rsp
0x18005026e  mov     [rbp+var_18], rax
0x180050272  mov     r12, [rbp+arg_20]
0x180050276  xor     r13d, r13d
0x180050279  mov     [rbp+rcSrc1.bottom], r13d
0x18005027d  xorps   xmm0, xmm0
0x180050280  mov     qword ptr [rbp+rcSrc1.left], r13
0x180050284  mov     rsi, r9
0x180050287  mov     ebx, r8d
0x18005028a  mov     edi, edx
0x18005028c  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180050290  cmp     edx, 7FFFFFFFh
0x180050296  jbe     short loc_1800502BD
0x180050298  mov     [rbp+rcSrc1.right], 0FFFFFFFFh
0x18005029f  mov     ebx, 80070216h
0x1800502a4  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800502ab  jz      loc_1800503A4
0x1800502b1  mov     ecx, ebx; int
0x1800502b3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800502b8  jmp     loc_1800503A4
0x1800502bd  mov     [rbp+rcSrc1.right], edx
0x1800502c0  cmp     ebx, 7FFFFFFFh
0x1800502c6  ja      loc_1800503C3
0x1800502cc  mov     [rbp+rcSrc1.bottom], ebx
0x1800502cf  test    rcx, rcx
0x1800502d2  jz      loc_1800503D9
0x1800502d8  mov     r14d, [rcx]
0x1800502db  mov     r15d, [rcx+4]
0x1800502df  mov     [rbp+rcSrc2.bottom], r13d
0x1800502e3  mov     [rbp+rcSrc2.left], r14d
0x1800502e7  mov     [rbp+rcSrc2.top], r15d
0x1800502eb  test    r14d, r14d
0x1800502ee  js      short loc_180050339
0x1800502f0  mov     edi, [rcx+8]
0x1800502f3  test    edi, edi
0x1800502f5  js      short loc_180050339
0x1800502f7  lea     eax, [r14+rdi]
0x1800502fb  cmp     eax, r14d
0x1800502fe  jb      short loc_180050339
0x180050300  cmp     eax, 7FFFFFFFh
0x180050305  ja      short loc_180050332
0x180050307  mov     [rbp+rcSrc2.right], eax
0x18005030a  test    r15d, r15d
0x18005030d  js      short loc_180050339
0x18005030f  mov     ebx, [rcx+0Ch]
0x180050312  test    ebx, ebx
0x180050314  js      short loc_180050339
0x180050316  lea     eax, [rbx+r15]
0x18005031a  cmp     eax, r15d
0x18005031d  jb      short loc_180050339
0x18005031f  cmp     eax, 7FFFFFFFh
0x180050324  jbe     short loc_18005034C
0x180050326  mov     [rbp+rcSrc2.bottom], 0FFFFFFFFh
0x18005032d  jmp     loc_18005029F
0x180050332  mov     [rbp+rcSrc2.right], 0FFFFFFFFh
0x180050339  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180050340  mov     ebx, 80070216h
0x180050345  jz      short loc_1800503A4
0x180050347  jmp     loc_1800502B1
0x18005034c  lea     r8, [rbp+rcSrc2]; lprcSrc2
0x180050350  mov     [rbp+rcSrc2.bottom], eax
0x180050353  lea     rdx, [rbp+rcSrc1]; lprcSrc1
0x180050357  lea     rcx, [rbp+rcDst]; lprcDst
0x18005035b  call    cs:__imp_IntersectRect
0x180050361  lea     rcx, [rbp+rcSrc2]; lprc
0x180050365  call    cs:__imp_IsRectEmpty
0x18005036b  test    eax, eax
0x18005036d  jnz     short loc_1800503CF
0x18005036f  lea     rdx, [rbp+rcSrc2]; lprc2
0x180050373  lea     rcx, [rbp+rcDst]; lprc1
0x180050377  call    cs:__imp_EqualRect
0x18005037d  test    eax, eax
0x18005037f  jz      short loc_1800503CF
0x180050381  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x180050385  test    rsi, rsi
0x180050388  jz      short loc_180050397
0x18005038a  mov     [rsi], r14d
0x18005038d  mov     [rsi+4], r15d
0x180050391  mov     [rsi+8], edi
0x180050394  mov     [rsi+0Ch], ebx
0x180050397  mov     ebx, r13d
0x18005039a  test    r12, r12
0x18005039d  jz      short loc_1800503A4
0x18005039f  movups  xmmword ptr [r12], xmm0
0x1800503a4  mov     eax, ebx
0x1800503a6  mov     rcx, [rbp+var_18]
0x1800503aa  xor     rcx, rsp; StackCookie
0x1800503ad  call    __security_check_cookie
0x1800503b2  add     rsp, 68h
0x1800503b6  pop     r15
0x1800503b8  pop     r14
0x1800503ba  pop     r13
0x1800503bc  pop     r12
0x1800503be  pop     rdi
0x1800503bf  pop     rsi
0x1800503c0  pop     rbx
0x1800503c1  pop     rbp
0x1800503c2  retn
0x1800503c3  mov     [rbp+rcSrc1.bottom], 0FFFFFFFFh
0x1800503ca  jmp     loc_18005029F
0x1800503cf  mov     ebx, 80070057h
0x1800503d4  jmp     loc_1800502A4
0x1800503d9  movaps  xmm0, xmmword ptr [rbp+rcSrc1.left]
0x1800503dd  mov     r14d, r13d
0x1800503e0  mov     r15d, r13d
0x1800503e3  jmp     short loc_180050385
```
