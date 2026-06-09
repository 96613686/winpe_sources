# CKernelReportDataCollection::GetDriverInformationFromRegistry(void *,int (*)(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,wchar_t const *,_DEVPROPKEY const *,ulong *,uchar *,ulong,ulong *,ulong))

- ea: `0x140043cbc`
- end: `0x14004496d`
- name: `?GetDriverInformationFromRegistry@CKernelReportDataCollection@@AEAAJPEAXP6AHPEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEB_WPEBU_DEVPROPKEY@@PEAKPEAEK5K@Z@Z`
- size: `3249`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *__hidden this, void *, int (__high *)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x140043bd8`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x140003f60`
- `0x14000551c`
- `0x14000e658`
- `0x140010034`
- `0x1400372dc`
- `0x14003b56c`
- `0x140042670`
- `0x140043cbc`
- `0x140044cd0`
- `0x140044e6c`
- `0x140045b18`
- `0x140045d88`
- `0x14005f510`
- `0x14005f588`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400440ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400441cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400440ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400441cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140043e78`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140043e78`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140043f77`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140043f77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004405f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400447c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044885`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044926`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004405f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400447c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044885`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044926`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043dd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004401c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140043dd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004401c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004409d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004409d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400442ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400444e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400442ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400444e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400446e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400446e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044543`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044543`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140044237`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140044237`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400448f3`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1400448f3`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x140044669`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x140044669`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1400445b3`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1400446bd`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1400445b3`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1400446bd`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x14004457d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x14004457d`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140043d92`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140043d92`

## string_xrefs

