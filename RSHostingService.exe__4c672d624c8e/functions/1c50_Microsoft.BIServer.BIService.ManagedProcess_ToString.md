# Microsoft.BIServer.BIService.ManagedProcess::ToString

- ea: `0x1c50`
- end: `0x1d86`
- name: `Microsoft.BIServer.BIService.ManagedProcess::ToString`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a90`
- `0x1bd0`
- `0x1c50`
- `0x1fa0`
- `0x20d0`
- `0x20f0`
- `0x2110`
- `0x2190`

## string_xrefs

- `0x1cb8`: `\n  path: `

## pseudocode

```c

```

## disassembly

```asm
0x1c50  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1c55  stloc.0
0x1c56  ldloc.0
0x1c57  ldstr    aName_0// "\n  name: "
0x1c5c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c61  ldarg.0
0x1c62  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1c67  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1c6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c71  ldstr    aIs// " is "
0x1c76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c7b  ldarg.0
0x1c7c  call     instance bool Microsoft.BIServer.BIService.ManagedProcess::IsRunning()
0x1c81  brtrue.s loc_1C8A
0x1c83  ldstr    aStopped// "STOPPED"
0x1c88  br.s     loc_1C8F
0x1c8a  ldstr    aRunning// "RUNNING"
0x1c8f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c94  pop
0x1c95  ldarg.0
0x1c96  ldfld    bool Microsoft.BIServer.BIService.ManagedProcess::_isManagementProcess
0x1c9b  brfalse.s loc_1CAB
0x1c9d  ldloc.0
0x1c9e  ldstr    aManagement// "\n  [Management]"
0x1ca3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ca8  pop
0x1ca9  br.s     loc_1CB7
0x1cab  ldloc.0
0x1cac  ldstr    aWorker// "\n  [Worker]"
0x1cb1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cb6  pop
0x1cb7  ldloc.0
0x1cb8  ldstr    aPath// "\n  path: "
0x1cbd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cc2  ldarg.0
0x1cc3  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1cc8  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Path()
0x1ccd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cd2  ldstr    aResolvesTo// " Resolves to "
0x1cd7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cdc  ldarg.0
0x1cdd  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1ce2  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Path()
0x1ce7  call     string Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory(string relativeDirectory)
0x1cec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cf1  pop
0x1cf2  ldloc.0
0x1cf3  ldstr    aParameters// "\n  parameters: ["
0x1cf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1cfd  ldarg.0
0x1cfe  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1d03  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Parameters()
0x1d08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d0d  ldstr    asc_6306// "]"
0x1d12  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d17  pop
0x1d18  ldarg.0
0x1d19  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1d1e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x1d23  brfalse.s loc_1D7F
0x1d25  ldloc.0
0x1d26  ldstr    aEnvironmentVar// "\n  Environment Variables:"
0x1d2b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d30  pop
0x1d31  ldarg.0
0x1d32  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1d37  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x1d3c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x1d41  stloc.1
0x1d42  br.s     loc_1D66
0x1d44  ldloca.s 1
0x1d46  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x1d4b  stloc.2
0x1d4c  ldloc.0
0x1d4d  ldstr    a01// "\n    {0} = {1}"
0x1d52  ldloca.s 2
0x1d54  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1d59  ldloca.s 2
0x1d5b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x1d60  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x1d65  pop
0x1d66  ldloca.s 1
0x1d68  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x1d6d  brtrue.s loc_1D44
0x1d6f  leave.s  loc_1D7F
0x1d71  ldloca.s 1
0x1d73  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x1d79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d7e  endfinally
0x1d7f  ldloc.0
0x1d80  callvirt instance string [mscorlib]System.Object::ToString()
0x1d85  ret
```
