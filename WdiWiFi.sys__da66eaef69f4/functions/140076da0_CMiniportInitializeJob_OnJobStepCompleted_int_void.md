# CMiniportInitializeJob::OnJobStepCompleted(int,void *)

- ea: `0x140076da0`
- end: `0x14007722a`
- name: `?OnJobStepCompleted@CMiniportInitializeJob@@UEAAXHPEAX@Z`
- size: `1162`
- prototype: `void __fastcall(CMiniportInitializeJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400101c8`
- `0x140010b20`
- `0x1400122e0`
- `0x1400297a0`
- `0x14002aa28`
- `0x140034e04`
- `0x140055f90`
- `0x140076da0`
- `0x140077230`
- `0x14008445c`
- `0x1400a1f3c`
- `0x1400a38f8`
- `0x1400a899c`
- `0x1400a89f8`
- `0x1400a8af4`
- `0x1400a8c94`
- `0x1400a9da0`
- `0x1400a9efc`
- `0x1400aa060`
- `0x1400aa42c`
- `0x1400da680`

## pseudocode

```c
void __fastcall CMiniportInitializeJob::OnJobStepCompleted(CMiniportInitializeJob *this, unsigned int a2, void *a3)
{
  _MINIPORT_INITIALIZE_JOB_STATE m_JobState; // esi
  unsigned int started; // edi
  char v6; // cl
  unsigned __int8 *p_SoftwareRadioState; // r14
  unsigned __int8 *p_HardwareRadioState; // rdi
  CAdapterPropertyCache *v9; // rax
  unsigned int v10; // eax
  int v11; // r9d
  CAdapterPropertyCache *v12; // rax
  CAdapterPropertyCache *v13; // rax
  unsigned __int8 v14; // di
  unsigned int FirmwareCapabilities; // eax
  __int64 v16; // [rsp+38h] [rbp-40h]
  unsigned __int8 v17; // [rsp+88h] [rbp+10h] BYREF

  m_JobState = this->m_JobState;
  v17 = 0;
  started = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      108,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  switch ( this->m_JobState )
  {
    case MiniportInitializeJobWaitingForOpenTaskComplete:
      started = CMiniportInitializeJob::CompleteOpenTask(this, started);
      if ( started )
        goto LABEL_54;
      this->m_pAdapter->m_InitializationState |= 4u;
      started = CAdapter::InitializeDataPath(this->m_pAdapter);
      if ( started )
        goto LABEL_54;
      m_JobState = MiniportInitializeJobWaitingForFirmwareCapabilities;
      this->m_pAdapter->m_InitializationState |= 8u;
      FirmwareCapabilities = CMiniportInitializeJob::StartGetFirmwareCapabilities(this);
LABEL_53:
      started = FirmwareCapabilities;
      goto LABEL_54;
    case MiniportInitializeJobWaitingForFirmwareCapabilities:
      started = CMiniportInitializeJob::CompleteGetFirmwareCapabilities(this, started, (int)a3);
      if ( started )
        goto LABEL_54;
      m_JobState = MiniportInitializeJobWaitingForFirmwareConfiguration;
      FirmwareCapabilities = CMiniportInitializeJob::StartSetFirmwareConfiguration(this);
      goto LABEL_53;
    case MiniportInitializeJobWaitingForFirmwareConfiguration:
      started = CMiniportInitializeJob::CompleteSetFirmwareConfiguration(this, started);
      if ( started )
        goto LABEL_54;
      started = CAdapter::StartDataPath(this->m_pAdapter);
      if ( started )
        goto LABEL_54;
      m_JobState = MiniportInitializeJobWaitingForCreatePortComplete;
      this->m_pAdapter->m_InitializationState |= 0x10u;
      FirmwareCapabilities = CMiniportInitializeJob::StartCreatePortJob(this, 0);
      goto LABEL_53;
  }
  if ( this->m_JobState != MiniportInitializeJobWaitingForCreatePortComplete )
  {
    if ( this->m_JobState == MiniportInitializeJobWaitingForSetRadioStateComplete )
    {
      if ( started && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          115,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          this->m_ActivityId,
          started);
      }
      goto LABEL_13;
    }
    goto LABEL_54;
  }
  started = CMiniportInitializeJob::CompleteCreatePortJob(this, started);
  if ( started )
    goto LABEL_54;
  m_JobState = MiniportInitializeJobWaitingForSetRadioStateComplete;
  p_SoftwareRadioState = &this->m_AdapterCapabilities.InterfaceAttributes.InterfaceCapabilities.SoftwareRadioState;
  p_HardwareRadioState = &this->m_AdapterCapabilities.InterfaceAttributes.InterfaceCapabilities.HardwareRadioState;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      109,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      *p_HardwareRadioState,
      *p_SoftwareRadioState);
  }
  v9 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  v10 = CPropertyCache::SetPropertyBoolean(v9, 0x2Du, *p_HardwareRadioState == 0);
  started = v10;
  if ( v10 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    v11 = 110;
    goto LABEL_31;
  }
  v12 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  v10 = CPropertyCache::SetPropertyBoolean(v12, 0x2Eu, *p_SoftwareRadioState == 0);
  started = v10;
  if ( v10 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    v11 = 111;
LABEL_31:
    LOBYTE(a2) = 2;
    LODWORD(v16) = v10;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      v11,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v16);
    goto LABEL_54;
  }
  v13 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  started = CPropertyCache::GetPropertyUchar(v13, 0x74u, &v17);
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        112,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
  }
  else
  {
    v14 = v17;
    if ( *p_SoftwareRadioState != v17 )
    {
LABEL_13:
      this->m_JobState = MiniportInitializeJobSettingMiniportAttributes;
      started = CMiniportInitializeJob::SetMiniportAttributes(this, 0);
      if ( !started )
      {
        this->m_JobState = MiniportInitializeJobStartingIHVOperations;
        started = CMiniportInitializeJob::PerformIHVOperationsStart(this);
        if ( !started )
          this->m_JobState = MiniportInitializeJobSucceeded;
      }
      v6 = 1;
      goto LABEL_17;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        113,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v17,
        *p_SoftwareRadioState);
    }
    started = CMiniportInitializeJob::StartSetRadioStateTask(this, v14);
    if ( started )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          114,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
      }
    }
    else
    {
      this->m_JobState = MiniportInitializeJobWaitingForSetRadioStateComplete;
    }
  }
LABEL_54:
  v6 = 0;
  if ( this->m_pAdapter->m_lResetRecovery )
  {
    CMiniportInitializeJob::SetMiniportAttributes(this, 1);
    started = 0;
    goto LABEL_20;
  }
LABEL_17:
  if ( started || v6 == 1 )
    CMiniportInitializeJob::FinishJob(this, m_JobState, started);
LABEL_20:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v16) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      116,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v16);
  }
}

```

