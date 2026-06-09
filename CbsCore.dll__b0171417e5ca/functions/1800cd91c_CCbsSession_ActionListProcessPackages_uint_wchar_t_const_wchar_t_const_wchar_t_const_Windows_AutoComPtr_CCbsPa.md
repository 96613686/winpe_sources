# CCbsSession::ActionListProcessPackages(uint,wchar_t const *,wchar_t const *,wchar_t const *,Windows::AutoComPtr<CCbsPackage> *)

- ea: `0x1800cd91c`
- end: `0x1800cf0ba`
- name: `?ActionListProcessPackages@CCbsSession@@AEAAJIPEB_W00PEAV?$AutoComPtr@VCCbsPackage@@@Windows@@@Z`
- size: `6046`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801d9584`

## callees

- `0x18000b46c`
- `0x18000e780`
- `0x180010cc0`
- `0x180013250`
- `0x18001387c`
- `0x1800138b8`
- `0x180015420`
- `0x1800194bc`
- `0x180019bdc`
- `0x180019c10`
- `0x180023f30`
- `0x1800261e0`
- `0x180026864`
- `0x18002a448`
- `0x18002c34c`
- `0x18002e280`
- `0x180043adc`
- `0x180045c24`
- `0x18004f454`
- `0x180055fc8`
- `0x180056e00`
- `0x180057c28`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad1f0`
- `0x1800bd218`
- `0x1800cd91c`
- `0x1800d1efc`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1801026fc`
- `0x180113730`
- `0x1801aead0`
- `0x1801c322c`
- `0x1801c9830`
- `0x1801c98ec`
- `0x1801c99cc`
- `0x1801c9d88`
- `0x1801cc018`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdfcd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cdfcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ce7df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ce7df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce795`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce795`

## string_xrefs

- `0x1800cea7a`: `Failed to write file: {}`
- `0x1800ceb61`: `Failed to open payload file: {}`
- `0x1800cdcfa`: `Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first`
- `0x1800ce94a`: `Failed to create package: {}`
- `0x1800cedea`: `Failed to allocate memory for manifest blob`
- `0x1800ced08`: `Failed to get directory`
- `0x1800cec3f`: `Failed to create directory {}`
- `0x1800cf00a`: `No entry in the ActionList: {} matched the FilePath: {}`
- `0x1800cdd8b`: `Failed to process RemoveFeature Action`
- `0x1800cdea6`: `Failed to process InstallFeature Action`
- `0x1800cef37`: `Evaluation of package path: {} for missing files is not allowed except for Express packages`

## pseudocode

```c
__int64 __fastcall CCbsSession::ActionListProcessPackages(
        CCbsSession *this,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  CCbsSession *v6; // r14
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rbx
  char v14; // r9
  char v15; // r10
  char v16; // r11
  __int64 i; // rax
  signed int v18; // edi
  __int64 v19; // rdx
  int IsSmartPended; // eax
  __int64 v21; // rbx
  __int64 j; // rbx
  __int64 k; // rbx
  __int64 m; // rbx
  __int64 n; // rdi
  int v26; // r10d
  int v27; // esi
  int v28; // eax
  int v29; // eax
  __int128 *v30; // rbx
  __int64 v31; // r14
  int WindowsUpdatePackage; // esi
  wchar_t *v33; // r14
  __int64 v34; // rdx
  unsigned __int64 v35; // r15
  __int64 v36; // rsi
  __int64 v37; // rdx
  int v38; // edx
  __int64 v39; // rbx
  __int64 v40; // r14
  __int64 v41; // rax
  __int64 v42; // rdx
  unsigned __int64 v43; // r14
  __int64 *v44; // rbx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rsi
  unsigned __int64 v47; // r12
  __int64 v48; // rcx
  bool v49; // zf
  wchar_t *v50; // rax
  unsigned int v51; // esi
  __int64 v52; // r15
  const wchar_t *v53; // rax
  __int64 v54; // r14
  __int64 ii; // rbx
  __int64 v56; // rsi
  int v57; // eax
  __int64 v58; // rdx
  wchar_t *v59; // rbx
  int v60; // r14d
  LPCVOID v61; // r15
  const WCHAR *v62; // rbx
  wchar_t *v63; // r14
  int Directory; // eax
  HANDLE FileW; // rax
  __int64 v66; // rdx
  const wchar_t *v67; // rax
  signed int LastError; // edi
  unsigned int v69; // eax
  __int64 v70; // rdx
  unsigned int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // r9
  __int64 v75; // r9
  void *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 v78; // [rsp+70h] [rbp-90h] BYREF
  char v79[8]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v82; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v83[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v84[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v85[4]; // [rsp+B0h] [rbp-50h] BYREF
  int *v86; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v87; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v88; // [rsp+D0h] [rbp-30h]
  int *v89; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v90; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-10h]
  wchar_t **v92; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v93; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v94; // [rsp+108h] [rbp+8h] BYREF
  __int64 v95; // [rsp+110h] [rbp+10h] BYREF
  __int64 v96; // [rsp+118h] [rbp+18h] BYREF
  __int128 v97; // [rsp+120h] [rbp+20h] BYREF
  __int64 v98; // [rsp+130h] [rbp+30h]
  __int128 v99; // [rsp+138h] [rbp+38h]
  __int64 v100; // [rsp+148h] [rbp+48h]
  __int64 v101; // [rsp+150h] [rbp+50h]
  __int128 v102; // [rsp+158h] [rbp+58h]
  __int64 v103; // [rsp+168h] [rbp+68h]
  __int128 v104; // [rsp+170h] [rbp+70h]
  __int64 v105; // [rsp+180h] [rbp+80h]
  __int128 v106; // [rsp+188h] [rbp+88h]
  __int64 v107; // [rsp+198h] [rbp+98h]
  __int64 v108; // [rsp+1A0h] [rbp+A0h]
  __int64 v109; // [rsp+1A8h] [rbp+A8h]
  int v110; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t *v111; // [rsp+1B8h] [rbp+B8h] BYREF
  HANDLE hFile; // [rsp+1C0h] [rbp+C0h] BYREF
  int v113; // [rsp+1C8h] [rbp+C8h] BYREF
  int v114; // [rsp+1CCh] [rbp+CCh] BYREF
  int v115; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+1D4h] [rbp+D4h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v118[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v119[24]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v120; // [rsp+218h] [rbp+118h]
  __int64 v121; // [rsp+228h] [rbp+128h]
  __int128 v122; // [rsp+240h] [rbp+140h] BYREF
  __int128 v123; // [rsp+250h] [rbp+150h] BYREF
  __int128 v124; // [rsp+260h] [rbp+160h] BYREF
  __int64 v125; // [rsp+270h] [rbp+170h]
  _BYTE v126[24]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int64 v127; // [rsp+298h] [rbp+198h]
  __int64 *v128; // [rsp+2A8h] [rbp+1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  *(_QWORD *)v84 = a6;
  v6 = this;
  v95 = a5;
  v88 = a4;
  v91 = 0;
  v110 = a2;
  v86 = (int *)this;
  v96 = a3;
  v118[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
  v90 = 0;
  v93 = 0;
  v118[1] = 0;
  v118[2] = 0;
  v114 = 0;
  v7 = ActionListParser::ReadActionList(a3, v118, &v93, &v90);
  v9 = v7;
  if ( v7 < 0 )
  {
    LODWORD(hFile) = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to load actions from {}",
        (__int64)&v96);
      *(_QWORD *)v85 = &hFile;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v10 = 2678;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)v9,
      (int)dwCreationDisposition);
    goto LABEL_241;
  }
  v11 = v93;
  v12 = *(_QWORD *)(v93 + 152);
  if ( !*(_QWORD *)(v12 + 64) )
  {
    v9 = -2146498222;
    v113 = -2146498222;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"ActionList: No package to process in actionList, this is not expected.");
      *(_QWORD *)v85 = &v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v10 = 2683;
    goto LABEL_9;
  }
  v13 = *(_QWORD *)(v12 + 56);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  for ( i = v13; i; i = *(_QWORD *)(i + 296) )
  {
    v8 = (unsigned int)(*(_DWORD *)(i + 140) - 2);
    if ( *(_DWORD *)(i + 140) == 2
      || (v8 = (unsigned int)(*(_DWORD *)(i + 140) - 3), *(_DWORD *)(i + 140) == 3)
      || (v8 = (unsigned int)(*(_DWORD *)(i + 140) - 4), *(_DWORD *)(i + 140) == 4) )
    {
LABEL_23:
      v14 = 1;
      continue;
    }
    v8 = (unsigned int)(*(_DWORD *)(i + 140) - 5);
    if ( *(_DWORD *)(i + 140) != 5 )
    {
      v8 = (unsigned int)(*(_DWORD *)(i + 140) - 6);
      if ( *(_DWORD *)(i + 140) != 6 )
      {
        v8 = (unsigned int)(*(_DWORD *)(i + 140) - 9);
        if ( *(_DWORD *)(i + 140) == 9 )
          goto LABEL_23;
        if ( *(_DWORD *)(i + 140) != 13 )
          continue;
      }
    }
    v15 = 1;
    if ( *(_DWORD *)(i + 144) == 2 || *(_QWORD *)(i + 264) && *(_DWORD *)(*(_QWORD *)(i + 256) + 48LL) == 2 )
      v16 = 1;
  }
  if ( v14 )
  {
    if ( v15 && v16 )
    {
      while ( v13 )
      {
        v94 = 0;
        if ( *(_DWORD *)(v13 + 140) == 2
          || *(_DWORD *)(v13 + 140) == 3
          || *(_DWORD *)(v13 + 140) == 4
          || *(_DWORD *)(v13 + 140) == 9 )
        {
          v18 = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v118,
                  (const struct _LUTF8_STRING *)(v13 + 200),
                  &v94);
          if ( v18 < 0 )
          {
            v19 = 2739;
            goto LABEL_41;
          }
          if ( CCbsStringArray::Find(
                 (CCbsSession *)((char *)v6 + 1888),
                 v94,
                 (int (*)(wchar_t *const *, wchar_t *const *))StringArrayIsEqualCaseInsensitive) == 0xFFFFFFFF )
          {
            v18 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)v6 + 1888), v94);
            if ( v18 < 0 )
            {
              v113 = v18;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed adding capability to array: {}",
                  (__int64)&v94);
                v87 = (wchar_t *)&v113;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v87);
              }
              v19 = 2746;
              goto LABEL_41;
            }
          }
        }
        v13 = *(_QWORD *)(v13 + 296);
      }
    }
    LODWORD(hFile) = 0;
    IsSmartPended = CCbsSession::LCUInstallIsSmartPended(v6, (int *const)&hFile);
    v9 = IsSmartPended;
    if ( IsSmartPended < 0 )
    {
      v115 = IsSmartPended;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting LCU smart pended state");
        v89 = &v115;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v89);
      }
      v10 = 2773;
      goto LABEL_9;
    }
    if ( (_DWORD)hFile )
    {
      v9 = -2146498554;
      v113 = -2146498554;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Attempted to install a FOD or LP with a postponed LCU instal"
                                                            "l pending, a reboot must be performed first");
        *(_QWORD *)v85 = &v113;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v85);
      }
      v10 = 2779;
      goto LABEL_9;
    }
    v11 = v93;
  }
  v21 = *(_QWORD *)(v11 + 136);
  if ( v21 )
  {
    for ( j = *(_QWORD *)(v21 + 16); j; j = *(_QWORD *)(j + 72) )
    {
      v18 = CCbsSession::AddFeatureToModify(v6, j, 0);
      if ( v18 < 0 )
      {
        NumberOfBytesWritten = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process RemoveFeature Action");
          *(_QWORD *)nNumberOfBytesToWrite = &NumberOfBytesWritten;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)nNumberOfBytesToWrite);
        }
        v19 = 2791;
        goto LABEL_41;
      }
    }
    for ( k = *(_QWORD *)(*(_QWORD *)(v93 + 136) + 32LL); k; k = *(_QWORD *)(k + 72) )
    {
      v18 = CCbsSession::AddFeatureToModify(v6, k, 64);
      if ( v18 < 0 )
      {
        LODWORD(v111) = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process DisableFeature Action");
          v92 = &v111;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v92);
        }
        v19 = 2796;
        goto LABEL_41;
      }
    }
    for ( m = **(_QWORD **)(v93 + 136); ; m = *(_QWORD *)(m + 72) )
    {
      if ( !m )
        goto LABEL_73;
      v18 = CCbsSession::AddFeatureToModify(v6, m, 112);
      if ( v18 < 0 )
        break;
    }
    v110 = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process InstallFeature Action");
      v86 = &v110;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v86);
    }
    v19 = 2801;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)(unsigned int)v18,
      (int)dwCreationDisposition);
    v9 = v18;
    goto LABEL_241;
  }
