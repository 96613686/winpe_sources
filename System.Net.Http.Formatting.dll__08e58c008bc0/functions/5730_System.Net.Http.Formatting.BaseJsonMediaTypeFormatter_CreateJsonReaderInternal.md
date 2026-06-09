# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonReaderInternal

- ea: `0x5730`
- end: `0x5758`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonReaderInternal`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x5680`

## callees

- `0x3610`
- `0x5730`
- `0x5760`
- `0xb4b0`

## string_xrefs

- `0x574a`: `CreateJsonReader`

## pseudocode

```c

```

## disassembly

```asm
0x5730  ldarg.0
0x5731  ldarg.1
0x5732  ldarg.2
0x5733  ldarg.3
0x5734  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonReader System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonReader(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x5739  stloc.0
0x573a  ldloc.0
0x573b  brtrue.s loc_5756
0x573d  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonReaderFactoryReturnedNull()
0x5742  ldc.i4.1
0x5743  newarr   [mscorlib]System.Object
0x5748  dup
0x5749  ldc.i4.0
0x574a  ldstr    aCreatejsonread// "CreateJsonReader"
0x574f  stelem.ref
0x5750  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x5755  throw
0x5756  ldloc.0
0x5757  ret
```
