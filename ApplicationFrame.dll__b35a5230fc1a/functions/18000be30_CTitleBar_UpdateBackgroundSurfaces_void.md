# CTitleBar::_UpdateBackgroundSurfaces(void)

- ea: `0x18000be30`
- end: `0x18000ca04`
- name: `?_UpdateBackgroundSurfaces@CTitleBar@@AEAAJXZ`
- size: `3028`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009460`
- `0x1800098c0`
- `0x18000ae40`
- `0x18000b080`
- `0x180025614`
- `0x18002a2e0`

## callees

- `0x180004c98`
- `0x18000be30`
- `0x18000d668`
- `0x18000d6a8`
- `0x18002df70`
- `0x180039a68`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000c972`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000c988`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000c972`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000c988`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000c1e3`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000c1e3`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x18000c83a`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x18000c83a`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CTitleBar::_UpdateBackgroundSurfaces(CTitleBar *this, __int64 a2, __int64 a3, float a4)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // r15
  __int64 (__fastcall *v16)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, __int64 *); // rbx
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // ebx
  char v29; // al
  unsigned int SysColor; // ebx
  DWORD v31; // r15d
  __int64 v32; // rcx
  int v33; // r14d
  __int64 v34; // r12
  __int64 (__fastcall *v35)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v36; // rdi
  void (__fastcall *v37)(__int64, __int64 *); // rbx
  __int64 v38; // rdi
  void (__fastcall *v39)(__int64, __int64 *); // rbx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r15
  __int64 (__fastcall *v47)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v48; // rdi
  void (__fastcall *v49)(__int64, __int64 *); // rbx
  __int64 v50; // rdi
  void (__fastcall *v51)(__int64, __int64 *); // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v58; // eax
  unsigned int v59; // ebx
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  unsigned int v66; // r8d
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  int v73; // ecx
  __int64 v74; // rdx
  int v75; // [rsp+20h] [rbp-79h]
  unsigned int *v76; // [rsp+20h] [rbp-79h]
  unsigned int *v77; // [rsp+20h] [rbp-79h]
  __int64 v78; // [rsp+40h] [rbp-59h] BYREF
  __int64 v79; // [rsp+48h] [rbp-51h] BYREF
  __int64 v80; // [rsp+50h] [rbp-49h] BYREF
  __int64 v81; // [rsp+58h] [rbp-41h] BYREF
  __int64 v82; // [rsp+60h] [rbp-39h] BYREF
  __int64 v83; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v84[2]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE pvParam[12]; // [rsp+78h] [rbp-21h] BYREF
  int v86; // [rsp+84h] [rbp-15h]
  __int128 v87; // [rsp+88h] [rbp-11h] BYREF
  __int128 v88; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) || *((_BYTE *)this + 572) )
    return 0;
  v80 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v80);
  v80 = 0;
  *(_QWORD *)v84 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v84);
  v6 = 0;
  *(_QWORD *)v84 = 0;
  v7 = *((_QWORD *)this + 14);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)v7 + 24LL))(
           *((_QWORD *)this + 14),
           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           v84);
    v6 = *(_QWORD *)v84;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 >= 0 )
  {
    if ( v6 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_de7d7c7b_5d22_423d_9746_b6c08d291ac9,
             &v80);
      v6 = *(_QWORD *)v84;
    }
    else
    {
      v8 = -2147467259;
    }
  }
  if ( v6 )
  {
    *(_QWORD *)v84 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v8 < 0 )
  {
LABEL_121:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v80);
    return (unsigned int)v8;
  }
  v9 = *((_QWORD *)this + 31);
  if ( v9 )
  {
    *((_QWORD *)this + 31) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v79 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v80 + 88LL))(v80, &v79);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA5,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v10,
      v75);
    v64 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    return v11;
  }
  if ( !v79 )
  {
LABEL_77:
    v62 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    return 0;
  }
  if ( *((_BYTE *)this + 562) )
    v12 = *((_DWORD *)this + 159);
  else
    v12 = *((_DWORD *)this + 160);
  v13 = *((_QWORD *)this + 31);
  if ( v13 )
  {
    *((_QWORD *)this + 31) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v83 = 0;
  LODWORD(v76) = 3;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v79 + 64LL))(v79, 1, 1, 87);
  if ( v14 < 0 )
    goto LABEL_105;
  v84[0] = BYTE2(v12) | ((BYTE1(v12) | ((v12 | 0xFFFFFF00) << 8)) << 8);
  v15 = v83;
  *(_QWORD *)pvParam = 0;
  v78 = 0;
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v83 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v78);
  v76 = (unsigned int *)pvParam;
  v14 = v16(v15, 0, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v78);
  if ( v14 >= 0 )
  {
    v82 = 0;
    v17 = v78;
    v18 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v82);
    v18(v17, &v82);
    v81 = 0;
    v19 = v82;
    v20 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 320LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v81);
    v20(v19, &v81);
    *(_QWORD *)&v87 = *(_QWORD *)pvParam;
    DWORD2(v87) = 0;
    HIDWORD(v87) = *(_DWORD *)pvParam + 1;
    LODWORD(v88) = *(_DWORD *)&pvParam[4] + 1;
    DWORD1(v88) = 1;
    v76 = v84;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v81 + 384LL))(v81, v78, 0, &v87);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    v21 = v81;
    if ( v81 )
    {
      v81 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  v23 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v14 < 0 )
  {
LABEL_105:
    v24 = 0;
    v25 = v83;
  }
  else
  {
    v24 = v83;
    v25 = 0;
  }
  *((_QWORD *)this + 31) = v24;
  if ( v25 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCAE,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v14,
      (int)v76);
    v71 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    v72 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    return (unsigned int)v14;
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 120LL))(
          *((_QWORD *)this + 17),
          *((_QWORD *)this + 31));
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCAF,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v26,
      (int)v76);
    v69 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    v70 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    return v27;
  }
  v28 = 0;
  *(_DWORD *)pvParam = 16;
  *(_QWORD *)&pvParam[4] = 0;
  v86 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, pvParam, 0) )
    v28 = pvParam[4] & 1;
  v29 = *((_BYTE *)this + 562);
  if ( v28 )
  {
    v73 = 9;
    if ( !v29 )
      v73 = 19;
    SysColor = GetSysColor(v73);
    v31 = GetSysColor(3 - (*((_BYTE *)this + 562) != 0));
  }
  else
  {
    if ( v29 )
    {
      v87 = 0;
      v88 = 0;
      if ( CTitleBar::_IsTitleBarColorized(this) && (int)DwmpGetColorizationParameters(&v87) >= 0 && DWORD1(v88) )
      {
        v84[0] = 0;
        ConvertColorizationParametersToARGB((struct _DWM_COLORIZATION_PARAMETERS *)&v87, v84);
        SysColor = v84[0] & 0xFF000000 | (LOBYTE(v84[0]) << 16) | BYTE2(v84[0]) | v84[0] & 0xFF00;
      }
      else
      {
        SysColor = CImmersiveColor::GetColor(303) & 0xFFFFFF | 0x99000000;
      }
    }
    else
    {
      SysColor = CImmersiveColor::GetColor(302) & 0xFFFFFF | 0x33000000;
      if ( *((_BYTE *)this + 565) && (*((_BYTE *)this + 1456) & 8) != 0 )
        SysColor = GDIHelpers::BlendColors((GDIHelpers *)*((unsigned int *)this + 160), SysColor, v66, a4);
    }
    v31 = 0;
  }
  v32 = *((_QWORD *)this + 32);
  if ( v32 )
  {
    *((_QWORD *)this + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v81 = 0;
  LODWORD(v77) = 1;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v79 + 64LL))(v79, 1, 1, 87);
  if ( v33 < 0 )
    goto LABEL_111;
  v84[0] = (unsigned __int8)(HIBYTE(SysColor) * BYTE2(SysColor) / 0xFFu)
         | (((unsigned __int8)(HIBYTE(SysColor) * BYTE1(SysColor) / 0xFFu)
           | (((HIBYTE(SysColor) << 8) | (unsigned __int8)(HIBYTE(SysColor) * (unsigned __int8)SysColor / 0xFFu)) << 8)) << 8);
  v34 = v81;
  *(_QWORD *)pvParam = 0;
  v78 = 0;
  v35 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v81 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v78);
  v77 = (unsigned int *)pvParam;
  v33 = v35(v34, 0, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v78);
  if ( v33 >= 0 )
  {
    v82 = 0;
    v36 = v78;
    v37 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v82);
    v37(v36, &v82);
    v83 = 0;
    v38 = v82;
    v39 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 320LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v83);
    v39(v38, &v83);
    *(_QWORD *)&v87 = *(_QWORD *)pvParam;
    DWORD2(v87) = 0;
    HIDWORD(v87) = *(_DWORD *)pvParam + 1;
    LODWORD(v88) = *(_DWORD *)&pvParam[4] + 1;
    DWORD1(v88) = 1;
    v77 = v84;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v83 + 384LL))(v83, v78, 0, &v87);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
    v40 = v83;
    if ( v83 )
    {
      v83 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
  }
  v42 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  if ( v33 < 0 )
  {
LABEL_111:
    v43 = 0;
    v44 = v81;
  }
  else
  {
    v43 = v81;
    v44 = 0;
  }
  *((_QWORD *)this + 32) = v43;
  if ( v44 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( v33 < 0 )
  {
    v74 = 3254;
LABEL_119:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v74,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v33,
      (int)v77);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v79);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v80);
    return (unsigned int)v33;
  }
  v45 = *((_QWORD *)this + 33);
  if ( v45 )
  {
    *((_QWORD *)this + 33) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v81 = 0;
  LODWORD(v77) = 3;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v79 + 64LL))(v79, 1, 1, 87);
  if ( v33 < 0 )
    goto LABEL_112;
  v84[0] = BYTE2(v31) | ((BYTE1(v31) | ((v31 | 0xFFFFFF00) << 8)) << 8);
  v46 = v81;
  *(_QWORD *)pvParam = 0;
  v78 = 0;
  v47 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v81 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v78);
  v77 = (unsigned int *)pvParam;
  v33 = v47(v46, 0, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v78);
  if ( v33 >= 0 )
  {
    v82 = 0;
    v48 = v78;
    v49 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v82);
    v49(v48, &v82);
    v83 = 0;
    v50 = v82;
    v51 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 320LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v83);
    v51(v50, &v83);
    *(_QWORD *)&v87 = *(_QWORD *)pvParam;
    DWORD2(v87) = 0;
    HIDWORD(v87) = *(_DWORD *)pvParam + 1;
    LODWORD(v88) = *(_DWORD *)&pvParam[4] + 1;
    DWORD1(v88) = 1;
    v77 = v84;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v83 + 384LL))(v83, v78, 0, &v87);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v46);
    v52 = v83;
    if ( v83 )
    {
      v83 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
  }
  v54 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  if ( v33 < 0 )
  {
LABEL_112:
    v55 = 0;
    v56 = v81;
  }
  else
  {
    v55 = v81;
    v56 = 0;
  }
  *((_QWORD *)this + 33) = v55;
  if ( v56 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  if ( v33 < 0 )
  {
    v74 = 3257;
    goto LABEL_119;
  }
  if ( !*((_BYTE *)this + 432)
    || (v57 = *((_QWORD *)this + 18)) == 0
    || (v58 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 120LL))(v57, *((_QWORD *)this + 32)),
        v59 = v58,
        v58 >= 0) )
  {
    v60 = *((_QWORD *)this + 19);
    if ( !v60 )
      goto LABEL_77;
    v61 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v60 + 120LL))(v60, *((_QWORD *)this + 33));
    v8 = v61;
    if ( v61 >= 0 )
      goto LABEL_77;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC2,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v61,
      (int)v77);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v79);
    goto LABEL_121;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCBD,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
    (const char *)(unsigned int)v58,
    (int)v77);
  v67 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  }
  v68 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  }
  return v59;
}

```

