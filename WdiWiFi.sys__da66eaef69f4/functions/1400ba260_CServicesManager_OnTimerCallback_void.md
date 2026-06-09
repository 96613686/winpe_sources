# CServicesManager::OnTimerCallback(void *)

- ea: `0x1400ba260`
- end: `0x1400ba64a`
- name: `?OnTimerCallback@CServicesManager@@EEAAXPEAX@Z`
- size: `1002`
- prototype: `void __fastcall(CServicesManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x14000da4c`
- `0x140012214`
- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x1400b8ac8`
- `0x1400ba260`
- `0x1400bb5ac`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400ba5cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ba5cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ba2f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ba2f2`

## pseudocode

```c
void __fastcall CServicesManager::OnTimerCallback(CServicesManager *this, CServicesManager *a2)
{
  CServicesManager *v2; // rdi
  char v4; // bp
  CNdisSpinLock *m_DeviceAndServiceUpdateLock; // rsi
  unsigned int m_VisibleFilteredDevices; // edx
  int v7; // r8d
  unsigned int m_AllExpiredDevices; // eax
  PDEVICE_OBJECT v9; // rcx
  int v10; // r9d
  PDEVICE_OBJECT v11; // rcx
  int v12; // r9d
  KIRQL OldIrql; // dl
  int v14; // edx
  __int64 v15; // [rsp+28h] [rbp-60h]
  __int128 v16; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+50h] [rbp-38h]

  v2 = a2;
  v17 = 0;
  v4 = 0;
  v16 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      194,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
  }
  m_DeviceAndServiceUpdateLock = this->m_DeviceAndServiceUpdateLock;
  m_DeviceAndServiceUpdateLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_DeviceAndServiceUpdateLock->m_SpinLock.SpinLock);
  m_DeviceAndServiceUpdateLock->m_IsLocked = 1;
  if ( &this->m_DeviceUpdateNotificationTimerToken == (unsigned int *)v2 )
  {
    this->m_DeviceUpdateNotificationTimerRunning = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(m_VisibleFilteredDevices) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        m_VisibleFilteredDevices,
        1,
        195,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
    }
    goto LABEL_23;
  }
  if ( &this->m_ExpiredDevicesCheckTimerToken != (unsigned int *)v2 )
    goto LABEL_48;
  m_AllExpiredDevices = this->m_AllExpiredDevices;
  this->m_DeviceExpiryNotificationTimerRunning = 0;
  if ( m_AllExpiredDevices )
  {
    if ( this->m_NotifyAllDevicesAndServices )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_23;
      v9 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_23;
      v10 = 196;
LABEL_17:
      LOBYTE(m_VisibleFilteredDevices) = 5;
      WPP_RECORDER_SF_d(
        v9->DeviceExtension,
        m_VisibleFilteredDevices,
        v7,
        v10,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        m_AllExpiredDevices);
LABEL_23:
      v16 = *(_OWORD *)&this->m_AllCurrentDevices;
      v17 = *(_QWORD *)&this->m_VisibleFilteredDevices;
      this->m_WaitingForP2PDeviceQuery = 1;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(m_VisibleFilteredDevices) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          m_VisibleFilteredDevices,
          1,
          202,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
      }
      CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisDevicePortNumber, 1073938470, 0, &v16, 0x18u);
      goto LABEL_48;
    }
    if ( CServicesManager::CheckForExpiredDevicesAndServices(this, MEMORY[0xFFFFF78000000014]) )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_23;
      v9 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_23;
      m_AllExpiredDevices = this->m_AllExpiredDevices;
      v10 = 197;
      goto LABEL_17;
    }
    m_VisibleFilteredDevices = this->m_VisibleFilteredDevices;
    if ( !m_VisibleFilteredDevices && !this->m_VisibleFilteredServices )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_48;
      v11 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_48;
      v12 = 199;
      goto LABEL_34;
    }
    v4 = 1;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(m_VisibleFilteredDevices) = 5;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        m_VisibleFilteredDevices,
        v7,
        198,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        this->m_VisibleFilteredDevices,
        this->m_VisibleFilteredServices);
    }
  }
  else
  {
    if ( !this->m_AllCurrentDevices )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_48;
      v11 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_48;
      v12 = 201;
LABEL_34:
      LOBYTE(m_VisibleFilteredDevices) = 5;
      WPP_RECORDER_SF_(
        v11->DeviceExtension,
        m_VisibleFilteredDevices,
        1,
        v12,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
      goto LABEL_48;
    }
    v4 = 1;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(m_VisibleFilteredDevices) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        m_VisibleFilteredDevices,
        v7,
        200,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        this->m_AllCurrentDevices);
    }
  }
LABEL_48:
  OldIrql = m_DeviceAndServiceUpdateLock->m_SpinLock.OldIrql;
  m_DeviceAndServiceUpdateLock->m_IsLocked = 0;
  KeReleaseSpinLock(&m_DeviceAndServiceUpdateLock->m_SpinLock.SpinLock, OldIrql);
  if ( v4 )
    CServicesManager::StartDeviceExpiryNotificationTimer(this);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v15) = 0;
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      1,
      203,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      v15);
  }
}

```

