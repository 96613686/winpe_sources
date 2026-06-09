# InitDropdownFonts(void)

- ea: `0x180106af4`
- end: `0x180106dcc`
- name: `?InitDropdownFonts@@YAJXZ`
- size: `728`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18023af3c`
- `0x180308d2c`

## callees

- `0x1800e15d0`
- `0x1800e6178`
- `0x180105a74`
- `0x18010682c`
- `0x180106af4`
- `0x180144ac4`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbscpy_s` at `0x180106c30`
- `MSVCR100!_mbscpy_s` at `0x180106c30`
- `KERNEL32!MulDiv` at `0x180106c15`
- `KERNEL32!MulDiv` at `0x180106c15`
- `USER32!GetDC` at `0x180106b66`
- `USER32!GetDC` at `0x180106b66`
- `USER32!ReleaseDC` at `0x180106dad`
- `USER32!ReleaseDC` at `0x180106dad`
- `GDI32!GetTextMetricsA` at `0x180106cef`
- `GDI32!GetTextMetricsA` at `0x180106cef`
- `GDI32!SelectObject` at `0x180106cc7`
- `GDI32!SelectObject` at `0x180106d98`
- `GDI32!SelectObject` at `0x180106cc7`
- `GDI32!SelectObject` at `0x180106d98`
- `GDI32!CreateFontIndirectA` at `0x180106c43`
- `GDI32!CreateFontIndirectA` at `0x180106c86`
- `GDI32!CreateFontIndirectA` at `0x180106c43`
- `GDI32!CreateFontIndirectA` at `0x180106c86`
- `GDI32!DeleteObject` at `0x180106d35`
- `GDI32!DeleteObject` at `0x180106d66`
- `GDI32!DeleteObject` at `0x180106d35`
- `GDI32!DeleteObject` at `0x180106d66`

## pseudocode

```c
__int64 InitDropdownFonts(void)
{
  int v1; // eax
  int FontNameAndHeightOfStrid; // [rsp+20h] [rbp-C0h]
  __int64 v3; // [rsp+28h] [rbp-B8h]
  HDC hdc; // [rsp+30h] [rbp-B0h]
  HGDIOBJ h; // [rsp+38h] [rbp-A8h]
  int nNumber; // [rsp+40h] [rbp-A0h] BYREF
  unsigned __int8 *Src; // [rsp+48h] [rbp-98h] BYREF
  HFONT v8; // [rsp+50h] [rbp-90h]
  HFONT v9; // [rsp+58h] [rbp-88h]
  LOGFONTA lf; // [rsp+60h] [rbp-80h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+A0h] [rbp-40h] BYREF

  v3 = *((_QWORD *)PebappCur() + 1);
  Src = 0;
  h = 0;
  if ( *(_QWORD *)(v3 + 1016) && *(_QWORD *)(v3 + 1008) )
    return 0;
  hdc = GetDC(0);
  if ( hdc )
  {
    lf.lfWidth = 0;
    lf.lfEscapement = 0;
    lf.lfOrientation = 0;
    lf.lfItalic = 0;
    lf.lfUnderline = 0;
    lf.lfStrikeOut = 0;
    lf.lfOutPrecision = 0;
    lf.lfClipPrecision = 0;
    lf.lfQuality = 2;
    lf.lfPitchAndFamily = 0;
    lf.lfCharSet = GetCharset();
    FontNameAndHeightOfStrid = GetFontNameAndHeightOfStrid(0xDECCu, 0xDECDu, (char **)&Src, &nNumber);
    if ( FontNameAndHeightOfStrid >= 0 )
    {
      v1 = DPIMGR::DpiY((DPIMGR *)g_dpiMgr);
      lf.lfHeight = -MulDiv(nNumber, v1, 72);
      _mbscpy_s((unsigned __int8 *)lf.lfFaceName, 0x20u, Src);
      lf.lfWeight = 300;
      v8 = CreateFontIndirectA(&lf);
      *(_QWORD *)(v3 + 1016) = v8;
      if ( v8 )
      {
        lf.lfWeight = 700;
        v9 = CreateFontIndirectA(&lf);
        *(_QWORD *)(v3 + 1008) = v9;
        if ( v9 )
        {
          h = SelectObject(hdc, *(HGDIOBJ *)(v3 + 1016));
          if ( h )
          {
            if ( GetTextMetricsA(hdc, &tm) )
              *(_DWORD *)(v3 + 1024) = tm.tmAveCharWidth;
            else
              FontNameAndHeightOfStrid = -2147024882;
          }
          else
          {
            FontNameAndHeightOfStrid = -2147024882;
          }
        }
        else
        {
          FontNameAndHeightOfStrid = -2147024882;
        }
      }
      else
      {
        FontNameAndHeightOfStrid = -2147024882;
      }
    }
  }
  else
  {
    FontNameAndHeightOfStrid = -2147024882;
  }
  if ( FontNameAndHeightOfStrid < 0 )
  {
    if ( *(_QWORD *)(v3 + 1016) )
    {
      DeleteObject(*(HGDIOBJ *)(v3 + 1016));
      *(_QWORD *)(v3 + 1016) = 0;
    }
    if ( *(_QWORD *)(v3 + 1008) )
    {
      DeleteObject(*(HGDIOBJ *)(v3 + 1008));
      *(_QWORD *)(v3 + 1008) = 0;
    }
  }
  SysFreeStringA(Src);
  if ( h )
    SelectObject(hdc, h);
  if ( hdc )
    ReleaseDC(0, hdc);
  return (unsigned int)FontNameAndHeightOfStrid;
}

```

