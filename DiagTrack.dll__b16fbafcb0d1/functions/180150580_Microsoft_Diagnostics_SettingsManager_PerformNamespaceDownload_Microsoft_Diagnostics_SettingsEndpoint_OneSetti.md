# Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload(Microsoft::Diagnostics::SettingsEndpoint &,OneSettingsDownloadSession *,unsigned __int64 const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,std::optional<ulong>,bool &)

- ea: `0x180150580`
- end: `0x180152d1e`
- name: `?PerformNamespaceDownload@SettingsManager@Diagnostics@Microsoft@@AEAAJAEAVSettingsEndpoint@23@PEAUOneSettingsDownloadSession@@AEB_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$optional@K@7@AEA_N@Z`
- size: `10142`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::SettingsManager *this, struct Microsoft::Diagnostics::SettingsEndpoint *, __int64, unsigned __int64 *, __int64, char, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `68`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18014dc8c`
- `0x180260ecc`

## callees

- `0x180002a28`
- `0x1800050c4`
- `0x180005644`
- `0x18001ef98`
- `0x180020e30`
- `0x18002110c`
- `0x180021538`
- `0x18002ac10`
- `0x18002afd8`
- `0x18002b7c0`
- `0x18002b9c0`
- `0x18002cb04`
- `0x18002df00`
- `0x180031168`
- `0x18003119c`
- `0x180035130`
- `0x18003c66c`
- `0x180049d00`
- `0x18004ae94`
- `0x18004b6ac`
- `0x180052240`
- `0x180053ff4`
- `0x1800561a4`
- `0x18005fb44`
- `0x180064e34`
- `0x180064e8c`
- `0x180064eb0`
- `0x180081924`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008ab10`
- `0x18008abf4`
- `0x18009c7e4`
- `0x18009c85c`
- `0x18009c8c0`
- `0x1800a34b0`
- `0x1800b44ec`
- `0x1800b47f0`
- `0x1800b5cb4`
- `0x1800bc658`
- `0x1800cf7d8`
- `0x1800d11c0`
- `0x1800d77a8`
- `0x180102bbc`
- `0x18011715c`
- `0x180121fa0`
- `0x180125100`
- `0x18012d7b0`
- `0x18012d9d0`
- `0x18012e9d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801507b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801507b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180150cf8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180150cf8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801507aa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801507aa`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180150c37`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180150c37`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180150d57`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180150d57`

## string_xrefs

