# CServicesManager::StartDeviceExpiryNotificationTimer(void)

- ea: `0x1400bb5ac`
- end: `0x1400bb848`
- name: `?StartDeviceExpiryNotificationTimer@CServicesManager@@QEAAXXZ`
- size: `668`
- prototype: `void __fastcall(CServicesManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14005136c`
- `0x1400ba260`

## callees

- `0x140023cf0`
- `0x140025d38`
- `0x140026490`
- `0x140034e04`
- `0x140034ec4`
- `0x140069a90`
- `0x1400bb5ac`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb7f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb7f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb61a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb61a`

## pseudocode

```c
void __fastcall CServicesManager::StartDeviceExpiryNotificationTimer(CServicesManager *this)
{
  CNdisSpinLock *m_DeviceAndServiceUpdateLock; // rdi
  PDEVICE_OBJECT v3; // rcx
  int v4; // r9d
  bool v5; // zf
  unsigned int NextActivityId; // eax
  __int64 v7; // r10
  unsigned int v8; // r9d
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  KIRQL OldIrql; // dl
  __int64 v13; // [rsp+28h] [rbp-60h]

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      218,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
  }
  if ( this->m_P2PBackgroundNotificationsEnabled )
  {
    m_DeviceAndServiceUpdateLock = this->m_DeviceAndServiceUpdateLock;
    m_DeviceAndServiceUpdateLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_DeviceAndServiceUpdateLock->m_SpinLock.SpinLock);
    m_DeviceAndServiceUpdateLock->m_IsLocked = 1;
    if ( this->m_DeviceUpdateNotificationTimerRunning || this->m_DeviceExpiryNotificationTimerRunning )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v3 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_36;
      v4 = 219;
      goto LABEL_35;
    }
    if ( this->m_WaitingForP2PDeviceQuery )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v3 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_36;
      v4 = 220;
LABEL_35:
      WPP_RECORDER_SF_(v3->DeviceExtension, 5, 1, v4, (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
LABEL_36:
      OldIrql = m_DeviceAndServiceUpdateLock->m_SpinLock.OldIrql;
      m_DeviceAndServiceUpdateLock->m_IsLocked = 0;
      KeReleaseSpinLock(&m_DeviceAndServiceUpdateLock->m_SpinLock.SpinLock, OldIrql);
      goto LABEL_37;
    }
    if ( this->m_NotifyAllDevicesAndServices )
    {
      v5 = this->m_AllCurrentDevices == 0;
    }
    else
    {
      if ( this->m_VisibleFilteredDevices )
        goto LABEL_24;
      v5 = this->m_VisibleFilteredServices == 0;
    }
    if ( v5 )
    {
      if ( this->m_ExpiredDevicesCheckTimerToken )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            223,
            (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
        }
        EventQueue::DeregisterTimeoutCallback(&this->m_pAdapter->m_EventQueue, this->m_ExpiredDevicesCheckTimerToken);
        this->m_ExpiredDevicesCheckTimerToken = 0;
      }
      goto LABEL_36;
    }
LABEL_24:
    this->m_DeviceExpiryNotificationTimerRunning = 1;
    NextActivityId = IActivityId::get_NextActivityId();
    v9 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
           (EventQueue *)(v7 + 808),
           NextActivityId,
           this,
           v8,
           &this->m_ExpiredDevicesCheckTimerToken,
           (enum _WDF_EXECUTION_LEVEL)v13,
           0,
           0,
           &this->m_ExpiredDevicesCheckTimerToken);
    if ( v9 )
    {
      this->m_DeviceExpiryNotificationTimerRunning = 0;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v13) = v9;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          222,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          v13);
      }
    }
    else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
           && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        221,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        this->m_AllCurrentDevices,
        this->m_VisibleFilteredDevices,
        this->m_VisibleFilteredServices);
    }
    goto LABEL_36;
  }
LABEL_37:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v13) = 0;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      224,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      v13);
  }
}

