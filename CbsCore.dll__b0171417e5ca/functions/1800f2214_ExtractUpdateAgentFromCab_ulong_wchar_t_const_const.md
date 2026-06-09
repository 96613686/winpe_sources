# ExtractUpdateAgentFromCab(ulong,wchar_t const * const)

- ea: `0x1800f2214`
- end: `0x1800f2900`
- name: `?ExtractUpdateAgentFromCab@@YAJKQEB_W@Z`
- size: `1772`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *const)`
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006ba9c`
- `0x1800c4d00`
- `0x1800e7aa4`

## callees

- `0x180011a14`
- `0x180013250`
- `0x180015420`
- `0x180023ca8`
- `0x1800261e0`
- `0x18002a448`
- `0x180042448`
- `0x180057c28`
- `0x180059a00`
- `0x18005a548`
- `0x18005dd58`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800f2214`
- `0x18012c2b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2848`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f2439`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f264c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f2439`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f264c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800f260f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800f2834`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800f260f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800f2834`

## string_xrefs

- `0x1800f22cb`: `updateagent.dll`
- `0x1800f2802`: `updateagent.dll`
- `0x1800f2347`: `Failed to create path to the updateagent cab.`
- `0x1800f23e1`: `Failed to extract update agent from the cab`
- `0x1800f2432`: `DESKTOP_DEPLOYMENT_OVERRIDE_DLL_PATH`
- `0x1800f24b8`: `*.dll`
- `0x1800f26b1`: `Failed to copy file from: {} to {}`
- `0x1800f2871`: `Failed to copy file from: {} to {}`
- `0x1800f2645`: `UPDATE_AGENT_OVERRIDE_DLL_PATH`

## pseudocode

```c
__int64 __fastcall ExtractUpdateAgentFromCab(__int64 a1, const wchar_t *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  wchar_t *v6; // rbx
  int v7; // edi
  __int64 v8; // rdx
  int Directory; // eax
  int AllFilesFromCabinet; // eax
  DWORD EnvironmentVariableW; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  _QWORD *v15; // r14
  _QWORD *v16; // r15
  const WCHAR *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  LPCWSTR v20; // rsi
  signed int LastError; // r14d
  unsigned int v22; // eax
  const WCHAR *v24; // rdi
  LPCWSTR v25; // rbx
  signed int v26; // esi
  unsigned int v27; // eax
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v31; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-B8h] BYREF
  void *v33; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v34; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v36[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v37[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[24]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  _QWORD *v40; // [rsp+A8h] [rbp-58h]
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v35 = 0;
  v34 = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  memset_0(Buffer, 0, 0x208u);
  v3 = SczAllocFromSzAndEnsureBackslash(&v34, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = SczAllocConcatSz(&v34, L"metadata\\");
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 586;
      goto LABEL_5;
    }
    v6 = v34;
    v7 = SczAllocFormatted(&lpNewFileName, L"%ws%ws", v34, L"updateagent.dll");
    if ( v7 < 0 )
    {
      v8 = 587;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
        (const char *)(unsigned int)v7,
        v28);
LABEL_9:
      v4 = v7;
      goto LABEL_54;
    }
    if ( !(unsigned int)DoesFileExist(lpNewFileName, 0) )
    {
      Directory = RecursivelyCreateDirectory(v6, 0);
      v7 = Directory;
      if ( Directory < 0 )
      {
        v36[0] = Directory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path to the updateagent cab.");
          *(_QWORD *)v29 = v36;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v29);
        }
        v8 = 592;
        goto LABEL_8;
      }
      v7 = SczAllocFormatted(&v35, L"%ws%ws", a2, L"desktopdeployment.cab");
      if ( v7 < 0 )
      {
        v8 = 605;
        goto LABEL_8;
      }
      AllFilesFromCabinet = DpxExtractAllFilesFromCabinet(v35, v6);
      v7 = AllFilesFromCabinet;
      if ( AllFilesFromCabinet < 0 )
      {
        v36[0] = AllFilesFromCabinet;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract update agent from the cab");
          *(_QWORD *)v29 = v36;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v29);
        }
        v8 = 609;
        goto LABEL_8;
      }
      EnvironmentVariableW = GetEnvironmentVariableW(L"DESKTOP_DEPLOYMENT_OVERRIDE_DLL_PATH", Buffer, 0x104u);
      if ( EnvironmentVariableW && EnvironmentVariableW < 0x104 )
      {
        *(_QWORD *)v29 = 0;
        CCbsStringArray::CCbsStringArray((CCbsStringArray *)v38);
        v7 = SczAllocFromSz(v29, Buffer);
        if ( v7 < 0 )
        {
          v13 = 620;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
            (const char *)(unsigned int)v7,
            v28);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v38);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
          goto LABEL_9;
        }
        v14 = CbsEnumFiles(v12, v6, L"*.dll", v38);
        v7 = v14;
        if ( v14 < 0 )
        {
          v36[0] = v14;
          if ( LogAdapter::g_Logger )
          {
            v37[0] = v6;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to enumerate deployment files in {}",
              (__int64)v37);
            v31 = v36;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v31);
          }
          v13 = 623;
          goto LABEL_25;
        }
        if ( !v39 )
        {
          v7 = -2146498560;
          LODWORD(v37[0]) = -2146498560;
          if ( LogAdapter::g_Logger )
          {
            v33 = v6;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to find deployment files in {}",
              (__int64)&v33);
            v31 = (unsigned int *)v37;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v31);
          }
          v13 = 625;
          goto LABEL_25;
        }
        v15 = v40;
        v16 = &v40[v39];
        while ( 1 )
        {
          if ( v15 == v16 )
          {
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v38);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
            goto LABEL_42;
          }
          v7 = SczAllocCombinePath2Sz(&lpExistingFileName, *(_QWORD *)v29, *v15);
          if ( v7 < 0 )
          {
            v13 = 629;
            goto LABEL_25;
          }
          v17 = lpExistingFileName;
          if ( (unsigned int)DoesFileExist(lpExistingFileName, 0) )
          {
            v18 = SczAllocCombinePath2Sz(&lpNewFileName, v6, *v15);
            v19 = v18;
            if ( v18 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x279,
                (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
                (const char *)(unsigned int)v18,
                v28);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v38);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
              v4 = v19;
              goto LABEL_54;
            }
            v20 = lpNewFileName;
            if ( !CopyFileW(v17, lpNewFileName, 0) )
              break;
          }
          ++v15;
        }
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          v33 = (void *)v20;
          v31 = (unsigned int *)v17;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to copy file from: {} to {}",
            (__int64)&v31,
            (__int64)&v33);
          if ( LastError > 0 )
            v22 = (unsigned __int16)LastError | 0x80070000;
          else
            v22 = LastError;
          LODWORD(v37[0]) = v22;
          *(_QWORD *)v36 = v37;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v36);
        }
        if ( LastError )
        {
          v4 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x27F,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
                 (const char *)(unsigned int)LastError,
                 v28);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v38);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
          goto LABEL_54;
        }
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v38);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v29);
      }
      else
      {
LABEL_42:
        if ( GetEnvironmentVariableW(L"UPDATE_AGENT_OVERRIDE_DLL_PATH", Buffer, 0x104u) - 1 <= 0x102 )
        {
          v7 = SczAllocFromSz(&lpExistingFileName, Buffer);
          if ( v7 < 0 )
          {
            v8 = 648;
            goto LABEL_8;
          }
          v24 = lpExistingFileName;
          if ( (unsigned int)DoesFileExist(lpExistingFileName, 0) )
          {
            v3 = SczAllocCombinePath2Sz(&lpNewFileName, v6, L"updateagent.dll");
            v4 = v3;
            if ( v3 < 0 )
            {
              v5 = 652;
              goto LABEL_5;
            }
            v25 = lpNewFileName;
            if ( !CopyFileW(v24, lpNewFileName, 0) )
            {
              v26 = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                v33 = (void *)v25;
                v31 = (unsigned int *)v24;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to copy file from: {} to {}",
                  (__int64)&v31,
                  (__int64)&v33);
                if ( v26 > 0 )
                  v27 = (unsigned __int16)v26 | 0x80070000;
                else
                  v27 = v26;
                LODWORD(v37[0]) = v27;
                *(_QWORD *)v29 = v37;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {0}",
                  (__int64)v29);
              }
              if ( v26 )
              {
                v4 = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x292,
                       (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
                       (const char *)(unsigned int)v26,
                       v28);
                goto LABEL_54;
              }
            }
          }
        }
      }
    }
    v4 = 0;
    goto LABEL_54;
  }
  v5 = 585;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\core\\cbscorehelpers.cpp",
    (const char *)(unsigned int)v3,
    v28);
