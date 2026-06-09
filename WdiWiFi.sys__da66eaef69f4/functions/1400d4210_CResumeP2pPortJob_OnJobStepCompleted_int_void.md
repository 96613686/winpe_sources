# CResumeP2pPortJob::OnJobStepCompleted(int,void *)

- ea: `0x1400d4210`
- end: `0x1400d4555`
- name: `?OnJobStepCompleted@CResumeP2pPortJob@@UEAAXHPEAX@Z`
- size: `837`
- prototype: `void __fastcall(CResumeP2pPortJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004a7c`
- `0x140004c3c`
- `0x140010b20`
- `0x140034e04`
- `0x140034ec4`
- `0x1400706f8`
- `0x1400a8fe8`
- `0x1400d36dc`
- `0x1400d398c`
- `0x1400d3ac4`
- `0x1400d4210`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400d4360`
- `ntoskrnl!ExAllocatePool2` at `0x1400d4360`

## pseudocode

```c
void __fastcall CResumeP2pPortJob::OnJobStepCompleted(CResumeP2pPortJob *this, __int64 a2, void *a3)
{
  int started; // ebx
  CResumeP2pPortJob::<unnamed_type_m_ResumeP2pPortStep> m_ResumeP2pPortStep; // ecx
  __int32 v6; // ecx
  CPortPropertyCache *p_m_PortPropertyCache; // rcx
  int v8; // edx
  int v9; // r9d
  CResumeAdvSettingJob *m_pResumeAdvSettingJob; // rcx
  CSetWFDAdvertisementSettings *Pool2; // rax
  int v12; // edx
  CResumeAdvSettingJob *v13; // r14
  int NextAdvertisement; // eax
  CResumeAdvSettingJob *v15; // rdx
  unsigned __int8 *v16; // [rsp+28h] [rbp-18h]
  unsigned __int8 *v17; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+38h] BYREF

  started = 0;
  m_ResumeP2pPortStep = this->m_ResumeP2pPortStep;
  LOBYTE(v18) = 0;
  if ( m_ResumeP2pPortStep == ResumeP2pPortStepInitialized )
  {
    started = CCreateMacOidJob::InitializeForResume(&this->m_CreateMacOidJob, this->m_pPort);
    if ( started )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v9 = 39;
        goto LABEL_35;
      }
      goto LABEL_5;
    }
    this->m_ResumeP2pPortStep = ResumeP2pPortStepAwaitCreateMacCompletion;
    started = CJobBase::StartChildJob(this, &this->m_CreateMacOidJob);
    if ( started )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_5;
      v9 = 40;
      goto LABEL_35;
    }
    goto LABEL_4;
  }
  v6 = m_ResumeP2pPortStep - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      goto LABEL_4;
  }
  else
  {
    p_m_PortPropertyCache = &this->m_pPort->m_PortPropertyCache;
    this->m_ResumeP2pPortStep = ResumeP2pPortStepAwaitAutoPsmCompletion;
    started = CPropertyCache::GetPropertyUchar(p_m_PortPropertyCache, 0x49u, (unsigned __int8 *)&v18);
    if ( !started && (_BYTE)v18 )
    {
      started = CResumeAutoPsmJob::InitializeForResume(
                  &this->m_ResumeAutoPsm,
                  this->m_pAdapter,
                  this->m_pPort->m_NdisPortNumber);
      if ( started )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_5;
        v9 = 41;
      }
      else
      {
        started = CJobBase::StartChildJob(this, &this->m_ResumeAutoPsm);
        if ( !started )
          goto LABEL_4;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_5;
        v9 = 42;
      }
LABEL_35:
      LODWORD(v16) = started;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        v9,
        (__int64)&WPP_7a44bc4aed983e36663f9a3eaccbbc91_Traceguids,
        v16);
      goto LABEL_5;
    }
  }
  m_pResumeAdvSettingJob = this->m_pResumeAdvSettingJob;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  if ( m_pResumeAdvSettingJob )
    ((void (__fastcall *)(CResumeAdvSettingJob *, __int64, void *))m_pResumeAdvSettingJob->~CResumeAdvSettingJob)(
      m_pResumeAdvSettingJob,
      1,
      a3);
  Pool2 = (CSetWFDAdvertisementSettings *)ExAllocatePool2(64, 1544, 1198089303);
  v13 = (CResumeAdvSettingJob *)Pool2;
  if ( !Pool2 )
  {
    this->m_pResumeAdvSettingJob = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        43,
        (__int64)&WPP_7a44bc4aed983e36663f9a3eaccbbc91_Traceguids);
    }
