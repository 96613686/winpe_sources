# System.Net.Http.Formatting.XmlMediaTypeFormatter::WriteToStreamAsync

- ea: `0x93b0`
- end: `0x93ff`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::WriteToStreamAsync`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x93b0`
- `0x9400`
- `0xb1b0`
- `0xb1d0`
- `0xb1e0`
- `0xb3c0`

## string_xrefs

- `0x93c7`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x93b0  ldarg.1
0x93b1  ldnull
0x93b2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x93b7  brfalse.s loc_93C4
0x93b9  ldstr    aType// "type"
0x93be  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x93c3  throw
0x93c4  ldarg.3
0x93c5  brtrue.s loc_93D2
0x93c7  ldstr    aWritestream// "writeStream"
0x93cc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x93d1  throw
0x93d2  ldarga.s 6
0x93d4  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x93d9  brfalse.s loc_93E1
0x93db  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::Canceled()
0x93e0  ret
0x93e1  nop
0x93e2  ldarg.0
0x93e3  ldarg.1
0x93e4  ldarg.2
0x93e5  ldarg.3
0x93e6  ldarg.s  4
0x93e8  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content)
0x93ed  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::Completed()
0x93f2  stloc.0
0x93f3  leave.s  loc_93FD
0x93f5  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::FromError(class [mscorlib]System.Exception exception)
0x93fa  stloc.0
0x93fb  leave.s  loc_93FD
0x93fd  ldloc.0
0x93fe  ret
```
