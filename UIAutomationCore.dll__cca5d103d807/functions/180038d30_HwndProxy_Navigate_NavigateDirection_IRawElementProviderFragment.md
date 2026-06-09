# HwndProxy::Navigate(NavigateDirection,IRawElementProviderFragment * *)

- ea: `0x180038d30`
- end: `0x180039d04`
- name: `?Navigate@HwndProxy@@UEAAJW4NavigateDirection@@PEAPEAUIRawElementProviderFragment@@@Z`
- size: `4052`
- prototype: `__int64 __fastcall(HwndProxy *__hidden this, enum NavigateDirection, struct IRawElementProviderFragment **)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b790`
- `0x18002f580`
- `0x180032724`
- `0x18003635c`
- `0x1800386b8`
- `0x180038d30`
- `0x180039d0c`
- `0x180039fac`
- `0x18003a188`
- `0x18003b150`
- `0x18003b5ec`
- `0x18009ad80`
- `0x18009c800`
- `0x1800d2f00`
- `0x18012478c`
- `0x18012eaf4`
- `0x1801577dc`
- `0x180197754`
- `0x1801a8cf4`
- `0x1801b785c`
- `0x1801caa88`
- `0x1801cabe4`
- `0x1801e8320`
- `0x1801e887c`
- `0x1802dd010`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x180038e51`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x180038e51`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800390e0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800390e0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180038e5a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180038e5a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180038e37`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x180038e37`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800397c8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x1800397c8`

## string_xrefs

- `0x180039455`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x180039494`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x180039673`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x18003975f`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x1800398f1`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x1800397f5`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800392f4`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039336`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039354`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039722`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039a65`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039ac1`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039b6d`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039be7`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039c3b`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180039875`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x1800398d0`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x18003999f`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x180039ccb`: `onecore\windows\accessibletech\uiautomationcore\navigationhelperproxyonecore.cpp`
- `0x180038e07`: `onecore\windows\accessibletech\uiautomationcore\cautomation.cpp`
- `0x180039439`: `onecore\windows\accessibletech\uiautomationcore\cautomation.cpp`
- `0x180039543`: `onecore\windows\accessibletech\uiautomationcore\cautomation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall HwndProxy::Navigate(
        HwndProxy *this,
        enum NavigateDirection a2,
        struct IRawElementProviderFragment **a3)
{
  struct NavigationHelperProxyOneCore *v5; // r12
  char v6; // r14
  HWND v7; // rdi
  int TransactionTimeout; // eax
  HWND v9; // r14
  HWND PropW; // rax
  HWND RealOwner; // rdi
  HWND Ancestor; // r15
  char v13; // di
  __int64 v14; // rbx
  __int64 v15; // r15
  char *v16; // rax
  char *v17; // r14
  HWND v18; // rax
  HWND v19; // rbx
  __int64 v20; // rdx
  HWND v21; // r15
  GUID v22; // xmm0
  char v23; // r12
  int Instance; // eax
  unsigned int v25; // edi
  NavigationHelperProxyOneCore *v26; // rdi
  const WCHAR *v27; // rax
  int v28; // r8d
  int v29; // ecx
  struct NavigationHelperProxyOneCore *v30; // rcx
  struct ProviderEntryPoint *v31; // rcx
  HWND v32; // rcx
  struct IRawElementProviderFragment *v33; // rcx
  int ComboFromList; // eax
  int UiaManagerCrossMachineProxy; // eax
  unsigned int v37; // edi
  struct NavigationHelperProxyOneCore *v38; // rcx
  GUID v39; // xmm0
  __int16 v40; // ax
  char v41; // cl
  int v42; // edx
  HWND v43; // rdi
  int v44; // eax
  struct NavigationHelperProxyOneCore *v45; // rcx
  int v46; // edx
  int v47; // edx
  HWND v48; // rdi
  int v49; // eax
  __int64 NextSibling; // rax
  int v51; // eax
  int v52; // eax
  bool v53; // al
  struct NavigationHelperProxyOneCore *v54; // rcx
  struct NavigationHelperProxyOneCore *v55; // rcx
  __int64 v56; // rcx
  GUID v57; // xmm0
  int v58; // eax
  struct NavigationHelperProxyOneCore *v59; // rcx
  struct NavigationHelperProxyOneCore *v60; // rcx
  struct NavigationHelperProxyOneCore *v61; // rcx
  int v62; // eax
  unsigned int v63; // eax
  struct NavigationHelperProxyOneCore *v64; // rcx
  unsigned int *v65; // rax
  unsigned int *v66; // rbx
  int v67; // eax
  char *v68; // rcx
  int v69; // eax
  __int64 v70; // rdx
  struct NavigationHelperProxyOneCore **v71; // rcx
  int v72; // eax
  struct NavigationHelperProxyOneCore **v73; // rcx
  struct NavigationHelperProxyOneCore **v74; // rcx
  int v75; // eax
  void *v76; // rax
  int v77; // [rsp+20h] [rbp-E0h]
  int v78; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+20h] [rbp-E0h]
  int v80; // [rsp+20h] [rbp-E0h]
  struct NavigationHelperProxyOneCore *v81; // [rsp+30h] [rbp-D0h] BYREF
  struct NavigationHelperProxyOneCore *v82; // [rsp+38h] [rbp-C8h] BYREF
  HWND v83; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v84; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v85; // [rsp+50h] [rbp-B0h] BYREF
  struct ProviderEntryPoint *v86; // [rsp+58h] [rbp-A8h]
  __int16 v87; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v88; // [rsp+62h] [rbp-9Eh]
  int v89; // [rsp+6Ah] [rbp-96h]
  __int16 v90; // [rsp+6Eh] [rbp-92h]
  __m128i v91; // [rsp+70h] [rbp-90h]
  __int128 v92; // [rsp+80h] [rbp-80h] BYREF
  __m128i v93; // [rsp+90h] [rbp-70h]
  GUID v94; // [rsp+A0h] [rbp-60h]
  __int16 v95; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v96; // [rsp+B2h] [rbp-4Eh]
  int v97; // [rsp+BAh] [rbp-46h]
  __int16 v98; // [rsp+BEh] [rbp-42h]
  __m128i si128; // [rsp+C0h] [rbp-40h]
  __int128 v100; // [rsp+D0h] [rbp-30h]
  __m128i v101; // [rsp+E0h] [rbp-20h]
  char v102; // [rsp+F0h] [rbp-10h]
  _BYTE v103[152]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v104[24]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR ClassName[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  *a3 = 0;
  v85 = 0;
  v5 = 0;
  v6 = 0;
  if ( a2 == NavigateDirection_Parent )
  {
    if ( *((_BYTE *)this + 56) )
      goto LABEL_54;
    if ( !*((_BYTE *)this + 76) )
    {
      LOBYTE(v81) = 0;
      *(_WORD *)((char *)&v81 + 1) = 0;
      BYTE3(v81) = 0;
      HIDWORD(v81) = 60000;
      v7 = *(HWND *)(*(_QWORD *)(*((_QWORD *)this + 11) + 16LL) + 56LL);
      v83 = v7;
      if ( v7 )
        (*(void (__fastcall **)(HWND))(*(_QWORD *)v7 + 8LL))(v7);
      if ( *((_DWORD *)v7 + 216) >= 0x80000u )
      {
        LOBYTE(v81) = 1;
        TransactionTimeout = CUIAutomation::get_TransactionTimeout((CUIAutomation *)v7, (unsigned int *)&v81 + 1);
        if ( TransactionTimeout < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x914,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomation.cpp",
            (const char *)(unsigned int)TransactionTimeout,
            v77);
      }
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v7 + 16LL))(v7);
      v9 = (HWND)*((_QWORD *)this + 6);
      PropW = (HWND)GetPropW(v9, L"CrossProcessParentHWND");
      RealOwner = PropW;
      if ( !PropW || !IsWindow(PropW) )
      {
        Ancestor = GetAncestor(v9, 1u);
        if ( Ancestor != GetDesktopWindow() )
          goto LABEL_11;
        v83 = 0;
        ComboFromList = BasicHwndUtils::GetComboFromList(v9, (struct UIA_TIMEOUTDATA *)&v81, &v83);
        RealOwner = v83;
        if ( ComboFromList < 0 )
          RealOwner = 0;
        if ( !RealOwner )
        {
          RealOwner = BasicHwndUtils::GetRealOwner(v9);
          if ( !RealOwner )
LABEL_11:
            RealOwner = Ancestor;
        }
      }
      v85 = (__int64)RealOwner;
      goto LABEL_13;
    }
    v82 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    UiaManagerCrossMachineProxy = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
                                    (const struct _GUID *)((char *)this + 60),
                                    &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
                                    (void **)&v82);
    v37 = UiaManagerCrossMachineProxy;
    if ( UiaManagerCrossMachineProxy < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
        (const char *)(unsigned int)UiaManagerCrossMachineProxy,
        v77);
      v38 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(struct NavigationHelperProxyOneCore *))(*(_QWORD *)v38 + 16LL))(v38);
      }
      return v37;
    }
    v81 = 0;
    v83 = 0;
    v75 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, _QWORD, struct NavigationHelperProxyOneCore **, HWND *))(*(_QWORD *)v82 + 56LL))(
            v82,
            *((_QWORD *)this + 6),
            &v81,
            &v83);
    v37 = v75;
    if ( v75 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
        (const char *)(unsigned int)v75,
        v77);
      goto LABEL_150;
    }
    v76 = v83;
    if ( v83 )
    {
      v5 = v81;
      v6 = 0;
    }
    else
    {
      v76 = v81;
      v6 = 1;
    }
    v85 = (__int64)v76;
    v73 = &v82;
    goto LABEL_156;
  }
  v42 = a2 - 1;
  if ( !v42 )
  {
    if ( *((_BYTE *)this + 56) )
      goto LABEL_54;
    if ( !*((_BYTE *)this + 76) )
    {
      LOBYTE(v81) = 0;
      *(_WORD *)((char *)&v81 + 1) = 0;
      BYTE3(v81) = 0;
      HIDWORD(v81) = 60000;
      v43 = *(HWND *)(*(_QWORD *)(*((_QWORD *)this + 11) + 16LL) + 56LL);
      v83 = v43;
      if ( v43 )
        (*(void (__fastcall **)(HWND))(*(_QWORD *)v43 + 8LL))(v43);
      if ( *((_DWORD *)v43 + 216) >= 0x80000u )
      {
        LOBYTE(v81) = 1;
        v44 = CUIAutomation::get_TransactionTimeout((CUIAutomation *)v43, (unsigned int *)&v81 + 1);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x914,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomation.cpp",
            (const char *)(unsigned int)v44,
            v77);
      }
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v43 + 16LL))(v43);
      v93.m128i_i64[1] = 0;
      NextSibling = BasicHwndNavUtils::GetNextSibling(*((_QWORD *)this + 6), &v81, &v87);
      goto LABEL_79;
    }
    v81 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v69 = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
            (const struct _GUID *)((char *)this + 60),
            &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
            (void **)&v81);
    v37 = v69;
    if ( v69 < 0 )
    {
      v70 = 421;
      goto LABEL_147;
    }
    v69 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, _QWORD, __int64 *))(*(_QWORD *)v81 + 64LL))(
            v81,
            *((_QWORD *)this + 6),
            &v85);
    v37 = v69;
    if ( v69 < 0 )
    {
      v70 = 422;
      goto LABEL_147;
    }
