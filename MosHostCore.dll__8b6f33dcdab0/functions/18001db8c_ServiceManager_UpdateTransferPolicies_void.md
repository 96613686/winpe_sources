# ServiceManager::UpdateTransferPolicies(void)

- ea: `0x18001db8c`
- end: `0x18001dedf`
- name: `?UpdateTransferPolicies@ServiceManager@@AEAAJXZ`
- size: `851`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001405c`
- `0x1800142c4`
- `0x180014c00`
- `0x180015898`
- `0x1800166a8`
- `0x180016a54`
- `0x18001bbd0`
- `0x18001d224`

## callees

- `0x1800121d0`
- `0x1800121f0`
- `0x180013240`
- `0x1800163e0`
- `0x18001db8c`
- `0x18001ea30`
- `0x18001ea84`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `UMPDC!Pdcv2ActivationClientRegister` at `0x18001dc92`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18001dc92`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x18001dd5f`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x18001dd5f`
- `mapsbtsvc!MapsBackgroundTransferService_SetPowerPolicy` at `0x18001de57`
- `mapsbtsvc!MapsBackgroundTransferService_SetPowerPolicy` at `0x18001de57`
- `mapsbtsvc!MapsBackgroundTransferService_SetNetworkCostPolicy` at `0x18001dea0`
- `mapsbtsvc!MapsBackgroundTransferService_SetNetworkCostPolicy` at `0x18001dea0`
- `mapsbtsvc!MapsBackgroundTransferService_SetPriority` at `0x18001de7c`
- `mapsbtsvc!MapsBackgroundTransferService_SetPriority` at `0x18001de7c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001de73`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001de98`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001debc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001de73`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001de98`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001debc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001dbe5`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001dbe5`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001dcb2`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001dd7f`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001dcb2`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001dd7f`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001ddd3`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001ddd3`

## string_xrefs

- `0x18001dbdc`: `ServiceManager::UpdateTransferPolicies`
- `0x18001dca9`: `ServiceManager::UpdateTransferPolicies`
- `0x18001dd76`: `ServiceManager::UpdateTransferPolicies`
- `0x18001de6a`: `ServiceManager::UpdateTransferPolicies`
- `0x18001de8f`: `ServiceManager::UpdateTransferPolicies`
- `0x18001deb3`: `ServiceManager::UpdateTransferPolicies`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceManager::UpdateTransferPolicies(struct _RTL_CRITICAL_SECTION *this)
{
  int PolicyInt; // eax
  int v3; // r8d
  unsigned int v4; // esi
  unsigned int v5; // r15d
  unsigned int v6; // r12d
  BOOL v7; // edi
  HANDLE *p_OwningThread; // rsi
  int v9; // eax
  int v10; // eax
  LONG LockCount; // esi
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v22[3]; // [rsp+60h] [rbp-29h] BYREF
  _DWORD v23[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v24; // [rsp+80h] [rbp-9h]
  __int128 v25; // [rsp+88h] [rbp-1h]
  __int128 v26; // [rsp+98h] [rbp+Fh]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]
  int v28; // [rsp+F0h] [rbp+67h] BYREF
  int v29; // [rsp+F8h] [rbp+6Fh] BYREF

  CriticalSectionWithConditionVariable::Lock(this + 85, (__int64)v21);
  v29 = 0;
  PolicyInt = ServiceManager::CalculateTransferPolicy(
                (ServiceManager *)this,
                (enum ServiceManager::TransferPolicy *)&v29);
  if ( PolicyInt < 0 )
  {
    v3 = 3219;
LABEL_3:
    v4 = ZTraceReportPropagation(PolicyInt, "ServiceManager::UpdateTransferPolicies", v3, this);
LABEL_4:
    RelockableGate::~RelockableGate((RelockableGate *)v21);
    return v4;
  }
  v5 = 0;
  if ( ((v29 - 1) & 0xFFFFFFFD) != 0 )
  {
    v6 = 2;
    if ( BYTE2(this[107].SpinCount) )
      v5 = 2;
  }
  else
  {
    v6 = 0;
  }
  v7 = 1;
  if ( (unsigned int)(v29 - 2) <= 1 )
  {
    p_OwningThread = &this[86].OwningThread;
    if ( !this[86].OwningThread )
    {
      v19 = 0;
      v22[0] = 1;
      v22[1] = &ServiceManager::PdcActivatorCallback;
      v22[2] = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      v9 = Pdcv2ActivationClientRegister(46, v22, &v19);
      if ( v9 < 0 )
      {
        v4 = ZTraceReportOrigination(v9 | 0x10000000, "ServiceManager::UpdateTransferPolicies", 3255, this);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
        goto LABEL_4;
      }
      if ( p_OwningThread != (HANDLE *)&v19 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &this[86].OwningThread,
          v19);
        v19 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    }
    v5 |= 1u;
    if ( !this[86].LockSemaphore )
    {
      v20 = 0;
      v26 = 0;
      v27 = 0;
      v29 = 0;
      v23[0] = 1;
      v23[1] = 300;
      v24 = 0;
      v25 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v20,
        0);
      v10 = Pdcv2ActivationClientActivate(*p_OwningThread, v23, 0, 0, L"OfflineMapsDownload", 0, &v20, &v29);
      if ( v10 < 0 )
      {
        v4 = ZTraceReportOrigination(v10 | 0x10000000, "ServiceManager::UpdateTransferPolicies", 3282, this);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
        goto LABEL_4;
      }
      if ( &this[86].LockSemaphore != (HANDLE *)&v20 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &this[86].LockSemaphore,
          v20);
        v20 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &this[86].LockSemaphore,
      0);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &this[86].OwningThread,
      0);
  }
  LockCount = this[88].LockCount;
  v28 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Maps", L"AllowOfflineMapsDownloadOverMeteredConnection", &v28);
  if ( PolicyInt == -2147024769 )
  {
    v13 = 0xFFFF;
    v28 = 0xFFFF;
  }
  else
  {
    if ( PolicyInt < 0 )
    {
      v3 = 3304;
      goto LABEL_3;
    }
    v13 = v28;
  }
  if ( v13 != 1 )
  {
    if ( v13 )
    {
      v29 = 1;
      PolicyInt = ServiceManager::GetDownloadOnlyOnWifiSetting((ServiceManager *)this, &v29, v12);
      if ( PolicyInt < 0 )
      {
        v3 = 3321;
        goto LABEL_3;
      }
      if ( (v29 || BYTE2(this[107].SpinCount)) && LockCount != 3 )
        v7 = 0;
    }
    else
    {
      v7 = LockCount == 3;
    }
  }
  v4 = 0;
  v14 = 4 * v7;
  RelockableGate::~RelockableGate((RelockableGate *)v21);
  v15 = MapsBackgroundTransferService_SetPowerPolicy(v5);
  if ( v15 < 0 )
    ZTraceReportIgnore(v15, "ServiceManager::UpdateTransferPolicies", 3335, this);
  v16 = MapsBackgroundTransferService_SetPriority(v6);
  if ( v16 < 0 )
    ZTraceReportIgnore(v16, "ServiceManager::UpdateTransferPolicies", 3338, this);
  v17 = MapsBackgroundTransferService_SetNetworkCostPolicy(v14);
  if ( v17 < 0 )
    ZTraceReportIgnore(v17, "ServiceManager::UpdateTransferPolicies", 3341, this);
  return v4;
}

```

