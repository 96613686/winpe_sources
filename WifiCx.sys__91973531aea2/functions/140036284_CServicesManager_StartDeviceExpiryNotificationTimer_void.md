# CServicesManager::StartDeviceExpiryNotificationTimer(void)

- ea: `0x140036284`
- end: `0x140036538`
- name: `?StartDeviceExpiryNotificationTimer@CServicesManager@@QEAAXXZ`
- size: `692`
- prototype: `void __fastcall(CServicesManager *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x140037190`
- `0x14003759c`
- `0x14009454c`

## callees

- `0x14000c778`
- `0x14000cf40`
- `0x14000d054`
- `0x14001a1e0`
- `0x140024004`
- `0x140036284`
- `0x140036540`
- `0x140050574`
- `0x140061544`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400364e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400364e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003630a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003630a`

## pseudocode

```c
void __fastcall CServicesManager::StartDeviceExpiryNotificationTimer(CServicesManager *this, __int64 a2, __int64 a3)
{
  int v4; // edx
  __int64 v5; // rdi
  int v6; // edx
  PDEVICE_OBJECT v7; // rcx
  int v8; // r9d
  bool v9; // zf
  unsigned int NextActivityId; // eax
  __int64 v11; // r10
  unsigned int v12; // r9d
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  KIRQL v16; // dl
  __int64 v17; // [rsp+28h] [rbp-60h]

  if ( (unsigned int)Feature_54699885__private_IsEnabledDeviceUsageNoInline(this, a2, a3) )
  {
    CServicesManager::StartDeviceExpiryNotificationTimer_WDFLocks(this);
    return;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      259,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
  }
  if ( *((_BYTE *)this + 52) )
  {
    v5 = *((_QWORD *)this + 17);
    *(_BYTE *)(v5 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
    *(_BYTE *)(v5 + 16) = 1;
    if ( *((_BYTE *)this + 132) || *((_BYTE *)this + 133) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_38;
      v7 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_38;
      v8 = 260;
      goto LABEL_37;
    }
    if ( *((_BYTE *)this + 54) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_38;
      v7 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_38;
      v8 = 261;
LABEL_37:
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(v7->DeviceExtension, v6, 1, v8, (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
LABEL_38:
      v16 = *(_BYTE *)(v5 + 8);
      *(_BYTE *)(v5 + 16) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)v5, v16);
      goto LABEL_39;
    }
    if ( *((_BYTE *)this + 53) )
    {
      v9 = *((_DWORD *)this + 24) == 0;
    }
    else
    {
      if ( *((_DWORD *)this + 28) )
        goto LABEL_26;
      v9 = *((_DWORD *)this + 29) == 0;
    }
    if ( v9 )
    {
      if ( *((_DWORD *)this + 31) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v6) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            1,
            264,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
        }
        EventQueue::DeregisterTimeoutCallback((EventQueue *)(*((_QWORD *)this + 1) + 736LL), *((_DWORD *)this + 31));
        *((_DWORD *)this + 31) = 0;
      }
      goto LABEL_38;
    }
LABEL_26:
    *((_BYTE *)this + 133) = 1;
    NextActivityId = IActivityId::get_NextActivityId();
    v13 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
            (EventQueue *)(v11 + 736),
            NextActivityId,
            this,
            v12,
            (char *)this + 124,
            (enum _WDF_EXECUTION_LEVEL)v17,
            0,
            0,
            (unsigned int *)this + 31);
    if ( v13 )
    {
      *((_BYTE *)this + 133) = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v17) = v13;
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          263,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v17);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
           && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v14) = 5;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v15,
        262,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        *((_DWORD *)this + 24),
        *((_DWORD *)this + 28),
        *((_DWORD *)this + 29));
    }
    goto LABEL_38;
  }
LABEL_39:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v17) = 0;
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      265,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v17);
  }
}

