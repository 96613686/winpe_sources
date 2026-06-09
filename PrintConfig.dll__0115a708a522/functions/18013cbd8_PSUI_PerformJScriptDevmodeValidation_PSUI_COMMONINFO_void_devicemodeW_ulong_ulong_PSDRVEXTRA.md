# PSUI::PerformJScriptDevmodeValidation(PSUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)

- ea: `0x18013cbd8`
- end: `0x18013d2a7`
- name: `?PerformJScriptDevmodeValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z`
- size: `1743`
- prototype: `__int64 __fastcall(PSUI *this, struct PSUI::_COMMONINFO *, const struct _devicemodeW **, struct _devicemodeW **, _DWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18013b3d4`
- `0x18013d2b0`

## callees

- `0x180003430`
- `0x180003c64`
- `0x1800192f0`
- `0x180034084`
- `0x18003411c`
- `0x1800341bc`
- `0x1800ee8cc`
- `0x1800fdba0`
- `0x1800ff438`
- `0x1800ffc98`
- `0x180105360`
- `0x180107214`
- `0x180108e2c`
- `0x18012ec04`
- `0x18013bccc`
- `0x18013cbd8`
- `0x1801b56bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18013d1cb`
- `KERNEL32!LocalFree` at `0x18013d1cb`
- `KERNEL32!LocalAlloc` at `0x18013d1de`
- `KERNEL32!LocalAlloc` at `0x18013d1de`
- `OLEAUT32!__imp_SysFreeString` at `0x18013cef2`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d103`
- `OLEAUT32!__imp_SysFreeString` at `0x18013cef2`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d103`
- `ole32!CoInitializeEx` at `0x18013ccef`
- `ole32!CoInitializeEx` at `0x18013ccef`
- `ole32!CoUninitialize` at `0x18013cddb`
- `ole32!CoUninitialize` at `0x18013d148`
- `ole32!CoUninitialize` at `0x18013cddb`
- `ole32!CoUninitialize` at `0x18013d148`
- `ole32!CoTaskMemFree` at `0x18013cdf1`
- `ole32!CoTaskMemFree` at `0x18013cf11`
- `ole32!CoTaskMemFree` at `0x18013d265`
- `ole32!CoTaskMemFree` at `0x18013cdf1`
- `ole32!CoTaskMemFree` at `0x18013cf11`
- `ole32!CoTaskMemFree` at `0x18013d265`

## string_xrefs

