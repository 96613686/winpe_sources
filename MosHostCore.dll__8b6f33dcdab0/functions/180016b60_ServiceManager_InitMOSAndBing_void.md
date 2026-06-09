# ServiceManager::InitMOSAndBing(void)

- ea: `0x180016b60`
- end: `0x180016d35`
- name: `?InitMOSAndBing@ServiceManager@@AEAAJXZ`
- size: `469`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180013174`
- `0x180015ed0`
- `0x180016b60`
- `0x180016f20`
- `0x180016fdc`
- `0x18001b978`
- `0x18001d7c4`
- `0x18001d9a0`
- `0x18001e664`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180016cff`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180016cff`
- `BingOnlineServices!?SetRunningInService@ServiceRequestHelper@BingOnlineServices@@SAXXZ` at `0x180016c16`
- `BingOnlineServices!?SetRunningInService@ServiceRequestHelper@BingOnlineServices@@SAXXZ` at `0x180016c16`
- `MosStorage!MosStorageEnsureIsAppContainerCompliant` at `0x180016bc0`
- `MosStorage!MosStorageEnsureIsAppContainerCompliant` at `0x180016bc0`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016c10`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016cc1`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016d23`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016c10`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016cc1`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016d23`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016bd8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016bd8`
- `ZTrace_Maps!ZTraceHelper` at `0x180016b91`
- `ZTrace_Maps!ZTraceHelper` at `0x180016c4d`
- `ZTrace_Maps!ZTraceHelper` at `0x180016b91`
- `ZTrace_Maps!ZTraceHelper` at `0x180016c4d`

## string_xrefs

- `0x180016b6d`: `[MosHost] Service - Startup - initializing MOS and MapsStore ...`
- `0x180016b82`: `ServiceManager::InitMOSAndBing`
- `0x180016c38`: `[MosHost] Service - Startup - initializing MOS and MapsStore complete`

## pseudocode

