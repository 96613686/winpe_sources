# CTitleBar::_PaintButton(IDCompositionSurface *,CTitleBar::TitleBarControl,TITLE_BAR_BITMAP_TYPE,tagRECT const &,tagRECT const &)

- ea: `0x180008370`
- end: `0x180008cda`
- name: `?_PaintButton@CTitleBar@@AEAAJPEAUIDCompositionSurface@@W4TitleBarControl@1@W4TITLE_BAR_BITMAP_TYPE@@AEBUtagRECT@@3@Z`
- size: `2410`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009e40`

## callees

- `0x180004c98`
- `0x180007b30`
- `0x180008370`
- `0x180008d90`
- `0x180008e70`
- `0x1800092dc`
- `0x18000ad80`
- `0x18000d668`
- `0x18000da80`
- `0x18002d354`
- `0x18002df70`
- `0x180040270`
- `0x180043c30`
- `0x18004c498`
- `0x18005aeb8`
- `0x180072010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18000868f`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18000868f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180008765`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180008765`
- `GDI32!StretchDIBits` at `0x180008730`
- `GDI32!StretchDIBits` at `0x180008730`
- `GDI32!GetObjectW` at `0x180008890`
- `GDI32!GetObjectW` at `0x180008890`
- `GDI32!DeleteObject` at `0x1800083d3`
- `GDI32!DeleteObject` at `0x1800083d3`
- `GDI32!SelectObject` at `0x180008870`
- `GDI32!SelectObject` at `0x18000893b`
- `GDI32!SelectObject` at `0x180008870`
- `GDI32!SelectObject` at `0x18000893b`
- `GDI32!GdiAlphaBlend` at `0x18000892f`
- `GDI32!GdiAlphaBlend` at `0x18000892f`
- `GDI32!DeleteDC` at `0x180008944`
- `GDI32!DeleteDC` at `0x180008944`
- `GDI32!CreateCompatibleDC` at `0x180008858`
- `GDI32!CreateCompatibleDC` at `0x180008858`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CTitleBar::_PaintButton(__int64 a1, __int64 a2, int a3, int a4, int *a5, int *a6)
{
  float v6; // xmm3_4
  __int64 v7; // r15
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64, RECT *, GUID *, __int64 *); // rbx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int v14; // r12d
  int v15; // r13d
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int *v18; // rax
  __int64 v19; // rcx
  unsigned int Color; // r14d
  unsigned int v21; // r8d
  unsigned int v22; // edx
  unsigned int v23; // edi
  LONG v24; // r9d
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // r10d
  HDC v28; // rdi
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64, _QWORD); // r14
  __int64 v31; // r8
  void *v32; // rbx
  unsigned int v33; // eax
  unsigned int v34; // edi
  HDC CompatibleDC; // rax
  HDC v36; // rdi
  HGDIOBJ v37; // r14
  const char *v38; // r9
  int v39; // r10d
  bool IsMicaBackdropEnabled; // al
  int v41; // ecx
  int v42; // eax
  unsigned int v43; // r8d
  LONG left; // eax
  int DestHeight; // [rsp+20h] [rbp-E0h]
  int *DestHeighta; // [rsp+20h] [rbp-E0h]
  int DestHeightb; // [rsp+20h] [rbp-E0h]
  int DestHeightd; // [rsp+20h] [rbp-E0h]
  int DestHeighte; // [rsp+20h] [rbp-E0h]
  int DestHeightc; // [rsp+20h] [rbp-E0h]
  unsigned int Bits; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+74h] [rbp-8Ch]
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  LONG v54; // [rsp+80h] [rbp-80h] BYREF
  __int16 v55; // [rsp+84h] [rbp-7Ch]
  struct IDCompProvider *v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  int v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A4h] [rbp-5Ch]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  int v64[2]; // [rsp+B0h] [rbp-50h] BYREF
  HDC hdc; // [rsp+B8h] [rbp-48h] BYREF
  void *v66; // [rsp+C0h] [rbp-40h]
  __int64 *v67; // [rsp+C8h] [rbp-38h]
  char v68; // [rsp+D0h] [rbp-30h]
  struct tagRECT rcDst; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v70; // [rsp+E8h] [rbp-18h]
  RECT rcSrc; // [rsp+F8h] [rbp-8h] BYREF
  BITMAPINFO bmi; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  LODWORD(v66) = a4;
  v7 = a3;
  v57 = a2;
  if ( *(_BYTE *)(a1 + 558) || *(_BYTE *)(a1 + 576) || *(_BYTE *)(a1 + 572) )
    return 0;
  if ( a3 >= 14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB73,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      DestHeight);
    return 2147942487LL;
  }
  else
  {
    v53 = 0;
    *(_QWORD *)v64 = 0;
    hdc = 0;
    v59 = *a5;
    v61 = a5[1];
    v60 = *a6;
    v62 = a6[1];
    LODWORD(v56) = a6[2];
    v63 = a6[3];
    *(_QWORD *)&rcSrc.left = 0;
    rcSrc.right = a5[2] - v59;
    rcSrc.bottom = a5[3] - v61;
    v11 = *(__int64 (__fastcall **)(__int64, RECT *, GUID *, __int64 *))(*(_QWORD *)a2 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    DestHeighta = v64;
    v12 = v11(v57, &rcSrc, &GUID_4ae63092_6327_4c1b_80ae_bfe12ea32b86, &v53);
    v13 = v12;
    if ( *(_BYTE *)(a1 + 558) || *(_BYTE *)(a1 + 576) )
      goto LABEL_17;
    if ( v12 + 2005270523 <= 2 )
    {
      *(_QWORD *)&rcDst.left = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
      if ( (int)CTitleBar::_GetDCompProvider((CTitleBar *)a1, (struct IDCompProvider **)&rcDst) >= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcDst.left + 56LL))(*(_QWORD *)&rcDst.left);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
    }
    if ( (v13 & 0x80000000) == 0 )
    {
LABEL_17:
      v67 = &v57;
      v68 = 1;
      if ( v53 )
      {
        v14 = v64[1];
        v15 = v64[0];
        rcSrc.left += v64[0];
        rcSrc.right += v64[0];
        rcSrc.bottom += v64[1];
        rcSrc.top += v64[1];
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, HDC *))(*(_QWORD *)v53 + 88LL))(v53, 0, &hdc);
        v17 = v16;
        if ( *(_BYTE *)(a1 + 558) || *(_BYTE *)(a1 + 576) )
          goto LABEL_22;
        if ( v16 + 2005270523 <= 2 )
        {
          *(_QWORD *)&rcDst.left = 0;
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
          if ( (int)CTitleBar::_GetDCompProvider((CTitleBar *)a1, (struct IDCompProvider **)&rcDst) >= 0 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcDst.left + 56LL))(*(_QWORD *)&rcDst.left);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&rcDst);
        }
        if ( (v17 & 0x80000000) == 0 )
        {
LABEL_22:
          v18 = (unsigned int *)(a1 + 692);
          if ( (_DWORD)v7 != 13 )
            v18 = (unsigned int *)(a1 + 652);
          v19 = v18[4];
          Bits = v18[4];
          Color = v18[5];
          v21 = v18[6];
          v54 = v21;
          v22 = v18[7];
          v58 = v22;
          v23 = v18[8];
          v24 = v18[9];
          rcDst.left = v24;
          if ( *(_BYTE *)(a1 + 562) )
          {
            v25 = *v18;
            v52 = v18[2];
            v19 = Bits;
          }
          else
          {
            v25 = v18[1];
            v52 = v18[3];
          }
          v26 = *(_DWORD *)(a1 + 1480);
          if ( v26 == (_DWORD)v7 && ((v39 = *(_DWORD *)(a1 + 1484), v39 == 15) || v39 == v26) )
          {
            if ( (_DWORD)v7 == 11 )
            {
              Color = CImmersiveColor::GetColor((unsigned int)(v39 == 11) + 1120);
              v42 = 0;
              if ( BYTE2(Color) + 5 * BYTE1(Color) + 2 * (unsigned int)(unsigned __int8)Color <= 0x400 )
                v42 = 0xFFFFFF;
              v52 = v42;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTCC>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_VTCC>::GetImpl'::`2'::impl);
              if ( !(unsigned int)IsHighContrast() )
              {
                if ( *(_DWORD *)(a1 + 1484) == 11 )
                {
                  Color = -434362172;
                  v52 = GDIHelpers::BlendColors((GDIHelpers *)0xE61C28C4LL, 0xB3FFFFFF, v43, v6) | 0xFF000000;
                }
                else
                {
                  Color = -14931004;
                  v52 = -1;
                }
              }
            }
            else
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl'::`2'::impl);
              IsMicaBackdropEnabled = CTitleBar::_IsMicaBackdropEnabled((CTitleBar *)a1);
              v41 = *(_DWORD *)(a1 + 1484);
              if ( IsMicaBackdropEnabled )
              {
                if ( v41 == (_DWORD)v7 )
                  Color = v23;
              }
              else
              {
                Color = Bits;
                if ( v41 == (_DWORD)v7 )
                  Color = v58;
              }
              left = v54;
              if ( v41 == (_DWORD)v7 )
                left = rcDst.left;
              v52 = left;
            }
          }
          else if ( *(_BYTE *)(a1 + 564) )
          {
            if ( (_DWORD)v7 == 4 )
            {
              Color = v22;
              v52 = v24;
            }
            else
            {
              Color = v19;
              v52 = v21;
            }
          }
          else
          {
            if ( (*(_DWORD *)Feature_MicaBackdropInApplicationFrameHostTitlebar__descriptor & 4) == 0 )
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetCachedFeatureEnabledState(
                v19,
                &rcDst);
            v54 = 0;
            v55 = 3;
            rcDst.left = 3;
            LODWORD(DestHeighta) = wil_details_MapReportingKind(3, 1);
            if ( (unsigned int)wil::details::ReportUsageToServiceDirect(
                                 &qword_180092230,
                                 35681203,
                                 (v27 >> 10) & 1,
                                 (v27 >> 11) & 1,
                                 DestHeighta)
              && g_wil_details_pfnFeatureLoggingHook )
            {
              g_wil_details_pfnFeatureLoggingHook(35681203, &v54, 0, 1, &rcDst, 0, 0, 1);
            }
            Color = v25;
            if ( CTitleBar::_IsMicaBackdropEnabled((CTitleBar *)a1) )
              Color = 0;
          }
          v28 = hdc;
          memset(&bmi.bmiHeader.biSizeImage, 0, 24);
          bmi.bmiHeader.biSize = 40;
          bmi.bmiHeader.biWidth = 1;
          bmi.bmiHeader.biHeight = 1;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          rcDst = 0;
          CopyRect(&rcDst, &rcSrc);
          HIBYTE(Bits) = HIBYTE(Color);
          BYTE2(Bits) = HIBYTE(Color) * (unsigned __int8)Color / 0xFFu;
          BYTE1(Bits) = HIBYTE(Color) * BYTE1(Color) / 0xFFu;
          LOBYTE(Bits) = HIBYTE(Color) * BYTE2(Color) / 0xFFu;
          StretchDIBits(
            v28,
            rcDst.left,
            rcDst.top,
            rcDst.right - rcDst.left,
            rcDst.bottom - rcDst.top,
            0,
            0,
            1,
            1,
            &Bits,
            &bmi,
            0,
            0xCC0020u);
          v29 = *(_QWORD *)(a1 + 360);
          v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v29 + 40LL);
          rcDst.left = 16;
          *(_QWORD *)&rcDst.top = 0;
          rcDst.bottom = 0;
          SystemParametersInfoW(0x42u, 0x10u, &rcDst, 0);
          if ( (*(_BYTE *)(a1 + 559) || *(_BYTE *)(a1 + 560))
            && (*((_BYTE *)&CTitleBar::c_ControlProperties + v7) & 8) != 0 )
          {
            LOBYTE(v31) = 1;
          }
          else
          {
            v31 = 0;
          }
          DestHeightb = *(_DWORD *)(a1 + 528);
          v32 = (void *)v30(v29, (unsigned int)v66, v31, v52);
          v66 = v32;
          if ( v32 )
          {
            CompatibleDC = CreateCompatibleDC(0);
            v36 = CompatibleDC;
            if ( CompatibleDC )
            {
              v37 = SelectObject(CompatibleDC, v32);
              rcDst = 0;
              v70 = 0;
              if ( GetObjectW(v32, 32, &rcDst) )
              {
                Bits = 33488896;
                GdiAlphaBlend(
                  hdc,
                  v15 + v60 - v59 + ((int)v56 - v60 - rcDst.top) / 2,
                  v14 + v62 - v61 + (v63 - v62 - rcDst.right) / 2,
                  rcDst.top,
                  rcDst.right,
                  v36,
                  0,
                  0,
                  rcDst.top,
                  rcDst.right,
                  (BLENDFUNCTION)33488896);
              }
              else
              {
                wil::details::in1diag3::_Log_GetLastError(
                  retaddr,
                  (void *)0xBD3,
                  (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
                  v38);
              }
              SelectObject(v36, v37);
              DeleteDC(v36);
            }
          }
          (*(void (__fastcall **)(__int64, RECT *))(*(_QWORD *)v53 + 96LL))(v53, &rcSrc);
          v68 = 0;
          v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v57 + 32LL))(v57);
          v34 = v33;
          if ( *(_BYTE *)(a1 + 558) || *(_BYTE *)(a1 + 576) )
          {
            v34 = 0;
          }
          else
          {
            if ( v33 + 2005270523 <= 2 )
            {
              v56 = 0;
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
              if ( (int)CTitleBar::_GetDCompProvider((CTitleBar *)a1, &v56) >= 0 )
                (*(void (__fastcall **)(struct IDCompProvider *))(*(_QWORD *)v56 + 56LL))(v56);
              Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
            }
            if ( (v34 & 0x80000000) != 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF37,
                (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
                (const char *)v34,
                DestHeightb);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBEA,
                (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
                (const char *)v34,
                DestHeightc);
            }
          }
          if ( v32 )
            DeleteObject(v32);
          v10 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          return v34;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF37,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
            (const char *)v17,
            (int)v64);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB87,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
            (const char *)v17,
            DestHeighte);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 32LL))(v57);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
          return v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB84,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
          (const char *)0x8007000ELL,
          (int)v64);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 32LL))(v57);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
        return 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF37,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)v13,
        (int)v64);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7F,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)v13,
        DestHeightd);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
      return v13;
    }
  }
}

