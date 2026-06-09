# NGenTask.TaskExecutive::MinDaysInDisuse

- ea: `0x1f90`
- end: `0x2017`
- name: `NGenTask.TaskExecutive::MinDaysInDisuse`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x1f90`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x1f90  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1f95  ldstr    aSoftwareMicros_0// "Software\\Microsoft\\Windows\\CurrentVe"...
0x1f9a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1f9f  stloc.0
0x1fa0  ldloc.0
0x1fa1  brtrue.s loc_1FAF
0x1fa3  ldloca.s 2
0x1fa5  initobj  valuetype [mscorlib]System.Nullable`1<float64>
0x1fab  ldloc.2
0x1fac  stloc.2
0x1fad  leave.s  loc_2015
0x1faf  ldloc.0
0x1fb0  ldstr    aMindaysindisus// "MinDaysInDisuse"
0x1fb5  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1fba  stloc.1
0x1fbb  ldloc.1
0x1fbc  brfalse.s loc_1FCF
0x1fbe  ldloc.1
0x1fbf  isinst   [mscorlib]System.Int32
0x1fc4  brfalse.s loc_1FCF
0x1fc6  ldloc.1
0x1fc7  unbox.any [mscorlib]System.Int32
0x1fcc  ldc.i4.0
0x1fcd  bgt.s    loc_1FDB
0x1fcf  ldloca.s 3
0x1fd1  initobj  valuetype [mscorlib]System.Nullable`1<float64>
0x1fd7  ldloc.3
0x1fd8  stloc.2
0x1fd9  leave.s  loc_2015
0x1fdb  ldloc.1
0x1fdc  unbox.any [mscorlib]System.Int32
0x1fe1  conv.r8
0x1fe2  newobj   instance void valuetype [mscorlib]System.Nullable`1<float64>::.ctor(var<u1>)
0x1fe7  stloc.2
0x1fe8  leave.s  loc_2015
0x1fea  ldloc.0
0x1feb  brfalse.s loc_1FF3
0x1fed  ldloc.0
0x1fee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff3  endfinally
0x1ff4  stloc.s  4
0x1ff6  ldc.i4.0
0x1ff7  ldloc.s  4
0x1ff9  ldstr    aErrorRetrievin_0// "Error retrieving value of MinDaysInDisu"...
0x1ffe  ldc.i4.0
0x1fff  newarr   [mscorlib]System.Object
0x2004  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2009  ldloca.s 3
0x200b  initobj  valuetype [mscorlib]System.Nullable`1<float64>
0x2011  ldloc.3
0x2012  stloc.2
0x2013  leave.s  loc_2015
0x2015  ldloc.2
0x2016  ret
```
