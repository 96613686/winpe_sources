# CDeviceCommandOidJobBase::HandleNextDeviceCommand(void)

- ea: `0x1400bad7c`
- end: `0x1400bb057`
- name: `?HandleNextDeviceCommand@CDeviceCommandOidJobBase@@AEAAXXZ`
- size: `731`
- prototype: `void __fastcall(CDeviceCommandOidJobBase *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400bb1b0`
- `0x1400bb200`

## callees

- `0x14000c940`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x1400625a0`
- `0x140063a48`
- `0x14006403c`
- `0x1400bab7c`
- `0x1400bad7c`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CDeviceCommandOidJobBase::HandleNextDeviceCommand(CDeviceCommandOidJobBase *this, __int64 a2, int a3)
{
  __int64 *v4; // rdx
  int v5; // edi
  int v6; // edx
  int v7; // r8d
  unsigned __int8 **v8; // rsi
  _QWORD *v9; // rcx
  int v10; // eax
  int v11; // r9d
  int started; // eax
  int v13; // eax
  int v14; // eax
  int v15; // [rsp+30h] [rbp-58h]
  __int64 v16; // [rsp+38h] [rbp-50h]
  int v17; // [rsp+38h] [rbp-50h]

  v4 = WPP_094209726bdf38b8c0614759c6966a9d_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v4,
      a3,
      12,
      (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v4 = WPP_094209726bdf38b8c0614759c6966a9d_Traceguids;
  }
  if ( *((_BYTE *)this + 576) )
  {
    v5 = -1073676276;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v4,
        a3,
        13,
        (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        -1073676276);
    }
    goto LABEL_8;
  }
  v8 = (unsigned __int8 **)((char *)this + 608);
  v9 = (_QWORD *)*((_QWORD *)this + 76);
  if ( v9 )
  {
    operator delete(v9);
    *v8 = 0;
  }
  v10 = (*(__int64 (__fastcall **)(CDeviceCommandOidJobBase *, __int64, char *, char *, char *, char *, char *))(*(_QWORD *)this + 72LL))(
          this,
          48,
          (char *)this + 584,
          (char *)this + 592,
          (char *)this + 596,
          (char *)this + 600,
          (char *)this + 608);
  v5 = v10;
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_8:
      CDeviceCommandOidJobBase::CompleteJobHelper(this, v5);
      goto LABEL_30;
    }
    v11 = 14;
    v17 = v10;
    v15 = *((_DWORD *)this + 4);
LABEL_14:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      v11,
      (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
      (char)this,
      v15,
      v17);
    goto LABEL_8;
  }
  started = DeviceCommand::Initialize(
              *((DeviceCommand **)this + 136),
              *((_WORD *)this + 26),
              *((_DWORD *)this + 149),
              *((_DWORD *)this + 150),
              *v8);
  v5 = started;
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v11 = 15;
    goto LABEL_18;
  }
  v13 = *((_DWORD *)this + 148);
  if ( v13 == 2 )
  {
    started = Task::Initialize(
                (__int64)this + 616,
                (struct NotificationManager *)(*((_QWORD *)this + 67) + 1072LL),
                (struct DeviceCommandScheduler *)(*((_QWORD *)this + 67) + 1120LL),
                (struct EventQueue *)(*((_QWORD *)this + 67) + 736LL));
    v5 = started;
    if ( started )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_8;
      v11 = 16;
    }
    else
    {
      started = CJobBase::StartTask(this, (CDeviceCommandOidJobBase *)((char *)this + 616), v7);
      v5 = started;
      if ( !started )
        goto LABEL_30;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_8;
      v11 = 17;
    }
LABEL_18:
    v17 = started;
    v15 = *((_DWORD *)this + 4);
    goto LABEL_14;
  }
  if ( v13 == 1 )
  {
    v14 = CJobBase::QueueDeviceCommand(this, *((struct DeviceCommand **)this + 136), v7);
    v5 = v14;
    if ( v14 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_8;
      v17 = v14;
      v11 = 18;
      v15 = *((_DWORD *)this + 4);
      goto LABEL_14;
    }
  }
LABEL_30:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    LODWORD(v16) = v5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      19,
      (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v16);
  }
}

```

## disassembly