- `0x1801509bf`: `LastFileWrittenPath`
- `0x18015064b`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801506ca`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801506e0`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180150963`: `DestinationFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload(
        Microsoft::Diagnostics::SettingsManager *this,
        struct Microsoft::Diagnostics::SettingsEndpoint *a2,
        __int64 a3,
        unsigned __int64 *a4,
        __int64 a5,
        char a6,
        __int64 a7,
        _BYTE *a8)
{
  Microsoft::Diagnostics::SettingsManager *v9; // r14
  int v10; // r15d
  int Ticket; // eax
  bool v13; // al
  struct Microsoft::Diagnostics::EnterpriseData *EnterpriseData; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  const WCHAR *v17; // rcx
  __int64 v18; // r8
  _QWORD *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned __int64 *v23; // r12
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  const WCHAR *v26; // r8
  WCHAR *v27; // rcx
  HRESULT v28; // eax
  unsigned int v29; // ebx
  const WCHAR *v30; // rcx
  HANDLE FileW; // rax
  CONTEXT *v32; // rbx
  __int64 v33; // r8
  unsigned int v34; // ebx
  __int64 v35; // r8
  int v36; // r14d
  int v37; // r15d
  struct Microsoft::Diagnostics::SystemStateManager *SystemStateManager; // rax
  __int128 *v39; // rdx
  __int64 v40; // r12
  struct Microsoft::Diagnostics::EnterpriseData *v41; // rax
  __int64 v42; // r8
  __int64 AadDeviceToken; // rax
  __int64 v44; // rax
  __int64 v45; // r8
  int v46; // r15d
  __int128 v47; // xmm6
  __int64 v48; // r8
  __int128 v49; // xmm7
  __int64 v50; // r8
  __int128 v51; // xmm8
  __int64 v52; // r8
  struct _GUID v53; // xmm9
  unsigned int MillisToNextDownloadOnCostedNetwork; // eax
  int v55; // edx
  struct Microsoft::Diagnostics::SystemStateManager *v56; // rax
  __int64 v57; // r8
  std::_Ref_count_base *v58; // r12
  __int64 v59; // r8
  __int64 v60; // r8
  __int64 v61; // r8
  __int64 v62; // r8
  int Qword; // eax
  unsigned __int64 FileTimeAsULL; // rax
  int v65; // eax
  __int64 v66; // r8
  __int64 v67; // r8
  __int64 v68; // r8
  __int64 v69; // r8
  __int64 v70; // r8
  _QWORD *v71; // rax
  __int128 *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r8
  __int128 *p_Src; // rcx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r8
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // r8
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rax
  int v86; // r8d
  __int64 v87; // r9
  __int64 v88; // r10
  __int64 v89; // r11
  Microsoft::Diagnostics::HeartBeat *v90; // rax
  Microsoft::Diagnostics::HeartBeat *v91; // rax
  Microsoft::Diagnostics::HeartBeat *HeartbeatManager; // rcx
  __int64 v93; // r8
  Microsoft::Diagnostics::HeartBeat *v94; // rax
  unsigned int v95; // ebx
  unsigned int v96; // ebx
  __int64 v97; // r8
  int v98; // r9d
  unsigned int v99; // ecx
  _QWORD *v100; // rax
  __int64 v101; // r8
  _QWORD *v102; // rax
  struct _GUID v103; // xmm0
  __int64 v104; // r8
  _OWORD *v105; // rax
  BOOL v106; // edx
  int v107; // ecx
  int v108; // eax
  __int64 v109; // r8
  unsigned int v110; // ebx
  __m128i v111; // xmm6
  unsigned __int64 v112; // rax
  __int64 v113; // r8
  __int128 *v114; // rax
  __int64 v115; // rcx
  __int64 v116; // r8
  __int64 v117; // r8
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r8
  __int64 v121; // rcx
  __int64 v122; // r8
  __int64 v123; // r8
  __int64 v124; // rcx
  __int64 v125; // r8
  __int64 v126; // rax
  int v127; // r8d
  __int64 v128; // r9
  __int64 v129; // r10
  __int64 v130; // r11
  _QWORD *v131; // rax
  __int64 v132; // r8
  _QWORD *v133; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-838h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-838h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-838h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-838h]
  std::_Ref_count_base *v138[2]; // [rsp+80h] [rbp-7D8h] BYREF
  _DWORD v139[4]; // [rsp+90h] [rbp-7C8h] BYREF
  struct _GUID v140; // [rsp+A0h] [rbp-7B8h] BYREF
  int QueryParameters; // [rsp+B0h] [rbp-7A8h] BYREF
  bool v142; // [rsp+B4h] [rbp-7A4h]
  char v143; // [rsp+B5h] [rbp-7A3h]
  int v144[4]; // [rsp+C0h] [rbp-798h] BYREF
  __int64 v145; // [rsp+D0h] [rbp-788h] BYREF
  __int128 *v146; // [rsp+D8h] [rbp-780h] BYREF
  char v147; // [rsp+E0h] [rbp-778h]
  __int64 v148; // [rsp+E8h] [rbp-770h] BYREF
  __int64 v149; // [rsp+F0h] [rbp-768h] BYREF
  unsigned int v150[2]; // [rsp+F8h] [rbp-760h] BYREF
  __int64 v151[2]; // [rsp+100h] [rbp-758h] BYREF
  unsigned __int64 *v152; // [rsp+110h] [rbp-748h]
  __int64 v153; // [rsp+118h] [rbp-740h] BYREF
  __int128 v154; // [rsp+120h] [rbp-738h] BYREF
  __int64 v155; // [rsp+130h] [rbp-728h]
  __int64 v156; // [rsp+138h] [rbp-720h] BYREF
  Microsoft::Diagnostics::SettingsManager *v157; // [rsp+140h] [rbp-718h]
  _QWORD v158[2]; // [rsp+148h] [rbp-710h] BYREF
  char v159; // [rsp+158h] [rbp-700h]
  _BYTE *v160; // [rsp+160h] [rbp-6F8h]
  __int64 v161[2]; // [rsp+170h] [rbp-6E8h] BYREF
  _BYTE v162[16]; // [rsp+180h] [rbp-6D8h] BYREF
  _BYTE v163[16]; // [rsp+190h] [rbp-6C8h] BYREF
  _BYTE v164[16]; // [rsp+1A0h] [rbp-6B8h] BYREF
  __int64 v165[2]; // [rsp+1B0h] [rbp-6A8h] BYREF
  __int128 v166; // [rsp+1C0h] [rbp-698h] BYREF
  __int64 v167; // [rsp+1D0h] [rbp-688h]
  unsigned __int64 v168; // [rsp+1D8h] [rbp-680h]
  __int128 Src; // [rsp+1E0h] [rbp-678h] BYREF
  __m128i si128; // [rsp+1F0h] [rbp-668h]
  PWSTR pszPathOut[3]; // [rsp+200h] [rbp-658h] BYREF
  unsigned __int64 v172; // [rsp+218h] [rbp-640h]
  LPCWSTR lpFileName[4]; // [rsp+220h] [rbp-638h] BYREF
  PCWSTR pszPathIn[4]; // [rsp+240h] [rbp-618h] BYREF
  _BYTE v175[32]; // [rsp+260h] [rbp-5F8h] BYREF
  __int128 v176; // [rsp+280h] [rbp-5D8h] BYREF
  __m128i v177; // [rsp+290h] [rbp-5C8h]
  _QWORD v178[6]; // [rsp+2A0h] [rbp-5B8h] BYREF
  int v179[282]; // [rsp+2D0h] [rbp-588h] BYREF
  int v180[14]; // [rsp+738h] [rbp-120h] BYREF
  __int64 v181[4]; // [rsp+770h] [rbp-E8h] BYREF
  _BYTE v182[32]; // [rsp+790h] [rbp-C8h] BYREF
  _BYTE v183[32]; // [rsp+7B0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+0h]

  v152 = a4;
  v153 = a3;
  v9 = this;
  v157 = this;
  v161[0] = a5;
  v160 = a8;
  v10 = 0;
  v139[0] = 0;
  v154 = 0;
  v155 = 0;
  v146 = &v154;
  v147 = 1;
  if ( !Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature(a2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)0x8007007BLL,
      dwCreationDisposition);
    v147 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
    return 2147942523LL;
  }
  if ( *((_WORD *)a2 + 4) )
  {
    if ( !*(_QWORD *)(a5 + 16) )
    {
      *(struct _GUID *)((char *)v9 + 616) = *Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(&v140);
      Ticket = Microsoft::Diagnostics::DeviceTicket::GetTicket((char *)v9 + 552, a5);
      if ( Ticket < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x979,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)Ticket,
          dwCreationDisposition);
    }
  }
  v13 = _InterlockedCompareExchange64((_QWORD *)&xmmword_1804631B0 + 1, 0, 0) != 0;
  v142 = v13;
  if ( *((_BYTE *)a2 + 5) && v13 )
  {
    EnterpriseData = Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    LOBYTE(v15) = 1;
    Microsoft::Diagnostics::EnterpriseData::PopulateAadDeviceToken(EnterpriseData, v15);
  }
  Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath((__int64)a2, (__int64)lpFileName);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
  *(_OWORD *)v138 = *(_OWORD *)&off_1803846E0;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v138) )
  {
    std::wstring::operator std::wstring_view((char *)a2 + 168, v138, v16);
    if ( v138[1] )
    {
      v17 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v17 = lpFileName[0];
      if ( GetFileAttributesW(v17) == -1 )
      {
        v139[0] = GetLastError();
        v19 = (_QWORD *)std::wstring::operator std::wstring_view(&qword_1804626F0, &v140, v18);
        std::wstring::_Assign<wchar_t>((char *)a2 + 168, *v19, v19[1]);
        v138[0] = (std::_Ref_count_base *)L"SettingsManager_SettingsFileWentMissing_0";
        v138[1] = (std::_Ref_count_base *)41;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v179,
          (unsigned int)v138,
          0x1000000,
          0,
          0,
          0,
          0);
        std::wstring::operator std::wstring_view((char *)a2 + 104, &v148, v20);
        v138[0] = (std::_Ref_count_base *)L"Partner";
        v138[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
        std::wstring::operator std::wstring_view((char *)a2 + 136, &v148, v21);
        v138[0] = (std::_Ref_count_base *)L"Feature";
        v138[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
        std::wstring::operator std::wstring_view((char *)a2 + 72, &v148, v22);
        v138[0] = (std::_Ref_count_base *)L"Version";
        v138[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
        v138[0] = (std::_Ref_count_base *)L"GetFileAttributesLastError";
        v138[1] = (std::_Ref_count_base *)26;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v179, v180, v138, v139);
        v138[0] = (std::_Ref_count_base *)L"DestinationFilePath";
        v138[1] = (std::_Ref_count_base *)19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, lpFileName);
        std::wstring::wstring(&v176, (char *)a2 + 40);
        v10 = 4;
        v139[0] = 4;
        v138[0] = (std::_Ref_count_base *)L"LastFileWrittenPath";
        v138[1] = (std::_Ref_count_base *)19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, &v176);
        std::wstring::_Tidy_deallocate(&v176);
        v143 = *(_BYTE *)a2;
        v138[0] = (std::_Ref_count_base *)L"LastFileWrittenWasThisEpoch";
        v138[1] = (std::_Ref_count_base *)27;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<bool>((int)v179, (int)v180);
        v151[0] = *((_QWORD *)a2 + 3);
        v138[0] = (std::_Ref_count_base *)L"LastDownloadTime";
        v138[1] = (std::_Ref_count_base *)16;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
        v23 = v152;
        if ( *((_QWORD *)a2 + 3) <= *v152 )
          v24 = (*v152 - *((_QWORD *)a2 + 3)) / 0x2710;
        else
          v24 = 0;
        v151[0] = v24;
        v138[0] = (std::_Ref_count_base *)L"LastDownloadDeltaMillis";
        v138[1] = (std::_Ref_count_base *)23;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
        if ( *((_QWORD *)a2 + 4) <= *v23 )
          v25 = (*v23 - *((_QWORD *)a2 + 4)) / 0x2710;
        else
          v25 = 0;
        v151[0] = v25;
        v138[0] = (std::_Ref_count_base *)L"LastFileWrittenDeltaMillis";
        v138[1] = (std::_Ref_count_base *)26;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
        std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
          &v154,
          v179);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v179);
        v9 = v157;
      }
    }
  }
  std::operator+<wchar_t>(pszPathIn, lpFileName, L".new");
  LOBYTE(v148) = 0;
  v149 = -1;
  std::wstring::wstring(pszPathOut, pszPathIn[2], 0);
  v26 = (const WCHAR *)pszPathIn;
  if ( pszPathIn[3] > (PCWSTR)7 )
    v26 = pszPathIn[0];
  v27 = (WCHAR *)pszPathOut;
  if ( v172 > 7 )
    v27 = pszPathOut[0];
  v28 = PathCchCanonicalizeEx(v27, (size_t)pszPathOut[2] + 1, v26, 0);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9AD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)v28,
      dwCreationDisposition);
    std::wstring::_Tidy_deallocate(pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
    std::wstring::_Tidy_deallocate(pszPathIn);
    std::wstring::_Tidy_deallocate(lpFileName);
    v147 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
    return v29;
  }
  v30 = (const WCHAR *)pszPathOut;
  if ( v172 > 7 )
    v30 = pszPathOut[0];
  FileW = CreateFileW(v30, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
  if ( FileW != (HANDLE)-1LL )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v149,
      FileW);
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v32 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
  RtlCaptureContext(v32);
  LOBYTE(v33) = 3;
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(v151, 300000, v33, v32);
  *(_OWORD *)v138 = *(_OWORD *)&off_180384930;
  QueryParameters = Microsoft::Diagnostics::SettingsDownloader::GetQueryParameters(
                      &Src,
                      (__int64)v9 + 464,
                      (__int64)v9 + 496);
  if ( QueryParameters < 0 )
  {
    v138[0] = (std::_Ref_count_base *)L"SettingsManager_FailedToGetTargetingAttributes_0";
    v138[1] = (std::_Ref_count_base *)48;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v179,
      (unsigned int)v138,
      0x1000000,
      0,
      0,
      0,
      0);
    v138[0] = (std::_Ref_count_base *)L"ErrorCode";
    v138[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v179, (int)v180);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v154,
      v179);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v179);
  }
  *(_OWORD *)v138 = *(_OWORD *)&off_1803846C0;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v138)
    && std::wstring::find(&Src, L"&acc-validationmerge=true", 0) == -1 )
  {
    std::wstring::append(&Src, L"&acc-validationmerge=true");
  }
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v151);
  v166 = 0;
  v167 = 0;
  v168 = 7;
  LOWORD(v166) = 0;
  v34 = 0;
  QueryParameters = 0;
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v178);
  *(_QWORD *)v150 = 0;
  v156 = 0;
  *(_OWORD *)v138 = *(_OWORD *)&off_1803846D0;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v138) )
  {
    v36 = 0;
    v139[0] = 0;
    v37 = 304;
    std::wstring::operator std::wstring_view((char *)a2 + 168, v138, v35);
    std::wstring::_Assign<wchar_t>(&v166, v138[0], v138[1]);
    v34 = *((_DWORD *)a2 + 4);
    QueryParameters = v34;
LABEL_67:
    Microsoft::Diagnostics::SettingsManager::NotifySuccessfulSettingsDownload(v157, a2, v152);
    goto LABEL_68;
  }
  v176 = 0;
  v177 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v176) = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631F0, 0, 0) )
  {
    SystemStateManager = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::ProxyConfig::GetProxyOverrideServer((struct Microsoft::Diagnostics::SystemStateManager *)((char *)SystemStateManager + 696));
    v10 |= 8u;
    v139[0] = v10;
    std::wstring::operator=(&v176, v175);
    std::wstring::_Tidy_deallocate(v175);
  }
  Microsoft::Diagnostics::UserManager::GetNetworkImpersonationToken(&v145);
  *(_OWORD *)v138 = 0;
  v151[0] = v145;
  v39 = &v176;
  if ( v177.m128i_i64[1] > 7uLL )
    v39 = (__int128 *)v176;
  std::wstring::wstring(v181, v39);
  v40 = *((_QWORD *)v9 + 138);
  if ( *((_BYTE *)a2 + 5) && v142 )
  {
    v41 = Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    LOBYTE(v42) = 1;
    AadDeviceToken = Microsoft::Diagnostics::EnterpriseData::GetAadDeviceToken(v41, v158, v42);
    v44 = std::wstring::wstring(v183, AadDeviceToken);
    v46 = v10 | 1;
  }
  else
  {
    v44 = std::wstring::wstring(v182, &qword_1804626F0);
    v46 = v10 | 2;
  }
  v139[0] = v46;
  v47 = *(_OWORD *)std::wstring::operator std::wstring_view(v44, v163, v45);
  v49 = *(_OWORD *)std::wstring::operator std::wstring_view(v161[0], v164, v48);
  v51 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v162, v50);
  v53 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v175, v52);
  MillisToNextDownloadOnCostedNetwork = Microsoft::Diagnostics::SettingsManager::GetMillisToNextDownloadOnCostedNetwork(
                                          v9,
                                          a2);
  *(_OWORD *)v161 = v47;
  *(_OWORD *)v165 = v49;
  *(_OWORD *)v144 = v51;
  v140 = v53;
  LOBYTE(v55) = MillisToNextDownloadOnCostedNetwork == 0;
  v36 = Microsoft::Diagnostics::SettingsDownloader::PerformDownload(
          (int)a2,
          v55,
          (int)&v140,
          (int)v144,
          (__int64)v165,
          (__int64)v161,
          (__int64)&v148,
          v178,
          v153,
          a7,
          v40,
          (__int64)v181,
          v151[0],
          (__int64)v138,
          (__int64)v150,
          (__int64)&v156);
  v139[0] = v36;
  if ( (v46 & 2) != 0 )
  {
    LOBYTE(v46) = v46 & 0xFD;
    std::wstring::_Tidy_deallocate(v182);
  }
  if ( (v46 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v183);
  std::wstring::_Tidy_deallocate(v181);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631F0, 0, 0) )
  {
    v56 = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v140 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v176, v175, v56);
    Microsoft::Diagnostics::ProxyConfig::Update(v57 + 696, &v140, (unsigned int)v36);
  }
  if ( v36 == -2147023673 )
  {
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        byte_1803E7BC9);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)0x800704C7LL,
      dwCreationDispositiona);
    if ( v138[1] )
      std::_Ref_count_base::_Decref(v138[1]);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v145);
    std::wstring::_Tidy_deallocate(&v176);
    std::wstring::_Tidy_deallocate(v178);
    std::wstring::_Tidy_deallocate(&v166);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
    std::wstring::_Tidy_deallocate(pszPathIn);
    std::wstring::_Tidy_deallocate(lpFileName);
    v147 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
    return 2147943623LL;
  }
  v37 = 0;
  if ( v36 >= 0 )
  {
    v58 = v138[0];
    std::wstring::operator=(&v166, (char *)v138[0] + 72);
    v37 = *((_DWORD *)v58 + 16);
    if ( v37 == 200 )
    {
      v34 = *((_DWORD *)v58 + 27);
      QueryParameters = v34;
    }
  }
  if ( v138[1] )
    std::_Ref_count_base::_Decref(v138[1]);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v145);
  std::wstring::_Tidy_deallocate(&v176);
  if ( v37 == 304 || v37 == 200 )
    goto LABEL_67;
