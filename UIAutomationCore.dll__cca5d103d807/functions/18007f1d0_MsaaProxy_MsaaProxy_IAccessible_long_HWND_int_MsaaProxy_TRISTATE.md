# MsaaProxy::MsaaProxy(IAccessible *,long,HWND__ *,int,MsaaProxy::TRISTATE)

- ea: `0x18007f1d0`
- end: `0x1800805d9`
- name: `??0MsaaProxy@@IEAA@PEAUIAccessible@@JPEAUHWND__@@HW4TRISTATE@0@@Z`
- size: `5129`
- prototype: `MsaaProxy *__high(struct IAccessible *, int, HWND, int, enum MsaaProxy::TRISTATE)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005fe58`
- `0x18007de18`
- `0x18007e420`
- `0x18007ece0`
- `0x1800b92e0`
- `0x1800d206c`

## callees

- `0x180020230`
- `0x18002f580`
- `0x180036198`
- `0x18007e37c`
- `0x18007f1d0`
- `0x1800805e0`
- `0x180080cc0`
- `0x1800d9490`
- `0x180109ee8`
- `0x18012b47c`
- `0x1801a1438`
- `0x1801e887c`
- `0x1801e9234`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f5b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f969`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f5b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f65d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f65d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fa5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f6ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007faae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f6ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007faae`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180080432`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18008057c`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180080432`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18008057c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f4a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f4a9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007f506`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007f8be`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007fcd9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007fdaa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007f506`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007f8be`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007fcd9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007fdaa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800802fe`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18008031f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800803af`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800802fe`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18008031f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800803af`

## string_xrefs

- `0x18007fe96`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x18007ff50`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x18007ffe1`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x180080088`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x180080366`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x18008038d`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x1800801c9`: `IAccessibleEx::QueryInterface`
- `0x180080136`: `IAccessibleEx::GetObjectForChild`
- `0x18007fb40`: `IServiceProvider::QueryService`
- `0x18007fbce`: `IServiceProvider::QueryService`
- `0x1800804a6`: `IServiceProvider::QueryService`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall MsaaProxy::MsaaProxy(__int64 a1, struct IUnknown *a2, int a3, HWND a4, APTTYPE a5, APTTYPE pAptType)
{
  APTTYPE v10; // r15d
  __int64 *v11; // rbx
  __int64 v12; // rbx
  HRESULT ApartmentType; // eax
  struct IAccessibleEx *v14; // rax
  struct IAccessibleEx *v15; // rdi
  struct IAccessibleEx *v16; // rbx
  DWORD CurrentThreadId; // r10d
  _QWORD *v18; // rdx
  __int64 v19; // rax
  struct IAccessibleExVtbl *lpVtbl; // rax
  struct ProviderEntryPoint *v21; // rbx
  __int64 v22; // rax
  struct ProviderEntryPoint *v23; // rcx
  struct IAccessibleEx *v24; // rdi
  struct IUnknown *v25; // r12
  __int64 v26; // rbx
  APTTYPE v27; // r13d
  __int64 v28; // rbx
  struct IAccessibleEx *v29; // rbx
  struct IAccessibleEx *v30; // rax
  struct ProviderEntryPoint *v31; // rcx
  struct IAccessibleEx *v32; // rdx
  struct IAccessibleEx *v33; // r15
  __int64 v34; // rbx
  HRESULT v35; // eax
  struct ProviderEntryPoint *v36; // rax
  struct ProviderEntryPoint *v37; // rsi
  volatile signed __int32 *v38; // rbx
  DWORD v39; // r10d
  _QWORD *v40; // rdx
  __int64 v41; // rax
  HRESULT (__stdcall *GetObjectForChild)(IAccessibleEx *, int, IAccessibleEx **); // r15
  struct IAccessibleEx *v43; // rcx
  __int64 v44; // rax
  struct IAccessibleEx *v46; // rcx
  void (__fastcall *v47)(struct ProviderEntryPoint *, GUID *, GUID *, struct IAccessibleEx **); // rdi
  __int64 v48; // rcx
  HRESULT v49; // eax
  struct IAccessibleEx *v50; // rax
  int v51; // eax
  HRESULT v52; // eax
  struct IAccessibleEx *v53; // rax
  int v54; // eax
  HRESULT v55; // r13d
  struct ProviderEntryPoint *v56; // rax
  int v57; // eax
  HRESULT ClassObject; // r15d
  struct IAccessibleEx *v59; // rax
  int v60; // eax
  int ObjectForChild; // r15d
  struct ProviderEntryPoint *v62; // rbx
  struct ProviderEntryPoint *v63; // rbx
  LPVOID *ppv; // [rsp+20h] [rbp-58h]
  struct IAccessibleEx *v65; // [rsp+30h] [rbp-48h] BYREF
  struct IAccessibleEx *v66; // [rsp+38h] [rbp-40h]
  struct IUnknown *v67; // [rsp+40h] [rbp-38h]
  _QWORD v68[3]; // [rsp+48h] [rbp-30h] BYREF
  int v69; // [rsp+60h] [rbp-18h]
  int v70; // [rsp+64h] [rbp-14h]
  char v71; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  struct IAccessibleEx *v73; // [rsp+C8h] [rbp+50h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+D0h] [rbp+58h] BYREF
  struct ProviderEntryPoint *v75; // [rsp+D8h] [rbp+60h] BYREF

  *(_QWORD *)a1 = &RefcountBase::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  _InterlockedIncrement(&dword_18039DE7C);
  *(_QWORD *)a1 = &MsaaProxy::`vftable'{for `RefcountBase'};
  *(_QWORD *)(a1 + 16) = &MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderSimple2'};
  *(_QWORD *)(a1 + 24) = &MsaaProxy::`vftable'{for `IRawElementProviderFragment'};
  *(_QWORD *)(a1 + 32) = &MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderFragmentRoot'};
  *(_QWORD *)(a1 + 40) = &MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderTempIdString'};
  *(_QWORD *)(a1 + 48) = &MsaaNonClientProxyElement::`vftable'{for `IServiceProvider'};
  *(_QWORD *)(a1 + 56) = &MsaaProxy::`vftable'{for `IProxyProviderWinEventHandler'};
  *(_QWORD *)(a1 + 64) = &MsaaNonClientProxyElement::`vftable'{for `IExpandCollapseProvider'};
  *(_QWORD *)(a1 + 72) = &MsaaProxy::`vftable'{for `IInvokeProvider'};
  *(_QWORD *)(a1 + 80) = &MsaaNonClientProxyElement::`vftable'{for `IToggleProvider'};
  *(_QWORD *)(a1 + 88) = &MsaaProxy::`vftable'{for `ISelectionProvider'};
  *(_QWORD *)(a1 + 96) = &MsaaProxy::`vftable'{for `ISelectionItemProvider'};
  *(_QWORD *)(a1 + 104) = &MsaaProxy::`vftable'{for `IValueProvider'};
  *(_QWORD *)(a1 + 112) = &MsaaProxy::`vftable'{for `IRangeValueProvider'};
  *(_QWORD *)(a1 + 120) = &MsaaProxy::`vftable'{for `IGridProvider'};
  *(_QWORD *)(a1 + 128) = &MsaaProxy::`vftable'{for `IGridItemProvider'};
  *(_QWORD *)(a1 + 136) = &MsaaNonClientProxyElement::`vftable'{for `ITableProvider'};
  *(_QWORD *)(a1 + 144) = &MsaaNonClientProxyElement::`vftable'{for `ITableItemProvider'};
  *(_QWORD *)(a1 + 152) = &MsaaProxy::`vftable'{for `IScrollItemProvider'};
  *(_QWORD *)(a1 + 160) = &MsaaProxy::`vftable'{for `ILegacyIAccessibleProvider'};
  *(_QWORD *)(a1 + 168) = &MsaaNonClientProxyElement::`vftable'{for `ITextProvider2'};
  *(_QWORD *)(a1 + 176) = &MsaaNonClientProxyElement::`vftable'{for `ITextEditProvider'};
  *(_QWORD *)(a1 + 184) = &MsaaNonClientProxyElement::`vftable'{for `ITextChildProvider'};
  *(_QWORD *)(a1 + 192) = &MsaaNonClientProxyElement::`vftable'{for `IAccIdentity'};
  *(_QWORD *)(a1 + 200) = &MsaaProxy::`vftable'{for `IAccProxyVersion'};
  *(_QWORD *)(a1 + 208) = &MsaaNonClientProxyElement::`vftable'{for `IAccTimeout'};
  *(_QWORD *)(a1 + 216) = &MsaaNonClientProxyElement::`vftable'{for `IInternalMsaaProxy'};
  *(_QWORD *)(a1 + 224) = &MsaaProxy::`vftable'{for `IBuiltInProxy'};
  *(_QWORD *)(a1 + 232) = a4;
  v10 = a5;
  *(_DWORD *)(a1 + 240) = a5;
  v11 = (__int64 *)(a1 + 248);
  *(_QWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_DWORD *)(a1 + 280) = 0;
  *(_DWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_DWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 0;
  *(_QWORD *)(a1 + 360) = 0;
  *(_DWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 376) = 0;
  *(_QWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  *(_DWORD *)(a1 + 408) = 0;
  *(_DWORD *)(a1 + 412) = pAptType;
  *(_DWORD *)(a1 + 416) = 2;
  *(_DWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_DWORD *)(a1 + 448) = 0;
  *(_DWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_DWORD *)(a1 + 480) = 0;
  *(_BYTE *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 492) = 0;
  *(_QWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 0;
  *(_DWORD *)(a1 + 520) = 0;
  *(_DWORD *)(a1 + 528) = 0;
  *(_QWORD *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 544) = 0;
  *(_DWORD *)(a1 + 552) = 0;
  *(_DWORD *)(a1 + 560) = 0;
  CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, (LPVOID *)(a1 + 248));
  v12 = *v11;
  *(_QWORD *)(a1 + 264) = 0;
  *(_DWORD *)(a1 + 280) = 0;
  *(_DWORD *)(a1 + 256) = 0;
  if ( !a2 )
    goto LABEL_26;
  pAptType = APTTYPE_MTA;
  if ( v10 == APTTYPE_STA )
    goto LABEL_95;
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( BasicUiaUtils::s_isDesktop )
  {
    pAptQualifier = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
    if ( ApartmentType == -2147221008 )
    {
      pAptType = APTTYPE_NA;
      goto LABEL_181;
    }
    if ( ApartmentType < 0 )
      goto LABEL_12;
  }
  if ( pAptType == APTTYPE_NA )
  {
LABEL_181:
    *(_QWORD *)(a1 + 264) = a2;
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    goto LABEL_26;
  }
  if ( pAptType && pAptType != APTTYPE_MAINSTA )
  {
    if ( pAptType != APTTYPE_MTA )
      goto LABEL_26;
LABEL_95:
    if ( v12
      && (*(int (__fastcall **)(__int64, struct IUnknown *, GUID *, __int64))(*(_QWORD *)v12 + 24LL))(
           v12,
           a2,
           &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
           a1 + 280) >= 0 )
    {
      goto LABEL_26;
    }
LABEL_12:
    *(_DWORD *)(a1 + 256) = 1;
    goto LABEL_26;
  }
  v14 = (struct IAccessibleEx *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v15 = v14;
  v73 = v14;
  if ( !v14 )
  {
    *(_QWORD *)(a1 + 272) = 0;
    *(_DWORD *)(a1 + 256) = 1;
    goto LABEL_26;
  }
  v16 = 0;
  v14[2].lpVtbl = 0;
  v14[3].lpVtbl = 0;
  v14->lpVtbl = (struct IAccessibleExVtbl *)&RefcountBase::`vftable';
  LODWORD(v14[1].lpVtbl) = 1;
  _InterlockedIncrement(&dword_18039DE7C);
  v14->lpVtbl = (struct IAccessibleExVtbl *)&CApartmentTracker::`vftable'{for `RefcountBase'};
  v14[4].lpVtbl = 0;
  LODWORD(v14[5].lpVtbl) = 0;
  *(_QWORD *)(a1 + 272) = v14;
  v75 = 0;
  if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
  {
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
    v73 = 0;
    ClassObject = CoGetClassObject(
                    &CLSID_CUIAutomation,
                    1u,
                    0,
                    &GUID_00000001_0000_0000_c000_000000000046,
                    (LPVOID *)&v73);
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
    if ( ClassObject < 0 )
      goto LABEL_143;
    if ( v73 )
    {
      ((void (__fastcall *)(struct IAccessibleEx *))v73->lpVtbl->Release)(v73);
      v73 = 0;
    }
    g_ComMitigationDone = 1;
  }
  EnterCriticalSection(&CApartmentTracker::_classLock);
  CurrentThreadId = GetCurrentThreadId();
  _mm_lfence();
  v18 = (char *)Block
      + 16
      * (qword_18039F790
       & (0x100000001B3LL
        * (HIBYTE(CurrentThreadId)
         ^ (0x100000001B3LL
          * (BYTE2(CurrentThreadId)
           ^ (0x100000001B3LL
            * ((0x100000001B3LL * ((unsigned __int8)CurrentThreadId ^ 0xCBF29CE484222325uLL)) ^ BYTE1(CurrentThreadId))))))));
  v19 = v18[1];
  if ( v19 == qword_18039F768 )
  {
LABEL_98:
    v19 = 0;
  }
  else
  {
    while ( CurrentThreadId != *(_DWORD *)(v19 + 16) )
    {
      if ( v19 == *v18 )
        goto LABEL_98;
      v19 = *(_QWORD *)(v19 + 8);
    }
  }
  if ( !v19 )
    v19 = qword_18039F768;
  if ( v19 != qword_18039F768 )
    v16 = *(struct IAccessibleEx **)(v19 + 24);
  LeaveCriticalSection(&CApartmentTracker::_classLock);
  if ( !v16 )
  {
    v59 = (struct IAccessibleEx *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v16 = v59;
    v73 = v59;
    if ( v59 )
    {
      v59->lpVtbl = (struct IAccessibleExVtbl *)&RefcountBase::`vftable';
      LODWORD(v59[1].lpVtbl) = 1;
      _InterlockedIncrement(&dword_18039DE7C);
      v59->lpVtbl = (struct IAccessibleExVtbl *)&CApartmentTracker::`vftable'{for `RefcountBase'};
      v59[2].lpVtbl = (struct IAccessibleExVtbl *)&CApartmentTracker::`vftable'{for `IInitializeSpy'};
      LODWORD(v59[3].lpVtbl) = 0;
      v59[5].lpVtbl = 0;
      v59[4].lpVtbl = 0;
      v73 = v59;
      v60 = CApartmentTracker::Initialize((CApartmentTracker *)v59);
      ClassObject = v60;
      if ( v60 >= 0 )
        goto LABEL_21;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)(unsigned int)v60,
        (int)ppv);
      AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v73);
    }
    else
    {
      v73 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)0x8007000ELL,
        (int)ppv);
      ClassObject = -2147024882;
    }
