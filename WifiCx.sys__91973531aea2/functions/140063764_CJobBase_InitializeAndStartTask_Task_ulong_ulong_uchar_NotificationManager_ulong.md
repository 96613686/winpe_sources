# CJobBase::InitializeAndStartTask(Task *,ulong,ulong,uchar *,NotificationManager *,ulong *)

- ea: `0x140063764`
- end: `0x1400638bb`
- name: `?InitializeAndStartTask@CJobBase@@IEAAHPEAVTask@@KKPEAEPEAVNotificationManager@@PEAK@Z`
- size: `343`
- prototype: `int(CJobBase *__hidden this, struct Task *, unsigned int, unsigned int, unsigned __int8 *, struct NotificationManager *, unsigned int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140034a50`
- `0x140034e90`
- `0x140038c74`
- `0x140039164`
- `0x14005e92c`
- `0x140060740`
- `0x1400a0914`

## callees

- `0x14001d4c0`
- `0x14001e2c0`
- `0x1400625a0`
- `0x140062768`
- `0x140063240`
- `0x140063764`
- `0x14006403c`

## pseudocode

```c
__int64 __fastcall CJobBase::InitializeAndStartTask(
        CJobBase *this,
        struct Task *a2,
        int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        struct NotificationManager *a6,
        unsigned int *a7)
{
  unsigned int TaskDeviceCommand; // eax
  int v12; // r8d
  unsigned int v13; // ebx
  _UNKNOWN **v14; // rdx
  int v15; // r9d
  unsigned int started; // eax
  struct EventQueue *v17; // r9
  struct DeviceCommandScheduler *v18; // r8
  unsigned int v19; // eax
  int v21; // [rsp+30h] [rbp-48h]
  int v22; // [rsp+38h] [rbp-40h]
  struct DeviceCommand *v23; // [rsp+40h] [rbp-38h] BYREF

  v23 = 0;
  TaskDeviceCommand = Task::get_TaskDeviceCommand(a2, &v23, a3);
  v13 = TaskDeviceCommand;
  if ( !TaskDeviceCommand )
  {
    started = DeviceCommand::Initialize(v23, *((_WORD *)this + 26), a3, a4, a5);
    v13 = started;
    if ( started )
    {
      v14 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v13;
      v15 = 46;
    }
    else
    {
      v17 = (struct EventQueue *)*((_QWORD *)this + 4);
      v18 = (struct DeviceCommandScheduler *)*((_QWORD *)this + 9);
      if ( a7 )
        v19 = Task::Initialize((enum _WDF_EXECUTION_LEVEL)a2, a6, v18, v17, *a7);
      else
        v19 = Task::Initialize((__int64)a2, a6, v18, v17);
      v13 = v19;
      if ( v19 )
      {
        v14 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v13;
        v15 = 47;
        v22 = v19;
LABEL_17:
        v21 = *((_DWORD *)this + 4);
        goto LABEL_18;
      }
      started = CJobBase::StartTask(this, a2, v12);
      v13 = started;
      if ( !started )
        return v13;
      v14 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v13;
      v15 = 48;
    }
    v22 = started;
    goto LABEL_17;
  }
  v14 = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = 45;
    v22 = TaskDeviceCommand;
    v21 = *((_DWORD *)this + 4);
LABEL_18:
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      v12,
      v15,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      (char)this,
      v21,
      v22);
  }
  return v13;
}

```

## disassembly

