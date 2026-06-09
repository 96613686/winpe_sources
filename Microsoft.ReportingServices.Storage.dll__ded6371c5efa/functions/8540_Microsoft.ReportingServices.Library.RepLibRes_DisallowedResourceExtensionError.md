# Microsoft.ReportingServices.Library.RepLibRes::DisallowedResourceExtensionError

- ea: `0x8540`
- end: `0x854c`
- name: `Microsoft.ReportingServices.Library.RepLibRes::DisallowedResourceExtensionError`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x9890`

## string_xrefs

- `0x8540`: `DisallowedResourceExtensionError`

## pseudocode

```c

```

## disassembly

```asm
0x8540  ldstr    aDisallowedreso// "DisallowedResourceExtensionError"
0x8545  ldarg.0
0x8546  call     string Keys::GetString(string key, object arg0)
0x854b  ret
```
