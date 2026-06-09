# CInkCollector::_ConstructCursorFromProps(int,int,ulong,int,int)

- ea: `0x1800afd9c`
- end: `0x1800b0283`
- name: `?_ConstructCursorFromProps@CInkCollector@@AEAAJHHKHH@Z`
- size: `1255`
- prototype: `int(CInkCollector *__hidden this, int, int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b2b40`

## callees

- `0x1800afd9c`
- `0x180104f30`

## import_xrefs

- `USER32!DestroyCursor` at `0x1800afe42`
- `USER32!DestroyCursor` at `0x1800afe42`
- `USER32!GetSystemMetrics` at `0x1800afde4`
- `USER32!GetSystemMetrics` at `0x1800afdf9`
- `USER32!GetSystemMetrics` at `0x1800afe18`
- `USER32!GetSystemMetrics` at `0x1800afe29`
- `USER32!GetSystemMetrics` at `0x1800afde4`
- `USER32!GetSystemMetrics` at `0x1800afdf9`
- `USER32!GetSystemMetrics` at `0x1800afe18`
- `USER32!GetSystemMetrics` at `0x1800afe29`
- `USER32!CreateIconIndirect` at `0x1800b01d6`
- `USER32!CreateIconIndirect` at `0x1800b01d6`
- `USER32!GetDC` at `0x1800afe55`
- `USER32!GetDC` at `0x1800afe55`
- `USER32!ReleaseDC` at `0x1800b0253`
- `USER32!ReleaseDC` at `0x1800b0253`
- `GDI32!GdiFlush` at `0x1800b0121`
- `GDI32!GdiFlush` at `0x1800b0121`
- `GDI32!BitBlt` at `0x1800b011b`
- `GDI32!BitBlt` at `0x1800b011b`
- `GDI32!CreateDIBSection` at `0x1800b00c9`
- `GDI32!CreateDIBSection` at `0x1800b00c9`
- `GDI32!PatBlt` at `0x1800affe5`
- `GDI32!PatBlt` at `0x1800affe5`
- `GDI32!CreateBitmap` at `0x1800afef5`
- `GDI32!CreateBitmap` at `0x1800afef5`
- `GDI32!Ellipse` at `0x1800aff8d`
- `GDI32!Ellipse` at `0x1800b003b`
- `GDI32!Ellipse` at `0x1800aff8d`
- `GDI32!Ellipse` at `0x1800b003b`
- `GDI32!CreateSolidBrush` at `0x1800aff36`
- `GDI32!CreateSolidBrush` at `0x1800aff36`
- `GDI32!Rectangle` at `0x1800aff95`
- `GDI32!Rectangle` at `0x1800b0043`
- `GDI32!Rectangle` at `0x1800aff95`
- `GDI32!Rectangle` at `0x1800b0043`
- `GDI32!CreateCompatibleBitmap` at `0x1800afed1`
- `GDI32!CreateCompatibleBitmap` at `0x1800afed1`
- `GDI32!GetStockObject` at `0x1800aff5d`
- `GDI32!GetStockObject` at `0x1800afff0`
- `GDI32!GetStockObject` at `0x1800b000b`
- `GDI32!GetStockObject` at `0x1800aff5d`
- `GDI32!GetStockObject` at `0x1800afff0`
- `GDI32!GetStockObject` at `0x1800b000b`
- `GDI32!DeleteDC` at `0x1800b0205`
- `GDI32!DeleteDC` at `0x1800b023a`
- `GDI32!DeleteDC` at `0x1800b0248`
- `GDI32!DeleteDC` at `0x1800b0205`
- `GDI32!DeleteDC` at `0x1800b023a`
- `GDI32!DeleteDC` at `0x1800b0248`
- `GDI32!CreateCompatibleDC` at `0x1800afe6a`
- `GDI32!CreateCompatibleDC` at `0x1800afe76`
- `GDI32!CreateCompatibleDC` at `0x1800b009c`
- `GDI32!CreateCompatibleDC` at `0x1800afe6a`
- `GDI32!CreateCompatibleDC` at `0x1800afe76`
- `GDI32!CreateCompatibleDC` at `0x1800b009c`
- `GDI32!SelectObject` at `0x1800aff1a`
- `GDI32!SelectObject` at `0x1800aff4e`
- `GDI32!SelectObject` at `0x1800aff69`
- `GDI32!SelectObject` at `0x1800affa2`
- `GDI32!SelectObject` at `0x1800affaf`
- `GDI32!SelectObject` at `0x1800affc4`
- `GDI32!SelectObject` at `0x1800afffc`
- `GDI32!SelectObject` at `0x1800b0017`
- `GDI32!SelectObject` at `0x1800b0050`
- `GDI32!SelectObject` at `0x1800b005d`
- `GDI32!SelectObject` at `0x1800b0069`
- `GDI32!SelectObject` at `0x1800b00e2`
- `GDI32!SelectObject` at `0x1800b012d`
- `GDI32!SelectObject` at `0x1800b0139`
- `GDI32!SelectObject` at `0x1800b019f`
- `GDI32!SelectObject` at `0x1800b0212`
- `GDI32!SelectObject` at `0x1800aff1a`
- `GDI32!SelectObject` at `0x1800aff4e`
- `GDI32!SelectObject` at `0x1800aff69`
- `GDI32!SelectObject` at `0x1800affa2`
- `GDI32!SelectObject` at `0x1800affaf`
- `GDI32!SelectObject` at `0x1800affc4`
- `GDI32!SelectObject` at `0x1800afffc`
- `GDI32!SelectObject` at `0x1800b0017`
- `GDI32!SelectObject` at `0x1800b0050`
- `GDI32!SelectObject` at `0x1800b005d`
- `GDI32!SelectObject` at `0x1800b0069`
- `GDI32!SelectObject` at `0x1800b00e2`
- `GDI32!SelectObject` at `0x1800b012d`
- `GDI32!SelectObject` at `0x1800b0139`
- `GDI32!SelectObject` at `0x1800b019f`
- `GDI32!SelectObject` at `0x1800b0212`
- `GDI32!DeleteObject` at `0x1800affb8`
- `GDI32!DeleteObject` at `0x1800b01ed`
- `GDI32!DeleteObject` at `0x1800b021f`
- `GDI32!DeleteObject` at `0x1800b022d`
- `GDI32!DeleteObject` at `0x1800affb8`
- `GDI32!DeleteObject` at `0x1800b01ed`
- `GDI32!DeleteObject` at `0x1800b021f`
- `GDI32!DeleteObject` at `0x1800b022d`