```c
__int64 __fastcall ServiceManager::InitMOSAndBing(ServiceManager *this)
{
  int IsAppContainerCompliant; // eax
  int v3; // r8d
  ServiceManager *v4; // r9
  int v5; // edi
  int v6; // eax
  int v7; // eax
  int updated; // eax
  _BYTE v10[56]; // [rsp+30h] [rbp-38h] BYREF
  bool v11; // [rsp+70h] [rbp+8h] BYREF

  ZTraceHelper(
    5,
    "ServiceManager::InitMOSAndBing",
    1678,
    this,
    "[MosHost] Service - Startup - initializing MOS and MapsStore ...");
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v10);
  if ( *((_DWORD *)this + 882) != 1 )
    __int2c();
  RelockableGate::~RelockableGate((RelockableGate *)v10);
  IsAppContainerCompliant = MosStorageEnsureIsAppContainerCompliant();
  if ( IsAppContainerCompliant < 0 )
  {
    v3 = 1689;
LABEL_5:
    v4 = this;
LABEL_6:
    v5 = ZTraceReportPropagation(IsAppContainerCompliant, "ServiceManager::InitMOSAndBing", v3, v4);
    goto LABEL_14;
  }
  IsAppContainerCompliant = ServiceManager::InitializeConfigurationManager(this);
  if ( IsAppContainerCompliant < 0 )
  {
    v3 = 1691;
    goto LABEL_5;
  }
  v6 = ServiceManager::WriteApprovedPFNList(this);
  if ( v6 < 0 )
    ZTraceReportIgnore(v6, "ServiceManager::InitMOSAndBing", 1692, this);
  BingOnlineServices::ServiceRequestHelper::SetRunningInService();
  IsAppContainerCompliant = ServiceManager::InitializeMapsStore(this);
  v4 = this;
  if ( IsAppContainerCompliant < 0 )
  {
    v3 = 1696;
    goto LABEL_6;
  }
  v5 = 0;
  ZTraceHelper(
    5,
    "ServiceManager::InitMOSAndBing",
    1698,
    this,
    "[MosHost] Service - Startup - initializing MOS and MapsStore complete");
LABEL_14:
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v10);
  *((_DWORD *)this + 882) = ((v5 >> 31) & 0xFFFFFFFE) + 2;
  *((_DWORD *)this + 862) = v5;
  if ( v5 < 0 )
  {
    ServiceManager::UninitializeMOSAndBing(this);
    if ( *((_BYTE *)this + 4312) )
      goto LABEL_22;
    if ( v5 == -2147023504 || v5 == -2080309235 )
      goto LABEL_21;
    v11 = 0;
    v7 = ServiceManager::ScanMapDataForCorruption(this, &v11);
    if ( v7 < 0 )
      ZTraceReportIgnore(v7, "ServiceManager::InitMOSAndBing", 1722, this);
    if ( v11 )
    {
LABEL_21:
      ServiceManager::AttemptRepairMapDataAsync(this);
    }
    else
    {
LABEL_22:
      *((_DWORD *)this + 884) = 0;
      *((_DWORD *)this + 885) = v5;
      ServiceManager::FireOdmlStateChange(this);
    }
  }
  RelockableGate::~RelockableGate((RelockableGate *)v10);
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 430);
  if ( v5 >= 0 )
  {
    updated = ServiceManager::UpdateCachedCopyright(this);
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::InitMOSAndBing", 1747, this);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016b60  push    rbx
0x180016b62  push    rsi
0x180016b63  push    rdi
0x180016b64  push    r14
0x180016b66  sub     rsp, 48h
0x180016b6a  mov     rbx, rcx
0x180016b6d  lea     rax, aMoshostService_7; "[MosHost] Service - Startup - initializ"...
0x180016b74  mov     [rsp+68h+var_48], rax
0x180016b79  mov     r9, rcx
0x180016b7c  mov     r8d, 68Eh
0x180016b82  lea     r14, aServicemanager_20; "ServiceManager::InitMOSAndBing"
0x180016b89  mov     rdx, r14
0x180016b8c  mov     ecx, 5
0x180016b91  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180016b97  lea     rsi, [rbx+0D48h]
0x180016b9e  lea     rdx, [rsp+68h+var_38]
0x180016ba3  mov     rcx, rsi
0x180016ba6  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180016bab  cmp     dword ptr [rbx+0DC8h], 1
0x180016bb2  jz      short loc_180016BB6
0x180016bb4  int     2Ch; Windows NT - assertion failure
0x180016bb6  lea     rcx, [rsp+68h+var_38]; this
0x180016bbb  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180016bc0  call    cs:__imp_?MosStorageEnsureIsAppContainerCompliant@@YAJXZ; MosStorageEnsureIsAppContainerCompliant(void)
0x180016bc6  test    eax, eax
0x180016bc8  jns     short loc_180016BE2
0x180016bca  mov     r8d, 699h
0x180016bd0  mov     r9, rbx
0x180016bd3  mov     rdx, r14
0x180016bd6  mov     ecx, eax
0x180016bd8  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016bde  mov     edi, eax
0x180016be0  jmp     short loc_180016C53
0x180016be2  mov     rcx, rbx; this
0x180016be5  call    ?InitializeConfigurationManager@ServiceManager@@AEAAJXZ; ServiceManager::InitializeConfigurationManager(void)
0x180016bea  test    eax, eax
0x180016bec  jns     short loc_180016BF6
0x180016bee  mov     r8d, 69Bh
0x180016bf4  jmp     short loc_180016BD0
0x180016bf6  mov     rcx, rbx; this
0x180016bf9  call    ?WriteApprovedPFNList@ServiceManager@@AEAAJXZ; ServiceManager::WriteApprovedPFNList(void)
0x180016bfe  test    eax, eax
0x180016c00  jns     short loc_180016C16
0x180016c02  mov     r9, rbx
0x180016c05  mov     r8d, 69Ch
0x180016c0b  mov     rdx, r14
0x180016c0e  mov     ecx, eax
0x180016c10  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016c16  call    cs:__imp_?SetRunningInService@ServiceRequestHelper@BingOnlineServices@@SAXXZ; BingOnlineServices::ServiceRequestHelper::SetRunningInService(void)
0x180016c1c  mov     rcx, rbx; this
0x180016c1f  call    ?InitializeMapsStore@ServiceManager@@AEAAJXZ; ServiceManager::InitializeMapsStore(void)
0x180016c24  mov     r9, rbx
0x180016c27  mov     rdx, r14
0x180016c2a  test    eax, eax
0x180016c2c  jns     short loc_180016C36
0x180016c2e  mov     r8d, 6A0h
0x180016c34  jmp     short loc_180016BD6
0x180016c36  xor     edi, edi
0x180016c38  lea     rax, aMoshostService_2; "[MosHost] Service - Startup - initializ"...
0x180016c3f  mov     [rsp+68h+var_48], rax
0x180016c44  mov     r8d, 6A2h
0x180016c4a  lea     ecx, [rdi+5]
0x180016c4d  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180016c53  lea     rdx, [rsp+68h+var_38]
0x180016c58  mov     rcx, rsi
0x180016c5b  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180016c60  nop
0x180016c61  mov     eax, edi
0x180016c63  sar     eax, 1Fh
0x180016c66  and     eax, 0FFFFFFFEh
0x180016c69  add     eax, 2
0x180016c6c  mov     [rbx+0DC8h], eax
0x180016c72  mov     [rbx+0D78h], edi
0x180016c78  test    edi, edi
0x180016c7a  jns     short loc_180016CF1
0x180016c7c  mov     rcx, rbx; this
0x180016c7f  call    ?UninitializeMOSAndBing@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeMOSAndBing(void)
0x180016c84  cmp     byte ptr [rbx+10D8h], 0
0x180016c8b  jnz     short loc_180016CD8
0x180016c8d  cmp     edi, 80070570h
0x180016c93  jz      short loc_180016CCE
0x180016c95  cmp     edi, 8401000Dh
0x180016c9b  jz      short loc_180016CCE
0x180016c9d  mov     [rsp+68h+arg_0], 0
0x180016ca2  lea     rdx, [rsp+68h+arg_0]; bool *
0x180016ca7  mov     rcx, rbx; this
0x180016caa  call    ?ScanMapDataForCorruption@ServiceManager@@AEAAJPEA_N@Z; ServiceManager::ScanMapDataForCorruption(bool *)
0x180016caf  test    eax, eax
0x180016cb1  jns     short loc_180016CC7
0x180016cb3  mov     r9, rbx
0x180016cb6  mov     r8d, 6BAh
0x180016cbc  mov     rdx, r14
0x180016cbf  mov     ecx, eax
0x180016cc1  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016cc7  cmp     [rsp+68h+arg_0], 0
0x180016ccc  jz      short loc_180016CD8
0x180016cce  mov     rcx, rbx; this
0x180016cd1  call    ?AttemptRepairMapDataAsync@ServiceManager@@AEAAXXZ; ServiceManager::AttemptRepairMapDataAsync(void)
0x180016cd6  jmp     short loc_180016CF1
0x180016cd8  mov     dword ptr [rbx+0DD0h], 0
0x180016ce2  mov     [rbx+0DD4h], edi
0x180016ce8  mov     rcx, rbx; this
0x180016ceb  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180016cf0  nop
0x180016cf1  lea     rcx, [rsp+68h+var_38]; this
0x180016cf6  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180016cfb  lea     rcx, [rsi+28h]; ConditionVariable
0x180016cff  call    cs:__imp_WakeAllConditionVariable
0x180016d05  test    edi, edi
0x180016d07  js      short loc_180016D29
0x180016d09  mov     rcx, rbx; this
0x180016d0c  call    ?UpdateCachedCopyright@ServiceManager@@AEAAJXZ; ServiceManager::UpdateCachedCopyright(void)
0x180016d11  test    eax, eax
0x180016d13  jns     short loc_180016D29
0x180016d15  mov     r9, rbx
0x180016d18  mov     r8d, 6D3h
0x180016d1e  mov     rdx, r14
0x180016d21  mov     ecx, eax
0x180016d23  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016d29  mov     eax, edi
0x180016d2b  add     rsp, 48h
0x180016d2f  pop     r14
0x180016d31  pop     rdi
0x180016d32  pop     rsi
0x180016d33  pop     rbx
0x180016d34  retn
```
