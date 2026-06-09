# CTitleBarAcc::_AddChildren(void)

- ea: `0x18001e930`
- end: `0x18001f40e`
- name: `?_AddChildren@CTitleBarAcc@@AEAAXXZ`
- size: `2782`
- prototype: `void __fastcall(CTitleBarAcc *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e294`
- `0x180020cb4`
- `0x1800609c0`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x18001e930`
- `0x18001f414`
- `0x18001f550`
- `0x18001f5b4`
- `0x18001f710`
- `0x18001f780`
- `0x18001fa2c`
- `0x18001fb9c`
- `0x180020920`
- `0x180040270`
- `0x180043c30`
- `0x1800446fc`
- `0x180046b0c`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001ec93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f06f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001ec93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001f06f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18001e9ca`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18001e9ca`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001eddb`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001eea2`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001ef4b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f165`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f1dc`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f253`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f2c9`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f378`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001eddb`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001eea2`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001ef4b`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f165`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f1dc`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f253`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f2c9`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18001f378`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18001eebc`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x18001eebc`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001e9e3`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001e9fc`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea15`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea2e`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea47`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea61`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea7a`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea93`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001eaac`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001eac5`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001e9e3`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001e9fc`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea15`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea2e`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea47`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea61`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea7a`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001ea93`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001eaac`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18001eac5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CTitleBarAcc::_AddChildren(CTitleBarAcc *this)
{
  __int64 v2; // rsi
  char *v3; // rdi
  char *v4; // rcx
  int (__fastcall ***v5)(_QWORD, GUID *, _QWORD *); // rsi
  int (__fastcall *v6)(_QWORD, GUID *, _QWORD *); // rdi
  unsigned __int64 v7; // rdi
  CTitleBarSysMenuBar *v8; // rax
  CTitleBarSysMenuBar *v9; // rax
  CTitleBarSysMenuBar *v10; // rsi
  int v11; // eax
  unsigned __int64 v12; // rsi
  __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // r12
  char *v19; // rax
  char *v20; // r15
  unsigned __int64 v21; // rax
  int v22; // eax
  _QWORD *v23; // rcx
  char *v24; // rsi
  __int64 v25; // rcx
  CTitleBarButton *v26; // rax
  CTitleBarButton *v27; // rax
  CTitleBarButton *v28; // rdi
  void *v29; // rcx
  BOOL v30; // eax
  int v31; // ecx
  const struct _GUID *v32; // rdx
  void *v33; // rcx
  CTitleBarButton *v34; // rax
  CTitleBarButton *v35; // rax
  CTitleBarButton *v36; // r14
  unsigned __int64 v37; // r8
  __int64 v38; // r9
  unsigned __int64 v39; // r9
  void *v40; // rcx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // r15
  char *v43; // rax
  char *v44; // r14
  unsigned __int64 v45; // rax
  int v46; // eax
  void **v47; // rcx
  const struct _GUID *v48; // rdx
  const struct _GUID *v49; // rdx
  const struct _GUID *v50; // rdx
  const struct _GUID *v51; // rdx
  const struct _GUID *v52; // rdx
  void *v53; // [rsp+20h] [rbp-E0h] BYREF
  int v54; // [rsp+28h] [rbp-D8h] BYREF
  char *v55; // [rsp+30h] [rbp-D0h] BYREF
  char *v56; // [rsp+38h] [rbp-C8h]
  __int64 v57; // [rsp+40h] [rbp-C0h]
  RECT *p_rc; // [rsp+48h] [rbp-B8h]
  __int64 v59; // [rsp+50h] [rbp-B0h]
  _QWORD v60[3]; // [rsp+58h] [rbp-A8h] BYREF
  RECT v61; // [rsp+70h] [rbp-90h] BYREF
  RECT v62; // [rsp+80h] [rbp-80h] BYREF
  RECT v63; // [rsp+90h] [rbp-70h] BYREF
  RECT v64; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v65; // [rsp+B0h] [rbp-50h]
  __int128 v66; // [rsp+C0h] [rbp-40h]
  RECT rc; // [rsp+D0h] [rbp-30h] BYREF
  RECT v68; // [rsp+E0h] [rbp-20h] BYREF
  RECT v69; // [rsp+F0h] [rbp-10h] BYREF
  struct tagPOINT Points[2]; // [rsp+100h] [rbp+0h] BYREF
  RECT v71; // [rsp+110h] [rbp+10h] BYREF
  __int128 v72; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !*((_QWORD *)this + 22) )
    return;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  rc = 0;
  v68 = 0;
  v69 = 0;
  *(_OWORD *)&Points[0].x = 0;
  v71 = 0;
  v72 = 0;
  (*(void (__fastcall **)(_QWORD, RECT *))(**((_QWORD **)this + 28) + 208LL))(*((_QWORD *)this + 28), &v61);
  SetRectEmpty((LPRECT)((char *)this + 56));
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)this + 7, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, Points, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v64, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&rc, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v68, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v61, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v62, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v63, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v69, 2u);
  MapWindowPoints(*((HWND *)this + 22), 0, (LPPOINT)&v71, 2u);
  v2 = *((_QWORD *)this + 25);
  v3 = (char *)this + 144;
  if ( !this )
    v3 = 0;
  v4 = (char *)this + 16;
  if ( !this )
    v4 = 0;
  v55 = v4;
  if ( v4 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  v56 = v3;
  if ( v3 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
  v57 = 1;
  p_rc = &v61;
  v59 = v2;
  v54 = 0;
  v60[0] = 0;
  v5 = (int (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)this + 28);
  v6 = **v5;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v60);
  if ( v6(v5, &GUID_c8e34820_d46a_41bc_8c5c_5bc9fdee243d, v60) >= 0 )
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)v60[0] + 96LL))(v60[0], &v54);
  v7 = 4294967294LL;
  if ( *((_BYTE *)this + 265) )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 192);
    *((_QWORD *)this + 24) = 0;
    v8 = (CTitleBarSysMenuBar *)operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
    if ( !v8
      || (v9 = CTitleBarSysMenuBar::CTitleBarSysMenuBar(v8, (const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55),
          (v10 = v9) == 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebaracc.cpp",
        (const char *)0x8007000ELL,
        (int)v53);
      goto LABEL_35;
    }
    v11 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal>>(
            v9,
            &GUID_47edc87f_6c1f_4b96_9dfe_fb6d57297580,
            (char *)this + 192);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26A,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebaracc.cpp",
        (const char *)(unsigned int)v11,
        (int)v53);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal>::Release(v10);
      goto LABEL_35;
    }
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal>::Release(v10);
    v12 = *((_QWORD *)this + 32);
    v13 = *((_QWORD *)this + 30);
    if ( v13 != v12 )
      goto LABEL_32;
    v14 = v13 + 1;
    if ( v14 > 0xFFFFFFFE )
      goto LABEL_35;
    if ( v14 <= v12 )
      goto LABEL_32;
    v53 = 0;
    v15 = 2 * v12;
    if ( is_mul_ok(v12, 2u) )
    {
      v16 = v12;
      v17 = v12 + 4096;
      if ( v16 <= 0x1000 )
        v17 = v15;
      if ( v14 > v17 )
      {
        v17 = v14;
      }
      else if ( v17 > 0xFFFFFFFE )
      {
        v17 = 4294967294LL;
      }
      v53 = 0;
      v18 = 8 * v17;
      if ( is_mul_ok(v17, 8u) )
      {
        v19 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 29), 8 * v17);
        v20 = v19;
        if ( v19 )
        {
          v21 = CTCoAllocPolicy::_CoTaskMemSize(v19);
          if ( v21 > v18 )
            memset_0(&v20[v18], 0, v21 - v18);
          v22 = 0;
        }
        else
        {
          v22 = -2147024882;
        }
        if ( v22 >= 0 )
        {
          *((_QWORD *)this + 32) = v17;
          *((_QWORD *)this + 29) = v20;
LABEL_32:
          v23 = (_QWORD *)(*((_QWORD *)this + 29) + 8 * (*((_QWORD *)this + 30))++);
          if ( v23 )
          {
            *v23 = *((_QWORD *)this + 24);
            Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(v23);
          }
          ++HIDWORD(v57);
        }
      }
    }
  }
LABEL_35:
  v24 = (char *)this + 272;
  if ( (v54 & 0x80u) != 0 && *v24 < 0 && !IsRectEmpty(&v71) )
  {
    v53 = 0;
    LODWORD(v57) = 15;
    p_rc = &v71;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v48, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  }
  if ( (v54 & 0x40) != 0 && (*v24 & 0x40) != 0 && !IsRectEmpty(&v61) )
  {
    v53 = 0;
    LODWORD(v57) = 3;
    p_rc = &v61;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v49, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  }
  if ( (v54 & 8) != 0 && (*v24 & 8) != 0 && !IsRectEmpty(&v69) )
  {
    v53 = 0;
    LODWORD(v57) = 12;
    p_rc = &v69;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v50, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  }
  if ( (v54 & 0x10) != 0 && (*v24 & 0x10) != 0 && !IsRectEmpty(&v62) )
  {
    v53 = 0;
    LODWORD(v57) = 4;
    p_rc = &v62;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v51, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  }
  if ( (v54 & 1) == 0 || (*v24 & 1) == 0 || (*((_BYTE *)this + 268) & 2) != 0 || IsRectEmpty(&v64) )
    goto LABEL_40;
  v53 = 0;
  LODWORD(v57) = 6;
  p_rc = &v64;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  v53 = 0;
  v34 = (CTitleBarButton *)operator new(0x98u, (const struct std::nothrow_t *)std::nothrow);
  if ( v34
    && (v35 = CTitleBarButton::CTitleBarButton(v34, (const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55),
        (v36 = v35) != 0) )
  {
    v53 = (char *)v35 + 16;
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v35 + 2) + 8LL))((__int64)v35 + 16);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IInvokeProvider>::Release(v36);
    v37 = *((_QWORD *)this + 32);
    v38 = *((_QWORD *)this + 30);
    if ( v38 != v37 )
    {
LABEL_95:
      v47 = (void **)(*((_QWORD *)this + 29) + 8 * (*((_QWORD *)this + 30))++);
      if ( v47 )
      {
        *v47 = v53;
        Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(v47);
      }
      ++HIDWORD(v57);
      goto LABEL_78;
    }
    v39 = v38 + 1;
    if ( v39 <= 0xFFFFFFFE )
    {
      if ( v39 > v37 )
      {
        if ( !is_mul_ok(v37, 2u) )
          goto LABEL_78;
        v41 = v37 + 4096;
        if ( v37 <= 0x1000 )
          v41 = 2 * v37;
        if ( v39 <= v41 )
        {
          if ( v41 <= 0xFFFFFFFE )
            v7 = v41;
        }
        else
        {
          v7 = v39;
        }
        v42 = 8 * v7;
        if ( !is_mul_ok(v7, 8u) )
          goto LABEL_78;
        v43 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 29), 8 * v7);
        v44 = v43;
        if ( v43 )
        {
          v45 = CTCoAllocPolicy::_CoTaskMemSize(v43);
          if ( v45 > v42 )
            memset_0(&v44[v42], 0, v45 - v42);
          v46 = 0;
        }
        else
        {
          v46 = -2147024882;
        }
        if ( v46 < 0 )
          goto LABEL_78;
        *((_QWORD *)this + 32) = v7;
        *((_QWORD *)this + 29) = v44;
      }
      goto LABEL_95;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebaracc.cpp",
      (const char *)0x8007000ELL,
      (int)v53);
  }
LABEL_78:
  v40 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
  }
LABEL_40:
  if ( (v54 & 0x20) != 0 && (*v24 & 0x20) != 0 && !IsRectEmpty(&v63) )
  {
    v53 = 0;
    LODWORD(v57) = 5;
    p_rc = &v63;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v52, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
  }
  if ( (v54 & 2) != 0 && (*v24 & 2) != 0 && !IsRectEmpty(&v68) )
  {
    v53 = 0;
    v30 = IsZoomed(*((HWND *)this + 22));
    v31 = 7;
    if ( !v30 )
      v31 = 8;
    LODWORD(v57) = v31;
    p_rc = &v68;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    if ( CTitleBarButton::s_CreateInstance((const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55, v32, &v53) >= 0
      && (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                (char *)this + 232,
                &v53) >= 0 )
    {
      ++HIDWORD(v57);
    }
    v33 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
    }
  }
  if ( (v54 & 4) != 0 && (*v24 & 4) != 0 && !IsRectEmpty(&rc) )
  {
    v53 = 0;
    LODWORD(v57) = 11;
    p_rc = &rc;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v53);
    v53 = 0;
    v26 = (CTitleBarButton *)operator new(0x98u, (const struct std::nothrow_t *)std::nothrow);
    if ( v26
      && (v27 = CTitleBarButton::CTitleBarButton(v26, (const struct TITLE_BAR_ELEMENT_INIT_OPTIONS *)&v55),
          (v28 = v27) != 0) )
    {
      v53 = (char *)v27 + 16;
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v27 + 2) + 8LL))((__int64)v27 + 16);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IInvokeProvider>::Release(v28);
      if ( (int)CTSimpleArray<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>>>::_Add<Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal> const &>(
                  (char *)this + 232,
                  &v53) >= 0 )
        ++HIDWORD(v57);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebaracc.cpp",
        (const char *)0x8007000ELL,
        (int)v53);
    }
    v29 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v29 + 16LL))(v29);
    }
  }
  v25 = v60[0];
  if ( v60[0] )
  {
    v60[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( v56 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v56 + 16LL))(v56);
  if ( v55 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
}

```

