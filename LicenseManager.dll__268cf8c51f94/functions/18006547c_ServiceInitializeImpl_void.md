# ServiceInitializeImpl(void)

- ea: `0x18006547c`
- end: `0x1800656a1`
- name: `?ServiceInitializeImpl@@YAJXZ`
- size: `549`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180084330`

## callees

- `0x180004644`
- `0x180004738`
- `0x180013b50`
- `0x180056ca8`
- `0x1800593bc`
- `0x180061e24`
- `0x18006547c`
- `0x18006573c`
- `0x18006578c`
- `0x1800657f8`
- `0x18006bcf0`
- `0x18006e344`
- `0x180076e64`
- `0x18008e3a8`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006550e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006550e`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x1800655ac`
- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x1800655ac`

## string_xrefs

- `0x1800654a3`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800655e9`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180065681`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180065496`: `ServiceInitializeImpl`
- `0x180065674`: `ServiceInitializeImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 ServiceInitializeImpl(void)
{
  ApplicationLicenseManagerShared *v0; // rcx
  const char *v1; // r9
  __int64 result; // rax
  unsigned int v3; // ebx
  __int64 *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  ApplicationLicenseManagerShared *v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  UserSigninChangeWatcher **v10; // rax
  UserSigninChangeWatcher *v11; // rcx
  int lpData; // [rsp+20h] [rbp-28h]
  __int64 v13; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  int v18; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v18 = 0;
  try
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x841u,
      "ServiceInitializeImpl",
      (wchar_t *)L"License Manager starting...");
    if ( (unsigned __int8)IsXboxLicensingUndocked() )
    {
      ApplicationLicenseManagerShared::Initialize(v0);
      result = 0;
    }
    else
    {
      GetServiceMutableStateKey(&hKey, 0x20019u);
      LODWORD(Data) = 0;
      cbData = 4;
      RegQueryValueExW(hKey, L"LastSequenceId", 0, 0, (LPBYTE)&Data, &cbData);
      v3 = Data;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      AuditLogSequenceId = v3;
      v4 = (__int64 *)MakeCom<WnsListener,>(&Data);
      v5 = *v4;
      v13 = *v4;
      *v4 = 0;
      v18 = 1;
      v6 = Data;
      if ( Data )
      {
        Data = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      v13 = 0;
      Data = PushNotificationListener;
      PushNotificationListener = v5;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&Data);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v13);
      ApplicationLicenseManagerShared::Initialize(v7);
      if ( (unsigned __int8)IsCompareContentIdPresent(v8) && !(unsigned int)ShouldLicenseManagerServiceAutoStop() )
      {
        CreateApplicationLicenseManager(&cbData);
        Data = 0;
        v9 = Microsoft::WRL::ComPtr<ILicenseManager>::As<IUserSigninStateChange>(&cbData, &Data);
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x857,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v9,
            lpData);
        v10 = (UserSigninChangeWatcher **)MakeCom<UserSigninChangeWatcher,>(&v18);
        v11 = 0;
        if ( v14 != v10 )
        {
          v11 = *v10;
          *v10 = 0;
        }
        v14[0] = UserSigninWatcher;
        UserSigninWatcher = v11;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v14);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
        UserSigninChangeWatcher::Start(UserSigninWatcher, &Data);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&Data);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&cbData);
      }
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x85Du,
        "ServiceInitializeImpl",
        (wchar_t *)L"License Manager started");
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x860,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                           v1);
  }
  return result;
}

