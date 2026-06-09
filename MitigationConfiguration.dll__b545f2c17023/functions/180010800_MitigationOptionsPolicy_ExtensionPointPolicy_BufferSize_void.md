# MitigationOptionsPolicy::ExtensionPointPolicy::BufferSize(void)

- ea: `0x180010800`
- end: `0x180010806`
- name: `?BufferSize@ExtensionPointPolicy@MitigationOptionsPolicy@@UEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(MitigationOptionsPolicy::ExtensionPointPolicy *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::ExtensionPointPolicy::BufferSize(
        MitigationOptionsPolicy::ExtensionPointPolicy *this)
{
  return 8;
}

```

## disassembly

```asm
0x180010800  mov     eax, 8
0x180010805  retn
```
