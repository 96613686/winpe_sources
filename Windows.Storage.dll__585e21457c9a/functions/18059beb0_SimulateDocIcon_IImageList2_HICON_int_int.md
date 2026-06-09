# SimulateDocIcon(IImageList2 *,HICON__ *,int,int)

- ea: `0x18059beb0`
- end: `0x18059c37c`
- name: `?SimulateDocIcon@@YAPEAUHICON__@@PEAUIImageList2@@PEAU1@HH@Z`
- size: `1228`
- prototype: `HICON(struct IImageList2 *, HICON, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180138190`

## callees

- `0x1800c9310`
- `0x180238d60`
- `0x1802d5f50`
- `0x1803a4cb0`
- `0x18059bb64`
- `0x18059beb0`
- `0x18065a010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18059c2e0`
- `GDI32!DeleteObject` at `0x18059c33b`
- `GDI32!DeleteObject` at `0x18059c344`
- `GDI32!DeleteObject` at `0x18059c2e0`
- `GDI32!DeleteObject` at `0x18059c33b`
- `GDI32!DeleteObject` at `0x18059c344`
- `GDI32!SelectObject` at `0x18059bfc3`
- `GDI32!SelectObject` at `0x18059c02e`
- `GDI32!SelectObject` at `0x18059c20d`
- `GDI32!SelectObject` at `0x18059c2d6`
- `GDI32!SelectObject` at `0x18059c2fa`
- `GDI32!SelectObject` at `0x18059bfc3`
- `GDI32!SelectObject` at `0x18059c02e`
- `GDI32!SelectObject` at `0x18059c20d`
- `GDI32!SelectObject` at `0x18059c2d6`
- `GDI32!SelectObject` at `0x18059c2fa`
- `GDI32!CreateCompatibleDC` at `0x18059bfaa`
- `GDI32!CreateCompatibleDC` at `0x18059c1ae`
- `GDI32!CreateCompatibleDC` at `0x18059bfaa`
- `GDI32!CreateCompatibleDC` at `0x18059c1ae`
- `GDI32!CreateBitmap` at `0x18059bf94`
- `GDI32!CreateBitmap` at `0x18059bf94`
- `GDI32!CreateCompatibleBitmap` at `0x18059bf68`
- `GDI32!CreateCompatibleBitmap` at `0x18059bf68`
- `GDI32!BitBlt` at `0x18059c2c6`
- `GDI32!BitBlt` at `0x18059c2c6`
- `GDI32!DeleteDC` at `0x18059c2ed`
- `GDI32!DeleteDC` at `0x18059c303`
- `GDI32!DeleteDC` at `0x18059c2ed`
- `GDI32!DeleteDC` at `0x18059c303`
- `GDI32!GetDeviceCaps` at `0x18059bf2f`
- `GDI32!GetDeviceCaps` at `0x18059bf2f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x18059c08f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x18059c08f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x18059c23e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x18059c23e`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x18059c0fe`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x18059c27d`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x18059c0fe`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x18059c27d`
- `ext-ms-win-ntuser-gui-l1-3-0!CreateIconIndirect` at `0x18059c32f`
- `ext-ms-win-ntuser-gui-l1-3-0!CreateIconIndirect` at `0x18059c32f`
- `USER32!ReleaseDC` at `0x18059c34f`
- `USER32!ReleaseDC` at `0x18059c34f`
- `USER32!GetDC` at `0x18059bf12`
- `USER32!GetDC` at `0x18059bf12`

## pseudocode

