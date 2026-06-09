# UniDrvUI::PerformJScriptDevmodeValidation(UniDrvUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)

- ea: `0x180114e38`
- end: `0x180115507`
- name: `?PerformJScriptDevmodeValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z`
- size: `1743`
- prototype: `__int64 __fastcall(UniDrvUI *this, struct UniDrvUI::_COMMONINFO *, const struct _devicemodeW **, struct _devicemodeW **, _DWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180113264`
- `0x180115510`

## callees

- `0x180003430`
- `0x180003c64`
- `0x1800192f0`
- `0x180034084`
- `0x18003411c`
- `0x1800341bc`
- `0x1800ee8cc`
- `0x1800f7d64`
- `0x1800fdba0`
- `0x1800ff438`
- `0x1800ffc98`
- `0x180105360`
- `0x180107214`
- `0x180108e2c`
- `0x180113cb0`
- `0x180114e38`
- `0x1801b56bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18011542b`
- `KERNEL32!LocalFree` at `0x18011542b`
- `KERNEL32!LocalAlloc` at `0x18011543e`
- `KERNEL32!LocalAlloc` at `0x18011543e`
- `OLEAUT32!__imp_SysFreeString` at `0x180115152`
- `OLEAUT32!__imp_SysFreeString` at `0x180115363`
- `OLEAUT32!__imp_SysFreeString` at `0x180115152`
- `OLEAUT32!__imp_SysFreeString` at `0x180115363`
- `ole32!CoInitializeEx` at `0x180114f4f`
- `ole32!CoInitializeEx` at `0x180114f4f`
- `ole32!CoUninitialize` at `0x18011503b`
- `ole32!CoUninitialize` at `0x1801153a8`
- `ole32!CoUninitialize` at `0x18011503b`
- `ole32!CoUninitialize` at `0x1801153a8`
- `ole32!CoTaskMemFree` at `0x180115051`
- `ole32!CoTaskMemFree` at `0x180115171`
- `ole32!CoTaskMemFree` at `0x1801154c5`
- `ole32!CoTaskMemFree` at `0x180115051`
- `ole32!CoTaskMemFree` at `0x180115171`
- `ole32!CoTaskMemFree` at `0x1801154c5`

## string_xrefs

