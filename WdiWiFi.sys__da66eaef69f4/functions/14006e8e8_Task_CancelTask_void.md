# Task::CancelTask(void)

- ea: `0x14006e8e8`
- end: `0x14006eac9`
- name: `?CancelTask@Task@@QEAAXXZ`
- size: `481`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14006e870`
- `0x140075b58`
- `0x1400768e0`

## callees

- `0x140001008`
- `0x1400122e0`
- `0x14002aa28`
- `0x140049ed8`
- `0x14004bf10`
- `0x14004d594`
- `0x14006e8e8`
- `0x14007e5dc`
- `0x140082ff8`

## string_xrefs

- `0x14006ea03`: `Completed`

## pseudocode

```c
void __fastcall Task::CancelTask(Task *this, __int64 a2, int a3)
{
  int v4; // edx
  __int64 v5; // r8
  _WFC_TASK_STATE m_State; // ecx
  __int32 v7; // ecx
  __int32 v8; // ecx
  const char *v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned __int16 v13; // [rsp+70h] [rbp+30h] BYREF
  const char *v14; // [rsp+78h] [rbp+38h] BYREF
  const char *v15; // [rsp+80h] [rbp+40h] BYREF

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      28,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  if ( this->m_IsTaskCancelled )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      a3,
      29,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  else
  {
    this->m_IsTaskCancelled = 1;
    LODWORD(v14) = 0;
    DeviceCommand::get_CommandType(&this->m_TaskDeviceCommand, (unsigned int *)&v14);
    v13 = 0;
    DeviceCommand::get_PortId(&this->m_TaskDeviceCommand, &v13);
    if ( (unsigned int)dword_1400F8790 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400F8790, 5, v5) )
    {
      m_State = this->m_State;
      if ( m_State )
      {
        v7 = m_State - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 == 1 )
              v9 = "Completed";
            else
              v9 = "Unknown";
          }
          else
          {
            v9 = "Pending";
          }
        }
        else
        {
          v9 = "Starting";
        }
      }
      else
      {
        v9 = "Init";
      }
      v15 = v9;
      v14 = WDI_TLV::stringify::ToLogString((unsigned __int16)v14);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
        v10,
        (unsigned int)&byte_1400EF347,
        v11,
        v12,
        (__int64)&v14,
        (__int64)&v15,
        (__int64)&v13);
    }
    if ( this->m_State == WiFiTaskStatePending )
      DeviceCommandScheduler::CancelTask(this->m_pDeviceCommandScheduler, &this->m_TaskDeviceCommand);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      30,
      (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
      (char)this,
      this->m_ActivityId,
      0);
  }
}