LABEL_143:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
      (const char *)(unsigned int)ClassObject,
      (int)ppv);
    *(_DWORD *)(a1 + 256) = 1;
    goto LABEL_26;
  }
  if ( !LODWORD(v16[3].lpVtbl) )
  {
    ClassObject = -2147467259;
    goto LABEL_143;
  }
  _InterlockedIncrement((volatile signed __int32 *)&v16[1]);
LABEL_21:
  v75 = (struct ProviderEntryPoint *)v16;
  _InterlockedIncrement((volatile signed __int32 *)&v15[1]);
  v15[2].lpVtbl = v16[5].lpVtbl;
  lpVtbl = v16[5].lpVtbl;
  if ( lpVtbl )
    lpVtbl->GetObjectForChild = (HRESULT (__stdcall *)(IAccessibleEx *, int, IAccessibleEx **))v15;
  v16[5].lpVtbl = (struct IAccessibleExVtbl *)v15;
  v15[4].lpVtbl = (struct IAccessibleExVtbl *)a2;
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  LODWORD(v15[5].lpVtbl) = GetCurrentThreadId();
  if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)&v16[1], 0xFFFFFFFF) == 1 )
    ((void (__fastcall *)(struct IAccessibleEx *, __int64))v16->lpVtbl->QueryInterface)(v16, 1);