```

## disassembly

```asm
0x180008370  mov     [rsp-8+arg_10], rbx
0x180008375  push    rbp
0x180008376  push    rsi
0x180008377  push    rdi
0x180008378  push    r12
0x18000837a  push    r13
0x18000837c  push    r14
0x18000837e  push    r15
0x180008380  lea     rbp, [rsp-40h]
0x180008385  sub     rsp, 140h
0x18000838c  mov     rax, cs:__security_cookie
0x180008393  xor     rax, rsp
0x180008396  mov     [rbp+70h+var_38], rax
0x18000839a  mov     dword ptr [rbp+70h+var_B0], r9d
0x18000839e  movsxd  r15, r8d
0x1800083a1  mov     rsi, rcx
0x1800083a4  mov     rax, [rbp+70h+arg_28]
0x1800083ab  mov     rcx, [rbp+70h+arg_20]
0x1800083b2  mov     [rbp+70h+var_E0], rdx
0x1800083b6  cmp     byte ptr [rsi+22Eh], 0
0x1800083bd  jz      short loc_180008423
0x1800083bf  xor     eax, eax
0x1800083c1  jmp     short loc_1800083FC
0x1800083c3  test    edi, edi
0x1800083c5  js      loc_180008CA4
0x1800083cb  test    rbx, rbx
0x1800083ce  jz      short loc_1800083DA
0x1800083d0  mov     rcx, rbx; ho
0x1800083d3  call    cs:__imp_DeleteObject
0x1800083d9  nop
0x1800083da  mov     rcx, [rsp+170h+var_F8]
0x1800083df  test    rcx, rcx
0x1800083e2  jz      short loc_1800083FA
0x1800083e4  mov     [rsp+170h+var_F8], 0
0x1800083ed  mov     rdx, [rcx]
0x1800083f0  mov     rax, [rdx+10h]
0x1800083f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f9  nop
0x1800083fa  mov     eax, edi
0x1800083fc  mov     rcx, [rbp+70h+var_38]
0x180008400  xor     rcx, rsp; StackCookie
0x180008403  call    __security_check_cookie
0x180008408  mov     rbx, [rsp+170h+arg_10]
0x180008410  add     rsp, 140h
0x180008417  pop     r15
0x180008419  pop     r14
0x18000841b  pop     r13
0x18000841d  pop     r12
0x18000841f  pop     rdi
0x180008420  pop     rsi
0x180008421  pop     rbp
0x180008422  retn
0x180008423  cmp     byte ptr [rsi+240h], 0
0x18000842a  jnz     short loc_1800083BF
0x18000842c  cmp     byte ptr [rsi+23Ch], 0
0x180008433  jnz     short loc_1800083BF
0x180008435  cmp     r15d, 0Eh
0x180008439  jge     loc_180008A10
0x18000843f  xor     edi, edi
0x180008441  mov     [rsp+170h+var_F8], rdi
0x180008446  mov     qword ptr [rbp+70h+var_C0], rdi
0x18000844a  mov     [rbp+70h+hdc], rdi
0x18000844e  mov     r9d, [rcx]
0x180008451  mov     [rbp+70h+var_D4], r9d
0x180008455  mov     r10d, [rcx+4]
0x180008459  mov     [rbp+70h+var_CC], r10d
0x18000845d  mov     r8d, [rax]
0x180008460  mov     [rbp+70h+var_D0], r8d
0x180008464  mov     r8d, [rax+4]
0x180008468  mov     [rbp+70h+var_C8], r8d
0x18000846c  mov     r8d, [rax+8]
0x180008470  mov     dword ptr [rbp+70h+var_E8], r8d
0x180008474  mov     r8d, [rax+0Ch]
0x180008478  mov     [rbp+70h+var_C4], r8d
0x18000847c  mov     qword ptr [rbp+70h+rcSrc.left], rdi
0x180008480  mov     eax, [rcx+8]
0x180008483  sub     eax, r9d
0x180008486  mov     [rbp+70h+rcSrc.right], eax
0x180008489  mov     eax, [rcx+0Ch]
0x18000848c  sub     eax, r10d
0x18000848f  mov     [rbp+70h+rcSrc.bottom], eax
0x180008492  mov     rax, [rdx]
0x180008495  mov     rbx, [rax+18h]
0x180008499  lea     rcx, [rsp+170h+var_F8]
0x18000849e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800084a3  lea     rax, [rbp+70h+var_C0]
0x1800084a7  mov     qword ptr [rsp+170h+DestHeight], rax; int
0x1800084ac  lea     r9, [rsp+170h+var_F8]
0x1800084b1  lea     r8, _GUID_4ae63092_6327_4c1b_80ae_bfe12ea32b86
0x1800084b8  lea     rdx, [rbp+70h+rcSrc]
0x1800084bc  mov     rcx, [rbp+70h+var_E0]
0x1800084c0  mov     rax, rbx
0x1800084c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c8  mov     ebx, eax
0x1800084ca  cmp     [rsi+22Eh], dil
0x1800084d1  jnz     short loc_1800084F3
0x1800084d3  cmp     [rsi+240h], dil
0x1800084da  jnz     short loc_1800084F3
0x1800084dc  lea     ecx, [rax+7785FFFBh]
0x1800084e2  cmp     ecx, 2
0x1800084e5  jbe     loc_180008A35
0x1800084eb  test    ebx, ebx
0x1800084ed  js      loc_180008A71
0x1800084f3  lea     rax, [rbp+70h+var_E0]
0x1800084f7  mov     [rbp+70h+var_A8], rax
0x1800084fb  mov     [rbp+70h+var_A0], 1
0x1800084ff  mov     rcx, [rsp+170h+var_F8]
0x180008504  test    rcx, rcx
0x180008507  jz      loc_180008AB3
0x18000850d  mov     r12d, [rbp+70h+var_C0+4]
0x180008511  mov     r13d, [rbp+70h+var_C0]
0x180008515  add     [rbp+70h+rcSrc.left], r13d
0x180008519  add     [rbp+70h+rcSrc.right], r13d
0x18000851d  add     [rbp+70h+rcSrc.bottom], r12d
0x180008521  add     [rbp+70h+rcSrc.top], r12d
0x180008525  mov     rax, [rcx]
0x180008528  lea     r8, [rbp+70h+hdc]
0x18000852c  xor     edx, edx
0x18000852e  mov     rax, [rax+58h]
0x180008532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008537  mov     ebx, eax
0x180008539  cmp     byte ptr [rsi+22Eh], 0
0x180008540  jnz     short loc_180008562
0x180008542  cmp     byte ptr [rsi+240h], 0
0x180008549  jnz     short loc_180008562
0x18000854b  lea     ecx, [rax+7785FFFBh]
0x180008551  cmp     ecx, 2
0x180008554  jbe     loc_180008AF7
0x18000855a  test    ebx, ebx
0x18000855c  js      loc_180008B33
0x180008562  cmp     r15d, 0Dh
0x180008566  lea     rax, [rsi+2B4h]
0x18000856d  jz      short loc_180008576
0x18000856f  lea     rax, [rsi+28Ch]
0x180008576  mov     ecx, [rax+10h]
0x180008579  mov     [rsp+170h+Bits], ecx
0x18000857d  mov     r14d, [rax+14h]
0x180008581  mov     r8d, [rax+18h]
0x180008585  mov     [rbp+70h+var_F0], r8d
0x180008589  mov     edx, [rax+1Ch]
0x18000858c  mov     [rbp+70h+var_D8], edx
0x18000858f  mov     edi, [rax+20h]
0x180008592  mov     r9d, [rax+24h]
0x180008596  mov     [rbp+70h+rcDst.left], r9d
0x18000859a  cmp     byte ptr [rsi+232h], 0
0x1800085a1  jz      loc_18000894F
0x1800085a7  mov     ebx, [rax]
0x1800085a9  mov     ecx, [rax+8]
0x1800085ac  mov     [rsp+170h+var_FC], ecx
0x1800085b0  mov     ecx, [rsp+170h+Bits]
0x1800085b4  mov     eax, [rsi+5C8h]
0x1800085ba  cmp     eax, r15d
0x1800085bd  jz      loc_180008965
0x1800085c3  cmp     byte ptr [rsi+234h], 0
0x1800085ca  jnz     loc_180008C4A
0x1800085d0  mov     rax, cs:Feature_MicaBackdropInApplicationFrameHostTitlebar__descriptor
0x1800085d7  mov     r10d, [rax]
0x1800085da  test    r10b, 4
0x1800085de  jz      loc_1800089FF
0x1800085e4  xor     eax, eax
0x1800085e6  mov     [rbp+70h+var_F0], eax
0x1800085e9  mov     [rbp+70h+var_EC], 3
0x1800085ef  mov     [rbp+70h+rcDst.left], 3
0x1800085f6  mov     edx, 1
0x1800085fb  mov     ecx, 3
0x180008600  call    wil_details_MapReportingKind
0x180008605  mov     r9d, r10d
0x180008608  shr     r9d, 0Bh
0x18000860c  and     r9d, 1
0x180008610  shr     r10d, 0Ah
0x180008614  and     r10d, 1
0x180008618  mov     byte ptr [rsp+170h+SrcWidth], 3
0x18000861d  mov     [rsp+170h+DestHeight], eax
0x180008621  mov     r8d, r10d
0x180008624  mov     edx, 22073B3h
0x180008629  lea     rcx, qword_180092230
0x180008630  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180008635  test    eax, eax
0x180008637  jnz     loc_1800089B3
0x18000863d  mov     rcx, rsi; this
0x180008640  call    ?_IsMicaBackdropEnabled@CTitleBar@@AEBA_NXZ; CTitleBar::_IsMicaBackdropEnabled(void)
0x180008645  mov     r14d, ebx
0x180008648  xor     ecx, ecx
0x18000864a  test    al, al
0x18000864c  cmovnz  r14d, ecx
0x180008650  mov     ebx, r14d
0x180008653  shr     ebx, 18h
0x180008656  mov     rdi, [rbp+70h+hdc]
0x18000865a  xorps   xmm0, xmm0
0x18000865d  movdqu  xmmword ptr [rbp+70h+bmi.bmiHeader.biSizeImage], xmm0
0x180008662  xor     eax, eax
0x180008664  mov     qword ptr [rbp+70h+bmi.bmiHeader.biClrImportant], rax
0x180008668  mov     [rbp+70h+bmi.bmiHeader.biSize], 28h ; '('
0x18000866f  mov     ecx, 1
0x180008674  mov     [rbp+70h+bmi.bmiHeader.biWidth], ecx
0x180008677  mov     [rbp+70h+bmi.bmiHeader.biHeight], ecx
0x18000867a  mov     qword ptr [rbp+70h+bmi.bmiHeader.biPlanes], 200001h
0x180008682  movdqu  xmmword ptr [rbp+70h+rcDst.left], xmm0
0x180008687  lea     rdx, [rbp+70h+rcSrc]; lprcSrc
0x18000868b  lea     rcx, [rbp+70h+rcDst]; lprcDst
0x18000868f  call    cs:__imp_CopyRect
0x180008695  mov     byte ptr [rsp+170h+Bits+3], bl
0x180008699  movzx   ecx, r14b
0x18000869d  imul    ecx, ebx
0x1800086a0  mov     eax, 80808081h
0x1800086a5  mul     ecx
0x1800086a7  shr     edx, 7
0x1800086aa  mov     byte ptr [rsp+170h+Bits+2], dl
0x1800086ae  movzx   ecx, r14w
0x1800086b2  shr     ecx, 8
0x1800086b5  imul    ecx, ebx
0x1800086b8  mov     eax, 80808081h
0x1800086bd  mul     ecx
0x1800086bf  shr     edx, 7
0x1800086c2  mov     byte ptr [rsp+170h+Bits+1], dl
0x1800086c6  shr     r14d, 10h
0x1800086ca  movzx   ecx, r14b
0x1800086ce  imul    ecx, ebx
0x1800086d1  mov     eax, 80808081h
0x1800086d6  mul     ecx
0x1800086d8  shr     edx, 7
0x1800086db  mov     byte ptr [rsp+170h+Bits], dl
0x1800086df  mov     eax, [rbp+70h+rcDst.bottom]
0x1800086e2  mov     r8d, [rbp+70h+rcDst.top]; yDest
0x1800086e6  sub     eax, r8d
0x1800086e9  mov     r9d, [rbp+70h+rcDst.right]
0x1800086ed  mov     edx, [rbp+70h+rcDst.left]; xDest
0x1800086f0  sub     r9d, edx; DestWidth
0x1800086f3  mov     [rsp+170h+rop], 0CC0020h; rop
0x1800086fb  xor     ebx, ebx
0x1800086fd  mov     [rsp+170h+iUsage], ebx; iUsage
0x180008701  lea     rcx, [rbp+70h+bmi]
0x180008705  mov     [rsp+170h+lpbmi], rcx; lpbmi
0x18000870a  lea     rcx, [rsp+170h+Bits]
0x18000870f  mov     [rsp+170h+lpBits], rcx; lpBits
0x180008714  mov     ecx, 1
0x180008719  mov     [rsp+170h+SrcHeight], ecx; SrcHeight
0x18000871d  mov     [rsp+170h+SrcWidth], ecx; SrcWidth
0x180008721  mov     [rsp+170h+ySrc], ebx; ySrc
0x180008725  mov     [rsp+170h+xSrc], ebx; xSrc
0x180008729  mov     [rsp+170h+DestHeight], eax; DestHeight
0x18000872d  mov     rcx, rdi; hdc
0x180008730  call    cs:__imp_StretchDIBits
0x180008736  mov     rdi, [rsi+168h]
0x18000873d  mov     rax, [rdi]
0x180008740  mov     r14, [rax+28h]
0x180008744  mov     [rbp+70h+rcDst.left], 10h
0x18000874b  xor     eax, eax
0x18000874d  mov     qword ptr [rbp+70h+rcDst.top], rax
0x180008751  mov     [rbp+70h+rcDst.bottom], eax
0x180008754  xor     r9d, r9d; fWinIni
0x180008757  lea     r8, [rbp+70h+rcDst]; pvParam
0x18000875b  mov     edx, 10h; uiParam
0x180008760  mov     ecx, 42h ; 'B'; uiAction
0x180008765  call    cs:__imp_SystemParametersInfoW
0x18000876b  test    eax, eax
0x18000876d  jz      short loc_180008775
0x18000876f  mov     ebx, [rbp+70h+rcDst.top]
0x180008772  and     ebx, 1
0x180008775  mov     ecx, [rsi+210h]
0x18000877b  cmp     byte ptr [rsi+22Fh], 0
0x180008782  jnz     loc_180008C6A
0x180008788  cmp     byte ptr [rsi+230h], 0
0x18000878f  jnz     loc_180008C6A
0x180008795  xor     r8d, r8d
0x180008798  mov     byte ptr [rsp+170h+xSrc], bl
0x18000879c  mov     [rsp+170h+DestHeight], ecx; int
0x1800087a0  mov     r9d, [rsp+170h+var_FC]
0x1800087a5  mov     edx, dword ptr [rbp+70h+var_B0]
0x1800087a8  mov     rcx, rdi
0x1800087ab  mov     rax, r14
0x1800087ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087b3  mov     rbx, rax
0x1800087b6  mov     [rbp+70h+var_B0], rax
0x1800087ba  test    rax, rax
0x1800087bd  jnz     loc_180008856
0x1800087c3  mov     rcx, [rsp+170h+var_F8]
0x1800087c8  mov     rax, [rcx]
0x1800087cb  lea     rdx, [rbp+70h+rcSrc]
0x1800087cf  mov     rax, [rax+60h]
0x1800087d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d8  mov     [rbp+70h+var_A0], 0
0x1800087dc  mov     rcx, [rbp+70h+var_E0]
0x1800087e0  mov     rax, [rcx]
0x1800087e3  mov     rax, [rax+20h]
0x1800087e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ec  mov     edi, eax
0x1800087ee  cmp     byte ptr [rsi+22Eh], 0
0x1800087f5  jnz     loc_18000895E
0x1800087fb  cmp     byte ptr [rsi+240h], 0
0x180008802  jnz     loc_18000895E
0x180008808  add     eax, 7785FFFBh
0x18000880d  cmp     eax, 2
0x180008810  ja      loc_1800083C3
0x180008816  mov     [rbp+70h+var_E8], 0
0x18000881e  lea     rcx, [rbp+70h+var_E8]
0x180008822  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180008827  lea     rdx, [rbp+70h+var_E8]; struct IDCompProvider **
0x18000882b  mov     rcx, rsi; this
0x18000882e  call    ?_GetDCompProvider@CTitleBar@@AEAAJPEAPEAUIDCompProvider@@@Z; CTitleBar::_GetDCompProvider(IDCompProvider * *)
  ... truncated ...
```
