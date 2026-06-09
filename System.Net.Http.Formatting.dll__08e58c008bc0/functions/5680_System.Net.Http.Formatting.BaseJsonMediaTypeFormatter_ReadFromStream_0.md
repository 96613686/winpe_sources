# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream_0

- ea: `0x5680`
- end: `0x572a`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream_0`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x5610`
- `0x59e0`
- `0x7980`

## callees

- `0x5680`
- `0x5730`
- `0x5770`
- `0xb3c0`
- `0xd500`

## string_xrefs

- `0x56a5`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x5680  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x5685  stloc.0
0x5686  ldloc.0
0x5687  ldarg.s  4
0x5689  stfld    class System.Net.Http.Formatting.IFormatterLogger <>c__DisplayClass16_0::formatterLogger
0x568e  ldarg.1
0x568f  ldnull
0x5690  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5695  brfalse.s loc_56A2
0x5697  ldstr    aType// "type"
0x569c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x56a1  throw
0x56a2  ldarg.2
0x56a3  brtrue.s loc_56B0
0x56a5  ldstr    aReadstream// "readStream"
0x56aa  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x56af  throw
0x56b0  ldarg.3
0x56b1  brtrue.s loc_56BE
0x56b3  ldstr    aEffectiveencod// "effectiveEncoding"
0x56b8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x56bd  throw
0x56be  ldarg.0
0x56bf  ldarg.1
0x56c0  ldarg.2
0x56c1  ldarg.3
0x56c2  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonReaderInternal(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x56c7  stloc.1
0x56c8  ldloc.1
0x56c9  ldc.i4.0
0x56ca  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonReader::set_CloseInput(bool)
0x56cf  ldloc.1
0x56d0  ldarg.0
0x56d1  ldfld    int32 System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_maxDepth
0x56d6  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x56db  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonReader::set_MaxDepth(valuetype [mscorlib]System.Nullable`1<int32>)
0x56e0  ldarg.0
0x56e1  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonSerializerInternal()
0x56e6  stloc.2
0x56e7  ldnull
0x56e8  stloc.3
0x56e9  ldloc.0
0x56ea  ldfld    class System.Net.Http.Formatting.IFormatterLogger <>c__DisplayClass16_0::formatterLogger
0x56ef  brfalse.s loc_5705
0x56f1  ldloc.0
0x56f2  ldftn    instance void <>c__DisplayClass16_0::<ReadFromStream>b__0(object sender, class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs e)
0x56f8  newobj   instance void class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>::.ctor(object, native int)
0x56fd  stloc.3
0x56fe  ldloc.2
0x56ff  ldloc.3
0x5700  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::add_Error(class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>)
0x5705  nop
0x5706  ldloc.2
0x5707  ldloc.1
0x5708  ldarg.1
0x5709  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Deserialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, class [mscorlib]System.Type)
0x570e  stloc.s  4
0x5710  leave.s  loc_5727
0x5712  ldloc.3
0x5713  brfalse.s loc_571C
0x5715  ldloc.2
0x5716  ldloc.3
0x5717  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::remove_Error(class [mscorlib]System.EventHandler`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.ErrorEventArgs>)
0x571c  endfinally
0x571d  ldloc.1
0x571e  brfalse.s loc_5726
0x5720  ldloc.1
0x5721  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5726  endfinally
0x5727  ldloc.s  4
0x5729  ret
```
