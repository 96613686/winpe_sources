# Art::ColorSchemeDlg::UpdatePreview(void)

- ea: `0x18041b528`
- end: `0x18041b7c3`
- name: `?UpdatePreview@ColorSchemeDlg@Art@@AEAAXXZ`
- size: `667`
- prototype: `void __fastcall(Art::ColorSchemeDlg *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180419e38`
- `0x18099f050`
- `0x18099f3a4`

## callees

- `0x180128840`
- `0x1801d8b80`
- `0x180279030`
- `0x180279050`
- `0x18029ab98`
- `0x18041b528`
- `0x18041b7c4`
- `0x18042d584`
- `0x180435010`
- `0x1804360f8`
- `0x180a2473c`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x18041b6da`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x18041b6da`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18041b609`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18041b609`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x18041b6ec`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x18041b6ec`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041b743`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041b753`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041b743`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18041b753`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18041b56e`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18041b593`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18041b56e`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18041b593`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041b70b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18041b70b`
- `GDI32!SelectObject` at `0x18041b777`
- `GDI32!SelectObject` at `0x18041b777`
- `GDI32!DeleteDC` at `0x18041b780`
- `GDI32!DeleteDC` at `0x18041b780`
- `USER32!GetSysColor` at `0x18041b666`
- `USER32!GetSysColor` at `0x18041b666`
- `USER32!GetDC` at `0x18041b5e0`
- `USER32!GetDC` at `0x18041b5e0`
- `USER32!ReleaseDC` at `0x18041b791`
- `USER32!ReleaseDC` at `0x18041b791`

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
0x18041b528  mov     [rsp+arg_8], rbx
0x18041b52d  mov     [rsp+arg_10], rsi
0x18041b532  push    rdi
0x18041b533  push    r14
0x18041b535  push    r15
0x18041b537  sub     rsp, 0C0h
0x18041b53e  mov     rax, cs:__security_cookie
0x18041b545  xor     rax, rsp
0x18041b548  mov     [rsp+0D8h+var_20], rax
0x18041b550  mov     rbx, rcx
0x18041b553  call    ?GetSampleWidth@ColorSchemeDlg@Art@@AEAAHXZ; Art::ColorSchemeDlg::GetSampleWidth(void)
0x18041b558  mov     edi, eax
0x18041b55a  lea     rsi, [rbx+3C8h]
0x18041b561  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18041b566  test    al, al
0x18041b568  jnz     short loc_18041B576
0x18041b56a  xor     edx, edx
0x18041b56c  mov     ecx, edi
0x18041b56e  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x18041b574  jmp     short loc_18041B580
0x18041b576  mov     edx, edi
0x18041b578  mov     rcx, rsi
0x18041b57b  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x18041b580  mov     r15d, eax
0x18041b583  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18041b588  test    al, al
0x18041b58a  jnz     short loc_18041B59B
0x18041b58c  xor     edx, edx
0x18041b58e  mov     ecx, 0A6h
0x18041b593  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x18041b599  jmp     short loc_18041B5A8
0x18041b59b  mov     edx, 0A6h
0x18041b5a0  mov     rcx, rsi
0x18041b5a3  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x18041b5a8  mov     edi, eax
0x18041b5aa  mov     qword ptr [rsp+0D8h+var_80.left], 0
0x18041b5b3  mov     eax, r15d
0x18041b5b6  cdq
0x18041b5b7  mov     ecx, 2
0x18041b5bc  idiv    ecx
0x18041b5be  mov     [rsp+0D8h+var_80.right], eax
0x18041b5c2  mov     [rsp+0D8h+var_80.bottom], edi
0x18041b5c6  mov     [rsp+0D8h+var_70.left], eax
0x18041b5ca  mov     [rsp+0D8h+var_70.top], 0
0x18041b5d2  lea     eax, [r15-1]
0x18041b5d6  mov     [rsp+0D8h+var_70.right], eax
0x18041b5da  mov     [rsp+0D8h+var_70.bottom], edi
0x18041b5de  xor     ecx, ecx; hWnd
0x18041b5e0  call    cs:__imp_GetDC
0x18041b5e6  mov     r14, rax
0x18041b5e9  mov     [rsp+0D8h+var_48], rax
0x18041b5f1  xorps   xmm0, xmm0
0x18041b5f4  movdqu  [rsp+0D8h+var_40], xmm0
0x18041b5fd  xor     r9d, r9d
0x18041b600  mov     r8d, edi
0x18041b603  mov     edx, r15d
0x18041b606  mov     rcx, rax
0x18041b609  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x18041b60f  mov     rsi, rax
0x18041b612  mov     [rsp+0D8h+var_50], rax
0x18041b61a  test    rax, rax
0x18041b61d  jnz     short loc_18041B62D
0x18041b61f  mov     ecx, 13906CCh; unsigned int
0x18041b624  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x18041b629  nop
0x18041b62a  jmp     short $+2
0x18041b62c  nop
0x18041b62d  xorps   xmm0, xmm0
0x18041b630  movdqu  xmmword ptr [rsp+0D8h+hdc], xmm0
0x18041b636  mov     r8, rsi; HBITMAP
0x18041b639  mov     rdx, r14; HDC
0x18041b63c  lea     rcx, [rsp+0D8h+hdc]; this
0x18041b641  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x18041b646  mov     qword ptr [rsp+0D8h+rc.left], 0
0x18041b652  mov     [rsp+0D8h+rc.right], r15d
0x18041b65a  mov     [rsp+0D8h+rc.bottom], edi
0x18041b661  mov     ecx, 5; nIndex
0x18041b666  call    cs:__imp_GetSysColor
0x18041b66c  lea     r8, [rsp+0D8h+rc]; lprc
0x18041b674  mov     edx, eax; HDC
0x18041b676  mov     rdi, [rsp+0D8h+hdc]
0x18041b67b  mov     rcx, rdi; this
0x18041b67e  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x18041b683  xor     r9d, r9d; bool
0x18041b686  lea     r8, [rsp+0D8h+var_80]; struct tagRECT *
0x18041b68b  mov     rdx, rdi; HDC
0x18041b68e  mov     rcx, rbx; this
0x18041b691  call    ?DrawSample@ColorSchemeDlg@Art@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::ColorSchemeDlg::DrawSample(HDC__ *,tagRECT const &,bool)
0x18041b696  mov     r9b, 1; bool
0x18041b699  lea     r8, [rsp+0D8h+var_70]; struct tagRECT *
0x18041b69e  mov     rdx, rdi; HDC
0x18041b6a1  mov     rcx, rbx; this
0x18041b6a4  call    ?DrawSample@ColorSchemeDlg@Art@@AEAAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::ColorSchemeDlg::DrawSample(HDC__ *,tagRECT const &,bool)
0x18041b6a9  mov     [rsp+0D8h+var_88], 0
0x18041b6b2  mov     [rsp+0D8h+var_98], 0
0x18041b6b7  mov     [rsp+0D8h+var_A0], 1
0x18041b6bc  mov     [rsp+0D8h+var_A8], 0
0x18041b6c1  mov     [rsp+0D8h+var_B0], 0
0x18041b6c6  mov     [rsp+0D8h+var_B8], 0
0x18041b6cb  or      r9d, 0FFFFFFFFh
0x18041b6cf  xor     r8d, r8d
0x18041b6d2  lea     rdx, [rsp+0D8h+var_88]
0x18041b6d7  mov     rcx, rsi
0x18041b6da  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x18041b6e0  mov     rcx, [rsp+0D8h+var_88]
0x18041b6e5  test    rcx, rcx
0x18041b6e8  jz      short loc_18041B6F7
0x18041b6ea  xor     edx, edx
0x18041b6ec  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x18041b6f2  mov     rcx, [rsp+0D8h+var_88]; this
0x18041b6f7  mov     rsi, rcx
0x18041b6fa  mov     rbx, [rbx+3B8h]
0x18041b701  test    rbx, rbx
0x18041b704  jnz     short loc_18041B713
0x18041b706  mov     ecx, 7A0740h
0x18041b70b  call    cs:__imp_MsoShipAssertTagProc
0x18041b711  jmp     short loc_18041B749
0x18041b713  test    rsi, rsi
0x18041b716  jz      short loc_18041B74E
0x18041b718  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x18041b71d  mov     rcx, [rsp+0D8h+var_88]
0x18041b722  test    rsi, rsi
0x18041b725  jz      short loc_18041B74E
0x18041b727  mov     rax, [rbx]
0x18041b72a  mov     r9, rsi
0x18041b72d  xor     edx, edx
0x18041b72f  lea     r8d, [rdx+0Dh]
0x18041b733  mov     rcx, rbx
0x18041b736  mov     rax, [rax+30h]
0x18041b73a  call    cs:__guard_dispatch_icall_fptr
0x18041b740  mov     rcx, rsi
0x18041b743  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18041b749  mov     rcx, [rsp+0D8h+var_88]
0x18041b74e  test    rcx, rcx
0x18041b751  jz      short loc_18041B759
0x18041b753  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x18041b759  mov     [rsp+0D8h+var_88], 0
0x18041b762  test    rdi, rdi
0x18041b765  jz      short loc_18041B787
0x18041b767  mov     rdx, [rsp+0D8h+hdc+8]; h
0x18041b76f  test    rdx, rdx
0x18041b772  jz      short loc_18041B77D
0x18041b774  mov     rcx, rdi; hdc
0x18041b777  call    cs:__imp_SelectObject
0x18041b77d  mov     rcx, rdi; hdc
0x18041b780  call    cs:__imp_DeleteDC
0x18041b786  nop
0x18041b787  test    r14, r14
0x18041b78a  jz      short loc_18041B798
0x18041b78c  mov     rdx, r14; hDC
0x18041b78f  xor     ecx, ecx; hWnd
0x18041b791  call    cs:__imp_ReleaseDC
0x18041b797  nop
0x18041b798  jmp     short $+2
0x18041b79a  mov     rcx, [rsp+0D8h+var_20]
0x18041b7a2  xor     rcx, rsp; StackCookie
0x18041b7a5  call    __security_check_cookie
0x18041b7aa  lea     r11, [rsp+0D8h+var_18]
0x18041b7b2  mov     rbx, [r11+28h]
0x18041b7b6  mov     rsi, [r11+30h]
0x18041b7ba  mov     rsp, r11
0x18041b7bd  pop     r15
0x18041b7bf  pop     r14
0x18041b7c1  pop     rdi
0x18041b7c2  retn
```
