# SPTelemetry::ModelUpdate::GetComponentName(void)

- ea: `0x140006200`
- end: `0x140006208`
- name: `?GetComponentName@ModelUpdate@SPTelemetry@@UEAAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(SPTelemetry::ModelUpdate *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x140006200`: `ModelUpdate`

## pseudocode

```c
const char *__fastcall SPTelemetry::ModelUpdate::GetComponentName(SPTelemetry::ModelUpdate *this)
{
  return "ModelUpdate";
}

```

## disassembly

```asm
0x140006200  lea     rax, aModelupdate; "ModelUpdate"
0x140006207  retn
```