```asm
0x140063764  push    rbx
0x140063766  push    rbp
0x140063767  push    rsi
0x140063768  push    rdi
0x140063769  push    r14
0x14006376b  sub     rsp, 50h
0x14006376f  mov     rsi, rdx
0x140063772  mov     [rsp+78h+var_38], 0
0x14006377b  mov     rdi, rcx
0x14006377e  lea     rdx, [rsp+78h+var_38]; struct DeviceCommand **
0x140063783  mov     rcx, rsi; this
0x140063786  mov     ebp, r9d
0x140063789  mov     r14d, r8d
0x14006378c  call    ?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z; Task::get_TaskDeviceCommand(DeviceCommand * *)
0x140063791  mov     ebx, eax
0x140063793  test    eax, eax
0x140063795  jz      short loc_1400637C1
0x140063797  lea     rdx, WPP_RECORDER_INITIALIZED
0x14006379e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400637a5  jz      loc_1400638AD
0x1400637ab  mov     ecx, [rdi+10h]
0x1400637ae  mov     r9d, 2Dh ; '-'
0x1400637b4  mov     [rsp+78h+var_40], eax
0x1400637b8  mov     [rsp+78h+var_48], ecx
0x1400637bc  jmp     loc_14006388A
0x1400637c1  mov     rax, [rsp+78h+arg_20]
0x1400637c9  mov     r9d, ebp; unsigned int
0x1400637cc  movzx   edx, word ptr [rdi+34h]; unsigned __int16
0x1400637d0  mov     r8d, r14d; unsigned int
0x1400637d3  mov     rcx, [rsp+78h+var_38]; this
0x1400637d8  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x1400637dd  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x1400637e2  mov     ebx, eax
0x1400637e4  test    eax, eax
0x1400637e6  jz      short loc_140063804
0x1400637e8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400637ef  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400637f6  jz      loc_1400638AD
0x1400637fc  mov     r9d, 2Eh ; '.'
0x140063802  jmp     short loc_14006387F
0x140063804  mov     rax, [rsp+78h+arg_30]
0x14006380c  mov     rcx, rsi; this
0x14006380f  mov     r9, [rdi+20h]; struct EventQueue *
0x140063813  mov     r8, [rdi+48h]; struct DeviceCommandScheduler *
0x140063817  mov     rdx, [rsp+78h+arg_28]; struct NotificationManager *
0x14006381f  test    rax, rax
0x140063822  jnz     short loc_14006382B
0x140063824  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x140063829  jmp     short loc_140063836
0x14006382b  mov     eax, [rax]
0x14006382d  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x140063831  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@K@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *,ulong)
0x140063836  mov     ebx, eax
0x140063838  test    eax, eax
0x14006383a  jz      short loc_140063858
0x14006383c  lea     rdx, WPP_RECORDER_INITIALIZED
0x140063843  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14006384a  jz      short loc_1400638AD
0x14006384c  mov     r9d, 2Fh ; '/'
0x140063852  mov     [rsp+78h+var_40], eax
0x140063856  jmp     short loc_140063883
0x140063858  mov     rdx, rsi; struct Task *
0x14006385b  mov     rcx, rdi; this
0x14006385e  call    ?StartTask@CJobBase@@IEAAHPEAVTask@@@Z; CJobBase::StartTask(Task *)
0x140063863  mov     ebx, eax
0x140063865  test    eax, eax
0x140063867  jz      short loc_1400638AD
0x140063869  lea     rdx, WPP_RECORDER_INITIALIZED
0x140063870  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140063877  jz      short loc_1400638AD
0x140063879  mov     r9d, 30h ; '0'
0x14006387f  mov     [rsp+78h+var_40], eax
0x140063883  mov     eax, [rdi+10h]
0x140063886  mov     [rsp+78h+var_48], eax
0x14006388a  mov     rcx, cs:WPP_GLOBAL_Control
0x140063891  lea     rax, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x140063898  mov     [rsp+78h+var_50], rdi
0x14006389d  mov     dl, 2
0x14006389f  mov     [rsp+78h+var_58], rax
0x1400638a4  mov     rcx, [rcx+40h]
0x1400638a8  call    WPP_RECORDER_SF_qDD
0x1400638ad  mov     eax, ebx
0x1400638af  add     rsp, 50h
0x1400638b3  pop     r14
0x1400638b5  pop     rdi
0x1400638b6  pop     rsi
0x1400638b7  pop     rbp
0x1400638b8  pop     rbx
0x1400638b9  retn
```
