# UniDrvUI::TryPrintSupportValidation(UniDrvUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)

- ea: `0x180115610`
- end: `0x180115dda`
- name: `?TryPrintSupportValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z`
- size: `1994`
- prototype: `__int64 __fastcall(void **this, struct UniDrvUI::_COMMONINFO *, void *, unsigned __int16 *, struct _devicemodeW **, _DWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180110fe8`
- `0x180113264`

## callees

- `0x180003c64`
- `0x1800ee8cc`
- `0x1800f7d64`
- `0x1800ffc98`
- `0x180105360`
- `0x180107214`
- `0x180108e2c`
- `0x180113cb0`
- `0x180115610`
- `0x1801b56bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180115d0b`
- `KERNEL32!LocalFree` at `0x180115d0b`
- `KERNEL32!LocalAlloc` at `0x180115d1f`
- `KERNEL32!LocalAlloc` at `0x180115d1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18011586e`
- `OLEAUT32!__imp_SysFreeString` at `0x180115b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180115c9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18011586e`
- `OLEAUT32!__imp_SysFreeString` at `0x180115b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180115c9f`
- `OLEAUT32!__imp_VariantInit` at `0x180115a32`
- `OLEAUT32!__imp_VariantInit` at `0x180115a32`
- `ole32!CoCreateInstance` at `0x180115a7a`
- `ole32!CoCreateInstance` at `0x180115a7a`
- `ole32!CoInitializeEx` at `0x180115678`
- `ole32!CoInitializeEx` at `0x180115678`
- `ole32!CoUninitialize` at `0x1801156a6`
- `ole32!CoUninitialize` at `0x180115775`
- `ole32!CoUninitialize` at `0x180115b41`
- `ole32!CoUninitialize` at `0x180115ce0`
- `ole32!CoUninitialize` at `0x1801156a6`
- `ole32!CoUninitialize` at `0x180115775`
- `ole32!CoUninitialize` at `0x180115b41`
- `ole32!CoUninitialize` at `0x180115ce0`
- `ole32!CoTaskMemFree` at `0x1801156bd`
- `ole32!CoTaskMemFree` at `0x18011578c`
- `ole32!CoTaskMemFree` at `0x18011588b`
- `ole32!CoTaskMemFree` at `0x180115b58`
- `ole32!CoTaskMemFree` at `0x180115db0`
- `ole32!CoTaskMemFree` at `0x1801156bd`
- `ole32!CoTaskMemFree` at `0x18011578c`
- `ole32!CoTaskMemFree` at `0x18011588b`
- `ole32!CoTaskMemFree` at `0x180115b58`
- `ole32!CoTaskMemFree` at `0x180115db0`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x1801159f4`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x1801159f4`

## string_xrefs

