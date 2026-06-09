# DmGenerateMaaAttestationClaims(unsigned __int64,unsigned __int64,ushort const *,ushort const *,uchar const *,ulong,ushort const *,int,targetAik,uchar * *,ulong *,ushort * *,ushort * *)

- ea: `0x180089090`
- end: `0x180089a8a`
- name: `?DmGenerateMaaAttestationClaims@@YAJ_K0PEBG1PEBEK1HW4targetAik@@PEAPEAEPEAKPEAPEAG6@Z`
- size: `2554`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180054ec0`
- `0x180057c6c`
- `0x180058368`
- `0x18005cb4c`
- `0x180062728`
- `0x180084ac8`
- `0x1800853f0`
- `0x180085760`
- `0x1800872ec`
- `0x180089090`
- `0x18008b4d0`
- `0x18008b94c`
- `0x18008ba9c`
- `0x180090e4c`
- `0x180090fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089259`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800891cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800891cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089966`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089966`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089249`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1800892ed`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089766`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1800898c0`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089249`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1800892ed`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089766`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x1800898c0`
- `ncrypt!NCryptImportKey` at `0x1800894dc`
- `ncrypt!NCryptImportKey` at `0x1800894dc`
- `ncrypt!NCryptFreeObject` at `0x1800893b4`
- `ncrypt!NCryptFreeObject` at `0x18008948d`
- `ncrypt!NCryptFreeObject` at `0x1800893b4`
- `ncrypt!NCryptFreeObject` at `0x18008948d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180089365`
- `ncrypt!NCryptOpenStorageProvider` at `0x180089365`
- `ncrypt!NCryptSetProperty` at `0x180089514`
- `ncrypt!NCryptSetProperty` at `0x180089514`
- `ncrypt!NCryptOpenKey` at `0x1800893e7`
- `ncrypt!NCryptOpenKey` at `0x1800893e7`
- `AzureAttestManager!AttestationGetReport` at `0x1800898ec`
- `AzureAttestManager!AttestationGetReport` at `0x180089995`
- `AzureAttestManager!AttestationGetReport` at `0x1800898ec`
- `AzureAttestManager!AttestationGetReport` at `0x180089995`
- `AzureAttestManager!AttestationCreateSession` at `0x180089632`
- `AzureAttestManager!AttestationCreateSession` at `0x180089632`
- `AzureAttestManager!AttestationCloseSession` at `0x1800895a6`
- `AzureAttestManager!AttestationCloseSession` at `0x1800895a6`

## string_xrefs

- `0x180089a07`: `DmGenerateMaaAttestationClaims: GetSystemDirectoryW Failed`
- `0x18008928a`: `DmGenerateMaaAttestationClaims: SetDllDirectoryW Failed`
- `0x180089665`: `DmGenerateMaaAttestationClaims: AttestationCreateSession Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DmGenerateMaaAttestationClaims(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        int a9,
        HLOCAL *a10,
        _DWORD *a11,
        __int64 a12,
        __int64 a13)
{
  __int64 v14; // r14
  HLOCAL *v17; // r15
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  SECURITY_STATUS Report; // edi
  signed int LastError; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  SECURITY_STATUS v26; // eax
  wil *v27; // rcx
  NCRYPT_HANDLE v28; // rdi
  const wchar_t *v29; // r8
  __int64 v30; // r9
  void *v31; // rcx
  NCRYPT_HANDLE v32; // rdi
  __int64 v33; // rdi
  int v34; // edx
  __int128 *v35; // rax
  __int64 v36; // r9
  unsigned int v37; // eax
  char v38; // al
  int i; // edi
  int v40; // eax
  SECURITY_STATUS v41; // esi
  void *v42; // rcx
  bool v43; // zf
  __int64 v44; // rax
  void *v45; // rcx
  __int64 v46; // rcx
  const wchar_t *v47; // r8
  __int64 v48; // r8
  __int64 v50; // r9
  unsigned int v51; // eax
  _QWORD *dwFlags; // [rsp+20h] [rbp-418h]
  int pbData; // [rsp+28h] [rbp-410h]
  unsigned int v54; // [rsp+50h] [rbp-3E8h] BYREF
  char v55; // [rsp+54h] [rbp-3E4h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+58h] [rbp-3E0h] BYREF
  void *v57; // [rsp+60h] [rbp-3D8h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp-3D0h] BYREF
  SIZE_T uBytes; // [rsp+70h] [rbp-3C8h] BYREF
  int v60; // [rsp+78h] [rbp-3C0h] BYREF
  __int64 v61; // [rsp+80h] [rbp-3B8h] BYREF
  __int64 v62; // [rsp+88h] [rbp-3B0h] BYREF
  char v63; // [rsp+91h] [rbp-3A7h]
  BYTE pbInput[4]; // [rsp+94h] [rbp-3A4h] BYREF
  __int128 v65; // [rsp+98h] [rbp-3A0h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-390h]
  __int128 v67; // [rsp+B0h] [rbp-388h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-378h]
  __int64 v69; // [rsp+C8h] [rbp-370h]
  HLOCAL *v70; // [rsp+D0h] [rbp-368h]
  _QWORD v71[2]; // [rsp+D8h] [rbp-360h] BYREF
  _WORD v72[8]; // [rsp+E8h] [rbp-350h] BYREF
  __int128 v73; // [rsp+F8h] [rbp-340h] BYREF
  __int64 v74; // [rsp+108h] [rbp-330h]
  _QWORD v75[2]; // [rsp+110h] [rbp-328h] BYREF
  _WORD v76[8]; // [rsp+120h] [rbp-318h] BYREF
  __int64 v77; // [rsp+130h] [rbp-308h]
  __int64 v78; // [rsp+138h] [rbp-300h]
  _DWORD *v79; // [rsp+140h] [rbp-2F8h]
  __int128 v80; // [rsp+148h] [rbp-2F0h] BYREF
  __int64 v81; // [rsp+158h] [rbp-2E0h]
  _QWORD v82[3]; // [rsp+160h] [rbp-2D8h] BYREF
  _QWORD v83[5]; // [rsp+178h] [rbp-2C0h] BYREF
  char v84; // [rsp+1A0h] [rbp-298h]
  const web::http::http_exception *v85; // [rsp+1A8h] [rbp-290h] BYREF
  BYTE v86[24]; // [rsp+1B0h] [rbp-288h] BYREF
  BYTE v87[4]; // [rsp+1C8h] [rbp-270h] BYREF
  int v88; // [rsp+1CCh] [rbp-26Ch]
  int v89; // [rsp+1D0h] [rbp-268h]
  WCHAR PathName[264]; // [rsp+1E0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v14 = a3;
  v69 = a3;
  v77 = a5;
  v78 = a7;
  v17 = a10;
  v70 = a10;
  v79 = a11;
  if ( !a1 || !a3 || !a4 )
    return 2147942487LL;
  v54 = 0;
  v62 = 0;
  v75[0] = v76;
  v75[1] = v76;
  v76[0] = 0;
  v71[0] = v72;
  v71[1] = v72;
  v72[0] = 0;
  v83[0] = &a12;
  v83[1] = v75;
  v83[2] = &v54;
  v83[3] = &a13;
  v83[4] = v71;
  v84 = 1;
  if ( GetSystemDirectoryW(PathName, 0x104u) - 1 > 0x102 )
  {
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v18,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: GetSystemDirectoryW Failed",
        2147942487LL);
    Report = -2147024809;
    goto LABEL_90;
  }
  v19 = StringCchCatW(PathName, 0x104u, L"\\HealthAttestationClient");
  Report = v19;
  v54 = v19;
  if ( v19 < 0 )
  {
    if ( a8 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        McTemplateU0zd_EventWriteTransfer(
          v20,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateMaaAttestationClaims: StringCchCatW Failed",
          (unsigned int)v19);
        Report = v54;
      }
    }
    goto LABEL_90;
  }
  if ( !SetDllDirectoryW(PathName) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v54 = LastError;
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v23,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: SetDllDirectoryW Failed",
        (unsigned int)LastError);
      LastError = v54;
    }
    Report = LastError;
    goto LABEL_90;
  }
  v63 = 1;
  v24 = InitializeAttestationApis();
  Report = v24;
  v54 = v24;
  if ( v24 < 0 )
  {
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v25,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: InitializeAttestationApis Failed",
        (unsigned int)v24);
      Report = v54;
    }