- `0x180115185`: `Try retrieving the driver's URI from the config file`
- `0x180114ee7`: `Attempt to check if the DevMode element exists in the current cache`
- `0x180114ecc`: `Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE`
- `0x180114f38`: `Current DevMode element does not exist in the current cache`
- `0x180114f0e`: `Current DevMode element exists in the current cache`
- `0x1801153fe`: `The DevMode element exists in the cache, set the return data value`
- `0x180115219`: `Get print ticket XML`
- `0x1801153c0`: `The DevMode element does not exist in the cache, try to insert it into the cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UniDrvUI::PerformJScriptDevmodeValidation(
        UniDrvUI *this,
        struct UniDrvUI::_COMMONINFO *a2,
        const struct _devicemodeW **a3,
        struct _devicemodeW **a4,
        _DWORD *a5,
        unsigned int *a6)
{
  unsigned __int16 *v9; // r15
  __int64 v10; // rax
  char v12; // di
  unsigned __int16 *v13; // r14
  char v14; // di
  int ProviderSchemaVersion; // esi
  struct IXMLDOMDocument2 *v16; // r13
  _QWORD *v17; // rbx
  int *v18; // r9
  int v19; // edx
  int v20; // r14d
  OLECHAR *v21; // rcx
  struct IXMLDOMElement **v22; // r8
  ATL::CRegObject *v23; // rcx
  const void *v24; // rbx
  unsigned int v25; // ecx
  const struct _devicemodeW *v26; // rax
  struct _devicemodeW *v27; // [rsp+28h] [rbp-89h]
  struct _devicemodeW *v28; // [rsp+28h] [rbp-89h]
  unsigned int uBytes; // [rsp+4Ch] [rbp-65h] BYREF
  unsigned int uBytes_4; // [rsp+50h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-59h] BYREF
  int v32; // [rsp+60h] [rbp-51h] BYREF
  _DWORD v33[3]; // [rsp+64h] [rbp-4Dh] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-41h] BYREF
  int v35; // [rsp+78h] [rbp-39h] BYREF
  void *Block; // [rsp+80h] [rbp-31h] BYREF
  _QWORD *v37; // [rsp+88h] [rbp-29h]
  unsigned int v38[2]; // [rsp+90h] [rbp-21h] BYREF
  struct IXMLDOMDocument2 *v39[2]; // [rsp+98h] [rbp-19h]
  __int64 v40; // [rsp+A8h] [rbp-9h]
  __int16 v41; // [rsp+B0h] [rbp-1h]
  int v42; // [rsp+B4h] [rbp+3h]
  struct IXMLDOMDocument2 *v43; // [rsp+B8h] [rbp+7h]
  __int64 v44; // [rsp+C0h] [rbp+Fh]
  unsigned int v47; // [rsp+120h] [rbp+6Fh]

  v47 = (unsigned int)a4;
  v44 = -2;
  v9 = 0;
  v33[0] = 0;
  v35 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::PerformJScriptDevmodeValidation", L"Enter");
  if ( !this )
    return 2147942487LL;
  v10 = *((_QWORD *)this + 6);
  if ( !v10 || !*(_QWORD *)(v10 + 32) )
    return 2147942487LL;
  if ( (*(_DWORD *)(v10 + 24) & 0x100000) == 0 )
    return 0;
  if ( (*((_DWORD *)this + 10) & 0x400000) != 0 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE");
    JSDevModeCacheInvalidate();
  }
  v12 = 0;
  Block = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::PerformJScriptDevmodeValidation",
    L"Attempt to check if the DevMode element exists in the current cache");
  if ( !(unsigned int)JSDevModeCacheFind(*((wchar_t **)this + 3), a2, *a3, (struct _devicemodeW **)&Block) )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"Current DevMode element exists in the current cache");
    v12 = 1;
  }
  uBytes = 0;
  pv = 0;
  v13 = (unsigned __int16 *)Block;
  if ( v12 )
  {
    ProviderSchemaVersion = 0;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"The DevMode element exists in the cache, set the return data value");
    v24 = v13;
    v25 = v13[34] + v13[35];
    uBytes = v25;
LABEL_57:
    if ( v47 != v25 )
    {
      if ( *a3 )
      {
        LocalFree((HLOCAL)*a3);
        v25 = uBytes;
      }
      v26 = (const struct _devicemodeW *)LocalAlloc(0, v25);
      *a3 = v26;
      if ( !v26 )
      {
        ProviderSchemaVersion = -2147024882;
        *a5 = 0;
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::PerformJScriptDevmodeValidation",
          L"Failed to allocate memory (hr = 0x%x)",
          2147942414LL);
        goto LABEL_65;
      }
      v25 = uBytes;
    }
    memcpy_0((void *)*a3, v24, v25);
    *a5 = uBytes;
    if ( a6 )
      *(_QWORD *)a6 = (char *)*a3 + (*a3)->dmSize;
    goto LABEL_65;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::PerformJScriptDevmodeValidation",
    L"Current DevMode element does not exist in the current cache");
  v14 = 0;
  ProviderSchemaVersion = CoInitializeEx(0, 0);
  if ( ProviderSchemaVersion < 0 )
  {
    if ( ProviderSchemaVersion == -2147417850 )
      ProviderSchemaVersion = 0;
  }
  else
  {
    v14 = 1;
  }
  v16 = 0;
  v43 = 0;
  *(_QWORD *)v38 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v34 = 0;
  v17 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180239588);
  v37 = v17;
  if ( v17 )
  {
    *v17 = &UniDrvUI::CPrintTicketProvider::`vftable';
    v17[1] = 0;
    v17[2] = 0;
    v17[3] = 0;
    v17[4] = 0;
    *((_DWORD *)v17 + 10) = 1;
    v17[6] = 0;
    v17[7] = 0;
    v17[9] = 0;
    v17[10] = 0;
    v17[11] = 0;
    _InterlockedIncrement(&UniDrvUI::g_cComponents);
  }
  else
  {
    v17 = 0;
  }
  v37 = v17;
  if ( !v17 )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v38);
    if ( v14 )
      CoUninitialize();
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v13 )
      operator delete(v13);
    return 2147500037LL;
  }
  if ( ProviderSchemaVersion >= 0 )
  {
    uBytes_4 = 0;
    ProviderSchemaVersion = UniDrvUI::GetProviderSchemaVersion(
                              a2,
                              v17,
                              (struct UniDrvUI::CPrintTicketProvider *)&uBytes_4,
                              v18);
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"Get the Provider Schema's version:  %d.",
      uBytes_4);
    if ( ProviderSchemaVersion >= 0 )
    {
      v32 = 0;
      *(_QWORD *)&v33[1] = 0;
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PerformJScriptDevmodeValidation",
        L"Bind with the printer");
      ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct UniDrvUI::_COMMONINFO *, _QWORD, int *, _DWORD *, int *, _DWORD *))(*v17 + 32LL))(
                                v17,
                                a2,
                                uBytes_4,
                                &v35,
                                v33,
                                &v32,
                                &v33[1]);
      if ( *(_QWORD *)&v33[1] )
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::PerformJScriptDevmodeValidation",
          L"Release any namespaces the driver provided");
        uBytes_4 = 0;
        v19 = v32;
        if ( v32 > 0 )
        {
          v20 = uBytes_4;
          do
          {
            v21 = *(OLECHAR **)(*(_QWORD *)&v33[1] + 8LL * v20);
            if ( v21 )
            {
              SysFreeString(v21);
              v19 = v32;
            }
            ++v20;
          }
          while ( v20 < v19 );
          v13 = (unsigned __int16 *)Block;
        }
        CoTaskMemFree(*(LPVOID *)&v33[1]);
      }
      if ( ProviderSchemaVersion >= 0 )
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::PerformJScriptDevmodeValidation",
          L"Try retrieving the driver's URI from the config file");
        v34 = 0;
        ProviderSchemaVersion = UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                                  (UniDrvUI::CPrintTicketProvider *)v17,
                                  &v34);
        if ( ProviderSchemaVersion < 0
          || (ProviderSchemaVersion = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
                                        (NPrintTicketUtil::CPrintTicketWrapper *)v38,
                                        (struct IXMLDOMDocument2 **)L"psf:PrintTicket",
                                        v22),
              ProviderSchemaVersion < 0) )
        {
          v9 = v34;
        }
        else
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
            "UniDrvUI::PerformJScriptDevmodeValidation",
            L"Convert the public portion via the shim");
          v9 = v34;
          LODWORD(v27) = v33[0];
          ProviderSchemaVersion = publicdm::PublicDevmodeToJobTicket(
                                    a2,
                                    *((void **)this + 3),
                                    v34,
                                    (*a3)->dmDeviceName,
                                    v27,
                                    (__int64)v38);
          if ( ProviderSchemaVersion >= 0 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
              "UniDrvUI::PerformJScriptDevmodeValidation",
              L"Get print ticket XML");
            if ( v39[0] )
            {
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v39[0]->lpVtbl->AddRef)(v39[0]);
              v16 = v39[0];
              v43 = v39[0];
              DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                "UniDrvUI::PerformJScriptDevmodeValidation",
                L"Invoke the providers conversion method to convert driver-specific converion");
              ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, struct IXMLDOMDocument2 *))(*v17 + 56LL))(
                                        v17,
                                        v47,
                                        *a3,
                                        v16);
              if ( ProviderSchemaVersion >= 0 )
              {
                DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                  "UniDrvUI::PerformJScriptDevmodeValidation",
                  L"Invoking the JScript ValidatePrintTicket");
                ProviderSchemaVersion = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(
                                          (UniDrvUI::CPrintTicketProvider *)v17,
                                          v16);
                if ( ProviderSchemaVersion >= 0 )
                {
                  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                    "UniDrvUI::PerformJScriptDevmodeValidation",
                    L"Filter print ticket");
                  ProviderSchemaVersion = ATL::CRegObject::Release(v23);
                  if ( ProviderSchemaVersion >= 0 )
                  {
                    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                      "UniDrvUI::PerformJScriptDevmodeValidation",
                      L"Convert the print ticket to DevMode");
                    ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct IXMLDOMDocument2 *, _QWORD, _QWORD, unsigned int *, LPVOID *))(*v17 + 48LL))(
                                              v17,
                                              v16,
                                              v47,
                                              *a3,
                                              &uBytes,
                                              &pv);
                    if ( ProviderSchemaVersion >= 0 )
                    {
                      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                        "UniDrvUI::PerformJScriptDevmodeValidation",
                        L"Invoke public shim to convert JobTicket to public DevMode");
                      LODWORD(v28) = v33[0];
                      ProviderSchemaVersion = publicdm::JobTicketToPublicDevmode(
                                                a2,
                                                v38,
                                                *((const WCHAR **)this + 3),
                                                v9,
                                                v28->dmDeviceName,
                                                (DEVMODEW *)pv);
                    }
                  }
                }
              }
            }
            else
            {
              ProviderSchemaVersion = -2147467259;
            }
          }
        }
      }
    }
  }
  if ( v9 )
    SysFreeString(v9);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v38);
  (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
  if ( v16 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v16->lpVtbl->Release)(v16);
  if ( v14 )
    CoUninitialize();
  if ( ProviderSchemaVersion >= 0 )
  {
    v24 = pv;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"The DevMode element does not exist in the cache, try to insert it into the cache");
    JSDevModeCacheInsert(*((unsigned __int16 **)this + 3), a2, *a3, (struct _devicemodeW *)pv, uBytes);
    v25 = uBytes;
    goto LABEL_57;
  }
