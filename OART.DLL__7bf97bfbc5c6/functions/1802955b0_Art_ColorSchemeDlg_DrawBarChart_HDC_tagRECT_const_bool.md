# Art::ColorSchemeDlg::DrawBarChart(HDC__ *,tagRECT const &,bool)

- ea: `0x1802955b0`
- end: `0x18029579f`
- name: `?DrawBarChart@ColorSchemeDlg@Art@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z`
- size: `495`
- prototype: `void(Art::ColorSchemeDlg *__hidden this, HDC, const struct tagRECT *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180294d44`

## callees

- `0x180070fe0`
- `0x1802955b0`
- `0x1802957a0`
- `0x180337554`

## import_xrefs

- `GDI32!CreatePen` at `0x1802955fc`
- `GDI32!CreatePen` at `0x1802955fc`
- `GDI32!LineTo` at `0x18029564b`
- `GDI32!LineTo` at `0x18029564b`
- `GDI32!MoveToEx` at `0x18029563a`
- `GDI32!MoveToEx` at `0x18029563a`
- `GDI32!Rectangle` at `0x18029570d`
- `GDI32!Rectangle` at `0x18029570d`
- `GDI32!SelectObject` at `0x180295620`
- `GDI32!SelectObject` at `0x180295730`
- `GDI32!SelectObject` at `0x180295764`
- `GDI32!SelectObject` at `0x180295620`
- `GDI32!SelectObject` at `0x180295730`
- `GDI32!SelectObject` at `0x180295764`
- `GDI32!DeleteObject` at `0x18029573f`
- `GDI32!DeleteObject` at `0x180295772`
- `GDI32!DeleteObject` at `0x18029573f`
- `GDI32!DeleteObject` at `0x180295772`
- `USER32!OffsetRect` at `0x1802956a2`
- `USER32!OffsetRect` at `0x18029571d`
- `USER32!OffsetRect` at `0x1802956a2`
- `USER32!OffsetRect` at `0x18029571d`

## pseudocode

```c
void __fastcall Art::ColorSchemeDlg::DrawBarChart(Art::ColorSchemeDlg *this, HDC a2, const struct tagRECT *a3, char a4)
{
  HPEN Pen; // rax
  HGDIOBJ v8; // rdi
  int v9; // r12d
  unsigned int v10; // r15d
  double *v11; // r14
  unsigned int ColorRGB; // eax
  HPEN v13; // [rsp+30h] [rbp-50h]
  HGDIOBJ ho[2]; // [rsp+48h] [rbp-38h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-28h]
  struct tagRECT rc; // [rsp+60h] [rbp-20h] BYREF

  Pen = CreatePen(0, 1, a4 != 0 ? 38816067 : 50331647);
  v13 = Pen;
  v8 = 0;
  if ( Pen && a2 )
    v8 = SelectObject(a2, Pen);
  MoveToEx(a2, a3->left, a3->bottom, 0);
  LineTo(a2, a3->right, a3->bottom);
  v9 = (a3->right - a3->left) / 7;
  rc.left = a3->left;
  rc.top = a3->top;
  rc.right = v9 + rc.left;
  rc.bottom = a3->bottom + 1;
  OffsetRect(&rc, v9 / 2, 0);
  v10 = 4;
  v11 = (double *)qword_180B83880;
  do
  {
    ColorRGB = Art::ColorSchemeDlg::GetColorRGB(this, v10);
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)ho, a2, ColorRGB);
    Rectangle(a2, rc.left, (int)((double)rc.bottom - (double)(rc.bottom - rc.top) * *v11), rc.right + 1, rc.bottom);
    OffsetRect(&rc, v9, 0);
    if ( h )
      SelectObject((HDC)ho[1], h);
    if ( ho[0] )
      DeleteObject(ho[0]);
    ++v10;
    ++v11;
  }
  while ( (__int64)v11 < (__int64)L"FillRect" );
  if ( v8 )
    SelectObject(a2, v8);
  if ( v13 )
    DeleteObject(v13);
}

```

## disassembly