LABEL_30:
    if ( started )
      goto LABEL_5;
    goto LABEL_4;
  }
  CSetWFDAdvertisementSettings::CSetWFDAdvertisementSettings(Pool2, this->m_ActivityId);
  v13->CSetWFDAdvertisementSettings::CSimpleSetDeviceCommandOidJob::COidJobBase::CJobBase::IOperationCompletionCallback::__vftable = (CResumeAdvSettingJob_vtbl *)&CResumeAdvSettingJob::`vftable'{for `IOperationCompletionCallback'};
  v13->CSetWFDAdvertisementSettings::CSimpleSetDeviceCommandOidJob::COidJobBase::CJobBase::IEventQueueCallback::__vftable = (IEventQueueCallback_vtbl *)&CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
  this->m_pResumeAdvSettingJob = v13;
  NextAdvertisement = CResumeP2pPortJob::GetNextAdvertisement(this, &v19, &v18, &v17);
  if ( NextAdvertisement )
  {
    started = 0;
    this->m_ResumeP2pPortStep = ResumeP2pPortStepAwaitSetAdvCompletion;
    if ( NextAdvertisement != -2147483622 )
      started = NextAdvertisement;
    goto LABEL_30;
  }
  started = CResumeAdvSettingJob::InitializeForResume(
              this->m_pResumeAdvSettingJob,
              this->m_pAdapter,
              this->m_NdisPortNumber,
              v19,
              v18,
              v17);
  if ( !started )
  {
    v15 = this->m_pResumeAdvSettingJob;
    this->m_ResumeP2pPortStep = ResumeP2pPortStepAwaitAutoPsmCompletion;
    started = CJobBase::StartChildJob(this, v15);
    if ( started )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v9 = 45;
        goto LABEL_35;
      }
      goto LABEL_5;
    }
LABEL_4:
    if ( this->m_ResumeP2pPortStep != ResumeP2pPortStepAwaitSetAdvCompletion )
      return;
    goto LABEL_5;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v9 = 44;
    goto LABEL_35;
  }
LABEL_5:
  CJobBase::CompleteJob(this, started, (int)a3);
}

