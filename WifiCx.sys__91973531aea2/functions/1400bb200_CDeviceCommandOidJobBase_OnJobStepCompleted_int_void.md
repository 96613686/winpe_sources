# CDeviceCommandOidJobBase::OnJobStepCompleted(int,void *)

- ea: `0x1400bb200`
- end: `0x1400bb4fb`
- name: `?OnJobStepCompleted@CDeviceCommandOidJobBase@@UEAAXHPEAX@Z`
- size: `763`
- prototype: `void __fastcall(CDeviceCommandOidJobBase *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140013390`
- `0x140013510`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002073c`
- `0x140020860`
- `0x14005113c`
- `0x1400bab7c`
- `0x1400bad7c`
- `0x1400bb200`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CDeviceCommandOidJobBase::OnJobStepCompleted(CDeviceCommandOidJobBase *this, unsigned int a2, void *a3)
{
  unsigned int v3; // esi
  unsigned int v4; // edi
  int v6; // eax
  int CommandResult; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  unsigned int StatusFromCommandResult; // eax
  int v12; // r9d
  struct Task *v13; // rdi
  unsigned int StatusFromTaskOutput; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // r8d
  int v18; // edi
  int v19; // edx
  int v20; // edx
  int v21; // r8d
  int v22; // [rsp+30h] [rbp-30h]
  __int64 v23; // [rsp+38h] [rbp-28h]
  unsigned int v24; // [rsp+38h] [rbp-28h]
  unsigned __int8 *v25[2]; // [rsp+50h] [rbp-10h] BYREF
  int v26; // [rsp+A0h] [rbp+40h] BYREF
  char v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+58h] BYREF

  v28 = 0;
  v3 = -1073741823;
  v26 = -1073741823;
  v4 = a2;
  v25[0] = 0;
  v27 = 0;
  if ( !a2 )
  {
    v6 = *((_DWORD *)this + 148);
    if ( v6 == 1 )
    {
      CommandResult = DeviceCommand::get_CommandResult(*((DeviceCommand **)this + 136), &v28, v25);
      if ( CommandResult )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_22:
          v4 = v3;
          goto LABEL_23;
        }
        v10 = v4 + 20;
LABEL_6:
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          v9,
          v10,
          (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          CommandResult);
        goto LABEL_22;
      }
      StatusFromCommandResult = CMessageHelper::GetStatusFromCommandResult(
                                  *((struct DeviceCommand **)this + 136),
                                  (unsigned int *)&v26);
      v4 = StatusFromCommandResult;
      if ( StatusFromCommandResult )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = 21;
          v24 = StatusFromCommandResult;
          v22 = *((_DWORD *)this + 4);
LABEL_17:
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            (_DWORD)a3,
            v12,
            (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
            (char)this,
            v22,
            v24);
          goto LABEL_18;
        }
        goto LABEL_18;
      }
    }
    else
    {
      if ( v6 != 2 )
      {
LABEL_20:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_qDqD(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            (_DWORD)a3,
            24,
            (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            *((_QWORD *)this + 73),
            v3);
        }
        goto LABEL_22;
      }
      v13 = (CDeviceCommandOidJobBase *)((char *)this + 616);
      CommandResult = Task::get_OutputBuffer((CDeviceCommandOidJobBase *)((char *)this + 616), &v28, v25);
      if ( CommandResult )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_22;
        v10 = 22;
        goto LABEL_6;
      }
      StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(v13, (unsigned int *)&v26);
      v4 = StatusFromTaskOutput;
      if ( StatusFromTaskOutput )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v24 = StatusFromTaskOutput;
          v12 = 23;
          v22 = *((_DWORD *)this + 4);
          goto LABEL_17;
        }
LABEL_18:
        v3 = v26;
        goto LABEL_23;
      }
    }
    v3 = v26;
    if ( !v26 )
      goto LABEL_23;
    goto LABEL_20;
  }
LABEL_23:
  v15 = (*(__int64 (__fastcall **)(CDeviceCommandOidJobBase *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned __int8 *, char *))(*(_QWORD *)this + 80LL))(
          this,
          *((_QWORD *)this + 73),
          v4,
          v3,
          v28,
          v25[0],
          &v27);
  v18 = v15;
  if ( v15 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v23) = v15;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        25,
        (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v23);
    }
    v19 = v18;
LABEL_31:
    CDeviceCommandOidJobBase::CompleteJobHelper(this, v19);
    goto LABEL_35;
  }
  if ( !v27 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        26,
        (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    v19 = 0;
    goto LABEL_31;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      v17,
      27,
      (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  CDeviceCommandOidJobBase::HandleNextDeviceCommand(this, v16, v17);
LABEL_35:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v20) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v23) = v18;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        v21,
        28,
        (__int64)WPP_094209726bdf38b8c0614759c6966a9d_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v23);
    }
  }
}

```

## disassembly

