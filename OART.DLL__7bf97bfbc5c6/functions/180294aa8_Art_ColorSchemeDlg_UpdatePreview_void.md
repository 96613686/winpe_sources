# Art::ColorSchemeDlg::UpdatePreview(void)

- ea: `0x180294aa8`
- end: `0x180294d43`
- name: `?UpdatePreview@ColorSchemeDlg@Art@@AEAAXXZ`
- size: `667`
- prototype: `void __fastcall(Art::ColorSchemeDlg *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180477b60`
- `0x180994e70`
- `0x1809951c4`

## callees

- `0x18000dbc0`
- `0x180070fe0`
- `0x180071720`
- `0x1800f4b68`
- `0x180294aa8`
- `0x180294d44`
- `0x1802cec40`
- `0x1803375ac`
- `0x180337dbc`
- `0x1803d83f4`
- `0x180a1b6bc`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180294c5a`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180294c5a`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180294b89`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180294b89`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180294c6c`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180294c6c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180294cc3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180294cd3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180294cc3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180294cd3`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180294aee`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180294b13`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180294aee`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180294b13`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180294c8b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180294c8b`
- `GDI32!SelectObject` at `0x180294cf7`
- `GDI32!SelectObject` at `0x180294cf7`
- `GDI32!DeleteDC` at `0x180294d00`
- `GDI32!DeleteDC` at `0x180294d00`
- `USER32!GetSysColor` at `0x180294be6`
- `USER32!GetSysColor` at `0x180294be6`
- `USER32!GetDC` at `0x180294b60`
- `USER32!GetDC` at `0x180294b60`
- `USER32!ReleaseDC` at `0x180294d11`
- `USER32!ReleaseDC` at `0x180294d11`

## pseudocode

```c
void __fastcall Art::ColorSchemeDlg::UpdatePreview(Art::ColorSchemeDlg *this)
{
  unsigned int SampleWidth; // edi
  Art *v3; // rcx
  bool v4; // r8
  LONG v5; // eax
  Art *v6; // rcx
  LONG v7; // r15d
  bool v8; // r8
  LONG v9; // eax
  LONG v10; // edi
  HDC DC; // r14
  HBITMAP CompatibleBitmap; // rsi
  DWORD SysColor; // eax
  HDC v14; // rdi
  const struct tagRECT *v15; // r9
  NetUI::BaseValue *v16; // rcx
  NetUI::BaseValue *v17; // rsi
  __int64 v18; // rbx
  NetUI::BaseValue *v19; // [rsp+50h] [rbp-88h] BYREF
  struct tagRECT v20; // [rsp+58h] [rbp-80h] BYREF
  struct tagRECT v21; // [rsp+68h] [rbp-70h] BYREF
  HDC hdc[2]; // [rsp+78h] [rbp-60h] BYREF
  HBITMAP v23; // [rsp+88h] [rbp-50h]
  HDC v24; // [rsp+90h] [rbp-48h]
  __int128 v25; // [rsp+98h] [rbp-40h]
  RECT rc; // [rsp+A8h] [rbp-30h] BYREF

  SampleWidth = Art::ColorSchemeDlg::GetSampleWidth(this);
  if ( Art::FDynamicDpiEnabled(v3) )
    v5 = Art::ScaleForDPI((char *)this + 968, SampleWidth);
  else
    v5 = NetUI::ScalePixelsForSystemSettings((NetUI *)SampleWidth, 0, v4);
  v7 = v5;
  if ( Art::FDynamicDpiEnabled(v6) )
    v9 = Art::ScaleForDPI((char *)this + 968, 166);
  else
    v9 = NetUI::ScalePixelsForSystemSettings((NetUI *)0xA6, 0, v8);
  v10 = v9;
  *(_QWORD *)&v20.left = 0;
  v20.right = v7 / 2;
  v20.bottom = v9;
  v21.left = v7 / 2;
  v21.top = 0;
  v21.right = v7 - 1;
  v21.bottom = v9;
  DC = GetDC(0);
  v24 = DC;
  v25 = 0;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, v7, v10, 0);
  v23 = CompatibleBitmap;
  if ( !CompatibleBitmap )
    Ofc::CLastErrorException::ThrowTag(0x13906CCu);
  *(_OWORD *)hdc = 0;
  Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc, DC, CompatibleBitmap);
  *(_QWORD *)&rc.left = 0;
  rc.right = v7;
  rc.bottom = v10;
  SysColor = GetSysColor(5);
  v14 = hdc[0];
  Ofc::FillRect(hdc[0], (HDC)SysColor, &rc, v15);
  Art::ColorSchemeDlg::DrawSample(this, v14, &v20, 0);
  Art::ColorSchemeDlg::DrawSample(this, v14, &v21, 1);
  v19 = 0;
  FlexUI::FlexValue::CreateImage(CompatibleBitmap, (struct FlexUI::FlexValueSP *)&v19, 0, 0xFFFFFFFF, 0, 0, 0, 1, 0);
  v16 = v19;
  if ( v19 )
  {
    FlexUI::FlexValue::SetGraphicScaleForDPI(v19, 0);
    v16 = v19;
  }
  v17 = v16;
  v18 = *((_QWORD *)this + 119);
  if ( v18 )
  {
    if ( !v16 )
      goto LABEL_16;
    NetUI::BaseValue::AddRef(v16);
    (*(void (__fastcall **)(__int64, _QWORD, __int64, NetUI::BaseValue *))(*(_QWORD *)v18 + 48LL))(v18, 0, 13, v17);
    NetUI::BaseValue::Release(v17);
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v16 = v19;
LABEL_16:
  if ( v16 )
    NetUI::BaseValue::Release(v16);
  v19 = 0;
  if ( v14 )
  {
    if ( hdc[1] )
      SelectObject(v14, hdc[1]);
    DeleteDC(v14);
  }
  if ( DC )
    ReleaseDC(0, DC);
}

