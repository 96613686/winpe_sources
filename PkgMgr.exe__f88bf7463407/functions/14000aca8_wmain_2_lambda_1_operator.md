# _wmain_::_2_::_lambda_1_::operator()

- ea: `0x14000aca8`
- end: `0x14000b44e`
- name: `_wmain_::_2_::_lambda_1_::operator()`
- size: `1958`
- prototype: `__int64 __fastcall(wchar_t ***)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d734`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000726c`
- `0x140007524`
- `0x1400092fc`
- `0x14000a1dc`
- `0x14000aab4`
- `0x14000ab58`
- `0x14000aca8`
- `0x14000b454`
- `0x14000bf34`
- `0x14000c384`
- `0x14000ccac`
- `0x14000d410`
- `0x140011100`
- `0x1400113d4`
- `0x140011d50`
- `0x140013288`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000aeb6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000aeb6`

## string_xrefs

- `0x14000b2ba`: `Failed to allocate memory for command line.`
- `0x14000b31e`: `Failed to allocate memory for command line.`
- `0x14000ae3d`: `Failed adding backslash to module path {}`
- `0x14000af0d`: `Failed to add global dism options to the command line.`
- `0x14000b249`: `Failed to add global dism options to the command line.`
- `0x14000afb7`: `Failed installing package {}`
- `0x14000b02c`: `Failed uninstalling package(s)`
- `0x14000b0b0`: `Failed installing selectable updates`
- `0x14000b131`: `Failed uninstalling selectable updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wmain_::_2_::_lambda_1_::operator()(wchar_t ***a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  int started; // eax
  int v5; // edx
  __int64 v6; // rdx
  int ModulePath; // eax
  int v8; // edx
  int v9; // eax
  int v10; // edx
  wchar_t *v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rcx
  int v14; // edx
  int v15; // eax
  unsigned int v16; // r12d
  int v17; // edx
  __int64 v18; // rdx
  wchar_t **v19; // rdx
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  int v24; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // edx
  int v31; // eax
  int v32; // edx
  int v33; // eax
  int v34; // edx
  int v35; // eax
  int v36; // edx
  int v37; // eax
  __int64 v38; // rcx
  int v39; // edx
  int v41; // [rsp+20h] [rbp-60h]
  int v42[2]; // [rsp+30h] [rbp-50h] BYREF
  int v43[2]; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *v44; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v45[2]; // [rsp+48h] [rbp-38h] BYREF
  int v46; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *v47; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v48; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v45[1] = -2;
  v46 = 0;
  v48 = 0;
  v44 = 0;
  v47 = 0;
  v45[0] = 0;
  v2 = CConfig::ParseCommandLine(*a1, *(_DWORD *)a1[1], (wchar_t **const)*a1[2]);
  v3 = v2;
  if ( !v2 )
  {
    if ( (*a1)[30] )
    {
      started = StartLogs((struct CConfig *)*a1);
      v3 = started;
      if ( started < 0 )
      {
        v46 = started;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed enabling tracing");
          *(_QWORD *)v43 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v5,
            3,
            (unsigned int)": {}",
            (__int64)v43);
        }
        v6 = 398;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
          (const char *)v3,
          v41);
        goto LABEL_81;
      }
    }
    ModulePath = GetModulePath(&v44);
    v3 = ModulePath;
    if ( ModulePath < 0 )
    {
      v46 = ModulePath;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting module location");
        *(_QWORD *)v43 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v8,
          3,
          (unsigned int)": {}",
          (__int64)v43);
      }
      v6 = 401;
      goto LABEL_10;
    }
    v9 = SczEnsureBackslashTerminated(&v44);
    v3 = v9;
    if ( v9 < 0 )
    {
      v46 = v9;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v43 = v44;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed adding backslash to module path {}",
          (__int64)v43);
        *(_QWORD *)v42 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          3,
          (unsigned int)": {}",
          (__int64)v42);
      }
      v6 = 402;
      goto LABEL_10;
    }
    v11 = v44;
    v12 = (unsigned int)WdsLoad(v44, 0);
    LogAdapter::TraceAtLevelIfFailed<long,>(
      3,
      v12,
      "Unable to load and initialize WDS, continuing without text logging support.");
    LogAdapter::TraceAtLevel<>(v13, &word_14002D1C8);
    *(_QWORD *)v42 = GetCommandLineW();
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        1,
        (unsigned int)"pkgmgr called with: \"{}\"",
        (__int64)v42);
    }
    v15 = AddGlobalOptions(&v47, v11, (struct CConfig *)*a1);
    v16 = v15;
    if ( v15 < 0 )
    {
      v46 = v15;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to add global dism options to the command line.");
        *(_QWORD *)v42 = &v46;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v17,
          3,
          (unsigned int)": {}",
          (__int64)v42);
      }
      v18 = 414;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
        (const char *)v16,
        v41);
      v3 = v16;
      goto LABEL_81;
    }
    v19 = *a1;
    if ( !*((_DWORD *)*a1 + 82) )
    {
      if ( *((_DWORD *)v19 + 38) )
      {
        v20 = InstallPackage(&v47, *v19);
        v16 = v20;
        if ( v20 < 0 )
        {
          v46 = v20;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v42 = **a1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed installing package {}",
              (__int64)v42);
            *(_QWORD *)v43 = &v46;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v21,
              3,
              (unsigned int)": {}",
              (__int64)v43);
          }
          v18 = 420;
          goto LABEL_25;
        }
      }
      else if ( *((_DWORD *)v19 + 39) )
      {
        v22 = UninstallPackages(&v47, *v19, (struct CCbsStringArray *)(v19 + 11));
        v16 = v22;
        if ( v22 < 0 )
        {
          v46 = v22;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed uninstalling package(s)");
            *(_QWORD *)v42 = &v46;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v23,
              3,
              (unsigned int)": {}",
              (__int64)v42);
          }
          v18 = 425;
          goto LABEL_25;
        }
      }
      else if ( *((_DWORD *)v19 + 56) )
      {
        v24 = ProcessSelectableUpdates(&v47, *v19, v19[9], (struct CCbsStringArray *)(v19 + 20), 1);
        v16 = v24;
        if ( v24 < 0 )
        {
          v46 = v24;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed installing selectable updates");
            *(_QWORD *)v42 = &v46;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              3,
              (unsigned int)": {}",
              (__int64)v42);
          }
          v18 = 430;
          goto LABEL_25;
        }
      }
      else
      {
        if ( !*((_DWORD *)v19 + 57) )
          goto LABEL_57;
        v26 = ProcessSelectableUpdates(&v47, *v19, v19[9], (struct CCbsStringArray *)(v19 + 20), 0);
        v16 = v26;
        if ( v26 < 0 )
        {
          v46 = v26;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed uninstalling selectable updates");
            *(_QWORD *)v42 = &v46;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v27,
              3,
              (unsigned int)": {}",
              (__int64)v42);
          }
          v18 = 435;
          goto LABEL_25;
        }
      }
      v28 = StartDism(v47, &v46, &v48);
      v16 = v28;
      if ( v28 < 0 )
      {
        v46 = v28;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to start dism.exe.");
          *(_QWORD *)v42 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v30,
            3,
            (unsigned int)": {}",
            (__int64)v42);
        }
        v18 = 442;
        goto LABEL_25;
      }
      if ( v46 )
      {
        if ( v48 == 3010 )
        {
          *(_DWORD *)a1[4] = 1;
          LogAdapter::TraceAtLevel<>(v29, "Dism.exe returned: ERROR_SUCCESS_REBOOT_REQUIRED");
        }
        else if ( (int)v48 > 0 )
        {
          LODWORD(v12) = (unsigned __int16)v48 | 0x80070000;
        }
        else
        {
          LODWORD(v12) = v48;
        }
      }
    }
LABEL_57:
    if ( (*a1)[29] )
    {
      v31 = AddGlobalOptions(&v47, v11, (struct CConfig *)*a1);
      v3 = v31;
      if ( v31 < 0 )
      {
        v46 = v31;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to add global dism options to the command line.");
          *(_QWORD *)v42 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v32,
            3,
            (unsigned int)": {}",
            (__int64)v42);
        }
        v6 = 460;
        goto LABEL_10;
      }
      v33 = SczAllocFormatted(v45, L" /apply-unattend:\"%s\"", (*a1)[29]);
      v3 = v33;
      if ( v33 < 0 )
      {
        v46 = v33;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v42 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v34,
            3,
            (unsigned int)": {}",
            (__int64)v42);
        }
        v6 = 461;
        goto LABEL_10;
      }
      v35 = SczAllocConcatSz(&v47, v45[0]);
      v3 = v35;
      if ( v35 < 0 )
      {
        v46 = v35;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v42 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v36,
            3,
            (unsigned int)": {}",
            (__int64)v42);
        }
        v6 = 462;
        goto LABEL_10;
      }
      v37 = StartDism(v47, &v46, &v48);
      v3 = v37;
      if ( v37 < 0 )
      {
        v46 = v37;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to start dism.exe.");
          *(_QWORD *)v42 = &v46;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v39,
            3,
            (unsigned int)": {}",
            (__int64)v42);
        }
        v6 = 463;
        goto LABEL_10;
      }
      if ( v46 )
      {
        if ( v48 == 3010 )
        {
          *(_DWORD *)a1[4] = 1;
          LogAdapter::TraceAtLevel<>(v38, "Dism.exe returned: ERROR_SUCCESS_REBOOT_REQUIRED");
        }
        else if ( (int)v48 > 0 )
        {
          LODWORD(v12) = (unsigned __int16)v48 | 0x80070000;
        }
        else
        {
          LODWORD(v12) = v48;
        }
      }
    }
    v3 = v12;
    goto LABEL_81;
  }
  if ( v2 == 1 )
    v3 = 0;
  else
    *(_DWORD *)a1[3] = 1;
LABEL_81:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v45);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v47);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v44);
  return v3;
}

```

