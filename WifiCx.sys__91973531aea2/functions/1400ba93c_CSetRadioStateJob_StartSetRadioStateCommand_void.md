# CSetRadioStateJob::StartSetRadioStateCommand(void)

- ea: `0x1400ba93c`
- end: `0x1400bab73`
- name: `?StartSetRadioStateCommand@CSetRadioStateJob@@AEAAHXZ`
- size: `567`
- prototype: `__int64 __fastcall(CSetRadioStateJob *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400b9ea0`
- `0x1400ba210`

## callees

- `0x140012f80`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140040c54`
- `0x1400625a0`
- `0x140063240`
- `0x14006403c`
- `0x1400ba93c`

## pseudocode

```c
__int64 __fastcall CSetRadioStateJob::StartSetRadioStateCommand(CSetRadioStateJob *this, __int64 a2, int a3)
{
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // r8
  int v7; // r9d
  unsigned int v8; // edi
  int v9; // r9d
  unsigned int TaskDeviceCommand; // eax
  int v11; // r8d
  int v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+38h] [rbp-40h]
  int v15; // [rsp+38h] [rbp-40h]
  char v16; // [rsp+80h] [rbp+8h] BYREF
  struct DeviceCommand *v17; // [rsp+88h] [rbp+10h] BYREF

  v17 = 0;
  v16 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      41,
      (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v4 = Task::Initialize(
         (__int64)this + 576,
         (struct NotificationManager *)(*((_QWORD *)this + 67) + 1072LL),
         (struct DeviceCommandScheduler *)(*((_QWORD *)this + 67) + 1120LL),
         (struct EventQueue *)(*((_QWORD *)this + 67) + 736LL));
  v8 = v4;
  if ( v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 42;
      v15 = v4;
      v13 = *((_DWORD *)this + 4);
LABEL_21:
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v6,
        v9,
        (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
        (char)this,
        v13,
        v15);
    }
LABEL_22:
    CJobBase::CompleteJob(this, v8, v6, v7);
    goto LABEL_23;
  }
  TaskDeviceCommand = Task::get_TaskDeviceCommand((CSetRadioStateJob *)((char *)this + 576), &v17, v6);
  v8 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v9 = 43;
LABEL_20:
    v15 = TaskDeviceCommand;
    v13 = *((_DWORD *)this + 4);
    goto LABEL_21;
  }
  v11 = *((_QWORD *)this + 67) + 5384;
  v16 = *((_BYTE *)this + 4344);
  TaskDeviceCommand = GenerateWdiTaskSetRadioStateToIhv(
                        (unsigned int)&v16,
                        48,
                        v11,
                        (int)this + 4360,
                        (__int64)this + 4352);
  v8 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v9 = 44;
    goto LABEL_20;
  }
  TaskDeviceCommand = DeviceCommand::Initialize(
                        v17,
                        0xFFFF,
                        11,
                        *((_DWORD *)this + 1090),
                        *((unsigned __int8 **)this + 544));
  v8 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v9 = 45;
    goto LABEL_20;
  }
  TaskDeviceCommand = CJobBase::StartTask(this, (CSetRadioStateJob *)((char *)this + 576), v6);
  v8 = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v9 = 46;
    goto LABEL_20;
  }
LABEL_23:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    LODWORD(v14) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      47,
      (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v14);
  }
  return v8;
}

