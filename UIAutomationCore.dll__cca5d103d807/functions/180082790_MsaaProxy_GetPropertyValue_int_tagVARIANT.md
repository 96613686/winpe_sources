# MsaaProxy::GetPropertyValue(int,tagVARIANT *)

- ea: `0x180082790`
- end: `0x1800832c3`
- name: `?GetPropertyValue@MsaaProxy@@UEAAJHPEAUtagVARIANT@@@Z`
- size: `2867`
- prototype: `__int64 __fastcall(MsaaProxy *__hidden this, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000f680`
- `0x180020230`
- `0x18002f580`
- `0x180032724`
- `0x18003c820`
- `0x18008179c`
- `0x180082790`
- `0x1800832cc`
- `0x180083818`
- `0x18008438c`
- `0x1800857bc`
- `0x18008a7e4`
- `0x18008ae94`
- `0x180112848`
- `0x180158918`
- `0x18015db24`
- `0x180169bd0`
- `0x180186cd0`
- `0x1801a1438`
- `0x1801e26d4`
- `0x1801e8320`
- `0x180237770`
- `0x1802c3491`
- `0x1802dd010`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180082caf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180082caf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180082818`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180082818`
- `OLEAUT32!__imp_VariantInit` at `0x1800829f2`
- `OLEAUT32!__imp_VariantInit` at `0x1800829f2`
- `OLEAUT32!__imp_VariantClear` at `0x180082a05`
- `OLEAUT32!__imp_VariantClear` at `0x180082a05`

## string_xrefs

