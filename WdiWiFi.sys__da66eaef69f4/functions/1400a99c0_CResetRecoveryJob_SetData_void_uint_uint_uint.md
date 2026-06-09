# CResetRecoveryJob::SetData(void *,uint,uint *,uint *)

- ea: `0x1400a99c0`
- end: `0x1400a9c6c`
- name: `?SetData@CResetRecoveryJob@@UEAAHPEAXIPEAI1@Z`
- size: `684`
- prototype: `__int64 __fastcall(CResetRecoveryJob *__hidden this, void *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400122e0`
- `0x140013000`
- `0x140034e04`
- `0x140034ec4`
- `0x140049ed8`
- `0x1400a14f0`
- `0x1400a29d0`
- `0x1400a3cb8`
- `0x1400a3f30`
- `0x1400a99c0`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x1400a9a84`
- `NDIS!NdisWriteErrorLogEntry` at `0x1400a9a84`

## pseudocode

```c
__int64 __fastcall CResetRecoveryJob::SetData(
        CResetRecoveryJob *this,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int v6; // esi
  unsigned int *v8; // rax
  CAdapter *m_pAdapter; // rax
  struct DeviceCommand *m_pActiveDeviceCommand; // rbx
  CAdapterPropertyCache *v11; // rax
  char PropertyBooleanOrDefault; // bp
  int v13; // r8d
  signed __int32 v14; // edx
  CAdapter *v15; // rcx
  unsigned int v16; // edx
  unsigned int v17; // ebx
  int v18; // edx
  CAdapter *v19; // rcx
  char v21[8]; // [rsp+28h] [rbp-60h]
  unsigned int v22; // [rsp+90h] [rbp+8h] BYREF

  v6 = 0;
  v22 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      257,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
  }
  v8 = a5;
  *a4 = 8;
  *v8 = 8;
  m_pAdapter = this->m_pAdapter;
  m_pActiveDeviceCommand = m_pAdapter->m_CommandScheduler.m_pActiveDeviceCommand;
  if ( m_pActiveDeviceCommand )
  {
    DeviceCommand::get_CommandType(m_pAdapter->m_CommandScheduler.m_pActiveDeviceCommand, &v22);
    v6 = v22;
  }
  NdisWriteErrorLogEntry(this->m_pAdapter->m_MiniportAdapterHandle, 0xC000138A, 2u);
  _InterlockedAdd(&this->m_pAdapter->m_lResetTriggerCount, 1u);
  v11 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v11, 0x14u, 0);
  CAdapter::TraceLoggingResetRecovery(
    this->m_pAdapter,
    3u,
    v6,
    this->m_pAdapter->m_lResetTriggerCount,
    this->m_pAdapter->m_OemPLDRSupported,
    PropertyBooleanOrDefault);
  v14 = _InterlockedExchangeAdd(&this->m_pAdapter->m_lResetRecovery, 1u);
  v15 = this->m_pAdapter;
  v16 = v14 + 1;
  if ( v16 <= 1 )
  {
    if ( m_pActiveDeviceCommand )
    {
      CAdapter::TriggerControlPathDiagnostics(v15, 3u, v6);
      CAdapter::CollectDebugData(this->m_pAdapter, m_pActiveDeviceCommand, 0, m_pActiveDeviceCommand->m_pParentJob);
    }
    else
    {
      CAdapter::TriggerControlPathDiagnostics(v15, 3u, 0);
    }
    v19 = this->m_pAdapter;
    if ( v19->m_OemPLDRSupported )
    {
      if ( PropertyBooleanOrDefault )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            1,
            260,
            (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
        v17 = -1073676276;
      }
      else
      {
        v17 = 0;
        CAdapter::ReenumerateFailedAdapter(v19);
      }
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          259,
          (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids);
      v17 = -1073741637;
    }
    goto LABEL_25;
  }
  if ( v15->m_OemPLDRSupported )
    v17 = PropertyBooleanOrDefault != 0 ? 0xC001000C : 0;
  else
    v17 = -1073741637;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      v13,
      258,
      (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v17);
LABEL_25:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      *(_DWORD *)v21 = v17;
      LOBYTE(v18) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        1,
        261,
        (__int64)WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids,
        *(_QWORD *)v21);
    }
  }
  return v17;
}

