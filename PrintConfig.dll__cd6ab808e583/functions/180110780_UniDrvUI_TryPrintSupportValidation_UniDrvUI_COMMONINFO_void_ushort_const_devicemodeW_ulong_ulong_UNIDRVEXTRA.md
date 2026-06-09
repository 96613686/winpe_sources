# UniDrvUI::TryPrintSupportValidation(UniDrvUI::_COMMONINFO *,void *,ushort const *,_devicemodeW * *,ulong,ulong *,_UNIDRVEXTRA * *)

- ea: `0x180110780`
- end: `0x180110edd`
- name: `?TryPrintSupportValidation@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAXPEBGPEAPEAU_devicemodeW@@KPEAKPEAPEAU_UNIDRVEXTRA@@@Z`
- size: `1885`
- prototype: `int(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, void *, const unsigned __int16 *, struct _devicemodeW **, unsigned int, unsigned int *, struct _UNIDRVEXTRA **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010c380`
- `0x18010e5ac`

## callees

- `0x180003b44`
- `0x1800ea034`
- `0x1800f32a4`
- `0x1800fb18c`
- `0x180100818`
- `0x180102674`
- `0x18010427c`
- `0x18010ef50`
- `0x180110780`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180110e21`
- `KERNEL32!LocalFree` at `0x180110e21`
- `KERNEL32!LocalAlloc` at `0x180110e2f`
- `KERNEL32!LocalAlloc` at `0x180110e2f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801109c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180110c34`
- `OLEAUT32!__imp_SysFreeString` at `0x180110dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801109c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180110c34`
- `OLEAUT32!__imp_SysFreeString` at `0x180110dc1`
- `OLEAUT32!__imp_VariantInit` at `0x180110b72`
- `OLEAUT32!__imp_VariantInit` at `0x180110b72`
- `ole32!CoCreateInstance` at `0x180110bb4`
- `ole32!CoCreateInstance` at `0x180110bb4`
- `ole32!CoInitializeEx` at `0x1801107e8`
- `ole32!CoInitializeEx` at `0x1801107e8`
- `ole32!CoUninitialize` at `0x180110810`
- `ole32!CoUninitialize` at `0x1801108d3`
- `ole32!CoUninitialize` at `0x180110c6f`
- `ole32!CoUninitialize` at `0x180110dfc`
- `ole32!CoUninitialize` at `0x180110810`
- `ole32!CoUninitialize` at `0x1801108d3`
- `ole32!CoUninitialize` at `0x180110c6f`
- `ole32!CoUninitialize` at `0x180110dfc`
- `ole32!CoTaskMemFree` at `0x180110821`
- `ole32!CoTaskMemFree` at `0x1801108e4`
- `ole32!CoTaskMemFree` at `0x1801109d7`
- `ole32!CoTaskMemFree` at `0x180110c80`
- `ole32!CoTaskMemFree` at `0x180110eba`
- `ole32!CoTaskMemFree` at `0x180110821`
- `ole32!CoTaskMemFree` at `0x1801108e4`
- `ole32!CoTaskMemFree` at `0x1801109d7`
- `ole32!CoTaskMemFree` at `0x180110c80`
- `ole32!CoTaskMemFree` at `0x180110eba`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x180110b3a`
- `Print.PrintSupport.Source!ValidatePrintTicket` at `0x180110b3a`

## string_xrefs

