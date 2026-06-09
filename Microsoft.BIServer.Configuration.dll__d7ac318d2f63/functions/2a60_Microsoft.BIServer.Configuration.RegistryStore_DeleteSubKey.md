# Microsoft.BIServer.Configuration.RegistryStore::DeleteSubKey

- ea: `0x2a60`
- end: `0x2aad`
- name: `Microsoft.BIServer.Configuration.RegistryStore::DeleteSubKey`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x2a60`
- `0x2ae0`

## string_xrefs

- `0x2a6b`: `REGISTRY: Delete {0} {1}`
- `0x2a92`: `Could not remove registry key {0} from parent {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2a60  ldarg.0
0x2a61  ldarg.1
0x2a62  call     instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::GetSubKey(string subKeyName)
0x2a67  stloc.0
0x2a68  ldloc.0
0x2a69  brfalse.s loc_2A90
0x2a6b  ldstr    aRegistryDelete// "REGISTRY: Delete {0} {1}"
0x2a70  ldc.i4.2
0x2a71  newarr   [mscorlib]System.Object
0x2a76  dup
0x2a77  ldc.i4.0
0x2a78  ldloc.0
0x2a79  callvirt instance string [mscorlib]System.Object::ToString()
0x2a7e  stelem.ref
0x2a7f  dup
0x2a80  ldc.i4.1
0x2a81  ldarg.2
0x2a82  stelem.ref
0x2a83  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2a88  ldloc.0
0x2a89  ldarg.2
0x2a8a  ldc.i4.0
0x2a8b  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string, bool)
0x2a90  leave.s  loc_2AAC
0x2a92  ldstr    aCouldNotRemove// "Could not remove registry key {0} from "...
0x2a97  ldc.i4.2
0x2a98  newarr   [mscorlib]System.Object
0x2a9d  dup
0x2a9e  ldc.i4.0
0x2a9f  ldarg.2
0x2aa0  stelem.ref
0x2aa1  dup
0x2aa2  ldc.i4.1
0x2aa3  ldarg.1
0x2aa4  stelem.ref
0x2aa5  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x2aaa  leave.s  loc_2AAC
0x2aac  ret
```
