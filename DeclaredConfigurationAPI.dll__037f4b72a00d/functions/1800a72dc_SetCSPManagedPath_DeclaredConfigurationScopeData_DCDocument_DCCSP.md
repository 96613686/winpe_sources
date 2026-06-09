# SetCSPManagedPath(DeclaredConfigurationScopeData *,DCDocument *,DCCSP *)

- ea: `0x1800a72dc`
- end: `0x1800a83d2`
- name: `?SetCSPManagedPath@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCCSP@@@Z`
- size: `4342`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, struct DCCSP *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ae150`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018cc4`
- `0x1800192b4`
- `0x180019d38`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18004d158`
- `0x18004d1ac`
- `0x18004dc70`
- `0x18004eb9c`
- `0x18004ec50`
- `0x18005ec48`
- `0x18005efe8`
- `0x1800600bc`
- `0x18009a2e4`
- `0x1800a0de4`
- `0x1800a5bf0`
- `0x1800a72dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a7758`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a7758`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800a758b`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800a758b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800a759b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800a759b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a828b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a828b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7a34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7fc2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7a34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7fc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a7b4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a806f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a7b4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a806f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a78c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a79e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7f73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a814f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a78c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a79e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7c39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7f73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a814f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a7c5e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a8174`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a7c5e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800a8174`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x1800a8222`
- `api-ms-win-shcore-registry-l1-1-0!SHCopyKeyW` at `0x1800a8222`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a77b7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7939`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7bca`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7d93`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7ed9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a80e2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a77b7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7939`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7bca`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7d93`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a7ed9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a80e2`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800a767d`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800a76fd`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800a767d`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800a76fd`

## string_xrefs

- `0x1800a7d04`: `Failed to find valid UserSid`
- `0x1800a780a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a7998`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a7d18`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a7f36`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a7559`: `SetCSPManagedPath`
- `0x1800a82fb`: `SetCSPManagedPath`
- `0x1800a7591`: `clientcertificateinstall/scep`
- `0x1800a7a67`: `SetCSPManagedPath create new key path`
- `0x1800a7ff5`: `SetCSPManagedPath create new key path`
- `0x1800a8248`: `SetCSPManagedPath ShCopyKey`
- `0x1800a82b5`: `SetCSPManagedPath delete reg tree`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetCSPManagedPath(const unsigned __int16 **a1, struct DCDocument *a2, struct DCCSP *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rax
  _WORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // r8
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  void *v14; // rcx
  unsigned __int16 **v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 i; // rax
  __int64 v21; // rax
  char v22; // dl
  int v23; // ecx
  signed int MdmEnrollmentWithLinkedEnrollment; // ebx
  __int16 v25; // r8
  int v26; // r9d
  char **v27; // rcx
  const wchar_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // r8
  _QWORD *v33; // rdx
  const unsigned __int16 *v34; // rdi
  int *v35; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v37; // r12
  const wchar_t *v38; // rdx
  __int64 v39; // rdx
  LSTATUS v40; // eax
  bool v41; // cc
  const WCHAR *v42; // rdx
  LPCWSTR *v43; // rsi
  int *v44; // rdi
  const unsigned __int16 *v45; // rbx
  char v46; // al
  const wchar_t *v47; // rdx
  __int64 v48; // rdx
  HKEY *v49; // rcx
  LSTATUS v50; // eax
  LSTATUS v51; // eax
  int v52; // ecx
  HKEY *v53; // rcx
  LSTATUS v54; // eax
  int *v55; // rdi
  const unsigned __int16 *v56; // rbx
  const WCHAR *v57; // rdx
  HKEY *v58; // rcx
  int *v59; // rbx
  char v60; // al
  const wchar_t *v61; // rsi
  const wchar_t *v62; // rdx
  const WCHAR *v63; // rdx
  LSTATUS v64; // r12d
  LPCWSTR *v65; // rdi
  int *v66; // rbx
  char v67; // al
  const wchar_t *v68; // rdx
  __int64 v69; // rdx
  LSTATUS v70; // eax
  LSTATUS v71; // eax
  int v72; // ecx
  LSTATUS v73; // eax
  int *v74; // rbx
  const WCHAR *v75; // rdx
  const WCHAR *v76; // rdx
  LSTATUS v77; // eax
  int v78; // ecx
  const wchar_t *v79; // r8
  const WCHAR *v80; // rdx
  LSTATUS v81; // eax
  const wchar_t *v82; // r9
  int phkResult; // [rsp+20h] [rbp-218h]
  wchar_t phkResulta; // [rsp+20h] [rbp-218h]
  int phkResultb; // [rsp+20h] [rbp-218h]
  int phkResultc; // [rsp+20h] [rbp-218h]
  int phkResultd; // [rsp+20h] [rbp-218h]
  long double samDesired; // [rsp+28h] [rbp-210h]
  const char *samDesireda; // [rsp+28h] [rbp-210h]
  HKEY hkeyDest; // [rsp+60h] [rbp-1D8h] BYREF
  LPCWSTR v92; // [rsp+68h] [rbp-1D0h] BYREF
  _WORD *v93; // [rsp+70h] [rbp-1C8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-1B8h] BYREF
  DWORD cValues; // [rsp+88h] [rbp-1B0h] BYREF
  HKEY v97[2]; // [rsp+90h] [rbp-1A8h] BYREF
  char v98; // [rsp+A0h] [rbp-198h]
  DWORD v99; // [rsp+B0h] [rbp-188h] BYREF
  LPCWSTR pszSrcSubKey[3]; // [rsp+B8h] [rbp-180h] BYREF
  unsigned __int64 v101; // [rsp+D0h] [rbp-168h]
  int v102[2]; // [rsp+D8h] [rbp-160h] BYREF
  unsigned __int64 v103; // [rsp+F0h] [rbp-148h]
  HKEY v104[2]; // [rsp+100h] [rbp-138h] BYREF
  char v105; // [rsp+110h] [rbp-128h]
  int v106[2]; // [rsp+120h] [rbp-118h] BYREF
  unsigned __int64 v107; // [rsp+138h] [rbp-100h]
  unsigned __int16 *v108[3]; // [rsp+140h] [rbp-F8h] BYREF
  unsigned __int64 v109; // [rsp+158h] [rbp-E0h]
  char *v110[4]; // [rsp+160h] [rbp-D8h] BYREF
  _BYTE v111[32]; // [rsp+180h] [rbp-B8h] BYREF
  unsigned __int16 v112[40]; // [rsp+1A0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  std::wstring::wstring((__int64)v108);
  std::wstring::wstring((__int64)v111);
  std::wstring::wstring((__int64)v110);
  v7 = (_QWORD *)(v6 + 88);
  if ( *(_QWORD *)(v6 + 112) > 7u )
    v7 = (_QWORD *)*v7;
  v8 = (_WORD *)v7 + 2;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  std::wstring::_Assign<unsigned short>((char **)v108, v8, (char *)v10);
  v11 = (const unsigned __int16 *)v108;
  if ( v109 > 7 )
    v11 = v108[0];
  if ( (unsigned int)DCDoesCspNeedPrefix(v11) )
  {
    v15 = v108;
    if ( v109 > 7 )
      v15 = (unsigned __int16 **)v108[0];
    v16 = std::operator+<unsigned short>(v104, L"./", (char *)a2 + 32);
    v17 = std::operator+<unsigned short>(pszSrcSubKey, v16, L"/");
    v18 = std::operator+<unsigned short>(v102, v17, v15);
    v19 = std::operator+<unsigned short>(v106, v18, L"/");
    std::wstring::operator=(v111, v19);
    std::wstring::_Tidy_deallocate(v106);
    std::wstring::_Tidy_deallocate(v102);
    std::wstring::_Tidy_deallocate(pszSrcSubKey);
    v14 = v104;
  }
  else
  {
    v12 = std::operator+<unsigned short>(v102, L"./", v108);
    v13 = std::operator+<unsigned short>(v106, v12, L"/");
    std::wstring::operator=(v111, v13);
    std::wstring::_Tidy_deallocate(v106);
    v14 = v102;
  }
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Assign<unsigned short>(v110, &word_180142E98, 0);
  for ( i = *((_QWORD *)a3 + 2); i != *((_QWORD *)a3 + 3); i += 16 )
  {
    if ( *(_QWORD *)(*(_QWORD *)i + 248LL) )
    {
      v21 = std::operator+<unsigned short>(v106, v111, *(_QWORD *)i + 232LL);
      std::wstring::operator=(v110, v21);
      std::wstring::_Tidy_deallocate(v106);
      memset_0(v112, 0, 0x4Eu);
      MdmEnrollmentWithLinkedEnrollment = FindMdmEnrollmentWithLinkedEnrollment(*a1, v112);
      if ( MdmEnrollmentWithLinkedEnrollment < 0 )
      {
        MdmEnrollmentWithLinkedEnrollment = -2147024894;
        if ( byte_180189FC1 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v23,
            (unsigned int)OrchestratorGenericFailure,
            (unsigned int)L"SetCSPManagedPath",
            (unsigned int)L"could not find a MDM enrollment associated with the MMPC enrollment",
            2);
        goto LABEL_161;
      }
      v27 = v110;
      if ( v110[3] > (char *)7 )
        LOWORD(v27) = v110[0];
      v28 = (const wchar_t *)o((wchar_t)v27, v22, v25, v26, phkResulta, samDesired);
      if ( !wcsstr(v28, L"clientcertificateinstall/scep") )
        goto LABEL_161;
      std::wstring::find_last_of(v110, L"/");
      std::wstring::wstring((__int64)pszSrcSubKey);
      try
      {
        v30 = std::wstring::substr(v110, v104, v29 + 1, -1);
        std::wstring::operator=(pszSrcSubKey, v30);
        std::wstring::_Tidy_deallocate(v104);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x643,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        std::wstring::_Tidy_deallocate(pszSrcSubKey);
        MdmEnrollmentWithLinkedEnrollment = -2147024882;
        goto LABEL_161;
      }
      v93 = 0;
      std::wstring::wstring((__int64)v106);
      std::wstring::wstring((__int64)v102);
      *(_OWORD *)v104 = 0;
      MdmEnrollmentWithLinkedEnrollment = DCGetGuidFromEnrollmentId(v112, (struct _GUID *)v104);
      if ( MdmEnrollmentWithLinkedEnrollment < 0
        || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v93,
              0),
            *(_OWORD *)v97 = *(_OWORD *)v104,
            MdmEnrollmentWithLinkedEnrollment = GetProviderID(v97, &v93),
            MdmEnrollmentWithLinkedEnrollment < 0) )
      {
        if ( byte_180189FC1 >= 0 )
          goto LABEL_160;
        v82 = L"could not find ServerID for main enrollment";
      }
      else
      {
        v32 = -1;
        do
          ++v32;
        while ( v93[v32] );
        std::wstring::_Assign<unsigned short>((char **)v106, v93, (char *)v32);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v93,
          0);
        MdmEnrollmentWithLinkedEnrollment = DCGetGuidFromEnrollmentId(*a1, (struct _GUID *)v104);
        if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v93,
            0);
          MdmEnrollmentWithLinkedEnrollment = GetProviderID(v104, &v93);
          if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
          {
            do
              ++v9;
            while ( v93[v9] );
            std::wstring::_Assign<unsigned short>((char **)v102, v93, (char *)v9);
            lpSubKey = 0;
            v92 = 0;
            hKey = 0;
            hkeyDest = 0;
            v33 = (_QWORD *)((char *)a2 + 32);
            if ( *((_QWORD *)a2 + 7) > 7u )
              v33 = (_QWORD *)*v33;
            if ( !(unsigned int)_o__wcsicmp(L"User", v33) )
            {
              v34 = a1[1];
              if ( !v34 || !*v34 )
              {
                MdmEnrollmentWithLinkedEnrollment = -2147024809;
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x66E,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
                  (const char *)0x80070057LL,
                  (int)"Failed to find valid UserSid",
                  samDesireda);
                goto LABEL_89;
              }
              v35 = v106;
              if ( v107 > 7 )
                v35 = *(int **)v106;
              v104[0] = (HKEY)&lpSubKey;
              v104[1] = 0;
              v105 = 1;
              IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
              v37 = L"OSData\\%s\\Software\\Microsoft\\SCEP\\%s";
              v38 = L"OSData\\%s\\Software\\Microsoft\\SCEP\\%s";
              if ( !IsStateSeparationEnabled )
                v38 = L"%s\\Software\\Microsoft\\SCEP\\%s";
              MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v104[1], v38, 2, v34, v35);
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v104);
              if ( MdmEnrollmentWithLinkedEnrollment < 0 )
              {
                v39 = 1655;
                goto LABEL_41;
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &hKey,
                0);
              v40 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0xF003Fu, &hKey);
              MdmEnrollmentWithLinkedEnrollment = v40;
              v41 = v40 <= 0;
              if ( v40 )
              {
LABEL_43:
                if ( !v41 )
                  MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v40 | 0x80070000;
                goto LABEL_89;
              }
              v97[0] = 0;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                v97,
                0);
              v42 = (const WCHAR *)pszSrcSubKey;
              if ( v101 > 7 )
                v42 = pszSrcSubKey[0];
              cValues = RegOpenKeyExW(hKey, v42, 0, 0xF003Fu, v97);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                v97,
                0);
              v43 = pszSrcSubKey;
              if ( v101 > 7 )
                v43 = (LPCWSTR *)pszSrcSubKey[0];
              v44 = v102;
              if ( v103 > 7 )
                v44 = *(int **)v102;
              v45 = a1[1];
              v104[0] = (HKEY)&v92;
              v104[1] = 0;
              v105 = 1;
              v46 = RtlIsStateSeparationEnabled();
              v47 = L"OSData\\%s\\Software\\Microsoft\\SCEP\\%s\\%s";
              if ( !v46 )
                v47 = L"%s\\Software\\Microsoft\\SCEP\\%s\\%s";
              MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v104[1], v47, 3, v45, v44, v43);
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v104);
              if ( MdmEnrollmentWithLinkedEnrollment < 0 )
              {
                v48 = 1690;
                goto LABEL_55;
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &hkeyDest,
                0);
              v50 = RegOpenKeyExW(HKEY_USERS, v92, 0, 0xF003Fu, &hkeyDest);
              if ( v50 == 2 )
              {
                if ( !cValues )
                {
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                    &hkeyDest,
                    0);
                  v51 = RegCreateKeyExW(HKEY_USERS, v92, 0, 0, 0, 0xF003Fu, 0, &hkeyDest, 0);
                  if ( v51 )
                  {
                    if ( v51 > 0 )
                      MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v51 | 0x80070000;
                    else
                      MdmEnrollmentWithLinkedEnrollment = v51;
                    if ( byte_180189FC1 < 0 )
                      McTemplateU0zzd_EventWriteTransfer(
                        v52,
                        (unsigned int)OrchestratorGenericFailure,
                        (unsigned int)L"SetCSPManagedPath create new key path",
                        (_DWORD)v92,
                        MdmEnrollmentWithLinkedEnrollment);
LABEL_56:
                    v49 = v97;
LABEL_57:
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v49);
                    goto LABEL_89;
                  }
                  goto LABEL_84;
                }
                v53 = v97;