## pseudocode

```c
__int64 __fastcall CInkCollector::_ConstructCursorFromProps(HCURSOR *this, int a2, int a3, COLORREF a4, int a5, int a6)
{
  unsigned int v7; // r13d
  int v10; // r15d
  HCURSOR v11; // rcx
  HDC DC; // rax
  HDC v13; // r12
  HDC CompatibleDC; // rdi
  HDC v15; // rax
  HDC v16; // rsi
  int v17; // r14d
  int v18; // r15d
  HBITMAP Bitmap; // r13
  HGDIOBJ v20; // rax
  HBRUSH SolidBrush; // rax
  HBRUSH v22; // rbx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v24; // rbx
  HGDIOBJ v25; // rax
  HGDIOBJ v26; // rax
  HDC v27; // rax
  HDC v28; // r15
  HBITMAP v29; // rax
  HGDIOBJ v30; // rbx
  HGDIOBJ v31; // r11
  int v32; // r10d
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rcx
  HGDIOBJ v36; // r14
  HICON v37; // rbx
  int right; // [rsp+50h] [rbp-89h]
  int bottom; // [rsp+54h] [rbp-85h]
  int cy; // [rsp+58h] [rbp-81h]
  unsigned int v42; // [rsp+5Ch] [rbp-7Dh]
  HGDIOBJ ppvBits; // [rsp+60h] [rbp-79h] BYREF
  HGDIOBJ ho; // [rsp+68h] [rbp-71h]
  HGDIOBJ h; // [rsp+70h] [rbp-69h]
  CInkCollector *v46; // [rsp+78h] [rbp-61h]
  HGDIOBJ v47; // [rsp+80h] [rbp-59h]
  ICONINFO piconinfo; // [rsp+88h] [rbp-51h] BYREF
  BITMAPINFO pbmi; // [rsp+A8h] [rbp-31h] BYREF

  v46 = (CInkCollector *)this;
  v7 = -2147467259;
  v42 = -2147467259;
  v10 = a2;
  if ( a2 >= GetSystemMetrics(78) / 2 )
    v10 = GetSystemMetrics(78) / 2;
  if ( a5 )
  {
    a3 = v10;
  }
  else if ( a3 >= GetSystemMetrics(79) / 2 )
  {
    a3 = GetSystemMetrics(79) / 2;
  }
  v11 = this[80];
  if ( v11 )
  {
    DestroyCursor(v11);
    this[80] = 0;
  }
  DC = GetDC(0);
  v13 = DC;
  if ( DC )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    v15 = CreateCompatibleDC(v13);
    v16 = v15;
    if ( CompatibleDC )
    {
      if ( !v15 )
        goto LABEL_44;
      right = v10 + 2;
      bottom = a3 + 2;
      v17 = 8 * ((v10 + 9) / 8);
      v18 = 8 * ((bottom + 7) / 8);
      cy = v18;
      h = CreateCompatibleBitmap(v13, v17, v18);
      Bitmap = CreateBitmap(v17, v18, 1u, 1u, 0);
      v20 = h;
      if ( h )
      {
        if ( Bitmap )
        {
          v47 = SelectObject(CompatibleDC, h);
          if ( a6 && !a4 )
            a4 = 65793;
          SolidBrush = CreateSolidBrush(a4);
          v22 = SolidBrush;
          if ( SolidBrush )
          {
            ho = SelectObject(CompatibleDC, SolidBrush);
            StockObject = GetStockObject(6);
            ppvBits = SelectObject(CompatibleDC, StockObject);
            if ( a5 )
              Ellipse(CompatibleDC, 0, 0, right, bottom);
            else
              Rectangle(CompatibleDC, 0, 0, right, bottom);
            SelectObject(CompatibleDC, ppvBits);
            SelectObject(CompatibleDC, ho);
            DeleteObject(v22);
            v24 = SelectObject(v16, Bitmap);
            PatBlt(v16, 0, 0, v17, v18, 0xFF0062u);
            v25 = GetStockObject(4);
            ppvBits = SelectObject(v16, v25);
            v26 = GetStockObject(7);
            ho = SelectObject(v16, v26);
            if ( a5 )
              Ellipse(v16, 0, 0, right, bottom);
            else
              Rectangle(v16, 0, 0, right, bottom);
            SelectObject(v16, ho);
            SelectObject(v16, ppvBits);
            SelectObject(v16, v24);
            pbmi.bmiHeader.biSize = 40;
            pbmi.bmiHeader.biWidth = v17;
            pbmi.bmiHeader.biHeight = 8 * ((bottom + 7) / 8);
            *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
            memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
            v27 = CreateCompatibleDC(CompatibleDC);
            v28 = v27;
            if ( v27 )
            {
              ppvBits = 0;
              v29 = CreateDIBSection(v27, &pbmi, 0, &ppvBits, 0, 0);
              ho = v29;
              if ( v29 )
              {
                v30 = SelectObject(v28, v29);
                BitBlt(v28, 0, 0, v17, cy, CompatibleDC, 0, 0, 0xCC0020u);
                GdiFlush();
                SelectObject(v28, v30);
                v31 = SelectObject(v16, Bitmap);
                if ( a6 )
                {
                  v32 = 8 * ((bottom + 7) / 8);
                  v33 = 0;
                  if ( cy > 0 )
                  {
                    do
                    {
                      v34 = 0;
                      if ( v17 > 0 )
                      {
                        do
                        {
                          v35 = v17 * v33 + v34;
                          if ( *((_BYTE *)ppvBits + 4 * v35 + 2)
                            || *((_BYTE *)ppvBits + 4 * v35)
                            || *((_BYTE *)ppvBits + 4 * v35 + 1) )
                          {
                            *((_BYTE *)ppvBits + 4 * v35 + 3) = 0x80;
                          }
                          ++v34;
                        }
                        while ( v34 < v17 );
                        v32 = 8 * ((bottom + 7) / 8);
                      }
                      ++v33;
                    }
                    while ( v33 < v32 );
                  }
                }
                SelectObject(v16, v31);
                v36 = ho;
                piconinfo.fIcon = 0;
                piconinfo.xHotspot = right / 2;
                piconinfo.hbmMask = Bitmap;
                piconinfo.hbmColor = (HBITMAP)ho;
                piconinfo.yHotspot = bottom / 2;
                *(&piconinfo.yHotspot + 1) = 0;
                v37 = CreateIconIndirect(&piconinfo);
                *((_QWORD *)v46 + 80) = v37;
                DeleteObject(v36);
                v42 = v37 == 0 ? 0x80004005 : 0;
              }
              DeleteDC(v28);
            }
          }
          SelectObject(CompatibleDC, v47);
          v20 = h;
        }
        DeleteObject(v20);
      }
      if ( Bitmap )
        DeleteObject(Bitmap);
      v7 = v42;
    }
    else if ( !v15 )
    {
      goto LABEL_45;
    }
    DeleteDC(v16);
    if ( !CompatibleDC )
    {
LABEL_45:
      ReleaseDC(0, v13);
      return v7;
    }
LABEL_44:
    DeleteDC(CompatibleDC);
    goto LABEL_45;
  }
  return v7;
}

```