## disassembly

```asm
0x1400ba260  mov     [rsp+arg_8], rbx
0x1400ba265  mov     [rsp+arg_10], rbp
0x1400ba26a  push    rsi
0x1400ba26b  push    rdi
0x1400ba26c  push    r12
0x1400ba26e  push    r13
0x1400ba270  push    r14
0x1400ba272  sub     rsp, 60h
0x1400ba276  mov     rax, cs:__security_cookie
0x1400ba27d  xor     rax, rsp
0x1400ba280  mov     [rsp+88h+var_30], rax
0x1400ba285  xor     r14d, r14d
0x1400ba288  xorps   xmm0, xmm0
0x1400ba28b  xor     eax, eax
0x1400ba28d  mov     rdi, rdx
0x1400ba290  mov     [rsp+88h+var_38], rax
0x1400ba295  mov     rbx, rcx
0x1400ba298  mov     bpl, r14b
0x1400ba29b  movups  [rsp+88h+var_48], xmm0
0x1400ba2a0  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ba2a7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400ba2ae  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba2b5  lea     r13d, [r14+1]
0x1400ba2b9  jz      short loc_1400BA2E8
0x1400ba2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba2c2  cmp     byte ptr [rcx+29h], 5
0x1400ba2c6  jnb     short loc_1400BA2CF
0x1400ba2c8  cmp     [rcx+48h], r14w
0x1400ba2cd  jz      short loc_1400BA2E8
0x1400ba2cf  mov     rcx, [rcx+40h]
0x1400ba2d3  mov     r9d, 0C2h
0x1400ba2d9  mov     r8d, r13d
0x1400ba2dc  mov     [rsp+88h+var_68], rax
0x1400ba2e1  mov     dl, 5
0x1400ba2e3  call    WPP_RECORDER_SF_
0x1400ba2e8  mov     rsi, [rbx+88h]
0x1400ba2ef  mov     rcx, rsi; SpinLock
0x1400ba2f2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400ba2f9  nop     dword ptr [rax+rax+00h]
0x1400ba2fe  mov     [rsi+8], al
0x1400ba301  lea     rax, [rbx+80h]
0x1400ba308  mov     [rsi+10h], r13b
0x1400ba30c  cmp     rax, rdi
0x1400ba30f  jnz     short loc_1400BA362
0x1400ba311  mov     [rbx+84h], r14b
0x1400ba318  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba31f  jz      loc_1400BA40C
0x1400ba325  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba32c  cmp     byte ptr [rcx+29h], 5
0x1400ba330  jnb     short loc_1400BA33D
0x1400ba332  cmp     [rcx+48h], r14w
0x1400ba337  jz      loc_1400BA40C
0x1400ba33d  mov     rcx, [rcx+40h]
0x1400ba341  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba348  mov     r9d, 0C3h
0x1400ba34e  mov     [rsp+88h+var_68], rdi
0x1400ba353  mov     r8d, r13d
0x1400ba356  mov     dl, 5
0x1400ba358  call    WPP_RECORDER_SF_
0x1400ba35d  jmp     loc_1400BA413
0x1400ba362  lea     rax, [rbx+7Ch]
0x1400ba366  cmp     rax, rdi
0x1400ba369  jnz     loc_1400BA5BE
0x1400ba36f  mov     eax, [rbx+68h]
0x1400ba372  mov     [rbx+85h], r14b
0x1400ba379  test    eax, eax
0x1400ba37b  jz      loc_1400BA54C
0x1400ba381  cmp     [rbx+35h], r14b
0x1400ba385  jz      short loc_1400BA3C7
0x1400ba387  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba38e  jz      short loc_1400BA40C
0x1400ba390  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba397  cmp     byte ptr [rcx+29h], 5
0x1400ba39b  jnb     short loc_1400BA3A4
0x1400ba39d  cmp     [rcx+48h], r14w
0x1400ba3a2  jz      short loc_1400BA40C
0x1400ba3a4  mov     r9d, 0C4h
0x1400ba3aa  mov     rcx, [rcx+40h]
0x1400ba3ae  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba3b5  mov     dword ptr [rsp+88h+var_60], eax
0x1400ba3b9  mov     dl, 5
0x1400ba3bb  mov     [rsp+88h+var_68], rdi
0x1400ba3c0  call    WPP_RECORDER_SF_d
0x1400ba3c5  jmp     short loc_1400BA413
0x1400ba3c7  mov     rdx, 0FFFFF78000000014h
0x1400ba3d1  mov     rcx, rbx; this
0x1400ba3d4  mov     rdx, [rdx]; unsigned __int64
0x1400ba3d7  call    ?CheckForExpiredDevicesAndServices@CServicesManager@@QEAAK_K@Z; CServicesManager::CheckForExpiredDevicesAndServices(unsigned __int64)
0x1400ba3dc  test    eax, eax
0x1400ba3de  jz      loc_1400BA4A3
0x1400ba3e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba3eb  jz      short loc_1400BA40C
0x1400ba3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba3f4  cmp     byte ptr [rcx+29h], 5
0x1400ba3f8  jnb     short loc_1400BA401
0x1400ba3fa  cmp     [rcx+48h], r14w
0x1400ba3ff  jz      short loc_1400BA40C
0x1400ba401  mov     eax, [rbx+68h]
0x1400ba404  mov     r9d, 0C5h
0x1400ba40a  jmp     short loc_1400BA3AA
0x1400ba40c  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba413  mov     eax, [rbx+60h]
0x1400ba416  mov     dword ptr [rsp+88h+var_48], eax
0x1400ba41a  mov     eax, [rbx+64h]
0x1400ba41d  mov     dword ptr [rsp+88h+var_48+4], eax
0x1400ba421  mov     eax, [rbx+68h]
0x1400ba424  mov     dword ptr [rsp+88h+var_48+8], eax
0x1400ba428  mov     eax, [rbx+6Ch]
0x1400ba42b  mov     dword ptr [rsp+88h+var_48+0Ch], eax
0x1400ba42f  mov     eax, [rbx+70h]
0x1400ba432  mov     dword ptr [rsp+88h+var_38], eax
0x1400ba436  mov     eax, [rbx+74h]
0x1400ba439  mov     dword ptr [rsp+88h+var_38+4], eax
0x1400ba43d  mov     [rbx+36h], r13b
0x1400ba441  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba448  jz      short loc_1400BA477
0x1400ba44a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba451  cmp     byte ptr [rcx+29h], 5
0x1400ba455  jnb     short loc_1400BA45E
0x1400ba457  cmp     [rcx+48h], r14w
0x1400ba45c  jz      short loc_1400BA477
0x1400ba45e  mov     rcx, [rcx+40h]
0x1400ba462  mov     r9d, 0CAh
0x1400ba468  mov     r8d, r13d
0x1400ba46b  mov     [rsp+88h+var_68], rdi
0x1400ba470  mov     dl, 5
0x1400ba472  call    WPP_RECORDER_SF_
0x1400ba477  mov     edx, [rbx+18h]; unsigned int
0x1400ba47a  lea     rax, [rsp+88h+var_48]
0x1400ba47f  mov     rcx, [rbx+8]; this
0x1400ba483  xor     r9d, r9d; void *
0x1400ba486  mov     dword ptr [rsp+88h+var_60], 18h; unsigned int
0x1400ba48e  mov     r8d, 40030026h; int
0x1400ba494  mov     [rsp+88h+var_68], rax; void *
0x1400ba499  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400ba49e  jmp     loc_1400BA5C5
0x1400ba4a3  mov     edx, [rbx+70h]
0x1400ba4a6  test    edx, edx
0x1400ba4a8  jnz     short loc_1400BA4FA
0x1400ba4aa  cmp     [rbx+74h], r14d
0x1400ba4ae  jnz     short loc_1400BA4FA
0x1400ba4b0  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba4b7  jz      loc_1400BA5BE
0x1400ba4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba4c4  cmp     byte ptr [rcx+29h], 5
0x1400ba4c8  jnb     short loc_1400BA4D5
0x1400ba4ca  cmp     [rcx+48h], r14w
0x1400ba4cf  jz      loc_1400BA5BE
0x1400ba4d5  mov     r9d, 0C7h
0x1400ba4db  mov     rcx, [rcx+40h]
0x1400ba4df  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba4e6  mov     r8d, r13d
0x1400ba4e9  mov     [rsp+88h+var_68], rdi
0x1400ba4ee  mov     dl, 5
0x1400ba4f0  call    WPP_RECORDER_SF_
0x1400ba4f5  jmp     loc_1400BA5C5
0x1400ba4fa  mov     bpl, r13b
0x1400ba4fd  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba504  jz      loc_1400BA5BE
0x1400ba50a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba511  cmp     byte ptr [rcx+29h], 5
0x1400ba515  jnb     short loc_1400BA522
0x1400ba517  cmp     [rcx+48h], r14w
0x1400ba51c  jz      loc_1400BA5BE
0x1400ba522  mov     eax, [rbx+74h]
0x1400ba525  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba52c  mov     rcx, [rcx+40h]
0x1400ba530  mov     r9d, 0C6h
0x1400ba536  mov     [rsp+88h+var_58], eax
0x1400ba53a  mov     dword ptr [rsp+88h+var_60], edx
0x1400ba53e  mov     dl, 5
0x1400ba540  mov     [rsp+88h+var_68], rdi
0x1400ba545  call    WPP_RECORDER_SF_Ld
0x1400ba54a  jmp     short loc_1400BA5C5
0x1400ba54c  mov     eax, [rbx+60h]
0x1400ba54f  test    eax, eax
0x1400ba551  jz      short loc_1400BA596
0x1400ba553  mov     bpl, r13b
0x1400ba556  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba55d  jz      short loc_1400BA5BE
0x1400ba55f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba566  cmp     byte ptr [rcx+29h], 5
0x1400ba56a  jnb     short loc_1400BA573
0x1400ba56c  cmp     [rcx+48h], r14w
0x1400ba571  jz      short loc_1400BA5BE
0x1400ba573  mov     rcx, [rcx+40h]
0x1400ba577  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba57e  mov     dword ptr [rsp+88h+var_60], eax
0x1400ba582  mov     r9d, 0C8h
0x1400ba588  mov     dl, 5
0x1400ba58a  mov     [rsp+88h+var_68], rdi
0x1400ba58f  call    WPP_RECORDER_SF_d
0x1400ba594  jmp     short loc_1400BA5C5
0x1400ba596  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba59d  jz      short loc_1400BA5BE
0x1400ba59f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba5a6  cmp     byte ptr [rcx+29h], 5
0x1400ba5aa  jnb     short loc_1400BA5B3
0x1400ba5ac  cmp     [rcx+48h], r14w
0x1400ba5b1  jz      short loc_1400BA5BE
0x1400ba5b3  mov     r9d, 0C9h
0x1400ba5b9  jmp     loc_1400BA4DB
0x1400ba5be  lea     rdi, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400ba5c5  mov     dl, [rsi+8]; NewIrql
0x1400ba5c8  mov     rcx, rsi; SpinLock
0x1400ba5cb  mov     [rsi+10h], r14b
0x1400ba5cf  call    cs:__imp_KeReleaseSpinLock
0x1400ba5d6  nop     dword ptr [rax+rax+00h]
0x1400ba5db  test    bpl, bpl
0x1400ba5de  jz      short loc_1400BA5E8
0x1400ba5e0  mov     rcx, rbx; this
0x1400ba5e3  call    ?StartDeviceExpiryNotificationTimer@CServicesManager@@QEAAXXZ; CServicesManager::StartDeviceExpiryNotificationTimer(void)
0x1400ba5e8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400ba5ef  jz      short loc_1400BA623
0x1400ba5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba5f8  cmp     byte ptr [rcx+29h], 5
0x1400ba5fc  jnb     short loc_1400BA605
0x1400ba5fe  cmp     [rcx+48h], r14w
0x1400ba603  jz      short loc_1400BA623
0x1400ba605  mov     rcx, [rcx+40h]
0x1400ba609  mov     r9d, 0CBh
0x1400ba60f  mov     dword ptr [rsp+88h+var_60], r14d
0x1400ba614  mov     r8d, r13d
0x1400ba617  mov     dl, 5
0x1400ba619  mov     [rsp+88h+var_68], rdi
0x1400ba61e  call    WPP_RECORDER_SF_D
0x1400ba623  mov     rcx, [rsp+88h+var_30]
0x1400ba628  xor     rcx, rsp; StackCookie
0x1400ba62b  call    __security_check_cookie
0x1400ba630  lea     r11, [rsp+88h+var_28]
0x1400ba635  mov     rbx, [r11+38h]
0x1400ba639  mov     rbp, [r11+40h]
0x1400ba63d  mov     rsp, r11
0x1400ba640  pop     r14
0x1400ba642  pop     r13
0x1400ba644  pop     r12
0x1400ba646  pop     rdi
0x1400ba647  pop     rsi
0x1400ba648  retn
```