LABEL_20:
    SetDllDirectoryW(0);
    goto LABEL_90;
  }
  v57 = 0;
  v61 = 0;
  *(_DWORD *)v87 = 1297371211;
  v89 = -2130706429;
  v88 = 12;
  *(_DWORD *)pbInput = 29426128;
  hObject = 0;
  v73 = 0;
  v74 = 0;
  phProvider = 0;
  v26 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  Report = v26;
  v54 = v26;
  if ( a9 == 1 )
  {
    if ( v26 < 0 )
      goto LABEL_28;
    Report = DmSetWindowsAIKPlatformStorageLocation(phProvider);
    v54 = Report;
    if ( Report < 0 )
      goto LABEL_28;
    v28 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v60);
      NCryptFreeObject(v28);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v60);
    }
    hObject = 0;
    Report = NCryptOpenKey(phProvider, &hObject, L"Windows AIK", 0, 0);
    v54 = Report;
    if ( Report < 0 )
    {
LABEL_28:
      if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v29 = L"DmGenerateMaaAttestationClaims: SetWindowsAik Failed";
LABEL_30:
        v30 = (unsigned int)Report;
LABEL_31:
        McTemplateU0zd_EventWriteTransfer(v27, EnterpriseDiagnosticsTPMFunctionFailure, v29, v30);
        Report = v54;
        goto LABEL_32;
      }
      goto LABEL_32;
    }
  }
  else
  {
    if ( v26 < 0 )
      goto LABEL_84;
    v32 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v60);
      NCryptFreeObject(v32);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v60);
    }
    hObject = 0;
    Report = NCryptImportKey(phProvider, 0, L"PcpTpmPersistentKeyBlob", 0, &hObject, v87, 0xCu, 0);
    v54 = Report;
    if ( Report < 0
      || (Report = NCryptSetProperty(hObject, L"KeyCertificateFromTpmNvram", pbInput, 4u, 0), v54 = Report, Report < 0) )
    {
LABEL_84:
      if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v29 = L"DmGenerateMaaAttestationClaims: SetAzureAik Failed";
        goto LABEL_30;
      }
