# QueryWlidsvcProperties(ulong &,ulong &,bool &)

- ea: `0x18001ad0c`
- end: `0x18001af92`
- name: `?QueryWlidsvcProperties@@YAJAEAK0AEA_N@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001bb84`

## callees

- `0x180003160`
- `0x180004594`
- `0x180006e64`
- `0x180006e84`
- `0x180019a2c`
- `0x18001a68c`
- `0x18001a6ac`
- `0x18001a730`
- `0x18001ad0c`
- `0x18001b688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ae5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ae5f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ad65`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ad65`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ada2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ada2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001ae15`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001aeaf`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001ae15`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001aeaf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001adf1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001adf1`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001aef9`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001aef9`

## string_xrefs

- `0x18001ad5c`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall QueryWlidsvcProperties(unsigned int *a1, unsigned int *a2, bool *a3)
{
  SC_HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v9; // rax
  const char *v10; // r9
  SC_HANDLE v11; // rbx
  __int64 v12; // rdx
  struct _QUERY_SERVICE_CONFIGW *v13; // rax
  struct _QUERY_SERVICE_CONFIGW *v14; // rdi
  __int64 v15; // rdx
  const char *v16; // r9
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-E0h] BYREF
  SC_HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v21; // [rsp+38h] [rbp-C8h] BYREF
  SC_HANDLE v22; // [rsp+40h] [rbp-C0h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[336]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *a1 = -1;
  *a2 = -1;
  *a3 = 1;
  MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties((MSAClientTraceTelemetry::QueryWlidsvcProperties *)v24);
  v6 = OpenSCManagerW(0, L"ServicesActive", 4u);
  v22 = v6;
  if ( v6 )
  {
    v9 = OpenServiceW(v6, L"wlidsvc", 5u);
    v19 = v9;
    v11 = v9;
    if ( !v9 )
    {
      v12 = 107;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                    v10);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
      goto LABEL_24;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v9, &ServiceStatus) )
    {
      v12 = 112;
      goto LABEL_5;
    }
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(v11, 0, 0, &pcbBytesNeeded) )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        (const char *)0x8000FFFFLL,
        pcbBytesNeeded);
      goto LABEL_6;
    }
    if ( GetLastError() != 122 )
    {
      v12 = 123;
      goto LABEL_5;
    }
    v13 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
    v21 = v13;
    v14 = v13;
    if ( v13 )
    {
      if ( !QueryServiceConfigW(v11, v13, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x86,
                      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                      v16);
        goto LABEL_16;
      }
      v20 = -1;
      if ( !(unsigned __int8)IsPolicyManager_GetPolicyIntPresent()
        || (LastError = PolicyManager_GetPolicyInt(L"Accounts", L"AllowMicrosoftAccountSignInAssistant", &v20),
            (int)(LastError + 0x80000000) < 0)
        || LastError == -2147024769 )
      {
        *a3 = v20 != 0;
        *a2 = v14->dwStartType;
        *a1 = ServiceStatus.dwCurrentState;
        wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v24);
        wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        LastError = 0;
        goto LABEL_24;
      }
      v15 = 142;
    }
    else
    {
      LastError = -2147024882;
      v15 = 127;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      (const char *)LastError,
      pcbBytesNeeded);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(&v21);
    goto LABEL_6;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x64,
                (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                v7);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v22);
  MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties((MSAClientTraceTelemetry::QueryWlidsvcProperties *)v24);
  return LastError;
}

```

## disassembly

