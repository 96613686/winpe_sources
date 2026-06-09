# CUVHDProfileTelemetryLogging::GetLicenseInfo(long *,ulong *,ulong * *)

- ea: `0x180032b20`
- end: `0x180033441`
- name: `?GetLicenseInfo@CUVHDProfileTelemetryLogging@@SAJPEAJPEAKPEAPEAK@Z`
- size: `2337`
- prototype: `__int64 __fastcall(int *, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800337b0`

## callees

- `0x180003f30`
- `0x180012d7c`
- `0x180028b84`
- `0x180032aac`
- `0x180032ae8`
- `0x180032b20`
- `0x180033448`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032bb3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180032bb3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800333bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800333bb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180032c94`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180032c94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032c04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032c04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003305f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003305f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180033103`
- `OLEAUT32!__imp_SysAllocString` at `0x180033124`
- `OLEAUT32!__imp_SysAllocString` at `0x180033103`
- `OLEAUT32!__imp_SysAllocString` at `0x180033124`
- `OLEAUT32!__imp_SysFreeString` at `0x180033201`
- `OLEAUT32!__imp_SysFreeString` at `0x180033201`
- `OLEAUT32!__imp_VariantInit` at `0x180032b6f`
- `OLEAUT32!__imp_VariantInit` at `0x180032b79`
- `OLEAUT32!__imp_VariantInit` at `0x180032b83`
- `OLEAUT32!__imp_VariantInit` at `0x180032b8d`
- `OLEAUT32!__imp_VariantInit` at `0x180033149`
- `OLEAUT32!__imp_VariantInit` at `0x180032b6f`
- `OLEAUT32!__imp_VariantInit` at `0x180032b79`
- `OLEAUT32!__imp_VariantInit` at `0x180032b83`
- `OLEAUT32!__imp_VariantInit` at `0x180032b8d`
- `OLEAUT32!__imp_VariantInit` at `0x180033149`
- `OLEAUT32!__imp_VariantClear` at `0x180033116`
- `OLEAUT32!__imp_VariantClear` at `0x18003328e`
- `OLEAUT32!__imp_VariantClear` at `0x180033298`
- `OLEAUT32!__imp_VariantClear` at `0x1800332e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800332f3`
- `OLEAUT32!__imp_VariantClear` at `0x180033357`
- `OLEAUT32!__imp_VariantClear` at `0x180033361`
- `OLEAUT32!__imp_VariantClear` at `0x1800333ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800333d8`
- `OLEAUT32!__imp_VariantClear` at `0x1800333e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800333ec`
- `OLEAUT32!__imp_VariantClear` at `0x180033116`
- `OLEAUT32!__imp_VariantClear` at `0x18003328e`
- `OLEAUT32!__imp_VariantClear` at `0x180033298`
- `OLEAUT32!__imp_VariantClear` at `0x1800332e9`
- `OLEAUT32!__imp_VariantClear` at `0x1800332f3`
- `OLEAUT32!__imp_VariantClear` at `0x180033357`
- `OLEAUT32!__imp_VariantClear` at `0x180033361`
- `OLEAUT32!__imp_VariantClear` at `0x1800333ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800333d8`
- `OLEAUT32!__imp_VariantClear` at `0x1800333e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800333ec`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180032fd7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180032fd7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180033092`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180033092`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003337f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003337f`

## string_xrefs

- `0x180032c10`: `CoCreateInstance() failed failed: 0x%x in %s`
- `0x180032c30`: `\\.\ROOT\cimv2\TerminalServices`
- `0x180032cba`: `SELECT * FROM Win32_TerminalServiceSetting`
- `0x180032d5f`: `__PATH`
- `0x180032d80`: `Failed to get class __PATH property. failed: 0x%x in %s`
- `0x180032d9e`: `Failed to get class __PATH property. Return value is not VT_BSTR. failed: 0x%x in %s`
- `0x18003309e`: `SafeArrayAccessData failed. failed: 0x%x in %s`
- `0x1800330d9`: `Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus. failed: 0x%x in %s`
- `0x180033373`: `Failed to create a new instance of a class. failed: 0x%x in %s`
- `0x180033395`: `SafeArrayUnaccessData failed. failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUVHDProfileTelemetryLogging::GetLicenseInfo(int *a1, unsigned int *a2, unsigned int **a3)
{
  unsigned int **v3; // r15
  unsigned int *v4; // r12
  LONG lVal; // r13d
  void *v6; // rsi
  HRESULT Instance; // eax
  LONG v8; // ebx
  int v9; // edi
  const char *v10; // rdx
  __int64 v11; // r8
  struct IUnknown *v12; // rdx
  int v13; // ebx
  int v14; // eax
  struct IUnknown *v15; // rdx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  struct IUnknown *v19; // rdx
  SAFEARRAY *parray; // r12
  HRESULT UBound; // eax
  bool v22; // zf
  unsigned int v23; // eax
  HRESULT v24; // eax
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // r8
  int Method; // eax
  __int64 i; // r15
  const OLECHAR *v29; // rbx
  int v30; // eax
  int v31; // eax
  IUnknown *v32; // rsi
  __int64 v33; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  ATL::CComBSTR *v35; // rax
  int v36; // eax
  int v37; // eax
  HRESULT v38; // eax
  struct IUnknown *v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *pProxy; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v44; // [rsp+70h] [rbp-90h]
  struct IUnknown *ppv; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  struct IWbemClassObject *v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG v50; // [rsp+B0h] [rbp-50h] BYREF
  void *ppvData; // [rsp+C8h] [rbp-38h] BYREF
  struct IWbemClassObject *v52; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v53; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+108h] [rbp+8h] BYREF
  VARIANTARG v56; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v57; // [rsp+128h] [rbp+28h] BYREF
  LONG plUbound; // [rsp+1A8h] [rbp+A8h] BYREF

  ppv = 0;
  v3 = a3;
  pProxy = 0;
  v4 = a2;
  v49 = 0;
  v40 = 0;
  v52 = 0;
  v48 = 0;
  VariantInit(&pvarg);
  VariantInit(&v53);
  VariantInit(&v57);
  VariantInit(&v56);
  ppvData = 0;
  plUbound = 0;
  lVal = 0;
  v47 = 0;
  v6 = 0;
  v43 = 0;
  Instance = CoInitializeEx(0, 2u);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v9 = 0;
    v10 = "CoInitializeEx() failed. failed: 0x%x in %s";
