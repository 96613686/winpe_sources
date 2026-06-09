# UniDrvUI::PerformJScriptDevmodeValidation(UniDrvUI::_COMMONINFO *,void *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)

- ea: `0x18010fff8`
- end: `0x18011068a`
- name: `?PerformJScriptDevmodeValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z`
- size: `1682`
- prototype: `int(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, void *, struct _devicemodeW **, unsigned int, unsigned int *, struct _UNIDRVEXTRA **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18010e5ac`
- `0x180110690`

## callees

- `0x180003310`
- `0x180003b44`
- `0x180018780`
- `0x180032fe8`
- `0x180033080`
- `0x180033120`
- `0x1800ea034`
- `0x1800f32a4`
- `0x1800f9058`
- `0x1800fa9ac`
- `0x1800fb18c`
- `0x180100818`
- `0x180102674`
- `0x18010427c`
- `0x18010ef50`
- `0x18010fff8`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1801105c1`
- `KERNEL32!LocalFree` at `0x1801105c1`
- `KERNEL32!LocalAlloc` at `0x1801105ce`
- `KERNEL32!LocalAlloc` at `0x1801105ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180110300`
- `OLEAUT32!__imp_SysFreeString` at `0x180110505`
- `OLEAUT32!__imp_SysFreeString` at `0x180110300`
- `OLEAUT32!__imp_SysFreeString` at `0x180110505`
- `ole32!CoInitializeEx` at `0x18011010f`
- `ole32!CoInitializeEx` at `0x18011010f`
- `ole32!CoUninitialize` at `0x1801101f5`
- `ole32!CoUninitialize` at `0x180110544`
- `ole32!CoUninitialize` at `0x1801101f5`
- `ole32!CoUninitialize` at `0x180110544`
- `ole32!CoTaskMemFree` at `0x180110205`
- `ole32!CoTaskMemFree` at `0x180110319`
- `ole32!CoTaskMemFree` at `0x18011064f`
- `ole32!CoTaskMemFree` at `0x180110205`
- `ole32!CoTaskMemFree` at `0x180110319`
- `ole32!CoTaskMemFree` at `0x18011064f`

## string_xrefs

- `0x1801100ce`: `Current DevMode element exists in the current cache`
- `0x1801100a7`: `Attempt to check if the DevMode element exists in the current cache`
- `0x1801100f8`: `Current DevMode element does not exist in the current cache`
- `0x18011008c`: `Clearing the cache because the flag is set as FLAG_V4_JS_DEVMODE_CACHE_INVALIDATE`
- `0x1801103bb`: `Get print ticket XML`
- `0x180110327`: `Try retrieving the driver's URI from the config file`
- `0x180110556`: `The DevMode element does not exist in the cache, try to insert it into the cache`
- `0x180110594`: `The DevMode element exists in the cache, set the return data value`

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
  if ( !(unsigned int)JSDevModeCacheFind(
                        *((const unsigned __int16 **)this + 3),
                        a2,
                        *a3,
                        (struct _devicemodeW **)&Block) )
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
  v44 = 0;
  *(_QWORD *)v39 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v35 = 0;
  v17 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180231880);
  v38 = v17;
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
      v33 = 0;
      *(_QWORD *)&v34[1] = 0;
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PerformJScriptDevmodeValidation",
        L"Bind with the printer");
      ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, struct UniDrvUI::_COMMONINFO *, _QWORD, int *, _DWORD *, int *))(*v17 + 32LL))(
                                v17,
                                a2,
                                uBytes_4,
                                &v36,
                                v34,
                                &v33);
      if ( *(_QWORD *)&v34[1] )
      {
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::PerformJScriptDevmodeValidation",
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
          "UniDrvUI::PerformJScriptDevmodeValidation",
          L"Try retrieving the driver's URI from the config file");
        v35 = 0;
        ProviderSchemaVersion = UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                                  (UniDrvUI::CPrintTicketProvider *)v17,
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
            "UniDrvUI::PerformJScriptDevmodeValidation",
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
              "UniDrvUI::PerformJScriptDevmodeValidation",
              L"Get print ticket XML");
            if ( v40[0] )
            {
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v40[0]->lpVtbl->AddRef)(v40[0]);
              v16 = v40[0];
              v44 = v40[0];
              DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
                "UniDrvUI::PerformJScriptDevmodeValidation",
                L"Invoke the providers conversion method to convert driver-specific converion");
              ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, const struct _devicemodeW *, struct IXMLDOMDocument2 *))(*v17 + 56LL))(
                                        v17,
                                        v48,
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
                        "UniDrvUI::PerformJScriptDevmodeValidation",
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
      "UniDrvUI::PerformJScriptDevmodeValidation",
      L"The DevMode element does not exist in the cache, try to insert it into the cache");
    JSDevModeCacheInsert(*((const unsigned __int16 **)this + 3), a2, *a3, (const struct _devicemodeW *)pv, uBytes);
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
0x18010fff8  mov     rax, rsp
0x18010fffb  mov     [rax+20h], r9d
0x18010ffff  mov     [rax+10h], rdx
0x180110003  mov     [rax+8], rcx
0x180110007  push    rbp
0x180110008  push    rsi
0x180110009  push    rdi
0x18011000a  push    r12
0x18011000c  push    r13
0x18011000e  push    r14
0x180110010  push    r15
0x180110012  lea     rbp, [rax-4Fh]
0x180110016  sub     rsp, 0C0h
0x18011001d  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x180110025  mov     [rax+18h], rbx
0x180110029  mov     r12, r8
0x18011002c  mov     rsi, rdx
0x18011002f  mov     rbx, rcx
0x180110032  xor     r15d, r15d
0x180110035  mov     dword ptr [rbp+47h+var_94], r15d
0x180110039  mov     [rbp+47h+var_80], r15d
0x18011003d  lea     rdx, aEnter_0; "Enter"
0x180110044  lea     r13, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x18011004b  mov     rcx, r13; char *
0x18011004e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110053  test    rbx, rbx
0x180110056  jz      loc_18011066A
0x18011005c  mov     rax, [rbx+30h]
0x180110060  test    rax, rax
0x180110063  jz      loc_18011066A
0x180110069  cmp     [rax+20h], r15
0x18011006d  jz      loc_18011066A
0x180110073  test    dword ptr [rax+18h], 100000h
0x18011007a  jnz     short loc_180110083
0x18011007c  xor     eax, eax
0x18011007e  jmp     loc_18011066F
0x180110083  test    dword ptr [rbx+28h], 400000h
0x18011008a  jz      short loc_1801100A0
0x18011008c  lea     rdx, aClearingTheCac; "Clearing the cache because the flag is "...
0x180110093  mov     rcx, r13; char *
0x180110096  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011009b  call    ?JSDevModeCacheInvalidate@@YAXXZ; JSDevModeCacheInvalidate(void)
0x1801100a0  mov     dil, r15b
0x1801100a3  mov     [rbp+47h+Block], r15
0x1801100a7  lea     rdx, aAttemptToCheck; "Attempt to check if the DevMode element"...
0x1801100ae  mov     rcx, r13; char *
0x1801100b1  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801100b6  lea     r9, [rbp+47h+Block]; struct _devicemodeW **
0x1801100ba  mov     r8, [r12]; struct _devicemodeW *
0x1801100be  mov     rdx, rsi; void *
0x1801100c1  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1801100c5  call    ?JSDevModeCacheFind@@YAJPEBGQEAXPEBU_devicemodeW@@PEAPEAU1@@Z; JSDevModeCacheFind(ushort const *,void * const,_devicemodeW const *,_devicemodeW * *)
0x1801100ca  test    eax, eax
0x1801100cc  jnz     short loc_1801100E0
0x1801100ce  lea     rdx, aCurrentDevmode; "Current DevMode element exists in the c"...
0x1801100d5  mov     rcx, r13; char *
0x1801100d8  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801100dd  mov     dil, 1
0x1801100e0  mov     dword ptr [rbp+47h+uBytes], r15d
0x1801100e4  mov     [rbp+47h+pv], r15
0x1801100e8  mov     r14, [rbp+47h+Block]
0x1801100ec  mov     rcx, r13; char *
0x1801100ef  test    dil, dil
0x1801100f2  jnz     loc_180110591
0x1801100f8  lea     rdx, aCurrentDevmode_0; "Current DevMode element does not exist "...
0x1801100ff  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110104  mov     dil, r15b
0x180110107  mov     [rbp+47h+var_B0], r15b
0x18011010b  xor     edx, edx; dwCoInit
0x18011010d  xor     ecx, ecx; pvReserved
0x18011010f  call    cs:__imp_CoInitializeEx
0x180110115  mov     esi, eax
0x180110117  test    eax, eax
0x180110119  js      short loc_180110124
0x18011011b  mov     dil, 1
0x18011011e  mov     [rbp+47h+var_B0], dil
0x180110122  jmp     short loc_18011012E
0x180110124  cmp     esi, 80010106h
0x18011012a  cmovz   esi, r15d
0x18011012e  mov     r13, r15
0x180110131  mov     [rbp+47h+var_40], r15
0x180110135  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18011013c  mov     qword ptr [rbp+47h+var_68], rax
0x180110140  xorps   xmm0, xmm0
0x180110143  movdqu  xmmword ptr [rbp+47h+var_60], xmm0
0x180110148  mov     [rbp+47h+var_50], r15
0x18011014c  mov     [rbp+47h+var_48], r15w
0x180110151  mov     [rbp+47h+var_44], r15d
0x180110155  mov     [rbp+47h+var_88], r15
0x180110159  lea     rdx, qword_180231880; struct std::nothrow_t *
0x180110160  mov     ecx, 60h ; '`'; unsigned __int64
0x180110165  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18011016a  mov     rbx, rax
0x18011016d  mov     [rbp+47h+var_70], rax
0x180110171  test    rax, rax
0x180110174  jz      short loc_1801101DB
0x180110176  lea     rax, ??_7CPrintTicketProvider@UniDrvUI@@6B@; const UniDrvUI::CPrintTicketProvider::`vftable'
0x18011017d  mov     [rbx], rax
0x180110180  mov     qword ptr [rbx+8], 0
0x180110188  mov     qword ptr [rbx+10h], 0
0x180110190  mov     qword ptr [rbx+18h], 0
0x180110198  mov     qword ptr [rbx+20h], 0
0x1801101a0  mov     dword ptr [rbx+28h], 1
0x1801101a7  mov     qword ptr [rbx+30h], 0
0x1801101af  mov     qword ptr [rbx+38h], 0
0x1801101b7  mov     qword ptr [rbx+48h], 0
0x1801101bf  mov     qword ptr [rbx+50h], 0
0x1801101c7  mov     qword ptr [rbx+58h], 0
0x1801101cf  lock inc cs:?g_cComponents@UniDrvUI@@3JA; long UniDrvUI::g_cComponents
0x1801101d6  test    rbx, rbx
0x1801101d9  jnz     short loc_1801101DD
0x1801101db  xor     ebx, ebx
0x1801101dd  mov     [rbp+47h+var_70], rbx
0x1801101e1  test    rbx, rbx
0x1801101e4  jnz     short loc_18011022A
0x1801101e6  lea     rcx, [rbp+47h+var_68]; this
0x1801101ea  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1801101ef  nop
0x1801101f0  test    dil, dil
0x1801101f3  jz      short loc_1801101FC
0x1801101f5  call    cs:__imp_CoUninitialize
0x1801101fb  nop
0x1801101fc  mov     rcx, [rbp+47h+pv]; pv
0x180110200  test    rcx, rcx
0x180110203  jz      short loc_180110213
0x180110205  call    cs:__imp_CoTaskMemFree
0x18011020b  mov     [rbp+47h+pv], 0
0x180110213  test    r14, r14
0x180110216  jz      short loc_180110220
0x180110218  mov     rcx, r14; Block
0x18011021b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180110220  mov     eax, 80004005h
0x180110225  jmp     loc_18011066F
0x18011022a  test    esi, esi
0x18011022c  js      loc_1801104FD
0x180110232  mov     dword ptr [rbp+47h+uBytes+4], 0
0x180110239  lea     r8, [rbp+47h+uBytes+4]; struct UniDrvUI::CPrintTicketProvider *
0x18011023d  mov     rdx, rbx; void *
0x180110240  mov     rcx, [rbp+47h+arg_8]; this
0x180110244  call    ?GetProviderSchemaVersion@UniDrvUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; UniDrvUI::GetProviderSchemaVersion(void *,UniDrvUI::CPrintTicketProvider *,int *)
0x180110249  mov     esi, eax
0x18011024b  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x18011024f  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x180110256  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x18011025d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110262  test    esi, esi
0x180110264  js      loc_1801104FD
0x18011026a  mov     [rbp+47h+var_98], 0
0x180110271  mov     qword ptr [rbp+47h+var_94+4], 0
0x180110279  lea     rdx, aBindWithThePri; "Bind with the printer"
0x180110280  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110287  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011028c  mov     rax, [rbx]
0x18011028f  lea     rcx, [rbp+47h+var_94+4]
0x180110293  mov     [rsp+30h], rcx; struct _devicemodeW *
0x180110298  lea     rcx, [rbp+47h+var_98]
0x18011029c  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x1801102a1  lea     rcx, [rbp+47h+var_94]
0x1801102a5  mov     [rsp+0F0h+var_D0], rcx
0x1801102aa  lea     r9, [rbp+47h+var_80]
0x1801102ae  mov     r8d, dword ptr [rbp+47h+uBytes+4]
0x1801102b2  mov     rdx, [rbp+47h+arg_8]
0x1801102b6  mov     rcx, rbx
0x1801102b9  mov     rax, [rax+20h]
0x1801102bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801102c2  mov     esi, eax
0x1801102c4  cmp     qword ptr [rbp+47h+var_94+4], 0
0x1801102c9  jz      short loc_18011031F
0x1801102cb  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x1801102d2  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801102d9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801102de  mov     dword ptr [rbp+47h+uBytes+4], 0
0x1801102e5  mov     edx, [rbp+47h+var_98]
0x1801102e8  test    edx, edx
0x1801102ea  jle     short loc_180110315
0x1801102ec  mov     r14d, dword ptr [rbp+47h+uBytes+4]
0x1801102f0  movsxd  rcx, r14d
0x1801102f3  mov     rax, qword ptr [rbp+47h+var_94+4]
0x1801102f7  mov     rcx, [rax+rcx*8]; bstrString
0x1801102fb  test    rcx, rcx
0x1801102fe  jz      short loc_180110309
0x180110300  call    cs:__imp_SysFreeString
0x180110306  mov     edx, [rbp+47h+var_98]
0x180110309  inc     r14d
0x18011030c  cmp     r14d, edx
0x18011030f  jl      short loc_1801102F0
0x180110311  mov     r14, [rbp+47h+Block]
0x180110315  mov     rcx, qword ptr [rbp+47h+var_94+4]; pv
0x180110319  call    cs:__imp_CoTaskMemFree
0x18011031f  test    esi, esi
0x180110321  js      loc_1801104FD
0x180110327  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x18011032e  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110335  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011033a  mov     [rbp+47h+var_88], 0
0x180110342  lea     rdx, [rbp+47h+var_88]; unsigned __int16 **
0x180110346  mov     rcx, rbx; this
0x180110349  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@UniDrvUI@@QEAAJPEAPEAG@Z; UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x18011034e  mov     esi, eax
0x180110350  test    eax, eax
0x180110352  js      loc_1801104F9
0x180110358  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x18011035f  lea     rcx, [rbp+47h+var_68]; this
0x180110363  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x180110368  mov     esi, eax
0x18011036a  test    eax, eax
0x18011036c  js      loc_1801104F9
0x180110372  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x180110379  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110380  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110385  mov     eax, dword ptr [rbp+47h+var_94]
0x180110388  mov     r15, [rbp+47h+var_88]
0x18011038c  lea     rcx, [rbp+47h+var_68]
0x180110390  mov     qword ptr [rsp+0F0h+var_C8], rcx; unsigned int
0x180110395  mov     dword ptr [rsp+0F0h+var_D0], eax; struct _devicemodeW *
0x180110399  mov     r9, [r12]; unsigned __int16 *
0x18011039d  mov     r8, r15; unsigned __int16 *
0x1801103a0  mov     rdx, [rbp+47h+arg_0]
0x1801103a4  mov     rdx, [rdx+18h]; void *
0x1801103a8  mov     rcx, [rbp+47h+arg_8]; this
0x1801103ac  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x1801103b1  mov     esi, eax
0x1801103b3  test    eax, eax
0x1801103b5  js      loc_1801104FD
0x1801103bb  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x1801103c2  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801103c9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801103ce  mov     rcx, [rbp+47h+var_60]
0x1801103d2  test    rcx, rcx
0x1801103d5  jnz     short loc_1801103E1
0x1801103d7  mov     esi, 80004005h
0x1801103dc  jmp     loc_1801104FD
0x1801103e1  mov     rax, [rcx]
0x1801103e4  mov     rax, [rax+8]
0x1801103e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801103ed  mov     r13, [rbp+47h+var_60]
0x1801103f1  mov     [rbp+47h+var_40], r13
0x1801103f5  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x1801103fc  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110403  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110408  mov     rax, [rbx]
0x18011040b  mov     r9, r13
0x18011040e  mov     r8, [r12]
0x180110412  mov     edx, [rbp+47h+arg_18]
0x180110415  mov     rcx, rbx
0x180110418  mov     rax, [rax+38h]
0x18011041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110421  mov     esi, eax
0x180110423  test    eax, eax
0x180110425  js      loc_1801104FD
0x18011042b  lea     rdx, aInvokingTheJsc; "Invoking the JScript ValidatePrintTicke"...
0x180110432  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110439  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011043e  mov     rdx, r13; struct IXMLDOMDocument2 *
0x180110441  mov     rcx, rbx; this
0x180110444  call    ?PerformJScriptValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@QEAAJPEAUIXMLDOMDocument2@@@Z; UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(IXMLDOMDocument2 *)
0x180110449  mov     esi, eax
0x18011044b  test    eax, eax
0x18011044d  js      loc_1801104FD
0x180110453  lea     rdx, aFilterPrintTic; "Filter print ticket"
0x18011045a  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110461  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110466  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18011046b  mov     esi, eax
0x18011046d  test    eax, eax
0x18011046f  js      loc_1801104FD
0x180110475  lea     rdx, aConvertThePrin; "Convert the print ticket to DevMode"
0x18011047c  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x180110483  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110488  mov     rax, [rbx]
0x18011048b  lea     rcx, [rbp+47h+pv]
0x18011048f  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x180110494  lea     rcx, [rbp+47h+uBytes]
0x180110498  mov     [rsp+0F0h+var_D0], rcx
0x18011049d  mov     r9, [r12]
0x1801104a1  mov     r8d, [rbp+47h+arg_18]
0x1801104a5  mov     rdx, r13
0x1801104a8  mov     rcx, rbx
0x1801104ab  mov     rax, [rax+30h]
0x1801104af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801104b4  mov     esi, eax
0x1801104b6  test    eax, eax
0x1801104b8  js      short loc_1801104FD
0x1801104ba  lea     rdx, aInvokePublicSh; "Invoke public shim to convert JobTicket"...
0x1801104c1  lea     rcx, aUnidrvuiPerfor; "UniDrvUI::PerformJScriptDevmodeValidati"...
0x1801104c8  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801104cd  mov     rax, [rbp+47h+pv]
0x1801104d1  mov     ecx, dword ptr [rbp+47h+var_94]
0x1801104d4  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned int
0x1801104d9  mov     dword ptr [rsp+0F0h+var_D0], ecx; unsigned __int16 *
0x1801104dd  mov     r9, r15; unsigned __int16 *
0x1801104e0  mov     rax, [rbp+47h+arg_0]
0x1801104e4  mov     r8, [rax+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1801104e8  lea     rdx, [rbp+47h+var_68]; void *
0x1801104ec  mov     rcx, [rbp+47h+arg_8]; this
0x1801104f0  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x1801104f5  mov     esi, eax
0x1801104f7  jmp     short loc_1801104FD
0x1801104f9  mov     r15, [rbp+47h+var_88]
0x1801104fd  test    r15, r15
  ... truncated ...
```
