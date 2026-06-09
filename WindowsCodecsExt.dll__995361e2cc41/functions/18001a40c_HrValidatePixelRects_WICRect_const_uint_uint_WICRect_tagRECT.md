# HrValidatePixelRects(WICRect const *,uint,uint,WICRect *,tagRECT *)

- ea: `0x18001a40c`
- end: `0x18001a594`
- name: `?HrValidatePixelRects@@YAJPEBUWICRect@@IIPEAU1@PEAUtagRECT@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(const struct WICRect *, unsigned int, unsigned int, struct WICRect *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e54`
- `0x18001a730`

## callees

- `0x1800171c4`
- `0x18001a40c`
- `0x180021a30`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18001a4f9`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18001a4f9`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18001a4dd`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18001a4dd`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18001a4e7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18001a4e7`

## pseudocode

```c
__int64 __fastcall HrValidatePixelRects(
        const struct WICRect *a1,
        unsigned int a2,
        unsigned int a3,
        struct WICRect *a4,
        struct tagRECT *a5)
{
  int Width; // r14d
  int Height; // esi
  INT X; // ebx
  INT Y; // edi
  RECT v10; // xmm0
  unsigned int v11; // ebx
  RECT rcSrc2; // [rsp+20h] [rbp-48h] BYREF
  RECT rcSrc1; // [rsp+30h] [rbp-38h] BYREF
  tagRECT rcDst; // [rsp+40h] [rbp-28h] BYREF

  Width = a2;
  rcSrc1.bottom = 0;
  *(_QWORD *)&rcSrc1.left = 0;
  Height = a3;
  rcDst = 0;
  if ( a2 > 0x7FFFFFFF )
  {
    rcSrc1.right = -1;
    goto LABEL_25;
  }
  rcSrc1.right = a2;
  if ( a3 > 0x7FFFFFFF )
  {
    rcSrc1.bottom = -1;
    goto LABEL_25;
  }
  rcSrc1.bottom = a3;
  if ( !a1 )
  {
    v10 = rcSrc1;
    X = 0;
    Y = 0;
    goto LABEL_19;
  }
  X = a1->X;
  Y = a1->Y;
  rcSrc2.bottom = 0;
  rcSrc2.left = X;
  rcSrc2.top = Y;
  if ( X < 0 )
    goto LABEL_25;
  Width = a1->Width;
  if ( Width < 0 || X + Width < (unsigned int)X )
    goto LABEL_25;
  if ( (unsigned int)(X + Width) > 0x7FFFFFFF )
  {
    rcSrc2.right = -1;
    goto LABEL_25;
  }
  rcSrc2.right = X + Width;
  if ( Y < 0 )
    goto LABEL_25;
  Height = a1->Height;
  if ( Height < 0 || Height + Y < (unsigned int)Y )
    goto LABEL_25;
  if ( (unsigned int)(Height + Y) > 0x7FFFFFFF )
  {
    rcSrc2.bottom = -1;
LABEL_25:
    v11 = -2147024362;
    goto LABEL_26;
  }
  rcSrc2.bottom = Height + Y;
  IntersectRect(&rcDst, &rcSrc1, &rcSrc2);
  if ( !IsRectEmpty(&rcSrc2) && EqualRect(&rcDst, &rcSrc2) )
  {
    v10 = rcDst;
LABEL_19:
    if ( a4 )
    {
      a4->X = X;
      a4->Y = Y;
      a4->Width = Width;
      a4->Height = Height;
    }
    v11 = 0;
    if ( a5 )
      *a5 = v10;
    return v11;
  }
  v11 = -2147024809;
LABEL_26:
  if ( g_doStackCaptures )
    DoStackCapture(v11);
  return v11;
}

