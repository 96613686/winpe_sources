# GdipUtil::BufferedPainter::BufferedPainter(HDC__ *,tagRECT const &)

- ea: `0x180009ee0`
- end: `0x18000a14f`
- name: `??0BufferedPainter@GdipUtil@@QEAA@PEAUHDC__@@AEBUtagRECT@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(GdipUtil::BufferedPainter *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800093fc`
- `0x180009920`
- `0x18002a138`
- `0x18002ab5c`

## callees

- `0x180009ee0`
- `0x18000a160`
- `0x18003f800`
- `0x180077da0`

## import_xrefs

- `gdiplus!GdipCreateFromHDC` at `0x18000a0b6`
- `gdiplus!GdipCreateFromHDC` at `0x18000a0b6`
- `gdiplus!GdipDeleteGraphics` at `0x18000a0dd`
- `gdiplus!GdipDeleteGraphics` at `0x18000a0dd`
- `gdiplus!GdipAlloc` at `0x18000a09b`
- `gdiplus!GdipAlloc` at `0x18000a09b`
- `gdiplus!GdipFree` at `0x18000a0e6`
- `gdiplus!GdipFree` at `0x18000a0e6`
- `GDI32!SelectObject` at `0x18000a07d`
- `GDI32!SelectObject` at `0x18000a07d`
- `GDI32!CreateCompatibleDC` at `0x18000a03d`
- `GDI32!CreateCompatibleDC` at `0x18000a03d`
- `GDI32!SetLayout` at `0x18000a06f`
- `GDI32!SetLayout` at `0x18000a06f`
- `GDI32!DeleteObject` at `0x18000a01a`
- `GDI32!DeleteObject` at `0x18000a01a`
- `GDI32!GetLayout` at `0x18000a05d`
- `GDI32!GetLayout` at `0x18000a05d`
- `GDI32!CreateDIBSection` at `0x18000a000`
- `GDI32!CreateDIBSection` at `0x18000a000`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a033`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a054`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a0ff`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a033`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a054`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000a0ff`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18000a08c`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18000a08c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
GdipUtil::BufferedPainter *__fastcall GdipUtil::BufferedPainter::BufferedPainter(
        GdipUtil::BufferedPainter *this,
        HDC a2,
        const struct tagRECT *a3)
{
  GdipUtil::BufferedPainter *v3; // rdi
  int v4; // ecx
  unsigned int v5; // ebx
  unsigned int v6; // esi
  HDC v7; // r14
  void *hSection; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  int v11; // edx
  HBITMAP v12; // rbx
  HBITMAP v13; // rax
  int v14; // edx
  HDC CompatibleDC; // rbx
  DWORD Layout; // eax
  HGDIOBJ v17; // rax
  Base *v18; // rcx
  __int64 v19; // rsi
  int v20; // edx
  __int64 v21; // rbx
  _QWORD *v22; // rsi
  int v23; // eax
  int v25; // eax
  int v26; // ecx
  void *ppvBits[2]; // [rsp+30h] [rbp-88h] BYREF
  GdipUtil::BufferedPainter *v28; // [rsp+40h] [rbp-78h]
  _BYTE v29[16]; // [rsp+50h] [rbp-68h] BYREF
  BITMAPINFO pbmi; // [rsp+60h] [rbp-58h] BYREF

  v3 = this;
  v28 = this;
  *(_QWORD *)this = &GdipUtil::BufferedPainterBase::`vftable';
  *((_QWORD *)this + 1) = a2;
  *((struct tagRECT *)this + 1) = *a3;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_BYTE *)this + 48) = 0;
  if ( *((_DWORD *)this + 6) <= *((_DWORD *)this + 4) || (v4 = 0, *((_DWORD *)v3 + 7) <= *((_DWORD *)v3 + 5)) )
  {
    v4 = 2;
    *((_DWORD *)v3 + 8) = 2;
  }
  *(_QWORD *)v3 = &GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::`vftable';
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  if ( !v4 )
  {
    v5 = *((_DWORD *)v3 + 7) - *((_DWORD *)v3 + 5);
    v6 = *((_DWORD *)v3 + 6) - *((_DWORD *)v3 + 4);
    v7 = (HDC)*((_QWORD *)v3 + 1);
    hSection = 0;
    if ( GdipUtilPrivate::g_theBitmapCache > 0 )
    {
      v9 = v5 * (unsigned __int64)v6;
      if ( v9 <= 0xFFFFFFFF )
      {
        v10 = 4LL * (unsigned int)v9;
        if ( v10 <= 0xFFFFFFFF )
          hSection = GdipUtilPrivate::BitmapCache::GetFileMapping(0, v10);
      }
    }
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = v6;
    pbmi.bmiHeader.biHeight = -v5;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    ppvBits[0] = 0;
    v12 = CreateDIBSection(v7, &pbmi, 0, ppvBits, hSection, 0);
    v13 = (HBITMAP)*((_QWORD *)v3 + 7);
    if ( v12 == v13 )
    {
      v12 = (HBITMAP)*((_QWORD *)v3 + 7);
    }
    else
    {
      if ( v13 )
        DeleteObject(*((HGDIOBJ *)v3 + 7));
      *((_QWORD *)v3 + 7) = v12;
    }
    try
    {
      if ( !v12 )
        Base::Throw((Base *)0x8007000ELL, v11);
      CompatibleDC = CreateCompatibleDC(*((HDC *)v3 + 1));
      *((_QWORD *)v3 + 8) = CompatibleDC;
      if ( !CompatibleDC )
        Base::Throw((Base *)0x8007000ELL, v14);
      Layout = GetLayout(CompatibleDC);
      if ( (Layout & 1) != 0 )
        SetLayout(CompatibleDC, Layout & 0xFFFFFFFE);
      v17 = SelectObject(*((HDC *)v3 + 8), *((HGDIOBJ *)v3 + 7));
      *((_QWORD *)v3 + 9) = v17;
      if ( !v17 )
        Base::ThrowLastError(v18);
      v19 = *((_QWORD *)v3 + 8);
      v21 = GdipAlloc(16);
      if ( v21 )
      {
        ppvBits[0] = 0;
        *(_DWORD *)(v21 + 8) = GdipCreateFromHDC(v19, ppvBits);
        *(void **)v21 = ppvBits[0];
      }
      else
      {
        v21 = 0;
      }
      v22 = (_QWORD *)*((_QWORD *)v3 + 5);
      if ( v22 == (_QWORD *)v21 )
      {
        v21 = *((_QWORD *)v3 + 5);
      }
      else
      {
        if ( v22 )
        {
          GdipDeleteGraphics(*v22);
          GdipFree(v22);
        }
        *((_QWORD *)v3 + 5) = v21;
      }
      if ( !v21 )
        Base::Throw((Base *)0x8007000ELL, v20);
      v23 = *(_DWORD *)(v21 + 8);
      *(_DWORD *)(v21 + 8) = 0;
      *((_DWORD *)v3 + 8) = v23;
      if ( !v23 )
        GdipUtil::BufferedPainterBase::TranslateGraphics(v3);
    }
    catch ( Base::Exception v29 )
    {
      v25 = Base::Exception::operator long(v29);
      v26 = 1;
      if ( v25 == -2147024882 )
        v26 = 3;
      *((_DWORD *)v28 + 8) = v26;
      Base::Exception::~Exception((Base::Exception *)v29);
      return v28;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180009ee0  mov     [rsp+arg_8], rbx
0x180009ee5  mov     [rsp+arg_10], rsi
0x180009eea  push    rdi
0x180009eeb  push    r14
0x180009eed  push    r15
0x180009eef  sub     rsp, 0A0h
0x180009ef6  mov     rax, cs:__security_cookie
0x180009efd  xor     rax, rsp
0x180009f00  mov     [rsp+0B8h+var_28], rax
0x180009f08  mov     rdi, rcx
0x180009f0b  mov     [rsp+0B8h+var_78], rcx
0x180009f10  lea     rax, ??_7BufferedPainterBase@GdipUtil@@6B@; const GdipUtil::BufferedPainterBase::`vftable'
0x180009f17  mov     [rcx], rax
0x180009f1a  mov     [rcx+8], rdx
0x180009f1e  movups  xmm0, xmmword ptr [r8]
0x180009f22  movups  xmmword ptr [rcx+10h], xmm0
0x180009f26  xor     r15d, r15d
0x180009f29  mov     [rcx+20h], r15d
0x180009f2d  mov     [rcx+28h], r15
0x180009f31  mov     [rcx+30h], r15b
0x180009f35  mov     eax, [rcx+10h]
0x180009f38  cmp     [rcx+18h], eax
0x180009f3b  jle     short loc_180009F48
0x180009f3d  mov     ecx, r15d
0x180009f40  mov     eax, [rdi+14h]
0x180009f43  cmp     [rdi+1Ch], eax
0x180009f46  jg      short loc_180009F50
0x180009f48  mov     ecx, 2
0x180009f4d  mov     [rdi+20h], ecx
0x180009f50  lea     rax, ??_7?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@6B@; const GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::`vftable'
0x180009f57  mov     [rdi], rax
0x180009f5a  mov     [rdi+38h], r15
0x180009f5e  mov     [rdi+40h], r15
0x180009f62  mov     [rdi+48h], r15
0x180009f66  test    ecx, ecx
0x180009f68  jnz     loc_18000A123
0x180009f6e  mov     ebx, [rdi+1Ch]
0x180009f71  sub     ebx, [rdi+14h]
0x180009f74  mov     esi, [rdi+18h]
0x180009f77  sub     esi, [rdi+10h]
0x180009f7a  mov     r14, [rdi+8]
0x180009f7e  mov     rcx, r15; this
0x180009f81  cmp     cs:?g_theBitmapCache@GdipUtilPrivate@@3VBitmapCache@1@A, r15d; GdipUtilPrivate::BitmapCache GdipUtilPrivate::g_theBitmapCache
0x180009f88  jle     short loc_180009FAF
0x180009f8a  mov     edx, esi
0x180009f8c  mov     eax, ebx
0x180009f8e  imul    rdx, rax
0x180009f92  mov     eax, 0FFFFFFFFh
0x180009f97  cmp     rdx, rax
0x180009f9a  ja      short loc_180009FAF
0x180009f9c  mov     edx, edx
0x180009f9e  shl     rdx, 2; unsigned int
0x180009fa2  cmp     rdx, rax
0x180009fa5  ja      short loc_180009FAF
0x180009fa7  call    ?GetFileMapping@BitmapCache@GdipUtilPrivate@@AEAAPEAXI@Z; GdipUtilPrivate::BitmapCache::GetFileMapping(uint)
0x180009fac  mov     rcx, rax
0x180009faf  xorps   xmm0, xmm0
0x180009fb2  xor     eax, eax
0x180009fb4  movups  xmmword ptr [rsp+0B8h+pbmi.bmiHeader.biWidth], xmm0
0x180009fb9  movups  xmmword ptr [rsp+0B8h+pbmi.bmiHeader.biSizeImage], xmm0
0x180009fbe  mov     qword ptr [rsp+0B8h+pbmi.bmiHeader.biClrImportant], rax
0x180009fc6  mov     [rsp+0B8h+pbmi.bmiHeader.biSize], 28h ; '('
0x180009fce  mov     [rsp+0B8h+pbmi.bmiHeader.biWidth], esi
0x180009fd2  neg     ebx
0x180009fd4  mov     [rsp+0B8h+pbmi.bmiHeader.biHeight], ebx
0x180009fd8  mov     qword ptr [rsp+0B8h+pbmi.bmiHeader.biPlanes], 200001h
0x180009fe1  mov     [rsp+0B8h+ppvBits], r15
0x180009fe6  mov     [rsp+0B8h+offset], r15d; offset
0x180009feb  mov     [rsp+0B8h+hSection], rcx; hSection
0x180009ff0  lea     r9, [rsp+0B8h+ppvBits]; ppvBits
0x180009ff5  xor     r8d, r8d; usage
0x180009ff8  lea     rdx, [rsp+0B8h+pbmi]; pbmi
0x180009ffd  mov     rcx, r14; hdc
0x18000a000  call    cs:__imp_CreateDIBSection
0x18000a006  mov     rbx, rax
0x18000a009  mov     rax, [rdi+38h]
0x18000a00d  cmp     rbx, rax
0x18000a010  jz      short loc_18000A026
0x18000a012  test    rax, rax
0x18000a015  jz      short loc_18000A020
0x18000a017  mov     rcx, rax; ho
0x18000a01a  call    cs:__imp_DeleteObject
0x18000a020  mov     [rdi+38h], rbx
0x18000a024  jmp     short loc_18000A029
0x18000a026  mov     rbx, rax
0x18000a029  test    rbx, rbx
0x18000a02c  jnz     short loc_18000A039
0x18000a02e  mov     ecx, 8007000Eh
0x18000a033  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000a039  mov     rcx, [rdi+8]; hdc
0x18000a03d  call    cs:__imp_CreateCompatibleDC
0x18000a043  mov     rbx, rax
0x18000a046  mov     [rdi+40h], rax
0x18000a04a  test    rax, rax
0x18000a04d  jnz     short loc_18000A05A
0x18000a04f  mov     ecx, 8007000Eh
0x18000a054  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000a05a  mov     rcx, rbx; hdc
0x18000a05d  call    cs:__imp_GetLayout
0x18000a063  test    al, 1
0x18000a065  jz      short loc_18000A075
0x18000a067  and     eax, 0FFFFFFFEh
0x18000a06a  mov     edx, eax; l
0x18000a06c  mov     rcx, rbx; hdc
0x18000a06f  call    cs:__imp_SetLayout
0x18000a075  mov     rdx, [rdi+38h]; h
0x18000a079  mov     rcx, [rdi+40h]; hdc
0x18000a07d  call    cs:__imp_SelectObject
0x18000a083  mov     [rdi+48h], rax
0x18000a087  test    rax, rax
0x18000a08a  jnz     short loc_18000A092
0x18000a08c  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18000a092  mov     rsi, [rdi+40h]
0x18000a096  mov     ecx, 10h
0x18000a09b  call    cs:__imp_GdipAlloc
0x18000a0a1  mov     rbx, rax
0x18000a0a4  test    rax, rax
0x18000a0a7  jz      short loc_18000A0C9
0x18000a0a9  mov     [rsp+0B8h+ppvBits], r15
0x18000a0ae  lea     rdx, [rsp+0B8h+ppvBits]
0x18000a0b3  mov     rcx, rsi
0x18000a0b6  call    cs:__imp_GdipCreateFromHDC
0x18000a0bc  mov     [rbx+8], eax
0x18000a0bf  mov     rax, [rsp+0B8h+ppvBits]
0x18000a0c4  mov     [rbx], rax
0x18000a0c7  jmp     short loc_18000A0CC
0x18000a0c9  mov     rbx, r15
0x18000a0cc  mov     rsi, [rdi+28h]
0x18000a0d0  cmp     rsi, rbx
0x18000a0d3  jz      short loc_18000A0F2
0x18000a0d5  test    rsi, rsi
0x18000a0d8  jz      short loc_18000A0EC
0x18000a0da  mov     rcx, [rsi]
0x18000a0dd  call    cs:__imp_GdipDeleteGraphics
0x18000a0e3  mov     rcx, rsi
0x18000a0e6  call    cs:__imp_GdipFree
0x18000a0ec  mov     [rdi+28h], rbx
0x18000a0f0  jmp     short loc_18000A0F5
0x18000a0f2  mov     rbx, rsi
0x18000a0f5  test    rbx, rbx
0x18000a0f8  jnz     short loc_18000A105
0x18000a0fa  mov     ecx, 8007000Eh
0x18000a0ff  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000a105  mov     eax, [rbx+8]
0x18000a108  mov     [rbx+8], r15d
0x18000a10c  mov     [rdi+20h], eax
0x18000a10f  test    eax, eax
0x18000a111  jnz     short loc_18000A11C
0x18000a113  mov     rcx, rdi; this
0x18000a116  call    ?TranslateGraphics@BufferedPainterBase@GdipUtil@@IEAAXXZ; GdipUtil::BufferedPainterBase::TranslateGraphics(void)
0x18000a11b  nop
0x18000a11c  jmp     short loc_18000A123
0x18000a11e  mov     rdi, [rsp+0B8h+var_78]
0x18000a123  mov     rax, rdi
0x18000a126  mov     rcx, [rsp+0B8h+var_28]
0x18000a12e  xor     rcx, rsp; StackCookie
0x18000a131  call    __security_check_cookie
0x18000a136  lea     r11, [rsp+0B8h+var_18]
0x18000a13e  mov     rbx, [r11+28h]
0x18000a142  mov     rsi, [r11+30h]
0x18000a146  mov     rsp, r11
0x18000a149  pop     r15
0x18000a14b  pop     r14
0x18000a14d  pop     rdi
0x18000a14e  retn
```
