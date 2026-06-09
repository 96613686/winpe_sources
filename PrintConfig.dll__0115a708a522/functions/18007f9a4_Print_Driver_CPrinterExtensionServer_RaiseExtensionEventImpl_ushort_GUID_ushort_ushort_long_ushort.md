# Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl(ushort *,_GUID,ushort *,ushort * *,long *,ushort * *)

- ea: `0x18007f9a4`
- end: `0x180080154`
- name: `?RaiseExtensionEventImpl@CPrinterExtensionServer@Driver@Print@@AEAAXPEAGU_GUID@@0PEAPEAGPEAJ2@Z`
- size: `1968`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *this, unsigned __int16 *, struct _GUID *, unsigned __int16 *, unsigned __int16 **, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f700`

## callees

- `0x180003400`
- `0x180003c20`
- `0x180004564`
- `0x18000f830`
- `0x18000fa4c`
- `0x18001535c`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180038a44`
- `0x18007df7c`
- `0x18007e3c4`
- `0x18007ee20`
- `0x18007f41c`
- `0x18007f5b4`
- `0x18007f9a4`
- `0x18008045c`
- `0x1800815c0`
- `0x1801b56b0`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007fdac`
- `KERNEL32!CloseHandle` at `0x18007fdac`
- `KERNEL32!OpenProcess` at `0x18007fd2a`
- `KERNEL32!OpenProcess` at `0x18007fd2a`
- `ole32!CoRevertToSelf` at `0x18007ff91`
- `ole32!CoRevertToSelf` at `0x18007ff91`
- `ole32!CoImpersonateClient` at `0x18007fa41`
- `ole32!CoImpersonateClient` at `0x18007fa41`

## string_xrefs

- `0x18007fcf2`: `Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x`
- `0x18007feba`: `Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Removed and terminated process and child processes.`
- `0x18007fecc`: `Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Removed but not terminated due to 0x%x.`
- `0x18007fe69`: `Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Not removed despite error.`
- `0x1800800a4`: `StartExtensionApp printerName=%ws reasonId=%ws driverId=%ws pNewServer=nullptr.`
- `0x18007fc6b`: `Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl`
- `0x1800800ab`: `Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl`
- `0x18007fde0`: `client=%u(0x%p) hr=0x%x; Removed because reasonIsSingleUse.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl(
        Print::Driver::CPrinterExtensionServer *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        int *a6,
        unsigned __int16 **a7)
{
  struct _GUID *v7; // rbx
  HRESULT v9; // eax
  Print::Driver::CPrinterExtensionServer *v10; // rcx
  bool v11; // si
  _QWORD *v12; // rax
  Print::Driver::CPrinterExtensionServer *v13; // rcx
  _QWORD *v14; // rax
  int Instance; // edi
  _QWORD *v16; // rbx
  int v17; // r14d
  _QWORD *v18; // rdi
  _QWORD *v19; // rsi
  DWORD v20; // r13d
  int v21; // eax
  int v22; // r15d
  int v23; // r13d
  DWORD v24; // r14d
  char *v25; // rbx
  int v26; // eax
  _QWORD *v27; // r9
  __int64 v28; // r8
  unsigned __int16 *v29; // rdx
  int v30; // eax
  struct Print::Driver::Telemetry::PrintConfigTelemetry *v31; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v32; // rcx
  __int128 *v33; // rax
  __int128 *v34; // r9
  int v35[2]; // [rsp+20h] [rbp-E0h]
  int v36[2]; // [rsp+20h] [rbp-E0h]
  int v37[2]; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+28h] [rbp-D8h]
  char v39; // [rsp+30h] [rbp-D0h]
  bool v40; // [rsp+31h] [rbp-CFh]
  bool v41; // [rsp+32h] [rbp-CEh]
  DWORD dwProcessId[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v43; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v44; // [rsp+48h] [rbp-B8h] BYREF
  void *v45[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID *v46; // [rsp+60h] [rbp-A0h]
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID pExceptionObject[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v50; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v51; // [rsp+A8h] [rbp-58h]
  unsigned __int16 **v52; // [rsp+B0h] [rbp-50h]
  struct _GUID v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  struct _GUID v55; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v56; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v57; // [rsp+100h] [rbp+0h]
  unsigned __int64 v58; // [rsp+108h] [rbp+8h]
  __int128 v59; // [rsp+110h] [rbp+10h] BYREF
  __int64 v60; // [rsp+120h] [rbp+20h]
  unsigned __int64 v61; // [rsp+128h] [rbp+28h]

  v54 = -2;
  v50 = a4;
  v7 = a3;
  v46 = a3;
  v44 = a2;
  v52 = a5;
  *(_QWORD *)&v53.Data1 = a6;
  v51 = a7;
  if ( memcmp_0(a3, &PRINTER_EXTENSION_REASON_PRINT_PREFERENCES, 0x10u)
    && memcmp_0(v7, &PRINTER_EXTENSION_REASON_DRIVER_EVENT, 0x10u) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xEu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        -2147024809);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
    throw (hr_error *)pExceptionObject;
  }
  v9 = CoImpersonateClient();
  if ( v9 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v9);
    throw (hr_error *)pExceptionObject;
  }
  *a5 = 0;
  *a6 = 1;
  *a7 = 0;
  v55 = 0;
  Print::Driver::CPrinterExtensionServer::GetTargetPrinterDriverId(v10, &v44, &v55);
  v41 = memcmp_0(&PRINTER_EXTENSION_REASON_PRINT_PREFERENCES, v7, 0x10u) == 0;
  v11 = memcmp_0(&PRINTER_EXTENSION_REASON_PRINT_PREFERENCES, v7, 0x10u) == 0;
  v40 = v11;
  v45[0] = 0;
  v45[1] = 0;
  v12 = operator new(0x18u);
  *v12 = v12;
  v12[1] = v12;
  v45[0] = v12;
  if ( !v41 )
    Print::Driver::CPrinterExtensionServer::FindTargetExtensionServers(v13, (__int64)&v55, (__int64)v7, (__int64 *)v45);
  v59 = 0;
  v60 = 0;
  v61 = 7;
  LOWORD(v59) = 0;
  Win32Adapters::Guid::StringFromGuid(v7, (__int64)&v59);
  v56 = 0;
  v57 = 0;
  v58 = 7;
  LOWORD(v56) = 0;
  Win32Adapters::Guid::StringFromGuid(&v55, (__int64)&v56);
  v14 = v45[0];
  if ( (_QWORD *)*v14 == v14 )
  {
    *(_QWORD *)dwProcessId = 0;
    Print::Driver::CPrinterExtensionServer::StartExtensionApp(this, &v55, v7, (__int64 *)dwProcessId);
    if ( !*(_QWORD *)dwProcessId )
    {
      v33 = &v56;
      if ( v58 > 7 )
        v33 = (__int128 *)v56;
      v34 = &v59;
      if ( v61 > 7 )
        v34 = (__int128 *)v59;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
        L"StartExtensionApp printerName=%ws reasonId=%ws driverId=%ws pNewServer=nullptr.",
        v44,
        v34,
        v33);
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0xFu,
          (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
          -2147023728);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, -2147023728);
      throw (hr_error *)pExceptionObject;
    }
    v43 = *(_QWORD **)dwProcessId;
    (*(void (**)(void))(**(_QWORD **)dwProcessId + 8LL))();
    std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>::push_front(
      (__int64 **)v45,
      &v43);
    if ( v43 )
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
    if ( *(_QWORD *)dwProcessId )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)dwProcessId + 16LL))(*(_QWORD *)dwProcessId);
    v14 = v45[0];
  }
  v48 = 0;
  v47 = 0;
  if ( v11 )
  {
    v43 = 0;
    Instance = ATL::CComObject<Print::Driver::CPrinterExtensionEventCallback>::CreateInstance((char **)&v43);
    v16 = v43;
    if ( Instance >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v43 + 8LL))(v43);
      Instance = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v16)(
                   v16,
                   &GUID_8b6f4821_fe64_4df3_9fa3_7bc6db02505a,
                   &v48);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v16)(
                     v16,
                     &GUID_c3854ce3_9fdd_4249_8247_ec0574314ccc,
                     &v47);
    }
    if ( v16 )
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x10u,
          (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
          Instance);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, Instance);
      throw (hr_error *)pExceptionObject;
    }
    v14 = v45[0];
    v7 = v46;
  }
  v39 = 0;
  v17 = 0;
  v18 = (_QWORD *)*v14;
  while ( v18 != v14 )
  {
    v19 = (_QWORD *)v18[2];
    v43 = v19;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 8LL))(v19);
    v20 = (*(__int64 (__fastcall **)(_QWORD *))(*v19 + 48LL))(v19);
    dwProcessId[0] = v20;
    pExceptionObject[0] = *v7;
    v21 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *, struct _GUID *, unsigned __int16 *, __int64))(*v19 + 88LL))(
            v19,
            v44,
            pExceptionObject,
            v50,
            v47);
    v22 = v21;
    if ( v21 < 0 )
    {
      if ( (unsigned int)(v21 + 2147023196) <= 0x12B || v21 == -2147467262 )
      {
        if ( v17 >= 0 )
          v17 = v21;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 32LL))(v19);
        v30 = (*(__int64 (__fastcall **)(_QWORD *))(*v19 + 72LL))(v19);
        v27 = v19;
        v28 = v20;
        if ( v30 >= 0 )
        {
          v29 = L"Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Removed and terminated process and child processes.";
          goto LABEL_48;
        }
        LODWORD(v38) = v30;
        v35[0] = v22;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
          L"Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Removed but not terminated due to 0x%x.",
          v20,
          v19,
          *(_QWORD *)v35,
          v38);
      }
      else
      {
        if ( !memcmp_0(&PRINTER_EXTENSION_REASON_PRINT_PREFERENCES, v7, 0x10u) )
          v17 = v22;
        v27 = v19;
        v28 = v20;
        v29 = L"Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x; Not removed despite error.";
LABEL_48:
        v35[0] = v22;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
          v29,
          v28,
          v27,
          *(_QWORD *)v35);
      }
      v23 = -2147023728;
      goto LABEL_34;
    }
    v35[0] = v21;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
      L"Fire_OnExtensionEventInternal client=%u(0x%p) hr=0x%x",
      v20,
      v19,
      *(_QWORD *)v35);
    v23 = -2147023728;
    if ( v22 || !v40 )
    {
      v39 = 1;
      v17 = v22;
    }
    else
    {
      v24 = dwProcessId[0];
      v25 = (char *)OpenProcess(0x100000u, 0, dwProcessId[0]);
      *(_QWORD *)&pExceptionObject[0].Data1 = v25;
      v26 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v48 + 24LL))(
              v48,
              v25,
              *(_QWORD *)&v53.Data1,
              v52,
              v51);
      v23 = v26;
      v37[0] = v26;
      if ( v26 < 0 )
      {
        v39 = 0;
        v17 = v26;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
          L"WaitForResult client=%u(0x%p) hr=0x%x.",
          dwProcessId[0],
          v19,
          *(_QWORD *)v37);
      }
      else
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
          L"WaitForResult client=%u(0x%p) hr=0x%x.",
          v24,
          v19,
          *(_QWORD *)v37);
        v39 = 1;
        v17 = 0;
      }
      if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v25);
      v7 = v46;
    }
