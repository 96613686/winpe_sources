# Microsoft.VisualStudio.Setup.Cache.ErrorState::set_LogFilePath

- ea: `0x19420`
- end: `0x19433`
- name: `Microsoft.VisualStudio.Setup.Cache.ErrorState::set_LogFilePath`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x19428`: `LogFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x19420  ldarg.0
0x19421  ldarg.0
0x19422  ldflda   string Microsoft.VisualStudio.Setup.Cache.ErrorState::logFilePath
0x19427  ldarg.1
0x19428  ldstr    aLogfilepath// "LogFilePath"
0x1942d  call     T0x2B0000C3
0x19432  ret
```
