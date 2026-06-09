# ServiceManager::CompleteOperation(long)

- ea: `0x1800142c4`
- end: `0x18001473b`
- name: `?CompleteOperation@ServiceManager@@QEAAXJ@Z`
- size: `1143`
- prototype: `void __fastcall(struct _FILETIME *this, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011580`

## callees

- `0x18000bd00`
- `0x18000f67c`
- `0x18000f98c`
- `0x180010d54`
- `0x180012828`
- `0x1800142c4`
- `0x180014c00`
- `0x180015ed0`
- `0x180016d3c`
- `0x180017220`
- `0x18001aea4`
- `0x18001af8c`
- `0x18001b79c`
- `0x18001bcc0`
- `0x18001bce4`
- `0x18001bd50`
- `0x18001db8c`
- `0x18001eec4`
- `0x18001f650`
- `0x180022754`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014357`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014357`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800146ff`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800146ff`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001437b`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800143c5`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800143e7`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800145e8`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001464c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800146f5`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014728`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001437b`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800143c5`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800143e7`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800145e8`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001464c`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800146f5`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014728`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001445e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800145d0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001445e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800145d0`
- `ZTrace_Maps!ZTraceHelper` at `0x180014432`
- `ZTrace_Maps!ZTraceHelper` at `0x18001448e`
- `ZTrace_Maps!ZTraceHelper` at `0x1800144f0`
- `ZTrace_Maps!ZTraceHelper` at `0x18001458b`
- `ZTrace_Maps!ZTraceHelper` at `0x18001462a`
- `ZTrace_Maps!ZTraceHelper` at `0x180014432`
- `ZTrace_Maps!ZTraceHelper` at `0x18001448e`
- `ZTrace_Maps!ZTraceHelper` at `0x1800144f0`
- `ZTrace_Maps!ZTraceHelper` at `0x18001458b`
- `ZTrace_Maps!ZTraceHelper` at `0x18001462a`

## string_xrefs

- `0x18001435d`: `LastMapUpdateDate`
- `0x180014567`: `(Un)Installation is pausing`
- `0x180014340`: `ServiceManager::CompleteOperation`
- `0x1800144e1`: `ServiceManager::CompleteOperation`
- `0x18001457c`: `ServiceManager::CompleteOperation`
- `0x18001461b`: `ServiceManager::CompleteOperation`
- `0x1800144cc`: `(Un)Installation is suspending`
- `0x180014606`: `(Un)Installation is cancelling: 0x%08X`
- `0x1800145c7`: `ServiceManager::ShowDelayedPausedToast`

## pseudocode

