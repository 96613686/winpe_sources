# _FHbmpsOfBits(tagBITMAPINFO *,HBITMAP__ * *,HBITMAP__ * *)

- ea: `0x1800b06c0`
- end: `0x1800b0b59`
- name: `?_FHbmpsOfBits@@YAHPEAUtagBITMAPINFO@@PEAPEAUHBITMAP__@@1@Z`
- size: `1177`
- prototype: `__int64 __fastcall(struct tagBITMAPINFO *, HBITMAP *, HBITMAP *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b0cec`
- `0x1800b0d68`
- `0x1800b0fa8`

## callees

- `0x180029b14`
- `0x1800b0694`
- `0x1800b06c0`
- `0x180379380`

## import_xrefs

- `USER32!GetDC` at `0x1800b0740`
- `USER32!GetDC` at `0x1800b0740`
- `USER32!ReleaseDC` at `0x1800b0aad`
- `USER32!ReleaseDC` at `0x1800b0aad`
- `GDI32!CreateCompatibleDC` at `0x1800b077a`
- `GDI32!CreateCompatibleDC` at `0x1800b0790`
- `GDI32!CreateCompatibleDC` at `0x1800b077a`
- `GDI32!CreateCompatibleDC` at `0x1800b0790`
- `GDI32!BitBlt` at `0x1800b0883`
- `GDI32!BitBlt` at `0x1800b08e5`
- `GDI32!BitBlt` at `0x1800b0984`
- `GDI32!BitBlt` at `0x1800b09b8`
- `GDI32!BitBlt` at `0x1800b0a53`
- `GDI32!BitBlt` at `0x1800b0a87`
- `GDI32!BitBlt` at `0x1800b0883`
- `GDI32!BitBlt` at `0x1800b08e5`
- `GDI32!BitBlt` at `0x1800b0984`
- `GDI32!BitBlt` at `0x1800b09b8`
- `GDI32!BitBlt` at `0x1800b0a53`
- `GDI32!BitBlt` at `0x1800b0a87`
- `GDI32!CreateDIBitmap` at `0x1800b076e`
- `GDI32!CreateDIBitmap` at `0x1800b076e`
- `GDI32!GetPixel` at `0x1800b07ed`
- `GDI32!GetPixel` at `0x1800b07ed`
- `GDI32!DeleteDC` at `0x1800b0acc`
- `GDI32!DeleteDC` at `0x1800b0aef`
- `GDI32!DeleteDC` at `0x1800b0acc`
- `GDI32!DeleteDC` at `0x1800b0aef`
- `GDI32!GetObjectA` at `0x1800b07b7`
- `GDI32!GetObjectA` at `0x1800b0914`
- `GDI32!GetObjectA` at `0x1800b07b7`
- `GDI32!GetObjectA` at `0x1800b0914`
- `GDI32!SelectObject` at `0x1800b07cb`
- `GDI32!SelectObject` at `0x1800b0831`
- `GDI32!SelectObject` at `0x1800b094c`
- `GDI32!SelectObject` at `0x1800b0a10`
- `GDI32!SelectObject` at `0x1800b0ac3`
- `GDI32!SelectObject` at `0x1800b0ae6`
- `GDI32!SelectObject` at `0x1800b0b08`
- `GDI32!SelectObject` at `0x1800b07cb`
- `GDI32!SelectObject` at `0x1800b0831`
- `GDI32!SelectObject` at `0x1800b094c`
- `GDI32!SelectObject` at `0x1800b0a10`
- `GDI32!SelectObject` at `0x1800b0ac3`
- `GDI32!SelectObject` at `0x1800b0ae6`
- `GDI32!SelectObject` at `0x1800b0b08`
- `GDI32!SetTextColor` at `0x1800b08ac`
- `GDI32!SetTextColor` at `0x1800b08ac`
- `GDI32!SetBkColor` at `0x1800b084a`
- `GDI32!SetBkColor` at `0x1800b0893`
- `GDI32!SetBkColor` at `0x1800b084a`
- `GDI32!SetBkColor` at `0x1800b0893`
- `GDI32!DeleteObject` at `0x1800b09ca`
- `GDI32!DeleteObject` at `0x1800b09dc`
- `GDI32!DeleteObject` at `0x1800b0b16`
- `GDI32!DeleteObject` at `0x1800b0b24`
- `GDI32!DeleteObject` at `0x1800b0b32`
- `GDI32!DeleteObject` at `0x1800b09ca`
- `GDI32!DeleteObject` at `0x1800b09dc`
- `GDI32!DeleteObject` at `0x1800b0b16`
- `GDI32!DeleteObject` at `0x1800b0b24`
- `GDI32!DeleteObject` at `0x1800b0b32`
- `GDI32!CreateBitmap` at `0x1800b0815`
- `GDI32!CreateBitmap` at `0x1800b0815`