LABEL_68:
  if ( v37 != 304 )
  {
    v138[0] = (std::_Ref_count_base *)L"SettingsManager_DownloadOneSettingsNamespace_0";
    v138[1] = (std::_Ref_count_base *)46;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v179,
      (unsigned int)v138,
      0x1000000,
      0,
      0,
      0,
      0);
    v138[0] = (std::_Ref_count_base *)L"ErrorCode";
    v138[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v140, v59);
    v138[0] = (std::_Ref_count_base *)L"Version";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v140, v60);
    v138[0] = (std::_Ref_count_base *)L"Partner";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v140, v61);
    v138[0] = (std::_Ref_count_base *)L"Feature";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"Parameters";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, &Src);
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v140, v62);
    v138[0] = (std::_Ref_count_base *)L"ClientETag";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"ServerETag";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, &v166);
    v138[0] = (std::_Ref_count_base *)L"RefreshIntervalFromHeader";
    v138[1] = (std::_Ref_count_base *)25;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v179, v180, v138, &QueryParameters);
    v138[0] = (std::_Ref_count_base *)L"Headers";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, v178);
    LODWORD(v145) = v37 == 200;
    v138[0] = (std::_Ref_count_base *)L"Changed";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<int>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadPollTime";
    v138[1] = (std::_Ref_count_base *)16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadDurationMs";
    v138[1] = (std::_Ref_count_base *)18;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadOnDiskFileSizeBytes";
    v138[1] = (std::_Ref_count_base *)27;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<__int64>((int)v179, (int)v180);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v154,
      v179);
