# CSearchEditBox::_UpdateFont(void)

- ea: `0x1800b9240`
- end: `0x1800b962d`
- name: `?_UpdateFont@CSearchEditBox@@EEAAXXZ`
- size: `1005`
- prototype: `void __fastcall(CSearchEditBox *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800b9240`
- `0x1800b9634`
- `0x180107b64`
- `0x18013f7d0`
- `0x1801406c8`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x1800b95f6`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800b95f6`
- `KERNEL32!MulDiv` at `0x1800b940a`
- `KERNEL32!MulDiv` at `0x1800b940a`
- `USER32!SystemParametersInfoW` at `0x1800b95e0`
- `USER32!SystemParametersInfoW` at `0x1800b95e0`
- `USER32!GetSysColor` at `0x1800b939f`
- `USER32!GetSysColor` at `0x1800b939f`
- `GDI32!DeleteObject` at `0x1800b92da`
- `GDI32!DeleteObject` at `0x1800b92da`
- `GDI32!GetDeviceCaps` at `0x1800b93f6`
- `GDI32!GetDeviceCaps` at `0x1800b93f6`
- `GDI32!GetTextExtentPointW` at `0x1800b9506`
- `GDI32!GetTextExtentPointW` at `0x1800b9506`
- `GDI32!SelectObject` at `0x1800b94e6`
- `GDI32!SelectObject` at `0x1800b954a`
- `GDI32!SelectObject` at `0x1800b94e6`
- `GDI32!SelectObject` at `0x1800b954a`
- `GDI32!CreateFontIndirectW` at `0x1800b94d3`
- `GDI32!CreateFontIndirectW` at `0x1800b94d3`
- `UxTheme!GetThemeFont` at `0x1800b92c0`
- `UxTheme!GetThemeFont` at `0x1800b92c0`
- `UxTheme!GetThemeBool` at `0x1800b95b3`
- `UxTheme!GetThemeBool` at `0x1800b95b3`
- `UxTheme!GetThemeColor` at `0x1800b93cb`
- `UxTheme!GetThemeColor` at `0x1800b93cb`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800b9530`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800b9530`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800b9539`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800b9539`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1800b9512`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1800b9512`

## pseudocode

