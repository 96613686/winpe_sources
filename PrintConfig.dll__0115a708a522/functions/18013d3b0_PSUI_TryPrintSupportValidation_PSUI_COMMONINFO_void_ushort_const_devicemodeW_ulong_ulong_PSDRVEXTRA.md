# PSUI::TryPrintSupportValidation(PSUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)

- ea: `0x18013d3b0`
- end: `0x18013db7a`
- name: `?TryPrintSupportValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z`
- size: `1994`
- prototype: `__int64 __fastcall(void **this, struct PSUI::_COMMONINFO *, void *, unsigned __int16 *, struct _devicemodeW **, _DWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801396d8`
- `0x18013b3d4`

## callees

- `0x180003c64`
- `0x1800ee8cc`
- `0x1800ffc98`
- `0x180105360`
- `0x180107214`
- `0x180108e2c`
- `0x18012ec04`
- `0x18013bccc`
- `0x18013d3b0`
- `0x1801b56bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18013daab`
- `KERNEL32!LocalFree` at `0x18013daab`
- `KERNEL32!LocalAlloc` at `0x18013dabf`
- `KERNEL32!LocalAlloc` at `0x18013dabf`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d60e`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d8a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18013da3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d60e`
- `OLEAUT32!__imp_SysFreeString` at `0x18013d8a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18013da3f`
- `OLEAUT32!__imp_VariantInit` at `0x18013d7d2`
- `OLEAUT32!__imp_VariantInit` at `0x18013d7d2`
- `ole32!CoCreateInstance` at `0x18013d81a`
- `ole32!CoCreateInstance` at `0x18013d81a`
- `ole32!CoInitializeEx` at `0x18013d418`
- `ole32!CoInitializeEx` at `0x18013d418`
- `ole32!CoUninitialize` at `0x18013d446`
- `ole32!CoUninitialize` at `0x18013d515`
- `ole32!CoUninitialize` at `0x18013d8e1`
- `ole32!CoUninitialize` at `0x18013da80`
- `ole32!CoUninitialize` at `0x18013d446`
- `ole32!CoUninitialize` at `0x18013d515`
- `ole32!CoUninitialize` at `0x18013d8e1`
- `ole32!CoUninitialize` at `0x18013da80`
- `ole32!CoTaskMemFree` at `0x18013d45d`
- `ole32!CoTaskMemFree` at `0x18013d52c`
- `ole32!CoTaskMemFree` at `0x18013d62b`
- `ole32!CoTaskMemFree` at `0x18013d8f8`
- `ole32!CoTaskMemFree` at `0x18013db50`
- `ole32!CoTaskMemFree` at `0x18013d45d`
- `ole32!CoTaskMemFree` at `0x18013d52c`
- `ole32!CoTaskMemFree` at `0x18013d62b`
- `ole32!CoTaskMemFree` at `0x18013d8f8`
- `ole32!CoTaskMemFree` at `0x18013db50`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x18013d794`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x18013d794`

## string_xrefs

