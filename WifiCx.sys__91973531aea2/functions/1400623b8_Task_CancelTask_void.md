# Task::CancelTask(void)

- ea: `0x1400623b8`
- end: `0x140062599`
- name: `?CancelTask@Task@@QEAAXXZ`
- size: `481`
- prototype: `void __fastcall(Task *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140063458`
- `0x1400915b0`
- `0x1400c2f80`

## callees

- `0x140001008`
- `0x140001394`
- `0x14001c100`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140022cb4`
- `0x140039b80`
- `0x140061b6c`
- `0x1400623b8`

## string_xrefs

- `0x1400624d3`: `Completed`

## pseudocode

```c
void __fastcall Task::CancelTask(Task *this, __int64 a2, int a3)
{
  int v4; // edx
  int v5; // r8d
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  const char *v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned __int16 v13; // [rsp+70h] [rbp+30h] BYREF
  const char *v14; // [rsp+78h] [rbp+38h] BYREF
  const char *v15; // [rsp+80h] [rbp+40h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      28,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (char)this,
      *((_DWORD *)this + 8));
  }
  if ( *((_BYTE *)this + 52) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      a3,
      29,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (char)this,
      *((_DWORD *)this + 8));
  }
  else
  {
    *((_BYTE *)this + 52) = 1;
    LODWORD(v14) = 0;
    DeviceCommand::get_CommandType((Task *)((char *)this + 56), (unsigned int *)&v14);
    v13 = 0;
    DeviceCommand::get_PortId((Task *)((char *)this + 56), &v13);
    if ( (unsigned int)dword_14010EC48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14010EC48, 5) )
    {
      v6 = *((_DWORD *)this + 12);
      if ( v6 )
      {
        v7 = v6 - 1;
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
        (unsigned int)&unk_140104610,
        v11,
        v12,
        (__int64)&v14,
        (__int64)&v15,
        (__int64)&v13);
    }
    if ( *((_DWORD *)this + 12) == 2 )
      DeviceCommandScheduler::CancelTask(*((DeviceCommandScheduler **)this + 31), (Task *)((char *)this + 56));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      30,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (char)this,
      *((_DWORD *)this + 8),
      0);
  }
}