LABEL_67:
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v53);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v92);
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
                std::wstring::_Tidy_deallocate(v102);
                std::wstring::_Tidy_deallocate(v106);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
                std::wstring::_Tidy_deallocate(pszSrcSubKey);
                MdmEnrollmentWithLinkedEnrollment = -2147024894;
LABEL_161:
                std::wstring::_Tidy_deallocate(v110);
                std::wstring::_Tidy_deallocate(v111);
                std::wstring::_Tidy_deallocate(v108);
                return (unsigned int)MdmEnrollmentWithLinkedEnrollment;
              }
              if ( v50 )
              {
                if ( v50 > 0 )
                  MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v50 | 0x80070000;
                else
                  MdmEnrollmentWithLinkedEnrollment = v50;
                goto LABEL_56;
              }
              if ( cValues )
              {
                cValues = 0;
                v54 = RegQueryInfoKeyW(hkeyDest, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
                MdmEnrollmentWithLinkedEnrollment = v54;
                if ( v54 > 0 )
                  MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v54 | 0x80070000;
                if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
                {
                  if ( cValues )
                    goto LABEL_84;
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                    &hkeyDest,
                    0);
                  v55 = v102;
                  if ( v103 > 7 )
                    v55 = *(int **)v102;
                  v56 = a1[1];
                  v104[0] = (HKEY)&v92;
                  v104[1] = 0;
                  v105 = 1;
                  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
                    v37 = L"%s\\Software\\Microsoft\\SCEP\\%s";
                  MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v104[1], v37, 2, v56, v55);
                  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v104);
                  if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
                  {
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                      &hkeyDest,
                      0);
                    RegOpenKeyExW(HKEY_USERS, v92, 0, 0xF003Fu, &hkeyDest);
                    v57 = (const WCHAR *)pszSrcSubKey;
                    if ( v101 > 7 )
                      v57 = pszSrcSubKey[0];
                    RegDeleteKeyW(hkeyDest, v57);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v97);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v92);
                    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
                    std::wstring::_Tidy_deallocate(v102);
                    std::wstring::_Tidy_deallocate(v106);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
                    std::wstring::_Tidy_deallocate(pszSrcSubKey);
                    MdmEnrollmentWithLinkedEnrollment = 0;
                    goto LABEL_161;
                  }
                  v48 = 1757;
                }
                else
                {
                  v48 = 1745;
                }
