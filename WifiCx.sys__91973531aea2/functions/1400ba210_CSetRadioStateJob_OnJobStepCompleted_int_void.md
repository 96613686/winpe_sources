# CSetRadioStateJob::OnJobStepCompleted(int,void *)

- ea: `0x1400ba210`
- end: `0x1400ba486`
- name: `?OnJobStepCompleted@CSetRadioStateJob@@UEAAXHPEAX@Z`
- size: `630`
- prototype: `void __fastcall(CSetRadioStateJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140012f80`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002073c`
- `0x14009490c`
- `0x1400b9c50`
- `0x1400ba210`
- `0x1400ba804`
- `0x1400ba93c`

## pseudocode

```c
void __fastcall CSetRadioStateJob::OnJobStepCompleted(CSetRadioStateJob *this, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v4; // edi
  __int64 v6; // rdx
  unsigned int StatusFromTaskOutput; // eax
  int v8; // edx
  struct CPort *NextPortToReset; // rax
  int v10; // edx
  int v11; // r8d
  unsigned int started; // eax
  unsigned int v13; // esi
  __int64 v14; // rsi
  int v15; // edx
  int v16; // r8d
  __int64 v17; // rsi
  unsigned int v18; // eax
  __int64 v19; // [rsp+28h] [rbp-50h]
  int v20; // [rsp+80h] [rbp+8h] BYREF

  v4 = a2;
  v20 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      31,
      (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( *((_DWORD *)this + 1087) == 1 )
  {
    NextPortToReset = CSetRadioStateJob::GetNextPortToReset(this);
    if ( NextPortToReset )
    {
      started = CSetRadioStateJob::StartDot11ResetSubJob(this, NextPortToReset);
      v13 = started;
      if ( !started )
      {
        *((_DWORD *)this + 1087) = 1;
        goto LABEL_33;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = started;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          32,
          (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
          v19);
      }
      v6 = v13;
    }
    else
    {
      v14 = *((_QWORD *)this + 67);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v11,
          33,
          (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      CBSSListManager::DeleteAllEntries((CBSSListManager *)(v14 + 1336));
      v17 = *((_QWORD *)this + 67);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v15) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          v16,
          34,
          (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      CBSSListManager::DeleteAllEntries((CBSSListManager *)(v17 + 1736));
      v18 = CSetRadioStateJob::StartSetRadioStateCommand(this);
      if ( !v18 )
      {
        *((_DWORD *)this + 1087) = 2;
        goto LABEL_33;
      }
      v6 = v18;
    }
    goto LABEL_11;
  }
  if ( *((_DWORD *)this + 1087) == 2 )
  {
    if ( v4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          35,
          (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids);
      }
    }
    else
    {
      StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(
                               (CSetRadioStateJob *)((char *)this + 576),
                               (unsigned int *)&v20);
      v4 = StatusFromTaskOutput;
      if ( !StatusFromTaskOutput )
      {
        v6 = 0;
        goto LABEL_11;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = StatusFromTaskOutput;
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          36,
          (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
          v19);
      }
    }
    v6 = v4;
LABEL_11:
    CJobBase::CompleteJob(this, v6, a3, a4);
  }
LABEL_33:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      37,
      (__int64)WPP_82fae3e111d336447358f3c6c484df01_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v4);
  }
}

