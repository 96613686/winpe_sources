# CTravelBand::_SetButtonImagesThemedMode(void)

- ea: `0x18003fbc8`
- end: `0x18003ff3e`
- name: `?_SetButtonImagesThemedMode@CTravelBand@@AEAAXXZ`
- size: `886`
- prototype: `void __fastcall(CTravelBand *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003f93c`

## callees

- `0x18003f74c`
- `0x18003fbc8`
- `0x18003ff44`
- `0x180040ab0`
- `0x1800471dc`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003feca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ff15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003feca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ff15`
- `USER32!SendMessageW` at `0x18003fe31`
- `USER32!SendMessageW` at `0x18003fe31`
- `USER32!FillRect` at `0x18003fd64`
- `USER32!FillRect` at `0x18003fd64`
- `GDI32!DeleteDC` at `0x18003fe61`
- `GDI32!DeleteDC` at `0x18003fe61`
- `GDI32!DeleteObject` at `0x18003fdde`
- `GDI32!DeleteObject` at `0x18003fdde`
- `GDI32!SelectObject` at `0x18003fd49`
- `GDI32!SelectObject` at `0x18003fd9a`
- `GDI32!SelectObject` at `0x18003fd49`
- `GDI32!SelectObject` at `0x18003fd9a`
- `GDI32!GetStockObject` at `0x18003fd54`
- `GDI32!GetStockObject` at `0x18003fd54`
- `GDI32!CreateDIBSection` at `0x18003fd2d`
- `GDI32!CreateDIBSection` at `0x18003fd2d`
- `UxTheme!DrawThemeBackground` at `0x18003fd8c`
- `UxTheme!DrawThemeBackground` at `0x18003fd8c`
- `UxTheme!GetThemePartSize` at `0x18003fc45`
- `UxTheme!GetThemePartSize` at `0x18003fc45`

## string_xrefs

- `0x18003febc`: `ImageList_Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTravelBand::_SetButtonImagesThemedMode(CTravelBand *this)
{
  HDC ScreenMemoryDC; // rbx
  unsigned int cx; // r14d
  unsigned int cy; // esi
  int i; // r13d
  int v6; // edi
  struct _IMAGELIST *v7; // r12
  int v8; // eax
  int j; // esi
  int v10; // r14d
  HBITMAP v11; // rax
  HBITMAP v12; // rdi
  HGDIOBJ v13; // r14
  HBRUSH StockObject; // rax
  HRESULT v15; // esi
  __int64 v16; // rcx
  FARPROC ProcAddress; // rax
  UINT v18; // edx
  struct _IMAGELIST *v19; // rax
  LONG v20; // [rsp+40h] [rbp-69h]
  int v21; // [rsp+44h] [rbp-65h]
  LONG v22; // [rsp+48h] [rbp-61h]
  int v23; // [rsp+50h] [rbp-59h]
  SIZE psz; // [rsp+58h] [rbp-51h] BYREF
  void *ppvBits[3]; // [rsp+60h] [rbp-49h] BYREF
  RECT rc; // [rsp+78h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+88h] [rbp-21h] BYREF

  if ( *((_QWORD *)this + 16) )
  {
    ScreenMemoryDC = CreateScreenMemoryDC();
    ppvBits[1] = ScreenMemoryDC;
    if ( ScreenMemoryDC )
    {
      psz = 0;
      GetThemePartSize(*((HTHEME *)this + 22), ScreenMemoryDC, 1, 1, 0, TS_DRAW, &psz);
      cx = psz.cx;
      v22 = psz.cx;
      cy = psz.cy;
      v20 = psz.cy;
      CTravelBand::ScaleAndSetPadding(this, psz.cx, psz.cy);
      for ( i = 1; i <= 4; ++i )
      {
        v6 = -(*((_BYTE *)this + 120) != 0);
        if ( qword_1802913A8 == (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))-1LL )
        {
          if ( g_hinstCC || (DelayLoadCC(32), g_hinstCC) )
            qword_1802913A8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))GetProcAddress(
                                                                                                g_hinstCC,
                                                                                                "ImageList_Create");
          else
            qword_1802913A8 = 0;
        }
        if ( qword_1802913A8 )
        {
          v7 = (struct _IMAGELIST *)qword_1802913A8(cx, cy, 32, (unsigned int)(v6 + 2), 0);
          if ( v7 )
          {
            v8 = 2 - (*((_BYTE *)this + 120) != 0);
            v23 = v8;
            for ( j = 1; ; ++j )
            {
              v21 = j;
              if ( j > v8 )
                break;
              memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
              pbmi.bmiHeader.biSize = 40;
              pbmi.bmiHeader.biWidth = cx;
              pbmi.bmiHeader.biHeight = v20;
              *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
              *(_QWORD *)&rc.left = 0;
              rc.right = cx;
              rc.bottom = v20;
              v10 = -1;
              ppvBits[0] = 0;
              v11 = CreateDIBSection(ScreenMemoryDC, &pbmi, 0, ppvBits, 0, 0);
              v12 = v11;
              ppvBits[2] = v11;
              if ( v11 )
              {
                v13 = SelectObject(ScreenMemoryDC, v11);
                StockObject = (HBRUSH)GetStockObject(0);
                FillRect(ScreenMemoryDC, &rc, StockObject);
                v15 = DrawThemeBackground(*((HTHEME *)this + 22), ScreenMemoryDC, j, i, &rc, 0);
                SelectObject(ScreenMemoryDC, v13);
                if ( v15 < 0 )
                {
                  v10 = -1;
                }
                else
                {
                  ProcAddress = (FARPROC)qword_180291388;
                  if ( qword_180291388 == -1 )
                  {
                    if ( g_hinstCC || (DelayLoadCC(v16), g_hinstCC) )
                      ProcAddress = GetProcAddress(g_hinstCC, "ImageList_Add");
                    else
                      ProcAddress = 0;
                    qword_180291388 = (__int64)ProcAddress;
                  }
                  if ( ProcAddress )
                    v10 = ((__int64 (__fastcall *)(struct _IMAGELIST *, HBITMAP, _QWORD))ProcAddress)(v7, v12, 0);
                  else
                    v10 = -1;
                }
                j = v21;
              }
              if ( v12 )
                DeleteObject(v12);
              if ( v10 < 0 )
              {
                ImageList_Destroy(v7);
                cx = v22;
                goto LABEL_27;
              }
              v8 = v23;
              cx = v22;
            }
            switch ( i )
            {
              case 1:
                v18 = 1072;
                break;
              case 2:
                v18 = 1076;
                break;
              case 3:
                v18 = 1128;
                break;
              case 4:
                v18 = 1078;
                break;
              default:
                goto LABEL_27;
            }
            v19 = (struct _IMAGELIST *)SendMessageW(*((HWND *)this + 16), v18, 0, (LPARAM)v7);
            if ( v19 )
              ImageList_Destroy(v19);
LABEL_27:
            cy = v20;
          }
        }
      }
    }
    if ( ScreenMemoryDC )
      DeleteDC(ScreenMemoryDC);
  }
}