```asm
0x1400bad7c  push    rbx
0x1400bad7e  push    rbp
0x1400bad7f  push    rsi
0x1400bad80  push    rdi
0x1400bad81  push    r12
0x1400bad83  push    r13
0x1400bad85  push    r14
0x1400bad87  push    r15
0x1400bad89  sub     rsp, 48h
0x1400bad8d  mov     rbx, rcx
0x1400bad90  lea     r13, WPP_RECORDER_INITIALIZED
0x1400bad97  xor     r12d, r12d
0x1400bad9a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400bada1  lea     rdx, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bada8  jz      short loc_1400BADE7
0x1400badaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400badb1  cmp     byte ptr [rcx+29h], 5
0x1400badb5  jnb     short loc_1400BADBE
0x1400badb7  cmp     [rcx+48h], r12w
0x1400badbc  jz      short loc_1400BADE7
0x1400badbe  mov     eax, [rbx+10h]
0x1400badc1  mov     r9d, 0Ch
0x1400badc7  mov     rcx, [rcx+40h]
0x1400badcb  mov     dword ptr [rsp+88h+var_58], eax
0x1400badcf  mov     [rsp+88h+var_60], rbx
0x1400badd4  mov     [rsp+88h+var_68], rdx
0x1400badd9  mov     dl, 5
0x1400baddb  call    WPP_RECORDER_SF_qD
0x1400bade0  lea     rdx, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bade7  cmp     [rbx+240h], r12b
0x1400badee  jz      short loc_1400BAE45
0x1400badf0  mov     edi, 0C001000Ch
0x1400badf5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400badfc  jz      short loc_1400BAE2F
0x1400badfe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bae05  mov     r9d, 0Dh
0x1400bae0b  mov     eax, [rbx+10h]
0x1400bae0e  mov     dword ptr [rsp+88h+var_50], 0C001000Ch
0x1400bae16  mov     dword ptr [rsp+88h+var_58], eax
0x1400bae1a  mov     rcx, [rcx+40h]
0x1400bae1e  mov     [rsp+88h+var_60], rbx
0x1400bae23  mov     [rsp+88h+var_68], rdx
0x1400bae28  mov     dl, 2
0x1400bae2a  call    WPP_RECORDER_SF_qDD
0x1400bae2f  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bae36  mov     edx, edi; int
0x1400bae38  mov     rcx, rbx; this
0x1400bae3b  call    ?CompleteJobHelper@CDeviceCommandOidJobBase@@AEAAXH@Z; CDeviceCommandOidJobBase::CompleteJobHelper(int)
0x1400bae40  jmp     loc_1400BB002
0x1400bae45  lea     rsi, [rbx+260h]
0x1400bae4c  mov     rcx, [rsi]; void *
0x1400bae4f  test    rcx, rcx
0x1400bae52  jz      short loc_1400BAE5C
0x1400bae54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400bae59  mov     [rsi], r12
0x1400bae5c  mov     rax, [rbx]
0x1400bae5f  lea     r15, [rbx+258h]
0x1400bae66  mov     [rsp+88h+var_58], rsi
0x1400bae6b  lea     r14, [rbx+250h]
0x1400bae72  lea     rbp, [rbx+254h]
0x1400bae79  mov     [rsp+88h+var_60], r15
0x1400bae7e  lea     r8, [rbx+248h]
0x1400bae85  mov     [rsp+88h+var_68], rbp
0x1400bae8a  mov     rax, [rax+48h]
0x1400bae8e  mov     r9, r14
0x1400bae91  mov     edx, 30h ; '0'
0x1400bae96  mov     rcx, rbx
0x1400bae99  call    _guard_dispatch_icall
0x1400bae9e  mov     edi, eax
0x1400baea0  test    eax, eax
0x1400baea2  jz      short loc_1400BAEE6
0x1400baea4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400baeab  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400baeb2  jz      short loc_1400BAE36
0x1400baeb4  mov     ecx, [rbx+10h]
0x1400baeb7  mov     r9d, 0Eh
0x1400baebd  mov     dword ptr [rsp+88h+var_50], eax
0x1400baec1  mov     dword ptr [rsp+88h+var_58], ecx
0x1400baec5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400baecc  mov     dl, 2
0x1400baece  mov     [rsp+88h+var_60], rbx
0x1400baed3  mov     [rsp+88h+var_68], rsi
0x1400baed8  mov     rcx, [rcx+40h]
0x1400baedc  call    WPP_RECORDER_SF_qDD
0x1400baee1  jmp     loc_1400BAE36
0x1400baee6  mov     rax, [rsi]
0x1400baee9  mov     r9d, [r15]; unsigned int
0x1400baeec  mov     r8d, [rbp+0]; unsigned int
0x1400baef0  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x1400baef4  mov     rcx, [rbx+440h]; this
0x1400baefb  mov     [rsp+88h+var_68], rax; unsigned __int8 *
0x1400baf00  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x1400baf05  mov     edi, eax
0x1400baf07  test    eax, eax
0x1400baf09  jz      short loc_1400BAF32
0x1400baf0b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400baf12  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400baf19  jz      loc_1400BAE36
0x1400baf1f  mov     r9d, 0Fh
0x1400baf25  mov     dword ptr [rsp+88h+var_50], eax
0x1400baf29  mov     eax, [rbx+10h]
0x1400baf2c  mov     dword ptr [rsp+88h+var_58], eax
0x1400baf30  jmp     short loc_1400BAEC5
0x1400baf32  mov     eax, [r14]
0x1400baf35  cmp     eax, 2
0x1400baf38  jnz     short loc_1400BAFB7
0x1400baf3a  mov     rdx, [rbx+218h]
0x1400baf41  lea     rsi, [rbx+268h]
0x1400baf48  mov     rcx, rsi; this
0x1400baf4b  lea     r9, [rdx+2E0h]; struct EventQueue *
0x1400baf52  lea     r8, [rdx+460h]; struct DeviceCommandScheduler *
0x1400baf59  add     rdx, 430h; struct NotificationManager *
0x1400baf60  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x1400baf65  mov     edi, eax
0x1400baf67  test    eax, eax
0x1400baf69  jz      short loc_1400BAF87
0x1400baf6b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400baf72  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400baf79  jz      loc_1400BAE36
0x1400baf7f  mov     r9d, 10h
0x1400baf85  jmp     short loc_1400BAF25
0x1400baf87  mov     rdx, rsi; struct Task *
0x1400baf8a  mov     rcx, rbx; this
0x1400baf8d  call    ?StartTask@CJobBase@@IEAAHPEAVTask@@@Z; CJobBase::StartTask(Task *)
0x1400baf92  mov     edi, eax
0x1400baf94  test    eax, eax
0x1400baf96  jz      short loc_1400BAFFB
0x1400baf98  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400baf9f  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bafa6  jz      loc_1400BAE36
0x1400bafac  mov     r9d, 11h
0x1400bafb2  jmp     loc_1400BAF25
0x1400bafb7  cmp     eax, 1
0x1400bafba  jnz     short loc_1400BAFFB
0x1400bafbc  mov     rdx, [rbx+440h]; struct DeviceCommand *
0x1400bafc3  mov     rcx, rbx; this
0x1400bafc6  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x1400bafcb  mov     edi, eax
0x1400bafcd  test    eax, eax
0x1400bafcf  jz      short loc_1400BAFFB
0x1400bafd1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400bafd8  jz      loc_1400BAE2F
0x1400bafde  mov     dword ptr [rsp+88h+var_50], eax
0x1400bafe2  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bafe9  mov     eax, [rbx+10h]
0x1400bafec  mov     r9d, 12h
0x1400baff2  mov     dword ptr [rsp+88h+var_58], eax
0x1400baff6  jmp     loc_1400BAEC5
0x1400baffb  lea     rsi, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bb002  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400bb009  jz      short loc_1400BB045
0x1400bb00b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb012  cmp     byte ptr [rcx+29h], 5
0x1400bb016  jnb     short loc_1400BB01F
0x1400bb018  cmp     [rcx+48h], r12w
0x1400bb01d  jz      short loc_1400BB045
0x1400bb01f  mov     eax, [rbx+10h]
0x1400bb022  mov     r9d, 13h
0x1400bb028  mov     rcx, [rcx+40h]
0x1400bb02c  mov     dl, 5
0x1400bb02e  mov     dword ptr [rsp+88h+var_50], edi
0x1400bb032  mov     dword ptr [rsp+88h+var_58], eax
0x1400bb036  mov     [rsp+88h+var_60], rbx
0x1400bb03b  mov     [rsp+88h+var_68], rsi
0x1400bb040  call    WPP_RECORDER_SF_qDD
0x1400bb045  add     rsp, 48h
0x1400bb049  pop     r15
0x1400bb04b  pop     r14
0x1400bb04d  pop     r13
0x1400bb04f  pop     r12
0x1400bb051  pop     rdi
0x1400bb052  pop     rsi
0x1400bb053  pop     rbp
0x1400bb054  pop     rbx
0x1400bb055  retn
```
