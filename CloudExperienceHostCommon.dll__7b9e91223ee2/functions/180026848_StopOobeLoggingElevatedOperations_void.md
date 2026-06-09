# StopOobeLoggingElevatedOperations(void)

- ea: `0x180026848`
- end: `0x180026c74`
- name: `?StopOobeLoggingElevatedOperations@@YAXXZ`
- size: `1068`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026830`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x18001a540`
- `0x18001b004`
- `0x1800227ac`
- `0x180022c50`
- `0x18002327c`
- `0x180023634`
- `0x180024d70`
- `0x180025ff0`
- `0x18002649c`
- `0x180026848`
- `0x180027aac`
- `0x180027aec`
- `0x1800d8c00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026a69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026a69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026b3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002699f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026a05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026aa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002699f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026a05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026aa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026a40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026af4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026a40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026af4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026bc3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026bf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026bc3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180026bf0`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800268b0`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800268b0`

## string_xrefs

- `0x180026be4`: `RestoredWallPaperFullPath`
- `0x1800268fb`: `ETWAutoLoggerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void StopOobeLoggingElevatedOperations(void)
{
  ULONG v0; // eax
  int RedirectionKeyPath; // eax
  const char *v2; // r9
  unsigned int v3; // r8d
  const char *v4; // r9
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  bool v7; // bl
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v24; // [rsp+60h] [rbp-A0h] BYREF
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
      &v24,
      (char *)L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger",
      0xFFFFFFFFFFFFFFFFuLL,
      v2);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpSubKey,
      &v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    v5 = lpSubKey;
    if ( lpSubKey )
      goto LABEL_7;
    wil::details::in1diag3::_Log_NullAlloc(retaddr, 0, v3, v4);
  }
  v5 = lpSubKey;
LABEL_7:
  hKey = 0;
  if ( v5 )
  {
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
    if ( v6 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
        (const char *)v6,
        phkResulta);
    }
    else
    {
      pvData = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      hkey = 0;
      if ( !RegOpenKeyExW(hKey, L"CloudExperienceHostOobe", 0, 0x2001Fu, &hkey)
        && !RegGetValueW(hkey, 0, L"Start", 0x20000018u, 0, &pvData, &cbData)
        && pvData == 1 )
      {
        goto LABEL_19;
      }
      if ( CompareStringOrdinal(lpSubKey, -1, L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger", -1, 1) != 2 )
      {
        v7 = 0;
        v24 = 0;
        v8 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\CloudExperienceHostOobe",
               0,
               0x2001Fu,
               &v24);
        if ( v8 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x42,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
            (const char *)v8,
            phkResultb);
        }
        else if ( !RegGetValueW(v24, 0, L"Start", 0x20000018u, 0, &pvData, &cbData) )
        {
          v7 = pvData == 1;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
        if ( v7 )
        {
LABEL_19:
          v9 = RegSetValueExW(hkey, L"Start", 0, 4u, Data, cbData);
          if ( v9 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
              (const char *)v9,
              phkResultc);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl'::`2'::impl,
    v5);
  hkey = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", 0, 0x2001Bu, &hkey);
  v11 = retaddr;
  if ( v10 )
  {
    v12 = 84;
LABEL_28:
    wil::details::in1diag3::_Log_Win32(
      v11,
      (void *)v12,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v10,
      phkResultd);
    goto LABEL_29;
  }
  v13 = RegDeleteValueW(hkey, L"RestoreStatus");
  if ( v13 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v13,
      phkResultd);
  v10 = RegDeleteValueW(hkey, L"RestoredWallPaperFullPath");
  v11 = retaddr;
  if ( v10 )
  {
    v12 = 87;
    goto LABEL_28;
  }
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>();
  v14 = OOBE::CompleteTime::SetAsCurrentTime();
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)(unsigned int)v14,
      phkResultd);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180026848  push    rbp
