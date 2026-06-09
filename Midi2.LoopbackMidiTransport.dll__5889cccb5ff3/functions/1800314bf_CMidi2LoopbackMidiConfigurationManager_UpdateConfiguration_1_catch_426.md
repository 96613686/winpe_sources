# _CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch$426

- ea: `0x1800314bf`
- end: `0x180031556`
- name: `_CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch$426`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x1800017d0`
- `0x18000ccd8`
- `0x1800314bf`

## string_xrefs

- `0x180031503`: `CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration`
- `0x1800314ea`: `Other exception processing json`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch_426(__int64 a1, _QWORD *a2)
{
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d

  v3 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v3 > 2u )
  {
    a2[44] = a2[46];
    a2[13] = L"Other exception processing json";
    a2[46] = a2[102];
    a2[11] = "CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v3,
      (unsigned int)&dword_1800580DC,
      v4,
      v5,
      (__int64)(a2 + 11),
      (__int64)(a2 + 46),
      (__int64)(a2 + 13),
      (__int64)(a2 + 44));
  }
  return 0;
}

```

## disassembly

```asm
0x1800314bf  mov     [rsp+arg_8], rdx
0x1800314c4  push    rbp
0x1800314c5  sub     rsp, 50h
0x1800314c9  mov     rbp, rdx
0x1800314cc  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x1800314d1  mov     rcx, [rax+8]
0x1800314d5  mov     eax, [rcx]
0x1800314d7  cmp     eax, 2
0x1800314da  jbe     short loc_180031545
0x1800314dc  mov     rax, [rbp+170h]
0x1800314e3  mov     [rbp+160h], rax
0x1800314ea  lea     rax, aOtherException; "Other exception processing json"
0x1800314f1  mov     [rbp+68h], rax
0x1800314f5  mov     rax, [rbp+330h]
0x1800314fc  mov     [rbp+170h], rax
0x180031503  lea     rax, aCmidi2loopback_6; "CMidi2LoopbackMidiConfigurationManager:"...
0x18003150a  mov     [rbp+58h], rax
0x18003150e  lea     rax, [rbp+160h]
0x180031515  mov     [rsp+58h+var_20], rax
0x18003151a  lea     rax, [rbp+68h]
0x18003151e  mov     [rsp+58h+var_28], rax
0x180031523  lea     rax, [rbp+170h]
0x18003152a  mov     [rsp+58h+var_30], rax
0x18003152f  lea     rax, [rbp+58h]
0x180031533  mov     [rsp+58h+var_38], rax
0x180031538  lea     rdx, dword_1800580DC
0x18003153f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180031544  nop
0x180031545  mov     rax, 0
0x18003154f  add     rsp, 50h
0x180031553  pop     rbp
0x180031554  retn
```
