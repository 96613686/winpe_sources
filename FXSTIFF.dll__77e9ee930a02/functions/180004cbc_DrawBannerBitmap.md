# DrawBannerBitmap

- ea: `0x180004cbc`
- end: `0x180004f14`
- name: `DrawBannerBitmap`
- size: `600`
- prototype: `_BOOL8 __fastcall(const WCHAR *, LONG, LONG, HBITMAP *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ed0`

## callees

- `0x180004cbc`
- `0x18001899e`
- `0x1800189d0`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180004e06`
- `GDI32!CreateFontIndirectW` at `0x180004e06`
- `GDI32!DeleteObject` at `0x180004e97`
- `GDI32!DeleteObject` at `0x180004eca`
- `GDI32!DeleteObject` at `0x180004e97`
- `GDI32!DeleteObject` at `0x180004eca`
- `GDI32!DeleteDC` at `0x180004ede`
- `GDI32!DeleteDC` at `0x180004ede`
- `GDI32!CreateCompatibleDC` at `0x180004da0`
- `GDI32!CreateCompatibleDC` at `0x180004da0`
- `GDI32!CreateDIBSection` at `0x180004dd0`
- `GDI32!CreateDIBSection` at `0x180004dd0`
- `GDI32!SelectObject` at `0x180004dee`
- `GDI32!SelectObject` at `0x180004e20`
- `GDI32!SelectObject` at `0x180004e83`
- `GDI32!SelectObject` at `0x180004eae`
- `GDI32!SelectObject` at `0x180004dee`
- `GDI32!SelectObject` at `0x180004e20`
- `GDI32!SelectObject` at `0x180004e83`
- `GDI32!SelectObject` at `0x180004eae`
- `USER32!DrawTextW` at `0x180004e4d`
- `USER32!DrawTextW` at `0x180004e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall DrawBannerBitmap(const WCHAR *a1, LONG a2, LONG a3, HBITMAP *a4, _QWORD *a5)
{
  HDC CompatibleDC; // rbx
  HBITMAP v6; // rsi
  HGDIOBJ v7; // r15
  HFONT v8; // r14
  HBITMAP v10; // rax
  HFONT v11; // rax
  HGDIOBJ v12; // rdi
  void *v13; // rcx
  void *ppvBits; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpchText; // [rsp+40h] [rbp-C0h]
  _BYTE pbmi[48]; // [rsp+48h] [rbp-B8h] BYREF
  tagRECT rc; // [rsp+78h] [rbp-88h] BYREF
  LOGFONTW lf; // [rsp+90h] [rbp-70h] BYREF

  lpchText = a1;
  *(_DWORD *)&pbmi[8] = -a3;
  CompatibleDC = 0;
  rc.bottom = a3;
  v6 = 0;
  *(_DWORD *)&pbmi[4] = a2;
  *(_DWORD *)&pbmi[20] = 0;
  v7 = 0;
  *(_DWORD *)&pbmi[36] = 0;
  v8 = 0;
  ppvBits = 0;
  *(_QWORD *)&rc.left = 0;
  rc.right = a2;
  *(_DWORD *)pbmi = 40;
  *(_QWORD *)&pbmi[12] = 65537;
  *(_DWORD *)&pbmi[24] = 7874;
  *(_QWORD *)&pbmi[28] = 7874;
  *(_QWORD *)&pbmi[40] = 0xFFFFFF;
  memset_0(&lf, 0, sizeof(lf));
  lf.lfWeight = 400;
  lf.lfHeight = 2 - a3;
  *(_DWORD *)&lf.lfCharSet = 1;
  lf.lfPitchAndFamily = 1;
  if ( lpchText
    && a2 > 0
    && a3 > 0
    && (CompatibleDC = CreateCompatibleDC(0)) != 0
    && (v10 = CreateDIBSection(0, (const BITMAPINFO *)pbmi, 0, &ppvBits, 0, 0), (v6 = v10) != 0)
    && (v7 = SelectObject(CompatibleDC, v10)) != 0
    && (v11 = CreateFontIndirectW(&lf), (v8 = v11) != 0)
    && (v12 = SelectObject(CompatibleDC, v11)) != 0 )
  {
    DrawTextW(CompatibleDC, lpchText, -1, &rc, 0x25u);
    v13 = ppvBits;
    *a4 = v6;
    *a5 = v13;
    SelectObject(CompatibleDC, v12);
  }
  else
  {
    *a4 = 0;
    *a5 = 0;
  }
  if ( v8 )
    DeleteObject(v8);
  if ( v7 )
    SelectObject(CompatibleDC, v7);
  if ( !ppvBits && v6 )
    DeleteObject(v6);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  return *a5 != 0;
}