LABEL_73:
  for ( n = *(_QWORD *)(v12 + 56); n; n = *(_QWORD *)(n + 296) )
  {
    v82 = 0;
    lpBuffer = 0;
    v111 = 0;
    v78 = 0;
    CCbsArray<MultiplePayloadsforPackage>::CCbsArray<MultiplePayloadsforPackage>(v119, v8);
    if ( !v26 || *(_DWORD *)(n + 136) != 4 )
    {
      v27 = *(_DWORD *)(n + 144);
      if ( v26 )
        v27 = *(_DWORD *)(*(_QWORD *)(n + 256) + 48LL);
      v28 = DuplicateParserString(
              (struct Windows::Rtl::IPoolAllocator *)v118,
              (const struct _LUTF8_STRING *)(n + 40),
              (wchar_t **)&lpBuffer);
      v9 = v28;
      if ( v28 < 0 )
      {
        v37 = 2835;
LABEL_233:
        v75 = (unsigned int)v28;
LABEL_234:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v75,
          (int)dwCreationDisposition);
LABEL_235:
        CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
        goto LABEL_241;
      }
      if ( !v27 )
      {
        lpFileName = 0;
        v29 = SczAllocCombinePath2Sz(&lpFileName, v88, lpBuffer);
        v9 = v29;
        if ( v29 < 0 )
        {
          v66 = 2840;
          goto LABEL_166;
        }
        v29 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)v6 + 1952), lpFileName);
        v9 = v29;
        if ( v29 < 0 )
        {
          v66 = 2842;
LABEL_166:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v66,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v29,
            (int)dwCreationDisposition);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
          goto LABEL_235;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      }
      v115 = v110 & 0x40;
      if ( (v110 & 0x40) != 0 || !(unsigned int)_o__wcsicmp(lpBuffer, v95) )
      {
        if ( v27 != 2 )
        {
          v9 = -2146498557;
          v110 = -2146498557;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Evaluation of package path: {} for missing files is not allowed except for Express packages",
              (__int64)&v95);
            *(_QWORD *)v83 = &v110;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v83);
          }
          v75 = 2148468739LL;
          v37 = 2861;
          goto LABEL_234;
        }
        v108 = 0;
        v98 = 0;
        v100 = 0;
        v97 = 0;
        v101 = 0;
        v99 = 0;
        v103 = 0;
        v102 = 0;
        v105 = 0;
        v104 = 0;
        v107 = 0;
        v106 = 0;
        v109 = 0;
        if ( *(_QWORD *)(n + 264) )
        {
          v30 = *(__int128 **)(n + 256);
        }
        else
        {
          v30 = &v97;
          BYTE3(v109) = *(_BYTE *)(n + 305);
          v102 = *(_OWORD *)(n + 40);
          v103 = *(_QWORD *)(n + 56);
          BYTE4(v109) = *(_BYTE *)(n + 307);
          v104 = *(_OWORD *)(n + 88);
          v105 = *(_QWORD *)(n + 104);
          BYTE5(v109) = *(_BYTE *)(n + 308);
          v106 = *(_OWORD *)(n + 112);
          v107 = *(_QWORD *)(n + 128);
        }
        v31 = v88;
        while ( v30 )
        {
          v125 = 0;
          v122 = 0;
          v123 = 0;
          v124 = 0;
          WindowsUpdatePackage = DuplicateParserString(
                                   (struct Windows::Rtl::IPoolAllocator *)v118,
                                   (const struct _LUTF8_STRING *)(n + 40),
                                   (wchar_t **)&lpBuffer);
          if ( WindowsUpdatePackage < 0 )
          {
            v34 = 2881;
            goto LABEL_177;
          }
          WindowsUpdatePackage = SczAllocFromSz((char *)&v122 + 8, lpBuffer);
          if ( WindowsUpdatePackage < 0 )
          {
            v34 = 2883;
            goto LABEL_177;
          }
          if ( *((_BYTE *)v30 + 140) )
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v118,
                                     (const struct _LUTF8_STRING *)(v30 + 5),
                                     &v82);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2894;
              goto LABEL_177;
            }
            v33 = v82;
            WindowsUpdatePackage = SczAllocFormatted(&v78, L"%ws%ws", v88, v82);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2895;