```

## disassembly

```asm
0x1400ba93c  mov     rax, rsp
0x1400ba93f  mov     [rax+18h], rbx
0x1400ba943  push    rbp
0x1400ba944  push    rsi
0x1400ba945  push    rdi
0x1400ba946  push    r12
0x1400ba948  push    r13
0x1400ba94a  push    r14
0x1400ba94c  push    r15
0x1400ba94e  sub     rsp, 40h
0x1400ba952  xor     ebp, ebp
0x1400ba954  mov     rbx, rcx
0x1400ba957  mov     [rax+10h], rbp
0x1400ba95b  mov     [rax+8], bpl
0x1400ba95f  lea     r12, WPP_RECORDER_INITIALIZED
0x1400ba966  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400ba96d  lea     r13, WPP_82fae3e111d336447358f3c6c484df01_Traceguids
0x1400ba974  jz      short loc_1400BA9AB
0x1400ba976  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba97d  cmp     byte ptr [rcx+29h], 5
0x1400ba981  jnb     short loc_1400BA989
0x1400ba983  cmp     [rcx+48h], bp
0x1400ba987  jz      short loc_1400BA9AB
0x1400ba989  mov     eax, [rbx+10h]
0x1400ba98c  mov     r9d, 29h ; ')'
0x1400ba992  mov     rcx, [rcx+40h]
0x1400ba996  mov     dl, 5
0x1400ba998  mov     [rsp+78h+var_48], eax
0x1400ba99c  mov     [rsp+78h+var_50], rbx
0x1400ba9a1  mov     [rsp+78h+var_58], r13
0x1400ba9a6  call    WPP_RECORDER_SF_qD
0x1400ba9ab  mov     rdx, [rbx+218h]
0x1400ba9b2  lea     rsi, [rbx+240h]
0x1400ba9b9  mov     rcx, rsi; this
0x1400ba9bc  lea     r9, [rdx+2E0h]; struct EventQueue *
0x1400ba9c3  lea     r8, [rdx+460h]; struct DeviceCommandScheduler *
0x1400ba9ca  add     rdx, 430h; struct NotificationManager *
0x1400ba9d1  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x1400ba9d6  mov     edi, eax
0x1400ba9d8  test    eax, eax
0x1400ba9da  jz      short loc_1400BA9FF
0x1400ba9dc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400ba9e3  jz      loc_1400BAB0C
0x1400ba9e9  mov     ecx, [rbx+10h]
0x1400ba9ec  mov     r9d, 2Ah ; '*'
0x1400ba9f2  mov     dword ptr [rsp+78h+var_40], eax
0x1400ba9f6  mov     [rsp+78h+var_48], ecx
0x1400ba9fa  jmp     loc_1400BAAF0
0x1400ba9ff  lea     rdx, [rsp+78h+arg_8]; struct DeviceCommand **
0x1400baa07  mov     rcx, rsi; this
0x1400baa0a  call    ?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z; Task::get_TaskDeviceCommand(DeviceCommand * *)
0x1400baa0f  mov     edi, eax
0x1400baa11  test    eax, eax
0x1400baa13  jz      short loc_1400BAA2D
0x1400baa15  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400baa1c  jz      loc_1400BAB0C
0x1400baa22  mov     r9d, 2Bh ; '+'
0x1400baa28  jmp     loc_1400BAAE5
0x1400baa2d  mov     r8, [rbx+218h]
0x1400baa34  lea     r15, [rbx+1108h]
0x1400baa3b  mov     al, [rbx+10F8h]
0x1400baa41  lea     r14, [rbx+1100h]
0x1400baa48  add     r8, 1508h
0x1400baa4f  mov     [rsp+78h+arg_0], al
0x1400baa56  mov     r9, r15
0x1400baa59  mov     [rsp+78h+var_58], r14
0x1400baa5e  mov     edx, 30h ; '0'
0x1400baa63  lea     rcx, [rsp+78h+arg_0]
0x1400baa6b  call    GenerateWdiTaskSetRadioStateToIhv
0x1400baa70  mov     edi, eax
0x1400baa72  test    eax, eax
0x1400baa74  jz      short loc_1400BAA8B
0x1400baa76  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400baa7d  jz      loc_1400BAB0C
0x1400baa83  mov     r9d, 2Ch ; ','
0x1400baa89  jmp     short loc_1400BAAE5
0x1400baa8b  mov     rax, [r14]
0x1400baa8e  mov     edx, 0FFFFh; unsigned __int16
0x1400baa93  mov     r9d, [r15]; unsigned int
0x1400baa96  mov     r8d, 0Bh; unsigned int
0x1400baa9c  mov     rcx, [rsp+78h+arg_8]; this
0x1400baaa4  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x1400baaa9  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x1400baaae  mov     edi, eax
0x1400baab0  test    eax, eax
0x1400baab2  jz      short loc_1400BAAC5
0x1400baab4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400baabb  jz      short loc_1400BAB0C
0x1400baabd  mov     r9d, 2Dh ; '-'
0x1400baac3  jmp     short loc_1400BAAE5
0x1400baac5  mov     rdx, rsi; struct Task *
0x1400baac8  mov     rcx, rbx; this
0x1400baacb  call    ?StartTask@CJobBase@@IEAAHPEAVTask@@@Z; CJobBase::StartTask(Task *)
0x1400baad0  mov     edi, eax
0x1400baad2  test    eax, eax
0x1400baad4  jz      short loc_1400BAB16
0x1400baad6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400baadd  jz      short loc_1400BAB0C
0x1400baadf  mov     r9d, 2Eh ; '.'
0x1400baae5  mov     dword ptr [rsp+78h+var_40], eax
0x1400baae9  mov     eax, [rbx+10h]
0x1400baaec  mov     [rsp+78h+var_48], eax
0x1400baaf0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400baaf7  mov     dl, 2
0x1400baaf9  mov     [rsp+78h+var_50], rbx
0x1400baafe  mov     [rsp+78h+var_58], r13
0x1400bab03  mov     rcx, [rcx+40h]
0x1400bab07  call    WPP_RECORDER_SF_qDD
0x1400bab0c  mov     edx, edi; int
0x1400bab0e  mov     rcx, rbx; this
0x1400bab11  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400bab16  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bab1d  jz      short loc_1400BAB58
0x1400bab1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bab26  cmp     byte ptr [rcx+29h], 5
0x1400bab2a  jnb     short loc_1400BAB32
0x1400bab2c  cmp     [rcx+48h], bp
0x1400bab30  jz      short loc_1400BAB58
0x1400bab32  mov     eax, [rbx+10h]
0x1400bab35  mov     r9d, 2Fh ; '/'
0x1400bab3b  mov     rcx, [rcx+40h]
0x1400bab3f  mov     dl, 5
0x1400bab41  mov     dword ptr [rsp+78h+var_40], edi
0x1400bab45  mov     [rsp+78h+var_48], eax
0x1400bab49  mov     [rsp+78h+var_50], rbx
0x1400bab4e  mov     [rsp+78h+var_58], r13
0x1400bab53  call    WPP_RECORDER_SF_qDD
0x1400bab58  mov     rbx, [rsp+78h+arg_10]
0x1400bab60  mov     eax, edi
0x1400bab62  add     rsp, 40h
0x1400bab66  pop     r15
0x1400bab68  pop     r14
0x1400bab6a  pop     r13
0x1400bab6c  pop     r12
0x1400bab6e  pop     rdi
0x1400bab6f  pop     rsi
0x1400bab70  pop     rbp
0x1400bab71  retn
```