```asm
0x18001ad0c  mov     [rsp-8+arg_18], rbx
0x18001ad11  push    rbp
0x18001ad12  push    rsi
0x18001ad13  push    rdi
0x18001ad14  push    r14
0x18001ad16  push    r15
0x18001ad18  lea     rbp, [rsp-0D0h]
0x18001ad20  sub     rsp, 1D0h
0x18001ad27  mov     rax, cs:__security_cookie
0x18001ad2e  xor     rax, rsp
0x18001ad31  mov     [rbp+0F0h+var_30], rax
0x18001ad38  or      eax, 0FFFFFFFFh
0x18001ad3b  mov     rsi, rcx
0x18001ad3e  mov     [rcx], eax
0x18001ad40  mov     r15, r8
0x18001ad43  mov     [rdx], eax
0x18001ad45  lea     rcx, [rsp+1F0h+var_180]; this
0x18001ad4a  mov     byte ptr [r8], 1
0x18001ad4e  mov     r14, rdx
0x18001ad51  call    ??$?0$$V@QueryWlidsvcProperties@MSAClientTraceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(wistd::integral_constant<char,0>)
0x18001ad56  mov     r8d, 4; dwDesiredAccess
0x18001ad5c  lea     rdx, DatabaseName; "ServicesActive"
0x18001ad63  xor     ecx, ecx; lpMachineName
0x18001ad65  call    cs:__imp_OpenSCManagerW
0x18001ad6b  mov     [rsp+1F0h+var_1B0], rax
0x18001ad70  test    rax, rax
0x18001ad73  jnz     short loc_18001AD92
0x18001ad75  mov     rcx, [rbp+0F8h]; this
0x18001ad7c  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ad83  lea     edx, [rax+64h]; void *
0x18001ad86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ad8b  mov     ebx, eax
0x18001ad8d  jmp     loc_18001AF56
0x18001ad92  mov     r8d, 5; dwDesiredAccess
0x18001ad98  lea     rdx, ServiceName; "wlidsvc"
0x18001ad9f  mov     rcx, rax; hSCManager
0x18001ada2  call    cs:__imp_OpenServiceW
0x18001ada8  mov     [rsp+1F0h+var_1C8], rax
0x18001adad  mov     rbx, rax
0x18001adb0  test    rax, rax
0x18001adb3  jnz     short loc_18001ADDC
0x18001adb5  lea     edx, [rax+6Bh]; void *
0x18001adb8  mov     rcx, [rbp+0F8h]; this
0x18001adbf  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001adc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001adcb  mov     ebx, eax
0x18001adcd  lea     rcx, [rsp+1F0h+var_1C8]
0x18001add2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001add7  jmp     loc_18001AF56
0x18001addc  xorps   xmm0, xmm0
0x18001addf  lea     rdx, [rsp+1F0h+ServiceStatus]; lpServiceStatus
0x18001ade4  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwServiceType], xmm0
0x18001ade9  mov     rcx, rbx; hService
0x18001adec  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001adf1  call    cs:__imp_QueryServiceStatus
0x18001adf7  test    eax, eax
0x18001adf9  jnz     short loc_18001AE00
0x18001adfb  lea     edx, [rax+70h]
0x18001adfe  jmp     short loc_18001ADB8
0x18001ae00  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x18001ae05  mov     [rsp+1F0h+pcbBytesNeeded], 0; int
0x18001ae0d  xor     r8d, r8d; cbBufSize
0x18001ae10  xor     edx, edx; lpServiceConfig
0x18001ae12  mov     rcx, rbx; hService
0x18001ae15  call    cs:__imp_QueryServiceConfigW
0x18001ae1b  test    eax, eax
0x18001ae1d  jz      short loc_18001AE41
0x18001ae1f  mov     rcx, [rbp+0F8h]; this
0x18001ae26  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ae2d  mov     ebx, 8000FFFFh
0x18001ae32  mov     edx, 7Ah ; 'z'; void *
0x18001ae37  mov     r9d, ebx; char *
0x18001ae3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae3f  jmp     short loc_18001ADCD
0x18001ae41  call    cs:__imp_GetLastError
0x18001ae47  cmp     eax, 7Ah ; 'z'
0x18001ae4a  jz      short loc_18001AE56
0x18001ae4c  mov     edx, 7Bh ; '{'
0x18001ae51  jmp     loc_18001ADB8
0x18001ae56  mov     edx, [rsp+1F0h+pcbBytesNeeded]; uBytes
0x18001ae5a  mov     ecx, 40h ; '@'; uFlags
0x18001ae5f  call    cs:__imp_LocalAlloc
0x18001ae65  mov     [rsp+1F0h+var_1B8], rax
0x18001ae6a  mov     rdi, rax
0x18001ae6d  test    rax, rax
0x18001ae70  jnz     short loc_18001AE9F
0x18001ae72  mov     ebx, 8007000Eh
0x18001ae77  lea     edx, [rax+7Fh]; void *
0x18001ae7a  mov     rcx, [rbp+0F8h]; this
0x18001ae81  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ae88  mov     r9d, ebx; char *
0x18001ae8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae90  lea     rcx, [rsp+1F0h+var_1B8]
0x18001ae95  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x18001ae9a  jmp     loc_18001ADCD
0x18001ae9f  mov     r8d, [rsp+1F0h+pcbBytesNeeded]; cbBufSize
0x18001aea4  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x18001aea9  mov     rdx, rdi; lpServiceConfig
0x18001aeac  mov     rcx, rbx; hService
0x18001aeaf  call    cs:__imp_QueryServiceConfigW
0x18001aeb5  test    eax, eax
0x18001aeb7  jnz     short loc_18001AED5
0x18001aeb9  mov     rcx, [rbp+0F8h]; this
0x18001aec0  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001aec7  mov     edx, 86h; void *
0x18001aecc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001aed1  mov     ebx, eax
0x18001aed3  jmp     short loc_18001AE90
0x18001aed5  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFh
0x18001aedd  call    IsPolicyManager_GetPolicyIntPresent
0x18001aee2  test    al, al
0x18001aee4  jz      short loc_18001AF1F
0x18001aee6  lea     r8, [rsp+1F0h+var_1C0]
0x18001aeeb  lea     rdx, aAllowmicrosoft; "AllowMicrosoftAccountSignInAssistant"
0x18001aef2  lea     rcx, aAccounts; "Accounts"
0x18001aef9  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001aeff  mov     ebx, eax
0x18001af01  mov     eax, 80000000h
0x18001af06  lea     ecx, [rbx+rax]
0x18001af09  test    eax, ecx
0x18001af0b  jnz     short loc_18001AF1F
0x18001af0d  cmp     ebx, 8007007Fh
0x18001af13  jz      short loc_18001AF1F
0x18001af15  mov     edx, 8Eh
0x18001af1a  jmp     loc_18001AE7A
0x18001af1f  cmp     [rsp+1F0h+var_1C0], 0
0x18001af24  lea     rcx, [rsp+1F0h+var_180]
0x18001af29  setnz   al
0x18001af2c  mov     [r15], al
0x18001af2f  mov     eax, [rdi+4]
0x18001af32  mov     [r14], eax
0x18001af35  mov     eax, [rsp+1F0h+ServiceStatus.dwCurrentState]
0x18001af39  mov     [rsi], eax
0x18001af3b  call    ?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001af40  lea     rcx, [rsp+1F0h+var_1B8]
0x18001af45  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x18001af4a  lea     rcx, [rsp+1F0h+var_1C8]
0x18001af4f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001af54  xor     ebx, ebx
0x18001af56  lea     rcx, [rsp+1F0h+var_1B0]
0x18001af5b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18001af60  lea     rcx, [rsp+1F0h+var_180]; this
0x18001af65  call    ??1QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAA@XZ; MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(void)
0x18001af6a  mov     eax, ebx
0x18001af6c  mov     rcx, [rbp+0F0h+var_30]
0x18001af73  xor     rcx, rsp; StackCookie
0x18001af76  call    __security_check_cookie
0x18001af7b  mov     rbx, [rsp+1F0h+arg_18]
0x18001af83  add     rsp, 1D0h
0x18001af8a  pop     r15
0x18001af8c  pop     r14
0x18001af8e  pop     rdi
0x18001af8f  pop     rsi
0x18001af90  pop     rbp
0x18001af91  retn
```
