# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`scalar deleting destructor'(uint)

- ea: `0x18000a970`
- end: `0x18000a998`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002494`
- `0x18000a970`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a970  push    rbx
0x18000a972  sub     rsp, 20h
0x18000a976  mov     dword ptr [rcx+14h], 0C0000001h
0x18000a97d  mov     rbx, rcx
0x18000a980  test    dl, 1
0x18000a983  jz      short loc_18000A98F
0x18000a985  mov     edx, 18h
0x18000a98a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a98f  mov     rax, rbx
0x18000a992  add     rsp, 20h
0x18000a996  pop     rbx
0x18000a997  retn
```