- `0x18013d643`: `Try retrieving the driver's URI from the config file`
- `0x18013d6d7`: `Get print ticket XML`
- `0x18013d98a`: `PSA Unable to set validated PT to IXMLDOMDocument2`
- `0x18013d831`: `PSA Unable to set create IXMLDOMDocument2 for return`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall PSUI::TryPrintSupportValidation(
        void **this,
        struct PSUI::_COMMONINFO *a2,
        void *a3,
        unsigned __int16 *a4,
        struct _devicemodeW **a5,
        _DWORD *a6,
        unsigned int *a7)
{
  PSUI *v8; // r12
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
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::TryPrintSupportValidation", L"Enter");
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
  v14 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180239F68);
  v40 = v14;
  if ( v14 )
  {
    *v14 = &PSUI::CPrintTicketProvider::`vftable';
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
    _InterlockedIncrement(&PSUI::g_cComponents);
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
  ProviderSchemaVersion = PSUI::GetProviderSchemaVersion(
                            v8,
                            v14,
                            (struct PSUI::CPrintTicketProvider *)((char *)&v30 + 4),
                            v15);
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::TryPrintSupportValidation",
    L"Get the Provider Schema's version:  %d.",
    HIDWORD(v30));
  if ( ProviderSchemaVersion < 0 )
    goto LABEL_68;
  LODWORD(v31) = 0;
  v33 = 0;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::TryPrintSupportValidation", L"Bind with the printer");
  ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, PSUI *, _QWORD, int *, int *, LPVOID *, LPVOID *))(*v14 + 32LL))(
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
      "PSUI::TryPrintSupportValidation",
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
    "PSUI::TryPrintSupportValidation",
    L"Try retrieving the driver's URI from the config file");
  bstrString = 0;
  ProviderSchemaVersion = PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(
                            (PSUI::CPrintTicketProvider *)v14,
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
    "PSUI::TryPrintSupportValidation",
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
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::TryPrintSupportValidation", L"Get print ticket XML");
  if ( !(_QWORD)v42 )
  {
    ProviderSchemaVersion = -2147467259;
    goto LABEL_68;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42 + 8LL))(v42);
  v12 = (LPVOID)v42;
  v39 = (LPVOID)v42;
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::TryPrintSupportValidation",
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
          "PSUI::TryPrintSupportValidation",
          L"Failed to allocate memory (hr = 0x%x)",
          2147942414LL);
LABEL_83:
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::TryPrintSupportValidation",
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
  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::TryPrintSupportValidation", L"Invoking ValidatePrintTicket");
  v33 = 0;
  v34 = 0;
  (**(void (__fastcall ***)(LPVOID, GUID *, LPVOID *))v12)(v12, &GUID_0000000c_0000_0000_c000_000000000046, &v33);
  v21 = ValidatePrintTicket(a3, v33, &v34);
  ProviderSchemaVersion = v21;
  if ( v21 < 0 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "PSUI::TryPrintSupportValidation",
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
        "PSUI::TryPrintSupportValidation",
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
        "PSUI::TryPrintSupportValidation",
        L"PSA Unable to set validated PT to IXMLDOMDocument2");
      v24 = v31;
    }
    if ( v24 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_61;
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "PSUI::TryPrintSupportValidation",
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
0x18013d3b0  mov     rax, rsp
0x18013d3b3  mov     [rax+18h], r8
0x18013d3b7  mov     [rax+10h], rdx
0x18013d3bb  mov     [rax+8], rcx
0x18013d3bf  push    rbp
0x18013d3c0  push    rsi
0x18013d3c1  push    rdi
0x18013d3c2  push    r12
0x18013d3c4  push    r13
0x18013d3c6  push    r14
0x18013d3c8  push    r15
0x18013d3ca  lea     rbp, [rax-47h]
0x18013d3ce  sub     rsp, 100h
0x18013d3d5  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18013d3dd  mov     [rax+20h], rbx
0x18013d3e1  mov     r13, r9
0x18013d3e4  mov     r12, rdx
0x18013d3e7  xor     esi, esi
0x18013d3e9  mov     [rsp+130h+var_C0], esi
0x18013d3ed  mov     [rbp+3Fh+var_B0], esi
0x18013d3f0  lea     rdx, aEnter_0; "Enter"
0x18013d3f7  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d3fe  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d403  mov     dword ptr [rsp+130h+uBytes], esi
0x18013d407  mov     [rsp+130h+pv], rsi
0x18013d40c  mov     dil, sil
0x18013d40f  mov     byte ptr [rsp+130h+var_F0], sil
0x18013d414  xor     edx, edx; dwCoInit
0x18013d416  xor     ecx, ecx; pvReserved
0x18013d418  call    cs:__imp_CoInitializeEx
0x18013d41f  nop     dword ptr [rax+rax+00h]
0x18013d424  mov     ebx, eax
0x18013d426  test    eax, eax
0x18013d428  js      short loc_18013D434
0x18013d42a  mov     dil, 1
0x18013d42d  mov     byte ptr [rsp+130h+var_F0], dil
0x18013d432  jmp     short loc_18013D43D
0x18013d434  cmp     ebx, 80010106h
0x18013d43a  cmovz   ebx, esi
0x18013d43d  test    ebx, ebx
0x18013d43f  jns     short loc_18013D470
0x18013d441  test    dil, dil
0x18013d444  jz      short loc_18013D453
0x18013d446  call    cs:__imp_CoUninitialize
0x18013d44d  nop     dword ptr [rax+rax+00h]
0x18013d452  nop
0x18013d453  mov     rcx, [rsp+130h+pv]; pv
0x18013d458  test    rcx, rcx
0x18013d45b  jz      short loc_18013D469
0x18013d45d  call    cs:__imp_CoTaskMemFree
0x18013d464  nop     dword ptr [rax+rax+00h]
0x18013d469  mov     eax, ebx
0x18013d46b  jmp     loc_18013DB5E
0x18013d470  mov     r14, rsi
0x18013d473  mov     [rbp+3Fh+var_A8], rsi
0x18013d477  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18013d47e  mov     qword ptr [rbp+3Fh+var_98], rax
0x18013d482  xorps   xmm0, xmm0
0x18013d485  movdqu  [rbp+3Fh+var_90], xmm0
0x18013d48a  mov     [rbp+3Fh+var_80], rsi
0x18013d48e  mov     [rbp+3Fh+var_78], si
0x18013d492  mov     [rbp+3Fh+var_74], esi
0x18013d495  mov     r15, rsi
0x18013d498  mov     [rbp+3Fh+bstrString], rsi
0x18013d49c  lea     rdx, qword_180239F68; struct std::nothrow_t *
0x18013d4a3  mov     ecx, 60h ; '`'; unsigned __int64
0x18013d4a8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18013d4ad  mov     rbx, rax
0x18013d4b0  mov     [rbp+3Fh+var_A0], rax
0x18013d4b4  test    rax, rax
0x18013d4b7  jz      short loc_18013D4FA
0x18013d4b9  lea     rax, ??_7CPrintTicketProvider@PSUI@@6B@; const PSUI::CPrintTicketProvider::`vftable'
0x18013d4c0  mov     [rbx], rax
0x18013d4c3  mov     [rbx+8], rsi
0x18013d4c7  mov     [rbx+10h], rsi
0x18013d4cb  mov     [rbx+18h], rsi
0x18013d4cf  mov     [rbx+20h], rsi
0x18013d4d3  mov     dword ptr [rbx+28h], 1
0x18013d4da  mov     [rbx+30h], rsi
0x18013d4de  mov     [rbx+38h], rsi
0x18013d4e2  mov     [rbx+48h], rsi
0x18013d4e6  mov     [rbx+50h], rsi
0x18013d4ea  mov     [rbx+58h], rsi
0x18013d4ee  lock inc cs:?g_cComponents@PSUI@@3JA; long PSUI::g_cComponents
0x18013d4f5  test    rbx, rbx
0x18013d4f8  jnz     short loc_18013D4FD
0x18013d4fa  mov     rbx, rsi
0x18013d4fd  mov     [rbp+3Fh+var_A0], rbx
0x18013d501  test    rbx, rbx
0x18013d504  jnz     short loc_18013D542
0x18013d506  lea     rcx, [rbp+3Fh+var_98]; this
0x18013d50a  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18013d50f  nop
0x18013d510  test    dil, dil
0x18013d513  jz      short loc_18013D522
0x18013d515  call    cs:__imp_CoUninitialize
0x18013d51c  nop     dword ptr [rax+rax+00h]
0x18013d521  nop
0x18013d522  mov     rcx, [rsp+130h+pv]; pv
0x18013d527  test    rcx, rcx
0x18013d52a  jz      short loc_18013D538
0x18013d52c  call    cs:__imp_CoTaskMemFree
0x18013d533  nop     dword ptr [rax+rax+00h]
0x18013d538  mov     eax, 80004005h
0x18013d53d  jmp     loc_18013DB5E
0x18013d542  mov     dword ptr [rsp+130h+var_F0+4], esi
0x18013d546  lea     r8, [rsp+130h+var_F0+4]; struct PSUI::CPrintTicketProvider *
0x18013d54b  mov     rdx, rbx; void *
0x18013d54e  mov     rcx, r12; this
0x18013d551  call    ?GetProviderSchemaVersion@PSUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; PSUI::GetProviderSchemaVersion(void *,PSUI::CPrintTicketProvider *,int *)
0x18013d556  mov     esi, eax
0x18013d558  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x18013d55d  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x18013d564  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d56b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d570  test    esi, esi
0x18013d572  js      loc_18013DA37
0x18013d578  mov     dword ptr [rsp+130h+var_E8], 0
0x18013d580  mov     [rsp+130h+var_D8], 0
0x18013d589  lea     rdx, aBindWithThePri; "Bind with the printer"
0x18013d590  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d597  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d59c  mov     rax, [rbx]
0x18013d59f  lea     rcx, [rsp+130h+var_D8]
0x18013d5a4  mov     [rsp+30h], rcx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18013d5a9  lea     rcx, [rsp+130h+var_E8]
0x18013d5ae  mov     qword ptr [rsp+130h+var_108], rcx
0x18013d5b3  lea     rcx, [rsp+130h+var_C0]
0x18013d5b8  mov     [rsp+130h+ppv], rcx
0x18013d5bd  lea     r9, [rbp+3Fh+var_B0]
0x18013d5c1  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x18013d5c6  mov     rdx, r12
0x18013d5c9  mov     rcx, rbx
0x18013d5cc  mov     rax, [rax+20h]
0x18013d5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d5d5  mov     esi, eax
0x18013d5d7  cmp     [rsp+130h+var_D8], 0
0x18013d5dd  jz      short loc_18013D63B
0x18013d5df  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x18013d5e6  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d5ed  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d5f2  xor     r12d, r12d
0x18013d5f5  mov     edx, dword ptr [rsp+130h+var_E8]
0x18013d5f9  test    edx, edx
0x18013d5fb  jle     short loc_18013D626
0x18013d5fd  movsxd  rcx, r12d
0x18013d600  mov     rax, [rsp+130h+var_D8]
0x18013d605  mov     rcx, [rax+rcx*8]; bstrString
0x18013d609  test    rcx, rcx
0x18013d60c  jz      short loc_18013D61E
0x18013d60e  call    cs:__imp_SysFreeString
0x18013d615  nop     dword ptr [rax+rax+00h]
0x18013d61a  mov     edx, dword ptr [rsp+130h+var_E8]
0x18013d61e  inc     r12d
0x18013d621  cmp     r12d, edx
0x18013d624  jl      short loc_18013D5FD
0x18013d626  mov     rcx, [rsp+130h+var_D8]; pv
0x18013d62b  call    cs:__imp_CoTaskMemFree
0x18013d632  nop     dword ptr [rax+rax+00h]
0x18013d637  mov     r12, [rbp+3Fh+arg_8]
0x18013d63b  test    esi, esi
0x18013d63d  js      loc_18013DA37
0x18013d643  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x18013d64a  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d651  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d656  mov     [rbp+3Fh+bstrString], 0
0x18013d65e  lea     rdx, [rbp+3Fh+bstrString]; unsigned __int16 **
0x18013d662  mov     rcx, rbx; this
0x18013d665  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@PSUI@@QEAAJPEAPEAG@Z; PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x18013d66a  mov     esi, eax
0x18013d66c  test    eax, eax
0x18013d66e  js      loc_18013DA33
0x18013d674  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x18013d67b  lea     rcx, [rbp+3Fh+var_98]; this
0x18013d67f  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x18013d684  mov     esi, eax
0x18013d686  test    eax, eax
0x18013d688  js      loc_18013DA33
0x18013d68e  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x18013d695  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d69c  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d6a1  mov     eax, [rsp+130h+var_C0]
0x18013d6a5  mov     r15, [rbp+3Fh+bstrString]
0x18013d6a9  lea     rcx, [rbp+3Fh+var_98]
0x18013d6ad  mov     qword ptr [rsp+130h+var_108], rcx; unsigned int
0x18013d6b2  mov     dword ptr [rsp+130h+ppv], eax; struct _devicemodeW *
0x18013d6b6  mov     r9, [r13+0]; unsigned __int16 *
0x18013d6ba  mov     r8, r15; unsigned __int16 *
0x18013d6bd  mov     rdx, [rbp+3Fh+arg_0]
0x18013d6c1  mov     rdx, [rdx+18h]; void *
0x18013d6c5  mov     rcx, r12; this
0x18013d6c8  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x18013d6cd  mov     esi, eax
0x18013d6cf  test    eax, eax
0x18013d6d1  js      loc_18013DA37
0x18013d6d7  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x18013d6de  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d6e5  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d6ea  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x18013d6ee  test    rcx, rcx
0x18013d6f1  jnz     short loc_18013D6FD
0x18013d6f3  mov     esi, 80004005h
0x18013d6f8  jmp     loc_18013DA37
0x18013d6fd  mov     rax, [rcx]
0x18013d700  mov     rax, [rax+8]
0x18013d704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d709  mov     r14, qword ptr [rbp+3Fh+var_90]
0x18013d70d  mov     [rbp+3Fh+var_A8], r14
0x18013d711  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x18013d718  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d71f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d724  mov     rax, [rbx]
0x18013d727  mov     r9, r14
0x18013d72a  mov     r8, [r13+0]
0x18013d72e  mov     edx, dword ptr [rbp+3Fh+arg_20]
0x18013d731  mov     rcx, rbx
0x18013d734  mov     rax, [rax+38h]
0x18013d738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d73d  mov     esi, eax
0x18013d73f  test    eax, eax
0x18013d741  js      loc_18013DA37
0x18013d747  lea     rdx, aInvokingValida; "Invoking ValidatePrintTicket"
0x18013d74e  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d755  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013d75a  mov     [rsp+130h+var_D8], 0
0x18013d763  mov     [rsp+130h+var_D0], 0
0x18013d76c  mov     rax, [r14]
0x18013d76f  lea     r8, [rsp+130h+var_D8]
0x18013d774  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18013d77b  mov     rcx, r14
0x18013d77e  mov     rax, [rax]
0x18013d781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d786  lea     r8, [rsp+130h+var_D0]
0x18013d78b  mov     rdx, [rsp+130h+var_D8]
0x18013d790  mov     rcx, [rbp+3Fh+arg_10]
0x18013d794  call    cs:__imp_ValidatePrintTicket
0x18013d79b  nop     dword ptr [rax+rax+00h]
0x18013d7a0  mov     esi, eax
0x18013d7a2  test    eax, eax
0x18013d7a4  jns     short loc_18013D7C1
0x18013d7a6  mov     r8d, eax
0x18013d7a9  lea     rdx, aPsaValidationR; "PSA Validation returned with (hr: 0x%x)"...
0x18013d7b0  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d7b7  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013d7bc  jmp     loc_18013D9B4
0x18013d7c1  xorps   xmm0, xmm0
0x18013d7c4  xor     eax, eax
0x18013d7c6  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18013d7ca  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x18013d7ce  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18013d7d2  call    cs:__imp_VariantInit
0x18013d7d9  nop     dword ptr [rax+rax+00h]
0x18013d7de  mov     eax, 0Dh
0x18013d7e3  mov     word ptr [rbp+3Fh+pvarg], ax
0x18013d7e7  mov     rax, [rsp+130h+var_D0]
0x18013d7ec  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x18013d7f0  xor     eax, eax
0x18013d7f2  mov     word ptr [rsp+130h+var_F0+4], ax
0x18013d7f7  mov     [rsp+130h+var_E8], rax
0x18013d7fc  lea     rax, [rsp+130h+var_E8]
0x18013d801  mov     [rsp+130h+ppv], rax; ppv
0x18013d806  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18013d80d  xor     edx, edx; pUnkOuter
0x18013d80f  lea     r8d, [rdx+1]; dwClsContext
0x18013d813  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18013d81a  call    cs:__imp_CoCreateInstance
0x18013d821  nop     dword ptr [rax+rax+00h]
0x18013d826  mov     r12d, eax
0x18013d829  test    eax, eax
0x18013d82b  jns     loc_18013D90C
0x18013d831  lea     rdx, aPsaUnableToSet; "PSA Unable to set create IXMLDOMDocumen"...
0x18013d838  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013d83f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013d844  nop
0x18013d845  mov     rcx, [rsp+130h+var_E8]
0x18013d84a  xor     esi, esi
0x18013d84c  test    rcx, rcx
0x18013d84f  jz      short loc_18013D862
0x18013d851  mov     rax, [rcx]
0x18013d854  mov     rax, [rax+10h]
0x18013d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d85d  mov     [rsp+130h+var_E8], rsi
0x18013d862  mov     rcx, [rsp+130h+var_D0]
0x18013d867  test    rcx, rcx
0x18013d86a  jz      short loc_18013D87D
0x18013d86c  mov     rax, [rcx]
0x18013d86f  mov     rax, [rax+10h]
0x18013d873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d878  mov     [rsp+130h+var_D0], rsi
0x18013d87d  mov     rcx, [rsp+130h+var_D8]
0x18013d882  test    rcx, rcx
0x18013d885  jz      short loc_18013D898
0x18013d887  mov     rax, [rcx]
0x18013d88a  mov     rax, [rax+10h]
0x18013d88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d893  mov     [rsp+130h+var_D8], rsi
0x18013d898  test    r15, r15
0x18013d89b  jz      short loc_18013D8AD
0x18013d89d  mov     rcx, r15; bstrString
0x18013d8a0  call    cs:__imp_SysFreeString
  ... truncated ...
```
