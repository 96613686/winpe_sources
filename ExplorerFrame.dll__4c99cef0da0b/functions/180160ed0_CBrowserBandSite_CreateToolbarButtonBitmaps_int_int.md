# CBrowserBandSite::_CreateToolbarButtonBitmaps(int,int)

- ea: `0x180160ed0`
- end: `0x18016107b`
- name: `?_CreateToolbarButtonBitmaps@CBrowserBandSite@@MEAAPEAUHBITMAP__@@HH@Z`
- size: `427`
- prototype: `HBITMAP(CBrowserBandSite *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180160ed0`
- `0x180207e74`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180160f6b`
- `KERNEL32!MulDiv` at `0x180160f7e`
- `KERNEL32!MulDiv` at `0x180160f6b`
- `KERNEL32!MulDiv` at `0x180160f7e`
- `USER32!GetDC` at `0x180160f25`
- `USER32!GetDC` at `0x180160f25`
- `USER32!ReleaseDC` at `0x18016105a`
- `USER32!ReleaseDC` at `0x18016105a`
- `GDI32!DeleteDC` at `0x180161027`
- `GDI32!DeleteDC` at `0x18016104f`
- `GDI32!DeleteDC` at `0x180161027`
- `GDI32!DeleteDC` at `0x18016104f`
- `GDI32!CreateCompatibleBitmap` at `0x180160faf`
- `GDI32!CreateCompatibleBitmap` at `0x180160faf`
- `GDI32!DeleteObject` at `0x180161046`
- `GDI32!DeleteObject` at `0x180161046`
- `GDI32!SelectObject` at `0x180160f52`
- `GDI32!SelectObject` at `0x180160fc3`
- `GDI32!SelectObject` at `0x18016101e`
- `GDI32!SelectObject` at `0x180161038`
- `GDI32!SelectObject` at `0x180160f52`
- `GDI32!SelectObject` at `0x180160fc3`
- `GDI32!SelectObject` at `0x18016101e`
- `GDI32!SelectObject` at `0x180161038`
- `GDI32!StretchBlt` at `0x18016100f`
- `GDI32!StretchBlt` at `0x18016100f`
- `GDI32!CreateCompatibleDC` at `0x180160f3a`
- `GDI32!CreateCompatibleDC` at `0x180160f90`
- `GDI32!CreateCompatibleDC` at `0x180160f3a`
- `GDI32!CreateCompatibleDC` at `0x180160f90`

## pseudocode

```c
HBITMAP __fastcall CBrowserBandSite::_CreateToolbarButtonBitmaps(CBrowserBandSite *this, int a2, int a3)
{
  HBITMAP MappedBitmap; // rbp
  HBITMAP v6; // r14
  HDC DC; // rax
  HDC v8; // rdi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  int v11; // r12d
  HDC v12; // r15
  int v13; // r13d
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v15; // r12
  HGDIOBJ v16; // rbx
  int hDest; // [rsp+A8h] [rbp+10h]
  HGDIOBJ h; // [rsp+B8h] [rbp+20h]

  MappedBitmap = CreateMappedBitmap(g_hinst, 545, 0, 0, 0);
  v6 = MappedBitmap;
  if ( a2 != 96 || a3 != 96 )
  {
    DC = GetDC(0);
    v8 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        h = SelectObject(CompatibleDC, MappedBitmap);
        v11 = MulDiv(13, a2, 96);
        hDest = MulDiv(11, a3, 96);
        v12 = CreateCompatibleDC(v8);
        if ( v12 )
        {
          v13 = 3 * v11;
          CompatibleBitmap = CreateCompatibleBitmap(v8, 3 * v11, hDest);
          v15 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v16 = SelectObject(v12, CompatibleBitmap);
            StretchBlt(v12, 0, 0, v13, hDest, hdcSrc, 0, 0, 39, 11, 0xCC0020u);
            v6 = v15;
            SelectObject(v12, v16);
          }
          DeleteDC(v12);
        }
        SelectObject(hdcSrc, h);
        if ( v6 != MappedBitmap )
          DeleteObject(MappedBitmap);
        DeleteDC(hdcSrc);
      }
      ReleaseDC(0, v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180160ed0  mov     [rsp+arg_0], rbx
0x180160ed5  push    rbp
0x180160ed6  push    rsi
0x180160ed7  push    rdi
0x180160ed8  push    r12
0x180160eda  push    r13
0x180160edc  push    r14
0x180160ede  push    r15
0x180160ee0  sub     rsp, 60h
0x180160ee4  mov     rcx, cs:g_hinst; hInstance
0x180160eeb  mov     ebx, r8d
0x180160eee  mov     r15d, edx
0x180160ef1  mov     [rsp+98h+iNumMaps], 0; iNumMaps
0x180160ef9  xor     r8d, r8d; wFlags
0x180160efc  mov     edx, 221h; idBitmap
0x180160f01  xor     r9d, r9d; lpColorMap
0x180160f04  call    CreateMappedBitmap
0x180160f09  mov     r13d, 60h ; '`'
0x180160f0f  mov     rbp, rax
0x180160f12  mov     r14, rax
0x180160f15  cmp     r15d, r13d
0x180160f18  jnz     short loc_180160F23
0x180160f1a  cmp     ebx, r13d
0x180160f1d  jz      loc_180161060
0x180160f23  xor     ecx, ecx; hWnd
0x180160f25  call    cs:__imp_GetDC
0x180160f2b  mov     rdi, rax
0x180160f2e  test    rax, rax
0x180160f31  jz      loc_180161060
0x180160f37  mov     rcx, rax; hdc
0x180160f3a  call    cs:__imp_CreateCompatibleDC
0x180160f40  mov     rsi, rax
0x180160f43  test    rax, rax
0x180160f46  jz      loc_180161055
0x180160f4c  mov     rdx, rbp; h
0x180160f4f  mov     rcx, rax; hdc
0x180160f52  call    cs:__imp_SelectObject
0x180160f58  mov     r8d, r13d; nDenominator
0x180160f5b  mov     edx, r15d; nNumerator
0x180160f5e  mov     ecx, 0Dh; nNumber
0x180160f63  mov     [rsp+98h+h], rax
0x180160f6b  call    cs:__imp_MulDiv
0x180160f71  mov     r8d, r13d; nDenominator
0x180160f74  mov     edx, ebx; nNumerator
0x180160f76  mov     ecx, 0Bh; nNumber
0x180160f7b  mov     r12d, eax
0x180160f7e  call    cs:__imp_MulDiv
0x180160f84  mov     rcx, rdi; hdc
0x180160f87  mov     [rsp+98h+hDest], eax
0x180160f8e  mov     ebx, eax
0x180160f90  call    cs:__imp_CreateCompatibleDC
0x180160f96  mov     r15, rax
0x180160f99  test    rax, rax
0x180160f9c  jz      loc_18016102D
0x180160fa2  lea     r13d, [r12+r12*2]
0x180160fa6  mov     r8d, ebx; cy
0x180160fa9  mov     edx, r13d; cx
0x180160fac  mov     rcx, rdi; hdc
0x180160faf  call    cs:__imp_CreateCompatibleBitmap
0x180160fb5  mov     r12, rax
0x180160fb8  test    rax, rax
0x180160fbb  jz      short loc_180161024
0x180160fbd  mov     rdx, rax; h
0x180160fc0  mov     rcx, r15; hdc
0x180160fc3  call    cs:__imp_SelectObject
0x180160fc9  mov     [rsp+98h+rop], 0CC0020h; rop
0x180160fd1  mov     r9d, r13d; wDest
0x180160fd4  mov     [rsp+98h+hSrc], 0Bh; hSrc
0x180160fdc  mov     rbx, rax
0x180160fdf  mov     eax, [rsp+98h+hDest]
0x180160fe6  xor     r8d, r8d; yDest
0x180160fe9  mov     [rsp+98h+wSrc], 27h ; '''; wSrc
0x180160ff1  xor     edx, edx; xDest
0x180160ff3  mov     [rsp+98h+ySrc], 0; ySrc
0x180160ffb  mov     rcx, r15; hdcDest
0x180160ffe  mov     [rsp+98h+xSrc], 0; xSrc
0x180161006  mov     [rsp+98h+hdcSrc], rsi; hdcSrc
0x18016100b  mov     [rsp+98h+iNumMaps], eax; hDest
0x18016100f  call    cs:__imp_StretchBlt
0x180161015  mov     rdx, rbx; h
0x180161018  mov     rcx, r15; hdc
0x18016101b  mov     r14, r12
0x18016101e  call    cs:__imp_SelectObject
0x180161024  mov     rcx, r15; hdc
0x180161027  call    cs:__imp_DeleteDC
0x18016102d  mov     rdx, [rsp+98h+h]; h
0x180161035  mov     rcx, rsi; hdc
0x180161038  call    cs:__imp_SelectObject
0x18016103e  cmp     r14, rbp
0x180161041  jz      short loc_18016104C
0x180161043  mov     rcx, rbp; ho
0x180161046  call    cs:__imp_DeleteObject
0x18016104c  mov     rcx, rsi; hdc
0x18016104f  call    cs:__imp_DeleteDC
0x180161055  mov     rdx, rdi; hDC
0x180161058  xor     ecx, ecx; hWnd
0x18016105a  call    cs:__imp_ReleaseDC
0x180161060  mov     rbx, [rsp+98h+arg_0]
0x180161068  mov     rax, r14
0x18016106b  add     rsp, 60h
0x18016106f  pop     r15
0x180161071  pop     r14
0x180161073  pop     r13
0x180161075  pop     r12
0x180161077  pop     rdi
0x180161078  pop     rsi
0x180161079  pop     rbp
0x18016107a  retn
```
