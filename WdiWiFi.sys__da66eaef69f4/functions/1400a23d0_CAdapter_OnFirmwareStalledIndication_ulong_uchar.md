# CAdapter::OnFirmwareStalledIndication(ulong,uchar *)

- ea: `0x1400a23d0`
- end: `0x1400a25c4`
- name: `?OnFirmwareStalledIndication@CAdapter@@AEAAXKPEAE@Z`
- size: `500`
- prototype: `void __fastcall(CAdapter *this, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004a2a0`

## callees

- `0x140013000`
- `0x140034e04`
- `0x140034ec4`
- `0x140049ed8`
- `0x1400a14f0`
- `0x1400a23d0`
- `0x1400a29d0`
- `0x1400a3cb8`
- `0x1400a3f30`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x1400a2475`
- `NDIS!NdisWriteErrorLogEntry` at `0x1400a2475`

## pseudocode

```c
void __fastcall CAdapter::OnFirmwareStalledIndication(CAdapter *this, __int64 a2, unsigned __int8 *a3)
{
  unsigned int v4; // esi
  DeviceCommand *m_pActiveDeviceCommand; // rdi
  CAdapterPropertyCache *v6; // rax
  char PropertyBooleanOrDefault; // bp
  int v8; // r9d
  char v9; // dl
  int v10; // edx
  struct CJobBase *m_pParentJob; // r9
  unsigned int v12; // [rsp+88h] [rbp+10h] BYREF

  v4 = 0;
  v12 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      123,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  m_pActiveDeviceCommand = this->m_CommandScheduler.m_pActiveDeviceCommand;
  if ( m_pActiveDeviceCommand )
  {
    DeviceCommand::get_CommandType(this->m_CommandScheduler.m_pActiveDeviceCommand, &v12);
    v4 = v12;
  }
  NdisWriteErrorLogEntry(this->m_MiniportAdapterHandle, 0xC000138A, 2u);
  _InterlockedAdd(&this->m_lResetTriggerCount, 1u);
  v6 = this->GetAdapterPropertyCache(&this->IPropertyCacheDirectory);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v6, 0x14u, 0);
  CAdapter::TraceLoggingResetRecovery(
    this,
    4u,
    v4,
    this->m_lResetTriggerCount,
    this->m_OemPLDRSupported,
    PropertyBooleanOrDefault);
  if ( _InterlockedIncrement(&this->m_lResetRecovery) <= 1 )
  {
    if ( m_pActiveDeviceCommand )
    {
      CAdapter::TriggerControlPathDiagnostics(this, 4u, v4);
      m_pParentJob = 0;
      if ( v4 != 75 )
        m_pParentJob = m_pActiveDeviceCommand->m_pParentJob;
      CAdapter::CollectDebugData(this, m_pActiveDeviceCommand, 0, m_pParentJob);
    }
    else
    {
      CAdapter::TriggerControlPathDiagnostics(this, 4u, 0);
    }
    if ( this->m_OemPLDRSupported )
    {
      if ( !PropertyBooleanOrDefault )
        CAdapter::ReenumerateFailedAdapter(this);
      goto LABEL_21;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    v8 = 125;
    v9 = 2;
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    v8 = 124;
    v9 = 4;
  }
  WPP_RECORDER_SF_(
    WPP_GLOBAL_Control->DeviceExtension,
    v9,
    1,
    v8,
    (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
LABEL_21:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      126,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      0);
  }
}

