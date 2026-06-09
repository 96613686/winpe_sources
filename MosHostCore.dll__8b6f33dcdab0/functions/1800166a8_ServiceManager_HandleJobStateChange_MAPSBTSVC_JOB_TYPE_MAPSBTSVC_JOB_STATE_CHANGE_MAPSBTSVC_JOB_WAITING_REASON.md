# ServiceManager::HandleJobStateChange(MAPSBTSVC_JOB_TYPE,MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON)

- ea: `0x1800166a8`
- end: `0x18001699c`
- name: `?HandleJobStateChange@ServiceManager@@AEAAXW4MAPSBTSVC_JOB_TYPE@@W4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@Z`
- size: `756`
- prototype: `void __fastcall(__int64, int, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x180018490`

## callees

- `0x18000d3cc`
- `0x18000d538`
- `0x18000f67c`
- `0x1800165b0`
- `0x1800166a8`
- `0x1800169a4`
- `0x18001be24`
- `0x18001db8c`
- `0x18001ed28`
- `0x18001f554`
- `0x18001f650`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001675c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016780`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800167cc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016822`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016915`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001675c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016780`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800167cc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016822`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016915`
- `ZTrace_Maps!ZTraceHelper` at `0x18001670b`
- `ZTrace_Maps!ZTraceHelper` at `0x18001670b`

## string_xrefs

- `0x1800166fc`: `ServiceManager::HandleJobStateChange`

## pseudocode

```c
void __fastcall ServiceManager::HandleJobStateChange(__int64 a1, int a2, int a3, int a4)
{
  int v7; // esi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rcx
  int updated; // eax
  int v14; // esi
  int v15; // edi
  int v16; // edi
  OdmlMapDataPackage **v17; // rcx
  OdmlMapDataPackage *v18; // rcx
  int ShouldUseWlanString; // eax
  _BYTE v20[56]; // [rsp+60h] [rbp-38h] BYREF
  int v21; // [rsp+B0h] [rbp+18h] BYREF

  ZTraceHelper(
    1,
    "ServiceManager::HandleJobStateChange",
    2183,
    a1,
    "Job state change: %d | %d | %d | %d | %d | %d",
    *(_DWORD *)(a1 + 3528),
    *(_DWORD *)(a1 + 3520),
    *(_DWORD *)(a1 + 3524),
    a2,
    a3,
    a4);
  if ( !a3 )
  {
    CriticalSectionWithConditionVariable::Lock(a1 + 3400, v20);
    v14 = 0;
    v15 = a4 - 2;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 == 1 )
          v14 = 3;
      }
      else
      {
        v14 = 2;
      }
    }
    else
    {
      v14 = 1;
    }
    v17 = *(OdmlMapDataPackage ***)(a1 + 3784);
    if ( (__int64)(*(_QWORD *)(a1 + 3792) - (_QWORD)v17) >> 3 )
    {
      v18 = *v17;
      if ( *((_DWORD *)v18 + 8) == 4 || *((_DWORD *)v18 + 8) == 5 && *((_DWORD *)v18 + 11) != v14 )
      {
        *((_DWORD *)v18 + 11) = v14;
        *((_DWORD *)v18 + 8) = 5;
        OdmlMapDataPackage::FirePackageChange(v18);
      }
    }
    ServiceWatchdog::Restart(a1 + 3944, 5);
    TransferMonitor::Stop((TransferMonitor *)(a1 + 4112));
    if ( !*(_BYTE *)(a1 + 4314)
      && v14 == 2
      && (PackageManager::GetCurrentOperationInfo((PackageManager *)(a1 + 3568)) & 0x200) != 0 )
    {
      v21 = 0;
      ShouldUseWlanString = ServiceManager::GetShouldUseWlanString((ServiceManager *)a1, &v21);
      if ( ShouldUseWlanString < 0 )
        ZTraceReportIgnore(ShouldUseWlanString, "ServiceManager::HandleJobStateChange", 2219, (const void *)a1);
      ServiceManager::ShowToast(
        (ServiceManager *)a1,
        0x6Au,
        v21 != 0 ? 107 : 103,
        L"MapsOpPausedNet",
        L"LastOperationPausedByNetworkNotification",
        0x861C46800uLL,
        0,
        &dword_180027ABC,
        &dword_180027ABC,
        0,
        0);
    }
    goto LABEL_33;
  }
  v7 = a3 - 1;
  if ( !v7 )
  {
    CriticalSectionWithConditionVariable::Lock(a1 + 3400, v20);
    ServiceWatchdog::Restart(a1 + 3944, 6);
    v10 = TransferMonitor::Start((TransferMonitor *)(a1 + 4112));
    if ( v10 < 0 )
      ZTraceReportIgnore(v10, "ServiceManager::HandleJobStateChange", 2237, (const void *)a1);
    *(_BYTE *)(a1 + 4313) = 0;
    v11 = *(__int64 **)(a1 + 3784);
    if ( (__int64)(*(_QWORD *)(a1 + 3792) - (_QWORD)v11) >> 3 )
    {
      v12 = *v11;
      if ( *(_DWORD *)(v12 + 32) == 5 )
        OdmlMapDataPackage::SetState(v12, 4);
    }
    updated = ServiceManager::UpdateTransferPolicies((ServiceManager *)a1);
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::HandleJobStateChange", 2247, (const void *)a1);
LABEL_33:
    RelockableGate::~RelockableGate((RelockableGate *)v20);
    return;
  }
  if ( v7 == 1 )
  {
    ServiceWatchdog::Restart(a1 + 3944, 7);
    TransferMonitor::Stop((TransferMonitor *)(a1 + 4112));
    v8 = ServiceManager::HandleMapsInstallJobSustainedPause(a1);
    if ( v8 < 0 )
      ZTraceReportIgnore(v8, "ServiceManager::HandleJobStateChange", 2255, (const void *)a1);
    v9 = ServiceManager::UpdateTransferPolicies((ServiceManager *)a1);
    if ( v9 < 0 )
      ZTraceReportIgnore(v9, "ServiceManager::HandleJobStateChange", 2258, (const void *)a1);
  }
}

```

