# CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140042194`
- end: `0x140042254`
- name: `?ProcessDeviceIdentityNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14000c598`
- `0x140042194`
- `0x140044b74`

## string_xrefs

- `0x14004222c`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400421df`: `CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rax
  int updated; // eax
  int v10[2]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v12; // [rsp+60h] [rbp+8h] BYREF
  const wchar_t *v13; // [rsp+70h] [rbp+18h] BYREF
  CMidiEndpointProtocolWorker *v14; // [rsp+78h] [rbp+20h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v7 = (_QWORD *)*v7;
    v12 = v7;
    v14 = this;
    v13 = L"Received Device Identity Notification";
    *(_QWORD *)v10 = "CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008BF29,
      v5,
      v6,
      v10,
      (__int64)&v14,
      &v13,
      &v12);
  }
  updated = CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty(this, a2);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D4,
      (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)updated);
  *((_BYTE *)this + 321) = 1;
  return 0;
}

```

## disassembly

```asm
0x140042194  mov     [rsp+arg_8], rbx
0x140042199  push    rdi
0x14004219a  sub     rsp, 50h
0x14004219e  mov     rdi, rdx
0x1400421a1  mov     rbx, rcx
0x1400421a4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400421a9  mov     rcx, [rax+8]
0x1400421ad  mov     eax, [rcx]
0x1400421af  cmp     eax, 4
0x1400421b2  jbe     short loc_140042218
0x1400421b4  lea     rax, [rbx+38h]
0x1400421b8  cmp     qword ptr [rax+18h], 7
0x1400421bd  jbe     short loc_1400421C2
0x1400421bf  mov     rax, [rax]
0x1400421c2  mov     [rsp+58h+arg_0], rax
0x1400421c7  lea     rdx, byte_14008BF29
0x1400421ce  lea     rax, aReceivedDevice; "Received Device Identity Notification"
0x1400421d5  mov     [rsp+58h+arg_18], rbx
0x1400421da  mov     [rsp+58h+arg_10], rax
0x1400421df  lea     rax, aCmidiendpointp_9; "CMidiEndpointProtocolWorker::ProcessDev"...
0x1400421e6  mov     qword ptr [rsp+58h+var_18], rax
0x1400421eb  lea     rax, [rsp+58h+arg_0]
0x1400421f0  mov     [rsp+58h+var_20], rax
0x1400421f5  lea     rax, [rsp+58h+arg_10]
0x1400421fa  mov     [rsp+58h+var_28], rax
0x1400421ff  lea     rax, [rsp+58h+arg_18]
0x140042204  mov     [rsp+58h+var_30], rax
0x140042209  lea     rax, [rsp+58h+var_18]
0x14004220e  mov     qword ptr [rsp+58h+var_38], rax; int
0x140042213  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140042218  mov     rdx, rdi; struct WindowsMidiServicesInternal::PackedUmp128 *
0x14004221b  mov     rcx, rbx; this
0x14004221e  call    ?UpdateDeviceIdentityProperty@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty(WindowsMidiServicesInternal::PackedUmp128 &)
0x140042223  test    eax, eax
0x140042225  jns     short loc_140042240
0x140042227  mov     rcx, [rsp+58h]; this
0x14004222c  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140042233  mov     r9d, eax; char *
0x140042236  mov     edx, 2D4h; void *
0x14004223b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140042240  mov     byte ptr [rbx+141h], 1
0x140042247  xor     eax, eax
0x140042249  mov     rbx, [rsp+58h+arg_8]
0x14004224e  add     rsp, 50h
0x140042252  pop     rdi
0x140042253  retn
```