```

## disassembly

```asm
0x1400623b8  mov     [rsp-28h+arg_18], rbx
0x1400623bd  push    rbp
0x1400623be  push    rsi
0x1400623bf  push    rdi
0x1400623c0  push    r12
0x1400623c2  push    r15
0x1400623c4  mov     rbp, rsp
0x1400623c7  sub     rsp, 40h
0x1400623cb  mov     rbx, rcx
0x1400623ce  lea     r15, WPP_RECORDER_INITIALIZED
0x1400623d5  xor     esi, esi
0x1400623d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400623de  lea     r12, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x1400623e5  jz      short loc_14006241C
0x1400623e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400623ee  cmp     byte ptr [rcx+29h], 5
0x1400623f2  jnb     short loc_1400623FA
0x1400623f4  cmp     [rcx+48h], si
0x1400623f8  jz      short loc_14006241C
0x1400623fa  mov     eax, [rbx+20h]
0x1400623fd  mov     r9d, 1Ch
0x140062403  mov     rcx, [rcx+40h]
0x140062407  mov     dl, 5
0x140062409  mov     dword ptr [rsp+40h+var_10], eax
0x14006240d  mov     [rsp+40h+var_18], rbx
0x140062412  mov     [rsp+40h+var_20], r12
0x140062417  call    WPP_RECORDER_SF_qD
0x14006241c  cmp     [rbx+34h], sil
0x140062420  jz      short loc_14006245D
0x140062422  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062429  jz      loc_140062584
0x14006242f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062436  mov     r9d, 1Dh
0x14006243c  mov     eax, [rbx+20h]
0x14006243f  mov     dl, 2
0x140062441  mov     dword ptr [rsp+40h+var_10], eax
0x140062445  mov     [rsp+40h+var_18], rbx
0x14006244a  mov     rcx, [rcx+40h]
0x14006244e  mov     [rsp+40h+var_20], r12
0x140062453  call    WPP_RECORDER_SF_qD
0x140062458  jmp     loc_140062542
0x14006245d  lea     rdi, [rbx+38h]
0x140062461  mov     byte ptr [rbx+34h], 1
0x140062465  mov     rcx, rdi; this
0x140062468  mov     dword ptr [rbp+arg_8], esi
0x14006246b  lea     rdx, [rbp+arg_8]; unsigned int *
0x14006246f  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x140062474  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x140062478  mov     [rbp+arg_0], si
0x14006247c  mov     rcx, rdi; this
0x14006247f  call    ?get_PortId@DeviceCommand@@QEAAHPEAG@Z; DeviceCommand::get_PortId(ushort *)
0x140062484  mov     eax, cs:dword_14010EC48
0x14006248a  cmp     eax, 5
0x14006248d  jbe     loc_14006252D
0x140062493  mov     edx, 5
0x140062498  lea     rcx, dword_14010EC48
0x14006249f  call    _tlgKeywordOn
0x1400624a4  test    al, al
0x1400624a6  jz      loc_14006252D
0x1400624ac  movzx   eax, [rbp+arg_0]
0x1400624b0  mov     ecx, [rbx+30h]
0x1400624b3  mov     [rbp+arg_0], ax
0x1400624b7  test    ecx, ecx
0x1400624b9  jz      short loc_1400624EE
0x1400624bb  sub     ecx, 1
0x1400624be  jz      short loc_1400624E5
0x1400624c0  sub     ecx, 1
0x1400624c3  jz      short loc_1400624DC
0x1400624c5  cmp     ecx, 1
0x1400624c8  jz      short loc_1400624D3
0x1400624ca  lea     rax, aUnknown; "Unknown"
0x1400624d1  jmp     short loc_1400624F5
0x1400624d3  lea     rax, aCompleted; "Completed"
0x1400624da  jmp     short loc_1400624F5
0x1400624dc  lea     rax, aPending; "Pending"
0x1400624e3  jmp     short loc_1400624F5
0x1400624e5  lea     rax, aStarting; "Starting"
0x1400624ec  jmp     short loc_1400624F5
0x1400624ee  lea     rax, aInit; "Init"
0x1400624f5  movzx   ecx, word ptr [rbp+arg_8]
0x1400624f9  mov     [rbp+arg_10], rax
0x1400624fd  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140062502  mov     [rbp+arg_8], rax
0x140062506  lea     rdx, unk_140104610
0x14006250d  lea     rax, [rbp+arg_0]
0x140062511  mov     [rsp+40h+var_10], rax
0x140062516  lea     rax, [rbp+arg_10]
0x14006251a  mov     [rsp+40h+var_18], rax
0x14006251f  lea     rax, [rbp+arg_8]
0x140062523  mov     [rsp+40h+var_20], rax
0x140062528  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &)
0x14006252d  cmp     dword ptr [rbx+30h], 2
0x140062531  jnz     short loc_140062542
0x140062533  mov     rcx, [rbx+0F8h]; this
0x14006253a  mov     rdx, rdi; struct DeviceCommand *
0x14006253d  call    ?CancelTask@DeviceCommandScheduler@@QEAAXPEAVDeviceCommand@@@Z; DeviceCommandScheduler::CancelTask(DeviceCommand *)
0x140062542  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062549  jz      short loc_140062584
0x14006254b  mov     rcx, cs:WPP_GLOBAL_Control
0x140062552  cmp     byte ptr [rcx+29h], 5
0x140062556  jnb     short loc_14006255E
0x140062558  cmp     [rcx+48h], si
0x14006255c  jz      short loc_140062584
0x14006255e  mov     eax, [rbx+20h]
0x140062561  mov     r9d, 1Eh
0x140062567  mov     rcx, [rcx+40h]
0x14006256b  mov     dl, 5
0x14006256d  mov     [rsp+40h+var_8], esi
0x140062571  mov     dword ptr [rsp+40h+var_10], eax
0x140062575  mov     [rsp+40h+var_18], rbx
0x14006257a  mov     [rsp+40h+var_20], r12
0x14006257f  call    WPP_RECORDER_SF_qDD
0x140062584  mov     rbx, [rsp+40h+arg_18]
0x14006258c  add     rsp, 40h
0x140062590  pop     r15
0x140062592  pop     r12
0x140062594  pop     rdi
0x140062595  pop     rsi
0x140062596  pop     rbp
0x140062597  retn
```