LABEL_26:
  *(_WORD *)(a1 + 320) = 3;
  *(_DWORD *)(a1 + 328) = a3;
  v66 = 0;
  v67 = 0;
  v73 = 0;
  v75 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct ProviderEntryPoint **))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
    &v75);
  v21 = v75;
  if ( !v75 )
    goto LABEL_27;
  if ( memcmp_0(&GUID_f8b80ada_2c44_48d0_89be_5ff23c9cd875, &GUID_00000000_0000_0000_c000_000000000046, 0x10u) )
  {
LABEL_85:
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v46,
        MsaaProviderCallout_Start,
        L"IServiceProvider::QueryService",
        (unsigned int)a4,
        ppv);
      v21 = v75;
    }
    (*(void (__fastcall **)(struct ProviderEntryPoint *, GUID *, GUID *, struct IAccessibleEx **))(*(_QWORD *)v21 + 24LL))(
      v21,
      &GUID_f8b80ada_2c44_48d0_89be_5ff23c9cd875,
      &GUID_f8b80ada_2c44_48d0_89be_5ff23c9cd875,
      &v73);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v48,
        MsaaProviderCallout_Stop,
        L"IServiceProvider::QueryService",
        (unsigned int)a4,
        ppv);
    v21 = v75;
LABEL_27:
    if ( v21 )
    {
      v22 = *(_QWORD *)v21;
      v23 = v21;
LABEL_29:
      (*(void (__fastcall **)(struct ProviderEntryPoint *))(v22 + 16))(v23);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  v65 = 0;
  v68[0] = L"IServiceProvider::QueryService";
  v68[1] = v21;
  v68[2] = a4;
  v71 = 1;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    McTemplateU0zd_EventWriteTransfer(
      0,
      MsaaProviderCallout_Start,
      L"IServiceProvider::QueryService",
      (unsigned int)a4,
      ppv);
    v21 = v75;
  }
  v47 = *(void (__fastcall **)(struct ProviderEntryPoint *, GUID *, GUID *, struct IAccessibleEx **))(*(_QWORD *)v21 + 24LL);
  v65 = 0;
  v47(v21, &GUID_acd46652_829d_41cb_a5fc_17acf43661ac, &GUID_00000000_0000_0000_c000_000000000046, &v65);
  v46 = v65;
  if ( !v65 )
  {
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        0,
        MsaaProviderCallout_Stop,
        L"IServiceProvider::QueryService",
        (unsigned int)a4,
        ppv);
      v46 = v65;
    }
    if ( v46 )
      ((void (__fastcall *)(struct IAccessibleEx *))v46->lpVtbl->Release)(v46);
    v21 = v75;
    goto LABEL_85;
  }
  v69 = -2147467259;
  v70 = 610;
  MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)v68);
  if ( v65 )
    ((void (__fastcall *)(struct IAccessibleEx *))v65->lpVtbl->Release)(v65);
  v23 = v75;
  if ( v75 )
  {
    v22 = *(_QWORD *)v75;
    goto LABEL_29;
  }
