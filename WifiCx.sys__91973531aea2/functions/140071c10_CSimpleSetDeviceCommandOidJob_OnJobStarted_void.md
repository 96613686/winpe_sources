# CSimpleSetDeviceCommandOidJob::OnJobStarted(void)

- ea: `0x140071c10`
- end: `0x140071f17`
- name: `?OnJobStarted@CSimpleSetDeviceCommandOidJob@@UEAAXXZ`
- size: `775`
- prototype: `void __fastcall(CSimpleSetDeviceCommandOidJob *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14007b850`

## callees

- `0x140012f80`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14001f938`
- `0x1400625a0`
- `0x140063240`
- `0x140063a48`
- `0x14006403c`
- `0x140071c10`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CSimpleSetDeviceCommandOidJob::OnJobStarted(CSimpleSetDeviceCommandOidJob *this, __int16 a2, int a3)
{
  struct DeviceCommand **v4; // r14
  unsigned int TaskDeviceCommand; // eax
  int v6; // edx
  __int64 v7; // r8
  int v8; // r9d
  unsigned int started; // edi
  int v10; // r9d
  unsigned int v11; // eax
  unsigned __int8 *v12; // rax
  unsigned int v13; // r9d
  __int16 v14; // dx
  DeviceCommand *v15; // rcx
  int v16; // [rsp+30h] [rbp-58h]
  __int64 v17; // [rsp+38h] [rbp-50h]
  unsigned int v18; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int8 *v20; // [rsp+A0h] [rbp+18h] BYREF

  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      65,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v4 = (struct DeviceCommand **)((char *)this + 616);
  TaskDeviceCommand = Task::get_TaskDeviceCommand(
                        (CSimpleSetDeviceCommandOidJob *)((char *)this + 624),
                        (struct DeviceCommand **)this + 77);
  started = TaskDeviceCommand;
  if ( TaskDeviceCommand )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 66;
      LODWORD(v17) = TaskDeviceCommand;
      v16 = *((_DWORD *)this + 4);
LABEL_12:
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v7,
        v10,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        v16,
        v17);
    }
LABEL_27:
    CJobBase::CompleteJob(this, started, v7, v8);
    goto LABEL_28;
  }
  v11 = (*(__int64 (__fastcall **)(CSimpleSetDeviceCommandOidJob *, _QWORD, _QWORD, _QWORD, _QWORD, int, unsigned int *, unsigned int *, unsigned __int8 **))(*(_QWORD *)this + 72LL))(
          this,
          *((_QWORD *)this + 73),
          *((unsigned int *)this + 148),
          *((_QWORD *)this + 75),
          *((_QWORD *)this + 76),
          48,
          &v18,
          &v19,
          &v20);
  started = v11;
  if ( v11 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v10 = 67;
LABEL_11:
    LODWORD(v17) = v11;
    v16 = *((_DWORD *)this + 4);
    goto LABEL_12;
  }
  v7 = v18;
  if ( v18 == 2050 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_WORD)v6,
        v18,
        68,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    goto LABEL_27;
  }
  v12 = v20;
  v13 = v19;
  v14 = *((_WORD *)this + 26);
  v15 = *v4;
  *((_QWORD *)this + 137) = v20;
  *((_DWORD *)this + 276) = v13;
  v11 = DeviceCommand::Initialize(v15, v14, v7, v13, v12);
  started = v11;
  if ( v11 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v10 = 69;
    goto LABEL_11;
  }
  if ( *((_BYTE *)this + 596) )
  {
    v11 = Task::Initialize(
            (__int64)this + 624,
            (struct NotificationManager *)(*((_QWORD *)this + 67) + 1072LL),
            (struct DeviceCommandScheduler *)(*((_QWORD *)this + 67) + 1120LL),
            (struct EventQueue *)(*((_QWORD *)this + 67) + 736LL));
    started = v11;
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v10 = 70;
      goto LABEL_11;
    }
    started = CJobBase::StartTask(this, (CSimpleSetDeviceCommandOidJob *)((char *)this + 624), v7);
  }
  else
  {
    v11 = CJobBase::QueueDeviceCommand(this, *v4, v7);
    started = v11;
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v10 = 71;
      goto LABEL_11;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDL(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      72,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v18);
  if ( started )
    goto LABEL_27;
LABEL_28:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    LODWORD(v17) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      73,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v17);
  }
}

```

## disassembly

