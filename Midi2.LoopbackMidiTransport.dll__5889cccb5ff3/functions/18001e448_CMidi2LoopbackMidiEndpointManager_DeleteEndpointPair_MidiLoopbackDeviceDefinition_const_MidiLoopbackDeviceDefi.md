# CMidi2LoopbackMidiEndpointManager::DeleteEndpointPair(MidiLoopbackDeviceDefinition const &,MidiLoopbackDeviceDefinition const &)

- ea: `0x18001e448`
- end: `0x18001e503`
- name: `?DeleteEndpointPair@CMidi2LoopbackMidiEndpointManager@@QEAAJAEBUMidiLoopbackDeviceDefinition@@0@Z`
- size: `187`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiEndpointManager *__hidden this, const struct MidiLoopbackDeviceDefinition *, const struct MidiLoopbackDeviceDefinition *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018710`

## callees

- `0x180001a38`
- `0x18000ccd8`
- `0x18001b624`
- `0x18001e448`
- `0x18001e50c`

## string_xrefs

- `0x18001e470`: `CMidi2LoopbackMidiEndpointManager::DeleteEndpointPair`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::DeleteEndpointPair(
        CMidi2LoopbackMidiEndpointManager *this,
        const struct MidiLoopbackDeviceDefinition *a2,
        const struct MidiLoopbackDeviceDefinition *a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // eax
  int v12; // [rsp+20h] [rbp-28h]
  int v13[2]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2LoopbackMidiEndpointManager *v15; // [rsp+68h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v15 = this;
    *(_QWORD *)v13 = "CMidi2LoopbackMidiEndpointManager::DeleteEndpointPair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)qword_180058738,
      v7,
      v8,
      (__int64)v13,
      (__int64)&v15);
  }
  v9 = CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(this, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)(unsigned int)v9,
      v12);
  v10 = CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(this, a3);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)(unsigned int)v10,
      v12);
  return 0;
}

```

## disassembly

```asm
0x18001e448  mov     [rsp+arg_0], rbx
0x18001e44d  mov     [rsp+arg_8], rsi
0x18001e452  push    rdi
0x18001e453  sub     rsp, 40h
0x18001e457  mov     rsi, r8
0x18001e45a  mov     rdi, rdx
0x18001e45d  mov     rbx, rcx
0x18001e460  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001e465  mov     rcx, [rax+8]
0x18001e469  mov     eax, [rcx]
0x18001e46b  cmp     eax, 4
0x18001e46e  jbe     short loc_18001E4A1
0x18001e470  lea     rax, aCmidi2loopback_11; "CMidi2LoopbackMidiEndpointManager::Dele"...
0x18001e477  mov     [rsp+48h+arg_18], rbx
0x18001e47c  mov     qword ptr [rsp+48h+var_18], rax
0x18001e481  lea     rdx, qword_180058738
0x18001e488  lea     rax, [rsp+48h+arg_18]
0x18001e48d  mov     [rsp+48h+var_20], rax
0x18001e492  lea     rax, [rsp+48h+var_18]
0x18001e497  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001e49c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001e4a1  mov     rdx, rdi; struct MidiLoopbackDeviceDefinition *
0x18001e4a4  mov     rcx, rbx; this
0x18001e4a7  call    ?DeleteSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJAEBUMidiLoopbackDeviceDefinition@@@Z; CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(MidiLoopbackDeviceDefinition const &)
0x18001e4ac  test    eax, eax
0x18001e4ae  jns     short loc_18001E4C9
0x18001e4b0  mov     rcx, [rsp+48h]; this
0x18001e4b5  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001e4bc  mov     r9d, eax; char *
0x18001e4bf  mov     edx, 0BAh; void *
0x18001e4c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e4c9  mov     rdx, rsi; struct MidiLoopbackDeviceDefinition *
0x18001e4cc  mov     rcx, rbx; this
0x18001e4cf  call    ?DeleteSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJAEBUMidiLoopbackDeviceDefinition@@@Z; CMidi2LoopbackMidiEndpointManager::DeleteSingleEndpoint(MidiLoopbackDeviceDefinition const &)
0x18001e4d4  test    eax, eax
0x18001e4d6  jns     short loc_18001E4F1
0x18001e4d8  mov     rcx, [rsp+48h]; this
0x18001e4dd  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001e4e4  mov     r9d, eax; char *
0x18001e4e7  mov     edx, 0BBh; void *
0x18001e4ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e4f1  mov     rbx, [rsp+48h+arg_0]
0x18001e4f6  xor     eax, eax
0x18001e4f8  mov     rsi, [rsp+48h+arg_8]
0x18001e4fd  add     rsp, 40h
0x18001e501  pop     rdi
0x18001e502  retn
```