LABEL_30:
  v24 = v73;
  if ( v73 && a3 )
  {
    v65 = 0;
    ObjectForChild = ProviderCallouts::GetObjectForChild(v73, a3, &v65);
    ((void (__fastcall *)(struct IAccessibleEx *))v73->lpVtbl->Release)(v73);
    v24 = 0;
    v73 = 0;
    if ( ObjectForChild >= 0 )
    {
      if ( v65 )
      {
        v24 = v65;
        v73 = v65;
      }
    }
    else
    {
      v62 = 0;
      v75 = 0;
      if ( a4 )
      {
        v75 = 0;
        ProviderEntryPoint::CreateUsingHwnd(a4, &v75);
        v62 = v75;
      }
      Error::GeneralProviderError(a2, L"IAccessibleEx::GetObjectForChild", ObjectForChild, v62, 600, 1);
      if ( v62 )
        (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v62 + 16LL))(v62);
      v24 = v73;
    }
  }
  v25 = 0;
  v65 = 0;
  if ( v24 )
  {
    v75 = 0;
    if ( ((unsigned __int64 (__fastcall *)(struct IAccessibleEx *, GUID *, struct ProviderEntryPoint **))v24->lpVtbl->QueryInterface)(
           v24,
           &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
           &v75) )
    {
      v25 = 0;
      v65 = 0;
    }
    else
    {
      v25 = (struct IUnknown *)v75;
      v65 = (struct IAccessibleEx *)v75;
      if ( v75 )
      {
LABEL_163:
        v24 = v73;
        goto LABEL_32;
      }
    }
    v63 = 0;
    v75 = 0;
    if ( a4 )
    {
      v75 = 0;
      ProviderEntryPoint::CreateUsingHwnd(a4, &v75);
      v63 = v75;
    }
    Error::GeneralProviderError(a2, L"IAccessibleEx::QueryInterface", -2147467262, v63, 608, 1);
    if ( v63 )
      (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v63 + 16LL))(v63);
    goto LABEL_163;
  }
LABEL_32:
  v66 = v24;
  v73 = 0;
  v67 = v25;
  v26 = *(_QWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 352) = 0;
  *(_DWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 344) = 0;
  v27 = a5;
  if ( !v24 )
    goto LABEL_33;
  pAptType = APTTYPE_MTA;
  if ( a5 == APTTYPE_STA )
  {
LABEL_126:
    if ( v26 )
    {
      v51 = (*(__int64 (__fastcall **)(__int64, struct IAccessibleEx *, GUID *, __int64))(*(_QWORD *)v26 + 24LL))(
              v26,
              v24,
              &GUID_f8b80ada_2c44_48d0_89be_5ff23c9cd875,
              a1 + 368);
LABEL_113:
      if ( v51 >= 0 )
        goto LABEL_33;
    }
LABEL_114:
    *(_DWORD *)(a1 + 344) = 1;
    goto LABEL_33;
  }
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( BasicUiaUtils::s_isDesktop )
  {
    a5 = APTTYPE_STA;
    v49 = CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&a5);
    if ( v49 == -2147221008 )
    {
      pAptType = APTTYPE_NA;
      goto LABEL_191;
    }
    if ( v49 < 0 )
      goto LABEL_114;
  }
  switch ( pAptType )
  {
    case APTTYPE_NA:
LABEL_191:
      *(_QWORD *)(a1 + 352) = v24;
      ((void (__fastcall *)(struct IAccessibleEx *))v24->lpVtbl->AddRef)(v24);
      break;
    case APTTYPE_STA:
    case APTTYPE_MAINSTA:
      v50 = (struct IAccessibleEx *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      v73 = v50;
      if ( v50 )
      {
        v50[2].lpVtbl = 0;
        v50[3].lpVtbl = 0;
        v50->lpVtbl = (struct IAccessibleExVtbl *)&RefcountBase::`vftable';
        LODWORD(v50[1].lpVtbl) = 1;
        _InterlockedIncrement(&dword_18039DE7C);
        v50->lpVtbl = (struct IAccessibleExVtbl *)&CApartmentTracker::`vftable'{for `RefcountBase'};
        v50[4].lpVtbl = 0;
        LODWORD(v50[5].lpVtbl) = 0;
        *(_QWORD *)(a1 + 360) = v50;
        v51 = STATrackedObject::SetObject((STATrackedObject *)v50, (struct IUnknown *)v24);
        goto LABEL_113;
      }
      *(_QWORD *)(a1 + 360) = 0;
      *(_DWORD *)(a1 + 344) = 1;
      break;
    case APTTYPE_MTA:
      goto LABEL_126;
  }
LABEL_33:
  v28 = *(_QWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 384) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  *(_DWORD *)(a1 + 376) = 0;
  if ( !v25 )
    goto LABEL_34;
  a5 = APTTYPE_MTA;
  if ( v27 == APTTYPE_STA )
  {
LABEL_140:
    if ( v28 )
    {
      v54 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, GUID *, __int64))(*(_QWORD *)v28 + 24LL))(
              v28,
              v25,
              &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
              a1 + 400);
LABEL_124:
      if ( v54 >= 0 )
        goto LABEL_34;
    }
LABEL_125:
    *(_DWORD *)(a1 + 376) = 1;
    goto LABEL_34;
  }
  if ( BasicUiaUtils::IsDesktop() )
  {
    pAptType = APTTYPE_STA;
    v52 = CoGetApartmentType(&a5, (APTTYPEQUALIFIER *)&pAptType);
    if ( v52 == -2147221008 )
    {
      a5 = APTTYPE_NA;
      goto LABEL_193;
    }
    if ( v52 < 0 )
      goto LABEL_125;
  }
  if ( a5 == APTTYPE_NA )
  {
LABEL_193:
    *(_QWORD *)(a1 + 384) = v25;
    ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->AddRef)(v25);
    goto LABEL_34;
  }
  if ( a5 && a5 != APTTYPE_MAINSTA )
  {
    if ( a5 != APTTYPE_MTA )
      goto LABEL_34;
    goto LABEL_140;
  }
  v53 = (struct IAccessibleEx *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v73 = v53;
  if ( v53 )
  {
    v53[2].lpVtbl = 0;
    v53[3].lpVtbl = 0;
    v53->lpVtbl = (struct IAccessibleExVtbl *)&RefcountBase::`vftable';
    LODWORD(v53[1].lpVtbl) = 1;
    _InterlockedIncrement(&dword_18039DE7C);
    v53->lpVtbl = (struct IAccessibleExVtbl *)&CApartmentTracker::`vftable'{for `RefcountBase'};
    v53[4].lpVtbl = 0;
    LODWORD(v53[5].lpVtbl) = 0;
    *(_QWORD *)(a1 + 392) = v53;
    v54 = STATrackedObject::SetObject((STATrackedObject *)v53, v25);
    goto LABEL_124;
  }
  *(_QWORD *)(a1 + 392) = 0;
  *(_DWORD *)(a1 + 376) = 1;