## disassembly

```asm
0x140076da0  mov     rax, rsp
0x140076da3  mov     [rax+8], rbx
0x140076da7  mov     [rax+18h], rbp
0x140076dab  push    rsi
0x140076dac  push    rdi
0x140076dad  push    r12
0x140076daf  push    r14
0x140076db1  push    r15
0x140076db3  sub     rsp, 50h
0x140076db7  mov     esi, [rcx+200h]
0x140076dbd  xor     ebp, ebp
0x140076dbf  mov     [rax+10h], bpl
0x140076dc3  mov     edi, edx
0x140076dc5  mov     rbx, rcx
0x140076dc8  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140076dcf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140076dd6  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x140076ddd  jz      short loc_140076E14
0x140076ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140076de6  cmp     byte ptr [rcx+29h], 5
0x140076dea  jnb     short loc_140076DF2
0x140076dec  cmp     [rcx+48h], bp
0x140076df0  jz      short loc_140076E14
0x140076df2  mov     eax, [rbx+10h]
0x140076df5  mov     r9d, 6Ch ; 'l'
0x140076dfb  mov     rcx, [rcx+40h]
0x140076dff  mov     dl, 5
0x140076e01  mov     [rsp+78h+var_48], eax
0x140076e05  mov     [rsp+78h+var_50], rbx
0x140076e0a  mov     [rsp+78h+var_58], r12
0x140076e0f  call    WPP_RECORDER_SF_qD
0x140076e14  mov     ecx, [rbx+200h]
0x140076e1a  sub     ecx, 2
0x140076e1d  jz      loc_1400771B8
0x140076e23  sub     ecx, 1
0x140076e26  jz      loc_14007719B
0x140076e2c  sub     ecx, 1
0x140076e2f  jz      loc_140077154
0x140076e35  sub     ecx, 2
0x140076e38  jz      loc_140076F2F
0x140076e3e  cmp     ecx, 1
0x140076e41  jnz     loc_140077203
0x140076e47  test    edi, edi
0x140076e49  jz      short loc_140076E7F
0x140076e4b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140076e52  jz      short loc_140076E7F
0x140076e54  mov     eax, [rbx+10h]
0x140076e57  lea     r9d, [rcx+72h]
0x140076e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140076e62  mov     dl, 2
0x140076e64  mov     dword ptr [rsp+78h+var_40], edi
0x140076e68  mov     [rsp+78h+var_48], eax
0x140076e6c  mov     [rsp+78h+var_50], rbx
0x140076e71  mov     rcx, [rcx+40h]
0x140076e75  mov     [rsp+78h+var_58], r12
0x140076e7a  call    WPP_RECORDER_SF_qDD
0x140076e7f  xor     edx, edx; bool
0x140076e81  mov     dword ptr [rbx+200h], 8
0x140076e8b  mov     rcx, rbx; this
0x140076e8e  call    ?SetMiniportAttributes@CMiniportInitializeJob@@AEAAH_N@Z; CMiniportInitializeJob::SetMiniportAttributes(bool)
0x140076e93  mov     edi, eax
0x140076e95  test    eax, eax
0x140076e97  jnz     short loc_140076EBB
0x140076e99  mov     rcx, rbx; this
0x140076e9c  mov     dword ptr [rbx+200h], 9
0x140076ea6  call    ?PerformIHVOperationsStart@CMiniportInitializeJob@@AEAAHXZ; CMiniportInitializeJob::PerformIHVOperationsStart(void)
0x140076eab  mov     edi, eax
0x140076ead  test    eax, eax
0x140076eaf  jnz     short loc_140076EBB
0x140076eb1  mov     dword ptr [rbx+200h], 0Ah
0x140076ebb  mov     cl, 1
0x140076ebd  test    edi, edi
0x140076ebf  jnz     short loc_140076EC6
0x140076ec1  cmp     cl, 1
0x140076ec4  jnz     short loc_140076ED3
0x140076ec6  mov     r8d, edi; int
0x140076ec9  mov     edx, esi; enum _MINIPORT_INITIALIZE_JOB_STATE
0x140076ecb  mov     rcx, rbx; this
0x140076ece  call    ?FinishJob@CMiniportInitializeJob@@IEAAXW4_MINIPORT_INITIALIZE_JOB_STATE@@H@Z; CMiniportInitializeJob::FinishJob(_MINIPORT_INITIALIZE_JOB_STATE,int)
0x140076ed3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140076eda  jz      short loc_140076F15
0x140076edc  mov     rcx, cs:WPP_GLOBAL_Control
0x140076ee3  cmp     byte ptr [rcx+29h], 5
0x140076ee7  jnb     short loc_140076EEF
0x140076ee9  cmp     [rcx+48h], bp
0x140076eed  jz      short loc_140076F15
0x140076eef  mov     eax, [rbx+10h]
0x140076ef2  mov     r9d, 74h ; 't'
0x140076ef8  mov     rcx, [rcx+40h]
0x140076efc  mov     dl, 5
0x140076efe  mov     dword ptr [rsp+78h+var_40], edi
0x140076f02  mov     [rsp+78h+var_48], eax
0x140076f06  mov     [rsp+78h+var_50], rbx
0x140076f0b  mov     [rsp+78h+var_58], r12
0x140076f10  call    WPP_RECORDER_SF_qDD
0x140076f15  lea     r11, [rsp+78h+var_28]
0x140076f1a  mov     rbx, [r11+30h]
0x140076f1e  mov     rbp, [r11+40h]
0x140076f22  mov     rsp, r11
0x140076f25  pop     r15
0x140076f27  pop     r14
0x140076f29  pop     r12
0x140076f2b  pop     rdi
0x140076f2c  pop     rsi
0x140076f2d  retn
0x140076f2f  mov     edx, edi; int
0x140076f31  mov     rcx, rbx; this
0x140076f34  call    ?CompleteCreatePortJob@CMiniportInitializeJob@@IEAAHH@Z; CMiniportInitializeJob::CompleteCreatePortJob(int)
0x140076f39  mov     edi, eax
0x140076f3b  test    eax, eax
0x140076f3d  jnz     loc_140077203
0x140076f43  lea     esi, [rax+7]
0x140076f46  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140076f4d  lea     r14, [rbx+15BDh]
0x140076f54  lea     rdi, [rbx+15BCh]
0x140076f5b  jz      short loc_140076F93
0x140076f5d  movzx   eax, byte ptr [r14]
0x140076f61  lea     r9d, [rsi+66h]
0x140076f65  movzx   ecx, byte ptr [rdi]
0x140076f68  mov     dl, 4
0x140076f6a  mov     [rsp+78h+var_38], eax
0x140076f6e  mov     eax, [rbx+10h]
0x140076f71  mov     dword ptr [rsp+78h+var_40], ecx
0x140076f75  mov     rcx, cs:WPP_GLOBAL_Control
0x140076f7c  mov     [rsp+78h+var_48], eax
0x140076f80  mov     [rsp+78h+var_50], rbx
0x140076f85  mov     [rsp+78h+var_58], r12
0x140076f8a  mov     rcx, [rcx+40h]
0x140076f8e  call    WPP_RECORDER_SF_qDdd
0x140076f93  mov     rcx, [rbx+208h]
0x140076f9a  add     rcx, 8
0x140076f9e  mov     rax, [rcx]
0x140076fa1  mov     rax, [rax+8]
0x140076fa5  call    _guard_dispatch_icall
0x140076faa  cmp     [rdi], bpl
0x140076fad  mov     edx, 2Dh ; '-'; unsigned int
0x140076fb2  mov     rcx, rax; this
0x140076fb5  setz    r8b; unsigned __int8
0x140076fb9  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x140076fbe  mov     edi, eax
0x140076fc0  test    eax, eax
0x140076fc2  jz      short loc_140077003
0x140076fc4  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140076fcb  jz      loc_140077203
0x140076fd1  mov     r9d, 6Eh ; 'n'
0x140076fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140076fde  mov     dl, 2
0x140076fe0  mov     dword ptr [rsp+78h+var_40], eax
0x140076fe4  mov     eax, [rbx+10h]
0x140076fe7  mov     [rsp+78h+var_48], eax
0x140076feb  mov     rcx, [rcx+40h]
0x140076fef  mov     [rsp+78h+var_50], rbx
0x140076ff4  mov     [rsp+78h+var_58], r12
0x140076ff9  call    WPP_RECORDER_SF_qDD
0x140076ffe  jmp     loc_140077203
0x140077003  mov     rcx, [rbx+208h]
0x14007700a  add     rcx, 8
0x14007700e  mov     rax, [rcx]
0x140077011  mov     rax, [rax+8]
0x140077015  call    _guard_dispatch_icall
0x14007701a  cmp     [r14], bpl
0x14007701d  mov     edx, 2Eh ; '.'; unsigned int
0x140077022  mov     rcx, rax; this
0x140077025  setz    r8b; unsigned __int8
0x140077029  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14007702e  mov     edi, eax
0x140077030  test    eax, eax
0x140077032  jz      short loc_140077049
0x140077034  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14007703b  jz      loc_140077203
0x140077041  mov     r9d, 6Fh ; 'o'
0x140077047  jmp     short loc_140076FD7
0x140077049  mov     rcx, [rbx+208h]
0x140077050  add     rcx, 8
0x140077054  mov     rax, [rcx]
0x140077057  mov     rax, [rax+8]
0x14007705b  call    _guard_dispatch_icall
0x140077060  lea     r8, [rsp+78h+arg_8]; unsigned __int8 *
0x140077068  mov     edx, 74h ; 't'; unsigned int
0x14007706d  mov     rcx, rax; this
0x140077070  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x140077075  mov     edi, eax
0x140077077  test    eax, eax
0x140077079  jz      short loc_1400770B6
0x14007707b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140077082  jz      loc_140077203
0x140077088  mov     rcx, cs:WPP_GLOBAL_Control
0x14007708f  mov     r9d, 70h ; 'p'
0x140077095  mov     eax, [rbx+10h]
0x140077098  mov     dl, 2
0x14007709a  mov     [rsp+78h+var_48], eax
0x14007709e  mov     [rsp+78h+var_50], rbx
0x1400770a3  mov     rcx, [rcx+40h]
0x1400770a7  mov     [rsp+78h+var_58], r12
0x1400770ac  call    WPP_RECORDER_SF_qD
0x1400770b1  jmp     loc_140077203
0x1400770b6  movzx   eax, byte ptr [r14]
0x1400770ba  movzx   edi, [rsp+78h+arg_8]
0x1400770c2  cmp     al, dil
0x1400770c5  jnz     loc_140076E7F
0x1400770cb  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400770d2  jz      short loc_140077105
0x1400770d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400770db  mov     r9d, 71h ; 'q'
0x1400770e1  mov     [rsp+78h+var_38], eax
0x1400770e5  mov     dl, 4
0x1400770e7  mov     eax, [rbx+10h]
0x1400770ea  mov     dword ptr [rsp+78h+var_40], edi
0x1400770ee  mov     rcx, [rcx+40h]
0x1400770f2  mov     [rsp+78h+var_48], eax
0x1400770f6  mov     [rsp+78h+var_50], rbx
0x1400770fb  mov     [rsp+78h+var_58], r12
0x140077100  call    WPP_RECORDER_SF_qDdd
0x140077105  mov     dl, dil; unsigned __int8
0x140077108  mov     rcx, rbx; this
0x14007710b  call    ?StartSetRadioStateTask@CMiniportInitializeJob@@IEAAHE@Z; CMiniportInitializeJob::StartSetRadioStateTask(uchar)
0x140077110  mov     edi, eax
0x140077112  test    eax, eax
0x140077114  jz      short loc_140077149
0x140077116  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14007711d  jz      loc_140077203
0x140077123  mov     rcx, cs:WPP_GLOBAL_Control
0x14007712a  mov     r9d, 72h ; 'r'
0x140077130  mov     dl, 2
0x140077132  mov     [rsp+78h+var_58], r12
0x140077137  mov     rcx, [rcx+40h]
0x14007713b  lea     r8d, [r9-71h]
0x14007713f  call    WPP_RECORDER_SF_
0x140077144  jmp     loc_140077203
0x140077149  mov     [rbx+200h], esi
0x14007714f  jmp     loc_140077203
0x140077154  mov     edx, edi; int
0x140077156  mov     rcx, rbx; this
0x140077159  call    ?CompleteSetFirmwareConfiguration@CMiniportInitializeJob@@IEAAHH@Z; CMiniportInitializeJob::CompleteSetFirmwareConfiguration(int)
0x14007715e  mov     edi, eax
0x140077160  test    eax, eax
0x140077162  jnz     loc_140077203
0x140077168  mov     rcx, [rbx+208h]; this
0x14007716f  call    ?StartDataPath@CAdapter@@QEAAHXZ; CAdapter::StartDataPath(void)
0x140077174  mov     edi, eax
0x140077176  test    eax, eax
0x140077178  jnz     loc_140077203
0x14007717e  mov     rax, [rbx+208h]
0x140077185  lea     esi, [rdi+6]
0x140077188  xor     edx, edx; unsigned __int8
0x14007718a  mov     rcx, rbx; this
0x14007718d  or      dword ptr [rax+12F0h], 10h
0x140077194  call    ?StartCreatePortJob@CMiniportInitializeJob@@IEAAHE@Z; CMiniportInitializeJob::StartCreatePortJob(uchar)
0x140077199  jmp     short loc_140077201
0x14007719b  mov     edx, edi; int
0x14007719d  mov     rcx, rbx; this
0x1400771a0  call    ?CompleteGetFirmwareCapabilities@CMiniportInitializeJob@@AEAAHH@Z; CMiniportInitializeJob::CompleteGetFirmwareCapabilities(int)
0x1400771a5  mov     edi, eax
0x1400771a7  test    eax, eax
0x1400771a9  jnz     short loc_140077203
0x1400771ab  mov     rcx, rbx; this
0x1400771ae  lea     esi, [rax+4]
0x1400771b1  call    ?StartSetFirmwareConfiguration@CMiniportInitializeJob@@IEAAHXZ; CMiniportInitializeJob::StartSetFirmwareConfiguration(void)
0x1400771b6  jmp     short loc_140077201
0x1400771b8  mov     edx, edi; int
0x1400771ba  mov     rcx, rbx; this
0x1400771bd  call    ?CompleteOpenTask@CMiniportInitializeJob@@IEAAHH@Z; CMiniportInitializeJob::CompleteOpenTask(int)
0x1400771c2  mov     edi, eax
0x1400771c4  test    eax, eax
0x1400771c6  jnz     short loc_140077203
0x1400771c8  mov     rax, [rbx+208h]
0x1400771cf  or      dword ptr [rax+12F0h], 4
0x1400771d6  mov     rcx, [rbx+208h]; this
0x1400771dd  call    ?InitializeDataPath@CAdapter@@QEAAHXZ; CAdapter::InitializeDataPath(void)
0x1400771e2  mov     edi, eax
0x1400771e4  test    eax, eax
0x1400771e6  jnz     short loc_140077203
0x1400771e8  mov     rax, [rbx+208h]
0x1400771ef  lea     esi, [rdi+3]
0x1400771f2  mov     rcx, rbx; this
0x1400771f5  or      dword ptr [rax+12F0h], 8
0x1400771fc  call    ?StartGetFirmwareCapabilities@CMiniportInitializeJob@@AEAAHXZ; CMiniportInitializeJob::StartGetFirmwareCapabilities(void)
0x140077201  mov     edi, eax
0x140077203  mov     rax, [rbx+208h]
0x14007720a  mov     cl, bpl
0x14007720d  cmp     [rax+15C8h], ebp
0x140077213  jz      loc_140076EBD
0x140077219  mov     dl, 1; bool
0x14007721b  mov     rcx, rbx; this
0x14007721e  call    ?SetMiniportAttributes@CMiniportInitializeJob@@AEAAH_N@Z; CMiniportInitializeJob::SetMiniportAttributes(bool)
0x140077223  mov     edi, ebp
0x140077225  jmp     loc_140076ED3
```