```asm
0x1400bb200  push    rbp
0x1400bb202  push    rbx
0x1400bb203  push    rsi
0x1400bb204  push    rdi
0x1400bb205  push    r12
0x1400bb207  push    r14
0x1400bb209  push    r15
0x1400bb20b  mov     rbp, rsp
0x1400bb20e  sub     rsp, 60h
0x1400bb212  xor     r14d, r14d
0x1400bb215  lea     r15, WPP_RECORDER_INITIALIZED
0x1400bb21c  mov     [rbp+arg_18], r14d
0x1400bb220  mov     esi, 0C0000001h
0x1400bb225  mov     [rbp+arg_0], esi
0x1400bb228  mov     edi, edx
0x1400bb22a  mov     [rbp+var_10], r14
0x1400bb22e  mov     rbx, rcx
0x1400bb231  mov     [rbp+arg_8], r14b
0x1400bb235  lea     r12, WPP_094209726bdf38b8c0614759c6966a9d_Traceguids
0x1400bb23c  test    edx, edx
0x1400bb23e  jnz     loc_1400BB3B6
0x1400bb244  mov     eax, [rcx+250h]
0x1400bb24a  cmp     eax, 1
0x1400bb24d  jnz     loc_1400BB2E2
0x1400bb253  mov     rcx, [rcx+440h]; this
0x1400bb25a  lea     r8, [rbp+var_10]; unsigned __int8 **
0x1400bb25e  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400bb262  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x1400bb267  test    eax, eax
0x1400bb269  jz      short loc_1400BB2A8
0x1400bb26b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb272  jz      loc_1400BB3B4
0x1400bb278  lea     r9d, [rdi+14h]
0x1400bb27c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb283  mov     dl, 2
0x1400bb285  mov     dword ptr [rsp+60h+var_28], eax
0x1400bb289  mov     eax, [rbx+10h]
0x1400bb28c  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb290  mov     rcx, [rcx+40h]
0x1400bb294  mov     [rsp+60h+var_38], rbx
0x1400bb299  mov     [rsp+60h+var_40], r12
0x1400bb29e  call    WPP_RECORDER_SF_qDD
0x1400bb2a3  jmp     loc_1400BB3B4
0x1400bb2a8  mov     rcx, [rbx+440h]; struct DeviceCommand *
0x1400bb2af  lea     rdx, [rbp+arg_0]; int *
0x1400bb2b3  call    ?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z; CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)
0x1400bb2b8  mov     edi, eax
0x1400bb2ba  test    eax, eax
0x1400bb2bc  jz      loc_1400BB36B
0x1400bb2c2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb2c9  jz      loc_1400BB366
0x1400bb2cf  mov     ecx, [rbx+10h]
0x1400bb2d2  mov     r9d, 15h
0x1400bb2d8  mov     dword ptr [rsp+60h+var_28], eax
0x1400bb2dc  mov     dword ptr [rsp+60h+var_30], ecx
0x1400bb2e0  jmp     short loc_1400BB34A
0x1400bb2e2  cmp     eax, 2
0x1400bb2e5  jnz     loc_1400BB372
0x1400bb2eb  lea     rdi, [rcx+268h]
0x1400bb2f2  mov     rcx, rdi; this
0x1400bb2f5  lea     r8, [rbp+var_10]; unsigned __int8 **
0x1400bb2f9  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400bb2fd  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x1400bb302  test    eax, eax
0x1400bb304  jz      short loc_1400BB31E
0x1400bb306  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb30d  jz      loc_1400BB3B4
0x1400bb313  mov     r9d, 16h
0x1400bb319  jmp     loc_1400BB27C
0x1400bb31e  lea     rdx, [rbp+arg_0]; int *
0x1400bb322  mov     rcx, rdi; struct Task *
0x1400bb325  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x1400bb32a  mov     edi, eax
0x1400bb32c  test    eax, eax
0x1400bb32e  jz      short loc_1400BB36B
0x1400bb330  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb337  jz      short loc_1400BB366
0x1400bb339  mov     dword ptr [rsp+60h+var_28], eax
0x1400bb33d  mov     r9d, 17h
0x1400bb343  mov     eax, [rbx+10h]
0x1400bb346  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb34a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb351  mov     dl, 2
0x1400bb353  mov     [rsp+60h+var_38], rbx
0x1400bb358  mov     [rsp+60h+var_40], r12
0x1400bb35d  mov     rcx, [rcx+40h]
0x1400bb361  call    WPP_RECORDER_SF_qDD
0x1400bb366  mov     esi, [rbp+arg_0]
0x1400bb369  jmp     short loc_1400BB3B6
0x1400bb36b  mov     esi, [rbp+arg_0]
0x1400bb36e  test    esi, esi
0x1400bb370  jz      short loc_1400BB3B6
0x1400bb372  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb379  jz      short loc_1400BB3B4
0x1400bb37b  mov     rax, [rbx+248h]
0x1400bb382  mov     r9d, 18h
0x1400bb388  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb38f  mov     dl, 4
0x1400bb391  mov     [rsp+60h+var_20], esi
0x1400bb395  mov     [rsp+60h+var_28], rax
0x1400bb39a  mov     eax, [rbx+10h]
0x1400bb39d  mov     rcx, [rcx+40h]
0x1400bb3a1  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb3a5  mov     [rsp+60h+var_38], rbx
0x1400bb3aa  mov     [rsp+60h+var_40], r12
0x1400bb3af  call    WPP_RECORDER_SF_qDqD
0x1400bb3b4  mov     edi, esi
0x1400bb3b6  mov     rax, [rbx]
0x1400bb3b9  lea     rcx, [rbp+arg_8]
0x1400bb3bd  mov     rdx, [rbx+248h]
0x1400bb3c4  mov     r9d, esi
0x1400bb3c7  mov     [rsp+60h+var_30], rcx
0x1400bb3cc  mov     r8d, edi
0x1400bb3cf  mov     rcx, [rbp+var_10]
0x1400bb3d3  mov     rax, [rax+50h]
0x1400bb3d7  mov     [rsp+60h+var_38], rcx
0x1400bb3dc  mov     ecx, [rbp+arg_18]
0x1400bb3df  mov     dword ptr [rsp+60h+var_40], ecx
0x1400bb3e3  mov     rcx, rbx
0x1400bb3e6  call    _guard_dispatch_icall
0x1400bb3eb  mov     edi, eax
0x1400bb3ed  test    eax, eax
0x1400bb3ef  jz      short loc_1400BB42B
0x1400bb3f1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb3f8  jz      short loc_1400BB427
0x1400bb3fa  mov     ecx, [rbx+10h]
0x1400bb3fd  mov     r9d, 19h
0x1400bb403  mov     dword ptr [rsp+60h+var_28], eax
0x1400bb407  mov     dl, 2
0x1400bb409  mov     dword ptr [rsp+60h+var_30], ecx
0x1400bb40d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb414  mov     [rsp+60h+var_38], rbx
0x1400bb419  mov     [rsp+60h+var_40], r12
0x1400bb41e  mov     rcx, [rcx+40h]
0x1400bb422  call    WPP_RECORDER_SF_qDD
0x1400bb427  mov     edx, edi
0x1400bb429  jmp     short loc_1400BB465
0x1400bb42b  cmp     [rbp+arg_8], r14b
0x1400bb42f  jnz     short loc_1400BB46F
0x1400bb431  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb438  jz      short loc_1400BB463
0x1400bb43a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb441  mov     r9d, 1Ah
0x1400bb447  mov     eax, [rbx+10h]
0x1400bb44a  mov     dl, 4
0x1400bb44c  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb450  mov     [rsp+60h+var_38], rbx
0x1400bb455  mov     rcx, [rcx+40h]
0x1400bb459  mov     [rsp+60h+var_40], r12
0x1400bb45e  call    WPP_RECORDER_SF_qD
0x1400bb463  xor     edx, edx; int
0x1400bb465  mov     rcx, rbx; this
0x1400bb468  call    ?CompleteJobHelper@CDeviceCommandOidJobBase@@AEAAXH@Z; CDeviceCommandOidJobBase::CompleteJobHelper(int)
0x1400bb46d  jmp     short loc_1400BB4A9
0x1400bb46f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb476  jz      short loc_1400BB4A1
0x1400bb478  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb47f  mov     r9d, 1Bh
0x1400bb485  mov     eax, [rbx+10h]
0x1400bb488  mov     dl, 4
0x1400bb48a  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb48e  mov     [rsp+60h+var_38], rbx
0x1400bb493  mov     rcx, [rcx+40h]
0x1400bb497  mov     [rsp+60h+var_40], r12
0x1400bb49c  call    WPP_RECORDER_SF_qD
0x1400bb4a1  mov     rcx, rbx; this
0x1400bb4a4  call    ?HandleNextDeviceCommand@CDeviceCommandOidJobBase@@AEAAXXZ; CDeviceCommandOidJobBase::HandleNextDeviceCommand(void)
0x1400bb4a9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bb4b0  jz      short loc_1400BB4EB
0x1400bb4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb4b9  mov     dl, 5
0x1400bb4bb  cmp     [rcx+29h], dl
0x1400bb4be  jnb     short loc_1400BB4C7
0x1400bb4c0  cmp     [rcx+48h], r14w
0x1400bb4c5  jz      short loc_1400BB4EB
0x1400bb4c7  mov     eax, [rbx+10h]
0x1400bb4ca  mov     r9d, 1Ch
0x1400bb4d0  mov     rcx, [rcx+40h]
0x1400bb4d4  mov     dword ptr [rsp+60h+var_28], edi
0x1400bb4d8  mov     dword ptr [rsp+60h+var_30], eax
0x1400bb4dc  mov     [rsp+60h+var_38], rbx
0x1400bb4e1  mov     [rsp+60h+var_40], r12
0x1400bb4e6  call    WPP_RECORDER_SF_qDD
0x1400bb4eb  add     rsp, 60h
0x1400bb4ef  pop     r15
0x1400bb4f1  pop     r14
0x1400bb4f3  pop     r12
0x1400bb4f5  pop     rdi
0x1400bb4f6  pop     rsi
0x1400bb4f7  pop     rbx
0x1400bb4f8  pop     rbp
0x1400bb4f9  retn
```