0x18002684a  push    rbx
0x18002684b  push    rsi
0x18002684c  push    r14
0x18002684e  push    r15
0x180026850  lea     rbp, [rsp-1010h]
0x180026858  mov     eax, 1110h
0x18002685d  call    _alloca_probe
0x180026862  sub     rsp, rax
0x180026865  mov     rax, cs:__security_cookie
0x18002686c  xor     rax, rsp
0x18002686f  mov     [rbp+1030h+var_30], rax
0x180026876  mov     ebx, 107Ch
0x18002687b  mov     r8d, ebx; Size
0x18002687e  xor     edx, edx; Val
0x180026880  lea     rcx, [rbp+1030h+Properties]; void *
0x180026884  call    memset_0
0x180026889  mov     [rbp+1030h+Properties.Wnode.BufferSize], ebx
0x18002688c  mov     [rbp+1030h+Properties.LoggerNameOffset], 78h ; 'x'
0x180026893  mov     [rbp+1030h+Properties.LogFileNameOffset], 87Ah
0x18002689a  mov     r14d, 1
0x1800268a0  mov     r9d, r14d; ControlCode
0x1800268a3  lea     r8, [rbp+1030h+Properties]; Properties
0x1800268a7  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x1800268ae  xor     ecx, ecx; TraceHandle
0x1800268b0  call    cs:__imp_ControlTraceW
0x1800268b6  mov     rcx, [rbp+1038h]; this
0x1800268bd  lea     rsi, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\StopO"...
0x1800268c4  test    eax, eax
0x1800268c6  jz      short loc_1800268D7
0x1800268c8  mov     r9d, eax; char *
0x1800268cb  mov     r8, rsi; unsigned int
0x1800268ce  lea     edx, [r14+1Eh]; void *
0x1800268d2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800268d7  mov     [rsp+1130h+lpSubKey], 0
0x1800268e0  xor     edx, edx
0x1800268e2  lea     rcx, [rsp+1130h+lpSubKey]
0x1800268e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800268ec  lea     r8, [rsp+1130h+lpSubKey]; unsigned __int16 **
0x1800268f1  lea     rbx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x1800268f8  mov     rdx, rbx; unsigned __int16 *
0x1800268fb  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x180026902  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180026907  mov     rcx, [rbp+1038h]; this
0x18002690e  test    eax, eax
0x180026910  jns     short loc_180026962
0x180026912  mov     r9d, eax; char *
0x180026915  mov     r8, rsi; unsigned int
0x180026918  mov     edx, 27h ; '''; void *
0x18002691d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026922  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026926  mov     rdx, rbx
0x180026929  lea     rcx, [rsp+1130h+var_10D0]
0x18002692e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026933  lea     rdx, [rsp+1130h+var_10D0]
0x180026938  lea     rcx, [rsp+1130h+lpSubKey]
0x18002693d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180026942  lea     rcx, [rsp+1130h+var_10D0]
0x180026947  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002694c  mov     rcx, [rbp+1038h]; this
0x180026953  mov     rdx, [rsp+1130h+lpSubKey]; void *
0x180026958  test    rdx, rdx
0x18002695b  jnz     short loc_180026967
0x18002695d  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x180026962  mov     rdx, [rsp+1130h+lpSubKey]; lpSubKey
0x180026967  mov     [rsp+1130h+hKey], 0
0x180026970  mov     r15, 0FFFFFFFF80000002h
0x180026977  test    rdx, rdx
0x18002697a  jz      loc_180026B6A
0x180026980  mov     [rsp+1130h+hKey], 0
0x180026989  lea     rax, [rsp+1130h+hKey]
0x18002698e  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026993  mov     r9d, 20019h; samDesired
0x180026999  xor     r8d, r8d; ulOptions
0x18002699c  mov     rcx, r15; hKey
0x18002699f  call    cs:__imp_RegOpenKeyExW
0x1800269a5  mov     rcx, [rbp+1038h]; this
0x1800269ac  test    eax, eax
0x1800269ae  jz      short loc_1800269C5
0x1800269b0  mov     r9d, eax; char *
0x1800269b3  mov     r8, rsi; unsigned int
0x1800269b6  mov     edx, 2Fh ; '/'; void *
0x1800269bb  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800269c0  jmp     loc_180026B6A
0x1800269c5  mov     [rsp+1130h+var_10F0], 0
0x1800269cd  mov     [rsp+1130h+cbData], 4
0x1800269d5  mov     dword ptr [rsp+1130h+Data], 0
0x1800269dd  mov     [rsp+1130h+hkey], 0
0x1800269e6  lea     rax, [rsp+1130h+hkey]
0x1800269eb  mov     [rsp+1130h+phkResult], rax; phkResult
0x1800269f0  mov     r9d, 2001Fh; samDesired
0x1800269f6  xor     r8d, r8d; ulOptions
0x1800269f9  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x180026a00  mov     rcx, [rsp+1130h+hKey]; hKey
0x180026a05  call    cs:__imp_RegOpenKeyExW
0x180026a0b  test    eax, eax
0x180026a0d  jnz     short loc_180026A55
0x180026a0f  lea     rax, [rsp+1130h+cbData]
0x180026a14  mov     [rsp+1130h+pcbData], rax; pcbData
0x180026a19  lea     rax, [rsp+1130h+var_10F0]
0x180026a1e  mov     [rsp+1130h+pvData], rax; pvData
0x180026a23  mov     [rsp+1130h+phkResult], 0; pdwType
0x180026a2c  mov     r9d, 20000018h; dwFlags
0x180026a32  lea     r8, aStart; "Start"
0x180026a39  xor     edx, edx; lpSubKey
0x180026a3b  mov     rcx, [rsp+1130h+hkey]; hkey
0x180026a40  call    cs:__imp_RegGetValueW
0x180026a46  test    eax, eax
0x180026a48  jnz     short loc_180026A55
0x180026a4a  cmp     [rsp+1130h+var_10F0], r14d
0x180026a4f  jz      loc_180026B18
0x180026a55  mov     dword ptr [rsp+1130h+phkResult], r14d; bIgnoreCase
0x180026a5a  or      r9d, 0FFFFFFFFh; cchCount2
0x180026a5e  mov     r8, rbx; lpString2
0x180026a61  or      edx, r9d; cchCount1
0x180026a64  mov     rcx, [rsp+1130h+lpSubKey]; lpString1
0x180026a69  call    cs:__imp_CompareStringOrdinal
0x180026a6f  cmp     eax, 2
0x180026a72  jz      loc_180026B60
0x180026a78  xor     bl, bl
0x180026a7a  mov     [rsp+1130h+var_10D0], 0
0x180026a83  lea     rax, [rsp+1130h+var_10D0]
0x180026a88  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026a8d  mov     r9d, 2001Fh; samDesired
0x180026a93  xor     r8d, r8d; ulOptions
0x180026a96  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x180026a9d  mov     rcx, r15; hKey
0x180026aa0  call    cs:__imp_RegOpenKeyExW
0x180026aa6  mov     rcx, [rbp+1038h]; this
0x180026aad  test    eax, eax
0x180026aaf  jz      short loc_180026AC3
0x180026ab1  mov     r9d, eax; char *
0x180026ab4  mov     r8, rsi; unsigned int
0x180026ab7  mov     edx, 42h ; 'B'; void *
0x180026abc  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026ac1  jmp     short loc_180026B0A
0x180026ac3  lea     rax, [rsp+1130h+cbData]
0x180026ac8  mov     [rsp+1130h+pcbData], rax; pcbData
0x180026acd  lea     rax, [rsp+1130h+var_10F0]
0x180026ad2  mov     [rsp+1130h+pvData], rax; pvData
0x180026ad7  mov     [rsp+1130h+phkResult], 0; pdwType
0x180026ae0  mov     r9d, 20000018h; dwFlags
0x180026ae6  lea     r8, aStart; "Start"
0x180026aed  xor     edx, edx; lpSubKey
0x180026aef  mov     rcx, [rsp+1130h+var_10D0]; hkey
0x180026af4  call    cs:__imp_RegGetValueW
0x180026afa  test    eax, eax
0x180026afc  jnz     short loc_180026B0A
0x180026afe  movzx   ebx, bl
0x180026b01  cmp     [rsp+1130h+var_10F0], r14d
0x180026b06  cmovz   ebx, r14d
0x180026b0a  lea     rcx, [rsp+1130h+var_10D0]
0x180026b0f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026b14  test    bl, bl
0x180026b16  jz      short loc_180026B60
0x180026b18  mov     eax, [rsp+1130h+cbData]
0x180026b1c  mov     dword ptr [rsp+1130h+pvData], eax; cbData
0x180026b20  lea     rax, [rsp+1130h+Data]
0x180026b25  mov     [rsp+1130h+phkResult], rax; unsigned int
0x180026b2a  mov     r9d, 4; dwType
0x180026b30  xor     r8d, r8d; Reserved
0x180026b33  lea     rdx, aStart; "Start"
0x180026b3a  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026b3f  call    cs:__imp_RegSetValueExW
0x180026b45  mov     rcx, [rbp+1038h]; this
0x180026b4c  test    eax, eax
0x180026b4e  jz      short loc_180026B60
0x180026b50  mov     r9d, eax; char *
0x180026b53  mov     r8, rsi; unsigned int
0x180026b56  mov     edx, 4Dh ; 'M'; void *
0x180026b5b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026b60  lea     rcx, [rsp+1130h+hkey]
0x180026b65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026b6a  mov     dl, r14b
0x180026b6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer> `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl(void)'::`2'::impl
0x180026b74  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026b79  mov     [rsp+1130h+hkey], 0
0x180026b82  lea     rax, [rsp+1130h+hkey]
0x180026b87  mov     [rsp+1130h+phkResult], rax; int
0x180026b8c  mov     r9d, 2001Bh; samDesired
0x180026b92  xor     r8d, r8d; ulOptions
0x180026b95  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026b9c  mov     rcx, r15; hKey
0x180026b9f  call    cs:__imp_RegOpenKeyExW
0x180026ba5  mov     rcx, [rbp+1038h]
0x180026bac  test    eax, eax
0x180026bae  jz      short loc_180026BB7
0x180026bb0  mov     edx, 54h ; 'T'
0x180026bb5  jmp     short loc_180026C06
0x180026bb7  lea     rdx, aRestorestatus; "RestoreStatus"
0x180026bbe  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026bc3  call    cs:__imp_RegDeleteValueW
0x180026bc9  mov     rcx, [rbp+1038h]; this
0x180026bd0  test    eax, eax
0x180026bd2  jz      short loc_180026BE4
0x180026bd4  mov     r9d, eax; char *
0x180026bd7  mov     r8, rsi; unsigned int
0x180026bda  mov     edx, 56h ; 'V'; void *
0x180026bdf  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026be4  lea     rdx, aRestoredwallpa; "RestoredWallPaperFullPath"
0x180026beb  mov     rcx, [rsp+1130h+hkey]; hKey
0x180026bf0  call    cs:__imp_RegDeleteValueW
0x180026bf6  mov     rcx, [rbp+1038h]; this
0x180026bfd  test    eax, eax
0x180026bff  jz      short loc_180026C11
0x180026c01  mov     edx, 57h ; 'W'; void *
0x180026c06  mov     r9d, eax; char *
0x180026c09  mov     r8, rsi; unsigned int
0x180026c0c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026c11  lea     rcx, [rsp+1130h+hkey]
0x180026c16  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026c1b  call    ??$HandleEvent@$0BK@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>(bool)
0x180026c20  call    OOBE__CompleteTime__SetAsCurrentTime
0x180026c25  mov     rcx, [rbp+1038h]; this
0x180026c2c  test    eax, eax
0x180026c2e  jns     short loc_180026C41
0x180026c30  mov     r9d, eax; char *
0x180026c33  mov     r8, rsi; unsigned int
0x180026c36  mov     edx, 61h ; 'a'; void *
0x180026c3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026c40  nop
0x180026c41  lea     rcx, [rsp+1130h+hKey]
0x180026c46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026c4b  nop
0x180026c4c  lea     rcx, [rsp+1130h+lpSubKey]
0x180026c51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026c56  mov     rcx, [rbp+1030h+var_30]
0x180026c5d  xor     rcx, rsp; StackCookie
0x180026c60  call    __security_check_cookie
0x180026c65  add     rsp, 1110h
0x180026c6c  pop     r15
0x180026c6e  pop     r14
0x180026c70  pop     rsi
0x180026c71  pop     rbx
0x180026c72  pop     rbp
0x180026c73  retn
```
