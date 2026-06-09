# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonWriterInternal

- ea: `0x58b0`
- end: `0x58d8`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonWriterInternal`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x5840`

## callees

- `0x3630`
- `0x58b0`
- `0x58e0`
- `0xb4b0`

## string_xrefs

- `0x58ca`: `CreateJsonWriter`

## pseudocode

```c

```

## disassembly

```asm
0x58b0  ldarg.0
0x58b1  ldarg.1
0x58b2  ldarg.2
0x58b3  ldarg.3
0x58b4  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateJsonWriter(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream writeStream, class [mscorlib]System.Text.Encoding effectiveEncoding)
0x58b9  stloc.0
0x58ba  ldloc.0
0x58bb  brtrue.s loc_58D6
0x58bd  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonWriterFactoryReturnedNull()
0x58c2  ldc.i4.1
0x58c3  newarr   [mscorlib]System.Object
0x58c8  dup
0x58c9  ldc.i4.0
0x58ca  ldstr    aCreatejsonwrit// "CreateJsonWriter"
0x58cf  stelem.ref
0x58d0  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x58d5  throw
0x58d6  ldloc.0
0x58d7  ret
```