```

## disassembly

```asm
0x1400bb5ac  push    rbx
0x1400bb5ae  push    rsi
0x1400bb5af  push    rdi
0x1400bb5b0  push    r12
0x1400bb5b2  push    r14
0x1400bb5b4  push    r15
0x1400bb5b6  sub     rsp, 58h
0x1400bb5ba  mov     rbx, rcx
0x1400bb5bd  xor     esi, esi; __annotation("TMF:",
0x1400bb5bf  lea     r14, WPP_RECORDER_INITIALIZED
0x1400bb5c6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bb5cd  lea     r12, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400bb5d4  lea     r15d, [rsi+1]
0x1400bb5d8  jz      short loc_1400BB606
0x1400bb5da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb5e1  cmp     byte ptr [rcx+29h], 5
0x1400bb5e5  jnb     short loc_1400BB5ED
0x1400bb5e7  cmp     [rcx+48h], si
0x1400bb5eb  jz      short loc_1400BB606
0x1400bb5ed  mov     rcx, [rcx+40h]
0x1400bb5f1  mov     r9d, 0DAh
0x1400bb5f7  mov     r8d, r15d
0x1400bb5fa  mov     [rsp+88h+var_68], r12
0x1400bb5ff  mov     dl, 5
0x1400bb601  call    WPP_RECORDER_SF_
0x1400bb606  cmp     [rbx+34h], sil
0x1400bb60a  jz      loc_1400BB800
0x1400bb610  mov     rdi, [rbx+88h]
0x1400bb617  mov     rcx, rdi; SpinLock
0x1400bb61a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bb621  nop     dword ptr [rax+rax+00h]
0x1400bb626  mov     [rdi+8], al
0x1400bb629  mov     [rdi+10h], r15b
0x1400bb62d  cmp     [rbx+84h], sil
0x1400bb634  jnz     loc_1400BB7B5
0x1400bb63a  cmp     [rbx+85h], sil
0x1400bb641  jnz     loc_1400BB7B5
0x1400bb647  cmp     [rbx+36h], sil
0x1400bb64b  jz      short loc_1400BB67C
0x1400bb64d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb654  jz      loc_1400BB7EA
0x1400bb65a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb661  cmp     byte ptr [rcx+29h], 5
0x1400bb665  jnb     short loc_1400BB671
0x1400bb667  cmp     [rcx+48h], si
0x1400bb66b  jz      loc_1400BB7EA
0x1400bb671  mov     r9d, 0DCh
0x1400bb677  jmp     loc_1400BB7D7
0x1400bb67c  cmp     [rbx+35h], sil
0x1400bb680  jz      short loc_1400BB687
0x1400bb682  cmp     [rbx+60h], esi
0x1400bb685  jmp     short loc_1400BB68F
0x1400bb687  cmp     [rbx+70h], esi
0x1400bb68a  jnz     short loc_1400BB6EA
0x1400bb68c  cmp     [rbx+74h], esi
0x1400bb68f  jnz     short loc_1400BB6EA
0x1400bb691  cmp     [rbx+7Ch], esi
0x1400bb694  jz      loc_1400BB7EA
0x1400bb69a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb6a1  jz      short loc_1400BB6CF
0x1400bb6a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb6aa  cmp     byte ptr [rcx+29h], 5
0x1400bb6ae  jnb     short loc_1400BB6B6
0x1400bb6b0  cmp     [rcx+48h], si
0x1400bb6b4  jz      short loc_1400BB6CF
0x1400bb6b6  mov     rcx, [rcx+40h]
0x1400bb6ba  mov     r9d, 0DFh
0x1400bb6c0  mov     r8d, r15d
0x1400bb6c3  mov     [rsp+88h+var_68], r12
0x1400bb6c8  mov     dl, 5
0x1400bb6ca  call    WPP_RECORDER_SF_
0x1400bb6cf  mov     rcx, [rbx+8]
0x1400bb6d3  mov     edx, [rbx+7Ch]; unsigned int
0x1400bb6d6  add     rcx, 328h; this
0x1400bb6dd  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x1400bb6e2  mov     [rbx+7Ch], esi
0x1400bb6e5  jmp     loc_1400BB7EA
0x1400bb6ea  mov     r10, [rbx+8]
0x1400bb6ee  mov     r9d, [rbx+98h]
0x1400bb6f5  mov     [rbx+85h], r15b
0x1400bb6fc  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x1400bb701  lea     rdx, [rbx+7Ch]
0x1400bb705  mov     r8, rbx; struct ITimerCallback *
0x1400bb708  mov     [rsp+88h+var_48], rdx; unsigned int *
0x1400bb70d  lea     rcx, [r10+328h]; this
0x1400bb714  mov     [rsp+88h+var_50], rsi; struct TimerRegistrationContext **
0x1400bb719  mov     [rsp+88h+var_58], sil; bool
0x1400bb71e  mov     [rsp+88h+var_68], rdx; void *
0x1400bb723  mov     edx, eax; unsigned int
0x1400bb725  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x1400bb72a  test    eax, eax
0x1400bb72c  jnz     short loc_1400BB77F
0x1400bb72e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb735  jz      loc_1400BB7EA
0x1400bb73b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb742  cmp     byte ptr [rcx+29h], 5
0x1400bb746  jnb     short loc_1400BB752
0x1400bb748  cmp     [rcx+48h], si
0x1400bb74c  jz      loc_1400BB7EA
0x1400bb752  mov     eax, [rbx+74h]
0x1400bb755  mov     r9d, 0DDh
0x1400bb75b  mov     rcx, [rcx+40h]
0x1400bb75f  mov     dl, 5
0x1400bb761  mov     dword ptr [rsp+88h+var_50], eax
0x1400bb765  mov     eax, [rbx+70h]
0x1400bb768  mov     dword ptr [rsp+88h+var_58], eax
0x1400bb76c  mov     eax, [rbx+60h]
0x1400bb76f  mov     dword ptr [rsp+88h+var_60], eax
0x1400bb773  mov     [rsp+88h+var_68], r12
0x1400bb778  call    WPP_RECORDER_SF_ddd
0x1400bb77d  jmp     short loc_1400BB7EA
0x1400bb77f  mov     [rbx+85h], sil
0x1400bb786  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb78d  jz      short loc_1400BB7EA
0x1400bb78f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb796  mov     r9d, 0DEh
0x1400bb79c  mov     dword ptr [rsp+88h+var_60], eax
0x1400bb7a0  mov     r8d, r15d
0x1400bb7a3  mov     dl, 2
0x1400bb7a5  mov     [rsp+88h+var_68], r12
0x1400bb7aa  mov     rcx, [rcx+40h]
0x1400bb7ae  call    WPP_RECORDER_SF_D
0x1400bb7b3  jmp     short loc_1400BB7EA
0x1400bb7b5  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb7bc  jz      short loc_1400BB7EA
0x1400bb7be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb7c5  cmp     byte ptr [rcx+29h], 5
0x1400bb7c9  jnb     short loc_1400BB7D1
0x1400bb7cb  cmp     [rcx+48h], si
0x1400bb7cf  jz      short loc_1400BB7EA
0x1400bb7d1  mov     r9d, 0DBh
0x1400bb7d7  mov     rcx, [rcx+40h]
0x1400bb7db  mov     r8d, r15d
0x1400bb7de  mov     dl, 5
0x1400bb7e0  mov     [rsp+88h+var_68], r12
0x1400bb7e5  call    WPP_RECORDER_SF_
0x1400bb7ea  mov     dl, [rdi+8]; NewIrql
0x1400bb7ed  mov     rcx, rdi; SpinLock
0x1400bb7f0  mov     [rdi+10h], sil
0x1400bb7f4  call    cs:__imp_KeReleaseSpinLock
0x1400bb7fb  nop     dword ptr [rax+rax+00h]
0x1400bb800  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400bb807  jz      short loc_1400BB839
0x1400bb809  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb810  cmp     byte ptr [rcx+29h], 5
0x1400bb814  jnb     short loc_1400BB81C
0x1400bb816  cmp     [rcx+48h], si
0x1400bb81a  jz      short loc_1400BB839
0x1400bb81c  mov     rcx, [rcx+40h]
0x1400bb820  mov     r9d, 0E0h
0x1400bb826  mov     dword ptr [rsp+88h+var_60], esi
0x1400bb82a  mov     r8d, r15d
0x1400bb82d  mov     dl, 5
0x1400bb82f  mov     [rsp+88h+var_68], r12
0x1400bb834  call    WPP_RECORDER_SF_D
0x1400bb839  add     rsp, 58h
0x1400bb83d  pop     r15
0x1400bb83f  pop     r14
0x1400bb841  pop     r12
0x1400bb843  pop     rdi
0x1400bb844  pop     rsi
0x1400bb845  pop     rbx
0x1400bb846  retn
```