LABEL_177:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v34,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)WindowsUpdatePackage,
                (int)dwCreationDisposition);
              MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v122);
              goto LABEL_178;
            }
          }
          else
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v118,
                                     (const struct _LUTF8_STRING *)(n + 40),
                                     &v82);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2899;
              goto LABEL_177;
            }
            v33 = v82;
            WindowsUpdatePackage = SczAllocFormatted(&v78, L"%ws%ws", v88, v82);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2900;
              goto LABEL_177;
            }
          }
          WindowsUpdatePackage = SczAllocFromSz(&v122, v33);
          if ( WindowsUpdatePackage < 0 )
          {
            v34 = 2903;
            goto LABEL_177;
          }
          v31 = v88;
          WindowsUpdatePackage = SczAllocFormatted(&v123, L"%ws%ws", v88, (_QWORD)v122);
          if ( WindowsUpdatePackage < 0 )
          {
            v34 = 2909;
            goto LABEL_177;
          }
          if ( *((_BYTE *)v30 + 141) )
          {
            WindowsUpdatePackage = DuplicateParserString(
                                     (struct Windows::Rtl::IPoolAllocator *)v118,
                                     (const struct _LUTF8_STRING *)((char *)v30 + 104),
                                     &v111);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2913;
              goto LABEL_177;
            }
            WindowsUpdatePackage = SczAllocFormatted((char *)&v124 + 8, L"%ws%ws", v31, v111);
            if ( WindowsUpdatePackage < 0 )
            {
              v34 = 2919;
              goto LABEL_177;
            }
            *(_QWORD *)v85 = *((_QWORD *)&v124 + 1);
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                1,
                1,
                (__int64)"ActionList: Using TurboContainer: {}",
                (__int64)v85);
          }
          CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::SwapOntoBack(v119, &v122);
          MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v122);
          v30 = (__int128 *)*((_QWORD *)v30 + 16);
        }
        v35 = 0;
        if ( *(_BYTE *)(n + 308) )
        {
          v28 = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v118,
                  (const struct _LUTF8_STRING *)(n + 112),
                  &v111);
          v9 = v28;
          if ( v28 < 0 )
          {
            v37 = 2931;
            goto LABEL_233;
          }
          v36 = (__int64)v86;
          v28 = SczAllocFormatted(v86 + 582, L"%ws%ws", v31, v111);
          v9 = v28;
          if ( v28 < 0 )
          {
            v37 = 2933;
            goto LABEL_233;
          }
        }
        else
        {
          v36 = (__int64)v86;
        }
        CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v126);
        v39 = v121;
        v40 = v121 + 56 * v120;
        while ( v39 != v40 )
        {
          v41 = *(_QWORD *)(v39 + 16);
          v89 = 0;
          *(_QWORD *)v85 = v41;
          if ( LogAdapter::g_Logger )
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              1,
              1,
              (__int64)"ActionList: Checking package: {} for missing files",
              (__int64)v85);
          Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v89);
          v42 = *(_QWORD *)(v36 + 1128);
          dwCreationDisposition = v85;
          *(GUID *)v85 = GUID_NULL;
          WindowsUpdatePackage = CCbsSession::CreateWindowsUpdatePackage(v36, v42, 0, 0);
          if ( WindowsUpdatePackage < 0 )
          {
            v110 = WindowsUpdatePackage;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v84 = v78;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to create package: {}",
                (__int64)v84);
              *(_QWORD *)v85 = &v110;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v85);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB8B,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)WindowsUpdatePackage,
              (int)dwCreationDisposition);
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v89);
            goto LABEL_183;
          }
          *(_QWORD *)v85 = v89;
          CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add(v126, v85);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v89);
          v36 = (__int64)v86;
          v39 += 56;
        }
        v43 = v127;
        v44 = v128;
        if ( v127 > 1 )
        {
          v45 = v127 - 1;
          do
          {
            v46 = v35 + 1;
            v47 = v35;
            v35 = v46;
            if ( v46 < v43 )
            {
              do
              {
                if ( (int)PackageVersionComparator(v44[v47], v44[v46]) > 0 )
                {
                  v48 = v44[v47];
                  v44[v47] = v44[v46];
                  v44[v46] = v48;
                }
                ++v46;
              }
              while ( v46 < v43 );
              v45 = v43 - 1;
            }
          }
          while ( v35 < v45 );
        }
        v49 = *(_DWORD *)(n + 136) == 5;
        v50 = (wchar_t *)&v44[v43];
        v51 = 257;
        v87 = v50;
        if ( !v49 )
          v51 = 1;
        LODWORD(v111) = v51;
        while ( v44 != (__int64 *)v50 )
        {
          v52 = *v44;
          if ( v43 > 1 )
          {
            v53 = &qword_1802EB518;
            if ( *(_QWORD *)(v52 + 120) )
              v53 = *(const wchar_t **)(v52 + 120);
            *(_QWORD *)v85 = v53;
            if ( LogAdapter::g_Logger )
            {
              LOBYTE(v38) = 1;
              LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v38,
                1,
                (unsigned int)"MFL: Adding payload package index: {} package: {} for MFL generation",
                (__int64)&v114,
                (__int64)v85);
            }
          }
          ++v114;
          WindowsUpdatePackage = CCbsPackage::InitiateChanges(
                                   v52,
                                   (__int64)v86,
                                   *((void **)v86 + 141),
                                   v51,
                                   112,
                                   0,
                                   0,
                                   0);
          if ( WindowsUpdatePackage < 0 )
          {
            v113 = WindowsUpdatePackage;
            if ( LogAdapter::g_Logger )
            {
              v67 = &qword_1802EB518;
              if ( *(_QWORD *)(v52 + 120) )
                v67 = *(const wchar_t **)(v52 + 120);
              *(_QWORD *)v84 = v67;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed Initiating changes for package: {}",
                (__int64)v84);
              *(_QWORD *)v83 = &v113;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v83);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBAF,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)WindowsUpdatePackage,
              (int)dwCreationDisposition);