LABEL_142:
    v6 = 1;
    v73 = &v81;
LABEL_156:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v73);
LABEL_54:
    v13 = 0;
    if ( !v6 )
      goto LABEL_14;
    goto LABEL_55;
  }
  v46 = v42 - 1;
  if ( !v46 )
  {
    if ( *((_BYTE *)this + 56) )
      goto LABEL_54;
    if ( !*((_BYTE *)this + 76) )
    {
      UiaClientState::GetTimeoutData(*((_QWORD *)this + 11), &v83, 1);
      v93.m128i_i64[1] = 0;
      NextSibling = BasicHwndNavUtils::GetPreviousSibling(*((_QWORD *)this + 6), &v83, &v87);
      goto LABEL_79;
    }
    v81 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v69 = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
            (const struct _GUID *)((char *)this + 60),
            &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
            (void **)&v81);
    v37 = v69;
    if ( v69 >= 0 )
    {
      v69 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, _QWORD, __int64 *))(*(_QWORD *)v81 + 72LL))(
              v81,
              *((_QWORD *)this + 6),
              &v85);
      v37 = v69;
      if ( v69 >= 0 )
        goto LABEL_142;
      v70 = 441;
    }
    else
    {
      v70 = 440;
    }
LABEL_147:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v70,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
      (const char *)(unsigned int)v69,
      v77);
    v74 = &v81;
