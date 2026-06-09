# UiaReturnRawElementProvider

- ea: `0x1800d8050`
- end: `0x1800d89e3`
- name: `UiaReturnRawElementProvider`
- size: `2451`
- prototype: `LONG_PTR __stdcall(HWND hwnd, WPARAM wParam, LPARAM lParam, IRawElementProviderSimple *el)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d8050`

## callees

- `0x18000b790`
- `0x18000f680`
- `0x1800288d0`
- `0x180029d54`
- `0x18002b608`
- `0x18002f580`
- `0x180036198`
- `0x180061aec`
- `0x180062520`
- `0x180063580`
- `0x180063720`
- `0x180069888`
- `0x180080cc0`
- `0x1800d8050`
- `0x1800d89ec`
- `0x1800d9490`
- `0x180137bf8`
- `0x180149464`
- `0x180156a48`
- `0x180196a0c`
- `0x1801c80a0`
- `0x1801d8148`
- `0x1801e5c4c`
- `0x1801e8320`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1801e9258`
- `0x1801ef320`
- `0x1801f1280`
- `0x180236814`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d81cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d81cc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x1800d88ca`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x1800d88ca`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800d848f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800d84b0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800d848f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800d84b0`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-2!IsEnhancedWindowingEnabled` at `0x1800d87bc`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-2!IsEnhancedWindowingEnabled` at `0x1800d87bc`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!GetUiaEndpoint` at `0x1800d87e1`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-1!GetUiaEndpoint` at `0x1800d87e1`

## string_xrefs