```

## disassembly

```asm
0x1400a99c0  mov     rax, rsp
0x1400a99c3  push    rbx
0x1400a99c4  push    rbp
0x1400a99c5  push    rsi
0x1400a99c6  push    rdi
0x1400a99c7  push    r12
0x1400a99c9  push    r13
0x1400a99cb  push    r14
0x1400a99cd  push    r15
0x1400a99cf  sub     rsp, 48h
0x1400a99d3  xor     r14d, r14d
0x1400a99d6  mov     rbx, r9
0x1400a99d9  mov     esi, r14d
0x1400a99dc  mov     [rax+8], r14d
0x1400a99e0  mov     rdi, rcx
0x1400a99e3  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a99ea  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400a99f1  lea     r12, WPP_8d6574c180af3f8bf64eff8be1ffb4e5_Traceguids
0x1400a99f8  lea     r13d, [r14+1]
0x1400a99fc  jz      short loc_1400A9A2B
0x1400a99fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9a05  cmp     byte ptr [rcx+29h], 5
0x1400a9a09  jnb     short loc_1400A9A12
0x1400a9a0b  cmp     [rcx+48h], r14w
0x1400a9a10  jz      short loc_1400A9A2B
0x1400a9a12  mov     rcx, [rcx+40h]
0x1400a9a16  mov     r9d, 101h
0x1400a9a1c  mov     r8d, r13d
0x1400a9a1f  mov     qword ptr [rsp+88h+var_68], r12
0x1400a9a24  mov     dl, 5
0x1400a9a26  call    WPP_RECORDER_SF_
0x1400a9a2b  mov     rax, [rsp+88h+arg_20]
0x1400a9a33  mov     ecx, 8
0x1400a9a38  mov     [rbx], ecx
0x1400a9a3a  mov     [rax], ecx
0x1400a9a3c  mov     rax, [rdi+200h]
0x1400a9a43  mov     rbx, [rax+4B8h]
0x1400a9a4a  test    rbx, rbx
0x1400a9a4d  jz      short loc_1400A9A66
0x1400a9a4f  lea     rdx, [rsp+88h+arg_0]; unsigned int *
0x1400a9a57  mov     rcx, rbx; this
0x1400a9a5a  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400a9a5f  mov     esi, [rsp+88h+arg_0]
0x1400a9a66  mov     rcx, [rdi+200h]
0x1400a9a6d  mov     r9d, 3
0x1400a9a73  mov     edx, 0C000138Ah; ErrorCode
0x1400a9a78  mov     [rsp+88h+var_68], esi
0x1400a9a7c  mov     rcx, [rcx+58h]; NdisAdapterHandle
0x1400a9a80  lea     r8d, [r9-1]; NumberOfErrorValues
0x1400a9a84  call    cs:__imp_NdisWriteErrorLogEntry
0x1400a9a8b  nop     dword ptr [rax+rax+00h]
0x1400a9a90  mov     rax, [rdi+200h]
0x1400a9a97  lock add [rax+15C4h], r13d
0x1400a9a9f  mov     rcx, [rdi+200h]
0x1400a9aa6  add     rcx, 8
0x1400a9aaa  mov     rax, [rcx]
0x1400a9aad  mov     rax, [rax+8]
0x1400a9ab1  call    _guard_dispatch_icall
0x1400a9ab6  xor     r8d, r8d; unsigned __int8
0x1400a9ab9  mov     rcx, rax; this
0x1400a9abc  lea     edx, [r8+14h]; unsigned int
0x1400a9ac0  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a9ac5  mov     rcx, [rdi+200h]; this
0x1400a9acc  mov     r8d, esi; unsigned int
0x1400a9acf  mov     [rsp+88h+var_60], al; char
0x1400a9ad3  mov     bpl, al
0x1400a9ad6  mov     edx, [rcx+15D4h]
0x1400a9adc  mov     r9d, [rcx+15C4h]; unsigned int
0x1400a9ae3  mov     [rsp+88h+var_68], edx; unsigned int
0x1400a9ae7  mov     edx, 3; unsigned int
0x1400a9aec  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x1400a9af1  mov     rcx, [rdi+200h]
0x1400a9af8  mov     edx, r13d
0x1400a9afb  lock xadd [rcx+15C8h], edx
0x1400a9b03  mov     rcx, [rdi+200h]; this
0x1400a9b0a  add     edx, r13d
0x1400a9b0d  cmp     edx, r13d
0x1400a9b10  jbe     short loc_1400A9B6C
0x1400a9b12  cmp     [rcx+15D4h], r14d
0x1400a9b19  jnz     short loc_1400A9B22
0x1400a9b1b  mov     ebx, 0C00000BBh
0x1400a9b20  jmp     short loc_1400A9B2D
0x1400a9b22  neg     bpl
0x1400a9b25  sbb     ebx, ebx
0x1400a9b27  and     ebx, 0C001000Ch
0x1400a9b2d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a9b34  jz      loc_1400A9C58
0x1400a9b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9b41  mov     r9d, 102h
0x1400a9b47  mov     eax, [rdi+10h]
0x1400a9b4a  mov     dl, 4
0x1400a9b4c  mov     [rsp+88h+var_50], ebx
0x1400a9b50  mov     [rsp+88h+var_58], eax
0x1400a9b54  mov     rcx, [rcx+40h]
0x1400a9b58  mov     qword ptr [rsp+88h+var_60], rdi
0x1400a9b5d  mov     qword ptr [rsp+88h+var_68], r12
0x1400a9b62  call    WPP_RECORDER_SF_qDD
0x1400a9b67  jmp     loc_1400A9C1E
0x1400a9b6c  mov     edx, 3; unsigned int
0x1400a9b71  test    rbx, rbx
0x1400a9b74  jz      short loc_1400A9B99
0x1400a9b76  mov     r8d, esi; unsigned int
0x1400a9b79  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a9b7e  mov     r9, [rbx+0A8h]; struct CJobBase *
0x1400a9b85  xor     r8d, r8d; struct Task *
0x1400a9b88  mov     rcx, [rdi+200h]; this
0x1400a9b8f  mov     rdx, rbx; struct DeviceCommand *
0x1400a9b92  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x1400a9b97  jmp     short loc_1400A9BA1
0x1400a9b99  xor     r8d, r8d; unsigned int
0x1400a9b9c  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a9ba1  mov     rcx, [rdi+200h]; this
0x1400a9ba8  cmp     [rcx+15D4h], r14d
0x1400a9baf  jnz     short loc_1400A9BE1
0x1400a9bb1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a9bb8  jz      short loc_1400A9BDA
0x1400a9bba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9bc1  mov     r9d, 103h
0x1400a9bc7  mov     r8d, r13d
0x1400a9bca  mov     qword ptr [rsp+88h+var_68], r12
0x1400a9bcf  mov     dl, 2
0x1400a9bd1  mov     rcx, [rcx+40h]
0x1400a9bd5  call    WPP_RECORDER_SF_
0x1400a9bda  mov     ebx, 0C00000BBh
0x1400a9bdf  jmp     short loc_1400A9C1E
0x1400a9be1  test    bpl, bpl
0x1400a9be4  jnz     short loc_1400A9BF0
0x1400a9be6  mov     ebx, r14d
0x1400a9be9  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400a9bee  jmp     short loc_1400A9C1E
0x1400a9bf0  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a9bf7  jz      short loc_1400A9C19
0x1400a9bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9c00  mov     r9d, 104h
0x1400a9c06  mov     r8d, r13d
0x1400a9c09  mov     qword ptr [rsp+88h+var_68], r12
0x1400a9c0e  mov     dl, 2
0x1400a9c10  mov     rcx, [rcx+40h]
0x1400a9c14  call    WPP_RECORDER_SF_
0x1400a9c19  mov     ebx, 0C001000Ch
0x1400a9c1e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a9c25  jz      short loc_1400A9C58
0x1400a9c27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9c2e  cmp     byte ptr [rcx+29h], 5
0x1400a9c32  jnb     short loc_1400A9C3B
0x1400a9c34  cmp     [rcx+48h], r14w
0x1400a9c39  jz      short loc_1400A9C58
0x1400a9c3b  mov     rcx, [rcx+40h]
0x1400a9c3f  mov     r9d, 105h
0x1400a9c45  mov     dword ptr [rsp+88h+var_60], ebx
0x1400a9c49  mov     r8d, r13d
0x1400a9c4c  mov     dl, 5
0x1400a9c4e  mov     qword ptr [rsp+88h+var_68], r12
0x1400a9c53  call    WPP_RECORDER_SF_D
0x1400a9c58  mov     eax, ebx
0x1400a9c5a  add     rsp, 48h
0x1400a9c5e  pop     r15
0x1400a9c60  pop     r14
0x1400a9c62  pop     r13
0x1400a9c64  pop     r12
0x1400a9c66  pop     rdi
0x1400a9c67  pop     rsi
0x1400a9c68  pop     rbp
0x1400a9c69  pop     rbx
0x1400a9c6a  retn
```