LABEL_151:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v74);
    return v37;
  }
  v47 = v46 - 1;
  if ( v47 )
  {
    if ( v47 != 1 )
      return 2147500037LL;
    v68 = (char *)this - 24;
    if ( !v68[100] && !*((_QWORD *)this + 10) )
    {
      UiaClientState::GetTimeoutData(*((_QWORD *)this + 11), &v83, 1);
      v93.m128i_i64[1] = 0;
      NextSibling = BasicHwndNavUtils::GetLastChild(*((HWND *)this + 6), (struct UIA_TIMEOUTDATA *)&v83);
LABEL_79:
      v85 = NextSibling;
LABEL_13:
      v13 = 0;
      goto LABEL_14;
    }
    HwndProxy::GetCrossMachineHwndInfoBasedOnSurrogateSetting(v68, v104);
    v81 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v69 = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
            (const struct _GUID *)&v104[8],
            &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
            (void **)&v81);
    v37 = v69;
    if ( v69 >= 0 )
    {
      v69 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, _QWORD, __int64 *))(*(_QWORD *)v81 + 88LL))(
              v81,
              *(_QWORD *)v104,
              &v85);
      v37 = v69;
      if ( v69 >= 0 )
      {
        v71 = &v81;
        goto LABEL_132;
      }
      v70 = 476;
    }
    else
    {
      v70 = 475;
    }
    goto LABEL_147;
  }
  if ( !*((_BYTE *)this + 76) && !*((_QWORD *)this + 10) )
  {
    LOBYTE(v81) = 0;
    *(_WORD *)((char *)&v81 + 1) = 0;
    BYTE3(v81) = 0;
    HIDWORD(v81) = 60000;
    v48 = *(HWND *)(*(_QWORD *)(*((_QWORD *)this + 11) + 16LL) + 56LL);
    v83 = v48;
    if ( v48 )
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v48 + 8LL))(v48);
    if ( *((_DWORD *)v48 + 216) >= 0x80000u )
    {
      LOBYTE(v81) = 1;
      v49 = CUIAutomation::get_TransactionTimeout((CUIAutomation *)v48, (unsigned int *)&v81 + 1);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x914,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\cautomation.cpp",
          (const char *)(unsigned int)v49,
          v77);
    }
    (*(void (__fastcall **)(HWND))(*(_QWORD *)v48 + 16LL))(v48);
    v93.m128i_i64[1] = 0;
    NextSibling = BasicHwndNavUtils::GetFirstChild(*((HWND *)this + 6), (struct UIA_TIMEOUTDATA *)&v81);
    goto LABEL_79;
  }
  v56 = *((_QWORD *)this + 10);
  if ( v56 )
  {
    v57 = GUID_NULL;
  }
  else
  {
    v56 = *((_QWORD *)this + 6);
    v57 = *(GUID *)((char *)this + 60);
  }
  v94 = v57;
  *(_QWORD *)v104 = v56;
  *(GUID *)&v104[8] = v57;
  v82 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  v58 = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
          (const struct _GUID *)&v104[8],
          &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
          (void **)&v82);
  v37 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
      (const char *)(unsigned int)v58,
      v77);
    v59 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(struct NavigationHelperProxyOneCore *))(*(_QWORD *)v59 + 16LL))(v59);
    }
    return v37;
  }
  v72 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, _QWORD, __int64 *))(*(_QWORD *)v82 + 80LL))(
          v82,
          *(_QWORD *)v104,
          &v85);
  v37 = v72;
  if ( v72 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
      (const char *)(unsigned int)v72,
      v77);
LABEL_150:
    v74 = &v82;
    goto LABEL_151;
  }
  v71 = &v82;
LABEL_132:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v71);
LABEL_55:
  if ( *((_QWORD *)this + 10) )
  {
    v39 = GUID_NULL;
    v13 = 1;
    v40 = *(_WORD *)&v104[17];
    v41 = v104[19];
  }
  else
  {
    v39 = *(GUID *)((char *)this + 60);
    v13 = *((_BYTE *)this + 76);
    v40 = *(_WORD *)((char *)this + 77);
    v41 = *((_BYTE *)this + 79);
  }
  *(GUID *)v104 = v39;
  *(_WORD *)&v104[17] = v40;
  v104[19] = v41;