```

## disassembly

```asm
0x14006e8e8  mov     [rsp-28h+arg_18], rbx
0x14006e8ed  push    rbp
0x14006e8ee  push    rsi
0x14006e8ef  push    rdi
0x14006e8f0  push    r12
0x14006e8f2  push    r15
0x14006e8f4  mov     rbp, rsp
0x14006e8f7  sub     rsp, 40h
0x14006e8fb  mov     rbx, rcx
0x14006e8fe  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006e905  xor     esi, esi
0x14006e907  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006e90e  lea     r12, WPP_13843484fb6a395abd563b849973c7a7_Traceguids
0x14006e915  jz      short loc_14006E94C
0x14006e917  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e91e  cmp     byte ptr [rcx+29h], 5
0x14006e922  jnb     short loc_14006E92A
0x14006e924  cmp     [rcx+48h], si
0x14006e928  jz      short loc_14006E94C
0x14006e92a  mov     eax, [rbx+20h]
0x14006e92d  mov     r9d, 1Ch
0x14006e933  mov     rcx, [rcx+40h]
0x14006e937  mov     dl, 5
0x14006e939  mov     dword ptr [rsp+40h+var_10], eax
0x14006e93d  mov     [rsp+40h+var_18], rbx
0x14006e942  mov     [rsp+40h+var_20], r12
0x14006e947  call    WPP_RECORDER_SF_qD
0x14006e94c  cmp     [rbx+34h], sil
0x14006e950  jz      short loc_14006E98D
0x14006e952  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006e959  jz      loc_14006EAB4
0x14006e95f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e966  mov     r9d, 1Dh
0x14006e96c  mov     eax, [rbx+20h]
0x14006e96f  mov     dl, 2
0x14006e971  mov     dword ptr [rsp+40h+var_10], eax
0x14006e975  mov     [rsp+40h+var_18], rbx
0x14006e97a  mov     rcx, [rcx+40h]
0x14006e97e  mov     [rsp+40h+var_20], r12
0x14006e983  call    WPP_RECORDER_SF_qD
0x14006e988  jmp     loc_14006EA72
0x14006e98d  lea     rdi, [rbx+38h]
0x14006e991  mov     byte ptr [rbx+34h], 1
0x14006e995  mov     rcx, rdi; this
0x14006e998  mov     dword ptr [rbp+arg_8], esi
0x14006e99b  lea     rdx, [rbp+arg_8]; unsigned int *
0x14006e99f  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x14006e9a4  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x14006e9a8  mov     [rbp+arg_0], si
0x14006e9ac  mov     rcx, rdi; this
0x14006e9af  call    ?get_PortId@DeviceCommand@@QEAAHPEAG@Z; DeviceCommand::get_PortId(ushort *)
0x14006e9b4  mov     eax, cs:dword_1400F8790
0x14006e9ba  cmp     eax, 5
0x14006e9bd  jbe     loc_14006EA5D
0x14006e9c3  mov     edx, 5
0x14006e9c8  lea     rcx, dword_1400F8790
0x14006e9cf  call    _tlgKeywordOn
0x14006e9d4  test    al, al
0x14006e9d6  jz      loc_14006EA5D
0x14006e9dc  movzx   eax, [rbp+arg_0]
0x14006e9e0  mov     ecx, [rbx+30h]
0x14006e9e3  mov     [rbp+arg_0], ax
0x14006e9e7  test    ecx, ecx
0x14006e9e9  jz      short loc_14006EA1E
0x14006e9eb  sub     ecx, 1
0x14006e9ee  jz      short loc_14006EA15
0x14006e9f0  sub     ecx, 1
0x14006e9f3  jz      short loc_14006EA0C
0x14006e9f5  cmp     ecx, 1
0x14006e9f8  jz      short loc_14006EA03
0x14006e9fa  lea     rax, aUnknown; "Unknown"
0x14006ea01  jmp     short loc_14006EA25
0x14006ea03  lea     rax, aCompleted; "Completed"
0x14006ea0a  jmp     short loc_14006EA25
0x14006ea0c  lea     rax, aPending; "Pending"
0x14006ea13  jmp     short loc_14006EA25
0x14006ea15  lea     rax, aStarting; "Starting"
0x14006ea1c  jmp     short loc_14006EA25
0x14006ea1e  lea     rax, aInit; "Init"
0x14006ea25  movzx   ecx, word ptr [rbp+arg_8]
0x14006ea29  mov     [rbp+arg_10], rax
0x14006ea2d  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x14006ea32  mov     [rbp+arg_8], rax
0x14006ea36  lea     rdx, byte_1400EF347
0x14006ea3d  lea     rax, [rbp+arg_0]
0x14006ea41  mov     [rsp+40h+var_10], rax
0x14006ea46  lea     rax, [rbp+arg_10]
0x14006ea4a  mov     [rsp+40h+var_18], rax
0x14006ea4f  lea     rax, [rbp+arg_8]
0x14006ea53  mov     [rsp+40h+var_20], rax
0x14006ea58  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x14006ea5d  cmp     dword ptr [rbx+30h], 2
0x14006ea61  jnz     short loc_14006EA72
0x14006ea63  mov     rcx, [rbx+0F8h]; this
0x14006ea6a  mov     rdx, rdi; struct DeviceCommand *
0x14006ea6d  call    ?CancelTask@DeviceCommandScheduler@@QEAAXPEAVDeviceCommand@@@Z; DeviceCommandScheduler::CancelTask(DeviceCommand *)
0x14006ea72  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14006ea79  jz      short loc_14006EAB4
0x14006ea7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea82  cmp     byte ptr [rcx+29h], 5
0x14006ea86  jnb     short loc_14006EA8E
0x14006ea88  cmp     [rcx+48h], si
0x14006ea8c  jz      short loc_14006EAB4
0x14006ea8e  mov     eax, [rbx+20h]
0x14006ea91  mov     r9d, 1Eh
0x14006ea97  mov     rcx, [rcx+40h]
0x14006ea9b  mov     dl, 5
0x14006ea9d  mov     [rsp+40h+var_8], esi
0x14006eaa1  mov     dword ptr [rsp+40h+var_10], eax
0x14006eaa5  mov     [rsp+40h+var_18], rbx
0x14006eaaa  mov     [rsp+40h+var_20], r12
0x14006eaaf  call    WPP_RECORDER_SF_qDD
0x14006eab4  mov     rbx, [rsp+40h+arg_18]
0x14006eabc  add     rsp, 40h
0x14006eac0  pop     r15
0x14006eac2  pop     r12
0x14006eac4  pop     rdi
0x14006eac5  pop     rsi
0x14006eac6  pop     rbp
0x14006eac7  retn
```
