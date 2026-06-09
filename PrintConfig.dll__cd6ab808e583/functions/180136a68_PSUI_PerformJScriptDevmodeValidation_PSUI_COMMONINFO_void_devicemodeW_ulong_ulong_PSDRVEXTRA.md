# PSUI::PerformJScriptDevmodeValidation(PSUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)

- ea: `0x180136a68`
- end: `0x1801370fa`
- name: `?PerformJScriptDevmodeValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z`
- size: `1682`
- prototype: `int(PSUI *__hidden this, struct PSUI::_COMMONINFO *, void *, struct _devicemodeW **, unsigned int, unsigned int *, struct _PSDRVEXTRA **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18013534c`
- `0x180137100`

## callees

- `0x180003310`
- `0x180003b44`
- `0x180018780`
- `0x180032fe8`
- `0x180033080`
- `0x180033120`
- `0x1800ea034`
- `0x1800f9058`
- `0x1800fa9ac`
- `0x1800fb18c`
- `0x180100818`
- `0x180102674`
- `0x18010427c`
- `0x180128f0c`
- `0x180135bfc`
- `0x180136a68`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180137031`
- `KERNEL32!LocalFree` at `0x180137031`
- `KERNEL32!LocalAlloc` at `0x18013703e`
- `KERNEL32!LocalAlloc` at `0x18013703e`
- `OLEAUT32!__imp_SysFreeString` at `0x180136d70`
- `OLEAUT32!__imp_SysFreeString` at `0x180136f75`
- `OLEAUT32!__imp_SysFreeString` at `0x180136d70`
- `OLEAUT32!__imp_SysFreeString` at `0x180136f75`
- `ole32!CoInitializeEx` at `0x180136b7f`
- `ole32!CoInitializeEx` at `0x180136b7f`
- `ole32!CoUninitialize` at `0x180136c65`
- `ole32!CoUninitialize` at `0x180136fb4`
- `ole32!CoUninitialize` at `0x180136c65`
- `ole32!CoUninitialize` at `0x180136fb4`
- `ole32!CoTaskMemFree` at `0x180136c75`
- `ole32!CoTaskMemFree` at `0x180136d89`
- `ole32!CoTaskMemFree` at `0x1801370bf`
- `ole32!CoTaskMemFree` at `0x180136c75`
- `ole32!CoTaskMemFree` at `0x180136d89`
- `ole32!CoTaskMemFree` at `0x1801370bf`

## string_xrefs

- `0x180136b3e`: `Current DevMode element exists in the current cache`
- `0x180136b17`: `Attempt to check if the DevMode element exists in the current cache`
- `0x180136b68`: `Current DevMode element does not exist in the current cache`
- `0x180136afc`: `Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE`
- `0x180136e2b`: `Get print ticket XML`
- `0x180136d97`: `Try retrieving the driver's URI from the config file`
- `0x180136fc6`: `The DevMode element does not exist in the cache, try to insert it into the cache`
- `0x180137004`: `The DevMode element exists in the cache, set the return data value`

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
  HRESULT ProviderSchemaVersion; // esi
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
  struct _devicemodeW *v29; // [rsp+38h] [rbp-79h]
  unsigned int uBytes; // [rsp+4Ch] [rbp-65h] BYREF
  unsigned int uBytes_4; // [rsp+50h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-59h] BYREF
  int v33; // [rsp+60h] [rbp-51h] BYREF
  _DWORD v34[3]; // [rsp+64h] [rbp-4Dh] BYREF
  unsigned __int16 *v35; // [rsp+70h] [rbp-41h] BYREF
  int v36; // [rsp+78h] [rbp-39h] BYREF
  void *Block; // [rsp+80h] [rbp-31h] BYREF
  _QWORD *v38; // [rsp+88h] [rbp-29h]
  unsigned int v39[2]; // [rsp+90h] [rbp-21h] BYREF
  struct IXMLDOMDocument2 *v40[2]; // [rsp+98h] [rbp-19h]
  __int64 v41; // [rsp+A8h] [rbp-9h]
  __int16 v42; // [rsp+B0h] [rbp-1h]
  int v43; // [rsp+B4h] [rbp+3h]
  struct IXMLDOMDocument2 *v44; // [rsp+B8h] [rbp+7h]
  __int64 v45; // [rsp+C0h] [rbp+Fh]
  unsigned int v48; // [rsp+120h] [rbp+6Fh]

  v48 = (unsigned int)a4;
  v45 = -2;
  v9 = 0;
  v34[0] = 0;
  v36 = 0;
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
  if ( !(unsigned int)JSDevModeCacheFind(
                        *((const unsigned __int16 **)this + 3),
                        a2,
                        *a3,
                        (struct _devicemodeW **)&Block) )
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
    if ( v48 != v25 )
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
  v44 = 0;
  *(_QWORD *)v39 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v35 = 0;
  v17 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180232260);
  v38 = v17;
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
  v38 = v17;
  if ( !v17 )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v39);
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
      v33 = 0;
      *(_QWORD *)&v34[1] = 0;
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PerformJScriptDevmodeValidation", L"Bind with the printer");
      ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct PSUI::_COMMONINFO *, _QWORD, int *, _DWORD *, int *))(*v17 + 32LL))(
                                v17,
                                a2,
                                uBytes_4,
                                &v36,
                                v34,
                                &v33);
      if ( *(_QWORD *)&v34[1] )
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PerformJScriptDevmodeValidation",
          L"Release any namespaces the driver provided");
        uBytes_4 = 0;
        v19 = v33;
        if ( v33 > 0 )
        {
          v20 = uBytes_4;
          do
          {
            v21 = *(OLECHAR **)(*(_QWORD *)&v34[1] + 8LL * v20);
            if ( v21 )
            {
              SysFreeString(v21);
              v19 = v33;
            }
            ++v20;
          }
          while ( v20 < v19 );
          v13 = (unsigned __int16 *)Block;
        }
        CoTaskMemFree(*(LPVOID *)&v34[1]);
      }
      if ( ProviderSchemaVersion >= 0 )
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PerformJScriptDevmodeValidation",
          L"Try retrieving the driver's URI from the config file");
        v35 = 0;
        ProviderSchemaVersion = PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                                  (PSUI::CPrintTicketProvider *)v17,
                                  &v35);
        if ( ProviderSchemaVersion < 0
          || (ProviderSchemaVersion = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
                                        (NPrintTicketUtil::CPrintTicketWrapper *)v39,
                                        L"psf:PrintTicket",
                                        v22),
              ProviderSchemaVersion < 0) )
        {
          v9 = v35;
        }
        else
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
            "PSUI::PerformJScriptDevmodeValidation",
            L"Convert the public portion via the shim");
          v9 = v35;
          LODWORD(v27) = v34[0];
          ProviderSchemaVersion = publicdm::PublicDevmodeToJobTicket(
                                    a2,
                                    *((void **)this + 3),
                                    v35,
                                    (*a3)->dmDeviceName,
                                    v27,
                                    (unsigned int)v39,
                                    (struct NPrintTicketUtil::CPrintTicketWrapper *)&v34[1]);
          if ( ProviderSchemaVersion >= 0 )
          {
            DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
              "PSUI::PerformJScriptDevmodeValidation",
              L"Get print ticket XML");
            if ( v40[0] )
            {
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v40[0]->lpVtbl->AddRef)(v40[0]);
              v16 = v40[0];
              v44 = v40[0];
              DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                "PSUI::PerformJScriptDevmodeValidation",
                L"Invoke the providers conversion method to convert driver-specific converion");
              ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, const struct _devicemodeW *, struct IXMLDOMDocument2 *))(*v17 + 56LL))(
                                        v17,
                                        v48,
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
                    ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct IXMLDOMDocument2 *, _QWORD, const struct _devicemodeW *, unsigned int *, LPVOID *))(*v17 + 48LL))(
                                              v17,
                                              v16,
                                              v48,
                                              *a3,
                                              &uBytes,
                                              &pv);
                    if ( ProviderSchemaVersion >= 0 )
                    {
                      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                        "PSUI::PerformJScriptDevmodeValidation",
                        L"Invoke public shim to convert JobTicket to public DevMode");
                      LODWORD(v28) = v34[0];
                      ProviderSchemaVersion = publicdm::JobTicketToPublicDevmode(
                                                a2,
                                                v39,
                                                *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 3),
                                                v9,
                                                v28->dmDeviceName,
                                                (unsigned int)pv,
                                                v29);
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
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v39);
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
    JSDevModeCacheInsert(*((const unsigned __int16 **)this + 3), a2, *a3, (const struct _devicemodeW *)pv, uBytes);
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
0x180136a68  mov     rax, rsp
0x180136a6b  mov     [rax+20h], r9d
0x180136a6f  mov     [rax+10h], rdx
0x180136a73  mov     [rax+8], rcx
0x180136a77  push    rbp
0x180136a78  push    rsi
0x180136a79  push    rdi
0x180136a7a  push    r12
0x180136a7c  push    r13
0x180136a7e  push    r14
0x180136a80  push    r15
0x180136a82  lea     rbp, [rax-4Fh]
0x180136a86  sub     rsp, 0C0h
0x180136a8d  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x180136a95  mov     [rax+18h], rbx
0x180136a99  mov     r12, r8
0x180136a9c  mov     rsi, rdx
0x180136a9f  mov     rbx, rcx
0x180136aa2  xor     r15d, r15d
0x180136aa5  mov     dword ptr [rbp+47h+var_94], r15d
0x180136aa9  mov     [rbp+47h+var_80], r15d
0x180136aad  lea     rdx, aEnter_0; "Enter"
0x180136ab4  lea     r13, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136abb  mov     rcx, r13; char *
0x180136abe  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136ac3  test    rbx, rbx
0x180136ac6  jz      loc_1801370DA
0x180136acc  mov     rax, [rbx+30h]
0x180136ad0  test    rax, rax
0x180136ad3  jz      loc_1801370DA
0x180136ad9  cmp     [rax+20h], r15
0x180136add  jz      loc_1801370DA
0x180136ae3  test    dword ptr [rax+18h], 100000h
0x180136aea  jnz     short loc_180136AF3
0x180136aec  xor     eax, eax
0x180136aee  jmp     loc_1801370DF
0x180136af3  test    dword ptr [rbx+28h], 400000h
0x180136afa  jz      short loc_180136B10
0x180136afc  lea     rdx, aClearingTheCac; "Clearing the cache because the flag is "...
0x180136b03  mov     rcx, r13; char *
0x180136b06  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136b0b  call    ?JSDevModeCacheInvalidate@@YAXXZ; JSDevModeCacheInvalidate(void)
0x180136b10  mov     dil, r15b
0x180136b13  mov     [rbp+47h+Block], r15
0x180136b17  lea     rdx, aAttemptToCheck; "Attempt to check if the DevMode element"...
0x180136b1e  mov     rcx, r13; char *
0x180136b21  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136b26  lea     r9, [rbp+47h+Block]; struct _devicemodeW **
0x180136b2a  mov     r8, [r12]; struct _devicemodeW *
0x180136b2e  mov     rdx, rsi; void *
0x180136b31  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180136b35  call    ?JSDevModeCacheFind@@YAJPEBGQEAXPEBU_devicemodeW@@PEAPEAU1@@Z; JSDevModeCacheFind(ushort const *,void * const,_devicemodeW const *,_devicemodeW * *)
0x180136b3a  test    eax, eax
0x180136b3c  jnz     short loc_180136B50
0x180136b3e  lea     rdx, aCurrentDevmode; "Current DevMode element exists in the c"...
0x180136b45  mov     rcx, r13; char *
0x180136b48  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136b4d  mov     dil, 1
0x180136b50  mov     dword ptr [rbp+47h+uBytes], r15d
0x180136b54  mov     [rbp+47h+pv], r15
0x180136b58  mov     r14, [rbp+47h+Block]
0x180136b5c  mov     rcx, r13; char *
0x180136b5f  test    dil, dil
0x180136b62  jnz     loc_180137001
0x180136b68  lea     rdx, aCurrentDevmode_0; "Current DevMode element does not exist "...
0x180136b6f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136b74  mov     dil, r15b
0x180136b77  mov     [rbp+47h+var_B0], r15b
0x180136b7b  xor     edx, edx; dwCoInit
0x180136b7d  xor     ecx, ecx; pvReserved
0x180136b7f  call    cs:__imp_CoInitializeEx
0x180136b85  mov     esi, eax
0x180136b87  test    eax, eax
0x180136b89  js      short loc_180136B94
0x180136b8b  mov     dil, 1
0x180136b8e  mov     [rbp+47h+var_B0], dil
0x180136b92  jmp     short loc_180136B9E
0x180136b94  cmp     esi, 80010106h
0x180136b9a  cmovz   esi, r15d
0x180136b9e  mov     r13, r15
0x180136ba1  mov     [rbp+47h+var_40], r15
0x180136ba5  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180136bac  mov     qword ptr [rbp+47h+var_68], rax
0x180136bb0  xorps   xmm0, xmm0
0x180136bb3  movdqu  xmmword ptr [rbp+47h+var_60], xmm0
0x180136bb8  mov     [rbp+47h+var_50], r15
0x180136bbc  mov     [rbp+47h+var_48], r15w
0x180136bc1  mov     [rbp+47h+var_44], r15d
0x180136bc5  mov     [rbp+47h+var_88], r15
0x180136bc9  lea     rdx, qword_180232260; struct std::nothrow_t *
0x180136bd0  mov     ecx, 60h ; '`'; unsigned __int64
0x180136bd5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180136bda  mov     rbx, rax
0x180136bdd  mov     [rbp+47h+var_70], rax
0x180136be1  test    rax, rax
0x180136be4  jz      short loc_180136C4B
0x180136be6  lea     rax, ??_7CPrintTicketProvider@PSUI@@6B@; const PSUI::CPrintTicketProvider::`vftable'
0x180136bed  mov     [rbx], rax
0x180136bf0  mov     qword ptr [rbx+8], 0
0x180136bf8  mov     qword ptr [rbx+10h], 0
0x180136c00  mov     qword ptr [rbx+18h], 0
0x180136c08  mov     qword ptr [rbx+20h], 0
0x180136c10  mov     dword ptr [rbx+28h], 1
0x180136c17  mov     qword ptr [rbx+30h], 0
0x180136c1f  mov     qword ptr [rbx+38h], 0
0x180136c27  mov     qword ptr [rbx+48h], 0
0x180136c2f  mov     qword ptr [rbx+50h], 0
0x180136c37  mov     qword ptr [rbx+58h], 0
0x180136c3f  lock inc cs:?g_cComponents@PSUI@@3JA; long PSUI::g_cComponents
0x180136c46  test    rbx, rbx
0x180136c49  jnz     short loc_180136C4D
0x180136c4b  xor     ebx, ebx
0x180136c4d  mov     [rbp+47h+var_70], rbx
0x180136c51  test    rbx, rbx
0x180136c54  jnz     short loc_180136C9A
0x180136c56  lea     rcx, [rbp+47h+var_68]; this
0x180136c5a  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180136c5f  nop
0x180136c60  test    dil, dil
0x180136c63  jz      short loc_180136C6C
0x180136c65  call    cs:__imp_CoUninitialize
0x180136c6b  nop
0x180136c6c  mov     rcx, [rbp+47h+pv]; pv
0x180136c70  test    rcx, rcx
0x180136c73  jz      short loc_180136C83
0x180136c75  call    cs:__imp_CoTaskMemFree
0x180136c7b  mov     [rbp+47h+pv], 0
0x180136c83  test    r14, r14
0x180136c86  jz      short loc_180136C90
0x180136c88  mov     rcx, r14; Block
0x180136c8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180136c90  mov     eax, 80004005h
0x180136c95  jmp     loc_1801370DF
0x180136c9a  test    esi, esi
0x180136c9c  js      loc_180136F6D
0x180136ca2  mov     dword ptr [rbp+47h+uBytes+4], 0
0x180136ca9  lea     r8, [rbp+47h+uBytes+4]; struct PSUI::CPrintTicketProvider *
0x180136cad  mov     rdx, rbx; void *
0x180136cb0  mov     rcx, [rbp+47h+arg_8]; this
0x180136cb4  call    ?GetProviderSchemaVersion@PSUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; PSUI::GetProviderSchemaVersion(void *,PSUI::CPrintTicketProvider *,int *)
0x180136cb9  mov     esi, eax
0x180136cbb  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x180136cbf  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x180136cc6  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136ccd  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136cd2  test    esi, esi
0x180136cd4  js      loc_180136F6D
0x180136cda  mov     [rbp+47h+var_98], 0
0x180136ce1  mov     qword ptr [rbp+47h+var_94+4], 0
0x180136ce9  lea     rdx, aBindWithThePri; "Bind with the printer"
0x180136cf0  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136cf7  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136cfc  mov     rax, [rbx]
0x180136cff  lea     rcx, [rbp+47h+var_94+4]
0x180136d03  mov     [rsp+30h], rcx; struct _devicemodeW *
0x180136d08  lea     rcx, [rbp+47h+var_98]
0x180136d0c  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x180136d11  lea     rcx, [rbp+47h+var_94]
0x180136d15  mov     [rsp+0F0h+var_D0], rcx
0x180136d1a  lea     r9, [rbp+47h+var_80]
0x180136d1e  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x180136d22  mov     rdx, [rbp+47h+arg_8]
0x180136d26  mov     rcx, rbx
0x180136d29  mov     rax, [rax+20h]
0x180136d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136d32  mov     esi, eax
0x180136d34  cmp     qword ptr [rbp+47h+var_94+4], 0
0x180136d39  jz      short loc_180136D8F
0x180136d3b  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x180136d42  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136d49  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136d4e  mov     dword ptr [rbp+47h+uBytes+4], 0
0x180136d55  mov     edx, [rbp+47h+var_98]
0x180136d58  test    edx, edx
0x180136d5a  jle     short loc_180136D85
0x180136d5c  mov     r14d, dword ptr [rbp+47h+uBytes+4]
0x180136d60  movsxd  rcx, r14d
0x180136d63  mov     rax, qword ptr [rbp+47h+var_94+4]
0x180136d67  mov     rcx, [rax+rcx*8]; bstrString
0x180136d6b  test    rcx, rcx
0x180136d6e  jz      short loc_180136D79
0x180136d70  call    cs:__imp_SysFreeString
0x180136d76  mov     edx, [rbp+47h+var_98]
0x180136d79  inc     r14d
0x180136d7c  cmp     r14d, edx
0x180136d7f  jl      short loc_180136D60
0x180136d81  mov     r14, [rbp+47h+Block]
0x180136d85  mov     rcx, qword ptr [rbp+47h+var_94+4]; pv
0x180136d89  call    cs:__imp_CoTaskMemFree
0x180136d8f  test    esi, esi
0x180136d91  js      loc_180136F6D
0x180136d97  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x180136d9e  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136da5  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136daa  mov     [rbp+47h+var_88], 0
0x180136db2  lea     rdx, [rbp+47h+var_88]; unsigned __int16 **
0x180136db6  mov     rcx, rbx; this
0x180136db9  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@PSUI@@QEAAJPEAPEAG@Z; PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x180136dbe  mov     esi, eax
0x180136dc0  test    eax, eax
0x180136dc2  js      loc_180136F69
0x180136dc8  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x180136dcf  lea     rcx, [rbp+47h+var_68]; this
0x180136dd3  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x180136dd8  mov     esi, eax
0x180136dda  test    eax, eax
0x180136ddc  js      loc_180136F69
0x180136de2  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x180136de9  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136df0  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136df5  mov     eax, dword ptr [rbp+47h+var_94]
0x180136df8  mov     r15, [rbp+47h+var_88]
0x180136dfc  lea     rcx, [rbp+47h+var_68]
0x180136e00  mov     qword ptr [rsp+0F0h+var_C8], rcx; unsigned int
0x180136e05  mov     dword ptr [rsp+0F0h+var_D0], eax; struct _devicemodeW *
0x180136e09  mov     r9, [r12]; unsigned __int16 *
0x180136e0d  mov     r8, r15; unsigned __int16 *
0x180136e10  mov     rdx, [rbp+47h+arg_0]
0x180136e14  mov     rdx, [rdx+18h]; void *
0x180136e18  mov     rcx, [rbp+47h+arg_8]; this
0x180136e1c  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x180136e21  mov     esi, eax
0x180136e23  test    eax, eax
0x180136e25  js      loc_180136F6D
0x180136e2b  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x180136e32  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136e39  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136e3e  mov     rcx, [rbp+47h+var_60]
0x180136e42  test    rcx, rcx
0x180136e45  jnz     short loc_180136E51
0x180136e47  mov     esi, 80004005h
0x180136e4c  jmp     loc_180136F6D
0x180136e51  mov     rax, [rcx]
0x180136e54  mov     rax, [rax+8]
0x180136e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136e5d  mov     r13, [rbp+47h+var_60]
0x180136e61  mov     [rbp+47h+var_40], r13
0x180136e65  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x180136e6c  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136e73  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136e78  mov     rax, [rbx]
0x180136e7b  mov     r9, r13
0x180136e7e  mov     r8, [r12]
0x180136e82  mov     edx, [rbp+47h+arg_18]
0x180136e85  mov     rcx, rbx
0x180136e88  mov     rax, [rax+38h]
0x180136e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136e91  mov     esi, eax
0x180136e93  test    eax, eax
0x180136e95  js      loc_180136F6D
0x180136e9b  lea     rdx, aInvokingTheJsc; "Invoking the JScript ValidatePrintTicke"...
0x180136ea2  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136ea9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136eae  mov     rdx, r13; struct IXMLDOMDocument2 *
0x180136eb1  mov     rcx, rbx; this
0x180136eb4  call    ?PerformJScriptValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@QEAAJPEAUIXMLDOMDocument2@@@Z; UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(IXMLDOMDocument2 *)
0x180136eb9  mov     esi, eax
0x180136ebb  test    eax, eax
0x180136ebd  js      loc_180136F6D
0x180136ec3  lea     rdx, aFilterPrintTic; "Filter print ticket"
0x180136eca  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136ed1  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136ed6  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x180136edb  mov     esi, eax
0x180136edd  test    eax, eax
0x180136edf  js      loc_180136F6D
0x180136ee5  lea     rdx, aConvertThePrin; "Convert the print ticket to DevMode"
0x180136eec  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136ef3  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136ef8  mov     rax, [rbx]
0x180136efb  lea     rcx, [rbp+47h+pv]
0x180136eff  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x180136f04  lea     rcx, [rbp+47h+uBytes]
0x180136f08  mov     [rsp+0F0h+var_D0], rcx
0x180136f0d  mov     r9, [r12]
0x180136f11  mov     r8d, [rbp+47h+arg_18]
0x180136f15  mov     rdx, r13
0x180136f18  mov     rcx, rbx
0x180136f1b  mov     rax, [rax+30h]
0x180136f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136f24  mov     esi, eax
0x180136f26  test    eax, eax
0x180136f28  js      short loc_180136F6D
0x180136f2a  lea     rdx, aInvokePublicSh; "Invoke public shim to convert JobTicket"...
0x180136f31  lea     rcx, aPsuiPerformjsc; "PSUI::PerformJScriptDevmodeValidation"
0x180136f38  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180136f3d  mov     rax, [rbp+47h+pv]
0x180136f41  mov     ecx, dword ptr [rbp+47h+var_94]
0x180136f44  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned int
0x180136f49  mov     dword ptr [rsp+0F0h+var_D0], ecx; unsigned __int16 *
0x180136f4d  mov     r9, r15; unsigned __int16 *
0x180136f50  mov     rax, [rbp+47h+arg_0]
0x180136f54  mov     r8, [rax+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180136f58  lea     rdx, [rbp+47h+var_68]; void *
0x180136f5c  mov     rcx, [rbp+47h+arg_8]; this
0x180136f60  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x180136f65  mov     esi, eax
0x180136f67  jmp     short loc_180136F6D
0x180136f69  mov     r15, [rbp+47h+var_88]
0x180136f6d  test    r15, r15
  ... truncated ...
```