LABEL_183:
            CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
LABEL_178:
            CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
            v9 = WindowsUpdatePackage;
            goto LABEL_241;
          }
          if ( !**(_QWORD **)v84 )
            Windows::AutoComPtr<CCbsUpdate>::operator=(*(_QWORD *)v84, v52);
          v51 = (unsigned int)v111;
          ++v44;
          v50 = v87;
        }
        v54 = *((_QWORD *)v86 + 296);
        *(_QWORD *)v85 = v54;
        if ( v54 )
        {
          for ( ii = **(_QWORD **)(v93 + 112); ii; ii = *(_QWORD *)(ii + 256) )
          {
            v79[0] = 0;
            if ( (int)Windows::StringUtil::Rtl::AreStringsEqualByOrdinalCaseInvariant<_LUTF8_STRING,_LUTF8_STRING>(
                        n + 176,
                        ii + 80,
                        v79) >= 0
              && v79[0] )
            {
              v56 = *(_QWORD *)(ii + 240);
              while ( 1 )
              {
                if ( !v56 )
                  goto LABEL_162;
                lpBuffer = 0;
                *(_QWORD *)nNumberOfBytesToWrite = 0;
                hFile = 0;
                v92 = 0;
                v87 = 0;
                lpFileName = 0;
                v82 = 0;
                v111 = 0;
                v57 = DuplicateParserString(
                        (struct Windows::Rtl::IPoolAllocator *)v118,
                        (const struct _LUTF8_STRING *)(v56 + 376),
                        (wchar_t **)&hFile);
                v9 = v57;
                if ( v57 < 0 )
                {
                  v73 = 3027;
                  goto LABEL_214;
                }
                v57 = DuplicateParserString(
                        (struct Windows::Rtl::IPoolAllocator *)v118,
                        (const struct _LUTF8_STRING *)(v56 + 72),
                        &v87);
                v9 = v57;
                if ( v57 < 0 )
                {
                  v73 = 3029;
                  goto LABEL_214;
                }
                v57 = SczAllocFormatted(&v82, L"%ws%ws", v88, v87);
                v9 = v57;
                if ( v57 < 0 )
                  break;
                v58 = FileFromPath(hFile);
                v59 = v82;
                v92 = (wchar_t **)v58;
                v87 = v82;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    1,
                    (__int64)"Extracting {} from container {} ....",
                    (__int64)&v92,
                    (__int64)&v87);
                  v58 = (__int64)v92;
                }
                v60 = (*(__int64 (__fastcall **)(__int64, __int64, DWORD *, wchar_t *))(*(_QWORD *)v54 + 16LL))(
                        v54,
                        v58,
                        nNumberOfBytesToWrite,
                        v59);
                if ( v60 < 0 )
                {
                  v110 = v60;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (__int64)"Failed to get CIX file size: {}",
                      (__int64)&v92);
                    *(_QWORD *)v83 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v83);
                  }
                  v72 = 3039;
