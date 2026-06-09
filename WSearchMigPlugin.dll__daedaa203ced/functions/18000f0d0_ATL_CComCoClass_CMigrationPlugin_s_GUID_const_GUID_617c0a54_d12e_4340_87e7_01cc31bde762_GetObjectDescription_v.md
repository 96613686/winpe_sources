# ATL::CComCoClass<CMigrationPlugin,&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762>::GetObjectDescription(void)

- ea: `0x18000f0d0`
- end: `0x18000f0d3`
- name: `?GetObjectDescription@?$CComCoClass@VCMigrationPlugin@@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B@ATL@@SAPEB_WXZ`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002918`

## pseudocode

```c
__int64 ATL::CComCoClass<CMigrationPlugin,&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762>::GetObjectDescription()
{
  return 0;
}

```

## disassembly

```asm
0x18000f0d0  xor     eax, eax
0x18000f0d2  retn
```