```c
HICON __fastcall SimulateDocIcon(struct IImageList2 *a1, HICON a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // r12
  __int64 v5; // r15
  HICON v6; // rsi
  HDC DC; // rax
  HDC v9; // r13
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v11; // rdi
  HDC CompatibleDC; // rax
  HDC v13; // r14
  unsigned int StockImageIndex; // ecx
  void (__fastcall *v15)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int); // rax
  void (__fastcall *v16)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD); // rax
  __int64 v17; // rcx
  HICON v18; // r9
  unsigned int v19; // ebx
  unsigned int v20; // esi
  unsigned int v21; // r9d
  unsigned int v22; // ecx
  struct tagRGBQUAD *v23; // r11
  unsigned int v24; // edx
  unsigned int v25; // r12d
  unsigned int v26; // r10d
  unsigned int v27; // r9d
  unsigned int v28; // edx
  __int64 v29; // rax
  HDC v30; // rbx
  HBITMAP v31; // rax
  HGDIOBJ v32; // rax
  void *v33; // rsi
  HGDIOBJ v34; // rbx
  unsigned int cyWidth; // [rsp+60h] [rbp-69h] BYREF
  int xLeft; // [rsp+64h] [rbp-65h]
  HDC hdc; // [rsp+68h] [rbp-61h]
  HBITMAP v39; // [rsp+70h] [rbp-59h]
  HGDIOBJ h; // [rsp+78h] [rbp-51h]
  HICON hIcon; // [rsp+80h] [rbp-49h]
  HGDIOBJ ho; // [rsp+88h] [rbp-41h]
  HGDIOBJ v43; // [rsp+90h] [rbp-39h]
  struct tagRGBQUAD *ppvBits; // [rsp+98h] [rbp-31h] BYREF
  ICONINFO piconinfo; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-9h] BYREF
  int v47; // [rsp+C8h] [rbp-1h]
  unsigned int v48; // [rsp+CCh] [rbp+3h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  hIcon = a2;
  if ( !a2 || ((int (__fastcall *)(struct IImageList2 *, _QWORD, _QWORD))a1->lpVtbl->Resize)(a1, a3, a4) < 0 )
    return 0;
  DC = GetDC(0);
  v9 = DC;
  if ( DC )
  {
    ppvBits = 0;
    if ( GetDeviceCaps(DC, 12) < 24 )
    {
      cyWidth = 0;
      CompatibleBitmap = CreateCompatibleBitmap(v9, v5, v4);
    }
    else
    {
      cyWidth = 1;
      CompatibleBitmap = DIBSectionUtil::Create(v9, 0x20u, v5, v4, &ppvBits);
    }
    v39 = CompatibleBitmap;
    v11 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      h = CreateBitmap(v5, v4, 1u, 1u, 0);
      if ( h )
      {
        CompatibleDC = CreateCompatibleDC(v9);
        v13 = CompatibleDC;
        if ( CompatibleDC )
        {
          v43 = SelectObject(CompatibleDC, h);
          StockImageIndex = Shell_GetStockImageIndex(SIID_DOCNOASSOC);
          xLeft = StockImageIndex;
          v15 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int))qword_180802548;
          if ( qword_180802548 == -1 )
          {
            GetProcFromComCtl32(&qword_180802548, "ImageList_Draw");
            v15 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int))qword_180802548;
            StockImageIndex = xLeft;
          }
          if ( v15 )
            v15(a1, StockImageIndex, v13, 0, 0, 16);
          SelectObject(v13, v11);
          v16 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD))qword_180802570;
          if ( qword_180802570 == -1 )
          {
            GetProcFromComCtl32(&qword_180802570, "ImageList_DrawEx");
            v16 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD))qword_180802570;
          }
          v17 = 0;
          if ( v16 )
            v16(a1, (unsigned int)xLeft, v13, 0, 0, 0, 0, 0, -16777216, 0);
          if ( (unsigned int)SHGetCurColorRes(v17) <= 8 )
          {
            hdc = CreateCompatibleDC(v13);
            v30 = hdc;
            if ( hdc )
            {
              cyWidth = (int)v4 / 2;
              xLeft = (int)v5 / 2;
              v31 = DIBSectionUtil::Create(v9, 0x18u, (int)v5 / 2 + 2, (int)v4 / 2 + 2, 0);
              ho = v31;
              if ( v31 )
              {
                v32 = SelectObject(hdc, v31);
                v47 = xLeft + 3;
                v48 = cyWidth + 3;
                v33 = v32;
                v46 = 0;
                SHFillRectClr(hdc, &v46, 0xFFFFFF);
                DrawIconEx(hdc, 1, 1, hIcon, xLeft, cyWidth, 0, 0, 3u);
                BitBlt(v13, (int)v5 / 4 - 1, (int)v4 / 4 - 1, xLeft + 3, cyWidth + 3, hdc, 0, 0, 0xCC0020u);
                v30 = hdc;
                SelectObject(hdc, v33);
                DeleteObject(ho);
                v11 = v39;
              }
              DeleteDC(v30);
            }
          }
          else
          {
            v18 = v6;
            v19 = (int)v4 / 4;
            xLeft = (int)v5 / 4;
            v20 = (int)v5 / 4;
            LODWORD(v39) = (int)v4 / 2;
            LODWORD(hdc) = (int)v5 / 2;
            DrawIconEx(v13, (int)v5 / 4, (int)v4 / 4, v18, (int)v5 / 2, (int)v4 / 2, 0, 0, 3u);
            if ( cyWidth )
            {
              cyWidth = 0;
              if ( (int)ULongLongToULong(v5 * v4, &cyWidth) >= 0 )
              {
                v22 = v21;
                v23 = ppvBits;
                v24 = v21;
                if ( cyWidth )
                {
                  v25 = v21 + 1;
                  while ( !v22 )
                  {
                    if ( ppvBits[v24].rgbReserved != (_BYTE)v21 )
                      v22 = v21 + 1;
                    v24 += v25;
                    if ( v24 >= cyWidth )
                    {
                      if ( !v22 )
                        goto LABEL_39;
                      break;
                    }
                  }
                  v26 = v19 + (_DWORD)v39;
                  if ( v19 < v19 + (unsigned int)v39 )
                  {
                    v27 = v20 + (_DWORD)hdc;
                    do
                    {
                      if ( v20 < v27 )
                      {
                        v28 = (int)v5 / 4;
                        do
                        {
                          v29 = (_DWORD)v5 * v19 + v28;
                          v28 += v25;
                          v23[v29].rgbReserved = -1;
                        }
                        while ( v28 < v27 );
                      }
                      v19 += v25;
                    }
                    while ( v19 < v26 );
                  }
                }
              }
            }
          }
LABEL_39:
          SelectObject(v13, v43);
          DeleteDC(v13);
        }
        v34 = h;
        piconinfo.hbmMask = (HBITMAP)h;
        *(_QWORD *)&piconinfo.xHotspot = 0;
        *(&piconinfo.yHotspot + 1) = 0;
        piconinfo.fIcon = 1;
        piconinfo.hbmColor = v11;
        v6 = CreateIconIndirect(&piconinfo);
        DeleteObject(v34);
      }
      DeleteObject(v11);
    }
    ReleaseDC(0, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18059beb0  push    rbp
0x18059beb2  push    rbx
0x18059beb3  push    rsi
0x18059beb4  push    rdi
0x18059beb5  push    r12
0x18059beb7  push    r13
0x18059beb9  push    r14
0x18059bebb  push    r15
0x18059bebd  lea     rbp, [rsp-1Fh]
0x18059bec2  sub     rsp, 0E8h
0x18059bec9  mov     rax, cs:__security_cookie
0x18059bed0  xor     rax, rsp
0x18059bed3  mov     [rbp+57h+var_50], rax
0x18059bed7  xor     r14d, r14d
0x18059beda  mov     r12d, r9d
0x18059bedd  mov     r15d, r8d
0x18059bee0  mov     rsi, rdx
0x18059bee3  mov     [rbp+57h+hIcon], rdx
0x18059bee7  mov     rbx, rcx
0x18059beea  test    rdx, rdx
0x18059beed  jz      loc_18059C35A
0x18059bef3  mov     rax, [rcx]
0x18059bef6  mov     r8d, r12d
0x18059bef9  mov     edx, r15d
0x18059befc  mov     rax, [rax+100h]
0x18059bf03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059bf08  test    eax, eax
0x18059bf0a  js      loc_18059C35A
0x18059bf10  xor     ecx, ecx; hWnd
0x18059bf12  call    cs:__imp_GetDC
0x18059bf18  mov     r13, rax
0x18059bf1b  test    rax, rax
0x18059bf1e  jz      loc_18059C355
0x18059bf24  lea     edx, [r14+0Ch]; index
0x18059bf28  mov     [rbp+57h+ppvBits], r14
0x18059bf2c  mov     rcx, rax; hdc
0x18059bf2f  call    cs:__imp_GetDeviceCaps
0x18059bf35  mov     rcx, r13; HDC
0x18059bf38  cmp     eax, 18h
0x18059bf3b  jl      short loc_18059BF5E
0x18059bf3d  lea     rax, [rbp+57h+ppvBits]
0x18059bf41  mov     [rbp+57h+var_C0], 1
0x18059bf48  lea     edx, [r14+20h]; unsigned __int16
0x18059bf4c  mov     [rsp+120h+lpBits], rax; ppvBits
0x18059bf51  mov     r9d, r12d; unsigned int
0x18059bf54  mov     r8d, r15d; unsigned int
0x18059bf57  call    ?Create@DIBSectionUtil@@SAPEAUHBITMAP__@@PEAUHDC__@@GIIPEAPEAUtagRGBQUAD@@@Z; DIBSectionUtil::Create(HDC__ *,ushort,uint,uint,tagRGBQUAD * *)
0x18059bf5c  jmp     short loc_18059BF6E
0x18059bf5e  mov     r8d, r12d; cy
0x18059bf61  mov     [rbp+57h+var_C0], r14d
0x18059bf65  mov     edx, r15d; cx
0x18059bf68  call    cs:__imp_CreateCompatibleBitmap
0x18059bf6e  mov     [rbp+57h+var_B0], rax
0x18059bf72  mov     rdi, rax
0x18059bf75  test    rax, rax
0x18059bf78  jz      loc_18059C34A
0x18059bf7e  mov     eax, 1
0x18059bf83  mov     [rsp+120h+lpBits], r14; lpBits
0x18059bf88  mov     r9d, eax; nBitCount
0x18059bf8b  mov     r8d, eax; nPlanes
0x18059bf8e  mov     edx, r12d; nHeight
0x18059bf91  mov     ecx, r15d; nWidth
0x18059bf94  call    cs:__imp_CreateBitmap
0x18059bf9a  mov     [rbp+57h+h], rax
0x18059bf9e  test    rax, rax
0x18059bfa1  jz      loc_18059C341
0x18059bfa7  mov     rcx, r13; hdc
0x18059bfaa  call    cs:__imp_CreateCompatibleDC
0x18059bfb0  mov     r14, rax
0x18059bfb3  test    rax, rax
0x18059bfb6  jz      loc_18059C309
0x18059bfbc  mov     rdx, [rbp+57h+h]; h
0x18059bfc0  mov     rcx, rax; hdc
0x18059bfc3  call    cs:__imp_SelectObject
0x18059bfc9  xor     ecx, ecx; enum SHSTOCKICONID
0x18059bfcb  mov     [rbp+57h+var_90], rax
0x18059bfcf  call    ?Shell_GetStockImageIndex@@YAHW4SHSTOCKICONID@@@Z; Shell_GetStockImageIndex(SHSTOCKICONID)
0x18059bfd4  mov     ecx, eax
0x18059bfd6  mov     [rbp+57h+xLeft], eax
0x18059bfd9  mov     rax, cs:qword_180802548
0x18059bfe0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18059bfe4  jnz     short loc_18059C003
0x18059bfe6  lea     rdx, aImagelistDraw; "ImageList_Draw"
0x18059bfed  lea     rcx, qword_180802548
0x18059bff4  call    _GetProcFromComCtl32
0x18059bff9  mov     rax, cs:qword_180802548
0x18059c000  mov     ecx, [rbp+57h+xLeft]
0x18059c003  test    rax, rax
0x18059c006  jz      short loc_18059C028
0x18059c008  mov     edx, ecx
0x18059c00a  mov     [rsp+120h+cyWidth], 10h
0x18059c012  mov     rcx, rbx
0x18059c015  mov     dword ptr [rsp+120h+lpBits], 0
0x18059c01d  xor     r9d, r9d
0x18059c020  mov     r8, r14
0x18059c023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c028  mov     rdx, rdi; h
0x18059c02b  mov     rcx, r14; hdc
0x18059c02e  call    cs:__imp_SelectObject
0x18059c034  mov     rax, cs:qword_180802570
0x18059c03b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18059c03f  jnz     short loc_18059C05B
0x18059c041  lea     rdx, aImagelistDrawe; "ImageList_DrawEx"
0x18059c048  lea     rcx, qword_180802570
0x18059c04f  call    _GetProcFromComCtl32
0x18059c054  mov     rax, cs:qword_180802570
0x18059c05b  xor     ecx, ecx
0x18059c05d  test    rax, rax
0x18059c060  jz      short loc_18059C08F
0x18059c062  mov     edx, [rbp+57h+xLeft]
0x18059c065  xor     r9d, r9d
0x18059c068  mov     [rsp+120h+var_D8], ecx
0x18059c06c  mov     r8, r14
0x18059c06f  mov     [rsp+120h+diFlags], 0FF000000h
0x18059c077  mov     dword ptr [rsp+120h+hbrFlickerFreeDraw], ecx
0x18059c07b  mov     [rsp+120h+istepIfAniCur], ecx
0x18059c07f  mov     [rsp+120h+cyWidth], ecx
0x18059c083  mov     dword ptr [rsp+120h+lpBits], ecx
0x18059c087  mov     rcx, rbx
0x18059c08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c08f  call    cs:__imp_SHGetCurColorRes
0x18059c095  cmp     eax, 8
0x18059c098  jbe     loc_18059C1AB
0x18059c09e  mov     ecx, 4
0x18059c0a3  mov     [rsp+120h+diFlags], 3; diFlags
0x18059c0ab  mov     eax, r12d
0x18059c0ae  mov     [rsp+120h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18059c0b7  cdq
0x18059c0b8  mov     [rsp+120h+istepIfAniCur], 0; istepIfAniCur
0x18059c0c0  idiv    ecx
0x18059c0c2  mov     r9, rsi; hIcon
0x18059c0c5  mov     ebx, eax
0x18059c0c7  mov     eax, r15d
0x18059c0ca  cdq
0x18059c0cb  idiv    ecx
0x18059c0cd  mov     ecx, 2
0x18059c0d2  mov     [rbp+57h+xLeft], eax
0x18059c0d5  mov     eax, r12d
0x18059c0d8  mov     esi, [rbp+57h+xLeft]
0x18059c0db  cdq
0x18059c0dc  idiv    ecx
0x18059c0de  mov     r8d, eax
0x18059c0e1  mov     dword ptr [rbp+57h+var_B0], eax
0x18059c0e4  mov     eax, r15d
0x18059c0e7  mov     [rsp+120h+cyWidth], r8d; cyWidth
0x18059c0ec  cdq
0x18059c0ed  mov     r8d, ebx; yTop
0x18059c0f0  idiv    ecx
0x18059c0f2  mov     edx, esi; xLeft
0x18059c0f4  mov     rcx, r14; hdc
0x18059c0f7  mov     dword ptr [rbp+57h+hdc], eax
0x18059c0fa  mov     dword ptr [rsp+120h+lpBits], eax; cxWidth
0x18059c0fe  call    cs:__imp_DrawIconEx
0x18059c104  xor     r9d, r9d
0x18059c107  cmp     [rbp+57h+var_C0], r9d
0x18059c10b  jz      loc_18059C2F3
0x18059c111  mov     rcx, r12
0x18059c114  mov     [rbp+57h+var_C0], r9d
0x18059c118  imul    rcx, r15; unsigned __int64
0x18059c11c  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x18059c120  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18059c125  test    eax, eax
0x18059c127  js      loc_18059C2F3
0x18059c12d  mov     r8d, [rbp+57h+var_C0]
0x18059c131  mov     ecx, r9d
0x18059c134  mov     r11, [rbp+57h+ppvBits]
0x18059c138  mov     edx, r9d
0x18059c13b  test    r8d, r8d
0x18059c13e  jz      loc_18059C2F3
0x18059c144  lea     r12d, [r9+1]
0x18059c148  test    ecx, ecx
0x18059c14a  jnz     short loc_18059C167
0x18059c14c  mov     eax, edx
0x18059c14e  cmp     [r11+rax*4+3], r9b
0x18059c153  cmovnz  ecx, r12d
0x18059c157  add     edx, r12d
0x18059c15a  cmp     edx, r8d
0x18059c15d  jb      short loc_18059C148
0x18059c15f  test    ecx, ecx
0x18059c161  jz      loc_18059C2F3
0x18059c167  mov     r10d, dword ptr [rbp+57h+var_B0]
0x18059c16b  add     r10d, ebx
0x18059c16e  cmp     ebx, r10d
0x18059c171  jnb     loc_18059C2F3
0x18059c177  mov     r9d, dword ptr [rbp+57h+hdc]
0x18059c17b  add     r9d, esi
0x18059c17e  cmp     esi, r9d
0x18059c181  jnb     short loc_18059C19E
0x18059c183  mov     r8d, ebx
0x18059c186  mov     edx, esi
0x18059c188  imul    r8d, r15d
0x18059c18c  lea     eax, [r8+rdx]
0x18059c190  add     edx, r12d
0x18059c193  mov     byte ptr [r11+rax*4+3], 0FFh
0x18059c199  cmp     edx, r9d
0x18059c19c  jb      short loc_18059C18C
0x18059c19e  add     ebx, r12d
0x18059c1a1  cmp     ebx, r10d
0x18059c1a4  jb      short loc_18059C17E
0x18059c1a6  jmp     loc_18059C2F3
0x18059c1ab  mov     rcx, r14; hdc
0x18059c1ae  call    cs:__imp_CreateCompatibleDC
0x18059c1b4  mov     [rbp+57h+hdc], rax
0x18059c1b8  mov     rbx, rax
0x18059c1bb  test    rax, rax
0x18059c1be  jz      loc_18059C2F3
0x18059c1c4  mov     ecx, 2
0x18059c1c9  mov     [rsp+120h+lpBits], 0; ppvBits
0x18059c1d2  mov     eax, r12d
0x18059c1d5  cdq
0x18059c1d6  idiv    ecx
0x18059c1d8  mov     r8d, eax
0x18059c1db  mov     [rbp+57h+var_C0], eax
0x18059c1de  mov     eax, r15d
0x18059c1e1  cdq
0x18059c1e2  idiv    ecx
0x18059c1e4  lea     r9d, [r8+2]; unsigned int
0x18059c1e8  lea     edx, [rcx+16h]; unsigned __int16
0x18059c1eb  mov     [rbp+57h+xLeft], eax
0x18059c1ee  mov     rcx, r13; HDC
0x18059c1f1  lea     r8d, [rax+2]; unsigned int
0x18059c1f5  call    ?Create@DIBSectionUtil@@SAPEAUHBITMAP__@@PEAUHDC__@@GIIPEAPEAUtagRGBQUAD@@@Z; DIBSectionUtil::Create(HDC__ *,ushort,uint,uint,tagRGBQUAD * *)
0x18059c1fa  mov     [rbp+57h+ho], rax
0x18059c1fe  test    rax, rax
0x18059c201  jz      loc_18059C2EA
0x18059c207  mov     rdx, rax; h
0x18059c20a  mov     rcx, rbx; hdc
0x18059c20d  call    cs:__imp_SelectObject
0x18059c213  mov     edi, [rbp+57h+xLeft]
0x18059c216  lea     rdx, [rbp+57h+var_60]
0x18059c21a  mov     ebx, [rbp+57h+var_C0]
0x18059c21d  add     edi, 3
0x18059c220  mov     rcx, [rbp+57h+hdc]
0x18059c224  add     ebx, 3
0x18059c227  mov     r8d, 0FFFFFFh
0x18059c22d  mov     [rbp+57h+var_58], edi
0x18059c230  mov     [rbp+57h+var_54], ebx
0x18059c233  mov     rsi, rax
0x18059c236  mov     [rbp+57h+var_60], 0
0x18059c23e  call    cs:__imp_SHFillRectClr
0x18059c244  mov     eax, [rbp+57h+var_C0]
0x18059c247  mov     r9, [rbp+57h+hIcon]; hIcon
0x18059c24b  mov     rcx, [rbp+57h+hdc]; hdc
0x18059c24f  mov     [rsp+120h+diFlags], 3; diFlags
0x18059c257  mov     [rsp+120h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18059c260  mov     [rsp+120h+istepIfAniCur], 0; istepIfAniCur
0x18059c268  mov     [rsp+120h+cyWidth], eax; cyWidth
0x18059c26c  mov     eax, [rbp+57h+xLeft]
0x18059c26f  mov     dword ptr [rsp+120h+lpBits], eax; cxWidth
0x18059c273  mov     eax, 1
0x18059c278  mov     r8d, eax; yTop
0x18059c27b  mov     edx, eax; xLeft
0x18059c27d  call    cs:__imp_DrawIconEx
0x18059c283  mov     eax, r12d
0x18059c286  mov     [rsp+120h+diFlags], 0CC0020h; rop
0x18059c28e  cdq
0x18059c28f  mov     dword ptr [rsp+120h+hbrFlickerFreeDraw], 0; y1
0x18059c297  mov     ecx, 4
0x18059c29c  mov     [rsp+120h+istepIfAniCur], 0; x1
0x18059c2a4  idiv    ecx
0x18059c2a6  mov     r9d, edi; cx
0x18059c2a9  lea     r8d, [rax-1]; y
0x18059c2ad  mov     eax, r15d
0x18059c2b0  cdq
0x18059c2b1  idiv    ecx
0x18059c2b3  mov     rcx, [rbp+57h+hdc]
0x18059c2b7  mov     qword ptr [rsp+120h+cyWidth], rcx; hdcSrc
0x18059c2bc  mov     rcx, r14; hdc
0x18059c2bf  mov     dword ptr [rsp+120h+lpBits], ebx; cy
0x18059c2c3  lea     edx, [rax-1]; x
0x18059c2c6  call    cs:__imp_BitBlt
0x18059c2cc  mov     rbx, [rbp+57h+hdc]
0x18059c2d0  mov     rdx, rsi; h
0x18059c2d3  mov     rcx, rbx; hdc
0x18059c2d6  call    cs:__imp_SelectObject
0x18059c2dc  mov     rcx, [rbp+57h+ho]; ho
0x18059c2e0  call    cs:__imp_DeleteObject
0x18059c2e6  mov     rdi, [rbp+57h+var_B0]
0x18059c2ea  mov     rcx, rbx; hdc
0x18059c2ed  call    cs:__imp_DeleteDC
0x18059c2f3  mov     rdx, [rbp+57h+var_90]; h
0x18059c2f7  mov     rcx, r14; hdc
0x18059c2fa  call    cs:__imp_SelectObject
0x18059c300  mov     rcx, r14; hdc
0x18059c303  call    cs:__imp_DeleteDC
0x18059c309  mov     rbx, [rbp+57h+h]
0x18059c30d  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x18059c311  mov     [rbp+57h+piconinfo.hbmMask], rbx
0x18059c315  mov     qword ptr [rbp+57h+piconinfo.xHotspot], 0
0x18059c31d  mov     dword ptr [rbp+57h+piconinfo+0Ch], 0
0x18059c324  mov     [rbp+57h+piconinfo.fIcon], 1
0x18059c32b  mov     [rbp+57h+piconinfo.hbmColor], rdi
0x18059c32f  call    cs:__imp_CreateIconIndirect
0x18059c335  mov     rcx, rbx; ho
0x18059c338  mov     rsi, rax
0x18059c33b  call    cs:__imp_DeleteObject
0x18059c341  mov     rcx, rdi; ho
0x18059c344  call    cs:__imp_DeleteObject
0x18059c34a  mov     rdx, r13; hDC
0x18059c34d  xor     ecx, ecx; hWnd
  ... truncated ...
```
