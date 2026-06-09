# UtConvertBitmapToDib(HBITMAP__ *,HPALETTE__ *)

- ea: `0x180040e18`
- end: `0x180041171`
- name: `?UtConvertBitmapToDib@@YAPEAXPEAUHBITMAP__@@PEAUHPALETTE__@@@Z`
- size: `857`
- prototype: `void *__fastcall(HBITMAP__ *hBitmap, HPALETTE__ *hpal)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180033878`
- `0x180090c04`
- `0x1800a16c8`

## callees

- `0x180040e18`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180040ea4`
- `KERNELBASE!GlobalAlloc` at `0x180040f8a`
- `KERNELBASE!GlobalAlloc` at `0x180040ea4`
- `KERNELBASE!GlobalAlloc` at `0x180040f8a`
- `KERNELBASE!GlobalFree` at `0x180040ef2`
- `KERNELBASE!GlobalFree` at `0x18004113c`
- `KERNELBASE!GlobalFree` at `0x18004114a`
- `KERNELBASE!GlobalFree` at `0x180040ef2`
- `KERNELBASE!GlobalFree` at `0x18004113c`
- `KERNELBASE!GlobalFree` at `0x18004114a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180041084`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180041084`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180040ee9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180040fe6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180041055`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180041067`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800410f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180040ee9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180040fe6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180041055`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180041067`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800410f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180040eb9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180040f9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180041097`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180040eb9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180040f9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180041097`
- `GDI32!GetDIBits` at `0x180041012`
- `GDI32!GetDIBits` at `0x1800410e6`
- `GDI32!GetDIBits` at `0x180041012`
- `GDI32!GetDIBits` at `0x1800410e6`
- `GDI32!RealizePalette` at `0x1800410ba`
- `GDI32!RealizePalette` at `0x1800410ba`
- `GDI32!CreatePalette` at `0x180040edd`
- `GDI32!CreatePalette` at `0x180040edd`
- `GDI32!DeleteObject` at `0x180041129`
- `GDI32!DeleteObject` at `0x180041129`
- `GDI32!GetObjectW` at `0x180040f2b`
- `GDI32!GetObjectW` at `0x180040f2b`
- `GDI32!GetDeviceCaps` at `0x180040e80`
- `GDI32!GetDeviceCaps` at `0x180040e80`
- `GDI32!GetStockObject` at `0x180040f10`
- `GDI32!GetStockObject` at `0x180040f10`
- `GDI32!SelectPalette` at `0x1800410ae`
- `GDI32!SelectPalette` at `0x180041109`
- `GDI32!SelectPalette` at `0x1800410ae`
- `GDI32!SelectPalette` at `0x180041109`
- `USER32!ReleaseDC` at `0x180040e8d`
- `USER32!ReleaseDC` at `0x180041116`
- `USER32!ReleaseDC` at `0x180040e8d`
- `USER32!ReleaseDC` at `0x180041116`
- `USER32!GetDC` at `0x180040e68`
- `USER32!GetDC` at `0x180040fd5`
- `USER32!GetDC` at `0x180040e68`
- `USER32!GetDC` at `0x180040fd5`

## pseudocode

