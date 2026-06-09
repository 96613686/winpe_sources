# NgcSvc::NgcServiceReconfigureContainerService

- ea: `0x1800638f0`
- end: `0x180063b72`
- name: `NgcSvc::NgcServiceReconfigureContainerService`
- size: `642`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180063594`
- `0x180063b78`

## callees

- `0x180007964`
- `0x180028d18`
- `0x180034cf8`
- `0x180046d90`
- `0x18005cee0`
- `0x180063394`
- `0x1800638f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006395c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006395c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800639f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aea`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800639b2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800639b2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180063921`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180063921`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180063a7d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180063a7d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180063ae0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180063ae0`

## string_xrefs

- `0x180063918`: `ServicesActive`
- `0x180063944`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x1800639d7`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x180063b10`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcSvc::NgcServiceReconfigureContainerService(unsigned __int8 a1)
{
  int v1; // edi
  SC_HANDLE v2; // rax
  const char *v3; // r9
  DWORD LastError; // ebx
  DWORD v5; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  DWORD v10; // eax
  char *v11; // rdx
  unsigned int lpBinaryPathName; // [rsp+20h] [rbp-49h]
  DWORD v14; // [rsp+60h] [rbp-9h] BYREF
  SC_HANDLE v15; // [rsp+68h] [rbp-1h] BYREF
  SC_HANDLE v16; // [rsp+70h] [rbp+7h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v1 = a1;
  v2 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v16 = v2;
  if ( v2 )
  {
    v6 = OpenServiceW(v2, L"ngcctnrsvc", (32 * v1) | 2u);
    v7 = v6;
    v15 = v6;
    if ( v6 )
    {
      if ( ChangeServiceConfigW(v6, 0xFFFFFFFF, v1 + 3, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !(_BYTE)v1 || ControlService(v7, 1u, &ServiceStatus) || (LastError = GetLastError(), LastError == 1062) )
        {
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
          LastError = 0;
          goto LABEL_28;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
            (const char *)LastError,
            lpBinaryPathName);
          goto LABEL_10;
        }
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_10;
        v14 = LastError;
        v11 = byte_1800FD3ED;
        goto LABEL_14;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v9 = 87;
        goto LABEL_9;
      }
      v10 = GetLastError();
      LastError = v10;
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_10;
      v11 = byte_1800FD413;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v9 = 58;
LABEL_9:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v9,
                      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
                      v8);
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
        goto LABEL_28;
      }
      v10 = GetLastError();
      LastError = v10;
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_10;
      v11 = (char *)&word_1800FD43E;
    }
    v14 = v10;
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v11,
      0,
      0,
      (__int64)&v14);
    goto LABEL_10;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x24,
                  (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
                  v3);
  }
  else
  {
    v5 = GetLastError();
    LastError = v5;
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v14 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FD461,
        0,
        0,
        (__int64)&v14);
    }
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
  return LastError;
}