```asm
0x1802955b0  mov     [rsp-38h+arg_18], rbx
0x1802955b5  push    rbp
0x1802955b6  push    rsi
0x1802955b7  push    rdi
0x1802955b8  push    r12
0x1802955ba  push    r13
0x1802955bc  push    r14
0x1802955be  push    r15
0x1802955c0  mov     rbp, rsp
0x1802955c3  sub     rsp, 80h
0x1802955ca  mov     rax, cs:__security_cookie
0x1802955d1  xor     rax, rsp
0x1802955d4  mov     [rbp+var_10], rax
0x1802955d8  mov     r14, r8
0x1802955db  mov     rbx, rdx
0x1802955de  mov     r13, rcx
0x1802955e1  neg     r9b
0x1802955e4  sbb     r8d, r8d
0x1802955e7  and     r8d, 0FF504944h
0x1802955ee  add     r8d, 2FFFFFFh; color
0x1802955f5  mov     edx, 1; cWidth
0x1802955fa  xor     ecx, ecx; iStyle
0x1802955fc  call    cs:__imp_CreatePen
0x180295602  mov     [rbp+var_50], rax
0x180295606  mov     [rbp+var_48], rbx
0x18029560a  xor     edi, edi
0x18029560c  mov     [rbp+var_40], rdi
0x180295610  test    rax, rax
0x180295613  jz      short loc_18029562D
0x180295615  test    rbx, rbx
0x180295618  jz      short loc_18029562D
0x18029561a  mov     rdx, rax; h
0x18029561d  mov     rcx, rbx; hdc
0x180295620  call    cs:__imp_SelectObject
0x180295626  mov     rdi, rax
0x180295629  mov     [rbp+var_40], rax
0x18029562d  xor     r9d, r9d; lppt
0x180295630  mov     r8d, [r14+0Ch]; y
0x180295634  mov     edx, [r14]; x
0x180295637  mov     rcx, rbx; hdc
0x18029563a  call    cs:__imp_MoveToEx
0x180295640  mov     r8d, [r14+0Ch]; y
0x180295644  mov     edx, [r14+8]; x
0x180295648  mov     rcx, rbx; hdc
0x18029564b  call    cs:__imp_LineTo
0x180295651  mov     r8d, [r14]
0x180295654  mov     ecx, [r14+8]
0x180295658  sub     ecx, r8d
0x18029565b  mov     eax, 92492493h
0x180295660  imul    ecx
0x180295662  lea     r12d, [rcx+rdx]
0x180295666  sar     r12d, 2
0x18029566a  mov     eax, r12d
0x18029566d  shr     eax, 1Fh
0x180295670  add     r12d, eax
0x180295673  mov     [rbp+rc.left], r8d
0x180295677  mov     eax, [r14+4]
0x18029567b  mov     [rbp+rc.top], eax
0x18029567e  lea     eax, [r12+r8]
0x180295682  mov     [rbp+rc.right], eax
0x180295685  mov     eax, [r14+0Ch]
0x180295689  inc     eax
0x18029568b  mov     [rbp+rc.bottom], eax
0x18029568e  mov     eax, r12d
0x180295691  cdq
0x180295692  mov     ecx, 2
0x180295697  idiv    ecx
0x180295699  mov     edx, eax; dx
0x18029569b  xor     r8d, r8d; dy
0x18029569e  lea     rcx, [rbp+rc]; lprc
0x1802956a2  call    cs:__imp_OffsetRect
0x1802956a8  mov     r15d, 4
0x1802956ae  lea     r14, qword_180B83880
0x1802956b5  lea     rsi, aFillrect_0; "FillRect"
0x1802956bc  mov     edx, r15d
0x1802956bf  mov     rcx, r13
0x1802956c2  call    ?GetColorRGB@ColorSchemeDlg@Art@@AEAAKW4ColorSchemeIndex@2@@Z; Art::ColorSchemeDlg::GetColorRGB(Art::ColorSchemeIndex)
0x1802956c7  mov     r8d, eax; unsigned int
0x1802956ca  mov     rdx, rbx; HDC
0x1802956cd  lea     rcx, [rbp+ho]; this
0x1802956d1  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1802956d6  mov     r9d, [rbp+rc.right]
0x1802956da  inc     r9d; right
0x1802956dd  mov     ecx, [rbp+rc.bottom]
0x1802956e0  movd    xmm1, ecx
0x1802956e4  cvtdq2pd xmm1, xmm1
0x1802956e8  mov     eax, ecx
0x1802956ea  sub     eax, [rbp+rc.top]
0x1802956ed  movd    xmm0, eax
0x1802956f1  cvtdq2pd xmm0, xmm0
0x1802956f5  mulsd   xmm0, qword ptr [r14]
0x1802956fa  subsd   xmm1, xmm0
0x1802956fe  cvttsd2si r8d, xmm1; top
0x180295703  mov     [rsp+80h+bottom], ecx; bottom
0x180295707  mov     edx, [rbp+rc.left]; left
0x18029570a  mov     rcx, rbx; hdc
0x18029570d  call    cs:__imp_Rectangle
0x180295713  xor     r8d, r8d; dy
0x180295716  mov     edx, r12d; dx
0x180295719  lea     rcx, [rbp+rc]; lprc
0x18029571d  call    cs:__imp_OffsetRect
0x180295723  mov     rdx, [rbp+h]; h
0x180295727  test    rdx, rdx
0x18029572a  jz      short loc_180295736
0x18029572c  mov     rcx, [rbp+hdc]; hdc
0x180295730  call    cs:__imp_SelectObject
0x180295736  mov     rcx, [rbp+ho]; ho
0x18029573a  test    rcx, rcx
0x18029573d  jz      short loc_180295745
0x18029573f  call    cs:__imp_DeleteObject
0x180295745  inc     r15d
0x180295748  add     r14, 8
0x18029574c  cmp     r14, rsi
0x18029574f  jl      loc_1802956BC
0x180295755  test    rdi, rdi
0x180295758  mov     rsi, [rbp+var_50]
0x18029575c  jz      short loc_18029576A
0x18029575e  mov     rdx, rdi; h
0x180295761  mov     rcx, rbx; hdc
0x180295764  call    cs:__imp_SelectObject
0x18029576a  test    rsi, rsi
0x18029576d  jz      short loc_180295778
0x18029576f  mov     rcx, rsi; ho
0x180295772  call    cs:__imp_DeleteObject
0x180295778  mov     rcx, [rbp+var_10]
0x18029577c  xor     rcx, rsp; StackCookie
0x18029577f  call    __security_check_cookie
0x180295784  mov     rbx, [rsp+80h+arg_18]
0x18029578c  add     rsp, 80h
0x180295793  pop     r15
0x180295795  pop     r14
0x180295797  pop     r13
0x180295799  pop     r12
0x18029579b  pop     rdi
0x18029579c  pop     rsi
0x18029579d  pop     rbp
0x18029579e  retn
```
