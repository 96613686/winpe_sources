# s_DrawGlyph

- ea: `0x18006c9bc`
- end: `0x18006cc67`
- name: `s_DrawGlyph`
- size: `683`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, int, int, int iStateId, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006d26c`

## callees

- `0x18002cf10`
- `0x180030aec`
- `0x18003f214`
- `0x180041ec0`
- `0x180043c30`
- `0x1800446fc`
- `0x18006c9bc`
- `0x18006e750`

## import_xrefs

- `UxTheme!GetThemeColor` at `0x18006cb5d`
- `UxTheme!GetThemeColor` at `0x18006cbb9`
- `UxTheme!GetThemeColor` at `0x18006cb5d`
- `UxTheme!GetThemeColor` at `0x18006cbb9`
- `GDI32!SetBkMode` at `0x18006cb31`
- `GDI32!SetBkMode` at `0x18006cc1a`
- `GDI32!SetBkMode` at `0x18006cb31`
- `GDI32!SetBkMode` at `0x18006cc1a`
- `GDI32!SetTextColor` at `0x18006cbca`
- `GDI32!SetTextColor` at `0x18006cc0d`
- `GDI32!SetTextColor` at `0x18006cbca`
- `GDI32!SetTextColor` at `0x18006cc0d`
- `GDI32!CreateFontIndirectW` at `0x18006cb01`
- `GDI32!CreateFontIndirectW` at `0x18006cb01`
- `GDI32!SelectObject` at `0x18006cbd8`
- `GDI32!SelectObject` at `0x18006cc26`
- `GDI32!SelectObject` at `0x18006cbd8`
- `GDI32!SelectObject` at `0x18006cc26`
- `USER32!GetWindowLongW` at `0x18006ca6e`
- `USER32!GetWindowLongW` at `0x18006ca6e`
- `USER32!DrawTextW` at `0x18006cbf7`
- `USER32!DrawTextW` at `0x18006cbf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_DrawGlyph(
        HWND hWnd,
        __int64 a2,
        void *a3,
        HDC a4,
        int a5,
        __int16 a6,
        int iStateId,
        struct tagRECT *a8,
        unsigned int a9)
{
  unsigned int v10; // r13d
  char v12; // di
  UINT v13; // r12d
  int *v14; // r15
  unsigned int v15; // ebx
  int v16; // eax
  LONG v17; // eax
  int Error; // esi
  HFONT v19; // rbx
  HTHEME v20; // r13
  COLORREF v21; // r9d
  COLORREF v22; // edi
  HGDIOBJ v23; // rbx
  COLORREF pColor; // [rsp+30h] [rbp-B1h] BYREF
  COLORREF v26; // [rsp+34h] [rbp-ADh] BYREF
  int v27; // [rsp+38h] [rbp-A9h] BYREF
  WCHAR chText[2]; // [rsp+3Ch] [rbp-A5h] BYREF
  int v29; // [rsp+40h] [rbp-A1h] BYREF
  int v30; // [rsp+44h] [rbp-9Dh] BYREF
  int mode; // [rsp+48h] [rbp-99h]
  HTHEME hTheme; // [rsp+50h] [rbp-91h]
  LPRECT lprc; // [rsp+58h] [rbp-89h]
  HFONT v34[2]; // [rsp+60h] [rbp-81h] BYREF
  LOGFONTW lf; // [rsp+70h] [rbp-71h] BYREF

  hTheme = a3;
  v10 = a2;
  lprc = a8;
  wcscpy(chText, L"");
  v27 = 63372;
  v29 = 59764;
  v30 = 59763;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_HVCZMTest>::GetImpl'::`2'::impl,
    a2);
  if ( a5 == 11 )
  {
    v12 = 0;
    v13 = 37;
    v14 = &v27;
    if ( (a6 & 0x200) != 0 )
      v14 = (int *)chText;
    v15 = (a6 & 0x200) != 0 ? -16 : -10;
  }
  else
  {
    if ( a5 != 16 )
      return (unsigned int)-2147023728;
    v16 = GetWindowLongW(hWnd, -20) & 0x400000;
    v12 = 1;
    v15 = -10;
    v14 = &v29;
    if ( v16 )
      v14 = &v30;
    v13 = v16 != 0 ? 131109 : 37;
  }
  memset_0(&lf, 0, sizeof(lf));
  v17 = DPIToPPIHelpers::ScaleByType(a9, v15, hWnd, v10);
  if ( v12 && (v17 & 1) == 0 )
    --v17;
  lf.lfHeight = v17;
  lf.lfWeight = 400;
  lf.lfCharSet = 1;
  lf.lfQuality = 5;
  Error = StringCchCopyW(lf.lfFaceName, 0x20u, L"Segoe Fluent Icons");
  if ( Error >= 0 )
  {
    v19 = CreateFontIndirectW(&lf);
    v34[0] = v19;
    if ( v19 )
    {
      Error = 0;
      mode = SetBkMode(a4, 1);
      pColor = 0;
      v20 = hTheme;
      GetThemeColor(hTheme, 9, 0, 3802, &pColor);
      v21 = 0xFFFFFF;
      if ( BYTE2(pColor) + 5 * BYTE1(pColor) + 2 * (unsigned int)(unsigned __int8)pColor > 0x400 )
        v21 = 0;
      v26 = v21;
      if ( ((iStateId - 2) & 0xFFFFFFFD) == 0 )
      {
        GetThemeColor(v20, 27, iStateId, 3803, &v26);
        v21 = v26;
      }
      v22 = SetTextColor(a4, v21);
      v23 = SelectObject(a4, v19);
      if ( !DrawTextW(a4, (LPCWSTR)v14, 1, lprc, v13) )
        Error = ResultFromKnownLastError();
      SetTextColor(a4, v22);
      SetBkMode(a4, mode);
      SelectObject(a4, v23);
    }
    else
    {
      Error = -2147467259;
    }
    CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(v34);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006c9bc  push    rbp
0x18006c9be  push    rbx
0x18006c9bf  push    rsi
0x18006c9c0  push    rdi
0x18006c9c1  push    r12
0x18006c9c3  push    r13
0x18006c9c5  push    r14
0x18006c9c7  push    r15
0x18006c9c9  lea     rbp, [rsp-7]
0x18006c9ce  sub     rsp, 0E8h
0x18006c9d5  mov     rax, cs:__security_cookie
0x18006c9dc  xor     rax, rsp
0x18006c9df  mov     [rbp+3Fh+var_50], rax
0x18006c9e3  mov     r14, r9
0x18006c9e6  mov     [rsp+120h+hTheme], r8
0x18006c9eb  mov     r13d, edx
0x18006c9ee  mov     rsi, rcx
0x18006c9f1  mov     rax, [rbp+3Fh+arg_38]
0x18006c9f8  mov     [rsp+120h+lprc], rax
0x18006c9fd  mov     dword ptr [rsp+120h+chText], 0E915h
0x18006ca05  mov     [rsp+120h+var_E8], 0F78Ch
0x18006ca0d  mov     [rsp+120h+var_E0], 0E974h
0x18006ca15  mov     [rsp+120h+var_DC], 0E973h
0x18006ca1d  mov     dl, 1
0x18006ca1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HVCZMTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HVCZMTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest> `wil::Feature<__WilFeatureTraits_Feature_HVCZMTest>::GetImpl(void)'::`2'::impl
0x18006ca26  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HVCZMTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006ca2b  cmp     [rbp+3Fh+arg_20], 0Bh
0x18006ca2f  jnz     short loc_18006CA5C
0x18006ca31  xor     dil, dil
0x18006ca34  mov     r12d, 25h ; '%'
0x18006ca3a  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18006ca3d  and     eax, 200h
0x18006ca42  lea     r15, [rsp+120h+var_E8]
0x18006ca47  lea     rcx, [rsp+120h+chText]
0x18006ca4c  cmovnz  r15, rcx
0x18006ca50  neg     eax
0x18006ca52  sbb     ebx, ebx
0x18006ca54  and     ebx, 0FFFFFFFAh
0x18006ca57  add     ebx, 0FFFFFFF6h
0x18006ca5a  jmp     short loc_18006CA9F
0x18006ca5c  cmp     [rbp+3Fh+arg_20], 10h
0x18006ca60  jnz     loc_18006CC40
0x18006ca66  mov     edx, 0FFFFFFECh; nIndex
0x18006ca6b  mov     rcx, rsi; hWnd
0x18006ca6e  call    cs:__imp_GetWindowLongW
0x18006ca74  and     eax, 400000h
0x18006ca79  mov     dil, 1
0x18006ca7c  mov     ebx, 0FFFFFFF6h
0x18006ca81  lea     r15, [rsp+120h+var_E0]
0x18006ca86  lea     rcx, [rsp+120h+var_DC]
0x18006ca8b  cmovnz  r15, rcx
0x18006ca8f  neg     eax
0x18006ca91  sbb     eax, eax
0x18006ca93  and     eax, 20000h
0x18006ca98  lea     r12d, [rbx+2Fh]
0x18006ca9c  add     r12d, eax
0x18006ca9f  xor     edx, edx; Val
0x18006caa1  lea     r8d, [rdx+5Ch]; Size
0x18006caa5  lea     rcx, [rbp+3Fh+lf]; void *
0x18006caa9  call    memset_0
0x18006caae  mov     r9d, r13d
0x18006cab1  mov     r8, rsi
0x18006cab4  mov     edx, ebx
0x18006cab6  mov     ecx, [rbp+3Fh+arg_40]
0x18006cabc  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006cac1  test    dil, dil
0x18006cac4  jz      short loc_18006CACC
0x18006cac6  test    al, 1
0x18006cac8  jnz     short loc_18006CACC
0x18006caca  dec     eax
0x18006cacc  mov     [rbp+3Fh+lf.lfHeight], eax
0x18006cacf  mov     [rbp+3Fh+lf.lfWeight], 190h
0x18006cad6  mov     [rbp+3Fh+lf.lfCharSet], 1
0x18006cada  mov     [rbp+3Fh+lf.lfQuality], 5
0x18006cade  lea     r8, aSegoeFluentIco; "Segoe Fluent Icons"
0x18006cae5  mov     edx, 20h ; ' '; unsigned __int64
0x18006caea  lea     rcx, [rbp+3Fh+lf.lfFaceName]; unsigned __int16 *
0x18006caee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006caf3  mov     esi, eax
0x18006caf5  test    eax, eax
0x18006caf7  js      loc_18006CC45
0x18006cafd  lea     rcx, [rbp+3Fh+lf]; lplf
0x18006cb01  call    cs:__imp_CreateFontIndirectW
0x18006cb07  mov     rbx, rax
0x18006cb0a  mov     [rsp+120h+var_C0], rax
0x18006cb0f  test    rax, rax
0x18006cb12  jz      loc_18006CC2E
0x18006cb18  xor     esi, esi
0x18006cb1a  mov     eax, [rbp+3Fh+iStateId]
0x18006cb1d  add     eax, 0FFFFFFFEh
0x18006cb20  test    eax, 0FFFFFFFDh
0x18006cb25  mov     edi, esi
0x18006cb27  setz    dil
0x18006cb2b  lea     edx, [rsi+1]; mode
0x18006cb2e  mov     rcx, r14; hdc
0x18006cb31  call    cs:__imp_SetBkMode
0x18006cb37  mov     [rsp+120h+mode], eax
0x18006cb3b  mov     [rsp+120h+var_F0], esi
0x18006cb3f  lea     rax, [rsp+120h+var_F0]
0x18006cb44  mov     [rsp+120h+pColor], rax; pColor
0x18006cb49  mov     r9d, 0EDAh; iPropId
0x18006cb4f  xor     r8d, r8d; iStateId
0x18006cb52  lea     edx, [rsi+9]; iPartId
0x18006cb55  mov     r13, [rsp+120h+hTheme]
0x18006cb5a  mov     rcx, r13; hTheme
0x18006cb5d  call    cs:__imp_GetThemeColor
0x18006cb63  mov     r8d, [rsp+120h+var_F0]
0x18006cb68  movzx   ecx, r8w
0x18006cb6c  shr     ecx, 8
0x18006cb6f  lea     edx, [rcx+rcx*4]
0x18006cb72  mov     ecx, r8d
0x18006cb75  shr     ecx, 10h
0x18006cb78  movzx   eax, cl
0x18006cb7b  add     edx, eax
0x18006cb7d  movzx   eax, r8b
0x18006cb81  lea     edx, [rdx+rax*2]
0x18006cb84  xor     eax, eax
0x18006cb86  mov     r9d, 0FFFFFFh
0x18006cb8c  cmp     edx, 400h
0x18006cb92  cmova   r9d, eax
0x18006cb96  mov     [rsp+120h+var_EC], r9d
0x18006cb9b  test    edi, edi
0x18006cb9d  jz      short loc_18006CBC4
0x18006cb9f  lea     rax, [rsp+120h+var_EC]
0x18006cba4  mov     [rsp+120h+pColor], rax; pColor
0x18006cba9  mov     r9d, 0EDBh; iPropId
0x18006cbaf  mov     r8d, [rbp+3Fh+iStateId]; iStateId
0x18006cbb3  lea     edx, [rsi+1Bh]; iPartId
0x18006cbb6  mov     rcx, r13; hTheme
0x18006cbb9  call    cs:__imp_GetThemeColor
0x18006cbbf  mov     r9d, [rsp+120h+var_EC]
0x18006cbc4  mov     edx, r9d; color
0x18006cbc7  mov     rcx, r14; hdc
0x18006cbca  call    cs:__imp_SetTextColor
0x18006cbd0  mov     edi, eax
0x18006cbd2  mov     rdx, rbx; h
0x18006cbd5  mov     rcx, r14; hdc
0x18006cbd8  call    cs:__imp_SelectObject
0x18006cbde  mov     rbx, rax
0x18006cbe1  mov     dword ptr [rsp+120h+pColor], r12d; format
0x18006cbe6  mov     r9, [rsp+120h+lprc]; lprc
0x18006cbeb  mov     r8d, 1; cchText
0x18006cbf1  mov     rdx, r15; lpchText
0x18006cbf4  mov     rcx, r14; hdc
0x18006cbf7  call    cs:__imp_DrawTextW
0x18006cbfd  test    eax, eax
0x18006cbff  jnz     short loc_18006CC08
0x18006cc01  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006cc06  mov     esi, eax
0x18006cc08  mov     edx, edi; color
0x18006cc0a  mov     rcx, r14; hdc
0x18006cc0d  call    cs:__imp_SetTextColor
0x18006cc13  mov     edx, [rsp+120h+mode]; mode
0x18006cc17  mov     rcx, r14; hdc
0x18006cc1a  call    cs:__imp_SetBkMode
0x18006cc20  mov     rdx, rbx; h
0x18006cc23  mov     rcx, r14; hdc
0x18006cc26  call    cs:__imp_SelectObject
0x18006cc2c  jmp     short loc_18006CC33
0x18006cc2e  mov     esi, 80004005h
0x18006cc33  lea     rcx, [rsp+120h+var_C0]
0x18006cc38  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x18006cc3d  nop
0x18006cc3e  jmp     short loc_18006CC45
0x18006cc40  mov     esi, 80070490h
0x18006cc45  mov     eax, esi
0x18006cc47  mov     rcx, [rbp+3Fh+var_50]
0x18006cc4b  xor     rcx, rsp; StackCookie
0x18006cc4e  call    __security_check_cookie
0x18006cc53  add     rsp, 0E8h
0x18006cc5a  pop     r15
0x18006cc5c  pop     r14
0x18006cc5e  pop     r13
0x18006cc60  pop     r12
0x18006cc62  pop     rdi
0x18006cc63  pop     rsi
0x18006cc64  pop     rbx
0x18006cc65  pop     rbp
0x18006cc66  retn
```