LABEL_55:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v48,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
                  (const char *)(unsigned int)MdmEnrollmentWithLinkedEnrollment,
                  phkResultc);
                goto LABEL_56;
              }
LABEL_84:
              v58 = v97;
LABEL_135:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v58);
              v76 = (const WCHAR *)pszSrcSubKey;
              if ( v101 > 7 )
                v76 = pszSrcSubKey[0];
              v77 = SHCopyKeyW(hKey, v76, hkeyDest, 0);
              if ( v77 )
              {
                if ( v77 > 0 )
                  MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v77 | 0x80070000;
                else
                  MdmEnrollmentWithLinkedEnrollment = v77;
                if ( byte_180189FC1 < 0 )
                {
                  v79 = L"SetCSPManagedPath ShCopyKey";
LABEL_143:
                  McTemplateU0zzd_EventWriteTransfer(
                    v78,
                    (unsigned int)OrchestratorGenericFailure,
                    (_DWORD)v79,
                    (_DWORD)lpSubKey,
                    MdmEnrollmentWithLinkedEnrollment);
                }
              }
              else
              {
                v80 = (const WCHAR *)pszSrcSubKey;
                if ( v101 > 7 )
                  v80 = pszSrcSubKey[0];
                v81 = RegDeleteTreeW(hKey, v80);
                if ( v81 )
                {
                  MdmEnrollmentWithLinkedEnrollment = v81 > 0 ? (unsigned __int16)v81 | 0x80070000 : v81;
                  if ( byte_180189FC1 < 0 )
                  {
                    v79 = L"SetCSPManagedPath delete reg tree";
                    goto LABEL_143;
                  }
                }
              }
