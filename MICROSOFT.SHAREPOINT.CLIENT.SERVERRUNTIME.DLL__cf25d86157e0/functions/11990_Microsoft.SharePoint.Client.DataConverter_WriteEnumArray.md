# Microsoft.SharePoint.Client.DataConverter::WriteEnumArray

- ea: `0x11990`
- end: `0x119ef`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteEnumArray`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x11990`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13560`

## string_xrefs

- `0x11993`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x11990  ldarg.0
0x11991  brtrue.s loc_1199E
0x11993  ldstr    aWriter// "writer"
0x11998  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1199d  throw
0x1199e  ldarg.1
0x1199f  brfalse.s loc_119B2
0x119a1  ldtoken  mvar<u1>
0x119a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x119ab  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x119b0  brtrue.s loc_119B9
0x119b2  ldarg.0
0x119b3  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x119b8  ret
0x119b9  ldarg.0
0x119ba  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x119bf  ldarg.1
0x119c0  stloc.1
0x119c1  ldc.i4.0
0x119c2  stloc.2
0x119c3  br.s     loc_119E2
0x119c5  ldloc.1
0x119c6  ldloc.2
0x119c7  ldelem   mvar<u1>
0x119cc  stloc.0
0x119cd  ldarg.0
0x119ce  ldloc.0
0x119cf  box      mvar<u1>
0x119d4  castclass [mscorlib]System.Enum
0x119d9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(class [mscorlib]System.Enum value)
0x119de  ldloc.2
0x119df  ldc.i4.1
0x119e0  add
0x119e1  stloc.2
0x119e2  ldloc.2
0x119e3  ldloc.1
0x119e4  ldlen
0x119e5  conv.i4
0x119e6  blt.s    loc_119C5
0x119e8  ldarg.0
0x119e9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x119ee  ret
```