LABEL_34:
  v73 = 0;
  v65 = 0;
  ((void (__fastcall *)(struct IUnknown *, GUID *, struct IAccessibleEx **))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
    &v65);
  v29 = v65;
  if ( v65 )
  {
    GetObjectForChild = v65->lpVtbl->GetObjectForChild;
    v43 = v73;
    v73 = 0;
    if ( v43 )
      ((void (__fastcall *)(struct IAccessibleEx *))v43->lpVtbl->Release)(v43);
    ((void (__fastcall *)(struct IAccessibleEx *, GUID *, GUID *, struct IAccessibleEx **))GetObjectForChild)(
      v29,
      &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
      &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
      &v73);
    v29 = v65;
  }
  if ( !v73 )
  {
    v75 = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, struct ProviderEntryPoint **))a2->lpVtbl->QueryInterface)(
      a2,
      &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
      &v75);
    v30 = (struct IAccessibleEx *)v75;
    v31 = 0;
    v75 = 0;
    v32 = v73;
    v73 = v30;
    if ( v32 )
    {
      ((void (__fastcall *)(struct IAccessibleEx *))v32->lpVtbl->Release)(v32);
      v31 = v75;
    }
    if ( v31 )
      (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v31 + 16LL))(v31);
    v29 = v65;
  }
  if ( v29 )
    ((void (__fastcall *)(struct IAccessibleEx *))v29->lpVtbl->Release)(v29);
  v33 = v73;
  if ( !v73 )
    goto LABEL_69;
  v34 = *(_QWORD *)(a1 + 248);
  *(_QWORD *)(a1 + 296) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_DWORD *)(a1 + 288) = 0;
  a5 = APTTYPE_MTA;
  if ( v27 )
  {
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( BasicUiaUtils::s_isDesktop )
    {
      pAptType = APTTYPE_STA;
      v35 = CoGetApartmentType(&a5, (APTTYPEQUALIFIER *)&pAptType);
      if ( v35 == -2147221008 )
      {
        a5 = APTTYPE_NA;
        goto LABEL_195;
      }
      if ( v35 < 0 )
      {
LABEL_130:
        *(_DWORD *)(a1 + 288) = 1;
        goto LABEL_69;
      }
    }
    if ( a5 != APTTYPE_NA )
    {
      if ( a5 && a5 != APTTYPE_MAINSTA )
      {
        if ( a5 != APTTYPE_MTA )
          goto LABEL_69;
        goto LABEL_137;
      }
      v36 = (struct ProviderEntryPoint *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      v37 = v36;
      v75 = v36;
      if ( !v36 )
      {
        *(_QWORD *)(a1 + 304) = 0;
        *(_DWORD *)(a1 + 288) = 1;
        goto LABEL_69;
      }
      *((_QWORD *)v36 + 2) = 0;
      *((_QWORD *)v36 + 3) = 0;
      *(_QWORD *)v36 = &RefcountBase::`vftable';
      *((_DWORD *)v36 + 2) = 1;
      _InterlockedIncrement(&dword_18039DE7C);
      *(_QWORD *)v36 = &CApartmentTracker::`vftable'{for `RefcountBase'};
      *((_QWORD *)v36 + 4) = 0;
      *((_DWORD *)v36 + 10) = 0;
      *(_QWORD *)(a1 + 304) = v36;
      v65 = 0;
      if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
      {
        `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
        v75 = 0;
        v55 = CoGetClassObject(&CLSID_CUIAutomation, 1u, 0, &GUID_00000001_0000_0000_c000_000000000046, (LPVOID *)&v75);
        `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
        if ( v55 < 0 )
        {
LABEL_129:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
            (const char *)(unsigned int)v55,
            (int)ppv);
          goto LABEL_130;
        }
        if ( v75 )
          (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v75 + 16LL))(v75);
        g_ComMitigationDone = 1;
      }
      v38 = 0;
      EnterCriticalSection(&CApartmentTracker::_classLock);
      v39 = GetCurrentThreadId();
      _mm_lfence();
      v40 = (char *)Block
          + 16
          * (qword_18039F790
           & (0x100000001B3LL
            * (HIBYTE(v39)
             ^ (0x100000001B3LL
              * (BYTE2(v39)
               ^ (0x100000001B3LL * ((0x100000001B3LL * ((unsigned __int8)v39 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v39))))))));
      v41 = v40[1];
      if ( v41 == qword_18039F768 )
      {
LABEL_90:
        v41 = 0;
      }
      else
      {
        while ( v39 != *(_DWORD *)(v41 + 16) )
        {
          if ( v41 == *v40 )
            goto LABEL_90;
          v41 = *(_QWORD *)(v41 + 8);
        }
      }
      if ( !v41 )
        v41 = qword_18039F768;
      if ( v41 != qword_18039F768 )
        v38 = *(volatile signed __int32 **)(v41 + 24);
      LeaveCriticalSection(&CApartmentTracker::_classLock);
      if ( v38 )
      {
        if ( *((_DWORD *)v38 + 6) )
        {
          _InterlockedIncrement(v38 + 2);
LABEL_64:
          v65 = (struct IAccessibleEx *)v38;
          _InterlockedIncrement((volatile signed __int32 *)v37 + 2);
          *((_QWORD *)v37 + 2) = *((_QWORD *)v38 + 5);
          v44 = *((_QWORD *)v38 + 5);
          if ( v44 )
            *(_QWORD *)(v44 + 24) = v37;
          *((_QWORD *)v38 + 5) = v37;
          *((_QWORD *)v37 + 4) = v33;
          ((void (__fastcall *)(struct IAccessibleEx *))v33->lpVtbl->AddRef)(v33);
          *((_DWORD *)v37 + 10) = GetCurrentThreadId();
          if ( v38 && _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(void *, __int64))v38)((void *)v38, 1);
          goto LABEL_69;
        }
        v55 = -2147467259;
      }
      else
      {
        v56 = (struct ProviderEntryPoint *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
        v38 = (volatile signed __int32 *)v56;
        v75 = v56;
        if ( v56 )
        {
          *(_QWORD *)v56 = &RefcountBase::`vftable';
          *((_DWORD *)v56 + 2) = 1;
          _InterlockedIncrement(&dword_18039DE7C);
          *(_QWORD *)v56 = &CApartmentTracker::`vftable'{for `RefcountBase'};
          *((_QWORD *)v56 + 2) = &CApartmentTracker::`vftable'{for `IInitializeSpy'};
          *((_DWORD *)v56 + 6) = 0;
          *((_QWORD *)v56 + 5) = 0;
          *((_QWORD *)v56 + 4) = 0;
          v75 = v56;
          v57 = CApartmentTracker::Initialize(v56);
          v55 = v57;
          if ( v57 >= 0 )
            goto LABEL_64;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
            (const char *)(unsigned int)v57,
            (int)ppv);
          AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&v75);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF8,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
            (const char *)0x8007000ELL,
            (int)ppv);
          v55 = -2147024882;
        }
      }
      goto LABEL_129;
    }
