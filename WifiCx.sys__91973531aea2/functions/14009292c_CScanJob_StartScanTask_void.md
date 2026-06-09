# CScanJob::StartScanTask(void)

- ea: `0x14009292c`
- end: `0x140092b4f`
- name: `?StartScanTask@CScanJob@@AEAAHXZ`
- size: `547`
- prototype: `__int64 __fastcall(CScanJob *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140091900`

## callees

- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002ed50`
- `0x140040aa4`
- `0x1400625a0`
- `0x140063240`
- `0x14006403c`
- `0x14009292c`

## pseudocode

```c
__int64 __fastcall CScanJob::StartScanTask(CScanJob *this, __int64 a2, int a3)
{
  unsigned int v4; // eax
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // edi
  int v8; // r9d
  unsigned int TaskDeviceCommand; // eax
  int v10; // r8d
  int v12; // [rsp+30h] [rbp-58h]
  __int64 v13; // [rsp+38h] [rbp-50h]
  int v14; // [rsp+38h] [rbp-50h]
  struct DeviceCommand *v15; // [rsp+90h] [rbp+8h] BYREF

  v15 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      22,
      (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v4 = Task::Initialize(
         (__int64)this + 552,
         (struct NotificationManager *)(*((_QWORD *)this + 67) + 1072LL),
         (struct DeviceCommandScheduler *)(*((_QWORD *)this + 67) + 1120LL),
         (struct EventQueue *)(*((_QWORD *)this + 67) + 736LL));
  v7 = v4;
  if ( v4 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v8 = 23;
    v14 = v4;
    v12 = *((_DWORD *)this + 4);
    goto LABEL_21;
  }
  TaskDeviceCommand = Task::get_TaskDeviceCommand((CScanJob *)((char *)this + 552), &v15, v6);
  v7 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v8 = 24;
    goto LABEL_20;
  }
  TaskDeviceCommand = GenerateWdiTaskScanToIhv(
                        (int)this + 1024,
                        48,
                        (unsigned int)*((_QWORD *)this + 67) + 5384,
                        (int)this + 1176,
                        (__int64)this + 1168);
  v7 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v8 = 25;
    goto LABEL_20;
  }
  TaskDeviceCommand = DeviceCommand::Initialize(
                        v15,
                        *((_WORD *)this + 26),
                        4,
                        *((_DWORD *)this + 294),
                        *((unsigned __int8 **)this + 146));
  v7 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v8 = 26;
    goto LABEL_20;
  }
  *((_QWORD *)this + 248) = CSystem::get_CurrentTime();
  TaskDeviceCommand = CJobBase::StartTask(this, (CScanJob *)((char *)this + 552), v10);
  v7 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v8 = 27;
LABEL_20:
    v14 = TaskDeviceCommand;
    v12 = *((_DWORD *)this + 4);
LABEL_21:
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      v8,
      (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
      (char)this,
      v12,
      v14);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    LODWORD(v13) = v7;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      28,
      (__int64)WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v13);
  }
  return v7;
}

