# NGenTask.TaskExecutive::IsFramework35Installed

- ea: `0x20e0`
- end: `0x2141`
- name: `NGenTask.TaskExecutive::IsFramework35Installed`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x20e0`
- `0x2c60`

## string_xrefs

- `0x212b`: `Unable to determine if .NET 3.5 is installed`

## pseudocode

```c

```

## disassembly

```asm
0x20e0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x20e5  ldstr    aSoftwareMicros_4// "Software\\Microsoft\\.NETFramework\\pol"...
0x20ea  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x20ef  stloc.0
0x20f0  ldloc.0
0x20f1  brfalse.s loc_2118
0x20f3  ldloc.0
0x20f4  ldstr    a50727// "50727"
0x20f9  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x20fe  isinst   [mscorlib]System.String
0x2103  stloc.1
0x2104  ldloc.1
0x2105  brfalse.s loc_2118
0x2107  ldloc.1
0x2108  ldstr    a5072750727// "50727-50727"
0x210d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2112  brfalse.s loc_2118
0x2114  ldc.i4.1
0x2115  stloc.2
0x2116  leave.s  loc_213F
0x2118  leave.s  loc_2124
0x211a  ldloc.0
0x211b  brfalse.s loc_2123
0x211d  ldloc.0
0x211e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2123  endfinally
0x2124  ldc.i4.0
0x2125  stloc.2
0x2126  leave.s  loc_213F
0x2128  stloc.3
0x2129  ldc.i4.0
0x212a  ldloc.3
0x212b  ldstr    aUnableToDeterm// "Unable to determine if .NET 3.5 is inst"...
0x2130  ldc.i4.0
0x2131  newarr   [mscorlib]System.Object
0x2136  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x213b  ldc.i4.1
0x213c  stloc.2
0x213d  leave.s  loc_213F
0x213f  ldloc.2
0x2140  ret
```
