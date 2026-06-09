# Task::OnTaskCompletedHandler(int,ulong,uchar *)

- ea: `0x14002ace4`
- end: `0x14002b0a9`
- name: `?OnTaskCompletedHandler@Task@@IEAAXHKPEAE@Z`
- size: `965`
- prototype: `void __fastcall(Task *__hidden this, int, unsigned int, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140029bc0`
- `0x14002ab20`
- `0x14005f868`
- `0x1400a6600`

## callees

- `0x14000158c`
- `0x140005ec8`
- `0x1400122e0`
- `0x1400236f4`
- `0x140023ae0`
- `0x14002aa28`
- `0x14002ace4`
- `0x140049ed8`
- `0x140049fe8`
- `0x14004d594`
- `0x14004ff88`
- `0x1400730f4`
- `0x14007e5dc`
- `0x140082ff8`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002af01`
- `ntoskrnl!ExAllocatePool2` at `0x14002af01`

## pseudocode

```c
void __fastcall Task::OnTaskCompletedHandler(Task *this, int a2, __int64 a3, unsigned __int8 *a4)
{
  size_t v5; // rsi
  Task *v7; // rbx
  __int64 *v8; // rdx
  DeviceCommand *p_m_TaskDeviceCommand; // rsi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned __int8 *m_OutputBuffer; // rcx
  unsigned __int8 *Pool2; // rax
  int v15; // edx
  int v16; // r8d
  unsigned __int8 *v17; // rcx
  int v18; // edx
  unsigned int m_NotificationRegistrationToken; // edx
  __int64 v20; // [rsp+38h] [rbp-30h]
  unsigned int v21[2]; // [rsp+50h] [rbp-18h] BYREF
  int v22[4]; // [rsp+58h] [rbp-10h] BYREF
  unsigned __int16 v23; // [rsp+B0h] [rbp+48h] BYREF

  v5 = (unsigned int)a3;
  v7 = this;
  v8 = WPP_13843484fb6a395abd563b849973c7a7_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    this = (Task *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        44,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v7,
        v7->m_ActivityId);
      v8 = WPP_13843484fb6a395abd563b849973c7a7_Traceguids;
    }
  }
  if ( v7->m_State == WiFiTaskStateCompleted )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        45,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v7,
        v7->m_ActivityId);
    }
    if ( v7->m_CallStatus )
      a2 = 0;
LABEL_10:
    p_m_TaskDeviceCommand = &v7->m_TaskDeviceCommand;
    if ( !a2 )
      goto LABEL_32;
    goto LABEL_11;
  }
  if ( a2 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        47,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v7,
        v7->m_ActivityId,
        a2);
    }
    goto LABEL_20;
  }
  if ( !a4 || (unsigned int)v5 < 0x30 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDqD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        46,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v7,
        v7->m_ActivityId,
        (char)a4,
        v5);
    }
    a2 = -1073676267;
LABEL_20:
    p_m_TaskDeviceCommand = &v7->m_TaskDeviceCommand;
    goto LABEL_11;
  }
  m_OutputBuffer = v7->m_OutputBuffer;
  if ( m_OutputBuffer )
  {
    operator delete(m_OutputBuffer);
    v7->m_OutputBuffer = 0;
    v7->m_OutputBufferLength = 0;
  }
  Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v5, 1198089303);
  v7->m_OutputBuffer = Pool2;
  if ( Pool2 )
  {
    v7->m_OutputBufferLength = v5;
    memmove(Pool2, a4, v5);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v17 = v7->m_OutputBuffer;
      v18 = *((unsigned __int16 *)v17 + 16);
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_qDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        a3,
        49,
        (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
        (char)v7,
        v7->m_ActivityId,
        *((_WORD *)v17 + 16),
        *((_DWORD *)v17 + 10),
        *((_DWORD *)v17 + 9));
      p_m_TaskDeviceCommand = &v7->m_TaskDeviceCommand;
      goto LABEL_32;
    }
    goto LABEL_10;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v16,
      48,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (char)v7,
      v7->m_ActivityId);
  }
  a2 = -1073741670;
  p_m_TaskDeviceCommand = &v7->m_TaskDeviceCommand;
LABEL_11:
  v21[0] = 0;
  DeviceCommand::get_CommandType(p_m_TaskDeviceCommand, v21);
  v23 = 0;
  DeviceCommand::get_PortId(p_m_TaskDeviceCommand, &v23);
  if ( (unsigned int)dword_1400F8790 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400F8790, 5, a3) )
  {
    v22[0] = a2;
    *(_QWORD *)v21 = WDI_TLV::stringify::ToLogString(v21[0]);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
      v10,
      (unsigned int)byte_1400EF2E5,
      v11,
      v12,
      (__int64)v21,
      (__int64)v22,
      (__int64)&v23);
  }
