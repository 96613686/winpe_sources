# DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(void)

- ea: `0x180054bd8`
- end: `0x180054dbb`
- name: `?EnableDeploymentTask@DeviceCredentialMgr@DcaMgr@@AEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialMgr *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800547f0`
- `0x180099258`

## callees

- `0x18000782c`
- `0x180048434`
- `0x180054bd8`
- `0x180054dc4`
- `0x180054df0`
- `0x1800596ec`
- `0x18005cee0`
- `0x180097a9c`
- `0x180099a90`
- `0x1800a0de4`
- `0x1800a5e58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054ca7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054ca7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180054cef`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180054d62`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180054cef`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180054d62`

## string_xrefs

- `0x180054c47`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054d03`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054d29`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054d76`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180054c8f`: `DeploymentTaskCreated`
- `0x180054d51`: `DeploymentTaskCreated`
- `0x180054c38`: `CreateLocalAccount`
- `0x180054bfe`: `EnableDeploymentTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DcaMgr::DeviceCredentialMgr::EnableDeploymentTask(DcaMgr::DeviceCredentialMgr *this)
{
  int LocalAccount; // ebx
  const unsigned __int16 *v2; // rdx
  unsigned int v3; // eax
  unsigned int v4; // eax
  int DeploymentTask; // eax
  unsigned int v6; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  const char *pvData; // [rsp+28h] [rbp-D8h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  int Data; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v14[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "EnableDeploymentTask");
  v14[0] = &DevCredSvcTraceLoggingProvider::EnableDeploymentTask::`vftable';
  DevCredSvcTraceLoggingProvider::EnableDeploymentTask::StartActivity((DevCredSvcTraceLoggingProvider::EnableDeploymentTask *)v14);
  LocalAccount = CreateLocalAccount();
  if ( LocalAccount >= 0 )
  {
    v11 = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
           L"DeploymentTaskCreated",
           0x10u,
           0,
           &v11,
           &pcbData) )
    {
      v3 = 0;
      v11 = 0;
    }
    else
    {
      v3 = v11;
    }
    if ( v3 != 4 )
    {
      Data = 0;
      v4 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\SpecialAccounts\\UserList",
             L"CDFAccount",
             4u,
             &Data,
             4u);
      if ( v4 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x651,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)v4,
          pdwType);
      DeploymentTask = PackageUtil::CreateDeploymentTask();
      LocalAccount = DeploymentTask;
      if ( DeploymentTask < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x653,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)(unsigned int)DeploymentTask,
          pdwType);
        goto LABEL_14;
      }
      v11 = 4;
      v6 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
             L"DeploymentTaskCreated",
             4u,
             &v11,
             4u);
      if ( v6 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)v6,
          pdwTypea);
    }
    DevCredSvcTraceLoggingProvider::EnableDeploymentTask::Stop(
      (DevCredSvcTraceLoggingProvider::EnableDeploymentTask *)v14,
      v2);
    LocalAccount = 0;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x631,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)(unsigned int)LocalAccount,
    (int)"CreateLocalAccount",
    pvData);
LABEL_14:
  DevCredSvcTraceLoggingProvider::EnableDeploymentTask::~EnableDeploymentTask((DevCredSvcTraceLoggingProvider::EnableDeploymentTask *)v14);
  return (unsigned int)LocalAccount;
}

```

## disassembly

```asm
0x180054bd8  push    rbp
0x180054bda  push    rbx
0x180054bdb  push    rsi
0x180054bdc  push    r14
0x180054bde  lea     rbp, [rsp-0B8h]
0x180054be6  sub     rsp, 1B8h
0x180054bed  mov     rax, cs:__security_cookie
0x180054bf4  xor     rax, rsp
0x180054bf7  mov     [rbp+0D0h+var_30], rax
0x180054bfe  lea     rdx, aEnabledeployme; "EnableDeploymentTask"
0x180054c05  lea     rcx, [rsp+1D0h+var_180]
0x180054c0a  call    ??0?$ActivityBase@VDevCredSvcTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180054c0f  lea     rax, ??_7EnableDeploymentTask@DevCredSvcTraceLoggingProvider@@6B@; const DevCredSvcTraceLoggingProvider::EnableDeploymentTask::`vftable'
0x180054c16  mov     [rsp+1D0h+var_180], rax
0x180054c1b  lea     rcx, [rsp+1D0h+var_180]; this
0x180054c20  call    ?StartActivity@EnableDeploymentTask@DevCredSvcTraceLoggingProvider@@QEAAXXZ; DevCredSvcTraceLoggingProvider::EnableDeploymentTask::StartActivity(void)
0x180054c25  nop
0x180054c26  call    CreateLocalAccount
0x180054c2b  mov     ebx, eax
0x180054c2d  test    eax, eax
0x180054c2f  jns     short loc_180054C5D
0x180054c31  mov     rcx, [rbp+0D8h]; this
0x180054c38  lea     rax, aCreatelocalacc; "CreateLocalAccount"
0x180054c3f  mov     [rsp+1D0h+pdwType], rax; int
0x180054c44  mov     r9d, ebx; char *
0x180054c47  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054c4e  mov     edx, 631h; void *
0x180054c53  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054c58  jmp     loc_180054D93
0x180054c5d  mov     [rsp+1D0h+var_190], 0
0x180054c65  mov     esi, 4
0x180054c6a  mov     [rsp+1D0h+var_18C], esi
0x180054c6e  lea     rax, [rsp+1D0h+var_18C]
0x180054c73  mov     [rsp+1D0h+pcbData], rax; pcbData
0x180054c78  lea     rax, [rsp+1D0h+var_190]
0x180054c7d  mov     [rsp+1D0h+pvData], rax; pvData
0x180054c82  mov     [rsp+1D0h+pdwType], 0; pdwType
0x180054c8b  lea     r9d, [rsi+0Ch]; dwFlags
0x180054c8f  lea     r8, aDeploymenttask; "DeploymentTaskCreated"
0x180054c96  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180054c9d  mov     r14, 0FFFFFFFF80000002h
0x180054ca4  mov     rcx, r14; hkey
0x180054ca7  call    cs:__imp_RegGetValueW
0x180054cad  test    eax, eax
0x180054caf  jz      short loc_180054CB9
0x180054cb1  xor     eax, eax
0x180054cb3  mov     [rsp+1D0h+var_190], eax
0x180054cb7  jmp     short loc_180054CBD
0x180054cb9  mov     eax, [rsp+1D0h+var_190]
0x180054cbd  cmp     eax, esi
0x180054cbf  jz      loc_180054D87
0x180054cc5  mov     [rsp+1D0h+Data], 0
0x180054ccd  mov     dword ptr [rsp+1D0h+pvData], esi; cbData
0x180054cd1  lea     rax, [rsp+1D0h+Data]
0x180054cd6  mov     [rsp+1D0h+pdwType], rax; int
0x180054cdb  mov     r9d, esi; dwType
0x180054cde  lea     r8, AccountName; "CDFAccount"
0x180054ce5  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180054cec  mov     rcx, r14; hKey
0x180054cef  call    cs:__imp_RegSetKeyValueW
0x180054cf5  mov     rcx, [rbp+0D8h]; this
0x180054cfc  test    eax, eax
0x180054cfe  jz      short loc_180054D14
0x180054d00  mov     r9d, eax; char *
0x180054d03  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054d0a  mov     edx, 651h; void *
0x180054d0f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180054d14  call    ?CreateDeploymentTask@PackageUtil@@SAJXZ; PackageUtil::CreateDeploymentTask(void)
0x180054d19  mov     ebx, eax
0x180054d1b  test    eax, eax
0x180054d1d  jns     short loc_180054D3C
0x180054d1f  mov     rcx, [rbp+0D8h]; this
0x180054d26  mov     r9d, eax; char *
0x180054d29  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054d30  mov     edx, 653h; void *
0x180054d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054d3a  jmp     short loc_180054D93
0x180054d3c  mov     [rsp+1D0h+var_190], esi
0x180054d40  mov     dword ptr [rsp+1D0h+pvData], esi; cbData
0x180054d44  lea     rax, [rsp+1D0h+var_190]
0x180054d49  mov     [rsp+1D0h+pdwType], rax; unsigned int
0x180054d4e  mov     r9d, esi; dwType
0x180054d51  lea     r8, aDeploymenttask; "DeploymentTaskCreated"
0x180054d58  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180054d5f  mov     rcx, r14; hKey
0x180054d62  call    cs:__imp_RegSetKeyValueW
0x180054d68  mov     rcx, [rbp+0D8h]; this
0x180054d6f  test    eax, eax
0x180054d71  jz      short loc_180054D87
0x180054d73  mov     r9d, eax; char *
0x180054d76  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180054d7d  mov     edx, 65Ch; void *
0x180054d82  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180054d87  lea     rcx, [rsp+1D0h+var_180]; this
0x180054d8c  call    ?Stop@EnableDeploymentTask@DevCredSvcTraceLoggingProvider@@QEAAXPEBG@Z; DevCredSvcTraceLoggingProvider::EnableDeploymentTask::Stop(ushort const *)
0x180054d91  xor     ebx, ebx
0x180054d93  lea     rcx, [rsp+1D0h+var_180]; this
0x180054d98  call    ??1EnableDeploymentTask@DevCredSvcTraceLoggingProvider@@QEAA@XZ; DevCredSvcTraceLoggingProvider::EnableDeploymentTask::~EnableDeploymentTask(void)
0x180054d9d  mov     eax, ebx
0x180054d9f  mov     rcx, [rbp+0D0h+var_30]
0x180054da6  xor     rcx, rsp; StackCookie
0x180054da9  call    __security_check_cookie
0x180054dae  add     rsp, 1B8h
0x180054db5  pop     r14
0x180054db7  pop     rsi
0x180054db8  pop     rbx
0x180054db9  pop     rbp
0x180054dba  retn
```
