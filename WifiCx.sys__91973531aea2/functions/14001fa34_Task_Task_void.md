# Task::~Task(void)

- ea: `0x14001fa34`
- end: `0x14001fb7f`
- name: `??1Task@@UEAA@XZ`
- size: `331`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `17`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x14002b0b4`
- `0x14004cd7c`
- `0x14005ff68`
- `0x14005ffa8`
- `0x140062380`
- `0x1400687d0`
- `0x1400704a4`
- `0x140070808`
- `0x140070870`
- `0x140070a8c`
- `0x140076adc`
- `0x14007ff6c`
- `0x14007ffd4`
- `0x14008fc90`
- `0x14009c874`
- `0x1400a1178`
- `0x1400a1278`

## callees

- `0x14000c940`
- `0x14000d054`
- `0x14001fa34`
- `0x140060f7c`
- `0x140061544`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb57`

## pseudocode

```c
void __fastcall Task::~Task(Task *this)
{
  unsigned int v1; // edx
  unsigned int v3; // edx
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx

  v1 = *((_DWORD *)this + 66);
  *(_QWORD *)this = &Task::`vftable'{for `IOperationCompletionCallback'};
  *((_QWORD *)this + 1) = &Task::`vftable'{for `IEventQueueCallback'};
  *((_QWORD *)this + 2) = &Task::`vftable'{for `INotifyDeviceIndicationCallback'};
  *((_QWORD *)this + 3) = &Task::`vftable'{for `ITimerCallback'};
  if ( v1 )
  {
    NotificationManager::DeregisterNotificationHandler(*((NotificationManager **)this + 34), v1);
    *((_DWORD *)this + 66) = 0;
  }
  v3 = *((_DWORD *)this + 111);
  if ( v3 )
  {
    EventQueue::DeregisterTimeoutCallback(*((EventQueue **)this + 30), v3);
    *((_DWORD *)this + 111) = 0;
  }
  v4 = (_QWORD *)*((_QWORD *)this + 54);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 54) = 0;
    *((_DWORD *)this + 107) = 0;
  }
  v5 = (_QWORD *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 7) = &CancelDeviceCommand::`vftable';
  if ( v5 )
  {
    if ( g_Feature_56544556_MoveToWDFMemory_IsEnabled )
    {
      if ( (unsigned __int64)v5 < 0x10 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v3) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v3,
            1,
            13,
            (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
        }
      }
      else
      {
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, *(v5 - 1));
      }
    }
    else
    {
      ExFreePoolWithTag(v5, 0x47696457u);
    }
    *((_QWORD *)this + 26) = 0;
    *((_DWORD *)this + 50) = 0;
  }
}

```

## disassembly

```asm
0x14001fa34  push    rbx
0x14001fa36  sub     rsp, 30h
0x14001fa3a  mov     edx, [rcx+108h]; unsigned int
0x14001fa40  lea     rax, ??_7Task@@6BIOperationCompletionCallback@@@; const Task::`vftable'{for `IOperationCompletionCallback'}
0x14001fa47  mov     [rcx], rax
0x14001fa4a  lea     rax, ??_7Task@@6BIEventQueueCallback@@@; const Task::`vftable'{for `IEventQueueCallback'}
0x14001fa51  mov     [rcx+8], rax
0x14001fa55  lea     rax, ??_7Task@@6BINotifyDeviceIndicationCallback@@@; const Task::`vftable'{for `INotifyDeviceIndicationCallback'}
0x14001fa5c  mov     [rcx+10h], rax
0x14001fa60  lea     rax, ??_7Task@@6BITimerCallback@@@; const Task::`vftable'{for `ITimerCallback'}
0x14001fa67  mov     [rcx+18h], rax
0x14001fa6b  mov     rbx, rcx
0x14001fa6e  test    edx, edx
0x14001fa70  jz      short loc_14001FA88
0x14001fa72  mov     rcx, [rcx+110h]; this
0x14001fa79  call    ?DeregisterNotificationHandler@NotificationManager@@QEAAHK@Z; NotificationManager::DeregisterNotificationHandler(ulong)
0x14001fa7e  mov     dword ptr [rbx+108h], 0
0x14001fa88  mov     edx, [rbx+1BCh]; unsigned int
0x14001fa8e  test    edx, edx
0x14001fa90  jz      short loc_14001FAA8
0x14001fa92  mov     rcx, [rbx+0F0h]; this
0x14001fa99  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x14001fa9e  mov     dword ptr [rbx+1BCh], 0
0x14001faa8  mov     rcx, [rbx+1B0h]; void *
0x14001faaf  test    rcx, rcx
0x14001fab2  jz      short loc_14001FACE
0x14001fab4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001fab9  mov     qword ptr [rbx+1B0h], 0
0x14001fac4  mov     dword ptr [rbx+1ACh], 0
0x14001face  mov     rcx, [rbx+0D0h]; P
0x14001fad5  lea     rax, ??_7CancelDeviceCommand@@6B@; const CancelDeviceCommand::`vftable'
0x14001fadc  mov     [rbx+38h], rax
0x14001fae0  test    rcx, rcx
0x14001fae3  jz      loc_14001FB78
0x14001fae9  cmp     cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA, 0; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14001faf0  jz      short loc_14001FB52
0x14001faf2  cmp     rcx, 10h
0x14001faf6  jb      short loc_14001FB18
0x14001faf8  mov     rax, cs:WdfFunctions_01031
0x14001faff  mov     rdx, [rcx-8]
0x14001fb03  mov     rcx, cs:WdfDriverGlobals
0x14001fb0a  mov     rax, [rax+680h]
0x14001fb11  call    _guard_dispatch_icall
0x14001fb16  jmp     short loc_14001FB63
0x14001fb18  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fb1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fb26  jz      short loc_14001FB63
0x14001fb28  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb2f  lea     rax, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x14001fb36  mov     r9d, 0Dh
0x14001fb3c  mov     [rsp+38h+var_18], rax
0x14001fb41  mov     dl, 2
0x14001fb43  mov     rcx, [rcx+40h]
0x14001fb47  lea     r8d, [r9-0Ch]
0x14001fb4b  call    WPP_RECORDER_SF_
0x14001fb50  jmp     short loc_14001FB63
0x14001fb52  mov     edx, 47696457h; Tag
0x14001fb57  call    cs:__imp_ExFreePoolWithTag
0x14001fb5e  nop     dword ptr [rax+rax+00h]
0x14001fb63  mov     qword ptr [rbx+0D0h], 0
0x14001fb6e  mov     dword ptr [rbx+0C8h], 0
0x14001fb78  add     rsp, 30h
0x14001fb7c  pop     rbx
0x14001fb7d  retn
```
