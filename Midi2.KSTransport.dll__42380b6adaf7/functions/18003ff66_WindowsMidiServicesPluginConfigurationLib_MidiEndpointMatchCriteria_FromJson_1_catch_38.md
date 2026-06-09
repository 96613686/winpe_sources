# _WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson_::_1_::catch$38

- ea: `0x18003ff66`
- end: `0x18003ff92`
- name: `_WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson_::_1_::catch$38`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ff7a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ff7a`

## string_xrefs

- `0x18003ff73`: `Exception parsing MIDI Endpoint Match JSON.`

## pseudocode

```c
__int64 WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson_::_1_::catch_38()
{
  OutputDebugStringW(L"Exception parsing MIDI Endpoint Match JSON.");
  return 0;
}

```

## disassembly

```asm
0x18003ff66  mov     [rsp+arg_8], rdx
0x18003ff6b  push    rbp
0x18003ff6c  sub     rsp, 20h
0x18003ff70  mov     rbp, rdx
0x18003ff73  lea     rcx, aExceptionParsi_0; "Exception parsing MIDI Endpoint Match J"...
0x18003ff7a  call    cs:__imp_OutputDebugStringW
0x18003ff80  nop
0x18003ff81  mov     rax, 0
0x18003ff8b  add     rsp, 20h
0x18003ff8f  pop     rbp
0x18003ff90  retn
```
