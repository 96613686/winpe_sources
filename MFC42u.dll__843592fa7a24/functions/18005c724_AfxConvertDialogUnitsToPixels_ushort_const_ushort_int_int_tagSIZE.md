# _AfxConvertDialogUnitsToPixels(ushort const *,ushort,int,int,tagSIZE *)

- ea: `0x18005c724`
- end: `0x18005c8db`
- name: `?_AfxConvertDialogUnitsToPixels@@YAXPEBGGHHPEAUtagSIZE@@@Z`
- size: `439`
- prototype: `void __usercall(wchar_t *Source@<rcx>, unsigned __int16@<dx>, int@<r8d>, int@<r9d>, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005c0f0`

## callees

- `0x18005c724`
- `0x1800d1f92`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18005c7c0`
- `msvcrt!wcscpy_s` at `0x18005c7c0`
- `KERNEL32!MulDiv` at `0x18005c79f`
- `KERNEL32!MulDiv` at `0x18005c89b`
- `KERNEL32!MulDiv` at `0x18005c8b1`
- `KERNEL32!MulDiv` at `0x18005c79f`
- `KERNEL32!MulDiv` at `0x18005c89b`
- `KERNEL32!MulDiv` at `0x18005c8b1`
- `USER32!GetDialogBaseUnits` at `0x18005c86e`
- `USER32!GetDialogBaseUnits` at `0x18005c877`
- `USER32!GetDialogBaseUnits` at `0x18005c86e`
- `USER32!GetDialogBaseUnits` at `0x18005c877`
- `USER32!ReleaseDC` at `0x18005c88a`
- `USER32!ReleaseDC` at `0x18005c88a`
- `USER32!GetDC` at `0x18005c773`
- `USER32!GetDC` at `0x18005c773`
- `GDI32!GetDeviceCaps` at `0x18005c791`
- `GDI32!GetDeviceCaps` at `0x18005c791`
- `GDI32!DeleteObject` at `0x18005c866`
- `GDI32!DeleteObject` at `0x18005c866`
- `GDI32!GetTextExtentPoint32W` at `0x18005c837`
- `GDI32!GetTextExtentPoint32W` at `0x18005c837`
- `GDI32!GetTextMetricsW` at `0x18005c809`
- `GDI32!GetTextMetricsW` at `0x18005c809`
- `GDI32!SelectObject` at `0x18005c7e2`
- `GDI32!SelectObject` at `0x18005c85d`
- `GDI32!SelectObject` at `0x18005c7e2`
- `GDI32!SelectObject` at `0x18005c85d`
- `GDI32!CreateFontIndirectW` at `0x18005c7ca`
- `GDI32!CreateFontIndirectW` at `0x18005c7ca`

## pseudocode

```c
void __fastcall _AfxConvertDialogUnitsToPixels(
        wchar_t *Source,
        unsigned __int16 a2,
        int a3,
        int a4,
        struct tagSIZE *a5)
{
  int v6; // ebx
  HDC DC; // rsi
  int DeviceCaps; // eax
  int v10; // eax
  HFONT v11; // rax
  HFONT v12; // r12
  HGDIOBJ v13; // rbx
  unsigned int v14; // r14d
  int DialogBaseUnits; // edi
  struct tagSIZE psizl; // [rsp+28h] [rbp-A9h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+30h] [rbp-A1h] BYREF
  LOGFONTW lf; // [rsp+70h] [rbp-61h] BYREF

  v6 = a2;
  memset_0(&lf, 0, sizeof(lf));
  DC = GetDC(0);
  memset_0(&lf, 0, sizeof(lf));
  DeviceCaps = GetDeviceCaps(DC, 90);
  v10 = MulDiv(v6, DeviceCaps, 72);
  lf.lfWeight = 400;
  lf.lfCharSet = 1;
  lf.lfHeight = -v10;
  wcscpy_s(lf.lfFaceName, 0x20u, Source);
  v11 = CreateFontIndirectW(&lf);
  v12 = v11;
  if ( v11 )
  {
    v13 = SelectObject(DC, v11);
    memset(&tm, 0, sizeof(tm));
    GetTextMetricsW(DC, &tm);
    v14 = tm.tmHeight + tm.tmExternalLeading;
    psizl = 0;
    GetTextExtentPoint32W(DC, L"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz", 52, &psizl);
    DialogBaseUnits = (psizl.cx + 26) / 52;
    SelectObject(DC, v13);
    DeleteObject(v12);
  }
  else
  {
    DialogBaseUnits = (unsigned __int16)GetDialogBaseUnits();
    v14 = (unsigned int)GetDialogBaseUnits() >> 16;
  }
  ReleaseDC(0, DC);
  a5->cx = MulDiv(a3, DialogBaseUnits, 4);
  a5->cy = MulDiv(a4, v14, 8);
}

