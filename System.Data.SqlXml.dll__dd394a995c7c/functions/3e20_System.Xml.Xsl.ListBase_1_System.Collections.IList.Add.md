# System.Xml.Xsl.ListBase`1::System.Collections.IList.Add

- ea: `0x3e20`
- end: `0x3e57`
- name: `System.Xml.Xsl.ListBase`1::System.Collections.IList.Add`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3e20`

## string_xrefs

- `0x3e2d`: `Arg_IncompatibleParamType`

## pseudocode

```c

```

## disassembly

```asm
0x3e20  ldarg.1
0x3e21  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e26  call     bool class System.Xml.Xsl.ListBase`1<var<u1>>::IsCompatibleType(object)
0x3e2b  brtrue.s loc_3E42
0x3e2d  ldstr    aArgIncompatibl// "Arg_IncompatibleParamType"
0x3e32  call     string [System.Xml]System.Xml.Res::GetString(string)
0x3e37  ldstr    aValue// "value"
0x3e3c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3e41  throw
0x3e42  ldarg.0
0x3e43  ldarg.1
0x3e44  unbox.any var<u1>
0x3e49  callvirt instance void class System.Xml.Xsl.ListBase`1<var<u1>>::Add(var<u1>)
0x3e4e  ldarg.0
0x3e4f  callvirt instance int32 class System.Xml.Xsl.ListBase`1<var<u1>>::get_Count()
0x3e54  ldc.i4.1
0x3e55  sub
0x3e56  ret
```
