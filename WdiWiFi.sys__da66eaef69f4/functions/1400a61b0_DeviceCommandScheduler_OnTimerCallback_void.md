# DeviceCommandScheduler::OnTimerCallback(void *)

- ea: `0x1400a61b0`
- end: `0x1400a65b1`
- name: `?OnTimerCallback@DeviceCommandScheduler@@UEAAXPEAX@Z`
- size: `1025`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400036a0`
- `0x140012214`
- `0x140013000`
- `0x140034e04`
- `0x140034ec4`
- `0x140049ed8`
- `0x14004c378`
- `0x14004d6a8`
- `0x140069a90`
- `0x1400a14f0`
- `0x1400a29d0`
- `0x1400a3cb8`
- `0x1400a3f30`
- `0x1400a61b0`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x1400a627b`
- `NDIS!NdisWriteErrorLogEntry` at `0x1400a627b`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::OnTimerCallback(DeviceCommandScheduler *this, void *a2, int a3)
{
  int v4; // edx
  unsigned int *p_m_pActiveDeviceCommand; // r14
  CPropertyCache *v6; // rax
  char PropertyBooleanOrDefault; // al
  volatile signed __int32 *pThis; // rcx
  void *v9; // rcx
  int v10; // r9d
  CCtlPlane **p_m_pControlPlane; // rdi
  __int64 v12; // r12
  signed __int32 v13; // esi
  _DWORD *v14; // r15
  DeviceCommand *v15; // rcx
  int v16; // edx
  int v17; // r8d
  DeviceCommand *v18; // rcx
  int v19; // r8d
  unsigned int MessageId; // edx
  CAdapter *v21; // rcx
  unsigned int v22[2]; // [rsp+20h] [rbp-50h]
  char v23[8]; // [rsp+28h] [rbp-48h]
  char v24; // [rsp+28h] [rbp-48h]
  char v25; // [rsp+30h] [rbp-40h]
  struct _WFC_MESSAGE_METADATA v26; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int8 *v29; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      37,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids);
    v4 = 0;
  }
  if ( !this->m_pControlPlane )
    goto LABEL_37;
  p_m_pActiveDeviceCommand = (unsigned int *)&this->m_pActiveDeviceCommand;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      a3,
      38,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
      *p_m_pActiveDeviceCommand,
      *p_m_pActiveDeviceCommand);
  }
  v22[0] = *p_m_pActiveDeviceCommand;
  NdisWriteErrorLogEntry(
    *((NDIS_HANDLE *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis + 11),
    0xC000138A,
    2u,
    1,
    *(_QWORD *)v22);
  v6 = (CPropertyCache *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis
                                                             + 1)
                                                           + 8LL))((char *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis + 8);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v6, 0x14u, 0);
  pThis = (volatile signed __int32 *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis;
  LOBYTE(v27) = PropertyBooleanOrDefault;
  _InterlockedAdd(pThis + 1393, 1u);
  CAdapter::TraceLoggingResetRecovery(
    (CAdapter *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis,
    1u,
    *p_m_pActiveDeviceCommand,
    *((_DWORD *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis + 1393),
    *((_DWORD *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis + 1397),
    PropertyBooleanOrDefault);
  v9 = this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis;
  v4 = 0;
  if ( !*((_DWORD *)v9 + 1397) && *(_QWORD *)(*((_QWORD *)v9 + 13) + 152LL) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    v10 = 39;
LABEL_12:
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      v10,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids);
    v4 = 0;
    goto LABEL_37;
  }
  p_m_pControlPlane = &this->m_pControlPlane;
  v12 = 0;
  if ( *p_m_pActiveDeviceCommand != 75 )
    v12 = *(_QWORD *)&(*p_m_pControlPlane)->m_OidRequest.NdisReserved[40];
  v13 = _InterlockedIncrement((volatile signed __int32 *)v9 + 1394);
  v14 = (_DWORD *)&this->m_pEventQueue + 1;
  if ( v13 == 1 )
  {
    CAdapter::TriggerControlPathDiagnostics(
      (CAdapter *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis,
      1u,
      *p_m_pActiveDeviceCommand);
    CAdapter::CollectDebugData(
      (CAdapter *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis,
      (struct DeviceCommand *)*p_m_pControlPlane,
      0,
      (struct CJobBase *)v12);
    v4 = 0;
LABEL_17:
    if ( *((_DWORD *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis + 1397) )
    {
      if ( *p_m_pActiveDeviceCommand == 75 || v12 && *(_DWORD *)(v12 + 60) != 175 )
      {
        v18 = (DeviceCommand *)*p_m_pControlPlane;
        *((_DWORD *)&v26 + 2) &= 0xFFFFFFF8;
        v28 = 0;
        v29 = 0;
        v26._Command.pOriginalOidRequest = 0;
        v26.MessageType = WfcMessageResponse;
        DeviceCommand::get_InputBuffer(v18, &v28, &v29);
        if ( v29 && v28 >= 0x30 )
        {
          MessageId = *(_DWORD *)v29;
          v26._Command.MappedWdiOid = *((_DWORD *)v29 + 4);
          v26.Message.PortId = *((_WORD *)v29 + 16);
          v26.Message.TransactionId = *((_DWORD *)v29 + 10);
          v26.MessageId = MessageId;
        }
        else
        {
          MessageId = v26.MessageId;
        }
        v26.MessageLength = 48;
        v26._Command.MinimumOutputLength = -1073676280;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v25 = MessageId;
          v24 = MessageId;
          LOBYTE(MessageId) = 4;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            MessageId,
            v19,
            42,
            (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
            v24,
            v25);
        }
        DeviceCommand::get_CommandType((DeviceCommand *)*p_m_pControlPlane, (unsigned int *)&this->m_pEventQueue);
        DeviceCommand::get_CommandToken((DeviceCommand *)*p_m_pControlPlane, (unsigned int *)&this->m_pEventQueue + 1);
        DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(
          (DeviceCommandScheduler *)((char *)this - 16),
          0x30u,
          &v26);
        v4 = 0;
      }
      if ( v13 == 1 )
      {
        v21 = (CAdapter *)this->m_FailsafeLowerLayerCompletionEvent.m_Link.pThis;
        if ( v21->m_IsRecoverable && !(_BYTE)v27 )
        {
          CAdapter::ReenumerateFailedAdapter(v21);
          v4 = 0;
        }
      }
      goto LABEL_37;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    v10 = 41;
    goto LABEL_12;
  }
  if ( !*v14 )
    goto LABEL_17;
  v15 = (DeviceCommand *)*p_m_pControlPlane;
  v27 = 0;
  DeviceCommand::get_CommandType(v15, &v27);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return;
  LOBYTE(v16) = 2;
  WPP_RECORDER_SF_ddd(
    WPP_GLOBAL_Control->DeviceExtension,
    v16,
    v17,
    40,
    (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
    v13,
    v27,
    *v14);
  v4 = 0;
LABEL_37:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    *(_DWORD *)v23 = 0;
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      43,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
      *(_QWORD *)v23);
  }
}

```

## disassembly

```asm
0x1400a61b0  mov     [rsp-38h+arg_8], rbx
0x1400a61b5  push    rbp
0x1400a61b6  push    rsi
0x1400a61b7  push    rdi
0x1400a61b8  push    r12
0x1400a61ba  push    r13
0x1400a61bc  push    r14
0x1400a61be  push    r15
0x1400a61c0  mov     rbp, rsp
0x1400a61c3  sub     rsp, 70h
0x1400a61c7  mov     rbx, rcx
0x1400a61ca  xor     edx, edx; __annotation("TMF:",
0x1400a61cc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a61d3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a61da  lea     rdi, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x1400a61e1  lea     r15d, [rdx+1]
0x1400a61e5  jz      short loc_1400A621C
0x1400a61e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a61ee  cmp     byte ptr [rcx+29h], 5
0x1400a61f2  jnb     short loc_1400A61FA
0x1400a61f4  cmp     [rcx+48h], dx
0x1400a61f8  jz      short loc_1400A621C
0x1400a61fa  mov     rcx, [rcx+40h]
0x1400a61fe  mov     r9d, 25h ; '%'
0x1400a6204  mov     r8d, r15d
0x1400a6207  mov     qword ptr [rsp+70h+var_50], rdi
0x1400a620c  mov     dl, 5
0x1400a620e  call    WPP_RECORDER_SF_
0x1400a6213  xor     edx, edx
0x1400a6215  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a621c  cmp     [rbx+18h], rdx
0x1400a6220  jz      loc_1400A65A8
0x1400a6226  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x1400a622d  lea     r14, [rbx+28h]
0x1400a6231  jz      short loc_1400A625B
0x1400a6233  mov     eax, [r14]
0x1400a6236  mov     r9d, 26h ; '&'
0x1400a623c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6243  mov     dl, 2
0x1400a6245  mov     dword ptr [rsp+70h+var_40], eax
0x1400a6249  mov     dword ptr [rsp+70h+var_48], eax
0x1400a624d  mov     qword ptr [rsp+70h+var_50], rdi
0x1400a6252  mov     rcx, [rcx+40h]
0x1400a6256  call    WPP_RECORDER_SF_Ld
0x1400a625b  mov     rcx, [rbx+0A0h]
0x1400a6262  mov     r9d, r15d
0x1400a6265  mov     eax, [r14]
0x1400a6268  mov     edx, 0C000138Ah; ErrorCode
0x1400a626d  mov     r8d, 2; NumberOfErrorValues
0x1400a6273  mov     [rsp+70h+var_50], eax
0x1400a6277  mov     rcx, [rcx+58h]; NdisAdapterHandle
0x1400a627b  call    cs:__imp_NdisWriteErrorLogEntry
0x1400a6282  nop     dword ptr [rax+rax+00h]
0x1400a6287  mov     rcx, [rbx+0A0h]
0x1400a628e  add     rcx, 8
0x1400a6292  mov     rax, [rcx]
0x1400a6295  mov     rax, [rax+8]
0x1400a6299  call    _guard_dispatch_icall
0x1400a629e  xor     r8d, r8d; unsigned __int8
0x1400a62a1  mov     rcx, rax; this
0x1400a62a4  lea     edx, [r8+14h]; unsigned int
0x1400a62a8  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a62ad  mov     rcx, [rbx+0A0h]
0x1400a62b4  mov     byte ptr [rbp+arg_0], al
0x1400a62b7  lock add [rcx+15C4h], r15d
0x1400a62bf  mov     rcx, [rbx+0A0h]; this
0x1400a62c6  mov     r8d, [r14]; unsigned int
0x1400a62c9  mov     [rsp+70h+var_48], al; char
0x1400a62cd  mov     edx, [rcx+15D4h]
0x1400a62d3  mov     r9d, [rcx+15C4h]; unsigned int
0x1400a62da  mov     [rsp+70h+var_50], edx; unsigned int
0x1400a62de  mov     edx, r15d; unsigned int
0x1400a62e1  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x1400a62e6  mov     rcx, [rbx+0A0h]
0x1400a62ed  xor     edx, edx
0x1400a62ef  cmp     [rcx+15D4h], edx
0x1400a62f5  jnz     short loc_1400A633D
0x1400a62f7  mov     rax, [rcx+68h]
0x1400a62fb  cmp     [rax+98h], rdx
0x1400a6302  jz      short loc_1400A633D
0x1400a6304  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a630b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400a6312  jz      loc_1400A658F
0x1400a6318  lea     r9d, [rdx+27h]
0x1400a631c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6323  mov     r8d, r15d
0x1400a6326  mov     dl, 2
0x1400a6328  mov     qword ptr [rsp+70h+var_50], rdi
0x1400a632d  mov     rcx, [rcx+40h]
0x1400a6331  call    WPP_RECORDER_SF_
0x1400a6336  xor     edx, edx
0x1400a6338  jmp     loc_1400A6556
0x1400a633d  cmp     dword ptr [r14], 4Bh ; 'K'
0x1400a6341  lea     rdi, [rbx+18h]
0x1400a6345  mov     r12, rdx
0x1400a6348  jz      short loc_1400A6354
0x1400a634a  mov     rax, [rdi]
0x1400a634d  mov     r12, [rax+0A8h]
0x1400a6354  mov     esi, r15d
0x1400a6357  lock xadd [rcx+15C8h], esi
0x1400a635f  add     esi, r15d
0x1400a6362  lea     r15, [rbx+24h]
0x1400a6366  cmp     esi, 1
0x1400a6369  jnz     short loc_1400A63D0
0x1400a636b  mov     r8d, [r14]; unsigned int
0x1400a636e  mov     edx, esi; unsigned int
0x1400a6370  mov     rcx, [rbx+0A0h]; this
0x1400a6377  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a637c  mov     rdx, [rdi]; struct DeviceCommand *
0x1400a637f  mov     r9, r12; struct CJobBase *
0x1400a6382  mov     rcx, [rbx+0A0h]; this
0x1400a6389  xor     r8d, r8d; struct Task *
0x1400a638c  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x1400a6391  xor     edx, edx
0x1400a6393  mov     rax, [rbx+0A0h]
0x1400a639a  cmp     [rax+15D4h], edx
0x1400a63a0  jnz     loc_1400A6439
0x1400a63a6  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a63ad  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400a63b4  jz      loc_1400A658F
0x1400a63ba  mov     r9d, 29h ; ')'
0x1400a63c0  lea     rdi, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x1400a63c7  lea     r15d, [r9-28h]
0x1400a63cb  jmp     loc_1400A631C
0x1400a63d0  cmp     [r15], edx
0x1400a63d3  jz      short loc_1400A6393
0x1400a63d5  mov     rcx, [rdi]; this
0x1400a63d8  mov     [rbp+arg_0], edx
0x1400a63db  lea     rdx, [rbp+arg_0]; unsigned int *
0x1400a63df  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400a63e4  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a63eb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400a63f2  jz      loc_1400A658F
0x1400a63f8  mov     eax, [r15]
0x1400a63fb  lea     rdi, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x1400a6402  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6409  mov     r9d, 28h ; '('
0x1400a640f  mov     [rsp+70h+var_38], eax
0x1400a6413  mov     dl, 2
0x1400a6415  mov     eax, [rbp+arg_0]
0x1400a6418  mov     dword ptr [rsp+70h+var_40], eax
0x1400a641c  mov     rcx, [rcx+40h]
0x1400a6420  mov     dword ptr [rsp+70h+var_48], esi
0x1400a6424  mov     qword ptr [rsp+70h+var_50], rdi
0x1400a6429  call    WPP_RECORDER_SF_ddd
0x1400a642e  xor     edx, edx
0x1400a6430  lea     r15d, [rdx+1]
0x1400a6434  jmp     loc_1400A6556
0x1400a6439  cmp     dword ptr [r14], 4Bh ; 'K'
0x1400a643d  jz      short loc_1400A6457
0x1400a643f  test    r12, r12
0x1400a6442  jz      loc_1400A6522
0x1400a6448  cmp     dword ptr [r12+3Ch], 0AFh
0x1400a6451  jz      loc_1400A6522
0x1400a6457  mov     rcx, [rdi]; this
0x1400a645a  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x1400a645e  and     dword ptr [rbp+var_30.UseDirectOidCall], 0FFFFFFF8h
0x1400a6462  mov     [rbp+arg_10], edx
0x1400a6465  mov     [rbp+arg_18], rdx
0x1400a6469  mov     qword ptr [rbp+var_30.___u6+8], rdx
0x1400a646d  lea     rdx, [rbp+arg_10]; unsigned int *
0x1400a6471  mov     [rbp+var_30.MessageType], 3
0x1400a6478  call    ?get_InputBuffer@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_InputBuffer(ulong *,uchar * *)
0x1400a647d  mov     rcx, [rbp+arg_18]
0x1400a6481  mov     r12d, 30h ; '0'
0x1400a6487  test    rcx, rcx
0x1400a648a  jz      short loc_1400A64AD
0x1400a648c  cmp     [rbp+arg_10], r12d
0x1400a6490  jb      short loc_1400A64AD
0x1400a6492  mov     eax, [rcx+10h]
0x1400a6495  mov     edx, [rcx]
0x1400a6497  mov     dword ptr [rbp+var_30.___u6], eax
0x1400a649a  movzx   eax, word ptr [rcx+20h]
0x1400a649e  mov     [rbp+var_30.Message.PortId], ax
0x1400a64a2  mov     eax, [rcx+28h]
0x1400a64a5  mov     [rbp+var_30.Message.TransactionId], eax
0x1400a64a8  mov     [rbp+var_30.MessageId], edx
0x1400a64ab  jmp     short loc_1400A64B0
0x1400a64ad  mov     edx, [rbp+var_30.MessageId]
0x1400a64b0  mov     [rbp+var_30.MessageLength], r12d
0x1400a64b4  mov     dword ptr [rbp+var_30.___u6+4], 0C0010008h
0x1400a64bb  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a64c2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400a64c9  jz      short loc_1400A64F7
0x1400a64cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a64d2  lea     rax, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x1400a64d9  mov     dword ptr [rsp+70h+var_40], edx
0x1400a64dd  mov     r9d, 2Ah ; '*'
0x1400a64e3  mov     dword ptr [rsp+70h+var_48], edx
0x1400a64e7  mov     dl, 4
0x1400a64e9  mov     qword ptr [rsp+70h+var_50], rax
0x1400a64ee  mov     rcx, [rcx+40h]
0x1400a64f2  call    WPP_RECORDER_SF_Ld
0x1400a64f7  mov     rcx, [rdi]; this
0x1400a64fa  lea     rdx, [rbx+20h]; unsigned int *
0x1400a64fe  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400a6503  mov     rcx, [rdi]; this
0x1400a6506  mov     rdx, r15; unsigned int *
0x1400a6509  call    ?get_CommandToken@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandToken(ulong *)
0x1400a650e  lea     r8, [rbp+var_30]; struct _WFC_MESSAGE_METADATA *
0x1400a6512  mov     edx, r12d; unsigned int
0x1400a6515  lea     rcx, [rbx-10h]; this
0x1400a6519  call    ?CompleteSendCommand_PostHangCheck@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@@Z; DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(ulong,_WFC_MESSAGE_METADATA *)
0x1400a651e  xor     edx, edx
0x1400a6520  jmp     short loc_1400A6529
0x1400a6522  lea     r14, WPP_RECORDER_INITIALIZED
0x1400a6529  mov     r15d, 1
0x1400a652f  cmp     esi, r15d
0x1400a6532  jnz     short loc_1400A654F
0x1400a6534  mov     rcx, [rbx+0A0h]; this
0x1400a653b  cmp     [rcx+12F5h], dl
0x1400a6541  jz      short loc_1400A654F
0x1400a6543  cmp     byte ptr [rbp+arg_0], dl
0x1400a6546  jnz     short loc_1400A654F
0x1400a6548  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400a654d  xor     edx, edx
0x1400a654f  lea     rdi, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x1400a6556  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a655d  jz      short loc_1400A658F
0x1400a655f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6566  cmp     byte ptr [rcx+29h], 5
0x1400a656a  jnb     short loc_1400A6572
0x1400a656c  cmp     [rcx+48h], dx
0x1400a6570  jz      short loc_1400A658F
0x1400a6572  mov     rcx, [rcx+40h]
0x1400a6576  mov     r9d, 2Bh ; '+'
0x1400a657c  mov     dword ptr [rsp+70h+var_48], edx
0x1400a6580  mov     r8d, r15d
0x1400a6583  mov     dl, 5
0x1400a6585  mov     qword ptr [rsp+70h+var_50], rdi
0x1400a658a  call    WPP_RECORDER_SF_D
0x1400a658f  mov     rbx, [rsp+70h+arg_8]
0x1400a6597  add     rsp, 70h
0x1400a659b  pop     r15
0x1400a659d  pop     r14
0x1400a659f  pop     r13
0x1400a65a1  pop     r12
0x1400a65a3  pop     rdi
0x1400a65a4  pop     rsi
0x1400a65a5  pop     rbp
0x1400a65a6  retn
0x1400a65a8  lea     r14, WPP_RECORDER_INITIALIZED
0x1400a65af  jmp     short loc_1400A6556
```