```

## disassembly

```asm
0x1400a23d0  mov     rax, rsp
0x1400a23d3  mov     [rax+10h], edx
0x1400a23d6  push    rbx
0x1400a23d7  push    rbp
0x1400a23d8  push    rsi
0x1400a23d9  push    rdi
0x1400a23da  push    r12
0x1400a23dc  push    r13
0x1400a23de  push    r14
0x1400a23e0  push    r15
0x1400a23e2  sub     rsp, 38h
0x1400a23e6  xor     r14d, r14d
0x1400a23e9  mov     rbx, rcx
0x1400a23ec  mov     esi, r14d
0x1400a23ef  mov     [rax+10h], r14d
0x1400a23f3  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a23fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400a2401  lea     r13, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a2408  lea     r15d, [r14+1]
0x1400a240c  jz      short loc_1400A243B
0x1400a240e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2415  cmp     byte ptr [rcx+29h], 5
0x1400a2419  jnb     short loc_1400A2422
0x1400a241b  cmp     [rcx+48h], r14w
0x1400a2420  jz      short loc_1400A243B
0x1400a2422  mov     rcx, [rcx+40h]
0x1400a2426  mov     r9d, 7Bh ; '{'
0x1400a242c  mov     r8d, r15d
0x1400a242f  mov     qword ptr [rsp+78h+var_58], r13
0x1400a2434  mov     dl, 5
0x1400a2436  call    WPP_RECORDER_SF_
0x1400a243b  mov     rdi, [rbx+4B8h]
0x1400a2442  test    rdi, rdi
0x1400a2445  jz      short loc_1400A245E
0x1400a2447  lea     rdx, [rsp+78h+arg_8]; unsigned int *
0x1400a244f  mov     rcx, rdi; this
0x1400a2452  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400a2457  mov     esi, [rsp+78h+arg_8]
0x1400a245e  mov     rcx, [rbx+58h]; NdisAdapterHandle
0x1400a2462  mov     r9d, 4
0x1400a2468  mov     edx, 0C000138Ah; ErrorCode
0x1400a246d  mov     [rsp+78h+var_58], esi
0x1400a2471  lea     r8d, [r9-2]; NumberOfErrorValues
0x1400a2475  call    cs:__imp_NdisWriteErrorLogEntry
0x1400a247c  nop     dword ptr [rax+rax+00h]
0x1400a2481  lock add [rbx+15C4h], r15d
0x1400a2489  lea     rcx, [rbx+8]
0x1400a248d  mov     rax, [rcx]
0x1400a2490  mov     rax, [rax+8]
0x1400a2494  call    _guard_dispatch_icall
0x1400a2499  xor     r8d, r8d; unsigned __int8
0x1400a249c  mov     rcx, rax; this
0x1400a249f  lea     edx, [r8+14h]; unsigned int
0x1400a24a3  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a24a8  mov     ecx, [rbx+15D4h]
0x1400a24ae  mov     r8d, esi; unsigned int
0x1400a24b1  mov     r9d, [rbx+15C4h]; unsigned int
0x1400a24b8  mov     edx, 4; unsigned int
0x1400a24bd  mov     [rsp+78h+var_50], al; char
0x1400a24c1  mov     bpl, al
0x1400a24c4  mov     [rsp+78h+var_58], ecx; unsigned int
0x1400a24c8  mov     rcx, rbx; this
0x1400a24cb  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x1400a24d0  mov     ecx, r15d
0x1400a24d3  lock xadd [rbx+15C8h], ecx
0x1400a24db  add     ecx, r15d
0x1400a24de  cmp     ecx, r15d
0x1400a24e1  jle     short loc_1400A2512
0x1400a24e3  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a24ea  jz      loc_1400A25B2
0x1400a24f0  mov     r9d, 7Ch ; '|'
0x1400a24f6  mov     dl, 4
0x1400a24f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a24ff  mov     r8d, r15d
0x1400a2502  mov     qword ptr [rsp+78h+var_58], r13
0x1400a2507  mov     rcx, [rcx+40h]
0x1400a250b  call    WPP_RECORDER_SF_
0x1400a2510  jmp     short loc_1400A2577
0x1400a2512  mov     edx, 4; unsigned int
0x1400a2517  mov     rcx, rbx; this
0x1400a251a  test    rdi, rdi
0x1400a251d  jz      short loc_1400A2546
0x1400a251f  mov     r8d, esi; unsigned int
0x1400a2522  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a2527  mov     r9, r14
0x1400a252a  cmp     esi, 4Bh ; 'K'
0x1400a252d  jz      short loc_1400A2536
0x1400a252f  mov     r9, [rdi+0A8h]; struct CJobBase *
0x1400a2536  xor     r8d, r8d; struct Task *
0x1400a2539  mov     rdx, rdi; struct DeviceCommand *
0x1400a253c  mov     rcx, rbx; this
0x1400a253f  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x1400a2544  jmp     short loc_1400A254E
0x1400a2546  xor     r8d, r8d; unsigned int
0x1400a2549  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a254e  cmp     [rbx+15D4h], r14d
0x1400a2555  jnz     short loc_1400A256A
0x1400a2557  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a255e  jz      short loc_1400A25B2
0x1400a2560  mov     r9d, 7Dh ; '}'
0x1400a2566  mov     dl, 2
0x1400a2568  jmp     short loc_1400A24F8
0x1400a256a  test    bpl, bpl
0x1400a256d  jnz     short loc_1400A2577
0x1400a256f  mov     rcx, rbx; this
0x1400a2572  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400a2577  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400a257e  jz      short loc_1400A25B2
0x1400a2580  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2587  cmp     byte ptr [rcx+29h], 5
0x1400a258b  jnb     short loc_1400A2594
0x1400a258d  cmp     [rcx+48h], r14w
0x1400a2592  jz      short loc_1400A25B2
0x1400a2594  mov     rcx, [rcx+40h]
0x1400a2598  mov     r9d, 7Eh ; '~'
0x1400a259e  mov     dword ptr [rsp+78h+var_50], r14d
0x1400a25a3  mov     r8d, r15d
0x1400a25a6  mov     dl, 5
0x1400a25a8  mov     qword ptr [rsp+78h+var_58], r13
0x1400a25ad  call    WPP_RECORDER_SF_D
0x1400a25b2  add     rsp, 38h
0x1400a25b6  pop     r15
0x1400a25b8  pop     r14
0x1400a25ba  pop     r13
0x1400a25bc  pop     r12
0x1400a25be  pop     rdi
0x1400a25bf  pop     rsi
0x1400a25c0  pop     rbp
0x1400a25c1  pop     rbx
0x1400a25c2  retn
```