## disassembly

```asm
0x14000aca8  mov     rax, rsp
0x14000acab  push    rbp
0x14000acac  push    rdi
0x14000acad  push    r12
0x14000acaf  push    r13
0x14000acb1  push    r14
0x14000acb3  mov     rbp, rsp
0x14000acb6  sub     rsp, 80h
0x14000acbd  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x14000acc5  mov     [rax+10h], rbx
0x14000acc9  mov     [rax+18h], rsi
0x14000accd  mov     rax, cs:__security_cookie
0x14000acd4  xor     rax, rsp
0x14000acd7  mov     [rbp+var_10], rax
0x14000acdb  mov     rsi, rcx
0x14000acde  xor     r13d, r13d
0x14000ace1  mov     [rbp+var_28], r13d
0x14000ace5  mov     [rbp+var_18], r13d
0x14000ace9  mov     [rbp+var_40], r13
0x14000aced  mov     [rbp+var_20], r13
0x14000acf1  mov     [rbp+var_38], r13
0x14000acf5  mov     r8, [rcx+10h]
0x14000acf9  mov     rdx, [rcx+8]
0x14000acfd  mov     r8, [r8]; wchar_t **
0x14000ad00  mov     edx, [rdx]; int
0x14000ad02  mov     rcx, [rcx]; this
0x14000ad05  call    ?ParseCommandLine@CConfig@@QEAAJHQEAPEA_W@Z; CConfig::ParseCommandLine(int,wchar_t * * const)
0x14000ad0a  mov     ebx, eax
0x14000ad0c  test    eax, eax
0x14000ad0e  jz      short loc_14000AD2C
0x14000ad10  cmp     eax, 1
0x14000ad13  jnz     short loc_14000AD1D
0x14000ad15  mov     ebx, r13d
0x14000ad18  jmp     loc_14000B407
0x14000ad1d  mov     rax, [rsi+18h]
0x14000ad21  mov     dword ptr [rax], 1
0x14000ad27  jmp     loc_14000B407
0x14000ad2c  mov     rcx, [rsi]; this
0x14000ad2f  cmp     [rcx+0F0h], r13
0x14000ad36  jz      short loc_14000ADAC
0x14000ad38  call    ?StartLogs@@YAJPEAVCConfig@@@Z; StartLogs(CConfig *)
0x14000ad3d  mov     ebx, eax
0x14000ad3f  test    eax, eax
0x14000ad41  jns     short loc_14000ADAC
0x14000ad43  mov     [rbp+var_28], eax
0x14000ad46  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ad4d  test    rcx, rcx
0x14000ad50  jz      short loc_14000AD8F
0x14000ad52  lea     r9, aFailedEnabling_0; "Failed enabling tracing"
0x14000ad59  mov     edi, 3
0x14000ad5e  mov     r8d, edi
0x14000ad61  xor     edx, edx
0x14000ad63  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000ad68  lea     rax, [rbp+var_28]
0x14000ad6c  mov     qword ptr [rbp+var_48], rax
0x14000ad70  lea     rax, [rbp+var_48]
0x14000ad74  mov     qword ptr [rsp+80h+var_60], rax; int
0x14000ad79  lea     r9, asc_14002D4FC; ": {}"
0x14000ad80  mov     r8d, edi
0x14000ad83  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ad8a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ad8f  mov     edx, 18Eh; void *
0x14000ad94  mov     rcx, [rbp+28h]; this
0x14000ad98  mov     r9d, ebx; char *
0x14000ad9b  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000ada2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ada7  jmp     loc_14000B407
0x14000adac  lea     rcx, [rbp+var_40]; wchar_t **
0x14000adb0  call    ?GetModulePath@@YAJPEAPEA_W@Z; GetModulePath(wchar_t * *)
0x14000adb5  mov     ebx, eax
0x14000adb7  test    eax, eax
0x14000adb9  jns     short loc_14000AE0E
0x14000adbb  mov     [rbp+var_28], eax
0x14000adbe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000adc5  test    rcx, rcx
0x14000adc8  jz      short loc_14000AE07
0x14000adca  lea     r9, aFailedGettingM_0; "Failed getting module location"
0x14000add1  mov     edi, 3
0x14000add6  mov     r8d, edi
0x14000add9  xor     edx, edx
0x14000addb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000ade0  lea     rax, [rbp+var_28]
0x14000ade4  mov     qword ptr [rbp+var_48], rax
0x14000ade8  lea     rax, [rbp+var_48]
0x14000adec  mov     qword ptr [rsp+80h+var_60], rax
0x14000adf1  lea     r9, asc_14002D4FC; ": {}"
0x14000adf8  mov     r8d, edi
0x14000adfb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ae02  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ae07  mov     edx, 191h
0x14000ae0c  jmp     short loc_14000AD94
0x14000ae0e  lea     rcx, [rbp+var_40]
0x14000ae12  call    SczEnsureBackslashTerminated
0x14000ae17  mov     ebx, eax
0x14000ae19  test    eax, eax
0x14000ae1b  jns     short loc_14000AE84
0x14000ae1d  mov     [rbp+var_28], eax
0x14000ae20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ae27  test    rcx, rcx
0x14000ae2a  jz      short loc_14000AE7A
0x14000ae2c  mov     rdx, [rbp+var_40]
0x14000ae30  mov     qword ptr [rbp+var_48], rdx
0x14000ae34  lea     rax, [rbp+var_48]
0x14000ae38  mov     qword ptr [rsp+80h+var_60], rax
0x14000ae3d  lea     r9, aFailedAddingBa; "Failed adding backslash to module path "...
0x14000ae44  mov     edi, 3
0x14000ae49  mov     r8d, edi
0x14000ae4c  xor     edx, edx
0x14000ae4e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000ae53  lea     rax, [rbp+var_28]
0x14000ae57  mov     qword ptr [rbp+var_50], rax
0x14000ae5b  lea     rax, [rbp+var_50]
0x14000ae5f  mov     qword ptr [rsp+80h+var_60], rax
0x14000ae64  lea     r9, asc_14002D4FC; ": {}"
0x14000ae6b  mov     r8d, edi
0x14000ae6e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ae75  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ae7a  mov     edx, 192h
0x14000ae7f  jmp     loc_14000AD94
0x14000ae84  xor     edx, edx; HINSTANCE
0x14000ae86  mov     rbx, [rbp+var_40]
0x14000ae8a  mov     rcx, rbx; wchar_t *
0x14000ae8d  call    ?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z; WdsLoad(wchar_t const *,HINSTANCE__ *)
0x14000ae92  mov     r14d, eax
0x14000ae95  lea     r8, aUnableToLoadAn; "Unable to load and initialize WDS, cont"...
0x14000ae9c  mov     edx, eax
0x14000ae9e  mov     edi, 3
0x14000aea3  mov     ecx, edi
0x14000aea5  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x14000aeaa  lea     rdx, word_14002D1C8
0x14000aeb1  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x14000aeb6  call    cs:__imp_GetCommandLineW
0x14000aebc  mov     qword ptr [rbp+var_50], rax
0x14000aec0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000aec7  test    rcx, rcx
0x14000aeca  jz      short loc_14000AEE8
0x14000aecc  lea     rax, [rbp+var_50]
0x14000aed0  mov     qword ptr [rsp+80h+var_60], rax
0x14000aed5  lea     r9, aPkgmgrCalledWi; "pkgmgr called with: \"{}\""
0x14000aedc  lea     r8d, [rdi-2]
0x14000aee0  mov     dl, r8b
0x14000aee3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000aee8  mov     r8, [rsi]; struct CConfig *
0x14000aeeb  mov     rdx, rbx; wchar_t *
0x14000aeee  lea     rcx, [rbp+var_20]; wchar_t **
0x14000aef2  call    ?AddGlobalOptions@@YAJPEAPEA_WPEA_WPEAVCConfig@@@Z; AddGlobalOptions(wchar_t * *,wchar_t *,CConfig *)
0x14000aef7  mov     r12d, eax
0x14000aefa  test    eax, eax
0x14000aefc  jns     short loc_14000AF65
0x14000aefe  mov     [rbp+var_28], eax
0x14000af01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000af08  test    rcx, rcx
0x14000af0b  jz      short loc_14000AF45
0x14000af0d  lea     r9, aFailedToAddGlo; "Failed to add global dism options to th"...
0x14000af14  mov     r8d, edi
0x14000af17  xor     edx, edx
0x14000af19  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000af1e  lea     rax, [rbp+var_28]
0x14000af22  mov     qword ptr [rbp+var_50], rax
0x14000af26  lea     rax, [rbp+var_50]
0x14000af2a  mov     qword ptr [rsp+80h+var_60], rax; int
0x14000af2f  lea     r9, asc_14002D4FC; ": {}"
0x14000af36  mov     r8d, edi
0x14000af39  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000af40  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000af45  mov     edx, 19Eh; void *
0x14000af4a  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000af51  mov     r9d, r12d; char *
0x14000af54  mov     rcx, [rbp+28h]; this
0x14000af58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000af5d  mov     ebx, r12d
0x14000af60  jmp     loc_14000B407
0x14000af65  mov     rdx, [rsi]
0x14000af68  cmp     [rdx+148h], r13d
0x14000af6f  jnz     loc_14000B218
0x14000af75  cmp     [rdx+98h], r13d
0x14000af7c  jz      short loc_14000AFF9
0x14000af7e  mov     rdx, [rdx]; wchar_t *
0x14000af81  lea     rcx, [rbp+var_20]; wchar_t **
0x14000af85  call    ?InstallPackage@@YAJPEAPEA_WPEB_W@Z; InstallPackage(wchar_t * *,wchar_t const *)
0x14000af8a  mov     r12d, eax
0x14000af8d  test    eax, eax
0x14000af8f  jns     loc_14000B173
0x14000af95  mov     [rbp+var_28], eax
0x14000af98  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000af9f  test    rcx, rcx
0x14000afa2  jz      short loc_14000AFEF
0x14000afa4  mov     rdx, [rsi]
0x14000afa7  mov     r8, [rdx]
0x14000afaa  mov     qword ptr [rbp+var_50], r8
0x14000afae  lea     rax, [rbp+var_50]
0x14000afb2  mov     qword ptr [rsp+80h+var_60], rax
0x14000afb7  lea     r9, aFailedInstalli_0; "Failed installing package {}"
0x14000afbe  mov     r8d, edi
0x14000afc1  xor     edx, edx
0x14000afc3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000afc8  lea     rax, [rbp+var_28]
0x14000afcc  mov     qword ptr [rbp+var_48], rax
0x14000afd0  lea     rax, [rbp+var_48]
0x14000afd4  mov     qword ptr [rsp+80h+var_60], rax
0x14000afd9  lea     r9, asc_14002D4FC; ": {}"
0x14000afe0  mov     r8d, edi
0x14000afe3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000afea  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000afef  mov     edx, 1A4h
0x14000aff4  jmp     loc_14000AF4A
0x14000aff9  cmp     [rdx+9Ch], r13d
0x14000b000  jz      short loc_14000B06E
0x14000b002  lea     r8, [rdx+58h]; struct CCbsStringArray *
0x14000b006  mov     rdx, [rdx]; wchar_t *
0x14000b009  lea     rcx, [rbp+var_20]; wchar_t **
0x14000b00d  call    ?UninstallPackages@@YAJPEAPEA_WPEB_WAEAVCCbsStringArray@@@Z; UninstallPackages(wchar_t * *,wchar_t const *,CCbsStringArray &)
0x14000b012  mov     r12d, eax
0x14000b015  test    eax, eax
0x14000b017  jns     loc_14000B173
0x14000b01d  mov     [rbp+var_28], eax
0x14000b020  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b027  test    rcx, rcx
0x14000b02a  jz      short loc_14000B064
0x14000b02c  lea     r9, aFailedUninstal_0; "Failed uninstalling package(s)"
0x14000b033  mov     r8d, edi
0x14000b036  xor     edx, edx
0x14000b038  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b03d  lea     rax, [rbp+var_28]
0x14000b041  mov     qword ptr [rbp+var_50], rax
0x14000b045  lea     rax, [rbp+var_50]
0x14000b049  mov     qword ptr [rsp+80h+var_60], rax
0x14000b04e  lea     r9, asc_14002D4FC; ": {}"
0x14000b055  mov     r8d, edi
0x14000b058  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b05f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b064  mov     edx, 1A9h
0x14000b069  jmp     loc_14000AF4A
0x14000b06e  cmp     [rdx+0E0h], r13d
0x14000b075  jz      short loc_14000B0F2
0x14000b077  lea     r9, [rdx+0A0h]; struct CCbsStringArray *
0x14000b07e  mov     [rsp+80h+var_60], 1; int
0x14000b086  mov     r8, [rdx+48h]; wchar_t *
0x14000b08a  mov     rdx, [rdx]; wchar_t *
0x14000b08d  lea     rcx, [rbp+var_20]; wchar_t **
0x14000b091  call    ?ProcessSelectableUpdates@@YAJPEAPEA_WPEB_W1AEAVCCbsStringArray@@H@Z; ProcessSelectableUpdates(wchar_t * *,wchar_t const *,wchar_t const *,CCbsStringArray &,int)
0x14000b096  mov     r12d, eax
0x14000b099  test    eax, eax
0x14000b09b  jns     loc_14000B173
0x14000b0a1  mov     [rbp+var_28], eax
0x14000b0a4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b0ab  test    rcx, rcx
0x14000b0ae  jz      short loc_14000B0E8
0x14000b0b0  lea     r9, aFailedInstalli; "Failed installing selectable updates"
0x14000b0b7  mov     r8d, edi
0x14000b0ba  xor     edx, edx
0x14000b0bc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b0c1  lea     rax, [rbp+var_28]
0x14000b0c5  mov     qword ptr [rbp+var_50], rax
0x14000b0c9  lea     rax, [rbp+var_50]
0x14000b0cd  mov     qword ptr [rsp+80h+var_60], rax
0x14000b0d2  lea     r9, asc_14002D4FC; ": {}"
0x14000b0d9  mov     r8d, edi
0x14000b0dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b0e3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b0e8  mov     edx, 1AEh
0x14000b0ed  jmp     loc_14000AF4A
0x14000b0f2  cmp     [rdx+0E4h], r13d
0x14000b0f9  jz      loc_14000B218
0x14000b0ff  lea     r9, [rdx+0A0h]; struct CCbsStringArray *
0x14000b106  mov     [rsp+80h+var_60], r13d; int
0x14000b10b  mov     r8, [rdx+48h]; wchar_t *
0x14000b10f  mov     rdx, [rdx]; wchar_t *
0x14000b112  lea     rcx, [rbp+var_20]; wchar_t **
0x14000b116  call    ?ProcessSelectableUpdates@@YAJPEAPEA_WPEB_W1AEAVCCbsStringArray@@H@Z; ProcessSelectableUpdates(wchar_t * *,wchar_t const *,wchar_t const *,CCbsStringArray &,int)
0x14000b11b  mov     r12d, eax
0x14000b11e  test    eax, eax
0x14000b120  jns     short loc_14000B173
0x14000b122  mov     [rbp+var_28], eax
0x14000b125  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b12c  test    rcx, rcx
0x14000b12f  jz      short loc_14000B169
0x14000b131  lea     r9, aFailedUninstal; "Failed uninstalling selectable updates"
0x14000b138  mov     r8d, edi
0x14000b13b  xor     edx, edx
0x14000b13d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000b142  lea     rax, [rbp+var_28]
0x14000b146  mov     qword ptr [rbp+var_50], rax
0x14000b14a  lea     rax, [rbp+var_50]
0x14000b14e  mov     qword ptr [rsp+80h+var_60], rax
0x14000b153  lea     r9, asc_14002D4FC; ": {}"
0x14000b15a  mov     r8d, edi
0x14000b15d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000b164  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000b169  mov     edx, 1B3h
0x14000b16e  jmp     loc_14000AF4A
0x14000b173  lea     r8, [rbp+var_18]; unsigned int *
0x14000b177  lea     rdx, [rbp+var_28]; int *
0x14000b17b  mov     rcx, [rbp+var_20]; wchar_t *
0x14000b17f  call    ?StartDism@@YAJPEA_WPEAHPEAK@Z; StartDism(wchar_t *,int *,ulong *)
0x14000b184  mov     r12d, eax
0x14000b187  test    eax, eax
0x14000b189  jns     short loc_14000B1DC
0x14000b18b  mov     [rbp+var_28], eax
0x14000b18e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