LABEL_65:
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::PerformJScriptDevmodeValidation",
    L"Exit with (hr: 0x%x).",
    (unsigned int)ProviderSchemaVersion);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v13 )
    operator delete(v13);
  return (unsigned int)ProviderSchemaVersion;
}

```

## disassembly

```asm
0x180114e38  mov     rax, rsp
0x180114e3b  mov     [rax+20h], r9d
0x180114e3f  mov     [rax+10h], rdx
0x180114e43  mov     [rax+8], rcx
0x180114e47  push    rbp
0x180114e48  push    rsi
0x180114e49  push    rdi
0x180114e4a  push    r12
0x180114e4c  push    r13
0x180114e4e  push    r14
0x180114e50  push    r15
0x180114e52  lea     rbp, [rax-4Fh]
0x180114e56  sub     rsp, 0C0h
0x180114e5d  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x180114e65  mov     [rax+18h], rbx
0x180114e69  mov     r12, r8
0x180114e6c  mov     rsi, rdx
0x180114e6f  mov     rbx, rcx
0x180114e72  xor     r15d, r15d
0x180114e75  mov     dword ptr [rbp+47h+var_94], r15d
0x180114e79  mov     [rbp+47h+var_80], r15d
0x180114e7d  lea     rdx, aEnter_0; "Enter"
0x180114e84  lea     r13, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180114e8b  mov     rcx, r13; char *
0x180114e8e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114e93  test    rbx, rbx
0x180114e96  jz      loc_1801154E6
0x180114e9c  mov     rax, [rbx+30h]
0x180114ea0  test    rax, rax
0x180114ea3  jz      loc_1801154E6
0x180114ea9  cmp     [rax+20h], r15
0x180114ead  jz      loc_1801154E6
0x180114eb3  test    dword ptr [rax+18h], 100000h
0x180114eba  jnz     short loc_180114EC3
0x180114ebc  xor     eax, eax
0x180114ebe  jmp     loc_1801154EB
0x180114ec3  test    dword ptr [rbx+28h], 400000h
0x180114eca  jz      short loc_180114EE0
0x180114ecc  lea     rdx, aClearingTheCac; "Clearing the cache because the flag is "...
0x180114ed3  mov     rcx, r13; char *
0x180114ed6  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114edb  call    ?JSDevModeCacheInvalidate@@YAXXZ; JSDevModeCacheInvalidate(void)
0x180114ee0  mov     dil, r15b
0x180114ee3  mov     [rbp+47h+Block], r15
0x180114ee7  lea     rdx, aAttemptToCheck; "Attempt to check if the DevMode element"...
0x180114eee  mov     rcx, r13; char *
0x180114ef1  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114ef6  lea     r9, [rbp+47h+Block]; struct _devicemodeW **
0x180114efa  mov     r8, [r12]; struct _devicemodeW *
0x180114efe  mov     rdx, rsi; void *
0x180114f01  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180114f05  call    ?JSDevModeCacheFind@@YAJPEBGQEAXPEBU_devicemodeW@@PEAPEAU1@@Z; JSDevModeCacheFind(ushort const *,void * const,_devicemodeW const *,_devicemodeW * *)
0x180114f0a  test    eax, eax
0x180114f0c  jnz     short loc_180114F20
0x180114f0e  lea     rdx, aCurrentDevmode; "Current DevMode element exists in the c"...
0x180114f15  mov     rcx, r13; char *
0x180114f18  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114f1d  mov     dil, 1
0x180114f20  mov     dword ptr [rbp+47h+uBytes], r15d
0x180114f24  mov     [rbp+47h+pv], r15
0x180114f28  mov     r14, [rbp+47h+Block]
0x180114f2c  mov     rcx, r13; char *
0x180114f2f  test    dil, dil
0x180114f32  jnz     loc_1801153FB
0x180114f38  lea     rdx, aCurrentDevmode_0; "Current DevMode element does not exist "...
0x180114f3f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114f44  mov     dil, r15b
0x180114f47  mov     [rbp+47h+var_B0], r15b
0x180114f4b  xor     edx, edx; dwCoInit
0x180114f4d  xor     ecx, ecx; pvReserved
0x180114f4f  call    cs:__imp_CoInitializeEx
0x180114f56  nop     dword ptr [rax+rax+00h]
0x180114f5b  mov     esi, eax
0x180114f5d  test    eax, eax
0x180114f5f  js      short loc_180114F6A
0x180114f61  mov     dil, 1
0x180114f64  mov     [rbp+47h+var_B0], dil
0x180114f68  jmp     short loc_180114F74
0x180114f6a  cmp     esi, 80010106h
0x180114f70  cmovz   esi, r15d
0x180114f74  mov     r13, r15
0x180114f77  mov     [rbp+47h+var_40], r15
0x180114f7b  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180114f82  mov     qword ptr [rbp+47h+var_68], rax
0x180114f86  xorps   xmm0, xmm0
0x180114f89  movdqu  xmmword ptr [rbp+47h+var_60], xmm0
0x180114f8e  mov     [rbp+47h+var_50], r15
0x180114f92  mov     [rbp+47h+var_48], r15w
0x180114f97  mov     [rbp+47h+var_44], r15d
0x180114f9b  mov     [rbp+47h+var_88], r15
0x180114f9f  lea     rdx, qword_180239588; struct std::nothrow_t *
0x180114fa6  mov     ecx, 60h ; '`'; unsigned __int64
0x180114fab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180114fb0  mov     rbx, rax
0x180114fb3  mov     [rbp+47h+var_70], rax
0x180114fb7  test    rax, rax
0x180114fba  jz      short loc_180115021
0x180114fbc  lea     rax, ??_7CPrintTicketProvider@UniDrvUI@@6B@; const UniDrvUI::CPrintTicketProvider::`vftable'
0x180114fc3  mov     [rbx], rax
0x180114fc6  mov     qword ptr [rbx+8], 0
0x180114fce  mov     qword ptr [rbx+10h], 0
0x180114fd6  mov     qword ptr [rbx+18h], 0
0x180114fde  mov     qword ptr [rbx+20h], 0
0x180114fe6  mov     dword ptr [rbx+28h], 1
0x180114fed  mov     qword ptr [rbx+30h], 0
0x180114ff5  mov     qword ptr [rbx+38h], 0
0x180114ffd  mov     qword ptr [rbx+48h], 0
0x180115005  mov     qword ptr [rbx+50h], 0
0x18011500d  mov     qword ptr [rbx+58h], 0
0x180115015  lock inc cs:?g_cComponents@UniDrvUI@@3JA; long UniDrvUI::g_cComponents
0x18011501c  test    rbx, rbx
0x18011501f  jnz     short loc_180115023
0x180115021  xor     ebx, ebx
0x180115023  mov     [rbp+47h+var_70], rbx
0x180115027  test    rbx, rbx
0x18011502a  jnz     short loc_18011507C
0x18011502c  lea     rcx, [rbp+47h+var_68]; this
0x180115030  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180115035  nop
0x180115036  test    dil, dil
0x180115039  jz      short loc_180115048
0x18011503b  call    cs:__imp_CoUninitialize
0x180115042  nop     dword ptr [rax+rax+00h]
0x180115047  nop
0x180115048  mov     rcx, [rbp+47h+pv]; pv
0x18011504c  test    rcx, rcx
0x18011504f  jz      short loc_180115065
0x180115051  call    cs:__imp_CoTaskMemFree
0x180115058  nop     dword ptr [rax+rax+00h]
0x18011505d  mov     [rbp+47h+pv], 0
0x180115065  test    r14, r14
0x180115068  jz      short loc_180115072
0x18011506a  mov     rcx, r14; Block
0x18011506d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180115072  mov     eax, 80004005h
0x180115077  jmp     loc_1801154EB
0x18011507c  test    esi, esi
0x18011507e  js      loc_18011535B
0x180115084  mov     dword ptr [rbp+47h+uBytes+4], 0
0x18011508b  lea     r8, [rbp+47h+uBytes+4]; struct UniDrvUI::CPrintTicketProvider *
0x18011508f  mov     rdx, rbx; void *
0x180115092  mov     rcx, [rbp+47h+arg_8]; this
0x180115096  call    ?GetProviderSchemaVersion@UniDrvUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; UniDrvUI::GetProviderSchemaVersion(void *,UniDrvUI::CPrintTicketProvider *,int *)
0x18011509b  mov     esi, eax
0x18011509d  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x1801150a1  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x1801150a8  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801150af  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801150b4  test    esi, esi
0x1801150b6  js      loc_18011535B
0x1801150bc  mov     [rbp+47h+var_98], 0
0x1801150c3  mov     qword ptr [rbp+47h+var_94+4], 0
0x1801150cb  lea     rdx, aBindWithThePri; "Bind with the printer"
0x1801150d2  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801150d9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801150de  mov     rax, [rbx]
0x1801150e1  lea     rcx, [rbp+47h+var_94+4]
0x1801150e5  mov     [rsp+30h], rcx; struct _devicemodeW *
0x1801150ea  lea     rcx, [rbp+47h+var_98]
0x1801150ee  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x1801150f3  lea     rcx, [rbp+47h+var_94]
0x1801150f7  mov     [rsp+0F0h+var_D0], rcx
0x1801150fc  lea     r9, [rbp+47h+var_80]
0x180115100  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x180115104  mov     rdx, [rbp+47h+arg_8]
0x180115108  mov     rcx, rbx
0x18011510b  mov     rax, [rax+20h]
0x18011510f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115114  mov     esi, eax
0x180115116  cmp     qword ptr [rbp+47h+var_94+4], 0
0x18011511b  jz      short loc_18011517D
0x18011511d  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x180115124  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x18011512b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115130  mov     dword ptr [rbp+47h+uBytes+4], 0
0x180115137  mov     edx, [rbp+47h+var_98]
0x18011513a  test    edx, edx
0x18011513c  jle     short loc_18011516D
0x18011513e  mov     r14d, dword ptr [rbp+47h+uBytes+4]
0x180115142  movsxd  rcx, r14d
0x180115145  mov     rax, qword ptr [rbp+47h+var_94+4]
0x180115149  mov     rcx, [rax+rcx*8]; bstrString
0x18011514d  test    rcx, rcx
0x180115150  jz      short loc_180115161
0x180115152  call    cs:__imp_SysFreeString
0x180115159  nop     dword ptr [rax+rax+00h]
0x18011515e  mov     edx, [rbp+47h+var_98]
0x180115161  inc     r14d
0x180115164  cmp     r14d, edx
0x180115167  jl      short loc_180115142
0x180115169  mov     r14, [rbp+47h+Block]
0x18011516d  mov     rcx, qword ptr [rbp+47h+var_94+4]; pv
0x180115171  call    cs:__imp_CoTaskMemFree
0x180115178  nop     dword ptr [rax+rax+00h]
0x18011517d  test    esi, esi
0x18011517f  js      loc_18011535B
0x180115185  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x18011518c  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180115193  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115198  mov     [rbp+47h+var_88], 0
0x1801151a0  lea     rdx, [rbp+47h+var_88]; unsigned __int16 **
0x1801151a4  mov     rcx, rbx; this
0x1801151a7  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@UniDrvUI@@QEAAJPEAPEAG@Z; UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x1801151ac  mov     esi, eax
0x1801151ae  test    eax, eax
0x1801151b0  js      loc_180115357
0x1801151b6  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x1801151bd  lea     rcx, [rbp+47h+var_68]; this
0x1801151c1  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x1801151c6  mov     esi, eax
0x1801151c8  test    eax, eax
0x1801151ca  js      loc_180115357
0x1801151d0  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x1801151d7  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801151de  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801151e3  mov     eax, dword ptr [rbp+47h+var_94]
0x1801151e6  mov     r15, [rbp+47h+var_88]
0x1801151ea  lea     rcx, [rbp+47h+var_68]
0x1801151ee  mov     qword ptr [rsp+0F0h+var_C8], rcx; unsigned int
0x1801151f3  mov     dword ptr [rsp+0F0h+var_D0], eax; struct _devicemodeW *
0x1801151f7  mov     r9, [r12]; unsigned __int16 *
0x1801151fb  mov     r8, r15; unsigned __int16 *
0x1801151fe  mov     rdx, [rbp+47h+arg_0]
0x180115202  mov     rdx, [rdx+18h]; void *
0x180115206  mov     rcx, [rbp+47h+arg_8]; this
0x18011520a  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18011520f  mov     esi, eax
0x180115211  test    eax, eax
0x180115213  js      loc_18011535B
0x180115219  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x180115220  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180115227  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011522c  mov     rcx, [rbp+47h+var_60]
0x180115230  test    rcx, rcx
0x180115233  jnz     short loc_18011523F
0x180115235  mov     esi, 80004005h
0x18011523a  jmp     loc_18011535B
0x18011523f  mov     rax, [rcx]
0x180115242  mov     rax, [rax+8]
0x180115246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011524b  mov     r13, [rbp+47h+var_60]
0x18011524f  mov     [rbp+47h+var_40], r13
0x180115253  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x18011525a  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180115261  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115266  mov     rax, [rbx]
0x180115269  mov     r9, r13
0x18011526c  mov     r8, [r12]
0x180115270  mov     edx, [rbp+47h+arg_18]
0x180115273  mov     rcx, rbx
0x180115276  mov     rax, [rax+38h]
0x18011527a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011527f  mov     esi, eax
0x180115281  test    eax, eax
0x180115283  js      loc_18011535B
0x180115289  lea     rdx, aInvokingTheJsc; "Invoking the JScript ValidatePrintTicke"...
0x180115290  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180115297  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011529c  mov     rdx, r13; struct IXMLDOMDocument2 *
0x18011529f  mov     rcx, rbx; this
0x1801152a2  call    ?PerformJScriptValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@QEAAJPEAUIXMLDOMDocument2@@@Z; UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(IXMLDOMDocument2 *)
0x1801152a7  mov     esi, eax
0x1801152a9  test    eax, eax
0x1801152ab  js      loc_18011535B
0x1801152b1  lea     rdx, aFilterPrintTic; "Filter print ticket"
0x1801152b8  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801152bf  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801152c4  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1801152c9  mov     esi, eax
0x1801152cb  test    eax, eax
0x1801152cd  js      loc_18011535B
0x1801152d3  lea     rdx, aConvertThePrin; "Convert the print ticket to DevMode"
0x1801152da  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801152e1  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801152e6  mov     rax, [rbx]
0x1801152e9  lea     rcx, [rbp+47h+pv]
0x1801152ed  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x1801152f2  lea     rcx, [rbp+47h+uBytes]
0x1801152f6  mov     [rsp+0F0h+var_D0], rcx
0x1801152fb  mov     r9, [r12]
0x1801152ff  mov     r8d, [rbp+47h+arg_18]
0x180115303  mov     rdx, r13
0x180115306  mov     rcx, rbx
0x180115309  mov     rax, [rax+30h]
0x18011530d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115312  mov     esi, eax
0x180115314  test    eax, eax
0x180115316  js      short loc_18011535B
0x180115318  lea     rdx, aInvokePublicSh; "Invoke public shim to convert JobTicket"...
0x18011531f  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180115326  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011532b  mov     rax, [rbp+47h+pv]
0x18011532f  mov     ecx, dword ptr [rbp+47h+var_94]
0x180115332  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned int
0x180115337  mov     dword ptr [rsp+0F0h+var_D0], ecx; unsigned __int16 *
0x18011533b  mov     r9, r15; unsigned __int16 *
0x18011533e  mov     rax, [rbp+47h+arg_0]
0x180115342  mov     r8, [rax+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180115346  lea     rdx, [rbp+47h+var_68]; void *
0x18011534a  mov     rcx, [rbp+47h+arg_8]; this
  ... truncated ...
```
