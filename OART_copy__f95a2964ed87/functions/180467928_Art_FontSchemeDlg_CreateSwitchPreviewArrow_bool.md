# Art::FontSchemeDlg::CreateSwitchPreviewArrow(bool)

- ea: `0x180467928`
- end: `0x180467b6a`
- name: `?CreateSwitchPreviewArrow@FontSchemeDlg@Art@@CA?AVFlexValueSP@FlexUI@@_N@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180466fcc`

## callees

- `0x180278e70`
- `0x180435010`
- `0x1804360f8`
- `0x180467928`
- `0x180a2473c`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180467ad7`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180467ad7`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180467999`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180467999`
- `GDI32!CreatePen` at `0x1804679e6`
- `GDI32!CreatePen` at `0x1804679e6`
- `GDI32!LineTo` at `0x180467a82`
- `GDI32!LineTo` at `0x180467a93`
- `GDI32!LineTo` at `0x180467a82`
- `GDI32!LineTo` at `0x180467a93`
- `GDI32!MoveToEx` at `0x180467a66`
- `GDI32!MoveToEx` at `0x180467a66`
- `GDI32!SelectObject` at `0x180467a07`
- `GDI32!SelectObject` at `0x180467af0`
- `GDI32!SelectObject` at `0x180467b16`
- `GDI32!SelectObject` at `0x180467a07`
- `GDI32!SelectObject` at `0x180467af0`
- `GDI32!SelectObject` at `0x180467b16`
- `GDI32!DeleteObject` at `0x180467afe`
- `GDI32!DeleteObject` at `0x180467afe`
- `GDI32!DeleteDC` at `0x180467b1f`
- `GDI32!DeleteDC` at `0x180467b1f`
- `USER32!GetSysColor` at `0x1804679d2`
- `USER32!GetSysColor` at `0x180467a26`
- `USER32!GetSysColor` at `0x1804679d2`
- `USER32!GetSysColor` at `0x180467a26`
- `USER32!GetDC` at `0x18046796e`
- `USER32!GetDC` at `0x18046796e`
- `USER32!ReleaseDC` at `0x180467b30`
- `USER32!ReleaseDC` at `0x180467b30`

## pseudocode

```c
struct FlexUI::FlexValueSP *__fastcall Art::FontSchemeDlg::CreateSwitchPreviewArrow(
        struct FlexUI::FlexValueSP *a1,
        unsigned __int8 a2)
{
  int v2; // r12d
  HDC DC; // rsi
  HBITMAP CompatibleBitmap; // rax
  DWORD SysColor; // eax
  HPEN Pen; // rax
  HPEN v7; // rbp
  HGDIOBJ v8; // r14
  HDC v9; // rbx
  DWORD v10; // eax
  const struct tagRECT *v11; // r9
  int v12; // esi
  int v13; // edi
  int v14; // r12d
  int i; // r13d
  int v16; // r8d
  HDC v17; // rsi
  HBITMAP v20; // [rsp+58h] [rbp-80h]
  HDC hdc[2]; // [rsp+70h] [rbp-68h] BYREF
  HDC hDC; // [rsp+80h] [rbp-58h]
  __int128 v24; // [rsp+88h] [rbp-50h]
  RECT rc; // [rsp+98h] [rbp-40h] BYREF

  v2 = a2;
  DC = GetDC(0);
  hDC = DC;
  v24 = 0;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, 10, 5, 0);
  v20 = CompatibleBitmap;
  if ( !CompatibleBitmap )
  {
    Ofc::CLastErrorException::ThrowTag(0x13906CCu);
    __debugbreak();
  }
  *(_OWORD *)hdc = 0;
  Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc, DC, CompatibleBitmap);
  SysColor = GetSysColor(8);
  Pen = CreatePen(0, 1, SysColor | 0x2000000);
  v7 = Pen;
  v8 = 0;
  v9 = hdc[0];
  if ( Pen && hdc[0] )
    v8 = SelectObject(hdc[0], Pen);
  rc = (RECT)_mm_load_si128((const __m128i *)&_xmm);
  v10 = GetSysColor(15);
  Ofc::FillRect(v9, (HDC)v10, &rc, v11);
  v12 = 0;
  v13 = 4 * v2;
  v14 = (_BYTE)v2 != 0 ? 6 : 0;
  for ( i = 9; i > 7; --i )
  {
    MoveToEx(v9, v12, v13, 0);
    v16 = v12;
    if ( !a2 )
      v16 = i - 5;
    LineTo(v9, 4, v16);
    LineTo(v9, i, v14 - 1);
    ++v12;
  }
  *(_QWORD *)a1 = 0;
  FlexUI::FlexValue::CreateImage(v20, a1, 0, 0xFFFFFFFF, 0, 0, 0, 1, 0);
  v17 = hDC;
  if ( v8 )
    SelectObject(v9, v8);
  if ( v7 )
    DeleteObject(v7);
  if ( v9 )
  {
    if ( hdc[1] )
      SelectObject(v9, hdc[1]);
    DeleteDC(v9);
  }
  if ( v17 )
    ReleaseDC(0, v17);
  return a1;
}

```

