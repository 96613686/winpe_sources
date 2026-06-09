# Task::OnTimerCallback(void *)

- ea: `0x1400a6600`
- end: `0x1400a6991`
- name: `?OnTimerCallback@Task@@UEAAXPEAX@Z`
- size: `913`
- prototype: `void __fastcall(Task *__hidden this, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400014b8`
- `0x140013000`
- `0x1400297a0`
- `0x14002aa28`
- `0x14002ace4`
- `0x140034e04`
- `0x140034ec4`
- `0x140049ed8`
- `0x14004d594`
- `0x14007e5dc`
- `0x140082ff8`
- `0x1400a14f0`
- `0x1400a29d0`
- `0x1400a3cb8`
- `0x1400a3f30`
- `0x1400a6600`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x1400a66fa`
- `NDIS!NdisWriteErrorLogEntry` at `0x1400a66fa`

## pseudocode

```c
void __fastcall Task::OnTimerCallback(Task *this, void *a2)
{
  Task *v3; // r14
  CAdapter *v4; // rbx
  int v5; // edx
  int v6; // r8d
  IEventQueueCallback *v7; // rsi
  unsigned int v8; // r12d
  __int64 v9; // rcx
  CPropertyCache *v10; // rax
  __int64 v11; // r8
  unsigned int m_OemPLDRSupported; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  IEventQueueCallback *v16; // r15
  int v17; // edx
  int v18; // r8d
  int v19; // eax
  int v20; // r9d
  int v21; // edx
  char v22[8]; // [rsp+28h] [rbp-38h]
  int m_lResetTriggerCount; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-Ch] BYREF
  const char *v25; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+40h] BYREF
  bool v27; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 v28; // [rsp+B8h] [rbp+58h] BYREF

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      55,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids);
  }
  v3 = (Task *)((char *)this - 24);
  v26 = 0;
  v4 = *(CAdapter **)&this->m_TaskDeviceCommand.m_pParentJob->m_FailsafeJobStartedEvent.m_EventStatus;
  DeviceCommand::get_CommandType((DeviceCommand *)&this->IActivityId, &v26);
  v28 = 0;
  DeviceCommand::get_PortId((DeviceCommand *)&this->IActivityId, &v28);
  v7 = &this->IEventQueueCallback;
  v8 = v26;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      56,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (_BYTE)this - 24,
      (char)v7->__vftable,
      v26,
      v26);
  }
  NdisWriteErrorLogEntry(v4->m_MiniportAdapterHandle, 0xC000138A, 2u);
  v9 = *(_QWORD *)&this->m_TaskDeviceCommand.m_pParentJob->m_FailsafeJobStartedEvent.m_EventStatus + 8LL;
  v10 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  LOBYTE(v11) = CPropertyCache::GetPropertyBooleanOrDefault(v10, 0x14u, 0);
  LOBYTE(v26) = v11;
  _InterlockedIncrement(&v4->m_lResetTriggerCount);
  if ( (unsigned int)dword_1400F8790 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400F8790, 5, v11) )
  {
    m_lResetTriggerCount = v4->m_lResetTriggerCount;
    m_OemPLDRSupported = v4->m_OemPLDRSupported;
    v27 = (_BYTE)v11 == 0;
    v24 = m_OemPLDRSupported;
    v25 = WDI_TLV::stringify::ToLogString(v8);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_1400EF26D,
      v14,
      v15,
      (__int64)&v25,
      (__int64)&v28,
      (__int64)&v24,
      (__int64)&v27,
      (__int64)&m_lResetTriggerCount);
    LOBYTE(v11) = v26;
    v16 = &this->IEventQueueCallback;
  }
  else
  {
    v16 = &this->IEventQueueCallback;
  }
  CAdapter::TraceLoggingResetRecovery(v4, 2u, v8, v4->m_lResetTriggerCount, v4->m_OemPLDRSupported, v11);
  if ( v4->m_OemPLDRSupported )
  {
    v16 = &this->IEventQueueCallback;
  }
  else if ( v4->m_MiniportDriver->m_MiniportDriverCharacteristics.ResetHandlerEx )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v19 = (int)v7->__vftable;
      v20 = 57;
