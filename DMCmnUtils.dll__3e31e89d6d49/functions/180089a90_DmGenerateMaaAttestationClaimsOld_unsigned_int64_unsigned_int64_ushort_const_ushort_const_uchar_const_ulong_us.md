# DmGenerateMaaAttestationClaimsOld(unsigned __int64,unsigned __int64,ushort const *,ushort const *,uchar const *,ulong,ushort const *,int,targetAik,uchar * *,ulong *)

- ea: `0x180089a90`
- end: `0x18008a42b`
- name: `?DmGenerateMaaAttestationClaimsOld@@YAJ_K0PEBG1PEBEK1HW4targetAik@@PEAPEAEPEAK@Z`
- size: `2459`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x180058368`
- `0x18005cb4c`
- `0x180062728`
- `0x180084ac8`
- `0x1800853f0`
- `0x1800872ec`
- `0x180089a90`
- `0x18008b4d0`
- `0x18008b94c`
- `0x18008c1d4`
- `0x180090e4c`
- `0x180090fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089bcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180089b4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180089b4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008a2ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008a2ff`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089bbd`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089c65`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089fae`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a0c7`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a256`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a3a4`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089bbd`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089c65`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x180089fae`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a0c7`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a256`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetDllDirectoryW` at `0x18008a3a4`
- `ncrypt!NCryptImportKey` at `0x180089def`
- `ncrypt!NCryptImportKey` at `0x180089def`
- `ncrypt!NCryptFreeObject` at `0x180089d12`
- `ncrypt!NCryptFreeObject` at `0x180089da0`
- `ncrypt!NCryptFreeObject` at `0x180089d12`
- `ncrypt!NCryptFreeObject` at `0x180089da0`
- `ncrypt!NCryptOpenStorageProvider` at `0x180089cd0`
- `ncrypt!NCryptOpenStorageProvider` at `0x180089cd0`
- `ncrypt!NCryptSetProperty` at `0x180089e1d`
- `ncrypt!NCryptSetProperty` at `0x180089e1d`
- `ncrypt!NCryptOpenKey` at `0x180089d45`
- `ncrypt!NCryptOpenKey` at `0x180089d45`
- `AzureAttestManager!AttestationGetReport` at `0x18008a27f`
- `AzureAttestManager!AttestationGetReport` at `0x18008a32b`
- `AzureAttestManager!AttestationGetReport` at `0x18008a27f`
- `AzureAttestManager!AttestationGetReport` at `0x18008a32b`
- `AzureAttestManager!AttestationCreateSession` at `0x180089f5f`
- `AzureAttestManager!AttestationCreateSession` at `0x180089f5f`
- `AzureAttestManager!AttestationCloseSession` at `0x180089ed8`
- `AzureAttestManager!AttestationCloseSession` at `0x180089ed8`

## string_xrefs

- `0x18008a3dc`: `DmGenerateMaaAttestationClaims: GetSystemDirectoryW Failed`
- `0x180089c0a`: `DmGenerateMaaAttestationClaims: SetDllDirectoryW Failed`
- `0x180089f82`: `DmGenerateMaaAttestationClaims: AttestationCreateSession Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DmGenerateMaaAttestationClaimsOld(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        int a9,
        HLOCAL *a10,
        _DWORD *a11)
{
  __int64 v12; // r12
  __int64 v15; // rcx
  __int64 v16; // rcx
  signed int LastError; // eax
  __int64 v18; // rcx
  unsigned int v19; // esi
  unsigned int v20; // edi
  int v21; // eax
  __int64 v22; // rcx
  SECURITY_STATUS v23; // eax
  __int64 v24; // rcx
  int v25; // esi
  const wchar_t *v26; // r8
  __int64 v27; // r14
  int v28; // edx
  __int128 *v29; // rax
  __int64 v30; // r9
  unsigned int v31; // eax
  __int64 v32; // rcx
  unsigned int Report; // r14d
  char v34; // al
  int v35; // r14d
  wil *v36; // rcx
  HLOCAL *v37; // r15
  __int64 v38; // r13
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  unsigned int v44; // ebx
  unsigned int v45; // eax
  unsigned int v46; // ebx
  _QWORD *dwFlags; // [rsp+20h] [rbp-3C8h]
  int pbData; // [rsp+28h] [rbp-3C0h]
  char v49[8]; // [rsp+50h] [rbp-398h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+58h] [rbp-390h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-388h] BYREF
  SIZE_T uBytes; // [rsp+68h] [rbp-380h] BYREF
  int v53; // [rsp+70h] [rbp-378h] BYREF
  __int64 v54; // [rsp+78h] [rbp-370h] BYREF
  char *v55; // [rsp+80h] [rbp-368h]
  char v56; // [rsp+89h] [rbp-35Fh]
  BYTE pbInput[4]; // [rsp+8Ch] [rbp-35Ch] BYREF
  __int128 v58; // [rsp+90h] [rbp-358h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-348h]
  _QWORD v60[2]; // [rsp+A8h] [rbp-340h] BYREF
  _WORD v61[8]; // [rsp+B8h] [rbp-330h] BYREF
  _DWORD *v62; // [rsp+C8h] [rbp-320h]
  __int128 v63; // [rsp+D0h] [rbp-318h] BYREF
  __int64 v64; // [rsp+E0h] [rbp-308h]
  __int128 v65; // [rsp+E8h] [rbp-300h] BYREF
  __int64 v66; // [rsp+F8h] [rbp-2F0h]
  HLOCAL *v67; // [rsp+100h] [rbp-2E8h]
  __int64 v68; // [rsp+108h] [rbp-2E0h]
  __int64 v69; // [rsp+110h] [rbp-2D8h]
  __int64 v70; // [rsp+118h] [rbp-2D0h]
  HLOCAL *v71; // [rsp+120h] [rbp-2C8h]
  __int128 v72; // [rsp+128h] [rbp-2C0h] BYREF
  __int64 v73; // [rsp+138h] [rbp-2B0h]
  _QWORD v74[3]; // [rsp+140h] [rbp-2A8h] BYREF
  const web::http::http_exception *v75; // [rsp+158h] [rbp-290h] BYREF
  BYTE v76[24]; // [rsp+160h] [rbp-288h] BYREF
  BYTE v77[4]; // [rsp+178h] [rbp-270h] BYREF
  int v78; // [rsp+17Ch] [rbp-26Ch]
  int v79; // [rsp+180h] [rbp-268h]
  WCHAR Buffer[264]; // [rsp+190h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  v12 = a3;
  v69 = a3;
  v55 = a5;
  v68 = a7;
  v70 = a7;
  v67 = a10;
  v71 = a10;
  v62 = a11;
  if ( !a1 || !a3 || !a4 )
    return 2147942487LL;
  v54 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v15,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: GetSystemDirectoryW Failed",
        2147942487LL);
    v19 = -2147024809;
    goto LABEL_83;
  }
  if ( StringCchCatW(Buffer, 0x104u, L"\\HealthAttestationClient") < 0 )
  {
    if ( a8 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v16,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateMaaAttestationClaims: StringCchCatW Failed",
          1);
    }
