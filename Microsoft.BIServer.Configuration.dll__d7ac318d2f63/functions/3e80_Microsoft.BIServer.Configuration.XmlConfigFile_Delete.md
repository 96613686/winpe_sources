# Microsoft.BIServer.Configuration.XmlConfigFile::Delete

- ea: `0x3e80`
- end: `0x3eaa`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::Delete`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x3e60`
- `0x3e80`

## string_xrefs

- `0x3e8f`: `Removing ConfigReader File [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x3e80  ldarg.0
0x3e81  call     string Microsoft.BIServer.Configuration.XmlConfigFile::GetFileFromDirectory(string installDir)
0x3e86  stloc.0
0x3e87  ldloc.0
0x3e88  call     bool [mscorlib]System.IO.File::Exists(string)
0x3e8d  brfalse.s loc_3EA9
0x3e8f  ldstr    aRemovingConfig// "Removing ConfigReader File [{0}]"
0x3e94  ldc.i4.1
0x3e95  newarr   [mscorlib]System.Object
0x3e9a  dup
0x3e9b  ldc.i4.0
0x3e9c  ldloc.0
0x3e9d  stelem.ref
0x3e9e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3ea3  ldloc.0
0x3ea4  call     void [mscorlib]System.IO.File::Delete(string)
0x3ea9  ret
```
