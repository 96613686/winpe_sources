# GEL::Offscreen::CreateDIB(void)

- ea: `0x18010d674`
- end: `0x18010d80f`
- name: `?CreateDIB@Offscreen@GEL@@AEAAXXZ`
- size: `411`
- prototype: `void __fastcall(GEL::Offscreen *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016efd0`
- `0x1801f93d0`

## callees

- `0x180056ee0`
- `0x1800573f0`
- `0x18006286c`
- `0x1800629a0`
- `0x180064888`
- `0x1800d3964`
- `0x18010d674`
- `0x18010e57c`
- `0x18010e790`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18010d78d`
- `GDI32!CreateCompatibleDC` at `0x18010d78d`
- `GDI32!CreateDIBSection` at `0x18010d76b`
- `GDI32!CreateDIBSection` at `0x18010d76b`
- `GDI32!SelectObject` at `0x18010d7a7`
- `GDI32!SelectObject` at `0x18010d7a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GEL::Offscreen::CreateDIB(LONG *this)
{
  const struct Frame *v2; // rax
  HGDIOBJ *v3; // r14
  LONG v4; // eax
  LONG v5; // edx
  HBITMAP v6; // rbx
  HDC CompatibleDC; // rbx
  void *ppvBits; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-11h] BYREF
  int v10; // [rsp+50h] [rbp+7h]
  int v11; // [rsp+54h] [rbp+Bh]
  BITMAPINFO pbmi; // [rsp+58h] [rbp+Fh] BYREF

  v2 = (const struct Frame *)(*(__int64 (__fastcall **)(LONG *))(*(_QWORD *)this + 256LL))(this);
  Gfx::GDIPlusClipStack::ReleaseGraphics((Gfx::GDIPlusClipStack *)(this + 62), v2);
  Mso::TCntPtr<GEL::GraphicsSurface>::Clear(this + 80);
  ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(this + 74);
  v3 = (HGDIOBJ *)(this + 72);
  ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(this + 72);
  GEL::Offscreen::UpdateSize((GEL::Offscreen *)this);
  v4 = this[78];
  if ( this[76] >= v4 )
    v4 = this[76];
  this[78] = v4;
  v5 = this[79];
  if ( this[77] >= v5 )
    v5 = this[77];
  this[79] = v5;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biWidth = v4;
  pbmi.bmiHeader.biHeight = -v5;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  ppvBits = 0;
  v6 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
  ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(this + 72);
  *v3 = v6;
  if ( !v6 || !ppvBits )
  {
    *((_QWORD *)this + 39) = 0;
    v9[1] = 0;
    v9[2] = 0;
    v10 = 2;
    v11 = 8753674;
    v9[0] = &GEL::FatalException::`vftable';
    Ofc::CException::Throw((const struct Ofc::CException *)v9);
    __debugbreak();
  }
  CompatibleDC = CreateCompatibleDC(0);
  ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(this + 74);
  *((_QWORD *)this + 37) = CompatibleDC;
  SelectObject(CompatibleDC, *v3);
}

```

## disassembly

```asm
0x18010d674  mov     [rsp-8+arg_8], rbx
0x18010d679  mov     [rsp-8+arg_10], rsi
0x18010d67e  push    rbp
0x18010d67f  push    rdi
0x18010d680  push    r14
0x18010d682  lea     rbp, [rsp-47h]
0x18010d687  sub     rsp, 90h
0x18010d68e  mov     rax, cs:__security_cookie
0x18010d695  xor     rax, rsp
0x18010d698  mov     [rbp+57h+var_18], rax
0x18010d69c  mov     rdi, rcx
0x18010d69f  mov     rax, [rcx]
0x18010d6a2  mov     rax, [rax+100h]
0x18010d6a9  call    cs:__guard_dispatch_icall_fptr
0x18010d6af  mov     rdx, rax; struct Frame *
0x18010d6b2  lea     rcx, [rdi+0F8h]; this
0x18010d6b9  call    ?ReleaseGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@@Z; Gfx::GDIPlusClipStack::ReleaseGraphics(Gfx::ITarget::Frame const *)
0x18010d6be  lea     rcx, [rdi+140h]
0x18010d6c5  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x18010d6ca  lea     rsi, [rdi+128h]
0x18010d6d1  mov     rcx, rsi
0x18010d6d4  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x18010d6d9  lea     r14, [rdi+120h]
0x18010d6e0  mov     rcx, r14
0x18010d6e3  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x18010d6e8  mov     rcx, rdi; this
0x18010d6eb  call    ?UpdateSize@Offscreen@GEL@@AEAAXXZ; GEL::Offscreen::UpdateSize(void)
0x18010d6f0  mov     eax, [rdi+138h]
0x18010d6f6  mov     ecx, [rdi+130h]
0x18010d6fc  cmp     ecx, eax
0x18010d6fe  cmovge  eax, ecx
0x18010d701  mov     [rdi+138h], eax
0x18010d707  mov     edx, [rdi+13Ch]
0x18010d70d  mov     ecx, [rdi+134h]
0x18010d713  cmp     ecx, edx
0x18010d715  cmovge  edx, ecx
0x18010d718  mov     [rdi+13Ch], edx
0x18010d71e  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x18010d726  xorps   xmm0, xmm0
0x18010d729  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18010d72e  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18010d735  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18010d738  neg     edx
0x18010d73a  mov     [rbp+57h+pbmi.bmiHeader.biHeight], edx
0x18010d73d  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18010d745  mov     [rbp+57h+ppvBits], 0
0x18010d74d  mov     [rsp+0A0h+offset], 0; offset
0x18010d755  mov     [rsp+0A0h+hSection], 0; hSection
0x18010d75e  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18010d762  xor     r8d, r8d; usage
0x18010d765  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18010d769  xor     ecx, ecx; hdc
0x18010d76b  call    cs:__imp_CreateDIBSection
0x18010d771  mov     rbx, rax
0x18010d774  mov     rcx, r14
0x18010d777  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x18010d77c  mov     [r14], rbx
0x18010d77f  test    rbx, rbx
0x18010d782  jz      short loc_18010D7D1
0x18010d784  cmp     [rbp+57h+ppvBits], 0
0x18010d789  jz      short loc_18010D7D1
0x18010d78b  xor     ecx, ecx; hdc
0x18010d78d  call    cs:__imp_CreateCompatibleDC
0x18010d793  mov     rbx, rax
0x18010d796  mov     rcx, rsi
0x18010d799  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x18010d79e  mov     [rsi], rbx
0x18010d7a1  mov     rdx, [r14]; h
0x18010d7a4  mov     rcx, rbx; hdc
0x18010d7a7  call    cs:__imp_SelectObject
0x18010d7ad  mov     rcx, [rbp+57h+var_18]
0x18010d7b1  xor     rcx, rsp; StackCookie
0x18010d7b4  call    __security_check_cookie
0x18010d7b9  lea     r11, [rsp+0A0h+var_10]
0x18010d7c1  mov     rbx, [r11+28h]
0x18010d7c5  mov     rsi, [r11+30h]
0x18010d7c9  mov     rsp, r11
0x18010d7cc  pop     r14
0x18010d7ce  pop     rdi
0x18010d7cf  pop     rbp
0x18010d7d0  retn
0x18010d7d1  mov     qword ptr [rdi+138h], 0
0x18010d7dc  mov     [rbp+57h+var_60], 0
0x18010d7e4  mov     [rbp+57h+var_58], 0
0x18010d7ec  mov     [rbp+57h+var_50], 2
0x18010d7f3  mov     [rbp+57h+var_4C], 85920Ah
0x18010d7fa  lea     rax, ??_7FatalException@GEL@@6B@; const GEL::FatalException::`vftable'
0x18010d801  mov     [rbp+57h+var_68], rax
0x18010d805  lea     rcx, [rbp+57h+var_68]; struct Ofc::CException *
0x18010d809  call    ?Throw@CException@Ofc@@KAXAEBV12@@Z; Ofc::CException::Throw(Ofc::CException const &)
0x18010d80e  int     3; Trap to Debugger
```