- `0x140043dea`: `RegOpenKeyEx failed`
- `0x140043f0c`: `RegOpenKeyEx failed`
- `0x1400446d5`: `RegOpenKeyEx failed`
- `0x140043dff`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140043ea4`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140043f13`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x1400448d7`: `CKernelReportDataCollection::GetDriverInformationFromRegistry`
- `0x140044146`: `GenerateDriverPath failed`
- `0x140044857`: `WriteDriverRecord failed`
- `0x1400440e3`: `ImagePath`
- `0x140043dc5`: `System\CurrentControlSet\Services`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v9; // ebx
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
  wchar_t *v26; // rax
  WCHAR v27; // r9
  wchar_t *v28; // rcx
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
  int v61; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v64; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbHash; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD i; // [rsp+80h] [rbp-80h]
  HCATADMIN phCatAdmin; // [rsp+88h] [rbp-78h] BYREF
  void *v69; // [rsp+90h] [rbp-70h] BYREF
  _WORD *v70; // [rsp+98h] [rbp-68h]
  _WORD v71[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v72; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v73; // [rsp+B8h] [rbp-48h]
  _WORD v74[8]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cchName; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+D4h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+D8h] [rbp-28h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+E0h] [rbp-20h] BYREF
  CKernelReportDataCollection *v79; // [rsp+E8h] [rbp-18h]
  FILETIME v80; // [rsp+F0h] [rbp-10h] BYREF
  int (__high *v81)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // [rsp+F8h] [rbp-8h]
  LPCWSTR lpFileName[2]; // [rsp+100h] [rbp+0h] BYREF
  _WORD v83[8]; // [rsp+110h] [rbp+10h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+120h] [rbp+20h] BYREF
  void *v85; // [rsp+128h] [rbp+28h]
  _QWORD v86[2]; // [rsp+130h] [rbp+30h] BYREF
  const wchar_t *v87; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v88[5]; // [rsp+148h] [rbp+48h]
  char v89[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE Src[1568]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v91; // [rsp+7A0h] [rbp+6A0h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+7B0h] [rbp+6B0h] BYREF
  struct _SP_INF_SIGNER_INFO_V2_W InfSignerInfo; // [rsp+9C0h] [rbp+8C0h] BYREF
  BYTE pbHash[112]; // [rsp+FE0h] [rbp+EE0h] BYREF
  wchar_t v95[128]; // [rsp+1050h] [rbp+F50h] BYREF
  wchar_t v96[128]; // [rsp+1150h] [rbp+1050h] BYREF
  WCHAR InfName[264]; // [rsp+1250h] [rbp+1150h] BYREF
  _WORD pvData[264]; // [rsp+1460h] [rbp+1360h] BYREF
  wchar_t v99[264]; // [rsp+1670h] [rbp+1570h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+18C8h] [rbp+17C8h]

  v3 = a3;
  v81 = a3;
  v85 = a2;
  v4 = this;
  v79 = this;
  ftLastWriteTime = 0;
  v5 = 0;
  cbMaxSubKeyLen = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  cchName = 0;
  hKey = 0;
  lpFileName[0] = v83;
  lpFileName[1] = v83;
  v83[0] = 0;
  v80 = 0;
  v91 = 0;
  memset_0(&InfSignerInfo, 0, sizeof(InfSignerInfo));
  v61 = 0;
  v64 = 0;
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
  v88[3] = v5;
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
    v72 = v74;
    v73 = v74;
    v74[0] = 0;
    v69 = v71;
    v70 = v71;
    v71[0] = 0;
    cchName = cbMaxSubKeyLen;
    v14 = RegEnumKeyExW(hKey, v13, v5, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v14 )
    {
      if ( v14 == 259 )
      {
        if ( v69 != v71 )
          operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
        if ( v72 != v74 )
          operator delete(v72, (const struct std::nothrow_t *)&std::nothrow);
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
      if ( v69 != v71 )
        operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
      if ( v72 != v74 )
        operator delete(v72, (const struct std::nothrow_t *)&std::nothrow);
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
    v91 = 0;
    v96[0] = 0;
    v95[0] = 0;
    v99[0] = 0;
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
              && CKernelReportDataCollection::GetSubmissionId(v36, psCatInfo.wszCatalogFile, v96, 0x80u) >= 0 )
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
      v4 = v79;
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
          SubmissionId = CKernelReportDataCollection::GetSubmissionId(v19, InfSignerInfo.CatalogFile, v96, 0x80u);
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
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, __int128 *, int, unsigned int *, _DWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_ClassGuid,
                &v61,
                &v91,
                16,
                &v64,
                0)
          || v61 != 13 )
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
        if ( ((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, wchar_t *, int, unsigned int *, _DWORD))v3)(
               0,
               2,
               InfName,
               DEVPKEY_DriverPackage_DriverFlightIds,
               &v61,
               v95,
               128,
               &v64,
               0)
          && v61 == 8210 )
        {
          v21 = ((unsigned __int64)v64 >> 1) - 2;
          v22 = 0;
          if ( (unsigned __int64)v64 >> 1 != 2 )
          {
            do
            {
              if ( !v95[v22] )
                v95[v22] = 59;
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
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, wchar_t *, int, unsigned int *, _DWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_OriginalInfName,
                &v61,
                v99,
                260,
                &v64,
                0)
          || v61 != 18 )
        {
          v23 = 2147483646;
          v24 = InfName;
          v25 = 260;
          v26 = v99;
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
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64, WCHAR *, __int64 *, int *, FILETIME *, int, unsigned int *, _DWORD))v3)(
                0,
                2,
                InfName,
                DEVPKEY_DriverPackage_DriverDate,
                &v61,
                &v80,
                8,
                &v64,
                0)
          || v61 != 16 )
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
    if ( (int)CKernelReportDataCollection::GetFilterDriverInformation(v19, hkey, &v72, &v69) >= 0 )
    {
      if ( v72 != v73 )
      {
        v87 = L"GROUP";
        v88[0] = v72;
        v37 = 1;
      }
      v38 = v69;
      if ( v69 != v70 )
      {
        v39 = 2LL * v37;
        v88[v39 - 1] = L"ALTITUDE";
        v88[v39] = v38;
        ++v37;
      }
    }
    *(_OWORD *)v89 = v91;
    v86[0] = &v87;
    v86[1] = v37;
    v9 = CKernelReportDataCollection::WriteDriverRecord(
           (__int64)v4,
           v85,
           (const char *)lpFileName[0],
           (__int64)v86,
           v96,
           v95,
           (__int64)v89,
           v99,
           &v80);
    if ( v9 < 0 )
      break;
    if ( hkey )
      RegCloseKey(hkey);
    if ( v69 != v71 )
      operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
    if ( v72 != v74 )
      operator delete(v72, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v81;
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
  if ( v69 != v71 )
    operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
  if ( v72 != v74 )
    operator delete(v72, (const struct std::nothrow_t *)&std::nothrow);
LABEL_104:
  if ( phCatAdmin )
  {
    CryptCATAdminReleaseContext(phCatAdmin, 0);
    phCatAdmin = 0;
  }
  if ( lpFileName[0] != v83 )
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
0x140043cbc  mov     [rsp-8+arg_18], rbx
0x140043cc1  push    rbp
0x140043cc2  push    rsi
0x140043cc3  push    rdi
0x140043cc4  push    r12
0x140043cc6  push    r13
0x140043cc8  push    r14
0x140043cca  push    r15
0x140043ccc  lea     rbp, [rsp-1790h]
0x140043cd4  mov     eax, 1890h
0x140043cd9  call    _alloca_probe
0x140043cde  sub     rsp, rax
0x140043ce1  mov     rax, cs:__security_cookie
0x140043ce8  xor     rax, rsp
0x140043ceb  mov     [rbp+17C0h+var_40], rax
0x140043cf2  mov     rbx, r8
0x140043cf5  mov     [rbp+17C0h+var_17C8], rbx
0x140043cf9  mov     [rbp+17C0h+var_1798], rdx
0x140043cfd  mov     r14, rcx
0x140043d00  mov     [rbp+17C0h+var_17D8], rcx
0x140043d04  xor     r13d, r13d
0x140043d07  mov     qword ptr [rbp+17C0h+ftLastWriteTime.dwLowDateTime], r13
0x140043d0b  mov     r12d, r13d
0x140043d0e  mov     [rsp+18C0h+cbMaxSubKeyLen], r13d
0x140043d13  mov     dword ptr [rbp+17C0h+Data], r13d
0x140043d17  mov     [rsp+18C0h+cbData], r13d
0x140043d1c  mov     [rbp+17C0h+cchName], r13d
0x140043d20  mov     [rbp+17C0h+hKey], r13
0x140043d24  lea     rax, [rbp+17C0h+var_17B0]
0x140043d28  mov     [rbp+17C0h+lpFileName], rax
0x140043d2c  lea     rax, [rbp+17C0h+var_17B0]
0x140043d30  mov     [rbp+17C0h+var_17B8], rax
0x140043d34  mov     [rbp+17C0h+var_17B0], r13w
0x140043d39  mov     [rbp+17C0h+var_17D0], r13
0x140043d3d  xorps   xmm0, xmm0
0x140043d40  movups  [rbp+17C0h+var_1120], xmm0
0x140043d47  xor     edx, edx; Val
0x140043d49  mov     r8d, 620h; Size
0x140043d4f  lea     rcx, [rbp+17C0h+InfSignerInfo]; void *
0x140043d56  call    memset_0
0x140043d5b  mov     [rsp+18C0h+var_1860], r13d
0x140043d60  mov     [rsp+18C0h+var_184C], r13d
0x140043d65  mov     [rsp+18C0h+pcbHash], 64h ; 'd'
0x140043d6d  mov     [rbp+17C0h+phCatAdmin], r13
0x140043d71  xor     edx, edx; Val
0x140043d73  mov     r8d, 20Ch; Size
0x140043d79  lea     rcx, [rbp+17C0h+psCatInfo]; void *
0x140043d80  call    memset_0
0x140043d85  mov     [rbp+17C0h+phPrevCatInfo], r13
0x140043d89  xor     r8d, r8d; dwFlags
0x140043d8c  xor     edx, edx; pgSubsystem
0x140043d8e  lea     rcx, [rbp+17C0h+phCatAdmin]; phCatAdmin
0x140043d92  call    cs:__imp_CryptCATAdminAcquireContext
0x140043d99  nop     dword ptr [rax+rax+00h]
0x140043d9e  test    eax, eax
0x140043da0  jnz     short loc_140043DA6
0x140043da2  mov     [rbp+17C0h+phCatAdmin], r13
0x140043da6  mov     [rbp+17C0h+pvData], r13w
0x140043dae  lea     rcx, [rbp+17C0h+hKey]
0x140043db2  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140043db7  mov     [rsp+18C0h+phkResult], rax; phkResult
0x140043dbc  mov     r9d, 20019h; samDesired
0x140043dc2  xor     r8d, r8d; ulOptions
0x140043dc5  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services"
0x140043dcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140043dd3  call    cs:__imp_RegOpenKeyExW
0x140043dda  nop     dword ptr [rax+rax+00h]
0x140043ddf  test    eax, eax
0x140043de1  jz      short loc_140043E3F
0x140043de3  mov     rcx, [rbp+17C8h]; this
0x140043dea  lea     r13, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x140043df1  mov     [rsp+18C0h+lpcbMaxSubKeyLen], r13; int
0x140043df6  mov     edi, 80004005h
0x140043dfb  mov     dword ptr [rsp+18C0h+phkResult], edi; wil::details *
0x140043dff  lea     r9, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x140043e06  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043e0d  mov     edx, 495h; void *
0x140043e12  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043e17  call    cs:__imp_GetLastError
0x140043e1e  nop     dword ptr [rax+rax+00h]
0x140043e23  xor     r13d, r13d
0x140043e26  mov     ebx, eax
0x140043e28  test    eax, eax
0x140043e2a  jle     short loc_140043E35
0x140043e2c  movzx   ebx, ax
0x140043e2f  or      ebx, 80070000h
0x140043e35  test    ebx, ebx
0x140043e37  cmovns  ebx, edi
0x140043e3a  jmp     loc_1400448E8
0x140043e3f  mov     [rsp+18C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140043e44  mov     [rsp+18C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140043e49  mov     [rsp+18C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140043e4e  mov     [rsp+18C0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140043e53  mov     [rsp+18C0h+lpcValues], r13; lpcValues
0x140043e58  mov     [rsp+18C0h+lpcbMaxClassLen], r13; char *
0x140043e5d  lea     rax, [rsp+18C0h+cbMaxSubKeyLen]
0x140043e62  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; int
0x140043e67  mov     [rsp+18C0h+phkResult], r13; lpcSubKeys
0x140043e6c  xor     r9d, r9d; lpReserved
0x140043e6f  xor     r8d, r8d; lpcchClass
0x140043e72  xor     edx, edx; lpClass
0x140043e74  mov     rcx, [rbp+17C0h+hKey]; hKey
0x140043e78  call    cs:__imp_RegQueryInfoKeyW
0x140043e7f  nop     dword ptr [rax+rax+00h]
0x140043e84  test    eax, eax
0x140043e86  jz      short loc_140043ECD
0x140043e88  mov     rcx, [rbp+17C8h]; this
0x140043e8f  lea     rax, aRegqueryinfoke_1; "RegQueryInfoKey failed"
0x140043e96  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; int
0x140043e9b  mov     edi, 80004005h
0x140043ea0  mov     dword ptr [rsp+18C0h+phkResult], edi; wil::details *
0x140043ea4  lea     r9, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x140043eab  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043eb2  mov     edx, 4A8h; void *
0x140043eb7  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043ebc  call    cs:__imp_GetLastError
0x140043ec3  nop     dword ptr [rax+rax+00h]
0x140043ec8  jmp     loc_140043E26
0x140043ecd  mov     eax, [rsp+18C0h+cbMaxSubKeyLen]
0x140043ed1  inc     eax
0x140043ed3  mov     [rsp+18C0h+cbMaxSubKeyLen], eax
0x140043ed7  mov     edx, eax
0x140043ed9  lea     rcx, [rsp+18C0h+hkey]
0x140043ede  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x140043ee3  mov     r12, [rax]
0x140043ee6  mov     [rax], r13
0x140043ee9  mov     [rbp+17C0h+var_1760], r12
0x140043eed  mov     rcx, [rsp+18C0h+hkey]; void *
0x140043ef2  test    rcx, rcx
0x140043ef5  jz      short loc_140043EFC
0x140043ef7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043efc  test    r12, r12
0x140043eff  jz      loc_1400448C7
0x140043f05  mov     edi, r13d
0x140043f08  mov     [rbp+17C0h+var_1840], r13d
0x140043f0c  lea     r13, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x140043f13  lea     rsi, aCkernelreportd_0; "CKernelReportDataCollection::GetDriverI"...
0x140043f1a  lea     r15, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043f21  lea     rax, [rbp+17C0h+var_1800]
0x140043f25  mov     [rbp+17C0h+var_1810], rax
0x140043f29  lea     rax, [rbp+17C0h+var_1800]
0x140043f2d  mov     [rbp+17C0h+var_1808], rax
0x140043f31  xor     ecx, ecx
0x140043f33  mov     [rbp+17C0h+var_1800], cx
0x140043f37  lea     rax, [rbp+17C0h+var_1820]
0x140043f3b  mov     [rbp+17C0h+var_1830], rax
0x140043f3f  lea     rax, [rbp+17C0h+var_1820]
0x140043f43  mov     [rbp+17C0h+var_1828], rax
0x140043f47  mov     [rbp+17C0h+var_1820], cx
0x140043f4b  mov     eax, [rsp+18C0h+cbMaxSubKeyLen]
0x140043f4f  mov     [rbp+17C0h+cchName], eax
0x140043f52  lea     rax, [rbp+17C0h+ftLastWriteTime]
0x140043f56  mov     [rsp+18C0h+lpcValues], rax; lpftLastWriteTime
0x140043f5b  mov     [rsp+18C0h+lpcbMaxClassLen], rcx; char *
0x140043f60  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rcx; lpClass
0x140043f65  mov     [rsp+18C0h+phkResult], rcx; lpReserved
0x140043f6a  lea     r9, [rbp+17C0h+cchName]; lpcchName
0x140043f6e  mov     r8, r12; lpName
0x140043f71  mov     edx, edi; dwIndex
0x140043f73  mov     rcx, [rbp+17C0h+hKey]; hKey
0x140043f77  call    cs:__imp_RegEnumKeyExW
0x140043f7e  nop     dword ptr [rax+rax+00h]
0x140043f83  xor     ecx, ecx
0x140043f85  test    eax, eax
0x140043f87  jz      short loc_140043FF8
0x140043f89  cmp     eax, 103h
0x140043f8e  jz      loc_140044812
0x140043f94  mov     rcx, [rbp+17C8h]; this
0x140043f9b  lea     rdx, aRegenumkeyexFa; "RegEnumKeyEx failed"
0x140043fa2  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x140043fa7  mov     dword ptr [rsp+18C0h+phkResult], eax; wil::details *
0x140043fab  mov     r9, rsi; char *
0x140043fae  mov     r8, r15; unsigned int
0x140043fb1  mov     edx, 4D7h; void *
0x140043fb6  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140043fbb  nop
0x140043fbc  lea     rax, [rbp+17C0h+var_1820]
0x140043fc0  mov     rcx, [rbp+17C0h+var_1830]; void *
0x140043fc4  cmp     rcx, rax
0x140043fc7  jz      short loc_140043FD6
0x140043fc9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043fd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043fd5  nop
0x140043fd6  lea     rax, [rbp+17C0h+var_1800]
0x140043fda  mov     rcx, [rbp+17C0h+var_1810]; void *
0x140043fde  cmp     rcx, rax
0x140043fe1  jz      loc_140044808
0x140043fe7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043fee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043ff3  jmp     loc_140044808
0x140043ff8  mov     [rsp+18C0h+hkey], rcx
0x140043ffd  lea     rcx, [rsp+18C0h+hkey]
0x140044002  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140044007  mov     [rsp+18C0h+phkResult], rax; phkResult
0x14004400c  mov     r9d, 20019h; samDesired
0x140044012  xor     r8d, r8d; ulOptions
0x140044015  mov     rdx, r12; lpSubKey
0x140044018  mov     rcx, [rbp+17C0h+hKey]; hKey
0x14004401c  call    cs:__imp_RegOpenKeyExW
0x140044023  nop     dword ptr [rax+rax+00h]
0x140044028  test    eax, eax
0x14004402a  jz      short loc_140044070
0x14004402c  mov     [rsp+18C0h+lpcbMaxSubKeyLen], r13; int
0x140044031  mov     dword ptr [rsp+18C0h+phkResult], 80000000h; wil::details *
0x140044039  mov     edx, 4DFh; void *
0x14004403e  mov     r9, rsi; char *
0x140044041  mov     r8, r15; unsigned int
0x140044044  mov     rcx, [rbp+17C8h]; this
0x14004404b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044050  nop
0x140044051  mov     rcx, [rsp+18C0h+hkey]; hKey
0x140044056  test    rcx, rcx
0x140044059  jz      loc_140043FBC
0x14004405f  call    cs:__imp_RegCloseKey
0x140044066  nop     dword ptr [rax+rax+00h]
0x14004406b  jmp     loc_140043FBC
0x140044070  mov     [rsp+18C0h+cbData], 4
0x140044078  lea     rax, [rsp+18C0h+cbData]
0x14004407d  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x140044082  lea     rax, [rbp+17C0h+Data]
0x140044086  mov     [rsp+18C0h+phkResult], rax; lpData
0x14004408b  xor     r9d, r9d; lpType
0x14004408e  xor     r8d, r8d; lpReserved
0x140044091  lea     rdx, aType_0; "Type"
0x140044098  mov     rcx, [rsp+18C0h+hkey]; hKey
0x14004409d  call    cs:__imp_RegQueryValueExW
0x1400440a4  nop     dword ptr [rax+rax+00h]
0x1400440a9  xor     edx, edx; lpSubKey
0x1400440ab  test    eax, eax
0x1400440ad  jnz     short loc_140044051
0x1400440af  test    [rbp+17C0h+Data], 0Bh
0x1400440b3  jz      short loc_140044051
0x1400440b5  mov     [rsp+18C0h+cbData], 208h
0x1400440bd  mov     [rbp+17C0h+pvData], dx
0x1400440c4  lea     rax, [rsp+18C0h+cbData]
0x1400440c9  mov     [rsp+18C0h+lpcbMaxClassLen], rax; char *
0x1400440ce  lea     rax, [rbp+17C0h+pvData]
0x1400440d5  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; pvData
0x1400440da  mov     [rsp+18C0h+phkResult], rdx; pdwType
0x1400440df  lea     r9d, [rdx+2]; dwFlags
0x1400440e3  lea     r8, aImagepath; "ImagePath"
0x1400440ea  mov     rcx, [rsp+18C0h+hkey]; hkey
0x1400440ef  call    cs:__imp_RegGetValueW
0x1400440f6  nop     dword ptr [rax+rax+00h]
0x1400440fb  xor     ecx, ecx
0x1400440fd  test    eax, eax
0x1400440ff  jz      short loc_14004412F
0x140044101  mov     [rbp+17C0h+pvData], cx
0x140044108  mov     rcx, [rbp+17C8h]; this
0x14004410f  lea     rdx, aRegqueryvaluee; "RegQueryValueEx failed"
0x140044116  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14004411b  mov     dword ptr [rsp+18C0h+phkResult], eax; wil::details *
0x14004411f  mov     r9, rsi; char *
0x140044122  mov     r8, r15; unsigned int
0x140044125  mov     edx, 50Bh; void *
0x14004412a  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14004412f  lea     r9, [rbp+17C0h+lpFileName]
0x140044133  lea     r8, [rbp+17C0h+pvData]
0x14004413a  mov     rdx, r12
0x14004413d  call    ?GenerateDriverPath@CKernelReportDataCollection@@AEAAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CKernelReportDataCollection::GenerateDriverPath(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140044142  test    eax, eax
0x140044144  jns     short loc_140044160
0x140044146  lea     rdx, aGeneratedriver; "GenerateDriverPath failed"
0x14004414d  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rdx
0x140044152  mov     dword ptr [rsp+18C0h+phkResult], eax
0x140044156  mov     edx, 512h
0x14004415b  jmp     loc_14004403E
0x140044160  mov     rcx, [rbp+17C0h+lpFileName]; wchar_t *
0x140044164  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140044169  xor     edx, edx; lpSubKey
0x14004416b  test    al, al
0x14004416d  jz      loc_140044051
0x140044173  xorps   xmm0, xmm0
0x140044176  movdqa  [rbp+17C0h+var_1120], xmm0
0x14004417e  mov     [rbp+17C0h+var_770], dx
0x140044185  mov     [rbp+17C0h+var_870], dx
0x14004418c  mov     [rbp+17C0h+var_250], dx
0x140044193  mov     [rsp+18C0h+cbData], 208h
0x14004419b  mov     [rbp+17C0h+InfName], dx
0x1400441a2  lea     rax, [rsp+18C0h+cbData]
0x1400441a7  mov     [rsp+18C0h+lpcbMaxClassLen], rax; char *
0x1400441ac  lea     rax, [rbp+17C0h+InfName]
0x1400441b3  mov     [rsp+18C0h+lpcbMaxSubKeyLen], rax; pvData
0x1400441b8  mov     [rsp+18C0h+phkResult], rdx; pdwType
0x1400441bd  lea     r9d, [rdx+20h]; dwFlags
0x1400441c1  lea     r8, aOwners; "Owners"
0x1400441c8  mov     rcx, [rsp+18C0h+hkey]; hkey
0x1400441cd  call    cs:__imp_RegGetValueW
0x1400441d4  nop     dword ptr [rax+rax+00h]
0x1400441d9  xor     ecx, ecx
0x1400441db  test    eax, eax
0x1400441dd  jnz     loc_14004451E
0x1400441e3  call    IsSetupVerifyInfFileWPresent
0x1400441e8  test    al, al
0x1400441ea  jz      loc_14004428B
0x1400441f0  xor     edx, edx; Val
0x1400441f2  mov     r8d, 620h; Size
0x1400441f8  lea     rcx, [rbp+17C0h+Src]; void *
0x1400441ff  call    memset_0
0x140044204  lea     rcx, [rbp+17C0h+InfSignerInfo]; void *
  ... truncated ...
```
