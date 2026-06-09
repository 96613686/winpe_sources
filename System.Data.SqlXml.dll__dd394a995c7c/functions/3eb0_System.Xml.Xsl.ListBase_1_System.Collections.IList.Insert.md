# System.Xml.Xsl.ListBase`1::System.Collections.IList.Insert

- ea: `0x3eb0`
- end: `0x3ee0`
- name: `System.Xml.Xsl.ListBase`1::System.Collections.IList.Insert`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3eb0`

## string_xrefs

- `0x3ebd`: `Arg_IncompatibleParamType`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  ldarg.2
0x3eb1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3eb6  call     bool class System.Xml.Xsl.ListBase`1<var<u1>>::IsCompatibleType(object)
0x3ebb  brtrue.s loc_3ED2
0x3ebd  ldstr    aArgIncompatibl// "Arg_IncompatibleParamType"
0x3ec2  call     string [System.Xml]System.Xml.Res::GetString(string)
0x3ec7  ldstr    aValue// "value"
0x3ecc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3ed1  throw
0x3ed2  ldarg.0
0x3ed3  ldarg.1
0x3ed4  ldarg.2
0x3ed5  unbox.any var<u1>
0x3eda  callvirt instance void class System.Xml.Xsl.ListBase`1<var<u1>>::Insert(int32, var<u1>)
0x3edf  ret
```