- `0x1800d8610`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1800d86b9`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1800d8737`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1800d874d`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1800d83f2`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`
- `0x1800d8828`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`
- `0x1800d8845`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`
- `0x1800d8223`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi2.cpp`
- `0x1800d88ff`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi2.cpp`
- `0x1800d8971`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi2.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LONG_PTR __stdcall UiaReturnRawElementProvider(HWND hwnd, WPARAM wParam, LPARAM lParam, IRawElementProviderSimple *el)
{
  __int64 v8; // r13
  int v9; // eax
  int v10; // r8d
  LONG_PTR v11; // rbx
  struct IUiaNode *v12; // rax
  DWORD CurrentProcessId; // r15d
  int v14; // eax
  int v15; // edi
  struct IUiaNode *v16; // rcx
  int v17; // r8d
  PVOID v19; // rcx
  int v20; // r8d
  PVOID v21; // rcx
  PVOID v22; // rcx
  int v23; // r8d
  __int64 v24; // rcx
  bool v25; // al
  __int64 v26; // rax
  bool v27; // r15
  __int64 v28; // rcx
  __int64 v29; // rdi
  int v30; // eax
  ChannelBasedServerConnectionManager *v31; // rcx
  struct IUiaNode *v32; // rcx
  struct IUiaNode *v33; // rcx
  int v34; // r8d
  PVOID v35; // rcx
  struct IUiaNode *v36; // rcx
  __int64 v37; // rdx
  unsigned __int16 *v38; // r14
  __int64 v39; // rcx
  int v40; // eax
  int v41; // eax
  unsigned int PropW; // edi
  int ProviderEntryPointForCurrentView; // eax
  __int64 v44; // rdx
  int ProviderSideConnectionFormatString; // eax
  struct IUiaNode *v46; // rbx
  unsigned __int16 *v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  _BYTE v52[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IUiaNode *v53; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  IRawElementProviderSimple *ela; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v56[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v57; // [rsp+60h] [rbp-A0h]
  struct _GUID v58; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v59[2000]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1078h] [rbp+F78h]

  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v47 = (unsigned __int16 *)&v58;
    McGenEventWrite_EventWriteTransfer(hwnd, UIAutomationCoreAPI_UiaReturnRawElementProvider_Start);
  }
  v56[0] = "UiaReturnRawElementProvider";
  v56[1] = hwnd;
  v57 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      lParam,
      (unsigned int)"UiaReturnRawElementProvider",
      (char)hwnd,
      0);
  v54 = 0;
  v8 = -1;
  if ( dword_1803A3378 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 88LL) )
  {
    Init_thread_header(&dword_1803A3378);
    if ( dword_1803A3378 == -1 )
    {
      v25 = !BasicUiaUtils::IsDesktop()
         && (unsigned __int8)IsIsEnhancedWindowingEnabledPresent(v24)
         && (unsigned int)IsEnhancedWindowingEnabled(v39) != 0;
      byte_1803A337C = v25;
      Init_thread_footer(&dword_1803A3378);
    }
  }
  if ( byte_1803A337C )
  {
    v58 = GUID_NULL;
    if ( (unsigned int)GetUiaEndpoint(hwnd, &v58) )
    {
      v40 = UIAutomationProviderApi::ReturnRawElementProviderForEndpoint(&v58, wParam, lParam, el, &v54);
      v11 = v40;
      if ( v40 >= 0 )
        v11 = v54;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
          (const char *)(unsigned int)v40,
          v50);
LABEL_94:
      FlatApiCallTrace::~FlatApiCallTrace((FlatApiCallTrace *)v56);
LABEL_48:
      UiaReturnRawElementProvider_::_2_::PerfMarkerTrace::_PerfMarkerTrace(v52);
      return v11;
    }
  }
  v9 = CheckInit();
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
      (const char *)(unsigned int)v9,
      (int)v47);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v23,
        (unsigned int)"UiaReturnRawElementProvider",
        (char)hwnd,
        0);
    goto LABEL_48;
  }
  if ( el )
  {
    v53 = 0;
    ((void (__fastcall *)(IRawElementProviderSimple *, GUID *, struct IUiaNode **))el->lpVtbl->QueryInterface)(
      el,
      &GUID_a3d361a2_2919_42a1_b3dd_6595b432f2dd,
      &v53);
    v12 = v53;
    if ( v53 )
    {
      ela = 0;
      v53 = 0;
      *(_QWORD *)&v58.Data1 = v12;
      v41 = CrossMachineSurrogateRoot::ForHwndHost(hwnd, &v58);
      v11 = v41;
      if ( v41 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
          (const char *)(unsigned int)v41,
          (int)v47);
      else
        v11 = UiaReturnRawElementProvider(hwnd, wParam, lParam, ela);
      wil::com_ptr_t<CrossMachinePlaceholder,wil::err_exception_policy>::~com_ptr_t<CrossMachinePlaceholder,wil::err_exception_policy>(&ela);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v53);
      goto LABEL_94;
    }
  }
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( BasicUiaUtils::s_isDesktop )
  {
    v11 = MsaaBridge::HandleWMGetobject(hwnd, wParam, lParam, el);
    v54 = v11;
    if ( v11 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_sqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          v10,
          (unsigned int)"UiaReturnRawElementProvider",
          (char)hwnd,
          0);
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v19, "z");
      return v11;
    }
  }
  if ( (_DWORD)lParam == -25 )
  {
    if ( el )
    {
      v59[0] = 0;
      memset_0(&v59[1], 0, 0xF9Eu);
      CurrentProcessId = GetCurrentProcessId();
      v53 = 0;
      if ( !BasicUiaUtils::s_isDesktopDetermined )
      {
        BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
        BasicUiaUtils::s_isDesktopDetermined = 1;
      }
      if ( BasicUiaUtils::s_isDesktop )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        v14 = ProviderEntryPoint::CreateUsingHwnd(hwnd, &v53);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi2.cpp",
            (const char *)(unsigned int)v14,
            (int)v47);
          v16 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v16 + 16LL))(v16);
          }
          goto LABEL_23;
        }
LABEL_104:
        ProviderSideConnectionFormatString = ProviderEntryPoint::GetProviderSideConnectionFormatString(
                                               v53,
                                               wParam,
                                               CurrentProcessId,
                                               2000,
                                               v59);
        v15 = ProviderSideConnectionFormatString;
        if ( ProviderSideConnectionFormatString < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17F,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi2.cpp",
            (const char *)(unsigned int)ProviderSideConnectionFormatString,
            v51);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
          goto LABEL_23;
        }
        v46 = v53;
        v53 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        v38 = v59;
        v26 = -1;
        do
          ++v26;
        while ( v59[v26] );
        if ( v26 )
        {
          v27 = 0;
          if ( v59[0] != 33 )
            goto LABEL_56;
          v38 = &v59[1];
        }
        v27 = 1;
LABEL_56:
        if ( *((_DWORD *)v46 + 10) && (unsigned __int8)anonymous_namespace_::IsEmptyString(v38) )
        {
          v29 = -2147024809;
LABEL_67:
          v54 = v29;
LABEL_72:
          (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v46 + 16LL))(v46);
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_sqd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              v34,
              (unsigned int)"UiaReturnRawElementProvider",
              (char)hwnd,
              0);
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(v35, "z");
          return v29;
        }
        v53 = 0;
        LODWORD(v29) = UiaNodeFactory::FromLocalProvider(el, 0, 0, &v53, 0);
        if ( (int)v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x569,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
            (const char *)(unsigned int)v29,
            v48);
          v36 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v36 + 16LL))(v36);
          }
        }
        else
        {
          v30 = ChannelBasedServerConnectionManager::AddNodeToPendingObjects(v28, v53, v46, 4294967292LL);
          LODWORD(v29) = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x56A,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)(unsigned int)v30,
              0);
            v33 = v53;
            if ( v53 )
            {
              v53 = 0;
              (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v33 + 16LL))(v33);
            }
          }
          else
          {
            LODWORD(v29) = OverlappedIOManager::Init((OverlappedIOManager *)qword_18039E090);
            if ( (int)v29 < 0 )
            {
              v37 = 1401;
            }
            else
            {
              do
                ++v8;
              while ( v38[v8] );
              if ( !v8
                || (LODWORD(v29) = ChannelBasedServerConnectionManager::SetupConnectionEvents(v31, v38, v27),
                    (int)v29 >= 0) )
              {
                v32 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v32 + 16LL))(v32);
                }
                v29 = 0x10000;
                goto LABEL_67;
              }
              v37 = 1406;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v37,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)(unsigned int)v29,
              0);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x56D,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)(unsigned int)v29,
              v49);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
          }
        }
        v29 = (int)v29;
        v54 = v29;
        if ( !(_DWORD)v29 )
        {
          Error::GeneralProviderError((struct IUnknown *)el, L"LresultFromProvider", -2147467259, 0, 0, 0);
          v29 = v54;
        }
        goto LABEL_72;
      }
      PropW = (unsigned int)GetPropW(hwnd, L"Microsoft.Windows.WindowFactory.ViewId");
      if ( PropW )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        ProviderEntryPointForCurrentView = ProviderEntryPoint::CreateUsingViewId(PropW, &v53);
        v15 = ProviderEntryPointForCurrentView;
        if ( ProviderEntryPointForCurrentView >= 0 )
          goto LABEL_104;
        v44 = 373;
      }
      else
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
        ProviderEntryPointForCurrentView = UiaUtils::GetProviderEntryPointForCurrentView(hwnd, &v53);
        v15 = ProviderEntryPointForCurrentView;
        if ( ProviderEntryPointForCurrentView >= 0 )
          goto LABEL_104;
        v44 = 379;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v44,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi2.cpp",
        (const char *)(unsigned int)ProviderEntryPointForCurrentView,
        (int)v47);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
LABEL_23:
      Error::GeneralProviderError(
        (struct IUnknown *)el,
        L"GetProviderEntryPointAndConnectionFormatString",
        v15,
        0,
        0,
        0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_sqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          v17,
          (unsigned int)"UiaReturnRawElementProvider",
          (char)hwnd,
          0);
      UiaReturnRawElementProvider_::_2_::PerfMarkerTrace::_PerfMarkerTrace(v52);
      return v15;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v10,
        (unsigned int)"UiaReturnRawElementProvider",
        (char)hwnd,
        0);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v22, "z");
    return -2147024809;
  }
  else
  {
    Error::GeneralProviderError((struct IUnknown *)el, L"UiaReturnRawElementProvider", -2147467259, 0, 428, 0);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v20,
        (unsigned int)"UiaReturnRawElementProvider",
        (char)hwnd,
        0);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v21, "z");
    return 0;
  }
}

```

