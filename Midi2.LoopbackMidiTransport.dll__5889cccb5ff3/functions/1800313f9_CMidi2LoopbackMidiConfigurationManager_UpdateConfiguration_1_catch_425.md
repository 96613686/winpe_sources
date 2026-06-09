# _CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch$425

- ea: `0x1800313f9`
- end: `0x1800314b9`
- name: `_CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch$425`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180001ae0`
- `0x18000ccd8`
- `0x1800313f9`
- `0x180032010`

## string_xrefs

- `0x180031459`: `CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration`
- `0x180031440`: `std exception processing json`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration_::_1_::catch_425(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx
  int v4; // r8d
  int v5; // r9d

  v3 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v3 > 2u )
  {
    *(_QWORD *)(a2 + 352) = *(_QWORD *)(a2 + 368);
    *(_QWORD *)(a2 + 104) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 648) + 8LL))(*(_QWORD *)(a2 + 648));
    *(_QWORD *)(a2 + 368) = L"std exception processing json";
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a2 + 816);
    *(_QWORD *)(a2 + 112) = "CMidi2LoopbackMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v3,
      (unsigned int)byte_180058115,
      v4,
      v5,
      a2 + 112,
      a2 + 88,
      a2 + 368,
      a2 + 104,
      a2 + 352);
  }
  return 0;
}

```

## disassembly

```asm
0x1800313f9  mov     [rsp+arg_8], rdx
0x1800313fe  push    rbx
0x1800313ff  push    rbp
0x180031400  sub     rsp, 58h
0x180031404  mov     rbp, rdx
0x180031407  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18003140c  mov     rbx, [rax+8]
0x180031410  mov     eax, [rbx]
0x180031412  cmp     eax, 2
0x180031415  jbe     loc_1800314A7
0x18003141b  mov     rax, [rbp+170h]
0x180031422  mov     [rbp+160h], rax
0x180031429  mov     rcx, [rbp+288h]
0x180031430  mov     rax, [rcx]
0x180031433  mov     rax, [rax+8]
0x180031437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003143c  mov     [rbp+68h], rax
0x180031440  lea     rax, aStdExceptionPr; "std exception processing json"
0x180031447  mov     [rbp+170h], rax
0x18003144e  mov     rax, [rbp+330h]
0x180031455  mov     [rbp+58h], rax
0x180031459  lea     rax, aCmidi2loopback_6; "CMidi2LoopbackMidiConfigurationManager:"...
0x180031460  mov     [rbp+70h], rax
0x180031464  lea     rax, [rbp+160h]
0x18003146b  mov     [rsp+68h+var_28], rax
0x180031470  lea     rax, [rbp+68h]
0x180031474  mov     [rsp+68h+var_30], rax
0x180031479  lea     rax, [rbp+170h]
0x180031480  mov     [rsp+68h+var_38], rax
0x180031485  lea     rax, [rbp+58h]
0x180031489  mov     [rsp+68h+var_40], rax
0x18003148e  lea     rax, [rbp+70h]
0x180031492  mov     [rsp+68h+var_48], rax
0x180031497  lea     rdx, byte_180058115
0x18003149e  mov     rcx, rbx
0x1800314a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@35@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800314a6  nop
0x1800314a7  mov     rax, 0
0x1800314b1  add     rsp, 58h
0x1800314b5  pop     rbp
0x1800314b6  pop     rbx
0x1800314b7  retn
```
