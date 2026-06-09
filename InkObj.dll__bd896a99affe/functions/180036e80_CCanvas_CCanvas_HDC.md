# CCanvas::CCanvas(HDC__ *)

- ea: `0x180036e80`
- end: `0x18003715d`
- name: `??0CCanvas@@QEAA@PEAUHDC__@@@Z`
- size: `733`
- prototype: `CCanvas *(CCanvas *__hidden this, HDC)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18003b548`
- `0x18007d988`
- `0x180089390`
- `0x18008c540`
- `0x18009804c`

## callees

- `0x180036e80`
- `0x180037164`
- `0x1800446dc`
- `0x180044ab0`
- `0x180098a1c`

## import_xrefs

- `GDI32!GetClipRgn` at `0x18003710b`
- `GDI32!GetClipRgn` at `0x18003710b`
- `GDI32!CreateRectRgn` at `0x1800370fb`
- `GDI32!CreateRectRgn` at `0x1800370fb`
- `GDI32!GetViewportExtEx` at `0x1800370eb`
- `GDI32!GetViewportExtEx` at `0x1800370eb`
- `GDI32!GetWindowExtEx` at `0x1800370de`
- `GDI32!GetWindowExtEx` at `0x1800370de`
- `GDI32!GetMapMode` at `0x1800370c2`
- `GDI32!GetMapMode` at `0x1800370c2`
- `GDI32!GetWindowOrgEx` at `0x1800370a3`
- `GDI32!GetWindowOrgEx` at `0x1800370a3`
- `GDI32!GetViewportOrgEx` at `0x180037093`
- `GDI32!GetViewportOrgEx` at `0x180037093`
- `GDI32!GetWorldTransform` at `0x180037056`
- `GDI32!GetWorldTransform` at `0x180037056`
- `GDI32!GetGraphicsMode` at `0x180037045`
- `GDI32!GetGraphicsMode` at `0x180037045`
- `GDI32!SetLayout` at `0x180036fea`
- `GDI32!SetLayout` at `0x180036fea`
- `GDI32!GetDeviceCaps` at `0x180036ffd`
- `GDI32!GetDeviceCaps` at `0x180036ffd`
- `GDI32!DeleteObject` at `0x18003711a`
- `GDI32!DeleteObject` at `0x18003711a`
- `gdiplus!GdipCreatePath` at `0x180036f3e`
- `gdiplus!GdipCreatePath` at `0x180036f3e`
- `gdiplus!GdipAlloc` at `0x180037016`
- `gdiplus!GdipAlloc` at `0x180037016`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CCanvas *__fastcall CCanvas::CCanvas(CCanvas *this, HDC a2)
{
  char *v4; // r14
  Gdiplus::Graphics *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  int MapMode; // eax
  HRGN RectRgn; // rax
  Gdiplus::Graphics *pExceptionObject; // [rsp+78h] [rbp+10h] BYREF

  *(_QWORD *)this = &CCanvas::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_WORD *)this + 20) = 0;
  *((_BYTE *)this + 60) = 0;
  v4 = (char *)this + 64;
  *(XFORM *)((char *)this + 64) = CXform::UNIT_XFORM;
  *((_DWORD *)this + 22) = 1;
  *((_QWORD *)this + 14) = 0;
  `eh vector constructor iterator'(
    (char *)this + 120,
    0x10u,
    5u,
    (void (*)(void *))Gdiplus::GraphicsPath::`default constructor closure',
    (void (*)(void *))Gdiplus::GraphicsPath::~GraphicsPath);
  *((_BYTE *)this + 200) = 0;
  *((_DWORD *)this + 51) = 0;
  *((_BYTE *)this + 208) = 0;
  *((_DWORD *)this + 53) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = GdipCreatePath(0, (char *)this + 216);
  *((_QWORD *)this + 29) = 0;
  *((_BYTE *)this + 240) = 0;
  *((_DWORD *)this + 61) = 0;
  *((_QWORD *)this + 31) = a2;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *(_QWORD *)((char *)this + 300) = 0;
  *((_DWORD *)this + 77) = 1;
  *((_QWORD *)this + 39) = 1;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 41) = 0;
  Gdiplus::GraphicsPath::SetFillMode((char *)this + 120);
  *(_QWORD *)((char *)this + 52) = 0;
  *(_QWORD *)((char *)this + 44) = 0;
  *((_DWORD *)this + 24) = 1;
  *((_DWORD *)this + 23) = 1;
  *((_DWORD *)this + 26) = 1;
  *((_DWORD *)this + 25) = 1;
  *((_DWORD *)this + 64) = 0;
  if ( !a2 )
    return this;
  *((_DWORD *)this + 64) = SetLayout(a2, 0);
  if ( GetDeviceCaps(a2, 2) == 5 )
  {
    *((_DWORD *)this + 61) = 1;
    goto LABEL_6;
  }
  v5 = (Gdiplus::Graphics *)GdipAlloc(16);
  pExceptionObject = v5;
  if ( !v5 )
  {
    *((_QWORD *)this + 1) = 0;
LABEL_26:
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v6 = Gdiplus::Graphics::Graphics(v5, a2);
  *((_QWORD *)this + 1) = v6;
  if ( !v6 )
    goto LABEL_26;
LABEL_6:
  if ( GetGraphicsMode(a2) == 2 && GetWorldTransform(a2, (LPXFORM)v4) )
  {
    v7 = *(_QWORD *)v4 - *(_QWORD *)&CXform::UNIT_XFORM.eM11;
    if ( *(_QWORD *)v4 == *(_QWORD *)&CXform::UNIT_XFORM.eM11 )
    {
      v7 = *((_QWORD *)v4 + 1) - *(_QWORD *)&CXform::UNIT_XFORM.eM21;
      if ( !v7 )
        v7 = *((_QWORD *)v4 + 2) - *(_QWORD *)&CXform::UNIT_XFORM.eDx;
    }
    if ( v7 )
      *((_BYTE *)this + 60) = 1;
  }
  if ( GetViewportOrgEx(a2, (LPPOINT)((char *)this + 44))
    && GetWindowOrgEx(a2, (LPPOINT)((char *)this + 52))
    && (*((_DWORD *)this + 11) != *((_DWORD *)this + 13) || *((_DWORD *)this + 12) != *((_DWORD *)this + 14)) )
  {
    *((_BYTE *)this + 41) = 1;
  }
  MapMode = GetMapMode(a2);
  if ( MapMode <= 0 )
    MapMode = *((_DWORD *)this + 22);
  *((_DWORD *)this + 22) = MapMode;
  if ( MapMode >= 7 )
  {
    GetWindowExtEx(a2, (LPSIZE)((char *)this + 92));
    GetViewportExtEx(a2, (LPSIZE)((char *)this + 100));
  }
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  *((_QWORD *)this + 14) = RectRgn;
  if ( GetClipRgn(a2, RectRgn) < 1 )
  {
    DeleteObject(*((HGDIOBJ *)this + 14));
    *((_QWORD *)this + 14) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180036e80  mov     [rsp+arg_10], rbx
0x180036e85  mov     [rsp+arg_0], rcx
0x180036e8a  push    rbp
0x180036e8b  push    rsi
0x180036e8c  push    rdi
0x180036e8d  push    r12
0x180036e8f  push    r13
0x180036e91  push    r14
0x180036e93  push    r15
0x180036e95  sub     rsp, 30h
0x180036e99  mov     rbp, rdx
0x180036e9c  mov     rsi, rcx
0x180036e9f  lea     rax, ??_7CCanvas@@6B@; const CCanvas::`vftable'
0x180036ea6  mov     [rcx], rax
0x180036ea9  xor     r13d, r13d
0x180036eac  mov     [rcx+8], r13
0x180036eb0  mov     [rcx+10h], r13
0x180036eb4  mov     [rcx+18h], r13
0x180036eb8  mov     [rcx+20h], r13d
0x180036ebc  mov     [rcx+28h], r13w
0x180036ec1  mov     [rcx+3Ch], r13b
0x180036ec5  lea     r14, [rcx+40h]
0x180036ec9  movups  xmm0, xmmword ptr cs:?UNIT_XFORM@CXform@@2UtagXFORM@@B.eM11; tagXFORM const CXform::UNIT_XFORM ...
0x180036ed0  movups  xmmword ptr [r14], xmm0
0x180036ed4  movsd   xmm1, qword ptr cs:?UNIT_XFORM@CXform@@2UtagXFORM@@B.eDx; tagXFORM const CXform::UNIT_XFORM ...
0x180036edc  movsd   qword ptr [r14+10h], xmm1
0x180036ee2  lea     r12d, [r13+1]
0x180036ee6  mov     [rcx+58h], r12d
0x180036eea  mov     [rcx+70h], r13
0x180036eee  lea     rax, ??1GraphicsPath@Gdiplus@@QEAA@XZ; Gdiplus::GraphicsPath::~GraphicsPath(void)
0x180036ef5  mov     [rsp+68h+var_48], rax; void (*)(void *)
0x180036efa  lea     r9, ??_FGraphicsPath@Gdiplus@@QEAAXXZ; void (*)(void *)
0x180036f01  lea     edx, [r13+10h]; unsigned __int64
0x180036f05  lea     r8d, [r13+5]; unsigned __int64
0x180036f09  add     rcx, 78h ; 'x'; void *
0x180036f0d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180036f12  nop
0x180036f13  mov     [rsi+0C8h], r13b
0x180036f1a  mov     [rsi+0CCh], r13d
0x180036f21  mov     [rsi+0D0h], r13b
0x180036f28  mov     [rsi+0D4h], r13d
0x180036f2f  lea     rbx, [rsi+0D8h]
0x180036f36  mov     [rbx], r13
0x180036f39  mov     rdx, rbx
0x180036f3c  xor     ecx, ecx
0x180036f3e  call    cs:__imp_GdipCreatePath
0x180036f44  mov     [rbx+8], eax
0x180036f47  mov     [rsi+0E8h], r13
0x180036f4e  mov     [rsi+0F0h], r13b
0x180036f55  mov     [rsi+0F4h], r13d
0x180036f5c  mov     [rsi+0F8h], rbp
0x180036f63  mov     [rsi+100h], r13d
0x180036f6a  mov     [rsi+108h], r13
0x180036f71  mov     [rsi+110h], r13
0x180036f78  mov     [rsi+118h], r13
0x180036f7f  mov     [rsi+120h], r13
0x180036f86  mov     [rsi+12Ch], r13
0x180036f8d  mov     [rsi+134h], r12d
0x180036f94  mov     qword ptr [rsi+138h], 1
0x180036f9f  mov     [rsi+140h], r13d
0x180036fa6  mov     [rsi+148h], r13
0x180036fad  lea     rcx, [rsi+78h]
0x180036fb1  call    ?SetFillMode@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@W4FillMode@2@@Z; Gdiplus::GraphicsPath::SetFillMode(Gdiplus::FillMode)
0x180036fb6  lea     rbx, [rsi+34h]
0x180036fba  mov     [rbx], r13
0x180036fbd  lea     rdi, [rsi+2Ch]
0x180036fc1  mov     [rdi], r13
0x180036fc4  mov     [rsi+60h], r12d
0x180036fc8  mov     [rsi+5Ch], r12d
0x180036fcc  mov     eax, r12d
0x180036fcf  mov     [rsi+68h], eax
0x180036fd2  mov     [rsi+64h], eax
0x180036fd5  mov     [rsi+100h], r13d
0x180036fdc  test    rbp, rbp
0x180036fdf  jz      loc_180037124
0x180036fe5  xor     edx, edx; l
0x180036fe7  mov     rcx, rbp; hdc
0x180036fea  call    cs:__imp_SetLayout
0x180036ff0  mov     [rsi+100h], eax
0x180036ff6  lea     edx, [r13+2]; index
0x180036ffa  mov     rcx, rbp; hdc
0x180036ffd  call    cs:__imp_GetDeviceCaps
0x180037003  cmp     eax, 5
0x180037006  jnz     short loc_180037011
0x180037008  mov     [rsi+0F4h], r12d
0x18003700f  jmp     short loc_180037042
0x180037011  mov     ecx, 10h
0x180037016  call    cs:__imp_GdipAlloc
0x18003701c  mov     [rsp+68h+pExceptionObject], rax
0x180037021  test    rax, rax
0x180037024  jz      loc_18003713F
0x18003702a  mov     rdx, rbp; HDC
0x18003702d  mov     rcx, rax; this
0x180037030  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x180037035  mov     [rsi+8], rax
0x180037039  test    rax, rax
0x18003703c  jz      loc_180037143
0x180037042  mov     rcx, rbp; hdc
0x180037045  call    cs:__imp_GetGraphicsMode
0x18003704b  cmp     eax, 2
0x18003704e  jnz     short loc_18003708D
0x180037050  mov     rdx, r14; lpxf
0x180037053  mov     rcx, rbp; hdc
0x180037056  call    cs:__imp_GetWorldTransform
0x18003705c  test    eax, eax
0x18003705e  jz      short loc_18003708D
0x180037060  mov     rax, [r14]
0x180037063  sub     rax, qword ptr cs:?UNIT_XFORM@CXform@@2UtagXFORM@@B.eM11; tagXFORM const CXform::UNIT_XFORM ...
0x18003706a  jnz     short loc_180037084
0x18003706c  mov     rax, [r14+8]
0x180037070  sub     rax, qword ptr cs:?UNIT_XFORM@CXform@@2UtagXFORM@@B.eM21; tagXFORM const CXform::UNIT_XFORM ...
0x180037077  jnz     short loc_180037084
0x180037079  mov     rax, [r14+10h]
0x18003707d  sub     rax, qword ptr cs:?UNIT_XFORM@CXform@@2UtagXFORM@@B.eDx; tagXFORM const CXform::UNIT_XFORM ...
0x180037084  test    rax, rax
0x180037087  jz      short loc_18003708D
0x180037089  mov     byte ptr [rsi+3Ch], 1
0x18003708d  mov     rdx, rdi; lppoint
0x180037090  mov     rcx, rbp; hdc
0x180037093  call    cs:__imp_GetViewportOrgEx
0x180037099  test    eax, eax
0x18003709b  jz      short loc_1800370BF
0x18003709d  mov     rdx, rbx; lppoint
0x1800370a0  mov     rcx, rbp; hdc
0x1800370a3  call    cs:__imp_GetWindowOrgEx
0x1800370a9  test    eax, eax
0x1800370ab  jz      short loc_1800370BF
0x1800370ad  mov     eax, [rbx]
0x1800370af  cmp     [rdi], eax
0x1800370b1  jnz     short loc_1800370BB
0x1800370b3  mov     eax, [rsi+38h]
0x1800370b6  cmp     [rsi+30h], eax
0x1800370b9  jz      short loc_1800370BF
0x1800370bb  mov     byte ptr [rsi+29h], 1
0x1800370bf  mov     rcx, rbp; hdc
0x1800370c2  call    cs:__imp_GetMapMode
0x1800370c8  test    eax, eax
0x1800370ca  jg      short loc_1800370CF
0x1800370cc  mov     eax, [rsi+58h]
0x1800370cf  mov     [rsi+58h], eax
0x1800370d2  cmp     eax, 7
0x1800370d5  jl      short loc_1800370F1
0x1800370d7  lea     rdx, [rsi+5Ch]; lpsize
0x1800370db  mov     rcx, rbp; hdc
0x1800370de  call    cs:__imp_GetWindowExtEx
0x1800370e4  lea     rdx, [rsi+64h]; lpsize
0x1800370e8  mov     rcx, rbp; hdc
0x1800370eb  call    cs:__imp_GetViewportExtEx
0x1800370f1  xor     r9d, r9d; y2
0x1800370f4  xor     r8d, r8d; x2
0x1800370f7  xor     edx, edx; y1
0x1800370f9  xor     ecx, ecx; x1
0x1800370fb  call    cs:__imp_CreateRectRgn
0x180037101  mov     [rsi+70h], rax
0x180037105  mov     rdx, rax; hrgn
0x180037108  mov     rcx, rbp; hdc
0x18003710b  call    cs:__imp_GetClipRgn
0x180037111  cmp     eax, 1
0x180037114  jge     short loc_180037124
0x180037116  mov     rcx, [rsi+70h]; ho
0x18003711a  call    cs:__imp_DeleteObject
0x180037120  mov     [rsi+70h], r13
0x180037124  mov     rax, rsi
0x180037127  mov     rbx, [rsp+68h+arg_10]
0x18003712f  add     rsp, 30h
0x180037133  pop     r15
0x180037135  pop     r14
0x180037137  pop     r13
0x180037139  pop     r12
0x18003713b  pop     rdi
0x18003713c  pop     rsi
0x18003713d  pop     rbp
0x18003713e  retn
0x18003713f  mov     [rsi+8], r13
0x180037143  mov     dword ptr [rsp+68h+pExceptionObject], 8007000Eh
0x18003714b  lea     rdx, _TI1J; pThrowInfo
0x180037152  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180037157  call    _CxxThrowException_0
```
