# GdipUtil::RoundRectPath::Init(int,int,int,int,uint,uint,uint,uint,uint,uint,uint,uint)

- ea: `0x180028280`
- end: `0x180028526`
- name: `?Init@RoundRectPath@GdipUtil@@AEAAXHHHHIIIIIIII@Z`
- size: `678`
- prototype: `void __fastcall(GdipUtil::RoundRectPath *__hidden this, int, int, int, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180036720`

## callees

- `0x180028280`
- `0x1800387c8`
- `0x1800781a4`

## import_xrefs

- `gdiplus!GdipAddPathLineI` at `0x1800283a3`
- `gdiplus!GdipAddPathLineI` at `0x180028414`
- `gdiplus!GdipAddPathLineI` at `0x180028494`
- `gdiplus!GdipAddPathLineI` at `0x1800284fd`
- `gdiplus!GdipAddPathLineI` at `0x1800283a3`
- `gdiplus!GdipAddPathLineI` at `0x180028414`
- `gdiplus!GdipAddPathLineI` at `0x180028494`
- `gdiplus!GdipAddPathLineI` at `0x1800284fd`

## pseudocode

```c
void __fastcall GdipUtil::RoundRectPath::Init(
        GdipUtil::RoundRectPath *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13)
{
  int v13; // esi
  unsigned int v14; // r14d
  int v15; // edi
  int v17; // r13d
  int v20; // ecx
  unsigned int v21; // eax
  int v22; // ecx
  unsigned int v23; // eax
  int v24; // r8d
  unsigned int v25; // ebp
  int v26; // edx
  int v27; // edx
  int v28; // eax
  _DWORD *v29; // rsi
  _DWORD *v30; // rdi
  int v31; // eax
  unsigned int v32; // ecx
  _DWORD *v33; // rsi
  int v34; // eax
  int v35; // eax
  unsigned int v36; // [rsp+D0h] [rbp+38h]
  unsigned int v37; // [rsp+E8h] [rbp+50h]
  unsigned int v38; // [rsp+F0h] [rbp+58h]
  unsigned int v39; // [rsp+F8h] [rbp+60h]
  unsigned int v40; // [rsp+100h] [rbp+68h]

  v13 = a6;
  v14 = a4 - 1;
  v15 = a8;
  v17 = a9;
  v20 = a10;
  v21 = (int)(a4 - a2) / 2;
  if ( a6 >= v21 )
    v13 = (int)(a4 - a2) / 2;
  if ( a8 >= v21 )
    v15 = (int)(a4 - a2) / 2;
  if ( a10 >= v21 )
    v20 = (int)(a4 - a2) / 2;
  v37 = v20;
  v22 = a12;
  if ( a12 >= v21 )
    v22 = (int)(a4 - a2) / 2;
  v39 = v22;
  v23 = (int)(a5 - a3) / 2;
  v24 = a7;
  v25 = a5 - 1;
  v26 = a11;
  if ( a7 >= v23 )
    v24 = (int)(a5 - a3) / 2;
  v36 = v24;
  if ( a9 >= v23 )
    v17 = (int)(a5 - a3) / 2;
  if ( a11 >= v23 )
    v26 = (int)(a5 - a3) / 2;
  v38 = v26;
  v27 = a13;
  if ( a13 >= v23 )
    v27 = (int)(a5 - a3) / 2;
  v40 = v27;
  if ( v13 && v24 )
    Gdiplus::GraphicsPath::AddArc(
      this,
      a2,
      a3,
      (unsigned int)(2 * v13),
      2 * v24,
      LODWORD(FLOAT_180_0),
      LODWORD(FLOAT_90_0));
  v28 = GdipAddPathLineI(*(_QWORD *)this, a2 + v13, a3, v14 - v15, a3);
  v29 = (_DWORD *)((char *)this + 8);
  if ( v28 )
    *v29 = v28;
  if ( v15 && v17 )
  {
    Gdiplus::GraphicsPath::AddArc(
      this,
      v14 - 2 * v15,
      a3,
      (unsigned int)(2 * v15),
      2 * v17,
      LODWORD(FLOAT_270_0),
      LODWORD(FLOAT_90_0));
    v30 = (_DWORD *)((char *)this + 8);
  }
  else
  {
    v30 = (_DWORD *)((char *)this + 8);
  }
  v31 = GdipAddPathLineI(*(_QWORD *)this, v14, a3 + v17, v14, v25 - v38);
  if ( v31 )
    *v29 = v31;
  else
    v30 = (_DWORD *)((char *)this + 8);
  v32 = v37;
  if ( v37 && v38 )
  {
    Gdiplus::GraphicsPath::AddArc(this, v14 - 2 * v37, v25 - 2 * v38, 2 * v37, 2 * v38, 0, LODWORD(FLOAT_90_0));
    v32 = v37;
    v33 = (_DWORD *)((char *)this + 8);
  }
  else
  {
    v33 = v30;
  }
  v34 = GdipAddPathLineI(*(_QWORD *)this, v14 - v32, v25, a2 + v39, v25);
  if ( v34 )
    *v30 = v34;
  else
    v33 = v30;
  if ( v39 && v40 )
    Gdiplus::GraphicsPath::AddArc(this, a2, v25 - 2 * v40, 2 * v39, 2 * v40, LODWORD(FLOAT_90_0), LODWORD(FLOAT_90_0));
  v35 = GdipAddPathLineI(*(_QWORD *)this, a2, v25 - v40, a2, a3 + v36);
  if ( v35 )
    *v33 = v35;
  Gdiplus::GraphicsPath::CloseFigure(this);
}

```