```c
void __fastcall CSearchEditBox::_UpdateFont(CSearchEditBox *this)
{
  void *v2; // rcx
  void *v3; // rcx
  double lfHeight; // xmm6_8
  HWND v5; // rax
  __int64 v6; // rdx
  WCHAR *lfFaceName; // r8
  __int64 v8; // rcx
  _WORD *v9; // rax
  _WORD *v10; // rcx
  __int16 lfWeight; // ax
  DWORD SysColor; // eax
  void *v13; // rcx
  __int64 v14; // rcx
  HDC v15; // rsi
  int DeviceCaps; // eax
  __int128 v17; // xmm1
  __int64 v18; // rcx
  int v19; // eax
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  void *v25; // rcx
  int v26; // edx
  BYTE lfItalic; // cl
  HFONT v28; // rax
  HGDIOBJ v29; // rax
  void *v30; // r14
  struct DirectUI::Value *Int; // rax
  DirectUI::Value *v32; // rdi
  int v33; // edi
  LANGID UserDefaultUILanguage; // ax
  COLORREF pColor[2]; // [rsp+38h] [rbp-D0h] BYREF
  struct tagSIZE sz; // [rsp+40h] [rbp-C8h] BYREF
  LOGFONTW lf; // [rsp+48h] [rbp-C0h] BYREF
  __int128 Buf2; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v39[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-10h]
  __int128 v41; // [rsp+108h] [rbp+0h]
  int v42; // [rsp+118h] [rbp+10h]

  if ( *((_QWORD *)this + 30) )
  {
    if ( (memset_0(&lf, 0, sizeof(lf)), (v2 = (void *)*((_QWORD *)this + 80)) != 0)
      && GetThemeFont(v2, 0, 0, 0, 210, &lf) >= 0
      || SystemParametersInfoW(0x1Fu, 0x5Cu, &lf, 0) )
    {
      v3 = (void *)*((_QWORD *)this + 96);
      if ( v3 )
        DeleteObject(v3);
      lfHeight = (double)lf.lfHeight;
      v5 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 29) + 360LL))(*((_QWORD *)this + 29));
      lf.lfHeight = (int)(SHComputeSystemToMonitorDPIRatio(v5) * lfHeight);
      memset_0(&Buf2, 0, 0x74u);
      v6 = 32;
      *(_QWORD *)&Buf2 = 0xE840000300000074uLL;
      lfFaceName = lf.lfFaceName;
      v8 = 2147483646;
      v9 = (_WORD *)v39 + 5;
      do
      {
        if ( !v8 )
          break;
        if ( !*lfFaceName )
          break;
        *v9++ = *lfFaceName++;
        --v8;
        --v6;
      }
      while ( v6 );
      v10 = v9 - 1;
      pColor[0] = 0;
      if ( v6 )
        v10 = v9;
      lfWeight = lf.lfWeight;
      *v10 = 0;
      WORD6(v40) = lfWeight;
      BYTE9(v39[0]) = lf.lfPitchAndFamily;
      BYTE8(v39[0]) = lf.lfCharSet;
      SysColor = GetSysColor(8);
      v13 = (void *)*((_QWORD *)this + 80);
      pColor[0] = SysColor;
      if ( v13 )
      {
        GetThemeColor(v13, 1, 1, 3803, pColor);
        SysColor = pColor[0];
      }
      v14 = *((_QWORD *)this + 32);
      DWORD1(v39[0]) = SysColor;
      v15 = (HDC)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
      DeviceCaps = GetDeviceCaps(v15, 90);
      HIDWORD(Buf2) = 20 * MulDiv(-lf.lfHeight, 72, DeviceCaps);
      if ( memcmp_0((char *)this + 272, &Buf2, 0x74u) )
      {
        v17 = v39[0];
        v18 = *((_QWORD *)this + 30);
        v19 = v42;
        *((_OWORD *)this + 17) = Buf2;
        *((_DWORD *)this + 146) = 1;
        v20 = v39[1];
        *((_OWORD *)this + 18) = v17;
        v21 = v39[2];
        *((_OWORD *)this + 19) = v20;
        v22 = v39[3];
        *((_OWORD *)this + 20) = v21;
        v23 = v40;
        *((_OWORD *)this + 21) = v22;
        v24 = v41;
        *((_OWORD *)this + 22) = v23;
        *((_OWORD *)this + 23) = v24;
        *((_DWORD *)this + 96) = v19;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 152LL))(v18, 0x20000, 0x20000);
        *((_DWORD *)this + 146) = 0;
      }
      v25 = (void *)*((_QWORD *)this + 80);
      if ( v25 )
      {
        lf.lfItalic = 1;
        pColor[0] = 0;
        if ( GetThemeBool(v25, 1, 8, 2218, (BOOL *)pColor) >= 0 )
          lf.lfItalic &= -(pColor[0] != 0);
      }
      v26 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
      if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
      {
        v33 = 0;
        UserDefaultUILanguage = GetUserDefaultUILanguage();
        `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
        if ( UserDefaultUILanguage )
          v33 = IsBiDiLocale(UserDefaultUILanguage);
        _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v33 != 0);
        v26 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
      }
      lfItalic = lf.lfItalic;
      if ( v26 == 1 )
        lfItalic = 0;
      lf.lfItalic = lfItalic;
      v28 = CreateFontIndirectW(&lf);
      *((_QWORD *)this + 96) = v28;
      v29 = SelectObject(v15, v28);
      sz = 0;
      v30 = v29;
      GetTextExtentPointW(v15, L"0", 1, &sz);
      Int = (struct DirectUI::Value *)DirectUI::Value::CreateInt((unsigned int)sz.cy, 0);
      v32 = Int;
      if ( Int )
      {
        DirectUI::Element::SetValue(this, (const struct DirectUI::PropertyInfo *)&off_180217BD0, 1, Int);
        DirectUI::Value::Release(v32);
      }
      if ( v30 )
        SelectObject(v15, v30);
      (*(void (__fastcall **)(_QWORD, HDC))(**((_QWORD **)this + 32) + 32LL))(*((_QWORD *)this + 32), v15);
    }
  }
}

