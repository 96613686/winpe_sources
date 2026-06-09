# FSLaunchExePrivilegedAction::Run(void)

- ea: `0x1800ad810`
- end: `0x1800adcc7`
- name: `?Run@FSLaunchExePrivilegedAction@@UEAAJXZ`
- size: `1207`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18002035c`
- `0x18008907c`
- `0x18008b918`
- `0x18008bc58`
- `0x18009ced0`
- `0x1800a3c50`
- `0x1800ad74c`
- `0x1800ad810`
- `0x1800c264c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800adbe4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800adbe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adbf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adbf4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800adc10`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800adc10`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800adbb3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800adbb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adc4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adc59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adc4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800adc59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ad923`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ad923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ada67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ada67`

## string_xrefs

- `0x1800ad888`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800ad977`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800ada3a`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800adb26`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800adbc1`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`
- `0x1800adc3a`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeprivilegedaction.cpp`

## pseudocode

```c
__int64 __fastcall FSLaunchExePrivilegedAction::Run(LPCWSTR *this)
{
  bool v2; // dl
  signed int IsFileMicrosoftSigned; // ebx
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rbx
  int v6; // r8d
  __int64 v7; // rdx
  LPCWSTR v8; // rdx
  char *v9; // r15
  void *v10; // r14
  __int64 v11; // rdx
  void *v12; // rsi
  __int64 v13; // rdx
  const char *v14; // r9
  signed int LastError; // eax
  int v16; // ebx
  unsigned __int64 v17; // rdx
  unsigned __int8 v18; // cl
  __int64 v19; // rcx
  FlightSettingsAPITelemetryClass *v20; // rax
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  LPWSTR lpCommandLine[3]; // [rsp+98h] [rbp-68h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B0h] [rbp-50h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  int v37; // [rsp+180h] [rbp+80h] BYREF
  DWORD ExitCode; // [rsp+188h] [rbp+88h] BYREF
  struct _FILETIME v39; // [rsp+190h] [rbp+90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+198h] [rbp+98h] BYREF

  v37 = 0;
  pv = &v37;
  LOBYTE(v31) = 1;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v27);
  v28 = -1;
  v29 = -1;
  IsFileMicrosoftSigned = FlightSettingsAPICommon::ExpandEnvironmentPath(this[7], &v27);
  v37 = IsFileMicrosoftSigned;
  if ( IsFileMicrosoftSigned >= 0 )
  {
    IsFileMicrosoftSigned = CabUtils::IsFileMicrosoftSigned(v27, v2);
    v37 = IsFileMicrosoftSigned;
    if ( IsFileMicrosoftSigned < 0 )
    {
      v4 = 87;
      goto LABEL_3;
    }
    if ( !FSAllowlist::IsValueInAllowlist(*((FSAllowlist **)this[17] + 5), this[7])
      && !FSAllowlist::IsValueInAllowlist(*((FSAllowlist **)this[17] + 5), v27) )
    {
      IsFileMicrosoftSigned = -2146698722;
      v37 = -2146698722;
      v4 = 90;
      goto LABEL_3;
    }
    if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(this + 14) )
    {
      v5 = this[14];
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v39 = 0;
      IsFileMicrosoftSigned = FlightSettingsAPICommon::StringToFileTime(v5, &v39, v6);
      if ( IsFileMicrosoftSigned < 0 )
      {
        v7 = 197;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
          (const char *)(unsigned int)IsFileMicrosoftSigned,
          bInheritHandles);
        v37 = IsFileMicrosoftSigned;
        v4 = 95;
        goto LABEL_3;
      }
      if ( !FlightSettingsAPICommon::TimeDiffInMs(SystemTimeAsFileTime, v39) )
      {
        IsFileMicrosoftSigned = -2146698721;
        v7 = 201;
        goto LABEL_14;
      }
      v37 = 0;
    }
    pv = 0;
    v31 = 0;
    v32 = 0;
    if ( ((_BYTE)this[13] & 1) == 0
      || (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(this[17] + 24) )
    {
      v9 = (char *)(this + 10);
      v8 = this[10];
    }
    else
    {
      v8 = (LPCWSTR)*((_QWORD *)this[17] + 6);
      v9 = (char *)(this + 10);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&pv, v8, -1);
    if ( ((_BYTE)this[13] & 2) != 0 )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
      v25 = -1;
      v26 = -1;
      v10 = pv;
      IsFileMicrosoftSigned = FlightSettingsAPICommon::ExpandEnvironmentPath((LPCWSTR)pv, &v24);
      v37 = IsFileMicrosoftSigned;
      if ( IsFileMicrosoftSigned < 0 )
      {
        v11 = 113;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
          (const char *)(unsigned int)IsFileMicrosoftSigned,
          bInheritHandles);
LABEL_51:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        goto LABEL_52;
      }
      v12 = v24;
      v24 = 0;
      v26 = 0;
      v25 = 0;
      if ( v10 )
        CoTaskMemFree(v10);
      pv = v12;
      v32 = -1;
      v31 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
    }
    else
    {
      v12 = pv;
    }
    v24 = 0;
    v25 = 0;
    v26 = 0;
    if ( ((_BYTE)this[13] & 4) != 0 )
    {
      IsFileMicrosoftSigned = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                                &v24,
                                L"powershell.exe Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process; %s",
                                v27);
      if ( IsFileMicrosoftSigned < 0 )
      {
        v11 = 122;
        goto LABEL_23;
      }
    }
    else
    {
      IsFileMicrosoftSigned = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                                &v24,
                                v27,
                                -1);
      if ( IsFileMicrosoftSigned < 0 )
      {
        v11 = 126;
        goto LABEL_23;
      }
    }
    memset(lpCommandLine, 0, sizeof(lpCommandLine));
    if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(v9) )
    {
      IsFileMicrosoftSigned = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                                lpCommandLine,
                                v24,
                                -1);
      v37 = IsFileMicrosoftSigned;
      if ( IsFileMicrosoftSigned < 0 )
      {
        v13 = 136;
        goto LABEL_36;
      }
    }
    else
    {
      IsFileMicrosoftSigned = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                                lpCommandLine,
                                L"%s %s",
                                v24,
                                v12);
      v37 = IsFileMicrosoftSigned;
      if ( IsFileMicrosoftSigned < 0 )
      {
        v13 = 132;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
          (const char *)(unsigned int)IsFileMicrosoftSigned,
          bInheritHandles);
LABEL_50:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpCommandLine);
        goto LABEL_51;
      }
    }
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( !CreateProcessW(0, lpCommandLine[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      IsFileMicrosoftSigned = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0x9B,
                                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fs"
                                              "launchexeprivilegedaction.cpp",
                                v14);
      goto LABEL_50;
    }
    ExitCode = WaitForSingleObject(ProcessInformation.hProcess, 1000 * *((_DWORD *)this + 27));
    if ( ExitCode )
    {
      LastError = GetLastError();
      IsFileMicrosoftSigned = LastError;
      if ( LastError > 0 )
      {
        v16 = (unsigned __int16)LastError;
LABEL_46:
        IsFileMicrosoftSigned = v16 | 0x80070000;
      }
    }
    else
    {
      GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
      IsFileMicrosoftSigned = ExitCode;
      if ( (int)ExitCode > 0 )
      {
        v16 = (unsigned __int16)ExitCode;
        goto LABEL_46;
      }
    }
    v37 = IsFileMicrosoftSigned;
    if ( IsFileMicrosoftSigned < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
        (const char *)(unsigned int)IsFileMicrosoftSigned,
        bInheritHandlesa);
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    goto LABEL_50;
  }
  v4 = 84;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeprivilegedaction.cpp",
    (const char *)(unsigned int)IsFileMicrosoftSigned,
    bInheritHandles);
LABEL_52:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v27);
  if ( v37 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v18, v17) )
  {
    v20 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v19,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::LaunchExePrivilegedActionFailed_(v20, v37);
  }
  return (unsigned int)IsFileMicrosoftSigned;
}

```