LABEL_34:
    if ( v41 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v19 + 32LL))(v19);
      v36[0] = v17;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "Print::Driver::CPrinterExtensionServer::RaiseExtensionEventImpl",
        L"client=%u(0x%p) hr=0x%x; Removed because reasonIsSingleUse.",
        dwProcessId[0],
        v19,
        *(_QWORD *)v36);
    }
    if ( v40 && !v22 && v23 >= 0 )
    {
      if ( v19 )
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      break;
    }
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    v18 = (_QWORD *)*v18;
    v14 = v45[0];
  }
  v31 = Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
  if ( *((_QWORD *)v31 + 1) && **((_DWORD **)v31 + 1) )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
    pExceptionObject[0] = *v7;
    v53 = v55;
    Print::Driver::Telemetry::PrintConfigTelemetry::PrinterExtensionUse_(v32, v44, &v53, pExceptionObject, v17);
  }
  if ( !v39 && v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x11u,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v17);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v17);
    throw (hr_error *)pExceptionObject;
  }
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  std::wstring::~wstring((char **)&v56);
  std::wstring::~wstring((char **)&v59);
  std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>::~list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>(v45);
  if ( CoRevertToSelf() < 0 )
    __int2c();
}

```

## disassembly

```asm
0x18007f9a4  push    rbp
0x18007f9a6  push    rbx
0x18007f9a7  push    rsi
0x18007f9a8  push    rdi
0x18007f9a9  push    r12
0x18007f9ab  push    r13
0x18007f9ad  push    r14
0x18007f9af  push    r15
0x18007f9b1  lea     rbp, [rsp-48h]
0x18007f9b6  sub     rsp, 148h
0x18007f9bd  mov     [rbp+80h+var_B0], 0FFFFFFFFFFFFFFFEh
0x18007f9c5  mov     rax, cs:__security_cookie
0x18007f9cc  xor     rax, rsp
0x18007f9cf  mov     [rbp+80h+var_50], rax
0x18007f9d3  mov     [rbp+80h+var_E0], r9
0x18007f9d7  mov     rbx, r8
0x18007f9da  mov     [rsp+180h+var_120], rbx
0x18007f9df  mov     rdi, rcx
0x18007f9e2  mov     [rsp+180h+var_138], rdx
0x18007f9e7  mov     rsi, [rbp+80h+arg_20]
0x18007f9ee  mov     [rbp+80h+var_D0], rsi
0x18007f9f2  mov     r14, [rbp+80h+arg_28]
0x18007f9f9  mov     qword ptr [rbp+80h+var_C0.Data1], r14
0x18007f9fd  mov     r15, [rbp+80h+arg_30]
0x18007fa04  mov     [rbp+80h+var_D8], r15
0x18007fa08  mov     r12d, 10h
0x18007fa0e  mov     r8d, r12d; Size
0x18007fa11  lea     rdx, PRINTER_EXTENSION_REASON_PRINT_PREFERENCES; Buf2
0x18007fa18  mov     rcx, rbx; Buf1
0x18007fa1b  call    memcmp_0
0x18007fa20  xor     r13d, r13d
0x18007fa23  test    eax, eax
0x18007fa25  jz      short loc_18007FA41
0x18007fa27  mov     r8d, r12d; Size
0x18007fa2a  lea     rdx, PRINTER_EXTENSION_REASON_DRIVER_EVENT; Buf2
0x18007fa31  mov     rcx, rbx; Buf1
0x18007fa34  call    memcmp_0
0x18007fa39  test    eax, eax
0x18007fa3b  jnz     loc_180080012
0x18007fa41  call    cs:__imp_CoImpersonateClient
0x18007fa48  nop     dword ptr [rax+rax+00h]
0x18007fa4d  test    eax, eax
0x18007fa4f  js      loc_180080064
0x18007fa55  mov     [rsp+180h+var_14D], 1
0x18007fa5a  mov     [rsi], r13
0x18007fa5d  mov     dword ptr [r14], 1
0x18007fa64  mov     [r15], r13
0x18007fa67  xorps   xmm0, xmm0
0x18007fa6a  movups  xmmword ptr [rbp+80h+var_A0.Data1], xmm0
0x18007fa6e  lea     r8, [rbp+80h+var_A0]; struct _GUID *
0x18007fa72  lea     rdx, [rsp+180h+var_138]; unsigned __int16 **
0x18007fa77  call    ?GetTargetPrinterDriverId@CPrinterExtensionServer@Driver@Print@@AEAAXAEBQEAGAEAU_GUID@@@Z; Print::Driver::CPrinterExtensionServer::GetTargetPrinterDriverId(ushort * const &,_GUID &)
0x18007fa7c  mov     r8, r12; Size
0x18007fa7f  mov     rdx, rbx; Buf2
0x18007fa82  lea     rcx, PRINTER_EXTENSION_REASON_PRINT_PREFERENCES; Buf1
0x18007fa89  call    memcmp_0
0x18007fa8e  test    eax, eax
0x18007fa90  setz    r14b
0x18007fa94  mov     [rsp+180h+var_14E], r14b
0x18007fa99  mov     r8, r12; Size
0x18007fa9c  mov     rdx, rbx; Buf2
0x18007fa9f  lea     rcx, PRINTER_EXTENSION_REASON_PRINT_PREFERENCES; Buf1
0x18007faa6  call    memcmp_0
0x18007faab  test    eax, eax
0x18007faad  setz    sil
0x18007fab1  mov     [rsp+180h+var_14F], sil
0x18007fab6  mov     [rsp+180h+var_130], r13
0x18007fabb  mov     [rsp+180h+var_128], r13
0x18007fac0  mov     ecx, 18h; Size
0x18007fac5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007faca  mov     [rax], rax
0x18007facd  mov     [rax+8], rax
0x18007fad1  mov     [rsp+180h+var_130], rax
0x18007fad6  test    r14b, r14b
0x18007fad9  jnz     short loc_18007FAEC
0x18007fadb  lea     r9, [rsp+180h+var_130]
0x18007fae0  mov     r8, rbx
0x18007fae3  lea     rdx, [rbp+80h+var_A0]
0x18007fae7  call    ?FindTargetExtensionServers@CPrinterExtensionServer@Driver@Print@@AEAAXAEBU_GUID@@0AEAV?$list@V?$CAdapt@V?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@ATL@@@std@@@std@@@Z; Print::Driver::CPrinterExtensionServer::FindTargetExtensionServers(_GUID const &,_GUID const &,std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>> &)
0x18007faec  xorps   xmm0, xmm0
0x18007faef  movups  [rbp+80h+var_70], xmm0
0x18007faf3  mov     [rbp+80h+var_60], r13
0x18007faf7  mov     r14d, 7
0x18007fafd  mov     [rbp+80h+var_58], r14
0x18007fb01  mov     word ptr [rbp+80h+var_70], r13w
0x18007fb06  lea     rdx, [rbp+80h+var_70]
0x18007fb0a  mov     rcx, rbx
0x18007fb0d  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x18007fb12  xorps   xmm0, xmm0
0x18007fb15  movups  [rbp+80h+var_90], xmm0
0x18007fb19  mov     [rbp+80h+var_80], r13
0x18007fb1d  mov     [rbp+80h+var_78], r14
0x18007fb21  mov     word ptr [rbp+80h+var_90], r13w
0x18007fb26  lea     rdx, [rbp+80h+var_90]
0x18007fb2a  lea     rcx, [rbp+80h+var_A0]
0x18007fb2e  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x18007fb33  mov     rax, [rsp+180h+var_130]
0x18007fb38  cmp     [rax], rax
0x18007fb3b  jnz     loc_18007FBC2
0x18007fb41  mov     qword ptr [rsp+180h+dwProcessId], r13
0x18007fb46  lea     r9, [rsp+180h+dwProcessId]
0x18007fb4b  mov     r8, rbx
0x18007fb4e  lea     rdx, [rbp+80h+var_A0]
0x18007fb52  mov     rcx, rdi
0x18007fb55  call    ?StartExtensionApp@CPrinterExtensionServer@Driver@Print@@AEAAXAEBU_GUID@@0AEAV?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@Z; Print::Driver::CPrinterExtensionServer::StartExtensionApp(_GUID const &,_GUID const &,ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92> &)
0x18007fb5a  mov     rcx, qword ptr [rsp+180h+dwProcessId]
0x18007fb5f  test    rcx, rcx
0x18007fb62  jz      loc_180080080
0x18007fb68  mov     [rsp+180h+var_140], rcx
0x18007fb6d  test    rcx, rcx
0x18007fb70  jz      short loc_18007FB7F
0x18007fb72  mov     rax, [rcx]
0x18007fb75  mov     rax, [rax+8]
0x18007fb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fb7e  nop
0x18007fb7f  lea     rdx, [rsp+180h+var_140]
0x18007fb84  lea     rcx, [rsp+180h+var_130]
0x18007fb89  call    ?push_front@?$list@V?$CAdapt@V?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@ATL@@@std@@@std@@QEAAX$$QEAV?$CAdapt@V?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@ATL@@@Z; std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>::push_front(ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>> &&)
0x18007fb8e  nop
0x18007fb8f  mov     rcx, [rsp+180h+var_140]
0x18007fb94  test    rcx, rcx
0x18007fb97  jz      short loc_18007FBA6
0x18007fb99  mov     rax, [rcx]
0x18007fb9c  mov     rax, [rax+10h]
0x18007fba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fba5  nop
0x18007fba6  mov     rcx, qword ptr [rsp+180h+dwProcessId]
0x18007fbab  test    rcx, rcx
0x18007fbae  jz      short loc_18007FBBD
0x18007fbb0  mov     rax, [rcx]
0x18007fbb3  mov     rax, [rax+10h]
0x18007fbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fbbc  nop
0x18007fbbd  mov     rax, [rsp+180h+var_130]
0x18007fbc2  mov     [rsp+180h+var_110], r13
0x18007fbc7  mov     [rsp+180h+var_118], r13
0x18007fbcc  test    sil, sil
0x18007fbcf  jz      loc_18007FC60
0x18007fbd5  mov     [rsp+180h+var_140], r13
0x18007fbda  lea     rcx, [rsp+180h+var_140]
0x18007fbdf  call    ?CreateInstance@?$CComObject@VCPrinterExtensionEventCallback@Driver@Print@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Print::Driver::CPrinterExtensionEventCallback>::CreateInstance(ATL::CComObject<Print::Driver::CPrinterExtensionEventCallback> * *)
0x18007fbe4  mov     edi, eax
0x18007fbe6  mov     rbx, [rsp+180h+var_140]
0x18007fbeb  test    eax, eax
0x18007fbed  js      short loc_18007FC3A
0x18007fbef  mov     rax, [rbx]
0x18007fbf2  mov     rcx, rbx
0x18007fbf5  mov     rax, [rax+8]
0x18007fbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fbfe  mov     rax, [rbx]
0x18007fc01  lea     r8, [rsp+180h+var_110]
0x18007fc06  lea     rdx, _GUID_8b6f4821_fe64_4df3_9fa3_7bc6db02505a
0x18007fc0d  mov     rcx, rbx
0x18007fc10  mov     rax, [rax]
0x18007fc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc18  mov     edi, eax
0x18007fc1a  test    eax, eax
0x18007fc1c  js      short loc_18007FC3A
0x18007fc1e  mov     rax, [rbx]
0x18007fc21  lea     r8, [rsp+180h+var_118]
0x18007fc26  lea     rdx, _GUID_c3854ce3_9fdd_4249_8247_ec0574314ccc
0x18007fc2d  mov     rcx, rbx
0x18007fc30  mov     rax, [rax]
0x18007fc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc38  mov     edi, eax
0x18007fc3a  test    rbx, rbx
0x18007fc3d  jz      short loc_18007FC4E
0x18007fc3f  mov     rax, [rbx]
0x18007fc42  mov     rcx, rbx
0x18007fc45  mov     rax, [rax+10h]
0x18007fc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc4e  test    edi, edi
0x18007fc50  js      loc_180080109
0x18007fc56  mov     rax, [rsp+180h+var_130]
0x18007fc5b  mov     rbx, [rsp+180h+var_120]
0x18007fc60  mov     [rsp+180h+var_150], r13b
0x18007fc65  mov     r14d, r13d
0x18007fc68  mov     rdi, [rax]
0x18007fc6b  lea     r12, aPrintDriverCpr_0; "Print::Driver::CPrinterExtensionServer:"...
0x18007fc72  cmp     rdi, rax
0x18007fc75  jz      loc_18007FEF2
0x18007fc7b  mov     rsi, [rdi+10h]
0x18007fc7f  mov     [rsp+180h+var_140], rsi
0x18007fc84  test    rsi, rsi
0x18007fc87  jz      short loc_18007FC99
0x18007fc89  mov     rax, [rsi]
0x18007fc8c  mov     rcx, rsi
0x18007fc8f  mov     rax, [rax+8]
0x18007fc93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc98  nop
0x18007fc99  mov     rax, [rsi]
0x18007fc9c  mov     rcx, rsi
0x18007fc9f  mov     rax, [rax+30h]
0x18007fca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fca8  mov     r13d, eax
0x18007fcab  mov     [rsp+180h+dwProcessId], eax
0x18007fcaf  mov     rdx, [rsp+180h+var_118]
0x18007fcb4  movaps  xmm0, xmmword ptr [rbx]
0x18007fcb7  movdqa  [rbp+80h+pExceptionObject], xmm0
0x18007fcbc  mov     rcx, [rsi]
0x18007fcbf  mov     rax, [rcx+58h]
0x18007fcc3  mov     qword ptr [rsp+180h+var_160], rdx
0x18007fcc8  mov     r9, [rbp+80h+var_E0]
0x18007fccc  lea     r8, [rbp+80h+pExceptionObject]
0x18007fcd0  mov     rdx, [rsp+180h+var_138]
0x18007fcd5  mov     rcx, rsi
0x18007fcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fcdd  mov     r15d, eax
0x18007fce0  test    eax, eax
0x18007fce2  js      loc_18007FE33
0x18007fce8  mov     [rsp+180h+var_160], eax
0x18007fcec  mov     r9, rsi
0x18007fcef  mov     r8d, r13d
0x18007fcf2  lea     rdx, aFireOnextensio; "Fire_OnExtensionEventInternal client=%u"...
0x18007fcf9  mov     rcx, r12; char *
0x18007fcfc  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007fd01  mov     r13d, 80070490h
0x18007fd07  test    r15d, r15d
0x18007fd0a  jnz     loc_18007FE29
0x18007fd10  cmp     [rsp+180h+var_14F], r15b
0x18007fd15  jz      loc_18007FE29
0x18007fd1b  mov     r14d, [rsp+180h+dwProcessId]
0x18007fd20  mov     r8d, r14d; dwProcessId
0x18007fd23  xor     edx, edx; bInheritHandle
0x18007fd25  mov     ecx, 100000h; dwDesiredAccess
0x18007fd2a  call    cs:__imp_OpenProcess
0x18007fd31  nop     dword ptr [rax+rax+00h]
0x18007fd36  mov     rbx, rax
0x18007fd39  mov     qword ptr [rbp+80h+pExceptionObject], rax
0x18007fd3d  mov     rcx, [rsp+180h+var_110]
0x18007fd42  mov     rax, [rcx]
0x18007fd45  mov     rdx, [rbp+80h+var_D8]
0x18007fd49  mov     qword ptr [rsp+180h+var_160], rdx
0x18007fd4e  mov     r9, [rbp+80h+var_D0]
0x18007fd52  mov     r8, qword ptr [rbp+80h+var_C0.Data1]
0x18007fd56  mov     rdx, rbx
0x18007fd59  mov     rax, [rax+18h]
0x18007fd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fd62  mov     r13d, eax
0x18007fd65  mov     [rsp+180h+var_160], eax
0x18007fd69  mov     r9, rsi
0x18007fd6c  lea     rdx, aWaitforresultC; "WaitForResult client=%u(0x%p) hr=0x%x."
0x18007fd73  mov     rcx, r12; char *
0x18007fd76  test    eax, eax
0x18007fd78  js      short loc_18007FD8C
0x18007fd7a  mov     r8d, r14d
0x18007fd7d  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007fd82  mov     [rsp+180h+var_150], 1
0x18007fd87  mov     r14d, r15d
0x18007fd8a  jmp     short loc_18007FD9F
0x18007fd8c  mov     [rsp+180h+var_150], 0
0x18007fd91  mov     r14d, eax
0x18007fd94  mov     r8d, [rsp+180h+dwProcessId]
0x18007fd99  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007fd9e  nop
0x18007fd9f  lea     rax, [rbx-1]
0x18007fda3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007fda7  ja      short loc_18007FDB8
0x18007fda9  mov     rcx, rbx; hObject
0x18007fdac  call    cs:__imp_CloseHandle
0x18007fdb3  nop     dword ptr [rax+rax+00h]
0x18007fdb8  mov     rbx, [rsp+180h+var_120]
0x18007fdbd  cmp     [rsp+180h+var_14E], 0
0x18007fdc2  jz      short loc_18007FDEF
0x18007fdc4  mov     rax, [rsi]
0x18007fdc7  mov     rcx, rsi
0x18007fdca  mov     rax, [rax+20h]
0x18007fdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fdd3  mov     [rsp+180h+var_160], r14d
0x18007fdd8  mov     r9, rsi
0x18007fddb  mov     r8d, [rsp+180h+dwProcessId]
0x18007fde0  lea     rdx, aClientU0xPHr0x; "client=%u(0x%p) hr=0x%x; Removed becaus"...
0x18007fde7  mov     rcx, r12; char *
0x18007fdea  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007fdef  cmp     [rsp+180h+var_14F], 0
0x18007fdf4  jz      short loc_18007FE04
0x18007fdf6  test    r15d, r15d
0x18007fdf9  jnz     short loc_18007FE04
0x18007fdfb  test    r13d, r13d
0x18007fdfe  jns     loc_18007FEDA
0x18007fe04  xor     r13d, r13d
0x18007fe07  test    rsi, rsi
0x18007fe0a  jz      short loc_18007FE1C
0x18007fe0c  mov     rax, [rsi]
0x18007fe0f  mov     rcx, rsi
0x18007fe12  mov     rax, [rax+10h]
0x18007fe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fe1b  nop
0x18007fe1c  mov     rdi, [rdi]
0x18007fe1f  mov     rax, [rsp+180h+var_130]
0x18007fe24  jmp     loc_18007FC72
0x18007fe29  mov     [rsp+180h+var_150], 1
0x18007fe2e  mov     r14d, r15d
0x18007fe31  jmp     short loc_18007FDBD
0x18007fe33  add     eax, 7FF8F95Ch
0x18007fe38  cmp     eax, 12Bh
0x18007fe3d  jbe     short loc_18007FE88
0x18007fe3f  cmp     r15d, 80004002h
0x18007fe46  jz      short loc_18007FE88
0x18007fe48  mov     r8d, 10h; Size
  ... truncated ...
```