LABEL_78:
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v179);
    v36 = v139[0];
    v34 = QueryParameters;
    goto LABEL_79;
  }
  v151[0] = 0;
  v140 = *(struct _GUID *)&off_1803846B0;
  *(_OWORD *)v144 = *(_OWORD *)&off_180384850;
  Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v144, &v140, v151);
  if ( Qword < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA3E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)Qword,
      dwCreationDispositiona);
  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  if ( v151[0] > FileTimeAsULL )
  {
    v140 = *(struct _GUID *)&off_1803846B0;
    *(_OWORD *)v144 = *(_OWORD *)&off_180384850;
    v65 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v144, (int)&v140, v151[0], 0);
    if ( v65 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA44,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)(unsigned int)v65,
        dwCreationDispositionb);
    goto LABEL_77;
  }
  if ( FileTimeAsULL - v151[0] >= 0xC92A69C000LL )
  {
LABEL_77:
    v138[0] = (std::_Ref_count_base *)L"SettingsManager_DownloadOneSettingsNamespace_0";
    v138[1] = (std::_Ref_count_base *)46;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v179,
      (unsigned int)v138,
      0x1000000,
      0,
      0,
      0,
      0);
    v138[0] = (std::_Ref_count_base *)L"ErrorCode";
    v138[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v140, v66);
    v138[0] = (std::_Ref_count_base *)L"Version";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v140, v67);
    v138[0] = (std::_Ref_count_base *)L"Partner";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v140, v68);
    v138[0] = (std::_Ref_count_base *)L"Feature";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"Parameters";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, &Src);
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v140, v69);
    v138[0] = (std::_Ref_count_base *)L"ClientETag";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"ServerETag";
    v138[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, &v166);
    v138[0] = (std::_Ref_count_base *)L"RefreshIntervalFromHeader";
    v138[1] = (std::_Ref_count_base *)25;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v179, v180, v138, &QueryParameters);
    v138[0] = (std::_Ref_count_base *)L"Headers";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v179, v180, v138, v178);
    LODWORD(v145) = 0;
    v138[0] = (std::_Ref_count_base *)L"Changed";
    v138[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<int>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadPollTime";
    v138[1] = (std::_Ref_count_base *)16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadDurationMs";
    v138[1] = (std::_Ref_count_base *)18;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v179, (int)v180);
    v138[0] = (std::_Ref_count_base *)L"DownloadOnDiskFileSizeBytes";
    v138[1] = (std::_Ref_count_base *)27;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<__int64>((int)v179, (int)v180);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v154,
      v179);
    goto LABEL_78;
  }