```c
void __fastcall ServiceManager::CompleteOperation(struct _FILETIME *this, int a2)
{
  char v4; // r14
  RTL_CONDITION_VARIABLE *v5; // r15
  DWORD dwHighDateTime; // ecx
  char v7; // di
  DWORD dwLowDateTime; // eax
  ServiceManager *v9; // rcx
  int v10; // eax
  int updated; // eax
  int v12; // r8d
  int v13; // eax
  DWORD v14; // eax
  int inited; // eax
  int v16; // r8d
  int v17; // ebp
  DWORD v18; // ecx
  DWORD v19; // ecx
  int v20; // eax
  bool v21; // bp
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  struct OdmlMapDataPackage *NextPendingOperationIfAvailable; // rax
  int v27; // eax
  int Operation; // eax
  _BYTE v29[72]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  v5 = (RTL_CONDITION_VARIABLE *)&this[425];
  CriticalSectionWithConditionVariable::Lock(&this[425], v29);
  ServiceWatchdog::Stop((ServiceWatchdog *)&this[493]);
  TransferMonitor::Stop((TransferMonitor *)&this[514]);
  ServiceManager::AddCumulativeOperationTime((ServiceManager *)this);
  ServiceManager::LogOperationEndTelemetry((ServiceManager *)this, a2);
  dwHighDateTime = this[440].dwHighDateTime;
  v7 = 1;
  if ( dwHighDateTime - 5 > 1 )
  {
    dwLowDateTime = this[440].dwLowDateTime;
    if ( !dwLowDateTime )
      __int2c();
    if ( !dwHighDateTime )
      __int2c();
    if ( dwLowDateTime == 3 )
    {
      if ( a2 >= 0 )
      {
        GetSystemTimeAsFileTime(this + 445);
        v10 = ServiceManager::SetMapsRegDateToNow(v9, L"LastMapUpdateDate");
        if ( v10 < 0 )
          ZTraceReportIgnore(v10, "ServiceManager::CompleteOperation", 351, this);
        this[443].dwLowDateTime = 1;
        updated = ServiceManager::SetUpdateAvailability(this, 1);
        if ( updated < 0 )
        {
          v12 = 356;
LABEL_16:
          ZTraceReportIgnore(updated, "ServiceManager::CompleteOperation", v12, this);
        }
      }
    }
    else if ( dwLowDateTime == 1 && a2 < 0 )
    {
      updated = ServiceManager::ShowDownloadErrorToast((ServiceManager *)this, this[476].dwLowDateTime);
      if ( updated < 0 )
      {
        v12 = 360;
        goto LABEL_16;
      }
    }
    v13 = ServiceManager::OnOperationComplete((ServiceManager *)this, a2);
    if ( v13 < 0 )
      ZTraceReportIgnore(v13, "ServiceManager::CompleteOperation", 363, this);
    v14 = this[441].dwLowDateTime;
    if ( v14 == 4 )
    {
      if ( a2 >= 0 )
      {
        inited = ServiceManager::InitODML((ServiceManager *)this);
        if ( inited < 0 )
        {
          v7 = 0;
          v16 = 371;
LABEL_27:
          v17 = ZTraceReportPropagation(inited, "ServiceManager::CompleteOperation", v16, this);
          goto LABEL_61;
        }
        v4 = 1;
LABEL_23:
        ZTraceHelper(3, "ServiceManager::CompleteOperation", 382, this, "Operation finishes successfully");
        goto LABEL_51;
      }
    }
    else if ( v14 != 5 )
    {
      goto LABEL_22;
    }
    this[442].dwLowDateTime = 1;
    this[442].dwHighDateTime = a2;
    ServiceManager::FireOdmlStateChange((ServiceManager *)this);
LABEL_22:
    if ( a2 < 0 )
    {
      ZTraceHelper(0, "ServiceManager::CompleteOperation", 386, this, "Operation finishes with error code: 0x%08X", a2);
      goto LABEL_51;
    }
    goto LABEL_23;
  }
  v18 = this[441].dwHighDateTime;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( !v19 )
    {
      v21 = 0;
      __int2c();
      this[440].dwHighDateTime = 1;
      if ( this[440].dwLowDateTime == 1 )
      {
        v21 = (PackageManager::GetCurrentOperationInfo((PackageManager *)&this[446]) & 0x200) != 0;
        PackageManager::SetCurrentOperationInfoFlag(v22, 32);
      }
      else if ( this[440].dwLowDateTime == 3 )
      {
        v21 = BYTE2(this[539].dwLowDateTime) == 0;
      }
      ZTraceHelper(3, "ServiceManager::CompleteOperation", 302, this, "(Un)Installation is pausing");
      if ( v21 )
      {
        v23 = TimerQueue::QueueTimer(
                (TimerQueue *)&this[535],
                lambda_079228dceaa146165263bf89c14cc50e_::_lambda_invoker_cdecl_,
                this,
                0xBB8u,
                0);
        if ( v23 < 0 )
        {
          v24 = ZTraceReportPropagation(v23, "ServiceManager::ShowDelayedPausedToast", 3433, this);
          if ( v24 < 0 )
            ZTraceReportIgnore(v24, "ServiceManager::CompleteOperation", 310, this);
        }
      }
      v20 = (this[440].dwLowDateTime != 3) + 6;
      goto LABEL_36;
    }
    if ( v19 == 1 )
    {
      if ( this[440].dwLowDateTime == 1 )
        PackageManager::SetCurrentOperationInfoFlag(&this[446], 128);
      ZTraceHelper(3, "ServiceManager::CompleteOperation", 321, this, "(Un)Installation is suspending");
      ServiceManager::ResetOperationState((ServiceManager *)this);
      v20 = (this[440].dwLowDateTime != 3) + 8;
LABEL_36:
      this[442].dwLowDateTime = v20;
      this[442].dwHighDateTime = 0;
LABEL_50:
      ServiceManager::FireOdmlStateChange((ServiceManager *)this);
      goto LABEL_51;
    }
  }
  ZTraceHelper(3, "ServiceManager::CompleteOperation", 331, this, "(Un)Installation is cancelling: 0x%08X", a2);
  v25 = ServiceManager::OnOperationComplete((ServiceManager *)this, a2);
  if ( v25 < 0 )
    ZTraceReportIgnore(v25, "ServiceManager::CompleteOperation", 333, this);
  if ( this[441].dwLowDateTime - 4 <= 1 )
  {
    this[442].dwLowDateTime = 1;
    this[442].dwHighDateTime = a2;
    goto LABEL_50;
  }
LABEL_51:
  NextPendingOperationIfAvailable = PackageManager::GetNextPendingOperationIfAvailable((PackageManager *)&this[446]);
  if ( NextPendingOperationIfAvailable || this[440].dwHighDateTime == 1 )
    LOBYTE(NextPendingOperationIfAvailable) = 1;
  if ( HIBYTE(this[539].dwLowDateTime)
    || v4
    || !(_BYTE)NextPendingOperationIfAvailable && !MigrationEngine::IsMigrationPending((MigrationEngine *)&this[1]) )
  {
    v7 = 0;
    inited = ServiceManager::DetachClient((__int64)this, 2u, 0);
    if ( inited < 0 )
    {
      v16 = 399;
      goto LABEL_27;
    }
  }
  v17 = 0;
LABEL_61:
  RelockableGate::~RelockableGate((RelockableGate *)v29);
  v27 = ServiceManager::UpdateTransferPolicies((ServiceManager *)this);
  if ( v27 < 0 )
    ZTraceReportIgnore(v27, "ServiceManager::CompleteOperation", 405, this);
  WakeAllConditionVariable(v5 + 5);
  if ( v17 >= 0 && v7 )
  {
    Operation = ServiceManager::ProcessNextOperation((ServiceManager *)this);
    if ( Operation < 0 )
      ZTraceReportIgnore(Operation, "ServiceManager::CompleteOperation", 411, this);
  }
}

```

