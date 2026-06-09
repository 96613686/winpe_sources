# CServicesManager::StartDeviceExpiryNotificationTimer_WDFLocks(void)

- ea: `0x140036540`
- end: `0x1400367d1`
- name: `?StartDeviceExpiryNotificationTimer_WDFLocks@CServicesManager@@QEAAXXZ`
- size: `657`
- prototype: `void __fastcall(CServicesManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140036284`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14001a1e0`
- `0x14002007c`
- `0x14002293c`
- `0x140024004`
- `0x140036540`
- `0x140050574`
- `0x140061544`

## pseudocode

```c
void __fastcall CServicesManager::StartDeviceExpiryNotificationTimer_WDFLocks(CServicesManager *this)
{
  PDEVICE_OBJECT v2; // rcx
  int v3; // r9d
  bool v4; // zf
  unsigned int NextActivityId; // eax
  __int64 v6; // r10
  unsigned int v7; // r9d
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // [rsp+28h] [rbp-40h]
  char v12; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      252,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
  }
  if ( *((_BYTE *)this + 52) )
  {
    wil::details::unique_wdf_spin_lock_storage::acquire((char *)this + 144, &v12);
    if ( *((_BYTE *)this + 132) || *((_BYTE *)this + 133) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v2 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_36;
      v3 = 253;
      goto LABEL_35;
    }
    if ( *((_BYTE *)this + 54) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v2 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_36;
      v3 = 254;
LABEL_35:
      WPP_RECORDER_SF_(v2->DeviceExtension, 5, 1, v3, (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
LABEL_36:
      wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v12);
      goto LABEL_37;
    }
    if ( *((_BYTE *)this + 53) )
    {
      v4 = *((_DWORD *)this + 24) == 0;
    }
    else
    {
      if ( *((_DWORD *)this + 28) )
        goto LABEL_24;
      v4 = *((_DWORD *)this + 29) == 0;
    }
    if ( v4 )
    {
      if ( *((_DWORD *)this + 31) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            1,
            257,
            (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
        }
        EventQueue::DeregisterTimeoutCallback((EventQueue *)(*((_QWORD *)this + 1) + 736LL), *((_DWORD *)this + 31));
        *((_DWORD *)this + 31) = 0;
      }
      goto LABEL_36;
    }
LABEL_24:
    *((_BYTE *)this + 133) = 1;
    NextActivityId = IActivityId::get_NextActivityId();
    v8 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
           (EventQueue *)(v6 + 736),
           NextActivityId,
           this,
           v7,
           (char *)this + 124,
           (enum _WDF_EXECUTION_LEVEL)v11,
           0,
           0,
           (unsigned int *)this + 31);
    if ( v8 )
    {
      *((_BYTE *)this + 133) = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v11) = v8;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          256,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v11);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
           && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        255,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        *((_DWORD *)this + 24),
        *((_DWORD *)this + 28),
        *((_DWORD *)this + 29));
    }
    goto LABEL_36;
  }
LABEL_37:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v11) = 0;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      258,
      (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
      v11);
  }
}

