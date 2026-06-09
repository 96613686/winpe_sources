# Microsoft.BIServer.Configuration.RsCatalog::GetCatalogScriptContents

- ea: `0x2d30`
- end: `0x2d89`
- name: `Microsoft.BIServer.Configuration.RsCatalog::GetCatalogScriptContents`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c60`

## callees

- `0x2d30`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x2d35  stloc.0
0x2d36  ldstr    a0Scripts1Sql// "{0}.Scripts.{1}.sql"
0x2d3b  ldloc.0
0x2d3c  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x2d41  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x2d46  ldarg.1
0x2d47  call     string [mscorlib]System.String::Format(string, object, object)
0x2d4c  stloc.1
0x2d4d  ldloc.0
0x2d4e  ldloc.1
0x2d4f  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x2d54  stloc.3
0x2d55  ldloc.3
0x2d56  brtrue.s loc_2D5F
0x2d58  ldloc.1
0x2d59  newobj   instance void [mscorlib]System.Resources.MissingManifestResourceException::.ctor(string)
0x2d5e  throw
0x2d5f  ldloc.3
0x2d60  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x2d65  stloc.s  4
0x2d67  ldloc.s  4
0x2d69  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x2d6e  stloc.2
0x2d6f  leave.s  loc_2D87
0x2d71  ldloc.s  4
0x2d73  brfalse.s loc_2D7C
0x2d75  ldloc.s  4
0x2d77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d7c  endfinally
0x2d7d  ldloc.3
0x2d7e  brfalse.s loc_2D86
0x2d80  ldloc.3
0x2d81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d86  endfinally
0x2d87  ldloc.2
0x2d88  ret
```
