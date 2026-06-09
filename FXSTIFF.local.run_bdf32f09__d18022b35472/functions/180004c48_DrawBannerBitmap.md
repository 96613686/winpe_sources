# DrawBannerBitmap

- ea: `0x180004c48`
- end: `0x180004e59`
- name: `DrawBannerBitmap`
- size: `529`
- prototype: `_BOOL8 __fastcall(const WCHAR *, LONG, LONG, HBITMAP *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005d80`

## callees

- `0x180004c48`
- `0x180017bce`
- `0x180017c00`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180004d7c`
- `GDI32!CreateFontIndirectW` at `0x180004d7c`
- `GDI32!DeleteObject` at `0x180004df5`
- `GDI32!DeleteObject` at `0x180004e1c`
- `GDI32!DeleteObject` at `0x180004df5`
- `GDI32!DeleteObject` at `0x180004e1c`
- `GDI32!DeleteDC` at `0x180004e2a`
- `GDI32!DeleteDC` at `0x180004e2a`
- `GDI32!CreateCompatibleDC` at `0x180004d2c`
- `GDI32!CreateCompatibleDC` at `0x180004d2c`
- `GDI32!CreateDIBSection` at `0x180004d56`
- `GDI32!CreateDIBSection` at `0x180004d56`
- `GDI32!SelectObject` at `0x180004d6a`
- `GDI32!SelectObject` at `0x180004d90`
- `GDI32!SelectObject` at `0x180004de7`
- `GDI32!SelectObject` at `0x180004e06`
- `GDI32!SelectObject` at `0x180004d6a`
- `GDI32!SelectObject` at `0x180004d90`
- `GDI32!SelectObject` at `0x180004de7`
- `GDI32!SelectObject` at `0x180004e06`
- `USER32!DrawTextW` at `0x180004db7`
- `USER32!DrawTextW` at `0x180004db7`

## pseudocode

```c
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
0x180004c48  push    rbp
0x180004c4a  push    rbx
0x180004c4b  push    rsi
0x180004c4c  push    rdi
0x180004c4d  push    r12
0x180004c4f  push    r13
0x180004c51  push    r14
0x180004c53  push    r15
0x180004c55  lea     rbp, [rsp-8]
0x180004c5a  sub     rsp, 108h
0x180004c61  mov     rax, cs:__security_cookie
0x180004c68  xor     rax, rsp
0x180004c6b  mov     [rbp+40h+var_50], rax
0x180004c6f  mov     r12, [rbp+40h+arg_20]
0x180004c73  mov     eax, r8d
0x180004c76  neg     eax
0x180004c78  mov     [rsp+140h+lpchText], rcx
0x180004c7d  xor     ecx, ecx
0x180004c7f  mov     [rsp+140h+var_110], r8d
0x180004c84  mov     dword ptr [rsp+140h+pbmi+8], eax
0x180004c88  mov     ebx, ecx
0x180004c8a  mov     eax, 1EC2h
0x180004c8f  mov     [rbp+40h+rc.bottom], r8d
0x180004c93  mov     [rsp+140h+var_10C], edx
0x180004c97  mov     esi, ecx
0x180004c99  lea     r8d, [rcx+5Ch]; Size
0x180004c9d  mov     dword ptr [rsp+140h+pbmi+4], edx
0x180004ca1  mov     dword ptr [rsp+140h+pbmi+14h], ecx
0x180004ca5  mov     r15d, ecx
0x180004ca8  mov     dword ptr [rsp+140h+pbmi+24h], ecx
0x180004cac  mov     r14d, ecx
0x180004caf  mov     [rsp+140h+ppvBits], rcx
0x180004cb4  mov     edi, ecx
0x180004cb6  mov     qword ptr [rsp+140h+rc.left], rcx
0x180004cbb  mov     r13, r9
0x180004cbe  mov     [rbp+40h+rc.right], edx
0x180004cc1  lea     rcx, [rbp+40h+lf]; void *
0x180004cc5  xor     edx, edx; Val
0x180004cc7  mov     dword ptr [rsp+140h+pbmi], 28h ; '('
0x180004ccf  mov     qword ptr [rsp+140h+pbmi+0Ch], 10001h
0x180004cd8  mov     dword ptr [rsp+140h+pbmi+18h], eax
0x180004cdc  mov     qword ptr [rsp+140h+pbmi+1Ch], rax
0x180004ce1  mov     qword ptr [rsp+140h+pbmi+28h], 0FFFFFFh
0x180004cea  call    memset_0
0x180004cef  mov     ecx, [rsp+140h+var_110]
0x180004cf3  lea     eax, [rdi+2]
0x180004cf6  sub     eax, ecx
0x180004cf8  mov     [rbp+40h+lf.lfWeight], 190h
0x180004cff  mov     [rbp+40h+lf.lfHeight], eax
0x180004d02  mov     dword ptr [rbp+40h+lf.lfCharSet], 1
0x180004d09  mov     [rbp+40h+lf.lfPitchAndFamily], 1
0x180004d0d  cmp     [rsp+140h+lpchText], rbx
0x180004d12  jz      loc_180004DCC
0x180004d18  cmp     [rsp+140h+var_10C], ebx
0x180004d1c  jle     loc_180004DCC
0x180004d22  test    ecx, ecx
0x180004d24  jle     loc_180004DCC
0x180004d2a  xor     ecx, ecx; hdc
0x180004d2c  call    cs:__imp_CreateCompatibleDC
0x180004d32  mov     rbx, rax
0x180004d35  test    rax, rax
0x180004d38  jz      loc_180004DCC
0x180004d3e  mov     [rsp+140h+offset], esi; offset
0x180004d42  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x180004d47  xor     r8d, r8d; usage
0x180004d4a  mov     [rsp+140h+hSection], rdi; hSection
0x180004d4f  lea     rdx, [rsp+140h+pbmi]; pbmi
0x180004d54  xor     ecx, ecx; hdc
0x180004d56  call    cs:__imp_CreateDIBSection
0x180004d5c  mov     rsi, rax
0x180004d5f  test    rax, rax
0x180004d62  jz      short loc_180004DCC
0x180004d64  mov     rdx, rax; h
0x180004d67  mov     rcx, rbx; hdc
0x180004d6a  call    cs:__imp_SelectObject
0x180004d70  mov     r15, rax
0x180004d73  test    rax, rax
0x180004d76  jz      short loc_180004DCC
0x180004d78  lea     rcx, [rbp+40h+lf]; lplf
0x180004d7c  call    cs:__imp_CreateFontIndirectW
0x180004d82  mov     r14, rax
0x180004d85  test    rax, rax
0x180004d88  jz      short loc_180004DCC
0x180004d8a  mov     rdx, rax; h
0x180004d8d  mov     rcx, rbx; hdc
0x180004d90  call    cs:__imp_SelectObject
0x180004d96  mov     rdi, rax
0x180004d99  test    rax, rax
0x180004d9c  jz      short loc_180004DCC
0x180004d9e  mov     rdx, [rsp+140h+lpchText]; lpchText
0x180004da3  lea     r9, [rsp+140h+rc]; lprc
0x180004da8  or      r8d, 0FFFFFFFFh; cchText
0x180004dac  mov     dword ptr [rsp+140h+hSection], 25h ; '%'; format
0x180004db4  mov     rcx, rbx; hdc
0x180004db7  call    cs:__imp_DrawTextW
0x180004dbd  mov     rcx, [rsp+140h+ppvBits]
0x180004dc2  mov     [r13+0], rsi
0x180004dc6  mov     [r12], rcx
0x180004dca  jmp     short loc_180004DE1
0x180004dcc  mov     qword ptr [r13+0], 0
0x180004dd4  mov     qword ptr [r12], 0
0x180004ddc  test    rdi, rdi
0x180004ddf  jz      short loc_180004DED
0x180004de1  mov     rdx, rdi; h
0x180004de4  mov     rcx, rbx; hdc
0x180004de7  call    cs:__imp_SelectObject
0x180004ded  test    r14, r14
0x180004df0  jz      short loc_180004DFB
0x180004df2  mov     rcx, r14; ho
0x180004df5  call    cs:__imp_DeleteObject
0x180004dfb  test    r15, r15
0x180004dfe  jz      short loc_180004E0C
0x180004e00  mov     rdx, r15; h
0x180004e03  mov     rcx, rbx; hdc
0x180004e06  call    cs:__imp_SelectObject
0x180004e0c  cmp     [rsp+140h+ppvBits], 0
0x180004e12  jnz     short loc_180004E22
0x180004e14  test    rsi, rsi
0x180004e17  jz      short loc_180004E22
0x180004e19  mov     rcx, rsi; ho
0x180004e1c  call    cs:__imp_DeleteObject
0x180004e22  test    rbx, rbx
0x180004e25  jz      short loc_180004E30
0x180004e27  mov     rcx, rbx; hdc
0x180004e2a  call    cs:__imp_DeleteDC
0x180004e30  xor     eax, eax
0x180004e32  cmp     [r12], rax
0x180004e36  setnz   al
0x180004e39  mov     rcx, [rbp+40h+var_50]
0x180004e3d  xor     rcx, rsp; StackCookie
0x180004e40  call    __security_check_cookie
0x180004e45  add     rsp, 108h
0x180004e4c  pop     r15
0x180004e4e  pop     r14
0x180004e50  pop     r13
0x180004e52  pop     r12
0x180004e54  pop     rdi
0x180004e55  pop     rsi
0x180004e56  pop     rbx
0x180004e57  pop     rbp
0x180004e58  retn
```