LABEL_225:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v72,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)v60,
                    (int)dwCreationDisposition);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
                  v9 = v60;
LABEL_241:
                  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v118);
                  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v90);
                  return v9;
                }
                Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(
                  &lpBuffer,
                  *(_QWORD *)nNumberOfBytesToWrite);
                v61 = lpBuffer;
                if ( !lpBuffer )
                {
                  v9 = -2147024882;
                  v110 = -2147024882;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate memory for manifest blob");
                    *(_QWORD *)v83 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v83);
                  }
                  v74 = 2147942414LL;
                  v73 = 3042;
                  goto LABEL_215;
                }
                dwCreationDisposition = nNumberOfBytesToWrite;
                v9 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, LPCVOID, _QWORD))(**(_QWORD **)v85 + 8LL))(
                       *(_QWORD *)v85,
                       v92,
                       lpBuffer,
                       *(_QWORD *)nNumberOfBytesToWrite);
                if ( (v9 & 0x80000000) != 0 )
                {
                  v110 = v9;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (__int64)"Failed to get blob from turbocontainer: {}",
                      (__int64)&v92);
                    *(_QWORD *)v83 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v83);
                  }
                  v74 = v9;
                  v73 = 3046;
                  goto LABEL_215;
                }
                v57 = SczAllocFormatted(&lpFileName, L"%wsmetadata\\%ws", v88, hFile);
                v9 = v57;
                if ( v57 < 0 )
                {
                  v73 = 3048;
LABEL_214:
                  v74 = (unsigned int)v57;
LABEL_215:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v73,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)v74,
                    (int)dwCreationDisposition);
                  goto LABEL_197;
                }
                v62 = lpFileName;
                v60 = DirectoryFromPath((wchar_t *)lpFileName);
                if ( v60 < 0 )
                {
                  v110 = v60;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get directory");
                    *(_QWORD *)v83 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v83);
                  }
                  v72 = 3050;
                  goto LABEL_225;
                }
                v63 = v111;
                Directory = RecursivelyCreateDirectory(v111, 0);
                LODWORD(hFile) = Directory;
                if ( Directory < 0 )
                {
                  v110 = Directory;
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v83 = v63;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (__int64)"Failed to create directory {}",
                      (__int64)v83);
                    *(_QWORD *)v84 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v84);
                    Directory = (int)hFile;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xBEE,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)Directory,
                    (int)dwCreationDisposition);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
                  v9 = (unsigned int)hFile;
                  goto LABEL_241;
                }
                hFile = 0;
                NumberOfBytesWritten = 0;
                FileW = CreateFileW(v62, 0x40000000u, 0, 0, 2u, 0x80u, 0);
                Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
                  &hFile,
                  FileW);
                if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                {
                  LastError = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v83 = v62;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (__int64)"Failed to open payload file: {}",
                      (__int64)v83);
                    if ( LastError > 0 )
                      v71 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v71 = LastError;
                    v110 = v71;
                    *(_QWORD *)v84 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {0}",
                      (__int64)v84);
                  }
                  if ( LastError )
                  {
                    v70 = 3061;
LABEL_196:
                    v9 = wil::details::in1diag3::Return_Win32(
                           retaddr,
                           (void *)v70,
                           (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                           (const char *)(unsigned int)LastError,
                           (unsigned int)dwCreationDisposition);
                    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
LABEL_197:
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
                    goto LABEL_235;
                  }
LABEL_205:
                  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
LABEL_206:
                  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
                  v9 = 0;
                  goto LABEL_241;
                }
                if ( !WriteFile(hFile, v61, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
                {
                  LastError = GetLastError();
                  if ( LogAdapter::g_Logger )
                  {
                    *(_QWORD *)v83 = v62;
                    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (__int64)"Failed to write file: {}",
                      (__int64)v83);
                    if ( LastError > 0 )
                      v69 = (unsigned __int16)LastError | 0x80070000;
                    else
                      v69 = LastError;
                    v110 = v69;
                    *(_QWORD *)v84 = &v110;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {0}",
                      (__int64)v84);
                  }
                  if ( LastError )
                  {
                    v70 = 3066;
                    goto LABEL_196;
                  }
                  goto LABEL_205;
                }
                Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v82);
                Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
                Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
                v56 = *(_QWORD *)(v56 + 416);
                v54 = *(_QWORD *)v85;
              }
              v73 = 3031;
              goto LABEL_214;
            }
          }
        }
