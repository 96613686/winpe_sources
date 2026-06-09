# CANQPQueryJob::OnJobStepCompleted(int,void *)

- ea: `0x14004f700`
- end: `0x14004fef2`
- name: `?OnJobStepCompleted@CANQPQueryJob@@UEAAXHPEAX@Z`
- size: `2034`
- prototype: `void __fastcall(CANQPQueryJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140009420`
- `0x140013390`
- `0x140013510`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140022ab0`
- `0x140024004`
- `0x140040dec`
- `0x14004d3d8`
- `0x14004d960`
- `0x14004dce4`
- `0x14004df30`
- `0x14004f700`
- `0x140050318`
- `0x14005103c`
- `0x1400514c4`
- `0x1400515d4`
- `0x140051708`
- `0x140063a48`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CANQPQueryJob::OnJobStepCompleted(CANQPQueryJob *this, int a2, struct DeviceCommand *a3)
{
  int started; // edi
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // edx
  __int64 v12; // rax
  int v13; // r9d
  int v14; // edx
  DeviceCommand *v15; // rax
  int v16; // edx
  int v17; // r8d
  unsigned int *v18; // rsi
  DeviceCommand *v19; // rcx
  int v20; // eax
  int v21; // r9d
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // edx
  int NextActionFrameDialogTokenFromIhv; // eax
  bool v27; // zf
  struct DeviceCommand *v28; // rcx
  int CommandResult; // eax
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  int v31; // eax
  unsigned int v32; // edx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // r9d
  struct CBSSEntry *CachedBSSEntry; // rax
  int v37; // [rsp+20h] [rbp-50h]
  int v38; // [rsp+20h] [rbp-50h]
  int v39; // [rsp+20h] [rbp-50h]
  enum _WDF_EXECUTION_LEVEL v40; // [rsp+28h] [rbp-48h]
  struct TimerRegistrationContext **v41; // [rsp+38h] [rbp-38h]
  int v42; // [rsp+38h] [rbp-38h]
  unsigned int v43; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 *v44; // [rsp+68h] [rbp-8h] BYREF
  char v45; // [rsp+A8h] [rbp+38h] BYREF
  int v46; // [rsp+B8h] [rbp+48h] BYREF

  v46 = 0;
  started = a2;
  v45 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      101,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  CANQPQueryJob::CheckAndMarkPendingJobs(this, started, a3);
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 102;
      LODWORD(v41) = started;
LABEL_11:
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v7,
        v9,
        (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v41);
      goto LABEL_95;
    }
    goto LABEL_95;
  }
  if ( *((_BYTE *)this + 692) )
  {
    started = -1073676276;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 103;
      LODWORD(v41) = -1073676276;
      goto LABEL_11;
    }
LABEL_95:
    if ( !*((_DWORD *)this + 149) )
      *((_DWORD *)this + 149) = started;
    if ( CANQPQueryJob::CheckAndMarkPendingJobs(this, 0, 0) )
    {
      (*(void (__fastcall **)(CANQPQueryJob *))(*(_QWORD *)this + 24LL))(this);
      goto LABEL_101;
    }
    v11 = *((_DWORD *)this + 149);
LABEL_100:
    CANQPQueryJob::CleanupAndCompleteJob(this, v11);
    goto LABEL_101;
  }
  v7 = *((_DWORD *)this + 167);
  started = 0;
  if ( v7 == 1 )
  {
    LOBYTE(v12) = (_BYTE)this + 112;
    if ( a3 != (CANQPQueryJob *)((char *)this + 2928) )
    {
      LOBYTE(v10) = (_BYTE)this - 72;
      if ( a3 != (CANQPQueryJob *)((char *)this + 696) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v13 = 104;
        LOBYTE(v6) = 2;
LABEL_23:
        WPP_RECORDER_SF_qDqqq(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v7,
          v13,
          v37,
          (char)this,
          *((_DWORD *)this + 4),
          (char)a3,
          v10,
          v12);
        goto LABEL_101;
      }
    }
    CachedBSSEntry = CANQPQueryJob::FindCachedBSSEntry(this);
    if ( !CachedBSSEntry )
    {
      started = -1073676261;
      goto LABEL_95;
    }
    started = CANQPQueryJob::StartANQPQueryTask(this, CachedBSSEntry);
    goto LABEL_92;
  }
  switch ( *((_DWORD *)this + 167) )
  {
    case 2:
      v28 = (struct DeviceCommand *)*((_QWORD *)this + 675);
      v43 = 0;
      v44 = 0;
      if ( a3 != v28 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_qDqq(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v7,
          105,
          v37,
          (char)this,
          *((_DWORD *)this + 4),
          (char)a3,
          (char)v28);
        break;
      }
      started = CMessageHelper::GetStatusFromCommandResult(v28, &v46);
      if ( started || (started = v46) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_95;
        v35 = 106;
        v42 = started;
      }
      else
      {
        CommandResult = DeviceCommand::get_CommandResult(*((DeviceCommand **)this + 675), &v43, &v44);
        started = CommandResult;
        if ( !CommandResult && v43 >= 0x31 )
        {
          NextActionFrameDialogTokenFromIhv = ParseWdiGetNextActionFrameDialogTokenFromIhv(
                                                v43 - 48,
                                                v44 + 48,
                                                *((_QWORD *)this + 67) + 5384LL,
                                                &v45);
          started = NextActionFrameDialogTokenFromIhv;
          if ( NextActionFrameDialogTokenFromIhv )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_95;
            v9 = 108;
          }
          else
          {
            v30 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 675);
            if ( v30 )
              (**v30)(v30, 1);
            *((_BYTE *)this + 5456) = v45;
            *((_QWORD *)this + 675) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                4,
                v7,
                109,
                (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                (char)this,
                *((_DWORD *)this + 4));
            v31 = *((_DWORD *)this + 148);
            v32 = *((_DWORD *)this + 4);
            *((_BYTE *)this + 694) = 1;
            NextActionFrameDialogTokenFromIhv = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                                                  *((EventQueue **)this + 4),
                                                  v32,
                                                  (struct ITimerCallback *)(((unsigned __int64)this + 584)
                                                                          & -(__int64)(this != 0)),
                                                  (v31 & 0x11) != 0 ? 1000 : 2000,
                                                  (char *)this + 664,
                                                  v40,
                                                  0,
                                                  0,
                                                  (unsigned int *)this + 166);
            started = NextActionFrameDialogTokenFromIhv;
            if ( NextActionFrameDialogTokenFromIhv )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_95;
              v9 = 110;
            }
            else
            {
              v33 = *((unsigned __int16 *)this + 324);
              v34 = *((_QWORD *)this + 78) + 30LL;
              *((_DWORD *)this + 167) = 3;
              LOBYTE(v39) = 1;
              NextActionFrameDialogTokenFromIhv = CANQPQueryJob::BuildAndSendANQPRequestActionFrame(
                                                    this,
                                                    10,
                                                    v33,
                                                    v34,
                                                    v39);
              started = NextActionFrameDialogTokenFromIhv;
              if ( !NextActionFrameDialogTokenFromIhv )
                break;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_95;
              v9 = 111;
            }
          }
          goto LABEL_70;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_92:
          if ( started )
            goto LABEL_95;
          break;
        }
        v35 = 107;
        v42 = CommandResult;
      }
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v7,
        v35,
        (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v42);
      goto LABEL_92;
    case 4:
      v23 = *((_QWORD *)this + 690);
      if ( v23 || *((_QWORD *)this + 683) || *((_BYTE *)this + 693) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        WPP_RECORDER_SF_qDqqqD(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v7,
          v8,
          v37,
          (char)this,
          *((_DWORD *)this + 4),
          (char)a3,
          v23,
          *((_QWORD *)this + 683),
          *((_BYTE *)this + 693));
        break;
      }
      v24 = *((_DWORD *)this + 148);
      v25 = *((_DWORD *)this + 4);
      *((_BYTE *)this + 694) = 1;
      NextActionFrameDialogTokenFromIhv = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                                            *((EventQueue **)this + 4),
                                            v25,
                                            (struct ITimerCallback *)(((unsigned __int64)this + 584)
                                                                    & -(__int64)(this != 0)),
                                            (v24 & 0x11) != 0 ? 1000 : 2000,
                                            (char *)this + 664,
                                            v40,
                                            0,
                                            0,
                                            (unsigned int *)this + 166);
      started = NextActionFrameDialogTokenFromIhv;
      if ( NextActionFrameDialogTokenFromIhv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_95;
        v9 = 118;
      }
      else
      {
        v27 = *((_WORD *)this + 345) == 0;
        *((_WORD *)this + 345) = 0;
        *((_DWORD *)this + 167) = 3;
        LOBYTE(v38) = !v27;
        NextActionFrameDialogTokenFromIhv = CANQPQueryJob::BuildAndSendANQPRequestActionFrame(this, 12, 0, 0, v38);
        started = NextActionFrameDialogTokenFromIhv;
        if ( !NextActionFrameDialogTokenFromIhv )
          break;
        *((_DWORD *)this + 163) = 3;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_95;
        v9 = 119;
      }
LABEL_70:
      LODWORD(v41) = NextActionFrameDialogTokenFromIhv;
      goto LABEL_11;
    case 5:
    case 6:
      if ( *((_QWORD *)this + 690) )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        WPP_RECORDER_SF_qDqq(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          v7,
          112,
          v37,
          (char)this,
          *((_DWORD *)this + 4),
          (char)a3,
          *((_QWORD *)this + 690));
        break;
      }
      v14 = 4;
      if ( v7 != 5 )
        v14 = 7;
      *((_DWORD *)this + 167) = v14;
      v15 = (DeviceCommand *)operator new(0xB8u);
      v18 = (unsigned int *)((char *)this + 16);
      if ( v15 )
        v19 = DeviceCommand::DeviceCommand(v15, *v18);
      else
        v19 = 0;
      *((_QWORD *)this + 683) = v19;
      if ( !v19 )
      {
        started = -1073741670;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            v17,
            116,
            (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
            (char)this,
            *v18,
            -1073741670);
        }
LABEL_47:
        v22 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 683);
        if ( !v22 )
          goto LABEL_95;
        (**v22)(v22, 1);
        *((_QWORD *)this + 683) = 0;
        goto LABEL_92;
      }
      v20 = DeviceCommand::Initialize(v19, *((_WORD *)this + 26), 0x7Du, 0x30u, (unsigned __int8 *)this + 5472);
      started = v20;
      if ( v20 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_43;
        v21 = 115;
      }
      else
      {
        v20 = CJobBase::QueueDeviceCommand(this, *((struct DeviceCommand **)this + 683));
        started = v20;
        if ( !v20 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return;
          WPP_RECORDER_SF_qDq(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            v7,
            113,
            (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
            (char)this,
            *v18,
            *((_QWORD *)this + 683));
          break;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_43:
          if ( !started )
            break;
          goto LABEL_47;
        }
        v21 = 114;
      }
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v7,
        v21,
        (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
        (char)this,
        *v18,
        v20);
      goto LABEL_43;
    case 7:
      v10 = *((_QWORD *)this + 690);
      if ( !v10 && !*((_QWORD *)this + 683) )
      {
        v11 = 0;
        goto LABEL_100;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v12 = *((_QWORD *)this + 683);
      v13 = 120;
      v6 = 4;
      goto LABEL_23;
  }
LABEL_101:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    LODWORD(v41) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      121,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v41);
  }
}

```