## disassembly

```asm
0x18001e930  push    rbp
0x18001e932  push    rbx
0x18001e933  push    rsi
0x18001e934  push    rdi
0x18001e935  push    r12
0x18001e937  push    r13
0x18001e939  push    r14
0x18001e93b  push    r15
0x18001e93d  lea     rbp, [rsp-48h]
0x18001e942  sub     rsp, 148h
0x18001e949  mov     rax, cs:__security_cookie
0x18001e950  xor     rax, rsp
0x18001e953  mov     [rbp+80h+var_50], rax
0x18001e957  mov     rbx, rcx
0x18001e95a  cmp     qword ptr [rcx+0B0h], 0
0x18001e962  jz      loc_18001EDB2
0x18001e968  xorps   xmm0, xmm0
0x18001e96b  movdqa  xmmword ptr [rsp+180h+var_110.left], xmm0
0x18001e971  xorps   xmm1, xmm1
0x18001e974  movdqa  xmmword ptr [rbp+80h+var_100.left], xmm1
0x18001e979  movdqa  xmmword ptr [rbp+80h+var_F0.left], xmm0
0x18001e97e  movdqa  xmmword ptr [rbp+80h+var_E0.left], xmm1
0x18001e983  movdqa  [rbp+80h+var_D0], xmm0
0x18001e988  movdqa  [rbp+80h+var_C0], xmm1
0x18001e98d  movdqa  xmmword ptr [rbp+80h+rc.left], xmm0
0x18001e992  movdqa  xmmword ptr [rbp+80h+var_A0.left], xmm1
0x18001e997  movdqa  xmmword ptr [rbp+80h+var_90.left], xmm0
0x18001e99c  movdqa  xmmword ptr [rbp+80h+Points.x], xmm1
0x18001e9a1  movdqa  xmmword ptr [rbp+80h+var_70.left], xmm0
0x18001e9a6  movdqa  [rbp+80h+var_60], xmm1
0x18001e9ab  mov     rcx, [rcx+0E0h]
0x18001e9b2  mov     rax, [rcx]
0x18001e9b5  lea     rdx, [rsp+180h+var_110]
0x18001e9ba  mov     rax, [rax+0D0h]
0x18001e9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9c6  lea     rcx, [rbx+38h]; lprc
0x18001e9ca  call    cs:__imp_SetRectEmpty
0x18001e9d0  mov     r9d, 2; cPoints
0x18001e9d6  lea     r8, [rbx+38h]; lpPoints
0x18001e9da  xor     edx, edx; hWndTo
0x18001e9dc  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001e9e3  call    cs:__imp_MapWindowPoints
0x18001e9e9  mov     r9d, 2; cPoints
0x18001e9ef  lea     r8, [rbp+80h+Points]; lpPoints
0x18001e9f3  xor     edx, edx; hWndTo
0x18001e9f5  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001e9fc  call    cs:__imp_MapWindowPoints
0x18001ea02  mov     r9d, 2; cPoints
0x18001ea08  lea     r8, [rbp+80h+var_E0]; lpPoints
0x18001ea0c  xor     edx, edx; hWndTo
0x18001ea0e  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea15  call    cs:__imp_MapWindowPoints
0x18001ea1b  mov     r9d, 2; cPoints
0x18001ea21  lea     r8, [rbp+80h+rc]; lpPoints
0x18001ea25  xor     edx, edx; hWndTo
0x18001ea27  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea2e  call    cs:__imp_MapWindowPoints
0x18001ea34  mov     r9d, 2; cPoints
0x18001ea3a  lea     r8, [rbp+80h+var_A0]; lpPoints
0x18001ea3e  xor     edx, edx; hWndTo
0x18001ea40  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea47  call    cs:__imp_MapWindowPoints
0x18001ea4d  mov     r9d, 2; cPoints
0x18001ea53  lea     r8, [rsp+180h+var_110]; lpPoints
0x18001ea58  xor     edx, edx; hWndTo
0x18001ea5a  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea61  call    cs:__imp_MapWindowPoints
0x18001ea67  mov     r9d, 2; cPoints
0x18001ea6d  lea     r8, [rbp+80h+var_100]; lpPoints
0x18001ea71  xor     edx, edx; hWndTo
0x18001ea73  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea7a  call    cs:__imp_MapWindowPoints
0x18001ea80  mov     r9d, 2; cPoints
0x18001ea86  lea     r8, [rbp+80h+var_F0]; lpPoints
0x18001ea8a  xor     edx, edx; hWndTo
0x18001ea8c  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001ea93  call    cs:__imp_MapWindowPoints
0x18001ea99  mov     r9d, 2; cPoints
0x18001ea9f  lea     r8, [rbp+80h+var_90]; lpPoints
0x18001eaa3  xor     edx, edx; hWndTo
0x18001eaa5  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001eaac  call    cs:__imp_MapWindowPoints
0x18001eab2  mov     r9d, 2; cPoints
0x18001eab8  lea     r8, [rbp+80h+var_70]; lpPoints
0x18001eabc  xor     edx, edx; hWndTo
0x18001eabe  mov     rcx, [rbx+0B0h]; hWndFrom
0x18001eac5  call    cs:__imp_MapWindowPoints
0x18001eacb  mov     rsi, [rbx+0C8h]
0x18001ead2  lea     rdi, [rbx+90h]
0x18001ead9  xor     r13d, r13d
0x18001eadc  test    rbx, rbx
0x18001eadf  cmovz   rdi, r13
0x18001eae3  lea     rcx, [rbx+10h]
0x18001eae7  cmovz   rcx, r13
0x18001eaeb  mov     [rsp+180h+var_150], rcx
0x18001eaf0  test    rcx, rcx
0x18001eaf3  jz      short loc_18001EB02
0x18001eaf5  mov     rax, [rcx]
0x18001eaf8  mov     rax, [rax+8]
0x18001eafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb01  nop
0x18001eb02  mov     [rsp+180h+var_148], rdi
0x18001eb07  test    rdi, rdi
0x18001eb0a  jz      short loc_18001EB1C
0x18001eb0c  mov     rax, [rdi]
0x18001eb0f  mov     rcx, rdi
0x18001eb12  mov     rax, [rax+8]
0x18001eb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb1b  nop
0x18001eb1c  mov     [rsp+180h+var_140], 1
0x18001eb25  lea     rax, [rsp+180h+var_110]
0x18001eb2a  mov     [rsp+180h+var_138], rax
0x18001eb2f  mov     [rsp+180h+var_130], rsi
0x18001eb34  mov     [rsp+180h+var_158], r13d
0x18001eb39  mov     [rsp+180h+var_128], r13
0x18001eb3e  mov     rsi, [rbx+0E0h]
0x18001eb45  mov     rax, [rsi]
0x18001eb48  mov     rdi, [rax]
0x18001eb4b  lea     rcx, [rsp+180h+var_128]
0x18001eb50  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001eb55  lea     r8, [rsp+180h+var_128]
0x18001eb5a  lea     rdx, _GUID_c8e34820_d46a_41bc_8c5c_5bc9fdee243d
0x18001eb61  mov     rcx, rsi
0x18001eb64  mov     rax, rdi
0x18001eb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb6c  test    eax, eax
0x18001eb6e  js      short loc_18001EB86
0x18001eb70  mov     rcx, [rsp+180h+var_128]
0x18001eb75  mov     rax, [rcx]
0x18001eb78  lea     rdx, [rsp+180h+var_158]
0x18001eb7d  mov     rax, [rax+60h]
0x18001eb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb86  mov     edi, 0FFFFFFFEh
0x18001eb8b  mov     r12d, 8
0x18001eb91  cmp     byte ptr [rbx+109h], 0
0x18001eb98  jz      loc_18001ED0D
0x18001eb9e  lea     rcx, [rbx+0C0h]
0x18001eba5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001ebaa  mov     [rbx+0C0h], r13
0x18001ebb1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ebb8  mov     ecx, 0A0h; unsigned __int64
0x18001ebbd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ebc2  test    rax, rax
0x18001ebc5  jz      loc_18001F0F7
0x18001ebcb  lea     rdx, [rsp+180h+var_150]; struct TITLE_BAR_ELEMENT_INIT_OPTIONS *
0x18001ebd0  mov     rcx, rax; this
0x18001ebd3  call    ??0CTitleBarSysMenuBar@@QEAA@AEBUTITLE_BAR_ELEMENT_INIT_OPTIONS@@@Z; CTitleBarSysMenuBar::CTitleBarSysMenuBar(TITLE_BAR_ELEMENT_INIT_OPTIONS const &)
0x18001ebd8  mov     rsi, rax
0x18001ebdb  test    rax, rax
0x18001ebde  jz      loc_18001F0F7
0x18001ebe4  lea     r8, [rbx+0C0h]
0x18001ebeb  lea     rdx, _GUID_47edc87f_6c1f_4b96_9dfe_fb6d57297580
0x18001ebf2  mov     rcx, rax
0x18001ebf5  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccSystemMenuInternal@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccSystemMenuInternal@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal> *,_GUID const &,void * *)
0x18001ebfa  test    eax, eax
0x18001ebfc  js      loc_18001F11A
0x18001ec02  mov     rcx, rsi
0x18001ec05  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccSystemMenuInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccSystemMenuInternal>::Release(void)
0x18001ec0a  mov     rsi, [rbx+100h]
0x18001ec11  mov     r8, [rbx+0F0h]
0x18001ec18  cmp     r8, rsi
0x18001ec1b  jnz     loc_18001ECD1
0x18001ec21  inc     r8
0x18001ec24  cmp     r8, rdi
0x18001ec27  ja      loc_18001ED0D
0x18001ec2d  cmp     r8, rsi
0x18001ec30  jbe     loc_18001ECD1
0x18001ec36  mov     [rsp+180h+var_160], r13
0x18001ec3b  mov     eax, 2
0x18001ec40  mul     rsi
0x18001ec43  test    rdx, rdx
0x18001ec46  jnz     loc_18001ED0D
0x18001ec4c  mov     rcx, rax
0x18001ec4f  sub     rcx, rsi
0x18001ec52  add     rsi, 1000h
0x18001ec59  cmp     rcx, 1000h
0x18001ec60  cmovbe  rsi, rax
0x18001ec64  cmp     r8, rsi
0x18001ec67  ja      loc_18001F025
0x18001ec6d  cmp     rsi, rdi
0x18001ec70  ja      loc_18001F0E8
0x18001ec76  mov     [rsp+180h+var_160], r13
0x18001ec7b  mov     rax, r12
0x18001ec7e  mul     rsi
0x18001ec81  mov     r12, rax
0x18001ec84  test    rdx, rdx
0x18001ec87  jnz     short loc_18001ED07
0x18001ec89  mov     rdx, rax; cb
0x18001ec8c  mov     rcx, [rbx+0E8h]; pv
0x18001ec93  call    cs:__imp_CoTaskMemRealloc
0x18001ec99  mov     r15, rax
0x18001ec9c  test    rax, rax
0x18001ec9f  jz      loc_18001F0DE
0x18001eca5  mov     rcx, rax; void *
0x18001eca8  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001ecad  cmp     rax, r12
0x18001ecb0  ja      loc_18001F142
0x18001ecb6  mov     eax, r13d
0x18001ecb9  mov     r12d, 8
0x18001ecbf  test    eax, eax
0x18001ecc1  js      short loc_18001ED0D
0x18001ecc3  mov     [rbx+100h], rsi
0x18001ecca  mov     [rbx+0E8h], r15
0x18001ecd1  inc     qword ptr [rbx+0F0h]
0x18001ecd8  mov     rcx, [rbx+0F0h]
0x18001ecdf  mov     rax, [rbx+0E8h]
0x18001ece6  dec     rcx
0x18001ece9  lea     rcx, [rax+rcx*8]
0x18001eced  test    rcx, rcx
0x18001ecf0  jz      short loc_18001ED01
0x18001ecf2  mov     rax, [rbx+0C0h]
0x18001ecf9  mov     [rcx], rax
0x18001ecfc  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18001ed01  inc     dword ptr [rsp+180h+var_140+4]
0x18001ed05  jmp     short loc_18001ED0D
0x18001ed07  mov     r12d, 8
0x18001ed0d  lea     rsi, [rbx+110h]
0x18001ed14  test    byte ptr [rsp+180h+var_158], 80h
0x18001ed19  jnz     loc_18001F158
0x18001ed1f  test    byte ptr [rsp+180h+var_158], 40h
0x18001ed24  jnz     loc_18001F1CE
0x18001ed2a  test    byte ptr [rsp+180h+var_158], 8
0x18001ed2f  jnz     loc_18001F246
0x18001ed35  test    byte ptr [rsp+180h+var_158], 10h
0x18001ed3a  jnz     loc_18001F2BC
0x18001ed40  test    byte ptr [rsp+180h+var_158], 1
0x18001ed45  jnz     loc_18001EF31
0x18001ed4b  test    byte ptr [rsp+180h+var_158], 20h
0x18001ed50  jnz     loc_18001F36B
0x18001ed56  test    byte ptr [rsp+180h+var_158], 2
0x18001ed5b  jnz     loc_18001EE95
0x18001ed61  test    byte ptr [rsp+180h+var_158], 4
0x18001ed66  jnz     short loc_18001EDD2
0x18001ed68  mov     rcx, [rsp+180h+var_128]
0x18001ed6d  test    rcx, rcx
0x18001ed70  jz      short loc_18001ED84
0x18001ed72  mov     [rsp+180h+var_128], r13
0x18001ed77  mov     rax, [rcx]
0x18001ed7a  mov     rax, [rax+10h]
0x18001ed7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed83  nop
0x18001ed84  mov     rcx, [rsp+180h+var_148]
0x18001ed89  test    rcx, rcx
0x18001ed8c  jz      short loc_18001ED9B
0x18001ed8e  mov     rax, [rcx]
0x18001ed91  mov     rax, [rax+10h]
0x18001ed95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed9a  nop
0x18001ed9b  mov     rcx, [rsp+180h+var_150]
0x18001eda0  test    rcx, rcx
0x18001eda3  jz      short loc_18001EDB2
0x18001eda5  mov     rax, [rcx]
0x18001eda8  mov     rax, [rax+10h]
0x18001edac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edb1  nop
0x18001edb2  mov     rcx, [rbp+80h+var_50]
0x18001edb6  xor     rcx, rsp; StackCookie
0x18001edb9  call    __security_check_cookie
0x18001edbe  add     rsp, 148h
0x18001edc5  pop     r15
0x18001edc7  pop     r14
0x18001edc9  pop     r13
0x18001edcb  pop     r12
0x18001edcd  pop     rdi
0x18001edce  pop     rsi
0x18001edcf  pop     rbx
0x18001edd0  pop     rbp
0x18001edd1  retn
0x18001edd2  test    byte ptr [rsi], 4
0x18001edd5  jz      short loc_18001ED68
0x18001edd7  lea     rcx, [rbp+80h+rc]; lprc
0x18001eddb  call    cs:__imp_IsRectEmpty
0x18001ede1  test    eax, eax
0x18001ede3  jnz     short loc_18001ED68
0x18001ede5  mov     [rsp+180h+var_160], r13
0x18001edea  mov     dword ptr [rsp+180h+var_140], 0Bh
0x18001edf2  lea     rax, [rbp+80h+rc]
0x18001edf6  mov     [rsp+180h+var_138], rax
0x18001edfb  lea     rcx, [rsp+180h+var_160]
0x18001ee00  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001ee05  mov     [rsp+180h+var_160], r13; int
0x18001ee0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ee11  mov     ecx, 98h; unsigned __int64
0x18001ee16  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ee1b  test    rax, rax
0x18001ee1e  jz      loc_18001F3EA
0x18001ee24  lea     rdx, [rsp+180h+var_150]; struct TITLE_BAR_ELEMENT_INIT_OPTIONS *
0x18001ee29  mov     rcx, rax; this
0x18001ee2c  call    ??0CTitleBarButton@@QEAA@AEBUTITLE_BAR_ELEMENT_INIT_OPTIONS@@@Z; CTitleBarButton::CTitleBarButton(TITLE_BAR_ELEMENT_INIT_OPTIONS const &)
0x18001ee31  mov     rdi, rax
0x18001ee34  test    rax, rax
0x18001ee37  jz      loc_18001F3EA
0x18001ee3d  lea     rcx, [rax+10h]
0x18001ee41  mov     [rsp+180h+var_160], rcx
0x18001ee46  mov     rdx, [rcx]
0x18001ee49  mov     rax, [rdx+8]
0x18001ee4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee52  nop
0x18001ee53  mov     rcx, rdi
0x18001ee56  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIInvokeProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IInvokeProvider>::Release(void)
  ... truncated ...
```