```

## disassembly

```asm
0x180294aa8  mov     [rsp+arg_8], rbx
0x180294aad  mov     [rsp+arg_10], rsi
0x180294ab2  push    rdi
0x180294ab3  push    r14
0x180294ab5  push    r15
0x180294ab7  sub     rsp, 0C0h
0x180294abe  mov     rax, cs:__security_cookie
0x180294ac5  xor     rax, rsp
0x180294ac8  mov     [rsp+0D8h+var_20], rax
0x180294ad0  mov     rbx, rcx
0x180294ad3  call    ?GetSampleWidth@ColorSchemeDlg@Art@@AEAAHXZ; Art::ColorSchemeDlg::GetSampleWidth(void)
0x180294ad8  mov     edi, eax
0x180294ada  lea     rsi, [rbx+3C8h]
0x180294ae1  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x180294ae6  test    al, al
0x180294ae8  jnz     short loc_180294AF6
0x180294aea  xor     edx, edx
0x180294aec  mov     ecx, edi
0x180294aee  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x180294af4  jmp     short loc_180294B00
0x180294af6  mov     edx, edi
0x180294af8  mov     rcx, rsi
0x180294afb  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x180294b00  mov     r15d, eax
0x180294b03  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x180294b08  test    al, al
0x180294b0a  jnz     short loc_180294B1B
0x180294b0c  xor     edx, edx
0x180294b0e  mov     ecx, 0A6h
0x180294b13  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x180294b19  jmp     short loc_180294B28
0x180294b1b  mov     edx, 0A6h
0x180294b20  mov     rcx, rsi
0x180294b23  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x180294b28  mov     edi, eax
0x180294b2a  mov     qword ptr [rsp+0D8h+var_80.left], 0
0x180294b33  mov     eax, r15d
0x180294b36  cdq
0x180294b37  mov     ecx, 2
0x180294b3c  idiv    ecx
0x180294b3e  mov     [rsp+0D8h+var_80.right], eax
0x180294b42  mov     [rsp+0D8h+var_80.bottom], edi
0x180294b46  mov     [rsp+0D8h+var_70.left], eax
0x180294b4a  mov     [rsp+0D8h+var_70.top], 0
0x180294b52  lea     eax, [r15-1]
0x180294b56  mov     [rsp+0D8h+var_70.right], eax
0x180294b5a  mov     [rsp+0D8h+var_70.bottom], edi
0x180294b5e  xor     ecx, ecx; hWnd
0x180294b60  call    cs:__imp_GetDC
0x180294b66  mov     r14, rax
0x180294b69  mov     [rsp+0D8h+var_48], rax
0x180294b71  xorps   xmm0, xmm0
0x180294b74  movdqu  [rsp+0D8h+var_40], xmm0
0x180294b7d  xor     r9d, r9d
0x180294b80  mov     r8d, edi
0x180294b83  mov     edx, r15d
0x180294b86  mov     rcx, rax
0x180294b89  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180294b8f  mov     rsi, rax
0x180294b92  mov     [rsp+0D8h+var_50], rax
0x180294b9a  test    rax, rax
0x180294b9d  jnz     short loc_180294BAD
0x180294b9f  mov     ecx, 13906CCh; unsigned int
0x180294ba4  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x180294ba9  nop
0x180294baa  jmp     short $+2
0x180294bac  nop
0x180294bad  xorps   xmm0, xmm0
0x180294bb0  movdqu  xmmword ptr [rsp+0D8h+hdc], xmm0
0x180294bb6  mov     r8, rsi; HBITMAP
0x180294bb9  mov     rdx, r14; HDC
0x180294bbc  lea     rcx, [rsp+0D8h+hdc]; this
0x180294bc1  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x180294bc6  mov     qword ptr [rsp+0D8h+rc.left], 0
0x180294bd2  mov     [rsp+0D8h+rc.right], r15d
0x180294bda  mov     [rsp+0D8h+rc.bottom], edi
0x180294be1  mov     ecx, 5; nIndex
0x180294be6  call    cs:__imp_GetSysColor
0x180294bec  lea     r8, [rsp+0D8h+rc]; lprc
0x180294bf4  mov     edx, eax; HDC
0x180294bf6  mov     rdi, [rsp+0D8h+hdc]
0x180294bfb  mov     rcx, rdi; this
0x180294bfe  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180294c03  xor     r9d, r9d; bool
0x180294c06  lea     r8, [rsp+0D8h+var_80]; struct tagRECT *
0x180294c0b  mov     rdx, rdi; HDC
0x180294c0e  mov     rcx, rbx; this
0x180294c11  call    ?DrawSample@ColorSchemeDlg@Art@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::ColorSchemeDlg::DrawSample(HDC__ *,tagRECT const &,bool)
0x180294c16  mov     r9b, 1; bool
0x180294c19  lea     r8, [rsp+0D8h+var_70]; struct tagRECT *
0x180294c1e  mov     rdx, rdi; HDC
0x180294c21  mov     rcx, rbx; this
0x180294c24  call    ?DrawSample@ColorSchemeDlg@Art@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::ColorSchemeDlg::DrawSample(HDC__ *,tagRECT const &,bool)
0x180294c29  mov     [rsp+0D8h+var_88], 0
0x180294c32  mov     [rsp+0D8h+var_98], 0
0x180294c37  mov     [rsp+0D8h+var_A0], 1
0x180294c3c  mov     [rsp+0D8h+var_A8], 0
0x180294c41  mov     [rsp+0D8h+var_B0], 0
0x180294c46  mov     [rsp+0D8h+var_B8], 0
0x180294c4b  or      r9d, 0FFFFFFFFh
0x180294c4f  xor     r8d, r8d
0x180294c52  lea     rdx, [rsp+0D8h+var_88]
0x180294c57  mov     rcx, rsi
0x180294c5a  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x180294c60  mov     rcx, [rsp+0D8h+var_88]
0x180294c65  test    rcx, rcx
0x180294c68  jz      short loc_180294C77
0x180294c6a  xor     edx, edx
0x180294c6c  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x180294c72  mov     rcx, [rsp+0D8h+var_88]; this
0x180294c77  mov     rsi, rcx
0x180294c7a  mov     rbx, [rbx+3B8h]
0x180294c81  test    rbx, rbx
0x180294c84  jnz     short loc_180294C93
0x180294c86  mov     ecx, 7A0740h
0x180294c8b  call    cs:__imp_MsoShipAssertTagProc
0x180294c91  jmp     short loc_180294CC9
0x180294c93  test    rsi, rsi
0x180294c96  jz      short loc_180294CCE
0x180294c98  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x180294c9d  mov     rcx, [rsp+0D8h+var_88]
0x180294ca2  test    rsi, rsi
0x180294ca5  jz      short loc_180294CCE
0x180294ca7  mov     rax, [rbx]
0x180294caa  mov     r9, rsi
0x180294cad  xor     edx, edx
0x180294caf  lea     r8d, [rdx+0Dh]
0x180294cb3  mov     rcx, rbx
0x180294cb6  mov     rax, [rax+30h]
0x180294cba  call    cs:__guard_dispatch_icall_fptr
0x180294cc0  mov     rcx, rsi
0x180294cc3  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180294cc9  mov     rcx, [rsp+0D8h+var_88]
0x180294cce  test    rcx, rcx
0x180294cd1  jz      short loc_180294CD9
0x180294cd3  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180294cd9  mov     [rsp+0D8h+var_88], 0
0x180294ce2  test    rdi, rdi
0x180294ce5  jz      short loc_180294D07
0x180294ce7  mov     rdx, [rsp+0D8h+hdc+8]; h
0x180294cef  test    rdx, rdx
0x180294cf2  jz      short loc_180294CFD
0x180294cf4  mov     rcx, rdi; hdc
0x180294cf7  call    cs:__imp_SelectObject
0x180294cfd  mov     rcx, rdi; hdc
0x180294d00  call    cs:__imp_DeleteDC
0x180294d06  nop
0x180294d07  test    r14, r14
0x180294d0a  jz      short loc_180294D18
0x180294d0c  mov     rdx, r14; hDC
0x180294d0f  xor     ecx, ecx; hWnd
0x180294d11  call    cs:__imp_ReleaseDC
0x180294d17  nop
0x180294d18  jmp     short $+2
0x180294d1a  mov     rcx, [rsp+0D8h+var_20]
0x180294d22  xor     rcx, rsp; StackCookie
0x180294d25  call    __security_check_cookie
0x180294d2a  lea     r11, [rsp+0D8h+var_18]
0x180294d32  mov     rbx, [r11+28h]
0x180294d36  mov     rsi, [r11+30h]
0x180294d3a  mov     rsp, r11
0x180294d3d  pop     r15
0x180294d3f  pop     r14
0x180294d41  pop     rdi
0x180294d42  retn
```