LABEL_89:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v92);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
LABEL_160:
              std::wstring::_Tidy_deallocate(v102);
              std::wstring::_Tidy_deallocate(v106);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
              std::wstring::_Tidy_deallocate(pszSrcSubKey);
              goto LABEL_161;
            }
            v59 = v106;
            if ( v107 > 7 )
              v59 = *(int **)v106;
            v97[0] = (HKEY)&lpSubKey;
            v97[1] = 0;
            v98 = 1;
            v60 = RtlIsStateSeparationEnabled();
            v61 = L"OSData\\Software\\Microsoft\\SCEP\\%s";
            v62 = L"OSData\\Software\\Microsoft\\SCEP\\%s";
            if ( !v60 )
              v62 = L"Software\\Microsoft\\SCEP\\%s";
            MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v97[1], v62, 1, v59);
            wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v97);
            if ( MdmEnrollmentWithLinkedEnrollment < 0 )
            {
              v39 = 1782;
LABEL_41:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v39,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
                (const char *)(unsigned int)MdmEnrollmentWithLinkedEnrollment,
                phkResultb);
              goto LABEL_89;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hKey,
              0);
            v40 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
            MdmEnrollmentWithLinkedEnrollment = v40;
            v41 = v40 <= 0;
            if ( v40 )
              goto LABEL_43;
            v104[0] = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              v104,
              0);
            v63 = (const WCHAR *)pszSrcSubKey;
            if ( v101 > 7 )
              v63 = pszSrcSubKey[0];
            v64 = RegOpenKeyExW(hKey, v63, 0, 0xF003Fu, v104);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              v104,
              0);
            v65 = pszSrcSubKey;
            if ( v101 > 7 )
              v65 = (LPCWSTR *)pszSrcSubKey[0];
            v66 = v102;
            if ( v103 > 7 )
              v66 = *(int **)v102;
            v97[0] = (HKEY)&v92;
            v97[1] = 0;
            v98 = 1;
            v67 = RtlIsStateSeparationEnabled();
            v68 = L"OSData\\Software\\Microsoft\\SCEP\\%s\\%s";
            if ( !v67 )
              v68 = L"Software\\Microsoft\\SCEP\\%s\\%s";
            MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v97[1], v68, 2, v66, v65);
            wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v97);
            if ( MdmEnrollmentWithLinkedEnrollment < 0 )
            {
              v69 = 1816;
              goto LABEL_107;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hkeyDest,
              0);
            v70 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v92, 0, 0xF003Fu, &hkeyDest);
            if ( v70 == 2 )
            {
              if ( v64 )
              {
                v53 = v104;
                goto LABEL_67;
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &hkeyDest,
                0);
              v71 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v92, 0, 0, 0, 0xF003Fu, 0, &hkeyDest, 0);
              if ( v71 )
              {
                if ( v71 > 0 )
                  MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v71 | 0x80070000;
                else
                  MdmEnrollmentWithLinkedEnrollment = v71;
                if ( byte_180189FC1 < 0 )
                  McTemplateU0zzd_EventWriteTransfer(
                    v72,
                    (unsigned int)OrchestratorGenericFailure,
                    (unsigned int)L"SetCSPManagedPath create new key path",
                    (_DWORD)v92,
                    MdmEnrollmentWithLinkedEnrollment);
                goto LABEL_108;
              }
