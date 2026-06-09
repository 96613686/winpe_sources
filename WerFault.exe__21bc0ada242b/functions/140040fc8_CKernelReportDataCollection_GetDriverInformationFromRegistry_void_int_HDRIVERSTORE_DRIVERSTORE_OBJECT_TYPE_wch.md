# CKernelReportDataCollection::GetDriverInformationFromRegistry(void *,int (*)(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,wchar_t const *,_DEVPROPKEY const *,ulong *,uchar *,ulong,ulong *,ulong))

- ea: `0x140040fc8`
- end: `0x140041be2`
- name: `?GetDriverInformationFromRegistry@CKernelReportDataCollection@@AEAAJPEAXP6AHPEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEB_WPEBU_DEVPROPKEY@@PEAKPEAEK5K@Z@Z`
- size: `3098`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *__hidden this, void *, int (__high *)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x140040ee4`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140003f10`
- `0x140005468`
- `0x14000e3c4`
- `0x14000fa08`
- `0x140034d9c`
- `0x14003902c`
- `0x14003faf8`
- `0x140040fc8`
- `0x140041ef4`
- `0x140042084`
- `0x140042c60`
- `0x140042ed0`
- `0x14005b770`
- `0x14005b7e8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400413c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004149d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400413c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004149d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140041172`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140041172`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140041265`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140041265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041a52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041b0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041a52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041b0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041ba2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400410d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041304`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400410d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140041304`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140041379`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140041379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400411b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400415b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004179e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400411b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400415b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004179e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041976`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400417f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400417f5`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140041501`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140041501`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x140041b75`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x140041b75`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x140041909`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x140041909`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140041859`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140041957`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140041859`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140041957`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140041829`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x140041829`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14004109e`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14004109e`

## string_xrefs

- `0x1400410ea`: `RegOpenKeyEx failed`
- `0x1400411fa`: `RegOpenKeyEx failed`
- `0x140041969`: `RegOpenKeyEx failed`
- `0x1400410ff`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140041198`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140041201`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140041b59`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140041416`: `GenerateDriverPath failed`
- `0x140041adf`: `WriteDriverRecord failed`
- `0x1400413b9`: `ImagePath`
- `0x1400410cb`: `System\CurrentControlSet\Services`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKernelReportDataCollection::GetDriverInformationFromRegistry(
        CKernelReportDataCollection *this,
        void *a2,
        int (__high *a3)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))
{
  int (__high *v3)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // rbx
  CKernelReportDataCollection *v4; // r14
  WCHAR *v5; // r12
  HKEY *v6; // rax
  signed int LastError; // eax
  const struct std::nothrow_t *v8; // rdx
  signed int v9; // ebx
  WCHAR **unique_for; // rax
  const struct std::nothrow_t *v11; // rdx
  unsigned int v12; // r8d
  DWORD v13; // edi
  LSTATUS v14; // eax
  HKEY *v15; // rax
  LSTATUS ValueW; // eax
  __int64 v17; // rcx
  int DriverPath; // eax
  CKernelReportDataCollection *v19; // rcx
  int SubmissionId; // eax
  unsigned __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  WCHAR *v24; // r8
  __int64 v25; // rdx
  WCHAR *v26; // rax
  WCHAR v27; // r9
  WCHAR *v28; // rcx
  char *FileW; // rax
  void *v30; // r14
  HCATINFO v31; // rbx
  int v32; // edi
  CATALOG_INFO *p_psCatInfo; // rax
  _OWORD *v34; // rcx
  __int64 v35; // rdx
  CKernelReportDataCollection *v36; // rcx
  unsigned int v37; // ebx
  void *v38; // rcx
  __int64 v39; // rax
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulta; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultb; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultc; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultd; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulte; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultf; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultg; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulth; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulti; // [rsp+20h] [rbp-E0h]
  int lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLena; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLenb; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLenc; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLend; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLene; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLenf; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLeng; // [rsp+30h] [rbp-D0h]
  const char *lpcbMaxClassLenh; // [rsp+30h] [rbp-D0h]
  LPDWORD lpcbMaxValueNameLen; // [rsp+40h] [rbp-C0h]
  int v62; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v65; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbHash; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD i; // [rsp+80h] [rbp-80h]
  HCATADMIN phCatAdmin; // [rsp+88h] [rbp-78h] BYREF
  void *v70; // [rsp+90h] [rbp-70h] BYREF
  _WORD *v71; // [rsp+98h] [rbp-68h]
  _WORD v72[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v73; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v74; // [rsp+B8h] [rbp-48h]
  _WORD v75[8]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cchName; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+D4h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+D8h] [rbp-28h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+E0h] [rbp-20h] BYREF
  CKernelReportDataCollection *v80; // [rsp+E8h] [rbp-18h]
  __int64 v81; // [rsp+F0h] [rbp-10h] BYREF
  int (__high *v82)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // [rsp+F8h] [rbp-8h]
  LPCWSTR lpFileName[2]; // [rsp+100h] [rbp+0h] BYREF
  _WORD v84[8]; // [rsp+110h] [rbp+10h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+120h] [rbp+20h] BYREF
  void *v86; // [rsp+128h] [rbp+28h]
  _QWORD v87[2]; // [rsp+130h] [rbp+30h] BYREF
  const wchar_t *v88; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v89[5]; // [rsp+148h] [rbp+48h]
  char v90[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE Src[1568]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v92; // [rsp+7A0h] [rbp+6A0h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+7B0h] [rbp+6B0h] BYREF
  struct _SP_INF_SIGNER_INFO_V2_W InfSignerInfo; // [rsp+9C0h] [rbp+8C0h] BYREF
  BYTE pbHash[112]; // [rsp+FE0h] [rbp+EE0h] BYREF
  _WORD v96[128]; // [rsp+1050h] [rbp+F50h] BYREF
  wchar_t v97[128]; // [rsp+1150h] [rbp+1050h] BYREF
  WCHAR InfName[264]; // [rsp+1250h] [rbp+1150h] BYREF
  _WORD pvData[264]; // [rsp+1460h] [rbp+1360h] BYREF
  _WORD v100[264]; // [rsp+1670h] [rbp+1570h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+18C8h] [rbp+17C8h]

  v3 = a3;
  v82 = a3;
  v86 = a2;
  v4 = this;
  v80 = this;
  ftLastWriteTime = 0;
  v5 = 0;
  cbMaxSubKeyLen = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  cchName = 0;
  hKey = 0;
  lpFileName[0] = v84;
  lpFileName[1] = v84;
  v84[0] = 0;
  v81 = 0;
  v92 = 0;
  memset_0(&InfSignerInfo, 0, sizeof(InfSignerInfo));
  v62 = 0;
  v65 = 0;
  pcbHash = 100;
  phCatAdmin = 0;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  phPrevCatInfo = 0;
  if ( !CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
    phCatAdmin = 0;
  pvData[0] = 0;
  v6 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0, 0x20019u, v6) )
  {
    LODWORD(phkResult) = -2147467259;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x495,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
      "CKernelReportDataCollection::GetDriverInformationFromRegistry",
      phkResult,
      (int)"RegOpenKeyEx failed",
      lpcbMaxClassLen);
    LastError = GetLastError();
LABEL_5:
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    goto LABEL_104;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    LODWORD(phkResulta) = -2147467259;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x4A8,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
      "CKernelReportDataCollection::GetDriverInformationFromRegistry",
      phkResulta,
      (int)"RegQueryInfoKey failed",
      lpcbMaxClassLena);
    LastError = GetLastError();
    goto LABEL_5;
  }
  unique_for = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(&hkey, ++cbMaxSubKeyLen);
  v5 = *unique_for;
  *unique_for = 0;
  v89[3] = v5;
  if ( hkey )
    operator delete(hkey, v11);
  if ( !v5 )
  {
    v9 = -2147024882;
    LODWORD(phkResulta) = -2147024882;
    wil::details::in1diag4::Log_Hr(
      retaddr,
      (void *)0x4B8,
      v12,
      "CKernelReportDataCollection::GetDriverInformationFromRegistry",
      phkResulta,
      lpcbMaxSubKeyLen);
    goto LABEL_104;
  }
  v13 = 0;
  for ( i = 0; ; i = v13 )
  {
    v73 = v75;
    v74 = v75;
    v75[0] = 0;
    v70 = v72;
    v71 = v72;
    v72[0] = 0;
    cchName = cbMaxSubKeyLen;
    v14 = RegEnumKeyExW(hKey, v13, v5, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v14 )
    {
      if ( v14 == 259 )
      {
        if ( v70 != v72 )
          operator delete(v70, (const struct std::nothrow_t *)&std::nothrow);
        if ( v73 != v75 )
          operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
        v9 = 0;
        goto LABEL_104;
      }
      LODWORD(phkResultb) = v14;
      wil::details::in1diag4::Log_Win32Msg(
        retaddr,
        (void *)0x4D7,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetDriverInformationFromRegistry",
        phkResultb,
        (unsigned int)"RegEnumKeyEx failed",
        lpcbMaxClassLenb);
      goto LABEL_19;
    }
    hkey = 0;
    v15 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    if ( RegOpenKeyExW(hKey, v5, 0, 0x20019u, v15) )
    {
      LODWORD(phkResultc) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x4DF,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetDriverInformationFromRegistry",
        phkResultc,
        (int)"RegOpenKeyEx failed",
        lpcbMaxClassLenb);
LABEL_25:
      if ( hkey )
        RegCloseKey(hkey);
LABEL_19:
      if ( v70 != v72 )
        operator delete(v70, (const struct std::nothrow_t *)&std::nothrow);
      if ( v73 != v75 )
        operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_91;
    }
    cbData = 4;
    if ( RegQueryValueExW(hkey, L"Type", 0, 0, Data, &cbData) || (Data[0] & 0xB) == 0 )
      goto LABEL_25;
    cbData = 520;
    pvData[0] = 0;
    ValueW = RegGetValueW(hkey, 0, L"ImagePath", 2u, 0, pvData, &cbData);
    v17 = 0;
    if ( ValueW )
    {
      pvData[0] = 0;
      LODWORD(phkResultd) = ValueW;
      wil::details::in1diag4::Log_Win32Msg(
        retaddr,
        (void *)0x50B,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetDriverInformationFromRegistry",
        phkResultd,
        (unsigned int)"RegQueryValueEx failed",
        lpcbMaxClassLenc);
    }
    DriverPath = CKernelReportDataCollection::GenerateDriverPath(v17, v5, pvData, lpFileName);
    if ( DriverPath < 0 )
    {
      LODWORD(phkResultd) = DriverPath;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x512,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
        "CKernelReportDataCollection::GetDriverInformationFromRegistry",
        phkResultd,
        (int)"GenerateDriverPath failed",
        lpcbMaxClassLenc);
      goto LABEL_25;
    }
    if ( !UtilFileExists(lpFileName[0]) )
      goto LABEL_25;
    v92 = 0;
    v97[0] = 0;
    v96[0] = 0;
    v100[0] = 0;
    cbData = 520;
    InfName[0] = 0;
    if ( RegGetValueW(hkey, 0, L"Owners", 0x20u, 0, InfName, &cbData) )
    {
      FileW = (char *)CreateFileW(lpFileName[0], 0x80000000, 3u, 0, 3u, 0x80u, 0);
      v30 = FileW;
      v19 = (CKernelReportDataCollection *)(FileW + 1);
      if ( (unsigned __int64)(FileW + 1) > 1 )
      {
        if ( phCatAdmin && CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, pbHash, 0) )
        {
          phPrevCatInfo = 0;
          v31 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, &phPrevCatInfo);
          v32 = 0;
          while ( v31 )
          {
            if ( v32 )
              break;
            memset_0(Src, 0, 0x20Cu);
            p_psCatInfo = &psCatInfo;
            v34 = Src;
            v35 = 4;
            do
            {
              *(_OWORD *)&p_psCatInfo->cbStruct = *v34;
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[6] = v34[1];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[14] = v34[2];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[22] = v34[3];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[30] = v34[4];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[38] = v34[5];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[46] = v34[6];
              *(_OWORD *)&p_psCatInfo->wszCatalogFile[54] = v34[7];
              p_psCatInfo = (CATALOG_INFO *)((char *)p_psCatInfo + 128);
              v34 += 8;
              --v35;
            }
            while ( v35 );
            *(_OWORD *)&p_psCatInfo[-1].wszCatalogFile[258] = *(_OWORD *)((char *)v34 - 4);
            psCatInfo.cbStruct = 524;
            if ( CryptCATCatalogInfoFromContext(v31, &psCatInfo, 0)
              && CKernelReportDataCollection::GetSubmissionId(v36, psCatInfo.wszCatalogFile, v97, 0x80u) >= 0 )
            {
              v32 = 1;
            }
            else
            {
              phPrevCatInfo = v31;
              v31 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, &phPrevCatInfo);
            }
          }
          v13 = i;
        }
        CloseHandle(v30);
      }
      v4 = v80;
    }
    else
    {
      if ( (unsigned __int8)IsSetupVerifyInfFileWPresent(0) )
      {
        memset_0(Src, 0, sizeof(Src));
        memcpy_0(&InfSignerInfo, Src, sizeof(InfSignerInfo));
        InfSignerInfo.cbSize = 1568;
        if ( SetupVerifyInfFileW(InfName, 0, &InfSignerInfo) )
        {
          SubmissionId = CKernelReportDataCollection::GetSubmissionId(v19, InfSignerInfo.CatalogFile, v97, 0x80u);
          if ( SubmissionId < 0 )
          {
            LODWORD(phkResulte) = SubmissionId;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x549,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
              "CKernelReportDataCollection::GetDriverInformationFromRegistry",
              phkResulte,
              (int)"GetSubmissionId failed",
              lpcbMaxClassLend);
          }
        }
      }
      if ( v3 )
      {
        LODWORD(lpcbMaxValueNameLen) = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, __int128 *, int, unsigned int *, LPDWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_ClassGuid,
                &v62,
                &v92,
                16,
                &v65,
                lpcbMaxValueNameLen)
          || v62 != 13 )
        {
          LODWORD(phkResultf) = GetLastError();
          wil::details::in1diag4::Log_Win32Msg(
            retaddr,
            (void *)0x55F,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
            "CKernelReportDataCollection::GetDriverInformationFromRegistry",
            phkResultf,
            (unsigned int)"DriverStoreGetObjectProperty for DEVPKEY_DriverPackage_ClassGuid failed",
            lpcbMaxClassLene);
        }
        if ( ((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, _WORD *, int, unsigned int *, _DWORD))v3)(
               0,
               2,
               InfName,
               DEVPKEY_DriverPackage_DriverFlightIds,
               &v62,
               v96,
               128,
               &v65,
               0)
          && v62 == 8210 )
        {
          v21 = ((unsigned __int64)v65 >> 1) - 2;
          v22 = 0;
          if ( (unsigned __int64)v65 >> 1 != 2 )
          {
            do
            {
              if ( !v96[v22] )
                v96[v22] = 59;
              ++v22;
            }
            while ( v22 < v21 );
          }
        }
        else
        {
          LODWORD(phkResultg) = GetLastError();
          wil::details::in1diag4::Log_Win32Msg(
            retaddr,
            (void *)0x576,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
            "CKernelReportDataCollection::GetDriverInformationFromRegistry",
            phkResultg,
            (unsigned int)"DriverStoreGetObjectProperty for DEVPKEY_DriverPackage_DriverFlightIds failed",
            lpcbMaxClassLenf);
        }
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, _WORD *, int, unsigned int *, _DWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_OriginalInfName,
                &v62,
                v100,
                260,
                &v65,
                0)
          || v62 != 18 )
        {
          v23 = 2147483646;
          v24 = InfName;
          v25 = 260;
          v26 = v100;
          do
          {
            if ( !v23 )
              break;
            v27 = *v24;
            if ( !*v24 )
              break;
            ++v24;
            *v26++ = v27;
            --v23;
            --v25;
          }
          while ( v25 );
          v28 = v26 - 1;
          if ( v25 )
            v28 = v26;
          *v28 = 0;
        }
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, __int64 *, int, unsigned int *, _DWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_DriverDate,
                &v62,
                &v81,
                8,
                &v65,
                0)
          || v62 != 16 )
        {
          LODWORD(phkResulth) = GetLastError();
          wil::details::in1diag4::Log_Win32Msg(
            retaddr,
            (void *)0x594,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
            "CKernelReportDataCollection::GetDriverInformationFromRegistry",
            phkResulth,
            (unsigned int)"DriverStoreGetObjectProperty for DEVPKEY_DriverPackage_DriverDate failed",
            lpcbMaxClassLeng);
        }
      }
    }
    v37 = 0;
    if ( (int)CKernelReportDataCollection::GetFilterDriverInformation(v19, hkey, &v73, &v70) >= 0 )
    {
      if ( v73 != v74 )
      {
        v88 = L"GROUP";
        v89[0] = v73;
        v37 = 1;
      }
      v38 = v70;
      if ( v70 != v71 )
      {
        v39 = 2LL * v37;
        v89[v39 - 1] = L"ALTITUDE";
        v89[v39] = v38;
        ++v37;
      }
    }
    *(_OWORD *)v90 = v92;
    v87[0] = &v88;
    v87[1] = v37;
    v9 = CKernelReportDataCollection::WriteDriverRecord(v4, v86, lpFileName[0], v87, v97, v96, v90, v100, &v81);
    if ( v9 < 0 )
      break;
    if ( hkey )
      RegCloseKey(hkey);
    if ( v70 != v72 )
      operator delete(v70, (const struct std::nothrow_t *)&std::nothrow);
    if ( v73 != v75 )
      operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v82;
LABEL_91:
    ++v13;
  }
  LODWORD(phkResulti) = v9;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x5F8,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::GetDriverInformationFromRegistry",
    phkResulti,
    (int)"WriteDriverRecord failed",
    lpcbMaxClassLenh);
  if ( hkey )
    RegCloseKey(hkey);
  if ( v70 != v72 )
    operator delete(v70, (const struct std::nothrow_t *)&std::nothrow);
  if ( v73 != v75 )
    operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
LABEL_104:
  if ( phCatAdmin )
  {
    CryptCATAdminReleaseContext(phCatAdmin, 0);
    phCatAdmin = 0;
  }
  if ( lpFileName[0] != v84 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    operator delete(v5, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140040fc8  mov     [rsp-8+arg_18], rbx
0x140040fcd  push    rbp
0x140040fce  push    rsi
0x140040fcf  push    rdi
0x140040fd0  push    r12
0x140040fd2  push    r13
0x140040fd4  push    r14
0x140040fd6  push    r15
0x140040fd8  lea     rbp, [rsp-1790h]
0x140040fe0  mov     eax, 1890h
0x140040fe5  call    _alloca_probe
0x140040fea  sub     rsp, rax
0x140040fed  mov     rax, cs:__security_cookie
0x140040ff4  xor     rax, rsp
0x140040ff7  mov     [rbp+17C0h+var_40], rax
0x140040ffe  mov     rbx, r8
0x140041001  mov     [rbp+17C0h+var_17C8], rbx
0x140041005  mov     [rbp+17C0h+var_1798], rdx
0x140041009  mov     r14, rcx
0x14004100c  mov     [rbp+17C0h+var_17D8], rcx
0x140041010  xor     r13d, r13d
0x140041013  mov     qword ptr [rbp+17C0h+ftLastWriteTime.dwLowDateTime], r13
0x140041017  mov     r12d, r13d
0x14004101a  mov     [rsp+18C0h+cbMaxSubKeyLen], r13d
0x14004101f  mov     dword ptr [rbp+17C0h+Data], r13d
0x140041023  mov     [rsp+18C0h+cbData], r13d
0x140041028  mov     [rbp+17C0h+cchName], r13d
0x14004102c  mov     [rbp+17C0h+hKey], r13
0x140041030  lea     rax, [rbp+17C0h+var_17B0]
0x140041034  mov     [rbp+17C0h+lpFileName], rax
0x140041038  lea     rax, [rbp+17C0h+var_17B0]
0x14004103c  mov     [rbp+17C0h+var_17B8], rax
0x140041040  mov     [rbp+17C0h+var_17B0], r13w
0x140041045  mov     [rbp+17C0h+var_17D0], r13
0x140041049  xorps   xmm0, xmm0
0x14004104c  movups  [rbp+17C0h+var_1120], xmm0
0x140041053  xor     edx, edx; Val
0x140041055  mov     r8d, 620h; Size
0x14004105b  lea     rcx, [rbp+17C0h+InfSignerInfo]; void *
0x140041062  call    memset_0
0x140041067  mov     [rsp+18C0h+var_1860], r13d
0x14004106c  mov     [rsp+18C0h+var_184C], r13d
0x140041071  mov     [rsp+18C0h+pcbHash], 64h ; 'd'
0x140041079  mov     [rbp+17C0h+phCatAdmin], r13
0x14004107d  xor     edx, edx; Val
0x14004107f  mov     r8d, 20Ch; Size
0x140041085  lea     rcx, [rbp+17C0h+psCatInfo]; void *
0x14004108c  call    memset_0
0x140041091  mov     [rbp+17C0h+phPrevCatInfo], r13
0x140041095  xor     r8d, r8d; dwFlags
0x140041098  xor     edx, edx; pgSubsystem
0x14004109a  lea     rcx, [rbp+17C0h+phCatAdmin]; phCatAdmin
0x14004109e  call    cs:__imp_CryptCATAdminAcquireContext
0x1400410a4  test    eax, eax
0x1400410a6  jnz     short loc_1400410AC
0x1400410a8  mov     [rbp+17C0h+phCatAdmin], r13
0x1400410ac  mov     [rbp+17C0h+pvData], r13w
0x1400410b4  lea     rcx, [rbp+17C0h+hKey]
0x1400410b8  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400410bd  mov     [rsp+18C0h+phkResult], rax; phkResult
0x1400410c2  mov     r9d, 20019h; samDesired
0x1400410c8  xor     r8d, r8d; ulOptions
0x1400410cb  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services"
0x1400410d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400410d9  call    cs:__imp_RegOpenKeyExW
0x1400410df  test    eax, eax
0x1400410e1  jz      short loc_140041139
0x1400410e3  mov     rcx, [rbp+17C8h]; this
0x1400410ea  lea     r13, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x1400410f1  mov     [rsp+18C0h+lpcbMaxSubKeyLen], r13; int
0x1400410f6  mov     edi, 80004005h
0x1400410fb  mov     dword ptr [rsp+18C0h+phkResult], edi; wil::details *
0x1400410ff  lea     r9, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x140041106  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x14004110d  mov     edx, 495h; void *
0x140041112  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041117  call    cs:__imp_GetLastError
0x14004111d  xor     r13d, r13d
0x140041120  mov     ebx, eax
0x140041122  test    eax, eax
0x140041124  jle     short loc_14004112F
0x140041126  movzx   ebx, ax
0x140041129  or      ebx, 80070000h
0x14004112f  test    ebx, ebx
0x140041131  cmovns  ebx, edi
0x140041134  jmp     loc_140041B6A
0x140041139  mov     [rsp+18C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x14004113e  mov     [rsp+18C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140041143  mov     [rsp+18C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140041148  mov     [rsp+18C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x14004114d  mov     [rsp+18C0h+lpcValues], r13; lpcValues
0x140041152  mov     [rsp+18C0h+lpcbMaxClassLen], r13; char *
0x140041157  lea     rax, [rsp+18C0h+cbMaxSubKeyLen]
0x14004115c  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; int
0x140041161  mov     [rsp+18C0h+phkResult], r13; lpcSubKeys
0x140041166  xor     r9d, r9d; lpReserved
0x140041169  xor     r8d, r8d; lpcchClass
0x14004116c  xor     edx, edx; lpClass
0x14004116e  mov     rcx, [rbp+17C0h+hKey]; hKey
0x140041172  call    cs:__imp_RegQueryInfoKeyW
0x140041178  test    eax, eax
0x14004117a  jz      short loc_1400411BB
0x14004117c  mov     rcx, [rbp+17C8h]; this
0x140041183  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x14004118a  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; int
0x14004118f  mov     edi, 80004005h
0x140041194  mov     dword ptr [rsp+18C0h+phkResult], edi; wil::details *
0x140041198  lea     r9, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x14004119f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400411a6  mov     edx, 4A8h; void *
0x1400411ab  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400411b0  call    cs:__imp_GetLastError
0x1400411b6  jmp     loc_140041120
0x1400411bb  mov     eax, [rsp+18C0h+cbMaxSubKeyLen]
0x1400411bf  inc     eax
0x1400411c1  mov     [rsp+18C0h+cbMaxSubKeyLen], eax
0x1400411c5  mov     edx, eax
0x1400411c7  lea     rcx, [rsp+18C0h+hkey]
0x1400411cc  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1400411d1  mov     r12, [rax]
0x1400411d4  mov     [rax], r13
0x1400411d7  mov     [rbp+17C0h+var_1760], r12
0x1400411db  mov     rcx, [rsp+18C0h+hkey]; void *
0x1400411e0  test    rcx, rcx
0x1400411e3  jz      short loc_1400411EA
0x1400411e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400411ea  test    r12, r12
0x1400411ed  jz      loc_140041B49
0x1400411f3  mov     edi, r13d
0x1400411f6  mov     [rbp+17C0h+var_1840], r13d
0x1400411fa  lea     r13, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x140041201  lea     rsi, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x140041208  lea     r15, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x14004120f  lea     rax, [rbp+17C0h+var_1800]
0x140041213  mov     [rbp+17C0h+var_1810], rax
0x140041217  lea     rax, [rbp+17C0h+var_1800]
0x14004121b  mov     [rbp+17C0h+var_1808], rax
0x14004121f  xor     ecx, ecx
0x140041221  mov     [rbp+17C0h+var_1800], cx
0x140041225  lea     rax, [rbp+17C0h+var_1820]
0x140041229  mov     [rbp+17C0h+var_1830], rax
0x14004122d  lea     rax, [rbp+17C0h+var_1820]
0x140041231  mov     [rbp+17C0h+var_1828], rax
0x140041235  mov     [rbp+17C0h+var_1820], cx
0x140041239  mov     eax, [rsp+18C0h+cbMaxSubKeyLen]
0x14004123d  mov     [rbp+17C0h+cchName], eax
0x140041240  lea     rax, [rbp+17C0h+ftLastWriteTime]
0x140041244  mov     [rsp+18C0h+lpcValues], rax; lpftLastWriteTime
0x140041249  mov     [rsp+18C0h+lpcbMaxClassLen], rcx; char *
0x14004124e  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rcx; lpClass
0x140041253  mov     [rsp+18C0h+phkResult], rcx; lpReserved
0x140041258  lea     r9, [rbp+17C0h+cchName]; lpcchName
0x14004125c  mov     r8, r12; lpName
0x14004125f  mov     edx, edi; dwIndex
0x140041261  mov     rcx, [rbp+17C0h+hKey]; hKey
0x140041265  call    cs:__imp_RegEnumKeyExW
0x14004126b  xor     ecx, ecx
0x14004126d  test    eax, eax
0x14004126f  jz      short loc_1400412E0
0x140041271  cmp     eax, 103h
0x140041276  jz      loc_140041A9A
0x14004127c  mov     rcx, [rbp+17C8h]; this
0x140041283  lea     rdx, aRegenumkeyexFa; "RegEnumKeyEx failed"
0x14004128a  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14004128f  mov     dword ptr [rsp+18C0h+phkResult], eax; wil::details *
0x140041293  mov     r9, rsi; char *
0x140041296  mov     r8, r15; unsigned int
0x140041299  mov     edx, 4D7h; void *
0x14004129e  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x1400412a3  nop
0x1400412a4  lea     rax, [rbp+17C0h+var_1820]
0x1400412a8  mov     rcx, [rbp+17C0h+var_1830]; void *
0x1400412ac  cmp     rcx, rax
0x1400412af  jz      short loc_1400412BE
0x1400412b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400412b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400412bd  nop
0x1400412be  lea     rax, [rbp+17C0h+var_1800]
0x1400412c2  mov     rcx, [rbp+17C0h+var_1810]; void *
0x1400412c6  cmp     rcx, rax
0x1400412c9  jz      loc_140041A90
0x1400412cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400412d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400412db  jmp     loc_140041A90
0x1400412e0  mov     [rsp+18C0h+hkey], rcx
0x1400412e5  lea     rcx, [rsp+18C0h+hkey]
0x1400412ea  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400412ef  mov     [rsp+18C0h+phkResult], rax; phkResult
0x1400412f4  mov     r9d, 20019h; samDesired
0x1400412fa  xor     r8d, r8d; ulOptions
0x1400412fd  mov     rdx, r12; lpSubKey
0x140041300  mov     rcx, [rbp+17C0h+hKey]; hKey
0x140041304  call    cs:__imp_RegOpenKeyExW
0x14004130a  test    eax, eax
0x14004130c  jz      short loc_14004134C
0x14004130e  mov     [rsp+18C0h+lpcbMaxSubKeyLen], r13; int
0x140041313  mov     dword ptr [rsp+18C0h+phkResult], 80000000h; wil::details *
0x14004131b  mov     edx, 4DFh; void *
0x140041320  mov     r9, rsi; char *
0x140041323  mov     r8, r15; unsigned int
0x140041326  mov     rcx, [rbp+17C8h]; this
0x14004132d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041332  nop
0x140041333  mov     rcx, [rsp+18C0h+hkey]; hKey
0x140041338  test    rcx, rcx
0x14004133b  jz      loc_1400412A4
0x140041341  call    cs:__imp_RegCloseKey
0x140041347  jmp     loc_1400412A4
0x14004134c  mov     [rsp+18C0h+cbData], 4
0x140041354  lea     rax, [rsp+18C0h+cbData]
0x140041359  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x14004135e  lea     rax, [rbp+17C0h+Data]
0x140041362  mov     [rsp+18C0h+phkResult], rax; lpData
0x140041367  xor     r9d, r9d; lpType
0x14004136a  xor     r8d, r8d; lpReserved
0x14004136d  lea     rdx, aType_0; "Type"
0x140041374  mov     rcx, [rsp+18C0h+hkey]; hKey
0x140041379  call    cs:__imp_RegQueryValueExW
0x14004137f  xor     edx, edx; lpSubKey
0x140041381  test    eax, eax
0x140041383  jnz     short loc_140041333
0x140041385  test    [rbp+17C0h+Data], 0Bh
0x140041389  jz      short loc_140041333
0x14004138b  mov     [rsp+18C0h+cbData], 208h
0x140041393  mov     [rbp+17C0h+pvData], dx
0x14004139a  lea     rax, [rsp+18C0h+cbData]
0x14004139f  mov     [rsp+18C0h+lpcbMaxClassLen], rax; char *
0x1400413a4  lea     rax, [rbp+17C0h+pvData]
0x1400413ab  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; pvData
0x1400413b0  mov     [rsp+18C0h+phkResult], rdx; pdwType
0x1400413b5  lea     r9d, [rdx+2]; dwFlags
0x1400413b9  lea     r8, aImagepath; "ImagePath"
0x1400413c0  mov     rcx, [rsp+18C0h+hkey]; hkey
0x1400413c5  call    cs:__imp_RegGetValueW
0x1400413cb  xor     ecx, ecx
0x1400413cd  test    eax, eax
0x1400413cf  jz      short loc_1400413FF
0x1400413d1  mov     [rbp+17C0h+pvData], cx
0x1400413d8  mov     rcx, [rbp+17C8h]; this
0x1400413df  lea     rdx, aRegqueryvaluee; "RegQueryValueEx failed"
0x1400413e6  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x1400413eb  mov     dword ptr [rsp+18C0h+phkResult], eax; wil::details *
0x1400413ef  mov     r9, rsi; char *
0x1400413f2  mov     r8, r15; unsigned int
0x1400413f5  mov     edx, 50Bh; void *
0x1400413fa  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x1400413ff  lea     r9, [rbp+17C0h+lpFileName]
0x140041403  lea     r8, [rbp+17C0h+pvData]
0x14004140a  mov     rdx, r12
0x14004140d  call    ?GenerateDriverPath@CKernelReportDataCollection@@AEAAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReportDataCollection::GenerateDriverPath(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140041412  test    eax, eax
0x140041414  jns     short loc_140041430
0x140041416  lea     rdx, aGeneratedriver; "GenerateDriverPath failed"
0x14004141d  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx
0x140041422  mov     dword ptr [rsp+18C0h+phkResult], eax
0x140041426  mov     edx, 512h
0x14004142b  jmp     loc_140041320
0x140041430  mov     rcx, [rbp+17C0h+lpFileName]; wchar_t *
0x140041434  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140041439  xor     edx, edx; lpSubKey
0x14004143b  test    al, al
0x14004143d  jz      loc_140041333
0x140041443  xorps   xmm0, xmm0
0x140041446  movdqa  [rbp+17C0h+var_1120], xmm0
0x14004144e  mov     [rbp+17C0h+var_770], dx
0x140041455  mov     [rbp+17C0h+var_870], dx
0x14004145c  mov     [rbp+17C0h+var_250], dx
0x140041463  mov     [rsp+18C0h+cbData], 208h
0x14004146b  mov     [rbp+17C0h+InfName], dx
0x140041472  lea     rax, [rsp+18C0h+cbData]
0x140041477  mov     [rsp+18C0h+lpcbMaxClassLen], rax; char *
0x14004147c  lea     rax, [rbp+17C0h+InfName]
0x140041483  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; pvData
0x140041488  mov     [rsp+18C0h+phkResult], rdx; pdwType
0x14004148d  lea     r9d, [rdx+20h]; dwFlags
0x140041491  lea     r8, aOwners; "Owners"
0x140041498  mov     rcx, [rsp+18C0h+hkey]; hkey
0x14004149d  call    cs:__imp_RegGetValueW
0x1400414a3  xor     ecx, ecx
0x1400414a5  test    eax, eax
0x1400414a7  jnz     loc_1400417D0
0x1400414ad  call    IsSetupVerifyInfFileWPresent
0x1400414b2  test    al, al
0x1400414b4  jz      loc_14004154F
0x1400414ba  xor     edx, edx; Val
0x1400414bc  mov     r8d, 620h; Size
0x1400414c2  lea     rcx, [rbp+17C0h+Src]; void *
0x1400414c9  call    memset_0
0x1400414ce  lea     rcx, [rbp+17C0h+InfSignerInfo]; void *
0x1400414d5  lea     rdx, [rbp+17C0h+Src]; Src
0x1400414dc  mov     r8d, 620h; Size
0x1400414e2  call    memcpy_0
0x1400414e7  mov     [rbp+17C0h+InfSignerInfo.cbSize], 620h
0x1400414f1  lea     r8, [rbp+17C0h+InfSignerInfo]; InfSignerInfo
0x1400414f8  xor     edx, edx; AltPlatformInfo
0x1400414fa  lea     rcx, [rbp+17C0h+InfName]; InfName
0x140041501  call    cs:__imp_SetupVerifyInfFileW
0x140041507  test    eax, eax
0x140041509  jz      short loc_14004154F
0x14004150b  mov     r9d, 80h; unsigned int
  ... truncated ...
```
