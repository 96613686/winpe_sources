# WpW32TimeStartService

- ea: `0x180010578`
- end: `0x1800107f8`
- name: `WpW32TimeStartService`
- size: `640`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000d330`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005820`
- `0x180009174`
- `0x180010044`
- `0x180010578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010627`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800106ef`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800106ef`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180010619`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180010619`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800105d8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800105d8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800105fb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800105fb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800106fc`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800106fc`

## string_xrefs

- `0x1800107a6`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x1800107c3`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 WpW32TimeStartService()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rbx
  DWORD v5; // eax
  unsigned int v6; // r8d
  unsigned int LastError; // ebx
  int v8; // eax
  int v9; // edi
  __int64 v10; // rdx
  unsigned int v12; // [rsp+20h] [rbp-50h]
  SC_HANDLE v13; // [rsp+38h] [rbp-38h] BYREF
  SC_HANDLE v14; // [rsp+40h] [rbp-30h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)byte_180017771,
      0,
      0);
  v0 = OpenSCManagerW(0, 0, 1u);
  v13 = v0;
  if ( !v0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x17A,
                  (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                  v1);
    goto LABEL_39;
  }
  v2 = OpenServiceW(v0, L"W32Time", 0x14u);
  v14 = v2;
  v4 = v2;
  if ( !v2 )
  {
    v10 = 382;
LABEL_35:
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v10,
           (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
           v3);
    goto LABEL_36;
  }
  if ( StartServiceW(v2, 0, 0) )
  {
    v9 = 0;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    while ( 1 )
    {
      if ( !QueryServiceStatus(v4, &ServiceStatus) )
      {
        v10 = 409;
        goto LABEL_35;
      }
      if ( ServiceStatus.dwCurrentState == 4 )
        goto LABEL_11;
      if ( ServiceStatus.dwCurrentState == 1 )
        break;
      if ( (unsigned int)++v9 > 5 )
      {
        if ( (unsigned int)dword_18001C010 > 2 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_18001C010,
            (__int64)&unk_180017790,
            0,
            0);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
        return 2147943860LL;
      }
      Sleep(0x1F4u);
    }
    if ( (unsigned int)dword_18001C010 > 3 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18001C010,
        (__int64)&word_18001772E,
        0,
        0);
    LastError = -2147023834;
    goto LABEL_37;
  }
  v5 = GetLastError();
  if ( v5 != 1056 )
  {
    if ( v5 == 1058 )
    {
      if ( (unsigned int)dword_18001C010 > 3 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_18001C010,
          (__int64)&unk_1800178F0,
          0,
          0);
      LastError = -2147023838;
      goto LABEL_37;
    }
    if ( !v5 )
      goto LABEL_11;
    v8 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x191, v6, (const char *)v5, v12);
LABEL_36:
    LastError = v8;
    goto LABEL_37;
  }
  if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&byte_180017937,
      0,
      0);
LABEL_11:
  LastError = 0;
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
LABEL_39:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  return LastError;
}

```

## disassembly

