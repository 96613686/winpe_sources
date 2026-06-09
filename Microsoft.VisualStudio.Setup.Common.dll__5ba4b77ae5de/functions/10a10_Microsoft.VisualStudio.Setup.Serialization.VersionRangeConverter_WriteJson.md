# Microsoft.VisualStudio.Setup.Serialization.VersionRangeConverter::WriteJson

- ea: `0x10a10`
- end: `0x10a54`
- name: `Microsoft.VisualStudio.Setup.Serialization.VersionRangeConverter::WriteJson`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x10a10`

## string_xrefs

- `0x10a11`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10a10  ldarg.1
0x10a11  ldstr    aWriter// "writer"
0x10a16  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x10a1b  ldarg.2
0x10a1c  brtrue.s loc_10A25
0x10a1e  ldarg.1
0x10a1f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteNull()
0x10a24  ret
0x10a25  ldarg.2
0x10a26  isinst   Microsoft.VisualStudio.Setup.VersionRange
0x10a2b  brfalse.s loc_10A3A
0x10a2d  ldarg.1
0x10a2e  ldarg.2
0x10a2f  callvirt instance string [mscorlib]System.Object::ToString()
0x10a34  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x10a39  ret
0x10a3a  ldstr    aExpected0Value// "Expected {0} value type."
0x10a3f  ldtoken  Microsoft.VisualStudio.Setup.VersionRange
0x10a44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a49  call     string [mscorlib]System.String::Format(string, object)
0x10a4e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0x10a53  throw
```