```

## disassembly

```asm
0x1800b9240  mov     rax, rsp
0x1800b9243  mov     [rax+10h], rbx
0x1800b9247  mov     [rax+18h], rsi
0x1800b924b  push    rbp
0x1800b924c  push    rdi
0x1800b924d  push    r12
0x1800b924f  push    r14
0x1800b9251  push    r15
0x1800b9253  lea     rbp, [rax-68h]
0x1800b9257  sub     rsp, 140h
0x1800b925e  movaps  xmmword ptr [rax-38h], xmm6
0x1800b9262  mov     rax, cs:__security_cookie
0x1800b9269  xor     rax, rsp
0x1800b926c  mov     [rbp+60h+var_40], rax
0x1800b9270  xor     r15d, r15d
0x1800b9273  mov     rbx, rcx
0x1800b9276  cmp     [rcx+0F0h], r15
0x1800b927d  jz      loc_1800B9566
0x1800b9283  lea     edi, [r15+5Ch]
0x1800b9287  xor     edx, edx; Val
0x1800b9289  mov     r8d, edi; Size
0x1800b928c  lea     rcx, [rsp+160h+lf]; void *
0x1800b9291  call    memset_0
0x1800b9296  mov     rcx, [rbx+280h]; hTheme
0x1800b929d  test    rcx, rcx
0x1800b92a0  jz      loc_1800B95D2
0x1800b92a6  lea     rax, [rsp+160h+lf]
0x1800b92ab  xor     r9d, r9d; iStateId
0x1800b92ae  mov     [rsp+160h+pFont], rax; pFont
0x1800b92b3  xor     r8d, r8d; iPartId
0x1800b92b6  xor     edx, edx; hdc
0x1800b92b8  mov     [rsp+160h+iPropId], 0D2h; iPropId
0x1800b92c0  call    cs:__imp_GetThemeFont
0x1800b92c6  test    eax, eax
0x1800b92c8  js      loc_1800B95D2
0x1800b92ce  mov     rcx, [rbx+300h]; ho
0x1800b92d5  test    rcx, rcx
0x1800b92d8  jz      short loc_1800B92E0
0x1800b92da  call    cs:__imp_DeleteObject
0x1800b92e0  mov     rcx, [rbx+0E8h]
0x1800b92e7  movd    xmm6, [rsp+160h+lf.lfHeight]
0x1800b92ed  cvtdq2pd xmm6, xmm6
0x1800b92f1  mov     rax, [rcx]
0x1800b92f4  mov     rax, [rax+168h]
0x1800b92fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9300  mov     rcx, rax; HWND
0x1800b9303  call    ?SHComputeSystemToMonitorDPIRatio@@YANPEAUHWND__@@@Z; SHComputeSystemToMonitorDPIRatio(HWND__ *)
0x1800b9308  mulsd   xmm0, xmm6
0x1800b930c  lea     rcx, [rbp+60h+Buf2]; void *
0x1800b9310  xor     edx, edx; Val
0x1800b9312  cvttsd2si eax, xmm0
0x1800b9316  lea     r8d, [rdx+74h]; Size
0x1800b931a  mov     [rsp+160h+lf.lfHeight], eax
0x1800b931e  call    memset_0
0x1800b9323  mov     edx, 20h ; ' '
0x1800b9328  mov     dword ptr [rbp+60h+Buf2], 74h ; 't'
0x1800b932f  mov     dword ptr [rbp+60h+Buf2+4], 0E8400003h
0x1800b9336  lea     r8, [rsp+160h+lf.lfFaceName]
0x1800b933b  mov     ecx, 7FFFFFFEh
0x1800b9340  lea     rax, [rbp+60h+var_A6]
0x1800b9344  lea     r12d, [rdx-1Fh]
0x1800b9348  test    rcx, rcx
0x1800b934b  jz      short loc_1800B936B
0x1800b934d  movzx   r9d, word ptr [r8]
0x1800b9351  test    r9w, r9w
0x1800b9355  jz      short loc_1800B936B
0x1800b9357  mov     [rax], r9w
0x1800b935b  add     r8, 2
0x1800b935f  add     rax, 2
0x1800b9363  sub     rcx, r12
0x1800b9366  sub     rdx, r12
0x1800b9369  jnz     short loc_1800B9348
0x1800b936b  lea     rcx, [rax-2]
0x1800b936f  mov     [rsp+160h+pColor], r15d
0x1800b9374  test    rdx, rdx
0x1800b9377  mov     r14d, 8
0x1800b937d  cmovnz  rcx, rax
0x1800b9381  movzx   eax, word ptr [rsp+160h+lf.lfWeight]
0x1800b9386  mov     [rcx], r15w
0x1800b938a  mov     ecx, r14d; nIndex
0x1800b938d  mov     [rbp+60h+var_64], ax
0x1800b9391  mov     al, [rsp+160h+lf.lfPitchAndFamily]
0x1800b9395  mov     [rbp+60h+var_A7], al
0x1800b9398  mov     al, [rsp+160h+lf.lfCharSet]
0x1800b939c  mov     [rbp+60h+var_A8], al
0x1800b939f  call    cs:__imp_GetSysColor
0x1800b93a5  mov     rcx, [rbx+280h]; hTheme
0x1800b93ac  mov     [rsp+160h+pColor], eax
0x1800b93b0  test    rcx, rcx
0x1800b93b3  jz      short loc_1800B93D5
0x1800b93b5  lea     rax, [rsp+160h+pColor]
0x1800b93ba  mov     r9d, 0EDBh; iPropId
0x1800b93c0  mov     r8d, r12d; iStateId
0x1800b93c3  mov     qword ptr [rsp+160h+iPropId], rax; pColor
0x1800b93c8  mov     edx, r12d; iPartId
0x1800b93cb  call    cs:__imp_GetThemeColor
0x1800b93d1  mov     eax, [rsp+160h+pColor]
0x1800b93d5  mov     rcx, [rbx+100h]
0x1800b93dc  mov     [rbp+60h+var_AC], eax
0x1800b93df  mov     rax, [rcx]
0x1800b93e2  mov     rax, [rax+18h]
0x1800b93e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b93eb  mov     edx, 5Ah ; 'Z'; index
0x1800b93f0  mov     rcx, rax; hdc
0x1800b93f3  mov     rsi, rax
0x1800b93f6  call    cs:__imp_GetDeviceCaps
0x1800b93fc  mov     ecx, [rsp+160h+lf.lfHeight]
0x1800b9400  mov     edx, 48h ; 'H'; nNumerator
0x1800b9405  neg     ecx; nNumber
0x1800b9407  mov     r8d, eax; nDenominator
0x1800b940a  call    cs:__imp_MulDiv
0x1800b9410  lea     rdi, [rbx+110h]
0x1800b9417  mov     r8d, 74h ; 't'; Size
0x1800b941d  lea     rdx, [rbp+60h+Buf2]; Buf2
0x1800b9421  lea     ecx, [rax+rax*4]
0x1800b9424  shl     ecx, 2
0x1800b9427  mov     dword ptr [rbp+60h+Buf2+0Ch], ecx
0x1800b942a  mov     rcx, rdi; Buf1
0x1800b942d  call    memcmp_0
0x1800b9432  test    eax, eax
0x1800b9434  jz      short loc_1800B949F
0x1800b9436  movaps  xmm0, [rbp+60h+Buf2]
0x1800b943a  mov     edx, 20000h
0x1800b943f  movaps  xmm1, xmmword ptr [rbp-50h]
0x1800b9443  mov     r8d, edx
0x1800b9446  mov     rcx, [rbx+0F0h]
0x1800b944d  mov     eax, [rbp+60h+var_50]
0x1800b9450  movups  xmmword ptr [rdi], xmm0
0x1800b9453  mov     [rbx+248h], r12d
0x1800b945a  movaps  xmm0, [rbp+60h+var_A0]
0x1800b945e  movups  xmmword ptr [rdi+10h], xmm1
0x1800b9462  movaps  xmm1, [rbp+60h+var_90]
0x1800b9466  movups  xmmword ptr [rdi+20h], xmm0
0x1800b946a  movaps  xmm0, [rbp+60h+var_80]
0x1800b946e  movups  xmmword ptr [rdi+30h], xmm1
0x1800b9472  movaps  xmm1, xmmword ptr [rbp-10h]
0x1800b9476  movups  xmmword ptr [rdi+40h], xmm0
0x1800b947a  movaps  xmm0, [rbp+60h+var_60]
0x1800b947e  movups  xmmword ptr [rdi+50h], xmm1
0x1800b9482  movups  xmmword ptr [rdi+60h], xmm0
0x1800b9486  mov     [rdi+70h], eax
0x1800b9489  mov     rax, [rcx]
0x1800b948c  mov     rax, [rax+98h]
0x1800b9493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9498  mov     [rbx+248h], r15d
0x1800b949f  mov     rcx, [rbx+280h]; hTheme
0x1800b94a6  test    rcx, rcx
0x1800b94a9  jnz     loc_1800B9593
0x1800b94af  mov     edx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800b94b5  cmp     edx, 0FFFFFFFFh
0x1800b94b8  jz      loc_1800B95F3
0x1800b94be  movzx   ecx, [rsp+160h+lf.lfItalic]
0x1800b94c3  cmp     edx, r12d
0x1800b94c6  cmovz   ecx, r15d
0x1800b94ca  mov     [rsp+160h+lf.lfItalic], cl
0x1800b94ce  lea     rcx, [rsp+160h+lf]; lplf
0x1800b94d3  call    cs:__imp_CreateFontIndirectW
0x1800b94d9  mov     rdx, rax; h
0x1800b94dc  mov     [rbx+300h], rax
0x1800b94e3  mov     rcx, rsi; hdc
0x1800b94e6  call    cs:__imp_SelectObject
0x1800b94ec  lea     r9, [rsp+160h+sz]; lpsz
0x1800b94f1  mov     qword ptr [rsp+160h+sz.cx], r15
0x1800b94f6  mov     r8d, r12d; c
0x1800b94f9  lea     rdx, chText; "0"
0x1800b9500  mov     rcx, rsi; hdc
0x1800b9503  mov     r14, rax
0x1800b9506  call    cs:__imp_GetTextExtentPointW
0x1800b950c  mov     ecx, [rsp+160h+sz.cy]
0x1800b9510  xor     edx, edx
0x1800b9512  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x1800b9518  mov     rdi, rax
0x1800b951b  test    rax, rax
0x1800b951e  jz      short loc_1800B953F
0x1800b9520  mov     r9, rax
0x1800b9523  lea     rdx, off_180217BD0; "FontHeight"
0x1800b952a  mov     r8d, r12d
0x1800b952d  mov     rcx, rbx
0x1800b9530  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1800b9536  mov     rcx, rdi
0x1800b9539  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800b953f  test    r14, r14
0x1800b9542  jz      short loc_1800B9550
0x1800b9544  mov     rdx, r14; h
0x1800b9547  mov     rcx, rsi; hdc
0x1800b954a  call    cs:__imp_SelectObject
0x1800b9550  mov     rcx, [rbx+100h]
0x1800b9557  mov     rdx, rsi
0x1800b955a  mov     rax, [rcx]
0x1800b955d  mov     rax, [rax+20h]
0x1800b9561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9566  mov     rcx, [rbp+60h+var_40]
0x1800b956a  xor     rcx, rsp; StackCookie
0x1800b956d  call    __security_check_cookie
0x1800b9572  lea     r11, [rsp+160h+var_20]
0x1800b957a  mov     rbx, [r11+38h]
0x1800b957e  mov     rsi, [r11+40h]
0x1800b9582  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b9587  mov     rsp, r11
0x1800b958a  pop     r15
0x1800b958c  pop     r14
0x1800b958e  pop     r12
0x1800b9590  pop     rdi
0x1800b9591  pop     rbp
0x1800b9592  retn
0x1800b9593  lea     rax, [rsp+160h+pColor]
0x1800b9598  mov     [rsp+160h+lf.lfItalic], r12b
0x1800b959d  mov     r9d, 8AAh; iPropId
0x1800b95a3  mov     qword ptr [rsp+160h+iPropId], rax; pfVal
0x1800b95a8  mov     r8d, r14d; iStateId
0x1800b95ab  mov     [rsp+160h+pColor], r15d
0x1800b95b0  mov     edx, r12d; iPartId
0x1800b95b3  call    cs:__imp_GetThemeBool
0x1800b95b9  test    eax, eax
0x1800b95bb  js      loc_1800B94AF
0x1800b95c1  mov     eax, [rsp+160h+pColor]
0x1800b95c5  neg     eax
0x1800b95c7  sbb     cl, cl
0x1800b95c9  and     [rsp+160h+lf.lfItalic], cl
0x1800b95cd  jmp     loc_1800B94AF
0x1800b95d2  xor     r9d, r9d; fWinIni
0x1800b95d5  lea     r8, [rsp+160h+lf]; pvParam
0x1800b95da  mov     edx, edi; uiParam
0x1800b95dc  lea     ecx, [r9+1Fh]; uiAction
0x1800b95e0  call    cs:__imp_SystemParametersInfoW
0x1800b95e6  test    eax, eax
0x1800b95e8  jnz     loc_1800B92CE
0x1800b95ee  jmp     loc_1800B9566
0x1800b95f3  mov     edi, r15d
0x1800b95f6  call    cs:__imp_GetUserDefaultUILanguage
0x1800b95fc  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x1800b9603  test    ax, ax
0x1800b9606  jnz     short loc_1800B9621
0x1800b9608  mov     ecx, r15d
0x1800b960b  test    edi, edi
0x1800b960d  setnz   cl
0x1800b9610  xchg    ecx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800b9616  mov     edx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x1800b961c  jmp     loc_1800B94BE
0x1800b9621  movzx   ecx, ax; unsigned int
0x1800b9624  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x1800b9629  mov     edi, eax
0x1800b962b  jmp     short loc_1800B9608
```