LABEL_56:
    v19 = 1;
    goto LABEL_83;
  }
  if ( !SetDllDirectoryW(Buffer) )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v18,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: SetDllDirectoryW Failed",
        v19);
    goto LABEL_83;
  }
  v20 = 1;
  v56 = 1;
  v21 = InitializeAttestationApis();
  v19 = v21;
  if ( v21 < 0 )
  {
    if ( a8 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v22,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: InitializeAttestationApis Failed",
        (unsigned int)v21);
LABEL_19:
    SetDllDirectoryW(0);
    goto LABEL_83;
  }
  hObject = 0;
  *(_DWORD *)v77 = 1297371211;
  v79 = -2130706429;
  v78 = 12;
  *(_DWORD *)pbInput = 29426128;
  v65 = 0;
  v66 = 0;
  phProvider = 0;
  v23 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( a9 == 1 )
  {
    if ( v23 < 0
      || (v23 = DmSetWindowsAIKPlatformStorageLocation(phProvider), v23 < 0)
      || (hObject = 0, v23 = NCryptOpenKey(phProvider, &hObject, L"Windows AIK", 0, 0), v23 < 0) )
    {
      v25 = a8;
      if ( !a8 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_35;
      v26 = L"DmGenerateMaaAttestationClaims: SetWindowsAik Failed";
      goto LABEL_34;
    }
  }
  else if ( v23 < 0
         || (hObject = 0,
             v23 = NCryptImportKey(phProvider, 0, L"PcpTpmPersistentKeyBlob", 0, &hObject, v77, 0xCu, 0),
             v23 < 0)
         || (v23 = NCryptSetProperty(hObject, L"KeyCertificateFromTpmNvram", pbInput, 4u, 0), v23 < 0) )
  {
    v25 = a8;
    if ( !a8 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
      goto LABEL_35;
    v26 = L"DmGenerateMaaAttestationClaims: SetAzureAik Failed";
LABEL_34:
    McTemplateU0zd_EventWriteTransfer(v24, EnterpriseDiagnosticsTPMFunctionFailure, v26, (unsigned int)v23);
    goto LABEL_35;
  }
  LODWORD(v65) = 3;
  *((_QWORD *)&v65 + 1) = hObject;
  v25 = a8;
LABEL_35:
  v74[0] = 3;
  v74[2] = 0;
  v74[1] = a1;
  v72 = 0;
  v73 = 0;
  if ( a2 )
  {
    LODWORD(v72) = 3;
    *((_QWORD *)&v72 + 1) = a2;
  }
  v27 = v54;
  if ( v54 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v53);
    AttestationCloseSession(v27);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v53);
  }
  v54 = 0;
  v28 = 0;
  v29 = &v72;
  if ( !a2 )
    v29 = 0;
  v30 = -1;
  do
    ++v30;
  while ( *(_WORD *)(a4 + 2 * v30) );
  LOBYTE(v28) = a2 != 0;
  v31 = AttestationCreateSession(v55, a6, a4, (unsigned int)(v30 + 1), 0, &v65, v74, v29, v28, &v54);
  Report = v31;
  if ( v31 )
  {
    if ( v25 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v32,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: AttestationCreateSession Failed",
        v31);
LABEL_47:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    SetDllDirectoryW(0);
    v19 = Report;
LABEL_83:
    __1__unique_storage_U__resource_policy__KP6AJ_K__E_1_AttestationCloseSession__YAJ0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
    return v19;
  }
  v63 = 0;
  v64 = 0;
  v58 = 0;
  v59 = 0;
  v34 = 0;
  v49[0] = 0;
  v35 = 0;
  v53 = 0;
  v60[0] = v61;
  v36 = (wil *)v61;
  v60[1] = v61;
  v61[0] = 0;
  v37 = v67;
  v38 = v68;
  while ( !v34 )
  {
    if ( v35 >= 20 )
    {
      if ( v25 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v36,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateMaaAttestationClaims: Invalid Data",
          2147942413LL);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v60);
      std::vector<unsigned char>::_Tidy(&v58);
      std::vector<unsigned char>::_Tidy(&v63);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      SetDllDirectoryW(0);
      v19 = -2147024883;
      goto LABEL_83;
    }
    if ( (int)Attest(v54, &v63, &v58, v49, dwFlags, pbData) < 0 )
    {
      if ( v25 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v36,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGenerateMaaAttestationClaims: Attest Failed",
          1);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v60);
      std::vector<unsigned char>::_Tidy(&v58);
      std::vector<unsigned char>::_Tidy(&v63);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      SetDllDirectoryW(0);
      goto LABEL_56;
    }
    if ( *((_QWORD *)&v58 + 1) != (_QWORD)v58 )
    {
      try
      {
        LOBYTE(pbData) = v35 == 1;
        dwFlags = v60;
        v39 = SendToAttestationServiceOld(v76, &v58, v12, v38);
        std::vector<unsigned char>::operator=(&v63, v39);
        std::vector<unsigned char>::_Tidy(v76);
      }
      catch ( const web::http::http_exception *v75 )
      {
        v44 = *((_DWORD *)v75 + 6);
        if ( (int)v44 > 0 )
          v44 = (unsigned __int16)v44 | 0x80070000;
        LODWORD(v55) = v44;
        if ( a8 )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            McTemplateU0zd_EventWriteTransfer(
              v36,
              EnterpriseDiagnosticsTPMFunctionFailure,
              L"DmGenerateMaaAttestationClaims: SendToAttestationServiceFailed HTTP Error",
              v44);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
              McTemplateU0zd_EventWriteTransfer(v36, EnterpriseDiagnosticsTPMFunctionFailure, v60[0], v44);
          }
        }
        goto LABEL_59;
      }
      catch ( ... )
      {
        v45 = wil::ResultFromCaughtException(v36);
        v46 = v45;
        LODWORD(v55) = v45;
        if ( a8 )
        {
          v36 = (wil *)(unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits;
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            McTemplateU0zd_EventWriteTransfer(
              (unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits,
              EnterpriseDiagnosticsTPMFunctionFailure,
              L"DmGenerateMaaAttestationClaims: SendToAttestationServiceFailed Failed",
              v45);
            v36 = (wil *)(unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits;
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
              McTemplateU0zd_EventWriteTransfer(
                (unsigned int)Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits,
                EnterpriseDiagnosticsTPMFunctionFailure,
                v60[0],
                v46);
          }
        }
LABEL_59:
        v19 = (unsigned int)v55;
        if ( (int)v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75F,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\attestationutils\\attestationutils.cpp",
            (const char *)(unsigned int)v55,
            (int)v60);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v60);
          std::vector<unsigned char>::_Tidy(&v58);
          std::vector<unsigned char>::_Tidy(&v63);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          goto LABEL_19;
        }
        v20 = 1;
        v25 = a8;
        v35 = v53;
        v12 = v69;
        v38 = v70;
        v37 = v71;
      }
    }
    v53 = ++v35;
    v34 = v49[0];
  }
  LODWORD(uBytes) = 0;
  Report = AttestationGetReport(v54, 0, 0, &uBytes);
  v40 = Report + 0x80000000;
  if ( (int)v40 >= 0 && Report != -2147024774 )
  {
    if ( v25 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v40,
        EnterpriseDiagnosticsTPMFunctionFailure,
        L"DmGenerateMaaAttestationClaims: AttestationGetReport",
        Report);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v60);
    std::vector<unsigned char>::_Tidy(&v58);
    std::vector<unsigned char>::_Tidy(&v63);
    goto LABEL_47;
  }
  *v37 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v41 = (unsigned int)uBytes;
  *v62 = uBytes;
  if ( (int)AttestationGetReport(v54, *v37, v41, &uBytes) >= 0 )
  {
    v20 = 0;
  }
  else if ( v25 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0zd_EventWriteTransfer(
      v42,
      EnterpriseDiagnosticsTPMFunctionFailure,
      L"DmGenerateMaaAttestationClaims: AttestationGetReport",
      1);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v60);
  std::vector<unsigned char>::_Tidy(&v58);
  std::vector<unsigned char>::_Tidy(&v63);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  SetDllDirectoryW(0);
  __1__unique_storage_U__resource_policy__KP6AJ_K__E_1_AttestationCloseSession__YAJ0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
  return v20;
}

