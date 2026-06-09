# GEL::Offscreen::CreateDIB(void)

- ea: `0x180143f24`
- end: `0x1801440bf`
- name: `?CreateDIB@Offscreen@GEL@@AEAAXXZ`
- size: `411`
- prototype: `void __fastcall(GEL::Offscreen *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180173230`
- `0x1801fc7e0`

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x180081318`
- `0x180081440`
- `0x180082598`
- `0x1800beb6c`
- `0x1800dd774`
- `0x180143f24`
- `0x1801440c0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18014403d`
- `GDI32!CreateCompatibleDC` at `0x18014403d`
- `GDI32!CreateDIBSection` at `0x18014401b`
- `GDI32!CreateDIBSection` at `0x18014401b`
- `GDI32!SelectObject` at `0x180144057`
- `GDI32!SelectObject` at `0x180144057`

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
0x180143f24  mov     [rsp-8+arg_8], rbx
0x180143f29  mov     [rsp-8+arg_10], rsi
0x180143f2e  push    rbp
0x180143f2f  push    rdi
0x180143f30  push    r14
0x180143f32  lea     rbp, [rsp-47h]
0x180143f37  sub     rsp, 90h
0x180143f3e  mov     rax, cs:__security_cookie
0x180143f45  xor     rax, rsp
0x180143f48  mov     [rbp+57h+var_18], rax
0x180143f4c  mov     rdi, rcx
0x180143f4f  mov     rax, [rcx]
0x180143f52  mov     rax, [rax+100h]
0x180143f59  call    cs:__guard_dispatch_icall_fptr
0x180143f5f  mov     rdx, rax; struct Frame *
0x180143f62  lea     rcx, [rdi+0F8h]; this
0x180143f69  call    ?ReleaseGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@@Z; Gfx::GDIPlusClipStack::ReleaseGraphics(Gfx::ITarget::Frame const *)
0x180143f6e  lea     rcx, [rdi+140h]
0x180143f75  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x180143f7a  lea     rsi, [rdi+128h]
0x180143f81  mov     rcx, rsi
0x180143f84  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x180143f89  lea     r14, [rdi+120h]
0x180143f90  mov     rcx, r14
0x180143f93  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x180143f98  mov     rcx, rdi; this
0x180143f9b  call    ?UpdateSize@Offscreen@GEL@@AEAAXXZ; GEL::Offscreen::UpdateSize(void)
0x180143fa0  mov     eax, [rdi+138h]
0x180143fa6  mov     ecx, [rdi+130h]
0x180143fac  cmp     ecx, eax
0x180143fae  cmovge  eax, ecx
0x180143fb1  mov     [rdi+138h], eax
0x180143fb7  mov     edx, [rdi+13Ch]
0x180143fbd  mov     ecx, [rdi+134h]
0x180143fc3  cmp     ecx, edx
0x180143fc5  cmovge  edx, ecx
0x180143fc8  mov     [rdi+13Ch], edx
0x180143fce  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x180143fd6  xorps   xmm0, xmm0
0x180143fd9  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180143fde  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180143fe5  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180143fe8  neg     edx
0x180143fea  mov     [rbp+57h+pbmi.bmiHeader.biHeight], edx
0x180143fed  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180143ff5  mov     [rbp+57h+ppvBits], 0
0x180143ffd  mov     [rsp+0A0h+offset], 0; offset
0x180144005  mov     [rsp+0A0h+hSection], 0; hSection
0x18014400e  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180144012  xor     r8d, r8d; usage
0x180144015  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180144019  xor     ecx, ecx; hdc
0x18014401b  call    cs:__imp_CreateDIBSection
0x180144021  mov     rbx, rax
0x180144024  mov     rcx, r14
0x180144027  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x18014402c  mov     [r14], rbx
0x18014402f  test    rbx, rbx
0x180144032  jz      short loc_180144081
0x180144034  cmp     [rbp+57h+ppvBits], 0
0x180144039  jz      short loc_180144081
0x18014403b  xor     ecx, ecx; hdc
0x18014403d  call    cs:__imp_CreateCompatibleDC
0x180144043  mov     rbx, rax
0x180144046  mov     rcx, rsi
0x180144049  call    ?Empty@?$TGDIHolder@PEAUHDC__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HDC__ *>::Empty(void)
0x18014404e  mov     [rsi], rbx
0x180144051  mov     rdx, [r14]; h
0x180144054  mov     rcx, rbx; hdc
0x180144057  call    cs:__imp_SelectObject
0x18014405d  mov     rcx, [rbp+57h+var_18]
0x180144061  xor     rcx, rsp; StackCookie
0x180144064  call    __security_check_cookie
0x180144069  lea     r11, [rsp+0A0h+var_10]
0x180144071  mov     rbx, [r11+28h]
0x180144075  mov     rsi, [r11+30h]
0x180144079  mov     rsp, r11
0x18014407c  pop     r14
0x18014407e  pop     rdi
0x18014407f  pop     rbp
0x180144080  retn
0x180144081  mov     qword ptr [rdi+138h], 0
0x18014408c  mov     [rbp+57h+var_60], 0
0x180144094  mov     [rbp+57h+var_58], 0
0x18014409c  mov     [rbp+57h+var_50], 2
0x1801440a3  mov     [rbp+57h+var_4C], 85920Ah
0x1801440aa  lea     rax, ??_7FatalException@GEL@@6B@; const GEL::FatalException::`vftable'
0x1801440b1  mov     [rbp+57h+var_68], rax
0x1801440b5  lea     rcx, [rbp+57h+var_68]; struct Ofc::CException *
0x1801440b9  call    ?Throw@CException@Ofc@@KAXAEBV12@@Z; Ofc::CException::Throw(Ofc::CException const &)
0x1801440be  int     3; Trap to Debugger
```
