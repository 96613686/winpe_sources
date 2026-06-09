# NGenTask.TaskExecutive::IsPostRebootFlagSet

- ea: `0x21e0`
- end: `0x221b`
- name: `NGenTask.TaskExecutive::IsPostRebootFlagSet`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x24f0`

## callees

- `0x20a0`
- `0x21e0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x21e0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x21e5  ldarg.0
0x21e6  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x21eb  ldstr    aStatePendingre// "State\\PendingReboot"
0x21f0  call     string [mscorlib]System.String::Concat(string, string)
0x21f5  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x21fa  stloc.0
0x21fb  ldloc.0
0x21fc  ldnull
0x21fd  cgt.un
0x21ff  stloc.1
0x2200  leave.s  loc_2219
0x2202  stloc.2
0x2203  ldc.i4.0
0x2204  ldloc.2
0x2205  ldstr    aErrorAtPostreb// "Error at PostReboot flag check"
0x220a  ldc.i4.0
0x220b  newarr   [mscorlib]System.Object
0x2210  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2215  ldc.i4.0
0x2216  stloc.1
0x2217  leave.s  loc_2219
0x2219  ldloc.1
0x221a  ret
```
