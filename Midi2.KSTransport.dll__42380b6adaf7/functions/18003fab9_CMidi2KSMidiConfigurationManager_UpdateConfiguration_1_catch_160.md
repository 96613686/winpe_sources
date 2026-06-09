# _CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch$160

- ea: `0x18003fab9`
- end: `0x18003fb5c`
- name: `_CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch$160`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x180001c20`
- `0x18000db18`
- `0x18003fab9`

## string_xrefs

- `0x18003fb00`: `CMidi2KSMidiConfigurationManager::UpdateConfiguration`
- `0x18003fae4`: `Other exception processing json`

## pseudocode

```c
__int64 __fastcall CMidi2KSMidiConfigurationManager::UpdateConfiguration_::_1_::catch_160(__int64 a1, _QWORD *a2)
{
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d

  v3 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v3 > 2u )
  {
    a2[57] = a2[57];
    a2[59] = L"Other exception processing json";
    a2[16] = a2[56];
    a2[19] = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v3,
      (unsigned int)byte_180068C93,
      v4,
      v5,
      (__int64)(a2 + 19),
      (__int64)(a2 + 16),
      (__int64)(a2 + 59),
      (__int64)(a2 + 57));
  }
  return 0;
}

```

## disassembly

```asm
0x18003fab9  mov     [rsp+arg_8], rdx
0x18003fabe  push    rbp
0x18003fabf  sub     rsp, 50h
0x18003fac3  mov     rbp, rdx
0x18003fac6  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18003facb  mov     rcx, [rax+8]
0x18003facf  mov     eax, [rcx]
0x18003fad1  cmp     eax, 2
0x18003fad4  jbe     short loc_18003FB4B
0x18003fad6  mov     rax, [rbp+1C8h]
0x18003fadd  mov     [rbp+1C8h], rax
0x18003fae4  lea     rax, aOtherException; "Other exception processing json"
0x18003faeb  mov     [rbp+1D8h], rax
0x18003faf2  mov     rax, [rbp+1C0h]
0x18003faf9  mov     [rbp+80h], rax
0x18003fb00  lea     rax, aCmidi2ksmidico_2; "CMidi2KSMidiConfigurationManager::Updat"...
0x18003fb07  mov     [rbp+98h], rax
0x18003fb0e  lea     rax, [rbp+1C8h]
0x18003fb15  mov     [rsp+58h+var_20], rax
0x18003fb1a  lea     rax, [rbp+1D8h]
0x18003fb21  mov     [rsp+58h+var_28], rax
0x18003fb26  lea     rax, [rbp+80h]
0x18003fb2d  mov     [rsp+58h+var_30], rax
0x18003fb32  lea     rax, [rbp+98h]
0x18003fb39  mov     [rsp+58h+var_38], rax
0x18003fb3e  lea     rdx, byte_180068C93
0x18003fb45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003fb4a  nop
0x18003fb4b  mov     rax, 0
0x18003fb55  add     rsp, 50h
0x18003fb59  pop     rbp
0x18003fb5a  retn
```