```

## disassembly

```asm
0x140036540  mov     [rsp+arg_8], rbx
0x140036545  mov     [rsp+arg_10], rbp
0x14003654a  push    rdi
0x14003654b  push    r14
0x14003654d  push    r15
0x14003654f  sub     rsp, 50h
0x140036553  mov     rbx, rcx
0x140036556  xor     edi, edi
0x140036558  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003655f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140036566  lea     r14, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14003656d  lea     r15d, [rdi+1]
0x140036571  jz      short loc_14003659F
0x140036573  mov     rcx, cs:WPP_GLOBAL_Control
0x14003657a  cmp     byte ptr [rcx+29h], 5
0x14003657e  jnb     short loc_140036586
0x140036580  cmp     [rcx+48h], di
0x140036584  jz      short loc_14003659F
0x140036586  mov     rcx, [rcx+40h]
0x14003658a  mov     r9d, 0FCh
0x140036590  mov     r8d, r15d
0x140036593  mov     [rsp+68h+var_48], r14
0x140036598  mov     dl, 5
0x14003659a  call    WPP_RECORDER_SF_
0x14003659f  cmp     [rbx+34h], dil
0x1400365a3  jz      loc_140036781
0x1400365a9  lea     rcx, [rbx+90h]
0x1400365b0  lea     rdx, [rsp+68h+arg_0]
0x1400365b5  call    ?acquire@unique_wdf_spin_lock_storage@details@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@XZ; wil::details::unique_wdf_spin_lock_storage::acquire(void)
0x1400365ba  cmp     [rbx+84h], dil
0x1400365c1  jnz     loc_140036742
0x1400365c7  cmp     [rbx+85h], dil
0x1400365ce  jnz     loc_140036742
0x1400365d4  cmp     [rbx+36h], dil
0x1400365d8  jz      short loc_140036609
0x1400365da  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400365e1  jz      loc_140036777
0x1400365e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400365ee  cmp     byte ptr [rcx+29h], 5
0x1400365f2  jnb     short loc_1400365FE
0x1400365f4  cmp     [rcx+48h], di
0x1400365f8  jz      loc_140036777
0x1400365fe  mov     r9d, 0FEh
0x140036604  jmp     loc_140036764
0x140036609  cmp     [rbx+35h], dil
0x14003660d  jz      short loc_140036614
0x14003660f  cmp     [rbx+60h], edi
0x140036612  jmp     short loc_14003661C
0x140036614  cmp     [rbx+70h], edi
0x140036617  jnz     short loc_140036677
0x140036619  cmp     [rbx+74h], edi
0x14003661c  jnz     short loc_140036677
0x14003661e  cmp     [rbx+7Ch], edi
0x140036621  jz      loc_140036777
0x140036627  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003662e  jz      short loc_14003665C
0x140036630  mov     rcx, cs:WPP_GLOBAL_Control
0x140036637  cmp     byte ptr [rcx+29h], 5
0x14003663b  jnb     short loc_140036643
0x14003663d  cmp     [rcx+48h], di
0x140036641  jz      short loc_14003665C
0x140036643  mov     rcx, [rcx+40h]
0x140036647  mov     r9d, 101h
0x14003664d  mov     r8d, r15d
0x140036650  mov     [rsp+68h+var_48], r14
0x140036655  mov     dl, 5
0x140036657  call    WPP_RECORDER_SF_
0x14003665c  mov     rcx, [rbx+8]
0x140036660  mov     edx, [rbx+7Ch]; unsigned int
0x140036663  add     rcx, 2E0h; this
0x14003666a  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x14003666f  mov     [rbx+7Ch], edi
0x140036672  jmp     loc_140036777
0x140036677  mov     r10, [rbx+8]
0x14003667b  mov     r9d, [rbx+0A0h]
0x140036682  mov     [rbx+85h], r15b
0x140036689  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14003668e  lea     rdx, [rbx+7Ch]
0x140036692  mov     r8, rbx; struct ITimerCallback *
0x140036695  mov     [rsp+68h+var_28], rdx; unsigned int *
0x14003669a  lea     rcx, [r10+2E0h]; this
0x1400366a1  mov     [rsp+68h+var_30], rdi; struct TimerRegistrationContext **
0x1400366a6  mov     [rsp+68h+var_38], dil; bool
0x1400366ab  mov     [rsp+68h+var_48], rdx; void *
0x1400366b0  mov     edx, eax; unsigned int
0x1400366b2  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x1400366b7  test    eax, eax
0x1400366b9  jnz     short loc_14003670C
0x1400366bb  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400366c2  jz      loc_140036777
0x1400366c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366cf  cmp     byte ptr [rcx+29h], 5
0x1400366d3  jnb     short loc_1400366DF
0x1400366d5  cmp     [rcx+48h], di
0x1400366d9  jz      loc_140036777
0x1400366df  mov     eax, [rbx+74h]
0x1400366e2  mov     r9d, 0FFh
0x1400366e8  mov     rcx, [rcx+40h]
0x1400366ec  mov     dl, 5
0x1400366ee  mov     dword ptr [rsp+68h+var_30], eax
0x1400366f2  mov     eax, [rbx+70h]
0x1400366f5  mov     dword ptr [rsp+68h+var_38], eax
0x1400366f9  mov     eax, [rbx+60h]
0x1400366fc  mov     dword ptr [rsp+68h+var_40], eax
0x140036700  mov     [rsp+68h+var_48], r14
0x140036705  call    WPP_RECORDER_SF_dDd
0x14003670a  jmp     short loc_140036777
0x14003670c  mov     [rbx+85h], dil
0x140036713  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003671a  jz      short loc_140036777
0x14003671c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036723  mov     r9d, 100h
0x140036729  mov     dword ptr [rsp+68h+var_40], eax
0x14003672d  mov     r8d, r15d
0x140036730  mov     dl, 2
0x140036732  mov     [rsp+68h+var_48], r14
0x140036737  mov     rcx, [rcx+40h]
0x14003673b  call    WPP_RECORDER_SF_d
0x140036740  jmp     short loc_140036777
0x140036742  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140036749  jz      short loc_140036777
0x14003674b  mov     rcx, cs:WPP_GLOBAL_Control
0x140036752  cmp     byte ptr [rcx+29h], 5
0x140036756  jnb     short loc_14003675E
0x140036758  cmp     [rcx+48h], di
0x14003675c  jz      short loc_140036777
0x14003675e  mov     r9d, 0FDh
0x140036764  mov     rcx, [rcx+40h]
0x140036768  mov     r8d, r15d
0x14003676b  mov     dl, 5
0x14003676d  mov     [rsp+68h+var_48], r14
0x140036772  call    WPP_RECORDER_SF_
0x140036777  lea     rcx, [rsp+68h+arg_0]
0x14003677c  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x140036781  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140036788  jz      short loc_1400367BA
0x14003678a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036791  cmp     byte ptr [rcx+29h], 5
0x140036795  jnb     short loc_14003679D
0x140036797  cmp     [rcx+48h], di
0x14003679b  jz      short loc_1400367BA
0x14003679d  mov     rcx, [rcx+40h]
0x1400367a1  mov     r9d, 102h
0x1400367a7  mov     dword ptr [rsp+68h+var_40], edi
0x1400367ab  mov     r8d, r15d
0x1400367ae  mov     dl, 5
0x1400367b0  mov     [rsp+68h+var_48], r14
0x1400367b5  call    WPP_RECORDER_SF_d
0x1400367ba  lea     r11, [rsp+68h+var_18]
0x1400367bf  mov     rbx, [r11+28h]
0x1400367c3  mov     rbp, [r11+30h]
0x1400367c7  mov     rsp, r11
0x1400367ca  pop     r15
0x1400367cc  pop     r14
0x1400367ce  pop     rdi
0x1400367cf  retn
```