LABEL_134:
              v58 = v104;
              goto LABEL_135;
            }
            if ( v70 )
            {
              if ( v70 > 0 )
                MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v70 | 0x80070000;
              else
                MdmEnrollmentWithLinkedEnrollment = v70;
            }
            else
            {
              if ( !v64 )
                goto LABEL_134;
              v99 = 0;
              v73 = RegQueryInfoKeyW(hkeyDest, 0, 0, 0, 0, 0, 0, &v99, 0, 0, 0, 0);
              MdmEnrollmentWithLinkedEnrollment = v73;
              if ( v73 > 0 )
                MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v73 | 0x80070000;
              if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
              {
                if ( v99 )
                  goto LABEL_134;
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                  &hkeyDest,
                  0);
                v74 = v102;
                if ( v103 > 7 )
                  v74 = *(int **)v102;
                v97[0] = (HKEY)&v92;
                v97[1] = 0;
                v98 = 1;
                if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
                  v61 = L"Software\\Microsoft\\SCEP\\%s";
                MdmEnrollmentWithLinkedEnrollment = DCStringCchPrintfAllStrings(&v97[1], v61, 1, v74);
                wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v97);
                if ( MdmEnrollmentWithLinkedEnrollment >= 0 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                    &hkeyDest,
                    0);
                  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v92, 0, 0xF003Fu, &hkeyDest);
                  v75 = (const WCHAR *)pszSrcSubKey;
                  if ( v101 > 7 )
                    v75 = pszSrcSubKey[0];
                  RegDeleteKeyW(hkeyDest, v75);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v104);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyDest);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v92);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
                  std::wstring::_Tidy_deallocate(v102);
                  std::wstring::_Tidy_deallocate(v106);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
                  std::wstring::_Tidy_deallocate(pszSrcSubKey);
                  MdmEnrollmentWithLinkedEnrollment = 0;
                  goto LABEL_161;
                }
                v69 = 1883;
              }
              else
              {
                v69 = 1872;
              }
LABEL_107:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v69,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
                (const char *)(unsigned int)MdmEnrollmentWithLinkedEnrollment,
                phkResultd);
            }
LABEL_108:
            v49 = v104;
            goto LABEL_57;
          }
        }
        if ( byte_180189FC1 >= 0 )
          goto LABEL_160;
        v82 = L"could not find ServerID for mmpc enrollment";
      }
      McTemplateU0zzd_EventWriteTransfer(
        v31,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"SetCSPManagedPath",
        (_DWORD)v82,
        MdmEnrollmentWithLinkedEnrollment);
      goto LABEL_160;
    }
  }
  std::wstring::_Tidy_deallocate(v110);
  std::wstring::_Tidy_deallocate(v111);
  std::wstring::_Tidy_deallocate(v108);
  return 0;
}

