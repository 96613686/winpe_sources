# Windows::Services::Cortana::CortanaSettings::InternalGetRuntimeClassName(void)

- ea: `0x18000c3d0`
- end: `0x18000c3d8`
- name: `?InternalGetRuntimeClassName@CortanaSettings@Cortana@Services@Windows@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task`

## string_xrefs

- `0x18000c3d0`: `Windows.Services.Cortana.CortanaSettings`

## pseudocode

```c
const unsigned __int16 *Windows::Services::Cortana::CortanaSettings::InternalGetRuntimeClassName(void)
{
  return L"Windows.Services.Cortana.CortanaSettings";
}

```

## disassembly

```asm
0x18000c3d0  lea     rax, ?RuntimeClass_Windows_Services_Cortana_CortanaSettings@@3QBGB; "Windows.Services.Cortana.CortanaSetting"...
0x18000c3d7  retn
```
