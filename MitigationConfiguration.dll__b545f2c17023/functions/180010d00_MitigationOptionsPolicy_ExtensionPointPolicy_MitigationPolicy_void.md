# MitigationOptionsPolicy::ExtensionPointPolicy::MitigationPolicy(void)

- ea: `0x180010d00`
- end: `0x180010d06`
- name: `?MitigationPolicy@ExtensionPointPolicy@MitigationOptionsPolicy@@UEAA?AW4_IMAGE_MITIGATION_POLICY@@XZ`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## pseudocode

```c
__int64 MitigationOptionsPolicy::ExtensionPointPolicy::MitigationPolicy()
{
  return 6;
}

```

## disassembly

```asm
0x180010d00  mov     eax, 6
0x180010d05  retn
```