```

## disassembly

```asm
0x18003fbc8  push    rbp
0x18003fbca  push    rbx
0x18003fbcb  push    rsi
0x18003fbcc  push    rdi
0x18003fbcd  push    r12
0x18003fbcf  push    r13
0x18003fbd1  push    r14
0x18003fbd3  push    r15
0x18003fbd5  lea     rbp, [rsp-1Fh]
0x18003fbda  sub     rsp, 0C8h
0x18003fbe1  mov     rax, cs:__security_cookie
0x18003fbe8  xor     rax, rsp
0x18003fbeb  mov     [rbp+57h+var_48], rax
0x18003fbef  mov     r15, rcx
0x18003fbf2  xor     edi, edi
0x18003fbf4  cmp     [rcx+80h], rdi
0x18003fbfb  jz      loc_18003FE67
0x18003fc01  call    ?CreateScreenMemoryDC@@YAPEAUHDC__@@XZ; CreateScreenMemoryDC(void)
0x18003fc06  mov     rbx, rax
0x18003fc09  mov     [rbp+57h+var_98], rax
0x18003fc0d  test    rax, rax
0x18003fc10  jz      loc_18003FE59
0x18003fc16  mov     qword ptr [rbp+57h+var_A8.cx], rdi
0x18003fc1a  lea     rax, [rbp+57h+var_A8]
0x18003fc1e  mov     [rsp+100h+psz], rax; psz
0x18003fc23  mov     [rsp+100h+eSize], 2; eSize
0x18003fc2b  mov     [rsp+100h+prc], rdi; prc
0x18003fc30  mov     edi, 1
0x18003fc35  mov     r9d, edi; iStateId
0x18003fc38  mov     r8d, edi; iPartId
0x18003fc3b  mov     rdx, rbx; hdc
0x18003fc3e  mov     rcx, [r15+0B0h]; hTheme
0x18003fc45  call    cs:__imp_GetThemePartSize
0x18003fc4b  mov     r14d, [rbp+57h+var_A8.cx]
0x18003fc4f  mov     [rbp+57h+var_B8], r14d
0x18003fc53  mov     esi, [rbp+57h+var_A8.cy]
0x18003fc56  mov     [rbp+57h+var_C0], esi
0x18003fc59  mov     r8d, esi; unsigned int
0x18003fc5c  mov     edx, r14d; unsigned int
0x18003fc5f  mov     rcx, r15; this
0x18003fc62  call    ?ScaleAndSetPadding@CTravelBand@@AEAAXKK@Z; CTravelBand::ScaleAndSetPadding(ulong,ulong)
0x18003fc67  mov     r13d, edi
0x18003fc6a  lea     ecx, [rdi+1Fh]
0x18003fc6d  mov     al, [r15+78h]
0x18003fc71  neg     al
0x18003fc73  sbb     edi, edi
0x18003fc75  cmp     cs:qword_1802913A8, 0FFFFFFFFFFFFFFFFh
0x18003fc7d  jz      loc_18003FEA3
0x18003fc83  mov     rax, cs:qword_1802913A8
0x18003fc8a  test    rax, rax
0x18003fc8d  jz      loc_18003FE47
0x18003fc93  mov     dword ptr [rsp+100h+prc], 0
0x18003fc9b  lea     r9d, [rdi+2]
0x18003fc9f  mov     r8d, ecx
0x18003fca2  mov     edx, esi
0x18003fca4  mov     ecx, r14d
0x18003fca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcac  mov     r12, rax
0x18003fcaf  xor     edi, edi
0x18003fcb1  test    rax, rax
0x18003fcb4  jz      loc_18003FE47
0x18003fcba  mov     cl, [r15+78h]
0x18003fcbe  neg     cl
0x18003fcc0  sbb     eax, eax
0x18003fcc2  add     eax, 2
0x18003fcc5  mov     [rbp+57h+var_B0], eax
0x18003fcc8  lea     esi, [rdi+1]
0x18003fccb  mov     [rbp+57h+var_BC], esi
0x18003fcce  cmp     esi, eax
0x18003fcd0  jg      loc_18003FDFD
0x18003fcd6  xorps   xmm0, xmm0
0x18003fcd9  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18003fcde  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rdi
0x18003fce2  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18003fce9  mov     [rbp+57h+pbmi.bmiHeader.biWidth], r14d
0x18003fced  mov     eax, [rbp+57h+var_C0]
0x18003fcf0  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18003fcf3  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18003fcfb  mov     qword ptr [rbp+57h+rc.left], 0
0x18003fd03  mov     [rbp+57h+rc.right], r14d
0x18003fd07  mov     [rbp+57h+rc.bottom], eax
0x18003fd0a  or      r14d, 0FFFFFFFFh
0x18003fd0e  mov     [rbp+57h+var_B4], r14d
0x18003fd12  mov     [rbp+57h+ppvBits], rdi
0x18003fd16  mov     [rsp+100h+eSize], edi; offset
0x18003fd1a  mov     [rsp+100h+prc], rdi; hSection
0x18003fd1f  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18003fd23  xor     r8d, r8d; usage
0x18003fd26  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18003fd2a  mov     rcx, rbx; hdc
0x18003fd2d  call    cs:__imp_CreateDIBSection
0x18003fd33  mov     rdi, rax
0x18003fd36  mov     [rbp+57h+var_90], rax
0x18003fd3a  test    rax, rax
0x18003fd3d  jz      loc_18003FDD6
0x18003fd43  mov     rdx, rax; h
0x18003fd46  mov     rcx, rbx; hdc
0x18003fd49  call    cs:__imp_SelectObject
0x18003fd4f  mov     r14, rax
0x18003fd52  xor     ecx, ecx; i
0x18003fd54  call    cs:__imp_GetStockObject
0x18003fd5a  mov     r8, rax; hbr
0x18003fd5d  lea     rdx, [rbp+57h+rc]; lprc
0x18003fd61  mov     rcx, rbx; hDC
0x18003fd64  call    cs:__imp_FillRect
0x18003fd6a  mov     qword ptr [rsp+100h+eSize], 0; pClipRect
0x18003fd73  lea     rax, [rbp+57h+rc]
0x18003fd77  mov     [rsp+100h+prc], rax; pRect
0x18003fd7c  mov     r9d, r13d; iStateId
0x18003fd7f  mov     r8d, esi; iPartId
0x18003fd82  mov     rdx, rbx; hdc
0x18003fd85  mov     rcx, [r15+0B0h]; hTheme
0x18003fd8c  call    cs:__imp_DrawThemeBackground
0x18003fd92  mov     esi, eax
0x18003fd94  mov     rdx, r14; h
0x18003fd97  mov     rcx, rbx; hdc
0x18003fd9a  call    cs:__imp_SelectObject
0x18003fda0  test    esi, esi
0x18003fda2  js      loc_18003FF2B
0x18003fda8  mov     rax, cs:qword_180291388
0x18003fdaf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003fdb3  jz      loc_18003FEEE
0x18003fdb9  test    rax, rax
0x18003fdbc  jz      loc_18003FF34
0x18003fdc2  xor     r8d, r8d
0x18003fdc5  mov     rdx, rdi
0x18003fdc8  mov     rcx, r12
0x18003fdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdd0  mov     r14d, eax
0x18003fdd3  mov     esi, [rbp+57h+var_BC]
0x18003fdd6  test    rdi, rdi
0x18003fdd9  jz      short loc_18003FDE4
0x18003fddb  mov     rcx, rdi; ho
0x18003fdde  call    cs:__imp_DeleteObject
0x18003fde4  xor     edi, edi
0x18003fde6  test    r14d, r14d
0x18003fde9  js      loc_18003FE8E
0x18003fdef  inc     esi
0x18003fdf1  mov     eax, [rbp+57h+var_B0]
0x18003fdf4  mov     r14d, [rbp+57h+var_B8]
0x18003fdf8  jmp     loc_18003FCCB
0x18003fdfd  mov     ecx, r13d
0x18003fe00  sub     ecx, 1
0x18003fe03  jz      short loc_18003FE1F
0x18003fe05  sub     ecx, 1
0x18003fe08  jz      loc_18003FE9C
0x18003fe0e  sub     ecx, 1
0x18003fe11  jz      short loc_18003FE87
0x18003fe13  cmp     ecx, 1
0x18003fe16  jnz     short loc_18003FE44
0x18003fe18  mov     edx, 436h
0x18003fe1d  jmp     short loc_18003FE24
0x18003fe1f  mov     edx, 430h; Msg
0x18003fe24  mov     r9, r12; lParam
0x18003fe27  xor     r8d, r8d; wParam
0x18003fe2a  mov     rcx, [r15+80h]; hWnd
0x18003fe31  call    cs:__imp_SendMessageW
0x18003fe37  test    rax, rax
0x18003fe3a  jz      short loc_18003FE44
0x18003fe3c  mov     rcx, rax; himl
0x18003fe3f  call    ImageList_Destroy
0x18003fe44  mov     esi, [rbp+57h+var_C0]
0x18003fe47  inc     r13d
0x18003fe4a  cmp     r13d, 4
0x18003fe4e  mov     ecx, 20h ; ' '
0x18003fe53  jle     loc_18003FC6D
0x18003fe59  test    rbx, rbx
0x18003fe5c  jz      short loc_18003FE67
0x18003fe5e  mov     rcx, rbx; hdc
0x18003fe61  call    cs:__imp_DeleteDC
0x18003fe67  mov     rcx, [rbp+57h+var_48]
0x18003fe6b  xor     rcx, rsp; StackCookie
0x18003fe6e  call    __security_check_cookie
0x18003fe73  add     rsp, 0C8h
0x18003fe7a  pop     r15
0x18003fe7c  pop     r14
0x18003fe7e  pop     r13
0x18003fe80  pop     r12
0x18003fe82  pop     rdi
0x18003fe83  pop     rsi
0x18003fe84  pop     rbx
0x18003fe85  pop     rbp
0x18003fe86  retn
0x18003fe87  mov     edx, 468h
0x18003fe8c  jmp     short loc_18003FE24
0x18003fe8e  mov     rcx, r12; himl
0x18003fe91  call    ImageList_Destroy
0x18003fe96  mov     r14d, [rbp+57h+var_B8]
0x18003fe9a  jmp     short loc_18003FE44
0x18003fe9c  mov     edx, 434h
0x18003fea1  jmp     short loc_18003FE24
0x18003fea3  cmp     cs:g_hinstCC, 0
0x18003feab  jnz     short loc_18003FEBC
0x18003fead  call    DelayLoadCC
0x18003feb2  cmp     cs:g_hinstCC, 0
0x18003feba  jz      short loc_18003FEE1
0x18003febc  lea     rdx, aImagelistCreat; "ImageList_Create"
0x18003fec3  mov     rcx, cs:g_hinstCC; hModule
0x18003feca  call    cs:__imp_GetProcAddress
0x18003fed0  mov     cs:qword_1802913A8, rax
0x18003fed7  mov     ecx, 20h ; ' '
0x18003fedc  jmp     loc_18003FC83
0x18003fee1  mov     cs:qword_1802913A8, 0
0x18003feec  jmp     short loc_18003FED7
0x18003feee  cmp     cs:g_hinstCC, 0
0x18003fef6  jnz     short loc_18003FF07
0x18003fef8  call    DelayLoadCC
0x18003fefd  cmp     cs:g_hinstCC, 0
0x18003ff05  jz      short loc_18003FF27
0x18003ff07  lea     rdx, aImagelistAdd; "ImageList_Add"
0x18003ff0e  mov     rcx, cs:g_hinstCC; hModule
0x18003ff15  call    cs:__imp_GetProcAddress
0x18003ff1b  mov     cs:qword_180291388, rax
0x18003ff22  jmp     loc_18003FDB9
0x18003ff27  xor     eax, eax
0x18003ff29  jmp     short loc_18003FF1B
0x18003ff2b  mov     r14d, [rbp+57h+var_B4]
0x18003ff2f  jmp     loc_18003FDD3
0x18003ff34  or      r14d, 0FFFFFFFFh
0x18003ff38  jmp     loc_18003FDD3
```