## disassembly

```asm
0x1800d8050  push    rbp
0x1800d8052  push    rbx
0x1800d8053  push    rsi
0x1800d8054  push    rdi
0x1800d8055  push    r12
0x1800d8057  push    r13
0x1800d8059  push    r14
0x1800d805b  push    r15
0x1800d805d  lea     rbp, [rsp-0F38h]
0x1800d8065  mov     eax, 1038h
0x1800d806a  call    _alloca_probe
0x1800d806f  sub     rsp, rax
0x1800d8072  mov     rax, cs:__security_cookie
0x1800d8079  xor     rax, rsp
0x1800d807c  mov     [rbp+0F70h+var_50], rax
0x1800d8083  mov     r12, r9
0x1800d8086  mov     rdi, r8
0x1800d8089  mov     r14, rdx
0x1800d808c  mov     rsi, rcx
0x1800d808f  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800d8096  jnz     loc_1800D878E
0x1800d809c  lea     rax, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d80a3  mov     [rsp+1070h+var_1020], rax
0x1800d80a8  mov     [rsp+1070h+var_1018], rsi
0x1800d80ad  xor     r15d, r15d
0x1800d80b0  mov     [rsp+1070h+var_1010], r15d
0x1800d80b5  lea     rdx, WPP_GLOBAL_Control
0x1800d80bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d80c3  cmp     rcx, rdx
0x1800d80c6  jz      short loc_1800D80E8
0x1800d80c8  test    byte ptr [rcx+1Ch], 10h
0x1800d80cc  jz      short loc_1800D80E8
0x1800d80ce  lea     edx, [r15+0Bh]
0x1800d80d2  mov     [rsp+1070h+var_1048], r15d
0x1800d80d7  mov     [rsp+1070h+var_1050], rsi; int
0x1800d80dc  mov     r9, rax
0x1800d80df  mov     rcx, [rcx+10h]
0x1800d80e3  call    WPP_SF_sqd
0x1800d80e8  mov     [rsp+1070h+var_1030], r15
0x1800d80ed  mov     ecx, cs:_tls_index
0x1800d80f3  mov     rax, gs:58h
0x1800d80fc  mov     edx, 58h ; 'X'
0x1800d8101  mov     rax, [rax+rcx*8]
0x1800d8105  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800d8109  mov     eax, [rdx+rax]
0x1800d810c  cmp     cs:dword_1803A3378, eax
0x1800d8112  jg      loc_1800D844A
0x1800d8118  cmp     cs:byte_1803A337C, r15b
0x1800d811f  jnz     loc_1800D87CC
0x1800d8125  call    ?CheckInit@@YAJXZ; CheckInit(void)
0x1800d812a  movsxd  rbx, eax
0x1800d812d  test    eax, eax
0x1800d812f  js      loc_1800D83E8
0x1800d8135  test    r12, r12
0x1800d8138  jz      short loc_1800D8169
0x1800d813a  mov     [rsp+1070h+var_1038], r15
0x1800d813f  mov     rax, [r12]
0x1800d8143  lea     r8, [rsp+1070h+var_1038]
0x1800d8148  lea     rdx, _GUID_a3d361a2_2919_42a1_b3dd_6595b432f2dd
0x1800d814f  mov     rcx, r12
0x1800d8152  mov     rax, [rax]
0x1800d8155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d815a  nop
0x1800d815b  mov     rax, [rsp+1070h+var_1038]
0x1800d8160  test    rax, rax
0x1800d8163  jnz     loc_1800D8880
0x1800d8169  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800d816f  nop
0x1800d8170  test    al, al
0x1800d8172  jz      loc_1800D848A
0x1800d8178  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r15b; bool BasicUiaUtils::s_isDesktop
0x1800d817f  jz      short loc_1800D81A3
0x1800d8181  mov     r9, r12; struct IRawElementProviderSimple *
0x1800d8184  mov     r8, rdi; __int64
0x1800d8187  mov     rdx, r14; unsigned __int64
0x1800d818a  mov     rcx, rsi; HWND
0x1800d818d  call    ?HandleWMGetobject@MsaaBridge@@SA_JPEAUHWND__@@_K_JPEAUIRawElementProviderSimple@@@Z; MsaaBridge::HandleWMGetobject(HWND__ *,unsigned __int64,__int64,IRawElementProviderSimple *)
0x1800d8192  mov     rbx, rax
0x1800d8195  mov     [rsp+1070h+var_1030], rax
0x1800d819a  test    rax, rax
0x1800d819d  jnz     loc_1800D82BB
0x1800d81a3  cmp     edi, 0FFFFFFE7h
0x1800d81a6  jnz     loc_1800D8326
0x1800d81ac  test    r12, r12
0x1800d81af  jz      loc_1800D8397
0x1800d81b5  mov     [rbp+0F70h+var_FF0], r15w
0x1800d81ba  xor     edx, edx; Val
0x1800d81bc  mov     r8d, 0F9Eh; Size
0x1800d81c2  lea     rcx, [rbp+0F70h+var_FF0+2]; void *
0x1800d81c6  call    memset_0
0x1800d81cb  nop
0x1800d81cc  call    cs:__imp_GetCurrentProcessId
0x1800d81d2  mov     r15d, eax
0x1800d81d5  xor     edi, edi
0x1800d81d7  mov     [rsp+1070h+var_1038], rdi
0x1800d81dc  mov     dl, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800d81e2  nop
0x1800d81e3  test    dl, dl
0x1800d81e5  jz      loc_1800D84AB
0x1800d81eb  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, dil; bool BasicUiaUtils::s_isDesktop
0x1800d81f2  jz      loc_1800D88C0
0x1800d81f8  lea     rcx, [rsp+1070h+var_1038]
0x1800d81fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8202  lea     rdx, [rsp+1070h+var_1038]; struct ProviderEntryPoint **
0x1800d8207  mov     rcx, rsi; HWND
0x1800d820a  call    ?CreateUsingHwnd@ProviderEntryPoint@@SAJPEAUHWND__@@PEAPEAV1@@Z; ProviderEntryPoint::CreateUsingHwnd(HWND__ *,ProviderEntryPoint * *)
0x1800d820f  mov     edi, eax
0x1800d8211  test    eax, eax
0x1800d8213  jns     loc_1800D893F
0x1800d8219  mov     rcx, [rbp+0F78h]; this
0x1800d8220  mov     r9d, eax; char *
0x1800d8223  lea     r8, aOnecoreWindows_133; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d822a  mov     edx, 16Bh; void *
0x1800d822f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8234  nop
0x1800d8235  mov     rcx, [rsp+1070h+var_1038]
0x1800d823a  xor     r14d, r14d
0x1800d823d  test    rcx, rcx
0x1800d8240  jz      short loc_1800D8254
0x1800d8242  mov     [rsp+1070h+var_1038], r14
0x1800d8247  mov     rax, [rcx]
0x1800d824a  mov     rax, [rax+10h]
0x1800d824e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8253  nop
0x1800d8254  mov     [rsp+1070h+var_1048], r14d; int
0x1800d8259  mov     dword ptr [rsp+1070h+var_1050], r14d; int
0x1800d825e  xor     r9d, r9d; struct ProviderEntryPoint *
0x1800d8261  mov     r8d, edi; int
0x1800d8264  lea     rdx, aGetproviderent; "GetProviderEntryPointAndConnectionForma"...
0x1800d826b  mov     rcx, r12; struct IUnknown *
0x1800d826e  call    ?GeneralProviderError@Error@@CAXPEAUIUnknown@@PEBGJPEBVProviderEntryPoint@@HH@Z; Error::GeneralProviderError(IUnknown *,ushort const *,long,ProviderEntryPoint const *,int,int)
0x1800d8273  nop
0x1800d8274  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d827b  lea     rax, WPP_GLOBAL_Control
0x1800d8282  cmp     rcx, rax
0x1800d8285  jz      short loc_1800D82AC
0x1800d8287  test    byte ptr [rcx+1Ch], 10h
0x1800d828b  jz      short loc_1800D82AC
0x1800d828d  mov     edx, 0Dh
0x1800d8292  mov     [rsp+1070h+var_1048], r14d
0x1800d8297  mov     [rsp+1070h+var_1050], rsi
0x1800d829c  lea     r9, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d82a3  mov     rcx, [rcx+10h]
0x1800d82a7  call    WPP_SF_sqd
0x1800d82ac  lea     rcx, [rsp+1070h+var_1040]
0x1800d82b1  call    _UiaReturnRawElementProvider____2___PerfMarkerTrace___PerfMarkerTrace
0x1800d82b6  movsxd  rax, edi
0x1800d82b9  jmp     short loc_1800D8303
0x1800d82bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d82c2  lea     rax, WPP_GLOBAL_Control
0x1800d82c9  cmp     rcx, rax
0x1800d82cc  jz      short loc_1800D82F3
0x1800d82ce  test    byte ptr [rcx+1Ch], 10h
0x1800d82d2  jz      short loc_1800D82F3
0x1800d82d4  mov     edx, 0Dh
0x1800d82d9  mov     [rsp+1070h+var_1048], r15d
0x1800d82de  mov     [rsp+1070h+var_1050], rsi
0x1800d82e3  lea     r9, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d82ea  mov     rcx, [rcx+10h]
0x1800d82ee  call    WPP_SF_sqd
0x1800d82f3  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800d82fa  jnz     loc_1800D84CC
0x1800d8300  mov     rax, rbx
0x1800d8303  mov     rcx, [rbp+0F70h+var_50]
0x1800d830a  xor     rcx, rsp; StackCookie
0x1800d830d  call    __security_check_cookie
0x1800d8312  add     rsp, 1038h
0x1800d8319  pop     r15
0x1800d831b  pop     r14
0x1800d831d  pop     r13
0x1800d831f  pop     r12
0x1800d8321  pop     rdi
0x1800d8322  pop     rsi
0x1800d8323  pop     rbx
0x1800d8324  pop     rbp
0x1800d8325  retn
0x1800d8326  mov     [rsp+1070h+var_1048], r15d; int
0x1800d832b  mov     dword ptr [rsp+1070h+var_1050], 1ACh; int
0x1800d8333  xor     r9d, r9d; struct ProviderEntryPoint *
0x1800d8336  mov     r8d, 80004005h; int
0x1800d833c  lea     rdx, aUiareturnrawel_1; "UiaReturnRawElementProvider"
0x1800d8343  mov     rcx, r12; struct IUnknown *
0x1800d8346  call    ?GeneralProviderError@Error@@CAXPEAUIUnknown@@PEBGJPEBVProviderEntryPoint@@HH@Z; Error::GeneralProviderError(IUnknown *,ushort const *,long,ProviderEntryPoint const *,int,int)
0x1800d834b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8352  lea     rax, WPP_GLOBAL_Control
0x1800d8359  cmp     rcx, rax
0x1800d835c  jz      short loc_1800D8383
0x1800d835e  test    byte ptr [rcx+1Ch], 10h
0x1800d8362  jz      short loc_1800D8383
0x1800d8364  mov     edx, 0Dh
0x1800d8369  mov     [rsp+1070h+var_1048], r15d
0x1800d836e  mov     [rsp+1070h+var_1050], rsi
0x1800d8373  lea     r9, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d837a  mov     rcx, [rcx+10h]
0x1800d837e  call    WPP_SF_sqd
0x1800d8383  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800d838a  jnz     loc_1800D84ED
0x1800d8390  xor     eax, eax
0x1800d8392  jmp     loc_1800D8303
0x1800d8397  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d839e  lea     rax, WPP_GLOBAL_Control
0x1800d83a5  cmp     rcx, rax
0x1800d83a8  jz      short loc_1800D83CF
0x1800d83aa  test    byte ptr [rcx+1Ch], 10h
0x1800d83ae  jz      short loc_1800D83CF
0x1800d83b0  mov     edx, 0Dh
0x1800d83b5  mov     [rsp+1070h+var_1048], r15d
0x1800d83ba  mov     [rsp+1070h+var_1050], rsi
0x1800d83bf  lea     r9, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d83c6  mov     rcx, [rcx+10h]
0x1800d83ca  call    WPP_SF_sqd
0x1800d83cf  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800d83d6  jnz     loc_1800D850E
0x1800d83dc  mov     rax, 0FFFFFFFF80070057h
0x1800d83e3  jmp     loc_1800D8303
0x1800d83e8  mov     rcx, [rbp+0F78h]; this
0x1800d83ef  mov     r9d, ebx; char *
0x1800d83f2  lea     r8, aOnecoreWindows_45; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d83f9  mov     edx, 4Dh ; 'M'; void *
0x1800d83fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8403  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d840a  lea     rax, WPP_GLOBAL_Control
0x1800d8411  cmp     rcx, rax
0x1800d8414  jz      short loc_1800D843B
0x1800d8416  test    byte ptr [rcx+1Ch], 10h
0x1800d841a  jz      short loc_1800D843B
0x1800d841c  mov     edx, 0Dh
0x1800d8421  mov     [rsp+1070h+var_1048], r15d
0x1800d8426  mov     [rsp+1070h+var_1050], rsi
0x1800d842b  lea     r9, aUiareturnrawel_2; "UiaReturnRawElementProvider"
0x1800d8432  mov     rcx, [rcx+10h]
0x1800d8436  call    WPP_SF_sqd
0x1800d843b  lea     rcx, [rsp+1070h+var_1040]
0x1800d8440  call    _UiaReturnRawElementProvider____2___PerfMarkerTrace___PerfMarkerTrace
0x1800d8445  jmp     loc_1800D8300
0x1800d844a  lea     rcx, dword_1803A3378
0x1800d8451  call    _Init_thread_header
0x1800d8456  cmp     cs:dword_1803A3378, r13d
0x1800d845d  jnz     loc_1800D8118
0x1800d8463  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x1800d8468  test    al, al
0x1800d846a  jz      loc_1800D87AF
0x1800d8470  mov     al, r15b
0x1800d8473  mov     cs:byte_1803A337C, al
0x1800d8479  lea     rcx, dword_1803A3378
0x1800d8480  call    _Init_thread_footer
0x1800d8485  jmp     loc_1800D8118
0x1800d848a  mov     ecx, 1800h; nIndex
0x1800d848f  call    cs:__imp_GetSystemMetrics
0x1800d8495  test    eax, eax
0x1800d8497  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x1800d849e  nop
0x1800d849f  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800d84a6  jmp     loc_1800D8178
0x1800d84ab  mov     ecx, 1800h; nIndex
0x1800d84b0  call    cs:__imp_GetSystemMetrics
0x1800d84b6  test    eax, eax
0x1800d84b8  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x1800d84bf  nop
0x1800d84c0  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800d84c7  jmp     loc_1800D81EB
0x1800d84cc  lea     rax, [rsp+1070h+var_1000]
0x1800d84d1  mov     [rsp+1070h+var_1050], rax
0x1800d84d6  mov     r9d, 1
0x1800d84dc  lea     rdx, UIAutomationCoreAPI_UiaReturnRawElementProvider_Stop; "z"
0x1800d84e3  call    McGenEventWrite_EventWriteTransfer
0x1800d84e8  jmp     loc_1800D8300
0x1800d84ed  lea     rax, [rsp+1070h+var_1000]
0x1800d84f2  mov     [rsp+1070h+var_1050], rax
0x1800d84f7  mov     r9d, 1
0x1800d84fd  lea     rdx, UIAutomationCoreAPI_UiaReturnRawElementProvider_Stop; "z"
0x1800d8504  call    McGenEventWrite_EventWriteTransfer
0x1800d8509  jmp     loc_1800D8390
0x1800d850e  lea     rax, [rsp+1070h+var_1000]
0x1800d8513  mov     [rsp+1070h+var_1050], rax
0x1800d8518  mov     r9d, 1
0x1800d851e  lea     rdx, UIAutomationCoreAPI_UiaReturnRawElementProvider_Stop; "z"
0x1800d8525  call    McGenEventWrite_EventWriteTransfer
0x1800d852a  jmp     loc_1800D83DC
0x1800d852f  inc     rax
0x1800d8532  cmp     [rcx+rax*2], di
0x1800d8536  jnz     short loc_1800D852F
0x1800d8538  test    rax, rax
0x1800d853b  jnz     loc_1800D870E
0x1800d8541  mov     r15b, 1
0x1800d8544  cmp     [rbx+28h], edi
0x1800d8547  jnz     loc_1800D85E5
0x1800d854d  mov     [rsp+1070h+var_1038], rdi
0x1800d8552  mov     [rsp+1070h+var_1050], rdi; int
0x1800d8557  lea     r9, [rsp+1070h+var_1038]; struct IUiaNode **
0x1800d855c  xor     r8d, r8d; struct UiaClientState *
0x1800d855f  xor     edx, edx; int
0x1800d8561  mov     rcx, r12; struct IRawElementProviderSimple *
0x1800d8564  call    ?FromLocalProvider@UiaNodeFactory@@SAJPEAUIRawElementProviderSimple@@HPEAVUiaClientState@@PEAPEAVIUiaNode@@PEAH@Z; UiaNodeFactory::FromLocalProvider(IRawElementProviderSimple *,int,UiaClientState *,IUiaNode * *,int *)
0x1800d8569  mov     edi, eax
0x1800d856b  xor     eax, eax
0x1800d856d  test    edi, edi
0x1800d856f  js      loc_1800D86AF
0x1800d8575  mov     [rsp+1070h+var_1048], eax
0x1800d8579  mov     dword ptr [rsp+1070h+var_1050], eax; int
  ... truncated ...
```