LABEL_79:
  if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
  {
    LODWORD(v145) = v37;
    v139[0] = v37 == 200;
    v71 = v178;
    if ( v178[3] > 7u )
      v71 = (_QWORD *)v178[0];
    v153 = (__int64)v71;
    QueryParameters = v34;
    v72 = &v166;
    if ( v168 > 7 )
      v72 = (__int128 *)v166;
    v161[0] = (__int64)v72;
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v140, v70);
    std::wstring::operator std::wstring_view(v73, v144, v74);
    _tlgWrapBinary<wchar_t,2>(v175, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    v151[0] = (__int64)p_Src;
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v140, v75);
    std::wstring::operator std::wstring_view(v77, v144, v78);
    _tlgWrapBinary<wchar_t,2>(v162, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v140, v79);
    std::wstring::operator std::wstring_view(v80, v144, v81);
    _tlgWrapBinary<wchar_t,2>(v164, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v140, v82);
    std::wstring::operator std::wstring_view(v83, v144, v84);
    v85 = _tlgWrapBinary<wchar_t,2>(v163, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
    v150[0] = v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)v151,
      (unsigned int)&dword_1803E7B0C,
      v86,
      v87,
      (__int64)v150,
      v85,
      v87,
      v88,
      (__int64)v151,
      v89,
      (__int64)v161,
      (__int64)&QueryParameters,
      (__int64)&v153,
      (__int64)v139,
      (__int64)&v145);
  }
  if ( v36 >= 0 )
  {
    HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpAttempts(HeartbeatManager);
    v93 = 304;
    if ( v37 != 304 && v37 != 404 && v37 != 200 && v37 != 204 )
    {
      v94 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpFailures(v94);
      v95 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xA9C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)0x3A,
              dwCreationDispositiona);
      std::wstring::_Tidy_deallocate(v178);
      std::wstring::_Tidy_deallocate(&v166);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
      std::wstring::_Tidy_deallocate(pszPathIn);
      std::wstring::_Tidy_deallocate(lpFileName);
      v147 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
      return v95;
    }
    if ( a6 && v37 == 404 )
    {
      v96 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xAA6,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)0x43,
              dwCreationDispositiona);
      std::wstring::_Tidy_deallocate(v178);
      std::wstring::_Tidy_deallocate(&v166);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
      std::wstring::_Tidy_deallocate(pszPathIn);
      std::wstring::_Tidy_deallocate(lpFileName);
      v147 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
      return v96;
    }
    if ( v37 == 204 && (unsigned __int16)(*((_WORD *)a2 + 5) - 3) <= 1u )
    {
      if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          &dword_1803E7ABC);
      std::wstring::operator std::wstring_view((char *)a2 + 136, &v140, v93);
      std::wstring::operator std::wstring_view((char *)a2 + 104, v144, v97);
      LOBYTE(v98) = *((_WORD *)a2 + 3) == 0;
      Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
        (_DWORD)v157,
        (unsigned int)v144,
        (unsigned int)&v140,
        v98,
        6);
      *v160 = 1;
      std::wstring::_Tidy_deallocate(v178);
      std::wstring::_Tidy_deallocate(&v166);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
      std::wstring::_Tidy_deallocate(pszPathIn);
      std::wstring::_Tidy_deallocate(lpFileName);
      v147 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
      return 0;
    }
    else
    {
      *((_QWORD *)a2 + 3) = *v152;
      *(_WORD *)((char *)a2 + 1) = 0;
      v158[0] = v157;
      v158[1] = a2;
      v159 = 1;
      v99 = *((_DWORD *)v157 + 279);
      if ( v34 )
      {
        if ( v34 < v99 )
          v34 = *((_DWORD *)v157 + 279);
        if ( v34 > 0x1C20 )
          v34 = 7200;
        if ( v34 % v99 )
          v34 = v99 + v34 - v34 % v99;
        *((_DWORD *)a2 + 4) = v34;
      }
      if ( v167 && (v37 == 304 || v37 == 204) )
      {
        v100 = (_QWORD *)std::wstring::operator std::wstring_view(&v166, v175, 304);
        std::wstring::_Assign<wchar_t>((char *)a2 + 168, *v100, v100[1]);
        v102 = (_QWORD *)std::wstring::operator std::wstring_view(&Src, v175, v101);
        std::wstring::_Assign<wchar_t>((char *)a2 + 200, *v102, v102[1]);
      }
      if ( v37 == 200 )
      {
        v103 = *(struct _GUID *)std::wstring::operator std::wstring_view(pszPathIn, v175, v93);
        v105 = (_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v162, v104);
        v106 = *((_BYTE *)a2 + 4) != 0;
        v140 = v103;
        *(_OWORD *)v144 = *v105;
        LOBYTE(v107) = *((_WORD *)a2 + 3) == 0;
        v108 = Microsoft::Diagnostics::SettingsDownloader::PersistDownload(
                 v107,
                 v106,
                 (int)v144,
                 (int)&v140,
                 (AutoDeleteFile *)&v148);
        v110 = v108;
        if ( v108 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAEF,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v108,
            dwCreationDispositionc);
          v159 = 0;
          Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_2_::operator()(v158);
          std::wstring::_Tidy_deallocate(v178);
          std::wstring::_Tidy_deallocate(&v166);
          std::wstring::_Tidy_deallocate(&Src);
          std::wstring::_Tidy_deallocate(pszPathOut);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
          std::wstring::_Tidy_deallocate(pszPathIn);
          std::wstring::_Tidy_deallocate(lpFileName);
          v147 = 0;
          Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
          std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
          return v110;
        }
        v111 = *(__m128i *)std::wstring::operator std::wstring_view(lpFileName, v175, v109);
        v112 = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
        *(_BYTE *)a2 = 1;
        *((_QWORD *)a2 + 4) = v112;
        std::wstring::_Assign<wchar_t>((char *)a2 + 40, v111.m128i_i64[0], _mm_srli_si128(v111, 8).m128i_u64[0]);
        *v160 = 1;
        if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
        {
          v114 = &v166;
          if ( v168 > 7 )
            v114 = (__int128 *)v166;
          v153 = (__int64)v114;
          std::wstring::operator std::wstring_view((char *)a2 + 168, &v140, v113);
          std::wstring::operator std::wstring_view(v115, v144, v116);
          _tlgWrapBinary<wchar_t,2>(v175, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 136, &v140, v117);
          std::wstring::operator std::wstring_view(v118, v144, v119);
          _tlgWrapBinary<wchar_t,2>(v162, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 104, &v140, v120);
          std::wstring::operator std::wstring_view(v121, v144, v122);
          _tlgWrapBinary<wchar_t,2>(v164, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 72, &v140, v123);
          std::wstring::operator std::wstring_view(v124, v144, v125);
          v126 = _tlgWrapBinary<wchar_t,2>(v163, *(_QWORD *)v144, *(unsigned int *)v140.Data4);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>>(
            (unsigned int)&v153,
            (unsigned int)&unk_1803E7A50,
            v127,
            v128,
            v126,
            v128,
            v129,
            v130,
            (__int64)&v153);
        }
        if ( v167 )
        {
          v131 = (_QWORD *)std::wstring::operator std::wstring_view(&v166, v175, v113);
          std::wstring::_Assign<wchar_t>((char *)a2 + 168, *v131, v131[1]);
          v133 = (_QWORD *)std::wstring::operator std::wstring_view(&Src, v175, v132);
          std::wstring::_Assign<wchar_t>((char *)a2 + 200, *v133, v133[1]);
        }
      }
      v159 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_2_::operator()(v158);
      std::wstring::_Tidy_deallocate(v178);
      std::wstring::_Tidy_deallocate(&v166);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
      std::wstring::_Tidy_deallocate(pszPathIn);
      std::wstring::_Tidy_deallocate(lpFileName);
      v147 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
      return 0;
    }
  }
  else
  {
    if ( v36 == -2147012894 )
    {
      v90 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpAttempts(v90);
      v91 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpFailures(v91);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)v36,
      dwCreationDispositiona);
    std::wstring::_Tidy_deallocate(v178);
    std::wstring::_Tidy_deallocate(&v166);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v148);
    std::wstring::_Tidy_deallocate(pszPathIn);
    std::wstring::_Tidy_deallocate(lpFileName);
    v147 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v146);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v154);
    return (unsigned int)v36;
  }
}

