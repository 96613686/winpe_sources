# CPort::StartRoamJob(CRoamReconnectJob * *,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS,_WDF_EXECUTION_LEVEL)

- ea: `0x1400278fc`
- end: `0x140027cba`
- name: `?StartRoamJob@CPort@@QEAAHPEAPEAVCRoamReconnectJob@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WDF_EXECUTION_LEVEL@@@Z`
- size: `958`
- prototype: `__int64 __usercall@<rax>(CPort *__hidden this@<rcx>, struct CRoamReconnectJob **@<rdx>, enum _WFC_ROAM_CONNECT_TRIGGER@<r8d>, enum _WDI_ASSOC_STATUS@<r9d>, enum _WDI_ROAM_CONFIGURATION_FLAGS, enum _WDF_EXECUTION_LEVEL)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140029180`
- `0x140046f74`
- `0x14006ab80`
- `0x140084a6c`

## callees

- `0x140005888`
- `0x140010730`
- `0x1400176b0`
- `0x140026490`
- `0x1400278fc`
- `0x140027cc0`
- `0x140027d38`
- `0x140027e20`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x140063e50`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140027983`
- `ntoskrnl!ExAllocatePool2` at `0x140027983`

## pseudocode

```c
__int64 __fastcall CPort::StartRoamJob(
        CPort *this,
        struct CRoamReconnectJob **a2,
        __int32 a3,
        enum _WDI_ASSOC_STATUS a4,
        enum _WDI_ROAM_CONFIGURATION_FLAGS a5,
        enum _WDF_EXECUTION_LEVEL a6)
{
  unsigned int started; // esi
  __int64 *v11; // rdx
  int v12; // edx
  int v13; // r8d
  __int64 Pool2; // rax
  int v15; // edx
  int v16; // r8d
  unsigned int NextActivityId; // eax
  CRoamReconnectJob *v18; // r8
  CRoamReconnectJob *v19; // rdi
  int PropertyULong; // eax
  char v21; // r9
  int v22; // edx
  int v23; // r8d
  int v25; // r9d
  enum _WDI_ASSOC_STATUS v26[2]; // [rsp+28h] [rbp-60h]
  unsigned __int16 m_WfcPortId; // [rsp+30h] [rbp-58h]
  unsigned int v28; // [rsp+90h] [rbp+8h] BYREF

  started = 0;
  v28 = 0;
  v11 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      1,
      244,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
    v11 = WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids;
  }
  *a2 = 0;
  if ( this->m_Dot11State == WfcPortDot11StateInit )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return started;
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      a3,
      245,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)this,
      this->m_WfcPortId);
    goto LABEL_15;
  }
  if ( CAdapter::IsLowPowerTransitionPending(this->m_pAdapter) )
  {
    if ( a3 == 1 && this->m_WfcPortType == WfcPortTypeExtSTA )
    {
      CPort::ConfigureRoamAtResumeForAssociationLossInPowerTransition(
        this,
        a4,
        WfcRoamConnectTriggerAssociationLoss,
        a5);
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return started;
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        246,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        a3);
    }
    goto LABEL_15;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qDL(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      247,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)this,
      this->m_WfcPortId,
      a3);
  }
  Pool2 = ExAllocatePool2(64, 576, 1198089303);
  v16 = Pool2;
  if ( Pool2 )
  {
    NextActivityId = IActivityId::get_NextActivityId();
    v19 = CRoamReconnectJob::CRoamReconnectJob(v18, NextActivityId);
    if ( v19 )
    {
      PropertyULong = CPropertyCache::GetPropertyULong(&this->m_PortPropertyCache, 0x18u, &v28);
      v21 = 1;
      if ( !PropertyULong )
        v21 = v28;
      started = CRoamReconnectJob::Initialize(
                  v19,
                  this->m_pAdapter,
                  this->m_NdisPortNumber,
                  (v21 & 0x10) != 0,
                  (enum _WFC_ROAM_CONNECT_TRIGGER)a3,
                  a4,
                  a5);
      if ( started )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v25 = 249;
          m_WfcPortId = this->m_WfcPortId;
LABEL_36:
          LOBYTE(v22) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            v23,
            v25,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)this,
            m_WfcPortId);
        }
      }
      else
      {
        if ( a6 == WdfExecutionLevelPassive )
          v19->m_RequiresPassiveIrql = 1;
        started = ActiveJobsList::StartAddNewJob(
                    &this->m_pAdapter->m_ActiveJobsList,
                    v19,
                    (struct IOperationCompletionCallback *)((unsigned __int64)&this->IOperationCompletionCallback
                                                          & -(__int64)(this != 0)));
        if ( !started )
        {
          ++this->m_QueuedJobCount;
          *a2 = v19;
          goto LABEL_15;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v25 = 250;
          m_WfcPortId = this->m_WfcPortId;
          goto LABEL_36;
        }
      }
      ((void (__fastcall *)(CRoamReconnectJob *, __int64))v19->~CRoamReconnectJob)(v19, 1);
      goto LABEL_15;
    }
  }
  started = -1073741670;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return started;
  LOBYTE(v15) = 2;
  WPP_RECORDER_SF_qD(
    WPP_GLOBAL_Control->DeviceExtension,
    v15,
    v16,
    248,
    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
    (char)this,
    this->m_WfcPortId);
LABEL_15:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v26[0] = started;
    LOBYTE(v22) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      1,
      251,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      *(_QWORD *)v26);
  }
  return started;
}

```