LABEL_15:
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        v18,
        v20,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v3,
        v19);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  if ( (unsigned int)_InterlockedIncrement(&v4->m_lResetRecovery) > 1 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v19 = (int)v16->__vftable;
    v20 = 58;
    goto LABEL_15;
  }
  CAdapter::CollectDebugData(
    v4,
    (struct DeviceCommand *)&this->IActivityId,
    (Task *)((char *)this - 24),
    *(struct CJobBase **)&this->m_CallStatus);
  CAdapter::TriggerControlPathDiagnostics(v4, 2u, v8);
  if ( v4->m_OemPLDRSupported )
  {
    if ( v4->m_IsRecoverable && !(_BYTE)v26 )
      CAdapter::ReenumerateFailedAdapter(*(CAdapter **)&this->m_TaskDeviceCommand.m_pParentJob->m_FailsafeJobStartedEvent.m_EventStatus);
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      1,
      59,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids);
  }
LABEL_27:
  Task::OnTaskCompletedHandler(v3, -1073676280, 0, 0);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    *(_DWORD *)v22 = 0;
    LOBYTE(v21) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      1,
      60,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      *(_QWORD *)v22);
  }
}

```

## disassembly

```asm
0x1400a6600  mov     [rsp-38h+arg_8], rbx
0x1400a6605  push    rbp
0x1400a6606  push    rsi
0x1400a6607  push    rdi
0x1400a6608  push    r12
0x1400a660a  push    r13
0x1400a660c  push    r14
0x1400a660e  push    r15
0x1400a6610  mov     rbp, rsp
0x1400a6613  sub     rsp, 60h
0x1400a6617  mov     rdi, rcx
0x1400a661a  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6621  xor     r15d, r15d
0x1400a6624  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a662b  lea     rax, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a6632  jz      short loc_1400A6662
0x1400a6634  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a663b  cmp     byte ptr [rcx+29h], 5
0x1400a663f  jnb     short loc_1400A6648
0x1400a6641  cmp     [rcx+48h], r15w
0x1400a6646  jz      short loc_1400A6662
0x1400a6648  mov     rcx, [rcx+40h]
0x1400a664c  mov     r9d, 37h ; '7'
0x1400a6652  mov     dl, 5
0x1400a6654  mov     qword ptr [rsp+60h+var_40], rax
0x1400a6659  lea     r8d, [r9-36h]
0x1400a665d  call    WPP_RECORDER_SF_
0x1400a6662  lea     r14, [rdi-18h]
0x1400a6666  mov     [rbp+arg_0], r15d
0x1400a666a  mov     rax, [r14+0F8h]
0x1400a6671  lea     r13, [rdi+20h]
0x1400a6675  lea     rdx, [rbp+arg_0]; unsigned int *
0x1400a6679  mov     rcx, r13; this
0x1400a667c  mov     rbx, [rax+0B0h]
0x1400a6683  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400a6688  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x1400a668c  mov     [rbp+arg_18], r15w
0x1400a6691  mov     rcx, r13; this
0x1400a6694  call    ?get_PortId@DeviceCommand@@QEAAHPEAG@Z; DeviceCommand::get_PortId(ushort *)
0x1400a6699  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a66a0  lea     rsi, [rdi+8]
0x1400a66a4  mov     r12d, [rbp+arg_0]
0x1400a66a8  jz      short loc_1400A66E3
0x1400a66aa  mov     eax, [rsi]
0x1400a66ac  mov     r9d, 38h ; '8'
0x1400a66b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a66b9  mov     dl, 2
0x1400a66bb  mov     dword ptr [rsp+60h+var_20], r12d
0x1400a66c0  mov     dword ptr [rsp+60h+var_28], r12d
0x1400a66c5  mov     dword ptr [rsp+60h+var_30], eax
0x1400a66c9  lea     rax, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a66d0  mov     rcx, [rcx+40h]
0x1400a66d4  mov     qword ptr [rsp+60h+var_38], r14
0x1400a66d9  mov     qword ptr [rsp+60h+var_40], rax
0x1400a66de  call    WPP_RECORDER_SF_qDdd
0x1400a66e3  mov     rcx, [rbx+58h]; NdisAdapterHandle
0x1400a66e7  mov     r9d, 2
0x1400a66ed  mov     r8d, r9d; NumberOfErrorValues
0x1400a66f0  mov     [rsp+60h+var_40], r12d
0x1400a66f5  mov     edx, 0C000138Ah; ErrorCode
0x1400a66fa  call    cs:__imp_NdisWriteErrorLogEntry
0x1400a6701  nop     dword ptr [rax+rax+00h]
0x1400a6706  mov     rax, [rdi+0E0h]
0x1400a670d  mov     rcx, [rax+0B0h]
0x1400a6714  add     rcx, 8
0x1400a6718  mov     rax, [rcx]
0x1400a671b  mov     rax, [rax+8]
0x1400a671f  call    _guard_dispatch_icall
0x1400a6724  xor     r8d, r8d; unsigned __int8
0x1400a6727  mov     rcx, rax; this
0x1400a672a  lea     edx, [r8+14h]; unsigned int
0x1400a672e  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a6733  mov     r8b, al
0x1400a6736  mov     byte ptr [rbp+arg_0], al
0x1400a6739  lock inc dword ptr [rbx+15C4h]
0x1400a6740  mov     ecx, cs:dword_1400F8790
0x1400a6746  cmp     ecx, 2
0x1400a6749  jbe     loc_1400A67D5
0x1400a674f  mov     edx, 5
0x1400a6754  lea     rcx, dword_1400F8790
0x1400a675b  call    _tlgKeywordOn
0x1400a6760  test    al, al
0x1400a6762  jz      short loc_1400A67D5
0x1400a6764  mov     eax, [rbx+15C4h]
0x1400a676a  test    r8b, r8b
0x1400a676d  mov     [rbp+var_10], eax
0x1400a6770  movzx   ecx, r12w
0x1400a6774  mov     eax, [rbx+15D4h]
0x1400a677a  setz    [rbp+arg_10]
0x1400a677e  mov     [rbp+var_C], eax
0x1400a6781  movzx   eax, [rbp+arg_18]
0x1400a6785  mov     [rbp+arg_18], ax
0x1400a6789  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x1400a678e  mov     [rbp+var_8], rax
0x1400a6792  lea     rdx, byte_1400EF26D
0x1400a6799  lea     rax, [rbp+var_10]
0x1400a679d  mov     [rsp+60h+var_20], rax
0x1400a67a2  lea     rax, [rbp+arg_10]
0x1400a67a6  mov     [rsp+60h+var_28], rax
0x1400a67ab  lea     rax, [rbp+var_C]
0x1400a67af  mov     [rsp+60h+var_30], rax
0x1400a67b4  lea     rax, [rbp+arg_18]
0x1400a67b8  mov     qword ptr [rsp+60h+var_38], rax
0x1400a67bd  lea     rax, [rbp+var_8]
0x1400a67c1  mov     qword ptr [rsp+60h+var_40], rax
0x1400a67c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x1400a67cb  mov     r8b, byte ptr [rbp+arg_0]
0x1400a67cf  lea     r15, [rdi+8]
0x1400a67d3  jmp     short loc_1400A67D8
0x1400a67d5  mov     r15, rsi
0x1400a67d8  mov     eax, [rbx+15D4h]
0x1400a67de  mov     edx, 2; unsigned int
0x1400a67e3  mov     r9d, [rbx+15C4h]; unsigned int
0x1400a67ea  mov     rcx, rbx; this
0x1400a67ed  mov     [rsp+60h+var_38], r8b; char
0x1400a67f2  mov     r8d, r12d; unsigned int
0x1400a67f5  mov     [rsp+60h+var_40], eax; unsigned int
0x1400a67f9  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x1400a67fe  cmp     dword ptr [rbx+15D4h], 0
0x1400a6805  jnz     short loc_1400A685B
0x1400a6807  mov     rax, [rbx+68h]
0x1400a680b  cmp     qword ptr [rax+98h], 0
0x1400a6813  jz      short loc_1400A685E
0x1400a6815  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a681c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400a6823  lea     rdi, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a682a  jz      short loc_1400A6854
0x1400a682c  mov     eax, [rsi]
0x1400a682e  mov     r9d, 39h ; '9'
0x1400a6834  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a683b  mov     dl, 2
0x1400a683d  mov     dword ptr [rsp+60h+var_30], eax
0x1400a6841  mov     qword ptr [rsp+60h+var_38], r14
0x1400a6846  mov     qword ptr [rsp+60h+var_40], rdi
0x1400a684b  mov     rcx, [rcx+40h]
0x1400a684f  call    WPP_RECORDER_SF_qD
0x1400a6854  xor     esi, esi
0x1400a6856  jmp     loc_1400A692B
0x1400a685b  mov     r15, rsi
0x1400a685e  mov     eax, 1
0x1400a6863  lock xadd [rbx+15C8h], eax
0x1400a686b  inc     eax
0x1400a686d  cmp     eax, 1
0x1400a6870  jbe     short loc_1400A6894
0x1400a6872  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6879  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400a6880  lea     rdi, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a6887  jz      short loc_1400A6854
0x1400a6889  mov     eax, [r15]
0x1400a688c  mov     r9d, 3Ah ; ':'
0x1400a6892  jmp     short loc_1400A6834
0x1400a6894  mov     r9, [rdi+1B8h]; struct CJobBase *
0x1400a689b  mov     r8, r14; struct Task *
0x1400a689e  mov     rdx, r13; struct DeviceCommand *
0x1400a68a1  mov     rcx, rbx; this
0x1400a68a4  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x1400a68a9  mov     r8d, r12d; unsigned int
0x1400a68ac  mov     edx, 2; unsigned int
0x1400a68b1  mov     rcx, rbx; this
0x1400a68b4  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400a68b9  xor     esi, esi
0x1400a68bb  cmp     [rbx+15D4h], esi
0x1400a68c1  jnz     short loc_1400A68FB
0x1400a68c3  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a68ca  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400a68d1  lea     rdi, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a68d8  jz      short loc_1400A692B
0x1400a68da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a68e1  lea     r9d, [rsi+3Bh]
0x1400a68e5  lea     r8d, [rsi+1]
0x1400a68e9  mov     qword ptr [rsp+60h+var_40], rdi
0x1400a68ee  mov     dl, 2
0x1400a68f0  mov     rcx, [rcx+40h]
0x1400a68f4  call    WPP_RECORDER_SF_
0x1400a68f9  jmp     short loc_1400A692B
0x1400a68fb  cmp     [rbx+12F5h], sil
0x1400a6902  jz      short loc_1400A691D
0x1400a6904  cmp     byte ptr [rbp+arg_0], sil
0x1400a6908  jnz     short loc_1400A691D
0x1400a690a  mov     rcx, [rdi+0E0h]
0x1400a6911  mov     rcx, [rcx+0B0h]; this
0x1400a6918  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400a691d  lea     rdi, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x1400a6924  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400a692b  xor     r9d, r9d; unsigned __int8 *
0x1400a692e  xor     r8d, r8d; unsigned int
0x1400a6931  mov     edx, 0C0010008h; int
0x1400a6936  mov     rcx, r14; this
0x1400a6939  call    ?OnTaskCompletedHandler@Task@@IEAAXHKPEAE@Z; Task::OnTaskCompletedHandler(int,ulong,uchar *)
0x1400a693e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x1400a6945  jz      short loc_1400A6978
0x1400a6947  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a694e  cmp     byte ptr [rcx+29h], 5
0x1400a6952  jnb     short loc_1400A695A
0x1400a6954  cmp     [rcx+48h], si
0x1400a6958  jz      short loc_1400A6978
0x1400a695a  mov     rcx, [rcx+40h]
0x1400a695e  mov     r9d, 3Ch ; '<'
0x1400a6964  mov     dword ptr [rsp+60h+var_38], esi
0x1400a6968  mov     dl, 5
0x1400a696a  mov     qword ptr [rsp+60h+var_40], rdi
0x1400a696f  lea     r8d, [r9-3Bh]
0x1400a6973  call    WPP_RECORDER_SF_D
0x1400a6978  mov     rbx, [rsp+60h+arg_8]
0x1400a6980  add     rsp, 60h
0x1400a6984  pop     r15
0x1400a6986  pop     r14
0x1400a6988  pop     r13
0x1400a698a  pop     r12
0x1400a698c  pop     rdi
0x1400a698d  pop     rsi
0x1400a698e  pop     rbp
0x1400a698f  retn
```
