# Microsoft.VisualStudio.Setup.Serialization.VersionRangeConverter::ReadJson

- ea: `0x10990`
- end: `0x10a02`
- name: `Microsoft.VisualStudio.Setup.Serialization.VersionRangeConverter::ReadJson`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc570`
- `0x10990`

## string_xrefs

- `0x10991`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x10990  ldarg.1
0x10991  ldstr    aReader// "reader"
0x10996  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1099b  ldarg.1
0x1099c  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x109a1  ldc.i4.s 0xB
0x109a3  bne.un.s loc_109A7
0x109a5  ldnull
0x109a6  ret
0x109a7  ldarg.1
0x109a8  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0x109ad  ldc.i4.s 9
0x109af  bne.un.s loc_109E6
0x109b1  ldarg.1
0x109b2  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0x109b7  castclass [mscorlib]System.String
0x109bc  call     class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.VersionRange::Parse(string version)
0x109c1  stloc.0
0x109c2  leave.s  loc_10A00
0x109c4  stloc.1
0x109c5  ldstr    aErrorParsing0S// "Error parsing {0} string: {1}"
0x109ca  ldtoken  Microsoft.VisualStudio.Setup.VersionRange
0x109cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x109d4  ldloc.1
0x109d5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x109da  call     string [mscorlib]System.String::Format(string, object, object)
0x109df  ldloc.1
0x109e0  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string, class [mscorlib]System.Exception)
0x109e5  throw
0x109e6  ldstr    aExpected0Value// "Expected {0} value type."
0x109eb  ldtoken  Microsoft.VisualStudio.Setup.VersionRange
0x109f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x109f5  call     string [mscorlib]System.String::Format(string, object)
0x109fa  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0x109ff  throw
0x10a00  ldloc.0
0x10a01  ret
```