LABEL_54:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v34);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
  return v4;
}

```

## disassembly

```asm
0x1800f2214  push    rbp
0x1800f2216  push    rbx
0x1800f2217  push    rsi
0x1800f2218  push    rdi
0x1800f2219  push    r14
0x1800f221b  push    r15
0x1800f221d  lea     rbp, [rsp-1E8h]
0x1800f2225  sub     rsp, 2E8h
0x1800f222c  mov     rax, cs:__security_cookie
0x1800f2233  xor     rax, rsp
0x1800f2236  mov     [rbp+210h+var_40], rax
0x1800f223d  mov     rsi, rdx
0x1800f2240  mov     [rsp+310h+var_2B0], 0
0x1800f2249  xor     edx, edx; Val
0x1800f224b  mov     [rsp+310h+var_2B8], 0
0x1800f2254  mov     r8d, 208h; Size
0x1800f225a  mov     [rsp+310h+lpExistingFileName], 0
0x1800f2263  lea     rcx, [rbp+210h+Buffer]; void *
0x1800f2267  mov     [rsp+310h+lpNewFileName], 0
0x1800f2270  call    memset_0
0x1800f2275  mov     rdx, rsi
0x1800f2278  lea     rcx, [rsp+310h+var_2B8]
0x1800f227d  call    SczAllocFromSzAndEnsureBackslash
0x1800f2282  mov     ebx, eax
0x1800f2284  test    eax, eax
0x1800f2286  jns     short loc_1800F228F
0x1800f2288  mov     edx, 249h
0x1800f228d  jmp     short loc_1800F22AB
0x1800f228f  lea     rdx, aMetadata_0; "metadata\\"
0x1800f2296  lea     rcx, [rsp+310h+var_2B8]
0x1800f229b  call    SczAllocConcatSz
0x1800f22a0  mov     ebx, eax
0x1800f22a2  test    eax, eax
0x1800f22a4  jns     short loc_1800F22C6
0x1800f22a6  mov     edx, 24Ah; void *
0x1800f22ab  mov     rcx, [rbp+218h]; this
0x1800f22b2  lea     r8, aOnecoreBaseCbs_121; "onecore\\base\\cbs\\core\\cbscorehelper"...
0x1800f22b9  mov     r9d, eax; char *
0x1800f22bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f22c1  jmp     loc_1800F2765
0x1800f22c6  mov     rbx, [rsp+310h+var_2B8]
0x1800f22cb  lea     r9, aUpdateagentDll; "updateagent.dll"
0x1800f22d2  mov     r8, rbx
0x1800f22d5  lea     rdx, aWsWs_1; "%ws%ws"
0x1800f22dc  lea     rcx, [rsp+310h+lpNewFileName]
0x1800f22e1  call    SczAllocFormatted
0x1800f22e6  mov     edi, eax
0x1800f22e8  test    eax, eax
0x1800f22ea  jns     short loc_1800F230E
0x1800f22ec  mov     edx, 24Bh; void *
0x1800f22f1  mov     rcx, [rbp+218h]; this
0x1800f22f8  lea     r8, aOnecoreBaseCbs_121; "onecore\\base\\cbs\\core\\cbscorehelper"...
0x1800f22ff  mov     r9d, edi; char *
0x1800f2302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2307  mov     ebx, edi
0x1800f2309  jmp     loc_1800F2765
0x1800f230e  mov     rcx, [rsp+310h+lpNewFileName]
0x1800f2313  xor     edx, edx
0x1800f2315  call    DoesFileExist
0x1800f231a  test    eax, eax
0x1800f231c  jnz     loc_1800F2763
0x1800f2322  xor     edx, edx
0x1800f2324  mov     rcx, rbx
0x1800f2327  call    RecursivelyCreateDirectory
0x1800f232c  mov     edi, eax
0x1800f232e  test    eax, eax
0x1800f2330  jns     short loc_1800F238E
0x1800f2332  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f2339  mov     [rsp+310h+var_2A8], eax
0x1800f233d  test    rcx, rcx
0x1800f2340  jz      short loc_1800F2384
0x1800f2342  mov     ebx, 3
0x1800f2347  lea     r9, aFailedToCreate_18; "Failed to create path to the updateagen"...
0x1800f234e  mov     r8d, ebx
0x1800f2351  xor     edx, edx
0x1800f2353  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f2358  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f235f  lea     rax, [rsp+310h+var_2A8]
0x1800f2364  mov     qword ptr [rsp+310h+var_2E0], rax
0x1800f2369  lea     r9, asc_1802EE7AC; ": {}"
0x1800f2370  lea     rax, [rsp+310h+var_2E0]
0x1800f2375  mov     r8d, ebx
0x1800f2378  mov     dl, 1
0x1800f237a  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f237f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f2384  mov     edx, 250h
0x1800f2389  jmp     loc_1800F22F1
0x1800f238e  lea     r9, aDesktopdeploym; "desktopdeployment.cab"
0x1800f2395  mov     r8, rsi
0x1800f2398  lea     rdx, aWsWs_1; "%ws%ws"
0x1800f239f  lea     rcx, [rsp+310h+var_2B0]
0x1800f23a4  call    SczAllocFormatted
0x1800f23a9  mov     edi, eax
0x1800f23ab  test    eax, eax
0x1800f23ad  jns     short loc_1800F23B9
0x1800f23af  mov     edx, 25Dh
0x1800f23b4  jmp     loc_1800F22F1
0x1800f23b9  mov     rcx, [rsp+310h+var_2B0]; wchar_t *
0x1800f23be  mov     rdx, rbx; wchar_t *
0x1800f23c1  call    ?DpxExtractAllFilesFromCabinet@@YAJPEB_W0@Z; DpxExtractAllFilesFromCabinet(wchar_t const *,wchar_t const *)
0x1800f23c6  mov     edi, eax
0x1800f23c8  test    eax, eax
0x1800f23ca  jns     short loc_1800F2428
0x1800f23cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f23d3  mov     [rsp+310h+var_2A8], eax
0x1800f23d7  test    rcx, rcx
0x1800f23da  jz      short loc_1800F241E
0x1800f23dc  mov     ebx, 3
0x1800f23e1  lea     r9, aFailedToExtrac_12; "Failed to extract update agent from the"...
0x1800f23e8  mov     r8d, ebx
0x1800f23eb  xor     edx, edx
0x1800f23ed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f23f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f23f9  lea     rax, [rsp+310h+var_2A8]
0x1800f23fe  mov     qword ptr [rsp+310h+var_2E0], rax
0x1800f2403  lea     r9, asc_1802EE7AC; ": {}"
0x1800f240a  lea     rax, [rsp+310h+var_2E0]
0x1800f240f  mov     r8d, ebx
0x1800f2412  mov     dl, 1
0x1800f2414  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f2419  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f241e  mov     edx, 261h
0x1800f2423  jmp     loc_1800F22F1
0x1800f2428  mov     r8d, 104h; nSize
0x1800f242e  lea     rdx, [rbp+210h+Buffer]; lpBuffer
0x1800f2432  lea     rcx, aDesktopDeploym; "DESKTOP_DEPLOYMENT_OVERRIDE_DLL_PATH"
0x1800f2439  call    cs:__imp_GetEnvironmentVariableW
0x1800f2440  nop     dword ptr [rax+rax+00h]
0x1800f2445  test    eax, eax
0x1800f2447  jz      loc_1800F263B
0x1800f244d  cmp     eax, 104h
0x1800f2452  jnb     loc_1800F263B
0x1800f2458  lea     rcx, [rbp+210h+var_290]; this
0x1800f245c  mov     qword ptr [rsp+310h+var_2E0], 0
0x1800f2465  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x1800f246a  lea     rdx, [rbp+210h+Buffer]
0x1800f246e  lea     rcx, [rsp+310h+var_2E0]
0x1800f2473  call    SczAllocFromSz
0x1800f2478  mov     edi, eax
0x1800f247a  test    eax, eax
0x1800f247c  jns     short loc_1800F24B1
0x1800f247e  mov     edx, 26Ch; void *
0x1800f2483  mov     rcx, [rbp+218h]; this
0x1800f248a  lea     r8, aOnecoreBaseCbs_121; "onecore\\base\\cbs\\core\\cbscorehelper"...
0x1800f2491  mov     r9d, edi; char *
0x1800f2494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2499  lea     rcx, [rbp+210h+var_290]
0x1800f249d  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1800f24a2  lea     rcx, [rsp+310h+var_2E0]
0x1800f24a7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800f24ac  jmp     loc_1800F2307
0x1800f24b1  lea     r9, [rbp+210h+var_290]
0x1800f24b5  mov     rdx, rbx
0x1800f24b8  lea     r8, aDll; "*.dll"
0x1800f24bf  call    CbsEnumFiles
0x1800f24c4  mov     edi, eax
0x1800f24c6  test    eax, eax
0x1800f24c8  jns     short loc_1800F2535
0x1800f24ca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f24d1  mov     [rsp+310h+var_2A8], eax
0x1800f24d5  test    rcx, rcx
0x1800f24d8  jz      short loc_1800F252B
0x1800f24da  mov     [rsp+310h+var_2A0], rbx
0x1800f24df  lea     rax, [rsp+310h+var_2A0]
0x1800f24e4  mov     ebx, 3
0x1800f24e9  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f24ee  mov     r8d, ebx
0x1800f24f1  lea     r9, aFailedToEnumer_51; "Failed to enumerate deployment files in"...
0x1800f24f8  xor     edx, edx
0x1800f24fa  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800f24ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f2506  lea     rax, [rsp+310h+var_2A8]
0x1800f250b  mov     [rsp+310h+var_2D0], rax
0x1800f2510  lea     r9, asc_1802EE7AC; ": {}"
0x1800f2517  lea     rax, [rsp+310h+var_2D0]
0x1800f251c  mov     r8d, ebx
0x1800f251f  mov     dl, 1
0x1800f2521  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f2526  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f252b  mov     edx, 26Fh
0x1800f2530  jmp     loc_1800F2483
0x1800f2535  mov     rax, [rbp+210h+var_278]
0x1800f2539  test    rax, rax
0x1800f253c  jnz     short loc_1800F25AE
0x1800f253e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f2545  mov     edi, 800F0800h
0x1800f254a  mov     dword ptr [rsp+310h+var_2A0], edi
0x1800f254e  test    rcx, rcx
0x1800f2551  jz      short loc_1800F25A4
0x1800f2553  mov     [rsp+310h+var_2C0], rbx
0x1800f2558  lea     rax, [rsp+310h+var_2C0]
0x1800f255d  mov     ebx, 3
0x1800f2562  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f2567  mov     r8d, ebx
0x1800f256a  lea     r9, aFailedToFindDe; "Failed to find deployment files in {}"
0x1800f2571  xor     edx, edx
0x1800f2573  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800f2578  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f257f  lea     rax, [rsp+310h+var_2A0]
0x1800f2584  mov     [rsp+310h+var_2D0], rax
0x1800f2589  lea     r9, asc_1802EE7AC; ": {}"
0x1800f2590  lea     rax, [rsp+310h+var_2D0]
0x1800f2595  mov     r8d, ebx
0x1800f2598  mov     dl, 1
0x1800f259a  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f259f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f25a4  mov     edx, 271h
0x1800f25a9  jmp     loc_1800F2483
0x1800f25ae  mov     r14, [rbp+210h+var_268]
0x1800f25b2  lea     r15, [r14+rax*8]
0x1800f25b6  jmp     short loc_1800F2623
0x1800f25b8  mov     r8, [r14]
0x1800f25bb  lea     rcx, [rsp+310h+lpExistingFileName]
0x1800f25c0  mov     rdx, qword ptr [rsp+310h+var_2E0]
0x1800f25c5  call    SczAllocCombinePath2Sz
0x1800f25ca  mov     edi, eax
0x1800f25cc  test    eax, eax
0x1800f25ce  js      loc_1800F27E1
0x1800f25d4  mov     rdi, [rsp+310h+lpExistingFileName]
0x1800f25d9  xor     edx, edx
0x1800f25db  mov     rcx, rdi
0x1800f25de  call    DoesFileExist
0x1800f25e3  test    eax, eax
0x1800f25e5  jz      short loc_1800F261F
0x1800f25e7  mov     r8, [r14]
0x1800f25ea  lea     rcx, [rsp+310h+lpNewFileName]
0x1800f25ef  mov     rdx, rbx
0x1800f25f2  call    SczAllocCombinePath2Sz
0x1800f25f7  mov     esi, eax
0x1800f25f9  test    eax, eax
0x1800f25fb  js      loc_1800F27AF
0x1800f2601  mov     rsi, [rsp+310h+lpNewFileName]
0x1800f2606  xor     r8d, r8d; bFailIfExists
0x1800f2609  mov     rdx, rsi; lpNewFileName
0x1800f260c  mov     rcx, rdi; lpExistingFileName
0x1800f260f  call    cs:__imp_CopyFileW
0x1800f2616  nop     dword ptr [rax+rax+00h]
0x1800f261b  test    eax, eax
0x1800f261d  jz      short loc_1800F2687
0x1800f261f  add     r14, 8
0x1800f2623  cmp     r14, r15
0x1800f2626  jnz     short loc_1800F25B8
0x1800f2628  lea     rcx, [rbp+210h+var_290]
0x1800f262c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1800f2631  lea     rcx, [rsp+310h+var_2E0]
0x1800f2636  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800f263b  mov     r8d, 104h; nSize
0x1800f2641  lea     rdx, [rbp+210h+Buffer]; lpBuffer
0x1800f2645  lea     rcx, aUpdateAgentOve; "UPDATE_AGENT_OVERRIDE_DLL_PATH"
0x1800f264c  call    cs:__imp_GetEnvironmentVariableW
0x1800f2653  nop     dword ptr [rax+rax+00h]
0x1800f2658  dec     eax
0x1800f265a  cmp     eax, 102h
0x1800f265f  ja      loc_1800F2763
0x1800f2665  lea     rdx, [rbp+210h+Buffer]
0x1800f2669  lea     rcx, [rsp+310h+lpExistingFileName]
0x1800f266e  call    SczAllocFromSz
0x1800f2673  mov     edi, eax
0x1800f2675  test    eax, eax
0x1800f2677  jns     loc_1800F27EB
0x1800f267d  mov     edx, 288h
0x1800f2682  jmp     loc_1800F22F1
0x1800f2687  call    cs:__imp_GetLastError
0x1800f268e  nop     dword ptr [rax+rax+00h]
0x1800f2693  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f269a  mov     r14d, eax
0x1800f269d  test    rcx, rcx
0x1800f26a0  jz      short loc_1800F2719
0x1800f26a2  lea     rax, [rsp+310h+var_2C0]
0x1800f26a7  mov     [rsp+310h+var_2C0], rsi
0x1800f26ac  mov     [rsp+310h+var_2E8], rax
0x1800f26b1  lea     r9, aFailedToCopyFi_0; "Failed to copy file from: {} to {}"
0x1800f26b8  lea     rax, [rsp+310h+var_2D0]
0x1800f26bd  mov     [rsp+310h+var_2D0], rdi
0x1800f26c2  mov     ebx, 3
0x1800f26c7  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800f26cc  mov     r8d, ebx
0x1800f26cf  xor     edx, edx
0x1800f26d1  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800f26d6  test    r14d, r14d
0x1800f26d9  jg      short loc_1800F26E0
0x1800f26db  mov     eax, r14d
0x1800f26de  jmp     short loc_1800F26E9
0x1800f26e0  movzx   eax, r14w
0x1800f26e4  or      eax, 80070000h
0x1800f26e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f26f0  lea     r9, a0; ": {0}"
0x1800f26f7  mov     dword ptr [rsp+310h+var_2A0], eax
0x1800f26fb  mov     r8d, ebx
0x1800f26fe  lea     rax, [rsp+310h+var_2A0]
0x1800f2703  mov     dl, 1
0x1800f2705  mov     qword ptr [rsp+310h+var_2A8], rax
0x1800f270a  lea     rax, [rsp+310h+var_2A8]
0x1800f270f  mov     qword ptr [rsp+310h+var_2F0], rax; unsigned int
0x1800f2714  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f2719  test    r14d, r14d
0x1800f271c  jz      short loc_1800F2750
0x1800f271e  mov     rcx, [rbp+218h]; this
0x1800f2725  lea     r8, aOnecoreBaseCbs_121; "onecore\\base\\cbs\\core\\cbscorehelper"...
0x1800f272c  mov     r9d, r14d; char *
  ... truncated ...
```