```

## disassembly

```asm
0x1400ba210  mov     rax, rsp
0x1400ba213  push    rbx
0x1400ba214  push    rbp
0x1400ba215  push    rsi
0x1400ba216  push    rdi
0x1400ba217  push    r12
0x1400ba219  push    r15
0x1400ba21b  sub     rsp, 48h
0x1400ba21f  xor     ebp, ebp
0x1400ba221  mov     edi, edx
0x1400ba223  mov     [rax+8], ebp
0x1400ba226  mov     rbx, rcx
0x1400ba229  lea     r15, WPP_RECORDER_INITIALIZED
0x1400ba230  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba237  lea     r12, WPP_82fae3e111d336447358f3c6c484df01_Traceguids
0x1400ba23e  jz      short loc_1400BA275
0x1400ba240  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba247  cmp     byte ptr [rcx+29h], 5
0x1400ba24b  jnb     short loc_1400BA253
0x1400ba24d  cmp     [rcx+48h], bp
0x1400ba251  jz      short loc_1400BA275
0x1400ba253  mov     eax, [rbx+10h]
0x1400ba256  mov     r9d, 1Fh
0x1400ba25c  mov     rcx, [rcx+40h]
0x1400ba260  mov     dl, 5
0x1400ba262  mov     [rsp+78h+var_48], eax
0x1400ba266  mov     [rsp+78h+var_50], rbx
0x1400ba26b  mov     [rsp+78h+var_58], r12
0x1400ba270  call    WPP_RECORDER_SF_qD
0x1400ba275  mov     ecx, [rbx+10FCh]
0x1400ba27b  sub     ecx, 1
0x1400ba27e  jz      loc_1400BA315
0x1400ba284  cmp     ecx, 1
0x1400ba287  jnz     loc_1400BA436
0x1400ba28d  test    edi, edi
0x1400ba28f  jz      short loc_1400BA2C7
0x1400ba291  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba298  jz      short loc_1400BA2B8
0x1400ba29a  lea     r9d, [rcx+22h]
0x1400ba29e  mov     [rsp+78h+var_58], r12
0x1400ba2a3  mov     r8d, ecx
0x1400ba2a6  mov     dl, 2
0x1400ba2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba2af  mov     rcx, [rcx+40h]
0x1400ba2b3  call    WPP_RECORDER_SF_
0x1400ba2b8  mov     edx, edi; int
0x1400ba2ba  mov     rcx, rbx; this
0x1400ba2bd  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400ba2c2  jmp     loc_1400BA436
0x1400ba2c7  lea     rcx, [rbx+240h]; struct Task *
0x1400ba2ce  lea     rdx, [rsp+78h+arg_0]; int *
0x1400ba2d6  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x1400ba2db  mov     edi, eax
0x1400ba2dd  test    eax, eax
0x1400ba2df  jz      short loc_1400BA311
0x1400ba2e1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba2e8  jz      short loc_1400BA2B8
0x1400ba2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba2f1  mov     r9d, 24h ; '$'
0x1400ba2f7  mov     dword ptr [rsp+78h+var_50], eax
0x1400ba2fb  mov     dl, 2
0x1400ba2fd  mov     [rsp+78h+var_58], r12
0x1400ba302  mov     rcx, [rcx+40h]
0x1400ba306  lea     r8d, [r9-23h]
0x1400ba30a  call    WPP_RECORDER_SF_d
0x1400ba30f  jmp     short loc_1400BA2B8
0x1400ba311  xor     edx, edx
0x1400ba313  jmp     short loc_1400BA2BA
0x1400ba315  mov     rcx, rbx; this
0x1400ba318  call    ?GetNextPortToReset@CSetRadioStateJob@@AEAAPEAVCPort@@XZ; CSetRadioStateJob::GetNextPortToReset(void)
0x1400ba31d  test    rax, rax
0x1400ba320  jz      short loc_1400BA377
0x1400ba322  mov     rdx, rax; struct CPort *
0x1400ba325  mov     rcx, rbx; this
0x1400ba328  call    ?StartDot11ResetSubJob@CSetRadioStateJob@@AEAAHPEAVCPort@@@Z; CSetRadioStateJob::StartDot11ResetSubJob(CPort *)
0x1400ba32d  mov     esi, eax
0x1400ba32f  test    eax, eax
0x1400ba331  jnz     short loc_1400BA342
0x1400ba333  mov     dword ptr [rbx+10FCh], 1
0x1400ba33d  jmp     loc_1400BA436
0x1400ba342  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba349  jz      short loc_1400BA370
0x1400ba34b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba352  mov     r9d, 20h ; ' '
0x1400ba358  mov     dword ptr [rsp+78h+var_50], esi
0x1400ba35c  mov     dl, 2
0x1400ba35e  mov     [rsp+78h+var_58], r12
0x1400ba363  mov     rcx, [rcx+40h]
0x1400ba367  lea     r8d, [r9-1Fh]
0x1400ba36b  call    WPP_RECORDER_SF_d
0x1400ba370  mov     edx, esi
0x1400ba372  jmp     loc_1400BA2BA
0x1400ba377  mov     rsi, [rbx+218h]
0x1400ba37e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba385  jz      short loc_1400BA3BC
0x1400ba387  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba38e  cmp     byte ptr [rcx+29h], 5
0x1400ba392  jnb     short loc_1400BA39A
0x1400ba394  cmp     [rcx+48h], bp
0x1400ba398  jz      short loc_1400BA3BC
0x1400ba39a  mov     eax, [rbx+10h]
0x1400ba39d  mov     r9d, 21h ; '!'
0x1400ba3a3  mov     rcx, [rcx+40h]
0x1400ba3a7  mov     dl, 5
0x1400ba3a9  mov     [rsp+78h+var_48], eax
0x1400ba3ad  mov     [rsp+78h+var_50], rbx
0x1400ba3b2  mov     [rsp+78h+var_58], r12
0x1400ba3b7  call    WPP_RECORDER_SF_qD
0x1400ba3bc  lea     rcx, [rsi+538h]; this
0x1400ba3c3  call    ?DeleteAllEntries@CBSSListManager@@QEAAXXZ; CBSSListManager::DeleteAllEntries(void)
0x1400ba3c8  mov     rsi, [rbx+218h]
0x1400ba3cf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba3d6  jz      short loc_1400BA40D
0x1400ba3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba3df  cmp     byte ptr [rcx+29h], 5
0x1400ba3e3  jnb     short loc_1400BA3EB
0x1400ba3e5  cmp     [rcx+48h], bp
0x1400ba3e9  jz      short loc_1400BA40D
0x1400ba3eb  mov     eax, [rbx+10h]
0x1400ba3ee  mov     r9d, 22h ; '"'
0x1400ba3f4  mov     rcx, [rcx+40h]
0x1400ba3f8  mov     dl, 5
0x1400ba3fa  mov     [rsp+78h+var_48], eax
0x1400ba3fe  mov     [rsp+78h+var_50], rbx
0x1400ba403  mov     [rsp+78h+var_58], r12
0x1400ba408  call    WPP_RECORDER_SF_qD
0x1400ba40d  lea     rcx, [rsi+6C8h]; this
0x1400ba414  call    ?DeleteAllEntries@CBSSListManager@@QEAAXXZ; CBSSListManager::DeleteAllEntries(void)
0x1400ba419  mov     rcx, rbx; this
0x1400ba41c  call    ?StartSetRadioStateCommand@CSetRadioStateJob@@AEAAHXZ; CSetRadioStateJob::StartSetRadioStateCommand(void)
0x1400ba421  test    eax, eax
0x1400ba423  jz      short loc_1400BA42C
0x1400ba425  mov     edx, eax
0x1400ba427  jmp     loc_1400BA2BA
0x1400ba42c  mov     dword ptr [rbx+10FCh], 2
0x1400ba436  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400ba43d  jz      short loc_1400BA478
0x1400ba43f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba446  cmp     byte ptr [rcx+29h], 5
0x1400ba44a  jnb     short loc_1400BA452
0x1400ba44c  cmp     [rcx+48h], bp
0x1400ba450  jz      short loc_1400BA478
0x1400ba452  mov     eax, [rbx+10h]
0x1400ba455  mov     r9d, 25h ; '%'
0x1400ba45b  mov     rcx, [rcx+40h]
0x1400ba45f  mov     dl, 5
0x1400ba461  mov     [rsp+78h+var_40], edi
0x1400ba465  mov     [rsp+78h+var_48], eax
0x1400ba469  mov     [rsp+78h+var_50], rbx
0x1400ba46e  mov     [rsp+78h+var_58], r12
0x1400ba473  call    WPP_RECORDER_SF_qDD
0x1400ba478  add     rsp, 48h
0x1400ba47c  pop     r15
0x1400ba47e  pop     r12
0x1400ba480  pop     rdi
0x1400ba481  pop     rsi
0x1400ba482  pop     rbp
0x1400ba483  pop     rbx
0x1400ba484  retn
```