LABEL_195:
    *(_QWORD *)(a1 + 296) = v33;
    ((void (__fastcall *)(struct IAccessibleEx *))v33->lpVtbl->AddRef)(v33);
    goto LABEL_69;
  }
LABEL_137:
  if ( !v34
    || (*(int (__fastcall **)(__int64, struct IAccessibleEx *, GUID *, __int64))(*(_QWORD *)v34 + 24LL))(
         v34,
         v33,
         &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
         a1 + 312) < 0 )
  {
    goto LABEL_130;
  }
LABEL_69:
  if ( v73 )
    ((void (__fastcall *)(struct IAccessibleEx *))v73->lpVtbl->Release)(v73);
  if ( v25 )
    ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
  if ( v24 )
    ((void (__fastcall *)(struct IAccessibleEx *))v24->lpVtbl->Release)(v24);
  return a1;
}

```

## disassembly

```asm
0x18007f1d0  mov     [rsp-40h+arg_0], rcx
0x18007f1d5  push    rbp
0x18007f1d6  push    rbx
0x18007f1d7  push    rsi
0x18007f1d8  push    rdi
0x18007f1d9  push    r12
0x18007f1db  push    r13
0x18007f1dd  push    r14
0x18007f1df  push    r15
0x18007f1e1  mov     rbp, rsp
0x18007f1e4  sub     rsp, 78h
0x18007f1e8  mov     r13, r9
0x18007f1eb  mov     r12d, r8d
0x18007f1ee  mov     rsi, rdx
0x18007f1f1  mov     r14, rcx
0x18007f1f4  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x18007f1fb  mov     [rcx], rax
0x18007f1fe  mov     dword ptr [rcx+8], 1
0x18007f205  lock inc cs:dword_18039DE7C
0x18007f20c  lea     rax, ??_7MsaaProxy@@6BRefcountBase@@@; const MsaaProxy::`vftable'{for `RefcountBase'}
0x18007f213  mov     [rcx], rax
0x18007f216  lea     rax, ??_7MsaaNonClientProxyElement@@6BIRawElementProviderSimple2@@@; const MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderSimple2'}
0x18007f21d  mov     [rcx+10h], rax
0x18007f221  lea     rax, ??_7MsaaProxy@@6BIRawElementProviderFragment@@@; const MsaaProxy::`vftable'{for `IRawElementProviderFragment'}
0x18007f228  mov     [rcx+18h], rax
0x18007f22c  lea     rax, ??_7MsaaNonClientProxyElement@@6BIRawElementProviderFragmentRoot@@@; const MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderFragmentRoot'}
0x18007f233  mov     [rcx+20h], rax
0x18007f237  lea     rax, ??_7MsaaNonClientProxyElement@@6BIRawElementProviderTempIdString@@@; const MsaaNonClientProxyElement::`vftable'{for `IRawElementProviderTempIdString'}
0x18007f23e  mov     [rcx+28h], rax
0x18007f242  lea     rax, ??_7MsaaNonClientProxyElement@@6BIServiceProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `IServiceProvider'}
0x18007f249  mov     [rcx+30h], rax
0x18007f24d  lea     rax, ??_7MsaaProxy@@6BIProxyProviderWinEventHandler@@@; const MsaaProxy::`vftable'{for `IProxyProviderWinEventHandler'}
0x18007f254  mov     [rcx+38h], rax
0x18007f258  lea     rax, ??_7MsaaNonClientProxyElement@@6BIExpandCollapseProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `IExpandCollapseProvider'}
0x18007f25f  mov     [rcx+40h], rax
0x18007f263  lea     rax, ??_7MsaaProxy@@6BIInvokeProvider@@@; const MsaaProxy::`vftable'{for `IInvokeProvider'}
0x18007f26a  mov     [rcx+48h], rax
0x18007f26e  lea     rax, ??_7MsaaNonClientProxyElement@@6BIToggleProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `IToggleProvider'}
0x18007f275  mov     [rcx+50h], rax
0x18007f279  lea     rax, ??_7MsaaProxy@@6BISelectionProvider@@@; const MsaaProxy::`vftable'{for `ISelectionProvider'}
0x18007f280  mov     [rcx+58h], rax
0x18007f284  lea     rax, ??_7MsaaProxy@@6BISelectionItemProvider@@@; const MsaaProxy::`vftable'{for `ISelectionItemProvider'}
0x18007f28b  mov     [rcx+60h], rax
0x18007f28f  lea     rax, ??_7MsaaProxy@@6BIValueProvider@@@; const MsaaProxy::`vftable'{for `IValueProvider'}
0x18007f296  mov     [rcx+68h], rax
0x18007f29a  lea     rax, ??_7MsaaProxy@@6BIRangeValueProvider@@@; const MsaaProxy::`vftable'{for `IRangeValueProvider'}
0x18007f2a1  mov     [rcx+70h], rax
0x18007f2a5  lea     rax, ??_7MsaaProxy@@6BIGridProvider@@@; const MsaaProxy::`vftable'{for `IGridProvider'}
0x18007f2ac  mov     [rcx+78h], rax
0x18007f2b0  lea     rax, ??_7MsaaProxy@@6BIGridItemProvider@@@; const MsaaProxy::`vftable'{for `IGridItemProvider'}
0x18007f2b7  mov     [rcx+80h], rax
0x18007f2be  lea     rax, ??_7MsaaNonClientProxyElement@@6BITableProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `ITableProvider'}
0x18007f2c5  mov     [rcx+88h], rax
0x18007f2cc  lea     rax, ??_7MsaaNonClientProxyElement@@6BITableItemProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `ITableItemProvider'}
0x18007f2d3  mov     [rcx+90h], rax
0x18007f2da  lea     rax, ??_7MsaaProxy@@6BIScrollItemProvider@@@; const MsaaProxy::`vftable'{for `IScrollItemProvider'}
0x18007f2e1  mov     [rcx+98h], rax
0x18007f2e8  lea     rax, ??_7MsaaProxy@@6BILegacyIAccessibleProvider@@@; const MsaaProxy::`vftable'{for `ILegacyIAccessibleProvider'}
0x18007f2ef  mov     [rcx+0A0h], rax
0x18007f2f6  lea     rax, ??_7MsaaNonClientProxyElement@@6BITextProvider2@@@; const MsaaNonClientProxyElement::`vftable'{for `ITextProvider2'}
0x18007f2fd  mov     [rcx+0A8h], rax
0x18007f304  lea     rax, ??_7MsaaNonClientProxyElement@@6BITextEditProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `ITextEditProvider'}
0x18007f30b  mov     [rcx+0B0h], rax
0x18007f312  lea     rax, ??_7MsaaNonClientProxyElement@@6BITextChildProvider@@@; const MsaaNonClientProxyElement::`vftable'{for `ITextChildProvider'}
0x18007f319  mov     [rcx+0B8h], rax
0x18007f320  lea     rax, ??_7MsaaNonClientProxyElement@@6BIAccIdentity@@@; const MsaaNonClientProxyElement::`vftable'{for `IAccIdentity'}
0x18007f327  mov     [rcx+0C0h], rax
0x18007f32e  lea     rax, ??_7MsaaProxy@@6BIAccProxyVersion@@@; const MsaaProxy::`vftable'{for `IAccProxyVersion'}
0x18007f335  mov     [rcx+0C8h], rax
0x18007f33c  lea     rax, ??_7MsaaNonClientProxyElement@@6BIAccTimeout@@@; const MsaaNonClientProxyElement::`vftable'{for `IAccTimeout'}
0x18007f343  mov     [rcx+0D0h], rax
0x18007f34a  lea     rax, ??_7MsaaNonClientProxyElement@@6BIInternalMsaaProxy@@@; const MsaaNonClientProxyElement::`vftable'{for `IInternalMsaaProxy'}
0x18007f351  mov     [rcx+0D8h], rax
0x18007f358  lea     rax, ??_7MsaaProxy@@6BIBuiltInProxy@@@; const MsaaProxy::`vftable'{for `IBuiltInProxy'}
0x18007f35f  mov     [rcx+0E0h], rax
0x18007f366  mov     [rcx+0E8h], r9
0x18007f36d  mov     r15d, [rbp+arg_20]
0x18007f371  mov     [rcx+0F0h], r15d
0x18007f378  lea     rbx, [rcx+0F8h]
0x18007f37f  xor     ecx, ecx
0x18007f381  mov     [rbx], rcx
0x18007f384  mov     [r14+100h], ecx
0x18007f38b  mov     [r14+108h], rcx
0x18007f392  mov     [r14+110h], rcx
0x18007f399  mov     [r14+118h], ecx
0x18007f3a0  mov     [r14+120h], ecx
0x18007f3a7  mov     [r14+128h], rcx
0x18007f3ae  mov     [r14+130h], rcx
0x18007f3b5  mov     [r14+138h], ecx
0x18007f3bc  mov     [r14+158h], ecx
0x18007f3c3  mov     [r14+160h], rcx
0x18007f3ca  mov     [r14+168h], rcx
0x18007f3d1  mov     [r14+170h], ecx
0x18007f3d8  mov     [r14+178h], ecx
0x18007f3df  mov     [r14+180h], rcx
0x18007f3e6  mov     [r14+188h], rcx
0x18007f3ed  mov     [r14+190h], ecx
0x18007f3f4  mov     [r14+198h], ecx
0x18007f3fb  mov     eax, [rbp+pAptType]
0x18007f3fe  mov     [r14+19Ch], eax
0x18007f405  mov     dword ptr [r14+1A0h], 2
0x18007f410  mov     [r14+1A8h], ecx
0x18007f417  mov     [r14+1B0h], rcx
0x18007f41e  mov     [r14+1B8h], rcx
0x18007f425  mov     [r14+1C0h], ecx
0x18007f42c  mov     [r14+1C8h], ecx
0x18007f433  mov     [r14+1D0h], rcx
0x18007f43a  mov     [r14+1D8h], rcx
0x18007f441  mov     [r14+1E0h], ecx
0x18007f448  mov     [r14+1E8h], cl
0x18007f44f  mov     [r14+1ECh], rcx
0x18007f456  mov     [r14+1F8h], rcx
0x18007f45d  mov     [r14+200h], rcx
0x18007f464  mov     [r14+208h], ecx
0x18007f46b  mov     [r14+210h], ecx
0x18007f472  mov     [r14+218h], rcx
0x18007f479  mov     [r14+220h], rcx
0x18007f480  mov     [r14+228h], ecx
0x18007f487  mov     [r14+230h], ecx
0x18007f48e  mov     [rsp+78h+ppv], rbx; int
0x18007f493  lea     r9, IID_IGlobalInterfaceTable; riid
0x18007f49a  xor     edx, edx; pUnkOuter
0x18007f49c  mov     r8d, 1; dwClsContext
0x18007f4a2  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18007f4a9  call    cs:__imp_CoCreateInstance
0x18007f4af  mov     rbx, [rbx]
0x18007f4b2  xor     ecx, ecx
0x18007f4b4  mov     [r14+108h], rcx
0x18007f4bb  mov     [r14+118h], ecx
0x18007f4c2  mov     [r14+100h], ecx
0x18007f4c9  test    rsi, rsi
0x18007f4cc  jz      loc_18007F6CF
0x18007f4d2  mov     [rbp+pAptType], 1
0x18007f4d9  test    r15d, r15d
0x18007f4dc  jz      loc_18007FC51
0x18007f4e2  movzx   eax, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18007f4e9  nop
0x18007f4ea  test    al, al
0x18007f4ec  jz      loc_18008031A
0x18007f4f2  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isDesktop
0x18007f4f9  jz      short loc_18007F51B
0x18007f4fb  mov     [rbp+pAptQualifier], ecx
0x18007f4fe  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x18007f502  lea     rcx, [rbp+pAptType]; pAptType
0x18007f506  call    cs:__imp_CoGetApartmentType
0x18007f50c  cmp     eax, 800401F0h
0x18007f511  jz      loc_1800803D9
0x18007f517  test    eax, eax
0x18007f519  js      short loc_18007F58F
0x18007f51b  mov     eax, [rbp+pAptType]
0x18007f51e  cmp     eax, 2
0x18007f521  jz      loc_1800803E0
0x18007f527  test    eax, eax
0x18007f529  jnz     loc_18007FEB8
0x18007f52f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007f536  mov     ecx, 30h ; '0'; unsigned __int64
0x18007f53b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007f540  mov     rdi, rax
0x18007f543  mov     [rbp+arg_8], rax
0x18007f547  test    rax, rax
0x18007f54a  jz      loc_18008023C
0x18007f550  xor     ebx, ebx
0x18007f552  mov     [rax+10h], rbx
0x18007f556  mov     [rax+18h], rbx
0x18007f55a  lea     r15, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x18007f561  mov     [rax], r15
0x18007f564  mov     dword ptr [rax+8], 1
0x18007f56b  lock inc cs:dword_18039DE7C
0x18007f572  lea     rax, ??_7CApartmentTracker@@6BRefcountBase@@@; const CApartmentTracker::`vftable'{for `RefcountBase'}
0x18007f579  mov     [rdi], rax
0x18007f57c  mov     [rdi+20h], rbx
0x18007f580  mov     [rdi+28h], ebx
0x18007f583  mov     [r14+110h], rdi
0x18007f58a  test    rdi, rdi
0x18007f58d  jnz     short loc_18007F59F
0x18007f58f  mov     dword ptr [r14+100h], 1
0x18007f59a  jmp     loc_18007F6CF
0x18007f59f  mov     [rbp+arg_18], rbx
0x18007f5a3  cmp     cs:?g_ComMitigationDone@@3_NA, 0; bool g_ComMitigationDone
0x18007f5aa  jz      loc_1800803FB
0x18007f5b0  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007f5b7  call    cs:__imp_EnterCriticalSection
0x18007f5bd  call    cs:__imp_GetCurrentThreadId
0x18007f5c3  mov     r10d, eax
0x18007f5c6  mov     r9d, eax
0x18007f5c9  shr     r9d, 18h
0x18007f5cd  mov     ecx, eax
0x18007f5cf  shr     ecx, 10h
0x18007f5d2  movzx   r8d, cl
0x18007f5d6  mov     ecx, eax
0x18007f5d8  shr     ecx, 8
0x18007f5db  movzx   edx, cl
0x18007f5de  movzx   ecx, al
0x18007f5e1  lfence
0x18007f5e4  mov     rax, 0CBF29CE484222325h
0x18007f5ee  xor     rcx, rax
0x18007f5f1  mov     rax, 100000001B3h
0x18007f5fb  imul    rcx, rax
0x18007f5ff  xor     rdx, rcx
0x18007f602  imul    rdx, rax
0x18007f606  xor     rdx, r8
0x18007f609  imul    rdx, rax
0x18007f60d  xor     rdx, r9
0x18007f610  imul    rdx, rax
0x18007f614  and     rdx, cs:qword_18039F790
0x18007f61b  shl     rdx, 4
0x18007f61f  add     rdx, cs:Block
0x18007f626  mov     rax, [rdx+8]
0x18007f62a  mov     rcx, cs:qword_18039F768
0x18007f631  cmp     rax, rcx
0x18007f634  jz      loc_18007FC87
0x18007f63a  mov     r8, [rdx]
0x18007f63d  cmp     r10d, [rax+10h]
0x18007f641  jz      loc_18007FC89
0x18007f647  cmp     rax, r8
0x18007f64a  jz      loc_18007FC87
0x18007f650  mov     rax, [rax+8]
0x18007f654  jmp     short loc_18007F63D
0x18007f656  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007f65d  call    cs:__imp_LeaveCriticalSection
0x18007f663  test    rbx, rbx
0x18007f666  jz      loc_180080003
0x18007f66c  cmp     dword ptr [rbx+18h], 0
0x18007f670  jz      loc_18007FFD4
0x18007f676  lock inc dword ptr [rbx+8]
0x18007f67a  mov     [rbp+arg_18], rbx
0x18007f67e  lock inc dword ptr [rdi+8]
0x18007f682  mov     rax, [rbx+28h]
0x18007f686  mov     [rdi+10h], rax
0x18007f68a  mov     rax, [rbx+28h]
0x18007f68e  test    rax, rax
0x18007f691  jz      short loc_18007F697
0x18007f693  mov     [rax+18h], rdi
0x18007f697  mov     [rbx+28h], rdi
0x18007f69b  mov     [rdi+20h], rsi
0x18007f69f  mov     rax, [rsi]
0x18007f6a2  mov     rcx, rsi
0x18007f6a5  mov     rax, [rax+8]
0x18007f6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f6ae  call    cs:__imp_GetCurrentThreadId
0x18007f6b4  mov     [rdi+28h], eax
0x18007f6b7  test    rbx, rbx
0x18007f6ba  jz      short loc_18007F6CF
0x18007f6bc  mov     eax, 0FFFFFFFFh
0x18007f6c1  lock xadd [rbx+8], eax
0x18007f6c6  cmp     eax, 1
0x18007f6c9  jz      loc_18008048B
0x18007f6cf  mov     word ptr [r14+140h], 3
0x18007f6d9  mov     [r14+148h], r12d
0x18007f6e0  xor     edi, edi
0x18007f6e2  mov     [rbp+var_40], rdi
0x18007f6e6  mov     [rbp+var_38], rdi
0x18007f6ea  mov     [rbp+arg_8], rdi
0x18007f6ee  mov     [rbp+arg_18], rdi
0x18007f6f2  mov     rax, [rsi]
0x18007f6f5  lea     r8, [rbp+arg_18]
0x18007f6f9  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18007f700  mov     rcx, rsi
0x18007f703  mov     rax, [rax]
0x18007f706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f70b  nop
0x18007f70c  mov     rbx, [rbp+arg_18]
0x18007f710  test    rbx, rbx
0x18007f713  jnz     loc_18007FB27
0x18007f719  test    rbx, rbx
0x18007f71c  jz      short loc_18007F72E
0x18007f71e  mov     rax, [rbx]
0x18007f721  mov     rcx, rbx
0x18007f724  mov     rax, [rax+10h]
0x18007f728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f72d  nop
0x18007f72e  mov     rdi, [rbp+arg_8]
0x18007f732  test    rdi, rdi
0x18007f735  jnz     loc_1800800BF
0x18007f73b  xor     r15d, r15d
0x18007f73e  mov     r12d, r15d
0x18007f741  mov     [rbp+var_48], r15
0x18007f745  test    rdi, rdi
0x18007f748  jnz     loc_180080164
0x18007f74e  mov     [rbp+var_40], rdi
0x18007f752  mov     [rbp+arg_8], r15
0x18007f756  mov     [rbp+var_38], r12
0x18007f75a  mov     rbx, [r14+0F8h]
0x18007f761  mov     [r14+160h], r15
0x18007f768  mov     [r14+170h], r15d
0x18007f76f  mov     [r14+158h], r15d
0x18007f776  mov     r13d, [rbp+arg_20]
0x18007f77a  test    rdi, rdi
0x18007f77d  jnz     loc_18007FCA4
0x18007f783  mov     rbx, [r14+0F8h]
0x18007f78a  mov     [r14+180h], r15
0x18007f791  mov     [r14+190h], r15d
0x18007f798  mov     [r14+178h], r15d
0x18007f79f  test    r12, r12
0x18007f7a2  jnz     loc_18007FD85
0x18007f7a8  mov     [rbp+arg_8], r15
0x18007f7ac  mov     [rbp+var_48], r15
0x18007f7b0  mov     rax, [rsi]
0x18007f7b3  lea     r8, [rbp+var_48]
0x18007f7b7  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
  ... truncated ...
```