## disassembly

```asm
0x1800166a8  push    rbx
0x1800166aa  push    rsi
0x1800166ab  push    rdi
0x1800166ac  push    r14
0x1800166ae  sub     rsp, 78h
0x1800166b2  mov     edi, r9d
0x1800166b5  mov     esi, r8d
0x1800166b8  mov     rbx, rcx
0x1800166bb  mov     [rsp+98h+var_48], r9d
0x1800166c0  mov     [rsp+98h+var_50], r8d
0x1800166c5  mov     dword ptr [rsp+98h+var_58], edx
0x1800166c9  mov     eax, [rcx+0DC4h]
0x1800166cf  mov     dword ptr [rsp+98h+var_60], eax
0x1800166d3  mov     eax, [rcx+0DC0h]
0x1800166d9  mov     [rsp+98h+var_68], eax
0x1800166dd  mov     eax, [rcx+0DC8h]
0x1800166e3  mov     dword ptr [rsp+98h+var_70], eax
0x1800166e7  lea     rax, aJobStateChange; "Job state change: %d | %d | %d | %d | %"...
0x1800166ee  mov     [rsp+98h+var_78], rax
0x1800166f3  mov     r9, rcx
0x1800166f6  mov     r8d, 887h
0x1800166fc  lea     r14, aServicemanager_43; "ServiceManager::HandleJobStateChange"
0x180016703  mov     rdx, r14
0x180016706  mov     ecx, 1
0x18001670b  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180016711  test    esi, esi
0x180016713  jz      loc_18001682E
0x180016719  sub     esi, 1
0x18001671c  jz      short loc_18001678B
0x18001671e  cmp     esi, 1
0x180016721  jnz     loc_180016992
0x180016727  lea     rcx, [rbx+0F68h]
0x18001672e  lea     edx, [rsi+6]
0x180016731  call    ?Restart@ServiceWatchdog@@QEAAXW4RestartReason@1@@Z; ServiceWatchdog::Restart(ServiceWatchdog::RestartReason)
0x180016736  lea     rcx, [rbx+1010h]; this
0x18001673d  call    ?Stop@TransferMonitor@@QEAAXXZ; TransferMonitor::Stop(void)
0x180016742  mov     rcx, rbx
0x180016745  call    ?HandleMapsInstallJobSustainedPause@ServiceManager@@AEAAJW4MAPSBTSVC_JOB_TYPE@@@Z; ServiceManager::HandleMapsInstallJobSustainedPause(MAPSBTSVC_JOB_TYPE)
0x18001674a  test    eax, eax
0x18001674c  jns     short loc_180016762
0x18001674e  mov     r9, rbx
0x180016751  mov     r8d, 8CFh
0x180016757  mov     rdx, r14
0x18001675a  mov     ecx, eax
0x18001675c  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016762  mov     rcx, rbx; this
0x180016765  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x18001676a  test    eax, eax
0x18001676c  jns     loc_180016992
0x180016772  mov     r9, rbx
0x180016775  mov     r8d, 8D2h
0x18001677b  mov     rdx, r14
0x18001677e  mov     ecx, eax
0x180016780  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016786  jmp     loc_180016992
0x18001678b  lea     rcx, [rbx+0D48h]
0x180016792  lea     rdx, [rsp+98h+var_38]
0x180016797  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001679c  nop
0x18001679d  lea     rcx, [rbx+0F68h]
0x1800167a4  mov     edx, 6
0x1800167a9  call    ?Restart@ServiceWatchdog@@QEAAXW4RestartReason@1@@Z; ServiceWatchdog::Restart(ServiceWatchdog::RestartReason)
0x1800167ae  lea     rcx, [rbx+1010h]; this
0x1800167b5  call    ?Start@TransferMonitor@@QEAAJXZ; TransferMonitor::Start(void)
0x1800167ba  test    eax, eax
0x1800167bc  jns     short loc_1800167D2
0x1800167be  mov     r9, rbx
0x1800167c1  mov     r8d, 8BDh
0x1800167c7  mov     rdx, r14
0x1800167ca  mov     ecx, eax
0x1800167cc  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800167d2  mov     byte ptr [rbx+10D9h], 0
0x1800167d9  mov     rcx, [rbx+0EC8h]
0x1800167e0  mov     rax, [rbx+0ED0h]
0x1800167e7  sub     rax, rcx
0x1800167ea  sar     rax, 3
0x1800167ee  test    rax, rax
0x1800167f1  jz      short loc_180016808
0x1800167f3  mov     rcx, [rcx]
0x1800167f6  cmp     dword ptr [rcx+20h], 5
0x1800167fa  jnz     short loc_180016808
0x1800167fc  xor     r8d, r8d
0x1800167ff  lea     edx, [r8+4]
0x180016803  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x180016808  mov     rcx, rbx; this
0x18001680b  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x180016810  test    eax, eax
0x180016812  jns     short loc_180016829
0x180016814  mov     r9, rbx
0x180016817  mov     r8d, 8C7h
0x18001681d  mov     rdx, r14
0x180016820  mov     ecx, eax
0x180016822  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016828  nop
0x180016829  jmp     loc_180016988
0x18001682e  lea     rcx, [rbx+0D48h]
0x180016835  lea     rdx, [rsp+98h+var_38]
0x18001683a  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001683f  nop
0x180016840  xor     esi, esi
0x180016842  sub     edi, 2
0x180016845  jz      short loc_18001685D
0x180016847  sub     edi, 1
0x18001684a  jz      short loc_180016856
0x18001684c  cmp     edi, 1
0x18001684f  jnz     short loc_180016862
0x180016851  lea     esi, [rdi+2]
0x180016854  jmp     short loc_180016862
0x180016856  mov     esi, 2
0x18001685b  jmp     short loc_180016862
0x18001685d  mov     esi, 1
0x180016862  mov     rcx, [rbx+0EC8h]
0x180016869  mov     rax, [rbx+0ED0h]
0x180016870  sub     rax, rcx
0x180016873  sar     rax, 3
0x180016877  test    rax, rax
0x18001687a  jz      short loc_18001689F
0x18001687c  mov     rcx, [rcx]; this
0x18001687f  cmp     dword ptr [rcx+20h], 4
0x180016883  jz      short loc_180016890
0x180016885  cmp     dword ptr [rcx+20h], 5
0x180016889  jnz     short loc_18001689F
0x18001688b  cmp     [rcx+2Ch], esi
0x18001688e  jz      short loc_18001689F
0x180016890  mov     [rcx+2Ch], esi
0x180016893  mov     dword ptr [rcx+20h], 5
0x18001689a  call    ?FirePackageChange@OdmlMapDataPackage@@AEAAXXZ; OdmlMapDataPackage::FirePackageChange(void)
0x18001689f  lea     rcx, [rbx+0F68h]
0x1800168a6  mov     edx, 5
0x1800168ab  call    ?Restart@ServiceWatchdog@@QEAAXW4RestartReason@1@@Z; ServiceWatchdog::Restart(ServiceWatchdog::RestartReason)
0x1800168b0  lea     rcx, [rbx+1010h]; this
0x1800168b7  call    ?Stop@TransferMonitor@@QEAAXXZ; TransferMonitor::Stop(void)
0x1800168bc  cmp     byte ptr [rbx+10DAh], 0
0x1800168c3  jnz     loc_180016988
0x1800168c9  cmp     esi, 2
0x1800168cc  jnz     loc_180016988
0x1800168d2  lea     rcx, [rbx+0DF0h]; this
0x1800168d9  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x1800168de  bt      eax, 9
0x1800168e2  jnb     loc_180016988
0x1800168e8  mov     [rsp+98h+arg_10], 0
0x1800168f3  lea     rdx, [rsp+98h+arg_10]; int *
0x1800168fb  mov     rcx, rbx; this
0x1800168fe  call    ?GetShouldUseWlanString@ServiceManager@@UEAAJPEAH@Z; ServiceManager::GetShouldUseWlanString(int *)
0x180016903  test    eax, eax
0x180016905  jns     short loc_18001691B
0x180016907  mov     r9, rbx
0x18001690a  mov     r8d, 8ABh
0x180016910  mov     rdx, r14
0x180016913  mov     ecx, eax
0x180016915  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001691b  mov     eax, [rsp+98h+arg_10]
0x180016922  neg     eax
0x180016924  sbb     r8d, r8d
0x180016927  and     r8d, 4
0x18001692b  add     r8d, 67h ; 'g'; unsigned int
0x18001692f  mov     [rsp+98h+var_48], 0; unsigned int
0x180016937  mov     [rsp+98h+var_50], 0; unsigned int
0x18001693f  lea     rax, dword_180027ABC
0x180016946  mov     [rsp+98h+var_58], rax; unsigned __int16 *
0x18001694b  mov     [rsp+98h+var_60], rax; unsigned __int16 *
0x180016950  mov     [rsp+98h+var_68], 0; int
0x180016958  mov     rax, 861C46800h
0x180016962  mov     [rsp+98h+var_70], rax; unsigned __int64
0x180016967  lea     rax, aLastoperationp; "LastOperationPausedByNetworkNotificatio"...
0x18001696e  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180016973  lea     r9, aMapsoppausedne; "MapsOpPausedNet"
0x18001697a  mov     edx, 6Ah ; 'j'; unsigned int
0x18001697f  mov     rcx, rbx; this
0x180016982  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x180016987  nop
0x180016988  lea     rcx, [rsp+98h+var_38]; this
0x18001698d  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180016992  add     rsp, 78h
0x180016996  pop     r14
0x180016998  pop     rdi
0x180016999  pop     rsi
0x18001699a  pop     rbx
0x18001699b  retn
```