```asm
0x140071c10  mov     rax, rsp
0x140071c13  push    rbx
0x140071c14  push    rbp
0x140071c15  push    rsi
0x140071c16  push    rdi
0x140071c17  push    r12
0x140071c19  push    r14
0x140071c1b  push    r15
0x140071c1d  sub     rsp, 50h
0x140071c21  xor     ebp, ebp
0x140071c23  mov     rbx, rcx
0x140071c26  mov     [rax+8], ebp
0x140071c29  mov     [rax+10h], ebp
0x140071c2c  mov     [rax+18h], rbp
0x140071c30  lea     r15, WPP_RECORDER_INITIALIZED
0x140071c37  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071c3e  lea     r12, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x140071c45  jz      short loc_140071C7C
0x140071c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c4e  cmp     byte ptr [rcx+29h], 5
0x140071c52  jnb     short loc_140071C5A
0x140071c54  cmp     [rcx+48h], bp
0x140071c58  jz      short loc_140071C7C
0x140071c5a  mov     eax, [rbx+10h]
0x140071c5d  mov     r9d, 41h ; 'A'
0x140071c63  mov     rcx, [rcx+40h]
0x140071c67  mov     dl, 5
0x140071c69  mov     dword ptr [rsp+88h+var_58], eax
0x140071c6d  mov     [rsp+88h+var_60], rbx
0x140071c72  mov     [rsp+88h+var_68], r12
0x140071c77  call    WPP_RECORDER_SF_qD
0x140071c7c  lea     rsi, [rbx+270h]
0x140071c83  lea     r14, [rbx+268h]
0x140071c8a  mov     rcx, rsi; this
0x140071c8d  mov     rdx, r14; struct DeviceCommand **
0x140071c90  call    ?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z; Task::get_TaskDeviceCommand(DeviceCommand * *)
0x140071c95  mov     edi, eax
0x140071c97  test    eax, eax
0x140071c99  jz      short loc_140071CBE
0x140071c9b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071ca2  jz      loc_140071E92
0x140071ca8  mov     ecx, [rbx+10h]
0x140071cab  mov     r9d, 42h ; 'B'
0x140071cb1  mov     dword ptr [rsp+88h+var_50], eax
0x140071cb5  mov     dword ptr [rsp+88h+var_58], ecx
0x140071cb9  jmp     loc_140071D41
0x140071cbe  mov     rax, [rbx]
0x140071cc1  lea     rcx, [rsp+88h+arg_10]
0x140071cc9  mov     r9, [rbx+258h]
0x140071cd0  mov     r8d, [rbx+250h]
0x140071cd7  mov     rdx, [rbx+248h]
0x140071cde  mov     rax, [rax+48h]
0x140071ce2  mov     [rsp+88h+var_48], rcx
0x140071ce7  lea     rcx, [rsp+88h+arg_8]
0x140071cef  mov     [rsp+88h+var_50], rcx
0x140071cf4  lea     rcx, [rsp+88h+arg_0]
0x140071cfc  mov     [rsp+88h+var_58], rcx
0x140071d01  mov     rcx, [rbx+260h]
0x140071d08  mov     dword ptr [rsp+88h+var_60], 30h ; '0'
0x140071d10  mov     [rsp+88h+var_68], rcx
0x140071d15  mov     rcx, rbx
0x140071d18  call    _guard_dispatch_icall
0x140071d1d  mov     edi, eax
0x140071d1f  test    eax, eax
0x140071d21  jz      short loc_140071D62
0x140071d23  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071d2a  jz      loc_140071E92
0x140071d30  mov     r9d, 43h ; 'C'
0x140071d36  mov     dword ptr [rsp+88h+var_50], eax
0x140071d3a  mov     eax, [rbx+10h]
0x140071d3d  mov     dword ptr [rsp+88h+var_58], eax
0x140071d41  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d48  mov     dl, 2
0x140071d4a  mov     [rsp+88h+var_60], rbx
0x140071d4f  mov     [rsp+88h+var_68], r12
0x140071d54  mov     rcx, [rcx+40h]
0x140071d58  call    WPP_RECORDER_SF_qDD
0x140071d5d  jmp     loc_140071E92
0x140071d62  mov     r8d, [rsp+88h+arg_0]; unsigned int
0x140071d6a  cmp     r8d, 802h
0x140071d71  jnz     short loc_140071DAE
0x140071d73  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071d7a  jz      loc_140071E92
0x140071d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d87  mov     r9d, 44h ; 'D'
0x140071d8d  mov     eax, [rbx+10h]
0x140071d90  mov     dl, 4
0x140071d92  mov     dword ptr [rsp+88h+var_58], eax
0x140071d96  mov     [rsp+88h+var_60], rbx
0x140071d9b  mov     rcx, [rcx+40h]
0x140071d9f  mov     [rsp+88h+var_68], r12
0x140071da4  call    WPP_RECORDER_SF_qD
0x140071da9  jmp     loc_140071E92
0x140071dae  mov     rax, [rsp+88h+arg_10]
0x140071db6  mov     r9d, [rsp+88h+arg_8]; unsigned int
0x140071dbe  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x140071dc2  mov     rcx, [r14]; this
0x140071dc5  mov     [rbx+448h], rax
0x140071dcc  mov     [rsp+88h+var_68], rax; unsigned __int8 *
0x140071dd1  mov     [rbx+450h], r9d
0x140071dd8  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x140071ddd  mov     edi, eax
0x140071ddf  test    eax, eax
0x140071de1  jz      short loc_140071DFB
0x140071de3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071dea  jz      loc_140071E92
0x140071df0  mov     r9d, 45h ; 'E'
0x140071df6  jmp     loc_140071D36
0x140071dfb  cmp     [rbx+254h], bpl
0x140071e02  jz      loc_140071EEE
0x140071e08  mov     rdx, [rbx+218h]
0x140071e0f  mov     rcx, rsi; this
0x140071e12  lea     r9, [rdx+2E0h]; struct EventQueue *
0x140071e19  lea     r8, [rdx+460h]; struct DeviceCommandScheduler *
0x140071e20  add     rdx, 430h; struct NotificationManager *
0x140071e27  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x140071e2c  mov     edi, eax
0x140071e2e  test    eax, eax
0x140071e30  jz      short loc_140071E46
0x140071e32  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071e39  jz      short loc_140071E92
0x140071e3b  mov     r9d, 46h ; 'F'
0x140071e41  jmp     loc_140071D36
0x140071e46  mov     rdx, rsi; struct Task *
0x140071e49  mov     rcx, rbx; this
0x140071e4c  call    ?StartTask@CJobBase@@IEAAHPEAVTask@@@Z; CJobBase::StartTask(Task *)
0x140071e51  mov     edi, eax
0x140071e53  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071e5a  jz      short loc_140071E8E
0x140071e5c  mov     eax, [rsp+88h+arg_0]
0x140071e63  mov     r9d, 48h ; 'H'
0x140071e69  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e70  mov     dword ptr [rsp+88h+var_50], eax
0x140071e74  mov     eax, [rbx+10h]
0x140071e77  mov     dword ptr [rsp+88h+var_58], eax
0x140071e7b  mov     rcx, [rcx+40h]
0x140071e7f  mov     [rsp+88h+var_60], rbx
0x140071e84  mov     [rsp+88h+var_68], r12
0x140071e89  call    WPP_RECORDER_SF_qDL
0x140071e8e  test    edi, edi
0x140071e90  jz      short loc_140071E9C
0x140071e92  mov     edx, edi; int
0x140071e94  mov     rcx, rbx; this
0x140071e97  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x140071e9c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071ea3  jz      short loc_140071EDE
0x140071ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140071eac  cmp     byte ptr [rcx+29h], 5
0x140071eb0  jnb     short loc_140071EB8
0x140071eb2  cmp     [rcx+48h], bp
0x140071eb6  jz      short loc_140071EDE
0x140071eb8  mov     eax, [rbx+10h]
0x140071ebb  mov     r9d, 49h ; 'I'
0x140071ec1  mov     rcx, [rcx+40h]
0x140071ec5  mov     dl, 5
0x140071ec7  mov     dword ptr [rsp+88h+var_50], edi
0x140071ecb  mov     dword ptr [rsp+88h+var_58], eax
0x140071ecf  mov     [rsp+88h+var_60], rbx
0x140071ed4  mov     [rsp+88h+var_68], r12
0x140071ed9  call    WPP_RECORDER_SF_qDD
0x140071ede  add     rsp, 50h
0x140071ee2  pop     r15
0x140071ee4  pop     r14
0x140071ee6  pop     r12
0x140071ee8  pop     rdi
0x140071ee9  pop     rsi
0x140071eea  pop     rbp
0x140071eeb  pop     rbx
0x140071eec  retn
0x140071eee  mov     rdx, [r14]; struct DeviceCommand *
0x140071ef1  mov     rcx, rbx; this
0x140071ef4  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x140071ef9  mov     edi, eax
0x140071efb  test    eax, eax
0x140071efd  jz      loc_140071E53
0x140071f03  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140071f0a  jz      short loc_140071E92
0x140071f0c  mov     r9d, 47h ; 'G'
0x140071f12  jmp     loc_140071D36
```