LABEL_32:
  if ( !v7->m_IsDeviceCommandPending )
    a2 = EventQueue::PopulateAndQueueDeferredCallback(
           v7->m_pEventQueue,
           WiFiEventDeferredOperationCompletion,
           (void *)v7->m_pTaskCompletionCallback,
           v7,
           a2,
           &p_m_TaskDeviceCommand->m_FailsafeCompletionEvent);
  m_NotificationRegistrationToken = v7->m_NotificationRegistrationToken;
  v7->m_CallStatus = a2;
  v7->m_State = WiFiTaskStateCompleted;
  if ( m_NotificationRegistrationToken )
  {
    a2 = NotificationManager::DeregisterNotificationHandler(v7->m_pNotificationManager, m_NotificationRegistrationToken);
    v7->m_NotificationRegistrationToken = 0;
  }
  if ( !v7->m_bTimerStopped )
  {
    EventQueue::StopTimer((EventQueue *)this, v7->m_pTimerRegistrationContext);
    v7->m_bTimerStopped = 1;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(m_NotificationRegistrationToken) = 5;
    LODWORD(v20) = a2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      m_NotificationRegistrationToken,
      a3,
      50,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (char)v7,
      v7->m_ActivityId,
      v20);
  }
}

```

## disassembly

```asm
0x14002ace4  push    rbp
0x14002ace6  push    rbx
0x14002ace7  push    rsi
0x14002ace8  push    rdi
0x14002ace9  push    r12
0x14002aceb  push    r13
0x14002aced  push    r14
0x14002acef  push    r15
0x14002acf1  mov     rbp, rsp
0x14002acf4  sub     rsp, 68h
0x14002acf8  mov     r14, r9
0x14002acfb  mov     esi, r8d
0x14002acfe  mov     edi, edx
0x14002ad00  mov     rbx, rcx
0x14002ad03  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ad0a  xor     r12d, r12d
0x14002ad0d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002ad14  lea     rdx, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002ad1b  jz      short loc_14002AD5A
0x14002ad1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad24  cmp     byte ptr [rcx+29h], 5
0x14002ad28  jnb     short loc_14002AD31
0x14002ad2a  cmp     [rcx+48h], r12w
0x14002ad2f  jz      short loc_14002AD5A
0x14002ad31  mov     eax, [rbx+20h]
0x14002ad34  mov     r9d, 2Ch ; ','
0x14002ad3a  mov     rcx, [rcx+40h]
0x14002ad3e  mov     dword ptr [rsp+68h+var_38], eax
0x14002ad42  mov     [rsp+68h+var_40], rbx
0x14002ad47  mov     qword ptr [rsp+68h+var_48], rdx
0x14002ad4c  mov     dl, 5
0x14002ad4e  call    WPP_RECORDER_SF_qD
0x14002ad53  lea     rdx, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002ad5a  cmp     dword ptr [rbx+30h], 3
0x14002ad5e  jnz     loc_14002AE41
0x14002ad64  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002ad6b  jz      short loc_14002AD96
0x14002ad6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad74  mov     r9d, 2Dh ; '-'
0x14002ad7a  mov     eax, [rbx+20h]
0x14002ad7d  mov     dword ptr [rsp+68h+var_38], eax
0x14002ad81  mov     [rsp+68h+var_40], rbx
0x14002ad86  mov     rcx, [rcx+40h]
0x14002ad8a  mov     qword ptr [rsp+68h+var_48], rdx
0x14002ad8f  mov     dl, 4
0x14002ad91  call    WPP_RECORDER_SF_qD
0x14002ad96  cmp     [rbx+1B8h], r12d
0x14002ad9d  cmovnz  edi, r12d
0x14002ada1  lea     rsi, [rbx+38h]
0x14002ada5  test    edi, edi
0x14002ada7  jz      loc_14002AFD2
0x14002adad  lea     r14, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002adb4  lea     rdx, [rbp+var_18]; unsigned int *
0x14002adb8  mov     [rbp+var_18], r12d
0x14002adbc  mov     rcx, rsi; this
0x14002adbf  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x14002adc4  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x14002adc8  mov     [rbp+arg_0], r12w
0x14002adcd  mov     rcx, rsi; this
0x14002add0  call    ?get_PortId@DeviceCommand@@QEAAHPEAG@Z; DeviceCommand::get_PortId(ushort *)
0x14002add5  mov     eax, cs:dword_1400F8790
0x14002addb  cmp     eax, 2
0x14002adde  jbe     loc_14002AFD9
0x14002ade4  mov     edx, 5
0x14002ade9  lea     rcx, dword_1400F8790
0x14002adf0  call    _tlgKeywordOn
0x14002adf5  test    al, al
0x14002adf7  jz      loc_14002AFD9
0x14002adfd  movzx   eax, [rbp+arg_0]
0x14002ae01  movzx   ecx, word ptr [rbp+var_18]
0x14002ae05  mov     [rbp+arg_0], ax
0x14002ae09  mov     [rbp+var_10], edi
0x14002ae0c  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x14002ae11  mov     qword ptr [rbp+var_18], rax
0x14002ae15  lea     rdx, byte_1400EF2E5
0x14002ae1c  lea     rax, [rbp+arg_0]
0x14002ae20  mov     [rsp+68h+var_38], rax
0x14002ae25  lea     rax, [rbp+var_10]
0x14002ae29  mov     [rsp+68h+var_40], rax
0x14002ae2e  lea     rax, [rbp+var_18]
0x14002ae32  mov     qword ptr [rsp+68h+var_48], rax
0x14002ae37  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x14002ae3c  jmp     loc_14002AFD9
0x14002ae41  test    edi, edi
0x14002ae43  jnz     short loc_14002AE9C
0x14002ae45  test    r14, r14
0x14002ae48  jz      short loc_14002AE4F
0x14002ae4a  cmp     esi, 30h ; '0'
0x14002ae4d  jnb     short loc_14002AE98
0x14002ae4f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002ae56  jz      short loc_14002AE8A
0x14002ae58  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae5f  mov     r9d, 2Eh ; '.'
0x14002ae65  mov     eax, [rbx+20h]
0x14002ae68  mov     [rsp+68h+var_28], esi
0x14002ae6c  mov     [rsp+68h+var_30], r14
0x14002ae71  mov     rcx, [rcx+40h]
0x14002ae75  mov     dword ptr [rsp+68h+var_38], eax
0x14002ae79  mov     [rsp+68h+var_40], rbx
0x14002ae7e  mov     qword ptr [rsp+68h+var_48], rdx
0x14002ae83  mov     dl, 2
0x14002ae85  call    WPP_RECORDER_SF_qDqD
0x14002ae8a  mov     edi, 0C0010015h
0x14002ae8f  lea     rsi, [rbx+38h]
0x14002ae93  jmp     loc_14002ADAD
0x14002ae98  test    edi, edi
0x14002ae9a  jz      short loc_14002AED4
0x14002ae9c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002aea3  jz      short loc_14002AE8F
0x14002aea5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aeac  mov     r9d, 2Fh ; '/'
0x14002aeb2  mov     eax, [rbx+20h]
0x14002aeb5  mov     dword ptr [rsp+68h+var_30], edi
0x14002aeb9  mov     dword ptr [rsp+68h+var_38], eax
0x14002aebd  mov     rcx, [rcx+40h]
0x14002aec1  mov     [rsp+68h+var_40], rbx
0x14002aec6  mov     qword ptr [rsp+68h+var_48], rdx
0x14002aecb  mov     dl, 2
0x14002aecd  call    WPP_RECORDER_SF_qDD
0x14002aed2  jmp     short loc_14002AE8F
0x14002aed4  mov     rcx, [rbx+1B0h]; void *
0x14002aedb  test    rcx, rcx
0x14002aede  jz      short loc_14002AEF3
0x14002aee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002aee5  mov     [rbx+1B0h], r12
0x14002aeec  mov     [rbx+1ACh], r12d
0x14002aef3  mov     r8d, 47696457h
0x14002aef9  mov     rdx, rsi
0x14002aefc  mov     ecx, 40h ; '@'
0x14002af01  call    cs:__imp_ExAllocatePool2
0x14002af08  nop     dword ptr [rax+rax+00h]
0x14002af0d  mov     [rbx+1B0h], rax
0x14002af14  test    rax, rax
0x14002af17  jnz     short loc_14002AF5E
0x14002af19  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002af20  lea     r14, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002af27  jz      short loc_14002AF50
0x14002af29  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af30  lea     r9d, [rax+30h]
0x14002af34  mov     eax, [rbx+20h]
0x14002af37  mov     dl, 2
0x14002af39  mov     dword ptr [rsp+68h+var_38], eax
0x14002af3d  mov     [rsp+68h+var_40], rbx
0x14002af42  mov     rcx, [rcx+40h]
0x14002af46  mov     qword ptr [rsp+68h+var_48], r14
0x14002af4b  call    WPP_RECORDER_SF_qD
0x14002af50  mov     edi, 0C000009Ah
0x14002af55  lea     rsi, [rbx+38h]
0x14002af59  jmp     loc_14002ADB4
0x14002af5e  mov     r8, rsi; Size
0x14002af61  mov     [rbx+1ACh], esi
0x14002af67  mov     rdx, r14; Src
0x14002af6a  mov     rcx, rax; void *
0x14002af6d  call    memmove
0x14002af72  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002af79  jz      loc_14002ADA1
0x14002af7f  mov     rcx, [rbx+1B0h]
0x14002af86  lea     r14, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002af8d  mov     r9d, 31h ; '1'
0x14002af93  mov     eax, [rcx+24h]
0x14002af96  movzx   edx, word ptr [rcx+20h]
0x14002af9a  mov     [rsp+68h+var_20], eax
0x14002af9e  mov     eax, [rcx+28h]
0x14002afa1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afa8  mov     [rsp+68h+var_28], eax
0x14002afac  mov     eax, [rbx+20h]
0x14002afaf  mov     dword ptr [rsp+68h+var_30], edx
0x14002afb3  mov     dl, 4
0x14002afb5  mov     rcx, [rcx+40h]
0x14002afb9  mov     dword ptr [rsp+68h+var_38], eax
0x14002afbd  mov     [rsp+68h+var_40], rbx
0x14002afc2  mov     qword ptr [rsp+68h+var_48], r14
0x14002afc7  call    WPP_RECORDER_SF_qDddd
0x14002afcc  lea     rsi, [rbx+38h]
0x14002afd0  jmp     short loc_14002AFD9
0x14002afd2  lea     r14, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14002afd9  cmp     [rbx+1A8h], r12b
0x14002afe0  jnz     short loc_14002B00C
0x14002afe2  mov     r8, [rbx+100h]; void *
0x14002afe9  lea     rax, [rsi+10h]
0x14002afed  mov     rcx, [rbx+0F0h]; this
0x14002aff4  mov     r9, rbx; void *
0x14002aff7  mov     [rsp+68h+var_40], rax; struct Event *
0x14002affc  mov     edx, 1; enum _WFC_EVENT_TYPE
0x14002b001  mov     [rsp+68h+var_48], edi; int
0x14002b005  call    ?PopulateAndQueueDeferredCallback@EventQueue@@IEAAHW4_WFC_EVENT_TYPE@@PEAX1HPEAVEvent@@@Z; EventQueue::PopulateAndQueueDeferredCallback(_WFC_EVENT_TYPE,void *,void *,int,Event *)
0x14002b00a  mov     edi, eax
0x14002b00c  mov     edx, [rbx+108h]; unsigned int
0x14002b012  mov     [rbx+1B8h], edi
0x14002b018  mov     dword ptr [rbx+30h], 3
0x14002b01f  test    edx, edx
0x14002b021  jz      short loc_14002B038
0x14002b023  mov     rcx, [rbx+110h]; this
0x14002b02a  call    ?DeregisterNotificationHandler@NotificationManager@@QEAAHK@Z; NotificationManager::DeregisterNotificationHandler(ulong)
0x14002b02f  mov     edi, eax
0x14002b031  mov     [rbx+108h], r12d
0x14002b038  cmp     [rbx+1C8h], r12b
0x14002b03f  jnz     short loc_14002B054
0x14002b041  mov     rdx, [rbx+1C0h]; struct TimerRegistrationContext *
0x14002b048  call    ?StopTimer@EventQueue@@QEAAXPEAVTimerRegistrationContext@@@Z; EventQueue::StopTimer(TimerRegistrationContext *)
0x14002b04d  mov     byte ptr [rbx+1C8h], 1
0x14002b054  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002b05b  jz      short loc_14002B097
0x14002b05d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b064  cmp     byte ptr [rcx+29h], 5
0x14002b068  jnb     short loc_14002B071
0x14002b06a  cmp     [rcx+48h], r12w
0x14002b06f  jz      short loc_14002B097
0x14002b071  mov     eax, [rbx+20h]
0x14002b074  mov     r9d, 32h ; '2'
0x14002b07a  mov     rcx, [rcx+40h]
0x14002b07e  mov     dl, 5
0x14002b080  mov     dword ptr [rsp+68h+var_30], edi
0x14002b084  mov     dword ptr [rsp+68h+var_38], eax
0x14002b088  mov     [rsp+68h+var_40], rbx
0x14002b08d  mov     qword ptr [rsp+68h+var_48], r14
0x14002b092  call    WPP_RECORDER_SF_qDD
0x14002b097  add     rsp, 68h
0x14002b09b  pop     r15
0x14002b09d  pop     r14
0x14002b09f  pop     r13
0x14002b0a1  pop     r12
0x14002b0a3  pop     rdi
0x14002b0a4  pop     rsi
0x14002b0a5  pop     rbx
0x14002b0a6  pop     rbp
0x14002b0a7  retn
```
