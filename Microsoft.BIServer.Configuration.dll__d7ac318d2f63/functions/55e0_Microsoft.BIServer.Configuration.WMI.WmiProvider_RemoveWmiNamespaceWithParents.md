# Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespaceWithParents

- ea: `0x55e0`
- end: `0x563b`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespaceWithParents`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5530`
- `0x55e0`

## callees

- `0x5580`
- `0x55e0`
- `0x5640`

## string_xrefs

- `0x561f`: `Namespace {0} is empty and is being removed.`

## pseudocode

```c

```

## disassembly

```asm
0x55e0  ldarg.1
0x55e1  ldstr    asc_94A6// "\\"
0x55e6  ldc.i4.5
0x55e7  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x55ec  stloc.0
0x55ed  ldloc.0
0x55ee  ldc.i4.0
0x55ef  ble.s    loc_563A
0x55f1  ldarg.1
0x55f2  ldc.i4.0
0x55f3  ldloc.0
0x55f4  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x55f9  stloc.1
0x55fa  ldarg.1
0x55fb  ldloc.0
0x55fc  ldc.i4.1
0x55fd  add
0x55fe  ldarg.1
0x55ff  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5604  ldloc.0
0x5605  sub
0x5606  ldc.i4.1
0x5607  sub
0x5608  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x560d  stloc.2
0x560e  ldarg.0
0x560f  ldloc.1
0x5610  ldloc.2
0x5611  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespace(string wmiPath, string namespaceName)
0x5616  ldarg.0
0x5617  ldloc.1
0x5618  call     instance bool Microsoft.BIServer.Configuration.WMI.WmiProvider::IsNamespaceEmpty(string wmiPath)
0x561d  brfalse.s loc_563A
0x561f  ldstr    aNamespace0IsEm// "Namespace {0} is empty and is being rem"...
0x5624  ldc.i4.1
0x5625  newarr   [mscorlib]System.Object
0x562a  dup
0x562b  ldc.i4.0
0x562c  ldloc.1
0x562d  stelem.ref
0x562e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5633  ldarg.0
0x5634  ldloc.1
0x5635  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespaceWithParents(string wmiPath)
0x563a  ret
```
