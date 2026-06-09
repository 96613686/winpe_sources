# _WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson_::_1_::catch$66

- ea: `0x18005c66b`
- end: `0x18005c697`
- name: `_WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson_::_1_::catch$66`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005c67f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005c67f`

## string_xrefs

- `0x18005c678`: `Exception parsing MIDI Endpoint Custom Properties JSON.`

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
0x18005c66b  mov     [rsp+arg_8], rdx
0x18005c670  push    rbp
0x18005c671  sub     rsp, 20h
0x18005c675  mov     rbp, rdx
0x18005c678  lea     rcx, OutputString; "Exception parsing MIDI Endpoint Custom "...
0x18005c67f  call    cs:__imp_OutputDebugStringW
0x18005c685  nop
0x18005c686  mov     rax, 0
0x18005c690  add     rsp, 20h
0x18005c694  pop     rbp
0x18005c695  retn
```
