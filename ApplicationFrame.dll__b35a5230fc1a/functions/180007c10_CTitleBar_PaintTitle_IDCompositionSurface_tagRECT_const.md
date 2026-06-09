# CTitleBar::_PaintTitle(IDCompositionSurface *,tagRECT const &)

- ea: `0x180007c10`
- end: `0x180008362`
- name: `?_PaintTitle@CTitleBar@@AEAAJPEAUIDCompositionSurface@@AEBUtagRECT@@@Z`
- size: `1874`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this, struct IDCompositionSurface *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009e40`

## callees

- `0x180004c98`
- `0x180007c10`
- `0x180008e70`
- `0x18000ad80`
- `0x18000d6a8`
- `0x18000da80`
- `0x18002d354`
- `0x18003fbc0`
- `0x180040270`
- `0x180043c30`
- `0x18004c498`
- `0x18005702c`
- `0x1800571a4`
- `0x180057618`
- `0x180072010`

## import_xrefs

- `UxTheme!BeginBufferedPaint` at `0x180007dc3`
- `UxTheme!BeginBufferedPaint` at `0x180007dc3`
- `UxTheme!DrawThemeTextEx` at `0x180008053`
- `UxTheme!DrawThemeTextEx` at `0x180008053`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180007e9a`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180007e9a`
- `GDI32!StretchDIBits` at `0x180007f0c`
- `GDI32!StretchDIBits` at `0x180007f0c`
- `GDI32!SelectObject` at `0x180007f90`
- `GDI32!SelectObject` at `0x180008060`
- `GDI32!SelectObject` at `0x180007f90`
- `GDI32!SelectObject` at `0x180008060`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTitleBar::_PaintTitle(CTitleBar *this, struct IDCompositionSurface *a2, const struct tagRECT *a3)
{
  __int64 (__fastcall *v4)(struct IDCompositionSurface *, RECT *, GUID *, __int64 *); // rbx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // ecx
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  const char *v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // r10d
  int v15; // edi
  HDC v16; // rbx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, __int64, struct tagRECT *); // rbx
  __int64 v19; // rdx
  void *v20; // rax
  HDC v21; // r15
  HGDIOBJ v22; // r12
  bool v23; // cl
  DWORD v24; // r14d
  COLORREF v25; // eax
  const WCHAR *v26; // rbx
  HDC v27; // rdi
  void *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned int LastError; // ebx
  __int64 v33; // rcx
  __int64 v34; // rcx
  _WORD *v35; // rax
  int phdc; // [rsp+20h] [rbp-E0h]
  int phdca; // [rsp+20h] [rbp-E0h]
  int phdcb; // [rsp+20h] [rbp-E0h]
  __int64 xSrc; // [rsp+28h] [rbp-D8h]
  __int64 ySrc; // [rsp+30h] [rbp-D0h]
  int ySrca; // [rsp+30h] [rbp-D0h]
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  _QWORD Bits[2]; // [rsp+78h] [rbp-88h] BYREF
  HDC hdc; // [rsp+88h] [rbp-78h] BYREF
  int v45[2]; // [rsp+90h] [rbp-70h] BYREF
  HDC hdcTarget; // [rsp+98h] [rbp-68h] BYREF
  struct IDCompositionSurface *v47; // [rsp+A0h] [rbp-60h] BYREF
  HPAINTBUFFER v48; // [rsp+A8h] [rbp-58h] BYREF
  DTTOPTS pOptions; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v50[56]; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT rcDst; // [rsp+138h] [rbp+38h] BYREF
  RECT prcTarget; // [rsp+148h] [rbp+48h] BYREF
  BITMAPINFO bmi; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v47 = a2;
  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) || *((_BYTE *)this + 572) )
    return 0;
  v42 = 0;
  v48 = 0;
  *(_QWORD *)v45 = 0;
  hdcTarget = 0;
  *(_QWORD *)&prcTarget.left = 0;
  prcTarget.right = a3->right - a3->left;
  prcTarget.bottom = a3->bottom - a3->top;
  v4 = *(__int64 (__fastcall **)(struct IDCompositionSurface *, RECT *, GUID *, __int64 *))(*(_QWORD *)a2 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v42);
  v5 = v4(v47, &prcTarget, &GUID_4ae63092_6327_4c1b_80ae_bfe12ea32b86, &v42);
  v6 = v5;
  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
    goto LABEL_8;
  if ( v5 + 2005270523 <= 2 )
  {
    *(_QWORD *)&rcDst.left = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
    if ( (int)CTitleBar::_GetDCompProvider(this, (struct IDCompProvider **)&rcDst) >= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcDst.left + 56LL))(*(_QWORD *)&rcDst.left);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
  }
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_8:
    v7 = v45[0] - prcTarget.left;
    prcTarget.left = v45[0];
    prcTarget.right += v7;
    prcTarget.bottom += v45[1] - prcTarget.top;
    prcTarget.top = v45[1];
    v8 = lambda_51ce06f7f40c69f5ac58c049d86cf455_::_lambda_51ce06f7f40c69f5ac58c049d86cf455_(
           (unsigned int)&pOptions,
           (unsigned int)&v48,
           (unsigned int)&v42,
           (unsigned int)&hdcTarget,
           (__int64)&prcTarget,
           (__int64)this,
           (__int64)&v47);
    wil::ScopeExit__lambda_51ce06f7f40c69f5ac58c049d86cf455___(v50, v8);
    if ( v42 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, HDC *))(*(_QWORD *)v42 + 88LL))(v42, 0, &hdcTarget);
      v10 = v9;
      if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
        goto LABEL_13;
      if ( v9 + 2005270523 <= 2 )
      {
        *(_QWORD *)&rcDst.left = 0;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
        if ( (int)CTitleBar::_GetDCompProvider(this, (struct IDCompProvider **)&rcDst) >= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcDst.left + 56LL))(*(_QWORD *)&rcDst.left);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
      }
      if ( (v10 & 0x80000000) == 0 )
      {
LABEL_13:
        hdc = 0;
        v48 = BeginBufferedPaint(hdcTarget, &prcTarget, BPBF_TOPDOWNDIB, 0, &hdc);
        if ( v48 )
        {
          if ( (*(_DWORD *)Feature_MicaBackdropInApplicationFrameHostTitlebar__descriptor & 4) == 0 )
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetCachedFeatureEnabledState(
              v11,
              Bits);
          rcDst.left = 0;
          LOWORD(rcDst.top) = 3;
          LODWORD(Bits[0]) = 3;
          v13 = wil_details_MapReportingKind(3, 1);
          if ( (unsigned int)wil::details::ReportUsageToServiceDirect(
                               (__int64)&qword_180092230,
                               0x22073B3u,
                               (v14 >> 10) & 1,
                               (v14 >> 11) & 1,
                               v13,
                               xSrc,
                               ySrc,
                               3u)
            && g_wil_details_pfnFeatureLoggingHook )
          {
            LOBYTE(ySrca) = 0;
            g_wil_details_pfnFeatureLoggingHook(35681203, &rcDst, 0, 1, Bits, 0, ySrca, 1);
          }
          if ( !*((_QWORD *)this + 53)
            || *((_BYTE *)this + 569)
            || *((_BYTE *)this + 566)
            || *((_BYTE *)this + 565)
            || *((_BYTE *)this + 575)
            || CTitleBar::_IsTitleBarColorized(this)
            || (unsigned int)IsHighContrast() )
          {
            if ( *((_BYTE *)this + 562) )
              v15 = *((_DWORD *)this + 159);
            else
              v15 = *((_DWORD *)this + 160);
            v16 = hdc;
            memset(&bmi.bmiHeader.biSizeImage, 0, 24);
            bmi.bmiHeader.biSize = 40;
            bmi.bmiHeader.biWidth = 1;
            bmi.bmiHeader.biHeight = 1;
            *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
            rcDst = 0;
            CopyRect(&rcDst, &prcTarget);
            BYTE3(Bits[0]) = -1;
            BYTE1(Bits[0]) = BYTE1(v15);
            BYTE2(Bits[0]) = v15;
            LOBYTE(Bits[0]) = BYTE2(v15);
            StretchDIBits(
              v16,
              rcDst.left,
              rcDst.top,
              rcDst.right - rcDst.left,
              rcDst.bottom - rcDst.top,
              0,
              0,
              1,
              1,
              Bits,
              &bmi,
              0,
              0xCC0020u);
          }
          v35 = (_WORD *)*((_QWORD *)this + 57);
          if ( v35
            && *v35
            && (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 24LL))(*((_QWORD *)this + 45)) )
          {
            *(_QWORD *)&rcDst.left = 0;
            v17 = *((_QWORD *)this + 45);
            v18 = *(int (__fastcall **)(__int64, __int64, struct tagRECT *))(*(_QWORD *)v17 + 32LL);
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
            if ( v18(v17, v19, &rcDst) >= 0 )
            {
              v20 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&rcDst.left + 24LL))(*(_QWORD *)&rcDst.left);
              v21 = hdc;
              Bits[0] = hdc;
              v22 = SelectObject(hdc, v20);
              Bits[1] = v22;
              v23 = *((_BYTE *)this + 559) || *((_BYTE *)this + 560);
              v24 = 165926;
              if ( !v23 )
                v24 = 34852;
              pOptions.dwSize = 72;
              memset(&pOptions.dwFlags, 0, 68);
              pOptions.dwFlags = 8193;
              if ( *((_BYTE *)this + 562) )
                v25 = *((_DWORD *)this + 161);
              else
                v25 = *((_DWORD *)this + 162);
              pOptions.crText = v25;
              v26 = (const WCHAR *)*((_QWORD *)this + 57);
              v27 = hdc;
              v28 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 45) + 24LL))(*((_QWORD *)this + 45));
              DrawThemeTextEx(v28, v27, 0, 0, v26, -1, v24, &prcTarget, &pOptions);
              SelectObject(v21, v22);
            }
            v29 = *(_QWORD *)&rcDst.left;
            if ( *(_QWORD *)&rcDst.left )
            {
              *(_QWORD *)&rcDst.left = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
          }
          wil::details::ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___::_ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___(v50);
          v30 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          return 0;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xC12,
                      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
                      v12);
        wil::details::ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___::_ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___(v50);
        v33 = v42;
        if ( v42 )
        {
          v42 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        return LastError;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF37,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
          (const char *)v10,
          phdc);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0D,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
          (const char *)v10,
          phdcb);
        wil::details::ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___::_ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___(v50);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v42);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0B,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)0x8007000ELL,
        phdc);
      wil::details::ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___::_ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___(v50);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v42);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF37,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)v6,
      (int)v45);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBFB,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)v6,
      phdca);
    v34 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180007c10  mov     [rsp-8+arg_18], rbx
0x180007c15  push    rbp
0x180007c16  push    rsi
0x180007c17  push    rdi
0x180007c18  push    r12
0x180007c1a  push    r13
0x180007c1c  push    r14
0x180007c1e  push    r15
0x180007c20  lea     rbp, [rsp-90h]
0x180007c28  sub     rsp, 190h
0x180007c2f  mov     rax, cs:__security_cookie
0x180007c36  xor     rax, rsp
0x180007c39  mov     [rbp+0C0h+var_38], rax
0x180007c40  mov     rsi, rcx
0x180007c43  mov     [rbp+0C0h+var_120], rdx
0x180007c47  cmp     byte ptr [rcx+22Eh], 0
0x180007c4e  jnz     loc_1800080A7
0x180007c54  cmp     byte ptr [rcx+240h], 0
0x180007c5b  jnz     loc_1800080A7
0x180007c61  cmp     byte ptr [rcx+23Ch], 0
0x180007c68  jnz     loc_1800080A7
0x180007c6e  xor     r13d, r13d
0x180007c71  mov     [rsp+1C0h+var_150], r13
0x180007c76  mov     [rbp+0C0h+var_118], r13
0x180007c7a  mov     qword ptr [rbp+0C0h+var_130], r13
0x180007c7e  mov     [rbp+0C0h+hdcTarget], r13
0x180007c82  mov     qword ptr [rbp+0C0h+prcTarget.left], r13
0x180007c86  mov     eax, [r8+8]
0x180007c8a  sub     eax, [r8]
0x180007c8d  mov     [rbp+0C0h+prcTarget.right], eax
0x180007c90  mov     eax, [r8+0Ch]
0x180007c94  sub     eax, [r8+4]
0x180007c98  mov     [rbp+0C0h+prcTarget.bottom], eax
0x180007c9b  mov     rax, [rdx]
0x180007c9e  mov     rbx, [rax+18h]
0x180007ca2  lea     rcx, [rsp+1C0h+var_150]
0x180007ca7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180007cac  lea     rax, [rbp+0C0h+var_130]
0x180007cb0  mov     [rsp+1C0h+phdc], rax; int
0x180007cb5  lea     r9, [rsp+1C0h+var_150]
0x180007cba  lea     r8, _GUID_4ae63092_6327_4c1b_80ae_bfe12ea32b86
0x180007cc1  lea     rdx, [rbp+0C0h+prcTarget]
0x180007cc5  mov     rcx, [rbp+0C0h+var_120]
0x180007cc9  mov     rax, rbx
0x180007ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd1  mov     ebx, eax
0x180007cd3  cmp     [rsi+22Eh], r13b
0x180007cda  jnz     short loc_180007CFC
0x180007cdc  cmp     [rsi+240h], r13b
0x180007ce3  jnz     short loc_180007CFC
0x180007ce5  lea     ecx, [rax+7785FFFBh]
0x180007ceb  cmp     ecx, 2
0x180007cee  jbe     loc_1800081ED
0x180007cf4  test    ebx, ebx
0x180007cf6  js      loc_180008193
0x180007cfc  mov     r8d, [rbp+0C0h+var_130+4]
0x180007d00  mov     edx, [rbp+0C0h+prcTarget.top]
0x180007d03  sub     r8d, edx
0x180007d06  mov     ecx, [rbp+0C0h+var_130]
0x180007d09  mov     eax, [rbp+0C0h+prcTarget.left]
0x180007d0c  sub     ecx, eax
0x180007d0e  add     eax, ecx
0x180007d10  mov     [rbp+0C0h+prcTarget.left], eax
0x180007d13  add     [rbp+0C0h+prcTarget.right], ecx
0x180007d16  add     [rbp+0C0h+prcTarget.bottom], r8d
0x180007d1a  add     edx, r8d
0x180007d1d  mov     [rbp+0C0h+prcTarget.top], edx
0x180007d20  lea     rax, [rbp+0C0h+var_120]
0x180007d24  mov     qword ptr [rsp+1C0h+ySrc], rax
0x180007d29  mov     qword ptr [rsp+1C0h+xSrc], rsi
0x180007d2e  lea     rax, [rbp+0C0h+prcTarget]
0x180007d32  mov     [rsp+1C0h+phdc], rax; int
0x180007d37  lea     r9, [rbp+0C0h+hdcTarget]
0x180007d3b  lea     r8, [rsp+1C0h+var_150]
0x180007d40  lea     rdx, [rbp+0C0h+var_118]
0x180007d44  lea     rcx, [rbp+0C0h+pOptions]
0x180007d48  call    _lambda_51ce06f7f40c69f5ac58c049d86cf455____lambda_51ce06f7f40c69f5ac58c049d86cf455_
0x180007d4d  mov     rdx, rax
0x180007d50  lea     rcx, [rbp+0C0h+var_C0]
0x180007d54  call    wil__ScopeExit__lambda_51ce06f7f40c69f5ac58c049d86cf455___
0x180007d59  nop
0x180007d5a  mov     rcx, [rsp+1C0h+var_150]
0x180007d5f  test    rcx, rcx
0x180007d62  jz      loc_180008229
0x180007d68  mov     rax, [rcx]
0x180007d6b  lea     r8, [rbp+0C0h+hdcTarget]
0x180007d6f  xor     edx, edx
0x180007d71  mov     rax, [rax+58h]
0x180007d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7a  mov     ebx, eax
0x180007d7c  cmp     byte ptr [rsi+22Eh], 0
0x180007d83  jnz     short loc_180007DA5
0x180007d85  cmp     byte ptr [rsi+240h], 0
0x180007d8c  jnz     short loc_180007DA5
0x180007d8e  lea     ecx, [rax+7785FFFBh]
0x180007d94  cmp     ecx, 2
0x180007d97  jbe     loc_180008266
0x180007d9d  test    ebx, ebx
0x180007d9f  js      loc_1800082A2
0x180007da5  mov     [rbp+0C0h+hdc], r13
0x180007da9  lea     rax, [rbp+0C0h+hdc]
0x180007dad  mov     [rsp+1C0h+phdc], rax; phdc
0x180007db2  xor     r9d, r9d; pPaintParams
0x180007db5  mov     r8d, 2; dwFormat
0x180007dbb  lea     rdx, [rbp+0C0h+prcTarget]; prcTarget
0x180007dbf  mov     rcx, [rbp+0C0h+hdcTarget]; hdcTarget
0x180007dc3  call    cs:__imp_BeginBufferedPaint
0x180007dc9  mov     [rbp+0C0h+var_118], rax
0x180007dcd  test    rax, rax
0x180007dd0  jz      loc_18000813D
0x180007dd6  mov     rax, cs:Feature_MicaBackdropInApplicationFrameHostTitlebar__descriptor
0x180007ddd  mov     r10d, [rax]
0x180007de0  test    r10b, 4
0x180007de4  jz      loc_18000812B
0x180007dea  mov     [rbp+0C0h+rcDst.left], r13d
0x180007dee  mov     word ptr [rbp+0C0h+rcDst.top], 3
0x180007df4  mov     dword ptr [rsp+1C0h+Bits], 3
0x180007dfc  mov     r14d, 1
0x180007e02  mov     edx, r14d
0x180007e05  mov     ecx, 3
0x180007e0a  call    wil_details_MapReportingKind
0x180007e0f  mov     r9d, r10d
0x180007e12  shr     r9d, 0Bh
0x180007e16  and     r9d, r14d
0x180007e19  shr     r10d, 0Ah
0x180007e1d  and     r10d, r14d
0x180007e20  mov     byte ptr [rsp+1C0h+SrcWidth], 3
0x180007e25  mov     dword ptr [rsp+1C0h+phdc], eax
0x180007e29  mov     r8d, r10d
0x180007e2c  mov     edx, 22073B3h
0x180007e31  lea     rcx, qword_180092230
0x180007e38  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180007e3d  test    eax, eax
0x180007e3f  jnz     loc_1800080E9
0x180007e45  cmp     qword ptr [rsi+1A8h], 0
0x180007e4d  jnz     loc_1800082F4
0x180007e53  cmp     byte ptr [rsi+232h], 0
0x180007e5a  jnz     loc_1800080DE
0x180007e60  mov     edi, [rsi+280h]
0x180007e66  mov     rbx, [rbp+0C0h+hdc]
0x180007e6a  xorps   xmm0, xmm0
0x180007e6d  movdqu  xmmword ptr [rbp+0C0h+bmi.bmiHeader.biSizeImage], xmm0
0x180007e72  mov     qword ptr [rbp+0C0h+bmi.bmiHeader.biClrImportant], r13
0x180007e76  mov     [rbp+0C0h+bmi.bmiHeader.biSize], 28h ; '('
0x180007e7d  mov     [rbp+0C0h+bmi.bmiHeader.biWidth], r14d
0x180007e81  mov     [rbp+0C0h+bmi.bmiHeader.biHeight], r14d
0x180007e85  mov     qword ptr [rbp+0C0h+bmi.bmiHeader.biPlanes], 200001h
0x180007e8d  movdqu  xmmword ptr [rbp+0C0h+rcDst.left], xmm0
0x180007e92  lea     rdx, [rbp+0C0h+prcTarget]; lprcSrc
0x180007e96  lea     rcx, [rbp+0C0h+rcDst]; lprcDst
0x180007e9a  call    cs:__imp_CopyRect
0x180007ea0  mov     byte ptr [rsp+1C0h+Bits+3], 0FFh
0x180007ea5  mov     byte ptr [rsp+1C0h+Bits+2], dil
0x180007eaa  movzx   eax, di
0x180007ead  shr     ax, 8
0x180007eb1  mov     byte ptr [rsp+1C0h+Bits+1], al
0x180007eb5  shr     edi, 10h
0x180007eb8  mov     byte ptr [rsp+1C0h+Bits], dil
0x180007ebd  mov     eax, [rbp+0C0h+rcDst.bottom]
0x180007ec0  mov     r8d, [rbp+0C0h+rcDst.top]; yDest
0x180007ec4  sub     eax, r8d
0x180007ec7  mov     r9d, [rbp+0C0h+rcDst.right]
0x180007ecb  mov     edx, [rbp+0C0h+rcDst.left]; xDest
0x180007ece  sub     r9d, edx; DestWidth
0x180007ed1  mov     [rsp+1C0h+rop], 0CC0020h; rop
0x180007ed9  mov     [rsp+1C0h+iUsage], r13d; iUsage
0x180007ede  lea     rcx, [rbp+0C0h+bmi]
0x180007ee2  mov     [rsp+1C0h+lpbmi], rcx; lpbmi
0x180007ee7  lea     rcx, [rsp+1C0h+Bits]
0x180007eec  mov     [rsp+1C0h+lpBits], rcx; lpBits
0x180007ef1  mov     [rsp+1C0h+SrcHeight], r14d; SrcHeight
0x180007ef6  mov     [rsp+1C0h+SrcWidth], r14d; SrcWidth
0x180007efb  mov     [rsp+1C0h+ySrc], r13d; ySrc
0x180007f00  mov     [rsp+1C0h+xSrc], r13d; xSrc
0x180007f05  mov     dword ptr [rsp+1C0h+phdc], eax; DestHeight
0x180007f09  mov     rcx, rbx; hdc
0x180007f0c  call    cs:__imp_StretchDIBits
0x180007f12  jmp     loc_180008345
0x180007f17  mov     rcx, [rsi+168h]
0x180007f1e  mov     rax, [rcx]
0x180007f21  mov     rax, [rax+18h]
0x180007f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2a  test    rax, rax
0x180007f2d  jz      loc_180008081
0x180007f33  mov     qword ptr [rbp+0C0h+rcDst.left], r13
0x180007f37  mov     rdi, [rsi+168h]
0x180007f3e  mov     rax, [rdi]
0x180007f41  mov     rbx, [rax+20h]
0x180007f45  lea     rcx, [rbp+0C0h+rcDst]
0x180007f49  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180007f4e  movd    xmm1, dword ptr [rsi+210h]
0x180007f56  cvtdq2pd xmm1, xmm1
0x180007f5a  lea     r8, [rbp+0C0h+rcDst]
0x180007f5e  mov     rcx, rdi
0x180007f61  mov     rax, rbx
0x180007f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f69  test    eax, eax
0x180007f6b  js      loc_180008067
0x180007f71  mov     rcx, qword ptr [rbp+0C0h+rcDst.left]
0x180007f75  mov     rax, [rcx]
0x180007f78  mov     rax, [rax+18h]
0x180007f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f81  mov     r15, [rbp+0C0h+hdc]
0x180007f85  mov     [rsp+1C0h+Bits], r15
0x180007f8a  mov     rdx, rax; h
0x180007f8d  mov     rcx, r15; hdc
0x180007f90  call    cs:__imp_SelectObject
0x180007f96  mov     r12, rax
0x180007f99  mov     [rbp+0C0h+var_140], rax
0x180007f9d  cmp     byte ptr [rsi+22Fh], 0
0x180007fa4  jnz     loc_18000835A
0x180007faa  cmp     byte ptr [rsi+230h], 0
0x180007fb1  jnz     loc_18000835A
0x180007fb7  xor     cl, cl
0x180007fb9  mov     eax, 8824h
0x180007fbe  mov     r14d, 28826h
0x180007fc4  test    cl, cl
0x180007fc6  cmovz   r14d, eax
0x180007fca  mov     [rbp+0C0h+pOptions.dwSize], 48h ; 'H'
0x180007fd1  xorps   xmm0, xmm0
0x180007fd4  xor     eax, eax
0x180007fd6  movups  xmmword ptr [rbp+0C0h+pOptions.dwFlags], xmm0
0x180007fda  movups  xmmword ptr [rbp+0C0h+pOptions.iTextShadowType], xmm0
0x180007fde  movups  xmmword ptr [rbp+0C0h+pOptions.iFontPropId], xmm0
0x180007fe2  movups  xmmword ptr [rbp+0C0h+pOptions.iGlowSize], xmm0
0x180007fe6  mov     dword ptr [rbp+0C0h+pOptions.lParam+4], eax
0x180007fe9  mov     [rbp+0C0h+pOptions.dwFlags], 2001h
0x180007ff0  cmp     [rsi+232h], al
0x180007ff6  jz      loc_1800080D3
0x180007ffc  mov     eax, [rsi+284h]
0x180008002  mov     [rbp+0C0h+pOptions.crText], eax
0x180008005  mov     rbx, [rsi+1C8h]
0x18000800c  mov     rdi, [rbp+0C0h+hdc]
0x180008010  mov     rcx, [rsi+168h]
0x180008017  mov     rax, [rcx]
0x18000801a  mov     rax, [rax+18h]
0x18000801e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008023  lea     rcx, [rbp+0C0h+pOptions]
0x180008027  mov     qword ptr [rsp+1C0h+SrcHeight], rcx; pOptions
0x18000802c  lea     rcx, [rbp+0C0h+prcTarget]
0x180008030  mov     qword ptr [rsp+1C0h+SrcWidth], rcx; pRect
0x180008035  mov     [rsp+1C0h+ySrc], r14d; dwTextFlags
0x18000803a  mov     [rsp+1C0h+xSrc], 0FFFFFFFFh; cchText
0x180008042  mov     [rsp+1C0h+phdc], rbx; pszText
0x180008047  xor     r9d, r9d; iStateId
0x18000804a  xor     r8d, r8d; iPartId
0x18000804d  mov     rdx, rdi; hdc
0x180008050  mov     rcx, rax; hTheme
0x180008053  call    cs:__imp_DrawThemeTextEx
0x180008059  nop
0x18000805a  mov     rdx, r12; h
0x18000805d  mov     rcx, r15; hdc
0x180008060  call    cs:__imp_SelectObject
0x180008066  nop
0x180008067  mov     rcx, qword ptr [rbp+0C0h+rcDst.left]
0x18000806b  test    rcx, rcx
0x18000806e  jz      short loc_180008081
0x180008070  mov     qword ptr [rbp+0C0h+rcDst.left], r13
0x180008074  mov     rax, [rcx]
0x180008077  mov     rax, [rax+10h]
0x18000807b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008080  nop
0x180008081  lea     rcx, [rbp+0C0h+var_C0]
0x180008085  call    wil__details__ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455______ScopeExitFn__lambda_51ce06f7f40c69f5ac58c049d86cf455___
0x18000808a  nop
0x18000808b  mov     rcx, [rsp+1C0h+var_150]
0x180008090  test    rcx, rcx
0x180008093  jz      short loc_1800080A7
0x180008095  mov     [rsp+1C0h+var_150], r13
0x18000809a  mov     rax, [rcx]
0x18000809d  mov     rax, [rax+10h]
0x1800080a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a6  nop
0x1800080a7  xor     eax, eax
0x1800080a9  mov     rcx, [rbp+0C0h+var_38]
0x1800080b0  xor     rcx, rsp; StackCookie
0x1800080b3  call    __security_check_cookie
0x1800080b8  mov     rbx, [rsp+1C0h+arg_18]
0x1800080c0  add     rsp, 190h
0x1800080c7  pop     r15
0x1800080c9  pop     r14
0x1800080cb  pop     r13
0x1800080cd  pop     r12
0x1800080cf  pop     rdi
0x1800080d0  pop     rsi
0x1800080d1  pop     rbp
0x1800080d2  retn
0x1800080d3  mov     eax, [rsi+288h]
0x1800080d9  jmp     loc_180008002
0x1800080de  mov     edi, [rsi+27Ch]
0x1800080e4  jmp     loc_180007E66
0x1800080e9  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800080f0  test    rax, rax
0x1800080f3  jz      loc_180007E45
0x1800080f9  mov     qword ptr [rsp+1C0h+SrcWidth], r14
0x1800080fe  mov     byte ptr [rsp+1C0h+ySrc], 0
0x180008103  mov     qword ptr [rsp+1C0h+xSrc], r13
0x180008108  lea     rdx, [rsp+1C0h+Bits]
0x18000810d  mov     [rsp+1C0h+phdc], rdx
0x180008112  mov     r9d, r14d
  ... truncated ...
```