```

## disassembly

```asm
0x18006547c  push    rbx
0x18006547e  sub     rsp, 40h
0x180065482  mov     [rsp+48h+arg_10], 0
0x18006548a  lea     rax, aLicenseManager_0; "License Manager starting..."
0x180065491  mov     [rsp+48h+lpData], rax; Format
0x180065496  lea     r9, aServiceinitial_0; "ServiceInitializeImpl"
0x18006549d  mov     r8d, 841h; unsigned int
0x1800654a3  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800654aa  mov     ecx, 3; unsigned int
0x1800654af  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800654b4  call    IsXboxLicensingUndocked
0x1800654b9  test    al, al
0x1800654bb  jz      short loc_1800654C9
0x1800654bd  call    ?Initialize@ApplicationLicenseManagerShared@@QEAAXXZ; ApplicationLicenseManagerShared::Initialize(void)
0x1800654c2  xor     eax, eax
0x1800654c4  jmp     loc_18006569A
0x1800654c9  mov     edx, 20019h; samDesired
0x1800654ce  lea     rcx, [rsp+48h+hKey]; phkResult
0x1800654d3  call    ?GetServiceMutableStateKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; GetServiceMutableStateKey(ulong)
0x1800654d8  mov     dword ptr [rsp+48h+Data], 0
0x1800654e0  mov     [rsp+48h+cbData], 4
0x1800654e8  lea     rax, [rsp+48h+cbData]
0x1800654ed  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800654f2  lea     rax, [rsp+48h+Data]
0x1800654f7  mov     [rsp+48h+lpData], rax; int
0x1800654fc  xor     r9d, r9d; lpType
0x1800654ff  xor     r8d, r8d; lpReserved
0x180065502  lea     rdx, aLastsequenceid; "LastSequenceId"
0x180065509  mov     rcx, [rsp+48h+hKey]; hKey
0x18006550e  call    cs:__imp_RegQueryValueExW
0x180065514  mov     ebx, dword ptr [rsp+48h+Data]
0x180065518  lea     rcx, [rsp+48h+hKey]
0x18006551d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180065522  mov     cs:?AuditLogSequenceId@@3KA, ebx; ulong AuditLogSequenceId
0x180065528  lea     rcx, [rsp+48h+Data]
0x18006552d  call    ??$MakeCom@VWnsListener@@$$V@@YA?AV?$ComPtr@VWnsListener@@@WRL@Microsoft@@XZ; MakeCom<WnsListener,>(void)
0x180065532  mov     rbx, [rax]
0x180065535  mov     [rsp+48h+var_18], rbx
0x18006553a  mov     qword ptr [rax], 0
0x180065541  mov     [rsp+48h+arg_10], 1
0x180065549  mov     rcx, [rsp+48h+Data]
0x18006554e  test    rcx, rcx
0x180065551  jz      short loc_180065569
0x180065553  mov     [rsp+48h+Data], 0
0x18006555c  mov     rax, [rcx]
0x18006555f  mov     rax, [rax+10h]
0x180065563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065568  nop
0x180065569  mov     [rsp+48h+var_18], 0
0x180065572  mov     rax, cs:?PushNotificationListener@@3V?$ComPtr@UIWnsListener@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IWnsListener> PushNotificationListener
0x180065579  mov     [rsp+48h+Data], rax
0x18006557e  mov     cs:?PushNotificationListener@@3V?$ComPtr@UIWnsListener@@@WRL@Microsoft@@A, rbx; Microsoft::WRL::ComPtr<IWnsListener> PushNotificationListener
0x180065585  lea     rcx, [rsp+48h+Data]
0x18006558a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006558f  nop
0x180065590  lea     rcx, [rsp+48h+var_18]
0x180065595  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006559a  call    ?Initialize@ApplicationLicenseManagerShared@@QEAAXXZ; ApplicationLicenseManagerShared::Initialize(void)
0x18006559f  call    IsCompareContentIdPresent
0x1800655a4  test    al, al
0x1800655a6  jz      loc_180065668
0x1800655ac  call    cs:__imp_ShouldLicenseManagerServiceAutoStop
0x1800655b2  test    eax, eax
0x1800655b4  jnz     loc_180065668
0x1800655ba  lea     rcx, [rsp+48h+cbData]
0x1800655bf  call    ?CreateApplicationLicenseManager@@YA?AV?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@XZ; CreateApplicationLicenseManager(void)
0x1800655c4  nop
0x1800655c5  mov     [rsp+48h+Data], 0
0x1800655ce  lea     rdx, [rsp+48h+Data]
0x1800655d3  lea     rcx, [rsp+48h+cbData]
0x1800655d8  call    ??$As@UIUserSigninStateChange@@@?$ComPtr@UILicenseManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserSigninStateChange@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseManager>::As<IUserSigninStateChange>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUserSigninStateChange>>)
0x1800655dd  mov     rcx, [rsp+48h]; this
0x1800655e2  test    eax, eax
0x1800655e4  jns     short loc_1800655FA
0x1800655e6  mov     r9d, eax; char *
0x1800655e9  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800655f0  mov     edx, 857h; void *
0x1800655f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800655fa  lea     rcx, [rsp+48h+arg_10]
0x1800655ff  call    ??$MakeCom@VUserSigninChangeWatcher@@$$V@@YA?AV?$ComPtr@VUserSigninChangeWatcher@@@WRL@Microsoft@@XZ; MakeCom<UserSigninChangeWatcher,>(void)
0x180065604  xor     ecx, ecx
0x180065606  lea     rdx, [rsp+48h+var_10]
0x18006560b  cmp     rdx, rax
0x18006560e  jz      short loc_18006561A
0x180065610  mov     rcx, [rax]
0x180065613  mov     qword ptr [rax], 0
0x18006561a  mov     rax, cs:?UserSigninWatcher@@3V?$ComPtr@VUserSigninChangeWatcher@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<UserSigninChangeWatcher> UserSigninWatcher
0x180065621  mov     [rsp+48h+var_10], rax
0x180065626  mov     cs:?UserSigninWatcher@@3V?$ComPtr@VUserSigninChangeWatcher@@@WRL@Microsoft@@A, rcx; Microsoft::WRL::ComPtr<UserSigninChangeWatcher> UserSigninWatcher
0x18006562d  lea     rcx, [rsp+48h+var_10]
0x180065632  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180065637  lea     rcx, [rsp+48h+arg_10]
0x18006563c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180065641  lea     rdx, [rsp+48h+Data]
0x180065646  mov     rcx, cs:?UserSigninWatcher@@3V?$ComPtr@VUserSigninChangeWatcher@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<UserSigninChangeWatcher> UserSigninWatcher
0x18006564d  call    ?Start@UserSigninChangeWatcher@@QEAAXAEAV?$ComPtr@UIUserSigninStateChange@@@WRL@Microsoft@@@Z; UserSigninChangeWatcher::Start(Microsoft::WRL::ComPtr<IUserSigninStateChange> &)
0x180065652  nop
0x180065653  lea     rcx, [rsp+48h+Data]
0x180065658  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006565d  nop
0x18006565e  lea     rcx, [rsp+48h+cbData]
0x180065663  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180065668  lea     rax, aLicenseManager_2; "License Manager started"
0x18006566f  mov     [rsp+48h+lpData], rax; Format
0x180065674  lea     r9, aServiceinitial_0; "ServiceInitializeImpl"
0x18006567b  mov     r8d, 85Dh; unsigned int
0x180065681  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180065688  mov     ecx, 3; unsigned int
0x18006568d  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180065692  xor     eax, eax
0x180065694  jmp     short loc_18006569A
0x180065696  mov     eax, dword ptr [rsp+48h+Data]
0x18006569a  add     rsp, 40h
0x18006569e  pop     rbx
0x18006569f  retn
```