- `0x180082a8b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082bff`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082d66`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082db8`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082e29`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082f75`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800830a0`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800830d2`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180083126`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180083198`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800831eb`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180083281`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180082e52`: `onecore\windows\accessibletech\uiautomationcore\proxies\MsaaProxy.h`
- `0x180083045`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x18008325e`: `Microsoft: MSAA Proxy (IAccessible2)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsaaProxy::GetPropertyValue(MsaaProxy *this, int a2, struct tagVARIANT *a3, const char *a4)
{
  MsaaProxy *v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // rsi
  __int64 (__fastcall ***v12)(_QWORD, GUID *, _QWORD **); // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  struct IAccessible *v17; // rsi
  __int64 (__fastcall ***v18)(_QWORD, GUID *, struct IAccessible **); // rcx
  unsigned int v19; // r15d
  __int128 v20; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 result; // rax
  int v23; // eax
  unsigned int v24; // esi
  int v25; // eax
  int v26; // eax
  bool v27; // cf
  __int64 v28; // r9
  int v29; // eax
  int v30; // edi
  __int64 v31; // rcx
  LONG v32; // eax
  int v33; // eax
  unsigned int v34; // edi
  int accState; // eax
  unsigned int v36; // edi
  int PropertyValue; // eax
  unsigned int v38; // ebx
  __int64 v39; // rcx
  int v40; // ecx
  int v41; // esi
  unsigned int v42; // ebx
  int v43; // eax
  unsigned int v44; // edi
  int v45; // eax
  int v46; // eax
  unsigned int v47; // edi
  int accStringProperty; // eax
  unsigned int v49; // edi
  LONGLONG v50; // rax
  const unsigned __int16 *v51; // rcx
  int v52; // eax
  unsigned int v53; // edi
  int v54; // [rsp+20h] [rbp-1D8h]
  _QWORD *v55; // [rsp+30h] [rbp-1C8h] BYREF
  struct IAccessible *v56; // [rsp+38h] [rbp-1C0h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-1B8h] BYREF
  _QWORD v58[3]; // [rsp+60h] [rbp-198h] BYREF
  int v59; // [rsp+78h] [rbp-180h]
  int v60; // [rsp+7Ch] [rbp-17Ch]
  char v61; // [rsp+80h] [rbp-178h]
  WCHAR ClassName[128]; // [rsp+90h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  try
  {
    if ( !a3 )
      return 2147500035LL;
    a3->vt = 0;
    v7 = (MsaaProxy *)((char *)this - 16);
    if ( *((_DWORD *)this + 56)
      && (a2 == 30004 || a2 == 30016 || a2 == 30017 || a2 == 30107 || a2 == 30174)
      && GetClassNameW(*((HWND *)this + 27), ClassName, 128)
      && !wcscmp_0(ClassName, L"#32770") )
    {
      PropertyValue = ContainerProxy::GetPropertyValue(*((HWND *)this + 27), a2, a3, 0);
      v38 = PropertyValue;
      if ( PropertyValue >= 0 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x337,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
        (const char *)(unsigned int)PropertyValue,
        v54);
      return v38;
    }
    if ( a2 == 30003 )
    {
      v32 = MsaaProxy::ControlType(v7);
      if ( v32 )
      {
        a3->vt = 3;
        a3->lVal = v32;
      }
      return 0;
    }
    if ( a2 == 30107 )
    {
      *(_QWORD *)&pvarg.vt = 0;
      wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(&pvarg);
      v45 = AgileInterface<IAccessible2>::TryGet((char *)this + 272, *((_QWORD *)v7 + 31), &pvarg);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x341,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)v45,
          v54);
      v51 = L"Microsoft: MSAA Proxy (IAccessible2)";
      if ( !*(_QWORD *)&pvarg.vt )
        v51 = L"Microsoft: MSAA Proxy";
      v52 = HrSysAllocString(v51, &a3->bstrVal);
      v53 = v52;
      if ( v52 >= 0 )
      {
        a3->vt = 8;
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&pvarg);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x343,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)v52,
          v54);
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&pvarg);
        return v53;
      }
    }
    v55 = 0;
    if ( *((_DWORD *)this + 90) )
    {
LABEL_21:
      v56 = 0;
      if ( !*((_DWORD *)this + 60) )
      {
        v56 = 0;
        v14 = *((_QWORD *)this + 31);
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          v17 = (struct IAccessible *)*((_QWORD *)this + 31);
          v56 = v17;
LABEL_29:
          if ( !v17 )
          {
LABEL_50:
            v19 = -2147467259;
LABEL_51:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x369,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
              (const char *)v19,
              v54);
            if ( v56 )
              ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
            if ( v55 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v55 + 16LL))(v55, *v55);
            return v19;
          }
          if ( a2 > 30010 )
          {
            switch ( a2 )
            {
              case 30013:
                MsaaProxy::GetHelpText(v7, (int)&pvarg);
                v50 = *(_QWORD *)&pvarg.vt;
                *(_QWORD *)&pvarg.vt = 0;
                a3->llVal = v50;
                a3->vt = 8;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvarg);
                goto LABEL_44;
              case 30019:
                *(_DWORD *)&pvarg.vt = 0;
                accState = AccUtils::get_accState(
                             v17,
                             *((HWND *)this + 27),
                             (const struct tagVARIANT *)((char *)this + 304),
                             (unsigned int *)&pvarg.vt);
                v36 = accState;
                if ( accState < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3A8,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                    (const char *)(unsigned int)accState,
                    v54);
                  if ( v56 )
                    ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
                  if ( v55 )
                    (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
                  return v36;
                }
                v26 = *(_DWORD *)&pvarg.vt & 0x20000000;
                break;
              case 30022:
                *(_DWORD *)&pvarg.vt = 0;
                v23 = AccUtils::get_accState(
                        v17,
                        *((HWND *)this + 27),
                        (const struct tagVARIANT *)((char *)this + 304),
                        (unsigned int *)&pvarg.vt);
                v24 = v23;
                if ( v23 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3B0,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                    (const char *)(unsigned int)v23,
                    v54);
                  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v56);
                  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
                  return v24;
                }
                if ( (*(_DWORD *)&pvarg.vt & 0x10000) != 0 )
                {
                  v26 = 1;
                }
                else
                {
                  v25 = (*(__int64 (__fastcall **)(MsaaProxy *))(*(_QWORD *)v7 + 16LL))(v7);
                  v26 = MsaaProxy::CheckLocationForOffscreen(
                          v56,
                          (struct tagVARIANT *)((char *)this + 304),
                          *((HWND *)this + 27),
                          v25);
                }
                break;
              case 30174:
                *(_DWORD *)&pvarg.vt = 0;
                v43 = (*(__int64 (__fastcall **)(char *, VARIANTARG *))(*((_QWORD *)this + 18) + 88LL))(
                        (char *)this + 144,
                        &pvarg);
                v44 = v43;
                if ( v43 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3C3,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                    (const char *)(unsigned int)v43,
                    v54);
                  if ( v56 )
                    ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
                  if ( v55 )
                    (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
                  return v44;
                }
                v26 = *(_DWORD *)&pvarg.vt == 18;
                break;
              default:
                goto LABEL_42;
            }
LABEL_59:
            v27 = v26 != 0;
LABEL_83:
            a3->vt = 11;
            a3->iVal = -v27;
            goto LABEL_44;
          }
          if ( a2 == 30010 )
          {
            *(_DWORD *)&pvarg.vt = 0;
            v33 = AccUtils::get_accState(
                    v17,
                    *((HWND *)this + 27),
                    (const struct tagVARIANT *)((char *)this + 304),
                    (unsigned int *)&pvarg.vt);
            v34 = v33;
            if ( v33 >= 0 )
            {
              v27 = (pvarg.vt & 1) == 0;
              goto LABEL_83;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37E,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
              (const char *)(unsigned int)v33,
              v54);
            if ( v56 )
              ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
            if ( v55 )
              (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
            return v34;
          }
          if ( a2 == 30002 )
          {
            a3->vt = 3;
            *(_DWORD *)&pvarg.vt = 0;
            GetWindowThreadProcessId(*((HWND *)this + 27), (LPDWORD)&pvarg.vt);
            a3->lVal = *(_DWORD *)&pvarg.vt;
            goto LABEL_44;
          }
          if ( a2 != 30005 )
          {
            if ( a2 != 30007 )
            {
              if ( a2 == 30008 )
              {
                MsaaProxy::GetHasKeyboardFocusPropertyValue(v7, &pvarg);
                goto LABEL_43;
              }
              if ( a2 != 30009 )
              {
LABEL_42:
                MsaaProxy::GetPropertyValueFromAcc2(v7, &pvarg);
LABEL_43:
                v20 = *(_OWORD *)&pvarg.vt;
                pRecInfo = pvarg.pRecInfo;
                VariantInit(&pvarg);
                *(_OWORD *)&a3->vt = v20;
                a3->pRecInfo = pRecInfo;
                VariantClear(&pvarg);
LABEL_44:
                if ( v56 )
                  ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
                if ( v55 )
                  (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
                return 0;
              }
              *(_DWORD *)&pvarg.vt = 0;
              v46 = AccUtils::get_accState(
                      v17,
                      *((HWND *)this + 27),
                      (const struct tagVARIANT *)((char *)this + 304),
                      (unsigned int *)&pvarg.vt);
              v47 = v46;
              if ( v46 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x386,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                  (const char *)(unsigned int)v46,
                  v54);
                wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v56);
                wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
                return v47;
              }
              v26 = *(_DWORD *)&pvarg.vt & 0x100000;
              goto LABEL_59;
            }
            accStringProperty = AccUtils::get_accStringProperty(v17, *((_QWORD *)this + 27), (char *)this + 304, 4);
            v49 = accStringProperty;
            if ( accStringProperty < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x36F,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                (const char *)(unsigned int)accStringProperty,
                (_DWORD)a3 + 8);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v56);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
              return v49;
            }
LABEL_136:
            a3->vt = 8;
            goto LABEL_44;
          }
          v28 = *((_QWORD *)this + 27);
          a3->llVal = 0;
          v58[0] = L"IAccessible::get_accName";
          v58[1] = v17;
          v58[2] = v28;
          v60 = 600;
          v61 = 1;
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McTemplateU0zd_EventWriteTransfer(
              (unsigned int)(a2 - 30005),
              MsaaProviderCallout_Start,
              L"IAccessible::get_accName",
              v28);
          pvarg = *(VARIANTARG *)((char *)this + 304);
          v29 = SelectionItemRedirect::RemoveFromSelection((SelectionItemRedirect *)v17);
          v30 = v29;
          v59 = v29;
          if ( v29 == -2147352573 )
          {
            v59 = 0;
          }
          else if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14E,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
              (const char *)(unsigned int)v29,
              v54);
            MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)v58);
            goto LABEL_66;
          }
          MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)v58);
          v30 = 0;
LABEL_66:
          if ( v30 >= 0 )
            goto LABEL_136;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x376,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
            (const char *)(unsigned int)v30,
            v54);
          if ( v56 )
            ((void (__fastcall *)(struct IAccessible *))v56->lpVtbl->Release)(v56);
          if ( v55 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v55 + 16LL))(v55, *v55);
          return (unsigned int)v30;
        }
        v15 = *((unsigned int *)this + 66);
        if ( !(_DWORD)v15 && !*((_QWORD *)this + 32) )
          goto LABEL_50;
        v16 = *((_QWORD *)this + 32);
        if ( v16 )
        {
          v17 = 0;
          v56 = 0;
          v18 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IAccessible **))(v16 + 32);
          if ( !v18 )
          {
            v19 = -2147467259;
LABEL_28:
            if ( (v19 & 0x80000000) == 0 )
              goto LABEL_29;
LABEL_98:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF2,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\MsaaProxy.h",
              (const char *)v19,
              v54);
            goto LABEL_51;
          }
          v19 = (**v18)(v18, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &v56);
LABEL_27:
          v17 = v56;
          goto LABEL_28;
        }
        if ( (_DWORD)v15 )
        {
          v31 = *((_QWORD *)this + 29);
          if ( v31 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, struct IAccessible **))(*(_QWORD *)v31 + 40LL))(
                    v31,
                    v15,
                    &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
                    &v56);
            goto LABEL_27;
          }
        }
      }
      v19 = -2147467259;
      goto LABEL_98;
    }
    v55 = 0;
    v8 = *((_QWORD *)this + 46);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v11 = (_QWORD *)*((_QWORD *)this + 46);
      v55 = v11;
LABEL_103:
      if ( v11 )
      {
        *(_QWORD *)&pvarg.vt = L"IRawElementProviderSimple::GetPropertyValue";
        pvarg.llVal = (unsigned int)a2;
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          McTemplateU0zqq_EventWriteTransfer(
            (_DWORD)v12,
            (unsigned int)UiaProviderCallout_Start,
            (unsigned int)L"IRawElementProviderSimple::GetPropertyValue",
            a2,
            0);
        v41 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, struct tagVARIANT *))(*v11 + 40LL))(
                v11,
                (unsigned int)a2,
                a3);
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          McTemplateU0zqq_EventWriteTransfer(
            v40,
            (unsigned int)UiaProviderCallout_Stop,
            (unsigned int)L"IRawElementProviderSimple::GetPropertyValue",
            a2,
            0);
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x357,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
            (const char *)(unsigned int)v41,
            v54);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
          return (unsigned int)v41;
        }
        if ( a3->vt )
        {
          v42 = MsaaProxy_WrapProperty(v40, v7, a3);
          if ( v55 )
            (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
          return v42;
        }
      }
      goto LABEL_21;
    }
    v9 = *((unsigned int *)this + 96);
    if ( !(_DWORD)v9 && !*((_QWORD *)this + 47) )
      goto LABEL_21;
    v10 = *((_QWORD *)this + 47);
    if ( v10 )
    {
      v11 = 0;
      v55 = 0;
      v12 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **))(v10 + 32);
      if ( !v12 )
      {
        v13 = -2147467259;
LABEL_20:
        if ( v13 < 0 )
          goto LABEL_21;
        goto LABEL_103;
      }
      v13 = (**v12)(v12, &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c, &v55);
    }
    else
    {
      if ( !(_DWORD)v9 )
        goto LABEL_21;
      v39 = *((_QWORD *)v7 + 31);
      if ( !v39 )
        goto LABEL_21;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _QWORD **))(*(_QWORD *)v39 + 40LL))(
              v39,
              v9,
              &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
              &v55);
    }
    v11 = v55;
    goto LABEL_20;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3D3,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180082790  mov     rax, rsp
0x180082793  push    rbx
0x180082794  push    rsi
0x180082795  push    rdi
0x180082796  push    r12
0x180082798  push    r13
0x18008279a  push    r14
0x18008279c  push    r15
0x18008279e  sub     rsp, 1C0h
0x1800827a5  movaps  xmmword ptr [rax-48h], xmm6
0x1800827a9  movaps  xmmword ptr [rax-58h], xmm7
0x1800827ad  mov     rax, cs:__security_cookie
0x1800827b4  xor     rax, rsp
0x1800827b7  mov     [rsp+1F8h+var_68], rax
0x1800827bf  mov     rbx, r8
0x1800827c2  mov     r14d, edx
0x1800827c5  mov     rdi, rcx
0x1800827c8  xor     r13d, r13d
0x1800827cb  test    rbx, rbx
0x1800827ce  jz      loc_180082CC1
0x1800827d4  mov     [r8], r13w
0x1800827d8  lea     r12, [rcx-10h]
0x1800827dc  cmp     [r12+0F0h], r13d
0x1800827e4  jz      short loc_18008283E
0x1800827e6  mov     ecx, edx
0x1800827e8  sub     ecx, 7534h
0x1800827ee  jz      short loc_180082803
0x1800827f0  sub     ecx, 0Ch
0x1800827f3  jz      short loc_180082803
0x1800827f5  sub     ecx, 1
0x1800827f8  jz      short loc_180082803
0x1800827fa  sub     ecx, 5Ah ; 'Z'
0x1800827fd  jnz     loc_1800830B2
0x180082803  mov     r8d, 80h; nMaxCount
0x180082809  lea     rdx, [rsp+1F8h+ClassName]; lpClassName
0x180082811  mov     rcx, [rdi+0D8h]; hWnd
0x180082818  call    cs:__imp_GetClassNameW
0x18008281e  test    eax, eax
0x180082820  jz      short loc_18008283E
0x180082822  lea     rdx, a32770; "#32770"
0x180082829  lea     rcx, [rsp+1F8h+ClassName]; String1
0x180082831  call    wcscmp_0
0x180082836  test    eax, eax
0x180082838  jz      loc_180082DFF
0x18008283e  mov     ecx, r14d
0x180082841  sub     ecx, 7533h
0x180082847  jz      loc_180082C7E
0x18008284d  cmp     ecx, 68h ; 'h'
0x180082850  jz      loc_180083065
0x180082856  mov     [rsp+1F8h+var_1C8], r13
0x18008285b  cmp     [rdi+168h], r13d
0x180082862  jnz     short loc_1800828D5
0x180082864  mov     [rsp+1F8h+var_1C8], r13
0x180082869  mov     rcx, [rdi+170h]
0x180082870  test    rcx, rcx
0x180082873  jnz     loc_180082E9E
0x180082879  mov     edx, [rdi+180h]
0x18008287f  test    edx, edx
0x180082881  jnz     short loc_18008288C
0x180082883  cmp     [rdi+178h], r13
0x18008288a  jz      short loc_1800828D5
0x18008288c  mov     rax, [rdi+178h]
0x180082893  test    rax, rax
0x180082896  jz      loc_180082E68
0x18008289c  mov     rsi, r13
0x18008289f  mov     [rsp+1F8h+var_1C8], r13
0x1800828a4  mov     rcx, [rax+20h]
0x1800828a8  test    rcx, rcx
0x1800828ab  jz      loc_180082FE6
0x1800828b1  mov     rax, [rcx]
0x1800828b4  lea     r8, [rsp+1F8h+var_1C8]
0x1800828b9  lea     rdx, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c
0x1800828c0  mov     rax, [rax]
0x1800828c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828c8  mov     rsi, [rsp+1F8h+var_1C8]
0x1800828cd  test    eax, eax
0x1800828cf  jns     loc_180082EB6
0x1800828d5  mov     [rsp+1F8h+var_1C0], r13
0x1800828da  cmp     [rdi+0F0h], r13d
0x1800828e1  jnz     loc_180082E41
0x1800828e7  mov     [rsp+1F8h+var_1C0], r13
0x1800828ec  mov     rcx, [rdi+0F8h]
0x1800828f3  test    rcx, rcx
0x1800828f6  jnz     loc_180082CCB
0x1800828fc  mov     edx, [rdi+108h]
0x180082902  test    edx, edx
0x180082904  jz      loc_180082A6D
0x18008290a  mov     rax, [rdi+100h]
0x180082911  test    rax, rax
0x180082914  jz      loc_180082C46
0x18008291a  mov     rsi, r13
0x18008291d  mov     [rsp+1F8h+var_1C0], r13
0x180082922  mov     rcx, [rax+20h]
0x180082926  test    rcx, rcx
0x180082929  jz      loc_180082FBC
0x18008292f  mov     rax, [rcx]
0x180082932  lea     r8, [rsp+1F8h+var_1C0]
0x180082937  lea     rdx, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x18008293e  mov     rax, [rax]
0x180082941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082946  mov     r15d, eax
0x180082949  mov     rsi, [rsp+1F8h+var_1C0]
0x18008294e  test    r15d, r15d
0x180082951  js      loc_180082E47
0x180082957  test    rsi, rsi
0x18008295a  jz      loc_180082A7A
0x180082960  mov     eax, 753Ah
0x180082965  cmp     r14d, eax
0x180082968  jg      short loc_1800829A5
0x18008296a  jz      loc_180082CE8
0x180082970  mov     ecx, r14d
0x180082973  sub     ecx, 7532h
0x180082979  jz      loc_180082C99
0x18008297f  sub     ecx, 3
0x180082982  jz      loc_180082B51
0x180082988  sub     ecx, 2
0x18008298b  jz      loc_180083162
0x180082991  sub     ecx, 1
0x180082994  jz      loc_180082B3C
0x18008299a  cmp     ecx, 1
0x18008299d  jz      loc_1800830F5
0x1800829a3  jmp     short loc_1800829D2
0x1800829a5  mov     ecx, r14d
0x1800829a8  sub     ecx, 753Dh
0x1800829ae  jz      loc_180083219
0x1800829b4  sub     ecx, 6
0x1800829b7  jz      loc_180082D31
0x1800829bd  sub     ecx, 3
0x1800829c0  jz      loc_180082AD3
0x1800829c6  cmp     ecx, 98h
0x1800829cc  jz      loc_180082F43
0x1800829d2  mov     r8d, r14d
0x1800829d5  lea     rdx, [rsp+1F8h+pvarg]
0x1800829da  mov     rcx, r12
0x1800829dd  call    ?GetPropertyValueFromAcc2@MsaaProxy@@AEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@H@Z; MsaaProxy::GetPropertyValueFromAcc2(int)
0x1800829e2  movups  xmm6, xmmword ptr [rsp+1F8h+pvarg]
0x1800829e7  movsd   xmm7, qword ptr [rsp+1F8h+pvarg+10h]
0x1800829ed  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x1800829f2  call    cs:__imp_VariantInit
0x1800829f8  movups  xmmword ptr [rbx], xmm6
0x1800829fb  movsd   qword ptr [rbx+10h], xmm7
0x180082a00  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x180082a05  call    cs:__imp_VariantClear
0x180082a0b  nop
0x180082a0c  mov     rcx, [rsp+1F8h+var_1C0]
0x180082a11  test    rcx, rcx
0x180082a14  jz      short loc_180082A23
0x180082a16  mov     rax, [rcx]
0x180082a19  mov     rax, [rax+10h]
0x180082a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a22  nop
0x180082a23  mov     rcx, [rsp+1F8h+var_1C8]
0x180082a28  test    rcx, rcx
0x180082a2b  jz      short loc_180082A3A
0x180082a2d  mov     rax, [rcx]
0x180082a30  mov     rax, [rax+10h]
0x180082a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a39  nop
0x180082a3a  xor     eax, eax
0x180082a3c  mov     rcx, [rsp+1F8h+var_68]
0x180082a44  xor     rcx, rsp; StackCookie
0x180082a47  call    __security_check_cookie
0x180082a4c  lea     r11, [rsp+1F8h+var_38]
0x180082a54  movaps  xmm6, xmmword ptr [r11-10h]
0x180082a59  movaps  xmm7, xmmword ptr [r11-20h]
0x180082a5e  mov     rsp, r11
0x180082a61  pop     r15
0x180082a63  pop     r14
0x180082a65  pop     r13
0x180082a67  pop     r12
0x180082a69  pop     rdi
0x180082a6a  pop     rsi
0x180082a6b  pop     rbx
0x180082a6c  retn
0x180082a6d  cmp     [rdi+100h], r13
0x180082a74  jnz     loc_18008290A
0x180082a7a  mov     r15d, 80004005h
0x180082a80  mov     rcx, [rsp+1F8h]; this
0x180082a88  mov     r9d, r15d; char *
0x180082a8b  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180082a92  mov     edx, 369h; void *
0x180082a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082a9c  nop
0x180082a9d  mov     rcx, [rsp+1F8h+var_1C0]
0x180082aa2  test    rcx, rcx
0x180082aa5  jz      short loc_180082AB4
0x180082aa7  mov     rax, [rcx]
0x180082aaa  mov     rax, [rax+10h]
0x180082aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ab3  nop
0x180082ab4  mov     rcx, [rsp+1F8h+var_1C8]
0x180082ab9  test    rcx, rcx
0x180082abc  jz      short loc_180082ACB
0x180082abe  mov     rdx, [rcx]
0x180082ac1  mov     rax, [rdx+10h]
0x180082ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082aca  nop
0x180082acb  mov     eax, r15d
0x180082ace  jmp     loc_180082A3C
0x180082ad3  mov     dword ptr [rsp+1F8h+pvarg], r13d
0x180082ad8  lea     r14, [rdi+130h]
0x180082adf  lea     r9, [rsp+1F8h+pvarg]; unsigned int *
0x180082ae4  mov     r8, r14; struct tagVARIANT *
0x180082ae7  mov     rdx, [rdi+0D8h]; HWND
0x180082aee  mov     rcx, rsi; struct IAccessible *
0x180082af1  call    ?get_accState@AccUtils@@SAJPEAUIAccessible@@PEAUHWND__@@AEBUtagVARIANT@@PEAK@Z; AccUtils::get_accState(IAccessible *,HWND__ *,tagVARIANT const &,ulong *)
0x180082af6  mov     esi, eax
0x180082af8  test    eax, eax
0x180082afa  js      loc_1800831E0
0x180082b00  test    dword ptr [rsp+1F8h+pvarg], 10000h
0x180082b08  jnz     loc_180083028
0x180082b0e  mov     rax, [r12]
0x180082b12  mov     rcx, r12
0x180082b15  mov     rax, [rax+10h]
0x180082b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b1e  mov     r9d, eax; int
0x180082b21  mov     r8, [rdi+0D8h]; HWND
0x180082b28  mov     rdx, r14; struct tagVARIANT *
0x180082b2b  mov     rcx, [rsp+1F8h+var_1C0]; struct IAccessible *
0x180082b30  call    ?CheckLocationForOffscreen@MsaaProxy@@CAHPEAUIAccessible@@AEAUtagVARIANT@@PEAUHWND__@@H@Z; MsaaProxy::CheckLocationForOffscreen(IAccessible *,tagVARIANT &,HWND__ *,int)
0x180082b35  neg     eax
0x180082b37  jmp     loc_180082D20
0x180082b3c  mov     r8, rsi
0x180082b3f  lea     rdx, [rsp+1F8h+pvarg]
0x180082b44  mov     rcx, r12
0x180082b47  call    ?GetHasKeyboardFocusPropertyValue@MsaaProxy@@AEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@PEAUIAccessible@@@Z; MsaaProxy::GetHasKeyboardFocusPropertyValue(IAccessible *)
0x180082b4c  jmp     loc_1800829E2
0x180082b51  mov     r9, [rdi+0D8h]
0x180082b58  mov     [rbx+8], r13
0x180082b5c  mov     r8, cs:off_1802E3538; "IAccessible::get_accName"
0x180082b63  mov     [rsp+1F8h+var_198], r8
0x180082b68  mov     [rsp+1F8h+var_190], rsi
0x180082b6d  mov     dword ptr [rsp+1F8h+var_188], r9d
0x180082b72  mov     rax, r9
0x180082b75  sar     rax, 20h
0x180082b79  mov     dword ptr [rsp+1F8h+var_188+4], eax
0x180082b7d  mov     [rsp+1F8h+var_17C], 258h
0x180082b85  mov     eax, 1
0x180082b8a  mov     [rsp+1F8h+var_178], al
0x180082b91  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180082b98  jnz     loc_180082FD5
0x180082b9e  movups  xmm0, xmmword ptr [rdi+130h]
0x180082ba5  movaps  xmmword ptr [rsp+1F8h+pvarg], xmm0
0x180082baa  movsd   xmm1, qword ptr [rdi+140h]
0x180082bb2  movsd   qword ptr [rsp+1F8h+pvarg+10h], xmm1
0x180082bb8  lea     r8, [rbx+8]
0x180082bbc  lea     rdx, [rsp+1F8h+pvarg]
0x180082bc1  mov     rcx, rsi; this
0x180082bc4  call    ?RemoveFromSelection@SelectionItemRedirect@@EEAAJXZ; SelectionItemRedirect::RemoveFromSelection(void)
0x180082bc9  mov     edi, eax
0x180082bcb  mov     [rsp+1F8h+var_180], eax
0x180082bcf  cmp     eax, 80020003h
0x180082bd4  jnz     loc_180083032
0x180082bda  mov     [rsp+1F8h+var_180], r13d
0x180082bdf  lea     rcx, [rsp+1F8h+var_198]; this
0x180082be4  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x180082be9  mov     edi, r13d
0x180082bec  test    edi, edi
0x180082bee  jns     loc_1800831C6
0x180082bf4  mov     rcx, [rsp+1F8h]; this
0x180082bfc  mov     r9d, edi; char *
0x180082bff  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180082c06  mov     edx, 376h; void *
0x180082c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c10  nop
0x180082c11  mov     rcx, [rsp+1F8h+var_1C0]
0x180082c16  test    rcx, rcx
0x180082c19  jz      short loc_180082C28
0x180082c1b  mov     rax, [rcx]
0x180082c1e  mov     rax, [rax+10h]
0x180082c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c27  nop
0x180082c28  mov     rcx, [rsp+1F8h+var_1C8]
0x180082c2d  test    rcx, rcx
0x180082c30  jz      short loc_180082C3F
0x180082c32  mov     rdx, [rcx]
0x180082c35  mov     rax, [rdx+10h]
0x180082c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c3e  nop
0x180082c3f  mov     eax, edi
0x180082c41  jmp     loc_180082A3C
0x180082c46  test    edx, edx
0x180082c48  jz      loc_180082E41
0x180082c4e  mov     rcx, [rdi+0E8h]
0x180082c55  test    rcx, rcx
0x180082c58  jz      loc_180082E41
0x180082c5e  mov     rax, [rcx]
0x180082c61  lea     r9, [rsp+1F8h+var_1C0]
0x180082c66  lea     r8, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x180082c6d  mov     rax, [rax+28h]
0x180082c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c76  mov     r15d, eax
0x180082c79  jmp     loc_180082949
0x180082c7e  mov     rcx, r12; this
0x180082c81  call    ?ControlType@MsaaProxy@@AEAAHXZ; MsaaProxy::ControlType(void)
0x180082c86  test    eax, eax
0x180082c88  jz      short loc_180082C92
0x180082c8a  mov     word ptr [rbx], 3
0x180082c8f  mov     [rbx+8], eax
0x180082c92  xor     eax, eax
  ... truncated ...
```