- `0x180110a7d`: `Get print ticket XML`
- `0x1801109e9`: `Try retrieving the driver's URI from the config file`
- `0x180110bc5`: `PSA Unable to set create IXMLDOMDocument2 for return`
- `0x180110d0c`: `PSA Unable to set validated PT to IXMLDOMDocument2`

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
  v14 = operator new(0x60u, (const struct std::nothrow_t *)&qword_180231880);
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
  ProviderSchemaVersion = (*(__int64 (__fastcall **)(_QWORD *, UniDrvUI *, _QWORD, int *, int *, LPVOID *))(*v14 + 32LL))(
                            v14,
                            v8,
                            HIDWORD(v30),
                            &v38,
                            &v36,
                            &v31);
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
                                  L"psf:PrintTicket",
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
                            (unsigned int)v41,
                            (struct NPrintTicketUtil::CPrintTicketWrapper *)&v33);
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
0x180110780  mov     rax, rsp
0x180110783  mov     [rax+18h], r8
0x180110787  mov     [rax+10h], rdx
0x18011078b  mov     [rax+8], rcx
0x18011078f  push    rbp
0x180110790  push    rsi
0x180110791  push    rdi
0x180110792  push    r12
0x180110794  push    r13
0x180110796  push    r14
0x180110798  push    r15
0x18011079a  lea     rbp, [rax-47h]
0x18011079e  sub     rsp, 100h
0x1801107a5  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x1801107ad  mov     [rax+20h], rbx
0x1801107b1  mov     r13, r9
0x1801107b4  mov     r12, rdx
0x1801107b7  xor     esi, esi
0x1801107b9  mov     [rsp+130h+var_C0], esi
0x1801107bd  mov     [rbp+3Fh+var_B0], esi
0x1801107c0  lea     rdx, aEnter_0; "Enter"
0x1801107c7  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801107ce  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801107d3  mov     dword ptr [rsp+130h+uBytes], esi
0x1801107d7  mov     [rsp+130h+pv], rsi
0x1801107dc  mov     dil, sil
0x1801107df  mov     byte ptr [rsp+130h+var_F0], sil
0x1801107e4  xor     edx, edx; dwCoInit
0x1801107e6  xor     ecx, ecx; pvReserved
0x1801107e8  call    cs:__imp_CoInitializeEx
0x1801107ee  mov     ebx, eax
0x1801107f0  test    eax, eax
0x1801107f2  js      short loc_1801107FE
0x1801107f4  mov     dil, 1
0x1801107f7  mov     byte ptr [rsp+130h+var_F0], dil
0x1801107fc  jmp     short loc_180110807
0x1801107fe  cmp     ebx, 80010106h
0x180110804  cmovz   ebx, esi
0x180110807  test    ebx, ebx
0x180110809  jns     short loc_18011082E
0x18011080b  test    dil, dil
0x18011080e  jz      short loc_180110817
0x180110810  call    cs:__imp_CoUninitialize
0x180110816  nop
0x180110817  mov     rcx, [rsp+130h+pv]; pv
0x18011081c  test    rcx, rcx
0x18011081f  jz      short loc_180110827
0x180110821  call    cs:__imp_CoTaskMemFree
0x180110827  mov     eax, ebx
0x180110829  jmp     loc_180110EC2
0x18011082e  mov     r14, rsi
0x180110831  mov     [rbp+3Fh+var_A8], rsi
0x180110835  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18011083c  mov     qword ptr [rbp+3Fh+var_98], rax
0x180110840  xorps   xmm0, xmm0
0x180110843  movdqu  [rbp+3Fh+var_90], xmm0
0x180110848  mov     [rbp+3Fh+var_80], rsi
0x18011084c  mov     [rbp+3Fh+var_78], si
0x180110850  mov     [rbp+3Fh+var_74], esi
0x180110853  mov     r15, rsi
0x180110856  mov     [rbp+3Fh+bstrString], rsi
0x18011085a  lea     rdx, qword_180231880; struct std::nothrow_t *
0x180110861  mov     ecx, 60h ; '`'; unsigned __int64
0x180110866  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18011086b  mov     rbx, rax
0x18011086e  mov     [rbp+3Fh+var_A0], rax
0x180110872  test    rax, rax
0x180110875  jz      short loc_1801108B8
0x180110877  lea     rax, ??_7CPrintTicketProvider@UniDrvUI@@6B@; const UniDrvUI::CPrintTicketProvider::`vftable'
0x18011087e  mov     [rbx], rax
0x180110881  mov     [rbx+8], rsi
0x180110885  mov     [rbx+10h], rsi
0x180110889  mov     [rbx+18h], rsi
0x18011088d  mov     [rbx+20h], rsi
0x180110891  mov     dword ptr [rbx+28h], 1
0x180110898  mov     [rbx+30h], rsi
0x18011089c  mov     [rbx+38h], rsi
0x1801108a0  mov     [rbx+48h], rsi
0x1801108a4  mov     [rbx+50h], rsi
0x1801108a8  mov     [rbx+58h], rsi
0x1801108ac  lock inc cs:?g_cComponents@UniDrvUI@@3JA; long UniDrvUI::g_cComponents
0x1801108b3  test    rbx, rbx
0x1801108b6  jnz     short loc_1801108BB
0x1801108b8  mov     rbx, rsi
0x1801108bb  mov     [rbp+3Fh+var_A0], rbx
0x1801108bf  test    rbx, rbx
0x1801108c2  jnz     short loc_1801108F4
0x1801108c4  lea     rcx, [rbp+3Fh+var_98]; this
0x1801108c8  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x1801108cd  nop
0x1801108ce  test    dil, dil
0x1801108d1  jz      short loc_1801108DA
0x1801108d3  call    cs:__imp_CoUninitialize
0x1801108d9  nop
0x1801108da  mov     rcx, [rsp+130h+pv]; pv
0x1801108df  test    rcx, rcx
0x1801108e2  jz      short loc_1801108EA
0x1801108e4  call    cs:__imp_CoTaskMemFree
0x1801108ea  mov     eax, 80004005h
0x1801108ef  jmp     loc_180110EC2
0x1801108f4  mov     dword ptr [rsp+130h+var_F0+4], esi
0x1801108f8  lea     r8, [rsp+130h+var_F0+4]; struct UniDrvUI::CPrintTicketProvider *
0x1801108fd  mov     rdx, rbx; void *
0x180110900  mov     rcx, r12; this
0x180110903  call    ?GetProviderSchemaVersion@UniDrvUI@@YAJPEAXPEAVCPrintTicketProvider@1@PEAH@Z; UniDrvUI::GetProviderSchemaVersion(void *,UniDrvUI::CPrintTicketProvider *,int *)
0x180110908  mov     esi, eax
0x18011090a  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x18011090f  lea     rdx, aGetTheProvider; "Get the Provider Schema's version:  %d."
0x180110916  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x18011091d  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110922  test    esi, esi
0x180110924  js      loc_180110DB9
0x18011092a  mov     dword ptr [rsp+130h+var_E8], 0
0x180110932  mov     [rsp+130h+var_D8], 0
0x18011093b  lea     rdx, aBindWithThePri; "Bind with the printer"
0x180110942  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110949  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18011094e  mov     rax, [rbx]
0x180110951  lea     rcx, [rsp+130h+var_D8]
0x180110956  mov     [rsp+30h], rcx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18011095b  lea     rcx, [rsp+130h+var_E8]
0x180110960  mov     qword ptr [rsp+130h+var_108], rcx
0x180110965  lea     rcx, [rsp+130h+var_C0]
0x18011096a  mov     [rsp+130h+ppv], rcx
0x18011096f  lea     r9, [rbp+3Fh+var_B0]
0x180110973  mov     r8d, dword ptr [rsp+130h+var_F0+4]
0x180110978  mov     rdx, r12
0x18011097b  mov     rcx, rbx
0x18011097e  mov     rax, [rax+20h]
0x180110982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110987  mov     esi, eax
0x180110989  cmp     [rsp+130h+var_D8], 0
0x18011098f  jz      short loc_1801109E1
0x180110991  lea     rdx, aReleaseAnyName; "Release any namespaces the driver provi"...
0x180110998  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x18011099f  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801109a4  xor     r12d, r12d
0x1801109a7  mov     edx, dword ptr [rsp+130h+var_E8]
0x1801109ab  test    edx, edx
0x1801109ad  jle     short loc_1801109D2
0x1801109af  movsxd  rcx, r12d
0x1801109b2  mov     rax, [rsp+130h+var_D8]
0x1801109b7  mov     rcx, [rax+rcx*8]; bstrString
0x1801109bb  test    rcx, rcx
0x1801109be  jz      short loc_1801109CA
0x1801109c0  call    cs:__imp_SysFreeString
0x1801109c6  mov     edx, dword ptr [rsp+130h+var_E8]
0x1801109ca  inc     r12d
0x1801109cd  cmp     r12d, edx
0x1801109d0  jl      short loc_1801109AF
0x1801109d2  mov     rcx, [rsp+130h+var_D8]; pv
0x1801109d7  call    cs:__imp_CoTaskMemFree
0x1801109dd  mov     r12, [rbp+3Fh+arg_8]
0x1801109e1  test    esi, esi
0x1801109e3  js      loc_180110DB9
0x1801109e9  lea     rdx, aTryRetrievingT; "Try retrieving the driver's URI from th"...
0x1801109f0  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x1801109f7  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1801109fc  mov     [rbp+3Fh+bstrString], 0
0x180110a04  lea     rdx, [rbp+3Fh+bstrString]; unsigned __int16 **
0x180110a08  mov     rcx, rbx; this
0x180110a0b  call    ?GetNoPluginDriverNamespace@CPrintTicketProvider@UniDrvUI@@QEAAJPEAPEAG@Z; UniDrvUI::CPrintTicketProvider::GetNoPluginDriverNamespace(ushort * *)
0x180110a10  mov     esi, eax
0x180110a12  test    eax, eax
0x180110a14  js      loc_180110DB5
0x180110a1a  lea     rdx, aPsfPrintticket_0; "psf:PrintTicket"
0x180110a21  lea     rcx, [rbp+3Fh+var_98]; this
0x180110a25  call    ?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)
0x180110a2a  mov     esi, eax
0x180110a2c  test    eax, eax
0x180110a2e  js      loc_180110DB5
0x180110a34  lea     rdx, aConvertThePubl; "Convert the public portion via the shim"
0x180110a3b  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110a42  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110a47  mov     eax, [rsp+130h+var_C0]
0x180110a4b  mov     r15, [rbp+3Fh+bstrString]
0x180110a4f  lea     rcx, [rbp+3Fh+var_98]
0x180110a53  mov     qword ptr [rsp+130h+var_108], rcx; unsigned int
0x180110a58  mov     dword ptr [rsp+130h+ppv], eax; struct _devicemodeW *
0x180110a5c  mov     r9, [r13+0]; unsigned __int16 *
0x180110a60  mov     r8, r15; unsigned __int16 *
0x180110a63  mov     rdx, [rbp+3Fh+arg_0]
0x180110a67  mov     rdx, [rdx+18h]; void *
0x180110a6b  mov     rcx, r12; this
0x180110a6e  call    ?PublicDevmodeToJobTicket@publicdm@@YAJPEAXPEBG1PEAU_devicemodeW@@KPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z; publicdm::PublicDevmodeToJobTicket(void *,ushort const *,ushort const *,_devicemodeW *,ulong,NPrintTicketUtil::CPrintTicketWrapper *)
0x180110a73  mov     esi, eax
0x180110a75  test    eax, eax
0x180110a77  js      loc_180110DB9
0x180110a7d  lea     rdx, aGetPrintTicket; "Get print ticket XML"
0x180110a84  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110a8b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110a90  mov     rcx, qword ptr [rbp+3Fh+var_90]
0x180110a94  test    rcx, rcx
0x180110a97  jnz     short loc_180110AA3
0x180110a99  mov     esi, 80004005h
0x180110a9e  jmp     loc_180110DB9
0x180110aa3  mov     rax, [rcx]
0x180110aa6  mov     rax, [rax+8]
0x180110aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110aaf  mov     r14, qword ptr [rbp+3Fh+var_90]
0x180110ab3  mov     [rbp+3Fh+var_A8], r14
0x180110ab7  lea     rdx, aInvokeTheProvi; "Invoke the providers conversion method "...
0x180110abe  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110ac5  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110aca  mov     rax, [rbx]
0x180110acd  mov     r9, r14
0x180110ad0  mov     r8, [r13+0]
0x180110ad4  mov     edx, dword ptr [rbp+3Fh+arg_20]
0x180110ad7  mov     rcx, rbx
0x180110ada  mov     rax, [rax+38h]
0x180110ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110ae3  mov     esi, eax
0x180110ae5  test    eax, eax
0x180110ae7  js      loc_180110DB9
0x180110aed  lea     rdx, aInvokingValida; "Invoking ValidatePrintTicket"
0x180110af4  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110afb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180110b00  mov     [rsp+130h+var_D8], 0
0x180110b09  mov     [rsp+130h+var_D0], 0
0x180110b12  mov     rax, [r14]
0x180110b15  lea     r8, [rsp+130h+var_D8]
0x180110b1a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180110b21  mov     rcx, r14
0x180110b24  mov     rax, [rax]
0x180110b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110b2c  lea     r8, [rsp+130h+var_D0]
0x180110b31  mov     rdx, [rsp+130h+var_D8]
0x180110b36  mov     rcx, [rbp+3Fh+arg_10]
0x180110b3a  call    cs:__imp_ValidatePrintTicket
0x180110b40  mov     esi, eax
0x180110b42  test    eax, eax
0x180110b44  jns     short loc_180110B61
0x180110b46  mov     r8d, eax
0x180110b49  lea     rdx, aPsaValidationR; "PSA Validation returned with (hr: 0x%x)"...
0x180110b50  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110b57  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180110b5c  jmp     loc_180110D36
0x180110b61  xorps   xmm0, xmm0
0x180110b64  xor     eax, eax
0x180110b66  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180110b6a  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180110b6e  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180110b72  call    cs:__imp_VariantInit
0x180110b78  mov     eax, 0Dh
0x180110b7d  mov     word ptr [rbp+3Fh+pvarg], ax
0x180110b81  mov     rax, [rsp+130h+var_D0]
0x180110b86  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x180110b8a  xor     eax, eax
0x180110b8c  mov     word ptr [rsp+130h+var_F0+4], ax
0x180110b91  mov     [rsp+130h+var_E8], rax
0x180110b96  lea     rax, [rsp+130h+var_E8]
0x180110b9b  mov     [rsp+130h+ppv], rax; ppv
0x180110ba0  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180110ba7  xor     edx, edx; pUnkOuter
0x180110ba9  lea     r8d, [rdx+1]; dwClsContext
0x180110bad  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180110bb4  call    cs:__imp_CoCreateInstance
0x180110bba  mov     r12d, eax
0x180110bbd  test    eax, eax
0x180110bbf  jns     loc_180110C8E
0x180110bc5  lea     rdx, aPsaUnableToSet; "PSA Unable to set create IXMLDOMDocumen"...
0x180110bcc  lea     rcx, aUnidrvuiTrypri; "UniDrvUI::TryPrintSupportValidation"
0x180110bd3  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180110bd8  nop
0x180110bd9  mov     rcx, [rsp+130h+var_E8]
0x180110bde  xor     esi, esi
0x180110be0  test    rcx, rcx
0x180110be3  jz      short loc_180110BF6
0x180110be5  mov     rax, [rcx]
0x180110be8  mov     rax, [rax+10h]
0x180110bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110bf1  mov     [rsp+130h+var_E8], rsi
0x180110bf6  mov     rcx, [rsp+130h+var_D0]
0x180110bfb  test    rcx, rcx
0x180110bfe  jz      short loc_180110C11
0x180110c00  mov     rax, [rcx]
0x180110c03  mov     rax, [rax+10h]
0x180110c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110c0c  mov     [rsp+130h+var_D0], rsi
0x180110c11  mov     rcx, [rsp+130h+var_D8]
0x180110c16  test    rcx, rcx
0x180110c19  jz      short loc_180110C2C
0x180110c1b  mov     rax, [rcx]
0x180110c1e  mov     rax, [rax+10h]
0x180110c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110c27  mov     [rsp+130h+var_D8], rsi
0x180110c2c  test    r15, r15
0x180110c2f  jz      short loc_180110C3B
0x180110c31  mov     rcx, r15; bstrString
0x180110c34  call    cs:__imp_SysFreeString
0x180110c3a  nop
0x180110c3b  lea     rcx, [rbp+3Fh+var_98]; this
0x180110c3f  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180110c44  nop
0x180110c45  mov     rax, [rbx]
0x180110c48  mov     rcx, rbx
0x180110c4b  mov     rax, [rax+10h]
0x180110c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110c54  nop
0x180110c55  test    r14, r14
  ... truncated ...
```