```

## disassembly

```asm
0x180150580  mov     r11, rsp
0x180150583  push    rbx
0x180150584  push    rsi
0x180150585  push    rdi
0x180150586  push    r12
0x180150588  push    r13
0x18015058a  push    r14
0x18015058c  push    r15
0x18015058e  sub     rsp, 820h
0x180150595  movaps  xmmword ptr [r11-48h], xmm6
0x18015059a  movaps  xmmword ptr [r11-58h], xmm7
0x18015059f  movaps  xmmword ptr [r11-68h], xmm8
0x1801505a4  movaps  xmmword ptr [r11-78h], xmm9
0x1801505a9  mov     rax, cs:__security_cookie
0x1801505b0  xor     rax, rsp
0x1801505b3  mov     [rsp+858h+var_88], rax
0x1801505bb  mov     [rsp+858h+var_748], r9
0x1801505c3  mov     [rsp+858h+var_740], r8
0x1801505cb  mov     rdi, rdx
0x1801505ce  mov     r14, rcx
0x1801505d1  mov     [rsp+858h+var_718], rcx
0x1801505d9  mov     rsi, [rsp+858h+arg_20]
0x1801505e1  mov     [rsp+858h+var_6E8], rsi
0x1801505e9  mov     rax, [rsp+858h+arg_38]
0x1801505f1  mov     [rsp+858h+var_6F8], rax
0x1801505f9  xor     r12d, r12d
0x1801505fc  mov     r15d, r12d
0x1801505ff  mov     [r11-7C8h], r12d
0x180150606  xorps   xmm0, xmm0
0x180150609  movdqu  [rsp+858h+var_738], xmm0
0x180150612  mov     [r11-728h], r12
0x180150619  lea     rax, [r11-738h]
0x180150620  mov     [r11-780h], rax
0x180150627  mov     [rsp+858h+var_778], 1
0x18015062f  mov     rcx, rdx; this
0x180150632  call    ?HasValidPartnerFeature@SettingsEndpoint@Diagnostics@Microsoft@@QEBA_NXZ; Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature(void)
0x180150637  test    al, al
0x180150639  jnz     short loc_180150687
0x18015063b  mov     rcx, [rsp+858h]; this
0x180150643  mov     ebx, 8007007Bh
0x180150648  mov     r9d, ebx; char *
0x18015064b  lea     r8, aOnecoreBaseTel_83; "onecore\\base\\telemetry\\utc\\service"...
0x180150652  mov     edx, 96Fh; void *
0x180150657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015065c  nop
0x18015065d  mov     [rsp+858h+var_778], r12b
0x180150665  lea     rcx, [rsp+858h+var_780]
0x18015066d  call    _Microsoft__Diagnostics__SettingsManager__PerformNamespaceDownload____3____lambda_1___operator__
0x180150672  nop
0x180150673  lea     rcx, [rsp+858h+var_738]
0x18015067b  call    ?_Tidy@?$vector@VAsimovSyntheticEvent@Diagnostics@Microsoft@@V?$allocator@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(void)
0x180150680  mov     eax, ebx
0x180150682  jmp     loc_180152CE2
0x180150687  cmp     [rdi+8], r12w
0x18015068c  jz      short loc_1801506E0
0x18015068e  cmp     [rsi+10h], r12
0x180150692  jnz     short loc_1801506E0
0x180150694  lea     rbx, [r14+228h]
0x18015069b  lea     rcx, [rsp+858h+var_7B8]; retstr
0x1801506a3  call    ?GetMsaTokenClientIdGuid@SettingsManager@Diagnostics@Microsoft@@SA?AU_GUID@@XZ; Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(void)
0x1801506a8  movups  xmm0, xmmword ptr [rax]
0x1801506ab  movdqu  xmmword ptr [rbx+40h], xmm0
0x1801506b0  mov     rdx, rsi
0x1801506b3  mov     rcx, rbx
0x1801506b6  call    ?GetTicket@DeviceTicket@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::DeviceTicket::GetTicket(std::wstring &)
0x1801506bb  mov     rcx, [rsp+858h]; this
0x1801506c3  test    eax, eax
0x1801506c5  jns     short loc_1801506E0
0x1801506c7  mov     r9d, eax; char *
0x1801506ca  lea     r13, aOnecoreBaseTel_83; "onecore\\base\\telemetry\\utc\\service"...
0x1801506d1  mov     r8, r13; unsigned int
0x1801506d4  mov     edx, 979h; void *
0x1801506d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801506de  jmp     short loc_1801506E7
0x1801506e0  lea     r13, aOnecoreBaseTel_83; "onecore\\base\\telemetry\\utc\\service"...
0x1801506e7  mov     rcx, r12
0x1801506ea  xor     eax, eax
0x1801506ec  lock cmpxchg qword ptr cs:xmmword_1804631B0+8, rcx
0x1801506f5  setnz   al
0x1801506f8  mov     [rsp+858h+var_7A4], al
0x1801506ff  cmp     [rdi+5], r12b
0x180150703  jz      short loc_18015071F
0x180150705  test    al, al
0x180150707  jz      short loc_18015071F
0x180150709  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180150710  call    ?GetEnterpriseData@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVEnterpriseData@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData(void)
0x180150715  mov     dl, 1
0x180150717  mov     rcx, rax
0x18015071a  call    ?PopulateAadDeviceToken@EnterpriseData@Diagnostics@Microsoft@@QEAAXVAadDeviceTokenType@23@@Z; Microsoft::Diagnostics::EnterpriseData::PopulateAadDeviceToken(Microsoft::Diagnostics::AadDeviceTokenType)
0x18015071f  lea     rdx, [rsp+858h+lpFileName]
0x180150727  mov     rcx, rdi
0x18015072a  call    ?GetUnexpandedSettingsFilePath@SettingsEndpoint@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath(void)
0x18015072f  nop
0x180150730  xor     r8d, r8d
0x180150733  mov     dl, 1
0x180150735  lea     rcx, [rsp+858h+lpFileName]; lpSrc
0x18015073d  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180150742  movups  xmm0, xmmword ptr cs:off_1803846E0; "SkipMissingSettingsFileDetection"
0x180150749  movdqu  xmmword ptr [rsp+858h+var_7D8], xmm0
0x180150752  lea     rcx, [rsp+858h+var_7D8]
0x18015075a  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x18015075f  test    al, al
0x180150761  jnz     loc_180150BA8
0x180150767  lea     rbx, [rdi+0A8h]
0x18015076e  lea     rdx, [rsp+858h+var_7D8]
0x180150776  mov     rcx, rbx
0x180150779  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18015077e  mov     esi, 7
0x180150783  cmp     [rsp+858h+var_7D8+8], r12
0x18015078b  jz      loc_180150BAD
0x180150791  lea     rcx, [rsp+858h+lpFileName]
0x180150799  cmp     [rsp+858h+var_620], rsi
0x1801507a1  cmova   rcx, [rsp+858h+lpFileName]; lpFileName
0x1801507aa  call    cs:__imp_GetFileAttributesW
0x1801507b0  cmp     eax, 0FFFFFFFFh
0x1801507b3  jnz     loc_180150BAD
0x1801507b9  call    cs:__imp_GetLastError
0x1801507bf  mov     [rsp+858h+var_7C8], eax
0x1801507c6  lea     rdx, [rsp+858h+var_7B8]
0x1801507ce  lea     rcx, qword_1804626F0
0x1801507d5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801507da  mov     r8, [rax+8]
0x1801507de  mov     rdx, [rax]
0x1801507e1  mov     rcx, rbx
0x1801507e4  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801507e9  lea     rdx, aSettingsmanage_10; "SettingsManager_SettingsFileWentMissing"...
0x1801507f0  mov     [rsp+858h+var_7D8], rdx
0x1801507f8  mov     [rsp+858h+var_7D8+8], 29h ; ')'
0x180150804  mov     r8d, 1000000h
0x18015080a  mov     byte ptr [rsp+858h+hTemplateFile], r12b
0x18015080f  mov     byte ptr [rsp+858h+dwFlagsAndAttributes], r12b
0x180150814  mov     byte ptr [rsp+858h+dwCreationDisposition], r12b
0x180150819  mov     r9, 400000000000h
0x180150823  lea     rdx, [rsp+858h+var_7D8]
0x18015082b  lea     rcx, [rsp+858h+var_588]
0x180150833  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x180150838  nop
0x180150839  lea     rcx, [rdi+68h]
0x18015083d  lea     rdx, [rsp+858h+var_770]
0x180150845  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18015084a  lea     r12, aPartner; "Partner"
0x180150851  mov     [rsp+858h+var_7D8], r12
0x180150859  mov     [rsp+858h+var_7D8+8], rsi
0x180150861  lea     r9, [rsp+858h+var_770]
0x180150869  lea     r8, [rsp+858h+var_7D8]
0x180150871  lea     rdx, [rsp+858h+var_120]; int
0x180150879  lea     rcx, [rsp+858h+var_588]; int
0x180150881  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x180150886  lea     rcx, [rdi+88h]
0x18015088d  lea     rdx, [rsp+858h+var_770]
0x180150895  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18015089a  lea     r12, aFeature; "Feature"
0x1801508a1  mov     [rsp+858h+var_7D8], r12
0x1801508a9  mov     [rsp+858h+var_7D8+8], rsi
0x1801508b1  lea     r9, [rsp+858h+var_770]
0x1801508b9  lea     r8, [rsp+858h+var_7D8]
0x1801508c1  lea     rdx, [rsp+858h+var_120]; int
0x1801508c9  lea     rcx, [rsp+858h+var_588]; int
0x1801508d1  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x1801508d6  lea     rcx, [rdi+48h]
0x1801508da  lea     rdx, [rsp+858h+var_770]
0x1801508e2  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801508e7  lea     r14, aVersion_0; "Version"
0x1801508ee  mov     [rsp+858h+var_7D8], r14
0x1801508f6  mov     [rsp+858h+var_7D8+8], rsi
0x1801508fe  lea     r9, [rsp+858h+var_770]
0x180150906  lea     r8, [rsp+858h+var_7D8]
0x18015090e  lea     rdx, [rsp+858h+var_120]; int
0x180150916  lea     rcx, [rsp+858h+var_588]; int
0x18015091e  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x180150923  lea     rax, aGetfileattribu; "GetFileAttributesLastError"
0x18015092a  mov     [rsp+858h+var_7D8], rax
0x180150932  lea     r14d, [rsi+13h]
0x180150936  mov     [rsp+858h+var_7D8+8], r14
0x18015093e  lea     r9, [rsp+858h+var_7C8]
0x180150946  lea     r8, [rsp+858h+var_7D8]
0x18015094e  lea     rdx, [rsp+858h+var_120]
0x180150956  lea     rcx, [rsp+858h+var_588]
0x18015095e  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x180150963  lea     rax, aDestinationfil; "DestinationFilePath"
0x18015096a  mov     [rsp+858h+var_7D8], rax
0x180150972  lea     ebx, [rsi+0Ch]
0x180150975  mov     [rsp+858h+var_7D8+8], rbx
0x18015097d  lea     r9, [rsp+858h+lpFileName]
0x180150985  lea     r8, [rsp+858h+var_7D8]
0x18015098d  lea     rdx, [rsp+858h+var_120]
0x180150995  lea     rcx, [rsp+858h+var_588]
0x18015099d  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1801509a2  lea     rdx, [rdi+28h]
0x1801509a6  lea     rcx, [rsp+858h+var_5D8]
0x1801509ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801509b3  lea     r15d, [rsi-3]
0x1801509b7  mov     [rsp+858h+var_7C8], r15d
0x1801509bf  lea     rax, aLastfilewritte_0; "LastFileWrittenPath"
0x1801509c6  mov     [rsp+858h+var_7D8], rax
0x1801509ce  mov     [rsp+858h+var_7D8+8], rbx
0x1801509d6  lea     r9, [rsp+858h+var_5D8]
0x1801509de  lea     r8, [rsp+858h+var_7D8]
0x1801509e6  lea     rdx, [rsp+858h+var_120]
0x1801509ee  lea     rcx, [rsp+858h+var_588]
0x1801509f6  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1801509fb  nop
0x1801509fc  lea     rcx, [rsp+858h+var_5D8]
0x180150a04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180150a09  mov     al, [rdi]
0x180150a0b  mov     [rsp+858h+var_7A3], al
0x180150a12  lea     rax, aLastfilewritte; "LastFileWrittenWasThisEpoch"
0x180150a19  mov     [rsp+858h+var_7D8], rax
0x180150a21  mov     [rsp+858h+var_7D8+8], 1Bh
0x180150a2d  lea     r9, [rsp+858h+var_7A3]
0x180150a35  lea     r8, [rsp+858h+var_7D8]
0x180150a3d  lea     rdx, [rsp+858h+var_120]; int
0x180150a45  lea     rcx, [rsp+858h+var_588]; int
0x180150a4d  call    ??$AddField@_N@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<bool>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,bool const &)
0x180150a52  mov     rax, [rdi+18h]
0x180150a56  mov     [rsp+858h+var_758], rax
0x180150a5e  lea     rax, aLastdownloadti; "LastDownloadTime"
0x180150a65  mov     [rsp+858h+var_7D8], rax
0x180150a6d  mov     [rsp+858h+var_7D8+8], 10h
0x180150a79  lea     r9, [rsp+858h+var_758]
0x180150a81  lea     r8, [rsp+858h+var_7D8]
0x180150a89  lea     rdx, [rsp+858h+var_120]; int
0x180150a91  lea     rcx, [rsp+858h+var_588]; int
0x180150a99  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x180150a9e  mov     r12, [rsp+858h+var_748]
0x180150aa6  mov     rcx, [r12]
0x180150aaa  mov     rbx, 346DC5D63886594Bh
0x180150ab4  cmp     [rdi+18h], rcx
0x180150ab8  jbe     short loc_180150ABE
0x180150aba  xor     edx, edx
0x180150abc  jmp     short loc_180150ACC
0x180150abe  sub     rcx, [rdi+18h]
0x180150ac2  mov     rax, rbx
0x180150ac5  mul     rcx
0x180150ac8  shr     rdx, 0Bh
0x180150acc  mov     [rsp+858h+var_758], rdx
0x180150ad4  lea     rax, aLastdownloadde; "LastDownloadDeltaMillis"
0x180150adb  mov     [rsp+858h+var_7D8], rax
0x180150ae3  mov     [rsp+858h+var_7D8+8], 17h
0x180150aef  lea     r9, [rsp+858h+var_758]
0x180150af7  lea     r8, [rsp+858h+var_7D8]
0x180150aff  lea     rdx, [rsp+858h+var_120]; int
0x180150b07  lea     rcx, [rsp+858h+var_588]; int
0x180150b0f  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x180150b14  mov     rcx, [r12]
0x180150b18  cmp     [rdi+20h], rcx
0x180150b1c  jbe     short loc_180150B26
0x180150b1e  xor     r12d, r12d
0x180150b21  mov     edx, r12d
0x180150b24  jmp     short loc_180150B37
0x180150b26  sub     rcx, [rdi+20h]
0x180150b2a  mov     rax, rbx
0x180150b2d  mul     rcx
0x180150b30  shr     rdx, 0Bh
0x180150b34  xor     r12d, r12d
0x180150b37  mov     [rsp+858h+var_758], rdx
0x180150b3f  lea     rax, aLastfilewritte_2; "LastFileWrittenDeltaMillis"
0x180150b46  mov     [rsp+858h+var_7D8], rax
0x180150b4e  mov     [rsp+858h+var_7D8+8], r14
0x180150b56  lea     r9, [rsp+858h+var_758]
0x180150b5e  lea     r8, [rsp+858h+var_7D8]
0x180150b66  lea     rdx, [rsp+858h+var_120]; int
0x180150b6e  lea     rcx, [rsp+858h+var_588]; int
0x180150b76  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x180150b7b  lea     rdx, [rsp+858h+var_588]
0x180150b83  lea     rcx, [rsp+858h+var_738]
0x180150b8b  call    ??$_Emplace_one_at_back@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@?$vector@VAsimovSyntheticEvent@Diagnostics@Microsoft@@V?$allocator@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@@std@@AEAAAEAVAsimovSyntheticEvent@Diagnostics@Microsoft@@$$QEAV234@@Z; std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(Microsoft::Diagnostics::AsimovSyntheticEvent &&)
0x180150b90  nop
0x180150b91  lea     rcx, [rsp+858h+var_588]; this
0x180150b99  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x180150b9e  mov     r14, [rsp+858h+var_718]
0x180150ba6  jmp     short loc_180150BAD
0x180150ba8  mov     esi, 7
0x180150bad  lea     r8, aNew_0; ".new"
0x180150bb4  lea     rdx, [rsp+858h+lpFileName]
0x180150bbc  lea     rcx, [rsp+858h+pszPathIn]
0x180150bc4  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180150bc9  nop
0x180150bca  mov     byte ptr [rsp+858h+var_770], r12b
0x180150bd2  mov     [rsp+858h+var_768], 0FFFFFFFFFFFFFFFFh
0x180150bde  xor     r8d, r8d
0x180150be1  mov     rdx, [rsp+858h+var_608]
0x180150be9  lea     rcx, [rsp+858h+pszPathOut]
0x180150bf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180150bf6  nop
0x180150bf7  lea     r8, [rsp+858h+pszPathIn]
0x180150bff  cmp     [rsp+858h+var_600], rsi
0x180150c07  cmova   r8, [rsp+858h+pszPathIn]; pszPathIn
0x180150c10  mov     rdx, [rsp+858h+var_648]
0x180150c18  lea     rcx, [rsp+858h+pszPathOut]
0x180150c20  cmp     [rsp+858h+var_640], rsi
0x180150c28  cmova   rcx, [rsp+858h+pszPathOut]; pszPathOut
0x180150c31  inc     rdx; cchPathOut
0x180150c34  xor     r9d, r9d; dwFlags
0x180150c37  call    cs:__imp_PathCchCanonicalizeEx
0x180150c3d  mov     ebx, eax
0x180150c3f  test    eax, eax
0x180150c41  jns     short loc_180150CBE
0x180150c43  mov     rcx, [rsp+858h]; this
0x180150c4b  mov     r9d, eax; char *
  ... truncated ...
```