## disassembly

```asm
0x180106af4  push    rbp
0x180106af6  mov     rbp, rsp
0x180106af9  sub     rsp, 0E0h
0x180106b00  mov     rax, cs:__security_cookie
0x180106b07  xor     rax, rsp
0x180106b0a  mov     [rbp+var_8], rax
0x180106b0e  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x180106b13  mov     rax, [rax+8]
0x180106b17  mov     [rsp+0E0h+var_B8], rax
0x180106b1c  mov     [rsp+0E0h+var_C0], 0
0x180106b24  mov     [rsp+0E0h+Src], 0
0x180106b2d  mov     [rsp+0E0h+hdc], 0
0x180106b36  mov     [rsp+0E0h+h], 0
0x180106b3f  mov     rax, [rsp+0E0h+var_B8]
0x180106b44  cmp     qword ptr [rax+3F8h], 0
0x180106b4c  jz      short loc_180106B64
0x180106b4e  mov     rax, [rsp+0E0h+var_B8]
0x180106b53  cmp     qword ptr [rax+3F0h], 0
0x180106b5b  jz      short loc_180106B64
0x180106b5d  xor     eax, eax
0x180106b5f  jmp     loc_180106DB7
0x180106b64  xor     ecx, ecx; hWnd
0x180106b66  call    cs:__imp_GetDC
0x180106b6c  mov     [rsp+0E0h+hdc], rax
0x180106b71  cmp     [rsp+0E0h+hdc], 0
0x180106b77  jnz     short loc_180106B8B
0x180106b79  mov     [rsp+0E0h+var_C0], 8007000Eh
0x180106b81  jmp     loc_180106D13
0x180106b86  jmp     loc_180106D13
0x180106b8b  mov     [rsp+0E0h+lf.lfWidth], 0
0x180106b93  mov     [rsp+0E0h+lf.lfEscapement], 0
0x180106b9b  mov     [rsp+0E0h+lf.lfOrientation], 0
0x180106ba3  mov     [rsp+0E0h+lf.lfItalic], 0
0x180106ba8  mov     [rsp+0E0h+lf.lfUnderline], 0
0x180106bad  mov     [rsp+0E0h+lf.lfStrikeOut], 0
0x180106bb2  mov     [rsp+0E0h+lf.lfOutPrecision], 0
0x180106bb7  mov     [rsp+0E0h+lf.lfClipPrecision], 0
0x180106bbc  mov     [rsp+0E0h+lf.lfQuality], 2
0x180106bc1  mov     [rsp+0E0h+lf.lfPitchAndFamily], 0
0x180106bc6  call    ?GetCharset@@YAEXZ; GetCharset(void)
0x180106bcb  mov     [rsp+0E0h+lf.lfCharSet], al
0x180106bcf  lea     r9, [rsp+0E0h+nNumber]; int *
0x180106bd4  lea     r8, [rsp+0E0h+Src]; char **
0x180106bd9  mov     edx, 0DECDh; unsigned int
0x180106bde  mov     ecx, 0DECCh; unsigned int
0x180106be3  call    ?GetFontNameAndHeightOfStrid@@YAJIIPEAPEADPEAH@Z; GetFontNameAndHeightOfStrid(uint,uint,char * *,int *)
0x180106be8  mov     [rsp+0E0h+var_C0], eax
0x180106bec  cmp     [rsp+0E0h+var_C0], 0
0x180106bf1  jge     short loc_180106BFD
0x180106bf3  jmp     loc_180106D13
0x180106bf8  jmp     loc_180106D13
0x180106bfd  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180106c04  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x180106c09  mov     r8d, 48h ; 'H'; nDenominator
0x180106c0f  mov     edx, eax; nNumerator
0x180106c11  mov     ecx, [rsp+0E0h+nNumber]; nNumber
0x180106c15  call    cs:__imp_MulDiv
0x180106c1b  neg     eax
0x180106c1d  mov     [rsp+0E0h+lf.lfHeight], eax
0x180106c21  mov     r8, [rsp+0E0h+Src]; Src
0x180106c26  mov     edx, 20h ; ' '; SizeInBytes
0x180106c2b  lea     rcx, [rsp+0E0h+lf.lfFaceName]; Dst
0x180106c30  call    cs:__imp__mbscpy_s
0x180106c36  mov     [rsp+0E0h+lf.lfWeight], 12Ch
0x180106c3e  lea     rcx, [rsp+0E0h+lf]; lplf
0x180106c43  call    cs:__imp_CreateFontIndirectA
0x180106c49  mov     [rsp+0E0h+var_90], rax
0x180106c4e  mov     rax, [rsp+0E0h+var_B8]
0x180106c53  mov     rcx, [rsp+0E0h+var_90]
0x180106c58  mov     [rax+3F8h], rcx
0x180106c5f  cmp     [rsp+0E0h+var_90], 0
0x180106c65  jnz     short loc_180106C79
0x180106c67  mov     [rsp+0E0h+var_C0], 8007000Eh
0x180106c6f  jmp     loc_180106D13
0x180106c74  jmp     loc_180106D13
0x180106c79  mov     [rsp+0E0h+lf.lfWeight], 2BCh
0x180106c81  lea     rcx, [rsp+0E0h+lf]; lplf
0x180106c86  call    cs:__imp_CreateFontIndirectA
0x180106c8c  mov     [rsp+0E0h+var_88], rax
0x180106c91  mov     rax, [rsp+0E0h+var_B8]
0x180106c96  mov     rcx, [rsp+0E0h+var_88]
0x180106c9b  mov     [rax+3F0h], rcx
0x180106ca2  cmp     [rsp+0E0h+var_88], 0
0x180106ca8  jnz     short loc_180106CB6
0x180106caa  mov     [rsp+0E0h+var_C0], 8007000Eh
0x180106cb2  jmp     short loc_180106D13
0x180106cb4  jmp     short loc_180106D13
0x180106cb6  mov     rax, [rsp+0E0h+var_B8]
0x180106cbb  mov     rdx, [rax+3F8h]; h
0x180106cc2  mov     rcx, [rsp+0E0h+hdc]; hdc
0x180106cc7  call    cs:__imp_SelectObject
0x180106ccd  mov     [rsp+0E0h+h], rax
0x180106cd2  cmp     [rsp+0E0h+h], 0
0x180106cd8  jnz     short loc_180106CE6
0x180106cda  mov     [rsp+0E0h+var_C0], 8007000Eh
0x180106ce2  jmp     short loc_180106D13
0x180106ce4  jmp     short loc_180106D13
0x180106ce6  lea     rdx, [rbp+tm]; lptm
0x180106cea  mov     rcx, [rsp+0E0h+hdc]; hdc
0x180106cef  call    cs:__imp_GetTextMetricsA
0x180106cf5  test    eax, eax
0x180106cf7  jnz     short loc_180106D05
0x180106cf9  mov     [rsp+0E0h+var_C0], 8007000Eh
0x180106d01  jmp     short loc_180106D13
0x180106d03  jmp     short loc_180106D13
0x180106d05  mov     rax, [rsp+0E0h+var_B8]
0x180106d0a  mov     ecx, [rbp+tm.tmAveCharWidth]
0x180106d0d  mov     [rax+400h], ecx
0x180106d13  cmp     [rsp+0E0h+var_C0], 0
0x180106d18  jge     short loc_180106D7C
0x180106d1a  mov     rax, [rsp+0E0h+var_B8]
0x180106d1f  cmp     qword ptr [rax+3F8h], 0
0x180106d27  jz      short loc_180106D4B
0x180106d29  mov     rax, [rsp+0E0h+var_B8]
0x180106d2e  mov     rcx, [rax+3F8h]; ho
0x180106d35  call    cs:__imp_DeleteObject
0x180106d3b  mov     rax, [rsp+0E0h+var_B8]
0x180106d40  mov     qword ptr [rax+3F8h], 0
0x180106d4b  mov     rax, [rsp+0E0h+var_B8]
0x180106d50  cmp     qword ptr [rax+3F0h], 0
0x180106d58  jz      short loc_180106D7C
0x180106d5a  mov     rax, [rsp+0E0h+var_B8]
0x180106d5f  mov     rcx, [rax+3F0h]; ho
0x180106d66  call    cs:__imp_DeleteObject
0x180106d6c  mov     rax, [rsp+0E0h+var_B8]
0x180106d71  mov     qword ptr [rax+3F0h], 0
0x180106d7c  mov     rcx, [rsp+0E0h+Src]
0x180106d81  call    SysFreeStringA
0x180106d86  cmp     [rsp+0E0h+h], 0
0x180106d8c  jz      short loc_180106D9E
0x180106d8e  mov     rdx, [rsp+0E0h+h]; h
0x180106d93  mov     rcx, [rsp+0E0h+hdc]; hdc
0x180106d98  call    cs:__imp_SelectObject
0x180106d9e  cmp     [rsp+0E0h+hdc], 0
0x180106da4  jz      short loc_180106DB3
0x180106da6  mov     rdx, [rsp+0E0h+hdc]; hDC
0x180106dab  xor     ecx, ecx; hWnd
0x180106dad  call    cs:__imp_ReleaseDC
0x180106db3  mov     eax, [rsp+0E0h+var_C0]
0x180106db7  mov     rcx, [rbp+var_8]
0x180106dbb  xor     rcx, rsp; StackCookie
0x180106dbe  call    __security_check_cookie
0x180106dc3  add     rsp, 0E0h
0x180106dca  pop     rbp
0x180106dcb  retn
```