## disassembly

```asm
0x180028280  push    rbx
0x180028282  push    rbp
0x180028283  push    rsi
0x180028284  push    rdi
0x180028285  push    r12
0x180028287  push    r13
0x180028289  push    r14
0x18002828b  push    r15
0x18002828d  sub     rsp, 58h
0x180028291  mov     esi, [rsp+98h+arg_28]
0x180028298  lea     r14d, [r9-1]
0x18002829c  mov     edi, [rsp+98h+arg_38]
0x1800282a3  mov     r15d, edx
0x1800282a6  mov     r13d, [rsp+98h+arg_40]
0x1800282ae  mov     r12d, r8d
0x1800282b1  mov     r8d, 2
0x1800282b7  movaps  [rsp+98h+var_58], xmm6
0x1800282bc  movss   xmm6, cs:__real@42b40000
0x1800282c4  mov     rbx, rcx
0x1800282c7  mov     ecx, [rsp+98h+arg_48]
0x1800282ce  mov     eax, r9d
0x1800282d1  sub     eax, edx
0x1800282d3  cdq
0x1800282d4  idiv    r8d
0x1800282d7  cmp     esi, eax
0x1800282d9  cmovnb  esi, eax
0x1800282dc  cmp     edi, eax
0x1800282de  cmovnb  edi, eax
0x1800282e1  cmp     ecx, eax
0x1800282e3  cmovnb  ecx, eax
0x1800282e6  mov     [rsp+98h+arg_48], ecx
0x1800282ed  mov     ecx, [rsp+98h+arg_58]
0x1800282f4  cmp     ecx, eax
0x1800282f6  cmovnb  ecx, eax
0x1800282f9  mov     [rsp+98h+arg_58], ecx
0x180028300  mov     ecx, [rsp+98h+arg_20]
0x180028307  mov     eax, ecx
0x180028309  sub     eax, r12d
0x18002830c  cdq
0x18002830d  idiv    r8d
0x180028310  mov     r8d, [rsp+98h+arg_30]
0x180028318  lea     ebp, [rcx-1]
0x18002831b  mov     edx, [rsp+98h+arg_50]
0x180028322  cmp     r8d, eax
0x180028325  cmovnb  r8d, eax
0x180028329  cmp     r13d, eax
0x18002832c  mov     [rsp+98h+arg_30], r8d
0x180028334  cmovnb  r13d, eax
0x180028338  cmp     edx, eax
0x18002833a  cmovnb  edx, eax
0x18002833d  mov     [rsp+98h+arg_50], edx
0x180028344  mov     edx, [rsp+98h+arg_60]
0x18002834b  cmp     edx, eax
0x18002834d  cmovnb  edx, eax
0x180028350  mov     [rsp+98h+arg_60], edx
0x180028357  test    esi, esi
0x180028359  jz      short loc_18002838E
0x18002835b  test    r8d, r8d
0x18002835e  jz      short loc_18002838E
0x180028360  movss   xmm0, cs:__real@43340000
0x180028368  lea     eax, [r8+r8]
0x18002836c  movss   [rsp+98h+var_68], xmm6
0x180028372  lea     r9d, [rsi+rsi]
0x180028376  movss   [rsp+98h+var_70], xmm0
0x18002837c  mov     r8d, r12d
0x18002837f  mov     edx, r15d
0x180028382  mov     [rsp+98h+var_78], eax
0x180028386  mov     rcx, rbx
0x180028389  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHHMM@Z; Gdiplus::GraphicsPath::AddArc(int,int,int,int,float,float)
0x18002838e  mov     rcx, [rbx]
0x180028391  lea     edx, [r15+rsi]
0x180028395  mov     r9d, r14d
0x180028398  mov     [rsp+98h+var_78], r12d
0x18002839d  sub     r9d, edi
0x1800283a0  mov     r8d, r12d
0x1800283a3  call    cs:__imp_GdipAddPathLineI
0x1800283a9  lea     rsi, [rbx+8]
0x1800283ad  test    eax, eax
0x1800283af  jz      short loc_1800283B3
0x1800283b1  mov     [rsi], eax
0x1800283b3  test    edi, edi
0x1800283b5  jz      short loc_1800283F7
0x1800283b7  test    r13d, r13d
0x1800283ba  jz      short loc_1800283F7
0x1800283bc  movss   xmm0, cs:__real@43870000
0x1800283c4  lea     r9d, [rdi+rdi]
0x1800283c8  movss   [rsp+98h+var_68], xmm6
0x1800283ce  lea     eax, ds:0[r13*2]
0x1800283d6  mov     edx, r14d
0x1800283d9  movss   [rsp+98h+var_70], xmm0
0x1800283df  sub     edx, r9d
0x1800283e2  mov     [rsp+98h+var_78], eax
0x1800283e6  mov     r8d, r12d
0x1800283e9  mov     rcx, rbx
0x1800283ec  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHHMM@Z; Gdiplus::GraphicsPath::AddArc(int,int,int,int,float,float)
0x1800283f1  lea     rdi, [rbx+8]
0x1800283f5  jmp     short loc_1800283FA
0x1800283f7  mov     rdi, rsi
0x1800283fa  mov     rcx, [rbx]
0x1800283fd  lea     r8d, [r12+r13]
0x180028401  mov     eax, ebp
0x180028403  mov     r9d, r14d
0x180028406  sub     eax, [rsp+98h+arg_50]
0x18002840d  mov     edx, r14d
0x180028410  mov     [rsp+98h+var_78], eax
0x180028414  call    cs:__imp_GdipAddPathLineI
0x18002841a  test    eax, eax
0x18002841c  jz      short loc_180028422
0x18002841e  mov     [rsi], eax
0x180028420  jmp     short loc_180028425
0x180028422  mov     rdi, rsi
0x180028425  mov     ecx, [rsp+98h+arg_48]
0x18002842c  test    ecx, ecx
0x18002842e  jz      short loc_180028475
0x180028430  mov     eax, [rsp+98h+arg_50]
0x180028437  test    eax, eax
0x180028439  jz      short loc_180028475
0x18002843b  lea     r9d, [rcx+rcx]
0x18002843f  movss   [rsp+98h+var_68], xmm6
0x180028445  add     eax, eax
0x180028447  mov     r8d, ebp
0x18002844a  mov     edx, r14d
0x18002844d  xorps   xmm0, xmm0
0x180028450  movss   [rsp+98h+var_70], xmm0
0x180028456  sub     r8d, eax
0x180028459  sub     edx, r9d
0x18002845c  mov     [rsp+98h+var_78], eax
0x180028460  mov     rcx, rbx
0x180028463  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHHMM@Z; Gdiplus::GraphicsPath::AddArc(int,int,int,int,float,float)
0x180028468  mov     ecx, [rsp+98h+arg_48]
0x18002846f  lea     rsi, [rbx+8]
0x180028473  jmp     short loc_180028478
0x180028475  mov     rsi, rdi
0x180028478  mov     r13d, [rsp+98h+arg_58]
0x180028480  sub     r14d, ecx
0x180028483  mov     rcx, [rbx]
0x180028486  mov     r8d, ebp
0x180028489  mov     edx, r14d
0x18002848c  mov     [rsp+98h+var_78], ebp
0x180028490  lea     r9d, [r15+r13]
0x180028494  call    cs:__imp_GdipAddPathLineI
0x18002849a  test    eax, eax
0x18002849c  jz      short loc_1800284A2
0x18002849e  mov     [rdi], eax
0x1800284a0  jmp     short loc_1800284A5
0x1800284a2  mov     rsi, rdi
0x1800284a5  mov     edi, [rsp+98h+arg_60]
0x1800284ac  test    r13d, r13d
0x1800284af  jz      short loc_1800284E1
0x1800284b1  test    edi, edi
0x1800284b3  jz      short loc_1800284E1
0x1800284b5  lea     eax, [rdi+rdi]
0x1800284b8  movss   [rsp+98h+var_68], xmm6
0x1800284be  mov     r8d, ebp
0x1800284c1  movss   [rsp+98h+var_70], xmm6
0x1800284c7  sub     r8d, eax
0x1800284ca  mov     [rsp+98h+var_78], eax
0x1800284ce  lea     r9d, ds:0[r13*2]
0x1800284d6  mov     edx, r15d
0x1800284d9  mov     rcx, rbx
0x1800284dc  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHHMM@Z; Gdiplus::GraphicsPath::AddArc(int,int,int,int,float,float)
0x1800284e1  mov     eax, [rsp+98h+arg_30]
0x1800284e8  sub     ebp, edi
0x1800284ea  mov     rcx, [rbx]
0x1800284ed  add     eax, r12d
0x1800284f0  mov     r9d, r15d
0x1800284f3  mov     [rsp+98h+var_78], eax
0x1800284f7  mov     r8d, ebp
0x1800284fa  mov     edx, r15d
0x1800284fd  call    cs:__imp_GdipAddPathLineI
0x180028503  test    eax, eax
0x180028505  jz      short loc_180028509
0x180028507  mov     [rsi], eax
0x180028509  mov     rcx, rbx
0x18002850c  movaps  xmm6, [rsp+98h+var_58]
0x180028511  add     rsp, 58h
0x180028515  pop     r15
0x180028517  pop     r14
0x180028519  pop     r13
0x18002851b  pop     r12
0x18002851d  pop     rdi
0x18002851e  pop     rsi
0x18002851f  pop     rbp
0x180028520  pop     rbx
0x180028521  jmp     ?CloseFigure@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::CloseFigure(void)
```