LABEL_14:
  v14 = *((_QWORD *)this + 11);
  v15 = v85;
  *a3 = 0;
  if ( !v15 )
    return 0;
  v16 = (char *)operator new(0x78u, (const struct std::nothrow_t *)std::nothrow);
  v17 = v16;
  *(_QWORD *)&v94.Data1 = v16;
  if ( v16 )
  {
    *(_QWORD *)v16 = &RefcountBase::`vftable';
    *((_DWORD *)v16 + 2) = 1;
    _InterlockedIncrement(&dword_18039DE7C);
    *(_QWORD *)v16 = &HwndProxy::`vftable'{for `RefcountBase'};
    *((_QWORD *)v16 + 2) = &HwndProxy::`vftable'{for `IRawElementProviderSimple'};
    *((_QWORD *)v16 + 3) = &HwndProxy::`vftable'{for `IRawElementProviderFragment'};
    *((_QWORD *)v16 + 4) = &HwndProxy::`vftable'{for `IRawElementProviderFragmentRoot'};
    *((_QWORD *)v16 + 5) = &HwndProxy::`vftable'{for `IWindowProvider'};
    *((_QWORD *)v16 + 6) = &HwndProxy::`vftable'{for `ITransformProvider'};
    *((_QWORD *)v16 + 7) = &HwndProxy::`vftable'{for `IScrollProvider'};
    *((_QWORD *)v16 + 8) = &HwndProxy::`vftable'{for `IProviderProxy'};
    *((_QWORD *)v16 + 9) = v15;
    v16[80] = 0;
    *(_OWORD *)(v16 + 84) = *(_OWORD *)v104;
    v16[100] = v13;
    *(_WORD *)(v16 + 101) = *(_WORD *)&v104[17];
    v16[103] = v104[19];
    *((_QWORD *)v16 + 13) = v5;
    *((_QWORD *)v16 + 14) = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v83 = 0;
    v18 = (HWND)operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
    v19 = v18;
    v20 = 0;
    if ( !v18 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)0x8007000ELL,
        v77);
LABEL_37:
      v32 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(HWND, __int64))(*(_QWORD *)v32 + 16LL))(v32, v20);
      }
      goto LABEL_39;
    }
    v102 = 0;
    *((_QWORD *)v18 + 1) = &RefcountBase::`vftable';
    *((_DWORD *)v18 + 4) = 1;
    _InterlockedIncrement(&dword_18039DE7C);
    *(_QWORD *)v18 = &ProviderEntryPoint::`vftable'{for `IUnknown'};
    *((_QWORD *)v18 + 1) = &ProviderEntryPoint::`vftable'{for `RefcountBase'};
    *(_OWORD *)(v18 + 6) = 0;
    *((_DWORD *)v18 + 10) = 0;
    *(_OWORD *)(v18 + 11) = *(_OWORD *)v104;
    *((_BYTE *)v18 + 60) = v13;
    *(_WORD *)((char *)v18 + 61) = *(_WORD *)&v104[17];
    *((_BYTE *)v18 + 63) = v104[19];
    *((_QWORD *)v18 + 8) = 0;
    *((_BYTE *)v18 + 216) = 0;
    *((_BYTE *)v18 + 228) = 0;
    *((_BYTE *)v18 + 264) = 0;
    *((_BYTE *)v18 + 304) = 0;
    *((_BYTE *)v18 + 344) = 0;
    if ( v102 )
    {
      v87 = v95;
      v88 = v96;
      v89 = v97;
      v90 = v98;
      v91 = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = 0;
      v92 = v100;
      v93 = v101;
      v101 = si128;
      LOWORD(v100) = 0;
      std::optional<std::wstring>::operator=<std::wstring,0>(v18 + 58, &v87);
      std::optional<std::wstring>::operator=<std::wstring,0>(v19 + 68, &v92);
      AppContainerInfo::~AppContainerInfo((AppContainerInfo *)&v87);
      v20 = 0;
      if ( v102 )
      {
        AppContainerInfo::~AppContainerInfo((AppContainerInfo *)&v95);
        v20 = 0;
      }
    }
    *((_DWORD *)v19 + 10) = 0;
    *((_QWORD *)v19 + 3) = v15;
    *((_QWORD *)v19 + 8) = v5;
    v83 = v19;
    v17[80] = 0;
    v86 = 0;
    if ( *((_DWORD *)v19 + 10) == 1 )
    {
      v86 = (struct ProviderEntryPoint *)v19;
      (*(void (__fastcall **)(HWND, _QWORD))(*(_QWORD *)v19 + 8LL))(v19, 0);
    }
    else if ( !*((_DWORD *)v19 + 10) )
    {
      v84 = -1;
      v21 = (HWND)*((_QWORD *)v19 + 8);
      if ( v21 )
      {
        v22 = GUID_NULL;
        v23 = 1;
      }
      else
      {
        v22 = *(GUID *)(v19 + 11);
        v23 = *((_BYTE *)v19 + 60);
        *(_WORD *)&v104[17] = *(_WORD *)((char *)v19 + 61);
        v104[19] = *((_BYTE *)v19 + 63);
        v21 = (HWND)*((_QWORD *)v19 + 3);
      }
      v104[16] = v23;
      *(GUID *)v104 = v22;
      v82 = 0;
      Instance = NavigationHelperProxyOneCore::GetInstance(&v82);
      v25 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62A,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
          (const char *)(unsigned int)Instance,
          v77);
        v45 = v82;
        if ( v82 )
        {
          v82 = 0;
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v45 + 2) + 16LL))((__int64)v45 + 16);
        }
        goto LABEL_68;
      }
      v84 = -1;
      if ( v23 )
      {
        v81 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
        v62 = GlobalInterfaceFactory::GetUiaManagerCrossMachineProxy(
                (const struct _GUID *)v104,
                &GUID_d9ba44fa_703e_4886_a085_8eb0123eae05,
                (void **)&v81);
        v25 = v62;
        if ( v62 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7AF,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
            (const char *)(unsigned int)v62,
            v77);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
          goto LABEL_119;
        }
        v63 = (*(__int64 (__fastcall **)(struct NavigationHelperProxyOneCore *, HWND, unsigned int *))(*(_QWORD *)v81 + 48LL))(
                v81,
                v21,
                &v84);
        v25 = 0;
        if ( v63 != -2147023496 )
          v25 = v63;
        if ( (v25 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B6,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
            (const char *)v25,
            v77);
          v64 = v81;
          if ( v81 )
          {
            v81 = 0;
            (*(void (__fastcall **)(struct NavigationHelperProxyOneCore *))(*(_QWORD *)v64 + 16LL))(v64);
          }
          goto LABEL_119;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      }
      else
      {
        v26 = v82;
        if ( !GetClassNameW(v21, ClassName, 260) )
          goto LABEL_31;
        v27 = L"Windows.UI.Core.CoreWindow";
        do
        {
          v28 = *(const WCHAR *)((char *)v27 + (char *)ClassName - (char *)L"Windows.UI.Core.CoreWindow");
          v29 = *v27 - v28;
          if ( v29 )
            break;
          ++v27;
        }
        while ( v28 );
        if ( v29 )
          goto LABEL_31;
        v65 = (unsigned int *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v66 = v65;
        v81 = (struct NavigationHelperProxyOneCore *)v65;
        if ( !v65 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7C1,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
            (const char *)0x8007000ELL,
            v77);
          v25 = -2147024882;
LABEL_119:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x62B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
            (const char *)v25,
            v80);
          Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(&v82);
          goto LABEL_68;
        }
        *(_OWORD *)v65 = 0;
        *((_OWORD *)v65 + 1) = 0;
        *((_OWORD *)v65 + 2) = 0;
        *(_QWORD *)v65 = &RefcountBase::`vftable';
        v65[2] = 1;
        _InterlockedIncrement(&dword_18039DE7C);
        *((_QWORD *)v65 + 2) = 0;
        *((_QWORD *)v65 + 3) = 0;
        *(_QWORD *)v65 = &NavigationHelperProxyOneCore::HwndViewIdDeferredCallData::`vftable';
        *((_QWORD *)v65 + 4) = 0;
        v65[10] = -1;
        v81 = (struct NavigationHelperProxyOneCore *)v65;
        v65[4] = 1;
        *((_QWORD *)v65 + 4) = v21;
        v65[10] = -1;
        v67 = NavigationHelperProxyOneCore::DoCoreMessagingDeferredInvoke(
                v26,
                (struct NavigationHelperProxyOneCore::CoreMessagingDeferredCallData *)v65);
        v25 = v67;
        if ( v67 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7C6,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\navigationhelperproxyonecore.cpp",
            (const char *)(unsigned int)v67,
            v77);
          RefcountBase::Release((RefcountBase *)v66);
          goto LABEL_119;
        }
        v84 = v66[10];
        RefcountBase::Release((RefcountBase *)v66);
      }