```

## disassembly

```asm
0x1400d4210  mov     [rsp-18h+arg_8], rbx
0x1400d4215  mov     [rsp-18h+arg_10], rsi
0x1400d421a  push    rbp
0x1400d421b  push    rdi
0x1400d421c  push    r14
0x1400d421e  mov     rbp, rsp
0x1400d4221  sub     rsp, 40h
0x1400d4225  xor     ebx, ebx
0x1400d4227  mov     rdi, rcx
0x1400d422a  mov     ecx, [rcx+200h]
0x1400d4230  mov     byte ptr [rbp+arg_0], bl
0x1400d4233  test    ecx, ecx
0x1400d4235  jz      loc_1400D44B5
0x1400d423b  sub     ecx, 1
0x1400d423e  jz      short loc_1400D4270
0x1400d4240  cmp     ecx, 1
0x1400d4243  jz      loc_1400D431B
0x1400d4249  cmp     dword ptr [rdi+200h], 3
0x1400d4250  jnz     short loc_1400D425C
0x1400d4252  mov     edx, ebx; int
0x1400d4254  mov     rcx, rdi; this
0x1400d4257  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400d425c  mov     rbx, [rsp+40h+arg_8]
0x1400d4261  mov     rsi, [rsp+40h+arg_10]
0x1400d4266  add     rsp, 40h
0x1400d426a  pop     r14
0x1400d426c  pop     rdi
0x1400d426d  pop     rbp
0x1400d426e  retn
0x1400d4270  mov     rcx, [rdi+230h]
0x1400d4277  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x1400d427b  add     rcx, 3A8h; this
0x1400d4282  mov     dword ptr [rdi+200h], 2
0x1400d428c  mov     edx, 49h ; 'I'; unsigned int
0x1400d4291  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x1400d4296  mov     ebx, eax
0x1400d4298  test    eax, eax
0x1400d429a  jnz     short loc_1400D431B
0x1400d429c  cmp     byte ptr [rbp+arg_0], al
0x1400d429f  jz      short loc_1400D431B
0x1400d42a1  mov     r8, [rdi+230h]
0x1400d42a8  lea     rsi, [rdi+1760h]
0x1400d42af  mov     rdx, [rdi+220h]; struct CAdapter *
0x1400d42b6  mov     rcx, rsi; this
0x1400d42b9  mov     r8d, [r8+60h]; unsigned int
0x1400d42bd  call    ?InitializeForResume@CResumeAutoPsmJob@@QEAAHPEAVCAdapter@@K@Z; CResumeAutoPsmJob::InitializeForResume(CAdapter *,ulong)
0x1400d42c2  mov     ebx, eax
0x1400d42c4  test    eax, eax
0x1400d42c6  jz      short loc_1400D42E7
0x1400d42c8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d42cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d42d6  jz      loc_1400D4252
0x1400d42dc  mov     r9d, 29h ; ')'
0x1400d42e2  jmp     loc_1400D44EB
0x1400d42e7  mov     rdx, rsi; struct CJobBase *
0x1400d42ea  mov     rcx, rdi; this
0x1400d42ed  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400d42f2  mov     ebx, eax
0x1400d42f4  test    eax, eax
0x1400d42f6  jz      loc_1400D4249
0x1400d42fc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d4303  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d430a  jz      loc_1400D4252
0x1400d4310  mov     r9d, 2Ah ; '*'
0x1400d4316  jmp     loc_1400D44EB
0x1400d431b  mov     rcx, [rdi+1DA0h]
0x1400d4322  mov     esi, 1
0x1400d4327  mov     [rbp+arg_0], 0
0x1400d432e  mov     [rbp+var_10], 0
0x1400d4336  mov     [rbp+arg_18], 0
0x1400d433d  test    rcx, rcx
0x1400d4340  jz      short loc_1400D4350
0x1400d4342  mov     rax, [rcx]
0x1400d4345  mov     edx, esi
0x1400d4347  mov     rax, [rax+28h]
0x1400d434b  call    _guard_dispatch_icall
0x1400d4350  mov     edx, 608h
0x1400d4355  mov     ecx, 40h ; '@'
0x1400d435a  mov     r8d, 47696457h
0x1400d4360  call    cs:__imp_ExAllocatePool2
0x1400d4367  nop     dword ptr [rax+rax+00h]
0x1400d436c  mov     r14, rax
0x1400d436f  test    rax, rax
0x1400d4372  jz      loc_1400D4466
0x1400d4378  mov     edx, [rdi+10h]; unsigned int
0x1400d437b  mov     rcx, rax; this
0x1400d437e  call    ??0CSetWFDAdvertisementSettings@@QEAA@K@Z; CSetWFDAdvertisementSettings::CSetWFDAdvertisementSettings(ulong)
0x1400d4383  lea     rax, ??_7CResumeAdvSettingJob@@6BIOperationCompletionCallback@@@; const CResumeAdvSettingJob::`vftable'{for `IOperationCompletionCallback'}
0x1400d438a  mov     rcx, rdi; this
0x1400d438d  mov     [r14], rax
0x1400d4390  lea     r9, [rbp+var_10]; unsigned __int8 **
0x1400d4394  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400d439b  mov     [r14+8], rax
0x1400d439f  lea     r8, [rbp+arg_0]; unsigned int *
0x1400d43a3  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400d43a7  mov     [rdi+1DA0h], r14
0x1400d43ae  call    ?GetNextAdvertisement@CResumeP2pPortJob@@QEAAHPEAK0PEAPEAE@Z; CResumeP2pPortJob::GetNextAdvertisement(ulong *,ulong *,uchar * *)
0x1400d43b3  test    eax, eax
0x1400d43b5  jnz     loc_1400D4450
0x1400d43bb  mov     rax, [rbp+var_10]
0x1400d43bf  mov     r9d, [rbp+arg_18]; unsigned int
0x1400d43c3  mov     r8d, [rdi+228h]; unsigned int
0x1400d43ca  mov     rdx, [rdi+220h]; struct CAdapter *
0x1400d43d1  mov     rcx, [rdi+1DA0h]; this
0x1400d43d8  mov     [rsp+40h+var_18], rax; unsigned __int8 *
0x1400d43dd  mov     eax, [rbp+arg_0]
0x1400d43e0  mov     [rsp+40h+var_20], eax; unsigned int
0x1400d43e4  call    ?InitializeForResume@CResumeAdvSettingJob@@QEAAHPEAVCAdapter@@KKKPEAE@Z; CResumeAdvSettingJob::InitializeForResume(CAdapter *,ulong,ulong,ulong,uchar *)
0x1400d43e9  mov     ebx, eax
0x1400d43eb  test    eax, eax
0x1400d43ed  jz      short loc_1400D4411
0x1400d43ef  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d43f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d43fd  jz      loc_1400D4252
0x1400d4403  mov     r9d, 2Ch ; ','
0x1400d4409  mov     r8d, esi
0x1400d440c  jmp     loc_1400D44F1
0x1400d4411  mov     rdx, [rdi+1DA0h]; struct CJobBase *
0x1400d4418  mov     rcx, rdi; this
0x1400d441b  mov     dword ptr [rdi+200h], 2
0x1400d4425  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400d442a  mov     ebx, eax
0x1400d442c  test    eax, eax
0x1400d442e  jz      loc_1400D4249
0x1400d4434  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d443b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d4442  jz      loc_1400D4252
0x1400d4448  mov     r9d, 2Dh ; '-'
0x1400d444e  jmp     short loc_1400D4409
0x1400d4450  xor     ebx, ebx
0x1400d4452  mov     dword ptr [rdi+200h], 3
0x1400d445c  cmp     eax, 8000001Ah
0x1400d4461  cmovnz  ebx, eax
0x1400d4464  jmp     short loc_1400D44A8
0x1400d4466  mov     qword ptr [rdi+1DA0h], 0
0x1400d4471  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d4478  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d447f  jz      short loc_1400D44A8
0x1400d4481  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4488  lea     rax, WPP_7a44bc4aed983e36663f9a3eaccbbc91_Traceguids
0x1400d448f  mov     r9d, 2Bh ; '+'
0x1400d4495  mov     qword ptr [rsp+40h+var_20], rax
0x1400d449a  mov     r8d, esi
0x1400d449d  mov     dl, 2
0x1400d449f  mov     rcx, [rcx+40h]
0x1400d44a3  call    WPP_RECORDER_SF_
0x1400d44a8  test    ebx, ebx
0x1400d44aa  jnz     loc_1400D4252
0x1400d44b0  jmp     loc_1400D4249
0x1400d44b5  mov     rdx, [rdi+230h]; struct CPort *
0x1400d44bc  lea     r14, [rdi+338h]
0x1400d44c3  mov     rcx, r14; this
0x1400d44c6  call    ?InitializeForResume@CCreateMacOidJob@@QEAAHPEAVCPort@@@Z; CCreateMacOidJob::InitializeForResume(CPort *)
0x1400d44cb  mov     ebx, eax
0x1400d44cd  test    eax, eax
0x1400d44cf  jz      short loc_1400D4518
0x1400d44d1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d44d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d44df  jz      loc_1400D4252
0x1400d44e5  mov     r9d, 27h ; '''
0x1400d44eb  mov     r8d, 1
0x1400d44f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d44f8  lea     rax, WPP_7a44bc4aed983e36663f9a3eaccbbc91_Traceguids
0x1400d44ff  mov     dword ptr [rsp+40h+var_18], ebx
0x1400d4503  mov     dl, 2
0x1400d4505  mov     qword ptr [rsp+40h+var_20], rax
0x1400d450a  mov     rcx, [rcx+40h]
0x1400d450e  call    WPP_RECORDER_SF_D
0x1400d4513  jmp     loc_1400D4252
0x1400d4518  mov     esi, 1
0x1400d451d  mov     rdx, r14; struct CJobBase *
0x1400d4520  mov     rcx, rdi; this
0x1400d4523  mov     [rdi+200h], esi
0x1400d4529  call    ?StartChildJob@CJobBase@@IEAAHPEAV1@@Z; CJobBase::StartChildJob(CJobBase *)
0x1400d452e  mov     ebx, eax
0x1400d4530  test    eax, eax
0x1400d4532  jz      loc_1400D4249
0x1400d4538  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d453f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d4546  jz      loc_1400D4252
0x1400d454c  lea     r9d, [rsi+27h]
0x1400d4550  jmp     loc_1400D4409
```