LABEL_3:
    v11 = (unsigned int)Instance;
LABEL_4:
    _DbgPrintMessage(8, v10, v11, "CUVHDProfileTelemetryLogging::GetLicenseInfo");
    goto LABEL_50;
  }
  v9 = 1;
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)&ppv);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = "CoCreateInstance() failed failed: 0x%x in %s";
    goto LABEL_3;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))ppv->lpVtbl[1].QueryInterface)(
               ppv,
               L"\\\\.\\ROOT\\cimv2\\TerminalServices",
               0,
               0,
               0,
               128,
               0,
               0,
               &pProxy);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = "ConnectServer() failed failed: 0x%x in %s";
    goto LABEL_3;
  }
  Instance = CoSetProxyBlanket(pProxy, 0xAu, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = "CoSetProxyBlanket() failed failed: 0x%x in %s";
    goto LABEL_3;
  }
  Instance = ((__int64 (__fastcall *)(IUnknown *, const OLECHAR *, const wchar_t *, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
               pProxy,
               L"WQL",
               L"SELECT * FROM Win32_TerminalServiceSetting",
               48,
               0,
               &v47);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = "Failed to enum settingdata. failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( !v47 )
  {
    v8 = -2147467259;
    v10 = "Enum object is NULL. failed: 0x%x in %s";
    v11 = 2147500037LL;
    goto LABEL_4;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v47 + 32LL))(
         v47,
         0xFFFFFFFFLL,
         1,
         &v49,
         &v43);
  if ( v8 < 0 )
  {
LABEL_18:
    v11 = (unsigned int)v8;
    v10 = "Failed to get settingdata object. failed: 0x%x in %s";
    goto LABEL_4;
  }
  if ( !v43 )
  {
    v8 = -2147023728;
    goto LABEL_18;
  }
  Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v49 + 32LL))(
               v49,
               L"__PATH",
               0,
               &pvarg,
               0,
               0);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = "Failed to get class __PATH property. failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( pvarg.vt != 8 )
  {
    v8 = -2147467259;
    v10 = "Failed to get class __PATH property. Return value is not VT_BSTR. failed: 0x%x in %s";
LABEL_23:
    v11 = (unsigned int)v8;
    goto LABEL_4;
  }
  v13 = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, const wchar_t *, _QWORD, _QWORD, _QWORD, struct IUnknown **, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
          pProxy,
          pvarg.llVal,
          L"GetGracePeriodDays",
          0,
          0,
          0,
          &v40,
          0);
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "GetGracePeriodDays failed.");
    lVal = v13;
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v40->lpVtbl[1].AddRef)(
            v40,
            L"ReturnValue",
            0,
            &v53,
            0,
            0);
    v8 = v14;
    if ( v14 < 0 )
    {
      v11 = (unsigned int)v14;
      v10 = "Failed to get ReturnValue from GetGracePeriodDays call. failed: 0x%x in %s";
      goto LABEL_4;
    }
    lVal = v53.lVal;
    if ( v53.lVal < 0 )
    {
      _DbgPrintMessage(8, "GetGracePeriodDays failed.");
    }
    else
    {
      lVal = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v40->lpVtbl[1].AddRef)(
               v40,
               L"DaysLeft",
               0,
               &v57,
               0,
               0);
      if ( lVal < 0 )
        _DbgPrintMessage(8, "Failed to get DaysLeft value.");
      else
        lVal = v57.lVal;
    }
  }
  if ( v40 )
    ATL::AtlComPtrAssign(&v40, v15);
  v16 = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, const wchar_t *, _QWORD, _QWORD, _QWORD, struct IUnknown **, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
          pProxy,
          pvarg.llVal,
          L"GetSpecifiedLicenseServerList",
          0,
          0,
          0,
          &v40,
          0);
  v8 = v16;
  if ( v16 < 0 )
  {
    v11 = (unsigned int)v16;
    v10 = "Failed to execute GetSpecifiedLicenseServerList method. failed: 0x%x in %s";
    goto LABEL_4;
  }
  v17 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v40->lpVtbl[1].AddRef)(
          v40,
          L"ReturnValue",
          0,
          &v53,
          0,
          0);
  v8 = v17;
  if ( v17 < 0 )
  {
    v11 = (unsigned int)v17;
    v10 = "Failed to get ReturnValue from GetSpecifiedLicenseServerList call. failed: 0x%x in %s";
    goto LABEL_4;
  }
  v8 = v53.lVal;
  if ( v53.lVal < 0 )
  {
    v10 = "GetSpecifiedLicenseServerList failed. failed: 0x%x in %s";
    goto LABEL_23;
  }
  v18 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))v40->lpVtbl[1].AddRef)(
          v40,
          L"SpecifiedLSList",
          0,
          &v56,
          0);
  v8 = v18;
  if ( v18 < 0 )
  {
    v11 = (unsigned int)v18;
    v10 = "Failed to get SpecifiedLSList from GetSpecifiedLicenseServerList call. failed: 0x%x in %s";
    goto LABEL_4;
  }
  if ( v56.vt == 8200 )
  {
    parray = v56.parray;
    if ( v40 )
      ATL::AtlComPtrAssign(&v40, v19);
    UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    v8 = UBound;
    if ( UBound >= 0 )
    {
      v22 = plUbound == -1;
      v23 = ++plUbound;
      if ( !v22 )
      {
        v44 = LocalAlloc(0x40u, 4LL * v23);
        v6 = v44;
        if ( v44 )
        {
          v24 = SafeArrayAccessData(parray, &ppvData);
          v8 = v24;
          if ( v24 >= 0 )
          {
            Method = CUVHDProfileTelemetryLogging::GetMethod((struct IWbemServices *)pProxy, v25, v26, &v52, &v48, 0);
            v8 = Method;
            if ( Method >= 0 )
            {
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= plUbound )
                {
                  v38 = SafeArrayUnaccessData(parray);
                  v8 = v38;
                  if ( v38 < 0 )
                    _DbgPrintMessage(
                      8,
                      "SafeArrayUnaccessData failed. failed: 0x%x in %s",
                      v38,
                      "CUVHDProfileTelemetryLogging::GetLicenseInfo");
                  goto LABEL_77;
                }
                v41 = 0;
                v29 = SysAllocString(*((const OLECHAR **)ppvData + i));
                v46.vt = 0;
                VariantClear(&v46);
                v46.vt = 8;
                v46.llVal = (LONGLONG)SysAllocString(v29);
                if ( !v46.llVal && v29 )
                {
                  v46.vt = 10;
                  v46.lVal = -2147024882;
                  ATL::AtlThrowImpl(-2147024882);
                }
                VariantInit(&v50);
                v30 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, __int64 *))v48->lpVtbl->SpawnInstance)(
                        v48,
                        0,
                        &v41);
                v8 = v30;
                if ( v30 < 0 )
                  break;
                v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v41 + 40LL))(
                        v41,
                        L"ServerName",
                        0,
                        &v46,
                        0);
                v8 = v31;
                if ( v31 < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "Failed to put 'ServerName' parameter. failed: 0x%x in %s",
                    (unsigned int)v31,
                    "CUVHDProfileTelemetryLogging::GetLicenseInfo");
                  goto LABEL_82;
                }
                v32 = pProxy;
                v33 = v41;
                QueryInterface = pProxy->lpVtbl[8].QueryInterface;
                v35 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"GetTStoLSConnectivityStatus");
                v8 = ((__int64 (__fastcall *)(IUnknown *, LONGLONG, _QWORD, _QWORD, _QWORD, __int64, struct IUnknown **, _QWORD))QueryInterface)(
                       v32,
                       pvarg.llVal,
                       *(_QWORD *)v35,
                       0,
                       0,
                       v33,
                       &v40,
                       0);
                SysFreeString(bstrString);
                if ( v8 < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "Failed to execute SetSpecifiedLicenseServerList method. failed: 0x%x in %s",
                    (unsigned int)v8,
                    "CUVHDProfileTelemetryLogging::GetLicenseInfo");
                  goto LABEL_76;
                }
                v36 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v40->lpVtbl[1].AddRef)(
                        v40,
                        L"ReturnValue",
                        0,
                        &v53,
                        0,
                        0);
                v8 = v36;
                if ( v36 < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "Failed to get ReturnValue from GetTStoLSConnectivityStatus call. failed: 0x%x in %s",
                    (unsigned int)v36,
                    "CUVHDProfileTelemetryLogging::GetLicenseInfo");
                  goto LABEL_76;
                }
                v8 = v53.lVal;
                if ( v53.lVal < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "GetTStoLSConnectivityStatus failed. failed: 0x%x in %s",
                    v53.cyVal.Lo,
                    "CUVHDProfileTelemetryLogging::GetLicenseInfo");
                  goto LABEL_76;
                }
                v37 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v40->lpVtbl[1].AddRef)(
                        v40,
                        L"TStoLSConnectivityStatus",
                        0,
                        &v50,
                        0,
                        0);
                v8 = v37;
                if ( v37 < 0 )
                {
                  _DbgPrintMessage(
                    8,
                    "Failed to get SpecifiedLSList from TStoLSConnectivityStatus call. failed: 0x%x in %s",
                    (unsigned int)v37,
                    "CUVHDProfileTelemetryLogging::GetLicenseInfo");
LABEL_76:
                  VariantClear(&v50);
                  VariantClear(&v46);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                  v6 = v44;
                  v9 = 1;
                  goto LABEL_77;
                }
                v6 = v44;
                *((_DWORD *)v44 + i) = v50.lVal;
                VariantClear(&v50);
                VariantClear(&v46);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                v9 = 1;
              }
              _DbgPrintMessage(
                8,
                "Failed to create a new instance of a class. failed: 0x%x in %s",
                (unsigned int)v30,
                "CUVHDProfileTelemetryLogging::GetLicenseInfo");