LABEL_162:
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v126);
        if ( !v115 )
          goto LABEL_206;
        v6 = (CCbsSession *)v86;
      }
    }
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v119);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v78);
  }
  if ( !v114 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"No entry in the ActionList: {} matched the FilePath: {}",
        (__int64)&v96,
        (__int64)&v95);
      *(_QWORD *)v83 = &v110;
      v110 = -2147023728;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v83);
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC0D,
           (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
           (const char *)0x490,
           (unsigned int)dwCreationDisposition);
    goto LABEL_241;
  }
  LogAdapter::TraceAtLevel<unsigned long>(1, "{} packages are processed from the action list.", &v114);
  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v118);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v90);
  return 0;
}

```

## disassembly

```asm
0x1800cd91c  mov     [rsp-8+arg_8], rbx
0x1800cd921  push    rbp
0x1800cd922  push    rsi
0x1800cd923  push    rdi
0x1800cd924  push    r12
0x1800cd926  push    r13
0x1800cd928  push    r14
0x1800cd92a  push    r15
0x1800cd92c  lea     rbp, [rsp-1D0h]
0x1800cd934  sub     rsp, 2D0h
0x1800cd93b  mov     rax, cs:__security_cookie
0x1800cd942  xor     rax, rsp
0x1800cd945  mov     [rbp+200h+var_40], rax
0x1800cd94c  mov     rax, [rbp+200h+arg_28]
0x1800cd953  xor     r15d, r15d
0x1800cd956  mov     qword ptr [rbp+200h+var_260], rax
0x1800cd95a  mov     r10, r8
0x1800cd95d  mov     rax, [rbp+200h+arg_20]
0x1800cd964  mov     r14, rcx
0x1800cd967  mov     [rbp+200h+var_1F0], rax
0x1800cd96b  xorps   xmm0, xmm0
0x1800cd96e  xor     eax, eax
0x1800cd970  mov     [rbp+200h+var_230], r9
0x1800cd974  mov     [rbp+200h+var_210], rax
0x1800cd978  lea     r9, [rbp+200h+var_220]
0x1800cd97c  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x1800cd983  mov     [rbp+200h+var_150], edx
0x1800cd989  mov     [rbp+200h+var_240], rcx
0x1800cd98d  lea     rdx, [rbp+200h+var_120]
0x1800cd994  mov     [rbp+200h+var_1E8], r8
0x1800cd998  mov     rcx, r10
0x1800cd99b  lea     r8, [rbp+200h+var_200]
0x1800cd99f  mov     [rbp+200h+var_120], rax
0x1800cd9a6  movups  [rbp+200h+var_220], xmm0
0x1800cd9aa  mov     [rbp+200h+var_200], r15
0x1800cd9ae  mov     [rbp+200h+var_118], r15
0x1800cd9b5  mov     [rbp+200h+var_110], r15
0x1800cd9bc  mov     [rbp+200h+var_134], r15d
0x1800cd9c3  call    ?ReadActionList@ActionListParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUActionListDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; ActionListParser::ReadActionList(wchar_t const * const,Windows::Rtl::IPoolAllocator &,ActionListParser::ActionListDocument * *,Windows::Auto<_LBLOB> *)
0x1800cd9c8  mov     ebx, eax
0x1800cd9ca  test    eax, eax
0x1800cd9cc  jns     short loc_1800CDA33
0x1800cd9ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cd9d5  mov     dword ptr [rbp+200h+hFile], eax
0x1800cd9db  test    rcx, rcx
0x1800cd9de  jz      short loc_1800CDA2C
0x1800cd9e0  lea     rax, [rbp+200h+var_1E8]
0x1800cd9e4  xor     edx, edx
0x1800cd9e6  lea     r12d, [r15+3]
0x1800cd9ea  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cd9ef  mov     r8d, r12d
0x1800cd9f2  lea     r9, aFailedToLoadAc_2; "Failed to load actions from {}"
0x1800cd9f9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cd9fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda05  lea     rax, [rbp+200h+hFile]
0x1800cda0c  mov     qword ptr [rbp+200h+var_250], rax
0x1800cda10  lea     r9, asc_1802EE7AC; ": {}"
0x1800cda17  lea     rax, [rbp+200h+var_250]
0x1800cda1b  mov     r8d, r12d
0x1800cda1e  lea     edx, [r15+1]
0x1800cda22  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cda27  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cda2c  mov     edx, 0A76h
0x1800cda31  jmp     short loc_1800CDAA6
0x1800cda33  mov     r8, [rbp+200h+var_200]
0x1800cda37  mov     rsi, [r8+98h]
0x1800cda3e  cmp     [rsi+40h], r15
0x1800cda42  jnz     short loc_1800CDAC1
0x1800cda44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda4b  mov     ebx, 800F0952h
0x1800cda50  mov     [rbp+200h+var_138], ebx
0x1800cda56  test    rcx, rcx
0x1800cda59  jz      short loc_1800CDAA1
0x1800cda5b  mov     r12d, 3
0x1800cda61  lea     r9, aActionlistNoPa; "ActionList: No package to process in ac"...
0x1800cda68  mov     r8d, r12d
0x1800cda6b  xor     edx, edx
0x1800cda6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cda72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cda79  lea     rax, [rbp+200h+var_138]
0x1800cda80  mov     qword ptr [rbp+200h+var_250], rax
0x1800cda84  lea     r9, asc_1802EE7AC; ": {}"
0x1800cda8b  lea     rax, [rbp+200h+var_250]
0x1800cda8f  mov     r8d, r12d
0x1800cda92  lea     edx, [r12-2]
0x1800cda97  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; int
0x1800cda9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdaa1  mov     edx, 0A7Bh; void *
0x1800cdaa6  mov     rcx, [rbp+208h]; this
0x1800cdaad  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800cdab4  mov     r9d, ebx; char *
0x1800cdab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdabc  jmp     loc_1800CF078
0x1800cdac1  mov     rbx, [rsi+38h]
0x1800cdac5  mov     r12d, 3
0x1800cdacb  mov     r9b, r15b
0x1800cdace  mov     r10b, r15b
0x1800cdad1  mov     r11b, r15b
0x1800cdad4  mov     rax, rbx
0x1800cdad7  lea     r13d, [r12-2]
0x1800cdadc  test    rax, rax
0x1800cdadf  jz      short loc_1800CDB3D
0x1800cdae1  mov     edx, [rax+8Ch]
0x1800cdae7  sub     edx, 2
0x1800cdaea  jz      short loc_1800CDB31
0x1800cdaec  sub     edx, r13d
0x1800cdaef  jz      short loc_1800CDB31
0x1800cdaf1  sub     edx, r13d
0x1800cdaf4  jz      short loc_1800CDB31
0x1800cdaf6  sub     edx, r13d
0x1800cdaf9  jz      short loc_1800CDB0A
0x1800cdafb  sub     edx, r13d
0x1800cdafe  jz      short loc_1800CDB0A
0x1800cdb00  sub     edx, r12d
0x1800cdb03  jz      short loc_1800CDB31
0x1800cdb05  cmp     edx, 4
0x1800cdb08  jnz     short loc_1800CDB34
0x1800cdb0a  cmp     dword ptr [rax+90h], 2
0x1800cdb11  mov     r10b, r13b
0x1800cdb14  jz      short loc_1800CDB2C
0x1800cdb16  cmp     [rax+108h], r15
0x1800cdb1d  jbe     short loc_1800CDB34
0x1800cdb1f  mov     rcx, [rax+100h]
0x1800cdb26  cmp     dword ptr [rcx+30h], 2
0x1800cdb2a  jnz     short loc_1800CDB34
0x1800cdb2c  mov     r11b, r13b
0x1800cdb2f  jmp     short loc_1800CDB34
0x1800cdb31  mov     r9b, r13b
0x1800cdb34  mov     rax, [rax+128h]
0x1800cdb3b  jmp     short loc_1800CDADC
0x1800cdb3d  test    r9b, r9b
0x1800cdb40  jz      loc_1800CDD46
0x1800cdb46  test    r10b, r10b
0x1800cdb49  jz      loc_1800CDC64
0x1800cdb4f  test    r11b, r11b
0x1800cdb52  jz      loc_1800CDC64
0x1800cdb58  test    rbx, rbx
0x1800cdb5b  jz      loc_1800CDC64
0x1800cdb61  mov     [rbp+200h+var_1F8], r15
0x1800cdb65  mov     ecx, [rbx+8Ch]
0x1800cdb6b  sub     ecx, 2
0x1800cdb6e  jz      short loc_1800CDB7F
0x1800cdb70  sub     ecx, r13d
0x1800cdb73  jz      short loc_1800CDB7F
0x1800cdb75  sub     ecx, r13d
0x1800cdb78  jz      short loc_1800CDB7F
0x1800cdb7a  cmp     ecx, 5
0x1800cdb7d  jnz     short loc_1800CDBD6
0x1800cdb7f  lea     rdx, [rbx+0C8h]; struct _LUTF8_STRING *
0x1800cdb86  lea     r8, [rbp+200h+var_1F8]; wchar_t **
0x1800cdb8a  lea     rcx, [rbp+200h+var_120]; struct Windows::Rtl::IPoolAllocator *
0x1800cdb91  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800cdb96  mov     edi, eax
0x1800cdb98  test    eax, eax
0x1800cdb9a  js      loc_1800CDC42
0x1800cdba0  mov     rdx, [rbp+200h+var_1F8]; wchar_t *
0x1800cdba4  lea     rdi, [r14+760h]
0x1800cdbab  mov     rcx, rdi; this
0x1800cdbae  lea     r8, ?StringArrayIsEqualCaseInsensitive@@YAHAEBQEA_W0@Z; int (*)(wchar_t *const *, wchar_t *const *)
0x1800cdbb5  call    ?Find@CCbsStringArray@@QEBA_KQEB_WP6AHAEBQEA_W1@Z@Z; CCbsStringArray::Find(wchar_t const * const,int (*)(wchar_t * const &,wchar_t * const &))
0x1800cdbba  mov     ecx, 0FFFFFFFFh
0x1800cdbbf  cmp     rax, rcx
0x1800cdbc2  jnz     short loc_1800CDBD6
0x1800cdbc4  mov     rdx, [rbp+200h+var_1F8]; wchar_t *
0x1800cdbc8  mov     rcx, rdi; this
0x1800cdbcb  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x1800cdbd0  mov     edi, eax
0x1800cdbd2  test    eax, eax
0x1800cdbd4  js      short loc_1800CDBE2
0x1800cdbd6  mov     rbx, [rbx+128h]
0x1800cdbdd  jmp     loc_1800CDB58
0x1800cdbe2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdbe9  mov     [rbp+200h+var_138], edi
0x1800cdbef  test    rcx, rcx
0x1800cdbf2  jz      short loc_1800CDC3B
0x1800cdbf4  lea     rax, [rbp+200h+var_1F8]
0x1800cdbf8  mov     r8d, r12d
0x1800cdbfb  lea     r9, aFailedAddingCa; "Failed adding capability to array: {}"
0x1800cdc02  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdc07  xor     edx, edx
0x1800cdc09  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800cdc0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdc15  lea     rax, [rbp+200h+var_138]
0x1800cdc1c  mov     [rbp+200h+var_238], rax
0x1800cdc20  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdc27  lea     rax, [rbp+200h+var_238]
0x1800cdc2b  mov     r8d, r12d
0x1800cdc2e  mov     dl, r13b
0x1800cdc31  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdc36  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdc3b  mov     edx, 0ABAh
0x1800cdc40  jmp     short loc_1800CDC47
0x1800cdc42  mov     edx, 0AB3h; void *
0x1800cdc47  mov     rcx, [rbp+208h]; this
0x1800cdc4e  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800cdc55  mov     r9d, edi; char *
0x1800cdc58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdc5d  mov     ebx, edi
0x1800cdc5f  jmp     loc_1800CF078
0x1800cdc64  lea     rdx, [rbp+200h+hFile]; int *
0x1800cdc6b  mov     dword ptr [rbp+200h+hFile], r15d
0x1800cdc72  mov     rcx, r14; this
0x1800cdc75  call    ?LCUInstallIsSmartPended@CCbsSession@@QEAAJQEAH@Z; CCbsSession::LCUInstallIsSmartPended(int * const)
0x1800cdc7a  mov     ebx, eax
0x1800cdc7c  test    eax, eax
0x1800cdc7e  jns     short loc_1800CDCDA
0x1800cdc80  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdc87  mov     [rbp+200h+var_130], eax
0x1800cdc8d  test    rcx, rcx
0x1800cdc90  jz      short loc_1800CDCD0
0x1800cdc92  lea     r9, aFailedGettingL; "Failed getting LCU smart pended state"
0x1800cdc99  mov     r8d, r12d
0x1800cdc9c  xor     edx, edx
0x1800cdc9e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdca3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdcaa  lea     rax, [rbp+200h+var_130]
0x1800cdcb1  mov     [rbp+200h+var_228], rax
0x1800cdcb5  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdcbc  lea     rax, [rbp+200h+var_228]
0x1800cdcc0  mov     r8d, r12d
0x1800cdcc3  mov     dl, r13b
0x1800cdcc6  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdccb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdcd0  mov     edx, 0AD5h
0x1800cdcd5  jmp     loc_1800CDAA6
0x1800cdcda  cmp     dword ptr [rbp+200h+hFile], r15d
0x1800cdce1  jz      short loc_1800CDD42
0x1800cdce3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdcea  mov     ebx, 800F0806h
0x1800cdcef  mov     [rbp+200h+var_138], ebx
0x1800cdcf5  test    rcx, rcx
0x1800cdcf8  jz      short loc_1800CDD38
0x1800cdcfa  lea     r9, aAttemptedToIns; "Attempted to install a FOD or LP with a"...
0x1800cdd01  mov     r8d, r12d
0x1800cdd04  xor     edx, edx
0x1800cdd06  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdd0b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdd12  lea     rax, [rbp+200h+var_138]
0x1800cdd19  mov     qword ptr [rbp+200h+var_250], rax
0x1800cdd1d  lea     r9, asc_1802EE7AC; ": {}"
0x1800cdd24  lea     rax, [rbp+200h+var_250]
0x1800cdd28  mov     r8d, r12d
0x1800cdd2b  mov     dl, r13b
0x1800cdd2e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cdd33  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cdd38  mov     edx, 0ADBh
0x1800cdd3d  jmp     loc_1800CDAA6
0x1800cdd42  mov     r8, [rbp+200h+var_200]
0x1800cdd46  mov     rbx, [r8+88h]
0x1800cdd4d  test    rbx, rbx
0x1800cdd50  jz      loc_1800CDEEE
0x1800cdd56  mov     rbx, [rbx+10h]
0x1800cdd5a  test    rbx, rbx
0x1800cdd5d  jz      short loc_1800CDDD9
0x1800cdd5f  xor     r8d, r8d
0x1800cdd62  mov     rdx, rbx
0x1800cdd65  mov     rcx, r14
0x1800cdd68  call    ?AddFeatureToModify@CCbsSession@@AEAAJAEBU_LUTF8_STRING@@W4CbsState@@@Z; CCbsSession::AddFeatureToModify(_LUTF8_STRING const &,CbsState)
0x1800cdd6d  mov     edi, eax
0x1800cdd6f  test    eax, eax
0x1800cdd71  js      short loc_1800CDD79
0x1800cdd73  mov     rbx, [rbx+48h]
0x1800cdd77  jmp     short loc_1800CDD5A
0x1800cdd79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdd80  mov     [rbp+200h+NumberOfBytesWritten], edi
0x1800cdd86  test    rcx, rcx
0x1800cdd89  jz      short loc_1800CDDCF
0x1800cdd8b  lea     r9, aFailedToProces_29; "Failed to process RemoveFeature Action"
0x1800cdd92  mov     r8d, r12d
0x1800cdd95  xor     edx, edx
0x1800cdd97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cdd9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cdda3  lea     rax, [rbp+200h+NumberOfBytesWritten]
0x1800cddaa  mov     qword ptr [rbp+200h+nNumberOfBytesToWrite], rax
0x1800cddb1  lea     r9, asc_1802EE7AC; ": {}"
0x1800cddb8  lea     rax, [rbp+200h+nNumberOfBytesToWrite]
0x1800cddbf  mov     r8d, r12d
0x1800cddc2  mov     dl, r13b
0x1800cddc5  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800cddca  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cddcf  mov     edx, 0AE7h
0x1800cddd4  jmp     loc_1800CDC47
0x1800cddd9  mov     rax, [rbp+200h+var_200]
0x1800cdddd  mov     rbx, [rax+88h]
0x1800cdde4  mov     rbx, [rbx+20h]
0x1800cdde8  test    rbx, rbx
0x1800cddeb  jz      short loc_1800CDE64
0x1800cdded  mov     r8d, 40h ; '@'
0x1800cddf3  mov     rdx, rbx
0x1800cddf6  mov     rcx, r14
0x1800cddf9  call    ?AddFeatureToModify@CCbsSession@@AEAAJAEBU_LUTF8_STRING@@W4CbsState@@@Z; CCbsSession::AddFeatureToModify(_LUTF8_STRING const &,CbsState)
0x1800cddfe  mov     edi, eax
0x1800cde00  test    eax, eax
0x1800cde02  js      short loc_1800CDE0A
0x1800cde04  mov     rbx, [rbx+48h]
0x1800cde08  jmp     short loc_1800CDDE8
0x1800cde0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cde11  mov     dword ptr [rbp+200h+var_148], edi
0x1800cde17  test    rcx, rcx
0x1800cde1a  jz      short loc_1800CDE5A
  ... truncated ...
```
