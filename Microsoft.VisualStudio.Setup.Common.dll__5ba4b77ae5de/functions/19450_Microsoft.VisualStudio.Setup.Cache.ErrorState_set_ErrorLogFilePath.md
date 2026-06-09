# Microsoft.VisualStudio.Setup.Cache.ErrorState::set_ErrorLogFilePath

- ea: `0x19450`
- end: `0x19463`
- name: `Microsoft.VisualStudio.Setup.Cache.ErrorState::set_ErrorLogFilePath`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x19458`: `ErrorLogFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x19450  ldarg.0
0x19451  ldarg.0
0x19452  ldflda   string Microsoft.VisualStudio.Setup.Cache.ErrorState::errorLogFilePath
0x19457  ldarg.1
0x19458  ldstr    aErrorlogfilepa// "ErrorLogFilePath"
0x1945d  call     T0x2B0000C3
0x19462  ret
```