## pseudocode

```c
__int64 __fastcall _FHbmpsOfBits(struct tagBITMAPINFO *a1, HBITMAP *a2, HBITMAP *a3)
{
  unsigned int v3; // esi
  DWORD biClrUsed; // eax
  RGBQUAD *v7; // rdi
  unsigned int v8; // eax
  HBITMAP v9; // r15
  HDC v10; // r12
  HDC DC; // rax
  HDC v12; // r14
  HBITMAP DIBitmap; // r13
  HDC CompatibleDC; // r14
  HGDIOBJ v15; // rdi
  HBITMAP Bitmap; // rax
  HBITMAP v17; // rbx
  HBITMAP Bitmap3D; // rax
  HBITMAP v19; // rax
  _BYTE pv[4]; // [rsp+50h] [rbp-59h] BYREF
  int nWidth; // [rsp+54h] [rbp-55h]
  int nHeight; // [rsp+58h] [rbp-51h]
  HGDIOBJ h; // [rsp+70h] [rbp-39h]
  HGDIOBJ v24; // [rsp+78h] [rbp-31h]
  HDC hdc; // [rsp+80h] [rbp-29h]
  HBITMAP v26; // [rsp+88h] [rbp-21h]
  HGDIOBJ v27; // [rsp+90h] [rbp-19h]
  _BYTE v28[4]; // [rsp+98h] [rbp-11h] BYREF
  int v29; // [rsp+9Ch] [rbp-Dh]
  int v30; // [rsp+A0h] [rbp-9h]
  COLORREF color; // [rsp+110h] [rbp+67h]
  COLORREF colora; // [rsp+110h] [rbp+67h]
  int x; // [rsp+128h] [rbp+7Fh]

  v3 = 0;
  if ( a1->bmiHeader.biSize == 12 )
  {
    v8 = _NumColorOfBitCount(HIWORD(a1->bmiHeader.biHeight));
    v7 = (RGBQUAD *)((char *)&a1->bmiHeader.biPlanes + 2 * v8 + v8);
  }
  else
  {
    if ( a1->bmiHeader.biSize != 40 )
      return 0;
    biClrUsed = a1->bmiHeader.biClrUsed;
    if ( !biClrUsed )
      biClrUsed = _NumColorOfBitCount(a1->bmiHeader.biBitCount);
    v7 = &a1->bmiColors[biClrUsed];
  }
  v9 = 0;
  h = 0;
  v24 = 0;
  v10 = 0;
  DC = GetDC(0);
  v12 = DC;
  hdc = DC;
  if ( DC )
  {
    DIBitmap = CreateDIBitmap(DC, &a1->bmiHeader, 4u, v7, a1, 0);
    CompatibleDC = CreateCompatibleDC(v12);
    if ( CompatibleDC && (v10 = CreateCompatibleDC(hdc)) != 0 && DIBitmap && GetObjectA(DIBitmap, 32, pv) )
    {
      v15 = SelectObject(CompatibleDC, DIBitmap);
      v27 = v15;
      if ( v15 )
      {
        color = GetPixel(CompatibleDC, 0, nHeight - 1);
        if ( color != -1 )
        {
          Bitmap = CreateBitmap(nWidth, nHeight, 1u, 1u, 0);
          v17 = Bitmap;
          v26 = Bitmap;
          if ( Bitmap )
          {
            h = SelectObject(v10, Bitmap);
            if ( h )
            {
              if ( SetBkColor(CompatibleDC, color) != 0x80000000 )
              {
                BitBlt(v10, 0, 0, nWidth, nHeight, CompatibleDC, 0, 0, 0xCC0020u);
                if ( !color )
                {
LABEL_22:
                  Bitmap3D = LoadBitmap3D(Rby_hmodThun, 0x3DEu);
                  v9 = Bitmap3D;
                  if ( Bitmap3D && GetObjectA(Bitmap3D, 32, v28) )
                  {
                    x = (v29 - nWidth - 1) / 2;
                    colora = (v30 - nHeight - 1) / 2;
                    v24 = SelectObject(hdcDest, v9);
                    BitBlt(hdcDest, x, colora, nWidth, nHeight, v10, 0, 0, 0x8800C6u);
                    BitBlt(hdcDest, x, colora, nWidth, nHeight, CompatibleDC, 0, 0, 0xEE0086u);
                    if ( *a2 )
                      DeleteObject(*a2);
                    if ( *a3 )
                      DeleteObject(*a3);
                    *a2 = v9;
                    v19 = LoadBitmap3D(Rby_hmodThun, 0x3DFu);
                    v9 = v19;
                    if ( v19 && SelectObject(hdcDest, v19) )
                    {
                      BitBlt(hdcDest, x + 1, colora + 1, nWidth, nHeight, v10, 0, 0, 0x8800C6u);
                      BitBlt(hdcDest, x + 1, colora + 1, nWidth, nHeight, CompatibleDC, 0, 0, 0xEE0086u);
                      v17 = v26;
                      v15 = v27;
                      *a3 = v9;
                      v9 = 0;
                    }
                  }
                  goto LABEL_33;
                }
                if ( SetBkColor(CompatibleDC, 0) != 0x80000000 && SetTextColor(CompatibleDC, 0xFFFFFFu) != 0x80000000 )
                {
                  BitBlt(CompatibleDC, 0, 0, nWidth, nHeight, v10, 0, 0, 0x8800C6u);
                  goto LABEL_22;
                }
              }
            }
          }
LABEL_33:
          ReleaseDC(0, hdc);
          if ( CompatibleDC )
          {
            if ( v15 )
              SelectObject(CompatibleDC, v15);
            DeleteDC(CompatibleDC);
          }
          if ( v10 )
          {
            if ( h )
              SelectObject(v10, h);
            DeleteDC(v10);
          }
          if ( v24 )
            SelectObject(hdcDest, v24);
          if ( DIBitmap )
            DeleteObject(DIBitmap);
          if ( v17 )
            DeleteObject(v17);
          if ( v9 )
            DeleteObject(v9);
          goto LABEL_49;
        }
      }
    }
    else
    {
      v15 = 0;
    }
    v17 = 0;
    goto LABEL_33;
  }
LABEL_49:
  LOBYTE(v3) = *a2 != 0;
  return v3;
}

```

