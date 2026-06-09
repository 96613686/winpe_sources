# System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStreamAsync_0

- ea: `0x6b00`
- end: `0x6b42`
- name: `System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStreamAsync_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x6b00`
- `0x6b50`
- `0xb1d0`
- `0xb1e0`
- `0xb3c0`

## string_xrefs

- `0x6b17`: `writeStream`

## pseudocode

```c

```

## disassembly

```asm
0x6b00  ldarg.1
0x6b01  ldnull
0x6b02  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6b07  brfalse.s loc_6B14
0x6b09  ldstr    aType// "type"
0x6b0e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6b13  throw
0x6b14  ldarg.3
0x6b15  brtrue.s loc_6B22
0x6b17  ldstr    aWritestream// "writeStream"
0x6b1c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x6b21  throw
0x6b22  nop
0x6b23  ldarg.0
0x6b24  ldarg.1
0x6b25  ldarg.2
0x6b26  ldarg.3
0x6b27  ldarg.s  4
0x6b29  ldarg.s  6
0x6b2b  call     instance void System.Net.Http.Formatting.BufferedMediaTypeFormatter::WriteToStreamSync(class [mscorlib]System.Type type, object value, class [mscorlib]System.IO.Stream writeStream, class [System.Net.Http]System.Net.Http.HttpContent content, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6b30  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::Completed()
0x6b35  stloc.0
0x6b36  leave.s  loc_6B40
0x6b38  call     class [mscorlib]System.Threading.Tasks.Task System.Threading.Tasks.TaskHelpers::FromError(class [mscorlib]System.Exception exception)
0x6b3d  stloc.0
0x6b3e  leave.s  loc_6B40
0x6b40  ldloc.0
0x6b41  ret
```