## disassembly

```asm
0x180467928  mov     [rsp+arg_8], rbx
0x18046792d  mov     [rsp+arg_10], rbp
0x180467932  mov     [rsp+arg_18], rsi
0x180467937  push    rdi
0x180467938  push    r12
0x18046793a  push    r13
0x18046793c  push    r14
0x18046793e  push    r15
0x180467940  sub     rsp, 0B0h
0x180467947  mov     rax, cs:__security_cookie
0x18046794e  xor     rax, rsp
0x180467951  mov     [rsp+0D8h+var_30], rax
0x180467959  movzx   r12d, dl
0x18046795d  mov     [rsp+0D8h+var_88], r12b
0x180467962  mov     [rsp+0D8h+var_70], rcx
0x180467967  mov     [rsp+0D8h+var_80], rcx
0x18046796c  xor     ecx, ecx; hWnd
0x18046796e  call    cs:__imp_GetDC
0x180467974  mov     rsi, rax
0x180467977  mov     [rsp+0D8h+hDC], rax
0x18046797f  xorps   xmm0, xmm0
0x180467982  movdqu  [rsp+0D8h+var_50], xmm0
0x18046798b  xor     r9d, r9d
0x18046798e  lea     edx, [r9+0Ah]
0x180467992  lea     r8d, [r9+5]
0x180467996  mov     rcx, rax
0x180467999  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x18046799f  mov     [rsp+0D8h+var_80], rax
0x1804679a4  test    rax, rax
0x1804679a7  jnz     short loc_1804679B4
0x1804679a9  mov     ecx, 13906CCh; unsigned int
0x1804679ae  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1804679b3  int     3; Trap to Debugger
0x1804679b4  xorps   xmm0, xmm0
0x1804679b7  movdqu  xmmword ptr [rsp+0D8h+hdc], xmm0
0x1804679bd  mov     r8, rax; HBITMAP
0x1804679c0  mov     rdx, rsi; HDC
0x1804679c3  lea     rcx, [rsp+0D8h+hdc]; this
0x1804679c8  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1804679cd  mov     ecx, 8; nIndex
0x1804679d2  call    cs:__imp_GetSysColor
0x1804679d8  bts     eax, 19h
0x1804679dc  mov     r8d, eax; color
0x1804679df  mov     edx, 1; cWidth
0x1804679e4  xor     ecx, ecx; iStyle
0x1804679e6  call    cs:__imp_CreatePen
0x1804679ec  mov     rbp, rax
0x1804679ef  xor     r14d, r14d
0x1804679f2  mov     rbx, [rsp+0D8h+hdc]
0x1804679f7  test    rax, rax
0x1804679fa  jz      short loc_180467A10
0x1804679fc  test    rbx, rbx
0x1804679ff  jz      short loc_180467A10
0x180467a01  mov     rdx, rax; h
0x180467a04  mov     rcx, rbx; hdc
0x180467a07  call    cs:__imp_SelectObject
0x180467a0d  mov     r14, rax
0x180467a10  movdqa  xmm0, cs:__xmm@000000050000000a0000000000000000
0x180467a18  movdqu  xmmword ptr [rsp+0D8h+rc.left], xmm0
0x180467a21  mov     ecx, 0Fh; nIndex
0x180467a26  call    cs:__imp_GetSysColor
0x180467a2c  lea     r8, [rsp+0D8h+rc]; lprc
0x180467a34  mov     edx, eax; HDC
0x180467a36  mov     rcx, rbx; this
0x180467a39  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180467a3e  xor     esi, esi
0x180467a40  mov     edi, r12d
0x180467a43  shl     edi, 2
0x180467a46  mov     al, r12b
0x180467a49  neg     al
0x180467a4b  sbb     r12d, r12d
0x180467a4e  and     r12d, 6
0x180467a52  lea     r13d, [rsi+9]
0x180467a56  mov     r15b, [rsp+0D8h+var_88]
0x180467a5b  xor     r9d, r9d; lppt
0x180467a5e  mov     r8d, edi; y
0x180467a61  mov     edx, esi; x
0x180467a63  mov     rcx, rbx; hdc
0x180467a66  call    cs:__imp_MoveToEx
0x180467a6c  lea     eax, [r13-5]
0x180467a70  mov     r8d, esi
0x180467a73  test    r15b, r15b
0x180467a76  cmovz   r8d, eax; y
0x180467a7a  mov     edx, 4; x
0x180467a7f  mov     rcx, rbx; hdc
0x180467a82  call    cs:__imp_LineTo
0x180467a88  lea     r8d, [r12-1]; y
0x180467a8d  mov     edx, r13d; x
0x180467a90  mov     rcx, rbx; hdc
0x180467a93  call    cs:__imp_LineTo
0x180467a99  inc     esi
0x180467a9b  dec     r13d
0x180467a9e  cmp     r13d, 7
0x180467aa2  jg      short loc_180467A5B
0x180467aa4  mov     rdi, [rsp+0D8h+var_70]
0x180467aa9  xor     r12d, r12d
0x180467aac  mov     [rdi], r12
0x180467aaf  mov     [rsp+0D8h+var_98], r12b
0x180467ab4  mov     [rsp+0D8h+var_A0], 1
0x180467ab9  mov     [rsp+0D8h+var_A8], r12b
0x180467abe  mov     [rsp+0D8h+var_B0], r12b
0x180467ac3  mov     [rsp+0D8h+var_B8], r12b
0x180467ac8  or      r9d, 0FFFFFFFFh
0x180467acc  xor     r8d, r8d
0x180467acf  mov     rdx, rdi
0x180467ad2  mov     rcx, [rsp+0D8h+var_80]
0x180467ad7  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x180467add  test    r14, r14
0x180467ae0  mov     rsi, [rsp+0D8h+hDC]
0x180467ae8  jz      short loc_180467AF6
0x180467aea  mov     rdx, r14; h
0x180467aed  mov     rcx, rbx; hdc
0x180467af0  call    cs:__imp_SelectObject
0x180467af6  test    rbp, rbp
0x180467af9  jz      short loc_180467B04
0x180467afb  mov     rcx, rbp; ho
0x180467afe  call    cs:__imp_DeleteObject
0x180467b04  test    rbx, rbx
0x180467b07  jz      short loc_180467B26
0x180467b09  mov     rdx, [rsp+0D8h+hdc+8]; h
0x180467b0e  test    rdx, rdx
0x180467b11  jz      short loc_180467B1C
0x180467b13  mov     rcx, rbx; hdc
0x180467b16  call    cs:__imp_SelectObject
0x180467b1c  mov     rcx, rbx; hdc
0x180467b1f  call    cs:__imp_DeleteDC
0x180467b25  nop
0x180467b26  test    rsi, rsi
0x180467b29  jz      short loc_180467B36
0x180467b2b  mov     rdx, rsi; hDC
0x180467b2e  xor     ecx, ecx; hWnd
0x180467b30  call    cs:__imp_ReleaseDC
0x180467b36  mov     rax, rdi
0x180467b39  mov     rcx, [rsp+0D8h+var_30]
0x180467b41  xor     rcx, rsp; StackCookie
0x180467b44  call    __security_check_cookie
0x180467b49  lea     r11, [rsp+0D8h+var_28]
0x180467b51  mov     rbx, [r11+38h]
0x180467b55  mov     rbp, [r11+40h]
0x180467b59  mov     rsi, [r11+48h]
0x180467b5d  mov     rsp, r11
0x180467b60  pop     r15
0x180467b62  pop     r14
0x180467b64  pop     r13
0x180467b66  pop     r12
0x180467b68  pop     rdi
0x180467b69  retn
```