```

## disassembly

```asm
0x14009292c  mov     rax, rsp
0x14009292f  push    rbx
0x140092930  push    rbp
0x140092931  push    rsi
0x140092932  push    rdi
0x140092933  push    r12
0x140092935  push    r13
0x140092937  push    r14
0x140092939  push    r15
0x14009293b  sub     rsp, 48h
0x14009293f  xor     r12d, r12d
0x140092942  mov     rbx, rcx
0x140092945  mov     [rax+8], r12
0x140092949  lea     rbp, WPP_RECORDER_INITIALIZED
0x140092950  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092957  lea     r13, WPP_1fe3c85c899130460b7e9228c55753b1_Traceguids
0x14009295e  jz      short loc_140092996
0x140092960  mov     rcx, cs:WPP_GLOBAL_Control
0x140092967  cmp     byte ptr [rcx+29h], 5
0x14009296b  jnb     short loc_140092974
0x14009296d  cmp     [rcx+48h], r12w
0x140092972  jz      short loc_140092996
0x140092974  mov     eax, [rbx+10h]
0x140092977  mov     r9d, 16h
0x14009297d  mov     rcx, [rcx+40h]
0x140092981  mov     dl, 5
0x140092983  mov     [rsp+88h+var_58], eax
0x140092987  mov     [rsp+88h+var_60], rbx
0x14009298c  mov     [rsp+88h+var_68], r13
0x140092991  call    WPP_RECORDER_SF_qD
0x140092996  mov     rdx, [rbx+218h]
0x14009299d  lea     rsi, [rbx+228h]
0x1400929a4  mov     rcx, rsi; this
0x1400929a7  lea     r9, [rdx+2E0h]; struct EventQueue *
0x1400929ae  lea     r8, [rdx+460h]; struct DeviceCommandScheduler *
0x1400929b5  add     rdx, 430h; struct NotificationManager *
0x1400929bc  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x1400929c1  mov     edi, eax
0x1400929c3  test    eax, eax
0x1400929c5  jz      short loc_1400929EA
0x1400929c7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400929ce  jz      loc_140092B3B
0x1400929d4  mov     ecx, [rbx+10h]
0x1400929d7  mov     r9d, 17h
0x1400929dd  mov     dword ptr [rsp+88h+var_50], eax
0x1400929e1  mov     [rsp+88h+var_58], ecx
0x1400929e5  jmp     loc_140092ADC
0x1400929ea  lea     rdx, [rsp+88h+arg_0]; struct DeviceCommand **
0x1400929f2  mov     rcx, rsi; this
0x1400929f5  call    ?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z; Task::get_TaskDeviceCommand(DeviceCommand * *)
0x1400929fa  mov     edi, eax
0x1400929fc  test    eax, eax
0x1400929fe  jz      short loc_140092A18
0x140092a00  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092a07  jz      loc_140092B3B
0x140092a0d  mov     r9d, 18h
0x140092a13  jmp     loc_140092AD1
0x140092a18  mov     r8, [rbx+218h]
0x140092a1f  lea     r15, [rbx+498h]
0x140092a26  lea     r14, [rbx+490h]
0x140092a2d  add     r8, 1508h
0x140092a34  mov     r9, r15
0x140092a37  mov     [rsp+88h+var_68], r14
0x140092a3c  lea     rcx, [rbx+400h]
0x140092a43  mov     edx, 30h ; '0'
0x140092a48  call    GenerateWdiTaskScanToIhv
0x140092a4d  mov     edi, eax
0x140092a4f  test    eax, eax
0x140092a51  jz      short loc_140092A68
0x140092a53  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092a5a  jz      loc_140092B3B
0x140092a60  mov     r9d, 19h
0x140092a66  jmp     short loc_140092AD1
0x140092a68  mov     rax, [r14]
0x140092a6b  mov     r8d, 4; unsigned int
0x140092a71  mov     r9d, [r15]; unsigned int
0x140092a74  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x140092a78  mov     rcx, [rsp+88h+arg_0]; this
0x140092a80  mov     [rsp+88h+var_68], rax; unsigned __int8 *
0x140092a85  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x140092a8a  mov     edi, eax
0x140092a8c  test    eax, eax
0x140092a8e  jz      short loc_140092AA5
0x140092a90  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092a97  jz      loc_140092B3B
0x140092a9d  mov     r9d, 1Ah
0x140092aa3  jmp     short loc_140092AD1
0x140092aa5  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140092aaa  mov     rdx, rsi; struct Task *
0x140092aad  mov     [rbx+7C0h], rax
0x140092ab4  mov     rcx, rbx; this
0x140092ab7  call    ?StartTask@CJobBase@@IEAAHPEAVTask@@@Z; CJobBase::StartTask(Task *)
0x140092abc  mov     edi, eax
0x140092abe  test    eax, eax
0x140092ac0  jz      short loc_140092AF8
0x140092ac2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092ac9  jz      short loc_140092B3B
0x140092acb  mov     r9d, 1Bh
0x140092ad1  mov     dword ptr [rsp+88h+var_50], eax
0x140092ad5  mov     eax, [rbx+10h]
0x140092ad8  mov     [rsp+88h+var_58], eax
0x140092adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140092ae3  mov     dl, 2
0x140092ae5  mov     [rsp+88h+var_60], rbx
0x140092aea  mov     [rsp+88h+var_68], r13
0x140092aef  mov     rcx, [rcx+40h]
0x140092af3  call    WPP_RECORDER_SF_qDD
0x140092af8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140092aff  jz      short loc_140092B3B
0x140092b01  mov     rcx, cs:WPP_GLOBAL_Control
0x140092b08  cmp     byte ptr [rcx+29h], 5
0x140092b0c  jnb     short loc_140092B15
0x140092b0e  cmp     [rcx+48h], r12w
0x140092b13  jz      short loc_140092B3B
0x140092b15  mov     eax, [rbx+10h]
0x140092b18  mov     r9d, 1Ch
0x140092b1e  mov     rcx, [rcx+40h]
0x140092b22  mov     dl, 5
0x140092b24  mov     dword ptr [rsp+88h+var_50], edi
0x140092b28  mov     [rsp+88h+var_58], eax
0x140092b2c  mov     [rsp+88h+var_60], rbx
0x140092b31  mov     [rsp+88h+var_68], r13
0x140092b36  call    WPP_RECORDER_SF_qDD
0x140092b3b  mov     eax, edi
0x140092b3d  add     rsp, 48h
0x140092b41  pop     r15
0x140092b43  pop     r14
0x140092b45  pop     r13
0x140092b47  pop     r12
0x140092b49  pop     rdi
0x140092b4a  pop     rsi
0x140092b4b  pop     rbp
0x140092b4c  pop     rbx
0x140092b4d  retn
```