```

## disassembly

```asm
0x1800638f0  push    rbp
0x1800638f2  push    rbx
0x1800638f3  push    rsi
0x1800638f4  push    rdi
0x1800638f5  lea     rbp, [rsp-3Fh]
0x1800638fa  sub     rsp, 0A8h
0x180063901  mov     rax, cs:__security_cookie
0x180063908  xor     rax, rsp
0x18006390b  mov     [rbp+57h+var_28], rax
0x18006390f  movzx   edi, cl
0x180063912  mov     r8d, 80000000h; dwDesiredAccess
0x180063918  lea     rdx, DatabaseName; "ServicesActive"
0x18006391f  xor     ecx, ecx; lpMachineName
0x180063921  call    cs:__imp_OpenSCManagerW
0x180063927  mov     [rbp+57h+var_50], rax
0x18006392b  test    rax, rax
0x18006392e  jnz     short loc_18006399D
0x180063930  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063937  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006393c  test    al, al
0x18006393e  jz      short loc_18006395C
0x180063940  mov     rcx, [rbp+5Fh]; this
0x180063944  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006394b  mov     edx, 24h ; '$'; void *
0x180063950  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063955  mov     ebx, eax
0x180063957  jmp     loc_180063B4F
0x18006395c  call    cs:__imp_GetLastError
0x180063962  mov     ebx, eax
0x180063964  mov     ecx, cs:dword_180122070
0x18006396a  cmp     ecx, 2
0x18006396d  jbe     loc_180063B4F
0x180063973  mov     [rbp+57h+var_60], eax
0x180063976  lea     rax, [rbp+57h+var_60]
0x18006397a  mov     [rsp+0C0h+lpBinaryPathName], rax
0x18006397f  xor     r9d, r9d
0x180063982  xor     r8d, r8d
0x180063985  lea     rdx, byte_1800FD461
0x18006398c  lea     rcx, dword_180122070
0x180063993  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063998  jmp     loc_180063B4F
0x18006399d  mov     r8d, edi
0x1800639a0  shl     r8d, 5
0x1800639a4  or      r8d, 2; dwDesiredAccess
0x1800639a8  lea     rdx, ServiceName; "ngcctnrsvc"
0x1800639af  mov     rcx, rax; hSCManager
0x1800639b2  call    cs:__imp_OpenServiceW
0x1800639b8  mov     rbx, rax
0x1800639bb  mov     [rbp+57h+var_58], rax
0x1800639bf  test    rax, rax
0x1800639c2  jnz     short loc_180063A31
0x1800639c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800639cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800639d0  test    al, al
0x1800639d2  jz      short loc_1800639F7
0x1800639d4  lea     edx, [rbx+3Ah]; void *
0x1800639d7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800639de  mov     rcx, [rbp+5Fh]; this
0x1800639e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800639e7  mov     ebx, eax
0x1800639e9  lea     rcx, [rbp+57h+var_58]
0x1800639ed  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800639f2  jmp     loc_180063B4F
0x1800639f7  call    cs:__imp_GetLastError
0x1800639fd  mov     ebx, eax
0x1800639ff  mov     ecx, cs:dword_180122070
0x180063a05  cmp     ecx, 2
0x180063a08  jbe     short loc_1800639E9
0x180063a0a  lea     rdx, word_1800FD43E
0x180063a11  mov     [rbp+57h+var_60], eax
0x180063a14  lea     rax, [rbp+57h+var_60]
0x180063a18  xor     r9d, r9d
0x180063a1b  mov     [rsp+0C0h+lpBinaryPathName], rax
0x180063a20  xor     r8d, r8d
0x180063a23  lea     rcx, dword_180122070
0x180063a2a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063a2f  jmp     short loc_1800639E9
0x180063a31  lea     r8d, [rdi+3]; dwStartType
0x180063a35  mov     [rsp+0C0h+lpDisplayName], 0; lpDisplayName
0x180063a3e  mov     [rsp+0C0h+lpPassword], 0; lpPassword
0x180063a47  mov     [rsp+0C0h+lpServiceStartName], 0; lpServiceStartName
0x180063a50  mov     [rsp+0C0h+lpDependencies], 0; lpDependencies
0x180063a59  mov     [rsp+0C0h+lpdwTagId], 0; lpdwTagId
0x180063a62  mov     [rsp+0C0h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180063a6b  mov     [rsp+0C0h+lpBinaryPathName], 0; unsigned int
0x180063a74  or      edx, 0FFFFFFFFh; dwServiceType
0x180063a77  mov     r9d, edx; dwErrorControl
0x180063a7a  mov     rcx, rbx; hService
0x180063a7d  call    cs:__imp_ChangeServiceConfigW
0x180063a83  test    eax, eax
0x180063a85  jnz     short loc_180063AC4
0x180063a87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063a8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063a93  test    al, al
0x180063a95  jz      short loc_180063AA1
0x180063a97  mov     edx, 57h ; 'W'
0x180063a9c  jmp     loc_1800639D7
0x180063aa1  call    cs:__imp_GetLastError
0x180063aa7  mov     ebx, eax
0x180063aa9  mov     ecx, cs:dword_180122070
0x180063aaf  cmp     ecx, 2
0x180063ab2  jbe     loc_1800639E9
0x180063ab8  lea     rdx, byte_1800FD413
0x180063abf  jmp     loc_180063A11
0x180063ac4  xorps   xmm0, xmm0
0x180063ac7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180063acb  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180063acf  test    dil, dil
0x180063ad2  jz      short loc_180063B44
0x180063ad4  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180063ad8  mov     edx, 1; dwControl
0x180063add  mov     rcx, rbx; hService
0x180063ae0  call    cs:__imp_ControlService
0x180063ae6  test    eax, eax
0x180063ae8  jnz     short loc_180063B44
0x180063aea  call    cs:__imp_GetLastError
0x180063af0  mov     ebx, eax
0x180063af2  cmp     eax, 426h
0x180063af7  jz      short loc_180063B44
0x180063af9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063b00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063b05  test    al, al
0x180063b07  jz      short loc_180063B26
0x180063b09  mov     rcx, [rbp+5Fh]; this
0x180063b0d  mov     r9d, ebx; char *
0x180063b10  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180063b17  mov     edx, 72h ; 'r'; void *
0x180063b1c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180063b21  jmp     loc_1800639E9
0x180063b26  mov     eax, cs:dword_180122070
0x180063b2c  cmp     eax, 2
0x180063b2f  jbe     loc_1800639E9
0x180063b35  mov     [rbp+57h+var_60], ebx
0x180063b38  lea     rdx, byte_1800FD3ED
0x180063b3f  jmp     loc_180063A14
0x180063b44  lea     rcx, [rbp+57h+var_58]
0x180063b48  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180063b4d  xor     ebx, ebx
0x180063b4f  lea     rcx, [rbp+57h+var_50]
0x180063b53  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180063b58  mov     eax, ebx
0x180063b5a  mov     rcx, [rbp+57h+var_28]
0x180063b5e  xor     rcx, rsp; StackCookie
0x180063b61  call    __security_check_cookie
0x180063b66  add     rsp, 0A8h
0x180063b6d  pop     rdi
0x180063b6e  pop     rsi
0x180063b6f  pop     rbx
0x180063b70  pop     rbp
0x180063b71  retn
```
