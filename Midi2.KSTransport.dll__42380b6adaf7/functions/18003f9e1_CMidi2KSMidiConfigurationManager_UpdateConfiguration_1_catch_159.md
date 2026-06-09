# _CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch$159

- ea: `0x18003f9e1`
- end: `0x18003fab3`
- name: `_CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch$159`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180002098`
- `0x18000db18`
- `0x18003f9e1`
- `0x180041010`

## string_xrefs

- `0x18003fa47`: `CMidi2KSMidiConfigurationManager::UpdateConfiguration`
- `0x18003fa2b`: `std exception processing json`

## pseudocode

```c
__int64 __fastcall CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch_159(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rbx
  int v4; // r8d
  int v5; // r9d

  v3 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v3 > 2u )
  {
    *(_QWORD *)(a2 + 456) = *(_QWORD *)(a2 + 456);
    *(_QWORD *)(a2 + 472) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 368) + 8LL))(*(_QWORD *)(a2 + 368));
    *(_QWORD *)(a2 + 128) = L"std exception processing json";
    *(_QWORD *)(a2 + 152) = *(_QWORD *)(a2 + 448);
    *(_QWORD *)(a2 + 168) = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v3,
      (unsigned int)&dword_180068CCC,
      v4,
      v5,
      a2 + 168,
      a2 + 152,
      a2 + 128,
      a2 + 472,
      a2 + 456);
  }
  return 0;
}

```

## disassembly

```asm
0x18003f9e1  mov     [rsp+arg_8], rdx
0x18003f9e6  push    rbx
0x18003f9e7  push    rbp
0x18003f9e8  sub     rsp, 58h
0x18003f9ec  mov     rbp, rdx
0x18003f9ef  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18003f9f4  mov     rbx, [rax+8]
0x18003f9f8  mov     eax, [rbx]
0x18003f9fa  cmp     eax, 2
0x18003f9fd  jbe     loc_18003FAA1
0x18003fa03  mov     rax, [rbp+1C8h]
0x18003fa0a  mov     [rbp+1C8h], rax
0x18003fa11  mov     rcx, [rbp+170h]
0x18003fa18  mov     rax, [rcx]
0x18003fa1b  mov     rax, [rax+8]
0x18003fa1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa24  mov     [rbp+1D8h], rax
0x18003fa2b  lea     rax, aStdExceptionPr; "std exception processing json"
0x18003fa32  mov     [rbp+80h], rax
0x18003fa39  mov     rax, [rbp+1C0h]
0x18003fa40  mov     [rbp+98h], rax
0x18003fa47  lea     rax, aCmidi2ksmidico_2; "CMidi2KSMidiConfigurationManager::Updat"...
0x18003fa4e  mov     [rbp+0A8h], rax
0x18003fa55  lea     rax, [rbp+1C8h]
0x18003fa5c  mov     [rsp+68h+var_28], rax
0x18003fa61  lea     rax, [rbp+1D8h]
0x18003fa68  mov     [rsp+68h+var_30], rax
0x18003fa6d  lea     rax, [rbp+80h]
0x18003fa74  mov     [rsp+68h+var_38], rax
0x18003fa79  lea     rax, [rbp+98h]
0x18003fa80  mov     [rsp+68h+var_40], rax
0x18003fa85  lea     rax, [rbp+0A8h]
0x18003fa8c  mov     [rsp+68h+var_48], rax
0x18003fa91  lea     rdx, dword_180068CCC
0x18003fa98  mov     rcx, rbx
0x18003fa9b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@35@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003faa0  nop
0x18003faa1  mov     rax, 0
0x18003faab  add     rsp, 58h
0x18003faaf  pop     rbp
0x18003fab0  pop     rbx
0x18003fab1  retn
```