```

## disassembly

```asm
0x180089a90  push    rbx
0x180089a92  push    rsi
0x180089a93  push    rdi
0x180089a94  push    r12
0x180089a96  push    r13
0x180089a98  push    r14
0x180089a9a  push    r15
0x180089a9c  sub     rsp, 3B0h
0x180089aa3  mov     rax, cs:__security_cookie
0x180089aaa  xor     rax, rsp
0x180089aad  mov     [rsp+3E8h+var_48], rax
0x180089ab5  mov     r13, r9
0x180089ab8  mov     r12, r8
0x180089abb  mov     r15, rdx
0x180089abe  mov     r14, rcx
0x180089ac1  mov     [rsp+3E8h+var_2D8], r8
0x180089ac9  mov     rax, [rsp+3E8h+arg_20]
0x180089ad1  mov     [rsp+3E8h+var_368], rax
0x180089ad9  mov     rax, [rsp+3E8h+arg_30]
0x180089ae1  mov     [rsp+3E8h+var_2E0], rax
0x180089ae9  mov     [rsp+3E8h+var_2D0], rax
0x180089af1  mov     rax, [rsp+3E8h+arg_48]
0x180089af9  mov     [rsp+3E8h+var_2E8], rax
0x180089b01  mov     [rsp+3E8h+var_2C8], rax
0x180089b09  mov     rax, [rsp+3E8h+arg_50]
0x180089b11  mov     [rsp+3E8h+var_320], rax
0x180089b19  xor     ebx, ebx
0x180089b1b  test    rcx, rcx
0x180089b1e  jz      loc_18008A402
0x180089b24  test    r8, r8
0x180089b27  jz      loc_18008A402
0x180089b2d  test    r9, r9
0x180089b30  jz      loc_18008A402
0x180089b36  mov     [rsp+3E8h+var_370], rbx
0x180089b3b  mov     edi, 104h
0x180089b40  mov     edx, edi; uSize
0x180089b42  lea     rcx, [rsp+3E8h+Buffer]; lpBuffer
0x180089b4a  call    cs:__imp_GetSystemDirectoryW
0x180089b51  nop     dword ptr [rax+rax+00h]
0x180089b56  dec     eax
0x180089b58  cmp     eax, 102h
0x180089b5d  ja      loc_18008A3BF
0x180089b63  lea     r8, aHealthattestat; "\\HealthAttestationClient"
0x180089b6a  mov     edx, edi; unsigned __int64
0x180089b6c  lea     rcx, [rsp+3E8h+Buffer]; unsigned __int16 *
0x180089b74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180089b79  test    eax, eax
0x180089b7b  jns     short loc_180089BB5
0x180089b7d  lea     edi, [rbx+1]
0x180089b80  cmp     [rsp+3E8h+arg_38], ebx
0x180089b87  jz      loc_18008A0D3
0x180089b8d  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089b94  jz      loc_18008A0D3
0x180089b9a  mov     r9d, edi
0x180089b9d  lea     r8, aDmgeneratemaaa_11; "DmGenerateMaaAttestationClaims: StringC"...
0x180089ba4  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089bab  call    McTemplateU0zd_EventWriteTransfer
0x180089bb0  jmp     loc_18008A0D3
0x180089bb5  lea     rcx, [rsp+3E8h+Buffer]; lpPathName
0x180089bbd  call    cs:__imp_SetDllDirectoryW
0x180089bc4  nop     dword ptr [rax+rax+00h]
0x180089bc9  test    eax, eax
0x180089bcb  jnz     short loc_180089C22
0x180089bcd  call    cs:__imp_GetLastError
0x180089bd4  nop     dword ptr [rax+rax+00h]
0x180089bd9  mov     esi, eax
0x180089bdb  test    eax, eax
0x180089bdd  jle     short loc_180089BE8
0x180089bdf  movzx   esi, ax
0x180089be2  or      esi, 80070000h
0x180089be8  cmp     [rsp+3E8h+arg_38], ebx
0x180089bef  jz      loc_18008A3F4
0x180089bf5  mov     edi, 1
0x180089bfa  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089c01  jz      loc_18008A3F4
0x180089c07  mov     r9d, esi
0x180089c0a  lea     r8, aDmgeneratemaaa_9; "DmGenerateMaaAttestationClaims: SetDllD"...
0x180089c11  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089c18  call    McTemplateU0zd_EventWriteTransfer
0x180089c1d  jmp     loc_18008A3F4
0x180089c22  mov     edi, 1
0x180089c27  mov     [rsp+3E8h+var_35F], dil
0x180089c2f  call    ?InitializeAttestationApis@@YAJXZ; InitializeAttestationApis(void)
0x180089c34  mov     esi, eax
0x180089c36  test    eax, eax
0x180089c38  jns     short loc_180089C76
0x180089c3a  cmp     [rsp+3E8h+arg_38], ebx
0x180089c41  jz      short loc_180089C63
0x180089c43  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089c4a  jz      short loc_180089C63
0x180089c4c  mov     r9d, eax
0x180089c4f  lea     r8, aDmgeneratemaaa_1; "DmGenerateMaaAttestationClaims: Initial"...
0x180089c56  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089c5d  call    McTemplateU0zd_EventWriteTransfer
0x180089c62  nop
0x180089c63  xor     ecx, ecx; lpPathName
0x180089c65  call    cs:__imp_SetDllDirectoryW
0x180089c6c  nop     dword ptr [rax+rax+00h]
0x180089c71  jmp     loc_18008A3F4
0x180089c76  mov     [rsp+3E8h+hObject], rbx
0x180089c7b  mov     dword ptr [rsp+3E8h+var_270], 4D54504Bh
0x180089c86  mov     [rsp+3E8h+var_268], 81000003h
0x180089c91  mov     [rsp+3E8h+var_26C], 0Ch
0x180089c9c  mov     dword ptr [rsp+3E8h+pbInput], 1C101D0h
0x180089ca7  xorps   xmm0, xmm0
0x180089caa  xor     eax, eax
0x180089cac  movups  [rsp+3E8h+var_300], xmm0
0x180089cb4  mov     [rsp+3E8h+var_2F0], rax
0x180089cbc  mov     [rsp+3E8h+phProvider], rbx
0x180089cc1  xor     r8d, r8d; dwFlags
0x180089cc4  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180089ccb  lea     rcx, [rsp+3E8h+phProvider]; phProvider
0x180089cd0  call    cs:__imp_NCryptOpenStorageProvider
0x180089cd7  nop     dword ptr [rax+rax+00h]
0x180089cdc  cmp     [rsp+3E8h+arg_40], edi
0x180089ce3  jnz     loc_180089D81
0x180089ce9  test    eax, eax
0x180089ceb  js      short loc_180089D59
0x180089ced  mov     rcx, [rsp+3E8h+phProvider]; hObject
0x180089cf2  call    ?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z; DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)
0x180089cf7  test    eax, eax
0x180089cf9  js      short loc_180089D59
0x180089cfb  mov     rsi, [rsp+3E8h+hObject]
0x180089d00  test    rsi, rsi
0x180089d03  jz      short loc_180089D28
0x180089d05  lea     rcx, [rsp+3E8h+var_378]; this
0x180089d0a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089d0f  mov     rcx, rsi; hObject
0x180089d12  call    cs:__imp_NCryptFreeObject
0x180089d19  nop     dword ptr [rax+rax+00h]
0x180089d1e  lea     rcx, [rsp+3E8h+var_378]; this
0x180089d23  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089d28  mov     [rsp+3E8h+hObject], rbx
0x180089d2d  mov     [rsp+3E8h+dwFlags], ebx; dwFlags
0x180089d31  xor     r9d, r9d; dwLegacyKeySpec
0x180089d34  lea     r8, pszKeyName; "Windows AIK"
0x180089d3b  lea     rdx, [rsp+3E8h+hObject]; phKey
0x180089d40  mov     rcx, [rsp+3E8h+phProvider]; hProvider
0x180089d45  call    cs:__imp_NCryptOpenKey
0x180089d4c  nop     dword ptr [rax+rax+00h]
0x180089d51  test    eax, eax
0x180089d53  jns     loc_180089E2D
0x180089d59  mov     esi, [rsp+3E8h+arg_38]
0x180089d60  test    esi, esi
0x180089d62  jz      loc_180089E78
0x180089d68  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089d6f  jz      loc_180089E78
0x180089d75  lea     r8, aDmgeneratemaaa_2; "DmGenerateMaaAttestationClaims: SetWind"...
0x180089d7c  jmp     loc_180089E69
0x180089d81  test    eax, eax
0x180089d83  js      loc_180089E4E
0x180089d89  mov     rsi, [rsp+3E8h+hObject]
0x180089d8e  test    rsi, rsi
0x180089d91  jz      short loc_180089DB6
0x180089d93  lea     rcx, [rsp+3E8h+var_378]; this
0x180089d98  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089d9d  mov     rcx, rsi; hObject
0x180089da0  call    cs:__imp_NCryptFreeObject
0x180089da7  nop     dword ptr [rax+rax+00h]
0x180089dac  lea     rcx, [rsp+3E8h+var_378]; this
0x180089db1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089db6  mov     [rsp+3E8h+hObject], rbx
0x180089dbb  mov     [rsp+3E8h+var_3B0], ebx; dwFlags
0x180089dbf  mov     [rsp+3E8h+cbData], 0Ch; cbData
0x180089dc7  lea     rax, [rsp+3E8h+var_270]
0x180089dcf  mov     [rsp+3E8h+pbData], rax; pbData
0x180089dd4  lea     rax, [rsp+3E8h+hObject]
0x180089dd9  mov     qword ptr [rsp+3E8h+dwFlags], rax; phKey
0x180089dde  xor     r9d, r9d; pParameterList
0x180089de1  lea     r8, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x180089de8  xor     edx, edx; hImportKey
0x180089dea  mov     rcx, [rsp+3E8h+phProvider]; hProvider
0x180089def  call    cs:__imp_NCryptImportKey
0x180089df6  nop     dword ptr [rax+rax+00h]
0x180089dfb  test    eax, eax
0x180089dfd  js      short loc_180089E4E
0x180089dff  mov     [rsp+3E8h+dwFlags], ebx; dwFlags
0x180089e03  mov     r9d, 4; cbInput
0x180089e09  lea     r8, [rsp+3E8h+pbInput]; pbInput
0x180089e11  lea     rdx, aKeycertificate; "KeyCertificateFromTpmNvram"
0x180089e18  mov     rcx, [rsp+3E8h+hObject]; hObject
0x180089e1d  call    cs:__imp_NCryptSetProperty
0x180089e24  nop     dword ptr [rax+rax+00h]
0x180089e29  test    eax, eax
0x180089e2b  js      short loc_180089E4E
0x180089e2d  mov     dword ptr [rsp+3E8h+var_300], 3
0x180089e38  mov     rax, [rsp+3E8h+hObject]
0x180089e3d  mov     qword ptr [rsp+3E8h+var_300+8], rax
0x180089e45  mov     esi, [rsp+3E8h+arg_38]
0x180089e4c  jmp     short loc_180089E78
0x180089e4e  mov     esi, [rsp+3E8h+arg_38]
0x180089e55  test    esi, esi
0x180089e57  jz      short loc_180089E78
0x180089e59  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089e60  jz      short loc_180089E78
0x180089e62  lea     r8, aDmgeneratemaaa_7; "DmGenerateMaaAttestationClaims: SetAzur"...
0x180089e69  mov     r9d, eax
0x180089e6c  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089e73  call    McTemplateU0zd_EventWriteTransfer
0x180089e78  mov     [rsp+3E8h+var_2A8], 3
0x180089e84  mov     [rsp+3E8h+var_298], rbx
0x180089e8c  mov     [rsp+3E8h+var_2A0], r14
0x180089e94  xorps   xmm0, xmm0
0x180089e97  xor     eax, eax
0x180089e99  movups  [rsp+3E8h+var_2C0], xmm0
0x180089ea1  mov     [rsp+3E8h+var_2B0], rax
0x180089ea9  test    r15, r15
0x180089eac  jz      short loc_180089EC1
0x180089eae  mov     dword ptr [rsp+3E8h+var_2C0], 3
0x180089eb9  mov     qword ptr [rsp+3E8h+var_2C0+8], r15
0x180089ec1  mov     r14, [rsp+3E8h+var_370]
0x180089ec6  test    r14, r14
0x180089ec9  jz      short loc_180089EEE
0x180089ecb  lea     rcx, [rsp+3E8h+var_378]; this
0x180089ed0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089ed5  mov     rcx, r14
0x180089ed8  call    cs:__imp_AttestationCloseSession
0x180089edf  nop     dword ptr [rax+rax+00h]
0x180089ee4  lea     rcx, [rsp+3E8h+var_378]; this
0x180089ee9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089eee  mov     [rsp+3E8h+var_370], rbx
0x180089ef3  mov     edx, ebx
0x180089ef5  test    r15, r15
0x180089ef8  setnz   dl
0x180089efb  lea     rax, [rsp+3E8h+var_2C0]
0x180089f03  test    r15, r15
0x180089f06  cmovz   rax, rbx
0x180089f0a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180089f0e  inc     r9
0x180089f11  cmp     [r13+r9*2+0], bx
0x180089f17  jnz     short loc_180089F0E
0x180089f19  inc     r9d
0x180089f1c  lea     rcx, [rsp+3E8h+var_370]
0x180089f21  mov     [rsp+3E8h+var_3A0], rcx
0x180089f26  mov     [rsp+3E8h+var_3A8], edx
0x180089f2a  mov     qword ptr [rsp+3E8h+var_3B0], rax
0x180089f2f  lea     rax, [rsp+3E8h+var_2A8]
0x180089f37  mov     qword ptr [rsp+3E8h+cbData], rax
0x180089f3c  lea     rax, [rsp+3E8h+var_300]
0x180089f44  mov     [rsp+3E8h+pbData], rax
0x180089f49  mov     [rsp+3E8h+dwFlags], ebx
0x180089f4d  mov     r8, r13
0x180089f50  mov     edx, [rsp+3E8h+arg_28]
0x180089f57  mov     rcx, [rsp+3E8h+var_368]
0x180089f5f  call    cs:__imp_AttestationCreateSession
0x180089f66  nop     dword ptr [rax+rax+00h]
0x180089f6b  mov     r14d, eax
0x180089f6e  test    eax, eax
0x180089f70  jz      short loc_180089FC2
0x180089f72  test    esi, esi
0x180089f74  jz      short loc_180089F96
0x180089f76  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x180089f7d  jz      short loc_180089F96
0x180089f7f  mov     r9d, eax
0x180089f82  lea     r8, aDmgeneratemaaa_6; "DmGenerateMaaAttestationClaims: Attesta"...
0x180089f89  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x180089f90  call    McTemplateU0zd_EventWriteTransfer
0x180089f95  nop
0x180089f96  lea     rcx, [rsp+3E8h+hObject]
0x180089f9b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180089fa0  nop
0x180089fa1  lea     rcx, [rsp+3E8h+phProvider]
0x180089fa6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180089fab  nop
0x180089fac  xor     ecx, ecx; lpPathName
0x180089fae  call    cs:__imp_SetDllDirectoryW
0x180089fb5  nop     dword ptr [rax+rax+00h]
0x180089fba  mov     esi, r14d
0x180089fbd  jmp     loc_18008A3F4
0x180089fc2  xorps   xmm0, xmm0
0x180089fc5  movdqu  [rsp+3E8h+var_318], xmm0
0x180089fce  mov     [rsp+3E8h+var_308], rbx
0x180089fd6  movdqu  [rsp+3E8h+var_358], xmm0
0x180089fdf  mov     [rsp+3E8h+var_348], rbx
0x180089fe7  mov     al, bl
0x180089fe9  mov     [rsp+3E8h+var_398], bl
0x180089fed  mov     r14d, ebx
0x180089ff0  mov     [rsp+3E8h+var_378], ebx
0x180089ff4  lea     rcx, [rsp+3E8h+var_330]
0x180089ffc  mov     [rsp+3E8h+var_340], rcx
0x18008a004  lea     rcx, [rsp+3E8h+var_330]
0x18008a00c  mov     [rsp+3E8h+var_338], rcx
0x18008a014  mov     [rsp+3E8h+var_330], bx
0x18008a01c  mov     r15, [rsp+3E8h+var_2E8]
0x18008a024  mov     r13, [rsp+3E8h+var_2E0]
0x18008a02c  test    al, al
0x18008a02e  jnz     loc_18008A26C
0x18008a034  cmp     r14d, 14h
0x18008a038  jge     loc_18008A1ED
0x18008a03e  lea     r9, [rsp+3E8h+var_398]
0x18008a043  lea     r8, [rsp+3E8h+var_358]
0x18008a04b  lea     rdx, [rsp+3E8h+var_318]
0x18008a053  mov     rcx, [rsp+3E8h+var_370]
0x18008a058  call    ?Attest@@YAJ_KAEAV?$vector@EV?$allocator@E@std@@@std@@1AEA_N@Z; Attest(unsigned __int64,std::vector<uchar> &,std::vector<uchar> &,bool &)
0x18008a05d  test    eax, eax
0x18008a05f  jns     short loc_18008A0DA
0x18008a061  test    esi, esi
0x18008a063  jz      short loc_18008A085
0x18008a065  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x18008a06c  jz      short loc_18008A085
  ... truncated ...
```
