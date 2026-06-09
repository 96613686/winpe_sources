# _WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson_::_1_::catch$38

- ea: `0x18005c709`
- end: `0x18005c735`
- name: `_WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson_::_1_::catch$38`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005c71d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005c71d`

## string_xrefs

- `0x18005c716`: `Exception parsing MIDI Endpoint Match JSON.`

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
0x18005c709  mov     [rsp+arg_8], rdx
0x18005c70e  push    rbp
0x18005c70f  sub     rsp, 20h
0x18005c713  mov     rbp, rdx
0x18005c716  lea     rcx, aExceptionParsi_0; "Exception parsing MIDI Endpoint Match J"...
0x18005c71d  call    cs:__imp_OutputDebugStringW
0x18005c723  nop
0x18005c724  mov     rax, 0
0x18005c72e  add     rsp, 20h
0x18005c732  pop     rbp
0x18005c733  retn
```