```

## disassembly

```asm
0x1800a72dc  push    rbx
0x1800a72de  push    rsi
0x1800a72df  push    rdi
0x1800a72e0  push    r12
0x1800a72e2  push    r13
0x1800a72e4  push    r14
0x1800a72e6  push    r15
0x1800a72e8  sub     rsp, 200h
0x1800a72ef  mov     rax, cs:__security_cookie
0x1800a72f6  xor     rax, rsp
0x1800a72f9  mov     [rsp+238h+var_48], rax
0x1800a7301  mov     rsi, r8
0x1800a7304  mov     r14, rdx
0x1800a7307  mov     r13, rcx
0x1800a730a  lea     rcx, [rsp+238h+var_F8]
0x1800a7312  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a7317  nop
0x1800a7318  lea     rcx, [rsp+238h+var_B8]
0x1800a7320  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a7325  nop
0x1800a7326  lea     rcx, [rsp+238h+var_D8]
0x1800a732e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a7333  nop
0x1800a7334  lea     rax, [r8+58h]
0x1800a7338  cmp     qword ptr [rax+18h], 7
0x1800a733d  jbe     short loc_1800A7342
0x1800a733f  mov     rax, [rax]
0x1800a7342  lea     rdx, [rax+4]
0x1800a7346  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a734a  mov     r8, rdi
0x1800a734d  xor     r15d, r15d
0x1800a7350  inc     r8
0x1800a7353  cmp     [rdx+r8*2], r15w
0x1800a7358  jnz     short loc_1800A7350
0x1800a735a  lea     rcx, [rsp+238h+var_F8]
0x1800a7362  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a7367  lea     rcx, [rsp+238h+var_F8]
0x1800a736f  cmp     [rsp+238h+var_E0], 7
0x1800a7378  cmova   rcx, [rsp+238h+var_F8]; unsigned __int16 *
0x1800a7381  call    ?DCDoesCspNeedPrefix@@YAHPEBG@Z; DCDoesCspNeedPrefix(ushort const *)
0x1800a7386  lea     rdx, asc_180142BE8; "./"
0x1800a738d  test    eax, eax
0x1800a738f  jnz     short loc_1800A73E9
0x1800a7391  lea     r8, [rsp+238h+var_F8]
0x1800a7399  lea     rcx, [rsp+238h+var_160]
0x1800a73a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800a73a6  nop
0x1800a73a7  lea     r8, asc_18013EB9C; "/"
0x1800a73ae  mov     rdx, rax
0x1800a73b1  lea     rcx, [rsp+238h+var_118]
0x1800a73b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a73be  mov     rdx, rax
0x1800a73c1  lea     rcx, [rsp+238h+var_B8]
0x1800a73c9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a73ce  lea     rcx, [rsp+238h+var_118]
0x1800a73d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a73db  nop
0x1800a73dc  lea     rcx, [rsp+238h+var_160]
0x1800a73e4  jmp     loc_1800A749A
0x1800a73e9  lea     rbx, [rsp+238h+var_F8]
0x1800a73f1  cmp     [rsp+238h+var_E0], 7
0x1800a73fa  cmova   rbx, [rsp+238h+var_F8]
0x1800a7403  lea     r8, [r14+20h]
0x1800a7407  lea     rcx, [rsp+238h+var_138]
0x1800a740f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800a7414  nop
0x1800a7415  lea     r8, asc_18013EB9C; "/"
0x1800a741c  mov     rdx, rax
0x1800a741f  lea     rcx, [rsp+238h+pszSrcSubKey]
0x1800a7427  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a742c  nop
0x1800a742d  mov     r8, rbx
0x1800a7430  mov     rdx, rax
0x1800a7433  lea     rcx, [rsp+238h+var_160]
0x1800a743b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a7440  nop
0x1800a7441  lea     r8, asc_18013EB9C; "/"
0x1800a7448  mov     rdx, rax
0x1800a744b  lea     rcx, [rsp+238h+var_118]
0x1800a7453  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a7458  mov     rdx, rax
0x1800a745b  lea     rcx, [rsp+238h+var_B8]
0x1800a7463  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7468  lea     rcx, [rsp+238h+var_118]
0x1800a7470  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7475  nop
0x1800a7476  lea     rcx, [rsp+238h+var_160]
0x1800a747e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7483  nop
0x1800a7484  lea     rcx, [rsp+238h+pszSrcSubKey]
0x1800a748c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7491  nop
0x1800a7492  lea     rcx, [rsp+238h+var_138]
0x1800a749a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a749f  xor     r8d, r8d
0x1800a74a2  lea     rdx, word_180142E98
0x1800a74a9  lea     rcx, [rsp+238h+var_D8]
0x1800a74b1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a74b6  mov     rax, [rsi+10h]
0x1800a74ba  mov     rcx, [rsi+18h]
0x1800a74be  cmp     rax, rcx
0x1800a74c1  jz      loc_1800A8384
0x1800a74c7  mov     r8, [rax]
0x1800a74ca  cmp     [r8+0F8h], r15
0x1800a74d1  jnz     short loc_1800A74D9
0x1800a74d3  add     rax, 10h
0x1800a74d7  jmp     short loc_1800A74BE
0x1800a74d9  add     r8, 0E8h
0x1800a74e0  lea     rdx, [rsp+238h+var_B8]
0x1800a74e8  lea     rcx, [rsp+238h+var_118]
0x1800a74f0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x1800a74f5  mov     rdx, rax
0x1800a74f8  lea     rcx, [rsp+238h+var_D8]
0x1800a7500  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7505  lea     rcx, [rsp+238h+var_118]
0x1800a750d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7512  xor     edx, edx; Val
0x1800a7514  lea     r8d, [rdx+4Eh]; Size
0x1800a7518  lea     rcx, [rsp+238h+var_98]; void *
0x1800a7520  call    memset_0
0x1800a7525  lea     rdx, [rsp+238h+var_98]; unsigned __int16 *
0x1800a752d  mov     rcx, [r13+0]; unsigned __int16 *
0x1800a7531  call    ?FindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z; FindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)
0x1800a7536  mov     ebx, eax
0x1800a7538  test    eax, eax
0x1800a753a  jns     short loc_1800A7571
0x1800a753c  mov     ebx, 80070002h
0x1800a7541  cmp     cs:byte_180189FC1, r15b
0x1800a7548  jge     loc_1800A8357
0x1800a754e  mov     dword ptr [rsp+238h+phkResult], ebx
0x1800a7552  lea     r9, aCouldNotFindAM; "could not find a MDM enrollment associa"...
0x1800a7559  lea     r8, aSetcspmanagedp_1; "SetCSPManagedPath"
0x1800a7560  lea     rdx, OrchestratorGenericFailure
0x1800a7567  call    McTemplateU0zzd_EventWriteTransfer
0x1800a756c  jmp     loc_1800A8357
0x1800a7571  lea     rcx, [rsp+238h+var_D8]
0x1800a7579  cmp     [rsp+238h+var_C0], 7
0x1800a7582  cmova   rcx, [rsp+238h+var_D8]
0x1800a758b  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800a7591  lea     rdx, aClientcertific; "clientcertificateinstall/scep"
0x1800a7598  mov     rcx, rax; Str
0x1800a759b  call    cs:__imp_wcsstr
0x1800a75a1  test    rax, rax
0x1800a75a4  jz      loc_1800A8357
0x1800a75aa  lea     rdx, asc_18013EB9C; "/"
0x1800a75b1  lea     rcx, [rsp+238h+var_D8]
0x1800a75b9  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800a75be  mov     r8, rax
0x1800a75c1  lea     rcx, [rsp+238h+pszSrcSubKey]
0x1800a75c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a75ce  nop
0x1800a75cf  inc     r8
0x1800a75d2  mov     r9, rdi
0x1800a75d5  lea     rdx, [rsp+238h+var_138]
0x1800a75dd  lea     rcx, [rsp+238h+var_D8]
0x1800a75e5  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800a75ea  mov     rdx, rax
0x1800a75ed  lea     rcx, [rsp+238h+pszSrcSubKey]
0x1800a75f5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a75fa  lea     rcx, [rsp+238h+var_138]
0x1800a7602  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7607  nop
0x1800a7608  mov     [rsp+238h+var_1C8], r15
0x1800a760d  lea     rcx, [rsp+238h+var_118]
0x1800a7615  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a761a  nop
0x1800a761b  lea     rcx, [rsp+238h+var_160]
0x1800a7623  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a7628  nop
0x1800a7629  xorps   xmm1, xmm1
0x1800a762c  movups  xmmword ptr [rsp+238h+var_138], xmm1
0x1800a7634  lea     rdx, [rsp+238h+var_138]; struct _GUID *
0x1800a763c  lea     rcx, [rsp+238h+var_98]; unsigned __int16 *
0x1800a7644  call    ?DCGetGuidFromEnrollmentId@@YAJPEBGPEAU_GUID@@@Z; DCGetGuidFromEnrollmentId(ushort const *,_GUID *)
0x1800a7649  mov     ebx, eax
0x1800a764b  test    eax, eax
0x1800a764d  js      loc_1800A82E7
0x1800a7653  xor     edx, edx
0x1800a7655  lea     rcx, [rsp+238h+var_1C8]
0x1800a765a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a765f  movaps  xmm0, xmmword ptr [rsp+238h+var_138]
0x1800a7667  movdqa  xmmword ptr [rsp+238h+var_1A8], xmm0
0x1800a7670  lea     rdx, [rsp+238h+var_1C8]
0x1800a7675  lea     rcx, [rsp+238h+var_1A8]
0x1800a767d  call    cs:__imp_GetProviderID
0x1800a7683  mov     ebx, eax
0x1800a7685  test    eax, eax
0x1800a7687  js      loc_1800A82E7
0x1800a768d  mov     rdx, [rsp+238h+var_1C8]
0x1800a7692  mov     r8, rdi
0x1800a7695  inc     r8
0x1800a7698  cmp     [rdx+r8*2], r15w
0x1800a769d  jnz     short loc_1800A7695
0x1800a769f  lea     rcx, [rsp+238h+var_118]
0x1800a76a7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a76ac  xor     edx, edx
0x1800a76ae  lea     rcx, [rsp+238h+var_1C8]
0x1800a76b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a76b8  lea     rdx, [rsp+238h+var_138]; struct _GUID *
0x1800a76c0  mov     rcx, [r13+0]; unsigned __int16 *
0x1800a76c4  call    ?DCGetGuidFromEnrollmentId@@YAJPEBGPEAU_GUID@@@Z; DCGetGuidFromEnrollmentId(ushort const *,_GUID *)
0x1800a76c9  mov     ebx, eax
0x1800a76cb  test    eax, eax
0x1800a76cd  js      loc_1800A82D5
0x1800a76d3  xor     edx, edx
0x1800a76d5  lea     rcx, [rsp+238h+var_1C8]
0x1800a76da  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a76df  movaps  xmm0, xmmword ptr [rsp+238h+var_138]
0x1800a76e7  movdqa  xmmword ptr [rsp+238h+var_138], xmm0
0x1800a76f0  lea     rdx, [rsp+238h+var_1C8]
0x1800a76f5  lea     rcx, [rsp+238h+var_138]
0x1800a76fd  call    cs:__imp_GetProviderID
0x1800a7703  mov     ebx, eax
0x1800a7705  test    eax, eax
0x1800a7707  js      loc_1800A82D5
0x1800a770d  mov     rdx, [rsp+238h+var_1C8]
0x1800a7712  inc     rdi
0x1800a7715  cmp     [rdx+rdi*2], r15w
0x1800a771a  jnz     short loc_1800A7712
0x1800a771c  mov     r8, rdi
0x1800a771f  lea     rcx, [rsp+238h+var_160]
0x1800a7727  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a772c  mov     [rsp+238h+lpSubKey], r15
0x1800a7734  mov     [rsp+238h+var_1D0], r15
0x1800a7739  mov     [rsp+238h+hKey], r15
0x1800a773e  mov     [rsp+238h+hkeyDest], r15
0x1800a7743  lea     rdx, [r14+20h]
0x1800a7747  cmp     qword ptr [rdx+18h], 7
0x1800a774c  jbe     short loc_1800A7751
0x1800a774e  mov     rdx, [rdx]
0x1800a7751  lea     rcx, aUser_4; "User"
0x1800a7758  call    cs:__imp__o__wcsicmp
0x1800a775e  test    eax, eax
0x1800a7760  jnz     loc_1800A7D59
0x1800a7766  mov     rdi, [r13+8]
0x1800a776a  test    rdi, rdi
0x1800a776d  jz      loc_1800A7CFC
0x1800a7773  cmp     r15w, [rdi]
0x1800a7777  jz      loc_1800A7CFC
0x1800a777d  lea     rbx, [rsp+238h+var_118]
0x1800a7785  cmp     [rsp+238h+var_100], 7
0x1800a778e  cmova   rbx, qword ptr [rsp+238h+var_118]
0x1800a7797  lea     rax, [rsp+238h+lpSubKey]
0x1800a779f  mov     [rsp+238h+var_138], rax
0x1800a77a7  mov     [rsp+238h+var_138+8], r15
0x1800a77af  mov     [rsp+238h+var_128], 1
0x1800a77b7  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800a77bd  lea     rcx, aSSoftwareMicro_0; "%s\\Software\\Microsoft\\SCEP\\%s"
0x1800a77c4  lea     r12, aOsdataSSoftwar_0; "OSData\\%s\\Software\\Microsoft\\SCEP\\"...
0x1800a77cb  mov     rdx, r12
0x1800a77ce  test    al, al
0x1800a77d0  cmovz   rdx, rcx
0x1800a77d4  mov     [rsp+238h+phkResult], rbx; int
0x1800a77d9  mov     r9, rdi
0x1800a77dc  mov     r15d, 2
0x1800a77e2  mov     r8d, r15d
0x1800a77e5  lea     rcx, [rsp+238h+var_138+8]
0x1800a77ed  call    DCStringCchPrintfAllStrings
0x1800a77f2  mov     ebx, eax
0x1800a77f4  lea     rcx, [rsp+238h+var_138]
0x1800a77fc  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800a7801  test    ebx, ebx
0x1800a7803  jns     short loc_1800A7826
0x1800a7805  mov     edx, 677h; void *
0x1800a780a  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a7811  mov     r9d, ebx; char *
0x1800a7814  mov     rcx, [rsp+238h]; this
0x1800a781c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7821  jmp     loc_1800A7D29
0x1800a7826  xor     edx, edx
0x1800a7828  lea     rcx, [rsp+238h+hKey]
0x1800a782d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a7832  lea     rax, [rsp+238h+hKey]
0x1800a7837  mov     [rsp+238h+phkResult], rax; phkResult
0x1800a783c  mov     r14d, 0F003Fh
0x1800a7842  mov     r9d, r14d; samDesired
0x1800a7845  xor     r8d, r8d; ulOptions
0x1800a7848  mov     rdx, [rsp+238h+lpSubKey]; lpSubKey
0x1800a7850  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800a7857  call    cs:__imp_RegOpenKeyExW
0x1800a785d  mov     ebx, eax
0x1800a785f  test    eax, eax
0x1800a7861  jz      short loc_1800A7877
0x1800a7863  jle     loc_1800A7D29
0x1800a7869  movzx   ebx, ax
0x1800a786c  or      ebx, 80070000h
0x1800a7872  jmp     loc_1800A7D29
0x1800a7877  mov     [rsp+238h+var_1A8], 0
0x1800a7883  xor     edx, edx
0x1800a7885  lea     rcx, [rsp+238h+var_1A8]
0x1800a788d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a7892  lea     rdx, [rsp+238h+pszSrcSubKey]
0x1800a789a  cmp     [rsp+238h+var_168], 7
0x1800a78a3  cmova   rdx, [rsp+238h+pszSrcSubKey]; lpSubKey
0x1800a78ac  lea     rax, [rsp+238h+var_1A8]
0x1800a78b4  mov     [rsp+238h+phkResult], rax; phkResult
0x1800a78b9  mov     r9d, r14d; samDesired
0x1800a78bc  xor     r8d, r8d; ulOptions
0x1800a78bf  mov     rcx, [rsp+238h+hKey]; hKey
0x1800a78c4  call    cs:__imp_RegOpenKeyExW
  ... truncated ...
```