```

## disassembly

```asm
0x180004cbc  push    rbp
0x180004cbe  push    rbx
0x180004cbf  push    rsi
0x180004cc0  push    rdi
0x180004cc1  push    r12
0x180004cc3  push    r13
0x180004cc5  push    r14
0x180004cc7  push    r15
0x180004cc9  lea     rbp, [rsp-8]
0x180004cce  sub     rsp, 108h
0x180004cd5  mov     rax, cs:__security_cookie
0x180004cdc  xor     rax, rsp
0x180004cdf  mov     [rbp+40h+var_50], rax
0x180004ce3  mov     r12, [rbp+40h+arg_20]
0x180004ce7  mov     eax, r8d
0x180004cea  neg     eax
0x180004cec  mov     [rsp+140h+lpchText], rcx
0x180004cf1  xor     ecx, ecx
0x180004cf3  mov     [rsp+140h+var_110], r8d
0x180004cf8  mov     dword ptr [rsp+140h+pbmi+8], eax
0x180004cfc  mov     ebx, ecx
0x180004cfe  mov     eax, 1EC2h
0x180004d03  mov     [rbp+40h+rc.bottom], r8d
0x180004d07  mov     [rsp+140h+var_10C], edx
0x180004d0b  mov     esi, ecx
0x180004d0d  lea     r8d, [rcx+5Ch]; Size
0x180004d11  mov     dword ptr [rsp+140h+pbmi+4], edx
0x180004d15  mov     dword ptr [rsp+140h+pbmi+14h], ecx
0x180004d19  mov     r15d, ecx
0x180004d1c  mov     dword ptr [rsp+140h+pbmi+24h], ecx
0x180004d20  mov     r14d, ecx
0x180004d23  mov     [rsp+140h+ppvBits], rcx
0x180004d28  mov     edi, ecx
0x180004d2a  mov     qword ptr [rsp+140h+rc.left], rcx
0x180004d2f  mov     r13, r9
0x180004d32  mov     [rbp+40h+rc.right], edx
0x180004d35  lea     rcx, [rbp+40h+lf]; void *
0x180004d39  xor     edx, edx; Val
0x180004d3b  mov     dword ptr [rsp+140h+pbmi], 28h ; '('
0x180004d43  mov     qword ptr [rsp+140h+pbmi+0Ch], 10001h
0x180004d4c  mov     dword ptr [rsp+140h+pbmi+18h], eax
0x180004d50  mov     qword ptr [rsp+140h+pbmi+1Ch], rax
0x180004d55  mov     qword ptr [rsp+140h+pbmi+28h], 0FFFFFFh
0x180004d5e  call    memset_0
0x180004d63  mov     ecx, [rsp+140h+var_110]
0x180004d67  lea     eax, [rdi+2]
0x180004d6a  sub     eax, ecx
0x180004d6c  mov     [rbp+40h+lf.lfWeight], 190h
0x180004d73  mov     [rbp+40h+lf.lfHeight], eax
0x180004d76  mov     dword ptr [rbp+40h+lf.lfCharSet], 1
0x180004d7d  mov     [rbp+40h+lf.lfPitchAndFamily], 1
0x180004d81  cmp     [rsp+140h+lpchText], rbx
0x180004d86  jz      loc_180004E68
0x180004d8c  cmp     [rsp+140h+var_10C], ebx
0x180004d90  jle     loc_180004E68
0x180004d96  test    ecx, ecx
0x180004d98  jle     loc_180004E68
0x180004d9e  xor     ecx, ecx; hdc
0x180004da0  call    cs:__imp_CreateCompatibleDC
0x180004da7  nop     dword ptr [rax+rax+00h]
0x180004dac  mov     rbx, rax
0x180004daf  test    rax, rax
0x180004db2  jz      loc_180004E68
0x180004db8  mov     [rsp+140h+offset], esi; offset
0x180004dbc  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x180004dc1  xor     r8d, r8d; usage
0x180004dc4  mov     [rsp+140h+hSection], rdi; hSection
0x180004dc9  lea     rdx, [rsp+140h+pbmi]; pbmi
0x180004dce  xor     ecx, ecx; hdc
0x180004dd0  call    cs:__imp_CreateDIBSection
0x180004dd7  nop     dword ptr [rax+rax+00h]
0x180004ddc  mov     rsi, rax
0x180004ddf  test    rax, rax
0x180004de2  jz      loc_180004E68
0x180004de8  mov     rdx, rax; h
0x180004deb  mov     rcx, rbx; hdc
0x180004dee  call    cs:__imp_SelectObject
0x180004df5  nop     dword ptr [rax+rax+00h]
0x180004dfa  mov     r15, rax
0x180004dfd  test    rax, rax
0x180004e00  jz      short loc_180004E68
0x180004e02  lea     rcx, [rbp+40h+lf]; lplf
0x180004e06  call    cs:__imp_CreateFontIndirectW
0x180004e0d  nop     dword ptr [rax+rax+00h]
0x180004e12  mov     r14, rax
0x180004e15  test    rax, rax
0x180004e18  jz      short loc_180004E68
0x180004e1a  mov     rdx, rax; h
0x180004e1d  mov     rcx, rbx; hdc
0x180004e20  call    cs:__imp_SelectObject
0x180004e27  nop     dword ptr [rax+rax+00h]
0x180004e2c  mov     rdi, rax
0x180004e2f  test    rax, rax
0x180004e32  jz      short loc_180004E68
0x180004e34  mov     rdx, [rsp+140h+lpchText]; lpchText
0x180004e39  lea     r9, [rsp+140h+rc]; lprc
0x180004e3e  or      r8d, 0FFFFFFFFh; cchText
0x180004e42  mov     dword ptr [rsp+140h+hSection], 25h ; '%'; format
0x180004e4a  mov     rcx, rbx; hdc
0x180004e4d  call    cs:__imp_DrawTextW
0x180004e54  nop     dword ptr [rax+rax+00h]
0x180004e59  mov     rcx, [rsp+140h+ppvBits]
0x180004e5e  mov     [r13+0], rsi
0x180004e62  mov     [r12], rcx
0x180004e66  jmp     short loc_180004E7D
0x180004e68  mov     qword ptr [r13+0], 0
0x180004e70  mov     qword ptr [r12], 0
0x180004e78  test    rdi, rdi
0x180004e7b  jz      short loc_180004E8F
0x180004e7d  mov     rdx, rdi; h
0x180004e80  mov     rcx, rbx; hdc
0x180004e83  call    cs:__imp_SelectObject
0x180004e8a  nop     dword ptr [rax+rax+00h]
0x180004e8f  test    r14, r14
0x180004e92  jz      short loc_180004EA3
0x180004e94  mov     rcx, r14; ho
0x180004e97  call    cs:__imp_DeleteObject
0x180004e9e  nop     dword ptr [rax+rax+00h]
0x180004ea3  test    r15, r15
0x180004ea6  jz      short loc_180004EBA
0x180004ea8  mov     rdx, r15; h
0x180004eab  mov     rcx, rbx; hdc
0x180004eae  call    cs:__imp_SelectObject
0x180004eb5  nop     dword ptr [rax+rax+00h]
0x180004eba  cmp     [rsp+140h+ppvBits], 0
0x180004ec0  jnz     short loc_180004ED6
0x180004ec2  test    rsi, rsi
0x180004ec5  jz      short loc_180004ED6
0x180004ec7  mov     rcx, rsi; ho
0x180004eca  call    cs:__imp_DeleteObject
0x180004ed1  nop     dword ptr [rax+rax+00h]
0x180004ed6  test    rbx, rbx
0x180004ed9  jz      short loc_180004EEA
0x180004edb  mov     rcx, rbx; hdc
0x180004ede  call    cs:__imp_DeleteDC
0x180004ee5  nop     dword ptr [rax+rax+00h]
0x180004eea  xor     eax, eax
0x180004eec  cmp     [r12], rax
0x180004ef0  setnz   al
0x180004ef3  mov     rcx, [rbp+40h+var_50]
0x180004ef7  xor     rcx, rsp; StackCookie
0x180004efa  call    __security_check_cookie
0x180004eff  add     rsp, 108h
0x180004f06  pop     r15
0x180004f08  pop     r14
0x180004f0a  pop     r13
0x180004f0c  pop     r12
0x180004f0e  pop     rdi
0x180004f0f  pop     rsi
0x180004f10  pop     rbx
0x180004f11  pop     rbp
0x180004f12  retn
```
