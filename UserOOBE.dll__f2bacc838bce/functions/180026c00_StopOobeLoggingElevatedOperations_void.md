# StopOobeLoggingElevatedOperations(void)

- ea: `0x180026c00`
- end: `0x180027054`
- name: `?StopOobeLoggingElevatedOperations@@YAXXZ`
- size: `1108`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800232b0`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x18000a5c8`
- `0x18000aab8`
- `0x18000e270`
- `0x18000e580`
- `0x1800109f0`
- `0x180018c98`
- `0x18001f168`
- `0x180021b8c`
- `0x180025b8c`
- `0x180026600`
- `0x1800269d0`
- `0x180026c00`
- `0x180027978`
- `0x1800279b8`
- `0x18004b6e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026e31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026f13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026f13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026ec8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026ec8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026e74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026e74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026f7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026fa3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026fd0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026fa3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026fd0`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026c68`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180026c68`

## string_xrefs

- `0x180026fc4`: `RestoredWallPaperFullPath`
- `0x180026cb3`: `ETWAutoLoggerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void StopOobeLoggingElevatedOperations(void)
{
  ULONG v0; // eax
  int RedirectionKeyPath; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  unsigned int v5; // eax
  bool v6; // bl
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v13; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v23; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[16]; // [rsp+70h] [rbp-90h] BYREF
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1138h] [rbp+1038h]

  memset_0(&Properties, 0, 0x107Cu);
  Properties.Wnode.BufferSize = 4220;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 2170;
  v0 = ControlTraceW(0, L"CloudExperienceHostOobe", &Properties, 1u);
  if ( v0 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v0,
      phkResult);
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"ETWAutoLoggerPath",
                         L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResult);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v23,
      L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger",
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpSubKey,
      &v23);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
    if ( !lpSubKey )
      wil::details::in1diag3::_Log_NullAlloc(retaddr, v2, v3, v4);
  }
  hKey = 0;
  if ( lpSubKey )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    if ( v5 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
        (const char *)v5,
        phkResulta);
    }
    else
    {
      hkey = 0;
      pvData = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      if ( !RegOpenKeyExW(hKey, L"CloudExperienceHostOobe", 0, 0x2001Fu, &hkey)
        && !RegGetValueW(hkey, 0, L"Start", 0x20000018u, 0, &pvData, &cbData)
        && pvData == 1 )
      {
        goto LABEL_18;
      }
      if ( CompareStringOrdinal(lpSubKey, -1, L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger", -1, 1) != 2 )
      {
        v6 = 0;
        v23 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v23,
          0);
        v7 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\CloudExperienceHostOobe",
               0,
               0x2001Fu,
               &v23);
        if ( v7 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x42,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
            (const char *)v7,
            phkResultb);
        }
        else if ( !RegGetValueW(v23, 0, L"Start", 0x20000018u, 0, &pvData, &cbData) )
        {
          v6 = pvData == 1;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        if ( v6 )
        {
LABEL_18:
          v8 = RegSetValueExW(hkey, L"Start", 0, 4u, Data, cbData);
          if ( v8 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
              (const char *)v8,
              phkResultc);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  LOBYTE(v2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl'::`2'::impl,
    v2);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", 0, 0x2001Bu, &hkey);
  v10 = retaddr;
  if ( v9 )
  {
    v11 = 84;
LABEL_27:
    wil::details::in1diag3::_Log_Win32(
      v10,
      (void *)v11,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v9,
      phkResultd);
    goto LABEL_28;
  }
  v12 = RegDeleteValueW(hkey, L"RestoreStatus");
  if ( v12 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v12,
      phkResultd);
  v9 = RegDeleteValueW(hkey, L"RestoredWallPaperFullPath");
  v10 = retaddr;
  if ( v9 )
  {
    v11 = 87;
    goto LABEL_27;
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>();
  v13 = OOBE::CompleteTime::SetAsCurrentTime();
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)(unsigned int)v13,
      phkResultd);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180026c00  push    rbp
