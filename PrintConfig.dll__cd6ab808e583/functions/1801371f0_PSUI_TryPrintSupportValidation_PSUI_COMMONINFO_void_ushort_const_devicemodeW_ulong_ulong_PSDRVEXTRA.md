# PSUI::TryPrintSupportValidation(PSUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_PSDRVEXTRA * *)

- ea: `0x1801371f0`
- end: `0x18013794d`
- name: `?TryPrintSupportValidation@PSUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_PSDRVEXTRA@@@Z`
- size: `1885`
- prototype: `int(PSUI *__hidden this, struct PSUI::_COMMONINFO *, void *, const unsigned __int16 *, struct _devicemodeW **, unsigned int, unsigned int *, struct _PSDRVEXTRA **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801336a0`
- `0x18013534c`

## callees

- `0x180003b44`
- `0x1800ea034`
- `0x1800fb18c`
- `0x180100818`
- `0x180102674`
- `0x18010427c`
- `0x180128f0c`
- `0x180135bfc`
- `0x1801371f0`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180137891`
- `KERNEL32!LocalFree` at `0x180137891`
- `KERNEL32!LocalAlloc` at `0x18013789f`
- `KERNEL32!LocalAlloc` at `0x18013789f`
- `OLEAUT32!__imp_SysFreeString` at `0x180137430`
- `OLEAUT32!__imp_SysFreeString` at `0x1801376a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180137831`
- `OLEAUT32!__imp_SysFreeString` at `0x180137430`
- `OLEAUT32!__imp_SysFreeString` at `0x1801376a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180137831`
- `OLEAUT32!__imp_VariantInit` at `0x1801375e2`
- `OLEAUT32!__imp_VariantInit` at `0x1801375e2`
- `ole32!CoCreateInstance` at `0x180137624`
- `ole32!CoCreateInstance` at `0x180137624`
- `ole32!CoInitializeEx` at `0x180137258`
- `ole32!CoInitializeEx` at `0x180137258`
- `ole32!CoUninitialize` at `0x180137280`
- `ole32!CoUninitialize` at `0x180137343`
- `ole32!CoUninitialize` at `0x1801376df`
- `ole32!CoUninitialize` at `0x18013786c`
- `ole32!CoUninitialize` at `0x180137280`
- `ole32!CoUninitialize` at `0x180137343`
- `ole32!CoUninitialize` at `0x1801376df`
- `ole32!CoUninitialize` at `0x18013786c`
- `ole32!CoTaskMemFree` at `0x180137291`
- `ole32!CoTaskMemFree` at `0x180137354`
- `ole32!CoTaskMemFree` at `0x180137447`
- `ole32!CoTaskMemFree` at `0x1801376f0`
- `ole32!CoTaskMemFree` at `0x18013792a`
- `ole32!CoTaskMemFree` at `0x180137291`
- `ole32!CoTaskMemFree` at `0x180137354`
- `ole32!CoTaskMemFree` at `0x180137447`
- `ole32!CoTaskMemFree` at `0x1801376f0`
- `ole32!CoTaskMemFree` at `0x18013792a`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x1801375aa`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x1801375aa`

## string_xrefs

- `0x1801374ed`: `Get print ticket XML`
- `0x180137459`: `Try retrieving the driver's URI from the config file`
- `0x180137635`: `PSA Unable to set create IXMLDOMDocument2 for return`
- `0x18013777c`: `PSA Unable to set validated PT to IXMLDOMDocument2`

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
  v14 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180232260);
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
  ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, PSUI *, _QWORD, int *, int *, LPVOID *))(*v14 + 32LL))(
                            v14,
                            v8,
                            HIDWORD(v30),
                            &v38,
                            &v36,
                            &v31);
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
                                  L"psf:PrintTicket",
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
                            (unsigned int)v41,
                            (struct NPrintTicketUtil::CPrintTicketWrapper *)&v33);
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
0x1801371f0  mov     rax, rsp
0x1801371f3  mov     [rax+18h], r8
0x1801371f7  mov     [rax+10h], rdx
0x1801371fb  mov     [rax+8], rcx
0x1801371ff  push    rbp
0x180137200  push    rsi
0x180137201  push    rdi
0x180137202  push    r12
0x180137204  push    r13
0x180137206  push    r14
0x180137208  push    r15
0x18013720a  lea     rbp, [rax-47h]
0x18013720e  sub     rsp, 100h
0x180137215  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18013721d  mov     [rax+20h], rbx
0x180137221  mov     r13, r9
0x180137224  mov     r12, rdx
0x180137227  xor     esi, esi
0x180137229  mov     [rsp+130h+var_C0], esi
0x18013722d  mov     [rbp+3Fh+var_B0], esi
0x180137230  lea     rdx, aEnter_0; "Enter"
0x180137237  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013723e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137243  mov     dword ptr [rsp+130h+uBytes], esi
0x180137247  mov     [rsp+130h+pv], rsi
0x18013724c  mov     dil, sil
0x18013724f  mov     byte ptr [rsp+130h+var_F0], sil
0x180137254  xor     edx, edx; dwCoInit
0x180137256  xor     ecx, ecx; pvReserved
0x180137258  call    cs:__imp_CoInitializeEx
0x18013725e  mov     ebx, eax
0x180137260  test    eax, eax
0x180137262  js      short loc_18013726E
0x180137264  mov     dil, 1
0x180137267  mov     byte ptr [rsp+130h+var_F0], dil
0x18013726c  jmp     short loc_180137277
0x18013726e  cmp     ebx, 80010106h
0x180137274  cmovz   ebx, esi
0x180137277  test    ebx, ebx
0x180137279  jns     short loc_18013729E
0x18013727b  test    dil, dil
0x18013727e  jz      short loc_180137287
0x180137280  call    cs:__imp_CoUninitialize
0x180137286  nop
0x180137287  mov     rcx, [rsp+130h+pv]; pv
0x18013728c  test    rcx, rcx
0x18013728f  jz      short loc_180137297
0x180137291  call    cs:__imp_CoTaskMemFree
0x180137297  mov     eax, ebx
0x180137299  jmp     loc_180137932
0x18013729e  mov     r14, rsi
0x1801372a1  mov     [rbp+3Fh+var_A8], rsi
0x1801372a5  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x1801372ac  mov     qword ptr [rbp+3Fh+var_98], rax
0x1801372b0  xorps   xmm0, xmm0
0x1801372b3  movdqu  [rbp+3Fh+var_90], xmm0
0x1801372b8  mov     [rbp+3Fh+var_80], rsi
0x1801372bc  mov     [rbp+3Fh+var_78], si
0x1801372c0  mov     [rbp+3Fh+var_74], esi
0x1801372c3  mov     r15, rsi
0x1801372c6  mov     [rbp+3Fh+bstrString], rsi
0x1801372ca  lea     rdx, qword_180232260; struct std::nothrow_t *
0x1801372d1  mov     ecx, 60h ; '`'; unsigned __int64
0x1801372d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801372db  mov     rbx, rax
0x1801372de  mov     [rbp+3Fh+var_A0], rax
0x1801372e2  test    rax, rax
0x1801372e5  jz      short loc_180137328
0x1801372e7  lea     rax, ??_7CPrintTicketProvider@PSUI@@6B@; const PSUI::CPrintTicketProvider::`vftable'
0x1801372ee  mov     [rbx], rax
0x1801372f1  mov     [rbx+8], rsi
0x1801372f5  mov     [rbx+10h], rsi
0x1801372f9  mov     [rbx+18h], rsi
0x1801372fd  mov     [rbx+20h], rsi
0x180137301  mov     dword ptr [rbx+28h], 1
0x180137308  mov     [rbx+30h], rsi
0x18013730c  mov     [rbx+38h], rsi
0x180137310  mov     [rbx+48h], rsi
0x180137314  mov     [rbx+50h], rsi
0x180137318  mov     [rbx+58h], rsi
0x18013731c  lock inc cs:?g_cComponents@PSUI@@3JA; long PSUI::g_cComponents
0x180137323  test    rbx, rbx
0x180137326  jnz     short loc_18013732B
0x180137328  mov     rbx, rsi
0x18013732b  mov     [rbp+3Fh+var_A0], rbx
0x18013732f  test    rbx, rbx
0x180137332  jnz     short loc_180137364
0x180137334  lea     rcx, [rbp+3Fh+var_98]; this
0x180137338  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18013733d  nop
0x18013733e  test    dil, dil
0x180137341  jz      short loc_18013734A
0x180137343  call    cs:__imp_CoUninitialize
0x180137349  nop
0x18013734a  mov     rcx, [rsp+130h+pv]; pv
0x18013734f  test    rcx, rcx
0x180137352  jz      short loc_18013735A
0x180137354  call    cs:__imp_CoTaskMemFree
0x18013735a  mov     eax, 80004005h
0x18013735f  jmp     loc_180137932
0x180137364  mov     dword ptr [rsp+130h+var_F0+4], esi
0x180137368  lea     r8, [rsp+130h+var_F0+4]; struct PSUI::CPrintTicketProvider *
0x18013736d  mov     rdx, rbx; void *
0x180137370  mov     rcx, r12; this
0x180137373  call    ?GetProviderSchemaVersion@PSUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; PSUI::GetProviderSchemaVersion(void *,PSUI::CPrintTicketProvider *,int *)
0x180137378  mov     esi, eax
0x18013737a  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x18013737f  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x180137386  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013738d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137392  test    esi, esi
0x180137394  js      loc_180137829
0x18013739a  mov     dword ptr [rsp+130h+var_E8], 0
0x1801373a2  mov     [rsp+130h+var_D8], 0
0x1801373ab  lea     rdx, aBindWithThePri; "Bind with the printer"
0x1801373b2  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x1801373b9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801373be  mov     rax, [rbx]
0x1801373c1  lea     rcx, [rsp+130h+var_D8]
0x1801373c6  mov     [rsp+30h], rcx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1801373cb  lea     rcx, [rsp+130h+var_E8]
0x1801373d0  mov     qword ptr [rsp+130h+var_108], rcx
0x1801373d5  lea     rcx, [rsp+130h+var_C0]
0x1801373da  mov     [rsp+130h+ppv], rcx
0x1801373df  lea     r9, [rbp+3Fh+var_B0]
0x1801373e3  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x1801373e8  mov     rdx, r12
0x1801373eb  mov     rcx, rbx
0x1801373ee  mov     rax, [rax+20h]
0x1801373f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801373f7  mov     esi, eax
0x1801373f9  cmp     [rsp+130h+var_D8], 0
0x1801373ff  jz      short loc_180137451
0x180137401  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x180137408  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013740f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137414  xor     r12d, r12d
0x180137417  mov     edx, dword ptr [rsp+130h+var_E8]
0x18013741b  test    edx, edx
0x18013741d  jle     short loc_180137442
0x18013741f  movsxd  rcx, r12d
0x180137422  mov     rax, [rsp+130h+var_D8]
0x180137427  mov     rcx, [rax+rcx*8]; bstrString
0x18013742b  test    rcx, rcx
0x18013742e  jz      short loc_18013743A
0x180137430  call    cs:__imp_SysFreeString
0x180137436  mov     edx, dword ptr [rsp+130h+var_E8]
0x18013743a  inc     r12d
0x18013743d  cmp     r12d, edx
0x180137440  jl      short loc_18013741F
0x180137442  mov     rcx, [rsp+130h+var_D8]; pv
0x180137447  call    cs:__imp_CoTaskMemFree
0x18013744d  mov     r12, [rbp+3Fh+arg_8]
0x180137451  test    esi, esi
0x180137453  js      loc_180137829
0x180137459  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x180137460  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x180137467  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013746c  mov     [rbp+3Fh+bstrString], 0
0x180137474  lea     rdx, [rbp+3Fh+bstrString]; unsigned __int16 **
0x180137478  mov     rcx, rbx; this
0x18013747b  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@PSUI@@QEAAJPEAPEAG@Z; PSUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x180137480  mov     esi, eax
0x180137482  test    eax, eax
0x180137484  js      loc_180137825
0x18013748a  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x180137491  lea     rcx, [rbp+3Fh+var_98]; this
0x180137495  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x18013749a  mov     esi, eax
0x18013749c  test    eax, eax
0x18013749e  js      loc_180137825
0x1801374a4  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x1801374ab  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x1801374b2  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801374b7  mov     eax, [rsp+130h+var_C0]
0x1801374bb  mov     r15, [rbp+3Fh+bstrString]
0x1801374bf  lea     rcx, [rbp+3Fh+var_98]
0x1801374c3  mov     qword ptr [rsp+130h+var_108], rcx; unsigned int
0x1801374c8  mov     dword ptr [rsp+130h+ppv], eax; struct _devicemodeW *
0x1801374cc  mov     r9, [r13+0]; unsigned __int16 *
0x1801374d0  mov     r8, r15; unsigned __int16 *
0x1801374d3  mov     rdx, [rbp+3Fh+arg_0]
0x1801374d7  mov     rdx, [rdx+18h]; void *
0x1801374db  mov     rcx, r12; this
0x1801374de  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x1801374e3  mov     esi, eax
0x1801374e5  test    eax, eax
0x1801374e7  js      loc_180137829
0x1801374ed  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x1801374f4  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x1801374fb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137500  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180137504  test    rcx, rcx
0x180137507  jnz     short loc_180137513
0x180137509  mov     esi, 80004005h
0x18013750e  jmp     loc_180137829
0x180137513  mov     rax, [rcx]
0x180137516  mov     rax, [rax+8]
0x18013751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013751f  mov     r14, qword ptr [rbp+3Fh+var_90]
0x180137523  mov     [rbp+3Fh+var_A8], r14
0x180137527  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x18013752e  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x180137535  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013753a  mov     rax, [rbx]
0x18013753d  mov     r9, r14
0x180137540  mov     r8, [r13+0]
0x180137544  mov     edx, dword ptr [rbp+3Fh+arg_20]
0x180137547  mov     rcx, rbx
0x18013754a  mov     rax, [rax+38h]
0x18013754e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137553  mov     esi, eax
0x180137555  test    eax, eax
0x180137557  js      loc_180137829
0x18013755d  lea     rdx, aInvokingValida; "Invoking ValidatePrintTicket"
0x180137564  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x18013756b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180137570  mov     [rsp+130h+var_D8], 0
0x180137579  mov     [rsp+130h+var_D0], 0
0x180137582  mov     rax, [r14]
0x180137585  lea     r8, [rsp+130h+var_D8]
0x18013758a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180137591  mov     rcx, r14
0x180137594  mov     rax, [rax]
0x180137597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013759c  lea     r8, [rsp+130h+var_D0]
0x1801375a1  mov     rdx, [rsp+130h+var_D8]
0x1801375a6  mov     rcx, [rbp+3Fh+arg_10]
0x1801375aa  call    cs:__imp_ValidatePrintTicket
0x1801375b0  mov     esi, eax
0x1801375b2  test    eax, eax
0x1801375b4  jns     short loc_1801375D1
0x1801375b6  mov     r8d, eax
0x1801375b9  lea     rdx, aPsaValidationR; "PSA Validation returned with (hr: 0x%x)"...
0x1801375c0  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x1801375c7  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801375cc  jmp     loc_1801377A6
0x1801375d1  xorps   xmm0, xmm0
0x1801375d4  xor     eax, eax
0x1801375d6  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x1801375da  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x1801375de  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1801375e2  call    cs:__imp_VariantInit
0x1801375e8  mov     eax, 0Dh
0x1801375ed  mov     word ptr [rbp+3Fh+pvarg], ax
0x1801375f1  mov     rax, [rsp+130h+var_D0]
0x1801375f6  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x1801375fa  xor     eax, eax
0x1801375fc  mov     word ptr [rsp+130h+var_F0+4], ax
0x180137601  mov     [rsp+130h+var_E8], rax
0x180137606  lea     rax, [rsp+130h+var_E8]
0x18013760b  mov     [rsp+130h+ppv], rax; ppv
0x180137610  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180137617  xor     edx, edx; pUnkOuter
0x180137619  lea     r8d, [rdx+1]; dwClsContext
0x18013761d  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180137624  call    cs:__imp_CoCreateInstance
0x18013762a  mov     r12d, eax
0x18013762d  test    eax, eax
0x18013762f  jns     loc_1801376FE
0x180137635  lea     rdx, aPsaUnableToSet; "PSA Unable to set create IXMLDOMDocumen"...
0x18013763c  lea     rcx, aPsuiTryprintsu; "PSUI::TryPrintSupportValidation"
0x180137643  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180137648  nop
0x180137649  mov     rcx, [rsp+130h+var_E8]
0x18013764e  xor     esi, esi
0x180137650  test    rcx, rcx
0x180137653  jz      short loc_180137666
0x180137655  mov     rax, [rcx]
0x180137658  mov     rax, [rax+10h]
0x18013765c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137661  mov     [rsp+130h+var_E8], rsi
0x180137666  mov     rcx, [rsp+130h+var_D0]
0x18013766b  test    rcx, rcx
0x18013766e  jz      short loc_180137681
0x180137670  mov     rax, [rcx]
0x180137673  mov     rax, [rax+10h]
0x180137677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013767c  mov     [rsp+130h+var_D0], rsi
0x180137681  mov     rcx, [rsp+130h+var_D8]
0x180137686  test    rcx, rcx
0x180137689  jz      short loc_18013769C
0x18013768b  mov     rax, [rcx]
0x18013768e  mov     rax, [rax+10h]
0x180137692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137697  mov     [rsp+130h+var_D8], rsi
0x18013769c  test    r15, r15
0x18013769f  jz      short loc_1801376AB
0x1801376a1  mov     rcx, r15; bstrString
0x1801376a4  call    cs:__imp_SysFreeString
0x1801376aa  nop
0x1801376ab  lea     rcx, [rbp+3Fh+var_98]; this
0x1801376af  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1801376b4  nop
0x1801376b5  mov     rax, [rbx]
0x1801376b8  mov     rcx, rbx
0x1801376bb  mov     rax, [rax+10h]
0x1801376bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801376c4  nop
0x1801376c5  test    r14, r14
  ... truncated ...
```
