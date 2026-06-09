# CCreatePortJob::CompleteCreatePortTask(int)

- ea: `0x14006b72c`
- end: `0x14006bbe8`
- name: `?CompleteCreatePortTask@CCreatePortJob@@AEAAHH@Z`
- size: `1212`
- prototype: `__int64 __fastcall(CCreatePortJob *__hidden this, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140069900`

## callees

- `0x1400100f8`
- `0x140011114`
- `0x140011244`
- `0x1400122e0`
- `0x1400297a0`
- `0x14002aa28`
- `0x14004da7c`
- `0x140061328`
- `0x14006b72c`
- `0x14007b02c`
- `0x14007e60c`
- `0x140086dc0`
- `0x14008d9c8`
- `0x1400a8158`
- `0x1400aaa4c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006b9d6`
- `ntoskrnl!ExAllocatePool2` at `0x14006b9d6`

## pseudocode

```c
__int64 __fastcall CCreatePortJob::CompleteCreatePortTask(CCreatePortJob *this, unsigned int a2, int a3)
{
  unsigned int StatusFromTaskOutput; // edi
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  unsigned __int16 PortNumber; // ax
  _WDI_INDICATION_CREATE_PORT_COMPLETE_PARAMETERS *p_m_CreatePortIndicationParameters; // rbp
  unsigned int OutputBuffer; // eax
  int v11; // r9d
  CPort *Pool2; // rax
  CPort *v13; // rsi
  unsigned int v14; // eax
  CAdapter *m_pAdapter; // rdx
  int v16; // r8d
  int v17; // r9d
  int v18; // edx
  unsigned __int8 i; // al
  int v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+38h] [rbp-50h]
  int v23; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int8 *v25; // [rsp+A8h] [rbp+20h] BYREF

  StatusFromTaskOutput = a2;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        19,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        20,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
  }
  if ( StatusFromTaskOutput )
    goto LABEL_45;
  StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(&this->m_CreateTask, &v23);
  if ( !StatusFromTaskOutput )
  {
    OutputBuffer = Task::get_OutputBuffer(&this->m_CreateTask, &v24, &v25);
    StatusFromTaskOutput = OutputBuffer;
    if ( OutputBuffer )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromTaskOutput;
      v11 = 22;
    }
    else
    {
      p_m_CreatePortIndicationParameters = &this->m_CreatePortIndicationParameters;
      OutputBuffer = ParseWdiIndicationCreatePortCompleteFromIhv(
                       v24 - 48,
                       v25 + 48,
                       &this->m_pAdapter->m_TlvContext,
                       &this->m_CreatePortIndicationParameters);
      StatusFromTaskOutput = OutputBuffer;
      if ( !OutputBuffer )
      {
        PortNumber = this->m_CreatePortIndicationParameters.PortAttributes.PortNumber;
        goto LABEL_21;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return StatusFromTaskOutput;
      v11 = 23;
    }
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      v11,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      OutputBuffer);
LABEL_45:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      LODWORD(v22) = StatusFromTaskOutput;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        30,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v22);
    }
    return StatusFromTaskOutput;
  }
  if ( !this->m_CreatedNdisPortNumber )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return StatusFromTaskOutput;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      21,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      StatusFromTaskOutput,
      v23);
    goto LABEL_45;
  }
  PortNumber = this->m_CreatedNdisPortNumber;
  p_m_CreatePortIndicationParameters = &this->m_CreatePortIndicationParameters;
LABEL_21:
  this->m_CreatedPortId = PortNumber;
  if ( !this->m_bCreateForResume )
  {
    Pool2 = (CPort *)ExAllocatePool2(64, 1144, 1198089303);
    if ( !Pool2 || (v13 = CPort::CPort(Pool2)) == 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          a3,
          26,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      StatusFromTaskOutput = -1073741670;
      goto LABEL_45;
    }
    v14 = CPort::Initialize(
            v13,
            this->m_pAdapter,
            this->m_PortType,
            this->m_CreatedNdisPortNumber,
            this->m_CreatedPortId,
            (unsigned __int8 *const)p_m_CreatePortIndicationParameters);
    StatusFromTaskOutput = v14;
    if ( v14 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_41:
        CPort::`scalar deleting destructor'(v13, (unsigned int)m_pAdapter);
        goto LABEL_45;
      }
      v17 = 27;
      LODWORD(v22) = v14;
    }
    else
    {
      CPropertyCache::SetPropertyULong(&v13->m_PortPropertyCache, 0x18u, this->m_uOpmodeMask);
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDqdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          v16,
          28,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
          (char)this,
          this->m_ActivityId,
          (char)v13,
          v13->m_NdisPortNumber,
          v13->m_WfcPortId);
      m_pAdapter = this->m_pAdapter;
      for ( i = 0; i < 5u; ++i )
      {
        if ( !m_pAdapter->m_pPortList[i] )
        {
          m_pAdapter->m_pPortList[i] = v13;
          StatusFromTaskOutput = 0;
          CTxMgr::AddPortId(&this->m_pAdapter->m_TxMgr, v13->m_WfcPortId);
          ((void (__fastcall *)(void *, _QWORD, _QWORD))this->m_pAdapter->m_MiniportDataHandlers.TalTxRxAddPortHandler)(
            this->m_pAdapter->m_MiniportTalTxRxContext,
            v13->m_WfcPortId,
            (unsigned int)this->m_uOpmodeMask);
          goto LABEL_45;
        }
      }
      StatusFromTaskOutput = -1073676272;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v17 = 29;
      LODWORD(v22) = -1073676272;
    }
    LOBYTE(m_pAdapter) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)m_pAdapter,
      v16,
      v17,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v22);
    goto LABEL_41;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      PortNumber,
      24,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      this->m_pPortToResume->m_WfcPortId,
      PortNumber);
  }
  this->m_pPortToResume->m_WfcPortId = this->m_CreatedPortId;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qD_MAC__MAC_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      v7,
      v21,
      (char)this,
      this->m_ActivityId,
      (__int64)this->m_pPortToResume->m_MacAddress,
      (__int64)p_m_CreatePortIndicationParameters);
    goto LABEL_45;
  }
  return StatusFromTaskOutput;
}