LABEL_31:
      if ( v84 == -1 )
        goto LABEL_32;
      v81 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v103[144] = 0;
      v51 = ProviderEntryPoint::CreateUsingViewId(v104, v84, v103, &v81);
      v25 = v51;
      if ( v51 >= 0 )
      {
        v86 = v81;
LABEL_32:
        v30 = v82;
        if ( v82 )
        {
          v82 = 0;
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v30 + 2) + 16LL))((__int64)v30 + 16);
        }
        goto LABEL_34;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x630,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
        (const char *)(unsigned int)v51,
        v77);
      v60 = v81;
      if ( v81 )
      {
        v81 = 0;
        (*(void (__fastcall **)(struct NavigationHelperProxyOneCore *))(*(_QWORD *)v60 + 16LL))(v60);
      }
      v61 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v61 + 2) + 16LL))((__int64)v61 + 16);
      }
LABEL_68:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FB,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
        (const char *)v25,
        v79);
LABEL_35:
      v31 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(struct ProviderEntryPoint *, __int64))(*(_QWORD *)v31 + 16LL))(v31, v20);
      }
      goto LABEL_37;
    }
LABEL_34:
    if ( v86 )
    {
      v81 = 0;
      Microsoft::WRL::ComPtr<NavigationHelperProxyOneCore>::InternalRelease(&v81);
      v52 = NavigationHelperProxyOneCore::GetInstance(&v81);
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x600,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
          (const char *)(unsigned int)v52,
          v77);
        v55 = v81;
        if ( v81 )
        {
          v81 = 0;
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v55 + 2) + 16LL))((__int64)v55 + 16);
        }
      }
      else
      {
        v84 = 0;
        v53 = NavigationHelperProxyOneCore::GetParentViewId(v81, v86, &v84) >= 0 && v84 != -1;
        v17[80] = v53;
        v54 = v81;
        if ( v81 )
        {
          v81 = 0;
          (*(void (__fastcall **)(__int64))(*((_QWORD *)v54 + 2) + 16LL))((__int64)v54 + 16);
        }
      }
    }
    goto LABEL_35;
  }
  v17 = 0;
LABEL_39:
  v33 = (struct IRawElementProviderFragment *)((unsigned __int64)(v17 + 24) & -(__int64)(v17 != 0));
  *a3 = v33;
  if ( v33 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
    (const char *)0x8007000ELL,
    v77);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F1,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\hwndproxy.cpp",
    (const char *)0x8007000ELL,
    v78);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180038d30  mov     [rsp-8+arg_8], rbx
