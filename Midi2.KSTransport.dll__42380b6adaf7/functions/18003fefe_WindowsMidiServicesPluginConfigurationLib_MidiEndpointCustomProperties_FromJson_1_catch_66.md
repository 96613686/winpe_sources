# _WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson_::_1_::catch$66

- ea: `0x18003fefe`
- end: `0x18003ff2a`
- name: `_WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson_::_1_::catch$66`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ff12`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ff12`

## string_xrefs

- `0x18003ff0b`: `Exception parsing MIDI Endpoint Custom Properties JSON.`

## pseudocode

```c
__int64 WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson_::_1_::catch_66()
{
  OutputDebugStringW(L"Exception parsing MIDI Endpoint Custom Properties JSON.");
  return 0;
}

```

## disassembly

```asm
0x18003fefe  mov     [rsp+arg_8], rdx
0x18003ff03  push    rbp
0x18003ff04  sub     rsp, 20h
0x18003ff08  mov     rbp, rdx
0x18003ff0b  lea     rcx, OutputString; "Exception parsing MIDI Endpoint Custom "...
0x18003ff12  call    cs:__imp_OutputDebugStringW
0x18003ff18  nop
0x18003ff19  mov     rax, 0
0x18003ff23  add     rsp, 20h
0x18003ff27  pop     rbp
0x18003ff28  retn
```
