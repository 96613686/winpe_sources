# Microsoft.BIServer.Configuration.XmlConfigFile::AddUrlApplications

- ea: `0x4080`
- end: `0x40d0`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::AddUrlApplications`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x3fa0`
- `0x3fc0`
- `0x4080`

## string_xrefs

- `0x4080`: `Delete existing URL applications`

## pseudocode

```c

```

## disassembly

```asm
0x4080  ldstr    aDeleteExisting// "Delete existing URL applications"
0x4085  call     T0x2B000015
0x408a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x408f  ldarg.0
0x4090  call     instance void Microsoft.BIServer.Configuration.XmlConfigFile::DeleteUrlApplications()
0x4095  ldstr    aSettingUrlAppl// "Setting URL applications"
0x409a  call     T0x2B000015
0x409f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x40a4  ldarg.1
0x40a5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x40aa  stloc.0
0x40ab  br.s     loc_40BB
0x40ad  ldloc.0
0x40ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.Configuration.Application>::get_Current()
0x40b3  stloc.1
0x40b4  ldarg.0
0x40b5  ldloc.1
0x40b6  call     instance void Microsoft.BIServer.Configuration.XmlConfigFile::AddUrlApplicationNode(class Microsoft.BIServer.Configuration.Application urlUrlApplication)
0x40bb  ldloc.0
0x40bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x40c1  brtrue.s loc_40AD
0x40c3  leave.s  loc_40CF
0x40c5  ldloc.0
0x40c6  brfalse.s loc_40CE
0x40c8  ldloc.0
0x40c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40ce  endfinally
0x40cf  ret
```