```c
void *__fastcall UtConvertBitmapToDib(HBITMAP hBitmap, HPALETTE hpal)
{
  HPALETTE StockObject; // rbp
  HDC DC; // rax
  HDC v5; // rdi
  __int16 DeviceCaps; // bx
  HGLOBAL v7; // rax
  void *v8; // rbx
  LOGPALETTE *v9; // rax
  __int64 v10; // rdx
  void *v11; // rbx
  void *v12; // rdi
  int v13; // r13d
  unsigned int v14; // esi
  unsigned __int64 v15; // r15
  int v16; // r12d
  HGLOBAL v17; // rax
  tagBITMAPINFO *v18; // rax
  tagBITMAPINFO *lpbmi; // r14
  HDC v20; // rax
  HDC v21; // r12
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rsi
  SIZE_T v24; // rdx
  HGLOBAL v25; // rax
  tagBITMAPINFO *v26; // rsi
  HPALETTE v27; // rbx
  tagBITMAP bm; // [rsp+40h] [rbp-58h] BYREF
  int v31; // [rsp+B0h] [rbp+18h]

  StockObject = hpal;
  memset(&bm, 0, sizeof(bm));
  if ( !hBitmap )
    return 0;
  v31 = 0;
  if ( !hpal )
  {
    DC = GetDC(0);
    v5 = DC;
    if ( DC )
    {
      DeviceCaps = GetDeviceCaps(DC, (_DWORD)StockObject + 38);
      ReleaseDC(0, v5);
      if ( (DeviceCaps & 0x100) == 0 )
      {
        StockObject = (HPALETTE)GetStockObject(15);
        goto LABEL_11;
      }
      v7 = GlobalAlloc((int)StockObject + 66, 0x408u);
      v8 = v7;
      if ( v7 )
      {
        v9 = (LOGPALETTE *)GlobalLock(v7);
        v10 = 0;
        *(_DWORD *)&v9->palVersion = 16777984;
        do
        {
          *(_WORD *)&v9->palPalEntry[v10].peRed = v10;
          *(_WORD *)&v9->palPalEntry[v10].peBlue = 512;
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (int)v10 < 256 );
        StockObject = CreatePalette(v9);
        GlobalUnlock(v8);
        GlobalFree(v8);
        if ( StockObject )
        {
          v31 = 1;
          goto LABEL_11;
        }
      }
    }
    return 0;
  }
LABEL_11:
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !GetObjectW(hBitmap, 32, &bm) )
    goto LABEL_36;
  v14 = bm.bmPlanes * bm.bmBitsPixel;
  if ( ((bm.bmBitsPixel - 16) & 0xFFEF) != 0 )
  {
    v15 = bm.bmBitsPixel == 24 ? 40LL : 4 * (1LL << v14) + 40;
    v16 = 0;
  }
  else
  {
    v15 = 52;
    v16 = 3;
  }
  v17 = GlobalAlloc(0x42u, (unsigned int)v15);
  v11 = v17;
  if ( !v17 )
    goto LABEL_36;
  v18 = (tagBITMAPINFO *)GlobalLock(v17);
  lpbmi = v18;
  if ( !v18 )
    goto LABEL_36;
  v18->bmiHeader.biSize = 40;
  v18->bmiHeader.biWidth = bm.bmWidth;
  v18->bmiHeader.biHeight = bm.bmHeight;
  v18->bmiHeader.biPlanes = 1;
  v18->bmiHeader.biBitCount = v14;
  v18->bmiHeader.biCompression = v16;
  v20 = GetDC(0);
  v21 = v20;
  if ( v20 )
  {
    GetDIBits(v20, hBitmap, 0, bm.bmHeight, 0, lpbmi, 0);
    if ( lpbmi->bmiHeader.biSizeImage )
    {
      LODWORD(v23) = lpbmi->bmiHeader.biSizeImage;
    }
    else
    {
      v22 = (unsigned int)bm.bmWidth * (unsigned __int64)v14;
      if ( v22 > 0xFFFFFFFF
        || (int)v22 + 31 < (unsigned int)v22
        || (v23 = (unsigned int)bm.bmHeight * ((unsigned __int64)(unsigned int)(v22 + 31) >> 3), v23 > 0xFFFFFFFF) )
      {
        GlobalUnlock(v11);
LABEL_35:
        ReleaseDC(0, v21);
        goto LABEL_36;
      }
      lpbmi->bmiHeader.biSizeImage = v23;
    }
    GlobalUnlock(v11);
    v24 = v15 + (unsigned int)v23;
    if ( v24 >= v15 )
    {
      v25 = GlobalReAlloc(v11, v24, 2u);
      v12 = v25;
      if ( v25 )
      {
        v11 = 0;
        v26 = (tagBITMAPINFO *)GlobalLock(v25);
        if ( v26 )
        {
          v27 = SelectPalette(v21, StockObject, 0);
          RealizePalette(v21);
          LOBYTE(v13) = GetDIBits(v21, hBitmap, 0, LOWORD(v26->bmiHeader.biHeight), (char *)v26 + v15, v26, 0) != 0;
          GlobalUnlock(v12);
          if ( v27 )
            SelectPalette(v21, v27, 0);
          v11 = 0;
        }
      }
    }
    goto LABEL_35;
  }
  GlobalUnlock(v11);
LABEL_36:
  if ( v31 )
    DeleteObject(StockObject);
  if ( !v13 )
  {
    if ( v11 )
      GlobalFree(v11);
    if ( v12 )
    {
      GlobalFree(v12);
      return 0;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180040e18  mov     rax, rsp
0x180040e1b  mov     [rax+10h], rbx
0x180040e1f  mov     [rax+8], hBitmap
0x180040e23  push    rbp
0x180040e24  push    rsi
0x180040e25  push    rdi
0x180040e26  push    r12
0x180040e28  push    r13
0x180040e2a  push    r14
0x180040e2c  push    r15
0x180040e2e  sub     rsp, 60h
0x180040e32  xorps   xmm0, xmm0
0x180040e35  mov     rbp, hpal
0x180040e38  mov     rsi, hBitmap
0x180040e3b  movups  xmmword ptr [rax-58h], xmm0
0x180040e3f  movups  xmmword ptr [rax-48h], xmm0
0x180040e43  test    hBitmap, hBitmap
0x180040e46  jz      loc_180041157
0x180040e4c  mov     [rsp+98h+arg_10], 0
0x180040e57  mov     r14d, 1
0x180040e5d  test    hpal, hpal
0x180040e60  jnz     loc_180040F19
0x180040e66  xor     ecx, ecx; hWnd
0x180040e68  call    cs:__imp_GetDC
0x180040e6e  mov     rdi, rax
0x180040e71  test    rax, rax
0x180040e74  jz      loc_180041157
0x180040e7a  lea     edx, [rbp+26h]; index
0x180040e7d  mov     hBitmap, rax; hdc
0x180040e80  call    cs:__imp_GetDeviceCaps
0x180040e86  mov     hpal, rdi; hDC
0x180040e89  xor     ecx, ecx; hWnd
0x180040e8b  mov     ebx, eax
0x180040e8d  call    cs:__imp_ReleaseDC
0x180040e93  mov     edi, 100h
0x180040e98  test    edi, ebx
0x180040e9a  jz      short loc_180040F0B
0x180040e9c  mov     edx, 408h; dwBytes
0x180040ea1  lea     ecx, [rbp+42h]; uFlags
0x180040ea4  call    cs:__imp_GlobalAlloc
0x180040eaa  mov     rbx, rax
0x180040ead  test    rax, rax
0x180040eb0  jz      loc_180041157
0x180040eb6  mov     hBitmap, rax; hMem
0x180040eb9  call    cs:__imp_GlobalLock
0x180040ebf  mov     hBitmap, rax; plpal
0x180040ec2  xor     edx, edx
0x180040ec4  mov     dword ptr [rax], 1000300h
0x180040eca  mov     [rax+hpal*4+4], dx
0x180040ecf  mov     word ptr [rax+hpal*4+6], 200h
0x180040ed6  add     edx, r14d
0x180040ed9  cmp     edx, edi
0x180040edb  jl      short loc_180040ECA
0x180040edd  call    cs:__imp_CreatePalette
0x180040ee3  mov     hBitmap, rbx; hMem
0x180040ee6  mov     rbp, rax
0x180040ee9  call    cs:__imp_GlobalUnlock
0x180040eef  mov     hBitmap, rbx; hMem
0x180040ef2  call    cs:__imp_GlobalFree
0x180040ef8  test    rbp, rbp
0x180040efb  jz      loc_180041157
0x180040f01  mov     [rsp+98h+arg_10], r14d
0x180040f09  jmp     short loc_180040F19
0x180040f0b  mov     ecx, 0Fh; i
0x180040f10  call    cs:__imp_GetStockObject
0x180040f16  mov     rbp, rax
0x180040f19  xor     ebx, ebx
0x180040f1b  lea     r8, [rsp+98h+bm]; pv
0x180040f20  mov     hBitmap, rsi; h
0x180040f23  xor     edi, edi
0x180040f25  xor     r13d, r13d
0x180040f28  lea     edx, [rbx+20h]; c
0x180040f2b  call    cs:__imp_GetObjectW
0x180040f31  test    eax, eax
0x180040f33  jz      loc_18004111C
0x180040f39  movzx   ecx, [rsp+98h+bm.bmBitsPixel]
0x180040f3e  mov     edx, 0FFEFh
0x180040f43  movzx   eax, [rsp+98h+bm.bmPlanes]
0x180040f48  mov     esi, ecx
0x180040f4a  imul    esi, eax
0x180040f4d  lea     eax, [hBitmap-10h]
0x180040f50  test    dx, ax
0x180040f53  jz      short loc_180040F78
0x180040f55  lea     eax, [rbx+18h]
0x180040f58  cmp     ax, cx
0x180040f5b  jnz     short loc_180040F66
0x180040f5d  lea     r15d, [rbx+28h]
0x180040f61  xor     r12d, r12d
0x180040f64  jmp     short loc_180040F82
0x180040f66  mov     ecx, esi
0x180040f68  mov     rax, r14
0x180040f6b  shl     rax, cl
0x180040f6e  lea     r15, ds:28h[rax*4]
0x180040f76  jmp     short loc_180040F61
0x180040f78  mov     r15d, 34h ; '4'
0x180040f7e  lea     r12d, [r15-31h]
0x180040f82  mov     edx, r15d; dwBytes
0x180040f85  mov     ecx, 42h ; 'B'; uFlags
0x180040f8a  call    cs:__imp_GlobalAlloc
0x180040f90  mov     rbx, rax
0x180040f93  test    rax, rax
0x180040f96  jz      loc_18004111C
0x180040f9c  mov     hBitmap, rax; hMem
0x180040f9f  call    cs:__imp_GlobalLock
0x180040fa5  mov     r14, rax
0x180040fa8  test    rax, rax
0x180040fab  jz      loc_18004111C
0x180040fb1  mov     dword ptr [rax], 28h ; '('
0x180040fb7  mov     ecx, [rsp+98h+bm.bmWidth]
0x180040fbb  mov     [rax+4], ecx
0x180040fbe  mov     ecx, [rsp+98h+bm.bmHeight]
0x180040fc2  mov     [rax+8], ecx
0x180040fc5  xor     ecx, ecx; hWnd
0x180040fc7  mov     word ptr [rax+0Ch], 1
0x180040fcd  mov     [rax+0Eh], si
0x180040fd1  mov     [rax+10h], r12d
0x180040fd5  call    cs:__imp_GetDC
0x180040fdb  mov     r12, rax
0x180040fde  test    rax, rax
0x180040fe1  jnz     short loc_180040FF1
0x180040fe3  mov     hBitmap, rbx; hMem
0x180040fe6  call    cs:__imp_GlobalUnlock
0x180040fec  jmp     loc_18004111C
0x180040ff1  mov     r9d, [rsp+98h+bm.bmHeight]; cLines
0x180040ff6  xor     r8d, r8d; start
0x180040ff9  mov     hpal, [rsp+98h+hbm]; hbm
0x180041001  mov     hBitmap, r12; hdc
0x180041004  mov     [rsp+98h+usage], edi; usage
0x180041008  mov     [rsp+98h+lpbmi], r14; lpbmi
0x18004100d  mov     [rsp+98h+lpvBits], rdi; lpvBits
0x180041012  call    cs:__imp_GetDIBits
0x180041018  cmp     [r14+14h], edi
0x18004101c  jnz     short loc_180041060
0x18004101e  mov     eax, [rsp+98h+bm.bmWidth]
0x180041022  mov     edx, 0FFFFFFFFh
0x180041027  mov     ecx, esi
0x180041029  imul    hBitmap, rax
0x18004102d  cmp     hBitmap, hpal
0x180041030  ja      short loc_180041052
0x180041032  lea     eax, [hBitmap+1Fh]
0x180041035  cmp     eax, ecx
0x180041037  jb      short loc_180041052
0x180041039  mov     esi, eax
0x18004103b  mov     eax, [rsp+98h+bm.bmHeight]
0x18004103f  shr     rsi, 3
0x180041043  imul    rsi, rax
0x180041047  cmp     rsi, hpal
0x18004104a  ja      short loc_180041052
0x18004104c  mov     [r14+14h], esi
0x180041050  jmp     short loc_180041064
0x180041052  mov     hBitmap, rbx; hMem
0x180041055  call    cs:__imp_GlobalUnlock
0x18004105b  jmp     loc_180041111
0x180041060  mov     esi, [r14+14h]
0x180041064  mov     hBitmap, rbx; hMem
0x180041067  call    cs:__imp_GlobalUnlock
0x18004106d  mov     edx, esi
0x18004106f  add     hpal, r15; dwBytes
0x180041072  cmp     hpal, r15
0x180041075  jb      loc_180041111
0x18004107b  mov     r8d, 2; uFlags
0x180041081  mov     hBitmap, rbx; hMem
0x180041084  call    cs:__imp_GlobalReAlloc
0x18004108a  mov     rdi, rax
0x18004108d  test    rax, rax
0x180041090  jz      short loc_180041111
0x180041092  mov     hBitmap, rax; hMem
0x180041095  xor     ebx, ebx
0x180041097  call    cs:__imp_GlobalLock
0x18004109d  mov     rsi, rax
0x1800410a0  test    rax, rax
0x1800410a3  jz      short loc_180041111
0x1800410a5  xor     r8d, r8d; bForceBkgd
0x1800410a8  mov     hpal, rbp; hPal
0x1800410ab  mov     hBitmap, r12; hdc
0x1800410ae  call    cs:__imp_SelectPalette
0x1800410b4  mov     hBitmap, r12; hdc
0x1800410b7  mov     rbx, rax
0x1800410ba  call    cs:__imp_RealizePalette
0x1800410c0  movzx   r9d, word ptr [rsi+8]; cLines
0x1800410c5  lea     hBitmap, [rsi+r15]
0x1800410c9  mov     hpal, [rsp+98h+hbm]; hbm
0x1800410d1  xor     r8d, r8d; start
0x1800410d4  mov     [rsp+98h+usage], r13d; usage
0x1800410d9  mov     [rsp+98h+lpbmi], rsi; lpbmi
0x1800410de  mov     [rsp+98h+lpvBits], hBitmap; lpvBits
0x1800410e3  mov     hBitmap, r12; hdc
0x1800410e6  call    cs:__imp_GetDIBits
0x1800410ec  test    eax, eax
0x1800410ee  mov     hBitmap, rdi; hMem
0x1800410f1  setnz   r13b
0x1800410f5  call    cs:__imp_GlobalUnlock
0x1800410fb  test    rbx, rbx
0x1800410fe  jz      short loc_18004110F
0x180041100  xor     r8d, r8d; bForceBkgd
0x180041103  mov     hpal, rbx; hPal
0x180041106  mov     hBitmap, r12; hdc
0x180041109  call    cs:__imp_SelectPalette
0x18004110f  xor     ebx, ebx
0x180041111  mov     hpal, r12; hDC
0x180041114  xor     ecx, ecx; hWnd
0x180041116  call    cs:__imp_ReleaseDC
0x18004111c  cmp     [rsp+98h+arg_10], 0
0x180041124  jz      short loc_18004112F
0x180041126  mov     hBitmap, rbp; ho
0x180041129  call    cs:__imp_DeleteObject
0x18004112f  test    r13d, r13d
0x180041132  jnz     short loc_180041152
0x180041134  test    rbx, rbx
0x180041137  jz      short loc_180041142
0x180041139  mov     hBitmap, rbx; hMem
0x18004113c  call    cs:__imp_GlobalFree
0x180041142  test    rdi, rdi
0x180041145  jz      short loc_180041152
0x180041147  mov     hBitmap, rdi; hMem
0x18004114a  call    cs:__imp_GlobalFree
0x180041150  xor     edi, edi
0x180041152  mov     rax, rdi
0x180041155  jmp     short loc_180041159
0x180041157  xor     eax, eax
0x180041159  mov     rbx, [rsp+98h+arg_8]
0x180041161  add     rsp, 60h
0x180041165  pop     r15
0x180041167  pop     r14
0x180041169  pop     r13
0x18004116b  pop     r12
0x18004116d  pop     rdi
0x18004116e  pop     rsi
0x18004116f  pop     rbp
0x180041170  retn
```