## disassembly

```asm
0x18001db8c  mov     [rsp-8+arg_10], rbx
0x18001db91  push    rbp
0x18001db92  push    rsi
0x18001db93  push    rdi
0x18001db94  push    r12
0x18001db96  push    r13
0x18001db98  push    r14
0x18001db9a  push    r15
0x18001db9c  lea     rbp, [rsp-27h]
0x18001dba1  sub     rsp, 0B0h
0x18001dba8  mov     rbx, rcx
0x18001dbab  add     rcx, 0D48h
0x18001dbb2  lea     rdx, [rbp+57h+var_90]
0x18001dbb6  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001dbbb  nop
0x18001dbbc  xor     r13d, r13d
0x18001dbbf  mov     [rbp+57h+arg_8], r13d
0x18001dbc3  lea     rdx, [rbp+57h+arg_8]; enum ServiceManager::TransferPolicy *
0x18001dbc7  mov     rcx, rbx; this
0x18001dbca  call    ?CalculateTransferPolicy@ServiceManager@@AEAAJPEAW4TransferPolicy@1@@Z; ServiceManager::CalculateTransferPolicy(ServiceManager::TransferPolicy *)
0x18001dbcf  test    eax, eax
0x18001dbd1  jns     short loc_18001DBFB
0x18001dbd3  mov     r8d, 0C93h
0x18001dbd9  mov     r9, rbx
0x18001dbdc  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001dbe3  mov     ecx, eax
0x18001dbe5  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001dbeb  mov     esi, eax
0x18001dbed  lea     rcx, [rbp+57h+var_90]; this
0x18001dbf1  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001dbf6  jmp     loc_18001DEC2
0x18001dbfb  mov     r15d, r13d
0x18001dbfe  mov     ecx, [rbp+57h+arg_8]
0x18001dc01  lea     eax, [rcx-1]
0x18001dc04  test    eax, 0FFFFFFFDh
0x18001dc09  jz      short loc_18001DC1F
0x18001dc0b  mov     r12d, 2
0x18001dc11  cmp     [rbx+10DAh], r13b
0x18001dc18  jz      short loc_18001DC22
0x18001dc1a  mov     r15d, r12d
0x18001dc1d  jmp     short loc_18001DC22
0x18001dc1f  mov     r12d, r13d
0x18001dc22  lea     eax, [rcx-2]
0x18001dc25  mov     edi, 1
0x18001dc2a  cmp     eax, edi
0x18001dc2c  jbe     short loc_18001DC4F
0x18001dc2e  lea     rcx, [rbx+0D88h]
0x18001dc35  xor     edx, edx
0x18001dc37  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001dc3c  lea     rcx, [rbx+0D80h]
0x18001dc43  xor     edx, edx
0x18001dc45  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001dc4a  jmp     loc_18001DDB7
0x18001dc4f  lea     rsi, [rbx+0D80h]
0x18001dc56  cmp     [rsi], r13
0x18001dc59  jnz     loc_18001DCEA
0x18001dc5f  mov     [rbp+57h+var_A0], r13
0x18001dc63  mov     [rbp+57h+var_80], 1
0x18001dc6b  lea     rax, ?PdcActivatorCallback@ServiceManager@@CAXPEAXW4_PDC_ACTIVATOR_ERROR_DETAIL@@00@Z; ServiceManager::PdcActivatorCallback(void *,_PDC_ACTIVATOR_ERROR_DETAIL,void *,void *)
0x18001dc72  mov     [rbp+57h+var_78], rax
0x18001dc76  mov     [rbp+57h+var_70], r13
0x18001dc7a  xor     edx, edx
0x18001dc7c  lea     rcx, [rbp+57h+var_A0]
0x18001dc80  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001dc85  lea     r8, [rbp+57h+var_A0]
0x18001dc89  lea     rdx, [rbp+57h+var_80]
0x18001dc8d  mov     ecx, 2Eh ; '.'
0x18001dc92  call    cs:__imp_Pdcv2ActivationClientRegister
0x18001dc98  test    eax, eax
0x18001dc9a  jns     short loc_18001DCC8
0x18001dc9c  bts     eax, 1Ch
0x18001dca0  mov     r9, rbx
0x18001dca3  mov     r8d, 0CB7h
0x18001dca9  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001dcb0  mov     ecx, eax
0x18001dcb2  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001dcb8  mov     esi, eax
0x18001dcba  lea     rcx, [rbp+57h+var_A0]
0x18001dcbe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001dcc3  jmp     loc_18001DBED
0x18001dcc8  lea     rax, [rbp+57h+var_A0]
0x18001dccc  cmp     rsi, rax
0x18001dccf  jz      short loc_18001DCE1
0x18001dcd1  mov     rdx, [rbp+57h+var_A0]
0x18001dcd5  mov     rcx, rsi
0x18001dcd8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001dcdd  mov     [rbp+57h+var_A0], r13
0x18001dce1  lea     rcx, [rbp+57h+var_A0]
0x18001dce5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001dcea  or      r15d, edi
0x18001dced  lea     r14, [rbx+0D88h]
0x18001dcf4  cmp     [r14], r13
0x18001dcf7  jnz     loc_18001DDB7
0x18001dcfd  mov     [rbp+57h+var_98], r13
0x18001dd01  xorps   xmm0, xmm0
0x18001dd04  movdqu  [rbp+57h+var_48], xmm0
0x18001dd09  mov     [rbp+57h+var_38], r13
0x18001dd0d  mov     [rbp+57h+arg_8], r13d
0x18001dd11  mov     [rbp+57h+var_68], edi
0x18001dd14  mov     [rbp+57h+var_64], 12Ch
0x18001dd1b  mov     [rbp+57h+var_60], r13
0x18001dd1f  movdqu  [rbp+57h+var_58], xmm0
0x18001dd24  xor     edx, edx
0x18001dd26  lea     rcx, [rbp+57h+var_98]
0x18001dd2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001dd2f  lea     rax, [rbp+57h+arg_8]
0x18001dd33  mov     [rsp+0E0h+var_A8], rax
0x18001dd38  lea     rax, [rbp+57h+var_98]
0x18001dd3c  mov     [rsp+0E0h+var_B0], rax
0x18001dd41  mov     [rsp+0E0h+var_B8], r13d
0x18001dd46  lea     rax, aOfflinemapsdow; "OfflineMapsDownload"
0x18001dd4d  mov     [rsp+0E0h+var_C0], rax
0x18001dd52  xor     r9d, r9d
0x18001dd55  xor     r8d, r8d
0x18001dd58  lea     rdx, [rbp+57h+var_68]
0x18001dd5c  mov     rcx, [rsi]
0x18001dd5f  call    cs:__imp_Pdcv2ActivationClientActivate
0x18001dd65  test    eax, eax
0x18001dd67  jns     short loc_18001DD95
0x18001dd69  bts     eax, 1Ch
0x18001dd6d  mov     r9, rbx
0x18001dd70  mov     r8d, 0CD2h
0x18001dd76  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001dd7d  mov     ecx, eax
0x18001dd7f  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001dd85  mov     esi, eax
0x18001dd87  lea     rcx, [rbp+57h+var_98]
0x18001dd8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001dd90  jmp     loc_18001DBED
0x18001dd95  lea     rax, [rbp+57h+var_98]
0x18001dd99  cmp     r14, rax
0x18001dd9c  jz      short loc_18001DDAE
0x18001dd9e  mov     rdx, [rbp+57h+var_98]
0x18001dda2  mov     rcx, r14
0x18001dda5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001ddaa  mov     [rbp+57h+var_98], r13
0x18001ddae  lea     rcx, [rbp+57h+var_98]
0x18001ddb2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ddb7  mov     esi, [rbx+0DC8h]
0x18001ddbd  mov     [rbp+57h+arg_0], r13d
0x18001ddc1  lea     r8, [rbp+57h+arg_0]
0x18001ddc5  lea     rdx, aAllowofflinema; "AllowOfflineMapsDownloadOverMeteredConn"...
0x18001ddcc  lea     rcx, aMaps; "Maps"
0x18001ddd3  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001ddd9  cmp     eax, 8007007Fh
0x18001ddde  jnz     short loc_18001DDEA
0x18001dde0  mov     eax, 0FFFFh
0x18001dde5  mov     [rbp+57h+arg_0], eax
0x18001dde8  jmp     short loc_18001DDFC
0x18001ddea  test    eax, eax
0x18001ddec  jns     short loc_18001DDF9
0x18001ddee  mov     r8d, 0CE8h
0x18001ddf4  jmp     loc_18001DBD9
0x18001ddf9  mov     eax, [rbp+57h+arg_0]
0x18001ddfc  cmp     eax, edi
0x18001ddfe  jz      short loc_18001DE45
0x18001de00  test    eax, eax
0x18001de02  jnz     short loc_18001DE10
0x18001de04  mov     edi, r13d
0x18001de07  cmp     esi, 3
0x18001de0a  setz    dil
0x18001de0e  jmp     short loc_18001DE45
0x18001de10  mov     [rbp+57h+arg_8], edi
0x18001de13  lea     rdx, [rbp+57h+arg_8]; int *
0x18001de17  mov     rcx, rbx; this
0x18001de1a  call    ?GetDownloadOnlyOnWifiSetting@ServiceManager@@UEAAJPEAH@Z; ServiceManager::GetDownloadOnlyOnWifiSetting(int *)
0x18001de1f  test    eax, eax
0x18001de21  jns     short loc_18001DE2E
0x18001de23  mov     r8d, 0CF9h
0x18001de29  jmp     loc_18001DBD9
0x18001de2e  cmp     [rbp+57h+arg_8], r13d
0x18001de32  jnz     short loc_18001DE3D
0x18001de34  cmp     [rbx+10DAh], r13b
0x18001de3b  jz      short loc_18001DE45
0x18001de3d  cmp     esi, 3
0x18001de40  jz      short loc_18001DE45
0x18001de42  mov     edi, r13d
0x18001de45  mov     esi, r13d
0x18001de48  shl     edi, 2
0x18001de4b  lea     rcx, [rbp+57h+var_90]; this
0x18001de4f  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001de54  mov     ecx, r15d
0x18001de57  call    cs:__imp_?MapsBackgroundTransferService_SetPowerPolicy@@YAJW4MAPSBTSVC_POWER_POLICY_FLAG@@@Z; MapsBackgroundTransferService_SetPowerPolicy(MAPSBTSVC_POWER_POLICY_FLAG)
0x18001de5d  test    eax, eax
0x18001de5f  jns     short loc_18001DE79
0x18001de61  mov     r9, rbx
0x18001de64  mov     r8d, 0D07h
0x18001de6a  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001de71  mov     ecx, eax
0x18001de73  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001de79  mov     ecx, r12d
0x18001de7c  call    cs:__imp_?MapsBackgroundTransferService_SetPriority@@YAJW4MAPSBTSVC_JOB_PRIORITY@@@Z; MapsBackgroundTransferService_SetPriority(MAPSBTSVC_JOB_PRIORITY)
0x18001de82  test    eax, eax
0x18001de84  jns     short loc_18001DE9E
0x18001de86  mov     r9, rbx
0x18001de89  mov     r8d, 0D0Ah
0x18001de8f  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001de96  mov     ecx, eax
0x18001de98  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001de9e  mov     ecx, edi
0x18001dea0  call    cs:__imp_?MapsBackgroundTransferService_SetNetworkCostPolicy@@YAJW4MAPSBTSVC_NETWORK_COST_POLICY@@@Z; MapsBackgroundTransferService_SetNetworkCostPolicy(MAPSBTSVC_NETWORK_COST_POLICY)
0x18001dea6  test    eax, eax
0x18001dea8  jns     short loc_18001DEC2
0x18001deaa  mov     r9, rbx
0x18001dead  mov     r8d, 0D0Dh
0x18001deb3  lea     rdx, aServicemanager_88; "ServiceManager::UpdateTransferPolicies"
0x18001deba  mov     ecx, eax
0x18001debc  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001dec2  mov     eax, esi
0x18001dec4  mov     rbx, [rsp+0E0h+arg_10]
0x18001decc  add     rsp, 0B0h
0x18001ded3  pop     r15
0x18001ded5  pop     r14
0x18001ded7  pop     r13
0x18001ded9  pop     r12
0x18001dedb  pop     rdi
0x18001dedc  pop     rsi
0x18001dedd  pop     rbp
0x18001dede  retn
```