```

## disassembly

```asm
0x14006b72c  mov     rax, rsp
0x14006b72f  push    rbx
0x14006b730  push    rbp
0x14006b731  push    rsi
0x14006b732  push    rdi
0x14006b733  push    r12
0x14006b735  push    r14
0x14006b737  push    r15
0x14006b739  sub     rsp, 50h
0x14006b73d  xor     r14d, r14d
0x14006b740  mov     edi, edx
0x14006b742  mov     [rax+10h], r14d
0x14006b746  mov     rbx, rcx
0x14006b749  mov     [rax+18h], r14d
0x14006b74d  mov     [rax+20h], r14
0x14006b751  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006b758  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006b75f  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x14006b766  jz      short loc_14006B7D4
0x14006b768  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b76f  cmp     byte ptr [rcx+29h], 5
0x14006b773  jnb     short loc_14006B77C
0x14006b775  cmp     [rcx+48h], r14w
0x14006b77a  jz      short loc_14006B79E
0x14006b77c  mov     eax, [rbx+10h]
0x14006b77f  mov     r9d, 13h
0x14006b785  mov     rcx, [rcx+40h]
0x14006b789  mov     dl, 5
0x14006b78b  mov     [rsp+88h+var_58], eax
0x14006b78f  mov     [rsp+88h+var_60], rbx
0x14006b794  mov     qword ptr [rsp+88h+var_68], r12
0x14006b799  call    WPP_RECORDER_SF_qD
0x14006b79e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b7a5  jz      short loc_14006B7D4
0x14006b7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b7ae  mov     r9d, 14h
0x14006b7b4  mov     eax, [rbx+10h]
0x14006b7b7  mov     dl, 4
0x14006b7b9  mov     dword ptr [rsp+88h+var_50], edi
0x14006b7bd  mov     [rsp+88h+var_58], eax
0x14006b7c1  mov     rcx, [rcx+40h]
0x14006b7c5  mov     [rsp+88h+var_60], rbx
0x14006b7ca  mov     qword ptr [rsp+88h+var_68], r12
0x14006b7cf  call    WPP_RECORDER_SF_qDD
0x14006b7d4  test    edi, edi
0x14006b7d6  jnz     loc_14006BB93
0x14006b7dc  lea     rsi, [rbx+200h]
0x14006b7e3  mov     rcx, rsi; struct Task *
0x14006b7e6  lea     rdx, [rsp+88h+arg_8]; int *
0x14006b7ee  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x14006b7f3  mov     edi, eax
0x14006b7f5  test    eax, eax
0x14006b7f7  jz      short loc_14006B85F
0x14006b7f9  cmp     [rbx+3D8h], r14d
0x14006b800  jz      short loc_14006B815
0x14006b802  movzx   eax, word ptr [rbx+3D8h]
0x14006b809  lea     rbp, [rbx+108Ch]
0x14006b810  jmp     loc_14006B911
0x14006b815  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b81c  jz      loc_14006BBD6
0x14006b822  mov     eax, [rsp+88h+arg_8]
0x14006b829  mov     r9d, 15h
0x14006b82f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b836  mov     dl, 2
0x14006b838  mov     dword ptr [rsp+88h+var_48], eax
0x14006b83c  mov     eax, [rbx+10h]
0x14006b83f  mov     dword ptr [rsp+88h+var_50], edi
0x14006b843  mov     rcx, [rcx+40h]
0x14006b847  mov     [rsp+88h+var_58], eax
0x14006b84b  mov     [rsp+88h+var_60], rbx
0x14006b850  mov     qword ptr [rsp+88h+var_68], r12
0x14006b855  call    WPP_RECORDER_SF_qDDd
0x14006b85a  jmp     loc_14006BB93
0x14006b85f  lea     r8, [rsp+88h+arg_18]; unsigned __int8 **
0x14006b867  mov     rcx, rsi; this
0x14006b86a  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x14006b872  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x14006b877  mov     edi, eax
0x14006b879  test    eax, eax
0x14006b87b  jz      short loc_14006B892
0x14006b87d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b884  jz      loc_14006BBD6
0x14006b88a  mov     r9d, 16h
0x14006b890  jmp     short loc_14006B8DE
0x14006b892  mov     ecx, [rsp+88h+arg_10]
0x14006b899  lea     rbp, [rbx+108Ch]
0x14006b8a0  mov     r8, [rbx+3E0h]
0x14006b8a7  add     ecx, 0FFFFFFD0h
0x14006b8aa  mov     rdx, [rsp+88h+arg_18]
0x14006b8b2  add     r8, 3FF8h
0x14006b8b9  add     rdx, 30h ; '0'
0x14006b8bd  mov     r9, rbp
0x14006b8c0  call    ParseWdiIndicationCreatePortCompleteFromIhv
0x14006b8c5  mov     edi, eax
0x14006b8c7  test    eax, eax
0x14006b8c9  jz      short loc_14006B90A
0x14006b8cb  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b8d2  jz      loc_14006BBD6
0x14006b8d8  mov     r9d, 17h
0x14006b8de  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b8e5  mov     dl, 2
0x14006b8e7  mov     dword ptr [rsp+88h+var_50], eax
0x14006b8eb  mov     eax, [rbx+10h]
0x14006b8ee  mov     [rsp+88h+var_58], eax
0x14006b8f2  mov     rcx, [rcx+40h]
0x14006b8f6  mov     [rsp+88h+var_60], rbx
0x14006b8fb  mov     qword ptr [rsp+88h+var_68], r12
0x14006b900  call    WPP_RECORDER_SF_qDD
0x14006b905  jmp     loc_14006BB93
0x14006b90a  movzx   eax, word ptr [rbx+1092h]
0x14006b911  mov     [rbx+3DCh], ax
0x14006b918  cmp     [rbx+1070h], r14b
0x14006b91f  jz      loc_14006B9C6
0x14006b925  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b92c  jz      short loc_14006B96F
0x14006b92e  movzx   r8d, ax
0x14006b932  mov     r9d, 18h
0x14006b938  mov     rax, [rbx+1078h]
0x14006b93f  mov     dl, 4
0x14006b941  mov     dword ptr [rsp+88h+var_48], r8d
0x14006b946  movzx   ecx, word ptr [rax+64h]
0x14006b94a  mov     eax, [rbx+10h]
0x14006b94d  mov     dword ptr [rsp+88h+var_50], ecx
0x14006b951  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b958  mov     [rsp+88h+var_58], eax
0x14006b95c  mov     [rsp+88h+var_60], rbx
0x14006b961  mov     qword ptr [rsp+88h+var_68], r12
0x14006b966  mov     rcx, [rcx+40h]
0x14006b96a  call    WPP_RECORDER_SF_qDdd
0x14006b96f  mov     rcx, [rbx+1078h]
0x14006b976  movzx   eax, word ptr [rbx+3DCh]
0x14006b97d  mov     [rcx+64h], ax
0x14006b981  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006b988  jz      loc_14006BBD6
0x14006b98e  mov     rax, [rbx+1078h]
0x14006b995  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b99c  add     rax, 208h
0x14006b9a2  mov     [rsp+88h+var_48], rbp
0x14006b9a7  mov     [rsp+88h+var_50], rax
0x14006b9ac  mov     eax, [rbx+10h]
0x14006b9af  mov     rcx, [rcx+40h]
0x14006b9b3  mov     [rsp+88h+var_58], eax
0x14006b9b7  mov     [rsp+88h+var_60], rbx
0x14006b9bc  call    WPP_RECORDER_SF_qD_MAC__MAC_
0x14006b9c1  jmp     loc_14006BB93
0x14006b9c6  mov     edx, 478h
0x14006b9cb  mov     ecx, 40h ; '@'
0x14006b9d0  mov     r8d, 47696457h
0x14006b9d6  call    cs:__imp_ExAllocatePool2
0x14006b9dd  nop     dword ptr [rax+rax+00h]
0x14006b9e2  test    rax, rax
0x14006b9e5  jz      loc_14006BB5C
0x14006b9eb  mov     rcx, rax; this
0x14006b9ee  call    ??0CPort@@QEAA@XZ; CPort::CPort(void)
0x14006b9f3  mov     rsi, rax
0x14006b9f6  test    rax, rax
0x14006b9f9  jz      loc_14006BB5C
0x14006b9ff  movzx   eax, word ptr [rbx+3DCh]
0x14006ba06  mov     rcx, rsi; this
0x14006ba09  mov     r9d, [rbx+3D8h]; unsigned int
0x14006ba10  mov     r8d, [rbx+3E8h]; enum _WFC_PORT_TYPE
0x14006ba17  mov     rdx, [rbx+3E0h]; CAdapter *
0x14006ba1e  mov     [rsp+88h+var_60], rbp; unsigned __int8 *
0x14006ba23  mov     [rsp+88h+var_68], ax; unsigned __int16
0x14006ba28  call    ?Initialize@CPort@@QEAAHPEAVCAdapter@@W4_WFC_PORT_TYPE@@KGQEAE@Z; CPort::Initialize(CAdapter *,_WFC_PORT_TYPE,ulong,ushort,uchar * const)
0x14006ba2d  mov     edi, eax
0x14006ba2f  test    eax, eax
0x14006ba31  jz      short loc_14006BA4F
0x14006ba33  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006ba3a  jz      loc_14006BB52
0x14006ba40  mov     r9d, 1Bh
0x14006ba46  mov     dword ptr [rsp+88h+var_50], eax
0x14006ba4a  jmp     loc_14006BB2F
0x14006ba4f  mov     r8d, [rbx+3ECh]; unsigned int
0x14006ba56  lea     rcx, [rsi+3A8h]; this
0x14006ba5d  mov     edx, 18h; unsigned int
0x14006ba62  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14006ba67  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006ba6e  jz      short loc_14006BAAB
0x14006ba70  movzx   eax, word ptr [rsi+64h]
0x14006ba74  mov     r9d, 1Ch
0x14006ba7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ba81  mov     [rsp+88h+var_40], eax
0x14006ba85  mov     eax, [rsi+60h]
0x14006ba88  mov     dword ptr [rsp+88h+var_48], eax
0x14006ba8c  mov     eax, [rbx+10h]
0x14006ba8f  mov     rcx, [rcx+40h]
0x14006ba93  mov     [rsp+88h+var_50], rsi
0x14006ba98  mov     [rsp+88h+var_58], eax
0x14006ba9c  mov     [rsp+88h+var_60], rbx
0x14006baa1  mov     qword ptr [rsp+88h+var_68], r12
0x14006baa6  call    WPP_RECORDER_SF_qDqdd
0x14006baab  mov     rdx, [rbx+3E0h]
0x14006bab2  mov     al, r14b
0x14006bab5  cmp     al, 5
0x14006bab7  jnb     short loc_14006BB13
0x14006bab9  movzx   ecx, al
0x14006babc  cmp     [rdx+rcx*8+1318h], r14
0x14006bac4  jz      short loc_14006BACA
0x14006bac6  inc     al
0x14006bac8  jmp     short loc_14006BAB5
0x14006baca  mov     [rdx+rcx*8+1318h], rsi
0x14006bad2  mov     edi, r14d
0x14006bad5  mov     rcx, [rbx+3E0h]
0x14006badc  movzx   edx, word ptr [rsi+64h]; unsigned __int16
0x14006bae0  add     rcx, 3A10h; this
0x14006bae7  call    ?AddPortId@CTxMgr@@QEAAHG@Z; CTxMgr::AddPortId(ushort)
0x14006baec  mov     rcx, [rbx+3E0h]
0x14006baf3  mov     r8d, [rbx+3ECh]
0x14006bafa  movzx   edx, word ptr [rsi+64h]
0x14006bafe  mov     rax, [rcx+3ED4h]
0x14006bb05  mov     rcx, [rcx+70h]
0x14006bb09  call    _guard_dispatch_icall
0x14006bb0e  jmp     loc_14006BB93
0x14006bb13  mov     edi, 0C0010010h
0x14006bb18  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bb1f  jz      short loc_14006BB52
0x14006bb21  mov     r9d, 1Dh
0x14006bb27  mov     dword ptr [rsp+88h+var_50], 0C0010010h
0x14006bb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bb36  mov     dl, 2
0x14006bb38  mov     eax, [rbx+10h]
0x14006bb3b  mov     [rsp+88h+var_58], eax
0x14006bb3f  mov     [rsp+88h+var_60], rbx
0x14006bb44  mov     rcx, [rcx+40h]
0x14006bb48  mov     qword ptr [rsp+88h+var_68], r12
0x14006bb4d  call    WPP_RECORDER_SF_qDD
0x14006bb52  mov     rcx, rsi; this
0x14006bb55  call    ??_GCPort@@QEAAPEAXI@Z; CPort::`scalar deleting destructor'(uint)
0x14006bb5a  jmp     short loc_14006BB93
0x14006bb5c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bb63  jz      short loc_14006BB8E
0x14006bb65  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bb6c  mov     r9d, 1Ah
0x14006bb72  mov     eax, [rbx+10h]
0x14006bb75  mov     dl, 2
0x14006bb77  mov     [rsp+88h+var_58], eax
0x14006bb7b  mov     [rsp+88h+var_60], rbx
0x14006bb80  mov     rcx, [rcx+40h]
0x14006bb84  mov     qword ptr [rsp+88h+var_68], r12
0x14006bb89  call    WPP_RECORDER_SF_qD
0x14006bb8e  mov     edi, 0C000009Ah
0x14006bb93  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006bb9a  jz      short loc_14006BBD6
0x14006bb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bba3  cmp     byte ptr [rcx+29h], 5
0x14006bba7  jnb     short loc_14006BBB0
0x14006bba9  cmp     [rcx+48h], r14w
0x14006bbae  jz      short loc_14006BBD6
0x14006bbb0  mov     eax, [rbx+10h]
0x14006bbb3  mov     r9d, 1Eh
0x14006bbb9  mov     rcx, [rcx+40h]
0x14006bbbd  mov     dl, 5
0x14006bbbf  mov     dword ptr [rsp+88h+var_50], edi
0x14006bbc3  mov     [rsp+88h+var_58], eax
0x14006bbc7  mov     [rsp+88h+var_60], rbx
0x14006bbcc  mov     qword ptr [rsp+88h+var_68], r12
0x14006bbd1  call    WPP_RECORDER_SF_qDD
0x14006bbd6  mov     eax, edi
0x14006bbd8  add     rsp, 50h
0x14006bbdc  pop     r15
0x14006bbde  pop     r14
0x14006bbe0  pop     r12
0x14006bbe2  pop     rdi
0x14006bbe3  pop     rsi
0x14006bbe4  pop     rbp
0x14006bbe5  pop     rbx
0x14006bbe6  retn
```