LABEL_82:
              VariantClear(&v50);
              VariantClear(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
LABEL_77:
              v3 = a3;
            }
            else
            {
              _DbgPrintMessage(
                8,
                "Failed to get Win32_TerminalServiceSetting.GetTStoLSConnectivityStatus. failed: 0x%x in %s",
                (unsigned int)Method,
                "CUVHDProfileTelemetryLogging::GetLicenseInfo");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "SafeArrayAccessData failed. failed: 0x%x in %s",
              (unsigned int)v24,
              "CUVHDProfileTelemetryLogging::GetLicenseInfo");
          }
        }
        else
        {
          v8 = -2147467259;
          _DbgPrintMessage(8, "Out of mememory while allocating pdwServerStatus");
        }
      }
    }
    else
    {
      _DbgPrintMessage(8, "SafeArrayGetLBound failed 0x%x", UBound);
    }
    v4 = a2;
  }
  else
  {
    v8 = -2147467259;
    _DbgPrintMessage(8, "SpecifiedLSList value is invalid.");
  }
LABEL_50:
  if ( pProxy )
    ATL::AtlComPtrAssign(&pProxy, v12);
  if ( ppv )
    ATL::AtlComPtrAssign(&ppv, v12);
  if ( v8 < 0 )
  {
    if ( v6 )
      LocalFree(v6);
  }
  else
  {
    *v3 = (unsigned int *)v6;
    *a1 = lVal;
    *v4 = plUbound;
  }
  if ( v9 )
    CoUninitialize();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  VariantClear(&v56);
  VariantClear(&v57);
  VariantClear(&v53);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180032b20  mov     [rsp-8+arg_10], r8