## disassembly

```asm
0x18000be30  push    rbp
0x18000be32  push    rbx
0x18000be33  push    rsi
0x18000be34  push    rdi
0x18000be35  push    r12
0x18000be37  push    r13
0x18000be39  push    r14
0x18000be3b  push    r15
0x18000be3d  lea     rbp, [rsp-1Fh]
0x18000be42  sub     rsp, 0B8h
0x18000be49  mov     rax, cs:__security_cookie
0x18000be50  xor     rax, rsp
0x18000be53  mov     [rbp+57h+var_48], rax
0x18000be57  mov     rsi, rcx
0x18000be5a  cmp     byte ptr [rcx+22Eh], 0
0x18000be61  jz      short loc_18000BE85
0x18000be63  xor     eax, eax
0x18000be65  mov     rcx, [rbp+57h+var_48]
0x18000be69  xor     rcx, rsp; StackCookie
0x18000be6c  call    __security_check_cookie
0x18000be71  add     rsp, 0B8h
0x18000be78  pop     r15
0x18000be7a  pop     r14
0x18000be7c  pop     r13
0x18000be7e  pop     r12
0x18000be80  pop     rdi
0x18000be81  pop     rsi
0x18000be82  pop     rbx
0x18000be83  pop     rbp
0x18000be84  retn
0x18000be85  cmp     byte ptr [rcx+240h], 0
0x18000be8c  jnz     short loc_18000BE63
0x18000be8e  cmp     byte ptr [rcx+23Ch], 0
0x18000be95  jnz     short loc_18000BE63
0x18000be97  xor     r13d, r13d
0x18000be9a  mov     [rbp+57h+var_A0], r13
0x18000be9e  lea     rcx, [rbp+57h+var_A0]
0x18000bea2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000bea7  mov     [rbp+57h+var_A0], r13
0x18000beab  mov     qword ptr [rbp+57h+var_80], r13
0x18000beaf  lea     rcx, [rbp+57h+var_80]
0x18000beb3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000beb8  nop
0x18000beb9  mov     ecx, r13d
0x18000bebc  mov     qword ptr [rbp+57h+var_80], rcx
0x18000bec0  mov     r9, [rsi+70h]
0x18000bec4  test    r9, r9
0x18000bec7  jz      loc_18000C95B
0x18000becd  mov     rax, [r9]
0x18000bed0  lea     r8, [rbp+57h+var_80]
0x18000bed4  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18000bedb  mov     rcx, r9
0x18000bede  mov     rax, [rax+18h]
0x18000bee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee7  mov     ebx, eax
0x18000bee9  mov     rcx, qword ptr [rbp+57h+var_80]
0x18000beed  test    ebx, ebx
0x18000beef  js      short loc_18000BF16
0x18000bef1  test    rcx, rcx
0x18000bef4  jz      loc_18000C77F
0x18000befa  mov     rax, [rcx]
0x18000befd  lea     r8, [rbp+57h+var_A0]
0x18000bf01  lea     rdx, _GUID_de7d7c7b_5d22_423d_9746_b6c08d291ac9
0x18000bf08  mov     rax, [rax]
0x18000bf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf10  mov     ebx, eax
0x18000bf12  mov     rcx, qword ptr [rbp+57h+var_80]
0x18000bf16  test    rcx, rcx
0x18000bf19  jz      short loc_18000BF2C
0x18000bf1b  mov     qword ptr [rbp+57h+var_80], r13
0x18000bf1f  mov     rdx, [rcx]
0x18000bf22  mov     rax, [rdx+10h]
0x18000bf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2b  nop
0x18000bf2c  test    ebx, ebx
0x18000bf2e  js      loc_18000C9F4
0x18000bf34  mov     rcx, [rsi+0F8h]
0x18000bf3b  test    rcx, rcx
0x18000bf3e  jz      short loc_18000BF54
0x18000bf40  mov     [rsi+0F8h], r13
0x18000bf47  mov     rax, [rcx]
0x18000bf4a  mov     rax, [rax+10h]
0x18000bf4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf53  nop
0x18000bf54  mov     [rbp+57h+var_A8], r13
0x18000bf58  mov     rcx, [rbp+57h+var_A0]
0x18000bf5c  mov     rax, [rcx]
0x18000bf5f  lea     rdx, [rbp+57h+var_A8]
0x18000bf63  mov     rax, [rax+58h]
0x18000bf67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf6c  mov     ebx, eax
0x18000bf6e  test    eax, eax
0x18000bf70  js      loc_18000C72B
0x18000bf76  cmp     [rbp+57h+var_A8], 0
0x18000bf7b  jz      loc_18000C6F2
0x18000bf81  cmp     byte ptr [rsi+232h], 0
0x18000bf88  jz      loc_18000C789
0x18000bf8e  mov     ebx, [rsi+27Ch]
0x18000bf94  mov     rcx, [rsi+0F8h]
0x18000bf9b  test    rcx, rcx
0x18000bf9e  jz      short loc_18000BFB4
0x18000bfa0  mov     [rsi+0F8h], r13
0x18000bfa7  mov     rax, [rcx]
0x18000bfaa  mov     rax, [rax+10h]
0x18000bfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb3  nop
0x18000bfb4  mov     rcx, [rbp+57h+var_A8]
0x18000bfb8  mov     [rbp+57h+var_88], r13
0x18000bfbc  mov     rax, [rcx]
0x18000bfbf  lea     rdx, [rbp+57h+var_88]
0x18000bfc3  mov     [rsp+0F0h+var_C8], rdx
0x18000bfc8  mov     [rsp+0F0h+var_D0], 3
0x18000bfd0  mov     edx, 1
0x18000bfd5  mov     r9d, 57h ; 'W'
0x18000bfdb  mov     r8d, edx
0x18000bfde  mov     rax, [rax+40h]
0x18000bfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe7  mov     r14d, eax
0x18000bfea  test    eax, eax
0x18000bfec  js      loc_18000C8E2
0x18000bff2  movzx   ecx, bl
0x18000bff5  or      ecx, 0FFFFFF00h
0x18000bffb  shl     ecx, 8
0x18000bffe  movzx   eax, bx
0x18000c001  shr     eax, 8
0x18000c004  or      ecx, eax
0x18000c006  shl     ecx, 8
0x18000c009  shr     ebx, 10h
0x18000c00c  movzx   eax, bl
0x18000c00f  or      ecx, eax
0x18000c011  mov     [rbp+57h+var_80], ecx
0x18000c014  mov     r15, [rbp+57h+var_88]
0x18000c018  mov     qword ptr [rbp+57h+pvParam], r13
0x18000c01c  mov     [rbp+57h+var_B0], r13
0x18000c020  mov     rax, [r15]
0x18000c023  mov     rbx, [rax+18h]
0x18000c027  lea     rcx, [rbp+57h+var_B0]
0x18000c02b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000c030  lea     rax, [rbp+57h+pvParam]
0x18000c034  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18000c039  lea     r9, [rbp+57h+var_B0]
0x18000c03d  lea     r8, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18000c044  xor     edx, edx
0x18000c046  mov     rcx, r15
0x18000c049  mov     rax, rbx
0x18000c04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c051  mov     r14d, eax
0x18000c054  test    eax, eax
0x18000c056  js      loc_18000C14B
0x18000c05c  mov     [rbp+57h+var_90], r13
0x18000c060  mov     rdi, [rbp+57h+var_B0]
0x18000c064  mov     rax, [rdi]
0x18000c067  mov     rbx, [rax+18h]
0x18000c06b  lea     rcx, [rbp+57h+var_90]
0x18000c06f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000c074  lea     rdx, [rbp+57h+var_90]
0x18000c078  mov     rcx, rdi
0x18000c07b  mov     rax, rbx
0x18000c07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c083  mov     [rbp+57h+var_98], r13
0x18000c087  mov     rdi, [rbp+57h+var_90]
0x18000c08b  mov     rax, [rdi]
0x18000c08e  mov     rbx, [rax+140h]
0x18000c095  lea     rcx, [rbp+57h+var_98]
0x18000c099  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000c09e  lea     rdx, [rbp+57h+var_98]
0x18000c0a2  mov     rcx, rdi
0x18000c0a5  mov     rax, rbx
0x18000c0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ad  mov     rax, qword ptr [rbp+57h+pvParam]
0x18000c0b1  mov     dword ptr [rbp+57h+var_68], eax
0x18000c0b4  mov     ecx, dword ptr [rbp+57h+pvParam+4]
0x18000c0b7  mov     dword ptr [rbp+57h+var_68+4], ecx
0x18000c0ba  mov     dword ptr [rbp+57h+var_68+8], r13d
0x18000c0be  inc     eax
0x18000c0c0  mov     dword ptr [rbp+57h+var_68+0Ch], eax
0x18000c0c3  lea     eax, [rcx+1]
0x18000c0c6  mov     dword ptr [rbp+57h+var_58], eax
0x18000c0c9  mov     dword ptr [rbp+57h+var_58+4], 1
0x18000c0d0  mov     rcx, [rbp+57h+var_98]
0x18000c0d4  mov     rax, [rcx]
0x18000c0d7  mov     [rsp+0F0h+var_C0], 4
0x18000c0df  mov     dword ptr [rsp+0F0h+var_C8], 4
0x18000c0e7  lea     rdx, [rbp+57h+var_80]
0x18000c0eb  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x18000c0f0  lea     r9, [rbp+57h+var_68]
0x18000c0f4  xor     r8d, r8d
0x18000c0f7  mov     rdx, [rbp+57h+var_B0]
0x18000c0fb  mov     rax, [rax+180h]
0x18000c102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c107  mov     rax, [r15]
0x18000c10a  mov     rcx, r15
0x18000c10d  mov     rax, [rax+20h]
0x18000c111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c116  nop
0x18000c117  mov     rcx, [rbp+57h+var_98]
0x18000c11b  test    rcx, rcx
0x18000c11e  jz      short loc_18000C131
0x18000c120  mov     [rbp+57h+var_98], r13
0x18000c124  mov     rax, [rcx]
0x18000c127  mov     rax, [rax+10h]
0x18000c12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c130  nop
0x18000c131  mov     rcx, [rbp+57h+var_90]
0x18000c135  test    rcx, rcx
0x18000c138  jz      short loc_18000C14B
0x18000c13a  mov     [rbp+57h+var_90], r13
0x18000c13e  mov     rax, [rcx]
0x18000c141  mov     rax, [rax+10h]
0x18000c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c14a  nop
0x18000c14b  mov     rcx, [rbp+57h+var_B0]
0x18000c14f  test    rcx, rcx
0x18000c152  jz      short loc_18000C165
0x18000c154  mov     [rbp+57h+var_B0], r13
0x18000c158  mov     rax, [rcx]
0x18000c15b  mov     rax, [rax+10h]
0x18000c15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c164  nop
0x18000c165  test    r14d, r14d
0x18000c168  js      loc_18000C8E2
0x18000c16e  mov     rax, [rbp+57h+var_88]
0x18000c172  mov     rcx, r13
0x18000c175  mov     [rsi+0F8h], rax
0x18000c17c  test    rcx, rcx
0x18000c17f  jz      short loc_18000C192
0x18000c181  mov     [rbp+57h+var_88], r13
0x18000c185  mov     rax, [rcx]
0x18000c188  mov     rax, [rax+10h]
0x18000c18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c191  nop
0x18000c192  test    r14d, r14d
0x18000c195  js      loc_18000C8EE
0x18000c19b  mov     rcx, [rsi+88h]
0x18000c1a2  mov     rax, [rcx]
0x18000c1a5  mov     rdx, [rsi+0F8h]
0x18000c1ac  mov     rax, [rax+78h]
0x18000c1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1b5  mov     ebx, eax
0x18000c1b7  test    eax, eax
0x18000c1b9  js      loc_18000C88E
0x18000c1bf  mov     ebx, r13d
0x18000c1c2  mov     dword ptr [rbp+57h+pvParam], 10h
0x18000c1c9  xor     eax, eax
0x18000c1cb  mov     qword ptr [rbp+57h+pvParam+4], rax
0x18000c1cf  mov     [rbp+57h+var_6C], eax
0x18000c1d2  xor     r9d, r9d; fWinIni
0x18000c1d5  lea     r8, [rbp+57h+pvParam]; pvParam
0x18000c1d9  mov     edx, 10h; uiParam
0x18000c1de  mov     ecx, 42h ; 'B'; uiAction
0x18000c1e3  call    cs:__imp_SystemParametersInfoW
0x18000c1e9  test    eax, eax
0x18000c1eb  jz      short loc_18000C1F3
0x18000c1ed  mov     ebx, dword ptr [rbp+57h+pvParam+4]
0x18000c1f0  and     ebx, 1
0x18000c1f3  movzx   eax, byte ptr [rsi+232h]
0x18000c1fa  test    ebx, ebx
0x18000c1fc  jnz     loc_18000C963
0x18000c202  test    al, al
0x18000c204  jz      loc_18000C794
0x18000c20a  xorps   xmm0, xmm0
0x18000c20d  movups  [rbp+57h+var_68], xmm0
0x18000c211  movups  [rbp+57h+var_58], xmm0
0x18000c215  mov     rcx, rsi; this
0x18000c218  call    ?_IsTitleBarColorized@CTitleBar@@AEBA_NXZ; CTitleBar::_IsTitleBarColorized(void)
0x18000c21d  test    al, al
0x18000c21f  jnz     loc_18000C836
0x18000c225  mov     ecx, 12Fh
0x18000c22a  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x18000c22f  mov     ebx, eax
0x18000c231  and     ebx, 0FFFFFFh
0x18000c237  or      ebx, 99000000h
0x18000c23d  mov     r15d, r13d
0x18000c240  mov     rcx, [rsi+100h]
0x18000c247  test    rcx, rcx
0x18000c24a  jz      short loc_18000C260
0x18000c24c  mov     [rsi+100h], r13
0x18000c253  mov     rax, [rcx]
0x18000c256  mov     rax, [rax+10h]
0x18000c25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c25f  nop
0x18000c260  mov     rcx, [rbp+57h+var_A8]
0x18000c264  mov     [rbp+57h+var_98], r13
0x18000c268  mov     rax, [rcx]
0x18000c26b  lea     rdx, [rbp+57h+var_98]
0x18000c26f  mov     [rsp+0F0h+var_C8], rdx
0x18000c274  mov     [rsp+0F0h+var_D0], 1
0x18000c27c  mov     edx, 1
0x18000c281  mov     r9d, 57h ; 'W'
0x18000c287  mov     r8d, edx
0x18000c28a  mov     rax, [rax+40h]
0x18000c28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c293  mov     r14d, eax
0x18000c296  test    eax, eax
0x18000c298  js      loc_18000C943
0x18000c29e  mov     r9d, ebx
0x18000c2a1  shr     r9d, 18h
0x18000c2a5  movzx   ecx, bl
0x18000c2a8  imul    ecx, r9d
0x18000c2ac  mov     eax, 80808081h
  ... truncated ...
```
