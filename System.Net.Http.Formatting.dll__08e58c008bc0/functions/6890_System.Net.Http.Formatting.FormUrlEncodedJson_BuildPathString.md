# System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString

- ea: `0x6890`
- end: `0x68c9`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6360`
- `0x6460`
- `0x6580`

## callees

- `0x6890`

## pseudocode

```c

```

## disassembly

```asm
0x6890  ldarg.0
0x6891  ldc.i4.0
0x6892  ldelem.ref
0x6893  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x6898  stloc.0
0x6899  ldc.i4.1
0x689a  stloc.1
0x689b  br.s     loc_68BE
0x689d  ldloc.0
0x689e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68a3  ldstr    a0_0// "[{0}]"
0x68a8  ldc.i4.1
0x68a9  newarr   [mscorlib]System.Object
0x68ae  dup
0x68af  ldc.i4.0
0x68b0  ldarg.0
0x68b1  ldloc.1
0x68b2  ldelem.ref
0x68b3  stelem.ref
0x68b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x68b9  pop
0x68ba  ldloc.1
0x68bb  ldc.i4.1
0x68bc  add
0x68bd  stloc.1
0x68be  ldloc.1
0x68bf  ldarg.1
0x68c0  ble.s    loc_689D
0x68c2  ldloc.0
0x68c3  callvirt instance string [mscorlib]System.Object::ToString()
0x68c8  ret
```