- `0x18013cf25`: `Try retrieving the driver's URI from the config file`
- `0x18013cc87`: `Attempt to check if the DevMode element exists in the current cache`
- `0x18013cc6c`: `Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE`
- `0x18013ccd8`: `Current DevMode element does not exist in the current cache`
- `0x18013ccae`: `Current DevMode element exists in the current cache`
- `0x18013d19e`: `The DevMode element exists in the cache, set the return data value`
- `0x18013cfb9`: `Get print ticket XML`
- `0x18013d160`: `The DevMode element does not exist in the cache, try to insert it into the cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PSUI::PerformJScriptDevmodeValidation(
        PSUI *this,
        struct PSUI::_COMMONINFO *a2,
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
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PerformJScriptDevmodeValidation", L"Enter");
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
      "PSUI::PerformJScriptDevmodeValidation",
      L"Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE");
    JSDevModeCacheInvalidate();
  }
  v12 = 0;
  Block = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::PerformJScriptDevmodeValidation",
    L"Attempt to check if the DevMode element exists in the current cache");
  if ( !(unsigned int)JSDevModeCacheFind(*((wchar_t **)this + 3), a2, *a3, (struct _devicemodeW **)&Block) )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PerformJScriptDevmodeValidation",
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
      "PSUI::PerformJScriptDevmodeValidation",
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
          "PSUI::PerformJScriptDevmodeValidation",
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
    "PSUI::PerformJScriptDevmodeValidation",
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
  v17 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180239F68);
  v37 = v17;
  if ( v17 )
  {
    *v17 = &PSUI::CPrintTicketProvider::`vftable';
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
    _InterlockedIncrement(&PSUI::g_cComponents);
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
    ProviderSchemaVersion = PSUI::GetProviderSchemaVersion(a2, v17, (struct PSUI::CPrintTicketProvider *)&uBytes_4, v18);
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PerformJScriptDevmodeValidation",
      L"Get the Provider Schema's version:  %d.",
      uBytes_4);
    if ( ProviderSchemaVersion >= 0 )
    {
      v32 = 0;
      *(_QWORD *)&v33[1] = 0;
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PerformJScriptDevmodeValidation", L"Bind with the printer");
      ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct PSUI::_COMMONINFO *, _QWORD, int *, _DWORD *, int *, _DWORD *))(*v17 + 32LL))(
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
          "PSUI::PerformJScriptDevmodeValidation",
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
          "PSUI::PerformJScriptDevmodeValidation",
          L"Try retrieving the driver's URI from the config file");
        v34 = 0;
        ProviderSchemaVersion = PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                                  (PSUI::CPrintTicketProvider *)v17,
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
            "PSUI::PerformJScriptDevmodeValidation",
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
              "PSUI::PerformJScriptDevmodeValidation",
              L"Get print ticket XML");
            if ( v39[0] )
            {
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v39[0]->lpVtbl->AddRef)(v39[0]);
              v16 = v39[0];
              v43 = v39[0];
              DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                "PSUI::PerformJScriptDevmodeValidation",
                L"Invoke the providers conversion method to convert driver-specific converion");
              ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, struct IXMLDOMDocument2 *))(*v17 + 56LL))(
                                        v17,
                                        v47,
                                        *a3,
                                        v16);
              if ( ProviderSchemaVersion >= 0 )
              {
                DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                  "PSUI::PerformJScriptDevmodeValidation",
                  L"Invoking the JScript ValidatePrintTicket");
                ProviderSchemaVersion = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(
                                          (UniDrvUI::CPrintTicketProvider *)v17,
                                          v16);
                if ( ProviderSchemaVersion >= 0 )
                {
                  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                    "PSUI::PerformJScriptDevmodeValidation",
                    L"Filter print ticket");
                  ProviderSchemaVersion = ATL::CRegObject::Release(v23);
                  if ( ProviderSchemaVersion >= 0 )
                  {
                    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                      "PSUI::PerformJScriptDevmodeValidation",
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
                        "PSUI::PerformJScriptDevmodeValidation",
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
      "PSUI::PerformJScriptDevmodeValidation",
      L"The DevMode element does not exist in the cache, try to insert it into the cache");
    JSDevModeCacheInsert(*((unsigned __int16 **)this + 3), a2, *a3, (struct _devicemodeW *)pv, uBytes);
    v25 = uBytes;
    goto LABEL_57;
  }