## disassembly

```asm
0x1800b06c0  mov     [rsp-8+arg_10], r8
0x1800b06c5  mov     [rsp-8+arg_8], rdx
0x1800b06ca  push    rbp
0x1800b06cb  push    rbx
0x1800b06cc  push    rsi
0x1800b06cd  push    rdi
0x1800b06ce  push    r12
0x1800b06d0  push    r13
0x1800b06d2  push    r14
0x1800b06d4  push    r15
0x1800b06d6  lea     rbp, [rsp-1Fh]
0x1800b06db  mov     eax, 0C8h
0x1800b06e0  call    _alloca_probe
0x1800b06e5  sub     rsp, rax
0x1800b06e8  xor     esi, esi
0x1800b06ea  cmp     dword ptr [rcx], 0Ch
0x1800b06ed  mov     rbx, rcx
0x1800b06f0  jz      short loc_1800B071A
0x1800b06f2  cmp     dword ptr [rcx], 28h ; '('
0x1800b06f5  jz      short loc_1800B06FE
0x1800b06f7  xor     eax, eax
0x1800b06f9  jmp     loc_1800B0B45
0x1800b06fe  mov     eax, [rcx+20h]
0x1800b0701  test    eax, eax
0x1800b0703  jnz     short loc_1800B070E
0x1800b0705  movzx   ecx, word ptr [rcx+0Eh]; unsigned int
0x1800b0709  call    ?_NumColorOfBitCount@@YAII@Z; _NumColorOfBitCount(uint)
0x1800b070e  mov     edi, eax
0x1800b0710  add     rdi, 0Ah
0x1800b0714  lea     rdi, [rbx+rdi*4]
0x1800b0718  jmp     short loc_1800B0730
0x1800b071a  movzx   ecx, word ptr [rcx+0Ah]; unsigned int
0x1800b071e  call    ?_NumColorOfBitCount@@YAII@Z; _NumColorOfBitCount(uint)
0x1800b0723  mov     edi, eax
0x1800b0725  add     rdi, 4
0x1800b0729  lea     rax, [rbx+rdi*2]
0x1800b072d  add     rdi, rax
0x1800b0730  xor     ecx, ecx; hWnd
0x1800b0732  mov     r15, rsi
0x1800b0735  mov     [rbp+57h+h], rsi
0x1800b0739  mov     [rbp+57h+var_88], rsi
0x1800b073d  mov     r12, rsi
0x1800b0740  call    cs:__imp_GetDC
0x1800b0746  mov     r14, rax
0x1800b0749  mov     [rbp+57h+hdc], rax
0x1800b074d  test    rax, rax
0x1800b0750  jz      loc_1800B0B38
0x1800b0756  mov     r9, rdi; pjBits
0x1800b0759  mov     r8d, 4; flInit
0x1800b075f  mov     rdx, rbx; pbmih
0x1800b0762  mov     rcx, rax; hdc
0x1800b0765  mov     [rsp+100h+iUsage], esi; iUsage
0x1800b0769  mov     [rsp+100h+pbmi], rbx; pbmi
0x1800b076e  call    cs:__imp_CreateDIBitmap
0x1800b0774  mov     rcx, r14; hdc
0x1800b0777  mov     r13, rax
0x1800b077a  call    cs:__imp_CreateCompatibleDC
0x1800b0780  mov     r14, rax
0x1800b0783  test    rax, rax
0x1800b0786  jz      loc_1800B0AA1
0x1800b078c  mov     rcx, [rbp+57h+hdc]; hdc
0x1800b0790  call    cs:__imp_CreateCompatibleDC
0x1800b0796  mov     r12, rax
0x1800b0799  test    rax, rax
0x1800b079c  jz      loc_1800B0AA1
0x1800b07a2  test    r13, r13
0x1800b07a5  jz      loc_1800B0AA1
0x1800b07ab  lea     r8, [rbp+57h+pv]; pv
0x1800b07af  mov     edx, 20h ; ' '; c
0x1800b07b4  mov     rcx, r13; h
0x1800b07b7  call    cs:__imp_GetObjectA
0x1800b07bd  test    eax, eax
0x1800b07bf  jz      loc_1800B0AA1
0x1800b07c5  mov     rdx, r13; h
0x1800b07c8  mov     rcx, r14; hdc
0x1800b07cb  call    cs:__imp_SelectObject
0x1800b07d1  mov     rdi, rax
0x1800b07d4  mov     [rbp+57h+var_70], rax
0x1800b07d8  test    rax, rax
0x1800b07db  jz      loc_1800B0AA4
0x1800b07e1  mov     r8d, [rbp+57h+nHeight]
0x1800b07e5  xor     edx, edx; x
0x1800b07e7  mov     rcx, r14; hdc
0x1800b07ea  dec     r8d; y
0x1800b07ed  call    cs:__imp_GetPixel
0x1800b07f3  mov     [rbp+57h+color], eax
0x1800b07f6  cmp     eax, 0FFFFFFFFh
0x1800b07f9  jz      loc_1800B0AA4
0x1800b07ff  mov     edx, [rbp+57h+nHeight]; nHeight
0x1800b0802  mov     ecx, [rbp+57h+nWidth]; nWidth
0x1800b0805  mov     eax, 1
0x1800b080a  mov     r9d, eax; nBitCount
0x1800b080d  mov     r8d, eax; nPlanes
0x1800b0810  mov     [rsp+100h+pbmi], rsi; lpBits
0x1800b0815  call    cs:__imp_CreateBitmap
0x1800b081b  mov     rbx, rax
0x1800b081e  mov     [rbp+57h+var_78], rax
0x1800b0822  test    rax, rax
0x1800b0825  jz      loc_1800B0AA7
0x1800b082b  mov     rdx, rax; h
0x1800b082e  mov     rcx, r12; hdc
0x1800b0831  call    cs:__imp_SelectObject
0x1800b0837  mov     [rbp+57h+h], rax
0x1800b083b  test    rax, rax
0x1800b083e  jz      loc_1800B0AA7
0x1800b0844  mov     edx, [rbp+57h+color]; color
0x1800b0847  mov     rcx, r14; hdc
0x1800b084a  call    cs:__imp_SetBkColor
0x1800b0850  cmp     eax, 80000000h
0x1800b0855  jz      loc_1800B0AA7
0x1800b085b  mov     eax, [rbp+57h+nHeight]
0x1800b085e  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b0862  mov     [rsp+100h+rop], 0CC0020h; rop
0x1800b086a  mov     [rsp+100h+y1], esi; y1
0x1800b086e  mov     [rsp+100h+x1], esi; x1
0x1800b0872  xor     r8d, r8d; y
0x1800b0875  xor     edx, edx; x
0x1800b0877  mov     rcx, r12; hdc
0x1800b087a  mov     qword ptr [rsp+100h+iUsage], r14; hdcSrc
0x1800b087f  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b0883  call    cs:__imp_BitBlt
0x1800b0889  cmp     [rbp+57h+color], esi
0x1800b088c  jz      short loc_1800B08EB
0x1800b088e  xor     edx, edx; color
0x1800b0890  mov     rcx, r14; hdc
0x1800b0893  call    cs:__imp_SetBkColor
0x1800b0899  cmp     eax, 80000000h
0x1800b089e  jz      loc_1800B0AA7
0x1800b08a4  mov     edx, 0FFFFFFh; color
0x1800b08a9  mov     rcx, r14; hdc
0x1800b08ac  call    cs:__imp_SetTextColor
0x1800b08b2  cmp     eax, 80000000h
0x1800b08b7  jz      loc_1800B0AA7
0x1800b08bd  mov     eax, [rbp+57h+nHeight]
0x1800b08c0  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b08c4  mov     [rsp+100h+rop], 8800C6h; rop
0x1800b08cc  mov     [rsp+100h+y1], esi; y1
0x1800b08d0  mov     [rsp+100h+x1], esi; x1
0x1800b08d4  xor     r8d, r8d; y
0x1800b08d7  xor     edx, edx; x
0x1800b08d9  mov     rcx, r14; hdc
0x1800b08dc  mov     qword ptr [rsp+100h+iUsage], r12; hdcSrc
0x1800b08e1  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b08e5  call    cs:__imp_BitBlt
0x1800b08eb  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800b08f2  mov     edx, 3DEh; unsigned __int16
0x1800b08f7  call    ?LoadBitmap3D@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@G@Z; LoadBitmap3D(HINSTANCE__ *,ushort)
0x1800b08fc  mov     r15, rax
0x1800b08ff  test    rax, rax
0x1800b0902  jz      loc_1800B0AA7
0x1800b0908  lea     r8, [rbp+57h+var_68]; pv
0x1800b090c  mov     edx, 20h ; ' '; c
0x1800b0911  mov     rcx, rax; h
0x1800b0914  call    cs:__imp_GetObjectA
0x1800b091a  test    eax, eax
0x1800b091c  jz      loc_1800B0AA7
0x1800b0922  mov     eax, [rbp+57h+var_64]
0x1800b0925  mov     rcx, cs:hdcDest; hdc
0x1800b092c  sub     eax, [rbp+57h+nWidth]
0x1800b092f  dec     eax
0x1800b0931  cdq
0x1800b0932  sub     eax, edx
0x1800b0934  sar     eax, 1
0x1800b0936  mov     [rbp+57h+x], eax
0x1800b0939  mov     eax, [rbp+57h+var_60]
0x1800b093c  sub     eax, [rbp+57h+nHeight]
0x1800b093f  dec     eax
0x1800b0941  cdq
0x1800b0942  sub     eax, edx
0x1800b0944  mov     rdx, r15; h
0x1800b0947  sar     eax, 1
0x1800b0949  mov     [rbp+57h+color], eax
0x1800b094c  call    cs:__imp_SelectObject
0x1800b0952  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b0956  mov     r8d, [rbp+57h+color]; y
0x1800b095a  mov     edx, [rbp+57h+x]; x
0x1800b095d  mov     rcx, cs:hdcDest; hdc
0x1800b0964  mov     [rsp+100h+rop], 8800C6h; rop
0x1800b096c  mov     [rsp+100h+y1], esi; y1
0x1800b0970  mov     [rbp+57h+var_88], rax
0x1800b0974  mov     eax, [rbp+57h+nHeight]
0x1800b0977  mov     [rsp+100h+x1], esi; x1
0x1800b097b  mov     qword ptr [rsp+100h+iUsage], r12; hdcSrc
0x1800b0980  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b0984  call    cs:__imp_BitBlt
0x1800b098a  mov     eax, [rbp+57h+nHeight]
0x1800b098d  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b0991  mov     r8d, [rbp+57h+color]; y
0x1800b0995  mov     edx, [rbp+57h+x]; x
0x1800b0998  mov     rcx, cs:hdcDest; hdc
0x1800b099f  mov     [rsp+100h+rop], 0EE0086h; rop
0x1800b09a7  mov     [rsp+100h+y1], esi; y1
0x1800b09ab  mov     [rsp+100h+x1], esi; x1
0x1800b09af  mov     qword ptr [rsp+100h+iUsage], r14; hdcSrc
0x1800b09b4  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b09b8  call    cs:__imp_BitBlt
0x1800b09be  mov     r11, [rbp+57h+arg_8]
0x1800b09c2  cmp     [r11], rsi
0x1800b09c5  jz      short loc_1800B09D0
0x1800b09c7  mov     rcx, [r11]; ho
0x1800b09ca  call    cs:__imp_DeleteObject
0x1800b09d0  mov     rax, [rbp+57h+arg_10]
0x1800b09d4  cmp     [rax], rsi
0x1800b09d7  jz      short loc_1800B09E2
0x1800b09d9  mov     rcx, [rax]; ho
0x1800b09dc  call    cs:__imp_DeleteObject
0x1800b09e2  mov     rax, [rbp+57h+arg_8]
0x1800b09e6  mov     edx, 3DFh; unsigned __int16
0x1800b09eb  mov     [rax], r15
0x1800b09ee  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800b09f5  call    ?LoadBitmap3D@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@G@Z; LoadBitmap3D(HINSTANCE__ *,ushort)
0x1800b09fa  mov     r15, rax
0x1800b09fd  test    rax, rax
0x1800b0a00  jz      loc_1800B0AA7
0x1800b0a06  mov     rcx, cs:hdcDest; hdc
0x1800b0a0d  mov     rdx, rax; h
0x1800b0a10  call    cs:__imp_SelectObject
0x1800b0a16  test    rax, rax
0x1800b0a19  jz      loc_1800B0AA7
0x1800b0a1f  mov     eax, [rbp+57h+nHeight]
0x1800b0a22  mov     ebx, [rbp+57h+color]
0x1800b0a25  mov     edi, [rbp+57h+x]
0x1800b0a28  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b0a2c  mov     rcx, cs:hdcDest; hdc
0x1800b0a33  mov     [rsp+100h+rop], 8800C6h; rop
0x1800b0a3b  mov     [rsp+100h+y1], esi; y1
0x1800b0a3f  mov     [rsp+100h+x1], esi; x1
0x1800b0a43  lea     r8d, [rbx+1]; y
0x1800b0a47  lea     edx, [rdi+1]; x
0x1800b0a4a  mov     qword ptr [rsp+100h+iUsage], r12; hdcSrc
0x1800b0a4f  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b0a53  call    cs:__imp_BitBlt
0x1800b0a59  mov     eax, [rbp+57h+nHeight]
0x1800b0a5c  mov     r9d, [rbp+57h+nWidth]; cx
0x1800b0a60  mov     rcx, cs:hdcDest; hdc
0x1800b0a67  mov     [rsp+100h+rop], 0EE0086h; rop
0x1800b0a6f  mov     [rsp+100h+y1], esi; y1
0x1800b0a73  mov     [rsp+100h+x1], esi; x1
0x1800b0a77  lea     r8d, [rbx+1]; y
0x1800b0a7b  lea     edx, [rdi+1]; x
0x1800b0a7e  mov     qword ptr [rsp+100h+iUsage], r14; hdcSrc
0x1800b0a83  mov     dword ptr [rsp+100h+pbmi], eax; cy
0x1800b0a87  call    cs:__imp_BitBlt
0x1800b0a8d  mov     r8, [rbp+57h+arg_10]
0x1800b0a91  mov     rbx, [rbp+57h+var_78]
0x1800b0a95  mov     rdi, [rbp+57h+var_70]
0x1800b0a99  mov     [r8], r15
0x1800b0a9c  mov     r15, rsi
0x1800b0a9f  jmp     short loc_1800B0AA7
0x1800b0aa1  mov     rdi, rsi
0x1800b0aa4  mov     rbx, rsi
0x1800b0aa7  mov     rdx, [rbp+57h+hdc]; hDC
0x1800b0aab  xor     ecx, ecx; hWnd
0x1800b0aad  call    cs:__imp_ReleaseDC
0x1800b0ab3  test    r14, r14
0x1800b0ab6  jz      short loc_1800B0AD2
0x1800b0ab8  test    rdi, rdi
0x1800b0abb  jz      short loc_1800B0AC9
0x1800b0abd  mov     rdx, rdi; h
0x1800b0ac0  mov     rcx, r14; hdc
0x1800b0ac3  call    cs:__imp_SelectObject
0x1800b0ac9  mov     rcx, r14; hdc
0x1800b0acc  call    cs:__imp_DeleteDC
0x1800b0ad2  test    r12, r12
0x1800b0ad5  jz      short loc_1800B0AF5
0x1800b0ad7  mov     rax, [rbp+57h+h]
0x1800b0adb  test    rax, rax
0x1800b0ade  jz      short loc_1800B0AEC
0x1800b0ae0  mov     rdx, rax; h
0x1800b0ae3  mov     rcx, r12; hdc
0x1800b0ae6  call    cs:__imp_SelectObject
0x1800b0aec  mov     rcx, r12; hdc
0x1800b0aef  call    cs:__imp_DeleteDC
0x1800b0af5  mov     rax, [rbp+57h+var_88]
0x1800b0af9  test    rax, rax
0x1800b0afc  jz      short loc_1800B0B0E
0x1800b0afe  mov     rcx, cs:hdcDest; hdc
0x1800b0b05  mov     rdx, rax; h
0x1800b0b08  call    cs:__imp_SelectObject
0x1800b0b0e  test    r13, r13
0x1800b0b11  jz      short loc_1800B0B1C
0x1800b0b13  mov     rcx, r13; ho
0x1800b0b16  call    cs:__imp_DeleteObject
0x1800b0b1c  test    rbx, rbx
0x1800b0b1f  jz      short loc_1800B0B2A
0x1800b0b21  mov     rcx, rbx; ho
0x1800b0b24  call    cs:__imp_DeleteObject
0x1800b0b2a  test    r15, r15
0x1800b0b2d  jz      short loc_1800B0B38
0x1800b0b2f  mov     rcx, r15; ho
0x1800b0b32  call    cs:__imp_DeleteObject
0x1800b0b38  mov     rax, [rbp+57h+arg_8]
0x1800b0b3c  cmp     [rax], rsi
0x1800b0b3f  setnz   sil
0x1800b0b43  mov     eax, esi
0x1800b0b45  add     rsp, 0C8h
0x1800b0b4c  pop     r15
0x1800b0b4e  pop     r14
0x1800b0b50  pop     r13
0x1800b0b52  pop     r12
  ... truncated ...
```