```

## disassembly

```asm
0x18001a40c  push    rbp
0x18001a40e  push    rbx
0x18001a40f  push    rsi
0x18001a410  push    rdi
0x18001a411  push    r12
0x18001a413  push    r13
0x18001a415  push    r14
0x18001a417  push    r15
0x18001a419  mov     rbp, rsp
0x18001a41c  sub     rsp, 68h
0x18001a420  mov     rax, cs:__security_cookie
0x18001a427  xor     rax, rsp
0x18001a42a  mov     [rbp+var_18], rax
0x18001a42e  mov     r12, [rbp+arg_20]
0x18001a432  xor     r13d, r13d
0x18001a435  mov     r14d, edx
0x18001a438  mov     [rbp+rcSrc1.bottom], r13d
0x18001a43c  mov     edx, 7FFFFFFFh
0x18001a441  mov     qword ptr [rbp+rcSrc1.left], r13
0x18001a445  xorps   xmm0, xmm0
0x18001a448  mov     r15, r9
0x18001a44b  mov     esi, r8d
0x18001a44e  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x18001a452  cmp     r14d, edx
0x18001a455  ja      loc_18001A559
0x18001a45b  mov     [rbp+rcSrc1.right], r14d
0x18001a45f  cmp     r8d, edx
0x18001a462  ja      loc_18001A550
0x18001a468  mov     [rbp+rcSrc1.bottom], r8d
0x18001a46c  test    rcx, rcx
0x18001a46f  jz      loc_18001A522
0x18001a475  mov     ebx, [rcx]
0x18001a477  mov     edi, [rcx+4]
0x18001a47a  mov     [rbp+rcSrc2.bottom], r13d
0x18001a47e  mov     [rbp+rcSrc2.left], ebx
0x18001a481  mov     [rbp+rcSrc2.top], edi
0x18001a484  test    ebx, ebx
0x18001a486  js      loc_18001A560
0x18001a48c  mov     r14d, [rcx+8]
0x18001a490  test    r14d, r14d
0x18001a493  js      loc_18001A560
0x18001a499  lea     eax, [rbx+r14]
0x18001a49d  cmp     eax, ebx
0x18001a49f  jb      loc_18001A560
0x18001a4a5  cmp     eax, edx
0x18001a4a7  ja      short loc_18001A519
0x18001a4a9  mov     [rbp+rcSrc2.right], eax
0x18001a4ac  test    edi, edi
0x18001a4ae  js      loc_18001A560
0x18001a4b4  mov     esi, [rcx+0Ch]
0x18001a4b7  test    esi, esi
0x18001a4b9  js      loc_18001A560
0x18001a4bf  lea     eax, [rsi+rdi]
0x18001a4c2  cmp     eax, edi
0x18001a4c4  jb      loc_18001A560
0x18001a4ca  cmp     eax, edx
0x18001a4cc  ja      short loc_18001A510
0x18001a4ce  lea     r8, [rbp+rcSrc2]; lprcSrc2
0x18001a4d2  mov     [rbp+rcSrc2.bottom], eax
0x18001a4d5  lea     rdx, [rbp+rcSrc1]; lprcSrc1
0x18001a4d9  lea     rcx, [rbp+rcDst]; lprcDst
0x18001a4dd  call    cs:__imp_IntersectRect
0x18001a4e3  lea     rcx, [rbp+rcSrc2]; lprc
0x18001a4e7  call    cs:__imp_IsRectEmpty
0x18001a4ed  test    eax, eax
0x18001a4ef  jnz     short loc_18001A509
0x18001a4f1  lea     rdx, [rbp+rcSrc2]; lprc2
0x18001a4f5  lea     rcx, [rbp+rcDst]; lprc1
0x18001a4f9  call    cs:__imp_EqualRect
0x18001a4ff  test    eax, eax
0x18001a501  jz      short loc_18001A509
0x18001a503  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x18001a507  jmp     short loc_18001A52C
0x18001a509  mov     ebx, 80070057h
0x18001a50e  jmp     short loc_18001A565
0x18001a510  mov     [rbp+rcSrc2.bottom], 0FFFFFFFFh
0x18001a517  jmp     short loc_18001A560
0x18001a519  mov     [rbp+rcSrc2.right], 0FFFFFFFFh
0x18001a520  jmp     short loc_18001A560
0x18001a522  movaps  xmm0, xmmword ptr [rbp+rcSrc1.left]
0x18001a526  mov     ebx, r13d
0x18001a529  mov     edi, r13d
0x18001a52c  test    r15, r15
0x18001a52f  jz      short loc_18001A540
0x18001a531  mov     [r15], ebx
0x18001a534  mov     [r15+4], edi
0x18001a538  mov     [r15+8], r14d
0x18001a53c  mov     [r15+0Ch], esi
0x18001a540  mov     ebx, r13d
0x18001a543  test    r12, r12
0x18001a546  jz      short loc_18001A575
0x18001a548  movdqu  xmmword ptr [r12], xmm0
0x18001a54e  jmp     short loc_18001A575
0x18001a550  mov     [rbp+rcSrc1.bottom], 0FFFFFFFFh
0x18001a557  jmp     short loc_18001A560
0x18001a559  mov     [rbp+rcSrc1.right], 0FFFFFFFFh
0x18001a560  mov     ebx, 80070216h
0x18001a565  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18001a56c  jz      short loc_18001A575
0x18001a56e  mov     ecx, ebx; int
0x18001a570  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a575  mov     eax, ebx
0x18001a577  mov     rcx, [rbp+var_18]
0x18001a57b  xor     rcx, rsp; StackCookie
0x18001a57e  call    __security_check_cookie
0x18001a583  add     rsp, 68h
0x18001a587  pop     r15
0x18001a589  pop     r14
0x18001a58b  pop     r13
0x18001a58d  pop     r12
0x18001a58f  pop     rdi
0x18001a590  pop     rsi
0x18001a591  pop     rbx
0x18001a592  pop     rbp
0x18001a593  retn
```
