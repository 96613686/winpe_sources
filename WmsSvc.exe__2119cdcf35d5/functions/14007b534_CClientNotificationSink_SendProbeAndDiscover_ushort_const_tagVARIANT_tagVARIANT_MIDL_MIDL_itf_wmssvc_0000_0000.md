# CClientNotificationSink::SendProbeAndDiscover(ushort const *,tagVARIANT *,tagVARIANT *,__MIDL___MIDL_itf_wmssvc_0000_0000_0030)

- ea: `0x14007b534`
- end: `0x14007be1f`
- name: `?SendProbeAndDiscover@CClientNotificationSink@@AEAAJPEBGPEAUtagVARIANT@@1W4__MIDL___MIDL_itf_wmssvc_0000_0000_0030@@@Z`
- size: `2283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14007a93c`
- `0x14007a9b0`

## callees

- `0x140015e1c`
- `0x140016268`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007a724`
- `0x14007b398`
- `0x14007b534`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x14007b687`
- `KERNEL32!ResetEvent` at `0x14007b691`
- `KERNEL32!ResetEvent` at `0x14007b687`
- `KERNEL32!ResetEvent` at `0x14007b691`
- `KERNEL32!WaitForMultipleObjects` at `0x14007b6c7`
- `KERNEL32!WaitForMultipleObjects` at `0x14007b6c7`
- `KERNEL32!GetLastError` at `0x14007b6e9`
- `KERNEL32!GetLastError` at `0x14007b7af`
- `KERNEL32!GetLastError` at `0x14007b6e9`
- `KERNEL32!GetLastError` at `0x14007b7af`
- `KERNEL32!IsDebuggerPresent` at `0x14007b610`
- `KERNEL32!IsDebuggerPresent` at `0x14007b744`
- `KERNEL32!IsDebuggerPresent` at `0x14007b80a`
- `KERNEL32!IsDebuggerPresent` at `0x14007b887`
- `KERNEL32!IsDebuggerPresent` at `0x14007b977`
- `KERNEL32!IsDebuggerPresent` at `0x14007ba18`
- `KERNEL32!IsDebuggerPresent` at `0x14007baf4`
- `KERNEL32!IsDebuggerPresent` at `0x14007bcd2`
- `KERNEL32!IsDebuggerPresent` at `0x14007bd85`
- `KERNEL32!IsDebuggerPresent` at `0x14007bdf6`
- `KERNEL32!IsDebuggerPresent` at `0x14007b610`
- `KERNEL32!IsDebuggerPresent` at `0x14007b744`
- `KERNEL32!IsDebuggerPresent` at `0x14007b80a`
- `KERNEL32!IsDebuggerPresent` at `0x14007b887`
- `KERNEL32!IsDebuggerPresent` at `0x14007b977`
- `KERNEL32!IsDebuggerPresent` at `0x14007ba18`
- `KERNEL32!IsDebuggerPresent` at `0x14007baf4`
- `KERNEL32!IsDebuggerPresent` at `0x14007bcd2`
- `KERNEL32!IsDebuggerPresent` at `0x14007bd85`
- `KERNEL32!IsDebuggerPresent` at `0x14007bdf6`
- `ole32!CoCreateInstance` at `0x14007b5c4`
- `ole32!CoCreateInstance` at `0x14007b5c4`
- `OLEAUT32!__imp_SysAllocString` at `0x14007ba86`
- `OLEAUT32!__imp_SysAllocString` at `0x14007baa0`
- `OLEAUT32!__imp_SysAllocString` at `0x14007bb35`
- `OLEAUT32!__imp_SysAllocString` at `0x14007bb4c`
- `OLEAUT32!__imp_SysAllocString` at `0x14007ba86`
- `OLEAUT32!__imp_SysAllocString` at `0x14007baa0`
- `OLEAUT32!__imp_SysAllocString` at `0x14007bb35`
- `OLEAUT32!__imp_SysAllocString` at `0x14007bb4c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bb98`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bba9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bbf9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bc02`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bc3c`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bb98`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bba9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bbf9`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bc02`
- `OLEAUT32!__imp_SysFreeString` at `0x14007bc3c`
- `OLEAUT32!__imp_VariantInit` at `0x14007b8f7`
- `OLEAUT32!__imp_VariantInit` at `0x14007b8f7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14007bc56`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14007bc56`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14007bc29`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14007bc29`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14007bb6a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14007bb84`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14007bb6a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14007bb84`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14007b922`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14007b9c4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14007b922`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14007b9c4`
- `SHLWAPI!StrCmpW` at `0x14007ba71`
- `SHLWAPI!StrCmpW` at `0x14007ba71`

## string_xrefs

- `0x14007b601`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b735`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b7fb`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b878`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b968`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007ba09`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007bae5`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007bcc3`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007bd76`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007bde7`: `termsrv\wms\src\middletier\discovery\common\clientnotificationsink.cpp`
- `0x14007b59e`: `CClientNotificationSink::SendProbeAndDiscover - CoCreating CLSID_NotificationManager.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClientNotificationSink::SendProbeAndDiscover(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5)
{
  VARIANTARG *v5; // rsi
  int v8; // ebx
  BSTR v9; // r12
  HRESULT Instance; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  const unsigned __int16 *v13; // r9
  CClientNotificationSink *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  const unsigned __int16 *v17; // r9
  DWORD v18; // eax
  __int64 v19; // r8
  const unsigned __int16 *v20; // r9
  signed int LastError; // eax
  unsigned int v22; // r15d
  bool v23; // zf
  const unsigned __int16 *v24; // rax
  signed int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rdx
  const unsigned __int16 *v28; // r9
  __int64 v29; // r8
  SAFEARRAY *Vector; // r14
  __int64 *i; // rsi
  __int64 v32; // r9
  _WORD *v33; // rax
  SAFEARRAY *v34; // rdi
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  const unsigned __int16 *v39; // r9
  __int64 v40; // r8
  const unsigned __int16 *v41; // [rsp+28h] [rbp-48h]
  const unsigned __int16 *v42; // [rsp+30h] [rbp-40h]
  int v43; // [rsp+38h] [rbp-38h]
  struct _RTL_CRITICAL_SECTION **v44; // [rsp+40h] [rbp-30h] BYREF
  void *pv; // [rsp+48h] [rbp-28h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-20h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+B0h] [rbp+40h] BYREF
  _WORD *v49; // [rsp+C0h] [rbp+50h]
  VARIANTARG *v50; // [rsp+C8h] [rbp+58h]

  v50 = (VARIANTARG *)a4;
  v49 = (_WORD *)a3;
  v5 = (VARIANTARG *)a4;
  v8 = 0;
  psa = 0;
  rgIndices = 0;
  pv = 0;
  v9 = 0;
  Handles[0] = *(HANDLE *)(a1 + 32);
  Handles[1] = *(HANDLE *)(a1 + 40);
  CAutoCriticalSection::CAutoCriticalSection((CAutoCriticalSection *)&v44, (struct CCriticalSection *)(a1 + 72), a3, a4);
  if ( !*(_QWORD *)(a1 + 184) )
  {
    DEBUGMSG(L"CClientNotificationSink::SendProbeAndDiscover - CoCreating CLSID_NotificationManager.\n");
    Instance = CoCreateInstance(
                 &CLSID_EventNotificationService,
                 0,
                 4u,
                 &GUID_47e90c71_b91c_410f_ac04_2e3517ea702a,
                 (LPVOID *)(a1 + 184));
    v8 = Instance;
    if ( Instance < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        0x31Bu,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CHRA",
        L"hr",
        Instance);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
          795,
          L"CClientNotificationSink::SendProbeAndDiscover",
          L"CHRA",
          L"hr",
          v8);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
          795,
          L"CClientNotificationSink::SendProbeAndDiscover",
          L"CHRA",
          L"hr",
          v8);
      goto LABEL_31;
    }
    DEBUGMSG(L"CClientNotificationSink::SendProbeAndDiscover - m_pEventSink initialized.\n");
  }
  CClientNotificationSink::CleanupDiscoveredServerList((CClientNotificationSink *)a1);
  ResetEvent(*(HANDLE *)(a1 + 32));
  ResetEvent(*(HANDLE *)(a1 + 40));
  *(_QWORD *)(a1 + 56) = a2;
  *(_DWORD *)(a1 + 64) = a5;
  CClientNotificationSink::SendProbe(v14, a2);
  CAutoCriticalSection::~CAutoCriticalSection(&v44, v15, v16, v17);
  v18 = WaitForMultipleObjects(2u, Handles, 0, 0x7530u);
  if ( v18 )
  {
    switch ( v18 )
    {
      case 1u:
        v8 = -2147023659;
        goto LABEL_57;
      case 0x102u:
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v22 = 830;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
          0x33Eu,
          L"CClientNotificationSink::SendProbeAndDiscover",
          L"CBRAEx",
          L"fStatus != 258L",
          v8);
        v23 = !IsDebuggerPresent();
        v24 = L"fStatus != 258L";
LABEL_15:
        if ( v23 )
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
            v22,
            L"CClientNotificationSink::SendProbeAndDiscover",
            L"CBRAEx",
            v24,
            v8);
        else
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
            v22,
            L"CClientNotificationSink::SendProbeAndDiscover",
            L"CBRAEx",
            v24,
            v8);
        goto LABEL_56;
      case 0xFFFFFFFF:
        v25 = GetLastError();
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v22 = 831;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
          0x33Fu,
          L"CClientNotificationSink::SendProbeAndDiscover",
          L"CBRAEx",
          L"fStatus != ((DWORD)0xFFFFFFFF)",
          v8);
        v23 = !IsDebuggerPresent();
        v24 = L"fStatus != ((DWORD)0xFFFFFFFF)";
        goto LABEL_15;
    }
  }
  *(_DWORD *)(a1 + 64) = -1;
  CAutoCriticalSection::CAutoCriticalSection(
    (CAutoCriticalSection *)&v44,
    (struct CCriticalSection *)(a1 + 72),
    v19,
    v20);
  if ( !v5 )
  {
    v8 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      0x34Au,
      L"CClientNotificationSink::SendProbeAndDiscover",
      L"CBRAEx",
      L"pServerList",
      -2147467261);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        842,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CBRAEx",
        L"pServerList",
        -2147467261);
      goto LABEL_31;
    }
    v43 = -2147467261;
    v42 = L"pServerList";
    v41 = L"CBRAEx";
    v26 = 842;
LABEL_28:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      v26,
      L"CClientNotificationSink::SendProbeAndDiscover",
      v41,
      v42,
      v43);
    goto LABEL_31;
  }
  VariantInit(v5);
  DEBUGMSG(
    L"CClientNotificationSink::SendProbeAndDiscover: Query peer WMS server list: Server list count is %d.\n",
    *(unsigned int *)(a1 + 8));
  v29 = *(unsigned int *)(a1 + 8);
  if ( !(_DWORD)v29 )
  {
    Vector = 0;
LABEL_55:
    v5->vt = 8200;
    v5->llVal = (LONGLONG)psa;
    psa = 0;
    v33 = v49;
    *v49 = 8200;
    *((_QWORD *)v33 + 1) = Vector;
    CAutoCriticalSection::~CAutoCriticalSection(&v44, v27, v29, v28);
    v9 = 0;
LABEL_56:
    if ( v8 < 0 )
      goto LABEL_57;
    return (unsigned int)v8;
  }
  psa = SafeArrayCreateVector(8u, 0, v29);
  if ( !psa )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      0x353u,
      L"CClientNotificationSink::SendProbeAndDiscover",
      L"CPR",
      L"pServerListSafeArray",
      -2147024882);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        851,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"pServerListSafeArray",
        -2147024882);
      goto LABEL_31;
    }
    v43 = -2147024882;
    v42 = L"pServerListSafeArray";
    v41 = L"CPR";
    v26 = 851;
    goto LABEL_28;
  }
  Vector = SafeArrayCreateVector(8u, 0, *(_DWORD *)(a1 + 8));
  if ( !Vector )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      0x356u,
      L"CClientNotificationSink::SendProbeAndDiscover",
      L"CPR",
      L"pIpAddressListSafeArray",
      -2147024882);
    if ( !IsDebuggerPresent() )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        854,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"pIpAddressListSafeArray",
        -2147024882);
      goto LABEL_31;
    }
    v43 = -2147024882;
    v42 = L"pIpAddressListSafeArray";
    v41 = L"CPR";
    v26 = 854;
    goto LABEL_28;
  }
  for ( i = *(__int64 **)(a1 + 16); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(a1 + 16) )
    {
      v5 = v50;
      goto LABEL_55;
    }
    if ( StrCmpW((PCWSTR)i[2], *(PCWSTR *)(a1 + 48)) )
      break;
    pv = SysAllocString(&psz);
    if ( !pv )
    {
      v8 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        0x360u,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"bstrServerName",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        v36 = 864;
        goto LABEL_68;
      }
      v40 = 864;
LABEL_70:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        v40,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"bstrServerName",
        -2147024882);
      goto LABEL_71;
    }
    v9 = SysAllocString(&psz);
    if ( !v9 )
    {
      v8 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        0x363u,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"bstrIpAddress",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        v32 = 867;
LABEL_47:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
          v32,
          L"CClientNotificationSink::SendProbeAndDiscover",
          L"CPR",
          L"bstrIpAddress",
          -2147024882);
        goto LABEL_31;
      }
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
        867,
        L"CClientNotificationSink::SendProbeAndDiscover",
        L"CPR",
        L"bstrIpAddress",
        -2147024882);
      goto LABEL_31;
    }
LABEL_50:
    v8 = SafeArrayPutElement(psa, &rgIndices, pv);
    if ( v8 < 0 )
      goto LABEL_31;
    v8 = SafeArrayPutElement(Vector, &rgIndices, v9);
    if ( v8 < 0 )
      goto LABEL_31;
    SysFreeString((BSTR)pv);
    pv = 0;
    SysFreeString(v9);
    ++rgIndices;
  }
  DEBUGMSG(L"CClientNotificationSink::SendProbeAndDiscover: Add server (%s) to the return list.\n", i[2]);
  pv = SysAllocString((const OLECHAR *)i[2]);
  if ( !pv )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      0x36Au,
      L"CClientNotificationSink::SendProbeAndDiscover",
      L"CPR",
      L"bstrServerName",
      -2147024882);
    if ( !IsDebuggerPresent() )
    {
      v40 = 874;
      goto LABEL_70;
    }
    v36 = 874;
LABEL_68:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
      v36,
      L"CClientNotificationSink::SendProbeAndDiscover",
      L"CPR",
      L"bstrServerName",
      -2147024882);
LABEL_71:
    CAutoCriticalSection::~CAutoCriticalSection(&v44, v37, v38, v39);
    v9 = 0;
    goto LABEL_57;
  }
  v9 = SysAllocString((const OLECHAR *)i[3]);
  if ( v9 )
    goto LABEL_50;
  v8 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
    0x36Du,
    L"CClientNotificationSink::SendProbeAndDiscover",
    L"CPR",
    L"bstrIpAddress",
    -2147024882);
  if ( IsDebuggerPresent() )
  {
    v32 = 877;
    goto LABEL_47;
  }
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\middletier\\discovery\\common\\clientnotificationsink.cpp",
    877,
    L"CClientNotificationSink::SendProbeAndDiscover",
    L"CPR",
    L"bstrIpAddress",
    -2147024882);
LABEL_31:
  CAutoCriticalSection::~CAutoCriticalSection(&v44, v11, v12, v13);
LABEL_57:
  SysFreeString((BSTR)pv);
  SysFreeString(v9);
  v34 = psa;
  if ( psa )
  {
    LODWORD(v44) = 0;
    if ( rgIndices > 0 )
    {
      do
      {
        if ( SafeArrayGetElement(v34, (LONG *)&v44, &pv) >= 0 && pv )
        {
          SysFreeString((BSTR)pv);
          pv = 0;
        }
        LODWORD(v44) = (_DWORD)v44 + 1;
      }
      while ( (int)v44 < rgIndices );
    }
    SafeArrayDestroy(v34);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14007b534  mov     [rsp-38h+arg_8], rbx
0x14007b539  mov     [rsp-38h+arg_18], r9
0x14007b53e  mov     [rsp-38h+arg_10], r8
0x14007b543  push    rbp
0x14007b544  push    rsi
0x14007b545  push    rdi
0x14007b546  push    r12
0x14007b548  push    r13
0x14007b54a  push    r14
0x14007b54c  push    r15
0x14007b54e  mov     rbp, rsp
0x14007b551  sub     rsp, 70h
0x14007b555  mov     rsi, r9
0x14007b558  mov     r13, rdx
0x14007b55b  mov     rdi, rcx
0x14007b55e  xor     eax, eax
0x14007b560  mov     ebx, eax
0x14007b562  mov     [rbp+psa], rax
0x14007b566  mov     [rbp+rgIndices], eax
0x14007b569  mov     [rbp+pv], rax
0x14007b56d  mov     r12d, eax
0x14007b570  mov     rax, [rcx+20h]
0x14007b574  mov     [rbp+Handles], rax
0x14007b578  mov     rax, [rcx+28h]
0x14007b57c  mov     [rbp+var_10], rax
0x14007b580  lea     rdx, [rcx+48h]; struct CCriticalSection *
0x14007b584  lea     rcx, [rbp+var_30]; this
0x14007b588  call    ??0CAutoCriticalSection@@QEAA@PEAVCCriticalSection@@@Z; CAutoCriticalSection::CAutoCriticalSection(CCriticalSection *)
0x14007b58d  nop
0x14007b58e  lea     r14, [rdi+0B8h]
0x14007b595  cmp     [r14], r12
0x14007b598  jnz     loc_14007B67B
0x14007b59e  lea     rcx, aCclientnotific_2; "CClientNotificationSink::SendProbeAndDi"...
0x14007b5a5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14007b5aa  mov     [rsp+70h+ppv], r14; ppv
0x14007b5af  lea     r9, _GUID_47e90c71_b91c_410f_ac04_2e3517ea702a; riid
0x14007b5b6  xor     edx, edx; pUnkOuter
0x14007b5b8  lea     r8d, [r12+4]; dwClsContext
0x14007b5bd  lea     rcx, CLSID_EventNotificationService; rclsid
0x14007b5c4  call    cs:__imp_CoCreateInstance
0x14007b5ca  mov     ebx, eax
0x14007b5cc  test    eax, eax
0x14007b5ce  jns     loc_14007B66F
0x14007b5d4  mov     [rsp+70h+var_48], eax; int
0x14007b5d8  lea     r15, aHr; "hr"
0x14007b5df  mov     [rsp+70h+ppv], r15; unsigned __int16 *
0x14007b5e4  lea     r13, aChra; "CHRA"
0x14007b5eb  mov     r9, r13; unsigned __int16 *
0x14007b5ee  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007b5f5  mov     r8, rsi; unsigned __int16 *
0x14007b5f8  mov     r14d, 31Bh
0x14007b5fe  mov     edx, r14d; unsigned int
0x14007b601  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b608  mov     rcx, rdi; unsigned __int16 *
0x14007b60b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b610  call    cs:__imp_IsDebuggerPresent
0x14007b616  test    eax, eax
0x14007b618  jz      short loc_14007B646
0x14007b61a  mov     [rsp+70h+var_38], ebx
0x14007b61e  mov     [rsp+70h+var_40], r15
0x14007b623  mov     qword ptr [rsp+70h+var_48], r13
0x14007b628  mov     [rsp+70h+ppv], rsi
0x14007b62d  mov     r9d, r14d
0x14007b630  mov     r8, rdi
0x14007b633  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007b63a  lea     ecx, [r12+2]; unsigned __int8
0x14007b63f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007b644  jmp     short loc_14007B66A
0x14007b646  mov     dword ptr [rsp+70h+var_40], ebx
0x14007b64a  mov     qword ptr [rsp+70h+var_48], r15
0x14007b64f  mov     [rsp+70h+ppv], r13
0x14007b654  mov     r9, rsi
0x14007b657  mov     r8d, r14d
0x14007b65a  mov     rdx, rdi
0x14007b65d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007b664  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007b669  nop
0x14007b66a  jmp     loc_14007B8E6
0x14007b66f  lea     rcx, aCclientnotific_4; "CClientNotificationSink::SendProbeAndDi"...
0x14007b676  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14007b67b  mov     rcx, rdi; this
0x14007b67e  call    ?CleanupDiscoveredServerList@CClientNotificationSink@@AEAAJXZ; CClientNotificationSink::CleanupDiscoveredServerList(void)
0x14007b683  mov     rcx, [rdi+20h]; hEvent
0x14007b687  call    cs:__imp_ResetEvent
0x14007b68d  mov     rcx, [rdi+28h]; hEvent
0x14007b691  call    cs:__imp_ResetEvent
0x14007b697  mov     [rdi+38h], r13
0x14007b69b  mov     eax, [rbp+arg_20]
0x14007b69e  mov     [rdi+40h], eax
0x14007b6a1  mov     rdx, r13; unsigned __int16 *
0x14007b6a4  call    ?SendProbe@CClientNotificationSink@@AEAAJPEBG@Z; CClientNotificationSink::SendProbe(ushort const *)
0x14007b6a9  nop
0x14007b6aa  lea     rcx, [rbp+var_30]; this
0x14007b6ae  call    ??1CAutoCriticalSection@@QEAA@XZ; CAutoCriticalSection::~CAutoCriticalSection(void)
0x14007b6b3  mov     r9d, 7530h; dwMilliseconds
0x14007b6b9  xor     r8d, r8d; bWaitAll
0x14007b6bc  lea     rdx, [rbp+Handles]; lpHandles
0x14007b6c0  lea     r13d, [r8+2]
0x14007b6c4  mov     ecx, r13d; nCount
0x14007b6c7  call    cs:__imp_WaitForMultipleObjects
0x14007b6cd  test    eax, eax
0x14007b6cf  jz      loc_14007B828
0x14007b6d5  cmp     eax, 1
0x14007b6d8  jz      loc_14007B81E
0x14007b6de  cmp     eax, 102h
0x14007b6e3  jnz     loc_14007B7AA
0x14007b6e9  call    cs:__imp_GetLastError
0x14007b6ef  mov     ebx, eax
0x14007b6f1  test    eax, eax
0x14007b6f3  jle     short loc_14007B6FE
0x14007b6f5  movzx   ebx, ax
0x14007b6f8  or      ebx, 80070000h
0x14007b6fe  mov     eax, 80004005h
0x14007b703  test    ebx, ebx
0x14007b705  cmovns  ebx, eax
0x14007b708  mov     [rsp+70h+var_48], ebx; int
0x14007b70c  lea     rax, aFstatus258l; "fStatus != 258L"
0x14007b713  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14007b718  lea     r14, aCbraex; "CBRAEx"
0x14007b71f  mov     r9, r14; unsigned __int16 *
0x14007b722  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007b729  mov     r8, rsi; unsigned __int16 *
0x14007b72c  mov     r15d, 33Eh
0x14007b732  mov     edx, r15d; unsigned int
0x14007b735  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b73c  mov     rcx, rdi; unsigned __int16 *
0x14007b73f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b744  call    cs:__imp_IsDebuggerPresent
0x14007b74a  test    eax, eax
0x14007b74c  lea     rax, aFstatus258l; "fStatus != 258L"
0x14007b753  jz      short loc_14007B782
0x14007b755  mov     [rsp+70h+var_38], ebx
0x14007b759  mov     [rsp+70h+var_40], rax
0x14007b75e  mov     qword ptr [rsp+70h+var_48], r14
0x14007b763  mov     [rsp+70h+ppv], rsi
0x14007b768  mov     r9d, r15d
0x14007b76b  mov     r8, rdi
0x14007b76e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007b775  mov     ecx, r13d; unsigned __int8
0x14007b778  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007b77d  jmp     loc_14007BBF1
0x14007b782  mov     dword ptr [rsp+70h+var_40], ebx
0x14007b786  mov     qword ptr [rsp+70h+var_48], rax
0x14007b78b  mov     [rsp+70h+ppv], r14
0x14007b790  mov     r9, rsi
0x14007b793  mov     r8d, r15d
0x14007b796  mov     rdx, rdi
0x14007b799  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007b7a0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007b7a5  jmp     loc_14007BBF1
0x14007b7aa  cmp     eax, 0FFFFFFFFh
0x14007b7ad  jnz     short loc_14007B828
0x14007b7af  call    cs:__imp_GetLastError
0x14007b7b5  mov     ebx, eax
0x14007b7b7  test    eax, eax
0x14007b7b9  jle     short loc_14007B7C4
0x14007b7bb  movzx   ebx, ax
0x14007b7be  or      ebx, 80070000h
0x14007b7c4  mov     eax, 80004005h
0x14007b7c9  test    ebx, ebx
0x14007b7cb  cmovns  ebx, eax
0x14007b7ce  mov     [rsp+70h+var_48], ebx; int
0x14007b7d2  lea     rax, aFstatusDword0x; "fStatus != ((DWORD)0xFFFFFFFF)"
0x14007b7d9  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14007b7de  lea     r14, aCbraex; "CBRAEx"
0x14007b7e5  mov     r9, r14; unsigned __int16 *
0x14007b7e8  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007b7ef  mov     r8, rsi; unsigned __int16 *
0x14007b7f2  mov     r15d, 33Fh
0x14007b7f8  mov     edx, r15d; unsigned int
0x14007b7fb  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b802  mov     rcx, rdi; unsigned __int16 *
0x14007b805  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b80a  call    cs:__imp_IsDebuggerPresent
0x14007b810  test    eax, eax
0x14007b812  lea     rax, aFstatusDword0x; "fStatus != ((DWORD)0xFFFFFFFF)"
0x14007b819  jmp     loc_14007B753
0x14007b81e  mov     ebx, 800704D5h
0x14007b823  jmp     loc_14007BBF5
0x14007b828  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x14007b82f  lea     rdx, [rdi+48h]; struct CCriticalSection *
0x14007b833  lea     rcx, [rbp+var_30]; this
0x14007b837  call    ??0CAutoCriticalSection@@QEAA@PEAVCCriticalSection@@@Z; CAutoCriticalSection::CAutoCriticalSection(CCriticalSection *)
0x14007b83c  nop
0x14007b83d  test    rsi, rsi
0x14007b840  jnz     loc_14007B8F4
0x14007b846  mov     ebx, 80004003h
0x14007b84b  mov     [rsp+70h+var_48], ebx; int
0x14007b84f  lea     rax, aPserverlist; "pServerList"
0x14007b856  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14007b85b  lea     r14, aCbraex; "CBRAEx"
0x14007b862  mov     r9, r14; unsigned __int16 *
0x14007b865  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007b86c  mov     r8, rsi; unsigned __int16 *
0x14007b86f  mov     r15d, 34Ah
0x14007b875  mov     edx, r15d; unsigned int
0x14007b878  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b87f  mov     rcx, rdi; unsigned __int16 *
0x14007b882  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b887  call    cs:__imp_IsDebuggerPresent
0x14007b88d  test    eax, eax
0x14007b88f  lea     rax, aPserverlist; "pServerList"
0x14007b896  jz      short loc_14007B8C2
0x14007b898  mov     [rsp+70h+var_38], ebx
0x14007b89c  mov     [rsp+70h+var_40], rax
0x14007b8a1  mov     qword ptr [rsp+70h+var_48], r14
0x14007b8a6  mov     r9d, r15d
0x14007b8a9  mov     ecx, r13d; unsigned __int8
0x14007b8ac  mov     [rsp+70h+ppv], rsi
0x14007b8b1  mov     r8, rdi
0x14007b8b4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14007b8bb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007b8c0  jmp     short loc_14007B8E6
0x14007b8c2  mov     dword ptr [rsp+70h+var_40], ebx
0x14007b8c6  mov     qword ptr [rsp+70h+var_48], rax
0x14007b8cb  mov     [rsp+70h+ppv], r14
0x14007b8d0  mov     r8d, r15d
0x14007b8d3  mov     r9, rsi
0x14007b8d6  mov     rdx, rdi
0x14007b8d9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007b8e0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007b8e5  nop
0x14007b8e6  lea     rcx, [rbp+var_30]; this
0x14007b8ea  call    ??1CAutoCriticalSection@@QEAA@XZ; CAutoCriticalSection::~CAutoCriticalSection(void)
0x14007b8ef  jmp     loc_14007BBF5
0x14007b8f4  mov     rcx, rsi; pvarg
0x14007b8f7  call    cs:__imp_VariantInit
0x14007b8fd  mov     edx, [rdi+8]
0x14007b900  lea     rcx, aCclientnotific_21; "CClientNotificationSink::SendProbeAndDi"...
0x14007b907  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14007b90c  mov     r8d, [rdi+8]; cElements
0x14007b910  test    r8d, r8d
0x14007b913  jz      loc_14007BE16
0x14007b919  mov     esi, 8
0x14007b91e  mov     ecx, esi; vt
0x14007b920  xor     edx, edx; lLbound
0x14007b922  call    cs:__imp_SafeArrayCreateVector
0x14007b928  mov     [rbp+psa], rax
0x14007b92c  test    rax, rax
0x14007b92f  jnz     loc_14007B9BC
0x14007b935  mov     r14d, 8007000Eh
0x14007b93b  mov     ebx, r14d
0x14007b93e  mov     [rsp+70h+var_48], r14d; int
0x14007b943  lea     rax, aPserverlistsaf; "pServerListSafeArray"
0x14007b94a  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14007b94f  lea     r15, aCpr; "CPR"
0x14007b956  mov     r9, r15; unsigned __int16 *
0x14007b959  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007b960  mov     r8, rsi; unsigned __int16 *
0x14007b963  mov     edx, 353h; unsigned int
0x14007b968  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007b96f  mov     rcx, rdi; unsigned __int16 *
0x14007b972  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007b977  call    cs:__imp_IsDebuggerPresent
0x14007b97d  test    eax, eax
0x14007b97f  lea     rax, aPserverlistsaf; "pServerListSafeArray"
0x14007b986  jz      short loc_14007B9A2
0x14007b988  mov     [rsp+70h+var_38], r14d
0x14007b98d  mov     [rsp+70h+var_40], rax
0x14007b992  mov     qword ptr [rsp+70h+var_48], r15
0x14007b997  mov     r9d, 353h
0x14007b99d  jmp     loc_14007B8A9
0x14007b9a2  mov     dword ptr [rsp+70h+var_40], r14d
0x14007b9a7  mov     qword ptr [rsp+70h+var_48], rax
0x14007b9ac  mov     [rsp+70h+ppv], r15
0x14007b9b1  mov     r8d, 353h
0x14007b9b7  jmp     loc_14007B8D3
0x14007b9bc  mov     ecx, esi; vt
0x14007b9be  mov     r8d, [rdi+8]; cElements
0x14007b9c2  xor     edx, edx; lLbound
0x14007b9c4  call    cs:__imp_SafeArrayCreateVector
0x14007b9ca  mov     r14, rax
0x14007b9cd  test    rax, rax
0x14007b9d0  jnz     loc_14007BA5D
0x14007b9d6  mov     r14d, 8007000Eh
0x14007b9dc  mov     ebx, r14d
0x14007b9df  mov     [rsp+70h+var_48], r14d; int
0x14007b9e4  lea     rax, aPipaddresslist; "pIpAddressListSafeArray"
0x14007b9eb  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14007b9f0  lea     r15, aCpr; "CPR"
0x14007b9f7  mov     r9, r15; unsigned __int16 *
0x14007b9fa  lea     rsi, aCclientnotific; "CClientNotificationSink::SendProbeAndDi"...
0x14007ba01  mov     r8, rsi; unsigned __int16 *
0x14007ba04  mov     edx, 356h; unsigned int
0x14007ba09  lea     rdi, aTermsrvWmsSrcM_0; "termsrv\\wms\\src\\middletier\\discover"...
0x14007ba10  mov     rcx, rdi; unsigned __int16 *
0x14007ba13  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007ba18  call    cs:__imp_IsDebuggerPresent
0x14007ba1e  test    eax, eax
0x14007ba20  lea     rax, aPipaddresslist; "pIpAddressListSafeArray"
0x14007ba27  jz      short loc_14007BA43
0x14007ba29  mov     [rsp+70h+var_38], r14d
0x14007ba2e  mov     [rsp+70h+var_40], rax
0x14007ba33  mov     qword ptr [rsp+70h+var_48], r15
0x14007ba38  mov     r9d, 356h
0x14007ba3e  jmp     loc_14007B8A9
0x14007ba43  mov     dword ptr [rsp+70h+var_40], r14d
0x14007ba48  mov     qword ptr [rsp+70h+var_48], rax
0x14007ba4d  mov     [rsp+70h+ppv], r15
0x14007ba52  mov     r8d, 356h
  ... truncated ...
```