```asm
0x180010578  push    rbp
0x18001057a  push    rbx
0x18001057b  push    rsi
0x18001057c  push    rdi
0x18001057d  push    r14
0x18001057f  mov     rbp, rsp
0x180010582  sub     rsp, 70h
0x180010586  mov     rax, cs:__security_cookie
0x18001058d  xor     rax, rsp
0x180010590  mov     [rbp+var_8], rax
0x180010594  mov     eax, cs:dword_18001C010
0x18001059a  lea     rsi, dword_18001C010
0x1800105a1  mov     r14d, 200h
0x1800105a7  cmp     eax, 4
0x1800105aa  jbe     short loc_1800105D0
0x1800105ac  mov     edx, r14d
0x1800105af  mov     rcx, rsi
0x1800105b2  call    _tlgKeywordOn
0x1800105b7  test    al, al
0x1800105b9  jz      short loc_1800105D0
0x1800105bb  xor     r9d, r9d
0x1800105be  lea     rdx, byte_180017771
0x1800105c5  xor     r8d, r8d
0x1800105c8  mov     rcx, rsi
0x1800105cb  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800105d0  xor     edx, edx; lpDatabaseName
0x1800105d2  xor     ecx, ecx; lpMachineName
0x1800105d4  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800105d8  call    cs:__imp_OpenSCManagerW
0x1800105de  mov     [rbp+var_38], rax
0x1800105e2  test    rax, rax
0x1800105e5  jz      loc_1800107BF
0x1800105eb  mov     r8d, 14h; dwDesiredAccess
0x1800105f1  lea     rdx, aW32time; "W32Time"
0x1800105f8  mov     rcx, rax; hSCManager
0x1800105fb  call    cs:__imp_OpenServiceW
0x180010601  mov     [rbp+var_30], rax
0x180010605  mov     rbx, rax
0x180010608  test    rax, rax
0x18001060b  jz      loc_18001079D
0x180010611  xor     r8d, r8d; lpServiceArgVectors
0x180010614  xor     edx, edx; dwNumServiceArgs
0x180010616  mov     rcx, rax; hService
0x180010619  call    cs:__imp_StartServiceW
0x18001061f  test    eax, eax
0x180010621  jnz     loc_1800106C4
0x180010627  call    cs:__imp_GetLastError
0x18001062d  cmp     eax, 420h
0x180010632  jnz     short loc_18001066A
0x180010634  mov     eax, cs:dword_18001C010
0x18001063a  cmp     eax, 4
0x18001063d  jbe     short loc_180010663
0x18001063f  mov     rdx, r14
0x180010642  mov     rcx, rsi
0x180010645  call    _tlgKeywordOn
0x18001064a  test    al, al
0x18001064c  jz      short loc_180010663
0x18001064e  xor     r9d, r9d
0x180010651  lea     rdx, byte_180017937
0x180010658  xor     r8d, r8d
0x18001065b  mov     rcx, rsi
0x18001065e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180010663  xor     ebx, ebx
0x180010665  jmp     loc_1800107B4
0x18001066a  cmp     eax, 422h
0x18001066f  jnz     short loc_1800106AA
0x180010671  mov     eax, cs:dword_18001C010
0x180010677  cmp     eax, 3
0x18001067a  jbe     short loc_1800106A0
0x18001067c  mov     rdx, r14
0x18001067f  mov     rcx, rsi
0x180010682  call    _tlgKeywordOn
0x180010687  test    al, al
0x180010689  jz      short loc_1800106A0
0x18001068b  xor     r9d, r9d
0x18001068e  lea     rdx, unk_1800178F0
0x180010695  xor     r8d, r8d
0x180010698  mov     rcx, rsi
0x18001069b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800106a0  mov     ebx, 80070422h
0x1800106a5  jmp     loc_1800107B4
0x1800106aa  test    eax, eax
0x1800106ac  jz      short loc_180010663
0x1800106ae  mov     rcx, [rbp+28h]; this
0x1800106b2  mov     r9d, eax; char *
0x1800106b5  mov     edx, 191h; void *
0x1800106ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800106bf  jmp     loc_1800107B2
0x1800106c4  xorps   xmm0, xmm0
0x1800106c7  xor     edi, edi
0x1800106c9  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800106cd  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800106d1  jmp     short loc_1800106F5
0x1800106d3  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x1800106d7  jz      short loc_180010663
0x1800106d9  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x1800106dd  jz      loc_180010767
0x1800106e3  inc     edi
0x1800106e5  cmp     edi, 5
0x1800106e8  ja      short loc_180010710
0x1800106ea  mov     ecx, 1F4h; dwMilliseconds
0x1800106ef  call    cs:__imp_Sleep
0x1800106f5  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800106f9  mov     rcx, rbx; hService
0x1800106fc  call    cs:__imp_QueryServiceStatus
0x180010702  test    eax, eax
0x180010704  jnz     short loc_1800106D3
0x180010706  mov     edx, 199h
0x18001070b  jmp     loc_1800107A2
0x180010710  mov     eax, cs:dword_18001C010
0x180010716  cmp     eax, 2
0x180010719  jbe     short loc_18001074E
0x18001071b  mov     rdx, r14
0x18001071e  mov     rcx, rsi
0x180010721  call    _tlgKeywordOn
0x180010726  test    al, al
0x180010728  jz      short loc_18001074E
0x18001072a  mov     eax, [rbp+ServiceStatus.dwCurrentState]
0x18001072d  lea     rdx, unk_180017790
0x180010734  mov     [rbp+var_40], eax
0x180010737  xor     r9d, r9d
0x18001073a  lea     rax, [rbp+var_40]
0x18001073e  xor     r8d, r8d
0x180010741  mov     rcx, rsi
0x180010744  mov     qword ptr [rsp+70h+var_50], rax
0x180010749  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001074e  lea     rcx, [rbp+var_30]
0x180010752  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010757  lea     rcx, [rbp+var_38]
0x18001075b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180010760  mov     eax, 800705B4h
0x180010765  jmp     short loc_1800107E1
0x180010767  mov     eax, cs:dword_18001C010
0x18001076d  cmp     eax, 3
0x180010770  jbe     short loc_180010796
0x180010772  mov     rdx, r14
0x180010775  mov     rcx, rsi
0x180010778  call    _tlgKeywordOn
0x18001077d  test    al, al
0x18001077f  jz      short loc_180010796
0x180010781  xor     r9d, r9d
0x180010784  lea     rdx, word_18001772E
0x18001078b  xor     r8d, r8d
0x18001078e  mov     rcx, rsi
0x180010791  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180010796  mov     ebx, 80070426h
0x18001079b  jmp     short loc_1800107B4
0x18001079d  mov     edx, 17Eh; void *
0x1800107a2  mov     rcx, [rbp+28h]; this
0x1800107a6  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800107ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800107b2  mov     ebx, eax
0x1800107b4  lea     rcx, [rbp+var_30]
0x1800107b8  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800107bd  jmp     short loc_1800107D6
0x1800107bf  mov     rcx, [rbp+28h]; this
0x1800107c3  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800107ca  mov     edx, 17Ah; void *
0x1800107cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800107d4  mov     ebx, eax
0x1800107d6  lea     rcx, [rbp+var_38]
0x1800107da  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800107df  mov     eax, ebx
0x1800107e1  mov     rcx, [rbp+var_8]
0x1800107e5  xor     rcx, rsp; StackCookie
0x1800107e8  call    __security_check_cookie
0x1800107ed  add     rsp, 70h
0x1800107f1  pop     r14
0x1800107f3  pop     rdi
0x1800107f4  pop     rsi
0x1800107f5  pop     rbx
0x1800107f6  pop     rbp
0x1800107f7  retn
```