0x180038d35  mov     [rsp-8+arg_18], rdi
0x180038d3a  push    rbp
0x180038d3b  push    r12
0x180038d3d  push    r13
0x180038d3f  push    r14
0x180038d41  push    r15
0x180038d43  lea     rbp, [rsp-2D0h]
0x180038d4b  sub     rsp, 3D0h
0x180038d52  mov     rax, cs:__security_cookie
0x180038d59  xor     rax, rsp
0x180038d5c  mov     [rbp+2F0h+var_30], rax
0x180038d63  mov     r13, r8
0x180038d66  mov     rbx, rcx
0x180038d69  xor     r15d, r15d
0x180038d6c  mov     [r8], r15
0x180038d6f  mov     [rsp+3F0h+var_3A0], r15
0x180038d74  mov     r12d, r15d
0x180038d77  mov     r14b, r15b
0x180038d7a  lea     rdi, _GUID_d9ba44fa_703e_4886_a085_8eb0123eae05
0x180038d81  test    edx, edx
0x180038d83  jnz     loc_1800393AE
0x180038d89  cmp     [rcx+38h], r15b
0x180038d8d  jnz     loc_18003936F
0x180038d93  cmp     [rcx+4Ch], r15b
0x180038d97  jnz     loc_1800392C0
0x180038d9d  mov     byte ptr [rsp+3F0h+var_3C0], r15b
0x180038da2  xor     eax, eax
0x180038da4  mov     word ptr [rsp+3F0h+var_3C0+1], ax
0x180038da9  mov     byte ptr [rsp+3F0h+var_3C0+3], al
0x180038dad  mov     dword ptr [rsp+3F0h+var_3C0+4], 0EA60h
0x180038db5  mov     rax, [rcx+58h]
0x180038db9  mov     rcx, [rax+10h]
0x180038dbd  mov     rdi, [rcx+38h]
0x180038dc1  mov     [rsp+3F0h+var_3B0], rdi
0x180038dc6  test    rdi, rdi
0x180038dc9  jz      short loc_180038DDB
0x180038dcb  mov     rax, [rdi]
0x180038dce  mov     rcx, rdi
0x180038dd1  mov     rax, [rax+8]
0x180038dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dda  nop
0x180038ddb  cmp     dword ptr [rdi+360h], 80000h
0x180038de5  jb      short loc_180038E19
0x180038de7  mov     byte ptr [rsp+3F0h+var_3C0], 1
0x180038dec  lea     rdx, [rsp+3F0h+var_3C0+4]; unsigned int *
0x180038df1  mov     rcx, rdi; this
0x180038df4  call    ?get_TransactionTimeout@CUIAutomation@@UEAAJPEAK@Z; CUIAutomation::get_TransactionTimeout(ulong *)
0x180038df9  mov     rcx, [rbp+2F8h]; this
0x180038e00  test    eax, eax
0x180038e02  jns     short loc_180038E19
0x180038e04  mov     r9d, eax; char *
0x180038e07  lea     r8, aOnecoreWindows_118; "onecore\\windows\\accessibletech\\uiaut"...
0x180038e0e  mov     edx, 914h; void *
0x180038e13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038e19  mov     rax, [rdi]
0x180038e1c  mov     rcx, rdi
0x180038e1f  mov     rax, [rax+10h]
0x180038e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e28  nop
0x180038e29  mov     r14, [rbx+30h]
0x180038e2d  lea     rdx, aCrossprocesspa; "CrossProcessParentHWND"
0x180038e34  mov     rcx, r14; hWnd
0x180038e37  call    cs:__imp_GetPropW
0x180038e3d  mov     rdi, rax
0x180038e40  test    rax, rax
0x180038e43  jnz     loc_1800397C5
0x180038e49  mov     edx, 1; gaFlags
0x180038e4e  mov     rcx, r14; hwnd
0x180038e51  call    cs:__imp_GetAncestor
0x180038e57  mov     r15, rax
0x180038e5a  call    cs:__imp_GetDesktopWindow
0x180038e60  cmp     r15, rax
0x180038e63  jz      loc_1800391D3
0x180038e69  mov     rdi, r15
0x180038e6c  xor     r15d, r15d
0x180038e6f  mov     [rsp+3F0h+var_3A0], rdi
0x180038e74  mov     dil, r15b
0x180038e77  mov     rbx, [rbx+58h]
0x180038e7b  mov     r15, [rsp+3F0h+var_3A0]
0x180038e80  mov     qword ptr [r13+0], 0
0x180038e88  test    r15, r15
0x180038e8b  jz      loc_1800391A5
0x180038e91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038e98  mov     ecx, 78h ; 'x'; unsigned __int64
0x180038e9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038ea2  mov     r14, rax
0x180038ea5  mov     qword ptr [rbp+2F0h+var_350], rax
0x180038ea9  test    rax, rax
0x180038eac  jz      loc_18003921D
0x180038eb2  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x180038eb9  mov     [r14], rax
0x180038ebc  mov     dword ptr [r14+8], 1
0x180038ec4  lock inc cs:dword_18039DE7C
0x180038ecb  lea     rax, ??_7HwndProxy@@6BRefcountBase@@@; const HwndProxy::`vftable'{for `RefcountBase'}
0x180038ed2  mov     [r14], rax
0x180038ed5  lea     rax, ??_7HwndProxy@@6BIRawElementProviderSimple@@@; const HwndProxy::`vftable'{for `IRawElementProviderSimple'}
0x180038edc  mov     [r14+10h], rax
0x180038ee0  lea     rax, ??_7HwndProxy@@6BIRawElementProviderFragment@@@; const HwndProxy::`vftable'{for `IRawElementProviderFragment'}
0x180038ee7  mov     [r14+18h], rax
0x180038eeb  lea     rax, ??_7HwndProxy@@6BIRawElementProviderFragmentRoot@@@; const HwndProxy::`vftable'{for `IRawElementProviderFragmentRoot'}
0x180038ef2  mov     [r14+20h], rax
0x180038ef6  lea     rax, ??_7HwndProxy@@6BIWindowProvider@@@; const HwndProxy::`vftable'{for `IWindowProvider'}
0x180038efd  mov     [r14+28h], rax
0x180038f01  lea     rax, ??_7HwndProxy@@6BITransformProvider@@@; const HwndProxy::`vftable'{for `ITransformProvider'}
0x180038f08  mov     [r14+30h], rax
0x180038f0c  lea     rax, ??_7HwndProxy@@6BIScrollProvider@@@; const HwndProxy::`vftable'{for `IScrollProvider'}
0x180038f13  mov     [r14+38h], rax
0x180038f17  lea     rax, ??_7HwndProxy@@6BIProviderProxy@@@; const HwndProxy::`vftable'{for `IProviderProxy'}
0x180038f1e  mov     [r14+40h], rax
0x180038f22  mov     [r14+48h], r15
0x180038f26  mov     byte ptr [r14+50h], 0
0x180038f2b  movups  xmm0, xmmword ptr [rbp+2F0h+var_260.Data1]
0x180038f32  movdqu  xmmword ptr [r14+54h], xmm0
0x180038f38  mov     [r14+64h], dil
0x180038f3c  movzx   eax, word ptr [rbp+2F0h+var_250+1]
0x180038f43  mov     [r14+65h], ax
0x180038f48  mov     al, byte ptr [rbp+2F0h+var_250+3]
0x180038f4e  mov     [r14+67h], al
0x180038f52  mov     [r14+68h], r12
0x180038f56  mov     [r14+70h], rbx
0x180038f5a  test    rbx, rbx
0x180038f5d  jz      short loc_180038F6F
0x180038f5f  mov     rax, [rbx]
0x180038f62  mov     rcx, rbx
0x180038f65  mov     rax, [rax+8]
0x180038f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f6e  nop
0x180038f6f  mov     [rsp+3F0h+var_3B0], 0
0x180038f78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038f7f  mov     ecx, 160h; unsigned __int64
0x180038f84  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038f89  mov     rbx, rax
0x180038f8c  xor     edx, edx
0x180038f8e  test    rax, rax
0x180038f91  jz      loc_1800397E8
0x180038f97  mov     [rbp+2F0h+var_300], dl
0x180038f9a  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x180038fa1  mov     [rbx+8], rax
0x180038fa5  mov     dword ptr [rbx+10h], 1
0x180038fac  lock inc cs:dword_18039DE7C
0x180038fb3  lea     rax, ??_7ProviderEntryPoint@@6BIUnknown@@@; const ProviderEntryPoint::`vftable'{for `IUnknown'}
0x180038fba  mov     [rbx], rax
0x180038fbd  lea     rax, ??_7ProviderEntryPoint@@6BRefcountBase@@@; const ProviderEntryPoint::`vftable'{for `RefcountBase'}
0x180038fc4  mov     [rbx+8], rax
0x180038fc8  xorps   xmm0, xmm0
0x180038fcb  movups  xmmword ptr [rbx+18h], xmm0
0x180038fcf  mov     [rbx+28h], edx
0x180038fd2  movups  xmm0, xmmword ptr [rbp+2F0h+var_260.Data1]
0x180038fd9  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x180038fde  mov     [rbx+3Ch], dil
0x180038fe2  movzx   eax, word ptr [rbp+2F0h+var_250+1]
0x180038fe9  mov     [rbx+3Dh], ax
0x180038fed  mov     al, byte ptr [rbp+2F0h+var_250+3]
0x180038ff3  mov     [rbx+3Fh], al
0x180038ff6  mov     [rbx+40h], rdx
0x180038ffa  mov     [rbx+0D8h], dl
0x180039000  mov     [rbx+0E4h], dl
0x180039006  lea     rcx, [rbx+0E8h]
0x18003900d  mov     [rcx+20h], dl
0x180039010  lea     rdi, [rbx+110h]
0x180039017  mov     [rdi+20h], dl
0x18003901a  mov     [rbx+158h], dl
0x180039020  cmp     [rbp+2F0h+var_300], dl
0x180039023  jnz     loc_180039225
0x180039029  mov     [rbx+28h], edx
0x18003902c  mov     [rbx+18h], r15
0x180039030  mov     [rbx+40h], r12
0x180039034  mov     [rsp+3F0h+var_3B0], rbx
0x180039039  xor     r12d, r12d
0x18003903c  mov     [r14+50h], r12b
0x180039040  mov     [rsp+3F0h+var_398], r12
0x180039045  cmp     dword ptr [rbx+28h], 1
0x180039049  jz      loc_180039CA8
0x18003904f  cmp     [rbx+28h], r12d
0x180039053  jnz     loc_180039147
0x180039059  mov     [rsp+3F0h+var_3A8], 0FFFFFFFFh
0x180039061  mov     r15, [rbx+40h]
0x180039065  test    r15, r15
0x180039068  jnz     loc_1800396AA
0x18003906e  movups  xmm0, xmmword ptr [rbx+2Ch]
0x180039072  mov     r12b, [rbx+3Ch]
0x180039076  movzx   eax, word ptr [rbx+3Dh]
0x18003907a  mov     word ptr [rbp+2F0h+var_250+1], ax
0x180039081  mov     al, [rbx+3Fh]
0x180039084  mov     byte ptr [rbp+2F0h+var_250+3], al
0x18003908a  mov     r15, [rbx+18h]
0x18003908e  mov     byte ptr [rbp+2F0h+var_250], r12b
0x180039095  movdqu  xmmword ptr [rbp+2F0h+var_260.Data1], xmm0
0x18003909d  mov     [rsp+3F0h+var_3B8], 0
0x1800390a6  lea     rcx, [rsp+3F0h+var_3B8]; struct NavigationHelperProxyOneCore **
0x1800390ab  call    ?GetInstance@NavigationHelperProxyOneCore@@SAJPEAPEAV1@@Z; NavigationHelperProxyOneCore::GetInstance(NavigationHelperProxyOneCore * *)
0x1800390b0  mov     edi, eax
0x1800390b2  test    eax, eax
0x1800390b4  js      loc_18003944B
0x1800390ba  mov     [rsp+3F0h+var_3A8], 0FFFFFFFFh
0x1800390c2  test    r12b, r12b
0x1800390c5  jnz     loc_18003980B
0x1800390cb  mov     rdi, [rsp+3F0h+var_3B8]
0x1800390d0  mov     r8d, 104h; nMaxCount
0x1800390d6  lea     rdx, [rbp+2F0h+ClassName]; lpClassName
0x1800390dd  mov     rcx, r15; hWnd
0x1800390e0  call    cs:__imp_GetClassNameW
0x1800390e6  xor     r12d, r12d
0x1800390e9  test    eax, eax
0x1800390eb  jz      short loc_18003911C
0x1800390ed  lea     rax, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800390f4  lea     r9, [rbp+2F0h+ClassName]
0x1800390fb  sub     r9, rax
0x1800390fe  movzx   ecx, word ptr [rax]
0x180039101  movzx   r8d, word ptr [rax+r9]
0x180039106  sub     ecx, r8d
0x180039109  jnz     short loc_180039114
0x18003910b  add     rax, 2
0x18003910f  test    r8d, r8d
0x180039112  jnz     short loc_1800390FE
0x180039114  test    ecx, ecx
0x180039116  jz      loc_1800398A5
0x18003911c  cmp     [rsp+3F0h+var_3A8], 0FFFFFFFFh
0x180039121  jnz     loc_180039586
0x180039127  mov     rcx, [rsp+3F0h+var_3B8]
0x18003912c  test    rcx, rcx
0x18003912f  jz      short loc_180039147
0x180039131  mov     [rsp+3F0h+var_3B8], r12
0x180039136  add     rcx, 10h
0x18003913a  mov     rax, [rcx]
0x18003913d  mov     rax, [rax+10h]
0x180039141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039146  nop
0x180039147  cmp     [rsp+3F0h+var_398], r12
0x18003914c  jnz     loc_1800395CE
0x180039152  mov     rcx, [rsp+3F0h+var_398]
0x180039157  test    rcx, rcx
0x18003915a  jz      short loc_18003916E
0x18003915c  mov     [rsp+3F0h+var_398], r12
0x180039161  mov     rax, [rcx]
0x180039164  mov     rax, [rax+10h]
0x180039168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003916d  nop
0x18003916e  mov     rcx, [rsp+3F0h+var_3B0]
0x180039173  test    rcx, rcx
0x180039176  jz      short loc_18003918E
0x180039178  mov     [rsp+3F0h+var_3B0], 0
0x180039181  mov     rax, [rcx]
0x180039184  mov     rax, [rax+10h]
0x180039188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003918d  nop
0x18003918e  lea     rax, [r14+18h]
0x180039192  neg     r14
0x180039195  sbb     rcx, rcx
0x180039198  and     rcx, rax
0x18003919b  mov     [r13+0], rcx
0x18003919f  jz      loc_180039329
0x1800391a5  xor     eax, eax
0x1800391a7  mov     rcx, [rbp+2F0h+var_30]
0x1800391ae  xor     rcx, rsp; StackCookie
0x1800391b1  call    __security_check_cookie
0x1800391b6  lea     r11, [rsp+3F0h+var_20]
0x1800391be  mov     rbx, [r11+38h]
0x1800391c2  mov     rdi, [r11+48h]
0x1800391c6  mov     rsp, r11
0x1800391c9  pop     r15
0x1800391cb  pop     r14
0x1800391cd  pop     r13
0x1800391cf  pop     r12
0x1800391d1  pop     rbp
0x1800391d2  retn
0x1800391d3  mov     [rsp+3F0h+var_3B0], 0
0x1800391dc  lea     r8, [rsp+3F0h+var_3B0]; HWND *
0x1800391e1  lea     rdx, [rsp+3F0h+var_3C0]; struct UIA_TIMEOUTDATA *
0x1800391e6  mov     rcx, r14; hWnd
0x1800391e9  call    ?GetComboFromList@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAPEAU2@@Z; BasicHwndUtils::GetComboFromList(HWND__ *,UIA_TIMEOUTDATA &,HWND__ * *)
0x1800391ee  mov     rdi, [rsp+3F0h+var_3B0]
0x1800391f3  xor     ecx, ecx
0x1800391f5  test    eax, eax
0x1800391f7  cmovs   rdi, rcx
0x1800391fb  test    rdi, rdi
0x1800391fe  jnz     loc_180038E6C
0x180039204  mov     rcx, r14; HWND
0x180039207  call    ?GetRealOwner@BasicHwndUtils@@SAPEAUHWND__@@PEAU2@@Z; BasicHwndUtils::GetRealOwner(HWND__ *)
0x18003920c  mov     rdi, rax
0x18003920f  test    rax, rax
0x180039212  jnz     loc_180038E6C
0x180039218  jmp     loc_180038E69
0x18003921d  xor     r14d, r14d
0x180039220  jmp     loc_18003918E
0x180039225  movzx   eax, [rbp+2F0h+var_340]
0x180039229  mov     [rsp+3F0h+var_390], ax
0x18003922e  movsd   xmm0, [rbp+2F0h+var_33E]
0x180039233  movsd   [rsp+3F0h+var_38E], xmm0
0x180039239  mov     eax, [rbp+2F0h+var_336]
0x18003923c  mov     [rsp+3F0h+var_386], eax
0x180039240  movzx   eax, [rbp+2F0h+var_332]
0x180039244  mov     [rsp+3F0h+var_382], ax
0x180039249  mov     rax, qword ptr [rbp+2F0h+var_330]
0x18003924d  mov     qword ptr [rsp+3F0h+var_380], rax
0x180039252  mov     rax, qword ptr [rbp+2F0h+var_330+8]
0x180039256  mov     qword ptr [rsp+3F0h+var_380+8], rax
0x18003925b  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x180039263  movdqu  [rbp+2F0h+var_330], xmm2
  ... truncated ...
```