## disassembly

```asm
0x1800ad810  push    rbp
0x1800ad812  push    rbx
0x1800ad813  push    rsi
0x1800ad814  push    rdi
0x1800ad815  push    r13
0x1800ad817  push    r14
0x1800ad819  push    r15
0x1800ad81b  lea     rbp, [rsp-40h]
0x1800ad820  sub     rsp, 140h
0x1800ad827  mov     rdi, rcx
0x1800ad82a  xor     r13d, r13d
0x1800ad82d  mov     [rbp+70h+arg_0], r13d
0x1800ad834  lea     rax, [rbp+70h+arg_0]
0x1800ad83b  mov     [rbp+70h+pv], rax
0x1800ad83f  mov     byte ptr [rbp+70h+var_E8], 1
0x1800ad843  mov     [rsp+170h+var_108], r13
0x1800ad848  mov     [rsp+170h+var_100], r13
0x1800ad84d  mov     [rsp+170h+var_F8], r13
0x1800ad852  lea     rcx, [rsp+170h+var_108]
0x1800ad857  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ad85c  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ad860  mov     [rsp+170h+var_100], r14
0x1800ad865  mov     [rsp+170h+var_F8], r14
0x1800ad86a  lea     rdx, [rsp+170h+var_108]; unsigned __int16 **
0x1800ad86f  mov     rcx, [rdi+38h]; lpSrc
0x1800ad873  call    ?ExpandEnvironmentPath@FlightSettingsAPICommon@@SAJPEBGPEAPEAG@Z; FlightSettingsAPICommon::ExpandEnvironmentPath(ushort const *,ushort * *)
0x1800ad878  mov     ebx, eax
0x1800ad87a  mov     [rbp+70h+arg_0], eax
0x1800ad880  test    eax, eax
0x1800ad882  jns     short loc_1800AD8A0
0x1800ad884  lea     edx, [r13+54h]; void *
0x1800ad888  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ad88f  mov     r9d, ebx; char *
0x1800ad892  mov     rcx, [rbp+78h]; this
0x1800ad896  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad89b  jmp     loc_1800ADC7C
0x1800ad8a0  mov     rcx, [rsp+170h+var_108]; unsigned __int16 *
0x1800ad8a5  call    ?IsFileMicrosoftSigned@CabUtils@@SAJPEBG_N@Z; CabUtils::IsFileMicrosoftSigned(ushort const *,bool)
0x1800ad8aa  mov     ebx, eax
0x1800ad8ac  mov     [rbp+70h+arg_0], eax
0x1800ad8b2  test    eax, eax
0x1800ad8b4  jns     short loc_1800AD8BD
0x1800ad8b6  mov     edx, 57h ; 'W'
0x1800ad8bb  jmp     short loc_1800AD888
0x1800ad8bd  mov     rcx, [rdi+88h]
0x1800ad8c4  mov     rdx, [rdi+38h]; unsigned __int16 *
0x1800ad8c8  mov     rcx, [rcx+28h]; this
0x1800ad8cc  call    ?IsValueInAllowlist@FSAllowlist@@QEAA_NPEBG@Z; FSAllowlist::IsValueInAllowlist(ushort const *)
0x1800ad8d1  test    al, al
0x1800ad8d3  jnz     short loc_1800AD900
0x1800ad8d5  mov     rcx, [rdi+88h]
0x1800ad8dc  mov     rdx, [rsp+170h+var_108]; unsigned __int16 *
0x1800ad8e1  mov     rcx, [rcx+28h]; this
0x1800ad8e5  call    ?IsValueInAllowlist@FSAllowlist@@QEAA_NPEBG@Z; FSAllowlist::IsValueInAllowlist(ushort const *)
0x1800ad8ea  test    al, al
0x1800ad8ec  jnz     short loc_1800AD900
0x1800ad8ee  mov     ebx, 800BFA1Eh
0x1800ad8f3  mov     [rbp+70h+arg_0], ebx
0x1800ad8f9  mov     edx, 5Ah ; 'Z'
0x1800ad8fe  jmp     short loc_1800AD888
0x1800ad900  lea     rcx, [rdi+70h]
0x1800ad904  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x1800ad909  test    al, al
0x1800ad90b  jnz     loc_1800AD99A
0x1800ad911  mov     rbx, [rdi+70h]
0x1800ad915  mov     qword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800ad91c  lea     rcx, [rbp+70h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ad923  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ad929  mov     qword ptr [rbp+70h+arg_10.dwLowDateTime], r13
0x1800ad930  lea     rdx, [rbp+70h+arg_10]; struct _FILETIME *
0x1800ad937  mov     rcx, rbx; unsigned __int16 *
0x1800ad93a  call    ?StringToFileTime@FlightSettingsAPICommon@@SAJPEBGPEAU_FILETIME@@H@Z; FlightSettingsAPICommon::StringToFileTime(ushort const *,_FILETIME *,int)
0x1800ad93f  mov     ebx, eax
0x1800ad941  test    eax, eax
0x1800ad943  jns     short loc_1800AD94C
0x1800ad945  mov     edx, 0C5h
0x1800ad94a  jmp     short loc_1800AD96E
0x1800ad94c  mov     rdx, qword ptr [rbp+70h+arg_10.dwLowDateTime]; struct _FILETIME
0x1800ad953  mov     rcx, qword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x1800ad95a  call    ?TimeDiffInMs@FlightSettingsAPICommon@@SA_KU_FILETIME@@0@Z; FlightSettingsAPICommon::TimeDiffInMs(_FILETIME,_FILETIME)
0x1800ad95f  test    rax, rax
0x1800ad962  jnz     short loc_1800AD993
0x1800ad964  mov     ebx, 800BFA1Fh
0x1800ad969  mov     edx, 0C9h; void *
0x1800ad96e  mov     r9d, ebx; char *
0x1800ad971  mov     rcx, [rbp+78h]; this
0x1800ad975  mov     edi, ebx
0x1800ad977  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ad97e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad983  mov     [rbp+70h+arg_0], ebx
0x1800ad989  mov     edx, 5Fh ; '_'
0x1800ad98e  jmp     loc_1800AD888
0x1800ad993  mov     [rbp+70h+arg_0], r13d
0x1800ad99a  mov     [rbp+70h+pv], r13
0x1800ad99e  mov     [rbp+70h+var_E8], r13
0x1800ad9a2  mov     [rbp+70h+var_E0], r13
0x1800ad9a6  test    byte ptr [rdi+68h], 1
0x1800ad9aa  jz      short loc_1800AD9D1
0x1800ad9ac  mov     rcx, [rdi+88h]
0x1800ad9b3  add     rcx, 30h ; '0'
0x1800ad9b7  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x1800ad9bc  test    al, al
0x1800ad9be  jnz     short loc_1800AD9D1
0x1800ad9c0  mov     rax, [rdi+88h]
0x1800ad9c7  mov     rdx, [rax+30h]
0x1800ad9cb  lea     r15, [rdi+50h]
0x1800ad9cf  jmp     short loc_1800AD9D8
0x1800ad9d1  lea     r15, [rdi+50h]
0x1800ad9d5  mov     rdx, [r15]
0x1800ad9d8  mov     r8, r14
0x1800ad9db  lea     rcx, [rbp+70h+pv]
0x1800ad9df  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad9e4  test    byte ptr [rdi+68h], 2
0x1800ad9e8  jz      loc_1800ADA89
0x1800ad9ee  mov     [rsp+170h+var_120], r13
0x1800ad9f3  mov     [rsp+170h+var_118], r13
0x1800ad9f8  mov     [rsp+170h+var_110], r13
0x1800ad9fd  lea     rcx, [rsp+170h+var_120]
0x1800ada02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ada07  mov     [rsp+170h+var_118], r14
0x1800ada0c  mov     [rsp+170h+var_110], r14
0x1800ada11  lea     rdx, [rsp+170h+var_120]; unsigned __int16 **
0x1800ada16  mov     r14, [rbp+70h+pv]
0x1800ada1a  mov     rcx, r14; lpSrc
0x1800ada1d  call    ?ExpandEnvironmentPath@FlightSettingsAPICommon@@SAJPEBGPEAPEAG@Z; FlightSettingsAPICommon::ExpandEnvironmentPath(ushort const *,ushort * *)
0x1800ada22  mov     ebx, eax
0x1800ada24  mov     [rbp+70h+arg_0], eax
0x1800ada2a  test    eax, eax
0x1800ada2c  jns     short loc_1800ADA4B
0x1800ada2e  mov     edx, 71h ; 'q'; void *
0x1800ada33  mov     rcx, [rbp+78h]; this
0x1800ada37  mov     r9d, ebx; char *
0x1800ada3a  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800ada41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ada46  jmp     loc_1800ADC68
0x1800ada4b  mov     rsi, [rsp+170h+var_120]
0x1800ada50  mov     [rsp+170h+var_120], r13
0x1800ada55  mov     [rsp+170h+var_110], r13
0x1800ada5a  mov     [rsp+170h+var_118], r13
0x1800ada5f  test    r14, r14
0x1800ada62  jz      short loc_1800ADA6D
0x1800ada64  mov     rcx, r14; pv
0x1800ada67  call    cs:__imp_CoTaskMemFree
0x1800ada6d  mov     [rbp+70h+pv], rsi
0x1800ada71  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ada75  mov     [rbp+70h+var_E0], r14
0x1800ada79  mov     [rbp+70h+var_E8], r14
0x1800ada7d  lea     rcx, [rsp+170h+var_120]
0x1800ada82  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ada87  jmp     short loc_1800ADA8D
0x1800ada89  mov     rsi, [rbp+70h+pv]
0x1800ada8d  mov     [rsp+170h+var_120], r13
0x1800ada92  mov     [rsp+170h+var_118], r13
0x1800ada97  mov     [rsp+170h+var_110], r13
0x1800ada9c  lea     rcx, [rsp+170h+var_120]
0x1800adaa1  test    byte ptr [rdi+68h], 4
0x1800adaa5  jz      short loc_1800ADAC8
0x1800adaa7  mov     r8, [rsp+170h+var_108]
0x1800adaac  lea     rdx, aPowershellExeS; "powershell.exe Set-ExecutionPolicy -Exe"...
0x1800adab3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800adab8  mov     ebx, eax
0x1800adaba  test    eax, eax
0x1800adabc  jns     short loc_1800ADAE5
0x1800adabe  mov     edx, 7Ah ; 'z'
0x1800adac3  jmp     loc_1800ADA33
0x1800adac8  mov     r8, r14
0x1800adacb  mov     rdx, [rsp+170h+var_108]
0x1800adad0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800adad5  mov     ebx, eax
0x1800adad7  test    eax, eax
0x1800adad9  jns     short loc_1800ADAE5
0x1800adadb  mov     edx, 7Eh ; '~'
0x1800adae0  jmp     loc_1800ADA33
0x1800adae5  mov     [rbp+70h+lpCommandLine], r13
0x1800adae9  mov     [rbp+70h+var_D0], r13
0x1800adaed  mov     [rbp+70h+var_C8], r13
0x1800adaf1  mov     rcx, r15
0x1800adaf4  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x1800adaf9  lea     rcx, [rbp+70h+lpCommandLine]
0x1800adafd  test    al, al
0x1800adaff  jnz     short loc_1800ADB3E
0x1800adb01  mov     r9, rsi
0x1800adb04  mov     r8, [rsp+170h+var_120]
0x1800adb09  lea     rdx, aSS_5; "%s %s"
0x1800adb10  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800adb15  mov     ebx, eax
0x1800adb17  mov     [rbp+70h+arg_0], eax
0x1800adb1d  test    eax, eax
0x1800adb1f  jns     short loc_1800ADB5E
0x1800adb21  mov     edx, 84h; void *
0x1800adb26  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800adb2d  mov     r9d, ebx; char *
0x1800adb30  mov     rcx, [rbp+78h]; this
0x1800adb34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adb39  jmp     loc_1800ADC5F
0x1800adb3e  mov     r8, r14
0x1800adb41  mov     rdx, [rsp+170h+var_120]
0x1800adb46  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800adb4b  mov     ebx, eax
0x1800adb4d  mov     [rbp+70h+arg_0], eax
0x1800adb53  test    eax, eax
0x1800adb55  jns     short loc_1800ADB5E
0x1800adb57  mov     edx, 88h
0x1800adb5c  jmp     short loc_1800ADB26
0x1800adb5e  xorps   xmm0, xmm0
0x1800adb61  xor     eax, eax
0x1800adb63  movups  xmmword ptr [rbp+70h+ProcessInformation.hProcess], xmm0
0x1800adb67  mov     qword ptr [rbp+70h+ProcessInformation.dwProcessId], rax
0x1800adb6b  xor     edx, edx; Val
0x1800adb6d  lea     r8d, [rax+64h]; Size
0x1800adb71  lea     rcx, [rbp+70h+StartupInfo+4]; void *
0x1800adb75  call    memset_0
0x1800adb7a  mov     [rbp+70h+StartupInfo.cb], 68h ; 'h'
0x1800adb81  lea     rax, [rbp+70h+ProcessInformation]
0x1800adb85  mov     [rsp+170h+lpProcessInformation], rax; lpProcessInformation
0x1800adb8a  lea     rax, [rbp+70h+StartupInfo]
0x1800adb8e  mov     [rsp+170h+lpStartupInfo], rax; lpStartupInfo
0x1800adb93  mov     [rsp+170h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1800adb98  mov     [rsp+170h+lpEnvironment], r13; lpEnvironment
0x1800adb9d  mov     [rsp+170h+dwCreationFlags], r13d; dwCreationFlags
0x1800adba2  mov     [rsp+170h+bInheritHandles], r13d; int
0x1800adba7  xor     r9d, r9d; lpThreadAttributes
0x1800adbaa  xor     r8d, r8d; lpProcessAttributes
0x1800adbad  mov     rdx, [rbp+70h+lpCommandLine]; lpCommandLine
0x1800adbb1  xor     ecx, ecx; lpApplicationName
0x1800adbb3  call    cs:__imp_CreateProcessW
0x1800adbb9  test    eax, eax
0x1800adbbb  jnz     short loc_1800ADBD9
0x1800adbbd  mov     rcx, [rbp+78h]; this
0x1800adbc1  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800adbc8  mov     edx, 9Bh; void *
0x1800adbcd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800adbd2  mov     ebx, eax
0x1800adbd4  jmp     loc_1800ADC5F
0x1800adbd9  imul    edx, [rdi+6Ch], 3E8h; dwMilliseconds
0x1800adbe0  mov     rcx, [rbp+70h+ProcessInformation.hProcess]; hHandle
0x1800adbe4  call    cs:__imp_WaitForSingleObject
0x1800adbea  mov     [rbp+70h+ExitCode], eax
0x1800adbf0  test    eax, eax
0x1800adbf2  jz      short loc_1800ADC05
0x1800adbf4  call    cs:__imp_GetLastError
0x1800adbfa  mov     ebx, eax
0x1800adbfc  test    eax, eax
0x1800adbfe  jle     short loc_1800ADC29
0x1800adc00  movzx   ebx, ax
0x1800adc03  jmp     short loc_1800ADC23
0x1800adc05  lea     rdx, [rbp+70h+ExitCode]; lpExitCode
0x1800adc0c  mov     rcx, [rbp+70h+ProcessInformation.hProcess]; hProcess
0x1800adc10  call    cs:__imp_GetExitCodeProcess
0x1800adc16  mov     ebx, [rbp+70h+ExitCode]
0x1800adc1c  test    ebx, ebx
0x1800adc1e  jle     short loc_1800ADC29
0x1800adc20  movzx   ebx, bx
0x1800adc23  or      ebx, 80070000h
0x1800adc29  mov     [rbp+70h+arg_0], ebx
0x1800adc2f  test    ebx, ebx
0x1800adc31  jns     short loc_1800ADC4B
0x1800adc33  mov     rcx, [rbp+78h]; this
0x1800adc37  mov     r9d, ebx; char *
0x1800adc3a  lea     r8, aOnecoreBaseFli_89; "onecore\\base\\flighting\\flightsetting"...
0x1800adc41  mov     edx, 0B2h; void *
0x1800adc46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc4b  mov     rcx, [rbp+70h+ProcessInformation.hThread]; hObject
0x1800adc4f  call    cs:__imp_CloseHandle
0x1800adc55  mov     rcx, [rbp+70h+ProcessInformation.hProcess]; hObject
0x1800adc59  call    cs:__imp_CloseHandle
0x1800adc5f  lea     rcx, [rbp+70h+lpCommandLine]
0x1800adc63  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800adc68  lea     rcx, [rsp+170h+var_120]
0x1800adc6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800adc72  lea     rcx, [rbp+70h+pv]
0x1800adc76  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800adc7b  nop
0x1800adc7c  lea     rcx, [rsp+170h+var_108]
0x1800adc81  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800adc86  nop
0x1800adc87  cmp     [rbp+70h+arg_0], r13d
0x1800adc8e  jge     short loc_1800ADCB3
0x1800adc90  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800adc95  test    al, al
0x1800adc97  jz      short loc_1800ADCB3
0x1800adc99  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800adca0  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800adca5  mov     edx, [rbp+70h+arg_0]; int
0x1800adcab  mov     rcx, rax; this
0x1800adcae  call    ?LaunchExePrivilegedActionFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::LaunchExePrivilegedActionFailed_(long)
0x1800adcb3  mov     eax, ebx
0x1800adcb5  add     rsp, 140h
0x1800adcbc  pop     r15
0x1800adcbe  pop     r14
0x1800adcc0  pop     r13
0x1800adcc2  pop     rdi
0x1800adcc3  pop     rsi
0x1800adcc4  pop     rbx
0x1800adcc5  pop     rbp
0x1800adcc6  retn
```