## disassembly

```asm
0x1800afd9c  push    rbp
0x1800afd9e  push    rbx
0x1800afd9f  push    rsi
0x1800afda0  push    rdi
0x1800afda1  push    r12
0x1800afda3  push    r13
0x1800afda5  push    r14
0x1800afda7  push    r15
0x1800afda9  lea     rbp, [rsp-0Fh]
0x1800afdae  sub     rsp, 0E8h
0x1800afdb5  mov     rax, cs:__security_cookie
0x1800afdbc  xor     rax, rsp
0x1800afdbf  mov     [rbp+47h+var_48], rax
0x1800afdc3  mov     rdi, rcx
0x1800afdc6  mov     [rbp+47h+var_A8], rcx
0x1800afdca  mov     esi, 4Eh ; 'N'
0x1800afdcf  mov     r13d, 80004005h
0x1800afdd5  mov     ecx, esi; nIndex
0x1800afdd7  mov     [rbp+47h+var_C4], r13d
0x1800afddb  mov     ebx, r9d
0x1800afdde  mov     r14d, r8d
0x1800afde1  mov     r15d, edx
0x1800afde4  call    cs:__imp_GetSystemMetrics
0x1800afdea  cdq
0x1800afdeb  lea     r12d, [rsi-4Ch]
0x1800afdef  idiv    r12d
0x1800afdf2  cmp     r15d, eax
0x1800afdf5  jl      short loc_1800AFE06
0x1800afdf7  mov     ecx, esi; nIndex
0x1800afdf9  call    cs:__imp_GetSystemMetrics
0x1800afdff  cdq
0x1800afe00  idiv    r12d
0x1800afe03  mov     r15d, eax
0x1800afe06  cmp     [rbp+47h+arg_20], 0
0x1800afe0a  jz      short loc_1800AFE11
0x1800afe0c  mov     r14d, r15d
0x1800afe0f  jmp     short loc_1800AFE36
0x1800afe11  mov     esi, 4Fh ; 'O'
0x1800afe16  mov     ecx, esi; nIndex
0x1800afe18  call    cs:__imp_GetSystemMetrics
0x1800afe1e  cdq
0x1800afe1f  idiv    r12d
0x1800afe22  cmp     r14d, eax
0x1800afe25  jl      short loc_1800AFE36
0x1800afe27  mov     ecx, esi; nIndex
0x1800afe29  call    cs:__imp_GetSystemMetrics
0x1800afe2f  cdq
0x1800afe30  idiv    r12d
0x1800afe33  mov     r14d, eax
0x1800afe36  mov     rcx, [rdi+280h]; hCursor
0x1800afe3d  test    rcx, rcx
0x1800afe40  jz      short loc_1800AFE53
0x1800afe42  call    cs:__imp_DestroyCursor
0x1800afe48  mov     qword ptr [rdi+280h], 0
0x1800afe53  xor     ecx, ecx; hWnd
0x1800afe55  call    cs:__imp_GetDC
0x1800afe5b  mov     r12, rax
0x1800afe5e  test    rax, rax
0x1800afe61  jz      loc_1800B0259
0x1800afe67  mov     rcx, rax; hdc
0x1800afe6a  call    cs:__imp_CreateCompatibleDC
0x1800afe70  mov     rcx, r12; hdc
0x1800afe73  mov     rdi, rax
0x1800afe76  call    cs:__imp_CreateCompatibleDC
0x1800afe7c  mov     rsi, rax
0x1800afe7f  test    rdi, rdi
0x1800afe82  jz      loc_1800B027C
0x1800afe88  test    rax, rax
0x1800afe8b  jz      loc_1800B0245
0x1800afe91  lea     eax, [r15+2]
0x1800afe95  mov     r8d, 8
0x1800afe9b  mov     [rsp+120h+right], eax
0x1800afe9f  lea     ecx, [r14+2]
0x1800afea3  add     eax, 7
0x1800afea6  mov     [rsp+120h+bottom], ecx
0x1800afeaa  cdq
0x1800afeab  idiv    r8d
0x1800afeae  mov     r14d, eax
0x1800afeb1  lea     eax, [rcx+7]
0x1800afeb4  cdq
0x1800afeb5  shl     r14d, 3
0x1800afeb9  idiv    r8d
0x1800afebc  mov     edx, r14d; cx
0x1800afebf  mov     rcx, r12; hdc
0x1800afec2  mov     r15d, eax
0x1800afec5  shl     r15d, 3
0x1800afec9  mov     r8d, r15d; cy
0x1800afecc  mov     [rsp+120h+cy], r15d
0x1800afed1  call    cs:__imp_CreateCompatibleBitmap
0x1800afed7  mov     edx, r15d; nHeight
0x1800afeda  mov     [rsp+120h+lpBits], 0; lpBits
0x1800afee3  mov     [rbp+47h+h], rax
0x1800afee7  mov     ecx, r14d; nWidth
0x1800afeea  mov     eax, 1
0x1800afeef  mov     r9d, eax; nBitCount
0x1800afef2  mov     r8d, eax; nPlanes
0x1800afef5  call    cs:__imp_CreateBitmap
0x1800afefb  mov     r13, rax
0x1800afefe  mov     rax, [rbp+47h+h]
0x1800aff02  test    rax, rax
0x1800aff05  jz      loc_1800B0225
0x1800aff0b  test    r13, r13
0x1800aff0e  jz      loc_1800B021C
0x1800aff14  mov     rdx, rax; h
0x1800aff17  mov     rcx, rdi; hdc
0x1800aff1a  call    cs:__imp_SelectObject
0x1800aff20  cmp     [rbp+47h+arg_28], 0
0x1800aff24  mov     [rbp+47h+var_A0], rax
0x1800aff28  jz      short loc_1800AFF34
0x1800aff2a  test    ebx, ebx
0x1800aff2c  mov     eax, 10101h
0x1800aff31  cmovz   ebx, eax
0x1800aff34  mov     ecx, ebx; color
0x1800aff36  call    cs:__imp_CreateSolidBrush
0x1800aff3c  mov     rbx, rax
0x1800aff3f  test    rax, rax
0x1800aff42  jz      loc_1800B020B
0x1800aff48  mov     rdx, rax; h
0x1800aff4b  mov     rcx, rdi; hdc
0x1800aff4e  call    cs:__imp_SelectObject
0x1800aff54  mov     ecx, 6; i
0x1800aff59  mov     [rbp+47h+ho], rax
0x1800aff5d  call    cs:__imp_GetStockObject
0x1800aff63  mov     rdx, rax; h
0x1800aff66  mov     rcx, rdi; hdc
0x1800aff69  call    cs:__imp_SelectObject
0x1800aff6f  mov     r9d, [rsp+120h+right]; right
0x1800aff74  xor     r8d, r8d; top
0x1800aff77  xor     edx, edx; left
0x1800aff79  mov     [rbp+47h+ppvBits], rax
0x1800aff7d  mov     rcx, rdi; hdc
0x1800aff80  mov     eax, [rsp+120h+bottom]
0x1800aff84  mov     dword ptr [rsp+120h+lpBits], eax; bottom
0x1800aff88  cmp     [rbp+47h+arg_20], edx
0x1800aff8b  jz      short loc_1800AFF95
0x1800aff8d  call    cs:__imp_Ellipse
0x1800aff93  jmp     short loc_1800AFF9B
0x1800aff95  call    cs:__imp_Rectangle
0x1800aff9b  mov     rdx, [rbp+47h+ppvBits]; h
0x1800aff9f  mov     rcx, rdi; hdc
0x1800affa2  call    cs:__imp_SelectObject
0x1800affa8  mov     rdx, [rbp+47h+ho]; h
0x1800affac  mov     rcx, rdi; hdc
0x1800affaf  call    cs:__imp_SelectObject
0x1800affb5  mov     rcx, rbx; ho
0x1800affb8  call    cs:__imp_DeleteObject
0x1800affbe  mov     rdx, r13; h
0x1800affc1  mov     rcx, rsi; hdc
0x1800affc4  call    cs:__imp_SelectObject
0x1800affca  mov     r9d, r14d; w
0x1800affcd  mov     [rsp+120h+rop], 0FF0062h; rop
0x1800affd5  xor     r8d, r8d; y
0x1800affd8  mov     dword ptr [rsp+120h+lpBits], r15d; h
0x1800affdd  xor     edx, edx; x
0x1800affdf  mov     rcx, rsi; hdc
0x1800affe2  mov     rbx, rax
0x1800affe5  call    cs:__imp_PatBlt
0x1800affeb  mov     ecx, 4; i
0x1800afff0  call    cs:__imp_GetStockObject
0x1800afff6  mov     rdx, rax; h
0x1800afff9  mov     rcx, rsi; hdc
0x1800afffc  call    cs:__imp_SelectObject
0x1800b0002  mov     ecx, 7; i
0x1800b0007  mov     [rbp+47h+ppvBits], rax
0x1800b000b  call    cs:__imp_GetStockObject
0x1800b0011  mov     rdx, rax; h
0x1800b0014  mov     rcx, rsi; hdc
0x1800b0017  call    cs:__imp_SelectObject
0x1800b001d  mov     r9d, [rsp+120h+right]; right
0x1800b0022  xor     r8d, r8d; top
0x1800b0025  xor     edx, edx; left
0x1800b0027  mov     [rbp+47h+ho], rax
0x1800b002b  mov     rcx, rsi; hdc
0x1800b002e  mov     eax, [rsp+120h+bottom]
0x1800b0032  mov     dword ptr [rsp+120h+lpBits], eax; bottom
0x1800b0036  cmp     [rbp+47h+arg_20], edx
0x1800b0039  jz      short loc_1800B0043
0x1800b003b  call    cs:__imp_Ellipse
0x1800b0041  jmp     short loc_1800B0049
0x1800b0043  call    cs:__imp_Rectangle
0x1800b0049  mov     rdx, [rbp+47h+ho]; h
0x1800b004d  mov     rcx, rsi; hdc
0x1800b0050  call    cs:__imp_SelectObject
0x1800b0056  mov     rdx, [rbp+47h+ppvBits]; h
0x1800b005a  mov     rcx, rsi; hdc
0x1800b005d  call    cs:__imp_SelectObject
0x1800b0063  mov     rdx, rbx; h
0x1800b0066  mov     rcx, rsi; hdc
0x1800b0069  call    cs:__imp_SelectObject
0x1800b006f  xorps   xmm0, xmm0
0x1800b0072  mov     [rbp+47h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800b0079  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biWidth], xmm0
0x1800b007d  xor     eax, eax
0x1800b007f  mov     [rbp+47h+pbmi.bmiHeader.biWidth], r14d
0x1800b0083  mov     rcx, rdi; hdc
0x1800b0086  mov     [rbp+47h+pbmi.bmiHeader.biHeight], r15d
0x1800b008a  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biPlanes], 200001h
0x1800b0092  xor     ebx, ebx
0x1800b0094  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800b0098  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biClrImportant], rax
0x1800b009c  call    cs:__imp_CreateCompatibleDC
0x1800b00a2  mov     r15, rax
0x1800b00a5  test    rax, rax
0x1800b00a8  jz      loc_1800B020B
0x1800b00ae  mov     [rsp+120h+rop], ebx; offset
0x1800b00b2  lea     r9, [rbp+47h+ppvBits]; ppvBits
0x1800b00b6  xor     r8d, r8d; usage
0x1800b00b9  mov     [rsp+120h+lpBits], rbx; hSection
0x1800b00be  lea     rdx, [rbp+47h+pbmi]; pbmi
0x1800b00c2  mov     [rbp+47h+ppvBits], rbx
0x1800b00c6  mov     rcx, rax; hdc
0x1800b00c9  call    cs:__imp_CreateDIBSection
0x1800b00cf  mov     [rbp+47h+ho], rax
0x1800b00d3  test    rax, rax
0x1800b00d6  jz      loc_1800B0202
0x1800b00dc  mov     rdx, rax; h
0x1800b00df  mov     rcx, r15; hdc
0x1800b00e2  call    cs:__imp_SelectObject
0x1800b00e8  mov     [rsp+120h+var_E0], 0CC0020h; rop
0x1800b00f0  mov     r9d, r14d; cx
0x1800b00f3  mov     [rsp+120h+y1], 0; y1
0x1800b00fb  mov     rbx, rax
0x1800b00fe  mov     eax, [rsp+120h+cy]
0x1800b0102  xor     r8d, r8d; y
0x1800b0105  mov     [rsp+120h+x1], 0; x1
0x1800b010d  xor     edx, edx; x
0x1800b010f  mov     qword ptr [rsp+120h+rop], rdi; hdcSrc
0x1800b0114  mov     rcx, r15; hdc
0x1800b0117  mov     dword ptr [rsp+120h+lpBits], eax; cy
0x1800b011b  call    cs:__imp_BitBlt
0x1800b0121  call    cs:__imp_GdiFlush
0x1800b0127  mov     rdx, rbx; h
0x1800b012a  mov     rcx, r15; hdc
0x1800b012d  call    cs:__imp_SelectObject
0x1800b0133  mov     rdx, r13; h
0x1800b0136  mov     rcx, rsi; hdc
0x1800b0139  call    cs:__imp_SelectObject
0x1800b013f  xor     ebx, ebx
0x1800b0141  mov     r11, rax
0x1800b0144  cmp     [rbp+47h+arg_28], ebx
0x1800b0147  jz      short loc_1800B0199
0x1800b0149  mov     r10d, [rsp+120h+cy]
0x1800b014e  mov     r8d, ebx
0x1800b0151  test    r10d, r10d
0x1800b0154  jle     short loc_1800B0199
0x1800b0156  mov     edx, ebx
0x1800b0158  test    r14d, r14d
0x1800b015b  jle     short loc_1800B0191
0x1800b015d  mov     r9d, r8d
0x1800b0160  imul    r9d, r14d
0x1800b0164  lea     eax, [r9+rdx]
0x1800b0168  movsxd  rcx, eax
0x1800b016b  mov     rax, [rbp+47h+ppvBits]
0x1800b016f  cmp     [rax+rcx*4+2], bl
0x1800b0173  jnz     short loc_1800B0180
0x1800b0175  cmp     [rax+rcx*4], bl
0x1800b0178  jnz     short loc_1800B0180
0x1800b017a  cmp     [rax+rcx*4+1], bl
0x1800b017e  jz      short loc_1800B0185
0x1800b0180  mov     byte ptr [rax+rcx*4+3], 80h
0x1800b0185  inc     edx
0x1800b0187  cmp     edx, r14d
0x1800b018a  jl      short loc_1800B0164
0x1800b018c  mov     r10d, [rsp+120h+cy]
0x1800b0191  inc     r8d
0x1800b0194  cmp     r8d, r10d
0x1800b0197  jl      short loc_1800B0156
0x1800b0199  mov     rdx, r11; h
0x1800b019c  mov     rcx, rsi; hdc
0x1800b019f  call    cs:__imp_SelectObject
0x1800b01a5  mov     eax, [rsp+120h+right]
0x1800b01a9  mov     ecx, 2
0x1800b01ae  mov     r14, [rbp+47h+ho]
0x1800b01b2  cdq
0x1800b01b3  idiv    ecx
0x1800b01b5  mov     [rbp+47h+piconinfo.fIcon], ebx
0x1800b01b8  mov     [rbp+47h+piconinfo.xHotspot], eax
0x1800b01bb  mov     eax, [rsp+120h+bottom]
0x1800b01bf  cdq
0x1800b01c0  mov     [rbp+47h+piconinfo.hbmMask], r13
0x1800b01c4  idiv    ecx
0x1800b01c6  lea     rcx, [rbp+47h+piconinfo]; piconinfo
0x1800b01ca  mov     [rbp+47h+piconinfo.hbmColor], r14
0x1800b01ce  mov     [rbp+47h+piconinfo.yHotspot], eax
0x1800b01d1  xor     eax, eax
0x1800b01d3  mov     dword ptr [rbp+47h+piconinfo+0Ch], eax
0x1800b01d6  call    cs:__imp_CreateIconIndirect
0x1800b01dc  mov     rbx, rax
0x1800b01df  mov     rcx, r14; ho
0x1800b01e2  mov     rax, [rbp+47h+var_A8]
0x1800b01e6  mov     [rax+280h], rbx
0x1800b01ed  call    cs:__imp_DeleteObject
0x1800b01f3  neg     rbx
0x1800b01f6  sbb     eax, eax
0x1800b01f8  not     eax
0x1800b01fa  and     eax, 80004005h
0x1800b01ff  mov     [rbp+47h+var_C4], eax
0x1800b0202  mov     rcx, r15; hdc
0x1800b0205  call    cs:__imp_DeleteDC
0x1800b020b  mov     rdx, [rbp+47h+var_A0]; h
  ... truncated ...
```
