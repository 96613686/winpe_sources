# System.Xml.Xsl.ListBase`1::System.Collections.IList.set_Item

- ea: `0x3df0`
- end: `0x3e20`
- name: `System.Xml.Xsl.ListBase`1::System.Collections.IList.set_Item`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3df0`

## string_xrefs

- `0x3dfd`: `Arg_IncompatibleParamType`

## pseudocode

```c

```

## disassembly

```asm
0x3df0  ldarg.2
0x3df1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3df6  call     bool class System.Xml.Xsl.ListBase`1<var<u1>>::IsCompatibleType(object)
0x3dfb  brtrue.s loc_3E12
0x3dfd  ldstr    aArgIncompatibl// "Arg_IncompatibleParamType"
0x3e02  call     string [System.Xml]System.Xml.Res::GetString(string)
0x3e07  ldstr    aValue// "value"
0x3e0c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3e11  throw
0x3e12  ldarg.0
0x3e13  ldarg.1
0x3e14  ldarg.2
0x3e15  unbox.any var<u1>
0x3e1a  callvirt instance void class System.Xml.Xsl.ListBase`1<var<u1>>::set_Item(int32, var<u1>)
0x3e1f  ret
```