- `0x1801158a3`: `Try retrieving the driver's URI from the config file`
- `0x180115937`: `Get print ticket XML`
- `0x180115bea`: `PSA Unable to set validated PT to IXMLDOMDocument2`
- `0x180115a91`: `PSA Unable to set create IXMLDOMDocument2 for return`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall UniDrvUI::TryPrintSupportValidation(
        void **this,
        struct UniDrvUI::_COMMONINFO *a2,
        void *a3,
        unsigned __int16 *a4,
        struct _devicemodeW **a5,
        _DWORD *a6,
        unsigned int *a7)
{
  UniDrvUI *v8; // r12
  char v9; // di
  HRESULT v10; // ebx
  LPVOID v12; // r14
  OLECHAR *v13; // r15
  _QWORD *v14; // rbx
  int *v15; // r9
  int ProviderSchemaVersion; // esi
  int v17; // r12d
  int i; // edx
  OLECHAR *v19; // rcx
  struct IXMLDOMElement **v20; // r8
  int v21; // eax
  HRESULT v22; // r12d
  int v23; // eax
  LPVOID v24; // rcx
  LPVOID v25; // r12
  const void *v26; // rbx
  unsigned int v27; // eax
  HLOCAL v28; // rax
  LPVOID *ppv; // [rsp+28h] [rbp-D1h]
  __int64 v30; // [rsp+48h] [rbp-B1h] BYREF
  LPVOID v31; // [rsp+50h] [rbp-A9h] BYREF
  SIZE_T uBytes; // [rsp+58h] [rbp-A1h] BYREF
  LPVOID v33; // [rsp+60h] [rbp-99h] BYREF
  LONGLONG v34; // [rsp+68h] [rbp-91h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-89h] BYREF
  int v36; // [rsp+78h] [rbp-81h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-79h] BYREF
  int v38; // [rsp+88h] [rbp-71h] BYREF
  LPVOID v39; // [rsp+90h] [rbp-69h]
  _QWORD *v40; // [rsp+98h] [rbp-61h]
  unsigned int v41[2]; // [rsp+A0h] [rbp-59h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-51h]
  __int64 v43; // [rsp+B8h] [rbp-41h]
  __int16 v44; // [rsp+C0h] [rbp-39h]
  int v45; // [rsp+C4h] [rbp-35h]
  VARIANTARG pvarg; // [rsp+C8h] [rbp-31h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-19h]
  VARIANTARG v48; // [rsp+E8h] [rbp-11h] BYREF

  v47 = -2;
  v8 = a2;
  v36 = 0;
  v38 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::TryPrintSupportValidation", L"Enter");
  LODWORD(uBytes) = 0;
  pv = 0;
  v9 = 0;
  v10 = CoInitializeEx(0, 0);
  if ( v10 < 0 )
  {
    if ( v10 == -2147417850 )
      v10 = 0;
  }
  else
  {
    v9 = 1;
  }
  if ( v10 < 0 )
  {
    if ( v9 )
      CoUninitialize();
    return (unsigned int)v10;
  }
  v12 = 0;
  v39 = 0;
  *(_QWORD *)v41 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v13 = 0;
  bstrString = 0;
  v14 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180239588);
  v40 = v14;
  if ( v14 )
  {
    *v14 = &UniDrvUI::CPrintTicketProvider::`vftable';
    v14[1] = 0;
    v14[2] = 0;
    v14[3] = 0;
    v14[4] = 0;
    *((_DWORD *)v14 + 10) = 1;
    v14[6] = 0;
    v14[7] = 0;
    v14[9] = 0;
    v14[10] = 0;
    v14[11] = 0;
    _InterlockedIncrement(&UniDrvUI::g_cComponents);
  }
  else
  {
    v14 = 0;
  }
  v40 = v14;
  if ( !v14 )
  {
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v41);
    if ( v9 )
      CoUninitialize();
    if ( pv )
      CoTaskMemFree(pv);
    return 2147500037LL;
  }
  HIDWORD(v30) = 0;
  ProviderSchemaVersion = UniDrvUI::GetProviderSchemaVersion(
                            v8,
                            v14,
                            (struct UniDrvUI::CPrintTicketProvider *)((char *)&v30 + 4),
                            v15);
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::TryPrintSupportValidation",
    L"Get the Provider Schema's version:  %d.",
    HIDWORD(v30));
  if ( ProviderSchemaVersion < 0 )
    goto LABEL_68;
  LODWORD(v31) = 0;
  v33 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::TryPrintSupportValidation", L"Bind with the printer");
  ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, UniDrvUI *, _QWORD, int *, int *, LPVOID *, LPVOID *))(*v14 + 32LL))(
                            v14,
                            v8,
                            HIDWORD(v30),
                            &v38,
                            &v36,
                            &v31,
                            &v33);
  if ( v33 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::TryPrintSupportValidation",
      L"Release any namespaces the driver provided");
    v17 = 0;
    for ( i = (int)v31; v17 < i; ++v17 )
    {
      v19 = (OLECHAR *)*((_QWORD *)v33 + v17);
      if ( v19 )
      {
        SysFreeString(v19);
        i = (int)v31;
      }
    }
    CoTaskMemFree(v33);
    v8 = a2;
  }
  if ( ProviderSchemaVersion < 0 )
    goto LABEL_68;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::TryPrintSupportValidation",
    L"Try retrieving the driver's URI from the config file");
  bstrString = 0;
  ProviderSchemaVersion = UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                            (UniDrvUI::CPrintTicketProvider *)v14,
                            &bstrString);
  if ( ProviderSchemaVersion < 0
    || (ProviderSchemaVersion = NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
                                  (NPrintTicketUtil::CPrintTicketWrapper *)v41,
                                  (struct IXMLDOMDocument2 **)L"psf:PrintTicket",
                                  v20),
        ProviderSchemaVersion < 0) )
  {
    v13 = bstrString;
    goto LABEL_68;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::TryPrintSupportValidation",
    L"Convert the public portion via the shim");
  v13 = bstrString;
  LODWORD(ppv) = v36;
  ProviderSchemaVersion = publicdm::PublicDevmodeToJobTicket(
                            v8,
                            this[3],
                            bstrString,
                            *(const unsigned __int16 **)a4,
                            (struct _devicemodeW *)ppv,
                            (__int64)v41);
  if ( ProviderSchemaVersion < 0 )
    goto LABEL_68;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::TryPrintSupportValidation", L"Get print ticket XML");
  if ( !(_QWORD)v42 )
  {
    ProviderSchemaVersion = -2147467259;
    goto LABEL_68;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42 + 8LL))(v42);
  v12 = (LPVOID)v42;
  v39 = (LPVOID)v42;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::TryPrintSupportValidation",
    L"Invoke the providers conversion method to convert driver-specific converion");
  ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, LPVOID))(*v14 + 56LL))(
                            v14,
                            (unsigned int)a5,
                            *(_QWORD *)a4,
                            v12);
  if ( ProviderSchemaVersion < 0 )
  {
LABEL_68:
    if ( v13 )
      SysFreeString(v13);
    NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v41);
    (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    if ( v12 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v9 )
      CoUninitialize();
    if ( ProviderSchemaVersion < 0 )
      goto LABEL_83;
    v26 = pv;
    v27 = uBytes;
    if ( (_DWORD)a5 != (_DWORD)uBytes )
    {
      if ( *(_QWORD *)a4 )
      {
        LocalFree(*(HLOCAL *)a4);
        v27 = uBytes;
      }
      v28 = LocalAlloc(0, v27);
      *(_QWORD *)a4 = v28;
      if ( !v28 )
      {
        ProviderSchemaVersion = -2147024882;
        *a6 = 0;
        DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
          "UniDrvUI::TryPrintSupportValidation",
          L"Failed to allocate memory (hr = 0x%x)",
          2147942414LL);
LABEL_83:
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::TryPrintSupportValidation",
          L"Exit with (hr: 0x%x).",
          (unsigned int)ProviderSchemaVersion);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)ProviderSchemaVersion;
      }
      v27 = uBytes;
    }
    memcpy_0(*(void **)a4, v26, v27);
    *a6 = uBytes;
    if ( a7 )
      *(_QWORD *)a7 = *(_QWORD *)a4 + *(unsigned __int16 *)(*(_QWORD *)a4 + 68LL);
    goto LABEL_83;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::TryPrintSupportValidation", L"Invoking ValidatePrintTicket");
  v33 = 0;
  v34 = 0;
  (**(void (__fastcall ***)(LPVOID, GUID *, LPVOID *))v12)(v12, &GUID_0000000c_0000_0000_c000_000000000046, &v33);
  v21 = ValidatePrintTicket(a3, v33, &v34);
  ProviderSchemaVersion = v21;
  if ( v21 < 0 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::TryPrintSupportValidation",
      L"PSA Validation returned with (hr: 0x%x).",
      (unsigned int)v21);
LABEL_61:
    if ( v34 )
    {
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    if ( v33 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    if ( ProviderSchemaVersion >= 0 )
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::TryPrintSupportValidation",
        L"Convert the print ticket to DevMode");
      ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, LPVOID, _QWORD, _QWORD, SIZE_T *, LPVOID *))(*v14 + 48LL))(
                                v14,
                                v12,
                                (unsigned int)a5,
                                *(_QWORD *)a4,
                                &uBytes,
                                &pv);
    }
    goto LABEL_68;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 13;
  pvarg.llVal = v34;
  WORD2(v30) = 0;
  v31 = 0;
  v22 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
          &v31);
  if ( v22 >= 0 )
  {
    v48 = pvarg;
    v23 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, char *))(*(_QWORD *)v31 + 464LL))(
            v31,
            &v48,
            (char *)&v30 + 4);
    v24 = v31;
    if ( WORD2(v30) == 0xFFFF )
    {
      v25 = 0;
      if ( v31 )
      {
        v25 = v31;
        v24 = 0;
        v31 = 0;
      }
      if ( v12 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
        v24 = v31;
      }
      v12 = v25;
      v39 = v25;
    }
    else if ( v31 || v23 < 0 )
    {
      ProviderSchemaVersion = -2147467259;
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::TryPrintSupportValidation",
        L"PSA Unable to set validated PT to IXMLDOMDocument2");
      v24 = v31;
    }
    if ( v24 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_61;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::TryPrintSupportValidation",
    L"PSA Unable to set create IXMLDOMDocument2 for return");
  if ( v31 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v13 )
    SysFreeString(v13);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v41);
  (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v9 )
    CoUninitialize();
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180115610  mov     rax, rsp
0x180115613  mov     [rax+18h], r8
0x180115617  mov     [rax+10h], rdx
0x18011561b  mov     [rax+8], rcx
0x18011561f  push    rbp
0x180115620  push    rsi
0x180115621  push    rdi
0x180115622  push    r12
0x180115624  push    r13
0x180115626  push    r14
0x180115628  push    r15
0x18011562a  lea     rbp, [rax-47h]
0x18011562e  sub     rsp, 100h
0x180115635  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18011563d  mov     [rax+20h], rbx
0x180115641  mov     r13, r9
0x180115644  mov     r12, rdx
0x180115647  xor     esi, esi
0x180115649  mov     [rsp+130h+var_C0], esi
0x18011564d  mov     [rbp+3Fh+var_B0], esi
0x180115650  lea     rdx, aEnter_0; "Enter"
0x180115657  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x18011565e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115663  mov     dword ptr [rsp+130h+uBytes], esi
0x180115667  mov     [rsp+130h+pv], rsi
0x18011566c  mov     dil, sil
0x18011566f  mov     byte ptr [rsp+130h+var_F0], sil
0x180115674  xor     edx, edx; dwCoInit
0x180115676  xor     ecx, ecx; pvReserved
0x180115678  call    cs:__imp_CoInitializeEx
0x18011567f  nop     dword ptr [rax+rax+00h]
0x180115684  mov     ebx, eax
0x180115686  test    eax, eax
0x180115688  js      short loc_180115694
0x18011568a  mov     dil, 1
0x18011568d  mov     byte ptr [rsp+130h+var_F0], dil
0x180115692  jmp     short loc_18011569D
0x180115694  cmp     ebx, 80010106h
0x18011569a  cmovz   ebx, esi
0x18011569d  test    ebx, ebx
0x18011569f  jns     short loc_1801156D0
0x1801156a1  test    dil, dil
0x1801156a4  jz      short loc_1801156B3
0x1801156a6  call    cs:__imp_CoUninitialize
0x1801156ad  nop     dword ptr [rax+rax+00h]
0x1801156b2  nop
0x1801156b3  mov     rcx, [rsp+130h+pv]; pv
0x1801156b8  test    rcx, rcx
0x1801156bb  jz      short loc_1801156C9
0x1801156bd  call    cs:__imp_CoTaskMemFree
0x1801156c4  nop     dword ptr [rax+rax+00h]
0x1801156c9  mov     eax, ebx
0x1801156cb  jmp     loc_180115DBE
0x1801156d0  mov     r14, rsi
0x1801156d3  mov     [rbp+3Fh+var_A8], rsi
0x1801156d7  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x1801156de  mov     qword ptr [rbp+3Fh+var_98], rax
0x1801156e2  xorps   xmm0, xmm0
0x1801156e5  movdqu  [rbp+3Fh+var_90], xmm0
0x1801156ea  mov     [rbp+3Fh+var_80], rsi
0x1801156ee  mov     [rbp+3Fh+var_78], si
0x1801156f2  mov     [rbp+3Fh+var_74], esi
0x1801156f5  mov     r15, rsi
0x1801156f8  mov     [rbp+3Fh+bstrString], rsi
0x1801156fc  lea     rdx, qword_180239588; struct std::nothrow_t *
0x180115703  mov     ecx, 60h ; '`'; unsigned __int64
0x180115708  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18011570d  mov     rbx, rax
0x180115710  mov     [rbp+3Fh+var_A0], rax
0x180115714  test    rax, rax
0x180115717  jz      short loc_18011575A
0x180115719  lea     rax, ??_7CPrintTicketProvider@UniDrvUI@@6B@; const UniDrvUI::CPrintTicketProvider::`vftable'
0x180115720  mov     [rbx], rax
0x180115723  mov     [rbx+8], rsi
0x180115727  mov     [rbx+10h], rsi
0x18011572b  mov     [rbx+18h], rsi
0x18011572f  mov     [rbx+20h], rsi
0x180115733  mov     dword ptr [rbx+28h], 1
0x18011573a  mov     [rbx+30h], rsi
0x18011573e  mov     [rbx+38h], rsi
0x180115742  mov     [rbx+48h], rsi
0x180115746  mov     [rbx+50h], rsi
0x18011574a  mov     [rbx+58h], rsi
0x18011574e  lock inc cs:?g_cComponents@UniDrvUI@@3JA; long UniDrvUI::g_cComponents
0x180115755  test    rbx, rbx
0x180115758  jnz     short loc_18011575D
0x18011575a  mov     rbx, rsi
0x18011575d  mov     [rbp+3Fh+var_A0], rbx
0x180115761  test    rbx, rbx
0x180115764  jnz     short loc_1801157A2
0x180115766  lea     rcx, [rbp+3Fh+var_98]; this
0x18011576a  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18011576f  nop
0x180115770  test    dil, dil
0x180115773  jz      short loc_180115782
0x180115775  call    cs:__imp_CoUninitialize
0x18011577c  nop     dword ptr [rax+rax+00h]
0x180115781  nop
0x180115782  mov     rcx, [rsp+130h+pv]; pv
0x180115787  test    rcx, rcx
0x18011578a  jz      short loc_180115798
0x18011578c  call    cs:__imp_CoTaskMemFree
0x180115793  nop     dword ptr [rax+rax+00h]
0x180115798  mov     eax, 80004005h
0x18011579d  jmp     loc_180115DBE
0x1801157a2  mov     dword ptr [rsp+130h+var_F0+4], esi
0x1801157a6  lea     r8, [rsp+130h+var_F0+4]; struct UniDrvUI::CPrintTicketProvider *
0x1801157ab  mov     rdx, rbx; void *
0x1801157ae  mov     rcx, r12; this
0x1801157b1  call    ?GetProviderSchemaVersion@UniDrvUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; UniDrvUI::GetProviderSchemaVersion(void *,UniDrvUI::CPrintTicketProvider *,int *)
0x1801157b6  mov     esi, eax
0x1801157b8  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x1801157bd  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x1801157c4  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801157cb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801157d0  test    esi, esi
0x1801157d2  js      loc_180115C97
0x1801157d8  mov     dword ptr [rsp+130h+var_E8], 0
0x1801157e0  mov     [rsp+130h+var_D8], 0
0x1801157e9  lea     rdx, aBindWithThePri; "Bind with the printer"
0x1801157f0  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801157f7  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801157fc  mov     rax, [rbx]
0x1801157ff  lea     rcx, [rsp+130h+var_D8]
0x180115804  mov     [rsp+30h], rcx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180115809  lea     rcx, [rsp+130h+var_E8]
0x18011580e  mov     qword ptr [rsp+130h+var_108], rcx
0x180115813  lea     rcx, [rsp+130h+var_C0]
0x180115818  mov     [rsp+130h+ppv], rcx
0x18011581d  lea     r9, [rbp+3Fh+var_B0]
0x180115821  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x180115826  mov     rdx, r12
0x180115829  mov     rcx, rbx
0x18011582c  mov     rax, [rax+20h]
0x180115830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115835  mov     esi, eax
0x180115837  cmp     [rsp+130h+var_D8], 0
0x18011583d  jz      short loc_18011589B
0x18011583f  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x180115846  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x18011584d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115852  xor     r12d, r12d
0x180115855  mov     edx, dword ptr [rsp+130h+var_E8]
0x180115859  test    edx, edx
0x18011585b  jle     short loc_180115886
0x18011585d  movsxd  rcx, r12d
0x180115860  mov     rax, [rsp+130h+var_D8]
0x180115865  mov     rcx, [rax+rcx*8]; bstrString
0x180115869  test    rcx, rcx
0x18011586c  jz      short loc_18011587E
0x18011586e  call    cs:__imp_SysFreeString
0x180115875  nop     dword ptr [rax+rax+00h]
0x18011587a  mov     edx, dword ptr [rsp+130h+var_E8]
0x18011587e  inc     r12d
0x180115881  cmp     r12d, edx
0x180115884  jl      short loc_18011585D
0x180115886  mov     rcx, [rsp+130h+var_D8]; pv
0x18011588b  call    cs:__imp_CoTaskMemFree
0x180115892  nop     dword ptr [rax+rax+00h]
0x180115897  mov     r12, [rbp+3Fh+arg_8]
0x18011589b  test    esi, esi
0x18011589d  js      loc_180115C97
0x1801158a3  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x1801158aa  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801158b1  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801158b6  mov     [rbp+3Fh+bstrString], 0
0x1801158be  lea     rdx, [rbp+3Fh+bstrString]; unsigned __int16 **
0x1801158c2  mov     rcx, rbx; this
0x1801158c5  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@UniDrvUI@@QEAAJPEAPEAG@Z; UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x1801158ca  mov     esi, eax
0x1801158cc  test    eax, eax
0x1801158ce  js      loc_180115C93
0x1801158d4  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x1801158db  lea     rcx, [rbp+3Fh+var_98]; this
0x1801158df  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x1801158e4  mov     esi, eax
0x1801158e6  test    eax, eax
0x1801158e8  js      loc_180115C93
0x1801158ee  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x1801158f5  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801158fc  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115901  mov     eax, [rsp+130h+var_C0]
0x180115905  mov     r15, [rbp+3Fh+bstrString]
0x180115909  lea     rcx, [rbp+3Fh+var_98]
0x18011590d  mov     qword ptr [rsp+130h+var_108], rcx; unsigned int
0x180115912  mov     dword ptr [rsp+130h+ppv], eax; struct _devicemodeW *
0x180115916  mov     r9, [r13+0]; unsigned __int16 *
0x18011591a  mov     r8, r15; unsigned __int16 *
0x18011591d  mov     rdx, [rbp+3Fh+arg_0]
0x180115921  mov     rdx, [rdx+18h]; void *
0x180115925  mov     rcx, r12; this
0x180115928  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18011592d  mov     esi, eax
0x18011592f  test    eax, eax
0x180115931  js      loc_180115C97
0x180115937  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x18011593e  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180115945  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011594a  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x18011594e  test    rcx, rcx
0x180115951  jnz     short loc_18011595D
0x180115953  mov     esi, 80004005h
0x180115958  jmp     loc_180115C97
0x18011595d  mov     rax, [rcx]
0x180115960  mov     rax, [rax+8]
0x180115964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115969  mov     r14, qword ptr [rbp+3Fh+var_90]
0x18011596d  mov     [rbp+3Fh+var_A8], r14
0x180115971  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x180115978  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x18011597f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180115984  mov     rax, [rbx]
0x180115987  mov     r9, r14
0x18011598a  mov     r8, [r13+0]
0x18011598e  mov     edx, dword ptr [rbp+3Fh+arg_20]
0x180115991  mov     rcx, rbx
0x180115994  mov     rax, [rax+38h]
0x180115998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011599d  mov     esi, eax
0x18011599f  test    eax, eax
0x1801159a1  js      loc_180115C97
0x1801159a7  lea     rdx, aInvokingValida; "Invoking ValidatePrintTicket"
0x1801159ae  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801159b5  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801159ba  mov     [rsp+130h+var_D8], 0
0x1801159c3  mov     [rsp+130h+var_D0], 0
0x1801159cc  mov     rax, [r14]
0x1801159cf  lea     r8, [rsp+130h+var_D8]
0x1801159d4  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1801159db  mov     rcx, r14
0x1801159de  mov     rax, [rax]
0x1801159e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801159e6  lea     r8, [rsp+130h+var_D0]
0x1801159eb  mov     rdx, [rsp+130h+var_D8]
0x1801159f0  mov     rcx, [rbp+3Fh+arg_10]
0x1801159f4  call    cs:__imp_ValidatePrintTicket
0x1801159fb  nop     dword ptr [rax+rax+00h]
0x180115a00  mov     esi, eax
0x180115a02  test    eax, eax
0x180115a04  jns     short loc_180115A21
0x180115a06  mov     r8d, eax
0x180115a09  lea     rdx, aPsaValidationR; "PSA Validation returned with (hr: 0x%x)"...
0x180115a10  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180115a17  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180115a1c  jmp     loc_180115C14
0x180115a21  xorps   xmm0, xmm0
0x180115a24  xor     eax, eax
0x180115a26  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180115a2a  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180115a2e  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180115a32  call    cs:__imp_VariantInit
0x180115a39  nop     dword ptr [rax+rax+00h]
0x180115a3e  mov     eax, 0Dh
0x180115a43  mov     word ptr [rbp+3Fh+pvarg], ax
0x180115a47  mov     rax, [rsp+130h+var_D0]
0x180115a4c  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x180115a50  xor     eax, eax
0x180115a52  mov     word ptr [rsp+130h+var_F0+4], ax
0x180115a57  mov     [rsp+130h+var_E8], rax
0x180115a5c  lea     rax, [rsp+130h+var_E8]
0x180115a61  mov     [rsp+130h+ppv], rax; ppv
0x180115a66  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180115a6d  xor     edx, edx; pUnkOuter
0x180115a6f  lea     r8d, [rdx+1]; dwClsContext
0x180115a73  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180115a7a  call    cs:__imp_CoCreateInstance
0x180115a81  nop     dword ptr [rax+rax+00h]
0x180115a86  mov     r12d, eax
0x180115a89  test    eax, eax
0x180115a8b  jns     loc_180115B6C
0x180115a91  lea     rdx, aPsaUnableToSet; "PSA Unable to set create IXMLDOMDocumen"...
0x180115a98  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180115a9f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180115aa4  nop
0x180115aa5  mov     rcx, [rsp+130h+var_E8]
0x180115aaa  xor     esi, esi
0x180115aac  test    rcx, rcx
0x180115aaf  jz      short loc_180115AC2
0x180115ab1  mov     rax, [rcx]
0x180115ab4  mov     rax, [rax+10h]
0x180115ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115abd  mov     [rsp+130h+var_E8], rsi
0x180115ac2  mov     rcx, [rsp+130h+var_D0]
0x180115ac7  test    rcx, rcx
0x180115aca  jz      short loc_180115ADD
0x180115acc  mov     rax, [rcx]
0x180115acf  mov     rax, [rax+10h]
0x180115ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115ad8  mov     [rsp+130h+var_D0], rsi
0x180115add  mov     rcx, [rsp+130h+var_D8]
0x180115ae2  test    rcx, rcx
0x180115ae5  jz      short loc_180115AF8
0x180115ae7  mov     rax, [rcx]
0x180115aea  mov     rax, [rax+10h]
0x180115aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115af3  mov     [rsp+130h+var_D8], rsi
0x180115af8  test    r15, r15
0x180115afb  jz      short loc_180115B0D
0x180115afd  mov     rcx, r15; bstrString
0x180115b00  call    cs:__imp_SysFreeString
  ... truncated ...
```