## disassembly

```asm
0x1800142c4  push    rbx
0x1800142c6  push    rbp
0x1800142c7  push    rsi
0x1800142c8  push    rdi
0x1800142c9  push    r14
0x1800142cb  push    r15
0x1800142cd  sub     rsp, 48h
0x1800142d1  mov     ebp, edx
0x1800142d3  mov     rbx, rcx
0x1800142d6  xor     r14b, r14b
0x1800142d9  lea     r15, [rcx+0D48h]
0x1800142e0  lea     rdx, [rsp+78h+var_48]
0x1800142e5  mov     rcx, r15
0x1800142e8  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800142ed  nop
0x1800142ee  lea     rcx, [rbx+0F68h]; this
0x1800142f5  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x1800142fa  lea     rcx, [rbx+1010h]; this
0x180014301  call    ?Stop@TransferMonitor@@QEAAXXZ; TransferMonitor::Stop(void)
0x180014306  mov     rcx, rbx; this
0x180014309  call    ?AddCumulativeOperationTime@ServiceManager@@AEAAXXZ; ServiceManager::AddCumulativeOperationTime(void)
0x18001430e  mov     edx, ebp; int
0x180014310  mov     rcx, rbx; this
0x180014313  call    ?LogOperationEndTelemetry@ServiceManager@@AEAAXJ@Z; ServiceManager::LogOperationEndTelemetry(long)
0x180014318  mov     ecx, [rbx+0DC4h]
0x18001431e  lea     eax, [rcx-5]
0x180014321  mov     edi, 1
0x180014326  cmp     eax, edi
0x180014328  jbe     loc_180014499
0x18001432e  mov     eax, [rbx+0DC0h]
0x180014334  test    eax, eax
0x180014336  jnz     short loc_18001433A
0x180014338  int     2Ch; Windows NT - assertion failure
0x18001433a  test    ecx, ecx
0x18001433c  jnz     short loc_180014340
0x18001433e  int     2Ch; Windows NT - assertion failure
0x180014340  lea     rsi, aServicemanager_53; "ServiceManager::CompleteOperation"
0x180014347  cmp     eax, 3
0x18001434a  jnz     short loc_18001439D
0x18001434c  test    ebp, ebp
0x18001434e  js      short loc_1800143CB
0x180014350  lea     rcx, [rbx+0DE8h]; lpSystemTimeAsFileTime
0x180014357  call    cs:__imp_GetSystemTimeAsFileTime
0x18001435d  lea     rdx, aLastmapupdated; "LastMapUpdateDate"
0x180014364  call    ?SetMapsRegDateToNow@ServiceManager@@AEAAJPEBG@Z; ServiceManager::SetMapsRegDateToNow(ushort const *)
0x180014369  test    eax, eax
0x18001436b  jns     short loc_180014381
0x18001436d  mov     r9, rbx
0x180014370  mov     r8d, 15Fh
0x180014376  mov     rdx, rsi
0x180014379  mov     ecx, eax
0x18001437b  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014381  mov     [rbx+0DD8h], edi
0x180014387  mov     edx, edi
0x180014389  mov     rcx, rbx
0x18001438c  call    ?SetUpdateAvailability@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z; ServiceManager::SetUpdateAvailability(__MIDL_odmlapi_0005)
0x180014391  test    eax, eax
0x180014393  jns     short loc_1800143CB
0x180014395  mov     r8d, 164h
0x18001439b  jmp     short loc_1800143BD
0x18001439d  cmp     eax, edi
0x18001439f  jnz     short loc_1800143CB
0x1800143a1  test    ebp, ebp
0x1800143a3  jns     short loc_1800143CB
0x1800143a5  mov     edx, [rbx+0EE0h]; unsigned int
0x1800143ab  mov     rcx, rbx; this
0x1800143ae  call    ?ShowDownloadErrorToast@ServiceManager@@AEAAJI@Z; ServiceManager::ShowDownloadErrorToast(uint)
0x1800143b3  test    eax, eax
0x1800143b5  jns     short loc_1800143CB
0x1800143b7  mov     r8d, 168h
0x1800143bd  mov     r9, rbx
0x1800143c0  mov     rdx, rsi
0x1800143c3  mov     ecx, eax
0x1800143c5  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800143cb  mov     edx, ebp; int
0x1800143cd  mov     rcx, rbx; this
0x1800143d0  call    ?OnOperationComplete@ServiceManager@@AEAAJJ@Z; ServiceManager::OnOperationComplete(long)
0x1800143d5  test    eax, eax
0x1800143d7  jns     short loc_1800143ED
0x1800143d9  mov     r9, rbx
0x1800143dc  mov     r8d, 16Bh
0x1800143e2  mov     rdx, rsi
0x1800143e5  mov     ecx, eax
0x1800143e7  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800143ed  mov     eax, [rbx+0DC8h]
0x1800143f3  cmp     eax, 4
0x1800143f6  jz      short loc_18001443D
0x1800143f8  cmp     eax, 5
0x1800143fb  jnz     short loc_180014411
0x1800143fd  mov     [rbx+0DD0h], edi
0x180014403  mov     [rbx+0DD4h], ebp
0x180014409  mov     rcx, rbx; this
0x18001440c  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014411  test    ebp, ebp
0x180014413  js      short loc_180014470
0x180014415  lea     rax, aOperationFinis; "Operation finishes successfully"
0x18001441c  mov     qword ptr [rsp+78h+var_58], rax
0x180014421  mov     r9, rbx
0x180014424  mov     r8d, 17Eh
0x18001442a  mov     rdx, rsi
0x18001442d  mov     ecx, 3
0x180014432  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180014438  jmp     loc_180014673
0x18001443d  test    ebp, ebp
0x18001443f  js      short loc_1800143FD
0x180014441  mov     rcx, rbx; this
0x180014444  call    ?InitODML@ServiceManager@@AEAAJXZ; ServiceManager::InitODML(void)
0x180014449  test    eax, eax
0x18001444b  jns     short loc_18001446B
0x18001444d  xor     dil, dil
0x180014450  mov     r8d, 173h
0x180014456  mov     r9, rbx
0x180014459  mov     rdx, rsi
0x18001445c  mov     ecx, eax
0x18001445e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180014464  mov     ebp, eax
0x180014466  jmp     loc_1800146D1
0x18001446b  mov     r14b, dil
0x18001446e  jmp     short loc_180014415
0x180014470  mov     [rsp+78h+var_50], ebp
0x180014474  lea     rax, aOperationFinis_0; "Operation finishes with error code: 0x%"...
0x18001447b  mov     qword ptr [rsp+78h+var_58], rax
0x180014480  mov     r9, rbx
0x180014483  mov     r8d, 182h
0x180014489  mov     rdx, rsi
0x18001448c  xor     ecx, ecx
0x18001448e  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180014494  jmp     loc_180014673
0x180014499  mov     ecx, [rbx+0DCCh]
0x18001449f  test    ecx, ecx
0x1800144a1  jz      loc_180014602
0x1800144a7  sub     ecx, edi
0x1800144a9  jz      short loc_180014522
0x1800144ab  cmp     ecx, edi
0x1800144ad  jnz     loc_180014602
0x1800144b3  cmp     [rbx+0DC0h], edi
0x1800144b9  jnz     short loc_1800144CC
0x1800144bb  lea     rcx, [rbx+0DF0h]
0x1800144c2  mov     edx, 80h
0x1800144c7  call    ?SetCurrentOperationInfoFlag@PackageManager@@QEAAXW4__MIDL_odmlapi_0003@@@Z; PackageManager::SetCurrentOperationInfoFlag(__MIDL_odmlapi_0003)
0x1800144cc  lea     rax, aUnInstallation_0; "(Un)Installation is suspending"
0x1800144d3  mov     qword ptr [rsp+78h+var_58], rax
0x1800144d8  mov     r9, rbx
0x1800144db  mov     r8d, 141h
0x1800144e1  lea     rsi, aServicemanager_53; "ServiceManager::CompleteOperation"
0x1800144e8  mov     rdx, rsi
0x1800144eb  mov     ecx, 3
0x1800144f0  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x1800144f6  mov     rcx, rbx; this
0x1800144f9  call    ?ResetOperationState@ServiceManager@@AEAAXXZ; ServiceManager::ResetOperationState(void)
0x1800144fe  xor     eax, eax
0x180014500  cmp     dword ptr [rbx+0DC0h], 3
0x180014507  setnz   al
0x18001450a  add     eax, 8
0x18001450d  mov     [rbx+0DD0h], eax
0x180014513  mov     dword ptr [rbx+0DD4h], 0
0x18001451d  jmp     loc_18001466B
0x180014522  xor     bpl, bpl
0x180014525  int     2Ch; Windows NT - assertion failure
0x180014527  mov     [rbx+0DC4h], edi
0x18001452d  mov     ecx, [rbx+0DC0h]
0x180014533  sub     ecx, edi
0x180014535  jz      short loc_180014549
0x180014537  cmp     ecx, 2
0x18001453a  jnz     short loc_180014567
0x18001453c  cmp     [rbx+10DAh], bpl
0x180014543  setz    bpl
0x180014547  jmp     short loc_180014567
0x180014549  lea     rcx, [rbx+0DF0h]; this
0x180014550  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180014555  mov     ebp, eax
0x180014557  shr     ebp, 9
0x18001455a  and     bpl, dil
0x18001455d  mov     edx, 20h ; ' '
0x180014562  call    ?SetCurrentOperationInfoFlag@PackageManager@@QEAAXW4__MIDL_odmlapi_0003@@@Z; PackageManager::SetCurrentOperationInfoFlag(__MIDL_odmlapi_0003)
0x180014567  lea     rax, aUnInstallation_1; "(Un)Installation is pausing"
0x18001456e  mov     qword ptr [rsp+78h+var_58], rax
0x180014573  mov     r9, rbx
0x180014576  mov     r8d, 12Eh
0x18001457c  lea     rsi, aServicemanager_53; "ServiceManager::CompleteOperation"
0x180014583  mov     rdx, rsi
0x180014586  mov     ecx, 3
0x18001458b  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180014591  test    bpl, bpl
0x180014594  jz      short loc_1800145EE
0x180014596  lea     rcx, [rbx+10B8h]; this
0x18001459d  mov     [rsp+78h+var_58], 0; unsigned int
0x1800145a5  mov     r9d, 0BB8h; unsigned int
0x1800145ab  mov     r8, rbx; void *
0x1800145ae  lea     rdx, _lambda_079228dceaa146165263bf89c14cc50e____lambda_invoker_cdecl_; void (*)(void *)
0x1800145b5  call    ?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z; TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)
0x1800145ba  test    eax, eax
0x1800145bc  jns     short loc_1800145EE
0x1800145be  mov     r9, rbx
0x1800145c1  mov     r8d, 0D69h
0x1800145c7  lea     rdx, aServicemanager_51; "ServiceManager::ShowDelayedPausedToast"
0x1800145ce  mov     ecx, eax
0x1800145d0  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800145d6  test    eax, eax
0x1800145d8  jns     short loc_1800145EE
0x1800145da  mov     r9, rbx
0x1800145dd  mov     r8d, 136h
0x1800145e3  mov     rdx, rsi
0x1800145e6  mov     ecx, eax
0x1800145e8  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800145ee  xor     eax, eax
0x1800145f0  cmp     dword ptr [rbx+0DC0h], 3
0x1800145f7  setnz   al
0x1800145fa  add     eax, 6
0x1800145fd  jmp     loc_18001450D
0x180014602  mov     [rsp+78h+var_50], ebp
0x180014606  lea     rax, aUnInstallation; "(Un)Installation is cancelling: 0x%08X"
0x18001460d  mov     qword ptr [rsp+78h+var_58], rax
0x180014612  mov     r9, rbx
0x180014615  mov     r8d, 14Bh
0x18001461b  lea     rsi, aServicemanager_53; "ServiceManager::CompleteOperation"
0x180014622  mov     rdx, rsi
0x180014625  mov     ecx, 3
0x18001462a  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180014630  mov     edx, ebp; int
0x180014632  mov     rcx, rbx; this
0x180014635  call    ?OnOperationComplete@ServiceManager@@AEAAJJ@Z; ServiceManager::OnOperationComplete(long)
0x18001463a  test    eax, eax
0x18001463c  jns     short loc_180014652
0x18001463e  mov     r9, rbx
0x180014641  mov     r8d, 14Dh
0x180014647  mov     rdx, rsi
0x18001464a  mov     ecx, eax
0x18001464c  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014652  mov     eax, [rbx+0DC8h]
0x180014658  sub     eax, 4
0x18001465b  cmp     eax, edi
0x18001465d  ja      short loc_180014673
0x18001465f  mov     [rbx+0DD0h], edi
0x180014665  mov     [rbx+0DD4h], ebp
0x18001466b  mov     rcx, rbx; this
0x18001466e  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014673  lea     rcx, [rbx+0DF0h]; this
0x18001467a  call    ?GetNextPendingOperationIfAvailable@PackageManager@@QEAAPEAVOdmlMapDataPackage@@XZ; PackageManager::GetNextPendingOperationIfAvailable(void)
0x18001467f  test    rax, rax
0x180014682  jnz     short loc_18001468C
0x180014684  cmp     [rbx+0DC4h], edi
0x18001468a  jnz     short loc_18001468F
0x18001468c  mov     al, dil
0x18001468f  cmp     byte ptr [rbx+10DBh], 0
0x180014696  jnz     short loc_1800146AE
0x180014698  test    r14b, r14b
0x18001469b  jnz     short loc_1800146AE
0x18001469d  test    al, al
0x18001469f  jnz     short loc_1800146CF
0x1800146a1  lea     rcx, [rbx+8]; this
0x1800146a5  call    ?IsMigrationPending@MigrationEngine@@IEAA_NXZ; MigrationEngine::IsMigrationPending(void)
0x1800146aa  test    al, al
0x1800146ac  jnz     short loc_1800146CF
0x1800146ae  xor     dil, dil
0x1800146b1  xor     r8d, r8d
0x1800146b4  lea     edx, [r8+2]
0x1800146b8  mov     rcx, rbx
0x1800146bb  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x1800146c0  test    eax, eax
0x1800146c2  jns     short loc_1800146CF
0x1800146c4  mov     r8d, 18Fh
0x1800146ca  jmp     loc_180014456
0x1800146cf  xor     ebp, ebp
0x1800146d1  lea     rcx, [rsp+78h+var_48]; this
0x1800146d6  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800146db  mov     rcx, rbx; this
0x1800146de  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x1800146e3  test    eax, eax
0x1800146e5  jns     short loc_1800146FB
0x1800146e7  mov     r9, rbx
0x1800146ea  mov     r8d, 195h
0x1800146f0  mov     rdx, rsi
0x1800146f3  mov     ecx, eax
0x1800146f5  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800146fb  lea     rcx, [r15+28h]; ConditionVariable
0x1800146ff  call    cs:__imp_WakeAllConditionVariable
0x180014705  test    ebp, ebp
0x180014707  js      short loc_18001472E
0x180014709  test    dil, dil
0x18001470c  jz      short loc_18001472E
0x18001470e  mov     rcx, rbx; this
0x180014711  call    ?ProcessNextOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessNextOperation(void)
0x180014716  test    eax, eax
0x180014718  jns     short loc_18001472E
0x18001471a  mov     r9, rbx
0x18001471d  mov     r8d, 19Bh
0x180014723  mov     rdx, rsi
0x180014726  mov     ecx, eax
0x180014728  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001472e  add     rsp, 48h
0x180014732  pop     r15
0x180014734  pop     r14
0x180014736  pop     rdi
0x180014737  pop     rsi
0x180014738  pop     rbp
0x180014739  pop     rbx
0x18001473a  retn
```
