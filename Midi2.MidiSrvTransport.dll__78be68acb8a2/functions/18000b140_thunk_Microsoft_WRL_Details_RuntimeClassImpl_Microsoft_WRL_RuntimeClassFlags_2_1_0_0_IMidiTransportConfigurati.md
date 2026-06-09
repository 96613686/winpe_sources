# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef`adjustor{8}' (void)

- ea: `0x18000b140`
- end: `0x18000b149`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b110`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000b140  sub     rcx, 8
0x18000b144  jmp     ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef(void)
```
