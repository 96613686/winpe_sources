# Art::FontSchemeDlg::CreateSwitchPreviewArrow(bool)

- ea: `0x180404c6c`
- end: `0x180404eae`
- name: `?CreateSwitchPreviewArrow@FontSchemeDlg@Art@@CA?AVFlexValueSP@FlexUI@@_N@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180404310`

## callees

- `0x180070fe0`
- `0x1803375ac`
- `0x180337dbc`
- `0x180404c6c`
- `0x180a1b6bc`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180404e1b`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180404e1b`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180404cdd`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180404cdd`
- `GDI32!CreatePen` at `0x180404d2a`
- `GDI32!CreatePen` at `0x180404d2a`
- `GDI32!LineTo` at `0x180404dc6`
- `GDI32!LineTo` at `0x180404dd7`
- `GDI32!LineTo` at `0x180404dc6`
- `GDI32!LineTo` at `0x180404dd7`
- `GDI32!MoveToEx` at `0x180404daa`
- `GDI32!MoveToEx` at `0x180404daa`
- `GDI32!SelectObject` at `0x180404d4b`
- `GDI32!SelectObject` at `0x180404e34`
- `GDI32!SelectObject` at `0x180404e5a`
- `GDI32!SelectObject` at `0x180404d4b`
- `GDI32!SelectObject` at `0x180404e34`
- `GDI32!SelectObject` at `0x180404e5a`
- `GDI32!DeleteObject` at `0x180404e42`
- `GDI32!DeleteObject` at `0x180404e42`
- `GDI32!DeleteDC` at `0x180404e63`
- `GDI32!DeleteDC` at `0x180404e63`
- `USER32!GetSysColor` at `0x180404d16`
- `USER32!GetSysColor` at `0x180404d6a`
- `USER32!GetSysColor` at `0x180404d16`
- `USER32!GetSysColor` at `0x180404d6a`
- `USER32!GetDC` at `0x180404cb2`
- `USER32!GetDC` at `0x180404cb2`
- `USER32!ReleaseDC` at `0x180404e74`
- `USER32!ReleaseDC` at `0x180404e74`

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
0x180404c6c  mov     [rsp+arg_8], rbx
0x180404c71  mov     [rsp+arg_10], rbp
0x180404c76  mov     [rsp+arg_18], rsi
0x180404c7b  push    rdi
0x180404c7c  push    r12
0x180404c7e  push    r13
0x180404c80  push    r14
0x180404c82  push    r15
0x180404c84  sub     rsp, 0B0h
0x180404c8b  mov     rax, cs:__security_cookie
0x180404c92  xor     rax, rsp
0x180404c95  mov     [rsp+0D8h+var_30], rax
0x180404c9d  movzx   r12d, dl
0x180404ca1  mov     [rsp+0D8h+var_88], r12b
0x180404ca6  mov     [rsp+0D8h+var_70], rcx
0x180404cab  mov     [rsp+0D8h+var_80], rcx
0x180404cb0  xor     ecx, ecx; hWnd
0x180404cb2  call    cs:__imp_GetDC
0x180404cb8  mov     rsi, rax
0x180404cbb  mov     [rsp+0D8h+hDC], rax
0x180404cc3  xorps   xmm0, xmm0
0x180404cc6  movdqu  [rsp+0D8h+var_50], xmm0
0x180404ccf  xor     r9d, r9d
0x180404cd2  lea     edx, [r9+0Ah]
0x180404cd6  lea     r8d, [r9+5]
0x180404cda  mov     rcx, rax
0x180404cdd  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180404ce3  mov     [rsp+0D8h+var_80], rax
0x180404ce8  test    rax, rax
0x180404ceb  jnz     short loc_180404CF8
0x180404ced  mov     ecx, 13906CCh; unsigned int
0x180404cf2  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x180404cf7  int     3; Trap to Debugger
0x180404cf8  xorps   xmm0, xmm0
0x180404cfb  movdqu  xmmword ptr [rsp+0D8h+hdc], xmm0
0x180404d01  mov     r8, rax; HBITMAP
0x180404d04  mov     rdx, rsi; HDC
0x180404d07  lea     rcx, [rsp+0D8h+hdc]; this
0x180404d0c  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x180404d11  mov     ecx, 8; nIndex
0x180404d16  call    cs:__imp_GetSysColor
0x180404d1c  bts     eax, 19h
0x180404d20  mov     r8d, eax; color
0x180404d23  mov     edx, 1; cWidth
0x180404d28  xor     ecx, ecx; iStyle
0x180404d2a  call    cs:__imp_CreatePen
0x180404d30  mov     rbp, rax
0x180404d33  xor     r14d, r14d
0x180404d36  mov     rbx, [rsp+0D8h+hdc]
0x180404d3b  test    rax, rax
0x180404d3e  jz      short loc_180404D54
0x180404d40  test    rbx, rbx
0x180404d43  jz      short loc_180404D54
0x180404d45  mov     rdx, rax; h
0x180404d48  mov     rcx, rbx; hdc
0x180404d4b  call    cs:__imp_SelectObject
0x180404d51  mov     r14, rax
0x180404d54  movdqa  xmm0, cs:__xmm@000000050000000a0000000000000000
0x180404d5c  movdqu  xmmword ptr [rsp+0D8h+rc.left], xmm0
0x180404d65  mov     ecx, 0Fh; nIndex
0x180404d6a  call    cs:__imp_GetSysColor
0x180404d70  lea     r8, [rsp+0D8h+rc]; lprc
0x180404d78  mov     edx, eax; HDC
0x180404d7a  mov     rcx, rbx; this
0x180404d7d  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180404d82  xor     esi, esi
0x180404d84  mov     edi, r12d
0x180404d87  shl     edi, 2
0x180404d8a  mov     al, r12b
0x180404d8d  neg     al
0x180404d8f  sbb     r12d, r12d
0x180404d92  and     r12d, 6
0x180404d96  lea     r13d, [rsi+9]
0x180404d9a  mov     r15b, [rsp+0D8h+var_88]
0x180404d9f  xor     r9d, r9d; lppt
0x180404da2  mov     r8d, edi; y
0x180404da5  mov     edx, esi; x
0x180404da7  mov     rcx, rbx; hdc
0x180404daa  call    cs:__imp_MoveToEx
0x180404db0  lea     eax, [r13-5]
0x180404db4  mov     r8d, esi
0x180404db7  test    r15b, r15b
0x180404dba  cmovz   r8d, eax; y
0x180404dbe  mov     edx, 4; x
0x180404dc3  mov     rcx, rbx; hdc
0x180404dc6  call    cs:__imp_LineTo
0x180404dcc  lea     r8d, [r12-1]; y
0x180404dd1  mov     edx, r13d; x
0x180404dd4  mov     rcx, rbx; hdc
0x180404dd7  call    cs:__imp_LineTo
0x180404ddd  inc     esi
0x180404ddf  dec     r13d
0x180404de2  cmp     r13d, 7
0x180404de6  jg      short loc_180404D9F
0x180404de8  mov     rdi, [rsp+0D8h+var_70]
0x180404ded  xor     r12d, r12d
0x180404df0  mov     [rdi], r12
0x180404df3  mov     [rsp+0D8h+var_98], r12b
0x180404df8  mov     [rsp+0D8h+var_A0], 1
0x180404dfd  mov     [rsp+0D8h+var_A8], r12b
0x180404e02  mov     [rsp+0D8h+var_B0], r12b
0x180404e07  mov     [rsp+0D8h+var_B8], r12b
0x180404e0c  or      r9d, 0FFFFFFFFh
0x180404e10  xor     r8d, r8d
0x180404e13  mov     rdx, rdi
0x180404e16  mov     rcx, [rsp+0D8h+var_80]
0x180404e1b  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x180404e21  test    r14, r14
0x180404e24  mov     rsi, [rsp+0D8h+hDC]
0x180404e2c  jz      short loc_180404E3A
0x180404e2e  mov     rdx, r14; h
0x180404e31  mov     rcx, rbx; hdc
0x180404e34  call    cs:__imp_SelectObject
0x180404e3a  test    rbp, rbp
0x180404e3d  jz      short loc_180404E48
0x180404e3f  mov     rcx, rbp; ho
0x180404e42  call    cs:__imp_DeleteObject
0x180404e48  test    rbx, rbx
0x180404e4b  jz      short loc_180404E6A
0x180404e4d  mov     rdx, [rsp+0D8h+hdc+8]; h
0x180404e52  test    rdx, rdx
0x180404e55  jz      short loc_180404E60
0x180404e57  mov     rcx, rbx; hdc
0x180404e5a  call    cs:__imp_SelectObject
0x180404e60  mov     rcx, rbx; hdc
0x180404e63  call    cs:__imp_DeleteDC
0x180404e69  nop
0x180404e6a  test    rsi, rsi
0x180404e6d  jz      short loc_180404E7A
0x180404e6f  mov     rdx, rsi; hDC
0x180404e72  xor     ecx, ecx; hWnd
0x180404e74  call    cs:__imp_ReleaseDC
0x180404e7a  mov     rax, rdi
0x180404e7d  mov     rcx, [rsp+0D8h+var_30]
0x180404e85  xor     rcx, rsp; StackCookie
0x180404e88  call    __security_check_cookie
0x180404e8d  lea     r11, [rsp+0D8h+var_28]
0x180404e95  mov     rbx, [r11+38h]
0x180404e99  mov     rbp, [r11+40h]
0x180404e9d  mov     rsi, [r11+48h]
0x180404ea1  mov     rsp, r11
0x180404ea4  pop     r15
0x180404ea6  pop     r14
0x180404ea8  pop     r13
0x180404eaa  pop     r12
0x180404eac  pop     rdi
0x180404ead  retn
```