## disassembly

```asm
0x1400278fc  mov     rax, rsp
0x1400278ff  push    rbx
0x140027900  push    rbp
0x140027901  push    rsi
0x140027902  push    rdi
0x140027903  push    r12
0x140027905  push    r13
0x140027907  push    r14
0x140027909  push    r15
0x14002790b  sub     rsp, 48h
0x14002790f  xor     r12d, r12d
0x140027912  mov     r15d, r9d
0x140027915  mov     esi, r12d
0x140027918  mov     [rax+8], r12d
0x14002791c  mov     ebp, r8d
0x14002791f  mov     r14, rdx
0x140027922  mov     rbx, rcx
0x140027925  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002792c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140027933  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14002793a  lea     r13d, [r12+1]
0x14002793f  jnz     loc_140027B2D
0x140027945  mov     [r14], r12
0x140027948  cmp     [rbx+32Ch], r12d
0x14002794f  jz      loc_140027B95
0x140027955  mov     rcx, [rbx+58h]; this
0x140027959  call    ?IsLowPowerTransitionPending@CAdapter@@QEAA_NXZ; CAdapter::IsLowPowerTransitionPending(void)
0x14002795e  test    al, al
0x140027960  jnz     loc_140027BD1
0x140027966  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14002796d  jnz     loc_140027AE6
0x140027973  mov     edx, 240h
0x140027978  mov     ecx, 40h ; '@'
0x14002797d  mov     r8d, 47696457h
0x140027983  call    cs:__imp_ExAllocatePool2
0x14002798a  nop     dword ptr [rax+rax+00h]
0x14002798f  mov     r8, rax
0x140027992  test    rax, rax
0x140027995  jz      loc_140027AA2
0x14002799b  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x1400279a0  mov     edx, eax; unsigned int
0x1400279a2  mov     rcx, r8; this
0x1400279a5  call    ??0CRoamReconnectJob@@QEAA@K@Z; CRoamReconnectJob::CRoamReconnectJob(ulong)
0x1400279aa  mov     rdi, rax
0x1400279ad  test    rax, rax
0x1400279b0  jz      loc_140027A9B
0x1400279b6  lea     rcx, [rbx+3A8h]; this
0x1400279bd  mov     edx, 18h; unsigned int
0x1400279c2  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x1400279ca  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400279cf  mov     r9d, r13d
0x1400279d2  test    eax, eax
0x1400279d4  jz      loc_140027B20
0x1400279da  mov     eax, [rsp+88h+arg_20]
0x1400279e1  mov     rcx, rdi; this
0x1400279e4  mov     r8d, [rbx+60h]; unsigned int
0x1400279e8  mov     rdx, [rbx+58h]; struct CAdapter *
0x1400279ec  mov     dword ptr [rsp+88h+var_58], eax; enum _WDI_ROAM_CONFIGURATION_FLAGS
0x1400279f0  shr     r9d, 4
0x1400279f4  and     r9b, r13b; bool
0x1400279f7  mov     [rsp+88h+var_60], r15d; enum _WDI_ASSOC_STATUS
0x1400279fc  mov     [rsp+88h+var_68], ebp; enum _WFC_ROAM_CONNECT_TRIGGER
0x140027a00  call    ?Initialize@CRoamReconnectJob@@QEAAHPEAVCAdapter@@K_NW4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CRoamReconnectJob::Initialize(CAdapter *,ulong,bool,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS)
0x140027a05  mov     esi, eax
0x140027a07  test    eax, eax
0x140027a09  jnz     loc_140027B6A
0x140027a0f  cmp     [rsp+88h+arg_28], 2
0x140027a17  jnz     short loc_140027A1D
0x140027a19  mov     [rdi+2Ah], r13b
0x140027a1d  lea     rcx, [rbx+8]
0x140027a21  mov     rax, rbx
0x140027a24  neg     rax
0x140027a27  mov     rdx, rdi; struct CJobBase *
0x140027a2a  sbb     r8, r8
0x140027a2d  and     r8, rcx; struct IOperationCompletionCallback *
0x140027a30  mov     rcx, [rbx+58h]
0x140027a34  add     rcx, 3E0h; this
0x140027a3b  call    ?StartAddNewJob@ActiveJobsList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@@Z; ActiveJobsList::StartAddNewJob(CJobBase *,IOperationCompletionCallback *)
0x140027a40  mov     esi, eax
0x140027a42  test    eax, eax
0x140027a44  jnz     loc_140027C4E
0x140027a4a  add     [rbx+328h], r13d
0x140027a51  mov     [r14], rdi
0x140027a54  lea     rdi, WPP_RECORDER_INITIALIZED
0x140027a5b  lea     rbx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027a62  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140027a69  jz      short loc_140027A87
0x140027a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a72  cmp     byte ptr [rcx+29h], 5
0x140027a76  jnb     loc_140027C98
0x140027a7c  cmp     [rcx+48h], r12w
0x140027a81  jnz     loc_140027C98
0x140027a87  mov     eax, esi
0x140027a89  add     rsp, 48h
0x140027a8d  pop     r15
0x140027a8f  pop     r14
0x140027a91  pop     r13
0x140027a93  pop     r12
0x140027a95  pop     rdi
0x140027a96  pop     rsi
0x140027a97  pop     rbp
0x140027a98  pop     rbx
0x140027a99  retn
0x140027a9b  lea     rdi, WPP_RECORDER_INITIALIZED
0x140027aa2  mov     esi, 0C000009Ah
0x140027aa7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140027aae  jz      short loc_140027A87
0x140027ab0  movzx   eax, word ptr [rbx+64h]
0x140027ab4  mov     r9d, 0F8h
0x140027aba  mov     rcx, cs:WPP_GLOBAL_Control
0x140027ac1  mov     dl, 2
0x140027ac3  mov     dword ptr [rsp+88h+var_58], eax
0x140027ac7  mov     qword ptr [rsp+88h+var_60], rbx
0x140027acc  lea     rbx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027ad3  mov     qword ptr [rsp+88h+var_68], rbx
0x140027ad8  mov     rcx, [rcx+40h]
0x140027adc  call    WPP_RECORDER_SF_qD
0x140027ae1  jmp     loc_140027A62
0x140027ae6  movzx   eax, word ptr [rbx+64h]
0x140027aea  mov     r9d, 0F7h
0x140027af0  mov     rcx, cs:WPP_GLOBAL_Control
0x140027af7  mov     dl, 4
0x140027af9  mov     [rsp+88h+var_50], ebp
0x140027afd  mov     dword ptr [rsp+88h+var_58], eax
0x140027b01  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027b08  mov     qword ptr [rsp+88h+var_60], rbx
0x140027b0d  mov     rcx, [rcx+40h]
0x140027b11  mov     qword ptr [rsp+88h+var_68], rax
0x140027b16  call    WPP_RECORDER_SF_qDL
0x140027b1b  jmp     loc_140027973
0x140027b20  mov     r9d, [rsp+88h+arg_0]
0x140027b28  jmp     loc_1400279DA
0x140027b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b34  cmp     byte ptr [rcx+29h], 5
0x140027b38  jnb     short loc_140027B45
0x140027b3a  cmp     [rcx+48h], r12w
0x140027b3f  jz      loc_140027945
0x140027b45  mov     rcx, [rcx+40h]
0x140027b49  mov     r9d, 0F4h
0x140027b4f  mov     qword ptr [rsp+88h+var_68], rdx
0x140027b54  mov     r8d, r13d
0x140027b57  mov     dl, 5
0x140027b59  call    WPP_RECORDER_SF_
0x140027b5e  lea     rdx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027b65  jmp     loc_140027945
0x140027b6a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027b71  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027b78  jnz     loc_140027C3E
0x140027b7e  mov     rax, [rdi]
0x140027b81  mov     edx, r13d
0x140027b84  mov     rcx, rdi
0x140027b87  mov     rax, [rax+28h]
0x140027b8b  call    _guard_dispatch_icall
0x140027b90  jmp     loc_140027A54
0x140027b95  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140027b9c  jz      loc_140027A87
0x140027ba2  movzx   eax, word ptr [rbx+64h]
0x140027ba6  mov     r9d, 0F5h
0x140027bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140027bb3  mov     dword ptr [rsp+88h+var_58], eax
0x140027bb7  mov     qword ptr [rsp+88h+var_60], rbx
0x140027bbc  mov     qword ptr [rsp+88h+var_68], rdx
0x140027bc1  mov     dl, 4
0x140027bc3  mov     rcx, [rcx+40h]
0x140027bc7  call    WPP_RECORDER_SF_qD
0x140027bcc  jmp     loc_140027A5B
0x140027bd1  cmp     ebp, r13d
0x140027bd4  jnz     short loc_140027BF7
0x140027bd6  cmp     [rbx+68h], r13d
0x140027bda  jnz     short loc_140027BF7
0x140027bdc  mov     r9d, [rsp+88h+arg_20]; enum _WDI_ROAM_CONFIGURATION_FLAGS
0x140027be4  mov     r8d, r13d; enum _WFC_ROAM_CONNECT_TRIGGER
0x140027be7  mov     edx, r15d; enum _WDI_ASSOC_STATUS
0x140027bea  mov     rcx, rbx; this
0x140027bed  call    ?ConfigureRoamAtResumeForAssociationLossInPowerTransition@CPort@@QEAAHW4_WDI_ASSOC_STATUS@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CPort::ConfigureRoamAtResumeForAssociationLossInPowerTransition(_WDI_ASSOC_STATUS,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ROAM_CONFIGURATION_FLAGS)
0x140027bf2  jmp     loc_140027A5B
0x140027bf7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140027bfe  jz      loc_140027A87
0x140027c04  movzx   eax, word ptr [rbx+64h]
0x140027c08  mov     r9d, 0F6h
0x140027c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c15  mov     dl, 4
0x140027c17  mov     [rsp+88h+var_50], ebp
0x140027c1b  mov     dword ptr [rsp+88h+var_58], eax
0x140027c1f  mov     qword ptr [rsp+88h+var_60], rbx
0x140027c24  lea     rbx, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027c2b  mov     rcx, [rcx+40h]
0x140027c2f  mov     qword ptr [rsp+88h+var_68], rbx
0x140027c34  call    WPP_RECORDER_SF_qDL
0x140027c39  jmp     loc_140027A62
0x140027c3e  movzx   ecx, word ptr [rbx+64h]
0x140027c42  mov     r9d, 0F9h
0x140027c48  mov     dword ptr [rsp+88h+var_58], ecx
0x140027c4c  jmp     short loc_140027C70
0x140027c4e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027c55  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027c5c  jz      loc_140027B7E
0x140027c62  movzx   eax, word ptr [rbx+64h]
0x140027c66  mov     r9d, 0FAh
0x140027c6c  mov     dword ptr [rsp+88h+var_58], eax
0x140027c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140027c77  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140027c7e  mov     qword ptr [rsp+88h+var_60], rbx
0x140027c83  mov     dl, 2
0x140027c85  mov     qword ptr [rsp+88h+var_68], rax
0x140027c8a  mov     rcx, [rcx+40h]
0x140027c8e  call    WPP_RECORDER_SF_qD
0x140027c93  jmp     loc_140027B7E
0x140027c98  mov     rcx, [rcx+40h]
0x140027c9c  mov     r9d, 0FBh
0x140027ca2  mov     [rsp+88h+var_60], esi
0x140027ca6  mov     r8d, r13d
0x140027ca9  mov     dl, 5
0x140027cab  mov     qword ptr [rsp+88h+var_68], rbx
0x140027cb0  call    WPP_RECORDER_SF_D
0x140027cb5  jmp     loc_140027A87
```