## disassembly

```asm
0x14004f700  mov     [rsp-28h+arg_0], rbx
0x14004f705  mov     [rsp-28h+arg_10], rsi
0x14004f70a  push    rbp
0x14004f70b  push    rdi
0x14004f70c  push    r12
0x14004f70e  push    r14
0x14004f710  push    r15
0x14004f712  mov     rbp, rsp
0x14004f715  sub     rsp, 70h
0x14004f719  xor     r14d, r14d
0x14004f71c  mov     rsi, r8
0x14004f71f  mov     [rbp+arg_18], r14d
0x14004f723  mov     edi, edx
0x14004f725  mov     [rbp+arg_8], r14b
0x14004f729  mov     rbx, rcx
0x14004f72c  lea     r15, WPP_RECORDER_INITIALIZED
0x14004f733  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f73a  lea     r12, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004f741  jz      short loc_14004F779
0x14004f743  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f74a  cmp     byte ptr [rcx+29h], 5
0x14004f74e  jnb     short loc_14004F757
0x14004f750  cmp     [rcx+48h], r14w
0x14004f755  jz      short loc_14004F779
0x14004f757  mov     eax, [rbx+10h]
0x14004f75a  mov     r9d, 65h ; 'e'
0x14004f760  mov     rcx, [rcx+40h]
0x14004f764  mov     dl, 5
0x14004f766  mov     dword ptr [rsp+70h+var_40], eax
0x14004f76a  mov     qword ptr [rsp+70h+var_48], rbx; enum _WDF_EXECUTION_LEVEL
0x14004f76f  mov     [rsp+70h+var_50], r12
0x14004f774  call    WPP_RECORDER_SF_qD
0x14004f779  mov     r8, rsi; void *
0x14004f77c  mov     edx, edi; int
0x14004f77e  mov     rcx, rbx; this
0x14004f781  call    ?CheckAndMarkPendingJobs@CANQPQueryJob@@AEAAEHPEAX@Z; CANQPQueryJob::CheckAndMarkPendingJobs(int,void *)
0x14004f786  test    edi, edi
0x14004f788  jz      short loc_14004F7A3
0x14004f78a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f791  jz      loc_14004FE56
0x14004f797  mov     r9d, 66h ; 'f'
0x14004f79d  mov     dword ptr [rsp+70h+var_38], edi
0x14004f7a1  jmp     short loc_14004F7CC
0x14004f7a3  cmp     [rbx+2B4h], r14b
0x14004f7aa  jz      short loc_14004F7F4
0x14004f7ac  mov     edi, 0C001000Ch
0x14004f7b1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f7b8  jz      loc_14004FE56
0x14004f7be  mov     r9d, 67h ; 'g'
0x14004f7c4  mov     dword ptr [rsp+70h+var_38], 0C001000Ch
0x14004f7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f7d3  mov     dl, 2
0x14004f7d5  mov     eax, [rbx+10h]
0x14004f7d8  mov     dword ptr [rsp+70h+var_40], eax
0x14004f7dc  mov     qword ptr [rsp+70h+var_48], rbx
0x14004f7e1  mov     rcx, [rcx+40h]
0x14004f7e5  mov     [rsp+70h+var_50], r12
0x14004f7ea  call    WPP_RECORDER_SF_qDD
0x14004f7ef  jmp     loc_14004FE56
0x14004f7f4  mov     r8d, [rbx+29Ch]
0x14004f7fb  mov     edi, r14d
0x14004f7fe  mov     ecx, r8d
0x14004f801  sub     ecx, 1
0x14004f804  jz      loc_14004FDFF
0x14004f80a  sub     ecx, 1
0x14004f80d  jz      loc_14004FBBB
0x14004f813  sub     ecx, 2
0x14004f816  jz      loc_14004FA67
0x14004f81c  sub     ecx, 1
0x14004f81f  jz      short loc_14004F899
0x14004f821  sub     ecx, 1
0x14004f824  jz      short loc_14004F899
0x14004f826  cmp     ecx, 1
0x14004f829  jnz     loc_14004FE95
0x14004f82f  mov     rcx, [rbx+1590h]
0x14004f836  test    rcx, rcx
0x14004f839  jnz     short loc_14004F84B
0x14004f83b  cmp     [rbx+1558h], r14
0x14004f842  jnz     short loc_14004F84B
0x14004f844  xor     edx, edx
0x14004f846  jmp     loc_14004FE8D
0x14004f84b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f852  jz      loc_14004FED8
0x14004f858  mov     rax, [rbx+1558h]
0x14004f85f  mov     r9d, 78h ; 'x'
0x14004f865  lea     edx, [r9-74h]
0x14004f869  mov     [rsp+70h+var_28], rax
0x14004f86e  mov     eax, [rbx+10h]
0x14004f871  mov     [rsp+70h+var_30], rcx
0x14004f876  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f87d  mov     [rsp+70h+var_38], rsi
0x14004f882  mov     dword ptr [rsp+70h+var_40], eax
0x14004f886  mov     qword ptr [rsp+70h+var_48], rbx
0x14004f88b  mov     rcx, [rcx+40h]
0x14004f88f  call    WPP_RECORDER_SF_qDqqq
0x14004f894  jmp     loc_14004FE95
0x14004f899  mov     rax, [rbx+1590h]
0x14004f8a0  test    rax, rax
0x14004f8a3  jz      short loc_14004F8E7
0x14004f8a5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f8ac  jz      loc_14004FED8
0x14004f8b2  mov     r9d, 70h ; 'p'
0x14004f8b8  mov     [rsp+70h+var_30], rax
0x14004f8bd  lea     edx, [r9-6Ch]
0x14004f8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f8c8  mov     eax, [rbx+10h]
0x14004f8cb  mov     [rsp+70h+var_38], rsi
0x14004f8d0  mov     dword ptr [rsp+70h+var_40], eax
0x14004f8d4  mov     rcx, [rcx+40h]
0x14004f8d8  mov     qword ptr [rsp+70h+var_48], rbx
0x14004f8dd  call    WPP_RECORDER_SF_qDqq
0x14004f8e2  jmp     loc_14004FE95
0x14004f8e7  mov     edx, 4
0x14004f8ec  cmp     r8d, 5
0x14004f8f0  mov     ecx, 0B8h; unsigned __int64
0x14004f8f5  lea     eax, [rdx+3]
0x14004f8f8  cmovnz  edx, eax
0x14004f8fb  mov     [rbx+29Ch], edx
0x14004f901  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004f906  lea     rsi, [rbx+10h]
0x14004f90a  test    rax, rax
0x14004f90d  jz      short loc_14004F91E
0x14004f90f  mov     edx, [rsi]; unsigned int
0x14004f911  mov     rcx, rax; this
0x14004f914  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x14004f919  mov     rcx, rax
0x14004f91c  jmp     short loc_14004F921
0x14004f91e  mov     rcx, r14; this
0x14004f921  mov     [rbx+1558h], rcx
0x14004f928  test    rcx, rcx
0x14004f92b  jz      loc_14004F9FD
0x14004f931  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x14004f935  lea     rax, [rbx+1560h]
0x14004f93c  mov     r9d, 30h ; '0'; unsigned int
0x14004f942  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x14004f947  lea     r8d, [r9+4Dh]; unsigned int
0x14004f94b  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x14004f950  mov     edi, eax
0x14004f952  test    eax, eax
0x14004f954  jnz     short loc_14004F9BE
0x14004f956  mov     rdx, [rbx+1558h]; struct DeviceCommand *
0x14004f95d  mov     rcx, rbx; this
0x14004f960  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x14004f965  mov     edi, eax
0x14004f967  test    eax, eax
0x14004f969  jnz     short loc_14004F9AD
0x14004f96b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f972  jz      loc_14004FED8
0x14004f978  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f97f  lea     r9d, [rax+71h]
0x14004f983  mov     rax, [rbx+1558h]
0x14004f98a  mov     [rsp+70h+var_38], rax
0x14004f98f  mov     eax, [rsi]
0x14004f991  mov     rcx, [rcx+40h]
0x14004f995  mov     dword ptr [rsp+70h+var_40], eax
0x14004f999  mov     qword ptr [rsp+70h+var_48], rbx
0x14004f99e  mov     [rsp+70h+var_50], r12
0x14004f9a3  call    WPP_RECORDER_SF_qDq
0x14004f9a8  jmp     loc_14004FE95
0x14004f9ad  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f9b4  jz      short loc_14004F9F3
0x14004f9b6  mov     r9d, 72h ; 'r'
0x14004f9bc  jmp     short loc_14004F9CD
0x14004f9be  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004f9c5  jz      short loc_14004F9F3
0x14004f9c7  mov     r9d, 73h ; 's'
0x14004f9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f9d4  mov     dl, 2
0x14004f9d6  mov     dword ptr [rsp+70h+var_38], eax
0x14004f9da  mov     eax, [rsi]
0x14004f9dc  mov     dword ptr [rsp+70h+var_40], eax
0x14004f9e0  mov     rcx, [rcx+40h]
0x14004f9e4  mov     qword ptr [rsp+70h+var_48], rbx
0x14004f9e9  mov     [rsp+70h+var_50], r12
0x14004f9ee  call    WPP_RECORDER_SF_qDD
0x14004f9f3  test    edi, edi
0x14004f9f5  jz      loc_14004FE95
0x14004f9fb  jmp     short loc_14004FA3B
0x14004f9fd  mov     edi, 0C000009Ah
0x14004fa02  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004fa09  jz      short loc_14004FA3B
0x14004fa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa12  mov     r9d, 74h ; 't'
0x14004fa18  mov     eax, [rsi]
0x14004fa1a  mov     dl, 2
0x14004fa1c  mov     dword ptr [rsp+70h+var_38], 0C000009Ah
0x14004fa24  mov     dword ptr [rsp+70h+var_40], eax
0x14004fa28  mov     rcx, [rcx+40h]
0x14004fa2c  mov     qword ptr [rsp+70h+var_48], rbx
0x14004fa31  mov     [rsp+70h+var_50], r12
0x14004fa36  call    WPP_RECORDER_SF_qDD
0x14004fa3b  mov     rcx, [rbx+1558h]
0x14004fa42  test    rcx, rcx
0x14004fa45  jz      loc_14004FE56
0x14004fa4b  mov     rax, [rcx]
0x14004fa4e  mov     edx, 1
0x14004fa53  mov     rax, [rax]
0x14004fa56  call    _guard_dispatch_icall
0x14004fa5b  mov     [rbx+1558h], r14
0x14004fa62  jmp     loc_14004FE4B
0x14004fa67  mov     rcx, [rbx+1590h]
0x14004fa6e  test    rcx, rcx
0x14004fa71  jnz     loc_14004FB6C
0x14004fa77  cmp     [rbx+1558h], r14
0x14004fa7e  jnz     loc_14004FB6C
0x14004fa84  cmp     [rbx+2B5h], r14b
0x14004fa8b  jnz     loc_14004FB6C
0x14004fa91  mov     eax, [rbx+250h]
0x14004fa97  lea     rdx, [rbx+298h]
0x14004fa9e  mov     [rsp+70h+var_30], rdx; unsigned int *
0x14004faa3  lea     rcx, [rbx+248h]
0x14004faaa  and     al, 11h
0x14004faac  mov     [rsp+70h+var_38], r14; struct TimerRegistrationContext **
0x14004fab1  neg     al
0x14004fab3  mov     [rsp+70h+var_40], r14b; bool
0x14004fab8  mov     [rsp+70h+var_50], rdx; void *
0x14004fabd  mov     rax, rbx
0x14004fac0  mov     edx, [rbx+10h]; unsigned int
0x14004fac3  sbb     r9d, r9d
0x14004fac6  and     r9d, 0FFFFFC18h
0x14004facd  mov     byte ptr [rbx+2B6h], 1
0x14004fad4  add     r9d, 7D0h; unsigned int
0x14004fadb  neg     rax
0x14004fade  sbb     r8, r8
0x14004fae1  and     r8, rcx; struct ITimerCallback *
0x14004fae4  mov     rcx, [rbx+20h]; this
0x14004fae8  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x14004faed  mov     edi, eax
0x14004faef  test    eax, eax
0x14004faf1  jz      short loc_14004FB0B
0x14004faf3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004fafa  jz      loc_14004FE56
0x14004fb00  mov     r9d, 76h ; 'v'
0x14004fb06  jmp     loc_14004FC71
0x14004fb0b  movzx   ecx, word ptr [rbx+2B2h]
0x14004fb12  test    cx, cx
0x14004fb15  mov     [rbx+2B2h], r14w
0x14004fb1d  mov     rcx, rbx
0x14004fb20  mov     dword ptr [rbx+29Ch], 3
0x14004fb2a  setnz   al
0x14004fb2d  xor     r8d, r8d
0x14004fb30  xor     r9d, r9d
0x14004fb33  mov     byte ptr [rsp+70h+var_50], al
0x14004fb37  lea     edx, [r8+0Ch]
0x14004fb3b  call    ?BuildAndSendANQPRequestActionFrame@CANQPQueryJob@@AEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@GPEAEE@Z; CANQPQueryJob::BuildAndSendANQPRequestActionFrame(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,ushort,uchar *,uchar)
0x14004fb40  mov     edi, eax
0x14004fb42  test    eax, eax
0x14004fb44  jz      loc_14004FE95
0x14004fb4a  mov     dword ptr [rbx+28Ch], 3
0x14004fb54  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004fb5b  jz      loc_14004FE56
0x14004fb61  mov     r9d, 77h ; 'w'
0x14004fb67  jmp     loc_14004FC71
0x14004fb6c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004fb73  jz      loc_14004FED8
0x14004fb79  movzx   eax, byte ptr [rbx+2B5h]
0x14004fb80  mov     [rsp+70h+var_20], eax
0x14004fb84  mov     rax, [rbx+1558h]
0x14004fb8b  mov     [rsp+70h+var_28], rax
0x14004fb90  mov     eax, [rbx+10h]
0x14004fb93  mov     [rsp+70h+var_30], rcx
0x14004fb98  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb9f  mov     [rsp+70h+var_38], rsi
0x14004fba4  mov     dword ptr [rsp+70h+var_40], eax
0x14004fba8  mov     qword ptr [rsp+70h+var_48], rbx
0x14004fbad  mov     rcx, [rcx+40h]
0x14004fbb1  call    WPP_RECORDER_SF_qDqqqD
0x14004fbb6  jmp     loc_14004FE95
0x14004fbbb  mov     rcx, [rbx+1518h]; struct DeviceCommand *
0x14004fbc2  mov     [rbp+var_10], r14d
0x14004fbc6  mov     [rbp+var_8], r14
0x14004fbca  cmp     rsi, rcx
0x14004fbcd  jz      short loc_14004FBEE
0x14004fbcf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004fbd6  jz      loc_14004FED8
0x14004fbdc  mov     r9d, 69h ; 'i'
0x14004fbe2  mov     [rsp+70h+var_30], rcx
0x14004fbe7  mov     dl, 2
0x14004fbe9  jmp     loc_14004F8C1
0x14004fbee  lea     rdx, [rbp+arg_18]; int *
0x14004fbf2  call    ?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z; CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)
0x14004fbf7  mov     edi, eax
0x14004fbf9  test    eax, eax
0x14004fbfb  jnz     loc_14004FDC3
0x14004fc01  mov     edi, [rbp+arg_18]
0x14004fc04  test    edi, edi
0x14004fc06  jnz     loc_14004FDC3
0x14004fc0c  mov     rcx, [rbx+1518h]; this
0x14004fc13  lea     r8, [rbp+var_8]; unsigned __int8 **
0x14004fc17  lea     rdx, [rbp+var_10]; unsigned int *
0x14004fc1b  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x14004fc20  mov     edi, eax
0x14004fc22  test    eax, eax
0x14004fc24  jnz     loc_14004FDAA
0x14004fc2a  mov     ecx, [rbp+var_10]
0x14004fc2d  cmp     ecx, 31h ; '1'
0x14004fc30  jb      loc_14004FDAA
0x14004fc36  mov     r8, [rbx+218h]
0x14004fc3d  lea     r9, [rbp+arg_8]
0x14004fc41  mov     rdx, [rbp+var_8]
  ... truncated ...
```