0x180032b25  mov     [rsp-8+arg_8], rdx
0x180032b2a  mov     [rsp-8+arg_0], rcx
0x180032b2f  push    rbp
0x180032b30  push    rbx
0x180032b31  push    rsi
0x180032b32  push    rdi
0x180032b33  push    r12
0x180032b35  push    r13
0x180032b37  push    r14
0x180032b39  push    r15
0x180032b3b  lea     rbp, [rsp-48h]
0x180032b40  sub     rsp, 148h
0x180032b47  xor     r14d, r14d
0x180032b4a  lea     rcx, [rbp+80h+pvarg]; pvarg
0x180032b4e  mov     [rsp+180h+var_108], r14
0x180032b53  mov     r15, r8
0x180032b56  mov     [rsp+180h+pProxy], r14
0x180032b5b  mov     r12, rdx
0x180032b5e  mov     [rbp+80h+var_D8], r14
0x180032b62  mov     [rsp+180h+var_130], r14
0x180032b67  mov     [rbp+80h+var_B0], r14
0x180032b6b  mov     [rbp+80h+var_E0], r14
0x180032b6f  call    cs:__imp_VariantInit
0x180032b75  lea     rcx, [rbp+80h+var_A8]; pvarg
0x180032b79  call    cs:__imp_VariantInit
0x180032b7f  lea     rcx, [rbp+80h+var_58]; pvarg
0x180032b83  call    cs:__imp_VariantInit
0x180032b89  lea     rcx, [rbp+80h+var_70]; pvarg
0x180032b8d  call    cs:__imp_VariantInit
0x180032b93  lea     edx, [r14+2]; dwCoInit
0x180032b97  mov     [rbp+80h+ppvData], r14
0x180032b9b  xor     ecx, ecx; pvReserved
0x180032b9d  mov     [rbp+80h+plUbound], r14d
0x180032ba4  mov     r13d, r14d
0x180032ba7  mov     [rbp+80h+var_E8], r14
0x180032bab  mov     esi, r14d
0x180032bae  mov     [rsp+180h+var_118], r14d
0x180032bb3  call    cs:__imp_CoInitializeEx
0x180032bb9  mov     ebx, eax
0x180032bbb  test    eax, eax
0x180032bbd  jns     short loc_180032BE2
0x180032bbf  mov     edi, r14d
0x180032bc2  lea     rdx, aCoinitializeex; "CoInitializeEx() failed. failed: 0x%x i"...
0x180032bc9  mov     r8d, eax
0x180032bcc  mov     ecx, 8; int
0x180032bd1  lea     r9, aCuvhdprofilete_4; "CUVHDProfileTelemetryLogging::GetLicens"...
0x180032bd8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032bdd  jmp     loc_180032FFC
0x180032be2  lea     rax, [rsp+180h+var_108]
0x180032be7  mov     edi, 1
0x180032bec  mov     r8d, edi; dwClsContext
0x180032bef  mov     [rsp+180h+ppv], rax; ppv
0x180032bf4  lea     r9, IID_IWbemLocator; riid
0x180032bfb  xor     edx, edx; pUnkOuter
0x180032bfd  lea     rcx, CLSID_WbemLocator; rclsid
0x180032c04  call    cs:__imp_CoCreateInstance
0x180032c0a  mov     ebx, eax
0x180032c0c  test    eax, eax
0x180032c0e  jns     short loc_180032C19
0x180032c10  lea     rdx, aCocreateinstan_0; "CoCreateInstance() failed failed: 0x%x "...
0x180032c17  jmp     short loc_180032BC9
0x180032c19  mov     rcx, [rsp+180h+var_108]
0x180032c1e  lea     rdx, [rsp+180h+pProxy]
0x180032c23  mov     [rsp+180h+var_140], rdx
0x180032c28  xor     r9d, r9d
0x180032c2b  mov     qword ptr [rsp+180h+dwCapabilities], r14
0x180032c30  lea     rdx, aRootCimv2Termi_0; "\\\\.\\ROOT\\cimv2\\TerminalServices"
0x180032c37  mov     [rsp+180h+pAuthInfo], r14
0x180032c3c  xor     r8d, r8d
0x180032c3f  mov     rax, [rcx]
0x180032c42  mov     [rsp+180h+dwImpLevel], 80h
0x180032c4a  mov     [rsp+180h+ppv], r14
0x180032c4f  mov     rax, [rax+18h]
0x180032c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c58  mov     ebx, eax
0x180032c5a  test    eax, eax
0x180032c5c  jns     short loc_180032C6A
0x180032c5e  lea     rdx, aConnectserverF; "ConnectServer() failed failed: 0x%x in "...
0x180032c65  jmp     loc_180032BC9
0x180032c6a  mov     rcx, [rsp+180h+pProxy]; pProxy
0x180032c6f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180032c73  mov     [rsp+180h+dwCapabilities], r14d; dwCapabilities
0x180032c78  xor     r8d, r8d; dwAuthzSvc
0x180032c7b  mov     [rsp+180h+pAuthInfo], r14; pAuthInfo
0x180032c80  mov     [rsp+180h+dwImpLevel], 3; dwImpLevel
0x180032c88  lea     edx, [r9+0Bh]; dwAuthnSvc
0x180032c8c  mov     dword ptr [rsp+180h+ppv], 6; dwAuthnLevel
0x180032c94  call    cs:__imp_CoSetProxyBlanket
0x180032c9a  mov     ebx, eax
0x180032c9c  test    eax, eax
0x180032c9e  jns     short loc_180032CAC
0x180032ca0  lea     rdx, aCosetproxyblan_0; "CoSetProxyBlanket() failed failed: 0x%x"...
0x180032ca7  jmp     loc_180032BC9
0x180032cac  mov     rcx, [rsp+180h+pProxy]
0x180032cb1  lea     rdx, [rbp+80h+var_E8]
0x180032cb5  mov     qword ptr [rsp+180h+dwImpLevel], rdx
0x180032cba  lea     r8, aSelectFromWin3; "SELECT * FROM Win32_TerminalServiceSett"...
0x180032cc1  mov     r9d, 30h ; '0'
0x180032cc7  mov     [rsp+180h+ppv], r14
0x180032ccc  lea     rdx, aWql; "WQL"
0x180032cd3  mov     rax, [rcx]
0x180032cd6  mov     rax, [rax+0A0h]
0x180032cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ce2  mov     ebx, eax
0x180032ce4  test    eax, eax
0x180032ce6  jns     short loc_180032CF4
0x180032ce8  lea     rdx, aFailedToEnumSe; "Failed to enum settingdata. failed: 0x%"...
0x180032cef  jmp     loc_180032BC9
0x180032cf4  mov     rcx, [rbp+80h+var_E8]
0x180032cf8  test    rcx, rcx
0x180032cfb  jnz     short loc_180032D11
0x180032cfd  mov     ebx, 80004005h
0x180032d02  lea     rdx, aEnumObjectIsNu; "Enum object is NULL. failed: 0x%x in %s"
0x180032d09  mov     r8d, ebx
0x180032d0c  jmp     loc_180032BCC
0x180032d11  mov     rax, [rcx]
0x180032d14  lea     r8, [rsp+180h+var_118]
0x180032d19  mov     [rsp+180h+ppv], r8
0x180032d1e  lea     r9, [rbp+80h+var_D8]
0x180032d22  mov     r8d, edi
0x180032d25  or      edx, 0FFFFFFFFh
0x180032d28  mov     rax, [rax+20h]
0x180032d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d31  mov     ebx, eax
0x180032d33  test    eax, eax
0x180032d35  js      short loc_180032D43
0x180032d37  cmp     [rsp+180h+var_118], r14d
0x180032d3c  jnz     short loc_180032D52
0x180032d3e  mov     ebx, 80070490h
0x180032d43  mov     r8d, ebx
0x180032d46  lea     rdx, aFailedToGetSet; "Failed to get settingdata object. faile"...
0x180032d4d  jmp     loc_180032BCC
0x180032d52  mov     rcx, [rbp+80h+var_D8]
0x180032d56  lea     r9, [rbp+80h+pvarg]
0x180032d5a  mov     qword ptr [rsp+180h+dwImpLevel], r14
0x180032d5f  lea     rdx, aPath; "__PATH"
0x180032d66  xor     r8d, r8d
0x180032d69  mov     [rsp+180h+ppv], r14
0x180032d6e  mov     rax, [rcx]
0x180032d71  mov     rax, [rax+20h]
0x180032d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d7a  mov     ebx, eax
0x180032d7c  test    eax, eax
0x180032d7e  jns     short loc_180032D8C
0x180032d80  lea     rdx, aFailedToGetCla_1; "Failed to get class __PATH property. fa"...
0x180032d87  jmp     loc_180032BC9
0x180032d8c  mov     r14d, 8
0x180032d92  cmp     word ptr [rbp+80h+pvarg], r14w
0x180032d97  jz      short loc_180032DB0
0x180032d99  mov     ebx, 80004005h
0x180032d9e  lea     rdx, aFailedToGetCla; "Failed to get class __PATH property. Re"...
0x180032da5  mov     r8d, ebx
0x180032da8  mov     ecx, r14d
0x180032dab  jmp     loc_180032BD1
0x180032db0  mov     rcx, [rsp+180h+pProxy]
0x180032db5  lea     rdx, [rsp+180h+var_130]
0x180032dba  xor     r8d, r8d
0x180032dbd  xor     r9d, r9d
0x180032dc0  mov     qword ptr [rsp+180h+dwCapabilities], r8
0x180032dc5  mov     [rsp+180h+pAuthInfo], rdx
0x180032dca  mov     rax, [rcx]
0x180032dcd  mov     rdx, qword ptr [rbp+80h+pvarg+8]
0x180032dd1  mov     qword ptr [rsp+180h+dwImpLevel], r8
0x180032dd6  mov     [rsp+180h+ppv], r8
0x180032ddb  lea     r8, aGetgraceperiod_0; "GetGracePeriodDays"
0x180032de2  mov     rax, [rax+0C0h]
0x180032de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dee  mov     ebx, eax
0x180032df0  test    eax, eax
0x180032df2  js      loc_180032E91
0x180032df8  mov     rcx, [rsp+180h+var_130]
0x180032dfd  lea     r9, [rbp+80h+var_A8]
0x180032e01  mov     qword ptr [rsp+180h+dwImpLevel], rsi
0x180032e06  lea     rdx, aReturnvalue; "ReturnValue"
0x180032e0d  xor     r8d, r8d
0x180032e10  mov     [rsp+180h+ppv], rsi
0x180032e15  mov     rax, [rcx]
0x180032e18  mov     rax, [rax+20h]
0x180032e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e21  mov     ebx, eax
0x180032e23  test    eax, eax
0x180032e25  jns     short loc_180032E36
0x180032e27  mov     r8d, eax
0x180032e2a  lea     rdx, aFailedToGetRet_1; "Failed to get ReturnValue from GetGrace"...
0x180032e31  jmp     loc_180032DA8
0x180032e36  mov     r13d, dword ptr [rbp+80h+var_A8+8]
0x180032e3a  xor     ebx, ebx
0x180032e3c  test    r13d, r13d
0x180032e3f  js      short loc_180032E80
0x180032e41  mov     rcx, [rsp+180h+var_130]
0x180032e46  lea     r9, [rbp+80h+var_58]
0x180032e4a  mov     qword ptr [rsp+180h+dwImpLevel], rbx
0x180032e4f  lea     rdx, aDaysleft; "DaysLeft"
0x180032e56  xor     r8d, r8d
0x180032e59  mov     [rsp+180h+ppv], rbx
0x180032e5e  mov     rax, [rcx]
0x180032e61  mov     rax, [rax+20h]
0x180032e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e6a  mov     r13d, eax
0x180032e6d  test    eax, eax
0x180032e6f  js      short loc_180032E77
0x180032e71  mov     r13d, dword ptr [rbp+80h+var_58+8]
0x180032e75  jmp     short loc_180032EA5
0x180032e77  lea     rdx, aFailedToGetDay; "Failed to get DaysLeft value."
0x180032e7e  jmp     short loc_180032E87
0x180032e80  lea     rdx, aGetgraceperiod; "GetGracePeriodDays failed."
0x180032e87  mov     ecx, r14d; int
0x180032e8a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032e8f  jmp     short loc_180032EA5
0x180032e91  lea     rdx, aGetgraceperiod; "GetGracePeriodDays failed."
0x180032e98  mov     ecx, r14d; int
0x180032e9b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032ea0  mov     r13d, ebx
0x180032ea3  xor     ebx, ebx
0x180032ea5  cmp     [rsp+180h+var_130], rbx
0x180032eaa  jz      short loc_180032EB6
0x180032eac  lea     rcx, [rsp+180h+var_130]; struct IUnknown **
0x180032eb1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180032eb6  mov     rcx, [rsp+180h+pProxy]
0x180032ebb  lea     rdx, [rsp+180h+var_130]
0x180032ec0  mov     qword ptr [rsp+180h+dwCapabilities], rbx
0x180032ec5  lea     r8, aGetspecifiedli; "GetSpecifiedLicenseServerList"
0x180032ecc  mov     [rsp+180h+pAuthInfo], rdx
0x180032ed1  xor     r9d, r9d
0x180032ed4  mov     rdx, qword ptr [rbp+80h+pvarg+8]
0x180032ed8  mov     rax, [rcx]
0x180032edb  mov     qword ptr [rsp+180h+dwImpLevel], rbx
0x180032ee0  mov     [rsp+180h+ppv], rbx
0x180032ee5  mov     rax, [rax+0C0h]
0x180032eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ef1  mov     ebx, eax
0x180032ef3  test    eax, eax
0x180032ef5  jns     short loc_180032F06
0x180032ef7  mov     r8d, eax
0x180032efa  lea     rdx, aFailedToExecut; "Failed to execute GetSpecifiedLicenseSe"...
0x180032f01  jmp     loc_180032DA8
0x180032f06  mov     rcx, [rsp+180h+var_130]
0x180032f0b  lea     r9, [rbp+80h+var_A8]
0x180032f0f  mov     qword ptr [rsp+180h+dwImpLevel], rsi
0x180032f14  lea     rdx, aReturnvalue; "ReturnValue"
0x180032f1b  xor     r8d, r8d
0x180032f1e  mov     [rsp+180h+ppv], rsi
0x180032f23  mov     rax, [rcx]
0x180032f26  mov     rax, [rax+20h]
0x180032f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f2f  mov     ebx, eax
0x180032f31  test    eax, eax
0x180032f33  jns     short loc_180032F44
0x180032f35  mov     r8d, eax
0x180032f38  lea     rdx, aFailedToGetRet; "Failed to get ReturnValue from GetSpeci"...
0x180032f3f  jmp     loc_180032DA8
0x180032f44  mov     ebx, dword ptr [rbp+80h+var_A8+8]
0x180032f47  test    ebx, ebx
0x180032f49  jns     short loc_180032F57
0x180032f4b  lea     rdx, aGetspecifiedli_0; "GetSpecifiedLicenseServerList failed. f"...
0x180032f52  jmp     loc_180032DA5
0x180032f57  mov     rcx, [rsp+180h+var_130]
0x180032f5c  lea     r9, [rbp+80h+var_70]
0x180032f60  mov     qword ptr [rsp+180h+dwImpLevel], rsi; struct IWbemClassObject **
0x180032f65  lea     rdx, aSpecifiedlslis_0; "SpecifiedLSList"
0x180032f6c  xor     r8d, r8d
0x180032f6f  mov     [rsp+180h+ppv], rsi
0x180032f74  mov     rax, [rcx]
0x180032f77  mov     rax, [rax+20h]
0x180032f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f80  mov     ebx, eax
0x180032f82  test    eax, eax
0x180032f84  jns     short loc_180032F95
0x180032f86  mov     r8d, eax
0x180032f89  lea     rdx, aFailedToGetSpe_0; "Failed to get SpecifiedLSList from GetS"...
0x180032f90  jmp     loc_180032DA8
0x180032f95  mov     eax, 2008h
0x180032f9a  cmp     word ptr [rbp+80h+var_70], ax
0x180032f9e  jz      short loc_180032FB6
0x180032fa0  lea     rdx, aSpecifiedlslis; "SpecifiedLSList value is invalid."
0x180032fa7  mov     ecx, r14d; int
0x180032faa  mov     ebx, 80004005h
0x180032faf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032fb4  jmp     short loc_180032FFC
0x180032fb6  mov     r12, qword ptr [rbp+80h+var_70+8]
0x180032fba  cmp     [rsp+180h+var_130], rsi
0x180032fbf  jz      short loc_180032FCB
0x180032fc1  lea     rcx, [rsp+180h+var_130]; struct IUnknown **
0x180032fc6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180032fcb  lea     r8, [rbp+80h+plUbound]; plUbound
0x180032fd2  mov     edx, edi; nDim
0x180032fd4  mov     rcx, r12; psa
0x180032fd7  call    cs:__imp_SafeArrayGetUBound
0x180032fdd  mov     ebx, eax
0x180032fdf  test    eax, eax
0x180032fe1  jns     short loc_180033044
0x180032fe3  mov     r8d, eax
0x180032fe6  lea     rdx, aSafearraygetlb; "SafeArrayGetLBound failed 0x%x"
0x180032fed  mov     ecx, r14d; int
0x180032ff0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032ff5  mov     r12, [rbp+80h+arg_8]
0x180032ffc  cmp     [rsp+180h+pProxy], 0
0x180033002  jz      short loc_18003300E
0x180033004  lea     rcx, [rsp+180h+pProxy]; struct IUnknown **
  ... truncated ...
```