```

## disassembly

```asm
0x140036284  push    rbx
0x140036286  push    rsi
0x140036287  push    rdi
0x140036288  push    r12
0x14003628a  push    r14
0x14003628c  push    r15
0x14003628e  sub     rsp, 58h
0x140036292  mov     rbx, rcx
0x140036295  call    Feature_54699885__private_IsEnabledDeviceUsageNoInline
0x14003629a  xor     esi, esi
0x14003629c  test    eax, eax
0x14003629e  jz      short loc_1400362AD
0x1400362a0  mov     rcx, rbx; this
0x1400362a3  call    ?StartDeviceExpiryNotificationTimer_WDFLocks@CServicesManager@@QEAAXXZ; CServicesManager::StartDeviceExpiryNotificationTimer_WDFLocks(void)
0x1400362a8  jmp     loc_140036529
0x1400362ad  lea     r14, WPP_RECORDER_INITIALIZED
0x1400362b4  mov     r15d, 1
0x1400362ba  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400362c1  lea     r12, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400362c8  jz      short loc_1400362F6
0x1400362ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400362d1  cmp     byte ptr [rcx+29h], 5
0x1400362d5  jnb     short loc_1400362DD
0x1400362d7  cmp     [rcx+48h], si
0x1400362db  jz      short loc_1400362F6
0x1400362dd  mov     rcx, [rcx+40h]
0x1400362e1  mov     r9d, 103h
0x1400362e7  mov     r8d, r15d
0x1400362ea  mov     [rsp+88h+var_68], r12
0x1400362ef  mov     dl, 5
0x1400362f1  call    WPP_RECORDER_SF_
0x1400362f6  cmp     [rbx+34h], sil
0x1400362fa  jz      loc_1400364F0
0x140036300  mov     rdi, [rbx+88h]
0x140036307  mov     rcx, rdi; SpinLock
0x14003630a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036311  nop     dword ptr [rax+rax+00h]
0x140036316  mov     [rdi+8], al
0x140036319  mov     [rdi+10h], r15b
0x14003631d  cmp     [rbx+84h], sil
0x140036324  jnz     loc_1400364A5
0x14003632a  cmp     [rbx+85h], sil
0x140036331  jnz     loc_1400364A5
0x140036337  cmp     [rbx+36h], sil
0x14003633b  jz      short loc_14003636C
0x14003633d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036344  jz      loc_1400364DA
0x14003634a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036351  cmp     byte ptr [rcx+29h], 5
0x140036355  jnb     short loc_140036361
0x140036357  cmp     [rcx+48h], si
0x14003635b  jz      loc_1400364DA
0x140036361  mov     r9d, 105h
0x140036367  jmp     loc_1400364C7
0x14003636c  cmp     [rbx+35h], sil
0x140036370  jz      short loc_140036377
0x140036372  cmp     [rbx+60h], esi
0x140036375  jmp     short loc_14003637F
0x140036377  cmp     [rbx+70h], esi
0x14003637a  jnz     short loc_1400363DA
0x14003637c  cmp     [rbx+74h], esi
0x14003637f  jnz     short loc_1400363DA
0x140036381  cmp     [rbx+7Ch], esi
0x140036384  jz      loc_1400364DA
0x14003638a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036391  jz      short loc_1400363BF
0x140036393  mov     rcx, cs:WPP_GLOBAL_Control
0x14003639a  cmp     byte ptr [rcx+29h], 5
0x14003639e  jnb     short loc_1400363A6
0x1400363a0  cmp     [rcx+48h], si
0x1400363a4  jz      short loc_1400363BF
0x1400363a6  mov     rcx, [rcx+40h]
0x1400363aa  mov     r9d, 108h
0x1400363b0  mov     r8d, r15d
0x1400363b3  mov     [rsp+88h+var_68], r12
0x1400363b8  mov     dl, 5
0x1400363ba  call    WPP_RECORDER_SF_
0x1400363bf  mov     rcx, [rbx+8]
0x1400363c3  mov     edx, [rbx+7Ch]; unsigned int
0x1400363c6  add     rcx, 2E0h; this
0x1400363cd  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x1400363d2  mov     [rbx+7Ch], esi
0x1400363d5  jmp     loc_1400364DA
0x1400363da  mov     r10, [rbx+8]
0x1400363de  mov     r9d, [rbx+0A0h]
0x1400363e5  mov     [rbx+85h], r15b
0x1400363ec  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x1400363f1  lea     rdx, [rbx+7Ch]
0x1400363f5  mov     r8, rbx; struct ITimerCallback *
0x1400363f8  mov     [rsp+88h+var_48], rdx; unsigned int *
0x1400363fd  lea     rcx, [r10+2E0h]; this
0x140036404  mov     [rsp+88h+var_50], rsi; struct TimerRegistrationContext **
0x140036409  mov     [rsp+88h+var_58], sil; bool
0x14003640e  mov     [rsp+88h+var_68], rdx; void *
0x140036413  mov     edx, eax; unsigned int
0x140036415  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x14003641a  test    eax, eax
0x14003641c  jnz     short loc_14003646F
0x14003641e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036425  jz      loc_1400364DA
0x14003642b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036432  cmp     byte ptr [rcx+29h], 5
0x140036436  jnb     short loc_140036442
0x140036438  cmp     [rcx+48h], si
0x14003643c  jz      loc_1400364DA
0x140036442  mov     eax, [rbx+74h]
0x140036445  mov     r9d, 106h
0x14003644b  mov     rcx, [rcx+40h]
0x14003644f  mov     dl, 5
0x140036451  mov     dword ptr [rsp+88h+var_50], eax
0x140036455  mov     eax, [rbx+70h]
0x140036458  mov     dword ptr [rsp+88h+var_58], eax
0x14003645c  mov     eax, [rbx+60h]
0x14003645f  mov     dword ptr [rsp+88h+var_60], eax
0x140036463  mov     [rsp+88h+var_68], r12
0x140036468  call    WPP_RECORDER_SF_dDd
0x14003646d  jmp     short loc_1400364DA
0x14003646f  mov     [rbx+85h], sil
0x140036476  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003647d  jz      short loc_1400364DA
0x14003647f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036486  mov     r9d, 107h
0x14003648c  mov     dword ptr [rsp+88h+var_60], eax
0x140036490  mov     r8d, r15d
0x140036493  mov     dl, 2
0x140036495  mov     [rsp+88h+var_68], r12
0x14003649a  mov     rcx, [rcx+40h]
0x14003649e  call    WPP_RECORDER_SF_d
0x1400364a3  jmp     short loc_1400364DA
0x1400364a5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400364ac  jz      short loc_1400364DA
0x1400364ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364b5  cmp     byte ptr [rcx+29h], 5
0x1400364b9  jnb     short loc_1400364C1
0x1400364bb  cmp     [rcx+48h], si
0x1400364bf  jz      short loc_1400364DA
0x1400364c1  mov     r9d, 104h
0x1400364c7  mov     rcx, [rcx+40h]
0x1400364cb  mov     r8d, r15d
0x1400364ce  mov     dl, 5
0x1400364d0  mov     [rsp+88h+var_68], r12
0x1400364d5  call    WPP_RECORDER_SF_
0x1400364da  mov     dl, [rdi+8]; NewIrql
0x1400364dd  mov     rcx, rdi; SpinLock
0x1400364e0  mov     [rdi+10h], sil
0x1400364e4  call    cs:__imp_KeReleaseSpinLock
0x1400364eb  nop     dword ptr [rax+rax+00h]
0x1400364f0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400364f7  jz      short loc_140036529
0x1400364f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140036500  cmp     byte ptr [rcx+29h], 5
0x140036504  jnb     short loc_14003650C
0x140036506  cmp     [rcx+48h], si
0x14003650a  jz      short loc_140036529
0x14003650c  mov     rcx, [rcx+40h]
0x140036510  mov     r9d, 109h
0x140036516  mov     dword ptr [rsp+88h+var_60], esi
0x14003651a  mov     r8d, r15d
0x14003651d  mov     dl, 5
0x14003651f  mov     [rsp+88h+var_68], r12
0x140036524  call    WPP_RECORDER_SF_d
0x140036529  add     rsp, 58h
0x14003652d  pop     r15
0x14003652f  pop     r14
0x140036531  pop     r12
0x140036533  pop     rdi
0x140036534  pop     rsi
0x140036535  pop     rbx
0x140036536  retn
```