LABEL_32:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v61);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      v31 = v57;
      v57 = 0;
      if ( v31 )
        MemoryFree(v31);
      goto LABEL_20;
    }
  }
  *((_QWORD *)&v73 + 1) = hObject;
  LODWORD(v73) = 3;
  v82[0] = 3;
  v82[2] = 0;
  v82[1] = a1;
  v80 = 0;
  v81 = 0;
  if ( a2 )
  {
    LODWORD(v80) = 3;
    *((_QWORD *)&v80 + 1) = a2;
  }
  v33 = v62;
  if ( v62 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v60);
    AttestationCloseSession(v33);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v60);
  }
  v62 = 0;
  v34 = 0;
  v35 = &v80;
  if ( !a2 )
    v35 = 0;
  v36 = -1;
  do
    ++v36;
  while ( *(_WORD *)(a4 + 2 * v36) );
  LOBYTE(v34) = a2 != 0;
  v37 = AttestationCreateSession(v77, a6, a4, (unsigned int)(v36 + 1), 0, &v73, v82, v35, v34, &v62);
  Report = v37;
  v54 = v37;
  if ( v37 )
  {
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      v30 = v37;
      v29 = L"DmGenerateMaaAttestationClaims: AttestationCreateSession Failed";
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v67 = 0;
  v68 = 0;
  v65 = 0;
  v66 = 0;
  v38 = 0;
  v55 = 0;
  for ( i = 0; ; ++i )
  {
    v60 = i;
    if ( v38 )
    {
      LODWORD(uBytes) = 0;
      Report = AttestationGetReport(v62, 0, 0, &uBytes);
      v54 = Report;
      v46 = 0x80000000LL;
      if ( (int)(Report + 0x80000000) < 0 || Report == -2147024774 )
      {
        *v17 = LocalAlloc(0x40u, (unsigned int)uBytes);
        v48 = (unsigned int)uBytes;
        *v79 = uBytes;
        Report = AttestationGetReport(v62, *v17, v48, &uBytes);
        v54 = Report;
        if ( Report >= 0
          || !a8
          || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        {
          goto LABEL_78;
        }
        v47 = L"DmGenerateMaaAttestationClaims: AttestationGetReport";
      }
      else
      {
        if ( !a8 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
          goto LABEL_78;
        v47 = L"DmGenerateMaaAttestationClaims: AttestationGetReport(size)";
      }
      McTemplateU0zd_EventWriteTransfer(v46, EnterpriseDiagnosticsTPMFunctionFailure, v47, (unsigned int)Report);
      Report = v54;
LABEL_78:
      std::vector<unsigned char>::_Tidy(&v65);
      std::vector<unsigned char>::_Tidy(&v67);
      goto LABEL_32;
    }
    if ( i >= 20 )
    {
      if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v27,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateMaaAttestationClaims: Invalid Data",
          2147942413LL);
      std::vector<unsigned char>::_Tidy(&v65);
      std::vector<unsigned char>::_Tidy(&v67);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v61);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      v45 = v57;
      v57 = 0;
      if ( v45 )
        MemoryFree(v45);
      SetDllDirectoryW(0);
      Report = -2147024883;
      goto LABEL_90;
    }
    v40 = Attest(v62, &v67, &v65, &v55, dwFlags, pbData);
    v41 = v40;
    v54 = v40;
    if ( v40 < 0 )
      break;
    if ( *((_QWORD *)&v65 + 1) != (_QWORD)v65 )
    {
      try
      {
        LOBYTE(pbData) = i == 1;
        dwFlags = v71;
        v44 = SendToAttestationService(v86, &v65, v14, v78);
        std::vector<unsigned char>::operator=(&v67, v44);
        std::vector<unsigned char>::_Tidy(v86);
      }
      catch ( const web::http::http_exception *v85 )
      {
        v50 = *((unsigned int *)v85 + 6);
        if ( (int)v50 > 0 )
          v50 = (unsigned __int16)v50 | 0x80070000;
        v54 = v50;
        if ( a8 )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            McTemplateU0zd_EventWriteTransfer(
              v27,
              EnterpriseDiagnosticsTPMFunctionFailure,
              L"DmGenerateMaaAttestationClaims: SendToAttestationServiceFailed HTTP Error",
              v50);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
              McTemplateU0zd_EventWriteTransfer(v27, EnterpriseDiagnosticsTPMFunctionFailure, v71[0], v54);
          }
        }
        v17 = v70;
        v14 = v69;
        i = v60;
      }
      catch ( ... )
      {
        v51 = wil::ResultFromCaughtException(v27);
        v54 = v51;
        if ( a8 )
        {
          v27 = (wil *)(unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits;
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            McTemplateU0zd_EventWriteTransfer(
              (unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits,
              EnterpriseDiagnosticsTPMFunctionFailure,
              L"DmGenerateMaaAttestationClaims: SendToAttestationServiceFailed Failed",
              v51);
            v27 = (wil *)(unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits;
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
              McTemplateU0zd_EventWriteTransfer(
                (unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits,
                EnterpriseDiagnosticsTPMFunctionFailure,
                v71[0],
                v54);
          }
        }
        v17 = v70;
        v14 = v69;
        i = v60;
      }
      v41 = v54;
      if ( (v54 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8BA,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
          (const char *)v54,
          (int)v71);
        goto LABEL_58;
      }
    }
    v38 = v55;
  }
  if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0zd_EventWriteTransfer(
      v27,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"DmGenerateMaaAttestationClaims: Attest Failed",
      (unsigned int)v40);
    v41 = v54;
  }
LABEL_58:
  std::vector<unsigned char>::_Tidy(&v65);
  std::vector<unsigned char>::_Tidy(&v67);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v61);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  v42 = v57;
  v43 = v57 == 0;
  v57 = 0;
  if ( !v43 )
    MemoryFree(v42);
  SetDllDirectoryW(0);
  Report = v41;
