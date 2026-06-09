# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef(void)

- ea: `0x18000b110`
- end: `0x18000b139`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@UIMidiServicePluginMetadataReporter@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b140`

## callees

- `0x18000b110`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager,IMidiServicePluginMetadataReporter>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 20);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000b110  mov     r9d, 7FFFFFFFh
0x18000b116  jmp     short loc_18000B126
0x18000b118  lea     edx, [r8+1]
0x18000b11c  mov     eax, r8d
0x18000b11f  lock cmpxchg [rcx+14h], edx
0x18000b124  jz      short loc_18000B131
0x18000b126  mov     r8d, [rcx+14h]
0x18000b12a  cmp     r8d, r9d
0x18000b12d  jnz     short loc_18000B118
0x18000b12f  jmp     short loc_18000B135
0x18000b131  lea     r9d, [r8+1]
0x18000b135  mov     eax, r9d
0x18000b138  retn
```