0x180026c02  push    rbx
0x180026c03  push    rsi
0x180026c04  push    r12
0x180026c06  push    r14
0x180026c08  lea     rbp, [rsp-1010h]
0x180026c10  mov     eax, 1110h
0x180026c15  call    _alloca_probe
0x180026c1a  sub     rsp, rax
0x180026c1d  mov     rax, cs:__security_cookie
0x180026c24  xor     rax, rsp
0x180026c27  mov     [rbp+1030h+var_30], rax
0x180026c2e  mov     ebx, 107Ch
0x180026c33  mov     r8d, ebx; Size
0x180026c36  xor     edx, edx; Val
0x180026c38  lea     rcx, [rbp+1030h+Properties]; void *
0x180026c3c  call    memset_0
0x180026c41  mov     [rbp+1030h+Properties.Wnode.BufferSize], ebx
0x180026c44  mov     [rbp+1030h+Properties.LoggerNameOffset], 78h ; 'x'
0x180026c4b  mov     [rbp+1030h+Properties.LogFileNameOffset], 87Ah
0x180026c52  mov     r14d, 1
0x180026c58  mov     r9d, r14d; ControlCode
0x180026c5b  lea     r8, [rbp+1030h+Properties]; Properties
0x180026c5f  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x180026c66  xor     ecx, ecx; TraceHandle
0x180026c68  call    cs:__imp_ControlTraceW
0x180026c6e  mov     rcx, [rbp+1038h]; this
0x180026c75  lea     rsi, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\StopO"...
0x180026c7c  test    eax, eax
0x180026c7e  jz      short loc_180026C8F
0x180026c80  mov     r9d, eax; char *
0x180026c83  mov     r8, rsi; unsigned int
0x180026c86  lea     edx, [r14+1Eh]; void *
0x180026c8a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026c8f  mov     [rsp+1130h+lpSubKey], 0
0x180026c98  xor     edx, edx
0x180026c9a  lea     rcx, [rsp+1130h+lpSubKey]
0x180026c9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026ca4  lea     r8, [rsp+1130h+lpSubKey]; unsigned __int16 **
0x180026ca9  lea     rbx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180026cb0  mov     rdx, rbx; unsigned __int16 *
0x180026cb3  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x180026cba  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180026cbf  mov     rcx, [rbp+1038h]; this
0x180026cc6  test    eax, eax
0x180026cc8  jns     short loc_180026D18
0x180026cca  mov     r9d, eax; char *
0x180026ccd  mov     r8, rsi; unsigned int
0x180026cd0  mov     edx, 27h ; '''; void *
0x180026cd5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026cda  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026cde  mov     rdx, rbx
0x180026ce1  lea     rcx, [rsp+1130h+var_10D0]
0x180026ce6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026ceb  lea     rdx, [rsp+1130h+var_10D0]
0x180026cf0  lea     rcx, [rsp+1130h+lpSubKey]
0x180026cf5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180026cfa  lea     rcx, [rsp+1130h+var_10D0]
0x180026cff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026d04  mov     rcx, [rbp+1038h]; this
0x180026d0b  cmp     [rsp+1130h+lpSubKey], 0
0x180026d11  jnz     short loc_180026D18
0x180026d13  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x180026d18  mov     [rsp+1130h+hKey], 0
0x180026d21  mov     r12, 0FFFFFFFF80000002h
0x180026d28  cmp     [rsp+1130h+lpSubKey], 0
0x180026d2e  jz      loc_180026F3E
0x180026d34  xor     edx, edx
0x180026d36  lea     rcx, [rsp+1130h+hKey]
0x180026d3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026d40  lea     rax, [rsp+1130h+hKey]
0x180026d45  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026d4a  mov     r9d, 20019h; samDesired
0x180026d50  xor     r8d, r8d; ulOptions
0x180026d53  mov     rdx, [rsp+1130h+lpSubKey]; lpSubKey
0x180026d58  mov     rcx, r12; hKey
0x180026d5b  call    cs:__imp_RegOpenKeyExW
0x180026d61  mov     rcx, [rbp+1038h]; this
0x180026d68  test    eax, eax
0x180026d6a  jz      short loc_180026D81
0x180026d6c  mov     r9d, eax; char *
0x180026d6f  mov     r8, rsi; unsigned int
0x180026d72  mov     edx, 2Fh ; '/'; void *
0x180026d77  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026d7c  jmp     loc_180026F3E
0x180026d81  mov     [rsp+1130h+hkey], 0
0x180026d8a  mov     [rsp+1130h+var_10E8], 0
0x180026d92  mov     [rsp+1130h+cbData], 4
0x180026d9a  mov     dword ptr [rsp+1130h+Data], 0
0x180026da2  xor     edx, edx
0x180026da4  lea     rcx, [rsp+1130h+hkey]
0x180026da9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026dae  lea     rax, [rsp+1130h+hkey]
0x180026db3  mov     [rsp+1130h+phkResult], rax; phkResult
0x180026db8  mov     r9d, 2001Fh; samDesired
0x180026dbe  xor     r8d, r8d; ulOptions
0x180026dc1  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x180026dc8  mov     rcx, [rsp+1130h+hKey]; hKey
0x180026dcd  call    cs:__imp_RegOpenKeyExW
0x180026dd3  test    eax, eax
0x180026dd5  jnz     short loc_180026E1D
0x180026dd7  lea     rax, [rsp+1130h+cbData]
0x180026ddc  mov     [rsp+1130h+pcbData], rax; pcbData
0x180026de1  lea     rax, [rsp+1130h+var_10E8]
0x180026de6  mov     [rsp+1130h+pvData], rax; pvData
0x180026deb  mov     [rsp+1130h+phkResult], 0; pdwType
0x180026df4  mov     r9d, 20000018h; dwFlags
0x180026dfa  lea     r8, aStart; "Start"
0x180026e01  xor     edx, edx; lpSubKey
0x180026e03  mov     rcx, [rsp+1130h+hkey]; hkey
0x180026e08  call    cs:__imp_RegGetValueW
0x180026e0e  test    eax, eax
0x180026e10  jnz     short loc_180026E1D
0x180026e12  cmp     [rsp+1130h+var_10E8], r14d
0x180026e17  jz      loc_180026EEC
0x180026e1d  mov     dword ptr [rsp+1130h+phkResult], r14d; bIgnoreCase
0x180026e22  or      r9d, 0FFFFFFFFh; cchCount2
0x180026e26  mov     r8, rbx; lpString2
0x180026e29  or      edx, r9d; cchCount1
0x180026e2c  mov     rcx, [rsp+1130h+lpSubKey]; lpString1
0x180026e31  call    cs:__imp_CompareStringOrdinal
0x180026e37  cmp     eax, 2
0x180026e3a  jz      loc_180026F34
0x180026e40  xor     bl, bl
0x180026e42  mov     [rsp+1130h+var_10D0], 0
0x180026e4b  xor     edx, edx
0x180026e4d  lea     rcx, [rsp+1130h+var_10D0]
0x180026e52  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026e57  lea     rax, [rsp+1130h+var_10D0]
0x180026e5c  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026e61  mov     r9d, 2001Fh; samDesired
0x180026e67  xor     r8d, r8d; ulOptions
0x180026e6a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180026e71  mov     rcx, r12; hKey
0x180026e74  call    cs:__imp_RegOpenKeyExW
0x180026e7a  mov     rcx, [rbp+1038h]; this
0x180026e81  test    eax, eax
0x180026e83  jz      short loc_180026E97
0x180026e85  mov     r9d, eax; char *
0x180026e88  mov     r8, rsi; unsigned int
0x180026e8b  mov     edx, 42h ; 'B'; void *
0x180026e90  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026e95  jmp     short loc_180026EDE
0x180026e97  lea     rax, [rsp+1130h+cbData]
0x180026e9c  mov     [rsp+1130h+pcbData], rax; pcbData
0x180026ea1  lea     rax, [rsp+1130h+var_10E8]
0x180026ea6  mov     [rsp+1130h+pvData], rax; pvData
0x180026eab  mov     [rsp+1130h+phkResult], 0; pdwType
0x180026eb4  mov     r9d, 20000018h; dwFlags
0x180026eba  lea     r8, aStart; "Start"
0x180026ec1  xor     edx, edx; lpSubKey
0x180026ec3  mov     rcx, [rsp+1130h+var_10D0]; hkey
0x180026ec8  call    cs:__imp_RegGetValueW
0x180026ece  test    eax, eax
0x180026ed0  jnz     short loc_180026EDE
0x180026ed2  movzx   ebx, bl
0x180026ed5  cmp     [rsp+1130h+var_10E8], r14d
0x180026eda  cmovz   ebx, r14d
0x180026ede  lea     rcx, [rsp+1130h+var_10D0]
0x180026ee3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026ee8  test    bl, bl
0x180026eea  jz      short loc_180026F34
0x180026eec  mov     eax, [rsp+1130h+cbData]
0x180026ef0  mov     dword ptr [rsp+1130h+pvData], eax; cbData
0x180026ef4  lea     rax, [rsp+1130h+Data]
0x180026ef9  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026efe  mov     r9d, 4; dwType
0x180026f04  xor     r8d, r8d; Reserved
0x180026f07  lea     rdx, aStart; "Start"
0x180026f0e  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026f13  call    cs:__imp_RegSetValueExW
0x180026f19  mov     rcx, [rbp+1038h]; this
0x180026f20  test    eax, eax
0x180026f22  jz      short loc_180026F34
0x180026f24  mov     r9d, eax; char *
0x180026f27  mov     r8, rsi; unsigned int
0x180026f2a  mov     edx, 4Dh ; 'M'; void *
0x180026f2f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026f34  lea     rcx, [rsp+1130h+hkey]
0x180026f39  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026f3e  mov     dl, r14b
0x180026f41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer> `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl(void)'::`2'::impl
0x180026f48  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026f4d  mov     [rsp+1130h+hkey], 0
0x180026f56  xor     edx, edx
0x180026f58  lea     rcx, [rsp+1130h+hkey]
0x180026f5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026f62  lea     rax, [rsp+1130h+hkey]
0x180026f67  mov     [rsp+1130h+phkResult], rax; int
0x180026f6c  mov     r9d, 2001Bh; samDesired
0x180026f72  xor     r8d, r8d; ulOptions
0x180026f75  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026f7c  mov     rcx, r12; hKey
0x180026f7f  call    cs:__imp_RegOpenKeyExW
0x180026f85  mov     rcx, [rbp+1038h]
0x180026f8c  test    eax, eax
0x180026f8e  jz      short loc_180026F97
0x180026f90  mov     edx, 54h ; 'T'
0x180026f95  jmp     short loc_180026FE6
0x180026f97  lea     rdx, aRestorestatus; "RestoreStatus"
0x180026f9e  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026fa3  call    cs:__imp_RegDeleteValueW
0x180026fa9  mov     rcx, [rbp+1038h]; this
0x180026fb0  test    eax, eax
0x180026fb2  jz      short loc_180026FC4
0x180026fb4  mov     r9d, eax; char *
0x180026fb7  mov     r8, rsi; unsigned int
0x180026fba  mov     edx, 56h ; 'V'; void *
0x180026fbf  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026fc4  lea     rdx, aRestoredwallpa; "RestoredWallPaperFullPath"
0x180026fcb  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026fd0  call    cs:__imp_RegDeleteValueW
0x180026fd6  mov     rcx, [rbp+1038h]; this
0x180026fdd  test    eax, eax
0x180026fdf  jz      short loc_180026FF1
0x180026fe1  mov     edx, 57h ; 'W'; void *
0x180026fe6  mov     r9d, eax; char *
0x180026fe9  mov     r8, rsi; unsigned int
0x180026fec  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026ff1  lea     rcx, [rsp+1130h+hkey]
0x180026ff6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026ffb  call    ??$HandleEvent@$0BK@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>(bool)
0x180027000  call    OOBE__CompleteTime__SetAsCurrentTime
0x180027005  mov     rcx, [rbp+1038h]; this
0x18002700c  test    eax, eax
0x18002700e  jns     short loc_180027021
0x180027010  mov     r9d, eax; char *
0x180027013  mov     r8, rsi; unsigned int
0x180027016  mov     edx, 61h ; 'a'; void *
0x18002701b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027020  nop
0x180027021  lea     rcx, [rsp+1130h+hKey]
0x180027026  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002702b  nop
0x18002702c  lea     rcx, [rsp+1130h+lpSubKey]
0x180027031  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027036  mov     rcx, [rbp+1030h+var_30]
0x18002703d  xor     rcx, rsp; StackCookie
0x180027040  call    __security_check_cookie
0x180027045  add     rsp, 1110h
0x18002704c  pop     r14
0x18002704e  pop     r12
0x180027050  pop     rsi
0x180027051  pop     rbx
0x180027052  pop     rbp
0x180027053  retn
```
