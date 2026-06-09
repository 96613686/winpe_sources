# Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_10

- ea: `0x1b1f0`
- end: `0x1b202`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_10`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1b000`

## string_xrefs

- `0x1b1f7`: `UsingGroupConfigFiles`

## pseudocode

```c

```

## disassembly

```asm
0x1b1f0  ldarg.0
0x1b1f1  ldarg.0
0x1b1f2  ldflda   bool Microsoft.VisualStudio.Setup.Cache.Instance::groupConfigsChanged
0x1b1f7  ldstr    aUsinggroupconf// "UsingGroupConfigFiles"
0x1b1fc  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged(bool& field, [opt] string propertyName)
0x1b201  ret
```
