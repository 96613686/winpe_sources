# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStreamAsync

- ea: `0x57d0`
- end: `0x581f`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStreamAsync`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x7a00`

## callees

- `0x57d0`
- `0x5820`
- `0xb1b0`
- `0xb1d0`
- `0xb1e0`
- `0xb3c0`

## string_xrefs

- `0x57e7`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x57d0  ldarg.1
0x57d1  ldnull
0x57d2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x57d7  brfalse.s loc_57E4
0x57d9  ldstr    aType// "type"
0x57de  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x57e3  throw
0x57e4  ldarg.3
0x57e5  brtrue.s loc_57F2
0x57e7  ldstr    aWritestream// "writeStream"
0x57ec  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x57f1  throw
0x57f2  ldarga.s 6
0x57f4  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x57f9  brfalse.s loc_5801
0x57fb  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::Canceled()
0x5800  ret
0x5801  nop
0x5802  ldarg.0
0x5803  ldarg.1
0x5804  ldarg.2
0x5805  ldarg.3
0x5806  ldarg.s  4
0x5808  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::WriteToStream(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content)
0x580d  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::Completed()
0x5812  stloc.0
0x5813  leave.s  loc_581D
0x5815  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::FromError(class [mscorlib]System.Exception exception)
0x581a  stloc.0
0x581b  leave.s  loc_581D
0x581d  ldloc.0
0x581e  ret
```