LABEL_90:
  v84 = 0;
  lambda_5f2fd0ade72e93e38326769b537935e7_::operator()(v83);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v71);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v75);
  __1__unique_storage_U__resource_policy__KP6AJ_K__E_1_AttestationCloseSession__YAJ0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&v62);
  return (unsigned int)Report;
}

```

## disassembly

```asm
0x180089090  mov     r11, rsp
0x180089093  push    rbx
0x180089094  push    rsi
0x180089095  push    rdi
0x180089096  push    r12
0x180089098  push    r13
0x18008909a  push    r14
0x18008909c  push    r15
0x18008909e  sub     rsp, 400h
0x1800890a5  mov     rax, cs:__security_cookie
0x1800890ac  xor     rax, rsp
0x1800890af  mov     [rsp+438h+var_48], rax
0x1800890b7  mov     r12, r9
0x1800890ba  mov     r14, r8
0x1800890bd  mov     rsi, rdx
0x1800890c0  mov     r13, rcx
0x1800890c3  mov     [rsp+438h+var_370], r8
0x1800890cb  mov     rax, [rsp+438h+arg_20]
0x1800890d3  mov     [rsp+438h+var_308], rax
0x1800890db  mov     rax, [rsp+438h+arg_30]
0x1800890e3  mov     [rsp+438h+var_300], rax
0x1800890eb  mov     r15, [rsp+438h+arg_48]
0x1800890f3  mov     [rsp+438h+var_368], r15
0x1800890fb  mov     rax, [rsp+438h+arg_50]
0x180089103  mov     [rsp+438h+var_2F8], rax
0x18008910b  xor     ebx, ebx
0x18008910d  test    rcx, rcx
0x180089110  jz      loc_180089A61
0x180089116  test    r8, r8
0x180089119  jz      loc_180089A61
0x18008911f  test    r9, r9
0x180089122  jz      loc_180089A61
0x180089128  mov     dword ptr [rsp+438h+var_3E8], ebx
0x18008912c  mov     [r11-3B0h], rbx
0x180089133  lea     rax, [r11-318h]
0x18008913a  mov     [r11-328h], rax
0x180089141  lea     rax, [r11-318h]
0x180089148  mov     [r11-320h], rax
0x18008914f  mov     [rsp+438h+var_318], bx
0x180089157  lea     rax, [r11-350h]
0x18008915e  mov     [r11-360h], rax
0x180089165  lea     rax, [r11-350h]
0x18008916c  mov     [r11-358h], rax
0x180089173  mov     [rsp+438h+var_350], bx
0x18008917b  lea     rax, [r11+60h]
0x18008917f  mov     [r11-2C0h], rax
0x180089186  lea     rax, [r11-328h]
0x18008918d  mov     [r11-2B8h], rax
0x180089194  lea     rax, [rsp+438h+var_3E8]
0x180089199  mov     [r11-2B0h], rax
0x1800891a0  lea     rax, [r11+68h]
0x1800891a4  mov     [r11-2A8h], rax
0x1800891ab  lea     rax, [r11-360h]
0x1800891b2  mov     [r11-2A0h], rax
0x1800891b9  mov     [rsp+438h+var_298], 1
0x1800891c1  mov     edi, 104h
0x1800891c6  mov     edx, edi; uSize
0x1800891c8  lea     rcx, [r11-258h]; lpBuffer
0x1800891cf  call    cs:__imp_GetSystemDirectoryW
0x1800891d6  nop     dword ptr [rax+rax+00h]
0x1800891db  dec     eax
0x1800891dd  cmp     eax, 102h
0x1800891e2  ja      loc_1800899EF
0x1800891e8  lea     r8, aHealthattestat; "\\HealthAttestationClient"
0x1800891ef  mov     edx, edi; unsigned __int64
0x1800891f1  lea     rcx, [rsp+438h+PathName]; unsigned __int16 *
0x1800891f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800891fe  mov     edi, eax
0x180089200  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089204  test    eax, eax
0x180089206  jns     short loc_180089241
0x180089208  cmp     [rsp+438h+arg_38], ebx
0x18008920f  jz      loc_180089A1F
0x180089215  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008921c  jz      loc_180089A1F
0x180089222  mov     r9d, eax
0x180089225  lea     r8, aDmgeneratemaaa_11; "DmGenerateMaaAttestationClaims: StringC"...
0x18008922c  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089233  call    McTemplateU0zd_EventWriteTransfer
0x180089238  mov     edi, dword ptr [rsp+438h+var_3E8]
0x18008923c  jmp     loc_180089A1F
0x180089241  lea     rcx, [rsp+438h+PathName]; lpPathName
0x180089249  call    cs:__imp_SetDllDirectoryW
0x180089250  nop     dword ptr [rax+rax+00h]
0x180089255  test    eax, eax
0x180089257  jnz     short loc_1800892A8
0x180089259  call    cs:__imp_GetLastError
0x180089260  nop     dword ptr [rax+rax+00h]
0x180089265  test    eax, eax
0x180089267  jle     short loc_180089271
0x180089269  movzx   eax, ax
0x18008926c  or      eax, 80070000h
0x180089271  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089275  cmp     [rsp+438h+arg_38], ebx
0x18008927c  jz      short loc_1800892A1
0x18008927e  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180089285  jz      short loc_1800892A1
0x180089287  mov     r9d, eax
0x18008928a  lea     r8, aDmgeneratemaaa_9; "DmGenerateMaaAttestationClaims: SetDllD"...
0x180089291  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089298  call    McTemplateU0zd_EventWriteTransfer
0x18008929d  mov     eax, dword ptr [rsp+438h+var_3E8]
0x1800892a1  mov     edi, eax
0x1800892a3  jmp     loc_180089A1F
0x1800892a8  mov     [rsp+438h+var_3A7], 1
0x1800892b0  call    ?InitializeAttestationApis@@YAJXZ; InitializeAttestationApis(void)
0x1800892b5  mov     edi, eax
0x1800892b7  mov     dword ptr [rsp+438h+var_3E8], eax
0x1800892bb  test    eax, eax
0x1800892bd  jns     short loc_1800892FE
0x1800892bf  cmp     [rsp+438h+arg_38], ebx
0x1800892c6  jz      short loc_1800892EB
0x1800892c8  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x1800892cf  jz      short loc_1800892EB
0x1800892d1  mov     r9d, eax
0x1800892d4  lea     r8, aDmgeneratemaaa_1; "DmGenerateMaaAttestationClaims: Initial"...
0x1800892db  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x1800892e2  call    McTemplateU0zd_EventWriteTransfer
0x1800892e7  mov     edi, dword ptr [rsp+438h+var_3E8]
0x1800892eb  xor     ecx, ecx; lpPathName
0x1800892ed  call    cs:__imp_SetDllDirectoryW
0x1800892f4  nop     dword ptr [rax+rax+00h]
0x1800892f9  jmp     loc_180089A1F
0x1800892fe  mov     [rsp+438h+var_3D8], rbx
0x180089303  mov     [rsp+438h+var_3B8], rbx
0x18008930b  mov     dword ptr [rsp+438h+var_270], 4D54504Bh
0x180089316  mov     [rsp+438h+var_268], 81000003h
0x180089321  mov     [rsp+438h+var_26C], 0Ch
0x18008932c  mov     dword ptr [rsp+438h+pbInput], 1C101D0h
0x180089337  mov     [rsp+438h+hObject], rbx
0x18008933c  xorps   xmm0, xmm0
0x18008933f  xor     eax, eax
0x180089341  movups  [rsp+438h+var_340], xmm0
0x180089349  mov     [rsp+438h+var_330], rax
0x180089351  mov     [rsp+438h+phProvider], rbx
0x180089356  xor     r8d, r8d; dwFlags
0x180089359  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180089360  lea     rcx, [rsp+438h+phProvider]; phProvider
0x180089365  call    cs:__imp_NCryptOpenStorageProvider
0x18008936c  nop     dword ptr [rax+rax+00h]
0x180089371  mov     edi, eax
0x180089373  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089377  cmp     [rsp+438h+arg_40], 1
0x18008937f  jnz     loc_18008946E
0x180089385  test    eax, eax
0x180089387  js      short loc_180089401
0x180089389  mov     rcx, [rsp+438h+phProvider]; hObject
0x18008938e  call    ?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z; DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)
0x180089393  mov     edi, eax
0x180089395  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089399  test    eax, eax
0x18008939b  js      short loc_180089401
0x18008939d  mov     rdi, [rsp+438h+hObject]
0x1800893a2  test    rdi, rdi
0x1800893a5  jz      short loc_1800893CA
0x1800893a7  lea     rcx, [rsp+438h+var_3C0]; this
0x1800893ac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800893b1  mov     rcx, rdi; hObject
0x1800893b4  call    cs:__imp_NCryptFreeObject
0x1800893bb  nop     dword ptr [rax+rax+00h]
0x1800893c0  lea     rcx, [rsp+438h+var_3C0]; this
0x1800893c5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800893ca  mov     [rsp+438h+hObject], rbx
0x1800893cf  mov     [rsp+438h+dwFlags], ebx; dwFlags
0x1800893d3  xor     r9d, r9d; dwLegacyKeySpec
0x1800893d6  lea     r8, pszKeyName; "Windows AIK"
0x1800893dd  lea     rdx, [rsp+438h+hObject]; phKey
0x1800893e2  mov     rcx, [rsp+438h+phProvider]; hProvider
0x1800893e7  call    cs:__imp_NCryptOpenKey
0x1800893ee  nop     dword ptr [rax+rax+00h]
0x1800893f3  mov     edi, eax
0x1800893f5  mov     dword ptr [rsp+438h+var_3E8], eax
0x1800893f9  test    eax, eax
0x1800893fb  jns     loc_18008952E
0x180089401  cmp     [rsp+438h+arg_38], ebx
0x180089408  jz      short loc_18008942D
0x18008940a  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180089411  jz      short loc_18008942D
0x180089413  lea     r8, aDmgeneratemaaa_2; "DmGenerateMaaAttestationClaims: SetWind"...
0x18008941a  mov     r9d, edi
0x18008941d  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089424  call    McTemplateU0zd_EventWriteTransfer
0x180089429  mov     edi, dword ptr [rsp+438h+var_3E8]
0x18008942d  lea     rcx, [rsp+438h+hObject]
0x180089432  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180089437  nop
0x180089438  lea     rcx, [rsp+438h+var_3B8]
0x180089440  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180089445  nop
0x180089446  lea     rcx, [rsp+438h+phProvider]
0x18008944b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180089450  nop
0x180089451  mov     rcx, [rsp+438h+var_3D8]; void *
0x180089456  mov     [rsp+438h+var_3D8], rbx
0x18008945b  test    rcx, rcx
0x18008945e  jz      loc_1800892EB
0x180089464  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180089469  jmp     loc_1800892EB
0x18008946e  test    eax, eax
0x180089470  js      loc_1800899C9
0x180089476  mov     rdi, [rsp+438h+hObject]
0x18008947b  test    rdi, rdi
0x18008947e  jz      short loc_1800894A3
0x180089480  lea     rcx, [rsp+438h+var_3C0]; this
0x180089485  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008948a  mov     rcx, rdi; hObject
0x18008948d  call    cs:__imp_NCryptFreeObject
0x180089494  nop     dword ptr [rax+rax+00h]
0x180089499  lea     rcx, [rsp+438h+var_3C0]; this
0x18008949e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800894a3  mov     [rsp+438h+hObject], rbx
0x1800894a8  mov     [rsp+438h+var_400], ebx; dwFlags
0x1800894ac  mov     [rsp+438h+cbData], 0Ch; cbData
0x1800894b4  lea     rax, [rsp+438h+var_270]
0x1800894bc  mov     [rsp+438h+pbData], rax; pbData
0x1800894c1  lea     rax, [rsp+438h+hObject]
0x1800894c6  mov     qword ptr [rsp+438h+dwFlags], rax; phKey
0x1800894cb  xor     r9d, r9d; pParameterList
0x1800894ce  lea     r8, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x1800894d5  xor     edx, edx; hImportKey
0x1800894d7  mov     rcx, [rsp+438h+phProvider]; hProvider
0x1800894dc  call    cs:__imp_NCryptImportKey
0x1800894e3  nop     dword ptr [rax+rax+00h]
0x1800894e8  mov     edi, eax
0x1800894ea  mov     dword ptr [rsp+438h+var_3E8], eax
0x1800894ee  test    eax, eax
0x1800894f0  js      loc_1800899C9
0x1800894f6  mov     [rsp+438h+dwFlags], ebx; dwFlags
0x1800894fa  mov     r9d, 4; cbInput
0x180089500  lea     r8, [rsp+438h+pbInput]; pbInput
0x180089508  lea     rdx, aKeycertificate; "KeyCertificateFromTpmNvram"
0x18008950f  mov     rcx, [rsp+438h+hObject]; hObject
0x180089514  call    cs:__imp_NCryptSetProperty
0x18008951b  nop     dword ptr [rax+rax+00h]
0x180089520  mov     edi, eax
0x180089522  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089526  test    eax, eax
0x180089528  js      loc_1800899C9
0x18008952e  mov     rax, [rsp+438h+hObject]
0x180089533  mov     ecx, 3
0x180089538  mov     qword ptr [rsp+438h+var_340+8], rax
0x180089540  mov     dword ptr [rsp+438h+var_340], ecx
0x180089547  mov     [rsp+438h+var_2D8], 3
0x180089553  mov     [rsp+438h+var_2C8], rbx
0x18008955b  mov     [rsp+438h+var_2D0], r13
0x180089563  xorps   xmm0, xmm0
0x180089566  xor     eax, eax
0x180089568  movups  [rsp+438h+var_2F0], xmm0
0x180089570  mov     [rsp+438h+var_2E0], rax
0x180089578  test    rsi, rsi
0x18008957b  jz      short loc_18008958C
0x18008957d  mov     dword ptr [rsp+438h+var_2F0], ecx
0x180089584  mov     qword ptr [rsp+438h+var_2F0+8], rsi
0x18008958c  mov     rdi, [rsp+438h+var_3B0]
0x180089594  test    rdi, rdi
0x180089597  jz      short loc_1800895BC
0x180089599  lea     rcx, [rsp+438h+var_3C0]; this
0x18008959e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800895a3  mov     rcx, rdi
0x1800895a6  call    cs:__imp_AttestationCloseSession
0x1800895ad  nop     dword ptr [rax+rax+00h]
0x1800895b2  lea     rcx, [rsp+438h+var_3C0]; this
0x1800895b7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800895bc  mov     [rsp+438h+var_3B0], rbx
0x1800895c4  mov     edx, ebx
0x1800895c6  test    rsi, rsi
0x1800895c9  setnz   dl
0x1800895cc  lea     rax, [rsp+438h+var_2F0]
0x1800895d4  test    rsi, rsi
0x1800895d7  cmovz   rax, rbx
0x1800895db  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800895df  inc     r9
0x1800895e2  cmp     [r12+r9*2], bx
0x1800895e7  jnz     short loc_1800895DF
0x1800895e9  inc     r9d
0x1800895ec  lea     rcx, [rsp+438h+var_3B0]
0x1800895f4  mov     [rsp+438h+var_3F0], rcx
0x1800895f9  mov     [rsp+438h+var_3F8], edx
0x1800895fd  mov     qword ptr [rsp+438h+var_400], rax
0x180089602  lea     rax, [rsp+438h+var_2D8]
0x18008960a  mov     qword ptr [rsp+438h+cbData], rax
0x18008960f  lea     rax, [rsp+438h+var_340]
0x180089617  mov     [rsp+438h+pbData], rax
0x18008961c  mov     [rsp+438h+dwFlags], ebx
0x180089620  mov     r8, r12
0x180089623  mov     edx, [rsp+438h+arg_28]
0x18008962a  mov     rcx, [rsp+438h+var_308]
0x180089632  call    cs:__imp_AttestationCreateSession
0x180089639  nop     dword ptr [rax+rax+00h]
0x18008963e  mov     edi, eax
0x180089640  mov     dword ptr [rsp+438h+var_3E8], eax
0x180089644  test    eax, eax
0x180089646  jz      short loc_180089671
0x180089648  cmp     [rsp+438h+arg_38], ebx
0x18008964f  jz      loc_18008942D
0x180089655  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008965c  jz      loc_18008942D
0x180089662  mov     r9d, eax
0x180089665  lea     r8, aDmgeneratemaaa_6; "DmGenerateMaaAttestationClaims: Attesta"...
0x18008966c  jmp     loc_18008941D
  ... truncated ...
```