LABEL_65:
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::PerformJScriptDevmodeValidation",
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
0x18013cbd8  mov     rax, rsp
0x18013cbdb  mov     [rax+20h], r9d
0x18013cbdf  mov     [rax+10h], rdx
0x18013cbe3  mov     [rax+8], rcx
0x18013cbe7  push    rbp
0x18013cbe8  push    rsi
0x18013cbe9  push    rdi
0x18013cbea  push    r12
0x18013cbec  push    r13
0x18013cbee  push    r14
0x18013cbf0  push    r15
0x18013cbf2  lea     rbp, [rax-4Fh]
0x18013cbf6  sub     rsp, 0C0h
0x18013cbfd  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x18013cc05  mov     [rax+18h], rbx
0x18013cc09  mov     r12, r8
0x18013cc0c  mov     rsi, rdx
0x18013cc0f  mov     rbx, rcx
0x18013cc12  xor     r15d, r15d
0x18013cc15  mov     dword ptr [rbp+47h+var_94], r15d
0x18013cc19  mov     [rbp+47h+var_80], r15d
0x18013cc1d  lea     rdx, aEnter_0; "Enter"
0x18013cc24  lea     r13, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013cc2b  mov     rcx, r13; char *
0x18013cc2e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cc33  test    rbx, rbx
0x18013cc36  jz      loc_18013D286
0x18013cc3c  mov     rax, [rbx+30h]
0x18013cc40  test    rax, rax
0x18013cc43  jz      loc_18013D286
0x18013cc49  cmp     [rax+20h], r15
0x18013cc4d  jz      loc_18013D286
0x18013cc53  test    dword ptr [rax+18h], 100000h
0x18013cc5a  jnz     short loc_18013CC63
0x18013cc5c  xor     eax, eax
0x18013cc5e  jmp     loc_18013D28B
0x18013cc63  test    dword ptr [rbx+28h], 400000h
0x18013cc6a  jz      short loc_18013CC80
0x18013cc6c  lea     rdx, aClearingTheCac; "Clearing the cache because the flag is "...
0x18013cc73  mov     rcx, r13; char *
0x18013cc76  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cc7b  call    ?JSDevModeCacheInvalidate@@YAXXZ; JSDevModeCacheInvalidate(void)
0x18013cc80  mov     dil, r15b
0x18013cc83  mov     [rbp+47h+Block], r15
0x18013cc87  lea     rdx, aAttemptToCheck; "Attempt to check if the DevMode element"...
0x18013cc8e  mov     rcx, r13; char *
0x18013cc91  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cc96  lea     r9, [rbp+47h+Block]; struct _devicemodeW **
0x18013cc9a  mov     r8, [r12]; struct _devicemodeW *
0x18013cc9e  mov     rdx, rsi; void *
0x18013cca1  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18013cca5  call    ?JSDevModeCacheFind@@YAJPEBGQEAXPEBU_devicemodeW@@PEAPEAU1@@Z; JSDevModeCacheFind(ushort const *,void * const,_devicemodeW const *,_devicemodeW * *)
0x18013ccaa  test    eax, eax
0x18013ccac  jnz     short loc_18013CCC0
0x18013ccae  lea     rdx, aCurrentDevmode; "Current DevMode element exists in the c"...
0x18013ccb5  mov     rcx, r13; char *
0x18013ccb8  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013ccbd  mov     dil, 1
0x18013ccc0  mov     dword ptr [rbp+47h+uBytes], r15d
0x18013ccc4  mov     [rbp+47h+pv], r15
0x18013ccc8  mov     r14, [rbp+47h+Block]
0x18013cccc  mov     rcx, r13; char *
0x18013cccf  test    dil, dil
0x18013ccd2  jnz     loc_18013D19B
0x18013ccd8  lea     rdx, aCurrentDevmode_0; "Current DevMode element does not exist "...
0x18013ccdf  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cce4  mov     dil, r15b
0x18013cce7  mov     [rbp+47h+var_B0], r15b
0x18013cceb  xor     edx, edx; dwCoInit
0x18013cced  xor     ecx, ecx; pvReserved
0x18013ccef  call    cs:__imp_CoInitializeEx
0x18013ccf6  nop     dword ptr [rax+rax+00h]
0x18013ccfb  mov     esi, eax
0x18013ccfd  test    eax, eax
0x18013ccff  js      short loc_18013CD0A
0x18013cd01  mov     dil, 1
0x18013cd04  mov     [rbp+47h+var_B0], dil
0x18013cd08  jmp     short loc_18013CD14
0x18013cd0a  cmp     esi, 80010106h
0x18013cd10  cmovz   esi, r15d
0x18013cd14  mov     r13, r15
0x18013cd17  mov     [rbp+47h+var_40], r15
0x18013cd1b  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18013cd22  mov     qword ptr [rbp+47h+var_68], rax
0x18013cd26  xorps   xmm0, xmm0
0x18013cd29  movdqu  xmmword ptr [rbp+47h+var_60], xmm0
0x18013cd2e  mov     [rbp+47h+var_50], r15
0x18013cd32  mov     [rbp+47h+var_48], r15w
0x18013cd37  mov     [rbp+47h+var_44], r15d
0x18013cd3b  mov     [rbp+47h+var_88], r15
0x18013cd3f  lea     rdx, qword_180239F68; struct std::nothrow_t *
0x18013cd46  mov     ecx, 60h ; '`'; unsigned __int64
0x18013cd4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18013cd50  mov     rbx, rax
0x18013cd53  mov     [rbp+47h+var_70], rax
0x18013cd57  test    rax, rax
0x18013cd5a  jz      short loc_18013CDC1
0x18013cd5c  lea     rax, ??_7CPrintTicketProvider@PSUI@@6B@; const PSUI::CPrintTicketProvider::`vftable'
0x18013cd63  mov     [rbx], rax
0x18013cd66  mov     qword ptr [rbx+8], 0
0x18013cd6e  mov     qword ptr [rbx+10h], 0
0x18013cd76  mov     qword ptr [rbx+18h], 0
0x18013cd7e  mov     qword ptr [rbx+20h], 0
0x18013cd86  mov     dword ptr [rbx+28h], 1
0x18013cd8d  mov     qword ptr [rbx+30h], 0
0x18013cd95  mov     qword ptr [rbx+38h], 0
0x18013cd9d  mov     qword ptr [rbx+48h], 0
0x18013cda5  mov     qword ptr [rbx+50h], 0
0x18013cdad  mov     qword ptr [rbx+58h], 0
0x18013cdb5  lock inc cs:?g_cComponents@PSUI@@3JA; long PSUI::g_cComponents
0x18013cdbc  test    rbx, rbx
0x18013cdbf  jnz     short loc_18013CDC3
0x18013cdc1  xor     ebx, ebx
0x18013cdc3  mov     [rbp+47h+var_70], rbx
0x18013cdc7  test    rbx, rbx
0x18013cdca  jnz     short loc_18013CE1C
0x18013cdcc  lea     rcx, [rbp+47h+var_68]; this
0x18013cdd0  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18013cdd5  nop
0x18013cdd6  test    dil, dil
0x18013cdd9  jz      short loc_18013CDE8
0x18013cddb  call    cs:__imp_CoUninitialize
0x18013cde2  nop     dword ptr [rax+rax+00h]
0x18013cde7  nop
0x18013cde8  mov     rcx, [rbp+47h+pv]; pv
0x18013cdec  test    rcx, rcx
0x18013cdef  jz      short loc_18013CE05
0x18013cdf1  call    cs:__imp_CoTaskMemFree
0x18013cdf8  nop     dword ptr [rax+rax+00h]
0x18013cdfd  mov     [rbp+47h+pv], 0
0x18013ce05  test    r14, r14
0x18013ce08  jz      short loc_18013CE12
0x18013ce0a  mov     rcx, r14; Block
0x18013ce0d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013ce12  mov     eax, 80004005h
0x18013ce17  jmp     loc_18013D28B
0x18013ce1c  test    esi, esi
0x18013ce1e  js      loc_18013D0FB
0x18013ce24  mov     dword ptr [rbp+47h+uBytes+4], 0
0x18013ce2b  lea     r8, [rbp+47h+uBytes+4]; struct PSUI::CPrintTicketProvider *
0x18013ce2f  mov     rdx, rbx; void *
0x18013ce32  mov     rcx, [rbp+47h+arg_8]; this
0x18013ce36  call    ?GetProviderSchemaVersion@PSUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; PSUI::GetProviderSchemaVersion(void *,PSUI::CPrintTicketProvider *,int *)
0x18013ce3b  mov     esi, eax
0x18013ce3d  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x18013ce41  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x18013ce48  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013ce4f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013ce54  test    esi, esi
0x18013ce56  js      loc_18013D0FB
0x18013ce5c  mov     [rbp+47h+var_98], 0
0x18013ce63  mov     qword ptr [rbp+47h+var_94+4], 0
0x18013ce6b  lea     rdx, aBindWithThePri; "Bind with the printer"
0x18013ce72  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013ce79  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013ce7e  mov     rax, [rbx]
0x18013ce81  lea     rcx, [rbp+47h+var_94+4]
0x18013ce85  mov     [rsp+30h], rcx; struct _devicemodeW *
0x18013ce8a  lea     rcx, [rbp+47h+var_98]
0x18013ce8e  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x18013ce93  lea     rcx, [rbp+47h+var_94]
0x18013ce97  mov     [rsp+0F0h+var_D0], rcx
0x18013ce9c  lea     r9, [rbp+47h+var_80]
0x18013cea0  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x18013cea4  mov     rdx, [rbp+47h+arg_8]
0x18013cea8  mov     rcx, rbx
0x18013ceab  mov     rax, [rax+20h]
0x18013ceaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ceb4  mov     esi, eax
0x18013ceb6  cmp     qword ptr [rbp+47h+var_94+4], 0
0x18013cebb  jz      short loc_18013CF1D
0x18013cebd  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x18013cec4  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013cecb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013ced0  mov     dword ptr [rbp+47h+uBytes+4], 0
0x18013ced7  mov     edx, [rbp+47h+var_98]
0x18013ceda  test    edx, edx
0x18013cedc  jle     short loc_18013CF0D
0x18013cede  mov     r14d, dword ptr [rbp+47h+uBytes+4]
0x18013cee2  movsxd  rcx, r14d
0x18013cee5  mov     rax, qword ptr [rbp+47h+var_94+4]
0x18013cee9  mov     rcx, [rax+rcx*8]; bstrString
0x18013ceed  test    rcx, rcx
0x18013cef0  jz      short loc_18013CF01
0x18013cef2  call    cs:__imp_SysFreeString
0x18013cef9  nop     dword ptr [rax+rax+00h]
0x18013cefe  mov     edx, [rbp+47h+var_98]
0x18013cf01  inc     r14d
0x18013cf04  cmp     r14d, edx
0x18013cf07  jl      short loc_18013CEE2
0x18013cf09  mov     r14, [rbp+47h+Block]
0x18013cf0d  mov     rcx, qword ptr [rbp+47h+var_94+4]; pv
0x18013cf11  call    cs:__imp_CoTaskMemFree
0x18013cf18  nop     dword ptr [rax+rax+00h]
0x18013cf1d  test    esi, esi
0x18013cf1f  js      loc_18013D0FB
0x18013cf25  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x18013cf2c  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013cf33  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cf38  mov     [rbp+47h+var_88], 0
0x18013cf40  lea     rdx, [rbp+47h+var_88]; unsigned __int16 **
0x18013cf44  mov     rcx, rbx; this
0x18013cf47  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@PSUI@@QEAAJPEAPEAG@Z; PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x18013cf4c  mov     esi, eax
0x18013cf4e  test    eax, eax
0x18013cf50  js      loc_18013D0F7
0x18013cf56  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x18013cf5d  lea     rcx, [rbp+47h+var_68]; this
0x18013cf61  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x18013cf66  mov     esi, eax
0x18013cf68  test    eax, eax
0x18013cf6a  js      loc_18013D0F7
0x18013cf70  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x18013cf77  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013cf7e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cf83  mov     eax, dword ptr [rbp+47h+var_94]
0x18013cf86  mov     r15, [rbp+47h+var_88]
0x18013cf8a  lea     rcx, [rbp+47h+var_68]
0x18013cf8e  mov     qword ptr [rsp+0F0h+var_C8], rcx; unsigned int
0x18013cf93  mov     dword ptr [rsp+0F0h+var_D0], eax; struct _devicemodeW *
0x18013cf97  mov     r9, [r12]; unsigned __int16 *
0x18013cf9b  mov     r8, r15; unsigned __int16 *
0x18013cf9e  mov     rdx, [rbp+47h+arg_0]
0x18013cfa2  mov     rdx, [rdx+18h]; void *
0x18013cfa6  mov     rcx, [rbp+47h+arg_8]; this
0x18013cfaa  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18013cfaf  mov     esi, eax
0x18013cfb1  test    eax, eax
0x18013cfb3  js      loc_18013D0FB
0x18013cfb9  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x18013cfc0  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013cfc7  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cfcc  mov     rcx, [rbp+47h+var_60]
0x18013cfd0  test    rcx, rcx
0x18013cfd3  jnz     short loc_18013CFDF
0x18013cfd5  mov     esi, 80004005h
0x18013cfda  jmp     loc_18013D0FB
0x18013cfdf  mov     rax, [rcx]
0x18013cfe2  mov     rax, [rax+8]
0x18013cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013cfeb  mov     r13, [rbp+47h+var_60]
0x18013cfef  mov     [rbp+47h+var_40], r13
0x18013cff3  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x18013cffa  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013d001  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d006  mov     rax, [rbx]
0x18013d009  mov     r9, r13
0x18013d00c  mov     r8, [r12]
0x18013d010  mov     edx, [rbp+47h+arg_18]
0x18013d013  mov     rcx, rbx
0x18013d016  mov     rax, [rax+38h]
0x18013d01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d01f  mov     esi, eax
0x18013d021  test    eax, eax
0x18013d023  js      loc_18013D0FB
0x18013d029  lea     rdx, aInvokingTheJsc; "Invoking the JScript ValidatePrintTicke"...
0x18013d030  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013d037  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d03c  mov     rdx, r13; struct IXMLDOMDocument2 *
0x18013d03f  mov     rcx, rbx; this
0x18013d042  call    ?PerformJScriptValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@QEAAJPEAUIXMLDOMDocument2@@@Z; UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(IXMLDOMDocument2 *)
0x18013d047  mov     esi, eax
0x18013d049  test    eax, eax
0x18013d04b  js      loc_18013D0FB
0x18013d051  lea     rdx, aFilterPrintTic; "Filter print ticket"
0x18013d058  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013d05f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d064  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18013d069  mov     esi, eax
0x18013d06b  test    eax, eax
0x18013d06d  js      loc_18013D0FB
0x18013d073  lea     rdx, aConvertThePrin; "Convert the print ticket to DevMode"
0x18013d07a  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013d081  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d086  mov     rax, [rbx]
0x18013d089  lea     rcx, [rbp+47h+pv]
0x18013d08d  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x18013d092  lea     rcx, [rbp+47h+uBytes]
0x18013d096  mov     [rsp+0F0h+var_D0], rcx
0x18013d09b  mov     r9, [r12]
0x18013d09f  mov     r8d, [rbp+47h+arg_18]
0x18013d0a3  mov     rdx, r13
0x18013d0a6  mov     rcx, rbx
0x18013d0a9  mov     rax, [rax+30h]
0x18013d0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d0b2  mov     esi, eax
0x18013d0b4  test    eax, eax
0x18013d0b6  js      short loc_18013D0FB
0x18013d0b8  lea     rdx, aInvokePublicSh; "Invoke public shim to convert JobTicket"...
0x18013d0bf  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x18013d0c6  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d0cb  mov     rax, [rbp+47h+pv]
0x18013d0cf  mov     ecx, dword ptr [rbp+47h+var_94]
0x18013d0d2  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned int
0x18013d0d7  mov     dword ptr [rsp+0F0h+var_D0], ecx; unsigned __int16 *
0x18013d0db  mov     r9, r15; unsigned __int16 *
0x18013d0de  mov     rax, [rbp+47h+arg_0]
0x18013d0e2  mov     r8, [rax+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18013d0e6  lea     rdx, [rbp+47h+var_68]; void *
0x18013d0ea  mov     rcx, [rbp+47h+arg_8]; this
  ... truncated ...
```
