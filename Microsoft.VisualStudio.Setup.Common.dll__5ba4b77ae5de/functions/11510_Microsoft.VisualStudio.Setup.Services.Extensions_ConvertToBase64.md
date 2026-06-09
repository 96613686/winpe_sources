# Microsoft.VisualStudio.Setup.Services.Extensions::ConvertToBase64

- ea: `0x11510`
- end: `0x11589`
- name: `Microsoft.VisualStudio.Setup.Services.Extensions::ConvertToBase64`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x11510`

## string_xrefs

- `0x11566`: `Failed to read {0} bytes from stream. Instead read {1} bytes`

## pseudocode

```c

```

## disassembly

```asm
0x11510  ldarg.0
0x11511  brtrue.s loc_1151E
0x11513  ldstr    aStream// "stream"
0x11518  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1151d  throw
0x1151e  ldarg.0
0x1151f  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x11524  stloc.0
0x11525  ldloc.0
0x11526  ldc.i4   0x7FFFFFFF
0x1152b  conv.i8
0x1152c  ble.s    loc_1154E
0x1152e  ldstr    aCannotConvertA// "Cannot convert a stream longer than ${0"...
0x11533  ldc.i4   0x7FFFFFFF
0x11538  box      [mscorlib]System.Int32
0x1153d  ldloc.0
0x1153e  box      [mscorlib]System.Int64
0x11543  call     string [mscorlib]System.String::Format(string, object, object)
0x11548  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x1154d  throw
0x1154e  ldloc.0
0x1154f  conv.i4
0x11550  stloc.1
0x11551  ldloc.1
0x11552  newarr   [mscorlib]System.Byte
0x11557  stloc.2
0x11558  ldarg.0
0x11559  ldloc.2
0x1155a  ldc.i4.0
0x1155b  ldloc.1
0x1155c  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x11561  stloc.3
0x11562  ldloc.3
0x11563  ldloc.1
0x11564  beq.s    loc_11582
0x11566  ldstr    aFailedToRead0B// "Failed to read {0} bytes from stream. I"...
0x1156b  ldloc.1
0x1156c  box      [mscorlib]System.Int32
0x11571  ldloc.3
0x11572  box      [mscorlib]System.Int32
0x11577  call     string [mscorlib]System.String::Format(string, object, object)
0x1157c  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x11581  throw
0x11582  ldloc.2
0x11583  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x11588  ret
```
