# System.Deployment.Application.Logger::GetRegitsryBasedLogFilePath

- ea: `0x170a0`
- end: `0x170df`
- name: `System.Deployment.Application.Logger::GetRegitsryBasedLogFilePath`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x17180`

## callees

- `0x170a0`

## string_xrefs

- `0x170b6`: `LogFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x170a0  ldnull
0x170a1  stloc.0
0x170a2  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0x170a7  ldstr    aSoftwareClasse// "SOFTWARE\\Classes\\Software\\Microsoft"...
0x170ac  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x170b1  stloc.1
0x170b2  ldloc.1
0x170b3  brfalse.s loc_170C6
0x170b5  ldloc.1
0x170b6  ldstr    aLogfilepath// "LogFilePath"
0x170bb  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x170c0  isinst   [mscorlib]System.String
0x170c5  stloc.0
0x170c6  leave.s  loc_170D2
0x170c8  ldloc.1
0x170c9  brfalse.s loc_170D1
0x170cb  ldloc.1
0x170cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x170d1  endfinally
0x170d2  leave.s  loc_170DD
0x170d4  pop
0x170d5  leave.s  loc_170DD
0x170d7  pop
0x170d8  leave.s  loc_170DD
0x170da  pop
0x170db  leave.s  loc_170DD
0x170dd  ldloc.0
0x170de  ret
```