```

## disassembly

```asm
0x18005c724  push    rbp
0x18005c726  push    rbx
0x18005c727  push    rsi
0x18005c728  push    rdi
0x18005c729  push    r12
0x18005c72b  push    r13
0x18005c72d  push    r14
0x18005c72f  push    r15
0x18005c731  lea     rbp, [rsp-17h]
0x18005c736  sub     rsp, 0E8h
0x18005c73d  mov     rax, cs:__security_cookie
0x18005c744  xor     rax, rsp
0x18005c747  mov     [rbp+4Fh+var_50], rax
0x18005c74b  mov     r15, [rbp+4Fh+arg_20]
0x18005c74f  mov     r13d, r8d
0x18005c752  movzx   ebx, dx
0x18005c755  mov     rdi, rcx
0x18005c758  mov     r14d, 5Ch ; '\'
0x18005c75e  mov     [rsp+120h+nNumber], r9d
0x18005c763  mov     r8d, r14d; Size
0x18005c766  lea     rcx, [rbp+4Fh+lf]; void *
0x18005c76a  xor     edx, edx; Val
0x18005c76c  call    memset_0
0x18005c771  xor     ecx, ecx; hWnd
0x18005c773  call    cs:__imp_GetDC
0x18005c779  mov     r8d, r14d; Size
0x18005c77c  lea     rcx, [rbp+4Fh+lf]; void *
0x18005c780  xor     edx, edx; Val
0x18005c782  mov     rsi, rax
0x18005c785  call    memset_0
0x18005c78a  lea     edx, [r14-2]; index
0x18005c78e  mov     rcx, rsi; hdc
0x18005c791  call    cs:__imp_GetDeviceCaps
0x18005c797  mov     ecx, ebx; nNumber
0x18005c799  lea     r8d, [r14-14h]; nDenominator
0x18005c79d  mov     edx, eax; nNumerator
0x18005c79f  call    cs:__imp_MulDiv
0x18005c7a5  mov     r8, rdi; Source
0x18005c7a8  mov     [rbp+4Fh+lf.lfWeight], 190h
0x18005c7af  neg     eax
0x18005c7b1  mov     [rbp+4Fh+lf.lfCharSet], 1
0x18005c7b5  lea     edx, [r14-3Ch]; SizeInWords
0x18005c7b9  mov     [rbp+4Fh+lf.lfHeight], eax
0x18005c7bc  lea     rcx, [rbp+4Fh+lf.lfFaceName]; Destination
0x18005c7c0  call    cs:__imp_wcscpy_s
0x18005c7c6  lea     rcx, [rbp+4Fh+lf]; lplf
0x18005c7ca  call    cs:__imp_CreateFontIndirectW
0x18005c7d0  mov     r12, rax
0x18005c7d3  test    rax, rax
0x18005c7d6  jz      loc_18005C86E
0x18005c7dc  mov     rdx, rax; h
0x18005c7df  mov     rcx, rsi; hdc
0x18005c7e2  call    cs:__imp_SelectObject
0x18005c7e8  xorps   xmm0, xmm0
0x18005c7eb  lea     rdx, [rsp+120h+tm]; lptm
0x18005c7f0  movups  xmmword ptr [rsp+120h+tm.tmOverhang], xmm0
0x18005c7f5  mov     rcx, rsi; hdc
0x18005c7f8  mov     rbx, rax
0x18005c7fb  movups  xmmword ptr [rbp+4Fh+tm.tmFirstChar], xmm0
0x18005c7ff  movups  xmmword ptr [rsp+120h+tm.tmHeight], xmm0
0x18005c804  movups  xmmword ptr [rsp+120h+tm.tmExternalLeading], xmm0
0x18005c809  call    cs:__imp_GetTextMetricsW
0x18005c80f  mov     r14d, [rsp+120h+tm.tmExternalLeading]
0x18005c814  lea     r9, [rsp+120h+psizl]; psizl
0x18005c819  add     r14d, [rsp+120h+tm.tmHeight]
0x18005c81e  lea     rdx, aAbcdefghijklmn; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18005c825  mov     r8d, 34h ; '4'; c
0x18005c82b  mov     qword ptr [rsp+120h+psizl.cx], 0
0x18005c834  mov     rcx, rsi; hdc
0x18005c837  call    cs:__imp_GetTextExtentPoint32W
0x18005c83d  mov     ecx, [rsp+120h+psizl.cx]
0x18005c841  mov     eax, 4EC4EC4Fh
0x18005c846  add     ecx, 1Ah
0x18005c849  imul    ecx
0x18005c84b  mov     rcx, rsi; hdc
0x18005c84e  mov     edi, edx
0x18005c850  mov     rdx, rbx; h
0x18005c853  sar     edi, 4
0x18005c856  mov     eax, edi
0x18005c858  shr     eax, 1Fh
0x18005c85b  add     edi, eax
0x18005c85d  call    cs:__imp_SelectObject
0x18005c863  mov     rcx, r12; ho
0x18005c866  call    cs:__imp_DeleteObject
0x18005c86c  jmp     short loc_18005C885
0x18005c86e  call    cs:__imp_GetDialogBaseUnits
0x18005c874  movzx   edi, ax
0x18005c877  call    cs:__imp_GetDialogBaseUnits
0x18005c87d  shr     rax, 10h
0x18005c881  movzx   r14d, ax
0x18005c885  mov     rdx, rsi; hDC
0x18005c888  xor     ecx, ecx; hWnd
0x18005c88a  call    cs:__imp_ReleaseDC
0x18005c890  mov     r8d, 4; nDenominator
0x18005c896  mov     edx, edi; nNumerator
0x18005c898  mov     ecx, r13d; nNumber
0x18005c89b  call    cs:__imp_MulDiv
0x18005c8a1  mov     ecx, [rsp+120h+nNumber]; nNumber
0x18005c8a5  mov     r8d, 8; nDenominator
0x18005c8ab  mov     edx, r14d; nNumerator
0x18005c8ae  mov     [r15], eax
0x18005c8b1  call    cs:__imp_MulDiv
0x18005c8b7  mov     [r15+4], eax
0x18005c8bb  mov     rcx, [rbp+4Fh+var_50]
0x18005c8bf  xor     rcx, rsp; StackCookie
0x18005c8c2  call    __security_check_cookie
0x18005c8c7  add     rsp, 0E8h
0x18005c8ce  pop     r15
0x18005c8d0  pop     r14
0x18005c8d2  pop     r13
0x18005c8d4  pop     r12
0x18005c8d6  pop     rdi
0x18005c8d7  pop     rsi
0x18005c8d8  pop     rbx
0x18005c8d9  pop     rbp
0x18005c8da  retn
```
